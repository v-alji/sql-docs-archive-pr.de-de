---
title: Verweigern von Berechtigungen für eine XML-Schemaauflistung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- denying permissions [SQL Server], XML server collections
ms.assetid: e2b300b0-e734-4c43-a4da-c78e6e5d4fba
author: rothja
ms.author: jroth
ms.openlocfilehash: 0791a9bd9c7f6b323886a38bed27bea84940770d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608433"
---
# <a name="deny-permissions-on-an-xml-schema-collection"></a><span data-ttu-id="cfaa2-102">Verweigern von Berechtigungen für eine XML-Schemaauflistung</span><span class="sxs-lookup"><span data-stu-id="cfaa2-102">Deny Permissions on an XML Schema Collection</span></span>
  <span data-ttu-id="cfaa2-103">Die Berechtigung zum Erstellen einer neuen XML-Schemaauflistung bzw. zum Verwenden einer vorhandenen Schemaauflistung kann verweigert werden.</span><span class="sxs-lookup"><span data-stu-id="cfaa2-103">Permission can be denied to either create a new XML schema collection or use an existing one.</span></span>  
  
## <a name="denying-permission-to-create-an-xml-schema-collection"></a><span data-ttu-id="cfaa2-104">Verweigern der Berechtigung zum Erstellen einer XML-Schemaauflistung</span><span class="sxs-lookup"><span data-stu-id="cfaa2-104">Denying Permission to Create an XML Schema Collection</span></span>  
 <span data-ttu-id="cfaa2-105">Es gibt folgende Möglichkeiten, um die Berechtigung zum Erstellen einer XML-Schemaauflistung zu verweigern:</span><span class="sxs-lookup"><span data-stu-id="cfaa2-105">You can deny permission to create an XML schema collection in the following ways:</span></span>  
  
-   <span data-ttu-id="cfaa2-106">Verweigern der ALTER-Berechtigung für das relationale Schema.</span><span class="sxs-lookup"><span data-stu-id="cfaa2-106">Deny ALTER permission on the relational schema.</span></span>  
  
-   <span data-ttu-id="cfaa2-107">Verweigern der CONTROL-Berechtigung für das relationale Schema, um alle Berechtigungen für das relationale Schema und alle darin enthaltenen Objekte zu verweigern.</span><span class="sxs-lookup"><span data-stu-id="cfaa2-107">Deny CONTROL on the relational schema to deny all permissions on the relational schema and on all the contained objects.</span></span>  
  
-   <span data-ttu-id="cfaa2-108">Verweigern der ALTER ANY SCHEMA-Berechtigung für die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="cfaa2-108">Deny ALTER ANY SCHEMA on the database.</span></span> <span data-ttu-id="cfaa2-109">In diesem Fall kann der Prinzipal keine XML-Schemaauflistung in der gesamten Datenbank erstellen.</span><span class="sxs-lookup"><span data-stu-id="cfaa2-109">In this case, the principal cannot create an XML schema collection anywhere in the database.</span></span> <span data-ttu-id="cfaa2-110">Beachten Sie, dass das Verweigern der ALTER- oder CONTROL-Berechtigung für die Datenbank alle Berechtigungen für alle Objekte in der Datenbank verweigert.</span><span class="sxs-lookup"><span data-stu-id="cfaa2-110">Note also that denying ALTER or CONTROL permission on the database denies all permissions on all objects in the database.</span></span>  
  
## <a name="denying-permissions-on-an-xml-schema-collection-object"></a><span data-ttu-id="cfaa2-111">Verweigern von Berechtigungen für ein XML-Schemaauflistungsobjekt</span><span class="sxs-lookup"><span data-stu-id="cfaa2-111">Denying Permissions on an XML Schema Collection Object</span></span>  
 <span data-ttu-id="cfaa2-112">Die folgenden Berechtigungen können mit den aufgeführten Ergebnissen für eine vorhandene XML-Schemaauflistung verweigert werden:</span><span class="sxs-lookup"><span data-stu-id="cfaa2-112">Following are the permission that can be denied on an existing XML schema collection and the results:</span></span>  
  
-   <span data-ttu-id="cfaa2-113">Durch das Verweigern der ALTER-Berechtigung wird einem Prinzipal die Fähigkeit zum Ändern des Inhalts der XML-Schemaauflistung abgesprochen.</span><span class="sxs-lookup"><span data-stu-id="cfaa2-113">Denying the ALTER permission denies the principal the ability to modify the contents of the XML schema collection.</span></span>  
  
-   <span data-ttu-id="cfaa2-114">Durch das Verweigern der CONTROL-Berechtigung wird einem Prinzipal die Fähigkeit zum Ausführen beliebiger Vorgänge mit der XML-Schemaauflistung abgesprochen.</span><span class="sxs-lookup"><span data-stu-id="cfaa2-114">Denying the CONTROL permission denies the principal the ability to perform any operation on the XML schema collection.</span></span>  
  
-   <span data-ttu-id="cfaa2-115">Durch das Verweigern der REFERENCES-Berechtigung wird einem Prinzipal die Fähigkeit zum Typisieren oder Einschränken von Spalten und Parametern vom Typ xml mithilfe der XML-Schemaauflistung abgesprochen.</span><span class="sxs-lookup"><span data-stu-id="cfaa2-115">Denying the REFERENCES permission denies the principal the ability to type or constrain xml type columns and parameters using the XML schema collection.</span></span> <span data-ttu-id="cfaa2-116">Außerdem wird dem Prinzipal die Möglichkeit zum Verweisen auf diese XML-Schemaauflistung aus anderen XML-Schemaauflistungen verweigert.</span><span class="sxs-lookup"><span data-stu-id="cfaa2-116">It also denies the principal the ability to refer to this XML schema collection from other XML schema collections.</span></span>  
  
-   <span data-ttu-id="cfaa2-117">Durch das Verweigern der VIEW DEFINITION-Berechtigung wird einem Prinzipal die Fähigkeit zum Anzeigen des Inhalts einer XML-Schemaauflistung abgesprochen.</span><span class="sxs-lookup"><span data-stu-id="cfaa2-117">Denying the VIEW DEFINITION permission denies the principal the ability to view the contents of an XML schema collection.</span></span>  
  
-   <span data-ttu-id="cfaa2-118">Durch das Verweigern der EXECUTE-Berechtigung wird dem Prinzipal die Fähigkeit zum Einfügen oder Aktualisieren von Werten in Spalten, Variablen und Parametern abgesprochen, die durch die XML-Auflistung typisiert oder eingeschränkt werden.</span><span class="sxs-lookup"><span data-stu-id="cfaa2-118">Denying the EXECUTE permission denies the principal the ability to insert or update the values in columns, variables, and parameters that are typed or constrained by the XML schema collection.</span></span> <span data-ttu-id="cfaa2-119">Außerdem wird dem Prinzipal die Möglichkeit zum Abfragen der Werte in diesen Spalten und Variablen vom Typ xml abgesprochen.</span><span class="sxs-lookup"><span data-stu-id="cfaa2-119">It also denies the principal the ability to query the values in those same xml type columns and variables.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="cfaa2-120">Beispiele</span><span class="sxs-lookup"><span data-stu-id="cfaa2-120">Examples</span></span>  
 <span data-ttu-id="cfaa2-121">Die Szenarien in den folgenden Beispielen veranschaulichen, wie XML-Schemaberechtigungen funktionieren.</span><span class="sxs-lookup"><span data-stu-id="cfaa2-121">The scenarios in the following examples show how XML schema permissions work.</span></span> <span data-ttu-id="cfaa2-122">Jedes dieser Beispiele erstellt die erforderliche Testdatenbank, die relationalen Schemas und Anmeldungen.</span><span class="sxs-lookup"><span data-stu-id="cfaa2-122">Each example creates the necessary test database, relational schemas, and logins.</span></span> <span data-ttu-id="cfaa2-123">Diesen Anmeldenamen werden die erforderlichen Berechtigungen für XML-Schemaauflistungen erteilt.</span><span class="sxs-lookup"><span data-stu-id="cfaa2-123">These logins are granted the necessary XML schema collection permissions.</span></span> <span data-ttu-id="cfaa2-124">Jedes der Beispiele führt am Ende den erforderlichen Cleanup aus.</span><span class="sxs-lookup"><span data-stu-id="cfaa2-124">Each example does the necessary cleanup at the end.</span></span>  
  
### <a name="a-preventing-a-user-from-creating-an-xml-schema-collection"></a><span data-ttu-id="cfaa2-125">A.</span><span class="sxs-lookup"><span data-stu-id="cfaa2-125">A.</span></span> <span data-ttu-id="cfaa2-126">Verhindern, dass ein Benutzer eine XML-Schemaauflistung erstellen kann</span><span class="sxs-lookup"><span data-stu-id="cfaa2-126">Preventing a user from creating an XML schema collection</span></span>  
 <span data-ttu-id="cfaa2-127">Wenn Sie verhindern möchten, dass ein Benutzer eine XML-Schemaauflistung erstellen kann, können Sie z. B. die ALTER-Berechtigung für ein relationales Schema verweigern.</span><span class="sxs-lookup"><span data-stu-id="cfaa2-127">One of the ways to prevent a user from creating an XML schema collection is by denying the ALTER permission on a relational schema.</span></span> <span data-ttu-id="cfaa2-128">Dies wird im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="cfaa2-128">This is shown in the following example.</span></span>  
  
 <span data-ttu-id="cfaa2-129">Dieses Beispiel erstellt einen Benutzer, `TestLogin1`, und eine Datenbank.</span><span class="sxs-lookup"><span data-stu-id="cfaa2-129">The example creates a user, `TestLogin1`, and a database.</span></span> <span data-ttu-id="cfaa2-130">Außerdem wird neben dem `dbo` -Schema ein relationales Schema in der Datenbank erstellt.</span><span class="sxs-lookup"><span data-stu-id="cfaa2-130">It also creates a relational schema, in addition to the `dbo` schema, in the database.</span></span> <span data-ttu-id="cfaa2-131">Anfangs ermöglicht die `CREATE XML SCHEMA` -Berechtigung dem Benutzer das Erstellen einer Schemaauflistung in der gesamten Datenbank.</span><span class="sxs-lookup"><span data-stu-id="cfaa2-131">Initially, the `CREATE XML SCHEMA` permission allows the user to create a schema collection anywhere in the database.</span></span> <span data-ttu-id="cfaa2-132">Das Beispiel verweigert dann die `ALTER` -Berechtigung für den Benutzer für eines der relationalen Schemas.</span><span class="sxs-lookup"><span data-stu-id="cfaa2-132">The example then denies `ALTER` permission to the user on one of the relational schemas.</span></span> <span data-ttu-id="cfaa2-133">Dies verhindert, dass der Benutzer eine XML-Schemaauflistung in diesem relationalen Schema erstellen kann.</span><span class="sxs-lookup"><span data-stu-id="cfaa2-133">This prevents the user from creating an XML schema collection in that relational schema.</span></span>  
  
```  
CREATE LOGIN TestLogin1 WITH password='SQLSvrPwd1'  
GO  
CREATE DATABASE SampleDBForSchemaPermissions  
GO  
USE SampleDBForSchemaPermissions  
GO  
-- Create another relational schema in the database.  
CREATE SCHEMA myOtherDBSchema  
GO  
CREATE USER TestLogin1  
GO  
-- For TestLogin1 to create/import XML schema collection, following  
-- permission needed.  
-- Database-level permissions  
GRANT CREATE XML SCHEMA COLLECTION TO TestLogin1  
GO  
GRANT ALTER ANY SCHEMA TO TestLogin1  
GO  
-- Now TestLogin1 can import an XML schema collection.  
SETUSER 'TestLogin1'  
GO  
CREATE XML SCHEMA COLLECTION myOtherDBSchema.myTestSchemaCollection AS '<?xml version="1.0" encoding="UTF-8" ?>  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
elementFormDefault="qualified">  
<xsd:element name="telephone" type="xsd:string" />  
</xsd:schema>'  
GO  
DROP XML SCHEMA COLLECTION myOtherDBSchema.myTestSchemaCollection  
GO  
-- Now deny permission from TestLogin1 to alter myOtherDBSchema.  
setuser  
GO  
DENY ALTER ON SCHEMA::myOtherDBSchema TO TestLogin1  
GO  
-- Now TestLogin1 cannot create xml schema collection.  
SETUSER 'TestLogin1'  
GO  
CREATE XML SCHEMA COLLECTION myOtherDBSchema.myTestSchemaCollection AS '<?xml version="1.0" encoding="UTF-8" ?>  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
elementFormDefault="qualified">  
<xsd:element name="telephone" type="xsd:string" />  
</xsd:schema>'  
GO  
-- Final cleanup  
SETUSER  
GO  
USE master  
GO  
DROP DATABASE SampleDBForSchemaPermissions  
GO  
DROP LOGIN TestLogin1  
GO  
```  
  
### <a name="b-denying-permissions-on-an-xml-schema-collection"></a><span data-ttu-id="cfaa2-134">B.</span><span class="sxs-lookup"><span data-stu-id="cfaa2-134">B.</span></span> <span data-ttu-id="cfaa2-135">Verweigern von Berechtigungen für eine XML-Schemaauflistung</span><span class="sxs-lookup"><span data-stu-id="cfaa2-135">Denying permissions on an XML schema collection</span></span>  
 <span data-ttu-id="cfaa2-136">Das folgende Beispiel zeigt, wie einem Anmeldenamen eine bestimmte Berechtigung für eine vorhandene XML-Schemaauflistung verweigert werden kann.</span><span class="sxs-lookup"><span data-stu-id="cfaa2-136">The following example shows how a specific permission on an existing XML schema collection can be denied to a login.</span></span> <span data-ttu-id="cfaa2-137">In diesem Beispiel wird einem Testanmeldenamen die REFERENCES-Berechtigung für eine vorhandene XML-Schemaauflistung verweigert.</span><span class="sxs-lookup"><span data-stu-id="cfaa2-137">In this example, a test login is denied REFERENCES permission on an existing XML schema collection.</span></span>  
  
 <span data-ttu-id="cfaa2-138">Dieses Beispiel erstellt einen Benutzer, `TestLogin1`, und eine Datenbank.</span><span class="sxs-lookup"><span data-stu-id="cfaa2-138">The example creates a user, `TestLogin1`, and a database.</span></span> <span data-ttu-id="cfaa2-139">Außerdem wird neben dem `dbo` -Schema ein relationales Schema in der Datenbank erstellt.</span><span class="sxs-lookup"><span data-stu-id="cfaa2-139">It also creates a relational schema, in addition to the `dbo` schema, in the database.</span></span> <span data-ttu-id="cfaa2-140">Anfangs ermöglicht die `CREATE XML SCHEMA` -Berechtigung dem Benutzer das Erstellen einer Schemaauflistung in der gesamten Datenbank.</span><span class="sxs-lookup"><span data-stu-id="cfaa2-140">Initially, the `CREATE XML SCHEMA` permission allows the user to create a schema collection anywhere in the database.</span></span>  
  
 <span data-ttu-id="cfaa2-141">Durch die `REFERENCES` -Berechtigung für die XML-Schemaauflistung kann `TestLogin1` das Schema beim Erstellen einer typisierten `xml` -Spalte in einer Tabelle verwenden.</span><span class="sxs-lookup"><span data-stu-id="cfaa2-141">The `REFERENCES` permission on the XML schema collection lets `TestLogin1` use the schema in creating a typed `xml` column in a table.</span></span> <span data-ttu-id="cfaa2-142">Wenn die `REFERENCES` -Berechtigung für die XML-Schemaauflistung verweigert wird, kann `TestLogin1` die XML-Schemaauflistung nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="cfaa2-142">If the `REFERENCES` permission on the XML schema collection is denied, it prevents the `TestLogin1` from using the XML schema collection.</span></span>  
  
```  
CREATE LOGIN TestLogin1 WITH password='SQLSvrPwd1'  
GO  
CREATE DATABASE SampleDBForSchemaPermissions  
GO  
USE SampleDBForSchemaPermissions  
GO  
-- Create another relational schema in the database.  
CREATE SCHEMA myOtherDBSchema  
GO  
CREATE USER TestLogin1  
GO  
-- For TestLogin1 to create/import XML schema collection, the following  
-- permission is required.  
-- Database-level permissions  
GRANT CREATE XML SCHEMA COLLECTION TO TestLogin1  
GO  
GRANT ALTER ANY SCHEMA TO TestLogin1  
GO  
-- Now TestLogin1 can import an XML schema collection.  
SETUSER 'TestLogin1'  
GO  
CREATE XML SCHEMA COLLECTION myOtherDBSchema.myTestSchemaCollection AS '<?xml version="1.0" encoding="UTF-8" ?>  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
elementFormDefault="qualified">  
<xsd:element name="telephone" type="xsd:string" />  
</xsd:schema>'  
GO  
-- Grant permission to TestLogin1 to create a table and reference the XML schema collection.  
SETUSER  
GO  
GRANT CREATE TABLE TO TestLogin1  
GO  
-- The user also needs REFERENCES permission to use the XML schema collection  
-- to create a typed XML column (REFERENCES permission on the schema   
-- collection is not needed).  
GRANT REFERENCES ON XML SCHEMA COLLECTION::myOtherDBSchema.myTestSchemaCollection   
TO TestLogin1  
GO  
  
--TestLogin1 can use the schema.  
CREATE TABLE T(i int, x xml (myOtherDBSchema.myTestSchemaCollection))  
GO  
-- Drop the table.  
DROP TABLE T  
GO  
-- Now deny REFERENCES permission to TestLogin1 on the schema created previously.  
SETUSER  
GO  
DENY REFERENCES ON XML SCHEMA COLLECTION::myOtherDBSchema.myTestSchemaCollection TO TestLogin1  
  
GO  
-- Now TestLogin1 cannot create xml schema collection  
SETUSER 'TestLogin1'  
GO  
-- Following statement fails. TestLogin1 does not have REFERENCES   
-- permission on the XML schema collection.  
CREATE TABLE T(i int, x xml (myOtherDBSchema.myTestSchemaCollection))  
GO  
  
-- Final cleanup  
SETUSER  
GO  
USE master  
GO  
DROP DATABASE SampleDBForSchemaPermissions  
GO  
DROP LOGIN TestLogin1  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="cfaa2-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cfaa2-143">See Also</span></span>  
 <span data-ttu-id="cfaa2-144">[Vergleichen von typisiertem XML mit nicht typisiertem XML](compare-typed-xml-to-untyped-xml.md) </span><span class="sxs-lookup"><span data-stu-id="cfaa2-144">[Compare Typed XML to Untyped XML](compare-typed-xml-to-untyped-xml.md) </span></span>  
 <span data-ttu-id="cfaa2-145">[XML-Schemaauflistungen &#40;SQL Server&#41;](xml-schema-collections-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="cfaa2-145">[XML Schema Collections &#40;SQL Server&#41;](xml-schema-collections-sql-server.md) </span></span>  
 <span data-ttu-id="cfaa2-146">[Anforderungen und Einschränkungen für XML-Schemaauflistungen auf dem Server](requirements-and-limitations-for-xml-schema-collections-on-the-server.md) </span><span class="sxs-lookup"><span data-stu-id="cfaa2-146">[Requirements and Limitations for XML Schema Collections on the Server](requirements-and-limitations-for-xml-schema-collections-on-the-server.md) </span></span>  
 <span data-ttu-id="cfaa2-147">[DENY (Objektberechtigungen) &#40;Transact-SQL&#41;](/sql/t-sql/statements/deny-object-permissions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cfaa2-147">[DENY Object Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/deny-object-permissions-transact-sql) </span></span>  
 <span data-ttu-id="cfaa2-148">[GRANT (Objektberechtigungen) &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-object-permissions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cfaa2-148">[GRANT Object Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-object-permissions-transact-sql) </span></span>  
 [<span data-ttu-id="cfaa2-149">XML-Daten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="cfaa2-149">XML Data &#40;SQL Server&#41;</span></span>](xml-data-sql-server.md)  
  
  
