---
title: Veröffentlichungsinformationen, Überwachungs Token (Transaktions Veröffentlichung, SQL Server 2005 und höher) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publicationinfo.tracertokens.f1
ms.assetid: a115ba95-17ae-45df-91bd-5a1a35f3745f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: af84ab9b9122a55367780976056ce95aa597f62a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721301"
---
# <a name="publication-information-tracer-tokens-transactional-publication-sql-server-2005-and-later"></a><span data-ttu-id="18230-102">Veröffentlichungsinformationen, Überwachungstoken (Transaktionsveröffentlichung, SQL Server 2005 und höher)</span><span class="sxs-lookup"><span data-stu-id="18230-102">Publication Information, Tracer Tokens (Transactional Publication, SQL Server 2005 and Later)</span></span>
  <span data-ttu-id="18230-103">Mithilfe der Registerkarte **Überwachungstoken** können Sie Verbindungen überprüfen und die Latenzzeit eines Systems messen, das die Transaktionsreplikation verwendet.</span><span class="sxs-lookup"><span data-stu-id="18230-103">The **Tracer Tokens** tab allows you to validate connections and to measure the latency of a system that uses transactional replication.</span></span> <span data-ttu-id="18230-104">Ein Token (eine geringe Mange an Daten) wird in das Transaktionsprotokoll der Veröffentlichungsdatenbank geschrieben, wie eine normale replizierte Transaktion gekennzeichnet und über das System gesendet. Auf diese Weise werden die folgenden Berechnungen ermöglicht:</span><span class="sxs-lookup"><span data-stu-id="18230-104">A token (a small amount of data) is written to the transaction log of the publication database, marked as though it were a typical replicated transaction, and sent through the system, allowing a calculation of:</span></span>  
  
-   <span data-ttu-id="18230-105">Wie viel Zeit zwischen dem Commit einer Transaktion auf dem Verleger und dem Einfügen des zugehörigen Befehls in die Verteilungsdatenbank auf dem Verteiler verstreicht.</span><span class="sxs-lookup"><span data-stu-id="18230-105">How much time elapses between a transaction being committed at the Publisher and the corresponding command being inserted in the distribution database at the Distributor.</span></span>  
  
-   <span data-ttu-id="18230-106">Wie viel Zeit zwischen dem Einfügen eines Befehls in die Verteilungsdatenbank und dem zugehörigen Commit einer Transaktion auf dem Abonnenten verstreicht.</span><span class="sxs-lookup"><span data-stu-id="18230-106">How much time elapses between a command being inserted in the distribution database and the corresponding transaction being committed at a Subscriber.</span></span>  
  
 <span data-ttu-id="18230-107">Mithilfe dieser Berechnungen können Sie verschiedene Fragen beantworten. Unter anderem diese:</span><span class="sxs-lookup"><span data-stu-id="18230-107">From these calculations, you can answer a number of questions, including:</span></span>  
  
-   <span data-ttu-id="18230-108">Welche Abonnenten benötigen am längsten, um eine Änderung vom Verleger zu empfangen?</span><span class="sxs-lookup"><span data-stu-id="18230-108">Which Subscribers take the longest to receive a change from the Publisher?</span></span>  
  
-   <span data-ttu-id="18230-109">Welcher der Abonnenten, die Überwachungstoken empfangen sollten, hat keine empfangen?</span><span class="sxs-lookup"><span data-stu-id="18230-109">Of the Subscribers expected to receive the tracer token, which, if any, have not received it?</span></span>  
  
## <a name="options"></a><span data-ttu-id="18230-110">Tastatur</span><span class="sxs-lookup"><span data-stu-id="18230-110">Options</span></span>  
 <span data-ttu-id="18230-111">Wenn Sie die Anzeige der Daten im Raster ändern möchten, klicken Sie mit der rechten Maustaste auf das Raster, und klicken Sie anschließend auf eine der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="18230-111">To change the way that the grid displays data, right-click the grid, and then click one of the following options:</span></span>  
  
-   <span data-ttu-id="18230-112">**Sortieren**: Sortieren Sie nach einer oder mehreren Spalten im Dialogfeld **Spalten sortieren** .</span><span class="sxs-lookup"><span data-stu-id="18230-112">**Sort**: Sort on one or more columns in the **Sort Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="18230-113">**Anzuzeigende Spalten auswählen**: Wählen Sie die anzuzeigenden Spalten sowie die Reihenfolge aus, in der diese im Dialogfeld **Spalten auswählen** angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="18230-113">**Choose Columns to Show**: Select which columns to display and the order in which to display them in the **Choose Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="18230-114">**Filtern**: Filtern Sie Zeilen im Raster auf Grundlage der Spaltenwerte im Dialogfeld **Filtereinstellungen** .</span><span class="sxs-lookup"><span data-stu-id="18230-114">**Filter**: Filter rows in the grid based on column values in the **Filter Settings** dialog box.</span></span>  
  
-   <span data-ttu-id="18230-115">**Filter löschen**: Löschen Sie alle Filtereinstellungen für das Raster.</span><span class="sxs-lookup"><span data-stu-id="18230-115">**Clear Filter**: Clear any filter settings for the grid.</span></span>  
  
 <span data-ttu-id="18230-116">Filtereinstellungen sind rasterspezifisch.</span><span class="sxs-lookup"><span data-stu-id="18230-116">Filter settings are specific to each grid.</span></span> <span data-ttu-id="18230-117">Die Spaltenauswahl und -sortierung wird auf alle Raster desselben Typs angewendet, z. B. das Veröffentlichungsraster für jeden Verleger.</span><span class="sxs-lookup"><span data-stu-id="18230-117">Column selection and sorting are applied to all grids of the same type, such as the publications grid for each Publisher.</span></span>  
  
 <span data-ttu-id="18230-118">**Überwachung einfügen**</span><span class="sxs-lookup"><span data-stu-id="18230-118">**Insert Tracer**</span></span>  
 <span data-ttu-id="18230-119">Klicken Sie auf diese Option, um ein Überwachungstoken in das Transaktionsprotokoll auf dem Verleger einzufügen.</span><span class="sxs-lookup"><span data-stu-id="18230-119">Click to insert a tracer token in the transaction log at the Publisher.</span></span>  
  
 <span data-ttu-id="18230-120">**Einfügungszeitpunkt**</span><span class="sxs-lookup"><span data-stu-id="18230-120">**Time inserted**</span></span>  
 <span data-ttu-id="18230-121">Wählen Sie einen Zeitpunkt aus, zu dem ein Überwachungstoken eingefügt wurde, um die Latenzzeitinformationen für diesen Zeitpunkt anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="18230-121">Select a time at which a tracer token was inserted to display latency information from that time.</span></span> <span data-ttu-id="18230-122">Standardmäßig werden Informationen zum aktuellsten Zeitpunkt angezeigt.</span><span class="sxs-lookup"><span data-stu-id="18230-122">By default, information from the most recent time is displayed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="18230-123">Die Informationen von Überwachungstoken werden für denselben Zeitraum wie andere Vergangenheitsdaten beibehalten. Der Zeitraum wird durch die Aufbewahrungsdauer für den Verlauf der Verteilungsdatenbank festgelegt.</span><span class="sxs-lookup"><span data-stu-id="18230-123">Tracer token information is retained for the same time period as other historical data, which is governed by the history retention period of the distribution database.</span></span> <span data-ttu-id="18230-124">Weitere Informationen zum Ändern der Eigenschaften der Verteilungsdatenbank finden Sie unter [Anzeigen und Ändern der Verteiler- und Verlegereigenschaften](view-and-modify-distributor-and-publisher-properties.md).</span><span class="sxs-lookup"><span data-stu-id="18230-124">For information about changing distribution database properties, see [View and Modify Distributor and Publisher Properties](view-and-modify-distributor-and-publisher-properties.md).</span></span>  
  
 <span data-ttu-id="18230-125">**Abonnement**</span><span class="sxs-lookup"><span data-stu-id="18230-125">**Subscription**</span></span>  
 <span data-ttu-id="18230-126">Der Name jedes Abonnements für die Veröffentlichung.</span><span class="sxs-lookup"><span data-stu-id="18230-126">The name of each subscription to the publication.</span></span>  
  
 <span data-ttu-id="18230-127">**Verleger zu Verteiler**</span><span class="sxs-lookup"><span data-stu-id="18230-127">**Publisher to Distributor**</span></span>  
 <span data-ttu-id="18230-128">Die verstrichene Zeit zwischen dem Commit einer Transaktion auf dem Verleger und dem Einfügen des zugehörigen Befehls in die Verteilungsdatenbank auf dem Verteiler.</span><span class="sxs-lookup"><span data-stu-id="18230-128">The elapsed time between a transaction being committed at the Publisher and the corresponding command being inserted in the distribution database at the Distributor.</span></span> <span data-ttu-id="18230-129">Der Wert **Ausstehend** zeigt an, dass der Token noch nicht beim Verteiler angekommen ist.</span><span class="sxs-lookup"><span data-stu-id="18230-129">A value of **Pending** indicates that the token has not yet reached the Distributor.</span></span> <span data-ttu-id="18230-130">Überprüfen Sie, ob der Protokolllese-Agent ausgeführt wird, wenn der Status Ausstehend fortdauert.</span><span class="sxs-lookup"><span data-stu-id="18230-130">If the pending state persists, ensure that the Log Reader Agent is running.</span></span>  
  
 <span data-ttu-id="18230-131">**Verteiler zu Abonnent**</span><span class="sxs-lookup"><span data-stu-id="18230-131">**Distributor to Subscriber**</span></span>  
 <span data-ttu-id="18230-132">Die verstrichene Zeit zwischen dem Einfügen eines Befehls in die Verteilungsdatenbank und dem zugehörigen Commit einer Transaktion auf dem Abonnenten.</span><span class="sxs-lookup"><span data-stu-id="18230-132">The elapsed time between a command being inserted in the distribution database and the corresponding transaction being committed at a Subscriber.</span></span> <span data-ttu-id="18230-133">Der Wert **Ausstehend** zeigt an, dass der Token noch nicht beim Abonnenten angekommen ist.</span><span class="sxs-lookup"><span data-stu-id="18230-133">A value of **Pending** indicates that the token has not yet reached the Subscriber.</span></span> <span data-ttu-id="18230-134">Überprüfen Sie, ob der Verteilungs-Agent ausgeführt wird, wenn der Status Ausstehend fortdauert.</span><span class="sxs-lookup"><span data-stu-id="18230-134">If the pending state persists, ensure that the Distribution Agent is running.</span></span>  
  
 <span data-ttu-id="18230-135">**Gesamtlatenz**</span><span class="sxs-lookup"><span data-stu-id="18230-135">**Total Latency**</span></span>  
 <span data-ttu-id="18230-136">Die verstrichene Zeit zwischen dem Commit für eine Transaktion auf dem Verleger und dem zugehörigen Commit für die Transaktion auf dem Abonnenten.</span><span class="sxs-lookup"><span data-stu-id="18230-136">The elapsed time between a transaction being committed at the Publisher and the corresponding transaction being committed at the Subscriber.</span></span> <span data-ttu-id="18230-137">Dieser Zeitraum stellt die End-to-End-Latenzzeit des Replikationssystems für diesen Abonnenten zu diesem Zeitpunkt dar.</span><span class="sxs-lookup"><span data-stu-id="18230-137">This represents the end-to-end latency of the replication system for this Subscriber at this time.</span></span> <span data-ttu-id="18230-138">Der Wert **Ausstehend** zeigt an, dass der Token noch nicht beim Abonnenten angekommen ist.</span><span class="sxs-lookup"><span data-stu-id="18230-138">A value of **Pending** indicates that the token has not yet reached the Subscriber.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18230-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="18230-139">See Also</span></span>  
 <span data-ttu-id="18230-140">[Starten und Beenden eines Replikations-Agents &#40;SQL Server Management Studio&#41;](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="18230-140">[Start and Stop a Replication Agent &#40;SQL Server Management Studio&#41;](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) </span></span>  
 <span data-ttu-id="18230-141">[Starten des Replikations Monitors](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="18230-141">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="18230-142">[Messen der Latenzzeit und Überprüfen der Verbindungen für die Transaktions Replikation](monitor/measure-latency-and-validate-connections-for-transactional-replication.md) </span><span class="sxs-lookup"><span data-stu-id="18230-142">[Measure Latency and Validate Connections for Transactional Replication](monitor/measure-latency-and-validate-connections-for-transactional-replication.md) </span></span>  
 <span data-ttu-id="18230-143">[Leistungsüberwachung mit dem Replikations Monitor](monitor/monitor-performance-with-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="18230-143">[Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md) </span></span>  
 <span data-ttu-id="18230-144">[Überwachen der Replikation](monitoring-replication.md) </span><span class="sxs-lookup"><span data-stu-id="18230-144">[Monitoring Replication](monitoring-replication.md) </span></span>  
 [<span data-ttu-id="18230-145">Übersicht über Replikations-Agents</span><span class="sxs-lookup"><span data-stu-id="18230-145">Replication Agents Overview</span></span>](agents/replication-agents-overview.md)  
  
  
