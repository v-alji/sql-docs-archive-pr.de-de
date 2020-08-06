---
title: MSSQLSERVER_9955 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9955 (Database Engine error)
ms.assetid: 77f30570-7790-4747-b372-eac71c036e19
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 56b9f9b4b7923f8973bd7167c3c1bf77e92300c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617023"
---
# <a name="mssqlserver_9955"></a><span data-ttu-id="d6fda-102">MSSQLSERVER_9955</span><span class="sxs-lookup"><span data-stu-id="d6fda-102">MSSQLSERVER_9955</span></span>
    
## <a name="details"></a><span data-ttu-id="d6fda-103">Details</span><span class="sxs-lookup"><span data-stu-id="d6fda-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d6fda-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="d6fda-104">Product Name</span></span>|<span data-ttu-id="d6fda-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d6fda-105">SQL Server</span></span>|  
|<span data-ttu-id="d6fda-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="d6fda-106">Event ID</span></span>|<span data-ttu-id="d6fda-107">9955</span><span class="sxs-lookup"><span data-stu-id="d6fda-107">9955</span></span>|  
|<span data-ttu-id="d6fda-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="d6fda-108">Event Source</span></span>|<span data-ttu-id="d6fda-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d6fda-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d6fda-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="d6fda-110">Component</span></span>|<span data-ttu-id="d6fda-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="d6fda-111">SQLEngine</span></span>|  
|<span data-ttu-id="d6fda-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="d6fda-112">Symbolic Name</span></span>|<span data-ttu-id="d6fda-113">FTXT2_MSSEARCHACCESSDENY</span><span class="sxs-lookup"><span data-stu-id="d6fda-113">FTXT2_MSSEARCHACCESSDENY</span></span>|  
|<span data-ttu-id="d6fda-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="d6fda-114">Message Text</span></span>|<span data-ttu-id="d6fda-115">SQL Server konnte die Named Pipe '%ls' zur Kommunikation mit dem Volltextfilterdaemon nicht erstellen (Windows-Fehler: %d).</span><span class="sxs-lookup"><span data-stu-id="d6fda-115">SQL Server failed to create named pipe '%ls' to communicate with the full-text filter daemon (Windows error: %d).</span></span> <span data-ttu-id="d6fda-116">Entweder ist bereits eine Named Pipe für einen Filterdaemon-Hostprozess vorhanden oder die Systemressourcen reichen nicht aus oder bei der Suche nach der Sicherheits-ID (SID) für die Kontogruppe des Filterdaemons ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="d6fda-116">Either a named pipe already exists for a filter daemon host process, the system is low on resources, or the security identification number (SID) lookup for the filter daemon account group failed.</span></span> <span data-ttu-id="d6fda-117">Um diesen Fehler zu beheben, müssen Sie alle laufenden Prozesse des Volltextfilterdaemons beenden und ggf. das Dienstkonto des Volltextdaemon-Startprogramms neu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="d6fda-117">To resolve this error, terminate any running full-text filter daemon processes, and if necessary reconfigure the full-text daemon launcher service account.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d6fda-118">Erklärung</span><span class="sxs-lookup"><span data-stu-id="d6fda-118">Explanation</span></span>  
 <span data-ttu-id="d6fda-119">Diese Meldung wird angezeigt, weil [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] die Named Pipe zur Kommunikation mit dem Volltextfilterdaemon nicht erstellen konnte.</span><span class="sxs-lookup"><span data-stu-id="d6fda-119">This message occurs because [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failed to create a named pipe to communicate with the full-text filter daemon.</span></span> <span data-ttu-id="d6fda-120">Entweder ist bereits eine Named Pipe für einen Filterdaemon-Hostprozess vorhanden oder die Systemressourcen reichen nicht aus oder bei der Suche nach der Sicherheits-ID (SID) für die Kontogruppe des Filterdaemons ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="d6fda-120">Either a named pipe already exists for a filter daemon host process, the system is low on resources, or the security identification number (SID) lookup for the filter daemon account group failed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d6fda-121">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="d6fda-121">User Action</span></span>  
 <span data-ttu-id="d6fda-122">Um diesen Fehler zu beheben, müssen Sie alle laufenden Prozesse des Volltextfilterdaemons beenden und ggf. das Hostkonto des Volltextfilterdaemons mit dem SQL Server-Konfigurations-Manager neu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="d6fda-122">To resolve this error, terminate any running full-text filter daemon processes, and if necessary reconfigure the full-text daemon host account by using the SQL Server Configuration Manager.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6fda-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d6fda-123">See Also</span></span>  
 <span data-ttu-id="d6fda-124">[SQL Server-Konfigurations-Manager](../sql-server-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="d6fda-124">[SQL Server Configuration Manager](../sql-server-configuration-manager.md) </span></span>  
 <span data-ttu-id="d6fda-125">[Festlegen des Dienst Kontos für das Start Programm des Volltextfilterdaemons](../search/set-the-service-account-for-the-full-text-filter-daemon-launcher.md) </span><span class="sxs-lookup"><span data-stu-id="d6fda-125">[Set the Service Account for the Full-text Filter Daemon Launcher](../search/set-the-service-account-for-the-full-text-filter-daemon-launcher.md) </span></span>  
 [<span data-ttu-id="d6fda-126">Volltextsuche</span><span class="sxs-lookup"><span data-stu-id="d6fda-126">Full-Text Search</span></span>](../search/full-text-search.md)  
  
  
