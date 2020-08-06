---
title: Exportieren von Daten (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- exporting data [Master Data Services]
- subscription views [Master Data Services]
- subscription views [Master Data Services], about subscription views
ms.assetid: 8b74409a-ea70-45f8-84c7-da6905e4901a
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: edae5b996c25a1b6053231ed2f69ef511b9fbfa6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618076"
---
# <a name="exporting-data-master-data-services"></a><span data-ttu-id="093a7-102">Exportieren von Daten (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="093a7-102">Exporting Data (Master Data Services)</span></span>
  <span data-ttu-id="093a7-103">Sie können [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] -Daten in Abonnementsysteme exportieren, indem Sie Abonnementsichten erstellen.</span><span class="sxs-lookup"><span data-stu-id="093a7-103">You can export [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] data to subscribing systems by creating subscriptions views.</span></span> <span data-ttu-id="093a7-104">Die veröffentlichten Daten in der Datenbank [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] können dann von jedem Abonnementsystem angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="093a7-104">Any subscribing system can then view the published data in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="093a7-105">Weitere Informationen zu Ansichten finden Sie unter [Ansichten](../relational-databases/views/views.md).</span><span class="sxs-lookup"><span data-stu-id="093a7-105">For more information about views, see [Views](../relational-databases/views/views.md).</span></span>  
  
## <a name="subscription-view-formats"></a><span data-ttu-id="093a7-106">Abonnementsichtformate</span><span class="sxs-lookup"><span data-stu-id="093a7-106">Subscription View Formats</span></span>  
 <span data-ttu-id="093a7-107">Wenn Sie eine Sicht in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]erstellen, steht Ihnen eine Reihe von Standardsichtformaten in [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] zur Auswahl.</span><span class="sxs-lookup"><span data-stu-id="093a7-107">When you create a view in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], you choose from a set of standard view formats that [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] provides.</span></span> <span data-ttu-id="093a7-108">Mithilfe dieser Formate können Sie Sichten mit folgendem Inhalt erstellen:</span><span class="sxs-lookup"><span data-stu-id="093a7-108">You can use these formats to create views that show:</span></span>  
  
-   <span data-ttu-id="093a7-109">Alle Blattelemente und deren Attribute</span><span class="sxs-lookup"><span data-stu-id="093a7-109">All leaf members and their attributes.</span></span>  
  
-   <span data-ttu-id="093a7-110">Alle konsolidierten Elemente und deren Attribute</span><span class="sxs-lookup"><span data-stu-id="093a7-110">All consolidated members and their attributes.</span></span>  
  
-   <span data-ttu-id="093a7-111">Alle Auflistungen und deren Attribute</span><span class="sxs-lookup"><span data-stu-id="093a7-111">All collections and their attributes.</span></span>  
  
-   <span data-ttu-id="093a7-112">Die Elemente, die der Auflistung explizit hinzugefügt wurden</span><span class="sxs-lookup"><span data-stu-id="093a7-112">The members explicitly added to a collection.</span></span>  
  
-   <span data-ttu-id="093a7-113">Elemente in einer abgeleiteten Hierarchie in einem Format mit über- und untergeordneten Elementen oder Ebenen</span><span class="sxs-lookup"><span data-stu-id="093a7-113">The members in a derived hierarchy, in either a parent child or level format.</span></span>  
  
-   <span data-ttu-id="093a7-114">Elemente in allen expliziten Hierarchien für eine Entität in einem Format mit über- und untergeordneten Elementen oder Ebenen</span><span class="sxs-lookup"><span data-stu-id="093a7-114">The members in all explicit hierarchies for an entity, in either a parent child or level format.</span></span>  
  
## <a name="subscription-views-can-become-out-of-date"></a><span data-ttu-id="093a7-115">Abonnementsichten können ihre Aktualität verlieren</span><span class="sxs-lookup"><span data-stu-id="093a7-115">Subscription Views Can Become Out-of-Date</span></span>  
 <span data-ttu-id="093a7-116">Nachdem Sie für eine Entität oder eine Hierarchie eine Abonnementsicht erstellt haben, werden Änderungen an den zugeordneten Modellobjekten nicht automatisch in der Sicht widergespiegelt.</span><span class="sxs-lookup"><span data-stu-id="093a7-116">After you create a subscription view for an entity or hierarchy, changes to the associated model objects are not automatically reflected in the view.</span></span> <span data-ttu-id="093a7-117">Sie müssen eine Abonnementsicht in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] ggf. erneut generieren, um Änderungen an den Modellobjekten widerzuspiegeln.</span><span class="sxs-lookup"><span data-stu-id="093a7-117">You might need to regenerate a subscription view in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] to reflect changes to model objects.</span></span> <span data-ttu-id="093a7-118">Die Spalte **Geändert** auf der Seite **Exportieren** wird bei einer Änderung der Modellobjekte in **True** geändert.</span><span class="sxs-lookup"><span data-stu-id="093a7-118">The **Changed** column on the **Export** page is updated to **True** when model objects change.</span></span> <span data-ttu-id="093a7-119">Der Wert**True** gibt an, dass Sie die Abonnementsicht bearbeiten und speichern sollten, um die Sicht erneut zu generieren.</span><span class="sxs-lookup"><span data-stu-id="093a7-119">**True** indicates that you should edit the subscription view and save it, which regenerates the view.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="093a7-120">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="093a7-120">Related Tasks</span></span>  
  
|<span data-ttu-id="093a7-121">Taskbeschreibung</span><span class="sxs-lookup"><span data-stu-id="093a7-121">Task Description</span></span>|<span data-ttu-id="093a7-122">Thema</span><span class="sxs-lookup"><span data-stu-id="093a7-122">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="093a7-123">Erstellen Sie eine Abonnementsicht der Masterdaten.</span><span class="sxs-lookup"><span data-stu-id="093a7-123">Create a subscription view of your master data.</span></span>|[<span data-ttu-id="093a7-124">Erstellen Sie eine Abonnement Sicht &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="093a7-124">Create a Subscription View &#40;Master Data Services&#41;</span></span>](create-a-subscription-view-to-export-data-master-data-services.md)|  
|<span data-ttu-id="093a7-125">Löschen Sie eine vorhandene Abonnementsicht.</span><span class="sxs-lookup"><span data-stu-id="093a7-125">Delete an existing subscription view.</span></span>|[<span data-ttu-id="093a7-126">Löschen einer Abonnementsicht &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="093a7-126">Delete a Subscription View &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/delete-a-subscription-view-master-data-services.md)|  
  
## <a name="related-content"></a><span data-ttu-id="093a7-127">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="093a7-127">Related Content</span></span>  
  
-   [<span data-ttu-id="093a7-128">Abonnementsichtformate &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="093a7-128">Subscription View Formats &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/subscription-view-formats-master-data-services.md)  
  
-   [<span data-ttu-id="093a7-129">Ansichten</span><span class="sxs-lookup"><span data-stu-id="093a7-129">Views</span></span>](../relational-databases/views/views.md)  
  
  
