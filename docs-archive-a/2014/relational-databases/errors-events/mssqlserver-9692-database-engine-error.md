---
title: MSSQLSERVER_9692 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9692 (Database Engine error)
ms.assetid: 02399d6e-ab5e-4f30-8a3e-2bb1e8c135b5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6b6ba95771aafffa5a322ffa1b7443419936addd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617034"
---
# <a name="mssqlserver_9692"></a>MSSQLSERVER_9692
    
## <a name="details"></a>Details  
  
|||  
|-|-|  
|Produktname|SQL Server|  
|Ereignis-ID|9692|  
|Ereignisquelle|MSSQLSERVER|  
|Komponente|SQLEngine|  
|Symbolischer Name|SB2_CANT_LISTEN_PORT_IN_USE|  
|Meldungstext|Der %S_MSG-Protokolltransport kann nicht an Port %d lauschen, weil er von einem anderen Prozess verwendet wird|  
  
## <a name="explanation"></a>Erklärung  
 Ein anderes Programm auf dem Computer verwendet den angegebenen TCP-Port.  
  
## <a name="user-action"></a>Benutzeraktion  
 Führen `netstat -aon` Sie aus, um zu bestimmen, welches Programm den Port verwendet. Deaktivieren Sie die entsprechende Anwendung, oder geben Sie einen anderen Port für Service Broker an.  
  
  
