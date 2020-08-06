---
title: MSSQLSERVER_601 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "601"
helpviewer_keywords:
- 601 (Database Engine error)
ms.assetid: 2039cc0a-9a43-4369-a04a-935e384388b6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 459a983d72a91e628e8cc33636d3abd81998f1d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622153"
---
# <a name="mssqlserver_601"></a><span data-ttu-id="5669b-102">MSSQLSERVER_601</span><span class="sxs-lookup"><span data-stu-id="5669b-102">MSSQLSERVER_601</span></span>
    
## <a name="details"></a><span data-ttu-id="5669b-103">Details</span><span class="sxs-lookup"><span data-stu-id="5669b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5669b-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="5669b-104">Product Name</span></span>|<span data-ttu-id="5669b-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="5669b-105">SQL Server</span></span>|  
|<span data-ttu-id="5669b-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="5669b-106">Event ID</span></span>|<span data-ttu-id="5669b-107">601</span><span class="sxs-lookup"><span data-stu-id="5669b-107">601</span></span>|  
|<span data-ttu-id="5669b-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="5669b-108">Event Source</span></span>|<span data-ttu-id="5669b-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="5669b-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="5669b-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="5669b-110">Component</span></span>|<span data-ttu-id="5669b-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="5669b-111">SQLEngine</span></span>|  
|<span data-ttu-id="5669b-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="5669b-112">Symbolic Name</span></span>||  
|<span data-ttu-id="5669b-113">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="5669b-113">Message Text</span></span>|<span data-ttu-id="5669b-114">Aufgrund von Datenverschiebungen konnte der Scanvorgang mit NOLOCK nicht fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="5669b-114">Could not continue scan with NOLOCK due to data movement.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5669b-115">Erklärung</span><span class="sxs-lookup"><span data-stu-id="5669b-115">Explanation</span></span>  
 <span data-ttu-id="5669b-116">Die Abfrage kann von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] nicht weiter ausgeführt werden, da versucht wird, Daten zu lesen, die durch eine andere Transaktion aktualisiert oder gelöscht wurden.</span><span class="sxs-lookup"><span data-stu-id="5669b-116">The [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] cannot continue executing the query because it is trying to read data that was updated or deleted by another transaction.</span></span> <span data-ttu-id="5669b-117">Für die Abfrage wird der Sperrhinweis NOLOCK oder die Isolationsstufe für Transaktionen READ UNCOMMITTED verwendet.</span><span class="sxs-lookup"><span data-stu-id="5669b-117">The query is using either the NOLOCK locking hint or the READ UNCOMMITTED transaction isolation level.</span></span>  
  
 <span data-ttu-id="5669b-118">Normalerweise wird der Zugriff auf Daten verweigert, die durch eine andere Transaktion geändert wurden, da die Daten mit Sperren belegt werden.</span><span class="sxs-lookup"><span data-stu-id="5669b-118">Typically, access to data that is being changed by another transaction is denied because of locks put on the data.</span></span> <span data-ttu-id="5669b-119">Mithilfe des Sperrhinweises NOLOCK und der Isolationsstufe für Transaktionen READ UNCOMMITTED können mit einer Abfrage jedoch Daten gelesen werden, die durch eine andere Transaktion gesperrt sind.</span><span class="sxs-lookup"><span data-stu-id="5669b-119">However, the NOLOCK locking hint and READ UNCOMMITTED transaction isolation level let a query read data that is locked by another transaction.</span></span> <span data-ttu-id="5669b-120">Dies wird als Dirty Read bezeichnet, da Sie Werte lesen können, für die noch kein Commit ausgeführt wurde und an denen Änderungen vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="5669b-120">This is referred to as a dirty read because you can read values that have not yet been committed and that are subject to change.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5669b-121">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="5669b-121">User Action</span></span>  
 <span data-ttu-id="5669b-122">Durch diesen Fehler wird die Abfrage abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="5669b-122">This error cancels the query.</span></span> <span data-ttu-id="5669b-123">Übermitteln Sie die Abfrage erneut, oder entfernen Sie den Sperrhinweis NOLOCK.</span><span class="sxs-lookup"><span data-stu-id="5669b-123">Either resubmit the query or remove the NOLOCK locking hint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5669b-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5669b-124">See Also</span></span>  
 <span data-ttu-id="5669b-125">[MSSQLSERVER_605](mssqlserver-605-database-engine-error.md) </span><span class="sxs-lookup"><span data-stu-id="5669b-125">[MSSQLSERVER_605](mssqlserver-605-database-engine-error.md) </span></span>  
 <span data-ttu-id="5669b-126">[Tabellenhinweise &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-table) </span><span class="sxs-lookup"><span data-stu-id="5669b-126">[Table Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-table) </span></span>  
 <span data-ttu-id="5669b-127">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5669b-127">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span></span>  
 [<span data-ttu-id="5669b-128">SET TRANSACTION ISOLATION LEVEL &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5669b-128">SET TRANSACTION ISOLATION LEVEL &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/set-transaction-isolation-level-transact-sql)  
  
  
