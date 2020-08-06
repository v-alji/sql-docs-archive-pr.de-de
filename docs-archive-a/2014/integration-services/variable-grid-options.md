---
title: Variablen Raster Optionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.variableoptionswindow.f1
helpviewer_keywords:
- Choose Variable Columns dialog box
ms.assetid: 7cccc230-3b20-4074-804f-3448d9616a83
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b90e1a3c69e4eaf1f123603e0082ecb1eda4e893
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609939"
---
# <a name="variable-grid-options"></a><span data-ttu-id="76a94-102">Variable Rasteroptionen</span><span class="sxs-lookup"><span data-stu-id="76a94-102">Variable Grid Options</span></span>
  <span data-ttu-id="76a94-103">Im Dialogfeld **Variable Rasteroptionen** können Sie die Spalten auswählen, die im Fenster **Variablen** angezeigt werden, und die Filter auswählen, die auf die Liste der Variablen angewendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="76a94-103">Use the **Variable Grid Options** dialog box to select the columns that will display in the **Variables** window and to select the filters to apply to the list of variables.</span></span> <span data-ttu-id="76a94-104">Weitere Informationen über die Eigenschaften der zugehörigen Variablen finden Sie unter [Integration Services-Variablen &#40;SSIS&#41;](integration-services-ssis-variables.md).</span><span class="sxs-lookup"><span data-stu-id="76a94-104">For more information about the corresponding variable properties, see [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md).</span></span>  
  
## <a name="options-for-filter"></a><span data-ttu-id="76a94-105">Optionen für Filter</span><span class="sxs-lookup"><span data-stu-id="76a94-105">Options for Filter</span></span>  
 <span data-ttu-id="76a94-106">**Systemvariablen anzeigen**</span><span class="sxs-lookup"><span data-stu-id="76a94-106">**Show system variables**</span></span>  
 <span data-ttu-id="76a94-107">Wählen Sie diese Option aus, um Systemvariablen im Fenster **Variablen** aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="76a94-107">Select to list system variables in the **Variables** window.</span></span> <span data-ttu-id="76a94-108">Systemvariablen sind vordefiniert.</span><span class="sxs-lookup"><span data-stu-id="76a94-108">System variables are predefined.</span></span> <span data-ttu-id="76a94-109">Systemvariablen können nicht hinzugefügt oder gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="76a94-109">You cannot add or delete system variables.</span></span> <span data-ttu-id="76a94-110">Sie können die Eigenschafteneinstellung **RaiseChangedEvent** ändern.</span><span class="sxs-lookup"><span data-stu-id="76a94-110">You can modify the **RaiseChangedEvent** property setting.</span></span>  
  
 <span data-ttu-id="76a94-111">Diese Liste ist mit Farbcodes versehen.</span><span class="sxs-lookup"><span data-stu-id="76a94-111">This list is color coded.</span></span> <span data-ttu-id="76a94-112">Systemvariablen werden grau, benutzerdefinierte Variablen werden schwarz angezeigt.</span><span class="sxs-lookup"><span data-stu-id="76a94-112">System variables are gray, and user-defined variables are black.</span></span>  
  
 <span data-ttu-id="76a94-113">**Variablen aller Bereiche anzeigen**</span><span class="sxs-lookup"><span data-stu-id="76a94-113">**Show variables of all scopes**</span></span>  
 <span data-ttu-id="76a94-114">Wählen Sie diese Option aus, um Variablen innerhalb des Bereichs des Pakets und innerhalb des Bereichs von Containern, Tasks und Ereignishandlern im Paket anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="76a94-114">Select to show variables within the scope the package, and within the scope of containers, tasks, and event handlers in the package.</span></span> <span data-ttu-id="76a94-115">Deaktivieren Sie diese Option, um nur Variablen innerhalb des Bereichs des Pakets und innerhalb des Bereichs eines ausgewählten Containers, Tasks oder Ereignishandlers anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="76a94-115">Clear this option to show only variables within the scope of the package and within the scope of a selected container, task, or event handler.</span></span>  
  
 <span data-ttu-id="76a94-116">Weitere Informationen zu Variablenbereichen finden Sie unter [Integration Services-Variablen &#40;SSIS&#41;](integration-services-ssis-variables.md).</span><span class="sxs-lookup"><span data-stu-id="76a94-116">For more information about variable scope, see [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md).</span></span>  
  
## <a name="options-for-columns"></a><span data-ttu-id="76a94-117">Optionen für Spalten</span><span class="sxs-lookup"><span data-stu-id="76a94-117">Options for Columns</span></span>  
 <span data-ttu-id="76a94-118">Wählen Sie die Spalten aus, die im Fenster **Variablen** angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="76a94-118">Select the columns that you want to appear in the **Variables** window.</span></span>  
  
-   <span data-ttu-id="76a94-119">**Umfang**</span><span class="sxs-lookup"><span data-stu-id="76a94-119">**Scope**</span></span>  
  
-   <span data-ttu-id="76a94-120">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="76a94-120">**Data type**</span></span>  
  
-   <span data-ttu-id="76a94-121">**Wert**</span><span class="sxs-lookup"><span data-stu-id="76a94-121">**Value**</span></span>  
  
-   <span data-ttu-id="76a94-122">**Namespace**</span><span class="sxs-lookup"><span data-stu-id="76a94-122">**Namespace**</span></span>  
  
-   <span data-ttu-id="76a94-123">**Ereignis bei Änderung des Variablenwertes auslösen**</span><span class="sxs-lookup"><span data-stu-id="76a94-123">**Raise event when variable value changes**</span></span>  
  
-   <span data-ttu-id="76a94-124">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="76a94-124">**Description**</span></span>  
  
-   <span data-ttu-id="76a94-125">**Ausdruck**</span><span class="sxs-lookup"><span data-stu-id="76a94-125">**Expression**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76a94-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="76a94-126">See Also</span></span>  
 <span data-ttu-id="76a94-127">[Fenster "Variablen"](../../2014/integration-services/variables-window.md) </span><span class="sxs-lookup"><span data-stu-id="76a94-127">[Variables Window](../../2014/integration-services/variables-window.md) </span></span>  
 <span data-ttu-id="76a94-128">[Integration Services-Variablen &#40;SSIS&#41;](integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="76a94-128">[Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md) </span></span>  
 <span data-ttu-id="76a94-129">[Verwenden von Variablen in Paketen](../../2014/integration-services/use-variables-in-packages.md) </span><span class="sxs-lookup"><span data-stu-id="76a94-129">[Use Variables in Packages](../../2014/integration-services/use-variables-in-packages.md) </span></span>  
 [<span data-ttu-id="76a94-130">Integration Services-Ereignishandler &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="76a94-130">Integration Services &#40;SSIS&#41; Event Handlers</span></span>](integration-services-ssis-event-handlers.md)  
  
  
