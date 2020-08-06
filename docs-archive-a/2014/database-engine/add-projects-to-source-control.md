---
title: Hinzufügen von Projekten zur Quell Code Verwaltung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- adding projects
- projects [SQL Server Management Studio], adding
ms.assetid: fd4616b2-a564-4a66-ac53-d1f5cba213c2
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0afef4ef91e4d80db7e956d03a95a2ecffe1dc4b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610045"
---
# <a name="add-projects-to-source-control"></a><span data-ttu-id="0e71b-102">Hinzufügen von Projekten zur Quellcodeverwaltung</span><span class="sxs-lookup"><span data-stu-id="0e71b-102">Add Projects to Source Control</span></span>
  [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]<span data-ttu-id="0e71b-103">-Projektmappen können mehrere Skriptprojekte hosten.</span><span class="sxs-lookup"><span data-stu-id="0e71b-103">solutions can host multiple script projects.</span></span> <span data-ttu-id="0e71b-104">Wie Sie ein Projekt zur Quellcodeverwaltung hinzufügen, hängt davon ab, ob die entsprechende Projektmappe der Quellcodeverwaltung unterliegt.</span><span class="sxs-lookup"><span data-stu-id="0e71b-104">How you add a project to source control depends upon whether the solution to which the project belongs is under source control.</span></span> <span data-ttu-id="0e71b-105">Wenn die Projektmappe der Quellcodeverwaltung unterliegt, wird beim Einchecken der Projektmappe das Projekt automatisch der Quellcodeverwaltung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="0e71b-105">If the solution is under source control, checking in the solution automatically adds the project to source control.</span></span> <span data-ttu-id="0e71b-106">Weitere Informationen zum Einchecken von Projektmappen finden [Sie unter Einchecken von Dateien](../../2014/database-engine/check-in-files.md).</span><span class="sxs-lookup"><span data-stu-id="0e71b-106">For more information about checking in solutions, see [Check In Files](../../2014/database-engine/check-in-files.md).</span></span>  
  
 <span data-ttu-id="0e71b-107">Wenn die Projektmappe für dieses Projekt nicht der Quellcodeverwaltung unterliegt, können Sie der Quellcodeverwaltung die Projektmappe hinzufügen. Die Quellcodeverwaltung fügt dann automatisch die Projekte der Projektmappe hinzu.</span><span class="sxs-lookup"><span data-stu-id="0e71b-107">If the solution that this project belongs to is not under source control, you can add that solution to source control, which then automatically adds the solution's projects.</span></span> <span data-ttu-id="0e71b-108">Weitere Informationen zum Hinzufügen von Lösungen zur Quell Code Verwaltung finden [Sie unter Hinzufügen von Lösungen zur Quell](../../2014/database-engine/add-solutions-to-source-control.md)Code Verwaltung.</span><span class="sxs-lookup"><span data-stu-id="0e71b-108">For more information about adding solutions to source control, see [Add Solutions to Source Control](../../2014/database-engine/add-solutions-to-source-control.md).</span></span>  
  
 <span data-ttu-id="0e71b-109">Wenn Sie die Projekt Mappe nicht der Quell Code Verwaltung hinzufügen möchten, können Sie das Projekt mit dem Befehl **Auswahl zur Quell Code Verwaltung hinzufügen** manuell hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="0e71b-109">If you do not want to add the solution to source control, you can use the **Add Selection to Source Control** command to add the project manually.</span></span>  
  
 <span data-ttu-id="0e71b-110">Datenbankobjekte werden nicht direkt vom Quellcodeverwaltungsanbieter geschützt. Sie können jedoch Skripts von Datenbankobjekten erstellen und die Skripts unter der Quellcodeverwaltung speichern.</span><span class="sxs-lookup"><span data-stu-id="0e71b-110">Database objects are not directly protected by the source control provider, but you can create scripts of database objects and save the scripts under source control.</span></span>  
  
### <a name="to-add-a-project-to-source-control"></a><span data-ttu-id="0e71b-111">So fügen Sie der Quellcodeverwaltung ein Projekt hinzu</span><span class="sxs-lookup"><span data-stu-id="0e71b-111">To add a project to source control</span></span>  
  
1.  <span data-ttu-id="0e71b-112">Wählen Sie im Projektmappen-Explorer ein Projekt aus.</span><span class="sxs-lookup"><span data-stu-id="0e71b-112">In Solution Explorer, select a project.</span></span>  
  
2.  <span data-ttu-id="0e71b-113">Zeigen Sie im Menü **Datei** auf **Quell**Code Verwaltung, und klicken Sie dann auf **Ausgewählte Projekte zur Quell Code Verwaltung hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="0e71b-113">On the **File** menu, point to **Source Control**, and then click **Add Selected Projects to Source Control**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0e71b-114">Wenn Sie den Befehl **Ausgewählte Projekte zur Quell Code Verwaltung hinzufügen** verwenden, um ein Projekt hinzuzufügen, das zu einer Projekt Mappe mit Quell Code Verwaltung gehört, werden Sie gefragt, ob Sie das Projekt als Unterordner der Lösung für die Quell Code Verwaltung hinzufügen oder das Projekt als separaten Ordner hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="0e71b-114">If you use the **Add Selected Projects to Source Control** command to add a project that belongs to a source-controlled solution, you are prompted whether you want to add the project as a subfolder of the source-controlled solution or to add the project as a separate folder.</span></span>  
  
3.  <span data-ttu-id="0e71b-115">Melden Sie sich beim Quellcodeverwaltungsanbieter an, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="0e71b-115">If prompted, log on to your source control provider.</span></span>  
  
4.  <span data-ttu-id="0e71b-116">Das Dialogfeld **zu SourceSafe-Projekt hinzufügen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0e71b-116">The **Add to SourceSafe Project** dialog box appears.</span></span> <span data-ttu-id="0e71b-117">Der Name des Projekts wird im Feld **Projekt** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0e71b-117">The name of your project appears in the **Project** box.</span></span>  
  
5.  <span data-ttu-id="0e71b-118">Öffnen Sie in der Liste **Ordner** den Ordner, in dem Sie das Projekt platzieren möchten.</span><span class="sxs-lookup"><span data-stu-id="0e71b-118">In the **Folders** list, open the folder where you want to place your project.</span></span> <span data-ttu-id="0e71b-119">Alternativ können Sie auf **Erstellen** klicken, um einen Ordner mit dem Namen zu erstellen, der im Feld **Projekt** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="0e71b-119">Alternatively, you can click **Create** to create a folder with the name displayed in the **Project** box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e71b-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0e71b-120">See Also</span></span>  
 [<span data-ttu-id="0e71b-121">Hinzufügen von Projektmappen und Projekten zur Quellcodeverwaltung</span><span class="sxs-lookup"><span data-stu-id="0e71b-121">Add Solutions and Projects to Source Control</span></span>](../../2014/database-engine/add-solutions-and-projects-to-source-control.md)  
  
  
