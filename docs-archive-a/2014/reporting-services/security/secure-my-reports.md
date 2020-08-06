---
title: Sichern von „Meine Berichte“ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- denying My Reports folder access
- private folders [Reporting Services]
- user workspace [Reporting Services]
- security [Reporting Services], My Reports folder
- My Reports folder [Reporting Services]
ms.assetid: 3b23a382-13b8-4196-9a93-7fe62d03a63c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b0a832133852e05c54a80b73fad8a91426840467
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697442"
---
# <a name="secure-my-reports"></a><span data-ttu-id="2f035-102">Sichern von Meine Berichte</span><span class="sxs-lookup"><span data-stu-id="2f035-102">Secure My Reports</span></span>
  <span data-ttu-id="2f035-103">Die Funktion Meine Berichte stellt einen vom Benutzer verwalteten Arbeitsbereich zum Verwenden von Berichten bereit.</span><span class="sxs-lookup"><span data-stu-id="2f035-103">The My Reports feature provides a user-managed workspace for working with reports.</span></span> <span data-ttu-id="2f035-104">Damit der Ordner Meine Berichte seinen Zweck erfüllt, sind im Vergleich zu anderen Ordnern, die zur allgemeinen Verwendung dienen, für den Ordner Meine Berichte weniger stark einschränkende Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2f035-104">In order to serve its intended purpose, the My Reports folder requires less restrictive permissions than other folders that are available for general use.</span></span> <span data-ttu-id="2f035-105">Benutzer, die nur über die Berechtigung zum Anzeigen und Ausführen von Berichten in anderen Ordnern verfügen, benötigen möglicherweise erweiterte Berechtigungen, um den Ordner "Meine Berichte" und die in ihrem Besitz befindlichen Inhalt zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="2f035-105">Users who have permissions to only view and run reports in other folders might require an expanded set of permissions to manage their My Reports folders and content that they own.</span></span> [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="2f035-106">enthält zu diesem Zweck eine spezielle Rollenzuweisung und Rollendefinition.</span><span class="sxs-lookup"><span data-stu-id="2f035-106">provides a specialized role assignment and role definition for this purpose.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2f035-107">Meine Berichte ist nur im Berichts-Manager verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2f035-107">My Reports is available only in Report Manager.</span></span> <span data-ttu-id="2f035-108">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2f035-108">It is not available in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
## <a name="role-assignment-for-my-reports"></a><span data-ttu-id="2f035-109">Rollenzuweisung für Meine Berichte</span><span class="sxs-lookup"><span data-stu-id="2f035-109">Role Assignment for My Reports</span></span>  
 <span data-ttu-id="2f035-110">Die Rollenzuweisung für Meine Berichte enthält vordefinierte Elemente und wird automatisch für jeden Benutzer erstellt, der einen Ordner Meine Berichte aktiviert.</span><span class="sxs-lookup"><span data-stu-id="2f035-110">The role assignment for My Reports has preset elements and is automatically created for each user who activates a My Reports folder.</span></span> <span data-ttu-id="2f035-111">Die automatische Zuweisung der Sicherheit durch den Berichtsserver ist besonders hilfreich für Organisationen, die Meine Berichte auf breiter Basis verwenden, weil es nicht notwendig ist, dass Administratoren den Zugriff für jeden Benutzer von Meine Berichte aktivieren.</span><span class="sxs-lookup"><span data-stu-id="2f035-111">Having the report server automatically assign security is especially useful for organizations that use My Reports widely because administrators do not have to enable access for each My Reports user.</span></span>  
  
 <span data-ttu-id="2f035-112">Eine Rollenzuweisung für **Meine Berichte** setzt sich wie folgt zusammen:</span><span class="sxs-lookup"><span data-stu-id="2f035-112">A **My Reports** role assignment consists of the following elements:</span></span>  
  
-   <span data-ttu-id="2f035-113">Der meine Berichte Ordner des Benutzers, der sich im Ordner "Benutzerordner \\ *\<username>* \Meine Berichte" befindet.</span><span class="sxs-lookup"><span data-stu-id="2f035-113">The user's My Reports folder, which is located in Users Folders\\*\<username>* \My Reports folder.</span></span>  
  
-   <span data-ttu-id="2f035-114">Das Benutzerkonto, das beim Aktivieren des Ordners Meine Berichte bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="2f035-114">The user account, which is determined when the My Reports folder is activated.</span></span> <span data-ttu-id="2f035-115">Ein Ordner wird aktiviert, wenn ein Benutzer auf einen Ordner Meine Berichte im Berichts-Manager klickt oder wenn ein Bericht im Berichts-Designer im Ordner Meine Berichte veröffentlicht wird.</span><span class="sxs-lookup"><span data-stu-id="2f035-115">A folder is activated when a user clicks a My Reports folder in Report Manager or when publishing a report to a My Reports folder from Report Designer.</span></span> <span data-ttu-id="2f035-116">Dieser Ordner wird außerdem aktiviert, wenn ein Benutzer Eigenschaften über den Link Meine Berichte anfordert.</span><span class="sxs-lookup"><span data-stu-id="2f035-116">This folder is also activated when a user requests properties on the My Reports link.</span></span>  
  
-   <span data-ttu-id="2f035-117">Die vordefinierte Rollendefinition für Meine Berichte.</span><span class="sxs-lookup"><span data-stu-id="2f035-117">The predefined role definition for My Reports.</span></span>  
  
## <a name="role-definition-for-my-reports"></a><span data-ttu-id="2f035-118">Rollendefinition für Meine Berichte</span><span class="sxs-lookup"><span data-stu-id="2f035-118">Role Definition for My Reports</span></span>  
 <span data-ttu-id="2f035-119">In der Rollendefinition für **Meine Berichte** sind Aufgaben enthalten, die die Inhaltsverwaltung eines Ordners Meine Berichte unterstützen.</span><span class="sxs-lookup"><span data-stu-id="2f035-119">The **My Reports** role definition includes tasks that support content management of a My Reports folder.</span></span> <span data-ttu-id="2f035-120">Die Rolle **Meine Berichte** ist als Rolle für einen einzelnen Verwendungszweck gedacht.</span><span class="sxs-lookup"><span data-stu-id="2f035-120">The **My Reports** role is intended to be a single-purpose role.</span></span> <span data-ttu-id="2f035-121">Sie können diese Rolle zwar für eine beliebige Sicherheitsrichtlinie auf Elementebene auswählen, aber davon wird abgeraten, um zu verhindern, dass Sie die Rolle für andere Ordneranforderungen anpassen.</span><span class="sxs-lookup"><span data-stu-id="2f035-121">Although you can choose it for any item-level security policy, you should avoid doing so to minimize the chance that you will modify it to accommodate other folder requirements.</span></span> <span data-ttu-id="2f035-122">Das Reservieren der **Meine Berichte** -Rolle für die Funktion Meine Berichte trägt dazu bei, dass die Benutzer eine einheitliche Oberfläche vorfinden.</span><span class="sxs-lookup"><span data-stu-id="2f035-122">Reserving the **My Reports** role for the My Reports feature can help you maintain a consistent experience for users.</span></span>  
  
 <span data-ttu-id="2f035-123">Standardmäßig ändern nur Berichtsserveradministratoren die **Meine Berichte** -Rolle.</span><span class="sxs-lookup"><span data-stu-id="2f035-123">By default, only report server administrators modify the **My Reports** role.</span></span> <span data-ttu-id="2f035-124">Sie können die **Meine Berichte** -Rolle anpassen, indem Sie die darin enthaltenen Aufgaben ändern.</span><span class="sxs-lookup"><span data-stu-id="2f035-124">You can customize the **My Reports** role by changing the tasks it contains.</span></span> <span data-ttu-id="2f035-125">Außerdem können Sie diese Rolle durch eine andere Rolle ersetzen.</span><span class="sxs-lookup"><span data-stu-id="2f035-125">You can also substitute a different role.</span></span>  
  
## <a name="denying-access-to-my-reports"></a><span data-ttu-id="2f035-126">Verweigern des Zugriffs auf Meine Berichte</span><span class="sxs-lookup"><span data-stu-id="2f035-126">Denying Access to My Reports</span></span>  
 <span data-ttu-id="2f035-127">Sie können Benutzern folgendermaßen den Zugriff auf Meine Berichte verweigern:</span><span class="sxs-lookup"><span data-stu-id="2f035-127">You can prevent users from accessing My Reports by:</span></span>  
  
-   <span data-ttu-id="2f035-128">Deaktivieren von Meine Berichte auf der Seite Siteeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="2f035-128">Disabling My Reports on the Site Settings page.</span></span> <span data-ttu-id="2f035-129">Weitere Informationen finden Sie unter [Aktivieren und Deaktivieren von "Meine Berichte"](../report-server/enable-and-disable-my-reports.md).</span><span class="sxs-lookup"><span data-stu-id="2f035-129">For more information, see [Enable and Disable My Reports](../report-server/enable-and-disable-my-reports.md).</span></span>  
  
-   <span data-ttu-id="2f035-130">Entfernen aller Aufgaben aus der **Meine Berichte** -Rolle.</span><span class="sxs-lookup"><span data-stu-id="2f035-130">Removing all tasks from the **My Reports** role.</span></span>  
  
 <span data-ttu-id="2f035-131">Wenn Sie Meine Berichte deaktivieren, wird der Link zum Ordner Meine Berichte aus dem Berichts-Manager entfernt.</span><span class="sxs-lookup"><span data-stu-id="2f035-131">When you disable My Reports, the link to a My Reports folder is removed from Report Manager.</span></span> <span data-ttu-id="2f035-132">Die zugrunde liegende Ordnerstruktur, die Meine Berichte unterstützt (d. h. der Ordner Benutzerordner und die zugehörigen Unterordner), sind weiterhin verfügbar und können aufgerufen werden, wenn ein Benutzer den Ordnerpfad kennt.</span><span class="sxs-lookup"><span data-stu-id="2f035-132">The underlying folder structure that supports My Reports (that is, the Users Folders folder and subfolders) is still available and can be accessed if a user knows the folder path.</span></span> <span data-ttu-id="2f035-133">Durch das Entfernen von Aufgaben aus der **Meine Berichte** -Rolle wird die Zugriffsverweigerung sichergestellt.</span><span class="sxs-lookup"><span data-stu-id="2f035-133">Removing tasks from **My Reports** role ensures that access is prevented.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f035-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2f035-134">See Also</span></span>  
 <span data-ttu-id="2f035-135">[Sichere Berichte und Ressourcen](secure-reports-and-resources.md) </span><span class="sxs-lookup"><span data-stu-id="2f035-135">[Secure Reports and Resources](secure-reports-and-resources.md) </span></span>  
 <span data-ttu-id="2f035-136">[Sichere Ordner](secure-folders.md) </span><span class="sxs-lookup"><span data-stu-id="2f035-136">[Secure Folders](secure-folders.md) </span></span>  
 [<span data-ttu-id="2f035-137">Granting Permissions on a Native Mode Report Server (Erteilen von Berechtigungen für einen Berichtsserver im einheitlichen Modus)</span><span class="sxs-lookup"><span data-stu-id="2f035-137">Granting Permissions on a Native Mode Report Server</span></span>](granting-permissions-on-a-native-mode-report-server.md)  
  
  
