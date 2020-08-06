---
title: MSSQL_ENG014144 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014144 error
ms.assetid: fdc744d5-530e-48c4-9420-cca032fd482b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0d93f06a585bcc01c52438ff7b99bbd635532402
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607670"
---
# <a name="mssql_eng014144"></a><span data-ttu-id="4126f-102">MSSQL_ENG014144</span><span class="sxs-lookup"><span data-stu-id="4126f-102">MSSQL_ENG014144</span></span>
    
## <a name="message-details"></a><span data-ttu-id="4126f-103">Meldungsdetails</span><span class="sxs-lookup"><span data-stu-id="4126f-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4126f-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="4126f-104">Product Name</span></span>|<span data-ttu-id="4126f-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="4126f-105">SQL Server</span></span>|  
|<span data-ttu-id="4126f-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="4126f-106">Event ID</span></span>|<span data-ttu-id="4126f-107">14144</span><span class="sxs-lookup"><span data-stu-id="4126f-107">14144</span></span>|  
|<span data-ttu-id="4126f-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="4126f-108">Event Source</span></span>|<span data-ttu-id="4126f-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="4126f-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="4126f-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="4126f-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="4126f-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="4126f-111">Symbolic Name</span></span>||  
|<span data-ttu-id="4126f-112">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="4126f-112">Message Text</span></span>|<span data-ttu-id="4126f-113">Der '%s'-Abonnent kann nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="4126f-113">Cannot drop Subscriber '%s'.</span></span> <span data-ttu-id="4126f-114">Für ihn sind Abonnements in der %2!s!-Veröffentlichungsdatenbank vorhanden.</span><span class="sxs-lookup"><span data-stu-id="4126f-114">There are subscriptions for it in the publication database '%s'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4126f-115">Erklärung</span><span class="sxs-lookup"><span data-stu-id="4126f-115">Explanation</span></span>  
 <span data-ttu-id="4126f-116">Eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz, die als Abonnent konfiguriert ist, kann nicht aus der Rolle des Abonnenten entfernt werden, so lange für die Instanz aktive Abonnements konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="4126f-116">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that is configured as a Subscriber cannot be removed from the role of Subscriber while there are active subscriptions configured for the instance.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4126f-117">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="4126f-117">User Action</span></span>  
 <span data-ttu-id="4126f-118">Löschen Sie alle zugeordneten Abonnements, bevor Sie versuchen, den Abonnentenstatus der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz zu ändern:</span><span class="sxs-lookup"><span data-stu-id="4126f-118">Drop all associated subscriptions before attempting to change the Subscriber status of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance:</span></span>  
  
1.  <span data-ttu-id="4126f-119">Führen Sie [sp_helpsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql) in der Publikationsdatenbank auf dem Verleger aus, um nach Abonnements zu suchen.</span><span class="sxs-lookup"><span data-stu-id="4126f-119">Execute [sp_helpsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql) in the publication database at the Publisher to find subscriptions.</span></span>  
  
2.  <span data-ttu-id="4126f-120">Führen Sie [sp_dropsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropsubscription-transact-sql) in der Publikationsdatenbank aus, um Abonnements zu löschen.</span><span class="sxs-lookup"><span data-stu-id="4126f-120">Execute [sp_dropsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropsubscription-transact-sql) in the publication database to drop subscriptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4126f-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4126f-121">See Also</span></span>  
 <span data-ttu-id="4126f-122">[Fehler- und Ereignisreferenz &#40;Replikation&#41;](errors-and-events-reference-replication.md) </span><span class="sxs-lookup"><span data-stu-id="4126f-122">[Errors and Events Reference &#40;Replication&#41;](errors-and-events-reference-replication.md) </span></span>  
 [<span data-ttu-id="4126f-123">Abonnieren von Veröffentlichungen</span><span class="sxs-lookup"><span data-stu-id="4126f-123">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
