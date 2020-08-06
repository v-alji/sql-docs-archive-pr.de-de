---
title: Client seitige XML-Formatierung (SQLXML 4,0) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- FOR XML clause, formatting
- middle tier XML formatting [SQLXML]
- client-side XML formatting
- client-side-xml attribute
ms.assetid: 9630a21d-a93b-4d3b-8a25-c4b32399f993
author: rothja
ms.author: jroth
ms.openlocfilehash: bf4a680d79a25d24ebdf779b41fd3be5a5d6a605
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619709"
---
# <a name="client-side-xml-formatting-sqlxml-40"></a><span data-ttu-id="b631e-102">Clientseitige XML-Formatierung (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="b631e-102">Client-side XML Formatting (SQLXML 4.0)</span></span>
  <span data-ttu-id="b631e-103">Dieses Thema enthält Informationen zur clientseitigen XML-Formatierung.</span><span class="sxs-lookup"><span data-stu-id="b631e-103">This topic provides information about client-side XML formatting.</span></span> <span data-ttu-id="b631e-104">Als clientseitige Formatierung wird die Formatierung von XML-Code auf der mittleren Ebene bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="b631e-104">Client-side formatting refers to the formatting of XML on the middle tier.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b631e-105">Dieses Thema enthält zusätzliche Informationen zur clientseitigen Verwendung der FOR XML-Klausel und setzt voraus, dass Sie bereits mit der FOR XML-Klausel vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="b631e-105">This topic provides additional information about using the FOR XML clause on the client side, and assumes you are already familiar with the FOR XML clause.</span></span> <span data-ttu-id="b631e-106">Weitere Informationen zu for XML finden Sie unter [Erstellen von XML mithilfe von for XML](../../xml/for-xml-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b631e-106">For more information about FOR XML, see [Constructing XML Using FOR XML](../../xml/for-xml-sql-server.md).</span></span>  
  
 <span data-ttu-id="b631e-107">**Wichtig** Zur Verwendung der Client seitigen for XML-Funktionalität mit dem neuen- `xml` Datentyp sollten Clients immer den [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11)-Datenanbieter anstelle des SQLOLEDB-Anbieters verwenden.</span><span class="sxs-lookup"><span data-stu-id="b631e-107">**Important** To use client-side FOR XML functionality with the new `xml` data type, clients should always use the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) data provider instead of the SQLOLEDB provider.</span></span> <span data-ttu-id="b631e-108">SQLNCLI11 ist die neueste Version des SQLmServer-Anbieters und erkennt die in [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] eingeführten Datentypen vollständig.</span><span class="sxs-lookup"><span data-stu-id="b631e-108">SQLNCLI11 is the latest version of the SQL Server provider and fully understands data types introduced in [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="b631e-109">Das Verhalten für clientseitiges FOR XML mit dem SQLOLEDB-Anbieter behandelt `xml`-Datentypen als Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="b631e-109">The behavior for client side FOR XML with the SQLOLEDB provider will treat `xml` data types as strings.</span></span>  
  
## <a name="formatting-xml-documents-on-the-client-side"></a><span data-ttu-id="b631e-110">Clientseitige Formatierung von XML-Dokumenten</span><span class="sxs-lookup"><span data-stu-id="b631e-110">Formatting XML Documents on the Client Side</span></span>  
 <span data-ttu-id="b631e-111">Wenn eine Clientanwendung die folgende Abfrage ausführt:</span><span class="sxs-lookup"><span data-stu-id="b631e-111">When a client application executes the following query:</span></span>  
  
```  
SELECT FirstName, LastName  
FROM   Person.Contact  
FOR XML RAW  
```  
  
 <span data-ttu-id="b631e-112">Wird nur dieser Teil der Abfrage an den Server gesendet:</span><span class="sxs-lookup"><span data-stu-id="b631e-112">...only this part of the query is sent to the server:</span></span>  
  
```  
SELECT FirstName, LastName  
FROM   Person.Contact  
```  
  
 <span data-ttu-id="b631e-113">Der Server führt die Abfrage aus und gibt ein Rowset (das FirstName und lastnamecolumschlag enthält) an den Client zurück.</span><span class="sxs-lookup"><span data-stu-id="b631e-113">The server executes the query and returns a rowset (which contains FirstName and LastNamecolumns) to the client.</span></span> <span data-ttu-id="b631e-114">Die mittlere Ebene wendet dann die FOR XML-Transformation auf das Rowset an und gibt die XML-Formatierung an den Client zurück.</span><span class="sxs-lookup"><span data-stu-id="b631e-114">The middle tier then applies the FOR XML transformation to the rowset and returns XML formatting to the client.</span></span>  
  
 <span data-ttu-id="b631e-115">Entsprechend gibt der Server beim Ausführen einer XPath-Abfrage das Rowset an den Client zurück und die FOR XML EXPLICIT-Transformation wird auf das Rowset auf dem Client angewendet. Somit wird die gewünschte XML-Formatierung erzeugt.</span><span class="sxs-lookup"><span data-stu-id="b631e-115">Similarly, when you execute an XPath query, the server returns the rowset to the client and the FOR XML EXPLICIT transformation is applied to the rowset on the client, generating the desired XML formatting.</span></span>  
  
 <span data-ttu-id="b631e-116">Die folgende Tabelle zeigt die Modi, die Sie mit clientseitigem FOR XML angeben können.</span><span class="sxs-lookup"><span data-stu-id="b631e-116">The following table shows the modes you can specify with client-side FOR XML.</span></span>  
  
|<span data-ttu-id="b631e-117">Clientseitiger FOR XML-Modus</span><span class="sxs-lookup"><span data-stu-id="b631e-117">Client-side FOR XML mode</span></span>|<span data-ttu-id="b631e-118">Comment</span><span class="sxs-lookup"><span data-stu-id="b631e-118">Comment</span></span>|  
|-------------------------------|-------------|  
|<span data-ttu-id="b631e-119">RAW</span><span class="sxs-lookup"><span data-stu-id="b631e-119">RAW</span></span>|<span data-ttu-id="b631e-120">Erzeugt bei Festlegung in clientseitigem oder serverseitigem FOR XML identische Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="b631e-120">Produces identical results when specified in client-side or server-side FOR XML.</span></span>|  
|<span data-ttu-id="b631e-121">NESTED</span><span class="sxs-lookup"><span data-stu-id="b631e-121">NESTED</span></span>|<span data-ttu-id="b631e-122">Ist dem serverseitigen FOR XML AUTO-Modus ähnlich.</span><span class="sxs-lookup"><span data-stu-id="b631e-122">Is similar to FOR XML AUTO mode on the server-side.</span></span>|  
|<span data-ttu-id="b631e-123">EXPLICIT</span><span class="sxs-lookup"><span data-stu-id="b631e-123">EXPLICIT</span></span>|<span data-ttu-id="b631e-124">Ist dem serverseitigen FOR XML EXPLICIT-Modus ähnlich.</span><span class="sxs-lookup"><span data-stu-id="b631e-124">Is similar to server-side FOR XML EXPLICIT mode.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="b631e-125">Wenn Sie den AUTO-Modus angeben und clientseitige XML-Formatierung anfordern, wird die gesamte Abfrage an den Server gesendet, d. h. die XML-Formatierung findet auf dem Server statt.</span><span class="sxs-lookup"><span data-stu-id="b631e-125">If you specify AUTO mode and request client-side XML formatting, the entire query is sent to the server; that is, XML formatting occurs on the server.</span></span> <span data-ttu-id="b631e-126">Dies ist praktisch, aber beachten Sie, dass der NESTED-Modus Basistabellennamen als Elementnamen in dem generierten XML-Dokument zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="b631e-126">This is done for convenience, but note that the NESTED mode returns base table names as element names in the XML document that is generated.</span></span> <span data-ttu-id="b631e-127">Einige der von Ihnen erstellten Anwendungen erfordern möglicherweise Basistabellennamen.</span><span class="sxs-lookup"><span data-stu-id="b631e-127">Some of the applications you write might require base table names.</span></span> <span data-ttu-id="b631e-128">Angenommen, Sie führen eine gespeicherte Prozedur aus, laden die Ergebnisdaten in ein Dataset (im [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework) und erstellen dann später ein DiffGram, um die Daten in den Tabellen zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="b631e-128">For example, you might execute a stored procedure and load the resulting data in a Dataset (in the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework), and then later generate a DiffGram to update data in the tables.</span></span> <span data-ttu-id="b631e-129">In einem solchen Fall benötigen Sie die Basistabelleninformationen und müssen den NESTED-Modus verwenden.</span><span class="sxs-lookup"><span data-stu-id="b631e-129">In such a case, you would need the base table information and you would have to use the NESTED mode.</span></span>  
  
## <a name="benefits-of-client-side-xml-formatting"></a><span data-ttu-id="b631e-130">Vorteile der clientseitigen XML-Formatierung</span><span class="sxs-lookup"><span data-stu-id="b631e-130">Benefits of Client-side XML formatting</span></span>  
 <span data-ttu-id="b631e-131">Im Folgenden werden einige Vorteile der Formatierung von XML auf dem Client aufgezeigt.</span><span class="sxs-lookup"><span data-stu-id="b631e-131">The following are some benefits of formatting XML on the client.</span></span>  
  
### <a name="if-you-have-stored-procedures-on-the-server-that-return-a-single-rowset-you-can-request-client-side-for-xml-transformation-to-generate-an-xml"></a><span data-ttu-id="b631e-132">Wenn auf dem Server gespeicherte Prozeduren gespeichert sind, die ein einzelnes Rowset zurückgeben, können Sie zur Erstellung des XML-Code die clientseitige FOR XML-Transformation anfordern.</span><span class="sxs-lookup"><span data-stu-id="b631e-132">If you have stored procedures on the server that return a single rowset, you can request client-side FOR XML transformation to generate an XML.</span></span>  
 <span data-ttu-id="b631e-133">Nehmen Sie die folgende gespeicherte Prozedur als Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b631e-133">For example, consider the following stored procedure.</span></span> <span data-ttu-id="b631e-134">Diese Prozedur gibt den Vor- und Nachnamen der Mitarbeiter aus der Person.Contact-Tabelle in der AdventureWorks-Datenbank zurück:</span><span class="sxs-lookup"><span data-stu-id="b631e-134">This procedure returns the first and last names of employees from the Person.Contact table in the AdventureWorks database:</span></span>  
  
```  
IF EXISTS (SELECT name FROM sysobjects  
   WHERE name = 'GetContacts' AND type = 'P')  
   DROP PROCEDURE GetContacts  
GO  
CREATE PROCEDURE GetContacts  
AS  
    SELECT   FirstName, LastName  
    FROM     Person.Contact  
```  
  
 <span data-ttu-id="b631e-135">Die folgende XML-Beispielvorlage führt die gespeicherte Prozedur aus.</span><span class="sxs-lookup"><span data-stu-id="b631e-135">The following sample XML template executes the stored procedure.</span></span> <span data-ttu-id="b631e-136">Die FOR XML-Klausel wird nach dem Namen der gespeicherten Prozedur festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b631e-136">The FOR XML clause is specified after the stored procedure name.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query client-side-xml="1">  
    EXEC GetContacts FOR XML NESTED  
  </sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="b631e-137">Da das **Client seitige XML-** Attribut in der Vorlage auf 1 (true) festgelegt ist, wird die gespeicherte Prozedur auf dem Server ausgeführt, und das zweispaltige Rowset, das vom Server zurückgegeben wird, wird auf der mittleren Ebene in XML transformiert und an den Client zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b631e-137">Because the **client-side-xml** attribute is set to 1 (true) in the template, the stored procedure is executed on the server and the two-column rowset that is returned by the server is transformed into XML on the middle tier and returned to the client.</span></span> <span data-ttu-id="b631e-138">(Hier wird nur ein Teilergebnis angezeigt.)</span><span class="sxs-lookup"><span data-stu-id="b631e-138">(Only a partial result is shown here.)</span></span>  
  
```  
 <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Person.Contact FirstName="Gustavo" LastName="Achong" />   
  <Person.Contact FirstName="Catherine" LastName="Abel" />  
</ROOT>  
```  
  
> [!NOTE]  
>  <span data-ttu-id="b631e-139">Wenn Sie den SQLXMLOLEDB-Anbieter oder verwaltete SQLXML-Klassen verwenden, können Sie mithilfe der `ClientSideXml`-Eigenschaft clientseitige XML-Formatierung anfordern.</span><span class="sxs-lookup"><span data-stu-id="b631e-139">When you are using the SQLXMLOLEDB Provider or SQLXML Managed Classes, you can use the `ClientSideXml` property to request client-side XML formatting.</span></span>  
  
### <a name="the-workload-is-more-balanced"></a><span data-ttu-id="b631e-140">Die Arbeitsauslastung wird besser verteilt.</span><span class="sxs-lookup"><span data-stu-id="b631e-140">The workload is more balanced.</span></span>  
 <span data-ttu-id="b631e-141">Da der Client die XML-Formatierung ausführt, wird die Arbeitsauslastung zwischen Server und Client besser verteilt. Der Server verfügt über mehr Kapazität für andere Aufgaben.</span><span class="sxs-lookup"><span data-stu-id="b631e-141">Because the client does the XML formatting, the workload is balanced between the server and client, freeing the server to do other things.</span></span>  
  
## <a name="supporting-client-side-xml-formatting"></a><span data-ttu-id="b631e-142">Unterstützung clientseitiger XML-Formatierung</span><span class="sxs-lookup"><span data-stu-id="b631e-142">Supporting Client-side XML Formatting</span></span>  
 <span data-ttu-id="b631e-143">Zur Unterstützung der clientseitigen XML-Formatierung bietet SQLXML:</span><span class="sxs-lookup"><span data-stu-id="b631e-143">To support the client-side XML formatting functionality, SQLXML provides:</span></span>  
  
-   <span data-ttu-id="b631e-144">SQLXMLOLEDB-Anbieter</span><span class="sxs-lookup"><span data-stu-id="b631e-144">SQLXMLOLEDB Provider</span></span>  
  
-   <span data-ttu-id="b631e-145">SQLXML, verwaltete Klassen</span><span class="sxs-lookup"><span data-stu-id="b631e-145">SQLXML Managed Classes</span></span>  
  
-   <span data-ttu-id="b631e-146">Verbesserte Unterstützung für XML-Vorlagen</span><span class="sxs-lookup"><span data-stu-id="b631e-146">Enhanced XML template support</span></span>  
  
-   <span data-ttu-id="b631e-147">SqlXmlCommand. ClientSideXML (Eigenschaft)</span><span class="sxs-lookup"><span data-stu-id="b631e-147">SqlXmlCommand.ClientSideXml property</span></span>  
  
     <span data-ttu-id="b631e-148">Sie können die clientseitige Formatierung festlegen, indem Sie diese Eigenschaft der verwalteten SQLXML-Klassen auf true festlegen.</span><span class="sxs-lookup"><span data-stu-id="b631e-148">You can specify client-side formatting by setting this property of the SQLXML managed classes to true.</span></span>  
  
## <a name="enhanced-xml-template-support"></a><span data-ttu-id="b631e-149">Erweiterte XML-Vorlagen Unterstützung</span><span class="sxs-lookup"><span data-stu-id="b631e-149">Enhanced XML Template Support</span></span>  
 <span data-ttu-id="b631e-150">Ab [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] wurde die XML-Vorlage in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] durch das Hinzufügen des **Client seitigen XML-** Attributs erweitert.</span><span class="sxs-lookup"><span data-stu-id="b631e-150">Beginning with [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], the XML template in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] has been enhanced with the addition of the **client-side-xml** attribute.</span></span> <span data-ttu-id="b631e-151">Wenn dieses Attribut auf true festgelegt wird, wird der XML-Code auf dem Client formatiert.</span><span class="sxs-lookup"><span data-stu-id="b631e-151">If this attribute is set to true, XML is formatted on the client.</span></span> <span data-ttu-id="b631e-152">Beachten Sie, dass dieses Vorlagen Attribut in der Funktionalität mit der anbieterspezifischen SQLXMLOLEDB-Eigenschaft "ClientSideXML" identisch ist.</span><span class="sxs-lookup"><span data-stu-id="b631e-152">Note that this template attribute is identical in functionality to the SQLXMLOLEDB Provider-specific ClientSideXML property.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b631e-153">Wenn Sie in einer ADO-Anwendung, die den SQLXMLOLEDB-Anbieter verwendet, eine XML-Vorlage ausführen und sowohl das **Client-Side-XML-** Attribut in der Vorlage als auch die ClientSideXML-Eigenschaft des Anbieters angeben, hat der in der Vorlage angegebene Wert Vorrang.</span><span class="sxs-lookup"><span data-stu-id="b631e-153">If you execute an XML template in an ADO application that is using the SQLXMLOLEDB Provider, and you specify both the **client-side-xml** attribute in the template and the provider ClientSideXML property, the value specified in the template takes precedence.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b631e-154">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b631e-154">See Also</span></span>  
 <span data-ttu-id="b631e-155">[Architektur der Client seitigen und Server seitigen XML-Formatierung &#40;SQLXML 4,0&#41;](server-side-xml-formatting-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="b631e-155">[Architecture of Client-side and Server-side XML Formatting &#40;SQLXML 4.0&#41;](server-side-xml-formatting-sqlxml-4-0.md) </span></span>  
 <span data-ttu-id="b631e-156">[Für XML-&#40;SQL Server&#41;](../../xml/for-xml-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b631e-156">[FOR XML &#40;SQL Server&#41;](../../xml/for-xml-sql-server.md) </span></span>  
 <span data-ttu-id="b631e-157">[Informationen zu den XML-Sicherheitsüberlegungen &#40;SQLXML 4,0&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/security/for-xml-security-considerations-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="b631e-157">[FOR XML Security Considerations &#40;SQLXML 4.0&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/security/for-xml-security-considerations-sqlxml-4-0.md) </span></span>  
 <span data-ttu-id="b631e-158">[XML-Datentyp Unterstützung in SQLXML 4,0](../xml-data-type-support-in-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="b631e-158">[xml Data Type Support in SQLXML 4.0](../xml-data-type-support-in-sqlxml-4-0.md) </span></span>  
 <span data-ttu-id="b631e-159">[Verwaltete SQLXML-Klassen](../../sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/sqlxml-4-0-net-framework-support-managed-classes.md) </span><span class="sxs-lookup"><span data-stu-id="b631e-159">[SQLXML Managed Classes](../../sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/sqlxml-4-0-net-framework-support-managed-classes.md) </span></span>  
 <span data-ttu-id="b631e-160">[Client seitige und Server seitige XML-Formatierung &#40;SQLXML 4,0&#41;](client-side-vs-server-side-xml-formatting-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="b631e-160">[Client-side vs. Server-side XML Formatting &#40;SQLXML 4.0&#41;](client-side-vs-server-side-xml-formatting-sqlxml-4-0.md) </span></span>  
 <span data-ttu-id="b631e-161">[SqlXmlCommand-Objekt &#40;verwalteten SQLXML-Klassen&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/sqlxml-managed-classes-sqlxmlcommand-object.md) </span><span class="sxs-lookup"><span data-stu-id="b631e-161">[SqlXmlCommand Object &#40;SQLXML Managed Classes&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/sqlxml-managed-classes-sqlxmlcommand-object.md) </span></span>  
 [<span data-ttu-id="b631e-162">XML-Daten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b631e-162">XML Data &#40;SQL Server&#41;</span></span>](../../xml/xml-data-sql-server.md)  
  
  
