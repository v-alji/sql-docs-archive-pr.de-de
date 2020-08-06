---
title: XML-Schemaauflistungen (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- XSD schemas [SQL Server]
- xml_schema_namespace function
- XML schema collections [SQL Server], about XML schema collections
- metadata [SQL Server], XML schema collections
- queries [XML in SQL Server], XML schema collections
- schema collections [SQL Server]
- schemas [SQL Server], XML
- XML [SQL Server], schema collections
- XML schema collections [SQL Server]
- schema collections [SQL Server], about XML schema collections
ms.assetid: 659d41aa-ccec-4554-804a-722a96ef25c2
author: rothja
ms.author: jroth
ms.openlocfilehash: 3ee4757f1353278447ee55e97c8d4ba23aa2d649
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619674"
---
# <a name="xml-schema-collections-sql-server"></a><span data-ttu-id="c1fe5-102">XML-Schemaauflistungen (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="c1fe5-102">XML Schema Collections (SQL Server)</span></span>
  <span data-ttu-id="c1fe5-103">Wie im Thema [XML &#40;Transact-SQL&#41;](/sql/t-sql/xml/xml-transact-sql)beschrieben, bietet SQL Server systemeigene Speicherung von XML-Daten durch den- `xml` Datentyp.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-103">As described in the topic, [xml &#40;Transact-SQL&#41;](/sql/t-sql/xml/xml-transact-sql), SQL Server provides native storage of XML data through the `xml` data type.</span></span> <span data-ttu-id="c1fe5-104">Optional können Sie XSD-Schemas einer Variablen oder einer Spalte vom `xml` Typ über eine XML-Schema Auflistung zuordnen.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-104">You can optionally associate XSD schemas with a variable or a column of `xml` type through an XML schema collection.</span></span> <span data-ttu-id="c1fe5-105">Die XML-Schemaauflistung speichert die importierten XML-Schemas und wird dann für folgende Zwecke verwendet:</span><span class="sxs-lookup"><span data-stu-id="c1fe5-105">The XML schema collection stores the imported XML schemas and is then used to do the following:</span></span>  
  
-   <span data-ttu-id="c1fe5-106">Überprüfen von XML-Instanzen</span><span class="sxs-lookup"><span data-stu-id="c1fe5-106">Validate XML instances</span></span>  
  
-   <span data-ttu-id="c1fe5-107">Typisierung der in der Datenbank gespeicherten XML-Daten</span><span class="sxs-lookup"><span data-stu-id="c1fe5-107">Type the XML data as it is stored in the database</span></span>  
  
 <span data-ttu-id="c1fe5-108">Beachten Sie, dass die XML-Schemaauflistung wie eine Tabelle in der Datenbank eine Metadatenentität ist.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-108">Note that the XML schema collection is a metadata entity like a table in the database.</span></span> <span data-ttu-id="c1fe5-109">Sie können sie erstellen, ändern und löschen.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-109">You can create, modify, and drop them.</span></span> <span data-ttu-id="c1fe5-110">In einer [CREATE XML SCHEMA COLLECTION (Transact-SQL)](/sql/t-sql/statements/create-xml-schema-collection-transact-sql) -Anweisung angegebene Schemas werden automatisch in das neu erstellte XML-Schemaauflistungsobjekt importiert.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-110">Schemas specified in a [CREATE XML SCHEMA COLLECTION (Transact-SQL)](/sql/t-sql/statements/create-xml-schema-collection-transact-sql) statement are automatically imported into the newly created XML schema collection object.</span></span> <span data-ttu-id="c1fe5-111">Mit der [ALTER XML SCHEMA COLLECTION (Transact-SQL)](/sql/t-sql/statements/alter-xml-schema-collection-transact-sql) -Anweisung können Sie zusätzliche Schemas oder Schemakomponenten in ein in der Datenbank vorhandenes Auflistungsobjekt importieren.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-111">You can import additional schemas or schema components into an existing collection object in the database by using the [ALTER XML SCHEMA COLLECTION (Transact-SQL)](/sql/t-sql/statements/alter-xml-schema-collection-transact-sql) statement.</span></span>  
  
 <span data-ttu-id="c1fe5-112">Wie im Thema [Vergleichen von typisiertem XML mit nicht typisiertem XML](../xml/compare-typed-xml-to-untyped-xml.md) beschrieben wird, wird der XML-Code, der in einer Spalte oder in einer Variablen mit zugeordnetem Schema gespeichert ist, als **typisiertes** XML bezeichnet, weil das Schema die für die Instanzendaten benötigten Datentypinformationen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-112">As described in the topic, [Typed vs. Untyped XML](../xml/compare-typed-xml-to-untyped-xml.md), the XML stored in a column or variable that a schema is associated with is referred to as **typed** XML, because the schema provides the necessary data type information for the instance data.</span></span> <span data-ttu-id="c1fe5-113">SQL Server verwendet diese Typinformationen für die Optimierung des Datenspeichers.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-113">SQL Server uses this type information to optimize data storage.</span></span>  
  
 <span data-ttu-id="c1fe5-114">Die Abfrageverarbeitungs-Engine verwendet das Schema außerdem zur Typüberprüfung sowie zur Optimierung der Abfragen und zur Datenänderung.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-114">The query-processing engine also uses the schema for type checking and to optimize queries and data modification.</span></span>  
  
 <span data-ttu-id="c1fe5-115">Außerdem verwendet SQL Server die zugeordnete XML-Schema Auflistung im Fall von typisiertem `xml` , um die XML-Instanz zu validieren.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-115">Also, SQL Server uses the associated XML schema collection, in the case of typed `xml`, to validate the XML instance.</span></span> <span data-ttu-id="c1fe5-116">Wenn die XML-Instanz dem Schema entspricht, lässt die Datenbank das Speichern der Instanz und ihrer Typinformation im System zu.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-116">If the XML instance complies with the schema, the database allows the instance to be stored in the system with their type information.</span></span> <span data-ttu-id="c1fe5-117">Anderenfalls wird die Instanz abgelehnt.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-117">Otherwise, it rejects the instance.</span></span>  
  
 <span data-ttu-id="c1fe5-118">Um ein in der Datenbank gespeichertes Schema abzurufen, können Sie die systeminterne Funktion XML_SCHEMA_NAMESPACE verwenden.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-118">You can use the intrinsic function XML_SCHEMA_NAMESPACE to retrieve the schema collection that is stored in the database.</span></span> <span data-ttu-id="c1fe5-119">Weitere Informationen finden Sie unter [Anzeigen einer gespeicherten XML-Schemaauflistung](../xml/view-a-stored-xml-schema-collection.md).</span><span class="sxs-lookup"><span data-stu-id="c1fe5-119">For more information, see [View a Stored XML Schema Collection](../xml/view-a-stored-xml-schema-collection.md).</span></span>  
  
 <span data-ttu-id="c1fe5-120">Die XML-Schemaauflistung können Sie auch verwenden, um XML-Variablen, -Parameter und -Spalten zu typisieren.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-120">You can also use the XML schema collection to type XML variables, parameters, and columns.</span></span>  
  
##  <a name="ddl-for-managing-schema-collections"></a><a name="ddl"></a> <span data-ttu-id="c1fe5-121">DDL zum Verwalten von Schemaauflistungen</span><span class="sxs-lookup"><span data-stu-id="c1fe5-121">DDL for Managing Schema Collections</span></span>  
 <span data-ttu-id="c1fe5-122">Sie können XML-Schemaauflistungen in der Datenbank erstellen und Variablen und Spalten des `xml`-Typs zuordnen.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-122">You can create XML schema collections in the database and associate them with variables and columns of `xml` type.</span></span> <span data-ttu-id="c1fe5-123">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] bietet die folgenden DDL-Anweisungen zum Verwalten von Schemaauflistungen:</span><span class="sxs-lookup"><span data-stu-id="c1fe5-123">To manage schema collections in the database, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides the following DDL statements:</span></span>  
  
-   <span data-ttu-id="c1fe5-124">[CREATE XML SCHEMA COLLECTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-xml-schema-collection-transact-sql) Importiert die Schemakomponenten in eine Datenbank.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-124">[CREATE XML SCHEMA COLLECTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-xml-schema-collection-transact-sql) Imports schema components into a database.</span></span>  
  
-   <span data-ttu-id="c1fe5-125">[ALTER XML SCHEMA COLLECTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-xml-schema-collection-transact-sql) Ändert die Schemakomponenten in einer vorhandenen XML-Schemaauflistung.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-125">[ALTER XML SCHEMA COLLECTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-xml-schema-collection-transact-sql) Modifies the schema components in an existing XML schema collection.</span></span>  
  
-   <span data-ttu-id="c1fe5-126">[DROP XML SCHEMA COLLECTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-xml-schema-collection-transact-sql) Löscht eine gesamte XML-Schemaauflistung und alle zugehörigen Komponenten.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-126">[DROP XML SCHEMA COLLECTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-xml-schema-collection-transact-sql) Deletes a complete XML schema collection and all its components.</span></span>  
  
 <span data-ttu-id="c1fe5-127">Um eine XML-Schemaauflistung und die darin enthaltenen Schemas zu verwenden, müssen Sie zuerst mit der CREATE XML SCHEMA COLLECTION-Anweisung die Auflistung und die Schemas erstellen.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-127">To use an XML schema collection and the schemas it contains, you must first create the collection and the schemas by using the CREATE XML SCHEMA COLLECTION statement.</span></span> <span data-ttu-id="c1fe5-128">Nach dem Erstellen der Schemaauflistung können Sie Variablen und Spalten vom Typ `xml` erstellen und diese der Schemaauflistung zuordnen.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-128">After the schema collection is created, you can then create variables and columns of `xml` type and associate the schema collection with them.</span></span> <span data-ttu-id="c1fe5-129">Beachten Sie, dass nach dem Erstellen der Schemaauflistung verschiedene Schemakomponenten in den Metadaten gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-129">Note that after a schema collection is created, various schema components are stored in the metadata.</span></span> <span data-ttu-id="c1fe5-130">Mit der Anweisung ALTER XML SCHEMA COLLECTION können Sie zu vorhandenen Schemas außerdem weitere Komponenten oder zu vorhandenen Auflistungen neue Schemas hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-130">You can also use the ALTER XML SCHEMA COLLECTION to add more components to the existing schemas or add new schemas to an existing collection.</span></span>  
  
 <span data-ttu-id="c1fe5-131">Zum Löschen der Schemaauflistung verwenden Sie die DROP XML SCHEMA COLLECTION-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-131">To drop the schema collection, use the DROP XML SCHEMA COLLECTION statement.</span></span> <span data-ttu-id="c1fe5-132">Diese Anweisung löscht alle in der Auflistung enthaltenen Schemas und entfernt das Auflistungsobjekt.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-132">This drops all schemas that are contained in the collection and removes the collection object.</span></span> <span data-ttu-id="c1fe5-133">Beachten Sie, dass zum Löschen einer Schemaauflistung zuerst die unter [DROP XML SCHEMA COLLECTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-xml-schema-collection-transact-sql) beschriebenen Bedingungen erfüllt sein müssen.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-133">Note that before you can drop a schema collection, the conditions described in [DROP XML SCHEMA COLLECTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-xml-schema-collection-transact-sql)must be met.</span></span>  
  
##  <a name="understanding-schema-components"></a><a name="components"></a> <span data-ttu-id="c1fe5-134">Grundlegendes zu Schemakomponenten</span><span class="sxs-lookup"><span data-stu-id="c1fe5-134">Understanding Schema Components</span></span>  
 <span data-ttu-id="c1fe5-135">Wenn Sie die CREATE XML SCHEMA COLLECTION-Anweisung verwenden, werden verschiedene Schemakomponenten in die Datenbank importiert.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-135">When you use the CREATE XML SCHEMA COLLECTION statement, various schema components are imported into the database.</span></span> <span data-ttu-id="c1fe5-136">Zu den Schemakomponenten gehören Schemaelemente, -attribute und -typdefinitionen.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-136">Schema components include schema elements, attributes, and type definitions.</span></span> <span data-ttu-id="c1fe5-137">Wenn Sie die DROP XML SCHEMA COLLECTION-Anweisung verwenden, wird die komplette Schemaauflistung entfernt.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-137">When you use the DROP XML SCHEMA COLLECTION statement, you remove the complete collection.</span></span>  
  
 <span data-ttu-id="c1fe5-138">CREATE XML SCHEMA COLLECTION speichert die Schemakomponenten in verschiedenen Systemtabellen.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-138">CREATE XML SCHEMA COLLECTION saves the schema components into various system tables.</span></span>  
  
 <span data-ttu-id="c1fe5-139">Angenommen, das folgende Schema liegt vor:</span><span class="sxs-lookup"><span data-stu-id="c1fe5-139">For example, consider the following schema:</span></span>  
  
```  
<?xml version="1.0"?>  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            targetNamespace="uri:Cust_Orders2"  
            xmlns="uri:Cust_Orders2" >  
  <xsd:attribute name="SomeAttribute" type="xsd:int" />  
  <xsd:complexType name="SomeType" />  
  <xsd:complexType name="OrderType" >  
    <xsd:sequence>  
      <xsd:element name="OrderDate" type="xsd:date" />  
      <xsd:element name="RequiredDate" type="xsd:date" />  
      <xsd:element name="ShippedDate" type="xsd:date" />  
    </xsd:sequence>  
    <xsd:attribute name="OrderID" type="xsd:ID" />  
    <xsd:attribute name="CustomerID"  />  
    <xsd:attribute name="EmployeeID"  />  
  </xsd:complexType>  
  <xsd:complexType name="CustomerType" >  
     <xsd:sequence>  
        <xsd:element name="Order" type="OrderType"  
                     maxOccurs="unbounded" />  
       </xsd:sequence>  
      <xsd:attribute name="CustomerID" type="xsd:string" />  
      <xsd:attribute name="OrderIDList" type="xsd:IDREFS" />  
  </xsd:complexType>  
  <xsd:element name="Customer" type="CustomerType" />  
</xsd:schema>  
```  
  
 <span data-ttu-id="c1fe5-140">Das obige Schema zeigt die verschiedenen Attributtypen von Komponenten, die in der Datenbank gespeichert werden können.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-140">The previous schema shows the different types of components that can be stored in the database.</span></span> <span data-ttu-id="c1fe5-141">Hierzu zählen `SomeAttribute`, `SomeType`, `OrderType`, `CustomerType`, `Customer`, `Order`, `CustomerID`, `OrderID`, `OrderDate`, `RequiredDate`und `ShippedDate`.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-141">These include `SomeAttribute`, `SomeType`, `OrderType`, `CustomerType`, `Customer`, `Order`, `CustomerID`, `OrderID`, `OrderDate`, `RequiredDate`, and `ShippedDate`.</span></span>  
  
### <a name="component-categories"></a><span data-ttu-id="c1fe5-142">Komponentenkategorien</span><span class="sxs-lookup"><span data-stu-id="c1fe5-142">Component Categories</span></span>  
 <span data-ttu-id="c1fe5-143">Die in der Datenbank gespeicherten Schemakomponenten fallen in folgende Kategorien:</span><span class="sxs-lookup"><span data-stu-id="c1fe5-143">The Schema components stored in the database fall into the following categories:</span></span>  
  
-   <span data-ttu-id="c1fe5-144">ELEMENT</span><span class="sxs-lookup"><span data-stu-id="c1fe5-144">ELEMENT</span></span>  
  
-   <span data-ttu-id="c1fe5-145">ATTRIBUTE</span><span class="sxs-lookup"><span data-stu-id="c1fe5-145">ATTRIBUTE</span></span>  
  
-   <span data-ttu-id="c1fe5-146">TYPE (für einfache oder komplexe Typen)</span><span class="sxs-lookup"><span data-stu-id="c1fe5-146">TYPE (for simple or complex types)</span></span>  
  
-   <span data-ttu-id="c1fe5-147">ATTRIBUTEGROUP</span><span class="sxs-lookup"><span data-stu-id="c1fe5-147">ATTRIBUTEGROUP</span></span>  
  
-   <span data-ttu-id="c1fe5-148">MODELGROUP</span><span class="sxs-lookup"><span data-stu-id="c1fe5-148">MODELGROUP</span></span>  
  
 <span data-ttu-id="c1fe5-149">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c1fe5-149">For example:</span></span>  
  
-   <span data-ttu-id="c1fe5-150">**SomeAttribute** ist eine ATTRIBUTE-Komponente.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-150">**SomeAttribute** is an ATTRIBUTE component.</span></span>  
  
-   <span data-ttu-id="c1fe5-151">**SomeType**, **OrderType**und **CustomerType** sind TYPE-Komponenten.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-151">**SomeType**, **OrderType**, and **CustomerType** are TYPE components.</span></span>  
  
-   <span data-ttu-id="c1fe5-152">**Customer** ist eine ELEMENT-Komponente.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-152">**Customer** is an ELEMENT component.</span></span>  
  
 <span data-ttu-id="c1fe5-153">Wenn Sie ein Schema in die Datenbank importieren, wird von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nicht das Schema als solches gespeichert.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-153">When you import a schema into the database, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not store the schema itself.</span></span> <span data-ttu-id="c1fe5-154">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] speichert stattdessen die verschiedenen Einzelkomponenten.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-154">Instead, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stores the various individual components.</span></span> <span data-ttu-id="c1fe5-155">Das \<Schema>-Tag wird demnach nicht gespeichert, es werden nur die darin definierten Komponenten aufbewahrt.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-155">That is, the \<Schema> tag is not stored, only the components that are defined within it are preserved.</span></span> <span data-ttu-id="c1fe5-156">Nicht alle Schemaelemente werden erhalten.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-156">All schema elements are not preserved.</span></span> <span data-ttu-id="c1fe5-157">Wenn das \<Schema>-Tag Attribute enthält, die das Standardverhalten seiner Komponenten definieren, werden diese Attribute während des Importvorgangs in die darin enthaltenen Komponenten verschoben. Die folgende Tabelle stellt dies dar.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-157">If the \<Schema> tag contains attributes that specify default behavior of its components, these attributes are moved to the schema components within it during the import process, as shown in the following table.</span></span>  
  
|<span data-ttu-id="c1fe5-158">Attributname</span><span class="sxs-lookup"><span data-stu-id="c1fe5-158">Attribute name</span></span>|<span data-ttu-id="c1fe5-159">Verhalten</span><span class="sxs-lookup"><span data-stu-id="c1fe5-159">Behavior</span></span>|  
|--------------------|--------------|  
|<span data-ttu-id="c1fe5-160">**attributeFormDefault**</span><span class="sxs-lookup"><span data-stu-id="c1fe5-160">**attributeFormDefault**</span></span>|<span data-ttu-id="c1fe5-161">Das **form** -Attribut, das für alle im Schema enthaltenen Attributdeklarationen angewendet wird, die dieses Attribut noch nicht enthalten. Der Wert wird auf den Wert des **attributeFormDefault** -Attributs festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-161">The **form** attribute applied to all attribute declarations in the schema where it is not already present and the value is set to the value of the **attributeFormDefault** attribute.</span></span>|  
|<span data-ttu-id="c1fe5-162">**elementFormDefault**</span><span class="sxs-lookup"><span data-stu-id="c1fe5-162">**elementFormDefault**</span></span>|<span data-ttu-id="c1fe5-163">Das **form** -Attribut, das für alle im Schema enthaltenen Elementdeklarationen angewendet wird, die dieses Attribut noch nicht enthalten. Der Wert wird auf den Wert des **elementFormDefault** -Attributs festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-163">The **form** attribute applied to all element declarations in the schema where it is not already present and the value is set to the value of the **elementFormDefault** attribute.</span></span>|  
|<span data-ttu-id="c1fe5-164">**blockDefault**</span><span class="sxs-lookup"><span data-stu-id="c1fe5-164">**blockDefault**</span></span>|<span data-ttu-id="c1fe5-165">Das **block** -Attribut, das für alle Elementdeklarationen und Typdefinitionen angewendet wird, die dieses Attribut noch nicht enthalten. Der Wert wird auf den Wert des **blockDefault** -Attributs festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-165">The **block** attribute applied to all element declarations and type definitions where it is not already present and the value is set to the value of the **blockDefault** attribute.</span></span>|  
|<span data-ttu-id="c1fe5-166">**finalDefault**</span><span class="sxs-lookup"><span data-stu-id="c1fe5-166">**finalDefault**</span></span>|<span data-ttu-id="c1fe5-167">Das **final** -Attribut, das für alle Elementdeklarationen und Typdefinitionen angewendet wird, die dieses Attribut noch nicht enthalten. Der Wert wird auf den Wert des **finalDefault** -Attributs festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-167">The **final** attribute applied to all element declarations and type definitions where it is not already present and the value is set to the value of the **finalDefault** attribute.</span></span>|  
|<span data-ttu-id="c1fe5-168">**targetNamespace**</span><span class="sxs-lookup"><span data-stu-id="c1fe5-168">**targetNamespace**</span></span>|<span data-ttu-id="c1fe5-169">Zum Zielnamespace gehörende Informationen zu den Komponenten werden in den Metadaten gespeichert.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-169">Information about the components that belong to the target namespace is stored in the metadata.</span></span>|  
  
##  <a name="permissions-on-an-xml-schema-collection"></a><a name="perms"></a> <span data-ttu-id="c1fe5-170">Berechtigungen für eine XML-Schemaauflistung</span><span class="sxs-lookup"><span data-stu-id="c1fe5-170">Permissions on an XML Schema Collection</span></span>  
 <span data-ttu-id="c1fe5-171">Sie müssen über die entsprechenden Berechtigungen verfügen, um die folgenden Aufgaben durchführen zu können:</span><span class="sxs-lookup"><span data-stu-id="c1fe5-171">You must have the necessary permissions to do the following:</span></span>  
  
-   <span data-ttu-id="c1fe5-172">Erstellen/Laden der XML-Schemaauflistung</span><span class="sxs-lookup"><span data-stu-id="c1fe5-172">Create/load the XML schema collection</span></span>  
  
-   <span data-ttu-id="c1fe5-173">Ändern der XML-Schemaauflistung</span><span class="sxs-lookup"><span data-stu-id="c1fe5-173">Modify the XML schema collection</span></span>  
  
-   <span data-ttu-id="c1fe5-174">Löschen der XML-Schemaauflistung</span><span class="sxs-lookup"><span data-stu-id="c1fe5-174">Drop the XML schema collection</span></span>  
  
-   <span data-ttu-id="c1fe5-175">Verwenden Sie die XML-Schema Auflistung, um `xml` Typspalten, Variablen und Parameter einzugeben, oder verwenden Sie Sie in Tabellen-oder Spalten Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-175">Use the XML schema collection to type `xml` type columns, variables, and parameters, or use it in table or column constraints</span></span>  
  
 <span data-ttu-id="c1fe5-176">Das SQL Server-Sicherheitsmodell lässt die CONTROL-Berechtigung für jedes Objekt zu.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-176">The SQL Server security model allows CONTROL permission on every object.</span></span> <span data-ttu-id="c1fe5-177">Der Empfänger dieser Berechtigung erhält alle anderen Berechtigungen für das Objekt.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-177">The grantee of this permission obtains all other permissions on the object.</span></span> <span data-ttu-id="c1fe5-178">Der Besitzer des Objekts verfügt ebenfalls über alle Berechtigungen für das Objekt.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-178">The owner of the object also has all the permissions on the object.</span></span>  
  
 <span data-ttu-id="c1fe5-179">Der Besitzer und der Empfänger der CONTROL-Berechtigung für ein Objekt können beliebige Berechtigungen für das Objekt erteilen.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-179">The owner and the grantee of the CONTROL permission on an object can grant any permission on the object.</span></span> <span data-ttu-id="c1fe5-180">Ein Benutzer, der nicht der Besitzer ist und keine CONTROL-Berechtigung besitzt, kann dennoch Berechtigungen für ein Objekt erteilen, wenn WITH GRANT OPTION angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-180">A user who is not the owner and does not have CONTROL permission can still grant permission on an object when WITH GRANT OPTION is specified.</span></span> <span data-ttu-id="c1fe5-181">Angenommen, Benutzer A verfügt über WITH GRANT OPTION z. B. über REFERENCES-Berechtigung für eine XML-Schemaauflistung S, besitzt jedoch keine weiteren Berechtigungen für S. Benutzer A kann Benutzer B die REFERENCES-Berechtigung für Schemaauflistung S erteilen.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-181">For example, assume User A has REFERENCES permission on XML schema collection S, through WITH GRANT OPTION, but no other permissions on S. User A could grant User B REFERENCES permission on schema collection S.</span></span>  
  
 <span data-ttu-id="c1fe5-182">Das Sicherheitsmodell ermöglicht außerdem Berechtigungen zum Erstellen oder Verwenden von XML-Schemaauflistungen oder zum Übertragen des Besitzes von einem auf einen anderen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-182">The security model also allows permissions to create and use XML schema collections or transfer ownership from one user to another.</span></span> <span data-ttu-id="c1fe5-183">In den folgenden Themen werden die Berechtigungen für XML-Schemaauflistungen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-183">The following topics describe the XML schema collection permissions.</span></span>  
  
-   [<span data-ttu-id="c1fe5-184">Erteilen von Berechtigungen für eine XML-Schemaauflistung</span><span class="sxs-lookup"><span data-stu-id="c1fe5-184">Grant Permissions on an XML Schema Collection</span></span>](../xml/grant-permissions-on-an-xml-schema-collection.md)  
  
     <span data-ttu-id="c1fe5-185">Dieses Thema erläutert das Erteilen von Berechtigungen zum Erstellen von XML-Schemaauflistungen sowie das Erteilen von Berechtigungen für ein XML-Schemaauflistungsobjekt.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-185">This topic discussess how to grant permissions to create an XML schema collection and how to grant permissions on an XML schema collection object.</span></span>  
  
-   [<span data-ttu-id="c1fe5-186">Aufheben der Berechtigungen für eine XML-Schemaauflistung</span><span class="sxs-lookup"><span data-stu-id="c1fe5-186">Revoke Permissions on an XML Schema Collection</span></span>](../xml/revoke-permissions-on-an-xml-schema-collection.md)  
  
     <span data-ttu-id="c1fe5-187">Dieses Thema erläutert das Aufheben von Berechtigungen zum Verhindern der Erstellung einer XML-Schemaauflistung sowie das Aufheben von Berechtigungen für ein XML-Schemaauflistungsobjekt.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-187">This topic discusses how revoking permissions can be used to prevent the creation of an XML schema collection and how to revoke permissions on an XML schema collection object.</span></span>  
  
-   [<span data-ttu-id="c1fe5-188">Verweigern von Berechtigungen für eine XML-Schemaauflistung</span><span class="sxs-lookup"><span data-stu-id="c1fe5-188">Deny Permissions on an XML Schema Collection</span></span>](../xml/deny-permissions-on-an-xml-schema-collection.md)  
  
     <span data-ttu-id="c1fe5-189">Dieses Thema erläutert das Verweigern von Berechtigungen zum Erstellen einer XML-Schemaauflistung sowie das Verweigern von Berechtigungen für ein XML-Schemaauflistungsobjekt.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-189">This topic discusses how to deny permissions to create an XML schema collection and deny permission on an XML schema collection object.</span></span>  
  
##  <a name="getting-information-about-xml-schemas-and-schema-collections"></a><a name="info"></a> <span data-ttu-id="c1fe5-190">Abrufen von Informationen zu XML-Schemas und -Schemaauflistungen</span><span class="sxs-lookup"><span data-stu-id="c1fe5-190">Getting Information about XML Schemas and Schema Collections</span></span>  
 <span data-ttu-id="c1fe5-191">XML-Schemaauflistungen sind in der Katalogsicht sys.xml_schema_collections aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-191">XML schema collections are enumerated in the catalog view, sys.xml_schema_collections.</span></span> <span data-ttu-id="c1fe5-192">Die XML-Schemaauflistung "sys" wird durch das System definiert.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-192">The XML schema collection "sys" is defined by the system.</span></span> <span data-ttu-id="c1fe5-193">Sie enthält die vordefinierten Namespaces, die in allen benutzerdefinierten XML-Schemaauflistungen verwendet werden können, ohne dass sie explizit geladen werden müssen.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-193">It contains the predefined namespaces that can be used in all user-defined XML schema collections without having to load them explicitly.</span></span> <span data-ttu-id="c1fe5-194">Diese Auflistung enthält die Namespaces für xml, xs, xsi, fn und xdt.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-194">This list contains the namespaces for xml, xs, xsi, fn, and xdt.</span></span> <span data-ttu-id="c1fe5-195">Zwei weitere Katalogsichten sind sys.xml_schema_namespaces, die alle Namespaces innerhalb jeder Schemaauflistung aufführt, und sys.xml_components, die alle XML-Schemakomponenten innerhalb jedes XML-Schemas aufführt.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-195">Two other catalog views are sys.xml_schema_namespaces, which enumerates all namespaces within each XML schema collection, and sys.xml_components, which enumerates all XML schema components within each XML schema.</span></span>  
  
 <span data-ttu-id="c1fe5-196">Die integrierte Funktion **XML_SCHEMA_NAMESPACE**, Schema *Name, XmlSchemaCollectionName, Namespace-URI*, ergibt eine Instanz des- `xml` Datentyps.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-196">The built-in function **XML_SCHEMA_NAMESPACE**, *schemaName, XmlSchemacollectionName, namespace-uri*, yields an `xml` data type instance..</span></span> <span data-ttu-id="c1fe5-197">Diese Instanz enthält XML-Schemafragmente für Schemas, die in einer XML-Schemaauflistung enthalten sind, mit Ausnahme der vordefinierten XML-Schemas.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-197">This instance contains XML schema fragments for schemas that are contained in an XML schema collection, except the predefined XML schemas.</span></span>  
  
 <span data-ttu-id="c1fe5-198">Es gibt folgende Möglichkeiten, um den Inhalt einer XML-Schemaauflistung aufzuführen:</span><span class="sxs-lookup"><span data-stu-id="c1fe5-198">You can enumerate the contents of an XML schema collection in the following ways:</span></span>  
  
-   <span data-ttu-id="c1fe5-199">Schreiben Sie Transact-SQL-Abfragen zur jeweiligen Katalogsicht für XML-Schemaauflistungen.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-199">Write Transact-SQL queries on the appropriate catalog views for XML schema collections.</span></span>  
  
-   <span data-ttu-id="c1fe5-200">Verwenden Sie die integrierte Funktion **XML_SCHEMA_NAMESPACE()** .</span><span class="sxs-lookup"><span data-stu-id="c1fe5-200">Use the built-in function **XML_SCHEMA_NAMESPACE()**.</span></span> <span data-ttu-id="c1fe5-201">Sie können `xml` Datentyp Methoden auf die Ausgabe dieser Funktion anwenden.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-201">You can apply `xml` data type methods on the output of this function.</span></span> <span data-ttu-id="c1fe5-202">Allerdings können Sie dabei die zugrunde liegenden XML-Schemas nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-202">However, you cannot modify the underlying XML schemas.</span></span>  
  
 <span data-ttu-id="c1fe5-203">Diese Möglichkeiten werden in den folgenden Beispielen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-203">These are illustrated in the following examples.</span></span>  
  
### <a name="example-enumerate-the-xml-namespaces-in-an-xml-schema-collection"></a><span data-ttu-id="c1fe5-204">Beispiel: Enumeration der XML-Namespaces in einer XML-Schemaauflistung</span><span class="sxs-lookup"><span data-stu-id="c1fe5-204">Example: Enumerate the XML Namespaces in an XML Schema Collection</span></span>  
 <span data-ttu-id="c1fe5-205">Verwenden Sie die folgende Abfrage für die XML-Schemaauflistung "myCollection":</span><span class="sxs-lookup"><span data-stu-id="c1fe5-205">Use the following query for the XML schema collection "myCollection":</span></span>  
  
```  
SELECT XSN.name  
FROM    sys.xml_schema_collections XSC JOIN sys.xml_schema_namespaces XSN  
    ON (XSC.xml_collection_id = XSN.xml_collection_id)  
WHERE    XSC.name = 'myCollection'     
```  
  
### <a name="example-enumerate-the-contents-of-an-xml-schema-collection"></a><span data-ttu-id="c1fe5-206">Beispiel: Enumeration des Inhalts einer XML-Schemaauflistung</span><span class="sxs-lookup"><span data-stu-id="c1fe5-206">Example: Enumerate the Contents of an XML Schema Collection</span></span>  
 <span data-ttu-id="c1fe5-207">Mit der folgenden Anweisung wird der Inhalt der XML-Schemaauflistung "myCollection" innerhalb des relationalen Schemas dbo aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-207">The following statement enumerates the contents of the XML schema collection "myCollection" within the relational schema, dbo.</span></span>  
  
```  
SELECT XML_SCHEMA_NAMESPACE (N'dbo', N'myCollection')  
```  
  
 <span data-ttu-id="c1fe5-208">Einzelne XML-Schemas innerhalb der Auflistung können als `xml` Datentyp Instanzen abgerufen werden, indem der Ziel Namespace als drittes Argument für **XML_SCHEMA_NAMESPACE ()** angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-208">Individual XML schemas within the collection can be obtained as `xml` data type instances by specifying the target namespace as the third argument to **XML_SCHEMA_NAMESPACE()**.</span></span> <span data-ttu-id="c1fe5-209">Dies wird im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-209">This is shown in the following example.</span></span>  
  
### <a name="example-output-a-specified-schema-from-an-xml-schema-collection"></a><span data-ttu-id="c1fe5-210">Beispiel: Ausgeben eines angegebenen Schemas für eine XML-Schemaauflistung</span><span class="sxs-lookup"><span data-stu-id="c1fe5-210">Example: Output a Specified Schema from an XML Schema Collection</span></span>  
 <span data-ttu-id="c1fe5-211">Mit der folgenden Anweisung wird das XML-Schema mit dem Zielnamespace <https://www.microsoft.com/books> aus der XML-Schemaauflistung „myCollection“ innerhalb des relationalen Schemas „dbo“ ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-211">The following statement outputs the XML schema with the target namespace "<https://www.microsoft.com/books>" from the XML schema collection "myCollection" within the relational schema, dbo.</span></span>  
  
```  
SELECT XML_SCHEMA_NAMESPACE (N'dbo', N'myCollection',   
N'https://www.microsoft.com/books')  
```  
  
### <a name="querying-xml-schemas"></a><span data-ttu-id="c1fe5-212">Abfragen von XML-Schemas</span><span class="sxs-lookup"><span data-stu-id="c1fe5-212">Querying XML Schemas</span></span>  
 <span data-ttu-id="c1fe5-213">Es gibt folgende Möglichkeiten, um XML-Schemas, die Sie in XML-Schemaauflistungen geladen haben, abzufragen:</span><span class="sxs-lookup"><span data-stu-id="c1fe5-213">You can query XML schemas that you have loaded into XML schema collections in the following ways:</span></span>  
  
-   <span data-ttu-id="c1fe5-214">Schreiben Sie Transact-SQL-Abfragen zu Katalogsichten für XML-Schemaauflistungen.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-214">Write Transact-SQL queries on catalog views for XML schema namespaces.</span></span>  
  
-   <span data-ttu-id="c1fe5-215">Erstellen Sie eine Tabelle, die eine `xml`-Datentypspalte enthält, um die XML-Schemas zu speichern, und laden Sie diese auch in das XML-Typsystem.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-215">Create a table that contains an `xml` data type column to store your XML schemas and also load them into the XML type system.</span></span> <span data-ttu-id="c1fe5-216">Sie können dann diese XML-Spalte abfragen, indem Sie `xml`-Datentypmethoden verwenden.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-216">You can query the XML column by using the `xml` data type methods.</span></span> <span data-ttu-id="c1fe5-217">Für diese Spalte können Sie auch einen XML-Index erstellen.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-217">Also, you can build an XML index on this column.</span></span> <span data-ttu-id="c1fe5-218">Allerdings muss die Anwendung für diese Vorgehensweise die Konsistenz zwischen den in der XML-Spalte gespeicherten XML-Schemas und dem XML-Typsystem beibehalten.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-218">However, with this approach, the application must maintain consistency between the XML schemas stored in the XML column and the XML type system.</span></span> <span data-ttu-id="c1fe5-219">Wenn Sie z. B. den XML-Schemanamespace aus dem XML-Typsystem löschen, müssen Sie ihn auch aus der Tabelle löschen, damit die Konsistenz beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="c1fe5-219">For example, if you drop the XML schema namespace from the XML type system, you also have to drop it from the table in order to preserve consistency.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1fe5-220">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c1fe5-220">See Also</span></span>  
 <span data-ttu-id="c1fe5-221">[Anzeigen einer gespeicherten XML-Schemaauflistung](../xml/view-a-stored-xml-schema-collection.md) </span><span class="sxs-lookup"><span data-stu-id="c1fe5-221">[View a Stored XML Schema Collection](../xml/view-a-stored-xml-schema-collection.md) </span></span>  
 <span data-ttu-id="c1fe5-222">[Vorverarbeiten eines Schemas zum Zusammenführen eingeschlossener Schemas](../xml/preprocess-a-schema-to-merge-included-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="c1fe5-222">[Preprocess a Schema to Merge Included Schemas](../xml/preprocess-a-schema-to-merge-included-schemas.md) </span></span>  
 [<span data-ttu-id="c1fe5-223">Anforderungen und Einschränkungen für XML-Schemaauflistungen auf dem Server</span><span class="sxs-lookup"><span data-stu-id="c1fe5-223">Requirements and Limitations for XML Schema Collections on the Server</span></span>](../xml/requirements-and-limitations-for-xml-schema-collections-on-the-server.md)  
  
  
