---
title: Zuweisen von Hierarchieelementberechtigungen (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- permissions [Master Data Services], assigning member permissions
- members [Master Data Services], assigning permissions
ms.assetid: e1b8b46a-7cd1-4a7d-9345-dd7df081e145
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 4a1602f9fe351f826b63d4447f90dcf02a10f49e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618779"
---
# <a name="assign-hierarchy-member-permissions-master-data-services"></a><span data-ttu-id="e799b-102">Zuweisen von Hierarchieelementberechtigungen (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="e799b-102">Assign Hierarchy Member Permissions (Master Data Services)</span></span>
  <span data-ttu-id="e799b-103">Weisen Sie Hierarchieelementen Berechtigungen zu, um Benutzer oder Gruppen Zugriff auf die Anzeige von Daten im Funktionsbereich **Explorer** von [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]zu geben.</span><span class="sxs-lookup"><span data-stu-id="e799b-103">Assign permissions to hierarchy members to give users or groups access to view data in the **Explorer** functional area of [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span></span>  
  
 <span data-ttu-id="e799b-104">Hierarchieelementberechtigungen sind optional.</span><span class="sxs-lookup"><span data-stu-id="e799b-104">Hierarchy member permissions are optional.</span></span> <span data-ttu-id="e799b-105">Sie bieten zusätzliche Granularität für die Modellierung von Objektberechtigungen; diese sind erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e799b-105">They provide added granularity to model object permissions, which are required.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e799b-106">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="e799b-106">Prerequisites</span></span>  
 <span data-ttu-id="e799b-107">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="e799b-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="e799b-108">Sie müssen über die Berechtigung verfügen, auf den Funktionsbereich **Benutzer- und Gruppenberechtigungen** zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="e799b-108">You must have permission to access the **Users and Group Permissions** functional area.</span></span>  
  
-   <span data-ttu-id="e799b-109">Sie müssen ein Modelladministrator sein.</span><span class="sxs-lookup"><span data-stu-id="e799b-109">You must be a model administrator.</span></span> <span data-ttu-id="e799b-110">Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="e799b-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-assign-hierarchy-member-permissions"></a><span data-ttu-id="e799b-111">So weisen Sie Hierarchieelementberechtigungen zu</span><span class="sxs-lookup"><span data-stu-id="e799b-111">To assign hierarchy member permissions</span></span>  
  
1.  <span data-ttu-id="e799b-112">Klicken Sie in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]auf **Benutzer- und Gruppenberechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="e799b-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **User and Group Permissions**.</span></span>  
  
2.  <span data-ttu-id="e799b-113">Wählen Sie auf der Seite **Benutzer** oder **Gruppen** die Zeile für den Benutzer oder die Gruppe aus, den bzw. die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="e799b-113">On the **Users** or **Groups** page, select the row for the user or group that you want to edit.</span></span>  
  
3.  <span data-ttu-id="e799b-114">Klicken Sie auf **Ausgewähltem Benutzer bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="e799b-114">Click **Edit selected user**.</span></span>  
  
4.  <span data-ttu-id="e799b-115">Klicken Sie auf die Registerkarte **Hierarchieelemente** .</span><span class="sxs-lookup"><span data-stu-id="e799b-115">Click the **Hierarchy Members** tab.</span></span>  
  
5.  <span data-ttu-id="e799b-116">Wählen Sie aus der Liste **Modell** ein Modell aus.</span><span class="sxs-lookup"><span data-stu-id="e799b-116">From the **Model** list, select a model.</span></span>  
  
6.  <span data-ttu-id="e799b-117">Wählen Sie aus der Liste **Version** eine Version aus.</span><span class="sxs-lookup"><span data-stu-id="e799b-117">From the **Version** list, select a version.</span></span>  
  
7.  <span data-ttu-id="e799b-118">Wählen Sie aus der Liste **Hierarchie** eine Hierarchie aus.</span><span class="sxs-lookup"><span data-stu-id="e799b-118">From the **Hierarchy** list, select a hierarchy.</span></span>  
  
8.  <span data-ttu-id="e799b-119">Klicken Sie auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="e799b-119">Click **Edit**.</span></span>  
  
9. <span data-ttu-id="e799b-120">Erweitern Sie die Struktur, und klicken Sie auf den Hierarchieknoten, dem Sie Berechtigungen zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="e799b-120">Expand the tree, and click the hierarchy node you want to assign permissions to.</span></span>  
  
10. <span data-ttu-id="e799b-121">**Wählen Sie**im Menü die Option schreibgeschützt, **Aktualisieren**oder **verweigern**aus.</span><span class="sxs-lookup"><span data-stu-id="e799b-121">From the menu, select **Read-only**, **Update**, or **Deny**.</span></span>  
  
11. <span data-ttu-id="e799b-122">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="e799b-122">Click **Save**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e799b-123">Hierarchieelementberechtigungen werden nicht sofort wirksam.</span><span class="sxs-lookup"><span data-stu-id="e799b-123">Hierarchy member permissions do not take effect immediately.</span></span> <span data-ttu-id="e799b-124">Weitere Informationen finden Sie unter [Sofortiges Anwenden von Elementberechtigungen &#40;Master Data Services&#41;](../../2014/master-data-services/immediately-apply-member-permissions-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="e799b-124">See [Immediately Apply Member Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/immediately-apply-member-permissions-master-data-services.md) for more information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e799b-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e799b-125">See Also</span></span>  
 <span data-ttu-id="e799b-126">[Löschen von Hierarchie Element Berechtigungen &#40;Master Data Services&#41;](../../2014/master-data-services/delete-hierarchy-member-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="e799b-126">[Delete Hierarchy Member Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/delete-hierarchy-member-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="e799b-127">[Zuweisen von Berechtigungen für Modell Objekte &#40;Master Data Services&#41;](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="e799b-127">[Assign Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md) </span></span>  
 [<span data-ttu-id="e799b-128">Berechtigungen für Hierarchieelemente &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="e799b-128">Hierarchy Member Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/hierarchy-member-permissions-master-data-services.md)  
  
  
