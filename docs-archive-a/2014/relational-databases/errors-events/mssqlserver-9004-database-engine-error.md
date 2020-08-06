---
title: MSSQLSERVER_9004 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9004 (Database Engine error)
ms.assetid: b528bb49-340c-4a81-9c8d-cefce6562f16
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 910665b4349e5b13c5abb4fd687dcf0c6fc122cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617042"
---
# <a name="mssqlserver_9004"></a><span data-ttu-id="e566b-102">MSSQLSERVER_9004</span><span class="sxs-lookup"><span data-stu-id="e566b-102">MSSQLSERVER_9004</span></span>
    
## <a name="details"></a><span data-ttu-id="e566b-103">Details</span><span class="sxs-lookup"><span data-stu-id="e566b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e566b-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="e566b-104">Product Name</span></span>|<span data-ttu-id="e566b-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e566b-105">SQL Server</span></span>|  
|<span data-ttu-id="e566b-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="e566b-106">Event ID</span></span>|<span data-ttu-id="e566b-107">9004</span><span class="sxs-lookup"><span data-stu-id="e566b-107">9004</span></span>|  
|<span data-ttu-id="e566b-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="e566b-108">Event Source</span></span>|<span data-ttu-id="e566b-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e566b-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e566b-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="e566b-110">Component</span></span>|<span data-ttu-id="e566b-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="e566b-111">SQLEngine</span></span>|  
|<span data-ttu-id="e566b-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="e566b-112">Symbolic Name</span></span>|<span data-ttu-id="e566b-113">LOG_CORRUPT</span><span class="sxs-lookup"><span data-stu-id="e566b-113">LOG_CORRUPT</span></span>|  
|<span data-ttu-id="e566b-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="e566b-114">Message Text</span></span>|<span data-ttu-id="e566b-115">Fehler beim Verarbeiten des Protokolls für die '%.\*ls'-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="e566b-115">An error occurred while processing the log for database '%.\*ls'.</span></span>  <span data-ttu-id="e566b-116">Führen Sie nach Möglichkeit eine Wiederherstellung von einer Sicherung aus.</span><span class="sxs-lookup"><span data-stu-id="e566b-116">If possible, restore from backup.</span></span> <span data-ttu-id="e566b-117">Falls keine Sicherung verfügbar ist, muss das Protokoll möglicherweise neu erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="e566b-117">If a backup is not available, it might be necessary to rebuild the log.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e566b-118">Erklärung</span><span class="sxs-lookup"><span data-stu-id="e566b-118">Explanation</span></span>  
 <span data-ttu-id="e566b-119">Bei der Verarbeitung des Protokolls während eines Rollbacks, einer Wiederherstellung oder Replikation ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="e566b-119">An error was encountered while processing the log during rollback, recovery, or replication.</span></span> <span data-ttu-id="e566b-120">Dabei kann es sich um einen vom Betriebssystem erkannten Fehler oder um einen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] erkannten internen Konsistenzfehler handeln.</span><span class="sxs-lookup"><span data-stu-id="e566b-120">This could indicate an error detected by the operating system-or an internal consistency error detected by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e566b-121">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="e566b-121">User Action</span></span>  
 <span data-ttu-id="e566b-122">Durch eine der folgenden Aktionen wird dieser Fehler korrigiert:</span><span class="sxs-lookup"><span data-stu-id="e566b-122">One of the following actions will correct this error:</span></span>  
  
-   <span data-ttu-id="e566b-123">Nehmen Sie eine Wiederherstellung aus einer Sicherung vor.</span><span class="sxs-lookup"><span data-stu-id="e566b-123">Restore from a backup.</span></span>  
  
-   <span data-ttu-id="e566b-124">Erstellen Sie das Protokoll neu.</span><span class="sxs-lookup"><span data-stu-id="e566b-124">Rebuild the log.</span></span>  
  
 <span data-ttu-id="e566b-125">Überprüfen Sie außerdem die Systemereignis- und Fehlerprotokolle, um Probleme innerhalb des Systems zu identifizieren, die für den Fehler verantwortlich sein können.</span><span class="sxs-lookup"><span data-stu-id="e566b-125">Also, check system event and error logs to identify issues within the system that may have caused the problem.</span></span>  
  
  
