---
title: srv_getbindtoken (API für erweiterte gespeicherte Prozeduren) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_getbindtoken
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_getbindtoken
ms.assetid: c947d011-08ac-4fb8-b925-3da6e0999277
author: rothja
ms.author: jroth
ms.openlocfilehash: d42f95c8a7df87f20ebaa30501b96b5f2a00815a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622109"
---
# <a name="srv_getbindtoken-extended-stored-procedure-api"></a><span data-ttu-id="b4bd7-102">srv_getbindtoken (API für erweiterte gespeicherte Prozeduren)</span><span class="sxs-lookup"><span data-stu-id="b4bd7-102">srv_getbindtoken (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="b4bd7-103">Verwenden Sie stattdessen die CLR-Integration.</span><span class="sxs-lookup"><span data-stu-id="b4bd7-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="b4bd7-104">Enthält ein Bindungstoken der Transaktion in der aktuellen Clientsitzung, mit dem die erweiterte gespeicherte Prozedur aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="b4bd7-104">Obtains a bind token of the transaction in the current client session that invokes the extended stored procedure.</span></span>  
  
 <span data-ttu-id="b4bd7-105">Die erweiterte gespeicherte Prozedur kann dann mithilfe von **sp_bindsession** eine neue Sitzung binden, die sie mit demselben Server für die vorhandene Transaktion erstellt. So kann die neue Sitzung denselben Transaktionssperrbereich zusammen mit der Clientsitzung nutzen, die die erweiterte gespeicherte Prozedur aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="b4bd7-105">The extended stored procedure can then use **sp_bindsession** to bind any new session it creates against the same server to the existing transaction so that the new session can share the same transaction lock space with the client session that invoked the extended stored procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4bd7-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="b4bd7-106">Syntax</span></span>  
  
```  
  
int srv_getbindtoken (  
SRV_PROC*  
srvproc  
,  
char*  
bindtoken  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="b4bd7-107">Argumente</span><span class="sxs-lookup"><span data-stu-id="b4bd7-107">Arguments</span></span>  
 <span data-ttu-id="b4bd7-108">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="b4bd7-108">*srvproc*</span></span>  
 <span data-ttu-id="b4bd7-109">Ein Zeiger auf die SRV_PROC-Struktur, die das Handle für eine bestimmte Clientverbindung ist.</span><span class="sxs-lookup"><span data-stu-id="b4bd7-109">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection.</span></span> <span data-ttu-id="b4bd7-110">Die Struktur enthält alle Kontrollinformationen, mit der die API-Bibliothek für erweiterte gespeicherte Prozeduren Kommunikationen und Daten zwischen der Anwendung und dem Client verwaltet.</span><span class="sxs-lookup"><span data-stu-id="b4bd7-110">The structure contains all the information that the Extended Stored Procedure API library uses to manage communications and data between the application and the client.</span></span>  
  
 <span data-ttu-id="b4bd7-111">*bindtoken*</span><span class="sxs-lookup"><span data-stu-id="b4bd7-111">*bindtoken*</span></span>  
 <span data-ttu-id="b4bd7-112">Ein Zeiger auf einen Puffer, in dem das Bindungstoken kopiert wird.</span><span class="sxs-lookup"><span data-stu-id="b4bd7-112">Is a pointer to a buffer where the bind token will be copied.</span></span> <span data-ttu-id="b4bd7-113">Das Bindungstoken wird als eine Zeichenfolge dargestellt, die auf NULL endet.</span><span class="sxs-lookup"><span data-stu-id="b4bd7-113">The bind token is represented as a null-terminated string.</span></span> <span data-ttu-id="b4bd7-114">Der Puffer, den Sie angeben, muss mindestens 255 Bytes lang sein.</span><span class="sxs-lookup"><span data-stu-id="b4bd7-114">The buffer you specify should be at least 255 bytes in length.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="b4bd7-115">Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="b4bd7-115">Returns</span></span>  
 <span data-ttu-id="b4bd7-116">SUCCEED oder FAIL.</span><span class="sxs-lookup"><span data-stu-id="b4bd7-116">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b4bd7-117">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="b4bd7-117">Remarks</span></span>  
  
### <a name="to-bind-an-extended-stored-procedure-session-to-the-client-session-that-called-it-so-they-share-the-same-transaction-lock-space"></a><span data-ttu-id="b4bd7-118">So binden Sie eine Sitzung der erweiterten gespeicherten Prozedur an die Clientsitzung, die die Prozedur aufgerufen hat, sodass beide Sitzungen denselben Transaktionssperrbereich nutzen</span><span class="sxs-lookup"><span data-stu-id="b4bd7-118">To bind an extended stored procedure session to the client session that called it so they share the same transaction lock space</span></span>  
  
1.  <span data-ttu-id="b4bd7-119">Die erweiterte gespeicherte Prozedur ruft **svr_getbindtoken** auf, um das Bindungstoken für die aktuelle Transaktion in der Sitzung abzurufen.</span><span class="sxs-lookup"><span data-stu-id="b4bd7-119">The extended stored procedure calls **svr_getbindtoken** to get the bind token for the current transaction in the session.</span></span> <span data-ttu-id="b4bd7-120">Das Token wird im gegebenen *bindtoken*-Parameter zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b4bd7-120">The token is returned in the given *bindtoken* parameter.</span></span>  
  
2.  <span data-ttu-id="b4bd7-121">Die erweiterte gespeicherte Prozedur öffnet auf demselben Server neue Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="b4bd7-121">The extended stored procedure opens new session(s) against the same server.</span></span> <span data-ttu-id="b4bd7-122">Innerhalb dieser Sitzung verwendet die erweiterte gespeicherte Prozedur das Bindungstoken mit **sp_bindsession**, um die neue Sitzung an dieselbe Transaktion zu binden.</span><span class="sxs-lookup"><span data-stu-id="b4bd7-122">Inside that session, the extended stored procedure uses the bind token with **sp_bindsession** to bind the new session to the same transaction.</span></span> <span data-ttu-id="b4bd7-123">Die erweiterte gespeicherte Prozedur kann mehrere Sitzungen erstellen und alle Sitzungen an dieselbe Transaktion binden.</span><span class="sxs-lookup"><span data-stu-id="b4bd7-123">The extended stored procedure can create multiple sessions and bind all the sessions to the same transaction.</span></span>  
  
3.  <span data-ttu-id="b4bd7-124">Die Bindung einer gebundenen Sitzung wird aufgehoben, wenn die externe gespeicherte Prozedur eine leere Zeichenfolge zurückgibt oder wenn **sp_bindsession** mit einer leeren Zeichenfolge aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="b4bd7-124">A bound session is unbound when the external stored procedure returns or when **sp_bindsession** is called with an empty string.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b4bd7-125">Es kann immer jeweils nur eine gebundene Sitzung Zugriff auf eine gemeinsam genutzte Verbindung haben.</span><span class="sxs-lookup"><span data-stu-id="b4bd7-125">Only one bound session at a time can have access to a shared connection.</span></span> <span data-ttu-id="b4bd7-126">Wenn eine Sitzung derzeit eine Anweisung auf dem Server ausführt oder auf Ergebnisse vom Server wartet, können andere Sitzungen, die dieselbe gebundene Verbindung nutzen, erst dann auf den Server zugreifen, wenn die aktuelle Sitzung die aktuelle Anweisung ausgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="b4bd7-126">If one session is currently executing a statement at the server or has results pending from the server, no other sessions sharing the same bound connection can gain access to the server until the current session has finished executing the current statement.</span></span> <span data-ttu-id="b4bd7-127">Wenn durch eine andere Sitzung auf die Verbindung zugegriffen wird, solange der Server ausgelastet ist, wird an die den Konflikt verursachende Sitzung die Fehlermeldung zurückgegeben, dass die Verbindung verwendet wird und der Zugriffsversuch der Sitzung später wiederholt werden kann.</span><span class="sxs-lookup"><span data-stu-id="b4bd7-127">If a session attempts to gain access to the connection while the server is busy, an error is returned to the conflicting session indicating the connection is in use and the session should retry later.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b4bd7-128">Sie sollten den Quellcode der erweiterten gespeicherten Prozeduren sorgfältig prüfen, und Sie sollten die kompilierten DLL-Dateien testen, bevor Sie sie auf einem Produktionsserver installieren.</span><span class="sxs-lookup"><span data-stu-id="b4bd7-128">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="b4bd7-129">Weitere Informationen zum Überprüfen und Testen der Sicherheit finden Sie auf dieser [Microsoft-Website](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="b4bd7-129">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4bd7-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b4bd7-130">See Also</span></span>  
 <span data-ttu-id="b4bd7-131">[sp_bindsession (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-bindsession-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b4bd7-131">[sp_bindsession &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-bindsession-transact-sql) </span></span>  
 [<span data-ttu-id="b4bd7-132">sp_getbindtoken &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b4bd7-132">sp_getbindtoken &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-getbindtoken-transact-sql)  
  
  
