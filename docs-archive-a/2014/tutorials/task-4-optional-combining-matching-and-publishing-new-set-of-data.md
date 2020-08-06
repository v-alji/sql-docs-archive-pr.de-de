---
title: 'Aufgabe 4 (optional): kombinieren, abgleichen und Veröffentlichen eines neuen Datensatzes | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 13a13f03-b307-4555-8e33-6d98c459d994
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 9ddcec19fa8b957bf77b6ea5269b4d033779bdf1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608946"
---
# <a name="task-4-optional-combining-matching-and-publishing-new-set-of-data"></a><span data-ttu-id="a56e5-102">Aufgabe 4 (optional): Kombination, Abgleich und Veröffentlichung eines neuen Datensatzes</span><span class="sxs-lookup"><span data-stu-id="a56e5-102">Task 4 (Optional): Combining, Matching, and Publishing New Set of Data</span></span>
  <span data-ttu-id="a56e5-103">Es ist möglich, dass Sie dem MDS-Repository im Laufe der Zeit weitere Daten hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="a56e5-103">Over time, you will want to add more data to the MDS repository.</span></span> <span data-ttu-id="a56e5-104">Vor dem Hinzufügen von Daten kann es hilfreich sein, die neuen Daten mit den bereits in MDS verwalteten Daten zu vergleichen, um sicherzustellen, dass Sie keine doppelten oder ungenauen Daten hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="a56e5-104">Before adding data, it can be useful to compare the new data to the data that's already managed in MDS, to ensure that you are not adding duplicate or inaccurate data.</span></span> <span data-ttu-id="a56e5-105">Im Master Data Services-Add-In für Excel können Sie Daten aus zwei Arbeitsblättern kombinieren und die Daten dann vergleichen, um Duplikate zu identifizieren und zu entfernen, bevor Sie die Daten in MDS veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="a56e5-105">In the Master Data Services Add-in for Excel, you can combine data from two worksheets and the compare the data to identify and remove duplicates before publishing the data to MDS.</span></span> <span data-ttu-id="a56e5-106">Die Abgleichsfunktion des MDS-Add-Ins für Excel verwendet die DQS-Abgleichsfunktionalität, um Übereinstimmungen in den Daten zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="a56e5-106">The matching feature of MDS Excel Add-in uses the DQS matching functionality to identify matches in the data.</span></span> <span data-ttu-id="a56e5-107">In dieser Aufgabe kombinieren Sie Daten aus zwei Arbeitsblättern in einem Arbeitsblatt und führen dann die Abgleichsaktivität aus, um Duplikate zu identifizieren und zu entfernen, bevor Sie die Daten in MDS veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="a56e5-107">In this task, you will combine data from a two worksheets into one and then perform the matching activity to identify and remove duplicates before publishing to MDS.</span></span> <span data-ttu-id="a56e5-108">Weitere Informationen finden Sie [unter Data Quality](https://msdn.microsoft.com/library/hh548681.aspx) -Abgleich in den Themen MDS-Add-in für Excel und [Kombinieren von Daten](https://msdn.microsoft.com/library/hh548680.aspx) .</span><span class="sxs-lookup"><span data-stu-id="a56e5-108">See [Data Quality Matching in the MDS Add-in for Excel](https://msdn.microsoft.com/library/hh548681.aspx) and [Combine Data](https://msdn.microsoft.com/library/hh548680.aspx) topics for more details.</span></span>  
  
1.  <span data-ttu-id="a56e5-109">Startet eine neue Instanz von **Excel**.</span><span class="sxs-lookup"><span data-stu-id="a56e5-109">Launch new instance of **Excel**.</span></span> <span data-ttu-id="a56e5-110">Zeigen Sie im **Startmenü**auf **Ausführen**, geben Sie **Excel**ein, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a56e5-110">Click **Start**, point to **Run**, type **Excel**, and click **OK**.</span></span>  
  
2.  <span data-ttu-id="a56e5-111">Wechseln Sie zur Registerkarte **Master Daten** , indem Sie in der Menüleiste auf **Master Daten** klicken.</span><span class="sxs-lookup"><span data-stu-id="a56e5-111">Switch to the **Master Data** tab by clicking **Master Data** on the menu bar.</span></span>  
  
3.  <span data-ttu-id="a56e5-112">Klicken Sie im Menüband in der Gruppe **verbinden und laden** auf **verbinden** , um eine Verbindung mit dem **MDS-Server**herzustellen.</span><span class="sxs-lookup"><span data-stu-id="a56e5-112">Click **Connect** on the ribbon in the **Connect and Load** group to connect to the **MDS server**.</span></span> <span data-ttu-id="a56e5-113">Sie haben diese Verbindung zuvor in dieser Lektion konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="a56e5-113">You have configured this connection earlier in this lesson.</span></span>  
  
     <span data-ttu-id="a56e5-114">![Excel – Schaltfläche "Explorer anzeigen" auf der Registerkarte "Masterdaten"](../../2014/tutorials/media/et-combinematchandpublishnewsod-01.jpg "Excel – Schaltfläche "Explorer anzeigen" auf der Registerkarte "Masterdaten"")</span><span class="sxs-lookup"><span data-stu-id="a56e5-114">![Excel - Show Explorer Button on Master Data Tabl](../../2014/tutorials/media/et-combinematchandpublishnewsod-01.jpg "Excel - Show Explorer Button on Master Data Tabl")</span></span>  
  
4.  <span data-ttu-id="a56e5-115">Der Bereich **Master Daten-Explorer** auf der rechten Seite sollte angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="a56e5-115">You should see the **Master Data Explorer** pane to the right.</span></span> <span data-ttu-id="a56e5-116">Wenn die Master Daten-Explorer nicht angezeigt wird, klicken Sie im Menüband auf die Schaltfläche **Explorer anzeigen** .</span><span class="sxs-lookup"><span data-stu-id="a56e5-116">If you do not see the Master Data Explorer, click **Show Explorer** button on the ribbon.</span></span>  
  
5.  <span data-ttu-id="a56e5-117">Wählen Sie im Fenster **Master Daten-Explorer** in der Dropdown Liste für das **Modell**die Option **Suppliers** aus.</span><span class="sxs-lookup"><span data-stu-id="a56e5-117">In the **Master Data Explorer** Window, select **Suppliers** in the drop-down list for the **Model**.</span></span> <span data-ttu-id="a56e5-118">Sie sollten sehen, dass das Modell über eine Entität verfügt: **Supplier**.</span><span class="sxs-lookup"><span data-stu-id="a56e5-118">You should see that the model has one entity: **Supplier**.</span></span>  
  
     <span data-ttu-id="a56e5-119">![Excel – Master Data Explorer (Fenster)](../../2014/tutorials/media/et-combinematchandpublishnewsod-02.jpg "Excel – Master Data Explorer (Fenster)")</span><span class="sxs-lookup"><span data-stu-id="a56e5-119">![Excel - Master Data Explorer Window](../../2014/tutorials/media/et-combinematchandpublishnewsod-02.jpg "Excel - Master Data Explorer Window")</span></span>  
  
6.  <span data-ttu-id="a56e5-120">Doppelklicken Sie in der Liste Entität auf **Lieferant** , um die Entitäts Elemente in das Excel-Arbeitsblatt zu laden.</span><span class="sxs-lookup"><span data-stu-id="a56e5-120">Double-click **Supplier** in the entity list to load the entity members into the Excel worksheet.</span></span>  
  
7.  <span data-ttu-id="a56e5-121">Klicken Sie unten auf **Tabelle2** , um zur Registerkarte **Tabelle2** zu wechseln. Wenn **Tabelle2**nicht angezeigt wird, fügen Sie ein neues Arbeitsblatt hinzu.</span><span class="sxs-lookup"><span data-stu-id="a56e5-121">Click **Sheet2** at the bottom to switch to the **Sheet2** tab. If you do not see **Sheet2**, add a new worksheet.</span></span>  
  
8.  <span data-ttu-id="a56e5-122">Öffnen Sie **Suppliers.xls** Datei (die ursprüngliche Eingabedatei, die in den Tutorial-Dateien enthalten ist), und kopieren Sie alle (drei) Zeilen aus dem **combineandberberarbeitsblatt** in **Tabelle2**.</span><span class="sxs-lookup"><span data-stu-id="a56e5-122">Open **Suppliers.xls** file (the original input file that is included in the tutorial files) and copy all (three) rows from the **CombineAndCleanse** worksheet to **Sheet2**.</span></span>  
  
9. <span data-ttu-id="a56e5-123">Wechseln Sie zurück zum **Lieferanten** Blatt im **Buch 1-Microsoft Excel** (nicht zur **bereinigten und übereinstimmenden Lieferantenliste** Excel), das mit **MDS**verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="a56e5-123">Switch back to the **Supplier** sheet in the **Book 1 - Microsoft Excel** (not the **Cleansed and Matched Supplier List** Excel) that is connected to **MDS**.</span></span>  
  
10. <span data-ttu-id="a56e5-124">Klicken Sie in der Menüleiste auf **Master Daten** .</span><span class="sxs-lookup"><span data-stu-id="a56e5-124">Click **Master Data** on the menu bar.</span></span>  
  
11. <span data-ttu-id="a56e5-125">Klicken Sie im Menüband auf **Daten kombinieren** .</span><span class="sxs-lookup"><span data-stu-id="a56e5-125">Click **Combine Data** on the ribbon.</span></span> <span data-ttu-id="a56e5-126">Das Dialogfeld **Daten kombinieren** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a56e5-126">You will see the **Combine Data** dialog box.</span></span>  
  
12. <span data-ttu-id="a56e5-127">Klicken Sie im Dialogfeld **Daten kombinieren** auf die Schaltfläche neben dem Textfeld **mit MDS-Daten zu kombinierender Bereich** , wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="a56e5-127">In the **Combine Data** dialog box, click the button next to **Range to combine with MDS data** text box as shown in the following image.</span></span>  
  
     <span data-ttu-id="a56e5-128">![Excel – Daten kombinieren (Dialogfeld)](../../2014/tutorials/media/et-combinematchandpublishnewsod-03.jpg "Excel – Daten kombinieren (Dialogfeld)")</span><span class="sxs-lookup"><span data-stu-id="a56e5-128">![Excel - Combine Data Dialog Box](../../2014/tutorials/media/et-combinematchandpublishnewsod-03.jpg "Excel - Combine Data Dialog Box")</span></span>  
  
13. <span data-ttu-id="a56e5-129">Das Dialogfeld sollte jetzt verkleinert angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="a56e5-129">You should see the shrunken dialog box now.</span></span> <span data-ttu-id="a56e5-130">Klicken Sie nun auf **Tabelle2** , um zur Registerkarte **Tabelle2** zu wechseln, die die neuen Lieferantendaten mit vier Zeilen (einschließlich einer Kopfzeile) enthält.</span><span class="sxs-lookup"><span data-stu-id="a56e5-130">Now, click **Sheet2** to switch to the **Sheet2** tab that has the new supplier data with 4 rows (including one header row).</span></span>  
  
14. <span data-ttu-id="a56e5-131">Wählen Sie im **Tabelle2** **alle Zeilen einschließlich der Kopfzeile** aus (auch wenn Sie bereits ausgewählt sind).</span><span class="sxs-lookup"><span data-stu-id="a56e5-131">In the **Sheet2**, select **all rows including the header row** (even if they seem to be already selected).</span></span> <span data-ttu-id="a56e5-132">Sie sollten sehen, dass der **Bereich, der mit MDS-Daten kombiniert** werden soll, automatisch aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="a56e5-132">You should see the **Range to combine with MDS data** is automatically updated.</span></span>  
  
     <span data-ttu-id="a56e5-133">![Excel – Daten kombinieren (Dialogfeld) – minimiert](../../2014/tutorials/media/et-combinematchandpublishnewsod-04.jpg "Excel – Daten kombinieren (Dialogfeld) – minimiert")</span><span class="sxs-lookup"><span data-stu-id="a56e5-133">![Excel - Combine Data Dialog Box - Minimized](../../2014/tutorials/media/et-combinematchandpublishnewsod-04.jpg "Excel - Combine Data Dialog Box - Minimized")</span></span>  
  
15. <span data-ttu-id="a56e5-134">Wechseln Sie zurück zur Registerkarte **Suppliers** , ohne das Dialogfeld **Daten kombinieren** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="a56e5-134">Switch back to the **Suppliers** tab without closing the **Combine Data** dialog box.</span></span>  
  
16. <span data-ttu-id="a56e5-135">Klicken Sie neben dem **Textfeld**auf die **Schaltfläche** .</span><span class="sxs-lookup"><span data-stu-id="a56e5-135">Click the **button** next to the **text box**.</span></span> <span data-ttu-id="a56e5-136">Das Dialogfeld sollte jetzt erweitert angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="a56e5-136">You should see that the dialog box is expanded now.</span></span> <span data-ttu-id="a56e5-137">Alle Zuordnungen zwischen den Spalten der MDS- **Entität** " **Supplier** " und " **Excel** " werden automatisch aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="a56e5-137">You should see all the mappings between columns of the **Supplier** MDS **entity** to **Excel** columns are automatically populated.</span></span>  
  
     <span data-ttu-id="a56e5-138">![Excel – Daten kombinieren (Dialogfeld) – mit Daten gefüllt](../../2014/tutorials/media/et-combinematchandpublishnewsod-05.jpg "Excel – Daten kombinieren (Dialogfeld) – mit Daten gefüllt")</span><span class="sxs-lookup"><span data-stu-id="a56e5-138">![Excel - Combine Data Dialog Box Filled with Data](../../2014/tutorials/media/et-combinematchandpublishnewsod-05.jpg "Excel - Combine Data Dialog Box Filled with Data")</span></span>  
  
17. <span data-ttu-id="a56e5-139">Stellen Sie sicher, dass die Spalte " **Code** Entität" der Spalte " **SupplierID** " im Arbeitsblatt und die Entitäts Spalte " **ZIP-Code** " der Spalte " **ZIP** -Code" im Arbeitsblatt zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="a56e5-139">Ensure that **Code** entity column is mapped to the **SupplierID** column in the worksheet and **Zip Code** entity column is mapped to the **Zip Code** column in the worksheet.</span></span>  
  
18. <span data-ttu-id="a56e5-140">Klicken Sie im Dialogfeld **Daten kombinieren** auf **kombinieren**.</span><span class="sxs-lookup"><span data-stu-id="a56e5-140">On the **Combine Data** dialog box, click **Combine**.</span></span>  
  
19. <span data-ttu-id="a56e5-141">Überprüfen Sie, ob drei Datenzeilen am Ende des Arbeitsblatts hinzugefügt wurden und ob diese farblich codiert sind.</span><span class="sxs-lookup"><span data-stu-id="a56e5-141">Confirm that three data rows are added to the bottom of the worksheet and they should be color coded.</span></span>  
  
     <span data-ttu-id="a56e5-142">![Excel – Neue Elemente nach dem Kombinieren](../../2014/tutorials/media/et-combinematchandpublishnewsod-06.jpg "Excel – Neue Elemente nach dem Kombinieren")</span><span class="sxs-lookup"><span data-stu-id="a56e5-142">![Excel - New Elements after Combining](../../2014/tutorials/media/et-combinematchandpublishnewsod-06.jpg "Excel - New Elements after Combining")</span></span>  
  
20. <span data-ttu-id="a56e5-143">Klicken Sie im Menüband auf **mathematische Daten** , um Duplikate zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="a56e5-143">Click **Math Data** on the ribbon to identify duplicates.</span></span> <span data-ttu-id="a56e5-144">Diese Funktion verwendet die Abgleichsfunktionalität von DQS.</span><span class="sxs-lookup"><span data-stu-id="a56e5-144">This feature uses the matching functionality of DQS.</span></span>  
  
21. <span data-ttu-id="a56e5-145">Wählen Sie im Dialogfeld **Daten abgleichen** die Option **Suppliers** für die **DQS-Wissensdatenbank**aus.</span><span class="sxs-lookup"><span data-stu-id="a56e5-145">In the **Match Data** dialog box, select **Suppliers** for **DQS Knowledge Base**.</span></span>  
  
     <span data-ttu-id="a56e5-146">![Excel – Daten abgleichen (Dialogfeld)](../../2014/tutorials/media/et-combinematchandpublishnewsod-07.jpg "Excel – Daten abgleichen (Dialogfeld)")</span><span class="sxs-lookup"><span data-stu-id="a56e5-146">![Excel - Match Data Dialog Box](../../2014/tutorials/media/et-combinematchandpublishnewsod-07.jpg "Excel - Match Data Dialog Box")</span></span>  
  
22. <span data-ttu-id="a56e5-147">Ordnen Sie Arbeitsblattspalten Domänen zu, wie in der folgenden Tabelle gezeigt.</span><span class="sxs-lookup"><span data-stu-id="a56e5-147">Map worksheet columns to domains as shown in the following table.</span></span>  
  
    |<span data-ttu-id="a56e5-148">Arbeitsblattspalte</span><span class="sxs-lookup"><span data-stu-id="a56e5-148">Worksheet Column</span></span>|<span data-ttu-id="a56e5-149">Domain</span><span class="sxs-lookup"><span data-stu-id="a56e5-149">Domain</span></span>|  
    |----------------------|------------|  
    |<span data-ttu-id="a56e5-150">Code (Sie haben "Supplier ID" als Code für die Entität "Supplier" in MDS hochgeladen)</span><span class="sxs-lookup"><span data-stu-id="a56e5-150">Code (you uploaded Supplier ID as the Code for the Supplier entity in MDS)</span></span>|<span data-ttu-id="a56e5-151">Supplier ID</span><span class="sxs-lookup"><span data-stu-id="a56e5-151">Supplier ID</span></span>|  
    |<span data-ttu-id="a56e5-152">Name (Sie haben "Supplier Name" als Name für die Entität "Supplier" in MDS hochgeladen)</span><span class="sxs-lookup"><span data-stu-id="a56e5-152">Name (you uploaded Supplier Name as the Name for the Supplier entity to MDS)</span></span>|<span data-ttu-id="a56e5-153">Supplier Name</span><span class="sxs-lookup"><span data-stu-id="a56e5-153">Supplier Name</span></span>|  
    |<span data-ttu-id="a56e5-154">ContactEmailAddress</span><span class="sxs-lookup"><span data-stu-id="a56e5-154">ContactEmailAddress</span></span>|<span data-ttu-id="a56e5-155">ContactEmail</span><span class="sxs-lookup"><span data-stu-id="a56e5-155">ContactEmail</span></span>|  
  
23. <span data-ttu-id="a56e5-156">Wählen Sie **Voraussetzung** für die **Code** Spalten Zuordnung aus.</span><span class="sxs-lookup"><span data-stu-id="a56e5-156">Select **Prerequisite** for the **Code** column mapping.</span></span>  
  
24. <span data-ttu-id="a56e5-157">Geben Sie **70%** als **Gewichtung** für **Lieferanten Name** und **30%** als **Gewichtung** für die **Kontakt-e-Mail** ein, wie in der Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="a56e5-157">Enter **70%** as the **weight** for **Supplier Name** and **30%** as the **weight** for **Contact Email** as shown in the image.</span></span>  
  
25. <span data-ttu-id="a56e5-158">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a56e5-158">Click **OK**.</span></span>  
  
26. <span data-ttu-id="a56e5-159">Der Abgleichsprozess sollte ein Duplikat für den Lieferanten mit dem folgenden **Code identifizieren: S1**.</span><span class="sxs-lookup"><span data-stu-id="a56e5-159">The matching process should identify one duplicate for the supplier with **Code: S1**.</span></span>  
  
     <span data-ttu-id="a56e5-160">![Excel – Abgleichsergebnisse](../../2014/tutorials/media/et-combinematchandpublishnewsod-08.jpg "Excel – Abgleichsergebnisse")</span><span class="sxs-lookup"><span data-stu-id="a56e5-160">![Excel - Matching Results](../../2014/tutorials/media/et-combinematchandpublishnewsod-08.jpg "Excel - Matching Results")</span></span>  
  
27. <span data-ttu-id="a56e5-161">Wählen Sie die **doppelte Zeile (Orange)**, klicken Sie mit der rechten Maustaste, und klicken Sie auf **Löschen** , um die Zeile zu löschen.</span><span class="sxs-lookup"><span data-stu-id="a56e5-161">Select the **duplicate row (orange)**, right-click, and click **Delete** to delete the row.</span></span>  
  
28. <span data-ttu-id="a56e5-162">Löschen Sie die Spalte **CLUSTER_ID** , da Sie Sie nicht mehr benötigen.</span><span class="sxs-lookup"><span data-stu-id="a56e5-162">Delete the **CLUSTER_ID** column since you don't need it anymore.</span></span>  
  
29. <span data-ttu-id="a56e5-163">Klicken Sie auf **veröffentlichen** , um die anderen beiden neuen Datensätze mit den **Codes S66** und **S57** in MDS zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="a56e5-163">Click **Publish** to publish the other two new records with **Codes S66** and **S57** to MDS.</span></span>  
  
30. <span data-ttu-id="a56e5-164">Fügen Sie im Dialogfeld **veröffentlichen und** **kommentieren eine Anmerkung**hinzu, und klicken Sie auf **veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="a56e5-164">In the **Publish and Annotate** dialog box, add an **annotation**, and click **Publish**.</span></span>  
  
31. <span data-ttu-id="a56e5-165">Wechseln Sie zur **Master Data Manager-Webanwendung**.</span><span class="sxs-lookup"><span data-stu-id="a56e5-165">Switch to the **Master Data Manager Web application**.</span></span>  
  
32. <span data-ttu-id="a56e5-166">Vergewissern Sie sich, dass auf der Startseite die Option **Suppliers** für das **Modell**ausgewählt ist, und klicken Sie auf **Explorer**.</span><span class="sxs-lookup"><span data-stu-id="a56e5-166">On the home page, ensure that **Suppliers** is selected for the **Model**, and click **Explorer**.</span></span> <span data-ttu-id="a56e5-167">Wenn der **Explorer** bereits geöffnet ist, aktualisieren Sie den Internetbrowser.</span><span class="sxs-lookup"><span data-stu-id="a56e5-167">If you already have the **Explorer** open, refresh the internet browser.</span></span>  
  
33. <span data-ttu-id="a56e5-168">**Sortieren** Sie die Liste nach **Code** , und suchen Sie nach Datensätzen mit **S57** und **S66** als Codes.</span><span class="sxs-lookup"><span data-stu-id="a56e5-168">**Sort** the list by **Code** and look for records with **S57** and **S66** as codes.</span></span> <span data-ttu-id="a56e5-169">Sie können auch die **Filter** Schaltfläche auf der Symbolleiste verwenden, um nach einem bestimmten Datensatz in der Liste zu suchen.</span><span class="sxs-lookup"><span data-stu-id="a56e5-169">You can also use the **Filter** button on the toolbar to search for a specific record in the list.</span></span>  
  
34. <span data-ttu-id="a56e5-170">Schließen Sie jetzt **Mappe1-Microsoft Excel-** Fenster, ohne die Datei zu speichern.</span><span class="sxs-lookup"><span data-stu-id="a56e5-170">Now, close **Book1 - Microsoft Excel** window without saving the file.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="a56e5-171">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="a56e5-171">Next Step</span></span>  
 [<span data-ttu-id="a56e5-172">Aufgabe 5: Erstellen eines domänenbasierten Attributs aus Excel</span><span class="sxs-lookup"><span data-stu-id="a56e5-172">Task 5: Creating a Domain-Based Attribute from Excel</span></span>](../../2014/tutorials/task-5-creating-a-domain-based-attribute-from-excel.md)  
  
  
