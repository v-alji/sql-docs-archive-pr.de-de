---
title: Report Server-Windows-Dienst (MSSQLServer) 107 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- MSSQLServer 107 error
ms.assetid: 52b5704b-27f9-400a-a821-d8fa0786afe4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 8651f98b47b698fbe3cfb6a152b9220a84ed7256
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616933"
---
# <a name="report-server-windows-service-mssqlserver-107"></a><span data-ttu-id="ac5d6-102">Report Server-Windows-Dienst (MSSQLServer) 107</span><span class="sxs-lookup"><span data-stu-id="ac5d6-102">Report Server Windows Service (MSSQLServer) 107</span></span>
    
## <a name="details"></a><span data-ttu-id="ac5d6-103">Details</span><span class="sxs-lookup"><span data-stu-id="ac5d6-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ac5d6-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="ac5d6-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="ac5d6-105">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="ac5d6-105">Event ID</span></span>|<span data-ttu-id="ac5d6-106">107</span><span class="sxs-lookup"><span data-stu-id="ac5d6-106">107</span></span>|  
|<span data-ttu-id="ac5d6-107">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="ac5d6-107">Event Source</span></span>|<span data-ttu-id="ac5d6-108">Report Server-Windows-Dienst</span><span class="sxs-lookup"><span data-stu-id="ac5d6-108">Report Server Windows Service</span></span>|  
|<span data-ttu-id="ac5d6-109">Komponente</span><span class="sxs-lookup"><span data-stu-id="ac5d6-109">Component</span></span>|[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]|  
|<span data-ttu-id="ac5d6-110">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="ac5d6-110">Message Text</span></span>|<span data-ttu-id="ac5d6-111">Es kann keine Verbindung zwischen dem Report Server-Windows-Dienst (MSSQLSERVER) und der Berichtsserver-Datenbank hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="ac5d6-111">Report Server Windows Service (MSSQLSERVER) cannot connect to the report server database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ac5d6-112">Erklärung</span><span class="sxs-lookup"><span data-stu-id="ac5d6-112">Explanation</span></span>  
 <span data-ttu-id="ac5d6-113">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Report Server-Dienst kann keine Verbindung zur Berichtsserver-Datenbank herstellen.</span><span class="sxs-lookup"><span data-stu-id="ac5d6-113">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Report Server service cannot connect to the report server database.</span></span> <span data-ttu-id="ac5d6-114">Dieser Fehler tritt während des Neustarts eines Diensts auf, wenn keine Verbindung zur Berichtsserver-Datenbank hergestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="ac5d6-114">This error occurs during a service restart if a connection to the report server database cannot be established.</span></span> <span data-ttu-id="ac5d6-115">Der Fehler tritt unter den folgenden Bedingungen auf:</span><span class="sxs-lookup"><span data-stu-id="ac5d6-115">Conditions under which this error occurs include the following:</span></span>  
  
-   <span data-ttu-id="ac5d6-116">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-[!INCLUDE[ssDE](../../includes/ssde-md.md)]-Dienst wird nicht ausgeführt, wenn der Berichtsserverdienst gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="ac5d6-116">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] service is not running when the Report Server service starts.</span></span>  
  
-   <span data-ttu-id="ac5d6-117">Die Verbindung zum [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Dienst schlägt fehl, da Remoteverbindungen oder das TCP/IP-Protokoll nicht aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="ac5d6-117">The connection to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] service fails because remote connections or the TCP/IP protocol is not enabled.</span></span>  
  
-   <span data-ttu-id="ac5d6-118">Die Berichtsserver-Datenbank wurde nicht ordnungsgemäß konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="ac5d6-118">The report server database is not configured correctly.</span></span>  
  
-   <span data-ttu-id="ac5d6-119">Das Dienstkonto wurde nicht ordnungsgemäß konfiguriert, oder das Konto verfügt nicht mehr über die Berechtigung für die Berichtsserver-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="ac5d6-119">The service account is not configured correctly, or the account no longer has permissions on the report server database.</span></span> <span data-ttu-id="ac5d6-120">Dies tritt auf, wenn Sie beim Einrichten des Kontos oder der Berichtsserver-Datenbank nicht das [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Konfigurationstool verwenden.</span><span class="sxs-lookup"><span data-stu-id="ac5d6-120">This can occur if you do not use the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool to set up the account or the report server database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ac5d6-121">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="ac5d6-121">User Action</span></span>  
 <span data-ttu-id="ac5d6-122">Starten Sie den [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Dienst, wenn er nicht bereits ausgeführt wird, und stellen Sie sicher, dass für das TCP/IP-Protokoll Remoteverbindungen zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="ac5d6-122">Start the [!INCLUDE[ssDE](../../includes/ssde-md.md)] service if it is not running and check that remote connections are enabled for TCP/IP protocol.</span></span>  
  
 <span data-ttu-id="ac5d6-123">Verwenden Sie zum Konfigurieren der Berichtsserver-Datenbank und des Dienstkontos das [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Konfigurationstool.</span><span class="sxs-lookup"><span data-stu-id="ac5d6-123">Use the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool to configure the report server database and service account.</span></span>  
  
## <a name="internal-only"></a><span data-ttu-id="ac5d6-124">Nur intern</span><span class="sxs-lookup"><span data-stu-id="ac5d6-124">Internal-Only</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac5d6-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ac5d6-125">See Also</span></span>  
 <span data-ttu-id="ac5d6-126">[Konfigurieren des Berichtsserver-Dienstkontos &#40;SSRS-Konfigurations-Manager&#41;](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="ac5d6-126">[Configure the Report Server Service Account &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="ac5d6-127">[Reporting Services-Konfigurations-Manager &#40;einheitlicher Modus&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="ac5d6-127">[Reporting Services Configuration Manager &#40;Native Mode&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) </span></span>  
 [<span data-ttu-id="ac5d6-128">Start and Stop the Report Server Service (Starten und Beenden des Berichtsserverdiensts)</span><span class="sxs-lookup"><span data-stu-id="ac5d6-128">Start and Stop the Report Server Service</span></span>](../report-server/start-and-stop-the-report-server-service.md)  
  
  
