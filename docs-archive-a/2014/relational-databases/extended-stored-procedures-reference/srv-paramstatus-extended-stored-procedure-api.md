---
title: srv_paramstatus (API für erweiterte gespeicherte Prozeduren) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_paramstatus
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_paramstatus
ms.assetid: 86cecd45-0b09-42e9-8152-32a12a1c2b7a
author: rothja
ms.author: jroth
ms.openlocfilehash: d89d4ccbb6a97ff47669ad4ed9c0b4c22ac934eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695601"
---
# <a name="srv_paramstatus-extended-stored-procedure-api"></a><span data-ttu-id="0d9cf-102">'srv_paramstatus' (API für erweiterte gespeicherte Prozeduren)</span><span class="sxs-lookup"><span data-stu-id="0d9cf-102">srv_paramstatus (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="0d9cf-103">Verwenden Sie stattdessen die CLR-Integration.</span><span class="sxs-lookup"><span data-stu-id="0d9cf-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="0d9cf-104">Gibt den Status eines bestimmten Aufrufparameters für eine remote gespeicherte Prozedur zurück.</span><span class="sxs-lookup"><span data-stu-id="0d9cf-104">Returns the status of a particular remote stored procedure call parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d9cf-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="0d9cf-105">Syntax</span></span>  
  
```  
  
int srv_paramstatus (  
SRV_PROC *  
srvproc  
,  
int  
n   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="0d9cf-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="0d9cf-106">Arguments</span></span>  
 <span data-ttu-id="0d9cf-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="0d9cf-107">*srvproc*</span></span>  
 <span data-ttu-id="0d9cf-108">Ist ein Zeiger auf die SRV_PROC-Struktur, die das Handle für eine bestimmte Clientverbindung ist (in diesem Fall das Handle, das den Aufruf der remote gespeicherten Prozedur erhalten hat).</span><span class="sxs-lookup"><span data-stu-id="0d9cf-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure call).</span></span> <span data-ttu-id="0d9cf-109">Die Struktur enthält Informationen, mit der die API-Bibliothek für erweiterte gespeicherte Prozeduren die Kommunikation und Daten zwischen der Anwendung und dem Client verwaltet.</span><span class="sxs-lookup"><span data-stu-id="0d9cf-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="0d9cf-110">*n*</span><span class="sxs-lookup"><span data-stu-id="0d9cf-110">*n*</span></span>  
 <span data-ttu-id="0d9cf-111">Gibt die Anzahl der Parameter an.</span><span class="sxs-lookup"><span data-stu-id="0d9cf-111">Indicates the number of the parameter.</span></span> <span data-ttu-id="0d9cf-112">Die erste Parameternummer ist 1.</span><span class="sxs-lookup"><span data-stu-id="0d9cf-112">The first parameter is number 1.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="0d9cf-113">Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="0d9cf-113">Returns</span></span>  
 <span data-ttu-id="0d9cf-114">`int` mit Statusflags für den Parameter.</span><span class="sxs-lookup"><span data-stu-id="0d9cf-114">An `int` that contains status flags for the parameter.</span></span> <span data-ttu-id="0d9cf-115">Aktuell gibt es nur einen Flag: Wenn das Bit 0 auf 1 festgelegt ist, ist der Parameter ein Rückgabeparameter.</span><span class="sxs-lookup"><span data-stu-id="0d9cf-115">Currently, there is only one flag: If bit 0 is set to 1, the parameter is a return parameter.</span></span> <span data-ttu-id="0d9cf-116">Wenn es keinen *n*-ten Parameter oder keine remote gespeicherte Prozedur gibt, wird -1 zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0d9cf-116">If there is no *n*th parameter or if there is no remote stored procedure, it returns -1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0d9cf-117">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="0d9cf-117">Remarks</span></span>  
 <span data-ttu-id="0d9cf-118">Diese Routine gibt die Statusflags für einen Aufrufparameter einer remote gespeicherten Prozedur zurück.</span><span class="sxs-lookup"><span data-stu-id="0d9cf-118">This routine returns the status flags for a remote stored procedure call parameter.</span></span>  
  
 <span data-ttu-id="0d9cf-119">Parameter enthalten die zwischen Clients und der Anwendung mit remote gespeicherten Prozeduren übergebenen Daten.</span><span class="sxs-lookup"><span data-stu-id="0d9cf-119">Parameters contain data passed between clients and the application with remote stored procedures.</span></span> <span data-ttu-id="0d9cf-120">Der Client kann bestimmte Parameter als Rückgabeparameter angeben.</span><span class="sxs-lookup"><span data-stu-id="0d9cf-120">The client can specify certain parameters as return parameters.</span></span> <span data-ttu-id="0d9cf-121">Diese Rückgabeparameter können Werte enthalten, die von der Anwendung wieder an den Client übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="0d9cf-121">These return parameters can contain values that the application passes back to the client.</span></span>  
  
 <span data-ttu-id="0d9cf-122">Aktuell gibt es nur ein einziges Statusflag. Es gibt an, ob der Parameter ein Rückgabeparameter ist.</span><span class="sxs-lookup"><span data-stu-id="0d9cf-122">Currently, the only status flag is one that indicates whether the parameter is a return parameter.</span></span>  
  
 <span data-ttu-id="0d9cf-123">Wenn eine remote gespeicherte Prozedur mit Parametern aufgerufen wird, werden die Parameter entweder mit ihrem Namen oder mit ihrer Position übergeben (unbenannt).</span><span class="sxs-lookup"><span data-stu-id="0d9cf-123">When a remote stored procedure call is made with parameters, the parameters can be passed either by name or by position (unnamed).</span></span> <span data-ttu-id="0d9cf-124">Werden beim Aufruf einer remote gespeicherten Prozedur einige Parameter über ihren Namen und andere über ihre Position übergeben, so tritt ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="0d9cf-124">If the remote stored procedure call is made with some parameters passed by name and some passed by position, an error occurs.</span></span> <span data-ttu-id="0d9cf-125">Wenn ein Fehler auftritt, wird der SRV_RPC-Handler weiterhin aufgerufen, wird jedoch so angezeigt, als ob keine Parameter vorhanden wären und **srv_rpcparams** 0 zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="0d9cf-125">If an error occurs, the SRV_RPC handler is still called, but it appears as if there were no parameters, and **srv_rpcparams** returns 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="0d9cf-126">Sie sollten den Quellcode der erweiterten gespeicherten Prozeduren sorgfältig prüfen, und Sie sollten die kompilierten DLL-Dateien testen, bevor Sie sie auf einem Produktionsserver installieren.</span><span class="sxs-lookup"><span data-stu-id="0d9cf-126">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="0d9cf-127">Weitere Informationen zum Überprüfen und Testen der Sicherheit finden Sie auf dieser [Microsoft-Website](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="0d9cf-127">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d9cf-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0d9cf-128">See Also</span></span>  
 [<span data-ttu-id="0d9cf-129">srv_rpcparams (API für erweiterte gespeicherte Prozeduren)</span><span class="sxs-lookup"><span data-stu-id="0d9cf-129">srv_rpcparams &#40;Extended Stored Procedure API&#41;</span></span>](srv-rpcparams-extended-stored-procedure-api.md)  
  
  
