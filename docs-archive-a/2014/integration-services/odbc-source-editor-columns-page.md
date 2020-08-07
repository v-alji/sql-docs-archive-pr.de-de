---
title: Quellen-Editor für ODBC (Seite Spalten) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.odbcsource.columns.f1
ms.assetid: 565984eb-8318-4be7-bebc-262209cf5065
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7a11ab6a86978366d07fbe63362f1702310b5d89
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718574"
---
# <a name="odbc-source-editor-columns-page"></a><span data-ttu-id="20aad-102">Quellen-Editor für ODBC (Seite Spalten)</span><span class="sxs-lookup"><span data-stu-id="20aad-102">ODBC Source Editor (Columns Page)</span></span>
  <span data-ttu-id="20aad-103">Auf der Seite **Spalten** des Dialogfelds **Quellen-Editor für ODBC** können Sie jeder externen Spalte (Quellspalte) eine Ausgabespalte zuordnen.</span><span class="sxs-lookup"><span data-stu-id="20aad-103">Use the **Columns** page of the **ODBC Source Editor** dialog box to map an output column to each external (source) column.</span></span>  
  
 <span data-ttu-id="20aad-104">Weitere Informationen zur ODBC-Quelle finden Sie unter [ODBC Source](data-flow/odbc-source.md).</span><span class="sxs-lookup"><span data-stu-id="20aad-104">To learn more about the ODBC source, see [ODBC Source](data-flow/odbc-source.md).</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="20aad-105">Aufgabenliste</span><span class="sxs-lookup"><span data-stu-id="20aad-105">Task List</span></span>  
 <span data-ttu-id="20aad-106">**So öffnen Sie die Seite "Spalten" des Quellen-Editors für ODBC**</span><span class="sxs-lookup"><span data-stu-id="20aad-106">**To open the ODBC Source Editor Columns Page**</span></span>  
  
1.  <span data-ttu-id="20aad-107">Öffnen Sie in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]das [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] -Paket, das die ODBC-Quelle enthält.</span><span class="sxs-lookup"><span data-stu-id="20aad-107">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] package that has the ODBC source.</span></span>  
  
2.  <span data-ttu-id="20aad-108">Doppelklicken Sie auf der Registerkarte **Datenfluss** auf die ODBC-Quelle.</span><span class="sxs-lookup"><span data-stu-id="20aad-108">On the **Data Flow** tab, double-click the ODBC source.</span></span>  
  
3.  <span data-ttu-id="20aad-109">Klicken Sie im **Quellen-Editor für ODBC**auf **Spalten**.</span><span class="sxs-lookup"><span data-stu-id="20aad-109">In the **ODBC Source Editor**, click **Columns**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="20aad-110">Optionen</span><span class="sxs-lookup"><span data-stu-id="20aad-110">Options</span></span>  
  
### <a name="available-external-columns"></a><span data-ttu-id="20aad-111">Verfügbare externe Spalten</span><span class="sxs-lookup"><span data-stu-id="20aad-111">Available External Columns</span></span>  
 <span data-ttu-id="20aad-112">Eine Liste der in der Datenquelle verfügbaren externen Spalten.</span><span class="sxs-lookup"><span data-stu-id="20aad-112">A list of available external columns in the data source.</span></span> <span data-ttu-id="20aad-113">Mit der Tabelle können keine Spalten hinzugefügt oder gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="20aad-113">You cannot use this table to add or delete columns.</span></span> <span data-ttu-id="20aad-114">Wählen Sie die zu verwendenden Spalten aus der Datenquelle aus.</span><span class="sxs-lookup"><span data-stu-id="20aad-114">Select the columns to use from the source.</span></span> <span data-ttu-id="20aad-115">Die ausgewählten Spalten werden der Liste **Externe Spalte** in der Reihenfolge hinzugefügt, in der Sie sie auswählen.</span><span class="sxs-lookup"><span data-stu-id="20aad-115">The selected columns are added to the **External Column** list in the order they are selected.</span></span>  
  
 <span data-ttu-id="20aad-116">Aktivieren Sie das Kontrollkästchen **Alle auswählen** , um alle Spalten auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="20aad-116">Select the **Select All** check box to select all of the columns.</span></span>  
  
### <a name="external-column"></a><span data-ttu-id="20aad-117">Externe Spalte</span><span class="sxs-lookup"><span data-stu-id="20aad-117">External Column</span></span>  
 <span data-ttu-id="20aad-118">Eine Ansicht der externen Spalten (Quellspalten) in der Reihenfolge, in der sie angezeigt werden, wenn Sie Komponenten konfigurieren, die Daten aus dieser Quelle verwenden.</span><span class="sxs-lookup"><span data-stu-id="20aad-118">A view of the external (source) columns in the order that you see them when configuring components that consume data from the ODBC source.</span></span>  
  
### <a name="output-column"></a><span data-ttu-id="20aad-119">Ausgabespalte</span><span class="sxs-lookup"><span data-stu-id="20aad-119">Output Column</span></span>  
 <span data-ttu-id="20aad-120">Geben Sie für jede Ausgabespalte einen eindeutigen Namen ein.</span><span class="sxs-lookup"><span data-stu-id="20aad-120">Enter a unique name for each output column.</span></span> <span data-ttu-id="20aad-121">Standardmäßig wird der Name der ausgewählten externen (Quell-)Spalte verwendet. Sie können jedoch auch einen beschreibenden Namen angeben, sofern dieser eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="20aad-121">The default is the name of the selected external (source) column; however, you can choose any unique, descriptive name.</span></span> <span data-ttu-id="20aad-122">Der eingegebene Name wird im SSIS-Designer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="20aad-122">The name entered is displayed in the SSIS Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20aad-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="20aad-123">See Also</span></span>  
 <span data-ttu-id="20aad-124">[Der Quellen-Editor für ODBC &#40;Verbindungs-Manager-Seite&#41;](../../2014/integration-services/odbc-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="20aad-124">[ODBC Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/odbc-source-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="20aad-125">Quellen-Editor für ODBC &#40;Seite „Fehlerausgabe“&#41;</span><span class="sxs-lookup"><span data-stu-id="20aad-125">ODBC Source Editor &#40;Error Output Page&#41;</span></span>](../../2014/integration-services/odbc-source-editor-error-output-page.md)  
  
  
