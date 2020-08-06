---
title: srv_paraminfo (API für erweiterte gespeicherte Prozeduren) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_paraminfo
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_paraminfo
ms.assetid: ee2afd4e-0d91-462b-9403-98d481546330
author: rothja
ms.author: jroth
ms.openlocfilehash: cc3d51acc2ca560246c46267840db72934223999
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725818"
---
# <a name="srv_paraminfo-extended-stored-procedure-api"></a><span data-ttu-id="44fa5-102">srv_paraminfo (API für erweiterte gespeicherte Prozeduren)</span><span class="sxs-lookup"><span data-stu-id="44fa5-102">srv_paraminfo (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="44fa5-103">Verwenden Sie stattdessen die CLR-Integration.</span><span class="sxs-lookup"><span data-stu-id="44fa5-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="44fa5-104">Gibt Informationen zu einem Parameter zurück.</span><span class="sxs-lookup"><span data-stu-id="44fa5-104">Returns information about a parameter.</span></span> <span data-ttu-id="44fa5-105">Diese Funktion ersetzt folgende Funktionen: [srv_paramtype](srv-paramtype-extended-stored-procedure-api.md), [srv_paramlen](srv-paramlen-extended-stored-procedure-api.md), [srv_parammaxlen](srv-parammaxlen-extended-stored-procedure-api.md) und [srv_paramdata](srv-paramdata-extended-stored-procedure-api.md).</span><span class="sxs-lookup"><span data-stu-id="44fa5-105">This function supersedes the following functions: [srv_paramtype](srv-paramtype-extended-stored-procedure-api.md), [srv_paramlen](srv-paramlen-extended-stored-procedure-api.md), [srv_parammaxlen](srv-parammaxlen-extended-stored-procedure-api.md), and [srv_paramdata](srv-paramdata-extended-stored-procedure-api.md).</span></span> <span data-ttu-id="44fa5-106">**srv_paraminfo** unterstützt die Datentypen unter [Datentypen](data-types-extended-stored-procedure-api.md) und Daten der Länge 0 (null).</span><span class="sxs-lookup"><span data-stu-id="44fa5-106">**srv_paraminfo** supports the data types in [Data Types](data-types-extended-stored-procedure-api.md) and zero-length data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44fa5-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="44fa5-107">Syntax</span></span>  
  
```  
  
int srv_paraminfo (  
SRV_PROC *  
srvproc  
,  
int  
n  
,  
BYTE *  
pbType  
,  
ULONG *  
pcbMaxLen  
,  
ULONG *  
pcbActualLen  
,  
BYTE *  
pbData  
,  
BOOL *  
pfNull  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="44fa5-108">Argumente</span><span class="sxs-lookup"><span data-stu-id="44fa5-108">Arguments</span></span>  
 <span data-ttu-id="44fa5-109">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="44fa5-109">*srvproc*</span></span>  
 <span data-ttu-id="44fa5-110">Ein Handle für eine Clientverbindung.</span><span class="sxs-lookup"><span data-stu-id="44fa5-110">A handle for a client connection.</span></span>  
  
 <span data-ttu-id="44fa5-111">*n*</span><span class="sxs-lookup"><span data-stu-id="44fa5-111">*n*</span></span>  
 <span data-ttu-id="44fa5-112">Die Ordnungszahl des festzulegenden Parameters.</span><span class="sxs-lookup"><span data-stu-id="44fa5-112">The ordinal number of the parameter to be set.</span></span> <span data-ttu-id="44fa5-113">Der erste Parameter ist 1.</span><span class="sxs-lookup"><span data-stu-id="44fa5-113">The first parameter is 1.</span></span>  
  
 <span data-ttu-id="44fa5-114">*pbType*</span><span class="sxs-lookup"><span data-stu-id="44fa5-114">*pbType*</span></span>  
 <span data-ttu-id="44fa5-115">Der Datentyp des Parameters.</span><span class="sxs-lookup"><span data-stu-id="44fa5-115">The data type of the parameter.</span></span>  
  
 <span data-ttu-id="44fa5-116">*pcbMaxLen*</span><span class="sxs-lookup"><span data-stu-id="44fa5-116">*pcbMaxLen*</span></span>  
 <span data-ttu-id="44fa5-117">Zeiger auf die maximale Länge des Parameters.</span><span class="sxs-lookup"><span data-stu-id="44fa5-117">Pointer to the maximum length of the parameter.</span></span>  
  
 <span data-ttu-id="44fa5-118">*pcbActualLen*</span><span class="sxs-lookup"><span data-stu-id="44fa5-118">*pcbActualLen*</span></span>  
 <span data-ttu-id="44fa5-119">Zeiger auf die tatsächliche Länge des Parameters.</span><span class="sxs-lookup"><span data-stu-id="44fa5-119">Pointer to the actual length of the parameter.</span></span> <span data-ttu-id="44fa5-120">Der Wert 0 (\**pcbActualLen* == 0) gibt Daten der Länge 0 (null) an, wenn \* *pfNull* auf FALSE festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="44fa5-120">A value of 0 (\**pcbActualLen* == 0) signifies zero-length data if \**pfNull* is set to FALSE.</span></span>  
  
 <span data-ttu-id="44fa5-121">*pbData*</span><span class="sxs-lookup"><span data-stu-id="44fa5-121">*pbData*</span></span>  
 <span data-ttu-id="44fa5-122">Zeiger auf den Puffer für Parameterdaten.</span><span class="sxs-lookup"><span data-stu-id="44fa5-122">Pointer to the buffer for parameter data.</span></span> <span data-ttu-id="44fa5-123">Wenn *pbData* nicht NULL ist, schreibt die API für erweiterte gespeicherte Prozeduren \**pcbActualLen*-Datenbytes in \**pbData*.</span><span class="sxs-lookup"><span data-stu-id="44fa5-123">If *pbData* is not NULL, the Extended Store Procedure API writes \**pcbActualLen* bytes of data to \**pbData*.</span></span> <span data-ttu-id="44fa5-124">Wenn *pbData* NULL ist, werden keine Daten in \**pbData* geschrieben, die Funktion gibt jedoch \**pbType*, \**pcbMaxLen*, \**pcbActualLen*, und \**pfNull* zurück.</span><span class="sxs-lookup"><span data-stu-id="44fa5-124">If *pbData* is NULL, no data is written to \**pbData* but the function returns \**pbType*, \**pcbMaxLen*, \**pcbActualLen*, and \**pfNull*.</span></span> <span data-ttu-id="44fa5-125">Der Arbeitsspeicher für diesen Puffer muss von der Anwendung verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="44fa5-125">The memory for this buffer must be managed by the application.</span></span>  
  
 <span data-ttu-id="44fa5-126">*pfNull*</span><span class="sxs-lookup"><span data-stu-id="44fa5-126">*pfNull*</span></span>  
 <span data-ttu-id="44fa5-127">Zeiger auf ein NULL-Flag.</span><span class="sxs-lookup"><span data-stu-id="44fa5-127">Pointer to a null flag.</span></span><span data-ttu-id="44fa5-128">\ **pfNull* ist auf TRUE festgelegt, wenn der Wert des Parameters NULL ist.</span><span class="sxs-lookup"><span data-stu-id="44fa5-128">\ **pfNull* is set to TRUE if the value of the parameter is NULL.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="44fa5-129">Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="44fa5-129">Returns</span></span>  
 <span data-ttu-id="44fa5-130">Wenn die Parameterinformationen erfolgreich abgerufen wurden, wird SUCCEED zurückgegeben, andernfalls FAIL.</span><span class="sxs-lookup"><span data-stu-id="44fa5-130">If the parameter information was successfully obtained, SUCCEED is returned; otherwise, FAIL.</span></span> <span data-ttu-id="44fa5-131">Es wird FAIL zurückgegeben, wenn keine aktuelle remote gespeicherte Prozedur vorhanden ist und wenn kein remote gespeicherter *n*-Prozedurparameter vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="44fa5-131">FAIL is returned when there is no current remote stored procedure and when there is no *n*th remote stored procedure parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="44fa5-132">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="44fa5-132">Remarks</span></span>  
 <span data-ttu-id="44fa5-133">**Sicherheitshinweis** Sie sollten den Quellcode der erweiterten gespeicherten Prozeduren gründlich überprüfen. Außerdem sollten Sie die kompilierten DLLs vor der Installation auf einem Produktionsserver testen.</span><span class="sxs-lookup"><span data-stu-id="44fa5-133">**Security Note** You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="44fa5-134">Weitere Informationen zum Überprüfen und Testen der Sicherheit finden Sie auf dieser [Microsoft-Website](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="44fa5-134">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44fa5-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="44fa5-135">See Also</span></span>  
 [<span data-ttu-id="44fa5-136">Erweiterte gespeicherte Prozeduren – Programmierreferenz</span><span class="sxs-lookup"><span data-stu-id="44fa5-136">Extended Stored Procedures Programmer's Reference</span></span>](database-engine-extended-stored-procedures-reference.md)  
  
  
