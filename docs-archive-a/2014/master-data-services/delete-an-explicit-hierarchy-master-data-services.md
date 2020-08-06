---
title: Löschen einer expliziten Hierarchie (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- explicit hierarchies, deleting
- deleting explicit hierarchies [Master Data Services]
ms.assetid: 4ce177b0-9884-47a2-9cea-212e845dd762
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 744f96a2705a3abbc2318ecd3c9b0c7fffb7605e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630692"
---
# <a name="delete-an-explicit-hierarchy-master-data-services"></a><span data-ttu-id="21b10-102">Löschen einer expliziten Hierarchie (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="21b10-102">Delete an Explicit Hierarchy (Master Data Services)</span></span>
  <span data-ttu-id="21b10-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]können Sie eine explizite Hierarchie löschen, die Sie nicht mehr benötigen.</span><span class="sxs-lookup"><span data-stu-id="21b10-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], delete an explicit hierarchy when you no longer need it.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="21b10-104">Wenn Sie eine explizite Hierarchie löschen, werden alle konsolidierten Elemente in der Hierarchie ebenfalls gelöscht.</span><span class="sxs-lookup"><span data-stu-id="21b10-104">When you delete an explicit hierarchy, all consolidated members in the hierarchy are deleted also.</span></span> <span data-ttu-id="21b10-105">Wenn Sie alle expliziten Hierarchien für eine Entität löschen, werden auch alle Auflistungen für die Entität gelöscht und die Entität ist nicht mehr für explizite Hierarchien und Auflistungen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="21b10-105">If you delete all explicit hierarchies for an entity, all collections for the entity are also deleted and the entity is no longer enabled for explicit hierarchies and collections.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="21b10-106">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="21b10-106">Prerequisites</span></span>  
 <span data-ttu-id="21b10-107">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="21b10-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="21b10-108">Sie müssen über die Berechtigung verfügen, auf den Funktionsbereich **System Verwaltung** zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="21b10-108">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="21b10-109">Sie müssen ein Modelladministrator sein.</span><span class="sxs-lookup"><span data-stu-id="21b10-109">You must be a model administrator.</span></span> <span data-ttu-id="21b10-110">Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="21b10-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-delete-an-explicit-hierarchy"></a><span data-ttu-id="21b10-111">So löschen Sie eine explizite Hierarchie</span><span class="sxs-lookup"><span data-stu-id="21b10-111">To delete an explicit hierarchy</span></span>  
  
1.  <span data-ttu-id="21b10-112">Klicken Sie in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]auf **Systemverwaltung**.</span><span class="sxs-lookup"><span data-stu-id="21b10-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="21b10-113">Zeigen Sie auf der Seite **Modellansicht** auf der Menüleiste auf **Verwalten** , und klicken Sie auf **Entitäten**.</span><span class="sxs-lookup"><span data-stu-id="21b10-113">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="21b10-114">Wählen Sie auf der Seite **Entitätsverwaltung** aus der Liste **Modell** ein Modell aus.</span><span class="sxs-lookup"><span data-stu-id="21b10-114">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="21b10-115">Wählen Sie die Zeile der Entität aus, die die zu löschende explizite Hierarchie enthält.</span><span class="sxs-lookup"><span data-stu-id="21b10-115">Select the row for the entity that contains the explicit hierarchy you want to delete.</span></span>  
  
5.  <span data-ttu-id="21b10-116">Klicken Sie auf **Ausgewählte Entität bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="21b10-116">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="21b10-117">Klicken Sie auf der Seite **Entität bearbeiten** im Bereich **explizite Hierarchien** auf die explizite Hierarchie, die Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="21b10-117">On the **Edit Entity** page, in the **Explicit Hierarchies** pane, click the explicit hierarchy you want to delete.</span></span>  
  
7.  <span data-ttu-id="21b10-118">Klicken Sie auf **ausgewählte Hierarchie löschen**.</span><span class="sxs-lookup"><span data-stu-id="21b10-118">Click **Delete selected hierarchy**.</span></span>  
  
8.  <span data-ttu-id="21b10-119">Klicken Sie im Bestätigungsdialogfeld auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="21b10-119">In the confirmation dialog box, click **OK**.</span></span>  
  
9. <span data-ttu-id="21b10-120">Klicken Sie im zusätzlichen Bestätigungsdialogfeld auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="21b10-120">In the additional confirmation dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21b10-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="21b10-121">See Also</span></span>  
 <span data-ttu-id="21b10-122">[Erstellen einer expliziten Hierarchie &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-explicit-hierarchy-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="21b10-122">[Create an Explicit Hierarchy &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-explicit-hierarchy-master-data-services.md) </span></span>  
 [<span data-ttu-id="21b10-123">Explizite Hierarchien &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="21b10-123">Explicit Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/explicit-hierarchies-master-data-services.md)  
  
  
