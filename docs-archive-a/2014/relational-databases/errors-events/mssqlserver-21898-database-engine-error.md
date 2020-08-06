---
title: MSSQLSERVER_21898 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 21898 (Database Engine error)
ms.assetid: 02405b21-3d4e-4c2d-b4b3-d7b1ec05edb4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 78ce7eacf7f026bf9977af2c367b954a3639b357
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699656"
---
# <a name="mssqlserver_21898"></a><span data-ttu-id="13a95-102">MSSQLSERVER_21898</span><span class="sxs-lookup"><span data-stu-id="13a95-102">MSSQLSERVER_21898</span></span>
    
## <a name="details"></a><span data-ttu-id="13a95-103">Details</span><span class="sxs-lookup"><span data-stu-id="13a95-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="13a95-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="13a95-104">Product Name</span></span>|<span data-ttu-id="13a95-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="13a95-105">SQL Server</span></span>|  
|<span data-ttu-id="13a95-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="13a95-106">Event ID</span></span>|<span data-ttu-id="13a95-107">21898</span><span class="sxs-lookup"><span data-stu-id="13a95-107">21898</span></span>|  
|<span data-ttu-id="13a95-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="13a95-108">Event Source</span></span>|<span data-ttu-id="13a95-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="13a95-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="13a95-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="13a95-110">Component</span></span>|<span data-ttu-id="13a95-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="13a95-111">SQLEngine</span></span>|  
|<span data-ttu-id="13a95-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="13a95-112">Symbolic Name</span></span>|<span data-ttu-id="13a95-113">SQLErrorNum21898</span><span class="sxs-lookup"><span data-stu-id="13a95-113">SQLErrorNum21898</span></span>|  
|<span data-ttu-id="13a95-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="13a95-114">Message Text</span></span>|<span data-ttu-id="13a95-115">Der Verleger '%s' verwendet Verteilungsdatenbank '%s' und nicht '%s', die erforderlich ist, um die Veröffentlichungsdatenbank '%s' zu hosten.</span><span class="sxs-lookup"><span data-stu-id="13a95-115">The publisher '%s' uses distribution database '%s' and not '%s' which is required in order to host the publishing database '%s'.</span></span> <span data-ttu-id="13a95-116">Führen Sie `sp_changedistpublisher` auf dem Verteiler '%s' aus, um die vom Verleger verwendete Verteilungsdatenbank in '%s' zu ändern.</span><span class="sxs-lookup"><span data-stu-id="13a95-116">Run `sp_changedistpublisher` at distributor '%s' to change the distribution database used by the publisher to '%s'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="13a95-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="13a95-117">Explanation</span></span>  
 <span data-ttu-id="13a95-118">`sp_validate_redirected_publisher` fragt msdb.dbo.MSdistpublishers beim lokalen Verteiler ab, um zu überprüfen, ob die vom neuen Verleger verwendete Verteilungsdatenbank mit der vom ursprünglichen Verleger verwendeten Verteilungsdatenbank identisch ist.</span><span class="sxs-lookup"><span data-stu-id="13a95-118">`sp_validate_redirected_publisher` queries msdb.dbo.MSdistpublishers at the local distributor to verify that the distribution database used by the new publisher is the same as the distribution database used by the original publisher.</span></span> <span data-ttu-id="13a95-119">Dieser Fehler wird zurückgegeben, wenn diese Datenbanken verschieden sind und sich der Verleger deswegen nicht mehr als Host für die Verlegerdatenbank eignet.</span><span class="sxs-lookup"><span data-stu-id="13a95-119">This error is returned when these databases are different, making the publisher an unsuitable host for the publisher database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="13a95-120">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="13a95-120">User Action</span></span>  
 <span data-ttu-id="13a95-121">Führen Sie gespeicherte Prozedur `sp_changedistpublisher` aus, um die Verteilungsdatenbank für den neuen Verleger in die vom ursprünglichen Verleger verwendete Verteilungsdatenbank zu ändern.</span><span class="sxs-lookup"><span data-stu-id="13a95-121">Execute stored procedure `sp_changedistpublisher` to change the distribution database for the new publisher to that used by the original publisher.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="13a95-122">Durch die Ausführung von `sp_changedistpublisher` wird das Problem behoben, wenn die falsche Verteilungsdatenbank angegeben wurde, als `sp_adddistpublisher` beim Verteiler für den Verleger ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="13a95-122">Running `sp_changedistpublisher` will address the problem if the wrong distribution database was entered when `sp_adddistpublisher` was run at the distributor for the publisher.</span></span> <span data-ttu-id="13a95-123">Wenn der Remoteverleger jedoch über vorhandene Veröffentlichungen aus einer anderen Veröffentlichungsdatenbank verfügt, für die die identifizierte Verteilungsdatenbank genutzt wird, dann ist diese Änderung ungeeignet.</span><span class="sxs-lookup"><span data-stu-id="13a95-123">However, if the remote publisher has existing publications from another publishing database that make use of the identified distribution database, this change is not appropriate.</span></span> <span data-ttu-id="13a95-124">Die Replikation mit der benannten Verteilungsdatenbank muss systematisch entfernt und dann mit der Verteilungsdatenbank des ursprünglichen Verlegers wieder eingerichtet werden, damit der neue Verleger ordnungsgemäß als Host fungieren kann.</span><span class="sxs-lookup"><span data-stu-id="13a95-124">Replication using the named distribution database needs to be systematically removed and then reestablished using the original publisher's distribution database in order for the new publisher to function as a suitable host.</span></span>  
  
  
