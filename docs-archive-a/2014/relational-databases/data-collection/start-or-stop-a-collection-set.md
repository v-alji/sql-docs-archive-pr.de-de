---
title: Starten oder Beenden eines Sammlungssatzes | Microsoft Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- collection sets [SQL Server], stopping
- collection sets [SQL Server], starting
ms.assetid: 48a7b2fe-6bc3-4278-a7ec-1babc1290345
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e37d4b2edcd7a6e048c405b072bcbf9b1fef78c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621020"
---
# <a name="start-or-stop-a-collection-set"></a><span data-ttu-id="9ab9d-102">Starten oder Beenden eines Sammlungssatzes</span><span class="sxs-lookup"><span data-stu-id="9ab9d-102">Start or Stop a Collection Set</span></span>
  <span data-ttu-id="9ab9d-103">In diesem Thema wird beschrieben, wie ein Sammlungssatz in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]gestartet oder angehalten wird.</span><span class="sxs-lookup"><span data-stu-id="9ab9d-103">This topic describes how to start or stop a collection set in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="9ab9d-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="9ab9d-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="9ab9d-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="9ab9d-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="9ab9d-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="9ab9d-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="9ab9d-107">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="9ab9d-107">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="9ab9d-108">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="9ab9d-108">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="9ab9d-109">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="9ab9d-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="9ab9d-110">**So starten oder halten Sie einen Sammlungssatz an, und zwar mit**</span><span class="sxs-lookup"><span data-stu-id="9ab9d-110">**To start or stop a collection set, using:**</span></span>  
  
     [<span data-ttu-id="9ab9d-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9ab9d-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="9ab9d-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9ab9d-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="9ab9d-113">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="9ab9d-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="9ab9d-114">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="9ab9d-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="9ab9d-115">Gespeicherte Prozeduren für den Datensammler und Katalogsichten werden in der **msdb** -Datenbank gespeichert.</span><span class="sxs-lookup"><span data-stu-id="9ab9d-115">Data Collector stored procedures and catalog views are stored in the **msdb** database.</span></span>  
  
-   <span data-ttu-id="9ab9d-116">Im Gegensatz zu regulären gespeicherten Prozeduren werden die Parameter für die gespeicherten Prozeduren des Datensammlers genau eingegeben und unterstützen die automatische Datentypkonvertierung nicht.</span><span class="sxs-lookup"><span data-stu-id="9ab9d-116">Unlike regular stored procedures, the parameters for data collector stored procedures are strictly typed and do not support automatic data type conversion.</span></span> <span data-ttu-id="9ab9d-117">Wenn diese Parameter nicht mit den richtigen Datentypen für Eingabeparameter aufgerufen werden, wie in der Argumentbeschreibung angegeben, gibt die gespeicherte Prozedur einen Fehler zurück.</span><span class="sxs-lookup"><span data-stu-id="9ab9d-117">If these parameters are not called with the correct input parameter data types, as specified in the argument description, the stored procedure returns an error.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="9ab9d-118">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="9ab9d-118">Prerequisites</span></span>  
  
-   <span data-ttu-id="9ab9d-119">Der SQL Server-Agent muss gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="9ab9d-119">SQL Server Agent must be started.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="9ab9d-120">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="9ab9d-120">Recommendations</span></span>  
  
-   <span data-ttu-id="9ab9d-121">Fragen Sie die [syscollector_collection_sets](/sql/relational-databases/system-catalog-views/syscollector-collection-sets-transact-sql) -Katalogsicht ab, um Informationen zu Sammlungssätzen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="9ab9d-121">To obtain information about collection sets, query the [syscollector_collection_sets](/sql/relational-databases/system-catalog-views/syscollector-collection-sets-transact-sql) catalog view.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="9ab9d-122">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="9ab9d-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="9ab9d-123">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="9ab9d-123">Permissions</span></span>  
 <span data-ttu-id="9ab9d-124">Erfordert die Mitgliedschaft in der festen Datenbankrolle **dc_operator** .</span><span class="sxs-lookup"><span data-stu-id="9ab9d-124">Requires membership in the **dc_operator** fixed database role.</span></span> <span data-ttu-id="9ab9d-125">Wenn der Sammlungssatz über kein Proxykonto verfügt, ist die Mitgliedschaft in der festen Serverrolle **sysadmin** erforderlich. Beispiele</span><span class="sxs-lookup"><span data-stu-id="9ab9d-125">If the collection set does not have a proxy account, membership in the **sysadmin** fixed server role is required.Examples</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="9ab9d-126">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9ab9d-126">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-start-a-collection-set"></a><span data-ttu-id="9ab9d-127">So starten Sie einen Sammlungssatz</span><span class="sxs-lookup"><span data-stu-id="9ab9d-127">To start a collection set</span></span>  
  
1.  <span data-ttu-id="9ab9d-128">Erweitern Sie im Objekt-Explorer nacheinander die Knoten **Verwaltung** , **Datensammlung**und dann **Systemdaten-Sammlungssätze**.</span><span class="sxs-lookup"><span data-stu-id="9ab9d-128">In Object Explorer, expand the **Management** node, expand **Data Collection**, and then expand **System Data Collection Sets**.</span></span>  
  
2.  <span data-ttu-id="9ab9d-129">Klicken Sie mit der rechten Maustaste auf den Sammlungssatz, den Sie starten möchten, und klicken Sie anschließend auf **Datenauflistsatz starten**.</span><span class="sxs-lookup"><span data-stu-id="9ab9d-129">Right-click the collection set that you want to start, and then click **Start Data Collection Set**.</span></span>  
  
     <span data-ttu-id="9ab9d-130">Ein Meldungsfeld mit dem Ergebnis des Vorgangs wird angezeigt, und ein grüner Pfeil auf dem Symbol für den Sammlungssatz weist darauf hin, dass der Sammlungssatz gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="9ab9d-130">A message box displays the results of this action, and a green arrow on the icon for the collection set indicates that the collection set has started.</span></span>  
  
#### <a name="to-stop-a-collection-set"></a><span data-ttu-id="9ab9d-131">So beenden Sie einen Sammlungssatz</span><span class="sxs-lookup"><span data-stu-id="9ab9d-131">To stop a collection set</span></span>  
  
1.  <span data-ttu-id="9ab9d-132">Erweitern Sie im Objekt-Explorer nacheinander die Knoten **Verwaltung** , **Datensammlung**und dann **Systemdaten-Sammlungssätze**.</span><span class="sxs-lookup"><span data-stu-id="9ab9d-132">In Object Explorer, expand the **Management** node, expand **Data Collection**, and then expand **System Data Collection Sets**.</span></span>  
  
2.  <span data-ttu-id="9ab9d-133">Klicken Sie mit der rechten Maustaste auf den Sammlungssatz, den Sie beenden möchten, und klicken Sie anschließend auf **Datensammlungssatz beenden**.</span><span class="sxs-lookup"><span data-stu-id="9ab9d-133">Right-click the collection set that you want to stop, and then click **Stop Data Collection Set**.</span></span>  
  
     <span data-ttu-id="9ab9d-134">Ein Meldungsfeld mit den Ergebnissen dieses Vorgangs wird angezeigt, und ein roter Kreis auf dem Symbol für den Sammlungssatz weist darauf hin, dass der Sammlungssatz beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="9ab9d-134">A message box displays the results of this action, and a red circle on the icon for the collection set indicates that the collection set has stopped.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="9ab9d-135">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9ab9d-135">Using Transact-SQL</span></span>  
  
#### <a name="to-start-a-collection-set"></a><span data-ttu-id="9ab9d-136">So starten Sie einen Sammlungssatz</span><span class="sxs-lookup"><span data-stu-id="9ab9d-136">To start a collection set</span></span>  
  
1.  <span data-ttu-id="9ab9d-137">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="9ab9d-137">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="9ab9d-138">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="9ab9d-138">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="9ab9d-139">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="9ab9d-139">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="9ab9d-140">In diesem Beispiel wird [sp_syscollector_start_collection_set](/sql/relational-databases/system-stored-procedures/sp-syscollector-start-collection-set-transact-sql) verwendet, um den Sammlungssatz zu starten, der über die ID von `1`verfügt.</span><span class="sxs-lookup"><span data-stu-id="9ab9d-140">This example uses [sp_syscollector_start_collection_set](/sql/relational-databases/system-stored-procedures/sp-syscollector-start-collection-set-transact-sql) to start the collection set that has the ID of `1`.</span></span>  
  
```sql  
USE msdb;  
GO  
EXEC sp_syscollector_start_collection_set @collection_set_id = 1;  
```  
  
#### <a name="to-stop-a-collection-set"></a><span data-ttu-id="9ab9d-141">So beenden Sie einen Sammlungssatz</span><span class="sxs-lookup"><span data-stu-id="9ab9d-141">To stop a collection set</span></span>  
  
1.  <span data-ttu-id="9ab9d-142">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="9ab9d-142">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="9ab9d-143">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="9ab9d-143">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="9ab9d-144">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="9ab9d-144">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="9ab9d-145">In diesem Beispiel wird [sp_syscollector_stop_collection_set](/sql/relational-databases/system-stored-procedures/sp-syscollector-stop-collection-set-transact-sql) verwendet, um den Sammlungssatz anzuhalten, der über die ID von `1`verfügt.</span><span class="sxs-lookup"><span data-stu-id="9ab9d-145">This example uses [sp_syscollector_stop_collection_set](/sql/relational-databases/system-stored-procedures/sp-syscollector-stop-collection-set-transact-sql) to stop the collection set that has the ID of `1`.</span></span>  
  
```sql  
USE msdb;  
GO  
EXEC sp_syscollector_stop_collection_set @collection_set_id = 1;  
```  
  
## <a name="see-also"></a><span data-ttu-id="9ab9d-146">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9ab9d-146">See Also</span></span>  
 <span data-ttu-id="9ab9d-147">[Sichten des Datensammlers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/data-collector-views-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9ab9d-147">[Data Collector Views &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/data-collector-views-transact-sql) </span></span>  
 [<span data-ttu-id="9ab9d-148">Datensammlung</span><span class="sxs-lookup"><span data-stu-id="9ab9d-148">Data Collection</span></span>](data-collection.md)  
  
  
