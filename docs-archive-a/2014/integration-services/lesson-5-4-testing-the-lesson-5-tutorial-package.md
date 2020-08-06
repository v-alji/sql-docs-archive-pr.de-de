---
title: 'Schritt 4: Testen des Lektion 5-Tutorialpakets | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5215b77d-c2ec-4b25-a3de-ca49ea197d74
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 76e4692de4daa9ddd6ed0e418bed5cda74ec7650
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615434"
---
# <a name="step-4-testing-the-lesson-5-tutorial-package"></a><span data-ttu-id="d3f3a-102">Schritt 4: Testen des Tutorialpakets aus Lektion 5</span><span class="sxs-lookup"><span data-stu-id="d3f3a-102">Step 4: Testing the Lesson 5 Tutorial Package</span></span>
  <span data-ttu-id="d3f3a-103">Zur Laufzeit erhält Ihr Paket den Wert für die `Directory`-Eigenschaft von einer zur Laufzeit aktualisierten Variable. Es wird also nicht der ursprüngliche Verzeichnisname verwendet, den Sie beim Erstellen des Pakets angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="d3f3a-103">At run time, your package will obtain the value for the `Directory` property from a variable updated at run time, rather than using the original directory name that you specified when you created the package.</span></span> <span data-ttu-id="d3f3a-104">Der Wert der Variablen wird durch die Datei SSISTutorial.dtsConfig aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="d3f3a-104">The value of the variable is populated by the SSISTutorial.dtsConfig file.</span></span>  
  
 <span data-ttu-id="d3f3a-105">Um zu überprüfen, ob vom Paket die Directory-Eigenschaft während der Laufzeit auf den neuen Wert aktualisiert wird, führen Sie das Paket einfach aus.</span><span class="sxs-lookup"><span data-stu-id="d3f3a-105">To verify that the package updates the Directory property with the new value during run time, simply execute the package.</span></span> <span data-ttu-id="d3f3a-106">Weil nur drei Beispieldatendateien in das neue Verzeichnis kopiert werden, wird der Datenfluss nur drei Mal ausgeführt, statt durch 14 Dateien im ursprünglichen Ordner zu iterieren.</span><span class="sxs-lookup"><span data-stu-id="d3f3a-106">Because only three sample data files were copied to the new directory, the data flow will run only three times, rather than iterate through the 14 files in the original folder.</span></span>  
  
## <a name="checking-the-package-layout"></a><span data-ttu-id="d3f3a-107">Überprüfen des Paketlayouts</span><span class="sxs-lookup"><span data-stu-id="d3f3a-107">Checking the Package Layout</span></span>  
 <span data-ttu-id="d3f3a-108">Bevor Sie das Paket testen, sollten Sie überprüfen, ob Ablaufsteuerung und Datenfluss im Paket aus Lektion 5 die in den folgenden Diagrammen gezeigten Objekte enthalten.</span><span class="sxs-lookup"><span data-stu-id="d3f3a-108">Before you test the package you should verify that the control and data flows in the Lesson 5 package contains the objects shown in the following diagrams.</span></span> <span data-ttu-id="d3f3a-109">Die Ablaufsteuerung sollte mit der Ablaufsteuerung in Lektion 4 übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="d3f3a-109">The control flow should be identical to the control flow in lesson 4.</span></span> <span data-ttu-id="d3f3a-110">Der Datenfluss sollte mit dem Datenfluss in Lektion 4 übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="d3f3a-110">The data flow should be identical to the data flow in lessons 4.</span></span>  
  
 <span data-ttu-id="d3f3a-111">**Ablaufsteuerung**</span><span class="sxs-lookup"><span data-stu-id="d3f3a-111">**Control Flow**</span></span>  
  
 <span data-ttu-id="d3f3a-112">![Ablaufsteuerung im Paket](../../2014/tutorials/media/task4lesson2control.gif "Ablaufsteuerung im Paket")</span><span class="sxs-lookup"><span data-stu-id="d3f3a-112">![Control flow in package](../../2014/tutorials/media/task4lesson2control.gif "Control flow in package")</span></span>  
  
 <span data-ttu-id="d3f3a-113">**Datenfluss**</span><span class="sxs-lookup"><span data-stu-id="d3f3a-113">**Data Flow**</span></span>  
  
 <span data-ttu-id="d3f3a-114">![Datenfluss im Paket](../../2014/tutorials/media/task9lesson1data.gif "Datenfluss im Paket")</span><span class="sxs-lookup"><span data-stu-id="d3f3a-114">![Data flow in package](../../2014/tutorials/media/task9lesson1data.gif "Data flow in package")</span></span>  
  
### <a name="to-test-the-lesson-5-tutorial-package"></a><span data-ttu-id="d3f3a-115">So testen Sie das Lernprogrammpaket aus Lektion 5</span><span class="sxs-lookup"><span data-stu-id="d3f3a-115">To test the Lesson 5 tutorial package</span></span>  
  
1.  <span data-ttu-id="d3f3a-116">Klicken Sie im Menü **Debuggen** auf die Option **Debuggen starten**.</span><span class="sxs-lookup"><span data-stu-id="d3f3a-116">On the **Debug** menu, click **Start Debugging**.</span></span>  
  
2.  <span data-ttu-id="d3f3a-117">Nachdem die Ausführung des Pakets abgeschlossen ist, klicken Sie im Menü **Debuggen** auf **Debuggen Debuggen**.</span><span class="sxs-lookup"><span data-stu-id="d3f3a-117">After the package has completed running, on the **Debug** menu, and then click **Stop Debugging**.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="d3f3a-118">Nächste Lektion</span><span class="sxs-lookup"><span data-stu-id="d3f3a-118">Next Lesson</span></span>  
 [<span data-ttu-id="d3f3a-119">Lektion 6: Verwenden von Parametern mit dem Projektbereitstellungsmodell</span><span class="sxs-lookup"><span data-stu-id="d3f3a-119">Lesson 6: Using Parameters with the Project Deployment Model</span></span>](../integration-services/lesson-6-using-parameters-with-the-project-deployment-model-in-ssis.md)  
  
  
