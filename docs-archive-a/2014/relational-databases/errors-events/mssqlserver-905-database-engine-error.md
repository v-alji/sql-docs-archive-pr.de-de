---
title: MSSQLSERVER_905 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 905 (Database Engine error)
ms.assetid: c828bb2e-e554-4f81-b76c-2b3740d2b944
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7dd3c8c5a287e2d123e2a9d1430ecd49b27f29f5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617041"
---
# <a name="mssqlserver_905"></a><span data-ttu-id="0956a-102">MSSQLSERVER_905</span><span class="sxs-lookup"><span data-stu-id="0956a-102">MSSQLSERVER_905</span></span>
    
## <a name="details"></a><span data-ttu-id="0956a-103">Details</span><span class="sxs-lookup"><span data-stu-id="0956a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0956a-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="0956a-104">Product Name</span></span>|<span data-ttu-id="0956a-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="0956a-105">SQL Server</span></span>|  
|<span data-ttu-id="0956a-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="0956a-106">Event ID</span></span>|<span data-ttu-id="0956a-107">905</span><span class="sxs-lookup"><span data-stu-id="0956a-107">905</span></span>|  
|<span data-ttu-id="0956a-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="0956a-108">Event Source</span></span>|<span data-ttu-id="0956a-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="0956a-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="0956a-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="0956a-110">Component</span></span>|<span data-ttu-id="0956a-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="0956a-111">SQLEngine</span></span>|  
|<span data-ttu-id="0956a-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="0956a-112">Symbolic Name</span></span>|<span data-ttu-id="0956a-113">DBSTARTUP_EE_PARTITIONING</span><span class="sxs-lookup"><span data-stu-id="0956a-113">DBSTARTUP_EE_PARTITIONING</span></span>|  
|<span data-ttu-id="0956a-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="0956a-114">Message Text</span></span>|<span data-ttu-id="0956a-115">Die '%.\*ls'-Datenbank kann in dieser Edition von SQL Server nicht gestartet werden, weil sie eine '%.\*ls'-Partitionsfunktion enthält.</span><span class="sxs-lookup"><span data-stu-id="0956a-115">Database '%.\*ls' cannot be started in this edition of SQL Server because it contains a partition function '%.\*ls'.</span></span> <span data-ttu-id="0956a-116">Das Partitionieren wird nur von SQL Server Enterprise Edition unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0956a-116">Only Enterprise edition of SQL Server supports partitioning.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0956a-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="0956a-117">Explanation</span></span>  
 <span data-ttu-id="0956a-118">Die Datenbank enthält mindestens eine partitionierte Tabelle bzw. mindestens einen partitionierten Index.</span><span class="sxs-lookup"><span data-stu-id="0956a-118">The database contains one or more partitioned tables or indexes.</span></span> <span data-ttu-id="0956a-119">In dieser Edition von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] kann keine Partitionierung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0956a-119">This edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot use partitioning.</span></span> <span data-ttu-id="0956a-120">Deshalb kann die Datenbank nicht ordnungsgemäß gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="0956a-120">Therefore, the database cannot be started correctly.</span></span> <span data-ttu-id="0956a-121">Partitionierte Tabellen und Indizes sind nicht in jeder Edition von [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0956a-121">Partitioned tables and indexes are not available in every edition of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="0956a-122">Eine Liste der Funktionen, die von den Editionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]unterstützt werden, finden Sie unter [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="0956a-122">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0956a-123">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="0956a-123">User Action</span></span>  
 <span data-ttu-id="0956a-124">Trennen Sie die Datenbank mithilfe der gespeicherten Prozedur sp_detach_db.</span><span class="sxs-lookup"><span data-stu-id="0956a-124">Detach the database by using the sp_detach_db stored procedure.</span></span> <span data-ttu-id="0956a-125">Verschieben Sie die Dateien bei Bedarf, und fügen Sie dann die Datenbank an eine Instanz der unterstützen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Edition an. Verwenden Sie dazu CREATE DATABASE mit der FOR ATTACH-Option oder der FOR ATTACH_REBUILD_LOG-Option.</span><span class="sxs-lookup"><span data-stu-id="0956a-125">Move the files if it is needed, and then attach the database to an instance of a supported [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] edition by using the CREATE DATABASE with the FOR ATTACH or FOR ATTACH_REBUILD_LOG option.</span></span> <span data-ttu-id="0956a-126">Deaktivieren Sie die Partitionierung für alle Tabellen, und entfernen Sie die Partitionierungsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="0956a-126">Disable partitioning on all tables and remove the partitioning functions.</span></span> <span data-ttu-id="0956a-127">Trennen Sie die Datenbank wieder, und fügen Sie sie an den aktuellen Server an.</span><span class="sxs-lookup"><span data-stu-id="0956a-127">Detach the database again, and reattach the database to the current server.</span></span>  
  
  
