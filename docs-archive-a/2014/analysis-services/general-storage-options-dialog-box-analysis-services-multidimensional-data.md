---
title: Allgemein (Dialog Feld "Speicheroptionen") (Analysis Services-Mehrdimensionale Daten) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.partitiondesigner.partitionstoragesettings.setstorageoptions.storage.f1
ms.assetid: ee1fac79-ae15-4c3c-9a98-33db04388817
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0963b3536dc5156d3a89fc27d3fa6221a4df18e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616265"
---
# <a name="general-storage-options-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="bbc0e-102">Allgemein (Dialogfeld „Speicheroptionen“) (Analysis Services – Mehrdimensionale Daten)</span><span class="sxs-lookup"><span data-stu-id="bbc0e-102">General (Storage Options Dialog Box) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="bbc0e-103">Mithilfe der Registerkarte **Allgemein** im Dialogfeld **Speicheroptionen** in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] können Sie die Einstellungen für den Speichermodus und das proaktive Zwischenspeichern für eine Dimension, einen Cube, eine Measuregruppe oder eine Partition festlegen.</span><span class="sxs-lookup"><span data-stu-id="bbc0e-103">Use the **General** tab of the **Storage Options** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to set the storage mode and proactive caching settings for a dimension, cube, measure group, or partition.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bbc0e-104">Sie sollten mit den Funktionen für den Speichermodus und das proaktive Zwischenspeichern vertraut sein, bevor Sie Änderungen an diesen Einstellungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="bbc0e-104">You should be familiar with storage mode and proactive caching functionality before modifying these settings.</span></span> <span data-ttu-id="bbc0e-105">Weitere Informationen finden Sie unter [Proaktives Zwischenspeichern &#40;Partitionen&#41;](multidimensional-models-olap-logical-cube-objects/partitions-proactive-caching.md).</span><span class="sxs-lookup"><span data-stu-id="bbc0e-105">For more information, see [Proactive Caching &#40;Partitions&#41;](multidimensional-models-olap-logical-cube-objects/partitions-proactive-caching.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="bbc0e-106">Tastatur</span><span class="sxs-lookup"><span data-stu-id="bbc0e-106">Options</span></span>  
  
|<span data-ttu-id="bbc0e-107">Begriff</span><span class="sxs-lookup"><span data-stu-id="bbc0e-107">Term</span></span>|<span data-ttu-id="bbc0e-108">Definition</span><span class="sxs-lookup"><span data-stu-id="bbc0e-108">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="bbc0e-109">**Speichermodus**</span><span class="sxs-lookup"><span data-stu-id="bbc0e-109">**Storage mode**</span></span>|<span data-ttu-id="bbc0e-110">Wählt den für das Objekt zu verwendenden Speichermodus aus.</span><span class="sxs-lookup"><span data-stu-id="bbc0e-110">Selects the storage mode to use for the object.</span></span><br /><br /> <span data-ttu-id="bbc0e-111">**MOLAP**</span><span class="sxs-lookup"><span data-stu-id="bbc0e-111">**MOLAP**</span></span><br /> <span data-ttu-id="bbc0e-112">Für das Objekt wird die mehrdimensionale OLAP (MOLAP)-Speicherung verwendet.</span><span class="sxs-lookup"><span data-stu-id="bbc0e-112">The object uses multidimensional OLAP (MOLAP) storage.</span></span><br /><br /> <span data-ttu-id="bbc0e-113">**HOLAP**</span><span class="sxs-lookup"><span data-stu-id="bbc0e-113">**HOLAP**</span></span><br /> <span data-ttu-id="bbc0e-114">Für das Objekt wird die hybride OLAP (HOLAP)-Speicherung verwendet.</span><span class="sxs-lookup"><span data-stu-id="bbc0e-114">The object uses hybrid OLAP (HOLAP) storage.</span></span><br /><br /> <span data-ttu-id="bbc0e-115">**ROLAP**</span><span class="sxs-lookup"><span data-stu-id="bbc0e-115">**ROLAP**</span></span><br /> <span data-ttu-id="bbc0e-116">Für das Objekt wird die relationale OLAP (ROLAP)-Speicherung verwendet.</span><span class="sxs-lookup"><span data-stu-id="bbc0e-116">The object uses relational OLAP (ROLAP) storage.</span></span>|  
|<span data-ttu-id="bbc0e-117">**Aktiviert die proaktive Zwischenspeicherung.**</span><span class="sxs-lookup"><span data-stu-id="bbc0e-117">**Enable proactive caching**</span></span>|<span data-ttu-id="bbc0e-118">Aktiviert die proaktive Zwischenspeicherung.</span><span class="sxs-lookup"><span data-stu-id="bbc0e-118">Enables proactive caching.</span></span><br /><br /> <span data-ttu-id="bbc0e-119">Hinweis: Wenn diese Option nicht ausgewählt ist, sind alle Optionen mit Ausnahme von **Speichermodus** deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="bbc0e-119">Note: If this option is not selected, all options except **Storage mode** are disabled.</span></span>|  
|<span data-ttu-id="bbc0e-120">**Cache bei Datenänderungen aktualisieren**</span><span class="sxs-lookup"><span data-stu-id="bbc0e-120">**Update the cache when data changes**</span></span>|<span data-ttu-id="bbc0e-121">Aktualisieren Sie mithilfe der auf der Registerkarte **Benachrichtigungen** ausgewählten Benachrichtigungsmethode bei jeder empfangenen Benachrichtigung das MOLAP-Image für das Objekt.</span><span class="sxs-lookup"><span data-stu-id="bbc0e-121">Uses the notification method selected in the **Notifications** tab to update the MOLAP image for the object whenever a notification is received.</span></span> <span data-ttu-id="bbc0e-122">Weitere Informationen zur Registerkarte **Benachrichtigungen** finden Sie unter [Benachrichtigungen &#40;Dialogfeld „Speicheroptionen“&#41; &#40;Analysis Services – Mehrdimensionale Daten&#41;](notifications-storage-options-dialog-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="bbc0e-122">For more information about the **Notifications** tab, see [Notifications &#40;Storage Options Dialog Box&#41; &#40;Analysis Services - Multidimensional Data&#41;](notifications-storage-options-dialog-analysis-services-multidimensional-data.md).</span></span><br /><br /> <span data-ttu-id="bbc0e-123">Hinweis: Diese Option ist nur aktiviert, wenn die Option **Proaktives Zwischenspeichern** aktivieren ausgewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="bbc0e-123">Note: This option is disabled unless **Enable proactive caching** is selected.</span></span>|  
|<span data-ttu-id="bbc0e-124">**Ruheintervall**</span><span class="sxs-lookup"><span data-stu-id="bbc0e-124">**Silence interval**</span></span>|<span data-ttu-id="bbc0e-125">Legt das Mindestintervall und die Zeiteinheit für die Inaktivität des Objekts fest, bevor das proaktive Zwischenspeichern mit dem Erstellen eines neuen MOLAP-Images für das Objekt beginnt.</span><span class="sxs-lookup"><span data-stu-id="bbc0e-125">Sets the minimum interval and units of time in which the object has no activity before proactive caching starts to create the new MOLAP image for the object.</span></span><br /><br /> <span data-ttu-id="bbc0e-126">Hinweis: Diese Option ist nur aktiviert, wenn die Option **Cache bei Datenänderungen aktualisieren** ausgewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="bbc0e-126">Note: This option is disabled unless **Update the cache when data changes** is selected.</span></span>|  
|<span data-ttu-id="bbc0e-127">**Ruhe-Überschreibungsintervall**</span><span class="sxs-lookup"><span data-stu-id="bbc0e-127">**Silence override interval**</span></span>|<span data-ttu-id="bbc0e-128">Legt das Maximumintervall und die Zeiteinheit nach dem Empfangen einer Benachrichtigung für das Objekt fest, nach der das proaktive Zwischenspeichern unabhängig von der aktuellen Aktivität des Objekts mit dem Erstellen eines neuen MOLAP-Images für das Objekt beginnt.</span><span class="sxs-lookup"><span data-stu-id="bbc0e-128">Sets the maximum interval and units of time in which, after a notification is received for the object, proactive caching starts to create a new MOLAP image for the object, regardless of the current activity of the object.</span></span> <span data-ttu-id="bbc0e-129">Benachrichtigungen, die nach Ende des Intervalls empfangen werden, brechen den durch dieses Intervall ausgelösten MOLAP-Imageprozess nicht ab.</span><span class="sxs-lookup"><span data-stu-id="bbc0e-129">Notifications received after this interval has been reached do not cancel the MOLAP image process triggered by this interval.</span></span><br /><br /> <span data-ttu-id="bbc0e-130">Hinweis: Diese Option ist nur aktiviert, wenn die Option **Cache bei Datenänderungen aktualisieren** ausgewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="bbc0e-130">Note: This option is disabled unless **Update the cache when data changes** is selected.</span></span> <span data-ttu-id="bbc0e-131">Beachten Sie auch, dass diese Option nicht festgelegt werden sollte, wenn der **Speicher Modus** auf **HOLAP**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="bbc0e-131">Also note that this option should not be set if **Storage mode** is set to **HOLAP**.</span></span>|  
|<span data-ttu-id="bbc0e-132">**Veralteten Cache löschen**</span><span class="sxs-lookup"><span data-stu-id="bbc0e-132">**Drop outdated cache**</span></span>|<span data-ttu-id="bbc0e-133">Gibt den Zeitraum zwischen dem Start des Erstellens eines neuen MOLAP-Caches und dem Entfernen des vorhandenen MOLAP-Caches an.</span><span class="sxs-lookup"><span data-stu-id="bbc0e-133">Specifies the period between the start of creating a new MOLAP cache and the removal of the existing MOLAP cache.</span></span><br /><br /> <span data-ttu-id="bbc0e-134">Hinweis: Diese Option ist nur aktiviert, wenn die Option **Proaktives Zwischenspeichern** aktivieren ausgewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="bbc0e-134">Note: This option is disabled unless **Enable proactive caching** is selected.</span></span> <span data-ttu-id="bbc0e-135">Beachten Sie auch, dass diese Option nicht festgelegt werden sollte, wenn der **Speicher Modus** auf HOLAP festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="bbc0e-135">Also note that this option should not be set if **Storage mode** is set to HOLAP.</span></span>|  
|<span data-ttu-id="bbc0e-136">**Latenz**</span><span class="sxs-lookup"><span data-stu-id="bbc0e-136">**Latency**</span></span>|<span data-ttu-id="bbc0e-137">Wählt das Intervall und die Zeiteinheiten für den Zeitraum zwischen dem Start des Erstellens eines neuen MOLAP-Caches und dem Entfernen des vorhandenen MOLAP-Caches aus.</span><span class="sxs-lookup"><span data-stu-id="bbc0e-137">Selects the interval and units of time for the period between the start of creating a new MOLAP cache and the removal of the existing MOLAP cache.</span></span><br /><br /> <span data-ttu-id="bbc0e-138">Hinweis: Diese Option ist nur aktiviert, wenn die Option **Veralteten Cache löschen** ausgewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="bbc0e-138">Note: This option is disabled unless **Drop outdated cache** is selected.</span></span> <span data-ttu-id="bbc0e-139">Beachten Sie auch, dass diese Option nicht festgelegt werden sollte, wenn der **Speicher Modus** auf **HOLAP**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="bbc0e-139">Also note that this option should not be set if **Storage mode** is set to **HOLAP**.</span></span>|  
|<span data-ttu-id="bbc0e-140">**Cache regelmäßig aktualisieren**</span><span class="sxs-lookup"><span data-stu-id="bbc0e-140">**Update the cache periodically**</span></span>|<span data-ttu-id="bbc0e-141">Aktualisiert das MOLAP-Image in regelmäßigen Abständen, unabhängig von einer Benachrichtigung.</span><span class="sxs-lookup"><span data-stu-id="bbc0e-141">Updates the MOLAP image on a regular basis, regardless of notification.</span></span><br /><br /> <span data-ttu-id="bbc0e-142">Hinweis: Diese Option ist nur aktiviert, wenn die Option **Proaktives Zwischenspeichern** aktivieren ausgewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="bbc0e-142">Note: This option is disabled unless **Enable proactive caching** is selected.</span></span> <span data-ttu-id="bbc0e-143">Beachten Sie auch, dass diese Option nicht festgelegt werden sollte, wenn der **Speicher Modus** auf **HOLAP**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="bbc0e-143">Also note that this option should not be set if **Storage mode** is set to **HOLAP**.</span></span>|  
|<span data-ttu-id="bbc0e-144">**Neuerstellungsintervall**</span><span class="sxs-lookup"><span data-stu-id="bbc0e-144">**Rebuild interval**</span></span>|<span data-ttu-id="bbc0e-145">Wählt das Intervall und die Zeiteinheiten für den Zeitraum aus, der nach dem Erstellen eines neuen MOLAP-Images [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] den MOLAP-Image Prozess für das Objekt erneut startet, unabhängig von der Benachrichtigung.</span><span class="sxs-lookup"><span data-stu-id="bbc0e-145">Selects the interval and units of time for the period that, after a new MOLAP image is created, [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] starts the MOLAP image process again for the object, regardless of notification.</span></span> <span data-ttu-id="bbc0e-146">Benachrichtigungen, die nach Ende des Intervalls empfangen werden, brechen den durch dieses Intervall ausgelösten MOLAP-Imageprozess nicht ab.</span><span class="sxs-lookup"><span data-stu-id="bbc0e-146">Notifications received after this interval has been reached do not cancel the MOLAP image process triggered by this interval.</span></span><br /><br /> <span data-ttu-id="bbc0e-147">Hinweis: Diese Option ist nur aktiviert, wenn die Option **Cache regelmäßig aktualisieren** ausgewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="bbc0e-147">Note: This option is disabled unless **Update the cache periodically** is selected.</span></span> <span data-ttu-id="bbc0e-148">Beachten Sie auch, dass diese Option nicht festgelegt werden sollte, wenn der **Speicher Modus** auf **HOLAP**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="bbc0e-148">Also note that this option should not be set if **Storage mode** is set to **HOLAP**.</span></span>|  
|<span data-ttu-id="bbc0e-149">**Sofort online schalten**</span><span class="sxs-lookup"><span data-stu-id="bbc0e-149">**Bring online immediately**</span></span>|<span data-ttu-id="bbc0e-150">Schaltet Objekte sofort online.</span><span class="sxs-lookup"><span data-stu-id="bbc0e-150">Brings objects online immediately.</span></span> <span data-ttu-id="bbc0e-151">Wenn diese Option festgelegt ist, verwenden Objekte die zugrunde liegende ROLAP-Speicherung zum Auflösen von Abfragen, während der MOLAP-Cache erneut erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="bbc0e-151">If this option is set, objects use the underlying ROLAP storage for resolving queries while the MOLAP cache is being rebuilt.</span></span> <span data-ttu-id="bbc0e-152">Wenn diese Option nicht festgelegt ist, werden Objekte erst online geschaltet, nachdem der MOLAP-Cache für das Objekt vollständig ist.</span><span class="sxs-lookup"><span data-stu-id="bbc0e-152">If this option is not set, objects are brought online only after the MOLAP cache for the object is complete.</span></span>|  
|<span data-ttu-id="bbc0e-153">**ROLAP-Aggregationen aktivieren**</span><span class="sxs-lookup"><span data-stu-id="bbc0e-153">**Enable ROLAP aggregations**</span></span>|<span data-ttu-id="bbc0e-154">Verwendet für die zugrunde liegende Datenquelle materialisierte Sichten zum Speichern von Aggregationen.</span><span class="sxs-lookup"><span data-stu-id="bbc0e-154">Uses materialized views on the underlying data source to store aggregations.</span></span><br /><br /> <span data-ttu-id="bbc0e-155">Hinweis: Wenn die zugrunde liegende Datenquelle keine materialisierten Sichten unterstützt, tritt bei der Verarbeitung des Objekts ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="bbc0e-155">Note: If the underlying data source does not support materialized views, an error will occur when the object is processed.</span></span>|  
|<span data-ttu-id="bbc0e-156">**Einstellungen auf Dimensionen anwenden**</span><span class="sxs-lookup"><span data-stu-id="bbc0e-156">**Apply settings to dimensions**</span></span>|<span data-ttu-id="bbc0e-157">Wendet die Einstellungen für den Speichermodus und das proaktive Zwischenspeichern auf verknüpfte Dimensionen an.</span><span class="sxs-lookup"><span data-stu-id="bbc0e-157">Applies storage mode and proactive caching settings to associated dimensions.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bbc0e-158">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bbc0e-158">See Also</span></span>  
 <span data-ttu-id="bbc0e-159">[Dialog Feld "Speicheroptionen" &#40;Analysis Services Mehrdimensionale Daten&#41;](storage-options-dialog-box-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="bbc0e-159">[Storage Options Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](storage-options-dialog-box-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="bbc0e-160">Das Dialog Feld Benachrichtigungen &#40;Speicheroptionen&#41; &#40;Analysis Services Mehrdimensionale Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="bbc0e-160">Notifications &#40;Storage Options Dialog Box&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](notifications-storage-options-dialog-analysis-services-multidimensional-data.md)  
  
  