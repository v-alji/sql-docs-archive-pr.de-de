---
title: Öffnen von Projekten aus der Quell Code Verwaltung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- projects [SQL Server Management Studio], opening
- opening projects
ms.assetid: 942f93a3-e264-4ec4-ba72-a28e0509a527
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 944b121516e3782e35e213e165405b0ecceb7456
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621651"
---
# <a name="open-projects-from-source-control"></a><span data-ttu-id="00e8d-102">Öffnen von Projekten aus der Quellcodeverwaltung</span><span class="sxs-lookup"><span data-stu-id="00e8d-102">Open Projects from Source Control</span></span>
  <span data-ttu-id="00e8d-103">Mit [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] können Sie Projekte direkt aus der Quellcodeverwaltung öffnen.</span><span class="sxs-lookup"><span data-stu-id="00e8d-103">You can use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to open projects directly from source control.</span></span> <span data-ttu-id="00e8d-104">Dabei ruft [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] die letzte Version des Projekts ab und kopiert sie auf den lokalen Datenträger.</span><span class="sxs-lookup"><span data-stu-id="00e8d-104">When you do this, [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] retrieves the latest version of the project and copies it to your local disk.</span></span> <span data-ttu-id="00e8d-105">Außerdem erstellt die [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)]-Umgebung automatisch eine Projektmappe für das Projekt.</span><span class="sxs-lookup"><span data-stu-id="00e8d-105">The [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] environment also creates a solution for the project automatically.</span></span>  
  
 <span data-ttu-id="00e8d-106">Wenn Sie ein Projekt aus der Quellcodeverwaltung geöffnet haben, können Sie die Projektdateien auschecken und ändern.</span><span class="sxs-lookup"><span data-stu-id="00e8d-106">After you have opened a project from source control, you can check out and modify the project files.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="00e8d-107">Das folgende Verfahren sollte nur einmal verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="00e8d-107">The following procedure should only be used once.</span></span> <span data-ttu-id="00e8d-108">Danach sollten Sie das Projekt wie jedes andere Projekt öffnen (durch Klicken auf " **Datei**", " **Öffnen**" und " **Projekt**").</span><span class="sxs-lookup"><span data-stu-id="00e8d-108">Thereafter, you should open the project like any other project (by clicking **File**, **Open**, and then **Project**).</span></span>  
  
### <a name="to-open-a-project-from-source-control"></a><span data-ttu-id="00e8d-109">So öffnen Sie ein Projekt aus der Quellcodeverwaltung</span><span class="sxs-lookup"><span data-stu-id="00e8d-109">To open a project from source control</span></span>  
  
1.  <span data-ttu-id="00e8d-110">Zeigen Sie im Menü **Datei** auf **Quell**Code Verwaltung, und klicken Sie dann auf **aus Quell**Code Verwaltung öffnen.</span><span class="sxs-lookup"><span data-stu-id="00e8d-110">On the **File** menu, point to **Source Control**, and click **Open From Source Control**.</span></span>  
  
2.  <span data-ttu-id="00e8d-111">Melden Sie sich bei [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe an, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="00e8d-111">If prompted, log on to [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe.</span></span>  
  
3.  <span data-ttu-id="00e8d-112">Öffnen Sie im Dialogfeld **Lokales Projekt aus SourceSafe erstellen** den Ordner, der das zu öffnende Projekt enthält.</span><span class="sxs-lookup"><span data-stu-id="00e8d-112">In the **Create local project from SourceSafe** dialog box, open the folder that contains the project to open.</span></span>  
  
4.  <span data-ttu-id="00e8d-113">Das Feld **Neues Projekt im Ordner erstellen** ändert sich, um das lokale Verzeichnis zu identifizieren, in dem das Projekt erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="00e8d-113">The **Create a new project in the folder** box changes to identify the local directory in which the project will be created.</span></span> <span data-ttu-id="00e8d-114">Wenn Sie das Projekt in einem anderen Verzeichnis platzieren möchten, geben Sie den Pfad zum Verzeichnis ein, oder verwenden Sie die Schaltfläche **Durchsuchen** , um das Verzeichnis auf dem lokalen Datenträger zu suchen.</span><span class="sxs-lookup"><span data-stu-id="00e8d-114">If you want to place the project in a different directory, type the path to the directory or use the **Browse** button to locate the directory on your local disk.</span></span>  
  
5.  <span data-ttu-id="00e8d-115">Vergewissern Sie sich im **Feld Neues Projekt im Ordner erstellen**, dass der richtige Ordner angezeigt wird, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="00e8d-115">In the **Create a new project in the folder box**, verify that the correct folder is displayed, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="00e8d-116">Wählen Sie im Dialogfeld Projekt Mappe **Öffnen** das Projekt aus, das Sie öffnen möchten, und klicken Sie auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="00e8d-116">In the **Open Solution** dialog box, select the project you want to open, and click **Open**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00e8d-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="00e8d-117">See Also</span></span>  
 <span data-ttu-id="00e8d-118">[Öffnen von Projektmappen und Projekten aus der Quell Code Verwaltung](../../2014/database-engine/open-solutions-and-projects-from-source-control.md) </span><span class="sxs-lookup"><span data-stu-id="00e8d-118">[Open Solutions and Projects from Source Control](../../2014/database-engine/open-solutions-and-projects-from-source-control.md) </span></span>  
 [<span data-ttu-id="00e8d-119">Öffnen von Projektmappen aus der Quellcodeverwaltung</span><span class="sxs-lookup"><span data-stu-id="00e8d-119">Open Solutions from Source Control</span></span>](../../2014/database-engine/open-solutions-from-source-control.md)  
  
  
