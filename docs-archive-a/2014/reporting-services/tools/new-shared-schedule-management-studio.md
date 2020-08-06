---
title: Neuer freigegebener Zeitplan (Management Studio) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.newschedule.f1
ms.assetid: b2c69586-d98e-4933-827d-f5e6c15c5203
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c6afd406730f815d3ab61e59cdebd21d564daa74
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615796"
---
# <a name="new-shared-schedule-management-studio"></a><span data-ttu-id="1e13f-102">Neuer freigegebener Zeitplan (Management Studio)</span><span class="sxs-lookup"><span data-stu-id="1e13f-102">New Shared Schedule (Management Studio)</span></span>
  <span data-ttu-id="1e13f-103">Mithilfe dieser Seite können Sie einen freigegebenen Zeitplan zur Ausführung veröffentlichter Berichte und Abonnements erstellen.</span><span class="sxs-lookup"><span data-stu-id="1e13f-103">Use this page to create a shared schedule to run published reports and subscriptions.</span></span> <span data-ttu-id="1e13f-104">Feigegebene Zeitpläne können anstelle berichts- oder abonnementspezifischer Zeitpläne verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1e13f-104">Shared schedules can be used in place of report-specific or subscription-specific schedules.</span></span> <span data-ttu-id="1e13f-105">Zentralisierte Zeitplaninformationen und die Möglichkeit, geplante Vorgänge anhalten und fortsetzen zu können, sind zwei Schlüsselfunktionen, die freigegebene Zeitpläne von elementspezifischen Zeitplänen unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="1e13f-105">Centralized schedule information and the ability to pause and resume scheduled operations are two key features that distinguish shared schedules from item-specific schedules.</span></span>  
  
 <span data-ttu-id="1e13f-106">Nicht alle Kombinationen der Häufigkeit können in einem einzelnen Zeitplan unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="1e13f-106">Not all frequency combinations can be supported in a single schedule.</span></span> <span data-ttu-id="1e13f-107">Wenn ein Bericht z. B. um 00:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="1e13f-107">For example, if you want to run a report at 12:00 P.M.</span></span> <span data-ttu-id="1e13f-108">und um 16:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="1e13f-108">and 4:00 P.M.</span></span> <span data-ttu-id="1e13f-109">an jedem Freitag ausgeführt werden soll, müssen Sie zwei Tageszeitpläne erstellen, in denen der Freitag als Ausführungstag angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="1e13f-109">every Friday, you must create two daily schedules that specify a Friday run date, one with a start time of 12:00 P.M.</span></span> <span data-ttu-id="1e13f-110">Der erste Zeitplan hat eine Startzeit von 00:00 Uhr, und für den zweiten ist eine Startzeit von 16:00 Uhr festgelegt.</span><span class="sxs-lookup"><span data-stu-id="1e13f-110">and another with a start time of 4:00 P.M.</span></span>  
  
 <span data-ttu-id="1e13f-111">Die Verarbeitung von Zeitplänen basiert auf der Ortszeit des Berichtsservers, auf dem der Zeitplan gehostet und verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="1e13f-111">Schedule processing is based on the local time of the report server that hosts and processes the schedule.</span></span>  
  
 <span data-ttu-id="1e13f-112">Öffnen Sie diese Seite, indem Sie [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]starten und eine Verbindung mit einem Berichtsserver herstellen. Klicken Sie mit der rechten Maustaste auf **Freigegebener Zeitplan**, und wählen Sie dann **Neuer Zeitplan**aus.</span><span class="sxs-lookup"><span data-stu-id="1e13f-112">To open this page, start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to a report server, right-click **Shared Schedule**, and select **New Schedule**.</span></span> <span data-ttu-id="1e13f-113">Um den Zeitplan zu speichern, muss der SQL Server-Agent-Dienst ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1e13f-113">To save the schedule, SQL Server Agent service must be running.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1e13f-114">Diese Funktion ist nicht in jeder Edition von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1e13f-114">This feature is not available in every edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="1e13f-115">Eine Liste der Funktionen, die von den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Editionen unterstützt werden, finden Sie unter [Von den SQL Server 2012-Editionen unterstützte Funktionen](https://go.microsoft.com/fwlink/?linkid=232473) (https://go.microsoft.com/fwlink/?linkid=232473).</span><span class="sxs-lookup"><span data-stu-id="1e13f-115">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2012](https://go.microsoft.com/fwlink/?linkid=232473) (https://go.microsoft.com/fwlink/?linkid=232473).</span></span>  
  
## <a name="options"></a><span data-ttu-id="1e13f-116">Tastatur</span><span class="sxs-lookup"><span data-stu-id="1e13f-116">Options</span></span>  
 <span data-ttu-id="1e13f-117">**Name**</span><span class="sxs-lookup"><span data-stu-id="1e13f-117">**Name**</span></span>  
 <span data-ttu-id="1e13f-118">Geben Sie einen Namen für den freigegebenen Zeitplan ein.</span><span class="sxs-lookup"><span data-stu-id="1e13f-118">Type a name for the shared schedule.</span></span> <span data-ttu-id="1e13f-119">Dieser Name wird in Dropdownlisten angezeigt, wenn Benutzer einen freigegebenen Zeitplan für Berichte und Abonnements auswählen.</span><span class="sxs-lookup"><span data-stu-id="1e13f-119">This name appears in drop-down lists when users select a shared schedule for reports and subscriptions.</span></span> <span data-ttu-id="1e13f-120">Stellen Sie sicher, dass Sie einen aussagekräftigen Namen angeben, der in eine Liste passt und den freigegebenen Zeitplan gut von einem anderen unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="1e13f-120">Be sure to provide a descriptive name that fits easily within a list and that easily distinguishes one shared schedule from another.</span></span> <span data-ttu-id="1e13f-121">Der Name muss mindestens ein alphanumerisches Zeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="1e13f-121">A name must contain at least one alphanumeric character.</span></span> <span data-ttu-id="1e13f-122">Er kann auch Leerzeichen und Sonderzeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="1e13f-122">It can also include spaces and some symbols.</span></span> <span data-ttu-id="1e13f-123">Folgende Zeichen können beim Angeben eines Namens nicht verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="1e13f-123">Do not use the following characters when specifying a name:</span></span>  
  
 <span data-ttu-id="1e13f-124">; ?</span><span class="sxs-lookup"><span data-stu-id="1e13f-124">; ?</span></span> <span data-ttu-id="1e13f-125">: \@ & = +, $/\*\< ></span><span class="sxs-lookup"><span data-stu-id="1e13f-125">: \@ & = + , $ / \* \< ></span></span>  
  
 <span data-ttu-id="1e13f-126">" /</span><span class="sxs-lookup"><span data-stu-id="1e13f-126">" /</span></span>  
  
 <span data-ttu-id="1e13f-127">**Diesen Zeitplan ausführen ab**</span><span class="sxs-lookup"><span data-stu-id="1e13f-127">**Begin running this schedule on**</span></span>  
 <span data-ttu-id="1e13f-128">Geben Sie ein Startdatum für diesen Zeitplan an.</span><span class="sxs-lookup"><span data-stu-id="1e13f-128">Specify a start date for this schedule.</span></span>  
  
 <span data-ttu-id="1e13f-129">**Dieser Zeitplan endet am**</span><span class="sxs-lookup"><span data-stu-id="1e13f-129">**Stop this schedule on**</span></span>  
 <span data-ttu-id="1e13f-130">Geben Sie ein Ablaufdatum für diesen Zeitplan an.</span><span class="sxs-lookup"><span data-stu-id="1e13f-130">Specify an expiration date for this schedule.</span></span>  
  
 <span data-ttu-id="1e13f-131">**Typ**</span><span class="sxs-lookup"><span data-stu-id="1e13f-131">**Type**</span></span>  
 <span data-ttu-id="1e13f-132">Gibt an, ob die Wiederholungsoption hauptsächlich auf Stunden, Tagen, Wochen oder Monaten basiert.</span><span class="sxs-lookup"><span data-stu-id="1e13f-132">Specifies whether the recurrence pattern is based primarily on hours, days, weeks, or months.</span></span>  
  
 <span data-ttu-id="1e13f-133">**Stunde (Serienmuster)**</span><span class="sxs-lookup"><span data-stu-id="1e13f-133">**Hour (Recurrence Pattern)**</span></span>  
 <span data-ttu-id="1e13f-134">Wählen Sie Optionen für die Ausführung eines geplanten Vorgangs in Stundenintervallen aus (um einen Bericht z. B. alle 6 Stunden auszuführen).</span><span class="sxs-lookup"><span data-stu-id="1e13f-134">Select options to run a scheduled operation in intervals of an hour (for example, to run a report every 6 hours).</span></span> <span data-ttu-id="1e13f-135">Das Intervall kann in Stunden und Minuten angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1e13f-135">You can specify the interval in hours and minutes.</span></span>  
  
 <span data-ttu-id="1e13f-136">**Tag (Serienmuster)**</span><span class="sxs-lookup"><span data-stu-id="1e13f-136">**Day (Recurrence Pattern)**</span></span>  
 <span data-ttu-id="1e13f-137">Wählen Sie Optionen für die Ausführung eines geplanten Vorgangs in Tagesintervallen aus (um einen Bericht z. B. alle 2 Tage auszuführen).</span><span class="sxs-lookup"><span data-stu-id="1e13f-137">Select options to run a scheduled operation in intervals of days (for example, to run a report every 2 days).</span></span> <span data-ttu-id="1e13f-138">Sie können das Intervall in Tagen und mit der Stunde und Minute der Ausführung des Zeitplans angeben.</span><span class="sxs-lookup"><span data-stu-id="1e13f-138">You can specify the interval in days and at the hour and minute you want the schedule to run.</span></span>  
  
 <span data-ttu-id="1e13f-139">**Woche (Serienmuster)**</span><span class="sxs-lookup"><span data-stu-id="1e13f-139">**Week (Recurrence Pattern)**</span></span>  
 <span data-ttu-id="1e13f-140">Wählen Sie Optionen für die Ausführung eines geplanten Vorgangs in Wochenintervallen aus. Dies gilt auch für den Fall, dass das zu wiederholende Muster auf Wochen basiert (wenn Sie einen Bericht z. B. jede zweite Woche ausführen wollen).</span><span class="sxs-lookup"><span data-stu-id="1e13f-140">Select options to run a scheduled operation in intervals of a week or when the pattern that you want to repeat is based on weeks (for example, to run a report every other week).</span></span> <span data-ttu-id="1e13f-141">Sie können bei einem wöchentlichen Zeitplan den Tag, die Stunde und die Minute für die Ausführung des Zeitplans angeben.</span><span class="sxs-lookup"><span data-stu-id="1e13f-141">You can specify a weekly schedule to the day, hour, and minute that you want the schedule to run.</span></span>  
  
 <span data-ttu-id="1e13f-142">**Monat (Serienmuster)**</span><span class="sxs-lookup"><span data-stu-id="1e13f-142">**Month (Recurrence Pattern)**</span></span>  
 <span data-ttu-id="1e13f-143">Wählen Sie Optionen für die Ausführung eines geplanten Vorgangs in Monatsintervallen aus. Dies gilt auch für den Fall, dass das zu wiederholende Muster auf Monaten basiert.</span><span class="sxs-lookup"><span data-stu-id="1e13f-143">Select options to run a scheduled operation in intervals of a month or when the pattern that you want to repeat is based on months.</span></span> <span data-ttu-id="1e13f-144">Sie können bei einem monatlichen Zeitplan den Tag, die Stunde und die Minute für die Ausführung des Zeitplans angeben.</span><span class="sxs-lookup"><span data-stu-id="1e13f-144">You can specify a monthly schedule to the day, hour, and minute that you want the schedule to run.</span></span> <span data-ttu-id="1e13f-145">Sie können im Zeitplan bestimmte Monate auslassen.</span><span class="sxs-lookup"><span data-stu-id="1e13f-145">You can omit specific months from the schedule.</span></span>  
  
 <span data-ttu-id="1e13f-146">**Einmal**</span><span class="sxs-lookup"><span data-stu-id="1e13f-146">**Once**</span></span>  
 <span data-ttu-id="1e13f-147">Wählen Sie diese Option aus, um einen Zeitplan zu erstellen, der zu einem bestimmten Termin einmal ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1e13f-147">Select this option to create a schedule that runs only once, on a specific date and time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e13f-148">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1e13f-148">See Also</span></span>  
 <span data-ttu-id="1e13f-149">[Berichtsserver im Management Studio (F1-Hilfe)](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="1e13f-149">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 <span data-ttu-id="1e13f-150">[Vorgehensweise: Herstellen einer Verbindung mit einem Berichtsserver in Management Studio](connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="1e13f-150">[Connect to a Report Server in Management Studio](connect-to-a-report-server-in-management-studio.md) </span></span>  
 <span data-ttu-id="1e13f-151">[Erstellen, Ändern oder Löschen von Zeitplänen](../subscriptions/create-modify-and-delete-schedules.md) </span><span class="sxs-lookup"><span data-stu-id="1e13f-151">[Create, Modify, and Delete Schedules](../subscriptions/create-modify-and-delete-schedules.md) </span></span>  
 <span data-ttu-id="1e13f-152">[Zeitpläne](../subscriptions/schedules.md) </span><span class="sxs-lookup"><span data-stu-id="1e13f-152">[Schedules](../subscriptions/schedules.md) </span></span>  
 [<span data-ttu-id="1e13f-153">Berichtsserver im Management Studio (F1-Hilfe)</span><span class="sxs-lookup"><span data-stu-id="1e13f-153">Report Server in Management Studio F1 Help</span></span>](report-server-in-management-studio-f1-help.md)  
  
  
