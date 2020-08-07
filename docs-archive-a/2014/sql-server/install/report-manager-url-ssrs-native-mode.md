---
title: Berichts-Manager-URL (einheitlicher SSRS-Modus) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.rsconfigtool.reportmanagervirtualdirectory.f1
ms.assetid: 45768952-23a6-45a5-b541-e7bf192b4a78
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: ec43c91bb2d24bb96cc6541d93311ce6dd234ed4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619558"
---
# <a name="report-manager-url-ssrs-native-mode"></a>Berichts-Manager-URL (einheitlicher SSRS-Modus)
  Auf der Seite der Berichts-Manager-URL können Sie die URL, mit der auf den Berichts-Manager zugegriffen wird, konfigurieren bzw. ändern. Standardmäßig übernimmt die URL des Berichts-Manager das Präfix, die IP-Adresse und den Port der URL des Report Server-Webdiensts. Dies ist darauf zurückzuführen, dass der Berichts-Manager Front-End-Zugriff auf den Webdienst bietet, der innerhalb desselben Berichtsserver-Diensts ausgeführt wird. Wenn Sie die Dienstanwendungen isolieren und den Berichts-Manager für den Zugriff auf einen Report Server-Webdienst auf einem anderen Computer verwenden, müssen Sie die Datei RSReportServer.config ändern, damit der Berichts-Manager auf eine andere Instanz verweist. Weitere Informationen zum Konfigurieren einer Berichts-Manager Verbindung mit einem Remote Berichts Server finden Sie unter [Konfigurations-Manager für Reporting Services &#40;einheitlicher Modus&#41;](../../../2014/sql-server/install/reporting-services-configuration-manager-native-mode.md).  
  
 [!INCLUDE[applies](../../includes/applies-md.md)]Einheitlicher [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Modus.  
  
 Wenn Sie den Berichtsserver so konfigurieren, dass er im integrierten SharePoint-Modus ausgeführt wird, erstellen Sie keine URL für den Berichts-Manager. Der Berichts-Manager wird auf einem Berichtsserver, der im integrierten SharePoint-Modus ausgeführt wird, nicht unterstützt. Wenn für den Berichts-Manager bereits eine URL vorhanden ist, ist diese nicht mehr verfügbar, sobald Sie den Berichtsserver für den integrierten SharePoint-Modus konfiguriert haben.  
  
 Um diese Seite zu öffnen, starten Sie den [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Konfigurations-Manager, und klicken Sie im Navigationsbereich auf **Berichts-Manager-URL** . Weitere Informationen zum Starten des Configuration Manager finden Sie unter [Konfigurations-Manager für Reporting Services &#40;einheitlicher Modus&#41;](../../../2014/sql-server/install/reporting-services-configuration-manager-native-mode.md).  
  
> [!NOTE]  
>  Wenn der Berichts-Manager nicht aktiviert ist, können Sie auf dieser Seite keine Optionen festlegen. Weitere Informationen zum Aktivieren von Berichts-Manager finden Sie unter [Konfigurations-Manager für Reporting Services &#40;einheitlicher Modus&#41;](../../../2014/sql-server/install/reporting-services-configuration-manager-native-mode.md).  
  
## <a name="options"></a>Optionen  
 **Virtuelles Verzeichnis**  
 Gibt den Namen des virtuellen Verzeichnisses für den Berichts-Manager an. Auf einem Computer kann nur jeweils ein Name eines virtuellen Verzeichnisses für jede Instanz des Berichts-Managers vorhanden sein.  
  
 **URLs**  
 Zeigt die für die aktuelle Berichts-Manager-Instanz definierte URL an.  
  
 **Erweitert**  
 Zeigt eine zusätzliche URL für die aktuelle Berichts-Manager-Instanz an.  
  
## <a name="see-also"></a>Weitere Informationen  
 [Konfigurieren einer URL &#40;SSRS-Configuration Manager&#41;](../../reporting-services/install-windows/configure-a-url-ssrs-configuration-manager.md)   
 [URLs in Konfigurationsdateien &#40;SSRS-Configuration Manager&#41;](../../reporting-services/install-windows/urls-in-configuration-files-ssrs-configuration-manager.md)   
 [Konfigurieren von Berichtsserver-URLs &#40;SSRS-Konfigurations-Manager&#41;](../../reporting-services/install-windows/configure-report-server-urls-ssrs-configuration-manager.md)  
  
  
