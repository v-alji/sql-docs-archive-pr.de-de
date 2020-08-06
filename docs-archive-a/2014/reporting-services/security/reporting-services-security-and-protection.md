---
title: Sicherheit und Schutz für Reporting Services | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- security [Reporting Services]
- Reporting Services, security
ms.assetid: 270075c5-bf12-4467-a775-abbda3d954a5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0f8c7a4186c5236260fb27d8de107ce8c97bd363
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621863"
---
# <a name="reporting-services-security-and-protection"></a><span data-ttu-id="d9003-102">Sicherheit und Schutz für Reporting Services</span><span class="sxs-lookup"><span data-stu-id="d9003-102">Reporting Services Security and Protection</span></span>
  <span data-ttu-id="d9003-103">In diesem Abschnitt wird beschrieben, welche Sicherheitsfunktionen in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d9003-103">You can use information in this section to learn about the security features of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="d9003-104">In diesem Abschnitt werden auch die Autorisierungsmodelle und die Authentifizierungsanbieter erläutert, die in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="d9003-104">This section also explains the authorization models and authentication providers supported in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>  
  
## <a name="extended-protection-for-authentication"></a><span data-ttu-id="d9003-105">Erweiterter Schutz für die Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="d9003-105">Extended Protection for Authentication</span></span>  
 <span data-ttu-id="d9003-106">Der erweiterte Schutz für die Authentifizierung wird ab [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d9003-106">Beginning with [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], support for Extended Protection for Authentication is available.</span></span> <span data-ttu-id="d9003-107">Die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Funktion unterstützt die Verwendung der Kanalbindung und Dienstbindung, um den Authentifizierungsschutz zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="d9003-107">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] feature supports the use of channel binding and service binding to enhance protection of authentication.</span></span> <span data-ttu-id="d9003-108">Die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Funktionen müssen mit einem Betriebssystem verwendet werden, das erweiterten Schutz unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d9003-108">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] features need to be used with an operating system that supports Extended Protection.</span></span> <span data-ttu-id="d9003-109">Weitere Informationen finden Sie unter [Extended Protection for Authentication with Reporting Services](extended-protection-for-authentication-with-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="d9003-109">For more information, see [Extended Protection for Authentication with Reporting Services](extended-protection-for-authentication-with-reporting-services.md).</span></span>  
  
## <a name="authentication-and-authorization"></a><span data-ttu-id="d9003-110">Authentifizierung und Autorisierung</span><span class="sxs-lookup"><span data-stu-id="d9003-110">Authentication and Authorization</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="d9003-111">bietet unterschiedliche Authentifizierungstypen für Benutzer und Clientanwendungen zur Authentifizierung mit dem Berichtsserver.</span><span class="sxs-lookup"><span data-stu-id="d9003-111">provides different authentication types for users and client applications to authenticate with the report server.</span></span> <span data-ttu-id="d9003-112">Mit dem richtigen Authentifizierungstyp für Ihren Berichtsserver kann Ihr Unternehmen die den Anforderungen entsprechende Sicherheitsstufe erzielen.</span><span class="sxs-lookup"><span data-stu-id="d9003-112">Using the right authentication type for your report server enables your organization to achieve the appropriate level of security required by your organization.</span></span> <span data-ttu-id="d9003-113">Weitere Informationen finden Sie unter [Authentication with the Report Server](authentication-with-the-report-server.md).</span><span class="sxs-lookup"><span data-stu-id="d9003-113">For more information, see [Authentication with the Report Server](authentication-with-the-report-server.md).</span></span>  
  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="d9003-114">verwendet auch Rollen und Berechtigungen, um den Benutzerzugriff auf Inhalte des Berichtsserverkatalogs (d.h. wer worauf und wie zugreifen kann) zu steuern.</span><span class="sxs-lookup"><span data-stu-id="d9003-114">also employs roles and permissions to control user access to content in the report server catalog (in other words, who can access what, and how s/he can access it).</span></span> <span data-ttu-id="d9003-115">Weitere Informationen finden Sie unter [Rollen und Berechtigungen &#40;Reporting Services&#41;](roles-and-permissions-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="d9003-115">For more information, see [Roles and Permissions &#40;Reporting Services&#41;](roles-and-permissions-reporting-services.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="d9003-116">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="d9003-116">Related Tasks</span></span>  
  
|<span data-ttu-id="d9003-117">Taskbeschreibungen</span><span class="sxs-lookup"><span data-stu-id="d9003-117">Task Descriptions</span></span>|<span data-ttu-id="d9003-118">Links</span><span class="sxs-lookup"><span data-stu-id="d9003-118">Links</span></span>|  
|-----------------------|-----------|  
|<span data-ttu-id="d9003-119">Konfigurieren Sie das Secure Sockets Layer (SSL), um Clientverbindungen zum Berichtsserver zu sichern.</span><span class="sxs-lookup"><span data-stu-id="d9003-119">Configure the Secure Socket Layer (SSL) to secure client connections to the report server.</span></span>|[<span data-ttu-id="d9003-120">Konfigurieren von SSL-Verbindungen auf einem Berichtsserver im einheitlichen Modus</span><span class="sxs-lookup"><span data-stu-id="d9003-120">Configure SSL Connections on a Native Mode Report Server</span></span>](configure-ssl-connections-on-a-native-mode-report-server.md)|  
  
  
