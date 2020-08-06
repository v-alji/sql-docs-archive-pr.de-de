---
title: MSSQLSERVER_3271 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3271 (Database Engine error)
ms.assetid: 21b8de4b-6624-4163-9561-1a6cc8fe3d51
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 56bdb5875dbba3fbe5037a308d713170a9b6f9ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617062"
---
# <a name="mssqlserver_3271"></a><span data-ttu-id="48c2e-102">MSSQLSERVER_3271</span><span class="sxs-lookup"><span data-stu-id="48c2e-102">MSSQLSERVER_3271</span></span>
    
## <a name="details"></a><span data-ttu-id="48c2e-103">Details</span><span class="sxs-lookup"><span data-stu-id="48c2e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="48c2e-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="48c2e-104">Product Name</span></span>|<span data-ttu-id="48c2e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="48c2e-105">SQL Server</span></span>|  
|<span data-ttu-id="48c2e-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="48c2e-106">Event ID</span></span>|<span data-ttu-id="48c2e-107">3271</span><span class="sxs-lookup"><span data-stu-id="48c2e-107">3271</span></span>|  
|<span data-ttu-id="48c2e-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="48c2e-108">Event Source</span></span>|<span data-ttu-id="48c2e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="48c2e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="48c2e-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="48c2e-110">Component</span></span>|<span data-ttu-id="48c2e-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="48c2e-111">SQLEngine</span></span>|  
|<span data-ttu-id="48c2e-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="48c2e-112">Symbolic Name</span></span>|<span data-ttu-id="48c2e-113">DMPIO_IO_ERROR</span><span class="sxs-lookup"><span data-stu-id="48c2e-113">DMPIO_IO_ERROR</span></span>|  
|<span data-ttu-id="48c2e-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="48c2e-114">Message Text</span></span>|<span data-ttu-id="48c2e-115">Nicht behebbarer E/A-Fehler für die Datei "%ls:" %ls.</span><span class="sxs-lookup"><span data-stu-id="48c2e-115">A nonrecoverable I/O error occurred on file "%ls:" %ls.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="48c2e-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="48c2e-116">Explanation</span></span>  
 <span data-ttu-id="48c2e-117">Dies ist ein allgemeiner Fehler, der auftritt, wenn das Betriebssystem beim Ausführen von E/A während eines Sicherungs- oder Wiederherstellungsvorgangs einen Fehler auslöst.</span><span class="sxs-lookup"><span data-stu-id="48c2e-117">This is a general error that occurs when the operating system raises an error while performing I/O during a backup or restore operation.</span></span> <span data-ttu-id="48c2e-118">In den meisten Situationen besteht die Ursache schlichtweg darin, dass das Sicherungsmedium voll ist.</span><span class="sxs-lookup"><span data-stu-id="48c2e-118">In most situations the cause is simply that the backup medium is full.</span></span>  
  
 <span data-ttu-id="48c2e-119">Der Fehler enthält möglicherweise zusätzlichen Text vom Betriebssystem, der besagt, dass der Datenträger voll ist.</span><span class="sxs-lookup"><span data-stu-id="48c2e-119">The error may include additional text from the operating system indicating that the disk is full.</span></span> <span data-ttu-id="48c2e-120">Wenn Sie einen Sicherungs- oder Wiederherstellungsvorgang mit Sicherungssoftware eines Drittanbieters ausführen, wird möglicherweise eine zusätzliche Meldung ausgegeben, die besagt, dass bei der Sicherung ein Fehler erzeugt wurde.</span><span class="sxs-lookup"><span data-stu-id="48c2e-120">When performing a backup or restore operation with third-party backup software an additional message may occur indicating that the backup failed.</span></span> <span data-ttu-id="48c2e-121">Die Meldung sieht möglicherweise wie der folgende Text aus:</span><span class="sxs-lookup"><span data-stu-id="48c2e-121">The message may look similar to the following text:</span></span>  
  
```  
"2005-08-02 16:05:16.04 spid55 Error: 18210, Severity: 16, State: 1.  
 2005-08-02 16:05:16.04 spid55 BackupVirtualDeviceFile  
::RequestDurableMedia: Flush failure on backup device 'VDINULL'.   
Operating system error 995(The I/O operation has been aborted because   
of either a thread exit or an application request.)."  
```  
  
 <span data-ttu-id="48c2e-122">Dies ist ein Hinweis darauf, dass die Sicherungssoftware eine Beendigung des Sicherungs- oder Wiederherstellungsvorgangs angefordert hat.</span><span class="sxs-lookup"><span data-stu-id="48c2e-122">This is an indication that the backup software requested a termination of the backup or restore operation.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="48c2e-123">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="48c2e-123">User Action</span></span>  
 <span data-ttu-id="48c2e-124">Führen Sie die folgenden Tasks entsprechend aus:</span><span class="sxs-lookup"><span data-stu-id="48c2e-124">Perform the following tasks as appropriate:</span></span>  
  
-   <span data-ttu-id="48c2e-125">Überprüfen Sie die vorherigen zugrunde liegenden Systemfehlermeldungen und SQL Server-Fehlermeldungen, um die Ursache des Fehlers zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="48c2e-125">Review the underlying system error messages and SQL Server error messages preceding this one to identify the cause of the failure.</span></span>  
  
-   <span data-ttu-id="48c2e-126">Stellen Sie sicher, dass das Sicherungs- und Wiederherstellungsmedium über genügend Speicherplatz verfügt.</span><span class="sxs-lookup"><span data-stu-id="48c2e-126">Ensure that the backup and restore medium has sufficient space.</span></span>  
  
-   <span data-ttu-id="48c2e-127">Beheben Sie alle Fehler, die von Sicherungs- und Wiederherstellungssoftware von Drittanbietern ausgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="48c2e-127">Correct any errors raised by third-party backup and restore software.</span></span>  
  
  
