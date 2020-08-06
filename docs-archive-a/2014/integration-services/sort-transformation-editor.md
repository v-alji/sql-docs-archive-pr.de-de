---
title: Transformations-Editor für Sortierung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sorttransformation.f1
helpviewer_keywords:
- Sort Transformation Editor
ms.assetid: 8ae23970-49a9-4d6d-9f15-c7074783347c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9f48c366f4337af29b03877f6bb20b804457a293
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726030"
---
# <a name="sort-transformation-editor"></a><span data-ttu-id="50a60-102">Transformations-Editor für Sortierung</span><span class="sxs-lookup"><span data-stu-id="50a60-102">Sort Transformation Editor</span></span>
  <span data-ttu-id="50a60-103">Mithilfe des Dialogfelds **Transformations-Editor für Sortierung** können Sie die zu sortierenden Spalten auswählen, die Sortierreihenfolge festlegen und angeben, ob Duplikate entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="50a60-103">Use the **Sort Transformation Editor** dialog box to select the columns to sort, set the sort order, and specify whether duplicates are removed.</span></span>  
  
 <span data-ttu-id="50a60-104">Weitere Informationen zur Transformation zum Sortieren finden Sie unter [Sort Transformation](data-flow/transformations/sort-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="50a60-104">To learn more about the Sort transformation, see [Sort Transformation](data-flow/transformations/sort-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="50a60-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="50a60-105">Options</span></span>  
 <span data-ttu-id="50a60-106">**Verfügbare Eingabespalten**</span><span class="sxs-lookup"><span data-stu-id="50a60-106">**Available Input Columns**</span></span>  
 <span data-ttu-id="50a60-107">Geben Sie mithilfe der Kontrollkästchen die zu sortierenden Spalten an.</span><span class="sxs-lookup"><span data-stu-id="50a60-107">Using the check boxes, specify the columns to sort.</span></span>  
  
 <span data-ttu-id="50a60-108">**Name**</span><span class="sxs-lookup"><span data-stu-id="50a60-108">**Name**</span></span>  
 <span data-ttu-id="50a60-109">Zeigen Sie den Namen jeder verfügbaren Eingabespalte an.</span><span class="sxs-lookup"><span data-stu-id="50a60-109">View the name of each available input column.</span></span>  
  
 <span data-ttu-id="50a60-110">**Passthrough**</span><span class="sxs-lookup"><span data-stu-id="50a60-110">**Passthrough**</span></span>  
 <span data-ttu-id="50a60-111">Geben Sie an, ob die Spalte in der sortierten Ausgabe eingeschlossen werden soll.</span><span class="sxs-lookup"><span data-stu-id="50a60-111">Indicate whether to include the column in the sorted output.</span></span>  
  
 <span data-ttu-id="50a60-112">**Eingabespalte**</span><span class="sxs-lookup"><span data-stu-id="50a60-112">**Input Column**</span></span>  
 <span data-ttu-id="50a60-113">Wählen Sie für jede Zeile eine Spalte aus der Liste der verfügbaren Eingabespalten aus.</span><span class="sxs-lookup"><span data-stu-id="50a60-113">Select from the list of available input columns for each row.</span></span> <span data-ttu-id="50a60-114">Ihre Auswahl wird entsprechend in der Auswahl der Kontrollkästchen in der **Verfügbare Eingabespalten** -Tabelle deutlich.</span><span class="sxs-lookup"><span data-stu-id="50a60-114">Your selections are reflected in the check box selections in the **Available Input Columns** table.</span></span>  
  
 <span data-ttu-id="50a60-115">**Ausgabealias**</span><span class="sxs-lookup"><span data-stu-id="50a60-115">**Output Alias**</span></span>  
 <span data-ttu-id="50a60-116">Geben Sie einen Alias für jede Spalte ein.</span><span class="sxs-lookup"><span data-stu-id="50a60-116">Type an alias for each output column.</span></span> <span data-ttu-id="50a60-117">Standardmäßig wird der Name der Eingabespalte verwendet. Sie können jedoch auch einen beschreibenden Namen angeben, sofern dieser eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="50a60-117">The default is the name of the input column; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="50a60-118">**Sortiertyp**</span><span class="sxs-lookup"><span data-stu-id="50a60-118">**Sort Type**</span></span>  
 <span data-ttu-id="50a60-119">Geben Sie an, ob in aufsteigender oder absteigender Reihenfolge sortiert wird.</span><span class="sxs-lookup"><span data-stu-id="50a60-119">Indicate whether to sort in ascending or descending order.</span></span>  
  
 <span data-ttu-id="50a60-120">**Sortierreihenfolge**</span><span class="sxs-lookup"><span data-stu-id="50a60-120">**Sort Order**</span></span>  
 <span data-ttu-id="50a60-121">Geben Sie die Reihenfolge an, in der die Spalten sortiert werden.</span><span class="sxs-lookup"><span data-stu-id="50a60-121">Indicate the order in which to sort columns.</span></span> <span data-ttu-id="50a60-122">Diese Einstellung muss manuell für jede Spalte vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="50a60-122">This must be set manually for each column.</span></span>  
  
 <span data-ttu-id="50a60-123">**Vergleichsflags**</span><span class="sxs-lookup"><span data-stu-id="50a60-123">**Comparison Flags**</span></span>  
 <span data-ttu-id="50a60-124">Weitere Informationen zu den Optionen für das Vergleichen von Zeichenfolgen finden Sie unter [Vergleichen von Zeichenfolgendaten](data-flow/comparing-string-data.md).</span><span class="sxs-lookup"><span data-stu-id="50a60-124">For information about the string comparison options, see [Comparing String Data](data-flow/comparing-string-data.md).</span></span>  
  
 <span data-ttu-id="50a60-125">**Zeilen mit doppelten Sortierwerten entfernen**</span><span class="sxs-lookup"><span data-stu-id="50a60-125">**Remove rows with duplicate sort values**</span></span>  
 <span data-ttu-id="50a60-126">Geben Sie an, ob die Transformation doppelte Zeilen in die Transformationsausgabe kopiert oder einen einzelnen Eintrag für alle Duplikate erstellt, basierend auf den angegebenen Optionen für den Zeichenfolgenvergleich.</span><span class="sxs-lookup"><span data-stu-id="50a60-126">Indicate whether the transformation copies duplicate rows to the transformation output, or creates a single entry for all duplicates, based on the specified string comparison options.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50a60-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="50a60-127">See Also</span></span>  
 [<span data-ttu-id="50a60-128">Fehler- und Meldungsreferenz von Integration Services</span><span class="sxs-lookup"><span data-stu-id="50a60-128">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
