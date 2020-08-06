---
title: Erstellen eines domänenbasierten Attributs (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- domain-based attributes [Master Data Services], creating
- creating domain-based attributes [Master Data Services]
- attributes [Master Data Services], creating domain-based attributes
ms.assetid: 11c31c9f-e6cc-47b7-b76a-d691f84c93c6
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 51c0f44bb76ae2ad4c25987ed5e5ee144a18c739
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609935"
---
# <a name="create-a-domain-based-attribute-master-data-services"></a><span data-ttu-id="3edfe-102">Erstellen eines domänenbasierten Attributs (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="3edfe-102">Create a Domain-Based Attribute (Master Data Services)</span></span>
  <span data-ttu-id="3edfe-103">Erstellen Sie in [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]ein domänenbasiertes Attribut, um die Werte eines Attributs mit Elementen aus einer Entität aufzufüllen.</span><span class="sxs-lookup"><span data-stu-id="3edfe-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a domain-based attribute to populate an attribute's values with members from an entity.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3edfe-104">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="3edfe-104">Prerequisites</span></span>  
 <span data-ttu-id="3edfe-105">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="3edfe-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="3edfe-106">Sie müssen über die Berechtigung verfügen, auf den Funktionsbereich **System Verwaltung** zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="3edfe-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="3edfe-107">Sie müssen ein Modelladministrator sein.</span><span class="sxs-lookup"><span data-stu-id="3edfe-107">You must be a model administrator.</span></span> <span data-ttu-id="3edfe-108">Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="3edfe-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="3edfe-109">Eine Entität muss vorhanden sein, um als Quelle der Attributwerte verwendet zu werden.</span><span class="sxs-lookup"><span data-stu-id="3edfe-109">An entity must exist to use as the source of the attribute values.</span></span> <span data-ttu-id="3edfe-110">Um zum Beispiel auf der Grundlage der Color-Entität ein domänenbasiertes Attribut zu erstellen, müssen Sie zuerst die Color-Entität erstellen.</span><span class="sxs-lookup"><span data-stu-id="3edfe-110">For example, to create a domain-based attribute based on the Color entity, you must first create the Color entity.</span></span> <span data-ttu-id="3edfe-111">Weitere Informationen finden Sie unter [Erstellen einer Entität &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="3edfe-111">For more information, see [Create an Entity &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="3edfe-112">Eine Entität muss vorhanden sein, um das Attribut dafür erstellen zu können.</span><span class="sxs-lookup"><span data-stu-id="3edfe-112">An entity must exist to create the attribute for.</span></span> <span data-ttu-id="3edfe-113">Weitere Informationen finden Sie unter [Erstellen einer Entität &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="3edfe-113">For more information, see [Create an Entity &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span></span>  
  
### <a name="to-create-a-domain-based-attribute"></a><span data-ttu-id="3edfe-114">So erstellen Sie ein domänenbasiertes Attribut</span><span class="sxs-lookup"><span data-stu-id="3edfe-114">To create a domain-based attribute</span></span>  
  
1.  <span data-ttu-id="3edfe-115">Klicken Sie in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]auf **Systemverwaltung**.</span><span class="sxs-lookup"><span data-stu-id="3edfe-115">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="3edfe-116">Zeigen Sie auf der Seite **Modellansicht** auf der Menüleiste auf **Verwalten** , und klicken Sie auf **Entitäten**.</span><span class="sxs-lookup"><span data-stu-id="3edfe-116">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="3edfe-117">Wählen Sie auf der Seite **Entitätsverwaltung** aus der Liste **Modell** ein Modell aus.</span><span class="sxs-lookup"><span data-stu-id="3edfe-117">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="3edfe-118">Wählen Sie die Zeile für die Entität aus, für die Sie ein Attribut erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="3edfe-118">Select the row for the entity that you want to create an attribute for.</span></span>  
  
5.  <span data-ttu-id="3edfe-119">Klicken Sie auf **Ausgewählte Entität bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="3edfe-119">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="3edfe-120">Auf der Seite **Entität bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="3edfe-120">On the **Edit Entity** page:</span></span>  
  
    -   <span data-ttu-id="3edfe-121">Wenn das Attribut für Blattelemente bestimmt ist, klicken Sie im Bereich **Blattelementattribute** auf **Blattattribut hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="3edfe-121">If the attribute is for leaf members, in the **Leaf member attributes** pane, click **Add leaf attribute**.</span></span>  
  
    -   <span data-ttu-id="3edfe-122">Wenn das Attribut für konsolidierte Elemente bestimmt ist, klicken Sie im Bereich **Konsolidierte Elementattribute** auf **Konsolidiertes Attribut hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="3edfe-122">If the attribute is for consolidated members, in the **Consolidated member attributes** pane, click **Add consolidated attribute**.</span></span>  
  
    -   <span data-ttu-id="3edfe-123">Wenn das Attribut für Auflistungen bestimmt ist, klicken Sie im Bereich **Auflistungsattribute** auf **Auflistungsattribut hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="3edfe-123">If the attribute is for collections, in the **Collection attributes** pane, click **Add collection attribute**.</span></span>  
  
7.  <span data-ttu-id="3edfe-124">Wählen Sie auf der Seite **Attribut hinzufügen** die Option **Domänen basiert** aus.</span><span class="sxs-lookup"><span data-stu-id="3edfe-124">On the **Add Attribute** page, select the **Domain-based** option.</span></span>  
  
8.  <span data-ttu-id="3edfe-125">Geben Sie im Feld **Name** einen Namen für das Attribut ein.</span><span class="sxs-lookup"><span data-stu-id="3edfe-125">In the **Name** box, type a name for the attribute.</span></span> <span data-ttu-id="3edfe-126">Es muss nicht der gleiche Name wie derjenige der Entität sein, die Sie für die Quelle der Attributwerte verwenden.</span><span class="sxs-lookup"><span data-stu-id="3edfe-126">It does not have to be the same name as the entity that you use for the source of the attribute values.</span></span>  
  
9. <span data-ttu-id="3edfe-127">Geben Sie im Feld **Pixelbreite anzeigen** die Breite der Attributspalte ein, die im **Explorerraster** angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="3edfe-127">In the **Display pixel width** box, type the width of the attribute column to be displayed in the **Explorer** grid.</span></span>  
  
10. <span data-ttu-id="3edfe-128">Wählen Sie in der Liste **Entität** die Entität aus, die verwendet werden soll, um die Attributwerte aufzufüllen.</span><span class="sxs-lookup"><span data-stu-id="3edfe-128">From the **Entity** list, choose the entity to be used to populate the attribute values.</span></span>  
  
11. <span data-ttu-id="3edfe-129">Optional.</span><span class="sxs-lookup"><span data-stu-id="3edfe-129">Optional.</span></span> <span data-ttu-id="3edfe-130">Wählen Sie **Änderungsnachverfolgung aktivieren** aus, um Änderungen an Gruppen von Attributen nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="3edfe-130">Select **Enable change tracking** to track changes to groups of attributes.</span></span> <span data-ttu-id="3edfe-131">Weitere Informationen finden Sie unter [Hinzufügen von Attributen zu einer Änderungsnachverfolgungsgruppe &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="3edfe-131">For more information, see [Add Attributes to a Change Tracking Group &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md).</span></span>  
  
12. <span data-ttu-id="3edfe-132">Klicken Sie auf **Attribut speichern**.</span><span class="sxs-lookup"><span data-stu-id="3edfe-132">Click **Save attribute**.</span></span>  
  
13. <span data-ttu-id="3edfe-133">Klicken Sie auf der Seite **Entitätsverwaltung** auf **Entität speichern**.</span><span class="sxs-lookup"><span data-stu-id="3edfe-133">On the **Entity Maintenance** page, click **Save entity**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3edfe-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3edfe-134">See Also</span></span>  
 <span data-ttu-id="3edfe-135">[Domänen basierte Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/domain-based-attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="3edfe-135">[Domain-Based Attributes &#40;Master Data Services&#41;](../../2014/master-data-services/domain-based-attributes-master-data-services.md) </span></span>  
 <span data-ttu-id="3edfe-136">[Erstellen Sie eine abgeleitete Hierarchie &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-derived-hierarchy-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="3edfe-136">[Create a Derived Hierarchy &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-derived-hierarchy-master-data-services.md) </span></span>  
 <span data-ttu-id="3edfe-137">[Ändern eines Attribut namens &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="3edfe-137">[Change an Attribute Name &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span></span>  
 [<span data-ttu-id="3edfe-138">Löschen eines Attributs &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="3edfe-138">Delete an Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/delete-an-attribute-master-data-services.md)  
  
  
