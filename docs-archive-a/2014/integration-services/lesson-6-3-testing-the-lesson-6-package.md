---
title: 'Schritt 3: Testen des Pakets aus Lektion 6 | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: c184c92d-948f-4037-a502-5fabd909c84c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3c7ab82e9b04fe0752252102374f745e311d830d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721602"
---
# <a name="step-3-testing-the-lesson-6-package"></a><span data-ttu-id="0d3e0-102">Schritt 3: Testen des Pakets aus Lektion 6</span><span class="sxs-lookup"><span data-stu-id="0d3e0-102">Step 3: Testing the Lesson 6 Package</span></span>
  <span data-ttu-id="0d3e0-103">Zur Laufzeit erhält Ihr Paket den Wert für die Eigenschaft "Verzeichnis" vom VarFolderName-Parameter.</span><span class="sxs-lookup"><span data-stu-id="0d3e0-103">At run time, your package will obtain the value for the Directory property from the VarFolderName parameter.</span></span>  
  
 <span data-ttu-id="0d3e0-104">Um zu überprüfen, ob vom Paket die Directory-Eigenschaft während der Laufzeit auf den neuen Wert aktualisiert wird, führen Sie das Paket einfach aus.</span><span class="sxs-lookup"><span data-stu-id="0d3e0-104">To verify that the package updates the Directory property with the new value during run time, simply execute the package.</span></span> <span data-ttu-id="0d3e0-105">Weil nur drei Beispieldatendateien in das neue Verzeichnis kopiert werden, wird der Datenfluss nur drei Mal ausgeführt, statt durch 14 Dateien im ursprünglichen Ordner zu iterieren.</span><span class="sxs-lookup"><span data-stu-id="0d3e0-105">Because only three sample data files were copied to the new directory, the data flow will run only three times, rather than iterate through the 14 files in the original folder.</span></span>  
  
## <a name="checking-the-package-layout"></a><span data-ttu-id="0d3e0-106">Überprüfen des Paketlayouts</span><span class="sxs-lookup"><span data-stu-id="0d3e0-106">Checking the Package Layout</span></span>  
 <span data-ttu-id="0d3e0-107">Bevor Sie das Paket testen, sollten Sie überprüfen, ob Ablaufsteuerung und Datenfluss im Paket aus Lektion 6 die in den folgenden Diagrammen gezeigten Objekte enthalten.</span><span class="sxs-lookup"><span data-stu-id="0d3e0-107">Before you test the package you should verify that the control and data flows in the Lesson 6 package contains the objects shown in the following diagrams.</span></span> <span data-ttu-id="0d3e0-108">Die Ablaufsteuerung sollte mit der Ablaufsteuerung in Lektion 5 übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="0d3e0-108">The control flow should be identical to the control flow in lesson 5.</span></span> <span data-ttu-id="0d3e0-109">Der Datenfluss sollte mit dem Datenfluss in Lektion 5 übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="0d3e0-109">The data flow should be identical to the data flow in lesson 5.</span></span>  
  
 <span data-ttu-id="0d3e0-110">**Ablaufsteuerung**</span><span class="sxs-lookup"><span data-stu-id="0d3e0-110">**Control Flow**</span></span>  
  
 <span data-ttu-id="0d3e0-111">![Ablaufsteuerung](../../2014/tutorials/media/task3lesson6control.jpg "Ablaufsteuerung")</span><span class="sxs-lookup"><span data-stu-id="0d3e0-111">![Control Flow](../../2014/tutorials/media/task3lesson6control.jpg "Control Flow")</span></span>  
  
 <span data-ttu-id="0d3e0-112">**Datenfluss**</span><span class="sxs-lookup"><span data-stu-id="0d3e0-112">**Data Flow**</span></span>  
  
 <span data-ttu-id="0d3e0-113">![Datenfluss](../../2014/tutorials/media/task3lesson6data.jpg "Datenfluss")</span><span class="sxs-lookup"><span data-stu-id="0d3e0-113">![Data Flow](../../2014/tutorials/media/task3lesson6data.jpg "Data Flow")</span></span>  
  
### <a name="to-test-the-lesson-6-tutorial-package"></a><span data-ttu-id="0d3e0-114">So testen Sie das Lektion 6-Lernprogrammpaket</span><span class="sxs-lookup"><span data-stu-id="0d3e0-114">TO test the Lesson 6 tutorial package</span></span>  
  
1.  <span data-ttu-id="0d3e0-115">Klicken Sie im Menü "Debuggen" auf "Debuggen starten".</span><span class="sxs-lookup"><span data-stu-id="0d3e0-115">On the Debug menu, click Start Debugging.</span></span>  
  
2.  <span data-ttu-id="0d3e0-116">Klicken Sie nach Ausführen des Pakets im Menü "Debuggen" auf "Debuggen beenden".</span><span class="sxs-lookup"><span data-stu-id="0d3e0-116">After the package has completed running, on the Debug menu, and then click Stop Debugging.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="0d3e0-117">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="0d3e0-117">Next Task in Lesson</span></span>  
 [<span data-ttu-id="0d3e0-118">Schritt 4: Bereitstellen des Pakets aus Lektion 6</span><span class="sxs-lookup"><span data-stu-id="0d3e0-118">Step 4: Deploying the Lesson 6 Package</span></span>](../integration-services/lesson-6-4-deploying-the-lesson-6-package.md)  
  
  
