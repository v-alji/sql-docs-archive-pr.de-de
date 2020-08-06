---
title: Quell Code Verwaltungs Verbindungen ändern | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- connections [SQL Server Management Studio], source controls
- source controls [SQL Server Management Studio], connections
ms.assetid: 538e3beb-f99c-4095-bd65-6413e872d26e
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 077a09cdca0c0aff777184f04467ca39592690aa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619368"
---
# <a name="change-source-control-connections"></a><span data-ttu-id="7e524-102">Ändern von Quellcodeverwaltungsverbindungen</span><span class="sxs-lookup"><span data-stu-id="7e524-102">Change Source Control Connections</span></span>
  <span data-ttu-id="7e524-103">Wenn Sie zum ersten Mal eine Projektmappe aus der Quellcodeverwaltung öffnen oder hinzufügen, erstellt der Quellcodeverwaltungsanbieter eine Zuordnung zwischen dem Stammordner des lokalen Projektmappenverzeichnisses und dem zugehörigen Serverordner.</span><span class="sxs-lookup"><span data-stu-id="7e524-103">The first time you add or open a solution from source control, your source control provider creates an association between the root folder of the local solution directory and its corresponding server folder.</span></span>  
  
 <span data-ttu-id="7e524-104">Der Stammordner (auch als einheitlicher Stamm bezeichnet) befindet sich auf dem Client.</span><span class="sxs-lookup"><span data-stu-id="7e524-104">The root folder (also called unified root) resides on the client.</span></span> <span data-ttu-id="7e524-105">Dabei handelt es sich um den Ordner, unter dem sich alle Dateien befinden, auf die eine Projektmappe oder ein Projekt verweist.</span><span class="sxs-lookup"><span data-stu-id="7e524-105">It is the folder beneath which all the files referenced by a solution or project can be found.</span></span> <span data-ttu-id="7e524-106">Um nach der letzten Version einer Projektmappe, deren Verlauf und deren Statusinformationen zu suchen, ermitteln Sie den Serverordner auf dem Quellcodeverwaltungsserver.</span><span class="sxs-lookup"><span data-stu-id="7e524-106">To find the latest version of a solution, its history, and its status information, locate the server folder, which resides on the source control server.</span></span> <span data-ttu-id="7e524-107">In [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe werden Serverordner als Projekte bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="7e524-107">In [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe, server folders are called projects.</span></span>  
  
 <span data-ttu-id="7e524-108">In vielen Situationen müssen Sie die Bindung oder Verbindung einer Projektmappe zum Serverordner aufheben.</span><span class="sxs-lookup"><span data-stu-id="7e524-108">In many situations, you need to unbind or disconnect a solution from its server folder.</span></span> <span data-ttu-id="7e524-109">Wenn z. B. der Computer, auf dem sich der Quellcodeverwaltungsanbieter befindet, nicht verfügbar ist, können Sie eine Verbindung mit einem Sicherungscomputer herstellen, die Bindung der Projektmappe mit einem gesicherten Serverordner wieder herstellen und die Arbeit wie gewohnt fortsetzen.</span><span class="sxs-lookup"><span data-stu-id="7e524-109">For example, if the computer on which your source control provider resides is unavailable, you can connect to a backup computer, rebind your solution to a backed-up server folder, and resume working normally.</span></span> <span data-ttu-id="7e524-110">Oder wenn ein quellcodeverwaltetes Projekt verzweigt ist, müssen Sie möglicherweise eine Bindung zwischen der Projektmappe und dem Serverordner einrichten, in dem sich die neue Projektversion befindet.</span><span class="sxs-lookup"><span data-stu-id="7e524-110">Also, if a source control project is forked, you may have to bind your solution to the server folder where the new project version resides.</span></span>  
  
 <span data-ttu-id="7e524-111">Über die Benutzeroberfläche des Quellcodeverwaltungsanbieters können Sie den Serverordner ändern, zu dem die Bindung der Projektmappe besteht.</span><span class="sxs-lookup"><span data-stu-id="7e524-111">Use the user interface of the source control provider to change the server folder that a solution is bound to.</span></span> <span data-ttu-id="7e524-112">Sie können die Benutzeroberfläche der Quellcodeverwaltung aus der [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]-Umgebung öffnen.</span><span class="sxs-lookup"><span data-stu-id="7e524-112">You can open the source control user interface from within the [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] environment.</span></span>  
  
#### <a name="to-open-the-source-control-user-interface-from-the-studio-environment"></a><span data-ttu-id="7e524-113">So öffnen Sie die Benutzeroberfläche der Quellcodeverwaltung aus der SQL Server Management Studio-Umgebung</span><span class="sxs-lookup"><span data-stu-id="7e524-113">To open the source control user interface from the Studio environment</span></span>  
  
1.  <span data-ttu-id="7e524-114">Zeigen Sie im Menü **Datei** auf **Quell**Code Verwaltung, und klicken Sie dann auf **Microsoft Visual SourceSafe starten**.</span><span class="sxs-lookup"><span data-stu-id="7e524-114">On the **File** menu, point to **Source Control**, and then click **Launch Microsoft Visual SourceSafe**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e524-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7e524-115">See Also</span></span>  
 <span data-ttu-id="7e524-116">[Grundlagen der Quellen Verwaltung](../../2014/database-engine/source-control-basics.md) </span><span class="sxs-lookup"><span data-stu-id="7e524-116">[Source Control Basics](../../2014/database-engine/source-control-basics.md) </span></span>  
 <span data-ttu-id="7e524-117">[Optionen für die Quell Code Verwaltung festlegen](../../2014/database-engine/set-source-control-options.md) </span><span class="sxs-lookup"><span data-stu-id="7e524-117">[Set Source Control Options](../../2014/database-engine/set-source-control-options.md) </span></span>  
 [<span data-ttu-id="7e524-118">Ausschließen von Dateien aus der Quellcodeverwaltung</span><span class="sxs-lookup"><span data-stu-id="7e524-118">Exclude Files from Source Control</span></span>](../../2014/database-engine/exclude-files-from-source-control.md)  
  
  
