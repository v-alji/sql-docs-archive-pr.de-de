---
title: MSSQLSERVER_32040 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 32040 (Database Engine error)
ms.assetid: 709219b1-f8b2-4696-8923-dd2e91492eb8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 05692e2f20b0719c1ca8f48282c3b7aaed8e2341
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617075"
---
# <a name="mssqlserver_32040"></a><span data-ttu-id="f010c-102">MSSQLSERVER_32040</span><span class="sxs-lookup"><span data-stu-id="f010c-102">MSSQLSERVER_32040</span></span>
    
## <a name="details"></a><span data-ttu-id="f010c-103">Details</span><span class="sxs-lookup"><span data-stu-id="f010c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f010c-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="f010c-104">Product Name</span></span>|<span data-ttu-id="f010c-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="f010c-105">SQL Server</span></span>|  
|<span data-ttu-id="f010c-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="f010c-106">Event ID</span></span>|<span data-ttu-id="f010c-107">32040</span><span class="sxs-lookup"><span data-stu-id="f010c-107">32040</span></span>|  
|<span data-ttu-id="f010c-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="f010c-108">Event Source</span></span>|<span data-ttu-id="f010c-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="f010c-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="f010c-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="f010c-110">Component</span></span>|<span data-ttu-id="f010c-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="f010c-111">SQLEngine</span></span>|  
|<span data-ttu-id="f010c-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="f010c-112">Symbolic Name</span></span>|<span data-ttu-id="f010c-113">SQLErrorNum32040</span><span class="sxs-lookup"><span data-stu-id="f010c-113">SQLErrorNum32040</span></span>|  
|<span data-ttu-id="f010c-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="f010c-114">Message Text</span></span>|<span data-ttu-id="f010c-115">Die Warnung für 'Älteste, nicht gesendete Transaktion' wurde ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="f010c-115">The alert for 'oldest unsent transaction' has been raised.</span></span> <span data-ttu-id="f010c-116">Der aktuelle Wert von '%d' überschreitet den Threshold '%d'.</span><span class="sxs-lookup"><span data-stu-id="f010c-116">The current value of '%d' surpasses the threshold '%d'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f010c-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="f010c-117">Explanation</span></span>  
 <span data-ttu-id="f010c-118">Dieses Ereignis der Datenbankspiegelung wird für die Prinzipalserverinstanz ausgelöst, um anzugeben, dass das Alter der ältesten, nicht gesendeten Transaktion einen vom Benutzer angegebenen Schwellenwert erreicht hat.</span><span class="sxs-lookup"><span data-stu-id="f010c-118">This database mirroring event is issued on the principal server instance to indicate that the age of the oldest unsent transaction has reached a user-specified threshold value.</span></span> <span data-ttu-id="f010c-119">Normalerweise tritt dieses Ereignis auf, weil sich die Leistung des Systems geändert hat.</span><span class="sxs-lookup"><span data-stu-id="f010c-119">Typically, this event occurs because the performance of the system has changed.</span></span> <span data-ttu-id="f010c-120">Entweder hat sich die Bandbreite zwischen den beiden Systemen reduziert, oder die Last hat sich erhöht.</span><span class="sxs-lookup"><span data-stu-id="f010c-120">Either the bandwidth between the two systems has decreased, or the load has increased.</span></span>  
  
 <span data-ttu-id="f010c-121">Das Alter der ältesten, nicht gesendeten Transaktion stellt eine Leistungsmetrik dar, mit der Sie das Potenzial für Datenverluste einschätzen können, das mit der Anzahl der Minuten der nicht gesendeten Transaktionen gemessen wird.</span><span class="sxs-lookup"><span data-stu-id="f010c-121">The age of the oldest unsent transaction is a performance metric that can help you evaluate the potential for data loss as measured by the number of minutes of unsent transactions.</span></span> <span data-ttu-id="f010c-122">Diese Metrik ist insbesondere für Sitzungen im Modus für hohe Leistung relevant.</span><span class="sxs-lookup"><span data-stu-id="f010c-122">This metric is especially relevant for high-performance mode sessions.</span></span> <span data-ttu-id="f010c-123">Diese Metrik ist jedoch auch für Sitzungen im Modus für hohe Sicherheit relevant, wenn die Spiegelung angehalten oder ausgesetzt wird, weil die Partner getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="f010c-123">However, this metric is also relevant for high-safety mode session when mirroring is paused or suspended because the partners become disconnected.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f010c-124">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="f010c-124">User Action</span></span>  
 <span data-ttu-id="f010c-125">Prüfen Sie die Auslastung für die Instanzen des Prinzipalservers und des Spiegelservers sowie die entsprechenden Netzwerkverbindungen, um die Ursache zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="f010c-125">Check the loads on the principal and mirror server instances and their network connection for the cause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f010c-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f010c-126">See Also</span></span>  
 <span data-ttu-id="f010c-127">[Datenbankspiegelung &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f010c-127">[Database Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="f010c-128">Verwenden von Warnungsschwellenwerten und Warnmeldungen für Spiegelungsleistungsmetriken &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f010c-128">Use Warning Thresholds and Alerts on Mirroring Performance Metrics &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/use-warning-thresholds-and-alerts-on-mirroring-performance-metrics-sql-server.md)  
  
  
