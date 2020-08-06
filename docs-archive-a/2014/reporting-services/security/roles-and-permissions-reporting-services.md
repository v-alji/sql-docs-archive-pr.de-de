---
title: Rollen und Berechtigungen (Reporting Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- access controls [Reporting Services]
- permissions [Reporting Services], about permissions
- security [Reporting Services], identity and access control
- authentication [Reporting Services]
- permissions [Reporting Services]
- security [Reporting Services], role-based
- identity [Reporting Services]
ms.assetid: eea655fe-43ed-418d-8233-b288a8f4daa4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0e6098a51afde04164e3ef0dfa5e5297457b4440
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618478"
---
# <a name="roles-and-permissions-reporting-services"></a><span data-ttu-id="221cd-102">Rollen und Berechtigungen (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="221cd-102">Roles and Permissions (Reporting Services)</span></span>
  <span data-ttu-id="221cd-103">Reporting Services stellt ein Authentifizierungssubsystem und ein rollenbasiertes Autorisierungsmodell bereit.</span><span class="sxs-lookup"><span data-stu-id="221cd-103">Reporting Services provides an authentication subsystem and role-based authorization model.</span></span> <span data-ttu-id="221cd-104">Authentifizierungs- und Autorisierungsmodelle sind je nachdem, ob der Berichtsserver im einheitlichen Modus oder im integrierten SharePoint-Modus ausgeführt wird, unterschiedlich.</span><span class="sxs-lookup"><span data-stu-id="221cd-104">Authentication and authorization models vary depending on whether the report server runs in native mode or SharePoint mode.</span></span> <span data-ttu-id="221cd-105">Ist der Berichtsserver Bestandteil einer umfangreicheren SharePoint-Bereitstellung, wird mit SharePoint-Berechtigungen festgelegt, wer Zugriff auf den Berichtsserver hat.</span><span class="sxs-lookup"><span data-stu-id="221cd-105">If the report server is part of a SharePoint deployment, SharePoint permissions determine who has access to the report server.</span></span>  
  
## <a name="identity-and-access-control-for-native-mode"></a><span data-ttu-id="221cd-106">Identität und Zugriffssteuerung für den systemeigenen Modus</span><span class="sxs-lookup"><span data-stu-id="221cd-106">Identity and Access Control for Native Mode</span></span>  
 <span data-ttu-id="221cd-107">Die Standardauthentifizierung basiert auf der Windows-Authentifizierung und der integrierten Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="221cd-107">Default authentication is based on Windows Authentication and integrated security.</span></span> <span data-ttu-id="221cd-108">Sie können die Authentifizierungseinstellungen so ändern, dass der Berichtsserver auf andere Authentifizierungsanforderungen reagieren kann. Alternativ können Sie sogar die Standardsicherheitsfunktionen durch eine von Ihnen bereitgestellte benutzerdefinierte Authentifizierungserweiterung ersetzen.</span><span class="sxs-lookup"><span data-stu-id="221cd-108">You can change the authentication settings to allow the report server to respond to different authentication requests, or even replace the default security features with a custom authentication extension that you provide.</span></span>  
  
 <span data-ttu-id="221cd-109">Die Autorisierung basiert auf Rollen, die Sie einem Prinzipal zuweisen.</span><span class="sxs-lookup"><span data-stu-id="221cd-109">Authorization is based on roles that you assign to a principle.</span></span> <span data-ttu-id="221cd-110">Jede Rolle besteht aus einer Reihe von zusammenhängenden Aufgaben, die wiederum aus zusammenhängenden Vorgängen bestehen.</span><span class="sxs-lookup"><span data-stu-id="221cd-110">Each role consists of a set of related tasks, which are in turn composed of related operations.</span></span> <span data-ttu-id="221cd-111">So erteilt z. B. die Aufgabe **Berichte verwalten** Zugriff auf folgende Berichtsservervorgänge: Anzeigen, Hinzufügen, Aktualisieren, Löschen und Planen von Berichten sowie Aktualisieren von Berichtseigenschaften.</span><span class="sxs-lookup"><span data-stu-id="221cd-111">For example, the **Manage reports** task grants access to the following report server operations: view reports, add report, update report, delete report, schedule report, and update report properties.</span></span>  
  
## <a name="identity-and-access-control-for-sharepoint-mode"></a><span data-ttu-id="221cd-112">Identität und Zugriffssteuerung für den SharePoint-Modus</span><span class="sxs-lookup"><span data-stu-id="221cd-112">Identity and Access Control for SharePoint Mode</span></span>  
 <span data-ttu-id="221cd-113">Im integrierten SharePoint-Modus werden die Authentifizierung und die Autorisierung auf der SharePoint-Website verarbeitet, bevor Anforderungen den Berichtsserver erreichen.</span><span class="sxs-lookup"><span data-stu-id="221cd-113">In SharePoint integrated mode, authentication and authorization are handled on the SharePoint site, before requests reach the report server.</span></span> <span data-ttu-id="221cd-114">Abhängig von der Konfiguration der Authentifizierung enthalten Anforderungen von einer SharePoint-Website ein Sicherheitstoken oder einen vertrauenswürdigen Benutzernamen.</span><span class="sxs-lookup"><span data-stu-id="221cd-114">Depending on how you configure authentication, requests from a SharePoint site include a security token or a trusted user name.</span></span> <span data-ttu-id="221cd-115">Durch die für SharePoint-Benutzer und -Gruppen festgelegten Berechtigungen wird der Zugriff auf in SharePoint-Bibliotheken gespeicherte Berichtsserverelemente autorisiert.</span><span class="sxs-lookup"><span data-stu-id="221cd-115">Permissions that you set for SharePoint users and groups authorize access to report server items that are placed in SharePoint libraries.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="221cd-116">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="221cd-116">In This Section</span></span>  
 [<span data-ttu-id="221cd-117">Granting Permissions on a Native Mode Report Server (Erteilen von Berechtigungen für einen Berichtsserver im einheitlichen Modus)</span><span class="sxs-lookup"><span data-stu-id="221cd-117">Granting Permissions on a Native Mode Report Server</span></span>](granting-permissions-on-a-native-mode-report-server.md)  
 <span data-ttu-id="221cd-118">Beschreibt das rollenbasierte Autorisierungsmodell, das Zugriff auf Inhalt und Vorgänge bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="221cd-118">Describes the role-based authorization model that provides access to content and operations.</span></span>  
  
 [<span data-ttu-id="221cd-119">Granting Permissions on Report Server Items on a SharePoint Site (Erteilen von Berechtigungen für Berichtsserverelemente auf einer SharePoint-Website)</span><span class="sxs-lookup"><span data-stu-id="221cd-119">Granting Permissions on Report Server Items on a SharePoint Site</span></span>](granting-permissions-on-report-server-items-on-a-sharepoint-site.md)  
 <span data-ttu-id="221cd-120">Erläutert, wie mit SharePoint-Gruppen, Berechtigungsebenen und Berechtigungen der Zugriff auf einen Berichtsserver gesteuert werden kann.</span><span class="sxs-lookup"><span data-stu-id="221cd-120">Explains how SharePoint groups, permission levels, and permissions are used to control access to a report server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="221cd-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="221cd-121">See Also</span></span>  
 <span data-ttu-id="221cd-122">[Authentifizierung mit dem Berichtsserver](authentication-with-the-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="221cd-122">[Authentication with the Report Server](authentication-with-the-report-server.md) </span></span>  
 [<span data-ttu-id="221cd-123">Granting Permissions on a Native Mode Report Server (Erteilen von Berechtigungen für einen Berichtsserver im einheitlichen Modus)</span><span class="sxs-lookup"><span data-stu-id="221cd-123">Granting Permissions on a Native Mode Report Server</span></span>](granting-permissions-on-a-native-mode-report-server.md)  
  
  
