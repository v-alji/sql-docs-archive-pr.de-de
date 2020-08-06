---
title: XML-Abfragesyntax für XML-Berichtsdaten (SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- namespaces [Reporting Services]
- data processing extensions [Reporting Services], data sources
- xmldp [Reporting Services]
- XML [Reporting Services], data retrieval
ms.assetid: d203886f-faa1-4a02-88f5-dd4c217181ef
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 62dde2b3ab18b5edb5c3786d39173fea3a0854ac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608307"
---
# <a name="xml-query-syntax-for-xml-report-data-ssrs"></a><span data-ttu-id="1ef87-102">XML-Abfragesyntax für XML-Berichtsdaten (SSRS)</span><span class="sxs-lookup"><span data-stu-id="1ef87-102">XML Query Syntax for XML Report Data (SSRS)</span></span>
  <span data-ttu-id="1ef87-103">In [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]können Sie Datasets für XML-Datenquellen erstellen.</span><span class="sxs-lookup"><span data-stu-id="1ef87-103">In [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you can create datasets for XML data sources.</span></span> <span data-ttu-id="1ef87-104">Wenn Sie eine Datenquelle definiert haben, erstellen Sie eine Abfrage für das Dataset.</span><span class="sxs-lookup"><span data-stu-id="1ef87-104">After you define a data source, you create a query for the dataset.</span></span> <span data-ttu-id="1ef87-105">Je nach Typ der XML-Daten, auf die die Datenquelle zeigt, können Sie die Datasetabfrage erstellen, indem Sie eine XML-`Query` oder einen Elementpfad einfügen.</span><span class="sxs-lookup"><span data-stu-id="1ef87-105">Depending on the type of XML data pointed to by the data source, you create the dataset query by including an XML `Query` or an element path.</span></span> <span data-ttu-id="1ef87-106">Ein XML `Query` -Code beginnt mit einem **\<Query>** -Tag und enthält Namespaces und XML-Elemente, die je nach Datenquelle variieren.</span><span class="sxs-lookup"><span data-stu-id="1ef87-106">An XML `Query` starts with a **\<Query>** tag and includes namespaces and XML elements that vary depending on the data source.</span></span> <span data-ttu-id="1ef87-107">Ein Elementpfad ist von Namespaces unabhängig und gibt die Knoten und Knotenattribute in den zugrunde liegenden XML-Daten an, die mit der XPath-ähnlichen Syntax verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1ef87-107">An element path is namespace-independent and specifies which nodes and node attributes to use from the underlying XML data with an XPath-like syntax.</span></span> <span data-ttu-id="1ef87-108">Weitere Informationen zu Elementpfaden finden Sie unter [Syntax für Elementpfade für XML-Berichtsdaten (SSRS)](report-data-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="1ef87-108">For more information about element paths, see [Element Path Syntax for XML Report Data &#40;SSRS&#41;](report-data-ssrs.md).</span></span>  
  
 <span data-ttu-id="1ef87-109">Sie können eine XML-Datenquelle für die folgenden Typen von XML-Daten erstellen:</span><span class="sxs-lookup"><span data-stu-id="1ef87-109">You can create an XML data source for the following types of XML data:</span></span>  
  
-   <span data-ttu-id="1ef87-110">XML-Dokumente, auf die eine URL über HTTP zeigt</span><span class="sxs-lookup"><span data-stu-id="1ef87-110">Xml documents pointed to by a URL using http protocol</span></span>  
  
-   <span data-ttu-id="1ef87-111">Webdienst-Endpunkte, die XML-Daten zurückgeben</span><span class="sxs-lookup"><span data-stu-id="1ef87-111">Web service endpoints that return XML data</span></span>  
  
-   <span data-ttu-id="1ef87-112">Eingebettete XML-Daten</span><span class="sxs-lookup"><span data-stu-id="1ef87-112">Embedded XML data</span></span>  
  
 <span data-ttu-id="1ef87-113">Die Art, wie Sie eine XML-`Query` oder einen Elementpfad angeben, ist vom Typ der XML-Daten abhängig.</span><span class="sxs-lookup"><span data-stu-id="1ef87-113">How you specify an XML `Query` or an element path depends on the type of XML data.</span></span>  
  
 <span data-ttu-id="1ef87-114">Bei einem XML-Dokument ist die XML-`Query` optional.</span><span class="sxs-lookup"><span data-stu-id="1ef87-114">For an XML document, the XML `Query` is optional.</span></span> <span data-ttu-id="1ef87-115">Wenn sie eingeschlossen wird, kann sie einen optionalen XML-`ElementPath` enthalten.</span><span class="sxs-lookup"><span data-stu-id="1ef87-115">If it is included, it can contain an optional XML `ElementPath`.</span></span> <span data-ttu-id="1ef87-116">Der Wert des XML-`ElementPath` verwendet die Syntax des Elementpfades.</span><span class="sxs-lookup"><span data-stu-id="1ef87-116">The value of the XML `ElementPath` uses the element path syntax.</span></span> <span data-ttu-id="1ef87-117">Sie schließen die XML-`Query` und den XML-`ElementPath` ein, um Namespaces ordnungsgemäß zu verarbeiten, wenn diese von den XML-Daten in der Datenquelle benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="1ef87-117">You include the XML `Query` and XML `ElementPath` to process namespaces correctly when it is needed by the XML data from the data source.</span></span>  
  
 <span data-ttu-id="1ef87-118">Für einen Webdienst-Endpunkt, auf den eine Verbindungszeichenfolgen-URL zeigt, definiert die XML-`Query` die Webdienstmethode, die SOAP-Aktion oder beide.</span><span class="sxs-lookup"><span data-stu-id="1ef87-118">For a Web service endpoint pointed to by a connection string URL, the XML `Query` defines either the Web service method, the SOAP action, or both.</span></span> <span data-ttu-id="1ef87-119">Der XML-Datenanbieter erstellt eine Webdienstanforderung, mit der XML-Daten abgerufen werden, die im Bericht verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1ef87-119">The XML data provider creates a Web service request that retrieves XML data to use for the report.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1ef87-120">Wenn ein Webdienst-Namespace ein Schrägstrichzeichen (`/)` enthält, fügen Sie die Webdienstmethode und die SOAP-Aktion ein, sodass die XML-Datenverarbeitungserweiterung den Namespace fehlerfrei ableiten kann.</span><span class="sxs-lookup"><span data-stu-id="1ef87-120">When a Web service namespace includes a forward slash (`/)` character, include both the Web service method and the SOAP action so that the XML data processing extension can derive the namespace correctly.</span></span>  
  
 <span data-ttu-id="1ef87-121">Für ein eingebettetes XML-Dokument definiert die XML-`Query` die zu verwendenden eingebetteten XML-Daten, außerdem enthält sie optionale Namespaces und einen optionalen XML-`ElementPath`.</span><span class="sxs-lookup"><span data-stu-id="1ef87-121">For an embedded XML document, the XML `Query` defines the embedded XML data to use, includes optional namespaces, and contains an optional XML `ElementPath`..</span></span>  
  
## <a name="specifying-query-parameters-for-xml-data"></a><span data-ttu-id="1ef87-122">Angeben von Abfrageparametern für XML-Daten</span><span class="sxs-lookup"><span data-stu-id="1ef87-122">Specifying Query Parameters for XML Data</span></span>  
 <span data-ttu-id="1ef87-123">Sie können Abfrageparameter für XML-Dokumente angeben.</span><span class="sxs-lookup"><span data-stu-id="1ef87-123">You can specify query parameters for XML documents.</span></span>  
  
-   <span data-ttu-id="1ef87-124">Bei URL-Anforderungen sind die Abfrageparameter als URL-Standardparameter enthalten.</span><span class="sxs-lookup"><span data-stu-id="1ef87-124">For URL requests, the query parameters are included as standard URL parameters.</span></span>  
  
-   <span data-ttu-id="1ef87-125">Bei Webdienstanforderungen werden Abfrageparameter an die Webdienstmethode übergeben.</span><span class="sxs-lookup"><span data-stu-id="1ef87-125">For Web service requests, query parameters are passed to the Web service method.</span></span> <span data-ttu-id="1ef87-126">Verwenden Sie zum Definieren eines Abfrageparameters im Dialogfeld **Dataseteigenschaften** die Seite **Parameter** .</span><span class="sxs-lookup"><span data-stu-id="1ef87-126">To define a query parameter, use the **Parameters** page of the **Dataset Properties** dialog box.</span></span> <span data-ttu-id="1ef87-127">Weitere Informationen finden Sie unter [Dataseteigenschaften (Dialogfeld), Parameter](dataset-properties-dialog-box-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="1ef87-127">For more information, see [Dataset Properties Dialog Box, Parameters](dataset-properties-dialog-box-parameters.md).</span></span>  
  
### <a name="example"></a><span data-ttu-id="1ef87-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1ef87-128">Example</span></span>  
 <span data-ttu-id="1ef87-129">Die Beispiele in der folgenden Tabelle veranschaulichen das Abrufen von Daten vom Berichtsserver-Webdienst, einem XML-Dokument und eingebetteten XML-Daten.</span><span class="sxs-lookup"><span data-stu-id="1ef87-129">The examples in the following table illustrate how to retrieve data from the Report Server Web service, an XML document, and embedded XML data.</span></span>  
  
|<span data-ttu-id="1ef87-130">XML-Datenquelle</span><span class="sxs-lookup"><span data-stu-id="1ef87-130">XML data source</span></span>|<span data-ttu-id="1ef87-131">Abfragebeispiel</span><span class="sxs-lookup"><span data-stu-id="1ef87-131">Query example</span></span>|  
|---------------------|-------------------|  
|<span data-ttu-id="1ef87-132">Webdienst-XML-Daten aus der ListChildren -Methode</span><span class="sxs-lookup"><span data-stu-id="1ef87-132">Web service XML data from ListChildren method.</span></span>|`<Query>`<br /><br /> `<Method Name="ListChildren" Namespace="https://schemas.microsoft.com/sqlserver/2005/06/30/reporting/reportingservices" />`<br /><br /> `</Query>`|  
|<span data-ttu-id="1ef87-133">Webdienst-XML-Daten von SoapAction.</span><span class="sxs-lookup"><span data-stu-id="1ef87-133">Web service XML data from SoapAction.</span></span>|`<Query xmlns=namespace>`<br /><br /> `<SoapAction>http://schemas/microsoft.com/sqlserver/2005/03/23/reporting/reportingservices/ListChildren</SoapAction>`<br /><br /> `</Query>`|  
|<span data-ttu-id="1ef87-134">XML-Dokument oder eingebettete XML-Daten, die Namespaces verwenden.</span><span class="sxs-lookup"><span data-stu-id="1ef87-134">XML Document or embedded XML data that uses namespaces.</span></span><br /><br /> <span data-ttu-id="1ef87-135">Abfrageelement, das Namespaces für einen Elementpfad angibt.</span><span class="sxs-lookup"><span data-stu-id="1ef87-135">Query element specifying namespaces for an element path.</span></span>|`<Query xmlns:es="https://schemas.microsoft.com/StandardSchemas/ExtendedSales">`<br /><br /> `<ElementPath>/Customers/Customer/Orders/Order/es:LineItems/es:LineItem</ElementPath>`<br /><br /> `</Query>`|  
|<span data-ttu-id="1ef87-136">Eingebettetes XML-Dokument.</span><span class="sxs-lookup"><span data-stu-id="1ef87-136">Embedded XML document.</span></span>|`<Query>`<br /><br /> `<XmlData>`<br /><br /> `<Customers>`<br /><br /> `<Customer ID="1">Bobby</Customer>`<br /><br /> `</Customers>`<br /><br /> `</XmlData>`<br /><br /> `<ElementPath>Customer {@}</ElementPath>`<br /><br /> `</Query>`|  
|<span data-ttu-id="1ef87-137">XML-Dokument, das Standardwerte verwendet.</span><span class="sxs-lookup"><span data-stu-id="1ef87-137">XML document that uses default.</span></span>|<span data-ttu-id="1ef87-138">*No query*.</span><span class="sxs-lookup"><span data-stu-id="1ef87-138">*No query*.</span></span><br /><br /> <span data-ttu-id="1ef87-139">Der Elementpfad wird vom XML-Dokument selbst abgeleitet und ist von Namespaces unabhängig.</span><span class="sxs-lookup"><span data-stu-id="1ef87-139">The element path is derived from the XML document itself and is namespace-independent.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="1ef87-140">Im ersten Webdienstbeispiel wird der Inhalt des Berichtsservers aufgeführt, der die <xref:ReportService2006.ReportingService2006.ListChildren%2A> -Methode</span><span class="sxs-lookup"><span data-stu-id="1ef87-140">The first Web service example lists the contents of the report server that uses the <xref:ReportService2006.ReportingService2006.ListChildren%2A> method.</span></span> <span data-ttu-id="1ef87-141">Diese Abfrage können Sie ausführen, indem Sie eine neue Datenquelle erstellen und die Verbindungszeichenfolge auf http://localhost/reportserver/reportservice2006.asmx festlegen.</span><span class="sxs-lookup"><span data-stu-id="1ef87-141">To run this query, you must create a new data source and set the connection string to http://localhost/reportserver/reportservice2006.asmx.</span></span> <span data-ttu-id="1ef87-142">Die <xref:ReportService2006.ReportingService2006.ListChildren%2A>-Methode nimmt zwei Parameter an: `Item` und `Recursive`.</span><span class="sxs-lookup"><span data-stu-id="1ef87-142">The <xref:ReportService2006.ReportingService2006.ListChildren%2A> method takes two parameters: `Item` and `Recursive`.</span></span> <span data-ttu-id="1ef87-143">Legen Sie den Standardwert für `Item` auf `/` und für `Recursive` auf `1` fest.</span><span class="sxs-lookup"><span data-stu-id="1ef87-143">Set the default value for `Item` to `/` and `Recursive` to `1`.</span></span>  
  
## <a name="specifying-namespaces"></a><span data-ttu-id="1ef87-144">Angeben von Namespaces</span><span class="sxs-lookup"><span data-stu-id="1ef87-144">Specifying Namespaces</span></span>  
 <span data-ttu-id="1ef87-145">Verwenden Sie das XML-`Query`-Element zum Angeben der in den XML-Daten der Datenquelle verwendeten Namespaces.</span><span class="sxs-lookup"><span data-stu-id="1ef87-145">Use the XML `Query` element to specify the namespaces that are used in the XML data from the data source.</span></span> <span data-ttu-id="1ef87-146">In der folgenden XML-Abfrage wird der Namespace `sales` verwendet.</span><span class="sxs-lookup"><span data-stu-id="1ef87-146">The following XML query uses the namespace `sales`.</span></span> <span data-ttu-id="1ef87-147">Die XML-`ElementPath`-Knoten für `sales:LineItems` und `sales:LineItem` verwenden den Namespace `sales`.</span><span class="sxs-lookup"><span data-stu-id="1ef87-147">The XML `ElementPath` nodes for `sales:LineItems` and `sales:LineItem` use the namespace `sales`.</span></span>  
  
```  
<Query xmlns:sales=  
"https://schemas.microsoft.com/StandardSchemas/ExtendedSales">  
   <SoapAction>  
      https://schemas.microsoft.com/SalesWebService/ListOrders   
   </SoapAction>  
   <ElementPath>  
      Customers/Customer/Orders/Order/sales:LineItems/sales:LineItem  
   </ElementPath>  
</Query>  
```  
  
 <span data-ttu-id="1ef87-148">Wenn Sie den Namespace des Datenanbieters so angeben möchten, dass der Standardnamespace leer bleibt, verwenden Sie `xmldp`.</span><span class="sxs-lookup"><span data-stu-id="1ef87-148">To specify the data provider namespace so that the default namespace remains empty, use `xmldp`.</span></span> <span data-ttu-id="1ef87-149">Dies wird im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="1ef87-149">This is shown in the following example.</span></span>  
  
### <a name="example"></a><span data-ttu-id="1ef87-150">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1ef87-150">Example</span></span>  
 <span data-ttu-id="1ef87-151">Im folgenden Beispiel wird das XML-Dokument DPNamespace.xml verwendet, das zur Veranschaulichung unter der Tabelle bereitgestellt ist.</span><span class="sxs-lookup"><span data-stu-id="1ef87-151">The following examples use the XML document DPNamespace.xml, which is provided for illustration after the table.</span></span> <span data-ttu-id="1ef87-152">In dieser Tabelle sind zwei Beispiele für XML-ElementPath-Syntax angegeben, die Namespacepräfixe enthalten.</span><span class="sxs-lookup"><span data-stu-id="1ef87-152">This table shows two examples of XML ElementPath syntax that includes namespace prefixes.</span></span>  
  
|<span data-ttu-id="1ef87-153">XML-Abfrageelement</span><span class="sxs-lookup"><span data-stu-id="1ef87-153">XML Query Element</span></span>|<span data-ttu-id="1ef87-154">Resultierende Felder im Dataset</span><span class="sxs-lookup"><span data-stu-id="1ef87-154">Resulting fields in the dataset</span></span>|  
|-----------------------|-------------------------------------|  
|\<Query/>|<span data-ttu-id="1ef87-155">Wert A: `https://schemas.microsoft.com/..` .</span><span class="sxs-lookup"><span data-stu-id="1ef87-155">Value A: `https://schemas.microsoft.com/..`.</span></span><br /><br /> <span data-ttu-id="1ef87-156">Wert B: `https://schemas.microsoft.com/..` .</span><span class="sxs-lookup"><span data-stu-id="1ef87-156">Value B: `https://schemas.microsoft.com/..`.</span></span><br /><br /> <span data-ttu-id="1ef87-157">Wert C: `https://schemas.microsoft.com/.` ..</span><span class="sxs-lookup"><span data-stu-id="1ef87-157">Value C: `https://schemas.microsoft.com/.`..</span></span>|  
|\<xmldp:Query xmlns:xmldp="https://schemas.microsoft.com/sqlserver/2005/02/reporting/XmlDPQuery" xmlns:ns="https://schemas.microsoft.com/..."><br /><br /> <span data-ttu-id="1ef87-158">\<xmldp:ElementPath>Root {} /NS: Element2/Node\</xmldp:ElementPath></span><span class="sxs-lookup"><span data-stu-id="1ef87-158">\<xmldp:ElementPath>Root {}/ns:Element2/Node\</xmldp:ElementPath></span></span><br /><br /> \</xmldp:Query>|<span data-ttu-id="1ef87-159">Value D</span><span class="sxs-lookup"><span data-stu-id="1ef87-159">Value D</span></span><br /><br /> <span data-ttu-id="1ef87-160">Value E</span><span class="sxs-lookup"><span data-stu-id="1ef87-160">Value E</span></span><br /><br /> <span data-ttu-id="1ef87-161">Value F</span><span class="sxs-lookup"><span data-stu-id="1ef87-161">Value F</span></span>|  
  
#### <a name="xml-document-dpnamespacexml"></a><span data-ttu-id="1ef87-162">XML-Dokument: DPNamespace.xml</span><span class="sxs-lookup"><span data-stu-id="1ef87-162">XML document: DPNamespace.xml</span></span>  
 <span data-ttu-id="1ef87-163">Sie können dieses XML-Dokument kopieren und unter einer URL speichern, auf den der Berichts-Designer zugreifen kann, um es als XML-Datenquelle zu verwenden: z. B. http://localhost/DPNamespace.xml.</span><span class="sxs-lookup"><span data-stu-id="1ef87-163">You can copy this XML and save it to a URL available for Report Designer to use as an XML data source: for example, http://localhost/DPNamespace.xml.</span></span>  
  
```  
<Root xmlns:ns="https://schemas.microsoft.com/...">  
   <ns:Element1>  
      <Node>Value A</Node>  
      <Node>Value B</Node>  
      <Node>Value C</Node>  
   </ns:Element1>  
   <ns:Element2>  
      <Node>Value D</Node>  
      <Node>Value E</Node>  
      <Node>Value F</Node>  
   </ns:Element2>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1ef87-164">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1ef87-164">See Also</span></span>  
 <span data-ttu-id="1ef87-165">[XML-Verbindungstyp &#40;SSRS-&#41;](xml-connection-type-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1ef87-165">[XML Connection Type &#40;SSRS&#41;](xml-connection-type-ssrs.md) </span></span>  
 [<span data-ttu-id="1ef87-166">Reporting Services-Tutorials (SSRS)</span><span class="sxs-lookup"><span data-stu-id="1ef87-166">Reporting Services Tutorials &#40;SSRS&#41;</span></span>](../reporting-services-tutorials-ssrs.md)  
  
  
