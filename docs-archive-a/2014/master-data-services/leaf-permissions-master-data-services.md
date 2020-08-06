---
title: Blattberechtigungen (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- attribute groups [Master Data Services], permissions
- members [Master Data Services], leaf member permissions
- permissions [Master Data Services], leaf members
- leaf members [Master Data Services], attribute permissions
- attributes [Master Data Services], leaf member attribute permissions
ms.assetid: bde16e8c-bcd4-4041-8130-55c5450e5f72
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 794e1d138b91e896b8df16765ae8984c6e60aca7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722870"
---
# <a name="leaf-permissions-master-data-services"></a><span data-ttu-id="6080d-102">Blattberechtigungen (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="6080d-102">Leaf Permissions (Master Data Services)</span></span>
  <span data-ttu-id="6080d-103">Blattberechtigungen gelten für die Attributwerte aller Blattelemente einer Entität.</span><span class="sxs-lookup"><span data-stu-id="6080d-103">Leaf permissions apply to the attribute values for all leaf members of an entity.</span></span>  
  
 <span data-ttu-id="6080d-104">Bei Entitäten, für die keine expliziten Hierarchien aktiviert wurden, erfolgen die Zuweisung einer Berechtigung zu einem **Blatt** und die Zuweisung einer Berechtigung zur Entität auf die gleiche Weise.</span><span class="sxs-lookup"><span data-stu-id="6080d-104">For entities without explicit hierarchies enabled, assigning permission to **Leaf** is the same as assigning permission to the entity.</span></span>  
  
 <span data-ttu-id="6080d-105">**Hinweise:**</span><span class="sxs-lookup"><span data-stu-id="6080d-105">**Notes:**</span></span>  
  
-   <span data-ttu-id="6080d-106">Blattberechtigungen gelten nur für den Funktionsbereich **Explorer** der Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="6080d-106">Leaf permissions apply to the **Explorer** functional area of the user interface only.</span></span>  
  
-   <span data-ttu-id="6080d-107">Den Attributen **Name** und **Code** zugewiesene Berechtigungen werden nicht erzwungen.</span><span class="sxs-lookup"><span data-stu-id="6080d-107">Permissions assigned to **Name** and **Code** attributes are not enforced.</span></span>  
  
|<span data-ttu-id="6080d-108">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="6080d-108">Permission</span></span>|<span data-ttu-id="6080d-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6080d-109">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="6080d-110">**Schreibgeschützt**</span><span class="sxs-lookup"><span data-stu-id="6080d-110">**Read-only**</span></span>|<span data-ttu-id="6080d-111">Blattelemente werden zwar angezeigt, können vom Benutzer jedoch nicht hinzufügt, entfernt oder geändert werden.</span><span class="sxs-lookup"><span data-stu-id="6080d-111">Leaf members are displayed but the user cannot add, remove, or change them.</span></span><br /><br /> <span data-ttu-id="6080d-112">Wenn konsolidierte Elemente vorhanden sind, werden die Namen und Codes zwar angezeigt, können vom Benutzer jedoch nicht hinzufügt, entfernt oder geändert werden.</span><span class="sxs-lookup"><span data-stu-id="6080d-112">If consolidated members exist, the names and codes are displayed but the user cannot add, remove, or change them.</span></span>|  
|<span data-ttu-id="6080d-113">**Aktualisieren**</span><span class="sxs-lookup"><span data-stu-id="6080d-113">**Update**</span></span>|<span data-ttu-id="6080d-114">Blattelemente werden angezeigt und können vom Benutzer hinzugefügt, entfernt und geändert werden.</span><span class="sxs-lookup"><span data-stu-id="6080d-114">Leaf members are displayed and the user can add, remove, and change them.</span></span><br /><br /> <span data-ttu-id="6080d-115">Wenn konsolidierte Elemente vorhanden sind, werden die Namen und Codes zwar angezeigt, können vom Benutzer jedoch nicht hinzufügt, entfernt oder geändert werden.</span><span class="sxs-lookup"><span data-stu-id="6080d-115">If consolidated members exist, the names and codes are displayed but the user cannot add, remove, or change them.</span></span>|  
|<span data-ttu-id="6080d-116">**Deny** (Verweigern)</span><span class="sxs-lookup"><span data-stu-id="6080d-116">**Deny**</span></span>|<span data-ttu-id="6080d-117">Blattelemente für die Entität werden nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6080d-117">Leaf members for the entity are not displayed.</span></span>|  
  
## <a name="attribute-permissions"></a><span data-ttu-id="6080d-118">Attributberechtigungen</span><span class="sxs-lookup"><span data-stu-id="6080d-118">Attribute Permissions</span></span>  
 <span data-ttu-id="6080d-119">Attributberechtigungen gelten für die Attributwerte der jeweiligen Entität.</span><span class="sxs-lookup"><span data-stu-id="6080d-119">Attribute permissions apply to the attribute's values for the specific entity.</span></span> <span data-ttu-id="6080d-120">Benutzer mit Attributberechtigungen wird lediglich verweigert, Elemente hinzuzufügen oder zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="6080d-120">Users with attribute permissions only cannot add or remove members.</span></span>  
  
|<span data-ttu-id="6080d-121">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="6080d-121">Permission</span></span>|<span data-ttu-id="6080d-122">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6080d-122">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="6080d-123">**Schreibgeschützt**</span><span class="sxs-lookup"><span data-stu-id="6080d-123">**Read-only**</span></span>|<span data-ttu-id="6080d-124">Das Attribut wird zwar angezeigt, aber der Benutzer kann keine Attributwerte ändern.</span><span class="sxs-lookup"><span data-stu-id="6080d-124">The attribute is displayed but the user cannot change attribute values.</span></span>|  
|<span data-ttu-id="6080d-125">**Aktualisieren**</span><span class="sxs-lookup"><span data-stu-id="6080d-125">**Update**</span></span>|<span data-ttu-id="6080d-126">Das Attribut wird angezeigt, und der Benutzer kann Attributwerte ändern.</span><span class="sxs-lookup"><span data-stu-id="6080d-126">The attribute is displayed and the user can change attribute values.</span></span>|  
|<span data-ttu-id="6080d-127">**Deny** (Verweigern)</span><span class="sxs-lookup"><span data-stu-id="6080d-127">**Deny**</span></span>|<span data-ttu-id="6080d-128">Das Attribut wird nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6080d-128">The attribute is not displayed.</span></span><br /><br /> <span data-ttu-id="6080d-129">Hinweis: Der Zugriff auf die Attribute Name und Code kann nicht explizit verweigert werden.</span><span class="sxs-lookup"><span data-stu-id="6080d-129">Note: You cannot explicitly deny access to Name and Code attributes.</span></span>|  
  
### <a name="example"></a><span data-ttu-id="6080d-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6080d-130">Example</span></span>  
 <span data-ttu-id="6080d-131">Weisen Sie dem Attribut „Subcategory“ der Entität „Product“ die Berechtigung **Aktualisieren** zu.</span><span class="sxs-lookup"><span data-stu-id="6080d-131">For the Product entity, assign **Update** permission to Subcategory attribute.</span></span> <span data-ttu-id="6080d-132">Verweigern Sie die Berechtigung für alle anderen Attribute.</span><span class="sxs-lookup"><span data-stu-id="6080d-132">Deny permission to all other attributes.</span></span>  
  
|<span data-ttu-id="6080d-133">Name</span><span class="sxs-lookup"><span data-stu-id="6080d-133">Name</span></span>|<span data-ttu-id="6080d-134">Code</span><span class="sxs-lookup"><span data-stu-id="6080d-134">Code</span></span>|<span data-ttu-id="6080d-135">Subcategory (Aktualisiert)</span><span class="sxs-lookup"><span data-stu-id="6080d-135">Subcategory (Update)</span></span>|  
|----------|----------|----------------------------|  
|<span data-ttu-id="6080d-136">Mountain-100</span><span class="sxs-lookup"><span data-stu-id="6080d-136">Mountain-100</span></span>|<span data-ttu-id="6080d-137">BK-M101</span><span class="sxs-lookup"><span data-stu-id="6080d-137">BK-M101</span></span>|<span data-ttu-id="6080d-138">{5}Mountain Bikes</span><span class="sxs-lookup"><span data-stu-id="6080d-138">{5} Mountain Bikes</span></span>|  
|<span data-ttu-id="6080d-139">Mountain-100</span><span class="sxs-lookup"><span data-stu-id="6080d-139">Mountain-100</span></span>|<span data-ttu-id="6080d-140">BK-M201</span><span class="sxs-lookup"><span data-stu-id="6080d-140">BK-M201</span></span>|<span data-ttu-id="6080d-141">{5}Mountain Bikes</span><span class="sxs-lookup"><span data-stu-id="6080d-141">{5} Mountain Bikes</span></span>|  
  
 <span data-ttu-id="6080d-142">Sie können im **Explorer**jeden Attributwert in der Spalte „Subcategory“ aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="6080d-142">In **Explorer**, you can update any attribute value in the Subcategory column.</span></span> <span data-ttu-id="6080d-143">Wenn Sie keine Berechtigung für ein Attribut haben, wird das Attribut nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6080d-143">If you do not have permission to an attribute, the attribute is not displayed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6080d-144">In diesem Beispiel ist Subcategory ein domänenbasiertes Attribut, das auf der SubcategoryList-Entität basiert.</span><span class="sxs-lookup"><span data-stu-id="6080d-144">In this example, Subcategory is a domain-based attribute, based on the SubcategoryList entity.</span></span> <span data-ttu-id="6080d-145">Sie können eine andere Unterkategorie für Mountain-100 auswählen, der SubcategoryList-Entität jedoch keine Elemente hinzufügen bzw. Elemente aus dieser Entität löschen.</span><span class="sxs-lookup"><span data-stu-id="6080d-145">You can select a different subcategory for Mountain-100 but you cannot add members to or delete members from the SubcategoryList entity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6080d-146">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6080d-146">See Also</span></span>  
 <span data-ttu-id="6080d-147">[Zuweisen von Berechtigungen für Modell Objekte &#40;Master Data Services&#41;](assign-model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="6080d-147">[Assign Model Object Permissions &#40;Master Data Services&#41;](assign-model-object-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="6080d-148">[Konsolidierte Berechtigungen &#40;Master Data Services&#41;](../../2014/master-data-services/consolidated-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="6080d-148">[Consolidated Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/consolidated-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="6080d-149">[Modell Objekt Berechtigungen &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="6080d-149">[Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="6080d-150">[Mitglieder &#40;Master Data Services&#41;](../../2014/master-data-services/members-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="6080d-150">[Members &#40;Master Data Services&#41;](../../2014/master-data-services/members-master-data-services.md) </span></span>  
 [<span data-ttu-id="6080d-151">Attribute &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="6080d-151">Attributes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/attributes-master-data-services.md)  
  
  
