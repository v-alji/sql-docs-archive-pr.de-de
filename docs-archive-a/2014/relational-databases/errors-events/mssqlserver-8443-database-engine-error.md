---
title: MSSQLSERVER_8443 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8443 (Database Engine error)
ms.assetid: a3541b9c-b1a8-4280-add1-275f08696b62
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ae02cc0d9e5661f4069884c22bf6eea0697bd2d7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719954"
---
# <a name="mssqlserver_8443"></a><span data-ttu-id="d0a72-102">MSSQLSERVER_8443</span><span class="sxs-lookup"><span data-stu-id="d0a72-102">MSSQLSERVER_8443</span></span>
    
## <a name="details"></a><span data-ttu-id="d0a72-103">Details</span><span class="sxs-lookup"><span data-stu-id="d0a72-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d0a72-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="d0a72-104">Product Name</span></span>|<span data-ttu-id="d0a72-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d0a72-105">SQL Server</span></span>|  
|<span data-ttu-id="d0a72-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="d0a72-106">Event ID</span></span>|<span data-ttu-id="d0a72-107">8443</span><span class="sxs-lookup"><span data-stu-id="d0a72-107">8443</span></span>|  
|<span data-ttu-id="d0a72-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="d0a72-108">Event Source</span></span>|<span data-ttu-id="d0a72-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d0a72-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d0a72-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="d0a72-110">Component</span></span>|<span data-ttu-id="d0a72-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="d0a72-111">SQLEngine</span></span>|  
|<span data-ttu-id="d0a72-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="d0a72-112">Symbolic Name</span></span>|<span data-ttu-id="d0a72-113">SB_DIALOG_WO_CONV_GROUP</span><span class="sxs-lookup"><span data-stu-id="d0a72-113">SB_DIALOG_WO_CONV_GROUP</span></span>|  
|<span data-ttu-id="d0a72-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="d0a72-114">Message Text</span></span>|<span data-ttu-id="d0a72-115">Die Konversation mit der ID '%.\*ls' und dem Initiator %d verweist auf die fehlende Konversationsgruppe '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="d0a72-115">The conversation with ID '%.\*ls' and initiator %d references a missing conversation group '%.\*ls'.</span></span> <span data-ttu-id="d0a72-116">Führen Sie DBCC CHECKDB aus, um die Datenbank zu analysieren und zu reparieren.</span><span class="sxs-lookup"><span data-stu-id="d0a72-116">Run DBCC CHECKDB to analyze and repair the database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d0a72-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="d0a72-117">Explanation</span></span>  
 <span data-ttu-id="d0a72-118">Von der Metadatenebene wurde NULL für die Konversationsgruppe zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d0a72-118">The metadata layer returned NULL for the conversation group.</span></span> <span data-ttu-id="d0a72-119">Die Datenbank wurde in irgendeiner Weise beschädigt.</span><span class="sxs-lookup"><span data-stu-id="d0a72-119">The database has been corrupted in some way.</span></span> <span data-ttu-id="d0a72-120">Eine mögliche Ursache für eine Beschädigung kann ein Datenträgerfehler sein.</span><span class="sxs-lookup"><span data-stu-id="d0a72-120">One possible source of corruption is a disk error.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d0a72-121">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="d0a72-121">User Action</span></span>  
 <span data-ttu-id="d0a72-122">Führen Sie DBCC CHECKDB im Reparaturmodus aus, um die Datenbank wieder in einen konsistenten Zustand zu bringen.</span><span class="sxs-lookup"><span data-stu-id="d0a72-122">Run DBCC CHECKDB in repair mode to bring the database back into a consistent state.</span></span> <span data-ttu-id="d0a72-123">Möglicherweise werden dabei Meldungen gelöscht, um die Konsistenz wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="d0a72-123">It may delete messages if necessary to restore consistency.</span></span> <span data-ttu-id="d0a72-124">Untersuchen Sie die Systemfehlerprotokolle, um festzustellen, ob dieser Fehler durch einen anderen Fehler im System verursacht wurde.</span><span class="sxs-lookup"><span data-stu-id="d0a72-124">Investigate system error logs to see if this error was caused by another failure in the system.</span></span>  
  
  
