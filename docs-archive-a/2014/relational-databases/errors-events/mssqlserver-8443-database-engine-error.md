---
title: MSSQLSERVER_8443 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8443 (Database Engine error)
ms.assetid: a3541b9c-b1a8-4280-add1-275f08696b62
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ae02cc0d9e5661f4069884c22bf6eea0697bd2d7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719954"
---
# <a name="mssqlserver_8443"></a>MSSQLSERVER_8443
    
## <a name="details"></a>Details  
  
|||  
|-|-|  
|Produktname|SQL Server|  
|Ereignis-ID|8443|  
|Ereignisquelle|MSSQLSERVER|  
|Komponente|SQLEngine|  
|Symbolischer Name|SB_DIALOG_WO_CONV_GROUP|  
|Meldungstext|Die Konversation mit der ID '%.*ls' und dem Initiator %d verweist auf die fehlende Konversationsgruppe '%.\*ls'. Führen Sie DBCC CHECKDB aus, um die Datenbank zu analysieren und zu reparieren.|  
  
## <a name="explanation"></a>Erklärung  
 Von der Metadatenebene wurde NULL für die Konversationsgruppe zurückgegeben. Die Datenbank wurde in irgendeiner Weise beschädigt. Eine mögliche Ursache für eine Beschädigung kann ein Datenträgerfehler sein.  
  
## <a name="user-action"></a>Benutzeraktion  
 Führen Sie DBCC CHECKDB im Reparaturmodus aus, um die Datenbank wieder in einen konsistenten Zustand zu bringen. Möglicherweise werden dabei Meldungen gelöscht, um die Konsistenz wiederherzustellen. Untersuchen Sie die Systemfehlerprotokolle, um festzustellen, ob dieser Fehler durch einen anderen Fehler im System verursacht wurde.  
  
  
