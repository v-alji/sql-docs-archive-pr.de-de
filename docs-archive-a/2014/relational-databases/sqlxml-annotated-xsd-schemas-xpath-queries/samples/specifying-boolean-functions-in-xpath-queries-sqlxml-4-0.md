---
title: Angeben von booleschen Funktionen in XPath-Abfragen (SQLXML 4,0) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath queries [SQLXML], Boolean functions
- false function
- not function [SQLXML]
- true function
- Boolean functions
ms.assetid: c72cd333-9294-4d41-84f2-1748bf20e3eb
author: rothja
ms.author: jroth
ms.openlocfilehash: d230c7cd8792066732085b9ce501c0794687d17d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608489"
---
# <a name="specifying-boolean-functions-in-xpath-queries-sqlxml-40"></a><span data-ttu-id="f1136-102">Angeben von booleschen Funktionen in XPath-Abfragen (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="f1136-102">Specifying Boolean Functions in XPath Queries (SQLXML 4.0)</span></span>
  <span data-ttu-id="f1136-103">In den folgenden Beispielen wird gezeigt, wie boolesche Funktionen in XPath-Abfragen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f1136-103">The following examples show how Boolean functions are specified in XPath queries.</span></span> <span data-ttu-id="f1136-104">Die XPath-Abfragen in diesen Beispielen werden für das in SampleSchema1.xml enthaltene Zuordnungsschema angegeben.</span><span class="sxs-lookup"><span data-stu-id="f1136-104">The XPath queries in these examples are specified against the mapping schema contained in SampleSchema1.xml.</span></span> <span data-ttu-id="f1136-105">Weitere Informationen zu diesem Beispiel Schema finden Sie unter [Beispiel: XSD-Schema mit Anmerkungen für XPath-Beispiele &#40;SQLXML 4,0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="f1136-105">For information about this sample schema, see [Sample Annotated XSD Schema for XPath Examples &#40;SQLXML 4.0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="f1136-106">Beispiele</span><span class="sxs-lookup"><span data-stu-id="f1136-106">Examples</span></span>  
  
## <a name="a-specify-the-not-boolean-function"></a><span data-ttu-id="f1136-107">A.</span><span class="sxs-lookup"><span data-stu-id="f1136-107">A.</span></span> <span data-ttu-id="f1136-108">Angeben der booleschen Funktion "not()"</span><span class="sxs-lookup"><span data-stu-id="f1136-108">Specify the not() Boolean function</span></span>  
 <span data-ttu-id="f1136-109">Diese Abfrage gibt alle untergeordneten **\<Customer>** Elemente des Kontext Knotens zurück, die keine untergeordneten **\<Order>** Elemente aufweisen:</span><span class="sxs-lookup"><span data-stu-id="f1136-109">This query returns all the **\<Customer>** child elements of the context node that do not have **\<Order>** child elements:</span></span>  
  
```  
/child::Customer[not(child::Order)]  
```  
  
 <span data-ttu-id="f1136-110">Die `child`-Achse ist die Standardachse.</span><span class="sxs-lookup"><span data-stu-id="f1136-110">The `child` axis is the default.</span></span> <span data-ttu-id="f1136-111">Daher kann die Abfrage wie folgt angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="f1136-111">Therefore, the query can be specified as:</span></span>  
  
```  
/Customer[not(Order)]  
```  
  
#### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="f1136-112">So testen Sie die XPath-Abfrage mit dem Zuordnungsschema</span><span class="sxs-lookup"><span data-stu-id="f1136-112">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="f1136-113">Kopieren Sie den [Beispiel Schema Code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) , und fügen Sie ihn in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="f1136-113">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="f1136-114">Speichern Sie die Datei unter dem Dateinamen SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="f1136-114">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="f1136-115">Erstellen Sie die folgende Vorlage (BooleanFunctionsA.xml), und speichern Sie sie in dem Verzeichnis, in dem SampleSchema1.xml gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="f1136-115">Create the following template (BooleanFunctionsA.xml) and save it in the directory where SampleSchema1.xml is saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        Customer[not(Order)]  
    </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="f1136-116">Der für das Zuordnungsschema (SampleSchema1.xml) angegebene Verzeichnispfad bezieht sich auf das Verzeichnis, in dem die Vorlage gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="f1136-116">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="f1136-117">Es kann auch ein absoluter Pfad angegeben werden. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f1136-117">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="f1136-118">Erstellen und verwenden Sie das SQLXML 4.0-Testskript (Sqlxml4test.vbs), um die Vorlage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f1136-118">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="f1136-119">Weitere Informationen finden Sie unter [Verwenden von ADO zum Ausführen von SQLXML 4,0-Abfragen](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="f1136-119">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="f1136-120">Im Folgenden finden Sie einen Auszug aus dem Resultset der Vorlagenausführung:</span><span class="sxs-lookup"><span data-stu-id="f1136-120">Here is the partial result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Customer CustomerID="13" SalesPersonID="286" TerritoryID="7" AccountNumber="13" CustomerType="S" />   
  <Customer CustomerID="32" SalesPersonID="289" TerritoryID="8" AccountNumber="32" CustomerType="S" />   
  <Customer CustomerID="35" SalesPersonID="275" TerritoryID="2" AccountNumber="35" CustomerType="S" />   
  ...  
</ROOT>  
```  
  
## <a name="b-specify-the-true-and-false-boolean-functions"></a><span data-ttu-id="f1136-121">B.</span><span class="sxs-lookup"><span data-stu-id="f1136-121">B.</span></span> <span data-ttu-id="f1136-122">Angeben der booleschen Funktionen "true()" und "false()"</span><span class="sxs-lookup"><span data-stu-id="f1136-122">Specify the true() and false() Boolean functions</span></span>  
 <span data-ttu-id="f1136-123">Diese Abfrage gibt alle **\<Customer>** untergeordneten-Elemente des Kontext Knotens zurück, die keine untergeordneten **\<Order>** Elemente aufweisen.</span><span class="sxs-lookup"><span data-stu-id="f1136-123">This query returns all **\<Customer>** element children of the context node that do not have **\<Order>** child elements.</span></span> <span data-ttu-id="f1136-124">In relationalem Sinn gibt diese Abfrage alle Kunden zurück, die keine Bestellungen aufgegeben haben.</span><span class="sxs-lookup"><span data-stu-id="f1136-124">In relational terms, this query returns all customers who have not placed any orders.</span></span>  
  
```  
/child::Customer[child::Order=false()]  
```  
  
 <span data-ttu-id="f1136-125">Die `child`-Achse ist die Standardachse.</span><span class="sxs-lookup"><span data-stu-id="f1136-125">The `child` axis is the default.</span></span> <span data-ttu-id="f1136-126">Daher kann die Abfrage wie folgt angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="f1136-126">Therefore, the query can be specified as:</span></span>  
  
```  
/Customer[Order=false()]  
```  
  
 <span data-ttu-id="f1136-127">Diese Abfrage entspricht Folgendem:</span><span class="sxs-lookup"><span data-stu-id="f1136-127">This query is equivalent to the following:</span></span>  
  
```  
/Customer[not(Order)]  
```  
  
 <span data-ttu-id="f1136-128">Die folgende Abfrage gibt alle Kunden zurück, die mindestens eine Bestellung aufgegeben haben:</span><span class="sxs-lookup"><span data-stu-id="f1136-128">The following query returns all the customers who have placed at least one order:</span></span>  
  
```  
/Customer[Order=true()]  
```  
  
 <span data-ttu-id="f1136-129">Diese Abfrage hat die folgende Entsprechung:</span><span class="sxs-lookup"><span data-stu-id="f1136-129">This query is equivalent to this one:</span></span>  
  
```  
/Customer[Order]  
```  
  
#### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="f1136-130">So testen Sie die XPath-Abfrage mit dem Zuordnungsschema</span><span class="sxs-lookup"><span data-stu-id="f1136-130">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="f1136-131">Kopieren Sie den [Beispiel Schema Code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) , und fügen Sie ihn in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="f1136-131">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="f1136-132">Speichern Sie die Datei unter dem Dateinamen SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="f1136-132">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="f1136-133">Erstellen Sie die folgende Vorlage (BooleanFunctionsB.xml), und speichern Sie sie in dem Verzeichnis, in dem SampleSchema1.xml gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="f1136-133">Create the following template (BooleanFunctionsB.xml) and save it in the directory where SampleSchema1.xml is saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        /Customer[Order=false()]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="f1136-134">Der für das Zuordnungsschema (SampleSchema1.xml) angegebene Verzeichnispfad bezieht sich auf das Verzeichnis, in dem die Vorlage gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="f1136-134">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="f1136-135">Es kann auch ein absoluter Pfad angegeben werden. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f1136-135">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="f1136-136">Erstellen und verwenden Sie das SQLXML 4.0-Testskript (Sqlxml4test.vbs), um die Vorlage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f1136-136">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="f1136-137">Weitere Informationen finden Sie unter [Verwenden von ADO zum Ausführen von SQLXML 4,0-Abfragen](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="f1136-137">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="f1136-138">Im Folgenden finden Sie einen Auszug aus dem Resultset der Vorlagenausführung:</span><span class="sxs-lookup"><span data-stu-id="f1136-138">Here is the partial result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Customer CustomerID="13" SalesPersonID="286" TerritoryID="7" AccountNumber="13" CustomerType="S" />   
  <Customer CustomerID="32" SalesPersonID="289" TerritoryID="8" AccountNumber="32" CustomerType="S" />   
  <Customer CustomerID="35" SalesPersonID="275" TerritoryID="2" AccountNumber="35" CustomerType="S" />   
  ...  
</ROOT>  
```  
  
  
