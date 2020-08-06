---
title: 'Lektion 3: Verwenden des Befehlszeilen-Hilfsprogramms DTA | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Database Engine [SQL Server], tutorials
ms.assetid: 30f27f4d-8852-4b12-ba62-57f63e496f1d
author: stevestein
ms.author: sstein
ms.openlocfilehash: abbde02cd73e01937e6d0669c10f2db28da8a76e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695001"
---
# <a name="lesson-3-using-the-dta-command-prompt-utility"></a><span data-ttu-id="ae74f-102">Lektion 3: Verwenden des Befehlszeilenprogramms dta</span><span class="sxs-lookup"><span data-stu-id="ae74f-102">Lesson 3: Using the dta Command Prompt Utility</span></span>
  <span data-ttu-id="ae74f-103">Mit dem Befehlszeilenprogramm **dta** wird die Funktionalität des Datenbankoptimierungsratgebers erweitert.</span><span class="sxs-lookup"><span data-stu-id="ae74f-103">The **dta** command-prompt utility offers functionality in addition to that provided by the Database Engine Tuning Advisor.</span></span>  
  
 <span data-ttu-id="ae74f-104">Sie können mit Ihren bevorzugten XML-Tools Eingabedateien für das Befehlszeilenprogramm erstellen und dabei das XML-Schema des Datenbankoptimierungsratgebers verwenden.</span><span class="sxs-lookup"><span data-stu-id="ae74f-104">You can use your favorite XML tools to create input files for the utility by using the Database Engine Tuning Advisor XML schema.</span></span> <span data-ttu-id="ae74f-105">Dieses Schema wird zusammen mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installiert. Es befindet sich unter: C:\Programme (x86)\Microsoft SQL Server\110\Tools\Binn\schemas\sqlserver\2004\07\dta\dtaschema.xsd.</span><span class="sxs-lookup"><span data-stu-id="ae74f-105">This schema is installed when you install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and can be found at: C:\Program Files (x86)\Microsoft SQL Server\110\Tools\Binn\schemas\sqlserver\2004\07\dta\dtaschema.xsd.</span></span>  
  
 <span data-ttu-id="ae74f-106">Das XML-Schema des Datenbankoptimierungsratgebers ist auch online auf [dieser Microsoft-Website](https://go.microsoft.com/fwlink/?linkid=43100&clcid=0x409)verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ae74f-106">The Database Engine Tuning Advisor XML schema is also available online at [this Microsoft Web site](https://go.microsoft.com/fwlink/?linkid=43100&clcid=0x409).</span></span>  
  
 <span data-ttu-id="ae74f-107">Das XML-Schema des Datenbankoptimierungsratgebers ermöglicht mehr Flexibilität beim Festlegen von Optimierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="ae74f-107">The Database Engine Tuning Advisor XML schema provides more flexibility to set tuning options.</span></span> <span data-ttu-id="ae74f-108">So ermöglicht es z. B. die Durchführung einer "Was-wäre-wenn-Analyse".</span><span class="sxs-lookup"><span data-stu-id="ae74f-108">For example, it enables you to perform "what-if" analysis.</span></span> <span data-ttu-id="ae74f-109">Für eine "Was-wäre-wenn-Analyse" wird für die Datenbank, die optimiert werden soll, eine Gruppe vorhandener sowie hypothetischer physischer Entwurfsstrukturen angegeben. Diese werden dann mit dem Datenbankoptimierungsratgeber analysiert, um herauszufinden, welche dieser hypothetischen Entwurfsstrukturen die Abfrageverarbeitung verbessert.</span><span class="sxs-lookup"><span data-stu-id="ae74f-109">"What-if" analysis involves specifying a set of existing and hypothetical physical design structures for the database you want to tune, and then analyzing it with the Database Engine Tuning Advisor to find out whether this hypothetical physical design will improve query processing performance.</span></span> <span data-ttu-id="ae74f-110">Diese Art einer Analyse hat den Vorteil, dass die neue Konfiguration ausgewertet werden kann, ohne dass eine Implementierung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="ae74f-110">This type of analysis provides the advantage of evaluating the new configuration without incurring the overhead of actually implementing it.</span></span> <span data-ttu-id="ae74f-111">Wenn die hypothetische physische Entwurfsstruktur nicht die gewünschten Leistungsverbesserungen erbringt, können Sie sie einfach ändern und erneut analysieren, bis die Konfiguration erreicht ist, mit der die gewünschten Ergebnisse erzielt werden.</span><span class="sxs-lookup"><span data-stu-id="ae74f-111">If your hypothetical physical design does not provide the performance improvements you want, it is easy to change it and analyze it again until you reach the configuration that produces the results you need.</span></span>  
  
 <span data-ttu-id="ae74f-112">Außerdem können Sie mit dem XML-Schema des Datenbankoptimierungsratgebers und mit dem Befehlszeilenprogramm **dta** Funktionen des Datenbankoptimierungsratgebers in Skripts übernehmen und diese in anderen Datenbankentwicklungstools verwenden.</span><span class="sxs-lookup"><span data-stu-id="ae74f-112">In addition, using the Database Engine Tuning Advisor XML schema and the **dta** command-prompt utility, you can incorporate Database Engine Tuning Advisor functionality into scripts and use it with other database design tools.</span></span>  
  
 <span data-ttu-id="ae74f-113">Auf die Verwendung der XML-Eingabefunktionen des Datenbankoptimierungsratgebers wird in dieser Lektion nicht eingegangen.</span><span class="sxs-lookup"><span data-stu-id="ae74f-113">Using the XML input functionality of Database Engine Tuning Advisor is beyond the scope of this lesson.</span></span>  
  
 <span data-ttu-id="ae74f-114">In dieser Lektion finden Sie eine Einführung in die Basissyntax des Befehlszeilenprogramms **dta** . Außerdem wird der Zugriff auf die Hilfe und das Optimieren der Arbeitsauslastung erläutert.</span><span class="sxs-lookup"><span data-stu-id="ae74f-114">This lesson provides an introduction to the basic **dta** command-prompt utility syntax, how to access help, and practice for tuning simple workloads.</span></span>  
  
 <span data-ttu-id="ae74f-115">Die Lektion enthält die folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="ae74f-115">It contains the following topic:</span></span>  
  
-   <span data-ttu-id="ae74f-116">Starten des Befehlszeilen-Hilfsprogramms **DTA** und Optimieren einer Arbeitsauslastung</span><span class="sxs-lookup"><span data-stu-id="ae74f-116">Starting the **dta** Command Prompt Utility and Tuning a Workload</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="ae74f-117">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="ae74f-117">Next Task in Lesson</span></span>  
 [<span data-ttu-id="ae74f-118">Starten des dta-Befehlszeilenprogramms und Optimieren einer Workload</span><span class="sxs-lookup"><span data-stu-id="ae74f-118">Starting the dta Command Prompt Utility and Tuning a Workload</span></span>](lesson-1-1-tuning-a-workload.md)  
  
  
