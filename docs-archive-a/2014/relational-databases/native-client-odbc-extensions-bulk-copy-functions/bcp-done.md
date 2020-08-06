---
title: bcp_done | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_done
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_done function
ms.assetid: e59b3f16-5b59-40da-880f-f3edf657d1ee
author: rothja
ms.author: jroth
ms.openlocfilehash: cb9b0cbcc927fcd10c2d81b3c5c3d39bb80a8e9b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607734"
---
# <a name="bcp_done"></a>'bcp_done'
  Beendet einen Massenkopiervorgang aus Programmvariablen nach [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , der mit [bcp_sendrow](bcp-sendrow.md)ausgeführt wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
DBINT bcp_done (  
    HDBC   
hdbc  
);  
  
```  
  
## <a name="arguments"></a>Argumente  
 *hdbc*  
 Das für den Massenkopiervorgang aktivierte ODBC-Verbindungshandle.  
  
## <a name="returns"></a>Gibt zurück  
 Die Anzahl von Zeilen, die nach dem letzten Aufruf von [bcp_batch](bcp-batch.md) permanent gespeichert wurden, oder -1 im Fall eines Fehlers.  
  
## <a name="remarks"></a>Bemerkungen  
 Rufen Sie **bcp_done** nach dem letzten Aufruf von [bcp_sendrow](bcp-sendrow.md) oder [bcp_moretext](bcp-moretext.md)auf. Wenn Sie **bcp_done** nach dem Kopieren aller Daten nicht aufrufen, treten Fehler auf.  
  
## <a name="see-also"></a>Weitere Informationen  
 [Bulk Copy Functions](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
