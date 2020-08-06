---
title: Angeben von Metaeigenschaften in OPENXML | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- overflow in XML document [SQL Server]
- metaproperties [XML in SQL Server]
- unconsumed data
- extracting information of XML nodes [SQL Server]
- OPENXML statement, metaproperties
ms.assetid: 29bfd1c6-3f9a-43c4-924a-53d438e442f4
author: rothja
ms.author: jroth
ms.openlocfilehash: c52d1162aa495deff8a0fde314fdcde0735d9c2f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719750"
---
# <a name="specify-metaproperties-in-openxml"></a><span data-ttu-id="d97e9-102">Angeben von Metaeigenschaften in OPENXML</span><span class="sxs-lookup"><span data-stu-id="d97e9-102">Specify Metaproperties in OPENXML</span></span>
  <span data-ttu-id="d97e9-103">Metaeigenschaftsattribute in einem XML-Dokument sind Attribute, die die Eigenschaften eines XML-Objekts (z. B. Element, Attribut oder ein beliebiger anderer DOM-Knoten) beschreiben.</span><span class="sxs-lookup"><span data-stu-id="d97e9-103">Metaproperty attributes in an XML document are attributes that describe the properties of an XML item, such as element, attribute, or any other DOM node.</span></span> <span data-ttu-id="d97e9-104">Diese Attribute sind nicht physisch im Text des XML-Dokuments enthalten.</span><span class="sxs-lookup"><span data-stu-id="d97e9-104">These attributes do not physically exist in the XML document text.</span></span> <span data-ttu-id="d97e9-105">Vielmehr stellt OPENXML diese Metaeigenschaften für alle XML-Objekte bereit.</span><span class="sxs-lookup"><span data-stu-id="d97e9-105">However, OPENXML provides these metaproperties for all the XML items.</span></span> <span data-ttu-id="d97e9-106">Die Metaeigenschaften ermöglichen es Ihnen, Informationen (wie etwa die relative Position oder Namespaceinformationen) über XML-Knoten zu extrahieren.</span><span class="sxs-lookup"><span data-stu-id="d97e9-106">These metaproperties allow you to extract information, such as local positioning and namespace information, of XML nodes.</span></span> <span data-ttu-id="d97e9-107">Diese Informationen bieten Ihnen mehr Details, als in der Textdarstellung zu sehen sind.</span><span class="sxs-lookup"><span data-stu-id="d97e9-107">This information provides you with more details than are apparent in the textual representation.</span></span>  
  
 <span data-ttu-id="d97e9-108">Sie können diese Metaeigenschaften Rowsetspalten in einer OPENXML-Anweisung mithilfe des *ColPattern* -Parameters zuordnen.</span><span class="sxs-lookup"><span data-stu-id="d97e9-108">You can map these metaproperties to the rowset columns in an OPENXML statement by using the *ColPattern* parameter.</span></span> <span data-ttu-id="d97e9-109">Die Spalten enthalten die Werte der Metaeigenschaften, denen sie zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="d97e9-109">The columns will contain the values of the metaproperties to which they are mapped.</span></span> <span data-ttu-id="d97e9-110">Weitere Informationen zur Syntax von OPENXML finden Sie unter [OPENXML &#40;Transact-SQL&#41;](/sql/t-sql/functions/openxml-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d97e9-110">For more information about the syntax of OPENXML, see [OPENXML &#40;Transact-SQL&#41;](/sql/t-sql/functions/openxml-transact-sql).</span></span>  
  
 <span data-ttu-id="d97e9-111">Für den Zugriff auf die Metaeigenschaftsattribute wird ein für SQL Server spezifischer Namespace bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="d97e9-111">To access the metaproperty attributes, a namespace that is specific to SQL Server is provided.</span></span> <span data-ttu-id="d97e9-112">Dieser Namespace **urn:schemas-microsoft-com:xml-metaprop** ermöglicht dem Benutzer den Zugriff auf die Metaeigenschaftsattribute.</span><span class="sxs-lookup"><span data-stu-id="d97e9-112">This namespace, **urn:schemas-microsoft-com:xml-metaprop** allows the user to access the metaproperty attributes.</span></span> <span data-ttu-id="d97e9-113">Wird das Ergebnis einer OPENXML-Abfrage in einem Rahmentabellenformat zurückgegeben, enthält die Rahmentabelle eine Spalte für jedes Metaeigenschaftsattribut (außer für die **xmltext** -Metaeigenschaft).</span><span class="sxs-lookup"><span data-stu-id="d97e9-113">If the result of an OPENXML query is returned in an edge table format, the edge table contains one column for each metaproperty attribute, except the **xmltext** metaproperty.</span></span>  
  
 <span data-ttu-id="d97e9-114">Einige der Metaeigenschaftsattribute werden zu Verarbeitungszwecken eingesetzt.</span><span class="sxs-lookup"><span data-stu-id="d97e9-114">Some of the metaproperty attributes are used for processing purposes.</span></span> <span data-ttu-id="d97e9-115">So wird z. B. das **xmltext** -Metaeigenschaftsattribut zur Bearbeitung von Überlaufdaten verwendet.</span><span class="sxs-lookup"><span data-stu-id="d97e9-115">For example, the **xmltext** metaproperty attribute is used for overflow handling.</span></span> <span data-ttu-id="d97e9-116">Die Bearbeitung von Überlaufdaten bezieht sich auf nicht verbrauchte, unverarbeitete Daten im Dokument.</span><span class="sxs-lookup"><span data-stu-id="d97e9-116">Overflow handling refers to the unconsumed, unprocessed data in the document.</span></span> <span data-ttu-id="d97e9-117">Eine der Spalten im von OPENXML generierten Rowset kann als Überlaufspalte identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="d97e9-117">One of the columns in the rowset that is generated by OPENXML can be identified as the overflow column.</span></span> <span data-ttu-id="d97e9-118">Dazu ordnen Sie diese Spalte mithilfe des **ColPattern** -Parameters der *xmltext* -Metaeigenschaft zu.</span><span class="sxs-lookup"><span data-stu-id="d97e9-118">You do this by mapping it to the **xmltext** metaproperty by using the *ColPattern* parameter.</span></span> <span data-ttu-id="d97e9-119">Die Spalte nimmt dann die Überlaufdaten auf.</span><span class="sxs-lookup"><span data-stu-id="d97e9-119">The column then receives the overflow data.</span></span> <span data-ttu-id="d97e9-120">Der *flags* -Parameter bestimmt, ob die Spalte ausschließlich nicht verbrauchte Daten oder alle Daten enthalten soll.</span><span class="sxs-lookup"><span data-stu-id="d97e9-120">The *flags* parameter determines whether the column contains everything or only the unconsumed data.</span></span>  
  
 <span data-ttu-id="d97e9-121">In der folgenden Tabelle werden die Metaeigenschaftsattribute für jedes analysierte XML-Element aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="d97e9-121">The following table lists the metaproperty attributes that each parsed XML element possesses.</span></span> <span data-ttu-id="d97e9-122">Mithilfe des Namespaces **urn:schemas-microsoft-com:xml-sql**kann auf diese Metaeigenschaftsattribute zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="d97e9-122">These metaproperty attributes can be accessed by using the namespace **urn:schemas-microsoft-com:xml-metaprop**.</span></span> <span data-ttu-id="d97e9-123">Jeder Wert, der direkt vom Benutzer im XML-Dokument mithilfe dieser Metaeigenschaften festgelegt wird, bleibt unberücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="d97e9-123">Any value that the user sets directly in the XML document by using these metaproperties is ignored.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d97e9-124">Sie können in XPath-Navigationen nicht auf diese Metaeigenschaften verweisen.</span><span class="sxs-lookup"><span data-stu-id="d97e9-124">You cannot reference these metaproperties in any XPath navigation.</span></span>  
  
|<span data-ttu-id="d97e9-125">Metaeigenschaftsattribut</span><span class="sxs-lookup"><span data-stu-id="d97e9-125">Metaproperty attribute</span></span>|<span data-ttu-id="d97e9-126">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d97e9-126">Description</span></span>|  
|----------------------------|-----------------|  
|<span data-ttu-id="d97e9-127">**\@mp:id**</span><span class="sxs-lookup"><span data-stu-id="d97e9-127">**\@mp:id**</span></span>|<span data-ttu-id="d97e9-128">Stellt einen systemgenerierten, dokumentweiten Bezeichner des DOM-Knotens bereit.</span><span class="sxs-lookup"><span data-stu-id="d97e9-128">Provides a system-generated, document-wide identifier of the DOM node.</span></span> <span data-ttu-id="d97e9-129">Dieser Bezeichner verweist auf denselben XML-Knoten, solange das Dokument nicht erneut analysiert wird.</span><span class="sxs-lookup"><span data-stu-id="d97e9-129">As long as the document is not reparsed, this ID refers to the same XML node.</span></span><br /><br /> <span data-ttu-id="d97e9-130">Eine XML-ID von **0** zeigt an, dass es sich bei dem Element um ein Stammelement handelt.</span><span class="sxs-lookup"><span data-stu-id="d97e9-130">An XML ID of **0** indicates that the element is a root element.</span></span> <span data-ttu-id="d97e9-131">Die übergeordnete XML-ID ist NULL.</span><span class="sxs-lookup"><span data-stu-id="d97e9-131">Its parent XML ID is NULL.</span></span>|  
|<span data-ttu-id="d97e9-132">**\@mp:localname**</span><span class="sxs-lookup"><span data-stu-id="d97e9-132">**\@mp:localname**</span></span>|<span data-ttu-id="d97e9-133">Speichert den lokalen Teil des Knotennamens.</span><span class="sxs-lookup"><span data-stu-id="d97e9-133">Stores the local part of the name of the node.</span></span> <span data-ttu-id="d97e9-134">Die Metaeigenschaft wird mit einem Präfix und einem Namespace-URI (Uniform Resource Identifier) zur Benennung von Element- oder Attributknoten verwendet.</span><span class="sxs-lookup"><span data-stu-id="d97e9-134">It is used with a prefix and a namespace URI to name element or attribute nodes.</span></span>|  
|<span data-ttu-id="d97e9-135">**\@mp:namespaceuri**</span><span class="sxs-lookup"><span data-stu-id="d97e9-135">**\@mp:namespaceuri**</span></span>|<span data-ttu-id="d97e9-136">Gibt den Namespace-URI des aktuellen Elements an.</span><span class="sxs-lookup"><span data-stu-id="d97e9-136">Provides the namespace URI of the current element.</span></span> <span data-ttu-id="d97e9-137">Ist der Wert dieses Attributs NULL, ist kein Namespace vorhanden.</span><span class="sxs-lookup"><span data-stu-id="d97e9-137">If the value of this attribute is NULL, no namespace is present</span></span>|  
|<span data-ttu-id="d97e9-138">**\@mp:prefix**</span><span class="sxs-lookup"><span data-stu-id="d97e9-138">**\@mp:prefix**</span></span>|<span data-ttu-id="d97e9-139">Speichert das Namespacepräfix des aktuellen Elementnamens.</span><span class="sxs-lookup"><span data-stu-id="d97e9-139">Stores the namespace prefix of the current element name.</span></span><br /><br /> <span data-ttu-id="d97e9-140">Wenn kein Präfix vorhanden ist (NULL) und ein URI angegeben ist, zeigt dieses Attribut an, dass der angegebene Namespace der Standardnamespace ist.</span><span class="sxs-lookup"><span data-stu-id="d97e9-140">If no prefix is present (NULL) and a URI is given, it indicates that the specified namespace is the default namespace.</span></span> <span data-ttu-id="d97e9-141">Ist kein URI angegeben, wird kein Namespace angefügt.</span><span class="sxs-lookup"><span data-stu-id="d97e9-141">If no URI is given, no namespace is attached.</span></span>|  
|<span data-ttu-id="d97e9-142">**\@mp:prev**</span><span class="sxs-lookup"><span data-stu-id="d97e9-142">**\@mp:prev**</span></span>|<span data-ttu-id="d97e9-143">Speichert das vorhergehende gleichgeordnete Objekt eines Knotens.</span><span class="sxs-lookup"><span data-stu-id="d97e9-143">Stores the previous sibling relative to a node.</span></span> <span data-ttu-id="d97e9-144">Dadurch werden Informationen über die Reihenfolge der Elemente im Dokument bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="d97e9-144">This provides information about the ordering of elements in the document.</span></span><br /><br /> <span data-ttu-id="d97e9-145">**\@mp:prev** enthält die XML-ID des vorhergehenden gleichgeordneten Elements, das über dasselbe übergeordnete Element verfügt.</span><span class="sxs-lookup"><span data-stu-id="d97e9-145">**\@mp:prev** contains the XML ID of the previous sibling that has the same parent element.</span></span> <span data-ttu-id="d97e9-146">Wird ein Element am Anfang der Liste der gleichgeordneten Elemente aufgeführt, ist **\@mp:prev** gleich NULL.</span><span class="sxs-lookup"><span data-stu-id="d97e9-146">If an element is at the front of the sibling list, **\@mp:prev** is NULL.</span></span>|  
|<span data-ttu-id="d97e9-147">**\@mp:xmltext**</span><span class="sxs-lookup"><span data-stu-id="d97e9-147">**\@mp:xmltext**</span></span>|<span data-ttu-id="d97e9-148">Wird zu Verarbeitungszwecken genutzt.</span><span class="sxs-lookup"><span data-stu-id="d97e9-148">Used for processing purposes.</span></span> <span data-ttu-id="d97e9-149">Legt die Textserialisierung des Elements und der zugehörigen Attribute und auch die Teilelemente fest, wie dies bei der Überlaufbearbeitung von OPENXML der Fall ist.</span><span class="sxs-lookup"><span data-stu-id="d97e9-149">It is the textual serialization of the element and its attributes, and also the subelements, as used in the overflow handling of OPENXML.</span></span>|  
  
 <span data-ttu-id="d97e9-150">In dieser Tabelle werden die zusätzlichen Eigenschaften übergeordneter Metaeigenschaftsattribute dargestellt, die Ihnen das Abrufen von Hierarchieinformationen ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="d97e9-150">This table shows the additional parent properties that are provided and which allow you to retrieve information about the hierarchy.</span></span>  
  
|<span data-ttu-id="d97e9-151">Übergeordnetes Metaeigenschaftsattribut</span><span class="sxs-lookup"><span data-stu-id="d97e9-151">Parent metaproperty attribute</span></span>|<span data-ttu-id="d97e9-152">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d97e9-152">Description</span></span>|  
|-----------------------------------|-----------------|  
|<span data-ttu-id="d97e9-153">**\@mp:parentid**</span><span class="sxs-lookup"><span data-stu-id="d97e9-153">**\@mp:parentid**</span></span>|<span data-ttu-id="d97e9-154">Entspricht **../\@mp:id**</span><span class="sxs-lookup"><span data-stu-id="d97e9-154">Corresponds to **../\@mp:id**</span></span>|  
|<span data-ttu-id="d97e9-155">**\@mp:parentlocalname**</span><span class="sxs-lookup"><span data-stu-id="d97e9-155">**\@mp:parentlocalname**</span></span>|<span data-ttu-id="d97e9-156">Entspricht **../\@mp:localname**</span><span class="sxs-lookup"><span data-stu-id="d97e9-156">Corresponds to **../\@mp:localname**</span></span>|  
|<span data-ttu-id="d97e9-157">**\@mp:parentnamespacerui**</span><span class="sxs-lookup"><span data-stu-id="d97e9-157">**\@mp:parentnamespacerui**</span></span>|<span data-ttu-id="d97e9-158">Entspricht **../\@mp:namespaceuri**</span><span class="sxs-lookup"><span data-stu-id="d97e9-158">Corresponds to **../\@mp:namespaceuri**</span></span>|  
|<span data-ttu-id="d97e9-159">**\@mp:parentprefix**</span><span class="sxs-lookup"><span data-stu-id="d97e9-159">**\@mp:parentprefix**</span></span>|<span data-ttu-id="d97e9-160">Entspricht **../\@mp:prefix**</span><span class="sxs-lookup"><span data-stu-id="d97e9-160">Corresponds to **../\@mp:prefix**</span></span>|  
  
## <a name="examples"></a><span data-ttu-id="d97e9-161">Beispiele</span><span class="sxs-lookup"><span data-stu-id="d97e9-161">Examples</span></span>  
 <span data-ttu-id="d97e9-162">In den folgenden Beispielen wird die Verwendung von OPENXML zum Erstellen unterschiedlicher Rowsetsichten veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="d97e9-162">The following examples illustrate how OPENXML is used to create different rowset views.</span></span>  
  
### <a name="a-mapping-the-openxml-rowset-columns-to-the-metaproperties"></a><span data-ttu-id="d97e9-163">A.</span><span class="sxs-lookup"><span data-stu-id="d97e9-163">A.</span></span> <span data-ttu-id="d97e9-164">Zuordnen der OPENXML-Rowsetspalten zu den Metaeigenschaften</span><span class="sxs-lookup"><span data-stu-id="d97e9-164">Mapping the OPENXML rowset columns to the metaproperties</span></span>  
 <span data-ttu-id="d97e9-165">In diesem Beispiel wird OPENXML zum Erstellen einer Rowsetsicht des XML-Beispieldokuments verwendet.</span><span class="sxs-lookup"><span data-stu-id="d97e9-165">This example uses OPENXML to create a rowset view of the sample XML document.</span></span> <span data-ttu-id="d97e9-166">Es veranschaulicht das Zuordnen verschiedener Metaeigenschaftsattribute zu Rowsetspalten in der OPENXML-Anweisung mithilfe des *ColPattern* -Parameters.</span><span class="sxs-lookup"><span data-stu-id="d97e9-166">Specifically, it shows how the various metaproperty attributes can be mapped to rowset columns in an OPENXML statement by using the *ColPattern* parameter.</span></span>  
  
 <span data-ttu-id="d97e9-167">Die OPENXML-Anweisung verdeutlicht Folgendes:</span><span class="sxs-lookup"><span data-stu-id="d97e9-167">The OPENXML statement illustrates the following:</span></span>  
  
-   <span data-ttu-id="d97e9-168">Die **id**-Spalte wird dem **\@mp:id**-Metaeigenschaftsattribut zugeordnet und zeigt an, dass die Spalte die systemgenerierte eindeutige XML-ID des Elements enthält.</span><span class="sxs-lookup"><span data-stu-id="d97e9-168">The **id** column is mapped to the **\@mp:id** metaproperty attribute and indicates that the column contains the system-generated unique XML ID of the element.</span></span>  
  
-   <span data-ttu-id="d97e9-169">Die **parent**-Spalte wird **\@mp:parentid** zugeordnet und zeigt an, dass die Spalte die XML-ID des übergeordneten Elements enthält.</span><span class="sxs-lookup"><span data-stu-id="d97e9-169">The **parent** column is mapped to **\@mp:parentid** and indicates that the column contains the XML ID of the parent of the element.</span></span>  
  
-   <span data-ttu-id="d97e9-170">Die **parentLocalName**-Spalte wird **\@mp:parentlocalname** zugeordnet und zeigt an, dass die Spalte den lokalen Namen des übergeordneten Elements enthält.</span><span class="sxs-lookup"><span data-stu-id="d97e9-170">The **parentLocalName** column is mapped to **\@mp:parentlocalname** and indicates that the column contains the local name of the parent.</span></span>  
  
 <span data-ttu-id="d97e9-171">Schließlich gibt die SELECT-Anweisung das von OPENXML bereitgestellte Rowset zurück.</span><span class="sxs-lookup"><span data-stu-id="d97e9-171">The SELECT statement then returns the rowset that is provided by OPENXML:</span></span>  
  
```  
DECLARE @idoc int  
DECLARE @doc nvarchar(1000)  
-- Sample XML document  
SET @doc = N'<root>  
  <Customer cid= "C1" name="Janine" city="Issaquah">  
      <Order oid="O1" date="1/20/1996" amount="3.5" />  
      <Order oid="O2" date="4/30/1997" amount="13.4">Customer was very satisfied</Order>  
   </Customer>  
   <Customer cid="C2" name="Ursula" city="Oelde" >  
      <Order oid="O3" date="7/14/1999" amount="100" note="Wrap it blue white red">  
          <Urgency>Important</Urgency>  
      </Order>  
      <Order oid="O4" date="1/20/1996" amount="10000"/>  
   </Customer>  
</root>'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @idoc OUTPUT, @doc  
  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@idoc, '/root/Customer/Order', 9)  
      WITH (id int '@mp:id',   
            oid char(5),   
            date datetime,   
            amount real,   
            parentIDNo int '@mp:parentid',   
            parentLocalName varchar(40) '@mp:parentlocalname')  
EXEC sp_xml_removedocument @idoc  
```  
  
 <span data-ttu-id="d97e9-172">Dies ist das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="d97e9-172">This is the result:</span></span>  
  
```  
id   oid         date                amount    parentIDNo  parentLocalName    
--- ------- ---------------------- ---------- ------------ ---------------  
6    O1    1996-01-20 00:00:00.000     3.5         2        Customer  
10   O2    1997-04-30 00:00:00.000     13.4        2        Customer  
19   O3    1999-07-14 00:00:00.000     100.0       15       Customer  
25   O4    1996-01-20 00:00:00.000     10000.0     15       Customer  
```  
  
### <a name="b-retrieving-the-whole-xml-document"></a><span data-ttu-id="d97e9-173">B.</span><span class="sxs-lookup"><span data-stu-id="d97e9-173">B.</span></span> <span data-ttu-id="d97e9-174">Abrufen des gesamten XML-Dokuments</span><span class="sxs-lookup"><span data-stu-id="d97e9-174">Retrieving the whole XML document</span></span>  
 <span data-ttu-id="d97e9-175">In diesem Beispiel wird mithilfe von OPENXML eine einspaltige Rowsetsicht des XML-Beispieldokuments erstellt.</span><span class="sxs-lookup"><span data-stu-id="d97e9-175">In this example, OPENXML is used to create a one-column rowset view of the sample XML document.</span></span> <span data-ttu-id="d97e9-176">Diese Spalte **Col1**wird der **xmltext** -Metaeigenschaft zugeordnet und wird zu einer Überlaufspalte.</span><span class="sxs-lookup"><span data-stu-id="d97e9-176">This column, **Col1**, is mapped to the **xmltext** metaproperty and becomes an overflow column.</span></span> <span data-ttu-id="d97e9-177">Deshalb nimmt die Spalte die nicht verbrauchten Daten auf.</span><span class="sxs-lookup"><span data-stu-id="d97e9-177">As a result, the column receives the unconsumed data.</span></span> <span data-ttu-id="d97e9-178">In diesem Fall handelt es sich dabei um das gesamte Dokument.</span><span class="sxs-lookup"><span data-stu-id="d97e9-178">In this case, it is the whole document.</span></span>  
  
 <span data-ttu-id="d97e9-179">Schließlich gibt die SELECT-Anweisung das vollständige Rowset zurück.</span><span class="sxs-lookup"><span data-stu-id="d97e9-179">The SELECT statement then returns the complete rowset.</span></span>  
  
```  
DECLARE @idoc int  
DECLARE @doc nvarchar(1000)  
SET @doc = N'<?xml version="1.0"?>  
<root>  
  <Customer cid= "C1" name="Janine" city="Issaquah">  
      <Order oid="O1" date="1/20/1996" amount="3.5" />  
      <Order oid="O2" date="4/30/1997" amount="13.4">Customer was very   
             satisfied</Order>  
   </Customer>  
   <Customer cid="C2" name="Ursula" city="Oelde" >  
      <Order oid="O3" date="7/14/1999" amount="100" note="Wrap it blue   
             white red">  
     <MyTag>Testing to see if all the subelements are returned</MyTag>  
          <Urgency>Important</Urgency>  
      </Order>  
      <Order oid="O4" date="1/20/1996" amount="10000"/>  
   </Customer>  
</root>'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @idoc OUTPUT, @doc  
  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@idoc, '/')  
   WITH (Col1 ntext '@mp:xmltext')  
```  
  
 <span data-ttu-id="d97e9-180">Um das gesamte Dokument ohne die XML-Deklaration abzurufen, kann die Abfrage wie folgt angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="d97e9-180">To retrieve the whole document without the XML declaration, the query can be specified as shown in the following:</span></span>  
  
```  
SELECT *  
FROM OPENXML (@idoc, '/root')  
   WITH (Col1 ntext '@mp:xmltext')  
EXEC sp_xml_removedocument @idoc  
```  
  
 <span data-ttu-id="d97e9-181">Die Abfrage gibt das Stammelement mit dem Namensstammverzeichnis sowie die Daten des Stammelements zurück.</span><span class="sxs-lookup"><span data-stu-id="d97e9-181">The query returns the root element that has the name root and the data that is contained by the root element</span></span>  
  
### <a name="c-specifying-the-xmltext-metaproperty-to-retrieve-the-unconsumed-data-in-a-column"></a><span data-ttu-id="d97e9-182">C.</span><span class="sxs-lookup"><span data-stu-id="d97e9-182">C.</span></span> <span data-ttu-id="d97e9-183">Angeben der xmltext-Metaeigenschaft zur Abfrage der nicht verbrauchten Daten in einer Spalte</span><span class="sxs-lookup"><span data-stu-id="d97e9-183">Specifying the xmltext metaproperty to retrieve the unconsumed data in a column</span></span>  
 <span data-ttu-id="d97e9-184">In diesem Beispiel wird OPENXML zum Erstellen einer Rowsetsicht des XML-Beispieldokuments verwendet.</span><span class="sxs-lookup"><span data-stu-id="d97e9-184">This example uses OPENXML to create a rowset view of the sample XML document.</span></span> <span data-ttu-id="d97e9-185">Das Beispiel veranschaulicht die Abfrage nicht verbrauchter XML-Daten durch Zuordnen des **xmltext** -Metaeigenschaftsattributs zu einer Rowsetspalte in OPENXML.</span><span class="sxs-lookup"><span data-stu-id="d97e9-185">The example shows how to retrieve unconsumed XML data by mapping the **xmltext** metaproperty attribute to a rowset column in OPENXML.</span></span>  
  
 <span data-ttu-id="d97e9-186">Die **comment**-Spalte wird durch Zuordnen zur **\@mp:xmltext**-Metaeigenschaft als Überlaufspalte identifiziert.</span><span class="sxs-lookup"><span data-stu-id="d97e9-186">The **comment** column is identified as the overflow column by mapping it to the **\@mp:xmltext** metaproperty.</span></span> <span data-ttu-id="d97e9-187">Der *flags* -Parameter wird auf **9** festgelegt (XML_ATTRIBUTE and XML_NOCOPY).</span><span class="sxs-lookup"><span data-stu-id="d97e9-187">The *flags* parameter is set to **9** (XML_ATTRIBUTE and XML_NOCOPY).</span></span> <span data-ttu-id="d97e9-188">Dies zeigt die **attributzentrierte** Zuordnung an und dass ausschließlich nicht verbrauchte Daten in die Überlaufspalte kopiert werden sollten.</span><span class="sxs-lookup"><span data-stu-id="d97e9-188">This indicates **attribute-centric** mapping and indicates that only the unconsumed data should be copied to the overflow column.</span></span>  
  
 <span data-ttu-id="d97e9-189">Schließlich gibt die SELECT-Anweisung das von OPENXML bereitgestellte Rowset zurück.</span><span class="sxs-lookup"><span data-stu-id="d97e9-189">The SELECT statement then returns the rowset provided by OPENXML.</span></span>  
  
 <span data-ttu-id="d97e9-190">In diesem Beispiel wird die **\@mp:parentlocalname**-Metaeigenschaft für eine Spalte (**ParentLocalName**) in dem von OPENXML generierten Rowset festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d97e9-190">In this example, the **\@mp:parentlocalname** metaproperty is set for a column, **ParentLocalName**, in the rowset generated by OPENXML.</span></span> <span data-ttu-id="d97e9-191">Folglich enthält diese Spalte den lokalen Namen des übergeordneten Elements.</span><span class="sxs-lookup"><span data-stu-id="d97e9-191">As a result, this column contains the local name of the parent element.</span></span>  
  
 <span data-ttu-id="d97e9-192">Es werden zwei zusätzliche Spalten im Rowset angegeben ( **parent** und **comment**).</span><span class="sxs-lookup"><span data-stu-id="d97e9-192">Two additional columns are specified in the rowset, **parent** and **comment**.</span></span> <span data-ttu-id="d97e9-193">Die **parent**-Spalte wird **\@mp:parentid** zugeordnet und zeigt an, dass die Spalte die XML-ID des übergeordneten Elements des Elements enthält.</span><span class="sxs-lookup"><span data-stu-id="d97e9-193">The **parent** column is mapped to **\@mp:parentid** and indicates that the column contains the XML ID of the parent element of the element.</span></span> <span data-ttu-id="d97e9-194">Die **comment\@-Spalte wird durch Zuordnen zur** mp:xmltext-Metaeigenschaft als Überlaufspalte identifiziert.</span><span class="sxs-lookup"><span data-stu-id="d97e9-194">The comment column is identified as the overflow column by mapping it to the **\@mp:xmltext** metaproperty.</span></span>  
  
```  
DECLARE @idoc int  
DECLARE @doc nvarchar(1000)  
-- sample XML document  
SET @doc = N'<root>  
  <Customer cid= "C1" name="Janine" city="Issaquah">  
      <Order oid="O1" date="1/20/1996" amount="3.5" />  
      <Order oid="O2" date="4/30/1997" amount="13.4">Customer was very satisfied</Order>  
   </Customer>  
   <Customer cid="C2" name="Ursula" city="Oelde" >  
      <Order oid="O3" date="7/14/1999" amount="100" note="Wrap it blue white red">  
          <Urgency>Important</Urgency>  
      </Order>  
      <Order oid="O4" date="1/20/1996" amount="10000"/>  
   </Customer>  
</root>  
'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @idoc OUTPUT, @doc  
  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@idoc, '/root/Customer/Order', 9)  
      WITH (oid char(5),   
            date datetime,  
            comment ntext '@mp:xmltext')  
EXEC sp_xml_removedocument @idoc  
```  
  
 <span data-ttu-id="d97e9-195">Dies ist das Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="d97e9-195">This is the result.</span></span> <span data-ttu-id="d97e9-196">Da die Spalten oid und date bereits verbraucht sind, werden sie nicht mehr in der Überlaufspalte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d97e9-196">Because the oid columns and date columns are already consumed, they do not appear in the overflow column.</span></span>  
  
```  
oid   date                        comment                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            
----- --------------------------- ----------------------------------------  
O1    1996-01-20 00:00:00.000     <Order amount="3.5"/>  
O2    1997-04-30 00:00:00.000     <Order amount="13.4">Customer was very   
                                   satisfied</Order>  
O3    1999-07-14 00:00:00.000     <Order amount="100" note="Wrap it blue   
                                   white red"><Urgency>   
                                   Important</Urgency></Order>  
O4    1996-01-20 00:00:00.000     <Order amount="10000"/>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d97e9-197">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d97e9-197">See Also</span></span>  
 <span data-ttu-id="d97e9-198">[OPENXML &#40;Transact-SQL&#41;](/sql/t-sql/functions/openxml-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d97e9-198">[OPENXML &#40;Transact-SQL&#41;](/sql/t-sql/functions/openxml-transact-sql) </span></span>  
 [<span data-ttu-id="d97e9-199">OPENXML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d97e9-199">OPENXML &#40;SQL Server&#41;</span></span>](../xml/openxml-sql-server.md)  
  
  
