---
title: Ausführen asynchroner Vorgänge | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- initialization [SQL Server Native Client]
- database connections [SQL Server Native Client]
- data access [SQL Server Native Client], asynchronous operations
- connections [SQL Server Native Client]
- asynchronous operations [SQL Server Native Client]
- rowsets [SQL Server], initializing
- SQLNCLI, asynchronous operations
- SQL Server Native Client, asynchronous operations
ms.assetid: 8fbd84b4-69cb-4708-9f0f-bbdf69029bcc
author: rothja
ms.author: jroth
ms.openlocfilehash: 4f7e8f4481923cd7da537f921248865d4fff7280
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698061"
---
# <a name="performing-asynchronous-operations"></a><span data-ttu-id="f2384-102">Ausführen asynchroner Vorgänge</span><span class="sxs-lookup"><span data-stu-id="f2384-102">Performing Asynchronous Operations</span></span>
  [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="f2384-103">ermöglicht es Anwendungen, asynchrone Datenbankvorgänge auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f2384-103">allows applications to perform asynchronous database operations.</span></span> <span data-ttu-id="f2384-104">Die asynchrone Verarbeitung ermöglicht es Methoden, Rückgaben unverzüglich zu übermitteln, ohne den aufrufenden Thread zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="f2384-104">Asynchronous processing enables methods to return immediately without blocking on the calling thread.</span></span> <span data-ttu-id="f2384-105">Dadurch kann ein Großteil der Leistungsfähigkeit und Flexibilität des Multithreadings genutzt werden, ohne dass Entwickler Threads explizit erstellen oder die Synchronisation durchführen müssen.</span><span class="sxs-lookup"><span data-stu-id="f2384-105">This allows much of the power and flexibility of multithreading, without requiring the developer to explicitly create threads or handle synchronization.</span></span> <span data-ttu-id="f2384-106">Anwendungen fordern die asynchrone Verarbeitung an, wenn sie eine Datenbankverbindung oder das Ergebnis einer Befehlsausführung initialisieren.</span><span class="sxs-lookup"><span data-stu-id="f2384-106">Applications request asynchronous processing when initializing a database connection, or when initializing the result from the execution of a command.</span></span>  
  
## <a name="opening-and-closing-a-database-connection"></a><span data-ttu-id="f2384-107">Öffnen und Schließen einer Datenbankverbindung</span><span class="sxs-lookup"><span data-stu-id="f2384-107">Opening and Closing a Database Connection</span></span>  
 <span data-ttu-id="f2384-108">Bei Verwendung des [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client-OLE DB Anbieters können Anwendungen, die für die asynchrone Initialisierung eines Datenquellen Objekts entworfen wurden, das DBPROPVAL_ASYNCH_INITIALIZE Bit in der DBPROP_INIT_ASYNCH-Eigenschaft vor dem Aufrufen von **IDBInitialize:: Initialisieren**festlegen.</span><span class="sxs-lookup"><span data-stu-id="f2384-108">When using the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider, applications designed to initialize a data source object asynchronously can set the DBPROPVAL_ASYNCH_INITIALIZE bit in the DBPROP_INIT_ASYNCH property prior to calling **IDBInitialize::Initialize**.</span></span> <span data-ttu-id="f2384-109">Wenn diese Eigenschaft festgelegt ist, antwortet der Anbieter unverzüglich auf den Aufruf von **Initialize** mit S_OK, wenn der Vorgang sofort ausgeführt wird, oder mit DB_S_ASYNCHRONOUS, wenn die Initialisierung asynchron fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="f2384-109">When this property is set, the provider returns immediately from the call to **Initialize** with either S_OK, if the operation has completed immediately, or DB_S_ASYNCHRONOUS, if the initialization is continuing asynchronously.</span></span> <span data-ttu-id="f2384-110">Anwendungen können die **IDBAsynchStatus** -oder [ISSAsynchStatus](../../native-client-ole-db-interfaces/issasynchstatus-ole-db.md)-Schnittstelle für das Datenquellen Objekt Abfragen und dann **IDBAsynchStatus:: GetStatus** oder[ISSAsynchStatus:: WaitForAsynchCompletion](../../native-client-ole-db-interfaces/issasynchstatus-waitforasynchcompletion-ole-db.md) aufrufen, um den Status der Initialisierung zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="f2384-110">Applications can query for the **IDBAsynchStatus** or [ISSAsynchStatus](../../native-client-ole-db-interfaces/issasynchstatus-ole-db.md)interface on the data source object, and then call **IDBAsynchStatus::GetStatus** or[ISSAsynchStatus::WaitForAsynchCompletion](../../native-client-ole-db-interfaces/issasynchstatus-waitforasynchcompletion-ole-db.md) to get the status of the initialization.</span></span>  
  
 <span data-ttu-id="f2384-111">Außerdem wurde dem DBPROPSET_SQLSERVERROWSET-Eigenschaftensatz die SSPROP_ISSAsynchStatus-Eigenschaft hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f2384-111">In addition, the SSPROP_ISSAsynchStatus property has been added to the DBPROPSET_SQLSERVERROWSET property set.</span></span> <span data-ttu-id="f2384-112">Anbieter, die die **ISSAsynchStatus**-Schnittstelle unterstützen, müssen diese Eigenschaft mit dem Wert VARIANT_TRUE implementieren.</span><span class="sxs-lookup"><span data-stu-id="f2384-112">Providers that support the **ISSAsynchStatus** interface must implement this property with a value of VARIANT_TRUE.</span></span>  
  
 <span data-ttu-id="f2384-113">**IDBAsynchStatus::Abort** oder [ISSAsynchStatus::Abort](../../native-client-ole-db-interfaces/issasynchstatus-abort-ole-db.md) kann aufgerufen werden, um den asynchronen Aufruf von **Initialize** abzubrechen.</span><span class="sxs-lookup"><span data-stu-id="f2384-113">**IDBAsynchStatus::Abort** or [ISSAsynchStatus::Abort](../../native-client-ole-db-interfaces/issasynchstatus-abort-ole-db.md) can be called to cancel the asynchronous **Initialize** call.</span></span> <span data-ttu-id="f2384-114">Der Consumer muss die asynchrone Datenquellinitialisierung explizit anfordern.</span><span class="sxs-lookup"><span data-stu-id="f2384-114">The consumer must explicitly request Asynchronous Data Source Initialization.</span></span> <span data-ttu-id="f2384-115">Andernfalls erfolgt die Rückgabe durch **IDBInitialize::Initialize** erst, wenn das Datenquellenobjekt vollständig initialisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="f2384-115">Otherwise, **IDBInitialize::Initialize** does not return until the data source object is completely initialized.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f2384-116">Datenquellen Objekte, die für das Verbindungspooling verwendet werden, können die **ISSAsynchStatus** -Schnittstelle im [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client-OLE DB Anbieter nicht abrufen.</span><span class="sxs-lookup"><span data-stu-id="f2384-116">Data source objects used for connection pooling cannot call the **ISSAsynchStatus** interface in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider.</span></span> <span data-ttu-id="f2384-117">Die **ISSAsynchStatus**-Schnittstelle wird nicht für Datenquellenobjekte aus dem Pool verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="f2384-117">The **ISSAsynchStatus** interface is not exposed for pooled data source objects.</span></span>  
>   
>  <span data-ttu-id="f2384-118">Wenn eine Anwendung die Verwendung der Cursor-Engine explizit erzwingt, unterstützen **IOpenRowset::OpenRowset** und **IMultipleResults::GetResult** keine asynchrone Verarbeitung.</span><span class="sxs-lookup"><span data-stu-id="f2384-118">If an application explicitly forces use of the cursor engine, **IOpenRowset::OpenRowset** and **IMultipleResults::GetResult** will not support asynchronous processing.</span></span>  
>   
>  <span data-ttu-id="f2384-119">Außerdem kann die Remoting-Proxy/Stub-DLL (in MDAC 2,8) die **ISSAsynchStatus** -Schnittstelle in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client nicht abrufen.</span><span class="sxs-lookup"><span data-stu-id="f2384-119">In addition, the remoting proxy/stub dll (in MDAC 2.8) cannot call the **ISSAsynchStatus** interface in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span></span> <span data-ttu-id="f2384-120">Die **ISSAsynchStatus**-Schnittstelle wird durch Remoting nicht verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="f2384-120">The **ISSAsynchStatus** interface is not exposed through remoting.</span></span>  
>   
>  <span data-ttu-id="f2384-121">Dienstkomponenten unterstützen **ISSAsynchStatus** nicht.</span><span class="sxs-lookup"><span data-stu-id="f2384-121">Service Components do not support **ISSAsynchStatus**.</span></span>  
  
## <a name="execution-and-rowset-initialization"></a><span data-ttu-id="f2384-122">Ausführung und Rowsetinitialisierung</span><span class="sxs-lookup"><span data-stu-id="f2384-122">Execution and Rowset Initialization</span></span>  
 <span data-ttu-id="f2384-123">Anwendungen, die dafür ausgelegt sind, das Ergebnis einer Befehlsausführung asynchron zu öffnen, können das DBPROPVAL_ASYNCH_INITIALIZE-Bit in der DBPROP_ROWSET_ASYNCH-Eigenschaft festlegen.</span><span class="sxs-lookup"><span data-stu-id="f2384-123">Applications designed to asynchronously open the result from the execution of a command can set the DBPROPVAL_ASYNCH_INITIALIZE bit in the DBPROP_ROWSET_ASYNCH property.</span></span> <span data-ttu-id="f2384-124">Wenn dieses Bit vor dem Aufrufen von **IDBInitialize::Initialize**, **ICommand::Execute**, **IOpenRowset::OpenRowset** oder **IMultipleResults::GetResult** festgelegt wird, muss das Argument *riid* auf IID_IDBAsynchStatus, IID_ISSAsynchStatus oder IID_Iunknown festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="f2384-124">When setting this bit prior to calling **IDBInitialize::Initialize**, **ICommand::Execute**, **IOpenRowset::OpenRowset** or **IMultipleResults::GetResult**, the *riid* argument must be set to IID_IDBAsynchStatus, IID_ISSAsynchStatus, or IID_IUnknown.</span></span>  
  
 <span data-ttu-id="f2384-125">Die Methode gibt unverzüglich S_OK zurück, wenn die Rowsetinitialisierung sofort ausgeführt wird, oder DB_S_ASYNCHRONOUS, wenn die Rowsetinitialisierung asynchron fortgesetzt wird, wobei *ppRowset* im Rowset auf die angeforderte Schnittstelle festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="f2384-125">The method returns immediately with S_OK if the rowset initialization completes immediately, or with DB_S_ASYNCHRONOUS if the rowset continues initializing asynchronously, with *ppRowset* set to the requested interface on the rowset.</span></span> <span data-ttu-id="f2384-126">Für den [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter kann diese Schnittstelle nur **IDBAsynchStatus** oder **ISSAsynchStatus**aufweisen.</span><span class="sxs-lookup"><span data-stu-id="f2384-126">For the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider, this interface can only be **IDBAsynchStatus** or **ISSAsynchStatus**.</span></span> <span data-ttu-id="f2384-127">Bis das Rowset vollständig initialisiert wurde, verhält sich diese Schnittstelle so, als befände sie sich im Zustand „Angehalten“. Der Aufruf von **QueryInterface** für andere Schnittstellen als **IID_IDBAsynchStatus** oder **IID_ISSAsynchStatus** führt möglicherweise zur Rückgabe von E_NOINTERFACE.</span><span class="sxs-lookup"><span data-stu-id="f2384-127">Until the rowset is fully initialized, this interface behaves as if it were in a suspended state, and calling **QueryInterface** for interfaces other than **IID_IDBAsynchStatus** or **IID_ISSAsynchStatus** may return E_NOINTERFACE.</span></span> <span data-ttu-id="f2384-128">Sofern der Consumer die asynchrone Verarbeitung nicht explizit anfordert, wird das Rowset synchron initialisiert.</span><span class="sxs-lookup"><span data-stu-id="f2384-128">Unless the consumer explicitly requests asynchronous processing, the rowset is initialized synchronously.</span></span> <span data-ttu-id="f2384-129">Alle angeforderten Schnittstellen sind verfügbar, wenn **IDBAsynchStaus::GetStatus** oder **ISSAsynchStatus::WaitForAsynchCompletion** die Rückgabe übermittelt, dass der asynchrone Vorgang abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="f2384-129">All requested interfaces are available when **IDBAsynchStaus::GetStatus** or **ISSAsynchStatus::WaitForAsynchCompletion** returns with the indication that asynchronous operation is complete.</span></span> <span data-ttu-id="f2384-130">Das bedeutet nicht notwendigerweise, dass das Rowset vollständig aufgefüllt ist, jedoch ist es komplett und voll funktionstüchtig.</span><span class="sxs-lookup"><span data-stu-id="f2384-130">This does not necessarily mean that the rowset is fully populated, but it is complete and fully functional.</span></span>  
  
 <span data-ttu-id="f2384-131">Wenn der ausgeführte Befehl kein Rowset zurückgibt, so gibt er doch unverzüglich ein Objekt zurück, das **IDBAsynchStatus** unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f2384-131">If the executed command does not return a rowset, it still returns immediately with an object that supports **IDBAsynchStatus**.</span></span>  
  
 <span data-ttu-id="f2384-132">Wenn Sie mehrere Ergebnisse von der asynchronen Befehlsausführung benötigen, sollten Sie Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="f2384-132">If you need to get multiple results from asynchronous command execution, you should:</span></span>  
  
-   <span data-ttu-id="f2384-133">Legen Sie das DBPROPVAL_ASYNCH_INITIALIZE-Bit der DBPROP_ROWSET_ASYNCH-Eigenschaft vor dem Ausführen des Befehls fest.</span><span class="sxs-lookup"><span data-stu-id="f2384-133">Set the DBPROPVAL_ASYNCH_INITIALIZE bit of the DBPROP_ROWSET_ASYNCH property, before executing the command.</span></span>  
  
-   <span data-ttu-id="f2384-134">Rufen Sie **ICommand::Execute** auf, und fordern Sie **IMultipleResults** an.</span><span class="sxs-lookup"><span data-stu-id="f2384-134">Call **ICommand::Execute**, and request **IMultipleResults**.</span></span>  
  
 <span data-ttu-id="f2384-135">Die **IDBAsynchStatus**-Schnittstelle und die **ISSAsynchStatus**-Schnittstelle können dann angefordert werden, indem die Schnittstelle für mehrere Ergebnisse mit **QueryInterface** abgefragt wird.</span><span class="sxs-lookup"><span data-stu-id="f2384-135">The **IDBAsynchStatus** and **ISSAsynchStatus** interfaces can then be obtained by querying the multiple results interface using **QueryInterface**.</span></span>  
  
 <span data-ttu-id="f2384-136">Wenn die Ausführung des Befehls abgeschlossen ist, kann **IMultipleResults** wie gewohnt verwendet werden. Es gibt jedoch eine Ausnahme für den synchronen Fall: Möglicherweise wird DB_S_ASYNCHRONOUS zurückgegeben; in diesem Fall kann mit **IDBAsynchStatus** oder **ISSAsynchStatus** ermittelt werden, wann der Vorgang abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="f2384-136">When the command has finished executing, **IMultipleResults** can be used as normal, with one exception from the synchronous case: DB_S_ASYNCHRONOUS may be returned, in which case **IDBAsynchStatus** or **ISSAsynchStatus** can be used to determine when the operation is complete.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="f2384-137">Beispiele</span><span class="sxs-lookup"><span data-stu-id="f2384-137">Examples</span></span>  
 <span data-ttu-id="f2384-138">Im folgenden Beispiel ruft die Anwendung eine nicht blockierende Methode auf, führt andere Verarbeitungsvorgänge aus und kehrt dann zur Verarbeitung der Ergebnisse zurück.</span><span class="sxs-lookup"><span data-stu-id="f2384-138">In the following example, the application calls a non-blocking method, does some other processing, and then returns to process the results.</span></span> <span data-ttu-id="f2384-139">**ISSAsynchStatus::WaitForAsynchCompletion** wartet auf das interne Ereignisobjekt, bis der asynchrone Vorgang ausgeführt wurde oder die durch *dwMilisecTimeOut* angegebene Zeit verstrichen ist.</span><span class="sxs-lookup"><span data-stu-id="f2384-139">**ISSAsynchStatus::WaitForAsynchCompletion** waits on the internal event object until the asynchronously executing operation is done or the amount of time specified by *dwMilisecTimeOut* is passed.</span></span>  
  
```  
// Set the DBPROPVAL_ASYNCH_INITIALIZE bit in the   
// DBPROP_ROWSET_ASYNCH property before calling Execute().  
  
DBPROPSET CmdPropset[1];  
DBPROP CmdProperties[1];  
  
CmdPropset[0].rgProperties = CmdProperties;  
CmdPropset[0].cProperties = 1;  
CmdPropset[0].guidPropertySet = DBPROPSET_ROWSET;  
  
// Set asynch mode for command.  
CmdProperties[0].dwPropertyID = DBPROP_ROWSET_ASYNCH;  
CmdProperties[0].vValue.vt = VT_I4;  
CmdProperties[0].vValue.lVal = DBPROPVAL_ASYNCH_INITIALIZE;  
CmdProperties[0].dwOptions = DBPROPOPTIONS_REQUIRED;  
  
hr = pICommandProps->SetProperties(1, CmdPropset);  
  
hr = pICommand->Execute(  
   pUnkOuter,  
   IID_ISSAsynchStatus,  
   pParams,  
   pcRowsAffected,  
   (IUnknown**)&pISSAsynchStatus);  
  
if (hr == DB_S_ASYNCHRONOUS)  
{  
   // Do some work here...  
  
   hr = pISSAsynchStatus->WaitForAsynchCompletion(dwMilisecTimeOut);  
   if ( hr == S_OK)  
   {  
      hr = pISSAsynchStatus->QueryInterface(IID_IRowset, (void**)&pRowset);  
      pISSAsynchStatus->Release();  
   }  
}  
```  
  
 <span data-ttu-id="f2384-140">**ISSAsynchStatus::WaitForAsynchCompletion** wartet auf das interne Ereignisobjekt, bis der asynchrone Vorgang ausgeführt oder der *dwMilisecTimeOut*-Wert übergeben wurde.</span><span class="sxs-lookup"><span data-stu-id="f2384-140">**ISSAsynchStatus::WaitForAsynchCompletion** waits on the internal event object until the asynchronously executing operation is done or the *dwMilisecTimeOut* value is passed.</span></span>  
  
 <span data-ttu-id="f2384-141">Im folgenden Beispiel wird die asynchrone Verarbeitung mit mehreren Resultsets veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="f2384-141">The following example shows asynchronous processing with multiple result sets:</span></span>  
  
```  
DBPROP CmdProperties[1];  
  
// Set asynch mode for command.  
CmdProperties[0].dwPropertyID = DBPROP_ROWSET_ASYNCH;  
CmdProperties[0].vValue.vt = VT_I4;  
CmdProperties[0].vValue.lVal = DBPROPVAL_ASYNCH_INITIALIZE;  
  
hr = pICommand->Execute(  
   pUnkOuter,  
   IID_IMultipleResults,  
   pParams,  
   pcRowsAffected,  
   (IUnknown**)&pIMultipleResults);  
  
// Use GetResults for ISSAsynchStatus.  
hr = pIMultipleResults->GetResult(IID_ISSAsynchStatus, (void **) &pISSAsynchStatus);  
  
if (hr == DB_S_ASYNCHRONOUS)  
{  
   // Do some work here...  
  
   hr = pISSAsynchStatus->WaitForAsynchCompletion(dwMilisecTimeOut);  
   if (hr == S_OK)  
   {  
      hr = pISSAsynchStatus->QueryInterface(IID_IRowset, (void**)&pRowset);  
      pISSAsynchStatus->Release();  
   }  
}  
```  
  
 <span data-ttu-id="f2384-142">Der Client kann den Status eines asynchron ausgeführten Vorgangs überprüfen, um das Blockieren zu verhindern, wie im folgenden Codebeispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="f2384-142">To prevent blocking, the client can check the status of a running asynchronous operation, as in the following example:</span></span>  
  
```  
// Set the DBPROPVAL_ASYNCH_INITIALIZE bit in the   
// DBPROP_ROWSET_ASYNCH property before calling Execute().  
hr = pICommand->Execute(  
   pUnkOuter,  
   IID_ISSAsynchStatus,  
   pParams,  
   pcRowsAffected,  
   (IUnknown**)&pISSAsynchStatus);   
  
if (hr == DB_S_ASYNCHRONOUS)  
{  
   do{  
      // Do some work...  
      hr = pISSAsynchStatus->GetStatus(DB_NULL_HCHAPTER, DBASYNCHOP_OPEN, NULL, NULL, &ulAsynchPhase, NULL);  
   }while (DBASYNCHPHASE_COMPLETE != ulAsynchPhase)  
   if SUCCEEDED(hr)  
   {  
      hr = pISSAsynchStatus->QueryInterface(IID_IRowset, (void**)&pRowset);  
   }  
   pIDBAsynchStatus->Release();  
}  
```  
  
 <span data-ttu-id="f2384-143">Im folgenden Beispiel wird veranschaulicht, wie Sie die gerade ausgeführte asynchrone Operation abbrechen können:</span><span class="sxs-lookup"><span data-stu-id="f2384-143">The following example demonstrates how you can cancel the currently running asynchronous operation:</span></span>  
  
```  
// Set the DBPROPVAL_ASYNCH_INITIALIZE bit in the   
// DBPROP_ROWSET_ASYNCH property before calling Execute().  
hr = pICommand->Execute(  
   pUnkOuter,  
   IID_ISSAsynchStatus,  
   pParams,  
   pcRowsAffected,  
   (IUnknown**)&pISSAsynchStatus);  
  
if (hr == DB_S_ASYNCHRONOUS)  
{  
   // Do some work...  
   hr = pISSAsynchStatus->Abort(DB_NULL_HCHAPTER, DBASYNCHOP_OPEN);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="f2384-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f2384-144">See Also</span></span>  
 <span data-ttu-id="f2384-145">[SQL Server Native Client-Funktionen](sql-server-native-client-features.md) </span><span class="sxs-lookup"><span data-stu-id="f2384-145">[SQL Server Native Client Features](sql-server-native-client-features.md) </span></span>  
 <span data-ttu-id="f2384-146">[Eigenschaften und Verhaltensweisen von Rowsets](../../native-client-ole-db-rowsets/rowset-properties-and-behaviors.md) </span><span class="sxs-lookup"><span data-stu-id="f2384-146">[Rowset Properties and Behaviors](../../native-client-ole-db-rowsets/rowset-properties-and-behaviors.md) </span></span>  
 [<span data-ttu-id="f2384-147">ISSAsynchStatus &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="f2384-147">ISSAsynchStatus &#40;OLE DB&#41;</span></span>](../../native-client-ole-db-interfaces/issasynchstatus-ole-db.md)  
  
  
