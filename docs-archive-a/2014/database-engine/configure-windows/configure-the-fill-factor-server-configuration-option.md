---
title: Konfigurieren der Serverkonfigurationsoption „Füllfaktor“ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- fill factor option [SQL Server]
ms.assetid: b920ec34-ba8b-4bb8-af53-a3ffd06bafa6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 02258c92b4a09277d371e605fd4729ba9fda3461
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618903"
---
# <a name="configure-the-fill-factor-server-configuration-option"></a><span data-ttu-id="b994e-102">Konfigurieren der Serverkonfigurationsoption Füllfaktor</span><span class="sxs-lookup"><span data-stu-id="b994e-102">Configure the fill factor Server Configuration Option</span></span>
  <span data-ttu-id="b994e-103">In diesem Thema wird beschrieben, wie die Serverkonfigurationsoption **Füllfaktor** in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="b994e-103">This topic describes how to configure the **fill factor** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="b994e-104">Der Füllfaktor wird zur erweiterten Leistungsoptimierung beim Speichern von Indexdaten bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="b994e-104">Fill factor is provided for fine-tuning index data storage and performance.</span></span> <span data-ttu-id="b994e-105">Wenn ein Index erstellt oder neu erstellt wird, bestimmt der Füllfaktorwert den prozentualen Speicherplatz, der auf jeder Blattebenenseite mit Daten gefüllt werden soll; der übrige freie Speicherplatz wird für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="b994e-105">When an index is created or rebuilt, the fill-factor value determines the percentage of space on each leaf-level page to be filled with data, reserving the rest as free space for future growth.</span></span> <span data-ttu-id="b994e-106">Weitere Informationen finden Sie unter [Angeben des Füllfaktors für einen Index](../../relational-databases/indexes/specify-fill-factor-for-an-index.md).</span><span class="sxs-lookup"><span data-stu-id="b994e-106">For more information, see [Specify Fill Factor for an Index](../../relational-databases/indexes/specify-fill-factor-for-an-index.md).</span></span>  
  
 <span data-ttu-id="b994e-107">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="b994e-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b994e-108">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="b994e-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b994e-109">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="b994e-109">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="b994e-110">Security</span><span class="sxs-lookup"><span data-stu-id="b994e-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b994e-111">**So konfigurieren Sie die Option Füllfaktor mit:**</span><span class="sxs-lookup"><span data-stu-id="b994e-111">**To configure the fill factor option, using:**</span></span>  
  
     [<span data-ttu-id="b994e-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b994e-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b994e-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b994e-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="b994e-114">**Nachverfolgung:**  [Nach dem Konfigurieren der Option „Füllfaktor“](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="b994e-114">**Follow Up:**  [After you configure the fill factor option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b994e-115">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="b994e-115">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="b994e-116">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="b994e-116">Recommendations</span></span>  
  
-   <span data-ttu-id="b994e-117">Diese Option ist eine erweiterte Option und sollte ausschließlich von einem erfahrenen Datenbankadministrator oder einem zertifizierten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Techniker geändert werden.</span><span class="sxs-lookup"><span data-stu-id="b994e-117">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b994e-118">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="b994e-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b994e-119">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="b994e-119">Permissions</span></span>  
 <span data-ttu-id="b994e-120">Die Ausführungsberechtigungen für **sp_configure** ohne Parameter oder nur mit dem ersten Parameter werden standardmäßig allen Benutzern erteilt.</span><span class="sxs-lookup"><span data-stu-id="b994e-120">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="b994e-121">Zum Ausführen von **sp_configure** mit beiden Parametern zum Ändern einer Konfigurationsoption oder zum Ausführen der RECONFIGURE-Anweisung muss einem Benutzer die ALTER SETTINGS-Berechtigung auf Serverebene erteilt worden sein.</span><span class="sxs-lookup"><span data-stu-id="b994e-121">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="b994e-122">Die ALTER SETTINGS-Berechtigung ist in den festen Serverrollen **sysadmin** und **serveradmin** eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="b994e-122">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b994e-123">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b994e-123">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-fill-factor-option"></a><span data-ttu-id="b994e-124">So konfigurieren Sie die Option Füllfaktor</span><span class="sxs-lookup"><span data-stu-id="b994e-124">To configure the fill factor option</span></span>  
  
1.  <span data-ttu-id="b994e-125">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf einen Server, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="b994e-125">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="b994e-126">Klicken Sie auf den Knoten **Datenbankeinstellungen** .</span><span class="sxs-lookup"><span data-stu-id="b994e-126">Click the **Database Settings** node.</span></span>  
  
3.  <span data-ttu-id="b994e-127">Geben Sie im Feld **Standardfüllfaktor für Indizes** den gewünschten Füllfaktor für den Index ein, oder wählen Sie ihn aus.</span><span class="sxs-lookup"><span data-stu-id="b994e-127">In the **Default index fill factor** box, type or select the index fill factor that you want.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b994e-128">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b994e-128">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-fill-factor-option"></a><span data-ttu-id="b994e-129">So konfigurieren Sie die Option Füllfaktor</span><span class="sxs-lookup"><span data-stu-id="b994e-129">To configure the fill factor option</span></span>  
  
1.  <span data-ttu-id="b994e-130">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="b994e-130">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b994e-131">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="b994e-131">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b994e-132">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="b994e-132">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="b994e-133">In diesem Beispiel wird gezeigt, wie [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) verwendet wird, um den Wert der Option `fill factor` auf `100`festzulegen.</span><span class="sxs-lookup"><span data-stu-id="b994e-133">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `fill factor` option to `100`.</span></span>  
  
```sql  
Use AdventureWorks2012;  
GO  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'fill factor', 100;  
GO  
RECONFIGURE;  
GO  
```  
  
 <span data-ttu-id="b994e-134">Weitere Informationen finden Sie unter [Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md)angezeigt oder konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="b994e-134">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-fill-factor-option"></a><a name="FollowUp"></a><span data-ttu-id="b994e-135">Nächster Schritt: Nach dem Konfigurieren der Option „Füllfaktor“</span><span class="sxs-lookup"><span data-stu-id="b994e-135">Follow Up: After you configure the fill factor option</span></span>  
 <span data-ttu-id="b994e-136">Der Server muss neu gestartet werden, bevor die Einstellung wirksam werden kann.</span><span class="sxs-lookup"><span data-stu-id="b994e-136">The server must be restarted before the setting can take effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b994e-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b994e-137">See Also</span></span>  
 <span data-ttu-id="b994e-138">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b994e-138">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="b994e-139">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b994e-139">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span></span>  
 <span data-ttu-id="b994e-140">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b994e-140">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span></span>  
 <span data-ttu-id="b994e-141">[Angeben des Füllfaktors für einen Index](../../relational-databases/indexes/specify-fill-factor-for-an-index.md) </span><span class="sxs-lookup"><span data-stu-id="b994e-141">[Specify Fill Factor for an Index](../../relational-databases/indexes/specify-fill-factor-for-an-index.md) </span></span>  
 <span data-ttu-id="b994e-142">[Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b994e-142">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="b994e-143">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b994e-143">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="b994e-144">sys.indexes &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b994e-144">sys.indexes &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-indexes-transact-sql)  
  
  
