---
title: Verwenden von XML-Daten in Anwendungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- parameters [XML in SQL Server]
- XML [SQL Server], ADO
- columns [XML in SQL Server], ADO.NET
- ADO [XML in SQL Server]
- columns [XML in SQL Server], SQL Server Native Client
- xml data type [SQL Server], ADO
- SQLNCLI, XML
- xml data type [SQL Server], SQL Server Native Client
- SQL Server Native Client, XML
- ADO.NET [XML in SQL Server]
- XML [SQL Server], ADO.NET
- columns [XML in SQL Server], ADO
- xml data type [SQL Server], ADO.NET
- XML [SQL Server], SQL Server Native Client
ms.assetid: 5dabf7e0-c6df-451d-a070-4661f84607fd
author: rothja
ms.author: jroth
ms.openlocfilehash: 79dd4f4d2ff3cd61bc33c632f499bfb8e8817f0f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695449"
---
# <a name="use-xml-data-in-applications"></a><span data-ttu-id="5c9be-102">Verwenden von XML-Daten in Anwendungen</span><span class="sxs-lookup"><span data-stu-id="5c9be-102">Use XML Data in Applications</span></span>
  <span data-ttu-id="5c9be-103">In diesem Thema werden die Optionen beschrieben, die Ihnen bei der Arbeit mit dem `xml`-Datentyp in Ihrer Anwendung zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="5c9be-103">This topic describes the options that are available to you for working with the `xml` data type in your application.</span></span> <span data-ttu-id="5c9be-104">Das Thema enthält Informationen zu Folgendem:</span><span class="sxs-lookup"><span data-stu-id="5c9be-104">The topic includes information about the following:</span></span>  
  
-   <span data-ttu-id="5c9be-105">Verarbeiten von XML in einer Spalte vom Typ `xml` mithilfe von ADO und [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client</span><span class="sxs-lookup"><span data-stu-id="5c9be-105">Handling XML from an `xml` type column by using ADO and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client</span></span>  
  
-   <span data-ttu-id="5c9be-106">Verarbeiten von XML in einer Spalte vom Typ `xml` mithilfe von ADO.NET</span><span class="sxs-lookup"><span data-stu-id="5c9be-106">Handling XML from an `xml` type column by using ADO.NET</span></span>  
  
-   <span data-ttu-id="5c9be-107">Verarbeiten des `xml`-Typs in Parametern mithilfe von ADO.NET</span><span class="sxs-lookup"><span data-stu-id="5c9be-107">Handling `xml` type in parameters by using ADO.NET</span></span>  
  
## <a name="handling-xml-from-an-xml-type-column-by-using-ado-and-sql-server-native-client"></a><span data-ttu-id="5c9be-108">Verarbeiten von XML in einer Spalte vom Typ xml mithilfe von ADO und SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="5c9be-108">Handling XML from an xml Type Column by Using ADO and SQL Server Native Client</span></span>  
 <span data-ttu-id="5c9be-109">Damit mit MDAC-Komponenten auf Typen und Funktionen zugegriffen werden kann, die in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]eingeführt wurden, müssen Sie die „DataTypeCompatibility“-Initialisierungseigenschaft in der ADO-Verbindungszeichenfolge festlegen.</span><span class="sxs-lookup"><span data-stu-id="5c9be-109">To use MDAC components to access the types and features that were introduced in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], you must set the DataTypeCompatibility initialization property in the ADO connection string.</span></span>  
  
 <span data-ttu-id="5c9be-110">Im folgenden VBScript-Beispiel werden die Ergebnisse der Abfrage einer `xml`-Datentypspalte, `Demographics`, in der `Sales.Store`-Tabelle der `AdventureWorks2012`-Beispieldatenbank angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5c9be-110">For example, the following Visual Basic Scripting Edition (VBScript) sample shows the results of querying an `xml` data type column, `Demographics`, in the `Sales.Store` table of the `AdventureWorks2012` sample database.</span></span> <span data-ttu-id="5c9be-111">Die Abfrage sucht insbesondere nach dem Instanzwert dieser Spalte für die Zeile, in der die `CustomerID` gleich dem Wert `3`ist.</span><span class="sxs-lookup"><span data-stu-id="5c9be-111">Specifically, the query looks for the instance value of this column for the row where the `CustomerID` is equal to `3`.</span></span>  
  
```  
Const DS = "MyServer"  
Const DB = "AdventureWorks2012"  
  
Set objConn = CreateObject("ADODB.Connection")  
Set objRs = CreateObject("ADODB.Recordset")  
  
CommandText = "SELECT Demographics" & _  
              " FROM Sales.Store" & _  
              " INNER JOIN Sales.Customer" & _  
              " ON Sales.Store.BusinessEntityID = sales.customer.StoreID" & _  
              " WHERE Sales.Customer.CustomerID = 3" & _  
              " OR Sales.Customer.CustomerID = 4"  
  
ConnectionString = "Provider=SQLNCLI11" & _  
                   ";Data Source=" & DS & _  
                   ";Initial Catalog=" & DB & _  
                   ";Integrated Security=SSPI;" & _  
                   "DataTypeCompatibility=80"  
  
'Connect to the data source.  
objConn.Open ConnectionString  
  
'Execute command through the connection and display  
Set objRs = objConn.Execute(CommandText)  
  
Dim rowcount  
rowcount = 0  
Do While Not objRs.EOF  
   rowcount = rowcount + 1  
   MsgBox "Row " & rowcount & _  
           vbCrLf & vbCrLf & objRs(0)  
   objRs.MoveNext  
Loop  
  
'Clean up.  
objRs.Close  
objConn.Close  
Set objRs = Nothing  
Set objConn = Nothing  
```  
  
 <span data-ttu-id="5c9be-112">In diesem Beispiel wird dargestellt, wie die Datentyp-Kompatibilitätseigenschaft festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="5c9be-112">This example shows how to set the data type compatibility property.</span></span> <span data-ttu-id="5c9be-113">Sie ist standardmäßig auf 0 (null) festgelegt, wenn Sie [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client verwenden.</span><span class="sxs-lookup"><span data-stu-id="5c9be-113">By default, this is set to 0 when you are using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span></span> <span data-ttu-id="5c9be-114">Wenn Sie den Wert auf 80 festgelegt haben, sorgt der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-Anbieter dafür, dass `xml`-Spalten und Spalten eines benutzerdefinierten Typs als [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)]-Datentypen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="5c9be-114">If you set the value to 80, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client provider will make `xml` and user-defined type columns appear as [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] data types.</span></span> <span data-ttu-id="5c9be-115">Dabei handelt es sich um DBTYPE_WSTR und DBTYPE_BYTES.</span><span class="sxs-lookup"><span data-stu-id="5c9be-115">This would be DBTYPE_WSTR and DBTYPE_BYTES, respectively.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="5c9be-116">Native Client muss ebenfalls auf dem Clientcomputer installiert und in der Verbindungszeichenfolge mit „`Provider=SQLNCLI11;...`“ zur Verwendung als Datenanbieter angegeben sein.</span><span class="sxs-lookup"><span data-stu-id="5c9be-116">Native Client must also be installed on the client computer and the connection string must specify it for use as the data provider with "`Provider=SQLNCLI11;...`".</span></span>  
  
#### <a name="to-test-this-example"></a><span data-ttu-id="5c9be-117">So testen Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="5c9be-117">To test this example</span></span>  
  
1.  <span data-ttu-id="5c9be-118">Prüfen Sie, ob [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client installiert ist und ob MDAC 2.6.0 oder höher auf dem Clientcomputer zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="5c9be-118">Verify that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client is installed and that MDAC 2.6.0or later is available on the client computer.</span></span>  
  
     <span data-ttu-id="5c9be-119">Weitere Informationen finden Sie unter [SQL Server Native Client-Programmierung](../native-client/sql-server-native-client-programming.md).</span><span class="sxs-lookup"><span data-stu-id="5c9be-119">For more information, see [SQL Server Native Client Programming](../native-client/sql-server-native-client-programming.md).</span></span>  
  
2.  <span data-ttu-id="5c9be-120">Prüfen Sie, ob die [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] -Beispieldatenbank in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installiert ist.</span><span class="sxs-lookup"><span data-stu-id="5c9be-120">Verify that the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed.</span></span>  
  
     <span data-ttu-id="5c9be-121">Für dieses Beispiel benötigen Sie die [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] -Beispieldatenbank.</span><span class="sxs-lookup"><span data-stu-id="5c9be-121">This example requires the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span>  
  
3.  <span data-ttu-id="5c9be-122">Kopieren Sie den weiter oben in diesem Thema dargestellten Code, und fügen Sie ihn in Ihren Text- oder Code-Editor ein.</span><span class="sxs-lookup"><span data-stu-id="5c9be-122">Copy the code shown previously in this topic and paste the code into your text or code editor.</span></span> <span data-ttu-id="5c9be-123">Speichern Sie die Datei unter dem Dateinamen HandlingXmlDataType.vbs.</span><span class="sxs-lookup"><span data-stu-id="5c9be-123">Save the file as HandlingXmlDataType.vbs.</span></span>  
  
4.  <span data-ttu-id="5c9be-124">Ändern Sie das Skript entsprechend Ihrer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Installation, und speichern Sie die Änderungen.</span><span class="sxs-lookup"><span data-stu-id="5c9be-124">Modify the script as required for your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation and save your changes.</span></span>  
  
     <span data-ttu-id="5c9be-125">Wenn z. B. `MyServer` angegeben ist, sollten Sie es durch `(local)` oder den tatsächlichen Namen des Servers ersetzen, auf dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installiert ist.</span><span class="sxs-lookup"><span data-stu-id="5c9be-125">For example, where `MyServer` is specified, you should replace it with either `(local)` or the actual name of the server on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed.</span></span>  
  
5.  <span data-ttu-id="5c9be-126">Führen Sie HandlingXmlDataType.vbs und das Skript aus.</span><span class="sxs-lookup"><span data-stu-id="5c9be-126">Run HandlingXmlDataType.vbs and execute the script.</span></span>  
  
 <span data-ttu-id="5c9be-127">Die Ergebnisse sollten ähnlich wie die folgende Beispielausgabe aussehen:</span><span class="sxs-lookup"><span data-stu-id="5c9be-127">The results should be similar to the following sample output:</span></span>  
  
```  
Row 1  
  
<StoreSurvey xmlns="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/StoreSurvey">  
  <AnnualSales>1500000</AnnualSales>  
  <AnnualRevenue>150000</AnnualRevenue>  
  <BankName>Primary International</BankName>  
  <BusinessType>OS</BusinessType>  
  <YearOpened>1974</YearOpened>  
  <Specialty>Road</Specialty>  
  <SquareFeet>38000</SquareFeet>  
  <Brands>3</Brands>  
  <Internet>DSL</Internet>  
  <NumberEmployees>40</NumberEmployees>  
</StoreSurvey>  
  
Row 2  
  
<StoreSurvey xmlns="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/StoreSurvey">  
  <AnnualSales>300000</AnnualSales>  
  <AnnualRevenue>30000</AnnualRevenue>  
  <BankName>United Security</BankName>  
  <BusinessType>BM</BusinessType>  
  <YearOpened>1976</YearOpened>  
  <Specialty>Road</Specialty>  
  <SquareFeet>6000</SquareFeet>  
  <Brands>2</Brands>  
  <Internet>DSL</Internet>  
  <NumberEmployees>5</NumberEmployees>  
</StoreSurvey>  
```  
  
## <a name="handling-xml-from-an-xml-type-column-by-using-adonet"></a><span data-ttu-id="5c9be-128">Verarbeiten von XML in einer Spalte vom Typ xml mithilfe von ADO.NET</span><span class="sxs-lookup"><span data-stu-id="5c9be-128">Handling XML from an xml Type Column by Using ADO.NET</span></span>  
 <span data-ttu-id="5c9be-129">Zum Verarbeiten von XML aus einer `xml` -Datentyp Spalte mithilfe von ADO.net und [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] können Sie das Standardverhalten der- `SqlCommand` Klasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="5c9be-129">To handle XML from an `xml` data type column by using ADO.NET and the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] you can use the standard behavior of the `SqlCommand` class.</span></span> <span data-ttu-id="5c9be-130">Eine `xml`-Datentypspalte und ihre Werte können z. B. mit einem `SqlDataReader` auf dieselbe Weise abgerufen werden wie eine beliebige SQL-Spalte. Wenn Sie jedoch mit dem Inhalt einer `xml`-Datentypspalte als XML arbeiten möchten, müssen Sie den Inhalt zunächst einem `XmlReader`-Typ zuweisen.</span><span class="sxs-lookup"><span data-stu-id="5c9be-130">For example, an `xml` data type column and its values can be retrieved in the same way any SQL column is retrieved by using a `SqlDataReader`.However, if you want to work with the contents of an `xml` data type column as XML, you will first have to assign the contents to an `XmlReader` type.</span></span>  
  
 <span data-ttu-id="5c9be-131">Weitere Informationen sowie einen Beispielcode finden Sie im Abschnitt über XML-Spaltenwerte in einem Datenleser in der [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnlong](../../includes/dnprdnlong-md.md)] SDK-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="5c9be-131">For more information and example code, see "XML Column Values in a Data Reader" in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnlong](../../includes/dnprdnlong-md.md)] SDK documentation.</span></span>  
  
## <a name="handling-an-xml-type-column-in-parameters-by-using-adonet"></a><span data-ttu-id="5c9be-132">Verarbeiten einer Spalte vom Typ xml in Parametern mithilfe von ADO.NET</span><span class="sxs-lookup"><span data-stu-id="5c9be-132">Handling an xml Type Column in Parameters by Using ADO.NET</span></span>  
 <span data-ttu-id="5c9be-133">Um einen xml-Datentyp, der als Parameter in ADO.NET und [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] übergeben wird, zu verarbeiten, können Sie den Wert als eine Instanz des `SqlXml`-Datentyps angeben.</span><span class="sxs-lookup"><span data-stu-id="5c9be-133">To handle an xml data type passed as a parameter in ADO.NET and the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], you can supply the value as an instance of the `SqlXml` data type.</span></span> <span data-ttu-id="5c9be-134">Es ist keine besondere Verarbeitung erforderlich, da die `xml`-Datentypspalten in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Parameterwerte auf dieselbe Weise annehmen können wie andere Spalten und Datentypen, z. B. `string` oder `integer`.</span><span class="sxs-lookup"><span data-stu-id="5c9be-134">No special handling is involved, because `xml` data type columns in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can accept parameter values in the same way as other columns and data types, such as `string` or `integer`.</span></span>  
  
 <span data-ttu-id="5c9be-135">Weitere Informationen sowie einen Beispielcode finden Sie im Abschnitt über XML-Werte als Befehlsparameter in der [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnlong](../../includes/dnprdnlong-md.md)] SDK-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="5c9be-135">For more information and example code, see "XML Values as Command Parameters" in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnlong](../../includes/dnprdnlong-md.md)] SDK documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c9be-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5c9be-136">See Also</span></span>  
 [<span data-ttu-id="5c9be-137">XML-Daten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5c9be-137">XML Data &#40;SQL Server&#41;</span></span>](xml-data-sql-server.md)  
  
  
