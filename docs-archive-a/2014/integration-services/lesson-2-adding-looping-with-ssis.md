---
title: 'Lektion 2: Hinzufügen von Schleifen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 01f2ed61-1e5a-4ec6-b6a6-2bd070c64077
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 65efb84b4e50b470470e396bbe5681ce4b5dfac3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615437"
---
# <a name="lesson-2-adding-looping"></a><span data-ttu-id="f8519-102">Lektion 2: Hinzufügen von Schleifen</span><span class="sxs-lookup"><span data-stu-id="f8519-102">Lesson 2: Adding Looping</span></span>
  <span data-ttu-id="f8519-103">In [Lektion 1: Erstellen des Projekts und des Basispakets](lesson-1-create-a-project-and-basic-package-with-ssis.md)haben Sie ein Paket erstellt, das Daten aus einer einzelnen Flatfilequelle extrahiert, die Daten mithilfe von Transformationen zum Suchen transformiert und schließlich die Daten in die **Fakten Tabelle factcurrency** der **AdventureWorksDW2012** -Beispieldatenbank geladen hat.</span><span class="sxs-lookup"><span data-stu-id="f8519-103">In [Lesson 1: Creating the Project and Basic Package](lesson-1-create-a-project-and-basic-package-with-ssis.md), you created a package that extracted data from a single flat file source, transformed the data using Lookup transformations, and finally loaded the data into the **FactCurrency** fact table of the **AdventureWorksDW2012** sample database.</span></span>  
  
 <span data-ttu-id="f8519-104">Das Verwenden einer einzelnen flachen Datei ist allerdings bei einem ETL-Vorgang (Extract, Transform and Load, Extrahieren, Transformieren und Laden) selten.</span><span class="sxs-lookup"><span data-stu-id="f8519-104">However, it is rare for an extract, transform, and load (ETL) process to use a single flat file.</span></span> <span data-ttu-id="f8519-105">Von einem typischen ETL-Vorgang würden Daten aus mehreren flachen Dateiquellen extrahiert.</span><span class="sxs-lookup"><span data-stu-id="f8519-105">A typical ETL process would extract data from multiple flat file sources.</span></span> <span data-ttu-id="f8519-106">Das Extrahieren von Daten aus mehreren Quellen erfordert eine iterative (wiederholende) Ablaufsteuerung.</span><span class="sxs-lookup"><span data-stu-id="f8519-106">Extracting data from multiple sources requires an iterative control flow.</span></span> <span data-ttu-id="f8519-107">Eine der am häufigsten erwarteten Features von [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] ist die Fähigkeit, Paketen problemlos Iterationen oder Schleifen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="f8519-107">One of the most anticipated features of [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] is the ability to easily add iteration or looping to packages.</span></span>  
  
 [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="f8519-108">bietet zwei Containertypen für Schleifenvorgänge durch Pakete an: den Foreach- und den For-Schleifencontainer.</span><span class="sxs-lookup"><span data-stu-id="f8519-108">provides two types of containers for looping through packages: the Foreach Loop container and the For Loop container.</span></span> <span data-ttu-id="f8519-109">Der Foreach-Schleifencontainer verwendet einen Enumerator für die Ausführung der Schleife, während der For-Schleifencontainer normalerweise einen Variablenausdruck verwendet.</span><span class="sxs-lookup"><span data-stu-id="f8519-109">The Foreach Loop container uses an enumerator to perform the looping, whereas the For Loop container typically uses a variable expression.</span></span> <span data-ttu-id="f8519-110">In dieser Lektion wird der Foreach-Schleifencontainer verwendet.</span><span class="sxs-lookup"><span data-stu-id="f8519-110">This lesson uses the Foreach Loop container.</span></span>  
  
 <span data-ttu-id="f8519-111">Durch den Foreach-Schleifencontainer wird es für ein Paket möglich, die Ablaufsteuerung für jedes Element eines angegebenen Enumerators zu wiederholen.</span><span class="sxs-lookup"><span data-stu-id="f8519-111">The Foreach Loop container enables a package to repeat the control flow for each member of a specified enumerator.</span></span> <span data-ttu-id="f8519-112">Mithilfe des Foreach-Schleifencontainer können Sie die folgenden Elemente aufzählen:</span><span class="sxs-lookup"><span data-stu-id="f8519-112">With the Foreach Loop container, you can enumerate:</span></span>  
  
-   <span data-ttu-id="f8519-113">ADO-Recordsetzeilen</span><span class="sxs-lookup"><span data-stu-id="f8519-113">ADO recordset rows</span></span>  
  
-   <span data-ttu-id="f8519-114">ADO.NET-Schemainformationen</span><span class="sxs-lookup"><span data-stu-id="f8519-114">ADO .Net schema information</span></span>  
  
-   <span data-ttu-id="f8519-115">Datei- und Verzeichnisstrukturen</span><span class="sxs-lookup"><span data-stu-id="f8519-115">File and directory structures</span></span>  
  
-   <span data-ttu-id="f8519-116">System-, Paket- und Benutzervariablen</span><span class="sxs-lookup"><span data-stu-id="f8519-116">System, package and user variables</span></span>  
  
-   <span data-ttu-id="f8519-117">Aufzählbare Objekte in einer Variablen</span><span class="sxs-lookup"><span data-stu-id="f8519-117">Enumerable objects contained in a variable</span></span>  
  
-   <span data-ttu-id="f8519-118">Elemente in einer Auflistung</span><span class="sxs-lookup"><span data-stu-id="f8519-118">Items in a collection</span></span>  
  
-   <span data-ttu-id="f8519-119">Knoten in einem XPath-Ausdruck (XML Path Language)</span><span class="sxs-lookup"><span data-stu-id="f8519-119">Nodes in an XML Path Language (XPath) expression</span></span>  
  
-   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="f8519-120">Management Objects (SMO)</span><span class="sxs-lookup"><span data-stu-id="f8519-120">Management Objects (SMO)</span></span>  
  
 <span data-ttu-id="f8519-121">In dieser Lektion ändern Sie das in Lektion 1 erstellte einfache ETL-Paket, um die Vorteile des Foreach-Schleifencontainers nutzen zu können.</span><span class="sxs-lookup"><span data-stu-id="f8519-121">In this lesson, you will modify the simple ETL package created in Lesson 1 to take advantage of the Foreach Loop container.</span></span> <span data-ttu-id="f8519-122">Sie legen auch benutzerdefinierte Paketvariablen fest, um die Iteration durch alle flachen Dateien im Ordner für das Lernprogrammpaket zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="f8519-122">You will also set user-defined package variables to enable the tutorial package to iterate through all the flat files in the folder.</span></span> <span data-ttu-id="f8519-123">Wenn Sie die vorherige Lektion nicht abgeschlossen haben, können Sie auch das abgeschlossene Paket aus Lektion 1 kopieren, das im Lernprogramm enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="f8519-123">If you have not completed the previous lesson, you can also copy the completed Lesson 1 package that is included with the tutorial.</span></span>  
  
 <span data-ttu-id="f8519-124">In dieser Lektion ändern Sie nur die Ablaufsteuerung, nicht den Datenfluss.</span><span class="sxs-lookup"><span data-stu-id="f8519-124">In this lesson, you will not modify the data flow, only the control flow.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f8519-125">Dieses Lernprogramm erfordert die **AdventureWorksDW2012** -Beispieldatenbank.</span><span class="sxs-lookup"><span data-stu-id="f8519-125">This tutorial requires the **AdventureWorksDW2012** sample database.</span></span> <span data-ttu-id="f8519-126">Weitere Informationen zum Installieren und Bereitstellen von **AdventureWorksDW2012**finden Sie unter [Reporting Services Produktbeispiel-Projekt auf CodePlex](https://go.microsoft.com/fwlink/p/?LinkID=526910).</span><span class="sxs-lookup"><span data-stu-id="f8519-126">For more information about how to install and deploy **AdventureWorksDW2012**, see [Reporting Services Product Samples on CodePlex](https://go.microsoft.com/fwlink/p/?LinkID=526910).</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="f8519-127">Lektionsaufgaben</span><span class="sxs-lookup"><span data-stu-id="f8519-127">Lesson Tasks</span></span>  
 <span data-ttu-id="f8519-128">Diese Lektion enthält die folgenden Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="f8519-128">This lesson contains the following tasks:</span></span>  
  
-   [<span data-ttu-id="f8519-129">Schritt 1: Kopieren des Pakets aus Lektion 1</span><span class="sxs-lookup"><span data-stu-id="f8519-129">Step 1: Copying the Lesson 1 Package</span></span>](lesson-2-1-copying-the-lesson-1-package.md)  
  
-   [<span data-ttu-id="f8519-130">Schritt 2: Hinzufügen und Konfigurieren des Foreach-Schleifencontainers</span><span class="sxs-lookup"><span data-stu-id="f8519-130">Step 2: Adding and Configuring the Foreach Loop Container</span></span>](lesson-2-2-adding-and-configuring-the-foreach-loop-container.md)  
  
-   [<span data-ttu-id="f8519-131">Schritt 3: Ändern des Flatfile-Verbindungs-Managers</span><span class="sxs-lookup"><span data-stu-id="f8519-131">Step 3: Modifying the Flat File Connection Manager</span></span>](lesson-2-3-modifying-the-flat-file-connection-manager.md)  
  
-   [<span data-ttu-id="f8519-132">Schritt 4: Testen des Tutorialpakets aus Lektion 2</span><span class="sxs-lookup"><span data-stu-id="f8519-132">Step 4: Testing the Lesson 2 Tutorial Package</span></span>](lesson-2-4-testing-the-lesson-2-tutorial-package.md)  
  
## <a name="start-the-lesson"></a><span data-ttu-id="f8519-133">Lektion beginnen</span><span class="sxs-lookup"><span data-stu-id="f8519-133">Start the Lesson</span></span>  
 [<span data-ttu-id="f8519-134">Schritt 1: Kopieren des Pakets aus Lektion 1</span><span class="sxs-lookup"><span data-stu-id="f8519-134">Step 1: Copying the Lesson 1 Package</span></span>](lesson-2-1-copying-the-lesson-1-package.md)  
  
## <a name="see-also"></a><span data-ttu-id="f8519-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f8519-135">See Also</span></span>  
 [<span data-ttu-id="f8519-136">For-Schleifencontainer</span><span class="sxs-lookup"><span data-stu-id="f8519-136">For Loop Container</span></span>](control-flow/for-loop-container.md)  
  
  
