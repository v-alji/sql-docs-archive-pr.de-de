---
title: Dialog Feld "Spalten Sichtbarkeit" (Berichts-Generator) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10127"
ms.assetid: 0c030cab-6087-45a5-99f0-c7bd693f20a1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4c775734a4dbba2120a2af86e35a3872f5fff718
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697582"
---
# <a name="column-visibility-dialog-box-report-builder"></a><span data-ttu-id="91bc3-102">Spaltensichtbarkeit (Dialogfeld) (Berichts-Generator)</span><span class="sxs-lookup"><span data-stu-id="91bc3-102">Column Visibility Dialog Box (Report Builder)</span></span>
  <span data-ttu-id="91bc3-103">Mithilfe des Dialogfelds **Spaltensichtbarkeit** können Sie die ausgewählte Spalte beim ersten Ausführen des Berichts anzeigen oder ausblenden oder die Sichtbarkeit der Spalte mit einem anderen Berichtselement aktivieren bzw. deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="91bc3-103">Use the **Column Visibility** dialog box to show or hide the selected column when the report is first run or to use another report item to toggle the visibility of the column.</span></span>  
  
## <a name="options"></a><span data-ttu-id="91bc3-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="91bc3-104">Options</span></span>  
 <span data-ttu-id="91bc3-105">**Bei erstmaliger Ausführung des Berichts**</span><span class="sxs-lookup"><span data-stu-id="91bc3-105">**When the report is initially run**</span></span>  
 <span data-ttu-id="91bc3-106">Wählen Sie eine Option aus, um die ursprüngliche Anzeige des Berichtselements im Bericht anzugeben.</span><span class="sxs-lookup"><span data-stu-id="91bc3-106">Select an option to indicate how the report item is initially displayed in the report.</span></span>  
  
 <span data-ttu-id="91bc3-107">**Anzeigen**</span><span class="sxs-lookup"><span data-stu-id="91bc3-107">**Show**</span></span>  
 <span data-ttu-id="91bc3-108">Wählen Sie diese Option aus, um die Spalte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="91bc3-108">Choose this option to show the column.</span></span>  
  
 <span data-ttu-id="91bc3-109">**Hide**</span><span class="sxs-lookup"><span data-stu-id="91bc3-109">**Hide**</span></span>  
 <span data-ttu-id="91bc3-110">Wählen Sie diese Option aus, um die Spalte auszublenden.</span><span class="sxs-lookup"><span data-stu-id="91bc3-110">Choose this option to hide the Column.</span></span>  
  
 <span data-ttu-id="91bc3-111">**Anzeigen oder Ausblenden auf Grundlage eines Ausdrucks**</span><span class="sxs-lookup"><span data-stu-id="91bc3-111">**Show or hide based on an expression**</span></span>  
 <span data-ttu-id="91bc3-112">Wählen Sie diese Option aus, um die ursprüngliche Sichtbarkeit mithilfe eines Ausdrucks zu variieren.</span><span class="sxs-lookup"><span data-stu-id="91bc3-112">Choose this option to vary the initial visibility using an expression.</span></span>  
  
 <span data-ttu-id="91bc3-113">Geben Sie einen Ausdruck ein, der das Element ausblendet, wenn der `Boolean` Wert `True` ausgewertet wird, oder der das Element anzeigt, wenn `False` ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="91bc3-113">Type an expression that evaluates to a `Boolean` value of `True` to hide the item and `False` to show the item.</span></span> <span data-ttu-id="91bc3-114">Klicken Sie auf die Ausdrucks Schaltfläche (*FX*), um den Ausdruck zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="91bc3-114">Click the Expression (*fx*) button to edit the expression.</span></span>  
  
 <span data-ttu-id="91bc3-115">**Sichtbarkeit kann von diesem Berichtselement ein-/ausgeschaltet werden**</span><span class="sxs-lookup"><span data-stu-id="91bc3-115">**Display can be toggled by this report item**</span></span>  
 <span data-ttu-id="91bc3-116">Wählen Sie diese Option aus, um ein Umschaltbild anzuzeigen, mit dem der Benutzer diese Spalte in einem HTML Berichts-Viewer anzeigen oder ausblenden kann.</span><span class="sxs-lookup"><span data-stu-id="91bc3-116">Choose this option to display a toggle image that enables the user to show or hide this column in an HTML report viewer.</span></span>  
  
 <span data-ttu-id="91bc3-117">Sie müssen den Namen eines Textfelds im Bericht eingeben oder wählen, in dem ein Umschaltbild angezeigt werden soll. Beispiel: Textbox1</span><span class="sxs-lookup"><span data-stu-id="91bc3-117">Type or select the name of a text box in the report in which to display a toggle image; for example, Textbox1.</span></span> <span data-ttu-id="91bc3-118">Das gewählte Textfeld muss im aktuellen oder enthaltenden Bereich für dieses Berichtselement enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="91bc3-118">The text box that you choose must be in the current or containing scope for this report item.</span></span> <span data-ttu-id="91bc3-119">Beispiel: Wenn Sie die Sichtbarkeit von Zeilen umschalten möchten, die mit einer untergeordneten Gruppe verknüpft sind, wählen Sie ein Textfeld in einer Zeile, die mit der übergeordneten Gruppe verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="91bc3-119">For example, to toggle visibility of rows associated with a child group, select a text box in a row associated with the parent group.</span></span> <span data-ttu-id="91bc3-120">Wählen Sie ein Textfeld, das in demselben enthaltenden Bereich enthalten ist wie das Diagramm, um die Sichtbarkeit eines Diagramms umzuschalten. Beispiel: der Berichtshauptteil oder ein Rechteck.</span><span class="sxs-lookup"><span data-stu-id="91bc3-120">To toggle visibility of a chart, select a text box that is in the same containing scope as the chart; for example, the report body or a rectangle.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91bc3-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="91bc3-121">See Also</span></span>  
 <span data-ttu-id="91bc3-122">[Beispiele für Ausdrücke &#40;Berichts-Generator und SSRS&#41;](report-design/expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="91bc3-122">[Expression Examples &#40;Report Builder and SSRS&#41;](report-design/expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="91bc3-123">[Hinzufügen einer Erweiterungs-oder Reduzier Aktion zu einem Element &#40;Berichts-Generator und SSRS&#41;](report-design/add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="91bc3-123">[Add an Expand or Collapse Action to an Item &#40;Report Builder and SSRS&#41;](report-design/add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="91bc3-124">[Images &#40;Berichts-Generator und SSRS&#41;](report-design/images-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="91bc3-124">[Images &#40;Report Builder and SSRS&#41;](report-design/images-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="91bc3-125">[Berichts-Generator Hilfe zu Dialog Feldern, Bereichen und Assistenten](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span><span class="sxs-lookup"><span data-stu-id="91bc3-125">[Report Builder Help for Dialog Boxes, Panes, and Wizards](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span></span>  
 [<span data-ttu-id="91bc3-126">Bildeigenschaften (Dialogfeld), Allgemein (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="91bc3-126">Image Properties Dialog Box, General &#40;Report Builder and SSRS&#41;</span></span>](../../2014/reporting-services/image-properties-dialog-box-general-report-builder-and-ssrs.md)  
  
  
