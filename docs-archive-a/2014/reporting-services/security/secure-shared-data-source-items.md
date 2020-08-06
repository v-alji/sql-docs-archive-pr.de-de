---
title: Sichern freigegebener Datenquellenelemente | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- shared data sources [Reporting Services]
- data sources [Reporting Services], shared
- security [Reporting Services], data sources
ms.assetid: 7299e498-0a1a-4821-a22a-5199bb773ce0
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c4177834a90e2852f4079e3b2bf5a1dd85b9cd51
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618472"
---
# <a name="secure-shared-data-source-items"></a><span data-ttu-id="bc357-102">Sichern freigegebener Datenquellenelemente</span><span class="sxs-lookup"><span data-stu-id="bc357-102">Secure Shared Data Source Items</span></span>
  <span data-ttu-id="bc357-103">Sie können ein freigegebenes Datenquellenelement sichern, um den Zugriff darauf zu aktivieren bzw. zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="bc357-103">You can set security on a shared data source item to enable or disable access to it.</span></span>  
  
 <span data-ttu-id="bc357-104">Ein Benutzer mit dem Mindestzugriffsrecht für eine freigegebene Datenquelle (z.B. der Zugriff über die **Browser** -Rolle) kann die Liste der Berichte anzeigen, die das Element verwenden, vorausgesetzt der Benutzer hat auch die Berechtigung zum Anzeigen der Berichte selbst.</span><span class="sxs-lookup"><span data-stu-id="bc357-104">A user who has minimal access to a shared data source (for example, the access granted through the **Browser** role) can view the list of reports that use the item, provided the user is also authorized to view the reports themselves.</span></span>  
  
 <span data-ttu-id="bc357-105">Ein Benutzer mit zusätzlichen Zugriffsrechten (z.B. über die **Inhalts-Manager** -Rolle) kann Eigenschaften für die freigegebene Datenquelle anzeigen und festlegen.</span><span class="sxs-lookup"><span data-stu-id="bc357-105">A user who has additional access (such as that granted through the **Content Manager** role) can view and set properties for the shared data source.</span></span>  
  
 <span data-ttu-id="bc357-106">Zum Festlegen der Sicherheit erstellen Sie eine Rollenzuweisung, die angibt, welches Benutzer- oder Gruppenkonto Zugriff auf die freigegebene Datenquelle hat.</span><span class="sxs-lookup"><span data-stu-id="bc357-106">To set security, you create a role assignment that specifies which user or group account has access to the shared data source.</span></span> <span data-ttu-id="bc357-107">Benutzer mit Zugriff auf ein freigegebenes Datenquellenelement können dessen Namen, Beschreibung, Verbindungszeichenfolge oder Anmeldeinformationen ändern.</span><span class="sxs-lookup"><span data-stu-id="bc357-107">Users who have access to a shared data source item can change its name, description, connection string, or credential information.</span></span>  
  
## <a name="tasks-and-access-to-items"></a><span data-ttu-id="bc357-108">Aufgaben und Zugriffsrechte für Elemente</span><span class="sxs-lookup"><span data-stu-id="bc357-108">Tasks and Access to Items</span></span>  
 <span data-ttu-id="bc357-109">Beim Erstellen von Rollenzuweisungen sollten Sie eine Rolle verwenden, die die folgenden Aufgaben einschließt, um den Benutzern und Gruppen die geeigneten Berechtigungen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="bc357-109">When creating role assignments, use a role that has these tasks to assign appropriate permissions to users and groups.</span></span>  
  
|<span data-ttu-id="bc357-110">Verwendete Aufgabe</span><span class="sxs-lookup"><span data-stu-id="bc357-110">Select this task</span></span>|<span data-ttu-id="bc357-111">Berechtigt zu folgender Aktion</span><span class="sxs-lookup"><span data-stu-id="bc357-111">To give users permission to</span></span>|  
|----------------------|---------------------------------|  
|<span data-ttu-id="bc357-112">Datenquellen anzeigen</span><span class="sxs-lookup"><span data-stu-id="bc357-112">View data sources</span></span>|<span data-ttu-id="bc357-113">Anzeigen des freigegebenen Datenquellenelements in der Ordnerhierarchie.</span><span class="sxs-lookup"><span data-stu-id="bc357-113">View the shared data source item in the folder hierarchy.</span></span> <span data-ttu-id="bc357-114">Ohne diese Aufgabe ist das Element für die Benutzer nicht sichtbar, und sie wissen möglicherweise nicht, dass die Datenquelle verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="bc357-114">Without this task, the item is not visible to users and they may not be aware that the data source is available.</span></span>|  
|<span data-ttu-id="bc357-115">Datenquellen verwalten</span><span class="sxs-lookup"><span data-stu-id="bc357-115">Manage data sources</span></span>|<span data-ttu-id="bc357-116">Anzeigen von Eigenschaften, die den Namen, eine Beschreibung und Verbindungsinformationen angeben.</span><span class="sxs-lookup"><span data-stu-id="bc357-116">View properties that specify the name, description, and connection information.</span></span> <span data-ttu-id="bc357-117">Mit dieser Aufgabe wird auch ein freigegebenes Datenquellenelement in der Ordnerhierarchie angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bc357-117">This task is also used to display a shared data source item in the folder hierarchy.</span></span> <span data-ttu-id="bc357-118">Wenn Sie diese Aufgabe auswählen, können Sie die Aufgabe "Datenquellen anzeigen" auslassen.</span><span class="sxs-lookup"><span data-stu-id="bc357-118">If you choose this task, you can omit the "View data sources" task.</span></span>|  
|<span data-ttu-id="bc357-119">Die Sicherheit für einzelne Elemente festlegen</span><span class="sxs-lookup"><span data-stu-id="bc357-119">Set security on items</span></span>|<span data-ttu-id="bc357-120">Erstellen und Ändern von Rollenzuweisungen, die den Zugriff auf die freigegebene Datenquelle steuern.</span><span class="sxs-lookup"><span data-stu-id="bc357-120">Create and modify role assignments that control access to the shared data source.</span></span> <span data-ttu-id="bc357-121">Diese Aufgabe muss zusammen mit Datenquellen anzeigen oder Datenquellen verwalten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bc357-121">This task must be used with either "View data source" or "Manage data sources" tasks.</span></span> <span data-ttu-id="bc357-122">Andernfalls zeigt sie keine Wirkung, weil der Benutzer das Element nicht auswählen kann.</span><span class="sxs-lookup"><span data-stu-id="bc357-122">If it is not, it has no effect because the user cannot select the item.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bc357-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bc357-123">See Also</span></span>  
 <span data-ttu-id="bc357-124">[Verwalten von Berichtsdatenquellen](../report-data/manage-report-data-sources.md) </span><span class="sxs-lookup"><span data-stu-id="bc357-124">[Manage Report Data Sources](../report-data/manage-report-data-sources.md) </span></span>  
 <span data-ttu-id="bc357-125">[Sichere Ordner](secure-folders.md) </span><span class="sxs-lookup"><span data-stu-id="bc357-125">[Secure Folders](secure-folders.md) </span></span>  
 <span data-ttu-id="bc357-126">[Sichere Berichte und Ressourcen](secure-reports-and-resources.md) </span><span class="sxs-lookup"><span data-stu-id="bc357-126">[Secure Reports and Resources](secure-reports-and-resources.md) </span></span>  
 <span data-ttu-id="bc357-127">[Erteilen von Berechtigungen für einen Berichtsserver im einheitlichen Modus](granting-permissions-on-a-native-mode-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="bc357-127">[Granting Permissions on a Native Mode Report Server](granting-permissions-on-a-native-mode-report-server.md) </span></span>  
 [<span data-ttu-id="bc357-128">Store Credentials in a Reporting Services Data Source (Speichern von Anmeldeinformationen in einer Reporting Services-Datenquelle)</span><span class="sxs-lookup"><span data-stu-id="bc357-128">Store Credentials in a Reporting Services Data Source</span></span>](../report-data/store-credentials-in-a-reporting-services-data-source.md)  
  
  
