---
title: Erstellen eines numerischen Attributs (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- attributes [Master Data Services], creating number attributes
- creating number attributes [Master Data Services]
ms.assetid: c0dbb6d8-ba78-485a-a40d-6d5cb7e75d0a
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: bb9302c0b585c21410a6a764dc2e6dac845c6299
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607879"
---
# <a name="create-a-numeric-attribute-master-data-services"></a><span data-ttu-id="b4f44-102">Erstellen eines numerischen Attributs (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="b4f44-102">Create a Numeric Attribute (Master Data Services)</span></span>
  <span data-ttu-id="b4f44-103">Erstellen Sie in [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]ein numerisches Attribut, wenn Sie möchten, dass Benutzer eine Zahl als Attributwert eingeben.</span><span class="sxs-lookup"><span data-stu-id="b4f44-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a numeric attribute when you want users to enter a number as an attribute value.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b4f44-104">Numerische Attribute weisen bestimmte Einschränkungen auf.</span><span class="sxs-lookup"><span data-stu-id="b4f44-104">Numeric attributes have limitations.</span></span> <span data-ttu-id="b4f44-105">Weitere Informationen finden Sie unter [Attribute &#40;Master Data Services&#41;](attributes-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="b4f44-105">For more information, see [Attributes &#40;Master Data Services&#41;](attributes-master-data-services.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b4f44-106">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="b4f44-106">Prerequisites</span></span>  
 <span data-ttu-id="b4f44-107">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="b4f44-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="b4f44-108">Sie müssen über die Berechtigung verfügen, auf den Funktionsbereich **System Verwaltung** zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="b4f44-108">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="b4f44-109">Sie müssen ein Modelladministrator sein.</span><span class="sxs-lookup"><span data-stu-id="b4f44-109">You must be a model administrator.</span></span> <span data-ttu-id="b4f44-110">Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="b4f44-110">For more information, see [Administrators &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="b4f44-111">Eine Entität muss vorhanden sein, um das Attribut dafür erstellen zu können.</span><span class="sxs-lookup"><span data-stu-id="b4f44-111">An entity must exist to create the attribute for.</span></span> <span data-ttu-id="b4f44-112">Weitere Informationen finden Sie unter [Erstellen einer Entität &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="b4f44-112">For more information, see [Create an Entity &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span></span>  
  
### <a name="to-create-a-numeric-attribute"></a><span data-ttu-id="b4f44-113">So erstellen Sie ein numerisches Attribut</span><span class="sxs-lookup"><span data-stu-id="b4f44-113">To create a numeric attribute</span></span>  
  
1.  <span data-ttu-id="b4f44-114">Klicken Sie in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]auf **Systemverwaltung**.</span><span class="sxs-lookup"><span data-stu-id="b4f44-114">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="b4f44-115">Zeigen Sie auf der Seite **Modellansicht** auf der Menüleiste auf **Verwalten** , und klicken Sie auf **Entitäten**.</span><span class="sxs-lookup"><span data-stu-id="b4f44-115">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="b4f44-116">Wählen Sie auf der Seite **Entitätsverwaltung** aus der Liste **Modell** ein Modell aus.</span><span class="sxs-lookup"><span data-stu-id="b4f44-116">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="b4f44-117">Wählen Sie die Zeile für die Entität aus, für die Sie ein Attribut erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="b4f44-117">Select the row for the entity that you want to create an attribute for.</span></span>  
  
5.  <span data-ttu-id="b4f44-118">Klicken Sie auf **Ausgewählte Entität bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="b4f44-118">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="b4f44-119">Auf der Seite **Entität bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="b4f44-119">On the **Edit Entity** page:</span></span>  
  
    -   <span data-ttu-id="b4f44-120">Wenn das Attribut für Blattelemente bestimmt ist, klicken Sie im Bereich **Blattelementattribute** auf **Blattattribut hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="b4f44-120">If the attribute is for leaf members, in the **Leaf member attributes** pane, click **Add leaf attribute**.</span></span>  
  
    -   <span data-ttu-id="b4f44-121">Wenn das Attribut für konsolidierte Elemente bestimmt ist, klicken Sie im Bereich **Konsolidierte Elementattribute** auf **Konsolidiertes Attribut hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="b4f44-121">If the attribute is for consolidated members, in the **Consolidated member attributes** pane, click **Add consolidated attribute**.</span></span>  
  
    -   <span data-ttu-id="b4f44-122">Wenn das Attribut für Auflistungen bestimmt ist, klicken Sie im Bereich **Auflistungsattribute** auf **Auflistungsattribut hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="b4f44-122">If the attribute is for collections, in the **Collection attributes** pane, click **Add collection attribute**.</span></span>  
  
7.  <span data-ttu-id="b4f44-123">Aktivieren Sie die Option **Freiform** auf der Seite **Attribut hinzufügen** .</span><span class="sxs-lookup"><span data-stu-id="b4f44-123">On the **Add Attribute** page, select the **Free-form** option.</span></span>  
  
8.  <span data-ttu-id="b4f44-124">Geben Sie im Feld **Name** einen Namen für das Attribut ein.</span><span class="sxs-lookup"><span data-stu-id="b4f44-124">In the **Name** box, type a name for the attribute.</span></span> <span data-ttu-id="b4f44-125">Eine Liste von Wörtern, die nicht als Attributnamen verwendet werden sollten, finden Sie unter [reservierte Wörter &#40;Master Data Services&#41;](../../2014/master-data-services/reserved-words-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="b4f44-125">For a list of words that should not be used as attribute names, see [Reserved Words &#40;Master Data Services&#41;](../../2014/master-data-services/reserved-words-master-data-services.md).</span></span>  
  
9. <span data-ttu-id="b4f44-126">Geben Sie im Feld **Pixelbreite anzeigen** die Breite der Attributspalte ein, die im **Explorerraster** angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="b4f44-126">In the **Display pixel width** box, type the width of the attribute column to be displayed in the **Explorer** grid.</span></span>  
  
10. <span data-ttu-id="b4f44-127">Wählen Sie aus der Liste **Datentyp\*\*\*\*Zahl**aus.</span><span class="sxs-lookup"><span data-stu-id="b4f44-127">From the **Data type** list, select **Number**.</span></span>  
  
11. <span data-ttu-id="b4f44-128">Geben Sie im Feld **Dezimalstellen** die Anzahl der Ziffern ein, die nach einem Dezimalzeichen eingegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="b4f44-128">In the **Decimals** box, type the number of numbers that can be entered after a decimal.</span></span>  
  
12. <span data-ttu-id="b4f44-129">Wählen Sie in der Liste **Eingabemaske** ein Format für negative Zahlen aus.</span><span class="sxs-lookup"><span data-stu-id="b4f44-129">From the **Input mask** list, select a format for negative numbers.</span></span>  
  
13. <span data-ttu-id="b4f44-130">Optional können Sie **Änderungsnachverfolgung aktivieren** auswählen, um Änderungen an Gruppen von Attributen nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="b4f44-130">Optionally, select **Enable change tracking** to track changes to groups of attributes.</span></span> <span data-ttu-id="b4f44-131">Weitere Informationen finden Sie unter [Hinzufügen von Attributen zu einer Änderungsnachverfolgungsgruppe &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md) .</span><span class="sxs-lookup"><span data-stu-id="b4f44-131">See [Add Attributes to a Change Tracking Group &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md) for more information.</span></span>  
  
14. <span data-ttu-id="b4f44-132">Klicken Sie auf **Attribut speichern**.</span><span class="sxs-lookup"><span data-stu-id="b4f44-132">Click **Save attribute**.</span></span>  
  
15. <span data-ttu-id="b4f44-133">Klicken Sie auf der Seite **Entitätsverwaltung** auf **Entität speichern**.</span><span class="sxs-lookup"><span data-stu-id="b4f44-133">On the **Entity Maintenance** page, click **Save entity**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4f44-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b4f44-134">See Also</span></span>  
 <span data-ttu-id="b4f44-135">[Attribute &#40;Master Data Services&#41;](attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="b4f44-135">[Attributes &#40;Master Data Services&#41;](attributes-master-data-services.md) </span></span>  
 <span data-ttu-id="b4f44-136">[Ändern eines Attribut namens &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="b4f44-136">[Change an Attribute Name &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span></span>  
 <span data-ttu-id="b4f44-137">[Erstellen eines domänenbasierten Attributs &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="b4f44-137">[Create a Domain-Based Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md) </span></span>  
 [<span data-ttu-id="b4f44-138">Erstellen eines Dateiattributs &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="b4f44-138">Create a File Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-file-attribute-master-data-services.md)  
  
  
