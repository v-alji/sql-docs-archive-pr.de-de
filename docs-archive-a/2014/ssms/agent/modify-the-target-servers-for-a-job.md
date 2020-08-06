---
title: Ändern der Zielserver für einen Auftrag | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- modifying target servers
- SQL Server Agent jobs, target servers
- target servers [SQL Server], modifying
ms.assetid: 9dbe24f2-acec-4aa2-920c-e8e96efa18e4
author: stevestein
ms.author: sstein
ms.openlocfilehash: 246a5bb59a681a70734cc8cabef4f724cda1b52e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616336"
---
# <a name="modify-the-target-servers-for-a-job"></a><span data-ttu-id="3aa62-102">Modify the Target Servers for a Job</span><span class="sxs-lookup"><span data-stu-id="3aa62-102">Modify the Target Servers for a Job</span></span>
  <span data-ttu-id="3aa62-103">In diesem Thema wird beschrieben, wie Sie die Zielserver für- [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent-Aufträge in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von oder ändern können [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3aa62-103">This topic describes how to change the target servers for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="3aa62-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="3aa62-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="3aa62-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="3aa62-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="3aa62-106">Security</span><span class="sxs-lookup"><span data-stu-id="3aa62-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="3aa62-107">**Ändern der Zielserver für einen Auftrag mit:**</span><span class="sxs-lookup"><span data-stu-id="3aa62-107">**To modify the target servers for a job, using:**</span></span>  
  
     [<span data-ttu-id="3aa62-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3aa62-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="3aa62-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3aa62-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3aa62-110">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="3aa62-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3aa62-111">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="3aa62-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="3aa62-112">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="3aa62-112">Permissions</span></span>  
 <span data-ttu-id="3aa62-113">Standardmäßig können Mitglieder der festen Serverrolle „sysadmin“ diese gespeicherte Prozedur ausführen.</span><span class="sxs-lookup"><span data-stu-id="3aa62-113">By default, members of the sysadmin fixed server role can execute this stored procedure.</span></span> <span data-ttu-id="3aa62-114">Andere Benutzer müssen Mitglieder einer der folgenden festen SQL Server-Agent-Datenbankrollen in der msdb-Datenbank sein:</span><span class="sxs-lookup"><span data-stu-id="3aa62-114">Other users must be granted one of the following SQL Server Agent fixed database roles in the msdb database:</span></span>  
  
1.  `SQLAgentUserRole`  
  
2.  `SQLAgentReaderRole`  
  
3.  <span data-ttu-id="3aa62-115">SQLAgentOperatorRole</span><span class="sxs-lookup"><span data-stu-id="3aa62-115">SQLAgentOperatorRole</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="3aa62-116">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3aa62-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-the-target-servers-for-a-job"></a><span data-ttu-id="3aa62-117">So ändern Sie die Zielserver für einen Auftrag</span><span class="sxs-lookup"><span data-stu-id="3aa62-117">To modify the target servers for a job</span></span>  
  
1.  <span data-ttu-id="3aa62-118">Stellen Sie in **Objekt-Explorer** eine Verbindung mit einer Instanz von her [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="3aa62-118">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="3aa62-119">Erweitern Sie **SQL Server-Agent**, erweitern Sie **Aufträge**, klicken Sie mit der rechten Maustaste auf einen Auftrag, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="3aa62-119">Expand **SQL Server Agent**, expand **Jobs**, right-click a job, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="3aa62-120">Wählen Sie im Dialogfeld **Auftragseigenschaften** die Seite **Ziele**aus, und klicken Sie auf **Ziel: Lokaler Server**oder auf **Ziel: Mehrere Server**.</span><span class="sxs-lookup"><span data-stu-id="3aa62-120">In the **Job Properties** dialog, select the **Targets**page, and click **Target local server**, or **Target multiple servers**.</span></span>  
  
     <span data-ttu-id="3aa62-121">Wenn Sie **Ziel: Mehrere Server**auswählen, geben Sie Server an, die Ziele für den Auftrag sind, indem Sie das Kästchen links neben dem Servernamen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="3aa62-121">If you choose **Target multiple servers**, designate the servers that will be targets for the job by checking the box to the left of the server name.</span></span> <span data-ttu-id="3aa62-122">Stellen Sie sicher, dass die Kästchen für die Server, die nicht Ziel für den Auftrag sind, deaktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="3aa62-122">Verify that the check boxes for servers that will not be targets of the job are unchecked.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="3aa62-123">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3aa62-123">Using Transact-SQL</span></span>  
  
#### <a name="to-modify-the-target-servers-for-a-job"></a><span data-ttu-id="3aa62-124">So ändern Sie die Zielserver für einen Auftrag</span><span class="sxs-lookup"><span data-stu-id="3aa62-124">To modify the target servers for a job</span></span>  
  
1.  <span data-ttu-id="3aa62-125">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="3aa62-125">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="3aa62-126">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="3aa62-126">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="3aa62-127">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="3aa62-127">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="3aa62-128">In diesem Beispiel wird der Multiserverauftrag „Weekly Sales Backups“ dem Server SEATTLE2 zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="3aa62-128">This example assigns the multiserver job Weekly Sales Backups to the server SEATTLE2.</span></span>  
  
```  
USE msdb ;  
GO  
  
EXEC dbo.sp_add_jobserver  
    @job_name = N'Weekly Sales Backups',   
    @server_name = N'SEATTLE2' ;   
GO  
  
```  
  
 <span data-ttu-id="3aa62-129">Weitere Informationen finden Sie unter [sp_add_jobserver &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobserver-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3aa62-129">For more information, see [sp_add_jobserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobserver-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3aa62-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3aa62-130">See Also</span></span>  
 [<span data-ttu-id="3aa62-131">Automatisierte Verwaltung in einem Unternehmen</span><span class="sxs-lookup"><span data-stu-id="3aa62-131">Automated Administration Across an Enterprise</span></span>](automated-administration-across-an-enterprise.md)  
  
  
