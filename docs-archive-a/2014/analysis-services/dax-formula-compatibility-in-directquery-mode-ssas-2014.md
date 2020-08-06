---
title: DAX-Formel Kompatibilität im directquery-Modus (SSAS 2014) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: de83cfa9-9ffe-4e24-9c74-96a3876cb4bd
author: minewiskan
ms.author: owend
ms.openlocfilehash: acaac82d6930787a45281c0e942def8df764f4f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616818"
---
# <a name="dax-formula-compatibility-in-directquery-mode-ssas-2014"></a><span data-ttu-id="411db-102">DAX-Formelkompatibilität im DirectQuery-Modus (SSAS 2014)</span><span class="sxs-lookup"><span data-stu-id="411db-102">DAX Formula Compatibility in DirectQuery Mode (SSAS 2014)</span></span>
<span data-ttu-id="411db-103">Die Data Analysis Expression Language (DAX) kann verwendet werden, um Measures und andere benutzerdefinierte Formeln für die Verwendung in Analysis Services tabellarischen Modellen, [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] Datenmodellen in Excel-Arbeitsmappen und Power BI Desktop Datenmodellen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="411db-103">The Data Analysis Expression language (DAX) can be used to create measures and other custom formulas for use in Analysis Services Tabular models, [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] data models in Excel workbooks, and Power BI Desktop data models.</span></span> <span data-ttu-id="411db-104">In den meisten Fällen sind die Modelle, die Sie in diesen Umgebungen erstellen, identisch, und Sie können dieselben Measures, Beziehungen und KPIs usw. verwenden. Wenn Sie jedoch ein Analysis Services tabellarisches Modell erstellen und im directquery-Modus bereitstellen, gibt es einige Einschränkungen für die Formeln, die Sie verwenden können.</span><span class="sxs-lookup"><span data-stu-id="411db-104">In most respects, the models you create in these environments are identical, and you can use the same measures, relationships, and KPIs, etc. However, if you author an Analysis Services Tabular model and deploy it in DirectQuery mode, there are some restrictions on the formulas that you can use.</span></span> <span data-ttu-id="411db-105">Dieses Thema bietet einen Überblick über diese Unterschiede und listet die Funktionen auf, die in SQL Server 2014 Analysis Services tabulars-Modell mit Kompatibilitäts Grad 1100 oder 1103 und im directquery-Modus nicht unterstützt werden, und listet die Funktionen auf, die unterstützt werden, aber möglicherweise andere Ergebnisse zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="411db-105">This topic provides an overview of those differences, lists the functions that are not supported in SQL Server 2014 Analysis Services tabulars model at compatibility level 1100 or 1103 and in DirectQuery mode, and lists the functions that are supported but might return different results.</span></span>  
  
<span data-ttu-id="411db-106">In diesem Thema verwenden wir den Begriff *Modell im Arbeitsspeicher* , um auf tabellarische Modelle zu verweisen, bei denen es sich um vollständig gehostete in-Memory-zwischengespeicherte Daten auf einem Analysis Services Server im tabellarischen Modus handelt.</span><span class="sxs-lookup"><span data-stu-id="411db-106">Within this topic, we use the term *in-memory model* to refer to  Tabular models, which are fully hosted in-memory cached data on an Analysis Services server running in Tabular mode.</span></span> <span data-ttu-id="411db-107">Wir verwenden *directquery-Modelle* , um auf tabellarische Modelle zu verweisen, die im directquery-Modus erstellt und/oder bereitgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="411db-107">We use *DirectQuery models* to refer to Tabular models that have been authored and/or deployed in DirectQuery mode.</span></span> <span data-ttu-id="411db-108">Weitere Informationen zum directquery-Modus finden Sie unter [directquery-Modus (SSAS-tabellarisch)](https://msdn.microsoft.com/45ad2965-05ec-4fb1-a164-d8060b562ea5).</span><span class="sxs-lookup"><span data-stu-id="411db-108">For information about DirectQuery mode, see [DirectQuery Mode (SSAS Tabular)](https://msdn.microsoft.com/45ad2965-05ec-4fb1-a164-d8060b562ea5).</span></span>  
  
  
## <a name="differences-between-in-memory-and-directquery-mode"></a><a name="bkmk_SemanticDifferences"></a><span data-ttu-id="411db-109">Unterschiede zwischen dem speicherinternen und DirectQuery-Modus</span><span class="sxs-lookup"><span data-stu-id="411db-109">Differences between in-memory and DirectQuery mode</span></span>  
<span data-ttu-id="411db-110">Abfragen eines Modells, das im DirectQuery-Modus bereitgestellt wird, können andere Ergebnisse zurückgeben als bei der Bereitstellung desselben Modells im Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="411db-110">Queries on a model deployed in DirectQuery mode can return different results than the same model deployed in in-memory mode.</span></span> <span data-ttu-id="411db-111">Dies liegt daran, dass bei directquery Daten direkt aus einem relationalen Datenspeicher abgefragt werden und dass für Formeln erforderliche Aggregationen mithilfe der relevanten relationalen Engine durchgeführt werden, anstatt die xvelocity-Engine für Datenanalyse im Arbeitsspeicher (vertipq) für Speicherung und Berechnung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="411db-111">This is because with DirectQuery, data is queried directly from a relational data store and aggregations required by formulas are performed using the relevant relational engine, rather than using the xVelocity in-memory analytics engine (VertiPaq) for storage and calculation.</span></span>  
  
<span data-ttu-id="411db-112">Beispielsweise behandeln bestimmte relationale Datenspeicher numerische Werte, Daten, NULL-Werte usw. auf unterschiedliche Weise.</span><span class="sxs-lookup"><span data-stu-id="411db-112">For example, there are differences in the way that certain relational data stores handle numeric values, dates, nulls, and so forth.</span></span>  
  
<span data-ttu-id="411db-113">Im Gegensatz dazu dient die DAX-Programmiersprache zum möglichst genauen Emulieren des Verhaltens von Funktionen in Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="411db-113">In contrast, the DAX language is intended to emulate as closely as possible the behavior of functions in Microsoft Excel.</span></span> <span data-ttu-id="411db-114">Beispielsweise versucht Excel bei der Behandlung von NULL-Werten, leeren Zeichenfolgen und Werten gleich 0 unabhängig vom genauen Datentyp die optimale Antwort bereitzustellen. Folglich verhält sich die xVelocity-Engine auf die gleiche Weise.</span><span class="sxs-lookup"><span data-stu-id="411db-114">For example, when handling nulls, empty strings and zero values, Excel attempts to provide the best answer regardless of the precise data type, and therefore the xVelocity engine does the same.</span></span> <span data-ttu-id="411db-115">Wird jedoch ein Tabellenmodell im DirectQuery-Modus bereitgestellt und übergibt es Formeln an eine relationale Datenquelle zur Auswertung, müssen die Daten gemäß der Semantik der relationalen Datenquelle behandelt werden. Dabei werden in der Regel leere Zeichenfolgen anders behandelt als NULL-Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="411db-115">However, when a tabular model is deployed in DirectQuery mode and passes formulas to a relational data source for evaluation, the data must be handled according to the semantics of the relational data source, which typically require distinct handling of empty strings vs. nulls.</span></span> <span data-ttu-id="411db-116">Aus diesem Grund kann die gleiche Formel ein anderes Ergebnis zurückgeben als im Fall der Auswertung anhand von zwischengespeicherten Daten sowie Daten, die lediglich aus dem relationalen Speicher zurückgegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="411db-116">For this reason, the same formula might return a different result when evaluated against cached data and against data returned solely from the relational store.</span></span>  
  
<span data-ttu-id="411db-117">Darüber hinaus können einige Funktionen nicht im directquery-Modus verwendet werden, da die Berechnung erfordert, dass die Daten im aktuellen Kontext als Parameter an die relationale Datenquelle gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="411db-117">Additionally, some functions cannot be used at all in DirectQuery mode because the calculation would require the data in the current context be sent to the relational data source as a parameter.</span></span> <span data-ttu-id="411db-118">Measures in einer- [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] Arbeitsmappe verwenden z. b. häufig Zeit Intelligenz Funktionen, die auf in der Arbeitsmappe verfügbare Datumsbereiche verweisen.</span><span class="sxs-lookup"><span data-stu-id="411db-118">For example, measures in a [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] workbook often use time-intelligence functions that reference date ranges available within the workbook.</span></span> <span data-ttu-id="411db-119">Derartige Formeln können im Allgemeinen nicht im DirectQuery-Modus verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="411db-119">Such formulas generally cannot be used in DirectQuery mode.</span></span>  
  
## <a name="semantic-differences"></a><span data-ttu-id="411db-120">Semantische Unterschiede</span><span class="sxs-lookup"><span data-stu-id="411db-120">Semantic differences</span></span>  
<span data-ttu-id="411db-121">Dieser Abschnitt listet die Typen der üblichen semantischen Unterschiede auf. Zudem werden Einschränkungen beschrieben, die u. U. für die Verwendung von Funktionen oder für Abfrageergebnisse gelten.</span><span class="sxs-lookup"><span data-stu-id="411db-121">This section lists the types of semantic differences that you can expect, and describes any limitations that might apply to the usage of functions or to query results.</span></span>  
  
### <a name="comparisons"></a><a name="bkmk_Comparisons"></a><span data-ttu-id="411db-122">Vergleiche</span><span class="sxs-lookup"><span data-stu-id="411db-122">Comparisons</span></span>  
<span data-ttu-id="411db-123">Die DAX-Programmiersprache in speicherinternen Modellen unterstützt Vergleiche von zwei Ausdrücken, die in Skalarwerte verschiedener Datentypen aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="411db-123">DAX in in-memory models support comparisons of two expressions that resolve to scalar values of different data types.</span></span> <span data-ttu-id="411db-124">Modelle, die im DirectQuery-Modus bereitgestellt werden, verwenden jedoch die Datentypen und Vergleichsoperatoren der relationalen Engine und geben daher u. U. unterschiedliche Ergebnisse zurück.</span><span class="sxs-lookup"><span data-stu-id="411db-124">However, models that are deployed in DirectQuery mode use the data types and comparison operators of the relational engine, and therefore might return different results.</span></span>  
  
<span data-ttu-id="411db-125">Die folgenden Vergleiche geben immer einen Fehler zurück, wenn sie in einer Berechnung in einer DirectQuery-Datenquelle verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="411db-125">The following comparisons will always return an error when used in a calculation on a DirectQuery data source:</span></span>  
  
-   <span data-ttu-id="411db-126">Numerischer Datentyp im Vergleich zu einem Zeichenfolgen-Datentyp</span><span class="sxs-lookup"><span data-stu-id="411db-126">Numeric data type compared to any string data type</span></span>  
  
-   <span data-ttu-id="411db-127">Numerischer Datentyp im Vergleich zu einem booleschen Wert</span><span class="sxs-lookup"><span data-stu-id="411db-127">Numeric data type compared to a Boolean value</span></span>  
  
-   <span data-ttu-id="411db-128">Zeichenfolgen-Datentyp im Vergleich zu einem booleschen Wert</span><span class="sxs-lookup"><span data-stu-id="411db-128">Any string data type compared to a Boolean value</span></span>  
  
<span data-ttu-id="411db-129">Im Allgemeinen toleriert die DAX-Programmiersprache mehr Datentypkonflikte in speicherinternen Modellen und versucht bis zu zweimal, eine implizite Umwandlung von Werten durchzuführen (wie in diesem Abschnitt beschrieben).</span><span class="sxs-lookup"><span data-stu-id="411db-129">In general, DAX is more forgiving of data type mismatches in in-memory models and will attempt an implicit cast of values up to two times, as described in this section.</span></span> <span data-ttu-id="411db-130">An einen relationalen Datenspeicher im DirectQuery-Modus gesendete Formeln werden jedoch strenger ausgewertet, wobei die Regeln der relationalen Engine berücksichtigt werden und mit höherer Wahrscheinlichkeit ein Fehlschlag auftritt.</span><span class="sxs-lookup"><span data-stu-id="411db-130">However, formulas sent to a relational data store in DirectQuery mode are evaluated more strictly, following the rules of the relational engine, and are more likely to fail.</span></span>  
  
<span data-ttu-id="411db-131">**Vergleiche von Zeichenfolgen und Zahlen**</span><span class="sxs-lookup"><span data-stu-id="411db-131">**Comparisons of strings and numbers**</span></span>  
<span data-ttu-id="411db-132">BEISPIEL: `"2" < 3`</span><span class="sxs-lookup"><span data-stu-id="411db-132">EXAMPLE: `"2" < 3`</span></span>  
  
<span data-ttu-id="411db-133">Die Formel vergleicht eine Textzeichenfolge mit einer Zahl.</span><span class="sxs-lookup"><span data-stu-id="411db-133">The formula compares a text string to a number.</span></span> <span data-ttu-id="411db-134">Der Ausdruck ist sowohl bei Modellen im DirectQuery-Modus als auch bei speicherinternen Modellen **true** .</span><span class="sxs-lookup"><span data-stu-id="411db-134">The expression is **true** in both DirectQuery mode and in-memory models.</span></span>  
  
<span data-ttu-id="411db-135">Bei einem speicherinternen Modell lautet das Ergebnis **true** , da Zahlen als Zeichenfolgen implizit in einen numerischen Datentyp für Vergleiche mit anderen Zahlen umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="411db-135">In an in-memory model, the result is **true** because numbers as strings are implicitly cast to a numerical data type for comparisons with other numbers.</span></span> <span data-ttu-id="411db-136">SQL wandelt auch Textzahlen implizit in Zahlen für den Vergleich mit numerischen Datentypen um.</span><span class="sxs-lookup"><span data-stu-id="411db-136">SQL also implicitly casts text numbers as numbers for comparison to numerical data types.</span></span>  
  
<span data-ttu-id="411db-137">Beachten Sie, dass dies eine Änderung des Verhaltens von der ersten Version von darstellt [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] , die **false**zurückgeben würde, da der Text "2" immer als größer als eine beliebige Zahl angesehen wird.</span><span class="sxs-lookup"><span data-stu-id="411db-137">Note that this represents a change in behavior from the first version of [!INCLUDE[ssGemini](../includes/ssgemini-md.md)], which would return **false**, because the text "2" would always be considered larger than any number.</span></span>  
  
<span data-ttu-id="411db-138">**Vergleich von Text mit booleschen Werten**</span><span class="sxs-lookup"><span data-stu-id="411db-138">**Comparison of text with Boolean**</span></span>  
<span data-ttu-id="411db-139">BEISPIEL: `"VERDADERO" = TRUE`</span><span class="sxs-lookup"><span data-stu-id="411db-139">EXAMPLE: `"VERDADERO" = TRUE`</span></span>  
  
<span data-ttu-id="411db-140">Dieser Ausdruck vergleicht eine Textzeichenfolge mit einem booleschen Wert.</span><span class="sxs-lookup"><span data-stu-id="411db-140">This expression compares a text string with a Boolean value.</span></span> <span data-ttu-id="411db-141">Im Allgemeinen führt der Vergleich von einem Zeichenfolgenwert mit einem booleschen Wert bei DirectQuery-Modellen bzw. speicherinternen Modellen zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="411db-141">In general, for DirectQuery or In-Memory models, comparing a string value to a Boolean value results in an error.</span></span> <span data-ttu-id="411db-142">Diese Regel gilt jedoch nicht, wenn die Zeichenfolge das Wort **true** oder **false**enthält. Wenn die Zeichenfolge Werte des Typs „true“ oder „false“ enthält, erfolgt eine Umwandlung in einen booleschen Wert. Daraufhin wird der Vergleich ausgeführt und ein logisches Ergebnis zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="411db-142">The only exceptions to the rule are when the string contains the word **true** or the word **false**; if the string contains any of true or false values, a conversion to Boolean is made and the comparison takes place giving the logical result.</span></span>  
  
<span data-ttu-id="411db-143">**Vergleich von NULL-Werten**</span><span class="sxs-lookup"><span data-stu-id="411db-143">**Comparison of nulls**</span></span>  
<span data-ttu-id="411db-144">BEISPIEL: `EVALUATE ROW("X", BLANK() = BLANK())`</span><span class="sxs-lookup"><span data-stu-id="411db-144">EXAMPLE: `EVALUATE ROW("X", BLANK() = BLANK())`</span></span>  
  
<span data-ttu-id="411db-145">Diese Formel vergleicht die SQL-Entsprechung eines NULL-Werts mit einem NULL-Wert.</span><span class="sxs-lookup"><span data-stu-id="411db-145">This formula compares the SQL equivalent of a null to a null.</span></span> <span data-ttu-id="411db-146">Sie gibt für speicherinterne Modelle sowie DirectQuery-Modelle **true** zurück. Eine Bereitstellung erfolgt im DirectQuery-Modell, um ein ähnliches Verhalten beim speicherinternen Modell zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="411db-146">It returns **true** in in-memory and DirectQuery models; a provision is made in DirectQuery model to guarantee similar behavior to in-memory model.</span></span>  
  
<span data-ttu-id="411db-147">Beachten Sie, dass ein NULL-Wert in Transact-SQL niemals gleich einem NULL-Wert ist.</span><span class="sxs-lookup"><span data-stu-id="411db-147">Note that in Transact-SQL, a null is never equal to a null.</span></span> <span data-ttu-id="411db-148">In der DAX-Programmiersprache jedoch ist ein Leerzeichen gleich einem anderen Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="411db-148">However, in DAX, a blank is equal to another blank.</span></span> <span data-ttu-id="411db-149">Dieses Verhalten gilt für alle speicherinternen Modelle.</span><span class="sxs-lookup"><span data-stu-id="411db-149">This behavior is the same for all in-memory models.</span></span> <span data-ttu-id="411db-150">Im DirectQuery-Modus wird hauptsächlich die Semantik von SQL Server verwendet. In diesem Fall wird jedoch von der Semantik abgewichen, indem ein neues Verhalten für Vergleiche von NULL-Werten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="411db-150">It is important to note that DirectQuery mode uses, most of, the semantics of SQL Server; but, in this case it separates from it giving a new behavior to NULL comparisons.</span></span>  
  
### <a name="casts"></a><a name="bkmk_Casts"></a><span data-ttu-id="411db-151">Umwandlungen</span><span class="sxs-lookup"><span data-stu-id="411db-151">Casts</span></span>  
  
<span data-ttu-id="411db-152">Es gibt in der DAX-Programmiersprache keine Umwandlungsfunktion als solche, aber implizite Umwandlungen werden bei vielen Vergleichsvorgängen sowie arithmetischen Vorgängen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="411db-152">There is no cast function as such in DAX, but implicit casts are performed in many comparison and arithmetic operations.</span></span> <span data-ttu-id="411db-153">Anhand des Vergleichsvorgangs bzw. arithmetischen Vorgangs wird der Datentyp des Ergebnisses bestimmt.</span><span class="sxs-lookup"><span data-stu-id="411db-153">It is the comparison or arithmetic operation that determines the data type of the result.</span></span> <span data-ttu-id="411db-154">Ein auf ein Objekt angewendeter</span><span class="sxs-lookup"><span data-stu-id="411db-154">For example,</span></span>  
  
-   <span data-ttu-id="411db-155">Boolesche Werte werden bei arithmetischen Vorgängen als numerisch betrachtet, beispielsweise als TRUE + 1. Alternativ wird die Funktion MIN für eine Spalte mit booleschen Werten angewendet.</span><span class="sxs-lookup"><span data-stu-id="411db-155">Boolean values are treated as numeric in arithmetic operations, such as TRUE + 1, or the function MIN applied to a column of Boolean values.</span></span> <span data-ttu-id="411db-156">Ein NOT-Vorgang gibt ebenfalls einen numerischen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="411db-156">A NOT operation also returns a numeric value.</span></span>  
  
-   <span data-ttu-id="411db-157">Boolesche Werte werden stets als logische Werte in Vergleichen sowie bei Verwendung mit EXACT, AND, OR, &amp;&amp;oder || betrachtet.</span><span class="sxs-lookup"><span data-stu-id="411db-157">Boolean values are always treated as logical values in comparisons and when used with EXACT, AND, OR, &amp;&amp;, or ||.</span></span>  
  
<span data-ttu-id="411db-158">**Umwandeln einer Zeichenfolge in einen booleschen Wert**</span><span class="sxs-lookup"><span data-stu-id="411db-158">**Cast from string to Boolean**</span></span>  
<span data-ttu-id="411db-159">Bei in-Memory-und directquery-Modellen sind Umwandlungen nur boolesche Werte aus diesen Zeichen folgen zulässig: **""** (leere Zeichenfolge), **"true"**, **"false"**; , wenn eine leere Zeichenfolge in einen false-Wert umgewandelt wird.</span><span class="sxs-lookup"><span data-stu-id="411db-159">In in-memory and DirectQuery models, casts are permitted to Boolean values from these strings only: **""** (empty string), **"true"**, **"false"**; where an empty string casts to false value.</span></span>  
  
<span data-ttu-id="411db-160">Umwandlungen anderer Zeichenfolgen in den booleschen Datentyp führen zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="411db-160">Casts to the Boolean data type of any other string results in an error.</span></span>  
  
<span data-ttu-id="411db-161">**Umwandeln einer Zeichenfolge in ein Datum/eine Uhrzeit**</span><span class="sxs-lookup"><span data-stu-id="411db-161">**Cast from string to date/time**</span></span>  
<span data-ttu-id="411db-162">Umwandlungen von Zeichenfolgendarstellungen für Daten und Uhrzeiten in tatsächliche **datetime** -Werte verhalten sich im DirectQuery-Modus auf die gleiche Weise wie bei SQL Server.</span><span class="sxs-lookup"><span data-stu-id="411db-162">In DirectQuery mode, casts from string representations of dates and times to actual **datetime** values behave the same way as they do in SQL Server.</span></span>  
  
<span data-ttu-id="411db-163">Informationen zu den Regeln, die Umwandlungen von Zeichen folgen in **DateTime** -Datentypen in [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] Modellen Regeln, finden Sie in der [DAX-Syntax Referenz](/dax/dax-syntax-reference).</span><span class="sxs-lookup"><span data-stu-id="411db-163">For information about the rules governing casts from string to **datetime** data types in [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] models, see the [DAX Syntax Reference](/dax/dax-syntax-reference).</span></span>
  
<span data-ttu-id="411db-164">Modelle, die den speicherinternen Datenspeicher verwenden, unterstützen weniger Textformate für Datumsangaben als die entsprechenden von SQL Server unterstützten Zeichenfolgenformate.</span><span class="sxs-lookup"><span data-stu-id="411db-164">Models that use the in-memory data store support a more limited range of text formats for dates than the string formats for dates that are supported by SQL Server.</span></span> <span data-ttu-id="411db-165">Die DAX-Programmiersprache unterstützt jedoch benutzerdefinierte Datums- und Uhrzeitformate.</span><span class="sxs-lookup"><span data-stu-id="411db-165">However, DAX supports custom date and time formats.</span></span>  
  
<span data-ttu-id="411db-166">**Umwandeln von Zeichenfolgen in andere nicht-boolesche Werte**</span><span class="sxs-lookup"><span data-stu-id="411db-166">**Cast from string to other non Boolean values**</span></span>  
<span data-ttu-id="411db-167">Bei der Umwandlung von Zeichenfolgen in nicht-boolesche Werte verhält sich der DirectQuery-Modus auf die gleiche Weise wie SQL Server.</span><span class="sxs-lookup"><span data-stu-id="411db-167">When casting from strings to non-Boolean values, DirectQuery mode behaves the same as SQL Server.</span></span> <span data-ttu-id="411db-168">Weitere Informationen finden Sie unter [CAST und CONVERT (Transact-SQL)](https://msdn.microsoft.com/a87d0850-c670-4720-9ad5-6f5a22343ea8).</span><span class="sxs-lookup"><span data-stu-id="411db-168">For more information, see [CAST and CONVERT (Transact-SQL)](https://msdn.microsoft.com/a87d0850-c670-4720-9ad5-6f5a22343ea8).</span></span>  
  
<span data-ttu-id="411db-169">**Umwandlung von Zahlen in Zeichenfolgen nicht zulässig**</span><span class="sxs-lookup"><span data-stu-id="411db-169">**Cast from numbers to string not allowed**</span></span>  
<span data-ttu-id="411db-170">BEISPIEL: `CONCATENATE(102,",345")`</span><span class="sxs-lookup"><span data-stu-id="411db-170">EXAMPLE: `CONCATENATE(102,",345")`</span></span>  
  
<span data-ttu-id="411db-171">Die Umwandlung von Zahlen in Zeichenfolgen ist bei SQL Server nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="411db-171">Casting from numbers to strings is not allowed in SQL Server.</span></span>  
  
<span data-ttu-id="411db-172">Diese Formel gibt einen Fehler in Tabellenmodellen und im DirectQuery-Modus zurück. Die Formel erzeugt allerdings in [!INCLUDE[ssGemini](../includes/ssgemini-md.md)]ein Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="411db-172">This formula returns an error in tabular models and in DirectQuery mode; however, the formula produces a result in [!INCLUDE[ssGemini](../includes/ssgemini-md.md)].</span></span>  
  
<span data-ttu-id="411db-173">**Keine Unterstützung für Umwandlungen mit zwei Versuchen in DirectQuery**</span><span class="sxs-lookup"><span data-stu-id="411db-173">**No support for two-try casts in DirectQuery**</span></span>  
<span data-ttu-id="411db-174">Bei speicherinternen Modellen erfolgt oftmals ein zweiter Umwandlungsversuch, wenn der erste fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="411db-174">In-memory models often attempt a second cast when the first one fails.</span></span> <span data-ttu-id="411db-175">Dies geschieht nicht im DirectQuery-Modus.</span><span class="sxs-lookup"><span data-stu-id="411db-175">This never happens in DirectQuery mode.</span></span>  
  
<span data-ttu-id="411db-176">BEISPIEL: `TODAY() + "13:14:15"`</span><span class="sxs-lookup"><span data-stu-id="411db-176">EXAMPLE: `TODAY() + "13:14:15"`</span></span>  
  
<span data-ttu-id="411db-177">In diesem Ausdruck weist der erste Parameter den Typ **datetime** und der zweite Parameter den Typ **string**auf.</span><span class="sxs-lookup"><span data-stu-id="411db-177">In this expression, the first parameter has type **datetime** and second parameter has type **string**.</span></span> <span data-ttu-id="411db-178">Die Umwandlungen werden jedoch im Fall der Kombination der Operanden unterschiedlich gehandhabt.</span><span class="sxs-lookup"><span data-stu-id="411db-178">However, the casts when combining the operands are handled differently.</span></span> <span data-ttu-id="411db-179">DAX führt eine implizite Umwandlung von **string** in **double**aus.</span><span class="sxs-lookup"><span data-stu-id="411db-179">DAX will perform an implicit cast from **string** to **double**.</span></span> <span data-ttu-id="411db-180">Bei speicherinternen Modellen versucht die Formel-Engine, eine direkte Umwandlung in **double** vorzunehmen. Missling dieser Vorgang, wird versucht, die Zeichenfolge in **datetime** umzuwandeln.</span><span class="sxs-lookup"><span data-stu-id="411db-180">In in-memory models, the formula engine attempts to cast directly to **double**, and if that fails, it will try to cast the string to **datetime**.</span></span>  
  
<span data-ttu-id="411db-181">Im DirectQuery-Modus wird nur die direkte Umwandlung von **string** in **double** übernommen.</span><span class="sxs-lookup"><span data-stu-id="411db-181">In DirectQuery mode, only the direct cast from **string** to **double** will be applied.</span></span> <span data-ttu-id="411db-182">Schlägt diese Umwandlung fehl, gibt die Formel einen Fehler zurück.</span><span class="sxs-lookup"><span data-stu-id="411db-182">If this cast fails, the formula will return an error.</span></span>  
  
### <a name="math-functions-and-arithmetic-operations"></a><a name="bkmk_Math"></a><span data-ttu-id="411db-183">Mathematische Funktionen und arithmetische Vorgänge</span><span class="sxs-lookup"><span data-stu-id="411db-183">Math functions and arithmetic operations</span></span>  
<span data-ttu-id="411db-184">Einige mathematische Funktionen geben im DirectQuery-Modus andere Ergebnisse zurück. Dies ist auf Unterschiede des zugrunde liegenden Datentyps oder der Umwandlungen zurückzuführen, die in Vorgängen übernommen werden können.</span><span class="sxs-lookup"><span data-stu-id="411db-184">Some mathematical functions will return different results in DirectQuery mode because of differences in the underlying data type or the casts that can be applied in operations.</span></span> <span data-ttu-id="411db-185">Zudem können sich die zuvor beschriebenen Einschränkungen der zulässigen Werte auf das Ergebnis von arithmetischen Vorgängen auswirken.</span><span class="sxs-lookup"><span data-stu-id="411db-185">Also, the restrictions described above on the allowed range of values might affect the outcome of arithmetic operations.</span></span>  
  
<span data-ttu-id="411db-186">**Reihenfolge der Hinzufügung**</span><span class="sxs-lookup"><span data-stu-id="411db-186">**Order of addition**</span></span>  
<span data-ttu-id="411db-187">Wenn Sie eine Formel erstellen, die eine Reihe von Zahlen hinzufügt, verarbeitet ein speicherinternes Modell die Zahlen u. U. in einer anderen Reihenfolge als ein DirectQuery-Modell.</span><span class="sxs-lookup"><span data-stu-id="411db-187">When you create a formula that adds a series of numbers, an in-memory model might process the numbers in a different order than a DirectQuery model.</span></span>  <span data-ttu-id="411db-188">Liegen demnach viele sehr hohe positive Zahlen und sehr hohe negative Zahlen vor, wird möglicherweise ein Fehler in einem Vorgang zurückgegeben, und ein weiterer Vorgang wird ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="411db-188">Therefore, when you have many very large positive numbers and very large negative numbers, you may get an error in one operation and results in another operation.</span></span>  
  
<span data-ttu-id="411db-189">**Verwendung der POWER-Funktion**</span><span class="sxs-lookup"><span data-stu-id="411db-189">**Use of the POWER function**</span></span>  
<span data-ttu-id="411db-190">BEISPIEL: `POWER(-64, 1/3)`</span><span class="sxs-lookup"><span data-stu-id="411db-190">EXAMPLE: `POWER(-64, 1/3)`</span></span>  
  
<span data-ttu-id="411db-191">Im DirectQuery-Modus kann die POWER-Funktion keine negativen Werte als Basis für Berechnungen mit Bruchexponenten verwenden.</span><span class="sxs-lookup"><span data-stu-id="411db-191">In DirectQuery mode, the POWER function cannot use negative values as the base when raised to a fractional exponent.</span></span> <span data-ttu-id="411db-192">Dies ist das erwartete Verhalten in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="411db-192">This is the expected behavior in SQL Server.</span></span>  
  
<span data-ttu-id="411db-193">Bei einem speicherinternen Modell gibt die Formel den Wert "-4" zurück.</span><span class="sxs-lookup"><span data-stu-id="411db-193">In an in-memory model, the formula returns -4.</span></span>  
  
<span data-ttu-id="411db-194">**Numerische Überlaufvorgänge**</span><span class="sxs-lookup"><span data-stu-id="411db-194">**Numerical overflow operations**</span></span>  
<span data-ttu-id="411db-195">In Transact-SQL geben Vorgänge, die zu einem numerischen Überlauf führen, einen Überlauffehler zurück. Daher geben auch Formeln, die zu einem Überlauf führen, einen Fehler im DirectQuery-Modus zurück.</span><span class="sxs-lookup"><span data-stu-id="411db-195">In Transact-SQL, operations that result in a numerical overflow return an overflow error; therefore, formulas that result in an overflow also raise an error in DirectQuery mode.</span></span>  
  
<span data-ttu-id="411db-196">Die gleiche Formel gibt allerdings bei Verwendung in einem speicherinternen Modell eine ganze Zahl mit einer Länge von acht Byte zurück.</span><span class="sxs-lookup"><span data-stu-id="411db-196">However, the same formula when used in an in-memory model returns an eight-byte integer.</span></span> <span data-ttu-id="411db-197">Das liegt daran, dass die Formel-Engine keine Überprüfungen für numerische Überläufe ausführt.</span><span class="sxs-lookup"><span data-stu-id="411db-197">That is because the formula engine does not perform checks for numerical overflows.</span></span>  
  
<span data-ttu-id="411db-198">**LOG-Funktionen mit Leerzeichen geben andere Ergebnisse zurück.**</span><span class="sxs-lookup"><span data-stu-id="411db-198">**LOG functions with blanks return different results**</span></span>  
<span data-ttu-id="411db-199">SQL Server behandelt NULL-Werte und Leerzeichen anders als die xVelocity-Engine.</span><span class="sxs-lookup"><span data-stu-id="411db-199">SQL Server handles nulls and blanks differently than the xVelocity engine.</span></span> <span data-ttu-id="411db-200">Daher gibt die folgende Formel einen Fehler im directquery-Modus zurück, gibt jedoch unendlich (-INF) im in-Memory-Modus zurück.</span><span class="sxs-lookup"><span data-stu-id="411db-200">As a result, the following formula returns an error in DirectQuery mode, but return infinity (-inf) in in-memory mode.</span></span>  
  
`EXAMPLE: LOG(blank())`  
  
<span data-ttu-id="411db-201">Die gleichen Einschränkungen gelten für die anderen logarithmischen Funktionen: LOG10 und LN.</span><span class="sxs-lookup"><span data-stu-id="411db-201">The same limitations apply to the other logarithmic functions: LOG10 and LN.</span></span>  
  
<span data-ttu-id="411db-202">Weitere Informationen zum **blank** -Datentyp in der DAX-Programmiersprache finden Sie in der [DAX-Syntaxspezifikation für PowerPivot](/dax/dax-syntax-reference).</span><span class="sxs-lookup"><span data-stu-id="411db-202">For more information about the **blank** data type in DAX, see [DAX Syntax Reference](/dax/dax-syntax-reference).</span></span>
  
<span data-ttu-id="411db-203">**Division durch 0 und Division durch Leerzeichen**</span><span class="sxs-lookup"><span data-stu-id="411db-203">**Division by 0 and division by Blank**</span></span>  
<span data-ttu-id="411db-204">Im DirectQuery-Modus führt die Division durch null (0) bzw. die Division durch BLANK stets zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="411db-204">In DirectQuery mode, division by zero (0) or division by BLANK will always result in an error.</span></span> <span data-ttu-id="411db-205">SQL Server unterstützt nicht die Definition der Unendlichkeit, und da das natürliche Ergebnis jeder Division durch 0 die Unendlichkeit ist, entspricht das Ergebnis einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="411db-205">SQL Server does not support the notion of infinity, and because the natural result of any division by 0 is infinity, the result is an error.</span></span> <span data-ttu-id="411db-206">SQL Server unterstützt jedoch die Division durch NULL-Werte, und das Ergebnis muss stets einem NULL-Wert entsprechen.</span><span class="sxs-lookup"><span data-stu-id="411db-206">However, SQL Server supports division by nulls, and the result must always equal null.</span></span>  
  
<span data-ttu-id="411db-207">Anstelle der Rückgabe unterschiedlicher Ergebnisse für diese Vorgänge geben beide Vorgangstypen (Division durch null und Division durch einen NULL-Wert) im DirectQuery-Modus einen Fehler zurück.</span><span class="sxs-lookup"><span data-stu-id="411db-207">Rather than return different results for these operations, in DirectQuery mode, both types of operations (division by zero and division by null) return an error.</span></span>  
  
<span data-ttu-id="411db-208">Beachten Sie, dass die Division durch 0 in Excel und in [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] -Modellen auch einen Fehler zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="411db-208">Note that, in Excel and in [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] models, division by zero also returns an error.</span></span> <span data-ttu-id="411db-209">Die Division durch ein Leerzeichen gibt ein Leerzeichen zurück.</span><span class="sxs-lookup"><span data-stu-id="411db-209">Division by a blank returns a blank.</span></span>  
  
<span data-ttu-id="411db-210">Die folgenden Ausdrücke sind in speicherinternen Modellen gültig, schlagen jedoch im DirectQuery-Modus fehl:</span><span class="sxs-lookup"><span data-stu-id="411db-210">The following expressions are all valid in in-memory models, but will fail in DirectQuery mode:</span></span>  
  
`1/BLANK`  
  
`1/0`  
  
`0.0/BLANK`  
  
`0/0`  
  
<span data-ttu-id="411db-211">Der Ausdruck `BLANK/BLANK` ist ein besonderer Fall, der `BLANK` sowohl in speicherinternen Modellen als auch im DirectQuery-Modus zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="411db-211">The expression `BLANK/BLANK` is a special case that returns `BLANK` in both for in-memory models, and in DirectQuery mode.</span></span>  
  
### <a name="supported-numeric-and-date-time-ranges"></a><a name="bkmk_Ranges"></a><span data-ttu-id="411db-212">Unterstützte numerische und Datums-/Uhrzeitbereiche</span><span class="sxs-lookup"><span data-stu-id="411db-212">Supported numeric and date-time ranges</span></span>  
<span data-ttu-id="411db-213">Formeln in [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] und tabellarischen Modellen im Arbeitsspeicher unterliegen den gleichen Einschränkungen wie Excel in Bezug auf die maximal zulässigen Werte für reelle Zahlen und Datumsangaben.</span><span class="sxs-lookup"><span data-stu-id="411db-213">Formulas in [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] and tabular models in-memory are subject to the same limitations as Excel with regard to maximum allowed values for real numbers and dates.</span></span> <span data-ttu-id="411db-214">Unterschiede können jedoch entstehen, wenn der maximale Wert von einer Berechnung oder einer Abfrage zurückgegeben wird, oder wenn Werte konvertiert, umgewandelt, gerundet oder gekürzt werden.</span><span class="sxs-lookup"><span data-stu-id="411db-214">However, differences can arise when the maximum value is returned from a calculation or query, or when values are converted, cast, rounded, or truncated.</span></span>  
  
-   <span data-ttu-id="411db-215">Werden Werte der Typen **Currency** und **Real** multipliziert, und ist das Ergebnis größer als der maximal mögliche Wert, wird im DirectQuery-Modus kein Fehler ausgelöst. Zudem wird ein NULL-Wert zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="411db-215">If values of types **Currency** and **Real** are multiplied, and the result is larger than the maximum possible value, in DirectQuery mode, no error is raised, and a null is returned.</span></span>  
  
-   <span data-ttu-id="411db-216">Bei speicherinternen Modellen wird kein Fehler ausgelöst, aber der maximale Wert wird zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="411db-216">In in-memory models, no error is raised, but the maximum value is returned.</span></span>  
  
<span data-ttu-id="411db-217">Da die zulässigen Datumsbereiche für Excel und SQL Server unterschiedlich sind, kann im Allgemeinen gewährleistet werden, dass Ergebnisse nur übereinstimmen, wenn sich Datumsangaben innerhalb des üblichen Datumsbereichs befinden. Dazu gehören die folgenden Datumsangaben:</span><span class="sxs-lookup"><span data-stu-id="411db-217">In general, because the accepted date ranges are different for Excel and SQL Server, results can be guaranteed to match only when dates are within the common date range, which is inclusive of the following dates:</span></span>  
  
-   <span data-ttu-id="411db-218">Frühestes Datum: 1. März 1990</span><span class="sxs-lookup"><span data-stu-id="411db-218">Earliest date: March 1, 1990</span></span>  
  
-   <span data-ttu-id="411db-219">Letztes Datum: 31. Dezember 9999</span><span class="sxs-lookup"><span data-stu-id="411db-219">Latest date: December 31, 9999</span></span>  
  
<span data-ttu-id="411db-220">Wenn in Formeln verwendete Datumsangaben außerhalb dieses Bereichs liegen, führt entweder die Formel zu einem Fehler, oder die Ergebnisse stimmen nicht überein.</span><span class="sxs-lookup"><span data-stu-id="411db-220">If any dates used in formulas fall outside this range, either the formula will result in an error, or the results will not match.</span></span>  
  
<span data-ttu-id="411db-221">**Von CEILING unterstützte Gleitkommawerte**</span><span class="sxs-lookup"><span data-stu-id="411db-221">**Floating point values supported by CEILING**</span></span>  
<span data-ttu-id="411db-222">BEISPIEL: `EVALUATE ROW("x", CEILING(-4.398488E+30, 1))`</span><span class="sxs-lookup"><span data-stu-id="411db-222">EXAMPLE: `EVALUATE ROW("x", CEILING(-4.398488E+30, 1))`</span></span>  
  
<span data-ttu-id="411db-223">Die Transact-SQL-Entsprechung für die DAX-CEILING-Funktion unterstützt nur Werte mit einer Größe von maximal 10^19.</span><span class="sxs-lookup"><span data-stu-id="411db-223">The Transact-SQL equivalent of the DAX CEILING function only supports values with magnitude of 10^19 or less.</span></span> <span data-ttu-id="411db-224">Als Faustregel gilt, dass Gleitkommawerte in **bigint**passen sollten.</span><span class="sxs-lookup"><span data-stu-id="411db-224">A rule of thumb is that floating point values should be able to fit into **bigint**.</span></span>  
  
<span data-ttu-id="411db-225">**Datepart-Funktionen mit Datumsangaben außerhalb des Bereichs**</span><span class="sxs-lookup"><span data-stu-id="411db-225">**Datepart functions with dates that are out of range**</span></span>  
<span data-ttu-id="411db-226">Bei Ergebnissen im DirectQuery-Modus wird gewährleistet, dass diese den Ergebnissen von speicherinternen Modellen nur entsprechen, wenn sich das als Argument verwendete Datum innerhalb des gültigen Datumsbereichs befindet.</span><span class="sxs-lookup"><span data-stu-id="411db-226">Results in DirectQuery mode are guaranteed to match those in in-memory models only when the date used as the argument is in the valid date range.</span></span> <span data-ttu-id="411db-227">Werden diese Bedingungen nicht erfüllt, wird entweder ein Fehler ausgelöst, oder die Formel gibt in DirectQuery andere Ergebnisse zurück als im speicherinternen Modus.</span><span class="sxs-lookup"><span data-stu-id="411db-227">If these conditions are not satisfied, either an error will be raised, or the formula will return different results in DirectQuery than in in-memory mode.</span></span>  
  
<span data-ttu-id="411db-228">BEISPIEL: `MONTH(0)` oder `YEAR(0)`</span><span class="sxs-lookup"><span data-stu-id="411db-228">EXAMPLE: `MONTH(0)` or `YEAR(0)`</span></span>  
  
<span data-ttu-id="411db-229">Im DirectQuery-Modus geben die Ausdrücke 12 bzw. 1899 zurück.</span><span class="sxs-lookup"><span data-stu-id="411db-229">In DirectQuery mode, the expressions return 12 and 1899, respectively.</span></span>  
  
<span data-ttu-id="411db-230">Bei speicherinternen Modellen geben die Ausdrücke 1 bzw. 1900 zurück.</span><span class="sxs-lookup"><span data-stu-id="411db-230">In in-memory models, the expressions return 1 and 1900, respectively.</span></span>  
  
<span data-ttu-id="411db-231">BEISPIEL:  `EOMONTH(0.0001, 1)`</span><span class="sxs-lookup"><span data-stu-id="411db-231">EXAMPLE:  `EOMONTH(0.0001, 1)`</span></span>  
  
<span data-ttu-id="411db-232">Die Ergebnisse dieses Ausdrucks stimmen nur überein, wenn sich die als Parameter angegebenen Daten innerhalb des gültigen Datumsbereichs befinden.</span><span class="sxs-lookup"><span data-stu-id="411db-232">The results of this expression will match only when the data supplied as a parameter is within the valid date range.</span></span>  
  
<span data-ttu-id="411db-233">BEISPIEL: `EOMONTH(blank(), blank())` oder `EDATE(blank(), blank())`</span><span class="sxs-lookup"><span data-stu-id="411db-233">EXAMPLE: `EOMONTH(blank(), blank())` or `EDATE(blank(), blank())`</span></span>  
  
<span data-ttu-id="411db-234">Die Ergebnisse dieses Ausdrucks sollten im DirectQuery-Modus sowie im speicherinternen Modus gleich sein.</span><span class="sxs-lookup"><span data-stu-id="411db-234">The results of this expression should be the same in DirectQuery mode and in-memory mode.</span></span>  
  
<span data-ttu-id="411db-235">**Kürzen von Zeitwerten**</span><span class="sxs-lookup"><span data-stu-id="411db-235">**Truncation of time values**</span></span>  
<span data-ttu-id="411db-236">BEISPIEL: `SECOND(1231.04097222222)`</span><span class="sxs-lookup"><span data-stu-id="411db-236">EXAMPLE: `SECOND(1231.04097222222)`</span></span>  
  
<span data-ttu-id="411db-237">Im DirectQuery-Modus wird das Ergebnis auf Basis der Regeln für SQL Server gekürzt. Zudem ergibt der Ausdruck den Wert "59".</span><span class="sxs-lookup"><span data-stu-id="411db-237">In DirectQuery mode, the result is truncated, following the rules of SQL Server, and the expression evaluates to 59.</span></span>  
  
<span data-ttu-id="411db-238">Bei speicherinternen Modellen werden die Ergebnisse jedes Zwischenvorgangs gerundet. Daher ergibt der Ausdruck den Wert "0".</span><span class="sxs-lookup"><span data-stu-id="411db-238">In in-memory models, the results of each interim operation are rounded; therefore, the expression evaluates to 0.</span></span>  
  
<span data-ttu-id="411db-239">Im folgenden Beispiel wird veranschaulicht, wie dieser Wert berechnet wird:</span><span class="sxs-lookup"><span data-stu-id="411db-239">The following example demonstrates how this value is calculated:</span></span>  
  
1.  <span data-ttu-id="411db-240">Der Bruch der Eingabe (0.04097222222) wird mit 24 multipliziert.</span><span class="sxs-lookup"><span data-stu-id="411db-240">The fraction of the input (0.04097222222) is multiplied by 24.</span></span>  
  
2.  <span data-ttu-id="411db-241">Der resultierende Stundenwert (0.98333333328) wird mit 60 multipliziert.</span><span class="sxs-lookup"><span data-stu-id="411db-241">The resulting hour value (0.98333333328) is multiplied by 60.</span></span>  
  
3.  <span data-ttu-id="411db-242">Der resultierende Minutenwert ist 58.9999999968.</span><span class="sxs-lookup"><span data-stu-id="411db-242">The resulting minute value is 58.9999999968.</span></span>  
  
4.  <span data-ttu-id="411db-243">Der Bruch des Minutenwerts (0.9999999968) wird mit 60 multipliziert.</span><span class="sxs-lookup"><span data-stu-id="411db-243">The fraction of the minute value (0.9999999968) is multiplied by 60.</span></span>  
  
5.  <span data-ttu-id="411db-244">Der resultierende zweite Wert (59.999999808) wird auf 60 aufgerundet.</span><span class="sxs-lookup"><span data-stu-id="411db-244">The resulting second value (59.999999808) rounds up to 60.</span></span>  
  
6.  <span data-ttu-id="411db-245">60 entspricht 0.</span><span class="sxs-lookup"><span data-stu-id="411db-245">60 is equivalent to 0.</span></span>  
  
<span data-ttu-id="411db-246">**SQL-Zeitdatentyp nicht unterstützt**</span><span class="sxs-lookup"><span data-stu-id="411db-246">**SQL Time data type not supported**</span></span>  
<span data-ttu-id="411db-247">Bei speicherinternen Modellen wird die Verwendung des neuen **Time** -Datentyps nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="411db-247">In-memory models do not support use of the new SQL **Time** data type.</span></span> <span data-ttu-id="411db-248">Im DirectQuery-Modus geben Formeln, die mit diesem Datentyp auf Spalten verweisen, einen Fehler zurück.</span><span class="sxs-lookup"><span data-stu-id="411db-248">In DirectQuery mode, formulas that reference columns with this data type will return an error.</span></span> <span data-ttu-id="411db-249">Zeitdatenspalten können nicht in ein speicherinternes Modell importiert werden.</span><span class="sxs-lookup"><span data-stu-id="411db-249">Time data columns cannot be imported into an in-memory model.</span></span>  
  
<span data-ttu-id="411db-250">In [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] und in zwischengespeicherten Modellen wandelt die Engine den Zeitwert jedoch manchmal in einen akzeptablen Datentyp um, und die Formel gibt ein Ergebnis zurück.</span><span class="sxs-lookup"><span data-stu-id="411db-250">However, in [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] and in cached models, sometimes the engine casts the time value to an acceptable data type, and the formula returns a result.</span></span>  
  
<span data-ttu-id="411db-251">Dieses Verhalten beeinflusst alle Funktionen, die eine Datumsspalte als Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="411db-251">This behavior affects all functions that use a date column as a parameter.</span></span>  
  
### <a name="currency"></a><a name="bkmk_Currency"></a><span data-ttu-id="411db-252">Währungs</span><span class="sxs-lookup"><span data-stu-id="411db-252">Currency</span></span>  
<span data-ttu-id="411db-253">Im DirectQuery-Modus muss der Wert innerhalb des folgenden Bereichs liegen, wenn das Ergebnis eines arithmetischen Vorgangs den Typ **Currency**aufweist:</span><span class="sxs-lookup"><span data-stu-id="411db-253">In DirectQuery mode, if the result of an arithmetic operation has the type **Currency**, the value must be within the following range:</span></span>  
  
-   <span data-ttu-id="411db-254">Minimum: -922337203685477,5808</span><span class="sxs-lookup"><span data-stu-id="411db-254">Minimum: -922337203685477.5808</span></span>  
  
-   <span data-ttu-id="411db-255">Maximum: 922337203685477,5807</span><span class="sxs-lookup"><span data-stu-id="411db-255">Maximum: 922337203685477.5807</span></span>  
  
<span data-ttu-id="411db-256">**Kombinieren von Währungs- und REAL-Datentypen**</span><span class="sxs-lookup"><span data-stu-id="411db-256">**Combining currency and REAL data types**</span></span>  
<span data-ttu-id="411db-257">BEISPIEL: `Currency sample 1`</span><span class="sxs-lookup"><span data-stu-id="411db-257">EXAMPLE: `Currency sample 1`</span></span>  
  
<span data-ttu-id="411db-258">Wenn die Typen **Currency** und **Real** multipliziert werden und das Ergebnis größer als 9223372036854774784 (0x7ffffffffffffc00) ist, wird im DirectQuery-Modus kein Fehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="411db-258">If **Currency** and **Real** types are multiplied, and the result is larger than 9223372036854774784 (0x7ffffffffffffc00), DirectQuery mode will not raise an error.</span></span>  
  
<span data-ttu-id="411db-259">Bei einem speicherinternen Modell wird ein Fehler ausgelöst, wenn der absolute Wert des Ergebnisses größer als 922337203685477,4784 ist.</span><span class="sxs-lookup"><span data-stu-id="411db-259">In an in-memory model, an error is raised if the absolute value of the result is larger than 922337203685477.4784.</span></span>  
  
<span data-ttu-id="411db-260">**Vorgang führt zu einem Wert außerhalb des Bereichs**</span><span class="sxs-lookup"><span data-stu-id="411db-260">**Operation results in an out-of-range value**</span></span>  
<span data-ttu-id="411db-261">BEISPIEL: `Currency sample 2`</span><span class="sxs-lookup"><span data-stu-id="411db-261">EXAMPLE: `Currency sample 2`</span></span>  
  
<span data-ttu-id="411db-262">Wenn Vorgänge zu zwei Währungswerten einen Wert ergeben, der sich außerhalb des angegebenen Bereichs befindet, wird bei speicherinternen Modellen ein Fehler ausgegeben, jedoch nicht bei DirectQuery-Modellen.</span><span class="sxs-lookup"><span data-stu-id="411db-262">If operations on any two currency values result in a value that is outside the specified range, an error is raised in in-memory models, but not in DirectQuery models.</span></span>  
  
<span data-ttu-id="411db-263">**Kombinieren von Währungsdatentypen mit anderen Datentypen**</span><span class="sxs-lookup"><span data-stu-id="411db-263">**Combining currency with other data types**</span></span>  
<span data-ttu-id="411db-264">Die Division von Währungswerten durch Werte anderer numerischer Typen kann zu unterschiedlichen Ergebnissen führen.</span><span class="sxs-lookup"><span data-stu-id="411db-264">Division of currency values by values of other numeric types can result in different results.</span></span>  
  
### <a name="aggregation-functions"></a><a name="bkmk_Aggregations"></a><span data-ttu-id="411db-265">Aggregationsfunktionen</span><span class="sxs-lookup"><span data-stu-id="411db-265">Aggregation functions</span></span>  
<span data-ttu-id="411db-266">Statistische Funktionen in einer Tabelle mit einer Zeile geben andere Ergebnisse zurück.</span><span class="sxs-lookup"><span data-stu-id="411db-266">Statistical functions on a table with one row return different results.</span></span> <span data-ttu-id="411db-267">Aggregationsfunktionen für leere Tabellen verhalten sich zudem bei speicherinternen Modellen anders als im DirectQuery-Modus.</span><span class="sxs-lookup"><span data-stu-id="411db-267">Aggregation functions over empty tables also behave differently in in-memory models than they do in DirectQuery mode.</span></span>  
  
<span data-ttu-id="411db-268">**Statistische Funktionen für eine Tabelle mit einer einzelnen Zeile**</span><span class="sxs-lookup"><span data-stu-id="411db-268">**Statistical functions over a table with a single row**</span></span>  
<span data-ttu-id="411db-269">Wenn die als Argument verwendete Tabelle eine einzelne Zeile enthält, geben statistische Funktionen wie STDEV und VAR im DirectQuery-Modus einen NULL-Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="411db-269">If the table that is used as argument contains a single row, in DirectQuery mode, statistical functions such as STDEV and VAR return null.</span></span>  
  
<span data-ttu-id="411db-270">In einem speicherinternen Modell gibt eine Formel, die STDEV oder VAR für eine Tabelle mit einer einzelnen Zeile verwendet, einen Fehler wegen einer Division durch 0 zurück.</span><span class="sxs-lookup"><span data-stu-id="411db-270">In an in-memory model, a formula that uses STDEV or VAR over a table with a single row returns a division by zero error.</span></span>  
  
### <a name="text-functions"></a><a name="bkmk_Text"></a><span data-ttu-id="411db-271">Textfunktionen</span><span class="sxs-lookup"><span data-stu-id="411db-271">Text functions</span></span>  
<span data-ttu-id="411db-272">Da relationale Datenspeicher andere Textdatentypen bereitstellen als Excel, werden bei der Suche nach Zeichenfolgen oder bei der Arbeit mit Teilzeichenfolgen möglicherweise andere Ergebnisse zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="411db-272">Because relational data stores provide different text data types than does Excel, you may see different results when searching strings or working with substrings.</span></span> <span data-ttu-id="411db-273">Die Länge der Zeichenfolgen kann auch unterschiedlich sein.</span><span class="sxs-lookup"><span data-stu-id="411db-273">The length of strings also can be different.</span></span>  
  
<span data-ttu-id="411db-274">Im Allgemeinen funktioniert jede Zeichenfolgenbearbeitung, die Spalten mit fester Größe verwendet, wie Argumente über andere Ergebnisse verfügen können.</span><span class="sxs-lookup"><span data-stu-id="411db-274">In general, any string manipulation functions that use fixed-size columns as arguments can have different results.</span></span>  
  
<span data-ttu-id="411db-275">Darüber hinaus unterstützen einige Textfunktionen in SQL Server zusätzliche Argumente, die nicht in Excel bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="411db-275">Additionally, in SQL Server, some text functions support additional arguments that are not provided in Excel.</span></span> <span data-ttu-id="411db-276">Wenn die Formel das fehlende Argument erfordert, können andere Ergebnisse oder Fehler im speicherinternen Modell zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="411db-276">If the formula requires the missing argument you can get different results or errors in the in-memory model.</span></span>  
  
<span data-ttu-id="411db-277">**Vorgänge, die ein Zeichen mit LEFT, RIGHT usw. zurückgeben, geben möglicherweise das richtige Zeichen zurück – allerdings in einer anderen Schreibweise. Alternativ werden keine Ergebnisse zurückgegeben.**</span><span class="sxs-lookup"><span data-stu-id="411db-277">**Operations that return a character using LEFT, RIGHT, etc. may return the correct character but in a different case, or no results**</span></span>  
<span data-ttu-id="411db-278">BEISPIEL: `LEFT(["text"], 2)`</span><span class="sxs-lookup"><span data-stu-id="411db-278">EXAMPLE: `LEFT(["text"], 2)`</span></span>  
  
<span data-ttu-id="411db-279">Im DirectQuery-Modus entspricht die Schreibweise des Zeichens, das zurückgegeben wird, stets dem Buchstaben, der in der Datenbank gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="411db-279">In DirectQuery mode, the case of the character that is returned is always exactly the same as the letter that is stored in the database.</span></span> <span data-ttu-id="411db-280">Das xVelocity-Engine verwendet jedoch aus Leistungsgründen einen anderen Algorithmus für die Komprimierung und Indizierung von Werten.</span><span class="sxs-lookup"><span data-stu-id="411db-280">However, the xVelocity engine uses a different algorithm for compression and indexing of values, to improve performance.</span></span>  
  
<span data-ttu-id="411db-281">Standardmäßig wird die Latin1_General-Sortierung verwendet (ohne Berücksichtigung der Groß-/Kleinschreibung und mit Unterscheidung von Akzenten).</span><span class="sxs-lookup"><span data-stu-id="411db-281">By default, the Latin1_General collation is used, which is case-insensitive but accent-sensitive.</span></span> <span data-ttu-id="411db-282">Sind mehrere Instanzen einer Textzeichenfolge in Kleinbuchstaben, Großbuchstaben oder mit gemischter Schreibweise vorhanden, werden folglich alle Instanzen als gleiche Zeichenfolge betrachtet, und nur die erste Instanz der Zeichenfolge wird im Index gespeichert.</span><span class="sxs-lookup"><span data-stu-id="411db-282">Therefore, if there are multiple instances of a text string in lower case, upper case, or mixed case, all instances are considered the same string, and only the first instance of the string is stored in the index.</span></span> <span data-ttu-id="411db-283">Sämtliche Textfunktionen, die bei gespeicherten Zeichenfolgen ausgeführt werden, rufen den angegebenen Teil des indizierten Formulars ab.</span><span class="sxs-lookup"><span data-stu-id="411db-283">All text functions that operate on stored strings will retrieve the specified portion of the indexed form.</span></span> <span data-ttu-id="411db-284">Daher gibt die Beispielformel den gleichen Wert für die gesamte Spalte zurück und verwendet dabei die erste Instanz als Eingabe.</span><span class="sxs-lookup"><span data-stu-id="411db-284">Therefore, the example formula would return the same value for the entire column, using the first instance as the input.</span></span>  
  
[<span data-ttu-id="411db-285">Zeichenfolgenspeicher und -sortierung in Tabellenmodellen</span><span class="sxs-lookup"><span data-stu-id="411db-285">String Storage and Collation in Tabular Models</span></span>](https://msdn.microsoft.com/8516f0ad-32ee-4688-a304-e705143642ca)  
  
<span data-ttu-id="411db-286">Dieses Verhalten gilt auch für andere Textfunktionen, einschließlich RIGHT, MID usw.</span><span class="sxs-lookup"><span data-stu-id="411db-286">This behavior also applies to other text functions, including RIGHT, MID, and so forth.</span></span>  
  
<span data-ttu-id="411db-287">**Zeichenfolgenlänge wirkt sich auf Ergebnisse aus**</span><span class="sxs-lookup"><span data-stu-id="411db-287">**String length affects results**</span></span>  
<span data-ttu-id="411db-288">BEISPIEL: `SEARCH("within string", "sample target  text", 1, 1)`</span><span class="sxs-lookup"><span data-stu-id="411db-288">EXAMPLE: `SEARCH("within string", "sample target  text", 1, 1)`</span></span>  
  
<span data-ttu-id="411db-289">Wenn Sie mit der SEARCH-Funktion nach einer Zeichenfolge suchen und die Zielzeichenfolge länger ist als die WITHIN-Zeichenfolge, löst der DirectQuery-Modus einen Fehler aus.</span><span class="sxs-lookup"><span data-stu-id="411db-289">If you search for a string using the SEARCH function, and the target string is longer than the within string, DirectQuery mode raises an error.</span></span>  
  
<span data-ttu-id="411db-290">Bei einem speicherinternen Modell wird die gesuchte Zeichenfolge zurückgegeben. Dabei wird jedoch ihre Länge auf die des &lt;WITHIN-Texts&gt;gekürzt.</span><span class="sxs-lookup"><span data-stu-id="411db-290">In an in-memory model, the searched string is returned, but with its length truncated to the length of &lt;within text&gt;.</span></span>  
  
<span data-ttu-id="411db-291">BEISPIEL: `EVALUATE ROW("X", REPLACE("CA", 3, 2, "California") )`</span><span class="sxs-lookup"><span data-stu-id="411db-291">EXAMPLE: `EVALUATE ROW("X", REPLACE("CA", 3, 2, "California") )`</span></span>  
  
<span data-ttu-id="411db-292">Wenn die Ersatzzeichenfolge länger ist als die Originalzeichenfolge, gibt die Formel im DirectQuery-Modus einen NULL-Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="411db-292">If the length of the replacement string is greater than the length of the original string, in DirectQuery mode, the formula returns null.</span></span>  
  
<span data-ttu-id="411db-293">Bei speicherinternen Modellen entspricht das Verhalten der Formel dem von Excel. Dabei werden die Quellzeichenfolge und Ersatzzeichenfolge verkettet, wodurch CACalifornia zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="411db-293">In in-memory models, the formula follows the behavior of Excel, which concatenates the source string and the replacement string, which returns CACalifornia.</span></span>  
  
<span data-ttu-id="411db-294">**TRIM (implizit) in der Mitte von Zeichenfolgen**</span><span class="sxs-lookup"><span data-stu-id="411db-294">**Implicit TRIM in the middle of strings**</span></span>  
<span data-ttu-id="411db-295">BEISPIEL: `TRIM(" A sample sentence with leading white space")`</span><span class="sxs-lookup"><span data-stu-id="411db-295">EXAMPLE: `TRIM(" A sample sentence with leading white space")`</span></span>  
  
<span data-ttu-id="411db-296">Der DirectQuery-Modus übersetzt die DAX-TRIM-Funktion in die SQL-Anweisung `LTRIM(RTRIM(<column>))`.</span><span class="sxs-lookup"><span data-stu-id="411db-296">DirectQuery mode translates the DAX TRIM function to the SQL statement `LTRIM(RTRIM(<column>))`.</span></span> <span data-ttu-id="411db-297">Folglich werden nur führende und nachfolgende Leerstellen entfernt.</span><span class="sxs-lookup"><span data-stu-id="411db-297">As a result, only leading and trailing white space is removed.</span></span>  
  
<span data-ttu-id="411db-298">Im Gegensatz dazu entfernt die gleiche Formel in einem speicherinternen Modell Leerzeichen innerhalb der Zeichenfolge – gemäß dem Verhalten von Excel.</span><span class="sxs-lookup"><span data-stu-id="411db-298">In contrast, the same formula in an in-memory model removes spaces within the string, following the behavior of Excel.</span></span>  
  
<span data-ttu-id="411db-299">**RTRIM (implizit) mit Verwendung der LEN-Funktion**</span><span class="sxs-lookup"><span data-stu-id="411db-299">**Implicit RTRIM with use of LEN function**</span></span>  
<span data-ttu-id="411db-300">BEISPIEL: `LEN('string_column')`</span><span class="sxs-lookup"><span data-stu-id="411db-300">EXAMPLE: `LEN('string_column')`</span></span>  
  
<span data-ttu-id="411db-301">Wie bei SQL Server entfernt auch der DirectQuery-Modus Leerstellen am Ende der Zeichenfolgenspalten automatisch (Ausführung der impliziten RTRIM-Funktion).</span><span class="sxs-lookup"><span data-stu-id="411db-301">Like SQL Server, DirectQuery mode automatically removes white space from the end of string columns: that is, it performs an implicit RTRIM.</span></span> <span data-ttu-id="411db-302">Daher können Formeln, die die LEN-Funktion verwenden, andere Werte zurückgeben, wenn die Zeichenfolge nachfolgende Leerzeichen aufweist.</span><span class="sxs-lookup"><span data-stu-id="411db-302">Therefore, formulas that use the LEN function can return different values if the string has trailing spaces.</span></span>  
  
<span data-ttu-id="411db-303">**Der speicherinterne Modus unterstützt zusätzliche Parameter für SUBSTITUTE.**</span><span class="sxs-lookup"><span data-stu-id="411db-303">**In-memory supports additional parameters for SUBSTITUTE**</span></span>  
<span data-ttu-id="411db-304">BEISPIEL: `SUBSTITUTE([Title],"Doctor","Dr.")`</span><span class="sxs-lookup"><span data-stu-id="411db-304">EXAMPLE: `SUBSTITUTE([Title],"Doctor","Dr.")`</span></span>  
  
<span data-ttu-id="411db-305">BEISPIEL: `SUBSTITUTE([Title],"Doctor","Dr.", 2)`</span><span class="sxs-lookup"><span data-stu-id="411db-305">EXAMPLE: `SUBSTITUTE([Title],"Doctor","Dr.", 2)`</span></span>  
  
<span data-ttu-id="411db-306">Im DirectQuery-Modus können Sie nur die Version dieser Funktion verwenden, die über drei (3) Parameter verfügt: ein Verweis auf eine Spalte, der alte Text und der neue Text.</span><span class="sxs-lookup"><span data-stu-id="411db-306">In DirectQuery mode, you can use only the version of this function that has three (3) parameters: a reference to a column, the old text, and the new text.</span></span> <span data-ttu-id="411db-307">Wenn Sie die zweite Formel verwenden, wird ein Fehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="411db-307">If you use the second formula, an error is raised.</span></span>  
  
<span data-ttu-id="411db-308">Bei speicherinternen Modellen können Sie einen optionalen vierten Parameter verwenden, um die Instanznummer der zu ersetzenden Zeichenfolge anzugeben.</span><span class="sxs-lookup"><span data-stu-id="411db-308">In in-memory models, you can use an optional fourth parameter to specify the instance number of the string to replace.</span></span> <span data-ttu-id="411db-309">Beispielsweise können Sie nur die zweite Instanz ersetzen usw.</span><span class="sxs-lookup"><span data-stu-id="411db-309">For example, you can replace only the second instance, etc.</span></span>  
  
<span data-ttu-id="411db-310">**Einschränkungen der Zeichenfolgenlänge für REPT-Vorgänge**</span><span class="sxs-lookup"><span data-stu-id="411db-310">**Restrictions on string lengths for REPT operations**</span></span>  
<span data-ttu-id="411db-311">Bei speicherinternen Modellen muss die Länge einer Zeichenfolge, die sich aus einem REPT-Vorgang ergibt, weniger als 32.767 Zeichen umfassen.</span><span class="sxs-lookup"><span data-stu-id="411db-311">In in-memory models, the length of a string resulting from an operation using REPT must be less than 32,767 characters.</span></span>  
  
<span data-ttu-id="411db-312">Diese Einschränkung gilt nicht für den DirectQuery-Modus.</span><span class="sxs-lookup"><span data-stu-id="411db-312">This limitation does not apply in DirectQuery mode.</span></span>  
  
<span data-ttu-id="411db-313">**Vorgänge für Teilzeichenfolgen geben abhängig von Zeichentyp andere Ergebnisse zurück**</span><span class="sxs-lookup"><span data-stu-id="411db-313">**Substring operations return different results depending on character type**</span></span>  
<span data-ttu-id="411db-314">BEISPIEL: `MID([col], 2, 5)`</span><span class="sxs-lookup"><span data-stu-id="411db-314">EXAMPLE: `MID([col], 2, 5)`</span></span>  
  
<span data-ttu-id="411db-315">Wenn der Eingabetext **varchar** oder **nvarchar**lautet, ist das Ergebnis der Formel immer gleich.</span><span class="sxs-lookup"><span data-stu-id="411db-315">If the input text is **varchar** or **nvarchar**, the result of the formula is always the same.</span></span>  
  
<span data-ttu-id="411db-316">Wenn der Text jedoch ein Zeichen mit fester Länge ist und der Wert für \* &lt; num_chars &gt; \* größer als die Länge der Ziel Zeichenfolge ist, wird im directquery-Modus am Ende der Ergebnis Zeichenfolge ein leeres-Objekt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="411db-316">However, if the text is a fixed-length character and the value for *&lt;num_chars&gt;* is greater than the length of the target string, in DirectQuery mode, a blank is added at the end of the result string.</span></span>  
  
<span data-ttu-id="411db-317">Bei einem speicherinternen Modell endet das Ergebnis beim letzten Zeichenfolgenzeichen (ohne Auffüllung).</span><span class="sxs-lookup"><span data-stu-id="411db-317">In an in-memory model, the result terminates at the last string character, with no padding.</span></span>  
  
## <a name="functions-supported-in-directquery-mode"></a><a name="bkmk_SupportedFunc"></a><span data-ttu-id="411db-318">Im directquery-Modus unterstützte Funktionen</span><span class="sxs-lookup"><span data-stu-id="411db-318">Functions supported in DirectQuery mode</span></span>  
<span data-ttu-id="411db-319">Die folgenden DAX-Funktionen können im DirectQuery-Modus verwendet werden, allerdings mit den im vorherigen Abschnitt beschriebenen Qualifikationen.</span><span class="sxs-lookup"><span data-stu-id="411db-319">The following DAX functions can be used in DirectQuery mode, but with the qualifications as described in the preceding section.</span></span>  
  
<span data-ttu-id="411db-320">**Text Funktionen**</span><span class="sxs-lookup"><span data-stu-id="411db-320">**Text functions**</span></span>  
  
<span data-ttu-id="411db-321">CONCATENATE</span><span class="sxs-lookup"><span data-stu-id="411db-321">CONCATENATE</span></span>  
  
<span data-ttu-id="411db-322">FIND</span><span class="sxs-lookup"><span data-stu-id="411db-322">FIND</span></span>  
  
<span data-ttu-id="411db-323">LEFT</span><span class="sxs-lookup"><span data-stu-id="411db-323">LEFT</span></span>  
  
<span data-ttu-id="411db-324">LEN</span><span class="sxs-lookup"><span data-stu-id="411db-324">LEN</span></span>  
  
<span data-ttu-id="411db-325">MID</span><span class="sxs-lookup"><span data-stu-id="411db-325">MID</span></span>  
  
<span data-ttu-id="411db-326">REPLACE</span><span class="sxs-lookup"><span data-stu-id="411db-326">REPLACE</span></span>  
  
<span data-ttu-id="411db-327">REPT</span><span class="sxs-lookup"><span data-stu-id="411db-327">REPT</span></span>  
  
<span data-ttu-id="411db-328">RIGHT</span><span class="sxs-lookup"><span data-stu-id="411db-328">RIGHT</span></span>  
  
<span data-ttu-id="411db-329">SUBSTITUTE</span><span class="sxs-lookup"><span data-stu-id="411db-329">SUBSTITUTE</span></span>  
  
<span data-ttu-id="411db-330">TRIM</span><span class="sxs-lookup"><span data-stu-id="411db-330">TRIM</span></span>  
  
<span data-ttu-id="411db-331">**Statistische Funktionen**</span><span class="sxs-lookup"><span data-stu-id="411db-331">**Statistical functions**</span></span>  
  
<span data-ttu-id="411db-332">COUNT</span><span class="sxs-lookup"><span data-stu-id="411db-332">COUNT</span></span>  
  
<span data-ttu-id="411db-333">STDEV.P</span><span class="sxs-lookup"><span data-stu-id="411db-333">STDEV.P</span></span>  
  
<span data-ttu-id="411db-334">STDEV.S</span><span class="sxs-lookup"><span data-stu-id="411db-334">STDEV.S</span></span>  
  
<span data-ttu-id="411db-335">STDEVX.P</span><span class="sxs-lookup"><span data-stu-id="411db-335">STDEVX.P</span></span>  
  
<span data-ttu-id="411db-336">STDEVX.S</span><span class="sxs-lookup"><span data-stu-id="411db-336">STDEVX.S</span></span>  
  
<span data-ttu-id="411db-337">VAR.P</span><span class="sxs-lookup"><span data-stu-id="411db-337">VAR.P</span></span>  
  
<span data-ttu-id="411db-338">VAR.S</span><span class="sxs-lookup"><span data-stu-id="411db-338">VAR.S</span></span>  
  
<span data-ttu-id="411db-339">VARX.P</span><span class="sxs-lookup"><span data-stu-id="411db-339">VARX.P</span></span>  
  
<span data-ttu-id="411db-340">VARX.S</span><span class="sxs-lookup"><span data-stu-id="411db-340">VARX.S</span></span>  
  
<span data-ttu-id="411db-341">**Datums-/Uhrzeit-Funktionen**</span><span class="sxs-lookup"><span data-stu-id="411db-341">**Date/time functions**</span></span>  
  
<span data-ttu-id="411db-342">DATE</span><span class="sxs-lookup"><span data-stu-id="411db-342">DATE</span></span>  
  
<span data-ttu-id="411db-343">EDATE</span><span class="sxs-lookup"><span data-stu-id="411db-343">EDATE</span></span>  
  
<span data-ttu-id="411db-344">EOMONTH</span><span class="sxs-lookup"><span data-stu-id="411db-344">EOMONTH</span></span>  
  
<span data-ttu-id="411db-345">DATE</span><span class="sxs-lookup"><span data-stu-id="411db-345">DATE</span></span>  
  
<span data-ttu-id="411db-346">TIME</span><span class="sxs-lookup"><span data-stu-id="411db-346">TIME</span></span>  
  
<span data-ttu-id="411db-347">SECOND</span><span class="sxs-lookup"><span data-stu-id="411db-347">SECOND</span></span>  
  
<span data-ttu-id="411db-348">**Mathematische Funktionen und Zahlenfunktionen**</span><span class="sxs-lookup"><span data-stu-id="411db-348">**Math and number functions**</span></span>  
  
<span data-ttu-id="411db-349">CEILING</span><span class="sxs-lookup"><span data-stu-id="411db-349">CEILING</span></span>  
  
<span data-ttu-id="411db-350">LN</span><span class="sxs-lookup"><span data-stu-id="411db-350">LN</span></span>  
  
<span data-ttu-id="411db-351">PROTOKOLL</span><span class="sxs-lookup"><span data-stu-id="411db-351">LOG</span></span>  
  
<span data-ttu-id="411db-352">LOG10</span><span class="sxs-lookup"><span data-stu-id="411db-352">LOG10</span></span>  
  
<span data-ttu-id="411db-353">POWER</span><span class="sxs-lookup"><span data-stu-id="411db-353">POWER</span></span>  
  
<span data-ttu-id="411db-354">**DAX-Tabellen Abfragen**</span><span class="sxs-lookup"><span data-stu-id="411db-354">**DAX Table queries**</span></span>  
  
<span data-ttu-id="411db-355">Es gibt einige Einschränkungen, wenn Sie Formeln anhand eines DirectQuery-Modells auswerten, indem Sie DAX-Tabellenabfragen verwenden.</span><span class="sxs-lookup"><span data-stu-id="411db-355">There are some limitations when you evaluate formulas against a DirectQuery model by using DAX Table queries.</span></span> <span data-ttu-id="411db-356">DirectQuery unterstützt in einer ORDER BY-Klausel keinen zweimaligen Verweis auf dieselbe Spalte.</span><span class="sxs-lookup"><span data-stu-id="411db-356">DirectQuery does not support referring to the same column twice in an ORDER BY clause.</span></span> <span data-ttu-id="411db-357">Die entsprechende Transact-SQL-Anweisung kann nicht erstellt werden, und die Abfrage schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="411db-357">The equivalent Transact-SQL statement cannot be created and the query fails.</span></span>  
  
<span data-ttu-id="411db-358">Bei einem speicherinternen Modell hat das Wiederholen der ORDER BY-Klausel keine Auswirkung auf die Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="411db-358">In an in-memory model, repeating the ORDER by clause has no effect on the results.</span></span>  
  
## <a name="functions-not-supported-in-directquery-mode"></a><a name="bkmk_NotSupportedFunc"></a><span data-ttu-id="411db-359">Im directquery-Modus nicht unterstützte Funktionen</span><span class="sxs-lookup"><span data-stu-id="411db-359">Functions not supported in DirectQuery Mode</span></span>  
<span data-ttu-id="411db-360">Einige DAX-Funktionen werden nicht in Modellen unterstützt, die im DirectQuery-Modus bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="411db-360">Some DAX functions are not supported in models that are deployed in DirectQuery mode.</span></span> <span data-ttu-id="411db-361">Wird eine bestimmte Funktion nicht unterstützt, kann dies auf mindestens einen der folgenden Gründe zurückgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="411db-361">The reasons that a particular function is not supported can include any or a combination of these reasons:</span></span>  
  
-   <span data-ttu-id="411db-362">Die zugrunde liegende relationale Engine kann keine Berechnungen ausführen, die gleichwertig mit denen der xVelocity-Engine sind.</span><span class="sxs-lookup"><span data-stu-id="411db-362">The underlying relational engine cannot perform calculations equivalent to those performed by the xVelocity engine.</span></span>  
  
-   <span data-ttu-id="411db-363">Die Formel lässt sich nicht in einen entsprechenden SQL-Ausdruck umwandeln.</span><span class="sxs-lookup"><span data-stu-id="411db-363">The formula cannot be converted to en equivalent SQL expression.</span></span>  
  
-   <span data-ttu-id="411db-364">Die Leistung des umgewandelten Ausdrucks und die resultierenden Berechnungen sind nicht akzeptabel.</span><span class="sxs-lookup"><span data-stu-id="411db-364">The performance of the converted expression and the resulting calculations would be unacceptable.</span></span>  
  
<span data-ttu-id="411db-365">Die folgenden DAX-Funktionen können in DirectQuery-Modellen nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="411db-365">The following DAX functions cannot be used in DirectQuery models.</span></span>  
  
<span data-ttu-id="411db-366">**Pfadfunktionen**</span><span class="sxs-lookup"><span data-stu-id="411db-366">**Path functions**</span></span>  
  
<span data-ttu-id="411db-367">PATH</span><span class="sxs-lookup"><span data-stu-id="411db-367">PATH</span></span>  
  
<span data-ttu-id="411db-368">PATHCONTAINS</span><span class="sxs-lookup"><span data-stu-id="411db-368">PATHCONTAINS</span></span>  
  
<span data-ttu-id="411db-369">PATHITEM</span><span class="sxs-lookup"><span data-stu-id="411db-369">PATHITEM</span></span>  
  
<span data-ttu-id="411db-370">PATHITEMREVERSE</span><span class="sxs-lookup"><span data-stu-id="411db-370">PATHITEMREVERSE</span></span>  
  
<span data-ttu-id="411db-371">PATHLENGTH</span><span class="sxs-lookup"><span data-stu-id="411db-371">PATHLENGTH</span></span>  
  
<span data-ttu-id="411db-372">**Sonstige Funktionen**</span><span class="sxs-lookup"><span data-stu-id="411db-372">**Misc functions**</span></span>  
  
<span data-ttu-id="411db-373">COUNTBLANK</span><span class="sxs-lookup"><span data-stu-id="411db-373">COUNTBLANK</span></span>  
  
<span data-ttu-id="411db-374">FIXED</span><span class="sxs-lookup"><span data-stu-id="411db-374">FIXED</span></span>  
  
<span data-ttu-id="411db-375">FORMAT</span><span class="sxs-lookup"><span data-stu-id="411db-375">FORMAT</span></span>  
  
<span data-ttu-id="411db-376">RAND</span><span class="sxs-lookup"><span data-stu-id="411db-376">RAND</span></span>  
  
<span data-ttu-id="411db-377">RANDBETWEEN</span><span class="sxs-lookup"><span data-stu-id="411db-377">RANDBETWEEN</span></span>  
  
<span data-ttu-id="411db-378">**Zeitintelligenzfunktionen: Start- und Enddaten**</span><span class="sxs-lookup"><span data-stu-id="411db-378">**Time intelligence functions: Start and end dates**</span></span>  
  
<span data-ttu-id="411db-379">DATESQTD</span><span class="sxs-lookup"><span data-stu-id="411db-379">DATESQTD</span></span>  
  
<span data-ttu-id="411db-380">DATESYTD</span><span class="sxs-lookup"><span data-stu-id="411db-380">DATESYTD</span></span>  
  
<span data-ttu-id="411db-381">DATESMTD</span><span class="sxs-lookup"><span data-stu-id="411db-381">DATESMTD</span></span>  
  
<span data-ttu-id="411db-382">DATESQTD</span><span class="sxs-lookup"><span data-stu-id="411db-382">DATESQTD</span></span>  
  
<span data-ttu-id="411db-383">DATESINPERIOD</span><span class="sxs-lookup"><span data-stu-id="411db-383">DATESINPERIOD</span></span>  
  
<span data-ttu-id="411db-384">TOTALMTD</span><span class="sxs-lookup"><span data-stu-id="411db-384">TOTALMTD</span></span>  
  
<span data-ttu-id="411db-385">TOTALQTD</span><span class="sxs-lookup"><span data-stu-id="411db-385">TOTALQTD</span></span>  
  
<span data-ttu-id="411db-386">TOTALYTD</span><span class="sxs-lookup"><span data-stu-id="411db-386">TOTALYTD</span></span>  
  
<span data-ttu-id="411db-387">DATESINPERIOD</span><span class="sxs-lookup"><span data-stu-id="411db-387">DATESINPERIOD</span></span>  
  
<span data-ttu-id="411db-388">SAMEPERIODLASTYEAR</span><span class="sxs-lookup"><span data-stu-id="411db-388">SAMEPERIODLASTYEAR</span></span>  
  
<span data-ttu-id="411db-389">PARALLELPERIOD</span><span class="sxs-lookup"><span data-stu-id="411db-389">PARALLELPERIOD</span></span>  
  
<span data-ttu-id="411db-390">**Zeit Intelligenz Funktionen: Guthaben**</span><span class="sxs-lookup"><span data-stu-id="411db-390">**Time-intelligence functions: Balances**</span></span>  
  
<span data-ttu-id="411db-391">OPENINGBALANCEMONTH</span><span class="sxs-lookup"><span data-stu-id="411db-391">OPENINGBALANCEMONTH</span></span>  
  
<span data-ttu-id="411db-392">OPENINGBALANCEQUARTER</span><span class="sxs-lookup"><span data-stu-id="411db-392">OPENINGBALANCEQUARTER</span></span>  
  
<span data-ttu-id="411db-393">OPENINGBALANCEYEAR</span><span class="sxs-lookup"><span data-stu-id="411db-393">OPENINGBALANCEYEAR</span></span>  
  
<span data-ttu-id="411db-394">CLOSINGBALANCEMONTH</span><span class="sxs-lookup"><span data-stu-id="411db-394">CLOSINGBALANCEMONTH</span></span>  
  
<span data-ttu-id="411db-395">CLOSINGBALANCEQUARTER</span><span class="sxs-lookup"><span data-stu-id="411db-395">CLOSINGBALANCEQUARTER</span></span>  
  
<span data-ttu-id="411db-396">CLOSINGBALANCEYEAR</span><span class="sxs-lookup"><span data-stu-id="411db-396">CLOSINGBALANCEYEAR</span></span>  
  
<span data-ttu-id="411db-397">**Zeitintelligenzfunktionen: Vorherige und kommende Zeiträume**</span><span class="sxs-lookup"><span data-stu-id="411db-397">**Time intelligence functions: Previous and next periods**</span></span>  
  
<span data-ttu-id="411db-398">PREVIOUSDAY</span><span class="sxs-lookup"><span data-stu-id="411db-398">PREVIOUSDAY</span></span>  
  
<span data-ttu-id="411db-399">PREVIOUSMONTH</span><span class="sxs-lookup"><span data-stu-id="411db-399">PREVIOUSMONTH</span></span>  
  
<span data-ttu-id="411db-400">PREVIOUSQUARTER</span><span class="sxs-lookup"><span data-stu-id="411db-400">PREVIOUSQUARTER</span></span>  
  
<span data-ttu-id="411db-401">PREVIOUSYEAR</span><span class="sxs-lookup"><span data-stu-id="411db-401">PREVIOUSYEAR</span></span>  
  
<span data-ttu-id="411db-402">NEXTDAY</span><span class="sxs-lookup"><span data-stu-id="411db-402">NEXTDAY</span></span>  
  
<span data-ttu-id="411db-403">NEXTMONTH</span><span class="sxs-lookup"><span data-stu-id="411db-403">NEXTMONTH</span></span>  
  
<span data-ttu-id="411db-404">NEXTQUARTER</span><span class="sxs-lookup"><span data-stu-id="411db-404">NEXTQUARTER</span></span>  
  
<span data-ttu-id="411db-405">NEXTYEAR</span><span class="sxs-lookup"><span data-stu-id="411db-405">NEXTYEAR</span></span>  
  
<span data-ttu-id="411db-406">**Zeitintelligenzfunktionen: Zeiträume und Berechnungen im Verlauf von Zeiträumen**</span><span class="sxs-lookup"><span data-stu-id="411db-406">**Time intelligence functions: Periods and calculations over periods**</span></span>  
  
<span data-ttu-id="411db-407">STARTOFMONTH</span><span class="sxs-lookup"><span data-stu-id="411db-407">STARTOFMONTH</span></span>  
  
<span data-ttu-id="411db-408">STARTOFQUARTER</span><span class="sxs-lookup"><span data-stu-id="411db-408">STARTOFQUARTER</span></span>  
  
<span data-ttu-id="411db-409">STARTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="411db-409">STARTOFYEAR</span></span>  
  
<span data-ttu-id="411db-410">ENDOFMONTH</span><span class="sxs-lookup"><span data-stu-id="411db-410">ENDOFMONTH</span></span>  
  
<span data-ttu-id="411db-411">ENDOFQUARTER</span><span class="sxs-lookup"><span data-stu-id="411db-411">ENDOFQUARTER</span></span>  
  
<span data-ttu-id="411db-412">ENDOFYEAR</span><span class="sxs-lookup"><span data-stu-id="411db-412">ENDOFYEAR</span></span>  
  
<span data-ttu-id="411db-413">FIRSTDATE</span><span class="sxs-lookup"><span data-stu-id="411db-413">FIRSTDATE</span></span>  
  
<span data-ttu-id="411db-414">LASTDATE</span><span class="sxs-lookup"><span data-stu-id="411db-414">LASTDATE</span></span>  
  
<span data-ttu-id="411db-415">DATEADD</span><span class="sxs-lookup"><span data-stu-id="411db-415">DATEADD</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="411db-416">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="411db-416">See also</span></span>  
[<span data-ttu-id="411db-417">DirectQuery-Modus (SSAS – tabellarisch)</span><span class="sxs-lookup"><span data-stu-id="411db-417">DirectQuery Mode (SSAS Tabular)</span></span>](https://msdn.microsoft.com/45ad2965-05ec-4fb1-a164-d8060b562ea5)  
  

