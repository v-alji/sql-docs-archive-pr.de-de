---
title: Quellen-Editor für Flatfiles (Seite Spalten) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.flatfilesourceadapter.columns.f1
helpviewer_keywords:
- Flat File Source Editor
ms.assetid: b5af5f65-c087-44fd-b5ae-d0441245fef2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9b0249b2b17d50fdef4b5cf4aff70a1318614257
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609349"
---
# <a name="flat-file-source-editor-columns-page"></a><span data-ttu-id="b880a-102">Quellen-Editor für Flatfiles (Seite Spalten)</span><span class="sxs-lookup"><span data-stu-id="b880a-102">Flat File Source Editor (Columns Page)</span></span>
  <span data-ttu-id="b880a-103">Mithilfe des Knotens **Spalten** des Dialogfelds **Quellen-Editor für Flatfiles** können Sie jeder externen (Quell-)Spalte eine Ausgabespalte zuordnen.</span><span class="sxs-lookup"><span data-stu-id="b880a-103">Use the **Columns** node of the **Flat File Source Editor** dialog box to map an output column to each external (source) column.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b880a-104">Die `FileNameColumnName` -Eigenschaft der Flatfilequelle und die- `FastParse` Eigenschaft ihrer Ausgabespalten sind nicht im Quellen- **Editor für Flatfiles**verfügbar, können jedoch mit dem- **Erweiterter Editor**festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="b880a-104">The `FileNameColumnName` property of the Flat File source and the `FastParse` property of its output columns are not available in the **Flat File Source Editor**, but can be set by using the **Advanced Editor**.</span></span> <span data-ttu-id="b880a-105">Weitere Informationen zu diesen Eigenschaften finden Sie im Abschnitt Flatfilequelle von [Flat File Custom Properties](data-flow/flat-file-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="b880a-105">For more information on these properties, see the Flat File Source section of [Flat File Custom Properties](data-flow/flat-file-custom-properties.md).</span></span>  
  
 <span data-ttu-id="b880a-106">Weitere Informationen zur Flatfilequelle finden Sie unter [Flat File Source](data-flow/flat-file-source.md).</span><span class="sxs-lookup"><span data-stu-id="b880a-106">To learn more about the Flat File source, see [Flat File Source](data-flow/flat-file-source.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="b880a-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="b880a-107">Options</span></span>  
 <span data-ttu-id="b880a-108">**Verfügbare externe Spalten**</span><span class="sxs-lookup"><span data-stu-id="b880a-108">**Available External Columns**</span></span>  
 <span data-ttu-id="b880a-109">Zeigt die Liste der in der Datenquelle verfügbaren externen Spalten an.</span><span class="sxs-lookup"><span data-stu-id="b880a-109">View the list of available external columns in the data source.</span></span> <span data-ttu-id="b880a-110">Mit der Tabelle können keine Spalten hinzugefügt oder gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="b880a-110">You cannot use this table to add or delete columns.</span></span>  
  
 <span data-ttu-id="b880a-111">**Externe Spalte**</span><span class="sxs-lookup"><span data-stu-id="b880a-111">**External Column**</span></span>  
 <span data-ttu-id="b880a-112">Zeigt die externen (Quell-)Spalten in der Reihenfolge an, in der sie von dem Task gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="b880a-112">View external (source) columns in the order in which the task will read them.</span></span> <span data-ttu-id="b880a-113">Sie können die Reihenfolge ändern, indem Sie zunächst die ausgewählten Spalten in der Tabelle löschen. Wählen Sie anschließend die externen Spalten in einer anderen Reihenfolge aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="b880a-113">You can change this order by first clearing the selected columns in the table, and then selecting external columns from the list in a different order.</span></span>  
  
 <span data-ttu-id="b880a-114">**Ausgabespalte**</span><span class="sxs-lookup"><span data-stu-id="b880a-114">**Output Column**</span></span>  
 <span data-ttu-id="b880a-115">Geben Sie für jede Ausgabespalte einen eindeutigen Namen an.</span><span class="sxs-lookup"><span data-stu-id="b880a-115">Provide a unique name for each output column.</span></span> <span data-ttu-id="b880a-116">Standardmäßig wird der Name der ausgewählten externen (Quell-)Spalte verwendet. Sie können jedoch auch einen beschreibenden Namen angeben, sofern dieser eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="b880a-116">The default is the name of the selected external (source) column; however, you can choose any unique, descriptive name.</span></span> <span data-ttu-id="b880a-117">Der angegebene Name wird im [!INCLUDE[ssIS](../includes/ssis-md.md)] -Designer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b880a-117">The name provided will be displayed within [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b880a-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b880a-118">See Also</span></span>  
 <span data-ttu-id="b880a-119">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="b880a-119">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="b880a-120">[Quellen-Editor für Flatfiles &#40;Seite Verbindungs-Manager&#41;](../../2014/integration-services/flat-file-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="b880a-120">[Flat File Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/flat-file-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="b880a-121">[Quellen-Editor für Flatfiles &#40;Seite Fehlerausgabe&#41;](../../2014/integration-services/flat-file-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="b880a-121">[Flat File Source Editor &#40;Error Output Page&#41;](../../2014/integration-services/flat-file-source-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="b880a-122">Verbindungs-Manager für Flatfiles</span><span class="sxs-lookup"><span data-stu-id="b880a-122">Flat File Connection Manager</span></span>](connection-manager/file-connection-manager.md)  
  
  
