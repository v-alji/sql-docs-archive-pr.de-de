---
title: Erstellen eines konsolidierten Elements (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- creating consolidated members [Master Data Services]
- members [Master Data Services], creating consolidated members
- consolidated members [Master Data Services], creating
ms.assetid: 431ab2d2-5517-4372-9980-142b05427c08
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c41673f6f3bf1f4de2a831ecd659321b273b6af9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718349"
---
# <a name="create-a-consolidated-member-master-data-services"></a><span data-ttu-id="ca868-102">Create a Consolidated Member (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="ca868-102">Create a Consolidated Member (Master Data Services)</span></span>
  <span data-ttu-id="ca868-103">Erstellen Sie in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]ein konsolidiertes Element, wenn Sie einen übergeordneten Knoten für eine explizite Hierarchie wollen.</span><span class="sxs-lookup"><span data-stu-id="ca868-103">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], create a consolidated member when you want a parent node for an explicit hierarchy.</span></span> <span data-ttu-id="ca868-104">Konsolidierte Elemente können eigene Attribute aufweisen.</span><span class="sxs-lookup"><span data-stu-id="ca868-104">Consolidated members can have their own attributes.</span></span> <span data-ttu-id="ca868-105">Sie werden zum Gruppieren verwendet.</span><span class="sxs-lookup"><span data-stu-id="ca868-105">They are used for grouping.</span></span> <span data-ttu-id="ca868-106">Wie im folgenden Beispiel gezeigt, können konsolidierte Elemente zum Gruppieren von Konten verwendet werden, die Konten unter sich haben.</span><span class="sxs-lookup"><span data-stu-id="ca868-106">As shown in the following example, consolidated members can be used for account groups that have accounts under them.</span></span>

 <span data-ttu-id="ca868-107">![Konsolidierte MDS-Elemente](../../2014/master-data-services/media/mds-consolidated-members.png "Konsolidierte MDS-Elemente")</span><span class="sxs-lookup"><span data-stu-id="ca868-107">![MDS Consolidated Members](../../2014/master-data-services/media/mds-consolidated-members.png "MDS Consolidated Members")</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ca868-108">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="ca868-108">Prerequisites</span></span>
 <span data-ttu-id="ca868-109">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="ca868-109">To perform this procedure:</span></span>

-   <span data-ttu-id="ca868-110">Sie müssen über die Berechtigung für den Zugriff auf den Funktionsbereich **Explorer** verfügen.</span><span class="sxs-lookup"><span data-stu-id="ca868-110">You must have permission to access the **Explorer** functional area.</span></span>

-   <span data-ttu-id="ca868-111">Sie müssen mindestens die Berechtigung **Aktualisieren** für das konsolidierte Modellobjekt für die Entität besitzen, der Sie ein Element hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ca868-111">You must have a minimum of **Update** permission to the consolidated model object for the entity you are adding a member to.</span></span>

### <a name="to-create-a-consolidated-member"></a><span data-ttu-id="ca868-112">So erstellen Sie ein konsolidiertes Element</span><span class="sxs-lookup"><span data-stu-id="ca868-112">To create a consolidated member</span></span>

1.  <span data-ttu-id="ca868-113">Wählen Sie auf der [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] -Startseite aus der Liste **Modell** ein Modell aus.</span><span class="sxs-lookup"><span data-stu-id="ca868-113">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, from the **Model** list, select a model.</span></span>

2.  <span data-ttu-id="ca868-114">Wählen Sie aus der Liste **Version** eine Version aus.</span><span class="sxs-lookup"><span data-stu-id="ca868-114">From the **Version** list, select a version.</span></span>

3.  <span data-ttu-id="ca868-115">Klicken Sie auf **Explorer**.</span><span class="sxs-lookup"><span data-stu-id="ca868-115">Click **Explorer**.</span></span>

4.  <span data-ttu-id="ca868-116">Zeigen Sie auf der Menüleiste auf **Hierarchien** , und klicken Sie auf den Namen der Hierarchie, der Sie ein konsolidiertes Element hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="ca868-116">From the menu bar, point to **Hierarchies** and click the name of the hierarchy you want to add a consolidated member to.</span></span>

5.  <span data-ttu-id="ca868-117">Aktivieren Sie über dem Raster die Option **Konsolidierte Elemente** oder **Alle konsolidierten Elemente in der Hierarchie** .</span><span class="sxs-lookup"><span data-stu-id="ca868-117">Above the grid, select either the **Consolidated members** or the **All consolidated members in hierarchy** option.</span></span>

6.  <span data-ttu-id="ca868-118">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ca868-118">Click **Add**.</span></span>

7.  <span data-ttu-id="ca868-119">Vervollständigen Sie im Bereich rechts die Felder.</span><span class="sxs-lookup"><span data-stu-id="ca868-119">In the pane on the right, complete the fields.</span></span>

8.  <span data-ttu-id="ca868-120">Optional.</span><span class="sxs-lookup"><span data-stu-id="ca868-120">Optional.</span></span> <span data-ttu-id="ca868-121">Geben Sie im Feld **Anmerkungen** einen Kommentar dazu ein, warum das Element hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="ca868-121">In the **Annotations** box, type a comment about why the member was added.</span></span> <span data-ttu-id="ca868-122">Alle Benutzer, die Zugriff auf das Element haben, können die Anmerkung anzeigen.</span><span class="sxs-lookup"><span data-stu-id="ca868-122">All users who have access to the member can view the annotation.</span></span>

9. <span data-ttu-id="ca868-123">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ca868-123">Click **OK**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ca868-124">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="ca868-124">Next Steps</span></span>

-   [<span data-ttu-id="ca868-125">Verschieben von Elementen innerhalb einer Hierarchie &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="ca868-125">Move Members within a Hierarchy &#40;Master Data Services&#41;</span></span>](move-members-within-a-hierarchy-master-data-services.md)

## <a name="see-also"></a><span data-ttu-id="ca868-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ca868-126">See Also</span></span>
 <span data-ttu-id="ca868-127">[Erstellen einer expliziten Hierarchie &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-explicit-hierarchy-master-data-services.md) [ein Blatt Element &#40;Master Data Services](../../2014/master-data-services/create-a-leaf-member-master-data-services.md)&#41;[Laden oder Aktualisieren von Elementen in Master Data Services mithilfe der stagingprozessmember](add-update-and-delete-data-master-data-services.md) [&#40;](../../2014/master-data-services/members-master-data-services.md) Master Data Services&#41;[expliziten Hierarchien](../../2014/master-data-services/explicit-hierarchies-master-data-services.md) &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="ca868-127">[Create an Explicit Hierarchy &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-explicit-hierarchy-master-data-services.md) [Create a Leaf Member &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-leaf-member-master-data-services.md) [Load or Update Members in Master Data Services by Using the Staging Process](add-update-and-delete-data-master-data-services.md) [Members &#40;Master Data Services&#41;](../../2014/master-data-services/members-master-data-services.md) [Explicit Hierarchies &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md)</span></span>


