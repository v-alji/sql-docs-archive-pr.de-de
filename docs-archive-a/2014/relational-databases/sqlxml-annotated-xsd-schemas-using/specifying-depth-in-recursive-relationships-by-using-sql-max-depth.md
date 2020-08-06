---
title: 'Angeben von Tiefe in rekursiven Beziehungen mithilfe von SQL: Max-Tiefe | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- max-depth annotation
- XPath queries [SQLXML], recursive relationships
- depth in recursive relationships [SQLXML]
- annotated XSD schemas, recursive relationships
- relationships [SQLXML], recursive relationships
- self joins
- recursive relationships [SQLXML]
- recursion [SQLXML]
- sql:max-depth
- recursive joins [SQLXML]
ms.assetid: 0ffdd57d-dc30-44d9-a8a0-f21cadedb327
author: rothja
ms.author: jroth
ms.openlocfilehash: 5e3ccb2de9c7b2ac8f8702b52aa990d755620e46
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619044"
---
# <a name="specifying-depth-in-recursive-relationships-by-using-sqlmax-depth"></a><span data-ttu-id="43b07-102">Angeben der Tiefe von rekursiven Beziehungen mit 'sql:max-depth'</span><span class="sxs-lookup"><span data-stu-id="43b07-102">Specifying Depth in Recursive Relationships by Using sql:max-depth</span></span>
  <span data-ttu-id="43b07-103">Wenn in einer relationalen Datenbank eine Tabelle in einer Beziehung zu sich selbst steht, wird dies als rekursive Beziehung bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="43b07-103">In relational databases, when a table is involved in a relationship with itself, it is called a recursive relationship.</span></span> <span data-ttu-id="43b07-104">Beispielsweise steht eine Tabelle, in der Mitarbeiterdatensätze gespeichert werden, in einer Beziehung zwischen Vorgesetzten und unterstellten Mitarbeitern mit sich selbst in Beziehung.</span><span class="sxs-lookup"><span data-stu-id="43b07-104">For example, in a supervisor-supervisee relationship, a table storing employee records is involved in a relationship with itself.</span></span> <span data-ttu-id="43b07-105">In diesem Fall spielt die Mitarbeitertabelle auf der einen Seite der Beziehung die Rolle des Vorgesetzten und auf der anderen Seite spielt dieselbe Tabelle die Rolle des unterstellten Mitarbeiters.</span><span class="sxs-lookup"><span data-stu-id="43b07-105">In this case, the employees table plays a role of supervisor on one side of the relationship, and the same table plays a role of supervisee on the other side.</span></span>  
  
 <span data-ttu-id="43b07-106">Zuordnungsschemas können rekursive Beziehungen enthalten, wenn ein Element und sein Vorgänger vom gleichen Typ sind.</span><span class="sxs-lookup"><span data-stu-id="43b07-106">Mapping schemas can include recursive relationships where an element and its ancestor are of the same type.</span></span>  
  
## <a name="example-a"></a><span data-ttu-id="43b07-107">Beispiel A</span><span class="sxs-lookup"><span data-stu-id="43b07-107">Example A</span></span>  
 <span data-ttu-id="43b07-108">Betrachten Sie die folgende Tabelle.</span><span class="sxs-lookup"><span data-stu-id="43b07-108">Consider the following table:</span></span>  
  
```  
Emp (EmployeeID, FirstName, LastName, ReportsTo)  
```  
  
 <span data-ttu-id="43b07-109">In dieser Tabelle enthält die Spalte ReportsTo die Mitarbeiter-ID des Vorgesetzten.</span><span class="sxs-lookup"><span data-stu-id="43b07-109">In this table, the ReportsTo column stores the employee ID of the manager.</span></span>  
  
 <span data-ttu-id="43b07-110">Angenommen, Sie möchten eine XML-Hierarchie der Mitarbeiter generieren, in der sich der Vorgesetzte an der Spitze der Hierarchie befindet, und die Mitarbeiter, die diesem Vorgesetzten unterstellt sind, wie in folgendem XML-Beispielfragment dargestellt, in der zugehörigen Hierarchie angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="43b07-110">Assume that you want to generate an XML hierarchy of employees in which the manager employee is at the top of the hierarchy, and in which the employees that report to that manager appear in the corresponding hierarchy as shown in the following sample XML fragment.</span></span> <span data-ttu-id="43b07-111">Dieses Fragment zeigt die *rekursive* Struktur für Employee 1 an.</span><span class="sxs-lookup"><span data-stu-id="43b07-111">What this fragment shows is the *recursive tree* for employee 1.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<root>  
  <Emp FirstName="Nancy" EmployeeID="1" LastName="Devolio">  
     <Emp FirstName="Andrew" EmployeeID="2" LastName="Fuller" />   
     <Emp FirstName="Janet" EmployeeID="3" LastName="Leverling">  
        <Emp FirstName="Margaret" EmployeeID="4" LastName="Peacock">  
          <Emp FirstName="Steven" EmployeeID="5" LastName="Devolio">  
...  
...  
</root>  
```  
  
 <span data-ttu-id="43b07-112">In diesem Fragment berichtet Mitarbeiter 5 an Mitarbeiter 4, Mitarbeiter 4 berichtet an Mitarbeiter 3, und die Mitarbeiter 3 und 2 berichten an Mitarbeiter 1.</span><span class="sxs-lookup"><span data-stu-id="43b07-112">In this fragment, employee 5 reports to employee 4, employee 4 reports to employee 3, and employees 3 and 2 reports to employee 1.</span></span>  
  
 <span data-ttu-id="43b07-113">Sie können das folgende XSD-Schema verwenden und eine XPath-Abfrage damit ausführen, um dieses Ergebnis zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="43b07-113">To produce this result, you can use the following XSD schema and specify an XPath query against it.</span></span> <span data-ttu-id="43b07-114">Das Schema beschreibt ein **\<Emp>** Element des Typs Mitarbeiter Type, das aus einem untergeordneten **\<Emp>** Element desselben Typs, Mitarbeiter Type, besteht.</span><span class="sxs-lookup"><span data-stu-id="43b07-114">The schema describes an **\<Emp>** element of type EmployeeType, consisting of an **\<Emp>** child element of the same type, EmployeeType.</span></span> <span data-ttu-id="43b07-115">Dies ist eine rekursive Beziehung (das Element und sein Vorgänger sind vom gleichen Typ).</span><span class="sxs-lookup"><span data-stu-id="43b07-115">This is a recursive relationship (the element and its ancestor are of the same type).</span></span> <span data-ttu-id="43b07-116">Außerdem verwendet das Schema eine **\<sql:relationship>** , um die über-/Unterordnungsbeziehung zwischen dem Supervisor und dem Supervisor zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="43b07-116">In addition, the schema uses a **\<sql:relationship>** to describe the parent-child relationship between the supervisor and supervisee.</span></span> <span data-ttu-id="43b07-117">Beachten Sie, dass **\<sql:relationship>** EMP in diesem sowohl die übergeordnete als auch die untergeordnete Tabelle ist.</span><span class="sxs-lookup"><span data-stu-id="43b07-117">Note that in this **\<sql:relationship>**, Emp is both the parent and the child table.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:dt="urn:schemas-microsoft-com:datatypes"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:annotation>  
    <xsd:appinfo>  
      <sql:relationship name="SupervisorSupervisee"  
                                  parent="Emp"  
                                  parent-key="EmployeeID"  
                                  child="Emp"  
                                  child-key="ReportsTo" />  
    </xsd:appinfo>  
  </xsd:annotation>  
  <xsd:element name="Emp" type="EmployeeType"   
                          sql:relation="Emp"   
                          sql:key-fields="EmployeeID"   
                          sql:limit-field="ReportsTo" />  
  <xsd:complexType name="EmployeeType">  
    <xsd:sequence>  
      <xsd:element name="Emp" type="EmployeeType"   
                              sql:relation="Emp"   
                              sql:key-fields="EmployeeID"  
                              sql:relationship="SupervisorSupervisee"  
                              sql:max-depth="6" />  
    </xsd:sequence>   
    <xsd:attribute name="EmployeeID" type="xsd:ID" />  
    <xsd:attribute name="FirstName" type="xsd:string"/>  
    <xsd:attribute name="LastName" type="xsd:string"/>  
  </xsd:complexType>  
</xsd:schema>  
```  
  
 <span data-ttu-id="43b07-118">Weil die Beziehung rekursiv ist, müssen Sie auf irgendeine Weise die Rekursionstiefe im Schema angeben können.</span><span class="sxs-lookup"><span data-stu-id="43b07-118">Because the relationship is recursive, you need some way to specify the depth of recursion in the schema.</span></span> <span data-ttu-id="43b07-119">Andernfalls enthält das Ergebnis eine endlose Rekursion (ein Mitarbeiter berichtet an den Mitarbeiter, der an den Mitarbeiter berichtet usw.).</span><span class="sxs-lookup"><span data-stu-id="43b07-119">Otherwise, the result will be an endless recursion (employee reporting to employee reporting to employee, and so on).</span></span> <span data-ttu-id="43b07-120">Mit der `sql:max-depth`-Anmerkung können Sie die Rekursionstiefe angeben.</span><span class="sxs-lookup"><span data-stu-id="43b07-120">The `sql:max-depth` annotation allows you to specify how deep in the recursion to go.</span></span> <span data-ttu-id="43b07-121">In diesem Beispiel müssen Sie wissen, über wie viele Ebenen die Managementhierarchie der betreffenden Firma verfügt, um einen Wert für `sql:max-depth` angeben zu können.</span><span class="sxs-lookup"><span data-stu-id="43b07-121">In this particular example, to specify a value for `sql:max-depth`, you must know how deep the management hierarchy goes in the company.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="43b07-122">Im Schema wird die `sql:limit-field`-Anmerkung, nicht jedoch die `sql:limit-value`-Anmerkung angegeben.</span><span class="sxs-lookup"><span data-stu-id="43b07-122">The schema specifies the `sql:limit-field` annotation, but does not specify the `sql:limit-value` annotation.</span></span> <span data-ttu-id="43b07-123">Dadurch wird der oberste Knoten der resultierenden Hierarchie lediglich auf diejenigen Mitarbeiter beschränkt, die niemandem unterstellt sind.</span><span class="sxs-lookup"><span data-stu-id="43b07-123">This limits the top node in the resulting hierarchy to only those employees who do not report to anyone.</span></span> <span data-ttu-id="43b07-124">(ReportsTo ist NULL.) Durch angeben `sql:limit-field` von und ohne Angabe `sql:limit-value` von (standardmäßig NULL) wird die Anmerkung erreicht.</span><span class="sxs-lookup"><span data-stu-id="43b07-124">(ReportsTo is NULL.) Specifying `sql:limit-field` and not specifying `sql:limit-value` (which defaults to NULL) annotation accomplishes this.</span></span> <span data-ttu-id="43b07-125">Wenn die resultierende XML-Hierarchie alle möglichen Berichtsstrukturen enthalten soll (die Berichtsstruktur für jeden in der Tabelle enthaltenen Mitarbeiter), dann entfernen Sie die `sql:limit-field`-Anmerkung aus dem Schema.</span><span class="sxs-lookup"><span data-stu-id="43b07-125">If you want the resulting XML to include every possible reporting tree (the reporting tree for every employee in the table), remove the `sql:limit-field` annotation from the schema.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="43b07-126">In der folgenden Prozedur wird die Datenbank tempdb verwendet.</span><span class="sxs-lookup"><span data-stu-id="43b07-126">The following procedure uses the tempdb database.</span></span>  
  
#### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="43b07-127">So testen Sie eine XPath-Beispiel Abfrage für das Schema</span><span class="sxs-lookup"><span data-stu-id="43b07-127">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="43b07-128">Erstellen Sie eine Beispieltabelle namens Emp in der Datenbank tempdb, auf die das virtuelle Stammverzeichnis zeigt.</span><span class="sxs-lookup"><span data-stu-id="43b07-128">Create a sample table called Emp in the tempdb database to which the virtual root points.</span></span>  
  
    ```  
    USE tempdb  
    CREATE TABLE Emp (  
           EmployeeID int primary key,   
           FirstName  varchar(20),   
           LastName   varchar(20),   
           ReportsTo int)  
    ```  
  
2.  <span data-ttu-id="43b07-129">Fügen Sie diese Beispieldaten hinzu:</span><span class="sxs-lookup"><span data-stu-id="43b07-129">Add this sample data:</span></span>  
  
    ```  
    INSERT INTO Emp values (1, 'Nancy', 'Devolio',NULL)  
    INSERT INTO Emp values (2, 'Andrew', 'Fuller',1)  
    INSERT INTO Emp values (3, 'Janet', 'Leverling',1)  
    INSERT INTO Emp values (4, 'Margaret', 'Peacock',3)  
    INSERT INTO Emp values (5, 'Steven', 'Devolio',4)  
    INSERT INTO Emp values (6, 'Nancy', 'Buchanan',5)  
    INSERT INTO Emp values (7, 'Michael', 'Suyama',6)  
    ```  
  
3.  <span data-ttu-id="43b07-130">Kopieren Sie den oben stehenden Schemacode, und fügen Sie ihn in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="43b07-130">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="43b07-131">Speichern Sie die Datei unter dem Dateinamen maxDepth.xml.</span><span class="sxs-lookup"><span data-stu-id="43b07-131">Save the file as maxDepth.xml.</span></span>  
  
4.  <span data-ttu-id="43b07-132">Kopieren Sie die folgende Vorlage, und fügen Sie sie in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="43b07-132">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="43b07-133">Speichern Sie die Datei unter dem Namen maxDepthT.xml im gleichen Verzeichnis, in dem Sie maxDepth.xml gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="43b07-133">Save the file as maxDepthT.xml in the same directory where you saved maxDepth.xml.</span></span> <span data-ttu-id="43b07-134">Die Abfrage in der Vorlage gibt alle in der Emp-Tabelle enthaltenen Elemente zurück.</span><span class="sxs-lookup"><span data-stu-id="43b07-134">The query in the template returns all the employees in the Emp table.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="maxDepth.xml">  
        /Emp  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="43b07-135">Der für das Zuordnungsschema (maxDepth.xml) angegebene Verzeichnispfad bezieht sich auf das Verzeichnis, in dem die Vorlage gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="43b07-135">The directory path specified for the mapping schema (maxDepth.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="43b07-136">Es kann auch ein absoluter Pfad angegeben werden. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="43b07-136">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\maxDepth.xml"  
    ```  
  
5.  <span data-ttu-id="43b07-137">Erstellen und verwenden Sie das SQLXML 4.0-Testskript (Sqlxml4test.vbs), um die Vorlage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="43b07-137">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span> <span data-ttu-id="43b07-138">Weitere Informationen finden Sie unter [Verwenden von ADO zum Ausführen von SQLXML 4,0-Abfragen](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="43b07-138">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="43b07-139">Dies ist das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="43b07-139">This is the result:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<root>  
  <Emp FirstName="Nancy" EmployeeID="1" LastName="Devolio">  
  <Emp FirstName="Andrew" EmployeeID="2" LastName="Fuller" />   
    <Emp FirstName="Janet" EmployeeID="3" LastName="Leverling">  
      <Emp FirstName="Margaret" EmployeeID="4" LastName="Peacock">  
        <Emp FirstName="Steven" EmployeeID="5" LastName="Devolio">  
          <Emp FirstName="Nancy" EmployeeID="6" LastName="Buchanan">  
            <Emp FirstName="Michael" EmployeeID="7" LastName="Suyama" />   
          </Emp>  
        </Emp>  
      </Emp>  
    </Emp>  
  </Emp>  
</root>  
```  
  
> [!NOTE]  
>  <span data-ttu-id="43b07-140">Um im Ergebnis Hierarchien mit einer unterschiedlichen Anzahl von Ebenen zu erzeugen, ändern Sie den Wert der `sql:max-depth`-Anmerkung im Schema und führen die Vorlage nach jeder Änderung erneut aus.</span><span class="sxs-lookup"><span data-stu-id="43b07-140">To produce different depths of hierarchies in the result, change the value of the `sql:max-depth` annotation in the schema and execute the template again after each change.</span></span>  
  
 <span data-ttu-id="43b07-141">Im vorherigen Schema **\<Emp>** hatten alle Elemente genau denselben Attribut Satz (Mitarbeiter-ID, **FirstName**und **LastName**).**EmployeeID**</span><span class="sxs-lookup"><span data-stu-id="43b07-141">In the previous schema, all the **\<Emp>** elements had exactly the same set of attributes (**EmployeeID**, **FirstName**, and **LastName**).</span></span> <span data-ttu-id="43b07-142">Das folgende Schema wurde leicht geändert, um ein zusätzliches **ReportsTo** -Attribut für alle Elemente zurückzugeben **\<Emp>** , die einem Vorgesetzten Berichten.</span><span class="sxs-lookup"><span data-stu-id="43b07-142">The following schema has been slightly modified to return an additional **ReportsTo** attribute for all the **\<Emp>** elements that report to a manager.</span></span>  
  
 <span data-ttu-id="43b07-143">Zum Beispiel zeigt dieses XML-Fragment die Untergebenen von Mitarbeiter 1 an:</span><span class="sxs-lookup"><span data-stu-id="43b07-143">For example, this XML fragment shows the subordinates of employee 1:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<root>  
<Emp FirstName="Nancy" EmployeeID="1" LastName="Devolio">  
  <Emp FirstName="Andrew" EmployeeID="2"   
       ReportsTo="1" LastName="Fuller" />   
  <Emp FirstName="Janet" EmployeeID="3"   
       ReportsTo="1" LastName="Leverling">  
...  
...  
```  
  
 <span data-ttu-id="43b07-144">Dies ist das überarbeitete Schema:</span><span class="sxs-lookup"><span data-stu-id="43b07-144">This is the revised schema:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:dt="urn:schemas-microsoft-com:datatypes"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:annotation>  
    <xsd:documentation>  
      Customer-Order-Order Details Schema  
      Copyright 2000 Microsoft. All rights reserved.  
    </xsd:documentation>  
    <xsd:appinfo>  
      <sql:relationship name="SupervisorSupervisee"   
                  parent="Emp"  
                  parent-key="EmployeeID"  
                  child="Emp"  
                  child-key="ReportsTo" />  
    </xsd:appinfo>  
  </xsd:annotation>  
  <xsd:element name="Emp"   
                   type="EmpType"   
                   sql:relation="Emp"   
                   sql:key-fields="EmployeeID"   
                   sql:limit-field="ReportsTo" />  
  <xsd:complexType name="EmpType">  
    <xsd:sequence>  
       <xsd:element name="Emp"   
                    type="EmpType"   
                    sql:relation="Emp"   
                    sql:key-fields="EmployeeID"  
                    sql:relationship="SupervisorSupervisee"  
                    sql:max-depth="6"/>  
    </xsd:sequence>   
    <xsd:attribute name="EmployeeID" type="xsd:int" />  
    <xsd:attribute name="FirstName" type="xsd:string"/>  
    <xsd:attribute name="LastName" type="xsd:string"/>  
    <xsd:attribute name="ReportsTo" type="xsd:int" />  
  </xsd:complexType>  
</xsd:schema>  
```  
  
## <a name="sqlmax-depth-annotation"></a><span data-ttu-id="43b07-145">sql:max-depth-Anmerkung</span><span class="sxs-lookup"><span data-stu-id="43b07-145">sql:max-depth Annotation</span></span>  
 <span data-ttu-id="43b07-146">In einem Schema, das aus rekursiven Beziehungen besteht, muss die Rekursionstiefe im Schema explizit angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="43b07-146">In a schema consisting of recursive relationships, the depth of recursion must be explicitly specified in the schema.</span></span> <span data-ttu-id="43b07-147">Dies ist erforderlich, um die entsprechende FOR XML EXPLICIT-Abfrage, die die gewünschten Ergebnisse zurückgibt, erfolgreich zu erzeugen.</span><span class="sxs-lookup"><span data-stu-id="43b07-147">This is required to successfully produce the corresponding FOR XML EXPLICIT query that returns the requested results.</span></span>  
  
 <span data-ttu-id="43b07-148">Verwenden Sie die `sql:max-depth`-Anmerkung im Schema, um die Rekursionstiefe einer rekursiven Beziehung anzugeben, die im Schema beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="43b07-148">Use the `sql:max-depth` annotation in the schema to specify the depth of recursion in a recursive relationship that is described in the schema.</span></span> <span data-ttu-id="43b07-149">Der Wert der `sql:max-depth`-Anmerkung ist eine positive ganze Zahl (1 bis 50), die die Anzahl der Rekursionen angibt: Durch die Angabe des Werts 1 wird die Rekursion bei dem Element angehalten, für das die `sql:max-depth`-Anmerkung angegeben wurde. Durch die Angabe des Werts 2 wird die Rekursion in der nächsten Ebene unter dem Element, für das `sql:max-depth` angegeben wurde, angehalten ; usw.</span><span class="sxs-lookup"><span data-stu-id="43b07-149">The value of the `sql:max-depth` annotation is a positive integer (1 to 50) that indicates the number of recursions:  A value of 1 stops the recursion at the element for which the `sql:max-depth` annotation is specified; a value of 2 stops the recursion at the next level from the element at which `sql:max-depth` is specified; and so on.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="43b07-150">In der zugrunde liegenden Implementierung wird eine XPath-Abfrage, die für ein Zuordnungsschema angegeben wird, in eine SELECT... FOR XML (explizite Abfrage).</span><span class="sxs-lookup"><span data-stu-id="43b07-150">In the underlying implementation, an XPath query that is specified against a mapping schema is converted to a SELECT ... FOR XML EXPLICIT query.</span></span> <span data-ttu-id="43b07-151">Bei dieser Abfrage ist es erforderlich, eine endliche Rekursionstiefe anzugeben.</span><span class="sxs-lookup"><span data-stu-id="43b07-151">This query requires you to specify a finite depth of recursion.</span></span> <span data-ttu-id="43b07-152">Je höher der Wert, der für `sql:max-depth` angegeben wird, desto umfangreicher ist die generierte FOR XML EXPLICIT-Abfrage.</span><span class="sxs-lookup"><span data-stu-id="43b07-152">The higher the value that you specify for `sql:max-depth`, the larger the FOR XML EXPLICIT query that is generated.</span></span> <span data-ttu-id="43b07-153">Dies könnte den Abrufvorgang verlangsamen.</span><span class="sxs-lookup"><span data-stu-id="43b07-153">This might slow the retrieval time.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="43b07-154">Bei Updategrams und beim XML-Massenladen wird die -Anmerkung ignoriert.</span><span class="sxs-lookup"><span data-stu-id="43b07-154">Updategrams and XML Bulk Load ignore the max-depth annotation.</span></span> <span data-ttu-id="43b07-155">Dies bedeutet, rekursive Updates oder Einfügungen werden unabhängig von dem Wert ausgeführt, der für  angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="43b07-155">This means, recursive updates or insertions will happen regardless of what value you specify for max-depth.</span></span>  
  
## <a name="specifying-sqlmax-depth-on-complex-elements"></a><span data-ttu-id="43b07-156">Angeben von 'sql:max-depth' für komplexe Elemente</span><span class="sxs-lookup"><span data-stu-id="43b07-156">Specifying sql:max-depth on Complex Elements</span></span>  
 <span data-ttu-id="43b07-157">Die `sql:max-depth`-Anmerkung kann für jedes komplexe Inhaltselement angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="43b07-157">The `sql:max-depth` annotation can be specified on any complex content element.</span></span>  
  
### <a name="recursive-elements"></a><span data-ttu-id="43b07-158">Rekursive Elemente</span><span class="sxs-lookup"><span data-stu-id="43b07-158">Recursive Elements</span></span>  
 <span data-ttu-id="43b07-159">Wenn `sql:max-depth` sowohl für das übergeordnete als auch das untergeordnete Element einer rekursiven Beziehung angegeben wird, dann hat die `sql:max-depth`-Anmerkung Vorrang, die für das übergeordnete Element angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="43b07-159">If `sql:max-depth` is specified on both the parent element and the child element in a recursive relationship, the `sql:max-depth` annotation specified on the parent takes precedence.</span></span> <span data-ttu-id="43b07-160">Beispielsweise wird die `sql:max-depth`-Anmerkung im folgenden Schema sowohl für das übergeordnete als auch das untergeordnete &lt;Emp&gt;-Element angegeben.</span><span class="sxs-lookup"><span data-stu-id="43b07-160">For example, in the following schema, the `sql:max-depth` annotation is specified on both the parent and the child employee elements.</span></span> <span data-ttu-id="43b07-161">In diesem Fall hat, `sql:max-depth=4` für das über **\<Emp>** geordnete Element angegeben (Rolle des Vorgesetzten), Vorrang.</span><span class="sxs-lookup"><span data-stu-id="43b07-161">In this case, `sql:max-depth=4`, specified on the **\<Emp>** parent element (playing a role of supervisor), takes precedence.</span></span> <span data-ttu-id="43b07-162">Der, der `sql:max-depth` für das untergeordnete **\<Emp>** Element (die Rolle "supervisee" spielt) angegeben wird, wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="43b07-162">The `sql:max-depth` specified on the child **\<Emp>** element (playing a role of supervisee) is ignored.</span></span>  
  
#### <a name="example-b"></a><span data-ttu-id="43b07-163">Beispiel B</span><span class="sxs-lookup"><span data-stu-id="43b07-163">Example B</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:dt="urn:schemas-microsoft-com:datatypes"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:annotation>  
    <xsd:appinfo>  
      <sql:relationship name="SupervisorSupervisee"  
                                  parent="Emp"  
                                  parent-key="EmployeeID"  
                                  child="Emp"  
                                  child-key="ReportsTo" />  
    </xsd:appinfo>  
  </xsd:annotation>  
  <xsd:element name="Emp" type="EmployeeType"   
                          sql:relation="Emp"   
                          sql:key-fields="EmployeeID"   
                          sql:limit-field="ReportsTo"   
                          sql:max-depth="3" />  
  <xsd:complexType name="EmployeeType">  
    <xsd:sequence>  
      <xsd:element name="Emp" type="EmployeeType"   
                              sql:relation="Emp"   
                              sql:key-fields="EmployeeID"  
                              sql:relationship="SupervisorSupervisee"  
                              sql:max-depth="2" />  
    </xsd:sequence>   
    <xsd:attribute name="EmployeeID" type="xsd:ID" />  
    <xsd:attribute name="FirstName" type="xsd:string"/>  
    <xsd:attribute name="LastName" type="xsd:string"/>  
  </xsd:complexType>  
</xsd:schema>  
```  
  
 <span data-ttu-id="43b07-164">Um dieses Schema zu testen, führen Sie die Schritte für Beispiel A weiter oben in diesem Thema aus.</span><span class="sxs-lookup"><span data-stu-id="43b07-164">To test this schema, follow the steps provided for Sample A, earlier in this topic.</span></span>  
  
### <a name="nonrecursive-elements"></a><span data-ttu-id="43b07-165">Nicht rekursive Elemente</span><span class="sxs-lookup"><span data-stu-id="43b07-165">Nonrecursive Elements</span></span>  
 <span data-ttu-id="43b07-166">Wenn die `sql:max-depth`-Anmerkung für ein Element in dem Schema angegeben wird, das keine Rekursion bewirkt, dann wird sie ignoriert.</span><span class="sxs-lookup"><span data-stu-id="43b07-166">If the `sql:max-depth` annotation is specified on an element in the schema that does not cause any recursion, it is ignored.</span></span> <span data-ttu-id="43b07-167">Im folgenden Schema besteht ein-Element aus einem untergeordneten- **\<Emp>** **\<Constant>** Element, das wiederum über ein untergeordnetes-Element verfügt **\<Emp>** .</span><span class="sxs-lookup"><span data-stu-id="43b07-167">In the following schema, an **\<Emp>** element consists of a **\<Constant>** child element, which, in turn, has an **\<Emp>** child element.</span></span>  
  
 <span data-ttu-id="43b07-168">In diesem Schema wird die-Anmerkung, die `sql:max-depth` für das-Element angegeben ist, **\<Constant>** ignoriert, da es keine Rekursion zwischen dem über **\<Emp>** geordneten und dem untergeordneten- **\<Constant>** Element gibt.</span><span class="sxs-lookup"><span data-stu-id="43b07-168">In this schema, the `sql:max-depth` annotation specified on the **\<Constant>** element is ignored because there is no recursion between the **\<Emp>** parent and the **\<Constant>** child element.</span></span> <span data-ttu-id="43b07-169">Es gibt jedoch eine Rekursion zwischen dem **\<Emp>** Vorgänger und dem untergeordneten Element **\<Emp>** .</span><span class="sxs-lookup"><span data-stu-id="43b07-169">But there is recursion between the **\<Emp>** ancestor and the **\<Emp>** child.</span></span> <span data-ttu-id="43b07-170">Das Schema gibt die `sql:max-depth`-Anmerkung für beide an.</span><span class="sxs-lookup"><span data-stu-id="43b07-170">The schema specifies the `sql:max-depth` annotation on both.</span></span> <span data-ttu-id="43b07-171">Daher hat die- `sql:max-depth` Anmerkung, die auf dem Vorgänger ( **\<Emp>** in der Rolle "Supervisor") angegeben ist, Vorrang.</span><span class="sxs-lookup"><span data-stu-id="43b07-171">Therefore, the `sql:max-depth` annotation that is specified on the ancestor (**\<Emp>** in the supervisor role) takes precedence.</span></span>  
  
#### <a name="example-c"></a><span data-ttu-id="43b07-172">Beispiel C</span><span class="sxs-lookup"><span data-stu-id="43b07-172">Example C</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:annotation>  
    <xsd:appinfo>  
      <sql:relationship name="SupervisorSupervisee"   
                  parent="Emp"   
                  child="Emp"   
                  parent-key="EmployeeID"   
                  child-key="ReportsTo"/>  
    </xsd:appinfo>  
  </xsd:annotation>  
  <xsd:element name="Emp"   
               sql:relation="Emp"   
               type="EmpType"  
               sql:limit-field="ReportsTo"  
               sql:max-depth="1" />  
    <xsd:complexType name="EmpType" >  
      <xsd:sequence>  
       <xsd:element name="Constant"   
                    sql:is-constant="1"   
                    sql:max-depth="20" >  
         <xsd:complexType >  
           <xsd:sequence>  
            <xsd:element name="Emp"   
                         sql:relation="Emp" type="EmpType"  
                         sql:relationship="SupervisorSupervisee"   
                         sql:max-depth="3" />  
         </xsd:sequence>  
         </xsd:complexType>  
         </xsd:element>  
      </xsd:sequence>  
      <xsd:attribute name="EmployeeID" type="xsd:int" />  
    </xsd:complexType>  
</xsd:schema>  
```  
  
 <span data-ttu-id="43b07-173">Um dieses Schema zu testen, führen Sie die für Beispiel A weiter oben in diesem Thema beschriebenen Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="43b07-173">To test this schema, follow the steps provided for Example A, earlier in this topic.</span></span>  
  
## <a name="complex-types-derived-by-restriction"></a><span data-ttu-id="43b07-174">Durch Einschränkungen abgeleitete komplexe Typen</span><span class="sxs-lookup"><span data-stu-id="43b07-174">Complex Types Derived by Restriction</span></span>  
 <span data-ttu-id="43b07-175">Wenn eine Ableitung komplexer Typen von vorhanden **\<restriction>** ist, können Elemente des entsprechenden komplexen Basistyps die-Anmerkung nicht angeben `sql:max-depth` .</span><span class="sxs-lookup"><span data-stu-id="43b07-175">If you have a complex type derivation by **\<restriction>**, elements of the corresponding base complex type cannot specify the `sql:max-depth` annotation.</span></span> <span data-ttu-id="43b07-176">In diesen Fällen kann die `sql:max-depth`-Anmerkung dem Element des abgeleiteten Typs hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="43b07-176">In these cases, the `sql:max-depth` annotation can be added to the element of the derived type.</span></span>  
  
 <span data-ttu-id="43b07-177">Wenn Sie hingegen eine Ableitung komplexer Typen durch haben **\<extension>** , können die Elemente des entsprechenden komplexen Basistyps die-Anmerkung angeben `sql:max-depth` .</span><span class="sxs-lookup"><span data-stu-id="43b07-177">On the other hand, if you have a complex type derivation by **\<extension>**, the elements of the corresponding base complex type can specify the `sql:max-depth` annotation.</span></span>  
  
 <span data-ttu-id="43b07-178">Beispielsweise erzeugt das folgende XSD-Schema einen Fehler, weil die `sql:max-depth`-Anmerkung für den Basistyp angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="43b07-178">For example, the following XSD schema generates an error because the `sql:max-depth` annotation is specified on the base type.</span></span> <span data-ttu-id="43b07-179">Diese Anmerkung wird für einen Typ, der von einem anderen Typ abgeleitet ist, nicht unterstützt **\<restriction>** .</span><span class="sxs-lookup"><span data-stu-id="43b07-179">This annotation is not supported on a type that is derived by **\<restriction>** from another type.</span></span> <span data-ttu-id="43b07-180">Zur Behebung dieses Problems müssen Sie das Schema ändern und die `sql:max-depth`-Anmerkung für Elemente im abgeleiteten Typ angeben.</span><span class="sxs-lookup"><span data-stu-id="43b07-180">To fix this problem, you must change the schema and specify the `sql:max-depth` annotation on element in the derived type.</span></span>  
  
#### <a name="example-d"></a><span data-ttu-id="43b07-181">Beispiel D</span><span class="sxs-lookup"><span data-stu-id="43b07-181">Example D</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:dt="urn:schemas-microsoft-com:datatypes"  
            xmlns:msdata="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:complexType name="CustomerBaseType">   
    <xsd:sequence>  
       <xsd:element name="CID" msdata:field="CustomerID" />  
       <xsd:element name="CompanyName"/>  
       <xsd:element name="Customers" msdata:max-depth="3">  
         <xsd:annotation>  
           <xsd:appinfo>  
             <msdata:relationship  
                     parent="Customers"  
                     parent-key="CustomerID"  
                     child-key="CustomerID"  
                     child="Customers" />  
           </xsd:appinfo>  
         </xsd:annotation>  
       </xsd:element>  
    </xsd:sequence>  
  </xsd:complexType>  
  <xsd:element name="Customers" type="CustomerType"/>  
  <xsd:complexType name="CustomerType">  
    <xsd:complexContent>  
       <xsd:restriction base="CustomerBaseType">  
          <xsd:sequence>  
            <xsd:element name="CID"   
                         type="xsd:string"/>  
            <xsd:element name="CompanyName"   
                         type="xsd:string"  
                         msdata:field="CName" />  
            <xsd:element name="Customers"   
                         type="CustomerType" />  
          </xsd:sequence>  
       </xsd:restriction>  
    </xsd:complexContent>  
  </xsd:complexType>  
</xsd:schema>   
```  
  
 <span data-ttu-id="43b07-182">Im Schema wird `sql:max-depth` für ein Element des komplexen Typs `CustomerBaseType` angegeben.</span><span class="sxs-lookup"><span data-stu-id="43b07-182">In the schema, `sql:max-depth` is specified on a `CustomerBaseType` complex type.</span></span> <span data-ttu-id="43b07-183">Das Schema gibt auch ein- **\<Customer>** Element vom Typ an `CustomerType` , das von abgeleitet wird `CustomerBaseType` .</span><span class="sxs-lookup"><span data-stu-id="43b07-183">The schema also specifies a **\<Customer>** element of type `CustomerType`, which is derived from `CustomerBaseType`.</span></span> <span data-ttu-id="43b07-184">Eine mit diesem Schema ausgeführte XPath-Abfrage erzeugt einen Fehler, weil `sql:max-depth` nicht für Elemente unterstützt wird, die in einem einfachen Einschränkungstyp definiert sind.</span><span class="sxs-lookup"><span data-stu-id="43b07-184">An XPath query specified on such a schema will generate an error, because `sql:max-depth` is not supported on an element that is defined in a restriction base type.</span></span>  
  
## <a name="schemas-with-a-deep-hierarchy"></a><span data-ttu-id="43b07-185">Schemas mit einer tiefen Hierarchie</span><span class="sxs-lookup"><span data-stu-id="43b07-185">Schemas with a Deep Hierarchy</span></span>  
 <span data-ttu-id="43b07-186">Möglicherweise liegt ein Schema vor, das eine tiefe Hierarchie umfasst, in der ein Element ein untergeordnetes Element enthält, das wiederum ein untergeordnetes Element enthalt usw.</span><span class="sxs-lookup"><span data-stu-id="43b07-186">You might have a schema that includes a deep hierarchy in which an element contains a child element, which in turn contains another child element, and so on.</span></span> <span data-ttu-id="43b07-187">Wenn die in einem solchen Schema angegebene `sql:max-depth`-Anmerkung ein XML-Dokument erzeugt, das eine Hierarchie mit mehr als 500 Ebenen umfasst (wobei das oberste Element auf Ebene 1, das diesem untergeordnete Element auf Ebene 2 etc. angesiedelt ist), wird ein Fehler zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="43b07-187">If the `sql:max-depth` annotation specified in such a schema generates an XML document that includes a hierarchy of more than 500 levels (with top-level element at level 1, its child at level 2, and so on), an error is returned.</span></span>  
  
  
