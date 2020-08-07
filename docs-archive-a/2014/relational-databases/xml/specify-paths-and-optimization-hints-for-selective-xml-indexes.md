---
title: Angeben von Pfaden und Optimierungshinweisen für selektive XML-Indizes | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
ms.assetid: 486ee339-165b-4aeb-b760-d2ba023d7d0a
author: rothja
ms.author: jroth
ms.openlocfilehash: 1a9d683fe57d489fdb9922b53d2c5c6825835216
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719738"
---
# <a name="specify-paths-and-optimization-hints-for-selective-xml-indexes"></a><span data-ttu-id="1eb30-102">Angeben von Pfaden und Optimierungshinweisen für selektive XML-Indizes</span><span class="sxs-lookup"><span data-stu-id="1eb30-102">Specify Paths and Optimization Hints for Selective XML Indexes</span></span>
  <span data-ttu-id="1eb30-103">In diesem Thema wird beschrieben, wie Sie Knotenpfade zum Index angeben, und es werden Optimierungshinweise für die Indizierung aufgeführt, wenn Sie selektive XML-Indizes erstellen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="1eb30-103">This topic describes how to specify node paths to index and optimization hints for indexing when you create or alter selective XML indexes.</span></span>  
  
 <span data-ttu-id="1eb30-104">Sie geben Knotenpfade und Optimierungshinweise gleichzeitig in einer der folgenden Anweisungen an:</span><span class="sxs-lookup"><span data-stu-id="1eb30-104">You specify node paths and optimization hints at the same time in one of the following statements:</span></span>  
  
-   <span data-ttu-id="1eb30-105">In der **FOR** -Klausel einer **CREATE** -Anweisung.</span><span class="sxs-lookup"><span data-stu-id="1eb30-105">In the **FOR** clause of a **CREATE** statement.</span></span> <span data-ttu-id="1eb30-106">Weitere Informationen finden Sie unter [CREATE SELECTIVE XML INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-selective-xml-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1eb30-106">For more information, see [CREATE SELECTIVE XML INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-selective-xml-index-transact-sql).</span></span>  
  
-   <span data-ttu-id="1eb30-107">In der **ADD** -Klausel einer **ALTER** -Anweisung.</span><span class="sxs-lookup"><span data-stu-id="1eb30-107">In the **ADD** clause of an **ALTER** statement.</span></span> <span data-ttu-id="1eb30-108">Weitere Informationen finden Sie unter [ALTER INDEX &#40;selektive XML-Indizes&#41;](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="1eb30-108">For more information, see [ALTER INDEX &#40;Selective XML Indexes&#41;](../indexes/indexes.md).</span></span>  
  
 <span data-ttu-id="1eb30-109">Weitere Informationen über selektive XML-Indizes finden Sie unter [Selektive XML-Indizes &#40;SXI&#41;](../xml/selective-xml-indexes-sxi.md).</span><span class="sxs-lookup"><span data-stu-id="1eb30-109">For more information about selective XML indexes, see [Selective XML Indexes &#40;SXI&#41;](../xml/selective-xml-indexes-sxi.md).</span></span>  
  
##  <a name="understanding-xquery-and-sql-server-types-in-untyped-xml"></a><a name="untyped"></a> <span data-ttu-id="1eb30-110">Grundlegendes zu XQuery- und SQL Server-Typen in nicht typisiertem XML</span><span class="sxs-lookup"><span data-stu-id="1eb30-110">Understanding XQuery and SQL Server Types in Untyped XML</span></span>  
 <span data-ttu-id="1eb30-111">Selektive XML-Indizes unterstützen zwei Typsysteme: XQuery-Typen und [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Typen.</span><span class="sxs-lookup"><span data-stu-id="1eb30-111">Selective XML indexes support two type systems: XQuery types and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] types.</span></span> <span data-ttu-id="1eb30-112">Der indizierte Pfad kann verwendet werden, um entweder eine Entsprechung für einen XQuery-Ausdruck oder um eine Entsprechung für den Rückgabetyp der value()-Methode des XML-Datentyps zu finden.</span><span class="sxs-lookup"><span data-stu-id="1eb30-112">The indexed path can be used either to match an XQuery expression, or to match the return type of the value() method of the XML data type.</span></span>  
  
-   <span data-ttu-id="1eb30-113">Wenn ein zu indizierender Pfad nicht kommentiert ist oder mit dem XQUERY-Schlüsselwort kommentiert ist, entspricht der Pfad einem XQuery-Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="1eb30-113">When a path to index is not annotated, or is annotated with the XQUERY keyword, the path matches an XQuery expression.</span></span> <span data-ttu-id="1eb30-114">Es gibt zwei Varianten von XQUERY-kommentierten Knotenpfaden:</span><span class="sxs-lookup"><span data-stu-id="1eb30-114">There are two variations for XQUERY-annotated node paths:</span></span>  
  
    -   <span data-ttu-id="1eb30-115">Wenn Sie das XQUERY-Schlüsselwort und den XQuery-Datentyp nicht angeben, werden Standardzuordnungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="1eb30-115">If you do not specify the XQUERY keyword and the XQuery data type, then default mappings are used.</span></span> <span data-ttu-id="1eb30-116">In der Regel sind Leistung und Speicher dann nicht optimal.</span><span class="sxs-lookup"><span data-stu-id="1eb30-116">Typically performance and storage are not optimal.</span></span>  
  
    -   <span data-ttu-id="1eb30-117">Wenn Sie das XQUERY-Schlüsselwort und den XQuery-Datentyp sowie optional andere Optimierungshinweise angeben, können Sie die bestmögliche Leistung und den effizientesten möglichen Speicher erzielen.</span><span class="sxs-lookup"><span data-stu-id="1eb30-117">If you specify the XQUERY keyword and the XQuery data type, and optionally other optimization hints, then you can achieve the best possible performance and the most efficient possible storage.</span></span> <span data-ttu-id="1eb30-118">Eine Umwandlung kann jedoch fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="1eb30-118">However, a cast can fail.</span></span>  
  
-   <span data-ttu-id="1eb30-119">Wenn ein zu indizierender Pfad mit dem SQL-Schlüsselwort kommentiert ist, entspricht der Pfad dem Rückgabetyp der value()-Methode des XML-Datentyps.</span><span class="sxs-lookup"><span data-stu-id="1eb30-119">When a path to index is annotated with the SQL keyword, the path matches the return type of the value() method of the XML data type.</span></span> <span data-ttu-id="1eb30-120">Geben Sie den entsprechenden [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datentyp an, bei dem es sich um den Rückgabetypen handelt, den Sie von der value()-Methode erwarten.</span><span class="sxs-lookup"><span data-stu-id="1eb30-120">Specify the appropriate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type, which is the return type that you expect from the value() method.</span></span>  
  
 <span data-ttu-id="1eb30-121">Es gibt feine Unterschiede zwischen dem XML-Typsystem der XQuery-Ausdrücke und dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Typsystem, das für die value()-Methode des XML-Datentyps angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="1eb30-121">There are subtle differences between the XQuery expressions XML type system and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] type system applied to the value() method of the XML data type.</span></span> <span data-ttu-id="1eb30-122">Zu diesen Unterschieden gehören unter anderem:</span><span class="sxs-lookup"><span data-stu-id="1eb30-122">These differences include the following:</span></span>  
  
-   <span data-ttu-id="1eb30-123">Das XQuery-Typsystem beachtet Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="1eb30-123">The XQuery type system is aware of trailing spaces.</span></span> <span data-ttu-id="1eb30-124">So sind zum Beispiel der Semantik des XQuery-Typs nach die Zeichenfolgen"abc" und "abc " nicht identisch, wohingegen diese Zeichenfolgen in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] identisch sind.</span><span class="sxs-lookup"><span data-stu-id="1eb30-124">For example, according to XQuery type semantics, the strings "abc" and "abc " are not equal, while in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] these strings are equal.</span></span>  
  
-   <span data-ttu-id="1eb30-125">XQuery-Gleitkommadatentypen unterstützen die speziellen Werte von +/- 0 (null) und +/- Unendlichkeit.</span><span class="sxs-lookup"><span data-stu-id="1eb30-125">XQuery floating point data types support special values of +/- zero and +/- infinity.</span></span> <span data-ttu-id="1eb30-126">Diese speziellen Werte werden in den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Gleitkommadatentypen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1eb30-126">These special values are not supported in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] floating point data types.</span></span>  
  
### <a name="xquery-types-in-untyped-xml"></a><span data-ttu-id="1eb30-127">XQuery-Typen in nicht typisiertem XML</span><span class="sxs-lookup"><span data-stu-id="1eb30-127">XQuery Types in Untyped XML</span></span>  
  
-   <span data-ttu-id="1eb30-128">XQuery-Typen entsprechen den XQuery-Ausdrücken in allen Methoden des XML-Datentyps, einschließlich der value()-Methode.</span><span class="sxs-lookup"><span data-stu-id="1eb30-128">XQuery types match XQuery expressions in all methods of the XML data type including the value() method.</span></span>  
  
-   <span data-ttu-id="1eb30-129">XQuery-Typen unterstützen diese Optimierungshinweise: node(), SINGLETON, DATA TYPE und MAXLENGTH.</span><span class="sxs-lookup"><span data-stu-id="1eb30-129">XQuery types support these optimization hints: node(), SINGLETON, DATA TYPE, and MAXLENGTH.</span></span>  
  
 <span data-ttu-id="1eb30-130">Für XQuery-Ausdrücke über nicht typisiertem XML können Sie zwischen zwei Vorgangsmodi auswählen:</span><span class="sxs-lookup"><span data-stu-id="1eb30-130">For XQuery expressions over untyped XML, you can choose between two modes of operation:</span></span>  
  
-   <span data-ttu-id="1eb30-131">**Standardmäßiger Zuordnungsmodus**.</span><span class="sxs-lookup"><span data-stu-id="1eb30-131">**Default mapping mode**.</span></span> <span data-ttu-id="1eb30-132">In diesem Modus geben Sie nur den Pfad an, wenn Sie einen selektiven XML-Index erstellen.</span><span class="sxs-lookup"><span data-stu-id="1eb30-132">In this mode, you specify only the path when creating a selective XML index.</span></span>  
  
-   <span data-ttu-id="1eb30-133">**Vom Benutzer angegebener Zuordnungsmodus**.</span><span class="sxs-lookup"><span data-stu-id="1eb30-133">**User-specified mapping mode**.</span></span> <span data-ttu-id="1eb30-134">In diesem Modus geben Sie sowohl den Pfad als auch optionale Optimierungshinweise an.</span><span class="sxs-lookup"><span data-stu-id="1eb30-134">In this mode, you specify both the path and optional optimization hints.</span></span>  
  
 <span data-ttu-id="1eb30-135">Der Standardzuordnungsmodus verwendet eine konservative Speicheroption, die immer sicher und allgemein ist.</span><span class="sxs-lookup"><span data-stu-id="1eb30-135">The default mapping mode uses a conservative storage option which is always safe and general.</span></span> <span data-ttu-id="1eb30-136">Sie kann jedem Ausdruckstyp entsprechen.</span><span class="sxs-lookup"><span data-stu-id="1eb30-136">It can match any expression type.</span></span> <span data-ttu-id="1eb30-137">Eine Einschränkung des Standardzuordnungsmodus ist die nicht optimale Leistung, da eine größere Anzahl von Laufzeitumwandlungen erforderlich ist, und sekundäre Indizes nicht verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="1eb30-137">A limitation of the default mapping mode is less than optimal performance, because an increased number of runtime casts are required, and secondary indexes are not available.</span></span>  
  
 <span data-ttu-id="1eb30-138">Hier ist ein Beispiel für einen selektiven, mit Standardzuordnungen erstellten XML-Index.</span><span class="sxs-lookup"><span data-stu-id="1eb30-138">Here is an example of a selective XML index created with default mappings.</span></span> <span data-ttu-id="1eb30-139">Für alle drei Pfade werden der Standardknotentyp (**xs:untypedAtomic**) und Kardinalität verwendet.</span><span class="sxs-lookup"><span data-stu-id="1eb30-139">For all three paths, the default node type (**xs:untypedAtomic**) and cardinality are used.</span></span>  
  
```sql  
CREATE SELECTIVE XML INDEX example_sxi_UX_default  
ON Tbl(xmlcol)  
FOR  
(  
mypath01 =  '/a/b',  
mypath02 = '/a/b/c',  
mypath03 = '/a/b/d'  
)  
```  
  
 <span data-ttu-id="1eb30-140">Mit dem vom Benutzer angegebene Zuordnungsmodus können Sie einen Typen und die Kardinalität für den Knoten angeben, um eine bessere Leistung zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="1eb30-140">The user-specified mapping mode lets you specify a type and cardinality for the node to obtain better performance.</span></span> <span data-ttu-id="1eb30-141">Diese verbesserte Leistung wird jedoch nur durch Verzicht auf Sicherheit (da eine Umwandlung fehlschlagen kann) und durch Verzicht auf Allgemeinheit (da nur der angegebene Typ mit dem selektiven XML-Index verglichen wird) erreicht.</span><span class="sxs-lookup"><span data-stu-id="1eb30-141">However, this improved performance is achieved by giving up safety - because a cast can fail - and generality - because only the specified type is matched with the selective XML index.</span></span>  
  
 <span data-ttu-id="1eb30-142">Die für nicht typisiertes XML unterstützten XQuery-Typen sind:</span><span class="sxs-lookup"><span data-stu-id="1eb30-142">The XQuery types supported for untyped XML case are:</span></span>  
  
-   <span data-ttu-id="1eb30-143">**xs:boolean**</span><span class="sxs-lookup"><span data-stu-id="1eb30-143">**xs:boolean**</span></span>  
  
-   <span data-ttu-id="1eb30-144">**xs:double**</span><span class="sxs-lookup"><span data-stu-id="1eb30-144">**xs:double**</span></span>  
  
-   <span data-ttu-id="1eb30-145">**xs:string**</span><span class="sxs-lookup"><span data-stu-id="1eb30-145">**xs:string**</span></span>  
  
-   <span data-ttu-id="1eb30-146">**xs:date**</span><span class="sxs-lookup"><span data-stu-id="1eb30-146">**xs:date**</span></span>  
  
-   <span data-ttu-id="1eb30-147">**xs:time**</span><span class="sxs-lookup"><span data-stu-id="1eb30-147">**xs:time**</span></span>  
  
-   <span data-ttu-id="1eb30-148">**xs:dateTime**</span><span class="sxs-lookup"><span data-stu-id="1eb30-148">**xs:dateTime**</span></span>  
  
 <span data-ttu-id="1eb30-149">Wenn der Typ nicht angegeben wird, wird davon ausgegangen, dass der Knoten den **xs:untypedAtomic** -Datentyp aufweist.</span><span class="sxs-lookup"><span data-stu-id="1eb30-149">If the type is not specified, the node is assumed to be of the **xs:untypedAtomic** data type.</span></span>  
  
 <span data-ttu-id="1eb30-150">Sie können den selektiven XML-Index wie nachfolgend aufgeführt optimieren:</span><span class="sxs-lookup"><span data-stu-id="1eb30-150">You can optimize the selective XML index shown in the following manner:</span></span>  
  
```sql  
CREATE SELECTIVE XML INDEX example_sxi_UX_optimized  
ON Tbl(xmlcol)  
FOR  
(  
mypath= '/a/b' as XQUERY 'node()',  
pathX = '/a/b/c' as XQUERY 'xs:double' SINGLETON,  
pathY = '/a/b/d' as XQUERY 'xs:string' MAXLENGTH(200) SINGLETON  
)  
-- mypath - Only the node value is needed; storage is saved.  
-- pathX - Performance is improved; secondary indexes are possible.  
-- pathY - Performance is improved; secondary indexes are possible; storage is saved.  
```  
  
### <a name="sql-server-types-in-untyped-xml"></a><span data-ttu-id="1eb30-151">SQL Server-Typen in nicht typisiertem XML</span><span class="sxs-lookup"><span data-stu-id="1eb30-151">SQL Server Types in Untyped XML</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="1eb30-152">Typen entsprechen dem Rückgabewert der value()-Methode.</span><span class="sxs-lookup"><span data-stu-id="1eb30-152">types match the return value of the value() method.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="1eb30-153">-Typen unterstützen diesen Optimierungshinweis: SINGLETON.</span><span class="sxs-lookup"><span data-stu-id="1eb30-153">types support this optimization hint: SINGLETON.</span></span>  
  
 <span data-ttu-id="1eb30-154">Die Angabe eines Typs ist für Pfade erforderlich, die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Typen zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="1eb30-154">Specifying a type is mandatory for paths that return [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] types.</span></span> <span data-ttu-id="1eb30-155">Verwenden Sie den gleichen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Typ, den Sie in der value()-Methode verwenden würden.</span><span class="sxs-lookup"><span data-stu-id="1eb30-155">Use the same [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] type that you would use in the value() method.</span></span>  
  
 <span data-ttu-id="1eb30-156">Betrachten Sie die folgende Abfrage:</span><span class="sxs-lookup"><span data-stu-id="1eb30-156">Consider the following query:</span></span>  
  
```sql  
SELECT T.record,  
    T.xmldata.value('(/a/b/d)[1]', 'NVARCHAR(200)')  
FROM myXMLTable T  
```  
  
 <span data-ttu-id="1eb30-157">Die angegebene Abfrage gibt einen Wert des Pfads `/a/b/d` zurück, der in einen NVARCHAR(200)-Datentyp gepackt ist, sodass der für den Knoten anzugebende Datentyp offensichtlich ist.</span><span class="sxs-lookup"><span data-stu-id="1eb30-157">The specified query returns a value from the path `/a/b/d` packed into an NVARCHAR(200) data type, so the data type to specify for the node is obvious.</span></span> <span data-ttu-id="1eb30-158">Es gibt jedoch kein Schema, um die Kardinalität des Knotens in nicht typisiertem XML anzugeben.</span><span class="sxs-lookup"><span data-stu-id="1eb30-158">However there is no schema to specify the cardinality of the node in untyped XML.</span></span> <span data-ttu-id="1eb30-159">Um diesen Knoten anzugeben ( `d` tritt höchstens einmal unter dem übergeordneten Knoten `b`auf), erstellen Sie einen selektiven XML-Index, der den Optimierungshinweis SINGLETON wie folgt verwendet:</span><span class="sxs-lookup"><span data-stu-id="1eb30-159">To specify that node `d` appears at most once under its parent node `b`, create a selective XML index that uses the SINGLETON optimization hint as follows:</span></span>  
  
```sql  
CREATE SELECTIVE XML INDEX example_sxi_US  
ON Tbl(xmlcol)  
FOR  
(  
node1223 = '/a/b/d' as SQL NVARCHAR(200) SINGLETON  
)  
```  
  

  
##  <a name="understanding-selective-xml-index-support-for-typed-xml"></a><a name="typed"></a> <span data-ttu-id="1eb30-160">Grundlegendes zu selektiver XML-Indexunterstützung für typisiertes XML</span><span class="sxs-lookup"><span data-stu-id="1eb30-160">Understanding Selective XML Index support for typed XML</span></span>  
 <span data-ttu-id="1eb30-161">Typisiertes XML in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ist ein Schema, das einem bestimmten XML-Dokument zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="1eb30-161">Typed XML in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is a schema associated with a given XML document.</span></span> <span data-ttu-id="1eb30-162">Das Schema definiert die Gesamtdokumentstruktur und Typen von Knoten.</span><span class="sxs-lookup"><span data-stu-id="1eb30-162">The schema defines overall document structure and types of nodes.</span></span> <span data-ttu-id="1eb30-163">Ist ein Schema vorhanden, wendet der selektive XML-Index die Schemastruktur an, wenn der Benutzer Pfade höher stuft. Daher ist es nicht notwendig, die XQUERY-Typen für Pfade anzugeben.</span><span class="sxs-lookup"><span data-stu-id="1eb30-163">If a schema exists, Selective XML Index applies the schema structure when the user promotes paths, so there is no need to specify the XQUERY types for paths.</span></span>  
  
 <span data-ttu-id="1eb30-164">Ein selektiver XML-Index unterstützt die folgenden XSD-Typen:</span><span class="sxs-lookup"><span data-stu-id="1eb30-164">Selective XML Index supports following XSD types:</span></span>  
  
-   <span data-ttu-id="1eb30-165">**xs:anyUri**</span><span class="sxs-lookup"><span data-stu-id="1eb30-165">**xs:anyUri**</span></span>  
  
-   <span data-ttu-id="1eb30-166">**xs:boolean**</span><span class="sxs-lookup"><span data-stu-id="1eb30-166">**xs:boolean**</span></span>  
  
-   <span data-ttu-id="1eb30-167">**xs:date**</span><span class="sxs-lookup"><span data-stu-id="1eb30-167">**xs:date**</span></span>  
  
-   <span data-ttu-id="1eb30-168">**xs:dateTime**</span><span class="sxs-lookup"><span data-stu-id="1eb30-168">**xs:dateTime**</span></span>  
  
-   <span data-ttu-id="1eb30-169">**xs:day**</span><span class="sxs-lookup"><span data-stu-id="1eb30-169">**xs:day**</span></span>  
  
-   <span data-ttu-id="1eb30-170">**xs:decimal**</span><span class="sxs-lookup"><span data-stu-id="1eb30-170">**xs:decimal**</span></span>  
  
-   <span data-ttu-id="1eb30-171">**xs:double**</span><span class="sxs-lookup"><span data-stu-id="1eb30-171">**xs:double**</span></span>  
  
-   <span data-ttu-id="1eb30-172">**xs: float**</span><span class="sxs-lookup"><span data-stu-id="1eb30-172">**xs:float**</span></span>  
  
-   <span data-ttu-id="1eb30-173">**xs:int**</span><span class="sxs-lookup"><span data-stu-id="1eb30-173">**xs:int**</span></span>  
  
-   <span data-ttu-id="1eb30-174">**xs:integer**</span><span class="sxs-lookup"><span data-stu-id="1eb30-174">**xs:integer**</span></span>  
  
-   <span data-ttu-id="1eb30-175">**xs:language**</span><span class="sxs-lookup"><span data-stu-id="1eb30-175">**xs:language**</span></span>  
  
-   <span data-ttu-id="1eb30-176">**xs:long**</span><span class="sxs-lookup"><span data-stu-id="1eb30-176">**xs:long**</span></span>  
  
-   <span data-ttu-id="1eb30-177">**xs:name**</span><span class="sxs-lookup"><span data-stu-id="1eb30-177">**xs:name**</span></span>  
  
-   <span data-ttu-id="1eb30-178">**xs:NCName**</span><span class="sxs-lookup"><span data-stu-id="1eb30-178">**xs:NCName**</span></span>  
  
-   <span data-ttu-id="1eb30-179">**xs:negativeInteger**</span><span class="sxs-lookup"><span data-stu-id="1eb30-179">**xs:negativeInteger**</span></span>  
  
-   <span data-ttu-id="1eb30-180">**xs:nmtoken**</span><span class="sxs-lookup"><span data-stu-id="1eb30-180">**xs:nmtoken**</span></span>  
  
-   <span data-ttu-id="1eb30-181">**xs:nonNegativeInteger**</span><span class="sxs-lookup"><span data-stu-id="1eb30-181">**xs:nonNegativeInteger**</span></span>  
  
-   <span data-ttu-id="1eb30-182">**xs:nonPositiveInteger**</span><span class="sxs-lookup"><span data-stu-id="1eb30-182">**xs:nonPositiveInteger**</span></span>  
  
-   <span data-ttu-id="1eb30-183">**xs:positiveInteger**</span><span class="sxs-lookup"><span data-stu-id="1eb30-183">**xs:positiveInteger**</span></span>  
  
-   <span data-ttu-id="1eb30-184">**xs:qname**</span><span class="sxs-lookup"><span data-stu-id="1eb30-184">**xs:qname**</span></span>  
  
-   <span data-ttu-id="1eb30-185">**xs:short**</span><span class="sxs-lookup"><span data-stu-id="1eb30-185">**xs:short**</span></span>  
  
-   <span data-ttu-id="1eb30-186">**xs:string**</span><span class="sxs-lookup"><span data-stu-id="1eb30-186">**xs:string**</span></span>  
  
-   <span data-ttu-id="1eb30-187">**xs:time**</span><span class="sxs-lookup"><span data-stu-id="1eb30-187">**xs:time**</span></span>  
  
-   <span data-ttu-id="1eb30-188">**xs:token**</span><span class="sxs-lookup"><span data-stu-id="1eb30-188">**xs:token**</span></span>  
  
-   <span data-ttu-id="1eb30-189">**xs:unsignedByte**</span><span class="sxs-lookup"><span data-stu-id="1eb30-189">**xs:unsignedByte**</span></span>  
  
-   <span data-ttu-id="1eb30-190">**xs:unsignedInt**</span><span class="sxs-lookup"><span data-stu-id="1eb30-190">**xs:unsignedInt**</span></span>  
  
-   <span data-ttu-id="1eb30-191">**xs:unsignedLong**</span><span class="sxs-lookup"><span data-stu-id="1eb30-191">**xs:unsignedLong**</span></span>  
  
-   <span data-ttu-id="1eb30-192">**xs:unsignedShort**</span><span class="sxs-lookup"><span data-stu-id="1eb30-192">**xs:unsignedShort**</span></span>  
  
 <span data-ttu-id="1eb30-193">Wenn ein selektiver XML-Index für ein Dokument erstellt wird, dem ein Schema zugeordnet ist, tritt beim Angeben eines XQUERY-Typs bei der Indexerstellung oder bei der Änderung ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="1eb30-193">When Selective XML Index is created over a document that has schema associated with it, specifying a XQUERY type at index creation or altering returns an error.</span></span> <span data-ttu-id="1eb30-194">Der Benutzer kann SQL-Typanmerkungen bei der Pfadheraufstufung verwenden.</span><span class="sxs-lookup"><span data-stu-id="1eb30-194">The user can use SQL type annotations in the path promotion part.</span></span> <span data-ttu-id="1eb30-195">Der SQL-Typ muss eine gültige Konvertierung des XSD-Typs sein, der im Schema definiert ist, oder es wird ein Fehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="1eb30-195">The SQL type must be a valid conversion from the XSD type defined in the schema, or an error is thrown.</span></span> <span data-ttu-id="1eb30-196">Es werden alle SQL-Typen unterstützt, die in XSD über eine entsprechende Darstellung verfügen, mit Ausnahme der Typen für Datum/Uhrzeit.</span><span class="sxs-lookup"><span data-stu-id="1eb30-196">All SQL types that have adequate representation in XSD are supported, with an exception of date/time types.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1eb30-197">Der selektive Index wird verwendet, wenn der bei der Pfadhöherstufung des selektiven XML-Index angegebene Typ mit dem Rückgabewert der value()-Methode identisch ist.</span><span class="sxs-lookup"><span data-stu-id="1eb30-197">The selective index is used if the type specified in the Selective XML Index path promotion is the same as the value() method return value.</span></span>  
  
 <span data-ttu-id="1eb30-198">Die folgenden Optimierungshinweise können mit typisierten XML-Dokumenten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="1eb30-198">The following optimization hints can be used with typed XML documents:</span></span>  
  
-   <span data-ttu-id="1eb30-199">node()-Optimierungshinweis.</span><span class="sxs-lookup"><span data-stu-id="1eb30-199">node() optimization hint.</span></span>  
  
-   <span data-ttu-id="1eb30-200">Der MAXLENGTH-Optimierungshinweis kann mit xs:string-Typen verwendet werden, um den indizierten Wert zu kürzen.</span><span class="sxs-lookup"><span data-stu-id="1eb30-200">MAXLENGTH optimization hint can be used with xs:string types to shorten the indexed value.</span></span>  
  
 <span data-ttu-id="1eb30-201">Weitere Informationen zu Optimierungshinweisen finden Sie unter [Angeben von Optimierungshinweisen](#hints).</span><span class="sxs-lookup"><span data-stu-id="1eb30-201">For more information about optimization hints, see [Specifying Optimization Hints](#hints).</span></span>  
  
##  <a name="specifying-paths"></a><a name="paths"></a> <span data-ttu-id="1eb30-202">Angeben von Pfaden</span><span class="sxs-lookup"><span data-stu-id="1eb30-202">Specifying Paths</span></span>  
 <span data-ttu-id="1eb30-203">Mit einem selektiven XML-Index können Sie nur eine Teilmenge der Knoten aus den gespeicherten XML-Daten, die für die voraussichtlich durchgeführten Abfragen relevant sind, indizieren.</span><span class="sxs-lookup"><span data-stu-id="1eb30-203">A selective XML index lets you index only a subset of nodes from the stored XML data that are relevant for the queries that you expect to run.</span></span> <span data-ttu-id="1eb30-204">Wenn die Teilmenge der relevanten Knoten viel kleiner als die Gesamtzahl der Knoten im XML-Dokument ist, speichert der selektive XML-Index nur die relevanten Knoten.</span><span class="sxs-lookup"><span data-stu-id="1eb30-204">When the subset of relevant nodes is much smaller than the total number of nodes in the XML document, the selective XML index stores only the relevant nodes.</span></span> <span data-ttu-id="1eb30-205">Um von einem selektiven XML-Index profitieren zu können, identifizieren Sie die richtige Teilmenge der Knoten für die Indizierung.</span><span class="sxs-lookup"><span data-stu-id="1eb30-205">To benefit from a selective XML index, identify the correct subset of nodes to index.</span></span>  
  
### <a name="choosing-the-nodes-to-index"></a><span data-ttu-id="1eb30-206">Auswählen der zu indizierenden Knoten</span><span class="sxs-lookup"><span data-stu-id="1eb30-206">Choosing the nodes to index</span></span>  
 <span data-ttu-id="1eb30-207">Mithilfe der beiden folgenden einfachen Prinzipien können Sie die richtige Teilmenge der Knoten ermitteln, die einem selektiven XML-Index hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="1eb30-207">You can use the following two simple principles to identify the correct subset of nodes to add to a selective XML index.</span></span>  
  
1.  <span data-ttu-id="1eb30-208">**Prinzip 1:** Indizieren Sie alle Knoten, die Sie untersuchen müssen, um einen bestimmten XQuery-Ausdruck auszuwerten.</span><span class="sxs-lookup"><span data-stu-id="1eb30-208">**Principle 1**: To evaluate a given XQuery expression, index all nodes that you need to examine.</span></span>  
  
    -   <span data-ttu-id="1eb30-209">Indizieren Sie alle Knoten, deren Vorhandensein oder Wert im XQuery-Ausdruck verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1eb30-209">Index all nodes whose existence or value is used in the XQuery expression.</span></span>  
  
    -   <span data-ttu-id="1eb30-210">Indizieren Sie alle Knoten im XQuery-Ausdruck, auf den XQuery-Prädikate angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="1eb30-210">Index all nodes in the XQuery expression on which XQuery predicates are applied.</span></span>  
  
     <span data-ttu-id="1eb30-211">Betrachten Sie die folgende einfache Abfrage des [Beispiel-XML-Dokuments](#sample) in diesem Thema:</span><span class="sxs-lookup"><span data-stu-id="1eb30-211">Consider the following simple query over the [sample XML document](#sample) in this topic:</span></span>  
  
    ```sql  
    SELECT T.record FROM myXMLTable T  
    WHERE T.xmldata.exist('/a/b[./c = "43"]') = 1  
    ```  
  
     <span data-ttu-id="1eb30-212">Um die XML-Instanzen zurückzugeben, die diese Abfrage erfüllen, muss ein selektiver XML-Index zwei Knoten in jeder XML-Instanz untersuchen:</span><span class="sxs-lookup"><span data-stu-id="1eb30-212">In order to return the XML instances that satisfy this query, a selective XML index needs to examine two nodes in every XML instance:</span></span>  
  
    -   <span data-ttu-id="1eb30-213">Knoten `c`, da sein Wert im XQuery-Ausdruck verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1eb30-213">Node `c`, because its value is used in the XQuery expression.</span></span>  
  
    -   <span data-ttu-id="1eb30-214">Knoten `b`, da ein Prädikat auf den Knoten`b` im XQuery-Ausdruck angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="1eb30-214">Node `b`, because a predicate is applied over node`b` in the XQuery expression.</span></span>  
  
2.  <span data-ttu-id="1eb30-215">**Prinzip 2:** Indizieren Sie alle Knoten, die zum Auswerten eines bestimmten XQuery-Ausdrucks erforderlich sind, um die optimale Leistung zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="1eb30-215">**Principle 2**: For best performance, index all nodes that are required to evaluate a given XQuery expression.</span></span> <span data-ttu-id="1eb30-216">Wenn Sie nur einige der Knoten indizieren, dann verbessert der selektive XML-Index die Auswertung der Teilausdrücke, die nur indizierte Knoten umfassen.</span><span class="sxs-lookup"><span data-stu-id="1eb30-216">If you index only some of the nodes, then the selective XML index improves the evaluation of sub-expressions that include only indexed nodes.</span></span>  
  
 <span data-ttu-id="1eb30-217">Um die Leistung der oben aufgeführten SELECT-Anweisung zu verbessern, können Sie den folgenden selektiven XML-Index erstellen:</span><span class="sxs-lookup"><span data-stu-id="1eb30-217">To improve the performance of the SELECT statement shown above, you can create the following selective XML index:</span></span>  
  
```sql  
CREATE SELECTIVE XML INDEX simple_sxi  
ON Tbl(xmlcol)  
FOR  
(  
    path123 =  '/a/b',  
    path124 =  '/a/b/c'  
)  
```  
  
### <a name="indexing-identical-paths"></a><span data-ttu-id="1eb30-218">Indizieren von identischen Pfaden</span><span class="sxs-lookup"><span data-stu-id="1eb30-218">Indexing identical paths</span></span>  
 <span data-ttu-id="1eb30-219">Sie können keine identischen Pfade als gleichen Datentyp unter verschiedenen Pfadnamen höher stufen.</span><span class="sxs-lookup"><span data-stu-id="1eb30-219">You cannot promote identical paths as the same data type under different path names.</span></span> <span data-ttu-id="1eb30-220">Die folgende Abfrage löst z. B. einen Fehler aus, da `pathOne` und `pathTwo` identisch sind:</span><span class="sxs-lookup"><span data-stu-id="1eb30-220">For example, the following query raises an error, because `pathOne` and `pathTwo` are identical:</span></span>  
  
```sql  
CREATE SELECTIVE INDEX test_simple_sxi ON T1(xmlCol)  
FOR  
(  
    pathOne = 'book/authors/authorID' AS XQUERY 'xs:string',  
    pathTwo = 'book/authors/authorID' AS XQUERY 'xs:string'  
)  
```  
  
 <span data-ttu-id="1eb30-221">Sie können jedoch identische Pfade als andere Datentypen mit anderen Namen höher stufen.</span><span class="sxs-lookup"><span data-stu-id="1eb30-221">However, you can promote identical paths as different data types with different names.</span></span> <span data-ttu-id="1eb30-222">So ist die folgende Abfrage beispielsweise jetzt akzeptabel, da die Datentypen verschieden sind:</span><span class="sxs-lookup"><span data-stu-id="1eb30-222">For example, the following query is now acceptable, because the data types are different:</span></span>  
  
```sql  
CREATE SELECTIVE INDEX test_simple_sxi ON T1(xmlCol)  
FOR  
(  
    pathOne = 'book/authors/authorID' AS XQUERY 'xs:double',  
    pathTwo = 'book/authors/authorID' AS XQUERY 'xs:string'  
)  
```  
  
### <a name="examples"></a><span data-ttu-id="1eb30-223">Beispiele</span><span class="sxs-lookup"><span data-stu-id="1eb30-223">Examples</span></span>  
 <span data-ttu-id="1eb30-224">Hier sind einige weitere Beispiele zum Auswählen der richtigen Knoten, die für verschiedene XQuery-Typen zu indizieren sind.</span><span class="sxs-lookup"><span data-stu-id="1eb30-224">Here are some additional examples of selecting the correct nodes to index for different XQuery types.</span></span>  
  
 <span data-ttu-id="1eb30-225">**Beispiel 1**</span><span class="sxs-lookup"><span data-stu-id="1eb30-225">**Example 1**</span></span>  
  
 <span data-ttu-id="1eb30-226">Hier ist eine einfache XQuery aufgeführt, die die exist()-Methode verwendet:</span><span class="sxs-lookup"><span data-stu-id="1eb30-226">Here is a simple XQuery that uses the exist() method:</span></span>  
  
```sql  
SELECT T.record FROM myXMLTable T  
WHERE T.xmldata.exist('/a/b/c/d/e/h') = 1  
```  
  
 <span data-ttu-id="1eb30-227">In der folgenden Tabelle sind die Knoten aufgeführt, die indiziert werden müssen, damit diese Abfrage den selektiven XML-Index verwendet.</span><span class="sxs-lookup"><span data-stu-id="1eb30-227">The following table shows the nodes that should be indexed to let this query use the selective XML index.</span></span>  
  
|<span data-ttu-id="1eb30-228">In den Index einzuschließender Knoten</span><span class="sxs-lookup"><span data-stu-id="1eb30-228">Node to include in the index</span></span>|<span data-ttu-id="1eb30-229">Grund zum Indizieren dieses Knotens</span><span class="sxs-lookup"><span data-stu-id="1eb30-229">Reason for indexing this node</span></span>|  
|----------------------------------|-----------------------------------|  
|<span data-ttu-id="1eb30-230">**/a/b/c/d/e/h**</span><span class="sxs-lookup"><span data-stu-id="1eb30-230">**/a/b/c/d/e/h**</span></span>|<span data-ttu-id="1eb30-231">Das Vorhandensein des Knotens `h` wird in der exist()-Methode ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="1eb30-231">The existence of node `h` is evaluated in the exist() method.</span></span>|  
  
 <span data-ttu-id="1eb30-232">**Beispiel 2**</span><span class="sxs-lookup"><span data-stu-id="1eb30-232">**Example 2**</span></span>  
  
 <span data-ttu-id="1eb30-233">Hier ist eine komplexere Variante der vorherigen XQuery mit einem angewendeten Prädikat aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="1eb30-233">Here is a more complex variation of the previous XQuery, with a predicate applied:</span></span>  
  
```sql  
SELECT T.record FROM myXMLTable T  
WHERE T.xmldata.exist('/a/b/c/d/e[./f = "SQL"]') = 1  
```  
  
 <span data-ttu-id="1eb30-234">In der folgenden Tabelle sind die Knoten aufgeführt, die indiziert werden müssen, damit diese Abfrage den selektiven XML-Index verwendet.</span><span class="sxs-lookup"><span data-stu-id="1eb30-234">The following table shows the nodes that should be indexed to let this query use the selective XML index.</span></span>  
  
|<span data-ttu-id="1eb30-235">In den Index einzuschließender Knoten</span><span class="sxs-lookup"><span data-stu-id="1eb30-235">Node to include in the index</span></span>|<span data-ttu-id="1eb30-236">Grund zum Indizieren dieses Knotens</span><span class="sxs-lookup"><span data-stu-id="1eb30-236">Reason for indexing this node</span></span>|  
|----------------------------------|-----------------------------------|  
|<span data-ttu-id="1eb30-237">**/a/b/c/d/e**</span><span class="sxs-lookup"><span data-stu-id="1eb30-237">**/a/b/c/d/e**</span></span>|<span data-ttu-id="1eb30-238">Ein Prädikat wird auf den Knoten `e`angewendet.</span><span class="sxs-lookup"><span data-stu-id="1eb30-238">A predicate is applied over node `e`.</span></span>|  
|<span data-ttu-id="1eb30-239">**/a/b/c/d/e/f**</span><span class="sxs-lookup"><span data-stu-id="1eb30-239">**/a/b/c/d/e/f**</span></span>|<span data-ttu-id="1eb30-240">Der Wert des Knotens `f` wird innerhalb des Prädikats ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="1eb30-240">The value of node `f` is evaluated inside the predicate.</span></span>|  
  
 <span data-ttu-id="1eb30-241">**Beispiel 3**</span><span class="sxs-lookup"><span data-stu-id="1eb30-241">**Example 3**</span></span>  
  
 <span data-ttu-id="1eb30-242">Hier ist eine komplexe Abfrage mit einer value()-Klausel aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="1eb30-242">Here is a more complex query with a value() clause:</span></span>  
  
```sql  
SELECT T.record,  
    T.xmldata.value('(/a/b/c/d/e[./f = "SQL"]/g)[1]', 'nvarchar(100)')  
FROM myXMLTable T  
```  
  
 <span data-ttu-id="1eb30-243">In der folgenden Tabelle sind die Knoten aufgeführt, die indiziert werden müssen, damit diese Abfrage den selektiven XML-Index verwendet.</span><span class="sxs-lookup"><span data-stu-id="1eb30-243">The following table shows the nodes that should be indexed to let this query use the selective XML index.</span></span>  
  
|<span data-ttu-id="1eb30-244">In den Index einzuschließender Knoten</span><span class="sxs-lookup"><span data-stu-id="1eb30-244">Node to include in the index</span></span>|<span data-ttu-id="1eb30-245">Grund zum Indizieren dieses Knotens</span><span class="sxs-lookup"><span data-stu-id="1eb30-245">Reason for indexing this node</span></span>|  
|----------------------------------|-----------------------------------|  
|<span data-ttu-id="1eb30-246">**/a/b/c/d/e**</span><span class="sxs-lookup"><span data-stu-id="1eb30-246">**/a/b/c/d/e**</span></span>|<span data-ttu-id="1eb30-247">Ein Prädikat wird auf den Knoten `e`angewendet.</span><span class="sxs-lookup"><span data-stu-id="1eb30-247">A predicate is applied over node `e`.</span></span>|  
|<span data-ttu-id="1eb30-248">**/a/b/c/d/e/f**</span><span class="sxs-lookup"><span data-stu-id="1eb30-248">**/a/b/c/d/e/f**</span></span>|<span data-ttu-id="1eb30-249">Der Wert des Knotens `f` wird innerhalb des Prädikats ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="1eb30-249">The value of node `f` is evaluated inside the predicate.</span></span>|  
|<span data-ttu-id="1eb30-250">**/a/b/c/d/e/g**</span><span class="sxs-lookup"><span data-stu-id="1eb30-250">**/a/b/c/d/e/g**</span></span>|<span data-ttu-id="1eb30-251">Der Wert des Knotens `g` wird von der value()-Methode zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="1eb30-251">The value of node `g` is returned by the value() method.</span></span>|  
  
 <span data-ttu-id="1eb30-252">**Beispiel 4**</span><span class="sxs-lookup"><span data-stu-id="1eb30-252">**Example 4**</span></span>  
  
 <span data-ttu-id="1eb30-253">Hier ist eine Abfrage aufgeführt, die eine FLWOR-Klausel innerhalb einer exist()-Klausel verwendet.</span><span class="sxs-lookup"><span data-stu-id="1eb30-253">Here is a query that uses a FLWOR clause inside an exist() clause.</span></span> <span data-ttu-id="1eb30-254">(Der Name "FLWOR" leitet sich von den fünf Klauseln ab, aus denen sich ein FLWOR-Ausdruck von XQuery zusammensetzen kann: for, let, where, order by und return.)</span><span class="sxs-lookup"><span data-stu-id="1eb30-254">(The name FLWOR comes from the five clauses that can make up an XQuery FLWOR expression: for, let, where, order by, and return.)</span></span>  
  
```sql  
SELECT T.record FROM myXMLTable T  
WHERE T.xmldata.exist('  
  For $x in /a/b/c/d/e  
  Where $x/f = "SQL"  
  Return $x/g  
') = 1  
```  
  
 <span data-ttu-id="1eb30-255">In der folgenden Tabelle sind die Knoten aufgeführt, die indiziert werden müssen, damit diese Abfrage den selektiven XML-Index verwendet.</span><span class="sxs-lookup"><span data-stu-id="1eb30-255">The following table shows the nodes that should be indexed to let this query use the selective XML index.</span></span>  
  
|<span data-ttu-id="1eb30-256">In den Index einzuschließender Knoten</span><span class="sxs-lookup"><span data-stu-id="1eb30-256">Node to include in the index</span></span>|<span data-ttu-id="1eb30-257">Grund zum Indizieren dieses Knotens</span><span class="sxs-lookup"><span data-stu-id="1eb30-257">Reason for indexing this node</span></span>|  
|----------------------------------|-----------------------------------|  
|<span data-ttu-id="1eb30-258">**/a/b/c/d/e**</span><span class="sxs-lookup"><span data-stu-id="1eb30-258">**/a/b/c/d/e**</span></span>|<span data-ttu-id="1eb30-259">Das Vorhandensein des Knotens `e` wird in der FLWOR-Klausel ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="1eb30-259">The existence of node `e` is evaluated in the FLWOR clause.</span></span>|  
|<span data-ttu-id="1eb30-260">**/a/b/c/d/e/f**</span><span class="sxs-lookup"><span data-stu-id="1eb30-260">**/a/b/c/d/e/f**</span></span>|<span data-ttu-id="1eb30-261">Der Wert des Knotens `f` wird in der FLWOR-Klausel ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="1eb30-261">The value of node `f` is evaluated in the FLWOR clause.</span></span>|  
|<span data-ttu-id="1eb30-262">**/a/b/c/d/e/g**</span><span class="sxs-lookup"><span data-stu-id="1eb30-262">**/a/b/c/d/e/g**</span></span>|<span data-ttu-id="1eb30-263">Das Vorhandensein des Knotens `g` wird von der exist()-Methode ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="1eb30-263">The existence of node `g` is evaluated by the exist() method.</span></span>|  
  

  
##  <a name="specifying-optimization-hints"></a><a name="hints"></a> <span data-ttu-id="1eb30-264">Angeben von Optimierungshinweisen</span><span class="sxs-lookup"><span data-stu-id="1eb30-264">Specifying Optimization Hints</span></span>  
 <span data-ttu-id="1eb30-265">Sie können optionale Optimierungshinweise verwenden, um zusätzliche Mappingdetails für einen Knoten anzugeben, der von einem selektiven XML-Index indiziert wird.</span><span class="sxs-lookup"><span data-stu-id="1eb30-265">You can use optional optimization hints to specify additional mapping details for a node indexed by a selective XML index.</span></span> <span data-ttu-id="1eb30-266">Sie können z. B. den Datentyp und die Kardinalität des Knotens sowie bestimmte Informationen zur Struktur der Daten angeben.</span><span class="sxs-lookup"><span data-stu-id="1eb30-266">For example, you can specify the data type and cardinality of the node, and certain information about the structure of the data.</span></span> <span data-ttu-id="1eb30-267">Diese zusätzlichen Informationen unterstützen eine bessere Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="1eb30-267">This additional information supports better mapping.</span></span> <span data-ttu-id="1eb30-268">Sie ermöglichen darüber hinaus eine Verbesserungen der Leistung und Speichereinsparungen oder sogar beides.</span><span class="sxs-lookup"><span data-stu-id="1eb30-268">It also results in improvements in performance or savings in storage, or both.</span></span>  
  
 <span data-ttu-id="1eb30-269">Die Verwendung von Optimierungshinweisen ist optional.</span><span class="sxs-lookup"><span data-stu-id="1eb30-269">The use of optimization hints is optional.</span></span> <span data-ttu-id="1eb30-270">Sie können stets die Standardzuordnungen übernehmen, die zuverlässig sind, möglicherweise jedoch keine optimale Leistung und Speicher bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="1eb30-270">You can always accept the default mappings, which are reliable but may not provide optimal performance and storage.</span></span>  
  
 <span data-ttu-id="1eb30-271">Einige Optimierungshinweise, z.B. der SINGLETON-Hinweis, schränken Ihre Daten ein.</span><span class="sxs-lookup"><span data-stu-id="1eb30-271">Some optimization hints - for example, the SINGLETON hint - introduce constraints over your data.</span></span> <span data-ttu-id="1eb30-272">In einigen Fällen werden möglicherweise Fehler ausgelöst, wenn diese Einschränkungen nicht erfüllt werden.</span><span class="sxs-lookup"><span data-stu-id="1eb30-272">In some cases, errors may be raised when those constraints are not met.</span></span>  
  
### <a name="benefits-of-optimization-hints"></a><span data-ttu-id="1eb30-273">Vorteile von Optimierungshinweisen</span><span class="sxs-lookup"><span data-stu-id="1eb30-273">Benefits of Optimization Hints</span></span>  
 <span data-ttu-id="1eb30-274">In der folgenden Tabelle sind die Optimierungshinweise aufgeführt, die einen effizienteren Speicher oder eine verbesserte Leistung ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="1eb30-274">The following table identifies the optimization hints that support more efficient storage or improved performance.</span></span>  
  
|<span data-ttu-id="1eb30-275">Optimierungshinweis</span><span class="sxs-lookup"><span data-stu-id="1eb30-275">Optimization hint</span></span>|<span data-ttu-id="1eb30-276">Effizienterer Speicher</span><span class="sxs-lookup"><span data-stu-id="1eb30-276">More efficient storage</span></span>|<span data-ttu-id="1eb30-277">Verbesserte Leistung</span><span class="sxs-lookup"><span data-stu-id="1eb30-277">Improved performance</span></span>|  
|-----------------------|----------------------------|--------------------------|  
|<span data-ttu-id="1eb30-278">**node()**</span><span class="sxs-lookup"><span data-stu-id="1eb30-278">**node()**</span></span>|<span data-ttu-id="1eb30-279">Ja</span><span class="sxs-lookup"><span data-stu-id="1eb30-279">Yes</span></span>|<span data-ttu-id="1eb30-280">Nein</span><span class="sxs-lookup"><span data-stu-id="1eb30-280">No</span></span>|  
|<span data-ttu-id="1eb30-281">**SINGLETON**</span><span class="sxs-lookup"><span data-stu-id="1eb30-281">**SINGLETON**</span></span>|<span data-ttu-id="1eb30-282">Nein</span><span class="sxs-lookup"><span data-stu-id="1eb30-282">No</span></span>|<span data-ttu-id="1eb30-283">Ja</span><span class="sxs-lookup"><span data-stu-id="1eb30-283">Yes</span></span>|  
|<span data-ttu-id="1eb30-284">**DATA TYPE**</span><span class="sxs-lookup"><span data-stu-id="1eb30-284">**DATA TYPE**</span></span>|<span data-ttu-id="1eb30-285">Ja</span><span class="sxs-lookup"><span data-stu-id="1eb30-285">Yes</span></span>|<span data-ttu-id="1eb30-286">Ja</span><span class="sxs-lookup"><span data-stu-id="1eb30-286">Yes</span></span>|  
|<span data-ttu-id="1eb30-287">**MAXLENGTH**</span><span class="sxs-lookup"><span data-stu-id="1eb30-287">**MAXLENGTH**</span></span>|<span data-ttu-id="1eb30-288">Ja</span><span class="sxs-lookup"><span data-stu-id="1eb30-288">Yes</span></span>|<span data-ttu-id="1eb30-289">Ja</span><span class="sxs-lookup"><span data-stu-id="1eb30-289">Yes</span></span>|  
  
### <a name="optimization-hints-and-data-types"></a><span data-ttu-id="1eb30-290">Optimierungshinweise und Datentypen</span><span class="sxs-lookup"><span data-stu-id="1eb30-290">Optimization Hints and Data Types</span></span>  
 <span data-ttu-id="1eb30-291">Sie können Knoten als XQuery-Datentypen oder als [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datentypen indizieren.</span><span class="sxs-lookup"><span data-stu-id="1eb30-291">You can index nodes as XQuery data types or as [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types.</span></span> <span data-ttu-id="1eb30-292">In der folgenden Tabelle ist aufgeführt, welche Optimierungshinweise für die einzelnen Datentypen unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="1eb30-292">The following table shows which optimization hints are supported with each data type.</span></span>  
  
|<span data-ttu-id="1eb30-293">Optimierungshinweis</span><span class="sxs-lookup"><span data-stu-id="1eb30-293">Optimization hint</span></span>|<span data-ttu-id="1eb30-294">XQuery-Datentypen</span><span class="sxs-lookup"><span data-stu-id="1eb30-294">XQuery data types</span></span>|<span data-ttu-id="1eb30-295">SQL-Datentypen</span><span class="sxs-lookup"><span data-stu-id="1eb30-295">SQL data types</span></span>|  
|-----------------------|-----------------------|--------------------|  
|<span data-ttu-id="1eb30-296">**node()**</span><span class="sxs-lookup"><span data-stu-id="1eb30-296">**node()**</span></span>|<span data-ttu-id="1eb30-297">Ja</span><span class="sxs-lookup"><span data-stu-id="1eb30-297">Yes</span></span>|<span data-ttu-id="1eb30-298">Nein</span><span class="sxs-lookup"><span data-stu-id="1eb30-298">No</span></span>|  
|<span data-ttu-id="1eb30-299">**SINGLETON**</span><span class="sxs-lookup"><span data-stu-id="1eb30-299">**SINGLETON**</span></span>|<span data-ttu-id="1eb30-300">Ja</span><span class="sxs-lookup"><span data-stu-id="1eb30-300">Yes</span></span>|<span data-ttu-id="1eb30-301">Ja</span><span class="sxs-lookup"><span data-stu-id="1eb30-301">Yes</span></span>|  
|<span data-ttu-id="1eb30-302">**DATA TYPE**</span><span class="sxs-lookup"><span data-stu-id="1eb30-302">**DATA TYPE**</span></span>|<span data-ttu-id="1eb30-303">Ja</span><span class="sxs-lookup"><span data-stu-id="1eb30-303">Yes</span></span>|<span data-ttu-id="1eb30-304">Nein</span><span class="sxs-lookup"><span data-stu-id="1eb30-304">No</span></span>|  
|<span data-ttu-id="1eb30-305">**MAXLENGTH**</span><span class="sxs-lookup"><span data-stu-id="1eb30-305">**MAXLENGTH**</span></span>|<span data-ttu-id="1eb30-306">Ja</span><span class="sxs-lookup"><span data-stu-id="1eb30-306">Yes</span></span>|<span data-ttu-id="1eb30-307">Nein</span><span class="sxs-lookup"><span data-stu-id="1eb30-307">No</span></span>|  
  
### <a name="node-optimization-hint"></a><span data-ttu-id="1eb30-308">node()-Optimierungshinweis</span><span class="sxs-lookup"><span data-stu-id="1eb30-308">node() optimization hint</span></span>  
 <span data-ttu-id="1eb30-309">Gilt für: XQuery-Datentypen</span><span class="sxs-lookup"><span data-stu-id="1eb30-309">Applies to: XQuery data types</span></span>  
  
 <span data-ttu-id="1eb30-310">Sie können mithilfe der node()-Optimierung einen Knoten angeben, dessen Wert nicht erforderlich ist, um die typische Abfrage auszuwerten.</span><span class="sxs-lookup"><span data-stu-id="1eb30-310">You can use the node() optimization to specify a node whose value is not required to evaluate the typical query.</span></span> <span data-ttu-id="1eb30-311">Dieser Hinweis reduziert Speicheranforderungen, wenn die typische Abfrage nur das Vorhandensein des Knotens auswerten muss.</span><span class="sxs-lookup"><span data-stu-id="1eb30-311">This hint reduces storage requirements when the typical query only has to evaluate the existence of the node.</span></span> <span data-ttu-id="1eb30-312">(Standardmäßig speichert ein selektiver XML-Index den Wert für alle höher gestuften Knoten, außer komplexen Knotentypen.)</span><span class="sxs-lookup"><span data-stu-id="1eb30-312">(By default, a selective XML index stores the value for all promoted nodes, except complex node types.)</span></span>  
  
 <span data-ttu-id="1eb30-313">Betrachten Sie das folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1eb30-313">Consider the following example:</span></span>  
  
```sql  
SELECT T.record FROM myXMLTable T  
WHERE T.xmldata.exist('/a/b[./c=5]') = 1  
```  
  
 <span data-ttu-id="1eb30-314">Um einen selektiven XML-Index zum Auswerten dieser Abfrage zu verwenden, stufen Sie die Knoten `b` und `c`höher.</span><span class="sxs-lookup"><span data-stu-id="1eb30-314">To use a selective XML index to evaluate this query, promote nodes `b` and `c`.</span></span> <span data-ttu-id="1eb30-315">Da jedoch der Wert des Knotens `b` nicht erforderlich ist, können Sie den node()-Hinweis mit der folgenden Syntax verwenden:</span><span class="sxs-lookup"><span data-stu-id="1eb30-315">However, since the value of node `b` is not required, you can use the node() hint with the following syntax:</span></span>  
  
 `/a/b/ as node()`  
  
 <span data-ttu-id="1eb30-316">Wenn eine Abfrage den Wert eines Knotens erfordert, der mit dem node()-Hinweis indiziert wurde, dann kann der selektive XML-Index nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1eb30-316">If a query requires the value of a node that has been indexed with the node() hint, then the selective XML index cannot be used.</span></span>  
  
### <a name="singleton-optimization-hint"></a><span data-ttu-id="1eb30-317">SINGLETON-Optimierungshinweis</span><span class="sxs-lookup"><span data-stu-id="1eb30-317">SINGLETON optimization hint</span></span>  
 <span data-ttu-id="1eb30-318">Gilt für: XQuery- oder [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Datentypen</span><span class="sxs-lookup"><span data-stu-id="1eb30-318">Applies to: XQuery or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types</span></span>  
  
 <span data-ttu-id="1eb30-319">Der SINGLETON-Optimierungshinweis gibt die Kardinalität eines Knotens an.</span><span class="sxs-lookup"><span data-stu-id="1eb30-319">The SINGLETON optimization hint specifies the cardinality of a node.</span></span> <span data-ttu-id="1eb30-320">Dieser Hinweis verbessert die Abfrageleistung, da im Voraus bekannt ist, dass ein Knoten höchstens einmal in seinem übergeordneten Element oder Vorgänger angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="1eb30-320">This hint improves query performance since it is known in advance that a node appears at most one time within its parent or ancestor.</span></span>  
  
 <span data-ttu-id="1eb30-321">Beachten Sie das [Beispiel-XML-Dokument](#sample) in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="1eb30-321">Consider the [sample XML document](#sample) in this topic.</span></span>  
  
 <span data-ttu-id="1eb30-322">Um einen selektiven XML-Index zum Abfragen dieses Dokuments zu verwenden, können Sie den SINGLETON-Hinweis für den Knoten `d` angeben, da er höchstens einmal in seinem übergeordneten Element vorkommt.</span><span class="sxs-lookup"><span data-stu-id="1eb30-322">To use a selective XML index to query this document, you can specify the SINGLETON hint for node `d` since it appears at most one time within its parent.</span></span>  
  
 <span data-ttu-id="1eb30-323">Wenn der SINGLETON-Hinweis angegeben wurde, ein Knoten jedoch mehr als einmal in seinem übergeordneten Element oder Vorgänger vorkommt, dann wird ein Fehler ausgelöst, wenn Sie den Index (für vorhandene Daten) erstellen, oder wenn Sie eine Abfrage (für neue Daten) ausführen.</span><span class="sxs-lookup"><span data-stu-id="1eb30-323">If the SINGLETON hint has been specified, but a node appears more than one time within its parent or ancestor, then an error is raised when you create the index (for existing data) or when you run a query (for new data).</span></span>  
  
### <a name="data-type-optimization-hint"></a><span data-ttu-id="1eb30-324">DATA TYPE-Optimierungshinweis</span><span class="sxs-lookup"><span data-stu-id="1eb30-324">DATA TYPE optimization hint</span></span>  
 <span data-ttu-id="1eb30-325">Gilt für: XQuery-Datentypen</span><span class="sxs-lookup"><span data-stu-id="1eb30-325">Applies to: XQuery data types</span></span>  
  
 <span data-ttu-id="1eb30-326">Mit dem DATA TYPE-Optimierungshinweis können Sie eine XQuery oder einen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datentyp für den indizierten Knoten angeben.</span><span class="sxs-lookup"><span data-stu-id="1eb30-326">The DATA TYPE optimization hint lets you specify an XQuery or a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type for the indexed node.</span></span> <span data-ttu-id="1eb30-327">Der Datentyp wird in der Datentabelle des selektiven XML-Indexes für die Spalte verwendet, die dem indizierten Knoten entspricht.</span><span class="sxs-lookup"><span data-stu-id="1eb30-327">The data type is used for the column in the data table of the selective XML index that corresponds to the indexed node.</span></span>  
  
 <span data-ttu-id="1eb30-328">Wenn es bei der Umwandlung eines vorhandenen Werts in den angegebenen Datentyp zu einem Fehler kommt, verursacht der Einfügevorgang (in den Index) keinen Fehler. Es wird jedoch ein NULL-Wert in die Datentabelle des Index eingefügt.</span><span class="sxs-lookup"><span data-stu-id="1eb30-328">When casting an existing value to the specified data type fails, the insert operation (into the index) does not fail; however, a null value is inserted into the data table of the index.</span></span>  
  
### <a name="maxlength-optimization-hint"></a><span data-ttu-id="1eb30-329">MAXLENGTH-Optimierungshinweis</span><span class="sxs-lookup"><span data-stu-id="1eb30-329">MAXLENGTH optimization hint</span></span>  
 <span data-ttu-id="1eb30-330">Gilt für: XQuery-Datentypen</span><span class="sxs-lookup"><span data-stu-id="1eb30-330">Applies to: XQuery data types</span></span>  
  
 <span data-ttu-id="1eb30-331">Mit dem MAXLENGTH-Optimierungshinweis können Sie die Länge der xs:string-Daten einschränken.</span><span class="sxs-lookup"><span data-stu-id="1eb30-331">The MAXLENGTH optimization hint lets you limit the length of xs:string data.</span></span> <span data-ttu-id="1eb30-332">MAXLENGTH ist nicht relevant für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datentypen, da Sie die Länge angeben, wenn Sie den VARCHAR- oder NVARCHAR-Datentyp angeben.</span><span class="sxs-lookup"><span data-stu-id="1eb30-332">MAXLENGTH is not relevant for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types since you specify the length when you specify the VARCHAR or NVARCHAR date types.</span></span>  
  
 <span data-ttu-id="1eb30-333">Wenn eine vorhandene Zeichenfolge länger als der angegebene Wert für MAXLENGTH ist, kommt es beim Einfügen dieses Werts zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="1eb30-333">When an existing string is longer than the specified MAXLENGTH, then inserting that value into the index fails.</span></span>  
  

  
##  <a name="sample-xml-document-for-examples"></a><a name="sample"></a> <span data-ttu-id="1eb30-334">Beispiel-XML-Dokument für Beispiele</span><span class="sxs-lookup"><span data-stu-id="1eb30-334">Sample XML Document for Examples</span></span>  
 <span data-ttu-id="1eb30-335">Auf das folgende Beispiel-XML-Dokument wird in den Beispielen in diesem Thema verwiesen:</span><span class="sxs-lookup"><span data-stu-id="1eb30-335">The following sample XML document is referenced in the examples in this topic:</span></span>  
  
```xml  
<a>  
    <b>  
         <c atc="aa">10</c>  
         <c atc="bb">15</c>  
         <d atd1="dd" atd2="ddd">md </d>  
    </b>  
     <b>  
        <c></c>  
        <c atc="">117</c>  
     </b>  
</a>  
```  
  

  
## <a name="see-also"></a><span data-ttu-id="1eb30-336">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1eb30-336">See Also</span></span>  
 <span data-ttu-id="1eb30-337">[Selektive XML-Indizes &#40;SXI&#41;](../xml/selective-xml-indexes-sxi.md) </span><span class="sxs-lookup"><span data-stu-id="1eb30-337">[Selective XML Indexes &#40;SXI&#41;](../xml/selective-xml-indexes-sxi.md) </span></span>  
 [<span data-ttu-id="1eb30-338">Erstellen, Ändern und Löschen selektiver XML-Indizes</span><span class="sxs-lookup"><span data-stu-id="1eb30-338">Create, Alter, and Drop Selective XML Indexes</span></span>](../xml/create-alter-and-drop-selective-xml-indexes.md)  
  
  
