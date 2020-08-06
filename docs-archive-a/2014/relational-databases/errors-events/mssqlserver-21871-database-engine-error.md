---
title: MSSQLSERVER_21871 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 21871 (Database Engine error)
ms.assetid: d3215378-9282-444f-a18b-00b96fd0133d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f26211da21829a0a898dfb36ff9fefd453c7ad44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699651"
---
# <a name="mssqlserver_21871"></a><span data-ttu-id="973a5-102">MSSQLSERVER_21871</span><span class="sxs-lookup"><span data-stu-id="973a5-102">MSSQLSERVER_21871</span></span>
    
## <a name="details"></a><span data-ttu-id="973a5-103">Details</span><span class="sxs-lookup"><span data-stu-id="973a5-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="973a5-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="973a5-104">Product Name</span></span>|<span data-ttu-id="973a5-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="973a5-105">SQL Server</span></span>|  
|<span data-ttu-id="973a5-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="973a5-106">Event ID</span></span>|<span data-ttu-id="973a5-107">21871</span><span class="sxs-lookup"><span data-stu-id="973a5-107">21871</span></span>|  
|<span data-ttu-id="973a5-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="973a5-108">Event Source</span></span>|<span data-ttu-id="973a5-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="973a5-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="973a5-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="973a5-110">Component</span></span>|<span data-ttu-id="973a5-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="973a5-111">SQLEngine</span></span>|  
|<span data-ttu-id="973a5-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="973a5-112">Symbolic Name</span></span>|<span data-ttu-id="973a5-113">SQLErrorNum21871</span><span class="sxs-lookup"><span data-stu-id="973a5-113">SQLErrorNum21871</span></span>|  
|<span data-ttu-id="973a5-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="973a5-114">Message Text</span></span>|<span data-ttu-id="973a5-115">Verleger %s der Datenbank %s wurde nicht umgeleitet.</span><span class="sxs-lookup"><span data-stu-id="973a5-115">Publisher %s of database %s has not been redirected.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="973a5-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="973a5-116">Explanation</span></span>  
 <span data-ttu-id="973a5-117">`sp_validate_replica_hosts_as_publishers` überprüft die Tabelle MSredirected_publishers in der Verteilungsdatenbank auf einen Eintrag für den identifizierten Verleger und die Verlegerdatenbank.</span><span class="sxs-lookup"><span data-stu-id="973a5-117">`sp_validate_replica_hosts_as_publishers` checks the table MSredirected_publishers in the distribution database for an entry for the identified publisher and publisher database.</span></span>  <span data-ttu-id="973a5-118">`sp_validate_replica_hosts_as_publishers` gibt den Fehler 21871 zurück, wenn kein Eintrag gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="973a5-118">`sp_validate_replica_hosts_as_publishers` returns error 21871 when no entry is found.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="973a5-119">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="973a5-119">User Action</span></span>  
 <span data-ttu-id="973a5-120">`sp_validate_replica_hosts_as_publishers` ist nur für umgeleitete Verleger relevant.</span><span class="sxs-lookup"><span data-stu-id="973a5-120">`sp_validate_replica_hosts_as_publishers` is only relevant for redirected publishers.</span></span> <span data-ttu-id="973a5-121">Wenn eine veröffentlichte Datenbank Mitglied einer AlwaysOn-Verfügbarkeitsgruppe ist, führen Sie die gespeicherte Prozedur `sp_redirect_publisher` aus, um den Verleger und die Verlegerdatenbank mit dem Verfügbarkeitsgruppenlistenernamen der Verfügbarkeitsgruppe zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="973a5-121">If the publisher database is a member of an availability group, use the stored procedure `sp_redirect_publisher` to associate the publisher and publisher database with the Availability Group Listener Name of the availability group.</span></span>  
  
  
