---
title: MSSQLSERVER_41332 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41332 (Database Engine error)
ms.assetid: d3403c3e-d178-4006-b6c9-c18609562db5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 72a87838673f07f7a40596517ab54533d944e15e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619875"
---
# <a name="mssqlserver_41332"></a>MSSQLSERVER_41332
    
## <a name="details"></a>Details  
  
|||  
|-|-|  
|Produktname|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|Ereignis-ID|41332|  
|Ereignisquelle|MSSQLSERVER|  
|Komponente|SQLEngine|  
|Symbolischer Name|SQL_SNAPSHOT_NOT_SUPPORTED|  
|Meldungstext|Wenn der TRANSACTION ISOLATION LEVEL der Sitzung auf SNAPSHOT festgelegt ist, kann nicht auf speicheroptimierte Tabellen und systemintern kompilierte gespeicherte Prozeduren zugegriffen werden, und diese können nicht erstellt werden.|  
  
## <a name="explanation"></a>Erklärung  
 Die Transaktion wurde auf der Momentaufnahmeisolationsstufe gestartet, und anschließend wurde versucht, eine nicht kompatible Funktion zu verwenden.  
  
## <a name="user-action"></a>Benutzeraktion  
 Starten Sie die Transaktion mit einer anderen Isolationsstufe. Weitere Informationen finden Sie unter [In-Memory OLTP &#40;Arbeitsspeicheroptimierung&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).  
  
## <a name="see-also"></a>Weitere Informationen  
 [In-Memory-OLTP &#40;Arbeitsspeicheroptimierung&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
