---
title: Editor für den Task ' Webdienst ' (Seite Ausgabe) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.webservicestask.output.f1
helpviewer_keywords:
- Web Service Task Editor
ms.assetid: 73c83969-7b0e-479d-a436-0a46b2068d01
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6ad034ae78a096ebe5998ac2c3d2573fe7c3bfd4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621563"
---
# <a name="web-service-task-editor-output-page"></a>Editor für den Task 'Webdienst' (Seite Ausgabe)
  Verwenden Sie die Seite **Ausgabe** des Dialogfelds **Editor für den Task 'Webdienst'** , um anzugeben, wo das durch die Webmethode zurückgegebene Ergebnis gespeichert werden soll.  
  
 Weitere Informationen zu diesem Task finden Sie unter [Webdienst (Task)](control-flow/web-service-task.md).  
  
## <a name="static-options"></a>Statische Optionen  
 **OutputType**  
 Wählt den Speichertyp, der beim Speichern der Ergebnisse verwendet werden soll. Diese Eigenschaft besitzt die in der folgenden Tabelle aufgeführten Optionen.  
  
|Wert|BESCHREIBUNG|  
|-----------|-----------------|  
|**File Connection**|Speichert die Ergebnisse in einer Datei. Wenn Sie diesen Wert auswählen, wird die dynamische Option **Datei**angezeigt.|  
|**Variable**|Speichert die Ergebnisse in einer Variablen. Wenn Sie diesen Wert auswählen, wird die dynamische Option **Variable**angezeigt.|  
  
## <a name="outputtype-dynamic-options"></a>OutputType (dynamische Optionen)  
  
### <a name="outputtype--file-connection"></a>OutputType = File Connection  
 **File**  
 Wählen Sie einen Dateiverbindungs-Manager aus der Liste aus, oder klicken Sie auf \<**New Connection...**>, um einen neuen Verbindungs-Manager zu erstellen.  
  
 **Verwandte Themen:** [Dateiverbindungs-Manager](connection-manager/file-connection-manager.md), [Dateiverbindungs-Manager-Editor](../../2014/integration-services/file-connection-manager-editor.md)  
  
### <a name="outputtype--variable"></a>OutputType = Variable  
 **Variable**  
 Wählen Sie eine Variable aus der Liste aus, oder klicken Sie auf \<**New Variable...**>, um eine neue Variable zu erstellen.  
  
 **Verwandte Themen:**  [Integration Services-Variablen &#40;SSIS&#41;](integration-services-ssis-variables.md), [Hinzufügen von Variablen](../../2014/integration-services/add-variable.md)  
  
## <a name="see-also"></a>Weitere Informationen  
 [Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md)   
 [Editor für den Task ' Webdienst ' &#40;Seite Allgemein&#41;](general-page-of-integration-services-designers-options.md)   
 [Editor für den Task ' Webdienst ' &#40;Eingabe Seite&#41;](../../2014/integration-services/web-service-task-editor-input-page.md)   
 [Seite Ausdrücke](expressions/expressions-page.md)  
  
  
