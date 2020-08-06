---
title: srv_rpcoptions (API für erweiterte gespeicherte Prozeduren) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_rpcoptions
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_rpcoptions
ms.assetid: dbcce5d1-d5a1-4379-9597-04e43af5923d
author: rothja
ms.author: jroth
ms.openlocfilehash: f5ebe4ab48721002e679ce149293b474a934e348
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726929"
---
# <a name="srv_rpcoptions-extended-stored-procedure-api"></a><span data-ttu-id="4d41e-102">srv_rpcoptions (API für erweiterte gespeicherte Prozeduren)</span><span class="sxs-lookup"><span data-stu-id="4d41e-102">srv_rpcoptions (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="4d41e-103">Verwenden Sie stattdessen die CLR-Integration.</span><span class="sxs-lookup"><span data-stu-id="4d41e-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="4d41e-104">Gibt die Laufzeitoptionen für die derzeit remote gespeicherte Prozedur zurück.</span><span class="sxs-lookup"><span data-stu-id="4d41e-104">Returns run-time options for the current remote stored procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d41e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="4d41e-105">Syntax</span></span>  
  
```  
  
DBUSMALLINT srv_rpcoptions ( SRV_PROC *  
srvproc   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="4d41e-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="4d41e-106">Arguments</span></span>  
 <span data-ttu-id="4d41e-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="4d41e-107">*srvproc*</span></span>  
 <span data-ttu-id="4d41e-108">Ist ein Zeiger auf die SRV_PROC-Struktur, die das Handle für eine bestimmte Clientverbindung ist (in diesem Fall das Handle, das die remote gespeicherte Prozedur erhalten hat).</span><span class="sxs-lookup"><span data-stu-id="4d41e-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure).</span></span> <span data-ttu-id="4d41e-109">Die Struktur enthält Informationen, mit der die API-Bibliothek für erweiterte gespeicherte Prozeduren die Kommunikation und Daten zwischen der Anwendung und dem Client verwaltet.</span><span class="sxs-lookup"><span data-stu-id="4d41e-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="4d41e-110">Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="4d41e-110">Returns</span></span>  
 <span data-ttu-id="4d41e-111">Eine Bitmap mit den in einer logischen Darstellung ODER für die derzeit remote gespeicherte Prozedur verbundenen Laufzeitflags.</span><span class="sxs-lookup"><span data-stu-id="4d41e-111">A bitmap that contains the run-time flags joined in a logical OR for the current remote stored procedure.</span></span> <span data-ttu-id="4d41e-112">Wenn keine aktuelle remote gespeicherte Prozedur vorhanden ist, wird 0 zurückgegeben und eine Meldung generiert.</span><span class="sxs-lookup"><span data-stu-id="4d41e-112">If there is not a current remote stored procedure, 0 is returned and a message is generated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4d41e-113">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="4d41e-113">Remarks</span></span>  
 <span data-ttu-id="4d41e-114">In der folgenden Tabelle werden die einzelnen Laufzeitflags beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4d41e-114">The following table describes each run-time flag.</span></span>  
  
|<span data-ttu-id="4d41e-115">Laufzeitflag</span><span class="sxs-lookup"><span data-stu-id="4d41e-115">Run-time flag</span></span>|<span data-ttu-id="4d41e-116">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4d41e-116">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="4d41e-117">SRV_NOMETADATA</span><span class="sxs-lookup"><span data-stu-id="4d41e-117">SRV_NOMETADATA</span></span>|<span data-ttu-id="4d41e-118">Der Client hat Ergebnisse ohne Metadateninformationen angefordert.</span><span class="sxs-lookup"><span data-stu-id="4d41e-118">The client has requested results without metadata information.</span></span> <span data-ttu-id="4d41e-119">Dieses Flag wird nur verwendet, wenn der Client mit einer Instanz von kommuniziert [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4d41e-119">This flag is only used when the client is communicating with an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4d41e-120">Eine Anwendung der API für erweiterte gespeicherte Prozeduren kann Metadateninformationen nicht auslassen.</span><span class="sxs-lookup"><span data-stu-id="4d41e-120">An Extended Stored Procedure API application cannot omit metadata information.</span></span>|  
|<span data-ttu-id="4d41e-121">SRV_RECOMPILE</span><span class="sxs-lookup"><span data-stu-id="4d41e-121">SRV_RECOMPILE</span></span>|<span data-ttu-id="4d41e-122">Der Client hat vor der Ausführung der remote gespeicherten Prozedur eine erneute Kompilierung angefordert.</span><span class="sxs-lookup"><span data-stu-id="4d41e-122">The client has requested to recompile the remote stored procedure before executing it.</span></span> <span data-ttu-id="4d41e-123">Dieses Flag gilt möglicherweise nicht für eine Anwendung der API für erweiterte gespeicherte Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="4d41e-123">This flag may not apply to an Extended Stored Procedure API application.</span></span>|  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4d41e-124">Sie sollten den Quellcode der erweiterten gespeicherten Prozeduren sorgfältig prüfen, und Sie sollten die kompilierten DLL-Dateien testen, bevor Sie sie auf einem Produktionsserver installieren.</span><span class="sxs-lookup"><span data-stu-id="4d41e-124">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="4d41e-125">Weitere Informationen zum Überprüfen und Testen der Sicherheit finden Sie auf dieser [Microsoft-Website](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="4d41e-125">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
