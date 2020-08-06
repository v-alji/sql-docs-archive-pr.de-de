---
title: Festlegen von Schwellenwerten und Warnungen im Replikationsmonitor | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- alerts [SQL Server replication]
- Merge Agent, thresholds and warnings
- Distribution Agent, thresholds and warnings
- thresholds [SQL Server replication]
- Replication Monitor, thresholds and warnings
- monitoring performance [SQL Server replication], thresholds and warnings
ms.assetid: 3a409c2c-b77e-4001-b81a-1dcd918618ec
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f34878a6398df34e55e6dd3783f2da736bee0959
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725509"
---
# <a name="set-thresholds-and-warnings-in-replication-monitor"></a><span data-ttu-id="584cb-102">Festlegen von Schwellenwerten und Warnungen im Replikationsmonitor</span><span class="sxs-lookup"><span data-stu-id="584cb-102">Set Thresholds and Warnings in Replication Monitor</span></span>
  <span data-ttu-id="584cb-103">Im Replikationsmonitor von [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] werden Statusinformationen für Veröffentlichungen und Abonnements angezeigt.</span><span class="sxs-lookup"><span data-stu-id="584cb-103">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Replication Monitor displays status information for publications and subscriptions.</span></span> <span data-ttu-id="584cb-104">Standardmäßig zeigt der Replikationsmonitor Warnungen nur für nicht initialisierte Abonnements an. Sie können Warnungen jedoch auch für andere Bedingungen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="584cb-104">By default, Replication Monitor displays warnings only for uninitialized subscriptions, but you can enable warnings for other conditions.</span></span> <span data-ttu-id="584cb-105">Sie sollten Warnungen für Ihre Topologie aktivieren, damit Sie rechtzeitig über Status und Leistung informiert werden.</span><span class="sxs-lookup"><span data-stu-id="584cb-105">It is recommended that you enable warnings for your topology, so that you are informed about status and performance in a timely manner.</span></span>  
  
 <span data-ttu-id="584cb-106">Beim Aktivieren einer Warnung geben Sie einen Schwellenwert an.</span><span class="sxs-lookup"><span data-stu-id="584cb-106">When you enable a warning, you specify a threshold.</span></span> <span data-ttu-id="584cb-107">Wenn dieser Schwellenwert erreicht oder überschritten wird, wird eine Warnung angezeigt (außer es muss ein Problem mit höherer Priorität angezeigt werden).</span><span class="sxs-lookup"><span data-stu-id="584cb-107">When that threshold is met or exceeded, a warning is displayed (unless an issue with a higher priority needs to be displayed).</span></span> <span data-ttu-id="584cb-108">Neben der Warnung im Replikationsmonitor kann bei Erreichen eines Schwellenwerts auch ein Warnhinweis ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="584cb-108">In addition to displaying a warning in Replication Monitor, reaching a threshold can also trigger an alert.</span></span> <span data-ttu-id="584cb-109">Sie können Warnungen für folgende Bedingungen aktivieren:</span><span class="sxs-lookup"><span data-stu-id="584cb-109">You can enable warnings for the following conditions:</span></span>  
  
-   <span data-ttu-id="584cb-110">Bevorstehender Abonnementablauf</span><span class="sxs-lookup"><span data-stu-id="584cb-110">Imminent subscription expiration</span></span>  
  
     <span data-ttu-id="584cb-111">Dieser Statuswert gilt für alle Arten der Replikation.</span><span class="sxs-lookup"><span data-stu-id="584cb-111">This applies to all types of replication.</span></span> <span data-ttu-id="584cb-112">Wenn der angegebene Schwellenwert erreicht oder überschritten wird, wird der Abonnementstatus als **Läuft demnächst ab/Abgelaufen**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="584cb-112">If the specified threshold is met or exceeded, the subscription status is displayed as **Expiring soon/Expired**.</span></span>  
  
-   <span data-ttu-id="584cb-113">Die angegebene Latenzzeit (Zeit, die zwischen dem Start einer Transaktion auf dem Verleger und dem Start der entsprechenden Transaktion auf dem Abonnenten vergeht) wird überschritten.</span><span class="sxs-lookup"><span data-stu-id="584cb-113">Exceeding the specified latency (the amount of time that elapses between a transaction being committed at the Publisher and the corresponding transaction being committed at the Subscriber).</span></span>  
  
     <span data-ttu-id="584cb-114">Betrifft nur Transaktionsreplikationen.</span><span class="sxs-lookup"><span data-stu-id="584cb-114">This applies to transactional replication.</span></span> <span data-ttu-id="584cb-115">Falls der angegebene Schwellenwert erreicht oder überschritten wird, wird der Abonnementstatus als **Leistungskritisch**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="584cb-115">If the specified threshold is met or exceeded, the subscription status is displayed as **Performance critical**.</span></span>  
  
-   <span data-ttu-id="584cb-116">Die angegebene Synchronisierungszeit wird überschritten.</span><span class="sxs-lookup"><span data-stu-id="584cb-116">Exceeding the specified synchronization time.</span></span>  
  
     <span data-ttu-id="584cb-117">Betrifft nur Mergereplikationen.</span><span class="sxs-lookup"><span data-stu-id="584cb-117">This applies to merge replication.</span></span> <span data-ttu-id="584cb-118">Wenn der angegebene Schwellenwert erreicht oder überschritten wird, wird als Status **Langer Mergevorgang**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="584cb-118">If the specified threshold is met or exceeded, the status is displayed as **Long-running merge**.</span></span> <span data-ttu-id="584cb-119">Sie können verschiedene Schwellenwerte für DFÜ- und Local Area Network-(LAN-)Verbindungen angeben.</span><span class="sxs-lookup"><span data-stu-id="584cb-119">You can specify different thresholds for dialup and Local Area Network (LAN) connections.</span></span>  
  
-   <span data-ttu-id="584cb-120">Die angegebene Zahl von Zeilen konnte nicht innerhalb der festgelegten Zeit verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="584cb-120">Falling short of processing the specified number of rows in a given amount of time.</span></span>  
  
     <span data-ttu-id="584cb-121">Betrifft nur Mergereplikationen.</span><span class="sxs-lookup"><span data-stu-id="584cb-121">This applies to merge replication.</span></span> <span data-ttu-id="584cb-122">Wenn der angegebene Schwellenwert erreicht oder überschritten wird, wird als Status **Leistungskritisch**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="584cb-122">If the specified threshold is met or exceeded, the status is displayed as **Performance critical**.</span></span> <span data-ttu-id="584cb-123">Sie können verschiedene Schwellenwerte für DFÜ- und LAN-Verbindungen angeben.</span><span class="sxs-lookup"><span data-stu-id="584cb-123">You can specify different thresholds for dialup and LAN connections.</span></span>  
  
 <span data-ttu-id="584cb-124">Weitere Informationen zu den Warnungen **Leistungskritisch** und **langer Mergevorgang**, finden Sie unter [Überwachen der Leistung mit dem Replikationsmonitor](monitor-performance-with-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="584cb-124">For more information on the warnings **Performance critical** and **Long-running merge**, see [Monitor Performance with Replication Monitor](monitor-performance-with-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="584cb-125">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="584cb-125">**In This Topic**</span></span>  
  
-   [<span data-ttu-id="584cb-126">Festlegen der Schwellenwerte und Warnungen für eine Transaktionsveröffentlichung</span><span class="sxs-lookup"><span data-stu-id="584cb-126">Set thresholds and warnings for a transactional publication</span></span>](#Transactional)  
  
-   [<span data-ttu-id="584cb-127">Festlegen der Schwellenwerte und Warnungen für eine Mergeveröffentlichung</span><span class="sxs-lookup"><span data-stu-id="584cb-127">Set thresholds and warnings for a merge publication</span></span>](#Merge)  
  
-   [<span data-ttu-id="584cb-128">Festlegen der Schwellenwerte und Warnungen für eine Momentaufnahmeveröffentlichung</span><span class="sxs-lookup"><span data-stu-id="584cb-128">Set thresholds and warnings for a snapshot publication</span></span>](#Snapshot)  
  
##  <a name="to-set-thresholds-and-warnings-for-a-transactional-publication"></a><a name="Transactional"></a> <span data-ttu-id="584cb-129">So legen Sie die Schwellenwerte und Warnungen für eine Transaktionsveröffentlichung fest</span><span class="sxs-lookup"><span data-stu-id="584cb-129">To set thresholds and warnings for a transactional publication</span></span>  
  
1.  <span data-ttu-id="584cb-130">Erweitern Sie im linken Bereich eine Verlegergruppe, erweitern Sie einen Verleger, und klicken Sie dann auf eine Veröffentlichung.</span><span class="sxs-lookup"><span data-stu-id="584cb-130">Expand a Publisher group in the left pane, expand a Publisher, and then click a publication.</span></span>  
  
2.  <span data-ttu-id="584cb-131">Klicken Sie auf die Registerkarte **Warnungen** . Wenn Sie weitere Informationen zu den Optionen auf dieser Registerkarte benötigen, klicken Sie auf der Menüleiste auf **Hilfe** .</span><span class="sxs-lookup"><span data-stu-id="584cb-131">Click the **Warnings** tab. To view more information about the options on this tab click **Help** on the menu bar.</span></span>  
  
3.  <span data-ttu-id="584cb-132">Aktivieren Sie eine Warnung, indem Sie das entsprechende Kontrollkästchen aktivieren: **Warnung, wenn ein Abonnement innerhalb des Schwellenwerts abläuft** oder **Warnung, wenn die Latenzzeit den Schwellenwert überschreitet**.</span><span class="sxs-lookup"><span data-stu-id="584cb-132">Enable a warning by selecting the appropriate check box: **Warn if a subscription will expire within the threshold** or **Warn if latency exceeds the threshold**.</span></span>  
  
4.  <span data-ttu-id="584cb-133">Legen Sie in der **Schwellenwert** -Spalte einen Schwellenwert für die Warnungen fest.</span><span class="sxs-lookup"><span data-stu-id="584cb-133">Set a threshold for the warnings in the **Threshold** column.</span></span> <span data-ttu-id="584cb-134">Wenn Sie z. B. unter Schritt 3 die Option **Warnung, wenn die Latenzzeit den Schwellenwert überschreitet** ausgewählt haben, können Sie in der **Schwellenwert** -Spalte eine Latenzzeit von **60 Sekunden** angeben.</span><span class="sxs-lookup"><span data-stu-id="584cb-134">For example, if you selected **Warn if latency exceeds the threshold** in step 3, you could select a latency of **60 seconds** in the **Threshold** column.</span></span>  
  
5.  <span data-ttu-id="584cb-135">Klicken Sie auf **Änderungen speichern**.</span><span class="sxs-lookup"><span data-stu-id="584cb-135">Click **Save Changes**.</span></span>  
  
#### <a name="to-configure-an-alert-for-a-threshold"></a><span data-ttu-id="584cb-136">So konfigurieren Sie eine Warnung für einen Schwellenwert</span><span class="sxs-lookup"><span data-stu-id="584cb-136">To configure an alert for a threshold</span></span>  
  
1.  <span data-ttu-id="584cb-137">Klicken Sie auf **Warnungen konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="584cb-137">Click **Configure Alerts**.</span></span>  
  
2.  <span data-ttu-id="584cb-138">Wählen Sie im Dialogfeld **Replikationswarnungen konfigurieren** eine Warnung aus, und klicken Sie dann auf **Konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="584cb-138">In the **Configure Replication Alerts** dialog box, select an alert, and then click **Configure**.</span></span>  
  
     <span data-ttu-id="584cb-139">In diesem Dialogfeld werden Warnungen für alle Veröffentlichungstypen angezeigt – auch für Warnungen, die nichts mit den Überwachungsschwellenwerten zu tun haben.</span><span class="sxs-lookup"><span data-stu-id="584cb-139">This dialog box displays alerts for all publication types, including alerts that are not related to monitoring thresholds.</span></span> <span data-ttu-id="584cb-140">Weitere Informationen finden Sie unter [Verwenden von Warnungen für Replikations-Agentereignisse](../agents/use-alerts-for-replication-agent-events.md).</span><span class="sxs-lookup"><span data-stu-id="584cb-140">For more information, see [Use Alerts for Replication Agent Events](../agents/use-alerts-for-replication-agent-events.md).</span></span>  
  
3.  <span data-ttu-id="584cb-141">Legen Sie im Dialogfeld **Eigenschaften von Warnung "\<AlertName>"** die gewünschten Optionen fest:</span><span class="sxs-lookup"><span data-stu-id="584cb-141">Set options in the **\<AlertName> alert properties** dialog box:</span></span>  
  
    -   <span data-ttu-id="584cb-142">Klicken Sie auf der Seite **Allgemein** auf **Aktivieren**, und geben Sie an, für welche Datenbank die Warnung gelten soll.</span><span class="sxs-lookup"><span data-stu-id="584cb-142">On the **General** page, click **Enable**; specify which database the alert should apply to.</span></span>  
  
    -   <span data-ttu-id="584cb-143">Geben Sie auf der Seite **Antwort** an, ob eine E-Mail gesendet und/oder ein Auftrag ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="584cb-143">On the **Response** page, specify whether an e-mail should be sent and/or a job should be executed.</span></span>  
  
    -   <span data-ttu-id="584cb-144">Passen Sie auf der Seite **Optionen** den Text der Antwort an.</span><span class="sxs-lookup"><span data-stu-id="584cb-144">On the **Options** page, customize the text of the response.</span></span>  
  
4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="584cb-145">Klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="584cb-145">Click **Close**.</span></span>  
  
##  <a name="set-thresholds-and-warnings-for-a-merge-publication"></a><a name="Merge"></a> <span data-ttu-id="584cb-146">Festlegen der Schwellenwerte und Warnungen für eine Mergeveröffentlichung</span><span class="sxs-lookup"><span data-stu-id="584cb-146">Set thresholds and warnings for a merge publication</span></span>  
  
1.  <span data-ttu-id="584cb-147">Erweitern Sie im linken Bereich eine Verlegergruppe, erweitern Sie einen Verleger, und klicken Sie dann auf eine Veröffentlichung.</span><span class="sxs-lookup"><span data-stu-id="584cb-147">Expand a Publisher group in the left pane, expand a Publisher, and then click a publication.</span></span>  
  
2.  <span data-ttu-id="584cb-148">Klicken Sie auf die Registerkarte **Warnungen** . Wenn Sie weitere Informationen zu den Optionen dieser Registerkarte erhalten möchten, klicken Sie auf der Menüleiste auf **Hilfe** .</span><span class="sxs-lookup"><span data-stu-id="584cb-148">Click the **Warnings** tab. To view more information about the options on this tab, click **Help** on the menu bar.</span></span>  
  
3.  <span data-ttu-id="584cb-149">Aktivieren Sie eine Warnung, indem Sie das entsprechende Kontrollkästchen aktivieren:</span><span class="sxs-lookup"><span data-stu-id="584cb-149">Enable a warning by selecting the appropriate check box:</span></span>  
  
    -   <span data-ttu-id="584cb-150">**Warnung, wenn ein Abonnement innerhalb des Schwellenwerts abläuft**</span><span class="sxs-lookup"><span data-stu-id="584cb-150">**Warn if a subscription will expire within the threshold**</span></span>  
  
    -   <span data-ttu-id="584cb-151">**Warnung, wenn eine Zusammenführungslänge für DFÜ-Verbindungen den Schwellenwert überschreitet**</span><span class="sxs-lookup"><span data-stu-id="584cb-151">**Warn if a merge length for dialup connections exceeds the threshold**</span></span>  
  
    -   <span data-ttu-id="584cb-152">**Warnung, wenn eine Zusammenführungslänge für LAN-Verbindungen den Schwellenwert überschreitet**</span><span class="sxs-lookup"><span data-stu-id="584cb-152">**Warn if a merge length for LAN connections exceeds the threshold**</span></span>  
  
    -   <span data-ttu-id="584cb-153">**Warnung, wenn der Wert für zusammengeführte Zeilen pro Sekunde für LAN-Verbindungen kleiner ist als der Schwellenwert**</span><span class="sxs-lookup"><span data-stu-id="584cb-153">**Warn if rows merged per second for LAN connections is less than the threshold**</span></span>  
  
    -   <span data-ttu-id="584cb-154">**Warnung, wenn der Wert für zusammengeführte Zeilen pro Sekunde für DFÜ-Verbindungen kleiner ist als der Schwellenwert**</span><span class="sxs-lookup"><span data-stu-id="584cb-154">**Warn if rows merged per second for dialup connections is less than the threshold**</span></span>  
  
4.  <span data-ttu-id="584cb-155">Legen Sie in der **Schwellenwert** -Spalte Schwellenwerte für die Warnungen fest</span><span class="sxs-lookup"><span data-stu-id="584cb-155">Set thresholds for the warnings in the **Threshold** column.</span></span> <span data-ttu-id="584cb-156">Wenn Sie beispielsweise unter Schritt 3 die Option **Warnung, wenn eine Zusammenführungslänge für DFÜ-Verbindungen den Schwellenwert überschreitet** ausgewählt haben, könnten Sie in der **Schwellenwert** -Spalte beispielsweise **10 Minuten** angeben.</span><span class="sxs-lookup"><span data-stu-id="584cb-156">For example, if you selected **Warn if a merge length for dialup connections exceeds the threshold** in step 3, you could select a time of **10 minutes** in the **Threshold** column.</span></span>  
  
5.  <span data-ttu-id="584cb-157">Klicken Sie auf **Änderungen speichern**.</span><span class="sxs-lookup"><span data-stu-id="584cb-157">Click **Save Changes**.</span></span>  
  
#### <a name="to-configure-an-alert-for-a-threshold"></a><span data-ttu-id="584cb-158">So konfigurieren Sie eine Warnung für einen Schwellenwert</span><span class="sxs-lookup"><span data-stu-id="584cb-158">To configure an alert for a threshold</span></span>  
  
1.  <span data-ttu-id="584cb-159">Klicken Sie auf **Warnungen konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="584cb-159">Click **Configure Alerts**.</span></span>  
  
2.  <span data-ttu-id="584cb-160">Wählen Sie im Dialogfeld **Replikationswarnungen konfigurieren** eine Warnung aus, und klicken Sie dann auf **Konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="584cb-160">In the **Configure Replication Alerts** dialog box, select an alert, and then click **Configure**.</span></span>  
  
     <span data-ttu-id="584cb-161">In diesem Dialogfeld werden Warnungen für alle Veröffentlichungstypen angezeigt – auch für Warnungen, die nichts mit den Überwachungsschwellenwerten zu tun haben.</span><span class="sxs-lookup"><span data-stu-id="584cb-161">This dialog box displays alerts for all publication types, including alerts that are not related to monitoring thresholds.</span></span>  
  
3.  <span data-ttu-id="584cb-162">Legen Sie im Dialogfeld **Eigenschaften von Warnung "\<AlertName>"** die gewünschten Optionen fest:</span><span class="sxs-lookup"><span data-stu-id="584cb-162">Set options in the **\<AlertName> alert properties** dialog box:</span></span>  
  
    -   <span data-ttu-id="584cb-163">Klicken Sie auf der Seite **Allgemein** auf **Aktivieren**, und geben Sie an, für welche Datenbank die Warnung gelten soll.</span><span class="sxs-lookup"><span data-stu-id="584cb-163">On the **General** page, click **Enable**; specify which database the alert should apply to.</span></span>  
  
    -   <span data-ttu-id="584cb-164">Geben Sie auf der Seite **Antwort** an, ob eine E-Mail gesendet und/oder ein Auftrag ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="584cb-164">On the **Response** page, specify whether an e-mail should be sent and/or a job should be executed.</span></span>  
  
    -   <span data-ttu-id="584cb-165">Passen Sie auf der Seite **Optionen** den Text der Antwort an.</span><span class="sxs-lookup"><span data-stu-id="584cb-165">On the **Options** page, customize the text of the response.</span></span>  
  
4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="584cb-166">Klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="584cb-166">Click **Close**.</span></span>  
  
##  <a name="set-thresholds-and-warnings-for-a-snapshot-publication"></a><a name="Snapshot"></a> <span data-ttu-id="584cb-167">Festlegen der Schwellenwerte und Warnungen für eine Momentaufnahmeveröffentlichung</span><span class="sxs-lookup"><span data-stu-id="584cb-167">Set thresholds and warnings for a snapshot publication</span></span>  
  
1.  <span data-ttu-id="584cb-168">Erweitern Sie im linken Bereich eine Verlegergruppe, erweitern Sie einen Verleger, und klicken Sie dann auf eine Veröffentlichung.</span><span class="sxs-lookup"><span data-stu-id="584cb-168">Expand a Publisher group in the left pane, expand a Publisher, and then click a publication.</span></span>  
  
2.  <span data-ttu-id="584cb-169">Klicken Sie auf die Registerkarte **Warnungen** . Wenn Sie weitere Informationen zu den Optionen auf dieser Registerkarte benötigen, klicken Sie im Menü am oberen Rand auf **Hilfe** .</span><span class="sxs-lookup"><span data-stu-id="584cb-169">Click the **Warnings** tab. To view more information about the options on this tab click **Help** on the top menu.</span></span>  
  
3.  <span data-ttu-id="584cb-170">Aktivieren Sie die Warnung, indem Sie das Kontrollkästchen **Warnung, wenn ein Abonnement innerhalb des Schwellenwerts abläuft**aktivieren.</span><span class="sxs-lookup"><span data-stu-id="584cb-170">Enable a warning by selecting the check box **Warn if a subscription will expire within the threshold**.</span></span>  
  
4.  <span data-ttu-id="584cb-171">Legen Sie in der **Schwellenwert** -Spalte einen Schwellenwert für die Warnung fest</span><span class="sxs-lookup"><span data-stu-id="584cb-171">Set a threshold for the warning in the **Threshold** column.</span></span> <span data-ttu-id="584cb-172">Sie können z.B. einen Wert von **70%** in der **Schwellenwert**-Spalte auswählen.</span><span class="sxs-lookup"><span data-stu-id="584cb-172">For example, you could select a value of **70%** in the **Threshold** column.</span></span>  
  
5.  <span data-ttu-id="584cb-173">Klicken Sie auf **Änderungen speichern**.</span><span class="sxs-lookup"><span data-stu-id="584cb-173">Click **Save Changes**.</span></span>  
  
#### <a name="to-configure-an-alert-for-a-threshold"></a><span data-ttu-id="584cb-174">So konfigurieren Sie eine Warnung für einen Schwellenwert</span><span class="sxs-lookup"><span data-stu-id="584cb-174">To configure an alert for a threshold</span></span>  
  
1.  <span data-ttu-id="584cb-175">Klicken Sie auf **Warnungen konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="584cb-175">Click **Configure Alerts**.</span></span>  
  
2.  <span data-ttu-id="584cb-176">Wählen Sie im Dialogfeld **Replikationswarnungen konfigurieren** eine Warnung aus, und klicken Sie dann auf **Konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="584cb-176">In the **Configure Replication Alerts** dialog box, select an alert, and then click **Configure**.</span></span>  
  
     <span data-ttu-id="584cb-177">In diesem Dialogfeld werden Warnungen für alle Veröffentlichungstypen angezeigt – auch für Warnungen, die nichts mit den Überwachungsschwellenwerten zu tun haben.</span><span class="sxs-lookup"><span data-stu-id="584cb-177">This dialog box displays alerts for all publication types, including alerts that are not related to monitoring thresholds.</span></span> <span data-ttu-id="584cb-178">Weitere Informationen finden Sie unter [Verwenden von Warnungen für Replikations-Agentereignisse](../agents/use-alerts-for-replication-agent-events.md).</span><span class="sxs-lookup"><span data-stu-id="584cb-178">For more information, see [Use Alerts for Replication Agent Events](../agents/use-alerts-for-replication-agent-events.md).</span></span>  
  
3.  <span data-ttu-id="584cb-179">Legen Sie im Dialogfeld **Eigenschaften von Warnung "\<AlertName>"** die gewünschten Optionen fest:</span><span class="sxs-lookup"><span data-stu-id="584cb-179">Set options in the **\<AlertName> alert properties** dialog box:</span></span>  
  
    -   <span data-ttu-id="584cb-180">Klicken Sie auf der Seite **Allgemein** auf **Aktivieren**, und geben Sie an, für welche Datenbank die Warnung gelten soll.</span><span class="sxs-lookup"><span data-stu-id="584cb-180">On the **General** page, click **Enable**; specify which database the alert should apply to.</span></span>  
  
    -   <span data-ttu-id="584cb-181">Geben Sie auf der Seite **Antwort** an, ob eine E-Mail gesendet und/oder ein Auftrag ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="584cb-181">On the **Response** page, specify whether an e-mail should be sent and/or a job should be executed.</span></span>  
  
    -   <span data-ttu-id="584cb-182">Passen Sie auf der Seite **Optionen** den Text der Antwort an.</span><span class="sxs-lookup"><span data-stu-id="584cb-182">On the **Options** page, customize the text of the response.</span></span>  
  
4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="584cb-183">Klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="584cb-183">Click **Close**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="584cb-184">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="584cb-184">See Also</span></span>  
 [<span data-ttu-id="584cb-185">Überwachen der Replikation</span><span class="sxs-lookup"><span data-stu-id="584cb-185">Monitoring Replication</span></span>](../monitoring-replication.md)  
  
  
