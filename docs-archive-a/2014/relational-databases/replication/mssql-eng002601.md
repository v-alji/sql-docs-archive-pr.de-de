---
title: MSSQL_ENG002601 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG002601 error
ms.assetid: 657c3ae6-9e4b-4c60-becc-4caf7435c1dc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c2e8340fef83749fd6d041af42566b10ed3542c2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724513"
---
# <a name="mssql_eng002601"></a><span data-ttu-id="d7067-102">MSSQL_ENG002601</span><span class="sxs-lookup"><span data-stu-id="d7067-102">MSSQL_ENG002601</span></span>
    
## <a name="message-details"></a><span data-ttu-id="d7067-103">Meldungsdetails</span><span class="sxs-lookup"><span data-stu-id="d7067-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d7067-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="d7067-104">Product Name</span></span>|<span data-ttu-id="d7067-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d7067-105">SQL Server</span></span>|  
|<span data-ttu-id="d7067-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="d7067-106">Event ID</span></span>|<span data-ttu-id="d7067-107">2601</span><span class="sxs-lookup"><span data-stu-id="d7067-107">2601</span></span>|  
|<span data-ttu-id="d7067-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="d7067-108">Event Source</span></span>|<span data-ttu-id="d7067-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d7067-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d7067-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="d7067-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="d7067-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="d7067-111">Symbolic Name</span></span>|<span data-ttu-id="d7067-112">–</span><span class="sxs-lookup"><span data-stu-id="d7067-112">N/A</span></span>|  
|<span data-ttu-id="d7067-113">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="d7067-113">Message Text</span></span>|<span data-ttu-id="d7067-114">Eine Zeile mit doppeltem Schlüssel kann in das „%1!s!“-Objekt mit dem eindeutigen „%.\*ls“-Index nicht eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="d7067-114">Cannot insert duplicate key row in object '%.\*ls' with unique index '%.\*ls'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d7067-115">Erklärung</span><span class="sxs-lookup"><span data-stu-id="d7067-115">Explanation</span></span>  
 <span data-ttu-id="d7067-116">Das ist ein allgemeiner Fehler, der unabhängig davon ausgelöst werden kann, ob eine Datenbank repliziert wird.</span><span class="sxs-lookup"><span data-stu-id="d7067-116">This is a general error that can be raised regardless of whether a database is replicated.</span></span> <span data-ttu-id="d7067-117">Bei replizierten Datenbanken wird der Fehler in der Regel ausgelöst, weil Primärschlüssel in der Topologie nicht richtig verwaltet wurden.</span><span class="sxs-lookup"><span data-stu-id="d7067-117">In replicated databases, the error is typically raised because primary keys have not been managed appropriately across the topology.</span></span> <span data-ttu-id="d7067-118">In einer verteilten Umgebung muss unbedingt sichergestellt werden, dass in mehreren Knoten nicht der gleiche Wert in eine Primärschlüsselspalte oder eine andere eindeutige Spalte eingefügt wird.</span><span class="sxs-lookup"><span data-stu-id="d7067-118">In a distributed environment it is essential to ensure that the same value is not inserted into a primary key column or any other unique column at more than one node.</span></span> <span data-ttu-id="d7067-119">Die folgenden Ursachen können zugrunde liegen:</span><span class="sxs-lookup"><span data-stu-id="d7067-119">Possible causes include the following:</span></span>  
  
-   <span data-ttu-id="d7067-120">Einfügungen und Updates an einer Zeile finden in mehreren Knoten statt.</span><span class="sxs-lookup"><span data-stu-id="d7067-120">Inserts and updates to a row are occurring at more than one node.</span></span> <span data-ttu-id="d7067-121">Die Mergereplikation und aktualisierbare Abonnements für Transaktionsreplikationen stellen jeweils eine Konflikterkennung und -lösung bereit. Dennoch ist es besser, eine bestimmte Zeile nur in einem Knoten einzufügen oder zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="d7067-121">Merge replication and updatable subscriptions for transactional replication both provide conflict detection and resolution, but it is still preferable to insert or update a given row at only one node.</span></span> <span data-ttu-id="d7067-122">Die Peer-zu-Peer-Transaktionsreplikation stellt keine Konflikterkennung und -lösung bereit. Einfügungen und Updates müssen partitioniert werden.</span><span class="sxs-lookup"><span data-stu-id="d7067-122">Peer-to-peer transactional does not provide conflict detection and resolution; it requires that inserts and updates be partitioned.</span></span>  
  
-   <span data-ttu-id="d7067-123">Auf einem Abonnenten wurde eine Zeile eingefügt, die schreibgeschützt sein sollte.</span><span class="sxs-lookup"><span data-stu-id="d7067-123">A row was inserted at a Subscriber that should be read-only.</span></span> <span data-ttu-id="d7067-124">Abonnenten von Momentaufnahmeveröffentlichungen sollten als schreibgeschützt behandelt werden, ebenso wie Abonnenten von Transaktionsveröffentlichungen, außer es werden aktualisierbare Abonnements oder die Peer-zu-Peer-Transaktionsreplikation verwendet.</span><span class="sxs-lookup"><span data-stu-id="d7067-124">Subscribers to snapshot publications should be treated as read-only, as should Subscribers to transactional publications unless updatable subscriptions or peer-to-peer transactional replication is used.</span></span>  
  
-   <span data-ttu-id="d7067-125">Es wird eine Tabelle mit einer Identitätsspalte verwendet, die Spalte wird jedoch nicht ordnungsgemäß verwaltet.</span><span class="sxs-lookup"><span data-stu-id="d7067-125">A table with an identity column is being used, but the column is not managed appropriately.</span></span>  
  
-   <span data-ttu-id="d7067-126">Bei der Mergereplikation kann dieser Fehler auch während eines INSERTs in die **MSmerge_contents**-Systemtabelle ausgelöst werden; die Fehlermeldung lautet dann ungefähr folgendermaßen: Eine Zeile mit doppeltem Schlüssel kann in das 'MSmerge_contents'-Objekt mit dem eindeutigen 'ucl1SycContents'-Index nicht eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="d7067-126">In merge replication, this error can also occur during an insert into the system table **MSmerge_contents**; the error raised is similar to: Cannot insert duplicate key row in object 'MSmerge_contents' with unique index 'ucl1SycContents.'</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d7067-127">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="d7067-127">User Action</span></span>  
 <span data-ttu-id="d7067-128">Die erforderliche Aktion hängt davon ab, weshalb der Fehler ausgelöst wurde:</span><span class="sxs-lookup"><span data-stu-id="d7067-128">The action required depends on the reason the error was raised:</span></span>  
  
-   <span data-ttu-id="d7067-129">Einfügungen und Updates an einer Zeile finden in mehreren Knoten statt.</span><span class="sxs-lookup"><span data-stu-id="d7067-129">Inserts and updates to a row are occurring at more than one node.</span></span>  
  
     <span data-ttu-id="d7067-130">Unabhängig vom Typ der verwendeten Replikation wird empfohlen, Einfügungen und Updates möglichst zu partitionieren, da dies den Verarbeitungsaufwand bei der Konflikterkennung und -lösung reduziert.</span><span class="sxs-lookup"><span data-stu-id="d7067-130">Regardless of the type of replication used, we recommend that you partition inserts and updates whenever possible, because this reduces the processing required for conflict detection and resolution.</span></span> <span data-ttu-id="d7067-131">Bei der Peer-zu-Peer-Transaktionsreplikation ist eine Partitionierung von Einfügungen und Updates erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d7067-131">For peer-to-peer transactional replication, partitioning inserts and updates is required.</span></span> <span data-ttu-id="d7067-132">Weitere Informationen finden Sie unter [Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="d7067-132">For more information, see [Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md).</span></span>  
  
-   <span data-ttu-id="d7067-133">Auf einem Abonnenten wurde eine Zeile eingefügt, die schreibgeschützt sein sollte.</span><span class="sxs-lookup"><span data-stu-id="d7067-133">A row was inserted at a Subscriber that should be read-only.</span></span>  
  
     <span data-ttu-id="d7067-134">Fügen Sie auf dem Abonnenten keine Zeilen ein und aktualisieren Sie keine Zeilen, es sei denn Sie verwenden die Mergereplikation, die Transaktionsreplikation mit aktualisierbaren Abonnements oder die Peer-zu-Peer-Transaktionsreplikation.</span><span class="sxs-lookup"><span data-stu-id="d7067-134">Do not insert or update rows at the Subscriber unless you are using merge replication, transactional replication with updatable subscriptions, or peer-to-peer transactional replication.</span></span>  
  
-   <span data-ttu-id="d7067-135">Es wird eine Tabelle mit einer Identitätsspalte verwendet, die Spalte wird jedoch nicht ordnungsgemäß verwaltet.</span><span class="sxs-lookup"><span data-stu-id="d7067-135">A table with an identity column is being used, but the column is not managed appropriately.</span></span>  
  
     <span data-ttu-id="d7067-136">Bei der Mergereplikation und der Transaktionsreplikation mit aktualisierbaren Abonnements sollten Identitätsspalten automatisch durch die Replikation verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="d7067-136">For merge replication and transactional replication with updatable subscriptions, identity columns should be managed automatically by replication.</span></span> <span data-ttu-id="d7067-137">Bei der Peer-zu-Peer-Transaktionsreplikation müssen sie manuell verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="d7067-137">For peer-to-peer transactional replication, they must be managed manually.</span></span> <span data-ttu-id="d7067-138">Weitere Informationen finden Sie unter [Replizieren von Identitätsspalten](publish/replicate-identity-columns.md).</span><span class="sxs-lookup"><span data-stu-id="d7067-138">For more information, see [Replicate Identity Columns](publish/replicate-identity-columns.md).</span></span>  
  
-   <span data-ttu-id="d7067-139">Der Fehler tritt während eines INSERTs in der **MSmerge_contents**-Systemtabelle auf.</span><span class="sxs-lookup"><span data-stu-id="d7067-139">The error occurs during an insert into the system table **MSmerge_contents**.</span></span>  
  
     <span data-ttu-id="d7067-140">Dieser Fehler kann auftreten, wenn für die Joinsfiltereigenschaft **join_unique_key**ein falscher Wert festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="d7067-140">This error can occur because of an incorrect value for the join filter property **join_unique_key**.</span></span> <span data-ttu-id="d7067-141">Diese Eigenschaft sollte nur auf TRUE festgelegt werden, wenn die verknüpfte Spalte in der übergeordneten Tabelle eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="d7067-141">This property should be set to TRUE only if the joined column in the parent table is unique.</span></span> <span data-ttu-id="d7067-142">Wenn die Eigenschaft auf TRUE festgelegt ist, die Spalte jedoch nicht eindeutig ist, wird dieser Fehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="d7067-142">If the property is set to TRUE, but the column is not unique, this error is raised.</span></span> <span data-ttu-id="d7067-143">Weitere Informationen zum Festlegen dieser Eigenschaft finden Sie unter [Definieren und Ändern eines Verknüpfungsfilters zwischen Mergeartikeln](publish/define-and-modify-a-join-filter-between-merge-articles.md).</span><span class="sxs-lookup"><span data-stu-id="d7067-143">For more information on setting this property, see [Define and Modify a Join Filter Between Merge Articles](publish/define-and-modify-a-join-filter-between-merge-articles.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7067-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d7067-144">See Also</span></span>  
 [<span data-ttu-id="d7067-145">Fehler- und Ereignisreferenz &#40;Replikation&#41;</span><span class="sxs-lookup"><span data-stu-id="d7067-145">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
