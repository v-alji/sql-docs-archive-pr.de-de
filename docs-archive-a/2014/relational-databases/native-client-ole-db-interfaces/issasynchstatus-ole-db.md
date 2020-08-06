---
title: ISSAsynchStatus (OLE DB) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- ISSAsynchStatus (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- ISSAsynchStatus interface
ms.assetid: c643f09f-9ccc-4d8b-9243-3cde86c2bd46
author: rothja
ms.author: jroth
ms.openlocfilehash: 4489f9d1ad576d49d885842f6969f9b61065791c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616040"
---
# <a name="issasynchstatus-ole-db"></a><span data-ttu-id="fa91b-102">ISSAsynchStatus (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="fa91b-102">ISSAsynchStatus (OLE DB)</span></span>
  <span data-ttu-id="fa91b-103">**ISSAsynchStatus** unterstützt asynchrone [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Vorgänge.</span><span class="sxs-lookup"><span data-stu-id="fa91b-103">**ISSAsynchStatus** exposes support for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] asynchronous operations.</span></span> <span data-ttu-id="fa91b-104">Hierbei handelt es sich um eine optionale Schnittstelle, die von der OLE DB-Kernschnittstelle **IDBAsynchStatus**erbt.</span><span class="sxs-lookup"><span data-stu-id="fa91b-104">This is an optional interface that inherits from the core OLE DB interface **IDBAsynchStatus**.</span></span> <span data-ttu-id="fa91b-105">Neben den von **IDBAsynchStatus** geerbten Methoden **Abort** und **GetStatus**stellt **ISSAsynchStatus** eine neue Methode bereit, die verwendet wird, um zu warten, bis ein asynchroner Vorgang abgeschlossen ist oder ein Timeout auftritt.</span><span class="sxs-lookup"><span data-stu-id="fa91b-105">In addition to the **Abort** and **GetStatus** methods inherited from **IDBAsynchStatus**, **ISSAsynchStatus** provides one new method that is used to wait until an asynchronous operation has completed or a time-out occurs.</span></span>  
  
|<span data-ttu-id="fa91b-106">Methode</span><span class="sxs-lookup"><span data-stu-id="fa91b-106">Method</span></span>|<span data-ttu-id="fa91b-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="fa91b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fa91b-108">ISSAsynchStatus::Abort &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="fa91b-108">ISSAsynchStatus::Abort &#40;OLE DB&#41;</span></span>](issasynchstatus-abort-ole-db.md)|<span data-ttu-id="fa91b-109">Bricht einen asynchron ausgeführten Vorgang ab.</span><span class="sxs-lookup"><span data-stu-id="fa91b-109">Cancels an asynchronously executing operation.</span></span>|  
|[<span data-ttu-id="fa91b-110">ISSAsynchStatus::GetStatus &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="fa91b-110">ISSAsynchStatus::GetStatus &#40;OLE DB&#41;</span></span>](issasynchstatus-getstatus-ole-db.md)|<span data-ttu-id="fa91b-111">Gibt den Status eines asynchron ausgeführten Vorgangs zurück.</span><span class="sxs-lookup"><span data-stu-id="fa91b-111">Returns the status of an asynchronously executing operation.</span></span>|  
|[<span data-ttu-id="fa91b-112">ISSAsynchStatus::WaitForAsynchCompletion &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="fa91b-112">ISSAsynchStatus::WaitForAsynchCompletion &#40;OLE DB&#41;</span></span>](issasynchstatus-waitforasynchcompletion-ole-db.md)|<span data-ttu-id="fa91b-113">Wartet, bis der asynchron ausgeführte Vorgang abgeschlossen ist oder ein Timeout auftritt.</span><span class="sxs-lookup"><span data-stu-id="fa91b-113">Waits until the asynchronously executing operation is complete or a time-out occurs.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa91b-114">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="fa91b-114">Remarks</span></span>  
 <span data-ttu-id="fa91b-115">Die **ISSAsynchStatus** -Implementierung der **ISSAsynchStatus::GetStatus** -Methode ist mit der **IDBAsynchStatus::GetStatus** -Methode identisch, gibt jedoch anstelle von DB_E_CANCELED E_UNEXPECTED zurück, wenn die Initialisierung eines Datenquellenobjekts abgebrochen wird (wenngleich **ISSAsynchStatus::WaitForAsynchCompletion** DB_E_CANCELED zurückgibt).</span><span class="sxs-lookup"><span data-stu-id="fa91b-115">The **ISSAsynchStatus** implementation of the **ISSAsynchStatus::GetStatus** method is the same as the **IDBAsynchStatus::GetStatus** method except that if the initialization of a data source object is aborted, E_UNEXPECTED is returned rather than DB_E_CANCELED (although **ISSAsynchStatus::WaitForAsynchCompletion** returns DB_E_CANCELED).</span></span> <span data-ttu-id="fa91b-116">Dies ist darauf zurückzuführen, dass das Datenquellenobjekt nach einem Abbruchvorgang nicht mehr den gewöhnlichen Status aufweist, sodass weitere Initialisierungsvorgänge durchgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="fa91b-116">This is because the data source object is not left in the usual state following an abort operation, so that further initialization operations may be attempted.</span></span>  
  
 <span data-ttu-id="fa91b-117">Die folgenden Methoden unterstützen die Verwendung der asynchronen Ausführung in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="fa91b-117">The following methods support the use of asynchronous execution in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="fa91b-118">**ICommand::Execute**</span><span class="sxs-lookup"><span data-stu-id="fa91b-118">**ICommand::Execute**</span></span>  
  
-   <span data-ttu-id="fa91b-119">**IOpenRowset::OpenRowset**</span><span class="sxs-lookup"><span data-stu-id="fa91b-119">**IOpenRowset::OpenRowset**</span></span>  
  
-   <span data-ttu-id="fa91b-120">**IMultipleResults::GetResult**</span><span class="sxs-lookup"><span data-stu-id="fa91b-120">**IMultipleResults::GetResult**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa91b-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fa91b-121">See Also</span></span>  
 <span data-ttu-id="fa91b-122">[Schnittstellen &#40;OLE DB&#41;](../../database-engine/dev-guide/interfaces-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="fa91b-122">[Interfaces &#40;OLE DB&#41;](../../database-engine/dev-guide/interfaces-ole-db.md) </span></span>  
 [<span data-ttu-id="fa91b-123">Ausführen asynchroner Vorgänge</span><span class="sxs-lookup"><span data-stu-id="fa91b-123">Performing Asynchronous Operations</span></span>](../native-client/features/performing-asynchronous-operations.md)  
  
  
