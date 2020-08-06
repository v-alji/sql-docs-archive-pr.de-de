---
title: 'Tutorial: Datenbankoptimierungsratgeber | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- Database Engine Tuning Advisor [SQL Server], tutorials
- tutorials [Database Engine Tuning Advisor]
ms.assetid: 3b54cbbe-d8c6-424d-92f1-aa58179f4da8
author: stevestein
ms.author: sstein
ms.openlocfilehash: 68e026cb28b875b834f20c906232285ede8e217b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608992"
---
# <a name="tutorial-database-engine-tuning-advisor"></a><span data-ttu-id="aad13-102">Tutorial: Datenbankoptimierungsratgeber</span><span class="sxs-lookup"><span data-stu-id="aad13-102">Tutorial: Database Engine Tuning Advisor</span></span>
  <span data-ttu-id="aad13-103">Willkommen beim Lernprogramm zum Datenbankoptimierungsratgeber.</span><span class="sxs-lookup"><span data-stu-id="aad13-103">Welcome to the Database Engine Tuning Advisor tutorial.</span></span> <span data-ttu-id="aad13-104">Der Datenbankoptimierungsratgeber prüft, wie Abfragen in den von Ihnen angegebenen Datenbanken verarbeitet werden. Er gibt dann eine Empfehlung ab, wie Sie die Verarbeitung von Abfragen verbessern können, indem Sie Datenbankstrukturen ändern, wie z. B. Indizes, indizierte Sichten und die Partitionierung.</span><span class="sxs-lookup"><span data-stu-id="aad13-104">Database Engine Tuning Advisor examines how queries are processed in the databases you specify, and then recommends how you can improve query processing performance by modifying database structures such as indexes, indexed views, and partitioning.</span></span>  
  
 <span data-ttu-id="aad13-105">Der Datenbankoptimierungsratgeber bietet zwei Benutzeroberflächen: eine grafische Benutzeroberfläche (GUI) und das Befehlszeilenhilfsprogramm **dta** .</span><span class="sxs-lookup"><span data-stu-id="aad13-105">Database Engine Tuning Advisor provides two user interfaces: a graphical user interface (GUI) and the **dta** command prompt utility.</span></span> <span data-ttu-id="aad13-106">Über die grafische Benutzeroberfläche können schnell die Ergebnisse von Optimierungssitzungen angezeigt werden. Das Hilfsprogramm **dta** ermöglicht die einfache Übernahme von Funktionen des Datenbankoptimierungsratgebers in Skripts für die automatische Optimierung.</span><span class="sxs-lookup"><span data-stu-id="aad13-106">The GUI makes it easy to quickly view the results of tuning sessions, and the **dta** utility makes it easy to incorporate Database Engine Tuning Advisor functionality into scripts for automated tuning.</span></span> <span data-ttu-id="aad13-107">Darüber hinaus kann der Datenbankoptimierungsratgeber XML-Eingaben annehmen und bietet somit eine bessere Steuerung des Optimierungsprozesses.</span><span class="sxs-lookup"><span data-stu-id="aad13-107">In addition, Database Engine Tuning Advisor can take XML input, which offers more control over the tuning process.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="aad13-108">Lernziele</span><span class="sxs-lookup"><span data-stu-id="aad13-108">What You Will Learn</span></span>  
 <span data-ttu-id="aad13-109">In diesem Lernprogramm erfahren Sie, wie Sie in der grafischen Benutzeroberfläche des Datenbankoptimierungsratgebers navigieren. Außerdem werden Sie einige einfache Aufgaben mithilfe der grafischen Benutzeroberfläche und mit dem Hilfsprogramm **dta** ausführen.</span><span class="sxs-lookup"><span data-stu-id="aad13-109">This tutorial will teach you how to navigate the Database Engine Tuning Advisor GUI, and how to perform some basic tasks with both the GUI and the **dta** utility.</span></span> <span data-ttu-id="aad13-110">Es enthält die folgenden Lektionen:</span><span class="sxs-lookup"><span data-stu-id="aad13-110">It contains the following lessons:</span></span>  
  
 [<span data-ttu-id="aad13-111">Lektion 1: Grundlagen zur Navigation im Datenbankoptimierungsratgeber</span><span class="sxs-lookup"><span data-stu-id="aad13-111">Lesson 1: Basic Navigation in Database Engine Tuning Advisor</span></span>](../../relational-databases/performance/database-engine-tuning-advisor.md)  
 <span data-ttu-id="aad13-112">In dieser Lektion machen Sie sich mit der grafischen Benutzeroberfläche des neuen Datenbankoptimierungsratgebers vertraut und lernen, wie Sie die Anzeigeoptionen und das Layout festlegen.</span><span class="sxs-lookup"><span data-stu-id="aad13-112">In this lesson, you will familiarize yourself with the new Database Engine Tuning Advisor GUI and learn how to set display options and layout.</span></span>  
  
 [<span data-ttu-id="aad13-113">Lektion 2: Verwenden des Datenbankoptimierungsratgebers</span><span class="sxs-lookup"><span data-stu-id="aad13-113">Lesson 2: Using Database Engine Tuning Advisor</span></span>](lesson-2-using-database-engine-tuning-advisor.md)  
 <span data-ttu-id="aad13-114">In dieser Lektion erfahren Sie, wie Sie einfache Optimierungsaufgaben mit der grafischen Benutzeroberfläche des Datenbankoptimierungsratgebers ausführen.</span><span class="sxs-lookup"><span data-stu-id="aad13-114">In this lesson, you will learn how to perform basic tuning tasks with the Database Engine Tuning Advisor GUI.</span></span>  
  
 [<span data-ttu-id="aad13-115">Lektion 3: Verwenden des Befehlszeilenprogramms dta</span><span class="sxs-lookup"><span data-stu-id="aad13-115">Lesson 3: Using the dta Command Prompt Utility</span></span>](lesson-3-using-the-dta-command-prompt-utility.md)  
 <span data-ttu-id="aad13-116">In dieser Lektion lernen Sie, wie Sie das Befehlszeilenprogramm **dta** starten und wie Sie einige einfache Optimierungsbefehle ausführen.</span><span class="sxs-lookup"><span data-stu-id="aad13-116">In this lesson, you learn how to start the **dta** command prompt utility and how to run some simple tuning commands.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aad13-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="aad13-117">Requirements</span></span>  
 <span data-ttu-id="aad13-118">Dieses Lernprogramm richtet sich an Datenbankadministratoren, die noch nicht mit der grafischen Benutzeroberfläche des Datenbankoptimierungsratgebers oder mit dem Befehlszeilenhilfsprogramm **dta** vertraut sind, die jedoch mit Datenbankkonzepten und -strukturen vertraut sind, wie z.B. mit Indizes und indizierten Sichten.</span><span class="sxs-lookup"><span data-stu-id="aad13-118">This tutorial is intended for database administrators who are not familiar with the Database Engine Tuning Advisor GUI or the **dta** command prompt utility, but who are experienced with database concepts and structures, such as indexes and indexed views.</span></span>  
  
 <span data-ttu-id="aad13-119">[!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] (bzw. eine höhere Version) muss mit der Beispieldatenbank [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] installiert werden.</span><span class="sxs-lookup"><span data-stu-id="aad13-119">You must install [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] (or a later version) with the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span> <span data-ttu-id="aad13-120">Aus Sicherheitsgründen werden die Beispieldatenbanken standardmäßig nicht installiert.</span><span class="sxs-lookup"><span data-stu-id="aad13-120">To enhance security, the sample databases are not installed by default.</span></span> <span data-ttu-id="aad13-121">Informationen zur Installation der Beispieldatenbanken finden Sie unter [Installieren der SQL Server-Beispiele und -Beispieldatenbanken](http://sqlserversamples.codeplex.com).</span><span class="sxs-lookup"><span data-stu-id="aad13-121">To install the sample databases, see [Installing SQL Server Samples and Sample Databases](http://sqlserversamples.codeplex.com).</span></span>  
  
## <a name="after-you-finish-this-tutorial"></a><span data-ttu-id="aad13-122">Weiterführende Informationen nach Abschluss dieses Lernprogramms</span><span class="sxs-lookup"><span data-stu-id="aad13-122">After You Finish This Tutorial</span></span>  
 <span data-ttu-id="aad13-123">Wenn Sie die Lektionen in diesem Lernprogramm durchgearbeitet haben, finden Sie unter folgenden Themen weitere Informationen zum Datenbankoptimierungsratgeber:</span><span class="sxs-lookup"><span data-stu-id="aad13-123">After you finish the lessons in this tutorial, refer to the following topics for more information about Database Engine Tuning Advisor:</span></span>  
  
-   <span data-ttu-id="aad13-124">[Database Engine Tuning Advisor](../../relational-databases/performance/database-engine-tuning-advisor.md) enthält Beschreibungen zum Ausführen von Tasks mit diesem Tool.</span><span class="sxs-lookup"><span data-stu-id="aad13-124">[Database Engine Tuning Advisor](../../relational-databases/performance/database-engine-tuning-advisor.md) for descriptions of how to perform tasks with this tool.</span></span>  
  
-   <span data-ttu-id="aad13-125">[dta Utility](dta-utility.md) enthält Referenzmaterial zum Eingabeaufforderungs-Hilfsprogramm und der optionalen XML-Datei, mit der Sie die Ausführung des Hilfsprogramms steuern können.</span><span class="sxs-lookup"><span data-stu-id="aad13-125">[dta Utility](dta-utility.md) for reference material on the command prompt utility and the optional XML file you can use to control the operation of the utility.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="aad13-126">Nächste Lektion</span><span class="sxs-lookup"><span data-stu-id="aad13-126">Next Lesson</span></span>  
 [<span data-ttu-id="aad13-127">Lektion 1: Grundlagen zur Navigation im Datenbankoptimierungsratgeber</span><span class="sxs-lookup"><span data-stu-id="aad13-127">Lesson 1: Basic Navigation in Database Engine Tuning Advisor</span></span>](../../relational-databases/performance/database-engine-tuning-advisor.md)  
  
  
