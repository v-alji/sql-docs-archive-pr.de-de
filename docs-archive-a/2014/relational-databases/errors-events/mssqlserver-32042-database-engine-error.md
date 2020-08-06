---
title: MSSQLSERVER_32042 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 32042 (Database Engine error)
ms.assetid: 53a51c7a-dcd4-4c15-b4d2-6aaa9dce76da
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: bd959d84da2c54310dea5156b1a45b73490211a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617074"
---
# <a name="mssqlserver_32042"></a><span data-ttu-id="239b0-102">MSSQLSERVER_32042</span><span class="sxs-lookup"><span data-stu-id="239b0-102">MSSQLSERVER_32042</span></span>
    
## <a name="details"></a><span data-ttu-id="239b0-103">Details</span><span class="sxs-lookup"><span data-stu-id="239b0-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="239b0-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="239b0-104">Product Name</span></span>|<span data-ttu-id="239b0-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="239b0-105">SQL Server</span></span>|  
|<span data-ttu-id="239b0-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="239b0-106">Event ID</span></span>|<span data-ttu-id="239b0-107">32042</span><span class="sxs-lookup"><span data-stu-id="239b0-107">32042</span></span>|  
|<span data-ttu-id="239b0-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="239b0-108">Event Source</span></span>|<span data-ttu-id="239b0-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="239b0-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="239b0-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="239b0-110">Component</span></span>|<span data-ttu-id="239b0-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="239b0-111">SQLEngine</span></span>|  
|<span data-ttu-id="239b0-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="239b0-112">Symbolic Name</span></span>|<span data-ttu-id="239b0-113">SQLErrorNum32042</span><span class="sxs-lookup"><span data-stu-id="239b0-113">SQLErrorNum32042</span></span>|  
|<span data-ttu-id="239b0-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="239b0-114">Message Text</span></span>|<span data-ttu-id="239b0-115">Die Warnung für 'Nicht gesendetes Protokoll' wurde ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="239b0-115">The alert for 'unsent log' has been raised.</span></span> <span data-ttu-id="239b0-116">Der aktuelle Wert von '%d' überschreitet den Threshold '%d'.</span><span class="sxs-lookup"><span data-stu-id="239b0-116">The current value of '%d' surpasses the threshold '%d'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="239b0-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="239b0-117">Explanation</span></span>  
 <span data-ttu-id="239b0-118">Dieses Ereignis der Datenbankspiegelung wird für die Prinzipalserverinstanz ausgelöst, um anzugeben, dass der Umfang des nicht gesendeten Protokolls einen vom Benutzer angegebenen Schwellenwert erreicht hat.</span><span class="sxs-lookup"><span data-stu-id="239b0-118">This database mirroring event is issued on the principal server instance to indicate that the amount of unsent log has reached a user-specified threshold value.</span></span> <span data-ttu-id="239b0-119">Normalerweise tritt dieses Ereignis auf, weil sich die Leistung des Systems geändert hat.</span><span class="sxs-lookup"><span data-stu-id="239b0-119">Typically, this event occurs because the performance of the system has changed.</span></span> <span data-ttu-id="239b0-120">Entweder hat sich die Bandbreite zwischen den beiden Systemen reduziert, oder die Last hat sich erhöht.</span><span class="sxs-lookup"><span data-stu-id="239b0-120">Either the bandwidth between the two systems has decreased, or the load has increased.</span></span>  
  
 <span data-ttu-id="239b0-121">Der Umfang des nicht gesendeten Protokolls ist eine Leistungsmetrik, mit der Sie die Wahrscheinlichkeit eines Datenverlusts im Hinblick auf die Anzahl von Kilobyte (KB) des nicht gesendeten Protokolls ermitteln können.</span><span class="sxs-lookup"><span data-stu-id="239b0-121">The amount of unsent log is a performance metric that can help you evaluate the potential for data loss in terms of the number of kilobytes (KB) of unsent log.</span></span> <span data-ttu-id="239b0-122">Diese Metrik ist insbesondere für Sitzungen im Modus für hohe Leistung relevant.</span><span class="sxs-lookup"><span data-stu-id="239b0-122">This metric is particularly relevant for high-performance mode sessions.</span></span> <span data-ttu-id="239b0-123">Diese Metrik ist jedoch auch für Sitzungen im Modus für hohe Sicherheit relevant, wenn die Spiegelung angehalten oder ausgesetzt wird, weil die Partner getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="239b0-123">However, this metric is also a relevant for high-safety mode session when mirroring is paused or suspended because the partners become disconnected.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="239b0-124">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="239b0-124">User Action</span></span>  
 <span data-ttu-id="239b0-125">Prüfen Sie die Auslastung für die Instanzen des Prinzipalservers und des Spiegelservers sowie die entsprechenden Netzwerkverbindungen, um die Ursache zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="239b0-125">Check the loads on the principal and mirror server instances and their network connection for the cause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="239b0-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="239b0-126">See Also</span></span>  
 <span data-ttu-id="239b0-127">[Datenbankspiegelung &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="239b0-127">[Database Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="239b0-128">Verwenden von Warnungsschwellenwerten und Warnmeldungen für Spiegelungsleistungsmetriken &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="239b0-128">Use Warning Thresholds and Alerts on Mirroring Performance Metrics &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/use-warning-thresholds-and-alerts-on-mirroring-performance-metrics-sql-server.md)  
  
  
