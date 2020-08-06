---
title: 'Schritt 2: Erstellen einer beschädigten Datei | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: cd0b18dc-66c3-4d88-86ef-8e40cb660fae
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0dd5fbe942774192881489e9ea430672f9da5083
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617175"
---
# <a name="step-2-creating-a-corrupted-file"></a><span data-ttu-id="7f0c8-102">Schritt 2: Erstellen einer beschädigten Datei</span><span class="sxs-lookup"><span data-stu-id="7f0c8-102">Step 2: Creating a Corrupted File</span></span>
  <span data-ttu-id="7f0c8-103">Um die Konfiguration und die Behandlung von Transformationsfehlern zu demonstrieren, müssen Sie eine Beispielflatfile erstellen, die beim Verarbeiten für eine Komponente einen Fehler erzeugt.</span><span class="sxs-lookup"><span data-stu-id="7f0c8-103">In order to demonstrate the configuration and handling of transformation errors, you will have to create a sample flat file that when processed causes a component to fail.</span></span>  
  
 <span data-ttu-id="7f0c8-104">In dieser Aufgabe erstellen Sie eine Kopie einer vorhandenen Beispielflatfile.</span><span class="sxs-lookup"><span data-stu-id="7f0c8-104">In this task, you will create a copy of an existing sample flat file.</span></span> <span data-ttu-id="7f0c8-105">Anschließend öffnen Sie die Datei im Editor und bearbeiten die **CurrencyID** -Spalte, um sicherzustellen, dass von ihr keine Übereinstimmung während der Transformationssuche produziert wird.</span><span class="sxs-lookup"><span data-stu-id="7f0c8-105">You will then open the file in Notepad and edit the **CurrencyID** column to ensure that it will fail to produce a match during the transformations lookup.</span></span> <span data-ttu-id="7f0c8-106">Wenn die neue Datei verarbeitet wird, erzeugt der Suchfehler einen Fehler der Currency Key Lookup-Transformation, sodass auch der Rest des Pakets fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="7f0c8-106">When the new file is processed, the lookup failure will cause the Currency Key Lookup transformation to fail and therefore fail the rest of the package.</span></span> <span data-ttu-id="7f0c8-107">Nach dem Erstellen der beschädigten Beispieldatei führen Sie das Paket aus, um den vom Paket verursachten Fehler anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="7f0c8-107">After you have created the corrupted sample file, you will run the package to view the package failure.</span></span>  
  
### <a name="to-create-a-corrupted-sample-flat-file"></a><span data-ttu-id="7f0c8-108">So erstellen Sie eine beschädigte Beispielflatfile</span><span class="sxs-lookup"><span data-stu-id="7f0c8-108">To create a corrupted sample flat file</span></span>  
  
1.  <span data-ttu-id="7f0c8-109">Öffnen Sie in Editor oder einem anderen Texteditor die Datei Currency_VEB.txt.</span><span class="sxs-lookup"><span data-stu-id="7f0c8-109">In Notepad or any other text editor, open the Currency_VEB.txt file.</span></span>  
  
     <span data-ttu-id="7f0c8-110">Die Beispieldaten sind in den SSIS-Lektionspaketen enthalten.</span><span class="sxs-lookup"><span data-stu-id="7f0c8-110">The sample data is included with the SSIS Lesson packages.</span></span> <span data-ttu-id="7f0c8-111">Um die Beispieldaten und die Lektionspakete herunterzuladen, gehen Sie wie folgt vor.</span><span class="sxs-lookup"><span data-stu-id="7f0c8-111">To download the sample data and the lesson packages, do the following.</span></span>  
  
    1.  <span data-ttu-id="7f0c8-112">Navigieren Sie zu [Integration Services Product Samples](https://go.microsoft.com/fwlink/?LinkID=267527).</span><span class="sxs-lookup"><span data-stu-id="7f0c8-112">Navigate to [Integration Services Product Samples](https://go.microsoft.com/fwlink/?LinkID=267527).</span></span>  
  
    2.  <span data-ttu-id="7f0c8-113">Klicken Sie auf die Registerkarte **DOWNLOADS** .</span><span class="sxs-lookup"><span data-stu-id="7f0c8-113">Click the **DOWNLOADS** tab.</span></span>  
  
    3.  <span data-ttu-id="7f0c8-114">Klicken Sie auf die Datei SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip.</span><span class="sxs-lookup"><span data-stu-id="7f0c8-114">Click the SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip file.</span></span>  
  
2.  <span data-ttu-id="7f0c8-115">Verwenden Sie die Funktion "suchen und ersetzen" des Text-Editors, um alle Instanzen von zu suchen `VEB` und diese durch zu ersetzen `BAD` .</span><span class="sxs-lookup"><span data-stu-id="7f0c8-115">Use the text editor's find and replace feature to find all instances of `VEB` and replace them with `BAD`.</span></span>  
  
3.  <span data-ttu-id="7f0c8-116">Speichern Sie im gleichen Ordner wie die anderen Beispiel Datendateien die geänderte Datei unter `Currency_BAD.txt` .</span><span class="sxs-lookup"><span data-stu-id="7f0c8-116">In the same folder as the other sample data files, save the modified file as `Currency_BAD.txt`.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="7f0c8-117">Stellen Sie sicher, dass `Currency_BAD.txt` in demselben Ordner wie die anderen Beispiel Datendateien gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="7f0c8-117">Make sure that `Currency_BAD.txt` is saved the same folder as the other sample data files.</span></span>  
  
4.  <span data-ttu-id="7f0c8-118">Schließen Sie den Texteditor.</span><span class="sxs-lookup"><span data-stu-id="7f0c8-118">Close your text editor.</span></span>  
  
### <a name="to-verify-that-an-error-will-occur-during-run-time"></a><span data-ttu-id="7f0c8-119">So überprüfen Sie das Auftreten eines Fehlers während der Laufzeit</span><span class="sxs-lookup"><span data-stu-id="7f0c8-119">To verify that an error will occur during run time</span></span>  
  
1.  <span data-ttu-id="7f0c8-120">Klicken Sie im Menü **Debuggen** auf die Option **Debuggen starten**.</span><span class="sxs-lookup"><span data-stu-id="7f0c8-120">On the **Debug** menu, click **Start Debugging**.</span></span>  
  
     <span data-ttu-id="7f0c8-121">In der dritten Iteration des Datenflusses wird von der Lookup Currency Key-Transformation versucht, die Datei Currency_BAD.txt zu verarbeiten, und die Transformation erzeugt einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="7f0c8-121">On the third iteration of the data flow, the Lookup Currency Key transformation tries to process the Currency_BAD.txt file, and the transformation will fail.</span></span> <span data-ttu-id="7f0c8-122">Der Fehler der Transformation erzeugt einen Fehler des gesamten Pakets.</span><span class="sxs-lookup"><span data-stu-id="7f0c8-122">The failure of the transformation will cause the whole package to fail.</span></span>  
  
2.  <span data-ttu-id="7f0c8-123">Klicken Sie im Menü **Debuggen** auf die Option **Debuggen beenden**.</span><span class="sxs-lookup"><span data-stu-id="7f0c8-123">On the **Debug** menu, click **Stop Debugging**.</span></span>  
  
3.  <span data-ttu-id="7f0c8-124">Klicken Sie auf der Entwurfsoberfläche auf die Registerkarte **Ausführungsergebnisse** .</span><span class="sxs-lookup"><span data-stu-id="7f0c8-124">On the design surface, click the **Execution Results** tab.</span></span>  
  
4.  <span data-ttu-id="7f0c8-125">Durchsuchen Sie das Protokoll und überprüfen Sie, ob der folgende nicht behandelte Fehler aufgetreten ist:</span><span class="sxs-lookup"><span data-stu-id="7f0c8-125">Browse through the log and verify that the following unhandled error occurred:</span></span>  
  
     `[Lookup Currency Key[27]] Error: Row yielded no match during lookup.`  
  
    > [!NOTE]  
    >  <span data-ttu-id="7f0c8-126">Die Zahl 27 ist die ID der Komponente.</span><span class="sxs-lookup"><span data-stu-id="7f0c8-126">The number 27 is the ID of the component.</span></span> <span data-ttu-id="7f0c8-127">Dieser Wert wird zugewiesen, wenn Sie den Datenfluss erstellen. Der Wert in Ihrem Paket kann sich von diesem Wert unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="7f0c8-127">This value is assigned when you build the data flow, and the value in your package may be different.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="7f0c8-128">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="7f0c8-128">Next Steps</span></span>  
 [<span data-ttu-id="7f0c8-129">Schritt 3: Hinzufügen der Fehlerflussumleitung</span><span class="sxs-lookup"><span data-stu-id="7f0c8-129">Step 3: Adding Error Flow Redirection</span></span>](lesson-4-3-adding-error-flow-redirection.md)  
  
  
