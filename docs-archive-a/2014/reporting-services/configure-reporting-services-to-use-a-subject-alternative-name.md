---
title: Konfigurieren Reporting Services für die Verwendung eines alternativen Antragsteller namens | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: ce458f9f-4b4f-4a58-aa75-9a90dda1e622
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0312d2d1fff8f854eb2ffb8d0dad2563212ee23b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723589"
---
# <a name="configure-reporting-services-to-use-a-subject-alternative-name"></a><span data-ttu-id="6cacc-102">Konfigurieren der Reporting Services für die Verwendung eines alternativen Antragstellernamens</span><span class="sxs-lookup"><span data-stu-id="6cacc-102">Configure Reporting Services to Use a Subject Alternative Name</span></span>
  <span data-ttu-id="6cacc-103">In diesem Thema wird erklärt, wie Sie [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] (SSRS) für die Verwendung eines alternativen Antragstellernamens (Subject Alternative Name, SAN) konfigurieren, indem Sie die Datei „rsreportserver.config“ ändern und das Tool „Netsh.exe“ verwenden.</span><span class="sxs-lookup"><span data-stu-id="6cacc-103">This topic explains how to configure [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] (SSRS) to use a subject alternative name (SAN) by modifying the rsreportserver.config file and using the Netsh.exe tool.</span></span>

||
|-|
|<span data-ttu-id="6cacc-104">**[!INCLUDE[applies](../includes/applies-md.md)]** [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] im einheitlichen Modus</span><span class="sxs-lookup"><span data-stu-id="6cacc-104">**[!INCLUDE[applies](../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Native mode</span></span>|

 <span data-ttu-id="6cacc-105">Die Anweisungen gelten sowohl für die Berichtsdienst-URL als auch die Webdienst-URL.</span><span class="sxs-lookup"><span data-stu-id="6cacc-105">The instructions apply to the Reporting Service URL as well as a Web Service URL.</span></span>

 <span data-ttu-id="6cacc-106">Zum Verwenden eines SAN muss das SSL-Zertifikat auf dem Server registriert und signiert sein und über den privaten Schlüssel verfügen.</span><span class="sxs-lookup"><span data-stu-id="6cacc-106">To use a SAN, the SSL certificate must be registered on the server, signed, and have the private key.</span></span> <span data-ttu-id="6cacc-107">Sie können kein selbstsigniertes Zertifikat verwenden.</span><span class="sxs-lookup"><span data-stu-id="6cacc-107">You cannot use a self-signed certificate</span></span>

 <span data-ttu-id="6cacc-108">URLs in [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] können für die Verwendung eines SSL-Zertifikats konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="6cacc-108">URLs in [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] can be configured to use an SSL certificate.</span></span> <span data-ttu-id="6cacc-109">Ein Zertifikat verfügt normalerweise nur über einen Antragstellernamen, der nur eine URL für eine SSL-Sitzung (Secure Sockets Layer) zulässt.</span><span class="sxs-lookup"><span data-stu-id="6cacc-109">A certificate normally has just a subject name, which allows only one URL for an SSL (Secure Sockets Layer) session.</span></span> <span data-ttu-id="6cacc-110">Der SAN ist ein zusätzliches Feld im Zertifikat, über das ein SSL-Zertifikat viele URLs überwachen und für diese gültig sein kann. Außerdem kann der SSL-Port dann mit anderen Anwendungen gemeinsam verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6cacc-110">The SAN is an additional field in the certificate that allows an SSL service to listen and be valid for many URLs, and to share the SSL port with other applications.</span></span> <span data-ttu-id="6cacc-111">Der SAN sieht wie folgt aus: www.s2.com.</span><span class="sxs-lookup"><span data-stu-id="6cacc-111">The SAN looks something like the following: www.s2.com.</span></span>

 <span data-ttu-id="6cacc-112">Weitere Informationen zu SSL-Einstellungen für [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]finden Sie unter [Konfigurieren von SSL-Verbindungen auf einem Berichtsserver im einheitlichen Modus](security/configure-ssl-connections-on-a-native-mode-report-server.md).</span><span class="sxs-lookup"><span data-stu-id="6cacc-112">For more information about SSL settings for [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], see [Configure SSL Connections on a Native Mode Report Server](security/configure-ssl-connections-on-a-native-mode-report-server.md).</span></span>

### <a name="configure-ssrs-to-use-a-subject-alternative-name-for-web-service-url"></a><span data-ttu-id="6cacc-113">Konfigurieren von SSRS für die Verwendung eines alternativen Antragstellernamens für die Webdienst-URL</span><span class="sxs-lookup"><span data-stu-id="6cacc-113">Configure SSRS to use a subject alternative name for Web Service URL</span></span>

1.  <span data-ttu-id="6cacc-114">Starten Sie den Konfigurations-Manager für Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="6cacc-114">Start Reporting Services Configuration Manager.</span></span>

     <span data-ttu-id="6cacc-115">Weitere Informationen finden Sie unter [Reporting Services-Konfigurations-Manager &#40;einheitlicher Modus&#41;](../sql-server/install/reporting-services-configuration-manager-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="6cacc-115">For more information, see [Reporting Services Configuration Manager &#40;Native Mode&#41;](../sql-server/install/reporting-services-configuration-manager-native-mode.md).</span></span>

2.  <span data-ttu-id="6cacc-116">Wählen Sie auf der Seite **Webdienst-URL** einen SSL-Port und ein SSL-Zertifikat aus.</span><span class="sxs-lookup"><span data-stu-id="6cacc-116">On the **Web Service URL** page, select an SSL port and SSL Certificate.</span></span>

     <span data-ttu-id="6cacc-117">![Reporting Services-Konfigurations-Manager](media/reportingservices-configurationmanager.png "Reporting Services-Konfigurations-Manager")</span><span class="sxs-lookup"><span data-stu-id="6cacc-117">![Reporting Services Configuration Manager](media/reportingservices-configurationmanager.png "Reporting Services Configuration Manager")</span></span>

     <span data-ttu-id="6cacc-118">Der Konfigurations-Manager registriert das SSL-Zertifikat für den Port.</span><span class="sxs-lookup"><span data-stu-id="6cacc-118">The configuration manager registers the SSL certificate for the port.</span></span>

3.  <span data-ttu-id="6cacc-119">Öffnen Sie die Datei rsreportserver.config.</span><span class="sxs-lookup"><span data-stu-id="6cacc-119">Open the rsreportserver.config file.</span></span>

     <span data-ttu-id="6cacc-120">Für den einheitlichen SSRS-Modus befindet sich die Datei standardmäßig in folgendem Ordner.</span><span class="sxs-lookup"><span data-stu-id="6cacc-120">For SSRS Native mode, the file is located by default in the following folder.</span></span>

    ```
    \Program Files\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer
    ```

4.  <span data-ttu-id="6cacc-121">Kopieren Sie den URL-Abschnitt für die Berichtsserver-Webdienstanwendung.</span><span class="sxs-lookup"><span data-stu-id="6cacc-121">Copy the URL section for the Report Server Web Service application.</span></span>

     <span data-ttu-id="6cacc-122">Im Folgenden ist beispielsweise der Original-URL-Abschnitt dargestellt.</span><span class="sxs-lookup"><span data-stu-id="6cacc-122">For example, the following is the original URL section.</span></span>

    ```
        <URL>
         <UrlString>https://localhost:443</UrlString>
         <AccountSid>S-1-5-20</AccountSid>
         <AccountName>NT Authority\NetworkService</AccountName>
        </URL>

    ```

     <span data-ttu-id="6cacc-123">Im Folgenden sehen Sie den modifizierten URL-Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="6cacc-123">The following is the modified URL section.</span></span>

    ```
    <URL>
         <UrlString>https://www.s1.com:443</UrlString>
         <AccountSid>S-1-5-20</AccountSid>
         <AccountName>NT Authority\NetworkService</AccountName>
        </URL>
        <URL>
         <UrlString>https://www.s2.com:443</UrlString>
         <AccountSid>S-1-5-20</AccountSid>
         <AccountName>NT Authority\NetworkService</AccountName>
        </URL>

    ```

5.  <span data-ttu-id="6cacc-124">Speichern Sie die Datei rsreportserver.config.</span><span class="sxs-lookup"><span data-stu-id="6cacc-124">Save the rsreportserver.config file.</span></span>

6.  <span data-ttu-id="6cacc-125">Starten Sie eine Eingabeaufforderung als Administrator, und führen Sie das Tool Netsh.exe aus.</span><span class="sxs-lookup"><span data-stu-id="6cacc-125">Start a command prompt as an administrator, and run the Netsh.exe tool.</span></span>

    ```
    C:\windows\system32\netsh
    ```

7.  <span data-ttu-id="6cacc-126">Wechseln Sie zum HTTP-Kontext, indem Sie Folgendes eingeben.</span><span class="sxs-lookup"><span data-stu-id="6cacc-126">Switch to the http context by typing the following.</span></span>

    ```
    Netsh>http
    ```

8.  <span data-ttu-id="6cacc-127">Zeigen Sie die vorhandenen URL-ACLs an, indem Sie Folgendes eingeben.</span><span class="sxs-lookup"><span data-stu-id="6cacc-127">Show the existing urlacls by typing the following.</span></span>

    ```
    Netsh http>show urlacl
    ```

     <span data-ttu-id="6cacc-128">Ein Eintrag wie der folgenden wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6cacc-128">An entry such as the following appears.</span></span>

    ```
    Reserved URL            : https:// www.s1.com:443/ReportServer/
        User: NT SERVICE\ReportServer
            Listen: Yes
            Delegate: No
            SDDL: D:(A;;GX;;;S-1-5-80-1234567890-123456789-123456789-123456789-1234567890)
    ```

     <span data-ttu-id="6cacc-129">Eine URL-ACL ist eine besitzverwaltete Zugriffssteuerungsliste (Discretionary Access Control List, DACL) für eine reservierte URL.</span><span class="sxs-lookup"><span data-stu-id="6cacc-129">An urlacl is a DACL (Discretionary Access Control List) for a reserved URL.</span></span>

9. <span data-ttu-id="6cacc-130">Erstellen Sie einen neuen Eintrag für den alternativen Antragstellernamen mit demselben Benutzer und derselben SDDL wie beim vorhandenen Eintrag, indem Sie Folgendes eingeben.</span><span class="sxs-lookup"><span data-stu-id="6cacc-130">Create a new entry for the subject alternative name, with the same user and SDDL as the existing entry, by typing the following.</span></span>

    ```
    netsh http>add urlacl  url=https://www.s2.com:443/ReportServer  
    user="NT Service\ReportServer" sddl=D:(A;;GX;;;S-1-5-80-1234567980-12346579-123456789-123456789-1234567890)

    ```

10. <span data-ttu-id="6cacc-131">Klicken Sie im Konfigurations-Manager für Reporting Services auf der Seite **Berichtsserverstatus** auf **Beenden** , und klicken Sie dann auf **Starten** , um den Berichtsserver neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="6cacc-131">On the **Report Server Status** page of the Reporting Services Configuration Manager, Click **Stop** and then click **Start** to restart the report server.</span></span>

## <a name="see-also"></a><span data-ttu-id="6cacc-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6cacc-132">See Also</span></span>
 <span data-ttu-id="6cacc-133">[RSReportServer-Konfigurationsdatei](report-server/rsreportserver-config-configuration-file.md) [Konfigurations-Manager für Reporting Services &#40;einheitlichen Modus,&#41;](../sql-server/install/reporting-services-configuration-manager-native-mode.md) [eine Reporting Services Konfigurationsdatei &#40;](report-server/modify-a-reporting-services-configuration-file-rsreportserver-config.md) RSreportserver.config&#41;[Konfigurieren von Berichts Server-URLs &#40;SSRS Configuration Manager](install-windows/configure-report-server-urls-ssrs-configuration-manager.md)&#41;</span><span class="sxs-lookup"><span data-stu-id="6cacc-133">[RSReportServer Configuration File](report-server/rsreportserver-config-configuration-file.md) [Reporting Services Configuration Manager &#40;Native Mode&#41;](../sql-server/install/reporting-services-configuration-manager-native-mode.md) [Modify a Reporting Services Configuration File &#40;RSreportserver.config&#41;](report-server/modify-a-reporting-services-configuration-file-rsreportserver-config.md) [Configure Report Server URLs  &#40;SSRS Configuration Manager&#41;](install-windows/configure-report-server-urls-ssrs-configuration-manager.md)</span></span>


