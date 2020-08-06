---
title: Attributgruppen (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- attribute groups [Master Data Services]
- attribute groups [Master Data Services], about attribute groups
ms.assetid: 648b3d0b-e15a-45f9-8292-3a54a072e62c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 390b402489799639e66a44992da1e20b0d0c1bbf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618762"
---
# <a name="attribute-groups-master-data-services"></a><span data-ttu-id="49df1-102">Attributgruppen (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="49df1-102">Attribute Groups (Master Data Services)</span></span>
  <span data-ttu-id="49df1-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]können Attribute in einer Entität mithilfe von Attributgruppen organisiert werden.</span><span class="sxs-lookup"><span data-stu-id="49df1-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], attribute groups help organize attributes in an entity.</span></span> <span data-ttu-id="49df1-104">Wenn eine Entität über viele Attribute verfügt, kann die Entität mit Attributgruppen besser in der [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] -Webanwendung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="49df1-104">When an entity has lots of attributes, attribute groups improve the way an entity is displayed in the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application.</span></span>  
  
## <a name="how-attribute-groups-change-the-display"></a><span data-ttu-id="49df1-105">Ändern der Anzeige mithilfe von Attributgruppen</span><span class="sxs-lookup"><span data-stu-id="49df1-105">How Attribute Groups Change the Display</span></span>  
 <span data-ttu-id="49df1-106">Attributgruppen werden als Registerkarten oberhalb des Rasters im Funktionsbereich **Explorer** von [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]angezeigt.</span><span class="sxs-lookup"><span data-stu-id="49df1-106">Attribute groups are displayed as tabs above the grid in the **Explorer** functional area of [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span></span>  
  
 <span data-ttu-id="49df1-107">Wenn eine Entität über eine große Anzahl von Attributen verfügt und Sie diese Entität in einem Raster in **Explorer**anzeigen, müssen Sie zum Anzeigen aller Attribute einen Bildlauf nach rechts durchführen.</span><span class="sxs-lookup"><span data-stu-id="49df1-107">When an entity has a large number of attributes and you view that entity in a grid in **Explorer**, you must scroll to the right to view all of the attributes.</span></span> <span data-ttu-id="49df1-108">Um dies zu vermeiden, können Sie Attributgruppen erstellen.</span><span class="sxs-lookup"><span data-stu-id="49df1-108">To prevent this scrolling, you can create attribute groups.</span></span>  
  
-   <span data-ttu-id="49df1-109">Attributgruppen schließen immer das Name-Attribut und das Code-Attribut ein.</span><span class="sxs-lookup"><span data-stu-id="49df1-109">Attribute groups always include the Name and Code attributes.</span></span>  
  
-   <span data-ttu-id="49df1-110">Jedes Attribut für eine Entität kann einer oder mehreren Attributgruppen angehören.</span><span class="sxs-lookup"><span data-stu-id="49df1-110">Each attribute for an entity can belong to one or more attribute groups.</span></span>  
  
-   <span data-ttu-id="49df1-111">Alle Attribute sind automatisch im **Explorer** auf der Registerkarte **Alle Attribute**enthalten.</span><span class="sxs-lookup"><span data-stu-id="49df1-111">All attributes are automatically included on the **All Attributes** tab in **Explorer**.</span></span>  
  
-   <span data-ttu-id="49df1-112">Es gibt keine Möglichkeit, die Registerkarte **Alle Attribute** auszublenden.</span><span class="sxs-lookup"><span data-stu-id="49df1-112">There is no way to hide the **All Attributes** tab.</span></span>  
  
 <span data-ttu-id="49df1-113">Attributgruppen werden im Funktionsbereich **Systemverwaltung** von [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]verwaltet.</span><span class="sxs-lookup"><span data-stu-id="49df1-113">Attribute groups are administered in the **System Administration** functional area of [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span></span>  
  
## <a name="show-or-hide-attribute-groups"></a><span data-ttu-id="49df1-114">Anzeigen oder Ausblenden von Attributgruppen</span><span class="sxs-lookup"><span data-stu-id="49df1-114">Show or Hide Attribute Groups</span></span>  
 <span data-ttu-id="49df1-115">Beim Erstellen einer Attributgruppe wird diese automatisch für alle Benutzer bis auf den Ersteller ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="49df1-115">When you create an attribute group, it is automatically hidden from all users except the one who created it.</span></span> <span data-ttu-id="49df1-116">Weitere Informationen zum Sichtbarmachen der Gruppe finden Sie unter [Sichtbarmachen einer Attributgruppe für Benutzer &#40;Master Data Services&#41;](make-an-attribute-group-visible-to-users-master-data-services.md)angezeigt.</span><span class="sxs-lookup"><span data-stu-id="49df1-116">For more information about making the group visible, see [Make an Attribute Group Visible to Users &#40;Master Data Services&#41;](make-an-attribute-group-visible-to-users-master-data-services.md).</span></span>  
  
 <span data-ttu-id="49df1-117">Wenn Sie ein bestimmtes Attribut innerhalb einer Gruppe ausblenden möchten, können Sie dem Attribut die Berechtigung **Verweigern** zuweisen.</span><span class="sxs-lookup"><span data-stu-id="49df1-117">If you want to hide a specific attribute within a group, you can assign **Deny** permission to the attribute.</span></span> <span data-ttu-id="49df1-118">Weitere Informationen finden Sie unter [Blattberechtigungen &#40;Master Data Services&#41;](../../2014/master-data-services/leaf-permissions-master-data-services.md) oder [Konsolidierte Berechtigungen &#40;Master Data Services&#41;](../../2014/master-data-services/consolidated-permissions-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="49df1-118">For more information, see [Leaf Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/leaf-permissions-master-data-services.md) or [Consolidated Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/consolidated-permissions-master-data-services.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="49df1-119">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="49df1-119">Related Tasks</span></span>  
  
|<span data-ttu-id="49df1-120">Taskbeschreibung</span><span class="sxs-lookup"><span data-stu-id="49df1-120">Task Description</span></span>|<span data-ttu-id="49df1-121">Thema</span><span class="sxs-lookup"><span data-stu-id="49df1-121">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="49df1-122">Erstellen Sie eine neue Attributgruppe, und fügen Sie ihr Attribute hinzu.</span><span class="sxs-lookup"><span data-stu-id="49df1-122">Create a new attribute group and add attributes to it.</span></span>|[<span data-ttu-id="49df1-123">Erstellen einer Attributgruppe &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="49df1-123">Create an Attribute Group &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-an-attribute-group-master-data-services.md)|  
|<span data-ttu-id="49df1-124">Machen Sie eine Attributgruppe für Benutzer sichtbar.</span><span class="sxs-lookup"><span data-stu-id="49df1-124">Make an attribute group visible to users.</span></span>|[<span data-ttu-id="49df1-125">Sichtbarmachen einer Attributgruppe für Benutzer &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="49df1-125">Make an Attribute Group Visible to Users &#40;Master Data Services&#41;</span></span>](make-an-attribute-group-visible-to-users-master-data-services.md)|  
|<span data-ttu-id="49df1-126">Ändern Sie den Namen einer vorhandenen Attributgruppe.</span><span class="sxs-lookup"><span data-stu-id="49df1-126">Change the name of an existing attribute group.</span></span>|[<span data-ttu-id="49df1-127">Ändern des Namens einer Attributgruppe &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="49df1-127">Change an Attribute Group Name &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/change-an-attribute-group-name-master-data-services.md)|  
|<span data-ttu-id="49df1-128">Löschen Sie eine vorhandeme Attributgruppe.</span><span class="sxs-lookup"><span data-stu-id="49df1-128">Delete an existing attribute group.</span></span>|[<span data-ttu-id="49df1-129">Löschen einer Attributgruppe &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="49df1-129">Delete an Attribute Group &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/delete-an-attribute-group-master-data-services.md)|  
  
## <a name="related-content"></a><span data-ttu-id="49df1-130">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="49df1-130">Related Content</span></span>  
  
-   [<span data-ttu-id="49df1-131">Attribute &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="49df1-131">Attributes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/attributes-master-data-services.md)  
  
  
