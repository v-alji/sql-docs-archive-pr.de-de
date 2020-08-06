---
title: srv_paramset (API für erweiterte gespeicherte Prozeduren) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_paramset
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_paramset
ms.assetid: 2a509206-a1b8-4b20-b0a2-ef680cef7bd8
author: rothja
ms.author: jroth
ms.openlocfilehash: 9ebe308e5e0c8fc24382582fb71db2f48c77541e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609219"
---
# <a name="srv_paramset-extended-stored-procedure-api"></a><span data-ttu-id="09cba-102">srv_paramset (API für erweiterte gespeicherte Prozeduren)</span><span class="sxs-lookup"><span data-stu-id="09cba-102">srv_paramset (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="09cba-103">Verwenden Sie stattdessen die CLR-Integration.</span><span class="sxs-lookup"><span data-stu-id="09cba-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="09cba-104">Legt den Wert eines Aufrufrückgabeparameters für eine remote gespeicherte Prozedur fest.</span><span class="sxs-lookup"><span data-stu-id="09cba-104">Sets the value of a remote stored procedure call return parameter.</span></span> <span data-ttu-id="09cba-105">Diese Funktion wurde durch die **srv_paramsetoutput**-Funktion ersetzt.</span><span class="sxs-lookup"><span data-stu-id="09cba-105">This function has been superseded by the **srv_paramsetoutput** function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09cba-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="09cba-106">Syntax</span></span>  
  
```  
  
int srv_paramset (  
SRV_PROC *  
srvproc  
,  
int  
n  
,   
void *  
data  
,  
int  
len   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="09cba-107">Argumente</span><span class="sxs-lookup"><span data-stu-id="09cba-107">Arguments</span></span>  
 <span data-ttu-id="09cba-108">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="09cba-108">*srvproc*</span></span>  
 <span data-ttu-id="09cba-109">Ist ein Zeiger auf die SRV_PROC-Struktur, die das Handle für eine bestimmte Clientverbindung ist (in diesem Fall das Handle, das den Aufruf der remote gespeicherten Prozedur erhalten hat).</span><span class="sxs-lookup"><span data-stu-id="09cba-109">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure call).</span></span> <span data-ttu-id="09cba-110">Die Struktur enthält Informationen, mit der die API-Bibliothek für erweiterte gespeicherte Prozeduren die Kommunikation und Daten zwischen der Anwendung und dem Client verwaltet.</span><span class="sxs-lookup"><span data-stu-id="09cba-110">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="09cba-111">*n*</span><span class="sxs-lookup"><span data-stu-id="09cba-111">*n*</span></span>  
 <span data-ttu-id="09cba-112">Gibt die Nummer des festzulegenden Parameters an.</span><span class="sxs-lookup"><span data-stu-id="09cba-112">Indicates the number of the parameter to set.</span></span> <span data-ttu-id="09cba-113">Der erste Parameter ist 1.</span><span class="sxs-lookup"><span data-stu-id="09cba-113">The first parameter is 1.</span></span>  
  
 <span data-ttu-id="09cba-114">*data*</span><span class="sxs-lookup"><span data-stu-id="09cba-114">*data*</span></span>  
 <span data-ttu-id="09cba-115">Ist ein Zeiger auf den Datenwert, der als Rückgabeparameter der remote gespeicherten Prozedur zurück an den Client gesendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="09cba-115">Is a pointer to the data value to be sent back to the client as the remote stored procedure return parameter.</span></span>  
  
 <span data-ttu-id="09cba-116">*Nest*</span><span class="sxs-lookup"><span data-stu-id="09cba-116">*len*</span></span>  
 <span data-ttu-id="09cba-117">Gibt die tatsächliche Länge der zurückzugebenden Daten an.</span><span class="sxs-lookup"><span data-stu-id="09cba-117">Specifies the actual length of the data to be returned.</span></span> <span data-ttu-id="09cba-118">Wenn der Datentyp des Parameters eine konstante Länge aufweist und keine NULL-Werte zulässt (z.B. *srvbit* oder *srvint1*), wird *len* ignoriert.</span><span class="sxs-lookup"><span data-stu-id="09cba-118">If the data type of the parameter is of a constant length and does not allow null values (for example, *srvbit* or *srvint1*), *len* is ignored.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="09cba-119">Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="09cba-119">Returns</span></span>  
 <span data-ttu-id="09cba-120">SUCCEED, wenn der Parameterwert erfolgreich festgelegt wurde; andernfalls FAIL.</span><span class="sxs-lookup"><span data-stu-id="09cba-120">SUCCEED if the parameter value was successfully set; otherwise, FAIL.</span></span> <span data-ttu-id="09cba-121">Es wird FAIL zurückgegeben, wenn es keine aktuelle remote gespeicherte Prozedur oder keinen *n*-ten Parameter für die remote gespeicherte Prozedur gibt, oder wenn der Parameter kein Rückgabeparameter oder das *len*-Argument ungültig ist.</span><span class="sxs-lookup"><span data-stu-id="09cba-121">FAIL is returned when there is no current remote stored procedure, when there is no *n*th remote stored procedure parameter, when the parameter is not a return parameter, and when the *len* argument is not legal.</span></span>  
  
 <span data-ttu-id="09cba-122">Wenn *len* 0 ist, wird NULL zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="09cba-122">If *len*is 0, it returns NULL.</span></span> <span data-ttu-id="09cba-123">*len* auf 0 festzulegen ist die einzige Möglichkeit, NULL an den Client zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="09cba-123">Setting *len* to 0 is the only way to return NULL to the client.</span></span>  
  
 <span data-ttu-id="09cba-124">Diese Funktion gibt die folgenden Werte zurück, wenn der-Parameter einem der- [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Datentypen entspricht.</span><span class="sxs-lookup"><span data-stu-id="09cba-124">This function returns the following values, if the parameter is one of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] data types.</span></span>  
  
|<span data-ttu-id="09cba-125">Neue Datentypen</span><span class="sxs-lookup"><span data-stu-id="09cba-125">New data types</span></span>|<span data-ttu-id="09cba-126">Länge der Rückgabedaten</span><span class="sxs-lookup"><span data-stu-id="09cba-126">Return data length</span></span>|  
|--------------------|------------------------|  
|`BITN`|<span data-ttu-id="09cba-127">\*\*NULL: \*\* *len* = 0, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="09cba-127">**NULL:** *len* = 0, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="09cba-128">**ZERO**: NICHT ZUTREFFEND</span><span class="sxs-lookup"><span data-stu-id="09cba-128">**ZERO:** N/A</span></span><br /><br /> <span data-ttu-id="09cba-129">**>= 255:** nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="09cba-129">**>=255:** N/A</span></span><br /><br /> <span data-ttu-id="09cba-130">**<255:** nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="09cba-130">**<255:** N/A</span></span>|  
|`BIGVARCHAR`|<span data-ttu-id="09cba-131">\*\*NULL: \*\* *len* = 0, data = IG, RET = 1</span><span class="sxs-lookup"><span data-stu-id="09cba-131">**NULL:** *len* = 0, data = IG, RET = 1</span></span><br /><br /> <span data-ttu-id="09cba-132">\*\*ZERO: \*\* *len* = IG, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="09cba-132">**ZERO:** *len* = IG, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="09cba-133">**>=255:** *len* = max8k, data = valid, RET = 0</span><span class="sxs-lookup"><span data-stu-id="09cba-133">**>=255:** *len* = max8k, data = valid, RET = 0</span></span><br /><br /> <span data-ttu-id="09cba-134">**<255:** *len* = <8k, data = valid, RET = 1</span><span class="sxs-lookup"><span data-stu-id="09cba-134">**<255:** *len* = <8k, data = valid, RET = 1</span></span>|  
|`BIGCHAR`|<span data-ttu-id="09cba-135">\*\*NULL: \*\* *len* = 0, data = IG, RET = 1</span><span class="sxs-lookup"><span data-stu-id="09cba-135">**NULL:** *len* = 0, data = IG, RET = 1</span></span><br /><br /> <span data-ttu-id="09cba-136">\*\*ZERO: \*\* *len* = IG, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="09cba-136">**ZERO:** *len* = IG, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="09cba-137">**>=255:** *len* = max8k, data = valid, RET = 0</span><span class="sxs-lookup"><span data-stu-id="09cba-137">**>=255:** *len* = max8k, data = valid, RET = 0</span></span><br /><br /> <span data-ttu-id="09cba-138">**<255:** *len* = <8k, data = valid, RET = 1</span><span class="sxs-lookup"><span data-stu-id="09cba-138">**<255:** *len* = <8k, data = valid, RET = 1</span></span>|  
|`BIGBINARY`|<span data-ttu-id="09cba-139">\*\*NULL: \*\* *len* = 0, data = IG, RET = 1</span><span class="sxs-lookup"><span data-stu-id="09cba-139">**NULL:** *len* = 0, data = IG, RET = 1</span></span><br /><br /> <span data-ttu-id="09cba-140">\*\*ZERO: \*\* *len* = IG, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="09cba-140">**ZERO:** *len* = IG, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="09cba-141">**>=255:** *len* = max8k, data = valid, RET = 0</span><span class="sxs-lookup"><span data-stu-id="09cba-141">**>=255:** *len* = max8k, data = valid, RET = 0</span></span><br /><br /> <span data-ttu-id="09cba-142">**<255:** *len* = <8k, data = valid, RET = 1</span><span class="sxs-lookup"><span data-stu-id="09cba-142">**<255:** *len* = <8k, data = valid, RET = 1</span></span>|  
|`BIGVARBINARY`|<span data-ttu-id="09cba-143">\*\*NULL: \*\* *len* = 0, data = IG, RET = 1</span><span class="sxs-lookup"><span data-stu-id="09cba-143">**NULL:** *len* = 0, data = IG, RET = 1</span></span><br /><br /> <span data-ttu-id="09cba-144">\*\*ZERO: \*\* *len* = IG, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="09cba-144">**ZERO:** *len* = IG, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="09cba-145">**>=255:** *len* = max8k, data = valid, RET = 0</span><span class="sxs-lookup"><span data-stu-id="09cba-145">**>=255:** *len* = max8k, data = valid, RET = 0</span></span><br /><br /> <span data-ttu-id="09cba-146">**<255:** *len* = <8k, data = valid, RET = 1</span><span class="sxs-lookup"><span data-stu-id="09cba-146">**<255:** *len* = <8k, data = valid, RET = 1</span></span>|  
|<span data-ttu-id="09cba-147">NCHAR</span><span class="sxs-lookup"><span data-stu-id="09cba-147">NCHAR</span></span>|<span data-ttu-id="09cba-148">\*\*NULL: \*\* *len* = 0, data = IG, RET = 1</span><span class="sxs-lookup"><span data-stu-id="09cba-148">**NULL:** *len* = 0, data = IG, RET = 1</span></span><br /><br /> <span data-ttu-id="09cba-149">\*\*ZERO: \*\* *len* = IG, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="09cba-149">**ZERO:** *len* = IG, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="09cba-150">**>=255:** *len* = max8k, data = valid, RET = 0</span><span class="sxs-lookup"><span data-stu-id="09cba-150">**>=255:** *len* = max8k, data = valid, RET = 0</span></span><br /><br /> <span data-ttu-id="09cba-151">**<255:** *len* = <8k, data = valid, RET = 1</span><span class="sxs-lookup"><span data-stu-id="09cba-151">**<255:** *len* = <8k, data = valid, RET = 1</span></span>|  
|<span data-ttu-id="09cba-152">NVARCHAR</span><span class="sxs-lookup"><span data-stu-id="09cba-152">NVARCHAR</span></span>|<span data-ttu-id="09cba-153">\*\*NULL: \*\* *len* = 0, data = IG, RET = 1</span><span class="sxs-lookup"><span data-stu-id="09cba-153">**NULL:** *len* = 0, data = IG, RET = 1</span></span><br /><br /> <span data-ttu-id="09cba-154">\*\*ZERO: \*\* *len* = IG, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="09cba-154">**ZERO:** *len* = IG, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="09cba-155">**>=255:** *len* = max8k, data = valid, RET = 0</span><span class="sxs-lookup"><span data-stu-id="09cba-155">**>=255:** *len* = max8k, data = valid, RET = 0</span></span><br /><br /> <span data-ttu-id="09cba-156">**<255:** *len* = <8k, data = valid, RET = 1</span><span class="sxs-lookup"><span data-stu-id="09cba-156">**<255:** *len* = <8k, data = valid, RET = 1</span></span>|  
|`NTEXT`|<span data-ttu-id="09cba-157">\*\*NULL: \*\* *len* = IG, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="09cba-157">**NULL:** *len* = IG, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="09cba-158">\*\*ZERO: \*\* *len* = IG, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="09cba-158">**ZERO:** *len* = IG, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="09cba-159">**>=255:** *len* = IG, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="09cba-159">**>=255:** *len* = IG, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="09cba-160">\*\* \< 255:\*\* *len* = IG, Data = IG, ret = 0</span><span class="sxs-lookup"><span data-stu-id="09cba-160">**\<255:** *len* = IG, data = IG, RET = 0</span></span>|  
|<span data-ttu-id="09cba-161">RET = Rückgabewert von srv_paramset</span><span class="sxs-lookup"><span data-stu-id="09cba-161">RET = Return value of srv_paramset</span></span>||  
|<span data-ttu-id="09cba-162">IG = Wert wird ignoriert</span><span class="sxs-lookup"><span data-stu-id="09cba-162">IG = Value will be ignored</span></span>||  
|<span data-ttu-id="09cba-163">valid = ein beliebiger gültiger Zeiger auf Daten</span><span class="sxs-lookup"><span data-stu-id="09cba-163">valid = Any valid pointer to data</span></span>||  
  
## <a name="remarks"></a><span data-ttu-id="09cba-164">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="09cba-164">Remarks</span></span>  
 <span data-ttu-id="09cba-165">Parameter enthalten die zwischen Clients und der Anwendung mit remote gespeicherten Prozeduren übergebenen Daten.</span><span class="sxs-lookup"><span data-stu-id="09cba-165">Parameters contain data passed between clients and the application with remote stored procedures.</span></span> <span data-ttu-id="09cba-166">Der Client kann bestimmte Parameter als Rückgabeparameter angeben.</span><span class="sxs-lookup"><span data-stu-id="09cba-166">The client can specify certain parameters as return parameters.</span></span> <span data-ttu-id="09cba-167">Diese Rückgabeparameter können Werte enthalten, die die Open Data Services-Anwendung wieder an den Client übergibt.</span><span class="sxs-lookup"><span data-stu-id="09cba-167">These return parameters can contain values that the Open Data Services server application passes back to the client.</span></span> <span data-ttu-id="09cba-168">Die Verwendung von Rückgabeparametern entspricht der Übergabe von Parametern nach Verweis.</span><span class="sxs-lookup"><span data-stu-id="09cba-168">Using return parameters is analogous to passing parameters by reference.</span></span>  
  
 <span data-ttu-id="09cba-169">Sie können den Rückgabewert für einen Parameter nicht festlegen, der nicht als Rückgabeparameter aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="09cba-169">You cannot set the return value for a parameter that wasn't invoked as a return parameter.</span></span> <span data-ttu-id="09cba-170">Verwenden Sie **srv_paramstatus**, um zu bestimmen, wie der Parameter aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="09cba-170">You can use **srv_paramstatus** to determine how the parameter was invoked.</span></span>  
  
 <span data-ttu-id="09cba-171">Diese Funktion legt zwar den Rückgabewert für einen Parameter fest, sendet den Rückgabewert jedoch nicht an den Client.</span><span class="sxs-lookup"><span data-stu-id="09cba-171">This function sets the return value for a parameter but it does not actually send the return value to the client.</span></span> <span data-ttu-id="09cba-172">Alle Rückgabeparameter werden unabhängig davon, ob die Rückgabewerte mit **srv_paramset** festgelegt wurden, automatisch an den Client gesendet, wenn **srv_senddone** mit dem festgelegtem Statusflag „SRV_DONE_FINAL“ aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="09cba-172">All return parameters, whether their return values have been set with **srv_paramset** or not, are automatically sent to the client when **srv_senddone** is called with the status flag SRV_DONE_FINAL set.</span></span>  
  
 <span data-ttu-id="09cba-173">Wenn eine remote gespeicherte Prozedur mit Parametern aufgerufen wird, werden die Parameter entweder mit ihrem Namen oder mit ihrer Position übergeben (unbenannt).</span><span class="sxs-lookup"><span data-stu-id="09cba-173">When a remote stored procedure call is made with parameters, the parameters can be passed either by name or by position (unnamed).</span></span> <span data-ttu-id="09cba-174">Werden beim Aufruf einer remote gespeicherten Prozedur einige Parameter über ihren Namen und andere über ihre Position übergeben, so tritt ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="09cba-174">If the remote stored procedure call is made with some parameters passed by name and some passed by position, an error occurs.</span></span> <span data-ttu-id="09cba-175">Der SRV_RPC-Handler wird trotzdem aufgerufen, scheinbar jedoch ohne Parameter, und **srv_rpcparams** gibt 0 (null) zurück.</span><span class="sxs-lookup"><span data-stu-id="09cba-175">The SRV_RPC handler is still called, but it appears as if there were no parameters, and **srv_rpcparams** returns 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="09cba-176">Sie sollten den Quellcode der erweiterten gespeicherten Prozeduren sorgfältig prüfen, und Sie sollten die kompilierten DLL-Dateien testen, bevor Sie sie auf einem Produktionsserver installieren.</span><span class="sxs-lookup"><span data-stu-id="09cba-176">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="09cba-177">Weitere Informationen zum Überprüfen und Testen der Sicherheit finden Sie auf dieser [Microsoft-Website](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="09cba-177">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09cba-178">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="09cba-178">See Also</span></span>  
 [<span data-ttu-id="09cba-179">srv_paramsetoutput (API für erweiterte gespeicherte Prozeduren)</span><span class="sxs-lookup"><span data-stu-id="09cba-179">srv_paramsetoutput &#40;Extended Stored Procedure API&#41;</span></span>](srv-paramsetoutput-extended-stored-procedure-api.md)  
  
  
