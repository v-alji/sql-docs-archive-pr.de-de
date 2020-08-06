---
title: srv_rpcparams (API für erweiterte gespeicherte Prozeduren) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_rpcparams
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_rpcparams
ms.assetid: 96a5e6f6-d320-4623-b96e-0a856e3abebb
author: rothja
ms.author: jroth
ms.openlocfilehash: 443b9ea8a67341afdb92f0c384148c8b1b42f752
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726921"
---
# <a name="srv_rpcparams-extended-stored-procedure-api"></a><span data-ttu-id="fcfaf-102">srv_rpcparams (API für erweiterte gespeicherte Prozeduren)</span><span class="sxs-lookup"><span data-stu-id="fcfaf-102">srv_rpcparams (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="fcfaf-103">Verwenden Sie stattdessen die CLR-Integration.</span><span class="sxs-lookup"><span data-stu-id="fcfaf-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="fcfaf-104">Gibt die Anzahl von Parametern für die derzeit remote gespeicherte Prozedur zurück.</span><span class="sxs-lookup"><span data-stu-id="fcfaf-104">Returns the number of parameters for the current remote stored procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcfaf-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="fcfaf-105">Syntax</span></span>  
  
```  
  
int srv_rpcparams ( SRV_PROC *  
srvproc   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="fcfaf-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="fcfaf-106">Arguments</span></span>  
 <span data-ttu-id="fcfaf-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="fcfaf-107">*srvproc*</span></span>  
 <span data-ttu-id="fcfaf-108">Ist ein Zeiger auf die SRV_PROC-Struktur, die das Handle für eine bestimmte Clientverbindung ist (in diesem Fall das Handle, das die remote gespeicherte Prozedur erhalten hat).</span><span class="sxs-lookup"><span data-stu-id="fcfaf-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure).</span></span> <span data-ttu-id="fcfaf-109">Die Struktur enthält Informationen, mit der die API-Bibliothek für erweiterte gespeicherte Prozeduren die Kommunikation und Daten zwischen der Anwendung und dem Client verwaltet.</span><span class="sxs-lookup"><span data-stu-id="fcfaf-109">The structure contains information that the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="fcfaf-110">Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="fcfaf-110">Returns</span></span>  
 <span data-ttu-id="fcfaf-111">Die Anzahl von Parametern in der remote gespeicherten Prozedur.</span><span class="sxs-lookup"><span data-stu-id="fcfaf-111">The number of parameters in the remote stored procedure.</span></span> <span data-ttu-id="fcfaf-112">Wenn die remote gespeicherte Prozedur keine Parameter enthält oder keine aktuelle remote gespeicherte Prozedur vorhanden ist, wird -1 zurückgegeben und ein Informationsfehler angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fcfaf-112">If there are no parameters in the remote stored procedure or if there is not a current remote stored procedure, -1 is returned and an information error occurs.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fcfaf-113">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="fcfaf-113">Remarks</span></span>  
 <span data-ttu-id="fcfaf-114">Diese Funktion gibt die Anzahl von Parametern in der aktuellen remote gespeicherten Prozedur zurück.</span><span class="sxs-lookup"><span data-stu-id="fcfaf-114">This function returns the number of parameters in the current remote stored procedure.</span></span> <span data-ttu-id="fcfaf-115">Sie wird normalerweise von der remote gespeicherten Prozedur aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="fcfaf-115">It is usually called from the remote stored procedure.</span></span>  
  
 <span data-ttu-id="fcfaf-116">Wenn eine remote gespeicherte Prozedur mit Parametern aufgerufen wird, werden die Parameter entweder mit ihrem Namen oder mit ihrer Position übergeben (unbenannt).</span><span class="sxs-lookup"><span data-stu-id="fcfaf-116">When a remote stored procedure call is made with parameters, the parameters can be passed either by name or by position (unnamed).</span></span> <span data-ttu-id="fcfaf-117">Werden beim Aufruf einer remote gespeicherte Prozedur einige Parameter mit ihrem Namen und einige mit ihrer Position übergeben, so tritt ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="fcfaf-117">If the remote stored procedure call was made with some parameters passed by name and some passed by position, an error occurs.</span></span> <span data-ttu-id="fcfaf-118">In diesem Fall wird der Handler der remote gespeicherten Prozedur aufgerufen, aber es werden keine remote gespeicherten Prozeduren empfangen, und **srv_rpcparams** gibt 0 zurück.</span><span class="sxs-lookup"><span data-stu-id="fcfaf-118">When this error occurs, the remote stored procedure handler is called, but it does not receive the parameters and **srv_rpcparams** returns 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="fcfaf-119">Sie sollten den Quellcode der erweiterten gespeicherten Prozeduren sorgfältig prüfen, und Sie sollten die kompilierten DLL-Dateien testen, bevor Sie sie auf einem Produktionsserver installieren.</span><span class="sxs-lookup"><span data-stu-id="fcfaf-119">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="fcfaf-120">Weitere Informationen zum Überprüfen und Testen der Sicherheit finden Sie auf dieser [Microsoft-Website](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="fcfaf-120">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
