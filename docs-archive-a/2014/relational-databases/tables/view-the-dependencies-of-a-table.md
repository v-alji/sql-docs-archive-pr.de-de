---
title: Anzeigen der Abhängigkeiten einer Tabelle | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- table dependencies [SQL Server]
- dependencies [SQL Server], tables
- displaying dependences
- viewing dependencies
ms.assetid: c4351ef5-e7d0-46e7-8367-88695e9974f8
author: stevestein
ms.author: sstein
ms.openlocfilehash: 20f54b913124cdaa8a7dfeebac01ba070cc37d88
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630582"
---
# <a name="view-the-dependencies-of-a-table"></a><span data-ttu-id="c6e86-102">Anzeigen der Abhängigkeiten einer Tabelle</span><span class="sxs-lookup"><span data-stu-id="c6e86-102">View the Dependencies of a Table</span></span>
  <span data-ttu-id="c6e86-103">Sie können die Abhängigkeiten einer Tabelle in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)] anzeigen.</span><span class="sxs-lookup"><span data-stu-id="c6e86-103">You can view a table's dependencies in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="c6e86-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="c6e86-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c6e86-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="c6e86-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c6e86-106">Security</span><span class="sxs-lookup"><span data-stu-id="c6e86-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c6e86-107">**So zeigen Sie die Abhängigkeiten einer Tabelle mit folgenden Elementen an:**</span><span class="sxs-lookup"><span data-stu-id="c6e86-107">**To view a table's dependencies, using:**</span></span>  
  
     [<span data-ttu-id="c6e86-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c6e86-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="c6e86-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c6e86-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c6e86-110">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="c6e86-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c6e86-111">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="c6e86-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c6e86-112">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="c6e86-112">Permissions</span></span>  
 <span data-ttu-id="c6e86-113">Erfordert die VIEW DEFINITION-Berechtigung für die Datenbank und die SELECT-Berechtigung für sys.sql_expression_dependencies für die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="c6e86-113">Requires VIEW DEFINITION permission on the database and SELECT permission on sys.sql_expression_dependencies for the database.</span></span> <span data-ttu-id="c6e86-114">Standardmäßig wird die SELECT-Berechtigung nur Mitgliedern der festen Datenbankrolle db_owner gewährt.</span><span class="sxs-lookup"><span data-stu-id="c6e86-114">By default, SELECT permission is granted only to members of the db_owner fixed database role.</span></span> <span data-ttu-id="c6e86-115">Wenn einem anderen Benutzer die SELECT-Berechtigung und die VIEW DEFINITION-Berechtigung erteilt werden, kann dieser Berechtigte alle Abhängigkeiten in der Datenbank anzeigen.</span><span class="sxs-lookup"><span data-stu-id="c6e86-115">When SELECT and VIEW DEFINITION permissions are granted to another user, the grantee can view all dependencies in the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c6e86-116">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c6e86-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-dependencies-of-a-table"></a><span data-ttu-id="c6e86-117">So zeigen Sie die Abhängigkeiten einer Tabelle an</span><span class="sxs-lookup"><span data-stu-id="c6e86-117">To view the dependencies of a table</span></span>  
  
1.  <span data-ttu-id="c6e86-118">Erweitern Sie im **Objekt-Explorer**den Ordner **Datenbanken**, erweitern Sie eine Datenbank, und erweitern Sie dann **Tabellen**.</span><span class="sxs-lookup"><span data-stu-id="c6e86-118">In **Object Explorer**, expand **Databases**, expand a database, and then expand **Tables**.</span></span>  
  
2.  <span data-ttu-id="c6e86-119">Klicken Sie mit der rechten Maustaste auf eine Tabelle, und klicken Sie dann auf **Abhängigkeiten anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="c6e86-119">Right-click a table, and then click **View Dependencies**.</span></span>  
  
3.  <span data-ttu-id="c6e86-120">Wählen Sie im Dialogfeld **Objektabhängigkeiten** _\<object name>_ entweder **Objekte, die von**  abhängig sind _\<object name>_ oder **Objekte, von denen** _\<object name>_ **abhängt** aus.</span><span class="sxs-lookup"><span data-stu-id="c6e86-120">In the **Object Dependencies**_\<object name>_ dialog box, select either **Objects that depend on** _\<object name>_, or **Objects on which**_\<object name>_**depends**.</span></span>  
  
4.  <span data-ttu-id="c6e86-121">Wählen Sie im Raster **Abhängigkeiten** ein Objekt aus.</span><span class="sxs-lookup"><span data-stu-id="c6e86-121">Select an object in the **Dependencies** grid.</span></span> <span data-ttu-id="c6e86-122">Der Objekttyp (z.B. „Trigger“ oder „Gespeicherte Prozedur“) wird im Feld **Typ** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c6e86-122">The type of object (such as "Trigger" or "Stored Procedure"), appears in the **Type** box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c6e86-123">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c6e86-123">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-objects-that-depend-on-a-table"></a><span data-ttu-id="c6e86-124">So zeigen Sie die Objekte an, die von einer Tabelle abhängen</span><span class="sxs-lookup"><span data-stu-id="c6e86-124">To view the objects that depend on a table</span></span>  
  
1.  <span data-ttu-id="c6e86-125">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="c6e86-125">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c6e86-126">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="c6e86-126">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c6e86-127">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="c6e86-127">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT * FROM sys.sql_expression_dependencies  
    WHERE referencing_id = OBJECT_ID(N'Production.vProductAndDescription');   
    GO  
  
    ```  
  
#### <a name="to-view-the-objects-on-which-a-table-depends"></a><span data-ttu-id="c6e86-128">So zeigen Sie die Objekte an, von denen eine Tabelle abhängt</span><span class="sxs-lookup"><span data-stu-id="c6e86-128">To view the objects on which a table depends</span></span>  
  
1.  <span data-ttu-id="c6e86-129">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="c6e86-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c6e86-130">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="c6e86-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c6e86-131">Im folgenden Beispiel werden die Objekte, die von der Tabelle `Production.Product`abhängen, zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c6e86-131">The following example returns the objects that depend on the table `Production.Product`.</span></span> <span data-ttu-id="c6e86-132">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="c6e86-132">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    SELECT * FROM sys.sql_expression_dependencies  
    WHERE referenced_id = OBJECT_ID(N'Production.Product');   
    GO  
  
    ```  
  
 <span data-ttu-id="c6e86-133">Weitere Informationen finden Sie unter [sys.sql_expression_dependencies &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c6e86-133">For additional information, see [sys.sql_expression_dependencies &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql)</span></span>  
  
  
