---
title: MSSQLSERVER_9002 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9002 (Database Engine error)
ms.assetid: 2e50841f-2b99-45f4-aec5-aa4add70cbeb
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b40fe70db8849d09f9296a06cbeed65a9c71e5a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619849"
---
# <a name="mssqlserver_9002"></a><span data-ttu-id="6b9b7-102">MSSQLSERVER_9002</span><span class="sxs-lookup"><span data-stu-id="6b9b7-102">MSSQLSERVER_9002</span></span>
    
## <a name="details"></a><span data-ttu-id="6b9b7-103">Details</span><span class="sxs-lookup"><span data-stu-id="6b9b7-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6b9b7-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="6b9b7-104">Product Name</span></span>|<span data-ttu-id="6b9b7-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="6b9b7-105">SQL Server</span></span>|  
|<span data-ttu-id="6b9b7-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="6b9b7-106">Event ID</span></span>|<span data-ttu-id="6b9b7-107">9002</span><span class="sxs-lookup"><span data-stu-id="6b9b7-107">9002</span></span>|  
|<span data-ttu-id="6b9b7-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="6b9b7-108">Event Source</span></span>|<span data-ttu-id="6b9b7-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="6b9b7-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="6b9b7-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="6b9b7-110">Component</span></span>|<span data-ttu-id="6b9b7-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="6b9b7-111">SQLEngine</span></span>|  
|<span data-ttu-id="6b9b7-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="6b9b7-112">Symbolic Name</span></span>|<span data-ttu-id="6b9b7-113">LOG_IS_FULL</span><span class="sxs-lookup"><span data-stu-id="6b9b7-113">LOG_IS_FULL</span></span>|  
|<span data-ttu-id="6b9b7-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="6b9b7-114">Message Text</span></span>|<span data-ttu-id="6b9b7-115">Das Transaktionsprotokoll für die '%.\*ls'-Datenbank ist voll.</span><span class="sxs-lookup"><span data-stu-id="6b9b7-115">The transaction log for database '%.\*ls' is full.</span></span> <span data-ttu-id="6b9b7-116">Die log_reuse_wait_desc-Spalte von sys.databases enthält Informationen dazu, warum Protokollspeicherplatz nicht erneut verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="6b9b7-116">To find out why space in the log cannot be reused, see the log_reuse_wait_desc column in sys.databases.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6b9b7-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="6b9b7-117">Explanation</span></span>  
 <span data-ttu-id="6b9b7-118">Das Datenbankprotokoll hat nicht mehr genügend Speicherplatz zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="6b9b7-118">The database log is out of space.</span></span> <span data-ttu-id="6b9b7-119">Die **log_reuse_wait_desc**-Spalte in **sys.databases** beschreibt, warum Protokollspeicherplatz nicht erneut verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="6b9b7-119">The **log_reuse_wait_desc** column in **sys.databases** describes why space in the log cannot be reused.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6b9b7-120">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="6b9b7-120">User Action</span></span>  
 <span data-ttu-id="6b9b7-121">Bestimmen Sie mit **sys.databases**, warum das Protokoll voll ist, und korrigieren Sie dann die Bedingung.</span><span class="sxs-lookup"><span data-stu-id="6b9b7-121">Use **sys.databases** to determine why the log is full and then correct the condition.</span></span> <span data-ttu-id="6b9b7-122">Weitere Informationen finden Sie unter „Problembehandlung bei vollen Transaktionsprotokollen (Fehler 9002)“ in der SQL Server-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="6b9b7-122">For more information, see "Troubleshooting a Full Transaction Log (Error 9002)" in SQL Server Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b9b7-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6b9b7-123">See Also</span></span>  
 <span data-ttu-id="6b9b7-124">[Problembehandlung bei vollen Transaktionsprotokollen &#40;SQL Server-Fehler 9002&#41;](../logs/troubleshoot-a-full-transaction-log-sql-server-error-9002.md) </span><span class="sxs-lookup"><span data-stu-id="6b9b7-124">[Troubleshoot a Full Transaction Log &#40;SQL Server Error 9002&#41;](../logs/troubleshoot-a-full-transaction-log-sql-server-error-9002.md) </span></span>  
 [<span data-ttu-id="6b9b7-125">sys.databases &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6b9b7-125">sys.databases &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql)  
  
  
