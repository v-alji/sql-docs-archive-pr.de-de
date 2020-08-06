---
title: MSSQLSERVER_833 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 833 (Database Engine error)
ms.assetid: 14129cc4-be80-4772-9e3f-0e5da4d0696b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8e20018c0fe1cd0748f4930e0022622adcbfad10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617986"
---
# <a name="mssqlserver_833"></a><span data-ttu-id="c042b-102">MSSQLSERVER_833</span><span class="sxs-lookup"><span data-stu-id="c042b-102">MSSQLSERVER_833</span></span>
    
## <a name="details"></a><span data-ttu-id="c042b-103">Details</span><span class="sxs-lookup"><span data-stu-id="c042b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c042b-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="c042b-104">Product Name</span></span>|<span data-ttu-id="c042b-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="c042b-105">SQL Server</span></span>|  
|<span data-ttu-id="c042b-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="c042b-106">Event ID</span></span>|<span data-ttu-id="c042b-107">833</span><span class="sxs-lookup"><span data-stu-id="c042b-107">833</span></span>|  
|<span data-ttu-id="c042b-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="c042b-108">Event Source</span></span>|<span data-ttu-id="c042b-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="c042b-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="c042b-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="c042b-110">Component</span></span>|<span data-ttu-id="c042b-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="c042b-111">SQLEngine</span></span>|  
|<span data-ttu-id="c042b-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="c042b-112">Symbolic Name</span></span>|<span data-ttu-id="c042b-113">BUF_LONG_IO</span><span class="sxs-lookup"><span data-stu-id="c042b-113">BUF_LONG_IO</span></span>|  
|<span data-ttu-id="c042b-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="c042b-114">Message Text</span></span>|<span data-ttu-id="c042b-115">Bei der SQL Server wurden% d e/a-Anforderungen für die Datei [% ls] in der Datenbank länger als% d Sekunden in Anspruch genommen `[%ls] (%d)` .</span><span class="sxs-lookup"><span data-stu-id="c042b-115">SQL Server has encountered %d occurrence(s) of I/O requests taking longer than %d seconds to complete on file [%ls] in database`[%ls] (%d)`.</span></span>  <span data-ttu-id="c042b-116">Das Dateihandle des Betriebssystems lautet 0x%p.</span><span class="sxs-lookup"><span data-stu-id="c042b-116">The OS file handle is 0x%p.</span></span>  <span data-ttu-id="c042b-117">Der Offset des letzten langen E/A-Vorgangs lautet: %#016I64x.</span><span class="sxs-lookup"><span data-stu-id="c042b-117">The offset of the latest long I/O is: %#016I64x.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c042b-118">Erklärung</span><span class="sxs-lookup"><span data-stu-id="c042b-118">Explanation</span></span>  
 <span data-ttu-id="c042b-119">Mit dieser Meldung wird angegeben, dass von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] eine Lese- oder Schreibanforderung vom Datenträger ausgegeben wurde und dass die Rückgabe der Anforderung länger als 15 Sekunden gedauert hat.</span><span class="sxs-lookup"><span data-stu-id="c042b-119">This message indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has issued a read or write request from disk, and that the request has taken longer than 15 seconds to return.</span></span> <span data-ttu-id="c042b-120">Dieser Fehler wird von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] gemeldet und deutet auf ein Problem mit dem E/A-Subsystem hin.</span><span class="sxs-lookup"><span data-stu-id="c042b-120">This error is reported by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and indicates a problem with the IO subsystem.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="c042b-121">Mögliche Ursachen</span><span class="sxs-lookup"><span data-stu-id="c042b-121">Possible Causes</span></span>  
 <span data-ttu-id="c042b-122">Dieses Problem kann durch eine beeinträchtigte Systemleistung, Hardware- oder Firmwarefehler, Gerätetreiberprobleme oder das Eingreifen von Filtertreibern im E/A-Vorgang verursacht werden.</span><span class="sxs-lookup"><span data-stu-id="c042b-122">This problem can be caused system performance issues, hardware errors, firmware errors, device driver problems, or filter driver intervention in the IO process.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c042b-123">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="c042b-123">User Action</span></span>  
 <span data-ttu-id="c042b-124">Sie können diesen Fehler durch Überprüfung des Systemereignisprotokolls auf hardwarebedingte Fehlermeldungen beheben.</span><span class="sxs-lookup"><span data-stu-id="c042b-124">Troubleshoot this error by examining the system event log for hardware-related error messages.</span></span> <span data-ttu-id="c042b-125">Sie können zudem hardwarespezifische Protokolle überprüfen, sofern diese verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="c042b-125">Also, examine hardware-specific logs if they are available.</span></span>  
  
 <span data-ttu-id="c042b-126">Prüfen Sie mit dem Systemmonitor die folgenden Leistungsindikatoren:</span><span class="sxs-lookup"><span data-stu-id="c042b-126">Use Performance Monitor to examine the following counters:</span></span>  
  
-   <span data-ttu-id="c042b-127">**Average Disk Sec/Transfer**</span><span class="sxs-lookup"><span data-stu-id="c042b-127">**Average Disk Sec/Transfer**</span></span>  
  
-   <span data-ttu-id="c042b-128">**Average Disk Queue Length**</span><span class="sxs-lookup"><span data-stu-id="c042b-128">**Average Disk Queue Length**</span></span>  
  
-   <span data-ttu-id="c042b-129">**Current Disk Queue Length**</span><span class="sxs-lookup"><span data-stu-id="c042b-129">**Current Disk Queue Length**</span></span>  
  
 <span data-ttu-id="c042b-130">Beispielsweise beträgt die Zeit von **Average Disk Sec/Transfer** für einen Computer mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] normalerweise unter 15 Millisekunden.</span><span class="sxs-lookup"><span data-stu-id="c042b-130">For example, the **Average Disk Sec/Transfer** time on a computer that is running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is typically less than 15 milliseconds.</span></span> <span data-ttu-id="c042b-131">Wenn sich der Wert **Average Disk Sec/Transfer** erhöht, ist dies ein Hinweis darauf, dass das E/A-Subsystem den E/A-Bedarf nicht optimal erfüllt.</span><span class="sxs-lookup"><span data-stu-id="c042b-131">If the **Average Disk Sec/Transfer** value increases, this indicates that the I/O subsystem is not optimally keeping up with the I/O demand.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c042b-132">Der Datenträgerzugriff wird möglicherweise durch ein Antivirenprogramm verzögert.</span><span class="sxs-lookup"><span data-stu-id="c042b-132">Disk access can be slowed by an antivirus program.</span></span> <span data-ttu-id="c042b-133">Schließen Sie die in der Fehlermeldung angegebenen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Datendateien von aktiven Virenüberprüfungen aus, um die Zugriffsgeschwindigkeit zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="c042b-133">To increase access speed, exclude the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data files that are specified in the error message from active virus scans.</span></span>  
  
 <span data-ttu-id="c042b-134">Weitere Informationen zu E/A-Fehlern finden Sie unter [Microsoft SQL Server I/O Basics, Chapter 2 (E/A-Grundlagen von Microsoft SQL Server, Kapitel 2)](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10)) und im Knowledge Base-Artikel unter [https://support.microsoft.com/kb/897284](https://support.microsoft.com/kb/897284).</span><span class="sxs-lookup"><span data-stu-id="c042b-134">For more information about I/O errors, see [Microsoft SQL Server I/O Basics, Chapter 2](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10)) and the Knowledge Base article at [https://support.microsoft.com/kb/897284](https://support.microsoft.com/kb/897284).</span></span>  
  
  
