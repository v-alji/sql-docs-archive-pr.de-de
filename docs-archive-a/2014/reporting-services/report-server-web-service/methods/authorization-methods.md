---
title: Autorisierungsmethoden | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- security [Reporting Services], reports
- authorization [Reporting Services]
- reports [Reporting Services], security
- tasks [Reporting Services]
- roles [Reporting Services], methods
ms.assetid: 45e9cf2c-facf-4801-9482-c855403f42a8
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b04a21b5075e939a4732e2f8ec219e169f4ba440
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721100"
---
# <a name="authorization-methods"></a><span data-ttu-id="d3038-102">Autorisierungsmethoden</span><span class="sxs-lookup"><span data-stu-id="d3038-102">Authorization Methods</span></span>
  <span data-ttu-id="d3038-103">Mit diesen Methoden können Sie Tasks, Rollen und Richtlinien auf dem Berichtsserver verwalten.</span><span class="sxs-lookup"><span data-stu-id="d3038-103">You can use these methods to manage tasks, roles, and policies on the report server.</span></span>  
  
|<span data-ttu-id="d3038-104">Methode</span><span class="sxs-lookup"><span data-stu-id="d3038-104">Method</span></span>|<span data-ttu-id="d3038-105">Aktion</span><span class="sxs-lookup"><span data-stu-id="d3038-105">Action</span></span>|  
|------------|------------|  
|<xref:ReportService2010.ReportingService2010.CreateRole%2A>|<span data-ttu-id="d3038-106">Fügt der Berichtsserver-Datenbank eine neue Rolle hinzu.</span><span class="sxs-lookup"><span data-stu-id="d3038-106">Adds a new role to the report server database.</span></span> <span data-ttu-id="d3038-107">Diese Methode gilt nur für den einheitlichen Modus.</span><span class="sxs-lookup"><span data-stu-id="d3038-107">This method =applies to native mode only.</span></span>|  
|<xref:ReportService2010.ReportingService2010.DeleteRole%2A>|<span data-ttu-id="d3038-108">Löscht eine Rolle aus der Berichtsserver-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="d3038-108">Deletes a role from the report server database.</span></span> <span data-ttu-id="d3038-109">Diese Methode gilt nur für den einheitlichen Modus.</span><span class="sxs-lookup"><span data-stu-id="d3038-109">This method applies to native mode only.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetPermissions%2A>|<span data-ttu-id="d3038-110">Gibt die Benutzerberechtigungen zurück, die einem bestimmten Element in der Berichtsserver-Datenbank oder SharePoint-Bibliothek zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="d3038-110">Returns the user permissions that are associated with a particular item in the report server database or SharePoint library.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetPolicies%2A>|<span data-ttu-id="d3038-111">Gibt die Richtlinien zurück, die einem bestimmten Element in der Berichtsserver-Datenbank oder SharePoint-Bibliothek zugeordnet sind</span><span class="sxs-lookup"><span data-stu-id="d3038-111">Returns the policies that are associated with a particular item in the report server database or SharePoint library.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetRoleProperties%2A>|<span data-ttu-id="d3038-112">Gibt die Eigenschaften von Rollenmetadaten und eine Auflistung zugehöriger Tasks zurück.</span><span class="sxs-lookup"><span data-stu-id="d3038-112">Returns role metadata properties and a collection of associated tasks.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetSystemPermissions%2A>|<span data-ttu-id="d3038-113">Gibt die Systemberechtigungen des Benutzers zurück.</span><span class="sxs-lookup"><span data-stu-id="d3038-113">Returns the user's system permissions.</span></span> <span data-ttu-id="d3038-114">Diese Methode gilt nur für den einheitlichen Modus.</span><span class="sxs-lookup"><span data-stu-id="d3038-114">This method applies to native mode only.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetSystemPolicies%2A>|<span data-ttu-id="d3038-115">Gibt die Systemrichtlinien zurück, einschließlich der Gruppen und Rollen, denen sie zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="d3038-115">Returns the system policies, including groups and roles with which they are associated.</span></span> <span data-ttu-id="d3038-116">Diese Methode gilt nur für den einheitlichen Modus.</span><span class="sxs-lookup"><span data-stu-id="d3038-116">This method applies to native mode only.</span></span>|  
|<xref:ReportService2010.ReportingService2010.InheritParentSecurity%2A>|<span data-ttu-id="d3038-117">Löscht die Richtlinien, die einem bestimmten Element in der Berichtsserver-Datenbank zugeordnet sind, und legt die Sicherheitsrichtlinien des Elements auf die Werte des übergeordneten Elements fest</span><span class="sxs-lookup"><span data-stu-id="d3038-117">Deletes the policies that are associated with a particular item in the report server database and sets the security policies for the item to those of its parent.</span></span>|  
|<xref:ReportService2010.ReportingService2010.IsSSLRequired%2A>|<span data-ttu-id="d3038-118">Gibt einen booleschen Wert zurück, der angibt, ob das Secure Sockets Layer (SSL)-Protokoll zur Verwendung des <xref:ReportService2010>-Endpunkts erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="d3038-118">Returns a Boolean value that indicates whether the Secure Socket Layer (SSL) protocol is required to use the <xref:ReportService2010> end point.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListRoles%2A>|<span data-ttu-id="d3038-119">Gibt die Namen und Beschreibungen der Rollen zurück, die vom Berichtsserver verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="d3038-119">Returns the names and descriptions of roles that are managed by the report server.</span></span>|  
|<xref:ReportExecution2005.ReportExecutionService.ListSecureMethods%2A>|<span data-ttu-id="d3038-120">Gibt eine Liste von SOAP-Methoden (Simple Object Access Protocol) im <xref:ReportExecution2005>-Endpunkt zurück, bei deren Aufruf eine sichere Verbindung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="d3038-120">Returns a list of Simple Object Access Protocol (SOAP) methods in the <xref:ReportExecution2005> endpoint that require a secure connection when invoked.</span></span> <span data-ttu-id="d3038-121">Mit der `SecureConnectionLevel`-Einstellung des Berichtsservers wird bestimmt, welche Methoden zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d3038-121">The `SecureConnectionLevel` setting of the report server is used to determine which methods are returned.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListTasks%2A>|<span data-ttu-id="d3038-122">Gibt die Tasks zurück, die vom Berichtsserver verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="d3038-122">Returns the tasks that are managed by the report server.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetPolicies%2A>|<span data-ttu-id="d3038-123">Legt die Richtlinien fest, die einem angegebenen Element zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="d3038-123">Sets the policies that are associated with a specified item.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetRoleProperties%2A>|<span data-ttu-id="d3038-124">Legt die Eigenschaften der Rollenmetadaten fest und ordnet einer Rolle eine Reihe von Tasks zu.</span><span class="sxs-lookup"><span data-stu-id="d3038-124">Sets role metadata properties and associates a set of tasks with a role.</span></span> <span data-ttu-id="d3038-125">Diese Methode gilt nur für den einheitlichen Modus.</span><span class="sxs-lookup"><span data-stu-id="d3038-125">This method applies to native mode only.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetSystemPolicies%2A>|<span data-ttu-id="d3038-126">Legt die Systemrichtlinie fest, die die Gruppen und ihre zugehörigen Rollen definiert.</span><span class="sxs-lookup"><span data-stu-id="d3038-126">Sets the system policy that defines groups and their associated roles.</span></span> <span data-ttu-id="d3038-127">Diese Methode gilt nur für den einheitlichen Modus.</span><span class="sxs-lookup"><span data-stu-id="d3038-127">This method applies to native mode only.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d3038-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d3038-128">See Also</span></span>  
 <span data-ttu-id="d3038-129">[Erstellen von Anwendungen mit dem Webdienst und .NET Framework](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="d3038-129">[Building Applications Using the Web Service and the .NET Framework](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 <span data-ttu-id="d3038-130">[Berichtsserver-Webdienst](../report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="d3038-130">[Report Server Web Service](../report-server-web-service.md) </span></span>  
 <span data-ttu-id="d3038-131">[Webdienstmethoden für Berichtsserver](report-server-web-service-methods.md) </span><span class="sxs-lookup"><span data-stu-id="d3038-131">[Report Server Web Service Methods](report-server-web-service-methods.md) </span></span>  
 [<span data-ttu-id="d3038-132">Technische Referenz (SSRS)</span><span class="sxs-lookup"><span data-stu-id="d3038-132">Technical Reference &#40;SSRS&#41;</span></span>](../../technical-reference-ssrs.md)  
  
  
