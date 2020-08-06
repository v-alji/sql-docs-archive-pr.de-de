---
title: Unterstützen von verteilten Transaktionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- OLE DB, transactions
- distributed transactions [OLE DB]
- MS DTC
- transactions [OLE DB]
- SQL Server Native Client OLE DB provider, transactions
- ITransactionJoin interface
- MS DTC, about distributed transaction support
ms.assetid: d250b43b-9260-4ea4-90cc-57d9a2f67ea7
author: rothja
ms.author: jroth
ms.openlocfilehash: 5a30a44dc007852922aa71685728b26e5bb872c3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722726"
---
# <a name="supporting-distributed-transactions"></a><span data-ttu-id="d6309-102">Unterstützen von verteilten Transaktionen</span><span class="sxs-lookup"><span data-stu-id="d6309-102">Supporting Distributed Transactions</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="d6309-103">Consumer von Native Client OLE DB-Anbietern können mit der **itransaktionjoin:: JoinTransaction** -Methode an einer verteilten Transaktion teilnehmen, die von Microsoft Distributed Transaction Coordinator (MS DTC) koordiniert wird.</span><span class="sxs-lookup"><span data-stu-id="d6309-103">Native Client OLE DB provider consumers can use the **ITransactionJoin::JoinTransaction** method to participate in a distributed transaction coordinated by Microsoft Distributed Transaction Coordinator (MS DTC).</span></span>  
  
 <span data-ttu-id="d6309-104">MS DTC macht COM-Objekte verfügbar, mit denen Clients koordinierte Transaktionen initiieren und an koordinierten Transaktionen teilnehmen können, die sich über mehrere Verbindungen zu verschiedenen Datenspeichern erstrecken.</span><span class="sxs-lookup"><span data-stu-id="d6309-104">MS DTC exposes COM objects that allow clients to initiate and participate in coordinated transactions across multiple connections to a variety of data stores.</span></span> <span data-ttu-id="d6309-105">Zum Initiieren einer Transaktion verwendet der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Consumer des Native Client OLE DB-Anbieters die Schnittstelle MS DTC **itransaktiondispenser** .</span><span class="sxs-lookup"><span data-stu-id="d6309-105">To initiate a transaction, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider consumer uses the MS DTC **ITransactionDispenser** interface.</span></span> <span data-ttu-id="d6309-106">Das **BeginTransaction**-Element von **ITransactionDispenser** gibt einen Verweis auf ein verteiltes Transaktionsobjekt zurück.</span><span class="sxs-lookup"><span data-stu-id="d6309-106">The **BeginTransaction** member of **ITransactionDispenser** returns a reference on a distributed transaction object.</span></span> <span data-ttu-id="d6309-107">Dieser Verweis wird [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mithilfe von **JoinTransaction**an den Native Client OLE DB-Anbieter übermittelt.</span><span class="sxs-lookup"><span data-stu-id="d6309-107">This reference is passed to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider using **JoinTransaction**.</span></span>  
  
 <span data-ttu-id="d6309-108">MS DTC unterstützt asynchrone „Commit“- und „Abort“-Funktionen bei verteilten Transaktionen.</span><span class="sxs-lookup"><span data-stu-id="d6309-108">MS DTC supports asynchronous commit and abort on distributed transactions.</span></span> <span data-ttu-id="d6309-109">Für Benachrichtigungen über den asynchronen Transaktionsstatus implementiert der Consumer die **ITransactionOutcomeEvents**-Schnittstelle und verbindet die Schnittstelle mit einem MS DTC-Transaktionsobjekt.</span><span class="sxs-lookup"><span data-stu-id="d6309-109">For notification on asynchronous transaction status, the consumer implements the **ITransactionOutcomeEvents** interface and connects the interface to an MS DTC transaction object.</span></span>  
  
 <span data-ttu-id="d6309-110">Für verteilte Transaktionen implementiert der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter **itransaktionjoin:: JoinTransaction** -Parameter wie folgt.</span><span class="sxs-lookup"><span data-stu-id="d6309-110">For distributed transactions, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider implements **ITransactionJoin::JoinTransaction** parameters as follows.</span></span>  
  
|<span data-ttu-id="d6309-111">Parameter</span><span class="sxs-lookup"><span data-stu-id="d6309-111">Parameter</span></span>|<span data-ttu-id="d6309-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d6309-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d6309-113">*punkTransactionCoord*</span><span class="sxs-lookup"><span data-stu-id="d6309-113">*punkTransactionCoord*</span></span>|<span data-ttu-id="d6309-114">Ein Zeiger auf ein MS DTC-Transaktionsobjekt</span><span class="sxs-lookup"><span data-stu-id="d6309-114">A pointer to an MS DTC transaction object.</span></span>|  
|<span data-ttu-id="d6309-115">*IsoLevel*</span><span class="sxs-lookup"><span data-stu-id="d6309-115">*IsoLevel*</span></span>|<span data-ttu-id="d6309-116">Wird vom [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter ignoriert.</span><span class="sxs-lookup"><span data-stu-id="d6309-116">Ignored by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider.</span></span> <span data-ttu-id="d6309-117">Die Isolationsstufe für MS DTC-koordinierte Transaktionen wird festgelegt, wenn der Consumer vom MS DTC ein Transaktionsobjekt abruft.</span><span class="sxs-lookup"><span data-stu-id="d6309-117">The isolation level for MS DTC-coordinated transactions is determined when the consumer acquires a transaction object from MS DTC.</span></span>|  
|<span data-ttu-id="d6309-118">*IsoFlags*</span><span class="sxs-lookup"><span data-stu-id="d6309-118">*IsoFlags*</span></span>|<span data-ttu-id="d6309-119">Muss den Wert 0 (null) haben.</span><span class="sxs-lookup"><span data-stu-id="d6309-119">Must be 0.</span></span> <span data-ttu-id="d6309-120">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter gibt XACT_E_NOISORETAIN zurück, wenn vom Consumer ein anderer Wert angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="d6309-120">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider returns XACT_E_NOISORETAIN if any other value is specified by the consumer.</span></span>|  
|<span data-ttu-id="d6309-121">*POtherOptions*</span><span class="sxs-lookup"><span data-stu-id="d6309-121">*POtherOptions*</span></span>|<span data-ttu-id="d6309-122">Wenn nicht NULL, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fordert der Native Client OLE DB-Anbieter das Options-Objekt von der-Schnittstelle an.</span><span class="sxs-lookup"><span data-stu-id="d6309-122">If not NULL, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider requests the options object from the interface.</span></span> <span data-ttu-id="d6309-123">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter gibt XACT_E_NOTIMEOUT zurück, wenn der *ulTimeout* -Member des Options-Objekts nicht 0 (null) ist.</span><span class="sxs-lookup"><span data-stu-id="d6309-123">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider returns XACT_E_NOTIMEOUT if the options object's *ulTimeout* member is not zero.</span></span> <span data-ttu-id="d6309-124">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter ignoriert den Wert des *szDescription* -Members.</span><span class="sxs-lookup"><span data-stu-id="d6309-124">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider ignores the value of the *szDescription* member.</span></span>|  
  
 <span data-ttu-id="d6309-125">In diesem Beispiel wird eine Transaktion mit MS DTC koordiniert.</span><span class="sxs-lookup"><span data-stu-id="d6309-125">This example coordinates transaction by using MS DTC.</span></span>  
  
```  
// Interfaces used in the example.  
IDBCreateSession*       pIDBCreateSession   = NULL;  
ITransactionJoin*       pITransactionJoin   = NULL;  
IDBCreateCommand*       pIDBCreateCommand   = NULL;  
IRowset*                pIRowset            = NULL;  
  
// Transaction dispenser and transaction from MS DTC.  
ITransactionDispenser*  pITransactionDispenser = NULL;  
ITransaction*           pITransaction       = NULL;  
  
    HRESULT             hr;  
  
// Get the command creation interface for the session.  
if (FAILED(hr = pIDBCreateSession->CreateSession(NULL,  
     IID_IDBCreateCommand, (IUnknown**) &pIDBCreateCommand)))  
    {  
    // Process error from session creation. Release any references and  
    // return.  
    }  
  
// Get a transaction dispenser object from MS DTC and  
// start a transaction.  
if (FAILED(hr = DtcGetTransactionManager(NULL, NULL,  
    IID_ITransactionDispenser, 0, 0, NULL,  
    (void**) &pITransactionDispenser)))  
    {  
    // Process error message from MS DTC, release any references,  
    // and then return.  
    }  
if (FAILED(hr = pITransactionDispenser->BeginTransaction(  
    NULL, ISOLATIONLEVEL_READCOMMITTED, ISOFLAG_RETAIN_DONTCARE,  
    NULL, &pITransaction)))  
    {  
    // Process error message from MS DTC, release any references,  
    // and then return.  
    }  
  
// Join the transaction.  
if (FAILED(pIDBCreateCommand->QueryInterface(IID_ITransactionJoin,  
    (void**) &pITransactionJoin)))  
    {  
    // Process failure to get an interface, release any references, and  
    // then return.  
    }  
if (FAILED(pITransactionJoin->JoinTransaction(  
    (IUnknown*) pITransaction, 0, 0, NULL)))  
    {  
    // Process join failure, release any references, and then return.  
    }  
  
// Get data into a rowset, then update the data. Functions are not  
// illustrated in this example.  
if (FAILED(hr = ExecuteCommand(pIDBCreateCommand, &pIRowset)))  
    {  
    // Release any references and return.  
    }  
  
// If rowset data update fails, then terminate the transaction, else  
// commit. The example doesn't retain the rowset.  
if (FAILED(hr = UpdateDataInRowset(pIRowset, bDelayedUpdate)))  
    {  
    // Get error from update, then abort.  
    pITransaction->Abort(NULL, FALSE, FALSE);  
    }  
else  
    {  
    if (FAILED(hr = pITransaction->Commit(FALSE, 0, 0)))  
        {  
        // Get error from failed commit.  
        //  
        // If a distributed commit fails, application logic could  
        // analyze failure and retry. In this example, terminate. The   
        // consumer must resolve this somehow.  
        pITransaction->Abort(NULL, FALSE, FALSE);  
        }  
    }  
  
if (FAILED(hr))  
    {  
    // Update of data or commit failed. Release any references and  
    // return.  
    }  
  
// Un-enlist from the distributed transaction by setting   
// the transaction object pointer to NULL.  
if (FAILED(pITransactionJoin->JoinTransaction(  
    (IUnknown*) NULL, 0, 0, NULL)))  
    {  
    // Process failure, and then return.  
    }  
  
// Release any references and continue.  
```  
  
## <a name="see-also"></a><span data-ttu-id="d6309-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d6309-126">See Also</span></span>  
 [<span data-ttu-id="d6309-127">Transaktionen</span><span class="sxs-lookup"><span data-stu-id="d6309-127">Transactions</span></span>](transactions.md)  
  
  
