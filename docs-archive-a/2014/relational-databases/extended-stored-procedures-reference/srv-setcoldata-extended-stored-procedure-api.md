---
title: srv_setcoldata (API für erweiterte gespeicherte Prozeduren) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_setcoldata
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_setcoldata
ms.assetid: 2e19205a-25ca-4d4a-916b-d591cf2c892b
author: rothja
ms.author: jroth
ms.openlocfilehash: b67aa2f7b5a37057d2ed87846689919d84ec4aaf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723886"
---
# <a name="srv_setcoldata-extended-stored-procedure-api"></a><span data-ttu-id="1f9bb-102">srv_setcoldata (API für erweiterte gespeicherte Prozeduren)</span><span class="sxs-lookup"><span data-stu-id="1f9bb-102">srv_setcoldata (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="1f9bb-103">Verwenden Sie stattdessen die CLR-Integration.</span><span class="sxs-lookup"><span data-stu-id="1f9bb-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="1f9bb-104">Gibt die aktuelle Adresse für die Daten einer Spalte an.</span><span class="sxs-lookup"><span data-stu-id="1f9bb-104">Specifies the current address for a column's data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f9bb-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="1f9bb-105">Syntax</span></span>  
  
```  
  
int srv_setcoldata (  
SRV_PROC *  
srvproc  
,  
int   
column  
,  
void *  
data   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="1f9bb-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="1f9bb-106">Arguments</span></span>  
 <span data-ttu-id="1f9bb-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="1f9bb-107">*srvproc*</span></span>  
 <span data-ttu-id="1f9bb-108">Ein Zeiger auf die SRV_PROC-Struktur, die das Handle für eine bestimmte Clientverbindung ist.</span><span class="sxs-lookup"><span data-stu-id="1f9bb-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection.</span></span> <span data-ttu-id="1f9bb-109">Die Struktur enthält Informationen, mit der die API-Bibliothek für erweiterte gespeicherte Prozeduren die Kommunikation und Daten zwischen der Anwendung und dem Client verwaltet.</span><span class="sxs-lookup"><span data-stu-id="1f9bb-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="1f9bb-110">*column*</span><span class="sxs-lookup"><span data-stu-id="1f9bb-110">*column*</span></span>  
 <span data-ttu-id="1f9bb-111">Gibt die Nummer der Spalte an, für die die Adresse angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="1f9bb-111">Indicates the number of the column the address is being specified for.</span></span> <span data-ttu-id="1f9bb-112">Die Spalten sind fortlaufend nummeriert, beginnend mit 1.</span><span class="sxs-lookup"><span data-stu-id="1f9bb-112">Columns are numbered beginning with 1.</span></span>  
  
 <span data-ttu-id="1f9bb-113">*data*</span><span class="sxs-lookup"><span data-stu-id="1f9bb-113">*data*</span></span>  
 <span data-ttu-id="1f9bb-114">Ist ein Zeiger für die Daten einer Spalte.</span><span class="sxs-lookup"><span data-stu-id="1f9bb-114">Is a pointer for a column's data.</span></span> <span data-ttu-id="1f9bb-115">Der *data* zugewiesene Speicher sollte erst freigegeben werden, wenn die Spaltendaten durch einen anderen Aufruf von **srv_setcoldata**ersetzt wurden oder wenn **srv_senddone** aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="1f9bb-115">Memory allocated for *data* should not be freed until the column data is replaced by another call to **srv_setcoldata**, or until **srv_senddone** is called.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="1f9bb-116">Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="1f9bb-116">Returns</span></span>  
 <span data-ttu-id="1f9bb-117">SUCCEED oder FAIL.</span><span class="sxs-lookup"><span data-stu-id="1f9bb-117">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1f9bb-118">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="1f9bb-118">Remarks</span></span>  
 <span data-ttu-id="1f9bb-119">Jede Spalte der Zeile muss zuerst mit **srv_describe**definiert werden.</span><span class="sxs-lookup"><span data-stu-id="1f9bb-119">Each column of the row must be defined first with **srv_describe**.</span></span> <span data-ttu-id="1f9bb-120">Spaltendatenadressen werden anfänglich mit **srv_describe**festgelegt.</span><span class="sxs-lookup"><span data-stu-id="1f9bb-120">Column data addresses are initially set with **srv_describe**.</span></span> <span data-ttu-id="1f9bb-121">Wenn sich die Adresse der Spaltendaten ändert, muss **srv_setcoldata** aufgerufen werden, um die neue Adresse der Daten anzugeben. Für jede geänderte Spalte muss **srv_setcoldata** separat aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="1f9bb-121">If the address of the column data changes, **srv_setcoldata** must be called to specify the new address of the data and **srv_setcoldata** must be called separately for each changed column.</span></span>  
  
 <span data-ttu-id="1f9bb-122">NULL-Daten werden dargestellt, indem die Länge der Spalte mit **srv_setcollen**auf 0 festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="1f9bb-122">Null data is represented by setting the column's length to 0 with **srv_setcollen**.</span></span> <span data-ttu-id="1f9bb-123">Die Datenadresse wird dann ignoriert.</span><span class="sxs-lookup"><span data-stu-id="1f9bb-123">The data address is then ignored.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="1f9bb-124">Sie sollten den Quellcode der erweiterten gespeicherten Prozeduren sorgfältig prüfen, und Sie sollten die kompilierten DLL-Dateien testen, bevor Sie sie auf einem Produktionsserver installieren.</span><span class="sxs-lookup"><span data-stu-id="1f9bb-124">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="1f9bb-125">Weitere Informationen zum Überprüfen und Testen der Sicherheit finden Sie auf dieser [Microsoft-Website](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="1f9bb-125">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f9bb-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1f9bb-126">See Also</span></span>  
 [<span data-ttu-id="1f9bb-127">srv_describe (API für erweiterte gespeicherte Prozeduren)</span><span class="sxs-lookup"><span data-stu-id="1f9bb-127">srv_describe &#40;Extended Stored Procedure API&#41;</span></span>](srv-describe-extended-stored-procedure-api.md)  
  
  
