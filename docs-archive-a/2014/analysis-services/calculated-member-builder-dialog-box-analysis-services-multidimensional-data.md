---
title: Generator für berechnete Elemente (Dialog Feld, Analysis Services Mehrdimensionale Daten) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.calculatedmemberbuilderdialog.f1
ms.assetid: 73b89a9f-f403-4ab8-99f7-e3ceb870c260
author: minewiskan
ms.author: owend
ms.openlocfilehash: 240e2f2471bf77c403119fd51278a975badc8358
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610295"
---
# <a name="calculated-member-builder-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="54d25-102">Dialogfeld 'Generator für berechnete Elemente' (Analysis Services – Mehrdimensionale Daten)</span><span class="sxs-lookup"><span data-stu-id="54d25-102">Calculated Member Builder Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="54d25-103">Verwenden Sie das Dialogfeld **Generator für berechnete Elemente** in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] , um ein berechnetes Element zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="54d25-103">Use the **Calculated Member Builder** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to build a calculated member.</span></span>  
  
## <a name="options"></a><span data-ttu-id="54d25-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="54d25-104">Options</span></span>  
  
|<span data-ttu-id="54d25-105">Begriff</span><span class="sxs-lookup"><span data-stu-id="54d25-105">Term</span></span>|<span data-ttu-id="54d25-106">Definition</span><span class="sxs-lookup"><span data-stu-id="54d25-106">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="54d25-107">**Name**</span><span class="sxs-lookup"><span data-stu-id="54d25-107">**Name**</span></span>|<span data-ttu-id="54d25-108">Geben Sie den Namen des berechneten Elements ein.</span><span class="sxs-lookup"><span data-stu-id="54d25-108">Type the name of the calculated member.</span></span>|  
|<span data-ttu-id="54d25-109">**Übergeordnete Hierarchie**</span><span class="sxs-lookup"><span data-stu-id="54d25-109">**Parent Hierarchy**</span></span>|<span data-ttu-id="54d25-110">Wählen Sie die übergeordnete Hierarchie aus, in der das berechnete Element erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="54d25-110">Select the hierarchy in which to create the calculated member.</span></span>|  
|<span data-ttu-id="54d25-111">**Übergeordnetes Element**</span><span class="sxs-lookup"><span data-stu-id="54d25-111">**Parent Member**</span></span>|<span data-ttu-id="54d25-112">Diese Option ist aktiviert, wenn Sie eine übergeordnete Hierarchie (außer der `Measures`-Dimension) mit mehreren Ebenen auswählen.</span><span class="sxs-lookup"><span data-stu-id="54d25-112">This option is enabled if you select a parent hierarchy (other than the `Measures` dimension) that has more than one level.</span></span> <span data-ttu-id="54d25-113">Klicken Sie auf die Schaltfläche (**..**.), um ein übergeordnetes Element auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="54d25-113">Click the ellipsis (**...**) button to select a parent member.</span></span> <span data-ttu-id="54d25-114">Das übergeordnete Element bestimmt den Speicherort des berechneten Elements in der Dimensionsstruktur.</span><span class="sxs-lookup"><span data-stu-id="54d25-114">The parent member determines the location of the calculated member in the dimension structure.</span></span>|  
|<span data-ttu-id="54d25-115">**Ausdruck**</span><span class="sxs-lookup"><span data-stu-id="54d25-115">**Expression**</span></span>|<span data-ttu-id="54d25-116">Geben Sie den MDX-Ausdruck ein, der verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="54d25-116">Type the MDX expression that will be used.</span></span>|  
|<span data-ttu-id="54d25-117">**Überprüfung**</span><span class="sxs-lookup"><span data-stu-id="54d25-117">**Check**</span></span>|<span data-ttu-id="54d25-118">Klicken Sie auf **Überprüfen** , um den in **Ausdruck**definierten MDX-Ausdruck zu testen.</span><span class="sxs-lookup"><span data-stu-id="54d25-118">Click **Check** to test the MDX expression defined in **Expression**.</span></span>|  
|<span data-ttu-id="54d25-119">**Metadaten**</span><span class="sxs-lookup"><span data-stu-id="54d25-119">**Metadata**</span></span>|<span data-ttu-id="54d25-120">Zeigt die Metadaten für das aktuelle [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Objekt an, das in den in **Ausdruck**definierten MDX-Ausdruck eingeschlossen werden kann.</span><span class="sxs-lookup"><span data-stu-id="54d25-120">Displays metadata for the current [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object that can be included in the MDX expression defined in **Expression**.</span></span><br /><br /> <span data-ttu-id="54d25-121">Sie können die MDX-Syntax für das ausgewählte Element kopieren, indem Sie mit der rechten Maustaste auf das Element klicken und die Option **Kopieren**auswählen oder indem Sie das ausgewählte Element auf **Ausdruck**ziehen.</span><span class="sxs-lookup"><span data-stu-id="54d25-121">You can copy the MDX syntax for the selected item by right-clicking the item and selecting **Copy**, or by dragging the selected item to **Expression**.</span></span>|  
|<span data-ttu-id="54d25-122">**Funktionen**</span><span class="sxs-lookup"><span data-stu-id="54d25-122">**Functions**</span></span>|<span data-ttu-id="54d25-123">Zeigt die für die aktuelle [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Instanz verfügbaren MDX-Funktionen an.</span><span class="sxs-lookup"><span data-stu-id="54d25-123">Displays the available MDX functions for the current [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance.</span></span> <span data-ttu-id="54d25-124">Die aufgelisteten Elemente werden aus dem MDSCHEMA_FUNCTIONS-Schemarowset abgerufen.</span><span class="sxs-lookup"><span data-stu-id="54d25-124">The items listed are retrieved from the MDSCHEMA_FUNCTIONS schema rowset.</span></span><br /><br /> <span data-ttu-id="54d25-125">Sie können die MDX-Syntax für das ausgewählte Element kopieren, indem Sie mit der rechten Maustaste auf das Element klicken und die Option **Kopieren**auswählen oder indem Sie das ausgewählte Element auf **Ausdruck**ziehen.</span><span class="sxs-lookup"><span data-stu-id="54d25-125">You can copy the MDX syntax for the selected item by right-clicking the item and selecting **Copy**, or by dragging the selected item to **Expression**.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="54d25-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="54d25-126">See Also</span></span>  
 [<span data-ttu-id="54d25-127">Multidimensional Expressions &#40;MDX&#41; – Referenz</span><span class="sxs-lookup"><span data-stu-id="54d25-127">Multidimensional Expressions &#40;MDX&#41; Reference</span></span>](/sql/mdx/multidimensional-expressions-mdx-reference)  
  
  
