---
title: Importieren von Bereinigungsprojektwerten in eine Domäne | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.kb.importprojectvalues.f1
ms.assetid: f23e38e2-39e0-42d7-abd5-34d8fcca5d2a
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 38616da5a0a8fb9c8f149d9f55a08b63dee5ff6a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700251"
---
# <a name="import-cleansing-project-values-into-a-domain"></a><span data-ttu-id="27034-102">Importieren von Bereinigungsprojektwerten in eine Domäne</span><span class="sxs-lookup"><span data-stu-id="27034-102">Import Cleansing Project Values into a Domain</span></span>
  <span data-ttu-id="27034-103">In [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) können Sie während des Bereinigungsprozesses in einem Datenqualitätsbereinigungsprojekt oder einem Integration Services-Paket mit der DQS-Bereinigungskomponente erfasstes Datenqualitätswissen in eine Domäne importieren.</span><span class="sxs-lookup"><span data-stu-id="27034-103">In [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS), you can import data quality knowledge gathered during the cleansing process in a data quality cleansing project or an Integration Services package containing the DQS Cleansing component into a domain.</span></span> <span data-ttu-id="27034-104">Dadurch wird sichergestellt, dass vertrauenswürdiges Wissen nicht verloren geht und dass die Wissensdatenbank ständig verbessert wird.</span><span class="sxs-lookup"><span data-stu-id="27034-104">This ensures that trusted knowledge is not lost, and that the knowledge base is continually improved.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="27034-105">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="27034-105">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="27034-106">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="27034-106">Prerequisites</span></span>  
  
-   <span data-ttu-id="27034-107">Zum Importieren von Bereinigungsprojektwerten in eine Domäne muss die Domäne im Bereinigungsprojekt in Data Quality Client oder dem Integration Services-Paket, das eine DQS-Bereinigungs-Komponente enthält, verwendet worden sein.</span><span class="sxs-lookup"><span data-stu-id="27034-107">To import cleansing project values into a domain, the domain must have been used in the cleansing project in Data Quality Client or in the Integration Services package containing a DQS Cleansing component.</span></span>  
  
-   <span data-ttu-id="27034-108">Das Bereinigungsprojekt in Data Quality Client oder dem Integration Services-Paket mit der DQS-Bereinigungskomponente muss erfolgreich abgeschlossen worden sein.</span><span class="sxs-lookup"><span data-stu-id="27034-108">The cleansing project in Data Quality Client or the Integration Services package containing the DQS Cleansing component must have successfully completed.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="27034-109">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="27034-109">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="27034-110">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="27034-110">Permissions</span></span>  
 <span data-ttu-id="27034-111">Sie müssen über die Rolle „dqs_kb_editor“ oder „dqs_administrator“ in der DQS_MAIN-Datenbank verfügen, um während des Bereinigungsprozesses gesammeltes Data Quality-Wissen in eine Domäne zu importieren.</span><span class="sxs-lookup"><span data-stu-id="27034-111">You must have the dqs_kb_editor or the dqs_administrator role on the DQS_MAIN database to import data quality knowledge gathered during the cleansing process into a domain.</span></span>  
  
##  <a name="import-cleansing-project-values"></a><a name="Import"></a><span data-ttu-id="27034-112">Importieren von Bereinigungs Projekt Werten</span><span class="sxs-lookup"><span data-stu-id="27034-112">Import Cleansing Project Values</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="27034-113">[Führen Sie die Data Quality-Client Anwendung](../../2014/data-quality-services/run-the-data-quality-client-application.md)aus.</span><span class="sxs-lookup"><span data-stu-id="27034-113">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="27034-114">Öffnen Sie im [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] -Startbildschirm in der Domänenverwaltungsaktivität eine Wissensdatenbank.</span><span class="sxs-lookup"><span data-stu-id="27034-114">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, open a knowledge base in the Domain Management activity.</span></span>  
  
3.  <span data-ttu-id="27034-115">Wenn Sie einer vorhandenen Domäne Werte hinzufügen, wählen Sie die Domäne in der Domänenliste aus.</span><span class="sxs-lookup"><span data-stu-id="27034-115">If adding values to an existing domain, select the domain in the domain list.</span></span>  
  
4.  <span data-ttu-id="27034-116">Klicken Sie auf die Registerkarte **Domänenwerte** , klicken Sie auf das Symbol **Werte importieren** in der Symbolleiste, und klicken Sie dann auf **Projektwerte importieren**.</span><span class="sxs-lookup"><span data-stu-id="27034-116">Click the **Domain Values** tab, click the **Import Values** icon in the icon bar, and then click **Import project values**.</span></span> <span data-ttu-id="27034-117">Das Dialogfeld **Projektwerte importieren** wird mit einer Liste von Data Quality-Projekten und Integration Services-Paketen angezeigt, die mit der Domäne bereinigt wurden.</span><span class="sxs-lookup"><span data-stu-id="27034-117">The **Import Project Values** dialog box appears with a list of data quality projects and Integration Services packages that were cleansed using the domain.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="27034-118"> Wenn kein Projekt mit der Domäne oder einer verknüpften Domäne erstellt wurde oder das Projekt nicht abgeschlossen wurde, ist die Option **Projektwerte importieren** nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="27034-118">If no project has been created using the domain or any of its linked domains, or the project was not finished, the **Import project values** option will not be available.</span></span>  
  
5.  <span data-ttu-id="27034-119">Im Dialogfeld **Projektwerte importieren** :</span><span class="sxs-lookup"><span data-stu-id="27034-119">In the **Import Project Values** dialog box:</span></span>  
  
    -   <span data-ttu-id="27034-120">Wählen Sie in der Dropdownliste **Importiert** die Option **Alle** aus, um alle Projekte anzuzeigen, oder **Nein** , um nur die Projekte anzuzeigen, deren Werte noch nicht importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="27034-120">Select **All** in the **Imported** drop-down list to display all projects, or **No** to display only projects whose values have not been imported yet.</span></span>  
  
    -   <span data-ttu-id="27034-121">Wählen Sie das Projekt aus, aus dem Sie Werte importieren möchten.</span><span class="sxs-lookup"><span data-stu-id="27034-121">Select the project that you want to import values from.</span></span>  
  
    -   <span data-ttu-id="27034-122">Wählen Sie **Werte aus der Registerkarte 'Neu' hinzufügen** aus, um Werte, zusätzlich zu Werten auf den Registerkarten **Richtig** und **Korrigiert** , in die neue Registerkarte zu importieren.</span><span class="sxs-lookup"><span data-stu-id="27034-122">Select **Add values from New tab** to import values in the new tab, in addition to values in the **Correct** and **Corrected** tabs.</span></span>  
  
    -   <span data-ttu-id="27034-123">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="27034-123">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="27034-124">Die Registerkarte **Domänenwerte** wird wieder angezeigt, und es wird eine Meldung zum erfolgreichen Importieren der Werte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="27034-124">You return to the **Domain Values** tab, and a message is displayed on successful import of the values.</span></span> <span data-ttu-id="27034-125">Werte, die importiert wurden und deshalb neu in der Domäne sind, werden in der Tabelle **Werte** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="27034-125">Values that have been imported, and so are new to the domain, will be displayed in the **Values** table.</span></span>  
  
7.  <span data-ttu-id="27034-126">Deaktivieren Sie **Nur neue anzeigen** , um alle Werte in der Domäne anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="27034-126">Deselect **Show Only New** to display all values that are in the domain.</span></span>  
  
8.  <span data-ttu-id="27034-127">Wählen Sie **Richtig**, **Fehler**oder **Ungültig** aus, um nur die Werte mit dem ausgewählten Typ anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="27034-127">Select **Correct**, **Error**, or **Invalid** to display only those values of the selected type.</span></span>  
  
9. <span data-ttu-id="27034-128">Um nach einer bestimmten Zeichenfolge zu suchen, geben Sie die Zeichenfolge in das Textfeld **Suchen** ein.</span><span class="sxs-lookup"><span data-stu-id="27034-128">To search for a specific string, enter the string in the **Find** text box.</span></span> <span data-ttu-id="27034-129">Klicken Sie auf den Pfeil nach oben oder nach unten, um durch die Werte zu blättern, die die Suchkriterien erfüllen.</span><span class="sxs-lookup"><span data-stu-id="27034-129">Click the up or down arrow to step through the values that meet the search criteria.</span></span> <span data-ttu-id="27034-130">Sie werden in Gelb hervorgehoben.</span><span class="sxs-lookup"><span data-stu-id="27034-130">They will be highlighted in yellow.</span></span>  
  
10. <span data-ttu-id="27034-131">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="27034-131">Click **Finish**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="27034-132"> Weitere Informationen zum Arbeiten mit Werten auf der Registerkarte **Domänenwerte** finden Sie unter [Change Domain Values](../../2014/data-quality-services/change-domain-values.md).</span><span class="sxs-lookup"><span data-stu-id="27034-132">For more information on working with values in the **Domain Values** tab, see [Change Domain Values](../../2014/data-quality-services/change-domain-values.md).</span></span>  
  
##  <a name="follow-up-after-importing-project-values-into-a-domain"></a><a name="FollowUp"></a> <span data-ttu-id="27034-133">Nachverfolgung: Nach dem Importieren von Projektwerten in eine Domäne</span><span class="sxs-lookup"><span data-stu-id="27034-133">Follow Up: After Importing Project Values into a Domain</span></span>  
 <span data-ttu-id="27034-134">Nachdem Sie während des Bereinigungsprozesses gesammeltes Data Quality-Wissen in eine Domäne importiert haben, können Sie andere Domänenverwaltungsaufgaben für die Domäne und die Werte ausführen.</span><span class="sxs-lookup"><span data-stu-id="27034-134">After you import data quality knowledge gathered during the cleansing process into a domain, you can perform other domain management tasks on the domain and the values.</span></span> <span data-ttu-id="27034-135">Weitere Informationen finden Sie unter [Verwalten einer Domäne](../../2014/data-quality-services/managing-a-domain.md).</span><span class="sxs-lookup"><span data-stu-id="27034-135">For more information, see [Managing a Domain](../../2014/data-quality-services/managing-a-domain.md).</span></span>  
  
##  <a name="values-that-will-be-imported"></a><a name="Values"></a> <span data-ttu-id="27034-136">Importierte Werte</span><span class="sxs-lookup"><span data-stu-id="27034-136">Values that Will Be Imported</span></span>  
 <span data-ttu-id="27034-137">Die folgenden Werte werden aus einem Projekt in eine Domäne importiert:</span><span class="sxs-lookup"><span data-stu-id="27034-137">The following values will be imported from a project into a domain:</span></span>  
  
-   <span data-ttu-id="27034-138">Nur Zeichenfolgenwerte werden in die Domäne importiert.</span><span class="sxs-lookup"><span data-stu-id="27034-138">Only string values are imported to the domain.</span></span>  
  
-   <span data-ttu-id="27034-139">Nur Werte aus den Registerkarten **Richtig**, **Korrigiert**und **Neu** auf der Seite **Ergebnisse verwalten und anzeigen** der **Bereinigungsaktivität** werden importiert.</span><span class="sxs-lookup"><span data-stu-id="27034-139">Only values from the **Correct**, **Corrected**, and **New** tabs on the **Manage and View results** page of the **Cleansing** activity will be imported.</span></span> <span data-ttu-id="27034-140">Werte auf der Registerkarte **Neu** werden nur importiert, wenn das Kontrollkästchen **Werte aus der Registerkarte 'Neu' hinzufügen** im Dialogfeld **Projektwerte importieren** aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="27034-140">Values from the **New** tab will be imported only if the **Add values from New tab** check box in the **Import Project Values** dialog box has been selected.</span></span>  
  
-   <span data-ttu-id="27034-141">Werte werden als richtig oder als Fehler mit der Korrektur importiert.</span><span class="sxs-lookup"><span data-stu-id="27034-141">Values will be imported as correct or as an error with its correction.</span></span> <span data-ttu-id="27034-142">Nur ein Fehlerwert mit einem Korrekturwert wird importiert.</span><span class="sxs-lookup"><span data-stu-id="27034-142">Only an error value with a correction value will be imported.</span></span>  
  
-   <span data-ttu-id="27034-143">Der Korrekturwert ist entweder ein neuer Wert, der in der Wissensdatenbank nicht vorhanden ist, oder ein vorhandener, richtiger Wert.</span><span class="sxs-lookup"><span data-stu-id="27034-143">The correction value will be either a new value that does not exist in the knowledge base or an existing correct value.</span></span>  
  
-   <span data-ttu-id="27034-144">Nur Korrekturen, die auf der Wertebene, nicht auf der Datensatzebene, ausgeführt wurden, werden in die Wissensdatenbank importiert.</span><span class="sxs-lookup"><span data-stu-id="27034-144">Only corrections performed on the value level, not the record level, will be imported into the knowledge base.</span></span>  
  
-   <span data-ttu-id="27034-145">Ungültige Werte werden erstellt, wenn der importierte Wert eine Domänenregel verletzt.</span><span class="sxs-lookup"><span data-stu-id="27034-145">Invalid values will be created if the imported value contradicts a domain rule.</span></span>  
  
-   <span data-ttu-id="27034-146">Wenn Sie Werte aus mehreren Projekten gleichzeitig importieren, werden die Werte in sequenzieller Reihenfolge importiert.</span><span class="sxs-lookup"><span data-stu-id="27034-146">If you import values from several projects at once, the values are imported in a sequential order.</span></span>  
  
-   <span data-ttu-id="27034-147">Eine Korrektur, die als Ergebnis einer begriffsbasierten Beziehung in einer Domäne vorgenommen wurde, wird als richtiger Wert (nicht als Fehler) importiert.</span><span class="sxs-lookup"><span data-stu-id="27034-147">A correction made as a result of a term-based relation in a domain is imported as a correct value (not as an error).</span></span>  
  
##  <a name="values-that-will-not-be-imported"></a><a name="ValuesNot"></a> <span data-ttu-id="27034-148">Nicht importierte Werte</span><span class="sxs-lookup"><span data-stu-id="27034-148">Values that Will Not Be Imported</span></span>  
 <span data-ttu-id="27034-149">Die folgenden Werte werden nicht aus einem Projekt in eine Domäne importiert:</span><span class="sxs-lookup"><span data-stu-id="27034-149">The following values will not be imported from a project into a domain:</span></span>  
  
-   <span data-ttu-id="27034-150">Werte aus den Registerkarten **Vorgeschlagen** und **Ungültig** auf der Seite **Ergebnisse verwalten und anzeigen** der **Bereinigungsaktivität** werden nicht importiert.</span><span class="sxs-lookup"><span data-stu-id="27034-150">Values from the **Suggested** and **Invalid** tabs on the **Manage and View results** page of the **Cleansing** activity will not be imported.</span></span>  
  
-   <span data-ttu-id="27034-151">Wenn ein im Bereinigungsprojekt gefundener Wert einem vorhandenen Wert in der Domäne widerspricht, wird der im Projekt gefundene Wert übersprungen.</span><span class="sxs-lookup"><span data-stu-id="27034-151">If a value found in the cleansing project contradicts an existing value in the domain, the value found in the project is skipped.</span></span> <span data-ttu-id="27034-152">Dies schließt Konflikte zwischen Bereinigungs- und Wissensdatenbankwerten ein.</span><span class="sxs-lookup"><span data-stu-id="27034-152">This will include conflicts between cleansing and knowledge base values.</span></span>  
  
-   <span data-ttu-id="27034-153">Korrekturen, die auf der Datensatzebene, ausgeführt wurden, werden nicht in die Wissensdatenbank importiert.</span><span class="sxs-lookup"><span data-stu-id="27034-153">Corrections performed on the record level will not be imported into the knowledge base.</span></span>  
  
-   <span data-ttu-id="27034-154">Kein Wert wird in eine Domäne importiert, wenn der Wert, den er ersetzen würde, korrigiert oder von einem Verweisdatendienst als richtig angenommen wurde.</span><span class="sxs-lookup"><span data-stu-id="27034-154">No value will be imported to a domain if the value that it would replace was corrected or approved as correct by a reference data service.</span></span>  
  
-   <span data-ttu-id="27034-155">Wenn ein Korrekturwert in der Wissensdatenbank als ungültig oder als Fehlerwert angezeigt wird, wird weder der Fehler noch der Korrekturwert importiert.</span><span class="sxs-lookup"><span data-stu-id="27034-155">If a correction value appears in the knowledge base as an invalid or error value, neither the error nor the correction value will be imported.</span></span>  
  
-   <span data-ttu-id="27034-156">Wenn die Domäne Teil einer Verbunddomäne ist und die Bereinigung in der Verbunddomäne ausgeführt wurde, werden keine Werte importiert.</span><span class="sxs-lookup"><span data-stu-id="27034-156">If the domain is part of a composite domain, and the cleansing was performed on the composite domain, no values will be imported.</span></span>  
  
-   <span data-ttu-id="27034-157">Sie können nur dann Werte aus einem Projekt importieren, wenn die Wissensdatenbank beschäftigt ist und vom importierenden Benutzer gesperrt wurde.</span><span class="sxs-lookup"><span data-stu-id="27034-157">You can import values from a project only when the knowledge base has a state of in-work and the knowledge base is locked by the user who is importing.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27034-158">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="27034-158">See Also</span></span>  
 <span data-ttu-id="27034-159">[Datenbereinigung](../../2014/data-quality-services/data-cleansing.md) </span><span class="sxs-lookup"><span data-stu-id="27034-159">[Data Cleansing](../../2014/data-quality-services/data-cleansing.md) </span></span>  
 [<span data-ttu-id="27034-160">DQS-Bereinigungstransformation</span><span class="sxs-lookup"><span data-stu-id="27034-160">DQS Cleansing Transformation</span></span>](../integration-services/data-flow/transformations/dqs-cleansing-transformation.md)  
  
  
