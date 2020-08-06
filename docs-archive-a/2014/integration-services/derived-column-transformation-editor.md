---
title: Transformations-Editor für abgeleitete Spalte | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.derivedcolumntransformation.f1
helpviewer_keywords:
- Derived Column Transformation Editor
ms.assetid: ff73923e-d245-43d8-bf24-af3bdc942e51
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 41a0f0dcd253473f78f2f38426b5fbd3d2ac2812
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621608"
---
# <a name="derived-column-transformation-editor"></a><span data-ttu-id="2cc0f-102">Transformations-Editor für abgeleitete Spalte</span><span class="sxs-lookup"><span data-stu-id="2cc0f-102">Derived Column Transformation Editor</span></span>
  <span data-ttu-id="2cc0f-103">Mithilfe des Dialogfelds **Transformations-Editor für abgeleitete Spalte** können Sie Ausdrücke erstellen, die neue Spalten oder Ersatzspalten auffüllen.</span><span class="sxs-lookup"><span data-stu-id="2cc0f-103">Use the **Derived Column Transformation Editor** dialog box to create expressions that populate new or replacement columns.</span></span>  
  
 <span data-ttu-id="2cc0f-104">Weitere Informationen zur Transformation für abgeleitete Spalten finden Sie unter [Derived Column Transformation](data-flow/transformations/derived-column-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="2cc0f-104">To learn more about the Derived Column transformation, see [Derived Column Transformation](data-flow/transformations/derived-column-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="2cc0f-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="2cc0f-105">Options</span></span>  
 <span data-ttu-id="2cc0f-106">**Variablen und Spalten**</span><span class="sxs-lookup"><span data-stu-id="2cc0f-106">**Variables and Columns**</span></span>  
 <span data-ttu-id="2cc0f-107">Erstellen Sie einen Ausdruck, der eine Variable oder eine Eingabespalte verwendet, indem Sie die Variable oder Spalte aus der Liste der verfügbaren Variablen und Spalten in eine vorhandene Tabellenzeile im unteren Bereich oder in eine neue Zeile am Ende der Liste ziehen.</span><span class="sxs-lookup"><span data-stu-id="2cc0f-107">Build an expression that uses a variable or an input column by dragging the variable or column from the list of available variables and columns to an existing table row in the pane below, or to a new row at the bottom of the list.</span></span>  
  
 <span data-ttu-id="2cc0f-108">**Funktionen und Operatoren**</span><span class="sxs-lookup"><span data-stu-id="2cc0f-108">**Functions and Operators**</span></span>  
 <span data-ttu-id="2cc0f-109">Erstellen Sie einen Ausdruck, der eine Funktion oder einen Operator zum Bewerten der Eingabedaten und zum Weiterleiten der Ausgabedaten verwendet, indem Sie die Funktionen und Operatoren aus der Liste in den unteren Bereich ziehen.</span><span class="sxs-lookup"><span data-stu-id="2cc0f-109">Build an expression that uses a function or an operator to evaluate input data and direct output data by dragging functions and operators from the list to the pane below.</span></span>  
  
 <span data-ttu-id="2cc0f-110">**Name der abgeleiteten Spalte**</span><span class="sxs-lookup"><span data-stu-id="2cc0f-110">**Derived Column Name**</span></span>  
 <span data-ttu-id="2cc0f-111">Geben Sie einen Namen für die abgeleitete Spalte an.</span><span class="sxs-lookup"><span data-stu-id="2cc0f-111">Provide a derived column name.</span></span> <span data-ttu-id="2cc0f-112">Standardwert ist eine nummerierte Liste mit abgeleiteten Spalten; Sie können jedoch einen eindeutigen, beschreibenden Namen auswählen.</span><span class="sxs-lookup"><span data-stu-id="2cc0f-112">The default is a numbered list of derived columns; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="2cc0f-113">**Abgeleitete Spalte**</span><span class="sxs-lookup"><span data-stu-id="2cc0f-113">**Derived Column**</span></span>  
 <span data-ttu-id="2cc0f-114">Wählen Sie eine abgeleitete Spalte aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="2cc0f-114">Select a derived column from the list.</span></span> <span data-ttu-id="2cc0f-115">Wählen Sie aus, ob die abgeleitete Spalte als neue Ausgabespalte hinzugefügt wird oder die Daten in einer vorhandenen Spalte ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="2cc0f-115">Choose whether to add the derived column as a new output column, or to replace the data in an existing column.</span></span>  
  
 <span data-ttu-id="2cc0f-116">**Ausdruck**</span><span class="sxs-lookup"><span data-stu-id="2cc0f-116">**Expression**</span></span>  
 <span data-ttu-id="2cc0f-117">Geben Sie einen Ausdruck ein, oder erstellen Sie einen, indem Sie aus der vorherigen Liste der verfügbaren Spalten, Variablen, Funktionen und Operatoren die entsprechenden Teile ziehen.</span><span class="sxs-lookup"><span data-stu-id="2cc0f-117">Type an expression or build one by dragging from the previous list of available columns, variables, functions, and operators.</span></span>  
  
 <span data-ttu-id="2cc0f-118">Der Wert dieser Eigenschaft kann mithilfe eines Eigenschaftsausdrucks angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="2cc0f-118">The value of this property can be specified by using a property expression.</span></span>  
  
 <span data-ttu-id="2cc0f-119">**Verwandte Themen:**[Integration Services-Ausdrücke &#40;SSIS&#41;](expressions/integration-services-ssis-expressions.md), [Operatoren &#40;SSIS-Ausdruck&#41;](expressions/operators-ssis-expression.md) und [Funktionen &#40;SSIS-Ausdruck&#41;](expressions/functions-ssis-expression.md)</span><span class="sxs-lookup"><span data-stu-id="2cc0f-119">**Related topics**: [Integration Services &#40;SSIS&#41; Expressions](expressions/integration-services-ssis-expressions.md), [Operators &#40;SSIS Expression&#41;](expressions/operators-ssis-expression.md), and [Functions &#40;SSIS Expression&#41;](expressions/functions-ssis-expression.md)</span></span>  
  
 <span data-ttu-id="2cc0f-120">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="2cc0f-120">**Data Type**</span></span>  
 <span data-ttu-id="2cc0f-121">Beim Hinzufügen von Daten zu einer neuen Spalte wertet das Dialogfeld **Transformations-Editor für abgeleitete Spalten** automatisch den Ausdruck aus und legt den Datentyp entsprechend fest.</span><span class="sxs-lookup"><span data-stu-id="2cc0f-121">If adding data to a new column, the **Derived Column TransformationEditor** dialog box automatically evaluates the expression and sets the data type appropriately.</span></span> <span data-ttu-id="2cc0f-122">Der Wert dieser Spalte ist schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="2cc0f-122">The value of this column is read-only.</span></span> <span data-ttu-id="2cc0f-123">Weitere Informationen finden Sie unter [Integration Services Datentypen](data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="2cc0f-123">For more information, see [Integration Services Data Types](data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="2cc0f-124">**Länge**</span><span class="sxs-lookup"><span data-stu-id="2cc0f-124">**Length**</span></span>  
 <span data-ttu-id="2cc0f-125">Beim Hinzufügen von Daten zu einer neuen Spalte wertet das Dialogfeld **Transformations-Editor für abgeleitete Spalten** automatisch den Ausdruck aus und legt die Spaltenlänge für Zeichenfolgendaten entsprechend fest.</span><span class="sxs-lookup"><span data-stu-id="2cc0f-125">If adding data to a new column, the **Derived Column TransformationEditor** dialog box automatically evaluates the expression and sets the column length for string data.</span></span> <span data-ttu-id="2cc0f-126">Der Wert dieser Spalte ist schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="2cc0f-126">The value of this column is read-only.</span></span>  
  
 <span data-ttu-id="2cc0f-127">**Genauigkeit**</span><span class="sxs-lookup"><span data-stu-id="2cc0f-127">**Precision**</span></span>  
 <span data-ttu-id="2cc0f-128">Beim Hinzufügen von Daten zu einer neuen Spalte legt das Dialogfeld **Transformations-Editor für abgeleitete Spalten** automatisch die Genauigkeit für numerische Daten basierend auf dem Datentyp fest.</span><span class="sxs-lookup"><span data-stu-id="2cc0f-128">If adding data to a new column, the **Derived Column TransformationEditor** dialog box automatically sets the precision for numeric data based on the data type.</span></span> <span data-ttu-id="2cc0f-129">Der Wert dieser Spalte ist schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="2cc0f-129">The value of this column is read-only.</span></span>  
  
 <span data-ttu-id="2cc0f-130">**Skalierung**</span><span class="sxs-lookup"><span data-stu-id="2cc0f-130">**Scale**</span></span>  
 <span data-ttu-id="2cc0f-131">Beim Hinzufügen von Daten zu einer neuen Spalte legt das Dialogfeld **Transformations-Editor für abgeleitete Spalten** automatisch die Skala für numerische Daten basierend auf dem Datentyp fest.</span><span class="sxs-lookup"><span data-stu-id="2cc0f-131">If adding data to a new column, the **Derived Column TransformationEditor** dialog box automatically sets the scale for numeric data based on the data type.</span></span> <span data-ttu-id="2cc0f-132">Der Wert dieser Spalte ist schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="2cc0f-132">The value of this column is read-only.</span></span>  
  
 <span data-ttu-id="2cc0f-133">**Codepage**</span><span class="sxs-lookup"><span data-stu-id="2cc0f-133">**Code Page**</span></span>  
 <span data-ttu-id="2cc0f-134">Beim Hinzufügen von Daten zu einer neuen Spalte legt das Dialogfeld **Transformations-Editor für abgeleitete Spalten** automatisch die Codepage für den DT_STR-Datentyp fest.</span><span class="sxs-lookup"><span data-stu-id="2cc0f-134">If adding data to a new column, the **Derived Column TransformationEditor** dialog box automatically sets code page for the DT_STR data type.</span></span> <span data-ttu-id="2cc0f-135">Sie können den Wert von **Codepage**aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="2cc0f-135">You can update **Code Page**.</span></span>  
  
 <span data-ttu-id="2cc0f-136">**Fehlerausgabe konfigurieren**</span><span class="sxs-lookup"><span data-stu-id="2cc0f-136">**Configure error output**</span></span>  
 <span data-ttu-id="2cc0f-137">Geben Sie mithilfe des Dialogfelds [Fehlerausgabe konfigurieren](../../2014/integration-services/configure-error-output.md) an, wie Fehler behandelt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="2cc0f-137">Specify how to handle errors by using the [Configure Error Output](../../2014/integration-services/configure-error-output.md) dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cc0f-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2cc0f-138">See Also</span></span>  
 <span data-ttu-id="2cc0f-139">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="2cc0f-139">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="2cc0f-140">Ableiten von Spaltenwerten mithilfe der Transformation für abgeleitete Spalten</span><span class="sxs-lookup"><span data-stu-id="2cc0f-140">Derive Column Values by Using the Derived Column Transformation</span></span>](data-flow/transformations/derive-column-values-by-using-the-derived-column-transformation.md)  
  
  
