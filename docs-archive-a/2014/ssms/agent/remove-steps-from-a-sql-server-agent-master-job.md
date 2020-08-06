---
title: Entfernen von Schritten aus einem Masterauftrag für den SQL Server-Agent |Microsoft-Dokumente
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: 871e6162-1221-464d-8f7f-7e454dcd9edb
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5996971225ee0b300b307c5af24dec464dbfd43c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622353"
---
# <a name="remove-steps-from-a-sql-server-agent-master-job"></a><span data-ttu-id="60740-102">Remove Steps from a SQL Server Agent Master Job</span><span class="sxs-lookup"><span data-stu-id="60740-102">Remove Steps from a SQL Server Agent Master Job</span></span>
  <span data-ttu-id="60740-103">In diesem Thema wird beschrieben, wie Sie Schritte aus einem Masterauftrag für den SQL Server-Agent in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]entfernen.</span><span class="sxs-lookup"><span data-stu-id="60740-103">This topic describes how to remove steps from a SQL Server Agent master job in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="60740-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="60740-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="60740-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="60740-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="60740-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="60740-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="60740-107">Security</span><span class="sxs-lookup"><span data-stu-id="60740-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="60740-108">**Entfernen von Schritten aus einem Masterauftrag für den SQL Server-Agent mit:**</span><span class="sxs-lookup"><span data-stu-id="60740-108">**To remove steps from a SQL Server Agent master job, using:**</span></span>  
  
     [<span data-ttu-id="60740-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="60740-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="60740-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="60740-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="60740-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="60740-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="60740-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="60740-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="60740-113">Ein Masterauftrag für den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent kann nicht gleichzeitig lokale Server und Remoteserver als Ziel haben.</span><span class="sxs-lookup"><span data-stu-id="60740-113">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent master job cannot be targeted at both local and remote servers.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="60740-114">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="60740-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="60740-115">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="60740-115">Permissions</span></span>  
 <span data-ttu-id="60740-116">Sie können nur Aufträge ändern, die in Ihrem Besitz sind, es sei denn, Sie sind ein Mitglied der festen Serverrolle **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="60740-116">Unless you are a member of the **sysadmin** fixed server role, you can only modify jobs that you own.</span></span> <span data-ttu-id="60740-117">Ausführliche Informationen finden Sie unter [Implementieren der SQL Server-Agent-Sicherheit](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="60740-117">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="60740-118">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="60740-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-remove-steps-from-a-sql-server-agent-master-job"></a><span data-ttu-id="60740-119">So entfernen Sie Schritte aus einem Masterauftrag für den SQL Server-Agent</span><span class="sxs-lookup"><span data-stu-id="60740-119">To remove steps from a SQL Server Agent master job</span></span>  
  
1.  <span data-ttu-id="60740-120">Klicken Sie im **Objekt-Explorer** auf das Pluszeichen, um den Server zu erweitern, der den Auftrag mit den zu löschenden Schritten enthält.</span><span class="sxs-lookup"><span data-stu-id="60740-120">In **Object Explorer,** click the plus sign to expand the server that contains the job where you want to delete steps.</span></span>  
  
2.  <span data-ttu-id="60740-121">Klicken Sie auf das Pluszeichen, um **SQL Server-Agent**zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="60740-121">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="60740-122">Klicken Sie auf das Pluszeichen, um den Ordner **Aufträge** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="60740-122">Click the plus sign to expand the **Jobs** folder.</span></span>  
  
4.  <span data-ttu-id="60740-123">Klicken Sie mit der rechten Maustaste auf den Auftrag, dessen Schritte Sie löschen möchten, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="60740-123">Right-click the job where you want to delete steps and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="60740-124">Wählen Sie im Dialogfeld **Auftrags Eigenschaften-**_job_name_ unter **Seite auswählen**die Option **Schritte**aus.</span><span class="sxs-lookup"><span data-stu-id="60740-124">In the **Job Properties -**_job_name_ dialog box, under **Select a page**, select **Steps**.</span></span>  
  
6.  <span data-ttu-id="60740-125">Wählen Sie unter **Auftragsschrittliste**den zu löschenden Auftragsschritt aus, und klicken Sie auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="60740-125">Under **Job step list**, select the job step you want to delete and click **Delete**.</span></span>  
  
7.  <span data-ttu-id="60740-126">Wenn Sie fertig sind, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="60740-126">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="60740-127">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="60740-127">Using Transact-SQL</span></span>  
  
#### <a name="to-remove-steps-from-a-sql-server-agent-master-job"></a><span data-ttu-id="60740-128">So entfernen Sie Schritte aus einem Masterauftrag für den SQL Server-Agent</span><span class="sxs-lookup"><span data-stu-id="60740-128">To remove steps from a SQL Server Agent master job</span></span>  
  
1.  <span data-ttu-id="60740-129">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="60740-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="60740-130">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="60740-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="60740-131">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="60740-131">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- removes job step 1 from the job Weekly Sales Data Backup   
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_delete_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_id = 1 ;  
    GO  
    ```  
  
 <span data-ttu-id="60740-132">Weitere Informationen finden Sie unter [sp_delete_jobstep &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-jobstep-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="60740-132">For more information, see [sp_delete_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-jobstep-transact-sql).</span></span>  
  
  
