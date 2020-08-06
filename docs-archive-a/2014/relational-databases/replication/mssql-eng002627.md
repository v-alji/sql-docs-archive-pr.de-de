---
title: MSSQL_ENG002627 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG002627 error
ms.assetid: 7f4136ac-3784-4a41-a98c-8a02308e4883
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: cf481635d6a24570792c9da04fe71ebea885ce5b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725482"
---
# <a name="mssql_eng002627"></a><span data-ttu-id="d572a-102">MSSQL_ENG002627</span><span class="sxs-lookup"><span data-stu-id="d572a-102">MSSQL_ENG002627</span></span>
    
## <a name="message-details"></a><span data-ttu-id="d572a-103">Meldungsdetails</span><span class="sxs-lookup"><span data-stu-id="d572a-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d572a-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="d572a-104">Product Name</span></span>|<span data-ttu-id="d572a-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d572a-105">SQL Server</span></span>|  
|<span data-ttu-id="d572a-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="d572a-106">Event ID</span></span>|<span data-ttu-id="d572a-107">2627</span><span class="sxs-lookup"><span data-stu-id="d572a-107">2627</span></span>|  
|<span data-ttu-id="d572a-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="d572a-108">Event Source</span></span>|<span data-ttu-id="d572a-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d572a-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d572a-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="d572a-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="d572a-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="d572a-111">Symbolic Name</span></span>|<span data-ttu-id="d572a-112">–</span><span class="sxs-lookup"><span data-stu-id="d572a-112">N/A</span></span>|  
|<span data-ttu-id="d572a-113">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="d572a-113">Message Text</span></span>|<span data-ttu-id="d572a-114">Verletzung der %1!s!-Einschränkung '%2!s!'.</span><span class="sxs-lookup"><span data-stu-id="d572a-114">Violation of %ls constraint '%.\*ls'.</span></span> <span data-ttu-id="d572a-115">Ein doppelter Schlüssel kann in das „%.\*ls“-Objekt nicht eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="d572a-115">Cannot insert duplicate key in object '%.\*ls'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d572a-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="d572a-116">Explanation</span></span>  
 <span data-ttu-id="d572a-117">Das ist ein allgemeiner Fehler, der unabhängig davon ausgelöst werden kann, ob eine Datenbank repliziert wird.</span><span class="sxs-lookup"><span data-stu-id="d572a-117">This is a general error that can be raised regardless of whether a database is replicated.</span></span> <span data-ttu-id="d572a-118">Bei replizierten Datenbanken wird der Fehler in der Regel ausgelöst, weil Primärschlüssel in der Topologie nicht richtig verwaltet wurden.</span><span class="sxs-lookup"><span data-stu-id="d572a-118">In replicated databases, the error is typically raised because primary keys have not been managed appropriately across the topology.</span></span> <span data-ttu-id="d572a-119">In einer verteilten Umgebung muss unbedingt sichergestellt werden, dass in mehreren Knoten nicht der gleiche Wert in eine Primärschlüsselspalte oder eine andere eindeutige Spalte eingefügt wird.</span><span class="sxs-lookup"><span data-stu-id="d572a-119">In a distributed environment it is essential to ensure that the same value is not inserted into a primary key column or any other unique column at more than one node.</span></span> <span data-ttu-id="d572a-120">Die folgenden Ursachen können zugrunde liegen:</span><span class="sxs-lookup"><span data-stu-id="d572a-120">Possible causes include the following:</span></span>  
  
-   <span data-ttu-id="d572a-121">Einfügungen und Updates an einer Zeile finden in mehreren Knoten statt.</span><span class="sxs-lookup"><span data-stu-id="d572a-121">Inserts and updates to a row are occurring at more than one node.</span></span> <span data-ttu-id="d572a-122">Die Mergereplikation und aktualisierbare Abonnements für Transaktionsreplikationen stellen jeweils eine Konflikterkennung und -lösung bereit. Dennoch ist es besser, eine bestimmte Zeile nur in einem Knoten einzufügen oder zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="d572a-122">Merge replication and updatable subscriptions for transactional replication both provide conflict detection and resolution, but it is still preferable to insert or update a given row at only one node.</span></span> <span data-ttu-id="d572a-123">Die Peer-zu-Peer-Transaktionsreplikation stellt keine Konflikterkennung und -lösung bereit. Einfügungen und Updates müssen partitioniert werden.</span><span class="sxs-lookup"><span data-stu-id="d572a-123">Peer-to-peer transactional does not provide conflict detection and resolution; it requires that inserts and updates be partitioned.</span></span>  
  
-   <span data-ttu-id="d572a-124">Auf einem Abonnenten wurde eine Zeile eingefügt, die schreibgeschützt sein sollte.</span><span class="sxs-lookup"><span data-stu-id="d572a-124">A row was inserted at a Subscriber that should be read-only.</span></span> <span data-ttu-id="d572a-125">Abonnenten von Momentaufnahmeveröffentlichungen sollten als schreibgeschützt behandelt werden, ebenso wie Abonnenten von Transaktionsveröffentlichungen, außer es werden aktualisierbare Abonnements oder die Peer-zu-Peer-Transaktionsreplikation verwendet.</span><span class="sxs-lookup"><span data-stu-id="d572a-125">Subscribers to snapshot publications should be treated as read-only, as should Subscribers to transactional publications unless updatable subscriptions or peer-to-peer transactional replication is used.</span></span>  
  
-   <span data-ttu-id="d572a-126">Es wird eine Tabelle mit einer Identitätsspalte verwendet, die Spalte wird jedoch nicht ordnungsgemäß verwaltet.</span><span class="sxs-lookup"><span data-stu-id="d572a-126">A table with an identity column is being used, but the column is not managed appropriately.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d572a-127">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="d572a-127">User Action</span></span>  
 <span data-ttu-id="d572a-128">Die erforderliche Aktion hängt davon ab, weshalb der Fehler ausgelöst wurde:</span><span class="sxs-lookup"><span data-stu-id="d572a-128">The action required depends on the reason the error was raised:</span></span>  
  
-   <span data-ttu-id="d572a-129">Einfügungen und Updates an einer Zeile finden in mehreren Knoten statt.</span><span class="sxs-lookup"><span data-stu-id="d572a-129">Inserts and updates to a row are occurring at more than one node.</span></span>  
  
     <span data-ttu-id="d572a-130">Unabhängig vom Typ der verwendeten Replikation wird empfohlen, Einfügungen und Updates möglichst zu partitionieren, da dies den Verarbeitungsaufwand bei der Konflikterkennung und -lösung reduziert.</span><span class="sxs-lookup"><span data-stu-id="d572a-130">Regardless of the type of replication used, we recommend that you partition inserts and updates whenever possible, because this reduces the processing required for conflict detection and resolution.</span></span> <span data-ttu-id="d572a-131">Bei der Peer-zu-Peer-Transaktionsreplikation ist eine Partitionierung von Einfügungen und Updates erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d572a-131">For peer-to-peer transactional replication, partitioning inserts and updates is required.</span></span> <span data-ttu-id="d572a-132">Weitere Informationen finden Sie unter [Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="d572a-132">For more information, see [Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md).</span></span>  
  
-   <span data-ttu-id="d572a-133">Auf einem Abonnenten wurde eine Zeile eingefügt, die schreibgeschützt sein sollte.</span><span class="sxs-lookup"><span data-stu-id="d572a-133">A row was inserted at a Subscriber that should be read-only.</span></span>  
  
     <span data-ttu-id="d572a-134">Fügen Sie auf dem Abonnenten keine Zeilen ein und aktualisieren Sie keine Zeilen, es sei denn Sie verwenden die Mergereplikation, die Transaktionsreplikation mit aktualisierbaren Abonnements oder die Peer-zu-Peer-Transaktionsreplikation.</span><span class="sxs-lookup"><span data-stu-id="d572a-134">Do not insert or update rows at the Subscriber unless you are using merge replication, transactional replication with updatable subscriptions, or peer-to-peer transactional replication.</span></span>  
  
-   <span data-ttu-id="d572a-135">Es wird eine Tabelle mit einer Identitätsspalte verwendet, die Spalte wird jedoch nicht ordnungsgemäß verwaltet.</span><span class="sxs-lookup"><span data-stu-id="d572a-135">A table with an identity column is being used, but the column is not managed appropriately.</span></span>  
  
     <span data-ttu-id="d572a-136">Bei der Mergereplikation und der Transaktionsreplikation mit aktualisierbaren Abonnements sollten Identitätsspalten automatisch durch die Replikation verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="d572a-136">For merge replication and transactional replication with updatable subscriptions, identity columns should be managed automatically by replication.</span></span> <span data-ttu-id="d572a-137">Bei der Peer-zu-Peer-Transaktionsreplikation müssen sie manuell verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="d572a-137">For peer-to-peer transactional replication, they must be managed manually.</span></span> <span data-ttu-id="d572a-138">Weitere Informationen finden Sie unter [Replizieren von Identitätsspalten](publish/replicate-identity-columns.md).</span><span class="sxs-lookup"><span data-stu-id="d572a-138">For more information, see [Replicate Identity Columns](publish/replicate-identity-columns.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d572a-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d572a-139">See Also</span></span>  
 <span data-ttu-id="d572a-140">[Fehler- und Ereignisreferenz &#40;Replikation&#41;](errors-and-events-reference-replication.md) </span><span class="sxs-lookup"><span data-stu-id="d572a-140">[Errors and Events Reference &#40;Replication&#41;](errors-and-events-reference-replication.md) </span></span>  
 <span data-ttu-id="d572a-141">[Mergereplikation](merge/merge-replication.md) </span><span class="sxs-lookup"><span data-stu-id="d572a-141">[Merge Replication](merge/merge-replication.md) </span></span>  
 <span data-ttu-id="d572a-142">[Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md) </span><span class="sxs-lookup"><span data-stu-id="d572a-142">[Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md) </span></span>  
 [<span data-ttu-id="d572a-143">Updatable Subscriptions for Transactional Replication</span><span class="sxs-lookup"><span data-stu-id="d572a-143">Updatable Subscriptions for Transactional Replication</span></span>](transactional/updatable-subscriptions-for-transactional-replication.md)  
  
  
