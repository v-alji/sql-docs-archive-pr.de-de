---
title: Löschen einer Warnung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, alerts
- alerts [SQL Server], deleting
- deleting alerts
- canceling alerts
- dropping alerts
- disabling alerts
- removing alerts
ms.assetid: c982b208-e2d1-4d34-8cee-940b9baf6586
author: stevestein
ms.author: sstein
ms.openlocfilehash: 15fdae19b150a5a06a32e91ec1947a0acfa5f900
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620108"
---
# <a name="delete-an-alert"></a><span data-ttu-id="57f36-102">Delete an Alert</span><span class="sxs-lookup"><span data-stu-id="57f36-102">Delete an Alert</span></span>
  <span data-ttu-id="57f36-103">In diesem Thema wird beschrieben, wie [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Sie-Agent-Warnungen in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von oder löschen können [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="57f36-103">This topic describes how to delete [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="57f36-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="57f36-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="57f36-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="57f36-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="57f36-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="57f36-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="57f36-107">Security</span><span class="sxs-lookup"><span data-stu-id="57f36-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="57f36-108">**So löschen Sie eine Warnung mit**</span><span class="sxs-lookup"><span data-stu-id="57f36-108">**To delete an alert, using:**</span></span>  
  
     [<span data-ttu-id="57f36-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="57f36-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="57f36-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="57f36-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="57f36-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="57f36-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="57f36-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="57f36-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="57f36-113">Durch das Entfernen einer Warnung werden auch die zugeordneten Benachrichtigungen entfernt.</span><span class="sxs-lookup"><span data-stu-id="57f36-113">Removing an alert also removes any notifications associated with the alert.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="57f36-114">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="57f36-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="57f36-115">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="57f36-115">Permissions</span></span>  
 <span data-ttu-id="57f36-116">Standardmäßig können nur Mitglieder der festen Serverrolle **sysadmin** Warnungen löschen.</span><span class="sxs-lookup"><span data-stu-id="57f36-116">By default, only members of the **sysadmin** fixed server role can delete alerts.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="57f36-117">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="57f36-117">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-an-alert"></a><span data-ttu-id="57f36-118">So löschen Sie eine Warnung</span><span class="sxs-lookup"><span data-stu-id="57f36-118">To delete an alert</span></span>  
  
1.  <span data-ttu-id="57f36-119">Klicken Sie im **Objekt-Explorer** auf das Pluszeichen, um den Server zu erweitern, der die SQL Server-Agent-Warnung enthält, die Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="57f36-119">In **Object Explorer,** click the plus sign to expand the server that contains the SQL Server Agent alert that you want to delete.</span></span>  
  
2.  <span data-ttu-id="57f36-120">Klicken Sie auf das Pluszeichen, um **SQL Server-Agent**zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="57f36-120">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="57f36-121">Klicken Sie auf das Pluszeichen, um den Ordner **Warnungen** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="57f36-121">Click the plus sign to expand the **Alerts** folder.</span></span>  
  
4.  <span data-ttu-id="57f36-122">Klicken Sie mit der rechten Maustaste auf die Warnung, die Sie löschen möchten, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="57f36-122">Right-click the alert you want to delete and select **Delete**.</span></span>  
  
5.  <span data-ttu-id="57f36-123">Stellen Sie im Dialogfeld **Objekt löschen** sicher, dass die richtige Warnung ausgewählt ist, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="57f36-123">In the **Delete Object** dialog box, confirm that the correct alert is selected and click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="57f36-124">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="57f36-124">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-an-alert"></a><span data-ttu-id="57f36-125">So löschen Sie eine Warnung</span><span class="sxs-lookup"><span data-stu-id="57f36-125">To delete an alert</span></span>  
  
1.  <span data-ttu-id="57f36-126">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="57f36-126">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="57f36-127">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="57f36-127">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="57f36-128">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="57f36-128">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- deletes the SQL Server Agent alert called 'Test Alert.'  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_delete_alert  
       @name = N'Test Alert' ;  
    GO  
    ```  
  
 <span data-ttu-id="57f36-129">Weitere Informationen finden Sie unter s[sp_delete_alert &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-alert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="57f36-129">For more information, see s[sp_delete_alert &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-alert-transact-sql).</span></span>  
  
  
