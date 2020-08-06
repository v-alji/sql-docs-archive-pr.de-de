---
title: 'Lektion 3: Hinzufügen der Protokollierung | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 64cd24cc-ba8e-4bd7-b10b-6b80d8b04af6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 58fcc29759f19ad215a76a1b9ed9bf313b4c869c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617179"
---
# <a name="lesson-3-adding-logging"></a><span data-ttu-id="93273-102">Lektion 3: Hinzufügen der Protokollierung</span><span class="sxs-lookup"><span data-stu-id="93273-102">Lesson 3: Adding Logging</span></span>
  [!INCLUDE[msCoName](../includes/msconame-md.md)] <span data-ttu-id="93273-103">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] umfasst Protokollierungsfunktionen für die Problembehandlung und Überwachung der Paketausführung mithilfe einer Reihe von Task- und Containerereignissen.</span><span class="sxs-lookup"><span data-stu-id="93273-103">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] includes logging features that let you troubleshoot and monitor package execution by providing a trace of task and container events.</span></span> <span data-ttu-id="93273-104">Die Protokollierungsfunktionen sind flexibel und können auf der Ebene des Pakets oder für einzelne Tasks und Container innerhalb des Pakets aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="93273-104">The logging features are flexible, and can be enabled at the package level or on individual tasks and containers within the package.</span></span> <span data-ttu-id="93273-105">Sie können dann auswählen, welche Ereignisse protokolliert werden sollen, und mehrere Protokolle für ein einzelnes Paket erstellen.</span><span class="sxs-lookup"><span data-stu-id="93273-105">You can select which events you want to log, and create multiple logs against a single package.</span></span>  
  
 <span data-ttu-id="93273-106">Die Protokollierung wird von einem Protokollanbieter zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="93273-106">Logging is provided by a log provider.</span></span> <span data-ttu-id="93273-107">Jeder Protokollanbieter ist in der Lage, Protokollierungsinformationen in verschiedenen Formaten und Zieltypen zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="93273-107">Each log provider can write logging information to different formats and destination types.</span></span> [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="93273-108">stellt die folgenden Protokollanbieter bereit:</span><span class="sxs-lookup"><span data-stu-id="93273-108">provides the following log providers:</span></span>  
  
-   <span data-ttu-id="93273-109">Textdatei</span><span class="sxs-lookup"><span data-stu-id="93273-109">Text file</span></span>  
  
-   [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)]  
  
-   <span data-ttu-id="93273-110">Windows-Ereignisprotokoll:</span><span class="sxs-lookup"><span data-stu-id="93273-110">Windows Event log</span></span>  
  
-   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]  
  
-   <span data-ttu-id="93273-111">XML-Datei:</span><span class="sxs-lookup"><span data-stu-id="93273-111">XML file</span></span>  
  
 <span data-ttu-id="93273-112">In dieser Lektion erstellen Sie eine Kopie des Pakets, das Sie in [Lektion 2: Hinzufügen von Schleifen](lesson-2-adding-looping-with-ssis.md)erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="93273-112">In this lesson, you will create a copy of the package that you created in [Lesson 2: Adding Looping](lesson-2-adding-looping-with-ssis.md).</span></span> <span data-ttu-id="93273-113">Beim Arbeiten mit diesem neuen Paket fügen Sie dann die Protokollierung hinzu und konfigurieren sie, um bestimmte Ereignisse während der Paketausführung zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="93273-113">Working with this new package, you will then add and configure logging to monitor specific events during package execution.</span></span> <span data-ttu-id="93273-114">Wenn Sie keine der vorherigen Lektionen abgeschlossen haben, können Sie auch das abgeschlossene Paket aus Lektion 2, das im Lernprogramm enthalten ist, kopieren.</span><span class="sxs-lookup"><span data-stu-id="93273-114">If you have not completed any of the previous lessons, you can also copy the completed Lesson 2 package that is included with the tutorial.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="93273-115">Dieses Lernprogramm erfordert die **AdventureWorksDW2012** -Beispieldatenbank.</span><span class="sxs-lookup"><span data-stu-id="93273-115">This tutorial requires the **AdventureWorksDW2012** sample database.</span></span> <span data-ttu-id="93273-116">Weitere Informationen zum Installieren und Bereitstellen von **AdventureWorksDW2012** [Reporting Services Produktbeispiele auf GitHub](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).</span><span class="sxs-lookup"><span data-stu-id="93273-116">For more information about how to install and deploy **AdventureWorksDW2012**, [Reporting Services Product Samples on GitHub](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="93273-117">Lektionsaufgaben</span><span class="sxs-lookup"><span data-stu-id="93273-117">Lesson Tasks</span></span>  
 <span data-ttu-id="93273-118">Diese Lektion enthält die folgenden Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="93273-118">This lesson contains the following tasks:</span></span>  
  
-   [<span data-ttu-id="93273-119">Schritt 1: Kopieren des Pakets aus Lektion 2</span><span class="sxs-lookup"><span data-stu-id="93273-119">Step 1: Copying the Lesson 2 Package</span></span>](lesson-3-1-copying-the-lesson-2-package.md)  
  
-   [<span data-ttu-id="93273-120">Schritt 2: Hinzufügen und Konfigurieren der Protokollierung</span><span class="sxs-lookup"><span data-stu-id="93273-120">Step 2: Adding and Configuring Logging</span></span>](lesson-3-2-adding-and-configuring-logging.md)  
  
-   [<span data-ttu-id="93273-121">Schritt 3: Testen des Tutorialpakets aus Lektion 3</span><span class="sxs-lookup"><span data-stu-id="93273-121">Step 3: Testing the Lesson 3 Tutorial Package</span></span>](../integration-services/lesson-3-3-testing-the-lesson-3-tutorial-package.md)  
  
## <a name="start-the-lesson"></a><span data-ttu-id="93273-122">Lektion beginnen</span><span class="sxs-lookup"><span data-stu-id="93273-122">Start the Lesson</span></span>  
 [<span data-ttu-id="93273-123">Schritt 1: Kopieren des Pakets aus Lektion 2</span><span class="sxs-lookup"><span data-stu-id="93273-123">Step 1: Copying the Lesson 2 Package</span></span>](lesson-3-1-copying-the-lesson-2-package.md)  
  
  
