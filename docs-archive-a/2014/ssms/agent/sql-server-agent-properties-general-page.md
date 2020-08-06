---
title: SQL Server-Agent-Eigenschaften (Seite Allgemein)|Microsoft-Dokumente
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.agent.general.f1
ms.assetid: b51601e9-5454-43c6-bb5e-24eb2ff043c8
author: stevestein
ms.author: sstein
ms.openlocfilehash: a67d5431be4025c18b11d6791b016fa83e957810
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621307"
---
# <a name="sql-server-agent-properties-general-page"></a>SQL Server-Agent-Eigenschaften (Seite Allgemein)
  Verwenden Sie diese Seite, um die allgemeinen Eigenschaften des- [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent-Dienstanbieter anzuzeigen und zu ändern.  
  
## <a name="options"></a>Tastatur  
 **Dienstzustand**  
 Zeigt den aktuellen Status des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Dienstes an.  
  
 **SQL Server nach unerwartetem Beenden automatisch neu starten**  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent startet [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] neu, wenn [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] unerwartet beendet wird.  
  
 **SQL Server-Agent nach unerwartetem Beenden automatisch neu starten**  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] startet [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent neu, wenn [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent unerwartet beendet wird.  
  
 **Filename**  
 Geben Sie den Dateinamen für das Fehlerprotokoll an.  
  
 **...**  
 Mit dieser Schaltfläche können Sie nach der Fehlerprotokolldatei suchen.  
  
 **Meldungen zur Ablaufverfolgung einschließen**  
 Meldungen zur Ablaufverfolgung werden in das Fehlerprotokoll eingeschlossen. Meldungen zur Ablaufverfolgung stellen detaillierte Informationen zu [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Vorgängen bereit. Deshalb benötigt die Protokolldatei mehr Datenträgerspeicherplatz, wenn diese Option ausgewählt ist. Diese Option sollte nur bei der Behandlung eines Problems ausgewählt werden, bei dem der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent eine Rolle spielt.  
  
 **OEM-Datei schreiben**  
 Speichert die Fehlerprotokolldatei als Nicht-Unicode-Datei. Dadurch wird der für die Protokolldatei erforderliche Datenträgerspeicherplatz reduziert. Meldungen, die Unicode enthalten, können jedoch schwieriger lesbar sein, wenn diese Option aktiviert ist.  
  
 **NET SEND-Empfänger**  
 Geben Sie den Namen eines Operators ein, der NET SEND-Benachrichtigungen von Meldungen empfängt, die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent in die Protokolldatei schreibt.  
  
## <a name="see-also"></a>Weitere Informationen  
 [Veranstalter](operators.md)   
 [SQL Server-Agent-Fehlerprotokoll](sql-server-agent-error-log.md)  
  
  
