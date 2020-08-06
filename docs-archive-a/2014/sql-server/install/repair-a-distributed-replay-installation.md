---
title: Reparieren einer Distributed Replay-Installation | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 6fcd8ca8-1ceb-457d-9545-096c74e274d7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 57f5b2bde308e48dbf14b52a8b159b30f6a98bc8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620143"
---
# <a name="repair-a-distributed-replay-installation"></a>Reparieren einer Distributed Replay-Installation
  Zur Reparatur einer Distributed Replay-Komponente (Controller oder Client) gehen Sie wie folgt vor:  
  
1.  Installieren Sie alle zugehörigen Dateien erneut auf dem Datenträger, und ersetzen Sie dabei alle vorhandenen Dateien.  
  
2.  Wenn das entsprechende Windows-Dienstkonto entfernt wurde, erstellen Sie dieses erneut.  
  
 Über den Reparaturvorgang können Sie Komponenten nicht hinzuzufügen oder entfernen. Um Komponenten hinzuzufügen oder zu entfernen, aktivieren oder deaktivieren Sie die entsprechende Komponente in der Funktionsstruktur auf der Seite **Funktionsauswahl** in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup.  
  
### <a name="to-repair-a-failed-installation-of-distributed-replay"></a>So reparieren Sie eine fehlerhafte Distributed Replay-Installation  
  
1.  Klicken Sie im **Startmenü** auf **Systemsteuerung**, und doppelklicken Sie dann auf **Software.**  
  
2.  Wählen Sie [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] im Fenster **Programm deinstallieren oder ändern** aus, und [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Klicken Sie dann im Dialogfeld auf **Reparieren**.  
  
3.  Führen Sie die Schritte im [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Assistenten aus, und wählen Sie auf der Seite **Features auswählen** die Distributed Replay Komponenten aus, die Sie reparieren möchten, und klicken Sie dann auf **Weiter.**  
  
4.  Schließen Sie den [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]-Installations-Assistenten ab, um die ausgewählten Distributed Replay-Funktionen zu reparieren.  
  
  
