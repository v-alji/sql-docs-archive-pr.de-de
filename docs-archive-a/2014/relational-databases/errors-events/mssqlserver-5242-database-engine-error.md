---
title: MSSQLSERVER_5242 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5242 (Database Engine error)
ms.assetid: 712b1a10-2f87-41df-a111-1ed9f14102d4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c979d0a788e80cf5c7e1ab9b9a1ca8eccc0eea19
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617054"
---
# <a name="mssqlserver_5242"></a><span data-ttu-id="b5a76-102">MSSQLSERVER_5242</span><span class="sxs-lookup"><span data-stu-id="b5a76-102">MSSQLSERVER_5242</span></span>
    
## <a name="details"></a><span data-ttu-id="b5a76-103">Details</span><span class="sxs-lookup"><span data-stu-id="b5a76-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b5a76-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="b5a76-104">Product Name</span></span>|<span data-ttu-id="b5a76-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b5a76-105">SQL Server</span></span>|  
|<span data-ttu-id="b5a76-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="b5a76-106">Event ID</span></span>|<span data-ttu-id="b5a76-107">5242</span><span class="sxs-lookup"><span data-stu-id="b5a76-107">5242</span></span>|  
|<span data-ttu-id="b5a76-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="b5a76-108">Event Source</span></span>|<span data-ttu-id="b5a76-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b5a76-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b5a76-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="b5a76-110">Component</span></span>|<span data-ttu-id="b5a76-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="b5a76-111">SQLEngine</span></span>|  
|<span data-ttu-id="b5a76-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="b5a76-112">Symbolic Name</span></span>||  
|<span data-ttu-id="b5a76-113">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="b5a76-113">Message Text</span></span>|<span data-ttu-id="b5a76-114">Bei einem internen Vorgang wurde eine Inkonsistenz in der '%.\*ls'-Datenbank (ID: %d) auf Seite %S_PGID gefunden.</span><span class="sxs-lookup"><span data-stu-id="b5a76-114">An inconsistency was detected during an internal operation in database '%.\*ls'(ID:%d) on page %S_PGID.</span></span> <span data-ttu-id="b5a76-115">Wenden Sie sich an den technischen Support.</span><span class="sxs-lookup"><span data-stu-id="b5a76-115">Please contact technical support.</span></span> <span data-ttu-id="b5a76-116">Referenznummer %ld.</span><span class="sxs-lookup"><span data-stu-id="b5a76-116">Reference number %ld.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b5a76-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="b5a76-117">Explanation</span></span>  
 <span data-ttu-id="b5a76-118">Auf der Datenbankseite, die in der Fehlermeldung angegeben wird, ist eine strukturelle Inkonsistenz aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="b5a76-118">A structural inconsistency occurred on the database page that is referenced in the error message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5a76-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b5a76-119">See Also</span></span>  
 <span data-ttu-id="b5a76-120">[DBCC CHECKDB &#40;Transact-SQL-&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b5a76-120">[DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) </span></span>  
 [<span data-ttu-id="b5a76-121">Datenbankdateien und Dateigruppen</span><span class="sxs-lookup"><span data-stu-id="b5a76-121">Database Files and Filegroups</span></span>](../databases/database-files-and-filegroups.md)  
  
  
