---
title: Datenprofilerstellungs-Task und -Viewer | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Data Profiling task [Integration Services], about data profiling
- data profiling
- profiling data
ms.assetid: 756840e3-aa09-45cd-9951-1a17af4b5925
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ae15d1cc75f8db04c36a830e44d07800c5aecf75
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616630"
---
# <a name="data-profiling-task-and-viewer"></a><span data-ttu-id="f1fa4-102">Datenprofilerstellungs-Task und -Viewer</span><span class="sxs-lookup"><span data-stu-id="f1fa4-102">Data Profiling Task and Viewer</span></span>
  <span data-ttu-id="f1fa4-103">Der Datenprofilerstellungs-Task bietet Funktionen zur Datenprofilerstellung beim Extrahieren, Transformieren und Laden von Daten.</span><span class="sxs-lookup"><span data-stu-id="f1fa4-103">The Data Profiling task provides data profiling functionality inside the process of extracting, transforming, and loading data.</span></span> <span data-ttu-id="f1fa4-104">Mit dem Datenprofilerstellungs-Task können Sie die folgenden Vorteile erzielen:</span><span class="sxs-lookup"><span data-stu-id="f1fa4-104">By using the Data Profiling task, you can achieve the following benefits:</span></span>  
  
-   <span data-ttu-id="f1fa4-105">Sie können die Quelldaten effizienter analysieren.</span><span class="sxs-lookup"><span data-stu-id="f1fa4-105">Analyze the source data more effectively</span></span>  
  
-   <span data-ttu-id="f1fa4-106">Sie können die Quelldaten besser verstehen.</span><span class="sxs-lookup"><span data-stu-id="f1fa4-106">Understand the source data better</span></span>  
  
-   <span data-ttu-id="f1fa4-107">Sie können Datenqualitätsprobleme verhindern, bevor diese ins Data Warehouse eingeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f1fa4-107">Prevent data quality problems before they are introduced into the data warehouse.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f1fa4-108">Der Datenprofilerstellungs-Task funktioniert nur mit Daten, die in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="f1fa4-108">The Data Profiling task works only with data that is stored in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f1fa4-109">Dieser Task funktioniert nicht mit Datenquellen von Drittanbietern oder dateibasierten Datenquellen.</span><span class="sxs-lookup"><span data-stu-id="f1fa4-109">It does not work with third-party or file-based data sources.</span></span>  
  
## <a name="data-profiling-overview"></a><span data-ttu-id="f1fa4-110">Übersicht über die Datenprofilerstellung</span><span class="sxs-lookup"><span data-stu-id="f1fa4-110">Data Profiling Overview</span></span>  
 <span data-ttu-id="f1fa4-111">Datenqualität ist für jedes Unternehmen von Bedeutung.</span><span class="sxs-lookup"><span data-stu-id="f1fa4-111">Data quality is important to every business.</span></span> <span data-ttu-id="f1fa4-112">Da Unternehmen zusätzlich zu ihren Transaktionssystemen analytische Systeme und Business Intelligence-Systeme erstellen, hängt die Zuverlässigkeit von Key Performance Indicators (KPIs) und Data Mining-Vorhersageabfragen vollständig von der Gültigkeit der Daten ab, auf denen diese Systeme basieren.</span><span class="sxs-lookup"><span data-stu-id="f1fa4-112">As enterprises build analytical and business intelligence systems on top of their transactional systems, the reliability of key performance indicators and of data mining predictions depends completely on the validity of the data on which they are based.</span></span> <span data-ttu-id="f1fa4-113">Obwohl die Bedeutung von gültigen Daten für Geschäftsentscheidungen ständig zunimmt, wird die Gewährleistung der Gültigkeit dieser Daten immer schwieriger.</span><span class="sxs-lookup"><span data-stu-id="f1fa4-113">But although the importance of valid data for business decision-making is increasing, the challenge of making sure of this data's validity is also increasing.</span></span> <span data-ttu-id="f1fa4-114">Daten von unterschiedlichen Systemen und Quellen und zahlreichen Benutzern strömen unaufhörlich in das Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="f1fa4-114">Data is streaming into the enterprise constantly from diverse systems and sources, and a large numbers of users.</span></span>  
  
 <span data-ttu-id="f1fa4-115">Es kann schwierig sein, Metriken für die Datenqualität zu definieren, da diese spezifisch für die jeweilige Domäne oder Anwendung sind.</span><span class="sxs-lookup"><span data-stu-id="f1fa4-115">Metrics for data quality can be difficult to define because they are specific to the domain or the application.</span></span> <span data-ttu-id="f1fa4-116">Ein gebräuchliches Verfahren zur Definition von Datenqualität ist die Datenprofilerstellung.</span><span class="sxs-lookup"><span data-stu-id="f1fa4-116">One common approach to defining data quality is data profiling.</span></span>  
  
 <span data-ttu-id="f1fa4-117">Ein Datenprofil ist eine Auflistung von Gesamtstatistiken zu Daten, die Folgendes einschließen könnten:</span><span class="sxs-lookup"><span data-stu-id="f1fa4-117">A data profile is a collection of aggregate statistics about data that might include the following:</span></span>  
  
-   <span data-ttu-id="f1fa4-118">Die Anzahl der Zeilen in der Customer-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="f1fa4-118">The number of rows in the Customer table.</span></span>  
  
-   <span data-ttu-id="f1fa4-119">Die Anzahl von unterschiedlichen Werten in der Spalte State.</span><span class="sxs-lookup"><span data-stu-id="f1fa4-119">The number of distinct values in the State column.</span></span>  
  
-   <span data-ttu-id="f1fa4-120">Die Anzahl von NULL-Werten oder fehlenden Werten in der Spalte Zip.</span><span class="sxs-lookup"><span data-stu-id="f1fa4-120">The number of null or missing values in the Zip column.</span></span>  
  
-   <span data-ttu-id="f1fa4-121">Die Verteilung der Werte in der Spalte City.</span><span class="sxs-lookup"><span data-stu-id="f1fa4-121">The distribution of values in the City column.</span></span>  
  
-   <span data-ttu-id="f1fa4-122">Die Stärke der funktionalen Abhängigkeit der Spalte „State“ von der Spalte „Zip“, d.h., der Staat sollte für einen bestimmten PLZ-Wert immer gleich sein.</span><span class="sxs-lookup"><span data-stu-id="f1fa4-122">The strength of the functional dependency of the State column on the Zip column-that is, the state should always be the same for a given zip value.</span></span>  
  
 <span data-ttu-id="f1fa4-123">Die Statistiken, die ein Datenprofil bietet, liefern Ihnen die erforderlichen Informationen, um effizient die Qualitätsprobleme zu minimieren, die durch die Verwendung der Quelldaten auftreten könnten.</span><span class="sxs-lookup"><span data-stu-id="f1fa4-123">The statistics that a data profile provides gives you the information that you need in order to effectively minimize the quality issues that might occur from using the source data.</span></span>  
  
## <a name="integration-services-and-data-profiling"></a><span data-ttu-id="f1fa4-124">SQL Server Integration Services und Datenprofilerstellung</span><span class="sxs-lookup"><span data-stu-id="f1fa4-124">Integration Services and Data Profiling</span></span>  
 <span data-ttu-id="f1fa4-125">In [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]besteht der Prozess der Datenprofilerstellung aus den folgenden Schritten:</span><span class="sxs-lookup"><span data-stu-id="f1fa4-125">In [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], the data profiling process consist of the following steps:</span></span>  
  
 <span data-ttu-id="f1fa4-126">**Schritt 1: Einrichten des Datenprofilerstellungs-Tasks**</span><span class="sxs-lookup"><span data-stu-id="f1fa4-126">**Step 1: Setting up the Data Profiling Task**</span></span>  
 <span data-ttu-id="f1fa4-127">Der Datenprofilerstellungs-Task ist ein Task, den Sie verwenden können, um die Profile zu konfigurieren, die Sie berechnen möchten.</span><span class="sxs-lookup"><span data-stu-id="f1fa4-127">The Data Profiling task is a task that you use to configure the profiles that you want to compute.</span></span> <span data-ttu-id="f1fa4-128">Sie führen dann das Paket aus, das den Datenprofilerstellungs-Task enthält, um die Profile zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="f1fa4-128">You then run the package that contains the Data Profiling task to compute the profiles.</span></span> <span data-ttu-id="f1fa4-129">Der Task speichert die Profilausgabe im XML-Format in einer Datei oder Paketvariablen.</span><span class="sxs-lookup"><span data-stu-id="f1fa4-129">The task saves the profile output in XML format to a file or a package variable.</span></span>  
  
 <span data-ttu-id="f1fa4-130">**Weitere Informationen:** [Einrichten von Datenprofilerstellungs-Tasks](data-profiling-task.md)</span><span class="sxs-lookup"><span data-stu-id="f1fa4-130">**For more information:** [Setup of the Data Profiling Task](data-profiling-task.md)</span></span>  
  
 <span data-ttu-id="f1fa4-131">**Schritt 2: Überprüfen der Profile, die der Datenprofilerstellungs-Task berechnet**</span><span class="sxs-lookup"><span data-stu-id="f1fa4-131">**Step 2: Reviewing the Profiles that the Data Profiling Task Computes**</span></span>  
 <span data-ttu-id="f1fa4-132">Wenn Sie die vom Datenprofilerstellungs-Task berechneten Datenprofile anzeigen möchten, senden Sie die Ausgabe an eine Datei, und verwenden Sie dann den Datenprofil-Viewer.</span><span class="sxs-lookup"><span data-stu-id="f1fa4-132">To view the data profiles that the Data Profiling task computes, you send the output to a file, and then you use the Data Profile Viewer.</span></span> <span data-ttu-id="f1fa4-133">Dieser Viewer ist ein eigenständiges Hilfsprogramm, das die Profilausgabe im Zusammenfassungs- und Detailformat mit optionaler Drilldownfunktion anzeigt.</span><span class="sxs-lookup"><span data-stu-id="f1fa4-133">This viewer is a stand-alone utility that displays the profile output in both summary and detail format with optional drilldown capability.</span></span>  
  
 <span data-ttu-id="f1fa4-134">**Weitere Informationen:** [Datenprofil-Viewer](data-profile-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="f1fa4-134">**For more information:** [Data Profile Viewer](data-profile-viewer.md)</span></span>  
  
### <a name="addition-of-conditional-logic-to-the-data-profiling-workflow"></a><span data-ttu-id="f1fa4-135">Hinzufügen von Bedingungslogik zum Datenprofilerstellungs-Workflow</span><span class="sxs-lookup"><span data-stu-id="f1fa4-135">Addition of Conditional Logic to the Data Profiling Workflow</span></span>  
 <span data-ttu-id="f1fa4-136">Der Datenprofilerstellungs-Task verfügt über keine integrierten Funktionen, die eine Verwendung von Bedingungslogik ermöglichen, um diesen Task auf der Grundlage der Profilausgabe mit Downstream-Tasks zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="f1fa4-136">The Data Profiling task does not have built-in features that allow you to use conditional logic to connect this task to downstream tasks based on the profile output.</span></span> <span data-ttu-id="f1fa4-137">Mit minimalem Programmieraufwand können Sie diese Logik jedoch problemlos einem Skripttask hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="f1fa4-137">However, you can easily add this logic, with a small amount of programming, in a Script task.</span></span> <span data-ttu-id="f1fa4-138">Der Skripttask könnte beispielsweise eine XPath-Abfrage für die Ausgabedatei des Datenprofilerstellungs-Tasks ausführen.</span><span class="sxs-lookup"><span data-stu-id="f1fa4-138">For example, the Script task could perform an XPath query against the output file of the Data Profiling task.</span></span> <span data-ttu-id="f1fa4-139">Durch die Abfrage könnte bestimmt werden, ob der Prozentwert von NULL-Werten in einer bestimmten Spalte einen bestimmten Schwellenwert überschreitet.</span><span class="sxs-lookup"><span data-stu-id="f1fa4-139">The query could determine whether the percentage of null values in a particular column exceeds a certain threshold.</span></span> <span data-ttu-id="f1fa4-140">Wenn der Prozentwert den Schwellenwert überschreitet, könnten Sie das Paket unterbrechen und das Problem in den Quelldaten vor dem Fortsetzen beheben.</span><span class="sxs-lookup"><span data-stu-id="f1fa4-140">If the percentage exceeds the threshold, you could interrupt the package and resolve the problem in the source data before continuing.</span></span> <span data-ttu-id="f1fa4-141">Weitere Informationen finden Sie unter [Einschließen einer Datenprofilerstellungs-Task in den Paketworkflow](incorporate-a-data-profiling-task-in-package-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="f1fa4-141">For more information, see [Incorporate a Data Profiling Task in Package Workflow](incorporate-a-data-profiling-task-in-package-workflow.md).</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="f1fa4-142">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="f1fa4-142">Related Content</span></span>  
 [<span data-ttu-id="f1fa4-143">Datenprofiler-Schema</span><span class="sxs-lookup"><span data-stu-id="f1fa4-143">Data Profiler Schema</span></span>](https://go.microsoft.com/fwlink/?LinkId=251524)  
  
  
