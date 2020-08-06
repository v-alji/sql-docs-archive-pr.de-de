---
title: Erstellen einer Sitzung für erweiterte Ereignisse mithilfe des Assistenten (Objekt-Explorer) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- Sql12.ssms.XeWizard.Summary.f1
- Sql12.ssms.XeWizard.SetSessionProperties.f1
- Sql12.ssms.XeWizard.CaptureAddFields.f1
- Sql12.ssms.XeWizard.SelectEvents.f1
- Sql12.ssms.XeWizard.SpecifySessionTargets.f1
- Sql12.ssms.XeWizard.Welcome.f1
- sql12.ssms.XeWizard.Welcome.f1
- Sql12.ssms.XeWizard.ChooseTemplate.f1
- Sql12.ssms.XeWizard.SetSessionEventFilters.f1
- Sql12.ssms.XeWizard.Results.f1
helpviewer_keywords:
- Sql11.ssms.XeWizard.CaptureAddFields.f1
- Sql11.ssms.XeWizard.SetSessionEventFilters.f1
- Sql11.ssms.XeWizard.SpecifySessionTargets.f1
- Sql11.ssms.XeWizard.Results.f1
- Sql11.ssms.XeWizard.ChooseTemplate.f1
- Sql11.ssms.XeWizard.SetSessionProperties.f1
- Sql11.ssms.XeWizard.Welcome.f1
- Sql11.ssms.XeWizard.Summary.f1
- Sql11.ssms.XeWizard.SelectEvents.f1
ms.assetid: 80c0456f-17c0-41d8-b2aa-502a2f3bb6de
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: cdfc9141b0b99d5b06fc73044b8f4fae623922b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618254"
---
# <a name="create-an-extended-events-session-using-the-wizard-object-explorer"></a><span data-ttu-id="359de-102">Erstellen einer Sitzung für erweiterte Ereignisse mithilfe des Assistenten (Objekt-Explorer)</span><span class="sxs-lookup"><span data-stu-id="359de-102">Create an Extended Events Session Using the Wizard (Object Explorer)</span></span>
  <span data-ttu-id="359de-103">Um Ihnen bei der Auswahl und Aufzeichnung von Ereignissen auf dem Server behilflich zu sein, umfasst Erweiterte Ereignisse einen Assistenten für neue Sitzungen, der Sie durch die Schritte der Erstellung einer Sitzung für erweiterte Ereignisse führt.</span><span class="sxs-lookup"><span data-stu-id="359de-103">To help you select and capture events on your server, Extended Events includes a New Session Wizard that guides you through the steps to create an Extended Events session.</span></span> <span data-ttu-id="359de-104">Mit dem Assistenten für neue Sitzungen die meisten Funktionen erweiterter Ereignisse angezeigt.</span><span class="sxs-lookup"><span data-stu-id="359de-104">The New Session Wizard exposes most of the Extended Events functionality.</span></span> <span data-ttu-id="359de-105">Mit dem Dialogfeld [Neue Sitzung](../../2014/database-engine/create-an-extended-events-session-using-the-new-session-dialog.md) können Sie zudem eine Sitzung für erweiterte Ereignisse definieren, die Ihre Daten erfasst, anzeigt und analysiert.</span><span class="sxs-lookup"><span data-stu-id="359de-105">The [New Session dialog](../../2014/database-engine/create-an-extended-events-session-using-the-new-session-dialog.md) also lets you define an Extended Events session that captures, displays, and analyzes your data.</span></span> <span data-ttu-id="359de-106">Mit dem Dialogfeld "Neue Sitzung" werden alle Funktionen erweiterter Ereignisse angezeigt.</span><span class="sxs-lookup"><span data-stu-id="359de-106">The New Session dialog exposes all Extended Events functionality.</span></span>  
  
### <a name="to-open-the-new-session-wizard"></a><span data-ttu-id="359de-107">So öffnen Sie den Assistenten für neue Sitzungen</span><span class="sxs-lookup"><span data-stu-id="359de-107">To open the New Session Wizard</span></span>  
  
1.  <span data-ttu-id="359de-108">Erweitern Sie im Objekt-Explorer den Knoten **Verwaltung** , und erweitern Sie dann **Erweiterte Ereignisse**.</span><span class="sxs-lookup"><span data-stu-id="359de-108">In Object Explorer, expand the **Management** node, and then expand **Extended Events**.</span></span>  
  
2.  <span data-ttu-id="359de-109">Klicken Sie mit der rechten Maustaste auf **Sitzungen**, und klicken Sie dann auf **Assistent für neue Sitzungen**.</span><span class="sxs-lookup"><span data-stu-id="359de-109">Right-click **Sessions**, and then click **New Session Wizard**.</span></span>  
  
### <a name="use-the-following-new-session-wizard-pages-to-create-an-event-session"></a><span data-ttu-id="359de-110">Verwenden der folgenden Seiten des Assistenten für neue Sitzungen zum Erstellen einer Ereignissitzung</span><span class="sxs-lookup"><span data-stu-id="359de-110">Use the following New Session Wizard pages to create an event session</span></span>  
  
-   [<span data-ttu-id="359de-111">Einführung</span><span class="sxs-lookup"><span data-stu-id="359de-111">Introduction</span></span>](#BKMK_Welcome)  
  
-   [<span data-ttu-id="359de-112">Festlegen von Sitzungseigenschaften</span><span class="sxs-lookup"><span data-stu-id="359de-112">Set Session Properties</span></span>](#BKMK_SetSessionProperties)  
  
-   [<span data-ttu-id="359de-113">Auswählen einer Vorlage</span><span class="sxs-lookup"><span data-stu-id="359de-113">Choose Template</span></span>](#BKMK_ChooseTemplate)  
  
-   [<span data-ttu-id="359de-114">Auswählen von Ereignissen für die Aufzeichnung</span><span class="sxs-lookup"><span data-stu-id="359de-114">Select Events to Capture</span></span>](#BKMK_SelectEventsToCapture)  
  
-   [<span data-ttu-id="359de-115">Aufzeichnen von globalen Feldern</span><span class="sxs-lookup"><span data-stu-id="359de-115">Capture Global Fields</span></span>](#BKMK_CaptureGlobalFields)  
  
-   [<span data-ttu-id="359de-116">Festlegen von Filtern für Sitzungsereignisse</span><span class="sxs-lookup"><span data-stu-id="359de-116">Set Session Event Filters</span></span>](#BKMK_SetSessionEventFilters)  
  
-   [<span data-ttu-id="359de-117">Angeben des Sitzungsdatenspeichers</span><span class="sxs-lookup"><span data-stu-id="359de-117">Specify Session Data Storage</span></span>](#BKMK_SpecifySessionDataOutput)  
  
-   [<span data-ttu-id="359de-118">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="359de-118">Summary</span></span>](#BKMK_Summary)  
  
-   [<span data-ttu-id="359de-119">Erstellen einer Ereignissitzung</span><span class="sxs-lookup"><span data-stu-id="359de-119">Create Event Session</span></span>](#BKMK_CreateEventSession)  
  
##  <a name="introduction"></a><a name="BKMK_Welcome"></a><span data-ttu-id="359de-120">Einführung</span><span class="sxs-lookup"><span data-stu-id="359de-120">Introduction</span></span>  
 <span data-ttu-id="359de-121">Gehen Sie auf der Seite **Einführung** wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="359de-121">On the **Introduction** page, do the following:</span></span>  
  
-   <span data-ttu-id="359de-122">Klicken Sie auf der Seite **Einführung** des Assistenten für neue Sitzungen auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="359de-122">On the **Introduction** page of the New Session Wizard, click **Next**.</span></span>  
  
     <span data-ttu-id="359de-123">Aktivieren Sie das Kontrollkästchen **Diese Seite nicht mehr anzeigen**, wenn Sie den Assistenten mehrmals verwenden werden und nicht bei jedem Start des Assistenten die Einführung lesen möchten.</span><span class="sxs-lookup"><span data-stu-id="359de-123">Select the **Do not show this page again** check box if you will be using the wizard more than once and do not want to read the introduction each time the wizard is launched.</span></span>  
  
##  <a name="set-session-properties"></a><a name="BKMK_SetSessionProperties"></a><span data-ttu-id="359de-124">Festlegen von Sitzungs Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="359de-124">Set Session Properties</span></span>  
 <span data-ttu-id="359de-125">Geben Sie auf der Seite **Sitzungseigenschaften festlegen** die folgenden Werte ein:</span><span class="sxs-lookup"><span data-stu-id="359de-125">On the **Set Session Properties** page, do the following:</span></span>  
  
-   <span data-ttu-id="359de-126">Geben Sie im Feld **Sitzungsname** einen aussagekräftigen Namen für die Ereignissitzung ein.</span><span class="sxs-lookup"><span data-stu-id="359de-126">In the **Session name** box, type a meaningful name for the event session.</span></span>  
  
     <span data-ttu-id="359de-127">Wenn Sie möchten, dass die Sitzung gestartet wird, wenn Sie den Server starten, aktivieren Sie das Kontrollkästchen **Ereignissitzung beim Serverstart starten** , und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="359de-127">If you want to start the session when you start the server, select the **Start the event session at server startup** check box, and then click **Next**.</span></span>  
  
##  <a name="choose-template"></a><a name="BKMK_ChooseTemplate"></a><span data-ttu-id="359de-128">Vorlage auswählen</span><span class="sxs-lookup"><span data-stu-id="359de-128">Choose Template</span></span>  
 <span data-ttu-id="359de-129">Führen Sie auf der Seite **Vorlage auswählen** die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="359de-129">On the **Choose Template** page, do the following:</span></span>  
  
-   <span data-ttu-id="359de-130">Aktivieren Sie die Option **Diese Ereignissitzungsvorlage verwenden** , um aus einem Satz vorkonfigurierter Vorlagen für häufig auftretende Probleme eine Auswahl zu treffen.</span><span class="sxs-lookup"><span data-stu-id="359de-130">Select the **Use this event session template** option to select from a set of pre-configured templates designed for common problems.</span></span> <span data-ttu-id="359de-131">Wählen Sie die gewünschte Vorlage aus der Dropdownliste aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="359de-131">Select the template you want to use from the drop-down list, and then click **Next**.</span></span>  
  
     <span data-ttu-id="359de-132">ODER</span><span class="sxs-lookup"><span data-stu-id="359de-132">-OR-</span></span>  
  
-   <span data-ttu-id="359de-133">Aktivieren Sie die Option **Keine Vorlage verwenden** , wenn Sie keine vorkonfigurierte Vorlage verwenden möchten, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="359de-133">Select the **Do not use a template** option if you do not want to use any pre-configured template, and then click **Next**.</span></span>  
  
##  <a name="select-events-to-capture"></a><a name="BKMK_SelectEventsToCapture"></a><span data-ttu-id="359de-134">Ereignisse für die Erfassung auswählen</span><span class="sxs-lookup"><span data-stu-id="359de-134">Select Events to Capture</span></span>  
 <span data-ttu-id="359de-135">Gehen Sie auf der Seite **Aufzuzeichnende Ereignisse auswählen** wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="359de-135">On the **Select Events to Capture** page, do the following:</span></span>  
  
1.  <span data-ttu-id="359de-136">Wählen Sie die Ereignisse, die Sie aufzeichnen möchten, aus der **Ereignisbibliothek**aus, und klicken Sie auf den Pfeil nach rechts.</span><span class="sxs-lookup"><span data-stu-id="359de-136">Select the events you want to capture from the **Event library**, and then click the right arrow.</span></span> <span data-ttu-id="359de-137">Durch UMSCHALT+Klicken oder STRG+Klicken können Sie mehrere Ereignisse in der Ereignisbibliothek auswählen.</span><span class="sxs-lookup"><span data-stu-id="359de-137">You can select multiple events in the Event Library by using either Shift+Click or Ctrl+Click.</span></span>  
  
     <span data-ttu-id="359de-138">Sie können in der Dropdownliste auswählen, wie nach den Ereignissen gesucht werden soll, die Sie aufzeichnen möchten.</span><span class="sxs-lookup"><span data-stu-id="359de-138">You can select how you want to search for the events you want to capture from the drop-down list box.</span></span> <span data-ttu-id="359de-139">Sie können beispielsweise nach Ereignisnamen oder Ereignisnamen und ihren Beschreibungen suchen.</span><span class="sxs-lookup"><span data-stu-id="359de-139">For example, you can search for event names or event names and their descriptions.</span></span> <span data-ttu-id="359de-140">Sie können in der Tabelle nach einem beliebigen Wort suchen, indem Sie im Feld **Ereignisbibliothek** den Text eingeben, den Sie suchen möchten.</span><span class="sxs-lookup"><span data-stu-id="359de-140">You can search for any word in the table by entering the text you want to search for in the **Event library** box.</span></span> <span data-ttu-id="359de-141">Wenn Sie z. b. das **lock_acquired** Ereignis suchen möchten, können Sie **Lock**oder **Lock Lock**eingeben.</span><span class="sxs-lookup"><span data-stu-id="359de-141">For example, if you want to find the **lock_acquired** event, you can enter **lock**, or **lock acquire**.</span></span>  
  
     <span data-ttu-id="359de-142">Die Ereignisse, die Sie auswählen, werden im Feld **Ausgewählte Ereignisse** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="359de-142">The events you select appear in the **Selected events** box.</span></span> <span data-ttu-id="359de-143">Um Ereignisse aus dem Feld **Ausgewählte Ereignisse** zu entfernen, klicken Sie auf die NACH-LINKS-TASTE.</span><span class="sxs-lookup"><span data-stu-id="359de-143">To remove events from the **Selected events** box, click the left arrow.</span></span>  
  
2.  <span data-ttu-id="359de-144">Nachdem Sie die Ereignisse ausgewählt haben, die Sie aufzeichnen möchten, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="359de-144">After you select the events you want to capture, click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="359de-145">Ereignisse aus dem Kanal **Debuggen** sind standardmäßig ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="359de-145">Events from the **Debug** channel are hidden by default.</span></span> <span data-ttu-id="359de-146">Um Debugereignisse anzuzeigen, wählen Sie **Debuggen** aus der Dropdownliste **Kanal** aus.</span><span class="sxs-lookup"><span data-stu-id="359de-146">To display debug events, select **Debug** from the **Channel** drop-down list.</span></span>  
  
##  <a name="capture-global-fields"></a><a name="BKMK_CaptureGlobalFields"></a><span data-ttu-id="359de-147">Globale Felder erfassen</span><span class="sxs-lookup"><span data-stu-id="359de-147">Capture Global Fields</span></span>  
 <span data-ttu-id="359de-148">Globale Felder (auch als Aktionen bezeichnet) werden verwendet, um einzelne oder mehrere Aktionen für die ausgewählten Ereignisse zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="359de-148">You use global fields (also referred to as actions) to associate single or multiple actions for your selected events.</span></span> <span data-ttu-id="359de-149">Wenn Sie auf der Seite **Vorlage auswählen** eine Vorlage auswählten, werden alle globalen Felder, die in der Vorlage definiert sind, auf dieser Seite angezeigt.</span><span class="sxs-lookup"><span data-stu-id="359de-149">If you selected a template on the **Choose Template** page, all of the global fields that are defined in the template are displayed on this page.</span></span>  
  
 <span data-ttu-id="359de-150">Gehen Sie auf der Seite **Globale Felder aufzeichnen** wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="359de-150">On the **Capture Global Fields** page, do the following:</span></span>  
  
-   <span data-ttu-id="359de-151">Wählen Sie die globalen Felder aus, die Sie für die Ereignissitzung aufzeichnen möchten, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="359de-151">Select the global fields that you want to capture for the event session, and then click **Next**.</span></span>  
  
     <span data-ttu-id="359de-152">Sie können globale Felder hinzufügen oder entfernen, indem Sie das Kontrollkästchen neben dem globalen Feld aktivieren bzw. deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="359de-152">You can remove or add global fields by selecting or clearing the check box next to the global field.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="359de-153">Die ausgewählten Aktionen werden nach **Namen** sortiert, sodass Sie die Möglichkeit haben, die zugeordneten Aktionen in alphabetischer Reihenfolge anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="359de-153">The selected actions are sorted by **Name** enabling you to view the associated actions in alphabetical order.</span></span> <span data-ttu-id="359de-154">Sie können nach auch nach Beschreibung oder dem Aktivierungs-/Deaktivierungsstatus sortieren, indem Sie auf die Spaltenüberschrift neben dem Feldnamen klicken.</span><span class="sxs-lookup"><span data-stu-id="359de-154">You can sort by description or by the enable/disable status by clicking the column heading next to the field name.</span></span>  
  
##  <a name="set-session-event-filters"></a><a name="BKMK_SetSessionEventFilters"></a><span data-ttu-id="359de-155">Festlegen von Sitzungs Ereignis filtern</span><span class="sxs-lookup"><span data-stu-id="359de-155">Set Session Event Filters</span></span>  
 <span data-ttu-id="359de-156">Sie können Filter (auch als Prädikate bezeichnet) anwenden, um die Ereignisse, die Sie aufzeichnen möchten, einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="359de-156">You can apply filters (also called predicates) to limit the events that you want to capture.</span></span> <span data-ttu-id="359de-157">Gehen Sie auf der Seite **Filter für Sitzungsereignisse festlegen** wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="359de-157">On the **Set Session Event Filters** page, do the following:</span></span>  
  
1.  <span data-ttu-id="359de-158">Wenn Sie keine vorkonfigurierte Vorlage verwenden, erstellen die Filterkriterien, und klicken dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="359de-158">If you are not using a pre-configured template, create your filter criteria, and then click **Next**.</span></span>  
  
     <span data-ttu-id="359de-159">Wenn Sie eine vorkonfigurierte Vorlage verwenden, werden im Abschnitt **Filter aus Vorlage (schreibgeschützt)** vom Assistenten für neue Sitzungen bereits aus der Vorlage erstellte Filter aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="359de-159">If you are using a pre-configured template, in the **Filters from template (read-only)** section, the New Session Wizard lists filters already created from the template.</span></span>  
  
2.  <span data-ttu-id="359de-160">Im Abschnitt **Zusätzliche Filter** können Sie zusätzliche Filter für die Ereignissitzung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="359de-160">In the **Additional filters** section, you can configure additional filters for the event session.</span></span>  
  
     <span data-ttu-id="359de-161">Die Filter, die Sie konfigurieren, gelten für alle ausgewählten Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="359de-161">The filters you configure apply to all selected events.</span></span> <span data-ttu-id="359de-162">Vom Assistenten für neue Sitzungen wird das Konfigurieren von Filtern für jedes einzelne Ereignis nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="359de-162">The New Session Wizard does not support configuring filters for each event.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="359de-163">Wenn Sie eine Gruppenklausel für den Filter konfigurieren, werden redundante Klammern aus dem Filter entfernt, nachdem das Ergebnis gespeichert wurde.</span><span class="sxs-lookup"><span data-stu-id="359de-163">When you configure a group clause for your filter, redundant parentheses are removed from the filter after the result is saved.</span></span> <span data-ttu-id="359de-164">Wenn Sie z. B. einen Filter erstellen, der **Klausel 1** und **Klausel 2**gruppiert, werden Klammern um die Klauseln angezeigt.</span><span class="sxs-lookup"><span data-stu-id="359de-164">For example, if you create a filter grouping **Clause 1** and **Clause 2**, parentheses will appear around the clauses.</span></span> <span data-ttu-id="359de-165">Nachdem Sie den Filter gespeichert haben, werden die redundanten Klammern entfernt.</span><span class="sxs-lookup"><span data-stu-id="359de-165">After you save the filter, the redundant parentheses are removed.</span></span> <span data-ttu-id="359de-166">Das Entfernen der Klammern hat keine Auswirkungen auf die Filterlogik.</span><span class="sxs-lookup"><span data-stu-id="359de-166">The removal of the parentheses does not affect the filter logic.</span></span>  
  
##  <a name="specify-session-data-storage"></a><a name="BKMK_SpecifySessionDataOutput"></a><span data-ttu-id="359de-167">Angeben des Sitzungsdaten Speichers</span><span class="sxs-lookup"><span data-stu-id="359de-167">Specify Session Data Storage</span></span>  
 <span data-ttu-id="359de-168">Auf der Seite **Sitzungsdatenspeicher angeben** geben Sie an, wie Daten für die Analyse erfasst werden sollen.</span><span class="sxs-lookup"><span data-stu-id="359de-168">You use the **Specify Session Data Storage** page to specify how you want to collect your data for analysis.</span></span> <span data-ttu-id="359de-169">SQL Server Erweiterte Ereignisse verwendet Ziele für die Datenausgabe.</span><span class="sxs-lookup"><span data-stu-id="359de-169">SQL Server Extended Events uses targets for data output.</span></span> <span data-ttu-id="359de-170">Ziele speichern Ereignisdaten und können Aktionen, wie z. B. das Schreiben in eine Datei und das Aggregieren von Ereignisdaten, ausführen.</span><span class="sxs-lookup"><span data-stu-id="359de-170">Targets store event data and can perform actions such as writing to a file and aggregating event data.</span></span> <span data-ttu-id="359de-171">Überlegen Sie sich, wie Sie die Daten für die Analyse erfassen möchten, und gehen Sie auf der Seite **Sitzungsdatenspeicher angeben** folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="359de-171">Decide how you want to collect your data for analysis, and on the **Specify Session Data Storage** page, do the following:</span></span>  
  
1.  <span data-ttu-id="359de-172">Bei großen Datasets und beim Erstellen von historischen Datensätzen aktivieren Sie das Kontrollkästchen **Daten zur späteren Analyse in einer Datei speichern** , und gehen Sie dann wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="359de-172">For large data sets and creating historical records, select the **Save data to a file for later analysis** check box, and then do the following:</span></span>  
  
    1.  <span data-ttu-id="359de-173">Geben Sie im Feld **Dateiname auf Server** den Pfad und den Dateinamen ein, oder klicken Sie auf **Durchsuchen** , um das Dateiverzeichnis, in dem Sie die Daten speichern möchten, auf dem Server anzugeben.</span><span class="sxs-lookup"><span data-stu-id="359de-173">In the **File name on server** box, enter the path and file name, or click **Browse** to specify the file directory on the server where you want to save the data.</span></span>  
  
    2.  <span data-ttu-id="359de-174">Aktivieren Sie das Kontrollkästchen **Maximale Dateigröße** , und geben Sie die maximale Dateigröße für die Zieldatei an.</span><span class="sxs-lookup"><span data-stu-id="359de-174">In the **Maximum file size** box, specify the maximum file size to be used for the file target.</span></span> <span data-ttu-id="359de-175">Wenn Sie keine maximale Dateigröße angeben, wird die Datei immer größer, bis der Speicherplatz auf dem Datenträger erschöpft ist.</span><span class="sxs-lookup"><span data-stu-id="359de-175">If you do not specify the maximum file size, the file will grow until the disk is full.</span></span> <span data-ttu-id="359de-176">Die Standarddateigröße beträgt 1 Gigabyte (GB).</span><span class="sxs-lookup"><span data-stu-id="359de-176">The default file size is 1 gigabyte (GB).</span></span>  
  
    3.  <span data-ttu-id="359de-177">Aktivieren Sie das Kontrollkästchen **Dateirollover aktivieren** , um Dateirollover für das Dateiziel zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="359de-177">Select the **Enable file rollover** check box to enable file rollover for the file target.</span></span>  
  
    4.  <span data-ttu-id="359de-178">Geben Sie im Feld **Maximale Anzahl von Dateien** die maximale Anzahl von Dateien an, die Sie im Dateisystem beibehalten möchten.</span><span class="sxs-lookup"><span data-stu-id="359de-178">In the **Maximum number of files** box, specify the maximum number of files you want to retain in the file system.</span></span>  
  
2.  <span data-ttu-id="359de-179">Aktivieren Sie zum Erfassen der neuesten Daten das Kontrollkästchen **Nur die neuesten Daten verwenden (ring_buffer-Ziel)** , und gehen Sie dann wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="359de-179">For collecting recent data, select the **Work with only the most recent data (ring buffer target)** check box, and then do the following:</span></span>  
  
    1.  <span data-ttu-id="359de-180">Im Feld **Anzahl beizubehaltender Ereignisse** geben Sie mithilfe der NACH-OBEN- und der NACH-UNTEN-TASTE die Anzahl der Ereignisse ein, die Sie beibehalten möchten, oder wählen diese aus.</span><span class="sxs-lookup"><span data-stu-id="359de-180">In the **Number of events to keep** box, enter or select the number of events you want to keep by using the up and down arrows.</span></span>  
  
    2.  <span data-ttu-id="359de-181">Geben Sie im Feld **Max. Pufferspeichergröße** die maximale Menge Pufferspeicher an, die verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="359de-181">In the **Maximum buffer memory size** box, specify the maximum amount of buffer memory to use.</span></span> <span data-ttu-id="359de-182">Die vorhandenen Ereignisse werden gelöscht, wenn dieser Wert erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="359de-182">The existing events are dropped when this value is reached.</span></span>  
  
    3.  <span data-ttu-id="359de-183">Wenn Sie eine bestimmte Anzahl von Ereignissen jedes Typs im Puffer beibehalten möchten, aktivieren Sie das Kontrollkästchen **Angegebene Anzahl von Ereignissen (pro Typ) bei vollem Puffer beibehalten** .</span><span class="sxs-lookup"><span data-stu-id="359de-183">If you want to keep a specific number of events of each type in the buffer, select the **Keep a specified number of events (per type) when the buffer is full** check box.</span></span>  
  
    4.  <span data-ttu-id="359de-184">Im Feld **Anzahl beizubehaltender Ereignisse (pro Typ)** geben Sie mithilfe der NACH-OBEN- und der NACH-UNTEN-TASTE die Anzahl der Ereignisse (pro Typ) ein, die Sie beibehalten möchten, oder wählen diese aus.</span><span class="sxs-lookup"><span data-stu-id="359de-184">In the **Number of events to keep (per type)** box, enter or select the number of events (per type) that you want to keep by using the up and down arrows.</span></span>  
  
##  <a name="summary"></a><a name="BKMK_Summary"></a> <span data-ttu-id="359de-185">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="359de-185">Summary</span></span>  
 <span data-ttu-id="359de-186">Gehen Sie auf der Seite **Zusammenfassung** wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="359de-186">On the **Summary** page, do the following:</span></span>  
  
1.  <span data-ttu-id="359de-187">Stellen Sie sicher, dass die Auswahl richtig ist.</span><span class="sxs-lookup"><span data-stu-id="359de-187">Make sure that your selections are correct.</span></span> <span data-ttu-id="359de-188">Erweitern Sie die Ereignissitzungsknoten, um zu überprüfen, dass die gesamte Auswahl in die Ereignissitzung eingeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="359de-188">Expand the event session nodes to verify that all of your selections will be included in the event session.</span></span>  
  
2.  <span data-ttu-id="359de-189">Klicken Sie auf **Skript** , um das Sitzungserstellungsskript in ein neues Abfrage-Editor-Fenster zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="359de-189">Click **Script** to export the session creation script to a new Query Editor window.</span></span>  
  
3.  <span data-ttu-id="359de-190">Klicken Sie auf **Fertig stellen** , um die Ereignissitzung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="359de-190">Click **Finish** to create the event session.</span></span>  
  
##  <a name="create-event-session"></a><a name="BKMK_CreateEventSession"></a><span data-ttu-id="359de-191">Ereignis Sitzung erstellen</span><span class="sxs-lookup"><span data-stu-id="359de-191">Create Event Session</span></span>  
 <span data-ttu-id="359de-192">Nachdem die Ereignissitzung erfolgreich erstellt wurde, gehen Sie auf der Seite **Ereignissitzung erstellen** folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="359de-192">On the **Create Event Session** page, after your event session has been successfully created, do the following:</span></span>  
  
1.  <span data-ttu-id="359de-193">Klicken Sie auf **Ereignissitzung direkt nach dem Erstellen der Sitzung starten** , um die Sitzung zu starten, nachdem Sie den Assistenten geschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="359de-193">Click **Start the event session immediately after session creation** to start the session after you close the wizard.</span></span> <span data-ttu-id="359de-194">Sie müssen die Ereignissitzung unmittelbar nach dem Erstellen der Sitzung starten, damit Sie die Livedaten beobachten können.</span><span class="sxs-lookup"><span data-stu-id="359de-194">You must start the event session immediately after you create the session to be able to watch live data.</span></span>  
  
2.  <span data-ttu-id="359de-195">Klicken Sie auf **Livedaten während der Aufzeichnung auf dem Bildschirm ansehen** , um Livedaten für die Ereignissitzung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="359de-195">Click **Watch live data on screen as it is captured** to view live data for your event session.</span></span> <span data-ttu-id="359de-196">Unmittelbar nach der Erstellung der Sitzung wird für die Livedaten eine Ablaufverfolgung gestartet.</span><span class="sxs-lookup"><span data-stu-id="359de-196">The live data will start displaying tracing immediately after the session is created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="359de-197">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="359de-197">See Also</span></span>  
 [<span data-ttu-id="359de-198">Erstellen einer Sitzung für erweiterte Ereignisse im Dialogfeld für neue Sitzungen</span><span class="sxs-lookup"><span data-stu-id="359de-198">Create an Extended Events Session Using the New Session Dialog</span></span>](../../2014/database-engine/create-an-extended-events-session-using-the-new-session-dialog.md)  
  
  
