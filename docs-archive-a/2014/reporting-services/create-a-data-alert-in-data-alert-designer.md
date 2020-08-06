---
title: Erstellen einer Datenwarnung im Datenwarnungs-Designer | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 8464ab9d-afe1-4490-955f-9f3319bcbf8d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 19c3001d4663848c009a353baa068f237d4a0b5b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719720"
---
# <a name="create-a-data-alert-in-data-alert-designer"></a><span data-ttu-id="c835d-102">Erstellen einer Datenwarnung im Datenwarnungs-Designer</span><span class="sxs-lookup"><span data-stu-id="c835d-102">Create a Data Alert in Data Alert Designer</span></span>
  <span data-ttu-id="c835d-103">Sie können Datenwarnungsdefinitionen im Datenwarnungs-Designer erstellen.</span><span class="sxs-lookup"><span data-stu-id="c835d-103">You create data alert definitions in Data Alert Designer.</span></span> <span data-ttu-id="c835d-104">Nach dem Speichern der Warnungsdefinitionen können Sie diese im Datenwarnungs-Designer erneut öffnen, bearbeiten und dann erneut speichern.</span><span class="sxs-lookup"><span data-stu-id="c835d-104">After you save the alert definitions, you can reopen, edit, and then resave them in Data Alert Designer.</span></span> <span data-ttu-id="c835d-105">Weitere Informationen zum Bearbeiten von Warnungsdefinitionen finden Sie unter [Verwalten meiner Datenwarnungen im Datenwarnungs-Manager](manage-my-data-alerts-in-data-alert-manager.md) und [Bearbeiten einer Datenwarnung im Warnungs-Designer](edit-a-data-alert-in-alert-designer.md).</span><span class="sxs-lookup"><span data-stu-id="c835d-105">For information about editing alert definitions, see [Manage My Data Alerts in Data Alert Manager](manage-my-data-alerts-in-data-alert-manager.md) and [Edit a Data Alert in Alert Designer](edit-a-data-alert-in-alert-designer.md).</span></span>

### <a name="to-create-a-data-alert-definition"></a><span data-ttu-id="c835d-106">So erstellen Sie eine Datenwarnungsdefinition</span><span class="sxs-lookup"><span data-stu-id="c835d-106">To create a data alert definition</span></span>

1.  <span data-ttu-id="c835d-107">Wechseln Sie zur SharePoint-Bibliothek mit dem Bericht, für den Sie eine Datenwarnungsdefinition erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="c835d-107">Locate the SharePoint library that contains the report that you want to create a data alert definition for.</span></span>

2.  <span data-ttu-id="c835d-108">Klicken Sie auf den Bericht.</span><span class="sxs-lookup"><span data-stu-id="c835d-108">Click the report.</span></span>

     <span data-ttu-id="c835d-109">Der Bericht wird ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c835d-109">The report runs.</span></span> <span data-ttu-id="c835d-110">Wenn der Bericht parametrisiert ist, überprüfen Sie, ob der Bericht die Daten enthält, für die Sie Warnmeldungen erhalten möchten.</span><span class="sxs-lookup"><span data-stu-id="c835d-110">If the report is parameterized, verify that the report shows the data that you want to receive alert messages about.</span></span> <span data-ttu-id="c835d-111">Wenn Sie die Spalten oder die Werte nicht sehen, an denen Sie interessiert sind, können Sie den Bericht mit anderen Parameterwerten erneut ausführen.</span><span class="sxs-lookup"><span data-stu-id="c835d-111">If you do not see the columns or values you are interested in, you might want to rerun the report, using different parameter values.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="c835d-112">Die zum Ausführen des Berichts ausgewählten Parameterwerte werden in der Warnungsdefinition gespeichert und verwendet, wenn der Bericht als Schritt der Verarbeitung der Warnungsdefinition erneut ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c835d-112">The parameter values you chose to run the report are saved in the alert definition and will be used when report is rerun as a step in processing the alert definition.</span></span> <span data-ttu-id="c835d-113">Um andere Parameterwerte zu verwenden, müssen Sie eine neue Warnungsdefinition erstellen.</span><span class="sxs-lookup"><span data-stu-id="c835d-113">To use different parameter values, you must create a new alert definition.</span></span>

3.  <span data-ttu-id="c835d-114">Klicken Sie im Menü **Aktionen** auf **Neue Datenwarnung**.</span><span class="sxs-lookup"><span data-stu-id="c835d-114">On the **Actions** menu, click **New Data Alert**.</span></span>

     <span data-ttu-id="c835d-115">Das folgende Bild zeigt das Menü **Aktionen** an.</span><span class="sxs-lookup"><span data-stu-id="c835d-115">The following picture shows the **Actions** menu.</span></span>

     <span data-ttu-id="c835d-116">![Öffnen des Warnungs-Designers über die SharePoint-Bibliothek](media/rs-openalertdesigneriw.gif "Öffnen des Warnungs-Designers über die SharePoint-Bibliothek")</span><span class="sxs-lookup"><span data-stu-id="c835d-116">![Open Alert Designer from SharePoint library](media/rs-openalertdesigneriw.gif "Open Alert Designer from SharePoint library")</span></span>

     <span data-ttu-id="c835d-117">Der Datenwarnungs-Designer wird geöffnet und zeigt die ersten 100 Zeilen des ersten Datenfeeds an, den der Bericht in einer Tabelle generiert.</span><span class="sxs-lookup"><span data-stu-id="c835d-117">The Data Alert Designer opens, showing the first 100 rows of the first data feed that the report generates in a table.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="c835d-118">Wenn Sie die Option **Neue Datenwarnung** nicht sehen, ist der Warndienst nicht auf der SharePoint-Website konfiguriert, oder die [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Edition umfasst keine Datenwarnungen.</span><span class="sxs-lookup"><span data-stu-id="c835d-118">If you do not see the **New Data Alert** option, the alerting service is not configured on the SharePoint site or the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] edition does not include data alerts.</span></span> <span data-ttu-id="c835d-119">Weitere Informationen finden Sie unter [Reporting Services-SharePoint-Dienst und -Dienstanwendungen](../../2014/reporting-services/reporting-services-sharepoint-service-and-service-applications.md).</span><span class="sxs-lookup"><span data-stu-id="c835d-119">For more information, see [Reporting Services SharePoint Service and Service Applications](../../2014/reporting-services/reporting-services-sharepoint-service-and-service-applications.md).</span></span>
    > 
    >  <span data-ttu-id="c835d-120">Ist die Option **Neue Datenwarnung** ausgegraut, ist die Berichtsdatenquelle so konfiguriert, dass integrierte Sicherheitsanmeldeinformationen verwendet werden oder eine Eingabeaufforderung für Anmeldeinformationen angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c835d-120">If the **New Data Alert** option is grayed, the report data source is configured to use integrated security credentials or prompt for credentials.</span></span> <span data-ttu-id="c835d-121">Zur Bereitstellung der Option **Neue Datenwarnung** müssen Sie die Datenquelle so aktualisieren, dass entweder gespeicherte Anmeldeinformationen oder keine Anmeldeinformationen zu verwenden sind.</span><span class="sxs-lookup"><span data-stu-id="c835d-121">To make the **New Data Alert** option available, you must update the data source to use stored credentials or no credentials.</span></span>

     <span data-ttu-id="c835d-122">Der Name des Datenfeeds wird in der Dropdownliste **Berichtsdatenname** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c835d-122">The name of the data feed appears in **Report data name** drop-down list.</span></span>

4.  <span data-ttu-id="c835d-123">Wählen Sie in der Dropdownliste **Berichtsdatenname** optional einen anderen Datenfeed aus.</span><span class="sxs-lookup"><span data-stu-id="c835d-123">Optionally, select a different data feed in the **Report data name** drop-down list.</span></span>

     <span data-ttu-id="c835d-124">Wenn kein Datenfeed aus dem Bericht generiert wird, können Sie für den Bericht keine Warnungsdefinition erstellen.</span><span class="sxs-lookup"><span data-stu-id="c835d-124">If no data feed is generated from the report, you cannot create an alert definition for the report.</span></span> <span data-ttu-id="c835d-125">Das Layout des Berichts bestimmt den Inhalt jedes Datenfeeds.</span><span class="sxs-lookup"><span data-stu-id="c835d-125">The layout of the report determines the content of each data feed.</span></span> <span data-ttu-id="c835d-126">Weitere Informationen finden Sie unter [Erstellen von Daten Feeds aus Berichten &#40;Berichts-Generator und SSRS&#41;](report-builder/generating-data-feeds-from-reports-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="c835d-126">For more information see, [Generating Data Feeds from Reports &#40;Report Builder and SSRS&#41;](report-builder/generating-data-feeds-from-reports-report-builder-and-ssrs.md).</span></span>

5.  <span data-ttu-id="c835d-127">Sie können im Textfeld **Warnungsname** den Standardnamen in einen sinnvolleren Namen ändern.</span><span class="sxs-lookup"><span data-stu-id="c835d-127">Optionally, in the **Alert name** text box, update the default name to be more meaningful.</span></span>

     <span data-ttu-id="c835d-128">Der Standardname der Warnungsdefinition entspricht dem Namen des Berichts.</span><span class="sxs-lookup"><span data-stu-id="c835d-128">The default name of the alert definition is the name of the report.</span></span> <span data-ttu-id="c835d-129">Warnungsdefinitionsnamen müssen nicht eindeutig sind, sodass sie schwer voneinander zu unterscheiden sind, wenn Sie die Liste der Warnungen später im Datenwarnungs-Manager anzeigen.</span><span class="sxs-lookup"><span data-stu-id="c835d-129">Alert definition names do not have to be unique, which can make it difficult to tell them apart when you later view the list of your alerts in Data Alert Manager.</span></span> <span data-ttu-id="c835d-130">Es empfiehlt sich, sinnvolle und eindeutige Namen für die Warnungsdefinitionen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="c835d-130">It is recommended that you use meaningful and unique names for your alert definitions.</span></span>

6.  <span data-ttu-id="c835d-131">Ändern Sie die Standarddatenoption optional von **die Daten im Datenfeed Folgendes enthalten** in **die Daten im Datenfeed Folgendes nicht enthalten**.</span><span class="sxs-lookup"><span data-stu-id="c835d-131">Optionally, change the default data option from **any data in the data feed has** to **no data in the data feed has**.</span></span>

7.  <span data-ttu-id="c835d-132">Klicken Sie auf **Regel hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="c835d-132">Click **Add rule**.</span></span>

     <span data-ttu-id="c835d-133">Eine Liste der Spalten im Datenfeed wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c835d-133">A list of the columns in the data feed appears.</span></span>

8.  <span data-ttu-id="c835d-134">Wählen Sie aus der Liste die Spalte aus, die Sie in der Regel verwenden möchten. Wählen Sie dann einen Vergleichsoperator aus, und geben Sie den Schwellenwert ein.</span><span class="sxs-lookup"><span data-stu-id="c835d-134">In the list, select the column that you want to use in the rule, and then select a comparison operator and enter the threshold value.</span></span>

     <span data-ttu-id="c835d-135">Abhängig vom Datentyp der ausgewählten Spalte sind andere Vergleichsoperatoren aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="c835d-135">Depending on the data type of the selected column, different comparison operators are listed.</span></span> <span data-ttu-id="c835d-136">Wenn die Spalte einen Datumsdatentyp aufweist, wird ein Kalendersymbol neben dem Schwellenwert für die Regel angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c835d-136">If the column has a date data type, a calendar icon displays next to threshold value for the rule.</span></span> <span data-ttu-id="c835d-137">Sie können Daten eingeben, indem Sie auf ein Datum im Kalender klicken oder das Datum eingeben.</span><span class="sxs-lookup"><span data-stu-id="c835d-137">You can enter a data by clicking a date in the calendar or typing the date.</span></span>

     <span data-ttu-id="c835d-138">Der Datenwarnungs-Designer stellt zwei Vergleichsmodi bereit: **Werteingabemodus** und **Feldauswahlmodus**.</span><span class="sxs-lookup"><span data-stu-id="c835d-138">Data Alert Designer provides two comparison modes: **Value Entry Mode** and **Field Selection Mode**.</span></span> <span data-ttu-id="c835d-139">Der Standardmodus ist der **Werteingabemodus**.</span><span class="sxs-lookup"><span data-stu-id="c835d-139">The default mode is **Value Entry Mode**.</span></span> <span data-ttu-id="c835d-140">Sie können OR-Klauseln nur hinzufügen, wenn der **Werteingabemodus** aktiviert ist und Sie den Vergleich **ist** verwenden.</span><span class="sxs-lookup"><span data-stu-id="c835d-140">You can add OR clauses only when you are in **Value Entry Mode** and are using the **is** comparison.</span></span>

9. <span data-ttu-id="c835d-141">Um eine OR-Klausel hinzuzufügen, klicken Sie auf den Pfeil nach unten und anschließend auf **Werteingabemodus**.</span><span class="sxs-lookup"><span data-stu-id="c835d-141">To add an OR clause, click the down-arrow, and then click **Value Entry Mode**.</span></span>

10. <span data-ttu-id="c835d-142">Geben Sie den Vergleichswert ein.</span><span class="sxs-lookup"><span data-stu-id="c835d-142">Type the comparison value.</span></span>

11. <span data-ttu-id="c835d-143">Klicken Sie optional erneut auf die Auslassungs Punkte **(...)** .</span><span class="sxs-lookup"><span data-stu-id="c835d-143">Optionally, click the ellipsis **(...)** again.</span></span>

     <span data-ttu-id="c835d-144">Die Auslassungs Punkte **(...)** werden in der Zeile mit der ersten Klausel angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c835d-144">The ellipsis **(...)** appears on the line that contains the first clause.</span></span>

     <span data-ttu-id="c835d-145">Eine OR-Klausel wird unten und innerhalb der AND-Regel hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="c835d-145">An OR clause is added below and within the AND rule.</span></span>

12. <span data-ttu-id="c835d-146">Klicken Sie optional auf den Pfeil nach unten, wählen Sie **Feldauswahlmodus**und anschließend eine Spalte in der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="c835d-146">Optionally, click the down-arrow, select **Field Selection Mode**, and then select a column in the list.</span></span>

     <span data-ttu-id="c835d-147">Sie werden bemerken, dass die Auslassungs Punkte **(...)** , auf die Sie zum Hinzufügen von OR-Klauseln klicken, verschwunden sind.</span><span class="sxs-lookup"><span data-stu-id="c835d-147">You will notice that the ellipsis **(...)** that you click to add OR clauses has disappeared.</span></span>

13. <span data-ttu-id="c835d-148">Klicken Sie optional erneut auf **Regel hinzufügen** , um weitere Regeln hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="c835d-148">Optionally, click **Add rule** again to add additional rules.</span></span>

     <span data-ttu-id="c835d-149">Die Regeln werden mithilfe des logischen AND-Operators kombiniert.</span><span class="sxs-lookup"><span data-stu-id="c835d-149">The rules are combined by using the AND logical operator.</span></span>

14. <span data-ttu-id="c835d-150">Wählen Sie in der Wiederholungsliste eine Option aus.</span><span class="sxs-lookup"><span data-stu-id="c835d-150">Select an option in the recurrence list.</span></span> <span data-ttu-id="c835d-151">Geben Sie abhängig vom Typ der Wiederholung ein Intervall ein.</span><span class="sxs-lookup"><span data-stu-id="c835d-151">Depending on the type of recurrence, enter an interval.</span></span>

15. <span data-ttu-id="c835d-152">Klicken Sie optional auf **Erweitert**.</span><span class="sxs-lookup"><span data-stu-id="c835d-152">Optionally, click **Advanced**.</span></span>

16. <span data-ttu-id="c835d-153">Ändern Sie optional das Startdatum der Warnmeldung, indem Sie ein anderes Datum eingeben oder den Kalender öffnen und auf ein Datum im Kalender klicken.</span><span class="sxs-lookup"><span data-stu-id="c835d-153">Optionally, change the date that the alert message starts on by typing a different date or opening the calendar, and then clicking a date in the calendar.</span></span>

     <span data-ttu-id="c835d-154">Das Standardstartdatum ist das aktuelle Datum.</span><span class="sxs-lookup"><span data-stu-id="c835d-154">The default start date is the current date.</span></span>

17. <span data-ttu-id="c835d-155">Aktivieren Sie optional das Kontrollkästchen neben **Warnung beenden**, und wählen Sie dann ein Datum aus, an dem die Warnmeldung enden soll.</span><span class="sxs-lookup"><span data-stu-id="c835d-155">Optionally, select the checkbox located next to **Stop alert on**, and then choose a date to stop the alert message.</span></span>

     <span data-ttu-id="c835d-156">Standardmäßig hat eine Warnmeldung kein Enddatum.</span><span class="sxs-lookup"><span data-stu-id="c835d-156">By default, an alert message has no stop date.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="c835d-157">Durch das Beenden einer Warnmeldung wird die Warnungsdefinition nicht gelöscht.</span><span class="sxs-lookup"><span data-stu-id="c835d-157">Stopping an alert message does not delete the alert definition.</span></span> <span data-ttu-id="c835d-158">Nach dem Beenden einer Warnmeldung können Sie diese durch Aktualisieren des Start- und Enddatums erneut starten.</span><span class="sxs-lookup"><span data-stu-id="c835d-158">After you stop an alert message, you can restart it by updating the start and stop dates.</span></span> <span data-ttu-id="c835d-159">Weitere Informationen zum Löschen von Warnungsdefinitionen finden Sie unter [Verwalten meiner Datenwarnungen im Datenwarnungs-Manager](manage-my-data-alerts-in-data-alert-manager.md).</span><span class="sxs-lookup"><span data-stu-id="c835d-159">For information about deleting alert definitions, see [Manage My Data Alerts in Data Alert Manager](manage-my-data-alerts-in-data-alert-manager.md).</span></span>

18. <span data-ttu-id="c835d-160">Deaktivieren Sie optional das Kontrollkästchen zum **Senden von Meldungen nur bei Ergebnisänderungen**.</span><span class="sxs-lookup"><span data-stu-id="c835d-160">Optionally, clear the **Send message only if results change** checkbox.</span></span>

     <span data-ttu-id="c835d-161">Wenn Sie Warnmeldungen häufig senden, sind redundante Informationen u. U. nicht erwünscht, und Sie sollten das Kontrollkästchen nicht deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="c835d-161">If you send alert messages frequently, redundant information might not be welcome and you should not clear this checkbox.</span></span>

19. <span data-ttu-id="c835d-162">Geben Sie die E-Mail-Adressen von Warnmeldungsempfängern ein.</span><span class="sxs-lookup"><span data-stu-id="c835d-162">Enter the email addresses of alert message recipients.</span></span> <span data-ttu-id="c835d-163">Trennen Sie Adressen mit Semikolons.</span><span class="sxs-lookup"><span data-stu-id="c835d-163">Separate addresses with semicolons.</span></span>

     <span data-ttu-id="c835d-164">Ist die E-Mail-Adresse des Erstellers der Warnungsdefinition verfügbar, wird sie dem Feld **Empfänger** hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="c835d-164">If the email address of the person who created the alert definition is available, it is added to the **Recipient(s)** box.</span></span>

20. <span data-ttu-id="c835d-165">Aktualisieren Sie optional im Textfeld **Betreff** die Betreffzeile der Warnmeldung.</span><span class="sxs-lookup"><span data-stu-id="c835d-165">Optionally, in the **Subject** text box, update the Subject line of the alert message.</span></span>

     <span data-ttu-id="c835d-166">Der Standard Betreff lautet \*\*Daten Warnung für \<data alert name> \*\*.</span><span class="sxs-lookup"><span data-stu-id="c835d-166">The default Subject is **Data alert for \<data alert name>**.</span></span>

21. <span data-ttu-id="c835d-167">Geben Sie optional im Textfeld **Beschreibung** eine Beschreibung der Warnmeldung ein.</span><span class="sxs-lookup"><span data-stu-id="c835d-167">Optionally, in the **Description** text box, type a description of the alert message.</span></span>

22. <span data-ttu-id="c835d-168">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="c835d-168">Click **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="c835d-169">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c835d-169">See Also</span></span>
 <span data-ttu-id="c835d-170">Datenwarnungs- [Designer](../../2014/reporting-services/data-alert-designer.md) [datenwarnungs-Manager für Warnungs Administratoren](../../2014/reporting-services/data-alert-manager-for-alerting-administrators.md) [Reporting Services Daten Warnungen](../ssms/agent/alerts.md)</span><span class="sxs-lookup"><span data-stu-id="c835d-170">[Data Alert Designer](../../2014/reporting-services/data-alert-designer.md) [Data Alert Manager for Alerting Administrators](../../2014/reporting-services/data-alert-manager-for-alerting-administrators.md) [Reporting Services Data Alerts](../ssms/agent/alerts.md)</span></span>


