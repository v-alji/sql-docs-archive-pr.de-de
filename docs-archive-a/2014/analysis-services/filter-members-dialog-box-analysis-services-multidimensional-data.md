---
title: Dialog Feld ' Elemente filtern ' (Analysis Services Mehrdimensionale Daten) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensiondesigner.filtermembers.f1
helpviewer_keywords:
- Filter Members dialog box
ms.assetid: 52c6da1d-9fb5-4dbc-bffa-248d11cd337c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 66980b1afe9d4eed353ae18c37ed1fdd052e62b9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608059"
---
# <a name="filter-members-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="6d54a-102">Dialogfeld 'Elemente filtern' (Analysis Services – Mehrdimensionale Daten)</span><span class="sxs-lookup"><span data-stu-id="6d54a-102">Filter Members Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="6d54a-103">Mithilfe des Dialogfelds **Elemente filtern** in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] können Sie Dimensionselemente nach Elementbeschriftung, Elementnamen, eindeutigen Elementnamen, Schlüsselspaltenwert oder Wertspaltenwert für die aktuelle Ebene filtern, während Sie eine Dimension auf der Registerkarte **Browser** von **Dimensions-Designer**durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="6d54a-103">Use the **Filter Members** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to filter dimension members by member caption, member name, member unique name, key column value, or value column value for the current level while browsing a dimension in the **Browser** tab of **Dimension Designer**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="6d54a-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="6d54a-104">Options</span></span>  
  
|<span data-ttu-id="6d54a-105">Begriff</span><span class="sxs-lookup"><span data-stu-id="6d54a-105">Term</span></span>|<span data-ttu-id="6d54a-106">Definition</span><span class="sxs-lookup"><span data-stu-id="6d54a-106">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="6d54a-107">**Filterausdruck**</span><span class="sxs-lookup"><span data-stu-id="6d54a-107">**Filter expression**</span></span>|<span data-ttu-id="6d54a-108">Zeigt ein Raster von Eigenschaften, Operatoren und Werten an, die zum Erstellen eines Filterausdrucks verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6d54a-108">Displays a grid of properties, operators, and values used to construct a filter expression.</span></span> <span data-ttu-id="6d54a-109">Nachdem eine Zeile hinzugefügt wurde, kann sie nicht mehr entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="6d54a-109">Note that after a row is added, it cannot be removed.</span></span> <span data-ttu-id="6d54a-110">Sie müssen das Dialogfeld schließen und erneut öffnen, um einen neuen Filterausdruck anzugeben.</span><span class="sxs-lookup"><span data-stu-id="6d54a-110">You must close and reopen the dialog box to specify a new filter expression.</span></span> <span data-ttu-id="6d54a-111">Das Raster enthält die folgenden Spalten:</span><span class="sxs-lookup"><span data-stu-id="6d54a-111">The grid contains the following columns:</span></span><br /><br /> <span data-ttu-id="6d54a-112">**Property**: Wählen Sie die-Eigenschaft des Members aus, der für den Filter Ausdruck verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="6d54a-112">**Property**: Select the property of the member to use for the filter expression.</span></span><br /><br /> <span data-ttu-id="6d54a-113">**Operator**: Wählen Sie den Operator aus, der für den Filter Ausdruck verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="6d54a-113">**Operator**: Select the operator to use for the filter expression.</span></span><br /><br /> <span data-ttu-id="6d54a-114">**Wert**: Geben Sie den Wert der in **Eigenschaft** ausgewählten Eigenschaft ein, die mithilfe des unter **Operator**angegebenen Operators ausgewertet werden soll.</span><span class="sxs-lookup"><span data-stu-id="6d54a-114">**Value**: Type the value of the property selected in **Property** to evaluate using the operator specified in **Operator**.</span></span>|  
|<span data-ttu-id="6d54a-115">**Testbereich**</span><span class="sxs-lookup"><span data-stu-id="6d54a-115">**Test pane**</span></span>|<span data-ttu-id="6d54a-116">Wenn Sie auf **Testen** klicken, werden in diesem Bereich die durch den Filterausdruck zurückgegebenen Elemente angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6d54a-116">When **Test** is clicked, this pane displays the members returned by the filter expression.</span></span> <span data-ttu-id="6d54a-117">Wenn für die unter **Filterausdruck**angegebenen Kriterien keine Elemente zurückgegeben werden, wird eine Warnung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6d54a-117">If no members are returned using the criteria specified in **Filter expression**, a warning is displayed.</span></span>|  
|<span data-ttu-id="6d54a-118">**Test**</span><span class="sxs-lookup"><span data-stu-id="6d54a-118">**Test**</span></span>|<span data-ttu-id="6d54a-119">Klicken Sie auf diese Option, um die unter **Filterausdruck**angegebenen Kriterien zu testen.</span><span class="sxs-lookup"><span data-stu-id="6d54a-119">Click to test the criteria specified in **Filter expression**.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6d54a-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6d54a-120">See Also</span></span>  
 <span data-ttu-id="6d54a-121">[Analysis Services Designer und Dialog Felder &#40;Mehrdimensionale Daten&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="6d54a-121">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="6d54a-122">Browser &#40;Dimensions-Designer&#41; &#40;Analysis Services Mehrdimensionale Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="6d54a-122">Browser &#40;Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](browser-dimension-designer-analysis-services-multidimensional-data.md)  
  
  
