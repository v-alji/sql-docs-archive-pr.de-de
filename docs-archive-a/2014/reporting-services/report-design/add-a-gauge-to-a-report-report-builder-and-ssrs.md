---
title: Hinzufügen eines Messgeräts zu einem Bericht (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 45da4fef-2b02-40e1-977c-f8f80d87155e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7125080d95e9c7b882df8d715cce5c6cf8aa6344
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722566"
---
# <a name="add-a-gauge-to-a-report-report-builder-and-ssrs"></a><span data-ttu-id="122dc-102">Hinzufügen eines Messgeräts zu einem Bericht (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="122dc-102">Add a Gauge to a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="122dc-103">Wenn Sie Daten in einem visuellen Format zusammenfassen möchten, verwenden Sie einen Messgerätdatenbereich.</span><span class="sxs-lookup"><span data-stu-id="122dc-103">When you want to summarize data in a visual format, you can use a Gauge data region.</span></span> <span data-ttu-id="122dc-104">Nachdem Sie einen Messgerätdatenbereich zur Entwurfsoberfläche hinzugefügt haben, können Sie Berichtsdatasetfelder in einen Datenbereich auf dem Messgerät ziehen.</span><span class="sxs-lookup"><span data-stu-id="122dc-104">After you add a Gauge data region to the design surface, you can drag report dataset fields to a data pane on the gauge.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-gauge-to-your-report"></a><span data-ttu-id="122dc-105">So fügen Sie ein Messgerät zu einem Bericht hinzu</span><span class="sxs-lookup"><span data-stu-id="122dc-105">To add a gauge to your report</span></span>  
  
1.  <span data-ttu-id="122dc-106">Erstellen Sie einen Bericht, oder öffnen Sie einen vorhandenen Bericht.</span><span class="sxs-lookup"><span data-stu-id="122dc-106">Create a report or open an existing report.</span></span>  
  
2.  <span data-ttu-id="122dc-107">Doppelklicken Sie auf der Registerkarte Einfügen auf Messgerät.</span><span class="sxs-lookup"><span data-stu-id="122dc-107">On the Insert tab, double-click Gauge.</span></span> <span data-ttu-id="122dc-108">Das Dialogfeld **Messgerättyp auswählen** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="122dc-108">The **Select Gauge Type** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="122dc-109">Wählen Sie den gewünschten Messgerättyp aus.</span><span class="sxs-lookup"><span data-stu-id="122dc-109">Select the type of gauge you want to add.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
    > [!NOTE]  
    >  <span data-ttu-id="122dc-110">Im Gegensatz zu Diagrammen gibt es nur zwei Messgerättypen, nämlich linear und radial.</span><span class="sxs-lookup"><span data-stu-id="122dc-110">Unlike Chart, Gauge has only two types: linear and radial.</span></span> <span data-ttu-id="122dc-111">Die im Dialogfeld **Messgerättyp auswählen** verfügbaren Messgeräte sind Vorlagen für diese beiden Arten von Messgeräten.</span><span class="sxs-lookup"><span data-stu-id="122dc-111">The available gauges in the **Select a Gauge Type** dialog box are templates for these two types of gauges.</span></span> <span data-ttu-id="122dc-112">Deshalb können Sie den Messgerättyp nicht ändern, nachdem Sie das Messgerät dem Bericht hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="122dc-112">For this reason, you cannot change the gauge type after you add the gauge to your report.</span></span> <span data-ttu-id="122dc-113">Wenn Sie den Typ ändern möchten, müssen Sie das Messgerät löschen und erneut hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="122dc-113">You must delete and re-add a gauge to change its type.</span></span>  
  
     <span data-ttu-id="122dc-114">Wenn der Bericht keine Datenquelle und kein Dataset enthält, wird das Dialogfeld **Datenquelleneigenschaften** geöffnet. Es führt Sie durch die einzelnen Schritte beim Erstellen von Datenquelle und Dataset.</span><span class="sxs-lookup"><span data-stu-id="122dc-114">If the report has no data source and dataset the **Data Source Properties** dialog box opens and takes you through the steps to create both.</span></span> <span data-ttu-id="122dc-115">Weitere Informationen finden Sie unter [Hinzufügen und Überprüfen einer Datenverbindung oder Datenquelle &#40;Berichts-Generator und SSRS&#41;](../report-data/add-and-verify-a-data-connection-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="122dc-115">For more information see, [Add and Verify a Data Connection or Data Source &#40;Report Builder and SSRS&#41;](../report-data/add-and-verify-a-data-connection-report-builder-and-ssrs.md).</span></span>  
  
     <span data-ttu-id="122dc-116">Wenn der Bericht eine Datenquelle, jedoch kein Dataset enthält, wird das Dialogfeld **Dataseteigenschaften** geöffnet. Es führt Sie durch die einzelnen Schritte beim Erstellen des Datasets.</span><span class="sxs-lookup"><span data-stu-id="122dc-116">If the report has a data source, but no dataset the **Dataset Properties** dialog box opens and takes you through the steps to create one.</span></span> <span data-ttu-id="122dc-117">Weitere Informationen finden Sie unter [Erstellen eines freigegebenen Datasets oder eingebetteten Datasets &#40;Berichts-Generator und SSRS&#41;](../report-data/create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="122dc-117">For more information, see [Create a Shared Dataset or Embedded Dataset &#40;Report Builder and SSRS&#41;](../report-data/create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs.md).</span></span>  
  
4.  <span data-ttu-id="122dc-118">Klicken Sie zum Anzeigen des Datenbereichs auf das Messgerät.</span><span class="sxs-lookup"><span data-stu-id="122dc-118">Click the gauge to display the data pane.</span></span> <span data-ttu-id="122dc-119">Standardmäßig verfügt ein Messgerät über einen Zeiger, der einem Wert entspricht.</span><span class="sxs-lookup"><span data-stu-id="122dc-119">By default, a gauge has one pointer corresponding to one value.</span></span> <span data-ttu-id="122dc-120">Sie können weitere Zeiger hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="122dc-120">You can add additional pointers.</span></span>  
  
5.  <span data-ttu-id="122dc-121">Fügen Sie der Datenfeldablagezone ein Feld aus dem Dataset hinzu.</span><span class="sxs-lookup"><span data-stu-id="122dc-121">Add one field from the dataset to the data field drop-zone.</span></span> <span data-ttu-id="122dc-122">Sie können nur ein Feld hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="122dc-122">You can add only one field.</span></span> <span data-ttu-id="122dc-123">Wenn Sie mehrere Felder anzeigen möchten, müssen Sie zusätzliche Zeiger hinzufügen, einen für jedes Feld.</span><span class="sxs-lookup"><span data-stu-id="122dc-123">If you want to display multiple fields, you must add additional pointers, one for each field.</span></span>  
  
     <span data-ttu-id="122dc-124">Klicken Sie mit der rechten Maustaste auf die Skalierung des Messgeräts, und wählen Sie **Skalierungseigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="122dc-124">Right-click the gauge scale, and select **Scale Properties**.</span></span> <span data-ttu-id="122dc-125">Geben Sie einen Wert für das **Minimum** und das **Maximum** der Skala ein.</span><span class="sxs-lookup"><span data-stu-id="122dc-125">Type a value for the **Minimum** and **Maximum** of the scale.</span></span> <span data-ttu-id="122dc-126">Weitere Informationen finden Sie unter [Festlegen eines Mindestwerts oder eines Höchstwerts auf einem Messgerät (Berichts-Generator und SSRS)](set-a-minimum-or-maximum-on-a-gauge-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="122dc-126">For more information, see [Set a Minimum or Maximum on a Gauge &#40;Report Builder and SSRS&#41;](set-a-minimum-or-maximum-on-a-gauge-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="122dc-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="122dc-127">See Also</span></span>  
 <span data-ttu-id="122dc-128">[Geschachtelte Datenbereiche &#40;Berichts-Generator und SSRS&#41;](nested-data-regions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="122dc-128">[Nested Data Regions &#40;Report Builder and SSRS&#41;](nested-data-regions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="122dc-129">Messgeräte &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="122dc-129">Gauges &#40;Report Builder and SSRS&#41;</span></span>](gauges-report-builder-and-ssrs.md)  
  
  
