---
title: MSSQL_ENG014120 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014120 error
ms.assetid: 6b169a3b-30da-4981-b998-b52d61811572
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e7f3484d9344a203ca8c44fee6b79605163ea069
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607674"
---
# <a name="mssql_eng014120"></a><span data-ttu-id="7855d-102">MSSQL_ENG014120</span><span class="sxs-lookup"><span data-stu-id="7855d-102">MSSQL_ENG014120</span></span>
    
## <a name="message-details"></a><span data-ttu-id="7855d-103">Meldungsdetails</span><span class="sxs-lookup"><span data-stu-id="7855d-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7855d-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="7855d-104">Product Name</span></span>|<span data-ttu-id="7855d-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="7855d-105">SQL Server</span></span>|  
|<span data-ttu-id="7855d-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="7855d-106">Event ID</span></span>|<span data-ttu-id="7855d-107">14120</span><span class="sxs-lookup"><span data-stu-id="7855d-107">14120</span></span>|  
|<span data-ttu-id="7855d-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="7855d-108">Event Source</span></span>|<span data-ttu-id="7855d-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7855d-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7855d-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="7855d-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="7855d-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="7855d-111">Symbolic Name</span></span>||  
|<span data-ttu-id="7855d-112">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="7855d-112">Message Text</span></span>|<span data-ttu-id="7855d-113">Die %1!s!-Verteilungsdatenbank konnte nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="7855d-113">Could not drop the distribution database '%s'.</span></span> <span data-ttu-id="7855d-114">Diese Verteilerdatenbank ist einem Verleger zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="7855d-114">This distributor database is associated with a Publisher.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7855d-115">Erklärung</span><span class="sxs-lookup"><span data-stu-id="7855d-115">Explanation</span></span>  
 <span data-ttu-id="7855d-116">In der Verteilungsdatenbank werden Metadaten und Verlaufsdaten für alle Replikations- und Transaktionstypen für die Transaktionsreplikation gespeichert.</span><span class="sxs-lookup"><span data-stu-id="7855d-116">The distribution database stores metadata and history data for all types of replication and transactions for transactional replication.</span></span> <span data-ttu-id="7855d-117">Dieser Fehler tritt bei dem Versuch auf, eine Verteilungsdatenbank zu löschen, die einem oder mehreren Verleger(n) zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="7855d-117">This error occurs if you attempt to drop a distribution database that is associated with one or more Publishers.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7855d-118">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="7855d-118">User Action</span></span>  
 <span data-ttu-id="7855d-119">Um eine Verteilungsdatenbank löschen zu können, müssen Sie zuerst die Zuordnung zwischen dem Verteiler und dem Verleger löschen.</span><span class="sxs-lookup"><span data-stu-id="7855d-119">To drop a distribution database you must first drop the association between the Distributor and the Publisher.</span></span> <span data-ttu-id="7855d-120">Weitere Informationen finden Sie unter [sp_dropdistpublisher &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropdistpublisher-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7855d-120">For more information, see [sp_dropdistpublisher &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropdistpublisher-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7855d-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7855d-121">See Also</span></span>  
 <span data-ttu-id="7855d-122">[Fehler- und Ereignisreferenz &#40;Replikation&#41;](errors-and-events-reference-replication.md) </span><span class="sxs-lookup"><span data-stu-id="7855d-122">[Errors and Events Reference &#40;Replication&#41;](errors-and-events-reference-replication.md) </span></span>  
 [<span data-ttu-id="7855d-123">Verteilung konfigurieren</span><span class="sxs-lookup"><span data-stu-id="7855d-123">Configure Distribution</span></span>](configure-distribution.md)  
  
  
