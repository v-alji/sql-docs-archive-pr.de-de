---
title: Transformations-Editor für Skripterstellung (Seite Eingabe Spalten) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.scriptcomponent.inputcolumn.f1
helpviewer_keywords:
- Script Transformation Editor
ms.assetid: d6e4ce84-3335-48e6-82d3-1c359ed87f63
author: chugugrace
ms.author: chugu
ms.openlocfilehash: daffb52b62ad59ae4fe574d7fa27d4820b9cb5a2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695825"
---
# <a name="script-transformation-editor-input-columns-page"></a><span data-ttu-id="1c351-102">Transformations-Editor für Skripterstellung (Seite Eingabespalten)</span><span class="sxs-lookup"><span data-stu-id="1c351-102">Script Transformation Editor (Input Columns Page)</span></span>
  <span data-ttu-id="1c351-103">Legen Sie mithilfe der Seite **Eingabespalten** des Dialogfelds **Transformations-Editor für Skripterstellung** die Eigenschaften für Eingabespalten fest.</span><span class="sxs-lookup"><span data-stu-id="1c351-103">Use the **Input Columns** page of the **Script Transformation Editor** dialog box to set properties on input columns.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1c351-104">Für Quellkomponenten, die Ausgaben, aber keine Eingaben haben, wird die Seite **Eingabespalten** nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1c351-104">The **Input Columns** page is not displayed for Source components, which have outputs but no inputs.</span></span>  
  
 <span data-ttu-id="1c351-105">Weitere Informationen zur Skriptkomponente finden Sie unter [Script Component](data-flow/transformations/script-component.md) und [Configuring the Script Component in the Script Component Editor](extending-packages-scripting/data-flow-script-component/configuring-the-script-component-in-the-script-component-editor.md).</span><span class="sxs-lookup"><span data-stu-id="1c351-105">To learn more about the Script component, see [Script Component](data-flow/transformations/script-component.md) and [Configuring the Script Component in the Script Component Editor](extending-packages-scripting/data-flow-script-component/configuring-the-script-component-in-the-script-component-editor.md).</span></span> <span data-ttu-id="1c351-106">Weitere Informationen zur Programmierung der Skriptkomponente finden Sie unter [Erweitern des Datenflusses mit der Skriptkomponente](extending-packages-scripting/data-flow-script-component/extending-the-data-flow-with-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="1c351-106">To learn about programming the Script component, see [Extending the Data Flow with the Script Component](extending-packages-scripting/data-flow-script-component/extending-the-data-flow-with-the-script-component.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="1c351-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="1c351-107">Options</span></span>  
 <span data-ttu-id="1c351-108">**Eingabename**</span><span class="sxs-lookup"><span data-stu-id="1c351-108">**Input name**</span></span>  
 <span data-ttu-id="1c351-109">Wählen Sie eine Option aus der Liste der verfügbaren Eingaben aus.</span><span class="sxs-lookup"><span data-stu-id="1c351-109">Select from the list of available inputs.</span></span>  
  
 <span data-ttu-id="1c351-110">**Verfügbare Eingabespalten**</span><span class="sxs-lookup"><span data-stu-id="1c351-110">**Available Input Columns**</span></span>  
 <span data-ttu-id="1c351-111">Geben Sie mithilfe der Kontrollkästchen die Spalten an, die von der Skripttransformation verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1c351-111">Using the check boxes, specify the columns that the script transformation will use.</span></span>  
  
 <span data-ttu-id="1c351-112">**Eingabespalte**</span><span class="sxs-lookup"><span data-stu-id="1c351-112">**Input Column**</span></span>  
 <span data-ttu-id="1c351-113">Wählen Sie für jede Zeile eine Spalte aus der Liste der verfügbaren Eingabespalten aus.</span><span class="sxs-lookup"><span data-stu-id="1c351-113">Select from the list of available input columns for each row.</span></span> <span data-ttu-id="1c351-114">Ihre Auswahl wird entsprechend in der Auswahl der Kontrollkästchen in der Tabelle **Verfügbare Eingabespalten**deutlich.</span><span class="sxs-lookup"><span data-stu-id="1c351-114">Your selections are reflected in the check box selections in the **Available Input Columns**table.</span></span>  
  
 <span data-ttu-id="1c351-115">**Ausgabealias**</span><span class="sxs-lookup"><span data-stu-id="1c351-115">**Output Alias**</span></span>  
 <span data-ttu-id="1c351-116">Geben Sie einen Alias für jede Spalte ein.</span><span class="sxs-lookup"><span data-stu-id="1c351-116">Type an alias for each output column.</span></span> <span data-ttu-id="1c351-117">Standardmäßig wird der Name der Eingabespalte verwendet. Sie können jedoch auch einen beschreibenden Namen angeben, sofern dieser eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="1c351-117">The default is the name of the input column; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="1c351-118">**Verwendungstyp**</span><span class="sxs-lookup"><span data-stu-id="1c351-118">**Usage Type**</span></span>  
 <span data-ttu-id="1c351-119">Geben Sie an, ob die Skripttransformation jede Spalte als `ReadOnly` oder `ReadWrite` behandeln soll.</span><span class="sxs-lookup"><span data-stu-id="1c351-119">Specify whether the Script Transformation will treat each column as `ReadOnly` or `ReadWrite`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c351-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1c351-120">See Also</span></span>  
 <span data-ttu-id="1c351-121">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="1c351-121">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="1c351-122">[Skript Komponententyp auswählen](../../2014/integration-services/select-script-component-type.md) </span><span class="sxs-lookup"><span data-stu-id="1c351-122">[Select Script Component Type](../../2014/integration-services/select-script-component-type.md) </span></span>  
 <span data-ttu-id="1c351-123">[Transformations-Editor für Skripterstellung &#40;Seite "Eingaben und Ausgaben"&#41;](../../2014/integration-services/script-transformation-editor-inputs-and-outputs-page.md) </span><span class="sxs-lookup"><span data-stu-id="1c351-123">[Script Transformation Editor &#40;Inputs and Outputs Page&#41;](../../2014/integration-services/script-transformation-editor-inputs-and-outputs-page.md) </span></span>  
 <span data-ttu-id="1c351-124">[Transformations-Editor für Skripterstellung &#40;Skript Seite&#41;](../../2014/integration-services/script-transformation-editor-script-page.md) </span><span class="sxs-lookup"><span data-stu-id="1c351-124">[Script Transformation Editor &#40;Script Page&#41;](../../2014/integration-services/script-transformation-editor-script-page.md) </span></span>  
 <span data-ttu-id="1c351-125">[Skript Transformations-Editor &#40;Seite "Verbindungs-Manager"&#41;](../../2014/integration-services/script-transformation-editor-connection-managers-page.md) </span><span class="sxs-lookup"><span data-stu-id="1c351-125">[Script Transformation Editor &#40;Connection Managers Page&#41;](../../2014/integration-services/script-transformation-editor-connection-managers-page.md) </span></span>  
 [<span data-ttu-id="1c351-126">Zusätzliche Skriptkomponentenbeispiele</span><span class="sxs-lookup"><span data-stu-id="1c351-126">Additional Script Component Examples</span></span>](extending-packages-scripting-data-flow-script-component-examples/additional-script-component-examples.md)  
  
  
