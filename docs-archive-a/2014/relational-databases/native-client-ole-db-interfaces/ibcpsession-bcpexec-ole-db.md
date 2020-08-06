---
title: IBCPSession::BCPExec (OLE DB) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- IBCPSession::BCPExec (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- BCPExec method
ms.assetid: 0f4ebb63-cf03-4e53-846e-6c3021cde007
author: rothja
ms.author: jroth
ms.openlocfilehash: 1452888e046b6223c64a6cdf6fe09b074b815702
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696801"
---
# <a name="ibcpsessionbcpexec-ole-db"></a><span data-ttu-id="1c82d-102">IBCPSession::BCPExec (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="1c82d-102">IBCPSession::BCPExec (OLE DB)</span></span>
  <span data-ttu-id="1c82d-103">Führt den Massenkopiervorgang aus.</span><span class="sxs-lookup"><span data-stu-id="1c82d-103">Performs the bulk copy operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c82d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1c82d-104">Syntax</span></span>  
  
```  
  
HRESULT BCPExec(   
DBROWCOUNT *pRowsCopied);  
```  
  
## <a name="remarks"></a><span data-ttu-id="1c82d-105">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="1c82d-105">Remarks</span></span>  
 <span data-ttu-id="1c82d-106">Mit der **BCPExec**-Methode werden Daten aus einer Benutzerdatei in eine Datenbanktabelle kopiert oder umgekehrt. Dies ist vom Wert des *eDirection*-Parameters abhängig, der für die [IBCPSession::BCPInit](ibcpsession-bcpinit-ole-db.md)-Methode verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1c82d-106">The **BCPExec** method copies data from a user file to a database table or vice versa, depending on the value of the *eDirection* parameter used with the [IBCPSession::BCPInit](ibcpsession-bcpinit-ole-db.md) method.</span></span>  
  
 <span data-ttu-id="1c82d-107">Rufen Sie vor dem Aufruf von **BCPExec**die **BCPInit** -Methode mit einem gültigen Benutzerdateinamen auf.</span><span class="sxs-lookup"><span data-stu-id="1c82d-107">Before calling **BCPExec**, call the **BCPInit** method with a valid user file name.</span></span> <span data-ttu-id="1c82d-108">Andernfalls wird ein Fehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="1c82d-108">Failure to do so results in an error.</span></span> <span data-ttu-id="1c82d-109">Die einzige Ausnahme besteht darin, wenn eine Abfrage für einen Massenkopiervorgang verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="1c82d-109">The only exception is if a query is to be used for a bulk copy out operation.</span></span> <span data-ttu-id="1c82d-110">In diesem Fall geben Sie in der **BCPInit** -Methode NULL für den Tabellennamen an, und dann geben Sie die Abfrage mithilfe der BCP_OPTION_HINTS-Option an.</span><span class="sxs-lookup"><span data-stu-id="1c82d-110">In that case specify NULL for the table name in the **BCPInit** method and then specify the query using the BCP_OPTION_HINTS option.</span></span>  
  
 <span data-ttu-id="1c82d-111">Die **BCPExec** -Methode ist die einzige Methode zum Massenkopieren, die wahrscheinlich für einige Zeit nicht zurückkehrt.</span><span class="sxs-lookup"><span data-stu-id="1c82d-111">The **BCPExec** method is the only bulk copy method that is likely to be outstanding for any length of time.</span></span> <span data-ttu-id="1c82d-112">Es ist deshalb die einzige Massenkopiermethode, die den asynchronen Modus unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1c82d-112">It is therefore the only bulk copy method that supports asynchronous mode.</span></span> <span data-ttu-id="1c82d-113">Um den asynchronen Modus zu verwenden, legen Sie die anbieterspezifische Sitzungs Eigenschaft SSPROP_ASYNCH_BULKCOPY auf VARIANT_TRUE fest, bevor Sie die **BCPExec** -Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="1c82d-113">To use asynchronous mode, set the provider specific session property SSPROP_ASYNCH_BULKCOPY to VARIANT_TRUE before calling the **BCPExec** method.</span></span> <span data-ttu-id="1c82d-114">Diese Eigenschaft ist im DBPROPSET_SQLSERVERSESSION-Eigenschaftensatz verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1c82d-114">This property is available in the DBPROPSET_SQLSERVERSESSION property set.</span></span> <span data-ttu-id="1c82d-115">Rufen Sie die **BCPExec** -Methode mit den gleichen Parametern auf, um den Vorgang auf Vollständigkeit zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="1c82d-115">To test for completion, call the **BCPExec** method with the same parameters.</span></span> <span data-ttu-id="1c82d-116">Wenn das Massenkopieren noch nicht abgeschlossen wurde, gibt die **BCPExec** -Methode DB_S_ASYNCHRONOUS zurück.</span><span class="sxs-lookup"><span data-stu-id="1c82d-116">If the bulk copy has not yet completed, the **BCPExec** method returns DB_S_ASYNCHRONOUS.</span></span> <span data-ttu-id="1c82d-117">Sie gibt überdies im *pRowsCopied* -Argument eine Statuszahl der Anzahl von Zeilen fest, die zum Server gesendet bzw. vom Server empfangen wurden.</span><span class="sxs-lookup"><span data-stu-id="1c82d-117">It also returns in the *pRowsCopied* argument a status count of the number of rows that have been sent to or received from the server.</span></span> <span data-ttu-id="1c82d-118">Für die zum Server gesendeten Zeilen wird erst ein Commit ausgeführt, wenn das Ende eines Batches erreicht wurde.</span><span class="sxs-lookup"><span data-stu-id="1c82d-118">Rows sent to the server are not committed until the end of a batch has been reached.</span></span>  
  
## <a name="arguments"></a><span data-ttu-id="1c82d-119">Argumente</span><span class="sxs-lookup"><span data-stu-id="1c82d-119">Arguments</span></span>  
 <span data-ttu-id="1c82d-120">*pRowsCopied*[out]</span><span class="sxs-lookup"><span data-stu-id="1c82d-120">*pRowsCopied*[out]</span></span>  
 <span data-ttu-id="1c82d-121">Ein Zeiger auf einen DWORD-Wert.</span><span class="sxs-lookup"><span data-stu-id="1c82d-121">A pointer to a DWORD.</span></span> <span data-ttu-id="1c82d-122">Die **BCPExec** -Methode füllt den DWORD-Wert mit der Anzahl von Zeilen, die erfolgreich kopiert wurden.</span><span class="sxs-lookup"><span data-stu-id="1c82d-122">The **BCPExec** method fills the DWORD with the number of rows successfully copied.</span></span> <span data-ttu-id="1c82d-123">Wenn das *pRowsCopied* -Argument auf NULL festgelegt wurde, wird es von der **BCPExec** -Methode ignoriert.</span><span class="sxs-lookup"><span data-stu-id="1c82d-123">If the *pRowsCopied* argument is set to NULL, it is ignored by the **BCPExec** method.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="1c82d-124">Rückgabecodewerte</span><span class="sxs-lookup"><span data-stu-id="1c82d-124">Return Code Values</span></span>  
 <span data-ttu-id="1c82d-125">S_OK</span><span class="sxs-lookup"><span data-stu-id="1c82d-125">S_OK</span></span>  
 <span data-ttu-id="1c82d-126">Die Methode wurde erfolgreich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1c82d-126">The method succeeded.</span></span>  
  
 <span data-ttu-id="1c82d-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1c82d-127">E_FAIL</span></span>  
 <span data-ttu-id="1c82d-128">Ein Anbieter spezifischer Fehler ist aufgetreten. Ausführliche Informationen erhalten Sie, wenn Sie die [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) -Schnittstelle verwenden.</span><span class="sxs-lookup"><span data-stu-id="1c82d-128">A provider-specific error occurred; for detailed information, use the [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) interface.</span></span>  
  
 <span data-ttu-id="1c82d-129">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="1c82d-129">E_UNEXPECTED</span></span>  
 <span data-ttu-id="1c82d-130">Die Methode wurde unerwartet aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="1c82d-130">The call to the method was unexpected.</span></span> <span data-ttu-id="1c82d-131">Die **BCPInit** -Methode wurde beispielsweise erst nach dem Aufruf dieser Methode aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="1c82d-131">For example, the **BCPInit** method was not called before calling this method.</span></span> <span data-ttu-id="1c82d-132">Wird auch zurückgegeben, wenn der Vorgang mit der BCP_OPTION_ABORT-Option abgebrochen und danach die **BCPExec** -Methode aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="1c82d-132">Also occurs if the operation has been aborted through using the BCP_OPTION_ABORT option, and the **BCPExec** method was called afterwards.</span></span>  
  
 <span data-ttu-id="1c82d-133">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="1c82d-133">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="1c82d-134">Fehler aufgrund nicht genügenden Arbeitsspeichers</span><span class="sxs-lookup"><span data-stu-id="1c82d-134">Out-of-memory error.</span></span>  
  
 <span data-ttu-id="1c82d-135">DB_S_ENDOFROWSET</span><span class="sxs-lookup"><span data-stu-id="1c82d-135">DB_S_ENDOFROWSET</span></span>  
 <span data-ttu-id="1c82d-136">Der Massenkopiervorgang wurde beendet, und die gesamte Datenübertragung wurde abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="1c82d-136">The bulk copy operation finished, and all the data transfer was completed.</span></span>  
  
 <span data-ttu-id="1c82d-137">DB_S_ASYNCHRONOUS</span><span class="sxs-lookup"><span data-stu-id="1c82d-137">DB_S_ASYNCHRONOUS</span></span>  
 <span data-ttu-id="1c82d-138">Der aktuelle Batch von Zeilen wurde kopiert.</span><span class="sxs-lookup"><span data-stu-id="1c82d-138">The current batch of rows has been copied.</span></span> <span data-ttu-id="1c82d-139">Rufen Sie die **BCPExec** -Methode erneut auf, um den nächsten Batch zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="1c82d-139">Call the **BCPExec** method again to transfer the next batch.</span></span>  
  
 <span data-ttu-id="1c82d-140">DB_S_ERRORSOCCURRED</span><span class="sxs-lookup"><span data-stu-id="1c82d-140">DB_S_ERRORSOCCURRED</span></span>  
 <span data-ttu-id="1c82d-141">Während des Massenkopiervorgangs sind Fehler aufgetreten, und einige Zeilen sind möglicherweise nicht kopiert worden.</span><span class="sxs-lookup"><span data-stu-id="1c82d-141">Errors occurred during the bulk copy operation, and some rows might not have been copied.</span></span> <span data-ttu-id="1c82d-142">Die Anzahl der Fehler ist immer noch weniger als die maximal zulässige Fehleranzahl.</span><span class="sxs-lookup"><span data-stu-id="1c82d-142">The number of errors is still less than the maximum errors allowed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c82d-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1c82d-143">See Also</span></span>  
 <span data-ttu-id="1c82d-144">[IBCPSession &#40;OLE DB&#41;](ibcpsession-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="1c82d-144">[IBCPSession &#40;OLE DB&#41;](ibcpsession-ole-db.md) </span></span>  
 [<span data-ttu-id="1c82d-145">Durchführen von Massenkopiervorgängen</span><span class="sxs-lookup"><span data-stu-id="1c82d-145">Performing Bulk Copy Operations</span></span>](../native-client/features/performing-bulk-copy-operations.md)  
  
  
