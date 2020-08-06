---
title: Implementieren von Sicherheitserweiterungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- security [Reporting Services], extensions
- forms-based authentication [Reporting Services]
- custom authentication [Reporting Services]
- extensions [Reporting Services], custom security
ms.assetid: d2327e7c-0d48-49e3-bcd9-3bba4e67a68b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: e5cf1fa6ce0e0a02a52e6a27f693c152d1f97152
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618511"
---
# <a name="implementing-a-security-extension"></a><span data-ttu-id="b686e-102">Implementieren von Sicherheitserweiterungen</span><span class="sxs-lookup"><span data-stu-id="b686e-102">Implementing a Security Extension</span></span>
  <span data-ttu-id="b686e-103">Die [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows-Authentifizierung ist das primäre System zum Sichern von Berichten in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b686e-103">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows Authentication is the primary system for securing reports in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="b686e-104">In bestimmten Fällen kann es jedoch sein, dass Sie das [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]-Sicherheitssystem erweitern müssen, um benutzerdefinierte Sicherheitsfunktionen in Ihr Unternehmen zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="b686e-104">In certain cases, however, you may need to extend the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] security system to accommodate custom security in your enterprise.</span></span> <span data-ttu-id="b686e-105">Hierzu verwenden Sie die Entwicklungsplattform, die von der [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]-API zur Verfügung gestellt wird.</span><span class="sxs-lookup"><span data-stu-id="b686e-105">You can do this using the development platform provided by the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] API.</span></span> <span data-ttu-id="b686e-106">In diesem Abschnitt finden Sie eine Übersicht der Sicherheitserweiterungen in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b686e-106">This section will present an overview of security extensions in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="b686e-107">Ausführliche Angaben zum Implementieren, Bereitstellen und Entfernen einer [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]-Sicherheitserweiterung finden Sie unter [SQL Server Reporting Services-Produktbeispiele](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="b686e-107">For complete details about implementing, deploying, and removing a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] security extension, please see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b686e-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="b686e-108">In This Section</span></span>  
 [<span data-ttu-id="b686e-109">Security Extensions Overview (Übersicht über Sicherheitserweiterungen)</span><span class="sxs-lookup"><span data-stu-id="b686e-109">Security Extensions Overview</span></span>](security-extensions-overview.md)  
 <span data-ttu-id="b686e-110">Stellt eine Übersicht über die Sicherheitserweiterungen der Reporting Services dar.</span><span class="sxs-lookup"><span data-stu-id="b686e-110">Provides an overview of Reporting Services Security Extensions.</span></span>  
  
 [<span data-ttu-id="b686e-111">Authentifizierung in Reporting Services</span><span class="sxs-lookup"><span data-stu-id="b686e-111">Authentication in Reporting Services</span></span>](authentication-in-reporting-services.md)  
 <span data-ttu-id="b686e-112">Erläutert die Authentifizierung in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b686e-112">Discusses authentication in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="b686e-113">Authorization in Reporting Services (Autorisierung in Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="b686e-113">Authorization in Reporting Services</span></span>](authorization-in-reporting-services.md)  
 <span data-ttu-id="b686e-114">Beschreibt die Autorisierung in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b686e-114">Covers authorization in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b686e-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b686e-115">See Also</span></span>  
 <xref:Microsoft.ReportingServices.Interfaces>   
 <span data-ttu-id="b686e-116">[Erweiterungen für Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="b686e-116">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 [<span data-ttu-id="b686e-117">Reporting Services Extension Library (Reporting Services-Erweiterungsbibliothek)</span><span class="sxs-lookup"><span data-stu-id="b686e-117">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
