---
title: Überlappende Modell- und Elementberechtigungen (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- models [Master Data Services], effective permissions
- permissions [Master Data Services], model and member overlaps
- members [Master Data Services], effective permissions
ms.assetid: 9fd7a555-43bf-4796-a8b6-1ca63a291216
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ec5f4019f25a777e4c70433bd9a7e72fca2277e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609284"
---
# <a name="overlapping-model-and-member-permissions-master-data-services"></a><span data-ttu-id="a6223-102">Überlappende Modell- und Elementberechtigungen (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="a6223-102">Overlapping Model and Member Permissions (Master Data Services)</span></span>
  <span data-ttu-id="a6223-103">Die einem Element zugewiesene Berechtigung kann mit einer einem Modellobjekt zugewiesenen Berechtigung überlappen.</span><span class="sxs-lookup"><span data-stu-id="a6223-103">Permission assigned to a member can overlap with permission assigned to a model object.</span></span> <span data-ttu-id="a6223-104">Bei einer Überlappung tritt die restriktivere Berechtigung in Kraft.</span><span class="sxs-lookup"><span data-stu-id="a6223-104">When overlaps occur, the more restrictive permission takes effect.</span></span>  
  
 <span data-ttu-id="a6223-105">Wenn ein Element über eine Berechtigung verfügt, die sich von der des zugehörigen Modellobjekts unterscheidet, gelten die folgenden Regeln:</span><span class="sxs-lookup"><span data-stu-id="a6223-105">If a member has permission that is different than its corresponding model object, the following rules apply:</span></span>  
  
-   <span data-ttu-id="a6223-106">Mit**Verweigern** werden alle anderen Berechtigungen überschrieben.</span><span class="sxs-lookup"><span data-stu-id="a6223-106">**Deny** overrides all other permissions.</span></span>  
  
-   <span data-ttu-id="a6223-107">Schreib **geschützte über schreibungen** von **Updates**.</span><span class="sxs-lookup"><span data-stu-id="a6223-107">**Read-only** overrides **Update**.</span></span>  
  
 <span data-ttu-id="a6223-108">Das folgende Bild zeigt, welche Berechtigungen für einen einzelnen Attributwert wirksam werden, wenn Attributberechtigungen sich von Elementberechtigungen unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="a6223-108">The following image shows which permissions take effect on an individual attribute value when attribute permissions are different than member permissions.</span></span>  
  
 <span data-ttu-id="a6223-109">![mds_conc_security_member_overlap_table](../../2014/master-data-services/media/mds-conc-security-member-overlap-table.gif "mds_conc_security_member_overlap_table")</span><span class="sxs-lookup"><span data-stu-id="a6223-109">![mds_conc_security_member_overlap_table](../../2014/master-data-services/media/mds-conc-security-member-overlap-table.gif "mds_conc_security_member_overlap_table")</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="a6223-110">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="a6223-110">Example 1</span></span>  
 <span data-ttu-id="a6223-111">![mds_conc_overlap_model_1](../../2014/master-data-services/media/mds-conc-overlap-model-1.gif "mds_conc_overlap_model_1")</span><span class="sxs-lookup"><span data-stu-id="a6223-111">![mds_conc_overlap_model_1](../../2014/master-data-services/media/mds-conc-overlap-model-1.gif "mds_conc_overlap_model_1")</span></span>  
  
 <span data-ttu-id="a6223-112">Auf der Registerkarte **Modelle** verfügt die Product-Entität über die zugewiesene Berechtigung **Aktualisieren** .</span><span class="sxs-lookup"><span data-stu-id="a6223-112">On the **Models** tab, the Product entity has **Update** permission assigned.</span></span> <span data-ttu-id="a6223-113">Diese Berechtigung wird von allen Attributen in der Entität geerbt.</span><span class="sxs-lookup"><span data-stu-id="a6223-113">All attributes in the entity inherit that permission.</span></span>  
  
 <span data-ttu-id="a6223-114">Auf der Registerkarte **Hierarchieelemente** verfügt der Unterkategorieknoten "Mountain Bikes" in einer abgeleiteten Hierarchie über die zugewiesene Berechtigung **Aktualisieren** .</span><span class="sxs-lookup"><span data-stu-id="a6223-114">On the **Hierarchy Members** tab, the Mountain Bikes subcategory node in a derived hierarchy has **Update** permission assigned.</span></span>  
  
 <span data-ttu-id="a6223-115">Ergebnis: In **Explorer**verfügt der Benutzer über die Berechtigung **Aktualisieren** für alle Attributwerte für alle Elemente im Knoten "Mountain Bikes".</span><span class="sxs-lookup"><span data-stu-id="a6223-115">Result: In **Explorer**, the user has **Update** permission to all attribute values for all members in the Mountain Bikes node.</span></span> <span data-ttu-id="a6223-116">Alle anderen Elemente und Attribute werden ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="a6223-116">All other members and attributes are hidden.</span></span>  
  
 <span data-ttu-id="a6223-117">![mds_conc_overlap_model_example_1](../../2014/master-data-services/media/mds-conc-overlap-model-example-1.gif "mds_conc_overlap_model_example_1")</span><span class="sxs-lookup"><span data-stu-id="a6223-117">![mds_conc_overlap_model_example_1](../../2014/master-data-services/media/mds-conc-overlap-model-example-1.gif "mds_conc_overlap_model_example_1")</span></span>  
  
## <a name="example-2"></a><span data-ttu-id="a6223-118">Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="a6223-118">Example 2</span></span>  
 <span data-ttu-id="a6223-119">![mds_conc_overlap_model_2](../../2014/master-data-services/media/mds-conc-overlap-model-2.gif "mds_conc_overlap_model_2")</span><span class="sxs-lookup"><span data-stu-id="a6223-119">![mds_conc_overlap_model_2](../../2014/master-data-services/media/mds-conc-overlap-model-2.gif "mds_conc_overlap_model_2")</span></span>  
  
 <span data-ttu-id="a6223-120">Auf der Registerkarte **Modelle** verfügt das Subcategory-Attribut über die zugewiesene Berechtigung **Aktualisieren** .</span><span class="sxs-lookup"><span data-stu-id="a6223-120">On the **Models** tab, the Subcategory attribute has **Update** permission assigned.</span></span>  
  
 <span data-ttu-id="a6223-121">Auf der Registerkarte **Hierarchie** Elemente wird dem Knoten Unterkategorie "Mountain Bikes" in einer abgeleiteten Hierarchie **die Berechtigung "** schreibgeschützt" explizit zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="a6223-121">On the **Hierarchy Members** tab, the Mountain Bikes subcategory node in a derived hierarchy is explicitly assigned **Read-only** permission.</span></span>  
  
 <span data-ttu-id="a6223-122">Ergebnis: in **Explorer**verfügt der Benutzer über die **Lese** Berechtigung für die SubCategory-Attributwerte für die Elemente im Knoten "Mountain Bikes".</span><span class="sxs-lookup"><span data-stu-id="a6223-122">Result: In **Explorer**, the user has **Read-only** permission to the Subcategory attribute values for the members in the Mountain Bikes node.</span></span> <span data-ttu-id="a6223-123">Alle anderen Elemente und Attribute werden ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="a6223-123">All other members and attributes are hidden.</span></span>  
  
 <span data-ttu-id="a6223-124">![mds_conc_overlap_model_example_2](../../2014/master-data-services/media/mds-conc-overlap-model-example-2.gif "mds_conc_overlap_model_example_2")</span><span class="sxs-lookup"><span data-stu-id="a6223-124">![mds_conc_overlap_model_example_2](../../2014/master-data-services/media/mds-conc-overlap-model-example-2.gif "mds_conc_overlap_model_example_2")</span></span>  
  
## <a name="example-3"></a><span data-ttu-id="a6223-125">Beispiel 3</span><span class="sxs-lookup"><span data-stu-id="a6223-125">Example 3</span></span>  
 <span data-ttu-id="a6223-126">![mds_conc_overlap_model_3](../../2014/master-data-services/media/mds-conc-overlap-model-3.gif "mds_conc_overlap_model_3")</span><span class="sxs-lookup"><span data-stu-id="a6223-126">![mds_conc_overlap_model_3](../../2014/master-data-services/media/mds-conc-overlap-model-3.gif "mds_conc_overlap_model_3")</span></span>  
  
 <span data-ttu-id="a6223-127">Auf der Registerkarte **Modelle** verfügt das Subcategory-Attribut über die zugewiesene **Lese** Berechtigung.</span><span class="sxs-lookup"><span data-stu-id="a6223-127">On the **Models** tab, the Subcategory attribute has **Read-only** permission assigned.</span></span>  
  
 <span data-ttu-id="a6223-128">Auf der Registerkarte **Hierarchieelemente** wird der Unterkategorie "Mountain Bikes" in einer abgeleiteten Hierarchie die Berechtigung **Aktualisieren** explizit zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="a6223-128">On the **Hierarchy Members** tab, the Mountain Bikes subcategory in a derived hierarchy is explicitly assigned **Update** permission.</span></span>  
  
 <span data-ttu-id="a6223-129">Ergebnis: in **Explorer**verfügt der Benutzer über die **Lese** Berechtigung für die Attributwerte.</span><span class="sxs-lookup"><span data-stu-id="a6223-129">Result: In **Explorer**, the user has **Read-only** permission to the attribute values.</span></span> <span data-ttu-id="a6223-130">Alle anderen Elemente und Attribute werden ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="a6223-130">All other members and attributes are hidden.</span></span>  
  
 <span data-ttu-id="a6223-131">![mds_conc_overlap_model_example_2](../../2014/master-data-services/media/mds-conc-overlap-model-example-2.gif "mds_conc_overlap_model_example_2")</span><span class="sxs-lookup"><span data-stu-id="a6223-131">![mds_conc_overlap_model_example_2](../../2014/master-data-services/media/mds-conc-overlap-model-example-2.gif "mds_conc_overlap_model_example_2")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6223-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a6223-132">See Also</span></span>  
 <span data-ttu-id="a6223-133">[Wie Berechtigungen &#40;Master Data Services bestimmt werden&#41;](how-permissions-are-determined-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="a6223-133">[How Permissions Are Determined &#40;Master Data Services&#41;](how-permissions-are-determined-master-data-services.md) </span></span>  
 [<span data-ttu-id="a6223-134">Überlappende Benutzer- und Gruppenberechtigungen &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="a6223-134">Overlapping User and Group Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/overlapping-user-and-group-permissions-master-data-services.md)  
  
  
