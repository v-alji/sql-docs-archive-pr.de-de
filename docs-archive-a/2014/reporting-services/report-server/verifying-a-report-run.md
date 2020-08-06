---
title: Überprüfen einer Berichtsausführung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- auditing [Reporting Services]
- verifying report execution
- logs [Reporting Services], verifying report run
- report execution data [Reporting Services]
- status information [Reporting Services]
- report processing [Reporting Services], verifying execution
- checking report execution
ms.assetid: 18a98f2f-6b40-454e-9b37-568ed1a96458
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c11c57f7c5f67b2557f5637ad10658abc9f80606
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617614"
---
# <a name="verifying-a-report-run"></a><span data-ttu-id="91f20-102">Überprüfen einer Berichtsausführung</span><span class="sxs-lookup"><span data-stu-id="91f20-102">Verifying a Report Run</span></span>
  <span data-ttu-id="91f20-103">Mit Protokolldateien oder den Statusinformationen, die zusammen mit einem Bericht im Berichts-Manager angezeigt werden, können Sie Informationen zum Status der Berichtsverarbeitung anzeigen.</span><span class="sxs-lookup"><span data-stu-id="91f20-103">To view information about the status of report processing, you can use log files or refer to status information that is displayed with the report in Report Manager.</span></span>  
  
## <a name="sources-of-report-execution-data"></a><span data-ttu-id="91f20-104">Quellen für Berichtausführungsdaten</span><span class="sxs-lookup"><span data-stu-id="91f20-104">Sources of Report Execution Data</span></span>  
 <span data-ttu-id="91f20-105">Die Berichtsausführungsprotokolle stellen umfangreiche Informationen zur Berichtsausführung bereit. Hierzu zählen der Name des Berichts, der Name des Benutzers, der den Bericht ausgeführt hat, der Zeitpunkt der Berichtsausführung sowie die verwendete Übermittlungserweiterung für die Weitergabe des Berichts.</span><span class="sxs-lookup"><span data-stu-id="91f20-105">The report execution logs provide comprehensive information about report execution, including the name of the report, the name of the user who ran the report, report execution time, and the delivery extension used to distribute the report.</span></span> <span data-ttu-id="91f20-106">Um diese Daten anzuzeigen und zu analysieren, kopieren Sie das Berichtsausführungsprotokoll in Datenbanktabellen, für die problemlos Abfragen ausgeführt und Berichte erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="91f20-106">To view and analyze this data, you can copy the report execution log into database tables that are easy to query and report on.</span></span>  
  
 <span data-ttu-id="91f20-107">Protokolldateien enthalten eine Vielzahl von Einträgen zur Berichtsausführung und zu anderen Serveraktivitäten.</span><span class="sxs-lookup"><span data-stu-id="91f20-107">Log files contain many entries about report execution and other server activity.</span></span> <span data-ttu-id="91f20-108">Da Protokolldateien so viele Daten enthalten, sollten Sie den Berichts-Manager verwenden, wenn Sie nur überprüfen möchten, wann der Bericht zuletzt ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="91f20-108">Because log files contain so much data, you may want to use Report Manager if you only want to verify when the report last ran.</span></span> <span data-ttu-id="91f20-109">Falls Sie zusätzliche Informationen benötigen, müssen Sie die Protokolldateien ansehen.</span><span class="sxs-lookup"><span data-stu-id="91f20-109">If you require additional information, you must view the log files.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="91f20-110">Im Berichts-Manager werden die Verarbeitungszeiten von Berichten, die bei Bedarf ausgeführt wurden, nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="91f20-110">Report Manager does not show the processing times of reports that run on demand.</span></span>  
  
 <span data-ttu-id="91f20-111">In der folgenden Tabelle ist beschrieben, wie Sie das Datum und die Uhrzeit der Verarbeitung für verschiedene Berichtstypen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="91f20-111">The following table describes how to view the processing date and time for various types of reports.</span></span>  
  
|<span data-ttu-id="91f20-112">Berichtstyp</span><span class="sxs-lookup"><span data-stu-id="91f20-112">For this type of report</span></span>|<span data-ttu-id="91f20-113">Datum und Uhrzeit ist hier zu finden</span><span class="sxs-lookup"><span data-stu-id="91f20-113">Date and time information is located here</span></span>|<span data-ttu-id="91f20-114">Vorgehensweise zum Anzeigen der Informationen</span><span class="sxs-lookup"><span data-stu-id="91f20-114">To view the information, do the following</span></span>|  
|-----------------------------|-----------------------------------------------|-----------------------------------------------|  
|<span data-ttu-id="91f20-115">Ein Bericht, der als Berichtsmomentaufnahme ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="91f20-115">A report that runs as a report snapshot.</span></span>|<span data-ttu-id="91f20-116">Auf der Seite Inhalt.</span><span class="sxs-lookup"><span data-stu-id="91f20-116">On the Contents page.</span></span> <span data-ttu-id="91f20-117">Weitere Informationen finden Sie unter [Inhalt (Seite) (Berichts-Manager)](../contents-page-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="91f20-117">For more information, see [Contents Page &#40;Report Manager&#41;](../contents-page-report-manager.md).</span></span>|<span data-ttu-id="91f20-118">1) Suchen Sie den Ordner, in dem der Bericht gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="91f20-118">1) Locate the folder that contains the report.</span></span><br /><span data-ttu-id="91f20-119">2) Wählen Sie für den Ordner die Sicht „Details“ aus.</span><span class="sxs-lookup"><span data-stu-id="91f20-119">2) Set the folder in Details view.</span></span><br /><span data-ttu-id="91f20-120">3) 3) notieren Sie sich das Datum und die Uhrzeit in der Spalte **beim Ausführen** .</span><span class="sxs-lookup"><span data-stu-id="91f20-120">3) 3) Note the date and time in the **When Run** column.</span></span>|  
|<span data-ttu-id="91f20-121">Eine Momentaufnahme im Berichtsverlauf.</span><span class="sxs-lookup"><span data-stu-id="91f20-121">A snapshot in report history.</span></span>|<span data-ttu-id="91f20-122">Auf der Eigenschaftenseite Verlauf.</span><span class="sxs-lookup"><span data-stu-id="91f20-122">On the History Properties page.</span></span> <span data-ttu-id="91f20-123">Weitere Informationen finden Sie unter [Momentaufnahmeoptionen (Eigenschaftenseite) (Berichts-Manager)](../snapshot-options-properties-page-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="91f20-123">For more information, see [Snapshot Options Properties Page &#40;Report Manager&#41;](../snapshot-options-properties-page-report-manager.md).</span></span>|<span data-ttu-id="91f20-124">1) Öffnen Sie den Bericht.</span><span class="sxs-lookup"><span data-stu-id="91f20-124">1) Open the report.</span></span><br /><span data-ttu-id="91f20-125">2) Klicken Sie auf die Seite **Eigenschaften** .</span><span class="sxs-lookup"><span data-stu-id="91f20-125">2) Click the **Properties** page.</span></span><br /><span data-ttu-id="91f20-126">3) Klicken Sie auf die Registerkarte **Verlauf** .</span><span class="sxs-lookup"><span data-stu-id="91f20-126">3) Click the **History** tab.</span></span><br /><span data-ttu-id="91f20-127">4) Notieren Sie sich das Datum und die Uhrzeit in der Spalte **Wann ausgeführt** .</span><span class="sxs-lookup"><span data-stu-id="91f20-127">4) Note the date and time in the **When Run** column.</span></span>|  
|<span data-ttu-id="91f20-128">Ein zwischengespeicherter Bericht.</span><span class="sxs-lookup"><span data-stu-id="91f20-128">A cached report.</span></span>|<span data-ttu-id="91f20-129">Im Zeitplan, der zum Erstellen und Aktualisieren des zwischengespeicherten Berichts verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="91f20-129">In the schedule used to create and refresh the cached report.</span></span>|<span data-ttu-id="91f20-130">1) Öffnen Sie den Bericht.</span><span class="sxs-lookup"><span data-stu-id="91f20-130">1) Open the report.</span></span><br /><span data-ttu-id="91f20-131">2) Klicken Sie auf die Seite **Eigenschaften** .</span><span class="sxs-lookup"><span data-stu-id="91f20-131">2) Click the **Properties** page.</span></span><br /><span data-ttu-id="91f20-132">3) Klicken Sie auf die Registerkarte **Ausführung** .</span><span class="sxs-lookup"><span data-stu-id="91f20-132">3) Click the **Execution** tab.</span></span><br /><span data-ttu-id="91f20-133">4) Öffnen Sie den Zeitplan.</span><span class="sxs-lookup"><span data-stu-id="91f20-133">4) Open the schedule.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="91f20-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="91f20-134">See Also</span></span>  
 <span data-ttu-id="91f20-135">[Reporting Services-Protokolldateien und Quellen](../report-server/reporting-services-log-files-and-sources.md) </span><span class="sxs-lookup"><span data-stu-id="91f20-135">[Reporting Services Log Files and Sources](../report-server/reporting-services-log-files-and-sources.md) </span></span>  
 <span data-ttu-id="91f20-136">[Festlegen von Berichtsverarbeitungseigenschaften](set-report-processing-properties.md) </span><span class="sxs-lookup"><span data-stu-id="91f20-136">[Set Report Processing Properties](set-report-processing-properties.md) </span></span>  
 [<span data-ttu-id="91f20-137">Berichts-Manager (einheitlicher SSRS-Modus)</span><span class="sxs-lookup"><span data-stu-id="91f20-137">Report Manager  &#40;SSRS Native Mode&#41;</span></span>](../report-manager-ssrs-native-mode.md)  
  
  
