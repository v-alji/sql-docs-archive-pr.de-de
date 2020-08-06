---
title: Erstellen eines Linkattributs (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- attributes [Master Data Services], creating link attributes
- creating link attributes [Master Data Services]
ms.assetid: e6658e9c-5b08-4b8d-b556-17ec2dd041d2
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 4770d7904371c10dc6720e8d3d7f28ca797d9b80
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622756"
---
# <a name="create-a-link-attribute-master-data-services"></a><span data-ttu-id="0acff-102">Erstellen eines Linkattributs (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="0acff-102">Create a Link Attribute (Master Data Services)</span></span>
  <span data-ttu-id="0acff-103">Erstellen Sie in [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] ein Linkattribut, wenn Sie möchten, dass Benutzer einen Link als Attributwert eingeben, z.B. `http://www.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="0acff-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a link attribute when you want users to enter a hyperlink as an attribute value, such as `http://www.contoso.com`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0acff-104">Wenn Benutzer einen Wert für ein Linkattribut eingeben, muss die Zeichenfolge mit **http://** beginnen, oder ein Fehler wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0acff-104">When users enter a value for a link attribute, the string must begin with **http://** or an error will be displayed.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0acff-105">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="0acff-105">Prerequisites</span></span>  
 <span data-ttu-id="0acff-106">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="0acff-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="0acff-107">Sie müssen über die Berechtigung verfügen, auf den Funktionsbereich **System Verwaltung** zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="0acff-107">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="0acff-108">Sie müssen ein Modelladministrator sein.</span><span class="sxs-lookup"><span data-stu-id="0acff-108">You must be a model administrator.</span></span> <span data-ttu-id="0acff-109">Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="0acff-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="0acff-110">Eine Entität muss vorhanden sein, um das Attribut dafür erstellen zu können.</span><span class="sxs-lookup"><span data-stu-id="0acff-110">An entity must exist to create the attribute for.</span></span> <span data-ttu-id="0acff-111">Weitere Informationen finden Sie unter [Erstellen einer Entität &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="0acff-111">For more information, see [Create an Entity &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span></span>  
  
### <a name="to-create-a-link-attribute"></a><span data-ttu-id="0acff-112">So erstellen Sie ein Linkattribut</span><span class="sxs-lookup"><span data-stu-id="0acff-112">To create a link attribute</span></span>  
  
1.  <span data-ttu-id="0acff-113">Klicken Sie in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]auf **Systemverwaltung**.</span><span class="sxs-lookup"><span data-stu-id="0acff-113">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="0acff-114">Zeigen Sie auf der Seite **Modellansicht** auf der Menüleiste auf **Verwalten** , und klicken Sie auf **Entitäten**.</span><span class="sxs-lookup"><span data-stu-id="0acff-114">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="0acff-115">Wählen Sie auf der Seite **Entitätsverwaltung** aus der Liste **Modell** ein Modell aus.</span><span class="sxs-lookup"><span data-stu-id="0acff-115">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="0acff-116">Wählen Sie die Zeile für die Entität aus, für die Sie ein Attribut erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="0acff-116">Select the row for the entity that you want to create an attribute for.</span></span>  
  
5.  <span data-ttu-id="0acff-117">Klicken Sie auf **Ausgewählte Entität bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="0acff-117">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="0acff-118">Auf der Seite **Entität bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="0acff-118">On the **Edit Entity** page:</span></span>  
  
    -   <span data-ttu-id="0acff-119">Wenn das Attribut für Blattelemente bestimmt ist, klicken Sie im Bereich **Blattelementattribute** auf **Blattattribut hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="0acff-119">If the attribute is for leaf members, in the **Leaf member attributes** pane, click **Add leaf attribute**.</span></span>  
  
    -   <span data-ttu-id="0acff-120">Wenn das Attribut für konsolidierte Elemente bestimmt ist, klicken Sie im Bereich **Konsolidierte Elementattribute** auf **Konsolidiertes Attribut hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="0acff-120">If the attribute is for consolidated members, in the **Consolidated member attributes** pane, click **Add consolidated attribute**.</span></span>  
  
    -   <span data-ttu-id="0acff-121">Wenn das Attribut für Auflistungen bestimmt ist, klicken Sie im Bereich **Auflistungsattribute** auf **Auflistungsattribut hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="0acff-121">If the attribute is for collections, in the **Collection attributes** pane, click **Add collection attribute**.</span></span>  
  
7.  <span data-ttu-id="0acff-122">Aktivieren Sie die Option **Freiform** auf der Seite **Attribut hinzufügen** .</span><span class="sxs-lookup"><span data-stu-id="0acff-122">On the **Add Attribute** page, select the **Free-form** option.</span></span>  
  
8.  <span data-ttu-id="0acff-123">Geben Sie im Feld **Name** einen Namen für das Attribut ein.</span><span class="sxs-lookup"><span data-stu-id="0acff-123">In the **Name** box, type a name for the attribute.</span></span> <span data-ttu-id="0acff-124">Eine Liste von Wörtern, die nicht als Attributnamen verwendet werden sollten, finden Sie unter [reservierte Wörter &#40;Master Data Services&#41;](../../2014/master-data-services/reserved-words-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="0acff-124">For a list of words that should not be used as attribute names, see [Reserved Words &#40;Master Data Services&#41;](../../2014/master-data-services/reserved-words-master-data-services.md).</span></span>  
  
9. <span data-ttu-id="0acff-125">Geben Sie im Feld **Pixelbreite anzeigen** die Breite der Attributspalte ein, die im **Explorerraster** angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="0acff-125">In the **Display pixel width** box, type the width of the attribute column to be displayed in the **Explorer** grid.</span></span>  
  
10. <span data-ttu-id="0acff-126">Wählen Sie **Link** in der Liste **Datentyp**aus.</span><span class="sxs-lookup"><span data-stu-id="0acff-126">From the **Data type** list, select **Link**.</span></span>  
  
11. <span data-ttu-id="0acff-127">Geben Sie im Feld **Länge** die maximal zulässige Anzahl von Zeichen ein.</span><span class="sxs-lookup"><span data-stu-id="0acff-127">In the **Length** box, type the maximum number of characters allowed.</span></span>  
  
12. <span data-ttu-id="0acff-128">Optional können Sie **Änderungsnachverfolgung aktivieren** auswählen, um Änderungen an Gruppen von Attributen nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="0acff-128">Optionally, select **Enable change tracking** to track changes to groups of attributes.</span></span> <span data-ttu-id="0acff-129">Weitere Informationen finden Sie unter [Hinzufügen von Attributen zu einer Änderungsnachverfolgungsgruppe &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="0acff-129">For more information, see [Add Attributes to a Change Tracking Group &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md).</span></span>  
  
13. <span data-ttu-id="0acff-130">Klicken Sie auf **Attribut speichern**.</span><span class="sxs-lookup"><span data-stu-id="0acff-130">Click **Save attribute**.</span></span>  
  
14. <span data-ttu-id="0acff-131">Klicken Sie auf der Seite **Entitätsverwaltung** auf **Entität speichern**.</span><span class="sxs-lookup"><span data-stu-id="0acff-131">On the **Entity Maintenance** page, click **Save entity**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0acff-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0acff-132">See Also</span></span>  
 <span data-ttu-id="0acff-133">[Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="0acff-133">[Attributes &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span></span>  
 <span data-ttu-id="0acff-134">[Ändern eines Attribut namens &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="0acff-134">[Change an Attribute Name &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span></span>  
 <span data-ttu-id="0acff-135">[Erstellen eines domänenbasierten Attributs &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="0acff-135">[Create a Domain-Based Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md) </span></span>  
 [<span data-ttu-id="0acff-136">Erstellen eines Dateiattributs &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="0acff-136">Create a File Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-file-attribute-master-data-services.md)  
  
  
