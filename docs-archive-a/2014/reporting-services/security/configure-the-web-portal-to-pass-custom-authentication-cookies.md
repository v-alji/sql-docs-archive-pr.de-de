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
# <a name="configure-report-manager-to-pass-custom-authentication-cookies"></a>Konfigurieren des Berichts-Managers für die Übergabe von benutzerdefinierten Authentifizierungscookies
  Falls Sie eine benutzerdefinierte Authentifizierungserweiterung verwenden, sollten Sie den Berichts-Manager für die Übertragung von benutzerdefinierten Authentifizierungscookies konfigurieren. Andernfalls überträgt der Berichts-Manager Cookies nur über HTTP-Anforderungen, die auf den Berichtsserver beschränkt sind. Sollen zusätzliche Cookies übertragen werden, müssen Sie Änderungen an der Datei RSReportServer.Config vornehmen.  
  
## <a name="modifying-the-rsreportserverconfig-file"></a>Ändern der Datei RSReportServer.Config  
 Sie können Berichts-Manager aktivieren, um zusätzliche Cookies an den Berichts Server zu übertragen, indem Sie `PassThroughCookies` den Berichts-Manager Konfigurationseinstellungen in der RSReportServer.config Datei ein <>-Element hinzufügen. Die Übertragung zusätzlicher Cookies ist vor allem bei Verwendung einer Authentifizierungslösung mit einmaliger Anmeldung nützlich, die nicht nur die Authentifizierungscookies des Berichtsservers, sondern auch Cookies der Authentifizierungssysteme von Drittanbietern benötigt.  
  
 Um zusätzliche Cookies zu aktivieren, die über HTTP-Anforderungen übertragen werden sollen, wenn der Berichts-Manager verwendet wird, legen Sie in der Datei RSReportServer.config die folgenden Elemente fest:  
  
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
  
## <a name="see-also"></a>Weitere Informationen  
 [Authentifizierung mit dem Berichtsserver](authentication-with-the-report-server.md)   
 [RSReportServer-Konfigurationsdatei](../report-server/rsreportserver-config-configuration-file.md)   
 [Übersicht über Sicherheitserweiterungen](../extensions/security-extension/security-extensions-overview.md)   
 [Konfigurieren und Verwalten eines Berichtsservers &#40;einheitlicher SSRS-Modus&#41;](../report-server/configure-and-administer-a-report-server-ssrs-native-mode.md)  
  
  
