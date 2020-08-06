---
title: Eine Auflistung der gespeicherten XML-Schemas anzeigen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- schema collections [SQL Server], viewing
- XML schemas [SQL Server], viewing
- CREATE XML SCHEMA COLLECTION statement
- xml_schema_namespace function
- XML schema collections [SQL Server], viewing
- displaying XML schema collections
- viewing XML schema collections
ms.assetid: e38031af-22df-4cd9-a14e-e316b822f91b
author: rothja
ms.author: jroth
ms.openlocfilehash: 6383fb17183a991d2f83325044663cc9671e9442
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609750"
---
# <a name="view-a-stored-xml-schema-collection"></a><span data-ttu-id="347c2-102">Anzeigen einer gespeicherten XML-Schemaauflistung</span><span class="sxs-lookup"><span data-stu-id="347c2-102">View a Stored XML Schema Collection</span></span>
  <span data-ttu-id="347c2-103">Nach dem Importieren einer XML-Schemaauflistung mithilfe von [CREATE XML SCHEMA COLLECTION](/sql/t-sql/statements/create-xml-schema-collection-transact-sql)werden die Schemakomponenten in den Metadaten gespeichert.</span><span class="sxs-lookup"><span data-stu-id="347c2-103">After you import an XML schema collection by using [CREATE XML SCHEMA COLLECTION](/sql/t-sql/statements/create-xml-schema-collection-transact-sql), the schema components are stored in the metadata.</span></span> <span data-ttu-id="347c2-104">Mit der systeminternen Funktion [xml_schema_namespace](/sql/t-sql/xml/xml-schema-namespace)können Sie die XML-Schemaauflistung rekonstruieren.</span><span class="sxs-lookup"><span data-stu-id="347c2-104">You can use the [xml_schema_namespace](/sql/t-sql/xml/xml-schema-namespace)intrinsic function to reconstruct the XML schema collection.</span></span> <span data-ttu-id="347c2-105">Diese Funktion gibt eine Instanz vom Datentyp `xml` zurück.</span><span class="sxs-lookup"><span data-stu-id="347c2-105">This function returns an `xml` data type instance.</span></span>  
  
 <span data-ttu-id="347c2-106">So ruft beispielsweise die folgende Abfrage eine XML-Schemaauflistung (`ProductDescriptionSchemaCollection`) aus dem relationalen Schema 'production' der [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] -Datenbank ab.</span><span class="sxs-lookup"><span data-stu-id="347c2-106">For example, the following query retrieves an XML schema collection (`ProductDescriptionSchemaCollection`) from the production relational schema in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span>  
  
```  
SELECT xml_schema_namespace(N'Production',N'ProductDescriptionSchemaCollection')  
GO  
```  
  
 <span data-ttu-id="347c2-107">Wenn nur ein Schema der XML-Schemaauflistung angezeigt werden soll, können Sie eine XQuery-Abfrage für das Ergebnis vom Typ `xml` angeben, das von `xml_schema_namespace` zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="347c2-107">If you want to see only one schema from the XML schema collection, you can specify XQuery against the `xml` type result that is returned by `xml_schema_namespace`.</span></span>  
  
```  
SELECT xml_schema_namespace(N'RelationalSchemaName',N'XmlSchemaCollectionName').query('  
/xs:schema[@targetNamespace="TargetNameSpace"]  
')  
GO  
```  
  
 <span data-ttu-id="347c2-108">So ruft beispielsweise die folgende Abfrage XML-Schemainformationen zur Produktgarantie und -wartung aus der XML-Schemaauflistung `ProductDescriptionSchemaCollection` ab.</span><span class="sxs-lookup"><span data-stu-id="347c2-108">For example, the following query retrieves product warranty and maintenance XML schema information from the `ProductDescriptionSchemaCollection` XML schema collection.</span></span>  
  
```  
SELECT xml_schema_namespace(N'Production',N'ProductDescriptionSchemaCollection').query('  
/xs:schema[@targetNamespace="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelWarrAndMain"]  
')  
GO  
```  
  
 <span data-ttu-id="347c2-109">Sie können auch den optionalen Zielnamespace als dritten Parameter an die `xml_schema_namespace` -Funktion übergeben, um ein bestimmtes Schema aus der Auflistung abzurufen, wie es in der folgenden Abfrage gezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="347c2-109">You can also pass the optional target namespace as the third parameter to the `xml_schema_namespace` function to retrieve specific schema from the collection, as shown in the following query:</span></span>  
  
```  
SELECT xml_schema_namespace(N'Production',N'ProductDescriptionSchemaCollection', N'https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelWarrAndMain')  
GO  
```  
  
 <span data-ttu-id="347c2-110">Wenn Sie eine XML-Schemaauflistung mithilfe von CREATE XML SCHEMA COLLECTION in der Datenbank erstellen, speichert die Anweisung die Schemakomponenten in den Metadaten.</span><span class="sxs-lookup"><span data-stu-id="347c2-110">When you create an XML schema collection by using CREATE XML SCHEMA COLLECTION in the database, the statement stores the schema components in the metadata.</span></span> <span data-ttu-id="347c2-111">Beachten Sie, dass nur die von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] interpretierbaren Schemakomponenten gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="347c2-111">Note that only the schema components that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] understands are stored.</span></span> <span data-ttu-id="347c2-112">Kommentare, Anmerkungen oder Nicht-XSD-Attribute werden nicht gespeichert.</span><span class="sxs-lookup"><span data-stu-id="347c2-112">Any comments, annotations, or non-XSD attributes are not stored.</span></span> <span data-ttu-id="347c2-113">Daher ist das von **xml_schema_namespace** rekonstruierte Schema zwar hinsichtlich seiner Funktionalität mit dem ursprünglichen Schema gleichwertig, sein Erscheinungsbild jedoch nicht unbedingt identisch.</span><span class="sxs-lookup"><span data-stu-id="347c2-113">Therefore, the schema reconstructed by **xml_schema_namespace** is functionally equivalent to the original schema, but it will not necessarily look the same.</span></span> <span data-ttu-id="347c2-114">Beispielsweise werden Sie die Präfixe des ursprünglichen Schemas nicht wiederfinden.</span><span class="sxs-lookup"><span data-stu-id="347c2-114">For example, you will not see the same prefixes you had in the original schema.</span></span> <span data-ttu-id="347c2-115">Das von **xml_schema_namespace** zurückgegebene Schema verwendet **t** als Präfix für den Zielnamespace und **ns1**, **ns2**usw. für andere Namespaces.</span><span class="sxs-lookup"><span data-stu-id="347c2-115">The schema returned by **xml_schema_namespace** uses **t** as the prefix for the target namespace and **ns1**, **ns2**, and so on, for other namespaces.</span></span>  
  
 <span data-ttu-id="347c2-116">Wenn Sie eine identische Kopie des XML-Schemas aufbewahren möchten, sollten Sie das XML-Schema in einer Datei oder in einer Datenbanktabelle in einer Spalte vom Typ `xml` speichern.</span><span class="sxs-lookup"><span data-stu-id="347c2-116">If you want to retain an identical copy of the XML schemas, you should save your XML schema in a file or in a database table in an `xml` type column.</span></span>  
  
 <span data-ttu-id="347c2-117">Die [sys.xml_schema_collections](/sql/relational-databases/system-catalog-views/sys-xml-schema-collections-transact-sql) -Katalogsicht gibt auch Informationen zu XML-Schemaauflistungen zurück.</span><span class="sxs-lookup"><span data-stu-id="347c2-117">The [sys.xml_schema_collections](/sql/relational-databases/system-catalog-views/sys-xml-schema-collections-transact-sql) catalog view also returns information about XML schema collections.</span></span> <span data-ttu-id="347c2-118">Zu diesen Informationen gehören der Name der Auflistung, das Erstellungsdatum und der Besitzer der Auflistung.</span><span class="sxs-lookup"><span data-stu-id="347c2-118">This information includes the name of the collection, the creation date, and the owner of the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="347c2-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="347c2-119">See Also</span></span>  
 [<span data-ttu-id="347c2-120">XML-Schemaauflistungen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="347c2-120">XML Schema Collections &#40;SQL Server&#41;</span></span>](xml-schema-collections-sql-server.md)  
  
  
