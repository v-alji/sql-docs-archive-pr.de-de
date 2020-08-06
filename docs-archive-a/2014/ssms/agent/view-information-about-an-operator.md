---
title: Anzeigen von Informationen zu einem Operator | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, operators
- viewing operators
- operators (users) [Database Engine], viewing with Management Studio
- jobs [SQL Server Agent], operators
- notifications [SQL Server], job status
- displaying operators
ms.assetid: 92c82cdf-f704-444e-9539-82aea7fe6fb7
author: stevestein
ms.author: sstein
ms.openlocfilehash: 680b90401f800a9c435bdae33b8e55385541cc4c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616317"
---
# <a name="view-information-about-an-operator"></a><span data-ttu-id="34b4a-102">View Information About an Operator</span><span class="sxs-lookup"><span data-stu-id="34b4a-102">View Information About an Operator</span></span>
  <span data-ttu-id="34b4a-103">In diesem Thema wird beschrieben, wie Sie Informationen zu einem- [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent-Operator in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von oder anzeigen können [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="34b4a-103">This topic describes how to view information about a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent operator in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="34b4a-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="34b4a-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="34b4a-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="34b4a-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="34b4a-106">Security</span><span class="sxs-lookup"><span data-stu-id="34b4a-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="34b4a-107">**So zeigen Sie Informationen zu einem Operator an mit**</span><span class="sxs-lookup"><span data-stu-id="34b4a-107">**To view information about an operator, using:**</span></span>  
  
     [<span data-ttu-id="34b4a-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="34b4a-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="34b4a-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="34b4a-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="34b4a-110">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="34b4a-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="34b4a-111">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="34b4a-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="34b4a-112">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="34b4a-112">Permissions</span></span>  
 <span data-ttu-id="34b4a-113">Standardmäßig können Mitglieder der festen Server Rolle **sysadmin** diese gespeicherte Prozedur ausführen.</span><span class="sxs-lookup"><span data-stu-id="34b4a-113">By default, members of the **sysadmin** fixed server role can execute this stored procedure.</span></span> <span data-ttu-id="34b4a-114">Andere Benutzer müssen Mitglieder der festen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Datenbankrollen in der **msdb** -Datenbank sein:</span><span class="sxs-lookup"><span data-stu-id="34b4a-114">Other users must be granted one of the following [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles in the **msdb** database:</span></span>  
  
-   <span data-ttu-id="34b4a-115">**SQLAgentUserRole**</span><span class="sxs-lookup"><span data-stu-id="34b4a-115">**SQLAgentUserRole**</span></span>  
  
-   <span data-ttu-id="34b4a-116">**SQLAgentReaderRole**</span><span class="sxs-lookup"><span data-stu-id="34b4a-116">**SQLAgentReaderRole**</span></span>  
  
-   <span data-ttu-id="34b4a-117">**SQLAgentOperatorRole**</span><span class="sxs-lookup"><span data-stu-id="34b4a-117">**SQLAgentOperatorRole**</span></span>  
  
 <span data-ttu-id="34b4a-118">Weitere Informationen zu den Berechtigungen dieser Rollen finden Sie unter [Feste Datenbankrollen des SQL Server-Agents](sql-server-agent-fixed-database-roles.md).</span><span class="sxs-lookup"><span data-stu-id="34b4a-118">For details about the permissions of these roles, see [SQL Server Agent Fixed Database Roles](sql-server-agent-fixed-database-roles.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="34b4a-119">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="34b4a-119">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-information-about-an-operator"></a><span data-ttu-id="34b4a-120">So zeigen Sie Informationen zu einem Operator an</span><span class="sxs-lookup"><span data-stu-id="34b4a-120">To view information about an operator</span></span>  
  
1.  <span data-ttu-id="34b4a-121">Klicken Sie im **Objekt-Explorer** auf das Pluszeichen, um den Server zu erweitern, der den Operator enthält, den Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="34b4a-121">In **Object Explorer**, click the plus sign to expand the server that contains the operator you want to view.</span></span>  
  
2.  <span data-ttu-id="34b4a-122">Klicken Sie auf das Pluszeichen, um **SQL Server-Agent**zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="34b4a-122">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="34b4a-123">Klicken Sie auf das Pluszeichen, um den Ordner **Operatoren** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="34b4a-123">Click the plus sign to expand the **Operators** folder.</span></span>  
  
4.  <span data-ttu-id="34b4a-124">Klicken Sie mit der rechten Maustaste auf den Operator, den Sie anzeigen möchten, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="34b4a-124">Right-click the operator that you want to view and select **Properties**.</span></span>  
  
     <span data-ttu-id="34b4a-125">Weitere Informationen zu den verfügbaren Optionen im Dialogfeld _Operatorname_**Eigenschaften** finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="34b4a-125">For more information on the available options contained in the _operator_name_**Properties** dialog box, see:</span></span>  
  
    -   [<span data-ttu-id="34b4a-126">Operator Eigenschaften und neuer Operator &#40;Seite "Allgemein"&#41;</span><span class="sxs-lookup"><span data-stu-id="34b4a-126">Operator Properties and New Operator &#40;General Page&#41;</span></span>](../../integration-services/general-page-of-integration-services-designers-options.md)  
  
    -   [<span data-ttu-id="34b4a-127">Operator Eigenschaften: Neuer Operator &#40;Seite "Benachrichtigungen"&#41;</span><span class="sxs-lookup"><span data-stu-id="34b4a-127">Operator Properties: New Operator &#40;Notifications Page&#41;</span></span>](operator-properties-new-operator-notifications-page.md)  
  
    -   [<span data-ttu-id="34b4a-128">Operatoreigenschaften &#40;Seite „Verlauf“&#41;</span><span class="sxs-lookup"><span data-stu-id="34b4a-128">Operator Properties &#40;History Page&#41;</span></span>](operator-properties-history-page.md)  
  
5.  <span data-ttu-id="34b4a-129">Wenn Sie fertig sind, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="34b4a-129">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="34b4a-130">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="34b4a-130">Using Transact-SQL</span></span>  
  
#### <a name="to-view-information-about-an-operator"></a><span data-ttu-id="34b4a-131">So zeigen Sie Informationen zu einem Operator an</span><span class="sxs-lookup"><span data-stu-id="34b4a-131">To view information about an operator</span></span>  
  
1.  <span data-ttu-id="34b4a-132">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="34b4a-132">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="34b4a-133">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="34b4a-133">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="34b4a-134">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="34b4a-134">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- reports information about operator Fran??ois Ajenstat   
    -- This example assumes that the operator exists.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_help_operator  
        @operator_name = N'Fran??ois Ajenstat' ;  
    GO  
    ```  
  
 <span data-ttu-id="34b4a-135">Weitere Informationen finden Sie unter [sp_help_operator &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-help-operator-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="34b4a-135">For more information, see [sp_help_operator &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-operator-transact-sql).</span></span>  
  
  
