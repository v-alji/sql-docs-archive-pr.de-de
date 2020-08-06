---
title: srv_paramlen (API für erweiterte gespeicherte Prozeduren) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_paramlen
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_paramlen
ms.assetid: d1fe92ff-cad6-4396-8216-125e5642e81e
author: rothja
ms.author: jroth
ms.openlocfilehash: fc2a0fa7f8409767a2afaa9c4c621ea72732b701
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725810"
---
# <a name="srv_paramlen-extended-stored-procedure-api"></a><span data-ttu-id="42968-102">srv_paramlen (API für erweiterte gespeicherte Prozeduren)</span><span class="sxs-lookup"><span data-stu-id="42968-102">srv_paramlen (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="42968-103">Verwenden Sie stattdessen die CLR-Integration.</span><span class="sxs-lookup"><span data-stu-id="42968-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="42968-104">Gibt die Datenlänge des Aufrufparameters für eine remote gespeicherte Prozedur zurück.</span><span class="sxs-lookup"><span data-stu-id="42968-104">Returns the data length of a remote stored procedure call parameter.</span></span> <span data-ttu-id="42968-105">Diese Funktion wurde durch die **srv_paraminfo**-Funktion ersetzt.</span><span class="sxs-lookup"><span data-stu-id="42968-105">This function has been superseded by the **srv_paraminfo** function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42968-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="42968-106">Syntax</span></span>  
  
```  
  
int srv_paramlen (  
SRV_PROC *  
srvproc  
,  
int  
n   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="42968-107">Argumente</span><span class="sxs-lookup"><span data-stu-id="42968-107">Arguments</span></span>  
 <span data-ttu-id="42968-108">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="42968-108">*srvproc*</span></span>  
 <span data-ttu-id="42968-109">Ist ein Zeiger auf die SRV_PROC-Struktur, die das Handle für eine bestimmte Clientverbindung ist (in diesem Fall das Handle, das den Aufruf der remote gespeicherten Prozedur erhalten hat).</span><span class="sxs-lookup"><span data-stu-id="42968-109">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure call).</span></span> <span data-ttu-id="42968-110">Die Struktur enthält Informationen, mit der die API-Bibliothek für erweiterte gespeicherte Prozeduren die Kommunikation und Daten zwischen der Anwendung und dem Client verwaltet.</span><span class="sxs-lookup"><span data-stu-id="42968-110">The structure contains information that the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="42968-111">*n*</span><span class="sxs-lookup"><span data-stu-id="42968-111">*n*</span></span>  
 <span data-ttu-id="42968-112">Gibt die Anzahl der Parameter an.</span><span class="sxs-lookup"><span data-stu-id="42968-112">Indicates the number of the parameter.</span></span> <span data-ttu-id="42968-113">Der erste Parameter ist 1.</span><span class="sxs-lookup"><span data-stu-id="42968-113">The first parameter is 1.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="42968-114">Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="42968-114">Returns</span></span>  
 <span data-ttu-id="42968-115">Die tatsächliche Länge der Parameterdaten in Byte.</span><span class="sxs-lookup"><span data-stu-id="42968-115">The actual length, in bytes, of the parameter data.</span></span> <span data-ttu-id="42968-116">Wenn es keinen *n*-ten Parameter gibt, oder wenn es keine remote gespeicherte Prozedur gibt, wird –1 zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="42968-116">If there is no *n*th parameter or there is no remote stored procedure, it returns -1.</span></span> <span data-ttu-id="42968-117">Wenn der *n*-te Parameter NULL ist, wird 0 zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="42968-117">If the *n*th parameter is NULL, it returns 0.</span></span>  
  
 <span data-ttu-id="42968-118">Diese Funktion gibt die folgenden Werte zurück, wenn der-Parameter einem der folgenden [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] System Datentypen entspricht.</span><span class="sxs-lookup"><span data-stu-id="42968-118">This function returns the following values, if the parameter is one of the following [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] system data types.</span></span>  
  
|<span data-ttu-id="42968-119">Neue Datentypen</span><span class="sxs-lookup"><span data-stu-id="42968-119">New data types</span></span>|<span data-ttu-id="42968-120">Länge der Eingabedaten</span><span class="sxs-lookup"><span data-stu-id="42968-120">Input data length</span></span>|  
|--------------------|-----------------------|  
|`BITN`|<span data-ttu-id="42968-121">**NULL**: 1</span><span class="sxs-lookup"><span data-stu-id="42968-121">**NULL:** 1</span></span><br /><br /> <span data-ttu-id="42968-122">**Null:** 1</span><span class="sxs-lookup"><span data-stu-id="42968-122">**ZERO:** 1</span></span><br /><br /> <span data-ttu-id="42968-123">**>= 255:** nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="42968-123">**>=255:** N/A</span></span><br /><br /> <span data-ttu-id="42968-124">**<255:** nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="42968-124">**<255:** N/A</span></span>|  
|`BIGVARCHAR`|<span data-ttu-id="42968-125">**NULL**: 0</span><span class="sxs-lookup"><span data-stu-id="42968-125">**NULL:** 0</span></span><br /><br /> <span data-ttu-id="42968-126">**Null:** 1</span><span class="sxs-lookup"><span data-stu-id="42968-126">**ZERO:** 1</span></span><br /><br /> <span data-ttu-id="42968-127">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="42968-127">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="42968-128">**<255:** tatsächlicher *len*-Wert</span><span class="sxs-lookup"><span data-stu-id="42968-128">**<255:** actual *len*</span></span>|  
|`BIGCHAR`|<span data-ttu-id="42968-129">**NULL**: 0</span><span class="sxs-lookup"><span data-stu-id="42968-129">**NULL:** 0</span></span><br /><br /> <span data-ttu-id="42968-130">**ZERO:** 255</span><span class="sxs-lookup"><span data-stu-id="42968-130">**ZERO:** 255</span></span><br /><br /> <span data-ttu-id="42968-131">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="42968-131">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="42968-132">**<255:** 255</span><span class="sxs-lookup"><span data-stu-id="42968-132">**<255:** 255</span></span>|  
|`BIGBINARY`|<span data-ttu-id="42968-133">**NULL**: 0</span><span class="sxs-lookup"><span data-stu-id="42968-133">**NULL:** 0</span></span><br /><br /> <span data-ttu-id="42968-134">**ZERO:** 255</span><span class="sxs-lookup"><span data-stu-id="42968-134">**ZERO:** 255</span></span><br /><br /> <span data-ttu-id="42968-135">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="42968-135">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="42968-136">**<255:** 255</span><span class="sxs-lookup"><span data-stu-id="42968-136">**<255:** 255</span></span>|  
|`BIGVARBINARY`|<span data-ttu-id="42968-137">**NULL**: 0</span><span class="sxs-lookup"><span data-stu-id="42968-137">**NULL:** 0</span></span><br /><br /> <span data-ttu-id="42968-138">**Null:** 1</span><span class="sxs-lookup"><span data-stu-id="42968-138">**ZERO:** 1</span></span><br /><br /> <span data-ttu-id="42968-139">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="42968-139">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="42968-140">**<255:** tatsächlicher *len*-Wert</span><span class="sxs-lookup"><span data-stu-id="42968-140">**<255:** actual *len*</span></span>|  
|`NCHAR`|<span data-ttu-id="42968-141">**NULL**: 0</span><span class="sxs-lookup"><span data-stu-id="42968-141">**NULL:** 0</span></span><br /><br /> <span data-ttu-id="42968-142">**ZERO:** 255</span><span class="sxs-lookup"><span data-stu-id="42968-142">**ZERO:** 255</span></span><br /><br /> <span data-ttu-id="42968-143">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="42968-143">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="42968-144">**<255:** 255</span><span class="sxs-lookup"><span data-stu-id="42968-144">**<255:** 255</span></span>|  
|`NVARCHAR`|<span data-ttu-id="42968-145">**NULL**: 0</span><span class="sxs-lookup"><span data-stu-id="42968-145">**NULL:** 0</span></span><br /><br /> <span data-ttu-id="42968-146">**Null:** 1</span><span class="sxs-lookup"><span data-stu-id="42968-146">**ZERO:** 1</span></span><br /><br /> <span data-ttu-id="42968-147">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="42968-147">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="42968-148">**<255:** tatsächlicher *len*-Wert</span><span class="sxs-lookup"><span data-stu-id="42968-148">**<255:** actual *len*</span></span>|  
|`NTEXT`|<span data-ttu-id="42968-149">**Null:** -1</span><span class="sxs-lookup"><span data-stu-id="42968-149">**NULL:** -1</span></span><br /><br /> <span data-ttu-id="42968-150">**ZERO:** –1</span><span class="sxs-lookup"><span data-stu-id="42968-150">**ZERO:** -1</span></span><br /><br /> <span data-ttu-id="42968-151">**>= 255:** -1</span><span class="sxs-lookup"><span data-stu-id="42968-151">**>=255:** -1</span></span><br /><br /> <span data-ttu-id="42968-152">**<255:** -1</span><span class="sxs-lookup"><span data-stu-id="42968-152">**<255:** -1</span></span>|  
  
 <span data-ttu-id="42968-153">\* tatsächlicher *len*-Wert = Länge von Mehrbyte-Zeichenfolgen (cch)</span><span class="sxs-lookup"><span data-stu-id="42968-153">\*   actual *len* = Length of multibyte character string (cch)</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="42968-154">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="42968-154">Remarks</span></span>  
 <span data-ttu-id="42968-155">Parameter einer remote gespeicherten Prozedur haben eine tatsächliche und eine maximale Datenlänge.</span><span class="sxs-lookup"><span data-stu-id="42968-155">Each remote stored procedure parameter has an actual and a maximum data length.</span></span> <span data-ttu-id="42968-156">Bei Standarddatentypen fester Länge, die keine Nullwerte zulassen, ist die tatsächliche Länge mit der maximalen Länge identisch.</span><span class="sxs-lookup"><span data-stu-id="42968-156">For standard fixed-length data types that do not allow null values, the actual and maximum lengths are the same.</span></span> <span data-ttu-id="42968-157">Bei Datentypen variabler Länge können die Längen unterschiedlich sein.</span><span class="sxs-lookup"><span data-stu-id="42968-157">For variable-length data types, the lengths can vary.</span></span> <span data-ttu-id="42968-158">Ein als `varchar(30)` deklarierter Parameter kann beispielsweise über Daten verfügen, die nur 10 Byte lang sind.</span><span class="sxs-lookup"><span data-stu-id="42968-158">For example, a parameter declared as `varchar(30)` can have data that is only 10 bytes long.</span></span> <span data-ttu-id="42968-159">Die tatsächliche Länge des Parameters ist 10, die maximale Länge jedoch 30.</span><span class="sxs-lookup"><span data-stu-id="42968-159">The parameter's actual length is 10 and its maximum length is 30.</span></span> <span data-ttu-id="42968-160">Die **srv_paramlen**-Funktion ruft die tatsächliche Datenlänge einer remote gespeicherten Prozedur in Byte ab.</span><span class="sxs-lookup"><span data-stu-id="42968-160">The **srv_paramlen** function gets the actual data length, in bytes, of a remote stored procedure.</span></span> <span data-ttu-id="42968-161">Zum Abrufen der maximalen Datenlänge eines Parameters verwenden Sie **srv_parammaxlen**.</span><span class="sxs-lookup"><span data-stu-id="42968-161">To obtain the maximum data length of a parameter, use **srv_parammaxlen**.</span></span>  
  
 <span data-ttu-id="42968-162">Wenn eine remote gespeicherte Prozedur mit Parametern aufgerufen wird, werden die Parameter entweder mit ihrem Namen oder mit ihrer Position übergeben (unbenannt).</span><span class="sxs-lookup"><span data-stu-id="42968-162">When a remote stored procedure call is made with parameters, the parameters can be passed either by name or by position (unnamed).</span></span> <span data-ttu-id="42968-163">Werden beim Aufruf einer remote gespeicherten Prozedur einige Parameter über ihren Namen und andere über ihre Position übergeben, so tritt ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="42968-163">If the remote stored procedure call is made with some parameters passed by name and some passed by position, an error occurs.</span></span> <span data-ttu-id="42968-164">Der SRV_RPC Handler wird immer noch aufgerufen, wird jedoch so angezeigt, als ob keine Parameter vorhanden wären und **srv_rpcparams** 0 zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="42968-164">The SRV_RPC handler is still called, but it appears as if there were no parameters and **srv_rpcparams** returns 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="42968-165">Sie sollten den Quellcode der erweiterten gespeicherten Prozeduren sorgfältig prüfen, und Sie sollten die kompilierten DLL-Dateien testen, bevor Sie sie auf einem Produktionsserver installieren.</span><span class="sxs-lookup"><span data-stu-id="42968-165">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="42968-166">Weitere Informationen zum Überprüfen und Testen der Sicherheit finden Sie auf dieser [Microsoft-Website](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="42968-166">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42968-167">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="42968-167">See Also</span></span>  
 <span data-ttu-id="42968-168">[srv_paraminfo &#40;API für erweiterte gespeicherte Prozeduren&#41;](srv-paraminfo-extended-stored-procedure-api.md) </span><span class="sxs-lookup"><span data-stu-id="42968-168">[srv_paraminfo &#40;Extended Stored Procedure API&#41;](srv-paraminfo-extended-stored-procedure-api.md) </span></span>  
 [<span data-ttu-id="42968-169">srv_rpcparams (API für erweiterte gespeicherte Prozeduren)</span><span class="sxs-lookup"><span data-stu-id="42968-169">srv_rpcparams &#40;Extended Stored Procedure API&#41;</span></span>](srv-rpcparams-extended-stored-procedure-api.md)  
  
  
