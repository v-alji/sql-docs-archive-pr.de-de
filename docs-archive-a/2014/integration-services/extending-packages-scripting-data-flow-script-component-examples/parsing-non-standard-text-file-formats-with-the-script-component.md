---
title: Analysieren von nicht standardmäßigen Textdateiformaten mit der Skriptkomponente | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- text file reading [Integration Services]
- Script component [Integration Services], non-standard text file formats
- transformations [Integration Services], components
- Script component [Integration Services], examples
ms.assetid: 1fda034d-09e4-4647-9a9f-e8d508c2cc8f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6a0ca1a0d10bdad40d39a366864a07d2b0a61d13
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696997"
---
# <a name="parsing-non-standard-text-file-formats-with-the-script-component"></a><span data-ttu-id="6e3f2-102">Analysieren von nicht standardmäßigen Textdateiformaten mit der Skriptkomponente</span><span class="sxs-lookup"><span data-stu-id="6e3f2-102">Parsing Non-Standard Text File Formats with the Script Component</span></span>
  <span data-ttu-id="6e3f2-103">Wenn Ihre Quelldaten in einem nicht standardmäßigen Format angeordnet sind, dann könnte es u. U. praktischer sein, Ihre gesamte Parser-Logik in einem einzigen Skript zu konsolidieren, anstatt mehrere [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Transformationen miteinander zu verketten, um das gleiche Ergebnis zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="6e3f2-103">When your source data is arranged in a non-standard format, you may find it more convenient to consolidate all your parsing logic in a single script than to chain together multiple [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] transformations to achieve the same result.</span></span>  
  
 [<span data-ttu-id="6e3f2-104">Beispiel 1: Analysieren von nach Zeilen getrennten Datensätzen</span><span class="sxs-lookup"><span data-stu-id="6e3f2-104">Example 1: Parsing Row-Delimited Records</span></span>](#example1)  
  
 [<span data-ttu-id="6e3f2-105">Beispiel 2: Teilen von übergeordneten und untergeordneten Datensätzen</span><span class="sxs-lookup"><span data-stu-id="6e3f2-105">Example 2: Splitting Parent and Child Records</span></span>](#example2)  
  
> [!NOTE]  
>  <span data-ttu-id="6e3f2-106">Wenn Sie eine Komponente erstellen möchten, die Sie einfacher in mehreren Datenflusstasks und Paketen wiederverwenden können, empfiehlt es sich, den Code in diesem Skriptkomponentenbeispiel als Ausgangspunkt für eine benutzerdefinierte Datenflusskomponente zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="6e3f2-106">If you want to create a component that you can more easily reuse across multiple Data Flow tasks and multiple packages, consider using the code in this Script component sample as the starting point for a custom data flow component.</span></span> <span data-ttu-id="6e3f2-107">Weitere Informationen finden Sie unter [Entwickeln einer benutzerdefinierten Datenflusskomponente](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="6e3f2-107">For more information, see [Developing a Custom Data Flow Component](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span></span>  
  
##  <a name="example-1-parsing-row-delimited-records"></a><a name="example1"></a> <span data-ttu-id="6e3f2-108">Beispiel 1: Analysieren von nach Zeilen getrennten Datensätzen</span><span class="sxs-lookup"><span data-stu-id="6e3f2-108">Example 1: Parsing Row-Delimited Records</span></span>  
 <span data-ttu-id="6e3f2-109">In diesem Beispiel wird gezeigt, wie eine Textdatei, in der sich jede Datenspalte auf einer separaten Zeile befindet, mithilfe der Skriptkomponente in eine Zieltabelle konvertiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="6e3f2-109">This example shows how to take a text file in which each column of data appears on a separate line and parse it into a destination table by using the Script component.</span></span>  
  
 <span data-ttu-id="6e3f2-110">Weitere Informationen zum Konfigurieren der Skript Komponente für die Verwendung als Transformation im Datenfluss finden Sie unter [Erstellen einer synchronen Transformation mit der Skript Komponente](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md)und [Erstellen einer asynchronen Transformation mit der Skript Komponente](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="6e3f2-110">For more information about how to configure the Script component for use as a transformation in the data flow, see [Creating a Synchronous Transformation with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md)and [Creating an Asynchronous Transformation with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md).</span></span>  
  
#### <a name="to-configure-this-script-component-example"></a><span data-ttu-id="6e3f2-111">So konfigurieren Sie dieses Skriptkomponentenbeispiel</span><span class="sxs-lookup"><span data-stu-id="6e3f2-111">To configure this Script Component example</span></span>  
  
1.  <span data-ttu-id="6e3f2-112">Erstellen und speichern Sie eine Textdatei mit dem Namen **rowdelimiteddata.txt**, die die folgenden Quelldaten enthält:</span><span class="sxs-lookup"><span data-stu-id="6e3f2-112">Create and save a text file named **rowdelimiteddata.txt** that contains the following source data:</span></span>  
  
    ```  
    FirstName: Nancy  
    LastName: Davolio  
    Title: Sales Representative  
    City: Seattle  
    StateProvince: WA  
  
    FirstName: Andrew  
    LastName: Fuller  
    Title: Vice President, Sales  
    City: Tacoma  
    StateProvince: WA  
  
    FirstName: Steven  
    LastName: Buchanan  
    Title: Sales Manager  
    City: London  
    StateProvince:  
  
    ```  
  
2.  <span data-ttu-id="6e3f2-113">Öffnen Sie [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] , und stellen Sie eine Verbindung zu einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="6e3f2-113">Open [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
3.  <span data-ttu-id="6e3f2-114">Wählen Sie eine Zieldatenbank aus, und öffnen Sie ein neues Abfragefenster.</span><span class="sxs-lookup"><span data-stu-id="6e3f2-114">Select a destination database, and open a new query window.</span></span> <span data-ttu-id="6e3f2-115">Führen Sie im Abfragefenster das folgende Skript aus, um die Zieltabelle zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="6e3f2-115">In the query window, execute the following script to create the destination table:</span></span>  
  
    ```  
    create table RowDelimitedData  
    (  
    FirstName varchar(32),  
    LastName varchar(32),  
    Title varchar(32),  
    City varchar(32),  
    StateProvince varchar(32)  
    )  
  
    ```  
  
4.  <span data-ttu-id="6e3f2-116">Öffnen Sie [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], und erstellen Sie ein neues [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Paket mit dem Namen ParseRowDelim.dtsx.</span><span class="sxs-lookup"><span data-stu-id="6e3f2-116">Open [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] and create a new [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package named ParseRowDelim.dtsx.</span></span>  
  
5.  <span data-ttu-id="6e3f2-117">Fügen Sie einen Verbindungs-Manager für Flatfiles zum Paket hinzu, benennen Sie ihn RowDelimitedData und konfigurieren Sie ihn, um eine Verbindung mit der Datei rowdelimiteddata.txt, die Sie in einem vorherigen Schritt erstellt haben, herzustellen.</span><span class="sxs-lookup"><span data-stu-id="6e3f2-117">Add a Flat File connection manager to the package, name it RowDelimitedData, and configure it to connect to the rowdelimiteddata.txt file that you created in a previous step.</span></span>  
  
6.  <span data-ttu-id="6e3f2-118">Fügen Sie einen OLE DB-Verbindungsmanager zum Paket hinzu und konfigurieren Sie ihn, um eine Verbindung zu der Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] und zur Datenbank, in der Sie die Zieltabelle erstellt haben, herzustellen.</span><span class="sxs-lookup"><span data-stu-id="6e3f2-118">Add an OLE DB connection manager to the package and configure it to connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and the database in which you created the destination table.</span></span>  
  
7.  <span data-ttu-id="6e3f2-119">Fügen Sie einen Datenflusstask zum Paket hinzu, und klicken Sie auf die Registerkarte **Datenfluss** des SSIS-Designers.</span><span class="sxs-lookup"><span data-stu-id="6e3f2-119">Add a Data Flow task to the package and click the **Data Flow** tab of SSIS Designer.</span></span>  
  
8.  <span data-ttu-id="6e3f2-120">Fügen Sie eine Flatfilequelle zum Datenfluss hinzu und konfigurieren Sie sie, um den RowDelimitedData-Verbindungs-Manager zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="6e3f2-120">Add a Flat File Source to the data flow and configure it to use the RowDelimitedData connection manager.</span></span> <span data-ttu-id="6e3f2-121">Wählen Sie auf der Seite **Spalten** des **Quellen-Editors für Flatfiles** die einzige verfügbare externe Spalte aus.</span><span class="sxs-lookup"><span data-stu-id="6e3f2-121">On the **Columns** page of the **Flat File Source Editor**, select the single available external column.</span></span>  
  
9. <span data-ttu-id="6e3f2-122">Fügen Sie eine Skriptkomponente zum Datenfluss hinzu, und konfigurieren Sie sie als Transformation.</span><span class="sxs-lookup"><span data-stu-id="6e3f2-122">Add a Script Component to the data flow and configure it as a transformation.</span></span> <span data-ttu-id="6e3f2-123">Verbinden Sie die Ausgabe der Flatfilequelle mit der Skriptkomponente.</span><span class="sxs-lookup"><span data-stu-id="6e3f2-123">Connect the output of the Flat File Source to the Script Component.</span></span>  
  
10. <span data-ttu-id="6e3f2-124">Doppelklicken Sie auf die Skriptkomponente, um den **Transformations-Editor für Skripterstellung** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="6e3f2-124">Double-click the Script component to display the **Script Transformation Editor**.</span></span>  
  
11. <span data-ttu-id="6e3f2-125">Wählen Sie auf der Seite **Eingabespalten** des **Transformations-Editors für Skripterstellung** die einzelne verfügbare Eingabespalte.</span><span class="sxs-lookup"><span data-stu-id="6e3f2-125">On the **Input Columns** page of the **Script Transformation Editor**, select the single available input column.</span></span>  
  
12. <span data-ttu-id="6e3f2-126">Wählen Sie auf der Seite **Eingaben und Ausgaben** des **Transformations-Editors für Skript**Erstellung die Option Ausgabe 0 aus, und legen Sie auf keine fest `SynchronousInputID` .</span><span class="sxs-lookup"><span data-stu-id="6e3f2-126">On the **Inputs and Outputs** page of the **Script Transformation Editor**, select Output 0 and set its `SynchronousInputID` to None.</span></span> <span data-ttu-id="6e3f2-127">Erstellen Sie 5 Ausgabespalten, die alle eine Typzeichenfolge [DT_STR] mit einer Länge von 32 aufweisen:</span><span class="sxs-lookup"><span data-stu-id="6e3f2-127">Create 5 output columns, all of type string [DT_STR] with a length of 32:</span></span>  
  
    -   <span data-ttu-id="6e3f2-128">FirstName</span><span class="sxs-lookup"><span data-stu-id="6e3f2-128">FirstName</span></span>  
  
    -   <span data-ttu-id="6e3f2-129">LastName</span><span class="sxs-lookup"><span data-stu-id="6e3f2-129">LastName</span></span>  
  
    -   <span data-ttu-id="6e3f2-130">Titel</span><span class="sxs-lookup"><span data-stu-id="6e3f2-130">Title</span></span>  
  
    -   <span data-ttu-id="6e3f2-131">City</span><span class="sxs-lookup"><span data-stu-id="6e3f2-131">City</span></span>  
  
    -   <span data-ttu-id="6e3f2-132">StateProvince</span><span class="sxs-lookup"><span data-stu-id="6e3f2-132">StateProvince</span></span>  
  
13. <span data-ttu-id="6e3f2-133">Klicken Sie im **Transformations-Editor für Skript**Erstellung auf der Seite **Skript** auf **Skript bearbeiten** , und geben Sie den Code ein, der in der- `ScriptMain` Klasse des Beispiels angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="6e3f2-133">On the **Script** page of the **Script Transformation Editor**, click **Edit Script** and enter the code shown in the `ScriptMain` class of the example.</span></span> <span data-ttu-id="6e3f2-134">Schließen Sie die Skriptentwicklungsumgebung und den **Transformations-Editor für Skripterstellung**.</span><span class="sxs-lookup"><span data-stu-id="6e3f2-134">Close the script development environment and the **Script Transformation Editor**.</span></span>  
  
14. <span data-ttu-id="6e3f2-135">Fügen Sie zum Datenfluss ein SQL Server-Ziel hinzu.</span><span class="sxs-lookup"><span data-stu-id="6e3f2-135">Add a SQL Server Destination to the data flow.</span></span> <span data-ttu-id="6e3f2-136">Konfigurieren Sie es, um den OLE DB-Verbindungs-Manager und die RowDelimitedData-Tabelle zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="6e3f2-136">Configure it to use the OLE DB connection manager and the RowDelimitedData table.</span></span> <span data-ttu-id="6e3f2-137">Verbinden Sie die Ausgabe der Skriptkomponente mit diesem Ziel.</span><span class="sxs-lookup"><span data-stu-id="6e3f2-137">Connect the output of the Script Component to this destination.</span></span>  
  
15. <span data-ttu-id="6e3f2-138">Führen Sie das Paket aus.</span><span class="sxs-lookup"><span data-stu-id="6e3f2-138">Run the package.</span></span> <span data-ttu-id="6e3f2-139">Untersuchen Sie nach der Beendung des Pakets die Datensätze in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Zieltabelle.</span><span class="sxs-lookup"><span data-stu-id="6e3f2-139">After the package has finished, examine the records in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination table.</span></span>  
  
```vb  
Public Overrides Sub Input0_ProcessInputRow(ByVal Row As Input0Buffer)  
  
    Dim columnName As String  
    Dim columnValue As String  
  
    ' Check for an empty row.  
    If Row.Column0.Trim.Length > 0 Then  
        columnName = Row.Column0.Substring(0, Row.Column0.IndexOf(":"))  
        ' Check for an empty value after the colon.  
        If Row.Column0.Substring(Row.Column0.IndexOf(":")).TrimEnd.Length > 1 Then  
            ' Extract the column value from after the colon and space.  
            columnValue = Row.Column0.Substring(Row.Column0.IndexOf(":") + 2)  
            Select Case columnName  
                Case "FirstName"  
                    ' The FirstName value indicates a new record.  
                    Me.Output0Buffer.AddRow()  
                    Me.Output0Buffer.FirstName = columnValue  
                Case "LastName"  
                    Me.Output0Buffer.LastName = columnValue  
                Case "Title"  
                    Me.Output0Buffer.Title = columnValue  
                Case "City"  
                    Me.Output0Buffer.City = columnValue  
                Case "StateProvince"  
                    Me.Output0Buffer.StateProvince = columnValue  
            End Select  
        End If  
    End If  
  
End Sub  
```  
  
```csharp  
public override void Input0_ProcessInputRow(Input0Buffer Row)  
    {  
  
        string columnName;  
        string columnValue;  
  
        // Check for an empty row.  
        if (Row.Column0.Trim().Length > 0)  
        {  
            columnName = Row.Column0.Substring(0, Row.Column0.IndexOf(":"));  
            // Check for an empty value after the colon.  
            if (Row.Column0.Substring(Row.Column0.IndexOf(":")).TrimEnd().Length > 1)  
            // Extract the column value from after the colon and space.  
            {  
                columnValue = Row.Column0.Substring(Row.Column0.IndexOf(":") + 2);  
                switch (columnName)  
                {  
                    case "FirstName":  
                        // The FirstName value indicates a new record.  
                        this.Output0Buffer.AddRow();  
                        this.Output0Buffer.FirstName = columnValue;  
                        break;  
                    case "LastName":  
                        this.Output0Buffer.LastName = columnValue;  
                        break;  
                    case "Title":  
                        this.Output0Buffer.Title = columnValue;  
                        break;  
                    case "City":  
                        this.Output0Buffer.City = columnValue;  
                        break;  
                    case "StateProvince":  
                        this.Output0Buffer.StateProvince = columnValue;  
                        break;  
                }  
            }  
        }  
  
    }  
```  
  
##  <a name="example-2-splitting-parent-and-child-records"></a><a name="example2"></a> <span data-ttu-id="6e3f2-140">Beispiel 2: Teilen von übergeordneten und untergeordneten Datensätzen</span><span class="sxs-lookup"><span data-stu-id="6e3f2-140">Example 2: Splitting Parent and Child Records</span></span>  
 <span data-ttu-id="6e3f2-141">In diesem Beispiel wird gezeigt, wie eine Textdatei, in der eine Trennzeichenzeile einer übergeordneten Datenzeile vorausgeht, auf die eine endlose Anzahl an untergeordneten Datenzeilen folgt, mithilfe der Skriptkomponente in ordnungsgemäß normalisierte übergeordnete und untergeordnete Zieltabellen konvertiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="6e3f2-141">This example shows how to take a text file, in which a separator row precedes a parent record row that is followed by an indefinite number of child record rows, and parse it into properly normalized parent and child destination tables by using the Script component.</span></span> <span data-ttu-id="6e3f2-142">Dieses einfache Beispiel kann in abgewandelter Form problemlos auf Quelldateien angewendet werden, die mehr als eine Zeile oder Spalte für jeden über- und untergeordneten Datensatz verwenden, vorausgesetzt, der Anfang und das Ende jedes Datensatzes kann bestimmt werden.</span><span class="sxs-lookup"><span data-stu-id="6e3f2-142">This simple example could easily be adapted for source files that use more than one row or column for each parent and child record, as long as there is some way to identify the beginning and end of each record.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="6e3f2-143">Dieses Beispiel dient nur Demonstrationszwecken.</span><span class="sxs-lookup"><span data-stu-id="6e3f2-143">This sample is intended for demonstration purposes only.</span></span> <span data-ttu-id="6e3f2-144">Wenn Sie das Beispiel mehr als einmal ausführen, fügt es doppelte Schlüsselwerte in die Zieltabelle ein.</span><span class="sxs-lookup"><span data-stu-id="6e3f2-144">If you run the sample more than once, it inserts duplicate key values into the destination table.</span></span>  
  
 <span data-ttu-id="6e3f2-145">Weitere Informationen zum Konfigurieren der Skript Komponente für die Verwendung als Transformation im Datenfluss finden Sie unter [Erstellen einer synchronen Transformation mit der Skript Komponente](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md)und [Erstellen einer asynchronen Transformation mit der Skript Komponente](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="6e3f2-145">For more information about how to configure the Script component for use as a transformation in the data flow, see [Creating a Synchronous Transformation with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md)and [Creating an Asynchronous Transformation with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md).</span></span>  
  
#### <a name="to-configure-this-script-component-example"></a><span data-ttu-id="6e3f2-146">So konfigurieren Sie dieses Skriptkomponentenbeispiel</span><span class="sxs-lookup"><span data-stu-id="6e3f2-146">To configure this Script Component example</span></span>  
  
1.  <span data-ttu-id="6e3f2-147">Erstellen und speichern Sie eine Textdatei mit dem Namen **parentchilddata.txt**, die die folgenden Quelldaten enthält:</span><span class="sxs-lookup"><span data-stu-id="6e3f2-147">Create and save a text file named **parentchilddata.txt** that contains the following source data:</span></span>  
  
    ```  
    **********  
    PARENT 1 DATA  
    child 1 data  
    child 2 data  
    child 3 data  
    child 4 data  
    **********  
    PARENT 2 DATA  
    child 5 data  
    child 6 data  
    child 7 data  
    child 8 data  
    **********  
  
    ```  
  
2.  <span data-ttu-id="6e3f2-148">Öffnen Sie [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , und stellen Sie eine Verbindung zu einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="6e3f2-148">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
3.  <span data-ttu-id="6e3f2-149">Wählen Sie eine Zieldatenbank aus, und öffnen Sie ein neues Abfragefenster.</span><span class="sxs-lookup"><span data-stu-id="6e3f2-149">Select a destination database, and open a new query window.</span></span> <span data-ttu-id="6e3f2-150">Führen Sie im Abfragefenster das folgende Skript aus, um die Zieltabellen zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="6e3f2-150">In the query window, execute the following script to create the destination tables:</span></span>  
  
    ```  
    CREATE TABLE [dbo].[Parents]([ParentID] [int] NOT NULL,  
    [ParentRecord] [varchar](32) NOT NULL,  
     CONSTRAINT [PK_Parents] PRIMARY KEY CLUSTERED   
    ([ParentID] ASC))  
    GO  
    CREATE TABLE [dbo].[Children]([ChildID] [int] NOT NULL,  
    [ParentID] [int] NOT NULL,  
    [ChildRecord] [varchar](32) NOT NULL,  
     CONSTRAINT [PK_Children] PRIMARY KEY CLUSTERED   
    ([ChildID] ASC))  
    GO  
    ALTER TABLE [dbo].[Children] ADD CONSTRAINT [FK_Children_Parents] FOREIGN KEY([ParentID])  
    REFERENCES [dbo].[Parents] ([ParentID])  
  
    ```  
  
4.  <span data-ttu-id="6e3f2-151">Öffnen Sie [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], und erstellen Sie ein neues [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Paket mit dem Namen SplitParentChild.dtsx.</span><span class="sxs-lookup"><span data-stu-id="6e3f2-151">Open [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] and create a new [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package named SplitParentChild.dtsx.</span></span>  
  
5.  <span data-ttu-id="6e3f2-152">Fügen Sie einen Verbindungs-Manager für Flatfiles zum Paket hinzu, benennen Sie ihn ParentChildData und konfigurieren Sie ihn, um eine Verbindung mit der Datei parentchilddata.txt file, die Sie in einem vorherigen Schritt erstellt haben, herzustellen.</span><span class="sxs-lookup"><span data-stu-id="6e3f2-152">Add a Flat File connection manager to the package, name it ParentChildData, and configure it to connect to the parentchilddata.txt file that you created in a previous step.</span></span>  
  
6.  <span data-ttu-id="6e3f2-153">Fügen Sie einen OLE DB-Verbindungsmanager zum Paket hinzu und konfigurieren Sie ihn, um ihn zu der Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] und zur Datenbank, in der Sie die Zieltabellen erstellt haben, hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="6e3f2-153">Add an OLE DB connection manager to the package and configure it to connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and the database in which you created the destination tables.</span></span>  
  
7.  <span data-ttu-id="6e3f2-154">Fügen Sie einen Datenflusstask zum Paket hinzu, und klicken Sie auf die Registerkarte **Datenfluss** des SSIS-Designers.</span><span class="sxs-lookup"><span data-stu-id="6e3f2-154">Add a Data Flow task to the package and click the **Data Flow** tab of SSIS Designer.</span></span>  
  
8.  <span data-ttu-id="6e3f2-155">Fügen Sie eine Flatfilequelle zum Datenfluss hinzu und konfigurieren Sie sie, um den ParentChildData-Verbindungs-Manager zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="6e3f2-155">Add a Flat File Source to the data flow and configure it to use the ParentChildData connection manager.</span></span> <span data-ttu-id="6e3f2-156">Wählen Sie auf der Seite **Spalten** des **Quellen-Editors für Flatfiles** die einzige verfügbare externe Spalte aus.</span><span class="sxs-lookup"><span data-stu-id="6e3f2-156">On the **Columns** page of the **Flat File Source Editor**, select the single available external column.</span></span>  
  
9. <span data-ttu-id="6e3f2-157">Fügen Sie eine Skriptkomponente zum Datenfluss hinzu, und konfigurieren Sie sie als Transformation.</span><span class="sxs-lookup"><span data-stu-id="6e3f2-157">Add a Script Component to the data flow and configure it as a transformation.</span></span> <span data-ttu-id="6e3f2-158">Verbinden Sie die Ausgabe der Flatfilequelle mit der Skriptkomponente.</span><span class="sxs-lookup"><span data-stu-id="6e3f2-158">Connect the output of the Flat File Source to the Script Component.</span></span>  
  
10. <span data-ttu-id="6e3f2-159">Doppelklicken Sie auf die Skriptkomponente, um den **Transformations-Editor für Skripterstellung** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="6e3f2-159">Double-click the Script component to display the **Script Transformation Editor**.</span></span>  
  
11. <span data-ttu-id="6e3f2-160">Wählen Sie auf der Seite **Eingabespalten** des **Transformations-Editors für Skripterstellung** die einzelne verfügbare Eingabespalte.</span><span class="sxs-lookup"><span data-stu-id="6e3f2-160">On the **Input Columns** page of the **Script Transformation Editor**, select the single available input column.</span></span>  
  
12. <span data-ttu-id="6e3f2-161">Wählen Sie auf der Seite **Eingaben und Ausgaben** des **Transformations-Editors für Skript**Erstellung die Option Ausgabe 0 aus, benennen Sie Sie in "Datensätze" um, und legen Sie Sie `SynchronousInputID` auf keine fest.</span><span class="sxs-lookup"><span data-stu-id="6e3f2-161">On the **Inputs and Outputs** page of the **Script Transformation Editor**, select Output 0, rename it to ParentRecords, and set its `SynchronousInputID` to None.</span></span> <span data-ttu-id="6e3f2-162">Erstellen Sie 2 Ausgabespalten:</span><span class="sxs-lookup"><span data-stu-id="6e3f2-162">Create 2 output columns:</span></span>  
  
    -   <span data-ttu-id="6e3f2-163">ParentID (der Primärschlüssel) vom Typ 4-Byte-Ganzzahl mit Vorzeichen [DT_I4]</span><span class="sxs-lookup"><span data-stu-id="6e3f2-163">ParentID (the primary key), of type four-byte signed integer [DT_I4]</span></span>  
  
    -   <span data-ttu-id="6e3f2-164">ParentRecord vom Typ String [DT_STR] mit einer Länge von 32.</span><span class="sxs-lookup"><span data-stu-id="6e3f2-164">ParentRecord, of type string [DT_STR] with a length of 32.</span></span>  
  
13. <span data-ttu-id="6e3f2-165">Erstellen Sie eine zweite Ausgabe, und nennen Sie sie ChildRecords.</span><span class="sxs-lookup"><span data-stu-id="6e3f2-165">Create a second output and name it ChildRecords.</span></span> <span data-ttu-id="6e3f2-166">`SynchronousInputID` der neuen Ausgabe ist bereits auf Keine festgelegt.</span><span class="sxs-lookup"><span data-stu-id="6e3f2-166">The `SynchronousInputID` of the new output is already set to None.</span></span> <span data-ttu-id="6e3f2-167">Erstellen Sie 3 Ausgabespalten:</span><span class="sxs-lookup"><span data-stu-id="6e3f2-167">Create 3 output columns:</span></span>  
  
    -   <span data-ttu-id="6e3f2-168">ChildID (der Primärschlüssel) vom Typ 4-Byte-Ganzzahl mit Vorzeichen [DT_I4]</span><span class="sxs-lookup"><span data-stu-id="6e3f2-168">ChildID (the primary key), of type four-byte signed integer [DT_I4]</span></span>  
  
    -   <span data-ttu-id="6e3f2-169">ParentID (der Fremdschlüssel), ebenfalls vom Typ 4-Byte-Ganzzahl mit Vorzeichen [DT_I4]</span><span class="sxs-lookup"><span data-stu-id="6e3f2-169">ParentID (the foreign key), also of type four-byte signed integer [DT_I4]</span></span>  
  
    -   <span data-ttu-id="6e3f2-170">ChildRecord vom Typ String [DT_STR] mit einer Länge von 50.</span><span class="sxs-lookup"><span data-stu-id="6e3f2-170">ChildRecord, of type string [DT_STR] with a length of 50</span></span>  
  
14. <span data-ttu-id="6e3f2-171">Klicken Sie im **Transformations-Editor für Skripterstellung** auf der Seite **Skript** auf **Skript bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="6e3f2-171">On the **Script** page of the **Script Transformation Editor**, click **Edit Script**.</span></span> <span data-ttu-id="6e3f2-172">Geben Sie in der `ScriptMain`-Klasse den im Beispiel gezeigten Code ein.</span><span class="sxs-lookup"><span data-stu-id="6e3f2-172">In the `ScriptMain` class, enter the code shown in the example.</span></span> <span data-ttu-id="6e3f2-173">Schließen Sie die Skriptentwicklungsumgebung und den **Transformations-Editor für Skripterstellung**.</span><span class="sxs-lookup"><span data-stu-id="6e3f2-173">Close the script development environment and the **Script Transformation Editor**.</span></span>  
  
15. <span data-ttu-id="6e3f2-174">Fügen Sie zum Datenfluss ein SQL Server-Ziel hinzu.</span><span class="sxs-lookup"><span data-stu-id="6e3f2-174">Add a SQL Server Destination to the data flow.</span></span> <span data-ttu-id="6e3f2-175">Verbinden Sie den ParentRecords-Ausgang der Skriptkomponente mit diesem Ziel. Konfigurieren Sie den OLE DB-Verbindungs-Manager und die übergeordnete Tabelle.</span><span class="sxs-lookup"><span data-stu-id="6e3f2-175">Connect the ParentRecords output of the Script Component to this destination.Configure it to use the OLE DB connection manager and the Parents table.</span></span>  
  
16. <span data-ttu-id="6e3f2-176">Fügen Sie zum Datenfluss ein weiteres SQL Server-Ziel hinzu.</span><span class="sxs-lookup"><span data-stu-id="6e3f2-176">Add another SQL Server Destination to the data flow.</span></span> <span data-ttu-id="6e3f2-177">Verbinden Sie die ChildRecords-Ausgabe der Skriptkomponente mit diesem Ziel.</span><span class="sxs-lookup"><span data-stu-id="6e3f2-177">Connect the ChildRecords output of the Script Component to this destination.</span></span> <span data-ttu-id="6e3f2-178">Konfigurieren Sie es, um den OLE DB-Verbindungs-Manager und die Children-Tabelle zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="6e3f2-178">Configure it to use the OLE DB connection manager and the Children table.</span></span>  
  
17. <span data-ttu-id="6e3f2-179">Führen Sie das Paket aus.</span><span class="sxs-lookup"><span data-stu-id="6e3f2-179">Run the package.</span></span> <span data-ttu-id="6e3f2-180">Untersuchen Sie nach der Beendung des Pakets die übergeordneten und untergeordneten Datensätze in den beiden [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Zieltabellen.</span><span class="sxs-lookup"><span data-stu-id="6e3f2-180">After the package has finished, examine the parent and child records in the two [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination tables.</span></span>  
  
```vb  
Public Overrides Sub Input0_ProcessInputRow(ByVal Row As Input0Buffer)  
  
    Static nextRowIsParent As Boolean = False  
    Static parentCounter As Integer = 0  
    Static childCounter As Integer = 0  
  
    ' If current row starts with separator characters,  
    '  then following row contains new parent record.  
    If Row.Column0.StartsWith("***") Then  
        nextRowIsParent = True  
    Else  
        If nextRowIsParent Then  
            ' Current row contains parent record.  
            parentCounter += 1  
            Me.ParentRecordsBuffer.AddRow()  
            Me.ParentRecordsBuffer.ParentID = parentCounter  
            Me.ParentRecordsBuffer.ParentRecord = Row.Column0  
            nextRowIsParent = False  
        Else  
            ' Current row contains child record.  
            childCounter += 1  
            Me.ChildRecordsBuffer.AddRow()  
            Me.ChildRecordsBuffer.ChildID = childCounter  
            Me.ChildRecordsBuffer.ParentID = parentCounter  
            Me.ChildRecordsBuffer.ChildRecord = Row.Column0  
        End If  
    End If  
  
End Sub  
```  
  
```csharp  
public override void Input0_ProcessInputRow(Input0Buffer Row)  
    {  
  
    int static_Input0_ProcessInputRow_childCounter = 0;  
    int static_Input0_ProcessInputRow_parentCounter = 0;  
    bool static_Input0_ProcessInputRow_nextRowIsParent = false;  
  
        // If current row starts with separator characters,   
        // then following row contains new parent record.   
        if (Row.Column0.StartsWith("***"))  
        {  
            static_Input0_ProcessInputRow_nextRowIsParent = true;  
        }  
        else  
        {  
            if (static_Input0_ProcessInputRow_nextRowIsParent)  
            {  
                // Current row contains parent record.   
                static_Input0_ProcessInputRow_parentCounter += 1;  
                this.ParentRecordsBuffer.AddRow();  
                this.ParentRecordsBuffer.ParentID = static_Input0_ProcessInputRow_parentCounter;  
                this.ParentRecordsBuffer.ParentRecord = Row.Column0;  
                static_Input0_ProcessInputRow_nextRowIsParent = false;  
            }  
            else  
            {  
                // Current row contains child record.   
                static_Input0_ProcessInputRow_childCounter += 1;  
                this.ChildRecordsBuffer.AddRow();  
                this.ChildRecordsBuffer.ChildID = static_Input0_ProcessInputRow_childCounter;  
                this.ChildRecordsBuffer.ParentID = static_Input0_ProcessInputRow_parentCounter;  
                this.ChildRecordsBuffer.ChildRecord = Row.Column0;  
            }  
        }  
  
    }  
```  
  
<span data-ttu-id="6e3f2-181">![Integration Services Symbol (klein)](../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="6e3f2-181">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="6e3f2-182">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="6e3f2-182">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="6e3f2-183">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="6e3f2-183">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="6e3f2-184">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="6e3f2-184">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e3f2-185">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6e3f2-185">See Also</span></span>  
 [<span data-ttu-id="6e3f2-186">Erstellen einer synchronen Transformation mit der Skriptkomponente</span><span class="sxs-lookup"><span data-stu-id="6e3f2-186">Creating a Synchronous Transformation with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md)  
 [<span data-ttu-id="6e3f2-187">Erstellen einer asynchronen Transformation mit der Skriptkomponente</span><span class="sxs-lookup"><span data-stu-id="6e3f2-187">Creating an Asynchronous Transformation with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md)  
  
  
