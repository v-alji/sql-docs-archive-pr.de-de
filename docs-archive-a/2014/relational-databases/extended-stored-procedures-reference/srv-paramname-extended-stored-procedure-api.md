---
title: srv_paramname (API für erweiterte gespeicherte Prozeduren) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_paramname
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_paramname
ms.assetid: 1a53d707-7b06-49cc-a0df-ac727cfe953f
author: rothja
ms.author: jroth
ms.openlocfilehash: 2227ac3d46efe7d09abc05964248229f3533d42d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725805"
---
# <a name="srv_paramname-extended-stored-procedure-api"></a><span data-ttu-id="6df6e-102">srv_paramname (API für erweiterte gespeicherte Prozeduren)</span><span class="sxs-lookup"><span data-stu-id="6df6e-102">srv_paramname (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="6df6e-103">Verwenden Sie stattdessen die CLR-Integration.</span><span class="sxs-lookup"><span data-stu-id="6df6e-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="6df6e-104">Gibt den Namen des Aufrufparameters für eine remote gespeicherte Prozedur zurück.</span><span class="sxs-lookup"><span data-stu-id="6df6e-104">Returns the name of a remote stored procedure call parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6df6e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="6df6e-105">Syntax</span></span>  
  
```  
  
DBCHAR * srv_paramname (  
SRV_PROC * srvproc,intn, int *len );  
```  
  
## <a name="arguments"></a><span data-ttu-id="6df6e-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="6df6e-106">Arguments</span></span>  
 <span data-ttu-id="6df6e-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="6df6e-107">*srvproc*</span></span>  
 <span data-ttu-id="6df6e-108">Ist ein Zeiger auf die SRV_PROC-Struktur, die das Handle für eine bestimmte Clientverbindung ist (in diesem Fall das Handle, das den Aufruf der remote gespeicherten Prozedur erhalten hat).</span><span class="sxs-lookup"><span data-stu-id="6df6e-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure call).</span></span> <span data-ttu-id="6df6e-109">Die Struktur enthält Informationen, mit der die API-Bibliothek für erweiterte gespeicherte Prozeduren die Kommunikation und Daten zwischen der Anwendung und dem Client verwaltet.</span><span class="sxs-lookup"><span data-stu-id="6df6e-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="6df6e-110">*n*</span><span class="sxs-lookup"><span data-stu-id="6df6e-110">*n*</span></span>  
 <span data-ttu-id="6df6e-111">Gibt die Anzahl der Parameter an.</span><span class="sxs-lookup"><span data-stu-id="6df6e-111">Indicates the number of the parameter.</span></span> <span data-ttu-id="6df6e-112">Der erste Parameter ist 1.</span><span class="sxs-lookup"><span data-stu-id="6df6e-112">The first parameter is 1.</span></span>  
  
 <span data-ttu-id="6df6e-113">*Nest*</span><span class="sxs-lookup"><span data-stu-id="6df6e-113">*len*</span></span>  
 <span data-ttu-id="6df6e-114">Stellt einen Zeiger auf eine `int`-Variable bereit, die die Länge des Parameternamens in Byte enthält.</span><span class="sxs-lookup"><span data-stu-id="6df6e-114">Provides a pointer to an `int` variable that contains the length, in bytes, of the parameter name.</span></span> <span data-ttu-id="6df6e-115">Wenn *len* NULL ist, wird die Länge des Parameternamens der remote gespeicherten Prozedur nicht zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="6df6e-115">If *len* is NULL, the length of the remote stored procedure parameter name is not returned.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="6df6e-116">Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="6df6e-116">Returns</span></span>  
 <span data-ttu-id="6df6e-117">Ein Zeiger auf eine auf NULL endende Zeichenfolge, die den Parameternamen enthält.</span><span class="sxs-lookup"><span data-stu-id="6df6e-117">A pointer to a null-terminated character string that contains the parameter name.</span></span> <span data-ttu-id="6df6e-118">Die Länge des Parameternamens wird in *len* gespeichert.</span><span class="sxs-lookup"><span data-stu-id="6df6e-118">The length of the parameter name is stored in *len*.</span></span> <span data-ttu-id="6df6e-119">Wenn es keinen *n*-ten Parameter oder keine remote gespeicherte Prozedur gibt, wird NULL zurückgegeben, *len* wird auf –1 festgelegt, und eine Informationsfehlermeldung wird gesendet.</span><span class="sxs-lookup"><span data-stu-id="6df6e-119">If there is no *n*th parameter or no remote stored procedure, it returns NULL, *len* is set to -1, and an informational error message is sent.</span></span> <span data-ttu-id="6df6e-120">Wenn der Parametername gleich NULL ist, wird *len* auf 0 festgelegt, und es wird eine NULL-terminierte leere Zeichenfolge zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="6df6e-120">If the parameter name is NULL, *len* is set to 0 and a null-terminated empty string is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6df6e-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="6df6e-121">Remarks</span></span>  
 <span data-ttu-id="6df6e-122">Diese Funktion ruft den Namen des Aufrufparameters einer remote gespeicherten Prozedur ab.</span><span class="sxs-lookup"><span data-stu-id="6df6e-122">This function gets the name of a remote stored procedure call parameter.</span></span> <span data-ttu-id="6df6e-123">Wenn eine remote gespeicherte Prozedur mit Parametern aufgerufen wird, werden die Parameter entweder mit ihrem Namen oder mit ihrer Position übergeben (unbenannt).</span><span class="sxs-lookup"><span data-stu-id="6df6e-123">When a remote stored procedure call is made with parameters, the parameters can be passed either by name or by position (unnamed).</span></span> <span data-ttu-id="6df6e-124">Werden beim Aufruf einer remote gespeicherten Prozedur einige Parameter über ihren Namen und andere über ihre Position übergeben, so tritt ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="6df6e-124">If the remote stored procedure call is made with some parameters passed by name and some passed by position, an error occurs.</span></span> <span data-ttu-id="6df6e-125">Der SRV_RPC-Handler wird trotzdem aufgerufen, scheinbar jedoch ohne Parameter, und **srv_rpcparams** gibt 0 (null) zurück.</span><span class="sxs-lookup"><span data-stu-id="6df6e-125">The SRV_RPC handler is still called, but it appears as if there were no parameters, and **srv_rpcparams** returns 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="6df6e-126">Sie sollten den Quellcode der erweiterten gespeicherten Prozeduren sorgfältig prüfen, und Sie sollten die kompilierten DLL-Dateien testen, bevor Sie sie auf einem Produktionsserver installieren.</span><span class="sxs-lookup"><span data-stu-id="6df6e-126">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="6df6e-127">Weitere Informationen zum Überprüfen und Testen der Sicherheit finden Sie auf dieser [Microsoft-Website](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="6df6e-127">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6df6e-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6df6e-128">See Also</span></span>  
 [<span data-ttu-id="6df6e-129">srv_rpcparams (API für erweiterte gespeicherte Prozeduren)</span><span class="sxs-lookup"><span data-stu-id="6df6e-129">srv_rpcparams &#40;Extended Stored Procedure API&#41;</span></span>](srv-rpcparams-extended-stored-procedure-api.md)  
  
  
