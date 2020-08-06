---
title: MSSQLSERVER_2546 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2546 (Database Engine error)
ms.assetid: c8f0e1b4-c7c4-45f2-9221-746714172313
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5c1c5f64ca0daba413f2b71c05f5b8e57b2d55df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696873"
---
# <a name="mssqlserver_2546"></a>MSSQLSERVER_2546
    
## <a name="details"></a>Details  
  
|||  
|-|-|  
|Produktname|SQL Server|  
|Ereignis-ID|2546|  
|Ereignisquelle|MSSQLSERVER|  
|Komponente|SQLEngine|  
|Symbolischer Name|DBCC_INDEX_MARKED_DISABLED|  
|Meldungstext|Der 'INDEX_NAME'-Index für die 'OBJECT_NAME'-Tabelle ist als deaktiviert markiert. Erstellen Sie den Index neu, um ihn online zu schalten.|  
  
## <a name="explanation"></a>Erklärung  
 Der angegebene Index ist als offline markiert oder deaktiviert. Daher kann dieser Index nicht geprüft werden.  
  
## <a name="user-action"></a>Benutzeraktion  
 Erstellen Sie den Index mithilfe von ALTER INDEX neu.  
  
## <a name="see-also"></a>Weitere Informationen  
 [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql)   
 [Neuorganisieren und Neuerstellen von Indizes](../indexes/indexes.md)  
  
  
