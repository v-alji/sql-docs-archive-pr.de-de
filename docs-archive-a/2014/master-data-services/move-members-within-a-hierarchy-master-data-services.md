---
title: Verschieben von Elementen innerhalb einer Hierarchie (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- hierarchies [Master Data Services], moving members
- explicit hierarchies, moving members
- derived hierarchies, moving members
- members [Master Data Services], moving
ms.assetid: 049c9a15-89c1-478c-8438-028fffc9e187
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 37167f76b965197dbf8e37e365778395ec640d38
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616589"
---
# <a name="move-members-within-a-hierarchy-master-data-services"></a><span data-ttu-id="f5dcc-102">Verschieben von Elementen innerhalb einer Hierarchie (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="f5dcc-102">Move Members within a Hierarchy (Master Data Services)</span></span>
  <span data-ttu-id="f5dcc-103">Sie können in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] Elemente innerhalb einer Hierarchie verschieben, um deren Position oder die Zuweisung des übergeordneten Elements zu ändern.</span><span class="sxs-lookup"><span data-stu-id="f5dcc-103">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], move members within a hierarchy to change their location or parent assignment.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f5dcc-104">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="f5dcc-104">Prerequisites</span></span>  
 <span data-ttu-id="f5dcc-105">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="f5dcc-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="f5dcc-106">Sie müssen über die Berechtigung für den Zugriff auf den Funktionsbereich **Explorer** verfügen.</span><span class="sxs-lookup"><span data-stu-id="f5dcc-106">You must have permission to access the **Explorer** functional area.</span></span>  
  
-   <span data-ttu-id="f5dcc-107">Bei expliziten Hierarchien müssen Sie mindestens über die Berechtigung **Aktualisieren** für die Entität verfügen.</span><span class="sxs-lookup"><span data-stu-id="f5dcc-107">For explicit hierarchies, you must have a minimum of **Update** permission to the entity.</span></span>  
  
-   <span data-ttu-id="f5dcc-108">Bei abgeleiteten Hierarchien benötigen Sie mindestens ein **Update** für das Modell und alle domänenbasierten Attribute, die in der Hierarchie verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f5dcc-108">For derived hierarchies, you must have a minimum of **Update** to the model and to any domain-based attributes used in the hierarchy.</span></span>  
  
### <a name="to-move-members-within-a-hierarchy"></a><span data-ttu-id="f5dcc-109">So verschieben Sie Elemente innerhalb einer Hierarchie</span><span class="sxs-lookup"><span data-stu-id="f5dcc-109">To move members within a hierarchy</span></span>  
  
1.  <span data-ttu-id="f5dcc-110">Wählen Sie auf der [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] -Startseite aus der Liste **Modell** ein Modell aus.</span><span class="sxs-lookup"><span data-stu-id="f5dcc-110">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, from the **Model** list, select a model.</span></span>  
  
2.  <span data-ttu-id="f5dcc-111">Wählen Sie aus der Liste **Version** eine Version aus.</span><span class="sxs-lookup"><span data-stu-id="f5dcc-111">From the **Version** list, select a version.</span></span>  
  
3.  <span data-ttu-id="f5dcc-112">Klicken Sie auf **Explorer**.</span><span class="sxs-lookup"><span data-stu-id="f5dcc-112">Click **Explorer**.</span></span>  
  
4.  <span data-ttu-id="f5dcc-113">Zeigen Sie auf der Menüleiste auf **Hierarchien** , und klicken Sie auf *Hierarchy_Name*.</span><span class="sxs-lookup"><span data-stu-id="f5dcc-113">From the menu bar, point to **Hierarchies** and click *hierarchy_name*.</span></span>  
  
5.  <span data-ttu-id="f5dcc-114">Klicken Sie im Bereich **Hierarchie** , in dem die Hierarchie in einer Baumstruktur angezeigt wird, auf das Kontrollkästchen für jedes Element, das Sie verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="f5dcc-114">In the **Hierarchy** pane, where the hierarchy is displayed in a tree structure, click the check box for each member you want to move.</span></span>  
  
6.  <span data-ttu-id="f5dcc-115">Klicken Sie oben im Bereich **Hierarchie** auf **Ausschneiden**.</span><span class="sxs-lookup"><span data-stu-id="f5dcc-115">At the top of the **Hierarchy** pane, click **Cut**.</span></span>  
  
7.  <span data-ttu-id="f5dcc-116">Aktivieren Sie im Bereich **Hierarchie** das Kontrollkästchen für den Member, in den die Elemente verschoben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f5dcc-116">In the **Hierarchy** pane, click the check box for the member you want to move the members to.</span></span>  
  
8.  <span data-ttu-id="f5dcc-117">Klicken Sie auf **Einfügen**.</span><span class="sxs-lookup"><span data-stu-id="f5dcc-117">Click **Paste**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f5dcc-118">In abgeleiteten Hierarchien können Sie Elemente nur in Elemente auf gleicher Ebene verschieben.</span><span class="sxs-lookup"><span data-stu-id="f5dcc-118">In derived hierarchies, you can move members to the same level only.</span></span> <span data-ttu-id="f5dcc-119">Auch die Sortierreihenfolge der Elemente kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="f5dcc-119">Also, you cannot change the sort order of members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5dcc-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f5dcc-120">See Also</span></span>  
 <span data-ttu-id="f5dcc-121">[Verschieben Sie explizite Hierarchie Elemente mithilfe des Stagingprozesses &#40;Master Data Services&#41;](add-update-and-delete-data-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="f5dcc-121">[Move Explicit Hierarchy Members by Using the Staging Process &#40;Master Data Services&#41;](add-update-and-delete-data-master-data-services.md) </span></span>  
 <span data-ttu-id="f5dcc-122">[Abgeleitete Hierarchien &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="f5dcc-122">[Derived Hierarchies &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-master-data-services.md) </span></span>  
 [<span data-ttu-id="f5dcc-123">Explizite Hierarchien &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="f5dcc-123">Explicit Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/explicit-hierarchies-master-data-services.md)  
  
  
