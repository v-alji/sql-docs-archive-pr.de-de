---
title: Ausschließen von Dateien aus der Quell Code Verwaltung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- excluding files from source control
- source controls [SQL Server Management Studio], file exclusions
ms.assetid: 7dcb6514-db5c-49eb-8b5a-2c766ce39aa7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 9fb3c5ccb4fcaad062236eec6d04f995557dc2b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701600"
---
# <a name="exclude-files-from-source-control"></a><span data-ttu-id="1b544-102">Ausschließen von Dateien aus der Quellcodeverwaltung</span><span class="sxs-lookup"><span data-stu-id="1b544-102">Exclude Files from Source Control</span></span>
  <span data-ttu-id="1b544-103">Wenn die Projekt Mappe, an der Sie arbeiten, Dateien enthält, für die keine Quell Code Verwaltungsdienste erforderlich sind, können Sie den Befehl **aus Quell** Code Verwaltung ausschließen verwenden, um die Datei aus der Quell Code Verwaltung auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="1b544-103">If the solution you are working on contains files that do not require source control services, you can use the **Exclude from Source Control** command to exclude the file from source control.</span></span> <span data-ttu-id="1b544-104">Dabei bleibt die Datei zwar in der [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe-Datenbank, wird aber nicht mehr mit dem Projekt ein- oder ausgecheckt.</span><span class="sxs-lookup"><span data-stu-id="1b544-104">When you do this, the file remains in the [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe database, but it is no longer checked in or out with the project.</span></span>  
  
 <span data-ttu-id="1b544-105">Sie sollten den Befehl **aus Quell** Code Verwaltung ausschließen nur für generierte Dateien verwenden.</span><span class="sxs-lookup"><span data-stu-id="1b544-105">You should use the **Exclude from Source Control** command only on generated files.</span></span> <span data-ttu-id="1b544-106">Eine generierte Datei kann auf [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] Grundlage des Inhalts einer anderen Datei in der Projekt Mappe vollständig neu erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="1b544-106">A generated file is one that can be entirely re-created by [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] based on the contents of another file in the solution.</span></span>  
  
### <a name="to-exclude-a-file-from-source-control"></a><span data-ttu-id="1b544-107">So schließen Sie eine Datei aus der Quellcodeverwaltung aus</span><span class="sxs-lookup"><span data-stu-id="1b544-107">To exclude a file from source control</span></span>  
  
1.  <span data-ttu-id="1b544-108">Wählen Sie die auszuschließende Datei im Projektmappen-Explorer aus.</span><span class="sxs-lookup"><span data-stu-id="1b544-108">In Solution Explorer, select the file to exclude.</span></span>  
  
2.  <span data-ttu-id="1b544-109">Zeigen Sie im Menü **Datei** auf **Quell**Code Verwaltung, und klicken Sie **Exclude** dann auf *\<file name>* **aus Quell**Code Verwaltung ausschließen.</span><span class="sxs-lookup"><span data-stu-id="1b544-109">On the **File** menu, point to **Source Control**, and then click **Exclude** *\<file name>* **from Source Control**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b544-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1b544-110">See Also</span></span>  
 <span data-ttu-id="1b544-111">[Grundlagen der Quellen Verwaltung](../../2014/database-engine/source-control-basics.md) </span><span class="sxs-lookup"><span data-stu-id="1b544-111">[Source Control Basics](../../2014/database-engine/source-control-basics.md) </span></span>  
 <span data-ttu-id="1b544-112">[Optionen für die Quell Code Verwaltung festlegen](../../2014/database-engine/set-source-control-options.md) </span><span class="sxs-lookup"><span data-stu-id="1b544-112">[Set Source Control Options](../../2014/database-engine/set-source-control-options.md) </span></span>  
 [<span data-ttu-id="1b544-113">Ändern von Quellcodeverwaltungsverbindungen</span><span class="sxs-lookup"><span data-stu-id="1b544-113">Change Source Control Connections</span></span>](../../2014/database-engine/change-source-control-connections.md)  
  
  
