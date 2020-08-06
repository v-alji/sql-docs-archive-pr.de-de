---
title: Anzeigen eines Sammlungssatzberichts (SQL Server Management Studio) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.dc.reporthistory.calendar.f1
helpviewer_keywords:
- collection sets [SQL Server], viewing reports
- reports [SQL Server], viewing collection set
ms.assetid: c3b1e791-9aa1-4bba-9622-4954568e1820
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: cb8755c67e6c03bb318fdb86d703f6d647d5a3eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621011"
---
# <a name="view-a-collection-set-report-sql-server-management-studio"></a><span data-ttu-id="397de-102">Anzeigen eines Sammlungssatzberichts (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="397de-102">View a Collection Set Report (SQL Server Management Studio)</span></span>
  <span data-ttu-id="397de-103">Nachdem Sie das Verwaltungs-Data Warehouse konfiguriert haben, können Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]einen Sammlungssatzbericht anzeigen.</span><span class="sxs-lookup"><span data-stu-id="397de-103">After you have configured the management data warehouse, you can view a collection set report in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="397de-104">Berichte werden für die Systemdatensammlungssätze bereitgestellt, die während des Setups installiert werden.</span><span class="sxs-lookup"><span data-stu-id="397de-104">Reports are provided for the System Data collection sets that are installed during Setup.</span></span> <span data-ttu-id="397de-105">Dazu gehören die folgenden Berichte:</span><span class="sxs-lookup"><span data-stu-id="397de-105">The reports include the following:</span></span>  
  
-   <span data-ttu-id="397de-106">Zusammenfassung der Datenträgerverwendung</span><span class="sxs-lookup"><span data-stu-id="397de-106">Disk Usage Summary</span></span>  
  
-   <span data-ttu-id="397de-107">Abfragestatistik - Verlauf</span><span class="sxs-lookup"><span data-stu-id="397de-107">Query Statistics History</span></span>  
  
-   <span data-ttu-id="397de-108">Serveraktivität - Verlauf</span><span class="sxs-lookup"><span data-stu-id="397de-108">Server Activity History</span></span>  
  
 <span data-ttu-id="397de-109">Mit dieser Prozedur wird der Bericht für den Sammlungssatz **Datenträgerverwendung** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="397de-109">This procedure displays the report for the **Disk Usage** collection set.</span></span> <span data-ttu-id="397de-110">Sie können den gleichen allgemeinen Schritten folgen, um die Berichte für die anderen Systemdaten-Sammlungssätze anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="397de-110">You can follow the same general procedure to view the reports for the other System Data collection sets.</span></span>  
  
### <a name="to-view-a-collection-set-report"></a><span data-ttu-id="397de-111">So zeigen Sie einen Sammlungssatzbericht an</span><span class="sxs-lookup"><span data-stu-id="397de-111">To view a collection set report</span></span>  
  
1.  <span data-ttu-id="397de-112">Die Tabellen für einen Bericht werden beim ersten Hochladen der gesammelten Daten erstellt.</span><span class="sxs-lookup"><span data-stu-id="397de-112">The tables for a report are created the first time that the collected data is uploaded.</span></span> <span data-ttu-id="397de-113">Wenn Sie versuchen, einen Bericht vor diesem ersten Upload anzuzeigen, tritt ein Fehler auf, und es wird kein Bericht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="397de-113">If you try to view a report before this first upload, an error occurs and no report is displayed.</span></span> <span data-ttu-id="397de-114">Um Daten für den Sammlungssatz „Datenträgerverwendung“ hochzuladen, erweitern Sie im Objekt-Explorer nacheinander den Ordner **Verwaltung** , **Datensammlung**sowie **Systemdaten-Sammlungssätze**, klicken Sie mit der rechten Maustaste auf den Sammlungssatz **Datenträgerverwendung** , und klicken Sie dann auf **Sammeln und jetzt hochladen**.</span><span class="sxs-lookup"><span data-stu-id="397de-114">To upload data for the Disk Usage collection set, in Object Explorer, expand the **Management** folder, expand **Data Collection**, expand **System Data Collection Sets**, right-click the **Disk Usage** collection set, and then click **Collect and Upload Now**.</span></span>  
  
2.  <span data-ttu-id="397de-115">Um den Bericht anzuzeigen, erweitern Sie im Objekt-Explorer den Ordner **Verwaltung** , klicken Sie mit der rechten Maustaste auf **Datensammlung**, zeigen Sie auf **Berichte**und dann auf **Verwaltungs-Data Warehouse**, und klicken Sie auf **Zusammenfassung der Datenträgerverwendung**.</span><span class="sxs-lookup"><span data-stu-id="397de-115">To view the report, in Object Explorer, expand the **Management** folder, right-click **Data Collection**, point to **Reports**, point to **Management Data Warehouse**, and then click **Disk Usage Summary**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="397de-116">Einige Berichte könnten eine Kalenderschaltfläche unter der Datensammlungszeitachse anzeigen.</span><span class="sxs-lookup"><span data-stu-id="397de-116">Some reports might display a calendar button under the data collection timeline.</span></span> <span data-ttu-id="397de-117">Klicken Sie auf diese Schaltfläche, um auf den **Kalender für Datensammlungsberichte**zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="397de-117">Click this button to access the **Data Collection Report Calendar**.</span></span>  
  
#### <a name="data-collection-report-calendar"></a><span data-ttu-id="397de-118">Kalender für Datensammlungsberichte</span><span class="sxs-lookup"><span data-stu-id="397de-118">Data Collection Report Calendar</span></span>  
 <span data-ttu-id="397de-119">Verwenden Sie dieses Dialogfeld, um das Startdatum, die Startzeit und die Dauer der Daten anzugeben, über die ein Bericht erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="397de-119">Use this dialog box to specify the start date, start time, and duration of the data that you want to report on.</span></span> <span data-ttu-id="397de-120">Sie können z. B. einen Bericht über die Datenträgerverwendung eines Servers für einen bestimmten 12-Stunden-Zeitraum am letzten Mittwoch erstellen.</span><span class="sxs-lookup"><span data-stu-id="397de-120">For example, you may want to report on the disk usage activity of a server for a specific 12-hour period last Wednesday.</span></span>  
  
 <span data-ttu-id="397de-121">**Startdatum**</span><span class="sxs-lookup"><span data-stu-id="397de-121">**Start date**</span></span>  
 <span data-ttu-id="397de-122">Geben Sie ein Anfangsdatum für die Berichtsdaten ein, oder wählen Sie ein Datum aus dem Kalender aus.</span><span class="sxs-lookup"><span data-stu-id="397de-122">Enter a beginning date for the report data, or select one from the calendar.</span></span>  
  
 <span data-ttu-id="397de-123">**Startzeit**</span><span class="sxs-lookup"><span data-stu-id="397de-123">**Start time**</span></span>  
 <span data-ttu-id="397de-124">Geben Sie eine Anfangszeit für die Berichtsdaten ein, oder wählen Sie ein Datum durch Klicken auf die Pfeile aus.</span><span class="sxs-lookup"><span data-stu-id="397de-124">Enter a beginning time for the report data or specify one by clicking the arrows.</span></span>  
  
 <span data-ttu-id="397de-125">**Duration**</span><span class="sxs-lookup"><span data-stu-id="397de-125">**Duration**</span></span>  
 <span data-ttu-id="397de-126">Geben Sie den Zeitraum an, der in den Bericht aufgenommen werden soll.</span><span class="sxs-lookup"><span data-stu-id="397de-126">Specify the time range to include in the report.</span></span> <span data-ttu-id="397de-127">Der Standardwert ist 240 Minuten.</span><span class="sxs-lookup"><span data-stu-id="397de-127">The default value is 240 minutes.</span></span> <span data-ttu-id="397de-128">Die möglichen Auswahlwerte sind 15 Minuten, 60 Minuten, 240 Minuten(4 Stunden), 720 Minuten (12 Stunden) und 1440 Minuten (24 Stunden).</span><span class="sxs-lookup"><span data-stu-id="397de-128">The possible values to select from are 15 minutes, 60 minutes, 240 minutes (4 hours), 720 minutes (12 hours), and 1440 minutes (24 hours).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="397de-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="397de-129">See Also</span></span>  
 <span data-ttu-id="397de-130">[Datensammlung](data-collection.md) </span><span class="sxs-lookup"><span data-stu-id="397de-130">[Data Collection](data-collection.md) </span></span>  
 <span data-ttu-id="397de-131">[Benutzerdefinierte Berichte in Management Studio](../../ssms/object/custom-reports-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="397de-131">[Custom Reports in Management Studio](../../ssms/object/custom-reports-in-management-studio.md) </span></span>  
 [<span data-ttu-id="397de-132">Konfigurieren des Verwaltungs-Data Warehouses &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="397de-132">Configure the Management Data Warehouse &#40;SQL Server Management Studio&#41;</span></span>](configure-the-management-data-warehouse-sql-server-management-studio.md)  
  
  
