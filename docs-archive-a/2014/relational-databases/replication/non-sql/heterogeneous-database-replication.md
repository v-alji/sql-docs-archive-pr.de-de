---
title: Heterogene Datenbankreplikation | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- heterogeneous database replication, about heterogeneous database replication
- replication [SQL Server], heterogeneous database replication
- heterogeneous database replication
ms.assetid: 3fd983ad-e206-45db-9054-417c9b5bb815
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d8988a425bc9519d43b8100e4cd34418114edae1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721307"
---
# <a name="heterogeneous-database-replication"></a><span data-ttu-id="e19d7-102">Heterogene Datenbankreplikation</span><span class="sxs-lookup"><span data-stu-id="e19d7-102">Heterogeneous Database Replication</span></span>
  [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="e19d7-103">unterstützt die folgenden heterogenen Szenarien für die Transaktions- und Momentaufnahmereplikation:</span><span class="sxs-lookup"><span data-stu-id="e19d7-103">supports the following heterogeneous scenarios for transactional and snapshot replication:</span></span>  
  
-   <span data-ttu-id="e19d7-104">Veröffentlichen von Daten aus Oracle in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e19d7-104">Publishing data from Oracle to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="e19d7-105">Veröffentlichen von Daten aus [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] an Nicht-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Abonnenten.</span><span class="sxs-lookup"><span data-stu-id="e19d7-105">Publishing data from [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Subscribers.</span></span>  
  
 <span data-ttu-id="e19d7-106">Die heterogene Replikation an Nicht-SQL Server-Abonnenten ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="e19d7-106">Heterogeneous replication to non-SQL Server subscribers is deprecated.</span></span> <span data-ttu-id="e19d7-107">Das Veröffentlichen mit Oracle ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="e19d7-107">Oracle Publishing is deprecated.</span></span> <span data-ttu-id="e19d7-108">Um Daten zu verschieben, erstellen Sie Lösungen mit Change Data Capture und [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e19d7-108">To move data, create solutions using change data capture and [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span></span>  
  
> [!CAUTION]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../../includes/ssnotedepfutureavoid-md.md)]  
  
## <a name="publishing-data-from-oracle"></a><span data-ttu-id="e19d7-109">Veröffentlichen von Daten aus Oracle</span><span class="sxs-lookup"><span data-stu-id="e19d7-109">Publishing Data from Oracle</span></span>  
 <span data-ttu-id="e19d7-110">Mit [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] können Sie Daten aus Oracle mit einem Großteil der Funktionen und ebenso einfach veröffentlichen wie bei der Momentaufnahme- und Transaktionsreplikation in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e19d7-110">You can use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to publish data from Oracle with most of the same features and ease-of-use as [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] snapshot and transactional replication.</span></span> <span data-ttu-id="e19d7-111">Das Veröffentlichen von Daten aus Oracle eignet sich ideal für die folgenden Szenarien:</span><span class="sxs-lookup"><span data-stu-id="e19d7-111">Publishing data from Oracle is ideal for the following scenarios:</span></span>  
  
|<span data-ttu-id="e19d7-112">Szenario</span><span class="sxs-lookup"><span data-stu-id="e19d7-112">Scenario</span></span>|<span data-ttu-id="e19d7-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e19d7-113">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="e19d7-114">Bereitstellungen von[!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="e19d7-114">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework application deployments</span></span>|<span data-ttu-id="e19d7-115">Führen Sie die Entwicklung mit [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Studio und [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] durch, und arbeiten Sie dabei mit Daten, die aus einer Nicht-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Datenbank repliziert wurden.</span><span class="sxs-lookup"><span data-stu-id="e19d7-115">Develop with [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Studio and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] while operating on data replicated from a non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database.</span></span>|  
|<span data-ttu-id="e19d7-116">Datawarehousing-Stagingserver</span><span class="sxs-lookup"><span data-stu-id="e19d7-116">Data warehousing staging servers</span></span>|<span data-ttu-id="e19d7-117">Sorgen Sie dafür, dass [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Stagingdatenbanken stets synchron mit der Nicht-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Datenbank sind.</span><span class="sxs-lookup"><span data-stu-id="e19d7-117">Keep [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] staging databases synchronized with a non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database.</span></span>|  
|<span data-ttu-id="e19d7-118">Migration nach [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e19d7-118">Migration to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]</span></span>|<span data-ttu-id="e19d7-119">Testen Sie Ihre Anwendung in Echtzeit mit [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , und replizieren Sie dabei die Änderungen am Quellsystem.</span><span class="sxs-lookup"><span data-stu-id="e19d7-119">Test your application in real time against [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] while replicating the source system's changes.</span></span> <span data-ttu-id="e19d7-120">Wechseln Sie endgültig zu [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , wenn Sie mit der Migration zufrieden sind.</span><span class="sxs-lookup"><span data-stu-id="e19d7-120">Switch to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] when satisfied with the migration.</span></span>|  
  
 <span data-ttu-id="e19d7-121">Weitere Informationen finden Sie unter [Veröffentlichungen mit Oracle (Übersicht)](oracle-publishing-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e19d7-121">For more information, see [Oracle Publishing Overview](oracle-publishing-overview.md).</span></span>  
  
## <a name="publishing-data-to-non-sql-server-subscribers"></a><span data-ttu-id="e19d7-122">Veröffentlichen von Daten für Nicht-SQL Server-Abonnenten</span><span class="sxs-lookup"><span data-stu-id="e19d7-122">Publishing Data to Non-SQL Server Subscribers</span></span>  
 <span data-ttu-id="e19d7-123">Die folgenden Nicht-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Datenbanken werden als Abonnenten für Momentaufnahme- und Transaktionsveröffentlichungen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="e19d7-123">The following non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] databases are supported as Subscribers to snapshot and transactional publications:</span></span>  
  
-   <span data-ttu-id="e19d7-124">Oracle für alle Plattformen, die durch Oracle unterstützt werden</span><span class="sxs-lookup"><span data-stu-id="e19d7-124">Oracle for all platforms that Oracle supports.</span></span>  
  
-   <span data-ttu-id="e19d7-125">IBM DB2 für AS400, MVS, Unix, Linux und Windows.</span><span class="sxs-lookup"><span data-stu-id="e19d7-125">IBM DB2 for AS400, MVS, Unix, Linux, and Windows.</span></span>  
  
 <span data-ttu-id="e19d7-126">Weitere Informationen finden Sie unter [Non-SQL Server Subscribers](non-sql-server-subscribers.md).</span><span class="sxs-lookup"><span data-stu-id="e19d7-126">For more information, see [Non-SQL Server Subscribers](non-sql-server-subscribers.md).</span></span>  
  
  
