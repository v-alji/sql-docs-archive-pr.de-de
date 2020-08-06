---
title: Festlegen des Datentyps einer Spalte (SSAS-tabellarisch) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 34e2d508-7b64-4503-a4f0-c6c6ad5f8a44
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1d747f96e836a683ccce3aca3c5e3349ca633210
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694733"
---
# <a name="set-the-data-type-of-a-column-ssas-tabular"></a><span data-ttu-id="10d5d-102">Festlegen des Datentyps einer Spalte (SSAS – tabellarisch)</span><span class="sxs-lookup"><span data-stu-id="10d5d-102">Set the Data Type of a Column (SSAS Tabular)</span></span>
  <span data-ttu-id="10d5d-103">Wenn Sie Daten importieren oder Daten in ein Modell einfügen, werden Datentypen vom Modell-Designer automatisch erkannt und angewendet.</span><span class="sxs-lookup"><span data-stu-id="10d5d-103">When you import data or paste data into a model, the model designer will automatically detect and apply data types.</span></span> <span data-ttu-id="10d5d-104">Nachdem Sie dem Modell Daten hinzugefügt haben, können Sie den Datentyp einer Spalte manuell ändern, um die Speicherung von Daten zu ändern.</span><span class="sxs-lookup"><span data-stu-id="10d5d-104">After you have added the data to the model, you can manually modify the data type of a column to change how data is stored.</span></span> <span data-ttu-id="10d5d-105">Bei Bedarf können Sie stattdessen nur das Anzeigeformat der Daten ändern, ohne die Methode der Datenspeicherung zu ändern.</span><span class="sxs-lookup"><span data-stu-id="10d5d-105">If you just want to change the format of how the data is displayed without changing the way it is stored, you can do that instead.</span></span>  
  
### <a name="to-change-the-data-type-or-display-format-for-a-column"></a><span data-ttu-id="10d5d-106">So ändern Sie den Datentyp oder das Anzeigeformat für eine Spalte</span><span class="sxs-lookup"><span data-stu-id="10d5d-106">To change the data type or display format for a column</span></span>  
  
1.  <span data-ttu-id="10d5d-107">Wählen Sie im Modell-Designer die Spalte aus, für die Sie den Datentyp oder das Anzeigeformat ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="10d5d-107">In the model designer, select the column for which you want to change the data type or display format.</span></span>  
  
2.  <span data-ttu-id="10d5d-108">Führen Sie im Fenster **Eigenschaften** der Spalte einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="10d5d-108">In the column **Properties** window, do one of the following:</span></span>  
  
    -   <span data-ttu-id="10d5d-109">Wählen Sie in der **Datenformat** -Eigenschaft ein anderes Datenformat aus.</span><span class="sxs-lookup"><span data-stu-id="10d5d-109">In the **Data Format** property, select a different data format.</span></span>  
  
    -   <span data-ttu-id="10d5d-110">Wählen Sie in der **Datentyp** -Eigenschaft einen anderen Datentyp aus.</span><span class="sxs-lookup"><span data-stu-id="10d5d-110">In the **Data Type** property, select a different data type.</span></span>  
  
## <a name="considerations-when-changing-data-types"></a><span data-ttu-id="10d5d-111">Überlegungen zum Ändern von Datentypen</span><span class="sxs-lookup"><span data-stu-id="10d5d-111">Considerations when Changing Data Types</span></span>  
 <span data-ttu-id="10d5d-112">Wenn Sie versuchen, den Datentyp einer Spalte zu ändern oder eine Datenkonvertierung auszuwählen, kann in einigen Fällen einer der folgenden Fehler auftreten:</span><span class="sxs-lookup"><span data-stu-id="10d5d-112">Sometimes when you try to change the data type of a column or select a data conversion, one of the following errors might occur:</span></span>  
  
-   <span data-ttu-id="10d5d-113">Fehler beim Ändern des Datentyps</span><span class="sxs-lookup"><span data-stu-id="10d5d-113">Failed to change data type</span></span>  
  
-   <span data-ttu-id="10d5d-114">Fehler beim Ändern des Spaltendatentyps</span><span class="sxs-lookup"><span data-stu-id="10d5d-114">Failed to change column data type</span></span>  
  
 <span data-ttu-id="10d5d-115">Diese Fehler können auch auftreten, wenn der Datentyp als Option in der Dropdownliste Datentyp verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="10d5d-115">These errors might occur even if the data type is available as an option in the Data Type dropdown list.</span></span> <span data-ttu-id="10d5d-116">In diesem Abschnitt erfahren Sie, warum diese Fehler auftreten und wie Sie sie korrigieren können.</span><span class="sxs-lookup"><span data-stu-id="10d5d-116">This section explains the cause of these errors and how you can correct them.</span></span>  
  
### <a name="understanding-automatically-determined-data-types"></a><span data-ttu-id="10d5d-117">Grundlegendes zur automatischen Ermittelung von Datentypen</span><span class="sxs-lookup"><span data-stu-id="10d5d-117">Understanding Automatically Determined Data Types</span></span>  
 <span data-ttu-id="10d5d-118">Wenn Sie einem Modell Daten hinzufügen, überprüft der Modell-Designer die Datenspalten, um festzustellen, welche Datentypen die jeweilige Spalte enthält.</span><span class="sxs-lookup"><span data-stu-id="10d5d-118">When you add data to a model, the model designer checks the columns of data to see what data types each column contains.</span></span> <span data-ttu-id="10d5d-119">Wenn die Daten in der jeweiligen Spalte konsistent sind, wird der Spalte der am besten passendste Datentyp zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="10d5d-119">If the data in that column is consistent, is assigns the most precise data type to the column.</span></span>  
  
 <span data-ttu-id="10d5d-120">Wenn Sie Daten jedoch aus Excel oder einer anderen Quelle hinzufügen, die keine einheitliche Verwendung eines einzelnen Datentyps in jeder Spalte erzwingt, weist der Modell-Designer den Datentyp zu, der auf alle Werte innerhalb der Spalte zutrifft.</span><span class="sxs-lookup"><span data-stu-id="10d5d-120">However, if you add data from Excel or another source that does not enforce the use of a single data type within each column, the model designer will assign a data type that accommodates all values within the column.</span></span> <span data-ttu-id="10d5d-121">Wenn eine Spalte Zahlen verschiedener Typen enthält, z. B. ganze Zahlen, lange Zahlen und Währung, verwendet der Modell-Designer den decimal-Datentyp.</span><span class="sxs-lookup"><span data-stu-id="10d5d-121">Therefore, if a column contains numbers of different types, such as integers, long numbers, and currency, the model designer will use a decimal data type.</span></span> <span data-ttu-id="10d5d-122">Wenn eine Spalte Ziffern und Text enthält, verwendet der Modell-Designer stattdessen den text-Datentyp.</span><span class="sxs-lookup"><span data-stu-id="10d5d-122">Alternatively, if a column mixes numbers and text, the model designer will use the text data type.</span></span> <span data-ttu-id="10d5d-123">Der Modell-Designer stellt keinen Datentyp bereit, der mit dem allgemeinen Datentyp in Excel vergleichbar wäre.</span><span class="sxs-lookup"><span data-stu-id="10d5d-123">The model designer does not provide a data type similar to the General data type available in Excel.</span></span>  
  
 <span data-ttu-id="10d5d-124">Wenn eine Spalte Zahlenwerte und Texteinträge enthält, können Sie die Spalte daher nicht in einen numerischen Datentyp konvertieren.</span><span class="sxs-lookup"><span data-stu-id="10d5d-124">Therefore, if a column contains both numbers and text values, you will not be able to convert the column to a numeric data type.</span></span>  
  
 <span data-ttu-id="10d5d-125">Die folgenden Datentypen sind in Business Intelligence-Semantikmodellen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="10d5d-125">The following data types are available in business intelligence semantic models:</span></span>  
  
|<span data-ttu-id="10d5d-126">Modelldatentypen</span><span class="sxs-lookup"><span data-stu-id="10d5d-126">Model data types</span></span>|  
|----------------------|  
|<span data-ttu-id="10d5d-127">Text</span><span class="sxs-lookup"><span data-stu-id="10d5d-127">Text</span></span><br /><br /> <span data-ttu-id="10d5d-128">Decimal Number</span><span class="sxs-lookup"><span data-stu-id="10d5d-128">Decimal Number</span></span><br /><br /> <span data-ttu-id="10d5d-129">Ganze Zahl</span><span class="sxs-lookup"><span data-stu-id="10d5d-129">Whole Number</span></span><br /><br /> <span data-ttu-id="10d5d-130">Währung</span><span class="sxs-lookup"><span data-stu-id="10d5d-130">Currency</span></span><br /><br /> <span data-ttu-id="10d5d-131">TRUE/FALSE</span><span class="sxs-lookup"><span data-stu-id="10d5d-131">TRUE/FALSE</span></span><br /><br /> <span data-ttu-id="10d5d-132">Date</span><span class="sxs-lookup"><span data-stu-id="10d5d-132">Date</span></span>|  
  
 <span data-ttu-id="10d5d-133">Wenn Sie feststellen, dass die Daten einen falschen bzw. nicht den gewünschten Datentyp aufweisen, haben Sie mehrere Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="10d5d-133">If you find that your data has a wrong data type, or at least a different one than you wanted, you have several options:</span></span>  
  
-   <span data-ttu-id="10d5d-134">Sie können die Daten erneut importieren.</span><span class="sxs-lookup"><span data-stu-id="10d5d-134">You can re-import the data.</span></span> <span data-ttu-id="10d5d-135">Hierzu öffnen Sie die vorhandene Verbindung mit der Datenquelle und importieren die Spalte erneut.</span><span class="sxs-lookup"><span data-stu-id="10d5d-135">To do this, open the existing connection to the data source and re-import the column.</span></span> <span data-ttu-id="10d5d-136">Je nach Datenquellentyp können Sie beim Import einen Filter anwenden, um Problemwerte zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="10d5d-136">Depending on the data source type, you might be able to apply a filter during import to remove problem values.</span></span>  
  
-   <span data-ttu-id="10d5d-137">Sie können in einer berechneten Spalte eine DAX-Formel erstellen, um einen neuen Wert des gewünschten Datentyps zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="10d5d-137">You can create a DAX formula in a calculated column to create a new value of the desired data type.</span></span> <span data-ttu-id="10d5d-138">Sie können z. B. die TRUNC-Funktion verwenden, um eine Dezimalzahl in eine ganze Zahl zu ändern. Sie können auch Informationsfunktionen und logische Funktionen kombinieren, um Werte zu testen und zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="10d5d-138">For example, the TRUNC function can be used to change a decimal number to a whole integer, or you can combine information functions and logical functions to test and convert values.</span></span>  
  
### <a name="understanding-data-conversion"></a><span data-ttu-id="10d5d-139">Grundlegendes zur Datenkonvertierung</span><span class="sxs-lookup"><span data-stu-id="10d5d-139">Understanding Data Conversion</span></span>  
 <span data-ttu-id="10d5d-140">Wenn bei der Auswahl einer Datenkonvertierungsoption ein Fehler auftritt, kann dies daran liegen, dass der aktuelle Datentyp der Spalte die ausgewählte Konvertierung nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="10d5d-140">If an error occurs when you select a data conversion option, it might be that the current data type of the column does not support the selected conversion.</span></span> <span data-ttu-id="10d5d-141">Nicht alle Konvertierungen sind für alle Datentypen zulässig.</span><span class="sxs-lookup"><span data-stu-id="10d5d-141">Not all conversions are allowed for all data types.</span></span> <span data-ttu-id="10d5d-142">Sie können eine Spalte z. B. nur dann in einen booleschen Datentyp ändern, wenn der aktuelle Datentyp der Spalte entweder eine Zahl (ganz oder dezimal) oder Text ist.</span><span class="sxs-lookup"><span data-stu-id="10d5d-142">For example, you can only change a column to a Boolean data type if the current data type of the column is either a number (whole or decimal) or text.</span></span> <span data-ttu-id="10d5d-143">Daher müssen Sie für die Daten in der Spalte einen passenden Datentyp auswählen.</span><span class="sxs-lookup"><span data-stu-id="10d5d-143">Therefore, you must choose an appropriate data type for the data in the column.</span></span>  
  
 <span data-ttu-id="10d5d-144">Nachdem Sie einen entsprechenden Datentyp ausgewählt haben, warnt der Modell-Designer Sie vor möglichen Änderungen an den Daten, z. B. geringere Genauigkeit oder abgeschnittene Daten.</span><span class="sxs-lookup"><span data-stu-id="10d5d-144">After you choose an appropriate data type, the model designer will warn you about possible changes to your data, such as loss of precision, or truncation.</span></span> <span data-ttu-id="10d5d-145">Klicken Sie zur Bestätigung auf OK, um die Daten in den neuen Datentyp zu ändern.</span><span class="sxs-lookup"><span data-stu-id="10d5d-145">Click OK to accept and change your data to the new data type.</span></span>  
  
 <span data-ttu-id="10d5d-146">Wenn der Datentyp unterstützt wird, der Modell-Designer jedoch Werte findet, die vom neuen Datentyp nicht unterstützt werden, erhalten Sie eine weitere Fehlermeldung. Sie müssen die Datenwerte korrigieren, bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="10d5d-146">If the data type is supported, but the model designer finds values that are not supported within the new data type, you will get another error, and will need to correct the data values before proceeding.</span></span>  
  
 <span data-ttu-id="10d5d-147">Unter [Unterstützte Datentypen &#40;SSAS – tabellarisch&#41;](data-types-supported-ssas-tabular.md)finden Sie detaillierte Informationen zu den Datentypen, die in Business Intelligence-Semantikmodellen verwendet werden. Zudem wird erläutert, wie die Datentypen implizit konvertiert und wie verschiedene Datentypen in Formeln verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="10d5d-147">For detailed information about the data types used in business intelligence semantic models, how they are implicitly converted, and how different data types are used in formulas, see [Data Types Supported &#40;SSAS Tabular&#41;](data-types-supported-ssas-tabular.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10d5d-148">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="10d5d-148">See Also</span></span>  
 [<span data-ttu-id="10d5d-149">Unterstützte Datentypen &#40;SSAS – tabellarisch&#41;</span><span class="sxs-lookup"><span data-stu-id="10d5d-149">Data Types Supported &#40;SSAS Tabular&#41;</span></span>](data-types-supported-ssas-tabular.md)  
  
  