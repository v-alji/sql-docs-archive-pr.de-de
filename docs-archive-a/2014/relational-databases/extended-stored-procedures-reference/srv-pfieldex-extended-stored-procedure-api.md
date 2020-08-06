---
title: srv_pfieldex (API für erweiterte gespeicherte Prozeduren) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_pfieldex
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_pfieldex
ms.assetid: d4e9a34b-b3a3-434f-8556-768bd20d145a
author: rothja
ms.author: jroth
ms.openlocfilehash: a474eafcb6b6d42161a7e67ce7f93636269c46c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615391"
---
# <a name="srv_pfieldex-extended-stored-procedure-api"></a><span data-ttu-id="86c6b-102">srv_pfieldex (API für erweiterte gespeicherte Prozeduren)</span><span class="sxs-lookup"><span data-stu-id="86c6b-102">srv_pfieldex (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="86c6b-103">Verwenden Sie stattdessen die CLR-Integration.</span><span class="sxs-lookup"><span data-stu-id="86c6b-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="86c6b-104">Gibt einen Zeiger auf Daten zurück, die das angeforderte SRV_PROC-Feld enthalten.</span><span class="sxs-lookup"><span data-stu-id="86c6b-104">Returns a pointer to data containing the requested SRV_PROC field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86c6b-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="86c6b-105">Syntax</span></span>  
  
```  
  
void *srv_pfieldex(SRV_PROC *   
srvproc  
, int   
field  
, int *   
len  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="86c6b-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="86c6b-106">Arguments</span></span>  
 <span data-ttu-id="86c6b-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="86c6b-107">*srvproc*</span></span>  
 <span data-ttu-id="86c6b-108">Ein Zeiger auf die SRV_PROC-Struktur, die das Handle für eine bestimmte Clientverbindung ist.</span><span class="sxs-lookup"><span data-stu-id="86c6b-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection.</span></span> <span data-ttu-id="86c6b-109">Die Struktur enthält Informationen, mit der die API-Bibliothek für erweiterte gespeicherte Prozeduren die Kommunikation und Daten zwischen der Anwendung und dem Client verwaltet.</span><span class="sxs-lookup"><span data-stu-id="86c6b-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="86c6b-110">*Flächen*</span><span class="sxs-lookup"><span data-stu-id="86c6b-110">*field*</span></span>  
 <span data-ttu-id="86c6b-111">Gibt das zurückzugebende *srvproc*-Feld an</span><span class="sxs-lookup"><span data-stu-id="86c6b-111">Specifies the *srvproc* field to return.</span></span>  
  
|<span data-ttu-id="86c6b-112">Feld</span><span class="sxs-lookup"><span data-stu-id="86c6b-112">Field</span></span>|<span data-ttu-id="86c6b-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="86c6b-113">Description</span></span>|<span data-ttu-id="86c6b-114">Rückgabetyp</span><span class="sxs-lookup"><span data-stu-id="86c6b-114">Return-type</span></span>|  
|-----------|-----------------|------------------|  
|<span data-ttu-id="86c6b-115">SRV_MSGLCID</span><span class="sxs-lookup"><span data-stu-id="86c6b-115">SRV_MSGLCID</span></span>|<span data-ttu-id="86c6b-116">Aktuelle Sitzungsmeldung-LCID</span><span class="sxs-lookup"><span data-stu-id="86c6b-116">Current session message LCID.</span></span>|<span data-ttu-id="86c6b-117">ULONG\*</span><span class="sxs-lookup"><span data-stu-id="86c6b-117">ULONG\*</span></span>|  
|<span data-ttu-id="86c6b-118">SRV_INSTANCENAME</span><span class="sxs-lookup"><span data-stu-id="86c6b-118">SRV_INSTANCENAME</span></span>|<span data-ttu-id="86c6b-119">Instanzname (wenn genannt); gibt andernfalls NULL zurück</span><span class="sxs-lookup"><span data-stu-id="86c6b-119">Instance name (if named); otherwise, returns NULL.</span></span>|<span data-ttu-id="86c6b-120">WCHAR\*</span><span class="sxs-lookup"><span data-stu-id="86c6b-120">WCHAR\*</span></span>|  
  
 <span data-ttu-id="86c6b-121">*Nest*</span><span class="sxs-lookup"><span data-stu-id="86c6b-121">*len*</span></span>  
 <span data-ttu-id="86c6b-122">Ein Zeiger auf eine **int**-Variable, die die Länge des zurückgegebenen *field*-Werts in Byte enthält.</span><span class="sxs-lookup"><span data-stu-id="86c6b-122">Is a pointer to an **int** variable that contains the length of the returned *field* value in bytes.</span></span> <span data-ttu-id="86c6b-123">Wenn *len* NULL ist, wird die Länge nicht zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="86c6b-123">If *len* is NULL, the length is not returned.</span></span> <span data-ttu-id="86c6b-124">Wenn NULL zurückgegeben wird, wird \**len* auf 0 (null) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="86c6b-124">When NULL is returned \**len* is set to 0.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="86c6b-125">Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="86c6b-125">Returns</span></span>  
 <span data-ttu-id="86c6b-126">Ein Zeiger auf Daten, deren Typ von *field* abhängt.</span><span class="sxs-lookup"><span data-stu-id="86c6b-126">A pointer to data whose type depends on *field*.</span></span> <span data-ttu-id="86c6b-127">NULL wird zurückgegeben, wenn *len* oder *srvproc* NULL ist.</span><span class="sxs-lookup"><span data-stu-id="86c6b-127">NULL is returned when *len* is NULL or *srvproc* is NULL.</span></span> <span data-ttu-id="86c6b-128">Ist *field* unbekannt, wird NULL zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="86c6b-128">If the *field* is unknown, NULL is returned.</span></span> <span data-ttu-id="86c6b-129">Wenn NULL zurückgegeben wird, wird \**len* auf 0 (null) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="86c6b-129">When NULL is returned \**len* is set to 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="86c6b-130">Der vom Server zurückgegebene Puffer sollte schreibgeschützt sein.</span><span class="sxs-lookup"><span data-stu-id="86c6b-130">The buffer returned from the server should be read only.</span></span> <span data-ttu-id="86c6b-131">Andernfalls ist der Serverstatus möglicherweise beschädigt.</span><span class="sxs-lookup"><span data-stu-id="86c6b-131">Otherwise, the server state may be corrupted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="86c6b-132">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="86c6b-132">Remarks</span></span>  
 <span data-ttu-id="86c6b-133">**Sicherheitshinweis** Sie sollten den Quellcode der erweiterten gespeicherten Prozeduren gründlich überprüfen. Außerdem sollten Sie die kompilierten DLLs vor der Installation auf einem Produktionsserver testen.</span><span class="sxs-lookup"><span data-stu-id="86c6b-133">**Security Note** You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="86c6b-134">Weitere Informationen zum Überprüfen und Testen der Sicherheit finden Sie auf dieser [Microsoft-Website](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="86c6b-134">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
