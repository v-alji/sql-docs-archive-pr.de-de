---
title: Beispiele für Ausdrücke (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.prod: sql-server-2014
ms.technology: reporting-services
ms.topic: conceptual
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.reviewer: ''
ms.custom: ''
ms.date: 03/08/2017
ms.openlocfilehash: c7ef06143dafdb5034d0f6202fdc16bc51f74ca8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616407"
---
# <a name="expression-examples-report-builder-and-ssrs"></a><span data-ttu-id="dc450-102">Beispiele für Ausdrücke (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="dc450-102">Expression Examples (Report Builder and SSRS)</span></span>

<span data-ttu-id="dc450-103">Ausdrücke werden in Berichten häufig zum Steuern des Inhalts und der Darstellung des Berichts verwendet.</span><span class="sxs-lookup"><span data-stu-id="dc450-103">Expressions are used frequently in reports to control content and report appearance.</span></span> <span data-ttu-id="dc450-104">Ausdrücke werden in geschrieben [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] und können integrierte Funktionen von benutzerdefiniertem Code, Berichts-und Gruppen Variablen sowie benutzerdefinierte Variablen verwenden.</span><span class="sxs-lookup"><span data-stu-id="dc450-104">Expressions are written in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)], and can use built-in functions custom code, report and group variables, and user-defined variables.</span></span> <span data-ttu-id="dc450-105">Ausdrücke beginnen immer mit einem Gleichheitszeichen (=).</span><span class="sxs-lookup"><span data-stu-id="dc450-105">Expressions begin with an equal sign (=).</span></span> <span data-ttu-id="dc450-106">Weitere Informationen zum Ausdrucks-Editor und den Verweistypen, die Sie einfügen können, finden Sie unter [Ausdrucksverwendungen in Berichten (Berichts-Generator und SSRS)](expression-uses-in-reports-report-builder-and-ssrs.md) und [Hinzufügen eines Ausdrucks (Berichts-Generator und SSRS)](add-an-expression-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="dc450-106">For more information about the expression editor and the types of references that you can include, see [Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md), and [Add an Expression &#40;Report Builder and SSRS&#41;](add-an-expression-report-builder-and-ssrs.md).</span></span>  

> [!IMPORTANT]  
>  <span data-ttu-id="dc450-107">Bei aktiviertem RDL-Sandkasten können nur bestimmte Typen und Elemente zum Veröffentlichungszeitpunkt des Berichts im Ausdruckstext verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dc450-107">When RDL Sandboxing is enabled, only certain types and members can be used in expression text at report publish time.</span></span> <span data-ttu-id="dc450-108">Weitere Informationen finden Sie unter [Enable and Disable RDL Sandboxing](../enable-and-disable-rdl-sandboxing.md).</span><span class="sxs-lookup"><span data-stu-id="dc450-108">For more information, see [Enable and Disable RDL Sandboxing](../enable-and-disable-rdl-sandboxing.md).</span></span>  

<span data-ttu-id="dc450-109">In diesem Thema sind Beispiele für Ausdrücke enthalten, die in einem Bericht für allgemeine Aufgaben verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="dc450-109">This topic provides examples of expressions that can be used for common tasks in a report.</span></span>  

-   <span data-ttu-id="dc450-110">[Visual Basic-Funktionen](#VisualBasicFunctions) : Beispiele für Datum, Zeichenfolge, Konvertierung und bedingte [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] -Funktionen.</span><span class="sxs-lookup"><span data-stu-id="dc450-110">[Visual Basic Functions](#VisualBasicFunctions) Examples for date, string, conversion and conditional [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] functions.</span></span>  

-   <span data-ttu-id="dc450-111">[Berichtsfunktionen:](#ReportFunctions) Beispiele für Aggregate und andere integrierte Berichtsfunktionen</span><span class="sxs-lookup"><span data-stu-id="dc450-111">[Report Functions](#ReportFunctions) Examples for aggregates and other built-in report functions.</span></span>  

-   <span data-ttu-id="dc450-112">[Darstellung von Berichtsdaten](#AppearanceofReportData) : Beispiele zur Änderung der Darstellung eines Berichts.</span><span class="sxs-lookup"><span data-stu-id="dc450-112">[Appearance of Report Data](#AppearanceofReportData) Examples for changing the appearance of a report.</span></span>  

-   <span data-ttu-id="dc450-113">[Eigenschaften](#Properties) Beispiele zum Festlegen von Berichtselementeigenschaften, um Format oder Sichtbarkeit zu steuern.</span><span class="sxs-lookup"><span data-stu-id="dc450-113">[Properties](#Properties) Examples for setting report item properties to control format or visibility.</span></span>  

-   <span data-ttu-id="dc450-114">[Parameter](#Parameters) : Beispiele für die Verwendung von Parametern in einem Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="dc450-114">[Parameters](#Parameters) Examples for using parameters in an expression.</span></span>  

-   <span data-ttu-id="dc450-115">[Benutzerdefinierter Code](#CustomCode) : Beispiele für eingebetteten benutzerdefinierten Code.</span><span class="sxs-lookup"><span data-stu-id="dc450-115">[Custom Code](#CustomCode) Examples of embedded custom code.</span></span>  

<span data-ttu-id="dc450-116">Beispiele für Ausdrücke und die jeweiligen Verwendungsmöglichkeiten finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="dc450-116">For expression examples for specific uses, see the following topics:</span></span>  

-   [<span data-ttu-id="dc450-117">Beispiele für Gruppierungsausdrücke &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="dc450-117">Group Expression Examples &#40;Report Builder and SSRS&#41;</span></span>](expression-examples-report-builder-and-ssrs.md)  

-   [<span data-ttu-id="dc450-118">Beispiele für Filtergleichungen &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="dc450-118">Filter Equation Examples &#40;Report Builder and SSRS&#41;</span></span>](filter-equation-examples-report-builder-and-ssrs.md)  

-   [<span data-ttu-id="dc450-119">Häufig verwendete Filter &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="dc450-119">Commonly Used Filters &#40;Report Builder and SSRS&#41;</span></span>](commonly-used-filters-report-builder-and-ssrs.md)  

-   [<span data-ttu-id="dc450-120">Verweise auf Berichts- und Gruppenvariablensammlungen &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="dc450-120">Report and Group Variables Collections References &#40;Report Builder and SSRS&#41;</span></span>](built-in-collections-report-and-group-variables-references-report-builder.md)  

<span data-ttu-id="dc450-121">Weitere Informationen zu einfachen und komplexen Ausdrücken, zu den Verwendungsmöglichkeiten von Ausdrücken sowie zu den Verweistypen, die Sie in einen Ausdruck einbinden können, finden Sie unter [Ausdrücke &#40;Berichts-Generator und SSRS&#41;](expressions-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="dc450-121">For more information about simple and complex expressions, where you can use expressions, and the types of references that you can include in an expression, see topics under [Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md).</span></span> <span data-ttu-id="dc450-122">Weitere Informationen zum Kontext, in dem Ausdrücke zum Berechnen von Aggregaten ausgewertet werden, finden Sie unter [Ausdrucksbereich für Gesamtwerte, Aggregate und integrierte Auflistungen (Berichts-Generator und SSRS)](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="dc450-122">For more information about the context in which expressions are evaluated for calculating aggregates, see [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  

<span data-ttu-id="dc450-123">Um das Schreiben von Ausdrücken zu erlernen, die viele der Funktionen und Operatoren verwenden, die auch in den beispielhaften Ausdrücken in diesem Thema zum Schreiben von Berichten verwendet werden, finden Sie weitere Informationen unter [Tutorial: Introducing Expressions](../tutorial-introducing-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="dc450-123">To learn how to write expressions that use many of the functions and operators also used by expression examples in this topic, but in the context of writing a report, see [Tutorial: Introducing Expressions](../tutorial-introducing-expressions.md).</span></span>  

<span data-ttu-id="dc450-124">Der Ausdrucks-Editor schließt eine hierarchische Sicht der integrierten Funktionen mit ein.</span><span class="sxs-lookup"><span data-stu-id="dc450-124">The expression editor includes a hierarchical view of built-in functions.</span></span> <span data-ttu-id="dc450-125">Wenn Sie die Funktion auswählen, wird im Wertebereich ein Codebeispiel angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dc450-125">When you select the function, a code example appears in the Values pane.</span></span> <span data-ttu-id="dc450-126">Weitere Informationen finden Sie im Dialogfeld [Ausdruck](../expression-dialog-box.md) oder [Dialogfeld Ausdruck &#40;Berichts-Generator&#41;](../expression-dialog-box-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="dc450-126">For more information, see the [Expression Dialog Box](../expression-dialog-box.md) or [Expression Dialog Box &#40;Report Builder&#41;](../expression-dialog-box-report-builder.md).</span></span>  

## <a name="functions"></a><span data-ttu-id="dc450-127">Functions</span><span class="sxs-lookup"><span data-stu-id="dc450-127">Functions</span></span>  

<span data-ttu-id="dc450-128">Viele Ausdrücke in einem Bericht enthalten Funktionen.</span><span class="sxs-lookup"><span data-stu-id="dc450-128">Many expressions in a report contain functions.</span></span> <span data-ttu-id="dc450-129">Mit diesen Funktionen können Sie Daten formatieren, Code anwenden und auf Berichtsmetadaten zugreifen.</span><span class="sxs-lookup"><span data-stu-id="dc450-129">You can format data, apply logic, and access report metadata using these functions.</span></span> <span data-ttu-id="dc450-130">Sie können Ausdrücke schreiben, die Funktionen aus der [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] Lauf Zeit Bibliothek und aus den <xref:System.Convert> -und- <xref:System.Math> Namespaces verwenden.</span><span class="sxs-lookup"><span data-stu-id="dc450-130">You can write expressions that use functions from the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] run-time library, and from the <xref:System.Convert> and <xref:System.Math> namespaces.</span></span> <span data-ttu-id="dc450-131">Sie können Verweise auf Funktionen aus anderen Assemblys oder benutzerdefinierten Code hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="dc450-131">You can add references to functions from other assemblies or custom code.</span></span> <span data-ttu-id="dc450-132">Sie können auch Klassen aus verwenden [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] , einschließlich <xref:System.Text.RegularExpressions> .</span><span class="sxs-lookup"><span data-stu-id="dc450-132">You can also use classes from the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], including <xref:System.Text.RegularExpressions>.</span></span>  

###  <a name="visual-basic-functions"></a><a name="VisualBasicFunctions"></a> <span data-ttu-id="dc450-133">Visual Basic-Funktionen</span><span class="sxs-lookup"><span data-stu-id="dc450-133">Visual Basic Functions</span></span>  
<span data-ttu-id="dc450-134">Mit [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] -Funktionen können Sie die Daten bearbeiten, die in Textfeldern angezeigt oder für Parameter, Eigenschaften oder sonstige Bereiche des Berichts verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dc450-134">You can use [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] functions to manipulate the data that is displayed in text boxes or that is used for parameters, properties, or other areas of the report.</span></span> <span data-ttu-id="dc450-135">In diesem Abschnitt werden Beispiele zur Veranschaulichung einiger dieser Funktionen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="dc450-135">This section provides examples demonstrating some of these functions.</span></span> <span data-ttu-id="dc450-136">Weitere Informationen finden Sie unter [Member der Visual Basic-Laufzeitbibliothek](https://go.microsoft.com/fwlink/?LinkId=198941) bei MSDN.</span><span class="sxs-lookup"><span data-stu-id="dc450-136">For more information, see [Visual Basic Runtime Library Members](https://go.microsoft.com/fwlink/?LinkId=198941) on MSDN.</span></span>  

<span data-ttu-id="dc450-137">Der [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] bietet zahlreiche benutzerdefinierte Formatoptionen, z. B. für bestimmte Datumsformate.</span><span class="sxs-lookup"><span data-stu-id="dc450-137">The [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] provides many custom format options, for example, for specific date formats.</span></span> <span data-ttu-id="dc450-138">Weitere Informationen finden Sie unter [Formatierung von Typen](https://go.microsoft.com/fwlink/?LinkId=112024) auf MSDN.</span><span class="sxs-lookup"><span data-stu-id="dc450-138">For more information, see [Formatting Types](https://go.microsoft.com/fwlink/?LinkId=112024) on MSDN.</span></span>  

#### <a name="math-functions"></a><span data-ttu-id="dc450-139">Mathematische Funktionen</span><span class="sxs-lookup"><span data-stu-id="dc450-139">Math Functions</span></span>  

-   <span data-ttu-id="dc450-140">Die `Round`-Funktion ermöglicht das Runden von Zahlen auf die nächste ganze Zahl.</span><span class="sxs-lookup"><span data-stu-id="dc450-140">The `Round` function is useful to round numbers to the nearest integer.</span></span> <span data-ttu-id="dc450-141">Mit dem folgenden Ausdruck wird der Wert 1,3 auf 1 abgerundet:</span><span class="sxs-lookup"><span data-stu-id="dc450-141">The following expression rounds a 1.3 to 1:</span></span>  

```  
= Round(1.3)  
```  

<span data-ttu-id="dc450-142">Sie können auch einen Ausdruck schreiben, um einen Wert auf ein von Ihnen angegebenes Vielfaches zu runden (vergleichbar mit der `MRound`-Funktion in Excel).</span><span class="sxs-lookup"><span data-stu-id="dc450-142">You can also write an expression to round a value to a multiple that you specify, similar to the `MRound` function in Excel.</span></span> <span data-ttu-id="dc450-143">Multiplizieren Sie den Wert mit einem Faktor, der eine ganze Zahl erzeugt, runden Sie die Zahl, und dividieren Sie dann durch den gleichen Faktor.</span><span class="sxs-lookup"><span data-stu-id="dc450-143">Multiply the value by a factor that creates an integer, round the number, and then divide by the same factor.</span></span> <span data-ttu-id="dc450-144">Verwenden Sie z. B. den folgenden Ausdruck, um 1,3 auf das nächste Vielfache von 0,2 (1,4) zu runden:</span><span class="sxs-lookup"><span data-stu-id="dc450-144">For example, to round 1.3 to the nearest multiple of .2 (1.4), use the following expression:</span></span>  

```  
= Round(1.3*5)/5  
```  

####  <a name="date-functions"></a><a name="DateFunctions"></a><span data-ttu-id="dc450-145">Datumsfunktionen</span><span class="sxs-lookup"><span data-stu-id="dc450-145">Date Functions</span></span>  

-   <span data-ttu-id="dc450-146">Die `Today`-Funktion stellt das aktuelle Datum bereit.</span><span class="sxs-lookup"><span data-stu-id="dc450-146">The `Today` function provides the current date.</span></span> <span data-ttu-id="dc450-147">Mit diesem Ausdruck können Sie in einem Textfeld das Datum im Bericht anzeigen oder aber in einem Parameter Daten basierend auf dem aktuellen Datum filtern.</span><span class="sxs-lookup"><span data-stu-id="dc450-147">This expression can be used in a text box to display the date on the report, or in a parameter to filter data based on the current date.</span></span>  

```  
=Today()  
```  

-   <span data-ttu-id="dc450-148">Mit der `DateAdd`-Funktion wird ein Datumsbereich basierend auf einem einzigen Parameter bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="dc450-148">The `DateAdd` function is useful for supplying a range of dates based on a single parameter.</span></span> <span data-ttu-id="dc450-149">Der folgende Ausdruck liefert das Datum des Tages, der sechs Monate nach dem Datum des *StartDate*-Parameters liegt.</span><span class="sxs-lookup"><span data-stu-id="dc450-149">The following expression provides a date that is six months after the date from a parameter named *StartDate*.</span></span>  

```  
=DateAdd(DateInterval.Month, 6, Parameters!StartDate.Value)  
```  

-   <span data-ttu-id="dc450-150">Die `Year`-Funktion zeigt das Jahr für ein bestimmtes Datum an.</span><span class="sxs-lookup"><span data-stu-id="dc450-150">The `Year` function displays the year for a particular date.</span></span> <span data-ttu-id="dc450-151">Hiermit können Sie Datumsangaben zusammenfassen oder die Jahreszahl für eine Datumsgruppe anzeigen.</span><span class="sxs-lookup"><span data-stu-id="dc450-151">You can use this to group dates together or to display the year as a label for a set of dates.</span></span> <span data-ttu-id="dc450-152">Dieser Ausdruck liefert das Jahr für eine bestimmte Gruppe von Bestelldaten.</span><span class="sxs-lookup"><span data-stu-id="dc450-152">This expression provides the year for a given group of sales order dates.</span></span> <span data-ttu-id="dc450-153">Mit der `Month`-Funktion und anderen Funktionen können Datumsangaben auch bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="dc450-153">The `Month` function and other functions can also be used to manipulate dates.</span></span> <span data-ttu-id="dc450-154">Weitere Informationen finden Sie in der Dokumentation zu [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dc450-154">For more information, see the [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] documentation.</span></span>  

```  
=Year(Fields!OrderDate.Value)  
```  

-   <span data-ttu-id="dc450-155">Sie können Funktionen in einem Ausdruck kombinieren, um das Format anzupassen.</span><span class="sxs-lookup"><span data-stu-id="dc450-155">You can combine functions in an expression to customize the format.</span></span> <span data-ttu-id="dc450-156">Durch den folgenden Ausdruck wird das Format Monat-Tag-Jahr eines Datums in das Format Monat-Woche-Woche geändert.</span><span class="sxs-lookup"><span data-stu-id="dc450-156">The following expression changes the format of a date in the form month-day-year to month-week-week number.</span></span> <span data-ttu-id="dc450-157">12/23/2009 wird z. B. in Dezember Woche 3 geändert:</span><span class="sxs-lookup"><span data-stu-id="dc450-157">For example, 12/23/2009 to December Week 3:</span></span>  

```  
=Format(Fields!MyDate.Value, "MMMM") & " Week " &   
(Int(DateDiff("d", DateSerial(Year(Fields!MyDate.Value),   
Month(Fields!MyDate.Value),1), Fields!FullDateAlternateKey.Value)/7)+1).ToString  
```  

<span data-ttu-id="dc450-158">Bei Verwendung als berechnetes Feld in einem Dataset können Sie diesen Ausdruck für ein Diagramm verwenden, um Werte nach der Woche in jedem Monat zu aggregieren.</span><span class="sxs-lookup"><span data-stu-id="dc450-158">When used as a calculated field in a dataset, you can use this expression on a chart to aggregate values by week within each month.</span></span>  

-   <span data-ttu-id="dc450-159">Der folgende Ausdruck legt für den SellStartDate-Wert das Format MMM-YY fest.</span><span class="sxs-lookup"><span data-stu-id="dc450-159">The following expression formats the SellStartDate value as MMM-YY.</span></span> <span data-ttu-id="dc450-160">Beim SellStartDate-Feld handelt es sich um einen datetime-Datentyp.</span><span class="sxs-lookup"><span data-stu-id="dc450-160">SellStartDate field is a datetime data type.</span></span>  

```  
=FORMAT(Fields!SellStartDate.Value, "MMM-yy")  
```  

-   <span data-ttu-id="dc450-161">Der folgende Ausdruck legt für den SellStartDate-Wert das Format dd/MM/yyyy fest.</span><span class="sxs-lookup"><span data-stu-id="dc450-161">The following expression formats the SellStartDate value as dd/MM/yyyy.</span></span> <span data-ttu-id="dc450-162">Beim SellStartDate-Feld handelt es sich um einen datetime-Datentyp.</span><span class="sxs-lookup"><span data-stu-id="dc450-162">The SellStartDate field is a datetime data type.</span></span>  

```  
=FORMAT(Fields!SellStartDate.Value, "dd/MM/yyyy")  
```  

-   <span data-ttu-id="dc450-163">Die `CDate`-Funktion konvertiert den Wert in ein Datum.</span><span class="sxs-lookup"><span data-stu-id="dc450-163">The `CDate` function converts the value to a date.</span></span> <span data-ttu-id="dc450-164">Die `Now`-Funktion gibt einen Datumswert zurück, der das aktuelle Datum und die aktuelle Uhrzeit des Systems enthält.</span><span class="sxs-lookup"><span data-stu-id="dc450-164">The `Now` function returns a date value containing the current date and time according to your system.</span></span> <span data-ttu-id="dc450-165">`DateDiff` gibt einen Long-Wert zurück, der die Zahl der Zeitintervalle zwischen zwei Datumswerten angibt.</span><span class="sxs-lookup"><span data-stu-id="dc450-165">`DateDiff` returns a Long value specifying the number of time intervals between two Date values.</span></span>  

<span data-ttu-id="dc450-166">Im folgenden Beispiel wird das Anfangsdatum des aktuellen Jahres angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dc450-166">The following example displays the start date of the current year</span></span>  

```  
=DateAdd(DateInterval.Year,DateDiff(DateInterval.Year,CDate("01/01/1900"),Now()),CDate("01/01/1900"))  
```  

-   <span data-ttu-id="dc450-167">Im folgenden Beispiel wird das Anfangsdatum des vorherigen Monats basierend auf dem aktuellen Monat angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dc450-167">The following example displays the start date for the previous month based on the current month.</span></span>  

```  
=DateAdd(DateInterval.Month,DateDiff(DateInterval.Month,CDate("01/01/1900"),Now())-1,CDate("01/01/1900"))  
```  

-   <span data-ttu-id="dc450-168">Der folgende Ausdruck generiert die Jahre des Intervalls zwischen SellStartDate und LastReceiptDate.</span><span class="sxs-lookup"><span data-stu-id="dc450-168">The following expression generates the interval years between SellStartDate and LastReceiptDate.</span></span> <span data-ttu-id="dc450-169">Diese Felder sind in zwei unterschiedlichen Datasets enthalten, DataSet1 und DataSet2.</span><span class="sxs-lookup"><span data-stu-id="dc450-169">These fields are in two different datasets, DataSet1 and DataSet2.</span></span> <span data-ttu-id="dc450-170">Die Aggregatfunktion [First-Funktion (Berichts-Generator und SSRS)](report-builder-functions-first-function.md) gibt den ersten Wert von SellStartDate in DataSet1 und den ersten Wert von LastReceiptDate in DataSet2 zurück.</span><span class="sxs-lookup"><span data-stu-id="dc450-170">The [First Function &#40;Report Builder and SSRS&#41;](report-builder-functions-first-function.md), which is an aggregate function, returns the first value of SellStartDate in DataSet1 and the first value of LastReceiptDate in DataSet2.</span></span>  

```  
=DATEDIFF("yyyy", First(Fields!SellStartDate.Value, "DataSet1"), First(Fields!LastReceiptDate.Value, "DataSet2"))  
```  

-   <span data-ttu-id="dc450-171">Die Funktion `DatePart` gibt einen ganzzahligen Wert zurück, der die angegebene Komponente eines bestimmten Date-Werts enthält. Der folgende Ausdruck gibt das Jahr für den ersten Wert von SellStartDate in DataSet1 zurück.</span><span class="sxs-lookup"><span data-stu-id="dc450-171">The `DatePart` function returns an Integer value containing the specified component of a given Date value.The following expression returns the year for the first value of the SellStartDate in DataSet1.</span></span> <span data-ttu-id="dc450-172">Der Datasetbereich ist angegeben, weil mehrere Datasets im Bericht enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="dc450-172">The dataset scope is specified because there are multiple datasets in the report.</span></span>  

```  
=Datepart("yyyy", First(Fields!SellStartDate.Value, "DataSet1"))  

```  

-   <span data-ttu-id="dc450-173">Die Funktion `DateSerial` gibt ein Date-Wert zurück, der das angegebene Jahr, den angegebenen Monat und Tag mit der auf Mitternacht festgelegten Zeitinformation darstellt.</span><span class="sxs-lookup"><span data-stu-id="dc450-173">The `DateSerial` function returns a Date value representing a specified year, month, and day, with the time information set to midnight.</span></span> <span data-ttu-id="dc450-174">Im folgenden Beispiel wird das Enddatum des vorherigen Monats basierend auf dem aktuellen Monat angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dc450-174">The following example displays the ending date for the prior month, based on the current month.</span></span>  

```  
=DateSerial(Year(Now()), Month(Now()), "1").AddDays(-1)  
```  

-   <span data-ttu-id="dc450-175">Mit den folgenden Ausdrücken werden unterschiedliche Datumsangaben basierend auf dem vom Benutzer ausgewählten date-Parameter angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dc450-175">The following expressions display various dates based on a date parameter value selected by the user.</span></span>  

|<span data-ttu-id="dc450-176">Beispielbeschreibung</span><span class="sxs-lookup"><span data-stu-id="dc450-176">Example Description</span></span>|<span data-ttu-id="dc450-177">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dc450-177">Example</span></span>|  
|-------------------------|-------------|  
|<span data-ttu-id="dc450-178">gestern</span><span class="sxs-lookup"><span data-stu-id="dc450-178">Yesterday</span></span>|`=DateSerial(Year(Parameters!TodaysDate.Value),Month(Parameters!TodaysDate.Value),Day(Parameters!TodaysDate.Value)-1)`|  
|<span data-ttu-id="dc450-179">Vor zwei Tagen</span><span class="sxs-lookup"><span data-stu-id="dc450-179">Two Days Ago</span></span>|`=DateSerial(Year(Parameters!TodaysDate.Value),Month(Parameters!TodaysDate.Value),Day(Parameters!TodaysDate.Value)-2)`|  
|<span data-ttu-id="dc450-180">Vor einem Monat</span><span class="sxs-lookup"><span data-stu-id="dc450-180">One Month Ago</span></span>|`=DateSerial(Year(Parameters!TodaysDate.Value),Month(Parameters!TodaysDate.Value)-1,Day(Parameters!TodaysDate.Value))`|  
|<span data-ttu-id="dc450-181">Vor zwei Monaten</span><span class="sxs-lookup"><span data-stu-id="dc450-181">Two Months Ago</span></span>|`=DateSerial(Year(Parameters!TodaysDate.Value),Month(Parameters!TodaysDate.Value)-2,Day(Parameters!TodaysDate.Value))`|  
|<span data-ttu-id="dc450-182">Vor einem Jahr</span><span class="sxs-lookup"><span data-stu-id="dc450-182">One Year Ago</span></span>|`=DateSerial(Year(Parameters!TodaysDate.Value)-1,Month(Parameters!TodaysDate.Value),Day(Parameters!TodaysDate.Value))`|  
|<span data-ttu-id="dc450-183">Vor zwei Jahren</span><span class="sxs-lookup"><span data-stu-id="dc450-183">Two Years Ago</span></span>|`=DateSerial(Year(Parameters!TodaysDate.Value)-2,Month(Parameters!TodaysDate.Value),Day(Parameters!TodaysDate.Value))`|  

####  <a name="string-functions"></a><a name="StringFunctions"></a><span data-ttu-id="dc450-184">Zeichen folgen Funktionen</span><span class="sxs-lookup"><span data-stu-id="dc450-184">String Functions</span></span>  

-   <span data-ttu-id="dc450-185">Mithilfe von Verkettungsoperatoren und [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] -Konstanten können Sie mehrere Felder kombinieren.</span><span class="sxs-lookup"><span data-stu-id="dc450-185">Combine more than one field by using concatenation operators and [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] constants.</span></span> <span data-ttu-id="dc450-186">Der folgende Ausdruck gibt zwei Felder zurück, die sich jeweils in einer eigenen Zeile in demselben Textfeld befinden.</span><span class="sxs-lookup"><span data-stu-id="dc450-186">The following expression returns two fields, each on a separate line in the same text box:</span></span>  

```  
=Fields!FirstName.Value & vbCrLf & Fields!LastName.Value   
```  

-   <span data-ttu-id="dc450-187">Mit der `Format`-Funktion können Sie Datumsangaben und Zahlen in einer Zeichenfolge formatieren.</span><span class="sxs-lookup"><span data-stu-id="dc450-187">Format dates and numbers in a string with the `Format` function.</span></span> <span data-ttu-id="dc450-188">Mit dem folgenden Ausdruck werden Werte des *StartDate* -Parameters und des *EndDate* -Parameters im langen Datumsformat angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dc450-188">The following expression displays values of the *StartDate* and *EndDate* parameters in long date format:</span></span>  

```  
=Format(Parameters!StartDate.Value, "D") & " through " &  Format(Parameters!EndDate.Value, "D")    
```  

<span data-ttu-id="dc450-189">Wenn das Textfeld nur ein Datum oder eine Zahl enthält, sollten Sie die Format-Eigenschaft des Textfelds verwenden, um anstelle der `Format` Funktion innerhalb des Textfelds eine Formatierung anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="dc450-189">If the text box contains only a date or number, you should use the Format property of the text box to apply formatting instead of the `Format` function within the text box.</span></span>  

-   <span data-ttu-id="dc450-190">Die `Right` `Len` Funktionen, und `InStr` sind nützlich, um eine Teil Zeichenfolge zurückzugeben, z. b. den *Domänen* \\ *Benutzer* Namen auf den Benutzernamen zu verkürzen.</span><span class="sxs-lookup"><span data-stu-id="dc450-190">The `Right`, `Len`, and `InStr` functions are useful for returning a substring, for example, trimming *DOMAIN*\\*username* to just the user name.</span></span> <span data-ttu-id="dc450-191">Der folgende Ausdruck gibt den Teil der Zeichenfolge rechts neben einem umgekehrten Schrägstrich (\\) des *User*-Parameters zurück:</span><span class="sxs-lookup"><span data-stu-id="dc450-191">The following expression returns the part of the string to the right of a backslash (\\) character from a parameter named *User*:</span></span>  

```  
=Right(Parameters!User.Value, Len(Parameters!User.Value) - InStr(Parameters!User.Value, "\"))  
```  

<span data-ttu-id="dc450-192">Der folgende Ausdruck ergibt denselben Wert wie der vorherige, wobei Member der- [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] <xref:System.String> Klasse anstelle von-Funktionen verwendet werden [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="dc450-192">The following expression results in the same value as the previous one, using members of the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] <xref:System.String> class instead of [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] functions:</span></span>  

```  
=Parameters!User.Value.Substring(Parameters!User.Value.IndexOf("\")+1, Parameters!User.Value.Length-Parameters!User.Value.IndexOf("\")-1)  
```  

-   <span data-ttu-id="dc450-193">Die ausgewählten Werte aus einem mehrwertigen Parameter können angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="dc450-193">Display the selected values from a multivalue parameter.</span></span> <span data-ttu-id="dc450-194">Im folgenden Beispiel wird die- `Join` Funktion verwendet, um die ausgewählten Werte des-Parameters *MySelection* zu einer einzelnen Zeichenfolge zu verketten, die als Ausdruck für den Wert eines Textfelds in einem Berichts Element festgelegt werden kann:</span><span class="sxs-lookup"><span data-stu-id="dc450-194">The following example uses the `Join` function to concatenate the selected values of the parameter *MySelection* into a single string that can be set as an expression for the value of a text box in a report item:</span></span>  

```  
= Join(Parameters!MySelection.Value)  
```  

<span data-ttu-id="dc450-195">Das folgende Beispiel hat die gleiche Funktion wie das Beispiel oben und zeigt darüber hinaus vor der Liste der ausgewählten Werte eine Textzeichenfolge an:</span><span class="sxs-lookup"><span data-stu-id="dc450-195">The following example does the same as the above example, as well as displays a text string prior to the list of selected values.</span></span>  

```  
="Report for " & JOIN(Parameters!MySelection.Value, " & ")  

```  

-   <span data-ttu-id="dc450-196">Die `Regex` Funktionen von [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] <xref:System.Text.RegularExpressions> sind nützlich, um das Format vorhandener Zeichen folgen zu ändern, z. b. das Formatieren einer Telefonnummer.</span><span class="sxs-lookup"><span data-stu-id="dc450-196">The `Regex` functions from the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] <xref:System.Text.RegularExpressions> are useful for changing the format of existing strings, for example, formatting a telephone number.</span></span> <span data-ttu-id="dc450-197">Der folgende Ausdruck verwendet die- `Replace` Funktion, um das Format einer zehnstelligen Telefonnummer in ein Feld von "*nnn* - *nnn* - *nnnn*" in "(*nnn*) *nnn* - *nnnn*" zu ändern:</span><span class="sxs-lookup"><span data-stu-id="dc450-197">The following expression uses the `Replace` function to change the format of a ten-digit telephone number in a field from "*nnn*-*nnn*-*nnnn*" to "(*nnn*) *nnn*-*nnnn*":</span></span>  

```  
=System.Text.RegularExpressions.Regex.Replace(Fields!Phone.Value, "(\d{3})[ -.]*(\d{3})[ -.]*(\d{4})", "($1) $2-$3")  
```  

> [!NOTE]  
>  <span data-ttu-id="dc450-198">Überprüfen Sie, ob der Wert für Fields!Phone.Value unter Umständen zusätzliche Leerzeichen enthält und vom Typ <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="dc450-198">Verify that the value for Fields!Phone.Value has no extra spaces and is of type <xref:System.String>.</span></span>  

#### <a name="lookup"></a><span data-ttu-id="dc450-199">Nachschlagen</span><span class="sxs-lookup"><span data-stu-id="dc450-199">Lookup</span></span>  

-   <span data-ttu-id="dc450-200">Durch Angabe eines Schlüsselfelds können Sie mit der `Lookup`-Funktion einen Wert von einem Dataset für eine 1:1-Beziehung, zum Beispiel ein Schlüssel-Wert-Paar, abrufen.</span><span class="sxs-lookup"><span data-stu-id="dc450-200">By specifying a key field, you can use the `Lookup` function to retrieve a value from a dataset for a one-to-one relationship, for example, a key-value pair.</span></span> <span data-ttu-id="dc450-201">Der folgende Ausdruck zeigt den Produktnamen aus einem Dataset („Product“) an, wenn der Produktbezeichner als Grundlage für die Übereinstimmung angegeben ist:</span><span class="sxs-lookup"><span data-stu-id="dc450-201">The following expression displays the product name from a dataset ("Product"), given the product identifier to match on:</span></span>  

```  
=Lookup(Fields!PID.Value, Fields!ProductID.Value, Fields!ProductName.Value, "Product")  
```  

#### <a name="lookupset"></a><span data-ttu-id="dc450-202">LookupSet</span><span class="sxs-lookup"><span data-stu-id="dc450-202">LookupSet</span></span>  

-   <span data-ttu-id="dc450-203">Indem Sie ein Schlüsselfeld angeben, können Sie mithilfe der `LookupSet`-Funktion einen Satz von Werten für eine 1:n-Beziehung aus einem Dataset abrufen.</span><span class="sxs-lookup"><span data-stu-id="dc450-203">By specifying a key field, you can use the `LookupSet` function to retrieve a set of values from a dataset for a one-to-many relationship.</span></span> <span data-ttu-id="dc450-204">Beispiel: Eine Person kann mehrere Telefonnummern haben.</span><span class="sxs-lookup"><span data-stu-id="dc450-204">For example, a person can have multiple telephone numbers.</span></span> <span data-ttu-id="dc450-205">Nehmen Sie im folgenden Beispiel an, dass das Dataset PhoneList in jeder Zeile einen Personenbezeichner und eine Telefonnummer enthält.</span><span class="sxs-lookup"><span data-stu-id="dc450-205">In the following example, assume the dataset PhoneList contains a person identifier and a telephone number in each row.</span></span> <span data-ttu-id="dc450-206">`LookupSet` gibt ein Array von Werten zurück.</span><span class="sxs-lookup"><span data-stu-id="dc450-206">`LookupSet` returns an array of values.</span></span> <span data-ttu-id="dc450-207">Der folgende Ausdruck kombiniert die Rückgabewerte in eine einzelne Zeichenfolge und zeigt die Liste der Telefonnummern für die mit "ContactID" angegebene Person an:</span><span class="sxs-lookup"><span data-stu-id="dc450-207">The following expression combines the return values into a single string and displays the list of telephone numbers for the person specified by ContactID:</span></span>  

```  
=Join(LookupSet(Fields!ContactID.Value, Fields!PersonID.Value, Fields!PhoneNumber.Value, "PhoneList"),",")  
```  

####  <a name="conversion-functions"></a><a name="ConversionFunctions"></a><span data-ttu-id="dc450-208">Konvertierungs Funktionen</span><span class="sxs-lookup"><span data-stu-id="dc450-208">Conversion Functions</span></span>  
<span data-ttu-id="dc450-209">Mithilfe der [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] -Funktionen können Sie einen Wert von einem Datentyp in einen anderen Datentyp konvertieren.</span><span class="sxs-lookup"><span data-stu-id="dc450-209">You can use [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] functions to convert a field from the one data type to a different data type.</span></span> <span data-ttu-id="dc450-210">Konvertierungsfunktionen können zum Konvertieren des Standarddatentyps für ein Feld in einen Datentyp verwendet werden, der für Berechnungen oder zum Kombinieren von Text erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="dc450-210">Conversion functions can be used to convert the default data type for a field to the data type needed for calculations or to combine text.</span></span>  

-   <span data-ttu-id="dc450-211">Mit dem folgenden Ausdruck wird die Konstante 500 in den Typ "Decimal" konvertiert, um sie mit einem [!INCLUDE[tsql](../../includes/tsql-md.md)] money-Datentyp im Feld "Wert" für einen Filterausdruck zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="dc450-211">The following expression converts the constant 500 to type Decimal in order to compare it to a [!INCLUDE[tsql](../../includes/tsql-md.md)] money data type in the Value field for a filter expression.</span></span>  

```  
=CDec(500)  
```  

-   <span data-ttu-id="dc450-212">Mit dem folgenden Ausdruck wird die Anzahl der für den mehrwertigen *MySelection*-Parameter ausgewählten Werte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dc450-212">The following expression displays the number of values selected for the multivalue parameter *MySelection*.</span></span>  

```  
=CStr(Parameters!MySelection.Count)  
```  

####  <a name="decision-functions"></a><a name="DecisionFunctions"></a> <span data-ttu-id="dc450-213">Entscheidungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="dc450-213">Decision Functions</span></span>  

-   <span data-ttu-id="dc450-214">Die `Iif`-Funktion gibt einen von zwei Werten zurück, und zwar abhängig davon, ob der Ausdruck mit TRUE ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="dc450-214">The `Iif` function returns one of two values depending on whether the expression is true or not.</span></span> <span data-ttu-id="dc450-215">Im folgenden Ausdruck wird mit der `Iif`-Funktion der boolesche Wert `True` zurückgegeben, falls der Wert von `LineTotal` 100 überschreitet.</span><span class="sxs-lookup"><span data-stu-id="dc450-215">The following expression uses the `Iif` function to return a Boolean value of `True` if the value of `LineTotal` exceeds 100.</span></span> <span data-ttu-id="dc450-216">Andernfalls wird `False` zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="dc450-216">Otherwise it returns `False`:</span></span>  

```  
=IIF(Fields!LineTotal.Value > 100, True, False)  
```  

-   <span data-ttu-id="dc450-217">Verwenden Sie mehrere `IIF`-Funktionen (die auch als "geschachtelte Iif-Funktionen" bezeichnet werden), um einen von drei Werten in Abhängigkeit vom Wert von `PctComplete` zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="dc450-217">Use multiple `IIF` functions (also known as "nested IIFs") to return one of three values depending on the value of `PctComplete`.</span></span> <span data-ttu-id="dc450-218">Der folgende Ausdruck kann in die Füllfarbe eines Textfelds platziert werden, um die Hintergrundfarbe basierend auf dem Wert im Textfeld zu ändern.</span><span class="sxs-lookup"><span data-stu-id="dc450-218">The following expression can be placed in the fill color of a text box to change the background color depending on the value in the text box.</span></span>  

```  
=IIF(Fields!PctComplete.Value >= 10, "Green", IIF(Fields!PctComplete.Value >= 1, "Blue", "Red"))  
```  

<span data-ttu-id="dc450-219">Werte, die größer oder gleich 10 sind, werden mit einem grünen Hintergrund angezeigt. Werte zwischen 1 und 9 erhalten einen blauen Hintergrund, und Werte kleiner als 1 werden mit rotem Hintergrund dargestellt.</span><span class="sxs-lookup"><span data-stu-id="dc450-219">Values greater than or equal to 10 display with a green background, between 1 and 9 display with a blue background, and less than 1 display with a red background.</span></span>  

-   <span data-ttu-id="dc450-220">Eine andere Möglichkeit, die gleiche Funktionalität zu erhalten, bietet die `Switch`-Funktion.</span><span class="sxs-lookup"><span data-stu-id="dc450-220">A different way to get the same functionality uses the `Switch` function.</span></span> <span data-ttu-id="dc450-221">Die `Switch`-Funktion ist nützlich, wenn Sie drei oder mehr Bedingungen testen müssen.</span><span class="sxs-lookup"><span data-stu-id="dc450-221">The `Switch` function is useful when you have three or more conditions to test.</span></span> <span data-ttu-id="dc450-222">Die `Switch`-Funktion gibt den Wert zurück, der mit dem ersten Ausdruck in einer Reihe verknüpft ist, die mit TRUE ausgewertet wird:</span><span class="sxs-lookup"><span data-stu-id="dc450-222">The `Switch` function returns the value associated with the first expression in a series that evaluates to true:</span></span>  

```  
=Switch(Fields!PctComplete.Value >= 10, "Green", Fields!PctComplete.Value >= 1, "Blue", Fields!PctComplete.Value = 1, "Yellow", Fields!PctComplete.Value <= 0, "Red",)  
```  

<span data-ttu-id="dc450-223">Werte, die größer oder gleich 10 sind, werden mit einem grünen Hintergrund angezeigt. Werte zwischen 1 und 9 erhalten einen blauen Hintergrund, Werte, die gleich 1 sind, einen gelben Hintergrund, und Werte, die 0 oder kleiner sind, werden mit einem roten Hintergrund dargestellt.</span><span class="sxs-lookup"><span data-stu-id="dc450-223">Values greater than or equal to 10 display with a green background, between 1 and 9 display with a blue background, equal to 1 display with a yellow background, and 0 or less display with a red background.</span></span>  

-   <span data-ttu-id="dc450-224">Mit dem Ausdruck wird der Wert des Feldes `ImportantDate` geprüft und "Red" zurückgegeben, wenn er älter als eine Woche ist. Andernfalls wird "Blue" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="dc450-224">Test the value of the `ImportantDate` field and return "Red" if it is more than a week old, and "Blue" otherwise.</span></span> <span data-ttu-id="dc450-225">Mit diesem Ausdruck kann die Color-Eigenschaft eines Textfelds in einem Berichtselement gesteuert werden:</span><span class="sxs-lookup"><span data-stu-id="dc450-225">This expression can be used to control the Color property of a text box in a report item:</span></span>  

```  
=IIF(DateDiff("d",Fields!ImportantDate.Value, Now())>7,"Red","Blue")  
```  

-   <span data-ttu-id="dc450-226">Mit dem Ausdruck wird der Wert des Felds `PhoneNumber` geprüft und "No Value" zurückgegeben, wenn er `null` (`Nothing` in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]) ist. Andernfalls wird der Wert der Telefonnummer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="dc450-226">Test the value of the `PhoneNumber` field and return "No Value" if it is `null` (`Nothing` in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]); otherwise return the phone number value.</span></span> <span data-ttu-id="dc450-227">Mit diesem Ausdruck kann der Wert eines Textfelds in einem Berichtselement gesteuert werden.</span><span class="sxs-lookup"><span data-stu-id="dc450-227">This expression can be used to control the value of a text box in a report item.</span></span>  

```  
=IIF(Fields!PhoneNumber.Value Is Nothing,"No Value",Fields!PhoneNumber.Value)  
```  

-   <span data-ttu-id="dc450-228">Mit dem Ausdruck wird der Wert des `Department`-Felds geprüft und entweder ein Unterberichtsname oder ein `null`-Wert (`Nothing` in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]) zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="dc450-228">Test the value of the `Department` field and return either a subreport name or a `null` (`Nothing` in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]).</span></span> <span data-ttu-id="dc450-229">Dieser Ausdruck kann für bedingte Drillthrough-Unterberichte verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dc450-229">This expression can be used for conditional drillthrough subreports.</span></span>  

```  
=IIF(Fields!Department.Value = "Development", "EmployeeReport", Nothing)  
```  

-   <span data-ttu-id="dc450-230">Prüft, ob ein Feldwert NULL ist.</span><span class="sxs-lookup"><span data-stu-id="dc450-230">Test if a field value is null.</span></span> <span data-ttu-id="dc450-231">Dieser Ausdruck kann verwendet werden, um die `Hidden`-Eigenschaft eines Bildberichtselements zu steuern.</span><span class="sxs-lookup"><span data-stu-id="dc450-231">This expression can be used to control the `Hidden` property of an image report item.</span></span> <span data-ttu-id="dc450-232">Im folgenden Beispiel wird das durch das Feld [LargePhoto] angegebene Bild nur angezeigt, wenn der Wert des Felds ungleich NULL ist.</span><span class="sxs-lookup"><span data-stu-id="dc450-232">In the following example, the image specified by the field [LargePhoto] is displayed only if the value of the field is not null.</span></span>  

```  
=IIF(IsNothing(Fields!LargePhoto.Value),True,False)  
```  

-   <span data-ttu-id="dc450-233">Die `MonthName`-Funktion gibt einen Zeichenfolgenwert zurück, der den Namen des angegebenen Monats enthält.</span><span class="sxs-lookup"><span data-stu-id="dc450-233">The `MonthName` function returns a string value containing the name of the specified month.</span></span> <span data-ttu-id="dc450-234">Im folgenden Beispiel wird NZ im Monatsfeld angezeigt, wenn das Feld den Wert 0 enthält.</span><span class="sxs-lookup"><span data-stu-id="dc450-234">The following example displays NA in the Month field when the field contains the value of 0.</span></span>  

```  
IIF(Fields!Month.Value=0,"NA",MonthName(IIF(Fields!Month.Value=0,1,Fields!Month.Value)))  

```  

###  <a name="report-functions"></a><a name="ReportFunctions"></a> <span data-ttu-id="dc450-235">Berichtsfunktionen:</span><span class="sxs-lookup"><span data-stu-id="dc450-235">Report Functions</span></span>  
<span data-ttu-id="dc450-236">In einem Ausdruck können Sie einen Verweis auf weitere Berichtsfunktionen hinzufügen, die Daten in einem Bericht bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="dc450-236">In an expression, you can add a reference to additional report functions that manipulate data in a report.</span></span> <span data-ttu-id="dc450-237">In diesem Abschnitt werden Beispiele für zwei dieser Funktionen behandelt.</span><span class="sxs-lookup"><span data-stu-id="dc450-237">This section provides examples for two of these functions.</span></span> <span data-ttu-id="dc450-238">Weitere Informationen zu Berichtsfunktionen sowie Beispiele finden Sie unter [Aggregatfunktionsreferenz &#40;Berichts-Generator und SSRS&#41;](report-builder-functions-aggregate-functions-reference.md).</span><span class="sxs-lookup"><span data-stu-id="dc450-238">For more information about report functions and examples, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md).</span></span>  

#####  <a name="sum"></a><a name="Sum"></a><span data-ttu-id="dc450-239">Pauschalen</span><span class="sxs-lookup"><span data-stu-id="dc450-239">Sum</span></span>  

-   <span data-ttu-id="dc450-240">Die `Sum`-Funktion gibt die Summe von Werten in einer Gruppe oder einem Datenbereich zurück.</span><span class="sxs-lookup"><span data-stu-id="dc450-240">The `Sum` function can total the values in a group or data region.</span></span> <span data-ttu-id="dc450-241">Diese Funktion ist hilfreich für die Kopf- oder Fußzeile einer Gruppe.</span><span class="sxs-lookup"><span data-stu-id="dc450-241">This function can be useful in the header or footer of a group.</span></span> <span data-ttu-id="dc450-242">Der folgende Ausdruck zeigt die Summe von Daten in der Gruppe bzw. im Datenbereich Order an:</span><span class="sxs-lookup"><span data-stu-id="dc450-242">The following expression displays the sum of data in the Order group or data region:</span></span>  

```  
=Sum(Fields!LineTotal.Value, "Order")  
```  

-   <span data-ttu-id="dc450-243">Sie können auch die `Sum`-Funktion für bedingte Aggregatberechnungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="dc450-243">You can also use the `Sum` function for conditional aggregate calculations.</span></span> <span data-ttu-id="dc450-244">Wenn ein Dataset ein Feld mit dem Namen State und den möglichen Werten Not Started, Started und Finished enthält, wird mit dem folgenden Ausdruck die Aggregatsumme bei Platzierung in einem Gruppenheader nur für den Wert Finished berechnet:</span><span class="sxs-lookup"><span data-stu-id="dc450-244">For example, if a dataset has a field that is named State with possible values Not Started, Started, Finished, the following expression, when placed in a group header, calculates the aggregate sum for only the value Finished:</span></span>  

```  
=Sum(IIF(Fields!State.Value = "Finished", 1, 0))  
```  

#####  <a name="rownumber"></a><a name="RowNumber"></a><span data-ttu-id="dc450-245">RowNumber</span><span class="sxs-lookup"><span data-stu-id="dc450-245">RowNumber</span></span>  

-   <span data-ttu-id="dc450-246">Mit der `RowNumber`-Funktion, die in einem Textfeld innerhalb eines Datenbereichs verwendet wird, wird die Zeilennummer für jede Instanz des Textfelds angezeigt, in der der Ausdruck enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="dc450-246">The `RowNumber` function, when used in a text box within a data region, displays the row number for each instance of the text box in which the expression appears.</span></span> <span data-ttu-id="dc450-247">Diese Funktion eignet sich, um Zeilen in einer Tabelle zu nummerieren.</span><span class="sxs-lookup"><span data-stu-id="dc450-247">This function can be useful to number rows in a table.</span></span> <span data-ttu-id="dc450-248">Sie ist auch bei komplizierteren Aufgaben hilfreich, z. B. beim Einfügen von Seitenumbrüchen auf der Grundlage der Zeilenanzahl.</span><span class="sxs-lookup"><span data-stu-id="dc450-248">It can also be useful for more complex tasks, such as providing page breaks based on number of rows.</span></span> <span data-ttu-id="dc450-249">Weitere Informationen finden Sie weiter unten unter " [Seitenumbrüche](#PageBreaks) ".</span><span class="sxs-lookup"><span data-stu-id="dc450-249">For more information, see [Page Breaks](#PageBreaks) in this topic.</span></span>  

<span data-ttu-id="dc450-250">Der Bereich, den Sie für `RowNumber`-Steuerelemente angeben, wenn die Neunumerierung beginnt.</span><span class="sxs-lookup"><span data-stu-id="dc450-250">The scope you specify for `RowNumber` controls when renumbering begins.</span></span> <span data-ttu-id="dc450-251">Das `Nothing`-Schlüsselwort gibt an, dass die Funktion die Zählung mit der ersten Zeile im äußersten Datenbereich beginnt.</span><span class="sxs-lookup"><span data-stu-id="dc450-251">The `Nothing` keyword indicates that the function will start counting at the first row in the outermost data region.</span></span> <span data-ttu-id="dc450-252">Wenn Sie in geschachtelten Datenbereichen mit dem Zählen beginnen möchten, verwenden Sie den Namen des Datenbereichs.</span><span class="sxs-lookup"><span data-stu-id="dc450-252">To start counting within nested data regions, use the name of the data region.</span></span> <span data-ttu-id="dc450-253">Um mit dem Zählen innerhalb einer Gruppe zu beginnen, verwenden Sie den Namen der Gruppe.</span><span class="sxs-lookup"><span data-stu-id="dc450-253">To start counting within a group, use the name of the group.</span></span>  

```  
=RowNumber(Nothing)  
```  

##  <a name="appearance-of-report-data"></a><a name="AppearanceofReportData"></a> <span data-ttu-id="dc450-254">Darstellung von Berichtsdaten</span><span class="sxs-lookup"><span data-stu-id="dc450-254">Appearance of Report Data</span></span>  
<span data-ttu-id="dc450-255">Mit Ausdrücken können Sie die Darstellung von Daten in einem Bericht ändern.</span><span class="sxs-lookup"><span data-stu-id="dc450-255">You can use expressions to manipulate how data appears on a report.</span></span> <span data-ttu-id="dc450-256">Beispielsweise können Sie die Werte von zwei Feldern in einem einzigen Textfeld anzeigen, Informationen zum Bericht anzeigen oder die Methode zum Einfügen von Seitenumbrüchen im Bericht ändern.</span><span class="sxs-lookup"><span data-stu-id="dc450-256">For example, you can display the values of two fields in a single text box, display information about the report, or affect how page breaks are inserted in the report.</span></span>  

###  <a name="page-headers-and-footers"></a><a name="PageHeadersandFooters"></a><span data-ttu-id="dc450-257">Seiten Kopfzeilen und-Fußzeilen</span><span class="sxs-lookup"><span data-stu-id="dc450-257">Page Headers and Footers</span></span>  
<span data-ttu-id="dc450-258">Beim Entwerfen eines Berichts soll möglicherweise der Name des Berichts und die Seitenzahl in der Fußzeile des Berichts angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="dc450-258">When designing a report, you may want to display the name of the report and page number in the report footer.</span></span> <span data-ttu-id="dc450-259">Dazu können Sie die folgenden Ausdrücke verwenden:</span><span class="sxs-lookup"><span data-stu-id="dc450-259">To do this, you can use the following expressions:</span></span>  

-   <span data-ttu-id="dc450-260">Der folgende Ausdruck stellt den Namen des Berichts und die Zeit seiner Ausführung bereit.</span><span class="sxs-lookup"><span data-stu-id="dc450-260">The following expression provides the name of the report and the time it was run.</span></span> <span data-ttu-id="dc450-261">Er kann in einem Textfeld in der Fußzeile oder im Hauptteil des Berichts eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="dc450-261">It can be placed in a text box in the report footer or in the body of the report.</span></span> <span data-ttu-id="dc450-262">Die Zeit wird mit der [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] -Formatzeichenfolge für ein kurzes Datum formatiert:</span><span class="sxs-lookup"><span data-stu-id="dc450-262">The time is formatted with the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] formatting string for short date:</span></span>  

```  
=Globals.ReportName & ", dated " & Format(Globals.ExecutionTime, "d")  
```  

-   <span data-ttu-id="dc450-263">Der folgende Ausdruck zeigt in einem Textfeld in der Fußzeile eines Berichts die Seitenzahl und die Gesamtseitenzahl im Bericht an:</span><span class="sxs-lookup"><span data-stu-id="dc450-263">The following expression, placed in a text box in the footer of a report, provides page number and total pages in the report:</span></span>  

```  
=Globals.PageNumber & " of " & Globals.TotalPages  
```  

<span data-ttu-id="dc450-264">Die folgenden Beispiele veranschaulichen, wie der erste und letzte Wert einer Seite in der Seitenkopfzeile angezeigt wird, ähnlich wie bei einer Verzeichnisauflistung.</span><span class="sxs-lookup"><span data-stu-id="dc450-264">The following examples describe how to display the first and last values from a page in the page header, similar to what you might find in a directory listing.</span></span> <span data-ttu-id="dc450-265">Bei diesem Beispiel wird von einem Datenbereich ausgegangen, der das `LastName`-Textfeld enthält.</span><span class="sxs-lookup"><span data-stu-id="dc450-265">The example assumes a data region that contains a text box named `LastName`.</span></span>  

-   <span data-ttu-id="dc450-266">Der folgende Ausdruck, der sich in einem Textfeld auf der linken Seite des Seitenkopfes befindet, gibt den ersten Wert des `LastName` -Textfelds auf der Seite an:</span><span class="sxs-lookup"><span data-stu-id="dc450-266">The following expression, placed in a text box on the left side of the page header, provides the first value of the `LastName` text box on the page:</span></span>  

```  
=First(ReportItems("LastName").Value)  
```  

-   <span data-ttu-id="dc450-267">Der folgende Ausdruck, der sich in einem Textfeld auf der rechten Seite des Seitenkopfes befindet, gibt den letzten Wert des `LastName` -Textfelds auf der Seite an:</span><span class="sxs-lookup"><span data-stu-id="dc450-267">The following expression, placed in a text box on the right side of the page header, provides the last value of the `LastName` text box on the page:</span></span>  

```  
=Last(ReportItems("LastName").Value)  
```  

<span data-ttu-id="dc450-268">Das folgende Beispiel beschreibt, wie die Summe einer Seite angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="dc450-268">The following example describes how to display a page total.</span></span> <span data-ttu-id="dc450-269">Bei diesem Beispiel wird von einem Datenbereich ausgegangen, der das `Cost`-Textfeld enthält.</span><span class="sxs-lookup"><span data-stu-id="dc450-269">The example assumes a data region that contains a text box named `Cost`.</span></span>  

-   <span data-ttu-id="dc450-270">Der folgende Ausdruck, im Seitenkopf oder -fuß platziert, gibt die Summe der Werte im `Cost` -Textfeld für die Seite an:</span><span class="sxs-lookup"><span data-stu-id="dc450-270">The following expression, placed in the page header or footer, provides the sum of the values in the `Cost` text box for the page:</span></span>  

```  
=Sum(ReportItems("Cost").Value)  
```  

> [!NOTE]  
>  <span data-ttu-id="dc450-271">In einem Seitenkopf oder -fuß kann pro Ausdruck nur auf ein einziges Berichtselement verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="dc450-271">You can refer to only one report item per expression in a page header or footer.</span></span> <span data-ttu-id="dc450-272">In Seitenkopf- und -fußausdrücken können Sie außerdem auf den Textfeldnamen, jedoch nicht auf den tatsächlichen Datenausdruck innerhalb des Textfelds verweisen.</span><span class="sxs-lookup"><span data-stu-id="dc450-272">Also, you can refer to the text box name, but not the actual data expression within the text box, in page header and footer expressions.</span></span>  

###  <a name="page-breaks"></a><a name="PageBreaks"></a> <span data-ttu-id="dc450-273">Seitenumbrüche</span><span class="sxs-lookup"><span data-stu-id="dc450-273">Page Breaks</span></span>  
<span data-ttu-id="dc450-274">In manchen Berichten möchten Sie möglicherweise einen Seitenumbruch am Ende einer bestimmten Anzahl von Zeilen einfügen, und zwar anstelle von bzw. zusätzlich zu Gruppen oder Berichtselementen.</span><span class="sxs-lookup"><span data-stu-id="dc450-274">In some reports, you may want to place a page break at the end of a specified number of rows instead of, or in addition to, on groups or report items.</span></span> <span data-ttu-id="dc450-275">Erstellen Sie dazu eine Gruppe mit den gewünschten Gruppen- oder Detaildatensätzen, und fügen Sie der Gruppe einen Seitenumbruch hinzu. Fügen Sie anschließend einen Gruppenausdruck hinzu, um eine Gruppierung nach einer bestimmten Anzahl von Zeilen durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="dc450-275">To do this, create a group that contains the groups or detail records you want, add a page break to the group, and then add a group expression to group by a specified number of rows.</span></span>  

-   <span data-ttu-id="dc450-276">Der folgende Ausdruck weist im Gruppenausdruck einer Gruppe von jeweils 25 Zeilen eine Zahl zu.</span><span class="sxs-lookup"><span data-stu-id="dc450-276">The following expression, when placed in the group expression, assigns a number to each set of 25 rows.</span></span> <span data-ttu-id="dc450-277">Wenn ein Seitenumbruch für die Gruppe definiert ist, ergibt sich aus diesem Ausdruck alle 25 Zeilen ein Seitenumbruch.</span><span class="sxs-lookup"><span data-stu-id="dc450-277">When a page break is defined for the group, this expression results in a page break every 25 rows.</span></span>  

```  
=Ceiling(RowNumber(Nothing)/25)  
```  

<span data-ttu-id="dc450-278">Damit der Benutzer einen Wert für die Anzahl der Zeilen pro Seite festlegen kann, erstellen Sie einen Parameter mit dem Namen `RowsPerPage` und basieren den Gruppenausdruck auf dem Parameter, wie im folgenden Ausdruck gezeigt:</span><span class="sxs-lookup"><span data-stu-id="dc450-278">To allow the user to set a value for the number of rows per page, create a parameter named `RowsPerPage` and base the group expression on the parameter, as shown in the following expression:</span></span>  

```  
=Ceiling(RowNumber(Nothing)/Parameters!RowsPerPage.Value)  
```  

<span data-ttu-id="dc450-279">Weitere Informationen zum Festlegen von Seitenumbrüchen für eine Gruppe finden Sie unter [Hinzufügen eines Seitenumbruchs &#40;Berichts-Generator und SSRS&#41;](add-a-page-break-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="dc450-279">For more information about setting page breaks for a group, see [Add a Page Break &#40;Report Builder and SSRS&#41;](add-a-page-break-report-builder-and-ssrs.md).</span></span>  

##  <a name="properties"></a><a name="Properties"></a> <span data-ttu-id="dc450-280">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="dc450-280">Properties</span></span>  
<span data-ttu-id="dc450-281">Mit Ausdrücken werden nicht nur Daten in Textfeldern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dc450-281">Expressions are not only used to display data in text boxes.</span></span> <span data-ttu-id="dc450-282">Sie können mit Ausdrücken auch festlegen, wie Eigenschaften auf Berichtselemente angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="dc450-282">They can also be used to change how properties are applied to report items.</span></span> <span data-ttu-id="dc450-283">Sie können Formatinformationen für ein Berichtselement ändern oder festlegen, ob es angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="dc450-283">You can change style information for a report item, or change its visibility.</span></span>  

###  <a name="formatting"></a><a name="Formatting"></a><span data-ttu-id="dc450-284">Ert</span><span class="sxs-lookup"><span data-stu-id="dc450-284">Formatting</span></span>  

-   <span data-ttu-id="dc450-285">Wenn der folgende Ausdruck in der Color-Eigenschaft eines Textfelds verwendet wird, wird die Farbe des Texts basierend auf dem Wert des Felds `Profit` geändert:</span><span class="sxs-lookup"><span data-stu-id="dc450-285">The following expression, when used in the Color property of a text box, changes the color of the text depending on the value of the `Profit` field:</span></span>  

```  
=Iif(Fields!Profit.Value < 0, "Red", "Black")  
```  

<span data-ttu-id="dc450-286">Sie können auch die [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] -Objektvariable `Me`verwenden.</span><span class="sxs-lookup"><span data-stu-id="dc450-286">You can also use the [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] object variable `Me`.</span></span> <span data-ttu-id="dc450-287">Diese Variable bietet eine andere Möglichkeit, auf den Wert eines Textfeldes zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="dc450-287">This variable is another way of referring to the value of a text box.</span></span>  

`=Iif(Me.Value < 0, "Red", "Black")`  

-   <span data-ttu-id="dc450-288">Wenn der folgende Ausdruck in der BackgroundColor-Eigenschaft eines Berichtselements in einem Datenbereich verwendet wird, wird die Hintergrundfarbe der Zeilen von hellgrün in weiß geändert:</span><span class="sxs-lookup"><span data-stu-id="dc450-288">The following expression, when used in the BackgroundColor property of a report item in a data region, alternates the background color of each row between pale green and white:</span></span>  

```  
=Iif(RowNumber(Nothing) Mod 2, "PaleGreen", "White")  
```  

<span data-ttu-id="dc450-289">Wenn Sie einen Ausdruck für einen angegebenen Bereich verwenden, müssen Sie möglicherweise das Dataset für die Aggregatfunktion angeben:</span><span class="sxs-lookup"><span data-stu-id="dc450-289">If you are using an expression for a specified scope, you may have to indicate the dataset for the aggregate function:</span></span>  

```  
=Iif(RowNumber("Employees") Mod 2, "PaleGreen", "White")  
```  

> [!NOTE]  
>  <span data-ttu-id="dc450-290">Verfügbare Farben stammen aus der [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] KnownColor-Enumeration.</span><span class="sxs-lookup"><span data-stu-id="dc450-290">Available colors come from the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] KnownColor enumeration.</span></span>  

### <a name="chart-colors"></a><span data-ttu-id="dc450-291">Diagrammfarben</span><span class="sxs-lookup"><span data-stu-id="dc450-291">Chart Colors</span></span>  
<span data-ttu-id="dc450-292">Mit benutzerdefiniertem Code können Sie die Reihenfolge steuern, in der Datenpunktwerten Farben zugeordnet werden, um Farben für ein Formdiagramm anzugeben.</span><span class="sxs-lookup"><span data-stu-id="dc450-292">To specify colors for a Shape chart, you can use custom code to control the order that colors are mapped to data point values.</span></span> <span data-ttu-id="dc450-293">Dies hilft bei der Verwendung konsistenter Farben für mehrere Diagramme mit gleichen Kategoriegruppen.</span><span class="sxs-lookup"><span data-stu-id="dc450-293">This helps you use consistent colors for multiple charts that have the same category groups.</span></span> <span data-ttu-id="dc450-294">Weitere Informationen finden Sie unter [Angeben von Farben, die für mehrere Formdiagramme konsistent sind &#40;Berichts-Generator und SSRS&#41;](charts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="dc450-294">For more information, see [Specify Consistent Colors across Multiple Shape Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md).</span></span>  

###  <a name="visibility"></a><a name="Visibility"></a><span data-ttu-id="dc450-295">Transparenz</span><span class="sxs-lookup"><span data-stu-id="dc450-295">Visibility</span></span>  
<span data-ttu-id="dc450-296">Berichtselemente können mithilfe der Sichtbarkeitseigenschaften ein- und ausgeblendet werden.</span><span class="sxs-lookup"><span data-stu-id="dc450-296">You can show and hide items in a report using the visibility properties for the report item.</span></span> <span data-ttu-id="dc450-297">In einem Datenbereich, wie z. B. einer Tabelle, können die Detailzeilen basierend auf dem Wert eines Ausdrucks anfänglich ausgeblendet werden.</span><span class="sxs-lookup"><span data-stu-id="dc450-297">In a data region such as a table, you can initially hide detail rows based on the value in an expression.</span></span>  

-   <span data-ttu-id="dc450-298">Wenn der folgende Ausdruck für die ursprüngliche Sichtbarkeit von Detailzeilen in einer Gruppe verwendet wird, werden die Detailzeilen für alle Umsätze angezeigt, die im `PctQuota` -Feld den Wert 90 % übersteigen:</span><span class="sxs-lookup"><span data-stu-id="dc450-298">The following expression, when used for initial visibility of detail rows in a group, shows the detail rows for all sales exceeding 90 percent in the `PctQuota` field:</span></span>  

```  
=Iif(Fields!PctQuota.Value>.9, False, True)  
```  

-   <span data-ttu-id="dc450-299">Wenn der folgende Ausdruck in der Hidden-Eigenschaft einer Tabelle festgelegt ist, wird die Tabelle mithilfe des Ausdrucks nur angezeigt, wenn sie mehr als 12 Zeilen enthält:</span><span class="sxs-lookup"><span data-stu-id="dc450-299">The following expression, when set in the Hidden property of a table, shows the table only if it has more than 12 rows:</span></span>  

```  
=IIF(CountRows()>12,false,true)  
```  

-   <span data-ttu-id="dc450-300">Wenn der folgende Ausdruck in der- `Hidden` Eigenschaft einer Spalte festgelegt wird, wird die Spalte nur angezeigt, wenn das Feld im Berichts DataSet vorhanden ist, nachdem die Daten aus der Datenquelle abgerufen wurden:</span><span class="sxs-lookup"><span data-stu-id="dc450-300">The following expression, when set in the `Hidden` property of a column, shows the column only if the field exists in the report dataset after the data is retrieved from the data source:</span></span>  

```  
=IIF(Fields!Column_1.IsMissing, true, false)  
```  

###  <a name="urls"></a><a name="Hyperlinks"></a><span data-ttu-id="dc450-301">Del</span><span class="sxs-lookup"><span data-stu-id="dc450-301">URLs</span></span>  
<span data-ttu-id="dc450-302">Sie können URLs anpassen, indem Sie die Berichtsdaten verwenden und bedingt steuern, ob URLs als Aktion für ein Textfeld hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="dc450-302">You can customize URLs by using report data and also conditionally control whether URLs are added as an action for a text box.</span></span>  

-   <span data-ttu-id="dc450-303">Wenn der folgende Ausdruck als Aktion für ein Textfeld verwendet wird, wird eine angepasste URL generiert, die das Datasetfeld `EmployeeID` als URL-Parameter angibt.</span><span class="sxs-lookup"><span data-stu-id="dc450-303">The following expression, when used as an action on a text box, generates a customized URL that specifies the dataset field `EmployeeID` as a URL parameter.</span></span>  

```  
="http://adventure-works/MyInfo?ID=" & Fields!EmployeeID.Value  
```  

<span data-ttu-id="dc450-304">Weitere Informationen finden Sie unter [Hinzufügen eines Links zu einer URL (Berichts-Generator und SSRS)](add-a-hyperlink-to-a-url-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="dc450-304">For more information, see [Add a Hyperlink to a URL &#40;Report Builder and SSRS&#41;](add-a-hyperlink-to-a-url-report-builder-and-ssrs.md).</span></span>  

-   <span data-ttu-id="dc450-305">Der folgende Ausdruck steuert bedingt, ob eine URL in einem Textfeld hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="dc450-305">The following expression conditionally controls whether to add a URL in a text box.</span></span> <span data-ttu-id="dc450-306">Dieser Ausdruck ist von einem Parameter mit dem Namen `IncludeURLs` abhängig, mit dem ein Benutzer entscheiden kann, ob aktive URLs in einen Bericht eingeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="dc450-306">This expression depends on a parameter named `IncludeURLs` that allows a user to decide whether to include active URLs in a report.</span></span> <span data-ttu-id="dc450-307">Dieser Ausdruck wird als Aktion in einem Textfeld festgelegt.</span><span class="sxs-lookup"><span data-stu-id="dc450-307">This expression is set as an action on a text box.</span></span> <span data-ttu-id="dc450-308">Indem Sie den Parameter auf FALSE festlegen und dann den Bericht anzeigen, können Sie den Bericht ohne Links nach Microsoft Excel exportieren.</span><span class="sxs-lookup"><span data-stu-id="dc450-308">By setting the parameter to False and then viewing the report, you can export the report Microsoft Excel without hyperlinks.</span></span>  

```  
=IIF(Parameters!IncludeURLs.Value,"http://adventure-works.com/productcatalog",Nothing)  
```  

##  <a name="report-data"></a><a name="ReportData"></a><span data-ttu-id="dc450-309">Berichtsdaten</span><span class="sxs-lookup"><span data-stu-id="dc450-309">Report Data</span></span>  
<span data-ttu-id="dc450-310">Mit Ausdrücken können die im Bericht verwendeten Daten bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="dc450-310">Expressions can be used to manipulate the data that is used in the report.</span></span> <span data-ttu-id="dc450-311">Sie können auf Parameter und sonstige Berichtsinformationen verweisen.</span><span class="sxs-lookup"><span data-stu-id="dc450-311">You can refer to parameters and other report information.</span></span> <span data-ttu-id="dc450-312">Es ist sogar möglich, die Abfrage zu ändern, mit der Daten für den Bericht abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="dc450-312">You can even change the query that is used to retrieve data for the report.</span></span>  

###  <a name="parameters"></a><a name="Parameters"></a> <span data-ttu-id="dc450-313">Parameter</span><span class="sxs-lookup"><span data-stu-id="dc450-313">Parameters</span></span>  
<span data-ttu-id="dc450-314">Ausdrücke können in einem Parameter verwendet werden, um den Standardwert für den Parameter zu ändern.</span><span class="sxs-lookup"><span data-stu-id="dc450-314">You can use expressions in a parameter to vary the default value for the parameter.</span></span> <span data-ttu-id="dc450-315">Beispielsweise können Sie mithilfe eines Parameters Daten nach einem bestimmten Benutzer basierend auf der Benutzer-ID filtern, mit der der Bericht ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="dc450-315">For example, you can use a parameter to filter data to a particular user based on the user ID that is used to run the report.</span></span>  

-   <span data-ttu-id="dc450-316">Wenn der folgende Ausdruck als Standardwert für einen Parameter verwendet wird, wird die Benutzer-ID der Person abgerufen, die den Bericht ausführt:</span><span class="sxs-lookup"><span data-stu-id="dc450-316">The following expression, when used as the default value for a parameter, collects the user ID of the person running the report:</span></span>  

```  
=User!UserID  
```  

-   <span data-ttu-id="dc450-317">Verwenden Sie die globale `Parameters`-Auflistung, um auf einen Parameter in einem Abfrageparameter, auf einen Filterausdruck, ein Textfeld oder einen anderen Bereich des Berichts zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="dc450-317">To refer to a parameter in a query parameter, filter expression, text box, or other area of the report, use the `Parameters` global collection.</span></span> <span data-ttu-id="dc450-318">Bei diesem Beispiel wird von einem Parameter namens *Department*ausgegangen:</span><span class="sxs-lookup"><span data-stu-id="dc450-318">This example assumes that the parameter is named *Department*:</span></span>  

```  
=Parameters!Department.Value  
```  

-   <span data-ttu-id="dc450-319">Parameter können in einem Bericht erstellt und trotzdem ausgeblendet werden.</span><span class="sxs-lookup"><span data-stu-id="dc450-319">Parameters can be created in a report but set to hidden.</span></span> <span data-ttu-id="dc450-320">Wenn der Bericht auf dem Berichtsserver ausgeführt wird, erscheint der Parameter nicht auf der Symbolleiste und der Leser des Berichts kann den Standardwert nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="dc450-320">When the report runs on the report server, the parameter does not appear in the toolbar and the report reader cannot change the default value.</span></span> <span data-ttu-id="dc450-321">Sie können einen ausgeblendeten, auf einen Standardwert festgelegten Parameter als benutzerdefinierte Konstante verwenden.</span><span class="sxs-lookup"><span data-stu-id="dc450-321">You can use a hidden parameter set to a default value as custom constant.</span></span> <span data-ttu-id="dc450-322">Diesen Wert können Sie in einem beliebigen Ausdruck verwenden, einschließlich eines Feldausdrucks.</span><span class="sxs-lookup"><span data-stu-id="dc450-322">You can use this value in any expression, including a field expression.</span></span> <span data-ttu-id="dc450-323">Der folgende Ausdruck gibt das vom Standardparameterwert für den Parameter mit dem Namen *ParameterField*angegebene Feld an:</span><span class="sxs-lookup"><span data-stu-id="dc450-323">The following expression identifies the field specified by the default parameter value for the parameter named *ParameterField*:</span></span>  

```  
=Fields(Parameters!ParameterField.Value).Value  
```  

## <a name="custom-code"></a><a name="CustomCode"></a><span data-ttu-id="dc450-324">Benutzerdefinierter Code</span><span class="sxs-lookup"><span data-stu-id="dc450-324">Custom Code</span></span>

<span data-ttu-id="dc450-325">In einem Bericht kann benutzerdefinierter Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dc450-325">You can use custom code in a report.</span></span> <span data-ttu-id="dc450-326">Benutzerdefinierter Code ist entweder in einen Bericht eingebettet oder in einer benutzerdefinierten Assembly gespeichert, die im Bericht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="dc450-326">Custom code is either embedded in a report or stored in a custom assembly which is used in the report.</span></span> <span data-ttu-id="dc450-327">Weitere Informationen zu benutzerdefiniertem Code finden Sie unter [Benutzerdefinierter Code und Assemblyverweise in Ausdrücken in Berichts-Designer (SSRS)](custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="dc450-327">For more information about custom code, see [Custom Code and Assembly References in Expressions in Report Designer &#40;SSRS&#41;](custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span></span>  

### <a name="using-group-variables-for-custom-aggregation"></a><span data-ttu-id="dc450-328">Verwenden von Gruppenvariablen für benutzerdefinierte Aggregation</span><span class="sxs-lookup"><span data-stu-id="dc450-328">Using Group Variables for Custom Aggregation</span></span>

<span data-ttu-id="dc450-329">Sie können den Wert für eine Gruppenvariable initialisieren, die zu einem bestimmten Gruppenbereich lokal ist, und anschließend einen Verweis auf diese Variable in den Ausdrücken einbinden.</span><span class="sxs-lookup"><span data-stu-id="dc450-329">You can initialize the value for a group variable that is local to a particular group scope and then include a reference to that variable in expressions.</span></span> <span data-ttu-id="dc450-330">Eine der Methoden, wie Sie eine Gruppenvariable mit benutzerdefiniertem Code verwenden können, besteht darin, ein benutzerdefiniertes Aggregat zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="dc450-330">One of the ways that you can use a group variable with custom code is to implement a custom aggregate.</span></span> <span data-ttu-id="dc450-331">Weitere Informationen finden Sie unter [Gruppevariablen in Reporting Services 2008 für benutzerdefinierte Aggregation verwenden](https://go.microsoft.com/fwlink/?LinkId=128714).</span><span class="sxs-lookup"><span data-stu-id="dc450-331">For more information, see [Using Group Variables in Reporting Services 2008 for Custom Aggregation](https://go.microsoft.com/fwlink/?LinkId=128714).</span></span>  

<span data-ttu-id="dc450-332">Weitere Informationen zu Variablen finden Sie unter [Verweise auf Berichts- und Gruppenvariablensammlungen &#40;Berichts-Generator und SSRS&#41;](built-in-collections-report-and-group-variables-references-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="dc450-332">For more information about variables, see [Report and Group Variables Collections References &#40;Report Builder and SSRS&#41;](built-in-collections-report-and-group-variables-references-report-builder.md).</span></span>  

## <a name="suppressing-null-or-zero-values-at-run-time"></a><span data-ttu-id="dc450-333">Unterdrücken von NULL oder 0 zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="dc450-333">Suppressing Null or Zero Values at Run Time</span></span>

<span data-ttu-id="dc450-334">Einige Werte in einem Ausdruck können zur Berichtsverarbeitungszeit mit NULL oder "nicht definiert" ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="dc450-334">Some values in an expression can evaluate to null or undefined at report processing time.</span></span> <span data-ttu-id="dc450-335">Dies kann zu Laufzeitfehlern und zur Anzeige von **#Error** im Textfeld anstelle des ausgewerteten Ausdrucks führen.</span><span class="sxs-lookup"><span data-stu-id="dc450-335">This can create run-time errors that result in **#Error** displaying in the text box instead of the evaluated expression.</span></span> <span data-ttu-id="dc450-336">Die `IIF`-Funktion ist für dieses Verhalten besonders empfindlich, da im Gegensatz zu einer If-Then-Else-Anweisung jeder Teil der `IIF`-Anweisung (einschließlich Funktionsaufrufe) ausgewertet wird, bevor er an die Routine zur Prüfung auf `true` oder `false` übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="dc450-336">The `IIF` function is particularly sensitive to this behavior because, unlike an If-Then-Else statement, each part of the `IIF` statement is evaluated (including function calls) before being passed to the routine that tests for `true` or `false`.</span></span> <span data-ttu-id="dc450-337">Die Anweisung `=IIF(Fields!Sales.Value is NOTHING, 0, Fields!Sales.Value)` generiert **#Error** im gerenderten Bericht, wenn `Fields!Sales.Value` NOTHING ist.</span><span class="sxs-lookup"><span data-stu-id="dc450-337">The statement `=IIF(Fields!Sales.Value is NOTHING, 0, Fields!Sales.Value)` generates **#Error** in the rendered report if `Fields!Sales.Value` is NOTHING.</span></span>  

<span data-ttu-id="dc450-338">Wählen Sie eine der folgenden Strategien aus, um diesen Fehler zu vermeiden:</span><span class="sxs-lookup"><span data-stu-id="dc450-338">To avoid this condition, use one of the following strategies:</span></span>  

-   <span data-ttu-id="dc450-339">Legen Sie den Zähler auf 0 und den Nenner auf 1 fest, wenn der Wert für das Feld B 0 oder nicht definiert ist. Andernfalls legen Sie den Zähler auf den Wert für Feld A und den Nenner auf den Wert für Feld B fest.</span><span class="sxs-lookup"><span data-stu-id="dc450-339">Set the numerator to 0 and the denominator to 1 if the value for field B is 0 or undefined; otherwise, set the numerator to the value for field A and the denominator to the value for field B.</span></span>  

```  
=IIF(Field!B.Value=0, 0, Field!A.Value / IIF(Field!B.Value =0, 1, Field!B.Value))  
```  

-   <span data-ttu-id="dc450-340">Verwenden Sie eine benutzerdefinierte Codefunktion, um den Wert für den Ausdruck zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="dc450-340">Use a custom code function to return the value for the expression.</span></span> <span data-ttu-id="dc450-341">Im folgenden Beispiel wird der Prozentsatzunterschied zwischen einem aktuellen Wert und einem vorherigen Wert zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="dc450-341">The following example returns the percentage difference between a current value and a previous value.</span></span> <span data-ttu-id="dc450-342">Dieser Wert kann zur Berechnung der Differenz zwischen zwei aufeinanderfolgenden Werten verwendet werden und verarbeitet den Grenzfall des ersten Vergleichs (wenn kein vorheriger Wert vorhanden ist) sowie Fälle, in denen entweder der vorherige Wert oder der aktuelle Wert `null` ist (`Nothing` in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="dc450-342">This can be used to calculate the difference between any two successive values and it handles the edge case of the first comparison (when there is no previous value) and cases whether either the previous value or the current value is `null` (`Nothing` in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]).</span></span>  

```  
Public Function GetDeltaPercentage(ByVal PreviousValue, ByVal CurrentValue) As Object  
     If IsNothing(PreviousValue) OR IsNothing(CurrentValue) Then  
          Return Nothing  
     Else if PreviousValue = 0 OR CurrentValue = 0 Then  
          Return Nothing  
     Else
          Return (CurrentValue - PreviousValue) / CurrentValue  
     End If  
End Function  
```  

<span data-ttu-id="dc450-343">Der folgende Ausdruck veranschaulicht, wie dieser benutzerdefinierte Code aus einem Textfeld für den Container „ColumnGroupByYear“ (Gruppe bzw. Datenbereich) aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="dc450-343">The following expression shows how to call this custom code from a text box, for the "ColumnGroupByYear" container (group or data region).</span></span>  

```  
=Code.GetDeltaPercentage(Previous(Sum(Fields!Sales.Value),"ColumnGroupByYear"), Sum(Fields!Sales.Value))  
```  

<span data-ttu-id="dc450-344">Dadurch wird die Ausführung von Laufzeitausnahmen vermieden.</span><span class="sxs-lookup"><span data-stu-id="dc450-344">This helps to avoid run-time exceptions.</span></span> <span data-ttu-id="dc450-345">Sie können nun einen Ausdruck wie `=IIF(Me.Value < 0, "red", "black")` in der `Color`-Eigenschaft des Textfelds verwenden, um den Text unter Bedingungen anzuzeigen, nämlich abhängig davon, ob die Werte größer oder kleiner als 0 sind.</span><span class="sxs-lookup"><span data-stu-id="dc450-345">You can now use an expression like `=IIF(Me.Value < 0, "red", "black")` in the `Color` property of the text box to conditionally the display text based on whether the values are greater than or less than 0.</span></span>  

## <a name="see-also"></a><span data-ttu-id="dc450-346">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dc450-346">See Also</span></span>

- [<span data-ttu-id="dc450-347">Beispiele für Filtergleichungen &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="dc450-347">Filter Equation Examples &#40;Report Builder and SSRS&#41;</span></span>](filter-equation-examples-report-builder-and-ssrs.md)
- [<span data-ttu-id="dc450-348">Beispiele für Gruppierungsausdrücke &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="dc450-348">Group Expression Examples &#40;Report Builder and SSRS&#41;</span></span>](expression-examples-report-builder-and-ssrs.md)
- [<span data-ttu-id="dc450-349">Ausdrucksverwendungen in Berichten &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="dc450-349">Expression Uses in Reports &#40;Report Builder and SSRS&#41;</span></span>](expression-uses-in-reports-report-builder-and-ssrs.md)
- [<span data-ttu-id="dc450-350">Ausdrücke &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="dc450-350">Expressions &#40;Report Builder and SSRS&#41;</span></span>](expressions-report-builder-and-ssrs.md)
- [<span data-ttu-id="dc450-351">Häufig verwendete Filter (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="dc450-351">Commonly Used Filters &#40;Report Builder and SSRS&#41;</span></span>](commonly-used-filters-report-builder-and-ssrs.md)