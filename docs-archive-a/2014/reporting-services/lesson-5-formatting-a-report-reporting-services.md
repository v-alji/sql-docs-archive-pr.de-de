---
title: 'Lektion 5: Formatieren eines Berichts (Reporting Services) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: ae46efa9-6e04-48ec-afb4-5a2314dcb05a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 00f0d780e957fd9ff995fefb1d033275a7da428d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621879"
---
# <a name="lesson-5-formatting-a-report-reporting-services"></a><span data-ttu-id="c356b-102">Lektion 5: Formatieren eines Berichts (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="c356b-102">Lesson 5: Formatting a Report (Reporting Services)</span></span>
  <span data-ttu-id="c356b-103">Nachdem Sie dem Sales Orders-Bericht einen Datenbereich sowie einige Felder hinzugefügt haben, können Sie die Felder für Datum und Währung sowie die Spaltenköpfe formatieren.</span><span class="sxs-lookup"><span data-stu-id="c356b-103">Now that you've added a data region and some fields to the Sales Orders report, you can format the date and currency fields and the column headers.</span></span>  
  
 <span data-ttu-id="c356b-104">Inhalte dieses Themas:</span><span class="sxs-lookup"><span data-stu-id="c356b-104">In this topic:</span></span>  
  
-   [<span data-ttu-id="c356b-105">Formatieren des Datums</span><span class="sxs-lookup"><span data-stu-id="c356b-105">Format the Date</span></span>](#bkmk_format_date)  
  
-   [<span data-ttu-id="c356b-106">Formatieren der Währung</span><span class="sxs-lookup"><span data-stu-id="c356b-106">Format the Currency</span></span>](#bkmk_format_currency)  
  
-   [<span data-ttu-id="c356b-107">Ändern von Textart und Spaltenbreite</span><span class="sxs-lookup"><span data-stu-id="c356b-107">Change Text Style and Column Widths</span></span>](#bkmk_change_textstyle)  
  
##  <a name="format-the-date"></a><a name="bkmk_format_date"></a><span data-ttu-id="c356b-108">Formatieren des Datums</span><span class="sxs-lookup"><span data-stu-id="c356b-108">Format the Date</span></span>  
 <span data-ttu-id="c356b-109">Im Feld Date werden standardmäßig Datums- und Uhrzeitangaben angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c356b-109">The Date field displays date and time information by default.</span></span> <span data-ttu-id="c356b-110">Durch entsprechende Formatierung kann auch nur das Datum angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c356b-110">You can format it to display only the date.</span></span>  
  
#### <a name="to-format-a-date-field"></a><span data-ttu-id="c356b-111">So formatieren Sie ein Datumsfeld</span><span class="sxs-lookup"><span data-stu-id="c356b-111">To format a date field</span></span>  
  
1.  <span data-ttu-id="c356b-112">Klicken Sie auf die Registerkarte **Entwurf** .</span><span class="sxs-lookup"><span data-stu-id="c356b-112">Click the **Design** tab.</span></span>  
  
2.  <span data-ttu-id="c356b-113">Klicken Sie mit der rechten Maustaste auf die Zelle mit dem Feldausdruck `[Date]` und anschließend auf das Dialogfeld **Textfeldeigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="c356b-113">Right-click the cell with the `[Date]` field expression and then click **Text Box Properties**.</span></span>  
  
3.  <span data-ttu-id="c356b-114">Klicken Sie auf **Zahl**, und wählen Sie dann im Feld **Kategorie** den Wert aus `Date` .</span><span class="sxs-lookup"><span data-stu-id="c356b-114">Click **Number**, and then in the **Category** field, select `Date`.</span></span>  
  
4.  <span data-ttu-id="c356b-115">Wählen Sie im Feld **Typ** die Option **31. Januar 2000**aus.</span><span class="sxs-lookup"><span data-stu-id="c356b-115">In the **Type** box, select **January 31, 2000**.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="c356b-116">Zeigen Sie den Bericht in der Vorschau an, um die Änderung am Feld `[Date]` zu sehen, und wechseln Sie dann zurück zur Entwurfsansicht.</span><span class="sxs-lookup"><span data-stu-id="c356b-116">Preview the report to see the change to the `[Date]` field and then change back to design view.</span></span>  
  
##  <a name="format-the-currency"></a><a name="bkmk_format_currency"></a><span data-ttu-id="c356b-117">Formatieren der Währung</span><span class="sxs-lookup"><span data-stu-id="c356b-117">Format the Currency</span></span>  
 <span data-ttu-id="c356b-118">Im Feld LineTotal wird eine Zahl im Standardzahlenformat angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c356b-118">The LineTotal field displays a general number.</span></span> <span data-ttu-id="c356b-119">Formatieren Sie das Feld, um die Zahl als Währung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c356b-119">Format it to display the number as currency.</span></span>  
  
#### <a name="to-format-a-currency-field"></a><span data-ttu-id="c356b-120">So formatieren Sie ein Währungsfeld</span><span class="sxs-lookup"><span data-stu-id="c356b-120">To format a currency field</span></span>  
  
1.  <span data-ttu-id="c356b-121">Klicken Sie mit der rechten Maustaste auf die Zelle mit dem Feldausdruck `[LineTotal]` und anschließend auf das Dialogfeld **Textfeldeigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="c356b-121">Right-click the cell with the `[LineTotal]` field expression and then click **Text Box Properties**.</span></span>  
  
2.  <span data-ttu-id="c356b-122">Klicken Sie auf **Zahl**, und wählen Sie im Feld **Kategorie** die Option **Währung**aus.</span><span class="sxs-lookup"><span data-stu-id="c356b-122">Click **Number**, and in the **Category** field, select **Currency**.</span></span>  
  
3.  <span data-ttu-id="c356b-123">Wenn die regionale Einstellung Englisch (USA) ist, sollten folgende Standardwerte verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="c356b-123">If your regional setting is English (United States), the defaults should be:</span></span>  
  
    -   <span data-ttu-id="c356b-124">**Dezimalstellen: 2**</span><span class="sxs-lookup"><span data-stu-id="c356b-124">**Decimal places: 2**</span></span>  
  
    -   <span data-ttu-id="c356b-125">**Negative Zahlen: ($12345.00)**</span><span class="sxs-lookup"><span data-stu-id="c356b-125">**Negative numbers: ($12345.00)**</span></span>  
  
    -   <span data-ttu-id="c356b-126">**Symbol: $ Englisch (USA)**</span><span class="sxs-lookup"><span data-stu-id="c356b-126">**Symbol: $ English (United States)**</span></span>  
  
4.  <span data-ttu-id="c356b-127">Wählen Sie **1000er-Trennzeichen verwenden**aus.</span><span class="sxs-lookup"><span data-stu-id="c356b-127">Select **Use 1000 separator (,)**.</span></span>  
  
     <span data-ttu-id="c356b-128">Wenn der Beispieltext **$12,345.00**lautet, sind alle Einstellungen korrekt.</span><span class="sxs-lookup"><span data-stu-id="c356b-128">If the sample text is:**$12,345.00**, then your settings are correct.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="c356b-129">Zeigen Sie den Bericht in der Vorschau an, um die Änderung am Feld `[LineTotal]` zu sehen, und wechseln Sie dann zurück zur Entwurfsansicht.</span><span class="sxs-lookup"><span data-stu-id="c356b-129">Preview the report to see the change to the `[LineTotal]` field and then change back to design view.</span></span>  
  
##  <a name="change-text-style-and-column-widths"></a><a name="bkmk_change_textstyle"></a><span data-ttu-id="c356b-130">Ändern der Textart und der Spaltenbreite</span><span class="sxs-lookup"><span data-stu-id="c356b-130">Change Text Style and Column Widths</span></span>  
 <span data-ttu-id="c356b-131">Sie können auch die Formatierung der Kopfzeile ändern, um diese von den anderen Datenzeilen im Bericht zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="c356b-131">You can also change the formatting of the header row to differentiate it from the rows of data in the report.</span></span> <span data-ttu-id="c356b-132">Abschließend passen Sie die Breite der Spalten an.</span><span class="sxs-lookup"><span data-stu-id="c356b-132">Lastly, you will adjust the widths of the columns.</span></span>  
  
#### <a name="to-format-header-rows-and-table-columns"></a><span data-ttu-id="c356b-133">So formatieren Sie Kopfzeilen und Tabellenspalten</span><span class="sxs-lookup"><span data-stu-id="c356b-133">To format header rows and table columns</span></span>  
  
1.  <span data-ttu-id="c356b-134">Klicken Sie auf die Tabelle, damit die Spalten- und Zeilenhandles über und neben der Tabelle angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c356b-134">Click the table so that column and row handles appear above and next to the table.</span></span>  
  
     <span data-ttu-id="c356b-135">![Entwurf, Tabelle mit Kopfzeile und Detailzeile](../../2014/tutorials/media/rs-basictabledetailsdesign.gif "Entwurf, Tabelle mit Kopfzeile und Detailzeile")</span><span class="sxs-lookup"><span data-stu-id="c356b-135">![Design, Table with header row and detail row](../../2014/tutorials/media/rs-basictabledetailsdesign.gif "Design, Table with header row and detail row")</span></span>  
  
     <span data-ttu-id="c356b-136">Die grauen Balken oberhalb und neben der Tabelle stellen die Spalten- und Zeilenhandles dar.</span><span class="sxs-lookup"><span data-stu-id="c356b-136">The gray bars along the top and side of the table are the column and row handles.</span></span>  
  
2.  <span data-ttu-id="c356b-137">Zeigen Sie auf die Zeile zwischen Spaltenhandles, sodass sich der Cursor in einen Doppelpfeil ändert.</span><span class="sxs-lookup"><span data-stu-id="c356b-137">Point to the line between column handles so that the cursor changes into a double arrow.</span></span> <span data-ttu-id="c356b-138">Ziehen Sie die Spalten auf die gewünschte Größe.</span><span class="sxs-lookup"><span data-stu-id="c356b-138">Drag the columns to the size you want.</span></span>  
  
3.  <span data-ttu-id="c356b-139">Markieren Sie die Zeile mit den Spaltenkopfbezeichnungen, und zeigen Sie im Menü **Format** auf **Schriftart** . Klicken Sie dann auf **Fett**.</span><span class="sxs-lookup"><span data-stu-id="c356b-139">Select the row containing column header labels and from the **Format** menu, point to **Font** and then click **Bold**.</span></span>  
  
4.  <span data-ttu-id="c356b-140">Um die Vorschau des Berichts anzuzeigen, klicken Sie auf die Registerkarte **Vorschau** . Dies sollte etwa wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="c356b-140">To preview your report, click the **Preview** tab. It should look something like this:</span></span>  
  
     <span data-ttu-id="c356b-141">![Vorschau der Tabelle mit fett formatierten Spaltenüberschriften](../../2014/tutorials/media/rs-basictabledetailsformattedpreview.gif "Vorschau der Tabelle mit fett formatierten Spaltenüberschriften")</span><span class="sxs-lookup"><span data-stu-id="c356b-141">![Preview of table with bold column headers](../../2014/tutorials/media/rs-basictabledetailsformattedpreview.gif "Preview of table with bold column headers")</span></span>  
  
5.  <span data-ttu-id="c356b-142">Klicken Sie im Menü **Datei** auf **Alle Speichern** , um den Bericht zu speichern.</span><span class="sxs-lookup"><span data-stu-id="c356b-142">On the **File** menu, click **Save All** to save the report.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="c356b-143">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="c356b-143">Next Steps</span></span>  
 <span data-ttu-id="c356b-144">Sie haben erfolgreich Spaltenköpfe sowie Datums- und Währungswerte formatiert.</span><span class="sxs-lookup"><span data-stu-id="c356b-144">You have successfully formatted column headers and date and currency values.</span></span> <span data-ttu-id="c356b-145">Als Nächstes fügen Sie dem Bericht Gruppierungen und Gesamtwerte hinzu.</span><span class="sxs-lookup"><span data-stu-id="c356b-145">Next, you will add grouping and totals to your report.</span></span> <span data-ttu-id="c356b-146">Siehe [Lektion 6: Hinzufügen von Gruppierungen und Gesamtwerten (Reporting Services)](../reporting-services/lesson-6-adding-grouping-and-totals-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="c356b-146">See [Lesson 6: Adding Grouping and Totals &#40;Reporting Services&#41;](../reporting-services/lesson-6-adding-grouping-and-totals-reporting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c356b-147">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c356b-147">See Also</span></span>  
 <span data-ttu-id="c356b-148">[Formatieren von Zahlen und Datumsangaben &#40;Berichts-Generator und SSRS&#41;](report-design/formatting-numbers-and-dates-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c356b-148">[Formatting Numbers and Dates &#40;Report Builder and SSRS&#41;](report-design/formatting-numbers-and-dates-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="c356b-149">Renderingverhalten (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="c356b-149">Rendering Behaviors &#40;Report Builder  and SSRS&#41;</span></span>](report-design/rendering-behaviors-report-builder-and-ssrs.md)  
  
  
