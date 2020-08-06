---
title: 'Neue System Rollenzuweisungen: Seite "System Rollenzuweisungen bearbeiten" (Berichts-Manager) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 62a22ab9-1eb4-4ce5-8dd7-06b5ed2d9a2a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6e04ec18b8ee27c5897156753c1e4f7991991eae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609702"
---
# <a name="new-system-role-assignments-edit-system-role-assignments-page-report-manager"></a><span data-ttu-id="20a3f-102">Neue Systemrollenzuweisung: Systemrollenzuweisung bearbeiten (Seite, Berichts-Manager)</span><span class="sxs-lookup"><span data-stu-id="20a3f-102">New System Role Assignments: Edit System Role Assignments Page (Report Manager)</span></span>
  <span data-ttu-id="20a3f-103">Verwenden Sie zum Definieren der Sicherheit für den Berichtsserver die Seite Neue Systemrollenzuweisung oder Systemrollenzuweisung bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="20a3f-103">Use the New System Role Assignments or Edit System Role Assignments page to define security for the report server.</span></span> <span data-ttu-id="20a3f-104">Die gesamte Sicherheit wird durch Rollenzuweisungen definiert, in denen spezifische Benutzer oder Gruppen zu Aufgaben zugeordnet werden, die diese ausführen können.</span><span class="sxs-lookup"><span data-stu-id="20a3f-104">All security is defined through role assignments that map specific users or groups to the tasks that they can perform.</span></span> <span data-ttu-id="20a3f-105">Die Aufgabenliste stellt eine Rollendefinition dar, die Sie beim Erstellen einer Rollenzuweisung auswählen.</span><span class="sxs-lookup"><span data-stu-id="20a3f-105">The task list is represented as a role definition that you select when making the role assignment.</span></span>  
  
 <span data-ttu-id="20a3f-106">Auf der Systemebene gelten die von Ihnen erstellten oder geänderten Rollenzuweisungen für den gesamten Berichtsserver.</span><span class="sxs-lookup"><span data-stu-id="20a3f-106">At the system level, the role assignments that you create or modify apply to the report server as a whole.</span></span> <span data-ttu-id="20a3f-107">Die Berechtigung zum Erstellen freigegebener Zeitpläne wird z. B. auf der Systemebene angegeben, da freigegebene Zeitpläne im gesamten System verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="20a3f-107">For example, the ability to create shared schedules is specified at the system level because shared schedules are used throughout the system.</span></span>  
  
 <span data-ttu-id="20a3f-108">Standardmäßig stellt Reporting Services zwei vordefinierte Systemebenenrollen bereit:</span><span class="sxs-lookup"><span data-stu-id="20a3f-108">By default, Reporting Services provides two predefined system level roles:</span></span>  
  
-   <span data-ttu-id="20a3f-109">Die Systembenutzerrolle umfasst Aufgaben, die es Benutzern ermöglichen, Berichtsservereigenschaften und freigegebene Zeitpläne anzuzeigen. Außerdem können Benutzer Berichtsdefinitionen ausführen, wodurch sie Berichte mit Durchklicken, die auf dem Berichtsserver veröffentlicht wurden, anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="20a3f-109">System User includes tasks that allow users to view report server properties and shared schedules, and to execute report definitions, which allows users to view clickthrough reports that have been published to the report server.</span></span> <span data-ttu-id="20a3f-110">Die meisten Benutzer sollten dieser Rolle zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="20a3f-110">Most users should be assigned to this role.</span></span>  
  
-   <span data-ttu-id="20a3f-111">Systemadministrator schließt Aufgaben für das Erstellen und Verwalten freigegebener Zeitpläne, das Festlegen von Servereigenschaften und das Erstellen von Rollenzuweisungen auf Systemebene für andere Benutzer ein.</span><span class="sxs-lookup"><span data-stu-id="20a3f-111">System Administrator includes tasks for creating and managing shared schedules, setting server properties, and creating system-level role assignments for other users.</span></span> <span data-ttu-id="20a3f-112">Nur wenige Benutzer benötigen Berechtigungen dieser Ebene.</span><span class="sxs-lookup"><span data-stu-id="20a3f-112">Few users require permissions at this level.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="20a3f-113">Navigation</span><span class="sxs-lookup"><span data-stu-id="20a3f-113">Navigation</span></span>  
 <span data-ttu-id="20a3f-114">Verwenden Sie folgendes Verfahren, um zu dieser Position in der Benutzeroberfläche zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="20a3f-114">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-new-system-role-assignments-or-edit-system-role-assignments-page"></a><span data-ttu-id="20a3f-115">So öffnen Sie die Seite 'Neue Systemrollenzuweisung' oder 'Systemrollenzuweisungen bearbeiten'</span><span class="sxs-lookup"><span data-stu-id="20a3f-115">To open the New System Role Assignments or Edit System Role Assignments page</span></span>  
  
1.  <span data-ttu-id="20a3f-116">Öffnen Sie den Berichts-Manager.</span><span class="sxs-lookup"><span data-stu-id="20a3f-116">Open Report Manager.</span></span>  
  
2.  <span data-ttu-id="20a3f-117">Klicken Sie in der oberen rechten Ecke der Seite auf **Siteeinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="20a3f-117">At the top of the page, in the right-hand corner, click **Site Settings**.</span></span> <span data-ttu-id="20a3f-118">Dadurch wird die Seite Allgemeine Eigenschaften der Website geöffnet.</span><span class="sxs-lookup"><span data-stu-id="20a3f-118">This opens the General properties page for the site.</span></span>  
  
3.  <span data-ttu-id="20a3f-119">Wählen Sie die Registerkarte **Sicherheit** aus. Sie müssen über Inhalts-Manager-und System Administrator Berechtigungen verfügen, um auf diese Seite zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="20a3f-119">Select the **Security** tab. You must have Content Manager and System Administrator permissions to access this page.</span></span>  
  
4.  <span data-ttu-id="20a3f-120">Um eine neue Rollenzuweisung zu erstellen, klicken Sie auf der Symbolleiste auf **Neue Rollenzuweisung** .</span><span class="sxs-lookup"><span data-stu-id="20a3f-120">To create a new role assignment, click **New Role Assignment** in the toolbar.</span></span> <span data-ttu-id="20a3f-121">Um eine vorhandene Rollenzuweisung zu bearbeiten, klicken Sie neben einer Gruppe oder einem Benutzer auf der Eigenschaftenseite Sicherheit auf **Bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="20a3f-121">To edit an existing role assignment, click **Edit** next to a group or user on the Security properties page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="20a3f-122">Tastatur</span><span class="sxs-lookup"><span data-stu-id="20a3f-122">Options</span></span>  
 <span data-ttu-id="20a3f-123">**Gruppe oder Benutzer**</span><span class="sxs-lookup"><span data-stu-id="20a3f-123">**Group or User**</span></span>  
 <span data-ttu-id="20a3f-124">Geben Sie den Namen eines Gruppen- oder Benutzerkontos in der Domäne ein.</span><span class="sxs-lookup"><span data-stu-id="20a3f-124">Type the name of a group or user account in your domain.</span></span> <span data-ttu-id="20a3f-125">Wenn der Berichtsserver unter einem lokalen Konto ausgeführt wird, müssen Sie lokale Gruppen oder Benutzer angeben.</span><span class="sxs-lookup"><span data-stu-id="20a3f-125">If the report server is running under a local account, you must specify local groups or users.</span></span> <span data-ttu-id="20a3f-126">Wenn der Berichtsserver unter einem Domänenkonto ausgeführt wird, müssen Sie Domänengruppen oder -benutzer angeben.</span><span class="sxs-lookup"><span data-stu-id="20a3f-126">If the report server is running under a domain account, you must specify domain groups or users.</span></span> <span data-ttu-id="20a3f-127">Geben Sie das Konto im folgenden Format ein: \<domain> \\<Konto \> .</span><span class="sxs-lookup"><span data-stu-id="20a3f-127">Enter the account in this format: \<domain>\\<account\>.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="20a3f-128">Dieses Feld ist nur auf der Seite Neue Rollenzuweisung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="20a3f-128">This box is available only on the New Role Assignment page.</span></span>  
  
 <span data-ttu-id="20a3f-129">**Rollen**</span><span class="sxs-lookup"><span data-stu-id="20a3f-129">**Roles**</span></span>  
 <span data-ttu-id="20a3f-130">Stellt eine Liste von Rollen auf Systemebene bereit, die Sie anderen Benutzern zuweisen können.</span><span class="sxs-lookup"><span data-stu-id="20a3f-130">Provides a list of system-level roles that you can assign to other users.</span></span> <span data-ttu-id="20a3f-131">Sie können mehrere Rollen für eine einzelne Rollenzuweisung angeben.</span><span class="sxs-lookup"><span data-stu-id="20a3f-131">You can specify multiple roles for a single role assignment.</span></span>  
  
 <span data-ttu-id="20a3f-132">Der Berichts-Manager zeigt die Aufgaben in jeder Rolle nicht an und bietet auch keine Möglichkeit, Aufgaben hinzuzufügen oder sie zu ändern.</span><span class="sxs-lookup"><span data-stu-id="20a3f-132">Report Manager does not display the tasks in each role or provide a way to add or modify the tasks.</span></span> <span data-ttu-id="20a3f-133">Sie müssen die Rollen so verwenden, wie sie definiert sind.</span><span class="sxs-lookup"><span data-stu-id="20a3f-133">You must use the roles as they are defined.</span></span> <span data-ttu-id="20a3f-134">Verwenden Sie, um Rollen zu erstellen, zu ändern oder zu löschen [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="20a3f-134">To create, modify, or delete roles, use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span></span> <span data-ttu-id="20a3f-135">Weitere Informationen finden Sie unter [Erstellen, Löschen oder Ändern einer Rolle &#40;Management Studio&#41;](security/role-definitions-create-delete-or-modify.md).</span><span class="sxs-lookup"><span data-stu-id="20a3f-135">For more information, see [Create, Delete, or Modify a Role &#40;Management Studio&#41;](security/role-definitions-create-delete-or-modify.md).</span></span>  
  
 <span data-ttu-id="20a3f-136">Beachten Sie, dass Sie bei Verwendung von [!INCLUDE[ssExpressEd2005](../includes/ssexpressed2005-md.md)] with Advanced Services die vorhandenen Rollen verwenden müssen.</span><span class="sxs-lookup"><span data-stu-id="20a3f-136">Note that if you are using [!INCLUDE[ssExpressEd2005](../includes/ssexpressed2005-md.md)] with Advanced Services, you must use the default roles that are provided.</span></span>  
  
 <span data-ttu-id="20a3f-137">**Beschreibungen**</span><span class="sxs-lookup"><span data-stu-id="20a3f-137">**Descriptions**</span></span>  
 <span data-ttu-id="20a3f-138">Zeigt zusätzliche Informationen zur Rolle an.</span><span class="sxs-lookup"><span data-stu-id="20a3f-138">Shows additional information about the role.</span></span> <span data-ttu-id="20a3f-139">Bei vordefinierten Rollen wie z. B. Systembenutzer oder Systemadministrator werden in der Beschreibung die Aufgaben zusammengefasst, die von einer Rolle unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="20a3f-139">For predefined roles such as System User or System Administrator, the description summarizes the tasks that each role supports.</span></span>  
  
 <span data-ttu-id="20a3f-140">**Rollenzuweisung löschen**</span><span class="sxs-lookup"><span data-stu-id="20a3f-140">**Delete Role Assignment**</span></span>  
 <span data-ttu-id="20a3f-141">Klicken Sie auf diese Schaltfläche, um eine vorhandene Rollenzuweisung für einen Benutzer oder eine Gruppe zu löschen.</span><span class="sxs-lookup"><span data-stu-id="20a3f-141">Click to delete an existing role assignment for a user or a group.</span></span> <span data-ttu-id="20a3f-142">Die letzte Rollenzuweisung kann nicht gelöscht werden, da jedes Element über mindestens eine Rollenzuweisung verfügen muss.</span><span class="sxs-lookup"><span data-stu-id="20a3f-142">You cannot delete a role assignment if it is the only one left (each item must have a minimum of one role assignment).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="20a3f-143">Diese Schaltfläche ist nur auf der Seite Rollenzuweisung bearbeiten verfügbar.</span><span class="sxs-lookup"><span data-stu-id="20a3f-143">This button is available only on the Edit Role Assignment page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20a3f-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="20a3f-144">See Also</span></span>  
 <span data-ttu-id="20a3f-145">[Berichts-Manager F1-Hilfe](../../2014/reporting-services/report-manager-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="20a3f-145">[Report Manager F1 Help](../../2014/reporting-services/report-manager-f1-help.md) </span></span>  
 <span data-ttu-id="20a3f-146">[Rollenzuweisungen](security/role-assignments.md) </span><span class="sxs-lookup"><span data-stu-id="20a3f-146">[Role Assignments](security/role-assignments.md) </span></span>  
 [<span data-ttu-id="20a3f-147">Rollendefinitionen</span><span class="sxs-lookup"><span data-stu-id="20a3f-147">Role Definitions</span></span>](security/role-definitions.md)  
  
  
