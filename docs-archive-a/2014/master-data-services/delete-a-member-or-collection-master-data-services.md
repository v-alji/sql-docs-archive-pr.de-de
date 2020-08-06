---
title: Löschen eines Elements oder einer Auflistung (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- collections [Master Data Services], deleting
- leaf members [Master Data Services], deleting
- deleting members [Master Data Services]
- members [Master Data Services], deleting
- consolidated members [Master Data Services], deleting
ms.assetid: 519130a7-4226-4d71-9124-d2ee0ce7e5bd
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 9b248750c0e755c3fc9e32d45068c754e64957b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695781"
---
# <a name="delete-a-member-or-collection-master-data-services"></a><span data-ttu-id="c81c7-102">Löschen eines Elements oder einer Auflistung (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="c81c7-102">Delete a Member or Collection (Master Data Services)</span></span>
  <span data-ttu-id="c81c7-103">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]können Sie ein Element oder eine Auflistung löschen, das bzw. die Sie nicht mehr benötigen.</span><span class="sxs-lookup"><span data-stu-id="c81c7-103">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], delete a member or collection when you no longer need it.</span></span> <span data-ttu-id="c81c7-104">Wenn Sie Elemente in einer Massenoperation löschen möchten, verwenden Sie stattdessen den Stagingprozess.</span><span class="sxs-lookup"><span data-stu-id="c81c7-104">If you want to delete members in bulk, use the staging process instead.</span></span> <span data-ttu-id="c81c7-105">Weitere Informationen finden Sie unter [deaktivieren oder Löschen von Elementen mithilfe des Stagingprozesses &#40;Master Data Services&#41;](add-update-and-delete-data-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="c81c7-105">For more information, see [Deactivate or Delete Members by Using the Staging Process &#40;Master Data Services&#41;](add-update-and-delete-data-master-data-services.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c81c7-106">Sie können kein Element löschen, das als domänenbasierter Attributwert für ein anderes Element verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c81c7-106">You cannot delete a member if it is used as a domain-based attribute value for another member.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c81c7-107">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="c81c7-107">Prerequisites</span></span>  
 <span data-ttu-id="c81c7-108">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="c81c7-108">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="c81c7-109">Sie müssen über die Berechtigung für den Zugriff auf den Funktionsbereich **Explorer** verfügen.</span><span class="sxs-lookup"><span data-stu-id="c81c7-109">You must have permission to access the **Explorer** functional area.</span></span>  
  
-   <span data-ttu-id="c81c7-110">Für Mitglieder müssen Sie mindestens über die Berechtigung **Aktualisieren** für das Blatt Modell Objekt verfügen, aus dem Sie ein Element löschen.</span><span class="sxs-lookup"><span data-stu-id="c81c7-110">For members, you must have a minimum of **Update** permission to the leaf model object you are deleting a member from.</span></span>  
  
-   <span data-ttu-id="c81c7-111">Bei Auflistungen müssen Sie für das zu löschende Blattauflistungsobjekt mindestens über die Berechtigung **Aktualisieren** verfügen.</span><span class="sxs-lookup"><span data-stu-id="c81c7-111">For collections, you must have a minimum of **Update** permission to the leaf collection object you are deleting.</span></span>  
  
### <a name="to-delete-a-member-or-collection"></a><span data-ttu-id="c81c7-112">So löschen Sie ein Element oder eine Auflistung</span><span class="sxs-lookup"><span data-stu-id="c81c7-112">To delete a member or collection</span></span>  
  
1.  <span data-ttu-id="c81c7-113">Wählen Sie auf der [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] -Startseite aus der Liste **Modell** ein Modell aus.</span><span class="sxs-lookup"><span data-stu-id="c81c7-113">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, from the **Model** list, select a model.</span></span>  
  
2.  <span data-ttu-id="c81c7-114">Wählen Sie aus der Liste **Version** eine Version aus.</span><span class="sxs-lookup"><span data-stu-id="c81c7-114">From the **Version** list, select a version.</span></span>  
  
3.  <span data-ttu-id="c81c7-115">Klicken Sie auf **Explorer**.</span><span class="sxs-lookup"><span data-stu-id="c81c7-115">Click **Explorer**.</span></span>  
  
4.  <span data-ttu-id="c81c7-116">Zum Löschen</span><span class="sxs-lookup"><span data-stu-id="c81c7-116">To delete:</span></span>  
  
    -   <span data-ttu-id="c81c7-117">eines Elements zeigen Sie auf der Menüleiste auf **Entitäten** und klicken auf den Namen der Entität, in der das Element enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="c81c7-117">A leaf member, from the menu bar, point to **Entities** and click the name of the entity that contains the member.</span></span>  
  
    -   <span data-ttu-id="c81c7-118">eines konsolidierten Elements zeigen Sie auf der Menüleiste auf **Hierarchien** und klicken auf den Namen der Hierarchie, in der das Element enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="c81c7-118">A consolidated member, from the menu bar, point to **Hierarchies** and click the name of the hierarchy that contains the member.</span></span> <span data-ttu-id="c81c7-119">Klicken Sie dann auf den Knoten in der Hierarchie, die das Element enthält.</span><span class="sxs-lookup"><span data-stu-id="c81c7-119">Then click the node in the hierarchy that contains the member.</span></span>  
  
    -   <span data-ttu-id="c81c7-120">einer Sammlung zeigen Sie auf der Menüleiste auf **Sammlungen** und klicken auf den Namen der Entität, in der die Sammlung enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="c81c7-120">A collection, from the menu bar, point to **Collections** and click the name of the entity that contains the collection.</span></span>  
  
5.  <span data-ttu-id="c81c7-121">Klicken Sie im Raster auf die Zeile mit dem Element oder der Sammlung, das bzw. die Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="c81c7-121">In the grid, click the row of the member or collection you want to delete.</span></span>  
  
6.  <span data-ttu-id="c81c7-122">Klicken Sie auf **Element löschen**, **Löschen**oder **Sammlung löschen**.</span><span class="sxs-lookup"><span data-stu-id="c81c7-122">Click **Delete Member**, **Delete**, or **Delete Collection**.</span></span>  
  
7.  <span data-ttu-id="c81c7-123">Klicken Sie im Bestätigungsdialogfeld auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="c81c7-123">In the confirmation dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c81c7-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c81c7-124">See Also</span></span>  
 <span data-ttu-id="c81c7-125">[Erneutes Aktivieren eines Elements oder einer Sammlung &#40;Master Data Services&#41;](../../2014/master-data-services/reactivate-a-member-or-collection-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="c81c7-125">[Reactivate a Member or Collection &#40;Master Data Services&#41;](../../2014/master-data-services/reactivate-a-member-or-collection-master-data-services.md) </span></span>  
 <span data-ttu-id="c81c7-126">[Mitglieder &#40;Master Data Services&#41;](../../2014/master-data-services/members-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="c81c7-126">[Members &#40;Master Data Services&#41;](../../2014/master-data-services/members-master-data-services.md) </span></span>  
 [<span data-ttu-id="c81c7-127">Sammlungen &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c81c7-127">Collections &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/collections-master-data-services.md)  
  
  
