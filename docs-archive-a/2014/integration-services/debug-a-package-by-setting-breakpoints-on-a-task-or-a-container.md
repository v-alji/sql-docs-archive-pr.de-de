---
title: Debuggen eines Pakets durch Festlegen von Breakpoints für einen Task oder Container | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- containers [Integration Services], breakpoints
- breakpoints [Integration Services]
- tasks [Integration Services], breakpoints
ms.assetid: e7fa106a-2221-403a-bb74-efc9f12bb450
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 21e334faff95e63e59bbf9c40fdf7e479de949da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609967"
---
# <a name="debug-a-package-by-setting-breakpoints-on-a-task-or-a-container"></a>Debuggen eines Pakets durch Festlegen von Breakpoints auf einem Task oder Container
  In diesem Verfahren wird beschrieben, wie in einem Paket, Task, For-Schleifencontainer, Foreach-Schleifencontainer oder einem Sequenzcontainer Breakpoints festgelegt werden.  
  
### <a name="to-set-breakpoints-in-a-package-a-task-or-a-container"></a>So legen Sie Breakpoints in einem Paket, einem Task oder einem Container fest  
  
1.  Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] das [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]-Projekt mit dem gewünschten Paket.  
  
2.  Doppelklicken Sie auf das Paket, in dem Sie Breakpoints festlegen möchten.  
  
3.  Gehen Sie im SSIS-Designer wie folgt vor:  
  
    -   Um Breakpoints im Paketobjekt festzulegen, klicken Sie auf die Registerkarte **Ablaufsteuerung,** setzen den Cursor an eine beliebige Stelle im Hintergrund der Entwurfsoberfläche, klicken mit der rechten Maustaste und wählen dann **Breakpoints bearbeiten**aus.  
  
    -   Um Breakpoints in einer Paketablaufsteuerung festzulegen, klicken Sie auf die Registerkarte **Ablaufsteuerung** , klicken mit der rechten Maustaste auf einen Task, einen For-Schleifencontainer, einen Foreach-Schleifencontainer oder einen Sequenzcontainer und dann auf **Breakpoints bearbeiten**.  
  
    -   Um Breakpoints in einem Ereignishandler festzulegen, klicken Sie auf die Registerkarte **Ereignishandler** , klicken mit der rechten Maustaste auf einen Task, einen For-Schleifencontainer, einen Foreach-Schleifencontainer oder einen Sequenzcontainer und dann auf **Breakpoints bearbeiten**.  
  
4.  Wählen Sie im Dialogfeld **Breakpoints festlegen\<container name>** die zu aktivierenden Breakpoints aus.  
  
5.  Ändern Sie wahlweise den Typ der Trefferanzahl und die Trefferanzahl für jeden Breakpoint.  
  
6.  Klicken Sie im Menü **Datei** auf **Ausgewählte Elemente speichern** , um das aktualisierte Paket zu speichern.  
  
## <a name="see-also"></a>Weitere Informationen  
 [Tools zur Problembehandlung für die Paketentwicklung](troubleshooting/troubleshooting-tools-for-package-development.md)   
 [Debuggen eines Skripts durch Festlegen von Breakpoints in einem Skript Task und einer Skript Komponente](data-flow/transformations/script-component.md)   
 [Codieren und Debuggen des Skript Tasks](control-flow/script-task.md)   
 [Codieren und Debuggen der Skriptkomponente](extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md)  
  
  
