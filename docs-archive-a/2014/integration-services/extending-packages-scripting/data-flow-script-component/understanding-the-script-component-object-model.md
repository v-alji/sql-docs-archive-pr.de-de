---
title: Grundlegendes zum Skript-Komponentenobjektmodell | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script component [Integration Services], object model
ms.assetid: 2a0aae82-39cc-4423-b09a-72d2f61033bd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a11556b00efc5749e8ddb895712d6c61f2459d8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617191"
---
# <a name="understanding-the-script-component-object-model"></a><span data-ttu-id="dd376-102">Grundlegendes zum Skript-Komponentenobjektmodell</span><span class="sxs-lookup"><span data-stu-id="dd376-102">Understanding the Script Component Object Model</span></span>
  <span data-ttu-id="dd376-103">Wie unter [codieren und Debuggen der Skript Komponente] beschrieben (.. /Extending-Packages-Scripting/Data-Flow-Script-Component/Coding-and-Debugging-the-Script-Component.MD, das Skript Komponenten Projekt enthält drei Projekt Elemente:</span><span class="sxs-lookup"><span data-stu-id="dd376-103">As discussed in [Coding and Debugging the Script Component](../extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md, the Script component project contains three project items:</span></span>

1.  <span data-ttu-id="dd376-104">Das `ScriptMain`-Element, das die `ScriptMain`-Klasse enthält, in die Sie den Code schreiben.</span><span class="sxs-lookup"><span data-stu-id="dd376-104">The `ScriptMain` item, which contains the `ScriptMain` class in which you write your code.</span></span> <span data-ttu-id="dd376-105">Die `ScriptMain`-Klasse erbt von der `UserComponent`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="dd376-105">The `ScriptMain` class inherits from the `UserComponent` class.</span></span>

2.  <span data-ttu-id="dd376-106">Das `ComponentWrapper`-Element, das die `UserComponent`-Klasse enthält, eine Instanz von <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent>, die die Methoden und Eigenschaften enthält, die Sie verwenden, um Daten zu verarbeiten und mit dem Paket zu interagieren.</span><span class="sxs-lookup"><span data-stu-id="dd376-106">The `ComponentWrapper` item, which contains the `UserComponent` class, an instance of <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> that contains the methods and properties that you will use to process data and to interact with the package.</span></span> <span data-ttu-id="dd376-107">Das `ComponentWrapper`-Element enthält auch `Connections`- und `Variables`-Auflistungsklassen.</span><span class="sxs-lookup"><span data-stu-id="dd376-107">The `ComponentWrapper` item also contains `Connections` and `Variables` collection classes.</span></span>

3.  <span data-ttu-id="dd376-108">Das `BufferWrapper`-Element, das Klassen enthält, das von <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer> für jede Eingabe und Ausgabe und typisierte Eigenschaften für jede Spalte erbt.</span><span class="sxs-lookup"><span data-stu-id="dd376-108">The `BufferWrapper` item, which contains classes that inherits from <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer> for each input and output, and typed properties for each column.</span></span>

 <span data-ttu-id="dd376-109">Beim Schreiben des Codes in das `ScriptMain`-Element verwenden Sie die in diesem Thema besprochenen Objekte, Methoden und Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="dd376-109">As you write your code in the `ScriptMain` item, you will use the objects, methods, and properties discussed in this topic.</span></span> <span data-ttu-id="dd376-110">Es werden nicht von jeder Komponente alle hier aufgeführten Methoden verwendet. Wenn sie jedoch verwendet werden, geschieht dies in der gezeigten Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="dd376-110">Each component will not use all the methods listed here; however, when used, they are used in the sequence shown.</span></span>

 <span data-ttu-id="dd376-111">Die <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent>-Basisklasse enthält keinen Implementierungscode für die in diesem Thema erläuterten Methoden.</span><span class="sxs-lookup"><span data-stu-id="dd376-111">The <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> base class does not contain any implementation code for the methods discussed in this topic.</span></span> <span data-ttu-id="dd376-112">Es ist daher unnötig, aber ungefährlich, Ihrer eigenen Implementierung der Methode einen Aufruf der Basisklassenimplementierung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="dd376-112">Therefore it is unnecessary, but harmless, to add a call to the base class implementation to your own implementation of the method.</span></span>

 <span data-ttu-id="dd376-113">Informationen darüber, wie die Methoden und Eigenschaften dieser Klassen in einem bestimmten Skriptkomponententyp zu verwenden sind, finden Sie unter [Additional Script Component Examples (Zusätzliche Skriptkomponentenbeispiele)](../../extending-packages-scripting-data-flow-script-component-examples/additional-script-component-examples.md).</span><span class="sxs-lookup"><span data-stu-id="dd376-113">For information about how to use the methods and properties of these classes in a particular type of Script component, see the section [Additional Script Component Examples](../../extending-packages-scripting-data-flow-script-component-examples/additional-script-component-examples.md).</span></span> <span data-ttu-id="dd376-114">Die Beispielthemen enthalten auch vollständige Codebeispiele.</span><span class="sxs-lookup"><span data-stu-id="dd376-114">The example topics also contain complete code samples.</span></span>

## <a name="acquireconnections-method"></a><span data-ttu-id="dd376-115">‚AcquireConnections’-Methode</span><span class="sxs-lookup"><span data-stu-id="dd376-115">AcquireConnections Method</span></span>
 <span data-ttu-id="dd376-116">Quellen und Ziele müssen im Allgemeinen eine Verbindung mit einer externen Datenquelle herstellen.</span><span class="sxs-lookup"><span data-stu-id="dd376-116">Sources and destinations generally must connect to an external data source.</span></span> <span data-ttu-id="dd376-117">Überschreiben Sie die <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.AcquireConnections%2A>-Methode der <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent>-Basisklasse, um die Verbindung oder die Verbindungsinformationen von dem entsprechenden Verbindungs-Manager abzurufen.</span><span class="sxs-lookup"><span data-stu-id="dd376-117">Override the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.AcquireConnections%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> base class to retrieve the connection or the connection information from the appropriate connection manager.</span></span>

 <span data-ttu-id="dd376-118">Im folgenden Beispiel wird `System.Data.SqlClient.SqlConnection` von einem ADO.NET-Verbindungs-Manager zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="dd376-118">The following example returns a `System.Data.SqlClient.SqlConnection` from an ADO.NET connection manager.</span></span>

```vb
Dim connMgr As IDTSConnectionManager100
Dim sqlConn As SqlConnection

Public Overrides Sub AcquireConnections(ByVal Transaction As Object)

    connMgr = Me.Connections.MyADONETConnection
    sqlConn = CType(connMgr.AcquireConnection(Nothing), SqlConnection)

End Sub
```

 <span data-ttu-id="dd376-119">Das folgende Beispiel gibt einen vollständigen Pfad- und Dateinamen von einem Verbindungs-Manager für Flatfiles zurück und öffnet anschließend die Datei mithilfe von `System.IO.StreamReader`.</span><span class="sxs-lookup"><span data-stu-id="dd376-119">The following example returns a complete path and file name from a Flat File Connection Manager, and then opens the file by using a `System.IO.StreamReader`.</span></span>

```vb
Private textReader As StreamReader
Public Overrides Sub AcquireConnections(ByVal Transaction As Object)

    Dim connMgr As IDTSConnectionManager100 = _
        Me.Connections.MyFlatFileSrcConnectionManager
    Dim exportedAddressFile As String = _
        CType(connMgr.AcquireConnection(Nothing), String)
    textReader = New StreamReader(exportedAddressFile)

End Sub
```

## <a name="preexecute-method"></a><span data-ttu-id="dd376-120">‚PreExecute’-Methode</span><span class="sxs-lookup"><span data-stu-id="dd376-120">PreExecute Method</span></span>
 <span data-ttu-id="dd376-121">Überschreiben Sie die <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.PreExecute%2A>-Methode der <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent>-Basisklasse immer dann, wenn Sie eine Verarbeitung nur einmal durchführen müssen, bevor Sie die Verarbeitung einer Datenzeile starten.</span><span class="sxs-lookup"><span data-stu-id="dd376-121">Override the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.PreExecute%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> base class whenever you have processing that you must perform one time only before you start processing rows of data.</span></span> <span data-ttu-id="dd376-122">In einem Ziel können Sie beispielsweise den parametrisierten Befehl, den das Ziel verwendet, so konfigurieren, dass jede Datenzeile in die Datenquelle eingefügt wird.</span><span class="sxs-lookup"><span data-stu-id="dd376-122">For example, in a destination, you may want to configure the parameterized command that the destination will use to insert each row of data into the data source.</span></span>

```vb
    Dim sqlConn As SqlConnection
    Dim sqlCmd As SqlCommand
    Dim sqlParam As SqlParameter
...
    Public Overrides Sub PreExecute()

        sqlCmd = New SqlCommand("INSERT INTO Person.Address2(AddressID, City) " & _
            "VALUES(@addressid, @city)", sqlConn)
        sqlParam = New SqlParameter("@addressid", SqlDbType.Int)
        sqlCmd.Parameters.Add(sqlParam)
        sqlParam = New SqlParameter("@city", SqlDbType.NVarChar, 30)
        sqlCmd.Parameters.Add(sqlParam)

    End Sub
```

```csharp
SqlConnection sqlConn; 
SqlCommand sqlCmd; 
SqlParameter sqlParam; 

public override void PreExecute() 
{ 

    sqlCmd = new SqlCommand("INSERT INTO Person.Address2(AddressID, City) " + "VALUES(@addressid, @city)", sqlConn); 
    sqlParam = new SqlParameter("@addressid", SqlDbType.Int); 
    sqlCmd.Parameters.Add(sqlParam); 
    sqlParam = new SqlParameter("@city", SqlDbType.NVarChar, 30); 
    sqlCmd.Parameters.Add(sqlParam); 

}
```

## <a name="processing-inputs-and-outputs"></a><span data-ttu-id="dd376-123">Verarbeiten von Eingaben und Ausgaben</span><span class="sxs-lookup"><span data-stu-id="dd376-123">Processing Inputs and Outputs</span></span>

### <a name="processing-inputs"></a><span data-ttu-id="dd376-124">Verarbeiten von Eingaben</span><span class="sxs-lookup"><span data-stu-id="dd376-124">Processing Inputs</span></span>
 <span data-ttu-id="dd376-125">Skriptkomponenten, die als Transformationen oder Ziele konfiguriert sind, weisen eine Eingabe auf.</span><span class="sxs-lookup"><span data-stu-id="dd376-125">Script components that are configured as transformations or destinations have one input.</span></span>

#### <a name="what-the-bufferwrapper-project-item-provides"></a><span data-ttu-id="dd376-126">Bereitstellungen durch das ‚BufferWrapper’-Projektelement</span><span class="sxs-lookup"><span data-stu-id="dd376-126">What the BufferWrapper Project Item Provides</span></span>
 <span data-ttu-id="dd376-127">Für jede von Ihnen konfigurierte Eingabe enthält das `BufferWrapper`-Projektelement eine Klasse, die von <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer> abgeleitet ist und denselben Namen hat wie die Eingabe.</span><span class="sxs-lookup"><span data-stu-id="dd376-127">For each input that you have configured, the `BufferWrapper` project item contains a class that derives from <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer> and has the same name as the input.</span></span> <span data-ttu-id="dd376-128">Jede Eingabepufferklasse enthält die folgenden Eigenschaften, Funktionen und Methoden:</span><span class="sxs-lookup"><span data-stu-id="dd376-128">Each input buffer class contains the following properties, functions, and methods:</span></span>

-   <span data-ttu-id="dd376-129">Benannte, typisierte Accessoreigenschaften für jede ausgewählte Eingabespalte.</span><span class="sxs-lookup"><span data-stu-id="dd376-129">Named, typed accessor properties for each selected input column.</span></span> <span data-ttu-id="dd376-130">Diese Eigenschaften sind schreibgeschützt oder weisen Lese-/Schreibzugriff auf, abhängig von dem für die Spalte auf der Seite **Eingabespalten** des Dialogfelds **Transformations-Editor für Skripterstellung** angegebenen **Verwendungstyp**.</span><span class="sxs-lookup"><span data-stu-id="dd376-130">These properties are read-only or read/write depending on the **Usage Type** specified for the column on the **Input Columns** page of the **Script Transformation Editor**.</span></span>

-   <span data-ttu-id="dd376-131">Eine **\<column>_IsNull**-Eigenschaft für jede ausgewählte Eingabespalte.</span><span class="sxs-lookup"><span data-stu-id="dd376-131">A **\<column>_IsNull** property for each selected input column.</span></span> <span data-ttu-id="dd376-132">Diese Eigenschaft ist ebenfalls schreibgeschützt oder weist Lese-/Schreibzugriff auf, abhängig von dem für die Spalte angegebenen **Verwendungstyp**.</span><span class="sxs-lookup"><span data-stu-id="dd376-132">This property is also read-only or read/write depending on the **Usage Type** specified for the column.</span></span>

-   <span data-ttu-id="dd376-133">Eine **DirectRowTo\<outputbuffer>** -Methode für jede konfigurierte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="dd376-133">A **DirectRowTo\<outputbuffer>** method for each configured output.</span></span> <span data-ttu-id="dd376-134">Sie verwenden diese Methoden beim Filtern von Zeilen in eine von mehreren Ausgaben in derselben `ExclusionGroup`.</span><span class="sxs-lookup"><span data-stu-id="dd376-134">You will use these methods when filtering rows to one of several outputs in the same `ExclusionGroup`.</span></span>

-   <span data-ttu-id="dd376-135">Eine `NextRow`-Funktion, um die nächste Eingabezeile abzurufen, und eine `EndOfRowset`-Funktion, um zu bestimmen, ob der letzte Datenpuffer verarbeitet wurde.</span><span class="sxs-lookup"><span data-stu-id="dd376-135">A `NextRow` function to get the next input row, and an `EndOfRowset` function to determine whether the last buffer of data has been processed.</span></span> <span data-ttu-id="dd376-136">Normalerweise benötigen Sie diese Funktionen nicht, wenn Sie die in der `UserComponent`-Basisklasse implementierten Eingabeverarbeitungsmethoden verwenden.</span><span class="sxs-lookup"><span data-stu-id="dd376-136">You typically do not need these functions when you use the input processing methods implemented in the `UserComponent` base class.</span></span> <span data-ttu-id="dd376-137">Im nächsten Abschnitt finden Sie weitere Informationen über die `UserComponent`-Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="dd376-137">The next section provides more information about the `UserComponent` base class.</span></span>

#### <a name="what-the-componentwrapper-project-item-provides"></a><span data-ttu-id="dd376-138">Bereitstellungen durch das ‚ComponentWrapper’-Projektelement</span><span class="sxs-lookup"><span data-stu-id="dd376-138">What the ComponentWrapper Project Item Provides</span></span>
 <span data-ttu-id="dd376-139">Das ComponentWrapper-Projektelement enthält eine Klasse mit dem Namen `UserComponent`, die von <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="dd376-139">The ComponentWrapper project item contains a class named `UserComponent` that derives from <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent>.</span></span> <span data-ttu-id="dd376-140">Die `ScriptMain`-Klasse, in die Sie Ihren benutzerdefinierten Code schreiben, wird wiederum von `UserComponent` abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="dd376-140">The `ScriptMain` class in which you write your custom code derives in turn from `UserComponent`.</span></span> <span data-ttu-id="dd376-141">Die `UserComponent`-Klasse enthält die folgenden Methoden:</span><span class="sxs-lookup"><span data-stu-id="dd376-141">The `UserComponent` class contains the following methods:</span></span>

-   <span data-ttu-id="dd376-142">Eine überschriebene Implementierung der `ProcessInput`-Methode.</span><span class="sxs-lookup"><span data-stu-id="dd376-142">An overridden implementation of the `ProcessInput` method.</span></span> <span data-ttu-id="dd376-143">Diese Methode wird von der Datenfluss-Engine zur Laufzeit direkt im Anschluss an die `PreExecute`-Methode (und u. U. mehrfach) aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="dd376-143">This is the method that the data flow engine calls next at run time after the `PreExecute` method, and it may be called multiple times.</span></span> <span data-ttu-id="dd376-144">`ProcessInput`übergibt die Verarbeitung an die \*\* \<inputbuffer> _ProcessInput\*\* -Methode.</span><span class="sxs-lookup"><span data-stu-id="dd376-144">`ProcessInput` hands off processing to the **\<inputbuffer>_ProcessInput** method.</span></span> <span data-ttu-id="dd376-145">Anschließend sucht die `ProcessInput`-Methode nach dem Ende des Eingabepuffers. Wenn das Ende des Puffers erreicht wurde, ruft sie die überschreibbare `FinishOutputs`-Methode und die private `MarkOutputsAsFinished`-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="dd376-145">Then the `ProcessInput` method checks for the end of the input buffer and, if the end of the buffer has been reached, calls the overridable `FinishOutputs` method and the private `MarkOutputsAsFinished` method.</span></span> <span data-ttu-id="dd376-146">Die `MarkOutputsAsFinished`-Methode ruft dann beim letzten Ausgabepuffer `SetEndOfRowset` auf.</span><span class="sxs-lookup"><span data-stu-id="dd376-146">The `MarkOutputsAsFinished` method then calls `SetEndOfRowset` on the last output buffer.</span></span>

-   <span data-ttu-id="dd376-147">Eine überschreibbare Implementierung der **\<inputbuffer>_ProcessInput**-Methode.</span><span class="sxs-lookup"><span data-stu-id="dd376-147">An overridable implementation of the **\<inputbuffer>_ProcessInput** method.</span></span> <span data-ttu-id="dd376-148">Diese Standardimplementierung durchläuft jede Eingabezeile einmal und ruft **\<inputbuffer>_ProcessInputRow** auf.</span><span class="sxs-lookup"><span data-stu-id="dd376-148">This default implementation simply loops through each input row and calls **\<inputbuffer>_ProcessInputRow**.</span></span>

-   <span data-ttu-id="dd376-149">Eine überschreibbare Implementierung der **\<inputbuffer>_ProcessInputRow**-Methode.</span><span class="sxs-lookup"><span data-stu-id="dd376-149">An overridable implementation of the **\<inputbuffer>_ProcessInputRow** method.</span></span> <span data-ttu-id="dd376-150">Der Standardimplementierung ist leer.</span><span class="sxs-lookup"><span data-stu-id="dd376-150">The default implementation is empty.</span></span> <span data-ttu-id="dd376-151">Dies ist die Methode, die Sie normalerweise überschreiben, um den benutzerdefinierten Datenverarbeitungscode zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="dd376-151">This is the method that you will normally override to write your custom data processing code.</span></span>

#### <a name="what-your-custom-code-should-do"></a><span data-ttu-id="dd376-152">Schritte, die der benutzerdefinierte Code ausführen sollte</span><span class="sxs-lookup"><span data-stu-id="dd376-152">What Your Custom Code Should Do</span></span>
 <span data-ttu-id="dd376-153">Sie können mithilfe der folgenden Methoden Eingaben in die `ScriptMain`-Klasse verarbeiten:</span><span class="sxs-lookup"><span data-stu-id="dd376-153">You can use the following methods to process input in the `ScriptMain` class:</span></span>

-   <span data-ttu-id="dd376-154">Überschreiben Sie **\<inputbuffer>_ProcessInputRow**, um die Daten in jeder Eingabezeile beim Durchlaufen zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="dd376-154">Override **\<inputbuffer>_ProcessInputRow** to process the data in each input row as it passes through.</span></span>

-   <span data-ttu-id="dd376-155">Überschreiben Sie **\<inputbuffer>_ProcessInput** nur dann, wenn Sie beim Durchlaufen der Eingabezeilen noch einen anderen Vorgang ausführen müssen.</span><span class="sxs-lookup"><span data-stu-id="dd376-155">Override **\<inputbuffer>_ProcessInput** only if you have to do something additional while looping through input rows.</span></span> <span data-ttu-id="dd376-156">(Sie müssen z. b. testen, um `EndOfRowset` andere Maßnahmen zu ergreifen, nachdem alle Zeilen verarbeitet wurden.) Ruft \*\* \<inputbuffer> _ProcessInputRow\*\* auf, um die Zeilen Verarbeitung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="dd376-156">(For example, you have to test for `EndOfRowset` to take some other action after all rows have been processed.) Call **\<inputbuffer>_ProcessInputRow** to perform the row processing.</span></span>

-   <span data-ttu-id="dd376-157">überschreiben Sie `FinishOutputs`, wenn Sie etwas mit den Ausgaben durchführen müssen, bevor sie geschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="dd376-157">Override `FinishOutputs` if you have to do something to the outputs before they are closed.</span></span>

 <span data-ttu-id="dd376-158">Die `ProcessInput`-Methode stellt sicher, dass diese Methoden zum jeweils richtigen Zeitpunkt aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="dd376-158">The `ProcessInput` method ensures that these methods are called at the appropriate times.</span></span>

### <a name="processing-outputs"></a><span data-ttu-id="dd376-159">Verarbeiten von Ausgaben</span><span class="sxs-lookup"><span data-stu-id="dd376-159">Processing Outputs</span></span>
 <span data-ttu-id="dd376-160">Skriptkomponenten, die als Quellen oder Transformationen konfiguriert sind, weisen mindestens eine Eingabe auf.</span><span class="sxs-lookup"><span data-stu-id="dd376-160">Script components configured as sources or transformations have one or more outputs.</span></span>

#### <a name="what-the-bufferwrapper-project-item-provides"></a><span data-ttu-id="dd376-161">Bereitstellungen durch das ‚BufferWrapper’-Projektelement</span><span class="sxs-lookup"><span data-stu-id="dd376-161">What the BufferWrapper Project Item Provides</span></span>
 <span data-ttu-id="dd376-162">Für jede von Ihnen konfigurierte Ausgabe enthält das BufferWrapper-Projektelement eine Klasse, die von <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer> abgeleitet ist und denselben Namen hat wie die Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="dd376-162">For each output that you have configured, the BufferWrapper project item contains a class that derives from <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer> and has the same name as the output.</span></span> <span data-ttu-id="dd376-163">Jede Eingabepufferklasse enthält die folgenden Eigenschaften und Methoden:</span><span class="sxs-lookup"><span data-stu-id="dd376-163">Each input buffer class contains the following properties and methods:</span></span>

-   <span data-ttu-id="dd376-164">Benannte, typisierte, lesegeschützte Accessoreigenschaften für jede ausgewählte Ausgabespalte.</span><span class="sxs-lookup"><span data-stu-id="dd376-164">Named, typed, write-only accessor properties for each output column.</span></span>

-   <span data-ttu-id="dd376-165">Eine schreibgeschützte \*\* \<column> _IsNull\*\* Eigenschaft für jede ausgewählte Ausgabe Spalte, die Sie verwenden können, um den Spaltenwert auf festzulegen `null` .</span><span class="sxs-lookup"><span data-stu-id="dd376-165">A write-only **\<column>_IsNull** property for each selected output column that you can use to set the column value to `null`.</span></span>

-   <span data-ttu-id="dd376-166">Eine `AddRow`-Methode, um dem Ausgabepuffer eine leere neue Zeile hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="dd376-166">An `AddRow` method to add an empty new row to the output buffer.</span></span>

-   <span data-ttu-id="dd376-167">Eine `SetEndOfRowset`-Methode, um der Datenfluss-Engine mitzuteilen, dass keine weiteren Datenpuffer erwartet werden.</span><span class="sxs-lookup"><span data-stu-id="dd376-167">A `SetEndOfRowset` method to let the data flow engine know that no more buffers of data are expected.</span></span> <span data-ttu-id="dd376-168">Außerdem gibt es eine `EndOfRowset`-Funktion, um zu bestimmen, ob der aktuelle Puffer der letzte Datenpuffer ist.</span><span class="sxs-lookup"><span data-stu-id="dd376-168">There is also an `EndOfRowset` function to determine whether the current buffer is the last buffer of data.</span></span> <span data-ttu-id="dd376-169">Diese Funktionen sind im Allgemeinen nicht erforderlich, wenn Sie die in der Basisklasse implementierten Eingabe Verarbeitungsmethoden verwenden `UserComponent` .</span><span class="sxs-lookup"><span data-stu-id="dd376-169">You generally do not need these functions when you use the input processing methods implemented in the `UserComponent` base class.</span></span>

#### <a name="what-the-componentwrapper-project-item-provides"></a><span data-ttu-id="dd376-170">Bereitstellungen durch das ‚ComponentWrapper’-Projektelement</span><span class="sxs-lookup"><span data-stu-id="dd376-170">What the ComponentWrapper Project Item Provides</span></span>
 <span data-ttu-id="dd376-171">Das ComponentWrapper-Projektelement enthält eine Klasse mit dem Namen `UserComponent`, die von <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="dd376-171">The ComponentWrapper project item contains a class named `UserComponent` that derives from <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent>.</span></span> <span data-ttu-id="dd376-172">Die `ScriptMain`-Klasse, in die Sie Ihren benutzerdefinierten Code schreiben, wird wiederum von `UserComponent` abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="dd376-172">The `ScriptMain` class in which you write your custom code derives in turn from `UserComponent`.</span></span> <span data-ttu-id="dd376-173">Die `UserComponent`-Klasse enthält die folgenden Methoden:</span><span class="sxs-lookup"><span data-stu-id="dd376-173">The `UserComponent` class contains the following methods:</span></span>

-   <span data-ttu-id="dd376-174">Eine überschriebene Implementierung der `PrimeOutput`-Methode.</span><span class="sxs-lookup"><span data-stu-id="dd376-174">An overridden implementation of the `PrimeOutput` method.</span></span> <span data-ttu-id="dd376-175">Diese Methode wird von der Datenfluss-Engine zur Laufzeit vor `ProcessInput` (und nur einmal) aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="dd376-175">The data flow engine calls this method before `ProcessInput` at run time, and it is only called one time.</span></span> <span data-ttu-id="dd376-176">`PrimeOutput` übergibt die Verarbeitung an die `CreateNewOutputRows`-Methode.</span><span class="sxs-lookup"><span data-stu-id="dd376-176">`PrimeOutput` hands off processing to the `CreateNewOutputRows` method.</span></span> <span data-ttu-id="dd376-177">Wenn die Komponente eine Quelle ist (d. h. die Komponente weist keine Eingaben auf), ruft `PrimeOutput` anschließend die überschreibbare `FinishOutputs`-Methode und die private `MarkOutputsAsFinished`-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="dd376-177">Then, if the component is a source (that is, the component has no inputs), `PrimeOutput` calls the overridable `FinishOutputs` method and the private `MarkOutputsAsFinished` method.</span></span> <span data-ttu-id="dd376-178">Die `MarkOutputsAsFinished`-Methode ruft beim letzten Ausgabepuffer `SetEndOfRowset` auf.</span><span class="sxs-lookup"><span data-stu-id="dd376-178">The `MarkOutputsAsFinished` method calls `SetEndOfRowset` on the last output buffer.</span></span>

-   <span data-ttu-id="dd376-179">Eine überschreibbare Implementierung der `CreateNewOutputRows`-Methode.</span><span class="sxs-lookup"><span data-stu-id="dd376-179">An overridable implementation of the `CreateNewOutputRows` method.</span></span> <span data-ttu-id="dd376-180">Der Standardimplementierung ist leer.</span><span class="sxs-lookup"><span data-stu-id="dd376-180">The default implementation is empty.</span></span> <span data-ttu-id="dd376-181">Dies ist die Methode, die Sie normalerweise überschreiben, um den benutzerdefinierten Datenverarbeitungscode zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="dd376-181">This is the method that you will normally override to write your custom data processing code.</span></span>

#### <a name="what-your-custom-code-should-do"></a><span data-ttu-id="dd376-182">Schritte, die der benutzerdefinierte Code ausführen sollte</span><span class="sxs-lookup"><span data-stu-id="dd376-182">What Your Custom Code Should Do</span></span>
 <span data-ttu-id="dd376-183">Sie können mithilfe der folgenden Methoden Ausgaben in der `ScriptMain`-Klasse verarbeiten:</span><span class="sxs-lookup"><span data-stu-id="dd376-183">You can use the following methods to process outputs in the `ScriptMain` class:</span></span>

-   <span data-ttu-id="dd376-184">Überschreiben Sie `CreateNewOutputRows` nur, wenn Sie Ausgabezeilen vor der Verarbeitung der Eingabezeilen hinzufügen und füllen können.</span><span class="sxs-lookup"><span data-stu-id="dd376-184">Override `CreateNewOutputRows` only when you can add and populate output rows before processing input rows.</span></span> <span data-ttu-id="dd376-185">Sie können beispielsweise `CreateNewOutputRows` in einer Quelle verwenden. In einer Transformation mit asynchronen Ausgaben sollten Sie jedoch `AddRow` während oder nach der Verarbeitung der Eingabedaten aufrufen.</span><span class="sxs-lookup"><span data-stu-id="dd376-185">For example, you can use `CreateNewOutputRows` in a source, but in a transformation with asynchronous outputs, you should call `AddRow` during or after the processing of input data.</span></span>

-   <span data-ttu-id="dd376-186">überschreiben Sie `FinishOutputs`, wenn Sie etwas mit den Ausgaben durchführen müssen, bevor sie geschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="dd376-186">Override `FinishOutputs` if you have to do something to the outputs before they are closed.</span></span>

 <span data-ttu-id="dd376-187">Die `PrimeOutput`-Methode stellt sicher, dass diese Methoden zum jeweils richtigen Zeitpunkt aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="dd376-187">The `PrimeOutput` method ensures that these methods are called at the appropriate times.</span></span>

## <a name="postexecute-method"></a><span data-ttu-id="dd376-188">‚PostExecute’-Methode</span><span class="sxs-lookup"><span data-stu-id="dd376-188">PostExecute Method</span></span>
 <span data-ttu-id="dd376-189">Überschreiben Sie die <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.PostExecute%2A>-Methode der <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent>-Basisklasse immer dann, wenn Sie eine Verarbeitung nur einmal durchführen müssen, nachdem Sie die Datenzeilen verarbeitet haben.</span><span class="sxs-lookup"><span data-stu-id="dd376-189">Override the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.PostExecute%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> base class whenever you have processing that you must perform one time only after you have processed the rows of data.</span></span> <span data-ttu-id="dd376-190">In einer Quelle können Sie beispielsweise den von Ihnen zum Laden von Daten in den Datenfluss verwendeten `System.Data.SqlClient.SqlDataReader` schließen.</span><span class="sxs-lookup"><span data-stu-id="dd376-190">For example, in a source, you may want to close the `System.Data.SqlClient.SqlDataReader` that you have used to load data into the data flow.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="dd376-191">Die Auflistung von `ReadWriteVariables` ist nur in der `PostExecute`-Methode verfügbar.</span><span class="sxs-lookup"><span data-stu-id="dd376-191">The collection of `ReadWriteVariables` is available only in the `PostExecute` method.</span></span> <span data-ttu-id="dd376-192">Sie können daher den Wert einer Paketvariablen nicht direkt inkrementieren, während Sie jede Datenzeile verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="dd376-192">Therefore you cannot directly increment the value of a package variable as you process each row of data.</span></span> <span data-ttu-id="dd376-193">Erhöhen Sie stattdessen den Wert einer lokalen Variablen, und legen Sie den Wert der Paket Variablen auf den Wert der lokalen Variablen in der-Methode fest, `PostExecute` nachdem alle Daten verarbeitet wurden.</span><span class="sxs-lookup"><span data-stu-id="dd376-193">Instead, increment the value of a local variable, and set the value of the package variable to the value of the local variable in the `PostExecute` method after all data has been processed.</span></span>

## <a name="releaseconnections-method"></a><span data-ttu-id="dd376-194">‚ReleaseConnections’-Methode</span><span class="sxs-lookup"><span data-stu-id="dd376-194">ReleaseConnections Method</span></span>
 <span data-ttu-id="dd376-195">Quellen und Ziele müssen generell eine Verbindung mit einer externen Datenquelle herstellen.</span><span class="sxs-lookup"><span data-stu-id="dd376-195">Sources and destinations typically must connect to an external data source.</span></span> <span data-ttu-id="dd376-196">Überschreiben Sie die <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ReleaseConnections%2A>-Methode der <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent>-Basisklasse, um die vorher in der <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.AcquireConnections%2A>-Methode geöffnete Verbindung zu schließen und freizugeben.</span><span class="sxs-lookup"><span data-stu-id="dd376-196">Override the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ReleaseConnections%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> base class to close and release the connection that you have opened previously in the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.AcquireConnections%2A> method.</span></span>

```vb
    Dim connMgr As IDTSConnectionManager100
...
    Public Overrides Sub ReleaseConnections()

        connMgr.ReleaseConnection(sqlConn)

    End Sub
```

```csharp
IDTSConnectionManager100 connMgr;

public override void ReleaseConnections()
{

    connMgr.ReleaseConnection(sqlConn);

}
```

<span data-ttu-id="dd376-197">![Integration Services Symbol (klein)](../../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="dd376-197">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="dd376-198">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="dd376-198">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="dd376-199">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="dd376-199">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="dd376-200">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="dd376-200">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="dd376-201">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dd376-201">See Also</span></span>
 <span data-ttu-id="dd376-202">[Konfigurieren der Skript Komponente im Skript Komponenten-Editor](configuring-the-script-component-in-the-script-component-editor.md) [codieren und Debuggen der Skript Komponente] (.. /extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md</span><span class="sxs-lookup"><span data-stu-id="dd376-202">[Configuring the Script Component in the Script Component Editor](configuring-the-script-component-in-the-script-component-editor.md) [Coding and Debugging the Script Component](../extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md</span></span>


