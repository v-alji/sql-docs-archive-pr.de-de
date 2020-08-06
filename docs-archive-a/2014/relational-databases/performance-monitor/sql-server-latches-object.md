---
title: SQL Server, Latches-Objekt | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Latches object
- SQLServer:Latches
ms.assetid: 2393ea1c-2bf3-41c3-9f37-b9761144eeca
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6f49ac00114065e971c0893f9217ab883eb2d7f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609834"
---
# <a name="sql-server-latches-object"></a>SQL Server, Latches-Objekt
  Das **SQLServer:Latches** -Objekt in Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] enthält Leistungsindikatoren zur Überwachung interner [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Ressourcensperren, die als Latches bezeichnet werden. Das Überwachen der Latches für die Ermittlung der Benutzeraktivität und der Ressourcennutzung kann Ihnen dabei helfen, Leistungsengpässe zu erkennen.  
  
 In dieser Tabelle werden die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Leistungsindikatoren **Latches** beschrieben.  
  
|Batches-Leistungsindikatoren von SQL Server|BESCHREIBUNG|  
|---------------------------------|-----------------|  
|**Durchschnittliche Wartezeit für Latch (in Millisekunden)**|Durchschnittliche Latchwartezeit (in Millisekunden) für wartende Latchanforderungen.|  
|**Latchwartezeit/Sekunde**|Anzahl der Latchanforderungen, für die Batches nicht sofort erteilt werden konnten.|  
|**Anzahl der SuperLatches-Objekte**|Anzahl der Batches, die zurzeit SuperLatches-Objekte sind.|  
|**SuperLatches-Heraufstufungen/Sekunde**|Anzahl der SuperLatches-Objekte, die in der letzten Sekunde zu normalen Batches herabgestuft wurden.|  
|**SuperLatches-Höherstufungen/Sekunde**|Anzahl der Batches, die in der letzten Sekunde zu SuperLatches-Objekten heraufgestuft wurden.|  
|**Gesamtwartezeit für Latch (in Millisekunden)**|Gesamtwartezeit (in Millisekunden) für Latchanforderungen, die in der vergangenen Sekunde warten mussten.|  
  
## <a name="see-also"></a>Weitere Informationen  
 [Überwachen der Ressourcenverwendung &#40;Systemmonitor&#41;](monitor-resource-usage-system-monitor.md)  
  
  
