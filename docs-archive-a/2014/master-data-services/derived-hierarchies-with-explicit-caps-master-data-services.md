---
title: Abgeleitete Hierarchien mit expliziten Abschlüssen (Master Data Services) |Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- hierarchies [Master Data Services], derived hierarchies with explicit caps
- explicit hierarchies, derived hierarchies with explicit caps
- derived hierarchies, derived hierarchies with explicit caps
ms.assetid: 6a82ff66-c137-4757-99bb-787d189b4295
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: d2460ddf098f0547c2876dd9689f5d2bf9b461a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609925"
---
# <a name="derived-hierarchies-with-explicit-caps-master-data-services"></a><span data-ttu-id="66fb8-102">Abgeleitete Hierarchien mit expliziten Abschlüssen (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="66fb8-102">Derived Hierarchies with Explicit Caps (Master Data Services)</span></span>
  <span data-ttu-id="66fb8-103">Wenn in [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]die Ebenen aus einer expliziten Hierarchie als oberste Ebenen einer abgeleiteten Hierarchie verwendet werden, wird dies als abgeleitete Hierarchie mit explizitem Abschluss bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="66fb8-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], when the levels from an explicit hierarchy are used as the top levels of a derived hierarchy, this is called a derived hierarchy with an explicit cap.</span></span>

 <span data-ttu-id="66fb8-104">Die explizite Hierarchie muss auf der gleichen Entität wie die Entität am oberen Ende der abgeleiteten Hierarchie basieren.</span><span class="sxs-lookup"><span data-stu-id="66fb8-104">The explicit hierarchy must be based on the same entity as the entity at the top of the derived hierarchy.</span></span>

 <span data-ttu-id="66fb8-105">In der [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] -Benutzeroberfläche erstellen Sie diesen Hierarchietyp durch Ziehen einer expliziten Hierarchie in die oberste Ebene einer abgeleiteten Hierarchie.</span><span class="sxs-lookup"><span data-stu-id="66fb8-105">In the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] user interface (UI), you create this type of hierarchy by dragging an explicit hierarchy to the top of a derived hierarchy.</span></span>

 <span data-ttu-id="66fb8-106">![mds_conc_explicit_cap_UI_structure](../../2014/master-data-services/media/mds-conc-explicit-cap-ui-structure.gif "mds_conc_explicit_cap_UI_structure")</span><span class="sxs-lookup"><span data-stu-id="66fb8-106">![mds_conc_explicit_cap_UI_structure](../../2014/master-data-services/media/mds-conc-explicit-cap-ui-structure.gif "mds_conc_explicit_cap_UI_structure")</span></span>

## <a name="derived-hierarchy-with-explicit-cap-example"></a><span data-ttu-id="66fb8-107">Beispiel für eine abgeleitete Hierarchie mit explizitem Abschluss</span><span class="sxs-lookup"><span data-stu-id="66fb8-107">Derived Hierarchy with Explicit Cap Example</span></span>
 <span data-ttu-id="66fb8-108">In diesem Beispiel stammen die Elemente in der expliziten Hierarchie aus der Entität Subcategory.</span><span class="sxs-lookup"><span data-stu-id="66fb8-108">In this example, the members in the explicit hierarchy are from the Subcategory entity.</span></span> <span data-ttu-id="66fb8-109">In der abgeleiteten Hierarchie stammen die Elemente der obersten Ebene auch aus der Entität Unterkategorie.</span><span class="sxs-lookup"><span data-stu-id="66fb8-109">In the derived hierarchy, the top-level members are also from the Subcategory entity.</span></span>

 <span data-ttu-id="66fb8-110">![mds_conc_explicit_cap_UI_example](../../2014/master-data-services/media/mds-conc-explicit-cap-ui-example.gif "mds_conc_explicit_cap_UI_example")</span><span class="sxs-lookup"><span data-stu-id="66fb8-110">![mds_conc_explicit_cap_UI_example](../../2014/master-data-services/media/mds-conc-explicit-cap-ui-example.gif "mds_conc_explicit_cap_UI_example")</span></span>

 <span data-ttu-id="66fb8-111">Durch die Verwendung der expliziten Hierarchie am oberen Rand einer abgeleiteten Hierarchie wird die abgeleitete Hierarchie unregelmäßig.</span><span class="sxs-lookup"><span data-stu-id="66fb8-111">By using the explicit hierarchy at the top of a derived hierarchy, the derived hierarchy becomes ragged.</span></span>

## <a name="rules"></a><span data-ttu-id="66fb8-112">Regeln</span><span class="sxs-lookup"><span data-stu-id="66fb8-112">Rules</span></span>

-   <span data-ttu-id="66fb8-113">Sie können nicht mehr als eine explizite Hierarchie in einer abgeleiteten Hierarchie mit explizitem Abschluss haben.</span><span class="sxs-lookup"><span data-stu-id="66fb8-113">You cannot have more than one explicit hierarchy in a derived hierarchy with explicit cap.</span></span>

-   <span data-ttu-id="66fb8-114">Sie können die gleiche explizite Hierarchie als Abschluss für mehrere abgeleitete Hierarchien verwenden.</span><span class="sxs-lookup"><span data-stu-id="66fb8-114">You can use the same explicit hierarchy as a cap for multiple derived hierarchies.</span></span>

-   <span data-ttu-id="66fb8-115">Sie können keine Hierarchieelementberechtigungen an abgeleitete Hierarchien mit expliziten Abschlüssen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="66fb8-115">You cannot assign hierarchy member permissions to derived hierarchies with explicit caps.</span></span> <span data-ttu-id="66fb8-116">Wenn Sie der expliziten Hierarchie oder der abgeleiteten Hierarchie einzeln Berechtigungen zuweisen, wirken sich die Berechtigungen auf beide Hierarchien aus.</span><span class="sxs-lookup"><span data-stu-id="66fb8-116">If you assign permissions to either the explicit hierarchy or the derived hierarchy individually, the permissions affect both hierarchies.</span></span>

## <a name="related-tasks"></a><span data-ttu-id="66fb8-117">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="66fb8-117">Related Tasks</span></span>

|<span data-ttu-id="66fb8-118">Taskbeschreibung</span><span class="sxs-lookup"><span data-stu-id="66fb8-118">Task Description</span></span>|<span data-ttu-id="66fb8-119">Thema</span><span class="sxs-lookup"><span data-stu-id="66fb8-119">Topic</span></span>|
|----------------------|-----------|
|<span data-ttu-id="66fb8-120">Erstellen Sie eine abgeleitete Hierarchie.</span><span class="sxs-lookup"><span data-stu-id="66fb8-120">Create a derived hierarchy.</span></span>|[<span data-ttu-id="66fb8-121">Erstellen einer abgeleiteten Hierarchie &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="66fb8-121">Create a Derived Hierarchy &#40;Master Data Services&#41;</span></span>](create-a-derived-hierarchy-master-data-services.md)|
|<span data-ttu-id="66fb8-122">Erstellen Sie eine explizite Hierarchie.</span><span class="sxs-lookup"><span data-stu-id="66fb8-122">Create an explicit hierarchy.</span></span>|[<span data-ttu-id="66fb8-123">Erstellen einer expliziten Hierarchie &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="66fb8-123">Create an Explicit Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-an-explicit-hierarchy-master-data-services.md)|
|<span data-ttu-id="66fb8-124">Löschen Sie eine vorhandene abgeleitete Hierarchie.</span><span class="sxs-lookup"><span data-stu-id="66fb8-124">Delete an existing derived hierarchy.</span></span>|[<span data-ttu-id="66fb8-125">Löschen einer abgeleiteten Hierarchie &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="66fb8-125">Delete a Derived Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/delete-a-derived-hierarchy-master-data-services.md)|
|||

## <a name="related-content"></a><span data-ttu-id="66fb8-126">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="66fb8-126">Related Content</span></span>

-   [<span data-ttu-id="66fb8-127">Abgeleitete Hierarchien &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="66fb8-127">Derived Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/derived-hierarchies-master-data-services.md)

-   [<span data-ttu-id="66fb8-128">Explizite Hierarchien &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="66fb8-128">Explicit Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/explicit-hierarchies-master-data-services.md)


