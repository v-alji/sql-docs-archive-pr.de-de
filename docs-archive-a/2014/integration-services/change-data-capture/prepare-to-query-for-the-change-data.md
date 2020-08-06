---
title: Vorbereiten zur Abfrage der Änderungsdaten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- incremental load [Integration Services],preparing query
ms.assetid: 9ea2db7a-3dca-4bbf-9903-cccd2d494b5f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5ab732389d5a747c596472f14f5229361dd46275
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608787"
---
# <a name="prepare-to-query-for-the-change-data"></a><span data-ttu-id="67f49-102">Vorbereiten zur Abfrage der Änderungsdaten</span><span class="sxs-lookup"><span data-stu-id="67f49-102">Prepare to Query for the Change Data</span></span>
  <span data-ttu-id="67f49-103">In der Ablaufsteuerung eines [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Pakets, das ein inkrementelles Laden von Änderungsdaten ausführt, besteht der dritte und letzte Task darin, die Abfrage der Änderungsdaten vorzubereiten und einen Datenflusstask hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="67f49-103">In the control flow of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that performs an incremental load of change data, the third and final task is to prepare to query for the change data and add a Data Flow task.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="67f49-104">Beim zweiten Task für die Ablaufsteuerung muss sichergestellt werden, dass die Änderungsdaten für das ausgewählte Intervall bereit sind.</span><span class="sxs-lookup"><span data-stu-id="67f49-104">The second task for the control flow is to ensure that the change data for the selected interval is ready.</span></span> <span data-ttu-id="67f49-105">Weitere Informationen zu diesem Task finden Sie unter [Bestimmen, ob die Änderungsdaten bereit sind](determine-whether-the-change-data-is-ready.md).</span><span class="sxs-lookup"><span data-stu-id="67f49-105">For more information about this task, see [Determine Whether the Change Data Is Ready](determine-whether-the-change-data-is-ready.md).</span></span> <span data-ttu-id="67f49-106">Eine Beschreibung des Gesamtprozesses zum Entwurf der Ablaufsteuerung finden Sie unter [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="67f49-106">For a description of the overall process of designing the control flow, see [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span></span>  
  
## <a name="design-considerations"></a><span data-ttu-id="67f49-107">Entwurfsaspekte</span><span class="sxs-lookup"><span data-stu-id="67f49-107">Design Considerations</span></span>  
 <span data-ttu-id="67f49-108">Wenn Sie die Änderungsdaten abrufen möchten, müssen Sie eine Transact-SQL-Tabellenwertfunktion aufrufen, die die Endpunkte des Intervalls als Eingabeparameter akzeptiert und für das angegebene Intervall Änderungsdaten zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="67f49-108">To retrieve the change data, you will call a Transact-SQL table-valued function that accepts the endpoints of the interval as input parameters and returns change data for the specified interval.</span></span> <span data-ttu-id="67f49-109">Eine Quellkomponente im Datenfluss ruft diese Funktion auf.</span><span class="sxs-lookup"><span data-stu-id="67f49-109">A source component in the data flow calls this function.</span></span> <span data-ttu-id="67f49-110">Weitere Informationen zu dieser Quellkomponente finden Sie unter [Abrufen und Verstehen der Änderungsdaten](retrieve-and-understand-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="67f49-110">For information about this source component, see [Retrieve and Understand the Change Data](retrieve-and-understand-the-change-data.md).</span></span>  
  
 <span data-ttu-id="67f49-111">Die am häufigsten verwendeten [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Quellkomponenten, einschließlich der OLE DB-Quelle, der ADO-Quelle und der ADO NET-Quelle, können für eine Tabellenwertfunktion keine Parameterinformationen ableiten.</span><span class="sxs-lookup"><span data-stu-id="67f49-111">The most frequently used [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] source components, including the OLE DB source, the ADO source, and the ADO NET source, cannot derive parameter information for a table-valued function.</span></span> <span data-ttu-id="67f49-112">Deshalb können die meisten Quellen eine parametrisierte Funktion nicht direkt aufrufen.</span><span class="sxs-lookup"><span data-stu-id="67f49-112">Therefore, most sources cannot call a parameterized function directly.</span></span>  
  
 <span data-ttu-id="67f49-113">Ihnen stehen zwei Entwurfsoptionen zur Verfügung, um die Eingabeparameter an die Funktion zu übergeben:</span><span class="sxs-lookup"><span data-stu-id="67f49-113">You have two design options for passing the input parameters to the function:</span></span>  
  
-   <span data-ttu-id="67f49-114">**Assemblieren Sie die parametrisierte Abfrage als Zeichenfolge**.</span><span class="sxs-lookup"><span data-stu-id="67f49-114">**Assemble the parameterized query as a string**.</span></span> <span data-ttu-id="67f49-115">Sie können einen Skripttask oder einen Task "SQL ausführen" verwenden, um eine dynamische SQL-Zeichenfolge mit Parameterwerten hartcodiert in die Zeichenfolge zu assemblieren.</span><span class="sxs-lookup"><span data-stu-id="67f49-115">You can use a Script task or an Execute SQL task to assemble a dynamic SQL string with parameter values hard-coded into the string.</span></span> <span data-ttu-id="67f49-116">Sie können dann diese Zeichenfolge in einer Paketvariablen speichern und diese verwenden, um die SqlCommand-Eigenschaft einer Quellkomponente festzulegen.</span><span class="sxs-lookup"><span data-stu-id="67f49-116">Then, you can store this string in a package variable and use it to set the SqlCommand property of a source component.</span></span> <span data-ttu-id="67f49-117">Dieser Ansatz ist erfolgreich, da die Quellkomponente nicht länger Parameterinformationen benötigt.</span><span class="sxs-lookup"><span data-stu-id="67f49-117">This approach succeeds because the source component no longer requires parameter information.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="67f49-118">Ein vorkompiliertes Skript verursacht weniger Aufwand als ein Task "SQL ausführen".</span><span class="sxs-lookup"><span data-stu-id="67f49-118">A precompiled script incurs less overhead than an Execute SQL task.</span></span>  
  
-   <span data-ttu-id="67f49-119">**Verwenden Sie einen parametrisierten Wrapper**.</span><span class="sxs-lookup"><span data-stu-id="67f49-119">**Use a parameterized wrapper**.</span></span> <span data-ttu-id="67f49-120">Alternativ können Sie eine parametrisierte gespeicherte Prozedur als Wrapper erstellen, der die parametrisierte Tabellenwertfunktion aufruft.</span><span class="sxs-lookup"><span data-stu-id="67f49-120">Alternatively, you can create a parameterized stored procedure as a wrapper that calls the parameterized table-valued function.</span></span> <span data-ttu-id="67f49-121">Dieser Ansatz ist erfolgreich, da eine Quellkomponente Parameterinformationen für eine gespeicherte Prozedur erfolgreich ableiten kann.</span><span class="sxs-lookup"><span data-stu-id="67f49-121">This approach succeeds because a source component can successfully derive parameter information for a stored procedure.</span></span>  
  
 <span data-ttu-id="67f49-122">Dieses Thema verwendet die erste Entwurfsoption und assembliert eine parametrisierte Abfrage als Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="67f49-122">This topic uses the first design option and assembles a parameterized query as a string.</span></span>  
  
## <a name="preparing-the-query"></a><span data-ttu-id="67f49-123">Vorbereiten der Abfrage</span><span class="sxs-lookup"><span data-stu-id="67f49-123">Preparing the Query</span></span>  
 <span data-ttu-id="67f49-124">Bevor Sie die Werte der Eingabeparameter in eine einzelne Abfragezeichenfolge verketten können, müssen Sie die für die Abfrage erforderlichen Paketvariablen einrichten.</span><span class="sxs-lookup"><span data-stu-id="67f49-124">Before you can concatenate the values of the input parameters into a single query string, you have to set up the package variables that the query needs.</span></span>  
  
#### <a name="to-set-up-package-variables"></a><span data-ttu-id="67f49-125">So richten Sie Paketvariablen ein</span><span class="sxs-lookup"><span data-stu-id="67f49-125">To set up package variables</span></span>  
  
-   <span data-ttu-id="67f49-126">Erstellen Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]im Fenster **Variablen** eine Variable mit einem Zeichenfolgen-Datentyp, damit die Abfragezeichenfolge durch den Task "SQL ausführen" zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="67f49-126">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], in the **Variables** window, create a variable with a string data type to hold the query string returned by the Execute SQL Task.</span></span>  
  
     <span data-ttu-id="67f49-127">In diesem Beispiel wird der Variablenname "SqlDataQuery" verwendet.</span><span class="sxs-lookup"><span data-stu-id="67f49-127">This example uses the variable name, SqlDataQuery.</span></span>  
  
 <span data-ttu-id="67f49-128">Wenn die Paketvariable erstellt wurde, können Sie einen Skripttask oder einen Task "SQL ausführen" verwenden, um die Werte der Eingabeparameter zu verketten.</span><span class="sxs-lookup"><span data-stu-id="67f49-128">With the package variable created, you can use either a Script task or Execute SQL task to concatenate the values of the input parameters.</span></span> <span data-ttu-id="67f49-129">Die folgenden zwei Prozeduren beschreiben, wie diese Komponenten konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="67f49-129">The following two procedures describe how to configure these components.</span></span>  
  
#### <a name="to-use-a-script-task-to-concatenate-the-query-string"></a><span data-ttu-id="67f49-130">So verwenden Sie einen Skripttask zur Verkettung der Abfragezeichenfolge</span><span class="sxs-lookup"><span data-stu-id="67f49-130">To use a Script task to concatenate the query string</span></span>  
  
1.  <span data-ttu-id="67f49-131">Fügen Sie dem Paket auf der Registerkarte **Ablaufsteuerung** nach dem For-Schleifencontainer einen Skripttask hinzu, und verbinden Sie den For-Schleifencontainer mit dem Task.</span><span class="sxs-lookup"><span data-stu-id="67f49-131">On the **Control Flow** tab, add a Script task to the package after the For Loop container and connect the For Loop container to the task.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="67f49-132">In dieser Prozedur wird davon ausgegangen, dass das Paket ein inkrementelles Laden aus einer einzelnen Tabelle ausführt.</span><span class="sxs-lookup"><span data-stu-id="67f49-132">This procedure assumes that the package performs an incremental load from a single table.</span></span> <span data-ttu-id="67f49-133">Wenn das Paket aus mehreren Tabellen lädt und ein übergeordnetes Paket mit mehreren untergeordneten Paketen hat, würde dieser Task jedem untergeordneten Paket als erste Komponente hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="67f49-133">If the package loads from multiple tables and has a parent package with multiple child packages, this task would be added as the first component to each child package.</span></span> <span data-ttu-id="67f49-134">Weitere Informationen finden Sie unter [Ausführen eines inkrementellen Ladens von mehreren Tabellen](perform-an-incremental-load-of-multiple-tables.md).</span><span class="sxs-lookup"><span data-stu-id="67f49-134">For more information, see [Perform an Incremental Load of Multiple Tables](perform-an-incremental-load-of-multiple-tables.md).</span></span>  
  
2.  <span data-ttu-id="67f49-135">Aktivieren Sie im **Skripttask-Editor**auf der Seite **Skript** die folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="67f49-135">In the **Script Task Editor**, on the **Script** page, select the following options:</span></span>  
  
    1.  <span data-ttu-id="67f49-136">Wählen Sie für **ReadOnlyVariables**die Optionen **User::DataReady**, **User::ExtractStartTime**und **User::ExtractEndTime** aus.</span><span class="sxs-lookup"><span data-stu-id="67f49-136">For **ReadOnlyVariables**, select **User::DataReady**, **User::ExtractStartTime**, and **User::ExtractEndTime** from the.</span></span>  
  
    2.  <span data-ttu-id="67f49-137">Wählen Sie für **ReadWriteVariables**die Option User::SqlDataQuery aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="67f49-137">For **ReadWriteVariables**, select User::SqlDataQuery from the list.</span></span>  
  
3.  <span data-ttu-id="67f49-138">Klicken Sie im **Skripttask-Editor**auf der Seite **Skript** auf **Skript bearbeiten** , um die Skriptentwicklungsumgebung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="67f49-138">In the **Script Task Editor**, on the **Script** page, click **Edit Script** to open the script development environment.</span></span>  
  
4.  <span data-ttu-id="67f49-139">Geben Sie in der Main-Prozedur eines der folgenden Codesegmente ein:</span><span class="sxs-lookup"><span data-stu-id="67f49-139">In the Main procedure, enter one of the following code segments:</span></span>  
  
    -   <span data-ttu-id="67f49-140">Wenn Sie in C# programmieren, geben Sie die folgenden Codezeilen ein:</span><span class="sxs-lookup"><span data-stu-id="67f49-140">If you are programming in C#, enter the following lines of code:</span></span>  
  
        ```  
        int dataReady;  
        System.DateTime extractStartTime;  
        System.DateTime extractEndTime;  
        string sqlDataQuery;  
  
        dataReady = (int)Dts.Variables["DataReady"].Value;  
        extractStartTime = (System.DateTime)Dts.Variables["ExtractStartTime"].Value;  
        extractEndTime = (System.DateTime)Dts.Variables["ExtractEndTime"].Value;  
  
        if (dataReady == 2)  
          {  
          sqlDataQuery = "SELECT * FROM CDCSample.uf_Customer('" + string.Format("{0:yyyy-MM-dd hh:mm:ss}", extractStartTime) + "', '" + string.Format("{0:yyyy-MM-dd hh:mm:ss}", extractEndTime) + "')";  
          }  
        else  
          {  
          sqlDataQuery = "SELECT * FROM CDCSample.uf_Customer(null" + ", '" + string.Format("{0:yyyy-MM-dd hh:mm:ss}", extractEndTime) + "')";  
          }  
  
        Dts.Variables["SqlDataQuery"].Value = sqlDataQuery;  
        ```  
  
         <span data-ttu-id="67f49-141">\- oder –</span><span class="sxs-lookup"><span data-stu-id="67f49-141">\- or -</span></span>  
  
    -   <span data-ttu-id="67f49-142">Wenn Sie in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]programmieren, geben Sie die folgenden Codezeilen ein:</span><span class="sxs-lookup"><span data-stu-id="67f49-142">If you are programming in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)], enter the following lines of code:</span></span>  
  
        ```  
        Dim dataReady As Integer  
        Dim extractStartTime As Date  
        Dim extractEndTime As Date  
        Dim sqlDataQuery As String  
  
        dataReady = CType(Dts.Variables("DataReady").Value, Integer)  
        extractStartTime = CType(Dts.Variables("ExtractStartTime").Value, Date)  
        extractEndTime = CType(Dts.Variables("ExtractEndTime").Value, Date)  
  
        If dataReady = 2 Then  
          sqlDataQuery = "SELECT * FROM CDCSample.uf_Customer('" & _  
              String.Format("{0:yyyy-MM-dd hh:mm:ss}", extractStartTime) & _  
              "', '" & _  
              String.Format("{0:yyyy-MM-dd hh:mm:ss}", extractEndTime) & _  
              "')"  
        Else  
          sqlDataQuery = "SELECT * FROM CDCSample.uf_Customer(null" & _  
              ", '" & _  
              String.Format("{0:yyyy-MM-dd hh:mm:ss}", extractEndTime) & _  
              "')"  
        End If  
  
        Dts.Variables("SqlDataQuery").Value = sqlDataQuery  
  
        ```  
  
5.  <span data-ttu-id="67f49-143">Verlassen Sie die Standardcodezeile, die `DtsExecResult.Success` aus der Ausführung des Skripts zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="67f49-143">Leave the default line of code which returns `DtsExecResult.Success` from the execution of the script.</span></span>  
  
6.  <span data-ttu-id="67f49-144">Schließen Sie die Skriptentwicklungsumgebung und den **Skripttask-Editor**.</span><span class="sxs-lookup"><span data-stu-id="67f49-144">Close the script development environment and the **Script Task Editor**.</span></span>  
  
#### <a name="to-use-an-execute-sql-task-to-concatenate-the-query-string"></a><span data-ttu-id="67f49-145">So verwenden Sie einen Task "SQL ausführen" zur Verkettung der Abfragezeichenfolge</span><span class="sxs-lookup"><span data-stu-id="67f49-145">To use an Execute SQL task to concatenate the query string</span></span>  
  
1.  <span data-ttu-id="67f49-146">Fügen Sie dem Paket auf der Registerkarte **Ablaufsteuerung** nach dem For-Schleifencontainer einen Task "SQL ausführen" hinzu, und verbinden Sie den For-Schleifencontainer mit diesem Task.</span><span class="sxs-lookup"><span data-stu-id="67f49-146">On the **Control Flow** tab, add an Execute SQL task to the package after the For Loop container and connect the For Loop container to this task.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="67f49-147">In dieser Prozedur wird davon ausgegangen, dass das Paket ein inkrementelles Laden aus einer einzelnen Tabelle ausführt.</span><span class="sxs-lookup"><span data-stu-id="67f49-147">This procedure assumes that the package performs an incremental load from a single table.</span></span> <span data-ttu-id="67f49-148">Wenn das Paket aus mehreren Tabellen lädt und ein übergeordnetes Paket mit mehreren untergeordneten Paketen hat, würde dieser Task jedem untergeordneten Paket als erste Komponente hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="67f49-148">If the package loads from multiple tables and has a parent package with multiple child packages, this task would be added as the first component to each child package.</span></span> <span data-ttu-id="67f49-149">Weitere Informationen finden Sie unter [Ausführen eines inkrementellen Ladens von mehreren Tabellen](perform-an-incremental-load-of-multiple-tables.md).</span><span class="sxs-lookup"><span data-stu-id="67f49-149">For more information, see [Perform an Incremental Load of Multiple Tables](perform-an-incremental-load-of-multiple-tables.md).</span></span>  
  
2.  <span data-ttu-id="67f49-150">Aktivieren Sie im **Skripttask-Editor**auf der Seite **Skript** die folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="67f49-150">In the **Execute SQL Task Editor**, on the **General** page, select the following options:</span></span>  
  
    1.  <span data-ttu-id="67f49-151">Wählen Sie für **ResultSet**die Option **Einzelne Zeile**aus.</span><span class="sxs-lookup"><span data-stu-id="67f49-151">For **ResultSet**, select **Single row**.</span></span>  
  
    2.  <span data-ttu-id="67f49-152">Konfigurieren Sie zur Quelldatenbank eine gültige Verbindung.</span><span class="sxs-lookup"><span data-stu-id="67f49-152">Configure a valid connection to the source database.</span></span>  
  
    3.  <span data-ttu-id="67f49-153">Wählen Sie für **SQLSourceType**die Option **Direkteingabe**aus.</span><span class="sxs-lookup"><span data-stu-id="67f49-153">For **SQLSourceType**, select **Direct input**.</span></span>  
  
    4.  <span data-ttu-id="67f49-154">Geben Sie für **SQLStatement**die folgende SQL-Anweisung ein:</span><span class="sxs-lookup"><span data-stu-id="67f49-154">For **SQLStatement**, enter the following SQL statement:</span></span>  
  
        ```  
        declare @ExtractStartTime datetime,  
        @ExtractEndTime datetime,   
        @DataReady int  
  
        select @DataReady = ?,   
        @ExtractStartTime = ?,   
        @ExtractEndTime = ?  
  
        if @DataReady = 2  
        select N'select * from CDCSample.uf_Customer'  
        + N'('''+ convert(nvarchar(30),@ExtractStartTime,120)  
        + ''', '''  
        + convert(nvarchar(30),@ExtractEndTime,120) + ''') '   
        as SqlDataQuery  
        else  
        select N'select * from CDCSample.uf_Customer'  
        + N'(null, '''  
        + convert(nvarchar(30),@ExtractEndTime,120)  
        + ''') '  
        as SqlDataQuery  
  
        ```  
  
        > [!NOTE]  
        >  <span data-ttu-id="67f49-155">Die `else`-Klausel in diesem Beispiel generiert eine Abfrage für das erste Laden der Änderungsdaten, indem für das Startdatum und die Startzeit ein NULL-Wert übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="67f49-155">The `else` clause in this sample generates a query for the initial load of change data by passing a null value for the starting date and time.</span></span> <span data-ttu-id="67f49-156">Dieses Beispiel befasst sich nicht mit dem Szenario, in dem Änderungen, die vor der Aktivierung von Change Data Capture vorgenommen wurden, auch ins Data Warehouse hochgeladen werden müssen.</span><span class="sxs-lookup"><span data-stu-id="67f49-156">This sample does not address the scenario in which changes that were made before change data capture was enabled also have to be uploaded to the data warehouse.</span></span>  
  
3.  <span data-ttu-id="67f49-157">Nehmen Sie auf der Seite **Parameterzuordnung** vom **Editor für den Task 'SQL ausführen'** die folgende Zuordnung vor:</span><span class="sxs-lookup"><span data-stu-id="67f49-157">On the **Parameter Mapping** page of the **Execute SQL Task Editor**, do the following mapping:</span></span>  
  
    1.  <span data-ttu-id="67f49-158">Ordnen Sie dem Parameter 0 die DataReady-Variable zu.</span><span class="sxs-lookup"><span data-stu-id="67f49-158">Map the DataReady variable to parameter 0.</span></span>  
  
    2.  <span data-ttu-id="67f49-159">Ordnen Sie dem Parameter 1 die ExtractStartTime-Variable zu.</span><span class="sxs-lookup"><span data-stu-id="67f49-159">Map the ExtractStartTime variable to parameter 1.</span></span>  
  
    3.  <span data-ttu-id="67f49-160">Ordnen Sie dem Parameter 2 die ExtractEndTime-Variable zu.</span><span class="sxs-lookup"><span data-stu-id="67f49-160">Map the ExtractEndTime variable to parameter 2.</span></span>  
  
4.  <span data-ttu-id="67f49-161">Ordnen Sie auf der Seite **Resultset** vom **Editor für den Task 'SQL ausführen'** der SqlDataQuery-Variablen den Ergebnisnamen zu.</span><span class="sxs-lookup"><span data-stu-id="67f49-161">On the **Result Set** page of the **Execute SQL Task Editor**, map the Result Name to the SqlDataQuery variable.</span></span>  
  
     <span data-ttu-id="67f49-162">Der Ergebnisname ist der Name der einzelnen Spalte, die zurückgegeben wird, SqlDataQuery.</span><span class="sxs-lookup"><span data-stu-id="67f49-162">The Result Name is the name of the single column that is returned, SqlDataQuery.</span></span>  
  
 <span data-ttu-id="67f49-163">Die oben beschriebenen Prozeduren konfigurieren einen Task, der eine Abfragezeichenfolge mit hartcodierten Zeichenfolgewerten für die Eingabeparameter vorbereitet.</span><span class="sxs-lookup"><span data-stu-id="67f49-163">The previous procedures configure a task that prepares a query string with hard-coded string values for the input parameters.</span></span> <span data-ttu-id="67f49-164">Der folgende Code ist ein Beispiel für eine solche Abfragezeichenfolge:</span><span class="sxs-lookup"><span data-stu-id="67f49-164">The following code is an example of such a query string:</span></span>  
  
 `select * from CDCSample. uf_Customer('2007-06-11 14:21:58', '2007-06-12 14:21:58')`  
  
## <a name="adding-a-data-flow-task"></a><span data-ttu-id="67f49-165">Hinzufügen eines Datenflusstasks</span><span class="sxs-lookup"><span data-stu-id="67f49-165">Adding a Data Flow Task</span></span>  
 <span data-ttu-id="67f49-166">Das Hinzufügen eines Datenflusstasks ist der letzte Schritt beim Entwerfen einer Ablaufsteuerung für ein Paket.</span><span class="sxs-lookup"><span data-stu-id="67f49-166">The last step in designing the control flow for the package is to add a Data Flow task.</span></span>  
  
#### <a name="to-add-a-data-flow-task-and-complete-the-control-flow"></a><span data-ttu-id="67f49-167">So fügen Sie einen Datenflusstask hinzu und vervollständigen Sie die Ablaufsteuerung</span><span class="sxs-lookup"><span data-stu-id="67f49-167">To add a Data Flow task and complete the control flow</span></span>  
  
-   <span data-ttu-id="67f49-168">Fügen Sie auf der Registerkarte **Ablaufsteuerung** einen Datenflusstask hinzu, und verbinden Sie den Task, der die Abfragezeichenfolge verkettet hat.</span><span class="sxs-lookup"><span data-stu-id="67f49-168">On the **Control Flow** tab, add a Data Flow task and connect the task that concatenated the query string.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="67f49-169">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="67f49-169">Next Step</span></span>  
 <span data-ttu-id="67f49-170">Nach der Vorbereitung der Abfragezeichenfolge und der Konfiguration des Datenflusstasks besteht der nächste Schritt darin, die Tabellenwertfunktion zu erstellen, mit der die Änderungsdaten von der Datenbank abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="67f49-170">After you prepare the query string and configure the Data Flow task, the next step is create the table-valued function that will retrieve the change data from the database.</span></span>  
  
 <span data-ttu-id="67f49-171">**Nächstes Thema:** [Erstellen der Funktion zum Abrufen der Änderungsdaten](create-the-function-to-retrieve-the-change-data.md)</span><span class="sxs-lookup"><span data-stu-id="67f49-171">**Next topic:** [Create the Function to Retrieve the Change Data](create-the-function-to-retrieve-the-change-data.md)</span></span>  
  
  
