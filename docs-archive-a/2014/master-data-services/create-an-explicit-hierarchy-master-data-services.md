---
title: Erstellen einer expliziten Hierarchie (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- creating explicit hierarchies [Master Data Services]
- explicit hierarchies, creating
ms.assetid: ba768393-6990-4eda-8cb0-d58cb3cfc2e2
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: aebf95e68f210fe5a573aed092231670c10fa188
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619880"
---
# <a name="create-an-explicit-hierarchy-master-data-services"></a><span data-ttu-id="c3d04-102">Erstellen einer expliziten Hierarchie (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="c3d04-102">Create an Explicit Hierarchy (Master Data Services)</span></span>
  <span data-ttu-id="c3d04-103">Erstellen Sie in [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]eine explizite Hierarchie, wenn Sie eine unregelmäßige Hierarchie benötigen, in der Elemente auf jeder Ebene vorhanden sein können.</span><span class="sxs-lookup"><span data-stu-id="c3d04-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create an explicit hierarchy when you need a ragged hierarchy in which members can exist at any level.</span></span> <span data-ttu-id="c3d04-104">Explizite Hierarchien enthalten Elemente aus einer einzelnen Entität.</span><span class="sxs-lookup"><span data-stu-id="c3d04-104">Explicit hierarchies contain members from a single entity.</span></span>  
  
 <span data-ttu-id="c3d04-105">Wenn Sie eine explizite Hierarchie erstellt haben, können Sie dieser im Funktionsbereich **Explorer** Elemente hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="c3d04-105">After you create an explicit hierarchy, you can add members to it in the **Explorer** functional area.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c3d04-106">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="c3d04-106">Prerequisites</span></span>  
 <span data-ttu-id="c3d04-107">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="c3d04-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="c3d04-108">Sie müssen über die Berechtigung verfügen, auf den Funktionsbereich **System Verwaltung** zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="c3d04-108">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="c3d04-109">Sie müssen ein Modelladministrator sein.</span><span class="sxs-lookup"><span data-stu-id="c3d04-109">You must be a model administrator.</span></span> <span data-ttu-id="c3d04-110">Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="c3d04-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="c3d04-111">Die Entität muss für explizite Hierarchien und Auflistungen aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="c3d04-111">The entity must be enabled for explicit hierarchies and collections.</span></span> <span data-ttu-id="c3d04-112">Weitere Informationen finden Sie unter [Aktivieren einer Entität für explizite Hierarchien und Auflistungen &#40;Master Data Services&#41;](../../2014/master-data-services/enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="c3d04-112">For more information, see [Enable an Entity for Explicit Hierarchies and Collections &#40;Master Data Services&#41;](../../2014/master-data-services/enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md).</span></span>  
  
### <a name="to-create-an-explicit-hierarchy"></a><span data-ttu-id="c3d04-113">So erstellen Sie eine explizite Hierarchie</span><span class="sxs-lookup"><span data-stu-id="c3d04-113">To create an explicit hierarchy</span></span>  
  
1.  <span data-ttu-id="c3d04-114">Klicken Sie in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]auf **Systemverwaltung**.</span><span class="sxs-lookup"><span data-stu-id="c3d04-114">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="c3d04-115">Zeigen Sie auf der Seite **Modellansicht** auf der Menüleiste auf **Verwalten** , und klicken Sie auf **Entitäten**.</span><span class="sxs-lookup"><span data-stu-id="c3d04-115">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="c3d04-116">Wählen Sie auf der Seite **Entitätsverwaltung** aus der Liste **Modell** ein Modell aus.</span><span class="sxs-lookup"><span data-stu-id="c3d04-116">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="c3d04-117">Wählen Sie die Zeile für die Entität aus, für die Sie eine explizite Hierarchie erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="c3d04-117">Select the row for the entity that you want to create an explicit hierarchy for.</span></span>  
  
5.  <span data-ttu-id="c3d04-118">Klicken Sie auf **Ausgewählte Entität bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="c3d04-118">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="c3d04-119">Klicken Sie auf der Seite **Entität bearbeiten** im Bereich **explizite Hierarchien** auf **explizite Hierarchie hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="c3d04-119">On the **Edit Entity** page, in the **Explicit hierarchies** pane, click **Add explicit hierarchy**.</span></span>  
  
7.  <span data-ttu-id="c3d04-120">Geben Sie auf der Seite **explizite Hierarchie hinzufügen** im Feld **Name der expliziten Hierarchie** einen Namen für die Hierarchie ein.</span><span class="sxs-lookup"><span data-stu-id="c3d04-120">On the **Add Explicit Hierarchy** page, in the **Explicit hierarchy name** box, type a name for the hierarchy.</span></span>  
  
8.  <span data-ttu-id="c3d04-121">Optional können Sie das Kontrollkästchen für **Obligatorische Hierarchie** deaktivieren, um die Hierarchie als nicht obligatorische Hierarchie zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c3d04-121">Optionally, clear the **Mandatory hierarchy** check box to create the hierarchy as a non-mandatory hierarchy.</span></span> <span data-ttu-id="c3d04-122">Weitere Informationen zu Hierarchietypen finden Sie unter [Explizite Hierarchien &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="c3d04-122">For more information about hierarchy types, see [Explicit Hierarchies &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md).</span></span>  
  
9. <span data-ttu-id="c3d04-123">Klicken Sie auf **Hierarchie speichern**.</span><span class="sxs-lookup"><span data-stu-id="c3d04-123">Click **Save hierarchy**.</span></span>  
  
10. <span data-ttu-id="c3d04-124">Klicken Sie auf der Seite **Entität bearbeiten** auf **Entität speichern**.</span><span class="sxs-lookup"><span data-stu-id="c3d04-124">On the **Edit Entity** page, click **Save entity**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="c3d04-125">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="c3d04-125">Next Steps</span></span>  
  
-   [<span data-ttu-id="c3d04-126">Erstellen eines konsolidierten Elements &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c3d04-126">Create a Consolidated Member &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-consolidated-member-master-data-services.md)  
  
-   [<span data-ttu-id="c3d04-127">Verschieben von Elementen innerhalb einer Hierarchie &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c3d04-127">Move Members within a Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/move-members-within-a-hierarchy-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="c3d04-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c3d04-128">See Also</span></span>  
 <span data-ttu-id="c3d04-129">[Explizite Hierarchien &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="c3d04-129">[Explicit Hierarchies &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md) </span></span>  
 <span data-ttu-id="c3d04-130">[Abgeleitete Hierarchien mit expliziten Caps &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-with-explicit-caps-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="c3d04-130">[Derived Hierarchies with Explicit Caps &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-with-explicit-caps-master-data-services.md) </span></span>  
 [<span data-ttu-id="c3d04-131">Ändern des Namens einer expliziten Hierarchie &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c3d04-131">Change an Explicit Hierarchy Name &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/change-an-explicit-hierarchy-name-master-data-services.md)  
  
  
