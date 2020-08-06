---
title: Behandlung von Problemen mit Berichten für die Paketausführung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 8fc476ac-bd69-434e-9636-70776e0b3b6c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b20d9c9c02af3f3df96e2ef46a7b25251793fa55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619901"
---
# <a name="troubleshooting-reports-for-package-execution"></a><span data-ttu-id="f6591-102">Behandlung von Problemen in Berichten für die Paketausführung</span><span class="sxs-lookup"><span data-stu-id="f6591-102">Troubleshooting Reports for Package Execution</span></span>
  <span data-ttu-id="f6591-103">In der aktuellen Version von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]sind Standardberichte in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] verfügbar, die für die Überwachung und Problembehandlung der im [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Katalog bereitgestellten [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Pakete hilfreich sind.</span><span class="sxs-lookup"><span data-stu-id="f6591-103">In the current release of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], standard reports are available in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to help you monitor and troubleshoot [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages that have been deployed to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] catalog.</span></span> <span data-ttu-id="f6591-104">Zwei dieser Paketberichte dienen insbesondere zum Anzeigen des Status der Paketausführung und zum Ermitteln der Ursache von Ausführungsfehlern.</span><span class="sxs-lookup"><span data-stu-id="f6591-104">Two of these package reports in particular help you to view package execution status and identify the cause of execution failures.</span></span>  
  
-   <span data-ttu-id="f6591-105">**Integration Services-Dashboard** : Dieser Bericht bietet eine Übersicht über alle Paketausführungen auf der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz in den letzten 24 Stunden.</span><span class="sxs-lookup"><span data-stu-id="f6591-105">**Integration Services Dashboard** - This report provides an overview of all the package executions on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance in the past 24 hours.</span></span> <span data-ttu-id="f6591-106">Der Bericht zeigt Informationen, wie z. B. den Status, Vorgangstyp, Paketnamen usw., für jedes Paket an.</span><span class="sxs-lookup"><span data-stu-id="f6591-106">The report displays information such as Status, Operation Type, Package Name, etc., for each package.</span></span>  
  
     <span data-ttu-id="f6591-107">Startzeit, Endzeit und Dauer können wie folgt interpretiert werden:</span><span class="sxs-lookup"><span data-stu-id="f6591-107">The Start Time, End Time, and Duration can be interpreted as follows:</span></span>  
  
    -   <span data-ttu-id="f6591-108">Wenn das Paket noch ausgeführt wird, gilt Dauer = aktuelle Zeit - Startzeit.</span><span class="sxs-lookup"><span data-stu-id="f6591-108">If the package is still running, then Duration = current time - Start Time</span></span>  
  
    -   <span data-ttu-id="f6591-109">Wenn das Paket abgeschlossen wurde, gilt Dauer = Endzeit - Startzeit.</span><span class="sxs-lookup"><span data-stu-id="f6591-109">If the package has completed, then Duration = End Time - Start Time</span></span>  
  
     <span data-ttu-id="f6591-110">Im Dashboard können Sie die Informationen zu jedem auf dem Server ausgeführten Paket erweitern, um spezifische Details über möglicherweise aufgetretene Paketausführungsfehler zu suchen.</span><span class="sxs-lookup"><span data-stu-id="f6591-110">For each package that has run on the server, the dashboard allows you to "zoom in" to find specific details on package execution errors that may have occurred.</span></span> <span data-ttu-id="f6591-111">Sie können z.B. auf **Übersicht** klicken, um eine allgemeine Übersicht über die Status der in der Ausführung enthaltenen Tasks anzuzeigen, oder auf **Alle Meldungen** , um die ausführlichen Meldungen anzuzeigen, die bei der Paketausführung erfasst wurden.</span><span class="sxs-lookup"><span data-stu-id="f6591-111">For example, click **Overview** to display a high-level overview of the status of the tasks in the execution, or **All Messages** to display the detailed messages that were captured as part of the package execution.</span></span>  
  
     <span data-ttu-id="f6591-112">Sie können die auf einer beliebigen Seite angezeigte Tabelle filtern, indem Sie auf **Filtern** klicken und dann im Dialogfeld **Filtereinstellungen** die gewünschten Kriterien auswählen.</span><span class="sxs-lookup"><span data-stu-id="f6591-112">You can filter the table displayed on any page by clicking **Filter** and then selecting criteria in the **Filter Settings** dialog.</span></span> <span data-ttu-id="f6591-113">Abhängig von den angezeigten Daten sind unterschiedliche Filterkriterien verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f6591-113">The filter criteria available depends on the data being displayed.</span></span> <span data-ttu-id="f6591-114">Sie können die Sortierreihenfolge des Berichts ändern, indem Sie im Dialogfeld **Filtereinstellungen** auf das Sortiersymbol klicken.</span><span class="sxs-lookup"><span data-stu-id="f6591-114">You can change the sort order of the report by clicking the sort icon in the **Filter Settings** dialog.</span></span>  
  
-   <span data-ttu-id="f6591-115">**Bericht „Aktivität – Alle Vorgänge“:** Dieser Bericht zeigt eine Zusammenfassung aller [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Ausführungen auf dem Server.</span><span class="sxs-lookup"><span data-stu-id="f6591-115">**Activity - All Executions Report** - This report displays a summary of all [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] executions that have been performed on the server.</span></span> <span data-ttu-id="f6591-116">Die Zusammenfassung enthält Informationen für jede Ausführung, z. B. Status, Startzeit und Endzeit.</span><span class="sxs-lookup"><span data-stu-id="f6591-116">The summary displays information for each execution such as status, start time, and end time.</span></span> <span data-ttu-id="f6591-117">Jeder Zusammenfassungseintrag enthält Links zu weiteren Informationen zur Ausführung, z. B. während der Ausführung generierten Meldungen und Leistungsdaten.</span><span class="sxs-lookup"><span data-stu-id="f6591-117">Each summary entry includes links to more information about the execution including messages generated during execution and performance data.</span></span> <span data-ttu-id="f6591-118">Wie in dem Integration Services-Dashboard können Sie einen Filter auf die Tabelle anwenden, um die angezeigten Informationen einzugrenzen.</span><span class="sxs-lookup"><span data-stu-id="f6591-118">As with the Integration Services Dashboard, you can apply a filter to the table to narrow down the information displayed.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="f6591-119">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="f6591-119">Related Tasks</span></span>  
 [<span data-ttu-id="f6591-120">Anzeigen von Berichten für den Integration Services-Server</span><span class="sxs-lookup"><span data-stu-id="f6591-120">View Reports for the Integration Services Server</span></span>](../view-reports-for-the-integration-services-server.md)  
  
## <a name="related-content"></a><span data-ttu-id="f6591-121">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="f6591-121">Related Content</span></span>  
 [<span data-ttu-id="f6591-122">Berichte für den Integration Services Server</span><span class="sxs-lookup"><span data-stu-id="f6591-122">Reports for the Integration Services Server</span></span>](../reports-for-the-integration-services-server.md)  
  
 [<span data-ttu-id="f6591-123">Behandlung von Problemen mit Paketausführungstools</span><span class="sxs-lookup"><span data-stu-id="f6591-123">Troubleshooting Tools for Package Execution</span></span>](troubleshooting-tools-for-package-execution.md)  
  
  
