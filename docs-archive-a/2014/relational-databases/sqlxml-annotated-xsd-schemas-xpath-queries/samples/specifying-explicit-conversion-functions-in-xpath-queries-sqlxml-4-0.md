---
title: Angeben von expliziten Konvertierungs Funktionen in XPath-Abfragen (SQLXML 4,0) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- explicit conversion functions [SQLXML]
- string function
- number function
- XPath queries [SQLXML], explicit conversion functions
ms.assetid: 1111cb5d-2bd9-4bdb-8de2-dc0e47452dd6
author: rothja
ms.author: jroth
ms.openlocfilehash: 5b4b9bd5f5665c8cb86cb74c1397e2bd06e113fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608484"
---
# <a name="specifying-explicit-conversion-functions-in-xpath-queries-sqlxml-40"></a><span data-ttu-id="3e754-102">Angeben von expliziten Konvertierungsfunktionen in XPath-Abfragen (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="3e754-102">Specifying Explicit Conversion Functions in XPath Queries (SQLXML 4.0)</span></span>
  <span data-ttu-id="3e754-103">In den folgenden Beispielen wird gezeigt, wie explizite Konvertierungsfunktionen in XPath-Abfragen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="3e754-103">The following examples show how explicit conversion functions are specified in XPath queries.</span></span> <span data-ttu-id="3e754-104">Die XPath-Abfragen in diesen Beispielen werden für das in SampleSchema1.xml enthaltene Zuordnungsschema angegeben.</span><span class="sxs-lookup"><span data-stu-id="3e754-104">The XPath queries in these examples are specified against the mapping schema contained in SampleSchema1.xml.</span></span> <span data-ttu-id="3e754-105">Weitere Informationen zu diesem Beispiel Schema finden Sie unter [Beispiel: XSD-Schema mit Anmerkungen für XPath-Beispiele &#40;SQLXML 4,0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="3e754-105">For information about this sample schema, see [Sample Annotated XSD Schema for XPath Examples &#40;SQLXML 4.0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="3e754-106">Beispiele</span><span class="sxs-lookup"><span data-stu-id="3e754-106">Examples</span></span>  
  
### <a name="a-use-the-number-explicit-conversion-function"></a><span data-ttu-id="3e754-107">A.</span><span class="sxs-lookup"><span data-stu-id="3e754-107">A.</span></span> <span data-ttu-id="3e754-108">Verwenden der expliziten Konvertierungsfunktion number()</span><span class="sxs-lookup"><span data-stu-id="3e754-108">Use the number() explicit conversion function</span></span>  
 <span data-ttu-id="3e754-109">Die `number()`-Funktion konvertiert ein Argument in eine Zahl.</span><span class="sxs-lookup"><span data-stu-id="3e754-109">The `number()` function converts an argument to a number.</span></span>  
  
 <span data-ttu-id="3e754-110">Wenn der Wert von " **ContactID** " nicht numerisch ist, konvertiert die folgende Abfrage " **ContactID** " in eine Zahl und vergleicht sie mit dem Wert 4.</span><span class="sxs-lookup"><span data-stu-id="3e754-110">Assuming the value of **ContactID** is nonnumeric, the following query converts **ContactID** to a number and compares it with the value 4.</span></span> <span data-ttu-id="3e754-111">Die Abfrage gibt dann alle untergeordneten- **\<Employee>** Elemente des Kontext Knotens zurück, wobei das **ContactID** -Attribut den numerischen Wert 4 aufweist:</span><span class="sxs-lookup"><span data-stu-id="3e754-111">The query then returns all **\<Employee>** element children of the context node with the **ContactID** attribute that has a numeric value of 4:</span></span>  
  
```  
/child::Contact[number(attribute::ContactID)= 4]  
```  
  
 <span data-ttu-id="3e754-112">Es kann eine Abkürzung für die `attribute`-Achse (@) angegeben werden, und da die `child`-Achse die Standardachse ist, muss sie in der Abfrage nicht angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="3e754-112">A shortcut to the `attribute` axis (@) can be specified, and because the `child` axis is the default, it can be omitted from the query:</span></span>  
  
```  
/Contact[number(@ContactID) = 4]  
```  
  
 <span data-ttu-id="3e754-113">In relationalen Begriffen gibt die Abfrage einen Mitarbeiter mit der **ContactID** -ID 4 zurück.</span><span class="sxs-lookup"><span data-stu-id="3e754-113">In relational terms, the query returns an employee with a **ContactID** of 4.</span></span>  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="3e754-114">So testen Sie die XPath-Abfrage mit dem Zuordnungsschema</span><span class="sxs-lookup"><span data-stu-id="3e754-114">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="3e754-115">Kopieren Sie den [Beispiel Schema Code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) , und fügen Sie ihn in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="3e754-115">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="3e754-116">Speichern Sie die Datei unter dem Dateinamen SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="3e754-116">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="3e754-117">Erstellen Sie die folgende Vorlage (ExplicitConversionA.xml), und speichern Sie sie in dem Verzeichnis, in dem SampleSchema1.xml gespeichert wurde.</span><span class="sxs-lookup"><span data-stu-id="3e754-117">Create the following template (ExplicitConversionA.xml) and save it in the directory where SampleSchema1.xml was saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        /Contact[number(@ContactID)=4]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="3e754-118">Der für das Zuordnungsschema (SampleSchema1.xml) angegebene Verzeichnispfad bezieht sich auf das Verzeichnis, in dem die Vorlage gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="3e754-118">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="3e754-119">Es kann auch ein absoluter Pfad angegeben werden. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3e754-119">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="3e754-120">Erstellen und verwenden Sie das SQLXML 4.0-Testskript (Sqlxml4test.vbs), um die Vorlage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="3e754-120">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="3e754-121">Weitere Informationen finden Sie unter [Verwenden von ADO zum Ausführen von SQLXML 4,0-Abfragen](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="3e754-121">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="3e754-122">Das Resultset für diese Vorlagenausführung sieht so aus:</span><span class="sxs-lookup"><span data-stu-id="3e754-122">The result set for this template execution is:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Contact ContactID="4" LastName="Acevedo" FirstName="Humberto" Title="Sr." />   
</ROOT>  
```  
  
### <a name="b-use-the-string-explicit-conversion-function"></a><span data-ttu-id="3e754-123">B.</span><span class="sxs-lookup"><span data-stu-id="3e754-123">B.</span></span> <span data-ttu-id="3e754-124">Verwenden der expliziten Konvertierungsfunktion string()</span><span class="sxs-lookup"><span data-stu-id="3e754-124">Use the string() explicit conversion function</span></span>  
 <span data-ttu-id="3e754-125">Die `string()`-Funktion konvertiert ein Argument in eine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="3e754-125">The `string()` function converts an argument to a string.</span></span>  
  
 <span data-ttu-id="3e754-126">Mit der folgenden Abfrage wird " **ContactID** " in eine Zeichenfolge konvertiert und mit dem Zeichen folgen Wert "4" verglichen.</span><span class="sxs-lookup"><span data-stu-id="3e754-126">The following query converts **ContactID** to a string and compares it with the string value "4".</span></span> <span data-ttu-id="3e754-127">Die Abfrage gibt alle untergeordneten- **\<Employee>** Elemente des Kontext Knotens mit einer **ContactID** zurück, die den Zeichen folgen Wert "4" aufweist:</span><span class="sxs-lookup"><span data-stu-id="3e754-127">The query returns all **\<Employee>** element children of the context node with a **ContactID** with a string value of "4":</span></span>  
  
```  
/child::Contact[string(attribute::ContactID)="4"]  
```  
  
 <span data-ttu-id="3e754-128">Es kann eine Abkürzung für die `attribute`-Achse (@) angegeben werden, und da die `child`-Achse die Standardachse ist, muss sie in der Abfrage nicht angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="3e754-128">A shortcut to the `attribute` axis (@) can be specified, and because the `child` axis is the default, it can be omitted from the query:</span></span>  
  
```  
/Contact[string(@ContactID)="4"]  
```  
  
 <span data-ttu-id="3e754-129">Diese Abfrage gibt praktisch die gleichen Ergebnisse wie das vorherige Abfragebeispiel zurück, obwohl hier der Zeichenfolgenwert und nicht der numerische Wert (d. h. die Zahl 4) ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="3e754-129">Functionally, this query returns the same results as the previous example query, though the evaluation is done against a string value and not the numeric value (that is, the number 4).</span></span>  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="3e754-130">So testen Sie die XPath-Abfrage mit dem Zuordnungsschema</span><span class="sxs-lookup"><span data-stu-id="3e754-130">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="3e754-131">Kopieren Sie den [Beispiel Schema Code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) , und fügen Sie ihn in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="3e754-131">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="3e754-132">Speichern Sie die Datei unter dem Dateinamen SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="3e754-132">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="3e754-133">Erstellen Sie die folgende Vorlage (ExplicitConversionB.xml), und speichern Sie sie in dem Verzeichnis, in dem SampleSchema1.xml gespeichert wurde.</span><span class="sxs-lookup"><span data-stu-id="3e754-133">Create the following template (ExplicitConversionB.xml) and save it in the directory where SampleSchema1.xml was saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        Contact[string(@ContactID)="4"]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="3e754-134">Der für das Zuordnungsschema (SampleSchema1.xml) angegebene Verzeichnispfad bezieht sich auf das Verzeichnis, in dem die Vorlage gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="3e754-134">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="3e754-135">Es kann auch ein absoluter Pfad angegeben werden. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3e754-135">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="3e754-136">Erstellen und verwenden Sie das SQLXML 4.0-Testskript (Sqlxml4test.vbs), um die Vorlage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="3e754-136">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="3e754-137">Weitere Informationen finden Sie unter [Verwenden von ADO zum Ausführen von SQLXML 4,0-Abfragen](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="3e754-137">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="3e754-138">Im Folgenden finden Sie das Resultset der Vorlagenausführung:</span><span class="sxs-lookup"><span data-stu-id="3e754-138">Here is the result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Contact ContactID="4" LastName="Acevedo" FirstName="Humberto" Title="Sr." />   
</ROOT>  
```  
  
  
