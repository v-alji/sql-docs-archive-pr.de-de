---
title: Ändern oder Löschen einer Rollenzuweisung (Berichts-Manager) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- removing role assignments
- roles [Reporting Services], assignments
- system roles [Reporting Services]
- modifying role assignments
- deleting role assignments
ms.assetid: 523bdd32-92cb-4b48-a3a9-d58b2385bde7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d67c5cdb7647d50008f72890e4ac3e3c7eed456e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700778"
---
# <a name="modify-or-delete-a-role-assignment-report-manager"></a><span data-ttu-id="e308b-102">Ändern oder Löschen einer Rollenzuweisung (Berichts-Manager)</span><span class="sxs-lookup"><span data-stu-id="e308b-102">Modify or Delete a Role Assignment (Report Manager)</span></span>
  <span data-ttu-id="e308b-103">Mit einer Rollenzuweisung werden eine Gruppe oder ein Benutzerkonto einer vordefinierten Rollendefinition zugewiesen, die ausführbare Aufgaben beinhaltet.</span><span class="sxs-lookup"><span data-stu-id="e308b-103">A role assignment maps a group or user account to a predefined role definition that includes tasks that can be performed.</span></span> <span data-ttu-id="e308b-104">Hiermit werden die Vorgangstypen festgelegt, die ein Benutzer für einen Ordner, einen Bericht, ein Modell oder einen anderen Inhaltstyp ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="e308b-104">It determines the types of operations that a user can perform relative to a folder, report, model, or other content type.</span></span> <span data-ttu-id="e308b-105">Verwenden Sie den Berichts-Manager zum Erstellen, Löschen oder Ändern von Rollenzuweisungen.</span><span class="sxs-lookup"><span data-stu-id="e308b-105">To create, modify, or delete role assignments, you use Report Manager.</span></span> <span data-ttu-id="e308b-106">Nach der Erstellung einer Rollenzuweisung für einen bestimmten Benutzer oder eine bestimmte Gruppe können Sie diese später durch Auswahl einer anderen Rolle ändern.</span><span class="sxs-lookup"><span data-stu-id="e308b-106">After you create a role assignment for a particular user or group, you can modify it later by selecting a different role.</span></span> <span data-ttu-id="e308b-107">Möchten Sie Berechtigungen für einen Berichtsserver widerrufen, können Sie die Rollenzuweisung vom Berichtsserver löschen.</span><span class="sxs-lookup"><span data-stu-id="e308b-107">If you want to revoke permissions to a report server, you can delete a role assignment from the report server.</span></span>  
  
 <span data-ttu-id="e308b-108">Je nach Zielsetzung können alternative Vorgehensweisen geeigneter sein.</span><span class="sxs-lookup"><span data-stu-id="e308b-108">Depending on your objective, alternative approaches might be more appropriate.</span></span> <span data-ttu-id="e308b-109">Beispiele hierfür sind die Anpassung oder Erstellung einer neuen Rollendefinition beziehungsweise die Änderung der Mitgliedschaft eines Gruppenkontos in Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e308b-109">Examples include customizing or creating a new role definition, or modifying the membership of a group account in Active Directory.</span></span>  
  
 <span data-ttu-id="e308b-110">Angenommen, Sie verfügen beispielsweise über eine Benutzergruppe, die ihren Inhalt vollständig verwalten muss, jedoch nicht über alle dem Inhalts-Manager zugewiesenen Berechtigungen verfügen soll.</span><span class="sxs-lookup"><span data-stu-id="e308b-110">For example, suppose you have a group of users who need to fully manage their content, but should not have the full set of permissions associated with Content Manager.</span></span> <span data-ttu-id="e308b-111">In diesem Fall könnten Sie eine neue Rollendefinition mit der Bezeichnung "Inhalts-Manager für Abteilung" erstellen, die alle Aufgaben des Inhalts-Manager enthält, ausgenommen **Sicherheit für einzelne Elemente festlegen**.</span><span class="sxs-lookup"><span data-stu-id="e308b-111">In this case, you could create a new role definition called Department Content Manager that includes all of the tasks in Content Manager except **Set security policies for items**.</span></span>  
  
 <span data-ttu-id="e308b-112">Ähnliches gilt, falls Sie System- oder Netzwerkadministrator sind und Active Directory-Gruppenkonten einfacher verwalten können als Rollenzuweisungen im Berichts-Manager. In diesem Fall können Sie den Aufwand für die Verwaltung von Rollenzuweisungen durch die Erstellung einer einzelnen Rollenzuweisung für ein Gruppenkonto und die anschließende Anpassung der Gruppenmitgliedschaft, wenn Benutzer keinen Zugriff mehr auf Berichte benötigen, verringern.</span><span class="sxs-lookup"><span data-stu-id="e308b-112">Similarly, if you are a system or network administrator and it is easier for you to manage Active Directory group accounts than role assignments in Report Manager, you could reduce the overhead of managing role assignments by creating a single role assignment for a group account, and then adjust group membership when users no longer require access to reports.</span></span>  
  
 <span data-ttu-id="e308b-113">Sollten Sie zu dem Schluss kommen, dass die Änderung oder Löschung einer Rollenzuweisung die beste Vorgehensweise ist, denken Sie daran, sowohl die Rollenzuweisungen auf Systemebene als auch die Rollenzuweisungen auf Elementebene zu prüfen.</span><span class="sxs-lookup"><span data-stu-id="e308b-113">If you determine that modifying or deleting a role assignment is the best approach, remember to check for both system role assignments and item role assignments.</span></span> <span data-ttu-id="e308b-114">Jeder Rollenzuweisungstyp wird auf anderen Seiten im Berichts-Manager konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="e308b-114">Each type of role assignment is configured through different pages in Report Manager.</span></span>  
  
### <a name="to-modify-or-delete-a-system-role-assignment"></a><span data-ttu-id="e308b-115">So löschen oder ändern Sie eine Systemrollenzuweisung</span><span class="sxs-lookup"><span data-stu-id="e308b-115">To modify or delete a system role assignment</span></span>  
  
1.  <span data-ttu-id="e308b-116">Starten Sie den [Berichts-Manager &#40;einheitlicher SSRS-Modus&#41;](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="e308b-116">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="e308b-117">Klicken Sie auf **Siteeinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="e308b-117">Click **Site Settings**.</span></span>  
  
3.  <span data-ttu-id="e308b-118">Klicken Sie auf **Sicherheit**.</span><span class="sxs-lookup"><span data-stu-id="e308b-118">Click **Security**.</span></span> <span data-ttu-id="e308b-119">Alle aktuell für den Server oder die Bereitstellung für horizontales Skalieren definierten Rollenzuweisungen auf Systemebene werden anhand des Kontonamens aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="e308b-119">All system-level role assignments currently defined for the server or scale-out deployment are listed by account name.</span></span>  
  
4.  <span data-ttu-id="e308b-120">Suchen Sie die zu ändernde oder zu löschende Rollenzuweisung.</span><span class="sxs-lookup"><span data-stu-id="e308b-120">Find the role assignment that you want to modify or delete.</span></span>  
  
5.  <span data-ttu-id="e308b-121">Zum Hinzufügen oder Entfernen der Rolle für einen bestimmten Benutzer oder eine bestimmte Gruppe klicken Sie auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="e308b-121">To add or remove the role for a particular user or group, click **Edit**.</span></span>  
  
6.  <span data-ttu-id="e308b-122">Aktivieren Sie zum Löschen einer Rollenzuweisung das Kontrollkästchen neben dem Gruppen- oder Benutzernamen, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="e308b-122">To delete a role assignment, click the check box next to the user or group name, and then click **Delete**.</span></span>  
  
### <a name="to-modify-or-delete-an-item-role-assignment"></a><span data-ttu-id="e308b-123">So löschen oder ändern Sie eine Elementrollenzuweisung</span><span class="sxs-lookup"><span data-stu-id="e308b-123">To modify or delete an item role assignment</span></span>  
  
1.  <span data-ttu-id="e308b-124">Starten Sie den **Berichts-Manager** , und suchen Sie das Element, für das Sie eine Rollenzuweisung bearbeiten oder löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="e308b-124">Start **Report Manager** and locate the item for which you want to edit or delete a role assignment.</span></span>  
  
2.  <span data-ttu-id="e308b-125">Zeigen Sie auf das Element, und klicken Sie auf den Dropdownpfeil.</span><span class="sxs-lookup"><span data-stu-id="e308b-125">Hover over the item, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="e308b-126">Klicken Sie im Dropdownmenü auf **Sicherheit**.</span><span class="sxs-lookup"><span data-stu-id="e308b-126">In the drop-down menu, click **Security**.</span></span>  
  
4.  <span data-ttu-id="e308b-127">Suchen Sie die zu ändernde oder zu löschende Rollenzuweisung.</span><span class="sxs-lookup"><span data-stu-id="e308b-127">Find the role assignment that you want to modify or delete.</span></span>  
  
5.  <span data-ttu-id="e308b-128">Zum Hinzufügen oder Entfernen der Rolle für einen bestimmten Benutzer oder eine bestimmte Gruppe klicken Sie auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="e308b-128">To add or remove the role for a particular user or group, click **Edit**.</span></span>  
  
6.  <span data-ttu-id="e308b-129">Aktivieren Sie zum Löschen einer Rollenzuweisung das Kontrollkästchen neben dem Gruppen- oder Benutzernamen, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="e308b-129">To delete a role assignment, click the check box next to the user or group name, and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e308b-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e308b-130">See Also</span></span>  
 <span data-ttu-id="e308b-131">(Create-and-manage-role-assignments.MD)</span><span class="sxs-lookup"><span data-stu-id="e308b-131">(create-and-manage-role-assignments.md)</span></span>   
 <span data-ttu-id="e308b-132">[Rollenzuweisungen](role-assignments.md) </span><span class="sxs-lookup"><span data-stu-id="e308b-132">[Role Assignments](role-assignments.md) </span></span>  
 <span data-ttu-id="e308b-133">[Die Seite "Site Einstellungen" &#40;Berichts-Manager&#41;](../site-settings-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="e308b-133">[Site Settings Page &#40;Report Manager&#41;](../site-settings-page-report-manager.md) </span></span>  
 [<span data-ttu-id="e308b-134">New System Role Assignments: Edit System Role Assignments Page (Report Manager) (Neue Systemrollenzuweisungen: Seite „Systemrollenzuweisungen bearbeiten“ (Berichts-Manager))</span><span class="sxs-lookup"><span data-stu-id="e308b-134">New System Role Assignments: Edit System Role Assignments Page &#40;Report Manager&#41;</span></span>](../new-system-role-assignments-edit-system-role-assignments-page-report-manager.md)  
  
  
