---
title: srv_rpcowner (API für erweiterte gespeicherte Prozeduren) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_rpcowner
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_rpcowner
ms.assetid: e81a60e6-14ea-47bc-a11c-3d7635344447
author: rothja
ms.author: jroth
ms.openlocfilehash: f903870d0ee01256addb1557eb7e9123853b39e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726926"
---
# <a name="srv_rpcowner-extended-stored-procedure-api"></a><span data-ttu-id="457d0-102">srv_rpcowner (API für erweiterte gespeicherte Prozeduren)</span><span class="sxs-lookup"><span data-stu-id="457d0-102">srv_rpcowner (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="457d0-103">Verwenden Sie stattdessen die CLR-Integration.</span><span class="sxs-lookup"><span data-stu-id="457d0-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="457d0-104">Gibt die Besitzerkomponente für die derzeit remote gespeicherte Prozedur zurück.</span><span class="sxs-lookup"><span data-stu-id="457d0-104">Returns the owner component for the current remote stored procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="457d0-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="457d0-105">Syntax</span></span>  
  
```  
  
DBCHAR * srv_rpcowner (  
SRV_PROC *  
srvproc  
,  
int *  
len   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="457d0-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="457d0-106">Arguments</span></span>  
 <span data-ttu-id="457d0-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="457d0-107">*srvproc*</span></span>  
 <span data-ttu-id="457d0-108">Ist ein Zeiger auf die SRV_PROC-Struktur, die das Handle für eine bestimmte Clientverbindung ist (in diesem Fall das Handle, das die remote gespeicherte Prozedur erhalten hat).</span><span class="sxs-lookup"><span data-stu-id="457d0-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure).</span></span> <span data-ttu-id="457d0-109">Die Struktur enthält Informationen, mit der die API-Bibliothek für erweiterte gespeicherte Prozeduren die Kommunikation und Daten zwischen der Anwendung und dem Client verwaltet.</span><span class="sxs-lookup"><span data-stu-id="457d0-109">The structure contains information that the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="457d0-110">*Nest*</span><span class="sxs-lookup"><span data-stu-id="457d0-110">*len*</span></span>  
 <span data-ttu-id="457d0-111">Ist ein Zeiger auf eine ganzzahlige Variable, die die Länge des Besitzernamens empfängt.</span><span class="sxs-lookup"><span data-stu-id="457d0-111">Is a pointer to an integer variable that receives the length of the owner name.</span></span> <span data-ttu-id="457d0-112">Der Parameter *len* kann NULL sein. In diesem Fall wird die Länge der Besitzerkomponente nicht zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="457d0-112">The parameter *len* can be NULL, in which case the length of the owner component is not returned.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="457d0-113">Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="457d0-113">Returns</span></span>  
 <span data-ttu-id="457d0-114">Ein DBCHAR-Zeiger auf die NULL-terminierte Besitzerkomponente für die aktuelle remote gespeicherte Prozedur.</span><span class="sxs-lookup"><span data-stu-id="457d0-114">A DBCHAR pointer to the null-terminated owner component for the current remote stored procedure.</span></span> <span data-ttu-id="457d0-115">Wenn keine aktuelle remote gespeicherte Prozedur vorhanden ist, wird NULL zurückgegeben, und *len* wird auf –1 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="457d0-115">If there is no current remote stored procedure, NULL is returned and *len* is set to - 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="457d0-116">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="457d0-116">Remarks</span></span>  
 <span data-ttu-id="457d0-117">Diese Funktion gibt nur die Besitzerkomponente der remote gespeicherten Prozedur zurück.</span><span class="sxs-lookup"><span data-stu-id="457d0-117">This function returns only the owner component of the remote stored procedure.</span></span> <span data-ttu-id="457d0-118">Nicht eingeschlossen sind die optionalen Spezifizierer für Name sowie Name und Nummer der remote gespeicherten Prozedur.</span><span class="sxs-lookup"><span data-stu-id="457d0-118">It does not include the optional specifiers for name, remote stored procedure name, and remote stored procedure number.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="457d0-119">Sie sollten den Quellcode der erweiterten gespeicherten Prozeduren sorgfältig prüfen, und Sie sollten die kompilierten DLL-Dateien testen, bevor Sie sie auf einem Produktionsserver installieren.</span><span class="sxs-lookup"><span data-stu-id="457d0-119">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="457d0-120">Weitere Informationen zum Überprüfen und Testen der Sicherheit finden Sie auf dieser [Microsoft-Website](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="457d0-120">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
