---
title: Dialog Feld "Einstellungen ändern" (Analysis Services Mehrdimensionale Daten) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.process.batchsettingsdialog.f1
ms.assetid: 0041e042-d7ce-48f9-a690-a6dc65471ff3
author: minewiskan
ms.author: owend
ms.openlocfilehash: e2649195e3aff4e17d378e54c4b1d656361dfe3a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615706"
---
# <a name="change-settings-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="d9ac1-102">Dialogfeld 'Einstellungen ändern' (Analysis Services – Mehrdimensionale Daten)</span><span class="sxs-lookup"><span data-stu-id="d9ac1-102">Change Settings Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="d9ac1-103">Mithilfe des in **und** bereitgestellten Dialogfelds [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] Einstellungen ändern [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] können Sie die Einstellungen ändern, mit denen die Verarbeitung der im Dialogfeld **Verarbeiten** aufgeführten Objekte gesteuert wird.</span><span class="sxs-lookup"><span data-stu-id="d9ac1-103">Use the **Change Settings** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] and [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to change the settings that govern the processing of objects listed in the **Process** dialog box.</span></span> <span data-ttu-id="d9ac1-104">Zum Anzeigen des Dialogfelds **Einstellungen ändern** klicken Sie im Dialogfeld **Verarbeiten** auf **Einstellungen ändern** .</span><span class="sxs-lookup"><span data-stu-id="d9ac1-104">You can display the **Change Settings** dialog box by clicking **Change Settings** on the **Process** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d9ac1-105"> Mit den in diesem Dialogfeld angegebenen Einstellungen werden die Standardeinstellungen überschrieben, die von der [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Datenbank an die im Dialogfeld **Verarbeiten** aufgeführten Objekte vererbt wurden.</span><span class="sxs-lookup"><span data-stu-id="d9ac1-105">Settings specified in this dialog box override default settings inherited from the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database for the objects listed in the **Process** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d9ac1-106">Tastatur</span><span class="sxs-lookup"><span data-stu-id="d9ac1-106">Options</span></span>  
 <span data-ttu-id="d9ac1-107">**Verarbeitungsoptionen**</span><span class="sxs-lookup"><span data-stu-id="d9ac1-107">**Processing options**</span></span>  
 <span data-ttu-id="d9ac1-108">Auf dieser Registerkarte können Sie Einstellungen zu Verarbeitungsreihenfolge, Rückschreibetabelle und den vom Verarbeitungsvorgang betroffenen Objekten ändern.</span><span class="sxs-lookup"><span data-stu-id="d9ac1-108">Use this tab to modify settings related to the processing order, writeback table, and affected objects for the processing operation.</span></span> <span data-ttu-id="d9ac1-109">Die Registerkarte enthält die folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="d9ac1-109">The tab contains the following options:</span></span>  
  
 <span data-ttu-id="d9ac1-110">**Parallel**</span><span class="sxs-lookup"><span data-stu-id="d9ac1-110">**Parallel**</span></span>  
 <span data-ttu-id="d9ac1-111">Klicken Sie hier, um Objekte parallel zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="d9ac1-111">Click to process the objects in parallel.</span></span>  
  
 <span data-ttu-id="d9ac1-112">**Maximal auszuführende parallele Tasks**</span><span class="sxs-lookup"><span data-stu-id="d9ac1-112">**Maximum parallel tasks**</span></span>  
 <span data-ttu-id="d9ac1-113">Wählen Sie die maximale Anzahl der Tasks aus, die vom Verarbeitungsvorgang parallel ausgeführt werden können, oder wählen Sie die Option **Entscheidung dem Server überlassen** aus, um die optimale Anzahl der parallel ausführbaren Tasks von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] bestimmen zu lassen.</span><span class="sxs-lookup"><span data-stu-id="d9ac1-113">Select the maximum number of tasks to execute in parallel by the processing operation, or choose **Let the server decide** to allow [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] to select an optimal number of parallel tasks.</span></span>  
  
 <span data-ttu-id="d9ac1-114">**Sequenziell**</span><span class="sxs-lookup"><span data-stu-id="d9ac1-114">**Sequential**</span></span>  
 <span data-ttu-id="d9ac1-115">Klicken Sie hier, um die Objekte sequenziell zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="d9ac1-115">Click to process the objects sequentially.</span></span>  
  
 <span data-ttu-id="d9ac1-116">**Transaktionsmodus**</span><span class="sxs-lookup"><span data-stu-id="d9ac1-116">**Transaction mode**</span></span>  
 <span data-ttu-id="d9ac1-117">Wählen Sie den Transaktionsmodus für die sequenzielle Verarbeitung von Objekten aus:</span><span class="sxs-lookup"><span data-stu-id="d9ac1-117">Choose the transaction mode that is used when objects are processed in sequential order:</span></span>  
  
-   <span data-ttu-id="d9ac1-118">Bei Auswahl von**Eine Transaktion** werden alle Objekte in ein und derselben Transaktion verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="d9ac1-118">**One Transaction** processes all objects in the same transaction.</span></span>  
  
-   <span data-ttu-id="d9ac1-119">Bei Auswahl von**Separate Transaktionen** werden alle Objekte, einschließlich abhängiger Objekte, in separaten Transaktionen verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="d9ac1-119">**Separate Transactions** processes all objects, including dependent objects, in separate transactions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d9ac1-120"> Diese Option ist nur aktiviert, wenn **Sequenziell** ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="d9ac1-120">This option is enabled only if **Sequential** is selected.</span></span>  
  
 <span data-ttu-id="d9ac1-121">**Rückschreibetabellenoption**</span><span class="sxs-lookup"><span data-stu-id="d9ac1-121">**Writeback table option**</span></span>  
 <span data-ttu-id="d9ac1-122">Wählen Sie die Option zum Verwalten der Rückschreibetabelle aus.</span><span class="sxs-lookup"><span data-stu-id="d9ac1-122">Choose the option used to manage a writeback table:</span></span>  
  
-   <span data-ttu-id="d9ac1-123">Mit**Erstellen** wird eine Rückschreibetabelle erstellt, sofern noch keine vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="d9ac1-123">**Create** creates a writeback table if it does not exist.</span></span> <span data-ttu-id="d9ac1-124">Wenn bereits eine Rückschreibetabelle vorhanden ist, wird ein Fehler gemeldet.</span><span class="sxs-lookup"><span data-stu-id="d9ac1-124">An error occurs if a writeback table already exists.</span></span>  
  
-   <span data-ttu-id="d9ac1-125">Mit**Immer erstellen** wird eine Rückschreibetabelle erstellt, sofern noch keine vorhanden ist. Eine bereits vorhandene Rückschreibetabelle wird dabei überschrieben.</span><span class="sxs-lookup"><span data-stu-id="d9ac1-125">**Create always** creates a writeback table if it does not exist, or overwrites the existing writeback table if it does exist.</span></span>  
  
-   <span data-ttu-id="d9ac1-126">Bei**Vorhandene verwenden** wird eine bereits vorhandene Rückschreibetabelle verwendet.</span><span class="sxs-lookup"><span data-stu-id="d9ac1-126">**Use existing** uses the existing writeback table if it exists.</span></span> <span data-ttu-id="d9ac1-127">Wenn keine Rückschreibetabelle vorhanden ist, wird ein Fehler gemeldet.</span><span class="sxs-lookup"><span data-stu-id="d9ac1-127">An error occurs if a writeback table does not exist.</span></span>  
  
 <span data-ttu-id="d9ac1-128">**Betroffene Objekte verarbeiten**</span><span class="sxs-lookup"><span data-stu-id="d9ac1-128">**Process affected objects**</span></span>  
 <span data-ttu-id="d9ac1-129">Aktivieren Sie diese Option, um Objekte aufzunehmen und zu verarbeiten, die von Objekten im Verarbeitungsvorgang abhängig sind.</span><span class="sxs-lookup"><span data-stu-id="d9ac1-129">Select to include and process objects that depend on objects included in the processing operation.</span></span>  
  
 <span data-ttu-id="d9ac1-130">**Dimensions Schlüsselfehler**</span><span class="sxs-lookup"><span data-stu-id="d9ac1-130">**Dimension key errors**</span></span>  
 <span data-ttu-id="d9ac1-131">Auf dieser Registerkarte können Sie Einstellungen zur Fehlerkonfiguration ändern, die für den Verarbeitungsvorgang verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d9ac1-131">Use this tab to modify settings related to the error configuration for the processing operation.</span></span> <span data-ttu-id="d9ac1-132">Die Registerkarte enthält die folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="d9ac1-132">The tab contains the following options:</span></span>  
  
 <span data-ttu-id="d9ac1-133">**Standardfehler Konfiguration verwenden**</span><span class="sxs-lookup"><span data-stu-id="d9ac1-133">**Use default error configuration**</span></span>  
 <span data-ttu-id="d9ac1-134">Aktivieren Sie diese Option, um für Objekte im Verarbeitungsvorgang die Standardfehlerkonfiguration zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="d9ac1-134">Select to use the default error configuration for objects in the processing operation.</span></span>  
  
 <span data-ttu-id="d9ac1-135">**Benutzerdefinierte Fehlerkonfiguration verwenden**</span><span class="sxs-lookup"><span data-stu-id="d9ac1-135">**Use custom error configuration**</span></span>  
 <span data-ttu-id="d9ac1-136">Aktivieren Sie diese Option, um für Objekte im Verarbeitungsvorgang die Fehlerkonfiguration zu definieren.</span><span class="sxs-lookup"><span data-stu-id="d9ac1-136">Select to define the error configuration for objects in the processing operation.</span></span>  
  
 <span data-ttu-id="d9ac1-137">**Schlüsselfehler Aktion**</span><span class="sxs-lookup"><span data-stu-id="d9ac1-137">**Key error action**</span></span>  
 <span data-ttu-id="d9ac1-138">Wählen Sie eine der folgenden Aktionen aus, die ausgeführt werden soll, wenn während der Verarbeitung ein neuer Schlüssel erkannt wird, der nicht ermittelt werden kann:</span><span class="sxs-lookup"><span data-stu-id="d9ac1-138">Choose one of the following actions that occur when a new key is encountered during processing that cannot be looked up:</span></span>  
  
-   <span data-ttu-id="d9ac1-139">Mit**In unbekanntes Element konvertieren** werden die Informationen für den Datensatz im unbekannten Element zusammengesetzt.</span><span class="sxs-lookup"><span data-stu-id="d9ac1-139">**Convert to unknown** aggregates the information for the record into the unknown member.</span></span>  
  
-   <span data-ttu-id="d9ac1-140">Mit**Datensatz verwerfen** werden die Informationen für den Datensatz von der Verarbeitung mit dem Objekt ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="d9ac1-140">**Discard record** excludes the information for the record from being processed with the object.</span></span>  
  
 <span data-ttu-id="d9ac1-141">**Fehler Anzahl ignorieren**</span><span class="sxs-lookup"><span data-stu-id="d9ac1-141">**Ignore errors count**</span></span>  
 <span data-ttu-id="d9ac1-142">Klicken Sie hier, um bei der Verarbeitung auftretende Fehler grundsätzlich zu ignorieren.</span><span class="sxs-lookup"><span data-stu-id="d9ac1-142">Click to ignore any errors that occur when processing.</span></span>  
  
 <span data-ttu-id="d9ac1-143">**Bei Fehler abbrechen**</span><span class="sxs-lookup"><span data-stu-id="d9ac1-143">**Stop on error**</span></span>  
 <span data-ttu-id="d9ac1-144">Klicken Sie hier, um die Verarbeitung bei Auftreten eines Fehlers zu beenden.</span><span class="sxs-lookup"><span data-stu-id="d9ac1-144">Click to stop processing when errors occur.</span></span> <span data-ttu-id="d9ac1-145">Durch diese Option werden die Optionen **Anzahl von Fehlern** und **Aktion bei Fehler** aktiviert.</span><span class="sxs-lookup"><span data-stu-id="d9ac1-145">This option enables the **Number of errors** and the **On error action** options.</span></span>  
  
 <span data-ttu-id="d9ac1-146">**Anzahl von Fehlern**</span><span class="sxs-lookup"><span data-stu-id="d9ac1-146">**Number of errors**</span></span>  
 <span data-ttu-id="d9ac1-147">Geben Sie die Anzahl der Fehler ein, die ignoriert werden, bevor die Verarbeitung beendet wird.</span><span class="sxs-lookup"><span data-stu-id="d9ac1-147">Type the number of errors that are ignored before processing stops.</span></span>  
  
 <span data-ttu-id="d9ac1-148">**Aktion bei Fehler**</span><span class="sxs-lookup"><span data-stu-id="d9ac1-148">**On error action**</span></span>  
 <span data-ttu-id="d9ac1-149">Wählen Sie eine der folgenden Aktionen aus, die ausgeführt wird, wenn die Anzahl der Fehler den in **Anzahl von Fehlern**angegebenen Wert überschreitet:</span><span class="sxs-lookup"><span data-stu-id="d9ac1-149">Choose one of the following actions to be taken when the number of errors exceeds the value in **Number of errors**:</span></span>  
  
-   <span data-ttu-id="d9ac1-150">Mit**Verarbeitung beenden** wird der Verarbeitungsvorgang beendet.</span><span class="sxs-lookup"><span data-stu-id="d9ac1-150">**Stop processing** ends the processing operation.</span></span>  
  
-   <span data-ttu-id="d9ac1-151">Mit**Protokollierung beenden** werden Protokollierungsfehler beendet, während der Verarbeitungsvorgang weiter ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d9ac1-151">**Stop logging** stops logging errors, but continues the processing operation.</span></span>  
  
 <span data-ttu-id="d9ac1-152">**Schlüssel nicht gefunden**</span><span class="sxs-lookup"><span data-stu-id="d9ac1-152">**Key not found**</span></span>  
 <span data-ttu-id="d9ac1-153">Geben Sie eine der folgenden Aktionen an, die ausgeführt wird, wenn ein Schlüssel bei der Verarbeitung eines Objekts nicht gefunden wird:</span><span class="sxs-lookup"><span data-stu-id="d9ac1-153">Specify one of the following actions to be taken when a key is not found when an object is processed:</span></span>  
  
-   <span data-ttu-id="d9ac1-154">Mit**Fehler ignorieren** wird der Fehler ignoriert.</span><span class="sxs-lookup"><span data-stu-id="d9ac1-154">**Ignore error** ignores the error.</span></span>  
  
-   <span data-ttu-id="d9ac1-155">**Melden und Fortfahren** meldet den Fehler und setzt den Verarbeitungsvorgang fort.</span><span class="sxs-lookup"><span data-stu-id="d9ac1-155">**Report and continue** reports the error and continues the processing operation.</span></span>  
  
-   <span data-ttu-id="d9ac1-156">Mit**Melden und Vorgang beenden** wird der Fehler gemeldet und der Verarbeitungsvorgang beendet.</span><span class="sxs-lookup"><span data-stu-id="d9ac1-156">**Report and stop** reports the error and stops the processing operation.</span></span>  
  
 <span data-ttu-id="d9ac1-157">**Doppelter Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="d9ac1-157">**Duplicate key**</span></span>  
 <span data-ttu-id="d9ac1-158">Geben Sie eine der folgenden Aktionen an, die ausgeführt wird, wenn bei der Verarbeitung eines Objekts ein doppelter Schlüssel gefunden wird:</span><span class="sxs-lookup"><span data-stu-id="d9ac1-158">Specify one of the following actions to be taken if a duplicate key is found when an object is processed:</span></span>  
  
-   <span data-ttu-id="d9ac1-159">Mit**Fehler ignorieren** wird der Fehler ignoriert.</span><span class="sxs-lookup"><span data-stu-id="d9ac1-159">**Ignore error** ignores the error.</span></span>  
  
-   <span data-ttu-id="d9ac1-160">**Melden und Fortfahren** meldet den Fehler und setzt den Verarbeitungsvorgang fort.</span><span class="sxs-lookup"><span data-stu-id="d9ac1-160">**Report and continue** reports the error and continues the processing operation.</span></span>  
  
-   <span data-ttu-id="d9ac1-161">Mit**Melden und Vorgang beenden** wird der Fehler gemeldet und der Verarbeitungsvorgang beendet.</span><span class="sxs-lookup"><span data-stu-id="d9ac1-161">**Report and stop** reports the error and stops the processing operation.</span></span>  
  
 <span data-ttu-id="d9ac1-162">**NULL-Schlüssel in unbekanntes konvertiert**</span><span class="sxs-lookup"><span data-stu-id="d9ac1-162">**Null key converted to unknown**</span></span>  
 <span data-ttu-id="d9ac1-163">Geben Sie eine der folgenden Aktionen an, die ausgeführt wird, wenn dem unbekannten Element bei der Verarbeitung des Objekts ein Elementschlüssel NULL hinzugefügt wird:</span><span class="sxs-lookup"><span data-stu-id="d9ac1-163">Specify one of the following actions to be taken when a null member key is added to the unknown member when an object is processed:</span></span>  
  
-   <span data-ttu-id="d9ac1-164">Mit**Fehler ignorieren** wird der Fehler ignoriert.</span><span class="sxs-lookup"><span data-stu-id="d9ac1-164">**Ignore error** ignores the error.</span></span>  
  
-   <span data-ttu-id="d9ac1-165">**Melden und Fortfahren** meldet den Fehler und setzt den Verarbeitungsvorgang fort.</span><span class="sxs-lookup"><span data-stu-id="d9ac1-165">**Report and continue** reports the error and continues the processing operation.</span></span>  
  
-   <span data-ttu-id="d9ac1-166">Mit**Melden und Vorgang beenden** wird der Fehler gemeldet und der Verarbeitungsvorgang beendet.</span><span class="sxs-lookup"><span data-stu-id="d9ac1-166">**Report and stop** reports the error and stops the processing operation.</span></span>  
  
 <span data-ttu-id="d9ac1-167">**NULL-Schlüssel nicht zulässig**</span><span class="sxs-lookup"><span data-stu-id="d9ac1-167">**Null key not allowed**</span></span>  
 <span data-ttu-id="d9ac1-168">Geben Sie eine der folgenden Aktionen an, die ausgeführt wird, wenn bei der Verarbeitung eines Objekts ein unzulässiger NULL-Schlüssel gefunden wird:</span><span class="sxs-lookup"><span data-stu-id="d9ac1-168">Specify one of the following actions to be taken when a null key is found, but not allowed, when an object is processed:</span></span>  
  
-   <span data-ttu-id="d9ac1-169">Mit**Fehler ignorieren** wird der Fehler ignoriert.</span><span class="sxs-lookup"><span data-stu-id="d9ac1-169">**Ignore error** ignores the error.</span></span>  
  
-   <span data-ttu-id="d9ac1-170">**Melden und Fortfahren** meldet den Fehler und setzt den Verarbeitungsvorgang fort.</span><span class="sxs-lookup"><span data-stu-id="d9ac1-170">**Report and continue** reports the error and continues the processing operation.</span></span>  
  
-   <span data-ttu-id="d9ac1-171">Mit**Melden und Vorgang beenden** wird der Fehler gemeldet und der Verarbeitungsvorgang beendet.</span><span class="sxs-lookup"><span data-stu-id="d9ac1-171">**Report and stop** reports the error and stops the processing operation.</span></span>  
  
 <span data-ttu-id="d9ac1-172">**Fehlerprotokollpfad**</span><span class="sxs-lookup"><span data-stu-id="d9ac1-172">**Error log path**</span></span>  
 <span data-ttu-id="d9ac1-173">Geben Sie den vollständigen Pfad und Dateinamen für die Fehlerprotokolldatei ein.</span><span class="sxs-lookup"><span data-stu-id="d9ac1-173">Type the full path and file name for the error log file.</span></span>  
  
 <span data-ttu-id="d9ac1-174">**Durchsuchen**</span><span class="sxs-lookup"><span data-stu-id="d9ac1-174">**Browse**</span></span>  
 <span data-ttu-id="d9ac1-175">Klicken Sie hier, um das Dialogfeld **Öffnen** zu öffnen und dort den vollständigen Pfad und Dateinamen der Fehlerprotokolldatei auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="d9ac1-175">Click to open the **Open** dialog box and select the full path and file name for the error log file.</span></span>  
  
 <span data-ttu-id="d9ac1-176">**Betroffene Objekte verarbeiten**</span><span class="sxs-lookup"><span data-stu-id="d9ac1-176">**Process affected objects**</span></span>  
 <span data-ttu-id="d9ac1-177">Klicken Sie hier, um die Objekte zu verarbeiten, die eine Abhängigkeit von den im Dialogfeld **Verarbeiten** ausgewählten Objekten aufweisen.</span><span class="sxs-lookup"><span data-stu-id="d9ac1-177">Click to process the objects that have a dependency on the objects selected in the **Process** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9ac1-178">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d9ac1-178">See Also</span></span>  
 <span data-ttu-id="d9ac1-179">[Analysis Services Designer und Dialog Felder &#40;Mehrdimensionale Daten&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="d9ac1-179">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="d9ac1-180">Verarbeiten (Dialog Feld) &#40;Analysis Services-mehrdimensionalen Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="d9ac1-180">Process Dialog Box &#40;Analysis Services - Multidimensional Data&#41;</span></span>](process-dialog-box-analysis-services-multidimensional-data.md)  
  
  
