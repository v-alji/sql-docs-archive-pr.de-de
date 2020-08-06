---
title: Sichtbarmachen einer Attributgruppe für Benutzer (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: b2f6cc27-dbc9-4f3f-961e-e81e76375248
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 309ad0392cd717d4a8a11470621144ef9e604fd9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607877"
---
# <a name="make-an-attribute-group-visible-to-users-master-data-services"></a><span data-ttu-id="253c8-102">Sichtbarmachen einer Attributgruppe für Benutzer (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="253c8-102">Make an Attribute Group Visible to Users (Master Data Services)</span></span>
  <span data-ttu-id="253c8-103">Machen Sie in [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]eine Attributgruppe für Benutzer oder Gruppen sichtbar, wenn Sie möchten, dass Benutzer im Funktionsbereich **Explorer** oberhalb des Rasters Registerkarten verwenden können.</span><span class="sxs-lookup"><span data-stu-id="253c8-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], make an attribute group visible to users or groups when you want users to have tabs above the grid in the **Explorer** functional area.</span></span>  
  
 <span data-ttu-id="253c8-104">Beim Erstellen einer Attributgruppe wird diese automatisch für alle Benutzer bis auf den Ersteller ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="253c8-104">When you create an attribute group, it is automatically hidden from all users except the one who created it.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="253c8-105">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="253c8-105">Prerequisites</span></span>  
 <span data-ttu-id="253c8-106">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="253c8-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="253c8-107">Sie müssen über die Berechtigung verfügen, auf den Funktionsbereich **System Verwaltung** zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="253c8-107">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="253c8-108">Sie müssen ein Modelladministrator sein.</span><span class="sxs-lookup"><span data-stu-id="253c8-108">You must be a model administrator.</span></span> <span data-ttu-id="253c8-109">Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="253c8-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="253c8-110">Es muss mindestens eine Attributgruppe vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="253c8-110">At least one attribute group must exist.</span></span> <span data-ttu-id="253c8-111">Weitere Informationen finden Sie unter [Erstellen einer Attributgruppe &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-attribute-group-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="253c8-111">For more information, see [Create an Attribute Group &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-attribute-group-master-data-services.md).</span></span>  
  
### <a name="to-make-an-attribute-group-visible-to-users"></a><span data-ttu-id="253c8-112">So machen Sie eine Attributgruppe für Benutzer sichtbar</span><span class="sxs-lookup"><span data-stu-id="253c8-112">To make an attribute group visible to users</span></span>  
  
1.  <span data-ttu-id="253c8-113">Klicken Sie in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]auf **Systemverwaltung**.</span><span class="sxs-lookup"><span data-stu-id="253c8-113">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="253c8-114">Zeigen Sie auf der Seite **Modell Ansicht** auf der Menüleiste auf **Verwalten** , und klicken Sie auf **Attribut Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="253c8-114">On the **Model View** page, from the menu bar, point to **Manage** and click **Attribute Groups**.</span></span>  
  
3.  <span data-ttu-id="253c8-115">Wählen Sie aus der Liste **Modell** ein Modell aus.</span><span class="sxs-lookup"><span data-stu-id="253c8-115">From the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="253c8-116">Wählen Sie aus der Liste **Entität** eine Entität aus.</span><span class="sxs-lookup"><span data-stu-id="253c8-116">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="253c8-117">Klicken Sie auf das Pluszeichen, um **Blatt Gruppen**, **konsolidierte Gruppen**oder Auflistungs **Gruppen**zu erweitern, je nach dem Typ der Gruppe, die Sie sichtbar machen möchten.</span><span class="sxs-lookup"><span data-stu-id="253c8-117">Click the plus sign to expand **Leaf Groups**, **Consolidated Groups**, or **Collection Groups**, depending on the type of group you want to make visible.</span></span>  
  
6.  <span data-ttu-id="253c8-118">Klicken Sie auf das Pluszeichen, um die Gruppe zu erweitern, die Sie sichtbar machen möchten.</span><span class="sxs-lookup"><span data-stu-id="253c8-118">Click the plus sign to expand the group you want to make visible.</span></span>  
  
7.  <span data-ttu-id="253c8-119">Klicken Sie entweder auf **Benutzer** oder **Gruppen**, je nachdem, ob Sie die Gruppe für einen Benutzer oder eine Gruppe sichtbar machen.</span><span class="sxs-lookup"><span data-stu-id="253c8-119">Click either **Users** or **Groups**, depending on whether you are making the group visible to a user or a group.</span></span>  
  
8.  <span data-ttu-id="253c8-120">Klicken Sie auf **ausgewähltes Element bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="253c8-120">Click **Edit selected item**.</span></span>  
  
9. <span data-ttu-id="253c8-121">Klicken Sie im Feld **verfügbar** auf Benutzer oder Gruppen, und klicken Sie auf den Pfeil **Hinzufügen** .</span><span class="sxs-lookup"><span data-stu-id="253c8-121">Click users or groups in the **Available** box and click the **Add** arrow.</span></span> <span data-ttu-id="253c8-122">Klicken Sie auf den Pfeil für **Alle hinzufügen** , um alles hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="253c8-122">To add all, click the **Add All** arrow.</span></span>  
  
10. <span data-ttu-id="253c8-123">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="253c8-123">Click **Save**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="253c8-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="253c8-124">See Also</span></span>  
 <span data-ttu-id="253c8-125">[Attribut Gruppen &#40;Master Data Services&#41;](../../2014/master-data-services/attribute-groups-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="253c8-125">[Attribute Groups &#40;Master Data Services&#41;](../../2014/master-data-services/attribute-groups-master-data-services.md) </span></span>  
 [<span data-ttu-id="253c8-126">Erstellen einer Attributgruppe &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="253c8-126">Create an Attribute Group &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-an-attribute-group-master-data-services.md)  
  
  
