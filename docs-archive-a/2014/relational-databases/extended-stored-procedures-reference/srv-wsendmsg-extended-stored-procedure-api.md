---
title: „srv_wsendmsg“ (API für die erweiterte gespeicherte Prozedur) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_wsendmsg
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_wsendmsg
ms.assetid: f2153076-32c9-4a52-8e1b-fc9618153543
author: rothja
ms.author: jroth
ms.openlocfilehash: 4cc915cce0befccb5c5af58e703c11b750af855b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725786"
---
# <a name="srv_wsendmsg-extended-stored-procedure-api"></a><span data-ttu-id="f8718-102">srv_wsendmsg (API für erweiterte gespeicherte Prozeduren)</span><span class="sxs-lookup"><span data-stu-id="f8718-102">srv_wsendmsg (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="f8718-103">Verwenden Sie stattdessen die CLR-Integration.</span><span class="sxs-lookup"><span data-stu-id="f8718-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="f8718-104">Sendet eine Unicode-Meldung an den Client.</span><span class="sxs-lookup"><span data-stu-id="f8718-104">Sends a Unicode message to the client.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8718-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f8718-105">Syntax</span></span>  
  
```  
  
int srv_wsendmsg(SRV_PROC *   
srvproc  
, int   
msgnum  
, int   
severity  
, WCHAR *   
message  
, int   
msglen  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="f8718-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="f8718-106">Arguments</span></span>  
 <span data-ttu-id="f8718-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="f8718-107">*srvproc*</span></span>  
 <span data-ttu-id="f8718-108">Ein Zeiger auf die SRV_PROC-Struktur, die das Handle für eine bestimmte Clientverbindung ist.</span><span class="sxs-lookup"><span data-stu-id="f8718-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection.</span></span> <span data-ttu-id="f8718-109">Die Struktur enthält Informationen, mit der die API-Bibliothek für erweiterte gespeicherte Prozeduren die Kommunikation und Daten zwischen der Anwendung und dem Client verwaltet.</span><span class="sxs-lookup"><span data-stu-id="f8718-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="f8718-110">*Msgnum*</span><span class="sxs-lookup"><span data-stu-id="f8718-110">*Msgnum*</span></span>  
 <span data-ttu-id="f8718-111">Eine 4-Byte-Meldungsnummer.</span><span class="sxs-lookup"><span data-stu-id="f8718-111">Is a 4-byte message number.</span></span>  
  
 <span data-ttu-id="f8718-112">*Severity*</span><span class="sxs-lookup"><span data-stu-id="f8718-112">*Severity*</span></span>  
 <span data-ttu-id="f8718-113">Gibt den Schweregrad des Fehlers an.</span><span class="sxs-lookup"><span data-stu-id="f8718-113">Specifies the severity of the error.</span></span> <span data-ttu-id="f8718-114">Ein Schweregrad kleiner oder gleich 10 wird als Informationsmeldung betrachtet, bei einem höheren Wert handelt es sich um einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="f8718-114">A severity less than or equal to 10 is considered an informational message; otherwise, it is an error.</span></span>  
  
 <span data-ttu-id="f8718-115">*Nachricht*</span><span class="sxs-lookup"><span data-stu-id="f8718-115">*message*</span></span>  
 <span data-ttu-id="f8718-116">Ein Zeiger auf die an den Client zu sendende Unicode-Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="f8718-116">Is a pointer to a Unicode string to be sent to the client.</span></span>  
  
 <span data-ttu-id="f8718-117">*msglen*</span><span class="sxs-lookup"><span data-stu-id="f8718-117">*msglen*</span></span>  
 <span data-ttu-id="f8718-118">Gibt die Länge von *message*in Zeichen an.</span><span class="sxs-lookup"><span data-stu-id="f8718-118">Specifies the length, in characters, of *message*.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="f8718-119">Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="f8718-119">Returns</span></span>  
 <span data-ttu-id="f8718-120">SUCCEED oder FAIL.</span><span class="sxs-lookup"><span data-stu-id="f8718-120">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8718-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="f8718-121">Remarks</span></span>  
 <span data-ttu-id="f8718-122">Verwenden Sie diese Funktion, um Meldungen in Unicode zu senden.</span><span class="sxs-lookup"><span data-stu-id="f8718-122">Use this function to send messages in Unicode.</span></span> <span data-ttu-id="f8718-123">Sie ähnelt **srv_sendmsg**, jedoch handelt es sich bei der gesendeten Meldung um eine WCHAR-Zeichenfolge und nicht um eine Zeichenfolge des Typs DBCHAR.</span><span class="sxs-lookup"><span data-stu-id="f8718-123">It is similar to **srv_sendmsg**, but the message it sends is a WCHAR string rather than type DBCHAR string.</span></span> <span data-ttu-id="f8718-124">Beachten Sie, dass die Länge der Meldung in Zeichen und nicht in Byte angegeben wird und dass *msglen* niemals SRV_NULLTERM entspricht.</span><span class="sxs-lookup"><span data-stu-id="f8718-124">Note that message length is reported in characters rather than bytes, and *msglen* will never be equal to SRV_NULLTERM.</span></span>  
  
 <span data-ttu-id="f8718-125">In folgenden Fällen gibt die Funktion FAIL zurück:</span><span class="sxs-lookup"><span data-stu-id="f8718-125">The function returns FAIL when</span></span>  
  
-   <span data-ttu-id="f8718-126">*msglen* befindet sich nicht im Bereich zwischen 0 und 32242.</span><span class="sxs-lookup"><span data-stu-id="f8718-126">The *msglen* given is not in the range of 0-32242.</span></span>  
  
-   <span data-ttu-id="f8718-127">*msglen* entspricht 0, der Meldungszeiger ist jedoch NULL.</span><span class="sxs-lookup"><span data-stu-id="f8718-127">The *msglen* given is 0 but the message pointer is NULL.</span></span>  
  
-   <span data-ttu-id="f8718-128">Beim Versenden der Fehlermeldung über das Netzwerk tritt ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="f8718-128">There is error when sending the error message through network.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f8718-129">Sie sollten den Quellcode der erweiterten gespeicherten Prozeduren sorgfältig prüfen, und Sie sollten die kompilierten DLL-Dateien testen, bevor Sie sie auf einem Produktionsserver installieren.</span><span class="sxs-lookup"><span data-stu-id="f8718-129">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="f8718-130">Weitere Informationen zum Überprüfen und Testen der Sicherheit finden Sie auf dieser [Microsoft-Website](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="f8718-130">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8718-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f8718-131">See Also</span></span>  
 [<span data-ttu-id="f8718-132">srv_sendmsg (API für die erweiterte gespeicherte Prozedur)</span><span class="sxs-lookup"><span data-stu-id="f8718-132">srv_sendmsg &#40;Extended Stored Procedure API&#41;</span></span>](srv-sendmsg-extended-stored-procedure-api.md)  
  
  
