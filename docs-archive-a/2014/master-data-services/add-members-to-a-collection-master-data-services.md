---
title: Hinzufügen von Elementen zu einer Auflistung (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- collections [Master Data Services], adding members
ms.assetid: 1a7155e6-2d4a-4ed1-a72c-edb37fa1a46b
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ce2038f3bc90a2f17506b0aadaaf9707fa911896
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622194"
---
# <a name="add-members-to-a-collection-master-data-services"></a><span data-ttu-id="6c4cd-102">Hinzufügen von Elementen zu einer Auflistung (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="6c4cd-102">Add Members to a Collection (Master Data Services)</span></span>
  <span data-ttu-id="6c4cd-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]können Sie Blatt- und konsolidierte Elemente zu einer Auflistung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="6c4cd-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], you can add leaf and consolidated members to a collection.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6c4cd-104">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="6c4cd-104">Prerequisites</span></span>  
 <span data-ttu-id="6c4cd-105">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="6c4cd-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="6c4cd-106">Sie müssen über die Berechtigung für den Zugriff auf den Funktionsbereich **Explorer** verfügen.</span><span class="sxs-lookup"><span data-stu-id="6c4cd-106">You must have permission to access the **Explorer** functional area.</span></span>  
  
-   <span data-ttu-id="6c4cd-107">Sie müssen mindestens über die Berechtigung **Aktualisieren** für das Sammlungsmodellobjekt verfügen, dem Sie Elemente hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="6c4cd-107">You must have a minimum of **Update** permission to the collection model object that you are adding members to.</span></span>  
  
-   <span data-ttu-id="6c4cd-108">Eine Sammlung muss vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="6c4cd-108">A collection must exist.</span></span> <span data-ttu-id="6c4cd-109">Weitere Informationen finden Sie unter [Erstellen einer Sammlung &#40;Master Data Services&#41;](create-a-collection-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="6c4cd-109">For more information, see [Create a Collection &#40;Master Data Services&#41;](create-a-collection-master-data-services.md).</span></span>  
  
### <a name="to-add-members-to-a-collection"></a><span data-ttu-id="6c4cd-110">So fügen Sie einer Sammlung Elemente hinzu</span><span class="sxs-lookup"><span data-stu-id="6c4cd-110">To add members to a collection</span></span>  
  
1.  <span data-ttu-id="6c4cd-111">Wählen Sie auf der [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] -Startseite aus der Liste **Modell** ein Modell aus.</span><span class="sxs-lookup"><span data-stu-id="6c4cd-111">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, from the **Model** list, select a model.</span></span>  
  
2.  <span data-ttu-id="6c4cd-112">Wählen Sie aus der Liste **Version** eine Version aus.</span><span class="sxs-lookup"><span data-stu-id="6c4cd-112">From the **Version** list, select a version.</span></span>  
  
3.  <span data-ttu-id="6c4cd-113">Klicken Sie auf **Explorer**.</span><span class="sxs-lookup"><span data-stu-id="6c4cd-113">Click **Explorer**.</span></span>  
  
4.  <span data-ttu-id="6c4cd-114">Zeigen Sie auf der Menüleiste auf **Sammlungen** , und klicken Sie auf einen *Entitätsnamen*.</span><span class="sxs-lookup"><span data-stu-id="6c4cd-114">From the menu bar, point to **Collections** and click *entity_name*.</span></span>  
  
5.  <span data-ttu-id="6c4cd-115">Klicken Sie im Raster auf die Zeile der Auflistung, der Sie Elemente hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="6c4cd-115">In the grid, click the row for the collection you want to add members to.</span></span>  
  
6.  <span data-ttu-id="6c4cd-116">Klicken Sie auf die Registerkarte **Sammlungselemente** .</span><span class="sxs-lookup"><span data-stu-id="6c4cd-116">Click the **Collection Members** tab.</span></span>  
  
7.  <span data-ttu-id="6c4cd-117">Klicken Sie auf **Elemente bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="6c4cd-117">Click **Edit Members**.</span></span>  
  
8.  <span data-ttu-id="6c4cd-118">Um die Liste der verfügbaren Elemente zu filtern, nehmen Sie Ihre Auswahl in der Liste links vor.</span><span class="sxs-lookup"><span data-stu-id="6c4cd-118">To filter the list of available members, select from the list on the left.</span></span>  
  
9. <span data-ttu-id="6c4cd-119">Klicken Sie auf die Zeile mit dem Element, das Sie hinzufügen möchten, und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="6c4cd-119">Click the row with the member you want to add and click **Add**.</span></span>  
  
10. <span data-ttu-id="6c4cd-120">Ordnen Sie optional Auflistungselemente durch das Klicken auf **Nach oben** oder **Nach unten**neu an.</span><span class="sxs-lookup"><span data-stu-id="6c4cd-120">Optionally, rearrange collection members by clicking **Up** or **Down**.</span></span>  
  
11. <span data-ttu-id="6c4cd-121">Legen Sie optional die Gewichtung fest, indem Sie in der Spalte **Gewichtung** auf einen Wert klicken.</span><span class="sxs-lookup"><span data-stu-id="6c4cd-121">Optionally, set weight values by clicking the value in the **Weight** column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c4cd-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6c4cd-122">See Also</span></span>  
 [<span data-ttu-id="6c4cd-123">Sammlungen &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="6c4cd-123">Collections &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/collections-master-data-services.md)  
  
  
