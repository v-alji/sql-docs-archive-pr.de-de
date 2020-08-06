---
title: Bearbeiten eines Operators | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, operators
- modifying operators
- jobs [SQL Server Agent], operators
- operators (users) [Database Engine], modifying with Management Studio
ms.assetid: b2ba2168-ca0b-4b59-9007-4e1e4c30679e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 45ffb520e240dfd97002060370ff6dcf7c60d083
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608221"
---
# <a name="edit-an-operator"></a><span data-ttu-id="d73a2-102">Bearbeiten eines Operators</span><span class="sxs-lookup"><span data-stu-id="d73a2-102">Edit an Operator</span></span>
  <span data-ttu-id="d73a2-103">In diesem Thema wird beschrieben, wie Sie für Operatoren die Möglichkeit zum Empfangen von Benachrichtigungen und deren E-Mail-, Pager- und NET SEND-Adressen in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="d73a2-103">This topic describes how to edit an operators' availability for receiving notifications and their e-mail, pager, and net send addresses in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="d73a2-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="d73a2-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d73a2-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="d73a2-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="d73a2-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="d73a2-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="d73a2-107">Security</span><span class="sxs-lookup"><span data-stu-id="d73a2-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="d73a2-108">**So bearbeiten Sie einen Operator mit**</span><span class="sxs-lookup"><span data-stu-id="d73a2-108">**To edit an operator, using:**</span></span>  
  
     [<span data-ttu-id="d73a2-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d73a2-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="d73a2-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d73a2-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d73a2-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="d73a2-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="d73a2-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="d73a2-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="d73a2-113">Die Pager- und **net send** -Optionen werden in zukünftigen Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nicht mehr im [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d73a2-113">The Pager and **net send** options will be removed from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in a future version of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d73a2-114">Nutzen Sie diese Funktionen bei Neuentwicklungen nicht mehr, und planen Sie die Änderung von Anwendungen, die diese Funktionen zurzeit verwenden.</span><span class="sxs-lookup"><span data-stu-id="d73a2-114">Avoid using these features in new development work, and plan to modify applications that currently use these features.</span></span>  
  
-   <span data-ttu-id="d73a2-115">Beachten Sie, dass E-Mail- und Pagerbenachrichtigungen an Operatoren nur versendet werden können, wenn der SQL Server-Agent für die Verwendung von Datenbank-E-Mail konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="d73a2-115">Note that SQL Server Agent must be configured to use Database Mail to send e-mail and pager notifications to operators.</span></span> <span data-ttu-id="d73a2-116">Weitere Informationen finden Sie unter [Zuweisen von Warnungen zu einem Operator](assign-alerts-to-an-operator.md).</span><span class="sxs-lookup"><span data-stu-id="d73a2-116">For more information, see [Assign Alerts to an Operator](assign-alerts-to-an-operator.md).</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="d73a2-117">können Aufträge problemlos mithilfe einer grafischen Oberfläche verwaltet werden. Dies ist die empfohlene Vorgehensweise für die Erstellung und Verwaltung der Auftragsinfrastruktur.</span><span class="sxs-lookup"><span data-stu-id="d73a2-117">provides an easy, graphical way to manage jobs, and is the recommended way to create and manage the job infrastructure.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d73a2-118">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="d73a2-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d73a2-119">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="d73a2-119">Permissions</span></span>  
 <span data-ttu-id="d73a2-120">Nur Mitglieder der festen Serverrolle **sysadmin** können Operatoren bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="d73a2-120">Only members of the **sysadmin** fixed server role can edit operators.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d73a2-121">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d73a2-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-edit-an-operator"></a><span data-ttu-id="d73a2-122">So bearbeiten Sie einen Operator</span><span class="sxs-lookup"><span data-stu-id="d73a2-122">To edit an operator</span></span>  
  
1.  <span data-ttu-id="d73a2-123">Klicken Sie im **Objekt-Explorer**auf das Pluszeichen, um den Server zu erweitern, der den Operator enthält, den Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="d73a2-123">In **Object Explorer**, click the plus sign to expand the server that contains the operator you want to edit.</span></span>  
  
2.  <span data-ttu-id="d73a2-124">Klicken Sie auf das Pluszeichen, um **SQL Server-Agent**zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="d73a2-124">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="d73a2-125">Klicken Sie auf das Pluszeichen, um den Ordner **Operatoren** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="d73a2-125">Click the plus sign to expand the **Operators** folder.</span></span>  
  
4.  <span data-ttu-id="d73a2-126">Klicken Sie mit der rechten Maustaste auf den Operator, den Sie bearbeiten möchten, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="d73a2-126">Right-click the operator that you want to edit and select **Properties**.</span></span>  
  
     <span data-ttu-id="d73a2-127">Weitere Informationen zu den verfügbaren Optionen im Dialogfeld _Operatorname_**Eigenschaften** finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="d73a2-127">For more information on the available options contained in the _operator_name_**Properties** dialog box, see:</span></span>  
  
    -   [<span data-ttu-id="d73a2-128">Operator Eigenschaften und neuer Operator &#40;Seite "Allgemein"&#41;</span><span class="sxs-lookup"><span data-stu-id="d73a2-128">Operator Properties and New Operator &#40;General Page&#41;</span></span>](../../integration-services/general-page-of-integration-services-designers-options.md)  
  
    -   [<span data-ttu-id="d73a2-129">Operator Eigenschaften: Neuer Operator &#40;Seite "Benachrichtigungen"&#41;</span><span class="sxs-lookup"><span data-stu-id="d73a2-129">Operator Properties: New Operator &#40;Notifications Page&#41;</span></span>](operator-properties-new-operator-notifications-page.md)  
  
    -   [<span data-ttu-id="d73a2-130">Operatoreigenschaften &#40;Seite „Verlauf“&#41;</span><span class="sxs-lookup"><span data-stu-id="d73a2-130">Operator Properties &#40;History Page&#41;</span></span>](operator-properties-history-page.md)  
  
5.  <span data-ttu-id="d73a2-131">Wenn Sie fertig sind, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="d73a2-131">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="d73a2-132">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d73a2-132">Using Transact-SQL</span></span>  
  
#### <a name="to-edit-an-operator"></a><span data-ttu-id="d73a2-133">So bearbeiten Sie einen Operator</span><span class="sxs-lookup"><span data-stu-id="d73a2-133">To edit an operator</span></span>  
  
1.  <span data-ttu-id="d73a2-134">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="d73a2-134">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d73a2-135">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="d73a2-135">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d73a2-136">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="d73a2-136">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- updates the operator status to enabled, and sets the days   
    -- (from Monday through Friday, from 8 A.M. through 5 P.M.) when the operator can be paged.   
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_update_operator   
        @name = N'Fran??ois Ajenstat',  
        @enabled = 1,  
        @email_address = N'fran??oisa',  
        @pager_address = N'5551290AW@pager.Adventure-Works.com',  
        @weekday_pager_start_time = 080000,  
        @weekday_pager_end_time = 170000,  
        @pager_days = 64 ;  
    GO  
    ```  
  
 <span data-ttu-id="d73a2-137">Weitere Informationen finden Sie unter [sp_update_operator &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-update-operator-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d73a2-137">For more information, see [sp_update_operator &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-operator-transact-sql).</span></span>  
  
  
