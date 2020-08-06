---
title: Ändern von vorhandenen Spalten in XML-Spalten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- tables [XML]
ms.assetid: 0d951424-9862-41fe-bd46-127f1c059bcb
author: rothja
ms.author: jroth
ms.openlocfilehash: 32447851fcfe2a54143a028a94539532bba6708d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608445"
---
# <a name="change-existing-columns-to-xml-columns"></a><span data-ttu-id="342ab-102">Ändern von vorhandenen Spalten in XML-Spalten</span><span class="sxs-lookup"><span data-stu-id="342ab-102">Change Existing Columns to XML Columns</span></span>
  <span data-ttu-id="342ab-103">Die ALTER TABLE-Anweisung unterstützt den `xml`-Datentyp.</span><span class="sxs-lookup"><span data-stu-id="342ab-103">The ALTER TABLE statement supports the `xml` data type.</span></span> <span data-ttu-id="342ab-104">So können Sie z. B. eine beliebige Spalte vom Zeichenfolgentyp in den `xml`-Datentyp ändern.</span><span class="sxs-lookup"><span data-stu-id="342ab-104">For example, you can alter any string type column to the `xml` data type.</span></span> <span data-ttu-id="342ab-105">Beachten Sie, dass die in der Spalte enthaltenen Dokumente dazu wohlgeformt sein müssen.</span><span class="sxs-lookup"><span data-stu-id="342ab-105">Note that in these cases, the documents contained in the column must be well formed.</span></span> <span data-ttu-id="342ab-106">Außerdem werden beim Ändern des Spaltentyps vom Zeichenfolgentyp in den typisierten XML-Typ die Dokumente in der Spalte anhand der angegebenen XSD-Schemas überprüft.</span><span class="sxs-lookup"><span data-stu-id="342ab-106">Also, if you are changing the type of the column from string to typed xml, the documents in the column are validated against the specified XSD schemas.</span></span>  
  
```  
CREATE TABLE T (Col1 int primary key, Col2 nvarchar(max))  
GO  
INSERT INTO T   
VALUES (1, '<Root><Product ProductID="1"/></Root>')  
GO  
ALTER TABLE T   
ALTER COLUMN Col2 xml  
GO  
```  
  
 <span data-ttu-id="342ab-107">Sie können eine nicht typisierte Spalte vom Typ `xml` in eine typisierte XML-Spalte ändern.</span><span class="sxs-lookup"><span data-stu-id="342ab-107">You can change an `xml` type column from untyped XML to typed XML.</span></span> <span data-ttu-id="342ab-108">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="342ab-108">For example:</span></span>  
  
```  
CREATE TABLE T (Col1 int primary key, Col2 xml)  
GO  
INSERT INTO T   
values (1, '<p1:ProductDescription ProductModelID="1"   
xmlns:p1="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription">  
            </p1:ProductDescription>')  
GO   
-- Make it a typed xml column by specifying a schema collection.  
ALTER TABLE T   
ALTER COLUMN Col2 xml (Production.ProductDescriptionSchemaCollection)  
GO  
```  
  
> [!NOTE]  
>  <span data-ttu-id="342ab-109">Das Skript wird für die [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] -Datenbank ausgeführt, da die XML-Schemaauflistung `Production.ProductDescriptionSchemaCollection`als Teil der [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] -Datenbank erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="342ab-109">The script will run against [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database, because the XML schema collection, `Production.ProductDescriptionSchemaCollection`, is created as part of the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span>  
  
 <span data-ttu-id="342ab-110">Im vorherigen Beispiel werden alle in der Spalte gespeicherten Instanzen mit den XSD-Schemas der angegebenen Auflistung überprüft und typisiert.</span><span class="sxs-lookup"><span data-stu-id="342ab-110">In the previous example, all the instances stored in the column are validated and typed against the XSD schemas in the specified collection.</span></span> <span data-ttu-id="342ab-111">Wenn die Spalte eine oder mehrere in Bezug auf das angegebene Schema ungültige XML-Instanzen enthält, erzeugt die `ALTER TABLE` -Anweisung einen Fehler, d. h. Sie können die nicht typisierte XML-Spalte nicht in eine typisierte XML-Spalte ändern.</span><span class="sxs-lookup"><span data-stu-id="342ab-111">If the column contains one or more XML instances that are invalid with regard to the specified schema, the `ALTER TABLE` statement will fail and you will not be able to change your untyped XML column into typed XML.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="342ab-112">Bei umfangreichen Tabellen kann das Ändern einer Spalte vom Typ `xml` äußerst aufwändig werden,</span><span class="sxs-lookup"><span data-stu-id="342ab-112">If a table is large, modifying an `xml` type column can be costly.</span></span> <span data-ttu-id="342ab-113">da jedes Dokument auf Wohlgeformtheit überprüft und bei typisierten XML-Dokumenten auch eine Überprüfung durchgeführt werden muss.</span><span class="sxs-lookup"><span data-stu-id="342ab-113">This is because each document must be checked for being well formed and, for typed XML, must also be validated.</span></span>  
  
 <span data-ttu-id="342ab-114">Weitere Informationen zu typisierten XML-Dokumenten finden Sie unter [Vergleichen von typisiertem XML mit nicht typisiertem XML](compare-typed-xml-to-untyped-xml.md).</span><span class="sxs-lookup"><span data-stu-id="342ab-114">For more information about typed XML, see [Compare Typed XML to Untyped XML](compare-typed-xml-to-untyped-xml.md).</span></span>  
  
  
