---
title: Transaktionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- OLE DB, transactions
- transactions [OLE DB]
- SQL Server Native Client OLE DB provider, transactions
ms.assetid: 3b41e33a-c1ca-4b2a-9464-312b0ed3ca89
author: rothja
ms.author: jroth
ms.openlocfilehash: 1067820e80f9c7a4e1af2c8a14c85bc9dbfdd6aa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620822"
---
# <a name="transactions"></a><span data-ttu-id="c90a6-102">Transaktionen</span><span class="sxs-lookup"><span data-stu-id="c90a6-102">Transactions</span></span>
  <span data-ttu-id="c90a6-103">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter implementiert lokale Transaktionsunterstützung.</span><span class="sxs-lookup"><span data-stu-id="c90a6-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider implements local transaction support.</span></span> <span data-ttu-id="c90a6-104">Der Consumer kann verteilte oder koordinierte Transaktionen mit Microsoft Distributed Transaction Coordinator (MS DTC) verwenden.</span><span class="sxs-lookup"><span data-stu-id="c90a6-104">The consumer can use distributed or coordinated transactions by using Microsoft Distributed Transaction Coordinator (MS DTC).</span></span> <span data-ttu-id="c90a6-105">Für Consumer, die Transaktions Steuerung benötigen, die mehrere Sitzungen umfasst, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] kann der Native Client OLE DB-Anbieter Transaktionen beitreten, die von MS DTC initiiert und verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="c90a6-105">For consumers requiring transaction control that spans multiple sessions, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider can join transactions initiated and maintained by MS DTC.</span></span>  
  
 <span data-ttu-id="c90a6-106">Standardmäßig verwendet der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter einen Autocommit-Transaktionsmodus, bei dem jede einzelne Aktion in einer Consumersitzung eine komplette Transaktion für eine Instanz von umfasst [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c90a6-106">By default, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider uses an autocommit transaction mode, where each discrete action on a consumer session comprises a complete transaction against an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c90a6-107">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Autocommitmodus des Native Client OLE DB-Anbieters ist lokal, und Autocommit-Transaktionen umfassen nie mehr als eine einzelne Sitzung.</span><span class="sxs-lookup"><span data-stu-id="c90a6-107">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider autocommit mode is local, and autocommit transactions never span more than a single session.</span></span>  
  
 <span data-ttu-id="c90a6-108">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter macht die **itransaktionlocal** -Schnittstelle verfügbar und ermöglicht dem Consumer, Transaktionen explizit und implizit auf einer einzelnen Verbindung mit einer Instanz von zu starten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c90a6-108">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes the **ITransactionLocal** interface, allowing the consumer to use explicitly and implicitly start transactions on a single connection to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c90a6-109">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter unterstützt keine netsted local-Transaktionen.</span><span class="sxs-lookup"><span data-stu-id="c90a6-109">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not support nested local transactions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c90a6-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="c90a6-110">In This Section</span></span>  
  
-   [<span data-ttu-id="c90a6-111">Unterstützen lokaler Transaktionen</span><span class="sxs-lookup"><span data-stu-id="c90a6-111">Supporting Local Transactions</span></span>](supporting-local-transactions.md)  
  
-   [<span data-ttu-id="c90a6-112">Unterstützen von verteilten Transaktionen</span><span class="sxs-lookup"><span data-stu-id="c90a6-112">Supporting Distributed Transactions</span></span>](supporting-distributed-transactions.md)  
  
-   [<span data-ttu-id="c90a6-113">Isolationsstufe &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="c90a6-113">Isolation Levels &#40;OLE DB&#41;</span></span>](isolation-levels-ole-db.md)  
  
## <a name="see-also"></a><span data-ttu-id="c90a6-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c90a6-114">See Also</span></span>  
 [<span data-ttu-id="c90a6-115">SQL Server Native Client &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="c90a6-115">SQL Server Native Client &#40;OLE DB&#41;</span></span>](../native-client/ole-db/sql-server-native-client-ole-db.md)  
  
  
