---
title: Benannte Mengen erstellen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- calculations [Analysis Services], named sets
- named sets [Analysis Services]
- members [Analysis Services], named sets
ms.assetid: 03cf97a4-1a18-45f3-acb0-35123bd619be
author: minewiskan
ms.author: owend
ms.openlocfilehash: e92984102ceb8ad0ac049c15870e9f1efd6090fe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696254"
---
# <a name="create-named-sets"></a><span data-ttu-id="d2175-102">Erstellen von benannten Mengen</span><span class="sxs-lookup"><span data-stu-id="d2175-102">Create Named Sets</span></span>
  <span data-ttu-id="d2175-103">Eine benannte Menge ist eine Menge von Dimensionselementen oder ein Mengenausdruck, der zur Wiederverwendung, z. B. in MDX-Abfragen (Multidimensional Expressions), erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="d2175-103">A named set is a set of dimension members or a set expression that is created for reuse, for example in Multidimensional Expressions (MDX) queries.</span></span> <span data-ttu-id="d2175-104">Sie können benannte Mengen durch Kombinieren von Cubedaten, arithmetischen Operatoren, Zahlen und Funktionen erstellen.</span><span class="sxs-lookup"><span data-stu-id="d2175-104">You can create named sets by combining cube data, arithmetic operators, numbers, and functions.</span></span> <span data-ttu-id="d2175-105">Sie können beispielsweise eine benannte Menge mit dem Namen Top Ten Factories erstellen, die die zehn Elemente der Factories-Dimension mit den höchsten Werten des Production-Measures enthält.</span><span class="sxs-lookup"><span data-stu-id="d2175-105">For example, you can create a named set called Top Ten Factories that contains the ten members of the Factories dimension that have the highest values for the Production measure.</span></span> <span data-ttu-id="d2175-106">Top Ten Factories kann dann von Endbenutzern in Abfragen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d2175-106">Top Ten Factories can then be used in queries by end users.</span></span> <span data-ttu-id="d2175-107">Ein Endbenutzer kann Top Ten Factories z. B. auf eine Achse und die Measures-Dimension, einschließlich Production, auf eine andere Achse platzieren.</span><span class="sxs-lookup"><span data-stu-id="d2175-107">For example, an end user can place Top Ten Factories on one axis and the Measures dimension, including Production, on another axis.</span></span> <span data-ttu-id="d2175-108">Weitere Informationen finden Sie unter [Berechnungen in mehrdimensionalen Modellen](calculations-in-multidimensional-models.md) und [Erstellen von benannten Mengen in MDX &#40;MDX&#41;](mdx/mdx-named-sets-building-named-sets.md).</span><span class="sxs-lookup"><span data-stu-id="d2175-108">For more information, see [Calculations in Multidimensional Models](calculations-in-multidimensional-models.md), and [Building Named Sets in MDX &#40;MDX&#41;](mdx/mdx-named-sets-building-named-sets.md).</span></span>  
  
 <span data-ttu-id="d2175-109">Mithilfe des Befehls **Neue benannte Menge** auf der Registerkarte **Berechnungen** des Cube-Designers können Sie eine benannte Menge erstellen.</span><span class="sxs-lookup"><span data-stu-id="d2175-109">To create a named set, use the **New Named Set** command on the **Calculations** tab of Cube Designer.</span></span> <span data-ttu-id="d2175-110">Dieser Befehl kann im Menü **Cube** auf der Symbolleiste der Registerkarte **Berechnungen** aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="d2175-110">This command can be invoked on the **Cube** menu on the **Calculations** tab toolbar.</span></span> <span data-ttu-id="d2175-111">Mit diesem Befehl wird ein Formular zum Angeben der folgenden Optionen für die benannte Menge angezeigt:</span><span class="sxs-lookup"><span data-stu-id="d2175-111">This command displays a form to specify the following options for the named set:</span></span>  
  
 <span data-ttu-id="d2175-112">**Name**</span><span class="sxs-lookup"><span data-stu-id="d2175-112">**Name**</span></span>  
 <span data-ttu-id="d2175-113">Wählt den Namen der benannten Menge aus.</span><span class="sxs-lookup"><span data-stu-id="d2175-113">Select the name of the named set.</span></span> <span data-ttu-id="d2175-114">Dieser Name wird Endbenutzern angezeigt, wenn sie den Cube durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="d2175-114">This name appears to end users when they browse the cube.</span></span>  
  
 <span data-ttu-id="d2175-115">**Ausdruck**</span><span class="sxs-lookup"><span data-stu-id="d2175-115">**Expression**</span></span>  
 <span data-ttu-id="d2175-116">Gibt den Ausdruck an, der die benannte Menge erzeugt.</span><span class="sxs-lookup"><span data-stu-id="d2175-116">Specify the expression that produces the named set.</span></span> <span data-ttu-id="d2175-117">Dieser Ausdruck kann in MDX geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="d2175-117">This expression can be written in MDX.</span></span> <span data-ttu-id="d2175-118">Der Ausdruck kann Folgendes enthalten:</span><span class="sxs-lookup"><span data-stu-id="d2175-118">The expression can contain any of the following:</span></span>  
  
-   <span data-ttu-id="d2175-119">Datenausdrücke, die für Cubekomponenten wie Dimensionen, Ebenen, Measures usw. stehen.</span><span class="sxs-lookup"><span data-stu-id="d2175-119">Data expressions that represent cube components such as dimensions, levels, measures, and so on.</span></span>  
  
-   <span data-ttu-id="d2175-120">Arithmetische Operatoren.</span><span class="sxs-lookup"><span data-stu-id="d2175-120">Arithmetic operators.</span></span>  
  
-   <span data-ttu-id="d2175-121">Zahlen.</span><span class="sxs-lookup"><span data-stu-id="d2175-121">Numbers.</span></span>  
  
-   <span data-ttu-id="d2175-122">Funktionen</span><span class="sxs-lookup"><span data-stu-id="d2175-122">Functions.</span></span>  
  
 <span data-ttu-id="d2175-123">Sie können Cubekomponenten von der Registerkarte **Metadaten** des Bereichs **Berechnungstools** in das Feld **Ausdruck** im Bereich des Formular-Editors für benannte Mengen \*\*\*\* kopieren oder ziehen.</span><span class="sxs-lookup"><span data-stu-id="d2175-123">You can copy or drag cube components from the **Metadata** tab of the **Calculation Tools** pane to the **Expression** box in the **Named Set Form Editor** pane.</span></span> <span data-ttu-id="d2175-124">Sie können Funktionen von der Registerkarte **Funktionen** des Bereichs **Berechnungstools** in das Feld **Ausdruck** im Bereich des Formular-Editors für benannte Mengen \*\*\*\* kopieren oder ziehen.</span><span class="sxs-lookup"><span data-stu-id="d2175-124">You can copy or drag functions from the **Functions** tab in the **Calculation Tools** pane to the **Expression** box in the **Named Set Form Editor** pane.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d2175-125">Wenn Sie den Mengen Ausdruck durch explizites benennen der Elemente in der Menge erstellen, schließen Sie die Liste der Elemente in ein Paar geschweifter Klammern ( {} ) ein.</span><span class="sxs-lookup"><span data-stu-id="d2175-125">If you create the set expression by explicitly naming the members in the set, enclose the list of members in a pair of braces ({}).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2175-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d2175-126">See Also</span></span>  
 [<span data-ttu-id="d2175-127">Berechnungen in mehrdimensionalen Modellen</span><span class="sxs-lookup"><span data-stu-id="d2175-127">Calculations in Multidimensional Models</span></span>](calculations-in-multidimensional-models.md)  
  
  
