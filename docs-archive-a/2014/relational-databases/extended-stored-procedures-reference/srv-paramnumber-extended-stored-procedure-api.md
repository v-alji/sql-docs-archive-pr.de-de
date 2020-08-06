---
title: srv_paramnumber (API für erweiterte gespeicherte Prozeduren) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_paramnumber
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_paramnumber
ms.assetid: d7a6dbff-71d9-4297-8a4f-bfd2876fe204
author: rothja
ms.author: jroth
ms.openlocfilehash: 1e621101c909ef251c40f38713e438d8e40d08a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620388"
---
# <a name="srv_paramnumber-extended-stored-procedure-api"></a><span data-ttu-id="8e74f-102">srv_paramnumber (API für erweiterte gespeicherte Prozeduren)</span><span class="sxs-lookup"><span data-stu-id="8e74f-102">srv_paramnumber (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="8e74f-103">Verwenden Sie stattdessen die CLR-Integration.</span><span class="sxs-lookup"><span data-stu-id="8e74f-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="8e74f-104">Gibt die Zahl eines Aufrufparameters für eine remote gespeicherte Prozedur zurück.</span><span class="sxs-lookup"><span data-stu-id="8e74f-104">Returns the number of a remote stored procedure call parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e74f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="8e74f-105">Syntax</span></span>  
  
```  
  
int srv_paramnumber (  
SRV_PROC *  
srvproc  
,  
DBCHAR *  
name  
,   
int  
namelen   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="8e74f-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="8e74f-106">Arguments</span></span>  
 <span data-ttu-id="8e74f-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="8e74f-107">*srvproc*</span></span>  
 <span data-ttu-id="8e74f-108">Ist ein Zeiger auf die SRV_PROC-Struktur, die das Handle für eine bestimmte Clientverbindung ist (in diesem Fall das Handle, das den Aufruf der remote gespeicherten Prozedur erhalten hat).</span><span class="sxs-lookup"><span data-stu-id="8e74f-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure call).</span></span> <span data-ttu-id="8e74f-109">Die Struktur enthält Informationen, mit der die API-Bibliothek für erweiterte gespeicherte Prozeduren die Kommunikation und Daten zwischen der Anwendung und dem Client verwaltet.</span><span class="sxs-lookup"><span data-stu-id="8e74f-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="8e74f-110">*name*</span><span class="sxs-lookup"><span data-stu-id="8e74f-110">*name*</span></span>  
 <span data-ttu-id="8e74f-111">Ein Zeiger auf den Parameter *name*</span><span class="sxs-lookup"><span data-stu-id="8e74f-111">Is a pointer to the parameter *name*.</span></span>  
  
 <span data-ttu-id="8e74f-112">*namelen*</span><span class="sxs-lookup"><span data-stu-id="8e74f-112">*namelen*</span></span>  
 <span data-ttu-id="8e74f-113">Die Länge von *name*</span><span class="sxs-lookup"><span data-stu-id="8e74f-113">Is the length of *name*.</span></span> <span data-ttu-id="8e74f-114">Wenn *name* NULL-terminiert ist, legen Sie für *namelen* den Wert SRV_NULLTERM fest.</span><span class="sxs-lookup"><span data-stu-id="8e74f-114">If *name* is null-terminated, set *namelen* to SRV_NULLTERM.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="8e74f-115">Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="8e74f-115">Returns</span></span>  
 <span data-ttu-id="8e74f-116">Die Parameternummer des benannten Parameters.</span><span class="sxs-lookup"><span data-stu-id="8e74f-116">The parameter number of the named parameter.</span></span> <span data-ttu-id="8e74f-117">Der erste Parameter ist 1.</span><span class="sxs-lookup"><span data-stu-id="8e74f-117">The first parameter is 1.</span></span> <span data-ttu-id="8e74f-118">Wenn es keinen Parameter namens *name* oder keine remote gespeicherte Prozedur gibt, wird der Wert 0 (null) zurückgegeben und eine Meldung generiert.</span><span class="sxs-lookup"><span data-stu-id="8e74f-118">If there is no parameter named *name* or no remote stored procedure, 0 is returned and a message is generated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8e74f-119">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="8e74f-119">Remarks</span></span>  
 <span data-ttu-id="8e74f-120">Wenn eine remote gespeicherte Prozedur mit Parametern aufgerufen wird, werden die Parameter entweder mit ihrem Namen oder mit ihrer Position übergeben (unbenannt).</span><span class="sxs-lookup"><span data-stu-id="8e74f-120">When a remote stored procedure call is made with parameters, the parameters can be passed either by name or by position (unnamed).</span></span> <span data-ttu-id="8e74f-121">Werden beim Aufruf einer remote gespeicherten Prozedur einige Parameter über ihren Namen und andere über ihre Position übergeben, so tritt ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="8e74f-121">If the remote stored procedure call is made with some parameters passed by name and some passed by position, an error occurs.</span></span> <span data-ttu-id="8e74f-122">Der SRV_RPC-Handler wird trotzdem aufgerufen, scheinbar jedoch ohne Parameter, und **srv_rpcparams** gibt 0 (null) zurück.</span><span class="sxs-lookup"><span data-stu-id="8e74f-122">The SRV_RPC handler is still called, but it appears as if there were no parameters, and **srv_rpcparams** returns 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="8e74f-123">Sie sollten den Quellcode der erweiterten gespeicherten Prozeduren sorgfältig prüfen, und Sie sollten die kompilierten DLL-Dateien testen, bevor Sie sie auf einem Produktionsserver installieren.</span><span class="sxs-lookup"><span data-stu-id="8e74f-123">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="8e74f-124">Weitere Informationen zum Überprüfen und Testen der Sicherheit finden Sie auf dieser [Microsoft-Website](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="8e74f-124">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e74f-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8e74f-125">See Also</span></span>  
 [<span data-ttu-id="8e74f-126">srv_rpcparams (API für erweiterte gespeicherte Prozeduren)</span><span class="sxs-lookup"><span data-stu-id="8e74f-126">srv_rpcparams &#40;Extended Stored Procedure API&#41;</span></span>](srv-rpcparams-extended-stored-procedure-api.md)  
  
  
