---
title: Erstellen eines Dateiattributs (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- creating file attributes [Master Data Services]
- attributes [Master Data Services], creating file attributes
ms.assetid: d224886b-2ef1-4658-8b01-2213cc4b8df6
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: f4f6e2f10a830d089d1d217f7cf54d0b8557add9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609934"
---
# <a name="create-a-file-attribute-master-data-services"></a><span data-ttu-id="653f7-102">Erstellen eines Dateiattributs (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="653f7-102">Create a File Attribute (Master Data Services)</span></span>
  <span data-ttu-id="653f7-103">Erstellen Sie in [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]ein Dateiattribut, um Attributwerte mit Dateien aufzufüllen.</span><span class="sxs-lookup"><span data-stu-id="653f7-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a file attribute to populate attribute values with files.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="653f7-104">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="653f7-104">Prerequisites</span></span>  
 <span data-ttu-id="653f7-105">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="653f7-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="653f7-106">Sie müssen über die Berechtigung verfügen, auf den Funktionsbereich **System Verwaltung** zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="653f7-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="653f7-107">Sie müssen ein Modelladministrator sein.</span><span class="sxs-lookup"><span data-stu-id="653f7-107">You must be a model administrator.</span></span> <span data-ttu-id="653f7-108">Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="653f7-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="653f7-109">Eine Entität muss vorhanden sein, um das Attribut dafür erstellen zu können.</span><span class="sxs-lookup"><span data-stu-id="653f7-109">An entity must exist to create the attribute for.</span></span> <span data-ttu-id="653f7-110">Weitere Informationen finden Sie unter [Erstellen einer Entität &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="653f7-110">For more information, see [Create an Entity &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span></span>  
  
### <a name="to-create-a-file-attribute"></a><span data-ttu-id="653f7-111">So erstellen Sie ein Dateiattribut</span><span class="sxs-lookup"><span data-stu-id="653f7-111">To create a file attribute</span></span>  
  
1.  <span data-ttu-id="653f7-112">Klicken Sie in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]auf **Systemverwaltung**.</span><span class="sxs-lookup"><span data-stu-id="653f7-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="653f7-113">Zeigen Sie auf der Seite **Modellansicht** auf der Menüleiste auf **Verwalten** , und klicken Sie auf **Entitäten**.</span><span class="sxs-lookup"><span data-stu-id="653f7-113">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="653f7-114">Wählen Sie auf der Seite **Entitätsverwaltung** aus der Liste **Modell** ein Modell aus.</span><span class="sxs-lookup"><span data-stu-id="653f7-114">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="653f7-115">Wählen Sie die Zeile für die Entität aus, für die Sie ein Attribut erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="653f7-115">Select the row for the entity that you want to create an attribute for.</span></span>  
  
5.  <span data-ttu-id="653f7-116">Klicken Sie auf **Ausgewählte Entität bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="653f7-116">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="653f7-117">Auf der Seite **Entität bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="653f7-117">On the **Edit Entity** page:</span></span>  
  
    -   <span data-ttu-id="653f7-118">Wenn das Attribut für Blattelemente bestimmt ist, klicken Sie im Bereich **Blattelementattribute** auf **Blattattribut hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="653f7-118">If the attribute is for leaf members, in the **Leaf member attributes** pane, click **Add leaf attribute**.</span></span>  
  
    -   <span data-ttu-id="653f7-119">Wenn das Attribut für konsolidierte Elemente bestimmt ist, klicken Sie im Bereich **Konsolidierte Elementattribute** auf **Konsolidiertes Attribut hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="653f7-119">If the attribute is for consolidated members, in the **Consolidated member attributes** pane, click **Add consolidated attribute**.</span></span>  
  
    -   <span data-ttu-id="653f7-120">Wenn das Attribut für Auflistungen bestimmt ist, klicken Sie im Bereich **Auflistungsattribute** auf **Auflistungsattribut hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="653f7-120">If the attribute is for collections, in the **Collection attributes** pane, click **Add collection attribute**.</span></span>  
  
7.  <span data-ttu-id="653f7-121">Wählen Sie auf der Seite **Attribut hinzufügen** die Option **Datei** aus.</span><span class="sxs-lookup"><span data-stu-id="653f7-121">On the **Add Attribute** page, select the **File** option.</span></span>  
  
8.  <span data-ttu-id="653f7-122">Geben Sie im Feld **Name** einen Namen für das Attribut ein.</span><span class="sxs-lookup"><span data-stu-id="653f7-122">In the **Name** box, type a name for the attribute.</span></span> <span data-ttu-id="653f7-123">Eine Liste von Wörtern, die nicht als Attributnamen verwendet werden sollten, finden Sie unter [reservierte Wörter &#40;Master Data Services&#41;](../../2014/master-data-services/reserved-words-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="653f7-123">For a list of words that should not be used as attribute names, see [Reserved Words &#40;Master Data Services&#41;](../../2014/master-data-services/reserved-words-master-data-services.md).</span></span>  
  
9. <span data-ttu-id="653f7-124">Geben Sie im Feld **Pixelbreite anzeigen** die Breite der Attributspalte ein, die im **Explorerraster** angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="653f7-124">In the **Display pixel width** box, type the width of the attribute column to be displayed in the **Explorer** grid.</span></span>  
  
10. <span data-ttu-id="653f7-125">Wählen Sie in der Liste **Dateierweiterung** mindestens einen Dateityp aus, den ein Benutzer hochladen kann, oder belassen Sie den Standardwert (\*. \* ), um alle Dateitypen zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="653f7-125">From the **File extension** list, select one or more file types that a user can upload, or leave the default (\*.\*) to allow all file types.</span></span>  
  
11. <span data-ttu-id="653f7-126">Optional können Sie **Änderungsnachverfolgung aktivieren** auswählen, um Änderungen an Gruppen von Attributen nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="653f7-126">Optionally, select **Enable change tracking** to track changes to groups of attributes.</span></span> <span data-ttu-id="653f7-127">Weitere Informationen finden Sie unter [Hinzufügen von Attributen zu einer Änderungsnachverfolgungsgruppe &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="653f7-127">For more information, see [Add Attributes to a Change Tracking Group &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md).</span></span>  
  
12. <span data-ttu-id="653f7-128">Klicken Sie auf **Attribut speichern**.</span><span class="sxs-lookup"><span data-stu-id="653f7-128">Click **Save attribute**.</span></span>  
  
13. <span data-ttu-id="653f7-129">Klicken Sie auf der Seite **Entitätsverwaltung** auf **Entität speichern**.</span><span class="sxs-lookup"><span data-stu-id="653f7-129">On the **Entity Maintenance** page, click **Save entity**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="653f7-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="653f7-130">See Also</span></span>  
 <span data-ttu-id="653f7-131">[Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="653f7-131">[Attributes &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span></span>  
 <span data-ttu-id="653f7-132">[Ändern eines Attribut namens &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="653f7-132">[Change an Attribute Name &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span></span>  
 <span data-ttu-id="653f7-133">[Erstellen eines domänenbasierten Attributs &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="653f7-133">[Create a Domain-Based Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md) </span></span>  
 [<span data-ttu-id="653f7-134">Erstellen eines Textattributs &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="653f7-134">Create a Text Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-text-attribute-master-data-services.md)  
  
  
