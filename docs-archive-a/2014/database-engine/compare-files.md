---
title: Dateien vergleichen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- versions [SQL Server], file comparisons
- comparing files
- file comparisons [SQL Server]
ms.assetid: 728811c4-5d7a-4420-abce-f56c5a0994d2
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: f29bf7098f0c73d0b672e20b973b1347349b31f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619357"
---
# <a name="compare-files"></a><span data-ttu-id="9db8d-102">Vergleichen von Dateien</span><span class="sxs-lookup"><span data-stu-id="9db8d-102">Compare Files</span></span>
  <span data-ttu-id="9db8d-103">Sie können Dateien vergleichen, um zu ermitteln, auf welche Weise eine Datei ihren aktuellen Zustand erreicht hat.</span><span class="sxs-lookup"><span data-stu-id="9db8d-103">You can compare files to determine how a file has progressed to its present state.</span></span> <span data-ttu-id="9db8d-104">Wenn Sie z. B. einen Fehler in einem Build Ihres Codeprojekts entdecken, nachdem eine bestimmte Version der Quelldatei eingecheckt wurde, können Sie die aktuelle Dateiversion mit einer vorherigen vergleichen.</span><span class="sxs-lookup"><span data-stu-id="9db8d-104">For example, if you detect a defect in a build of your code project after a particular source file version is checked in, you can compare the current file version to a previous one.</span></span> <span data-ttu-id="9db8d-105">Dies hilft Ihnen bei der dabei, den Code zu ermitteln, der den Fehler verursacht hat.</span><span class="sxs-lookup"><span data-stu-id="9db8d-105">This helps you to pinpoint the code that introduced the defect.</span></span>  
  
 <span data-ttu-id="9db8d-106">Sie können mit [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] eine lokale Kopie eines Projekts oder einer Datei mit der Version vergleichen, die in der Quellcodeverwaltung gespeichert ist, oder Sie können zwei lokale Dateien miteinander vergleichen.</span><span class="sxs-lookup"><span data-stu-id="9db8d-106">You can use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to compare a local copy of a project or file to the version stored in source control, or to compare two local files.</span></span> <span data-ttu-id="9db8d-107">Außerdem können Sie mithilfe **des** Verlaufs Befehls zwei beliebige Quell Code gesteuerte Versionen vergleichen.</span><span class="sxs-lookup"><span data-stu-id="9db8d-107">Also, using the **History** command, you can compare any two source-controlled versions.</span></span>  
  
### <a name="to-compare-files"></a><span data-ttu-id="9db8d-108">So vergleichen Sie Dateien</span><span class="sxs-lookup"><span data-stu-id="9db8d-108">To compare files</span></span>  
  
1.  <span data-ttu-id="9db8d-109">Wählen Sie im Projektmappen-Explorer ein Projekt oder eine der Projektdateien aus.</span><span class="sxs-lookup"><span data-stu-id="9db8d-109">In Solution Explorer, select either a project or one of the project files.</span></span>  
  
2.  <span data-ttu-id="9db8d-110">Zeigen Sie im Menü **Datei** auf **Quell**Code Verwaltung, und klicken Sie auf **vergleichen**.</span><span class="sxs-lookup"><span data-stu-id="9db8d-110">On the **File** menu, point to **Source Control**, and click **Compare**.</span></span>  
  
3.  <span data-ttu-id="9db8d-111">Wählen Sie im Dialogfeld **Differenz Optionen** die entsprechenden Optionen aus, und klicken Sie dann auf **Bericht**.</span><span class="sxs-lookup"><span data-stu-id="9db8d-111">In the **Difference Options** dialog box, select the appropriate options, and then click **Report**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9db8d-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9db8d-112">See Also</span></span>  
 <span data-ttu-id="9db8d-113">[Festlegen und Abrufen von Versionsinformationen](../../2014/database-engine/set-and-retrieve-version-information.md) </span><span class="sxs-lookup"><span data-stu-id="9db8d-113">[Set and Retrieve Version Information](../../2014/database-engine/set-and-retrieve-version-information.md) </span></span>  
 <span data-ttu-id="9db8d-114">[Datei Versionsverlauf anzeigen](../../2014/database-engine/view-file-history.md) </span><span class="sxs-lookup"><span data-stu-id="9db8d-114">[View File History](../../2014/database-engine/view-file-history.md) </span></span>  
 <span data-ttu-id="9db8d-115">[Anzeigen des Projektverlaufs](../../2014/database-engine/view-project-history.md) </span><span class="sxs-lookup"><span data-stu-id="9db8d-115">[View Project History](../../2014/database-engine/view-project-history.md) </span></span>  
 <span data-ttu-id="9db8d-116">[Datei Status anzeigen](../../2014/database-engine/view-file-status.md) </span><span class="sxs-lookup"><span data-stu-id="9db8d-116">[View File Status](../../2014/database-engine/view-file-status.md) </span></span>  
 [<span data-ttu-id="9db8d-117">Abrufen von Dateien</span><span class="sxs-lookup"><span data-stu-id="9db8d-117">Retrieve Files</span></span>](../../2014/database-engine/retrieve-files.md)  
  
  
