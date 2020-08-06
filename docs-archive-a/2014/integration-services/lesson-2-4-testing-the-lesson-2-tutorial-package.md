---
title: 'Schritt 4: Testen des Lektion 2-Tutorialpakets | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 0e8c0a25-8f79-41df-8ed2-f82a74b129cd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c055f80cbe9e6748b82569204e3a2d82e2f437e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609311"
---
# <a name="step-4-testing-the-lesson-2-tutorial-package"></a><span data-ttu-id="3a697-102">Schritt 4: Testen des Tutorialpakets aus Lektion 2</span><span class="sxs-lookup"><span data-stu-id="3a697-102">Step 4: Testing the Lesson 2 Tutorial Package</span></span>
  <span data-ttu-id="3a697-103">Mit dem jetzt konfigurierten Foreach-Schleifencontainer und Verbindungs-Manager für Flatfiles kann das Paket aus Lektion 2 nun die Sammlung von 14 Flatfiles im Sample Data-Ordner durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="3a697-103">With the Foreach Loop container and the Flat File connection manager now configured, the Lesson 2 package can iterate through the collection of 14 flat files in the Sample Data folder.</span></span> <span data-ttu-id="3a697-104">Jedes Mal, wenn ein Dateiname gefunden wird, der mit den angegebenen Dateinamenskriterien übereinstimmt, wird die benutzerdefinierte Variable vom Foreach-Schleifencontainer mit dem Dateinamen aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="3a697-104">Each time a file name is found that matches the specified file name criteria, the Foreach Loop container populates the user-defined variable with the file name.</span></span> <span data-ttu-id="3a697-105">Von dieser Variablen wird im Gegenzug die Eigenschaft ConnectionString des Verbindungs-Managers für Flatfiles aktualisiert, und es wird eine Verbindung mit der neuen Flatfile hergestellt.</span><span class="sxs-lookup"><span data-stu-id="3a697-105">This variable, in turn, updates the ConnectionString property of the Flat File connection manager, and a connection to the new flat file is made.</span></span> <span data-ttu-id="3a697-106">Vom Foreach-Schleifencontainer wird dann der unveränderte Datenflusstask gegen die Daten in der neuen Flatfile ausgeführt, bevor eine Verbindung zur nächsten Datei im Ordner hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="3a697-106">The Foreach Loop container then runs the unmodified data flow task against the data in the new flat file before connecting to the next file in the folder.</span></span>  
  
 <span data-ttu-id="3a697-107">Verwenden Sie die folgende Prozedur, um die neue Schleifenfunktionalität zu testen, die Sie zu Ihrem Paket hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="3a697-107">Use the following procedure to test the new looping functionality that you have added to your package.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3a697-108">Wenn Sie das Paket aus Lektion 1 ausgeführt haben, müssen Sie die Datensätze aus dbo.FactCurrency in AdventureWorksDW2012 löschen, bevor Sie das Paket von dieser Lektion aus ausführen. Andernfalls wird für das Paket eine Verletzung der PRIMARY KEY-Einschränkung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3a697-108">If you ran the package from Lesson 1, you will need to delete the records from dbo.FactCurrency in AdventureWorksDW2012 before you run the package from this lesson or the package will fail with errors indicating a Violation of Primary Key constraint.</span></span> <span data-ttu-id="3a697-109">Die gleichen Fehler werden angezeigt, wenn Sie das Paket durch Auswahl von Debuggen bzw. Debuggen starten (oder Drücken von F5) ausführen. Das liegt daran, dass sowohl Lektion 1 als auch Lektion 2 ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3a697-109">You will receive the same errors if you run the package by selecting Debug/Start Debugging (or press F5) because both Lesson 1 and Lesson 2 will run.</span></span> <span data-ttu-id="3a697-110">In Lektion 2 wird versucht, die Datensätze einzufügen, die bereits in Lektion 1 eingefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="3a697-110">Lesson 2 will attempt to insert records already inserted in Lesson 1.</span></span>  
  
## <a name="checking-the-package-layout"></a><span data-ttu-id="3a697-111">Überprüfen des Paketlayouts</span><span class="sxs-lookup"><span data-stu-id="3a697-111">Checking the Package Layout</span></span>  
 <span data-ttu-id="3a697-112">Bevor Sie das Paket testen, sollten Sie überprüfen, ob Ablaufsteuerung und Datenfluss im Paket aus Lektion 2 die in den folgenden Diagrammen gezeigten Objekte enthalten.</span><span class="sxs-lookup"><span data-stu-id="3a697-112">Before you test the package you should verify that the control and data flows in the Lesson 2 package contains the objects shown in the following diagrams.</span></span> <span data-ttu-id="3a697-113">Der Datenfluss sollte mit dem Datenfluss in Lektion 1 übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="3a697-113">The data flow should be identical to the data flow in lesson 1.</span></span>  
  
 <span data-ttu-id="3a697-114">**Ablaufsteuerung**</span><span class="sxs-lookup"><span data-stu-id="3a697-114">**Control Flow**</span></span>  
  
 <span data-ttu-id="3a697-115">![Ablaufsteuerung im Paket](../../2014/tutorials/media/task4lesson2control.gif "Ablaufsteuerung im Paket")</span><span class="sxs-lookup"><span data-stu-id="3a697-115">![Control flow in package](../../2014/tutorials/media/task4lesson2control.gif "Control flow in package")</span></span>  
  
 <span data-ttu-id="3a697-116">**Datenfluss**</span><span class="sxs-lookup"><span data-stu-id="3a697-116">**Data Flow**</span></span>  
  
 <span data-ttu-id="3a697-117">![Datenfluss im Paket](../../2014/tutorials/media/task9lesson1data.gif "Datenfluss im Paket")</span><span class="sxs-lookup"><span data-stu-id="3a697-117">![Data flow in package](../../2014/tutorials/media/task9lesson1data.gif "Data flow in package")</span></span>  
  
### <a name="to-test-the-lesson-2-tutorial-package"></a><span data-ttu-id="3a697-118">So testen Sie das Lektion 2-Lernprogrammpaket</span><span class="sxs-lookup"><span data-stu-id="3a697-118">To test the Lesson 2 tutorial package</span></span>  
  
1.  <span data-ttu-id="3a697-119">Klicken Sie im **Projektmappen-Explorer**mit der rechten Maustaste auf **Lesson 2.dtsx** , und klicken Sie auf **Paket ausführen**.</span><span class="sxs-lookup"><span data-stu-id="3a697-119">In **Solution Explorer**, right-click **Lesson 2.dtsx** and click **Execute Package**.</span></span>  
  
     <span data-ttu-id="3a697-120">Das Paket wird ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="3a697-120">The package will run.</span></span> <span data-ttu-id="3a697-121">Sie können den Status jeder Schleife im Ausgabefenster überprüfen, oder indem Sie **auf die Register** Karte Status klicken. Beispielsweise können Sie sehen, dass der Ziel Tabelle 1097 Zeilen aus dem Datei Currency_VEB.txt hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="3a697-121">You can verify the status of each loop in the Output window, or by clicking on the **Progress** tab. For example, you can see that 1097 lines were added to the destination table from the file Currency_VEB.txt.</span></span>  
  
2.  <span data-ttu-id="3a697-122">Klicken Sie nach Ausführen des Pakets im Menü **Debuggen** auf **Debuggen beenden**.</span><span class="sxs-lookup"><span data-stu-id="3a697-122">After the package has completed running, on the **Debug** menu, click **Stop Debugging**.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="3a697-123">Nächste Lektion</span><span class="sxs-lookup"><span data-stu-id="3a697-123">Next Lesson</span></span>  
 [<span data-ttu-id="3a697-124">Lektion 5: Hinzufügen von Paketkonfigurationen für das Paketbereitstellungsmodell</span><span class="sxs-lookup"><span data-stu-id="3a697-124">Lesson 5: Adding Package Configurations for the Package Deployment Model</span></span>](../integration-services/lesson-5-add-ssis-package-configurations-for-the-package-deployment-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="3a697-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3a697-125">See Also</span></span>  
 [<span data-ttu-id="3a697-126">Ausführung von Projekten und Paketen</span><span class="sxs-lookup"><span data-stu-id="3a697-126">Execution of Projects and Packages</span></span>](packages/run-integration-services-ssis-packages.md)  
  
  
