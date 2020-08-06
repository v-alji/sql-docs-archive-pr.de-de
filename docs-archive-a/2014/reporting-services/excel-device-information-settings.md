---
title: Geräteinformationseinstellungen für Excel | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- device information settings [Reporting Services], Excel rendering
- Excel [Reporting Services], rendering
ms.assetid: bb5f3566-f033-4470-be87-1f52fb7a4ab6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d71c83195c8f91984bbbce95bd00402928fdb36e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719612"
---
# <a name="excel-device-information-settings"></a>Geräteinformationseinstellungen für Excel
  In der folgenden Tabelle werden die Geräteinformationseinstellungen zum Rendern in das Format [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] aufgeführt.  
  
|Einstellung|value|  
|-------------|-----------|  
|**OmitDocumentMap**|Gibt an, ob die Dokumentstruktur für Berichte weggelassen werden soll, die sie unterstützen. Standardwert: `false`.|  
|**OmitFormulas**|Gibt an, ob Formeln aus dem gerenderten Bericht weggelassen werden sollen. Standardwert: `false`.|  
|`SimplePageHeade`rs|Gibt an, ob der Seitenkopf des Berichts in den Excel-Seitenkopf gerendert wird. Der Wert `false` gibt an, dass der Seitenkopf in die erste Zeile des Arbeitsblatts gerendert wird. Standardwert: `false`.|  
  
## <a name="see-also"></a>Weitere Informationen  
 <xref:ReportExecution2005.ReportExecutionService.Render%2A>   
 [Übergeben von Geräte Informationseinstellungen an Renderingerweiterungen](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md)   
 [Anpassen von Renderingerweiterungsparametern in RSReportServer.Config](customize-rendering-extension-parameters-in-rsreportserver-config.md)   
 [Technische Referenz (SSRS)](../../2014/reporting-services/technical-reference-ssrs.md)  
  
  
