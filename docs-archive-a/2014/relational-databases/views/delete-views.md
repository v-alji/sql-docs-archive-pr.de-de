---
title: Löschen von Sichten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- dropping views
- deleting views
- views [SQL Server], deleting
- removing views
ms.assetid: 6823c7f8-06ca-4bda-8482-7092f03d52a0
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3e05724f7d6384d0407e915207ad60a1cdfb01b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608467"
---
# <a name="delete-views"></a><span data-ttu-id="f54a7-102">Löschen von Sichten</span><span class="sxs-lookup"><span data-stu-id="f54a7-102">Delete Views</span></span>
  <span data-ttu-id="f54a7-103">Sie können Sichten in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] löschen, indem Sie Folgendes verwenden: [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f54a7-103">You can delete (drop) views in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)]</span></span>  
  

  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f54a7-104">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="f54a7-104">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="f54a7-105">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="f54a7-105">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="f54a7-106">Wenn Sie eine Sicht löschen, werden die Definition der Sicht sowie weitere Informationen zur Sicht aus dem Systemkatalog entfernt.</span><span class="sxs-lookup"><span data-stu-id="f54a7-106">When you drop a view, the definition of the view and other information about the view is deleted from the system catalog.</span></span> <span data-ttu-id="f54a7-107">Alle Berechtigungen für die Sicht werden ebenfalls gelöscht.</span><span class="sxs-lookup"><span data-stu-id="f54a7-107">All permissions for the view are also deleted.</span></span>  
  
-   <span data-ttu-id="f54a7-108">Eine mithilfe von `DROP TABLE` gelöschte Sicht in einer Tabelle muss explizit mit `DROP VIEW`gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="f54a7-108">Any view on a table that is dropped by using `DROP TABLE` must be dropped explicitly by using `DROP VIEW`.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f54a7-109">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="f54a7-109">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f54a7-110">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="f54a7-110">Permissions</span></span>  
 <span data-ttu-id="f54a7-111">Erfordert entweder die ALTER-Berechtigung für SCHEMA oder die CONTROL-Berechtigung für OBJECT.</span><span class="sxs-lookup"><span data-stu-id="f54a7-111">Requires ALTER permission on SCHEMA or CONTROL permission on OBJECT.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f54a7-112">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f54a7-112">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-view-from-a-database"></a><span data-ttu-id="f54a7-113">So löschen Sie eine Sicht aus einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="f54a7-113">To delete a view from a database</span></span>  
  
1.  <span data-ttu-id="f54a7-114">Erweitern Sie im **Objekt-Explorer**die Datenbank mit der Sicht, die Sie löschen möchten, und erweitern Sie dann den Ordner **Sichten** .</span><span class="sxs-lookup"><span data-stu-id="f54a7-114">In **Object Explorer**, expand the database that contains the view you want to delete, and then expand the **Views** folder.</span></span>  
  
2.  <span data-ttu-id="f54a7-115">Klicken Sie mit der rechten Maustaste auf die Sicht, die Sie löschen möchten, und klicken Sie auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="f54a7-115">Right-click the view you want to delete and click **Delete**.</span></span>  
  
3.  <span data-ttu-id="f54a7-116">Klicken Sie im Dialogfeld **Objekt löschen** auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f54a7-116">In the **Delete Object** dialog box, click **OK**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="f54a7-117">Klicken Sie im Dialogfeld **Objekt löschen** auf **Abhängigkeiten anzeigen** , um das Dialogfeld _view_name_**-Abhängigkeiten** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f54a7-117">Click **Show Dependencies** in the **Delete Object** dialog box to open the _view_name_**Dependencies** dialog box.</span></span> <span data-ttu-id="f54a7-118">Es werden alle Objekte angezeigt, die von der Sicht abhängig sind, und alle Objekte, von denen die Sicht abhängig ist.</span><span class="sxs-lookup"><span data-stu-id="f54a7-118">This will show all of the objects that depend on the view and all of the objects on which the view depends.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="f54a7-119">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f54a7-119">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-view-from-a-database"></a><span data-ttu-id="f54a7-120">So löschen Sie eine Sicht aus einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="f54a7-120">To delete a view from a database</span></span>  
  
1.  <span data-ttu-id="f54a7-121">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="f54a7-121">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f54a7-122">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="f54a7-122">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f54a7-123">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="f54a7-123">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="f54a7-124">Im Beispiel wird die angegebene Sicht nur gelöscht, wenn die Sicht bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="f54a7-124">The example deletes the specified view only if the view already exists.</span></span>  
  
    ```  
    USE AdventureWorks2012 ;  
    GO  
    IF OBJECT_ID ('HumanResources.EmployeeHireDate', 'V') IS NOT NULL  
    DROP VIEW HumanResources.EmployeeHireDate;  
    GO  
    ```  
  
 <span data-ttu-id="f54a7-125">Weitere Informationen finden Sie unter [DROP VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-view-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f54a7-125">For more information, see [DROP VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-view-transact-sql).</span></span>  
  
  
