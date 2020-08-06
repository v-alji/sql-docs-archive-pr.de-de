---
title: 'Schritt 5: Testen des Tutorialpakets aus Lektion 4 | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5f18df92-0248-4858-836b-c8b02f0e0439
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4a897f99bf68805e4e66c3b6bbe818b312077fb4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720233"
---
# <a name="step-5-testing-the-lesson-4-tutorial-package"></a><span data-ttu-id="8a03d-102">Schritt 5: Testen des Tutorialpakets aus Lektion 4</span><span class="sxs-lookup"><span data-stu-id="8a03d-102">Step 5: Testing the Lesson 4 Tutorial Package</span></span>
  <span data-ttu-id="8a03d-103">Die beschädigte Datei Currency_BAD.txt kann in der Currency Key-Transformation keine Übereinstimmung generieren.</span><span class="sxs-lookup"><span data-stu-id="8a03d-103">At run time, the corrupted file, Currency_BAD.txt, will fail to generate a match within the Currency Key Lookup transformation.</span></span> <span data-ttu-id="8a03d-104">Weil die Fehlerausgabe von Currency Key Lookup jetzt so konfiguriert wurde, dass fehlerhafte Zeilen zum neuen Ziel für fehlerhafte Dateien umgeleitet werden, erzeugt die Komponente keinen Fehler, und das Paket wird erfolgreich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="8a03d-104">Because the error output of Currency Key Lookup has now been configured to redirect failed rows to the new Failed Rows destination, the component does not fail, and the package runs successfully.</span></span> <span data-ttu-id="8a03d-105">Alle fehlgeschlagenen Zeilen werden in die Datei ErrorOutput.txt geschrieben.</span><span class="sxs-lookup"><span data-stu-id="8a03d-105">All failed error rows are written to ErrorOutput.txt.</span></span>  
  
 <span data-ttu-id="8a03d-106">In dieser Aufgabe testen Sie die überarbeitete Fehlerausgabekonfiguration, indem Sie das Paket ausführen.</span><span class="sxs-lookup"><span data-stu-id="8a03d-106">In this task, you will test the revised error output configuration by running the package.</span></span> <span data-ttu-id="8a03d-107">Bei einer erfolgreichen Paketausführung zeigen Sie dann den Inhalt der Datei ErrorOutput.txt an.</span><span class="sxs-lookup"><span data-stu-id="8a03d-107">Upon successful package execution, you will then view the contents of the ErrorOutput.txt file.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8a03d-108">Wenn Sie keine Fehlerzeilen in der Datei ErrorOutput.txt anhäufen möchten, sollten Sie den Dateiinhalt zwischen Paketausführungen manuell löschen.</span><span class="sxs-lookup"><span data-stu-id="8a03d-108">If you do not want to accumulate error rows in the ErrorOutput.txt file, you should manually delete the file content between package runs.</span></span>  
  
## <a name="checking-the-package-layout"></a><span data-ttu-id="8a03d-109">Überprüfen des Paketlayouts</span><span class="sxs-lookup"><span data-stu-id="8a03d-109">Checking the Package layout</span></span>  
 <span data-ttu-id="8a03d-110">Bevor Sie das Paket testen, sollten Sie überprüfen, ob Ablaufsteuerung und Datenfluss im Paket aus Lektion 4 die in den folgenden Diagrammen gezeigten Objekte enthalten.</span><span class="sxs-lookup"><span data-stu-id="8a03d-110">Before you test the package you should verify that the control flow and the data flow in the Lesson 4 package contain the objects shown in the following diagrams.</span></span> <span data-ttu-id="8a03d-111">Die Ablaufsteuerung sollte mit der Ablaufsteuerung in den Lektionen 2 bis 4 übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="8a03d-111">The control flow should be identical to the control flow in lessons 2 - 4.</span></span>  
  
 <span data-ttu-id="8a03d-112">**Ablaufsteuerung**</span><span class="sxs-lookup"><span data-stu-id="8a03d-112">**Control Flow**</span></span>  
  
 <span data-ttu-id="8a03d-113">![Ablaufsteuerung im Paket](../../2014/tutorials/media/task4lesson2control.gif "Ablaufsteuerung im Paket")</span><span class="sxs-lookup"><span data-stu-id="8a03d-113">![Control flow in package](../../2014/tutorials/media/task4lesson2control.gif "Control flow in package")</span></span>  
  
 <span data-ttu-id="8a03d-114">**Datenfluss**</span><span class="sxs-lookup"><span data-stu-id="8a03d-114">**Data Flow**</span></span>  
  
 <span data-ttu-id="8a03d-115">![Datenfluss im Paket](../../2014/tutorials/media/task5lesson5data.gif "Datenfluss im Paket")</span><span class="sxs-lookup"><span data-stu-id="8a03d-115">![Data flow in package](../../2014/tutorials/media/task5lesson5data.gif "Data flow in package")</span></span>  
  
### <a name="to-run-the-lesson-4-tutorial-package"></a><span data-ttu-id="8a03d-116">So führen Sie das Lernprogrammpaket aus Lektion 4 aus</span><span class="sxs-lookup"><span data-stu-id="8a03d-116">To run the Lesson 4 tutorial package</span></span>  
  
1.  <span data-ttu-id="8a03d-117">Klicken Sie im Menü **Debuggen** auf die Option **Debuggen starten**.</span><span class="sxs-lookup"><span data-stu-id="8a03d-117">On the **Debug** menu, click **Start Debugging**.</span></span>  
  
2.  <span data-ttu-id="8a03d-118">Klicken Sie nach Ausführen des Pakets im Menü **Debuggen** auf **Debuggen beenden**.</span><span class="sxs-lookup"><span data-stu-id="8a03d-118">After the package has completed running, on the **Debug** menu, click **Stop Debugging**.</span></span>  
  
### <a name="to-verify-the-contents-of-the-erroroutputtxt-file"></a><span data-ttu-id="8a03d-119">So überprüfen Sie den Inhalt der Datei ErrorOutput.txt</span><span class="sxs-lookup"><span data-stu-id="8a03d-119">To verify the contents of the ErrorOutput.txt file</span></span>  
  
-   <span data-ttu-id="8a03d-120">Öffnen Sie in Editor oder einem anderen Texteditor die Datei ErrorOutput.txt.</span><span class="sxs-lookup"><span data-stu-id="8a03d-120">In Notepad or any other text editor, open the ErrorOutput.txt file.</span></span> <span data-ttu-id="8a03d-121">Die standardmäßige Spaltenreihenfolge ist: AverageRate, CurrencyID, CurrencyDate, EndOfDateRate, ErrorCode, ErrorColumn und ErrorDescription.</span><span class="sxs-lookup"><span data-stu-id="8a03d-121">The default column order is: AverageRate, CurrencyID, CurrencyDate, EndOfDateRate, ErrorCode, ErrorColumn, ErrorDescription.</span></span>  
  
     <span data-ttu-id="8a03d-122">Beachten Sie, dass alle in der Datei enthaltenen Zeilen den nicht übereinstimmenden CurrencyID-Wert BAD, den ErrorCode-Wert -1071607778, den ErrorColumn-Wert 0 und den ErrorDescription-Wert "Die Zeile ergab bei der Suche keine Übereinstimmung" enthalten.</span><span class="sxs-lookup"><span data-stu-id="8a03d-122">Notice that all the rows in the file contain the unmatched CurrencyID value of BAD, the ErrorCode value of -1071607778, the ErrorColumn value of 0, and the ErrorDescription value "Row yielded no match during lookup".</span></span> <span data-ttu-id="8a03d-123">Der Wert für ErrorColumn ist auf 0 festgelegt, da der Fehler nicht spaltenspezifisch ist.</span><span class="sxs-lookup"><span data-stu-id="8a03d-123">The value of the ErrorColumn is set to 0 because the error is not column specific.</span></span> <span data-ttu-id="8a03d-124">Es ist der Suchvorgang, der fehlerhaft ist.</span><span class="sxs-lookup"><span data-stu-id="8a03d-124">It is the lookup operation that failed.</span></span> <span data-ttu-id="8a03d-125">.</span><span class="sxs-lookup"><span data-stu-id="8a03d-125">.</span></span>  
  
  
