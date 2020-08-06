---
title: MSSQL_ENG021385 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG021385 error
ms.assetid: a2c0444f-d97b-4760-8905-3574791c2e26
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b73d3216f07cb44d750a37149634258648f1bd48
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697934"
---
# <a name="mssql_eng021385"></a><span data-ttu-id="f4fb1-102">MSSQL_ENG021385</span><span class="sxs-lookup"><span data-stu-id="f4fb1-102">MSSQL_ENG021385</span></span>
    
## <a name="message-details"></a><span data-ttu-id="f4fb1-103">Meldungsdetails</span><span class="sxs-lookup"><span data-stu-id="f4fb1-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f4fb1-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="f4fb1-104">Product Name</span></span>|<span data-ttu-id="f4fb1-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="f4fb1-105">SQL Server</span></span>|  
|<span data-ttu-id="f4fb1-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="f4fb1-106">Event ID</span></span>|<span data-ttu-id="f4fb1-107">21385</span><span class="sxs-lookup"><span data-stu-id="f4fb1-107">21385</span></span>|  
|<span data-ttu-id="f4fb1-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="f4fb1-108">Event Source</span></span>|<span data-ttu-id="f4fb1-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="f4fb1-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="f4fb1-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="f4fb1-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="f4fb1-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="f4fb1-111">Symbolic Name</span></span>||  
|<span data-ttu-id="f4fb1-112">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="f4fb1-112">Message Text</span></span>|<span data-ttu-id="f4fb1-113">Der Momentaufnahmevorgang konnte die %1!s!-Veröffentlichung nicht verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="f4fb1-113">Snapshot failed to process publication '%s'.</span></span> <span data-ttu-id="f4fb1-114">Möglicherweise ist gerade eine Schemaänderungsaktivität aktiv, oder es werden neue Artikel hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f4fb1-114">Possibly due to active schema change activity or new articles being added.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f4fb1-115">Erklärung</span><span class="sxs-lookup"><span data-stu-id="f4fb1-115">Explanation</span></span>  
 <span data-ttu-id="f4fb1-116">Dieser Fehler wird ausgelöst, wenn die Ausführung des Momentaufnahme-Agents beginnt, während gerade Änderungen an der Veröffentlichung vorgenommen werden, z. B. Hinzufügen oder Löschen von Artikeln oder das Ausführen von Schemaänderungen an veröffentlichten Objekten.</span><span class="sxs-lookup"><span data-stu-id="f4fb1-116">This error is raised if the Snapshot Agent starts running when there are ongoing changes to the publication database, including adding or dropping articles and performing schema changes on published objects.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f4fb1-117">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="f4fb1-117">User Action</span></span>  
 <span data-ttu-id="f4fb1-118">Starten Sie den Momentaufnahme-Agent erneut, nachdem die Änderungen an der Veröffentlichungsdatenbank abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="f4fb1-118">Restart the Snapshot Agent after changes to the publication database are complete.</span></span> <span data-ttu-id="f4fb1-119">Weitere Informationen finden Sie unter [Starten und Beenden eines Replikations-Agents &#40;SQL Server Management Studio&#41;](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) oder [Ausführbare Konzepte für die Programmierung von Replikations-Agents](concepts/replication-agent-executables-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="f4fb1-119">For more information, see [Start and Stop a Replication Agent &#40;SQL Server Management Studio&#41;](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) and [Replication Agent Executables Concepts](concepts/replication-agent-executables-concepts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4fb1-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f4fb1-120">See Also</span></span>  
 [<span data-ttu-id="f4fb1-121">Fehler- und Ereignisreferenz &#40;Replikation&#41;</span><span class="sxs-lookup"><span data-stu-id="f4fb1-121">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
