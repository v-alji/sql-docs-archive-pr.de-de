---
title: Check-Ins verwalten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- checkins [SQL Server Management Studio]
- checking in files
- source controls [SQL Server Management Studio], checkins
ms.assetid: 293e60f3-15e3-4258-b73a-8baabe15c760
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: a868aafff6d9bd389671544b5f1898e82707d933
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622822"
---
# <a name="manage-checkins"></a><span data-ttu-id="fd9b6-102">Verwalten von Eincheckvorgängen</span><span class="sxs-lookup"><span data-stu-id="fd9b6-102">Manage Checkins</span></span>
  <span data-ttu-id="fd9b6-103">Um Änderungen an einer quellcodeverwalteten Datei anderen Benutzern zur Verfügung zu stellen, müssen Sie die Datei einchecken.</span><span class="sxs-lookup"><span data-stu-id="fd9b6-103">To make changes to a source-controlled file available to other users, you must check in the file.</span></span> <span data-ttu-id="fd9b6-104">Wenn Sie eine Datei einchecken, wird die von Ihnen erstellte Version in den Quellcodeverwaltungsanbieter kopiert und als letzte Dateiversion festgelegt. Sie ist allgemein für Benutzer verfügbar, die die entsprechenden Berechtigungen haben.</span><span class="sxs-lookup"><span data-stu-id="fd9b6-104">When you check in a file, the version you have created is copied to the source control provider, becomes the latest version of the file, and is generally available to users who have the appropriate permissions.</span></span>  
  
 <span data-ttu-id="fd9b6-105">Verwenden Sie [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] , um Dateien einzuchecken.</span><span class="sxs-lookup"><span data-stu-id="fd9b6-105">Use [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to check in files.</span></span> <span data-ttu-id="fd9b6-106">Wenn Sie den Speicher der Quellcodeverwaltung regelmäßig aktualisieren müssen, aber auch die Kontrolle über eine Gruppe von Dateien behalten müssen, können Sie festlegen, dass Dateien, die Sie einchecken, weiterhin für Sie ausgecheckt bleiben.</span><span class="sxs-lookup"><span data-stu-id="fd9b6-106">When you need to update the source control store periodically, but also need to maintain control over a set of files, you can specify that files you check in remain checked out to you.</span></span>  
  
 <span data-ttu-id="fd9b6-107">In der folgenden Tabelle werden die Themen in diesem Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fd9b6-107">The following table describes the topics in this section.</span></span>  
  
|<span data-ttu-id="fd9b6-108">Thema</span><span class="sxs-lookup"><span data-stu-id="fd9b6-108">Topic</span></span>|<span data-ttu-id="fd9b6-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="fd9b6-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="fd9b6-110">Einchecken von Dateien</span><span class="sxs-lookup"><span data-stu-id="fd9b6-110">Check In Files</span></span>](../../2014/database-engine/check-in-files.md)|<span data-ttu-id="fd9b6-111">Enthält Anweisungen zum Einchecken einer Datei, die Sie geändert haben.</span><span class="sxs-lookup"><span data-stu-id="fd9b6-111">Provides instructions on how to check in a file you have modified.</span></span>|  
|[<span data-ttu-id="fd9b6-112">Anzeigen einer Liste geänderter Dateien</span><span class="sxs-lookup"><span data-stu-id="fd9b6-112">View a List of Modified Files</span></span>](../../2014/database-engine/view-a-list-of-modified-files.md)|<span data-ttu-id="fd9b6-113">Erläutert, wie Sie eine Liste der geänderten Dateien anzeigen, die Sie nach dem Arbeiten zusammen einchecken können.</span><span class="sxs-lookup"><span data-stu-id="fd9b6-113">Explains how to display a list of modified files that you can check in together when you are finished working.</span></span>|  
|[<span data-ttu-id="fd9b6-114">Bearbeiten eingecheckter Dateien</span><span class="sxs-lookup"><span data-stu-id="fd9b6-114">Edit Checked-In Files</span></span>](../../2014/database-engine/edit-checked-in-files.md)|<span data-ttu-id="fd9b6-115">Erläutert die Konfiguration der [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]-Umgebung für das Ändern von Dateien, die nicht ausgecheckt sind.</span><span class="sxs-lookup"><span data-stu-id="fd9b6-115">Explains how to configure the [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] environment so that you can modify files that are not checked out.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fd9b6-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fd9b6-116">See Also</span></span>  
 [<span data-ttu-id="fd9b6-117">Verwalten von Auscheckvorgängen</span><span class="sxs-lookup"><span data-stu-id="fd9b6-117">Manage Checkouts</span></span>](../../2014/database-engine/manage-checkouts.md)  
  
  
