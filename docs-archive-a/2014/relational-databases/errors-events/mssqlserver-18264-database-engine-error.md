---
title: MSSQLSERVER_18264 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 18264 (Database Engine error)
ms.assetid: 3050fc56-2be5-43cf-916b-50a3ac5f89aa
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3edfeb82601e254c02df87cc4a978b9ab5e653e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619144"
---
# <a name="mssqlserver_18264"></a><span data-ttu-id="671aa-102">MSSQLSERVER_18264</span><span class="sxs-lookup"><span data-stu-id="671aa-102">MSSQLSERVER_18264</span></span>
    
## <a name="details"></a><span data-ttu-id="671aa-103">Details</span><span class="sxs-lookup"><span data-stu-id="671aa-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="671aa-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="671aa-104">Product Name</span></span>|<span data-ttu-id="671aa-105">Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="671aa-105">Microsoft SQL Server</span></span>|  
|<span data-ttu-id="671aa-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="671aa-106">Event ID</span></span>|<span data-ttu-id="671aa-107">18264</span><span class="sxs-lookup"><span data-stu-id="671aa-107">18264</span></span>|  
|<span data-ttu-id="671aa-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="671aa-108">Event Source</span></span>|<span data-ttu-id="671aa-109">MSSQLENGINE</span><span class="sxs-lookup"><span data-stu-id="671aa-109">MSSQLENGINE</span></span>|  
|<span data-ttu-id="671aa-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="671aa-110">Component</span></span>|<span data-ttu-id="671aa-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="671aa-111">SQLEngine</span></span>|  
|<span data-ttu-id="671aa-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="671aa-112">Symbolic Name</span></span>|<span data-ttu-id="671aa-113">STRMIO_DBDUMP</span><span class="sxs-lookup"><span data-stu-id="671aa-113">STRMIO_DBDUMP</span></span>|  
|<span data-ttu-id="671aa-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="671aa-114">Message Text</span></span>|<span data-ttu-id="671aa-115">Die Datenbank wurde gesichert.</span><span class="sxs-lookup"><span data-stu-id="671aa-115">Database backed up.</span></span> <span data-ttu-id="671aa-116">Datenbank: %s, Erstellungsdatum(-zeit): %s(%s), gesicherte Seiten: %d, Erste LSN: %s, Letzte LSN: %s, Anzahl der Sicherungsgeräte: %d, Geräteinformationen: (%s).</span><span class="sxs-lookup"><span data-stu-id="671aa-116">Database: %s, creation date(time): %s(%s), pages dumped: %d, first LSN: %s, last LSN: %s, number of dump devices: %d, device information: (%s).</span></span> <span data-ttu-id="671aa-117">Diese Meldung dient nur zu Informationszwecken.</span><span class="sxs-lookup"><span data-stu-id="671aa-117">This is an informational message only.</span></span> <span data-ttu-id="671aa-118">Es ist keine Benutzeraktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="671aa-118">No user action is required.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="671aa-119">Erklärung</span><span class="sxs-lookup"><span data-stu-id="671aa-119">Explanation</span></span>  
 <span data-ttu-id="671aa-120">Standardmäßig wird diese Informationsmeldung bei jeder erfolgreichen Sicherung dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Fehlerprotokoll und dem Systemereignisprotokoll hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="671aa-120">By default, every successful backup adds this informational message to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log and the system event log.</span></span> <span data-ttu-id="671aa-121">Wenn Sie das Transaktionsprotokoll sehr häufig sichern, kann die Anzahl dieser Meldungen schnell ansteigen, d.h., es entstehen sehr große Fehlerprotokolle, die das Suchen nach anderen Meldungen erschweren können.</span><span class="sxs-lookup"><span data-stu-id="671aa-121">If you very frequently back up the transaction log, these messages can accumulate quickly, creating very large error logs that can make finding other messages difficult.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="671aa-122">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="671aa-122">User Action</span></span>  
 <span data-ttu-id="671aa-123">Sie können diese Protokolleinträge mit dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Ablaufverfolgungsflag **3226** unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="671aa-123">You can suppress these log entries by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] trace flag **3226**.</span></span> <span data-ttu-id="671aa-124">Es ist sehr hilfreich, dieses Ablaufverfolgungsflag zu aktivieren, wenn Sie regelmäßig Protokollsicherungen ausführen und keines der Skripts von diesen Einträgen abhängig ist.</span><span class="sxs-lookup"><span data-stu-id="671aa-124">Enabling this trace flag is useful if you are running frequent log backups and if none of your scripts depend on those entries.</span></span>  
  
 <span data-ttu-id="671aa-125">Weitere Informationen zum Verwenden von Ablaufverfolgungsflags finden Sie in der SQL Server-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="671aa-125">For information about using trace flags, see SQL Server Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="671aa-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="671aa-126">See Also</span></span>  
 [<span data-ttu-id="671aa-127">Ablaufverfolgungsflags &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="671aa-127">Trace Flags &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql)  
  
  
