---
title: Domänenbasierte Attribute (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- domain-based attributes [Master Data Services], about domain-based attributes
- domain-based attributes [Master Data Services]
- attributes [Master Data Services], domain-based attributes
ms.assetid: df6f33ff-97f6-466c-af74-9780b2247473
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 9182974923848d49ed3e9ecfb58a14949784a2c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630674"
---
# <a name="domain-based-attributes-master-data-services"></a><span data-ttu-id="e610e-102">Domänenbasierte Attribute (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="e610e-102">Domain-Based Attributes (Master Data Services)</span></span>
  <span data-ttu-id="e610e-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]ist ein domänenbasiertes Attribut ein Attribut mit Werten, die mit Elementen aus einer anderen Entität aufgefüllt werden.</span><span class="sxs-lookup"><span data-stu-id="e610e-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], a domain-based attribute is an attribute with values that are populated by members from another entity.</span></span> <span data-ttu-id="e610e-104">Stellen Sie sich ein domänenbasiertes Attribut als eingeschränkte Liste vor. Domänenbasierte Attribute verhindern, dass Benutzer Attributwerte eingeben, die nicht gültig sind.</span><span class="sxs-lookup"><span data-stu-id="e610e-104">You can think of a domain-based attribute as a constrained list; domain-based attributes prevent users from entering attribute values that are not valid.</span></span> <span data-ttu-id="e610e-105">Um einen Attributwert auszuwählen, muss der Benutzer aus einer Liste auswählen.</span><span class="sxs-lookup"><span data-stu-id="e610e-105">To select an attribute value, the user must pick from a list.</span></span>

## <a name="domain-based-attribute-example"></a><span data-ttu-id="e610e-106">Beispiel für ein domänenbasiertes Attribut</span><span class="sxs-lookup"><span data-stu-id="e610e-106">Domain-Based Attribute Example</span></span>
 <span data-ttu-id="e610e-107">Im folgenden Bild verfügt die Produktentität über das domänenbasierte Attribut namens "Subcategory".</span><span class="sxs-lookup"><span data-stu-id="e610e-107">In the following image, the Product entity has a domain-based attribute called Subcategory.</span></span> <span data-ttu-id="e610e-108">Das Subcategory-Attribut wird mit Werten aus der Subcategory-Entität aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="e610e-108">The Subcategory attribute is populated by values from the Subcategory entity.</span></span>

 <span data-ttu-id="e610e-109">Die Entität Subcategory hat ein domänenbasiertes Attribut mit Namen Category.</span><span class="sxs-lookup"><span data-stu-id="e610e-109">The Subcategory entity has a domain-based attribute called Category.</span></span> <span data-ttu-id="e610e-110">Das Category-Attribut wird mit Werten aus der Category-Entität aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="e610e-110">The Category attribute is populated by values from the Category entity.</span></span>

 <span data-ttu-id="e610e-111">![Domänenbasierte Attribute in einer Entität](../../2014/master-data-services/media/mds-conc-domain-based-attribute-conceptual.gif "Domänenbasierte Attribute in einer Entität")</span><span class="sxs-lookup"><span data-stu-id="e610e-111">![Domain-Based Attributes in an Entity](../../2014/master-data-services/media/mds-conc-domain-based-attribute-conceptual.gif "Domain-Based Attributes in an Entity")</span></span>

## <a name="use-same-entity-for-multiple-domain-based-attributes"></a><span data-ttu-id="e610e-112">Dieselbe Entität für mehrere domänenbasierte Attribute verwenden</span><span class="sxs-lookup"><span data-stu-id="e610e-112">Use Same Entity for Multiple Domain-Based Attributes</span></span>
 <span data-ttu-id="e610e-113">Sie können die gleiche Entität als domänenbasiertes Attribut mehrerer Entitäten verwenden.</span><span class="sxs-lookup"><span data-stu-id="e610e-113">You can use the same entity as a domain-based attribute of multiple entities.</span></span> <span data-ttu-id="e610e-114">Sie können z. B. eine Entität mit dem Namen "YesNoIndicator" mit den folgenden Elementen erstellen: Yes, No und Maybe.</span><span class="sxs-lookup"><span data-stu-id="e610e-114">For example, you can create an entity called YesNoIndicator with the members: Yes, No, and Maybe.</span></span> <span data-ttu-id="e610e-115">Anschließend erstellen Sie ein domänenbasiertes Attribut mit dem Namen "InStock" und verwenden die "YesNoIndicator"-Entität als Quelle.</span><span class="sxs-lookup"><span data-stu-id="e610e-115">You can create a domain-based attribute named InStock and use the YesNoIndicator entity as the source.</span></span> <span data-ttu-id="e610e-116">Außerdem können Sie ein weiteres domänenbasiertes Attribut mit dem Namen "Approved" erstellen und die "YesNoIndicator"-Entität als Quelle verwenden.</span><span class="sxs-lookup"><span data-stu-id="e610e-116">You can also create another domain-based attribute named Approved and use the YesNoIndicator entity as a source.</span></span> <span data-ttu-id="e610e-117">Jedes Mal, wenn Benutzer aus einer Liste von Elementen der "YesNoIndicator"-Entität auswählen sollen, können Sie die Entität als domänenbasiertes Attribut verwenden.</span><span class="sxs-lookup"><span data-stu-id="e610e-117">Any time you want users to choose from a list of the YesNoIndicator entity's members, you can use the entity as a domain-based attribute.</span></span>

## <a name="domain-based-attributes-form-derived-hierarchies"></a><span data-ttu-id="e610e-118">Domänenbasierte Attribute bilden abgeleitete Hierarchien</span><span class="sxs-lookup"><span data-stu-id="e610e-118">Domain-Based Attributes Form Derived Hierarchies</span></span>
 <span data-ttu-id="e610e-119">Domänenbasierte Attributbeziehungen sind die Grundlage für abgeleitete Hierarchien.</span><span class="sxs-lookup"><span data-stu-id="e610e-119">Domain-based attribute relationships are the basis for derived hierarchies.</span></span> <span data-ttu-id="e610e-120">Weitere Informationen finden Sie unter [Abgeleitete Hierarchien &#40;Master Data Services&#41;](derived-hierarchies-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="e610e-120">For more information, see [Derived Hierarchies &#40;Master Data Services&#41;](derived-hierarchies-master-data-services.md).</span></span>

## <a name="related-tasks"></a><span data-ttu-id="e610e-121">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="e610e-121">Related Tasks</span></span>

|<span data-ttu-id="e610e-122">Taskbeschreibung</span><span class="sxs-lookup"><span data-stu-id="e610e-122">Task Description</span></span>|<span data-ttu-id="e610e-123">Thema</span><span class="sxs-lookup"><span data-stu-id="e610e-123">Topic</span></span>|
|----------------------|-----------|
|<span data-ttu-id="e610e-124">Erstellen Sie ein neues domänenbasiertes Attribut, für das eine vorhandene Entität als Quelle fungiert.</span><span class="sxs-lookup"><span data-stu-id="e610e-124">Create a new domain-based attribute that is sourced from an existing entity.</span></span>|[<span data-ttu-id="e610e-125">Erstellen eines domänenbasierten Attributs &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="e610e-125">Create a Domain-Based Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md)|
|<span data-ttu-id="e610e-126">Erstellen Sie eine neue Entität.</span><span class="sxs-lookup"><span data-stu-id="e610e-126">Create a new entity.</span></span>|[<span data-ttu-id="e610e-127">Erstellen einer Entität &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="e610e-127">Create an Entity &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-an-entity-master-data-services.md)|

## <a name="related-content"></a><span data-ttu-id="e610e-128">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="e610e-128">Related Content</span></span>

-   [<span data-ttu-id="e610e-129">Abgeleitete Hierarchien &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="e610e-129">Derived Hierarchies &#40;Master Data Services&#41;</span></span>](derived-hierarchies-master-data-services.md)

-   [<span data-ttu-id="e610e-130">Attribute &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="e610e-130">Attributes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/attributes-master-data-services.md)

-   [<span data-ttu-id="e610e-131">Entitäten &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="e610e-131">Entities &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/entities-master-data-services.md)


