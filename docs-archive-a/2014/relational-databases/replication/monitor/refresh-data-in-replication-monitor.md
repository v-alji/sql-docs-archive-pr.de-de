---
title: Aktualisieren von Daten in Replikationsmonitor | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- refreshing data
ms.assetid: e9582244-7d00-45f4-be16-020a65c76a5e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2f097dea21b06540293e9b60b7de9315323b4168
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725510"
---
# <a name="refresh-data-in-replication-monitor"></a><span data-ttu-id="3cbfe-102">Aktualisieren von Daten in Replikationsmonitor</span><span class="sxs-lookup"><span data-stu-id="3cbfe-102">Refresh Data in Replication Monitor</span></span>
  <span data-ttu-id="3cbfe-103">Im Replikationsmonitor können das Hauptfenster und die Detailfenster (die Fenster, die vom Hauptfenster aus aufrufbar sind) sowohl automatisch als auch manuell aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="3cbfe-103">In Replication Monitor, the main window and detail windows (those windows launched from the main window) can be refreshed automatically or manually.</span></span> <span data-ttu-id="3cbfe-104">Zum manuellen Aktualisieren eines Fensters drücken Sie F5.</span><span class="sxs-lookup"><span data-stu-id="3cbfe-104">To refresh a window manually, press F5.</span></span> <span data-ttu-id="3cbfe-105">Das Hauptfenster wird standardmäßig alle fünf Sekunden aktualisiert. Diese Zeiteinstellung kann aber für jeden Verleger individuell angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="3cbfe-105">By default, the main window is refreshed automatically every five seconds; the rate can be customized for each Publisher.</span></span>  
  
 <span data-ttu-id="3cbfe-106">Die im Replikationsmonitor angezeigten Daten werden aus einem Zwischenspeicher abgerufen. Informationen zum Zusammenhang zwischen dem Zwischenspeicher und dem Aktualisieren des Replikationsmonitors finden Sie unter [Zwischenspeichern, Aktualisieren und Leistung des Replikationsmonitors](caching-refresh-and-replication-monitor-performance.md).</span><span class="sxs-lookup"><span data-stu-id="3cbfe-106">The data displayed in Replication Monitor is queried from a cache; for information about the relationship between the cache and refreshing Replication Monitor, see [Caching, Refresh, and Replication Monitor Performance](caching-refresh-and-replication-monitor-performance.md).</span></span> <span data-ttu-id="3cbfe-107">Informationen zum Starten des Replikationsmonitors finden Sie unter [Starten des Replikationsmonitors](start-the-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="3cbfe-107">For information about starting Replication Monitor, see [Start the Replication Monitor](start-the-replication-monitor.md).</span></span>  
  
### <a name="to-set-refresh-options-for-replication-monitor"></a><span data-ttu-id="3cbfe-108">So legen Sie die Aktualisierungseinstellungen für den Replikationsmonitor fest</span><span class="sxs-lookup"><span data-stu-id="3cbfe-108">To set refresh options for Replication Monitor</span></span>  
  
1.  <span data-ttu-id="3cbfe-109">Klicken Sie mit der rechten Maustaste im linken Bereich des Replikationsmonitors auf einen Verleger, und klicken Sie dann auf **Verlegereinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="3cbfe-109">Right-click a Publisher in the left pane of Replication Monitor, and then click **Publisher Settings**.</span></span>  
  
2.  <span data-ttu-id="3cbfe-110">Legen Sie im Dialogfeld **Verlegereinstellungen** für die Optionen **Automatisch aktualisieren** und **Aktualisierungsrate** eine Einstellung fest.</span><span class="sxs-lookup"><span data-stu-id="3cbfe-110">In the **Publisher Settings** dialog box, set the **Auto refresh** and **Refresh rate** options.</span></span> <span data-ttu-id="3cbfe-111">Die Einstellung für **Automatisch aktualisieren** wirkt sich auf das Hauptfenster im Replikationsmonitor aus.</span><span class="sxs-lookup"><span data-stu-id="3cbfe-111">The **Auto refresh** setting affects the main window in Replication Monitor.</span></span> <span data-ttu-id="3cbfe-112">Die Einstellung **Aktualisierungsrate** hat darüber hinaus Auswirkungen auf die Detailfenster, für die eine automatische Aktualisierung festgelegt wird (Änderungen an dieser Einstellung gelten nur für die Detailfenster, die nach dieser Änderung geöffnet werden).</span><span class="sxs-lookup"><span data-stu-id="3cbfe-112">The **Refresh rate** setting also affects any detail windows that are set to refresh automatically (changes to the setting only affect the detail windows opened after the change).</span></span>  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="to-specify-that-a-detail-window-should-automatically-refresh"></a><span data-ttu-id="3cbfe-113">So geben Sie an, dass ein Detailfenster automatisch aktualisiert wird</span><span class="sxs-lookup"><span data-stu-id="3cbfe-113">To specify that a detail window should automatically refresh</span></span>  
  
1.  <span data-ttu-id="3cbfe-114">Öffnen Sie das gewünschte Detailfenster im Replikationsmonitor.</span><span class="sxs-lookup"><span data-stu-id="3cbfe-114">Open a detail window in Replication Monitor.</span></span> <span data-ttu-id="3cbfe-115">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3cbfe-115">For example:</span></span>  
  
    1.  <span data-ttu-id="3cbfe-116">Erweitern Sie im linken Bereich eine Verlegergruppe, erweitern Sie einen Verleger, und klicken Sie dann auf eine Veröffentlichung.</span><span class="sxs-lookup"><span data-stu-id="3cbfe-116">Expand a Publisher group in the left pane, expand a Publisher, and then click a publication.</span></span>  
  
    2.  <span data-ttu-id="3cbfe-117">Klicken Sie auf die Registerkarte **Alle Abonnements** .</span><span class="sxs-lookup"><span data-stu-id="3cbfe-117">Click the **All Subscriptions** tab.</span></span>  
  
    3.  <span data-ttu-id="3cbfe-118">Klicken Sie mit der rechten Maustaste auf ein Abonnement, und klicken Sie dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="3cbfe-118">Right-click a subscription, and then click **View Details**.</span></span>  
  
2.  <span data-ttu-id="3cbfe-119">Klicken Sie im Detailfenster **Abonnement \<SubscriptionName>** auf **Aktion** und anschließend auf **Automatisch aktualisieren**.</span><span class="sxs-lookup"><span data-stu-id="3cbfe-119">In the **Subscription \<SubscriptionName>** detail window, click **Action**, and then click **Auto Refresh**.</span></span> <span data-ttu-id="3cbfe-120">Die Häufigkeit der Aktualisierung richtet sich nach der Einstellung **Aktualisierungsrate** im Dialogfeld **Verlegereinstellungen** .</span><span class="sxs-lookup"><span data-stu-id="3cbfe-120">The refresh rate is determined by the **Refresh rate** setting in the **Publisher Settings** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cbfe-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3cbfe-121">See Also</span></span>  
 [<span data-ttu-id="3cbfe-122">Überwachen der Replikation</span><span class="sxs-lookup"><span data-stu-id="3cbfe-122">Monitoring Replication</span></span>](../monitoring-replication.md)  
  
  
