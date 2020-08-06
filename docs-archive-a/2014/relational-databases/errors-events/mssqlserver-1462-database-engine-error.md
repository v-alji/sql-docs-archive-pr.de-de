---
title: MSSQLSERVER_1462 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1462 (Database Engine error)
ms.assetid: 680e9c1c-a9d6-4765-b601-956d0a83324c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 704b847bde2d7b4da9da91b4b24bfe2b9e2afa07
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620948"
---
# <a name="mssqlserver_1462"></a><span data-ttu-id="86035-102">MSSQLSERVER_1462</span><span class="sxs-lookup"><span data-stu-id="86035-102">MSSQLSERVER_1462</span></span>
    
## <a name="details"></a><span data-ttu-id="86035-103">Details</span><span class="sxs-lookup"><span data-stu-id="86035-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="86035-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="86035-104">Product Name</span></span>|<span data-ttu-id="86035-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="86035-105">SQL Server</span></span>|  
|<span data-ttu-id="86035-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="86035-106">Event ID</span></span>|<span data-ttu-id="86035-107">1462</span><span class="sxs-lookup"><span data-stu-id="86035-107">1462</span></span>|  
|<span data-ttu-id="86035-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="86035-108">Event Source</span></span>|<span data-ttu-id="86035-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="86035-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="86035-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="86035-110">Component</span></span>|<span data-ttu-id="86035-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="86035-111">SQLEngine</span></span>|  
|<span data-ttu-id="86035-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="86035-112">Symbolic Name</span></span>|<span data-ttu-id="86035-113">DBM_DISABLED_DUE_TO_FAILED_REDO</span><span class="sxs-lookup"><span data-stu-id="86035-113">DBM_DISABLED_DUE_TO_FAILED_REDO</span></span>|  
|<span data-ttu-id="86035-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="86035-114">Message Text</span></span>|<span data-ttu-id="86035-115">Die Datenbankspiegelung wird aufgrund eines Fehlers beim Wiederholungsvorgang deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="86035-115">Database mirroring is disabled due to a failed redo operation.</span></span> <span data-ttu-id="86035-116">Der Vorgang kann nicht fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="86035-116">Unable to resume.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="86035-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="86035-117">Explanation</span></span>  
 <span data-ttu-id="86035-118">Bei der Datenbankspiegelung ist beim Wiederholungsvorgang für einen Protokolldatensatz für den Spiegel ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="86035-118">Database mirroring failed to redo a log record on the mirror.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="86035-119">Mögliche Ursachen</span><span class="sxs-lookup"><span data-stu-id="86035-119">Possible Causes</span></span>  
 <span data-ttu-id="86035-120">Die wahrscheinlichste Ursache besteht darin, dass ein Vorgang zum Hinzufügen einer Datei für die Prinzipaldatenbank abgeschlossen wurde, bei diesem Vorgang auf der Spiegeldatenbank jedoch ein Fehler aufgetreten ist, da sich Dateinamen oder Verzeichnisstrukturen auf dem Prinzipalserver und dem Spiegelserver unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="86035-120">The most likely cause is that an add-file operation completed on the principal database but then failed on the mirror database because file names or directory structures differ on the principal server and mirror server.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="86035-121">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="86035-121">User Action</span></span>  
 <span data-ttu-id="86035-122">Suchen Sie im [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Fehlerprotokoll nach der Fehlerursache.</span><span class="sxs-lookup"><span data-stu-id="86035-122">Look in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log for the cause of this error.</span></span> <span data-ttu-id="86035-123">Versuchen Sie, die Fehlerursache zu beheben, und setzen Sie anschließend die Datenbankspiegelung fort.</span><span class="sxs-lookup"><span data-stu-id="86035-123">Try to resolve the cause and resume mirroring on the database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86035-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="86035-124">See Also</span></span>  
 [<span data-ttu-id="86035-125">Problembehandlung für die Datenbankspiegelungskonfiguration &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="86035-125">Troubleshoot Database Mirroring Configuration &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/troubleshoot-database-mirroring-configuration-sql-server.md)  
  
  
