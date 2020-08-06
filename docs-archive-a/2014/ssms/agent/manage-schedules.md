---
title: Zeitpläne verwalten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.job.manageschedules.f1
ms.assetid: f56c0736-dccc-41d2-afcf-71344aff143a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6fa18d620d630484815966372d5de83bb52e8caf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616348"
---
# <a name="manage-schedules"></a><span data-ttu-id="00ea6-102">Zeitpläne verwalten</span><span class="sxs-lookup"><span data-stu-id="00ea6-102">Manage Schedules</span></span>
  <span data-ttu-id="00ea6-103">Ermöglicht das Anzeigen und Ändern von Eigenschaften für [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Auftrags Zeitpläne des-Agents.</span><span class="sxs-lookup"><span data-stu-id="00ea6-103">Allows you to view and change properties for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job schedules.</span></span>  
  
## <a name="options"></a><span data-ttu-id="00ea6-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="00ea6-104">Options</span></span>  
 <span data-ttu-id="00ea6-105">**Verfügbare Zeitpläne**</span><span class="sxs-lookup"><span data-stu-id="00ea6-105">**Available schedules**</span></span>  
 <span data-ttu-id="00ea6-106">Führt die für diesen Benutzer verfügbaren Zeitpläne auf.</span><span class="sxs-lookup"><span data-stu-id="00ea6-106">Lists the schedules available for this user.</span></span> <span data-ttu-id="00ea6-107">Ein Auftrag und ein Zeitplan müssen denselben Besitzer haben.</span><span class="sxs-lookup"><span data-stu-id="00ea6-107">Notice that a job and a schedule must have the same owner.</span></span> <span data-ttu-id="00ea6-108">Deshalb enthält die Liste nur Zeitpläne, die dem Besitzer des Auftrags gehören.</span><span class="sxs-lookup"><span data-stu-id="00ea6-108">Therefore, this list only includes schedules owned by the owner of the job.</span></span>  
  
 <span data-ttu-id="00ea6-109">**Name**</span><span class="sxs-lookup"><span data-stu-id="00ea6-109">**Name**</span></span>  
 <span data-ttu-id="00ea6-110">Zeigt den Namen des Zeitplans an.</span><span class="sxs-lookup"><span data-stu-id="00ea6-110">Displays the name of the schedule.</span></span>  
  
 <span data-ttu-id="00ea6-111">**Aktiviert**</span><span class="sxs-lookup"><span data-stu-id="00ea6-111">**Enabled**</span></span>  
 <span data-ttu-id="00ea6-112">Wählen Sie diese Option aus, um den Zeitplan zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="00ea6-112">Select this option to enable the schedule.</span></span>  
  
 <span data-ttu-id="00ea6-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="00ea6-113">**Description**</span></span>  
 <span data-ttu-id="00ea6-114">Beschreibt die Bedingungen, unter denen der Zeitplan den Auftrag ausführt.</span><span class="sxs-lookup"><span data-stu-id="00ea6-114">Describes the conditions under which the schedule runs the job.</span></span>  
  
 <span data-ttu-id="00ea6-115">**Aufträge im Zeitplan**</span><span class="sxs-lookup"><span data-stu-id="00ea6-115">**Jobs in schedule**</span></span>  
 <span data-ttu-id="00ea6-116">Listet die Auftragsnummern auf, die an den Zeitplan angefügt sind.</span><span class="sxs-lookup"><span data-stu-id="00ea6-116">Lists the job numbers attached to the schedule.</span></span> <span data-ttu-id="00ea6-117">Wenn Sie auf eine Nummer klicken, zeigen Sie die Eigenschaften des Auftrags an.</span><span class="sxs-lookup"><span data-stu-id="00ea6-117">Click a number to view the properties of the job.</span></span>  
  
 <span data-ttu-id="00ea6-118">**Neu**</span><span class="sxs-lookup"><span data-stu-id="00ea6-118">**New**</span></span>  
 <span data-ttu-id="00ea6-119">Klicken Sie auf diese Schaltfläche, um einen neuen Zeitplan zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="00ea6-119">Click this button to create a new schedule.</span></span>  
  
 <span data-ttu-id="00ea6-120">**Löschen**</span><span class="sxs-lookup"><span data-stu-id="00ea6-120">**Delete**</span></span>  
 <span data-ttu-id="00ea6-121">Klicken Sie auf diese Schaltfläche, um den ausgewählten Zeitplan zu löschen.</span><span class="sxs-lookup"><span data-stu-id="00ea6-121">Click this button to delete the selected schedule.</span></span>  
  
 <span data-ttu-id="00ea6-122">**Eigenschaften**</span><span class="sxs-lookup"><span data-stu-id="00ea6-122">**Properties**</span></span>  
 <span data-ttu-id="00ea6-123">Klicken Sie auf diese Schaltfläche, um die Eigenschaften des ausgewählten Zeitplans zu ändern.</span><span class="sxs-lookup"><span data-stu-id="00ea6-123">Click this button to change the properties of the selected schedule.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00ea6-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="00ea6-124">See Also</span></span>  
 [<span data-ttu-id="00ea6-125">Anlegen und Zuweisen von Zeitplänen zu Aufträgen</span><span class="sxs-lookup"><span data-stu-id="00ea6-125">Create and Attach Schedules to Jobs</span></span>](create-and-attach-schedules-to-jobs.md)  
  
  
