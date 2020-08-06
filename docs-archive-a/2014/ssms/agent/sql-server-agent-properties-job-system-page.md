---
title: Eigenschaften des SQL Server-Agents (Registerkarte Auftragssystem)|Microsoft-Dokumente
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.agent.job.f1
ms.assetid: e171d13e-1302-4f0e-88be-67d656aec8d3
author: stevestein
ms.author: sstein
ms.openlocfilehash: 743a8d558e97e9ad83cfc66e9ef1adf2e1bc0c2b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621304"
---
# <a name="sql-server-agent-properties-job-system-page"></a>Eigenschaften des SQL Server-Agents (Registerkarte Auftragssystem)
  Mithilfe dieser Seite können Sie anzeigen und ändern, wie Aufträge vom- [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent-Dienst verwaltet werden.  
  
## <a name="options"></a>Tastatur  
 **Timeoutintervall beim Herunterfahren (in Sekunden)**  
 Gibt an, wie viele Sekunden der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent vor dem Herunterfahren auf den Abschluss von Aufträgen abwartet. Wenn der Auftrag noch nach dem angegebenen Intervall ausgeführt wird, wird das Beenden des Auftrags vom [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent erzwungen.  
  
 **Nichtadministrator-Proxykonto verwenden**  
 Legt ein Nichtadministrator-Proxykonto für den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent fest. [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]und höhere Versionen unterstützen mehrere Proxys. Daher ist diese Option nur bei der Verwaltung [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] von verfügbar. Agent-Versionen vor [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] .  
  
 **Benutzername**  
 Geben Sie den Namen des Benutzers für das Nichtadministrator-Proxykonto ein. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] unterstützt mehrere Proxys. Diese Option betrifft daher nur die Verwaltung von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Versionen vor [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].  
  
 **Kennwort**  
 Geben Sie das Kennwort des Benutzers für das Nichtadministrator-Proxykonto ein. [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] und höhere Versionen unterstützen mehrere Proxys. Diese Option betrifft daher nur die Verwaltung von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Versionen vor [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].  
  
 **Domäne**  
 Geben Sie die Domäne des Benutzers für das Nichtadministrator-Proxykonto ein. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] unterstützt mehrere Proxys. Diese Option betrifft daher nur die Verwaltung von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Versionen vor [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].  
  
## <a name="see-also"></a>Weitere Informationen  
 [Implementieren von Aufträgen](implement-jobs.md)  
  
  
