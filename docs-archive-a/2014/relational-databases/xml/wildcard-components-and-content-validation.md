---
title: Platzhalterkomponenten und Inhaltsüberprüfung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- wildcard components [XML]
- content validation [XML]
ms.assetid: ffa7d974-3645-446c-8425-f0b22b6b060a
author: rothja
ms.author: jroth
ms.openlocfilehash: 76ff2b48efb8cff0b98827fe8522405682c294e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609753"
---
# <a name="wildcard-components-and-content-validation"></a><span data-ttu-id="0906d-102">Platzhalterkomponenten und Inhaltsüberprüfung</span><span class="sxs-lookup"><span data-stu-id="0906d-102">Wildcard Components and Content Validation</span></span>
  <span data-ttu-id="0906d-103">Platzhalterkomponenten werden verwendet, um die Flexibilität der zulässigen Inhalte in einem Inhaltsmodell zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="0906d-103">Wildcard components are used to increase flexibility in what is allowed to appear in a content model.</span></span> <span data-ttu-id="0906d-104">Diese Komponenten werden in der XSD-Sprache auf folgende Weise unterstützt:</span><span class="sxs-lookup"><span data-stu-id="0906d-104">These components are supported in the XSD language in the following ways:</span></span>  
  
-   <span data-ttu-id="0906d-105">Elementplatzhalterkomponenten.</span><span class="sxs-lookup"><span data-stu-id="0906d-105">Element wildcard components.</span></span> <span data-ttu-id="0906d-106">Diese werden durch das **\<xsd:any>** -Element dargestellt.</span><span class="sxs-lookup"><span data-stu-id="0906d-106">These are represented by the **\<xsd:any>** element.</span></span>  
  
-   <span data-ttu-id="0906d-107">Attributplatzhalterkomponenten.</span><span class="sxs-lookup"><span data-stu-id="0906d-107">Attribute wildcard components.</span></span> <span data-ttu-id="0906d-108">Diese werden durch das **\<xsd:anyAttribute>** -Element dargestellt.</span><span class="sxs-lookup"><span data-stu-id="0906d-108">These are represented by the **\<xsd:anyAttribute>** element.</span></span>  
  
 <span data-ttu-id="0906d-109">Die beiden Platzhalterzeichenelemente **\<xsd:any>** und **\<xsd:anyAttribute>** unterstützen die Verwendung eines **processContents**-Attributs.</span><span class="sxs-lookup"><span data-stu-id="0906d-109">Both wildcard character elements, **\<xsd:any>** and **\<xsd:anyAttribute>**, support the use of a **processContents** attribute.</span></span> <span data-ttu-id="0906d-110">Auf diese Weise können Sie einen Wert angeben, der angibt, wie XML-Anwendungen die Überprüfung des Dokumentinhalts durchführen, der diesen Platzhalterzeichenelementen zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="0906d-110">This lets you specify a value that indicates how XML applications handle the validation of document content associated with these wildcard character elements.</span></span> <span data-ttu-id="0906d-111">Die folgenden Werte und Auswirkungen werden bereitgestellt:</span><span class="sxs-lookup"><span data-stu-id="0906d-111">These are the different values and their effect:</span></span>  
  
-   <span data-ttu-id="0906d-112">Der **strict** -Wert gibt an, dass der Inhalt vollständig überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="0906d-112">The **strict** value specifies that the contents are fully validated.</span></span>  
  
-   <span data-ttu-id="0906d-113">Der **skip** -Wert gibt an, dass der Inhalt nicht überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="0906d-113">The **skip** value specifies that the contents are not validated.</span></span>  
  
-   <span data-ttu-id="0906d-114">Der **lax** -Wert gibt an, dass nur Elemente und Attribute überprüft werden, für die Schemadefinitionen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="0906d-114">The **lax** value specifies that only elements and attributes for which schema definitions are available are validated.</span></span>  
  
## <a name="lax-validation-and-xsanytype-elements"></a><span data-ttu-id="0906d-115">Lax-Überprüfung und xs:anyType-Elemente</span><span class="sxs-lookup"><span data-stu-id="0906d-115">Lax Validation and xs:anyType Elements</span></span>  
 <span data-ttu-id="0906d-116">Die XML-Schemaspezifikation verwendet die **lax** -Überprüfung für Elemente des **anyType** -Datentyps.</span><span class="sxs-lookup"><span data-stu-id="0906d-116">The XML Schema specification uses **lax** validation for elements of the **anyType** type.</span></span> <span data-ttu-id="0906d-117">Da [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] die "lax"-Überprüfung nicht unterstützte, wurde die strict-Überprüfung für Elemente des **anyType**-Datentyps verwendet.</span><span class="sxs-lookup"><span data-stu-id="0906d-117">Because [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] did not support lax validation, strict validation was applied for elements of the **anyType**.</span></span> <span data-ttu-id="0906d-118">Ab [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]wird die lax-Überprüfung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0906d-118">Beginning with [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], lax validation is supported.</span></span> <span data-ttu-id="0906d-119">Inhalt der Elemente des Typs **anyType** wird mit lax-Überprüfung überprüft.</span><span class="sxs-lookup"><span data-stu-id="0906d-119">Content of elements of type **anyType** will be validated using lax validation.</span></span>  
  
 <span data-ttu-id="0906d-120">Das folgende Beispiel veranschaulicht die laxÜberprüfung.</span><span class="sxs-lookup"><span data-stu-id="0906d-120">The following example illustrates the lax validation.</span></span> <span data-ttu-id="0906d-121">Das Schemaelement `e` weist den Typ **anyType** auf.</span><span class="sxs-lookup"><span data-stu-id="0906d-121">The schema element `e` is of the **anyType** type.</span></span> <span data-ttu-id="0906d-122">Im Beispiel werden typisierte **xml** -Variablen erstellt und die **strict** -Überprüfung des Elements vom Typ anyType veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="0906d-122">The example creates typed **xml** variables and illustrates the lax validation of the element of the **anyType** type.</span></span>  
  
```  
CREATE XML SCHEMA COLLECTION SC AS '  
<schema xmlns="http://www.w3.org/2001/XMLSchema"   
        targetNamespace="http://ns">  
   <element name="e" type="anyType"/>  
   <element name="a" type="byte"/>  
   <element name="b" type="string"/>  
 </schema>'  
GO  
```  
  
 <span data-ttu-id="0906d-123">Das folgende Beispiel ist erfolgreich, weil die Überprüfung von `<e>` erfolgreich ist:</span><span class="sxs-lookup"><span data-stu-id="0906d-123">The following example succeeds, because the validation of `<e>` is successful:</span></span>  
  
```  
DECLARE @var XML(SC)  
SET @var = '<e xmlns="http://ns"><a>1</a><b>data</b></e>'  
GO  
```  
  
 <span data-ttu-id="0906d-124">Das folgende Beispiel ist erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="0906d-124">The following example succeeds.</span></span> <span data-ttu-id="0906d-125">Die Instanz wird akzeptiert, obwohl kein `<c>` -Element im Schema definiert wird:</span><span class="sxs-lookup"><span data-stu-id="0906d-125">The instance is accepted, even though no element `<c>` is defined in the schema:</span></span>  
  
```  
DECLARE @var XML(SC)  
SET @var = '<e xmlns="http://ns"><a>1</a><c>Wrong</c><b>data</b></e>'  
GO  
```  
  
 <span data-ttu-id="0906d-126">Die XML-Instanz im folgenden Beispiel wird abgelehnt, weil die Definition des `<a>` -Elements keinen Zeichenfolgenwert zulässt.</span><span class="sxs-lookup"><span data-stu-id="0906d-126">The XML instance in the following example is rejected, because the definition of the `<a>` element does not allow a string value.</span></span>  
  
```  
DECLARE @var XML(SC)  
SET @var = '<e xmlns="http://ns"><a>Wrong</a><b>data</b></e>'  
SELECT @var  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="0906d-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0906d-127">See Also</span></span>  
 [<span data-ttu-id="0906d-128">Anforderungen und Einschränkungen für XML-Schemaauflistungen auf dem Server</span><span class="sxs-lookup"><span data-stu-id="0906d-128">Requirements and Limitations for XML Schema Collections on the Server</span></span>](requirements-and-limitations-for-xml-schema-collections-on-the-server.md)  
  
  
