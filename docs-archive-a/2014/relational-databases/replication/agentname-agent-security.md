---
title: '&lt;AgentName&gt;-Agent-Sicherheit | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newsubwizard.agentnameagentsecurity.f1
ms.assetid: d34c7ef8-cf77-4ffd-887f-3c4214dfd71e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: fc72d4380b4d1980da30b8445596e1919a859e31
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622597"
---
# <a name="ltagentnamegt-agent-security"></a>&lt;AgentName&gt;-Agent-Sicherheit
  Auf der Seite **\<AgentName>-Agent-Sicherheit** können Sie die Konten angeben, für die der Verteilungs-Agent (bei Transaktions- oder Momentaufnahmereplikation) oder der Merge-Agent (bei Mergereplikation) Verbindungen mit den Computern einer Replikationstopologie herstellt und ausführt. Informationen zu erforderlichen Berechtigungen für Agents und bewährten Methoden für die Replikationssicherheit finden Sie unter [Sicherheitsmodell des Replikations-Agent](security/replication-agent-security-model.md) und [Replikationssicherheit, bewährte Methoden](security/replication-security-best-practices.md).  
  
## <a name="options"></a>Tastatur  
 Klicken Sie in der Zeile jedes Abonnenten auf die Eigenschaftenschaltfläche (die Schaltfläche mit den **drei Punkten**), um eines der beiden Dialogfelder, **Sicherheit für den Verteilungs-Agent** oder **Sicherheit für den Merge-Agent**, zu öffnen. Klicken Sie in dem geöffneten Dialogfeld auf **Hilfe** , um weitere Informationen zu den Berechtigungen zu erhalten, die für die von den Agents verwendeten Konten erforderlich sind.  
  
 Wenn Sie die Einstellungen in einem der beiden Dialogfelder eingegeben haben, werden im Raster die Verbindungsinformationen zu dem Abonnenten angezeigt.  
  
 **Agent für Abonnent**  
 Die Namen aller Abonnenten.  
  
 **Verbindung mit Verteiler**  
 Wird bei der Transaktions- und Momentaufnahmereplikation angezeigt. Der Kontext, unter dem die Verbindung mit dem Verteiler hergestellt wird. Lokale Verbindungen werden immer unter dem Kontext des [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows-Kontos hergestellt, das zum Ausführen der Agents verwendet wird:  
  
-   Bei Pushabonnements ist die lokale Verbindung diejenige mit dem Verteiler. Daher wird in diesem Feld immer Folgendes angezeigt: **Identität annehmen '\<Domain>\\<Anmeldename\>'** oder **Identität annehmen '\<Computer>\\<Anmeldename\>'** für Pushabonnements  
  
-   Bei Pullabonnements kann die Verbindung auch unter dem Kontext einer [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Anmeldung hergestellt werden. In dem Feld wird eine der folgenden Optionen angezeigt: **Anmeldenamen '\<Login>' verwenden**, **Identität annehmen '\<Domain>\\<Anmeldename\>'** oder **Identität annehmen '\<Computer>\\<Anmeldename\>'** [!INCLUDE[msCoName](../../includes/msconame-md.md)] empfiehlt, alle Verbindungen unter dem Kontext des Windows-Kontos herzustellen.  
  
 **Verbindung mit Verleger &Verteiler**  
 Wird bei Mergereplikation angezeigt. Der Kontext, unter dem die Verbindung mit dem Verleger und Verteiler hergestellt wird. Lokale Verbindungen werden immer unter dem Kontext des Windows-Kontos hergestellt, das zum Ausführen der Agents verwendet wird.  
  
-   Bei Pushabonnements ist die lokale Verbindung diejenige mit dem Verleger und Verteiler. Daher wird in diesem Feld immer Folgendes angezeigt: **Identität annehmen '\<Domain>\\<Anmeldename\>'** oder **Identität annehmen '\<Computer>\\<Anmeldename\>'** für Pushabonnements  
  
-   Bei Pullabonnements kann die Verbindung auch unter dem Kontext einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Anmeldung hergestellt werden. In dem Feld wird eine der folgenden Optionen angezeigt: **Anmeldenamen '\<Login>' verwenden**, **Identität annehmen '\<Domain>\\<Anmeldename\>'** oder **Identität annehmen '\<Computer>\\<Anmeldename\>'** [!INCLUDE[msCoName](../../includes/msconame-md.md)] empfiehlt, alle Verbindungen unter dem Kontext des Windows-Kontos herzustellen.  
  
 **Verbindung mit Abonnent**  
 Der Kontext, unter dem die Verbindung mit dem Abonnenten hergestellt wird. Lokale Verbindungen werden immer unter dem Kontext des Windows-Kontos hergestellt, das zum Ausführen der Agents verwendet wird.  
  
-   Bei Pullabonnements ist die lokale Verbindung diejenige mit dem Abonnenten. Daher wird in diesem Feld immer Folgendes angezeigt: **Identität annehmen '\<Domain>\\<Anmeldename\>'** oder **Identität annehmen '\<Computer>\\<Anmeldename\>'** für Pushabonnements  
  
-   Bei Pushabonnements kann die Verbindung auch unter dem Kontext einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Anmeldung hergestellt werden. In dem Feld wird eine der folgenden Optionen angezeigt: **Anmeldenamen '\<Login>' verwenden**, **Identität annehmen '\<Domain>\\<Anmeldename\>'** oder **Identität annehmen '\<Computer>\\<Anmeldename\>'** [!INCLUDE[msCoName](../../includes/msconame-md.md)] empfiehlt, alle Verbindungen unter dem Kontext des Windows-Kontos herzustellen.  
  
## <a name="see-also"></a>Weitere Informationen  
 [Anzeigen und Ändern der Eigenschaften von Pullabonnements](view-and-modify-pull-subscription-properties.md)   
 [Anzeigen und Ändern der Eigenschaften von Pushabonnements](view-and-modify-push-subscription-properties.md)   
 [Verwalten von Anmeldeinformationen und Kennwörtern bei der Replikation](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication)   
 [Sicherheitsmodell des Replikations-Agents](security/replication-agent-security-model.md)   
 [SQL Server-Replikation Sicherheit](security/view-and-modify-replication-security-settings.md)  
  
  
