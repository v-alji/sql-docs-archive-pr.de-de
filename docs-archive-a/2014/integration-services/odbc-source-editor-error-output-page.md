---
title: Quellen-Editor für ODBC (Seite Fehlerausgabe) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.odbcsource.errorhandling.f1
ms.assetid: b2f6866c-db07-4cb3-9f38-889f8d2b03e6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a8e169875a26efbe0a7f1ac3d06856b393266eb2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718562"
---
# <a name="odbc-source-editor-error-output-page"></a><span data-ttu-id="21518-102">Quellen-Editor für ODBC (Seite Fehlerausgabe)</span><span class="sxs-lookup"><span data-stu-id="21518-102">ODBC Source Editor (Error Output Page)</span></span>
  <span data-ttu-id="21518-103">Auf der Seite **Fehlerausgabe** des Dialogfelds **Quellen-Editor für ODBC** können Sie Optionen für die Fehlerbehandlung auswählen.</span><span class="sxs-lookup"><span data-stu-id="21518-103">Use the **Error Output** page of the **ODBC Source Editor** dialog box to select error handling options.</span></span>  
  
 <span data-ttu-id="21518-104">Weitere Informationen zur ODBC-Quelle finden Sie unter [CDC Source](data-flow/cdc-source.md).</span><span class="sxs-lookup"><span data-stu-id="21518-104">To learn more about the ODBC source, see [CDC Source](data-flow/cdc-source.md).</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="21518-105">Aufgabenliste</span><span class="sxs-lookup"><span data-stu-id="21518-105">Task List</span></span>  
 <span data-ttu-id="21518-106">**So öffnen Sie die Seite "Fehlerausgabe" des Quellen-Editors für ODBC**</span><span class="sxs-lookup"><span data-stu-id="21518-106">**To open the ODBC Source Editor Error Output Page**</span></span>  
  
-   <span data-ttu-id="21518-107">Öffnen Sie in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]das [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] -Paket, das die ODBC-Quelle enthält.</span><span class="sxs-lookup"><span data-stu-id="21518-107">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] package that has the ODBC source.</span></span>  
  
-   <span data-ttu-id="21518-108">Doppelklicken Sie auf der Registerkarte **Datenfluss** auf die ODBC-Quelle.</span><span class="sxs-lookup"><span data-stu-id="21518-108">On the **Data Flow** tab, double-click the ODBC source.</span></span>  
  
-   <span data-ttu-id="21518-109">Klicken Sie im **Quellen-Editor für ODBC**auf **Fehlerausgabe**.</span><span class="sxs-lookup"><span data-stu-id="21518-109">In the **ODBC Source Editor**, click **Error Output**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="21518-110">Tastatur</span><span class="sxs-lookup"><span data-stu-id="21518-110">Options</span></span>  
  
### <a name="inputoutput"></a><span data-ttu-id="21518-111">Eingabe/Ausgabe</span><span class="sxs-lookup"><span data-stu-id="21518-111">Input/Output</span></span>  
 <span data-ttu-id="21518-112">Zeigt den Namen der Datenquelle an.</span><span class="sxs-lookup"><span data-stu-id="21518-112">View the name of the data source.</span></span>  
  
### <a name="column"></a><span data-ttu-id="21518-113">Column</span><span class="sxs-lookup"><span data-stu-id="21518-113">Column</span></span>  
 <span data-ttu-id="21518-114">Wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="21518-114">Not used.</span></span>  
  
### <a name="error"></a><span data-ttu-id="21518-115">Fehler</span><span class="sxs-lookup"><span data-stu-id="21518-115">Error</span></span>  
 <span data-ttu-id="21518-116">Wählen Sie aus, wie die ODBC-Quelle Fehler in einem Fluss behandeln soll: Fehler ignorieren, Zeile umleiten oder Komponente mit einem Fehler abbrechen.</span><span class="sxs-lookup"><span data-stu-id="21518-116">Select how the ODBC source should handle errors in a flow: ignore the failure, redirect the row, or fail the component.</span></span>  
  
### <a name="truncation"></a><span data-ttu-id="21518-117">Abschneiden</span><span class="sxs-lookup"><span data-stu-id="21518-117">Truncation</span></span>  
 <span data-ttu-id="21518-118">Wählen Sie aus, wie die ODBC-Quelle Kürzungen in einem Fluss behandeln soll: Fehler ignorieren, Zeile umleiten oder Komponente mit einem Fehler abbrechen.</span><span class="sxs-lookup"><span data-stu-id="21518-118">Select how the ODBC source should handle truncation in a flow: ignore the failure, redirect the row, or fail the component.</span></span>  
  
### <a name="description"></a><span data-ttu-id="21518-119">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="21518-119">Description</span></span>  
 <span data-ttu-id="21518-120">Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="21518-120">Not used.</span></span>  
  
### <a name="set-this-value-to-selected-cells"></a><span data-ttu-id="21518-121">Diesen Wert für ausgewählte Zellen festlegen</span><span class="sxs-lookup"><span data-stu-id="21518-121">Set this value to selected cells</span></span>  
 <span data-ttu-id="21518-122">Wählen Sie aus, wie die ODBC-Quelle im Fall eines Fehlers oder einer Kürzung mit den ausgewählten Zellen verfahren soll: Fehler ignorieren, Zeile umleiten oder Komponente mit einem Fehler abbrechen.</span><span class="sxs-lookup"><span data-stu-id="21518-122">Select how the ODBC source handles all selected cells when an error or truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
### <a name="apply"></a><span data-ttu-id="21518-123">Anwenden</span><span class="sxs-lookup"><span data-stu-id="21518-123">Apply</span></span>  
 <span data-ttu-id="21518-124">Wendet die Fehlerbehandlungsoptionen auf die ausgewählten Zellen an.</span><span class="sxs-lookup"><span data-stu-id="21518-124">Apply the error handling options to the selected cells.</span></span>  
  
## <a name="error-handling-options"></a><span data-ttu-id="21518-125">Fehlerbehandlungsoptionen</span><span class="sxs-lookup"><span data-stu-id="21518-125">Error Handling Options</span></span>  
 <span data-ttu-id="21518-126">Mit den folgenden Optionen konfigurieren Sie, wie die ODBC-Quelle Fehler und Kürzungen behandelt.</span><span class="sxs-lookup"><span data-stu-id="21518-126">You use the following options to configure how the ODBC source handles errors and truncations.</span></span>  
  
### <a name="fail-component"></a><span data-ttu-id="21518-127">Fehler bei Komponente</span><span class="sxs-lookup"><span data-stu-id="21518-127">Fail Component</span></span>  
 <span data-ttu-id="21518-128">Bei einem Fehler oder beim Abschneiden von Daten wird der Datenflusstask nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="21518-128">The Data Flow task fails when an error or a truncation occurs.</span></span> <span data-ttu-id="21518-129">Dies ist das Standardverhalten.</span><span class="sxs-lookup"><span data-stu-id="21518-129">This is the default behavior.</span></span>  
  
### <a name="ignore-failure"></a><span data-ttu-id="21518-130">Fehler ignorieren</span><span class="sxs-lookup"><span data-stu-id="21518-130">Ignore Failure</span></span>  
 <span data-ttu-id="21518-131">Der Fehler oder die Kürzung wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="21518-131">The error or the truncation is ignored.</span></span>  
  
### <a name="redirect-flow"></a><span data-ttu-id="21518-132">Zeile umleiten</span><span class="sxs-lookup"><span data-stu-id="21518-132">Redirect Flow</span></span>  
 <span data-ttu-id="21518-133">Die Zeile, die den Fehler oder die Kürzung verursacht, wird an die Fehlerausgabe der ODBC-Quelle umgeleitet.</span><span class="sxs-lookup"><span data-stu-id="21518-133">The row that is causing the error or the truncation is directed to the error output of the ODBC source.</span></span> <span data-ttu-id="21518-134">Weitere Informationen finden Sie unter [ODBC Source](data-flow/odbc-source.md).</span><span class="sxs-lookup"><span data-stu-id="21518-134">For more information, see [ODBC Source](data-flow/odbc-source.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21518-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="21518-135">See Also</span></span>  
 <span data-ttu-id="21518-136">[Der Quellen-Editor für ODBC &#40;Verbindungs-Manager-Seite&#41;](../../2014/integration-services/odbc-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="21518-136">[ODBC Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/odbc-source-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="21518-137">Quellen-Editor für ODBC &#40;Seite „Spalten“&#41;</span><span class="sxs-lookup"><span data-stu-id="21518-137">ODBC Source Editor &#40;Columns Page&#41;</span></span>](../../2014/integration-services/odbc-source-editor-columns-page.md)  
  
  
