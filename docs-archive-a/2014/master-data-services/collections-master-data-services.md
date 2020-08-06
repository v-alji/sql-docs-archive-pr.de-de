---
title: Auflistungen (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- collections [Master Data Services]
- collections [Master Data Services], about collections
ms.assetid: 5aa1d1e0-b4e5-4897-8e74-01dcf418df73
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ce49c57aad5da52dabba32a0f3fb9b6f4f45b209
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699998"
---
# <a name="collections-master-data-services"></a><span data-ttu-id="0c4ce-102">Auflistungen (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="0c4ce-102">Collections (Master Data Services)</span></span>
  <span data-ttu-id="0c4ce-103">Eine Auflistung ist eine Gruppe von Blatt- und konsolidierten Elementen einer einzelnen Entität.</span><span class="sxs-lookup"><span data-stu-id="0c4ce-103">A collection is a group of leaf and consolidated members from a single entity.</span></span> <span data-ttu-id="0c4ce-104">Verwenden Sie Auflistungen, wenn Sie keine vollständige Hierarchie benötigen und unterschiedliche Gruppierungen der Elemente zu Berichts- oder Analysezwecken anzeigen möchten oder wenn Sie eine Taxonomie erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="0c4ce-104">Use collections when you do not need a complete hierarchy and you want to view different groupings of members for reporting or analysis, or when you need to create a taxonomy.</span></span>  
  
## <a name="what-collections-contain"></a><span data-ttu-id="0c4ce-105">Inhalte von Auflistungen</span><span class="sxs-lookup"><span data-stu-id="0c4ce-105">What Collections Contain</span></span>  
 <span data-ttu-id="0c4ce-106">Es gibt bei Auflistungen keine Beschränkung hinsichtlich der Anzahl oder des Typs der Elemente, die eingebunden werden können, solange sich die Elemente in derselben Entität befinden.</span><span class="sxs-lookup"><span data-stu-id="0c4ce-106">Collections do not limit the number or type of members you can include, as long as the members are within the same entity.</span></span> <span data-ttu-id="0c4ce-107">Eine Auflistung kann konsolidierte Elemente und Blattelemente aus mehreren verbindlichen bzw. nicht verbindlichen expliziten Hierarchien enthalten.</span><span class="sxs-lookup"><span data-stu-id="0c4ce-107">A collection can contain leaf and consolidated members from multiple mandatory and non-mandatory explicit hierarchies.</span></span>  
  
 <span data-ttu-id="0c4ce-108">Wenn Sie eine Auflistung erstellen, erstellen Sie keine hierarchische Struktur; Sie erstellen eine flache Liste von Elementen.</span><span class="sxs-lookup"><span data-stu-id="0c4ce-108">When you create a collection, you are not creating a hierarchical structure; you are creating a flat list of members.</span></span> <span data-ttu-id="0c4ce-109">Wenn Sie einen Knoten aus einer Hierarchie auswählen und ihn der Auflistung hinzufügen, ist das konsolidierte Element, das Sie ausgewählt haben, das einzige der Auflistung hinzugefügte Element.</span><span class="sxs-lookup"><span data-stu-id="0c4ce-109">When you select a node from a hierarchy and add it to the collection, the consolidated member you selected is the only member added to the collection.</span></span>  
  
 <span data-ttu-id="0c4ce-110">Außerdem kann eine Auflistung weitere Auflistungen enthalten.</span><span class="sxs-lookup"><span data-stu-id="0c4ce-110">A collection can also contain other collections.</span></span> <span data-ttu-id="0c4ce-111">Zum Erstellen von Taxonomien können Sie Auflistungen verwenden, die wiederum aus Auflistungen bestehen.</span><span class="sxs-lookup"><span data-stu-id="0c4ce-111">You can use collections of collections to create taxonomies.</span></span>  
  
 <span data-ttu-id="0c4ce-112">Wenn Sie eine Auflistung erstellen, sind Sie automatisch als Besitzer aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="0c4ce-112">When you create a collection you are automatically listed as the owner.</span></span> <span data-ttu-id="0c4ce-113">Wenn Sie Administrator sind, können Sie nach Bedarf andere Attribute für die Auflistung erstellen.</span><span class="sxs-lookup"><span data-stu-id="0c4ce-113">If you are an administrator, you can create other attributes for your collection as needed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0c4ce-114">Bevor Sie eine Auflistung erstellen können, muss die Entität für explizite Hierarchien aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="0c4ce-114">Before you can create a collection, the entity must be enabled for explicit hierarchies.</span></span> <span data-ttu-id="0c4ce-115">Weitere Informationen finden Sie unter [Aktivieren einer Entität für explizite Hierarchien und Auflistungen &#40;Master Data Services&#41;](enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="0c4ce-115">For more information, see [Enable an Entity for Explicit Hierarchies and Collections &#40;Master Data Services&#41;](enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md).</span></span>  
  
## <a name="subscription-views-for-collections"></a><span data-ttu-id="0c4ce-116">Abonnementsichten für Auflistungen</span><span class="sxs-lookup"><span data-stu-id="0c4ce-116">Subscription Views for Collections</span></span>  
 <span data-ttu-id="0c4ce-117">Es gibt zwei Typen von Abonnementsichten, die Auflistungen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="0c4ce-117">There are two types of subscription views that show collections.</span></span> <span data-ttu-id="0c4ce-118">Das Format **Sammlungsattribute** zeigt eine Liste von Sammlungen und allen zu den jeweiligen Sammlungen gehörenden Attributen an (z.B. Beschreibung oder Besitzer).</span><span class="sxs-lookup"><span data-stu-id="0c4ce-118">The **Collection attributes** format shows a list of collections and any attributes related to the collections (like description or owner).</span></span> <span data-ttu-id="0c4ce-119">Das **Sammlungen** -Format zeigt alle Elemente in allen Auflistungen sowie jede Elementgewichtung und Sortierreihenfolge an.</span><span class="sxs-lookup"><span data-stu-id="0c4ce-119">The **Collections** format shows all members in all collections, as well as each members weight and sort order.</span></span> <span data-ttu-id="0c4ce-120">Weitere Informationen finden Sie unter [Exportieren von Daten &#40;Master Data Services&#41;](overview-exporting-data-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="0c4ce-120">For more information, see [Exporting Data &#40;Master Data Services&#41;](overview-exporting-data-master-data-services.md).</span></span>  
  
 <span data-ttu-id="0c4ce-121">Wenn Sie Gewichtungswerte für bestimmte Elemente in einer Auflistung festlegten, sind diese Werte in verwandten Abonnementsichten verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0c4ce-121">If you set weight values for specific members in a collection, these values are available in related subscription views.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="0c4ce-122">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="0c4ce-122">Related Tasks</span></span>  
  
|<span data-ttu-id="0c4ce-123">Taskbeschreibung</span><span class="sxs-lookup"><span data-stu-id="0c4ce-123">Task Description</span></span>|<span data-ttu-id="0c4ce-124">Thema</span><span class="sxs-lookup"><span data-stu-id="0c4ce-124">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="0c4ce-125">Aktivieren Sie eine Entität für explizite Hierarchien und Auflistungen.</span><span class="sxs-lookup"><span data-stu-id="0c4ce-125">Enable an entity for explicit hierarchies and collections.</span></span>|[<span data-ttu-id="0c4ce-126">Aktivieren einer Entität für explizite Hierarchien und Auflistungen &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="0c4ce-126">Enable an Entity for Explicit Hierarchies and Collections &#40;Master Data Services&#41;</span></span>](enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md)|  
|<span data-ttu-id="0c4ce-127">Erstellen Sie eine neue Sammlung.</span><span class="sxs-lookup"><span data-stu-id="0c4ce-127">Create a new collection.</span></span>|[<span data-ttu-id="0c4ce-128">Erstellen einer Sammlung &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="0c4ce-128">Create a Collection &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-collection-master-data-services.md)|  
|<span data-ttu-id="0c4ce-129">Fügen Sie Elemente einer vorhandenen Auflistung hinzu.</span><span class="sxs-lookup"><span data-stu-id="0c4ce-129">Add members to an existing collection.</span></span>|[<span data-ttu-id="0c4ce-130">Hinzufügen von Elementen zu einer Sammlung &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="0c4ce-130">Add Members to a Collection &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/add-members-to-a-collection-master-data-services.md)|  
  
## <a name="related-content"></a><span data-ttu-id="0c4ce-131">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="0c4ce-131">Related Content</span></span>  
  
-   [<span data-ttu-id="0c4ce-132">Explizite Hierarchien &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="0c4ce-132">Explicit Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/explicit-hierarchies-master-data-services.md)  
  
-   [<span data-ttu-id="0c4ce-133">Daten &#40;Master Data Services werden exportiert&#41;</span><span class="sxs-lookup"><span data-stu-id="0c4ce-133">Exporting Data &#40;Master Data Services&#41;</span></span>](overview-exporting-data-master-data-services.md)  
  
  
