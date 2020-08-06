---
title: Quellen-Editor für CDC (Seite Fehlerausgabe) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.cdcsource.errorhandling.f1
ms.assetid: 8a4c2cb8-fd2f-4c45-824f-b93473a8981e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b39532304fddfa90fabe8cafe2a6caf5b1fb5c8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621627"
---
# <a name="cdc-source-editor-error-output-page"></a><span data-ttu-id="9c051-102">Quellen-Editor für CDC (Seite Fehlerausgabe)</span><span class="sxs-lookup"><span data-stu-id="9c051-102">CDC Source Editor (Error Output Page)</span></span>
  <span data-ttu-id="9c051-103">Auf der Seite **Fehlerausgabe** des Dialogfelds **Quellen-Editor für CDC** können Sie Optionen für die Fehlerbehandlung auswählen.</span><span class="sxs-lookup"><span data-stu-id="9c051-103">Use the **Error Output** page of the **CDC Source Editor** dialog box to select error handling options.</span></span>  
  
 <span data-ttu-id="9c051-104">Weitere Informationen zur CDC-Quelle finden Sie unter [CDC Source](data-flow/cdc-source.md).</span><span class="sxs-lookup"><span data-stu-id="9c051-104">To learn more about the CDC source, see [CDC Source](data-flow/cdc-source.md).</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="9c051-105">Aufgabenliste</span><span class="sxs-lookup"><span data-stu-id="9c051-105">Task List</span></span>  
 <span data-ttu-id="9c051-106">**So öffnen Sie die Seite "Fehlerausgabe" des Quellen-Editors für CDC**</span><span class="sxs-lookup"><span data-stu-id="9c051-106">**To open the CDC Source Editor Error Output Page**</span></span>  
  
1.  <span data-ttu-id="9c051-107">Öffnen Sie in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]das [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] -Paket, das die CDC-Quelle enthält.</span><span class="sxs-lookup"><span data-stu-id="9c051-107">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] package that has the CDC source.</span></span>  
  
2.  <span data-ttu-id="9c051-108">Doppelklicken Sie auf der Registerkarte **Datenfluss** auf die CDC-Quelle.</span><span class="sxs-lookup"><span data-stu-id="9c051-108">On the **Data Flow** tab, double-click the CDC source.</span></span>  
  
3.  <span data-ttu-id="9c051-109">Klicken Sie im **Quellen-Editor für CDC**auf **Fehlerausgabe**.</span><span class="sxs-lookup"><span data-stu-id="9c051-109">In the **CDC Source Editor**, click **Error Output**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="9c051-110">Tastatur</span><span class="sxs-lookup"><span data-stu-id="9c051-110">Options</span></span>  
 <span data-ttu-id="9c051-111">**Eingabe/Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="9c051-111">**Input/Output**</span></span>  
 <span data-ttu-id="9c051-112">Zeigt den Namen der Datenquelle an.</span><span class="sxs-lookup"><span data-stu-id="9c051-112">View the name of the data source.</span></span>  
  
 <span data-ttu-id="9c051-113">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="9c051-113">**Column**</span></span>  
 <span data-ttu-id="9c051-114">Zeigt die externen Spalten (Quellspalten) an, die im Dialogfeld **Quellen-Editor für CDC** auf der Seite **Verbindungs-Manager** ausgewählt wurden.</span><span class="sxs-lookup"><span data-stu-id="9c051-114">View the external (source) columns that you selected on the **Connection Manager** page of the **CDC Source Editor** dialog box.</span></span>  
  
 <span data-ttu-id="9c051-115">**Fehler**</span><span class="sxs-lookup"><span data-stu-id="9c051-115">**Error**</span></span>  
 <span data-ttu-id="9c051-116">Wählen Sie aus, wie die CDC-Quelle Fehler in einem Fluss behandeln soll: Fehler ignorieren, Zeile umleiten oder Komponente mit einem Fehler abbrechen.</span><span class="sxs-lookup"><span data-stu-id="9c051-116">Select how the CDC source should handle errors in a flow: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="9c051-117">**Abschneiden**</span><span class="sxs-lookup"><span data-stu-id="9c051-117">**Truncation**</span></span>  
 <span data-ttu-id="9c051-118">Wählen Sie aus, wie die CDC-Quelle Kürzungen in einem Fluss behandeln soll: Fehler ignorieren, Zeile umleiten oder Komponente mit einem Fehler abbrechen.</span><span class="sxs-lookup"><span data-stu-id="9c051-118">Select how the CDC source should handle truncation in a flow: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="9c051-119">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="9c051-119">**Description**</span></span>  
 <span data-ttu-id="9c051-120">Wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="9c051-120">Not used.</span></span>  
  
 <span data-ttu-id="9c051-121">**Diesen Wert für ausgewählte Zellen festlegen**</span><span class="sxs-lookup"><span data-stu-id="9c051-121">**Set this value to selected cells**</span></span>  
 <span data-ttu-id="9c051-122">Wählen Sie aus, wie die CDC-Quelle im Fall eines Fehlers oder einer Kürzung mit den ausgewählten Zellen verfahren soll: Fehler ignorieren, Zeile umleiten oder Komponente mit einem Fehler abbrechen.</span><span class="sxs-lookup"><span data-stu-id="9c051-122">Select how the CDC source handles all selected cells when an error or truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="9c051-123">**Anwenden**</span><span class="sxs-lookup"><span data-stu-id="9c051-123">**Apply**</span></span>  
 <span data-ttu-id="9c051-124">Wendet die Fehlerbehandlungsoptionen auf die ausgewählten Zellen an.</span><span class="sxs-lookup"><span data-stu-id="9c051-124">Apply the error handling options to the selected cells.</span></span>  
  
## <a name="error-handling-options"></a><span data-ttu-id="9c051-125">Fehlerbehandlungsoptionen</span><span class="sxs-lookup"><span data-stu-id="9c051-125">Error Handling Options</span></span>  
 <span data-ttu-id="9c051-126">Mit den folgenden Optionen konfigurieren Sie, wie die CDC-Quelle Fehler und Kürzungen behandelt.</span><span class="sxs-lookup"><span data-stu-id="9c051-126">You use the following options to configure how the CDC source handles errors and truncations.</span></span>  
  
 <span data-ttu-id="9c051-127">**Fehler bei Komponente**</span><span class="sxs-lookup"><span data-stu-id="9c051-127">**Fail Component**</span></span>  
 <span data-ttu-id="9c051-128">Bei einem Fehler oder beim Abschneiden von Daten wird der Datenflusstask nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="9c051-128">The Data Flow task fails when an error or a truncation occurs.</span></span> <span data-ttu-id="9c051-129">Dies ist das Standardverhalten.</span><span class="sxs-lookup"><span data-stu-id="9c051-129">This is the default behavior.</span></span>  
  
 <span data-ttu-id="9c051-130">**Fehler ignorieren**</span><span class="sxs-lookup"><span data-stu-id="9c051-130">**Ignore Failure**</span></span>  
 <span data-ttu-id="9c051-131">Der Fehler oder die Kürzung wird ignoriert, und die Datenzeile wird an die Ausgabe der CDC-Quelle umgeleitet.</span><span class="sxs-lookup"><span data-stu-id="9c051-131">The error or the truncation is ignored and the data row is directed to the CDC source output.</span></span>  
  
 <span data-ttu-id="9c051-132">**Zeile umleiten**</span><span class="sxs-lookup"><span data-stu-id="9c051-132">**Redirect Flow**</span></span>  
 <span data-ttu-id="9c051-133">Der Fehler oder die Kürzung wird an die Fehlerausgabe der CDC-Quelle umgeleitet.</span><span class="sxs-lookup"><span data-stu-id="9c051-133">The error or the truncation data row is directed to the error output of the CDC source.</span></span> <span data-ttu-id="9c051-134">In diesem Fall wird die Fehlerbehandlung der CDC-Quelle verwendet.</span><span class="sxs-lookup"><span data-stu-id="9c051-134">In this case the CDC source error handling is used.</span></span> <span data-ttu-id="9c051-135">Weitere Informationen finden Sie unter [CDC Source](data-flow/cdc-source.md).</span><span class="sxs-lookup"><span data-stu-id="9c051-135">For more information, see [CDC Source](data-flow/cdc-source.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c051-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9c051-136">See Also</span></span>  
 <span data-ttu-id="9c051-137">[Quellen-Editor für CDC &#40;Seite „Verbindungs-Manager“&#41;](../../2014/integration-services/cdc-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="9c051-137">[CDC Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/cdc-source-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="9c051-138">Quellen-Editor für CDC &#40;Seite „Spalten“&#41;</span><span class="sxs-lookup"><span data-stu-id="9c051-138">CDC Source Editor &#40;Columns Page&#41;</span></span>](../../2014/integration-services/cdc-source-editor-columns-page.md)  
  
  
