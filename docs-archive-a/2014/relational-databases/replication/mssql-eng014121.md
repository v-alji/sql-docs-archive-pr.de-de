---
title: MSSQL_ENG014121 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014121 error
ms.assetid: c8595854-cce1-4566-ad64-d565555caded
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 04d4cbdd2197745d2d795814d88c4f7bc28eb90e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607675"
---
# <a name="mssql_eng014121"></a><span data-ttu-id="7ec8a-102">MSSQL_ENG014121</span><span class="sxs-lookup"><span data-stu-id="7ec8a-102">MSSQL_ENG014121</span></span>
    
## <a name="message-details"></a><span data-ttu-id="7ec8a-103">Meldungsdetails</span><span class="sxs-lookup"><span data-stu-id="7ec8a-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7ec8a-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="7ec8a-104">Product Name</span></span>|<span data-ttu-id="7ec8a-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="7ec8a-105">SQL Server</span></span>|  
|<span data-ttu-id="7ec8a-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="7ec8a-106">Event ID</span></span>|<span data-ttu-id="7ec8a-107">14121</span><span class="sxs-lookup"><span data-stu-id="7ec8a-107">14121</span></span>|  
|<span data-ttu-id="7ec8a-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="7ec8a-108">Event Source</span></span>|<span data-ttu-id="7ec8a-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7ec8a-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7ec8a-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="7ec8a-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="7ec8a-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="7ec8a-111">Symbolic Name</span></span>||  
|<span data-ttu-id="7ec8a-112">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="7ec8a-112">Message Text</span></span>|<span data-ttu-id="7ec8a-113">Der Verteiler '%1!s!' konnte nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="7ec8a-113">Could not drop the Distributor '%s'.</span></span> <span data-ttu-id="7ec8a-114">Dieser Verteiler besitzt zugeordnete Verteilungsdatenbanken.</span><span class="sxs-lookup"><span data-stu-id="7ec8a-114">This Distributor has associated distribution databases.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7ec8a-115">Erklärung</span><span class="sxs-lookup"><span data-stu-id="7ec8a-115">Explanation</span></span>  
 <span data-ttu-id="7ec8a-116">Eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz, die als Verteiler konfiguriert ist, kann nicht aus der Rolle des Verteilers entfernt werden, da der Instanz Verteilungsdatenbanken zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="7ec8a-116">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that is configured as a Distributor cannot be removed from the role of Distributor because there are distribution databases associated with the instance.</span></span> <span data-ttu-id="7ec8a-117">Dieser Fehler tritt bei dem Versuch auf, eine Verteilungsdatenbank zu löschen, die einem oder mehreren Verleger(n) zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="7ec8a-117">This error occurs if you attempt to drop a distribution database that is associated with one or more Publishers.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7ec8a-118">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="7ec8a-118">User Action</span></span>  
 <span data-ttu-id="7ec8a-119">Wenn Sie die Namen der Verleger und Verteilungsdatenbanken ermitteln möchten, die diesem Verteiler zugeordnet sind, führen Sie in einer beliebigen Datenbank auf dem Verteiler [sp_helpdistpublisher &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpdistpublisher-transact-sql) aus.</span><span class="sxs-lookup"><span data-stu-id="7ec8a-119">To find the names of any Publishers and distribution databases associated with this Distributor, execute [sp_helpdistpublisher &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpdistpublisher-transact-sql) from any database on the Distributor.</span></span>  
  
 <span data-ttu-id="7ec8a-120">Führen Sie [sp_dropdistributiondb &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropdistributiondb-transact-sql) für alle Verteilungsdatenbanken aus, die diesem Verteiler zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="7ec8a-120">Execute [sp_dropdistributiondb &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropdistributiondb-transact-sql) for any distribution databases associated with this Distributor.</span></span> <span data-ttu-id="7ec8a-121">Nachdem alle Verteilungsdatenbankenzuordnungen entfernt sind, können Sie die Verteilung deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="7ec8a-121">After all distribution database associations are removed, you can disable distribution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ec8a-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7ec8a-122">See Also</span></span>  
 <span data-ttu-id="7ec8a-123">[Fehler- und Ereignisreferenz &#40;Replikation&#41;](errors-and-events-reference-replication.md) </span><span class="sxs-lookup"><span data-stu-id="7ec8a-123">[Errors and Events Reference &#40;Replication&#41;](errors-and-events-reference-replication.md) </span></span>  
 [<span data-ttu-id="7ec8a-124">Verteilung konfigurieren</span><span class="sxs-lookup"><span data-stu-id="7ec8a-124">Configure Distribution</span></span>](configure-distribution.md)  
  
  
