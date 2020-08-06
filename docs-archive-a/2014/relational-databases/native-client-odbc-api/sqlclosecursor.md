---
title: SQLCloseCursor | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLCloseCursor function
ms.assetid: e7134d65-5c1c-4ae2-b119-d9b4b9a42483
author: rothja
ms.author: jroth
ms.openlocfilehash: 770a67432868516e5023d1cf0ff819501b4c130e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725702"
---
# <a name="sqlclosecursor"></a>SQLCloseCursor
  **SQLCloseCursor** ersetzt [SQLFreeStmt](sqlfreestmt.md) durch den *options* Wert SQL_CLOSE. Beim Empfang von **SQLCloseCursor**verwirft der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-ODBC-Treiber ausstehende Resultsetzeilen. Beachten Sie, dass die Spalten- und Parameterbindungen der Anweisung (sofern vorhanden) von **SQLCloseCursor**nicht geändert werden.  
  
## <a name="see-also"></a>Weitere Informationen  
 [SQLCloseCursor](https://go.microsoft.com/fwlink/?LinkId=59331)   
 [ODBC API Implementation Details](odbc-api-implementation-details.md)  
  
  
