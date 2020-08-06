---
title: Zeitplaneigenschaften (Allgemeine Seite) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.scheduleproperties.general.f1
ms.assetid: 20e43966-6caf-4972-a2e2-0d9131ac8f51
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a61837cd977526021be948d8c74a93eba6506e67
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616366"
---
# <a name="schedule-properties-general-page"></a><span data-ttu-id="250fc-102">Zeitplaneigenschaften (Registerkarte Allgemein)</span><span class="sxs-lookup"><span data-stu-id="250fc-102">Schedule Properties (General Page)</span></span>
  <span data-ttu-id="250fc-103">Auf dieser Seite können Sie einen freigegebenen Zeitplan anzeigen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="250fc-103">Use this page to view or modify a shared schedule.</span></span> <span data-ttu-id="250fc-104">Feigegebene Zeitpläne können anstelle berichts- oder abonnementspezifischer Zeitpläne verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="250fc-104">Shared schedules can be used in place of report-specific or subscription-specific schedules.</span></span> <span data-ttu-id="250fc-105">Änderungen am Zeitplan werden übernommen, nachdem Sie den Zeitplan gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="250fc-105">Changes to the schedule are applied after you save the schedule.</span></span> <span data-ttu-id="250fc-106">Die Bearbeitung eines Zeitplans hat keine Auswirkungen auf Aufträge, die gerade ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="250fc-106">Editing a schedule has no effect on jobs that are currently in progress.</span></span> <span data-ttu-id="250fc-107">Wenn Sie einen Zeitplan bearbeiten, der gerade verwendet wird, wird allen aktuell verarbeiteten Berichten und Abonnements, die durch den Zeitplan ausgelöst wurden, die Fertigstellung ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="250fc-107">If you edit a schedule while it is being used, all currently processing reports and subscriptions triggered from that schedule will be allowed to finish.</span></span>  
  
 <span data-ttu-id="250fc-108">Nicht alle Kombinationen der Häufigkeit können in einem einzelnen Zeitplan unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="250fc-108">Not all frequency combinations can be supported in a single schedule.</span></span> <span data-ttu-id="250fc-109">Wenn ein Bericht z. B. um 00:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="250fc-109">For example, if you want to run a report at 12:00 P.M.</span></span> <span data-ttu-id="250fc-110">und um 16:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="250fc-110">and 4:00 P.M.</span></span> <span data-ttu-id="250fc-111">an jedem Freitag ausgeführt werden soll, müssen Sie zwei Tageszeitpläne erstellen, in denen der Freitag als Ausführungstag angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="250fc-111">every Friday, you must create two daily schedules that specify a Friday run date, one with a start time of 12:00 P.M.</span></span> <span data-ttu-id="250fc-112">Der erste Zeitplan hat eine Startzeit von 00:00 Uhr, und für den zweiten ist eine Startzeit von 16:00 Uhr festgelegt.</span><span class="sxs-lookup"><span data-stu-id="250fc-112">and another with a start time of 4:00 P.M.</span></span>  
  
 <span data-ttu-id="250fc-113">Die Verarbeitung von Zeitplänen basiert auf der Ortszeit des Berichtsservers, auf dem der Zeitplan gehostet und verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="250fc-113">Schedule processing is based on the local time of the report server that hosts and processes the schedule.</span></span>  
  
 <span data-ttu-id="250fc-114">Um diese Seite zu öffnen, starten [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Sie, stellen eine Verbindung mit einem Berichts Server her, öffnen Sie den Ordner frei **gegebene Zeitpläne** , klicken mit **Properties**der rechten Maustaste auf einen freigegebenen Zeitplan, und wählen Sie</span><span class="sxs-lookup"><span data-stu-id="250fc-114">To open this page, start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to a report server, open the **Shared Schedules** folder, right-click a shared schedule, and select **Properties**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="250fc-115">Diese Funktion ist nicht in jeder Edition von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] verfügbar, und diese Seite wird nicht angezeigt, wenn Sie eine Edition ausführen, die nicht über diese Funktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="250fc-115">This feature is not available in every edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and this page does not appear when you are running an edition which does not have this feature.</span></span> <span data-ttu-id="250fc-116">Eine Liste der Funktionen, die von den-Editionen unterstützt werden [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , finden Sie [unter von den-Editionen unterstützte Funktionen SQL Server 2012](https://go.microsoft.com/fwlink/?linkid=232473) () https://go.microsoft.com/fwlink/?linkid=232473) .</span><span class="sxs-lookup"><span data-stu-id="250fc-116">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2012](https://go.microsoft.com/fwlink/?linkid=232473) (https://go.microsoft.com/fwlink/?linkid=232473).</span></span>  
  
## <a name="options"></a><span data-ttu-id="250fc-117">Tastatur</span><span class="sxs-lookup"><span data-stu-id="250fc-117">Options</span></span>  
 <span data-ttu-id="250fc-118">**Name**</span><span class="sxs-lookup"><span data-stu-id="250fc-118">**Name**</span></span>  
 <span data-ttu-id="250fc-119">Gibt den Namen des freigegebenen Zeitplans an.</span><span class="sxs-lookup"><span data-stu-id="250fc-119">Specifies the name for the shared schedule.</span></span>  
  
 <span data-ttu-id="250fc-120">**Diesen Zeitplan ausführen ab**</span><span class="sxs-lookup"><span data-stu-id="250fc-120">**Begin running this schedule on**</span></span>  
 <span data-ttu-id="250fc-121">Gibt ein Startdatum für diesen Zeitplan an.</span><span class="sxs-lookup"><span data-stu-id="250fc-121">Specifies a start date for this schedule.</span></span>  
  
 <span data-ttu-id="250fc-122">**Dieser Zeitplan endet am**</span><span class="sxs-lookup"><span data-stu-id="250fc-122">**Stop this schedule on**</span></span>  
 <span data-ttu-id="250fc-123">Gibt ein Ablaufdatum für diesen Zeitplan an.</span><span class="sxs-lookup"><span data-stu-id="250fc-123">Specifies an expiration date for this schedule.</span></span>  
  
 <span data-ttu-id="250fc-124">**Type**</span><span class="sxs-lookup"><span data-stu-id="250fc-124">**Type**</span></span>  
 <span data-ttu-id="250fc-125">Gibt an, ob die Wiederholungsoption hauptsächlich auf Stunden, Tagen, Wochen oder Monaten basiert oder nur einmal ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="250fc-125">Specifies whether the recurrence pattern is based primarily on hours, days, weeks, months, or only runs once.</span></span>  
  
 <span data-ttu-id="250fc-126">**Stunde (Serienmuster)**</span><span class="sxs-lookup"><span data-stu-id="250fc-126">**Hour (Recurrence Pattern)**</span></span>  
 <span data-ttu-id="250fc-127">Gibt die Optionen zum Ausführen eines geplanten Vorgangs in Intervallen von einer Stunde an (z. B., dass ein Bericht alle 6 Stunden ausgeführt wird).</span><span class="sxs-lookup"><span data-stu-id="250fc-127">Specifies options for running a scheduled operation in intervals of an hour (for example, to run a report every 6 hours).</span></span> <span data-ttu-id="250fc-128">Das Intervall kann in Stunden und Minuten angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="250fc-128">You can specify the interval in hours and minutes.</span></span>  
  
 <span data-ttu-id="250fc-129">**Tag (Serienmuster)**</span><span class="sxs-lookup"><span data-stu-id="250fc-129">**Day (Recurrence Pattern)**</span></span>  
 <span data-ttu-id="250fc-130">Gibt die Optionen zum Ausführen eines geplanten Vorgangs in Intervallen von Tagen an (z. B., dass ein Bericht alle 2 Tage ausgeführt wird).</span><span class="sxs-lookup"><span data-stu-id="250fc-130">Specifies options for running a scheduled operation in intervals of days (for example, to run a report every 2 days).</span></span> <span data-ttu-id="250fc-131">Sie können das Intervall in Tagen und mit der Stunde und Minute der Ausführung des Zeitplans angeben.</span><span class="sxs-lookup"><span data-stu-id="250fc-131">You can specify the interval in days and at the hour and minute you want the schedule to run.</span></span>  
  
 <span data-ttu-id="250fc-132">**Woche (Serienmuster)**</span><span class="sxs-lookup"><span data-stu-id="250fc-132">**Week (Recurrence Pattern)**</span></span>  
 <span data-ttu-id="250fc-133">Gibt die Optionen zum Ausführen eines geplanten Vorgangs in Intervallen von einer Woche oder gemäß einem zu wiederholenden Muster an, das auf Wochenangaben basiert (z. B., dass ein Bericht jede zweite Woche ausgeführt wird).</span><span class="sxs-lookup"><span data-stu-id="250fc-133">Specifies options for running a scheduled operation in intervals of a week or when the pattern that you want to repeat is based on weeks (for example, to run a report every other week).</span></span> <span data-ttu-id="250fc-134">Sie können bei einem wöchentlichen Zeitplan den Tag, die Stunde und die Minute für die Ausführung des Zeitplans angeben.</span><span class="sxs-lookup"><span data-stu-id="250fc-134">You can specify a weekly schedule to the day, hour, and minute that you want the schedule to run.</span></span>  
  
 <span data-ttu-id="250fc-135">**Monat (Serienmuster)**</span><span class="sxs-lookup"><span data-stu-id="250fc-135">**Month (Recurrence Pattern)**</span></span>  
 <span data-ttu-id="250fc-136">Gibt die Optionen zum Ausführen eines geplanten Vorgangs in Intervallen von einem Monat oder gemäß einem zu wiederholenden Muster an, das auf Monatsangaben basiert.</span><span class="sxs-lookup"><span data-stu-id="250fc-136">Specifies options for running a scheduled operation in intervals of a month or when the pattern that you want to repeat is based on months.</span></span> <span data-ttu-id="250fc-137">Sie können bei einem monatlichen Zeitplan den Tag, die Stunde und die Minute für die Ausführung des Zeitplans angeben.</span><span class="sxs-lookup"><span data-stu-id="250fc-137">You can specify a monthly schedule to the day, hour, and minute that you want the schedule to run.</span></span> <span data-ttu-id="250fc-138">Sie können im Zeitplan bestimmte Monate auslassen.</span><span class="sxs-lookup"><span data-stu-id="250fc-138">You can omit specific months from the schedule.</span></span>  
  
 <span data-ttu-id="250fc-139">**Einmalig**</span><span class="sxs-lookup"><span data-stu-id="250fc-139">**Once**</span></span>  
 <span data-ttu-id="250fc-140">Gibt einen Zeitplan an, der nur einmal an einem bestimmten Datum und zu einer bestimmten Uhrzeit ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="250fc-140">Specifies a schedule that runs only once, on a specific date and time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="250fc-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="250fc-141">See Also</span></span>  
 <span data-ttu-id="250fc-142">[Berichts Server in Management Studio F1-Hilfe](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="250fc-142">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 <span data-ttu-id="250fc-143">[Herstellen einer Verbindung mit einem Berichts Server in Management Studio](connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="250fc-143">[Connect to a Report Server in Management Studio](connect-to-a-report-server-in-management-studio.md) </span></span>  
 <span data-ttu-id="250fc-144">[Erstellen, Ändern oder Löschen von Zeitplänen](../subscriptions/create-modify-and-delete-schedules.md) </span><span class="sxs-lookup"><span data-stu-id="250fc-144">[Create, Modify, and Delete Schedules](../subscriptions/create-modify-and-delete-schedules.md) </span></span>  
 [<span data-ttu-id="250fc-145">Zeitpläne</span><span class="sxs-lookup"><span data-stu-id="250fc-145">Schedules</span></span>](../subscriptions/schedules.md)  
  
  
