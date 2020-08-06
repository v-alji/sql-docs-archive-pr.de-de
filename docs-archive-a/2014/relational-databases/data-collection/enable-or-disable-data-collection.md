---
title: Aktivieren oder Deaktivieren der Datensammlung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- data collector [SQL Server], disabling
- data collector [SQL Server], enabling
ms.assetid: 0137971b-fb48-4a3e-822a-3df2b9bb09d7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: af5cc647a63d3a9451086fc9e2211dec809e88fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609906"
---
# <a name="enable-or-disable-data-collection"></a><span data-ttu-id="b191d-102">Aktivieren oder Deaktivieren der Datensammlung</span><span class="sxs-lookup"><span data-stu-id="b191d-102">Enable or Disable Data Collection</span></span>
  <span data-ttu-id="b191d-103">In diesem Thema wird beschrieben, wie die Datensammlung in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]aktiviert oder deaktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="b191d-103">This topic describes how to enable or disable data collection in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="b191d-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="b191d-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b191d-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="b191d-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b191d-106">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="b191d-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b191d-107">**So aktivieren oder deaktivieren Sie die Datensammlung mit**</span><span class="sxs-lookup"><span data-stu-id="b191d-107">**To enable or disable data collection, using:**</span></span>  
  
     [<span data-ttu-id="b191d-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b191d-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b191d-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b191d-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b191d-110">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="b191d-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b191d-111">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="b191d-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b191d-112">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="b191d-112">Permissions</span></span>  
 <span data-ttu-id="b191d-113">Damit diese Prozedur ausgeführt werden kann, ist die Mitgliedschaft in der festen Datenbankrolle **dc_admin** oder **dc_operator** (mit EXECUTE-Berechtigung) erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b191d-113">Requires membership in the **dc_admin** or **dc_operator** (with EXECUTE permission) fixed database role to execute this procedure.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b191d-114">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b191d-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-enable-the-data-collector"></a><span data-ttu-id="b191d-115">So aktivieren Sie den Datensammler</span><span class="sxs-lookup"><span data-stu-id="b191d-115">To enable the data collector</span></span>  
  
1.  <span data-ttu-id="b191d-116">Erweitern Sie im Objekt-Explorer den Knoten **Verwaltung** .</span><span class="sxs-lookup"><span data-stu-id="b191d-116">In Object Explorer, expand the **Management** node.</span></span>  
  
2.  <span data-ttu-id="b191d-117">Klicken Sie mit der rechten Maustaste auf **Datensammlung**, und klicken Sie anschließend auf **Datensammlung aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="b191d-117">Right-click **Data Collection**, and then click **Enable Data Collection**.</span></span>  
  
#### <a name="to-disable-the-data-collector"></a><span data-ttu-id="b191d-118">So deaktivieren Sie den Datensammler</span><span class="sxs-lookup"><span data-stu-id="b191d-118">To disable the data collector</span></span>  
  
1.  <span data-ttu-id="b191d-119">Erweitern Sie im Objekt-Explorer den Knoten **Verwaltung** .</span><span class="sxs-lookup"><span data-stu-id="b191d-119">In Object Explorer, expand the **Management** node.</span></span>  
  
2.  <span data-ttu-id="b191d-120">Klicken Sie mit der rechten Maustaste auf **Datensammlung**, und klicken Sie anschließend auf **Datensammlung deaktivieren**.</span><span class="sxs-lookup"><span data-stu-id="b191d-120">Right-click **Data Collection**, and then click **Disable Data Collection**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b191d-121">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b191d-121">Using Transact-SQL</span></span>  
  
#### <a name="to-enable-the-data-collector"></a><span data-ttu-id="b191d-122">So aktivieren Sie den Datensammler</span><span class="sxs-lookup"><span data-stu-id="b191d-122">To enable the data collector</span></span>  
  
1.  <span data-ttu-id="b191d-123">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="b191d-123">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b191d-124">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="b191d-124">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b191d-125">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="b191d-125">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="b191d-126">In diesem Beispiel wird der Datensammler mithilfe von [sp_syscollector_enable_collector](/sql/relational-databases/system-stored-procedures/sp-syscollector-enable-collector-transact-sql) aktiviert.</span><span class="sxs-lookup"><span data-stu-id="b191d-126">This example uses [sp_syscollector_enable_collector](/sql/relational-databases/system-stored-procedures/sp-syscollector-enable-collector-transact-sql) to enable the data collector.</span></span>  
  
```sql  
USE msdb;  
GO  
EXEC dbo.sp_syscollector_enable_collector ;  
```  
  
#### <a name="to-disable-the-data-collector"></a><span data-ttu-id="b191d-127">So deaktivieren Sie den Datensammler</span><span class="sxs-lookup"><span data-stu-id="b191d-127">To disable the data collector</span></span>  
  
1.  <span data-ttu-id="b191d-128">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="b191d-128">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b191d-129">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="b191d-129">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b191d-130">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="b191d-130">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="b191d-131">In diesem Beispiel wird der Datensammler mithilfe von [sp_syscollector_disable_collector](/sql/relational-databases/system-stored-procedures/sp-syscollector-disable-collector-transact-sql) deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="b191d-131">This example uses [sp_syscollector_disable_collector](/sql/relational-databases/system-stored-procedures/sp-syscollector-disable-collector-transact-sql) to disable the data collector.</span></span>  
  
```sql  
USE msdb;  
GO  
EXEC dbo.sp_syscollector_disable_collector;  
```  
  
## <a name="see-also"></a><span data-ttu-id="b191d-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b191d-132">See Also</span></span>  
 <span data-ttu-id="b191d-133">[Datensammlung](data-collection.md) </span><span class="sxs-lookup"><span data-stu-id="b191d-133">[Data Collection](data-collection.md) </span></span>  
 [<span data-ttu-id="b191d-134">Gespeicherte Systemprozeduren &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b191d-134">System Stored Procedures &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/system-stored-procedures-transact-sql)  
  
  
