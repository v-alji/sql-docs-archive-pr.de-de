---
title: MSSQLSERVER_3417 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3417 (Database Engine error)
ms.assetid: 005829c8-cf57-4828-818a-bbe8ee2e00f0
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 680e5a4266c7d0d9aaacb7b3deb9525a002077e8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620898"
---
# <a name="mssqlserver_3417"></a><span data-ttu-id="b3c86-102">MSSQLSERVER_3417</span><span class="sxs-lookup"><span data-stu-id="b3c86-102">MSSQLSERVER_3417</span></span>
    
## <a name="details"></a><span data-ttu-id="b3c86-103">Details</span><span class="sxs-lookup"><span data-stu-id="b3c86-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b3c86-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="b3c86-104">Product Name</span></span>|<span data-ttu-id="b3c86-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b3c86-105">SQL Server</span></span>|  
|<span data-ttu-id="b3c86-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="b3c86-106">Event ID</span></span>|<span data-ttu-id="b3c86-107">3417</span><span class="sxs-lookup"><span data-stu-id="b3c86-107">3417</span></span>|  
|<span data-ttu-id="b3c86-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="b3c86-108">Event Source</span></span>|<span data-ttu-id="b3c86-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b3c86-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b3c86-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="b3c86-110">Component</span></span>|<span data-ttu-id="b3c86-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="b3c86-111">SQLEngine</span></span>|  
|<span data-ttu-id="b3c86-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="b3c86-112">Symbolic Name</span></span>|<span data-ttu-id="b3c86-113">REC_BADMASTER</span><span class="sxs-lookup"><span data-stu-id="b3c86-113">REC_BADMASTER</span></span>|  
|<span data-ttu-id="b3c86-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="b3c86-114">Message Text</span></span>|<span data-ttu-id="b3c86-115">Die master-Datenbank kann nicht wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="b3c86-115">Cannot recover the master database.</span></span> <span data-ttu-id="b3c86-116">SQL Server kann nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b3c86-116">SQL Server is unable to run.</span></span> <span data-ttu-id="b3c86-117">Stellen Sie die master-Datenbank von einer vollständigen Sicherung wieder her, reparieren Sie sie, oder erstellen Sie sie neu.</span><span class="sxs-lookup"><span data-stu-id="b3c86-117">Restore master from a full backup, repair it, or rebuild it.</span></span> <span data-ttu-id="b3c86-118">Weitere Informationen zum Neuerstellen der master-Datenbank finden Sie in der SQL Server-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="b3c86-118">For more information about how to rebuild the master database, see SQL Server Books Online.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b3c86-119">Erklärung</span><span class="sxs-lookup"><span data-stu-id="b3c86-119">Explanation</span></span>  
 <span data-ttu-id="b3c86-120">Die **master**-Datenbank kann von SQL Server nicht gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="b3c86-120">SQL Server cannot start the **master** database.</span></span> <span data-ttu-id="b3c86-121">Wenn die Datenbanken **master** oder **tempdb** nicht in den Onlinemodus gebracht werden können, kann SQL Server nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b3c86-121">If the **master** or **tempdb** cannot be brought online, SQL Server cannot run.</span></span> <span data-ttu-id="b3c86-122">Diesem Fehler sind normalerweise andere Fehler vorausgegangen.</span><span class="sxs-lookup"><span data-stu-id="b3c86-122">This error is usually preceded by other errors.</span></span> <span data-ttu-id="b3c86-123">Überprüfen Sie die Fehlerprotokolle, um die eigentliche Ursache des Fehlers zu finden.</span><span class="sxs-lookup"><span data-stu-id="b3c86-123">Review error logs to find the root cause.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b3c86-124">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="b3c86-124">User Action</span></span>  
 <span data-ttu-id="b3c86-125">Stellen Sie eine Sicherung der Datenbank wieder her, oder reparieren Sie die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="b3c86-125">Restore backup of the database or repair the database.</span></span>  
  
  
