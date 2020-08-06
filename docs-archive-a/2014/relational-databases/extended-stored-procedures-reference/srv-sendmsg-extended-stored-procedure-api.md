---
title: srv_sendmsg (API für die erweiterte gespeicherte Prozedur) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_sendmsg
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_sendmsg
ms.assetid: efcb50b9-f8ff-4121-bf67-05830171b928
author: rothja
ms.author: jroth
ms.openlocfilehash: 0821ad88f48313cfadea634a489def9b242a49f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726914"
---
# <a name="srv_sendmsg-extended-stored-procedure-api"></a><span data-ttu-id="f9722-102">srv_sendmsg (API für erweiterte gespeicherte Prozeduren)</span><span class="sxs-lookup"><span data-stu-id="f9722-102">srv_sendmsg (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="f9722-103">Verwenden Sie stattdessen die CLR-Integration.</span><span class="sxs-lookup"><span data-stu-id="f9722-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="f9722-104">Sendet eine Meldung an den Client.</span><span class="sxs-lookup"><span data-stu-id="f9722-104">Sends a message to the client.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9722-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f9722-105">Syntax</span></span>  
  
```  
  
int srv_sendmsg (  
SRV_PROC *  
srvproc  
,  
int  
msgtype  
,  
DBINT  
msgnum  
,  
DBTINYINT  
class  
,   
DBTINYINT  
state  
,  
DBCHAR *  
rpcname  
,  
int   
rpcnamelen  
,  
DBUSMALLINT  
linenum  
,  
DBCHAR *  
message  
,  
int  
msglen   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="f9722-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="f9722-106">Arguments</span></span>  
 <span data-ttu-id="f9722-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="f9722-107">*srvproc*</span></span>  
 <span data-ttu-id="f9722-108">Ein Zeiger auf die SRV_PROC-Struktur, die das Handle für eine bestimmte Clientverbindung ist (in diesem Fall das Handle, das die Sprachanforderung erhalten hat).</span><span class="sxs-lookup"><span data-stu-id="f9722-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the language request).</span></span> <span data-ttu-id="f9722-109">Die Struktur enthält Informationen, mit der die API-Bibliothek für erweiterte gespeicherte Prozeduren die Kommunikation und Daten zwischen der Anwendung und dem Client verwaltet.</span><span class="sxs-lookup"><span data-stu-id="f9722-109">The structure contains information that the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="f9722-110">*msgtype*</span><span class="sxs-lookup"><span data-stu-id="f9722-110">*msgtype*</span></span>  
 <span data-ttu-id="f9722-111">Ist entweder SRV_MSG_INFO oder SRV_MSG_ERROR, je nachdem, ob der Server eine Informations- oder Fehlermeldung sendet.</span><span class="sxs-lookup"><span data-stu-id="f9722-111">Is either SRV_MSG_INFO or SRV_MSG_ERROR, depending on whether the server is sending an informational or error message.</span></span>  
  
 <span data-ttu-id="f9722-112">*msgnum*</span><span class="sxs-lookup"><span data-stu-id="f9722-112">*msgnum*</span></span>  
 <span data-ttu-id="f9722-113">Eine 4-Byte-Meldungsnummer.</span><span class="sxs-lookup"><span data-stu-id="f9722-113">Is a 4-byte message number.</span></span>  
  
 <span data-ttu-id="f9722-114">*class*</span><span class="sxs-lookup"><span data-stu-id="f9722-114">*class*</span></span>  
 <span data-ttu-id="f9722-115">Gibt den Fehlerschweregrad an.</span><span class="sxs-lookup"><span data-stu-id="f9722-115">Specifies the error severity.</span></span> <span data-ttu-id="f9722-116">Ein Schweregrad kleiner oder gleich 10 wird als Informationsmeldung betrachtet.</span><span class="sxs-lookup"><span data-stu-id="f9722-116">A severity less than or equal to 10 is considered an informational message.</span></span>  
  
 <span data-ttu-id="f9722-117">*state*</span><span class="sxs-lookup"><span data-stu-id="f9722-117">*state*</span></span>  
 <span data-ttu-id="f9722-118">Stellt die Fehlerzustandsnummer für die aktuelle Meldung bereit.</span><span class="sxs-lookup"><span data-stu-id="f9722-118">Provides the error state number for the current message.</span></span> <span data-ttu-id="f9722-119">Die Fehlerzustandsnummer enthält Informationen über den Fehlerkontext.</span><span class="sxs-lookup"><span data-stu-id="f9722-119">The error state number provides information about the context of the error.</span></span> <span data-ttu-id="f9722-120">Gültige Zustandsnummern liegen zwischen 0 und 255.</span><span class="sxs-lookup"><span data-stu-id="f9722-120">Valid state numbers are from 0 through 255.</span></span>  
  
 <span data-ttu-id="f9722-121">*rpcname*</span><span class="sxs-lookup"><span data-stu-id="f9722-121">*rpcname*</span></span>  
 <span data-ttu-id="f9722-122">Wird derzeit nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f9722-122">Is currently not supported.</span></span>  
  
 <span data-ttu-id="f9722-123">*rpcnamelen*</span><span class="sxs-lookup"><span data-stu-id="f9722-123">*rpcnamelen*</span></span>  
 <span data-ttu-id="f9722-124">Wird derzeit nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f9722-124">Is currently not supported.</span></span>  
  
 <span data-ttu-id="f9722-125">*linumum*</span><span class="sxs-lookup"><span data-stu-id="f9722-125">*linenum*</span></span>  
 <span data-ttu-id="f9722-126">Die Zeilennummer im Sprachbefehlsbatch, für die die Meldung gilt.</span><span class="sxs-lookup"><span data-stu-id="f9722-126">Is the line number in the language command batch where the message applies.</span></span> <span data-ttu-id="f9722-127">Die Zeilennummern beginnen bei 1.</span><span class="sxs-lookup"><span data-stu-id="f9722-127">Line numbers start at 1.</span></span> <span data-ttu-id="f9722-128">Legen Sie den Wert auf 0 fest, wenn *linenum* nicht für die Meldung gilt.</span><span class="sxs-lookup"><span data-stu-id="f9722-128">If *linenum* does not apply to the message, set to 0.</span></span>  
  
 <span data-ttu-id="f9722-129">*Nachricht*</span><span class="sxs-lookup"><span data-stu-id="f9722-129">*message*</span></span>  
 <span data-ttu-id="f9722-130">Ein Zeiger auf die an den Client zu sendende Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="f9722-130">Is a pointer to the character string to be sent to the client.</span></span>  
  
 <span data-ttu-id="f9722-131">*msglen*</span><span class="sxs-lookup"><span data-stu-id="f9722-131">*msglen*</span></span>  
 <span data-ttu-id="f9722-132">Gibt die Länge von *message*in Byte an.</span><span class="sxs-lookup"><span data-stu-id="f9722-132">Specifies the length, in bytes, of *message*.</span></span> <span data-ttu-id="f9722-133">Wenn *message* NULL-terminiert ist, legen Sie für *msglen* den Wert SRV_NULLTERM fest.</span><span class="sxs-lookup"><span data-stu-id="f9722-133">If *message* is null-terminated, set *msglen* to SRV_NULLTERM.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="f9722-134">Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="f9722-134">Returns</span></span>  
 <span data-ttu-id="f9722-135">SUCCEED oder FAIL</span><span class="sxs-lookup"><span data-stu-id="f9722-135">SUCCEED or FAIL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f9722-136">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="f9722-136">Remarks</span></span>  
 <span data-ttu-id="f9722-137">Diese Funktion sendet Fehler- oder Informationsmeldungen an den Client.</span><span class="sxs-lookup"><span data-stu-id="f9722-137">This function sends error or informational messages to the client.</span></span> <span data-ttu-id="f9722-138">Sie wird für jede zu sendende Meldung einmal aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="f9722-138">It is called once for each message to be sent.</span></span>  
  
 <span data-ttu-id="f9722-139">Mithilfe von **srv_sendmsg** können Meldungen in beliebiger Reihenfolge gesendet werden, bevor oder nachdem alle Zeilen (sofern vorhanden) mit **srv_sendrow**gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="f9722-139">Messages can be sent to the client with **srv_sendmsg** in any order before or after all rows (if any) have been sent with **srv_sendrow**.</span></span> <span data-ttu-id="f9722-140">Ggf. müssen alle Meldungen an den Client gesendet werden, bevor der Abschlussstatus mit **srv_senddone**gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="f9722-140">All messages, if any, must be sent to the client before the completion status is sent with **srv_senddone**.</span></span>  
  
 <span data-ttu-id="f9722-141">Zum Versenden von Meldungen in Unicode verwenden Sie **srv_wsendmsg** anstelle von **srv_sendmsg**.</span><span class="sxs-lookup"><span data-stu-id="f9722-141">To send messages in Unicode, use **srv_wsendmsg** rather than **srv_sendmsg**.</span></span>  
  
 <span data-ttu-id="f9722-142">Weitere Informationen finden Sie unter [Unicode Data and Server Code Pages (Unicode-Daten und Server Codepages)](../extended-stored-procedures-programming/unicode-data-and-server-code-pages.md).</span><span class="sxs-lookup"><span data-stu-id="f9722-142">For more information see [Unicode Data and Server Code Pages](../extended-stored-procedures-programming/unicode-data-and-server-code-pages.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f9722-143">Sie sollten den Quellcode der erweiterten gespeicherten Prozeduren sorgfältig prüfen, und Sie sollten die kompilierten DLL-Dateien testen, bevor Sie sie auf einem Produktionsserver installieren.</span><span class="sxs-lookup"><span data-stu-id="f9722-143">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="f9722-144">Weitere Informationen zum Überprüfen und Testen der Sicherheit finden Sie auf dieser [Microsoft-Website](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="f9722-144">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
