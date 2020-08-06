---
title: Aktivieren einer Entität für explizite Hierarchien und Auflistungen (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- entities [Master Data Services], enabling for collections
- entities [Master Data Services], enabling for explicit hierarchies
ms.assetid: 380e77e5-ad60-43d4-9605-34a84525f5dd
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: a8129b3f67f050603f85ffb782a9dd209cb303fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695757"
---
# <a name="enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services"></a><span data-ttu-id="15f71-102">Aktivieren einer Entität für explizite Hierarchien und Auflistungen (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="15f71-102">Enable an Entity for Explicit Hierarchies and Collections (Master Data Services)</span></span>
  <span data-ttu-id="15f71-103">Aktivieren Sie in [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] eine Entität für explizite Hierarchien und Auflistungen, damit Sie explizite Hierarchien und Auflistungen für die Entität erstellen können.</span><span class="sxs-lookup"><span data-stu-id="15f71-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], enable an entity for explicit hierarchies and collections so that you can create explicit hierarchies and collections for the entity.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="15f71-104">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="15f71-104">Prerequisites</span></span>  
 <span data-ttu-id="15f71-105">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="15f71-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="15f71-106">Sie müssen über die Berechtigung verfügen, auf den Funktionsbereich **System Verwaltung** zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="15f71-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="15f71-107">Sie müssen ein Modelladministrator sein.</span><span class="sxs-lookup"><span data-stu-id="15f71-107">You must be a model administrator.</span></span> <span data-ttu-id="15f71-108">Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="15f71-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="15f71-109">Eine Entität muss vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="15f71-109">An entity must exist.</span></span> <span data-ttu-id="15f71-110">Weitere Informationen finden Sie unter [Erstellen einer Entität &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="15f71-110">For more information, see [Create an Entity &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span></span>  
  
### <a name="to-enable-an-entity-for-explicit-hierarchies-and-collections"></a><span data-ttu-id="15f71-111">So aktivieren Sie eine Entität für explizite Hierarchien und Auflistungen</span><span class="sxs-lookup"><span data-stu-id="15f71-111">To enable an entity for explicit hierarchies and collections</span></span>  
  
1.  <span data-ttu-id="15f71-112">Klicken Sie in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]auf **Systemverwaltung**.</span><span class="sxs-lookup"><span data-stu-id="15f71-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="15f71-113">Zeigen Sie auf der Seite **Modellansicht** auf der Menüleiste auf **Verwalten** , und klicken Sie auf **Entitäten**.</span><span class="sxs-lookup"><span data-stu-id="15f71-113">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="15f71-114">Wählen Sie auf der Seite **Entitätsverwaltung** aus der Liste **Modell** ein Modell aus.</span><span class="sxs-lookup"><span data-stu-id="15f71-114">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="15f71-115">Wählen Sie die Zeile für die Entität aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="15f71-115">Select the row for the entity that you want to update.</span></span>  
  
5.  <span data-ttu-id="15f71-116">Klicken Sie auf **Ausgewählte Entität bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="15f71-116">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="15f71-117">Wählen Sie in der Liste **explizite Hierarchien und Sammlungen aktivieren** die Option **Ja**aus.</span><span class="sxs-lookup"><span data-stu-id="15f71-117">From the **Enable explicit hierarchies and collections** list, select **Yes**.</span></span>  
  
7.  <span data-ttu-id="15f71-118">Geben Sie im Feld **Name der expliziten Hierarchie** einen Namen für eine explizite Hierarchie ein.</span><span class="sxs-lookup"><span data-stu-id="15f71-118">In the **Explicit hierarchy name** box, type a name for an explicit hierarchy.</span></span>  
  
8.  <span data-ttu-id="15f71-119">Optional können Sie das Kontrollkästchen für **Obligatorische Hierarchie** deaktivieren, um die Hierarchie als nicht obligatorische Hierarchie zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="15f71-119">Optionally, clear the **Mandatory hierarchy** check box to create the hierarchy as a non-mandatory hierarchy.</span></span>  
  
9. <span data-ttu-id="15f71-120">Klicken Sie auf **Entität speichern**.</span><span class="sxs-lookup"><span data-stu-id="15f71-120">Click **Save entity**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="15f71-121">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="15f71-121">Next Steps</span></span>  
  
-   [<span data-ttu-id="15f71-122">Erstellen einer expliziten Hierarchie &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="15f71-122">Create an Explicit Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-an-explicit-hierarchy-master-data-services.md)  
  
-   [<span data-ttu-id="15f71-123">Erstellen einer Sammlung &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="15f71-123">Create a Collection &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-collection-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="15f71-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="15f71-124">See Also</span></span>  
 <span data-ttu-id="15f71-125">[Entitäten &#40;Master Data Services&#41;](../../2014/master-data-services/entities-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="15f71-125">[Entities &#40;Master Data Services&#41;](../../2014/master-data-services/entities-master-data-services.md) </span></span>  
 <span data-ttu-id="15f71-126">[Explizite Hierarchien &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="15f71-126">[Explicit Hierarchies &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md) </span></span>  
 [<span data-ttu-id="15f71-127">Sammlungen &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="15f71-127">Collections &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/collections-master-data-services.md)  
  
  
