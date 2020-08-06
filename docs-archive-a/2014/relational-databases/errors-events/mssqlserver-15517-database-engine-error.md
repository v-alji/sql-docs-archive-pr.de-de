---
title: MSSQLSERVER_15517 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 15517 (Database Engine error)
ms.assetid: f94287f5-129f-4c52-9d34-62b996088001
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b8e66e211faf03e1457953d0292e711cde1798ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620946"
---
# <a name="mssqlserver_15517"></a><span data-ttu-id="04e32-102">MSSQLSERVER_15517</span><span class="sxs-lookup"><span data-stu-id="04e32-102">MSSQLSERVER_15517</span></span>
    
## <a name="details"></a><span data-ttu-id="04e32-103">Details</span><span class="sxs-lookup"><span data-stu-id="04e32-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="04e32-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="04e32-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="04e32-105">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="04e32-105">Event ID</span></span>|<span data-ttu-id="04e32-106">15517</span><span class="sxs-lookup"><span data-stu-id="04e32-106">15517</span></span>|  
|<span data-ttu-id="04e32-107">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="04e32-107">Event Source</span></span>|<span data-ttu-id="04e32-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="04e32-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="04e32-109">Komponente</span><span class="sxs-lookup"><span data-stu-id="04e32-109">Component</span></span>|<span data-ttu-id="04e32-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="04e32-110">SQLEngine</span></span>|  
|<span data-ttu-id="04e32-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="04e32-111">Symbolic Name</span></span>|<span data-ttu-id="04e32-112">SEC_CANNOTEXECUTEASUSER</span><span class="sxs-lookup"><span data-stu-id="04e32-112">SEC_CANNOTEXECUTEASUSER</span></span>|  
|<span data-ttu-id="04e32-113">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="04e32-113">Message Text</span></span>|<span data-ttu-id="04e32-114">Die Ausführung als Datenbankprinzipal ist nicht möglich, weil der Prinzipal „*principal*“ nicht vorhanden ist, für diesen Typ von Prinzipal kein Identitätswechsel möglich ist, oder Sie nicht die erforderliche Berechtigung haben.</span><span class="sxs-lookup"><span data-stu-id="04e32-114">Cannot execute as the database principal because the principal "*principal*" does not exist, this type of principal cannot be impersonated, or you do not have permission.</span></span>|  
  
## <a name="user-action"></a><span data-ttu-id="04e32-115">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="04e32-115">User Action</span></span>  
 <span data-ttu-id="04e32-116">Verwenden Sie den Namen eines vorhandenen Prinzipals, oder rufen Sie die IMPERSONATE-Berechtigung für den betreffenden Prinzipal ab.</span><span class="sxs-lookup"><span data-stu-id="04e32-116">Use the name of an existing principal or get the IMPERSONATE permission on that principal.</span></span>  
  
 <span data-ttu-id="04e32-117">15517 kann zudem nach dem Anfügen und Wiederherstellen einer Datenbank durch eine Person auftreten, die nicht mit dem ursprünglichen Datenbankbesitzer identisch ist.</span><span class="sxs-lookup"><span data-stu-id="04e32-117">15517 can also occur after performing an attach and restore of a database by someone other than the original database owner.</span></span> <span data-ttu-id="04e32-118">Ändern Sie zum Beheben dieses Fehlers den db_owner in eine Anmeldung auf Ihrem Server, indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="04e32-118">To resolve this error, change the db_owner to a login on your server, by running the following command:</span></span>  
  
```  
ALTER AUTHORIZATION ON DATABASE:: DBName TO [NewLogin]  
```  
  
## <a name="see-also"></a><span data-ttu-id="04e32-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="04e32-119">See Also</span></span>  
 [<span data-ttu-id="04e32-120">In-Memory-OLTP &#40;Arbeitsspeicheroptimierung&#41;</span><span class="sxs-lookup"><span data-stu-id="04e32-120">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
