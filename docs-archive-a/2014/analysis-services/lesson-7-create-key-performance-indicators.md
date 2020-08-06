---
title: 'Lektion 8: Erstellen von Key Performance-Indikatoren | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a6c8ac2b-64ba-456f-b418-7bf0afe145d1
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3beaab8a34844ecbd633eb5fabbacf37edfede2b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698732"
---
# <a name="lesson-8-create-key-performance-indicators"></a><span data-ttu-id="4106b-102">Lektion 8: Erstellen von Key Performance Indicators</span><span class="sxs-lookup"><span data-stu-id="4106b-102">Lesson 8: Create Key Performance Indicators</span></span>
  <span data-ttu-id="4106b-103">In dieser Lektion erstellen Sie Leistungskennzahlen (Key Performance Indicators, KPIs).</span><span class="sxs-lookup"><span data-stu-id="4106b-103">In this lesson, you will create Key Performance Indicators (KPIs).</span></span> <span data-ttu-id="4106b-104">KPIs dienen zum Messen der Leistung eines Werts, der durch ein *basismeasure* definiert wird, anhand eines *Zielwerts* , der ebenfalls durch ein Measure oder einen absoluten Wert definiert wird.</span><span class="sxs-lookup"><span data-stu-id="4106b-104">KPIs are used to gauge performance of a value, defined by a *Base* measure, against a *Target* value, also defined by a measure or by an absolute value.</span></span> <span data-ttu-id="4106b-105">Mit KPIs können Geschäftsleuten in Berichterstellungsclientanwendungen Zusammenfassungen von Geschäftserfolgen schnell und einfach verstehen bzw. Trends erkennen.</span><span class="sxs-lookup"><span data-stu-id="4106b-105">In reporting client applications, KPIs can provide business professionals a quick and easy way to understand a summary of business success or to identify trends.</span></span> <span data-ttu-id="4106b-106">Weitere Informationen finden Sie unter [KPIs &#40;SSAS – tabellarisch&#41;](tabular-models/kpis-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="4106b-106">To learn more, see [KPIs &#40;SSAS Tabular&#41;](tabular-models/kpis-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="4106b-107">Geschätzte Zeit zum Bearbeiten dieser Lektion: **15 Minuten**</span><span class="sxs-lookup"><span data-stu-id="4106b-107">Estimated time to complete this lesson: **15 minutes**</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4106b-108">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="4106b-108">Prerequisites</span></span>  
 <span data-ttu-id="4106b-109">Dieses Thema ist Teil eines Tutorials zur Tabellenmodellierung, das in der richtigen Reihenfolge absolviert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="4106b-109">This topic is part of a tabular modeling tutorial, which should be completed in order.</span></span> <span data-ttu-id="4106b-110">Sie sollten vor dem Ausführen der Aufgaben in dieser Lektion die vorherige Lektion abgeschlossen haben: [Lektion 7: Erstellen von Measures](lesson-6-create-measures.md).</span><span class="sxs-lookup"><span data-stu-id="4106b-110">Before performing the tasks in this lesson, you should have completed the previous lesson: [Lesson 7: Create Measures](lesson-6-create-measures.md).</span></span>  
  
## <a name="create-key-performance-indicators"></a><span data-ttu-id="4106b-111">Erstellen von Key Performance Indicators</span><span class="sxs-lookup"><span data-stu-id="4106b-111">Create Key Performance Indicators</span></span>  
  
#### <a name="to-create-an-internet-current-quarter-sales-performance-kpi"></a><span data-ttu-id="4106b-112">So erstellen Sie einen KPI zur Internetverkaufsleistung des aktuellen Quartals</span><span class="sxs-lookup"><span data-stu-id="4106b-112">To create an Internet Current Quarter Sales Performance KPI</span></span>  
  
1.  <span data-ttu-id="4106b-113">Klicken Sie im Modell-Designer auf die Tabelle (Registerkarte) **Internet Sales** .</span><span class="sxs-lookup"><span data-stu-id="4106b-113">In the model designer, click the **Internet Sales** table (tab).</span></span>  
  
2.  <span data-ttu-id="4106b-114">Klicken Sie im Measureraster auf eine leere Zelle.</span><span class="sxs-lookup"><span data-stu-id="4106b-114">In the measure grid, click an empty cell.</span></span>  
  
3.  <span data-ttu-id="4106b-115">Geben Sie in der Bearbeitungsleiste über der Tabelle folgende Formel ein:</span><span class="sxs-lookup"><span data-stu-id="4106b-115">In the formula bar, above the table, type the following formula:</span></span>  
  
     `Internet Current Quarter Sales Performance :=IFERROR([Internet Current Quarter Sales]/[Internet Previous Quarter Sales Proportion to QTD],BLANK())`  
  
     <span data-ttu-id="4106b-116">Drücken Sie nach dem Erstellen der Formel die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="4106b-116">When you have finished building the formula, press ENTER.</span></span>  
  
     <span data-ttu-id="4106b-117">Dieses Measure dient als Basismeasure für den KPI.</span><span class="sxs-lookup"><span data-stu-id="4106b-117">This measure will serve as the Base measure for the KPI.</span></span>  
  
4.  <span data-ttu-id="4106b-118">Klicken Sie im Measureraster mit der rechten Maustaste auf das Measure **Internet Current Quarter Sales Performance** und anschließend auf **KPI erstellen**.</span><span class="sxs-lookup"><span data-stu-id="4106b-118">In the measure grid, right-click the **Internet Current Quarter Sales Performance** measure, and then click **Create KPI**.</span></span>  
  
     <span data-ttu-id="4106b-119">Das Dialogfeld **Key Performance Indicator** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="4106b-119">The **Key Performance Indicator** dialog box opens.</span></span>  
  
5.  <span data-ttu-id="4106b-120">Wählen Sie im Dialogfeld **Key Performance Indicator** unter **Zielwert definieren**die Option **Absoluter Wert** aus.</span><span class="sxs-lookup"><span data-stu-id="4106b-120">In the **Key Performance Indicator** dialog box, in **Define Target Value**, select the **Absolute Value** option.</span></span>  
  
6.  <span data-ttu-id="4106b-121">Geben Sie im Feld **absoluter Wert den Wert** ein `1.1` , und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="4106b-121">In the **Absolute Value** field, type `1.1`, and then press ENTER.</span></span>  
  
7.  <span data-ttu-id="4106b-122">Geben Sie in **Status Schwellenwerte definieren**im linken (unteren) schiebereglerfeld ein `1` , und geben Sie dann im rechten (hohen) Schieberegler ein `1.07` .</span><span class="sxs-lookup"><span data-stu-id="4106b-122">In **Define Status Thresholds**, in the left (low) slider field, type `1`, and then in the right (high) slider field, type `1.07`.</span></span>  
  
8.  <span data-ttu-id="4106b-123">Wählen Sie unter **Symbolart auswählen**den Symboltyp Diamant (rot), Dreieck (gelb) oder Kreis (grün) aus.</span><span class="sxs-lookup"><span data-stu-id="4106b-123">In **Select Icon Style**, select the diamond (red), triangle (yellow), circle (green) icon type.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="4106b-124">Achten Sie auf das erweiterbare Feld **Beschreibungen** unterhalb der verfügbaren Symbolarten.</span><span class="sxs-lookup"><span data-stu-id="4106b-124">Notice the **Descriptions** expandable field below the available icon styles.</span></span> <span data-ttu-id="4106b-125">Sie können Typbeschreibungen eingeben, damit sich die verschiedenen KPI-Elemente in Clientanwendungen leichter identifizieren lassen.</span><span class="sxs-lookup"><span data-stu-id="4106b-125">You can type descriptions for the various KPI elements to make them more identifiable in client applications.</span></span>  
  
9. <span data-ttu-id="4106b-126">Klicken Sie auf **OK** , um den KPI abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="4106b-126">Click **OK** to complete the KPI.</span></span>  
  
     <span data-ttu-id="4106b-127">Achten Sie im Measureraster auf das Symbol neben dem Measure **Internet Current Quarter Sales Performance** .</span><span class="sxs-lookup"><span data-stu-id="4106b-127">In the measure grid, notice the icon next to the **Internet Current Quarter Sales Performance** measure.</span></span> <span data-ttu-id="4106b-128">Dieses Symbol gibt an, dass das Measure als Basiswert für einen KPI dient.</span><span class="sxs-lookup"><span data-stu-id="4106b-128">This icon indicates that this measure serves as a Base value for a KPI.</span></span>  
  
#### <a name="to-create-an-internet-current-quarter-margin-performance-kpi"></a><span data-ttu-id="4106b-129">So erstellen Sie einen KPI zur Internetumsatzleistung des aktuellen Quartals</span><span class="sxs-lookup"><span data-stu-id="4106b-129">To create an Internet Current Quarter Margin Performance KPI</span></span>  
  
1.  <span data-ttu-id="4106b-130">Klicken Sie im Measureraster für die Tabelle **Internet Sales** auf eine leere Zelle.</span><span class="sxs-lookup"><span data-stu-id="4106b-130">In the measure grid for the **Internet Sales** table, click an empty cell.</span></span>  
  
2.  <span data-ttu-id="4106b-131">Geben Sie in der Bearbeitungsleiste über der Tabelle folgende Formel ein:</span><span class="sxs-lookup"><span data-stu-id="4106b-131">In the formula bar, above the table, type the following formula:</span></span>  
  
     `Internet Current Quarter Margin Performance :=IF([Internet Previous Quarter Margin Proportion to QTD]<>0,([Internet Current Quarter Margin]-[Internet Previous Quarter Margin Proportion to QTD])/[Internet Previous Quarter Margin Proportion to QTD],BLANK())`  
  
     <span data-ttu-id="4106b-132">Drücken Sie nach dem Erstellen der Formel die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="4106b-132">When you have finished building the formula, press ENTER.</span></span>  
  
3.  <span data-ttu-id="4106b-133">Klicken Sie im Measureraster mit der rechten Maustaste auf das Measure **Internet Current Quarter Margin Performance** und anschließend auf **KPI erstellen**.</span><span class="sxs-lookup"><span data-stu-id="4106b-133">In the measure grid, right-click the **Internet Current Quarter Margin Performance** measure, and then click **Create KPI**.</span></span>  
  
4.  <span data-ttu-id="4106b-134">Wählen Sie im Dialogfeld **Key Performance Indicator** unter **Zielwert definieren**die Option **Absoluter Wert** aus.</span><span class="sxs-lookup"><span data-stu-id="4106b-134">In the **Key Performance Indicator** dialog box, in **Define Target Value**, select the **Absolute Value** option.</span></span>  
  
5.  <span data-ttu-id="4106b-135">Geben Sie im Feld **absoluter Wert den Wert** ein `1.25` .</span><span class="sxs-lookup"><span data-stu-id="4106b-135">In the **Absolute Value** field, type `1.25`.</span></span>  
  
6.  <span data-ttu-id="4106b-136">Verschieben Sie unter **Statusschwellenwerte definieren**den linken (unteren) Schieberegler, bis im Feld der Wert **0,8**angezeigt wird. Verschieben Sie anschließend den rechten (oberen) Schieberegler, bis im Feld **1,03**angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="4106b-136">In **Define Status Thresholds**, slide the left (low) slider field until the field displays **0.8**, and then slide the right (high) slider field, until the field displays **1.03**.</span></span>  
  
7.  <span data-ttu-id="4106b-137">Wählen Sie unter **Symbolart auswählen** die Raute (rot), das Dreieck, (gelb) und den Kreis (grün) aus, und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="4106b-137">In **Select Icon Style**, select the diamond (red), triangle (yellow), circle (green) icon type, and then click **OK**.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="4106b-138">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="4106b-138">Next Step</span></span>  
 <span data-ttu-id="4106b-139">Wenn Sie mit diesem Tutorial fortfahren möchten, wechseln Sie zur nächsten Lektion: [Lektion 9: Erstellen von Perspektiven](lesson-8-create-perspectives.md).</span><span class="sxs-lookup"><span data-stu-id="4106b-139">To continue this tutorial, go to the next lesson: [Lesson 9: Create Perspectives](lesson-8-create-perspectives.md).</span></span>  
  
  
