---
title: Laden der Ausgabe eines lokalen Pakets | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data flow [Integration Services], loading results
- loading data flow results
ms.assetid: aba8ecb7-0dcf-40d0-a2a8-64da0da94b93
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6799e593ab9d5ae1a9358bf54f4927838991ebd0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723990"
---
# <a name="loading-the-output-of-a-local-package"></a><span data-ttu-id="2c8b2-102">Laden der Ausgabe eines lokalen Pakets</span><span class="sxs-lookup"><span data-stu-id="2c8b2-102">Loading the Output of a Local Package</span></span>
  <span data-ttu-id="2c8b2-103">Clientanwendungen können die Ausgabe von [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Paketen lesen, wenn diese mithilfe von [!INCLUDE[vstecado](../../includes/vstecado-md.md)] in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Zielen oder mithilfe der Klassen im **System.IO**-Namespace in Flatfilezielen gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-103">Client applications can read the output of [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages when the output is saved to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destinations by using [!INCLUDE[vstecado](../../includes/vstecado-md.md)], or when the output is saved to a flat file destination by using the classes in the **System.IO** namespace.</span></span> <span data-ttu-id="2c8b2-104">Eine Clientanwendung kann jedoch die Ausgabe eines Pakets auch direkt aus dem Arbeitsspeicher lesen, ohne dass hierfür ein Zwischenschritt zur persistenten Speicherung der Daten erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-104">However, a client application can also read the output of a package directly from memory, without the need for an intermediate step to persist the data.</span></span> <span data-ttu-id="2c8b2-105">Der Schlüssel für diese Lösung ist der- `Microsoft.SqlServer.Dts.DtsClient` Namespace, der spezialisierte Implementierungen der `IDbConnection` -, `IDbCommand` -und **IDbDataParameter** -Schnittstellen aus dem **System. Data** -Namespace enthält.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-105">The key to this solution is the `Microsoft.SqlServer.Dts.DtsClient` namespace, which contains specialized implementations of the `IDbConnection`, `IDbCommand`, and **IDbDataParameter** interfaces from the **System.Data** namespace.</span></span> <span data-ttu-id="2c8b2-106">Die Assembly „Microsoft.SqlServer.Dts.DtsClient.dll“ wird standardmäßig im Verzeichnis **%ProgramFiles%\Microsoft SQL Server\100\DTS\Binn** installiert.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-106">The assembly Microsoft.SqlServer.Dts.DtsClient.dll is installed by default in **%ProgramFiles%\Microsoft SQL Server\100\DTS\Binn**.</span></span>

> [!NOTE]
>  <span data-ttu-id="2c8b2-107">Für die in diesem Artikel beschriebene Vorgehensweise müssen die DelayValidation-Eigenschaft des Datenflusstasks und alle übergeordneten Objekte auf den Standardwert **FALSE** festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-107">The procedure described in this topic requires that the DelayValidation property of the Data Flow task and of any parent objects be set to its default value of **False**.</span></span>

## <a name="description"></a><span data-ttu-id="2c8b2-108">Description</span><span class="sxs-lookup"><span data-stu-id="2c8b2-108">Description</span></span>
 <span data-ttu-id="2c8b2-109">In dieser Prozedur wird veranschaulicht, wie eine Clientanwendung in verwaltetem Code entwickelt wird, die die Ausgabe eines Pakets mit einem DataReader-Ziel direkt aus dem Arbeitsspeicher lädt.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-109">This procedure demonstrates how to develop a client application in managed code that loads the output of a package with a DataReader destination directly from memory.</span></span> <span data-ttu-id="2c8b2-110">Die hier zusammengefassten Schritte werden in dem folgenden Codebeispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-110">The steps summarized here are demonstrated in the code sample that follows.</span></span>

#### <a name="to-load-data-package-output-into-a-client-application"></a><span data-ttu-id="2c8b2-111">So laden Sie Datenpaketausgabe in eine Clientanwendung</span><span class="sxs-lookup"><span data-stu-id="2c8b2-111">To load data package output into a client application</span></span>

1.  <span data-ttu-id="2c8b2-112">Konfigurieren Sie in dem Paket ein DataReader-Ziel so, dass die Ausgabe empfangen wird, die in die Clientanwendung gelesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-112">In the package, configure a DataReader destination to receive the output that you want to read into the client application.</span></span> <span data-ttu-id="2c8b2-113">Geben Sie dem DataReader-Ziel einen aussagekräftigen Namen, da Sie diesen Namen später in der Clientanwendung verwenden werden.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-113">Give the DataReader destination a descriptive name, since you will use this name later in your client application.</span></span> <span data-ttu-id="2c8b2-114">Notieren Sie sich den Namen des DataReader-Ziels.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-114">Make a note of the name of the DataReader destination.</span></span>

2.  <span data-ttu-id="2c8b2-115">Legen Sie im Entwicklungsprojekt einen Verweis auf den- `Microsoft.SqlServer.Dts.DtsClient` Namespace fest, indem Sie die Assembly **Microsoft.SqlServer.Dts.DtsClient.dll**suchen.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-115">In the development project, set a reference to the `Microsoft.SqlServer.Dts.DtsClient` namespace by locating the assembly **Microsoft.SqlServer.Dts.DtsClient.dll**.</span></span> <span data-ttu-id="2c8b2-116">Diese Assembly wird standardmäßig im Verzeichnis **C:\Programme\Microsoft SQL Server\100\DTS\Binn** installiert.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-116">By default, this assembly is installed in **C:\Program Files\Microsoft SQL Server\100\DTS\Binn**.</span></span> <span data-ttu-id="2c8b2-117">Importieren Sie den Namespace mithilfe der c#- `Using` Anweisung oder der-Anweisung in Ihren Code [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] `Imports` .</span><span class="sxs-lookup"><span data-stu-id="2c8b2-117">Import the namespace into your code by using the C# `Using` or the [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] `Imports` statement.</span></span>

3.  <span data-ttu-id="2c8b2-118">Erstellen Sie in Ihrem Code ein Objekt vom Typ `DtsClient.DtsConnection` mit einer Verbindungs Zeichenfolge, die die Befehlszeilenparameter enthält, die für **dtexec.exe** zum Ausführen des Pakets erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-118">In your code, create an object of type `DtsClient.DtsConnection` with a connection string that contains the command-line parameters required by **dtexec.exe** to run the package.</span></span> <span data-ttu-id="2c8b2-119">Weitere Informationen finden Sie [hier](../packages/dtexec-utility.md).</span><span class="sxs-lookup"><span data-stu-id="2c8b2-119">For more information, see [dtexec Utility](../packages/dtexec-utility.md).</span></span> <span data-ttu-id="2c8b2-120">Öffnen Sie dann die Verbindung mit dieser Verbindungszeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-120">Then open the connection with this connection string.</span></span> <span data-ttu-id="2c8b2-121">Sie können auch das **dtexecui**-Hilfsprogramm verwenden, um die erforderliche Verbindungszeichenfolge visuell zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-121">You can also use the **dtexecui** utility to create the required connection string visually.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="2c8b2-122">Im Beispielcode wird das Laden des Pakets aus dem Dateisystem mithilfe der `/FILE <path and filename>`-Syntax veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-122">The sample code demonstrates loading the package from the file system by using the `/FILE <path and filename>` syntax.</span></span> <span data-ttu-id="2c8b2-123">Sie können das Paket jedoch auch aus der MSDB-Datenbank mithilfe der `/SQL <package name>`-Syntax oder aus dem [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Paket mithilfe der `/DTS \<folder name>\<package name>`-Syntax laden.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-123">However you can also load the package from the MSDB database by using the `/SQL <package name>` syntax, or from the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package store by using the `/DTS \<folder name>\<package name>` syntax.</span></span>

4.  <span data-ttu-id="2c8b2-124">Erstellen Sie ein Objekt vom Typ `DtsClient.DtsCommand`, das die zuvor erstellte `DtsConnection` verwendet und die `CommandText`-Eigenschaft auf den Namen des DataReader-Ziels in dem Paket festlegt.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-124">Create an object of type `DtsClient.DtsCommand` that uses the previously created `DtsConnection` and set its `CommandText` property to the name of the DataReader destination in the package.</span></span> <span data-ttu-id="2c8b2-125">Rufen Sie dann die `ExecuteReader`-Methode des Befehlsobjekts auf, um die Paketergebnisse in ein neues DataReader-Ziel zu laden.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-125">Then call the `ExecuteReader` method of the command object to load the package results into a new DataReader.</span></span>

5.  <span data-ttu-id="2c8b2-126">Optional können Sie die Ausgabe des Pakets indirekt parametrisieren, indem Sie die Auflistung von `DtsDataParameter`-Objekten im `DtsCommand`-Objekt verwenden, um Werte an die in dem Paket definierten Variablen zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-126">Optionally, you can indirectly parameterize the output of the package by using the collection of `DtsDataParameter` objects on the `DtsCommand` object to pass values to variables defined in the package.</span></span> <span data-ttu-id="2c8b2-127">Innerhalb des Pakets können Sie diese Variablen als Abfrageparameter oder in Ausdrücken verwenden, um die an das DataReader-Ziel zurückgegebenen Ergebnisse zu beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-127">Within the package, you can use these variables as query parameters or in expressions to affect the results returned to the DataReader destination.</span></span> <span data-ttu-id="2c8b2-128">Sie müssen diese Variablen im Paket im **DtsClient** -Namespace definieren, bevor Sie Sie mit dem- `DtsDataParameter` Objekt aus einer Client Anwendung verwenden können.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-128">You must define these variables in the package in the **DtsClient** namespace before you can use them with the `DtsDataParameter` object from a client application.</span></span> <span data-ttu-id="2c8b2-129">(Möglicherweise müssen Sie im Fenster **Variablen** auf die Symbolleisten Schaltfläche **Variablen Spalten auswählen** klicken, um die Spalte **Namespace** anzuzeigen.) Lassen Sie in Ihrem Client Code, wenn Sie der-Auflistung der einen hinzufügen `DtsDataParameter` `Parameters` `DtsCommand` , den DtsClient-Namespace Verweis aus dem Variablennamen weglassen.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-129">(You may need to click the **Choose Variable Columns** toolbar button in the **Variables** window to display the **Namespace** column.) In your client code, when you add a `DtsDataParameter` to the `Parameters` collection of the `DtsCommand`, omit the DtsClient namespace reference from the variable name.</span></span> <span data-ttu-id="2c8b2-130">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2c8b2-130">For example:</span></span>

    ```
    command.Parameters.Add(new DtsDataParameter("MyVariable", 1));
    ```

6.  <span data-ttu-id="2c8b2-131">Rufen Sie die `Read`-Methode des DataReader so oft wie benötigt wiederholt auf, um die Zeilen der Ausgabedaten zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-131">Call the `Read` method of the DataReader repeatedly as needed to loop through the rows of output data.</span></span> <span data-ttu-id="2c8b2-132">Verwenden Sie die Daten, oder speichern Sie die Daten zur späteren Verwendung in der Clientanwendung.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-132">Use the data, or save the data for later use, in the client application.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="2c8b2-133">Die `Read`-Methode dieser Implementierung des DataReader gibt, nachdem die letzte Zeile der Daten gelesen wurde, `true` noch ein weiteres Mal zurück.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-133">The `Read` method of this implementation of the DataReader returns `true` one more time after the last row of data has been read.</span></span> <span data-ttu-id="2c8b2-134">Daher ist es schwierig, den normalen Code zu verwenden, der den DataReader durchläuft, während von `Read``true` zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-134">This makes it difficult to use the usual code that loops through the DataReader while `Read` returns `true`.</span></span> <span data-ttu-id="2c8b2-135">Wenn der Code versucht, den DataReader oder die Verbindung nach dem Lesen der erwarteten Anzahl von Reihen zu schließen, ohne einen weiteren finalen Aufruf der `Read`-Methode durchzuführen, gibt der Code eine nicht behandelte Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-135">If your code attempts to close the DataReader or the connection after reading the expected number of rows, without an additional, final call to the `Read` method, the code will raise an unhandled exception.</span></span> <span data-ttu-id="2c8b2-136">Wenn der Code jedoch versucht, die Daten bei dieser letzten Iteration durch eine Schleife zu lesen und von `Read` immer noch `true` zurückgegeben wird, die letzte Zeile jedoch übergeben wurde, gibt der Code eine nicht behandelte `ApplicationException` mit der folgenden Meldung aus: "Das SSIS-IDataReader-Objekt liegt hinter dem Ende des Resultsets."</span><span class="sxs-lookup"><span data-stu-id="2c8b2-136">However, if your code attempts to read data on this final iteration through a loop, when `Read` still returns `true` but the last row has been passed, the code will raise an unhandled `ApplicationException` with the message, "The SSIS IDataReader is past the end of the resultset."</span></span> <span data-ttu-id="2c8b2-137">Dieses Verhalten unterscheidet sich von dem anderer DataReader-Implementierungen.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-137">This behavior is different from that of other DataReader implementations.</span></span> <span data-ttu-id="2c8b2-138">Wenn Sie daher eine Schleife verwenden, um die Zeilen in dem DataReader zu lesen, und von `Read` wird `true` zurückgegeben, müssen Sie den Code so schreiben, dass diese erwartete `ApplicationException` beim letzten erfolgreichen Aufruf der `Read`-Methode abgefangen, getestet und verworfen wird.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-138">Therefore, when using a loop to read through the rows in the DataReader while `Read` returns `true`, you need to write code to catch, test, and discard this anticipated `ApplicationException` on the last successful call to the `Read` method.</span></span> <span data-ttu-id="2c8b2-139">Sie können auch, wenn Sie die Anzahl von erwarteten Zeilen im Voraus wissen, die Zeilen verarbeiten und dann die `Read`-Methode ein letztes Mal aufrufen, bevor Sie den DataReader und die Verbindung schließen.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-139">Or, if you know in advance the number of rows expected, you can process the rows, and then call the `Read` method one more time before closing the DataReader and the connection.</span></span>

7.  <span data-ttu-id="2c8b2-140">Rufen Sie die `Dispose`-Methode des `DtsCommand`-Objekts auf.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-140">Call the `Dispose` method of the `DtsCommand` object.</span></span> <span data-ttu-id="2c8b2-141">Dies ist besonders wichtig, wenn Sie `DtsDataParameter`-Objekte verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-141">This is particularly important if you have used any `DtsDataParameter` objects.</span></span>

8.  <span data-ttu-id="2c8b2-142">Schließen Sie den DataReader und die Verbindungsobjekte.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-142">Close the DataReader and the connection objects.</span></span>

## <a name="example"></a><span data-ttu-id="2c8b2-143">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2c8b2-143">Example</span></span>
 <span data-ttu-id="2c8b2-144">Im folgenden Beispiel wird ein Paket ausgeführt, das einen einzelnen Aggregatwert berechnet und den Wert in einem DataReader-Ziel speichert. Dieser Wert wird dann vom DataReader gelesen und in einem Textfeld in einem Windows Form angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-144">The following example runs a package that calculates a single aggregate value and saves the value to a DataReader destination, and then reads this value from the DataReader and displays the value in a text box on a Windows Form.</span></span>

 <span data-ttu-id="2c8b2-145">Beim Laden der Ausgabe eines Pakets in einer Clientanwendung müssen keine Parameter verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-145">The use of parameters is not required when loading the output of a package into a client application.</span></span> <span data-ttu-id="2c8b2-146">Wenn Sie keinen Parameter verwenden möchten, können Sie die Verwendung der Variablen im **DtsClient** -Namespace weglassen und den Code weglassen, der das- `DtsDataParameter` Objekt verwendet.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-146">If you do not want to use a parameter, you can omit the use of the variable in the **DtsClient** namespace, and omit the code that uses the `DtsDataParameter` object.</span></span>

#### <a name="to-create-the-test-package"></a><span data-ttu-id="2c8b2-147">So erstellen Sie das Testpaket</span><span class="sxs-lookup"><span data-stu-id="2c8b2-147">To create the test package</span></span>

1.  <span data-ttu-id="2c8b2-148">Erstellen Sie ein neues [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Paket.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-148">Create a new [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package.</span></span> <span data-ttu-id="2c8b2-149">Im Beispielcode wird "DtsClientWParamPkg.dtsx" als Name des Pakets verwendet.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-149">The sample code uses "DtsClientWParamPkg.dtsx" as the name of the package.</span></span>

2.  <span data-ttu-id="2c8b2-150">Fügen Sie eine Variable der Typzeichenfolge im DtsClient-Namespace hinzu.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-150">Add a variable of type String in the DtsClient namespace.</span></span> <span data-ttu-id="2c8b2-151">Der Beispielscode verwendet "Country" als den Namen der Variablen.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-151">The sample code use Country as the name of the variable.</span></span> <span data-ttu-id="2c8b2-152">(Möglicherweise müssen Sie im Fenster **Variablen** auf **Variablenspalten auswählen** auf der Symbolleiste klicken, um die Spalte **Namespace** anzuzeigen.)</span><span class="sxs-lookup"><span data-stu-id="2c8b2-152">(You may need to click the **Choose Variable Columns** toolbar button in the **Variables** window to display the **Namespace** column.)</span></span>

3.  <span data-ttu-id="2c8b2-153">Fügen Sie einen OLE DB-Verbindungs-Manager hinzu, der eine Verbindung zu der [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)]-Beispieldatenbank herstellt.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-153">Add an OLE DB connection manager that connects to the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] sample database.</span></span>

4.  <span data-ttu-id="2c8b2-154">Fügen Sie dem Paket einen Datenflusstask hinzu, und wechseln Sie zur Datenfluss-Entwurfsoberfläche.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-154">Add a data flow task to the package and switch to the Data Flow design surface.</span></span>

5.  <span data-ttu-id="2c8b2-155">Fügen Sie dem Datenfluss eine OLE DB-Quelle hinzu, und konfigurieren Sie sie so, dass der zuvor erstellte OLE DB-Verbindungs-Manager verwendet werden kann, den Sie vorher erstellt haben. Fügen Sie auch den folgenden SQL-Befehl hinzu:</span><span class="sxs-lookup"><span data-stu-id="2c8b2-155">Add an OLE DB source to the data flow and configure it to use the OLE DB connection manager created previously, and the following SQL command:</span></span>

    ```
    SELECT * FROM Sales.vIndividualCustomer WHERE CountryRegionName = ?
    ```

6.  <span data-ttu-id="2c8b2-156">Klicken Sie auf, und ordnen Sie `Parameters` im Dialogfeld **Abfrage Parameter festlegen** den einzelnen Eingabeparameter in der Abfrage, Parameter0, der DtsClient:: Country-Variablen zu.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-156">Click `Parameters` and, in the **Set Query Parameters** dialog box, map the single input parameter in the query, Parameter0, to the DtsClient::Country variable.</span></span>

7.  <span data-ttu-id="2c8b2-157">Fügen Sie dem Datenfluss eine Transformation für das Aggregieren hinzu, und verbinden Sie die Ausgabe der OLE DB-Quelle mit der Transformation.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-157">Add an Aggregate transformation to the data flow, and connect the output of the OLE DB source to the transformation.</span></span> <span data-ttu-id="2c8b2-158">Öffnen Sie den Transformations-Editor für Aggregieren, und konfigurieren Sie ihn so, dass er einen "count all"-Vorgang für alle Eingabe Spalten (\*) ausführt und den aggregierten Wert mit dem Alias CustomerCount ausgibt.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-158">Open the Aggregate Transformation Editor and configure it to perform a "Count all" operation on all input columns (\*) and to output the aggregated value with the alias CustomerCount.</span></span>

8.  <span data-ttu-id="2c8b2-159">Fügen Sie dem Datenfluss ein DatenReader-Ziel hinzu, und verbinden Sie die Ausgabe der Transformation für das Aggregieren mit dem DataReader-Ziel.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-159">Add a DataReader destination to the data flow and connect the output of the Aggregate transformation to the DataReader destination.</span></span> <span data-ttu-id="2c8b2-160">Im Beispielcode wird "DataReaderDest" als Name des DataReader verwendet.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-160">The sample code uses "DataReaderDest" as the name of the DataReader.</span></span> <span data-ttu-id="2c8b2-161">Wählen Sie die einzelne verfügbare Eingabespalte, CustomerCount, für das Ziel aus.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-161">Select the single available input column, CustomerCount, for the destination.</span></span>

9. <span data-ttu-id="2c8b2-162">Speichern Sie das Paket.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-162">Save the package.</span></span> <span data-ttu-id="2c8b2-163">Die anschließend erstellte Testanwendung führt das Paket aus und ruft seine Ausgabe direkt vom Arbeitsspeicher ab.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-163">The test application created next will run the package and retrieve its output directly from memory.</span></span>

#### <a name="to-create-the-test-application"></a><span data-ttu-id="2c8b2-164">So erstellen Sie die Testanwendung</span><span class="sxs-lookup"><span data-stu-id="2c8b2-164">To create the test application</span></span>

1.  <span data-ttu-id="2c8b2-165">Erstellen Sie eine neue Windows Forms-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-165">Create a new Windows Forms application.</span></span>

2.  <span data-ttu-id="2c8b2-166">Fügen Sie einen Verweis auf den- `Microsoft.SqlServer.Dts.DtsClient` Namespace hinzu, indem Sie die Assembly mit demselben Namen in **%ProgramFiles%\Microsoft SQL server\100\dz\binn**suchen.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-166">Add a reference to the `Microsoft.SqlServer.Dts.DtsClient` namespace by browsing to the assembly of the same name in **%ProgramFiles%\Microsoft SQL Server\100\DTS\Binn**.</span></span>

3.  <span data-ttu-id="2c8b2-167">Kopieren Sie den folgenden Beispielcode, und fügen Sie ihn in das Codemodul für das Formular ein.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-167">Copy and paste the following sample code into the code module for the form.</span></span>

4.  <span data-ttu-id="2c8b2-168">Ändern Sie den Wert der `dtexecArgs` Variablen nach Bedarf, damit Sie die Befehlszeilenparameter enthält, die für **dtexec.exe** zum Ausführen des Pakets erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-168">Modify the value of the `dtexecArgs` variable as required so that it contains the command-line parameters required by **dtexec.exe** to run the package.</span></span> <span data-ttu-id="2c8b2-169">Im Beispielcode wird das Paket aus dem Dateisystem geladen.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-169">The sample code loads the package from the file system.</span></span>

5.  <span data-ttu-id="2c8b2-170">Ändern Sie den Wert der `dataReaderName` Variablen nach Bedarf, damit Sie den Namen des DataReader-Ziels im Paket enthält.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-170">Modify the value of the `dataReaderName` variable as required so that it contains the name of the DataReader destination in the package.</span></span>

6.  <span data-ttu-id="2c8b2-171">Setzen Sie eine Schaltfläche und ein Textfeld in das Formular.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-171">Put a button and a text box on the form.</span></span> <span data-ttu-id="2c8b2-172">Im Beispielcode `btnRun` wird als Name der Schaltfläche und `txtResults` als Name des Textfelds verwendet.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-172">The sample code uses `btnRun` as the name of the button, and `txtResults` as the name of the text box.</span></span>

7.  <span data-ttu-id="2c8b2-173">Führen Sie die Anwendung aus, und klicken Sie auf die Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-173">Run the application and click the button.</span></span> <span data-ttu-id="2c8b2-174">Nach einer kurzen Pause während der Ausführung des Pakets sollte der von dem Paket berechnete Aggregatwert (die Anzahl von Kunden in Kanada) im Textfeld auf dem Formular angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-174">After a brief pause while the package runs, you should see the aggregate value calculated by the package (the count of customers in Canada) displayed in the text box on the form.</span></span>

### <a name="sample-code"></a><span data-ttu-id="2c8b2-175">Beispielcode</span><span class="sxs-lookup"><span data-stu-id="2c8b2-175">Sample Code</span></span>

```vb
Imports System.Data
Imports Microsoft.SqlServer.Dts.DtsClient

Public Class Form1

  Private Sub btnRun_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles btnRun.Click

    Dim dtexecArgs As String
    Dim dataReaderName As String
    Dim countryName As String

    Dim dtsConnection As DtsConnection
    Dim dtsCommand As DtsCommand
    Dim dtsDataReader As IDataReader
    Dim dtsParameter As DtsDataParameter

    Windows.Forms.Cursor.Current = Cursors.WaitCursor

    dtexecArgs = "/FILE ""C:\...\DtsClientWParamPkg.dtsx"""
    dataReaderName = "DataReaderDest"
    countryName = "Canada"

    dtsConnection = New DtsConnection()
    With dtsConnection
      .ConnectionString = dtexecArgs
      .Open()
    End With

    dtsCommand = New DtsCommand(dtsConnection)
    dtsCommand.CommandText = dataReaderName

    dtsParameter = New DtsDataParameter("Country", DbType.String)
    dtsParameter.Direction = ParameterDirection.Input
    dtsCommand.Parameters.Add(dtsParameter)

    dtsParameter.Value = countryName

    dtsDataReader = dtsCommand.ExecuteReader(CommandBehavior.Default)

    With dtsDataReader
      .Read()
      txtResults.Text = .GetInt32(0).ToString("N0")
    End With

    'After reaching the end of data rows,
    ' call the Read method one more time.
    Try
      dtsDataReader.Read()
    Catch ex As Exception
      MessageBox.Show("Exception on final call to Read method:" & ControlChars.CrLf & _
      ex.Message & ControlChars.CrLf & _
      ex.InnerException.Message, "Exception on final call to Read method", _
      MessageBoxButtons.OK, MessageBoxIcon.Error)
    End Try

    ' The following method is a best practice, and is
    '  required when using DtsDataParameter objects.
    dtsCommand.Dispose()

    Try
      dtsDataReader.Close()
    Catch ex As Exception
      MessageBox.Show("Exception closing DataReader:" & ControlChars.CrLf & _
      ex.Message & ControlChars.CrLf & _
      ex.InnerException.Message, "Exception closing DataReader", _
      MessageBoxButtons.OK, MessageBoxIcon.Error)
    End Try

    Try
      dtsConnection.Close()
    Catch ex As Exception
      MessageBox.Show("Exception closing connection:" & ControlChars.CrLf & _
      ex.Message & ControlChars.CrLf & _
      ex.InnerException.Message, "Exception closing connection", _
      MessageBoxButtons.OK, MessageBoxIcon.Error)
    End Try

    Windows.Forms.Cursor.Current = Cursors.Default

  End Sub

End Class
```

```csharp
using System;
using System.Windows.Forms;
using System.Data;
using Microsoft.SqlServer.Dts.DtsClient;

namespace DtsClientWParamCS
{
  public partial class Form1 : Form
  {
    public Form1()
    {
      InitializeComponent();
      this.btnRun.Click += new System.EventHandler(this.btnRun_Click);
    }

    private void btnRun_Click(object sender, EventArgs e)
    {
      string dtexecArgs;
      string dataReaderName;
      string countryName;

      DtsConnection dtsConnection;
      DtsCommand dtsCommand;
      IDataReader dtsDataReader;
      DtsDataParameter dtsParameter;

      Cursor.Current = Cursors.WaitCursor;

      dtexecArgs = @"/FILE ""C:\...\DtsClientWParamPkg.dtsx""";
      dataReaderName = "DataReaderDest";
      countryName = "Canada";

      dtsConnection = new DtsConnection();
      {
        dtsConnection.ConnectionString = dtexecArgs;
        dtsConnection.Open();
      }

      dtsCommand = new DtsCommand(dtsConnection);
      dtsCommand.CommandText = dataReaderName;

      dtsParameter = new DtsDataParameter("Country", DbType.String);
      dtsParameter.Direction = ParameterDirection.Input;
      dtsCommand.Parameters.Add(dtsParameter);

      dtsParameter.Value = countryName;

      dtsDataReader = dtsCommand.ExecuteReader(CommandBehavior.Default);

      {
        dtsDataReader.Read();
        txtResults.Text = dtsDataReader.GetInt32(0).ToString("N0");
      }

      //After reaching the end of data rows,
      // call the Read method one more time.
      try
      {
        dtsDataReader.Read();
      }
      catch (Exception ex)
      {
        MessageBox.Show(
          "Exception on final call to Read method:\n" + ex.Message + "\n" + ex.InnerException.Message,
          "Exception on final call to Read method", MessageBoxButtons.OK, MessageBoxIcon.Error);
      }

      // The following method is a best practice, and is
      //  required when using DtsDataParameter objects.
      dtsCommand.Dispose();

      try
      {
        dtsDataReader.Close();
      }
      catch (Exception ex)
      {
        MessageBox.Show(
          "Exception closing DataReader:\n" + ex.Message + "\n" + ex.InnerException.Message,
          "Exception closing DataReader", MessageBoxButtons.OK, MessageBoxIcon.Error);
      }

      try
      {
        dtsConnection.Close();
      }
      catch (Exception ex)
      {
        MessageBox.Show(
          "Exception closing connection:\n" + ex.Message + "\n" + ex.InnerException.Message,
          "Exception closing connection", MessageBoxButtons.OK, MessageBoxIcon.Error);
      }

      Cursor.Current = Cursors.Default;

    }
  }
}
```

<span data-ttu-id="2c8b2-176">![Integration Services Symbol (klein)](../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="2c8b2-176">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="2c8b2-177">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="2c8b2-177">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="2c8b2-178">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="2c8b2-178">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="2c8b2-179">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="2c8b2-179">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="2c8b2-180">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2c8b2-180">See Also</span></span>
 <span data-ttu-id="2c8b2-181">Grundlegendes zu [den Unterschieden zwischen der lokalen und der Remote Ausführung von](../run-manage-packages-programmatically/understanding-the-differences-between-local-and-remote-execution.md) [Laden und Ausführen eines lokalen Pakets](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md) Programm [Gesteuertes Laden und Ausführen eines Remote Pakets](../run-manage-packages-programmatically/loading-and-running-a-remote-package-programmatically.md)</span><span class="sxs-lookup"><span data-stu-id="2c8b2-181">[Understanding the Differences between Local and Remote Execution](../run-manage-packages-programmatically/understanding-the-differences-between-local-and-remote-execution.md) [Loading and Running a Local Package Programmatically](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md) [Loading and Running a Remote Package Programmatically](../run-manage-packages-programmatically/loading-and-running-a-remote-package-programmatically.md)</span></span>


