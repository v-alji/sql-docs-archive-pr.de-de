---
title: 'Lektion 8: Definieren von Aktionen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 15459396-83c9-48a0-b10a-99ae38768c79
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4d4daaed3f1992478b309529fc15e2e903a27920
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722006"
---
# <a name="lesson-8-defining-actions"></a><span data-ttu-id="ad397-102">Lektion 8: Definieren von Aktionen</span><span class="sxs-lookup"><span data-stu-id="ad397-102">Lesson 8: Defining Actions</span></span>
  <span data-ttu-id="ad397-103">In dieser Lektion erfahren Sie, wie Sie Aktionen in Ihrem [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Projekt definieren können.</span><span class="sxs-lookup"><span data-stu-id="ad397-103">In this lesson, you will learn to define actions in your [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project.</span></span> <span data-ttu-id="ad397-104">Eine Aktion bezeichnet einfach eine in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] gespeicherte MDX-Anweisung (Multidimensional Expressions), die in Clientanwendungen integriert und von Benutzern gestartet werden kann.</span><span class="sxs-lookup"><span data-stu-id="ad397-104">An action is just a Multidimensional Expressions (MDX) statement that is stored in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] and which can be incorporated into client applications and started by a user.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ad397-105">Für alle Lektionen in diesem Lernprogramm sind abgeschlossene Projekte online verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ad397-105">Completed projects for all of the lessons in this tutorial are available online.</span></span> <span data-ttu-id="ad397-106">Sie können jede Lektion aufrufen, indem Sie ein abgeschlossenes Projekt aus der vorherigen Lektion als Ausgangspunkt verwenden.</span><span class="sxs-lookup"><span data-stu-id="ad397-106">You can jump ahead to any lesson by using the completed project from the previous lesson as a starting point.</span></span> <span data-ttu-id="ad397-107">[Klicken Sie hier](https://go.microsoft.com/fwlink/?LinkID=221866) , um die Beispielprojekte für dieses Lernprogramm herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="ad397-107">[Click here](https://go.microsoft.com/fwlink/?LinkID=221866) to download the sample projects that go with this tutorial.</span></span>  
  
 [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] <span data-ttu-id="ad397-108">unterstützt die in der folgenden Tabelle beschriebenen Typen von Aktionen.</span><span class="sxs-lookup"><span data-stu-id="ad397-108">supports the types of actions that are described in the following table.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ad397-109">CommandLine</span><span class="sxs-lookup"><span data-stu-id="ad397-109">CommandLine</span></span>|<span data-ttu-id="ad397-110">Führt einen Befehl an der Eingabeaufforderung aus.</span><span class="sxs-lookup"><span data-stu-id="ad397-110">Executes a command at the command prompt</span></span>|  
|<span data-ttu-id="ad397-111">Dataset</span><span class="sxs-lookup"><span data-stu-id="ad397-111">Dataset</span></span>|<span data-ttu-id="ad397-112">Gibt ein Dataset an eine Clientanwendung zurück.</span><span class="sxs-lookup"><span data-stu-id="ad397-112">Returns a dataset to a client application.</span></span>|  
|<span data-ttu-id="ad397-113">Drillthroughfilter</span><span class="sxs-lookup"><span data-stu-id="ad397-113">Drillthrough</span></span>|<span data-ttu-id="ad397-114">Gibt eine Drillthroughanweisung als Ausdruck zurück, den der Client zur Rückgabe eines Rowsets ausführt.</span><span class="sxs-lookup"><span data-stu-id="ad397-114">Returns a drillthrough statement as an expression, which the client executes to return a rowset</span></span>|  
|<span data-ttu-id="ad397-115">Html</span><span class="sxs-lookup"><span data-stu-id="ad397-115">Html</span></span>|<span data-ttu-id="ad397-116">Führt ein HTML-Skript in einem Internetbrowser aus.</span><span class="sxs-lookup"><span data-stu-id="ad397-116">Executes an HTML script in an Internet browser</span></span>|  
|<span data-ttu-id="ad397-117">Proprietär</span><span class="sxs-lookup"><span data-stu-id="ad397-117">Proprietary</span></span>|<span data-ttu-id="ad397-118">Führt einen Vorgang über eine Schnittstelle aus, die nicht in dieser Tabelle aufgelistet ist.</span><span class="sxs-lookup"><span data-stu-id="ad397-118">Performs an operation by using an interface other than those listed in this table.</span></span>|  
|<span data-ttu-id="ad397-119">Bericht</span><span class="sxs-lookup"><span data-stu-id="ad397-119">Report</span></span>|<span data-ttu-id="ad397-120">Übermittelt eine parametrisierte, URL-basierte Anforderung an einen Berichtsserver und gibt einen Bericht an eine Clientanwendung zurück.</span><span class="sxs-lookup"><span data-stu-id="ad397-120">Submits a parameterized URL-based request to a report server and returns a report to a client application.</span></span>|  
|<span data-ttu-id="ad397-121">Rowset</span><span class="sxs-lookup"><span data-stu-id="ad397-121">Rowset</span></span>|<span data-ttu-id="ad397-122">Gibt ein Rowset an eine Clientanwendung zurück.</span><span class="sxs-lookup"><span data-stu-id="ad397-122">Returns a rowset to a client application.</span></span>|  
|<span data-ttu-id="ad397-123">Anweisung</span><span class="sxs-lookup"><span data-stu-id="ad397-123">Statement</span></span>|<span data-ttu-id="ad397-124">Gibt einen OLE DB-Befehl zurück.</span><span class="sxs-lookup"><span data-stu-id="ad397-124">Runs an OLE DB command.</span></span>|  
|<span data-ttu-id="ad397-125">URL</span><span class="sxs-lookup"><span data-stu-id="ad397-125">URL</span></span>|<span data-ttu-id="ad397-126">Zeigt eine dynamische Webseite in einem Internetbrowser an.</span><span class="sxs-lookup"><span data-stu-id="ad397-126">Displays a dynamic Web page in an Internet browser.</span></span>|  
  
 <span data-ttu-id="ad397-127">Aktionen ermöglichen es Benutzern, eine Anwendung zu starten oder andere Schritte innerhalb des Kontexts eines bestimmten Elements auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ad397-127">Actions let users start an application or perform other steps within the context of a selected item.</span></span> <span data-ttu-id="ad397-128">Weitere Informationen finden Sie unter [Aktionen &#40;Analysis Services – mehrdimensionale Daten&#41;](multidimensional-models/actions-analysis-services-multidimensional-data.md)und [Aktionen in mehrdimensionalen Modellen](multidimensional-models/actions-in-multidimensional-models.md)</span><span class="sxs-lookup"><span data-stu-id="ad397-128">For more information, see [Actions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models/actions-analysis-services-multidimensional-data.md), [Actions in Multidimensional Models](multidimensional-models/actions-in-multidimensional-models.md)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ad397-129">Beispielaktionen finden Sie in den Aktionsbeispielen auf der Registerkarte Vorlagen im Bereich Berechnungstools oder in den Beispielen des [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] DW-Data Warehouse-Beispiels.</span><span class="sxs-lookup"><span data-stu-id="ad397-129">For examples of actions, see the action examples on the Templates tab in the Calculation Tools pane or in the examples in the [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] DW sample data warehouse.</span></span> <span data-ttu-id="ad397-130">Weitere Informationen zum Installieren dieser Datenbank finden Sie unter [Install Sample Data and Projects for the Analysis Services Multidimensional Modeling Tutorial](install-sample-data-and-projects.md).</span><span class="sxs-lookup"><span data-stu-id="ad397-130">For more information about installing this database, see [Install Sample Data and Projects for the Analysis Services Multidimensional Modeling Tutorial](install-sample-data-and-projects.md).</span></span>  
  
 <span data-ttu-id="ad397-131">Diese Lektion enthält den folgenden Task:</span><span class="sxs-lookup"><span data-stu-id="ad397-131">This lesson includes the following task:</span></span>  
  
 [<span data-ttu-id="ad397-132">Definieren und Verwenden einer Drillthroughaktion</span><span class="sxs-lookup"><span data-stu-id="ad397-132">Defining and Using a Drillthrough Action</span></span>](lesson-8-1-defining-and-using-a-drillthrough-action.md)  
 <span data-ttu-id="ad397-133">In diesem Task definieren, verwenden und ändern Sie eine Drillthroughaktion über die Faktendimensionsbeziehung, die Sie zu einem früheren Zeitpunkt in diesem Lernprogramm definiert haben.</span><span class="sxs-lookup"><span data-stu-id="ad397-133">In this task, you define, use, and then modify a drillthrough action through the fact dimension relationship that you defined earlier in this tutorial.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="ad397-134">Nächste Lektion</span><span class="sxs-lookup"><span data-stu-id="ad397-134">Next Lesson</span></span>  
 [<span data-ttu-id="ad397-135">Lektion 9: Definieren von Perspektiven und Übersetzungen</span><span class="sxs-lookup"><span data-stu-id="ad397-135">Lesson 9: Defining Perspectives and Translations</span></span>](lesson-9-defining-perspectives-and-translations.md)  
  
## <a name="see-also"></a><span data-ttu-id="ad397-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ad397-136">See Also</span></span>  
 <span data-ttu-id="ad397-137">[Analysis Services Tutorial-Szenario](analysis-services-tutorial-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="ad397-137">[Analysis Services Tutorial Scenario](analysis-services-tutorial-scenario.md) </span></span>  
 <span data-ttu-id="ad397-138">[Mehrdimensionale Modellierung &#40;Adventure Works-Tutorial&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="ad397-138">[Multidimensional Modeling &#40;Adventure Works Tutorial&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span></span>  
 <span data-ttu-id="ad397-139">[Aktionen &#40;Analysis Services Mehrdimensionale Daten&#41;](multidimensional-models/actions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="ad397-139">[Actions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models/actions-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="ad397-140">Aktionen in mehrdimensionalen Modellen</span><span class="sxs-lookup"><span data-stu-id="ad397-140">Actions in Multidimensional Models</span></span>](multidimensional-models/actions-in-multidimensional-models.md)  
  
  
