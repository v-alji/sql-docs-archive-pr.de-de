---
title: „srv_got_attention“ (API für die erweiterte gespeicherte Prozedur) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_got_attention
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_got_attention
ms.assetid: 805e68e1-d17f-41bd-8b9f-a27283bb6fbe
author: rothja
ms.author: jroth
ms.openlocfilehash: bb5432e2f5e259187e506237842fbb9110e27a69
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725821"
---
# <a name="srv_got_attention-extended-stored-procedure-api"></a>'srv_got_attention' (API für erweiterte gespeicherte Prozeduren)
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] Verwenden Sie stattdessen die CLR-Integration.  
  
 Überprüft, ob die aktuelle Verbindung oder der aktuelle Task abgebrochen werden muss, und gibt TRUE zurück, wenn die Verbindung beendet oder der Batch abgebrochen wurde.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
BOOL srv_got_attention  
(SRV_PROC *  
srvproc  
);  
  
```  
  
#### <a name="parameters"></a>Parameter  
 *srvproc*  
 Zeiger, der eine Datenbankverbindung identifiziert  
  
## <a name="return-value"></a>Rückgabewert  
 TRUE, wenn die Verbindung beendet oder der Batch abgebrochen wird. FALSE, wenn die Verbindung bzw. der Batch aktiv ist.  
  
## <a name="remarks"></a>Bemerkungen  
 Eine erweiterte gespeicherte Prozedur mit langer Ausführungszeit sollte die Servertätigkeit in regelmäßigen Abständen mit **srv_got_attention** prüfen, damit die Prozedur sich selbst beenden kann, falls die Verbindung beendet oder der Batch abgebrochen wurde.  
  
> [!IMPORTANT]  
>  Sie sollten den Quellcode der erweiterten gespeicherten Prozeduren sorgfältig prüfen, und Sie sollten die kompilierten DLL-Dateien testen, bevor Sie sie auf einem Produktionsserver installieren. Weitere Informationen zum Überprüfen und Testen der Sicherheit finden Sie auf dieser [Microsoft-Website](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).  
  
  
