---
title: Installations Regeln | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- SCC
- System Configuration Check, Setup
helpviewer_keywords:
- System Configuration Check page [SQL Server Installation Wizard]
- SQL Server Installation Wizard, System Configuration Check page
- SCC [SQL Server]
ms.assetid: 168c0445-5651-42fc-91f4-d9f27d9e2281
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: b3d9fe413174613cadc9277e5c7f21695a4021c2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722282"
---
# <a name="install-rules"></a>Installationsregeln
  Das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Setup überprüft die Computerkonfiguration, bevor der Setupvorgang abgeschlossen wird. Während des Setups von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] durchsucht die Systemkonfigurationsprüfung (System Configuration Checker, SCC) den Computer, auf dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installiert werden soll. SCC sucht nach Bedingungen, die ein erfolgreiches Setup von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] verhindern. Bevor Setup den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Installations-Assistenten startet, ruft SCC den Status jedes Elements ab. SCC vergleicht dann das Ergebnis mit den erforderlichen Bedingungen und gibt Anweisungen zum Entfernen der Blockierungsprobleme.  
  
 Die Systemkonfigurationsprüfung generiert einen Bericht, der eine kurze Beschreibung für jede ausgeführte Regel sowie den Ausführungsstatus enthält. Der Bericht der Systemkonfigurations Prüfung befindet sich unter% Program Files% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\setup Bootstrap\LOG \\<YYYYMMDD_HHMM>\\ .  
  
 Bevor Sie Setup ausführen, lesen Sie die folgenden Themen:  
  
1.  [Hardware- und Softwareanforderungen für die Installation von SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md)  
  
2.  [Von den Editionen von SQL Server 2014 unterstützte Features](../../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md)  
  
3.  [Überlegungen zur Sicherheit bei SQL Server-Installationen](../../../2014/sql-server/install/security-considerations-for-a-sql-server-installation.md)  
  
4.  [Lokale Sprachversionen in SQL Server](../../../2014/sql-server/install/local-language-versions-in-sql-server.md)  
  
 Weitere Referenzen:  
  
1.  [Unterstützte Versions- und Editionsupgrades](../../database-engine/install-windows/supported-version-and-edition-upgrades.md)  
  
2.  [Vor dem Installieren des Failoverclusterings](../failover-clusters/install/before-installing-failover-clustering.md)  
  
## <a name="additional-rule-topics"></a>Weitere Themen zu Regeln  
 Szenariospezifische Setupregeln finden Sie in den folgenden Themen:  
  
-   [Installation Rules](../../../2014/sql-server/install/installation-rules.md)  
  
-   [Funktions Regeln &#40;Upgrade&#41;](../../../2014/sql-server/install/feature-rules-upgrade.md)  
  
-   [Upgraderegeln für Editionen](../../../2014/sql-server/install/edition-upgrade-rules.md)  
  
-   [Deinstallationsregeln](../../../2014/sql-server/install/uninstallation-rules.md)  
  
-   [Regeln zum Vorbereiten des Images](../../../2014/sql-server/install/prepare-image-rules.md)  
  
-   [Regeln zum Abschließen des Images](../../../2014/sql-server/install/complete-image-rules.md)  
  
  
