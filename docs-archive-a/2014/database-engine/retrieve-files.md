---
title: Dateien abrufen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- version control services [SQL Server], file retrieval
- file retrieval [SQL Server]
- retrieving files
ms.assetid: 37b74426-e262-43b2-a81f-79b1fd1a36ec
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: ebced9ea69f304344893289140687cd6d511e923
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621157"
---
# <a name="retrieve-files"></a><span data-ttu-id="ad7c5-102">Abrufen von Dateien</span><span class="sxs-lookup"><span data-stu-id="ad7c5-102">Retrieve Files</span></span>
  <span data-ttu-id="ad7c5-103">Wenn Sie ein quellcodeverwaltetes Projekt geöffnet haben, können Sie mit [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] lokale Kopien von Projektdateien aus dem Speicher der Quellcodeverwaltung in das lokale Verzeichnis abrufen, in dem sich das Projekt befindet.</span><span class="sxs-lookup"><span data-stu-id="ad7c5-103">After you have opened a source-controlled project, you can use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to retrieve local copies of project files from the source control store to the local directory in which the project resides.</span></span>  
  
 <span data-ttu-id="ad7c5-104">Mit der integrierten Quellcodeverwaltung können Sie Dateien wie folgt abrufen:</span><span class="sxs-lookup"><span data-stu-id="ad7c5-104">You can use integrated source control to retrieve files in the following ways:</span></span>  
  
-   <span data-ttu-id="ad7c5-105">Befehl " **neueste Version (rekursiv)" erhalten**</span><span class="sxs-lookup"><span data-stu-id="ad7c5-105">**Get Latest Version (Recursive)** command</span></span>  
  
     <span data-ttu-id="ad7c5-106">Ruft die jeweils aktuelle eingecheckte Version der ausgewählten Dateien ab.</span><span class="sxs-lookup"><span data-stu-id="ad7c5-106">Retrieves the latest checked in version of the selected files.</span></span> <span data-ttu-id="ad7c5-107">Wenn eine Projektmappe oder ein Projekt ausgewählt ist, wird mit diesem Befehl die jeweils letzte Version aller Projektmappen und Projektdateien abgerufen.</span><span class="sxs-lookup"><span data-stu-id="ad7c5-107">If a solution or project is selected, this command retrieves the latest version of all solution and project files.</span></span>  
  
-   <span data-ttu-id="ad7c5-108">Befehl " **Get** "</span><span class="sxs-lookup"><span data-stu-id="ad7c5-108">**Get** command</span></span>  
  
     <span data-ttu-id="ad7c5-109">Zeigt das **Dialogfeld** abrufen an, mit dem Sie die neueste Version einer ausgewählten Datei abrufen oder eine Teilmenge der Dateien in der ausgewählten Projekt Mappe oder im Projekt abrufen können.</span><span class="sxs-lookup"><span data-stu-id="ad7c5-109">Displays the **Get** dialog box, which you can use to retrieve the latest version of a selected file, or to retrieve a subset of the files in the selected solution or project.</span></span>  
  
### <a name="to-retrieve-the-latest-version-of-all-the-files-in-a-project"></a><span data-ttu-id="ad7c5-110">So rufen Sie die letzte Version aller Dateien in einem Projekt ab</span><span class="sxs-lookup"><span data-stu-id="ad7c5-110">To retrieve the latest version of all the files in a project</span></span>  
  
1.  <span data-ttu-id="ad7c5-111">Wählen Sie im Projektmappen-Explorer das Projekt aus.</span><span class="sxs-lookup"><span data-stu-id="ad7c5-111">In Solution Explorer, select the project.</span></span>  
  
2.  <span data-ttu-id="ad7c5-112">Zeigen Sie im Menü **Datei** auf **Quell**Code Verwaltung, und klicken Sie dann auf **aktuellste Version erhalten (rekursiv)**.</span><span class="sxs-lookup"><span data-stu-id="ad7c5-112">On the **File** menu, point to **Source Control**, and then click **Get Latest Version (Recursive)**.</span></span>  
  
 <span data-ttu-id="ad7c5-113">Die jeweils aktuellen Versionen der Dateien im Projekt werden in den Projektspeicherort auf dem lokalen Datenträger abgerufen.</span><span class="sxs-lookup"><span data-stu-id="ad7c5-113">The most recent versions of the files in the project are retrieved to the project location on your local disk.</span></span>  
  
#### <a name="to-retrieve-only-certain-files-in-a-project"></a><span data-ttu-id="ad7c5-114">So rufen Sie nur bestimmte Dateien in einem Projekt ab</span><span class="sxs-lookup"><span data-stu-id="ad7c5-114">To retrieve only certain files in a project</span></span>  
  
1.  <span data-ttu-id="ad7c5-115">Wählen Sie im Projektmappen-Explorer das Element aus, das Sie abrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="ad7c5-115">In Solution Explorer, select the item you want to retrieve.</span></span>  
  
2.  <span data-ttu-id="ad7c5-116">Zeigen Sie im Menü **Datei** auf **Quell**Code Verwaltung, und klicken Sie dann auf **Get**.</span><span class="sxs-lookup"><span data-stu-id="ad7c5-116">On the **File** menu, point to **Source Control**, and then click **Get**.</span></span>  
  
3.  <span data-ttu-id="ad7c5-117">Klicken Sie im Dialogfeld **Get** auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ad7c5-117">In the **Get** dialog box, click **OK**.</span></span> <span data-ttu-id="ad7c5-118">Wenn Sie eine Projektmappe oder ein Projekt im Projektmappen-Explorer ausgewählt haben, können Sie auch die Kontrollkästchen neben den Elementen deaktivieren, die Sie nicht abrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="ad7c5-118">Alternatively, if you selected a solution or project in Solution Explorer, clear the check boxes that appear next to the items you do not want to retrieve.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad7c5-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ad7c5-119">See Also</span></span>  
 <span data-ttu-id="ad7c5-120">[Dialog Feld "Get" &#40;&#41;der Quell Code Verwaltung](../../2014/database-engine/get-dialog-box-source-control.md) </span><span class="sxs-lookup"><span data-stu-id="ad7c5-120">[Get Dialog Box &#40;Source Control&#41;](../../2014/database-engine/get-dialog-box-source-control.md) </span></span>  
 <span data-ttu-id="ad7c5-121">[Festlegen und Abrufen von Versionsinformationen](../../2014/database-engine/set-and-retrieve-version-information.md) </span><span class="sxs-lookup"><span data-stu-id="ad7c5-121">[Set and Retrieve Version Information](../../2014/database-engine/set-and-retrieve-version-information.md) </span></span>  
 <span data-ttu-id="ad7c5-122">[Anzeigen des Projektverlaufs](../../2014/database-engine/view-project-history.md) </span><span class="sxs-lookup"><span data-stu-id="ad7c5-122">[View Project History](../../2014/database-engine/view-project-history.md) </span></span>  
 [<span data-ttu-id="ad7c5-123">Anzeigen des Dateistatus</span><span class="sxs-lookup"><span data-stu-id="ad7c5-123">View File Status</span></span>](../../2014/database-engine/view-file-status.md)  
  
  
