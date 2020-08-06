---
title: srv_paramdata (API für erweiterte gespeicherte Prozeduren) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_paramdata
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_paramdata
ms.assetid: 3104514d-b404-47c9-b6d7-928106384874
author: rothja
ms.author: jroth
ms.openlocfilehash: 092ca5b811a12c3e6b199a6041ce6e4f8e02f4b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620391"
---
# <a name="srv_paramdata-extended-stored-procedure-api"></a><span data-ttu-id="46bca-102">srv_paramdata (API für erweiterte gespeicherte Prozeduren)</span><span class="sxs-lookup"><span data-stu-id="46bca-102">srv_paramdata (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="46bca-103">Verwenden Sie stattdessen die CLR-Integration.</span><span class="sxs-lookup"><span data-stu-id="46bca-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="46bca-104">Gibt den Wert eines Aufrufparameters für eine remote gespeicherte Prozedur zurück.</span><span class="sxs-lookup"><span data-stu-id="46bca-104">Returns the value of a remote stored procedure call parameter.</span></span> <span data-ttu-id="46bca-105">Diese Funktion wurde durch die **srv_paraminfo**-Funktion ersetzt.</span><span class="sxs-lookup"><span data-stu-id="46bca-105">This function has been superseded by the **srv_paraminfo** function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46bca-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="46bca-106">Syntax</span></span>  
  
```  
  
void * srv_paramdata (  
SRV_PROC *  
srvproc  
,  
int  
n   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="46bca-107">Argumente</span><span class="sxs-lookup"><span data-stu-id="46bca-107">Arguments</span></span>  
 <span data-ttu-id="46bca-108">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="46bca-108">*srvproc*</span></span>  
 <span data-ttu-id="46bca-109">Ist ein Zeiger auf die SRV_PROC-Struktur, die das Handle für eine bestimmte Clientverbindung ist (in diesem Fall das Handle, das den Aufruf der remote gespeicherten Prozedur erhalten hat).</span><span class="sxs-lookup"><span data-stu-id="46bca-109">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure call).</span></span> <span data-ttu-id="46bca-110">Die Struktur enthält Informationen, mit der die Bibliothek für erweiterte gespeicherte Prozeduren die Daten und Kommunikation zwischen der Anwendung und dem Client verwaltet.</span><span class="sxs-lookup"><span data-stu-id="46bca-110">The structure contains information the Extended Stored Procedure library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="46bca-111">*n*</span><span class="sxs-lookup"><span data-stu-id="46bca-111">*n*</span></span>  
 <span data-ttu-id="46bca-112">Entspricht der Nummer des Parameters.</span><span class="sxs-lookup"><span data-stu-id="46bca-112">Is the number of the parameter.</span></span> <span data-ttu-id="46bca-113">Die erste Parameternummer ist 1.</span><span class="sxs-lookup"><span data-stu-id="46bca-113">The first parameter is number 1.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="46bca-114">Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="46bca-114">Returns</span></span>  
 <span data-ttu-id="46bca-115">Ein Zeiger auf den Parameterwert.</span><span class="sxs-lookup"><span data-stu-id="46bca-115">A pointer to the parameter value.</span></span> <span data-ttu-id="46bca-116">Ist der *n*-te Parameter NULL, ist kein *n*-ter Parameter vorhanden, oder ist keine remote gespeicherte Prozedur vorhanden, wird NULL zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="46bca-116">If the *n*th parameter is NULL, there is no *n*th parameter, or there is no remote stored procedure, returns NULL.</span></span> <span data-ttu-id="46bca-117">Wenn der Parameterwert eine Zeichenfolge ist, kann er nicht NULL-terminiert sein.</span><span class="sxs-lookup"><span data-stu-id="46bca-117">If the parameter value is a string, it might not be null-terminated.</span></span> <span data-ttu-id="46bca-118">Verwenden Sie **srv_paramlen**, um die Länge der Zeichenfolge zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="46bca-118">Use **srv_paramlen** to determine the length of the string.</span></span>  
  
 <span data-ttu-id="46bca-119">Diese Funktion gibt die folgenden Werte zurück, wenn der-Parameter einem der- [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Datentypen entspricht.</span><span class="sxs-lookup"><span data-stu-id="46bca-119">This function returns the following values, if the parameter is one of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types.</span></span> <span data-ttu-id="46bca-120">Zeigerdaten umfassen, ob der Zeiger für den Datentyp gültig (VP), NULL oder nicht anwendbar (N/V) ist, sowie den Inhalt der Daten, auf die der Zeiger verweist.</span><span class="sxs-lookup"><span data-stu-id="46bca-120">Pointer data includes whether the pointer for the data type is valid (VP), NULL, or not applicable (N/A), and the contents of the data pointed to.</span></span>  
  
|<span data-ttu-id="46bca-121">Neue Datentypen</span><span class="sxs-lookup"><span data-stu-id="46bca-121">New data types</span></span>|<span data-ttu-id="46bca-122">Länge der Eingabedaten</span><span class="sxs-lookup"><span data-stu-id="46bca-122">Input data length</span></span>|  
|--------------------|-----------------------|  
|<span data-ttu-id="46bca-123">BITN</span><span class="sxs-lookup"><span data-stu-id="46bca-123">BITN</span></span>|<span data-ttu-id="46bca-124">**NULL**: VP, NULL</span><span class="sxs-lookup"><span data-stu-id="46bca-124">**NULL:** VP, NULL</span></span><br /><br /> <span data-ttu-id="46bca-125">**ZERO**: VP, NULL</span><span class="sxs-lookup"><span data-stu-id="46bca-125">**ZERO:** VP, NULL</span></span><br /><br /> <span data-ttu-id="46bca-126">**>= 255:** nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="46bca-126">**>=255:** N/A</span></span><br /><br /> <span data-ttu-id="46bca-127">**<255:** nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="46bca-127">**<255:** N/A</span></span>|  
|<span data-ttu-id="46bca-128">BIGVARCHAR</span><span class="sxs-lookup"><span data-stu-id="46bca-128">BIGVARCHAR</span></span>|<span data-ttu-id="46bca-129">**NULL**: NULL, NICHT ZUTREFFEND</span><span class="sxs-lookup"><span data-stu-id="46bca-129">**NULL:** NULL, N/A</span></span><br /><br /> <span data-ttu-id="46bca-130">**ZERO**: VP, NULL</span><span class="sxs-lookup"><span data-stu-id="46bca-130">**ZERO:** VP, NULL</span></span><br /><br /> <span data-ttu-id="46bca-131">**>=255:** VP, 255 Zeichen</span><span class="sxs-lookup"><span data-stu-id="46bca-131">**>=255:** VP, 255 chars</span></span><br /><br /> <span data-ttu-id="46bca-132">**<255:** VP, tatsächliche Daten</span><span class="sxs-lookup"><span data-stu-id="46bca-132">**<255:** VP, actual data</span></span>|  
|<span data-ttu-id="46bca-133">BIGCHAR</span><span class="sxs-lookup"><span data-stu-id="46bca-133">BIGCHAR</span></span>|<span data-ttu-id="46bca-134">**NULL**: NULL, NICHT ZUTREFFEND</span><span class="sxs-lookup"><span data-stu-id="46bca-134">**NULL:** NULL, N/A</span></span><br /><br /> <span data-ttu-id="46bca-135">**ZERO:** VP, 255 Leerräume</span><span class="sxs-lookup"><span data-stu-id="46bca-135">**ZERO:** VP, 255 spaces</span></span><br /><br /> <span data-ttu-id="46bca-136">**>=255:** VP, 255 Zeichen</span><span class="sxs-lookup"><span data-stu-id="46bca-136">**>=255:** VP, 255 chars</span></span><br /><br /> <span data-ttu-id="46bca-137">**<255:** VP, tatsächliche Daten und Auffüllung (bis 255)</span><span class="sxs-lookup"><span data-stu-id="46bca-137">**<255:** VP, actual data + padding (up to 255)</span></span>|  
|<span data-ttu-id="46bca-138">BIGBINARY</span><span class="sxs-lookup"><span data-stu-id="46bca-138">BIGBINARY</span></span>|<span data-ttu-id="46bca-139">**NULL**: NULL, NICHT ZUTREFFEND</span><span class="sxs-lookup"><span data-stu-id="46bca-139">**NULL:** NULL, N/A</span></span><br /><br /> <span data-ttu-id="46bca-140">**ZERO:** VP, 255 0x00</span><span class="sxs-lookup"><span data-stu-id="46bca-140">**ZERO:** VP, 255 0x00</span></span><br /><br /> <span data-ttu-id="46bca-141">**>=255:** VP, 255 Byte</span><span class="sxs-lookup"><span data-stu-id="46bca-141">**>=255:** VP, 255 bytes</span></span><br /><br /> <span data-ttu-id="46bca-142">**<255:** VP, tatsächliche Daten und Auffüllung (bis 255)</span><span class="sxs-lookup"><span data-stu-id="46bca-142">**<255:** VP, actual data + padding (up to 255)</span></span>|  
|<span data-ttu-id="46bca-143">BIGVARBINARY</span><span class="sxs-lookup"><span data-stu-id="46bca-143">BIGVARBINARY</span></span>|<span data-ttu-id="46bca-144">**NULL**: NULL, NICHT ZUTREFFEND</span><span class="sxs-lookup"><span data-stu-id="46bca-144">**NULL:** NULL, N/A</span></span><br /><br /> <span data-ttu-id="46bca-145">**ZERO**: VP, 0x00</span><span class="sxs-lookup"><span data-stu-id="46bca-145">**ZERO:** VP, 0x00</span></span><br /><br /> <span data-ttu-id="46bca-146">**>=255:** VP, 255 Byte</span><span class="sxs-lookup"><span data-stu-id="46bca-146">**>=255:** VP, 255 bytes</span></span><br /><br /> <span data-ttu-id="46bca-147">**<255:** VP, tatsächliche Daten</span><span class="sxs-lookup"><span data-stu-id="46bca-147">**<255:** VP, actual data</span></span>|  
|<span data-ttu-id="46bca-148">NCHAR</span><span class="sxs-lookup"><span data-stu-id="46bca-148">NCHAR</span></span>|<span data-ttu-id="46bca-149">**NULL**: NULL, NICHT ZUTREFFEND</span><span class="sxs-lookup"><span data-stu-id="46bca-149">**NULL:** NULL, N/A</span></span><br /><br /> <span data-ttu-id="46bca-150">**ZERO:** VP, 255 Leerräume</span><span class="sxs-lookup"><span data-stu-id="46bca-150">**ZERO:** VP, 255 spaces</span></span><br /><br /> <span data-ttu-id="46bca-151">**>=255:** VP, 255 Zeichen</span><span class="sxs-lookup"><span data-stu-id="46bca-151">**>=255:** VP, 255 chars</span></span><br /><br /> <span data-ttu-id="46bca-152">**<255:** VP, tatsächliche Daten und Auffüllung (bis 255)</span><span class="sxs-lookup"><span data-stu-id="46bca-152">**<255:** VP, actual data + padding (up to 255)</span></span>|  
|<span data-ttu-id="46bca-153">NVARCHAR</span><span class="sxs-lookup"><span data-stu-id="46bca-153">NVARCHAR</span></span>|<span data-ttu-id="46bca-154">**NULL**: NULL, NICHT ZUTREFFEND</span><span class="sxs-lookup"><span data-stu-id="46bca-154">**NULL:** NULL, N/A</span></span><br /><br /> <span data-ttu-id="46bca-155">**ZERO**: VP, NULL</span><span class="sxs-lookup"><span data-stu-id="46bca-155">**ZERO:** VP, NULL</span></span><br /><br /> <span data-ttu-id="46bca-156">**>=255:** VP, 255 Zeichen</span><span class="sxs-lookup"><span data-stu-id="46bca-156">**>=255:** VP, 255 chars</span></span><br /><br /> <span data-ttu-id="46bca-157">**<255:** VP, tatsächliche Daten</span><span class="sxs-lookup"><span data-stu-id="46bca-157">**<255:** VP, actual data</span></span>|  
|<span data-ttu-id="46bca-158">NTEXT</span><span class="sxs-lookup"><span data-stu-id="46bca-158">NTEXT</span></span>|<span data-ttu-id="46bca-159">**NULL**: NICHT ZUTREFFEND</span><span class="sxs-lookup"><span data-stu-id="46bca-159">**NULL:** N/A</span></span><br /><br /> <span data-ttu-id="46bca-160">**ZERO**: NICHT ZUTREFFEND</span><span class="sxs-lookup"><span data-stu-id="46bca-160">**ZERO:** N/A</span></span><br /><br /> <span data-ttu-id="46bca-161">**>= 255:** nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="46bca-161">**>=255:** N/A</span></span><br /><br /> <span data-ttu-id="46bca-162">\*\* \< 255:\*\* N/v</span><span class="sxs-lookup"><span data-stu-id="46bca-162">**\<255:** N/A</span></span>|  
  
 <span data-ttu-id="46bca-163">\* Daten enden nicht auf NULL. Es wird keine Warnung für abgeschnittene Daten, die größer als 255 Zeichen sind, ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="46bca-163">\*   data is not null-terminated; no warning is issued on truncation for data >255 characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="46bca-164">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="46bca-164">Remarks</span></span>  
 <span data-ttu-id="46bca-165">Wenn Sie den Parameternamen wissen, können Sie **srv_paramnumber** verwenden, um die Parameternummer abzurufen.</span><span class="sxs-lookup"><span data-stu-id="46bca-165">If you know the parameter name, you can use **srv_paramnumber** to get the parameter number.</span></span> <span data-ttu-id="46bca-166">Verwenden Sie **srv_paramlen**, um zu bestimmen, ob ein Parameter NULL ist.</span><span class="sxs-lookup"><span data-stu-id="46bca-166">To determine whether a parameter is NULL, use **srv_paramlen**.</span></span>  
  
 <span data-ttu-id="46bca-167">Wenn eine remote gespeicherte Prozedur mit Parametern aufgerufen wird, werden die Parameter mit ihrem Namen oder mit ihrer Position übergeben (unbenannt).</span><span class="sxs-lookup"><span data-stu-id="46bca-167">When a remote stored procedure call is made with parameters, the parameters can be passed by name or by position (unnamed).</span></span> <span data-ttu-id="46bca-168">Werden beim Aufruf einer remote gespeicherten Prozedur einige Parameter über ihren Namen und andere über ihre Position übergeben, so tritt ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="46bca-168">If the remote stored procedure call is made with some parameters passed by name and some passed by position, an error occurs.</span></span> <span data-ttu-id="46bca-169">Bei Auftreten eines Fehlers wird der SRV_RPC-Handler trotzdem aufgerufen, doch es sind scheinbar keine Parameter vorhanden und **srv_rpcparams** gibt 0 zurück.</span><span class="sxs-lookup"><span data-stu-id="46bca-169">If an error occurs, the SRV_RPC handler is still called, but it appears as if there were no parameters and **srv_rpcparams** returns 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="46bca-170">Sie sollten den Quellcode der erweiterten gespeicherten Prozeduren sorgfältig prüfen, und Sie sollten die kompilierten DLL-Dateien testen, bevor Sie sie auf einem Produktionsserver installieren.</span><span class="sxs-lookup"><span data-stu-id="46bca-170">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="46bca-171">Weitere Informationen zum Überprüfen und Testen der Sicherheit finden Sie auf dieser [Microsoft-Website](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="46bca-171">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46bca-172">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="46bca-172">See Also</span></span>  
 [<span data-ttu-id="46bca-173">srv_rpcparams (API für erweiterte gespeicherte Prozeduren)</span><span class="sxs-lookup"><span data-stu-id="46bca-173">srv_rpcparams &#40;Extended Stored Procedure API&#41;</span></span>](srv-rpcparams-extended-stored-procedure-api.md)  
  
  
