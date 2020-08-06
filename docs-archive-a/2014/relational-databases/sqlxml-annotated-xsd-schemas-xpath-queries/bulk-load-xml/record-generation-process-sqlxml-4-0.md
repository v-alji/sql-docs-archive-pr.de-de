---
title: Daten Satz Generierungsprozess (SQLXML 4,0) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XML Bulk Load [SQLXML], record generation process
- node scopes [SQLXML]
- record subsets [SQLXML]
- scope [SQLXML]
- key ordering rules [SQLXML]
- record generation process for bulk loads [SQLXML]
- entering node scope [SQLXML]
- bulk load [SQLXML], record generation process
- leaving node scope [SQLXML]
- schema mapping [SQLXML]
ms.assetid: d8885bbe-6f15-4fb9-9684-ca7883cfe9ac
author: rothja
ms.author: jroth
ms.openlocfilehash: 5734776864aecbda7adaf0b9b16180b5ebd55ce3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695498"
---
# <a name="record-generation-process-sqlxml-40"></a><span data-ttu-id="fb23f-102">Datensatzgenerierungsprozess (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="fb23f-102">Record Generation Process (SQLXML 4.0)</span></span>
  <span data-ttu-id="fb23f-103">Beim XML-Massenladen werden die XML-Eingabedaten verarbeitet und Datensätze für die entsprechenden Tabellen in Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] vorbereitet.</span><span class="sxs-lookup"><span data-stu-id="fb23f-103">XML Bulk Load processes the XML input data and prepares records for the appropriate tables in Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="fb23f-104">Die interne Logik beim XML-Massenladen entscheidet darüber, wann ein neuer Datensatz generiert wird, welche untergeordneten Elemente oder Attributwerte in die Datensatzfelder kopiert werden und wann der Datensatz vollständig ist und zum Einfügen an [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] gesendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="fb23f-104">The logic in XML Bulk Load determines when to generate a new record, what child element or attribute values to copy into the fields of the record, and when the record is complete and ready to be sent to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] for insertion.</span></span>  
  
 <span data-ttu-id="fb23f-105">Beim XML-Massenladen werden nicht alle XML-Eingabedaten in den Speicher geladen und keine vollständigen Datensätze erstellt, bevor Daten an [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="fb23f-105">XML Bulk Load does not load the entire XML input data into memory, and does not produce complete record sets before sending data to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="fb23f-106">Dies liegt daran, dass XML-Eingabedaten sehr große Dokumente bilden können und das Laden des gesamten Dokuments in den Speicher kostspielig sein kann.</span><span class="sxs-lookup"><span data-stu-id="fb23f-106">This is because XML input data can be a large document and loading the entire document in memory can be expensive.</span></span> <span data-ttu-id="fb23f-107">Stattdessen wird beim XML-Massenladen wie folgt vorgegangen:</span><span class="sxs-lookup"><span data-stu-id="fb23f-107">Instead, XML Bulk Load does the following:</span></span>  
  
1.  <span data-ttu-id="fb23f-108">Analysieren des Zuordnungsschemas und Vorbereiten des notwendigen Ausführungsplans.</span><span class="sxs-lookup"><span data-stu-id="fb23f-108">Analyzes the mapping schema and prepares the necessary execution plan.</span></span>  
  
2.  <span data-ttu-id="fb23f-109">Anwenden des Ausführungsplans auf die Daten im Eingabedatenstrom.</span><span class="sxs-lookup"><span data-stu-id="fb23f-109">Applies the execution plan to the data in the input stream.</span></span>  
  
 <span data-ttu-id="fb23f-110">Aufgrund dieser sequenziellen Verarbeitung müssen die XML-Eingabedaten auf eine bestimmte Weise bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="fb23f-110">This sequential processing makes it important to provide the XML input data in a specific way.</span></span> <span data-ttu-id="fb23f-111">Es ist wichtig, zu verstehen, wie das Zuordnungsschema beim XML-Massenladen analysiert wird und wie der Datensatzgenerierungsprozess abläuft.</span><span class="sxs-lookup"><span data-stu-id="fb23f-111">You must understand how XML Bulk Load analyzes the mapping schema and how the record generation process occurs.</span></span> <span data-ttu-id="fb23f-112">Mit diesem Wissen können Sie ein Zuordnungsschema für XML-Massenladen bereitstellen, das die gewünschten Ergebnisse liefert.</span><span class="sxs-lookup"><span data-stu-id="fb23f-112">With this understanding, you can provide a mapping schema to XML Bulk Load that produces the results you want.</span></span>  
  
 <span data-ttu-id="fb23f-113">Beim XML-Massenladen werden gängige Anmerkungen im Zuordnungsschema verarbeitet, darunter Spalten- und Tabellenzuordnungen (die explizit über Anmerkungen oder implizit über die Standardzuordnung angegeben werden), sowie Joinbeziehungen.</span><span class="sxs-lookup"><span data-stu-id="fb23f-113">XML Bulk Load handles common mapping schema annotations, including column and table mappings (specified explicitly by using annotations or implicitly through the default mapping), and join relationships.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fb23f-114">Es wird davon ausgegangen, dass Sie mit XSD- oder XDR-Zuordnungsschemas mit Anmerkungen vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="fb23f-114">It is assumed that you are familiar with annotated XSD or XDR mapping schemas.</span></span> <span data-ttu-id="fb23f-115">Weitere Informationen zu Schemas finden Sie unter [Einführung in XSD-Schemas mit Anmerkungen &#40;SQLXML 4,0&#41;](../../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md) oder [mit Anmerkungen versehene XDR-Schemas &#40;in SQLXML 4,0&#41;](../../sqlxml/annotated-xsd-schemas/annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="fb23f-115">For more information about schemas, see [Introduction to Annotated XSD Schemas &#40;SQLXML 4.0&#41;](../../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md) or [Annotated XDR Schemas &#40;Deprecated in SQLXML 4.0&#41;](../../sqlxml/annotated-xsd-schemas/annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="fb23f-116">Grundlage für das Verständnis der Datensatzgenerierung sind folgende Konzepte:</span><span class="sxs-lookup"><span data-stu-id="fb23f-116">Understanding record generation requires understanding the following concepts:</span></span>  
  
-   <span data-ttu-id="fb23f-117">Bereich eines Knotens</span><span class="sxs-lookup"><span data-stu-id="fb23f-117">Scope of a node</span></span>  
  
-   <span data-ttu-id="fb23f-118">Datensatzgenerierungsregel</span><span class="sxs-lookup"><span data-stu-id="fb23f-118">Record Generation Rule</span></span>  
  
-   <span data-ttu-id="fb23f-119">Datensatzteilmenge und Schlüsselsortierregel</span><span class="sxs-lookup"><span data-stu-id="fb23f-119">Record subset and the Key Ordering Rule</span></span>  
  
-   <span data-ttu-id="fb23f-120">Ausnahmen von der Datensatzgenerierungsregel</span><span class="sxs-lookup"><span data-stu-id="fb23f-120">Exceptions to the Record Generation Rule</span></span>  
  
## <a name="scope-of-a-node"></a><span data-ttu-id="fb23f-121">Bereich eines Knotens</span><span class="sxs-lookup"><span data-stu-id="fb23f-121">Scope of a Node</span></span>  
 <span data-ttu-id="fb23f-122">Ein Knoten (ein Element oder Attribut) in einem XML-Dokument wird in den Gültigkeits *Bereich* eingegeben, wenn der XML-Massen Ladevorgang im XML-Eingabedaten Strom auftritt.</span><span class="sxs-lookup"><span data-stu-id="fb23f-122">A node (an element or an attribute) in an XML document enters *into scope* when XML Bulk Load encounters it in the XML input data stream.</span></span> <span data-ttu-id="fb23f-123">Bei Elementknoten bringt das Starttag des Elements das Element in den Bereich.</span><span class="sxs-lookup"><span data-stu-id="fb23f-123">For an element node, the start tag of the element brings the element in scope.</span></span> <span data-ttu-id="fb23f-124">Bei Attributknoten bringt der Attributname das Attribut in den Bereich.</span><span class="sxs-lookup"><span data-stu-id="fb23f-124">For an attribute node, the attribute name brings the attribute in scope.</span></span>  
  
 <span data-ttu-id="fb23f-125">Ein Knoten verlässt den Bereich, wenn keine Daten mehr dafür vorliegen, das heißt entweder am Endtag (im Fall eines Elementknotens) oder am Ende eines Attributwerts (im Fall eines Attributknotens).</span><span class="sxs-lookup"><span data-stu-id="fb23f-125">A node leaves scope when there is no more data for it: either at the end tag (in the case of an element node) or at the end of an attribute value (in the case of an attribute node).</span></span>  
  
## <a name="record-generation-rule"></a><span data-ttu-id="fb23f-126">Datensatzgenerierungsregel</span><span class="sxs-lookup"><span data-stu-id="fb23f-126">Record Generation Rule</span></span>  
 <span data-ttu-id="fb23f-127">Gelangt ein (Element- oder Attribut-) Knoten in den Bereich, kann daraus ein Datensatz generiert werden.</span><span class="sxs-lookup"><span data-stu-id="fb23f-127">When a node (element or attribute) enters into scope, there is a potential for generating a record from that node.</span></span> <span data-ttu-id="fb23f-128">Der Datensatz besteht weiter, solange der zugeordnete Knoten im Bereich ist.</span><span class="sxs-lookup"><span data-stu-id="fb23f-128">The record lives as long as the associated node is in scope.</span></span> <span data-ttu-id="fb23f-129">Verlässt der Knoten den Bereich, wird der generierte Datensatz als vollständig (mit Daten) betrachtet und zum Einfügen an [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] gesendet.</span><span class="sxs-lookup"><span data-stu-id="fb23f-129">When the node goes out of scope, XML Bulk Load considers the generated record complete (with data) and sends it to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] for insertion.</span></span>  
  
 <span data-ttu-id="fb23f-130">Betrachten Sie beispielsweise das folgende XSD-Schemafragment:</span><span class="sxs-lookup"><span data-stu-id="fb23f-130">For example, consider the following XSD schema fragment:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Customer" sql:relation="Customers" >  
   <xsd:complexType>  
     <xsd:attribute name="CustomerID" type="xsd:string" />  
     <xsd:attribute name="CompanyName" type="xsd:string" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="fb23f-131">Das Schema gibt ein **\<Customer>** -Element mit den Attributen **CustomerID** und **CompanyName** an.</span><span class="sxs-lookup"><span data-stu-id="fb23f-131">The schema specifies a **\<Customer>** element with **CustomerID** and **CompanyName** attributes.</span></span> <span data-ttu-id="fb23f-132">Die-Anmerkung `sql:relation` ordnet das- **\<Customer>** Element der Customers-Tabelle zu.</span><span class="sxs-lookup"><span data-stu-id="fb23f-132">The `sql:relation` annotation maps the **\<Customer>** element to the Customers table.</span></span>  
  
 <span data-ttu-id="fb23f-133">Betrachten Sie dieses Fragment eines XML-Dokuments:</span><span class="sxs-lookup"><span data-stu-id="fb23f-133">Consider this fragment of an XML document:</span></span>  
  
```  
<Customer CustomerID="1" CompanyName="xyz" />  
<Customer CustomerID="2" CompanyName="abc" />  
...  
```  
  
 <span data-ttu-id="fb23f-134">Wenn für das XML-Massenladen das in den vorstehenden Absätzen erläuterte Schema und XML-Daten als Eingabe bereitgestellt werden, werden die (Element- und Attribut-) Knoten in den Quelldaten wie folgt verarbeitet:</span><span class="sxs-lookup"><span data-stu-id="fb23f-134">When XML Bulk Load is provided with the schema described in the preceding paragraphs and XML data as input, it processes the nodes (elements and attributes) in the source data as follows:</span></span>  
  
-   <span data-ttu-id="fb23f-135">Das Starttag des ersten **\<Customer>** Elements bringt dieses Element in den Gültigkeitsbereich.</span><span class="sxs-lookup"><span data-stu-id="fb23f-135">The start tag of the first **\<Customer>** element brings that element in scope.</span></span> <span data-ttu-id="fb23f-136">Dieser Knoten ist der Customers-Tabelle zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="fb23f-136">This node maps to the Customers table.</span></span> <span data-ttu-id="fb23f-137">Beim XML-Massenladen wird daher ein Datensatz für die Customers-Tabelle generiert.</span><span class="sxs-lookup"><span data-stu-id="fb23f-137">Therefore, XML Bulk Load generates a record for the Customers table.</span></span>  
  
-   <span data-ttu-id="fb23f-138">Im Schema sind alle Attribute des- **\<Customer>** Elements Spalten der Customers-Tabelle zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="fb23f-138">In the schema, all attributes of the **\<Customer>** element map to columns of the Customers table.</span></span> <span data-ttu-id="fb23f-139">Wenn diese Attribute in den Bereich gelangen, werden ihre Werte in den Kundendatensatz kopiert, der bereits vom übergeordneten Bereich generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="fb23f-139">As these attributes enter into scope, XML Bulk Load copies their values to the customer record that is already generated by the parent scope.</span></span>  
  
-   <span data-ttu-id="fb23f-140">Wenn das XML-Massen laden das Endtag für das-Element erreicht, verlässt das-Element den Gültigkeits **\<Customer>** Bereich.</span><span class="sxs-lookup"><span data-stu-id="fb23f-140">When XML Bulk Load reaches the end tag for the **\<Customer>** element, the element goes out of scope.</span></span> <span data-ttu-id="fb23f-141">Damit wird der Datensatz als vollständig betrachtet und an [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] gesendet.</span><span class="sxs-lookup"><span data-stu-id="fb23f-141">This causes XML Bulk Load to consider the record complete and send it to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="fb23f-142">Das XML-Massen laden folgt diesem Prozess für jedes nachfolgende **\<Customer>** Element.</span><span class="sxs-lookup"><span data-stu-id="fb23f-142">XML Bulk Load follows this process for each subsequent **\<Customer>** element.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="fb23f-143">Da in diesem Modell ein Datensatz eingefügt wird, wenn das Endtag erreicht ist (oder der Knoten den Bereich verlässt), müssen Sie alle mit dem Datensatz verknüpften Daten innerhalb des Knotenbereichs definieren.</span><span class="sxs-lookup"><span data-stu-id="fb23f-143">In this model, because a record is inserted when the end tag is reached (or the node is out of scope), you must define all of the data that is associated with the record within the scope of the node.</span></span>  
  
## <a name="record-subset-and-the-key-ordering-rule"></a><span data-ttu-id="fb23f-144">Daten Satz Teilmenge und Schlüssel Bestellungs Regel</span><span class="sxs-lookup"><span data-stu-id="fb23f-144">Record Subset and the Key Ordering Rule</span></span>  
 <span data-ttu-id="fb23f-145">Wenn Sie ein Zuordnungsschema angeben, das `<sql:relationship>` verwendet, werden diejenigen Datensätze als Teilmenge bezeichnet, die auf der Fremdschlüsselseite der Beziehung generiert werden.</span><span class="sxs-lookup"><span data-stu-id="fb23f-145">When you specify a mapping schema that uses `<sql:relationship>`, the subset term refers to the set of records that is generated on the foreign side of the relationship.</span></span> <span data-ttu-id="fb23f-146">Im folgenden Beispiel sind die CustOrder-Datensätze auf der Fremdschlüsselseite, `<sql:relationship>`.</span><span class="sxs-lookup"><span data-stu-id="fb23f-146">In the following example, the CustOrder records are on the foreign side, `<sql:relationship>`.</span></span>  
  
 <span data-ttu-id="fb23f-147">Nehmen Sie z. B. an, dass eine Datenbank die folgenden Tabellen enthält:</span><span class="sxs-lookup"><span data-stu-id="fb23f-147">For example, suppose a database contains the following tables:</span></span>  
  
-   <span data-ttu-id="fb23f-148">Cust (CustomerID, CompanyName, City)</span><span class="sxs-lookup"><span data-stu-id="fb23f-148">Cust (CustomerID, CompanyName, City)</span></span>  
  
-   <span data-ttu-id="fb23f-149">CustOrder (CustomerID, OrderID)</span><span class="sxs-lookup"><span data-stu-id="fb23f-149">CustOrder (CustomerID, OrderID)</span></span>  
  
 <span data-ttu-id="fb23f-150">Die CustomerID in der CustOrder-Tabelle ist ein Fremdschlüssel, der auf den CustomerID-Primärschlüssel in der Cust-Tabelle verweist.</span><span class="sxs-lookup"><span data-stu-id="fb23f-150">The CustomerID in the CustOrder table is a foreign key that refers to the CustomerID primary key in the Cust table.</span></span>  
  
 <span data-ttu-id="fb23f-151">Betrachten Sie jetzt die im folgenden XSD-Schema mit Anmerkungen angegebene XML-Sicht.</span><span class="sxs-lookup"><span data-stu-id="fb23f-151">Now, consider the XML view as specified in the following annotated XSD schema.</span></span> <span data-ttu-id="fb23f-152">Dieses Schema verwendet `<sql:relationship>`, um die Beziehung zwischen den Tabellen Cust und CustOrder anzugeben.</span><span class="sxs-lookup"><span data-stu-id="fb23f-152">This schema uses `<sql:relationship>` to specify the relationship between the Cust and CustOrder tables.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="CustCustOrder"  
          parent="Cust"  
          parent-key="CustomerID"  
          child="CustOrder"  
          child-key="CustomerID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Customers" sql:relation="Cust" >  
   <xsd:complexType>  
     <xsd:sequence>  
       <xsd:element name="CustomerID"  type="xsd:integer" />  
       <xsd:element name="CompanyName" type="xsd:string" />  
       <xsd:element name="City"        type="xsd:string" />  
       <xsd:element name="Order"   
                          sql:relation="CustOrder"  
                          sql:relationship="CustCustOrder" >  
         <xsd:complexType>  
          <xsd:attribute name="OrderID" type="xsd:integer" />  
         </xsd:complexType>  
       </xsd:element>  
     </xsd:sequence>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="fb23f-153">Die XML-Beispieldaten und die Schritte zum Erstellen eines funktionierenden Beispiels sind unten aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="fb23f-153">The sample XML data and the steps to create a working sample are given below.</span></span>  
  
-   <span data-ttu-id="fb23f-154">Wenn ein **\<Customer>** Elementknoten in der XML-Datendatei in den Gültigkeitsbereich eintritt, generiert XML-Massen laden einen Datensatz für die Cust-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="fb23f-154">When a **\<Customer>** element node in the XML data file enters into scope, XML Bulk Load generates a record for the Cust table.</span></span> <span data-ttu-id="fb23f-155">Beim XML-Massen laden werden dann die erforderlichen Spaltenwerte (CustomerID, CompanyName und City) aus den untergeordneten **\<CustomerID>** Elementen, und kopiert, **\<CompanyName>** **\<City>** Wenn diese Elemente in den Gültigkeitsbereich gelangen.</span><span class="sxs-lookup"><span data-stu-id="fb23f-155">XML Bulk Load then copies the necessary column values (CustomerID, CompanyName, and City) from the **\<CustomerID>**, **\<CompanyName>**, and the **\<City>** child elements as these elements enter into scope.</span></span>  
  
-   <span data-ttu-id="fb23f-156">Wenn ein **\<Order>** Elementknoten in den Bereich gelangt, generiert das XML-Massen laden einen Datensatz für die CustOrder-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="fb23f-156">When an **\<Order>** element node enters into scope, XML Bulk Load generates a record for the CustOrder table.</span></span> <span data-ttu-id="fb23f-157">XML-Massen laden kopiert den Wert des **OrderID** -Attributs in diesen Datensatz.</span><span class="sxs-lookup"><span data-stu-id="fb23f-157">XML Bulk Load copies the value of the **OrderID** attribute to this record.</span></span> <span data-ttu-id="fb23f-158">Der erforderliche Wert für die CustomerID-Spalte wird aus dem untergeordneten- **\<CustomerID>** Element des- **\<Customer>** Elements abgerufen.</span><span class="sxs-lookup"><span data-stu-id="fb23f-158">The value required for the CustomerID column is obtained from the **\<CustomerID>** child element of the **\<Customer>** element.</span></span> <span data-ttu-id="fb23f-159">Beim XML-Massen laden werden die in angegebenen Informationen verwendet, `<sql:relationship>` um den CustomerID-Fremdschlüssel Wert für diesen Datensatz abzurufen, es sei denn, das **CustomerID-** Attribut wurde im- **\<Order>** Element angegeben.</span><span class="sxs-lookup"><span data-stu-id="fb23f-159">XML Bulk Load uses the information that is specified in `<sql:relationship>` to obtain the CustomerID foreign key value for this record, unless the **CustomerID** attribute was specified in the **\<Order>** element.</span></span> <span data-ttu-id="fb23f-160">Generell gilt, dass beim XML-Massenladen der explizit im untergeordneten Element als Fremdschlüsselattribut angegebene Wert verwendet wird (sofern vorhanden) und er nicht über `<sql:relationship>` aus dem übergeordneten Element abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="fb23f-160">The general rule is that if the child element explicitly specifies a value for the foreign key attribute, XML Bulk Load uses that value and does not obtain the value from the parent element by using the specified `<sql:relationship>`.</span></span> <span data-ttu-id="fb23f-161">Wenn dieser **\<Order>** Elementknoten den Gültigkeitsbereich verlässt, sendet XML-Massen laden den Datensatz an [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] und verarbeitet dann alle nachfolgenden **\<Order>** Elementknoten auf die gleiche Weise.</span><span class="sxs-lookup"><span data-stu-id="fb23f-161">As this **\<Order>** element node goes out of scope, XML Bulk Load sends the record to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and then processes all the subsequent **\<Order>** element nodes in the same manner.</span></span>  
  
-   <span data-ttu-id="fb23f-162">Schließlich verlässt der **\<Customer>** Elementknoten den Gültigkeitsbereich.</span><span class="sxs-lookup"><span data-stu-id="fb23f-162">Finally, the **\<Customer>** element node goes out of scope.</span></span> <span data-ttu-id="fb23f-163">Der Kundendatensatz wird daraufhin an [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] gesendet.</span><span class="sxs-lookup"><span data-stu-id="fb23f-163">At that time, XML Bulk Load sends the customer record to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="fb23f-164">Bei allen nachfolgenden Kunden im XML-Datenstrom wird nach demselben Prozess vorgegangen.</span><span class="sxs-lookup"><span data-stu-id="fb23f-164">XML Bulk Load follows this process for all the subsequent customers in the XML data stream.</span></span>  
  
 <span data-ttu-id="fb23f-165">Zwei Beobachtungen zum Zuordnungsschema:</span><span class="sxs-lookup"><span data-stu-id="fb23f-165">Here are two observations about the mapping schema:</span></span>  
  
-   <span data-ttu-id="fb23f-166">Wenn das Schema der "Containment"-Regel entspricht (z. b. werden alle Daten, die dem Kunden und der Bestellung zugeordnet sind, innerhalb des Bereichs der zugeordneten **\<Customer>** -und- **\<Order>** Elementknoten definiert), ist das Massen Laden erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="fb23f-166">When the schema satisfies the "containment" rule (for example, all data that is associated with the customer and the order is defined within the scope of the associated **\<Customer>** and **\<Order>** element nodes), the bulk load succeeds.</span></span>  
  
-   <span data-ttu-id="fb23f-167">Beim Beschreiben des- **\<Customer>** Elements werden seine untergeordneten Elemente in der entsprechenden Reihenfolge angegeben.</span><span class="sxs-lookup"><span data-stu-id="fb23f-167">In describing the **\<Customer>** element, its child elements are specified in the appropriate order.</span></span> <span data-ttu-id="fb23f-168">In diesem Fall wird das untergeordnete- **\<CustomerID>** Element vor dem untergeordneten- **\<Order>** Element angegeben.</span><span class="sxs-lookup"><span data-stu-id="fb23f-168">In this case, the **\<CustomerID>** child element is specified before the **\<Order>** child element.</span></span> <span data-ttu-id="fb23f-169">Dies bedeutet, dass der Elementwert in der XML-Eingabe Datendatei **\<CustomerID>** als Fremdschlüssel Wert verfügbar ist, wenn das Element in den Gültigkeits **\<Order>** Bereich gelangt.</span><span class="sxs-lookup"><span data-stu-id="fb23f-169">This means that in the input XML data file, the **\<CustomerID>** element value is available as the foreign key value when the **\<Order>** element enters into scope.</span></span> <span data-ttu-id="fb23f-170">Die Schlüsselattribute werden gemäß der "Schlüsselsortierregel" zuerst angegeben.</span><span class="sxs-lookup"><span data-stu-id="fb23f-170">The key attributes are specified first; this is the "Key Ordering Rule."</span></span>  
  
     <span data-ttu-id="fb23f-171">Wenn Sie das untergeordnete- **\<CustomerID>** Element nach dem untergeordneten- **\<Order>** Element angeben, ist der Wert nicht verfügbar, wenn das Element in den Gültigkeits **\<Order>** Bereich eintritt.</span><span class="sxs-lookup"><span data-stu-id="fb23f-171">If you specify the **\<CustomerID>** child element after the **\<Order>** child element, the value is not available when the **\<Order>** element enters into scope.</span></span> <span data-ttu-id="fb23f-172">Wenn das **\</Order>** Endtag dann gelesen wird, gilt der Datensatz für die CustOrder-Tabelle als abgeschlossen und wird in die CustOrder-Tabelle mit einem NULL-Wert für die CustomerID-Spalte eingefügt, was nicht das gewünschte Ergebnis ist.</span><span class="sxs-lookup"><span data-stu-id="fb23f-172">When the **\</Order>** end tag is then read, the record for CustOrder table is considered complete and is inserted in the CustOrder table with a NULL value for the CustomerID column, which is not the desired result.</span></span>  
  
#### <a name="to-create-a-working-sample"></a><span data-ttu-id="fb23f-173">So erstellen Sie ein funktionierendes Beispiel</span><span class="sxs-lookup"><span data-stu-id="fb23f-173">To create a working sample</span></span>  
  
1.  <span data-ttu-id="fb23f-174">Speichern Sie das in diesem Beispiel bereitgestellte Schema unter dem Dateinamen SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="fb23f-174">Save the schema that is provided in this example as SampleSchema.xml.</span></span>  
  
2.  <span data-ttu-id="fb23f-175">Erstellen Sie die folgenden Tabellen:</span><span class="sxs-lookup"><span data-stu-id="fb23f-175">Create these tables:</span></span>  
  
    ```  
    CREATE TABLE Cust (  
                  CustomerID     int         PRIMARY KEY,  
                  CompanyName    varchar(20) NOT NULL,  
                  City           varchar(20) DEFAULT 'Seattle')  
    GO  
    CREATE TABLE CustOrder (  
                 OrderID        int         PRIMARY KEY,  
                 CustomerID     int         FOREIGN KEY REFERENCES                                          Cust(CustomerID))  
    GO  
    ```  
  
3.  <span data-ttu-id="fb23f-176">Speichern Sie die folgenden XML-Eingabedaten unter dem Dateinamen SampleXMLData.xml:</span><span class="sxs-lookup"><span data-stu-id="fb23f-176">Save the following sample XML input data as SampleXMLData.xml:</span></span>  
  
    ```  
    <ROOT>  
      <Customers>  
        <CustomerID>1111</CustomerID>  
        <CompanyName>Hanari Carnes</CompanyName>  
        <City>NY</City>   
        <Order OrderID="1" />  
        <Order OrderID="2" />  
      </Customers>  
  
      <Customers>  
        <CustomerID>1112</CustomerID>  
        <CompanyName>Toms Spezialitten</CompanyName>  
        <City>LA</City>  
        <Order OrderID="3" />  
      </Customers>  
      <Customers>  
        <CustomerID>1113</CustomerID>  
        <CompanyName>Victuailles en stock</CompanyName>  
        <Order OrderID="4" />  
    </Customers>  
    </ROOT>  
    ```  
  
4.  <span data-ttu-id="fb23f-177">Speichern Sie folgendes [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic Scripting Edition (VBScript)-Beispiel unter dem Dateinamen BulkLoad.vbs, und führen Sie es aus, um das XML-Massenladen auszuführen:</span><span class="sxs-lookup"><span data-stu-id="fb23f-177">To execute XML Bulk Load, save and execute the following [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic Scripting Edition (VBScript) example (BulkLoad.vbs):</span></span>  
  
    ```  
    set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
    objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
    objBL.ErrorLogFile = "c:\error.log"  
    objBL.CheckConstraints = True  
    objBL.Execute "c:\SampleSchema.xml", "c:\SampleXMLData.xml"  
    set objBL=Nothing  
    ```  
  
## <a name="exceptions-to-the-record-generation-rule"></a><span data-ttu-id="fb23f-178">Ausnahmen von der Datensatzgenerierungsregel</span><span class="sxs-lookup"><span data-stu-id="fb23f-178">Exceptions to the Record Generation Rule</span></span>  
 <span data-ttu-id="fb23f-179">Gelangt ein Knoten vom Typ IDREF oder IDREFS in den Bereich, wird kein Datensatz generiert.</span><span class="sxs-lookup"><span data-stu-id="fb23f-179">XML Bulk Load does not generate a record for a node when it enters into scope if that node is either an IDREF or IDREFS type.</span></span> <span data-ttu-id="fb23f-180">Stellen Sie sicher, dass an irgendeiner Stelle im Schema eine vollständige Beschreibung des Datensatzes vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="fb23f-180">You must make sure that a complete description of the record occurs at some place in the schema.</span></span> <span data-ttu-id="fb23f-181">Die `dt:type="nmtokens"`-Anmerkungen werden ebenso wie der IDREFS-Typ ignoriert.</span><span class="sxs-lookup"><span data-stu-id="fb23f-181">The `dt:type="nmtokens"` annotations are ignored just as the IDREFS type is ignored.</span></span>  
  
 <span data-ttu-id="fb23f-182">Sehen Sie sich beispielsweise das folgende XSD-Schema an, das die **\<Customer>** Elemente und beschreibt **\<Order>** .</span><span class="sxs-lookup"><span data-stu-id="fb23f-182">For example, consider the following XSD schema that describes **\<Customer>** and **\<Order>** elements.</span></span> <span data-ttu-id="fb23f-183">Das- **\<Customer>** Element enthält ein **OrderList** -Attribut des IDREFS-Typs.</span><span class="sxs-lookup"><span data-stu-id="fb23f-183">The **\<Customer>** element includes an **OrderList** attribute of the IDREFS type.</span></span> <span data-ttu-id="fb23f-184">Das `<sql:relationship>`-Tag gibt die 1:n-Beziehung zwischen dem Kunden und der Auftragsliste an.</span><span class="sxs-lookup"><span data-stu-id="fb23f-184">The `<sql:relationship>` tag specifies the one-to-many relationship between the customer and list of orders.</span></span>  
  
 <span data-ttu-id="fb23f-185">Das ist das Schema:</span><span class="sxs-lookup"><span data-stu-id="fb23f-185">This is the schema:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="CustCustOrder"  
                 parent="Cust"  
                 parent-key="CustomerID"  
                 child="CustOrder"  
                 child-key="CustomerID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Customers" sql:relation="Cust" >  
   <xsd:complexType>  
    <xsd:attribute name="CustomerID" type="xsd:integer" />  
    <xsd:attribute name="CompanyName" type="xsd:string" />  
    <xsd:attribute name="City" type="xsd:string" />  
    <xsd:attribute name="OrderList"   
                       type="xsd:IDREFS"   
                       sql:relation="CustOrder"   
                       sql:field="OrderID"  
                       sql:relationship="CustCustOrder" >  
    </xsd:attribute>  
  </xsd:complexType>  
 </xsd:element>  
  
  <xsd:element name="Order" sql:relation="CustOrder" >  
   <xsd:complexType>  
    <xsd:attribute name="OrderID" type="xsd:string" />  
    <xsd:attribute name="CustomerID" type="xsd:integer" />  
    <xsd:attribute name="OrderDate" type="xsd:date" />  
  </xsd:complexType>  
 </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="fb23f-186">Da der Massen Ladevorgang die Knoten des IDREFS-Typs ignoriert, gibt es keine Daten Satz Generierung, wenn der **OrderList** -Attribut Knoten in den Gültigkeitsbereich gelangt.</span><span class="sxs-lookup"><span data-stu-id="fb23f-186">Because Bulk Load ignores the nodes of IDREFS type, there is no record generation when the **OrderList** attribute node enters into scope.</span></span> <span data-ttu-id="fb23f-187">Um die Auftragsdatensätze der Orders-Tabelle hinzuzufügen, müssen Sie demnach diese Aufträge irgendwo im Schema beschreiben.</span><span class="sxs-lookup"><span data-stu-id="fb23f-187">Therefore, if you want the order records added to the Orders table, you must describe those orders somewhere in the schema.</span></span> <span data-ttu-id="fb23f-188">In diesem Schema wird durch das Angeben des- **\<Order>** Elements sichergestellt, dass das XML-Massen laden die Auftragsdaten Sätze der Orders-Tabelle hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="fb23f-188">In this schema, specifying the **\<Order>** element ensures that XML Bulk Load adds the order records to the Orders table.</span></span> <span data-ttu-id="fb23f-189">Das- **\<Order>** Element beschreibt alle Attribute, die zum Auffüllen des Datensatzes für die CustOrder-Tabelle erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="fb23f-189">The **\<Order>** element describes all the attributes that are required to fill the record for the CustOrder table.</span></span>  
  
 <span data-ttu-id="fb23f-190">Sie müssen sicherstellen, dass die Werte **CustomerID** und **OrderID** im- **\<Customer>** Element den Werten im- **\<Order>** Element entsprechen.</span><span class="sxs-lookup"><span data-stu-id="fb23f-190">You must ensure that the **CustomerID** and **OrderID** values in the **\<Customer>** element match the values in the **\<Order>** element.</span></span> <span data-ttu-id="fb23f-191">Sie sind verantwortlich für die Wahrung der referenziellen Integrität.</span><span class="sxs-lookup"><span data-stu-id="fb23f-191">You are responsible for maintaining referential integrity.</span></span>  
  
#### <a name="to-test-a-working-sample"></a><span data-ttu-id="fb23f-192">So testen Sie ein funktionstüchtiges Beispiel</span><span class="sxs-lookup"><span data-stu-id="fb23f-192">To test a working sample</span></span>  
  
1.  <span data-ttu-id="fb23f-193">Erstellen Sie die folgenden Tabellen:</span><span class="sxs-lookup"><span data-stu-id="fb23f-193">Create these tables:</span></span>  
  
    ```  
    CREATE TABLE Cust (  
                  CustomerID     int          PRIMARY KEY,  
                  CompanyName    varchar(20)  NOT NULL,  
                  City           varchar(20)  DEFAULT 'Seattle')  
    GO  
    CREATE TABLE CustOrder (  
                  OrderID        varchar(10) PRIMARY KEY,  
                  CustomerID     int         FOREIGN KEY REFERENCES                                          Cust(CustomerID),  
                  OrderDate      datetime DEFAULT '2000-01-01')  
    GO  
    ```  
  
2.  <span data-ttu-id="fb23f-194">Speichern Sie das in diesem Beispiel bereitgestellte Zuordnungsschema unter dem Dateinamen SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="fb23f-194">Save the mapping schema provided in this example as SampleSchema.xml.</span></span>  
  
3.  <span data-ttu-id="fb23f-195">Speichern Sie die folgenden XML-Daten unter dem Dateinamen SampleXMLData.xml:</span><span class="sxs-lookup"><span data-stu-id="fb23f-195">Save the following sample XML data as SampleXMLData.xml:</span></span>  
  
    ```  
    <ROOT>  
      <Customers CustomerID="1111" CompanyName="Sean Chai" City="NY"  
                 OrderList="Ord1 Ord2" />  
      <Customers CustomerID="1112" CompanyName="Dont Know" City="LA"  
                 OrderList="Ord3 Ord4" />  
      <Order OrderID="Ord1" CustomerID="1111" OrderDate="1999-01-01" />  
      <Order OrderID="Ord2" CustomerID="1111" OrderDate="1999-02-01" />  
      <Order OrderID="Ord3" CustomerID="1112" OrderDate="1999-03-01" />  
      <Order OrderID="Ord4" CustomerID="1112" OrderDate="1999-04-01" />  
    </ROOT>  
    ```  
  
4.  <span data-ttu-id="fb23f-196">Speichern Sie dieses VBScript-Beispiel (SampleVB.vbs), und führen Sie es aus, um das XML-Massenladen auszuführen:</span><span class="sxs-lookup"><span data-stu-id="fb23f-196">To execute XML Bulk Load, save and execute this VBScript example (SampleVB.vbs):</span></span>  
  
    ```  
    set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
    objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
    objBL.ErrorLogFile = "c:\error.log"  
    objBL.CheckConstraints=True  
    objBL.Execute "c:\SampleSchema.xml", "c:\SampleXMLData.xml"  
    set objBL=Nothing  
    ```  
  
  
