---
title: Nicht-SQL Server-Verleger | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- heterogeneous database replication, non-SQL Server Publishers
- non-SQL Server Publishers
- heterogeneous data sources, non-SQL Server Publishers
- Publishers [SQL Server replication], Oracle
ms.assetid: 08a160a6-33be-46b5-bc7b-d53180d8bdf1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f15f07dbf294d697afd385318f3dbf1447c8e2d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608554"
---
# <a name="non-sql-server-publishers"></a><span data-ttu-id="cebbf-102">Nicht-SQL Server-Verleger</span><span class="sxs-lookup"><span data-stu-id="cebbf-102">Non-SQL Server Publishers</span></span>
  <span data-ttu-id="cebbf-103">Durch das Veröffentlichen von Daten aus nicht-- [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Quellen können Sie Daten in konsolidieren [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cebbf-103">Publishing data from non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] sources allows you to consolidate data in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="cebbf-104">Mit[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] können Sie Momentaufnahme- oder Transaktionsdaten abonnieren, die aus einer Oracle-Datenbank veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="cebbf-104">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] can subscribe to snapshot or transactional data published from an Oracle database.</span></span> <span data-ttu-id="cebbf-105">Weitere Informationen zum Veröffentlichen mit Oracle finden Sie unter [Veröffentlichungen mit Oracle (Übersicht)](oracle-publishing-overview.md).</span><span class="sxs-lookup"><span data-stu-id="cebbf-105">For more information about publishing from Oracle, see [Oracle Publishing Overview](oracle-publishing-overview.md).</span></span>  
  
 <span data-ttu-id="cebbf-106">Die heterogene Replikation an Nicht-SQL Server-Abonnenten ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="cebbf-106">Heterogeneous replication to non-SQL Server subscribers is deprecated.</span></span> <span data-ttu-id="cebbf-107">Das Veröffentlichen mit Oracle ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="cebbf-107">Oracle Publishing is deprecated.</span></span> <span data-ttu-id="cebbf-108">Um Daten zu verschieben, erstellen Sie Lösungen mit Change Data Capture und [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cebbf-108">To move data, create solutions using change data capture and [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span></span>  
  
> [!CAUTION]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../../includes/ssnotedepfutureavoid-md.md)]  
  
 <span data-ttu-id="cebbf-109">Das Veröffentlichen von Daten aus Nicht-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Datenbanken eignet sich ideal für die folgenden Szenarien:</span><span class="sxs-lookup"><span data-stu-id="cebbf-109">Publishing from non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] databases is ideal for the following scenarios:</span></span>  
  
|<span data-ttu-id="cebbf-110">Szenario</span><span class="sxs-lookup"><span data-stu-id="cebbf-110">Scenario</span></span>|<span data-ttu-id="cebbf-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="cebbf-111">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="cebbf-112">Bereitstellungen von[!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="cebbf-112">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework application deployments</span></span>|<span data-ttu-id="cebbf-113">Führen Sie die Entwicklung mit [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Studio und [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] durch, und arbeiten Sie dabei mit Daten, die aus einer Nicht-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Datenbank repliziert wurden.</span><span class="sxs-lookup"><span data-stu-id="cebbf-113">Develop with [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Studio and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] while operating on data replicated from a non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database.</span></span>|  
|<span data-ttu-id="cebbf-114">Datawarehousing-Stagingserver</span><span class="sxs-lookup"><span data-stu-id="cebbf-114">Data warehousing staging servers</span></span>|<span data-ttu-id="cebbf-115">Sorgen Sie dafür, dass [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Stagingdatenbanken stets synchron mit der Nicht-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Datenbank sind.</span><span class="sxs-lookup"><span data-stu-id="cebbf-115">Keep [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] staging databases synchronized with a non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database.</span></span>|  
|<span data-ttu-id="cebbf-116">Migration nach [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cebbf-116">Migration to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]</span></span>|<span data-ttu-id="cebbf-117">Testen Sie Ihre Anwendung in Echtzeit mit [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , und replizieren Sie dabei die Änderungen am Quellsystem.</span><span class="sxs-lookup"><span data-stu-id="cebbf-117">Test your application in real time against [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] while replicating the source system's changes.</span></span> <span data-ttu-id="cebbf-118">Wechseln Sie endgültig zu [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , wenn Sie mit der Migration zufrieden sind.</span><span class="sxs-lookup"><span data-stu-id="cebbf-118">Switch to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] when satisfied with the migration.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cebbf-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cebbf-119">See Also</span></span>  
 [<span data-ttu-id="cebbf-120">Heterogene Datenbankreplikation</span><span class="sxs-lookup"><span data-stu-id="cebbf-120">Heterogeneous Database Replication</span></span>](heterogeneous-database-replication.md)  
  
  
