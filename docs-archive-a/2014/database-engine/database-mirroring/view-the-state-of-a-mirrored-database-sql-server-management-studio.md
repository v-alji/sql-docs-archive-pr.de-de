---
title: Anzeigen des Status einer gespiegelten Datenbank (SQL Server Management Studio) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- states [SQL Server], database mirroring
- database mirroring [SQL Server], states
ms.assetid: 544f4194-253e-4c57-96ca-31c16301434f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: fc691e8b746a816ab88448e3399aebad6d8844e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616674"
---
# <a name="view-the-state-of-a-mirrored-database-sql-server-management-studio"></a><span data-ttu-id="0b201-102">Anzeigen des Status einer gespiegelten Datenbank (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="0b201-102">View the State of a Mirrored Database (SQL Server Management Studio)</span></span>
  <span data-ttu-id="0b201-103">Während einer Datenbank-Spiegelungssitzung können Sie im Dialogfeld **Datenbankeigenschaften** auf der Seite **Wird gespiegelt** den Status anzeigen.</span><span class="sxs-lookup"><span data-stu-id="0b201-103">During a database mirroring session, you can view the status on the **Mirroring** page of the **Database Properties** dialog box.</span></span>  
  
### <a name="to-view-the-status-of-a-database-mirroring-session"></a><span data-ttu-id="0b201-104">So zeigen Sie den Status der Datenbank-Spiegelungssitzung an</span><span class="sxs-lookup"><span data-stu-id="0b201-104">To view the status of a database mirroring session</span></span>  
  
1.  <span data-ttu-id="0b201-105">Nachdem Sie eine Verbindung mit der Prinzipalserverinstanz hergestellt haben, klicken Sie im Objekt-Explorer auf den Servernamen, um die Serverstruktur zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="0b201-105">After connecting to the principal server instance, in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="0b201-106">Erweitern Sie **Datenbanken**, und wählen Sie die zu spiegelnde Datenbank aus.</span><span class="sxs-lookup"><span data-stu-id="0b201-106">Expand **Databases**, and select the database to be mirrored.</span></span>  
  
3.  <span data-ttu-id="0b201-107">Klicken Sie mit der rechten Maustaste auf die Datenbank, wählen Sie **Tasks**aus, und klicken Sie dann auf **Spiegeln**.</span><span class="sxs-lookup"><span data-stu-id="0b201-107">Right-click the database, select **Tasks**, and then click **Mirror**.</span></span> <span data-ttu-id="0b201-108">Dadurch wird die Seite **Spiegelung** im Dialogfeld **Datenbankeigenschaften** geöffnet.</span><span class="sxs-lookup"><span data-stu-id="0b201-108">This opens the **Mirroring** page of the **Database Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="0b201-109">Nach Beginn der Spiegelung wird im Fensterbereich **Status** der Status der Datenbank-Spiegelungssitzung angezeigt, und zwar ab dem Zeitpunkt, an dem Sie die Seite **Wird gespiegelt** ausgewählt oder auf die Schaltfläche **Aktualisieren** geklickt haben.</span><span class="sxs-lookup"><span data-stu-id="0b201-109">After mirroring begins, the **Status** panel displays the status of the database mirroring session as of when you selected the **Mirroring** page or clicked the **Refresh** button.</span></span> <span data-ttu-id="0b201-110">Folgende Werte sind für den Status möglich:</span><span class="sxs-lookup"><span data-stu-id="0b201-110">The possible states are as follows:</span></span>  
  
    |<span data-ttu-id="0b201-111">Zustände</span><span class="sxs-lookup"><span data-stu-id="0b201-111">States</span></span>|<span data-ttu-id="0b201-112">Erklärung</span><span class="sxs-lookup"><span data-stu-id="0b201-112">Explanation</span></span>|  
    |------------|-----------------|  
    |\<blank>|<span data-ttu-id="0b201-113">Es ist keine Datenbank-Spiegelungssitzung vorhanden und keine Aktivität auf der Seite **Spiegelung** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="0b201-113">No database mirroring session exists and there is no activity to report on the **Mirroring** page.</span></span>|  
    |<span data-ttu-id="0b201-114">Angehalten</span><span class="sxs-lookup"><span data-stu-id="0b201-114">Paused</span></span>|<span data-ttu-id="0b201-115">Die Prinzipaldatenbank wird ausgeführt, sendet jedoch keine Protokolle an den Spiegelserver.</span><span class="sxs-lookup"><span data-stu-id="0b201-115">The principal database is running but is not sending any logs to the mirror server.</span></span> <span data-ttu-id="0b201-116">Die Spiegelkopie der Datenbank ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0b201-116">The mirror copy of the database is not available.</span></span>|  
    |<span data-ttu-id="0b201-117">Keine Verbindung</span><span class="sxs-lookup"><span data-stu-id="0b201-117">No connection</span></span>|<span data-ttu-id="0b201-118">Die Prinzipalserverinstanz kann keine Verbindung mit dem Partner oder mit der Zeugenserverinstanz herstellen (soweit vorhanden).</span><span class="sxs-lookup"><span data-stu-id="0b201-118">The principal server instance cannot connect to its partner or to the witness server instance (if any)</span></span>|  
    |<span data-ttu-id="0b201-119">Wird synchronisiert</span><span class="sxs-lookup"><span data-stu-id="0b201-119">Synchronizing</span></span>|<span data-ttu-id="0b201-120">Der Inhalt der Spiegeldatenbank liegt zeitlich hinter dem Inhalt der Prinzipaldatenbank.</span><span class="sxs-lookup"><span data-stu-id="0b201-120">The contents of the mirror database are lagging behind the contents of the principal database.</span></span> <span data-ttu-id="0b201-121">Die Prinzipalserverinstanz sendet Protokolldatensätze an die Spiegelserverinstanz, die die Änderungen auf die Spiegeldatenbank anwendet, um ein Rollforward dafür auszuführen.</span><span class="sxs-lookup"><span data-stu-id="0b201-121">The principal server instance is sending log records to the mirror server instance, which is applying the changes to the mirror database to roll it forward.</span></span><br /><br /> <span data-ttu-id="0b201-122">Zu Beginn einer Datenbank-Spiegelungssitzung weisen die Spiegel- und Prinzipaldatenbanken den Wird synchronisiert-Status auf.</span><span class="sxs-lookup"><span data-stu-id="0b201-122">At the start of a database mirroring session, the mirror and principal databases are in the synchronizing state.</span></span>|  
    |<span data-ttu-id="0b201-123">Failover</span><span class="sxs-lookup"><span data-stu-id="0b201-123">Failover</span></span>|<span data-ttu-id="0b201-124">In der Prinzipalserverinstanz wurde ein manuelles Failover (Rollentausch) gestartet, aber noch nicht von der Spiegeldatenbank akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="0b201-124">On the principal server instance, a manual failover (role swap) has begun but has not yet accepted by the mirror.</span></span>|  
    |<span data-ttu-id="0b201-125">Synchronisiert</span><span class="sxs-lookup"><span data-stu-id="0b201-125">Synchronized</span></span>|<span data-ttu-id="0b201-126">Die Spiegeldatenbank enthält die gleichen Daten wie die Prinzipaldatenbank.</span><span class="sxs-lookup"><span data-stu-id="0b201-126">The mirror database contains the same data as the principal database.</span></span> <span data-ttu-id="0b201-127">Manuelles und automatisches Failover sind *nur* im Synchronisiert-Status möglich.</span><span class="sxs-lookup"><span data-stu-id="0b201-127">Manual and automatic failover are possible *only* in the synchronized state.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0b201-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0b201-128">See Also</span></span>  
 [<span data-ttu-id="0b201-129">Spiegelungsstatus &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0b201-129">Mirroring States &#40;SQL Server&#41;</span></span>](mirroring-states-sql-server.md)  
  
  
