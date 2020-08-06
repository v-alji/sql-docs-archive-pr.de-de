---
title: MSSQL_ENG004929 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG004929 error
ms.assetid: 1d9b1d88-1fbf-4089-b392-687d3b0220ca
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b202b28eabe1feb1ed180bda0d58d2e84c7d10d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608568"
---
# <a name="mssql_eng004929"></a><span data-ttu-id="bb4fd-102">MSSQL_ENG004929</span><span class="sxs-lookup"><span data-stu-id="bb4fd-102">MSSQL_ENG004929</span></span>
    
## <a name="message-details"></a><span data-ttu-id="bb4fd-103">Meldungsdetails</span><span class="sxs-lookup"><span data-stu-id="bb4fd-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bb4fd-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="bb4fd-104">Product Name</span></span>|<span data-ttu-id="bb4fd-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="bb4fd-105">SQL Server</span></span>|  
|<span data-ttu-id="bb4fd-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="bb4fd-106">Event ID</span></span>|<span data-ttu-id="bb4fd-107">4929</span><span class="sxs-lookup"><span data-stu-id="bb4fd-107">4929</span></span>|  
|<span data-ttu-id="bb4fd-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="bb4fd-108">Event Source</span></span>|<span data-ttu-id="bb4fd-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="bb4fd-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="bb4fd-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="bb4fd-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="bb4fd-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="bb4fd-111">Symbolic Name</span></span>||  
|<span data-ttu-id="bb4fd-112">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="bb4fd-112">Message Text</span></span>|<span data-ttu-id="bb4fd-113">Das %1!s!-Objekt '%2!s!' kann nicht geändert werden, da es für die Replikation veröffentlicht wird.</span><span class="sxs-lookup"><span data-stu-id="bb4fd-113">Cannot alter the %S_MSG '%.\*ls' because it is being published for replication.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="bb4fd-114">Erklärung</span><span class="sxs-lookup"><span data-stu-id="bb4fd-114">Explanation</span></span>  
 <span data-ttu-id="bb4fd-115">Dieser Fehler tritt normalerweise auf, wenn Sie versuchen, die PRIMARY KEY-Einschränkung einer Tabelle zu löschen, die für die Transaktionsreplikation veröffentlicht wird.</span><span class="sxs-lookup"><span data-stu-id="bb4fd-115">This error typically occurs if you attempt to drop the primary key constraint on a table that is published for transactional replication.</span></span> <span data-ttu-id="bb4fd-116">Die Transaktionsreplikation erfordert einen Primärschlüssel für jede veröffentlichte Tabelle. Aus diesem Grund kann die Einschränkung nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="bb4fd-116">Transactional replication requires a primary key for each published table; therefore the constraint cannot be dropped.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bb4fd-117">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="bb4fd-117">User Action</span></span>  
 <span data-ttu-id="bb4fd-118">Um die Einschränkung zu löschen, löschen Sie zunächst den der Tabelle zugeordneten Artikel.</span><span class="sxs-lookup"><span data-stu-id="bb4fd-118">To drop the constraint, first drop the article associated with the table.</span></span> <span data-ttu-id="bb4fd-119">Weitere Informationen finden Sie unter [Hinzufügen und Löschen von Artikeln aus vorhandenen Veröffentlichungen](publish/add-articles-to-and-drop-articles-from-existing-publications.md).</span><span class="sxs-lookup"><span data-stu-id="bb4fd-119">For more information, see [Add Articles to and Drop Articles from Existing Publications](publish/add-articles-to-and-drop-articles-from-existing-publications.md).</span></span> <span data-ttu-id="bb4fd-120">Falls dieser Fehler in einer Datenbank auftritt, die nicht repliziert wird, führen Sie [sp_removedbreplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) aus, um sicherzustellen, dass die Objekte in der Datenbank nicht als repliziert hervorgehoben sind.</span><span class="sxs-lookup"><span data-stu-id="bb4fd-120">If this error occurs in a database that is not replicated, execute [sp_removedbreplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) to ensure objects in the database are not marked as replicated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb4fd-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bb4fd-121">See Also</span></span>  
 [<span data-ttu-id="bb4fd-122">Fehler- und Ereignisreferenz &#40;Replikation&#41;</span><span class="sxs-lookup"><span data-stu-id="bb4fd-122">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
