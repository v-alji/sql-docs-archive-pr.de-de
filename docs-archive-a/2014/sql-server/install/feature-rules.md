---
title: Funktions Regeln | Microsoft-Dokumentation
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: f75541cb-f78d-4303-a641-d5d3d58ae1fa
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 5b0906e2f2c95a42849b6a69e60d5f26153d3a6e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697414"
---
# <a name="feature-rules"></a>Funktionsregeln
  Das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Setup überprüft die Computerkonfiguration, bevor der Setupvorgang abgeschlossen wird. Während des Setups von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] durchsucht die Systemkonfigurationsprüfung (System Configuration Checker, SCC) den Computer, auf dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installiert werden soll. SCC sucht nach Bedingungen, die ein erfolgreiches Setup von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] verhindern. Bevor Setup gestartet wird, ruft SCC den Status jedes Elements ab. SCC vergleicht dann das Ergebnis mit den erforderlichen Bedingungen und gibt Anweisungen zum Entfernen der Blockierungsprobleme.  
  
 Die Systemkonfigurationsprüfung generiert einen Bericht, der eine kurze Beschreibung für jede ausgeführte Regel sowie den Ausführungsstatus enthält. Der Bericht der Systemkonfigurations Prüfung befindet sich unter% Program Files% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\setup Bootstrap\LOG \\<YYYYMMDD_HHMM>\\ .  
  
 Bevor Sie Setup ausführen, lesen Sie die folgenden Themen:  
  
1.  [Hardware- und Softwareanforderungen für die Installation von SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md)  
  
2.  [Von den Editionen von SQL Server 2014 unterstützte Features](../../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md)  
  
3.  [Überlegungen zur Sicherheit bei SQL Server-Installationen](../../../2014/sql-server/install/security-considerations-for-a-sql-server-installation.md)  
  
4.  [Lokale Sprachversionen in SQL Server](../../../2014/sql-server/install/local-language-versions-in-sql-server.md)  
  
 Weitere Referenzen:  
  
1.  [Unterstützte Versions- und Editionsupgrades](../../database-engine/install-windows/supported-version-and-edition-upgrades.md)  
  
2.  [Vor dem Installieren des Failoverclusterings](../failover-clusters/install/before-installing-failover-clustering.md)  
  
  
