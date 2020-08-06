---
title: Konfigurieren von Berichts-Manager für die Übergabe von benutzerdefinierten Authentifizierungs Cookies | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- authentication [Reporting Services]
- extensions [Reporting Services], custom security
ms.assetid: 91aeb053-149e-4562-ae4c-a688d0e1b2ba
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 90e8798fb91152ec64e7f290dc1522fc8eaa451c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615262"
---
# <a name="configure-report-manager-to-pass-custom-authentication-cookies"></a><span data-ttu-id="b6783-102">Konfigurieren des Berichts-Managers für die Übergabe von benutzerdefinierten Authentifizierungscookies</span><span class="sxs-lookup"><span data-stu-id="b6783-102">Configure Report Manager to Pass Custom Authentication Cookies</span></span>
  <span data-ttu-id="b6783-103">Falls Sie eine benutzerdefinierte Authentifizierungserweiterung verwenden, sollten Sie den Berichts-Manager für die Übertragung von benutzerdefinierten Authentifizierungscookies konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b6783-103">If you are using a custom authentication extension, you should configure Report Manager to transmit custom authentication cookies.</span></span> <span data-ttu-id="b6783-104">Andernfalls überträgt der Berichts-Manager Cookies nur über HTTP-Anforderungen, die auf den Berichtsserver beschränkt sind.</span><span class="sxs-lookup"><span data-stu-id="b6783-104">Otherwise, Report Manager will only transmit cookies through HTTP requests specific to the report server.</span></span> <span data-ttu-id="b6783-105">Sollen zusätzliche Cookies übertragen werden, müssen Sie Änderungen an der Datei RSReportServer.Config vornehmen.</span><span class="sxs-lookup"><span data-stu-id="b6783-105">If you want to transmit additional cookies, you must modify the RSReportServer.Config file.</span></span>  
  
## <a name="modifying-the-rsreportserverconfig-file"></a><span data-ttu-id="b6783-106">Ändern der Datei RSReportServer.Config</span><span class="sxs-lookup"><span data-stu-id="b6783-106">Modifying the RSReportServer.Config File</span></span>  
 <span data-ttu-id="b6783-107">Sie können Berichts-Manager aktivieren, um zusätzliche Cookies an den Berichts Server zu übertragen, indem Sie `PassThroughCookies` den Berichts-Manager Konfigurationseinstellungen in der RSReportServer.config Datei ein <>-Element hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b6783-107">You can enable Report Manager to transmit additional cookies through to the report server by adding a <`PassThroughCookies`> element to the Report Manager configuration settings in the RSReportServer.config file.</span></span> <span data-ttu-id="b6783-108">Die Übertragung zusätzlicher Cookies ist vor allem bei Verwendung einer Authentifizierungslösung mit einmaliger Anmeldung nützlich, die nicht nur die Authentifizierungscookies des Berichtsservers, sondern auch Cookies der Authentifizierungssysteme von Drittanbietern benötigt.</span><span class="sxs-lookup"><span data-stu-id="b6783-108">Transmitting additional cookies is helpful in a single sign-on authentication solution that requires not only the report server authentication cookies, but also cookies from a third-party authentication system.</span></span>  
  
 <span data-ttu-id="b6783-109">Um zusätzliche Cookies zu aktivieren, die über HTTP-Anforderungen übertragen werden sollen, wenn der Berichts-Manager verwendet wird, legen Sie in der Datei RSReportServer.config die folgenden Elemente fest:</span><span class="sxs-lookup"><span data-stu-id="b6783-109">To enable additional cookies to be transmitted through HTTP requests when using Report Manager, set the following elements in the RSReportServer.config file:</span></span>  
  
```  
<UI>  
   <CustomAuthenticationUI>  
      ...  
      <PassThroughCookies>  
         <PassThroughCookie>cookiename1</PassThroughCookie>  
         <PassThroughCookie>cookiename2</PassThroughCookie>  
      </PassThroughCookies>  
   </CustomAuthenticationUI>  
      ...  
</UI>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b6783-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b6783-110">See Also</span></span>  
 <span data-ttu-id="b6783-111">[Authentifizierung mit dem Berichtsserver](authentication-with-the-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="b6783-111">[Authentication with the Report Server](authentication-with-the-report-server.md) </span></span>  
 <span data-ttu-id="b6783-112">[RSReportServer-Konfigurationsdatei](../report-server/rsreportserver-config-configuration-file.md) </span><span class="sxs-lookup"><span data-stu-id="b6783-112">[RSReportServer Configuration File](../report-server/rsreportserver-config-configuration-file.md) </span></span>  
 <span data-ttu-id="b6783-113">[Übersicht über Sicherheitserweiterungen](../extensions/security-extension/security-extensions-overview.md) </span><span class="sxs-lookup"><span data-stu-id="b6783-113">[Security Extensions Overview](../extensions/security-extension/security-extensions-overview.md) </span></span>  
 [<span data-ttu-id="b6783-114">Konfigurieren und Verwalten eines Berichtsservers &#40;einheitlicher SSRS-Modus&#41;</span><span class="sxs-lookup"><span data-stu-id="b6783-114">Configure and Administer a Report Server &#40;SSRS Native Mode&#41;</span></span>](../report-server/configure-and-administer-a-report-server-ssrs-native-mode.md)  
  
  
