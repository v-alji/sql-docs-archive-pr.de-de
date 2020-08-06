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
# <a name="srv_got_attention-extended-stored-procedure-api"></a><span data-ttu-id="f132a-102">'srv_got_attention' (API für erweiterte gespeicherte Prozeduren)</span><span class="sxs-lookup"><span data-stu-id="f132a-102">srv_got_attention (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="f132a-103">Verwenden Sie stattdessen die CLR-Integration.</span><span class="sxs-lookup"><span data-stu-id="f132a-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="f132a-104">Überprüft, ob die aktuelle Verbindung oder der aktuelle Task abgebrochen werden muss, und gibt TRUE zurück, wenn die Verbindung beendet oder der Batch abgebrochen wurde.</span><span class="sxs-lookup"><span data-stu-id="f132a-104">Checks whether the current connection or task needs to be aborted and returns TRUE if the connection is killed or the batch is aborted</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f132a-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f132a-105">Syntax</span></span>  
  
```  
  
BOOL srv_got_attention  
(SRV_PROC *  
srvproc  
);  
  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f132a-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="f132a-106">Parameters</span></span>  
 <span data-ttu-id="f132a-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="f132a-107">*srvproc*</span></span>  
 <span data-ttu-id="f132a-108">Zeiger, der eine Datenbankverbindung identifiziert</span><span class="sxs-lookup"><span data-stu-id="f132a-108">Pointer identifying a database connection.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f132a-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f132a-109">Return Value</span></span>  
 <span data-ttu-id="f132a-110">TRUE, wenn die Verbindung beendet oder der Batch abgebrochen wird.</span><span class="sxs-lookup"><span data-stu-id="f132a-110">TRUE if the connection is killed or the batch is aborted.</span></span> <span data-ttu-id="f132a-111">FALSE, wenn die Verbindung bzw. der Batch aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="f132a-111">FALSE if the connection or batch is active.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f132a-112">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="f132a-112">Remarks</span></span>  
 <span data-ttu-id="f132a-113">Eine erweiterte gespeicherte Prozedur mit langer Ausführungszeit sollte die Servertätigkeit in regelmäßigen Abständen mit **srv_got_attention** prüfen, damit die Prozedur sich selbst beenden kann, falls die Verbindung beendet oder der Batch abgebrochen wurde.</span><span class="sxs-lookup"><span data-stu-id="f132a-113">A long-running extended stored procedure should check the server attention by calling **srv_got_attention** periodically so that the procedure may terminate itself when the connection is killed or the batch is aborted.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f132a-114">Sie sollten den Quellcode der erweiterten gespeicherten Prozeduren sorgfältig prüfen, und Sie sollten die kompilierten DLL-Dateien testen, bevor Sie sie auf einem Produktionsserver installieren.</span><span class="sxs-lookup"><span data-stu-id="f132a-114">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="f132a-115">Weitere Informationen zum Überprüfen und Testen der Sicherheit finden Sie auf dieser [Microsoft-Website](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="f132a-115">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
