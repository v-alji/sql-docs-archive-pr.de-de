---
title: Hinzufügen von Attributen zu einer Änderungsnachverfolgungsgruppe (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- change tracking groups [Master Data Services]
- attributes [Master Data Services], change tracking groups
- change tracking groups [Master Data Services], adding attributes
ms.assetid: e153eb5f-70ca-4c6f-89d8-1f937ed3917d
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c8a13dad3ca886668c96c1886f8cd238d9adad9f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622196"
---
# <a name="add-attributes-to-a-change-tracking-group-master-data-services"></a><span data-ttu-id="0f205-102">Hinzufügen von Attributen zu einer Änderungsnachverfolgungsgruppe (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="0f205-102">Add Attributes to a Change Tracking Group (Master Data Services)</span></span>
  <span data-ttu-id="0f205-103">Fügen Sie in [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]einer Änderungsnachverfolgungsgruppe Attribute hinzu, wenn Sie Änderungen an den Werten des Attributs nachverfolgen möchten.</span><span class="sxs-lookup"><span data-stu-id="0f205-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], add attributes to a change tracking group when you want to track changes to the attribute's values.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0f205-104">Nachdem Sie einer Änderungsnachverfolgungsgruppe ein Attribut hinzugefügt haben, wird das Attribut in der [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] -Datenbank als geändert markiert, wenn die Werte für das Attribut geändert werden.</span><span class="sxs-lookup"><span data-stu-id="0f205-104">After you add an attribute to a change tracking group, when values for the attribute change, the attribute is flagged as changed in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="0f205-105">Erstellen Sie eine Geschäftsregel, um auf der Grundlage der Änderung zu handeln.</span><span class="sxs-lookup"><span data-stu-id="0f205-105">Create a business rule to take action based on the change.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0f205-106">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="0f205-106">Prerequisites</span></span>  
 <span data-ttu-id="0f205-107">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="0f205-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="0f205-108">Sie müssen über die Berechtigung verfügen, auf den Funktionsbereich **System Verwaltung** zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="0f205-108">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="0f205-109">Sie müssen ein Modelladministrator sein.</span><span class="sxs-lookup"><span data-stu-id="0f205-109">You must be a model administrator.</span></span> <span data-ttu-id="0f205-110">Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="0f205-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="0f205-111">Attribute müssen vorhanden sein, um sie der Änderungsnachverfolgungsgruppe hinzufügen zu können.</span><span class="sxs-lookup"><span data-stu-id="0f205-111">Attributes must exist to add to the change tracking group.</span></span> <span data-ttu-id="0f205-112">Weitere Informationen finden Sie unter [Erstellen eines Textattributs &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-text-attribute-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="0f205-112">For more information, see [Create a Text Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-text-attribute-master-data-services.md).</span></span>  
  
### <a name="to-add-attributes-to-a-change-tracking-group"></a><span data-ttu-id="0f205-113">So fügen Sie einer Änderungnachverfolgungsgruppe Attribute hinzu</span><span class="sxs-lookup"><span data-stu-id="0f205-113">To add attributes to a change tracking group</span></span>  
  
1.  <span data-ttu-id="0f205-114">Klicken Sie in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]auf **Systemverwaltung**.</span><span class="sxs-lookup"><span data-stu-id="0f205-114">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="0f205-115">Zeigen Sie auf der Seite **Modell-Explorer** auf der Menüleiste auf **Verwalten** , und klicken Sie auf **Entitäten**.</span><span class="sxs-lookup"><span data-stu-id="0f205-115">On the **Model Explorer** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="0f205-116">Wählen Sie auf der Seite **Entitätsverwaltung** aus der Liste **Modell** ein Modell aus.</span><span class="sxs-lookup"><span data-stu-id="0f205-116">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="0f205-117">Wählen Sie die Zeile für die Entität aus, für die Sie Attributwerte verfolgen möchten.</span><span class="sxs-lookup"><span data-stu-id="0f205-117">Select the row for the entity that you want to track attribute values for.</span></span>  
  
5.  <span data-ttu-id="0f205-118">Klicken Sie auf **Ausgewählte Entität bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="0f205-118">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="0f205-119">Auf der Seite **Entität bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="0f205-119">On the **Edit Entity** page:</span></span>  
  
    -   <span data-ttu-id="0f205-120">Wenn das Attribut für Blatt Elemente vorgesehen ist, wählen Sie im Bereich **Blatt Attribute** das Attribut aus, und klicken Sie auf **Blatt Attribut bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="0f205-120">If the attribute is for leaf members, in the **Leaf attributes** pane, select the attribute and click **Edit leaf attribute**.</span></span>  
  
    -   <span data-ttu-id="0f205-121">Wenn das Attribut für konsolidierte Elemente vorgesehen ist, wählen Sie im Bereich **konsolidierte Attribute** das Attribut aus, und klicken Sie auf **konsolidiertes Attribut bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="0f205-121">If the attribute is for consolidated members, in the **Consolidated attributes** pane, select the attribute and click **Edit consolidated attribute**.</span></span>  
  
    -   <span data-ttu-id="0f205-122">Wenn das Attribut für Auflistungen ist, wählen Sie im Bereich Auflistungs **Attribute** das Attribut aus, und klicken Sie auf **Sammlungs Attribut bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="0f205-122">If the attribute is for collections, in the **Collection attributes** pane, select the attribute and click **Edit collection attribute**.</span></span>  
  
7.  <span data-ttu-id="0f205-123">Aktivieren Sie das Kontrollkästchen **Änderungsverfolgung aktivieren** .</span><span class="sxs-lookup"><span data-stu-id="0f205-123">Select the **Enable change tracking** check box.</span></span>  
  
8.  <span data-ttu-id="0f205-124">Geben Sie im Feld **Änderungsverfolgungsgruppe** eine Zahl für die Gruppe ein.</span><span class="sxs-lookup"><span data-stu-id="0f205-124">In the **Change tracking group** box, type a number for the group.</span></span>  
  
9. <span data-ttu-id="0f205-125">Klicken Sie auf **Attribut speichern**.</span><span class="sxs-lookup"><span data-stu-id="0f205-125">Click **Save attribute**.</span></span>  
  
10. <span data-ttu-id="0f205-126">Klicken Sie auf der Seite **Entitätsverwaltung** auf **Entität speichern**.</span><span class="sxs-lookup"><span data-stu-id="0f205-126">On the **Entity Maintenance** page, click **Save entity**.</span></span>  
  
11. <span data-ttu-id="0f205-127">Wiederholen Sie diese Prozedur für alle Attribute, die Sie in die Gruppe einschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="0f205-127">Repeat this procedure for all attributes you want to include in the group.</span></span> <span data-ttu-id="0f205-128">Verwenden Sie die gleiche Änderungsnachverfolgungs-Gruppennummer für jedes Attribut in der Gruppe.</span><span class="sxs-lookup"><span data-stu-id="0f205-128">Use the same change tracking group number for each attribute in the group.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="0f205-129">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="0f205-129">Next Steps</span></span>  
  
-   [<span data-ttu-id="0f205-130">Initiieren von Aktionen auf der Grundlage von Attributwertänderungen &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="0f205-130">Initiate Actions Based on Attribute Value Changes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/initiate-actions-based-on-attribute-value-changes-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="0f205-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0f205-131">See Also</span></span>  
 <span data-ttu-id="0f205-132">[Erstellen Sie ein Text Attribut &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-text-attribute-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="0f205-132">[Create a Text Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-text-attribute-master-data-services.md) </span></span>  
 [<span data-ttu-id="0f205-133">Erstellen eines domänenbasierten Attributs &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="0f205-133">Create a Domain-Based Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md)  
  
  
