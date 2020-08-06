---
title: Transformation für abgeleitete Spalten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.derivedcolumntrans.f1
helpviewer_keywords:
- multiple derived columns
- expressions [Integration Services], derived columns
- derived columns
- columns [Integration Services], derivations
- Derived Column transformation
ms.assetid: 8eba755e-8e48-4233-bd1e-09a46bf2692f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7bbdc46f2e67b1b859fcfa446c584373cfbeca0d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608768"
---
# <a name="derived-column-transformation"></a><span data-ttu-id="d4585-102">Transformation für abgeleitete Spalten</span><span class="sxs-lookup"><span data-stu-id="d4585-102">Derived Column Transformation</span></span>
  <span data-ttu-id="d4585-103">Mit der Transformation für abgeleitete Spalten werden neue Spaltenwerte erstellt, indem Ausdrücke auf Transformationseingabespalten angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="d4585-103">The Derived Column transformation creates new column values by applying expressions to transformation input columns.</span></span> <span data-ttu-id="d4585-104">Ein Ausdruck kann eine beliebige Kombination von Variablen, Funktionen, Operatoren und Spalten aus der Transformationseingabe enthalten.</span><span class="sxs-lookup"><span data-stu-id="d4585-104">An expression can contain any combination of variables, functions, operators, and columns from the transformation input.</span></span> <span data-ttu-id="d4585-105">Das Ergebnis kann als neue Spalte hinzugefügt oder in eine vorhandene Spalte als Ersatzwert eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="d4585-105">The result can be added as a new column or inserted into an existing column as a replacement value.</span></span> <span data-ttu-id="d4585-106">Die Transformation für abgeleitete Spalten kann mehrere abgeleitete Spalten definieren, und jede Variable oder Eingabespalte kann in mehreren Ausdrücken verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d4585-106">The Derived Column transformation can define multiple derived columns, and any variable or input columns can appear in multiple expressions.</span></span>  
  
 <span data-ttu-id="d4585-107">Mit dieser Transformation können die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="d4585-107">You can use this transformation to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="d4585-108">Verketten von Daten aus verschiedenen Spalten zu einer abgeleiteten Spalte.</span><span class="sxs-lookup"><span data-stu-id="d4585-108">Concatenate data from different columns into a derived column.</span></span> <span data-ttu-id="d4585-109">Beispielsweise können Sie mithilfe des Ausdrucks **Werte aus den Spalten** FirstName **und** LastName **zu einer einzelnen abgeleiteten Spalte mit dem Namen**FullName `FirstName + " " + LastName`verketten.</span><span class="sxs-lookup"><span data-stu-id="d4585-109">For example, you can combine values from the **FirstName** and **LastName** columns into a single derived column named **FullName**, by using the expression `FirstName + " " + LastName`.</span></span>  
  
-   <span data-ttu-id="d4585-110">Extrahieren von Zeichen aus Zeichenfolgendaten mithilfe von Funktionen, wie z. B. SUBSTRING, und anschließendes Speichern des Ergebnisses in einer abgeleiteten Spalte.</span><span class="sxs-lookup"><span data-stu-id="d4585-110">Extract characters from string data by using functions such as SUBSTRING, and then store the result in a derived column.</span></span> <span data-ttu-id="d4585-111">Beispielsweise können Sie mithilfe des Ausdrucks **die Initialen einer Person aus der** FirstName `SUBSTRING(FirstName,1,1)`-Spalte extrahieren.</span><span class="sxs-lookup"><span data-stu-id="d4585-111">For example, you can extract a person's initial from the **FirstName** column, by using the expression `SUBSTRING(FirstName,1,1)`.</span></span>  
  
-   <span data-ttu-id="d4585-112">Anwenden mathematischer Funktionen auf numerische Daten und Speichern des Ergebnisses in einer abgeleiteten Spalte.</span><span class="sxs-lookup"><span data-stu-id="d4585-112">Apply mathematical functions to numeric data and store the result in a derived column.</span></span> <span data-ttu-id="d4585-113">Beispielsweise können Sie mithilfe des Ausdrucks **die Länge und die Genauigkeit der numerischen**SalesTax `ROUND(SalesTax, 2)`-Spalte in eine Zahl mit zwei Dezimalstellen ändern.</span><span class="sxs-lookup"><span data-stu-id="d4585-113">For example, you can change the length and precision of a numeric column, **SalesTax**, to a number with two decimal places, by using the expression `ROUND(SalesTax, 2)`.</span></span>  
  
-   <span data-ttu-id="d4585-114">Erstellen von Ausdrücken, die Eingabespalten und Variablen vergleichen.</span><span class="sxs-lookup"><span data-stu-id="d4585-114">Create expressions that compare input columns and variables.</span></span> <span data-ttu-id="d4585-115">Beispielsweise können Sie mithilfe des Ausdrucks **die** Version **-Variable mit den Daten in der**ProductVersion **-Spalte vergleichen und in Abhängigkeit vom Ergebnis des Vergleichs den Wert von** Version **bzw.** ProductVersion `ProductVersion == @Version? ProductVersion : @Version`verwenden.</span><span class="sxs-lookup"><span data-stu-id="d4585-115">For example, you can compare the variable **Version** against the data in the column **ProductVersion**, and depending on the comparison result, use the value of either **Version** or **ProductVersion**, by using the expression `ProductVersion == @Version? ProductVersion : @Version`.</span></span>  
  
-   <span data-ttu-id="d4585-116">Extrahieren von Elementen eines datetime-Werts.</span><span class="sxs-lookup"><span data-stu-id="d4585-116">Extract parts of a datetime value.</span></span> <span data-ttu-id="d4585-117">Beispielsweise können Sie mithilfe des Ausdrucks `DATEPART("year",GETDATE())`und den Funktionen "GETDATE" und "DATEPART" das aktuelle Jahr extrahieren.</span><span class="sxs-lookup"><span data-stu-id="d4585-117">For example, you can use the GETDATE and DATEPART functions to extract the current year, by using the expression `DATEPART("year",GETDATE())`.</span></span>  
  
-   <span data-ttu-id="d4585-118">Konvertieren Sie Datumszeichenfolgen mithilfe eines Ausdrucks in ein bestimmtes Format.</span><span class="sxs-lookup"><span data-stu-id="d4585-118">Convert date strings to a specific format using an expression.</span></span>  
  
## <a name="configuration-of-the-derived-column-transformation"></a><span data-ttu-id="d4585-119">Konfiguration der Transformation für abgeleitete Spalten</span><span class="sxs-lookup"><span data-stu-id="d4585-119">Configuration of the Derived Column Transformation</span></span>  
 <span data-ttu-id="d4585-120">Es gibt folgende Möglichkeiten, um die Transformation für abgeleitete Spalten zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="d4585-120">You can configure the Derived column transformation in the following ways:</span></span>  
  
-   <span data-ttu-id="d4585-121">Geben Sie für jede Eingabespalte oder jede neue Spalte, die geändert wird, einen Ausdruck ein.</span><span class="sxs-lookup"><span data-stu-id="d4585-121">Provide an expression for each input column or new column that will be changed.</span></span> <span data-ttu-id="d4585-122">Weitere Informationen finden Sie unter [Integration Services-Ausdrücke &#40;SSIS&#41;](../../expressions/integration-services-ssis-expressions.md)ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="d4585-122">For more information, see [Integration Services &#40;SSIS&#41; Expressions](../../expressions/integration-services-ssis-expressions.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d4585-123">Falls ein Ausdruck auf eine Eingabespalte verweist, die von der Transformation für abgeleitete Spalten überschrieben wird, wird im Ausdruck nicht der abgeleitete Wert, sondern der ursprüngliche Wert verwendet.</span><span class="sxs-lookup"><span data-stu-id="d4585-123">If an expression references an input column that is overwritten by the Derived Column transformation, the expression uses the original value of the column, not the derived value.</span></span>  
  
-   <span data-ttu-id="d4585-124">Wenn Sie neuen Spalten Ergebnisse hinzufügen und der Datentyp `string` lautet, geben Sie eine Codepage an.</span><span class="sxs-lookup"><span data-stu-id="d4585-124">If adding results to new columns and the data type is `string`, specify a code page.</span></span> <span data-ttu-id="d4585-125">Weitere Informationen finden Sie unter [Comparing String Data](../comparing-string-data.md).</span><span class="sxs-lookup"><span data-stu-id="d4585-125">For more information, see [Comparing String Data](../comparing-string-data.md).</span></span>  
  
 <span data-ttu-id="d4585-126">Die Transformation für bedingtes Teilen schließt die benutzerdefinierte Eigenschaft FriendlyExpression ein.</span><span class="sxs-lookup"><span data-stu-id="d4585-126">The Derived Column transformation includes the FriendlyExpression custom property.</span></span> <span data-ttu-id="d4585-127">Diese Eigenschaft kann beim Laden des Pakets mithilfe eines Eigenschaftsausdrucks aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="d4585-127">This property can be updated by a property expression when the package is loaded.</span></span> <span data-ttu-id="d4585-128">Weitere Informationen finden Sie unter [Verwenden von Eigenschaftsausdrücken in Paketen](../../expressions/use-property-expressions-in-packages.md)und [Benutzerdefinierte Eigenschaften von Transformationen](transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="d4585-128">For more information, see [Use Property Expressions in Packages](../../expressions/use-property-expressions-in-packages.md), and [Transformation Custom Properties](transformation-custom-properties.md).</span></span>  
  
 <span data-ttu-id="d4585-129">Diese Transformation weist eine Eingabe, eine reguläre Ausgabe und eine Fehlerausgabe auf.</span><span class="sxs-lookup"><span data-stu-id="d4585-129">This transformation has one input, one regular output, and one error output.</span></span>  
  
 <span data-ttu-id="d4585-130">Sie können Eigenschaften mit dem [!INCLUDE[ssIS](../../../includes/ssis-md.md)] -Designer oder programmgesteuert festlegen.</span><span class="sxs-lookup"><span data-stu-id="d4585-130">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="d4585-131">Weitere Informationen zu den Eigenschaften, die Sie im Dialogfeld **Transformations-Editor für abgeleitete Spalte** festlegen können, finden Sie unter [Derived Column Transformation Editor](../../derived-column-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="d4585-131">For more information about the properties that you can set in the **Derived Column Transformation Editor** dialog box, see [Derived Column Transformation Editor](../../derived-column-transformation-editor.md).</span></span>  
  
 <span data-ttu-id="d4585-132">Das Dialogfeld **Erweiterter Editor** enthält die Eigenschaften, die programmgesteuert festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="d4585-132">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="d4585-133">Klicken Sie auf eines der folgenden Themen, um weitere Informationen zu den Eigenschaften zu erhalten, die Sie im Dialogfeld **Erweiterter Editor** oder programmgesteuert festlegen können:</span><span class="sxs-lookup"><span data-stu-id="d4585-133">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="d4585-134">Common Properties</span><span class="sxs-lookup"><span data-stu-id="d4585-134">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="d4585-135">Benutzerdefinierte Eigenschaften von Transformationen</span><span class="sxs-lookup"><span data-stu-id="d4585-135">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
 <span data-ttu-id="d4585-136">Klicken Sie auf eines der folgenden Themen, um weitere Informationen zum Festlegen von Eigenschaften anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="d4585-136">For more information about how to set properties, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="d4585-137">Festlegen der Eigenschaften einer Datenflusskomponente</span><span class="sxs-lookup"><span data-stu-id="d4585-137">Set the Properties of a Data Flow Component</span></span>](../set-the-properties-of-a-data-flow-component.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="d4585-138">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="d4585-138">Related Tasks</span></span>  
  
-   [<span data-ttu-id="d4585-139">Ableiten von Spaltenwerten mithilfe der Transformation für abgeleitete Spalten</span><span class="sxs-lookup"><span data-stu-id="d4585-139">Derive Column Values by Using the Derived Column Transformation</span></span>](derived-column-transformation.md)  
  
## <a name="related-content"></a><span data-ttu-id="d4585-140">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="d4585-140">Related Content</span></span>  
 <span data-ttu-id="d4585-141">Technischer Artikel, [SSIS Expression Examples](https://go.microsoft.com/fwlink/?LinkId=220761), auf social.technet.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d4585-141">Technical article, [SSIS Expression Examples](https://go.microsoft.com/fwlink/?LinkId=220761), on social.technet.microsoft.com</span></span>  
  
 <span data-ttu-id="d4585-142">Blog, Gewusst [wie: Aufteilen von Spaltendaten mithilfe von SSIS](https://microsoft-ssis.blogspot.com/2012/10/split-multi-value-column-into-multiple.html).</span><span class="sxs-lookup"><span data-stu-id="d4585-142">Blog, [How to Split Column Data using SSIS](https://microsoft-ssis.blogspot.com/2012/10/split-multi-value-column-into-multiple.html).</span></span>  
  
  
