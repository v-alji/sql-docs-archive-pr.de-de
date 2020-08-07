---
title: Ziel-Editor für ODBC (Seite Fehlerausgabe) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.odbcdest.errorhandling.f1
ms.assetid: 0a743f8d-2a51-4296-9976-8104f5ca22d3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 475a2e00d67b221ddf05fdd273317fbab5248cd6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718580"
---
# <a name="odbc-destination-editor-error-output-page"></a><span data-ttu-id="f9247-102">Ziel-Editor für ODBC (Seite "Fehlerausgabe")</span><span class="sxs-lookup"><span data-stu-id="f9247-102">ODBC Destination Editor (Error Output Page)</span></span>
  <span data-ttu-id="f9247-103">Auf der Seite **Fehlerausgabe** des Dialogfelds **Ziel-Editor für ODBC** können Sie Optionen für die Fehlerbehandlung auswählen.</span><span class="sxs-lookup"><span data-stu-id="f9247-103">Use the **Error Output** page of the **ODBC Destination Editor** dialog box to select error handling options.</span></span>  
  
 <span data-ttu-id="f9247-104">Weitere Informationen zum ODBC-Ziel finden Sie unter [ODBC Destination](data-flow/odbc-destination.md).</span><span class="sxs-lookup"><span data-stu-id="f9247-104">To learn more about the ODBC destination, see [ODBC Destination](data-flow/odbc-destination.md).</span></span>  
  
 <span data-ttu-id="f9247-105">**So öffnen Sie die Seite "Fehlerausgabe" des Ziel-Editors für ODBC**</span><span class="sxs-lookup"><span data-stu-id="f9247-105">**To open the ODBC Destination Editor Error Output Page**</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="f9247-106">Aufgabenliste</span><span class="sxs-lookup"><span data-stu-id="f9247-106">Task List</span></span>  
  
-   <span data-ttu-id="f9247-107">Öffnen Sie in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]das [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] -Paket, das das ODBC-Ziel enthält.</span><span class="sxs-lookup"><span data-stu-id="f9247-107">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] package that has the ODBC destination.</span></span>  
  
-   <span data-ttu-id="f9247-108">Doppelklicken Sie auf der Registerkarte **Datenfluss** auf das ODBC-Ziel.</span><span class="sxs-lookup"><span data-stu-id="f9247-108">On the **Data Flow** tab, double-click the ODBC destination.</span></span>  
  
-   <span data-ttu-id="f9247-109">Klicken Sie im **Ziel-Editor für ODBC**auf **Fehlerausgabe**.</span><span class="sxs-lookup"><span data-stu-id="f9247-109">In the **ODBC Destination Editor**, click **Error Output**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="f9247-110">Tastatur</span><span class="sxs-lookup"><span data-stu-id="f9247-110">Options</span></span>  
  
### <a name="inputoutput"></a><span data-ttu-id="f9247-111">Eingabe/Ausgabe</span><span class="sxs-lookup"><span data-stu-id="f9247-111">Input/Output</span></span>  
 <span data-ttu-id="f9247-112">Zeigt den Namen der Datenquelle an.</span><span class="sxs-lookup"><span data-stu-id="f9247-112">View the name of the data source.</span></span>  
  
### <a name="column"></a><span data-ttu-id="f9247-113">Column</span><span class="sxs-lookup"><span data-stu-id="f9247-113">Column</span></span>  
 <span data-ttu-id="f9247-114">Wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="f9247-114">Not used.</span></span>  
  
### <a name="error"></a><span data-ttu-id="f9247-115">Fehler</span><span class="sxs-lookup"><span data-stu-id="f9247-115">Error</span></span>  
 <span data-ttu-id="f9247-116">Wählen Sie aus, wie das ODBC-Ziel Fehler in einem Fluss behandeln soll: Fehler ignorieren, Zeile umleiten oder Komponente mit einem Fehler abbrechen.</span><span class="sxs-lookup"><span data-stu-id="f9247-116">Select how the ODBC destination should handle errors in a flow: ignore the failure, redirect the row, or fail the component.</span></span>  
  
### <a name="truncation"></a><span data-ttu-id="f9247-117">Abschneiden</span><span class="sxs-lookup"><span data-stu-id="f9247-117">Truncation</span></span>  
 <span data-ttu-id="f9247-118">Wählen Sie aus, wie das ODBC-Ziel Kürzungen in einem Fluss behandeln soll: Fehler ignorieren, Zeile umleiten oder Komponente mit einem Fehler abbrechen.</span><span class="sxs-lookup"><span data-stu-id="f9247-118">Select how the ODBC destination should handle truncation in a flow: ignore the failure, redirect the row, or fail the component.</span></span>  
  
### <a name="description"></a><span data-ttu-id="f9247-119">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f9247-119">Description</span></span>  
 <span data-ttu-id="f9247-120">Zeigt eine Beschreibung des Fehlers an.</span><span class="sxs-lookup"><span data-stu-id="f9247-120">View a description of the error.</span></span>  
  
### <a name="set-this-value-to-selected-cells"></a><span data-ttu-id="f9247-121">Diesen Wert für ausgewählte Zellen festlegen</span><span class="sxs-lookup"><span data-stu-id="f9247-121">Set this value to selected cells</span></span>  
 <span data-ttu-id="f9247-122">Wählen Sie aus, wie das ODBC-Ziel im Fall eines Fehlers oder einer Kürzung mit den ausgewählten Zellen verfahren soll: Fehler ignorieren, Zeile umleiten oder Komponente mit einem Fehler abbrechen.</span><span class="sxs-lookup"><span data-stu-id="f9247-122">Select how the ODBC destination handles all selected cells when an error or truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
### <a name="apply"></a><span data-ttu-id="f9247-123">Anwenden</span><span class="sxs-lookup"><span data-stu-id="f9247-123">Apply</span></span>  
 <span data-ttu-id="f9247-124">Wendet die Fehlerbehandlungsoptionen auf die ausgewählten Zellen an.</span><span class="sxs-lookup"><span data-stu-id="f9247-124">Apply the error handling options to the selected cells.</span></span>  
  
## <a name="error-handling-options"></a><span data-ttu-id="f9247-125">Fehlerbehandlungsoptionen</span><span class="sxs-lookup"><span data-stu-id="f9247-125">Error Handling Options</span></span>  
 <span data-ttu-id="f9247-126">Mit den folgenden Optionen konfigurieren Sie, wie das ODBC-Ziel Fehler und Kürzungen behandelt.</span><span class="sxs-lookup"><span data-stu-id="f9247-126">You use the following options to configure how the ODBC destination handles errors and truncations.</span></span>  
  
### <a name="fail-component"></a><span data-ttu-id="f9247-127">Fehler bei Komponente</span><span class="sxs-lookup"><span data-stu-id="f9247-127">Fail Component</span></span>  
 <span data-ttu-id="f9247-128">Bei einem Fehler oder beim Abschneiden von Daten wird der Datenflusstask nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f9247-128">The Data Flow task fails when an error or a truncation occurs.</span></span> <span data-ttu-id="f9247-129">Dies ist das Standardverhalten.</span><span class="sxs-lookup"><span data-stu-id="f9247-129">This is the default behavior.</span></span>  
  
### <a name="ignore-failure"></a><span data-ttu-id="f9247-130">Fehler ignorieren</span><span class="sxs-lookup"><span data-stu-id="f9247-130">Ignore Failure</span></span>  
 <span data-ttu-id="f9247-131">Der Fehler oder die Kürzung wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="f9247-131">The error or the truncation is ignored.</span></span>  
  
### <a name="redirect-flow"></a><span data-ttu-id="f9247-132">Zeile umleiten</span><span class="sxs-lookup"><span data-stu-id="f9247-132">Redirect Flow</span></span>  
 <span data-ttu-id="f9247-133">Die Zeile, die den Fehler oder die Kürzung verursacht, wird an die Fehlerausgabe des ODBC-Ziels umgeleitet.</span><span class="sxs-lookup"><span data-stu-id="f9247-133">The row that is causing the error or the truncation is directed to the error output of the ODBC destination.</span></span> <span data-ttu-id="f9247-134">Weitere Informationen finden Sie unter "ODBC-Ziel".</span><span class="sxs-lookup"><span data-stu-id="f9247-134">For more information, see ODBC Destination.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9247-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f9247-135">See Also</span></span>  
 <span data-ttu-id="f9247-136">[Der Ziel-Editor für ODBC &#40;Verbindungs-Manager-Seite&#41;](../../2014/integration-services/odbc-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="f9247-136">[ODBC Destination Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/odbc-destination-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="f9247-137">Ziel-Editor für ODBC &#40;Seite Zuordnungen&#41;</span><span class="sxs-lookup"><span data-stu-id="f9247-137">ODBC Destination Editor &#40;Mappings Page&#41;</span></span>](../../2014/integration-services/odbc-destination-editor-mappings-page.md)  
  
  
