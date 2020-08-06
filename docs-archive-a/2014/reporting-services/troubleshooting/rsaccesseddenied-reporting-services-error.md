---
title: 'rsAccessedDenied: Reporting Services-Fehler | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- rsAccessDenied error
ms.assetid: 2f76b1bf-96a2-4755-b76b-84e933220efc
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 194006c2ef6f22b9bc27e9e8cbe1eebd027ed6b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618458"
---
# <a name="rsaccesseddenied---reporting-services-error"></a><span data-ttu-id="cc319-102">rsAccessedDenied – Reporting Services-Fehler</span><span class="sxs-lookup"><span data-stu-id="cc319-102">rsAccessedDenied - Reporting Services Error</span></span>
  <span data-ttu-id="cc319-103">Der [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Fehler **rsAccessedDenied** tritt auf, wenn ein Benutzer keine Berechtigung zum Ausführen einer Aktion hat,</span><span class="sxs-lookup"><span data-stu-id="cc319-103">The [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] error **rsAccessedDenied** occurs when a user does not have permission to perform an action.</span></span> <span data-ttu-id="cc319-104">z. B. wenn er nicht über eine Rollenzuweisung zum Öffnen eines Berichts verfügt oder den Browser nicht mit der entsprechenden Berechtigung geöffnet hat.</span><span class="sxs-lookup"><span data-stu-id="cc319-104">For, example, they do not have a role assignment that allows them to open a report or they did not open their browser with the required permissions.</span></span>  
  
||  
|-|  
|<span data-ttu-id="cc319-105">**[!INCLUDE[applies](../../includes/applies-md.md)]** [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] im einheitlichen Modus &#124; im SharePoint-Modus</span><span class="sxs-lookup"><span data-stu-id="cc319-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode &#124; SharePoint mode</span></span>|  
  
-   <span data-ttu-id="cc319-106">Wenn der Fehler beim direkten Zugreifen auf den Berichtsserver über eine URL auftritt, wird die Ausnahme einem HTTP 401-Fehler zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="cc319-106">If the error occurred while accessing the report server directly through a URL, the exception is mapped to an HTTP 401 error.</span></span>  
  
-   <span data-ttu-id="cc319-107">Wenn der Fehler während der Verwendung des Berichts-Managers oder eines anderen Tools auftritt, wird der Fehler in einer Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cc319-107">If the error occurred while using Report Manager or another tool, the error appears in an error page.</span></span>  
  
-   <span data-ttu-id="cc319-108">Wenn der Fehler während eines geplanten Vorgangs, eines geplanten Abonnements oder einer geplanten Übermittlung auftritt, wird der Fehler nur in der Berichtsserver-Protokolldatei aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="cc319-108">If the error occurred during a scheduled operation, subscription, or delivery, the error will appear in the report server log file only.</span></span>  
  
## <a name="details"></a><span data-ttu-id="cc319-109">Details</span><span class="sxs-lookup"><span data-stu-id="cc319-109">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cc319-110">**Produktname**</span><span class="sxs-lookup"><span data-stu-id="cc319-110">**Product Name**</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="cc319-111">**Ereignis-ID**</span><span class="sxs-lookup"><span data-stu-id="cc319-111">**Event ID**</span></span>|<span data-ttu-id="cc319-112">rsAccessedDenied</span><span class="sxs-lookup"><span data-stu-id="cc319-112">rsAccessedDenied</span></span>|  
|<span data-ttu-id="cc319-113">**Ereignisquelle**</span><span class="sxs-lookup"><span data-stu-id="cc319-113">**Event Source**</span></span>|<span data-ttu-id="cc319-114">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings</span><span class="sxs-lookup"><span data-stu-id="cc319-114">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings</span></span>|  
|<span data-ttu-id="cc319-115">**Komponente**</span><span class="sxs-lookup"><span data-stu-id="cc319-115">**Component**</span></span>|[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]|  
|<span data-ttu-id="cc319-116">**Meldungstext**</span><span class="sxs-lookup"><span data-stu-id="cc319-116">**Message Text**</span></span>|<span data-ttu-id="cc319-117">Die dem Benutzer 'mydomain\myAccount' erteilten Berechtigungen reichen zum Ausführen des Vorgangs nicht aus.</span><span class="sxs-lookup"><span data-stu-id="cc319-117">The permissions granted to user 'mydomain\myAccount' are insufficient for performing this operation.</span></span> <span data-ttu-id="cc319-118">(rsAccessDenied) (ReportingServicesLibrary)</span><span class="sxs-lookup"><span data-stu-id="cc319-118">(rsAccessDenied) (ReportingServicesLibrary)</span></span>|  
  
## <a name="user-action"></a><span data-ttu-id="cc319-119">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="cc319-119">User Action</span></span>  
 <span data-ttu-id="cc319-120">Berechtigungen für den Zugriff auf den Inhalt und die Vorgänge des Berichtsservers werden über Rollenzuweisungen gewährt.</span><span class="sxs-lookup"><span data-stu-id="cc319-120">Permission to access report server content and operations are granted through role assignments.</span></span> <span data-ttu-id="cc319-121">Bei einer Neuinstallation können nur lokale Administratoren auf einen Berichtsserver zugreifen.</span><span class="sxs-lookup"><span data-stu-id="cc319-121">On a new installation, only local administrators have access to a report server.</span></span> <span data-ttu-id="cc319-122">Wenn anderen Benutzern der Zugriff gewährt werden soll, muss ein lokaler Administrator Folgendes erstellen: eine Rollenzuweisung, mit der ein Domänenbenutzer oder ein Gruppenkonto angegeben wird, mindestens eine Rolle, mit der die Aufgaben definiert werden, die vom Benutzer ausgeführt werden können, und einen Bereich (in der Regel der Basisordner oder der Stammknoten der Ordnerhierarchie des Berichtsservers).</span><span class="sxs-lookup"><span data-stu-id="cc319-122">To grant access to other users, a local administrator must create a role assignment that specifies a domain user or group account, one or more roles that define the tasks the user can perform, and a scope (usually the Home folder or root node of the report server folder hierarchy).</span></span> <span data-ttu-id="cc319-123">Mithilfe des Berichts-Managers können Sie die Rollenzuweisungen erstellen.</span><span class="sxs-lookup"><span data-stu-id="cc319-123">You can use Report Manager to create the role assignments.</span></span> <span data-ttu-id="cc319-124">Weitere Informationen finden Sie unter "Rollenzuweisung" in der SQL Server-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="cc319-124">For more information, search for "Role Assignments" in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="cc319-125">Der Fehler wird außerdem durch lokale Administration des Berichtsservers verursacht.</span><span class="sxs-lookup"><span data-stu-id="cc319-125">This error is also caused by local administration of the report server.</span></span> <span data-ttu-id="cc319-126">Weitere Informationen finden Sie unter [Konfigurieren eines Berichtsservers im einheitlichen Modus für die lokale Verwaltung &#40;SSRS&#41;](../report-server/configure-a-native-mode-report-server-for-local-administration-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="cc319-126">For more information, see [Configure a Native Mode Report Server for Local Administration &#40;SSRS&#41;](../report-server/configure-a-native-mode-report-server-for-local-administration-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc319-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cc319-127">See Also</span></span>  
 <span data-ttu-id="cc319-128">[Rollenzuweisungen](../security/role-assignments.md) </span><span class="sxs-lookup"><span data-stu-id="cc319-128">[Role Assignments](../security/role-assignments.md) </span></span>  
 <span data-ttu-id="cc319-129">[Erteilen von Berechtigungen für einen Berichtsserver im einheitlichen Modus](../security/granting-permissions-on-a-native-mode-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="cc319-129">[Granting Permissions on a Native Mode Report Server](../security/granting-permissions-on-a-native-mode-report-server.md) </span></span>  
 [<span data-ttu-id="cc319-130">Rollen und Berechtigungen &#40;Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="cc319-130">Roles and Permissions &#40;Reporting Services&#41;</span></span>](../security/roles-and-permissions-reporting-services.md)  
  
  
