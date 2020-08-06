---
title: MSSQLSERVER_3961 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3961 (Database Engine error)
ms.assetid: 3bbc6965-6445-400c-940a-2d85b037513f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f55be9288b3c2e559633d0f67709829466fc8815
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621515"
---
# <a name="mssqlserver_3961"></a><span data-ttu-id="6bbe8-102">MSSQLSERVER_3961</span><span class="sxs-lookup"><span data-stu-id="6bbe8-102">MSSQLSERVER_3961</span></span>
    
## <a name="details"></a><span data-ttu-id="6bbe8-103">Details</span><span class="sxs-lookup"><span data-stu-id="6bbe8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6bbe8-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="6bbe8-104">Product Name</span></span>|<span data-ttu-id="6bbe8-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="6bbe8-105">SQL Server</span></span>|  
|<span data-ttu-id="6bbe8-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="6bbe8-106">Event ID</span></span>|<span data-ttu-id="6bbe8-107">3961</span><span class="sxs-lookup"><span data-stu-id="6bbe8-107">3961</span></span>|  
|<span data-ttu-id="6bbe8-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="6bbe8-108">Event Source</span></span>|<span data-ttu-id="6bbe8-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="6bbe8-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="6bbe8-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="6bbe8-110">Component</span></span>|<span data-ttu-id="6bbe8-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="6bbe8-111">SQLEngine</span></span>|  
|<span data-ttu-id="6bbe8-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="6bbe8-112">Symbolic Name</span></span>|<span data-ttu-id="6bbe8-113">XACT_METADATA_INVALID</span><span class="sxs-lookup"><span data-stu-id="6bbe8-113">XACT_METADATA_INVALID</span></span>|  
|<span data-ttu-id="6bbe8-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="6bbe8-114">Message Text</span></span>|<span data-ttu-id="6bbe8-115">Fehler bei der Momentaufnahmeisolationstransaktion in der '%.\*ls'-Datenbank, weil das von der Anweisung zugegriffene Objekt durch eine DDL-Anweisung in einer anderen gleichzeitigen Transaktion seit dem Beginn dieser Transaktion geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="6bbe8-115">Snapshot isolation transaction failed in database '%.\*ls' because the object accessed by the statement has been modified by a DDL statement in another concurrent transaction since the start of this transaction.</span></span>  <span data-ttu-id="6bbe8-116">Der Vorgang ist nicht zulässig, weil für die Metadaten keine Versionsverwaltung durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6bbe8-116">It is disallowed because the metadata is not versioned.</span></span> <span data-ttu-id="6bbe8-117">Ein gleichzeitiges Update von Metadaten kann zu Inkonsistenz führen, wenn es zu einer Vermischung mit der Momentaufnahmeisolation kommt.</span><span class="sxs-lookup"><span data-stu-id="6bbe8-117">A concurrent update to metadata can lead to inconsistency if mixed with snapshot isolation.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6bbe8-118">Erklärung</span><span class="sxs-lookup"><span data-stu-id="6bbe8-118">Explanation</span></span>  
 <span data-ttu-id="6bbe8-119">Dieser Fehler kann auftreten, wenn Sie im Rahmen der Momentaufnahmeisolation Metadaten abfragen und eine gleichzeitige DDL-Anweisung zum Aktualisieren der Metadaten vorhanden ist, auf die unter der Momentaufnahmeisolation zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="6bbe8-119">This error can occur if you are querying metadata under snapshot isolation and there is a concurrent DDL statement that updates the metadata that is being accessed under snapshot isolation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="6bbe8-120">unterstützt keine Versionsverwaltung von Metadaten.</span><span class="sxs-lookup"><span data-stu-id="6bbe8-120">does not support versioning of metadata.</span></span> <span data-ttu-id="6bbe8-121">Aus diesem Grund gelten Einschränkungen dafür, welche DDL-Vorgänge innerhalb einer expliziten Transaktion durchgeführt werden können, die der Momentaufnahmeisolation unterliegen.</span><span class="sxs-lookup"><span data-stu-id="6bbe8-121">For this reason, there are restrictions on what DDL operations can be performed within an explicit transaction running under snapshot isolation.</span></span> <span data-ttu-id="6bbe8-122">Eine implizite Transaktion ist laut Definition eine einzelne Anweisung, mit der die Semantik der Momentaufnahmeisolation auch bei Verwendung von DDL-Anweisungen erzwungen werden kann.</span><span class="sxs-lookup"><span data-stu-id="6bbe8-122">An implicit transaction, by definition, is a single statement which makes it possible to enforce the semantics of snapshot isolation even with DDL statements.</span></span> <span data-ttu-id="6bbe8-123">Die folgenden DDL-Anweisungen sind bei der Momentaufnahme-Isolationsstufe nach einer BEGIN TRANSACTION-Anweisung nicht zulässig: ALTER TABLE, CREATE INDEX, CREATE XML INDEX, ALTER INDEX, DROP INDEX, DBCC REINDEX, ALTER PARTITION FUNCTION, ALTER PARTITION SCHEME oder eine beliebige CLR-DDL-Anweisung (Common Language Runtime).</span><span class="sxs-lookup"><span data-stu-id="6bbe8-123">The following DDL statements are not permitted under snapshot isolation after a BEGIN TRANSACTION statement: ALTER TABLE, CREATE INDEX, CREATE XML INDEX, ALTER INDEX, DROP INDEX, DBCC REINDEX, ALTER PARTITION FUNCTION, ALTER PARTITION SCHEME, or any common language runtime (CLR) DDL statement.</span></span> <span data-ttu-id="6bbe8-124">Diese Anweisungen sind zulässig, wenn Sie die Momentaufnahmeisolation in impliziten Transaktionen verwenden.</span><span class="sxs-lookup"><span data-stu-id="6bbe8-124">These statements are permitted when you are using snapshot isolation within implicit transactions.</span></span> <span data-ttu-id="6bbe8-125">Eine implizite Transaktion ist laut Definition eine einzelne Anweisung, mit der die Semantik der Momentaufnahmeisolation auch bei Verwendung von DDL-Anweisungen erzwungen werden kann.</span><span class="sxs-lookup"><span data-stu-id="6bbe8-125">An implicit transaction, by definition, is a single statement which makes it possible to enforce the semantics of snapshot isolation even with DDL statements.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6bbe8-126">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="6bbe8-126">User Action</span></span>  
 <span data-ttu-id="6bbe8-127">Ändern Sie die Momentaufnahmeisolationsstufe vor dem Abfragen von Metadaten in eine Isolationsstufe, bei der es sich nicht um eine Momentaufnahmeisolationsstufe handelt, z. B. Read Committed.</span><span class="sxs-lookup"><span data-stu-id="6bbe8-127">Change the snapshot isolation level to a non-snapshot isolation level such as read committed before querying metadata.</span></span>  
  
  
