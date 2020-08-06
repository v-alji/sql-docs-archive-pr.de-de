---
title: Abrufen und Abfragen von XML-Daten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- XML data [SQL Server], retrieving
- XML instance retrieval
ms.assetid: 24a28760-1225-42b3-9c89-c9c0332d9c51
author: rothja
ms.author: jroth
ms.openlocfilehash: d387d1b96a57dcc7100368779f8ec6078fad5c7e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697590"
---
# <a name="retrieve-and-query-xml-data"></a><span data-ttu-id="09d81-102">Abrufen und Abfragen von XML-Daten</span><span class="sxs-lookup"><span data-stu-id="09d81-102">Retrieve and Query XML Data</span></span>
  <span data-ttu-id="09d81-103">In diesem Thema werden die Abfrageoptionen beschrieben, die für die Abfrage von XML-Daten anzugeben sind.</span><span class="sxs-lookup"><span data-stu-id="09d81-103">This topic describes the query options that you have to specify to query XML data.</span></span> <span data-ttu-id="09d81-104">Es beschreibt auch die Teile der XML-Instanzen, die nicht beibehalten werden, wenn sie in Datenbanken gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="09d81-104">It also describes the parts of XML instances that are not preserved when they are stored in databases.</span></span>  
  
##  <a name="features-of-an-xml-instance-that-are-not-preserved"></a><a name="features"></a> <span data-ttu-id="09d81-105">Funktionen einer XML-Instanz, die nicht beibehalten werden</span><span class="sxs-lookup"><span data-stu-id="09d81-105">Features of an XML Instance That Are Not Preserved</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="09d81-106">behält den Inhalt der XML-Instanz bei. Allerdings werden die Aspekte der XML-Instanz nicht beibehalten, die im Hinblick auf das XML-Datenmodell als nicht signifikant betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="09d81-106">preserves the content of the XML instance, but does not preserve aspects of the XML instance that are not considered to be significant in the XML data model.</span></span> <span data-ttu-id="09d81-107">Das bedeutet, dass eine abgerufene XML-Instanz möglicherweise nicht mit der Instanz identisch ist, die auf dem Server gespeichert wurde, aber die gleichen Informationen enthält.</span><span class="sxs-lookup"><span data-stu-id="09d81-107">This means that a retrieved XML instance might not be identical to the instance that was stored in the server, but will contain the same information.</span></span>  
  
### <a name="xml-declaration"></a><span data-ttu-id="09d81-108">XML-Deklaration</span><span class="sxs-lookup"><span data-stu-id="09d81-108">XML Declaration</span></span>  
 <span data-ttu-id="09d81-109">Die XML-Deklaration in einer Instanz wird nicht beibehalten, wenn die Instanz in der Datenbank gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="09d81-109">The XML declaration in an instance is not preserved when the instance is stored in the database.</span></span> <span data-ttu-id="09d81-110">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="09d81-110">For example:</span></span>  
  
```  
CREATE TABLE T1 (Col1 int primary key, Col2 xml)  
GO  
INSERT INTO T1 values (1, '<?xml version="1.0" encoding="windows-1252" ?><doc></doc>')  
GO  
SELECT Col2  
FROM T1  
```  
  
 <span data-ttu-id="09d81-111">Das Ergebnis ist `<doc/>`.</span><span class="sxs-lookup"><span data-stu-id="09d81-111">The result is `<doc/>`.</span></span>  
  
 <span data-ttu-id="09d81-112">Die XML-Deklaration, z. B. `<?xml version='1.0'?>`, wird nicht beibehalten, wenn die XML-Daten in einer `xml`-Datentypinstanz gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="09d81-112">The XML declaration, such as `<?xml version='1.0'?>`, is not preserved when storing XML data in an `xml` data type instance.</span></span> <span data-ttu-id="09d81-113">Dies ist beabsichtigt.</span><span class="sxs-lookup"><span data-stu-id="09d81-113">This is by design.</span></span> <span data-ttu-id="09d81-114">Die XML-Deklaration () und die zugehörigen Attribute (Version/Codierung/eigenständige) gehen verloren, nachdem Daten in den Typ konvertiert wurden `xml` .</span><span class="sxs-lookup"><span data-stu-id="09d81-114">The XML declaration () and its attributes (version/encoding/stand-alone) are lost after data is converted to type `xml`.</span></span> <span data-ttu-id="09d81-115">Die XML-Deklaration wird als Direktive für den XML-Parser behandelt.</span><span class="sxs-lookup"><span data-stu-id="09d81-115">The XML declaration is treated as a directive to the XML parser.</span></span> <span data-ttu-id="09d81-116">Die XML-Daten werden intern als ucs-2 gespeichert.</span><span class="sxs-lookup"><span data-stu-id="09d81-116">The XML data is stored internally as ucs-2.</span></span> <span data-ttu-id="09d81-117">Alle anderen PIs in der XML-Instanz werden beibehalten.</span><span class="sxs-lookup"><span data-stu-id="09d81-117">All other PIs in the XML instance are preserved.</span></span>  
  
  
### <a name="order-of-attributes"></a><span data-ttu-id="09d81-118">Reihenfolge von Attributen</span><span class="sxs-lookup"><span data-stu-id="09d81-118">Order of Attributes</span></span>  
 <span data-ttu-id="09d81-119">Die Reihenfolge der Attribute in einer XML-Instanz wird nicht erhalten.</span><span class="sxs-lookup"><span data-stu-id="09d81-119">The order of attributes in an XML instance is not preserved.</span></span> <span data-ttu-id="09d81-120">Bei einer Abfrage der in der `xml`-Typspalte gespeicherten XML-Instanz kann die Reihenfolge der Attribute in der resultierenden XML von der der ursprünglichen XML-Instanz abweichen.</span><span class="sxs-lookup"><span data-stu-id="09d81-120">When you query the XML instance stored in the `xml` type column, the order of attributes in the resulting XML may be different from the original XML instance.</span></span>  
  
  
### <a name="quotation-marks-around-attribute-values"></a><span data-ttu-id="09d81-121">Anführungszeichen um Attributwerte</span><span class="sxs-lookup"><span data-stu-id="09d81-121">Quotation Marks Around Attribute Values</span></span>  
 <span data-ttu-id="09d81-122">Einfache Anführungszeichen und doppelte Anführungszeichen um Attributwerte werden nicht erhalten.</span><span class="sxs-lookup"><span data-stu-id="09d81-122">Single quotation marks and double quotations marks around attribute values are not preserved.</span></span> <span data-ttu-id="09d81-123">Die Attributwerte werden in der Datenbank als Name/Wert-Paar gespeichert.</span><span class="sxs-lookup"><span data-stu-id="09d81-123">The attribute values are stored in the database as a name and value pair.</span></span> <span data-ttu-id="09d81-124">Die Anführungszeichen werden nicht gespeichert.</span><span class="sxs-lookup"><span data-stu-id="09d81-124">The quotation marks are not stored.</span></span> <span data-ttu-id="09d81-125">Wenn eine XQuery-Abfrage für eine XML-Instanz ausgeführt wird, wird die resultierende XML mit doppelten Anführungszeichen um die Attributwerte serialisiert.</span><span class="sxs-lookup"><span data-stu-id="09d81-125">When an XQuery is executed against an XML instance, the resulting XML is serialized with double quotation marks around the attribute values.</span></span>  
  
```  
DECLARE @x xml  
-- Use double quotation marks.  
SET @x = '<root a="1" />'  
SELECT @x  
GO  
DECLARE @x xml  
-- Use single quotation marks.  
SET @x = '<root a=''1'' />'  
SELECT @x  
GO  
```  
  
 <span data-ttu-id="09d81-126">Für beide Abfragen wird Folgendes zurückgeben: = `<root a="1" />`.</span><span class="sxs-lookup"><span data-stu-id="09d81-126">Both queries return = `<root a="1" />`.</span></span>  
  
  
### <a name="namespace-prefixes"></a><span data-ttu-id="09d81-127">Namespacepräfixe</span><span class="sxs-lookup"><span data-stu-id="09d81-127">Namespace Prefixes</span></span>  
 <span data-ttu-id="09d81-128">Namespacepräfixe werden nicht erhalten.</span><span class="sxs-lookup"><span data-stu-id="09d81-128">Namespace prefixes are not preserved.</span></span> <span data-ttu-id="09d81-129">Wenn Sie eine XQuery-Abfrage für eine `xml`-Typspalte angeben, werden vom serialisierten XML-Ergebnis möglicherweise andere Namespacepräfixe zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="09d81-129">When you specify XQuery against an `xml` type column, the serialized XML result may return different namespace prefixes.</span></span>  
  
```  
DECLARE @x xml  
SET @x = '<ns1:root xmlns:ns1="abc" xmlns:ns2="abc">  
            <ns2:SomeElement/>  
          </ns1:root>'  
SELECT @x  
SELECT @x.query('/*')  
GO  
```  
  
 <span data-ttu-id="09d81-130">Das Namespacepräfix des Ergebnisses kann unterschiedlich sein.</span><span class="sxs-lookup"><span data-stu-id="09d81-130">The namespace prefix in the result may be different.</span></span> <span data-ttu-id="09d81-131">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="09d81-131">For example:</span></span>  
  
```  
<p1:root xmlns:p1="abc"><p1:SomeElement/></p1:root>  
```  
  
  
##  <a name="setting-required-query-options"></a><a name="query"></a> <span data-ttu-id="09d81-132">Festlegen der erforderlichen Abfrageoptionen</span><span class="sxs-lookup"><span data-stu-id="09d81-132">Setting Required Query Options</span></span>  
 <span data-ttu-id="09d81-133">Beim Abfragen von `xml` Typspalten oder Variablen mithilfe von- `xml` Datentyp Methoden müssen die folgenden Optionen wie dargestellt festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="09d81-133">When querying `xml` type columns or variables using `xml` data type methods, the following options must be set as shown.</span></span>  
  
|<span data-ttu-id="09d81-134">SET-Optionen</span><span class="sxs-lookup"><span data-stu-id="09d81-134">SET Options</span></span>|<span data-ttu-id="09d81-135">Erforderliche Werte</span><span class="sxs-lookup"><span data-stu-id="09d81-135">Required Values</span></span>|  
|-----------------|---------------------|  
|<span data-ttu-id="09d81-136">ANSI_NULLS</span><span class="sxs-lookup"><span data-stu-id="09d81-136">ANSI_NULLS</span></span>|<span data-ttu-id="09d81-137">EIN</span><span class="sxs-lookup"><span data-stu-id="09d81-137">ON</span></span>|  
|<span data-ttu-id="09d81-138">ANSI_PADDING</span><span class="sxs-lookup"><span data-stu-id="09d81-138">ANSI_PADDING</span></span>|<span data-ttu-id="09d81-139">EIN</span><span class="sxs-lookup"><span data-stu-id="09d81-139">ON</span></span>|  
|<span data-ttu-id="09d81-140">ANSI_WARNINGS</span><span class="sxs-lookup"><span data-stu-id="09d81-140">ANSI_WARNINGS</span></span>|<span data-ttu-id="09d81-141">EIN</span><span class="sxs-lookup"><span data-stu-id="09d81-141">ON</span></span>|  
|<span data-ttu-id="09d81-142">ARITHABORT</span><span class="sxs-lookup"><span data-stu-id="09d81-142">ARITHABORT</span></span>|<span data-ttu-id="09d81-143">EIN</span><span class="sxs-lookup"><span data-stu-id="09d81-143">ON</span></span>|  
|<span data-ttu-id="09d81-144">CONCAT_NULL_YIELDS_NULL</span><span class="sxs-lookup"><span data-stu-id="09d81-144">CONCAT_NULL_YIELDS_NULL</span></span>|<span data-ttu-id="09d81-145">EIN</span><span class="sxs-lookup"><span data-stu-id="09d81-145">ON</span></span>|  
|<span data-ttu-id="09d81-146">NUMERIC_ROUNDABORT</span><span class="sxs-lookup"><span data-stu-id="09d81-146">NUMERIC_ROUNDABORT</span></span>|<span data-ttu-id="09d81-147">OFF</span><span class="sxs-lookup"><span data-stu-id="09d81-147">OFF</span></span>|  
|<span data-ttu-id="09d81-148">QUOTED_IDENTIFIER</span><span class="sxs-lookup"><span data-stu-id="09d81-148">QUOTED_IDENTIFIER</span></span>|<span data-ttu-id="09d81-149">EIN</span><span class="sxs-lookup"><span data-stu-id="09d81-149">ON</span></span>|  
  
 <span data-ttu-id="09d81-150">Wenn die Optionen nicht wie dargestellt festgelegt sind, schlagen Abfragen und Änderungen an `xml` Datentyp Methoden fehl.</span><span class="sxs-lookup"><span data-stu-id="09d81-150">If the options are not set as shown, queries and modifications on `xml` data type methods will fail.</span></span>  
  
  
## <a name="see-also"></a><span data-ttu-id="09d81-151">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="09d81-151">See Also</span></span>  
 [<span data-ttu-id="09d81-152">Erstellen von Instanzen der XML-Daten</span><span class="sxs-lookup"><span data-stu-id="09d81-152">Create Instances of XML Data</span></span>](create-instances-of-xml-data.md)  
  
  
