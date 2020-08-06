---
title: ISSAbort::Abort (OLE DB) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- ISSAbort::Abort (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- Abort method
ms.assetid: a5bca169-694b-4895-84ac-e8fba491e479
author: rothja
ms.author: jroth
ms.openlocfilehash: 3daad53087c876af8dc46bccc9c4bf7952976067
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718118"
---
# <a name="issabortabort-ole-db"></a><span data-ttu-id="7e48a-102">ISSAbort::Abort (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="7e48a-102">ISSAbort::Abort (OLE DB)</span></span>
  <span data-ttu-id="7e48a-103">Bricht das aktuelle Rowset sowie eventuell mit dem aktuellen Befehl verknüpfte Batchbefehle ab.</span><span class="sxs-lookup"><span data-stu-id="7e48a-103">Cancels the current rowset plus any batched commands associated with the current command.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e48a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7e48a-104">Syntax</span></span>  
  
```  
  
HRESULT Abort(void);  
```  
  
## <a name="remarks"></a><span data-ttu-id="7e48a-105">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="7e48a-105">Remarks</span></span>  
 <span data-ttu-id="7e48a-106">Wenn der abgebrochene Befehl eine gespeicherte Prozedur ist, wird die Ausführung der gespeicherten Prozedur (und aller Prozeduren, die diese Prozedur aufgerufen haben) sowie des Befehlsbatch, der den gespeicherten Prozeduraufruf enthielt, ebenfalls beendet.</span><span class="sxs-lookup"><span data-stu-id="7e48a-106">If the command being aborted is in a stored procedure, execution of the stored procedure (and any procedures which had called that procedure) will be terminated as well as the command batch which contains the stored procedure call.</span></span> <span data-ttu-id="7e48a-107">Falls der Server gerade ein Resultset an den Client überträgt, wird dieses gestoppt.</span><span class="sxs-lookup"><span data-stu-id="7e48a-107">If the server is in the process of transferring a result set to the client, this will be stopped.</span></span> <span data-ttu-id="7e48a-108">Wenn der Client ein Resultset nicht verarbeitet, wird durch Aufrufen von **ISSAbort::Abort** vor dem Freigeben des Rowsets die Rowsetfreigabe beschleunigt, aber wenn eine offene Transaktion vorhanden ist und XACT_ABORT auf ON gestellt ist, wird beim Aufrufen von **ISSAbort::Abort** ein Rollback für die Transaktion ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7e48a-108">If the client does not want to consume a result set, calling **ISSAbort::Abort** before releasing the rowset will speed up the rowset release, but if there is an open transaction and XACT_ABORT is ON, the transaction will be rolled back when **ISSAbort::Abort** is called</span></span>  
  
 <span data-ttu-id="7e48a-109">Sobald **ISSAbort::Abort** S_OK zurückgibt, kann die zugehörige **IMultipleResults** -Schnittstelle nicht mehr verwendet werden und gibt bei allen Methodenaufrufen DB_E_CANCELED zurück (außer bei Methoden, die durch die **IUnknown** -Schnittstelle definiert sind), bis sie wieder freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="7e48a-109">After **ISSAbort::Abort** returns S_OK, the associated **IMultipleResults** interface enters a unusable state and returns DB_E_CANCELED to all method calls (except for methods defined by the **IUnknown** interface) until it is released.</span></span> <span data-ttu-id="7e48a-110">Falls vor dem **Abort** -Aufruf ein **IRowset** von **IMultipleResults**empfangen wurde, ist dieses ebenfalls nicht mehr verwendbar und gibt bei allen Methodenaufrufen DB_E_CANCELED zurück (außer bei Methoden, die durch die **IUnknown** -Schnittstelle und **IRowset::ReleaseRows**definiert sind), bis es nach einem erfolgreichen Aufruf von **ISSAbort::Abort**wieder freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="7e48a-110">If an **IRowset** had been obtained from **IMultipleResults** prior to a call to **Abort**, it also enters an unusable state and returns DB_E_CANCELED to all method calls (except for methods defined by the **IUnknown** interface and **IRowset::ReleaseRows**) until it is released after a successful call to **ISSAbort::Abort**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7e48a-111">Wenn der Serverstatus „XACT_ABORT“ab [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] auf ON festgelegt ist, werden bei Ausführung von **ISSAbort::Abort** alle aktuellen impliziten oder expliziten Transaktionen beendet und ein Rollback ausgeführt, wenn eine Verbindung zu [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]besteht.</span><span class="sxs-lookup"><span data-stu-id="7e48a-111">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], if the server XACT_ABORT state is ON, executing **ISSAbort::Abort** will terminate and roll back any current implicit or explicit transaction when connected to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7e48a-112">Frühere Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] brechen die aktuelle Transaktion nicht ab.</span><span class="sxs-lookup"><span data-stu-id="7e48a-112">Earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will not abort the current transaction.</span></span>  
  
## <a name="arguments"></a><span data-ttu-id="7e48a-113">Argumente</span><span class="sxs-lookup"><span data-stu-id="7e48a-113">Arguments</span></span>  
 <span data-ttu-id="7e48a-114">Keine.</span><span class="sxs-lookup"><span data-stu-id="7e48a-114">None.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="7e48a-115">Rückgabecodewerte</span><span class="sxs-lookup"><span data-stu-id="7e48a-115">Return Code Values</span></span>  
 <span data-ttu-id="7e48a-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="7e48a-116">S_OK</span></span>  
 <span data-ttu-id="7e48a-117">Die **ISSAbort::Abort** -Methode gibt S_OK zurück, wenn der Batch abgebrochen wurde, andernfalls DB_E_CANTCANCEL.</span><span class="sxs-lookup"><span data-stu-id="7e48a-117">The **ISSAbort::Abort** method returns S_OK if the batch was canceled and DB_E_CANTCANCEL otherwise.</span></span> <span data-ttu-id="7e48a-118">Wenn der Batch bereits abgebrochen wurde, wird DB_E_CANCELED zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="7e48a-118">If the batch has already been canceled, DB_E_CANCELED is returned.</span></span>  
  
 <span data-ttu-id="7e48a-119">DB_E_CANCELED</span><span class="sxs-lookup"><span data-stu-id="7e48a-119">DB_E_CANCELED</span></span>  
 <span data-ttu-id="7e48a-120">Der Batch wurde bereits abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="7e48a-120">The batch has already been canceled.</span></span>  
  
 <span data-ttu-id="7e48a-121">DB_E_CANTCANCEL</span><span class="sxs-lookup"><span data-stu-id="7e48a-121">DB_E_CANTCANCEL</span></span>  
 <span data-ttu-id="7e48a-122">Der Batch wurde nicht abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="7e48a-122">The batch was not canceled.</span></span>  
  
 <span data-ttu-id="7e48a-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7e48a-123">E_FAIL</span></span>  
 <span data-ttu-id="7e48a-124">Ein Anbieter spezifischer Fehler ist aufgetreten. Ausführliche Informationen erhalten Sie, wenn Sie die [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) -Schnittstelle verwenden.</span><span class="sxs-lookup"><span data-stu-id="7e48a-124">A provider specific error occurred; for detailed information, use the [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) interface.</span></span>  
  
 <span data-ttu-id="7e48a-125">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="7e48a-125">E_UNEXPECTED</span></span>  
 <span data-ttu-id="7e48a-126">Die Methode wurde unerwartet aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="7e48a-126">The call to the method was unexpected.</span></span> <span data-ttu-id="7e48a-127">Zum Beispiel ist das Objekt in einem Zombiezustand, da **ISSAbort::Abort** bereits aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="7e48a-127">For example, the object is in a zombie state because **ISSAbort::Abort** has already been called.</span></span>  
  
 <span data-ttu-id="7e48a-128">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="7e48a-128">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="7e48a-129">Fehler aufgrund von nicht genügend Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="7e48a-129">Out of memory error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e48a-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7e48a-130">See Also</span></span>  
 [<span data-ttu-id="7e48a-131">ISSAbort &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="7e48a-131">ISSAbort &#40;OLE DB&#41;</span></span>](../../database-engine/dev-guide/issabort-ole-db.md)  
  
  
