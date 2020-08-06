---
title: Dialog Feld ' Sichtbarkeit der Zeile ' (Berichts-Generator) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10126"
ms.assetid: 117fb20c-2fda-437e-bcc5-9010d6d4b53b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 748cf1612f04e02a90a5d8579b56d3856dea0388
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615279"
---
# <a name="row-visibility-dialog-box-report-builder"></a><span data-ttu-id="8d0d7-102">Zeilensichtbarkeit (Dialogfeld) (Berichts-Generator)</span><span class="sxs-lookup"><span data-stu-id="8d0d7-102">Row Visibility Dialog Box (Report Builder)</span></span>
  <span data-ttu-id="8d0d7-103">Mit dem Dialogfeld **Sichtbarkeit anzeigen** können Sie die ausgewählte Zeile beim ersten Ausführen des Berichts anzeigen oder ausblenden oder die Sichtbarkeit der Zeile mit einem anderen Berichtselement aktivieren bzw. deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="8d0d7-103">Use the **Row Visibility** dialog box to show or hide the selected row when the report is first run or to use another report item to toggle the visibility of the row.</span></span>  
  
## <a name="options"></a><span data-ttu-id="8d0d7-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="8d0d7-104">Options</span></span>  
 <span data-ttu-id="8d0d7-105">**Bei erstmaliger Ausführung des Berichts**</span><span class="sxs-lookup"><span data-stu-id="8d0d7-105">**When the report is initially run**</span></span>  
 <span data-ttu-id="8d0d7-106">Wählen Sie eine Option aus, um die ursprüngliche Anzeige der Zeile im Bericht anzugeben.</span><span class="sxs-lookup"><span data-stu-id="8d0d7-106">Select an option to indicate how the row is initially displayed in the report.</span></span>  
  
 <span data-ttu-id="8d0d7-107">**Anzeigen**</span><span class="sxs-lookup"><span data-stu-id="8d0d7-107">**Show**</span></span>  
 <span data-ttu-id="8d0d7-108">Wählen Sie diese Option aus, um die Zeile anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8d0d7-108">Select this option to show the row.</span></span>  
  
 <span data-ttu-id="8d0d7-109">**Hide**</span><span class="sxs-lookup"><span data-stu-id="8d0d7-109">**Hide**</span></span>  
 <span data-ttu-id="8d0d7-110">Wählen Sie diese Option aus, um die Zeile auszublenden.</span><span class="sxs-lookup"><span data-stu-id="8d0d7-110">Select this option to hide the row.</span></span>  
  
 <span data-ttu-id="8d0d7-111">**Anzeigen oder Ausblenden auf Grundlage eines Ausdrucks**</span><span class="sxs-lookup"><span data-stu-id="8d0d7-111">**Show or hide based on an expression**</span></span>  
 <span data-ttu-id="8d0d7-112">Wählen Sie diese Option aus, um die ursprüngliche Sichtbarkeit mithilfe eines Ausdrucks zu variieren.</span><span class="sxs-lookup"><span data-stu-id="8d0d7-112">Select this option to vary the initial visibility using an expression.</span></span>  
  
 <span data-ttu-id="8d0d7-113">Geben Sie einen Ausdruck ein, der das Element ausblendet, wenn der `Boolean` Wert `True` ausgewertet wird, oder der das Element anzeigt, wenn `False` ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="8d0d7-113">Type an expression that evaluates to a `Boolean` value of `True` to hide the item and `False` to show the item.</span></span> <span data-ttu-id="8d0d7-114">Klicken Sie auf die **Ausdrucks** Schaltfläche (*FX*), um den Ausdruck zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="8d0d7-114">Click the **Expression** (*fx*) button to edit the expression.</span></span>  
  
 <span data-ttu-id="8d0d7-115">**Sichtbarkeit kann von diesem Berichtselement ein-/ausgeschaltet werden**</span><span class="sxs-lookup"><span data-stu-id="8d0d7-115">**Display can be toggled by this report item**</span></span>  
 <span data-ttu-id="8d0d7-116">Wählen Sie diese Option aus, um ein Umschaltbild anzuzeigen, mit dem der Benutzer diese Zeile in einem HTML Berichts-Viewer anzeigen oder ausblenden kann.</span><span class="sxs-lookup"><span data-stu-id="8d0d7-116">Choose this option to display a toggle image that enables the user to show or hide this row in an HTML report viewer.</span></span>  
  
 <span data-ttu-id="8d0d7-117">Sie müssen den Namen eines Textfelds im Bericht eingeben oder wählen, in dem ein Umschaltbild angezeigt werden soll. Beispiel: Textbox1</span><span class="sxs-lookup"><span data-stu-id="8d0d7-117">Type or select the name of a text box in the report in which to display a toggle image; for example, Textbox1.</span></span> <span data-ttu-id="8d0d7-118">Das gewählte Textfeld muss im aktuellen oder enthaltenden Bereich für dieses Berichtselement enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="8d0d7-118">The text box that you choose must be in the current or containing scope for this report item.</span></span> <span data-ttu-id="8d0d7-119">Beispiel: Wenn Sie die Sichtbarkeit von Zeilen umschalten möchten, die mit einer untergeordneten Gruppe verknüpft sind, wählen Sie ein Textfeld in einer Zeile, die mit der übergeordneten Gruppe verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="8d0d7-119">For example, to toggle visibility of rows associated with a child group, select a text box in a row associated with the parent group.</span></span> <span data-ttu-id="8d0d7-120">Wählen Sie ein Textfeld, das in demselben enthaltenden Bereich enthalten ist wie das Diagramm, um die Sichtbarkeit eines Diagramms umzuschalten. Beispiel: der Berichtshauptteil oder ein Rechteck.</span><span class="sxs-lookup"><span data-stu-id="8d0d7-120">To toggle visibility of a chart, select a text box that is in the same containing scope as the chart; for example, the report body or a rectangle.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d0d7-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8d0d7-121">See Also</span></span>  
 <span data-ttu-id="8d0d7-122">[Beispiele für Ausdrücke &#40;Berichts-Generator und SSRS&#41;](report-design/expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="8d0d7-122">[Expression Examples &#40;Report Builder and SSRS&#41;](report-design/expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="8d0d7-123">[Hinzufügen einer Erweiterungs-oder Reduzier Aktion zu einem Element &#40;Berichts-Generator und SSRS&#41;](report-design/add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="8d0d7-123">[Add an Expand or Collapse Action to an Item &#40;Report Builder and SSRS&#41;](report-design/add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="8d0d7-124">[Images &#40;Berichts-Generator und SSRS&#41;](report-design/images-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="8d0d7-124">[Images &#40;Report Builder and SSRS&#41;](report-design/images-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="8d0d7-125">[Berichts-Generator Hilfe zu Dialog Feldern, Bereichen und Assistenten](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span><span class="sxs-lookup"><span data-stu-id="8d0d7-125">[Report Builder Help for Dialog Boxes, Panes, and Wizards](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span></span>  
 [<span data-ttu-id="8d0d7-126">Bildeigenschaften (Dialogfeld), Allgemein (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="8d0d7-126">Image Properties Dialog Box, General &#40;Report Builder and SSRS&#41;</span></span>](../../2014/reporting-services/image-properties-dialog-box-general-report-builder-and-ssrs.md)  
  
  
