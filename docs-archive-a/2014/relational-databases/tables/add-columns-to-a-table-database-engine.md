---
title: Hinzufügen von Spalten zu einer Tabelle (Datenbank-Engine) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- inserting columns
- columns [SQL Server], adding
- adding columns
ms.assetid: abeb8d52-d562-4e29-9e1e-2923ae874859
author: stevestein
ms.author: sstein
ms.openlocfilehash: f7e9294de10be0df9ef470c75d0934e9f8787b55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617880"
---
# <a name="add-columns-to-a-table-database-engine"></a><span data-ttu-id="bb53e-102">Hinzufügen von Spalten zu einer Tabelle (Datenbank-Engine)</span><span class="sxs-lookup"><span data-stu-id="bb53e-102">Add Columns to a Table (Database Engine)</span></span>
  <span data-ttu-id="bb53e-103">In diesem Thema wird beschrieben, wie mit [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] oder [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Tabellenspalten in [!INCLUDE[tsql](../../includes/tsql-md.md)]hinzugefügt werden können.</span><span class="sxs-lookup"><span data-stu-id="bb53e-103">This topic describes how to add new columns to a table in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="bb53e-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="bb53e-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="bb53e-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="bb53e-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="bb53e-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="bb53e-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="bb53e-107">Security</span><span class="sxs-lookup"><span data-stu-id="bb53e-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="bb53e-108">**So fügen Sie Spalten ein mit:**</span><span class="sxs-lookup"><span data-stu-id="bb53e-108">**To insert columns, using:**</span></span>  
  
     [<span data-ttu-id="bb53e-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="bb53e-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="bb53e-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="bb53e-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="bb53e-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="bb53e-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="bb53e-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="bb53e-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="bb53e-113">Wenn Spalten mithilfe der ALTER TABLE-Anweisung zu einer Tabelle hinzugefügt werden, dann werden diese Spalten automatisch am Ende der Tabelle hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="bb53e-113">Using the ALTER TABLE statement to add columns to a table automatically adds those columns to the end of the table.</span></span> <span data-ttu-id="bb53e-114">Wenn die Spalten in einer bestimmten Reihenfolge in der Tabelle eingefügt werden sollen, verwenden Sie [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bb53e-114">If you want the columns in a specific order in the table, use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="bb53e-115">Beachten Sie jedoch, dass dies keine Best Practice für den Datenbankentwurf-ist.</span><span class="sxs-lookup"><span data-stu-id="bb53e-115">However, note that this is not a database design best practice.</span></span> <span data-ttu-id="bb53e-116">Best Practice ist, in der Anwendung oder auf der Abfrageebene die Reihenfolge anzugeben, in der die Spalten zurückgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="bb53e-116">Best practice is to specify the order in which the columns are returned at the application and query level.</span></span> <span data-ttu-id="bb53e-117">Sie sollten sich nicht darauf verlassen, dass bei Verwendung von SELECT \* alle Spalten in der Reihenfolge, in der sie in der Tabelle definiert worden sind, zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="bb53e-117">You should not rely on the use of SELECT \* to return all columns in an expected order based on the order in which they are defined in the table.</span></span> <span data-ttu-id="bb53e-118">Geben Sie die Spalten in Abfragen und Anwendungen immer namentlich in der Reihenfolge an, in der sie angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="bb53e-118">Always specify the columns by name in your queries and applications in the order in which you would like them to appear.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="bb53e-119">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="bb53e-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="bb53e-120">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="bb53e-120">Permissions</span></span>  
 <span data-ttu-id="bb53e-121">Erfordert die ALTER-Berechtigung für die Tabelle.</span><span class="sxs-lookup"><span data-stu-id="bb53e-121">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="bb53e-122">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="bb53e-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-insert-columns-into-a-table-with-table-designer"></a><span data-ttu-id="bb53e-123">So fügen Sie mit dem Tabellen-Designer Spalten in eine Tabelle ein</span><span class="sxs-lookup"><span data-stu-id="bb53e-123">To insert columns into a table with Table Designer</span></span>  
  
1.  <span data-ttu-id="bb53e-124">Klicken Sie im **Objekt-Explorer**mit der rechten Maustaste auf die Tabelle, der Sie Spalten hinzufügen möchten, und klicken Sie dann auf **Entwerfen**.</span><span class="sxs-lookup"><span data-stu-id="bb53e-124">In **Object Explorer**, right-click the table to which you want to add columns and choose **Design**.</span></span>  
  
2.  <span data-ttu-id="bb53e-125">Klicken Sie auf die leere Zelle in der Spalte **Spaltenname** .</span><span class="sxs-lookup"><span data-stu-id="bb53e-125">Click in the first blank cell in the **Column Name** column.</span></span>  
  
3.  <span data-ttu-id="bb53e-126">Geben Sie den Spaltennamen in die Zelle ein.</span><span class="sxs-lookup"><span data-stu-id="bb53e-126">Type the column name in the cell.</span></span> <span data-ttu-id="bb53e-127">Der Spaltenname muss angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="bb53e-127">The column name is a required value.</span></span>  
  
4.  <span data-ttu-id="bb53e-128">Drücken Sie die TAB-TASTE, um zu der Zelle **Datentyp** zu gelangen, und wählen Sie in der Dropdownliste einen Datentyp aus.</span><span class="sxs-lookup"><span data-stu-id="bb53e-128">Press the TAB key to go to the **Data Type** cell and select a data type from the dropdown.</span></span> <span data-ttu-id="bb53e-129">Dieser Wert ist ebenfalls obligatorisch. Wenn Sie keinen Wert auswählen, wird der Standardwert verwendet.</span><span class="sxs-lookup"><span data-stu-id="bb53e-129">This too is a required value, and will be assigned the default value if you don't choose one.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bb53e-130"> Sie können den Standardwert im Dialogfeld **Optionen** unter **Datenbanktools**ändern.</span><span class="sxs-lookup"><span data-stu-id="bb53e-130">You can change the default value in the **Options** dialog box under **Database Tools**.</span></span>  
  
5.  <span data-ttu-id="bb53e-131">Definieren Sie auf der Registerkarte **Spalteneigenschaften** weitere Spalteneigenschaften.</span><span class="sxs-lookup"><span data-stu-id="bb53e-131">Continue to define any other column properties in the **Column Properties** tab.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bb53e-132"> Die Standardwerte für die Spalteneigenschaften werden hinzugefügt, wenn Sie eine neue Spalte erstellen. Sie können die Werte jedoch auf der Registerkarte **Spalteneigenschaften** ändern.</span><span class="sxs-lookup"><span data-stu-id="bb53e-132">The default values for your column properties are added when you create a new column, but you can change them in the **Column Properties** tab.</span></span>  
  
6.  <span data-ttu-id="bb53e-133">Wenn Sie die gewünschten Spalten hinzugefügt haben, wählen Sie im Menü **Datei** die Option _Tabellenname_**speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="bb53e-133">When you are finished adding columns, from the **File** menu, choose **Save**_table name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="bb53e-134">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="bb53e-134">Using Transact-SQL</span></span>  
  
#### <a name="to-insert-columns-into-a-table"></a><span data-ttu-id="bb53e-135">So fügen Sie Spalten eine neue Tabelle ein</span><span class="sxs-lookup"><span data-stu-id="bb53e-135">To insert columns into a table</span></span>  
  
1.  <span data-ttu-id="bb53e-136">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="bb53e-136">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="bb53e-137">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="bb53e-137">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="bb53e-138">Im folgenden Beispiel werden der Tabelle `dbo.doc_exa`zwei Spalten hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="bb53e-138">The following example adds two columns to the table `dbo.doc_exa`.</span></span> <span data-ttu-id="bb53e-139">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="bb53e-139">Copy and paste the following example into the query window and click **Execute**</span></span>  
  
```  
ALTER TABLE dbo.doc_exa ADD column_b VARCHAR(20) NULL, column_c INT NULL ;  
```  
  
##  <a name="for-more-information-see-alter-table-40transact-sql41"></a><a name="FollowUp"></a><span data-ttu-id="bb53e-140">Weitere Informationen finden Sie unter [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="bb53e-140">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql)</span></span>  
  
  
