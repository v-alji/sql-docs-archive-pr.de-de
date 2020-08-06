---
title: MSSQLSERVER_1406 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1406 (Database Engine error)
ms.assetid: 915f97de-9b74-41f8-8bd5-b2d061416718
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: adaa0084b875f720c477189e0e8e085af124f4cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718208"
---
# <a name="mssqlserver_1406"></a>MSSQLSERVER_1406
    
## <a name="details"></a>Details  
  
|||  
|-|-|  
|Produktname|SQL Server|  
|Ereignis-ID|1406|  
|Ereignisquelle|MSSQLSERVER|  
|Komponente|SQLEngine|  
|Symbolischer Name|DBM_BADSTATEFORFORCESERVICE|  
|Meldungstext|Der Dienst kann nicht auf sichere Weise erzwungen werden. Entfernen Sie die Datenbankspiegelung, und stellen Sie die "%.*ls"-Datenbank wieder her, um Zugriff zu erhalten.|  
  
## <a name="explanation"></a>Erklärung  
 Der Dienst kann von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] nicht erzwungen werden, da mit dem Spiegelungsstatus nicht garantiert werden kann, dass der erzwungene Dienstvorgang ordnungsgemäß funktioniert.  
  
## <a name="user-action"></a>Benutzeraktion  
 Entfernen Sie die Datenbankspiegelung. Sie können anschließend die Spiegeldatenbank wiederherstellen, um Zugriff zu erhalten.  
  
## <a name="see-also"></a>Weitere Informationen  
 [Erzwingen des Diensts in einer Datenbank-Spiegelungssitzung (Transact-SQL)](../../database-engine/database-mirroring/force-service-in-a-database-mirroring-session-transact-sql.md)   
 [Entfernen der Datenbankspiegelung &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md)  
  
  
