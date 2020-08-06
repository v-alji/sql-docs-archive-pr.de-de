---
title: Anzeigen des Projektverlaufs | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- viewing project history
- version control services [SQL Server], project history
- projects [SQL Server Management Studio], historical information
- historical information [SQL Server], projects
ms.assetid: be0ea2ac-4a35-429c-9c9e-4001ea9035a4
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 85028141050e19e6ed6394a5bb17709ac8f906ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622233"
---
# <a name="view-project-history"></a><span data-ttu-id="07b84-102">Anzeigen der Projektversionsgeschichte</span><span class="sxs-lookup"><span data-stu-id="07b84-102">View Project History</span></span>
  <span data-ttu-id="07b84-103">Der Versionsverlauf eines [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe (VSS)-Projekts enthält eine Liste aller Aktionen, die für die einzelnen Projektdateien ausgeführt wurden, einschließlich Erstellen, Hinzufügen, Löschen und Wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="07b84-103">The history of a [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe (VSS) project includes a list of all the actions taken on each of the project files, including file creation, addition, deletion, and recovery.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="07b84-104">Ein Visual SourceSafe-Projekt wird häufig als Serverordner der Quellcodeverwaltung bezeichnet. Dabei handelt es sich um den Speicherort der Serverversion einer Datei unter Quellcodeverwaltung auf dem Server.</span><span class="sxs-lookup"><span data-stu-id="07b84-104">A Visual SourceSafe project is more commonly referred to as the source control server folder, the location where the server version of a source-controlled file is stored on the server.</span></span>  
  
 <span data-ttu-id="07b84-105">Mit [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] können Sie die Versionsgeschichte des Visual SourceSafe-Projekts untersuchen, zu dem die zurzeit geladene Projektmappe gehört.</span><span class="sxs-lookup"><span data-stu-id="07b84-105">You can use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to examine the history of the Visual SourceSafe project to which the currently loaded solution belongs.</span></span> <span data-ttu-id="07b84-106">Basierend auf den Informationen, die als Teil der Projektversionsgeschichte angezeigt werden, können Sie lokale Kopien von Dateiversionen abrufen, gelöschte Versionen wiederherstellen oder eine Dateiversion in mehreren Projekten freigeben.</span><span class="sxs-lookup"><span data-stu-id="07b84-106">Based on the information displayed as part of the history of a project, you can retrieve local copies of file versions, restore deleted versions, or share a file version between projects.</span></span>  
  
### <a name="to-view-the-history-of-a-vss-project"></a><span data-ttu-id="07b84-107">So zeigen Sie die Versionsgeschichte eines VSS-Projekts an</span><span class="sxs-lookup"><span data-stu-id="07b84-107">To view the history of a VSS project</span></span>  
  
1.  <span data-ttu-id="07b84-108">Wählen Sie im Projektmappen-Explorer das Projekt aus.</span><span class="sxs-lookup"><span data-stu-id="07b84-108">In Solution Explorer, select the project.</span></span>  
  
2.  <span data-ttu-id="07b84-109">Zeigen Sie im Menü **Datei** auf **Quell** Code Verwaltung, und klicken Sie auf **Verlauf anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="07b84-109">On the **File** menu, point to **Source Control** and click **View History**.</span></span>  
  
3.  <span data-ttu-id="07b84-110">Führen Sie im Dialogfeld **Verlauf von** \<Project> eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="07b84-110">In the **History of** \<Project> dialog box, perform any of the following actions:</span></span>  
  
    -   <span data-ttu-id="07b84-111">Zeigen Sie für eine ausgewählte Datei die Kopie des Quellcodeverwaltungssystems an.</span><span class="sxs-lookup"><span data-stu-id="07b84-111">View the source control system's copy of a selected file.</span></span>  
  
    -   <span data-ttu-id="07b84-112">Zeigen Sie weitere Informationen zu einer ausgewählten Datei an.</span><span class="sxs-lookup"><span data-stu-id="07b84-112">View detailed information about a selected file.</span></span>  
  
    -   <span data-ttu-id="07b84-113">Rufen Sie eine ausgewählte Datei auf den lokalen Datenträger ab.</span><span class="sxs-lookup"><span data-stu-id="07b84-113">Retrieve a selected file to your local disk.</span></span>  
  
    -   <span data-ttu-id="07b84-114">Checken Sie eine ausgewählte Datei aus.</span><span class="sxs-lookup"><span data-stu-id="07b84-114">Check out a selected file.</span></span>  
  
    -   <span data-ttu-id="07b84-115">Geben Sie eine ausgewählte Datei in zwei Projekten unter Quellcodeverwaltung frei.</span><span class="sxs-lookup"><span data-stu-id="07b84-115">Share a selected file between two source control projects.</span></span>  
  
    -   <span data-ttu-id="07b84-116">Exportieren Sie den Versionsgeschichtebericht an einen Drucker, in eine Datei oder in die Zwischenablage.</span><span class="sxs-lookup"><span data-stu-id="07b84-116">Export the history report to a printer, a file, or the Clipboard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07b84-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="07b84-117">See Also</span></span>  
 <span data-ttu-id="07b84-118">[Festlegen und Abrufen von Versionsinformationen](../../2014/database-engine/set-and-retrieve-version-information.md) </span><span class="sxs-lookup"><span data-stu-id="07b84-118">[Set and Retrieve Version Information](../../2014/database-engine/set-and-retrieve-version-information.md) </span></span>  
 <span data-ttu-id="07b84-119">[Datei Status anzeigen](../../2014/database-engine/view-file-status.md) </span><span class="sxs-lookup"><span data-stu-id="07b84-119">[View File Status](../../2014/database-engine/view-file-status.md) </span></span>  
 <span data-ttu-id="07b84-120">[Dateien abrufen](../../2014/database-engine/retrieve-files.md) </span><span class="sxs-lookup"><span data-stu-id="07b84-120">[Retrieve Files](../../2014/database-engine/retrieve-files.md) </span></span>  
 [<span data-ttu-id="07b84-121">Vergleichen von Dateien</span><span class="sxs-lookup"><span data-stu-id="07b84-121">Compare Files</span></span>](../../2014/database-engine/compare-files.md)  
  
  
