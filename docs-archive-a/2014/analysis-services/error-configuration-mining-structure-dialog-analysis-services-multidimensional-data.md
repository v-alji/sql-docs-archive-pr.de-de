---
title: Fehler Konfiguration (Dialog Feld "Mining Struktur") (Analysis Services-Mehrdimensionale Daten) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.miningstructuredialog.general.f1
ms.assetid: d9aa028b-bad9-49c7-a81c-c2150e4dd481
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5eb41da36400271a9b058ecf275d26bd22d3ee53
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622926"
---
# <a name="error-configuration-mining-structure-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="5acfb-102">Fehlerkonfiguration (Dialogfeld "Miningstruktur") (Analysis Services &ndash; Mehrdimensionale Daten)</span><span class="sxs-lookup"><span data-stu-id="5acfb-102">Error Configuration (Mining Structure Dialog Box) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="5acfb-103">Auf der Seite **Fehlerkonfiguration** im Dialogfeld **Miningstruktureigenschaften** können Sie in **SQL Server Management Studio** die Eigenschaften der Fehlerkonfiguration einer Miningstruktur in einer [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Datenbank festlegen.</span><span class="sxs-lookup"><span data-stu-id="5acfb-103">Use the **Error Configuration** page of the **Mining Structure Properties** dialog box in **SQL Server Management Studio** to set the error configuration properties of a mining structure in an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
## <a name="options"></a><span data-ttu-id="5acfb-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="5acfb-104">Options</span></span>  
 <span data-ttu-id="5acfb-105">**Standardfehler Konfiguration verwenden**</span><span class="sxs-lookup"><span data-stu-id="5acfb-105">**Use default error configuration**</span></span>  
 <span data-ttu-id="5acfb-106">Aktivieren Sie diese Option, um für Objekte im Verarbeitungsvorgang die Standardfehlerkonfiguration zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="5acfb-106">Select to use the default error configuration for objects in the processing operation.</span></span>  
  
 <span data-ttu-id="5acfb-107">**Schlüsselfehler Aktion**</span><span class="sxs-lookup"><span data-stu-id="5acfb-107">**Key error action**</span></span>  
 <span data-ttu-id="5acfb-108">Wählen Sie eine der folgenden Aktionen aus, die ausgeführt werden soll, wenn während der Verarbeitung ein neuer Schlüssel erkannt wird, der nicht ermittelt werden kann:</span><span class="sxs-lookup"><span data-stu-id="5acfb-108">Choose one of the following actions that occur when a new key is encountered during processing that cannot be looked up:</span></span>  
  
-   <span data-ttu-id="5acfb-109">Mit**In unbekanntes Element konvertieren** werden die Informationen für den Datensatz im unbekannten Element zusammengesetzt.</span><span class="sxs-lookup"><span data-stu-id="5acfb-109">**Convert to unknown** aggregates the information for the record into the unknown member.</span></span>  
  
-   <span data-ttu-id="5acfb-110">Mit**Datensatz verwerfen** werden die Informationen für den Datensatz von der Verarbeitung mit dem Objekt ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="5acfb-110">**Discard record** excludes the information for the record from being processed with the object.</span></span>  
  
 <span data-ttu-id="5acfb-111">**Fehler Anzahl ignorieren**</span><span class="sxs-lookup"><span data-stu-id="5acfb-111">**Ignore errors count**</span></span>  
 <span data-ttu-id="5acfb-112">Klicken Sie hier, um bei der Verarbeitung auftretende Fehler grundsätzlich zu ignorieren.</span><span class="sxs-lookup"><span data-stu-id="5acfb-112">Click to ignore any errors that occur when processing.</span></span>  
  
 <span data-ttu-id="5acfb-113">**Bei Fehler abbrechen**</span><span class="sxs-lookup"><span data-stu-id="5acfb-113">**Stop on error**</span></span>  
 <span data-ttu-id="5acfb-114">Klicken Sie hier, um die Verarbeitung bei Auftreten eines Fehlers zu beenden.</span><span class="sxs-lookup"><span data-stu-id="5acfb-114">Click to stop processing when errors occur.</span></span> <span data-ttu-id="5acfb-115">Durch diese Option werden die Optionen **Anzahl von Fehlern** und **Aktion bei Fehler** aktiviert.</span><span class="sxs-lookup"><span data-stu-id="5acfb-115">This option enables the **Number of errors** and the **On error action** options.</span></span>  
  
 <span data-ttu-id="5acfb-116">**Anzahl von Fehlern**</span><span class="sxs-lookup"><span data-stu-id="5acfb-116">**Number of errors**</span></span>  
 <span data-ttu-id="5acfb-117">Geben Sie die Anzahl der Fehler ein, die ignoriert werden, bevor die Verarbeitung beendet wird.</span><span class="sxs-lookup"><span data-stu-id="5acfb-117">Type the number of errors that are ignored before processing stops.</span></span>  
  
 <span data-ttu-id="5acfb-118">**Aktion bei Fehler**</span><span class="sxs-lookup"><span data-stu-id="5acfb-118">**On error action**</span></span>  
 <span data-ttu-id="5acfb-119">Wählen Sie eine der folgenden Aktionen aus, die ausgeführt wird, wenn die Anzahl der Fehler den in **Anzahl von Fehlern**angegebenen Wert überschreitet:</span><span class="sxs-lookup"><span data-stu-id="5acfb-119">Choose one of the following actions to be taken when the number of errors exceeds the value in **Number of errors**:</span></span>  
  
-   <span data-ttu-id="5acfb-120">Mit**Verarbeitung beenden** wird der Verarbeitungsvorgang beendet.</span><span class="sxs-lookup"><span data-stu-id="5acfb-120">**Stop processing** ends the processing operation.</span></span>  
  
-   <span data-ttu-id="5acfb-121">Mit**Protokollierung beenden** werden Protokollierungsfehler beendet, während der Verarbeitungsvorgang weiter ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5acfb-121">**Stop logging** stops logging errors, but continues the processing operation.</span></span>  
  
 <span data-ttu-id="5acfb-122">**Schlüssel nicht gefunden**</span><span class="sxs-lookup"><span data-stu-id="5acfb-122">**Key not found**</span></span>  
 <span data-ttu-id="5acfb-123">Geben Sie eine der folgenden Aktionen an, die ausgeführt wird, wenn ein Schlüssel bei der Verarbeitung eines Objekts nicht gefunden wird:</span><span class="sxs-lookup"><span data-stu-id="5acfb-123">Specify one of the following actions to be taken when a key is not found when an object is processed:</span></span>  
  
-   <span data-ttu-id="5acfb-124">**Fehler ignorieren** ignoriert den Fehler.</span><span class="sxs-lookup"><span data-stu-id="5acfb-124">**Ignore error** ignores the error</span></span>  
  
-   <span data-ttu-id="5acfb-125">Mit**Melden und Vorgang fortsetzen** wird der Fehler gemeldet und der Verarbeitungsvorgang fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="5acfb-125">**Report and continue** reports the error and continues the processing operation</span></span>  
  
-   <span data-ttu-id="5acfb-126">Mit**Melden und Vorgang beenden** wird der Fehler gemeldet und der Verarbeitungsvorgang beendet.</span><span class="sxs-lookup"><span data-stu-id="5acfb-126">**Report and stop** reports the error and stops the processing operation.</span></span>  
  
 <span data-ttu-id="5acfb-127">**Doppelter Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="5acfb-127">**Duplicate key**</span></span>  
 <span data-ttu-id="5acfb-128">Geben Sie eine der folgenden Aktionen an, die ausgeführt wird, wenn bei der Verarbeitung eines Objekts ein doppelter Schlüssel gefunden wird:</span><span class="sxs-lookup"><span data-stu-id="5acfb-128">Specify one of the following actions to be taken if a duplicate key is found when an object is processed:</span></span>  
  
-   <span data-ttu-id="5acfb-129">**Fehler ignorieren** ignoriert den Fehler.</span><span class="sxs-lookup"><span data-stu-id="5acfb-129">**Ignore error** ignores the error</span></span>  
  
-   <span data-ttu-id="5acfb-130">Mit**Melden und Vorgang fortsetzen** wird der Fehler gemeldet und der Verarbeitungsvorgang fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="5acfb-130">**Report and continue** reports the error and continues the processing operation</span></span>  
  
-   <span data-ttu-id="5acfb-131">Mit**Melden und Vorgang beenden** wird der Fehler gemeldet und der Verarbeitungsvorgang beendet.</span><span class="sxs-lookup"><span data-stu-id="5acfb-131">**Report and stop** reports the error and stops the processing operation.</span></span>  
  
 <span data-ttu-id="5acfb-132">**NULL-Schlüssel in unbekanntes konvertiert**</span><span class="sxs-lookup"><span data-stu-id="5acfb-132">**Null key converted to unknown**</span></span>  
 <span data-ttu-id="5acfb-133">Geben Sie eine der folgenden Aktionen an, die ausgeführt wird, wenn dem unbekannten Element bei der Verarbeitung des Objekts ein Elementschlüssel NULL hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="5acfb-133">Specify one of the following actions to be taken when a null member key is added to the unknown member when an object is processed.</span></span>  
  
-   <span data-ttu-id="5acfb-134">**Fehler ignorieren** ignoriert den Fehler.</span><span class="sxs-lookup"><span data-stu-id="5acfb-134">**Ignore error** ignores the error</span></span>  
  
-   <span data-ttu-id="5acfb-135">Mit**Melden und Vorgang fortsetzen** wird der Fehler gemeldet und der Verarbeitungsvorgang fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="5acfb-135">**Report and continue** reports the error and continues the processing operation</span></span>  
  
-   <span data-ttu-id="5acfb-136">Mit**Melden und Vorgang beenden** wird der Fehler gemeldet und der Verarbeitungsvorgang beendet.</span><span class="sxs-lookup"><span data-stu-id="5acfb-136">**Report and stop** reports the error and stops the processing operation.</span></span>  
  
 <span data-ttu-id="5acfb-137">**NULL-Schlüssel nicht zulässig**</span><span class="sxs-lookup"><span data-stu-id="5acfb-137">**Null key not allowed**</span></span>  
 <span data-ttu-id="5acfb-138">Geben Sie eine der folgenden Aktionen an, die ausgeführt wird, wenn bei der Verarbeitung eines Objekts ein unzulässiger NULL-Schlüssel gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="5acfb-138">Specify one of the following actions to be taken when a null key is found, but not allowed, when an object is processed.</span></span>  
  
-   <span data-ttu-id="5acfb-139">**Fehler ignorieren** ignoriert den Fehler.</span><span class="sxs-lookup"><span data-stu-id="5acfb-139">**Ignore error** ignores the error</span></span>  
  
-   <span data-ttu-id="5acfb-140">Mit**Melden und Vorgang fortsetzen** wird der Fehler gemeldet und der Verarbeitungsvorgang fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="5acfb-140">**Report and continue** reports the error and continues the processing operation</span></span>  
  
-   <span data-ttu-id="5acfb-141">Mit**Melden und Vorgang beenden** wird der Fehler gemeldet und der Verarbeitungsvorgang beendet.</span><span class="sxs-lookup"><span data-stu-id="5acfb-141">**Report and stop** reports the error and stops the processing operation.</span></span>  
  
 <span data-ttu-id="5acfb-142">**Fehlerprotokollpfad**</span><span class="sxs-lookup"><span data-stu-id="5acfb-142">**Error log path**</span></span>  
 <span data-ttu-id="5acfb-143">Geben Sie den vollständigen Pfad und Dateinamen für die Fehlerprotokolldatei ein.</span><span class="sxs-lookup"><span data-stu-id="5acfb-143">Type the full path and file name for the error log file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5acfb-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5acfb-144">See Also</span></span>  
 <span data-ttu-id="5acfb-145">[Mining Struktur Eigenschaften-Dialog &#40;Analysis Services-Data Mining-&#41;](mining-structure-properties-dialog-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="5acfb-145">[Mining Structure Properties Dialog &#40;Analysis Services - Data Mining&#41;](mining-structure-properties-dialog-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="5acfb-146">Das Dialog Feld allgemeine &#40;Mining Struktur&#41; &#40;Analysis Services Data Mining-&#41;</span><span class="sxs-lookup"><span data-stu-id="5acfb-146">General &#40;Mining Structure Dialog Box&#41; &#40;Analysis Services - Data Mining&#41;</span></span>](general-mining-structure-dialog-box-analysis-services-data-mining.md)  
  
  
