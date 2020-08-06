---
title: Hinzufügen von Lösungen zur Quell Code Verwaltung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- adding solutions
- solutions [SQL Server Management Studio], adding
ms.assetid: b9e36569-616d-4e47-9140-0978a9bfe923
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 1c72949fd8257332a36af52ab287ed326eed5274
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698534"
---
# <a name="add-solutions-to-source-control"></a><span data-ttu-id="e66c5-102">Hinzufügen von Projektmappen zur Quellcodeverwaltung</span><span class="sxs-lookup"><span data-stu-id="e66c5-102">Add Solutions to Source Control</span></span>
  <span data-ttu-id="e66c5-103">Wenn Sie eine Projektmappe zur Quellcodeverwaltung hinzufügen, möchten Sie in der Regel die gesamte Projektmappe und alle Projekte hinzufügen, die darin enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="e66c5-103">When you add a solution to source control, you usually want to add the entire solution and all the projects it contains.</span></span> <span data-ttu-id="e66c5-104">Sie können Projektmappen mit [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] zur Quellcodeverwaltung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e66c5-104">You can use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to add a solution to source control.</span></span>  
  
 <span data-ttu-id="e66c5-105">Ein [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]-Projekt befindet sich vollständig auf dem lokalen Datenträger.</span><span class="sxs-lookup"><span data-stu-id="e66c5-105">A [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] project resides completely on your local disk.</span></span> <span data-ttu-id="e66c5-106">Sie bearbeiten, speichern und erstellen Projekte lokal.</span><span class="sxs-lookup"><span data-stu-id="e66c5-106">You edit, save, and build projects locally.</span></span> <span data-ttu-id="e66c5-107">Nachdem Sie das Projekt der Quell Code Verwaltung hinzugefügt haben, können Sie den Befehl **Auschecken** verwenden, um die Dateien des Projekts aus der Quell Code Verwaltung zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="e66c5-107">After adding the project to source control, you can use the **Check Out** command to check the project's files out of source control.</span></span>  
  
### <a name="to-add-a-solution-to-source-control"></a><span data-ttu-id="e66c5-108">So fügen Sie eine Projektmappe zur Quellcodeverwaltung hinzu</span><span class="sxs-lookup"><span data-stu-id="e66c5-108">To add a solution to source control</span></span>  
  
1.  <span data-ttu-id="e66c5-109">Wählen Sie im Projektmappen-Explorer die Projektmappe aus, die Sie hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="e66c5-109">In Solution Explorer, select the solution you want to add.</span></span>  
  
2.  <span data-ttu-id="e66c5-110">Zeigen Sie im Menü **Datei** auf **Quell**Code Verwaltung, und klicken Sie dann auf Projekt Mappe zur Quell Code Verwaltung **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="e66c5-110">On the **File** menu, point to **Source Control**, and then click **Add Solution to Source Control**.</span></span>  
  
3.  <span data-ttu-id="e66c5-111">Melden Sie sich beim Quellcodeverwaltungsanbieter an, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="e66c5-111">If prompted, log on to your source control provider.</span></span>  
  
4.  <span data-ttu-id="e66c5-112">Das Dialogfeld **zu SourceSafe-Projekt hinzufügen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e66c5-112">The **Add to SourceSafe Project** dialog box appears.</span></span> <span data-ttu-id="e66c5-113">Der Name des Projekts wird im Feld **Projekt** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e66c5-113">The name of your project appears in the **Project** box.</span></span>  
  
5.  <span data-ttu-id="e66c5-114">Öffnen Sie in der Liste **Ordner** den Ordner, in dem Sie das Projekt platzieren möchten.</span><span class="sxs-lookup"><span data-stu-id="e66c5-114">In the **Folders** list, open the folder where you want to place your project.</span></span> <span data-ttu-id="e66c5-115">Alternativ können Sie auf **Erstellen** klicken, um einen Ordner mit dem Namen zu erstellen, der im Feld **Projekt** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="e66c5-115">Alternatively, you can click **Create** to create a folder with the name displayed in the **Project** box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e66c5-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e66c5-116">See Also</span></span>  
 <span data-ttu-id="e66c5-117">[Hinzufügen von Projektmappen und Projekten zur Quell Code Verwaltung](../../2014/database-engine/add-solutions-and-projects-to-source-control.md) </span><span class="sxs-lookup"><span data-stu-id="e66c5-117">[Add Solutions and Projects to Source Control](../../2014/database-engine/add-solutions-and-projects-to-source-control.md) </span></span>  
 [<span data-ttu-id="e66c5-118">Hinzufügen von Projekten zur Quellcodeverwaltung</span><span class="sxs-lookup"><span data-stu-id="e66c5-118">Add Projects to Source Control</span></span>](../../2014/database-engine/add-projects-to-source-control.md)  
  
  
