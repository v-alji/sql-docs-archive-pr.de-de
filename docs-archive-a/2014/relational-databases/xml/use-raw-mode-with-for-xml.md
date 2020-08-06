---
title: Verwenden des RAW-Modus mit FOR XML | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML RAW mode
- XMLSCHEMA option
- FOR XML clause, RAW mode
- RAW FOR XML mode
- ELEMENTS directive
- RAW mode
- XMLDATA option
ms.assetid: 02c1bc0b-760c-4589-9ab1-6927c6d9c734
author: rothja
ms.author: jroth
ms.openlocfilehash: b2908a98336ec8a6e12029ad471f22a33d7a4dcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722606"
---
# <a name="use-raw-mode-with-for-xml"></a><span data-ttu-id="6cd24-102">Verwenden des RAW-Modus mit FOR XML</span><span class="sxs-lookup"><span data-stu-id="6cd24-102">Use RAW Mode with FOR XML</span></span>
  <span data-ttu-id="6cd24-103">Der RAW-Modus wandelt jede Zeile im Resultset der Abfrage in ein XML-Element um, das den allgemeinen Bezeichner \<row> besitzt, oder in den optional bereitgestellten Elementnamen.</span><span class="sxs-lookup"><span data-stu-id="6cd24-103">RAW mode transforms each row in the query result set into an XML element that has the generic identifier \<row>, or the optionally provided element name.</span></span> <span data-ttu-id="6cd24-104">Standardmäßig wird jeder Spaltenwert im Rowset, der nicht NULL ist, einem Attribut des \<row>-Elements zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="6cd24-104">By default, each column value in the rowset that is not NULL is mapped to an attribute of the \<row> element.</span></span> <span data-ttu-id="6cd24-105">Wenn der FOR XML-Klausel die ELEMENTS-Direktive hinzugefügt wird, wird jeder Spaltenwert einem Unterelement des \<row>-Elements zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="6cd24-105">If the ELEMENTS directive is added to the FOR XML clause, each column value is mapped to a subelement of the \<row> element.</span></span> <span data-ttu-id="6cd24-106">Zusammen mit der ELEMENTS-Direktive können Sie optional die Option XSINIL angeben, um NULL-Spaltenwerte im Resultset einem Element zuzuordnen, das das Attribut xsi:nil=`"`true`"`besitzt.</span><span class="sxs-lookup"><span data-stu-id="6cd24-106">Together with the ELEMENTS directive, you can optionally specify the XSINIL option to map NULL column values in the result set to an element that has the attribute, xsi:nil=`"`true`"`.</span></span>  
  
 <span data-ttu-id="6cd24-107">Sie können ein Schema für das sich ergebende XML anfordern.</span><span class="sxs-lookup"><span data-stu-id="6cd24-107">You can request a schema for the resulting XML.</span></span> <span data-ttu-id="6cd24-108">Wenn Sie die Option XMLDATA angeben, wird ein Inline-XDR-Schema zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="6cd24-108">Specifying the XMLDATA option returns an in-line XDR schema.</span></span> <span data-ttu-id="6cd24-109">Wenn Sie die Option XMLSCHEMA angeben, wird ein Inline-XSD-Schema zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="6cd24-109">Specifying the XMLSCHEMA option returns an in-line XSD schema.</span></span> <span data-ttu-id="6cd24-110">Das Schema wird zu Beginn der Daten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6cd24-110">The schema appears at the start of the data.</span></span> <span data-ttu-id="6cd24-111">Im Resultset wird der Verweis auf den Schemanamespace für jedes Element der obersten Ebene wiederholt.</span><span class="sxs-lookup"><span data-stu-id="6cd24-111">In the result, the schema namespace reference is repeated for every top-level element.</span></span>  
  
 <span data-ttu-id="6cd24-112">Die Option BINARY BASE64 muss in der FOR XML-Klausel angegeben werden, um die Binärdaten im Base64-codierten Format zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="6cd24-112">The BINARY BASE64 option must be specified in the FOR XML clause to return the binary data in base64-encoded format.</span></span> <span data-ttu-id="6cd24-113">Im RAW-Modus führt das Abrufen von Binärdaten ohne Angabe der Option BINARY BASE64 zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="6cd24-113">In RAW mode, retrieving binary data without specifying the BINARY BASE64 option will result in an error.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6cd24-114">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="6cd24-114">In This Section</span></span>  
 <span data-ttu-id="6cd24-115">Dieser Abschnitt enthält folgende Beispiele:</span><span class="sxs-lookup"><span data-stu-id="6cd24-115">This section contains the following examples:</span></span>  
  
-   [<span data-ttu-id="6cd24-116">Beispiel: Abrufen von Produktmodellinformationen als XML</span><span class="sxs-lookup"><span data-stu-id="6cd24-116">Example: Retrieving Product Model Information as XML</span></span>](example-retrieving-product-model-information-as-xml.md)  
  
-   [<span data-ttu-id="6cd24-117">Beispiel: Angeben von XSINIL mit der ELEMENTS-Anweisung</span><span class="sxs-lookup"><span data-stu-id="6cd24-117">Example: Specifying XSINIL with the ELEMENTS Directive</span></span>](example-specifying-xsinil-with-the-elements-directive.md)  
  
-   [<span data-ttu-id="6cd24-118">Beispiel: Anfordern von Schemas als Ergebnisse mithilfe der Optionen XMLDATA und XMLSCHEMA</span><span class="sxs-lookup"><span data-stu-id="6cd24-118">Example: Requesting Schemas as Results with the XMLDATA and XMLSCHEMA Options</span></span>](example-requesting-schemas-as-results-with-the-xmldata-and-xmlschema-options.md)  
  
-   [<span data-ttu-id="6cd24-119">Beispiel: Abrufen von Binärdaten</span><span class="sxs-lookup"><span data-stu-id="6cd24-119">Example: Retrieving Binary Data</span></span>](example-retrieving-binary-data.md)  
  
-   [<span data-ttu-id="6cd24-120">Beispiel: Umbenennen des &#60;row&#62;-Elements</span><span class="sxs-lookup"><span data-stu-id="6cd24-120">Example: Renaming the &#60;row&#62; Element</span></span>](example-renaming-the-row-element.md)  
  
-   [<span data-ttu-id="6cd24-121">Beispiel: Angeben eines Stammelements für den mit FOR XML generierten XML-Code</span><span class="sxs-lookup"><span data-stu-id="6cd24-121">Example: Specifying a Root Element for the XML Generated by FOR XML</span></span>](example-specifying-a-root-element-for-the-xml-generated-by-for-xml.md)  
  
-   [<span data-ttu-id="6cd24-122">Beispiel: Abfragen von Spalten des Typs XML</span><span class="sxs-lookup"><span data-stu-id="6cd24-122">Example: Querying XMLType Columns</span></span>](example-querying-xmltype-columns.md)  
  
## <a name="see-also"></a><span data-ttu-id="6cd24-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6cd24-123">See Also</span></span>  
 <span data-ttu-id="6cd24-124">[Hinzufügen von Namespaces zu Abfragen mit WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md) </span><span class="sxs-lookup"><span data-stu-id="6cd24-124">[Add Namespaces to Queries with WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md) </span></span>  
 <span data-ttu-id="6cd24-125">[Verwenden des AUTO-Modus mit FOR XML](use-auto-mode-with-for-xml.md) </span><span class="sxs-lookup"><span data-stu-id="6cd24-125">[Use AUTO Mode with FOR XML](use-auto-mode-with-for-xml.md) </span></span>  
 <span data-ttu-id="6cd24-126">[Verwenden des EXPLICIT-Modus mit FOR XML](use-explicit-mode-with-for-xml.md) </span><span class="sxs-lookup"><span data-stu-id="6cd24-126">[Use EXPLICIT Mode with FOR XML](use-explicit-mode-with-for-xml.md) </span></span>  
 <span data-ttu-id="6cd24-127">[Verwenden des PATH-Modus mit FOR XML](use-path-mode-with-for-xml.md) </span><span class="sxs-lookup"><span data-stu-id="6cd24-127">[Use PATH Mode with FOR XML](use-path-mode-with-for-xml.md) </span></span>  
 <span data-ttu-id="6cd24-128">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6cd24-128">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span></span>  
 [<span data-ttu-id="6cd24-129">FOR XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6cd24-129">FOR XML &#40;SQL Server&#41;</span></span>](../xml/for-xml-sql-server.md)  
  
  
