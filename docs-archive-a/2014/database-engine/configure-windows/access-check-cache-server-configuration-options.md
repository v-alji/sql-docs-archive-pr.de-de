---
title: Serverkonfigurationsoptionen für den Zugriffsüberprüfungscache | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- access check cache option
- access check cache bucket count
- access check cache quota
ms.assetid: 0a992ea8-3ec6-4a4d-97b5-460ae7326247
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: feed895eeb7b11b4c41c51c4c26859a1057d2733
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607988"
---
# <a name="access-check-cache-server-configuration-options"></a>Serverkonfigurationsoptionen für den Zugriffsüberprüfungscache
Beim Zugriff auf Datenbankobjekte durch [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]wird die Zugriffsprüfung in einer internen Struktur zwischengespeichert, die als **access check result cache**bezeichnet wird. 
  
Die Option **access check cache bucket count** steuert die Anzahl der Hashbuckets, die für den Ergebniscache der Zugriffsüberprüfung verwendet werden. 

Die Option **access check cache quota** steuert die Anzahl der Einträge, die im Ergebniscache der Zugriffsüberprüfung gespeichert werden. Wenn die maximale Anzahl von Einträgen erreicht ist, werden die ältesten Einträge aus dem Ergebniscache der Zugriffsüberprüfung entfernt.
  
Die Standardwerte 0 geben an, dass [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] diese Optionen verwaltet. Von [!INCLUDE[ssKatmai](../../includes/ssKatmai-md.md)] bis [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] werden die Standardwerte in die folgenden internen Konfigurationen übersetzt:
-   Bei der Bucketanzahl für den Zugriffs Check Cache legt der Wert 0 einen Standardwert von 256-Bucket für die x86-Architektur und 2.048-Bucket für x64-und IA-64-Architekturen fest.
-   Bei der Zugriffs Überprüfung des Cache Kontingents legt der Wert 0 einen Standardwert von 1.024 Einträge für die x86-Architektur und 28.192.048-Bucket für x64-und IA-64-Architekturen fest.

In seltenen Fällen kann die Leistung durch das Ändern dieser Optionen verbessert werden. Beispielsweise können Sie den Ergebniscache für die Zugriffsüberprüfung verkleinern, wenn zu viel Arbeitsspeicher verwendet wird. Sie können den Ergebniscache für die Zugriffsüberprüfung auch vergrößern, wenn Sie bei der Neuberechnung von Berechtigungen eine hohe CPU-Auslastung feststellen.

> [!IMPORTANT]
> Microsoft empfiehlt, diese Optionen nur auf Anweisung des Microsoft-Kundendiensts zu ändern.
  
## <a name="see-also"></a>Weitere Informationen  
 [Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md)   
 [sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
