---
title: Konfigurieren und Verwalten eines Berichtsservers (einheitlicher SSRS-Modus) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/10/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Reporting Services, components
- deploying [Reporting Services], component options
- report servers [Reporting Services], component options
- configuration options [Reporting Services]
- administering Reporting Services
- components [Reporting Services], configuring
- configuring servers [Reporting Services]
ms.assetid: cfec012b-56f1-4346-9814-247acf22351c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5164fd2f9170cb092a45394f64f06d7622253f2b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619597"
---
# <a name="configure-and-administer-a-report-server-ssrs-native-mode"></a><span data-ttu-id="9fdcb-102">Konfigurieren und Verwalten eines Berichtsservers (einheitlicher SSRS-Modus)</span><span class="sxs-lookup"><span data-stu-id="9fdcb-102">Configure and Administer a Report Server (SSRS Native Mode)</span></span>
  <span data-ttu-id="9fdcb-103">In diesem Thema werden die Vorgehensweisen zum Konfigurieren von [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="9fdcb-103">This topic summarizes the approaches that you can use to configure [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="9fdcb-104">Es enthält außerdem eine Liste der Themen, in denen das Konfigurieren bestimmter Komponenten, Funktionen und Serverfunktionen erläutert wird.</span><span class="sxs-lookup"><span data-stu-id="9fdcb-104">It also includes a list of topics that explain how to configure specific components, features, or server capabilities.</span></span> <span data-ttu-id="9fdcb-105">Zum Konfigurieren von [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]können Sie folgendermaßen vorgehen:</span><span class="sxs-lookup"><span data-stu-id="9fdcb-105">To configure [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you can:</span></span>  
  
-   <span data-ttu-id="9fdcb-106">Rufen Sie den Reporting Services-Konfigurations-Manager auf.</span><span class="sxs-lookup"><span data-stu-id="9fdcb-106">Use the Reporting Services Configuration Manager.</span></span> <span data-ttu-id="9fdcb-107">Viele Themen in diesem Abschnitt enthalten Informationen zum Konfigurieren bestimmter Funktionen über dieses Tool.</span><span class="sxs-lookup"><span data-stu-id="9fdcb-107">Many of the topics in this section contain information about how to configure specific features through this tool.</span></span>  
  
-   <span data-ttu-id="9fdcb-108">Verwenden von [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] zum Anpassen von Servereigenschaften, zum Aktivieren von „Meine Berichte“ und Ablaufverfolgungsprotokollen und zum siteweiten Festlegen von Standardwerten.</span><span class="sxs-lookup"><span data-stu-id="9fdcb-108">Use [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] to customize server properties, enable My Reports, enable trace logs, and set site-wide defaults.</span></span> <span data-ttu-id="9fdcb-109">Weitere Informationen zur Verwaltung von Siteeinstellungen finden Sie unter [Reporting Services-Berichtsserver &#40;einheitlicher Modus&#41;](reporting-services-report-server-native-mode.md) .</span><span class="sxs-lookup"><span data-stu-id="9fdcb-109">For more information about site settings, see [Reporting Services Report Server &#40;Native Mode&#41;](reporting-services-report-server-native-mode.md) for Management Studio.</span></span> <span data-ttu-id="9fdcb-110">Beachten Sie, dass Sie Skripts erstellen und ausführen können, mit denen Servereigenschaften programmgesteuert festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="9fdcb-110">Note that you can create and run script that sets server properties programmatically.</span></span> <span data-ttu-id="9fdcb-111">Weitere Informationen finden Sie unter [Skripts für Bereitstellungs- und Verwaltungsaufgaben](../tools/script-deployment-and-administrative-tasks.md) und [Berichtsserver-Systemeigenschaften](../report-server-web-service/net-framework/reporting-services-properties-report-server-system-properties.md).</span><span class="sxs-lookup"><span data-stu-id="9fdcb-111">For more information, see [Script Deployment and Administrative Tasks](../tools/script-deployment-and-administrative-tasks.md) and [Report Server System Properties](../report-server-web-service/net-framework/reporting-services-properties-report-server-system-properties.md).</span></span>  
  
-   <span data-ttu-id="9fdcb-112">Verwenden Sie den Berichts-Manager zum Gewähren von Berechtigungen für den Zugriff auf den Berichtsserver.</span><span class="sxs-lookup"><span data-stu-id="9fdcb-112">Use Report Manager to grant permissions to access the report server.</span></span> <span data-ttu-id="9fdcb-113">Berechtigungen werden durch Rollenzuweisungen festgelegt, die Sie für jeden Benutzer bzw. jedes Gruppenkonto definieren.</span><span class="sxs-lookup"><span data-stu-id="9fdcb-113">Permissions are conveyed through role assignments that you define for each user or group account.</span></span> <span data-ttu-id="9fdcb-114">Weitere Informationen finden Sie unter [Rollen und Berechtigungen &#40;Reporting Services&#41;](../security/roles-and-permissions-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="9fdcb-114">For more information, see [Roles and Permissions &#40;Reporting Services&#41;](../security/roles-and-permissions-reporting-services.md).</span></span>  
  
-   <span data-ttu-id="9fdcb-115">Ändern Sie alternativ die Konfigurationsdateien, wenn Sie Anwendungseinstellungen ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="9fdcb-115">Optionally, modify configuration files to change application settings.</span></span> <span data-ttu-id="9fdcb-116">Weitere Informationen zu den entsprechenden Dateien und Richtlinien für deren Änderung finden Sie unter [Reporting Services Configuration Files](reporting-services-configuration-files.md).</span><span class="sxs-lookup"><span data-stu-id="9fdcb-116">For more information about each file and guidelines for modifying them, see [Reporting Services Configuration Files](reporting-services-configuration-files.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9fdcb-117">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="9fdcb-117">In This Section</span></span>  
 [<span data-ttu-id="9fdcb-118">Konfigurieren von Berichtsserver-URLs &#40;SSRS-Konfigurations-Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="9fdcb-118">Configure Report Server URLs  &#40;SSRS Configuration Manager&#41;</span></span>](../install-windows/configure-report-server-urls-ssrs-configuration-manager.md)  
 <span data-ttu-id="9fdcb-119">Beschreibt die Definition von URLs, die für den Zugriff auf den Berichtsserver und den Berichts-Manager verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9fdcb-119">Describes how to define the URLs used to access the report server and Report Manager.</span></span>  
  
 [<span data-ttu-id="9fdcb-120">Konfigurieren des Berichtsserver-Dienstkontos &#40;SSRS-Konfigurations-Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="9fdcb-120">Configure the Report Server Service Account &#40;SSRS Configuration Manager&#41;</span></span>](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md)  
 <span data-ttu-id="9fdcb-121">Gibt Empfehlungen und nennt Schritte zum Ändern von Dienstkonten und Kennwörtern.</span><span class="sxs-lookup"><span data-stu-id="9fdcb-121">Provides recommendations and steps on how to modify service account and password.</span></span>  
  
 [<span data-ttu-id="9fdcb-122">Erstellen einer Berichtsserver-Datenbank &#40;SSRS-Konfigurations-Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="9fdcb-122">Create a Report Server Database  &#40;SSRS Configuration Manager&#41;</span></span>](../../sql-server/install/create-a-report-server-database-ssrs-configuration-manager.md)  
 <span data-ttu-id="9fdcb-123">Beschreibt das Erstellen einer Berichtsserver-Datenbank, die für das Speichern von Server-Metadaten und -Objekten erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="9fdcb-123">Describes how to create a report server database, required for storing server metadata and objects.</span></span>  
  
 [<span data-ttu-id="9fdcb-124">Konfigurieren einer Verbindung mit der Berichtsserver-Datenbank &#40;SSRS-Konfigurations-Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="9fdcb-124">Configure a Report Server Database Connection  &#40;SSRS Configuration Manager&#41;</span></span>](../../sql-server/install/configure-a-report-server-database-connection-ssrs-configuration-manager.md)  
 <span data-ttu-id="9fdcb-125">Beschreibt das Ändern der Verbindungszeichenfolge, die vom Berichtsserver zum Herstellen einer Verbindung mit der Berichtsserver-Datenbank verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9fdcb-125">Describes how to modify the connection string used by the report server to connect to the report server database.</span></span>  
  
 [<span data-ttu-id="9fdcb-126">Konfigurieren eines Berichts Servers für die e-Mail-Übermittlung &#40;SSRS-Configuration Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="9fdcb-126">Configure a Report Server for E-Mail Delivery &#40;SSRS Configuration Manager&#41;</span></span>](../../sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md)  
 <span data-ttu-id="9fdcb-127">Beschreibt, wie Sie für einen Berichtsserver die Verteilung von Berichten per E-Mail konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="9fdcb-127">Describes how to configure a report server to support e-mail report distribution.</span></span>  
  
 [<span data-ttu-id="9fdcb-128">Konfigurieren des Kontos für die unbeaufsichtigte Ausführung &#40;SSRS-Konfigurations-Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="9fdcb-128">Configure the Unattended Execution Account &#40;SSRS Configuration Manager&#41;</span></span>](../install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md)  
 <span data-ttu-id="9fdcb-129">Beschreibt, wie Sie für ein Benutzerkonto die Verarbeitung von Berichten im unbeaufsichtigten Modus konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="9fdcb-129">Describes how to configure a user account to process reports in unattended mode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fdcb-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9fdcb-130">See Also</span></span>  
 <span data-ttu-id="9fdcb-131">[Konfigurieren des Berichts-Generator Zugriffs](configure-report-builder-access.md) </span><span class="sxs-lookup"><span data-stu-id="9fdcb-131">[Configure Report Builder Access](configure-report-builder-access.md) </span></span>  
 <span data-ttu-id="9fdcb-132">[Reporting Services-Konfigurationsdateien](reporting-services-configuration-files.md) </span><span class="sxs-lookup"><span data-stu-id="9fdcb-132">[Reporting Services Configuration Files](reporting-services-configuration-files.md) </span></span>  
 <span data-ttu-id="9fdcb-133">[Reporting Services-Konfigurations-Manager &#40;einheitlicher Modus&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="9fdcb-133">[Reporting Services Configuration Manager &#40;Native Mode&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) </span></span>  
 <span data-ttu-id="9fdcb-134">[Sicherheit und Schutz Reporting Services](../security/reporting-services-security-and-protection.md) </span><span class="sxs-lookup"><span data-stu-id="9fdcb-134">[Reporting Services Security and Protection](../security/reporting-services-security-and-protection.md) </span></span>  
 [<span data-ttu-id="9fdcb-135">Reporting Services-Berichtsserver &#40;einheitlicher Modus&#41;</span><span class="sxs-lookup"><span data-stu-id="9fdcb-135">Reporting Services Report Server &#40;Native Mode&#41;</span></span>](reporting-services-report-server-native-mode.md)  
  
  
