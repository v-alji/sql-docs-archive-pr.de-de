---
title: Ändern von Measures | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 7bd48810-15ce-45ff-862b-372d08606995
author: minewiskan
ms.author: owend
ms.openlocfilehash: fd352cbca1d21f5842e075d9cb8e5e766aa369b0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620635"
---
# <a name="modifying-measures"></a><span data-ttu-id="ef9b0-102">Ändern von Measures</span><span class="sxs-lookup"><span data-stu-id="ef9b0-102">Modifying Measures</span></span>
  <span data-ttu-id="ef9b0-103">Sie können die **FormatString** -Eigenschaft verwenden, um Formatierungseinstellungen zu definieren, die die Darstellung von Measures steuern.</span><span class="sxs-lookup"><span data-stu-id="ef9b0-103">You can use the **FormatString** property to define formatting settings that control how measures are displayed to users.</span></span> <span data-ttu-id="ef9b0-104">In dieser Aufgabe geben Sie Formatierungseigenschaften für die Währungs- und Prozentsatzmeasures im [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial-Cube an.</span><span class="sxs-lookup"><span data-stu-id="ef9b0-104">In this task, you specify formatting properties for the currency and percentage measures in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube.</span></span>  
  
### <a name="to-modify-the-measures-of-the-cube"></a><span data-ttu-id="ef9b0-105">So ändern Sie die Measures des Cubes</span><span class="sxs-lookup"><span data-stu-id="ef9b0-105">To modify the measures of the cube</span></span>  
  
1.  <span data-ttu-id="ef9b0-106">Wechseln Sie zur Registerkarte **Cubestruktur** des Cube-Designers für den [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial-Cube, erweitern Sie die **Internet Sales** -Measuregruppe im Bereich **Measures** , klicken Sie mit der rechten Maustaste auf **Order Quantity**, und klicken Sie anschließend auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="ef9b0-106">Switch to the **Cube Structure** tab of Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube, expand the **Internet Sales** measure group in the **Measures** pane, right-click **Order Quantity**, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="ef9b0-107">Klicken Sie im Eigenschaftenfenster auf das Pushpin-Symbol **Automatisch im Hintergrund** , um das Eigenschaftenfenster offen zu halten.</span><span class="sxs-lookup"><span data-stu-id="ef9b0-107">In the Properties window, click the **Auto Hide** pushpin icon to pin the Properties window open.</span></span>  
  
     <span data-ttu-id="ef9b0-108">Das Ändern von Eigenschaften für eine Reihe von Elementen ist einfacher, wenn das Eigenschaftenfenster geöffnet bleibt.</span><span class="sxs-lookup"><span data-stu-id="ef9b0-108">It is easier to change properties for several items in the cube when the Properties window remains open.</span></span>  
  
3.  <span data-ttu-id="ef9b0-109">Klicken Sie im Eigenschaftenfenster auf die Liste **FormatString** , und geben Sie anschließend **#,#** ein.</span><span class="sxs-lookup"><span data-stu-id="ef9b0-109">In the Properties window, click the **FormatString** list, and then type **#,#**.</span></span>  
  
4.  <span data-ttu-id="ef9b0-110">Klicken Sie auf der Symbolleiste der Registerkarte **Cubestruktur** auf der linken Seite auf das Symbol **Measuresraster anzeigen** .</span><span class="sxs-lookup"><span data-stu-id="ef9b0-110">On the toolbar of the **Cube Structure** tab, click the **Show Measures Grid** icon on the left.</span></span>  
  
     <span data-ttu-id="ef9b0-111">In der Rasteransicht können Sie mehrere Measures gleichzeitig auswählen.</span><span class="sxs-lookup"><span data-stu-id="ef9b0-111">The grid view lets you select multiple measures at the same time.</span></span>  
  
5.  <span data-ttu-id="ef9b0-112">Wählen Sie eine der folgenden Measures aus.</span><span class="sxs-lookup"><span data-stu-id="ef9b0-112">Select the following measures.</span></span> <span data-ttu-id="ef9b0-113">Um mehrere Measures auszuwählen, halten Sie beim Klicken die STRG-TASTE gedrückt:</span><span class="sxs-lookup"><span data-stu-id="ef9b0-113">You can select multiple measures by clicking each while holding down the CTRL key:</span></span>  
  
    -   <span data-ttu-id="ef9b0-114">**Unit Price**</span><span class="sxs-lookup"><span data-stu-id="ef9b0-114">**Unit Price**</span></span>  
  
    -   <span data-ttu-id="ef9b0-115">**Extended Amount**</span><span class="sxs-lookup"><span data-stu-id="ef9b0-115">**Extended Amount**</span></span>  
  
    -   <span data-ttu-id="ef9b0-116">**Discount Amount**</span><span class="sxs-lookup"><span data-stu-id="ef9b0-116">**Discount Amount**</span></span>  
  
    -   <span data-ttu-id="ef9b0-117">**Product Standard Cost**</span><span class="sxs-lookup"><span data-stu-id="ef9b0-117">**Product Standard Cost**</span></span>  
  
    -   <span data-ttu-id="ef9b0-118">**Total Product Cost**</span><span class="sxs-lookup"><span data-stu-id="ef9b0-118">**Total Product Cost**</span></span>  
  
    -   <span data-ttu-id="ef9b0-119">**Sales Amount**</span><span class="sxs-lookup"><span data-stu-id="ef9b0-119">**Sales Amount**</span></span>  
  
    -   <span data-ttu-id="ef9b0-120">**Tax Amt**</span><span class="sxs-lookup"><span data-stu-id="ef9b0-120">**Tax Amt**</span></span>  
  
    -   <span data-ttu-id="ef9b0-121">**Freight (Fracht)**</span><span class="sxs-lookup"><span data-stu-id="ef9b0-121">**Freight**</span></span>  
  
6.  <span data-ttu-id="ef9b0-122">Wählen Sie im Eigenschaftenfenster in der **FormatString** -Liste **Currency**aus.</span><span class="sxs-lookup"><span data-stu-id="ef9b0-122">In the Properties window, in the **FormatString** list, select **Currency**.</span></span>  
  
7.  <span data-ttu-id="ef9b0-123">Wählen Sie im Dropdown-Listenfeld oben im Eigenschaftenfenster (rechts unterhalb der Titelleiste) das Measure **Unit Price Discount Pct**und anschließend in der Liste **FormatString** die Option **Percent** aus.</span><span class="sxs-lookup"><span data-stu-id="ef9b0-123">In the drop-down list at the top of the Properties window (right below the title bar), select the measure **Unit Price Discount Pct**, and then select **Percent** in the **FormatString** list.</span></span>  
  
8.  <span data-ttu-id="ef9b0-124">Ändern Sie im Eigenschaftenfenster die **Name** -Eigenschaft für das **Unit Price discount PCT** -Measure in `Unit Price Discount Percentage` .</span><span class="sxs-lookup"><span data-stu-id="ef9b0-124">In the Properties window, change the **Name** property for the **Unit Price Discount Pct** measure to `Unit Price Discount Percentage`.</span></span>  
  
9. <span data-ttu-id="ef9b0-125">Klicken Sie im Bereich Measures auf **Tax Amt** , und ändern Sie den Namen dieses **Measures** in `Tax Amount` .</span><span class="sxs-lookup"><span data-stu-id="ef9b0-125">In the **Measures** pane, click **Tax Amt** and change the name of this measure to `Tax Amount`.</span></span>  
  
10. <span data-ttu-id="ef9b0-126">Klicken Sie im Eigenschaftenfenster auf das Symbol **Automatisch im Hintergrund** , um das Eigenschaftenfenster auszublenden, und anschließend auf der Symbolleiste der Registerkarte **Cubestruktur** auf **Measuresstruktur anzeigen** .</span><span class="sxs-lookup"><span data-stu-id="ef9b0-126">In the Properties window, click the **Auto Hide** icon to hide the Properties window, and then click **Show Measures Tree** on the toolbar of the **Cube Structure** tab.</span></span>  
  
11. <span data-ttu-id="ef9b0-127">Klicken Sie im Menü **File** (Datei) auf **Save All** (Alles speichern).</span><span class="sxs-lookup"><span data-stu-id="ef9b0-127">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="ef9b0-128">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="ef9b0-128">Next Task in Lesson</span></span>  
 [<span data-ttu-id="ef9b0-129">Ändern der Customer-Dimension</span><span class="sxs-lookup"><span data-stu-id="ef9b0-129">Modifying the Customer Dimension</span></span>](lesson-3-2-modifying-the-customer-dimension.md)  
  
## <a name="see-also"></a><span data-ttu-id="ef9b0-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ef9b0-130">See Also</span></span>  
 <span data-ttu-id="ef9b0-131">[Definieren von Daten Bank Dimensionen](multidimensional-models/define-database-dimensions.md) </span><span class="sxs-lookup"><span data-stu-id="ef9b0-131">[Define Database Dimensions](multidimensional-models/define-database-dimensions.md) </span></span>  
 [<span data-ttu-id="ef9b0-132">Konfigurieren von Measureeigenschaften</span><span class="sxs-lookup"><span data-stu-id="ef9b0-132">Configure Measure Properties</span></span>](multidimensional-models/configure-measure-properties.md)  
  
  
