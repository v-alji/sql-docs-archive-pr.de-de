---
title: Aggregieren von Werten in einem Dataset mithilfe der Transformation für das Aggregieren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Aggregate transformation [Integration Services]
- aggregate values [Integration Services]
- datasets [Integration Services], aggregate values
ms.assetid: 01b81c0f-d5e0-483b-81b2-73800a6945ac
author: chugugrace
ms.author: chugu
ms.openlocfilehash: de918c6c2adf194d5808ccd1b64c77a94a52e357
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695885"
---
# <a name="aggregate-values-in-a-dataset-by-using-the-aggregate-transformation"></a><span data-ttu-id="f7383-102">Aggregieren von Werten in einem Dataset mithilfe der Transformation für das Aggregieren</span><span class="sxs-lookup"><span data-stu-id="f7383-102">Aggregate Values in a Dataset by Using the Aggregate Transformation</span></span>
  <span data-ttu-id="f7383-103">Um eine Transformation für das Aggregieren hinzuzufügen und zu konfigurieren, muss das Paket bereits mindestens einen Datenflusstask und eine Quelle enthalten.</span><span class="sxs-lookup"><span data-stu-id="f7383-103">To add and configure an Aggregate transformation, the package must already include at least one Data Flow task and one source.</span></span>  
  
### <a name="to-aggregate-values-in-a-dataset"></a><span data-ttu-id="f7383-104">So aggregieren Sie Werte in einem Dataset</span><span class="sxs-lookup"><span data-stu-id="f7383-104">To aggregate values in a dataset</span></span>  
  
1.  <span data-ttu-id="f7383-105">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] das [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]-Projekt mit dem gewünschten Paket.</span><span class="sxs-lookup"><span data-stu-id="f7383-105">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="f7383-106">Doppelklicken Sie im Projektmappen-Explorer auf das Paket, um es zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f7383-106">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="f7383-107">Klicken Sie auf die Registerkarte **Datenfluss** , und ziehen Sie dann aus dem Bereich **Toolbox**die Transformation für das Aggregieren auf die Entwurfsoberfläche.</span><span class="sxs-lookup"><span data-stu-id="f7383-107">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the Aggregate transformation to the design surface.</span></span>  
  
4.  <span data-ttu-id="f7383-108">Verbinden Sie die Transformation für das Aggregieren mit dem Datenfluss, indem Sie einen Konnektor von der Quelle oder der vorherigen Transformation auf die Transformation für das Aggregieren ziehen.</span><span class="sxs-lookup"><span data-stu-id="f7383-108">Connect the Aggregate transformation to the data flow by dragging a connector from the source or the previous transformation to the Aggregate transformation.</span></span>  
  
5.  <span data-ttu-id="f7383-109">Doppelklicken Sie auf die Transformation.</span><span class="sxs-lookup"><span data-stu-id="f7383-109">Double-click the transformation.</span></span>  
  
6.  <span data-ttu-id="f7383-110">Klicken Sie im Dialogfeld **Transformations-Editor für Aggregieren** auf die Registerkarte **Aggregationen** .</span><span class="sxs-lookup"><span data-stu-id="f7383-110">In the **Aggregate Transformation Editor** dialog box, click the **Aggregations** tab.</span></span>  
  
7.  <span data-ttu-id="f7383-111">Aktivieren Sie in der Liste **Verfügbare Eingabespalten** das Kontrollkästchen neben den Spalten, für die Sie Werte aggregieren wollen.</span><span class="sxs-lookup"><span data-stu-id="f7383-111">In the **Available Input Columns** list, select the check box by the columns on which you want to aggregate values.</span></span> <span data-ttu-id="f7383-112">Die ausgewählten Spalten werden in der Tabelle angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f7383-112">The selected columns appear in the table.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f7383-113">Sie können eine Spalte mehrmals auswählen und mehrere Transformationen auf die Spalte anwenden.</span><span class="sxs-lookup"><span data-stu-id="f7383-113">You can select a column multiple times, applying multiple transformations to the column.</span></span> <span data-ttu-id="f7383-114">Um Aggregationen eindeutig zu identifizieren, wird an den Standardnamen des Ausgabealias der Spalte eine Zahl angefügt.</span><span class="sxs-lookup"><span data-stu-id="f7383-114">To uniquely identify aggregations, a number is appended to the default name of the output alias of the column.</span></span>  
  
8.  <span data-ttu-id="f7383-115">Optional können Sie den Wert in den **Ausgabealias** -Spalten ändern.</span><span class="sxs-lookup"><span data-stu-id="f7383-115">Optionally, modify the value in the **Output Alias** columns.</span></span>  
  
9. <span data-ttu-id="f7383-116">Um den Standardaggregationsvorgang, **GROUP BY**, zu ändern, wählen Sie in der Liste **Vorgang** einen anderen Vorgang aus.</span><span class="sxs-lookup"><span data-stu-id="f7383-116">To change the default aggregation operation, **Group by**, select a different operation in the **Operation** list.</span></span>  
  
10. <span data-ttu-id="f7383-117">Wählen Sie zum Ändern des Standardvergleichs die jeweiligen in der **Vergleichsflags** -Spalte aufgelisteten Vergleichsflags aus.</span><span class="sxs-lookup"><span data-stu-id="f7383-117">To change the default comparison, select the individual comparison flags listed in the **Comparison Flags** column.</span></span> <span data-ttu-id="f7383-118">Beim Vergleichen werden standardmäßig die Groß-/Kleinschreibung, der Kanatyp, Zeichen ohne Zwischenraum und die Zeichenbreite ignoriert.</span><span class="sxs-lookup"><span data-stu-id="f7383-118">By default, a comparison ignores case, kana type, non-spacing characters, and character width.</span></span>  
  
11. <span data-ttu-id="f7383-119">Geben Sie optional für die **COUNT DISTINCT** -Aggregation die genaue Anzahl von unterschiedlichen Werten in der **COUNT DISTINCT-Schlüssel** -Spalte an, oder wählen Sie die geschätzte Anzahl in der **COUNT DISTINCT-Skala** -Spalte aus.</span><span class="sxs-lookup"><span data-stu-id="f7383-119">Optionally, for the **Count distinct** aggregation, specify an exact number of distinct values in the **Count Distinct Keys** column, or select an approximate count in the **Count Distinct Scale** column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f7383-120">Durch Bereitstellen der genauen oder geschätzten Anzahl von unterschiedlichen Werten wird die Leistung optimiert, da die Transformation die hierfür erforderliche Arbeitsspeichermenge zuordnen kann.</span><span class="sxs-lookup"><span data-stu-id="f7383-120">Providing the number of distinct values, exact or approximate, optimizes performance, because the transformation can preallocate an appropriate amount of memory to do its work.</span></span>  
  
12. <span data-ttu-id="f7383-121">Klicken Sie optional auf **Erweitert** , und aktualisieren Sie den Namen der Ausgabe für die Transformation für das Aggregieren.</span><span class="sxs-lookup"><span data-stu-id="f7383-121">Optionally, click **Advanced** and update the name of the Aggregate transformation output.</span></span> <span data-ttu-id="f7383-122">Wenn die Aggregationen einen- `Group By` Vorgang einschließen, können Sie eine ungefähre Anzahl von Gruppierungs Schlüsselwerten in der **Schlüssel Skala** -Spalte auswählen oder eine genaue Anzahl von Gruppierungs Schlüsselwerten in der **Schlüssel** Spalte angeben.</span><span class="sxs-lookup"><span data-stu-id="f7383-122">If the aggregations include a `Group By` operation, you can select an approximate count of grouping key values in the **Keys Scale** column or specify an exact number of grouping key values in the **Keys** column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f7383-123">Durch Bereitstellen der genauen oder geschätzten Anzahl von unterschiedlichen Werten wird die Leistung optimiert, da die Transformation die hierfür erforderliche Arbeitsspeichermenge zuordnen kann.</span><span class="sxs-lookup"><span data-stu-id="f7383-123">Providing the number of distinct values, exact or approximate, optimizes performance, because the transformation can preallocate an appropriate amount of memory to do its work.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f7383-124">Die Optionen **Schlüsselskala** und **Schlüssel** schließen sich gegenseitig aus.</span><span class="sxs-lookup"><span data-stu-id="f7383-124">The **Keys Scale** and **Keys** options are mutually exclusive.</span></span> <span data-ttu-id="f7383-125">Wenn Sie in beide Spalten Werte eingeben, wird der jeweils größere Wert der **Schlüsselskala** -Spalte bzw. der **Schlüssel** -Spalte verwendet.</span><span class="sxs-lookup"><span data-stu-id="f7383-125">If you enter values in both columns, the larger value in either **Keys Scale** or **Keys** is used.</span></span>  
  
13. <span data-ttu-id="f7383-126">Klicken Sie optional auf die Registerkarte **Erweitert** , und legen Sie die Attribute fest, die zum Optimieren aller Vorgänge gelten, die die Transformation für das Aggregieren ausführt.</span><span class="sxs-lookup"><span data-stu-id="f7383-126">Optionally, click the **Advanced** tab and set the attributes that apply to optimizing all the operations that the Aggregate transformation performs.</span></span>  
  
14. <span data-ttu-id="f7383-127">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f7383-127">Click **OK**.</span></span>  
  
15. <span data-ttu-id="f7383-128">Klicken Sie im Menü **Datei** auf **Ausgewählte Elemente speichern** , um das aktualisierte Paket zu speichern.</span><span class="sxs-lookup"><span data-stu-id="f7383-128">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7383-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f7383-129">See Also</span></span>  
 <span data-ttu-id="f7383-130">[Transformation für das Aggregieren](aggregate-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="f7383-130">[Aggregate Transformation](aggregate-transformation.md) </span></span>  
 <span data-ttu-id="f7383-131">[SQL Server Integration Services-Transformationen](integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="f7383-131">[Integration Services Transformations](integration-services-transformations.md) </span></span>  
 <span data-ttu-id="f7383-132">[SQL Server Integration Services-Pfade](../integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="f7383-132">[Integration Services Paths](../integration-services-paths.md) </span></span>  
 [<span data-ttu-id="f7383-133">Datenflusstask</span><span class="sxs-lookup"><span data-stu-id="f7383-133">Data Flow Task</span></span>](../../control-flow/data-flow-task.md)  
  
  
