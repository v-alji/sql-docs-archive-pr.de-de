---
title: MSSQLSERVER_32044 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 32044 (Database Engine error)
ms.assetid: f2d073be-d9a1-4837-8a38-028d3e3403bd
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 27d9655c3a908f1302f048c6f68159d4f610367a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617073"
---
# <a name="mssqlserver_32044"></a><span data-ttu-id="657a3-102">MSSQLSERVER_32044</span><span class="sxs-lookup"><span data-stu-id="657a3-102">MSSQLSERVER_32044</span></span>
    
## <a name="details"></a><span data-ttu-id="657a3-103">Details</span><span class="sxs-lookup"><span data-stu-id="657a3-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="657a3-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="657a3-104">Product Name</span></span>|<span data-ttu-id="657a3-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="657a3-105">SQL Server</span></span>|  
|<span data-ttu-id="657a3-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="657a3-106">Event ID</span></span>|<span data-ttu-id="657a3-107">32044</span><span class="sxs-lookup"><span data-stu-id="657a3-107">32044</span></span>|  
|<span data-ttu-id="657a3-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="657a3-108">Event Source</span></span>|<span data-ttu-id="657a3-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="657a3-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="657a3-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="657a3-110">Component</span></span>|<span data-ttu-id="657a3-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="657a3-111">SQLEngine</span></span>|  
|<span data-ttu-id="657a3-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="657a3-112">Symbolic Name</span></span>|<span data-ttu-id="657a3-113">SQLErrorNum32044</span><span class="sxs-lookup"><span data-stu-id="657a3-113">SQLErrorNum32044</span></span>|  
|<span data-ttu-id="657a3-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="657a3-114">Message Text</span></span>|<span data-ttu-id="657a3-115">Die Warnung für 'Spiegelungscommitaufwand' wurde ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="657a3-115">The alert for 'mirror commit overhead' has been raised.</span></span> <span data-ttu-id="657a3-116">Der aktuelle Wert von '%d' überschreitet den Threshold '%d'.</span><span class="sxs-lookup"><span data-stu-id="657a3-116">The current value of '%d' surpasses the threshold '%d'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="657a3-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="657a3-117">Explanation</span></span>  
 <span data-ttu-id="657a3-118">Dieses Datenbankspiegelungsereignis wird auf der Prinzipalserverinstanz ausgegeben. Damit soll angegeben werden, dass aufgrund der Datenbankspiegelung mit der gesamten Wartezeit für den Commit ein vom Benutzer angegebener Schwellenwert erreicht oder überschritten wurde.</span><span class="sxs-lookup"><span data-stu-id="657a3-118">This database mirroring event is issued on the principal server instance to indicate that the aggregate commit wait time reached or exceeded a user-specified threshold value because of database mirroring.</span></span> <span data-ttu-id="657a3-119">Die Wartezeit ist das Produkt der Anzahl von Transaktionen und der jeweiligen Dauer.</span><span class="sxs-lookup"><span data-stu-id="657a3-119">The wait time is the product of the number of transactions and the time of each.</span></span> <span data-ttu-id="657a3-120">In den beiden folgenden Fällen werden z. B. jeweils 1000 Millisekunden Wartezeit erzeugt: 1000 Transaktionen \* 1 Millisekunde und 1 Transaktion \* 1000 Millisekunden.</span><span class="sxs-lookup"><span data-stu-id="657a3-120">For example, the following cases both produce 1000 milliseconds of wait time: 1000 transactions \* 1 millisecond, and 1 transaction \* 1000 milliseconds.</span></span> <span data-ttu-id="657a3-121">Eine erhöhte Commitwartezeit kann durch einen starken Anstieg der Anzahl von Transaktionen, durch Verzögerungen beim Senden des Protokolls oder Verzögerungen beim Leeren des Protokolls auf der Spiegelserverinstanz verursacht werden.</span><span class="sxs-lookup"><span data-stu-id="657a3-121">An increased commit wait time can be caused by a surge in the transaction count, delays in sending the log, or delays in flushing the log on the mirror server instance.</span></span>  
  
 <span data-ttu-id="657a3-122">Der Spiegelungscommitaufwand ist eine Leistungsmetrik, mit der Sie die aktuelle Leistungsauswirkung des synchronen Vorgangs beurteilen können.</span><span class="sxs-lookup"><span data-stu-id="657a3-122">The amount of mirror commit overhead is a performance metric that can help you evaluate the current performance impact of synchronous operation.</span></span> <span data-ttu-id="657a3-123">Diese Metrik ist nur im Modus für hohe Sicherheit relevant.</span><span class="sxs-lookup"><span data-stu-id="657a3-123">This metric is relevant only in high-safety mode.</span></span> <span data-ttu-id="657a3-124">Da der Modus für hohe Sicherheit synchron ausgeführt wird, wartet die Prinzipalserverinstanz darauf, einen Commit für die Transaktion auszuführen, nachdem ein Protokolldatensatz an die Spiegelserverinstanz gesendet wurde, bis eine Bestätigung darüber eingeht, dass der Protokolldatensatz von der Spiegelserverinstanz auf einen Datenträger geschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="657a3-124">Because high-safety mode is synchronous, the principal server instance waits to commit the transaction after it sends a log record to the mirror server instance until it receives confirmation that the mirror server instance has written the log record to disk.</span></span> <span data-ttu-id="657a3-125">Der Protokolldatensatz verbleibt auf dem Datenträger der Spiegelserverinstanz, solange auf die Wiederherstellung in der Spiegeldatenbank gewartet wird.</span><span class="sxs-lookup"><span data-stu-id="657a3-125">The log record remains on disk on the mirror server instance while it waits to be restored to the mirror database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="657a3-126">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="657a3-126">User Action</span></span>  
 <span data-ttu-id="657a3-127">Prüfen Sie die Auslastung für die Instanzen des Prinzipalservers und des Spiegelservers sowie die entsprechenden Netzwerkverbindungen, um die Ursache zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="657a3-127">Check the loads on the principal and mirror server instances and their network connection for the cause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="657a3-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="657a3-128">See Also</span></span>  
 <span data-ttu-id="657a3-129">[Datenbankspiegelung &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="657a3-129">[Database Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="657a3-130">Verwenden von Warnungsschwellenwerten und Warnmeldungen für Spiegelungsleistungsmetriken &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="657a3-130">Use Warning Thresholds and Alerts on Mirroring Performance Metrics &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/use-warning-thresholds-and-alerts-on-mirroring-performance-metrics-sql-server.md)  
  
  
