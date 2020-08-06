---
title: Transformations-Editor für Skripterstellung (Seite "Eingaben und Ausgaben") | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.scriptcomponent.columnproperties.f1
helpviewer_keywords:
- Script Transformation Editor
ms.assetid: 9659d2d2-5d73-4470-9768-e07b77142fc9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 16adf74a1cd8f0c778bc18eaff84437b8fc13603
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695821"
---
# <a name="script-transformation-editor-inputs-and-outputs-page"></a><span data-ttu-id="2d5c4-102">Transformations-Editor für Skripterstellung (Seiten Eingaben und Ausgaben)</span><span class="sxs-lookup"><span data-stu-id="2d5c4-102">Script Transformation Editor (Inputs and Outputs Page)</span></span>
  <span data-ttu-id="2d5c4-103">Auf der Seite **Eingaben und Ausgaben** des Dialogfelds **Transformations-Editor für Skripterstellung** können Sie Ein- und Ausgaben für die Skripterstellung hinzufügen, entfernen oder konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="2d5c4-103">Use the **Inputs and Outputs** page of the **Script Transformation Editor** dialog box to add, remove, and configure inputs and outputs for the Script Transformation.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2d5c4-104">Für Quellkomponenten sind keine Eingaben, sondern nur Ausgaben, und für Zielkomponenten keine Ausgaben, sondern nur Eingaben vorhanden.</span><span class="sxs-lookup"><span data-stu-id="2d5c4-104">Source components have outputs and no inputs, while destination components have inputs but no outputs.</span></span> <span data-ttu-id="2d5c4-105">Transformationen verfügen über Ein- und Ausgaben.</span><span class="sxs-lookup"><span data-stu-id="2d5c4-105">Transformations have both inputs and outputs.</span></span>  
  
 <span data-ttu-id="2d5c4-106">Weitere Informationen zur Skriptkomponente finden Sie unter [Script Component](data-flow/transformations/script-component.md) und [Configuring the Script Component in the Script Component Editor](extending-packages-scripting/data-flow-script-component/configuring-the-script-component-in-the-script-component-editor.md).</span><span class="sxs-lookup"><span data-stu-id="2d5c4-106">To learn more about the Script component, see [Script Component](data-flow/transformations/script-component.md) and [Configuring the Script Component in the Script Component Editor](extending-packages-scripting/data-flow-script-component/configuring-the-script-component-in-the-script-component-editor.md).</span></span> <span data-ttu-id="2d5c4-107">Weitere Informationen zur Programmierung der Skriptkomponente finden Sie unter [Erweitern des Datenflusses mit der Skriptkomponente](extending-packages-scripting/data-flow-script-component/extending-the-data-flow-with-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="2d5c4-107">To learn about programming the Script component, see [Extending the Data Flow with the Script Component](extending-packages-scripting/data-flow-script-component/extending-the-data-flow-with-the-script-component.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="2d5c4-108">Tastatur</span><span class="sxs-lookup"><span data-stu-id="2d5c4-108">Options</span></span>  
 <span data-ttu-id="2d5c4-109">**Inputs and outputs**</span><span class="sxs-lookup"><span data-stu-id="2d5c4-109">**Inputs and outputs**</span></span>  
 <span data-ttu-id="2d5c4-110">Wählen Sie auf der linken Seite eine Eingabe oder Ausgabe, um die entsprechenden Eigenschaften in der Tabelle auf der rechten Seite anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2d5c4-110">Select an input or output on the left to view its properties in the table on the right.</span></span> <span data-ttu-id="2d5c4-111">Welche Eigenschaften bearbeitet werden können, ist von der getroffenen Auswahl abhängig.</span><span class="sxs-lookup"><span data-stu-id="2d5c4-111">Properties available for editing vary according to the selection.</span></span> <span data-ttu-id="2d5c4-112">Viele dieser Eigenschaften sind schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="2d5c4-112">Many of the properties displayed are read-only.</span></span> <span data-ttu-id="2d5c4-113">Weitere Informationen zu den einzelnen Eigenschaften finden Sie unter den folgenden Themen.</span><span class="sxs-lookup"><span data-stu-id="2d5c4-113">For more information on the individual properties, see the following topics.</span></span>  
  
 [<span data-ttu-id="2d5c4-114">Common Properties</span><span class="sxs-lookup"><span data-stu-id="2d5c4-114">Common Properties</span></span>](../../2014/integration-services/common-properties.md)  
  
 [<span data-ttu-id="2d5c4-115">Benutzerdefinierte Eigenschaften von Transformationen</span><span class="sxs-lookup"><span data-stu-id="2d5c4-115">Transformation Custom Properties</span></span>](data-flow/transformations/transformation-custom-properties.md)  
  
 <span data-ttu-id="2d5c4-116">**Ausgabe hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="2d5c4-116">**Add Output**</span></span>  
 <span data-ttu-id="2d5c4-117">Fügen Sie der Liste eine weitere Ausgabe hinzu.</span><span class="sxs-lookup"><span data-stu-id="2d5c4-117">Add an additional output to the list.</span></span>  
  
 <span data-ttu-id="2d5c4-118">**Spalte hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="2d5c4-118">**Add Column**</span></span>  
 <span data-ttu-id="2d5c4-119">Wählen Sie einen Ordner aus, in den die neue Ausgabespalte platziert werden soll, und fügen Sie anschließend die Spalte hinzu, indem Sie auf **Spalte hinzufügen**klicken.</span><span class="sxs-lookup"><span data-stu-id="2d5c4-119">Select a folder in which to place the new output column, and then add the column by clicking **Add Column**.</span></span>  
  
 <span data-ttu-id="2d5c4-120">**Ausgabe entfernen**</span><span class="sxs-lookup"><span data-stu-id="2d5c4-120">**Remove Output**</span></span>  
 <span data-ttu-id="2d5c4-121">Wählen Sie eine Ausgabe aus, und entfernen Sie sie dann, indem Sie auf **Ausgabe entfernen**klicken.</span><span class="sxs-lookup"><span data-stu-id="2d5c4-121">Select an output, and then remove it by clicking **Remove Output**.</span></span>  
  
 <span data-ttu-id="2d5c4-122">**Spalte entfernen**</span><span class="sxs-lookup"><span data-stu-id="2d5c4-122">**Remove Column**</span></span>  
 <span data-ttu-id="2d5c4-123">Wählen Sie eine Spalte aus, und entfernen Sie sie dann, indem Sie auf **Spalte entfernen**klicken.</span><span class="sxs-lookup"><span data-stu-id="2d5c4-123">Select a column, and then remove it by clicking **Remove Column**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d5c4-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2d5c4-124">See Also</span></span>  
 <span data-ttu-id="2d5c4-125">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="2d5c4-125">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="2d5c4-126">[Skript Komponententyp auswählen](../../2014/integration-services/select-script-component-type.md) </span><span class="sxs-lookup"><span data-stu-id="2d5c4-126">[Select Script Component Type](../../2014/integration-services/select-script-component-type.md) </span></span>  
 <span data-ttu-id="2d5c4-127">[Transformations-Editor für Skripterstellung &#40;Seite Eingabe Spalten&#41;](../../2014/integration-services/script-transformation-editor-input-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="2d5c4-127">[Script Transformation Editor &#40;Input Columns Page&#41;](../../2014/integration-services/script-transformation-editor-input-columns-page.md) </span></span>  
 <span data-ttu-id="2d5c4-128">[Transformations-Editor für Skripterstellung &#40;Skript Seite&#41;](../../2014/integration-services/script-transformation-editor-script-page.md) </span><span class="sxs-lookup"><span data-stu-id="2d5c4-128">[Script Transformation Editor &#40;Script Page&#41;](../../2014/integration-services/script-transformation-editor-script-page.md) </span></span>  
 <span data-ttu-id="2d5c4-129">[Skript Transformations-Editor &#40;Seite "Verbindungs-Manager"&#41;](../../2014/integration-services/script-transformation-editor-connection-managers-page.md) </span><span class="sxs-lookup"><span data-stu-id="2d5c4-129">[Script Transformation Editor &#40;Connection Managers Page&#41;](../../2014/integration-services/script-transformation-editor-connection-managers-page.md) </span></span>  
 [<span data-ttu-id="2d5c4-130">Zusätzliche Skriptkomponentenbeispiele</span><span class="sxs-lookup"><span data-stu-id="2d5c4-130">Additional Script Component Examples</span></span>](extending-packages-scripting-data-flow-script-component-examples/additional-script-component-examples.md)  
  
  
