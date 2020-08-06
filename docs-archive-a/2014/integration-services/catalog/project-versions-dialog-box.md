---
title: Projektversionen (Dialogfeld) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.ssms.isprojectprop.versions.f1
ms.assetid: a48a387c-2e70-45bc-be2e-26e57a9bb2c4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 998dd194c2a056121fd6f7a404e75c7080b85aa1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721682"
---
# <a name="project-versions-dialog-box"></a><span data-ttu-id="7398b-102">Projektversionen (Dialogfeld)</span><span class="sxs-lookup"><span data-stu-id="7398b-102">Project Versions Dialog Box</span></span>
  <span data-ttu-id="7398b-103">Verwenden Sie das Dialogfeld **Projektversionen** , um Versionen eines Projekts anzuzeigen und eine frühere Version wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="7398b-103">Use the **Project Versions** dialog box to view versions of a project and to restore a previous version.</span></span>  
  
 <span data-ttu-id="7398b-104">Sie können frühere Versionen auch in der Sicht [catalog.object_versions &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-object-versions-ssisdb-database) anzeigen und die gespeicherte Prozedur [catalog.restore_project &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-restore-project-ssisdb-database) verwenden, um frühere Versionen wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="7398b-104">You can also view previous versions in the [catalog.object_versions &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-object-versions-ssisdb-database) view, and use the [catalog.restore_project &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-restore-project-ssisdb-database) stored procedure to restore previous versions.</span></span>  
  
 <span data-ttu-id="7398b-105">**Was möchten Sie tun?**</span><span class="sxs-lookup"><span data-stu-id="7398b-105">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="7398b-106">Öffnen des Dialogfelds "Projektversionen"</span><span class="sxs-lookup"><span data-stu-id="7398b-106">Open the Project Versions dialog box</span></span>](#open_dialog)  
  
-   [<span data-ttu-id="7398b-107">Wiederherstellen einer Projektversion</span><span class="sxs-lookup"><span data-stu-id="7398b-107">Restore a Project Version</span></span>](#restore)  
  
##  <a name="open-the-project-versions-dialog-box"></a><a name="open_dialog"></a> <span data-ttu-id="7398b-108">Öffnen des Dialogfelds "Projektversionen"</span><span class="sxs-lookup"><span data-stu-id="7398b-108">Open the Project Versions dialog box</span></span>  
  
1.  <span data-ttu-id="7398b-109">Stellen Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]eine Verbindung zum [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] -Server her.</span><span class="sxs-lookup"><span data-stu-id="7398b-109">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] server.</span></span>  
  
     <span data-ttu-id="7398b-110">Dies bedeutet, dass eine Verbindung mit der [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] -Instanz hergestellt werden muss, die als Host für die [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] -Datenbank fungiert.</span><span class="sxs-lookup"><span data-stu-id="7398b-110">That is, connect to the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that hosts the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] database.</span></span>  
  
2.  <span data-ttu-id="7398b-111">Erweitern Sie im Objekt-Explorer die Struktur, um den Knoten **Integration Services-Kataloge** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="7398b-111">In Object Explorer, expand the tree to display the **Integration Services Catalogs** node.</span></span>  
  
3.  <span data-ttu-id="7398b-112">Erweitern Sie den Knoten **Integration Services-Kataloge** , um den Knoten **SSISDB** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="7398b-112">Expand the **Integration Services Catalogs** node to display the **SSISDB** node.</span></span>  
  
4.  <span data-ttu-id="7398b-113">Der **SSISDB** -Knoten enthält einen oder mehrere Ordner, wovon jeder ein oder mehrere Projekte enthält.</span><span class="sxs-lookup"><span data-stu-id="7398b-113">The **SSISDB** node contains one or more folders that each contain one or more projects.</span></span> <span data-ttu-id="7398b-114">Erweitern Sie den Ordner, der das gewünschte Projekt enthält.</span><span class="sxs-lookup"><span data-stu-id="7398b-114">Expand the folder that contains the project you are interested in.</span></span>  
  
5.  <span data-ttu-id="7398b-115">Klicken Sie mit der rechten Maustaste auf das Projekt, und klicken Sie anschließend auf **Versionen**.</span><span class="sxs-lookup"><span data-stu-id="7398b-115">Right-click the project, and then click **Versions**.</span></span>  
  
 <span data-ttu-id="7398b-116">Im Dialogfeld **Projektversionen** wird in der Tabelle **Versionen** die Liste der Versionen des Projekts angezeigt, die auf dem Server bereitgestellt wurden, und zwar mit Bereitstellungsdatum und -zeit der Version, Wiederherstellungsdatum und -zeit der Version (wenn eine Wiederherstellung stattgefunden hat), der Versionsbeschreibung und einem Versionsbezeichner.</span><span class="sxs-lookup"><span data-stu-id="7398b-116">In the **Project Versions** dialog box, the **Versions** table displays the list of versions of the project that have been deployed on the server, with the date and time the version was deployed, the date and time the version was restored (if it was restored), the version description, and a version identifier.</span></span> <span data-ttu-id="7398b-117">Die derzeit aktive Version wird durch ein Häkchen in der **aktuellen** Spalte der Tabelle angegeben.</span><span class="sxs-lookup"><span data-stu-id="7398b-117">The currently active version is indicated with a check mark in the **Current** column of the table.</span></span>  
  
##  <a name="restore-a-project-version"></a><a name="restore"></a> <span data-ttu-id="7398b-118">Wiederherstellen einer Projektversion</span><span class="sxs-lookup"><span data-stu-id="7398b-118">Restore a Project Version</span></span>  
 <span data-ttu-id="7398b-119">Um eine frühere Version eines Projekts wiederherzustellen, wählen Sie die Version in der Tabelle **Versionen** aus, und klicken Sie dann auf **Ausgewählte Version wiederherstellen**.</span><span class="sxs-lookup"><span data-stu-id="7398b-119">To restore a previous version of a project, select the version in the **Versions** table, and then click **Restore to Selected Version**.</span></span> <span data-ttu-id="7398b-120">Das Projekt wird in der ausgewählten Version wiederhergestellt, und diese Version wird mit einem Häkchen in der **aktuellen** Spalte der Tabelle **Versionen** angegeben.</span><span class="sxs-lookup"><span data-stu-id="7398b-120">The project is restored to the selected version and that version is indicated with a check mark in the **Current** column of the **Versions** table.</span></span>  
  
  
