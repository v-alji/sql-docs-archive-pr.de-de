---
title: Beziehungen erstellen | Microsoft Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.createrelationships.f1
ms.assetid: 6ebd305f-ffd2-4a1d-b24c-e28c151b94f5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5a1095e193587ae7d416311031e5297a035ca37e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615460"
---
# <a name="create-relationships"></a><span data-ttu-id="4b3f3-102">Beziehungen erstellen</span><span class="sxs-lookup"><span data-stu-id="4b3f3-102">Create Relationships</span></span>
  <span data-ttu-id="4b3f3-103">Im Dialogfeld **Beziehungen erstellen** werden Zuordnungen zwischen Quellspalten und den von Ihnen im Transformations-Editor für Fuzzysuche, Transformations-Editor für Suche und Transformations-Editor für Ausdruckssuche konfigurierten Spalten von Nachschlagetabellen bearbeitet.</span><span class="sxs-lookup"><span data-stu-id="4b3f3-103">Use the **Create Relationships** dialog box to edit mappings between the source columns and the lookup table columns that you configured in the Fuzzy Lookup Transformation Editor, the Lookup Transformation Editor, and the Term Lookup Transformation Editor.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4b3f3-104">Im Dialogfeld **Beziehungen erstellen** werden nur die Listen **Eingabespalte** und **Suchspalte** angezeigt, wenn der Aufruf aus dem Transformations-Editor für Ausdruckssuche erfolgt.</span><span class="sxs-lookup"><span data-stu-id="4b3f3-104">The **Create Relationships** dialog box displays only the **Input Column** and **Lookup Column** lists when invoked from the Term Lookup Transformation Editor.</span></span>  
  
 <span data-ttu-id="4b3f3-105">Weitere Informationen zu den Transformationen, die das Dialogfeld **Beziehungen erstellen** verwenden, finden Sie unter [Fuzzy Lookup Transformation](lookup-transformation.md), [Lookup Transformation](lookup-transformation.md)und [Term Lookup Transformation](term-lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="4b3f3-105">To learn more about the transformations that use the **Create Relationships** dialog box, see [Fuzzy Lookup Transformation](lookup-transformation.md), [Lookup Transformation](lookup-transformation.md), and [Term Lookup Transformation](term-lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="4b3f3-106">Tastatur</span><span class="sxs-lookup"><span data-stu-id="4b3f3-106">Options</span></span>  
 <span data-ttu-id="4b3f3-107">**Eingabespalte**</span><span class="sxs-lookup"><span data-stu-id="4b3f3-107">**Input Column**</span></span>  
 <span data-ttu-id="4b3f3-108">Wählen Sie Spalten aus der Liste der verfügbaren Eingabespalten aus.</span><span class="sxs-lookup"><span data-stu-id="4b3f3-108">Select from the list of available input columns.</span></span>  
  
 <span data-ttu-id="4b3f3-109">**Suchspalte**</span><span class="sxs-lookup"><span data-stu-id="4b3f3-109">**Lookup Column**</span></span>  
 <span data-ttu-id="4b3f3-110">Wählen Sie eine Option aus der Liste der verfügbaren Suchspalten aus.</span><span class="sxs-lookup"><span data-stu-id="4b3f3-110">Select from the list of available lookup columns.</span></span>  
  
 <span data-ttu-id="4b3f3-111">**Zuordnungstyp**</span><span class="sxs-lookup"><span data-stu-id="4b3f3-111">**Mapping Type**</span></span>  
 <span data-ttu-id="4b3f3-112">Wählen Sie genaue oder Fuzzyübereinstimmungen aus.</span><span class="sxs-lookup"><span data-stu-id="4b3f3-112">Select fuzzy or exact matching.</span></span>  
  
 <span data-ttu-id="4b3f3-113">Wenn Sie Fuzzyübereinstimmungen verwenden, werden Zeilen als doppelt erkannt, sobald sie in den Spalten, deren Übereinstimmungstyp Fuzzy lautet, ausreichende Übereinstimmungen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="4b3f3-113">When you use fuzzy matching, rows are considered duplicates if they are sufficiently similar across all columns that have a fuzzy match type.</span></span> <span data-ttu-id="4b3f3-114">Um bei der Fuzzyübereinstimmung bessere Ergebnisse zu erzielen, können Sie angeben, dass für einige Spalten anstelle von Fuzzy die genaue Übereinstimmung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4b3f3-114">To obtain better results from fuzzy matching, you can specify that some columns should use exact matching instead of fuzzy matching.</span></span> <span data-ttu-id="4b3f3-115">Wenn Ihnen beispielsweise bekannt ist, dass eine bestimmte Spalte weder Fehler noch Inkonsistenzen aufweist, können Sie für diese Spalte die genaue Übereinstimmung angeben, sodass nur Zeilen, deren Werte genau mit Werten in der Spalte übereinstimmen, als mögliche Dopplungen erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="4b3f3-115">For example, if you know that a certain column contains no errors or inconsistencies, you can specify exact matching on that column, so that only rows which contain identical values in this column are considered as possible duplicates.</span></span> <span data-ttu-id="4b3f3-116">Dadurch erhöht sich die Genauigkeit der Fuzzyübereinstimmung für andere Spalten.</span><span class="sxs-lookup"><span data-stu-id="4b3f3-116">This increases the accuracy of fuzzy matching on other columns.</span></span>  
  
 <span data-ttu-id="4b3f3-117">**Vergleichsflags**</span><span class="sxs-lookup"><span data-stu-id="4b3f3-117">**Comparison Flags**</span></span>  
 <span data-ttu-id="4b3f3-118">Weitere Informationen zu den Optionen für das Vergleichen von Zeichenfolgen finden Sie unter [Vergleichen von Zeichenfolgendaten](../comparing-string-data.md).</span><span class="sxs-lookup"><span data-stu-id="4b3f3-118">For information about the string comparison options, see [Comparing String Data](../comparing-string-data.md).</span></span>  
  
 <span data-ttu-id="4b3f3-119">**Minimale Ähnlichkeit**</span><span class="sxs-lookup"><span data-stu-id="4b3f3-119">**Minimum Similarity**</span></span>  
 <span data-ttu-id="4b3f3-120">Legen Sie mithilfe des Schiebereglers den Schwellenwert für die Ähnlichkeit auf Spaltenebene fest.</span><span class="sxs-lookup"><span data-stu-id="4b3f3-120">Set the similarity threshold at the column level by using the slider.</span></span> <span data-ttu-id="4b3f3-121">Je näher der Wert an 1 liegt, desto stärker muss die Ähnlichkeit zwischen Suchwert und Quellwert sein, um als Übereinstimmung zu gelten.</span><span class="sxs-lookup"><span data-stu-id="4b3f3-121">The closer the value is to 1, the more the lookup value must resemble the source value to qualify as a match.</span></span> <span data-ttu-id="4b3f3-122">Durch eine Erhöhung des Schwellenwertes kann die Geschwindigkeit beim Abgleich erhöht werden, weil als Kandidaten dann weniger Datensätze berücksichtigt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="4b3f3-122">Increasing the threshold can improve the speed of matching because fewer candidate records have to be considered.</span></span>  
  
 <span data-ttu-id="4b3f3-123">**Ähnlichkeitsausgabealias**</span><span class="sxs-lookup"><span data-stu-id="4b3f3-123">**Similarity Output Alias**</span></span>  
 <span data-ttu-id="4b3f3-124">Geben Sie den Namen für eine Ausgabespalte an, die die Ähnlichkeitsergebnisse für die ausgewählte Spalte enthält.</span><span class="sxs-lookup"><span data-stu-id="4b3f3-124">Specify the name for a new output column that contains the similarity scores for the selected column.</span></span> <span data-ttu-id="4b3f3-125">Wenn Sie diesen Wert nicht angeben, wird die Ausgabespalte nicht erstellt.</span><span class="sxs-lookup"><span data-stu-id="4b3f3-125">If you leave this value empty, the output column is not created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b3f3-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4b3f3-126">See Also</span></span>  
 <span data-ttu-id="4b3f3-127">[Fehler- und Meldungsreferenz von Integration Services](../../integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="4b3f3-127">[Integration Services Error and Message Reference](../../integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="4b3f3-128">[Transformations-Editor für Fuzzysuche &#40;Registerkarte „Spalten“&#41;](../../fuzzy-lookup-transformation-editor-columns-tab.md) </span><span class="sxs-lookup"><span data-stu-id="4b3f3-128">[Fuzzy Lookup Transformation Editor &#40;Columns Tab&#41;](../../fuzzy-lookup-transformation-editor-columns-tab.md) </span></span>  
 <span data-ttu-id="4b3f3-129">[Transformations-Editor für Suche &#40;Seite „Spalten“&#41;](../../lookup-transformation-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="4b3f3-129">[Lookup Transformation Editor &#40;Columns Page&#41;](../../lookup-transformation-editor-columns-page.md) </span></span>  
 [<span data-ttu-id="4b3f3-130">Transformations-Editor für Ausdruckssuche &#40;Registerkarte Ausdruckssuche&#41;</span><span class="sxs-lookup"><span data-stu-id="4b3f3-130">Term Lookup Transformation Editor &#40;Term Lookup Tab&#41;</span></span>](../../term-lookup-transformation-editor-term-lookup-tab.md)  
  
  
