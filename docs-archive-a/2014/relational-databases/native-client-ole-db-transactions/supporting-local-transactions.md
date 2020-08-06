---
title: Unterstützen von lokalen Transaktionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- OLE DB, transactions
- autocommit mode
- transactions [OLE DB]
- ITransactionLocal interface
- SQL Server Native Client OLE DB provider, transactions
- local transactions [OLE DB]
ms.assetid: 78f2e5fc-b6fb-4eda-9f71-991a4d6c4902
author: rothja
ms.author: jroth
ms.openlocfilehash: a9bc11a038e56517aa42619117c371c1319b9ffe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620824"
---
# <a name="supporting-local-transactions"></a><span data-ttu-id="9cacb-102">Unterstützen lokaler Transaktionen</span><span class="sxs-lookup"><span data-stu-id="9cacb-102">Supporting Local Transactions</span></span>
  <span data-ttu-id="9cacb-103">Eine Sitzung begrenzt den Transaktions Bereich für eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] lokale Transaktion eines Native Client OLE DB Anbieters.</span><span class="sxs-lookup"><span data-stu-id="9cacb-103">A session delimits transaction scope for a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider local transaction.</span></span> <span data-ttu-id="9cacb-104">Wenn der Native Client OLE DB-Anbieter in Richtung eines Consumers [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] eine Anforderung an eine verbundene Instanz von sendet [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , stellt die Anforderung eine Arbeitseinheit für den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter dar.</span><span class="sxs-lookup"><span data-stu-id="9cacb-104">When, at the direction of a consumer, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider submits a request to a connected instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the request constitutes a unit of work for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider.</span></span> <span data-ttu-id="9cacb-105">Lokale Transaktionen wrappen immer eine oder mehrere Arbeitseinheiten in einer einzelnen systemeigenen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Client OLE DB-Anbieter Sitzung.</span><span class="sxs-lookup"><span data-stu-id="9cacb-105">Local transactions always wrap one or more units of work on a single [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider session.</span></span>  
  
 <span data-ttu-id="9cacb-106">Mithilfe des standardmäßigen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Autocommit-Modus von Native Client OLE DB-Anbieters wird eine einzelne Arbeitseinheit als Bereich einer lokalen Transaktion behandelt.</span><span class="sxs-lookup"><span data-stu-id="9cacb-106">Using the default [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider autocommit mode, a single unit of work is treated as the scope of a local transaction.</span></span> <span data-ttu-id="9cacb-107">Nur eine Einheit nimmt an der lokalen Transaktion teil.</span><span class="sxs-lookup"><span data-stu-id="9cacb-107">Only one unit participates in the local transaction.</span></span> <span data-ttu-id="9cacb-108">Wenn eine Sitzung erstellt wird, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] beginnt der Native Client OLE DB-Anbieter eine Transaktion für die Sitzung.</span><span class="sxs-lookup"><span data-stu-id="9cacb-108">When a session is created, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider begins a transaction for the session.</span></span> <span data-ttu-id="9cacb-109">Nach der erfolgreichen Verarbeitung einer Arbeitseinheit wird ein Commit für die Arbeit ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="9cacb-109">Upon successful completion of a work unit, the work is committed.</span></span> <span data-ttu-id="9cacb-110">Bei Auftreten eines Fehlers wird ein Rollback für den begonnenen Teil der Arbeit ausgeführt, und der Fehler wird dem Consumer gemeldet.</span><span class="sxs-lookup"><span data-stu-id="9cacb-110">On failure, any work begun is rolled back and the error is reported to the consumer.</span></span> <span data-ttu-id="9cacb-111">In beiden Fällen beginnt der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter eine neue lokale Transaktion für die Sitzung, sodass alle Aufgaben innerhalb einer Transaktion durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9cacb-111">In either case, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider begins a new local transaction for the session so that all work is conducted within a transaction.</span></span>  
  
 <span data-ttu-id="9cacb-112">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Consumer des Native Client OLE DB-Anbieters kann eine präzisere Kontrolle über den lokalen Transaktions Bereich mithilfe der **itransaktionlocal** -Schnittstelle leiten.</span><span class="sxs-lookup"><span data-stu-id="9cacb-112">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider consumer can direct more precise control over local transaction scope by using the **ITransactionLocal** interface.</span></span> <span data-ttu-id="9cacb-113">Wenn eine Consumersitzung eine Transaktion initiiert, werden alle Arbeitseinheiten der Sitzung zwischen dem Anfangspunkt der Transaktion und eventuellen Aufrufen der Methode **Commit** oder der Methode **Abort** als eine unteilbare Einheit behandelt.</span><span class="sxs-lookup"><span data-stu-id="9cacb-113">When a consumer session initiates a transaction, all session work units between the transaction start point and the eventual **Commit** or **Abort** method calls are treated as an atomic unit.</span></span> <span data-ttu-id="9cacb-114">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter beginnt implizit eine Transaktion, wenn er vom Consumer an ihn weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="9cacb-114">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider implicitly begins a transaction when directed to do so by the consumer.</span></span> <span data-ttu-id="9cacb-115">Wenn der Consumer keine Beibehaltung anfordert, kehrt die Sitzung zum Verhalten der übergeordneten Transaktionsebene zurück, in der Regel ist das der Autocommitmodus.</span><span class="sxs-lookup"><span data-stu-id="9cacb-115">If the consumer does not request retention, the session reverts to parent transaction-level behavior, most commonly autocommit mode.</span></span>  
  
 <span data-ttu-id="9cacb-116">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter unterstützt **ITransaction local:: Start Transaction** -Parameter wie folgt.</span><span class="sxs-lookup"><span data-stu-id="9cacb-116">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports **ITransactionLocal::StartTransaction** parameters as follows.</span></span>  
  
|<span data-ttu-id="9cacb-117">Parameter</span><span class="sxs-lookup"><span data-stu-id="9cacb-117">Parameter</span></span>|<span data-ttu-id="9cacb-118">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9cacb-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9cacb-119">*isoLevel*[in]</span><span class="sxs-lookup"><span data-stu-id="9cacb-119">*isoLevel*[in]</span></span>|<span data-ttu-id="9cacb-120">Die innerhalb dieser Transaktion zu verwendende Isolationsstufe.</span><span class="sxs-lookup"><span data-stu-id="9cacb-120">The isolation level to be used with this transaction.</span></span> <span data-ttu-id="9cacb-121">In lokalen Transaktionen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] unterstützt der Native Client OLE DB-Anbieter Folgendes:</span><span class="sxs-lookup"><span data-stu-id="9cacb-121">In local transactions, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports the following:</span></span><br /><br /> <span data-ttu-id="9cacb-122">-ISOLATIONLEVEL_UNSPECIFIED</span><span class="sxs-lookup"><span data-stu-id="9cacb-122">-   ISOLATIONLEVEL_UNSPECIFIED</span></span><br /><span data-ttu-id="9cacb-123">-ISOLATIONLEVEL_CHAOS</span><span class="sxs-lookup"><span data-stu-id="9cacb-123">-   ISOLATIONLEVEL_CHAOS</span></span><br /><span data-ttu-id="9cacb-124">-ISOLATIONLEVEL_READUNCOMMITTED</span><span class="sxs-lookup"><span data-stu-id="9cacb-124">-   ISOLATIONLEVEL_READUNCOMMITTED</span></span><br /><span data-ttu-id="9cacb-125">-ISOLATIONLEVEL_READCOMMITTED</span><span class="sxs-lookup"><span data-stu-id="9cacb-125">-   ISOLATIONLEVEL_READCOMMITTED</span></span><br /><span data-ttu-id="9cacb-126">-ISOLATIONLEVEL_REPEATABLEREAD</span><span class="sxs-lookup"><span data-stu-id="9cacb-126">-   ISOLATIONLEVEL_REPEATABLEREAD</span></span><br /><span data-ttu-id="9cacb-127">-ISOLATIONLEVEL_CURSORSTABILITY</span><span class="sxs-lookup"><span data-stu-id="9cacb-127">-   ISOLATIONLEVEL_CURSORSTABILITY</span></span><br /><span data-ttu-id="9cacb-128">-ISOLATIONLEVEL_REPEATABLEREAD</span><span class="sxs-lookup"><span data-stu-id="9cacb-128">-   ISOLATIONLEVEL_REPEATABLEREAD</span></span><br /><span data-ttu-id="9cacb-129">-ISOLATIONLEVEL_SERIALIZABLE</span><span class="sxs-lookup"><span data-stu-id="9cacb-129">-   ISOLATIONLEVEL_SERIALIZABLE</span></span><br /><span data-ttu-id="9cacb-130">-ISOLATIONLEVEL_ISOLATED</span><span class="sxs-lookup"><span data-stu-id="9cacb-130">-   ISOLATIONLEVEL_ISOLATED</span></span><br /><span data-ttu-id="9cacb-131">-ISOLATIONLEVEL_SNAPSHOT **Hinweis:** ab [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] ist ISOLATIONLEVEL_SNAPSHOT für das *isoLevel* -Argument gültig, unabhängig davon, ob die Versionsverwaltung für die Datenbank aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="9cacb-131">-   ISOLATIONLEVEL_SNAPSHOT **Note:**  Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], ISOLATIONLEVEL_SNAPSHOT is valid for the *isoLevel* argument whether or not versioning is enabled for the database.</span></span> <span data-ttu-id="9cacb-132">Jedoch tritt ein Fehler auf, wenn der Benutzer versucht, eine Anweisung auszuführen und die Versionsverwaltung nicht aktiviert und/oder die Datenbank nicht schreibgeschützt ist.</span><span class="sxs-lookup"><span data-stu-id="9cacb-132">However, an error will occur if the user attempts to execute a statement and versioning is not enabled and/or the database is not read-only.</span></span> <span data-ttu-id="9cacb-133">Zudem tritt bei einer Verbindung mit einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Version, die älter als [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] ist, der Fehler XACT_E_ISOLATIONLEVEL auf, wenn ISOLATIONLEVEL_SNAPSHOT als *isoLevel* angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="9cacb-133">In addition, the error XACT_E_ISOLATIONLEVEL will occur if ISOLATIONLEVEL_SNAPSHOT is specified as the *isoLevel* when connected to a version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] earlier than [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>|  
|<span data-ttu-id="9cacb-134">*isoFlags*[in]</span><span class="sxs-lookup"><span data-stu-id="9cacb-134">*isoFlags*[in]</span></span>|<span data-ttu-id="9cacb-135">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter gibt einen Fehler für einen beliebigen Wert ungleich 0 (null) zurück.</span><span class="sxs-lookup"><span data-stu-id="9cacb-135">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider returns an error for any value other than zero.</span></span>|  
|<span data-ttu-id="9cacb-136">*pOtherOptions*[in]</span><span class="sxs-lookup"><span data-stu-id="9cacb-136">*pOtherOptions*[in]</span></span>|<span data-ttu-id="9cacb-137">Wenn nicht NULL, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fordert der Native Client OLE DB-Anbieter das Options-Objekt von der-Schnittstelle an.</span><span class="sxs-lookup"><span data-stu-id="9cacb-137">If not NULL, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider requests the options object from the interface.</span></span> <span data-ttu-id="9cacb-138">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter gibt XACT_E_NOTIMEOUT zurück, wenn der *ulTimeout* -Member des Options-Objekts nicht 0 (null) ist.</span><span class="sxs-lookup"><span data-stu-id="9cacb-138">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider returns XACT_E_NOTIMEOUT if the options object's *ulTimeout* member is not zero.</span></span> <span data-ttu-id="9cacb-139">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter ignoriert den Wert des *szDescription* -Members.</span><span class="sxs-lookup"><span data-stu-id="9cacb-139">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider ignores the value of the *szDescription* member.</span></span>|  
|<span data-ttu-id="9cacb-140">*pulTransactionLevel*[out]</span><span class="sxs-lookup"><span data-stu-id="9cacb-140">*pulTransactionLevel*[out]</span></span>|<span data-ttu-id="9cacb-141">Wenn der Wert nicht NULL ist, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] gibt der Native Client OLE DB-Anbieter die auf dem Systemebene der Transaktion zurück.</span><span class="sxs-lookup"><span data-stu-id="9cacb-141">If not NULL, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider returns the nested level of the transaction.</span></span>|  
  
 <span data-ttu-id="9cacb-142">Für lokale Transaktionen implementiert der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter **ITransaction:: Abort** -Parameter wie folgt.</span><span class="sxs-lookup"><span data-stu-id="9cacb-142">For local transactions, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider implements **ITransaction::Abort** parameters as follows.</span></span>  
  
|<span data-ttu-id="9cacb-143">Parameter</span><span class="sxs-lookup"><span data-stu-id="9cacb-143">Parameter</span></span>|<span data-ttu-id="9cacb-144">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9cacb-144">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9cacb-145">*pboidReason*[in]</span><span class="sxs-lookup"><span data-stu-id="9cacb-145">*pboidReason*[in]</span></span>|<span data-ttu-id="9cacb-146">Wird bei Festlegung ignoriert.</span><span class="sxs-lookup"><span data-stu-id="9cacb-146">Ignored if set.</span></span> <span data-ttu-id="9cacb-147">Kann daher auch NULL sein.</span><span class="sxs-lookup"><span data-stu-id="9cacb-147">Can safely be NULL.</span></span>|  
|<span data-ttu-id="9cacb-148">*fRetaining*[in]</span><span class="sxs-lookup"><span data-stu-id="9cacb-148">*fRetaining*[in]</span></span>|<span data-ttu-id="9cacb-149">Wenn der Wert TRUE lautet, wird eine neue Transaktion implizit für die Sitzung begonnen.</span><span class="sxs-lookup"><span data-stu-id="9cacb-149">When TRUE, a new transaction is implicitly begun for the session.</span></span> <span data-ttu-id="9cacb-150">Für die Transaktion muss vom Consumer ein Commit ausgeführt werden oder sie muss beendet werden.</span><span class="sxs-lookup"><span data-stu-id="9cacb-150">The transaction must be committed or terminated by the consumer.</span></span> <span data-ttu-id="9cacb-151">Wenn der Wert false ist, wird der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Autocommit-Modus für die Sitzung vom Native Client OLE DB-Anbieter wieder hergestellt.</span><span class="sxs-lookup"><span data-stu-id="9cacb-151">When FALSE, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider reverts to autocommit mode for the session.</span></span>|  
|<span data-ttu-id="9cacb-152">*fAsync*[in]</span><span class="sxs-lookup"><span data-stu-id="9cacb-152">*fAsync*[in]</span></span>|<span data-ttu-id="9cacb-153">Der asynchrone Abbruch wird vom [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9cacb-153">Asynchronous abort is not supported by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider.</span></span> <span data-ttu-id="9cacb-154">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter gibt XACT_E_NOTSUPPORTED zurück, wenn der Wert nicht false ist.</span><span class="sxs-lookup"><span data-stu-id="9cacb-154">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider returns XACT_E_NOTSUPPORTED if the value is not FALSE.</span></span>|  
  
 <span data-ttu-id="9cacb-155">Für lokale Transaktionen implementiert der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter **ITransaction:: Commit** -Parameter wie folgt.</span><span class="sxs-lookup"><span data-stu-id="9cacb-155">For local transactions, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider implements **ITransaction::Commit** parameters as follows.</span></span>  
  
|<span data-ttu-id="9cacb-156">Parameter</span><span class="sxs-lookup"><span data-stu-id="9cacb-156">Parameter</span></span>|<span data-ttu-id="9cacb-157">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9cacb-157">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9cacb-158">*fRetaining*[in]</span><span class="sxs-lookup"><span data-stu-id="9cacb-158">*fRetaining*[in]</span></span>|<span data-ttu-id="9cacb-159">Wenn der Wert TRUE lautet, wird eine neue Transaktion implizit für die Sitzung begonnen.</span><span class="sxs-lookup"><span data-stu-id="9cacb-159">When TRUE, a new transaction is implicitly begun for the session.</span></span> <span data-ttu-id="9cacb-160">Für die Transaktion muss vom Consumer ein Commit ausgeführt werden oder sie muss beendet werden.</span><span class="sxs-lookup"><span data-stu-id="9cacb-160">The transaction must be committed or terminated by the consumer.</span></span> <span data-ttu-id="9cacb-161">Wenn der Wert false ist, wird der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Autocommit-Modus für die Sitzung vom Native Client OLE DB-Anbieter wieder hergestellt.</span><span class="sxs-lookup"><span data-stu-id="9cacb-161">When FALSE, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider reverts to autocommit mode for the session.</span></span>|  
|<span data-ttu-id="9cacb-162">*grfTC*[in]</span><span class="sxs-lookup"><span data-stu-id="9cacb-162">*grfTC*[in]</span></span>|<span data-ttu-id="9cacb-163">Asynchrone und Phase 1-Rückgaben werden vom [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9cacb-163">Asynchronous and phase one returns are not supported by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider.</span></span> <span data-ttu-id="9cacb-164">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter gibt XACT_E_NOTSUPPORTED für jeden anderen Wert als XACTTC_SYNC zurück.</span><span class="sxs-lookup"><span data-stu-id="9cacb-164">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider returns XACT_E_NOTSUPPORTED for any value other than XACTTC_SYNC.</span></span>|  
|<span data-ttu-id="9cacb-165">*grfRM*[in]</span><span class="sxs-lookup"><span data-stu-id="9cacb-165">*grfRM*[in]</span></span>|<span data-ttu-id="9cacb-166">Muss den Wert 0 (null) haben.</span><span class="sxs-lookup"><span data-stu-id="9cacb-166">Must be 0.</span></span>|  
  
 <span data-ttu-id="9cacb-167">Die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Rowsets des Native Client OLE DB-Anbieters in der Sitzung werden bei einem lokalen Commit-oder Abbruch Vorgang basierend auf den Werten der Rowseteigenschaften DBPROP_ABORTPRESERVE und DBPROP_COMMITPRESERVE beibehalten.</span><span class="sxs-lookup"><span data-stu-id="9cacb-167">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider rowsets on the session are preserved on a local commit or abort operation based on the values of the rowset properties DBPROP_ABORTPRESERVE and DBPROP_COMMITPRESERVE.</span></span> <span data-ttu-id="9cacb-168">Standardmäßig sind diese Eigenschaften VARIANT_FALSE, und alle [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB Provider-Rowsets in der Sitzung gehen nach einem Abbruch-oder Commitvorgang verloren.</span><span class="sxs-lookup"><span data-stu-id="9cacb-168">By default, these properties are both VARIANT_FALSE and all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider rowsets on the session are lost following an abort or commit operation.</span></span>  
  
 <span data-ttu-id="9cacb-169">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter implementiert nicht die **itransaktionobject** -Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="9cacb-169">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not implement the **ITransactionObject** interface.</span></span> <span data-ttu-id="9cacb-170">Bei einem Versuch des Consumers, einen Verweis auf die Schnittstelle abzurufen, wird E_NOINTERFACE zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9cacb-170">A consumer attempt to retrieve a reference on the interface returns E_NOINTERFACE.</span></span>  
  
 <span data-ttu-id="9cacb-171">Im folgenden Beispiel wird **ITransactionLocal** verwendet.</span><span class="sxs-lookup"><span data-stu-id="9cacb-171">This example uses **ITransactionLocal**.</span></span>  
  
```  
// Interfaces used in the example.  
IDBCreateSession*   pIDBCreateSession   = NULL;  
ITransaction*       pITransaction       = NULL;  
IDBCreateCommand*   pIDBCreateCommand   = NULL;  
IRowset*            pIRowset            = NULL;  
  
HRESULT             hr;  
  
// Get the command creation and local transaction interfaces for the  
// session.  
if (FAILED(hr = pIDBCreateSession->CreateSession(NULL,  
     IID_IDBCreateCommand, (IUnknown**) &pIDBCreateCommand)))  
    {  
    // Process error from session creation. Release any references and  
    // return.  
    }  
  
if (FAILED(hr = pIDBCreateCommand->QueryInterface(IID_ITransactionLocal,  
    (void**) &pITransaction)))  
    {  
    // Process error. Release any references and return.  
    }  
  
// Start the local transaction.  
if (FAILED(hr = ((ITransactionLocal*) pITransaction)->StartTransaction(  
    ISOLATIONLEVEL_REPEATABLEREAD, 0, NULL, NULL)))  
    {  
    // Process error from StartTransaction. Release any references and  
    // return.  
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
    // Get error from update, then terminate.  
    pITransaction->Abort(NULL, FALSE, FALSE);  
    }  
else  
    {  
    if (FAILED(hr = pITransaction->Commit(FALSE, XACTTC_SYNC, 0)))  
        {  
        // Get error from failed commit.  
        }  
    }  
  
if (FAILED(hr))  
    {  
    // Update of data or commit failed. Release any references and  
    // return.  
    }  
  
// Release any references and continue.  
```  
  
## <a name="see-also"></a><span data-ttu-id="9cacb-172">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9cacb-172">See Also</span></span>  
 <span data-ttu-id="9cacb-173">[Transaktionen](transactions.md) </span><span class="sxs-lookup"><span data-stu-id="9cacb-173">[Transactions](transactions.md) </span></span>  
 [<span data-ttu-id="9cacb-174">Arbeiten mit der Momentaufnahme Isolation</span><span class="sxs-lookup"><span data-stu-id="9cacb-174">Working with Snapshot Isolation</span></span>](../native-client/features/working-with-snapshot-isolation.md)  
  
  
