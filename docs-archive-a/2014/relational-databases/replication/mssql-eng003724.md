---
title: MSSQL_ENG003724 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG003724 error
ms.assetid: 10cb119d-92df-4124-b85d-cd2f2666c99c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: dbfb68575c5ffa73276b3bbe1643381c3f0cc412
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725478"
---
# <a name="mssql_eng003724"></a><span data-ttu-id="8ee90-102">MSSQL_ENG003724</span><span class="sxs-lookup"><span data-stu-id="8ee90-102">MSSQL_ENG003724</span></span>
    
## <a name="message-details"></a><span data-ttu-id="8ee90-103">Meldungsdetails</span><span class="sxs-lookup"><span data-stu-id="8ee90-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8ee90-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="8ee90-104">Product Name</span></span>|<span data-ttu-id="8ee90-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="8ee90-105">SQL Server</span></span>|  
|<span data-ttu-id="8ee90-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="8ee90-106">Event ID</span></span>|<span data-ttu-id="8ee90-107">3724</span><span class="sxs-lookup"><span data-stu-id="8ee90-107">3724</span></span>|  
|<span data-ttu-id="8ee90-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="8ee90-108">Event Source</span></span>|<span data-ttu-id="8ee90-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="8ee90-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="8ee90-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="8ee90-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="8ee90-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="8ee90-111">Symbolic Name</span></span>||  
|<span data-ttu-id="8ee90-112">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="8ee90-112">Message Text</span></span>|<span data-ttu-id="8ee90-113">Das %1!s! von '%3!s!' (%2!s!) ist nicht möglich, da das Objekt für die Replikation verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8ee90-113">Cannot %S_MSG the %S_MSG '%.\*ls' because it is being used for replication.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8ee90-114">Erklärung</span><span class="sxs-lookup"><span data-stu-id="8ee90-114">Explanation</span></span>  
 <span data-ttu-id="8ee90-115">Wenn Sie Objekte in einer Datenbank replizieren, werden diese Objekte in der **sysarticles** -Systemtabelle (bei Momentaufnahmen- und Transaktionsveröffentlichungen) bzw. **sysmergearticles** (bei Mergeveröffentlichungen) als repliziert gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="8ee90-115">When objects in a database are replicated, they are marked as replicated in the system table **sysarticles** (for snapshot and transactional publications) or **sysmergearticles** (for merge publications).</span></span> <span data-ttu-id="8ee90-116">Dieser Fehler wird ausgelöst, wenn Sie versuchen, ein repliziertes Objekt zu löschen.</span><span class="sxs-lookup"><span data-stu-id="8ee90-116">If you attempt drop a replicated object, this error is raised.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8ee90-117">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="8ee90-117">User Action</span></span>  
 <span data-ttu-id="8ee90-118">Stellen Sie vor dem Löschen sicher, dass das Datenbankobjekt nicht repliziert ist.</span><span class="sxs-lookup"><span data-stu-id="8ee90-118">Ensure the database object is not replicated before attempting to drop it.</span></span> <span data-ttu-id="8ee90-119">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8ee90-119">For example:</span></span>  
  
-   <span data-ttu-id="8ee90-120">Tritt der Fehler in der Veröffentlichungsdatenbank auf, löschen Sie den Artikel aus der Veröffentlichung, bevor Sie das Objekt löschen.</span><span class="sxs-lookup"><span data-stu-id="8ee90-120">If the error occurs in the publication database, drop the article from the publication before dropping the object.</span></span> <span data-ttu-id="8ee90-121">Weitere Informationen finden Sie unter [Hinzufügen und Löschen von Artikeln aus vorhandenen Veröffentlichungen](publish/add-articles-to-and-drop-articles-from-existing-publications.md).</span><span class="sxs-lookup"><span data-stu-id="8ee90-121">For more information, see [Add Articles to and Drop Articles from Existing Publications](publish/add-articles-to-and-drop-articles-from-existing-publications.md).</span></span>  
  
-   <span data-ttu-id="8ee90-122">Tritt der Fehler in der Abonnementdatenbank auf, löschen Sie das Abonnement, bevor Sie das Objekt löschen.</span><span class="sxs-lookup"><span data-stu-id="8ee90-122">If the error occurs in the subscription database, drop the subscription before dropping the object.</span></span> <span data-ttu-id="8ee90-123">Weitere Informationen finden Sie unter [Abonnieren von Veröffentlichungen](subscribe-to-publications.md).</span><span class="sxs-lookup"><span data-stu-id="8ee90-123">For more information, see [Subscribe to Publications](subscribe-to-publications.md).</span></span> <span data-ttu-id="8ee90-124">Bei Abonnements für Transaktionsreplikationen besteht die Möglichkeit, nicht gleich die gesamte Veröffentlichung zu löschen, sondern nur das Abonnement eines einzelnen Artikels zu löschen.</span><span class="sxs-lookup"><span data-stu-id="8ee90-124">For subscriptions to transactional publications, it is possible to drop the subscription to an individual article rather than the entire publication.</span></span> <span data-ttu-id="8ee90-125">Weitere Informationen finden Sie unter [sp_dropsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropsubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8ee90-125">For more information, see [sp_dropsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropsubscription-transact-sql).</span></span>  
  
 <span data-ttu-id="8ee90-126">Falls dieser Fehler in einer Datenbank auftritt, die nicht repliziert wird, führen Sie [sp_removedbreplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) aus, um sicherzustellen, dass die Objekte in der Datenbank nicht als repliziert hervorgehoben sind.</span><span class="sxs-lookup"><span data-stu-id="8ee90-126">If this error occurs in a database that is not replicated, execute [sp_removedbreplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) to ensure objects in the database are not marked as replicated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ee90-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8ee90-127">See Also</span></span>  
 [<span data-ttu-id="8ee90-128">Fehler- und Ereignisreferenz &#40;Replikation&#41;</span><span class="sxs-lookup"><span data-stu-id="8ee90-128">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
