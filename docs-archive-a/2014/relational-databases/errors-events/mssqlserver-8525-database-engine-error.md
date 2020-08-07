---
title: MSSQLSERVER_8525 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "8525"
helpviewer_keywords:
- 8525 (Database Engine error)
ms.assetid: 297867c1-691e-4d6b-a3be-a7575015ecfa
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 36db48ca2a9afd08dadcd12abc13b9978e227b00
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619861"
---
# <a name="mssqlserver_8525"></a><span data-ttu-id="57c82-102">MSSQLSERVER_8525</span><span class="sxs-lookup"><span data-stu-id="57c82-102">MSSQLSERVER_8525</span></span>
    
## <a name="details"></a><span data-ttu-id="57c82-103">Details</span><span class="sxs-lookup"><span data-stu-id="57c82-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="57c82-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="57c82-104">Product Name</span></span>|<span data-ttu-id="57c82-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="57c82-105">SQL Server</span></span>|  
|<span data-ttu-id="57c82-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="57c82-106">Event ID</span></span>|<span data-ttu-id="57c82-107">8525</span><span class="sxs-lookup"><span data-stu-id="57c82-107">8525</span></span>|  
|<span data-ttu-id="57c82-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="57c82-108">Event Source</span></span>|<span data-ttu-id="57c82-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="57c82-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="57c82-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="57c82-110">Component</span></span>|<span data-ttu-id="57c82-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="57c82-111">SQLEngine</span></span>|  
|<span data-ttu-id="57c82-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="57c82-112">Symbolic Name</span></span>||  
|<span data-ttu-id="57c82-113">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="57c82-113">Message Text</span></span>|<span data-ttu-id="57c82-114">Die verteilte Transaktion wurde abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="57c82-114">Distributed transaction completed.</span></span> <span data-ttu-id="57c82-115">Tragen Sie diese Sitzung in eine neue Transaktion oder in die NULL-Transaktion ein.</span><span class="sxs-lookup"><span data-stu-id="57c82-115">Either enlist this session in a new transaction or the NULL transaction.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="57c82-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="57c82-116">Explanation</span></span>  
 <span data-ttu-id="57c82-117">Für das Programmiermodell für die Verwendung des Distributed Transaction Coordinators mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], sind Anwendungen zum expliziten Eintragen in und Austragen aus einer verteilten Transaktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="57c82-117">The programming model for using the Distributed Transaction Coordinator with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] requires applications to explicitly enlist to and defect from a distributed transaction.</span></span>  
  
 <span data-ttu-id="57c82-118">Dieser Fehler tritt auf, wenn die folgenden vier Bedingungen erfüllt sind:</span><span class="sxs-lookup"><span data-stu-id="57c82-118">This error occurs when the following four conditions are met:</span></span>  
  
-   <span data-ttu-id="57c82-119">Die Anwendung wurde in eine verteilte Transaktion eingetragen.</span><span class="sxs-lookup"><span data-stu-id="57c82-119">The application has enlisted into a distributed transaction.</span></span>  
  
-   <span data-ttu-id="57c82-120">Die Transaktion wurde aus irgendeinem Grund beendet (durch einen Commit oder ein Rollback).</span><span class="sxs-lookup"><span data-stu-id="57c82-120">The transaction has ended, either committed or rolled back, for any reason.</span></span>  
  
-   <span data-ttu-id="57c82-121">Die Benutzeranwendung wurde nicht explizit aus einer verteilten Transaktion ausgetragen oder explizit in eine neue verteilte Transaktion eingetragen.</span><span class="sxs-lookup"><span data-stu-id="57c82-121">The user application has not explicitly defected from a distributed transaction or explicitly enlisted into a new distributed transaction.</span></span>  
  
-   <span data-ttu-id="57c82-122">Die Anwendung versucht jeden anderen Transaktionsvorgang als das Austragen aus einer vorhandenen verteilten Transaktion oder das Eintragen in eine neue verteilte Transaktion, z. B. das Ausgeben einer Abfrage oder das Starten einer lokalen Transaktion.</span><span class="sxs-lookup"><span data-stu-id="57c82-122">The application tries to do any transactional operation other than defecting from existing distributed transaction or enlisting to a new distributed transaction, such as issuing a query or starting a local transaction.</span></span>  
  
 <span data-ttu-id="57c82-123">Der Fehlerzustand 1 wird verwendet, wenn die Anwendung einen Vorgang ausführt, mit dem lokale Transaktionen erstellt werden, und Status 2 wird verwendet, wenn die Anwendung versucht, eine Eintragung in eine gebundene Sitzung vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="57c82-123">Error state 1 is used when the application performs an operation that creates local transactions, and state 2 is used when application tries to enlist to a bound session.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="57c82-124">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="57c82-124">User Action</span></span>  
 <span data-ttu-id="57c82-125">Nachdem eine Anwendung eine Eintragung in eine verteilte Transaktion vorgenommen hat, muss sich die Anwendung explizit aus der verteilten Transaktion austragen oder sich in eine andere verteilte Transaktion eintragen.</span><span class="sxs-lookup"><span data-stu-id="57c82-125">After an application has enlisted into a distributed transaction, the application must explicitly defect from the distributed transaction or enlist to another distributed transaction.</span></span> <span data-ttu-id="57c82-126">Damit wird implizit ein Austritt aus einer vorherigen eingetragenen Transaktion vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="57c82-126">This will implicitly defect from a previous enlisted transaction.</span></span> <span data-ttu-id="57c82-127">Informationen dazu, wie die genaue Syntax aus einer verteilten Transaktion ausgetragen oder in eine verteilte Transaktion eingetragen wird, finden Sie im Handbuch zur Programmierschnittstelle für die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="57c82-127">For the exact syntax to defect from or enlist to a distributed transaction, see the programming interface manual for the application.</span></span>  
  
  
