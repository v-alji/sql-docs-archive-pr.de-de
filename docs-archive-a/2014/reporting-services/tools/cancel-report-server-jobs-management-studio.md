---
title: Berichtsserveraufträge abbrechen (Management Studio) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.cancelreportserverjobs.f1
ms.assetid: 1c5b4975-49e9-4d0b-b298-2638e81edbfd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d0ef8ada32aab4ac368871da711d0fe63fff7620
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722502"
---
# <a name="cancel-report-server-jobs-management-studio"></a><span data-ttu-id="28327-102">Berichtsserveraufträge abbrechen (Management Studio)</span><span class="sxs-lookup"><span data-stu-id="28327-102">Cancel Report Server Jobs (Management Studio)</span></span>
  <span data-ttu-id="28327-103">Verwenden Sie das Dialogfeld **Berichtsserveraufträge abbrechen** , um ausgeführte Berichte anzuzeigen oder abzubrechen.</span><span class="sxs-lookup"><span data-stu-id="28327-103">Use the **Cancel Report Server Jobs** dialog box to view or cancel in-progress reports.</span></span> <span data-ttu-id="28327-104">Dieses Dialogfeld zeigt alle Aufträge an, die gerade auf dem Berichtsserver ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="28327-104">This dialog box shows all jobs that are currently running on the report server.</span></span> <span data-ttu-id="28327-105">Zwar können Sie gerade bearbeitete Aufträge nicht anhalten oder neu starten, jedoch können Sie alle oder einzelne Aufträge abbrechen, wenn ihr Abschluss zu lange dauert.</span><span class="sxs-lookup"><span data-stu-id="28327-105">Although you cannot pause or restart jobs that are currently processing, you can cancel all jobs or individual jobs if they are taking too long to complete.</span></span>  
  
 <span data-ttu-id="28327-106">Sie können sowohl Benutzer- als auch Systemaufträge abbrechen.</span><span class="sxs-lookup"><span data-stu-id="28327-106">You can cancel user jobs and system jobs.</span></span>  
  
-   <span data-ttu-id="28327-107">Als Benutzerauftrag wird ein Auftrag bezeichnet, der durch einen einzelnen Benutzer initiiert wird.</span><span class="sxs-lookup"><span data-stu-id="28327-107">A user job is any job that is initiated by an individual user.</span></span> <span data-ttu-id="28327-108">Dazu zählt das Ausführen eines Berichts bei Bedarf, das manuelle Erstellen einer Momentaufnahme zum Berichtsverlauf oder das manuelle Erstellen einer Momentaufnahme zur Berichtsausführung.</span><span class="sxs-lookup"><span data-stu-id="28327-108">This includes running a report on-demand, manually creating a report history snapshot, or manually creating report execution snapshot.</span></span> <span data-ttu-id="28327-109">Ein ausgeführtes Standardabonnement wird ebenfalls als Benutzerauftrag bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="28327-109">An in-progress standard subscription is also a user job.</span></span>  
  
-   <span data-ttu-id="28327-110">Als Systemauftrag wird ein Auftrag bezeichnet, der durch den Berichtsserver initiiert wird.</span><span class="sxs-lookup"><span data-stu-id="28327-110">A system job is one that is initiated by the report server.</span></span> <span data-ttu-id="28327-111">Systemaufträge schließen die geplante Berichtsverarbeitung ein.</span><span class="sxs-lookup"><span data-stu-id="28327-111">System jobs include scheduled report processing.</span></span>  
  
 <span data-ttu-id="28327-112">Öffnen Sie diese Seite, indem Sie [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]starten und eine Verbindung mit einem Berichtsserver herstellen. Klicken Sie mit der rechten Maustaste auf **Aufträge**, und klicken Sie anschließend auf **Alle Aufträge abbrechen**.</span><span class="sxs-lookup"><span data-stu-id="28327-112">To open this page, start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to a report server, right-click **Jobs**, and then click **Cancel All Jobs**.</span></span> <span data-ttu-id="28327-113">Sie können auch **Aufträge**öffnen und mit der rechten Maustaste auf einen auf dem Berichtsserver ausgeführten Auftrag klicken. Klicken Sie anschließend auf **Aufträge abbrechen**.</span><span class="sxs-lookup"><span data-stu-id="28327-113">You can also open **Jobs**, right-click a job that is running on the report server, and select **Cancel Job(s)**.</span></span>  
  
 <span data-ttu-id="28327-114">Vor dem Abbrechen eines Auftrags können Sie seine Eigenschaften anzeigen, um zu bestimmen, wann der Auftrag gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="28327-114">Before cancelling a job, you can view its properties to determine when the job started.</span></span> <span data-ttu-id="28327-115">Weitere Informationen finden Sie unter [Auftragseigenschaften (Management Studio)](job-properties-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="28327-115">For more information, see [Job Properties &#40;Management Studio&#41;](job-properties-management-studio.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="28327-116">Diese Funktion wird in [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] with Advanced Services nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="28327-116">This feature is not supported in [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] with Advanced Services.</span></span> <span data-ttu-id="28327-117">Die Seite wird nicht angezeigt, wenn Sie [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)]ausführen.</span><span class="sxs-lookup"><span data-stu-id="28327-117">The page does not appear when you are running [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="28327-118">Tastatur</span><span class="sxs-lookup"><span data-stu-id="28327-118">Options</span></span>  
 <span data-ttu-id="28327-119">**Name**</span><span class="sxs-lookup"><span data-stu-id="28327-119">**Name**</span></span>  
 <span data-ttu-id="28327-120">Zeigt den Berichtsnamen an.</span><span class="sxs-lookup"><span data-stu-id="28327-120">Shows the name of the report.</span></span> <span data-ttu-id="28327-121">Abonnements werden durch ihre Beschreibung identifiziert.</span><span class="sxs-lookup"><span data-stu-id="28327-121">Subscriptions are identified by their descriptions.</span></span>  
  
 <span data-ttu-id="28327-122">**Typ**</span><span class="sxs-lookup"><span data-stu-id="28327-122">**Type**</span></span>  
 <span data-ttu-id="28327-123">Die gültigen Werte sind **Benutzer** und **System**.</span><span class="sxs-lookup"><span data-stu-id="28327-123">Valid values are **User** and **System**.</span></span>  
  
 <span data-ttu-id="28327-124">**Startzeit**</span><span class="sxs-lookup"><span data-stu-id="28327-124">**Start Time**</span></span>  
 <span data-ttu-id="28327-125">Zeigt an, wann der Auftrag gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="28327-125">Shows when the job started.</span></span>  
  
 <span data-ttu-id="28327-126">**Benutzername**</span><span class="sxs-lookup"><span data-stu-id="28327-126">**User Name**</span></span>  
 <span data-ttu-id="28327-127">Bei Aufträgen, die von einem Benutzer initiiert wurden, zeigt diese Spalte den Namen des Benutzers an.</span><span class="sxs-lookup"><span data-stu-id="28327-127">For jobs that are initiated by a user, this column shows the name of the user.</span></span>  
  
 <span data-ttu-id="28327-128">**Status**</span><span class="sxs-lookup"><span data-stu-id="28327-128">**Status**</span></span>  
 <span data-ttu-id="28327-129">Zeigt den Status des Auftrags an.</span><span class="sxs-lookup"><span data-stu-id="28327-129">Shows the status of the job.</span></span> <span data-ttu-id="28327-130">Gültige Werte sind **Neu** und **Wird ausgeführt**.</span><span class="sxs-lookup"><span data-stu-id="28327-130">Valid values are **New** and **Running**.</span></span> <span data-ttu-id="28327-131">Bei Beginn des Auftrags ist der Status immer **Neu** .</span><span class="sxs-lookup"><span data-stu-id="28327-131">Status is always **New** when the job begins.</span></span> <span data-ttu-id="28327-132">Nach 60 Sekunden ändert sich der Status in **Wird ausgeführt**.</span><span class="sxs-lookup"><span data-stu-id="28327-132">After 60 seconds, status changes to **Running**.</span></span> <span data-ttu-id="28327-133">Sie müssen die Seite aktualisieren, damit die Änderung übernommen wird.</span><span class="sxs-lookup"><span data-stu-id="28327-133">You must refresh the page to pick up the change.</span></span>  
  
 <span data-ttu-id="28327-134">**OK**</span><span class="sxs-lookup"><span data-stu-id="28327-134">**OK**</span></span>  
 <span data-ttu-id="28327-135">Brechen Sie einen einzelnen Auftrag oder mehrere Aufträge ab.</span><span class="sxs-lookup"><span data-stu-id="28327-135">Cancel a single job or multiple jobs.</span></span> <span data-ttu-id="28327-136">Die Aufträge werden sofort abgebrochen und können nicht wiederaufgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="28327-136">The jobs are cancelled immediately and cannot be resumed.</span></span> <span data-ttu-id="28327-137">Wenn Sie versehentlich einen Auftrag abgebrochen haben, müssen sie den Bericht oder das Abonnement erneut anfordern, um einen neuen Auftrag zu starten.</span><span class="sxs-lookup"><span data-stu-id="28327-137">If you mistakenly cancel a job, you must request the report or subscription again to start a new job.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28327-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="28327-138">See Also</span></span>  
 <span data-ttu-id="28327-139">[Berichtsserver im Management Studio (F1-Hilfe)](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="28327-139">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 <span data-ttu-id="28327-140">[Vorgehensweise: Herstellen einer Verbindung mit einem Berichtsserver in Management Studio](connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="28327-140">[Connect to a Report Server in Management Studio](connect-to-a-report-server-in-management-studio.md) </span></span>  
 [<span data-ttu-id="28327-141">Verwalten eines ausgeführten Prozesses</span><span class="sxs-lookup"><span data-stu-id="28327-141">Manage a Running Process</span></span>](../subscriptions/manage-a-running-process.md)  
  
  
