---
title: MSSQLSERVER_825 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 825 (Database Engine error)
ms.assetid: f69f8214-5af1-4769-878b-117ad6eaff52
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3b17dfac371ad3c805fdbb0b5d3269fc451dd9d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617053"
---
# <a name="mssqlserver_825"></a><span data-ttu-id="6dd27-102">MSSQLSERVER_825</span><span class="sxs-lookup"><span data-stu-id="6dd27-102">MSSQLSERVER_825</span></span>
    
## <a name="details"></a><span data-ttu-id="6dd27-103">Details</span><span class="sxs-lookup"><span data-stu-id="6dd27-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6dd27-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="6dd27-104">Product Name</span></span>|<span data-ttu-id="6dd27-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="6dd27-105">SQL Server</span></span>|  
|<span data-ttu-id="6dd27-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="6dd27-106">Event ID</span></span>|<span data-ttu-id="6dd27-107">825</span><span class="sxs-lookup"><span data-stu-id="6dd27-107">825</span></span>|  
|<span data-ttu-id="6dd27-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="6dd27-108">Event Source</span></span>|<span data-ttu-id="6dd27-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="6dd27-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="6dd27-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="6dd27-110">Component</span></span>|<span data-ttu-id="6dd27-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="6dd27-111">SQLEngine</span></span>|  
|<span data-ttu-id="6dd27-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="6dd27-112">Symbolic Name</span></span>|<span data-ttu-id="6dd27-113">B_RETRYWORKED</span><span class="sxs-lookup"><span data-stu-id="6dd27-113">B_RETRYWORKED</span></span>|  
|<span data-ttu-id="6dd27-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="6dd27-114">Message Text</span></span>|<span data-ttu-id="6dd27-115">Ein Lesevorgang für die Datei '%ls' und den Offset %#016I64x war nach %d fehlerhaften Versuchen mit dem Fehler %ls erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="6dd27-115">A read of the file '%ls' at offset %#016I64x succeeded after failing %d time(s) with error: %ls.</span></span> <span data-ttu-id="6dd27-116">Weitere Informationen finden Sie möglicherweise in zusätzlichen Meldungen im SQL Server-Fehlerprotokoll und im Systemereignisprotokoll.</span><span class="sxs-lookup"><span data-stu-id="6dd27-116">Additional messages in the SQL Server error log and system event log may provide more detail.</span></span> <span data-ttu-id="6dd27-117">Dieser Fehler bedroht die Datenbankintegrität und muss behoben werden.</span><span class="sxs-lookup"><span data-stu-id="6dd27-117">This error condition threatens database integrity and must be corrected.</span></span> <span data-ttu-id="6dd27-118">Führen Sie eine vollständige Datenbankkonsistenzprüfung (DBCC CHECKDB) aus.</span><span class="sxs-lookup"><span data-stu-id="6dd27-118">Complete a full database consistency check (DBCC CHECKDB).</span></span> <span data-ttu-id="6dd27-119">Dieser Fehler kann viele Ursachen haben. Weitere Informationen finden Sie in der SQL Server-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="6dd27-119">This error can be caused by many factors; for more information, see SQL Server Books Online.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6dd27-120">Erklärung</span><span class="sxs-lookup"><span data-stu-id="6dd27-120">Explanation</span></span>  
 <span data-ttu-id="6dd27-121">Mit dieser Meldung wird angegeben, dass der Lesevorgang mindestens ein Mal wiederholt werden musste. Zudem wird hiermit auf ein größeres Problem mit der Datenträgerhardware hingewiesen.</span><span class="sxs-lookup"><span data-stu-id="6dd27-121">This message indicates that the read operation had to be reissued at least one time, and indicates a major problem with the disk hardware.</span></span> <span data-ttu-id="6dd27-122">Diese Meldung deutet aktuell nicht auf ein [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Problem hin, durch das Datenträgerproblem werden möglicherweise Datenverluste oder Beschädigungen der Datenbank verursacht, wenn es nicht behoben wird.</span><span class="sxs-lookup"><span data-stu-id="6dd27-122">This message does not currently indicate a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] problem, but the disk problem could cause data loss or database corruption if it is not resolved.</span></span> <span data-ttu-id="6dd27-123">Das Systemereignisprotokoll enthält möglicherweise ähnliche Ereignisse, anhand derer eine Problemdiagnose vorgenommen werden kann.</span><span class="sxs-lookup"><span data-stu-id="6dd27-123">The system event log may contain related events that help to diagnose the problem.</span></span> <span data-ttu-id="6dd27-124">Weitere Informationen zu E/A-Fehlern finden Sie unter [Microsoft SQL Server I/O Basics, Chapter 2 (E/A-Grundlagen von Microsoft SQL Server, Kapitel 2)](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10)).</span><span class="sxs-lookup"><span data-stu-id="6dd27-124">For more information about I/O errors, see [Microsoft SQL Server I/O Basics, Chapter 2](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10)).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6dd27-125">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="6dd27-125">User Action</span></span>  
 <span data-ttu-id="6dd27-126">Mit den folgenden Aktionen können Sie das zugrunde liegende Problem möglicherweise identifizieren und lösen:</span><span class="sxs-lookup"><span data-stu-id="6dd27-126">The following actions may help you identify and resolve the underlying problem:</span></span>  
  
-   <span data-ttu-id="6dd27-127">Beachten Sie das Fehlerprotokoll und den jeweiligen Text in dieser Meldung, um Informationen zu den Ursachen für das Problem zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="6dd27-127">Review the error log and the variable text in this message for clues that explain the problem.</span></span>  
  
-   <span data-ttu-id="6dd27-128">Prüfen Sie Ihr Datenträgersystem.</span><span class="sxs-lookup"><span data-stu-id="6dd27-128">Check your disk system.</span></span> <span data-ttu-id="6dd27-129">Das Problem ist möglicherweise auf die Datenträger, Datenträgercontroller, Arraykarten oder Datenträgertreiber zurückzuführen.</span><span class="sxs-lookup"><span data-stu-id="6dd27-129">The problem could be related to the disks, the disk controllers, array cards, or disk drivers.</span></span>  
  
-   <span data-ttu-id="6dd27-130">Die neuesten Hilfsprogramme zum Überprüfen des Status Ihres Datenträgersystems erhalten Sie beim Hersteller des Datenträgers.</span><span class="sxs-lookup"><span data-stu-id="6dd27-130">Contact the disk manufacturer for the latest utilities for checking the status of your disk system.</span></span>  
  
-   <span data-ttu-id="6dd27-131">Wenden Sie sich an den Hersteller des Datenträgers, um die neuesten Treiberupdates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="6dd27-131">Contact the disk manufacturer for the latest driver updates.</span></span>  
  
  
