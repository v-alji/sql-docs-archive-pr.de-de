---
title: Aufheben der Berechtigungen für eine XML-Schemaauflistung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- revoking permissions [SQL Server]
ms.assetid: 4e542b70-2d56-4a65-8a39-96a1ed477ca6
author: rothja
ms.author: jroth
ms.openlocfilehash: 3ab37c915f14207376e0c4a9582611bf8e65e0d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697589"
---
# <a name="revoke-permissions-on-an-xml-schema-collection"></a><span data-ttu-id="7d238-102">Aufheben der Berechtigungen für eine XML-Schemaauflistung</span><span class="sxs-lookup"><span data-stu-id="7d238-102">Revoke Permissions on an XML Schema Collection</span></span>
  <span data-ttu-id="7d238-103">Die Berechtigung zum Erstellen einer XML-Schemaauflistung kann mithilfe eines der folgenden Verfahren aufgehoben werden:</span><span class="sxs-lookup"><span data-stu-id="7d238-103">The permission to create an XML schema collection can be revoked by using one of the following:</span></span>  
  
-   <span data-ttu-id="7d238-104">Aufheben der ALTER-Berechtigung für das relationale Schema.</span><span class="sxs-lookup"><span data-stu-id="7d238-104">Revoke the ALTER permission for the relational schema.</span></span> <span data-ttu-id="7d238-105">Der Prinzipal kann in diesem Fall keine XML-Schemaauflistung im relationalen Schema erstellen.</span><span class="sxs-lookup"><span data-stu-id="7d238-105">Then, the principal cannot create an XML schema collection in the relational schema.</span></span> <span data-ttu-id="7d238-106">Der Prinzipal kann dies jedoch auch weiterhin in anderen relationalen Schemas in der gleichen Datenbank.</span><span class="sxs-lookup"><span data-stu-id="7d238-106">However, the principal can still do so in other relational schemas in the same database.</span></span>  
  
-   <span data-ttu-id="7d238-107">Aufheben der ALTER ANY SCHEMA-Berechtigung für die Datenbank für den Prinzipal.</span><span class="sxs-lookup"><span data-stu-id="7d238-107">Revoke the ALTER ANY SCHEMA permission on the database for the principal.</span></span> <span data-ttu-id="7d238-108">Der Prinzipal kann in diesem Fall keine XML-Schemaauflistung in der gesamten Datenbank erstellen.</span><span class="sxs-lookup"><span data-stu-id="7d238-108">Then, the principal cannot create an XML schema collection anywhere in the database.</span></span>  
  
-   <span data-ttu-id="7d238-109">Aufheben der CREATE XML SCHEMA COLLECTION- oder ALTER XML SCHEMA COLLECTION-Berechtigung für die Datenbank für den Prinzipal.</span><span class="sxs-lookup"><span data-stu-id="7d238-109">Revoke the CREATE XML SCHEMA COLLECTION or ALTER XML SCHEMA COLLECTION permission on the database for the principal.</span></span> <span data-ttu-id="7d238-110">Dies verhindert, dass der Prinzipal eine XML-Schemaauflistung innerhalb der Datenbank importieren kann.</span><span class="sxs-lookup"><span data-stu-id="7d238-110">This prevents the principal from importing an XML schema collection within the database.</span></span> <span data-ttu-id="7d238-111">Das Aufheben der ALTER- oder CONTROL-Berechtigung für die Datenbank besitzt die gleichen Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="7d238-111">Revoking the ALTER or CONTROL permission on the database has the same effect.</span></span>  
  
## <a name="revoking-permissions-on-an-existing-xml-schema-collection-object"></a><span data-ttu-id="7d238-112">Aufheben der Berechtigungen für ein vorhandenes XML-Schemaauflistungsobjekt</span><span class="sxs-lookup"><span data-stu-id="7d238-112">Revoking Permissions on an Existing XML Schema Collection Object</span></span>  
 <span data-ttu-id="7d238-113">Im Folgenden finden Sie die Berechtigungen, die für eine XML-Schemaauflistung aufgehoben werden können, sowie die Ergebnisse:</span><span class="sxs-lookup"><span data-stu-id="7d238-113">Following are the permissions that can be revoked on an XML schema collection and the results:</span></span>  
  
-   <span data-ttu-id="7d238-114">Durch das Aufheben der ALTER-Berechtigung wird die Fähigkeit eines Prinzipals zum Ändern des Inhalts der XML-Schemaauflistung aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="7d238-114">Revoking the ALTER permission revokes a principal's ability to modify the content of the XML schema collection.</span></span>  
  
-   <span data-ttu-id="7d238-115">Durch das Aufheben der TAKE OWNERSHIP-Berechtigung wird die Fähigkeit eines Prinzipals zum Übertragen des Besitzes der XML-Schemaauflistung aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="7d238-115">Revoking the TAKE OWNERSHIP permission revokes a principal's ability to transfer ownership of the XML schema collection.</span></span>  
  
-   <span data-ttu-id="7d238-116">Durch das Aufheben der REFERENCES-Berechtigung wird die Fähigkeit eines Prinzipals zum Verwenden der XML-Schemaauflistung zum Typisieren oder Einschränken von Spalten des xml-Typs in Tabellen und Sichten sowie Parametern aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="7d238-116">Revoking the REFERENCES permission revokes a principal's ability to use the XML schema collection for typing or constraining xml type columns, in tables and views, and parameters.</span></span> <span data-ttu-id="7d238-117">Außerdem wird die Berechtigung zum Verweisen auf diese Schemaauflistung aus anderen XML-Schemaauflistungen aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="7d238-117">It also revokes the permission to refer to this schema collection from other XML schema collections.</span></span>  
  
-   <span data-ttu-id="7d238-118">Durch das Aufheben der VIEW DEFINITION-Berechtigung wird die Fähigkeit eines Prinzipals zum Anzeigen des Inhalts einer XML-Schemaauflistung aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="7d238-118">Revoking the VIEW DEFINITION permission revokes a principal's ability to view the contents of an XML schema collection.</span></span>  
  
-   <span data-ttu-id="7d238-119">Durch das Aufheben der EXECUTE-Berechtigung wird die Fähigkeit eines Prinzipals zum Einfügen oder Aktualisieren von Werten in Spalten, Variablen und Parametern aufgehoben, die durch die XML-Auflistung typisiert oder eingeschränkt werden.</span><span class="sxs-lookup"><span data-stu-id="7d238-119">Revoking the EXECUTE permission revokes a principal's ability to insert or update values in columns, variables, and parameters that are typed or constrained by the XML collection.</span></span> <span data-ttu-id="7d238-120">Außerdem wird die Fähigkeit zum Abfragen solcher Spalten, Variablen oder Parameter vom Typ **xml** aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="7d238-120">It also revokes the ability to query such **xml** type columns, variables, or parameters.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="7d238-121">Beispiele</span><span class="sxs-lookup"><span data-stu-id="7d238-121">Examples</span></span>  
 <span data-ttu-id="7d238-122">Die Szenarien in den folgenden Beispielen veranschaulichen, wie XML-Schemaberechtigungen funktionieren.</span><span class="sxs-lookup"><span data-stu-id="7d238-122">The scenarios in the following examples illustrate how XML schema permissions work.</span></span> <span data-ttu-id="7d238-123">Jedes dieser Beispiele erstellt die erforderliche Testdatenbank, die relationalen Schemas und Anmeldungen.</span><span class="sxs-lookup"><span data-stu-id="7d238-123">Each example creates the necessary test database, relational schemas, and logins.</span></span> <span data-ttu-id="7d238-124">Diesen Anmeldenamen werden die erforderlichen Berechtigungen für XML-Schemaauflistungen erteilt.</span><span class="sxs-lookup"><span data-stu-id="7d238-124">These logins are granted the necessary XML schema collection permissions.</span></span> <span data-ttu-id="7d238-125">Jedes der Beispiele führt am Ende den erforderlichen Cleanup aus.</span><span class="sxs-lookup"><span data-stu-id="7d238-125">Each example does the necessary cleanup at the end.</span></span>  
  
### <a name="a-revoking-permissions-to-create-an-xml-schema-collection"></a><span data-ttu-id="7d238-126">A.</span><span class="sxs-lookup"><span data-stu-id="7d238-126">A.</span></span> <span data-ttu-id="7d238-127">Aufheben der Berechtigungen zum Erstellen einer XML-Schemaauflistung</span><span class="sxs-lookup"><span data-stu-id="7d238-127">Revoking permissions to create an XML schema collection</span></span>  
 <span data-ttu-id="7d238-128">Dieses Beispiel erstellt eine Anmeldung und eine Beispieldatenbank.</span><span class="sxs-lookup"><span data-stu-id="7d238-128">This example creates a login and a sample database.</span></span> <span data-ttu-id="7d238-129">Darüber hinaus wird in der Datenbank ein relationales Schema hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="7d238-129">It also adds a relational schema in the database.</span></span> <span data-ttu-id="7d238-130">Anfangs werden dem Anmeldenamen die ALTER-Berechtigung für relationale Schemas und andere erforderliche Berechtigungen zum Erstellen von XML-Schemaauflistungen erteilt.</span><span class="sxs-lookup"><span data-stu-id="7d238-130">Initially, the login is granted ALTER permission on both relational schemas and other necessary permissions to create XML schema collections.</span></span> <span data-ttu-id="7d238-131">Das Beispiel hebt dann die ALTER-Berechtigung für eines der relationalen Schemas in der Datenbank auf.</span><span class="sxs-lookup"><span data-stu-id="7d238-131">The example then revokes the ALTER permission on one of the relational schemas in the database.</span></span> <span data-ttu-id="7d238-132">Dies verhindert, dass der Anmeldename eine XML-Schemaauflistung erstellen kann.</span><span class="sxs-lookup"><span data-stu-id="7d238-132">This prevents the login from creating an XML schema collection.</span></span>  
  
```  
setuser  
go  
create login TestLogin1 with password='SQLSvrPwd1'  
go  
create database SampleDBForSchemaPermissions  
go  
use SampleDBForSchemaPermissions  
go  
-- Create another relational schema in the db (in addition to dbo schema)  
CREATE SCHEMA myOtherDBSchema  
go  
CREATE USER TestLogin1  
go  
-- For TestLogin1 to create/import XML schema collection, following  
-- permission needed  
-- CREATE XML SCHEMA is a database level permission  
GRANT CREATE XML SCHEMA COLLECTION TO TestLogin1  
go  
GRANT ALTER ON SCHEMA::myOtherDBSchema TO TestLogin1  
go  
GRANT ALTER ON SCHEMA::dbo TO TestLogin1  
go  
-- Now TestLogin1 can import an XML schema collection in both relational schemas.  
setuser 'TestLogin1'  
go  
CREATE XML SCHEMA COLLECTION dbo.myTestSchemaCollection AS '<?xml version="1.0" encoding="UTF-8" ?>  
  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
elementFormDefault="qualified">  
<xsd:element name="telephone" type="xsd:string" />  
</xsd:schema>'  
go  
-- TestLogin1 can create XML schema collection in myOtherDBSchema relational schema  
CREATE XML SCHEMA COLLECTION myOtherDBSchema.myTestSchemaCollection AS '<?xml version="1.0" encoding="UTF-8" ?>  
  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
elementFormDefault="qualified">  
<xsd:element name="telephone" type="xsd:string" />  
</xsd:schema>'  
go  
-- Let us drop XML schema collections from both relational schemas  
DROP XML SCHEMA COLLECTION myOtherDBSchema.myTestSchemaCollection  
go  
DROP XML SCHEMA COLLECTION dbo.myTestSchemaCollection  
go  
-- now REVOKE permission from TestLogin1 to alter myOtherDBSchema  
setuser  
go  
REVOKE ALTER ON SCHEMA::myOtherDBSchema FROM TestLogin1  
go  
-- now TestLogin1 cannot create xml schema collection in myOtherDBSchema  
setuser 'TestLogin1'  
go  
CREATE XML SCHEMA COLLECTION myOtherDBSchema.myTestSchemaCollection AS '<?xml version="1.0" encoding="UTF-8" ?>  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
elementFormDefault="qualified">  
<xsd:element name="telephone" type="xsd:string" />  
</xsd:schema>'  
go  
  
-- TestLogin1 can still create XML schema collections in dbo  
-- It cannot create XML schema collections anywhere in the database  
-- if we REVOKE CREATE XML SCHEMA COLLECTION permission  
SETUSER  
go  
REVOKE CREATE XML SCHEMA COLLECTION FROM TestLogin1  
go  
  
setuser 'TestLogin1'  
go  
-- the following now should fail  
CREATE XML SCHEMA COLLECTION dbo.myTestSchemaCollection AS '<?xml version="1.0" encoding="UTF-8" ?>  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
elementFormDefault="qualified">  
<xsd:element name="telephone" type="xsd:string" />  
</xsd:schema>'  
go  
  
-- Final cleanup  
SETUSER  
go  
USE master  
go  
DROP DATABASE SampleDBForSchemaPermissions  
go  
DROP LOGIN TestLogin1  
Go  
```  
  
## <a name="see-also"></a><span data-ttu-id="7d238-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7d238-133">See Also</span></span>  
 <span data-ttu-id="7d238-134">[XML-Daten &#40;SQL Server&#41;](xml-data-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7d238-134">[XML Data &#40;SQL Server&#41;](xml-data-sql-server.md) </span></span>  
 <span data-ttu-id="7d238-135">[Vergleichen von typisiertem XML mit nicht typisiertem XML](compare-typed-xml-to-untyped-xml.md) </span><span class="sxs-lookup"><span data-stu-id="7d238-135">[Compare Typed XML to Untyped XML](compare-typed-xml-to-untyped-xml.md) </span></span>  
 <span data-ttu-id="7d238-136">[XML-Schemaauflistungen &#40;SQL Server&#41;](xml-schema-collections-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7d238-136">[XML Schema Collections &#40;SQL Server&#41;](xml-schema-collections-sql-server.md) </span></span>  
 [<span data-ttu-id="7d238-137">Anforderungen und Einschränkungen für XML-Schemaauflistungen auf dem Server</span><span class="sxs-lookup"><span data-stu-id="7d238-137">Requirements and Limitations for XML Schema Collections on the Server</span></span>](requirements-and-limitations-for-xml-schema-collections-on-the-server.md)  
  
  
