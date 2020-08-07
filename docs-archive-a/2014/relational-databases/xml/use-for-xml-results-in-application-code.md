---
title: Verwenden von FOR XML-Ergebnissen in Anwendungscode | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML clause, application code usage
- XML [SQL Server], FOR XML clause
- ASP.NET [SQL Server]
- .NET Framework [SQL Server], FOR XML data
- ADO [SQL Server]
- XML data islands [SQL Server]
- data islands [SQL Server]
ms.assetid: 41ae67bd-ece9-49ea-8062-c8d658ab4154
author: rothja
ms.author: jroth
ms.openlocfilehash: 3cabe7e65cb53a28a370615ed84e38ba2b8db44c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621385"
---
# <a name="use-for-xml-results-in-application-code"></a><span data-ttu-id="58d88-102">Verwenden von FOR XML-Ergebnissen in Anwendungscode</span><span class="sxs-lookup"><span data-stu-id="58d88-102">Use FOR XML Results in Application Code</span></span>
  <span data-ttu-id="58d88-103">Mithilfe von FOR XML-Klauseln in SWL-Abfragen können Sie Abfrageergebnisse abrufen und sogar in XML-Daten umwandeln.</span><span class="sxs-lookup"><span data-stu-id="58d88-103">By using FOR XML clauses with SQL queries, you can retrieve and even cast query results as XML data.</span></span> <span data-ttu-id="58d88-104">Diese Funktionalität bietet Ihnen die folgenden Möglichkeiten, wenn FOR XML-Abfrageergebnisse in XML-Anwendungscode verwendet werden können:</span><span class="sxs-lookup"><span data-stu-id="58d88-104">This functionality allows you to do the following when FOR XML query results can be used in XML application code:</span></span>  
  
-   <span data-ttu-id="58d88-105">Abfragen von SQL-Tabellen für Instanzen von Werten von [XML-Daten&#40;SQL Server&#41;](xml-data-sql-server.md)</span><span class="sxs-lookup"><span data-stu-id="58d88-105">Query SQL tables for instances of [XML Data &#40;SQL Server&#41;](xml-data-sql-server.md) values</span></span>  
  
-   <span data-ttu-id="58d88-106">Wenden Sie die [TYPE Directive in FOR XML Queries](type-directive-in-for-xml-queries.md) an, um das Ergebnis von Abfragen zurückzugeben, die typisierte Text- oder Imagedaten als XML enthalten.</span><span class="sxs-lookup"><span data-stu-id="58d88-106">Apply the [TYPE Directive in FOR XML Queries](type-directive-in-for-xml-queries.md) to return the result of queries that contain text or image typed data as XML</span></span>  
  
 <span data-ttu-id="58d88-107">Dieses Thema enthält Beispiele und veranschaulicht diese Vorgehensweisen.</span><span class="sxs-lookup"><span data-stu-id="58d88-107">This topic provides examples that demonstrate these approaches.</span></span>  
  
## <a name="retrieving-for-xml-data-with-ado-and-xml-data-islands"></a><span data-ttu-id="58d88-108">Abrufen von FOR XML-Daten mit ADO und XML-Dateninseln</span><span class="sxs-lookup"><span data-stu-id="58d88-108">Retrieving FOR XML Data with ADO and XML Data Islands</span></span>  
 <span data-ttu-id="58d88-109">Beim Arbeiten mit FOR XML-Abfragen kann das ADO-Objekt `Stream` oder andere Objekte, die die `IStream`-COM-Schnittstelle unterstützen, wie z. B. die ASP-Objekte (Active Server Pages) `Request` und `Response`, zum Aufnehmen der Ergebnisse verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="58d88-109">The ADO `Stream` object or other objects that support the COM `IStream` interface, such as the Active Server Pages (ASP) `Request` and `Response` objects, can be used to contain the results when you are working with FOR XML queries.</span></span>  
  
 <span data-ttu-id="58d88-110">Der folgende ASP-Code zeigt z. B. die Ergebnisse der Abfrage der `xml`-Datentypspalte Demographics in der Sales.Store-Tabelle der AdventureWorks-Beispieldatenbank.</span><span class="sxs-lookup"><span data-stu-id="58d88-110">For example, the following ASP code shows the results of querying an `xml` data type column, Demographics, in the Sales.Store table of the AdventureWorks sample database.</span></span> <span data-ttu-id="58d88-111">Insbesondere sucht die Abfrage nach dem Instanzwert dieser Spalte für die Zeile, in der die CustomerID gleich 3 ist.</span><span class="sxs-lookup"><span data-stu-id="58d88-111">Specifically, the query looks for the instance value of this column for the row where the CustomerID is equal to 3.</span></span>  
  
```  
<!-- BeginRecordAndStreamVBS -->  
<%@ LANGUAGE = VBScript %>  
<!-- %  Option Explicit      % -->  
<!-- 'Request.ServerVariables("SERVER_NAME") & ";" & _ -->  
<HTML>  
<HEAD>  
<META NAME="GENERATOR" Content="Microsoft Developer Studio"/>  
<META HTTP-EQUIV="Content-Type" content="text/html"; charset="iso-8859-1">  
<TITLE>FOR XML Query Example</TITLE>  
<STYLE>  
   BODY  
   {  
      FONT-FAMILY: Tahoma;  
      FONT-SIZE: 8pt;  
      OVERFLOW: auto  
   }  
   H3  
   {  
      FONT-FAMILY: Tahoma;  
      FONT-SIZE: 8pt;  
      OVERFLOW: auto  
   }  
</STYLE>  
  
<!-- #include file="adovbs.inc" -->  
<%  
   Response.Write "<H3>Server-side processing</H3>"  
   Response.Write "Page Generated @ " & Now() & "<BR/>"  
   Dim adoConn  
   Set adoConn = Server.CreateObject("ADODB.Connection")  
   Dim sConn  
   sConn = "Provider=SQLOLEDB;Data Source=(local);" & _  
            "Initial Catalog=AdventureWorks;Integrated Security=SSPI;"  
   Response.write "Connect String = " & sConn & "<BR/>"  
   adoConn.ConnectionString = sConn  
   adoConn.CursorLocation = adUseClient  
   adoConn.Open  
   Response.write "ADO Version = " & adoConn.Version & "<BR/>"  
   Response.write "adoConn.State = " & adoConn.State & "<BR/>"  
   Dim adoCmd  
   Set adoCmd = Server.CreateObject("ADODB.Command")  
   Set adoCmd.ActiveConnection = adoConn  
   Dim sQuery  
   sQuery = "<ROOT xmlns:sql='urn:schemas-microsoft-com:xml-sql'><sql:query>SELECT Demographics from Sales.Store WHERE CustomerID = 3 FOR XML AUTO</sql:query></ROOT>"  
   Response.write "Query String = " & sQuery & "<BR/>"  
   Dim adoStreamQuery  
   Set adoStreamQuery = Server.CreateObject("ADODB.Stream")  
   adoStreamQuery.Open  
   adoStreamQuery.WriteText sQuery, adWriteChar  
   adoStreamQuery.Position = 0  
   adoCmd.CommandStream = adoStreamQuery  
   adoCmd.Dialect = "{5D531CB2-E6Ed-11D2-B252-00C04F681B71}"  
   Response.write "Pushing XML to client for processing "  & "<BR/>"  
   adoCmd.Properties("Output Stream") = Response  
   Response.write "<XML ID='MyDataIsle'>"  
   adoCmd.Execute , , 1024  
   Response.write "</XML>"  
%>  
<SCRIPT language="VBScript" For="window" Event="onload">  
   Dim xmlDoc  
   Set xmlDoc = MyDataIsle.XMLDocument  
   Dim root  
   Set root = xmlDoc.documentElement.childNodes.Item(0).childNodes.Item(0).childNodes.Item(0)  
   For each child in root.childNodes  
      dim OutputXML  
      OutputXML = document.all("log").innerHTML  
      document.all("log").innerHTML = OutputXML & "<LI><B>" & child.nodeName &  ":</B>  " & child.Text  & "</LI>"  
   Next  
   MsgBox xmlDoc.xml  
</SCRIPT>  
</HEAD>  
<BODY>  
   <H3>Client-side processing of XML Document MyDataIsle</H3>  
   <UL id=log>  
   </UL>  
</BODY>  
</HTML>  
<!-- EndRecordAndStreamVBS -->  
```  
  
 <span data-ttu-id="58d88-112">Diese ASP-Beispielseite enthält serverseitiges VBScript, das ADO zum Ausführen der FOR XML-Abfrage und zum Zurückgeben der XML-Ergebnisse in einer XML-Dateninsel (MyDataIsle) verwendet.</span><span class="sxs-lookup"><span data-stu-id="58d88-112">This example ASP page contains server-side VBScript that uses ADO to execute the FOR XML query and return the XML results in an XML data island, MyDataIsle.</span></span> <span data-ttu-id="58d88-113">Diese XML-Dateninsel wird dann an den Browser zurückgegeben und zur weiteren clientseitigen Verarbeitung bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="58d88-113">This XML data island is then returned in the browser for additional client-side processing.</span></span> <span data-ttu-id="58d88-114">Anschließend wird zusätzlicher clientseitiger VBScript-Code verwendet, um den Inhalt der XML-Dateninsel zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="58d88-114">Additional client-side VBScript code is then used to process the contents of the XML data island.</span></span> <span data-ttu-id="58d88-115">Dieser Vorgang wird durchgeführt, bevor der Inhalt als Teil des resultierenden DHTML-Codes angezeigt und ein Meldungsfeld geöffnet wird, das den vorverarbeiteten Inhalt der XML-Dateninsel zeigt.</span><span class="sxs-lookup"><span data-stu-id="58d88-115">This process is performed before displaying the contents as part of the resultant DHTML and opening a message box to show the preprocessed contents of the XML data island.</span></span>  
  
#### <a name="to-test-this-example"></a><span data-ttu-id="58d88-116">So testen Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="58d88-116">To test this example</span></span>  
  
1.  <span data-ttu-id="58d88-117">Überprüfen Sie, dass IIS installiert ist und dass die AdventureWorks-Beispieldatenbank für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="58d88-117">Verify that IIS is installed and that the AdventureWorks sample database for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has been installed.</span></span>  
  
     <span data-ttu-id="58d88-118">Für dieses Beispiel ist es erforderlich, dass Internet Information Services (IIS) Version 5.0 oder höher installiert und die ASP-Unterstützung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="58d88-118">This example requires that Internet Information Services (IIS) version 5.0, or later versions, are installed with ASP support enabled.</span></span> <span data-ttu-id="58d88-119">Außerdem muss die AdventureWorks-Beispieldatenbank installiert sein.</span><span class="sxs-lookup"><span data-stu-id="58d88-119">Also, the AdventureWorks sample database has to be installed.</span></span>  
  
2.  <span data-ttu-id="58d88-120">Kopieren Sie das zuvor bereitgestellte Codebeispiel, und fügen Sie es in den von Ihnen verwendeten XML- oder Texteditor ein.</span><span class="sxs-lookup"><span data-stu-id="58d88-120">Copy the code example that was previously provided and paste it into the XML or text editor that you use.</span></span> <span data-ttu-id="58d88-121">Speichern Sie die Datei als RetrieveResults.asp im Stammverzeichnis, das für IIS verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="58d88-121">Save the file as RetrieveResults.asp in the root directory that is used for IIS.</span></span> <span data-ttu-id="58d88-122">Üblicherweise ist das C:Inetpub\wwwroot.</span><span class="sxs-lookup"><span data-stu-id="58d88-122">Typically, this is C:Inetpub\wwwroot.</span></span>  
  
3.  <span data-ttu-id="58d88-123">Öffnen Sie die ASP-Seite in einem Browserfenster, indem Sie die folgende URL verwenden.</span><span class="sxs-lookup"><span data-stu-id="58d88-123">Open the ASP page in a browser window by using the following URL.</span></span> <span data-ttu-id="58d88-124">Ersetzen Sie zunächst 'MyServer' entweder durch "localhost" oder durch den tatsächlichen Namen des Servers, auf dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] und IIS installiert sind.</span><span class="sxs-lookup"><span data-stu-id="58d88-124">First, replace 'MyServer' with either "localhost" or the actual name of the server where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and IIS are installed.</span></span>  
  
    ```  
    http://MyServer/RetrieveResults.asp  
    ```  
  
 <span data-ttu-id="58d88-125">Die generierten HTML-Seitenergebnisse, die angezeigt werden, ähneln der folgenden Beispielausgabe:</span><span class="sxs-lookup"><span data-stu-id="58d88-125">The generated HTML page results that appear will be similar to the following sample output:</span></span>  
  
##### <a name="server-side-processing"></a><span data-ttu-id="58d88-126">Serverseitiges Verarbeiten</span><span class="sxs-lookup"><span data-stu-id="58d88-126">Server-side processing</span></span>  
 <span data-ttu-id="58d88-127">Page Generated \@ 3/11/2006 3:36:02 PM</span><span class="sxs-lookup"><span data-stu-id="58d88-127">Page Generated \@ 3/11/2006 3:36:02 PM</span></span>  
  
 <span data-ttu-id="58d88-128">Connect String = Provider=SQLOLEDB;Data Source=MyServer;Initial Catalog=AdventureWorks;Integrated Security=SSPI;</span><span class="sxs-lookup"><span data-stu-id="58d88-128">Connect String = Provider=SQLOLEDB;Data Source=MyServer;Initial Catalog=AdventureWorks;Integrated Security=SSPI;</span></span>  
  
 <span data-ttu-id="58d88-129">ADO Version = 2.8</span><span class="sxs-lookup"><span data-stu-id="58d88-129">ADO Version = 2.8</span></span>  
  
 <span data-ttu-id="58d88-130">adoConn.State = 1</span><span class="sxs-lookup"><span data-stu-id="58d88-130">adoConn.State = 1</span></span>  
  
 <span data-ttu-id="58d88-131">Query String = SELECT Demographics from Sales.Store WHERE CustomerID = 3 FOR XML AUTO</span><span class="sxs-lookup"><span data-stu-id="58d88-131">Query String = SELECT Demographics from Sales.Store WHERE CustomerID = 3 FOR XML AUTO</span></span>  
  
 <span data-ttu-id="58d88-132">Pushen von XML an Client zum Verarbeiten</span><span class="sxs-lookup"><span data-stu-id="58d88-132">Pushing XML to client for processing</span></span>  
  
##### <a name="client-side-processing-of-xml-document-mydataisle"></a><span data-ttu-id="58d88-133">Clientseitiges Verarbeiten von XML-Dokument MyDataIsle</span><span class="sxs-lookup"><span data-stu-id="58d88-133">Client-side processing of XML Document MyDataIsle</span></span>  
  
-   <span data-ttu-id="58d88-134">**AnnualSales:** 1.500.000</span><span class="sxs-lookup"><span data-stu-id="58d88-134">**AnnualSales:** 1500000</span></span>  
  
-   <span data-ttu-id="58d88-135">**AnnualRevenue:** 150.000</span><span class="sxs-lookup"><span data-stu-id="58d88-135">**AnnualRevenue:** 150000</span></span>  
  
-   <span data-ttu-id="58d88-136">**BankName:** Primary International</span><span class="sxs-lookup"><span data-stu-id="58d88-136">**BankName:** Primary International</span></span>  
  
-   <span data-ttu-id="58d88-137">**BusinessType:** OS</span><span class="sxs-lookup"><span data-stu-id="58d88-137">**BusinessType:** OS</span></span>  
  
-   <span data-ttu-id="58d88-138">**YearOpened:** 1974</span><span class="sxs-lookup"><span data-stu-id="58d88-138">**YearOpened:** 1974</span></span>  
  
-   <span data-ttu-id="58d88-139">**Specialty:** Straße</span><span class="sxs-lookup"><span data-stu-id="58d88-139">**Specialty:** Road</span></span>  
  
-   <span data-ttu-id="58d88-140">**SquareFeet:** 38.000</span><span class="sxs-lookup"><span data-stu-id="58d88-140">**SquareFeet:** 38000</span></span>  
  
-   <span data-ttu-id="58d88-141">**Brands:** 3</span><span class="sxs-lookup"><span data-stu-id="58d88-141">**Brands:** 3</span></span>  
  
-   <span data-ttu-id="58d88-142">**Internet:** DSL</span><span class="sxs-lookup"><span data-stu-id="58d88-142">**Internet:** DSL</span></span>  
  
-   <span data-ttu-id="58d88-143">**NumberEmployees:** 40</span><span class="sxs-lookup"><span data-stu-id="58d88-143">**NumberEmployees:** 40</span></span>  
  
 <span data-ttu-id="58d88-144">Das VBScript-Meldungsfeld zeigt dann den folgenden ursprünglichen, ungefilterten Inhalt der XML-Dateninsel, der durch die Ergebnisse der FOR XML-Abfrage zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="58d88-144">The VBScript message box will then show the following original, unfiltered XML data island contents that were returned by the FOR XML query results.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Sales.Store>  
    <Demographics>  
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
    </Demographics>  
  </Sales.Store>  
</ROOT>  
```  
  
## <a name="retrieving-for-xml-data-with-aspnet-and-the-net-framework"></a><span data-ttu-id="58d88-145">Abrufen der FOR XML-Daten mit ASP.NET und .Net Framework</span><span class="sxs-lookup"><span data-stu-id="58d88-145">Retrieving FOR XML Data with ASP.NET and the .NET Framework</span></span>  
 <span data-ttu-id="58d88-146">Wie im vorherigen Beispiel zeigt auch der folgende ASP-Code die Ergebnisse der Abfrage der `xml`-Datentypspalte Demographics in der Sales.Store-Tabelle der AdventureWorks-Beispieldatenbank.</span><span class="sxs-lookup"><span data-stu-id="58d88-146">As in the previous example, the following ASP.NET code shows the results of querying an `xml` data type column, Demographics, in the Sales.Store table of the AdventureWorks sample database.</span></span> <span data-ttu-id="58d88-147">Und wie im vorherigen Beispiel sucht die Abfrage nach dem Instanzwert dieser Spalte für die Zeile, in der die CustomerID gleich 3 ist.</span><span class="sxs-lookup"><span data-stu-id="58d88-147">As in the previous example, the query looks for the instance value of this column for the row where the CustomerID is equal to 3.</span></span>  
  
 <span data-ttu-id="58d88-148">In diesem Beispiel werden jedoch die folgenden verwalteten APIs von Microsoft .NET Framework verwendet, um das Zurückgeben und das Rendering der Ergebnisse der FOR XML-Abfrage zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="58d88-148">In this example, the following Microsoft .NET Framework managed APIs are used to accomplish the return and rendering of the FOR XML query results:</span></span>  
  
1.  <span data-ttu-id="58d88-149">`SqlConnection` wird verwendet, um basierend auf dem Inhalt einer angegebenen Verbindungszeichenfolgenvariablen stConn eine Verbindung mit SQL Server zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="58d88-149">`SqlConnection` is used to open a connection to SQL Server, based on the contents of a specified connection string variable, strConn.</span></span>  
  
2.  <span data-ttu-id="58d88-150">`SqlDataAdapter` wird dann als Datenadapter verwendet, und es verwendet die SQL-Verbindung und eine angegebene SQL-Abfragezeichenfolge, um die FOR XML-Abfrage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="58d88-150">`SqlDataAdapter` is then used as the data adapter and it uses the SQL connection and a specified SQL query string to execute the FOR XML query.</span></span>  
  
3.  <span data-ttu-id="58d88-151">Nach dem Ausführen der Abfrage wird die `SqlDataAdapter.Fill`-Methode aufgerufen und an eine Instanz eines `DataSet,` MyDataSet übergeben, um das Dataset mit der Ausgabe der FOR XML-Abfrage zu füllen.</span><span class="sxs-lookup"><span data-stu-id="58d88-151">After the query has executed, the `SqlDataAdapter.Fill` method is then called and passed an instance of a `DataSet,` MyDataSet, in order to fill the data set with the output of the FOR XML query.</span></span>  
  
4.  <span data-ttu-id="58d88-152">Anschließend wird die `DataSet.GetXml`-Methode aufgerufen, um die Abfrageergebnisse als eine Zeichenfolge zurückzugeben, die in der vom Server generierten HTML-Seite angezeigt werden kann.</span><span class="sxs-lookup"><span data-stu-id="58d88-152">The `DataSet.GetXml` method is then called to return the query results as a string that can be displayed in the server-generated HTML page.</span></span>  
  
    ```  
    <%@ Page Language="VB" %>  
    <HTML>  
    <HEAD>  
    <TITLE>FOR XML Query Example</TITLE>  
    <STYLE>  
       BODY  
       {  
          FONT-FAMILY: Tahoma;  
          FONT-SIZE: 8pt;  
          OVERFLOW: auto  
       }  
       H3  
       {  
          FONT-FAMILY: Tahoma;  
          FONT-SIZE: 8pt;  
          OVERFLOW: auto  
       }  
    </STYLE>  
    </HEAD>  
    <BODY>  
    <%  
    Dim s as String  
    s = "<H3>Server-side processing</H3>" & _  
        "Page Generated @ " & Now() & "<BR/>"  
  
    Dim SQL As String   
    SQL = "SELECT Demographics from Sales.Store WHERE CustomerID = 3 FOR XML AUTO"  
  
    Dim strConn As String   
    strConn = "Server=(local);Database=AdventureWorks;Integrated Security=SSPI;"  
  
    Dim MySqlConn As New System.Data.SqlClient.SqlConnection(strConn)  
    Dim MySqlAdapter As New System.Data.SqlClient.SqlDataAdapter(SQL,MySqlConn)  
    Dim MyDataSet As New System.Data.DataSet  
  
    MySqlConn.Open()  
    s = s & "<P>SqlConnection opened.</P>"   
  
    MySqlAdapter.Fill(MyDataSet)  
    s = s & "<P>" & MyDataSet.GetXml  & "</P>"  
  
    MySqlConn.Close()  
    s = s & "<P>SqlConnection closed.</P>"   
  
    Message.InnerHtml=s  
    %>  
    <SPAN id="Message" runat=server />  
    </BODY>  
    </HTML>  
    ```  
  
#### <a name="to-test-this-example"></a><span data-ttu-id="58d88-153">So testen Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="58d88-153">To test this example</span></span>  
  
1.  <span data-ttu-id="58d88-154">Überprüfen Sie, dass IIS installiert ist und dass die AdventureWorks-Beispieldatenbank für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="58d88-154">Verify that IIS is installed and that the AdventureWorks sample database for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has been installed.</span></span>  
  
     <span data-ttu-id="58d88-155">Für dieses Beispiel ist es erforderlich, dass Internet Information Services (IIS) Version 5.0 oder höher installiert und die ASP.NET-Unterstützung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="58d88-155">This example requires that Internet Information Services (IIS) version 5.0, or later versions, are installed with ASP.NET support enabled.</span></span> <span data-ttu-id="58d88-156">Außerdem muss die AdventureWorks-Beispieldatenbank installiert sein.</span><span class="sxs-lookup"><span data-stu-id="58d88-156">Also, the AdventureWorks sample database has to be installed.</span></span>  
  
2.  <span data-ttu-id="58d88-157">Kopieren Sie den zuvor bereitgestellten Code, und fügen Sie ihn in den von Ihnen verwendeten XML- oder Texteditor ein.</span><span class="sxs-lookup"><span data-stu-id="58d88-157">Copy the code that was previously provided and paste it into the XML or text editor that you use.</span></span> <span data-ttu-id="58d88-158">Speichern Sie die Datei als RetrieveResults.aspx im Stammverzeichnis, das für IIS verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="58d88-158">Save the file as RetrieveResults.aspx in the root directory used for IIS.</span></span> <span data-ttu-id="58d88-159">Üblicherweise ist das C:Inetpub\wwwroot.</span><span class="sxs-lookup"><span data-stu-id="58d88-159">Typically, this is C:Inetpub\wwwroot.</span></span>  
  
3.  <span data-ttu-id="58d88-160">Öffnen Sie die ASP.NET-Seite in einem Browserfenster, indem Sie die folgende URL verwenden.</span><span class="sxs-lookup"><span data-stu-id="58d88-160">Open the ASP.NET page in a browser window using the following URL.</span></span> <span data-ttu-id="58d88-161">Ersetzen Sie zunächst 'MyServer' entweder durch "localhost" oder durch den tatsächlichen Namen des Servers, auf dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] und IIS installiert sind.</span><span class="sxs-lookup"><span data-stu-id="58d88-161">First, replace 'MyServer' with either "localhost" or the actual name of the server where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and IIS are installed.</span></span>  
  
    ```  
    http://MyServer/RetrieveResults.aspx  
    ```  
  
 <span data-ttu-id="58d88-162">Die generierten HTML-Seitenergebnisse, die angezeigt werden, ähneln der folgenden Beispielausgabe:</span><span class="sxs-lookup"><span data-stu-id="58d88-162">The generated HTML page results that appear will be similar to the following sample output:</span></span>  
  
##### <a name="server-side-processing"></a><span data-ttu-id="58d88-163">Serverseitiges Verarbeiten</span><span class="sxs-lookup"><span data-stu-id="58d88-163">Server-side processing</span></span>  
  
```  
Page Generated @ 3/11/2006 3:36:02 PM  
  
SqlConnection opened.  
  
<Sales.Store><Demographics><StoreSurvey xmlns="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/StoreSurvey"><AnnualSales>1500000</AnnualSales><AnnualRevenue>150000</AnnualRevenue><BankName>Primary International</BankName><BusinessType>OS</BusinessType><YearOpened>1974</YearOpened><Specialty>Road</Specialty><SquareFeet>38000</SquareFeet><Brands>3</Brands><Internet>DSL</Internet><NumberEmployees>40</NumberEmployees></StoreSurvey></Demographics></Sales.Store>  
  
SqlConnection closed.  
```  
  
> [!NOTE]  
>  <span data-ttu-id="58d88-164">Mithilfe der- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `xml` Datentyp Unterstützung können Sie anfordern, dass das Ergebnis einer for XML-Abfrage als-Datentyp zurückgegeben wird `xml` , anstatt als Zeichen folgen-oder Image typisierte Daten, indem Sie die [Type-Direktive](type-directive-in-for-xml-queries.md)angeben.</span><span class="sxs-lookup"><span data-stu-id="58d88-164">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]`xml` data type support lets you request that the result of a FOR XML query be returned as `xml` data type, instead of as string or image typed data, by specifying the [TYPE directive](type-directive-in-for-xml-queries.md).</span></span> <span data-ttu-id="58d88-165">Wenn die TYPE-Direktive in FOR XML-Abfragen verwendet wird, ermöglicht sie den programmgesteuerten Zugriff auf die FOR XML-Ergebnisse, wie das auch in [Verwenden von XML-Daten in Anwendungen](use-xml-data-in-applications.md)gezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="58d88-165">When the TYPE directive is used in FOR XML queries, it provides programmatic access to the FOR XML results similar to that shown in [Use XML Data in Applications](use-xml-data-in-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58d88-166">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="58d88-166">See Also</span></span>  
 [<span data-ttu-id="58d88-167">FOR XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="58d88-167">FOR XML &#40;SQL Server&#41;</span></span>](for-xml-sql-server.md)  
  
  
