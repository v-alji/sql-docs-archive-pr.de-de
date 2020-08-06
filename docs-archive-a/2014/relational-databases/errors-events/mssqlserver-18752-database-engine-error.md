---
title: MSSQLSERVER_18752 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 18752 (Database Engine error)
ms.assetid: 234c58d8-7a1e-4b07-a64b-32a311527980
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a463e4019875f4a233ae2920f32bc2252376a41c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617077"
---
# <a name="mssqlserver_18752"></a><span data-ttu-id="bcedf-102">MSSQLSERVER_18752</span><span class="sxs-lookup"><span data-stu-id="bcedf-102">MSSQLSERVER_18752</span></span>
    
## <a name="details"></a><span data-ttu-id="bcedf-103">Details</span><span class="sxs-lookup"><span data-stu-id="bcedf-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bcedf-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="bcedf-104">Product Name</span></span>|<span data-ttu-id="bcedf-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="bcedf-105">SQL Server</span></span>|  
|<span data-ttu-id="bcedf-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="bcedf-106">Event ID</span></span>|<span data-ttu-id="bcedf-107">18752</span><span class="sxs-lookup"><span data-stu-id="bcedf-107">18752</span></span>|  
|<span data-ttu-id="bcedf-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="bcedf-108">Event Source</span></span>|<span data-ttu-id="bcedf-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="bcedf-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="bcedf-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="bcedf-110">Component</span></span>|<span data-ttu-id="bcedf-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="bcedf-111">SQLEngine</span></span>|  
|<span data-ttu-id="bcedf-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="bcedf-112">Symbolic Name</span></span>|<span data-ttu-id="bcedf-113">REPL_INUSE</span><span class="sxs-lookup"><span data-stu-id="bcedf-113">REPL_INUSE</span></span>|  
|<span data-ttu-id="bcedf-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="bcedf-114">Message Text</span></span>|<span data-ttu-id="bcedf-115">Nur jeweils ein Protokolllese-Agent oder eine protokollbezogene Prozedur (sp_repldone, sp_replcmds oder sp_replshowcmds) kann eine Verbindung mit einer Datenbank herstellen.</span><span class="sxs-lookup"><span data-stu-id="bcedf-115">Only one Log Reader Agent or log-related procedure (sp_repldone, sp_replcmds, and sp_replshowcmds) can connect to a database at a time.</span></span> <span data-ttu-id="bcedf-116">Falls Sie eine protokollbezogene Prozedur ausgeführt haben, löschen Sie vor dem Starten des Protokolllese-Agents oder dem Ausführen einer weiteren protokollbezogenen Prozedur die Verbindung, über die sie ausgeführt wurde, oder führen Sie 'sp_replflush' über diese Verbindung aus.</span><span class="sxs-lookup"><span data-stu-id="bcedf-116">If you executed a log-related procedure, drop the connection over which the procedure was executed or execute sp_replflush over that connection before starting the Log Reader Agent or executing another log-related procedure.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="bcedf-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="bcedf-117">Explanation</span></span>  
 <span data-ttu-id="bcedf-118">Nur jeweils ein Protokolllese-Agent oder eine protokollbezogene Prozedur kann eine Verbindung mit einer Datenbank herstellen.</span><span class="sxs-lookup"><span data-stu-id="bcedf-118">Only one Log Reader agent or log-related procedure can connect to a database at a time.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bcedf-119">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="bcedf-119">User Action</span></span>  
 <span data-ttu-id="bcedf-120">Stellen Sie sicher, dass kein weiterer Protokolllese-Agent für die gleiche Veröffentlichungsdatenbank ausgeführt wird und dass keine aktive Verbindung zuvor sp_replcmds/sp_repltrans/sp_repldone ausgeführt hat, ohne anschließend sp_replflush auszuführen oder die Verbindung zu trennen.</span><span class="sxs-lookup"><span data-stu-id="bcedf-120">Make sure no other logreader is running for the same publishing database, and no other active connection had previously run sp_replcmds/sp_repltrans/sp_repldone without running sp_replflush afterwards or disconnecting.</span></span>  
  
  
