---
title: Löschen eines Operators | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, operators
- canceling operators
- removing operators
- deleting operators
- dropping operators
- jobs [SQL Server Agent], operators
- operators (users) [Database Engine], deleting with Management Studio
ms.assetid: 2b7b8627-082d-4189-8584-abd3a9b604cf
author: stevestein
ms.author: sstein
ms.openlocfilehash: 75bea1c5c5fabff7ce55fe07a5181baa8f99e0fe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609015"
---
# <a name="delete-an-operator"></a><span data-ttu-id="bd0df-102">Delete an Operator</span><span class="sxs-lookup"><span data-stu-id="bd0df-102">Delete an Operator</span></span>
  <span data-ttu-id="bd0df-103">In diesem Thema wird beschrieben, wie Sie einen Operator entfernen, damit er keine [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent-Warn Benachrichtigungen mehr in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder empfängt [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bd0df-103">This topic describes how to remove an operator so they no longer receive [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alert notifications in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="bd0df-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="bd0df-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="bd0df-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="bd0df-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="bd0df-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="bd0df-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="bd0df-107">Security</span><span class="sxs-lookup"><span data-stu-id="bd0df-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="bd0df-108">**So löschen Sie einen Operator mit**</span><span class="sxs-lookup"><span data-stu-id="bd0df-108">**To delete an operator, using:**</span></span>  
  
     [<span data-ttu-id="bd0df-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="bd0df-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="bd0df-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="bd0df-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="bd0df-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="bd0df-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="bd0df-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="bd0df-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="bd0df-113">Beim Entfernen eines Operators werden alle dem Operator zugeordneten Benachrichtigungen ebenfalls entfernt.</span><span class="sxs-lookup"><span data-stu-id="bd0df-113">When an operator is removed, all the notifications associated with the operator are also removed.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="bd0df-114">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="bd0df-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="bd0df-115">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="bd0df-115">Permissions</span></span>  
 <span data-ttu-id="bd0df-116">Mitglieder der festen Serverrolle **sysadmin** können Operatoren löschen.</span><span class="sxs-lookup"><span data-stu-id="bd0df-116">Members of the **sysadmin** fixed server role can delete operators.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="bd0df-117">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="bd0df-117">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-an-operator"></a><span data-ttu-id="bd0df-118">So löschen Sie einen Operator</span><span class="sxs-lookup"><span data-stu-id="bd0df-118">To delete an operator</span></span>  
  
1.  <span data-ttu-id="bd0df-119">Klicken Sie im **Objekt-Explorer** auf das Pluszeichen, um den Server zu erweitern, der den Operator enthält, den Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="bd0df-119">In **Object Explorer**, click the plus sign to expand the server that contains the operator you want to delete.</span></span>  
  
2.  <span data-ttu-id="bd0df-120">Klicken Sie auf das Pluszeichen, um **SQL Server-Agent**zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="bd0df-120">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="bd0df-121">Klicken Sie auf das Pluszeichen, um den Ordner **Operatoren** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="bd0df-121">Click the plus sign to expand the **Operators** folder.</span></span>  
  
4.  <span data-ttu-id="bd0df-122">Klicken Sie mit der rechten Maustaste auf den Operator, den Sie löschen möchten, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="bd0df-122">Right-click the operator that you want to delete and select **Delete**.</span></span>  
  
5.  <span data-ttu-id="bd0df-123">Stellen Sie sicher, dass im Dialogfeld **Objekt löschen** der richtige Operator ausgewählt ist, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="bd0df-123">In the **Delete Object** dialog box, make sure that the correct operator is selected, and then click **OK**.</span></span> <span data-ttu-id="bd0df-124">Wenn ein anderer Operator die an den gelöschten Operator gesendeten Warnungen und Aufträge empfangen soll, aktivieren Sie **Neu zuweisen an** , und wählen Sie in der Liste den gewünschten Operator aus.</span><span class="sxs-lookup"><span data-stu-id="bd0df-124">If you want another operator to receive the alerts and jobs sent to the deleted operator, check **Reassign to** and select an operator in the list.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="bd0df-125">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="bd0df-125">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-an-operator"></a><span data-ttu-id="bd0df-126">So löschen Sie einen Operator</span><span class="sxs-lookup"><span data-stu-id="bd0df-126">To delete an operator</span></span>  
  
1.  <span data-ttu-id="bd0df-127">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="bd0df-127">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="bd0df-128">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="bd0df-128">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="bd0df-129">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="bd0df-129">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- deletes operator 'Test Operator' and reassigns all alerts and jobs sent to that operator to 'Fran??ois Ajenstat'  
    USE msdb ;  
    GO  
  
    EXEC sp_delete_operator @name = 'Test Operator',  
        @reassign_to_operator = 'Fran??ois Ajenstat';  
    GO  
    ```  
  
 <span data-ttu-id="bd0df-130">Weitere Informationen finden Sie unter [sp_delete_operator &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-operator-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="bd0df-130">For more information, see [sp_delete_operator &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-operator-transact-sql).</span></span>  
  
  
