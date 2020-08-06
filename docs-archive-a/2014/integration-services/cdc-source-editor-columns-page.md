---
title: Quellen-Editor für CDC (Seite Spalten) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.cdcsource.columns.f1
ms.assetid: bcf3030e-98d8-4445-967c-33c3f8ecb4fc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: aa30defb5e6873ea05e8e41c733477cf50d0dc4f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621628"
---
# <a name="cdc-source-editor-columns-page"></a><span data-ttu-id="e1128-102">Quellen-Editor für CDC (Seite Spalten)</span><span class="sxs-lookup"><span data-stu-id="e1128-102">CDC Source Editor (Columns Page)</span></span>
  <span data-ttu-id="e1128-103">Auf der Seite **Spalten** des Dialogfelds **Quellen-Editor für CDC** können Sie jeder externen Spalte (Quellspalte) eine Ausgabespalte zuordnen.</span><span class="sxs-lookup"><span data-stu-id="e1128-103">Use the **Columns** page of the **CDC Source Editor** dialog box to map an output column to each external (source) column.</span></span>  
  
 <span data-ttu-id="e1128-104">Weitere Informationen zur CDC-Quelle finden Sie unter [CDC Source](data-flow/cdc-source.md).</span><span class="sxs-lookup"><span data-stu-id="e1128-104">To learn more about the CDC source, see [CDC Source](data-flow/cdc-source.md).</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="e1128-105">Aufgabenliste</span><span class="sxs-lookup"><span data-stu-id="e1128-105">Task List</span></span>  
 <span data-ttu-id="e1128-106">**So öffnen Sie die Seite "Spalten" des Quellen-Editors für CDC**</span><span class="sxs-lookup"><span data-stu-id="e1128-106">**To open the CDC Source Editor Columns Page**</span></span>  
  
1.  <span data-ttu-id="e1128-107">Öffnen Sie in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]das [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] -Paket, das die CDC-Quelle enthält.</span><span class="sxs-lookup"><span data-stu-id="e1128-107">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] package that has the CDC source.</span></span>  
  
2.  <span data-ttu-id="e1128-108">Doppelklicken Sie auf der Registerkarte **Datenfluss** auf die CDC-Quelle.</span><span class="sxs-lookup"><span data-stu-id="e1128-108">On the **Data Flow** tab, double-click the CDC source.</span></span>  
  
3.  <span data-ttu-id="e1128-109">Klicken Sie im **Quellen-Editor für CDC**auf **Spalten**.</span><span class="sxs-lookup"><span data-stu-id="e1128-109">In the **CDC Source Editor**, click **Columns**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e1128-110">Tastatur</span><span class="sxs-lookup"><span data-stu-id="e1128-110">Options</span></span>  
 <span data-ttu-id="e1128-111">**Verfügbare externe Spalten**</span><span class="sxs-lookup"><span data-stu-id="e1128-111">**Available External Columns**</span></span>  
 <span data-ttu-id="e1128-112">Eine Liste der in der Datenquelle verfügbaren externen Spalten.</span><span class="sxs-lookup"><span data-stu-id="e1128-112">A list of available external columns in the data source.</span></span> <span data-ttu-id="e1128-113">Mit der Tabelle können keine Spalten hinzugefügt oder gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="e1128-113">You cannot use this table to add or delete columns.</span></span> <span data-ttu-id="e1128-114">Wählen Sie die zu verwendenden Spalten in der Datenquelle aus.</span><span class="sxs-lookup"><span data-stu-id="e1128-114">Select the columns to use in the source.</span></span> <span data-ttu-id="e1128-115">Die ausgewählten Spalten werden der Liste **Externe Spalte** in der Reihenfolge hinzugefügt, in der Sie sie auswählen.</span><span class="sxs-lookup"><span data-stu-id="e1128-115">The selected columns are added to the **External Column** list in the order they are selected.</span></span>  
  
 <span data-ttu-id="e1128-116">**Externe Spalte**</span><span class="sxs-lookup"><span data-stu-id="e1128-116">**External Column**</span></span>  
 <span data-ttu-id="e1128-117">Eine Ansicht der externen Spalten (Quellspalten) in der Reihenfolge, in der sie angezeigt werden, wenn Sie Komponenten konfigurieren, die Daten aus der CDC-Quelle verwenden.</span><span class="sxs-lookup"><span data-stu-id="e1128-117">A view of the external (source) columns in the order that you see them when configuring components that consume data from the CDC source.</span></span> <span data-ttu-id="e1128-118">Sie können diese Reihenfolge ändern, indem Sie zunächst die ausgewählten Spalten in der Liste **Verfügbare externe Spalten** löschen und anschließend die externen Spalten in einer anderen Reihenfolge in der Liste auswählen.</span><span class="sxs-lookup"><span data-stu-id="e1128-118">To change this order, first clear the selected columns in the **Available External Columns** list, and then select external columns from the list in a different order.</span></span> <span data-ttu-id="e1128-119">Die ausgewählten Spalten werden der Liste **Externe Spalte** in der Reihenfolge hinzugefügt, in der Sie sie auswählen.</span><span class="sxs-lookup"><span data-stu-id="e1128-119">The selected columns are added to the **External Column** list in the order you select them.</span></span>  
  
 <span data-ttu-id="e1128-120">**Ausgabespalte**</span><span class="sxs-lookup"><span data-stu-id="e1128-120">**Output Column**</span></span>  
 <span data-ttu-id="e1128-121">Geben Sie für jede Ausgabespalte einen eindeutigen Namen ein.</span><span class="sxs-lookup"><span data-stu-id="e1128-121">Enter a unique name for each output column.</span></span> <span data-ttu-id="e1128-122">Standardmäßig wird der Name der ausgewählten externen Spalte (Quellspalte) verwendet, Sie können jedoch auch einen beschreibenden Namen angeben, sofern dieser eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="e1128-122">The default is the name of the selected external (source) column, however you can choose any unique, descriptive name.</span></span> <span data-ttu-id="e1128-123">Der eingegebene Name wird im SSIS-Designer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e1128-123">The name entered is displayed in the SSIS Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1128-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e1128-124">See Also</span></span>  
 <span data-ttu-id="e1128-125">[Quellen-Editor für CDC &#40;Seite „Verbindungs-Manager“&#41;](../../2014/integration-services/cdc-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="e1128-125">[CDC Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/cdc-source-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="e1128-126">Quellen-Editor für CDC &#40;Seite „Fehlerausgabe“&#41;</span><span class="sxs-lookup"><span data-stu-id="e1128-126">CDC Source Editor &#40;Error Output Page&#41;</span></span>](../../2014/integration-services/cdc-source-editor-error-output-page.md)  
  
  
