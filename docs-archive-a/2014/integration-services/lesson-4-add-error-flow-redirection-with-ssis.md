---
title: 'Lektion 4: Hinzufügen der Fehler Fluss Umleitung | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 0c8dbda2-75e3-4278-9b4e-dcd220c92522
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5b1d1ff9abf59a6288d1b693fce5a6fb707a129b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724802"
---
# <a name="lesson-4-adding-error-flow-redirection"></a><span data-ttu-id="58598-102">Lektion 4: Hinzufügen der Fehlerflussumleitung</span><span class="sxs-lookup"><span data-stu-id="58598-102">Lesson 4: Adding Error Flow Redirection</span></span>
  <span data-ttu-id="58598-103">Um Fehler zu behandeln, die im Transformationsprozess auftreten können, [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] bietet Ihnen die Möglichkeit, für einzelne Komponenten und pro Spalte zu entscheiden, wie Daten behandelt werden, die nicht transformiert werden können.</span><span class="sxs-lookup"><span data-stu-id="58598-103">To handle errors that may occur in the transformation process, [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] gives you the ability to decide on a per component and per column basis how to handle data that cannot be transformed.</span></span> <span data-ttu-id="58598-104">Sie können einen Fehler in bestimmten Spalten ignorieren, die gesamte fehlgeschlagene Zeile umleiten, oder die gesamte Komponente als fehlerhaft behandeln.</span><span class="sxs-lookup"><span data-stu-id="58598-104">You can choose to ignore a failure in certain columns, redirect the entire failed row, or just fail the component.</span></span> <span data-ttu-id="58598-105">Standardmäßig sind alle Komponenten in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] so konfiguriert, dass sie bei Fehlern fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="58598-105">By default, all components in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] are configured to fail when errors occur.</span></span> <span data-ttu-id="58598-106">Das Behandeln einer Komponente als fehlerhaft verursacht wiederum die Behandlung des Pakets als fehlerhaft, und die gesamte nachfolgende Verarbeitung wird beendet.</span><span class="sxs-lookup"><span data-stu-id="58598-106">Failing a component, in turn, causes the package to fail and all subsequent processing to stop.</span></span>  
  
 <span data-ttu-id="58598-107">Anstatt das Beenden durch Fehler der Paketausführung zuzulassen, ist es eine bewährte Vorgehensweise, potenzielle Verarbeitungsfehler zu konfigurieren und zu handhaben, wenn sie innerhalb der Transformation auftreten.</span><span class="sxs-lookup"><span data-stu-id="58598-107">Instead of letting failures stop package execution, it is good practice to configure and handle potential processing errors as they occur within the transformation.</span></span> <span data-ttu-id="58598-108">Während das Ignorieren von Fehlern möglich ist, um die erfolgreiche Ausführung Ihrer Pakete sicherzustellen, ist es oft besser, die fehlgeschlagene Zeile zu einem anderen Verarbeitungspfad umzuleiten, wo die Daten und Fehler bestehen bleiben sowie zu einem späteren Zeitpunkt untersucht und erneut verarbeitet werden können.</span><span class="sxs-lookup"><span data-stu-id="58598-108">While you might choose to ignore failures to ensure your package runs successfully, it is often better to redirect the failed row to another processing path where the data and the error can be persisted, examined and reprocessed at a later time.</span></span>  
  
 <span data-ttu-id="58598-109">In dieser Lektion erstellen Sie eine Kopie des Pakets, das Sie in [Lesson 3: Adding Logging](lesson-3-add-logging-with-ssis.md)entwickelt haben.</span><span class="sxs-lookup"><span data-stu-id="58598-109">In this lesson, you will create a copy of the package that you developed in [Lesson 3: Adding Logging](lesson-3-add-logging-with-ssis.md).</span></span> <span data-ttu-id="58598-110">Beim Arbeiten mit diesem neuen Paket werden Sie eine beschädigte Version einer der Beispieldatendateien erstellen.</span><span class="sxs-lookup"><span data-stu-id="58598-110">Working with this new package, you will create a corrupted version of one of the sample data files.</span></span> <span data-ttu-id="58598-111">Durch die beschädigte Datei wird beim Ausführen des Pakets ein Verarbeitungsfehler erzwungen.</span><span class="sxs-lookup"><span data-stu-id="58598-111">The corrupted file will force a processing error to occur when you run the package.</span></span>  
  
 <span data-ttu-id="58598-112">Zur Behandlung von Fehlerdaten fügen Sie ein Flatfileziel hinzu, und konfigurieren Sie es. Das Flatfileziel schreibt alle Zeilen, die keinen Suchwert in der Lookup Currency Key-Transformation finden, in eine Datei.</span><span class="sxs-lookup"><span data-stu-id="58598-112">To handle the error data, you will add and configure a Flat File destination that will write any rows that fail to locate a lookup value in the Lookup Currency Key transformation to a file.</span></span>  
  
 <span data-ttu-id="58598-113">Bevor die Fehlerdaten in die Datei geschrieben werden, greift eine von Ihnen eingefügte Skriptkomponente ein, die mithilfe eines Skripts Fehlerbeschreibungen abruft.</span><span class="sxs-lookup"><span data-stu-id="58598-113">Before the error data is written to the file, you will include a Script component that uses script to get error descriptions.</span></span> <span data-ttu-id="58598-114">Sie konfigurieren dann die Lookup Currency Key-Transformation erneut, um alle Daten, die nicht verarbeitet werden konnten, an die Skripttransformation umzuleiten.</span><span class="sxs-lookup"><span data-stu-id="58598-114">You will then reconfigure the Lookup Currency Key transformation to redirect any data that could not be processed to the Script transformation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="58598-115">Dieses Lernprogramm erfordert die **AdventureWorksDW2012** -Beispieldatenbank.</span><span class="sxs-lookup"><span data-stu-id="58598-115">This tutorial requires the **AdventureWorksDW2012** sample database.</span></span> <span data-ttu-id="58598-116">Weitere Informationen zum Installieren und Bereitstellen von **AdventureWorksDW2012**finden Sie unter [Reporting Services Produktbeispiel-Projekt auf CodePlex](https://go.microsoft.com/fwlink/p/?LinkId=526910).</span><span class="sxs-lookup"><span data-stu-id="58598-116">For more information about how to install and deploy **AdventureWorksDW2012**, see [Reporting Services Product Samples Project on CodePlex](https://go.microsoft.com/fwlink/p/?LinkId=526910).</span></span>  
  
## <a name="tasks-in-lesson"></a><span data-ttu-id="58598-117">Aufgaben in der Lektion</span><span class="sxs-lookup"><span data-stu-id="58598-117">Tasks in Lesson</span></span>  
 <span data-ttu-id="58598-118">Diese Lektion enthält die folgenden Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="58598-118">This lesson contains the following tasks:</span></span>  
  
-   [<span data-ttu-id="58598-119">Schritt 1: Kopieren des Pakets aus Lektion 3</span><span class="sxs-lookup"><span data-stu-id="58598-119">Step 1: Copying the Lesson 3 Package</span></span>](lesson-4-1-copying-the-lesson-3-package.md)  
  
-   [<span data-ttu-id="58598-120">Schritt 2: Erstellen einer beschädigten Datei</span><span class="sxs-lookup"><span data-stu-id="58598-120">Step 2: Creating a Corrupted File</span></span>](lesson-4-2-creating-a-corrupted-file.md)  
  
-   [<span data-ttu-id="58598-121">Schritt 3: Hinzufügen der Fehlerflussumleitung</span><span class="sxs-lookup"><span data-stu-id="58598-121">Step 3: Adding Error Flow Redirection</span></span>](lesson-4-3-adding-error-flow-redirection.md)  
  
-   [<span data-ttu-id="58598-122">Schritt 4: Hinzufügen eines Flatfileziels</span><span class="sxs-lookup"><span data-stu-id="58598-122">Step 4: Adding a Flat File Destination</span></span>](lesson-4-4-adding-a-flat-file-destination.md)  
  
-   [<span data-ttu-id="58598-123">Schritt 5: Testen des Tutorialpakets aus Lektion 4</span><span class="sxs-lookup"><span data-stu-id="58598-123">Step 5: Testing the Lesson 4 Tutorial Package</span></span>](lesson-4-5-testing-the-lesson-4-tutorial-package.md)  
  
## <a name="start-the-lesson"></a><span data-ttu-id="58598-124">Lektion beginnen</span><span class="sxs-lookup"><span data-stu-id="58598-124">Start the Lesson</span></span>  
 [<span data-ttu-id="58598-125">Schritt 1: Kopieren des Pakets aus Lektion 3</span><span class="sxs-lookup"><span data-stu-id="58598-125">Step 1: Copying the Lesson 3 Package</span></span>](lesson-4-1-copying-the-lesson-3-package.md)  
  
  
