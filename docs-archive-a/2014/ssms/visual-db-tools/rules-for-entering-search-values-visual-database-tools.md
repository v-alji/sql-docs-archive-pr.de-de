---
title: Regeln für das Eingeben von Suchwerten (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- time [SQL Server], searches
- date searches
- dates [SQL Server], searches
- embedding apostrophes [SQL Server]
- logical value searches [SQL Server]
- case-sensitive search matches
- search criteria [SQL Server], rules
- text value searches [SQL Server]
- numeric value searches [SQL Server]
ms.assetid: 3c8134b7-83f4-41b4-99c8-e3949a685ff5
author: stevestein
ms.author: sstein
ms.openlocfilehash: 907bcac93863bc5660993e910b37e25e25a129b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609000"
---
# <a name="rules-for-entering-search-values-visual-database-tools"></a><span data-ttu-id="d6637-102">Regeln für das Eingeben von Suchwerten (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="d6637-102">Rules for Entering Search Values (Visual Database Tools)</span></span>
  <span data-ttu-id="d6637-103">In diesem Thema werden die Konventionen erläutert, die beim Eingeben der folgenden Arten von Literalwerten für eine Suchbedingung beachtet werden müssen:</span><span class="sxs-lookup"><span data-stu-id="d6637-103">This topic discusses the conventions you must use when entering the following types of literal values for a search condition:</span></span>  
  
-   <span data-ttu-id="d6637-104">Textwerte</span><span class="sxs-lookup"><span data-stu-id="d6637-104">Text values</span></span>  
  
-   <span data-ttu-id="d6637-105">Numerische Werte</span><span class="sxs-lookup"><span data-stu-id="d6637-105">Numeric values</span></span>  
  
-   <span data-ttu-id="d6637-106">Datumsangaben</span><span class="sxs-lookup"><span data-stu-id="d6637-106">Dates</span></span>  
  
-   <span data-ttu-id="d6637-107">Logische Werte</span><span class="sxs-lookup"><span data-stu-id="d6637-107">Logical values</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d6637-108">Die Informationen in diesem Thema leiten sich aus den Regeln für Standard-SQL-92 ab.</span><span class="sxs-lookup"><span data-stu-id="d6637-108">The information in this topic is derived from the rules for standard SQL-92.</span></span> <span data-ttu-id="d6637-109">Datenbanken können SQL jedoch auf unterschiedliche Art implementieren.</span><span class="sxs-lookup"><span data-stu-id="d6637-109">However, each database can implement SQL in its own way.</span></span> <span data-ttu-id="d6637-110">Die hier angezeigten Richtlinien sind daher nicht in jedem Fall gültig.</span><span class="sxs-lookup"><span data-stu-id="d6637-110">Therefore, the guidelines provided here might not apply in every case.</span></span> <span data-ttu-id="d6637-111">Informationen zum Eingeben von Suchwerten in einer bestimmten Datenbank erhalten Sie in der Dokumentation zur verwendeten Datenbank.</span><span class="sxs-lookup"><span data-stu-id="d6637-111">If you have questions about how to enter search values for a particular database, refer to the documentation for the database that you are using.</span></span>  
  
## <a name="searching-on-text-values"></a><span data-ttu-id="d6637-112">Suchen von Textwerten</span><span class="sxs-lookup"><span data-stu-id="d6637-112">Searching on Text Values</span></span>  
 <span data-ttu-id="d6637-113">Die folgenden Richtlinien gelten für die Eingabe von Textwerten in Suchbedingungen:</span><span class="sxs-lookup"><span data-stu-id="d6637-113">The following guidelines apply when you enter text values in search conditions:</span></span>  
  
-   <span data-ttu-id="d6637-114">**Anführungszeichen** Schließen Sie Textwerte in einfache Anführungszeichen ein, wie in diesem Beispiel für einen Nachnamen:</span><span class="sxs-lookup"><span data-stu-id="d6637-114">**Quotation marks** Enclose text values in single quotation marks, as in this example for a last name:</span></span>  
  
    ```  
    'Smith'  
    ```  
  
     <span data-ttu-id="d6637-115">Wenn Sie eine Suchbedingung im [Kriterienbereich](visual-database-tools.md)eingeben, müssen Sie nur den Textwert eingeben, woraufhin der Abfrage- und Sicht-Designer diesen automatisch in einfache Anführungszeichen einschließt.</span><span class="sxs-lookup"><span data-stu-id="d6637-115">If you are entering a search condition in the [Criteria Pane](visual-database-tools.md), you can simply type the text value and the Query and View Designer will automatically put single quotation marks around it.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d6637-116">In einigen Datenbanken werden Begriffe in einfachen Anführungszeichen als Literalwerte interpretiert, wohingegen Begriffe in doppelten Anführungszeichen als Datenbankobjekte wie Spalten- oder Tabellenverweise interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="d6637-116">In some databases, terms in single quotation marks are interpreted as literal values, whereas terms in double quotation marks are interpreted as database objects such as column or table references.</span></span> <span data-ttu-id="d6637-117">Daher ist es möglich, dass der Abfrage- und Sicht-Designer die Begriffe in doppelten Anführungszeichen zwar akzeptiert, sie jedoch nicht wie erwartet interpretiert.</span><span class="sxs-lookup"><span data-stu-id="d6637-117">Therefore, even though the Query and View Designer can accept terms in double quotation marks, it might interpret them differently than you expect.</span></span>  
  
-   <span data-ttu-id="d6637-118">**Einbetten von Apostrophen** Wenn die gesuchten Daten ein einzelnes Anführungszeichen (ein Apostroph) enthalten, können Sie mit zwei einzelnen Anführungszeichen kennzeichnen, dass dieses einzelne Anführungszeichen als Literalwert und nicht als Trennzeichen verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d6637-118">**Embedding apostrophes** If the data you are searching for contains a single quotation mark (an apostrophe), you can enter two single quotation marks to indicate that you mean the single quotation mark as a literal value and not a delimiter.</span></span> <span data-ttu-id="d6637-119">Mit der folgenden Bedingung suchen Sie z. B. nach dem Wert "Swann's Way":</span><span class="sxs-lookup"><span data-stu-id="d6637-119">For example, the following condition searches for the value "Swann's Way:"</span></span>  
  
    ```  
    ='Swann''s Way'  
    ```  
  
-   <span data-ttu-id="d6637-120">**Längenbegrenzung** Beachten Sie bei der Eingabe langer Zeichenfolgen die zulässige Höchstlänge für die SQL-Anweisung bei der verwendeten Datenbank.</span><span class="sxs-lookup"><span data-stu-id="d6637-120">**Length limits** Do not exceed the maximum length of the SQL statement for your database when entering long strings.</span></span>  
  
-   <span data-ttu-id="d6637-121">**Groß- und Kleinschreibung** Beachten Sie die Regeln für die Groß- und Kleinschreibung der verwendeten Datenbank.</span><span class="sxs-lookup"><span data-stu-id="d6637-121">**Case sensitivity** Follow the case sensitivity rules for the database you are using.</span></span> <span data-ttu-id="d6637-122">Die verwendete Datenbank bestimmt, ob bei Textsuchen die Groß- und Kleinschreibung beachtet werden muss.</span><span class="sxs-lookup"><span data-stu-id="d6637-122">The database you are using determines whether text searches are case sensitive.</span></span> <span data-ttu-id="d6637-123">In einigen Datenbanken muss beim Operator "=" die Groß- und Kleinschreibung beachtet werden, während in anderen auch Kombinationen von groß und klein geschriebenen Zeichen zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="d6637-123">For example, some databases interpret the operator "=" to mean an exact case-sensitive match, but others will allow matches on any combination of uppercase and lowercase characters.</span></span>  
  
     <span data-ttu-id="d6637-124">Wenn Sie nicht wissen, ob in der verwendeten Datenbank die Groß- und Kleinschreibung beachtet wird, können Sie mit den UPPER- oder LOWER-Funktionen in der Suchbedingung, wie im folgenden Beispiel gezeigt, die Großschreibung der Suchdaten in Kleinschreibung konvertieren und umgekehrt:</span><span class="sxs-lookup"><span data-stu-id="d6637-124">If you are unsure about whether the database uses a case-sensitive search, you can use the UPPER or LOWER functions in the search condition to convert the case of the search data, as illustrated in the following example:</span></span>  
  
    ```  
    WHERE UPPER(lname) = 'SMITH'  
    ```  
  
## <a name="searching-on-numeric-values"></a><span data-ttu-id="d6637-125">Suchen von numerischen Werten</span><span class="sxs-lookup"><span data-stu-id="d6637-125">Searching on Numeric Values</span></span>  
 <span data-ttu-id="d6637-126">Die folgenden Richtlinien gelten für die Eingabe von numerischen Werten in Suchbedingungen:</span><span class="sxs-lookup"><span data-stu-id="d6637-126">The following guidelines apply when you enter numeric values in search conditions:</span></span>  
  
-   <span data-ttu-id="d6637-127">**Anführungszeichen** Zahlen dürfen nicht in Anführungszeichen eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="d6637-127">**Quotation marks** Do not enclose numbers in quotation marks.</span></span>  
  
-   <span data-ttu-id="d6637-128">**Nicht numerische Zeichen** Fügen Sie keine nicht numerischen Zeichen außer dem dezimalen Trennzeichen (wie in der Windows-Systemsteuerung im Dialogfeld **Ländereinstellungen** definiert) und dem negativen Vorzeichen (-) ein.</span><span class="sxs-lookup"><span data-stu-id="d6637-128">**Non-numeric characters** Do not include non-numeric characters except the decimal separator (as defined in the **Regional Settings** dialog box of Windows Control Panel) and negative sign (-).</span></span> <span data-ttu-id="d6637-129">Fügen Sie keine Zeichen für das Gruppieren von Ziffern (z. B. einen Punkt zwischen Tausendergruppen) oder Währungssymbole ein.</span><span class="sxs-lookup"><span data-stu-id="d6637-129">Do not include digit grouping symbols (such as a comma between thousands) or currency symbols.</span></span>  
  
-   <span data-ttu-id="d6637-130">**Dezimalzeichen** Wenn Sie ganze Zahlen eingeben, können Sie ein Dezimalzeichen einfügen, um zu kennzeichnen, ob es sich bei diesem Wert um eine ganze oder um eine reelle Zahl handelt.</span><span class="sxs-lookup"><span data-stu-id="d6637-130">**Decimal marks** If you are entering whole numbers, you can include a decimal mark, whether the value you are searching for is an integer or a real number.</span></span>  
  
-   <span data-ttu-id="d6637-131">**Wissenschaftliche Schreibweise** Sie können sehr große oder kleine Zahlen wie im folgenden Beispiel mit der wissenschaftlichen Schreibweise eingeben:</span><span class="sxs-lookup"><span data-stu-id="d6637-131">**Scientific notation** You can enter very large or very small numbers using scientific notation, as in this example:</span></span>  
  
    ```  
    > 1.23456e-9  
    ```  
  
## <a name="searching-on-dates"></a><span data-ttu-id="d6637-132">Suchen von Datumsangaben</span><span class="sxs-lookup"><span data-stu-id="d6637-132">Searching on Dates</span></span>  
 <span data-ttu-id="d6637-133">Das für die Eingabe von Daten zu verwendende Format hängt von der Datenbank und dem Bereich des Abfrage- und Sicht-Designers ab, in dem Sie diese eingeben.</span><span class="sxs-lookup"><span data-stu-id="d6637-133">The format you use to enter dates depends on the database you are using and in what pane of the Query and View Designer you are entering the date.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d6637-134">Falls Sie nicht wissen, welches Format Ihre Datenquelle verwendet, geben Sie in der Filterzeile des Kriterienbereichs ein Datum in einem Ihnen vertrauten Format ein.</span><span class="sxs-lookup"><span data-stu-id="d6637-134">If you don't know which format your data source uses, type a date into the filter column of the Criteria pane in any format familiar to you.</span></span> <span data-ttu-id="d6637-135">Der Designer solche Einträge in den meisten Fällen in das geeignete Format konvertieren.</span><span class="sxs-lookup"><span data-stu-id="d6637-135">The designer will convert most of such entries into the appropriate format.</span></span>  
  
 <span data-ttu-id="d6637-136">Im Abfrage- und Sicht-Designer können die folgenden Datumsformate verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="d6637-136">The Query and View Designer can work with the following date formats:</span></span>  
  
-   <span data-ttu-id="d6637-137">**Gebietsschemaspezifisch** Das für Datumsangaben in den Einstellungen im Windows-Dialogfeld **Region** festgelegte Format.</span><span class="sxs-lookup"><span data-stu-id="d6637-137">**Locale-specific** The format specified for dates in the **Windows Regional Settings Properties** dialog box.</span></span>  
  
-   <span data-ttu-id="d6637-138">**Datenbankspezifisch** Jedes von der Datenbank akzeptierte Format.</span><span class="sxs-lookup"><span data-stu-id="d6637-138">**Database-specific** Any format understood by the database.</span></span>  
  
-   <span data-ttu-id="d6637-139">**ANSI-Standarddatum** Ein Format, bei dem wie im folgenden Beispiel geschweifte Klammern, die Markierung „d“ zum Kennzeichnen des Datums und eine Datumszeichenfolge verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="d6637-139">**ANSI standard date** A format that uses braces, the marker 'd' to designate the date, and a date string, as in the following example:</span></span>  
  
    ```  
    { d '1990-12-31' }  
    ```  
  
-   <span data-ttu-id="d6637-140">**ANSI-Standarddatum/-uhrzeit** Dies entspricht dem ANSI-Standarddatum, wobei aber „ts“ anstelle von „d“ verwendet wird und Stunden, Minuten und Sekunden zum Datum hinzugefügt werden (im 24-Stundenformat), wie im folgenden Beispiel für den 31. Dezember 1990 gezeigt:</span><span class="sxs-lookup"><span data-stu-id="d6637-140">**ANSI standard datetime** Similar to ANSI-standard date, but uses 'ts' instead of 'd' and adds hours, minutes, and seconds to the date (using a 24-hour clock), as in this example for December 31, 1990:</span></span>  
  
    ```  
    { ts '1990-12-31 00:00:00' }  
    ```  
  
     <span data-ttu-id="d6637-141">Im Allgemeinen wird das ANSI-Standarddatenformat bei Datenbanken verwendet, in denen Daten mit einem True-Date-Datentyp dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="d6637-141">In general, the ANSI standard date format is used with databases that represent dates using a true date data type.</span></span> <span data-ttu-id="d6637-142">Im Gegensatz dazu wird das Datetime-Format bei Datenbanken verwendet, die den Datetime-Datentyp unterstützen.</span><span class="sxs-lookup"><span data-stu-id="d6637-142">In contrast, the datetime format is used with databases that support a datetime data type.</span></span>  
  
 <span data-ttu-id="d6637-143">In der folgenden Tabelle werden die Datumsformate aufgeführt, die Sie in den verschiedenen Bereichen des Abfrage- und Sicht-Designers verwenden können.</span><span class="sxs-lookup"><span data-stu-id="d6637-143">The following table summarizes the date format that you can use in different panes of the Query and View Designer.</span></span>  
  
|<span data-ttu-id="d6637-144">**Bereich**</span><span class="sxs-lookup"><span data-stu-id="d6637-144">**Pane**</span></span>|<span data-ttu-id="d6637-145">**Datumsformat**</span><span class="sxs-lookup"><span data-stu-id="d6637-145">**Date format**</span></span>|  
|--------------|---------------------|  
|<span data-ttu-id="d6637-146">Kriterien</span><span class="sxs-lookup"><span data-stu-id="d6637-146">Criteria</span></span>|<span data-ttu-id="d6637-147">Gebietsschemaspezifisch? Datenbankspezifisch? ANSI-Standard</span><span class="sxs-lookup"><span data-stu-id="d6637-147">Locale-specific Database-specific ANSI standard</span></span><br /><br /> <span data-ttu-id="d6637-148">Die im [Kriterienbereich](visual-database-tools.md) eingegebenen Datumsangaben werden im SQL-Bereich in ein datenbankkompatibles Format konvertiert.</span><span class="sxs-lookup"><span data-stu-id="d6637-148">Dates entered in the [Criteria Pane](visual-database-tools.md) are converted to a database-compatible format in the SQL pane.</span></span>|  
|<span data-ttu-id="d6637-149">SQL</span><span class="sxs-lookup"><span data-stu-id="d6637-149">SQL</span></span>|<span data-ttu-id="d6637-150">Datenbankspezifisch? ANSI-Standard</span><span class="sxs-lookup"><span data-stu-id="d6637-150">Database-specific ANSI standard</span></span>|  
|<span data-ttu-id="d6637-151">Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="d6637-151">Results</span></span>|<span data-ttu-id="d6637-152">Gebietsschemaspezifisch</span><span class="sxs-lookup"><span data-stu-id="d6637-152">Locale-specific</span></span>|  
  
## <a name="searching-on-logical-values"></a><span data-ttu-id="d6637-153">Suchen von logischen Werten</span><span class="sxs-lookup"><span data-stu-id="d6637-153">Searching on Logical Values</span></span>  
 <span data-ttu-id="d6637-154">Das Format logischer Daten ist in den einzelnen Datenbanken unterschiedlich.</span><span class="sxs-lookup"><span data-stu-id="d6637-154">The format of logical data varies from database to database.</span></span> <span data-ttu-id="d6637-155">In vielen Fällen wird der Wert False als Null (0) gespeichert.</span><span class="sxs-lookup"><span data-stu-id="d6637-155">Very frequently, a value of False is stored as zero (0).</span></span> <span data-ttu-id="d6637-156">Der Wert True wird häufig als 1 und in bestimmten Fällen auch als -1 gespeichert</span><span class="sxs-lookup"><span data-stu-id="d6637-156">A value of True is most frequently stored as 1 and occasionally as -1.</span></span> <span data-ttu-id="d6637-157">Die folgenden Richtlinien gelten für die Eingabe von logischen Werten in Suchbedingungen:</span><span class="sxs-lookup"><span data-stu-id="d6637-157">The following guidelines apply when you enter logical values in search conditions:</span></span>  
  
-   <span data-ttu-id="d6637-158">Verwenden Sie zum Suchen des Werts False wie im folgenden Beispiel dargestellt eine 0:</span><span class="sxs-lookup"><span data-stu-id="d6637-158">To search for a value of False, use a zero, as in the following example:</span></span>  
  
    ```  
    SELECT * FROM authors  
    WHERE contract = 0  
    ```  
  
-   <span data-ttu-id="d6637-159">Wenn Sie nicht genau wissen, welches Format Sie für die Suche eines Werts True verwenden sollen, versuchen Sie es wie im folgenden Beispiel mit dem Wert 1:</span><span class="sxs-lookup"><span data-stu-id="d6637-159">If you are not sure what format to use when searching for a True value, try using 1, as in the following example:</span></span>  
  
    ```  
    SELECT * FROM authors  
    WHERE contract = 1  
    ```  
  
-   <span data-ttu-id="d6637-160">Sie können den Gültigkeitsbereich der Suche erweitern, indem Sie nach allen Werten suchen, die nicht 0 sind, wie im folgenden Beispiel dargestellt:</span><span class="sxs-lookup"><span data-stu-id="d6637-160">Alternatively, you can broaden the scope of the search by searching for any non-zero value, as in the following example:</span></span>  
  
    ```  
    SELECT * FROM authors  
    WHERE contract <> 0  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="d6637-161">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d6637-161">See Also</span></span>  
 [<span data-ttu-id="d6637-162">Angeben von Suchkriterien &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="d6637-162">Specify Search Criteria &#40;Visual Database Tools&#41;</span></span>](specify-search-criteria-visual-database-tools.md)  
  
  
