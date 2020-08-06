---
title: CDC-Splitter | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.cdcsplitter.f1
ms.assetid: 167bc5c6-fa36-439d-987c-b20acd1a77e2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 45dd16602625b28d2ca7e16f2fa6b0d62294fe81
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619245"
---
# <a name="cdc-splitter"></a><span data-ttu-id="8a825-102">CDC-Splitter</span><span class="sxs-lookup"><span data-stu-id="8a825-102">CDC Splitter</span></span>
  <span data-ttu-id="8a825-103">Der CDC-Splitter teilt einen einzelnen Fluss von Änderungszeilen aus einem CDC-Quelldatenfluss in unterschiedliche Datenflüsse für Einfüge-, Update und Löschvorgänge auf.</span><span class="sxs-lookup"><span data-stu-id="8a825-103">The CDC splitter splits a single flow of change rows from a CDC source data flow into different data flows for Insert, Update and Delete operations.</span></span> <span data-ttu-id="8a825-104">Der Datenfluss wird basierend auf der erforderlichen Spalte `__$operation` und seinen Standardwerten in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] -Änderungstabellen geteilt.</span><span class="sxs-lookup"><span data-stu-id="8a825-104">The data flow is split based on the required column `__$operation` and its standard values in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] change tables.</span></span>  
  
|<span data-ttu-id="8a825-105">Wert des Vorgangs</span><span class="sxs-lookup"><span data-stu-id="8a825-105">Value of Operation</span></span>|<span data-ttu-id="8a825-106">Output</span><span class="sxs-lookup"><span data-stu-id="8a825-106">Output</span></span>|<span data-ttu-id="8a825-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="8a825-107">Description</span></span>|  
|------------------------|------------|-----------------|  
|<span data-ttu-id="8a825-108">1</span><span class="sxs-lookup"><span data-stu-id="8a825-108">1</span></span>|<span data-ttu-id="8a825-109">Löschen</span><span class="sxs-lookup"><span data-stu-id="8a825-109">Delete</span></span>|<span data-ttu-id="8a825-110">Gelöschte Zeile</span><span class="sxs-lookup"><span data-stu-id="8a825-110">Deleted Row</span></span>|  
|<span data-ttu-id="8a825-111">2</span><span class="sxs-lookup"><span data-stu-id="8a825-111">2</span></span>|<span data-ttu-id="8a825-112">Einfügen</span><span class="sxs-lookup"><span data-stu-id="8a825-112">Insert</span></span>|<span data-ttu-id="8a825-113">Eingefügte Zeile (nicht verfügbar bei Verwendung des CDC-Modus **Net with merge** )</span><span class="sxs-lookup"><span data-stu-id="8a825-113">Inserted row (not available when using **Net with Merge** CDC mode)</span></span>|  
|<span data-ttu-id="8a825-114">3</span><span class="sxs-lookup"><span data-stu-id="8a825-114">3</span></span>|<span data-ttu-id="8a825-115">Aktualisieren</span><span class="sxs-lookup"><span data-stu-id="8a825-115">Update</span></span>|<span data-ttu-id="8a825-116">Zeile vor Update (nur bei Verwendung des CDC-Modus **All with Old Values** verfügbar)</span><span class="sxs-lookup"><span data-stu-id="8a825-116">Before-update row (available only when using **All with Old Values** CDC mode)</span></span>|  
|<span data-ttu-id="8a825-117">4</span><span class="sxs-lookup"><span data-stu-id="8a825-117">4</span></span>|<span data-ttu-id="8a825-118">Aktualisieren</span><span class="sxs-lookup"><span data-stu-id="8a825-118">Update</span></span>|<span data-ttu-id="8a825-119">Zeile nach Update (folgt auf die Zeile vor Update)</span><span class="sxs-lookup"><span data-stu-id="8a825-119">After-update row (follows the Before-update)</span></span>|  
|<span data-ttu-id="8a825-120">5</span><span class="sxs-lookup"><span data-stu-id="8a825-120">5</span></span>|<span data-ttu-id="8a825-121">Aktualisieren</span><span class="sxs-lookup"><span data-stu-id="8a825-121">Update</span></span>|<span data-ttu-id="8a825-122">Mergezeile (nur bei Verwendung des CDC-Modus **Net with merge** verfügbar)</span><span class="sxs-lookup"><span data-stu-id="8a825-122">Merge row (available only when using **Net with Merge** CDC mode)</span></span>|  
|<span data-ttu-id="8a825-123">Andere</span><span class="sxs-lookup"><span data-stu-id="8a825-123">Other</span></span>|<span data-ttu-id="8a825-124">Fehler</span><span class="sxs-lookup"><span data-stu-id="8a825-124">Error</span></span>||  
  
 <span data-ttu-id="8a825-125">Sie können den Splitter verwenden, um vordefinierte INSERT-, DELETE- und UPDATE-Ausgaben zur weiteren Verarbeitung zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="8a825-125">You can use the splitter to connect to pre-defined INSERT, DELETE, and UPDATE outputs for further processing.</span></span>  
  
 <span data-ttu-id="8a825-126">Die CDC-Splittertransformation weist eine normale Eingabe und eine Fehlerausgabe auf.</span><span class="sxs-lookup"><span data-stu-id="8a825-126">The CDC Splitter transformation has one regular input and one error output.</span></span>  
  
## <a name="error-handling"></a><span data-ttu-id="8a825-127">Fehlerbehandlung</span><span class="sxs-lookup"><span data-stu-id="8a825-127">Error Handling</span></span>  
 <span data-ttu-id="8a825-128">Die CDC-Splittertransformation weist eine Fehlerausgabe auf.</span><span class="sxs-lookup"><span data-stu-id="8a825-128">The CDC Splitter transformation has an error output.</span></span> <span data-ttu-id="8a825-129">Eingabezeilen mit einem ungültigen Wert für die Spalte $operation werden als fehlerhaft angesehen und gemäß der **ErrorRowDisposition** -Eigenschaft der Eingabe behandelt.</span><span class="sxs-lookup"><span data-stu-id="8a825-129">Input rows with an invalid value of the $operation column are considered erroneous and are handled according to the **ErrorRowDisposition** property of the input.</span></span>  
  
 <span data-ttu-id="8a825-130">Die Komponentenfehlerausgabe enthält die folgenden Ausgabespalten:</span><span class="sxs-lookup"><span data-stu-id="8a825-130">The component error output includes the following output columns:</span></span>  
  
-   <span data-ttu-id="8a825-131">**Fehlercode**: Auf 1 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="8a825-131">**Error Code**: Set to 1.</span></span>  
  
-   <span data-ttu-id="8a825-132">**Fehlerspalte**: Die Quellspalte, die den Fehler verursacht (für Konvertierungsfehler).</span><span class="sxs-lookup"><span data-stu-id="8a825-132">**Error Column**: The source column causing the error (for conversion errors).</span></span>  
  
-   <span data-ttu-id="8a825-133">**Fehlerzeilenspalten**: Die Eingabespalten der Zeile, die den Fehler verursacht hat.</span><span class="sxs-lookup"><span data-stu-id="8a825-133">**Error Row Columns**: The input columns of the row that caused the error.</span></span>  
  
## <a name="configuring-the-cdc-splitter"></a><span data-ttu-id="8a825-134">Konfigurieren des CDC-Splitters</span><span class="sxs-lookup"><span data-stu-id="8a825-134">Configuring the CDC Splitter</span></span>  
 <span data-ttu-id="8a825-135">Für den CDC-Splitter sind keine konfigurierbaren Eigenschaften vorhanden.</span><span class="sxs-lookup"><span data-stu-id="8a825-135">There are no configurable properties for the CDC splitter.</span></span>  
  
 <span data-ttu-id="8a825-136">Weitere Informationen zur Verwendung des CDC-Splitters finden Sie unter CDC-Komponenten für Microsoft SQL Server Integration Services.</span><span class="sxs-lookup"><span data-stu-id="8a825-136">For more information about using the CDC splitter, see CDC Components for Microsoft SQL Server Integration Services.</span></span>  
  
 <span data-ttu-id="8a825-137">Das Dialogfeld **Erweiterter Editor** enthält die Eigenschaften, die programmgesteuert festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="8a825-137">The **Advanced Editor** dialog box contains the properties that can be set programmatically.</span></span>  
  
 <span data-ttu-id="8a825-138">So öffnen Sie das Dialogfeld **Erweiterter Editor** :</span><span class="sxs-lookup"><span data-stu-id="8a825-138">To open the **Advanced Editor** dialog box:</span></span>  
  
-   <span data-ttu-id="8a825-139">Klicken Sie auf dem Bildschirm **Datenfluss** des [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] -Projekts mit der rechten Maustaste auf den CDC-Splitter, und wählen Sie **Erweiterten Editor anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="8a825-139">In the **Data Flow** screen of your [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] project, right click the CDC splitter and select **Show Advanced Editor**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a825-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8a825-140">See Also</span></span>  
 [<span data-ttu-id="8a825-141">Weiterleiten des CDC-Datenstroms gemäß Änderungstyp</span><span class="sxs-lookup"><span data-stu-id="8a825-141">Direct the CDC Stream According to the Type of Change</span></span>](direct-the-cdc-stream-according-to-the-type-of-change.md)  
  
  
