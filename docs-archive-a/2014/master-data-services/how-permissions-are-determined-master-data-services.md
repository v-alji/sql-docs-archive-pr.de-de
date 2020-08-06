---
title: 'Vorgehensweise: Festlegen von Berechtigungen (Master Data Services) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- permissions [Master Data Services], determining permissions
ms.assetid: 1dc0b43a-d023-4e7d-b027-8b1459fd058c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 3ea3306b772224bc8602659c7e17e8dc1634f0d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619178"
---
# <a name="how-permissions-are-determined-master-data-services"></a><span data-ttu-id="46eb1-102">Vorgehensweise: Festlegen von Berechtigungen (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="46eb1-102">How Permissions Are Determined (Master Data Services)</span></span>
  <span data-ttu-id="46eb1-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]ist die einfachste Methode zum Konfigurieren der Sicherheit, Modellobjektberechtigungen einer Gruppe zuzuweisen, deren Mitglied der Benutzer ist.</span><span class="sxs-lookup"><span data-stu-id="46eb1-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], the simplest way to configure security is to assign model object permissions to a group that the user is a member of.</span></span>

 <span data-ttu-id="46eb1-104">Die Sicherheit wird komplexer, wenn:</span><span class="sxs-lookup"><span data-stu-id="46eb1-104">Security becomes more complex when:</span></span>

-   <span data-ttu-id="46eb1-105">Modellobjekt- und Hierarchieelementberechtigungen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="46eb1-105">Both model object and hierarchy member permissions are assigned.</span></span>

-   <span data-ttu-id="46eb1-106">Der Benutzer Gruppen angehört und die Berechtigung dem Benutzer und Gruppen zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="46eb1-106">The user belongs to groups and permission is assigned to both the user and groups.</span></span>

-   <span data-ttu-id="46eb1-107">Der Benutzer Gruppen angehört und die Berechtigung mehreren Gruppen zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="46eb1-107">The user belongs to groups and permission is assigned to multiple groups.</span></span>

## <a name="permissions-assigned-to-a-single-group-or-user"></a><span data-ttu-id="46eb1-108">Einer einzelnen Gruppe oder einem Benutzer zugewiesene Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="46eb1-108">Permissions assigned to a single group or user</span></span>
 <span data-ttu-id="46eb1-109">Wenn Sie Berechtigungen einer einzelnen Gruppe oder einem Benutzer zuweisen, werden Berechtigungen gemäß dem folgenden Workflow festgelegt.</span><span class="sxs-lookup"><span data-stu-id="46eb1-109">If you assign permissions to a single group or user, permissions are determined based on the following workflow.</span></span>

 <span data-ttu-id="46eb1-110">![mds_conc_security_no_overlap](../../2014/master-data-services/media/mds-conc-security-no-overlap.gif "mds_conc_security_no_overlap")</span><span class="sxs-lookup"><span data-stu-id="46eb1-110">![mds_conc_security_no_overlap](../../2014/master-data-services/media/mds-conc-security-no-overlap.gif "mds_conc_security_no_overlap")</span></span>

### <a name="step-1-effective-attribute-permissions-are-determined"></a><span data-ttu-id="46eb1-111">Schritt 1: Effektive Attributberechtigungen werden festgelegt.</span><span class="sxs-lookup"><span data-stu-id="46eb1-111">Step 1: Effective attribute permissions are determined.</span></span>
 <span data-ttu-id="46eb1-112">Die folgende Liste beschreibt, wie effektive Attributberechtigungen festgelegt werden:</span><span class="sxs-lookup"><span data-stu-id="46eb1-112">The following list describes how effective attribute permissions are determined:</span></span>

-   <span data-ttu-id="46eb1-113">Modellobjekten zugewiesene Berechtigungen legen fest, auf welche Attribute ein Benutzer zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="46eb1-113">Permissions assigned to model objects determine which attributes a user can access.</span></span>

-   <span data-ttu-id="46eb1-114">Von allen Modellobjekten wird die Berechtigung automatisch vom nächst gelegenen Objekt auf einer höheren Ebene in der Modellstruktur geerbt.</span><span class="sxs-lookup"><span data-stu-id="46eb1-114">All model objects automatically inherit permission from the closest object at a higher level in the model structure.</span></span>

-   <span data-ttu-id="46eb1-115">Objekte auf derselben Ebene wie die Entität werden implizit verweigert.</span><span class="sxs-lookup"><span data-stu-id="46eb1-115">Any objects at the same level as the entity are implicitly denied.</span></span>

-   <span data-ttu-id="46eb1-116">Objekten auf einer höheren Ebene wird Navigationszugriff gewährt.</span><span class="sxs-lookup"><span data-stu-id="46eb1-116">Any objects at a higher level are given navigational access.</span></span> <span data-ttu-id="46eb1-117">Weitere Informationen zu navigationaccess finden Sie unter [Navigations Zugriff &#40;Master Data Services&#41;](navigational-access-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="46eb1-117">For more information about navigational access, see [Navigational Access &#40;Master Data Services&#41;](navigational-access-master-data-services.md).</span></span>

 <span data-ttu-id="46eb1-118">In diesem Beispiel wird einer Entität **die Berechtigung "** schreibgeschützt" zugewiesen, und diese Berechtigung wird von Ihrem Attribut geerbt, das sich auf einer niedrigeren Ebene in der Modellstruktur befindet.</span><span class="sxs-lookup"><span data-stu-id="46eb1-118">In this example, **Read-only** permission is assigned to an entity and that permission is inherited by its attribute, which is at a lower level in the model structure.</span></span> <span data-ttu-id="46eb1-119">Das Modell bietet Navigationszugriff auf diese Entität und ihr Attribut.</span><span class="sxs-lookup"><span data-stu-id="46eb1-119">The model provides navigational access to this entity and its attribute.</span></span> <span data-ttu-id="46eb1-120">Der anderen Entität im Modell wurde keine explizite Berechtigung zugewiesen, und von ihr werden keine Berechtigungen geerbt. Sie wird daher implizit verweigert.</span><span class="sxs-lookup"><span data-stu-id="46eb1-120">The other entity in the model has no explicit permission assigned and does not inherit any permissions, so it is implicitly denied.</span></span>

 <span data-ttu-id="46eb1-121">![mds_conc_inheritance_model](../../2014/master-data-services/media/mds-conc-inheritance-model.gif "mds_conc_inheritance_model")</span><span class="sxs-lookup"><span data-stu-id="46eb1-121">![mds_conc_inheritance_model](../../2014/master-data-services/media/mds-conc-inheritance-model.gif "mds_conc_inheritance_model")</span></span>

### <a name="step-2-if-hierarchy-member-permissions-are-assigned-effective-member-permissions-are-determined"></a><span data-ttu-id="46eb1-122">Schritt 2: Wenn Hierarchieelementberechtigungen zugewiesen werden, werden effektive Elementberechtigungen festgelegt.</span><span class="sxs-lookup"><span data-stu-id="46eb1-122">Step 2: If hierarchy member permissions are assigned, effective member permissions are determined.</span></span>
 <span data-ttu-id="46eb1-123">Die folgende Liste beschreibt, wie effektive Hierarchieelementberechtigungen festgelegt werden:</span><span class="sxs-lookup"><span data-stu-id="46eb1-123">The following list describes how effective hierarchy member permissions are determined:</span></span>

-   <span data-ttu-id="46eb1-124">Hierarchieknoten zugewiesene Berechtigungen legen fest, auf welche Elemente ein Benutzer zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="46eb1-124">Permissions assigned to hierarchy nodes determine which members a user can access.</span></span>

-   <span data-ttu-id="46eb1-125">Von allen Knoten in einer Hierarchie wird die Berechtigung automatisch vom nächst gelegenen Objekt auf einer höheren Ebene in der Hierarchiestruktur geerbt.</span><span class="sxs-lookup"><span data-stu-id="46eb1-125">All nodes in a hierarchy automatically inherit permission from the closest object at a higher level in the hierarchy structure.</span></span>

-   <span data-ttu-id="46eb1-126">Alle Knoten auf derselben Ebene werden implizit verweigert.</span><span class="sxs-lookup"><span data-stu-id="46eb1-126">Any nodes at the same level are implicitly denied.</span></span>

-   <span data-ttu-id="46eb1-127">Alle Knoten auf höheren Ebenen, denen keine Berechtigungen zugewiesen wurden, werden implizit verweigert.</span><span class="sxs-lookup"><span data-stu-id="46eb1-127">Any nodes at higher levels that do not have permissions assigned are implicitly denied.</span></span>

 <span data-ttu-id="46eb1-128">In diesem Beispiel wird einem Knoten der Hierarchie **die Berechtigung schreibgeschützt zugewiesen, und** diese Berechtigung wird von einem Knoten auf einer niedrigeren Ebene in der Hierarchiestruktur geerbt.</span><span class="sxs-lookup"><span data-stu-id="46eb1-128">In this example, **Read-only** permission is assigned to one node of the hierarchy and that permission is inherited by a node at a lower level in the hierarchy structure.</span></span> <span data-ttu-id="46eb1-129">Dem Stamm wurde keine Berechtigung zugewiesen, er wird daher implizit verweigert.</span><span class="sxs-lookup"><span data-stu-id="46eb1-129">The root has no permission assigned, so it is implicitly denied.</span></span> <span data-ttu-id="46eb1-130">Dem anderen Knoten in der Hierarchiestruktur wurde keine explizite Berechtigung zugewiesen, und von ihm werden keine Berechtigungen geerbt. Er wird daher implizit verweigert.</span><span class="sxs-lookup"><span data-stu-id="46eb1-130">The other node in the hierarchy structure has no explicit permission assigned and does not inherit any permissions, so it is implicitly denied.</span></span>

 <span data-ttu-id="46eb1-131">![mds_conc_inheritance_hierarchy](../../2014/master-data-services/media/mds-conc-inheritance-hierarchy.gif "mds_conc_inheritance_hierarchy")</span><span class="sxs-lookup"><span data-stu-id="46eb1-131">![mds_conc_inheritance_hierarchy](../../2014/master-data-services/media/mds-conc-inheritance-hierarchy.gif "mds_conc_inheritance_hierarchy")</span></span>

### <a name="step-3-the-intersection-of-attribute-and-member-permissions-is-determined"></a><span data-ttu-id="46eb1-132">Schritt 3: Die Schnittmenge von Attribut- und Elementberechtigungen wird bestimmt.</span><span class="sxs-lookup"><span data-stu-id="46eb1-132">Step 3: The intersection of attribute and member permissions is determined.</span></span>
 <span data-ttu-id="46eb1-133">Wenn sich die effektiven Attributberechtigungen von den effektiven Elementberechtigungen unterscheiden, müssen Berechtigungen für jeden einzelnen Attributwert festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="46eb1-133">If the effective attribute permissions are different than the effective member permissions, permissions must be determined for each individual attribute value.</span></span> <span data-ttu-id="46eb1-134">Weitere Informationen finden Sie unter [Überlappende Modell- und Elementberechtigungen &#40;Master Data Services&#41;](../../2014/master-data-services/overlapping-model-and-member-permissions-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="46eb1-134">For more information, see [Overlapping Model and Member Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/overlapping-model-and-member-permissions-master-data-services.md).</span></span>

## <a name="permissions-assigned-to-multiple-groups"></a><span data-ttu-id="46eb1-135">Mehreren Gruppen zugewiesene Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="46eb1-135">Permissions assigned to multiple groups</span></span>
 <span data-ttu-id="46eb1-136">Wenn ein Benutzer einer oder mehreren Gruppen angehört und Berechtigungen dem Benutzer und den Gruppen zugewiesen werden, wird der Workflow komplexer.</span><span class="sxs-lookup"><span data-stu-id="46eb1-136">If a user belongs to one or more groups and permissions are assigned to both the user and the groups, the workflow becomes more complex.</span></span>

 <span data-ttu-id="46eb1-137">![mds_conc_security_group_overlap](../../2014/master-data-services/media/mds-conc-security-group-overlap.gif "mds_conc_security_group_overlap")</span><span class="sxs-lookup"><span data-stu-id="46eb1-137">![mds_conc_security_group_overlap](../../2014/master-data-services/media/mds-conc-security-group-overlap.gif "mds_conc_security_group_overlap")</span></span>

 <span data-ttu-id="46eb1-138">In diesem Fall müssen überlappende Benutzer- und Gruppenberechtigungen aufgelöst werden, bevor Modellobjekt- und Hierarchieelementberechtigungen verglichen werden können.</span><span class="sxs-lookup"><span data-stu-id="46eb1-138">In this case, overlapping user and group permissions must be resolved before model object and hierarchy member permissions can be compared.</span></span> <span data-ttu-id="46eb1-139">Weitere Informationen finden Sie unter [Überlappende Benutzer- und Gruppenberechtigungen &#40;Master Data Services&#41;](../../2014/master-data-services/overlapping-user-and-group-permissions-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="46eb1-139">For more information, see [Overlapping User and Group Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/overlapping-user-and-group-permissions-master-data-services.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="46eb1-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="46eb1-140">See Also</span></span>
 <span data-ttu-id="46eb1-141">Über [Lapp Ende Benutzer-und Gruppenberechtigungen &#40;Master Data Services&#41;](../../2014/master-data-services/overlapping-user-and-group-permissions-master-data-services.md) über [Lapp enden Modell-und Element Berechtigungen &#40;Master Data Services&#41;](../../2014/master-data-services/overlapping-model-and-member-permissions-master-data-services.md)</span><span class="sxs-lookup"><span data-stu-id="46eb1-141">[Overlapping User and Group Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/overlapping-user-and-group-permissions-master-data-services.md) [Overlapping Model and Member Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/overlapping-model-and-member-permissions-master-data-services.md)</span></span>


