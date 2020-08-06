---
title: srv_sendrow (API für erweiterte gespeicherte Prozeduren) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_sendrow
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_sendrow
ms.assetid: a08f608a-10e6-4bff-9b48-0d02e8026cdb
author: rothja
ms.author: jroth
ms.openlocfilehash: df40348b8792a70f84719abfb42152fda9487e6b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726913"
---
# <a name="srv_sendrow-extended-stored-procedure-api"></a><span data-ttu-id="93bf3-102">srv_sendrow (API für erweiterte gespeicherte Prozeduren)</span><span class="sxs-lookup"><span data-stu-id="93bf3-102">srv_sendrow (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="93bf3-103">Verwenden Sie stattdessen die CLR-Integration.</span><span class="sxs-lookup"><span data-stu-id="93bf3-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="93bf3-104">Sendet eine Zeile mit Daten an den Client.</span><span class="sxs-lookup"><span data-stu-id="93bf3-104">Transmits a row of data to the client.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93bf3-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="93bf3-105">Syntax</span></span>  
  
```  
  
int srv_sendrow ( SRV_PROC *  
srvproc   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="93bf3-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="93bf3-106">Arguments</span></span>  
 <span data-ttu-id="93bf3-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="93bf3-107">*srvproc*</span></span>  
 <span data-ttu-id="93bf3-108">Ein Zeiger auf die SRV_PROC-Struktur, die das Handle für eine bestimmte Clientverbindung ist (in diesem Fall das Handle, das die Sprachanforderung erhalten hat).</span><span class="sxs-lookup"><span data-stu-id="93bf3-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the language request).</span></span> <span data-ttu-id="93bf3-109">Die Struktur enthält Informationen, mit der die API-Bibliothek für erweiterte gespeicherte Prozeduren die Kommunikation und Daten zwischen der Anwendung und dem Client verwaltet.</span><span class="sxs-lookup"><span data-stu-id="93bf3-109">The structure contains information that the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="93bf3-110">Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="93bf3-110">Returns</span></span>  
 <span data-ttu-id="93bf3-111">SUCCEED oder FAIL.</span><span class="sxs-lookup"><span data-stu-id="93bf3-111">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="93bf3-112">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="93bf3-112">Remarks</span></span>  
 <span data-ttu-id="93bf3-113">Die **srv_sendrow** -Funktion wird einmal für jede an den Client gesendete Zeile aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="93bf3-113">The **srv_sendrow** function is called once for each row sent to the client.</span></span> <span data-ttu-id="93bf3-114">Alle Zeilen müssen an den Client gesendet werden, bevor Nachrichten, Statuswerte oder Abschlussstatus mit **srv_sendmsg**, **srv_status**oder **srv_senddone**gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="93bf3-114">All rows must be sent to the client before any messages, status values, or completion statuses are sent with **srv_sendmsg**, **srv_status**, or **srv_senddone**.</span></span>  
  
 <span data-ttu-id="93bf3-115">Beim Senden einer Zeile, für die nicht alle Spalten mit **srv_describe** definiert wurden, zeigt die API für erweiterte gespeicherte Prozeduren eine Informationsfehlermeldung an und gibt FAIL an den Client zurück.</span><span class="sxs-lookup"><span data-stu-id="93bf3-115">Sending a row that has not had all its columns defined with **srv_describe** causes the Extended Stored Procedure API application to raise an informational error message and return FAIL to the client.</span></span> <span data-ttu-id="93bf3-116">In diesem Fall wird die Zeile nicht gesendet.</span><span class="sxs-lookup"><span data-stu-id="93bf3-116">In this case, the row is not sent.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="93bf3-117">Die API für erweiterte gespeicherte Prozeduren bietet keine Unterstützung für das Senden von COMPUTE-Zeilen an den Client.</span><span class="sxs-lookup"><span data-stu-id="93bf3-117">The Extended Stored Procedure API does not support sending compute rows to the client.</span></span> <span data-ttu-id="93bf3-118">Wenn eine Zeile, die `ntext`, `text`- oder `image`-Daten enthält, an den Client gesendet wird, werden der Textzeiger und der Text-Timestamp nicht einbezogen.</span><span class="sxs-lookup"><span data-stu-id="93bf3-118">Also, if a row containing `ntext`, `text`, or `image` data is sent to the client, the text pointer and text timestamp are not included.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="93bf3-119">Sie sollten den Quellcode der erweiterten gespeicherten Prozeduren sorgfältig prüfen, und Sie sollten die kompilierten DLL-Dateien testen, bevor Sie sie auf einem Produktionsserver installieren.</span><span class="sxs-lookup"><span data-stu-id="93bf3-119">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="93bf3-120">Weitere Informationen zum Überprüfen und Testen der Sicherheit finden Sie auf dieser [Microsoft-Website](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="93bf3-120">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93bf3-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="93bf3-121">See Also</span></span>  
 [<span data-ttu-id="93bf3-122">srv_describe (API für erweiterte gespeicherte Prozeduren)</span><span class="sxs-lookup"><span data-stu-id="93bf3-122">srv_describe &#40;Extended Stored Procedure API&#41;</span></span>](srv-describe-extended-stored-procedure-api.md)  
  
  
