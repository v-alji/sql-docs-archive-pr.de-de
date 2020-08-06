---
title: MSSQLSERVER_823 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 823 (Database Engine error)
ms.assetid: 0d9fce3c-3772-46ce-a7a3-4f4988dc6cae
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: fa5858bbdc9452a33a3d43fdd783e59556a11e57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617996"
---
# <a name="mssqlserver_823"></a><span data-ttu-id="2362b-102">MSSQLSERVER_823</span><span class="sxs-lookup"><span data-stu-id="2362b-102">MSSQLSERVER_823</span></span>
    
## <a name="details"></a><span data-ttu-id="2362b-103">Details</span><span class="sxs-lookup"><span data-stu-id="2362b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2362b-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="2362b-104">Product Name</span></span>|<span data-ttu-id="2362b-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="2362b-105">SQL Server</span></span>|  
|<span data-ttu-id="2362b-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="2362b-106">Event ID</span></span>|<span data-ttu-id="2362b-107">823</span><span class="sxs-lookup"><span data-stu-id="2362b-107">823</span></span>|  
|<span data-ttu-id="2362b-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="2362b-108">Event Source</span></span>|<span data-ttu-id="2362b-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="2362b-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="2362b-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="2362b-110">Component</span></span>|<span data-ttu-id="2362b-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="2362b-111">SQLEngine</span></span>|  
|<span data-ttu-id="2362b-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="2362b-112">Symbolic Name</span></span>|<span data-ttu-id="2362b-113">B_HARDERR</span><span class="sxs-lookup"><span data-stu-id="2362b-113">B_HARDERR</span></span>|  
|<span data-ttu-id="2362b-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="2362b-114">Message Text</span></span>|<span data-ttu-id="2362b-115">Das Betriebssystem hat während eines %S_MSG bei Offset %#016I64x in der Datei '%4!s!' den Fehler '%ls' an SQL Server zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2362b-115">The operating system returned error %ls to SQL Server during a %S_MSG at offset %#016I64x in file '%ls'.</span></span> <span data-ttu-id="2362b-116">Weitere Informationen finden Sie möglicherweise in zusätzlichen Meldungen im SQL Server-Fehlerprotokoll und im Systemereignisprotokoll.</span><span class="sxs-lookup"><span data-stu-id="2362b-116">Additional messages in the SQL Server error log and system event log may provide more detail.</span></span> <span data-ttu-id="2362b-117">Dieser Fehler kann die Datenbankintegrität beeinträchtigen und muss behoben werden.</span><span class="sxs-lookup"><span data-stu-id="2362b-117">This is a severe system-level error condition that threatens database integrity and must be corrected immediately.</span></span> <span data-ttu-id="2362b-118">Führen Sie eine vollständige Datenbankkonsistenzprüfung (DBCC CHECKDB) aus.</span><span class="sxs-lookup"><span data-stu-id="2362b-118">Complete a full database consistency check (DBCC CHECKDB).</span></span> <span data-ttu-id="2362b-119">Dieser Fehler kann viele Ursachen haben. Weitere Informationen finden Sie in der SQL Server-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="2362b-119">This error can be caused by many factors; for more information, see SQL Server Books Online.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2362b-120">Erklärung</span><span class="sxs-lookup"><span data-stu-id="2362b-120">Explanation</span></span>  
 <span data-ttu-id="2362b-121">Fehler bei einer Lese- oder Schreibanforderung in Windows.</span><span class="sxs-lookup"><span data-stu-id="2362b-121">A Windows read or write request has failed.</span></span> <span data-ttu-id="2362b-122">Der von Windows zurückgegebene Fehlercode und der entsprechende Text werden in die Meldung eingefügt.</span><span class="sxs-lookup"><span data-stu-id="2362b-122">The error code that is returned by Windows and the corresponding text are inserted into the message.</span></span> <span data-ttu-id="2362b-123">Im Fall des Lesevorgangs hat [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] bereits viermal versucht, die Leseanforderung zu wiederholen.</span><span class="sxs-lookup"><span data-stu-id="2362b-123">In the read case, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will have already retried the read request four times.</span></span> <span data-ttu-id="2362b-124">Dieser Fehler beruht oft auf einem Hardwarefehler, wird jedoch möglicherweise durch den Gerätetreiber verursacht.</span><span class="sxs-lookup"><span data-stu-id="2362b-124">This error is often the result of a hardware error, but may be caused by the device driver.</span></span> <span data-ttu-id="2362b-125">Weitere Informationen zu Fehler 823 finden Sie unter [https://support.microsoft.com/kb/828339](https://support.microsoft.com/kb/828339) .</span><span class="sxs-lookup"><span data-stu-id="2362b-125">For more information about error 823, see [https://support.microsoft.com/kb/828339](https://support.microsoft.com/kb/828339).</span></span> <span data-ttu-id="2362b-126">Weitere Informationen zu E/A-Fehlern finden Sie unter [Microsoft SQL Server I/O Basics, Chapter 2 (E/A-Grundlagen von Microsoft SQL Server, Kapitel 2)](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10)).</span><span class="sxs-lookup"><span data-stu-id="2362b-126">For more information about I/O errors, see [Microsoft SQL Server I/O Basics, Chapter 2](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10)).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2362b-127">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="2362b-127">User Action</span></span>  
 <span data-ttu-id="2362b-128">Überprüfen Sie, ob zusätzliche Informationen im Systemereignisprotokoll vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="2362b-128">Check for additional information in the system event log.</span></span> <span data-ttu-id="2362b-129">Wenden Sie sich an den Hardwarehersteller oder an Microsoft Support Services, um Unterstützung bei der Bestimmung der Ursache zu erhalten und diese Ursache zu beheben.</span><span class="sxs-lookup"><span data-stu-id="2362b-129">Contact the hardware manufacturer or Microsoft Customer Services and Support to determine the cause and corrective action.</span></span> <span data-ttu-id="2362b-130">Nachdem der Hardwarefehler behoben wurde, stellen Sie alle Datenbanken wieder her, und führen Sie DBCC CHECKDB aus.</span><span class="sxs-lookup"><span data-stu-id="2362b-130">After the hardware error is fixed, restore all databases and run DBCC CHECKDB.</span></span>  
  
  
