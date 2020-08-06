---
title: Elemente (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- leaf members [Master Data Services]
- consolidated members [Master Data Services]
- consolidated members [Master Data Services], about consolidated members
- members [Master Data Services], about members
- leaf members [Master Data Services], about leaf members
- members [Master Data Services]
ms.assetid: 0fda32b9-677d-4ba2-bb28-f76f2383a30f
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 89d2edb21b58575dffc21d9a6470171251889cc0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698414"
---
# <a name="members-master-data-services"></a><span data-ttu-id="6aa0e-102">Elemente (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="6aa0e-102">Members (Master Data Services)</span></span>
  <span data-ttu-id="6aa0e-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]sind Elemente die physischen Masterdaten.</span><span class="sxs-lookup"><span data-stu-id="6aa0e-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], members are the physical master data.</span></span> <span data-ttu-id="6aa0e-104">Ein Element kann z. B. ein Fahrrad mit der Modellbezeichnung Road-150 in einer Product-Entität oder ein bestimmter Kunde in einer Customer-Entität sein.</span><span class="sxs-lookup"><span data-stu-id="6aa0e-104">For example, a member can be a Road-150 bike in a Product entity or a specific customer in a Customer entity.</span></span>

## <a name="how-members-relate-to-other-model-objects"></a><span data-ttu-id="6aa0e-105">Zusammenhang zwischen Elementen und anderen Modellobjekten</span><span class="sxs-lookup"><span data-stu-id="6aa0e-105">How Members Relate to Other Model Objects</span></span>
 <span data-ttu-id="6aa0e-106">Sie können sich Elemente als Zeilen in einer Tabelle vorstellen.</span><span class="sxs-lookup"><span data-stu-id="6aa0e-106">You can think of members as rows in a table.</span></span> <span data-ttu-id="6aa0e-107">Verwandte Elemente sind in einer Entität enthalten, und jedes Element wird von Attributwerten definiert.</span><span class="sxs-lookup"><span data-stu-id="6aa0e-107">Related members are contained in an entity, and each member is defined by attribute values.</span></span>

 <span data-ttu-id="6aa0e-108">In diesem Beispiel stellt die Tabelle eine Entität, die Zeilen in der Tabelle die Elemente und die Spalten in der Tabelle die Attribute dar.</span><span class="sxs-lookup"><span data-stu-id="6aa0e-108">In this example, the table represents an entity, the rows in the table represent members, and the columns in the table represent attributes.</span></span> <span data-ttu-id="6aa0e-109">Jede Zelle stellt einen Attributwert für ein bestimmtes Element dar.</span><span class="sxs-lookup"><span data-stu-id="6aa0e-109">Each cell represents an attribute value for a specific member.</span></span>

 <span data-ttu-id="6aa0e-110">![Als Tabelle dargestellte Master Data Services-Entität](../../2014/master-data-services/media/mds-conc-entity-table.gif "Als Tabelle dargestellte Master Data Services-Entität")</span><span class="sxs-lookup"><span data-stu-id="6aa0e-110">![Master Data Services Entity Represented as Table](../../2014/master-data-services/media/mds-conc-entity-table.gif "Master Data Services Entity Represented as Table")</span></span>

## <a name="member-types"></a><span data-ttu-id="6aa0e-111">Elementtypen</span><span class="sxs-lookup"><span data-stu-id="6aa0e-111">Member Types</span></span>
 <span data-ttu-id="6aa0e-112">Es gibt drei Arten von Elementen: Blattelemente, konsolidierte Elemente und Sammlungselemente.</span><span class="sxs-lookup"><span data-stu-id="6aa0e-112">There are three types of members: leaf members, consolidated members, and collection members.</span></span>

 <span data-ttu-id="6aa0e-113">Blattelemente sind die Standardelemente in einer Entität.</span><span class="sxs-lookup"><span data-stu-id="6aa0e-113">Leaf members are the default members in an entity.</span></span>

-   <span data-ttu-id="6aa0e-114">In abgeleiteten Hierarchien sind Blattelemente der einzige Typ des Elements.</span><span class="sxs-lookup"><span data-stu-id="6aa0e-114">In derived hierarchies, leaf members are the only type of member.</span></span> <span data-ttu-id="6aa0e-115">Blattelemente aus einer Entität werden als übergeordnete Elemente der Blattelemente aus einer anderen Entität verwendet.</span><span class="sxs-lookup"><span data-stu-id="6aa0e-115">Leaf members from one entity are used as parents of leaf members from another entity.</span></span>

-   <span data-ttu-id="6aa0e-116">In expliziten Hierarchien sind Blattelemente die niedrigste Ebene und können nicht über untergeordnete Elemente verfügen.</span><span class="sxs-lookup"><span data-stu-id="6aa0e-116">In explicit hierarchies, leaf members are the lowest level and cannot have children.</span></span>

 <span data-ttu-id="6aa0e-117">Konsolidierte Elemente sind nur vorhanden, wenn explizite Hierarchien und Auflistungen für die Entität aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="6aa0e-117">Consolidated members exist only when explicit hierarchies and collections are enabled for the entity.</span></span>

-   <span data-ttu-id="6aa0e-118">Abgeleitete Hierarchien enthalten keine konsolidierten Elemente.</span><span class="sxs-lookup"><span data-stu-id="6aa0e-118">Derived hierarchies do not contain consolidated members.</span></span>

-   <span data-ttu-id="6aa0e-119">In expliziten Hierarchien können konsolidierte Elemente übergeordnete Elemente anderer Elemente innerhalb der Hierarchie sein, oder sie können untergeordnete Elemente sein.</span><span class="sxs-lookup"><span data-stu-id="6aa0e-119">In explicit hierarchies, consolidated members can be parents of other members within the hierarchy, or they can be children.</span></span>

## <a name="use-hierarchies-and-collections-to-organize-members"></a><span data-ttu-id="6aa0e-120">Organisieren von Elementen mithilfe von Hierarchien und Auflistungen</span><span class="sxs-lookup"><span data-stu-id="6aa0e-120">Use Hierarchies and Collections to Organize Members</span></span>
 <span data-ttu-id="6aa0e-121">Hierarchien und Auflistungen können verwendet werden, um Elemente für die Berichterstellung oder Analyse zu gruppieren.</span><span class="sxs-lookup"><span data-stu-id="6aa0e-121">Hierarchies and collections can be used to group members for reporting or analysis.</span></span> <span data-ttu-id="6aa0e-122">Weitere Informationen finden Sie unter [Hierarchien &#40;Master Data Services&#41;](hierarchies-master-data-services.md) und [Sammlungen &#40;Master Data Services&#41;](../../2014/master-data-services/collections-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="6aa0e-122">For more information, see [Hierarchies &#40;Master Data Services&#41;](hierarchies-master-data-services.md) and [Collections &#40;Master Data Services&#41;](../../2014/master-data-services/collections-master-data-services.md).</span></span>

## <a name="member-example"></a><span data-ttu-id="6aa0e-123">Beispiel für ein Element</span><span class="sxs-lookup"><span data-stu-id="6aa0e-123">Member Example</span></span>
 <span data-ttu-id="6aa0e-124">Im folgenden Beispiel schließt jedes Element einen Attributwert Name, Code, Subcategory StandardCost, ListPrice und FilePhoto ein.</span><span class="sxs-lookup"><span data-stu-id="6aa0e-124">In the following example, each member is made up of a Name, Code, Subcategory, StandardCost, ListPrice, and FilePhoto attribute value.</span></span>

 <span data-ttu-id="6aa0e-125">![Entitätstabelle für Fahrradprodukte](../../2014/master-data-services/media/mds-conc-entity-table-w-data.gif "Entitätstabelle für Fahrradprodukte")</span><span class="sxs-lookup"><span data-stu-id="6aa0e-125">![Bike Product Entity Table](../../2014/master-data-services/media/mds-conc-entity-table-w-data.gif "Bike Product Entity Table")</span></span>

## <a name="related-tasks"></a><span data-ttu-id="6aa0e-126">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="6aa0e-126">Related Tasks</span></span>

|<span data-ttu-id="6aa0e-127">Taskbeschreibung</span><span class="sxs-lookup"><span data-stu-id="6aa0e-127">Task Description</span></span>|<span data-ttu-id="6aa0e-128">Thema</span><span class="sxs-lookup"><span data-stu-id="6aa0e-128">Topic</span></span>|
|----------------------|-----------|
|<span data-ttu-id="6aa0e-129">Erstellen Sie ein Blattelement.</span><span class="sxs-lookup"><span data-stu-id="6aa0e-129">Create a new leaf member.</span></span>|[<span data-ttu-id="6aa0e-130">Erstellen eines Blattelements &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="6aa0e-130">Create a Leaf Member &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-leaf-member-master-data-services.md)|
|<span data-ttu-id="6aa0e-131">Erstellen Sie ein neues konsolidiertes Element.</span><span class="sxs-lookup"><span data-stu-id="6aa0e-131">Create a new consolidated member.</span></span>|[<span data-ttu-id="6aa0e-132">Erstellen eines konsolidierten Elements &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="6aa0e-132">Create a Consolidated Member &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-consolidated-member-master-data-services.md)|
|<span data-ttu-id="6aa0e-133">Löschen Sie ein vorhandenes Element oder eine Auflistung.</span><span class="sxs-lookup"><span data-stu-id="6aa0e-133">Delete an existing member or collection.</span></span>|[<span data-ttu-id="6aa0e-134">Löschen eines Elements oder einer Sammlung &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="6aa0e-134">Delete a Member or Collection &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/delete-a-member-or-collection-master-data-services.md)|
|<span data-ttu-id="6aa0e-135">Reaktivieren Sie ein gelöschtes Element oder eine Auflistung.</span><span class="sxs-lookup"><span data-stu-id="6aa0e-135">Reactivate a deleted member or collection.</span></span>|[<span data-ttu-id="6aa0e-136">Reaktivieren eines Elements oder einer Sammlung &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="6aa0e-136">Reactivate a Member or Collection &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/reactivate-a-member-or-collection-master-data-services.md)|
|<span data-ttu-id="6aa0e-137">Aktualisieren Sie die Attributwerte eines Elements.</span><span class="sxs-lookup"><span data-stu-id="6aa0e-137">Update the attribute values of a member.</span></span>|[<span data-ttu-id="6aa0e-138">Ändern des Attributtyps &#40;MDS-Add-In für Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="6aa0e-138">Change the Attribute Type &#40;MDS Add-in for Excel&#41;</span></span>](microsoft-excel-add-in/change-the-attribute-type-mds-add-in-for-excel.md)|
|<span data-ttu-id="6aa0e-139">Verschieben Sie Elemente innerhalb einer Hierarchie.</span><span class="sxs-lookup"><span data-stu-id="6aa0e-139">Move members within a hierarchy.</span></span>|[<span data-ttu-id="6aa0e-140">Verschieben von Elementen innerhalb einer Hierarchie &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="6aa0e-140">Move Members within a Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/move-members-within-a-hierarchy-master-data-services.md)|

## <a name="related-content"></a><span data-ttu-id="6aa0e-141">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="6aa0e-141">Related Content</span></span>

-   [<span data-ttu-id="6aa0e-142">Übersicht über Master Data Services</span><span class="sxs-lookup"><span data-stu-id="6aa0e-142">Master Data Services Overview</span></span>](master-data-services-overview-mds.md)

-   [<span data-ttu-id="6aa0e-143">Entitäten &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="6aa0e-143">Entities &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/entities-master-data-services.md)

-   [<span data-ttu-id="6aa0e-144">Attribute &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="6aa0e-144">Attributes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/attributes-master-data-services.md)

-   [<span data-ttu-id="6aa0e-145">Hierarchien &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="6aa0e-145">Hierarchies &#40;Master Data Services&#41;</span></span>](hierarchies-master-data-services.md)

-   [<span data-ttu-id="6aa0e-146">Sammlungen &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="6aa0e-146">Collections &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/collections-master-data-services.md)

-   [<span data-ttu-id="6aa0e-147">Blattberechtigungen &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="6aa0e-147">Leaf Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/leaf-permissions-master-data-services.md)

-   [<span data-ttu-id="6aa0e-148">Konsolidierte Berechtigungen &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="6aa0e-148">Consolidated Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/consolidated-permissions-master-data-services.md)

-   [<span data-ttu-id="6aa0e-149">Filteroperatoren &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="6aa0e-149">Filter Operators &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/filter-operators-master-data-services.md)


