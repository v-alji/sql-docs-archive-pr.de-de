---
title: Festlegen von Berechtigungen für Berichts Server Elemente auf einer SharePoint-Website (Reporting Services im integrierten SharePoint-Modus) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- permissions [Reporting Services], SharePoint integrated mode
- SharePoint integration [Reporting Services], permissions
ms.assetid: 2467c657-a3bf-4ec3-a88c-8877df19823d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f38497843ca99342f13952153d7fed957564e006
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697438"
---
# <a name="set-permissions-for-report-server-items-on-a-sharepoint-site-reporting-services-in-sharepoint-integrated-mode"></a><span data-ttu-id="bcedf-102">Festlegen von Berechtigungen für Berichtsserverelemente auf einer SharePoint-Website (Reporting Services im integrierten SharePoint-Modus)</span><span class="sxs-lookup"><span data-stu-id="bcedf-102">Set Permissions for Report Server Items on a SharePoint Site (Reporting Services in SharePoint Integrated Mode)</span></span>
  <span data-ttu-id="bcedf-103">Wenn von den standardmäßigen Sicherheitseinstellungen nicht die gewünschte Zugriffsebene bereitgestellt wird, können Sie neue Berechtigungen erstellen, die Zugriff auf bestimmte Berichtsserverelemente oder -vorgänge bieten.</span><span class="sxs-lookup"><span data-stu-id="bcedf-103">If default security settings do not provide the level of access that you require, you can create new permission levels to provide access to specific report server items or operations.</span></span> <span data-ttu-id="bcedf-104">Benutzerdefinierte Sicherheitseinstellungen können nützlich sein, wenn Sie den Zugriff auf einen bestimmten Bericht einschränken möchten.</span><span class="sxs-lookup"><span data-stu-id="bcedf-104">Custom security settings can be useful if you want to restrict access to a particular report.</span></span>  
  
 <span data-ttu-id="bcedf-105">Sie müssen der Websitebesitzer sein, um Berechtigungsebenen und -gruppen erstellen zu können.</span><span class="sxs-lookup"><span data-stu-id="bcedf-105">You must be a site owner to create permission levels and groups.</span></span> <span data-ttu-id="bcedf-106">Berechtigungsebenen werden in einer Website global verwendet.</span><span class="sxs-lookup"><span data-stu-id="bcedf-106">Permission levels are used globally throughout a site.</span></span> <span data-ttu-id="bcedf-107">Wenn Sie eine neue Berechtigungsebene erstellen, ist diese auch für andere Websitebesitzer verfügbar.</span><span class="sxs-lookup"><span data-stu-id="bcedf-107">If you create a new permission level, it will be available to other site owners.</span></span>  
  
 <span data-ttu-id="bcedf-108">Die meisten Berechtigungen werden von einer übergeordneten Website geerbt.</span><span class="sxs-lookup"><span data-stu-id="bcedf-108">Most permissions are inherited from a parent site.</span></span> <span data-ttu-id="bcedf-109">Wenn Sie Berechtigungen für eine bestimmte Bibliothek oder ein bestimmtes Element zuweisen, unterbrechen Sie die Berechtigungsvererbung und verursachen zusätzlichen Verwaltungsaufwand für die Berechtigungen für diesen Zweig der Websitehierarchie.</span><span class="sxs-lookup"><span data-stu-id="bcedf-109">If you assign permissions on a specific library or item, you break permission inheritance and incur additional overhead in how manage permissions for that branch of your site hierarchy.</span></span>  
  
 <span data-ttu-id="bcedf-110">Sie können Berechtigungen für Berichtsdefinitionen (RDL-Dateien), Modelle (SMDL-Dateien) und freigegebene Datenquellen (RSDS-Dateien) festlegen.</span><span class="sxs-lookup"><span data-stu-id="bcedf-110">You can set permissions on report definition (.rdl), model (.smdl), and shared data source (.rsds) files.</span></span> <span data-ttu-id="bcedf-111">Sie können vererbte und verwaltete Berechtigungen nicht für dasselbe Element kombinieren.</span><span class="sxs-lookup"><span data-stu-id="bcedf-111">You cannot combine inherited and managed permissions on the same item.</span></span> <span data-ttu-id="bcedf-112">Wenn Sie Berechtigungen direkt verwalten möchten, haben vererbte Berechtigungen keine Auswirkungen auf das aktuelle Element.</span><span class="sxs-lookup"><span data-stu-id="bcedf-112">If you choose to manage permissions directly, inherited permissions will have no effect on the current item.</span></span> <span data-ttu-id="bcedf-113">Wenn Sie die Berechtigungsvererbung später wiederherstellen möchten, können Sie im Menü **Aktionen** die Option **Berechtigungen erben** auswählen.</span><span class="sxs-lookup"><span data-stu-id="bcedf-113">If you want to resume permission inheritance later, you can select **Inherit Permissions** on the **Actions** menu.</span></span>  
  
 <span data-ttu-id="bcedf-114">Um Berechtigungen für Entitäten und Perspektiven in einem Modell festlegen zu können, müssen Sie für das Modell über die Berechtigungsebene Vollzugriff verfügen.</span><span class="sxs-lookup"><span data-stu-id="bcedf-114">To set permissions on entities and perspectives in a model, you must have Full Control level of permission for the model.</span></span> <span data-ttu-id="bcedf-115">Die Berechtigung Vollzugriff enthält die Berechtigung "Berechtigungen verwalten". Diese Berechtigung auf Websiteebene wird Websitebesitzern und anderen SharePoint-Gruppen erteilt, die über die Berechtigungsebene Vollzugriff verfügen.</span><span class="sxs-lookup"><span data-stu-id="bcedf-115">Full Control includes "Manage Permissions", which is a site level permission that is granted to site owners and other SharePoint groups who have Full Control level of permission.</span></span> <span data-ttu-id="bcedf-116">Wenn Sie bestimmten Benutzern die Möglichkeit bieten möchten, die Modellelementsicherheit festzulegen, müssen Sie die Berechtigungsvererbung unterbrechen und dem Benutzer oder der Gruppe erhöhte Berechtigungen für die Modelldatei erteilen (z. B. Vollzugriff).</span><span class="sxs-lookup"><span data-stu-id="bcedf-116">If you want to offer specific users the ability to set model item security, you must break permission inheritance and grant elevated permissions (such as Full Control) to the user or group on the model file.</span></span> <span data-ttu-id="bcedf-117">Wenn Sie Vollzugriff für ein Element, z. B. eine Datei in der Bibliothek, erteilen, sind die Berechtigungen auf dieses Element beschränkt und gelten nicht für das übergeordnete Element oder andere Elemente in derselben Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="bcedf-117">When you grant Full Control on an item such as a file in the library, the permissions are scoped to that item and do not extend to the parent or to other items within the same library.</span></span> <span data-ttu-id="bcedf-118">Sobald der Benutzer über die Berechtigung Berechtigungen verwalten für das Modell verfügt, kann er die Modellelementsicherheit über die SharePoint-Website oder im Modell-Designer festlegen.</span><span class="sxs-lookup"><span data-stu-id="bcedf-118">After the user has Manage Permissions permission on the model, he or she can use set model item security via the SharePoint site or Model Designer.</span></span>  
  
### <a name="to-set-permissions-on-an-individual-report-model-or-data-source"></a><span data-ttu-id="bcedf-119">So legen Sie Berechtigungen für einen einzelnen Bericht, ein Modell oder eine Datenquelle fest</span><span class="sxs-lookup"><span data-stu-id="bcedf-119">To set permissions on an individual report, model, or data source</span></span>  
  
1.  <span data-ttu-id="bcedf-120">Wenn die Bibliothek nicht bereits geöffnet ist, klicken Sie auf ihren Namen auf der Schnellstartleiste.</span><span class="sxs-lookup"><span data-stu-id="bcedf-120">If the library is not already open, click its name on the Quick Launch.</span></span> <span data-ttu-id="bcedf-121">Wenn der Name der Bibliothek nicht angezeigt wird, klicken Sie auf **Alle Websiteinhalte einblenden**und anschließend auf den Namen der Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="bcedf-121">If the name of your library does not appear, click **View All Site Content**, and then click the name of your library.</span></span>  
  
2.  <span data-ttu-id="bcedf-122">Zeigen Sie auf die Datei mit dem Bericht, dem Berichtsmodell oder der freigegebenen Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="bcedf-122">Point to the report, report model, or shared data source file.</span></span>  
  
3.  <span data-ttu-id="bcedf-123">Klicken Sie auf den Pfeil nach unten, und klicken Sie im Menü auf **Berechtigungen verwalten**.</span><span class="sxs-lookup"><span data-stu-id="bcedf-123">Click the down arrow, and on the menu, click **Manage Permissions**.</span></span>  
  
4.  <span data-ttu-id="bcedf-124">Klicken Sie im Menü **Aktionen** auf **Berechtigungen bearbeiten**, und klicken Sie dann auf **OK** , um die Aktion zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="bcedf-124">On the **Actions** menu, click **Edit Permissions**, and then click **OK** to confirm the action.</span></span>  
  
5.  <span data-ttu-id="bcedf-125">Wenn Sie einem Benutzer oder einer Gruppe ohne Berechtigungen zum Verwenden der Datei nun Berechtigungen erteilen möchten, klicken Sie auf **Neu**und dann auf **Benutzer hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="bcedf-125">To give permissions to a user or group that does not yet have permissions to use the file, click **New**, and then click **Add Users**.</span></span>  
  
6.  <span data-ttu-id="bcedf-126">Wenn Sie Berechtigungen für einen vorhandenen Benutzer oder eine Gruppe entfernen oder ändern möchten, aktivieren Sie das Kontrollkästchen neben dem Benutzer bzw. der Gruppe, und klicken Sie auf **Aktionen**und dann auf **Benutzerberechtigungen entfernen** oder **Benutzerberechtigungen bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="bcedf-126">To remove or modify permissions for an existing user or group, click the check box next to the user or group, click **Actions**, and then click **Remove User Permissions** or **Edit User Permissions**.</span></span>  
  
### <a name="to-set-permissions-that-enable-model-item-security"></a><span data-ttu-id="bcedf-127">So legen Sie Berechtigungen fest, mit denen die Modellelementsicherheit aktiviert wird</span><span class="sxs-lookup"><span data-stu-id="bcedf-127">To set permissions that enable model item security</span></span>  
  
1.  <span data-ttu-id="bcedf-128">Melden Sie sich an der SharePoint-Website mit einem Konto an, das über die Berechtigung Berechtigungen verwalten für die Website verfügt.</span><span class="sxs-lookup"><span data-stu-id="bcedf-128">Log in to the SharePoint site using an account that has Manage Permissions permission on the site.</span></span>  
  
2.  <span data-ttu-id="bcedf-129">Öffnen Sie die Bibliothek, die das Modell enthält.</span><span class="sxs-lookup"><span data-stu-id="bcedf-129">Open the library that contains the model.</span></span>  
  
3.  <span data-ttu-id="bcedf-130">Zeigen Sie auf das Modell.</span><span class="sxs-lookup"><span data-stu-id="bcedf-130">Point to the model.</span></span>  
  
4.  <span data-ttu-id="bcedf-131">Klicken Sie auf den Pfeil nach unten neben dem Modell, und klicken Sie auf **Berechtigungen verwalten**.</span><span class="sxs-lookup"><span data-stu-id="bcedf-131">Click the down arrow next to the model, and click **Manage Permissions**.</span></span>  
  
5.  <span data-ttu-id="bcedf-132">Klicken Sie auf **Aktionen**.</span><span class="sxs-lookup"><span data-stu-id="bcedf-132">Click **Actions**.</span></span>  
  
6.  <span data-ttu-id="bcedf-133">Klicken Sie auf **Berechtigungen bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="bcedf-133">Click **Edit Permissions**.</span></span> <span data-ttu-id="bcedf-134">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="bcedf-134">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="bcedf-135">Klicken Sie auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="bcedf-135">Click **New**.</span></span>  
  
8.  <span data-ttu-id="bcedf-136">Klicken Sie auf **Benutzer hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="bcedf-136">Click **Add Users**.</span></span>  
  
9. <span data-ttu-id="bcedf-137">Geben Sie in Benutzer/Gruppen das Benutzerkonto ein.</span><span class="sxs-lookup"><span data-stu-id="bcedf-137">In Users/Groups, enter the user account.</span></span>  
  
10. <span data-ttu-id="bcedf-138">Wählen Sie **Benutzern eine Berechtigung direkt erteilen**aus.</span><span class="sxs-lookup"><span data-stu-id="bcedf-138">Select **Give users permission directly**.</span></span>  
  
11. <span data-ttu-id="bcedf-139">Klicken Sie auf **Vollzugriff**.</span><span class="sxs-lookup"><span data-stu-id="bcedf-139">Click **Full Control**.</span></span>  
  
12. <span data-ttu-id="bcedf-140">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="bcedf-140">Click **OK**.</span></span> <span data-ttu-id="bcedf-141">Wenn ein Benutzer Berechtigungen für ein bestimmtes Modell verwalten kann, kann dieser Benutzer das Modell öffnen, um Berechtigungen in diesem Modell zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="bcedf-141">Once a user has the ability to manage permissions for a specific model, he or she can open the model to edit permissions within the model.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcedf-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bcedf-142">See Also</span></span>  
 <span data-ttu-id="bcedf-143">[Verwenden der integrierten Sicherheit in Windows SharePoint Services für Berichtsserverelemente](use-built-in-security-in-windows-sharepoint-services-for-report-server-items.md) </span><span class="sxs-lookup"><span data-stu-id="bcedf-143">[Use Built-in Security in Windows SharePoint Services for Report Server Items](use-built-in-security-in-windows-sharepoint-services-for-report-server-items.md) </span></span>  
 <span data-ttu-id="bcedf-144">[Festlegen von Berechtigungen für Berichtsservervorgänge in einer SharePoint-Webanwendung](set-permissions-for-report-server-operations-in-a-sharepoint-web-application.md) </span><span class="sxs-lookup"><span data-stu-id="bcedf-144">[Set Permissions for Report Server Operations in a SharePoint Web Application](set-permissions-for-report-server-operations-in-a-sharepoint-web-application.md) </span></span>  
 <span data-ttu-id="bcedf-145">[Vergleichen der Rollen und Aufgaben in Reporting Services mit SharePoint-Gruppen und -Berechtigungen](../reporting-services-roles-tasks-vs-sharepoint-groups-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="bcedf-145">[Compare Roles and Tasks in Reporting Services to SharePoint Groups and Permissions](../reporting-services-roles-tasks-vs-sharepoint-groups-permissions.md) </span></span>  
 <span data-ttu-id="bcedf-146">[Referenz zu SharePoint-Website- und Listenberechtigungen für Berichtsserverelemente](sharepoint-site-and-list-permission-reference-for-report-server-items.md) </span><span class="sxs-lookup"><span data-stu-id="bcedf-146">[SharePoint Site and List Permission Reference for Report Server Items](sharepoint-site-and-list-permission-reference-for-report-server-items.md) </span></span>  
 [<span data-ttu-id="bcedf-147">Granting Permissions on Report Server Items on a SharePoint Site (Erteilen von Berechtigungen für Berichtsserverelemente auf einer SharePoint-Website)</span><span class="sxs-lookup"><span data-stu-id="bcedf-147">Granting Permissions on Report Server Items on a SharePoint Site</span></span>](granting-permissions-on-report-server-items-on-a-sharepoint-site.md)  
  
  
