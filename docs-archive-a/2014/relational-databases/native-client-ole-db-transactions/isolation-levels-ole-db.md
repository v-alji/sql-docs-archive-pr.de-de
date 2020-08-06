---
title: Isolationsstufen (OLE DB) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- OLE DB, transactions
- isolation levels [OLE DB]
- transactions [OLE DB]
- SQL Server Native Client OLE DB provider, transactions
ms.assetid: d70ee72c-6e2a-4bcd-9456-4a697a866361
author: rothja
ms.author: jroth
ms.openlocfilehash: c7f6cbff4e68eaedd3e78a82cddd872ba5f8f19e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619079"
---
# <a name="isolation-levels-ole-db"></a><span data-ttu-id="e3a10-102">Isolationsstufen (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="e3a10-102">Isolation Levels (OLE DB)</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="e3a10-103">-Clients können Transaktionsisolationsstufen für eine Verbindung steuern.</span><span class="sxs-lookup"><span data-stu-id="e3a10-103">clients can control transaction-isolation levels for a connection.</span></span> <span data-ttu-id="e3a10-104">Zum Steuern der Transaktions Isolationsstufe [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] verwendet der Consumer des Native Client OLE DB Anbieters Folgendes:</span><span class="sxs-lookup"><span data-stu-id="e3a10-104">To control transaction-isolation level, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider consumer uses:</span></span>  
  
-   <span data-ttu-id="e3a10-105">DBPROPSET_SESSION Eigenschaften DBPROP_SESS_AUTOCOMMITISOLEVELS für den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] standardmäßigen Autocommitmodus des Native Client OLE DB Anbieters.</span><span class="sxs-lookup"><span data-stu-id="e3a10-105">DBPROPSET_SESSION property DBPROP_SESS_AUTOCOMMITISOLEVELS for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider default autocommit mode.</span></span>  
  
     <span data-ttu-id="e3a10-106">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Standardwert für den Native Client OLE DB-Anbieter für die Ebene ist DBPROPVAL_TI_READCOMMITTED.</span><span class="sxs-lookup"><span data-stu-id="e3a10-106">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider default for the level is DBPROPVAL_TI_READCOMMITTED.</span></span>  
  
-   <span data-ttu-id="e3a10-107">Der *isoLevel*-Parameter der **ITransactionLocal::StartTransaction**-Methode für lokale Manualcommit-Transaktionen.</span><span class="sxs-lookup"><span data-stu-id="e3a10-107">The *isoLevel* parameter of the **ITransactionLocal::StartTransaction** method for local manual-commit transactions.</span></span>  
  
-   <span data-ttu-id="e3a10-108">Der *isoLevel*-Parameter der **ITransactionDispenser::BeginTransaction**-Methode für MS DTC-koordinierte verteilte Transaktionen.</span><span class="sxs-lookup"><span data-stu-id="e3a10-108">The *isoLevel* parameter of the **ITransactionDispenser::BeginTransaction** method for MS DTC-coordinated distributed transactions.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="e3a10-109">lässt schreibgeschützten Zugriff auf die Dirty Read-Isolationsstufe zu.</span><span class="sxs-lookup"><span data-stu-id="e3a10-109">allows read-only access at the dirty read isolation level.</span></span> <span data-ttu-id="e3a10-110">Alle anderen Stufen schränken Parallelität ein, indem sie Sperren für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Objekte anwenden.</span><span class="sxs-lookup"><span data-stu-id="e3a10-110">All other levels restrict concurrency by applying locks to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] objects.</span></span> <span data-ttu-id="e3a10-111">Da der Client größere Parallelitätsstufen benötigt, wendet [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] größere Einschränkungen auf gleichzeitigem Zugriff auf Daten an.</span><span class="sxs-lookup"><span data-stu-id="e3a10-111">As the client requires greater concurrency levels, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] applies greater restrictions on concurrent access to data.</span></span> <span data-ttu-id="e3a10-112">Um die höchste Ebene des gleichzeitigen Zugriffs auf Daten aufrechtzuerhalten, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sollte der Consumer des Native Client OLE DB Anbieters seine Anforderungen für bestimmte Parallelitäts Ebenen intelligent steuern.</span><span class="sxs-lookup"><span data-stu-id="e3a10-112">To maintain the highest level of concurrent access to data, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider consumer should intelligently control its requests for specific concurrency levels.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] <span data-ttu-id="e3a10-113">hat Momentaufnahmeisolationsstufe eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e3a10-113">introduced snapshot isolation level.</span></span> <span data-ttu-id="e3a10-114">Weitere Informationen finden Sie unter [Arbeiten mit der Momentaufnahmeisolation](../native-client/features/working-with-snapshot-isolation.md).</span><span class="sxs-lookup"><span data-stu-id="e3a10-114">For more information, see [Working with Snapshot Isolation](../native-client/features/working-with-snapshot-isolation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3a10-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e3a10-115">See Also</span></span>  
 [<span data-ttu-id="e3a10-116">Transaktionen</span><span class="sxs-lookup"><span data-stu-id="e3a10-116">Transactions</span></span>](transactions.md)  
  
  
