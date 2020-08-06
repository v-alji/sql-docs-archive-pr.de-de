---
title: Verwalten eines Berichtsservers von Reporting Services im einheitlichen Modus | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Reporting Services Configuration tool
- configuration options [Reporting Services]
- report servers [Reporting Services], configuring
ms.assetid: 6ca03a09-d6a8-4c93-ba12-1c99dcbfb618
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0d44a9329074a20c04f878c055674ea563b297f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619577"
---
# <a name="manage-a-reporting-services-native-mode-report-server"></a><span data-ttu-id="80dd2-102">Verwalten eines Berichtsservers von Reporting Services im einheitlichen Modus</span><span class="sxs-lookup"><span data-stu-id="80dd2-102">Manage a Reporting Services Native Mode Report Server</span></span>
  <span data-ttu-id="80dd2-103">In diesem Abschnitt finden Sie Verfahren zum Konfigurieren einer Berichtsserverinstanz im einheitlichen Modus mithilfe des Reporting Services-Konfigurations-Managers.</span><span class="sxs-lookup"><span data-stu-id="80dd2-103">This section contains procedures for configuring a native mode report server instance using the Reporting Services Configuration Manager.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="80dd2-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="80dd2-104">In This Section</span></span>  
 <span data-ttu-id="80dd2-105">Die Themen in diesem Abschnitt sind in Kategorien geordnet, sodass Sie die benötigten Anweisungen leichter finden können.</span><span class="sxs-lookup"><span data-stu-id="80dd2-105">The topics in this section are organized into categories so that you can more easily find the instructions you want.</span></span> <span data-ttu-id="80dd2-106">Der erste Abschnitt enthält Themen zu Basiskonfigurationsaufgaben für einen Berichtsserver im einheitlichen Modus.</span><span class="sxs-lookup"><span data-stu-id="80dd2-106">The first section contains topics for basic configuration tasks for a native mode report server.</span></span> <span data-ttu-id="80dd2-107">Der zweite Abschnitt enthält Themen zur erweiterten Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="80dd2-107">The second section contains advanced configuration topics.</span></span> <span data-ttu-id="80dd2-108">Der dritte Abschnitt enthält Themen zum Konfigurieren eines Berichtsservers zur Ausführung im integrierten SharePoint-Modus.</span><span class="sxs-lookup"><span data-stu-id="80dd2-108">The third section contains topics for configuring a report server to run in SharePoint integrated mode.</span></span>  
  
### <a name="basic-configuration"></a><span data-ttu-id="80dd2-109">Basiskonfiguration</span><span class="sxs-lookup"><span data-stu-id="80dd2-109">Basic Configuration</span></span>  
 [<span data-ttu-id="80dd2-110">Reporting Services-Konfigurations-Manager &#40;einheitlicher Modus&#41;</span><span class="sxs-lookup"><span data-stu-id="80dd2-110">Reporting Services Configuration Manager &#40;Native Mode&#41;</span></span>](../../sql-server/install/reporting-services-configuration-manager-native-mode.md)  
 <span data-ttu-id="80dd2-111">Beschreibt die Schritte zum Starten des Reporting Services-Konfigurationstools.</span><span class="sxs-lookup"><span data-stu-id="80dd2-111">Provides steps for starting the Reporting Services Configuration tool.</span></span>  
  
 [<span data-ttu-id="80dd2-112">Konfigurieren eines Dienstkontos &#40;SSRS-Konfigurations-Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="80dd2-112">Configure a Service Account &#40;SSRS Configuration Manager&#41;</span></span>](../../sql-server/install/configure-a-service-account-ssrs-configuration-manager.md)  
 <span data-ttu-id="80dd2-113">Erläutert, wie Konto- und Kennwortinformationen für den Berichtsserver-Dienst angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="80dd2-113">Explains how to specify account and password information for the Report Server service.</span></span>  
  
 [<span data-ttu-id="80dd2-114">Registrieren eines Dienstprinzipalnamens &#40;SPN&#41; für einen Berichtsserver</span><span class="sxs-lookup"><span data-stu-id="80dd2-114">Register a Service Principal Name &#40;SPN&#41; for a Report Server</span></span>](register-a-service-principal-name-spn-for-a-report-server.md)  
 <span data-ttu-id="80dd2-115">Erläutert die manuelle Registrierung eines SPN für einen Berichtsserver, der unter einem Domänenbenutzerkonto in einem Netzwerk ausgeführt wird, das Kerberos-Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="80dd2-115">Explains how to manually register an SPN for a report server that runs under a domain user account on a network that uses Kerberos authentication.</span></span>  
  
 [<span data-ttu-id="80dd2-116">Konfigurieren einer URL &#40;SSRS-Konfigurations-Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="80dd2-116">Configure a URL  &#40;SSRS Configuration Manager&#41;</span></span>](../install-windows/configure-a-url-ssrs-configuration-manager.md)  
 <span data-ttu-id="80dd2-117">Beschreibt die Einrichtung einer oder mehrerer URLs, die für den Zugriff auf den Report Server-Webdienst und den Berichts-Manager verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="80dd2-117">Explains how to establish one or more URLs used to access the Report Server Web service and Report Manager.</span></span>  
  
 [<span data-ttu-id="80dd2-118">Erstellen einer Berichtsserver-Datenbank im einheitlichen Modus &#40;SSRS-Konfigurations-Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="80dd2-118">Create a Native Mode Report Server Database  &#40;SSRS Configuration Manager&#41;</span></span>](../install-windows/ssrs-report-server-create-a-native-mode-report-server-database.md)  
 <span data-ttu-id="80dd2-119">Beschreibt die Schritte zum Erstellen einer Berichtsserver-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="80dd2-119">Provides steps for creating a report server database.</span></span> <span data-ttu-id="80dd2-120">Dieses Verfahren ist für die Bereitstellung einer Reporting Services-Installation erforderlich.</span><span class="sxs-lookup"><span data-stu-id="80dd2-120">This step is required for deploying a Reporting Services installation.</span></span>  
  
### <a name="advanced-or-optional-configuration"></a><span data-ttu-id="80dd2-121">Erweiterte oder optionale Konfiguration</span><span class="sxs-lookup"><span data-stu-id="80dd2-121">Advanced or Optional Configuration</span></span>  
 [<span data-ttu-id="80dd2-122">Konfigurieren eines Berichtsservers im einheitlichen Modus für Bereitstellungen für horizontales Skalieren &#40;SSRS-Konfigurations-Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="80dd2-122">Configure a Native Mode Report Server Scale-Out Deployment &#40;SSRS Configuration Manager&#41;</span></span>](../install-windows/configure-a-native-mode-report-server-scale-out-deployment.md)  
 <span data-ttu-id="80dd2-123">Beschreibt die Schritte zum Konfigurieren mehrerer Berichtsserver für das gemeinsame Verwenden einer Berichtsserver-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="80dd2-123">Provides steps for configuring multiple report servers to share a report server database.</span></span>  
  
 [<span data-ttu-id="80dd2-124">Konfigurieren eines Berichts Servers für die e-Mail-Übermittlung &#40;SSRS-Configuration Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="80dd2-124">Configure a Report Server for E-Mail Delivery &#40;SSRS Configuration Manager&#41;</span></span>](../../sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md)  
 <span data-ttu-id="80dd2-125">Beschreibt die Schritte zum Konfigurieren eines Berichtsservers für die E-Mail-Verteilung.</span><span class="sxs-lookup"><span data-stu-id="80dd2-125">Provides steps for configuring a report server for e-mail distribution.</span></span>  
  
 [<span data-ttu-id="80dd2-126">Konfigurieren einer Firewall für den Zugriff auf den Berichtsserver</span><span class="sxs-lookup"><span data-stu-id="80dd2-126">Configure a Firewall for Report Server Access</span></span>](configure-a-firewall-for-report-server-access.md)  
 <span data-ttu-id="80dd2-127">Erklärt, wie für eingehende Anforderungen und ausgehende Antworten von einem Berichtsserver verwendete Ports geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="80dd2-127">Explains how to open ports used for inbound requests and outbound responses from a report server.</span></span>  
  
 [<span data-ttu-id="80dd2-128">Konfigurieren eines Berichtsservers im einheitlichen Modus für die lokale Verwaltung &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="80dd2-128">Configure a Native Mode Report Server for Local Administration &#40;SSRS&#41;</span></span>](configure-a-native-mode-report-server-for-local-administration-ssrs.md)  
 <span data-ttu-id="80dd2-129">Beschreibt zusätzliche Schritte, die erforderlich sind, um über http://localhost eine Verbindung mit dem Berichts-Manager oder einem Berichtsserver herzustellen.</span><span class="sxs-lookup"><span data-stu-id="80dd2-129">Describes additional steps required to connect to Report Manager or a report server using http://localhost.</span></span>  
  
 [<span data-ttu-id="80dd2-130">Configure a Report Server for Remote Administration (Konfigurieren eines Berichtsservers für die Remoteverwaltung)</span><span class="sxs-lookup"><span data-stu-id="80dd2-130">Configure a Report Server for Remote Administration</span></span>](configure-a-report-server-for-remote-administration.md)  
 <span data-ttu-id="80dd2-131">Erläutert, wie eine Remote-Berichtsserverinstanz so konfiguriert werden kann, dass Sie mit ihr eine Verbindung herstellen und sie über einen anderen Computer konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="80dd2-131">Explains how to configure a remote report server instance so that you can connect to and configure it from a different computer.</span></span>  
  
 [<span data-ttu-id="80dd2-132">Turn Reporting Services Features On or Off (Aktivieren und Deaktivieren der Reporting Services-Funktionen)</span><span class="sxs-lookup"><span data-stu-id="80dd2-132">Turn Reporting Services Features On or Off</span></span>](turn-reporting-services-features-on-or-off.md)  
 <span data-ttu-id="80dd2-133">Erklärt, wie nicht verwendete Funktionen in einer Reporting Services-Installation entfernt werden können.</span><span class="sxs-lookup"><span data-stu-id="80dd2-133">Explains how to remove unused features in a Reporting Services installation.</span></span>  
  
 [<span data-ttu-id="80dd2-134">Aktivieren von Remotefehlern &#40;Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="80dd2-134">Enable Remote Errors &#40;Reporting Services&#41;</span></span>](enable-remote-errors-reporting-services.md)  
 <span data-ttu-id="80dd2-135">Erläutert, wie Servereigenschaften auf einem Berichtsserver festgelegt werden, um zusätzliche Informationen zu auf Remoteservern aufgetretenen Fehlerbedingungen zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="80dd2-135">Explains how to set server properties on a report server to return additional information about error conditions that occur on remote servers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80dd2-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="80dd2-136">See Also</span></span>  
 <span data-ttu-id="80dd2-137">[Konfigurieren und Verwalten eines Berichtsservers &#40;einheitlicher SSRS-Modus&#41;](configure-and-administer-a-report-server-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="80dd2-137">[Configure and Administer a Report Server &#40;SSRS Native Mode&#41;](configure-and-administer-a-report-server-ssrs-native-mode.md) </span></span>  
 [<span data-ttu-id="80dd2-138">Konfiguration und Verwaltung eines Berichtsservers (SharePoint-Modus von Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="80dd2-138">Configuration and Administration of a Report Server &#40;Reporting Services SharePoint Mode&#41;</span></span>](../configure-administer-report-server-reporting-services-sharepoint-mode.md)  
  
  
