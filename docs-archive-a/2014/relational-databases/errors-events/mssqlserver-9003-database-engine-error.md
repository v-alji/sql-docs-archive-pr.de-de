---
title: MSSQLSERVER_9003 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9003 (Database Engine error)
ms.assetid: 7fdfb391-5c6f-428b-b434-6c3d0b30fd7b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6f67e4184ea54be6bcd5c2a74d3c0e0711b702f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619848"
---
# <a name="mssqlserver_9003"></a><span data-ttu-id="c25b7-102">MSSQLSERVER_9003</span><span class="sxs-lookup"><span data-stu-id="c25b7-102">MSSQLSERVER_9003</span></span>
    
## <a name="details"></a><span data-ttu-id="c25b7-103">Details</span><span class="sxs-lookup"><span data-stu-id="c25b7-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c25b7-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="c25b7-104">Product Name</span></span>|<span data-ttu-id="c25b7-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="c25b7-105">SQL Server</span></span>|  
|<span data-ttu-id="c25b7-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="c25b7-106">Event ID</span></span>|<span data-ttu-id="c25b7-107">9003</span><span class="sxs-lookup"><span data-stu-id="c25b7-107">9003</span></span>|  
|<span data-ttu-id="c25b7-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="c25b7-108">Event Source</span></span>|<span data-ttu-id="c25b7-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="c25b7-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="c25b7-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="c25b7-110">Component</span></span>|<span data-ttu-id="c25b7-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="c25b7-111">SQLEngine</span></span>|  
|<span data-ttu-id="c25b7-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="c25b7-112">Symbolic Name</span></span>|<span data-ttu-id="c25b7-113">LOG_INVALID_LSN</span><span class="sxs-lookup"><span data-stu-id="c25b7-113">LOG_INVALID_LSN</span></span>|  
|<span data-ttu-id="c25b7-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="c25b7-114">Message Text</span></span>|<span data-ttu-id="c25b7-115">Die Protokollscannummer %S_LSN, die an den Protokollscan in der '%.\*ls'-Datenbank übergeben wurde, ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="c25b7-115">The log scan number %S_LSN passed to log scan in database '%.\*ls' is not valid.</span></span> <span data-ttu-id="c25b7-116">Dieser Fehler kann darauf hinweisen, dass Daten beschädigt sind oder dass die Protokolldatei (LDF) nicht mit der Datendatei (MDF) übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="c25b7-116">This error may indicate data corruption or that the log file (.ldf) does not match the data file (.mdf).</span></span> <span data-ttu-id="c25b7-117">Falls dieser Fehler während der Replikation aufgetreten ist, müssen Sie die Veröffentlichung neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c25b7-117">If this error occurred during replication, re-create the publication.</span></span> <span data-ttu-id="c25b7-118">Andernfalls stellen Sie die Datenbank von einer Sicherung wieder her, falls das Problem zu einem Fehler beim Starten führt.</span><span class="sxs-lookup"><span data-stu-id="c25b7-118">Otherwise, restore from backup if the problem results in a failure during startup.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c25b7-119">Erklärung</span><span class="sxs-lookup"><span data-stu-id="c25b7-119">Explanation</span></span>  
 <span data-ttu-id="c25b7-120">Eine Komponente hat eine ungültige Protokollfolgenummer an den Protokoll-Manager für die Datenbank übergeben.</span><span class="sxs-lookup"><span data-stu-id="c25b7-120">A component passed an invalid log sequence number to the log manager for the database.</span></span> <span data-ttu-id="c25b7-121">Die Ursache kann eine Replikation, eine Beschädigung oder eine mangelnde Übereinstimmung zwischen der primären Datendatei und dem Protokoll sein.</span><span class="sxs-lookup"><span data-stu-id="c25b7-121">This could be replication, corruption, or an inconsistency between the primary data file and the log.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c25b7-122">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="c25b7-122">User Action</span></span>  
 <span data-ttu-id="c25b7-123">Falls dieser Fehler während der Replikation aufgetreten ist, erstellen Sie die Veröffentlichung neu.</span><span class="sxs-lookup"><span data-stu-id="c25b7-123">If this occurred during replication, recreate the publication.</span></span> <span data-ttu-id="c25b7-124">Stellen Sie sie andernfalls aus einer Sicherungskopie wieder her.</span><span class="sxs-lookup"><span data-stu-id="c25b7-124">Otherwise, restore from backup.</span></span>  
  
  
