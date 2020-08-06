---
title: Editor für den FTP-Task (Seite Dateiübertragung) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.ftptask.filetransfer.f1
helpviewer_keywords:
- File Transfer Protocol Task Editor
ms.assetid: 37e52220-feb2-474c-ad88-fa1b1059acd4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8094051e93c4165be6ae186bde394f9271d60669
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615446"
---
# <a name="ftp-task-editor-file-transfer-page"></a>Editor für den FTP-Task (Seite Dateiübertragung)
  Mithilfe der Seite **Dateiübertragung** des Dialogfelds **Editor für den FTP-Task** können Sie den FTP-Vorgang konfigurieren, der durch den Task ausgeführt wird.  
  
 Informationen zu diesem Task finden Sie unter [FTP-Task](control-flow/ftp-task.md).  
  
## <a name="options"></a>Tastatur  
 **IsRemotePathVariable**  
 Geben Sie an, ob der Remotepfad in einer Variablen gespeichert ist. Diese Eigenschaft besitzt die in der folgenden Tabelle aufgeführten Optionen.  
  
|Wert|BESCHREIBUNG|  
|-----------|-----------------|  
|**Wahr**|Der Zielpfad ist in einer Variablen gespeichert. Wenn Sie diesen Wert auswählen, wird die dynamische Option **RemoteVariable**angezeigt.|  
|**False**|Der Zielpfad wird in einem Dateiverbindungs-Manager angegeben. Wenn Sie diesen Wert auswählen, wird die dynamische Option **RemotePath**angezeigt.|  
  
 **OverwriteFileAtDestination**  
 Geben Sie an, ob eine Datei am Ziel überschrieben werden kann.  
  
 **IsLocalPathVariable**  
 Geben Sie an, ob der lokale Pfad in einer Variablen gespeichert ist. Diese Eigenschaft besitzt die in der folgenden Tabelle aufgeführten Optionen.  
  
|Wert|BESCHREIBUNG|  
|-----------|-----------------|  
|**Wahr**|Der Zielpfad ist in einer Variablen gespeichert. Wenn Sie diesen Wert auswählen, wird die dynamische Option **LocalVariable**angezeigt.|  
|**False**|Der Zielpfad wird in einem Dateiverbindungs-Manager angegeben. Wenn Sie diesen Wert auswählen, wird die dynamische Option **LocalPath**angezeigt.|  
  
 **Vorgang**  
 Wählen Sie den auszuführenden FTP-Vorgang aus. Diese Eigenschaft besitzt die in der folgenden Tabelle aufgeführten Optionen.  
  
|Wert|BESCHREIBUNG|  
|-----------|-----------------|  
|**Dateien senden**|Senden Sie Dateien. Wenn Sie diesen Wert auswählen, werden die dynamischen Optionen **LocalVariable**, **LocalPathRemoteVariable** und **RemotePath**angezeigt.|  
|**Dateien empfangen**|Empfangen Sie Dateien. Wenn Sie diesen Wert auswählen, werden die dynamischen Optionen **LocalVariable**, **LocalPathRemoteVariable** und **RemotePath**angezeigt.|  
|**Lokales Verzeichnis erstellen**|Erstellen Sie ein lokales Verzeichnis. Wenn Sie diesen Wert auswählen, werden die dynamischen Optionen **LocalVariable** und **LocalPath**angezeigt.|  
|**Remoteverzeichnis erstellen**|Erstellen Sie ein Remoteverzeichnis. Wenn Sie diesen Wert auswählen, werden die dynamischen Optionen **RemoteVariable** und **RemotePath**angezeigt.|  
|**Lokales Verzeichnis entfernen**|Entfernen Sie ein lokales Verzeichnis. Wenn Sie diesen Wert auswählen, werden die dynamischen Optionen **LocalVariable** und **LocalPath**angezeigt.|  
|**Remoteverzeichnis entfernen**|Entfernen Sie ein Remoteverzeichnis. Wenn Sie diesen Wert auswählen, werden die dynamischen Optionen **RemoteVariable** und **RemotePath**angezeigt.|  
|**Lokale Dateien löschen**|Löschen Sie lokale Dateien. Wenn Sie diesen Wert auswählen, werden die dynamischen Optionen **LocalVariable** und **LocalPath**angezeigt.|  
|**Remotedateien löschen**|Löschen Sie Remotedateien. Wenn Sie diesen Wert auswählen, werden die dynamischen Optionen **RemoteVariable** und **RemotePath**angezeigt.|  
  
 **IsTransferASCII**  
 Geben Sie an, ob die auf und von einem Remote-FTP-Server übertragenen Dateien im ASCII-Modus übertragen werden sollen.  
  
## <a name="isremotepathvariable-dynamic-options"></a>IsRemotePathVariable (dynamische Optionen)  
  
### <a name="isremotepathvariable--true"></a>IsRemotePathVariable = True  
 **RemoteVariable**  
 Wählen Sie eine vorhandene benutzerdefinierte Variable aus, oder klicken Sie auf \<**New variable...**>, um eine benutzerdefinierte Variable zu erstellen.  
  
 **Verwandte Themen:** [Integration Services-Variablen &#40;SSIS&#41;](integration-services-ssis-variables.md), Hinzufügen von Variablen  
  
### <a name="isremotepathvariable--false"></a>IsRemotePathVariable = False  
 **RemotePath**  
 Wählen Sie einen vorhandenen FTP-Verbindungs-Manager aus, oder klicken Sie auf \<**New connection...**>, um einen Verbindungs-Manager zu erstellen.  
  
 **Verwandte Themen:** [FTP-Verbindungs-Manager](connection-manager/ftp-connection-manager.md), [FTP-Verbindungs-Manager-Editor](../../2014/integration-services/ftp-connection-manager-editor.md)  
  
## <a name="islocalpathvariable-dynamic-options"></a>IsLocalPathVariable (dynamische Optionen)  
  
### <a name="islocalpathvariable--true"></a>IsLocalPathVariable = True  
 **LocalVariable**  
 Wählen Sie eine vorhandene benutzerdefinierte Variable aus, oder klicken Sie auf \<**New variable...**>, um eine Variable zu erstellen.  
  
 **Verwandte Themen:** [Integration Services-Variablen &#40;SSIS&#41;](integration-services-ssis-variables.md), Hinzufügen von Variablen  
  
### <a name="islocalpathvariable--false"></a>IsLocalPathVariable = False  
 **LocalPath**  
 Wählen Sie einen vorhandenen Dateiverbindungs-Manager aus, oder klicken Sie auf \<**New connection...**>, um einen Verbindungs-Manager zu erstellen.  
  
 **Verwandte Themen:**[Flat File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)  
  
## <a name="see-also"></a>Weitere Informationen  
 [Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md)   
 [Editor für den FTP-Task &#40;Seite "Allgemein"&#41;](general-page-of-integration-services-designers-options.md)   
 [Seite Ausdrücke](expressions/expressions-page.md)  
  
  
