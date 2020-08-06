---
title: Atom-Geräteinformationseinstellungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: fe4a56a4-5552-423c-85c1-895e2e212fee
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bdbac1500063accf868d4b538b82ba9f3b5aebb0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617817"
---
# <a name="atom-device-information-settings"></a>ATOM-Geräteinformationseinstellungen
  Die Geräteinformationseinstellungen für die Atom-Renderingerweiterung unterstützen die Übergabe des Namens eines Atom-Feeds und der zu verwendenden Zeichencodierung.  
  
 In der folgenden Tabelle sind die Geräteinformationseinstellungen für das Rendering in einem Datendienstdokument aufgeführt.  
  
|Einstellung|value|  
|-------------|-----------|  
|`DataFeed`|Wenn diese Einstellung angegeben ist, wird der Atom-Feed entsprechend dem Feednamen gerendert, der in ihr bereitgestellt wird. Andernfalls wird das Atom-Dienstdokument für den Bericht gerendert. Der eindeutige automatisch generierte Bezeichner des Datenfeeds. Dieser Wert wird intern verwendet, und Sie sollten ihn nicht ändern.|  
|**Codierung**|Der Internet Assigned Numbers Authority (IANA)-Name einer Zeichencodierung, die von .NET Framework unterstützt wird. Standardwert: `UTF-8`. Beispiele für andere Werte: ASCII, UTF-7 und UTF-16.|  
  
## <a name="see-also"></a>Weitere Informationen  
 <xref:ReportExecution2005.ReportExecutionService.Render%2A>   
 [Übergeben von Geräte Informationseinstellungen an Renderingerweiterungen](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md)   
 [Anpassen von Renderingerweiterungsparametern in RSReportServer.Config](customize-rendering-extension-parameters-in-rsreportserver-config.md)   
 [Technische Referenz (SSRS)](../../2014/reporting-services/technical-reference-ssrs.md)  
  
  
