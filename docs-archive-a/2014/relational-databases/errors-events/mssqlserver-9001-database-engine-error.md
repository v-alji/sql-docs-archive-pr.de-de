---
title: MSSQLSERVER_9001 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9001 (Database Engine error)
ms.assetid: a54de936-90c6-4845-aa96-29d32f154601
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0e61894d0d071fbdb36dcfb77895c46c61d0bbd1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719951"
---
# <a name="mssqlserver_9001"></a><span data-ttu-id="10a70-102">MSSQLSERVER_9001</span><span class="sxs-lookup"><span data-stu-id="10a70-102">MSSQLSERVER_9001</span></span>
    
## <a name="details"></a><span data-ttu-id="10a70-103">Details</span><span class="sxs-lookup"><span data-stu-id="10a70-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="10a70-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="10a70-104">Product Name</span></span>|<span data-ttu-id="10a70-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="10a70-105">SQL Server</span></span>|  
|<span data-ttu-id="10a70-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="10a70-106">Event ID</span></span>|<span data-ttu-id="10a70-107">9001</span><span class="sxs-lookup"><span data-stu-id="10a70-107">9001</span></span>|  
|<span data-ttu-id="10a70-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="10a70-108">Event Source</span></span>|<span data-ttu-id="10a70-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="10a70-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="10a70-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="10a70-110">Component</span></span>|<span data-ttu-id="10a70-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="10a70-111">SQLEngine</span></span>|  
|<span data-ttu-id="10a70-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="10a70-112">Symbolic Name</span></span>|<span data-ttu-id="10a70-113">LOG_NOT_AVAIL</span><span class="sxs-lookup"><span data-stu-id="10a70-113">LOG_NOT_AVAIL</span></span>|  
|<span data-ttu-id="10a70-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="10a70-114">Message Text</span></span>|<span data-ttu-id="10a70-115">Das Protokoll für die '%.\*ls'-Datenbank ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="10a70-115">The log for database '%.\*ls' is not available.</span></span> <span data-ttu-id="10a70-116">Überprüfen Sie das Ereignisprotokoll auf verwandte Fehlermeldungen.</span><span class="sxs-lookup"><span data-stu-id="10a70-116">Check the event log for related error messages.</span></span> <span data-ttu-id="10a70-117">Beheben Sie ggf. alle Fehler, und starten Sie die Datenbank neu.</span><span class="sxs-lookup"><span data-stu-id="10a70-117">Resolve any errors and restart the database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="10a70-118">Erklärung</span><span class="sxs-lookup"><span data-stu-id="10a70-118">Explanation</span></span>  
 <span data-ttu-id="10a70-119">Das Datenbankprotokoll wurde offline geschaltet</span><span class="sxs-lookup"><span data-stu-id="10a70-119">The database log was taken offline.</span></span> <span data-ttu-id="10a70-120">Normalerweise ist dies ein Zeichen für einen schwerwiegenden Fehle, der einen Neustart der Datenbank erfordert.</span><span class="sxs-lookup"><span data-stu-id="10a70-120">Usually this signifies a catastrophic failure that requires the database to restart.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="10a70-121">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="10a70-121">User Action</span></span>  
 <span data-ttu-id="10a70-122">Diagnostizieren Sie andere Fehler, und starten Sie die Instanz von SQL Server neu, wenn sie sich noch nicht selbst neu gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="10a70-122">Diagnose other errors and restart the instance of SQL Server if it has not already restarted itself.</span></span>  
  
  
