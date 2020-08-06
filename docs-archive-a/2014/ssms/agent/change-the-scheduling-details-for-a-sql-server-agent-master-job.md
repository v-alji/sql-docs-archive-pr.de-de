---
title: Ändern der Zeitplandetails für einen Rasterauftrag für den SQL Server-Agent | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: f5414451-4d8e-464b-bd9e-f2b70c6899b3
author: stevestein
ms.author: sstein
ms.openlocfilehash: 85546bc93e6626bfcc85a28f06a4c2fe24fe9fd1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622383"
---
# <a name="change-the-scheduling-details-for-a-sql-server-agent-master-job"></a><span data-ttu-id="4684e-102">Change the Scheduling Details for a SQL Server Agent Master Job</span><span class="sxs-lookup"><span data-stu-id="4684e-102">Change the Scheduling Details for a SQL Server Agent Master Job</span></span>
  <span data-ttu-id="4684e-103">In diesem Thema wird beschrieben, wie Sie Zeitplandetails mithilfe von [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] oder [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] in [!INCLUDE[tsql](../../includes/tsql-md.md)]ändern.</span><span class="sxs-lookup"><span data-stu-id="4684e-103">This topic describes how to change the scheduling details for a job definition in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="4684e-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="4684e-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="4684e-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="4684e-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="4684e-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="4684e-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="4684e-107">Security</span><span class="sxs-lookup"><span data-stu-id="4684e-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="4684e-108">**Ändern der Zeitplandetails für eine Auftragsdefinition mit:**</span><span class="sxs-lookup"><span data-stu-id="4684e-108">**To change the scheduling details for a job definition, using:**</span></span>  
  
     [<span data-ttu-id="4684e-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4684e-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="4684e-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4684e-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4684e-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="4684e-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="4684e-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="4684e-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="4684e-113">Ein Masterauftrag für den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent kann nicht gleichzeitig lokale Server und Remoteserver als Ziel haben.</span><span class="sxs-lookup"><span data-stu-id="4684e-113">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent master job cannot be targeted at both local and remote servers.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4684e-114">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="4684e-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4684e-115">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="4684e-115">Permissions</span></span>  
 <span data-ttu-id="4684e-116">Sie können nur Aufträge ändern, die in Ihrem Besitz sind, es sei denn, Sie sind ein Mitglied der festen Serverrolle **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="4684e-116">Unless you are a member of the **sysadmin** fixed server role, you can only modify jobs that you own.</span></span> <span data-ttu-id="4684e-117">Ausführliche Informationen finden Sie unter [Implementieren der SQL Server-Agent-Sicherheit](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="4684e-117">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4684e-118">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4684e-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-change-the-scheduling-details-for-a-job-definition"></a><span data-ttu-id="4684e-119">So ändern Sie die Zeitplandetails für eine Auftragsdefinition</span><span class="sxs-lookup"><span data-stu-id="4684e-119">To change the scheduling details for a job definition</span></span>  
  
1.  <span data-ttu-id="4684e-120">Klicken Sie im **Objekt-Explorer** auf das Pluszeichen, um den Server zu erweitern, in dem der Auftrag mit dem zu bearbeitenden Zeitplan enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="4684e-120">In **Object Explorer,** click the plus sign to expand the server that contains the job whose schedule you want to edit.</span></span>  
  
2.  <span data-ttu-id="4684e-121">Klicken Sie auf das Pluszeichen, um **SQL Server-Agent**zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="4684e-121">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="4684e-122">Klicken Sie auf das Pluszeichen, um den Ordner **Aufträge** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="4684e-122">Click the plus sign to expand the **Jobs** folder.</span></span>  
  
4.  <span data-ttu-id="4684e-123">Klicken Sie mit der rechten Maustaste auf den Auftrag, dessen Zeitplan Sie bearbeiten möchten, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="4684e-123">Right-click the job whose schedule you want to edit and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="4684e-124">Wählen Sie im Dialogfeld **Auftrags Eigenschaften-**_job_name_ unter **Seite auswählen**die Option **Zeitpläne**aus.</span><span class="sxs-lookup"><span data-stu-id="4684e-124">In the **Job Properties -**_job_name_ dialog box, under **Select a page**, select **Schedules**.</span></span> <span data-ttu-id="4684e-125">Weitere Informationen zu den verfügbaren Optionen auf dieser Seite finden Sie unter [Auftrags Eigenschaften: Seite "neue Aufträge &#40;Zeitpläne"&#41;](job-properties-new-job-schedules-page.md).</span><span class="sxs-lookup"><span data-stu-id="4684e-125">For more information on the available options on this page, see [Job Properties: New Job &#40;Schedules Page&#41;](job-properties-new-job-schedules-page.md).</span></span>  
  
6.  <span data-ttu-id="4684e-126">Wenn Sie fertig sind, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="4684e-126">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4684e-127">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4684e-127">Using Transact-SQL</span></span>  
  
#### <a name="to-change-the-scheduling-details-for-a-job-definition"></a><span data-ttu-id="4684e-128">So ändern Sie die Zeitplandetails für eine Auftragsdefinition</span><span class="sxs-lookup"><span data-stu-id="4684e-128">To change the scheduling details for a job definition</span></span>  
  
1.  <span data-ttu-id="4684e-129">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="4684e-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4684e-130">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="4684e-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4684e-131">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="4684e-131">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- changes the enabled status of the NightlyJobs schedule to 0   
    -- and sets the owner to terrid.   
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_update_schedule  
        @name = 'NightlyJobs',  
        @enabled = 0,  
        @owner_login_name = 'terrid' ;  
    GO  
    ```  
  
 <span data-ttu-id="4684e-132">Weitere Informationen finden Sie unter [sp_update_schedule &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-update-schedule-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4684e-132">For more information, see [sp_update_schedule &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-schedule-transact-sql).</span></span>  
  
  
