---
title: srv_parammaxlen (API für erweiterte gespeicherte Prozeduren) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_parammaxlen
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_parammaxlen
ms.assetid: 49bfc29d-f76a-4963-b0e6-b8532dfda850
author: rothja
ms.author: jroth
ms.openlocfilehash: b289743b3de4b115a67a029dcc0261854ee3a40b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725806"
---
# <a name="srv_parammaxlen-extended-stored-procedure-api"></a><span data-ttu-id="7014b-102">srv_parammaxlen (API für erweiterte gespeicherte Prozeduren)</span><span class="sxs-lookup"><span data-stu-id="7014b-102">srv_parammaxlen (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="7014b-103">Verwenden Sie stattdessen die CLR-Integration.</span><span class="sxs-lookup"><span data-stu-id="7014b-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="7014b-104">Gibt die maximale Datenlänge des Aufrufparameters für eine remote gespeicherte Prozedur zurück.</span><span class="sxs-lookup"><span data-stu-id="7014b-104">Returns the maximum data length of a remote stored procedure call parameter.</span></span> <span data-ttu-id="7014b-105">Diese Funktion wurde durch die **srv_paraminfo**-Funktion ersetzt.</span><span class="sxs-lookup"><span data-stu-id="7014b-105">This function has been superseded by the **srv_paraminfo** function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7014b-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="7014b-106">Syntax</span></span>  
  
```  
  
int srv_parammaxlen (  
SRV_PROC *  
srvproc  
,  
int  
n   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="7014b-107">Argumente</span><span class="sxs-lookup"><span data-stu-id="7014b-107">Arguments</span></span>  
 <span data-ttu-id="7014b-108">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="7014b-108">*srvproc*</span></span>  
 <span data-ttu-id="7014b-109">Ist ein Zeiger auf die SRV_PROC-Struktur, die das Handle für eine bestimmte Clientverbindung ist (in diesem Fall das Handle, das den Aufruf der remote gespeicherten Prozedur erhalten hat).</span><span class="sxs-lookup"><span data-stu-id="7014b-109">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure call).</span></span> <span data-ttu-id="7014b-110">Die Struktur enthält Informationen, mit der die API-Bibliothek für erweiterte gespeicherte Prozeduren die Kommunikation und Daten zwischen der Anwendung und dem Client verwaltet.</span><span class="sxs-lookup"><span data-stu-id="7014b-110">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="7014b-111">*n*</span><span class="sxs-lookup"><span data-stu-id="7014b-111">*n*</span></span>  
 <span data-ttu-id="7014b-112">Gibt die Anzahl der Parameter an.</span><span class="sxs-lookup"><span data-stu-id="7014b-112">Indicates the number of the parameter.</span></span> <span data-ttu-id="7014b-113">Der erste Parameter ist 1.</span><span class="sxs-lookup"><span data-stu-id="7014b-113">The first parameter is 1.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="7014b-114">Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="7014b-114">Returns</span></span>  
 <span data-ttu-id="7014b-115">Die maximale Länge der Parameterdaten in Byte.</span><span class="sxs-lookup"><span data-stu-id="7014b-115">The maximum length, in bytes, of the parameter data.</span></span> <span data-ttu-id="7014b-116">Wenn es keinen *n*-ten Parameter oder keine remote gespeicherte Prozedur gibt, wird -1 zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="7014b-116">If there is no *n*th parameter or if there is no remote stored procedure, it returns -1.</span></span>  
  
 <span data-ttu-id="7014b-117">Diese Funktion gibt die folgenden Werte zurück, wenn der-Parameter einem der folgenden [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Datentypen entspricht.</span><span class="sxs-lookup"><span data-stu-id="7014b-117">This function returns the following values, if the parameter is one of the following [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types.</span></span>  
  
|<span data-ttu-id="7014b-118">Neue Datentypen</span><span class="sxs-lookup"><span data-stu-id="7014b-118">New data types</span></span>|<span data-ttu-id="7014b-119">Länge der Eingabedaten</span><span class="sxs-lookup"><span data-stu-id="7014b-119">Input data length</span></span>|  
|--------------------|-----------------------|  
|`BITN`|<span data-ttu-id="7014b-120">**NULL**: 1</span><span class="sxs-lookup"><span data-stu-id="7014b-120">**NULL:** 1</span></span><br /><br /> <span data-ttu-id="7014b-121">**Null:** 1</span><span class="sxs-lookup"><span data-stu-id="7014b-121">**ZERO:** 1</span></span><br /><br /> <span data-ttu-id="7014b-122">**>= 255:** nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="7014b-122">**>=255:** N/A</span></span><br /><br /> <span data-ttu-id="7014b-123">**<255:** nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="7014b-123">**<255:** N/A</span></span>|  
|`BIGVARCHAR`|<span data-ttu-id="7014b-124">**NULL:** 255</span><span class="sxs-lookup"><span data-stu-id="7014b-124">**NULL:** 255</span></span><br /><br /> <span data-ttu-id="7014b-125">**ZERO:** 255</span><span class="sxs-lookup"><span data-stu-id="7014b-125">**ZERO:** 255</span></span><br /><br /> <span data-ttu-id="7014b-126">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="7014b-126">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="7014b-127">**<255:** 255</span><span class="sxs-lookup"><span data-stu-id="7014b-127">**<255:** 255</span></span>|  
|`BIGCHAR`|<span data-ttu-id="7014b-128">**NULL:** 255</span><span class="sxs-lookup"><span data-stu-id="7014b-128">**NULL:** 255</span></span><br /><br /> <span data-ttu-id="7014b-129">**ZERO:** 255</span><span class="sxs-lookup"><span data-stu-id="7014b-129">**ZERO:** 255</span></span><br /><br /> <span data-ttu-id="7014b-130">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="7014b-130">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="7014b-131">**<255:** 255</span><span class="sxs-lookup"><span data-stu-id="7014b-131">**<255:** 255</span></span>|  
|`BIGBINARY`|<span data-ttu-id="7014b-132">**NULL:** 255</span><span class="sxs-lookup"><span data-stu-id="7014b-132">**NULL:** 255</span></span><br /><br /> <span data-ttu-id="7014b-133">**ZERO:** 255</span><span class="sxs-lookup"><span data-stu-id="7014b-133">**ZERO:** 255</span></span><br /><br /> <span data-ttu-id="7014b-134">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="7014b-134">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="7014b-135">**<255:** 255</span><span class="sxs-lookup"><span data-stu-id="7014b-135">**<255:** 255</span></span>|  
|`BIGVARBINARY`|<span data-ttu-id="7014b-136">**NULL:** 255</span><span class="sxs-lookup"><span data-stu-id="7014b-136">**NULL:** 255</span></span><br /><br /> <span data-ttu-id="7014b-137">**ZERO:** 255</span><span class="sxs-lookup"><span data-stu-id="7014b-137">**ZERO:** 255</span></span><br /><br /> <span data-ttu-id="7014b-138">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="7014b-138">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="7014b-139">**<255:** 255</span><span class="sxs-lookup"><span data-stu-id="7014b-139">**<255:** 255</span></span>|  
|`NCHAR`|<span data-ttu-id="7014b-140">**NULL:** 255</span><span class="sxs-lookup"><span data-stu-id="7014b-140">**NULL:** 255</span></span><br /><br /> <span data-ttu-id="7014b-141">**ZERO:** 255</span><span class="sxs-lookup"><span data-stu-id="7014b-141">**ZERO:** 255</span></span><br /><br /> <span data-ttu-id="7014b-142">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="7014b-142">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="7014b-143">**<255:** 255</span><span class="sxs-lookup"><span data-stu-id="7014b-143">**<255:** 255</span></span>|  
|`NVARCHAR`|<span data-ttu-id="7014b-144">**NULL:** 255</span><span class="sxs-lookup"><span data-stu-id="7014b-144">**NULL:** 255</span></span><br /><br /> <span data-ttu-id="7014b-145">**ZERO:** 255</span><span class="sxs-lookup"><span data-stu-id="7014b-145">**ZERO:** 255</span></span><br /><br /> <span data-ttu-id="7014b-146">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="7014b-146">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="7014b-147">**<255:** 255</span><span class="sxs-lookup"><span data-stu-id="7014b-147">**<255:** 255</span></span>|  
|`NTEXT`|<span data-ttu-id="7014b-148">**Null:** -1</span><span class="sxs-lookup"><span data-stu-id="7014b-148">**NULL:** -1</span></span><br /><br /> <span data-ttu-id="7014b-149">**ZERO:** –1</span><span class="sxs-lookup"><span data-stu-id="7014b-149">**ZERO:** -1</span></span><br /><br /> <span data-ttu-id="7014b-150">**>= 255:** -1</span><span class="sxs-lookup"><span data-stu-id="7014b-150">**>=255:** -1</span></span><br /><br /> <span data-ttu-id="7014b-151">\*\* \< 255:\*\* -1</span><span class="sxs-lookup"><span data-stu-id="7014b-151">**\<255:** -1</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7014b-152">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="7014b-152">Remarks</span></span>  
 <span data-ttu-id="7014b-153">Parameter einer remote gespeicherten Prozedur haben eine tatsächliche und eine maximale Datenlänge.</span><span class="sxs-lookup"><span data-stu-id="7014b-153">Each remote stored procedure parameter has an actual and a maximum data length.</span></span> <span data-ttu-id="7014b-154">Bei Standarddatentypen fester Länge, die keine Nullwerte zulassen, ist die tatsächliche Länge mit der maximalen Länge identisch.</span><span class="sxs-lookup"><span data-stu-id="7014b-154">For standard fixed-length data types that do not allow null values, the actual and maximum lengths are the same.</span></span> <span data-ttu-id="7014b-155">Bei Datentypen variabler Länge können die Längen unterschiedlich sein.</span><span class="sxs-lookup"><span data-stu-id="7014b-155">For variable-length data types, the lengths can vary.</span></span> <span data-ttu-id="7014b-156">Ein als **varchar(30)** deklarierter Parameter kann beispielsweise über Daten verfügen, die nur 10 Byte lang sind.</span><span class="sxs-lookup"><span data-stu-id="7014b-156">For example, a parameter declared as **varchar(30)** can have data that is only 10 bytes long.</span></span> <span data-ttu-id="7014b-157">Die tatsächliche Länge des Parameters ist 10, die maximale Länge jedoch 30.</span><span class="sxs-lookup"><span data-stu-id="7014b-157">The parameter's actual length is 10 and its maximum length is 30.</span></span> <span data-ttu-id="7014b-158">Die Funktion **srv_parammaxlen** ruft die maximale Datenlänge einer remote gespeicherten Prozedur ab.</span><span class="sxs-lookup"><span data-stu-id="7014b-158">The **srv_parammaxlen** function gets the maximum data length of a remote stored procedure.</span></span> <span data-ttu-id="7014b-159">Zum Abrufen der tatsächlichen Datenlänge eines Parameters verwenden Sie **srv_paramlen**.</span><span class="sxs-lookup"><span data-stu-id="7014b-159">To obtain the actual length of a parameter, use **srv_paramlen**.</span></span>  
  
 <span data-ttu-id="7014b-160">Wenn eine remote gespeicherte Prozedur mit Parametern aufgerufen wird, werden die Parameter entweder mit ihrem Namen oder mit ihrer Position übergeben (unbenannt).</span><span class="sxs-lookup"><span data-stu-id="7014b-160">When a remote stored procedure call is made with parameters, the parameters can be passed either by name or by position (unnamed).</span></span> <span data-ttu-id="7014b-161">Werden beim Aufruf einer remote gespeicherten Prozedur einige Parameter über ihren Namen und andere über ihre Position übergeben, so tritt ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="7014b-161">If the remote stored procedure call is made with some parameters passed by name and some passed by position, an error occurs.</span></span> <span data-ttu-id="7014b-162">Der SRV_RPC-Handler wird trotzdem aufgerufen, scheinbar jedoch ohne Parameter, und **srv_rpcparams** gibt 0 (null) zurück.</span><span class="sxs-lookup"><span data-stu-id="7014b-162">The SRV_RPC handler is still called, but it appears as if there were no parameters, and **srv_rpcparams** returns 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="7014b-163">Sie sollten den Quellcode der erweiterten gespeicherten Prozeduren sorgfältig prüfen, und Sie sollten die kompilierten DLL-Dateien testen, bevor Sie sie auf einem Produktionsserver installieren.</span><span class="sxs-lookup"><span data-stu-id="7014b-163">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="7014b-164">Weitere Informationen zum Überprüfen und Testen der Sicherheit finden Sie auf dieser [Microsoft-Website](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="7014b-164">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7014b-165">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7014b-165">See Also</span></span>  
 <span data-ttu-id="7014b-166">[srv_paraminfo &#40;API für erweiterte gespeicherte Prozeduren&#41;](srv-paraminfo-extended-stored-procedure-api.md) </span><span class="sxs-lookup"><span data-stu-id="7014b-166">[srv_paraminfo &#40;Extended Stored Procedure API&#41;](srv-paraminfo-extended-stored-procedure-api.md) </span></span>  
 [<span data-ttu-id="7014b-167">srv_rpcparams (API für erweiterte gespeicherte Prozeduren)</span><span class="sxs-lookup"><span data-stu-id="7014b-167">srv_rpcparams &#40;Extended Stored Procedure API&#41;</span></span>](srv-rpcparams-extended-stored-procedure-api.md)  
  
  
