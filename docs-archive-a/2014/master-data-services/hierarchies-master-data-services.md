---
title: Hierarchien (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- hierarchies [Master Data Services]
- hierarchies [Master Data Services], about hierarchies
ms.assetid: 70dbb1fc-ead7-45be-9552-a45e3ccd8d21
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 126a01c03134c6859426c09fda398408694795f5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619182"
---
# <a name="hierarchies-master-data-services"></a><span data-ttu-id="2bf38-102">Hierarchien (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="2bf38-102">Hierarchies (Master Data Services)</span></span>
  <span data-ttu-id="2bf38-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]ist eine Hierarchie eine Baumstruktur, die Sie für folgende Zwecke verwenden können:</span><span class="sxs-lookup"><span data-stu-id="2bf38-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], a hierarchy is a tree structure that you can use to:</span></span>

-   <span data-ttu-id="2bf38-104">Gruppieren ähnlicher Elemente zu organisatorischen Zwecken</span><span class="sxs-lookup"><span data-stu-id="2bf38-104">Group similar members for organizational purposes.</span></span>

-   <span data-ttu-id="2bf38-105">Konsolidieren und Zusammenfassen von Elementen zu Berichts- und Analysezwecken</span><span class="sxs-lookup"><span data-stu-id="2bf38-105">Consolidate and summarize members for reporting and analysis.</span></span>

## <a name="what-hierarchies-contain"></a><span data-ttu-id="2bf38-106">Inhalt von Hierarchien</span><span class="sxs-lookup"><span data-stu-id="2bf38-106">What Hierarchies Contain</span></span>
 <span data-ttu-id="2bf38-107">Jede Hierarchie enthält Elemente aus einer oder mehreren Entitäten.</span><span class="sxs-lookup"><span data-stu-id="2bf38-107">Each hierarchy contains members from one or more entities.</span></span> <span data-ttu-id="2bf38-108">Wenn ein Element hinzugefügt, geändert oder gelöscht wird, werden alle Hierarchien aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="2bf38-108">When a member is added, changed, or deleted, all hierarchies are updated.</span></span> <span data-ttu-id="2bf38-109">Dadurch wird sichergestellt, dass die Daten in allen Hierarchien exakt sind.</span><span class="sxs-lookup"><span data-stu-id="2bf38-109">This ensures that the data is accurate in all hierarchies.</span></span> <span data-ttu-id="2bf38-110">Mit Hierarchien wird zudem sichergestellt, dass jedes Element genau einmal gezählt wird.</span><span class="sxs-lookup"><span data-stu-id="2bf38-110">Hierarchies also help ensure that each member is counted once and only once.</span></span>

 <span data-ttu-id="2bf38-111">Wenn Sie eine Gruppierung einer Teilmenge von Elementen erstellen möchten, erwägen Sie die Verwendung einer Auflistung.</span><span class="sxs-lookup"><span data-stu-id="2bf38-111">If you want to create a grouping of a subset of members, consider using a collection.</span></span> <span data-ttu-id="2bf38-112">Weitere Informationen finden Sie unter [Sammlungen &#40;Master Data Services&#41;](collections-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="2bf38-112">For more information, see [Collections &#40;Master Data Services&#41;](collections-master-data-services.md).</span></span>

## <a name="kinds-of-hierarchies"></a><span data-ttu-id="2bf38-113">Arten von Hierarchien</span><span class="sxs-lookup"><span data-stu-id="2bf38-113">Kinds of Hierarchies</span></span>
 <span data-ttu-id="2bf38-114">Sie können mehrere Hierarchien erstellen, um Elemente auf verschiedene Weisen anzuzeigen und zu organisieren.</span><span class="sxs-lookup"><span data-stu-id="2bf38-114">You can create multiple hierarchies to view and organize your members in different ways.</span></span> <span data-ttu-id="2bf38-115">Sie können Folgendes erstellen:</span><span class="sxs-lookup"><span data-stu-id="2bf38-115">You can create:</span></span>

-   <span data-ttu-id="2bf38-116">Unregelmäßige Hierarchien für eine einzelne Entität, als explizite Hierarchien bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="2bf38-116">Ragged hierarchies from a single entity, which are called explicit hierarchies.</span></span> <span data-ttu-id="2bf38-117">Weitere Informationen finden Sie unter [Explizite Hierarchien &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="2bf38-117">For more information, see [Explicit Hierarchies &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md).</span></span>

-   <span data-ttu-id="2bf38-118">Ebenenbasierte Hierarchien für mehrere Entitäten auf der Grundlage der vorhandenen Beziehungen zwischen Entitäten und deren Attributen, als abgeleitete Hierarchie bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="2bf38-118">Level-based hierarchies from multiple entities, based on the existing relationships between entities and their attributes, which are called derived hierarchies.</span></span> <span data-ttu-id="2bf38-119">Weitere Informationen finden Sie unter [Abgeleitete Hierarchien &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="2bf38-119">For more information, see [Derived Hierarchies &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-master-data-services.md).</span></span>

> [!NOTE]
>  <span data-ttu-id="2bf38-120">Alle Elemente in einer Hierarchie müssen demselben Modell angehören.</span><span class="sxs-lookup"><span data-stu-id="2bf38-120">All members in a hierarchy must be within the same model.</span></span>

## <a name="hierarchies-are-not-taxonomies"></a><span data-ttu-id="2bf38-121">Hierarchien sind keine Taxonomien</span><span class="sxs-lookup"><span data-stu-id="2bf38-121">Hierarchies Are Not Taxonomies</span></span>
 <span data-ttu-id="2bf38-122">Eine Hierarchie unterscheidet sich von einer Taxonomie.</span><span class="sxs-lookup"><span data-stu-id="2bf38-122">A hierarchy is different from a taxonomy.</span></span> <span data-ttu-id="2bf38-123">In einer Taxonomie werden Elemente nach mehreren Attributen gleichzeitig organisiert, während Elemente in einer Hierarchie jeweils nach einem Attribut organisiert werden.</span><span class="sxs-lookup"><span data-stu-id="2bf38-123">A taxonomy organizes members by multiple attributes at the same time, while a hierarchy organizes members by one attribute at a time.</span></span> <span data-ttu-id="2bf38-124">Eine Taxonomie kann das gleiche Element mehrfach enthalten, während eine Hierarchie ein Element nur einmal enthalten darf.</span><span class="sxs-lookup"><span data-stu-id="2bf38-124">A taxonomy can include the same member multiple times, while a hierarchy includes a member only once.</span></span>

 <span data-ttu-id="2bf38-125">Beispielsweise kann das gleiche Fahrrad zweimal in eine Taxonomie aufgenommen werden, einmal, weil es rot ist, und ein weiteres Mal, weil es eine 38er Größe hat.</span><span class="sxs-lookup"><span data-stu-id="2bf38-125">For example, the same bike can be included in a taxonomy twice: once because it's red, and once because it's a size 38.</span></span> <span data-ttu-id="2bf38-126">In einer Hierarchie ist das Fahrrad nur einmal enthalten. Sie müssen also festlegen, ob es mit Bezug zu seiner Farbe oder Größe angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="2bf38-126">In a hierarchy, the bike is included only once, so you must decide whether to show it in relation to its color or its size.</span></span>

## <a name="hierarchy-example"></a><span data-ttu-id="2bf38-127">Hierarchiebeispiel</span><span class="sxs-lookup"><span data-stu-id="2bf38-127">Hierarchy Example</span></span>
 <span data-ttu-id="2bf38-128">Im folgenden Beispiel werden Produktelemente nach Unterkategorieelementen gruppiert.</span><span class="sxs-lookup"><span data-stu-id="2bf38-128">In the following example, product members are grouped by subcategory members.</span></span>

 <span data-ttu-id="2bf38-129">![Beispiel für nach Unterkategorie gruppierte Hierarchie](../../2014/master-data-services/media/mds-conc-hierarchy.gif "Beispiel für nach Unterkategorie gruppierte Hierarchie")</span><span class="sxs-lookup"><span data-stu-id="2bf38-129">![Hierarchy Grouped by Subcategory Example](../../2014/master-data-services/media/mds-conc-hierarchy.gif "Hierarchy Grouped by Subcategory Example")</span></span>

## <a name="related-tasks"></a><span data-ttu-id="2bf38-130">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="2bf38-130">Related Tasks</span></span>

|<span data-ttu-id="2bf38-131">Taskbeschreibung</span><span class="sxs-lookup"><span data-stu-id="2bf38-131">Task Description</span></span>|<span data-ttu-id="2bf38-132">Thema</span><span class="sxs-lookup"><span data-stu-id="2bf38-132">Topic</span></span>|
|----------------------|-----------|
|<span data-ttu-id="2bf38-133">Aktivieren Sie eine Entität für explizite Hierarchien und Auflistungen.</span><span class="sxs-lookup"><span data-stu-id="2bf38-133">Enable an entity for explicit hierarchies and collections.</span></span>|[<span data-ttu-id="2bf38-134">Aktivieren einer Entität für explizite Hierarchien und Auflistungen &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="2bf38-134">Enable an Entity for Explicit Hierarchies and Collections &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md)|
|<span data-ttu-id="2bf38-135">Erstellen Sie explizite Hierarchie.</span><span class="sxs-lookup"><span data-stu-id="2bf38-135">Create a explicit hierarchy.</span></span>|[<span data-ttu-id="2bf38-136">Erstellen einer expliziten Hierarchie &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="2bf38-136">Create an Explicit Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-an-explicit-hierarchy-master-data-services.md)|
|<span data-ttu-id="2bf38-137">Erstellen Sie eine abgeleitete Hierarchie.</span><span class="sxs-lookup"><span data-stu-id="2bf38-137">Create a derived hierarchy.</span></span>|[<span data-ttu-id="2bf38-138">Erstellen einer abgeleiteten Hierarchie &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="2bf38-138">Create a Derived Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-derived-hierarchy-master-data-services.md)|
|<span data-ttu-id="2bf38-139">Blenden Sie Ebenen in einer vorhandenen abgeleiteten Hierarchie aus, oder löschen Sie Ebenen.</span><span class="sxs-lookup"><span data-stu-id="2bf38-139">Hide or delete levels in an existing derived hierarchy.</span></span>|[<span data-ttu-id="2bf38-140">Ausblenden oder Löschen von Ebenen in einer abgeleiteten Hierarchie &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="2bf38-140">Hide or Delete Levels in a Derived Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/hide-or-delete-levels-in-a-derived-hierarchy-master-data-services.md)|

## <a name="related-content"></a><span data-ttu-id="2bf38-141">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="2bf38-141">Related Content</span></span>

-   [<span data-ttu-id="2bf38-142">Explizite Hierarchien &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="2bf38-142">Explicit Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/explicit-hierarchies-master-data-services.md)

-   [<span data-ttu-id="2bf38-143">Abgeleitete Hierarchien &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="2bf38-143">Derived Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/derived-hierarchies-master-data-services.md)

-   [<span data-ttu-id="2bf38-144">Rekursive Hierarchien &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="2bf38-144">Recursive Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/recursive-hierarchies-master-data-services.md)

-   [<span data-ttu-id="2bf38-145">Abgeleitete Hierarchien mit expliziten Abschlüssen &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="2bf38-145">Derived Hierarchies with Explicit Caps &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/derived-hierarchies-with-explicit-caps-master-data-services.md)

-   [<span data-ttu-id="2bf38-146">Sammlungen &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="2bf38-146">Collections &#40;Master Data Services&#41;</span></span>](collections-master-data-services.md)


