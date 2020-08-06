---
title: Erstellen einer Auflistung (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- creating collections [Master Data Services]
- collections [Master Data Services], creating
ms.assetid: 3d4f152c-863c-4385-bca9-a9fcd0402e1f
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: f76171b4fd9b07f751d4f919011a443253fbe31b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718364"
---
# <a name="create-a-collection-master-data-services"></a><span data-ttu-id="5de91-102">Erstellen einer Auflistung (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="5de91-102">Create a Collection (Master Data Services)</span></span>
  <span data-ttu-id="5de91-103">Erstellen Sie in [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]eine Auflistung, wenn Sie flache Listen mit Blatt- und konsolidierten Elementen erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="5de91-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a collection when you want to create flat lists of leaf and consolidated members.</span></span> <span data-ttu-id="5de91-104">Auflistungen müssen nicht alle Elemente aus der Entität einschließen.</span><span class="sxs-lookup"><span data-stu-id="5de91-104">Collections do not need to include all members from the entity.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5de91-105">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="5de91-105">Prerequisites</span></span>  
 <span data-ttu-id="5de91-106">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="5de91-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="5de91-107">Sie müssen über die Berechtigung für den Zugriff auf den Funktionsbereich **Explorer** verfügen.</span><span class="sxs-lookup"><span data-stu-id="5de91-107">You must have permission to access the **Explorer** functional area.</span></span>  
  
-   <span data-ttu-id="5de91-108">Sie müssen mindestens über die Berechtigung **Aktualisieren** für das Auflistungsmodellobjekt der Entität verfügen.</span><span class="sxs-lookup"><span data-stu-id="5de91-108">You must have a minimum of **Update** permission to the collection model object for the entity.</span></span>  
  
-   <span data-ttu-id="5de91-109">Die Entität muss für explizite Hierarchien und Auflistungen aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="5de91-109">The entity must be enabled for explicit hierarchies and collections.</span></span> <span data-ttu-id="5de91-110">Weitere Informationen finden Sie unter [Aktivieren einer Entität für explizite Hierarchien und Auflistungen &#40;Master Data Services&#41;](enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="5de91-110">For more information, see [Enable an Entity for Explicit Hierarchies and Collections &#40;Master Data Services&#41;](enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md).</span></span>  
  
### <a name="to-create-a-collection"></a><span data-ttu-id="5de91-111">So erstellen Sie eine Sammlung</span><span class="sxs-lookup"><span data-stu-id="5de91-111">To create a collection</span></span>  
  
1.  <span data-ttu-id="5de91-112">Wählen Sie auf der [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] -Startseite aus der Liste **Modell** ein Modell aus.</span><span class="sxs-lookup"><span data-stu-id="5de91-112">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, from the **Model** list, select a model.</span></span>  
  
2.  <span data-ttu-id="5de91-113">Wählen Sie aus der Liste **Version** eine Version aus.</span><span class="sxs-lookup"><span data-stu-id="5de91-113">From the **Version** list, select a version.</span></span>  
  
3.  <span data-ttu-id="5de91-114">Klicken Sie auf **Explorer**.</span><span class="sxs-lookup"><span data-stu-id="5de91-114">Click **Explorer**.</span></span>  
  
4.  <span data-ttu-id="5de91-115">Zeigen Sie auf der Menüleiste auf **Sammlungen** , und klicken Sie auf einen *Entitätsnamen*.</span><span class="sxs-lookup"><span data-stu-id="5de91-115">From the menu bar, point to **Collections** and click *entity_name*.</span></span>  
  
5.  <span data-ttu-id="5de91-116">Klicken Sie auf **Auflistung hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="5de91-116">Click **Add collection**.</span></span>  
  
6.  <span data-ttu-id="5de91-117">Geben Sie auf der Registerkarte **Details** im Feld **Name** einen Namen für die Auflistung ein.</span><span class="sxs-lookup"><span data-stu-id="5de91-117">On the **Details** tab, in the **Name** box, type a name for the collection.</span></span>  
  
7.  <span data-ttu-id="5de91-118">Geben Sie im Feld **Code** einen eindeutigen Code für die Auflistung ein.</span><span class="sxs-lookup"><span data-stu-id="5de91-118">In the **Code** box, type a unique code for the collection.</span></span>  
  
8.  <span data-ttu-id="5de91-119">Geben Sie optional im Textfeld **Beschreibung** eine Beschreibung für die Auflistung ein.</span><span class="sxs-lookup"><span data-stu-id="5de91-119">Optionally, in the **Description** box, type a description for the collection.</span></span>  
  
9. <span data-ttu-id="5de91-120">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="5de91-120">Click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="5de91-121">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="5de91-121">Next Steps</span></span>  
  
-   [<span data-ttu-id="5de91-122">Hinzufügen von Elementen zu einer Sammlung &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="5de91-122">Add Members to a Collection &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/add-members-to-a-collection-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="5de91-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5de91-123">See Also</span></span>  
 <span data-ttu-id="5de91-124">[Sammlungen &#40;Master Data Services&#41;](../../2014/master-data-services/collections-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="5de91-124">[Collections &#40;Master Data Services&#41;](../../2014/master-data-services/collections-master-data-services.md) </span></span>  
 <span data-ttu-id="5de91-125">[Löschen eines Elements oder einer Sammlung &#40;Master Data Services&#41;](../../2014/master-data-services/delete-a-member-or-collection-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="5de91-125">[Delete a Member or Collection &#40;Master Data Services&#41;](../../2014/master-data-services/delete-a-member-or-collection-master-data-services.md) </span></span>  
 [<span data-ttu-id="5de91-126">Erstellen einer expliziten Hierarchie &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="5de91-126">Create an Explicit Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-an-explicit-hierarchy-master-data-services.md)  
  
  
