---
title: Installieren von ADOMD.net auf Web-Front-End-Servern, die die zentral Administration ausführen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: c2372180-e847-4cdb-b267-4befac3faf7e
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 0d9f52bf612c4878a8dacd4f5acfdcc135ae115e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609034"
---
# <a name="install-adomdnet-on-web-front-end-servers-running-central-administration"></a>Installieren von ADOMD.NET auf Web-Front-End-Servern, auf denen die Zentraladministration ausgeführt wird
  Wenn Sie PowerPivot für SharePoint in einer Farm installieren, die die Topologie "Zentraladministration ohne Excel Services oder PowerPivot für SharePoint" aufweist, laden Sie die Microsoft ADOMD.NET-Clientbibliothek herunter und installieren diese, wenn Sie Vollzugriff auf die integrierten Berichte im PowerPivot-Management-Dashboard erhalten möchten. Einige Berichte im Dashboard verwenden ADOMD.NET für den Zugriff auf interne Daten, die Berichtsdaten zur PowerPivot-Abfrageverarbeitung und zum Serverzustand in der Farm liefern.  
  
 **[!INCLUDE[applies](../../includes/applies-md.md)]** SharePoint 2010  
  
 Bei SharePoint 2013 ist der Anbieter im SQL Server Feature Pack enthalten. Informationen zum Herunterladen von spPowerPivot.msi finden Sie unter [Microsoft SQL Server 2014 Feature Pack](https://www.microsoft.com/download/details.aspx?id=35577) .  
  
### <a name="download-and-install-the-client-library"></a>Herunterladen und Installieren der Clientbibliothek  
  
1.  Suchen Sie auf der [Seite "SQL Server 2014 Feature Pack](https://go.microsoft.com/fwlink/?LinkID=296473)" nach Microsoft ADOMD.net.  
  
2.  Laden Sie das x64-Paket des `SQL_AS_ADOMD.msi`-Installationsprogramms herunter.  
  
3.  Führen Sie die MSI-Datei aus, um die Bibliothek zu installieren.  
  
4.  Setzen Sie IIS zurück, nachdem die Installation beendet wurde. Öffnen Sie eine Administrator Eingabeaufforderung, und geben Sie **iisreset**ein.  
  
### <a name="verify-installation"></a>Überprüfen der Installation  
  
1.  Wechseln Sie zu Windows\Assembly.  
  
2.  Klicken Sie mit der rechten Maustaste auf Microsoft. AnalysisServices. AdomdClient, und wählen Sie **Eigenschaften**aus.  
  
3.  Klicken Sie auf **Version**.  
  
4.  Vergewissern Sie sich, dass die Version 12,00 enthält.\<build number> und die Beschreibung lautet Microsoft. analysisservice. AdomdClient.  
  
## <a name="see-also"></a>Weitere Informationen  
 [PowerPivot-Management-Dashboard und Verwendungsdaten](https://docs.microsoft.com/analysis-services/power-pivot-sharepoint/power-pivot-management-dashboard-and-usage-data)  
  
  
