---
title: SQL Server, SQL Errors-Objekt | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- SQL Errors object
- SQLServer:SQL Errors
ms.assetid: 6e5273ca-29cb-4618-88a2-70b9b8d6cf76
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 11bfb728e79b4fc175fb8a2fe16c9f1662a205ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696757"
---
# <a name="sql-server-sql-errors-object"></a>SQL Server, SQL-Fehler-Objekt
  Durch das Objekt **SQLServer:SQL Errors** in Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] werden Indikatoren zum Überwachen von **SQL-Fehlern**zur Verfügung gestellt.  
  
 Diese Tabelle enthält eine Beschreibung der **SQL Errors**-Zähler in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
|Leistungsindikatoren von SQL-Fehler bei SQL Server|BESCHREIBUNG|  
|------------------------------------|-----------------|  
|**Fehler/Sekunde**|Anzahl der Fehler/Sekunde.|  
  
 Jeder Leistungsindikator in dem Objekt enthält die folgenden Instanzen:  
  
|Element|Definition|  
|----------|----------------|  
|**_Total**|Informationen zu allen Fehlern.|  
|**DB Offline Errors**|Es werden schwere Fehler nachverfolgt, die dazu führen, dass [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] die Datenbank offline schaltet.|  
|**Info Errors**|Informationen, die sich auf Fehlermeldungen beziehen, die den Benutzern als Informationen zur Verfügung gestellt werden, verursachen jedoch keine Fehler.|  
|**Kill Connection Errors**|Es werden schwere Fehler nachverfolgt, die dazu führen, dass [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] die aktuelle Verbindung unterbricht.|  
|**User Errors**|Informationen zu Benutzerfehlern.|  
  
## <a name="see-also"></a>Weitere Informationen  
 [Überwachen der Ressourcenverwendung &#40;Systemmonitor&#41;](monitor-resource-usage-system-monitor.md)  
  
  
