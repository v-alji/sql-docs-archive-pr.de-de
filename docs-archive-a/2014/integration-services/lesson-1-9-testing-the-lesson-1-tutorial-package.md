---
title: 'Schritt 9: Testen des Tutorialpakets aus Lektion 1 | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 9aee7acf-797b-46f2-830d-80ab64a9f0b6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: dff1132489c1683430b1003e88f5037664b11983
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618119"
---
# <a name="step-9-testing-the-lesson-1-tutorial-package"></a><span data-ttu-id="e5cf5-102">Schritt 9: Testen des Tutorialpakets aus Lektion 1</span><span class="sxs-lookup"><span data-stu-id="e5cf5-102">Step 9: Testing the Lesson 1 Tutorial Package</span></span>
  <span data-ttu-id="e5cf5-103">In dieser Lektion haben Sie die folgenden Aufgaben ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="e5cf5-103">In this lesson, you have done the following tasks:</span></span>  
  
-   <span data-ttu-id="e5cf5-104">Ein neues [!INCLUDE[ssIS](../includes/ssis-md.md)] -Projekt erstellt.</span><span class="sxs-lookup"><span data-stu-id="e5cf5-104">Created a new [!INCLUDE[ssIS](../includes/ssis-md.md)] project.</span></span>  
  
-   <span data-ttu-id="e5cf5-105">Die Verbindungs-Manager konfiguriert, die vom Paket zum Herstellen einer Verbindung mit den Quell- und Zieldaten benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="e5cf5-105">Configured the connection managers that the package needs to connect to the source and destination data.</span></span>  
  
-   <span data-ttu-id="e5cf5-106">Einen Datenfluss hinzugefügt, der Daten aus einer Flatfilequelle abruft, die notwendigen Transformationen zum Suchen in den Daten ausführt und die Daten für das Ziel konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="e5cf5-106">Added a data flow that takes the data from a flat file source, performs the necessary Lookup transformations on the data, and configures the data for the destination.</span></span>  
  
 <span data-ttu-id="e5cf5-107">Ihr Paket ist jetzt vollständig.</span><span class="sxs-lookup"><span data-stu-id="e5cf5-107">Your package is now complete!</span></span> <span data-ttu-id="e5cf5-108">Testen Sie jetzt Ihr Paket.</span><span class="sxs-lookup"><span data-stu-id="e5cf5-108">It is time to test your package.</span></span>  
  
## <a name="checking-the-package-layout"></a><span data-ttu-id="e5cf5-109">Überprüfen des Paketlayouts</span><span class="sxs-lookup"><span data-stu-id="e5cf5-109">Checking the Package Layout</span></span>  
 <span data-ttu-id="e5cf5-110">Bevor Sie das Paket testen, sollten Sie überprüfen, ob Ablaufsteuerung und Datenfluss im Paket aus Lektion 1 die in den folgenden Diagrammen gezeigten Objekte enthalten.</span><span class="sxs-lookup"><span data-stu-id="e5cf5-110">Before you test the package you should verify that the control and data flows in the Lesson 1 package contain the objects shown in the following diagrams.</span></span>  
  
 <span data-ttu-id="e5cf5-111">**Ablaufsteuerung**</span><span class="sxs-lookup"><span data-stu-id="e5cf5-111">**Control Flow**</span></span>  
  
 <span data-ttu-id="e5cf5-112">![Ablaufsteuerung im Paket](../../2014/tutorials/media/task9lesson1control.gif "Ablaufsteuerung im Paket")</span><span class="sxs-lookup"><span data-stu-id="e5cf5-112">![Control flow in package](../../2014/tutorials/media/task9lesson1control.gif "Control flow in package")</span></span>  
  
 <span data-ttu-id="e5cf5-113">**Datenfluss**</span><span class="sxs-lookup"><span data-stu-id="e5cf5-113">**Data Flow**</span></span>  
  
 <span data-ttu-id="e5cf5-114">![Datenfluss im Paket](../../2014/tutorials/media/task9lesson1data.gif "Datenfluss im Paket")</span><span class="sxs-lookup"><span data-stu-id="e5cf5-114">![Data flow in package](../../2014/tutorials/media/task9lesson1data.gif "Data flow in package")</span></span>  
  
### <a name="to-run-the-lesson-1-tutorial-package"></a><span data-ttu-id="e5cf5-115">So führen Sie das Lernprogrammpaket aus Lektion 1 aus</span><span class="sxs-lookup"><span data-stu-id="e5cf5-115">To run the Lesson 1 tutorial package</span></span>  
  
1.  <span data-ttu-id="e5cf5-116">Klicken Sie im Menü **Debuggen** auf die Option **Debuggen starten**.</span><span class="sxs-lookup"><span data-stu-id="e5cf5-116">On the **Debug** menu, click **Start Debugging**.</span></span>  
  
     <span data-ttu-id="e5cf5-117">Das Paket wird ausgeführt, wobei der **FactCurrency** -Faktentabelle in **AdventureWorksDW2012**1.097 Zeilen erfolgreich hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="e5cf5-117">The package will run, resulting in 1097 rows successfully added into the **FactCurrency** fact table in **AdventureWorksDW2012**.</span></span>  
  
2.  <span data-ttu-id="e5cf5-118">Klicken Sie nach Ausführen des Pakets im Menü **Debuggen** auf **Debuggen beenden**.</span><span class="sxs-lookup"><span data-stu-id="e5cf5-118">After the package has completed running, on the **Debug** menu, click **Stop Debugging**.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="e5cf5-119">Nächste Lektion</span><span class="sxs-lookup"><span data-stu-id="e5cf5-119">Next Lesson</span></span>  
 [<span data-ttu-id="e5cf5-120">Lektion 2: Hinzufügen von Schleifen</span><span class="sxs-lookup"><span data-stu-id="e5cf5-120">Lesson 2: Adding Looping</span></span>](../integration-services/lesson-2-adding-looping-with-ssis.md)  
  
## <a name="see-also"></a><span data-ttu-id="e5cf5-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e5cf5-121">See Also</span></span>  
 [<span data-ttu-id="e5cf5-122">Ausführung von Projekten und Paketen</span><span class="sxs-lookup"><span data-stu-id="e5cf5-122">Execution of Projects and Packages</span></span>](packages/run-integration-services-ssis-packages.md)  
  
  
