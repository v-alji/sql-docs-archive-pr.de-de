---
title: Einschränken des Berichtsverlaufs (Berichts-Manager) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- viewing report history
- report history [Reporting Services], viewing history
- report history [Reporting Services], configuring history
- historical data [Reporting Services]
- displaying report history
ms.assetid: 8e255792-d9ef-496f-a26c-9e969c1209a0
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 01318b1e1ccf0b0bf4512ab57de90cbf5ebc7365
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697462"
---
# <a name="limit-report-history-report-manager"></a><span data-ttu-id="d0a0e-102">Einschränken des Berichtsverlaufs (Berichts-Manager)</span><span class="sxs-lookup"><span data-stu-id="d0a0e-102">Limit Report History (Report Manager)</span></span>
  <span data-ttu-id="d0a0e-103">Der Berichtsverlauf stellt eine Auflistung von Berichtsmomentaufnahmen dar, die Sie im Laufe der Zeit erstellen.</span><span class="sxs-lookup"><span data-stu-id="d0a0e-103">Report history is a collection of report snapshots that you create over time.</span></span> <span data-ttu-id="d0a0e-104">Sie können den Berichtsverlauf nach Bedarf erstellen oder aber anhand eines Zeitplans festlegen, wie oft eine Momentaufnahme erstellt und dem Berichtsverlauf hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="d0a0e-104">You can create report history on demand, or schedule how often a snapshot is created and added to report history.</span></span>  
  
 <span data-ttu-id="d0a0e-105">Der Berichtsverlauf wird in der Berichtsserverdatenbank gespeichert.</span><span class="sxs-lookup"><span data-stu-id="d0a0e-105">Report history is stored in the report server database.</span></span> <span data-ttu-id="d0a0e-106">Wenn Berichtsmomentaufnahmen eine große Datenmenge enthalten, können Sie den Berichtsverlauf einschränken, um die Auswirkungen der Beibehaltung der Momentaufnahmen auf die Datenbankgröße zu minimieren.</span><span class="sxs-lookup"><span data-stu-id="d0a0e-106">If report snapshots contain a large amount of data, you might consider limiting report history to minimize the affect of snapshot retention on database size.</span></span>  
  
### <a name="to-configure-report-history-for-a-report-server"></a><span data-ttu-id="d0a0e-107">So konfigurieren Sie den Berichtsverlauf für einen Berichtsserver</span><span class="sxs-lookup"><span data-stu-id="d0a0e-107">To configure report history for a report server</span></span>  
  
1.  <span data-ttu-id="d0a0e-108">Klicken Sie im Berichts-Manager auf der globalen Symbolleiste auf **Siteeinstellungen** .</span><span class="sxs-lookup"><span data-stu-id="d0a0e-108">In Report Manager, click **Site Settings** on the global toolbar.</span></span>  
  
2.  <span data-ttu-id="d0a0e-109">Wählen Sie **Beliebig viele Momentaufnahmen im Berichtsverlauf speichern** aus, wenn Sie alle Berichtsverläufe unbegrenzt lange aufbewahren möchten.</span><span class="sxs-lookup"><span data-stu-id="d0a0e-109">Select **Keep an unlimited number of snapshots in report history** if you want to keep all report history indefinitely.</span></span> <span data-ttu-id="d0a0e-110">Wählen Sie andernfalls **Max. Anzahl von Kopien des Berichtsverlaufs** aus, um die maximale Anzahl von Momentaufnahmen anzugeben, die für einen bestimmten Bericht aufbewahrt werden können.</span><span class="sxs-lookup"><span data-stu-id="d0a0e-110">Otherwise, select **Limit the copies of report history** to specify the maximum number of snapshots that can be kept for any given report.</span></span>  
  
3.  <span data-ttu-id="d0a0e-111">Klicken Sie auf **Anwenden**.</span><span class="sxs-lookup"><span data-stu-id="d0a0e-111">Click **Apply**.</span></span>  
  
### <a name="to-configure-report-history-for-a-specific-report"></a><span data-ttu-id="d0a0e-112">So konfigurieren Sie den Berichtsverlauf für einen bestimmten Bericht</span><span class="sxs-lookup"><span data-stu-id="d0a0e-112">To configure report history for a specific report</span></span>  
  
1.  <span data-ttu-id="d0a0e-113">Navigieren Sie im Berichts-Manager zu dem Bericht, dessen Verlauf Sie konfigurieren möchten, und öffnen Sie ihn, indem Sie auf ihn klicken.</span><span class="sxs-lookup"><span data-stu-id="d0a0e-113">In Report Manager, navigate to the report for which you want to configure history, and then click the report to open it.</span></span>  
  
2.  <span data-ttu-id="d0a0e-114">Klicken Sie auf die Registerkarte **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="d0a0e-114">Click the **Properties** tab.</span></span>  
  
3.  <span data-ttu-id="d0a0e-115">Klicken Sie auf die Registerkarte **Verlauf**.</span><span class="sxs-lookup"><span data-stu-id="d0a0e-115">Click the **History** tab.</span></span>  
  
4.  <span data-ttu-id="d0a0e-116">Wählen Sie die Optionen für Ihren Bericht aus, und klicken Sie auf **Anwenden**.</span><span class="sxs-lookup"><span data-stu-id="d0a0e-116">Select the options for your report and click **Apply**.</span></span> <span data-ttu-id="d0a0e-117">Weitere Informationen zu den einzelnen Optionen finden Sie unter [Momentaufnahmeoptionen Eigenschaftenseite (Berichts-Manager)](../snapshot-options-properties-page-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="d0a0e-117">For details about each option, see [Snapshot Options Properties Page &#40;Report Manager&#41;](../snapshot-options-properties-page-report-manager.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0a0e-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d0a0e-118">See Also</span></span>  
 <span data-ttu-id="d0a0e-119">[Hinzufügen einer Momentaufnahme zum Berichts Verlauf &#40;Berichts-Manager&#41;](../report-server/add-a-snapshot-to-report-history-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="d0a0e-119">[Add a Snapshot to Report History &#40;Report Manager&#41;](../report-server/add-a-snapshot-to-report-history-report-manager.md) </span></span>  
 [<span data-ttu-id="d0a0e-120">Berichts-Manager &#40;einheitlicher SSRS-Modus&#41;</span><span class="sxs-lookup"><span data-stu-id="d0a0e-120">Report Manager  &#40;SSRS Native Mode&#41;</span></span>](../report-manager-ssrs-native-mode.md)  
  
  
