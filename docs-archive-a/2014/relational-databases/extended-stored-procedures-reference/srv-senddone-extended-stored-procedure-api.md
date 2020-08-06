---
title: srv_senddone (API für erweiterte gespeicherte Prozeduren) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_senddone
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_senddone
ms.assetid: 1fc4f1d5-56d4-43f6-b5e4-0c0cc295cba3
author: rothja
ms.author: jroth
ms.openlocfilehash: 877acdc1b666c7f4cbaab737590a1c55e474eb05
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726918"
---
# <a name="srv_senddone-extended-stored-procedure-api"></a><span data-ttu-id="464a3-102">srv_senddone (API für erweiterte gespeicherte Prozeduren)</span><span class="sxs-lookup"><span data-stu-id="464a3-102">srv_senddone (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="464a3-103">Verwenden Sie stattdessen die CLR-Integration.</span><span class="sxs-lookup"><span data-stu-id="464a3-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="464a3-104">Sendet eine Meldung über die Beendigung des Ergebnisses an den Client.</span><span class="sxs-lookup"><span data-stu-id="464a3-104">Sends a result completion message to the client.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="464a3-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="464a3-105">Syntax</span></span>  
  
```  
  
int srv_senddone (  
SRV_PROC *  
srvproc  
,  
DBUSMALLINT   
status  
,  
DBUSMALLINT  
info  
,  
DBINT  
count   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="464a3-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="464a3-106">Arguments</span></span>  
 <span data-ttu-id="464a3-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="464a3-107">*srvproc*</span></span>  
 <span data-ttu-id="464a3-108">Ein Zeiger auf die SRV_PROC-Struktur, die das Handle für eine bestimmte Clientverbindung ist (in diesem Fall das Handle, das die Sprachanforderung erhalten hat).</span><span class="sxs-lookup"><span data-stu-id="464a3-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the language request).</span></span> <span data-ttu-id="464a3-109">Die Struktur enthält Informationen, mit der die API-Bibliothek für erweiterte gespeicherte Prozeduren die Kommunikation und Daten zwischen der Anwendung und dem Client verwaltet.</span><span class="sxs-lookup"><span data-stu-id="464a3-109">The structure contains information that the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="464a3-110">*status*</span><span class="sxs-lookup"><span data-stu-id="464a3-110">*status*</span></span>  
 <span data-ttu-id="464a3-111">Ein 2-Byte-Feld für verschiedene *status* -Flags.</span><span class="sxs-lookup"><span data-stu-id="464a3-111">Is a 2-byte field for various *status* flags.</span></span> <span data-ttu-id="464a3-112">Mehrere Flags können mit den logischen Operatoren AND und OR mit *status* -Flagwerten festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="464a3-112">Multiple flags can be set by using the AND and OR logical operators with *status* flag values.</span></span> <span data-ttu-id="464a3-113">In der folgenden Tabelle sind die möglichen *status* -Flags aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="464a3-113">The following table lists possible *status* flags.</span></span>  
  
|<span data-ttu-id="464a3-114">Statusflag</span><span class="sxs-lookup"><span data-stu-id="464a3-114">Status flag</span></span>|<span data-ttu-id="464a3-115">Description</span><span class="sxs-lookup"><span data-stu-id="464a3-115">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="464a3-116">SRV_DONE_COUNT</span><span class="sxs-lookup"><span data-stu-id="464a3-116">SRV_DONE_COUNT</span></span>|<span data-ttu-id="464a3-117">Der *count* -Parameter enthält eine gültige Anzahl.</span><span class="sxs-lookup"><span data-stu-id="464a3-117">The *count* parameter contains a valid count.</span></span>|  
|<span data-ttu-id="464a3-118">SRV_DONE_ERROR</span><span class="sxs-lookup"><span data-stu-id="464a3-118">SRV_DONE_ERROR</span></span>|<span data-ttu-id="464a3-119">Der aktuelle Clientbefehl hat einen Fehler empfangen.</span><span class="sxs-lookup"><span data-stu-id="464a3-119">The current client command received an error.</span></span>|  
  
 <span data-ttu-id="464a3-120">*info*</span><span class="sxs-lookup"><span data-stu-id="464a3-120">*info*</span></span>  
 <span data-ttu-id="464a3-121">Ist ein reserviertes 2-Byte-Feld.</span><span class="sxs-lookup"><span data-stu-id="464a3-121">Is a reserved, 2-byte field.</span></span> <span data-ttu-id="464a3-122">Legen Sie diesen Wert standardmäßig auf 0 fest.</span><span class="sxs-lookup"><span data-stu-id="464a3-122">Set this value to 0.</span></span>  
  
 <span data-ttu-id="464a3-123">*count*</span><span class="sxs-lookup"><span data-stu-id="464a3-123">*count*</span></span>  
 <span data-ttu-id="464a3-124">Ein 4-Byte-Feld, das verwendet wird, um eine Anzahl für das aktuelle Resultset anzugeben.</span><span class="sxs-lookup"><span data-stu-id="464a3-124">Is a 4-byte field used to indicate a count for the current result set.</span></span> <span data-ttu-id="464a3-125">Wenn das SRV_DONE_COUNT-Flag im *status* -Feld festgelegt wird, enthält *count* eine gültige Anzahl.</span><span class="sxs-lookup"><span data-stu-id="464a3-125">If the SRV_DONE_COUNT flag is set in the *status* field, *count* holds a valid count.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="464a3-126">Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="464a3-126">Returns</span></span>  
 <span data-ttu-id="464a3-127">SUCCEED oder FAIL</span><span class="sxs-lookup"><span data-stu-id="464a3-127">SUCCEED or FAIL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="464a3-128">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="464a3-128">Remarks</span></span>  
 <span data-ttu-id="464a3-129">Eine Clientanforderung kann bewirken, dass der Server eine Reihe von Befehlen ausführt und einige Resultsets zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="464a3-129">A client request can cause the server to execute a number of commands and to return a number of result sets.</span></span> <span data-ttu-id="464a3-130">Für jedes Resultset muss **srv_senddone** dem Client eine Meldung über die Beendigung des Ergebnisses zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="464a3-130">For each result set, **srv_senddone** must return a result completion message to the client.</span></span>  
  
 <span data-ttu-id="464a3-131">Das *count* -Feld gibt die Anzahl der Zeilen an, auf die sich ein Befehl auswirkt.</span><span class="sxs-lookup"><span data-stu-id="464a3-131">The *count* field indicates the number of rows affected by a command.</span></span> <span data-ttu-id="464a3-132">Wenn das *count* -Feld eine Anzahl enthält, sollte das SRV_DONE_COUNT-Flag im *status* -Feld festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="464a3-132">If the *count* field contains a count, the SRV_DONE_COUNT flag should be set in the *status* field.</span></span> <span data-ttu-id="464a3-133">Anhand dieser Einstellung kann der Client zwischen einem *count* -Feld mit dem Wert 0 und einem nicht verwendeten *count* -Feld unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="464a3-133">This setting allows the client to distinguish between a *count* value of 0 and an unused *count* field.</span></span>  
  
 <span data-ttu-id="464a3-134">Rufen Sie **srv_senddone** nicht von der Behandlungsroutine für SRV_CONNECT aus auf.</span><span class="sxs-lookup"><span data-stu-id="464a3-134">Do not call **srv_senddone** from the SRV_CONNECT handler.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="464a3-135">Sie sollten den Quellcode der erweiterten gespeicherten Prozeduren sorgfältig prüfen, und Sie sollten die kompilierten DLL-Dateien testen, bevor Sie sie auf einem Produktionsserver installieren.</span><span class="sxs-lookup"><span data-stu-id="464a3-135">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="464a3-136">Weitere Informationen zum Überprüfen und Testen der Sicherheit finden Sie auf dieser [Microsoft-Website](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="464a3-136">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
