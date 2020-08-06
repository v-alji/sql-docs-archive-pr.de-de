---
title: 'Erstellen von CDATA-Abschnitten mit SQL: use-cdata (SQLXML 4,0) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- markup characters [SQLXML]
- special characters [SQLXML]
- use-cdata annotation
- plain text [SQLXML]
- CDATA sections
- escaping blocks of text [SQLXML]
- annotated XSD schemas, CDATA sections
- sql:use-cdata
ms.assetid: 26d2b9dc-f857-44ff-bcd4-aaf64ff809d0
author: rothja
ms.author: jroth
ms.openlocfilehash: c0ba0787efbda400590a75f0f3529e3df8819e41
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621434"
---
# <a name="creating-cdata-sections-using-sqluse-cdata-sqlxml-40"></a><span data-ttu-id="2d323-102">Erstellen von CDATA-Abschnitten mit sql:use-cdata (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="2d323-102">Creating CDATA Sections Using sql:use-cdata (SQLXML 4.0)</span></span>
  <span data-ttu-id="2d323-103">In XML werden Textblöcke, die Zeichen enthalten, die andernfalls als Markup erkannt würden, mit CDATA-Abschnitten in Escapezeichen umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="2d323-103">In XML, CDATA sections are used to escape blocks of text that contain characters that would otherwise be recognized as markup characters.</span></span>  
  
 <span data-ttu-id="2d323-104">Eine Datenbank in Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] kann manchmal Zeichen enthalten, die vom XML-Parser als Markup Zeichen behandelt werden, z. b. Spitze Klammern ( \< and > ), das kleiner-als-oder-gleich-Symbol (<=) und das kaufmännische und-Zeichen (&) als Markup Zeichen behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="2d323-104">A database in Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can sometimes contain characters that are treated as markup characters by the XML parser; for example, angle brackets (\< and >), the less-than-or-equal-to symbol (<=), and the ampersand (&) are treated as markup characters.</span></span> <span data-ttu-id="2d323-105">Sie können diese Sonderzeichen in einem CDATA-Abschnitt jedoch umschließen, um zu verhindern, dass sie als Markupzeichen behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="2d323-105">However, you can wrap this type of special characters in a CDATA section to prevent them from being treated as markup characters.</span></span> <span data-ttu-id="2d323-106">Der Text innerhalb des CDATA-Abschnitts wird vom XML-Parser als Nur-Text behandelt.</span><span class="sxs-lookup"><span data-stu-id="2d323-106">The text within the CDATA section is treated by the XML parser as plain text.</span></span>  
  
 <span data-ttu-id="2d323-107">Mit der `sql:use-cdata`-Anmerkung wird angegeben, dass die von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] zurückgegebenen Daten in einem CDATA-Abschnitt umschlossen werden (d. h., sie gibt an, ob der Wert aus einer Spalte, die von `sql:field` angegeben wird, in einem CDATA-Abschnitt eingeschlossen werden soll).</span><span class="sxs-lookup"><span data-stu-id="2d323-107">The `sql:use-cdata` annotation is used to specify that the data returned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] should be wrapped in a CDATA section (that is, it indicates whether the value from a column that is specified by `sql:field` should be enclosed in a CDATA section).</span></span> <span data-ttu-id="2d323-108">Die `sql:use-cdata`-Anmerkung kann nur für Elemente angegeben werden, die einer Datenbankspalte zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="2d323-108">The `sql:use-cdata` annotation can be specified only on elements that map to a database column.</span></span>  
  
 <span data-ttu-id="2d323-109">Die `sql:use-cdata`-Anmerkung akzeptiert einen booleschen Wert (0 = false und 1 = true).</span><span class="sxs-lookup"><span data-stu-id="2d323-109">The `sql:use-cdata` annotation takes a Boolean value (0 = false, 1 = true).</span></span> <span data-ttu-id="2d323-110">Zulässig sind die Werte 0, 1, true und false.</span><span class="sxs-lookup"><span data-stu-id="2d323-110">The acceptable values are 0, 1, true, and false.</span></span>  
  
 <span data-ttu-id="2d323-111">Diese Anmerkung kann nicht mit `sql:url-encode` oder für die Attributtypen ID, IDREF, IDREFS, NMTOKEN und NMTOKENS verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2d323-111">This annotation cannot be used with `sql:url-encode` or on the ID, IDREF, IDREFS, NMTOKEN, and NMTOKENS attribute types.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="2d323-112">Beispiele</span><span class="sxs-lookup"><span data-stu-id="2d323-112">Examples</span></span>  
 <span data-ttu-id="2d323-113">Es müssen bestimmte Anforderungen erfüllt sein, damit aus den folgenden Beispielen funktionierende Beispiele erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="2d323-113">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="2d323-114">Weitere Informationen finden Sie unter [Anforderungen zum Ausführen von SQLXML-Beispielen](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="2d323-114">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-sqluse-cdata-on-an-element"></a><span data-ttu-id="2d323-115">A.</span><span class="sxs-lookup"><span data-stu-id="2d323-115">A.</span></span> <span data-ttu-id="2d323-116">Angeben von sql:use-cdata für ein Element</span><span class="sxs-lookup"><span data-stu-id="2d323-116">Specifying sql:use-cdata on an element</span></span>  
 <span data-ttu-id="2d323-117">Im folgenden Schema `sql:use-cdata` wird für das-Element im-Element auf 1 (true) festgelegt **\<AddressLine1>** **\<Address>** .</span><span class="sxs-lookup"><span data-stu-id="2d323-117">In the following schema, `sql:use-cdata` is set to 1 (True) for the **\<AddressLine1>** within the **\<Address>** element.</span></span> <span data-ttu-id="2d323-118">Daraufhin werden die Daten in einem CDATA-Abschnitt zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2d323-118">As a result, the data is returned in a CDATA section.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Address"   
               sql:relation="Person.Address"   
               sql:key-fields="AddressID" >  
   <xsd:complexType>  
        <xsd:sequence>  
          <xsd:element name="AddressID"  type="xsd:string" />  
          <xsd:element name="AddressLine1" type="xsd:string"   
                       sql:use-cdata="1" />  
        </xsd:sequence>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="2d323-119">So testen Sie eine XPath-Beispiel Abfrage für das Schema</span><span class="sxs-lookup"><span data-stu-id="2d323-119">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="2d323-120">Kopieren Sie den oben stehenden Schemacode, und fügen Sie ihn in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="2d323-120">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="2d323-121">Speichern Sie die Datei unter dem Dateinamen UseCData.xml.</span><span class="sxs-lookup"><span data-stu-id="2d323-121">Save the file as UseCData.xml.</span></span>  
  
2.  <span data-ttu-id="2d323-122">Kopieren Sie die folgende Vorlage, und fügen Sie sie in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="2d323-122">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="2d323-123">Speichern Sie die Datei unter dem Namen UseCDataT.xml im gleichen Verzeichnis, in dem Sie UseCData.xml gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="2d323-123">Save the file as UseCDataT.xml in the same directory where you saved UseCData.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="UseCData.xml">  
            /Address[AddressID < 11]  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="2d323-124">Der für das Zuordnungschema (UseCData.xml) angegebene Verzeichnispfad bezieht sich auf das Verzeichnis, in dem die Vorlage gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="2d323-124">The directory path specified for the mapping schema (UseCData.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="2d323-125">Es kann auch ein absoluter Pfad angegeben werden. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2d323-125">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\UseCData.xml"  
    ```  
  
3.  <span data-ttu-id="2d323-126">Erstellen und verwenden Sie das SQLXML 4.0-Testskript (Sqlxml4test.vbs), um die Vorlage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="2d323-126">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="2d323-127">Weitere Informationen finden Sie unter [Verwenden von ADO zum Ausführen von SQLXML 4,0-Abfragen](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="2d323-127">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="2d323-128">Im Folgenden wird ein Teil des Resultsets aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="2d323-128">This is the partial result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">   
  <Address>   
    <AddressID>1</CustomerID>   
    <AddressLine1>   
      <![CDATA[ 1970 Napa Ct.  ]]>   
    </AddressLine1>   
  </Address>  
  <Address>  
    <AddressLine1>   
      <![CDATA[ 9833 Mt. Dias Blv. ]]>   
    </AddressLine1>   
  </Address>  
  ...  
</ROOT>  
```  
  
  
