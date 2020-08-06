---
title: Erstellen von Sichten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- views [SQL Server], creating
ms.assetid: 0b7bd2a1-544c-42ba-8e7b-4822f34d7b64
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8280f6d65d7252cad423abef849207111492c044
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608468"
---
# <a name="create-views"></a><span data-ttu-id="c0356-102">Erstellen von Sichten</span><span class="sxs-lookup"><span data-stu-id="c0356-102">Create Views</span></span>
  <span data-ttu-id="c0356-103">Sie können in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]Sichten erstellen.</span><span class="sxs-lookup"><span data-stu-id="c0356-103">You can create views in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="c0356-104">Eine Sicht kann für folgende Zwecke verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="c0356-104">A view can be used for the following purposes:</span></span>  
  
-   <span data-ttu-id="c0356-105">Um die Darstellung einer Datenbank für jeden einzelnen Benutzer einzuschränken, zu vereinfachen und anzupassen.</span><span class="sxs-lookup"><span data-stu-id="c0356-105">To focus, simplify, and customize the perception each user has of the database.</span></span>  
  
-   <span data-ttu-id="c0356-106">Als Sicherheitsmechanismus, indem Benutzern der Zugriff auf Daten über die Sicht ermöglicht wird, ohne diesen Benutzern jedoch die Berechtigungen für den direkten Zugriff auf die zugrunde liegenden Basistabellen zu gewähren.</span><span class="sxs-lookup"><span data-stu-id="c0356-106">As a security mechanism by allowing users to access data through the view, without granting the users permissions to directly access the underlying base tables.</span></span>  
  
-   <span data-ttu-id="c0356-107">Um eine abwärtskompatible Schnittstelle zum Emulieren einer Tabelle bereitzustellen, deren Schema geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="c0356-107">To provide a backward compatible interface to emulate a table whose schema has changed.</span></span>  
  
 <span data-ttu-id="c0356-108">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="c0356-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c0356-109">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="c0356-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c0356-110">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="c0356-110">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="c0356-111">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="c0356-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c0356-112">**So erstellen Sie eine Sicht mit:**</span><span class="sxs-lookup"><span data-stu-id="c0356-112">**To create a view, using:**</span></span>  
  
     [<span data-ttu-id="c0356-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c0356-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="c0356-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c0356-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c0356-115">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="c0356-115">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="c0356-116">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="c0356-116">Limitations and Restrictions</span></span>  
 <span data-ttu-id="c0356-117">Eine Sicht kann nur in der aktuellen Datenbank erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="c0356-117">A view can be created only in the current database.</span></span>  
  
 <span data-ttu-id="c0356-118">Für eine Sicht sind maximal 1.024 Spalten zulässig.</span><span class="sxs-lookup"><span data-stu-id="c0356-118">A view can have a maximum of 1,024 columns.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c0356-119">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="c0356-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c0356-120">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="c0356-120">Permissions</span></span>  
 <span data-ttu-id="c0356-121">Erfordert die CREATE VIEW-Berechtigung in der Datenbank und die ALTER-Berechtigung für das Schema, in dem die Sicht erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="c0356-121">Requires CREATE VIEW permission in the database and ALTER permission on the schema in which the view is being created.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c0356-122">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c0356-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-view-by-using-the-query-and-view-designer"></a><span data-ttu-id="c0356-123">So erstellen Sie eine Sicht mit dem Abfrage- und Sicht-Designer</span><span class="sxs-lookup"><span data-stu-id="c0356-123">To create a view by using the Query and View Designer</span></span>  
  
1.  <span data-ttu-id="c0356-124">Erweitern Sie im **Objekt-Explorer**die Datenbank, in der Sie die neue Sicht erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="c0356-124">In **Object Explorer**, expand the database where you want to create your new view.</span></span>  
  
2.  <span data-ttu-id="c0356-125">Klicken Sie mit der rechten Maustaste auf den Ordner **Sichten**, und klicken Sie anschließend auf **Neue Sicht…** .</span><span class="sxs-lookup"><span data-stu-id="c0356-125">Right-click the **Views** folder, then click **New View...**.</span></span>  
  
3.  <span data-ttu-id="c0356-126">Wählen Sie im Dialogfeld **Tabelle hinzufügen** das Element oder die Elemente, die Sie in die neue Sicht einschließen möchten, auf einer der folgenden Registerkarten aus: Tabellen, Sichten, Funktionen und Synonyme.</span><span class="sxs-lookup"><span data-stu-id="c0356-126">In the **Add Table** dialog box, select the element or elements that you want to include in your new view from one of the following tabs: Tables, Views, Functions, and Synonyms.</span></span>  
  
4.  <span data-ttu-id="c0356-127">Klicken Sie auf **Hinzufügen**und dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="c0356-127">Click **Add**, then click **Close**.</span></span>  
  
5.  <span data-ttu-id="c0356-128">Wählen Sie im **Diagrammbereich**die Spalten bzw. die anderen Elemente aus, die in der neuen Sicht enthalten sein sollen.</span><span class="sxs-lookup"><span data-stu-id="c0356-128">In the **Diagram Pane**, select the columns or other elements to include in the new view.</span></span>  
  
6.  <span data-ttu-id="c0356-129">Wählen Sie im **Kriterienbereich**zusätzliche Sortier- oder Filterkriterien für die Spalten aus.</span><span class="sxs-lookup"><span data-stu-id="c0356-129">In the **Criteria Pane**, select additional sort or filter criteria for the columns.</span></span>  
  
7.  <span data-ttu-id="c0356-130">Klicken Sie im Menü **Datei** auf **Speichern**_view name_.</span><span class="sxs-lookup"><span data-stu-id="c0356-130">On the **File** menu, click **Save**_view name_.</span></span>  
  
8.  <span data-ttu-id="c0356-131">Geben Sie im Dialogfeld **Namen auswählen** einen Namen für die neue Sicht ein, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="c0356-131">In the **Choose Name** dialog box, enter a name for the new view and click **OK**.</span></span>  
  
     <span data-ttu-id="c0356-132">Weitere Informationen über den Abfrage- und Sicht-Designer finden Sie unter [Tools im Abfrage- und Sicht-Designer &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c0356-132">For more information about the query and view designer, see [Query and View Designer Tools &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/visual-database-tools.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c0356-133">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c0356-133">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-view"></a><span data-ttu-id="c0356-134">So erstellen Sie eine Sicht</span><span class="sxs-lookup"><span data-stu-id="c0356-134">To create a view</span></span>  
  
1.  <span data-ttu-id="c0356-135">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="c0356-135">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c0356-136">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="c0356-136">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c0356-137">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="c0356-137">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012 ;   
    GO  
    CREATE VIEW HumanResources.EmployeeHireDate  
    AS  
    SELECT p.FirstName, p.LastName, e.HireDate  
    FROM HumanResources.Employee AS e JOIN Person.Person AS  p  
    ON e.BusinessEntityID = p.BusinessEntityID ;   
    GO  
    -- Query the view  
    SELECT FirstName, LastName, HireDate  
    FROM HumanResources.EmployeeHireDate  
    ORDER BY LastName;  
  
    ```  
  
 <span data-ttu-id="c0356-138">Weitere Informationen finden Sie unter [CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c0356-138">For more information, see [CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql).</span></span>  
  
  
