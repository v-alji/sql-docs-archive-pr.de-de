---
title: srv_paramtype (API für erweiterte gespeicherte Prozeduren) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_paramtype
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_paramtype
ms.assetid: badc6d36-8a87-42b5-b28c-9c4f5ded8552
author: rothja
ms.author: jroth
ms.openlocfilehash: 0c4b4006f8214670e3bd2bddfbaabe917fb9d778
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615392"
---
# <a name="srv_paramtype-extended-stored-procedure-api"></a><span data-ttu-id="7d505-102">srv_paramtype (API für erweiterte gespeicherte Prozeduren)</span><span class="sxs-lookup"><span data-stu-id="7d505-102">srv_paramtype (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="7d505-103">Verwenden Sie stattdessen die CLR-Integration.</span><span class="sxs-lookup"><span data-stu-id="7d505-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="7d505-104">Gibt den Datentyp des Aufrufparameters für eine remote gespeicherte Prozedur zurück.</span><span class="sxs-lookup"><span data-stu-id="7d505-104">Returns the data type of a remote stored procedure call parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d505-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="7d505-105">Syntax</span></span>  
  
```  
  
int srv_paramtype (  
SRV_PROC *  
srvproc  
,  
int  
n   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="7d505-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="7d505-106">Arguments</span></span>  
 <span data-ttu-id="7d505-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="7d505-107">*srvproc*</span></span>  
 <span data-ttu-id="7d505-108">Ist ein Zeiger auf die SRV_PROC-Struktur, die das Handle für eine bestimmte Clientverbindung ist (in diesem Fall das Handle, das den Aufruf der remote gespeicherten Prozedur erhalten hat).</span><span class="sxs-lookup"><span data-stu-id="7d505-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure call).</span></span> <span data-ttu-id="7d505-109">Die Struktur enthält Informationen, mit der die API-Bibliothek für erweiterte gespeicherte Prozeduren die Kommunikation und Daten zwischen der Anwendung und dem Client verwaltet.</span><span class="sxs-lookup"><span data-stu-id="7d505-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="7d505-110">*n*</span><span class="sxs-lookup"><span data-stu-id="7d505-110">*n*</span></span>  
 <span data-ttu-id="7d505-111">Gibt die Anzahl der Parameter an.</span><span class="sxs-lookup"><span data-stu-id="7d505-111">Indicates the number of the parameter.</span></span> <span data-ttu-id="7d505-112">Der erste Parameter ist 1.</span><span class="sxs-lookup"><span data-stu-id="7d505-112">The first parameter is 1.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="7d505-113">Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="7d505-113">Returns</span></span>  
 <span data-ttu-id="7d505-114">Ein Tokenwert für den Datentyp des Parameters.</span><span class="sxs-lookup"><span data-stu-id="7d505-114">A token value for the data type of the parameter.</span></span> <span data-ttu-id="7d505-115">Informationen zu Datentypen finden Sie unter [Datentypen (API für erweiterte gespeicherte Prozeduren)](data-types-extended-stored-procedure-api.md).</span><span class="sxs-lookup"><span data-stu-id="7d505-115">For information about data types, see [Data Types &#40;Extended Stored Procedure API&#41;](data-types-extended-stored-procedure-api.md).</span></span> <span data-ttu-id="7d505-116">Wenn es keinen *n*-ten Parameter oder keine remote gespeicherte Prozedur gibt, wird –1 zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="7d505-116">If there is no *n*th parameter or if there is no remote stored procedure, it returns - 1.</span></span>  
  
 <span data-ttu-id="7d505-117">Diese Funktion gibt die folgenden Werte zurück, wenn der-Parameter einem der- [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Datentypen entspricht.</span><span class="sxs-lookup"><span data-stu-id="7d505-117">This function returns the following values, if the parameter is one of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] data types.</span></span>  
  
|<span data-ttu-id="7d505-118">Neue Datentypen</span><span class="sxs-lookup"><span data-stu-id="7d505-118">New data types</span></span>|<span data-ttu-id="7d505-119">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7d505-119">Return value</span></span>|  
|--------------------|------------------|  
|`BITN`|<span data-ttu-id="7d505-120">SRVBIT</span><span class="sxs-lookup"><span data-stu-id="7d505-120">SRVBIT</span></span>|  
|`BIGVARCHAR`|<span data-ttu-id="7d505-121">VARCHAR</span><span class="sxs-lookup"><span data-stu-id="7d505-121">VARCHAR</span></span>|  
|`BIGCHAR`|<span data-ttu-id="7d505-122">CHAR</span><span class="sxs-lookup"><span data-stu-id="7d505-122">CHAR</span></span>|  
|`BIGBINARY`|<span data-ttu-id="7d505-123">BINARY</span><span class="sxs-lookup"><span data-stu-id="7d505-123">BINARY</span></span>|  
|`BIGVARBINARY`|<span data-ttu-id="7d505-124">VARBINARY</span><span class="sxs-lookup"><span data-stu-id="7d505-124">VARBINARY</span></span>|  
|`NCHAR`|<span data-ttu-id="7d505-125">CHAR</span><span class="sxs-lookup"><span data-stu-id="7d505-125">CHAR</span></span>|  
|`NVARCHAR`|<span data-ttu-id="7d505-126">VARCHAR</span><span class="sxs-lookup"><span data-stu-id="7d505-126">VARCHAR</span></span>|  
|`NTEXT`|<span data-ttu-id="7d505-127">-1</span><span class="sxs-lookup"><span data-stu-id="7d505-127">-1</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7d505-128">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="7d505-128">Remarks</span></span>  
 <span data-ttu-id="7d505-129">Wenn eine remote gespeicherte Prozedur mit Parametern aufgerufen wird, werden die Parameter entweder mit ihrem Namen oder mit ihrer Position übergeben (unbenannt).</span><span class="sxs-lookup"><span data-stu-id="7d505-129">When a remote stored procedure call is made with parameters, the parameters can be passed either by name or by position (unnamed).</span></span> <span data-ttu-id="7d505-130">Werden beim Aufruf einer remote gespeicherten Prozedur einige Parameter über ihren Namen und andere über ihre Position übergeben, so tritt ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="7d505-130">If the remote stored procedure call is made with some parameters passed by name and some passed by position, an error occurs.</span></span> <span data-ttu-id="7d505-131">Der SRV_RPC Handler wird immer noch aufgerufen, wird jedoch so angezeigt, als ob keine Parameter vorhanden wären und **srv_rpcparams** 0 zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="7d505-131">The SRV_RPC handler is still called, but it appears as if there were no parameters and **srv_rpcparams** returns 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="7d505-132">Sie sollten den Quellcode der erweiterten gespeicherten Prozeduren sorgfältig prüfen, und Sie sollten die kompilierten DLL-Dateien testen, bevor Sie sie auf einem Produktionsserver installieren.</span><span class="sxs-lookup"><span data-stu-id="7d505-132">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="7d505-133">Weitere Informationen zum Überprüfen und Testen der Sicherheit finden Sie auf dieser [Microsoft-Website](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="7d505-133">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d505-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7d505-134">See Also</span></span>  
 <span data-ttu-id="7d505-135">[srv_paraminfo &#40;API für erweiterte gespeicherte Prozeduren&#41;](srv-paraminfo-extended-stored-procedure-api.md) </span><span class="sxs-lookup"><span data-stu-id="7d505-135">[srv_paraminfo &#40;Extended Stored Procedure API&#41;](srv-paraminfo-extended-stored-procedure-api.md) </span></span>  
 [<span data-ttu-id="7d505-136">srv_rpcparams (API für erweiterte gespeicherte Prozeduren)</span><span class="sxs-lookup"><span data-stu-id="7d505-136">srv_rpcparams &#40;Extended Stored Procedure API&#41;</span></span>](srv-rpcparams-extended-stored-procedure-api.md)  
  
  
