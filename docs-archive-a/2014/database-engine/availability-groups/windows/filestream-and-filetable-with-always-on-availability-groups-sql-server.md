---
title: FILESTREAM und FILETABLE mit AlwaysOn-Verfügbarkeitsgruppen (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- FileTables [SQL Server], Availability Groups
- FILESTREAM [SQL Server], Availability Groups
- Availability Groups [SQL Server], interoperability
ms.assetid: fdceda9a-a9db-4d1d-8745-345992164a98
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e7de7b4d66890bb5f1fe49799844f666de81f4db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617276"
---
# <a name="filestream-and-filetable-with-alwayson-availability-groups-sql-server"></a><span data-ttu-id="90267-102">FILESTREAM und FileTable bei AlwaysOn-Verfügbarkeitsgruppen (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="90267-102">FILESTREAM and FileTable with AlwaysOn Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="90267-103">Dieses Thema enthält Informationen zur Verwendung der FILESTREAM- und FileTable-Funktionen mit [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="90267-103">This topic contains information about the using the FILESTREAM and FileTable features with [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="90267-104">Alle FILESTREAM-Funktionen werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="90267-104">All FILESTREAM functionality is supported.</span></span> <span data-ttu-id="90267-105">Nach einem Failover kann sowohl auf lesbaren sekundären Replikaten als auch auf dem neuen primären Replikat auf FILESTREAM-Daten zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="90267-105">After a failover, FILESTREAM data is accessible on both readable secondary replicas and on the new primary.</span></span>  
  
 <span data-ttu-id="90267-106">Die FileTable-Funktionalität wird teilweise unterstützt.</span><span class="sxs-lookup"><span data-stu-id="90267-106">FileTable functionality is partially supported.</span></span> <span data-ttu-id="90267-107">Nach einem Failover kann auf dem primären Replikat auf FileTable-Daten zugegriffen werden, nicht jedoch auf FileTable-Daten auf lesbaren sekundären Replikaten.</span><span class="sxs-lookup"><span data-stu-id="90267-107">After a failover, FileTable data is accessible on the primary replica, but FileTable data is not accessible on readable secondary replicas.</span></span>  
  
 <span data-ttu-id="90267-108">**In diesem Thema:**</span><span class="sxs-lookup"><span data-stu-id="90267-108">**In this Topic:**</span></span>  
  
-   [<span data-ttu-id="90267-109">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="90267-109">Prerequisites</span></span>](#Prerequisites)  
  
-   [<span data-ttu-id="90267-110">Verwenden von Virtual Network Namen (vnns) für FILESTREAM-und FILETABLE-Zugriff</span><span class="sxs-lookup"><span data-stu-id="90267-110">Using Virtual Network Names (VNNs) for FILESTREAM and FileTable Access</span></span>](#vnn)  
  
-   [<span data-ttu-id="90267-111">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="90267-111">Related Tasks</span></span>](#RelatedTasks)  
  
-   [<span data-ttu-id="90267-112">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="90267-112">Related Content</span></span>](#RelatedContent)  
  
##  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="90267-113">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="90267-113">Prerequisites</span></span>  
  
-   <span data-ttu-id="90267-114">Bevor Sie eine Datenbank, die FILESTREAM mit oder ohne FileTable verwendet, zu einer Verfügbarkeitsgruppe hinzufügen, stellen Sie sicher, dass FILESTREAM auf jeder Serverinstanz, die ein Verfügbarkeitsreplikat für die Verfügbarkeitsgruppe hostet, aktiviert worden ist.</span><span class="sxs-lookup"><span data-stu-id="90267-114">Before adding a database that uses FILESTREAM, with or without FileTable, to an availability group, ensure that FILESTREAM is enabled on every server instance that hosts an availability replica for the availability group.</span></span> <span data-ttu-id="90267-115">Weitere Informationen finden Sie unter [Enable and Configure FILESTREAM](../../../relational-databases/blob/enable-and-configure-filestream.md).</span><span class="sxs-lookup"><span data-stu-id="90267-115">For more information, see [Enable and Configure FILESTREAM](../../../relational-databases/blob/enable-and-configure-filestream.md).</span></span>  
  
##  <a name="using-virtual-network-names-vnns-for-filestream-and-filetable-access"></a><a name="vnn"></a> <span data-ttu-id="90267-116">Verwenden von virtuellen Netzwerknamen (VNNs) für den Zugriff auf FILESTREAM- und FileTable-Daten</span><span class="sxs-lookup"><span data-stu-id="90267-116">Using Virtual Network Names (VNNs) for FILESTREAM and FileTable Access</span></span>  
 <span data-ttu-id="90267-117">Wenn Sie FILESTREAM auf einer Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]aktivieren, wird eine Freigabe auf Instanzebene erstellt, um Zugriff auf die FILESTREAM-Daten zu gewähren.</span><span class="sxs-lookup"><span data-stu-id="90267-117">When you enable FILESTREAM on an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], an instance-level share is created to provide access to the FILESTREAM data.</span></span> <span data-ttu-id="90267-118">Sie greifen auf diese Freigabe zu, indem Sie den Computernamen im folgende Format angeben:</span><span class="sxs-lookup"><span data-stu-id="90267-118">You access this share by using the computer name in the following format:</span></span>  
  
 `\\<computer_name>\<filestream_share_name>`  
  
 <span data-ttu-id="90267-119">In einer AlwaysOn-Verfügbarkeitsgruppe wird der Name des Computers jedoch mit einem Virtuellen Netzwerknamen (kurz VNN) virtualisiert.</span><span class="sxs-lookup"><span data-stu-id="90267-119">In an AlwaysOn availability group, however, the name of the computer is virtualized by using a Virtual Network Name, or VNN.</span></span> <span data-ttu-id="90267-120">Wenn der Computer das primäre Replikat in einer Verfügbarkeitsgruppe ist und Datenbanken in der Verfügbarkeitsgruppe FILESTREAM-Daten enthalten, dann wird auch eine Freigabe im Bereich des VNNs erstellt, um Zugriff auf die FILESTREAM-Daten zu bieten.</span><span class="sxs-lookup"><span data-stu-id="90267-120">When the computer is the primary replica in an availability group, and databases in the availability group contain FILESTREAM data, then a VNN-scoped share is also created to provide access to the FILESTREAM data.</span></span> <span data-ttu-id="90267-121">Dies wirkt sich nicht auf den Transact-SQL-Zugriff auf FILESTREAM-Daten aus.</span><span class="sxs-lookup"><span data-stu-id="90267-121">This does not affect Transact-SQL access to FILESTREAM data.</span></span> <span data-ttu-id="90267-122">Anwendungen, die Dateisystem-APIs verwenden, müssen jedoch die Freigabe im Bereich des VNNs verwenden. Diese Freigabe hat einen Pfad im folgenden Format:</span><span class="sxs-lookup"><span data-stu-id="90267-122">However applications that use file system APIs have to use the VNN-scoped share, which has a path in the following format:</span></span>  
  
 `\\<VNN>\<filestream_share_name>`  
  
 <span data-ttu-id="90267-123">Diese Freigabe im VNN-Bereich wird erstellt, wenn eines der folgenden Ereignisse auftritt.</span><span class="sxs-lookup"><span data-stu-id="90267-123">This VNN-scoped share is created when one of the following events occurs.</span></span>  
  
-   <span data-ttu-id="90267-124">Sie fügen eine Datenbank hinzu, die FILESTREAM-Daten zu einer AlwaysOn-Verfügbarkeitsgruppe für das primäre Replikat enthält.</span><span class="sxs-lookup"><span data-stu-id="90267-124">You add a database that contains FILESTREAM data to an AlwaysOn availability group on the primary replica.</span></span> <span data-ttu-id="90267-125">In diesem Fall ist die Freigabe `\\<computer_name>\<filestream_share_name>` bereits vorhanden.</span><span class="sxs-lookup"><span data-stu-id="90267-125">In this case, the share `\\<computer_name>\<filestream_share_name>` already exists.</span></span> <span data-ttu-id="90267-126">Die Freigabe `\\<VNN>\<filestream_share_name>` wird erstellt.</span><span class="sxs-lookup"><span data-stu-id="90267-126">The share `\\<VNN>\<filestream_share_name>` is created.</span></span>  
  
-   <span data-ttu-id="90267-127">Sie aktivieren FILESTREAM für E/A-Streamingzugriff auf Datei für ein primäres Replikat, das Verfügbarkeitsgruppen enthält.</span><span class="sxs-lookup"><span data-stu-id="90267-127">You enable FILESTREAM for file i/o streaming access on a primary replica that has availability groups.</span></span> <span data-ttu-id="90267-128">Die folgenden Freigaben werden erstellt:</span><span class="sxs-lookup"><span data-stu-id="90267-128">The following shares are created:</span></span>  
  
    1.  `\\<computer_name>\<filestream_share_name>`  
  
    2.  <span data-ttu-id="90267-129">`\\<VNN1>\<filestream_share_name>` für die Verfügbarkeitsgruppe 1.</span><span class="sxs-lookup"><span data-stu-id="90267-129">`\\<VNN1>\<filestream_share_name>` for availability group 1.</span></span>  
  
    3.  <span data-ttu-id="90267-130">`\\<VNN2>\<filestream_share_name>` für die Verfügbarkeitsgruppe 2.</span><span class="sxs-lookup"><span data-stu-id="90267-130">`\\<VNN2>\<filestream_share_name>` for availability group 2.</span></span>  
  
 <span data-ttu-id="90267-131">Diese Freigaben im VNN-Bereich werden auch an alle sekundären Replikate weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="90267-131">These VNN-scoped shares are also propagated to all secondary replicas.</span></span>  
  
 <span data-ttu-id="90267-132">Wenn die Datenbank, die FILESTREAM- oder FileTable-Daten enthält, zu einer AlwaysOn-Verfügbarkeitsgruppe gehört:</span><span class="sxs-lookup"><span data-stu-id="90267-132">When the database that contains FILESTREAM or FileTable data belongs to an AlwaysOn availability group:</span></span>  
  
-   <span data-ttu-id="90267-133">Die FILESTREAM-Funktion und die FileTable-Funktion akzeptieren oder geben virtuelle Netzwerknamen (VNNs) statt Computernamen zurück.</span><span class="sxs-lookup"><span data-stu-id="90267-133">The FILESTREAM and FileTable functions accept or return virtual network names (VNNs) instead of computer names.</span></span> <span data-ttu-id="90267-134">Weitere Informationen zu diesen Funktionen finden Sie unter [Filestream- und FileTable-Funktionen &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/filestream-and-filetable-functions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="90267-134">For more information about these functions, see [Filestream and FileTable Functions &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/filestream-and-filetable-functions-transact-sql).</span></span>  
  
-   <span data-ttu-id="90267-135">Bei allen Zugriffen auf FILESTREAM- oder FileTable-Daten über Dateisystem-APIs sollten VNNs statt der Computernamen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="90267-135">All access to FILESTREAM or FileTable data through the file system APIs should use VNNs instead of computer names.</span></span>  
  
 <span data-ttu-id="90267-136">Wenn die Datenbank Teil einer Verfügbarkeitsgruppe ist und die Anwendung versucht, mit einem Computernamen im Format `\\<computer_name>\<filestream_share_name>` auf die Freigabe zuzugreifen, dann wird ein Fehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="90267-136">If your application tries to access the share by using the computer name in the format `\\<computer_name>\<filestream_share_name>` when the database is part of an availability group, then an error is raised.</span></span>  
  
 <span data-ttu-id="90267-137">Wenn die Datenbank kein Teil einer Verfügbarkeitsgruppe ist und die Anwendung versucht, auf die Freigabe mit einem Pfad im VNN-Bereich zuzugreifen, dann wird die Anforderung möglicherweise erfolgreich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="90267-137">If your application tries to access the share by using a VNN-scoped path when the database is not part of an availability group, then the request may succeed.</span></span> <span data-ttu-id="90267-138">In diesem Fall wird der virtuelle Netzwerkname in den Computernamen aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="90267-138">In this case, the virtual network name is resolved to the computer name.</span></span> <span data-ttu-id="90267-139">Von dieser Vorgehensweise wird jedoch stark abgeraten, da der Pfad im VNN-Bereich nicht mehr gültig ist, wenn die Verfügbarkeitsgruppe gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="90267-139">However this usage is strongly discouraged, since the VNN-scoped path will stop working if the availability group is dropped.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="90267-140">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="90267-140">Related Tasks</span></span>  
  
-   [<span data-ttu-id="90267-141">Aktivieren und Konfigurieren von FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="90267-141">Enable and Configure FILESTREAM</span></span>](../../../relational-databases/blob/enable-and-configure-filestream.md)  
  
-   [<span data-ttu-id="90267-142">Aktivieren der erforderlichen Komponenten für FileTable</span><span class="sxs-lookup"><span data-stu-id="90267-142">Enable the Prerequisites for FileTable</span></span>](../../../relational-databases/blob/enable-the-prerequisites-for-filetable.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="90267-143">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="90267-143">Related Content</span></span>  
 <span data-ttu-id="90267-144">Keine.</span><span class="sxs-lookup"><span data-stu-id="90267-144">None.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90267-145">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="90267-145">See Also</span></span>  
 [<span data-ttu-id="90267-146">Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="90267-146">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
  
  
