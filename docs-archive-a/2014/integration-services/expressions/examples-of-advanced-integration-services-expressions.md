---
title: Beispiele für erweiterte SQL Server Integration Services-Ausdrücke | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- functions [Integration Services]
- operators [Integration Services]
- expressions [Integration Services], examples
- examples [Integration Services]
ms.assetid: c7794ba3-0de5-466b-ae8a-9ddd27360049
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fb1e8dc6f9bffd22c917414f80f6ba9f257b25b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617216"
---
# <a name="examples-of-advanced-integration-services-expressions"></a><span data-ttu-id="75041-102">Beispiele für erweiterte SQL Server Integration Services-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="75041-102">Examples of Advanced Integration Services Expressions</span></span>
  <span data-ttu-id="75041-103">In diesem Abschnitt werden Beispiele für erweiterte Ausdrücke bereitgestellt, die mehrere Operatoren und Funktionen kombinieren.</span><span class="sxs-lookup"><span data-stu-id="75041-103">This section provides examples of advanced expressions that combine multiple operators and functions.</span></span> <span data-ttu-id="75041-104">Falls ein Ausdruck in einer Rangfolgeneinschränkung oder der Transformation für bedingtes Teilen verwendet wird, muss er zu einem booleschen Wert ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="75041-104">If an expression is used in a precedence constraint or the Conditional Split transformation, it must evaluate to a Boolean.</span></span> <span data-ttu-id="75041-105">Diese Einschränkung gilt jedoch nicht für Ausdrücke, die in Eigenschaftsausdrücken, Variablen, der Transformation für abgeleitete Spalten oder im For-Schleifencontainer verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="75041-105">That restriction, however, does not apply to expressions used in property expressions, variables, the Derived Column transformation, or the For Loop container.</span></span>  
  
 <span data-ttu-id="75041-106">In den folgenden Beispiele werden die [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Datenbanken **AdventureWorks** und [!INCLUDE[ssSampleDBDWobject](../../includes/sssampledbdwobject-md.md)] verwendet.</span><span class="sxs-lookup"><span data-stu-id="75041-106">The following examples use the **AdventureWorks** and the [!INCLUDE[ssSampleDBDWobject](../../includes/sssampledbdwobject-md.md)][!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases.</span></span> <span data-ttu-id="75041-107">Jedes Beispiel identifiziert die verwendeten Tabellen.</span><span class="sxs-lookup"><span data-stu-id="75041-107">Each example identifies the tables it uses.</span></span>  
  
## <a name="boolean-expressions"></a><span data-ttu-id="75041-108">Boolesche Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="75041-108">Boolean Expressions</span></span>  
  
-   <span data-ttu-id="75041-109">In diesem Beispiel wird die **Product** -Tabelle verwendet.</span><span class="sxs-lookup"><span data-stu-id="75041-109">This example uses the **Product** table.</span></span> <span data-ttu-id="75041-110">Der Ausdruck wertet den Monatseintrag in der **SellStartDate** -Spalte aus und gibt TRUE zurück, wenn der Monat Juni oder ein späterer Monat ist.</span><span class="sxs-lookup"><span data-stu-id="75041-110">The expression evaluates the month entry in the **SellStartDate** column and returns TRUE if the month is June or later.</span></span>  
  
    ```  
    DATEPART("mm",SellStartDate) > 6  
    ```  
  
-   <span data-ttu-id="75041-111">In diesem Beispiel wird die **Product** -Tabelle verwendet.</span><span class="sxs-lookup"><span data-stu-id="75041-111">This example uses the **Product** table.</span></span> <span data-ttu-id="75041-112">Die Ausdrucksauswertung wertet das gerundete Ergebnis aus der Division der **ListPrice** -Spalte durch die **StandardCost** -Spalte aus und gibt TRUE zurück, wenn das Ergebnis größer als 1.5 ist.</span><span class="sxs-lookup"><span data-stu-id="75041-112">The expression evaluates the rounded result of dividing the **ListPrice** column by the **StandardCost** column, and returns TRUE if the result is greater than 1.5.</span></span>  
  
    ```  
    ROUND(ListPrice / StandardCost,2) > 1.50  
    ```  
  
-   <span data-ttu-id="75041-113">In diesem Beispiel wird die **Product** -Tabelle verwendet.</span><span class="sxs-lookup"><span data-stu-id="75041-113">This example uses the **Product** table.</span></span> <span data-ttu-id="75041-114">Der Ausdruck gibt TRUE zurück, falls alle drei Operationen zu TRUE ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="75041-114">The expression returns TRUE if all three operations evaluate to TRUE.</span></span> <span data-ttu-id="75041-115">Wenn die **Size** -Spalte und die **BikeSize** -Variable inkompatible Datentypen aufweisen, erfordert der Ausdruck eine explizite Umwandlung, wie im zweiten Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="75041-115">If the **Size** column and the **BikeSize** variable have incompatible data types, the expression requires an explicit cast as shown the second example.</span></span> <span data-ttu-id="75041-116">Die Umwandlung in den DT_WSTR-Datentyp schließt die Länge der Zeichenfolge ein.</span><span class="sxs-lookup"><span data-stu-id="75041-116">The cast to DT_WSTR includes the length of the string.</span></span>  
  
    ```  
    MakeFlag ==  TRUE && FinishedGoodsFlag == TRUE && Size != @BikeSize  
    MakeFlag ==  TRUE && FinishedGoodsFlag == TRUE  && Size != (DT_WSTR,10)@BikeSize  
    ```  
  
-   <span data-ttu-id="75041-117">In diesem Beispiel wird die **CurrencyRate** -Tabelle verwendet.</span><span class="sxs-lookup"><span data-stu-id="75041-117">This example uses the **CurrencyRate** table.</span></span> <span data-ttu-id="75041-118">Der Ausdruck vergleicht Werte in Tabellen und Variablen.</span><span class="sxs-lookup"><span data-stu-id="75041-118">The expression compares values in tables and variables.</span></span> <span data-ttu-id="75041-119">Er gibt TRUE zurück, falls Einträge in den Spalten **FromCurrencyCode** oder **ToCurrencyCode** mit Variablenwerten identisch sind und falls der Wert in **AverageRate** größer als der Wert in **EndOfDayRate**ist.</span><span class="sxs-lookup"><span data-stu-id="75041-119">It returns TRUE if entries in the **FromCurrencyCode** or **ToCurrencyCode** columns are equal to variable values and if the value in **AverageRate** is greater that the value in **EndOfDayRate**.</span></span>  
  
    ```  
    (FromCurrencyCode == @FromCur || ToCurrencyCode == @ToCur) && AverageRate > EndOfDayRate  
    ```  
  
-   <span data-ttu-id="75041-120">In diesem Beispiel wird die **Currency** -Tabelle verwendet.</span><span class="sxs-lookup"><span data-stu-id="75041-120">This example uses the **Currency** table.</span></span> <span data-ttu-id="75041-121">Der Ausdruck gibt TRUE zurück, falls das erste Zeichen in der **Name** -Spalte nicht a oder A ist.</span><span class="sxs-lookup"><span data-stu-id="75041-121">The expression returns TRUE if the first character in the **Name** column is not a or A.</span></span>  
  
    ```  
    SUBSTRING(UPPER(Name),1,1) != "A"  
    ```  
  
     <span data-ttu-id="75041-122">Der folgende Ausdruck stellt die gleichen Ergebnisse bereit, ist jedoch effizienter, weil nur ein Zeichen in Großbuchstaben konvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="75041-122">The following expression provides the same results, but it is more efficient because only one character is converted to uppercase.</span></span>  
  
    ```  
    UPPER(SUBSTRING(Name,1,1)) != "A"  
    ```  
  
## <a name="non-boolean-expressions"></a><span data-ttu-id="75041-123">Nicht boolesche Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="75041-123">Non-Boolean Expressions</span></span>  
 <span data-ttu-id="75041-124">Nicht boolesche Ausdrücke werden in der Transformation für abgeleitete Spalten, in Eigenschaftsausdrücken und im For-Schleifencontainer verwendet.</span><span class="sxs-lookup"><span data-stu-id="75041-124">Non-Boolean expressions are used in the Derived Column transformation, property expressions, and the For Loop container.</span></span>  
  
-   <span data-ttu-id="75041-125">In diesem Beispiel wird die **Contact** -Tabelle verwendet.</span><span class="sxs-lookup"><span data-stu-id="75041-125">This example uses the **Contact** table.</span></span> <span data-ttu-id="75041-126">Der Ausdruck entfernt führende und nachfolgende Leerzeichen aus den Spalten **FirstName**, **MiddleName**und **LastName** .</span><span class="sxs-lookup"><span data-stu-id="75041-126">The expression removes leading and trailing spaces from the **FirstName**, **MiddleName**, and **LastName** columns.</span></span> <span data-ttu-id="75041-127">Er extrahiert den ersten Buchstaben der **MiddleName** -Spalte, falls sie ungleich NULL ist, verkettet den Anfangsbuchstaben des zweiten Vornamens sowie die Werte in **FirstName** und **LastName**und fügt zwischen den Werten entsprechende Leerzeichen ein.</span><span class="sxs-lookup"><span data-stu-id="75041-127">It extracts the first letter of the **MiddleName** column if it is not null, concatenates the middle initial and the values in **FirstName** and **LastName**, and inserts appropriate spaces between values.</span></span>  
  
    ```  
    TRIM(FirstName) + " " + (!ISNULL(MiddleName) ? SUBSTRING(MiddleName,1,1) + " " : "") + TRIM(LastName)  
    ```  
  
-   <span data-ttu-id="75041-128">In diesem Beispiel wird die **Contact** -Tabelle verwendet.</span><span class="sxs-lookup"><span data-stu-id="75041-128">This example uses the **Contact** table.</span></span> <span data-ttu-id="75041-129">Der Ausdruck überprüft Einträge in der **Salutation** -Spalte.</span><span class="sxs-lookup"><span data-stu-id="75041-129">The expression validates entries in the **Salutation** column.</span></span> <span data-ttu-id="75041-130">Er gibt einen **Salutation** -Eintrag oder eine leere Zeichenfolge zurück.</span><span class="sxs-lookup"><span data-stu-id="75041-130">It returns a **Salutation** entry or an empty string.</span></span>  
  
    ```  
    (Salutation == "Sr." || Salutation == "Ms." || Salutation == "Sra." || Salutation == "Mr.") ? Salutation : ""  
    ```  
  
-   <span data-ttu-id="75041-131">In diesem Beispiel wird die **Product** -Tabelle verwendet.</span><span class="sxs-lookup"><span data-stu-id="75041-131">This example uses the **Product** table.</span></span> <span data-ttu-id="75041-132">Der Ausdruck konvertiert das erste Zeichen in der **Color** -Spalte in Großbuchstaben und konvertiert die restlichen Zeichen in Kleinbuchstaben.</span><span class="sxs-lookup"><span data-stu-id="75041-132">The expression converts the first character in the **Color** column to uppercase and converts remaining characters to lowercase.</span></span>  
  
    ```  
    UPPER(SUBSTRING(Color,1,1)) + LOWER(SUBSTRING(Color,2,15))  
    ```  
  
-   <span data-ttu-id="75041-133">In diesem Beispiel wird die **Product** -Tabelle verwendet.</span><span class="sxs-lookup"><span data-stu-id="75041-133">This example uses the **Product** table.</span></span> <span data-ttu-id="75041-134">Der Ausdruck berechnet, seit wie vielen Monaten ein Produkt verkauft wird und gibt die Zeichenfolge "Unknown" zurück, falls die **SellStartDate** -Spalte oder die **SellEndDate** -Spalte NULL enthält.</span><span class="sxs-lookup"><span data-stu-id="75041-134">The expression calculates the number of months a product has been sold and returns the string "Unknown" if either the **SellStartDate** or the **SellEndDate** column contains NULL.</span></span>  
  
    ```  
    !(ISNULL(SellStartDate)) && !(ISNULL(SellEndDate)) ? (DT_WSTR,2)DATEDIFF("mm",SellStartDate,SellEndDate) : "Unknown"  
    ```  
  
-   <span data-ttu-id="75041-135">In diesem Beispiel wird die **Product** -Tabelle verwendet.</span><span class="sxs-lookup"><span data-stu-id="75041-135">This example uses the **Product** table.</span></span> <span data-ttu-id="75041-136">Der Ausdruck berechnet den Aufschlag für die **StandardCost** -Spalte und rundet das Ergebnis auf eine Genauigkeit von zwei Dezimalstellen auf.</span><span class="sxs-lookup"><span data-stu-id="75041-136">The expression calculates the markup on the **StandardCost** column and rounds the result to a precision of two.</span></span> <span data-ttu-id="75041-137">Das Ergebnis wird als Prozentsatz angezeigt.</span><span class="sxs-lookup"><span data-stu-id="75041-137">The result is presented as a percentage.</span></span>  
  
    ```  
    ROUND(ListPrice / StandardCost,2) * 100  
    ```  
  
## <a name="related-tasks"></a><span data-ttu-id="75041-138">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="75041-138">Related Tasks</span></span>  
 [<span data-ttu-id="75041-139">Verwenden eines Ausdrucks in einer Datenflusskomponente</span><span class="sxs-lookup"><span data-stu-id="75041-139">Use an Expression in a Data Flow Component</span></span>](../use-an-expression-in-a-data-flow-component.md)  
  
## <a name="related-content"></a><span data-ttu-id="75041-140">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="75041-140">Related Content</span></span>  
 <span data-ttu-id="75041-141">Technischer Artikel, [SSIS Expression Cheat Sheet](https://pragmaticworks.com/Resources/Cheat-Sheets/SSIS-Expression-Cheat-Sheet), auf pragmaticworks.com</span><span class="sxs-lookup"><span data-stu-id="75041-141">Technical article, [SSIS Expression Cheat Sheet](https://pragmaticworks.com/Resources/Cheat-Sheets/SSIS-Expression-Cheat-Sheet), on pragmaticworks.com</span></span>  
  
  
