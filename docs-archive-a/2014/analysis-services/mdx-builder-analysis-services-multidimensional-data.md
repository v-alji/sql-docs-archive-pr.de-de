---
title: MDX-Generator (Analysis Services Mehrdimensionale Daten) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.mdxbuilderdialof.f1
helpviewer_keywords:
- MDX Builder dialog box
ms.assetid: fecbf093-65ea-4e1b-b637-f04876f1cb0f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 391f4abe953184470be60cca41d53ee20e965423
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618942"
---
# <a name="mdx-builder-analysis-services---multidimensional-data"></a><span data-ttu-id="ff0ab-102">MDX-Generator (Analysis Services – Mehrdimensionale Daten)</span><span class="sxs-lookup"><span data-stu-id="ff0ab-102">MDX Builder (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="ff0ab-103">Im Dialogfeld **MDX-Generator** in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] oder [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] können Sie einen MDX-Ausdruck (Multidimensional Expressions) erstellen.</span><span class="sxs-lookup"><span data-stu-id="ff0ab-103">Use the **MDX Builder** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] or [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to build a Multidimensional Expressions (MDX) expression.</span></span> <span data-ttu-id="ff0ab-104">Um das Dialogfeld **MDX** -Generator anzuzeigen, klicken Sie auf die Schaltfläche mit den Auslassungs Punkten **Bearbeiten** (**...**), um die Option **Lesen des Cubeinhalts zulassen** , das Lesen der Option zum Lesen **von Zellen Inhalt, abhängig von der Zellen Sicherheit** oder die Option **Lesen und Schreiben des Cubeinhalts** zulassen auf der Seite **Zellen Daten** des **Rollen-Designers**zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="ff0ab-104">You can display the **MDX Builder** dialog box by clicking the **Edit MDX** ellipsis button (**...**) for the **Allow reading of cube content** option, the **Allow reading of cell content contingent on cell security** option, or the **Allow reading and writing of cube content** option on the **Cell Data** page of **Role Designer**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ff0ab-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="ff0ab-105">Options</span></span>  
  
|<span data-ttu-id="ff0ab-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="ff0ab-106">Term</span></span>|<span data-ttu-id="ff0ab-107">Definition</span><span class="sxs-lookup"><span data-stu-id="ff0ab-107">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="ff0ab-108">**Ausdruck**</span><span class="sxs-lookup"><span data-stu-id="ff0ab-108">**Expression**</span></span>|<span data-ttu-id="ff0ab-109">Geben Sie den MDX-Ausdruck ein, der verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ff0ab-109">Type the MDX expression to be used.</span></span>|  
|<span data-ttu-id="ff0ab-110">**Überprüfung**</span><span class="sxs-lookup"><span data-stu-id="ff0ab-110">**Check**</span></span>|<span data-ttu-id="ff0ab-111">Klicken Sie auf **Überprüfen** , um den in **Ausdruck**definierten MDX-Ausdruck zu testen.</span><span class="sxs-lookup"><span data-stu-id="ff0ab-111">Click **Check** to test the MDX expression defined in **Expression**.</span></span>|  
|<span data-ttu-id="ff0ab-112">**Metadaten**</span><span class="sxs-lookup"><span data-stu-id="ff0ab-112">**Metadata**</span></span>|<span data-ttu-id="ff0ab-113">Zeigt die Metadaten für das aktuelle [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Objekt an, das in den in **Ausdruck**definierten MDX-Ausdruck eingeschlossen werden kann.</span><span class="sxs-lookup"><span data-stu-id="ff0ab-113">Displays metadata for the current [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object that can be included in the MDX expression defined in **Expression**.</span></span><br /><br /> <span data-ttu-id="ff0ab-114">Sie können die MDX-Syntax für das ausgewählte Element kopieren, indem Sie mit der rechten Maustaste auf das Element klicken und im Kontextmenü die Option **Kopieren** auswählen, oder indem Sie das ausgewählte Element auf **Ausdruck**ziehen.</span><span class="sxs-lookup"><span data-stu-id="ff0ab-114">You can copy the MDX syntax for the selected item by right-clicking the item and selecting **Copy** from the context menu, or by dragging the selected item to **Expression**.</span></span>|  
|<span data-ttu-id="ff0ab-115">**Funktionen**</span><span class="sxs-lookup"><span data-stu-id="ff0ab-115">**Functions**</span></span>|<span data-ttu-id="ff0ab-116">Zeigt die für die aktuelle [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Instanz verfügbaren MDX-Funktionen an.</span><span class="sxs-lookup"><span data-stu-id="ff0ab-116">Displays available MDX functions for the current [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance.</span></span> <span data-ttu-id="ff0ab-117">Die aufgelisteten Elemente werden aus dem MDSCHEMA_FUNCTIONS-Schemarowset abgerufen.</span><span class="sxs-lookup"><span data-stu-id="ff0ab-117">The items listed are retrieved from the MDSCHEMA_FUNCTIONS schema rowset.</span></span><br /><br /> <span data-ttu-id="ff0ab-118">Sie können die MDX-Syntax für das ausgewählte Element kopieren, indem Sie mit der rechten Maustaste auf das Element klicken und im Kontextmenü die Option **Kopieren** auswählen, oder indem Sie das ausgewählte Element auf **Ausdruck**ziehen.</span><span class="sxs-lookup"><span data-stu-id="ff0ab-118">You can copy the MDX syntax for the selected item by right-clicking the item and selecting **Copy** from the context menu, or by dragging the selected item to **Expression**.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ff0ab-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ff0ab-119">See Also</span></span>  
 <span data-ttu-id="ff0ab-120">[Analysis Services Designer und Dialog Felder &#40;Mehrdimensionale Daten&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="ff0ab-120">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 <span data-ttu-id="ff0ab-121">[Zellen Daten &#40;Rollen-Designer&#41; &#40;Analysis Services Mehrdimensionale Daten&#41;](https://msdn.microsoft.com/library/ms177279(v=sql.120).aspx)</span><span class="sxs-lookup"><span data-stu-id="ff0ab-121">[Cell Data &#40;Role Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](https://msdn.microsoft.com/library/ms177279(v=sql.120).aspx)</span></span>  
  
  
