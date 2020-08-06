---
title: ISSAsynchStatus::WaitForAsynchCompletion (OLE DB) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- ISSAsynchStatus::WaitForAsynchCompletion (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- WaitForAsynchCompletion method
ms.assetid: 9f65e9e7-eb93-47a1-bc42-acd4649fbd0e
author: rothja
ms.author: jroth
ms.openlocfilehash: f57211d1c62535828704dc971e345b412c284cf1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616039"
---
# <a name="issasynchstatuswaitforasynchcompletion-ole-db"></a><span data-ttu-id="2cb01-102">ISSAsynchStatus::WaitForAsynchCompletion (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="2cb01-102">ISSAsynchStatus::WaitForAsynchCompletion (OLE DB)</span></span>
  <span data-ttu-id="2cb01-103">Wartet, bis der asynchron ausgeführte Vorgang abgeschlossen ist oder ein Timeout auftritt.</span><span class="sxs-lookup"><span data-stu-id="2cb01-103">Waits until the asynchronously executing operation is complete or until a time-out occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cb01-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2cb01-104">Syntax</span></span>  
  
```  
  
HRESULT WaitForAsynchCompletion(   
  DWORD dwMillisecTimeOut);  
```  
  
## <a name="arguments"></a><span data-ttu-id="2cb01-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="2cb01-105">Arguments</span></span>  
 <span data-ttu-id="2cb01-106">*dwMillisecTimeOut*[in]</span><span class="sxs-lookup"><span data-stu-id="2cb01-106">*dwMillisecTimeOut*[in]</span></span>  
 <span data-ttu-id="2cb01-107">Timeout in Millisekunden.</span><span class="sxs-lookup"><span data-stu-id="2cb01-107">Time-out in milliseconds.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="2cb01-108">Rückgabecodewerte</span><span class="sxs-lookup"><span data-stu-id="2cb01-108">Return Code Values</span></span>  
 <span data-ttu-id="2cb01-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="2cb01-109">S_OK</span></span>  
 <span data-ttu-id="2cb01-110">Die Methode wurde erfolgreich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2cb01-110">The method succeeded.</span></span>  
  
 <span data-ttu-id="2cb01-111">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="2cb01-111">E_UNEXPECTED</span></span>  
 <span data-ttu-id="2cb01-112">Ein Rowset wird nicht verwendet, da **ITransaction::Commit** oder **ITransaction::Abort** aufgerufen oder das Rowset während der ursprünglichen Initialisierungsphase abgebrochen wurde.</span><span class="sxs-lookup"><span data-stu-id="2cb01-112">A rowset is in an unused state because **ITransaction::Commit** or **ITransaction::Abort** has been called or the rowset was cancelled during its initialization phase.</span></span>  
  
 <span data-ttu-id="2cb01-113">DB_E_CANCELED</span><span class="sxs-lookup"><span data-stu-id="2cb01-113">DB_E_CANCELED</span></span>  
 <span data-ttu-id="2cb01-114">Die asynchrone Verarbeitung wurde während der Auffüllung des Rowsets oder Initialisierung des Datenquellobjekts abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="2cb01-114">Asynchronous processing was cancelled during rowset population or data source object initialization.</span></span>  
  
 <span data-ttu-id="2cb01-115">DB_S_ASYNCHRONOUS</span><span class="sxs-lookup"><span data-stu-id="2cb01-115">DB_S_ASYNCHRONOUS</span></span>  
 <span data-ttu-id="2cb01-116">Der Vorgang wurde noch nicht abgeschlossen, obwohl das angegebene Timeout erreicht wurde.</span><span class="sxs-lookup"><span data-stu-id="2cb01-116">The operation has not yet completed even though specified time-out has been reached.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2cb01-117">Zusätzlich zu den oben aufgelisteten Rückgabecodewerten unterstützt die **ISSAsynchStatus::WaitForAsynchCompletion** -Methode auch die Rückgabecodewerte, die von der wichtigsten OLEDB **ICommand::Execute** - und **IDBInitialize::Initialize** -Methode zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="2cb01-117">In addition to the return code values listed above, the **ISSAsynchStatus::WaitForAsynchCompletion** method also supports the return code values returned by the core OLEDB **ICommand::Execute** and **IDBInitialize::Initialize** methods.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2cb01-118">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="2cb01-118">Remarks</span></span>  
 <span data-ttu-id="2cb01-119">Die **ISSAsynchStatus::WaitForAsynchCompletion** -Methode gibt keine Werte zurück, bis der Timeoutwert (in Millisekunden) erreicht oder der ausstehende Vorgang abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="2cb01-119">The **ISSAsynchStatus::WaitForAsynchCompletion** method will not return until the time-out value (in milliseconds) has passed or the pending operation is done.</span></span> <span data-ttu-id="2cb01-120">Das **Command** -Objekt verfügt über eine **CommandTimeout** -Eigenschaft, die die Anzahl der Sekunden steuert, die eine Abfrage ausgeführt wird, bevor ein Timeout eintritt. Die **CommandTimeout** -Eigenschaft wird ignoriert, wenn Sie in Verbindung mit der **ISSAsynchStatus:: WaitForAsynchCompletion** -Methode verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2cb01-120">The **Command** object has a **CommandTimeout** property that controls the number of seconds a query will run before timing out. The **CommandTimeout** property will be ignored if used in conjunction with **ISSAsynchStatus::WaitForAsynchCompletion** method.</span></span>  
  
 <span data-ttu-id="2cb01-121">Die Timeouteigenschaft wird für asynchrone Vorgänge ignoriert.</span><span class="sxs-lookup"><span data-stu-id="2cb01-121">The time-out property is ignored for asynchronous operations.</span></span> <span data-ttu-id="2cb01-122">Der Timeout-Parameter **ISSAsynchStatus::WaitForAsynchCompletion** gibt die maximale Zeitspanne an, die verstreicht, bevor die Steuerung an den Aufrufer zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="2cb01-122">The time-out parameter of **ISSAsynchStatus::WaitForAsynchCompletion** specifies the maximum amount of time that will elapse before control is returned to the caller.</span></span> <span data-ttu-id="2cb01-123">Wenn dieses Timeout abläuft, wird DB_S_ASYNCHRONOUS zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2cb01-123">If this time-out expires, DB_S_ASYNCHRONOUS will be returned.</span></span> <span data-ttu-id="2cb01-124">Timeouts führen nie zum Abbruch asynchroner Vorgänge.</span><span class="sxs-lookup"><span data-stu-id="2cb01-124">Time-outs never cancel asynchronous operations.</span></span> <span data-ttu-id="2cb01-125">Wenn die Anwendung einen asynchronen Vorgang, der nicht innerhalb des Timeouts abgeschlossen wurde, abbrechen muss, muss sie auf das Timeout warten und, falls DB_S_ASYNCHRONOUS zurückgegeben wird, anschließend den Vorgang explizit abbrechen.</span><span class="sxs-lookup"><span data-stu-id="2cb01-125">If the application needs to cancel an asynchronous operation that does not complete within a time-out period, it must wait for the time-out and then explicitly cancel the operation if DB_S_ASYNCHRONOUS is returned.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2cb01-126">Wenn die OLE DB-Dienstkomponenten verwendet werden, wird möglicherweise S_OK zurückgegeben, wenn eigentlich DB_S_ASYNCHRONOUS erwartet wird. Daher sollten Anwendungen [ISSAsynchStatus::GetStatus](issasynchstatus-getstatus-ole-db.md) aufrufen, um den Abschluss zu prüfen, wenn S_OK oder DB_S_ASYNCHRONOUS zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="2cb01-126">When the OLE DB Service Components are used, S_OK may be returned when DB_S_ASYNCHRONOUS is expected, so applications should call [ISSAsynchStatus::GetStatus](issasynchstatus-getstatus-ole-db.md) to check for completion when S_OK or DB_S_ASYNCHRONOUS is returned.</span></span>  
  
 <span data-ttu-id="2cb01-127">Wenn der *dwMillisecTimeOut* -Wert auf INFINITE festgelegt wird, blockiert die **ISSAsynchStatus::WaitForAsynchCompletion** -Methode so lange, bis der Vorgang abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="2cb01-127">If the *dwMillisecTimeOut* value is set to INFINITE, the **ISSAsynchStatus::WaitForAsynchCompletion** method blocks until the operation is done.</span></span> <span data-ttu-id="2cb01-128">Wenn der *dwMillisecTimeOut* -Wert auf 0 festgelegt ist, gibt die Methode umgehend den Status des ausstehenden Vorgangs zurück.</span><span class="sxs-lookup"><span data-stu-id="2cb01-128">If the *dwMillisecTimeOut* value is set to 0, then the method will return immediately with the status of the pending operation.</span></span> <span data-ttu-id="2cb01-129">Wenn das Timeout abläuft, bevor der Vorgang abgeschlossen ist, wird DB_S_ASYNCHRONOUS zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2cb01-129">If the time-out expires before the operation is complete DB_S_ASYNCHRONOUS will be returned.</span></span>  
  
 <span data-ttu-id="2cb01-130">Wenn der Vorgang abgeschlossen ist, bevor das Timeout abläuft, entspricht der zurückgegebene HRESULT-Wert dem vom Vorgang zurückgegebenen HRESULT-Wert (dem HRESULT-Wert, der zurückgegeben worden wäre, wenn der Vorgang synchron ausgeführt worden wäre).</span><span class="sxs-lookup"><span data-stu-id="2cb01-130">If the operation completes before the time-out expires, the returned HRESULT will be the HRESULT returned by the operation (the HRESULT that would have been returned had the operation been performed synchronously).</span></span>  
  
 <span data-ttu-id="2cb01-131">Außerdem wurde dem DBPROPSET_SQLSERVERROWSET-Eigenschaftensatz die SSPROP_ISSAsynchStatus-Eigenschaft hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="2cb01-131">In addition, the SSPROP_ISSAsynchStatus property has been added to the DBPROPSET_SQLSERVERROWSET property set.</span></span> <span data-ttu-id="2cb01-132">Anbieter, die die [ISSAsynchStatus](issasynchstatus-ole-db.md)-Schnittstelle unterstützen, müssen diese Eigenschaft mit dem Wert VARIANT_TRUE implementieren.</span><span class="sxs-lookup"><span data-stu-id="2cb01-132">Providers that support the [ISSAsynchStatus](issasynchstatus-ole-db.md) interface must implement this property with a value of VARIANT_TRUE.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cb01-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2cb01-133">See Also</span></span>  
 <span data-ttu-id="2cb01-134">[Ausführen von asynchronen Vorgängen](../native-client/features/performing-asynchronous-operations.md) </span><span class="sxs-lookup"><span data-stu-id="2cb01-134">[Performing Asynchronous Operations](../native-client/features/performing-asynchronous-operations.md) </span></span>  
 [<span data-ttu-id="2cb01-135">ISSAsynchStatus &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="2cb01-135">ISSAsynchStatus &#40;OLE DB&#41;</span></span>](issasynchstatus-ole-db.md)  
  
  
