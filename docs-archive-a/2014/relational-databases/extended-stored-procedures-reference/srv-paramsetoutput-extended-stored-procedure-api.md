---
title: srv_paramsetoutput (API für erweiterte gespeicherte Prozeduren) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_paramsetoutput
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_paramsetoutput
ms.assetid: f2810e19-e513-458b-8925-5756b6ee1313
author: rothja
ms.author: jroth
ms.openlocfilehash: 2847367fe5d6052728cebf30467b68cb14fb8e63
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609216"
---
# <a name="srv_paramsetoutput-extended-stored-procedure-api"></a><span data-ttu-id="bcb10-102">srv_paramsetoutput (API für erweiterte gespeicherte Prozeduren)</span><span class="sxs-lookup"><span data-stu-id="bcb10-102">srv_paramsetoutput (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="bcb10-103">Verwenden Sie stattdessen die CLR-Integration.</span><span class="sxs-lookup"><span data-stu-id="bcb10-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="bcb10-104">Legt den Wert eines Rückgabeparameters fest.</span><span class="sxs-lookup"><span data-stu-id="bcb10-104">Sets the value of a return parameter.</span></span> <span data-ttu-id="bcb10-105">Diese Funktion setzt die **srv_paramset** -Funktion außer Kraft.</span><span class="sxs-lookup"><span data-stu-id="bcb10-105">This function supersedes the **srv_paramset** function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcb10-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="bcb10-106">Syntax</span></span>  
  
```  
  
int srv_paramsetoutput (  
SRV_PROC *  
srvproc  
,  
int  
n  
,  
BYTE *  
pbData  
,  
ULONG   
cbLen  
,  
BOOL  
fNull   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="bcb10-107">Argumente</span><span class="sxs-lookup"><span data-stu-id="bcb10-107">Arguments</span></span>  
 <span data-ttu-id="bcb10-108">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="bcb10-108">*srvproc*</span></span>  
 <span data-ttu-id="bcb10-109">Ein Handle für eine Clientverbindung.</span><span class="sxs-lookup"><span data-stu-id="bcb10-109">Is a handle for a client connection.</span></span>  
  
 <span data-ttu-id="bcb10-110">*n*</span><span class="sxs-lookup"><span data-stu-id="bcb10-110">*n*</span></span>  
 <span data-ttu-id="bcb10-111">Die Ordnungszahl des festzulegenden Parameters.</span><span class="sxs-lookup"><span data-stu-id="bcb10-111">Is the ordinal number of the parameter to be set.</span></span> <span data-ttu-id="bcb10-112">Der erste Parameter ist 1.</span><span class="sxs-lookup"><span data-stu-id="bcb10-112">The first parameter is 1.</span></span>  
  
 <span data-ttu-id="bcb10-113">*pbData*</span><span class="sxs-lookup"><span data-stu-id="bcb10-113">*pbData*</span></span>  
 <span data-ttu-id="bcb10-114">Ein Verweis auf den Datenwert, der als ein Prozedurrückgabeparameter an den Client zurückgesendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="bcb10-114">Is a pointer to the data value to be sent back to the client as a procedure return parameter.</span></span>  
  
 <span data-ttu-id="bcb10-115">*cbLen*</span><span class="sxs-lookup"><span data-stu-id="bcb10-115">*cbLen*</span></span>  
 <span data-ttu-id="bcb10-116">Die tatsächliche Länge der zurückzugebenden Daten.</span><span class="sxs-lookup"><span data-stu-id="bcb10-116">Is the actual length of the data to be returned.</span></span> <span data-ttu-id="bcb10-117">Wenn der Datentyp des Parameters Werte einer konstanten Länge angibt und keine NULL-Werte zulässt (z. B. *srvbit* oder *srvint1*), wird *cbLen* ignoriert.</span><span class="sxs-lookup"><span data-stu-id="bcb10-117">If the data type of the parameter specifies values of a constant length and does not allow null values (for example, *srvbit* or *srvint1*), *cbLen* is ignored.</span></span> <span data-ttu-id="bcb10-118">Der Wert 0 gibt Daten der Länge 0 (null) an, wenn *fNull* FALSE ist.</span><span class="sxs-lookup"><span data-stu-id="bcb10-118">A value of 0 signifies zero-length data if *fNull* is FALSE.</span></span>  
  
 <span data-ttu-id="bcb10-119">*fNull*</span><span class="sxs-lookup"><span data-stu-id="bcb10-119">*fNull*</span></span>  
 <span data-ttu-id="bcb10-120">Ein Flag, der angibt, ob der Wert des Rückgabeparameters NULL ist.</span><span class="sxs-lookup"><span data-stu-id="bcb10-120">Is a flag indicating whether the value of the return parameter is NULL.</span></span> <span data-ttu-id="bcb10-121">Legen Sie dieses Flag auf TRUE fest, wenn der Parameter auf NULL gesetzt werden soll.</span><span class="sxs-lookup"><span data-stu-id="bcb10-121">Set this flag to TRUE if the parameter should be set to NULL.</span></span> <span data-ttu-id="bcb10-122">Der Standardwert ist FALSE.</span><span class="sxs-lookup"><span data-stu-id="bcb10-122">The default value is FALSE.</span></span> <span data-ttu-id="bcb10-123">Wenn *fNull* auf TRUE gesetzt ist, sollte *cbLen* auf 0 gesetzt werden, anderenfalls schlägt die Funktion fehl.</span><span class="sxs-lookup"><span data-stu-id="bcb10-123">If *fNull* is set to TRUE, *cbLen* should be set to 0 or the function will fail.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="bcb10-124">Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="bcb10-124">Returns</span></span>  
 <span data-ttu-id="bcb10-125">Wenn die Parameterinformationen erfolgreich festgelegt wurden, wird SUCCEED zurückgegeben, andernfalls FAIL.</span><span class="sxs-lookup"><span data-stu-id="bcb10-125">If the parameter information was successfully set, SUCCEED is returned; otherwise, FAIL.</span></span> <span data-ttu-id="bcb10-126">FAIL wird in den folgenden Fällen zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="bcb10-126">FAIL is returned when</span></span>  
  
-   <span data-ttu-id="bcb10-127">Der Parameter ist kein Rückgabeparameter.</span><span class="sxs-lookup"><span data-stu-id="bcb10-127">the parameter is not a return parameter, or</span></span>  
  
-   <span data-ttu-id="bcb10-128">Das *cbLen* -Argument ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="bcb10-128">the *cbLen* argument is invalid.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bcb10-129">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="bcb10-129">Remarks</span></span>  
 <span data-ttu-id="bcb10-130">**Sicherheitshinweis** Sie sollten den Quellcode der erweiterten gespeicherten Prozeduren gründlich überprüfen. Außerdem sollten Sie die kompilierten DLLs vor der Installation auf einem Produktionsserver testen.</span><span class="sxs-lookup"><span data-stu-id="bcb10-130">**Security Note** You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="bcb10-131">Weitere Informationen zum Überprüfen und Testen der Sicherheit finden Sie auf dieser [Microsoft-Website](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="bcb10-131">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
