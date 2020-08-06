---
title: Reporting Services-Anmeldung (Dialogfeld) (SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.reportservicelogin.f1
ms.assetid: 2037d797-0b61-44c7-931f-6c689c3fc733
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 232ee51614a668b07263c3e3a4182f23652135bf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721040"
---
# <a name="reporting-services-login-dialog-box-ssrs"></a>Reporting Services-Anmeldung (Dialogfeld) (SSRS)
  Verwenden Sie das Dialogfeld **Reporting Services-Anmeldung** , um die Anmeldeinformationen zum Veröffentlichen von Berichten auf dem Berichtsserver bereitzustellen.  
  
-   **Hinweis** Wenn Sie zum ersten Mal einen Bericht auf einem Berichts Server veröffentlicht haben, nachdem Sie die Bereitstellungs Eigenschaft **TargetServerURL** für ein Projekt festgelegt haben, überprüfen Sie, ob der angegebene Servername dem Wert entspricht `http://localhost/reportserver` und nicht `http://localhost/reports` . Durch Angeben des `reports` -Verzeichnisses auf dem lokalen Server anstelle des `reportserver` -Verzeichnisses wird indirekt bewirkt, dass dieses Dialogfeld geöffnet wird. Weitere Informationen zum Festlegen von **TargetServerURL** finden Sie unter [Festlegen von Bereitstellungseigenschaften (Reporting Services)](set-deployment-properties-reporting-services.md).  
  
## <a name="options"></a>Tastatur  
 **Server**  
 Zeigt den Namen des Berichtsservers an. Beispiel: `http://localhost/reportserver`. Für Berichtsserver, die einen anderen Port verwenden als Standardport 80, schließen Sie die Portnummer ein. Beispiel: `http://localhost:81/reportserver`.  
  
 **Benutzername**  
 Geben Sie den Benutzernamen ein, der beim Anmelden am Webdienst verwendet werden soll.  
  
 **Kennwort**  
 Geben Sie das Kennwort ein, das beim Anmelden am Webdienst verwendet werden soll.  
  
## <a name="see-also"></a>Weitere Informationen  
 [Datenverbindungen, Datenquellen und Verbindungs Zeichenfolgen in Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md)   
 [Angeben von Anmelde Informationen und Verbindungsinformationen für Berichtsdaten Quellen](../report-data/specify-credential-and-connection-information-for-report-data-sources.md) [Berichts-Designer F1-Hilfe](report-designer-f1-help.md)  
  
  
