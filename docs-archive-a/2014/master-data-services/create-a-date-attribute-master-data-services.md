---
title: Erstellen eines Datenattributs (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- creating date attributes [Master Data Services]
- attributes [Master Data Services], creating date attributes
ms.assetid: 22a8f1a3-b4f2-4cfa-8495-7daad5ce9d12
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 93797b90ff03c6a2b60ce8e015897a46a7448aad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607882"
---
# <a name="create-a-date-attribute-master-data-services"></a><span data-ttu-id="949bc-102">Erstellen eines Datenattributs (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="949bc-102">Create a Date Attribute (Master Data Services)</span></span>
  <span data-ttu-id="949bc-103">Erstellen Sie in [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]ein Datumsattribut, wenn Sie möchten, dass Benutzer ein Datum als Attributwert eingeben.</span><span class="sxs-lookup"><span data-stu-id="949bc-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a date attribute when you want users to enter a date as an attribute value.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="949bc-104">Das Attribut heißt DateTime, aber Zeitwerte werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="949bc-104">The attribute is called DateTime, but time values are not supported.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="949bc-105">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="949bc-105">Prerequisites</span></span>  
 <span data-ttu-id="949bc-106">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="949bc-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="949bc-107">Sie müssen über die Berechtigung verfügen, auf den Funktionsbereich **System Verwaltung** zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="949bc-107">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="949bc-108">Sie müssen ein Modelladministrator sein.</span><span class="sxs-lookup"><span data-stu-id="949bc-108">You must be a model administrator.</span></span> <span data-ttu-id="949bc-109">Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="949bc-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="949bc-110">Sie müssen eine Entität haben, für das Sie das Attribut erstellen.</span><span class="sxs-lookup"><span data-stu-id="949bc-110">You must have an entity to create the attribute for.</span></span> <span data-ttu-id="949bc-111">Weitere Informationen finden Sie unter [Erstellen einer Entität &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="949bc-111">For more information, see [Create an Entity &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span></span>  
  
### <a name="to-create-a-date-attribute"></a><span data-ttu-id="949bc-112">So erstellen Sie ein Datumsattribut</span><span class="sxs-lookup"><span data-stu-id="949bc-112">To create a date attribute</span></span>  
  
1.  <span data-ttu-id="949bc-113">Klicken Sie in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]auf **Systemverwaltung**.</span><span class="sxs-lookup"><span data-stu-id="949bc-113">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="949bc-114">Zeigen Sie auf der Seite **Modellansicht** auf der Menüleiste auf **Verwalten** , und klicken Sie auf **Entitäten**.</span><span class="sxs-lookup"><span data-stu-id="949bc-114">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="949bc-115">Wählen Sie auf der Seite **Entitätsverwaltung** aus der Liste **Modell** ein Modell aus.</span><span class="sxs-lookup"><span data-stu-id="949bc-115">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="949bc-116">Wählen Sie die Zeile für die Entität aus, für die Sie ein Attribut erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="949bc-116">Select the row for the entity that you want to create an attribute for.</span></span>  
  
5.  <span data-ttu-id="949bc-117">Klicken Sie auf **Ausgewählte Entität bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="949bc-117">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="949bc-118">Auf der Seite **Entität bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="949bc-118">On the **Edit Entity** page:</span></span>  
  
    -   <span data-ttu-id="949bc-119">Wenn das Attribut für Blattelemente bestimmt ist, klicken Sie im Bereich **Blattelementattribute** auf **Blattattribut hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="949bc-119">If the attribute is for leaf members, in the **Leaf member attributes** pane, click **Add leaf attribute**.</span></span>  
  
    -   <span data-ttu-id="949bc-120">Wenn das Attribut für konsolidierte Elemente bestimmt ist, klicken Sie im Bereich **Konsolidierte Elementattribute** auf **Konsolidiertes Attribut hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="949bc-120">If the attribute is for consolidated members, in the **Consolidated member attributes** pane, click **Add consolidated attribute**.</span></span>  
  
    -   <span data-ttu-id="949bc-121">Wenn das Attribut für Auflistungen bestimmt ist, klicken Sie im Bereich **Auflistungsattribute** auf **Auflistungsattribut hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="949bc-121">If the attribute is for collections, in the **Collection attributes** pane, click **Add collection attribute**.</span></span>  
  
7.  <span data-ttu-id="949bc-122">Aktivieren Sie die Option **Freiform** auf der Seite **Attribut hinzufügen** .</span><span class="sxs-lookup"><span data-stu-id="949bc-122">On the **Add Attribute** page, select the **Free-form** option.</span></span>  
  
8.  <span data-ttu-id="949bc-123">Geben Sie im Feld **Name** einen Namen für das Attribut ein.</span><span class="sxs-lookup"><span data-stu-id="949bc-123">In the **Name** box, type a name for the attribute.</span></span> <span data-ttu-id="949bc-124">Eine Liste von Wörtern, die nicht als Attributnamen verwendet werden sollten, finden Sie unter [reservierte Wörter &#40;Master Data Services&#41;](../../2014/master-data-services/reserved-words-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="949bc-124">For a list of words that should not be used as attribute names, see [Reserved Words &#40;Master Data Services&#41;](../../2014/master-data-services/reserved-words-master-data-services.md).</span></span>  
  
9. <span data-ttu-id="949bc-125">Geben Sie im Feld **Pixelbreite anzeigen** die Breite der Attributspalte ein, die im **Explorerraster** angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="949bc-125">In the **Display pixel width** box, type the width of the attribute column to be displayed in the **Explorer** grid.</span></span>  
  
10. <span data-ttu-id="949bc-126">Wählen Sie aus der Liste **Datentyp** die Option **DateTime**aus.</span><span class="sxs-lookup"><span data-stu-id="949bc-126">From the **Data type** list, select **DateTime**.</span></span>  
  
11. <span data-ttu-id="949bc-127">Wählen Sie aus der Liste **Eingabeformat** ein Format für Datumsangaben aus.</span><span class="sxs-lookup"><span data-stu-id="949bc-127">From the **Input mask** list, select a format for dates.</span></span>  
  
12. <span data-ttu-id="949bc-128">Optional können Sie **Änderungsnachverfolgung aktivieren** auswählen, um Änderungen an Gruppen von Attributen nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="949bc-128">Optionally, select **Enable change tracking** to track changes to groups of attributes.</span></span> <span data-ttu-id="949bc-129">Weitere Informationen finden Sie unter [Hinzufügen von Attributen zu einer Änderungsnachverfolgungsgruppe &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="949bc-129">For more information, see [Add Attributes to a Change Tracking Group &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md).</span></span>  
  
13. <span data-ttu-id="949bc-130">Klicken Sie auf **Attribut speichern**.</span><span class="sxs-lookup"><span data-stu-id="949bc-130">Click **Save attribute**.</span></span>  
  
14. <span data-ttu-id="949bc-131">Klicken Sie auf der Seite **Entitätsverwaltung** auf **Entität speichern**.</span><span class="sxs-lookup"><span data-stu-id="949bc-131">On the **Entity Maintenance** page, click **Save entity**.</span></span>  
  
## <a name="to-display-the-time-portion-of-a-datetime-value"></a><span data-ttu-id="949bc-132">So zeigen Sie den Zeitbereich eines datetime-Werts an</span><span class="sxs-lookup"><span data-stu-id="949bc-132">To display the time portion of a datetime value</span></span>  
 <span data-ttu-id="949bc-133">Damit der Zeitbereich eines datetime-Werts in der Benutzeroberfläche angezeigt wird, müssen Sie ein geeignetes Eingabeformat für das Attribut auswählen.</span><span class="sxs-lookup"><span data-stu-id="949bc-133">To have the user interface display the time portion of a datetime value, you must select an appropriate input mask for the attribute.</span></span> <span data-ttu-id="949bc-134">Da keine der integrierten Masken für Datetime-Attribute hierzu geeignet ist, können Sie eine neue Maske hinzufügen, die die Anzeige der Uhrzeit ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="949bc-134">None of the built-in masks for Datetime attributes do this, but you can add a new mask that will allow you to display time.</span></span> <span data-ttu-id="949bc-135">Fügen Sie dazu der Tabelle mdm.tblList der MDS-Datenbank, in der integrierte Masken gespeichert werden, eine Zeile hinzu.</span><span class="sxs-lookup"><span data-stu-id="949bc-135">To do so, add a row in the mdm.tblList table of the MDS database, where the built-in masks are stored.</span></span> <span data-ttu-id="949bc-136">Die Zeile sollte über die folgenden Werte verfügen:</span><span class="sxs-lookup"><span data-stu-id="949bc-136">The row should have the following values:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="949bc-137">ListCode</span><span class="sxs-lookup"><span data-stu-id="949bc-137">ListCode</span></span>|<span data-ttu-id="949bc-138">lstInputMask</span><span class="sxs-lookup"><span data-stu-id="949bc-138">lstInputMask</span></span>|  
|<span data-ttu-id="949bc-139">ListName</span><span class="sxs-lookup"><span data-stu-id="949bc-139">ListName</span></span>|<span data-ttu-id="949bc-140">Eingabeformat</span><span class="sxs-lookup"><span data-stu-id="949bc-140">Input Mask</span></span>|  
|<span data-ttu-id="949bc-141">Seq</span><span class="sxs-lookup"><span data-stu-id="949bc-141">Seq</span></span>|<span data-ttu-id="949bc-142">19</span><span class="sxs-lookup"><span data-stu-id="949bc-142">19</span></span>|  
|<span data-ttu-id="949bc-143">List Option</span><span class="sxs-lookup"><span data-stu-id="949bc-143">List Option</span></span>|<span data-ttu-id="949bc-144">dd/MM/yyyy hh:mm:ss tt</span><span class="sxs-lookup"><span data-stu-id="949bc-144">dd/MM/yyyy hh:mm:ss tt</span></span>|  
|<span data-ttu-id="949bc-145">Option ID</span><span class="sxs-lookup"><span data-stu-id="949bc-145">Option ID</span></span>|<span data-ttu-id="949bc-146">19</span><span class="sxs-lookup"><span data-stu-id="949bc-146">19</span></span>|  
|<span data-ttu-id="949bc-147">Sichtbar</span><span class="sxs-lookup"><span data-stu-id="949bc-147">IsVisible</span></span>|<span data-ttu-id="949bc-148">1</span><span class="sxs-lookup"><span data-stu-id="949bc-148">1</span></span>|  
|<span data-ttu-id="949bc-149">Group_ID</span><span class="sxs-lookup"><span data-stu-id="949bc-149">Group_ID</span></span>|<span data-ttu-id="949bc-150">3</span><span class="sxs-lookup"><span data-stu-id="949bc-150">3</span></span>|  
  
 <span data-ttu-id="949bc-151">Nachdem Sie in die Tabelle „mdm.tblList“ eine Zeile mit den oben angegebenen Werten eingegeben haben, steht im Eingabeformat-Listenfeld die Maske „dd/MM/yyyy hh:mm:ss tt“ zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="949bc-151">After you enter a row with the above values in the mdm.tblList table, the "dd/MM/yyyy hh:mm:ss tt" mask will be available in the Input mask list box.</span></span> <span data-ttu-id="949bc-152">Anschließend können Sie diese Maske auswählen, um das Datum und die Uhrzeit in einer datetime-Attributspalte einer Entität im MDS-Explorer anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="949bc-152">You can then select that mask to display the date and time in a datetime attribute column of an entity in the MDS Explorer.</span></span>  
  
 <span data-ttu-id="949bc-153">Die Input Mask ist eine benutzerdefinierte .NET DateTime-Formatzeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="949bc-153">The Input Mask is a custom .NET DateTime format string.</span></span> <span data-ttu-id="949bc-154">Weitere Informationen finden Sie unter [Benutzerdefinierte Datums- und Uhrzeit-Formatzeichenfolgen](https://msdn.microsoft.com/library/8kb3ddd4\(v=vs.110\).aspx)</span><span class="sxs-lookup"><span data-stu-id="949bc-154">For more information, see [Custom Date and Time Format Strings](https://msdn.microsoft.com/library/8kb3ddd4\(v=vs.110\).aspx)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="949bc-155">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="949bc-155">See Also</span></span>  
 <span data-ttu-id="949bc-156">[Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="949bc-156">[Attributes &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span></span>  
 <span data-ttu-id="949bc-157">[Ändern eines Attribut namens &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="949bc-157">[Change an Attribute Name &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span></span>  
 <span data-ttu-id="949bc-158">[Erstellen eines domänenbasierten Attributs &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="949bc-158">[Create a Domain-Based Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md) </span></span>  
 [<span data-ttu-id="949bc-159">Erstellen eines Dateiattributs &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="949bc-159">Create a File Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-file-attribute-master-data-services.md)  
  
  
