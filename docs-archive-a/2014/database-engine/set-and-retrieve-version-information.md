---
title: Festlegen und Abrufen von Versionsinformationen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- historical information [SQL Server]
- source controls [SQL Server Management Studio], version information
- retrieving version information
- current file version information
- version control services [SQL Server], retrieving version information
- version control services [SQL Server], setting version information
- status information [SQL Server], source control files
- historical information [SQL Server], source control files
ms.assetid: c3f253c4-4e3d-48e8-8d90-bd6ee899faf7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: eff3d40ba9b663ba8611508c5b9f0c9961005b81
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696026"
---
# <a name="set-and-retrieve-version-information"></a><span data-ttu-id="11db5-102">Festlegen und Abrufen von Versionsinformationen</span><span class="sxs-lookup"><span data-stu-id="11db5-102">Set and Retrieve Version Information</span></span>
  <span data-ttu-id="11db5-103">Zu den Versionsinformationen zählen der Verlauf und der aktuelle Status einer Datei unter Quellcodeverwaltung.</span><span class="sxs-lookup"><span data-stu-id="11db5-103">Version information includes the history and current status of a source-controlled file.</span></span> <span data-ttu-id="11db5-104">Für jede Datei unter Quellcodeverwaltung verwaltet [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe umfassende Verlaufsdaten. Dadurch können Sie die Entwicklung einer oder mehrerer Dateien über einen bestimmten Zeitraum verfolgen.</span><span class="sxs-lookup"><span data-stu-id="11db5-104">For every source-controlled file, [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe maintains a comprehensive history, so you can track the evolution of one or more files over time.</span></span> <span data-ttu-id="11db5-105">Sie können diese Informationen auch dazu verwenden, um eine lokale Kopie einer beliebigen Version der Datei abzurufen oder zwei beliebige Versionen miteinander zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="11db5-105">You can also use this information to retrieve a local copy of any version of the file or to compare any two file versions.</span></span>  
  
 <span data-ttu-id="11db5-106">Zum Verlauf einer Datei gehört:</span><span class="sxs-lookup"><span data-stu-id="11db5-106">The history of a file includes:</span></span>  
  
-   <span data-ttu-id="11db5-107">Die Versionsnummer, die die Sequenz in Bezug auf andere Versionen dieser Datei identifiziert.</span><span class="sxs-lookup"><span data-stu-id="11db5-107">The version number, which identifies its sequence among other versions of the same file.</span></span>  
  
-   <span data-ttu-id="11db5-108">Die ausgeführte Aktion.</span><span class="sxs-lookup"><span data-stu-id="11db5-108">The action performed.</span></span> <span data-ttu-id="11db5-109">Zu den Vorgängen der Ablaufverfolgung zählen das Erstellen der Datei, das Einchecken und das Löschen.</span><span class="sxs-lookup"><span data-stu-id="11db5-109">Tracked operations include file creation, check in, and deletion.</span></span>  
  
-   <span data-ttu-id="11db5-110">Der Benutzername der Person, die eine Aktion für die Datei ausgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="11db5-110">The user name of the person who performed an action involving the file.</span></span>  
  
-   <span data-ttu-id="11db5-111">Datum und Uhrzeit der Ausführung des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="11db5-111">The date and time when the operation was performed.</span></span>  
  
 <span data-ttu-id="11db5-112">Visual SourceSafe verwaltet außerdem aktuelle Statusinformationen für die zurzeit geladene Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="11db5-112">Visual SourceSafe also maintains current status information on the currently loaded solution.</span></span> <span data-ttu-id="11db5-113">Diese Informationen liefern eine Momentaufnahme des aktuellen Status der Datei. Dazu zählen:  </span><span class="sxs-lookup"><span data-stu-id="11db5-113">This information provides a snapshot of the current state of the file, including:</span></span>  
  
-   <span data-ttu-id="11db5-114">Die Identität des Benutzers, der die Datei ausgecheckt hat.</span><span class="sxs-lookup"><span data-stu-id="11db5-114">The identity of the user who has the file checked out.</span></span>  
  
-   <span data-ttu-id="11db5-115">Die letzte Versionsnummer der ausgewählten Datei.</span><span class="sxs-lookup"><span data-stu-id="11db5-115">The latest version number of the selected file.</span></span>  
  
-   <span data-ttu-id="11db5-116">Das Datum, an dem die Version erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="11db5-116">The date when the version was created.</span></span>  
  
-   <span data-ttu-id="11db5-117">Der Benutzerkommentar, der der Version zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="11db5-117">The user comment associated with the version.</span></span>  
  
-   <span data-ttu-id="11db5-118">Die Pfade zu den Projekten, für die die Datei freigegeben ist.</span><span class="sxs-lookup"><span data-stu-id="11db5-118">The paths to the projects with which the file is shared.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="11db5-119">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="11db5-119">In This Section</span></span>  
  
-   [<span data-ttu-id="11db5-120">Anzeigen des Dateiverlaufs</span><span class="sxs-lookup"><span data-stu-id="11db5-120">View File History</span></span>](../../2014/database-engine/view-file-history.md)  
  
-   [<span data-ttu-id="11db5-121">Anzeigen der Projektversionsgeschichte</span><span class="sxs-lookup"><span data-stu-id="11db5-121">View Project History</span></span>](../../2014/database-engine/view-project-history.md)  
  
-   [<span data-ttu-id="11db5-122">Anzeigen des Dateistatus</span><span class="sxs-lookup"><span data-stu-id="11db5-122">View File Status</span></span>](../../2014/database-engine/view-file-status.md)  
  
-   [<span data-ttu-id="11db5-123">Abrufen von Dateien</span><span class="sxs-lookup"><span data-stu-id="11db5-123">Retrieve Files</span></span>](../../2014/database-engine/retrieve-files.md)  
  
-   [<span data-ttu-id="11db5-124">Angeben einer Version als letzte Version</span><span class="sxs-lookup"><span data-stu-id="11db5-124">Specify a Version as the Latest Version</span></span>](../../2014/database-engine/specify-a-version-as-the-latest-version.md)  
  
-   [<span data-ttu-id="11db5-125">Vergleichen von Dateien</span><span class="sxs-lookup"><span data-stu-id="11db5-125">Compare Files</span></span>](../../2014/database-engine/compare-files.md)  
  
-   [<span data-ttu-id="11db5-126">Freigeben von Dateien</span><span class="sxs-lookup"><span data-stu-id="11db5-126">Share Files</span></span>](../../2014/database-engine/share-files.md)  
  
-   [<span data-ttu-id="11db5-127">Erstellen von Verlaufs- und Statusberichten</span><span class="sxs-lookup"><span data-stu-id="11db5-127">Create History and Status Reports</span></span>](../../2014/database-engine/create-history-and-status-reports.md)  
  
## <a name="see-also"></a><span data-ttu-id="11db5-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="11db5-128">See Also</span></span>  
 [<span data-ttu-id="11db5-129">Grundlagen zur Quellcodeverwaltung</span><span class="sxs-lookup"><span data-stu-id="11db5-129">Source Control Basics</span></span>](../../2014/database-engine/source-control-basics.md)  
  
  
