---
title: Erstellen einer Attributgruppe (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- attribute groups [Master Data Services], creating
- creating attribute groups [Master Data Services]
ms.assetid: 798c325e-e8d8-412a-b02e-118f2741d1c7
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: fbd95869082ea0a73f3abea092163c4705e4da5c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721542"
---
# <a name="create-an-attribute-group-master-data-services"></a><span data-ttu-id="bf802-102">Erstellen einer Attributgruppe (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="bf802-102">Create an Attribute Group (Master Data Services)</span></span>
  <span data-ttu-id="bf802-103">Erstellen Sie in [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]Attributgruppen, wenn Sie Attribute auf einzelnen Registerkarten im **Explorerraster** anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="bf802-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create attribute groups when you want to display attributes on individual tabs in the **Explorer** grid.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bf802-104">Beim Erstellen einer Attributgruppe wird diese automatisch für alle Benutzer bis auf den Ersteller ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="bf802-104">When you create an attribute group, it is automatically hidden from all users except the one who created it.</span></span> <span data-ttu-id="bf802-105">Weitere Informationen zum Sichtbarmachen der Gruppe finden Sie unter [Sichtbarmachen einer Attributgruppe für Benutzer &#40;Master Data Services&#41;](make-an-attribute-group-visible-to-users-master-data-services.md)angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bf802-105">For more information about making the group visible, see [Make an Attribute Group Visible to Users &#40;Master Data Services&#41;](make-an-attribute-group-visible-to-users-master-data-services.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="bf802-106">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="bf802-106">Prerequisites</span></span>  
 <span data-ttu-id="bf802-107">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="bf802-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="bf802-108">Sie müssen über die Berechtigung verfügen, auf den Funktionsbereich **System Verwaltung** zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="bf802-108">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="bf802-109">Sie müssen ein Modelladministrator sein.</span><span class="sxs-lookup"><span data-stu-id="bf802-109">You must be a model administrator.</span></span> <span data-ttu-id="bf802-110">Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="bf802-110">For more information, see [Administrators &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="bf802-111">Es muss mindestens ein Attribut vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="bf802-111">At least one attribute must exist.</span></span> <span data-ttu-id="bf802-112">Weitere Informationen finden Sie unter [Erstellen eines Textattributs &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-text-attribute-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="bf802-112">For more information, see [Create a Text Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-text-attribute-master-data-services.md).</span></span>  
  
### <a name="to-create-an-attribute-group"></a><span data-ttu-id="bf802-113">So erstellen Sie eine Attributgruppe</span><span class="sxs-lookup"><span data-stu-id="bf802-113">To create an attribute group</span></span>  
  
1.  <span data-ttu-id="bf802-114">Klicken Sie in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]auf **Systemverwaltung**.</span><span class="sxs-lookup"><span data-stu-id="bf802-114">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="bf802-115">Zeigen Sie auf der Seite **Modell Ansicht** auf der Menüleiste auf **Verwalten** , und klicken Sie auf **Attribut Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="bf802-115">On the **Model View** page, from the menu bar, point to **Manage** and click **Attribute Groups**.</span></span>  
  
3.  <span data-ttu-id="bf802-116">Wählen Sie aus der Liste **Modell** ein Modell aus.</span><span class="sxs-lookup"><span data-stu-id="bf802-116">From the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="bf802-117">Wählen Sie aus der Liste **Entität** eine Entität aus.</span><span class="sxs-lookup"><span data-stu-id="bf802-117">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="bf802-118">Klicken Sie auf **Blattgruppen**, **Konsolidierte Gruppen**oder **Auflistungsgruppen** , um eine Attributgruppe von Blattelementen, konsolidierten Elementen oder Auflistungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="bf802-118">Click **Leaf Groups**, **Consolidated Groups**, or **Collection Groups** to create an attribute group of leaf members, consolidated members, or collections respectively.</span></span>  
  
6.  <span data-ttu-id="bf802-119">Klicken Sie auf **Attribut Gruppe hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="bf802-119">Click **Add attribute group**.</span></span>  
  
7.  <span data-ttu-id="bf802-120">Geben Sie im Feld **Name der Blatt Gruppe** einen Namen für die Gruppe ein.</span><span class="sxs-lookup"><span data-stu-id="bf802-120">In the **Leaf group name** box, type a name for the group.</span></span> <span data-ttu-id="bf802-121">Dies ist der Name, der auf der Registerkarte im **Explorer**angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="bf802-121">This is the name displayed on the tab in **Explorer**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bf802-122">Wenn Sie in Schritt 5 **konsolidierte Gruppen** oder **Sammlungs Gruppen** ausgewählt haben, ist dieses Feld der **konsolidierte Gruppenname** bzw. der **Name der Sammlungs Gruppe**.</span><span class="sxs-lookup"><span data-stu-id="bf802-122">If you selected **Consolidated Groups** or **Collection Groups** in step 5, this box is **Consolidated group name** or **Collection group name**, respectively.</span></span>  
  
8.  <span data-ttu-id="bf802-123">Klicken Sie auf **Gruppe speichern**.</span><span class="sxs-lookup"><span data-stu-id="bf802-123">Click **Save group**.</span></span>  
  
9. <span data-ttu-id="bf802-124">Erweitern Sie den Ordner für die Gruppe.</span><span class="sxs-lookup"><span data-stu-id="bf802-124">Expand the folder for the group.</span></span>  
  
10. <span data-ttu-id="bf802-125">Klicken Sie auf **Attribute**.</span><span class="sxs-lookup"><span data-stu-id="bf802-125">Click **Attributes**.</span></span>  
  
11. <span data-ttu-id="bf802-126">Klicken Sie auf **ausgewähltes Element bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="bf802-126">Click **Edit selected item**.</span></span>  
  
12. <span data-ttu-id="bf802-127">Klicken Sie im Feld **verfügbar** auf Attribute, und klicken Sie auf den Pfeil **Hinzufügen** .</span><span class="sxs-lookup"><span data-stu-id="bf802-127">Click attributes in the **Available** box and click the **Add** arrow.</span></span> <span data-ttu-id="bf802-128">Klicken Sie auf den Pfeil für **Alle hinzufügen** , um alles hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="bf802-128">To add all, click the **Add All** arrow.</span></span>  
  
13. <span data-ttu-id="bf802-129">Klicken Sie optional auf die Pfeile nach **oben** und **nach unten** , um die Reihenfolge der Attribute von links nach rechts zu ändern.</span><span class="sxs-lookup"><span data-stu-id="bf802-129">Optionally, click the **Up** and **Down** arrows to change the left-to-right order of the attributes.</span></span>  
  
14. <span data-ttu-id="bf802-130">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="bf802-130">Click **Save**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="bf802-131">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="bf802-131">Next Steps</span></span>  
  
-   [<span data-ttu-id="bf802-132">Sichtbarmachen einer Attributgruppe für Benutzer &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="bf802-132">Make an Attribute Group Visible to Users &#40;Master Data Services&#41;</span></span>](make-an-attribute-group-visible-to-users-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="bf802-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bf802-133">See Also</span></span>  
 <span data-ttu-id="bf802-134">[Attribut Gruppen &#40;Master Data Services&#41;](../../2014/master-data-services/attribute-groups-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="bf802-134">[Attribute Groups &#40;Master Data Services&#41;](../../2014/master-data-services/attribute-groups-master-data-services.md) </span></span>  
 <span data-ttu-id="bf802-135">[Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="bf802-135">[Attributes &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span></span>  
 <span data-ttu-id="bf802-136">[Ändern Sie den Namen einer Attribut Gruppe &#40;Master Data Services&#41;](../../2014/master-data-services/change-an-attribute-group-name-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="bf802-136">[Change an Attribute Group Name &#40;Master Data Services&#41;](../../2014/master-data-services/change-an-attribute-group-name-master-data-services.md) </span></span>  
 <span data-ttu-id="bf802-137">[Löschen Sie eine Attribut Gruppe &#40;Master Data Services&#41;](../../2014/master-data-services/delete-an-attribute-group-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="bf802-137">[Delete an Attribute Group &#40;Master Data Services&#41;](../../2014/master-data-services/delete-an-attribute-group-master-data-services.md) </span></span>  
 <span data-ttu-id="bf802-138">[Blatt Berechtigungen &#40;Master Data Services&#41;](../../2014/master-data-services/leaf-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="bf802-138">[Leaf Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/leaf-permissions-master-data-services.md) </span></span>  
 [<span data-ttu-id="bf802-139">Konsolidierte Berechtigungen &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="bf802-139">Consolidated Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/consolidated-permissions-master-data-services.md)  
  
  
