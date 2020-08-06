---
title: Synchronisieren von Zielserveruhren (SQL Server Management Studio) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, target servers
- clocks [SQL Server]
- master servers [SQL Server], clock synchronization
- synchronization [SQL Server], target server clocks
- target servers [SQL Server], clock synchronization
ms.assetid: 4fb80502-d271-4d06-bcbc-bfbbceb5f2a2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8e7150cd42699503ab22cdd89fb6206194bd64e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695245"
---
# <a name="synchronize-target-server-clocks-sql-server-management-studio"></a><span data-ttu-id="e3ef9-102">Synchronize Target Server Clocks (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="e3ef9-102">Synchronize Target Server Clocks (SQL Server Management Studio)</span></span>
  <span data-ttu-id="e3ef9-103">In diesem Thema wird beschrieben, wie Sie Zielserveruhren in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mit der Masterserveruhr mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]synchronisieren können.</span><span class="sxs-lookup"><span data-stu-id="e3ef9-103">This topic describes how to synchronize target server clocks in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] with the master server clock by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="e3ef9-104">Das Synchronisieren dieser Systemuhren unterstützt Auftragszeitpläne.</span><span class="sxs-lookup"><span data-stu-id="e3ef9-104">Synchronizing these system clocks supports your job schedules.</span></span>  
  
 <span data-ttu-id="e3ef9-105">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="e3ef9-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="e3ef9-106">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="e3ef9-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e3ef9-107">Security</span><span class="sxs-lookup"><span data-stu-id="e3ef9-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e3ef9-108">**So synchronisieren Sie die Uhren der Zielserver mit**</span><span class="sxs-lookup"><span data-stu-id="e3ef9-108">**To synchronize target server clocks, using:**</span></span>  
  
     [<span data-ttu-id="e3ef9-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e3ef9-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="e3ef9-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e3ef9-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e3ef9-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="e3ef9-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e3ef9-112">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="e3ef9-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e3ef9-113">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="e3ef9-113">Permissions</span></span>  
 <span data-ttu-id="e3ef9-114">Erfordert die Mitgliedschaft in der festen Serverrolle **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="e3ef9-114">Requires membership in the **sysadmin** fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="e3ef9-115">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e3ef9-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-synchronize-target-server-clocks"></a><span data-ttu-id="e3ef9-116">So synchronisieren Sie die Uhren der Zielserver</span><span class="sxs-lookup"><span data-stu-id="e3ef9-116">To synchronize target server clocks</span></span>  
  
1.  <span data-ttu-id="e3ef9-117">Klicken Sie im **Objekt-Explorer** auf das Pluszeichen, um den Server zu erweitern, auf dem Sie die Zielserveruhren mit der Masterserveruhr synchronisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="e3ef9-117">In **Object Explorer,** click the plus sign to expand the server where you want to synchronize the target server clocks with the master server clock.</span></span>  
  
2.  <span data-ttu-id="e3ef9-118">Klicken Sie mit der rechten Maustaste auf **SQL Server-Agent**, zeigen Sie auf **Multiserververwaltung**, und klicken Sie auf **Zielserver verwalten**.</span><span class="sxs-lookup"><span data-stu-id="e3ef9-118">Right-click **SQL Server Agent**, point to **Multi Server Administration**, and select **Manage Target Servers**.</span></span>  
  
3.  <span data-ttu-id="e3ef9-119">Klicken Sie im Dialogfeld **Zielserver verwalten** auf **Anweisungen bereitstellen**.</span><span class="sxs-lookup"><span data-stu-id="e3ef9-119">In the **Manage Target Servers** dialog box, click **Post Instructions**.</span></span>  
  
4.  <span data-ttu-id="e3ef9-120">Wählen Sie in der Liste **Anweisungstyp** die Option **Uhren synchronisieren**aus.</span><span class="sxs-lookup"><span data-stu-id="e3ef9-120">In the **Instruction type** list, select **Synchronize clocks**.</span></span>  
  
5.  <span data-ttu-id="e3ef9-121">Führen Sie unter **Empfänger**eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="e3ef9-121">Under **Recipients**, do one of the following:</span></span>  
  
    -   <span data-ttu-id="e3ef9-122">Klicken Sie auf **Alle Zielserver** , um die Uhren aller Zielserver mit der Uhr des Masterservers zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="e3ef9-122">Click **All target servers** to synchronize all target server clocks with the master server clock.</span></span>  
  
    -   <span data-ttu-id="e3ef9-123">Klicken Sie auf **Diese Zielserver** , um bestimmte Serveruhren zu synchronisieren, und wählen Sie dann alle Zielserver aus, deren Uhren mit der Uhr des Masterservers synchronisiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e3ef9-123">Click **These target servers** to synchronize certain server clocks, and then select each target server whose clock you want to synchronize with the master server clock.</span></span>  
  
6.  <span data-ttu-id="e3ef9-124">Wenn Sie fertig sind, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e3ef9-124">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="e3ef9-125">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e3ef9-125">Using Transact-SQL</span></span>  
  
#### <a name="to-synchronize-target-server-clocks"></a><span data-ttu-id="e3ef9-126">So synchronisieren Sie die Uhren der Zielserver</span><span class="sxs-lookup"><span data-stu-id="e3ef9-126">To synchronize target server clocks</span></span>  
  
1.  <span data-ttu-id="e3ef9-127">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="e3ef9-127">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e3ef9-128">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="e3ef9-128">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e3ef9-129">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="e3ef9-129">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE msdb ;  
    GO  
    -- resynchronizes the SEATTLE1 target server  
    EXEC dbo.sp_resync_targetserver  
        N'SEATTLE1' ;  
    GO  
    ```  
  
 <span data-ttu-id="e3ef9-130">Weitere Informationen finden Sie unter [sp_resync_targetserver &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-resync-targetserver-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e3ef9-130">For more information, see [sp_resync_targetserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-resync-targetserver-transact-sql).</span></span>  
  
  
