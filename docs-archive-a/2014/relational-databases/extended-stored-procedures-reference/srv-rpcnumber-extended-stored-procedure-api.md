---
title: srv_rpcnumber (API für erweiterte gespeicherte Prozeduren) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_rpcnumber
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_rpcnumber
ms.assetid: 3094085e-fe9e-423d-bf87-7852352c2d26
author: rothja
ms.author: jroth
ms.openlocfilehash: 25f30f8288125cf64d6b10a867d6af03c0f8ee91
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725794"
---
# <a name="srv_rpcnumber-extended-stored-procedure-api"></a><span data-ttu-id="f9f6f-102">srv_rpcnumber (API für erweiterte gespeicherte Prozeduren)</span><span class="sxs-lookup"><span data-stu-id="f9f6f-102">srv_rpcnumber (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="f9f6f-103">Verwenden Sie stattdessen die CLR-Integration.</span><span class="sxs-lookup"><span data-stu-id="f9f6f-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="f9f6f-104">Gibt die Nummernkomponente für den derzeit remote gespeicherten Prozeduraufruf zurück.</span><span class="sxs-lookup"><span data-stu-id="f9f6f-104">Returns the number component for the current remote stored procedure call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9f6f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f9f6f-105">Syntax</span></span>  
  
```  
  
int srv_rpcnumber ( SRV_PROC *  
srvproc   
)  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="f9f6f-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="f9f6f-106">Arguments</span></span>  
 <span data-ttu-id="f9f6f-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="f9f6f-107">*srvproc*</span></span>  
 <span data-ttu-id="f9f6f-108">Ist ein Zeiger auf die SRV_PROC-Struktur, die das Handle für eine bestimmte Clientverbindung ist (in diesem Fall das Handle, das die remote gespeicherte Prozedur erhalten hat).</span><span class="sxs-lookup"><span data-stu-id="f9f6f-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure).</span></span> <span data-ttu-id="f9f6f-109">Die Struktur enthält Informationen, mit der die API-Bibliothek für erweiterte gespeicherte Prozeduren die Kommunikation und Daten zwischen der Anwendung und dem Client verwaltet.</span><span class="sxs-lookup"><span data-stu-id="f9f6f-109">The structure contains information that the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="f9f6f-110">Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="f9f6f-110">Returns</span></span>  
 <span data-ttu-id="f9f6f-111">Die Nummernkomponente für die derzeit remote gespeicherte Prozedur.</span><span class="sxs-lookup"><span data-stu-id="f9f6f-111">The number component for the current remote stored procedure.</span></span> <span data-ttu-id="f9f6f-112">Wenn der Client beim Ausführen der remote gespeicherten Prozedur keine Nummernkomponente verwendet oder wenn derzeit keine remote gespeicherte Prozedur vorhanden ist, wird -1 zurückgegegeben.</span><span class="sxs-lookup"><span data-stu-id="f9f6f-112">If the client does not use a number component when running the remote stored procedure or if there is no current remote stored procedure, it returns - 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f9f6f-113">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="f9f6f-113">Remarks</span></span>  
 <span data-ttu-id="f9f6f-114">Diese Funktion gibt nur die Nummernkomponente der remote gespeicherten Prozedur zurück.</span><span class="sxs-lookup"><span data-stu-id="f9f6f-114">This function returns only the number component of the remote stored procedure.</span></span> <span data-ttu-id="f9f6f-115">Sie schließt die optionalen Spezifizierer für den Besitzer, den remote gespeicherten Prozedurnamen und den Datenbanknamen nicht ein.</span><span class="sxs-lookup"><span data-stu-id="f9f6f-115">It does not include the optional specifiers for owner, remote stored procedure name, and database name.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f9f6f-116">Sie sollten den Quellcode der erweiterten gespeicherten Prozeduren sorgfältig prüfen, und Sie sollten die kompilierten DLL-Dateien testen, bevor Sie sie auf einem Produktionsserver installieren.</span><span class="sxs-lookup"><span data-stu-id="f9f6f-116">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="f9f6f-117">Weitere Informationen zum Überprüfen und Testen der Sicherheit finden Sie auf dieser [Microsoft-Website](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="f9f6f-117">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
