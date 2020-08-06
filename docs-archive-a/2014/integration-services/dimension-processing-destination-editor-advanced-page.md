---
title: Ziel-Editor für Dimensions Verarbeitung (Seite erweitert) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dimprocessingtransformation.advanced.f1
helpviewer_keywords:
- Dimension Processing Destination Editor
ms.assetid: 2b30835a-2680-4d98-89a4-4f17e29e3818
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5be80cbbfb6871594d7481ccc0f9444d014885e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621601"
---
# <a name="dimension-processing-destination-editor-advanced-page"></a>Ziel-Editor für Dimensionsverarbeitung (Seite Erweitert)
  Verwenden Sie zum Konfigurieren der Fehlerbehandlung die Seite **Erweitert** im Dialogfeld **Ziel-Editor für Dimensionsverarbeitung** .  
  
 Weitere Informationen zum Ziel für Dimensionsverarbeitung finden Sie unter [Dimension Processing Destination](data-flow/dimension-processing-destination.md).  
  
## <a name="options"></a>Tastatur  
 **Standardfehlerkonfiguration verwenden**  
 Gibt an, ob die Standardfehlerbehandlung von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] verwendet werden soll. Standardmäßig ist dieser Wert auf `True` festgelegt.  
  
 **Schlüsselfehler Aktion**  
 Gibt an, wie Datensätze behandelt werden, die unzulässige Schlüsselwerte aufweisen.  
  
|Wert|BESCHREIBUNG|  
|-----------|-----------------|  
|**ConvertToUnknown**|Konvertiert den unzulässigen Schlüsselwert in den Wert `UnknownMember`.|  
|**DiscardRecord**|Verwirft den Datensatz.|  
  
 **Fehler ignorieren**  
 Gibt an, dass Fehler ignoriert werden sollen.  
  
 **Bei Fehler abbrechen**  
 Gibt an, dass die Verarbeitung beendet werden soll, wenn ein Fehler auftritt.  
  
 **Anzahl von Fehlern**  
 Gibt den Grenzwert für die Anzahl der Fehler an, bei dem die Verarbeitung beendet werden soll, wenn Sie **Bei Fehler beenden**ausgewählt haben.  
  
 **Aktion bei Fehler**  
 Gibt die Aktion an, die bei Erreichen des Fehlergrenzwertes ausgeführt wird, wenn Sie **Bei Fehler beenden**ausgewählt haben.  
  
|Wert|BESCHREIBUNG|  
|-----------|-----------------|  
|**StopProcessing**|Beendet die Verarbeitung.|  
|**StopLogging**|Beendet das Protokollieren der Fehler.|  
  
 **Schlüssel nicht gefunden**  
 Gibt die Aktion an, die beim Fehler Schlüssel nicht gefunden ausgeführt werden soll. Standardmäßig ist dieser Wert **ReportAndContinue**.  
  
|Wert|BESCHREIBUNG|  
|-----------|-----------------|  
|**IgnoreError**|Ignoriert den Fehler, und setzt die Verarbeitung fort.|  
|**ReportAndContinue**|Berichtet den Fehler, und setzt die Verarbeitung fort.|  
|**ReportAndStop**|Berichtet den Fehler, und beendet die Verarbeitung.|  
  
 **Doppelter Schlüssel**  
 Gibt die Aktion an, die beim Fehler Doppelter Schlüssel ausgeführt werden soll. Standardmäßig ist dieser Wert **IgnoreError**.  
  
|Wert|BESCHREIBUNG|  
|-----------|-----------------|  
|**IgnoreError**|Ignoriert den Fehler, und setzt die Verarbeitung fort.|  
|**ReportAndContinue**|Berichtet den Fehler, und setzt die Verarbeitung fort.|  
|**ReportAndStop**|Berichtet den Fehler, und beendet die Verarbeitung.|  
  
 **NULL-Schlüssel in unbekanntes konvertiert**  
 Gibt die Aktion an, die ausgeführt werden soll, wenn ein NULL-Schlüssel in den Wert `UnknownMember` konvertiert wurde. Standardmäßig ist dieser Wert **IgnoreError**.  
  
|Wert|BESCHREIBUNG|  
|-----------|-----------------|  
|**IgnoreError**|Ignoriert den Fehler, und setzt die Verarbeitung fort.|  
|**ReportAndContinue**|Berichtet den Fehler, und setzt die Verarbeitung fort.|  
|**ReportAndStop**|Berichtet den Fehler, und beendet die Verarbeitung.|  
  
 **NULL-Schlüssel nicht zulässig**  
 Gibt die Aktion an, die ausgeführt wird, wenn NULL-Schlüssel unzulässig sind und ein NULL-Schlüssel entdeckt wurde. Standardmäßig ist dieser Wert **ReportAndContinue**.  
  
|Wert|BESCHREIBUNG|  
|-----------|-----------------|  
|**IgnoreError**|Ignoriert den Fehler, und setzt die Verarbeitung fort.|  
|**ReportAndContinue**|Berichtet den Fehler, und setzt die Verarbeitung fort.|  
|**ReportAndStop**|Berichtet den Fehler, und beendet die Verarbeitung.|  
  
 **Fehlerprotokollpfad**  
 Geben Sie den Pfad für das Fehlerprotokoll ein, oder klicken Sie auf die Schaltfläche zum **Durchsuchen (...)** , um ein Ziel auszuwählen.  
  
 **Durchsuchen (…)**  
 Wählen Sie einen Pfad für das Fehlerprotokoll aus.  
  
## <a name="see-also"></a>Weitere Informationen  
 [Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md)   
 [Ziel-Editor für Dimensions Verarbeitung &#40;Seite Verbindungs-Manager&#41;](../../2014/integration-services/dimension-processing-destination-editor-connection-manager-page.md)   
 [Ziel-Editor für Dimensionsverarbeitung &#40;Seite Zuordnungen&#41;](../../2014/integration-services/dimension-processing-destination-editor-mappings-page.md)  
  
  
