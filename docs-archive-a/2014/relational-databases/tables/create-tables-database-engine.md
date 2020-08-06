---
title: Erstellen von Tabellen (Datenbank-Engine) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- table creation [SQL Server], Visual Database Tools
ms.assetid: 6f7c6ac5-e6d3-4dca-831e-b28442ba535b
author: stevestein
ms.author: sstein
ms.openlocfilehash: a8d84a4da6a10fbcbae311fe1bf738c03b85a4c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630589"
---
# <a name="create-tables-database-engine"></a><span data-ttu-id="1aa52-102">Erstellen von Tabellen (Datenbank-Engine)</span><span class="sxs-lookup"><span data-stu-id="1aa52-102">Create Tables (Database Engine)</span></span>
  <span data-ttu-id="1aa52-103">Sie können mit [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] oder [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] eine neue Tabelle erstellen, diese benennen und einer vorhandenen Datenbank in [!INCLUDE[tsql](../../includes/tsql-md.md)]hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="1aa52-103">You can create a new table, name it, and add it to an existing database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>

> [!NOTE]
>  <span data-ttu-id="1aa52-104">Wenn Sie mit einer SQL Azure-Datenbank verbunden sind, startet die neue Tabellenoption ein Vorlagenskript zum Erstellen einer Tabelle.</span><span class="sxs-lookup"><span data-stu-id="1aa52-104">If you are connected to a SQL Azure database, the new table option launches a create table template script.</span></span> <span data-ttu-id="1aa52-105">Bearbeiten Sie die Parameter, und führen Sie dann das Skript aus, um eine neue Tabelle zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1aa52-105">Edit the parameters, then run the script to create a new table.</span></span> <span data-ttu-id="1aa52-106">Weitere Informationen finden Sie unter [SQL Azure-Übersicht](https://microsoft.sharepoint.com/sites/infopedia_g01/pages/cards/azure-sql-database.aspx)(möglicherweise auf Englisch).</span><span class="sxs-lookup"><span data-stu-id="1aa52-106">For more information, see [SQL Azure Overview](https://microsoft.sharepoint.com/sites/infopedia_g01/pages/cards/azure-sql-database.aspx).</span></span>

 <span data-ttu-id="1aa52-107">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="1aa52-107">**In This Topic**</span></span>

-   <span data-ttu-id="1aa52-108">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="1aa52-108">**Before you begin:**</span></span>

     [<span data-ttu-id="1aa52-109">Security</span><span class="sxs-lookup"><span data-stu-id="1aa52-109">Security</span></span>](#Security)

-   <span data-ttu-id="1aa52-110">**So erstellen Sie eine Tabelle mit:**</span><span class="sxs-lookup"><span data-stu-id="1aa52-110">**To create a table, using:**</span></span>

     [<span data-ttu-id="1aa52-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1aa52-111">SQL Server Management Studio</span></span>](#SSMSProcedure)

     [<span data-ttu-id="1aa52-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1aa52-112">Transact-SQL</span></span>](#TsqlProcedure)

##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1aa52-113">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="1aa52-113">Before You Begin</span></span>

###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="1aa52-114">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="1aa52-114">Security</span></span>

####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="1aa52-115">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="1aa52-115">Permissions</span></span>
 <span data-ttu-id="1aa52-116">Es sind die CREATE TABLE-Berechtigung in der Datenbank und die ALTER-Berechtigung für das Schema erforderlich, in der die Tabelle erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="1aa52-116">Requires CREATE TABLE permission in the database and ALTER permission on the schema in which the table is being created.</span></span>

 <span data-ttu-id="1aa52-117">Wenn in der CREATE TABLE-Anweisung Spalten als CLR-benutzerdefinierter Typ definiert sind, ist entweder der Besitz des Typs oder die REFERENCES-Berechtigung für den Typ erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1aa52-117">If any columns in the CREATE TABLE statement are defined as a CLR user-defined type, either ownership of the type or REFERENCES permission on it is required.</span></span>

 <span data-ttu-id="1aa52-118">Wenn einer Spalte in der CREATE TABLE-Anweisung eine XML-Schemaauflistung zugeordnet ist, ist entweder der Besitz der XML-Schemaauflistung oder die REFERENCES-Berechtigung für die Auflistung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1aa52-118">If any columns in the CREATE TABLE statement have an XML schema collection associated with them, either ownership of the XML schema collection or REFERENCES permission on it is required.</span></span>

##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="1aa52-119">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1aa52-119">Using SQL Server Management Studio</span></span>

#### <a name="to-create-a-table-with-table-designer"></a><span data-ttu-id="1aa52-120">So erstellen Sie eine Tabelle mit dem Tabellen-Designer</span><span class="sxs-lookup"><span data-stu-id="1aa52-120">To create a table with Table Designer</span></span>

1.  <span data-ttu-id="1aa52-121">Stellen Sie im **Objekt-Explorer**eine Verbindung mit der [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Instanz her, in der die zu ändernde Datenbank enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="1aa52-121">In **Object Explorer**, connect to the instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] that contains the database to be modified.</span></span>

2.  <span data-ttu-id="1aa52-122">Erweitern Sie im **Objekt-Explorer**zuerst den Knoten **Datenbanken** und dann die Datenbank, in der die neue Tabelle angelegt werden soll.</span><span class="sxs-lookup"><span data-stu-id="1aa52-122">In **Object Explorer**, expand the **Databases** node and then expand the database that will contain the new table.</span></span>

3.  <span data-ttu-id="1aa52-123">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf den Knoten **Tabellen** der Datenbank, und klicken Sie auf **Neue Tabelle**.</span><span class="sxs-lookup"><span data-stu-id="1aa52-123">In Object Explorer, right-click the **Tables** node of your database and then click **New Table**.</span></span>

4.  <span data-ttu-id="1aa52-124">Geben Sie für die einzelnen Spalten Spaltennamen ein, wählen Sie Datentypen aus, und legen Sie fest, ob NULL-Werte zulässig sein sollen, wie in der folgenden Abbildung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="1aa52-124">Type column names, choose data types, and choose whether to allow nulls for each column as shown in the following illustration.</span></span>

     <span data-ttu-id="1aa52-125">![Spalten im Tabellen-Designer hinzufügen](../../database-engine/media/addcolumnsintabledesigner.gif "Spalten im Tabellen-Designer hinzufügen")</span><span class="sxs-lookup"><span data-stu-id="1aa52-125">![AddColumnsinTableDesigner](../../database-engine/media/addcolumnsintabledesigner.gif "AddColumnsinTableDesigner")</span></span>

5.  <span data-ttu-id="1aa52-126">Um weitere Eigenschaften für eine Spalte anzugeben, z. B. die Identität oder Werte für berechnete Spalten, klicken Sie auf die Spalte und wählen auf der Registerkarte mit den Spalteneigenschaften die geeigneten Eigenschaften aus.</span><span class="sxs-lookup"><span data-stu-id="1aa52-126">To specify more properties for a column, such as identity or computed column values, click the column and in the column properties tab, choose the appropriate properties.</span></span> <span data-ttu-id="1aa52-127">Weitere Informationen zu Spalteneigenschaften finden Sie unter [Tabellenspalteneigenschaften &#40;SQL Server Management Studio&#41;](table-column-properties-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="1aa52-127">For more information about column properties, see [Table Column Properties &#40;SQL Server Management Studio&#41;](table-column-properties-sql-server-management-studio.md).</span></span>

6.  <span data-ttu-id="1aa52-128">Um eine Spalte als Primärschlüssel festzulegen, klicken Sie mit der rechten Maustaste darauf, und wählen Sie **Primärschlüssel festlegen**aus.</span><span class="sxs-lookup"><span data-stu-id="1aa52-128">To specify a column as a primary key, right-click the column and select **Set Primary Key**.</span></span> <span data-ttu-id="1aa52-129">Weitere Informationen finden Sie unter [Create Primary Keys](../tables/create-primary-keys.md).</span><span class="sxs-lookup"><span data-stu-id="1aa52-129">For more information, see [Create Primary Keys](../tables/create-primary-keys.md).</span></span>

7.  <span data-ttu-id="1aa52-130">Um Fremdschlüsselbeziehungen, CHECK-Einschränkungen oder Indizes zu erstellen, klicken Sie mit der rechten Maustaste in den Bereich des Tabellen-Designers und wählen ein Objekt aus der Liste aus, wie in der folgenden Abbildung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="1aa52-130">To create foreign key relationships, check constraints, or indexes, right-click in the Table Designer pane and select an object from the list as shown in the following illustration.</span></span>

     <span data-ttu-id="1aa52-131">![Tabellenobjekte hinzufügen](../../database-engine/media/addtableobjects.gif "Tabellenobjekte hinzufügen")</span><span class="sxs-lookup"><span data-stu-id="1aa52-131">![AddTableObjects](../../database-engine/media/addtableobjects.gif "AddTableObjects")</span></span>

     <span data-ttu-id="1aa52-132">Weitere Informationen zu diesen Objekten finden Sie unter [Create Foreign Key Relationships](../tables/create-foreign-key-relationships.md), [Create Check Constraints](../tables/create-check-constraints.md) und [Indexes](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="1aa52-132">For more information about these objects, see [Create Foreign Key Relationships](../tables/create-foreign-key-relationships.md), [Create Check Constraints](../tables/create-check-constraints.md) and [Indexes](../indexes/indexes.md).</span></span>

8.  <span data-ttu-id="1aa52-133">Die Tabelle ist standardmäßig im **dbo** -Schema enthalten.</span><span class="sxs-lookup"><span data-stu-id="1aa52-133">By default, the table is contained in the **dbo** schema.</span></span> <span data-ttu-id="1aa52-134">Um ein anderes Schema für die Tabelle anzugeben, klicken Sie mit der rechten Maustaste in den Bereich des Tabellen-Designers, und wählen Sie **Eigenschaften** aus, wie in der folgenden Abbildung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="1aa52-134">To specify a different schema for the table, right-click in the Table Designer pane and select **Properties** as shown in the following illustration.</span></span> <span data-ttu-id="1aa52-135">Wählen Sie in der Dropdownliste **Schema** das geeignete Schema aus.</span><span class="sxs-lookup"><span data-stu-id="1aa52-135">From the **Schema** drop-down list, select the appropriate schema.</span></span>

     <span data-ttu-id="1aa52-136">![Tabellenschema angeben](../../database-engine/media/specifyatableschema.gif "Tabellenschema angeben")</span><span class="sxs-lookup"><span data-stu-id="1aa52-136">![Specifyatableschema](../../database-engine/media/specifyatableschema.gif "Specifyatableschema")</span></span>

     <span data-ttu-id="1aa52-137">Weitere Informationen zu Schemas finden Sie unter [Create a Database Schema](../security/authentication-access/create-a-database-schema.md).</span><span class="sxs-lookup"><span data-stu-id="1aa52-137">For more information about schemas, see [Create a Database Schema](../security/authentication-access/create-a-database-schema.md).</span></span>

9. <span data-ttu-id="1aa52-138">Wählen Sie im Menü **Datei** den Befehl *Tabellennamen* **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="1aa52-138">From the **File** menu, choose **Save** *table name*.</span></span>

10. <span data-ttu-id="1aa52-139">Geben Sie im Dialogfeld **Namen auswählen** einen Namen für die Tabelle ein, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="1aa52-139">In the **Choose Name** dialog box, type a name for the table and click **OK**.</span></span>

11. <span data-ttu-id="1aa52-140">Zum Anzeigen der neuen Tabelle erweitern Sie im **Objekt-Explorer**den Knoten **Tabellen** und drücken **F5** , um die Objektliste zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="1aa52-140">To view the new table, in **Object Explorer**, expand the **Tables** node and press **F5** to refresh the list of objects.</span></span> <span data-ttu-id="1aa52-141">Die neue Tabelle wird in der Tabellenliste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1aa52-141">The new table is displayed in the list of tables.</span></span>

##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="1aa52-142">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1aa52-142">Using Transact-SQL</span></span>

#### <a name="to-create-a-table-in-the-query-editor"></a><span data-ttu-id="1aa52-143">So erstellen Sie eine Tabelle im Abfrage-Editor</span><span class="sxs-lookup"><span data-stu-id="1aa52-143">To create a table in the Query Editor</span></span>

1.  <span data-ttu-id="1aa52-144">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="1aa52-144">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>

2.  <span data-ttu-id="1aa52-145">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="1aa52-145">On the Standard bar, click **New Query**.</span></span>

3.  <span data-ttu-id="1aa52-146">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="1aa52-146">Copy and paste the following example into the query window and click **Execute**.</span></span>

    ```
    CREATE TABLE dbo.PurchaseOrderDetail
    (
        PurchaseOrderID int NOT NULL
        ,LineNumber smallint NOT NULL
        ,ProductID int NULL
        ,UnitPrice money NULL
        ,OrderQty smallint NULL
        ,ReceivedQty float NULL
        ,RejectedQty float NULL
        ,DueDate datetime NULL
    );
    ```

 <span data-ttu-id="1aa52-147">Weitere Beispiele finden Sie unter [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1aa52-147">For more examples, see [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql).</span></span>


