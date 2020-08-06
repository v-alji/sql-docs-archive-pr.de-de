---
title: Transformations-Editor für Datenkonvertierung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dataconversiontransformation.f1
helpviewer_keywords:
- Data Conversion Transformation Editor
ms.assetid: 7b4e4873-e8fe-4549-a965-65bebdb270bc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4b893f04dcca2dd2a1a5874b55c1c1c608aaeb12
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726154"
---
# <a name="data-conversion-transformation-editor"></a><span data-ttu-id="7f16e-102">Transformations-Editor für Datenkonvertierung</span><span class="sxs-lookup"><span data-stu-id="7f16e-102">Data Conversion Transformation Editor</span></span>
  <span data-ttu-id="7f16e-103">Im Dialogfeld **Transformations-Editor für Datenkonvertierung** können Sie die zu konvertierenden Spalten und den Datentyp, in den die Spalte konvertiert werden soll, auswählen und Konvertierungsattribute festlegen.</span><span class="sxs-lookup"><span data-stu-id="7f16e-103">Use the **Data Conversion Transformation Editor** dialog box to select the columns to convert, select the data type to which the column is converted, and set conversion attributes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7f16e-104">Die- `FastParse` Eigenschaft der Ausgabespalten der Transformation für Datenkonvertierung ist im **Transformations-Editor für Datenkonvertierung**nicht verfügbar, kann jedoch mit dem- **Erweiterter Editor**festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="7f16e-104">The `FastParse` property of the output columns of the Data Conversion transformation is not available in the **Data Conversion Transformation Editor**, but can be set by using the **Advanced Editor**.</span></span> <span data-ttu-id="7f16e-105">Weitere Informationen zu dieser Eigenschaft finden Sie im Abschnitt "Transformation für Datenkonvertierung" von [Transformation Custom Properties](data-flow/transformations/transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="7f16e-105">For more information on this property, see the Data Conversion Transformation section of [Transformation Custom Properties](data-flow/transformations/transformation-custom-properties.md).</span></span>  
  
 <span data-ttu-id="7f16e-106">Weitere Informationen zur Transformation für Datenkonvertierung finden Sie unter [Data Conversion Transformation](data-flow/transformations/data-conversion-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="7f16e-106">To learn more about the Data Conversion transformation, see [Data Conversion Transformation](data-flow/transformations/data-conversion-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="7f16e-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="7f16e-107">Options</span></span>  
 <span data-ttu-id="7f16e-108">**Verfügbare Eingabespalten**</span><span class="sxs-lookup"><span data-stu-id="7f16e-108">**Available Input Columns**</span></span>  
 <span data-ttu-id="7f16e-109">Wählen Sie mithilfe der Kontrollkästchen die zu konvertierenden Spalten aus.</span><span class="sxs-lookup"><span data-stu-id="7f16e-109">Select columns to convert by using the check boxes.</span></span> <span data-ttu-id="7f16e-110">Durch Ihre Auswahl werden der nachfolgenden Tabelle Eingabespalten hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="7f16e-110">Your selections add input columns to the table below.</span></span>  
  
 <span data-ttu-id="7f16e-111">**Eingabespalte**</span><span class="sxs-lookup"><span data-stu-id="7f16e-111">**Input Column**</span></span>  
 <span data-ttu-id="7f16e-112">Wählen Sie zu konvertierende Spalten aus der Liste der verfügbaren Eingabespalten aus.</span><span class="sxs-lookup"><span data-stu-id="7f16e-112">Select columns to convert from the list of available input columns.</span></span> <span data-ttu-id="7f16e-113">Ihre Auswahl wird entsprechend in der Auswahl der Kontrollkästchen oben deutlich.</span><span class="sxs-lookup"><span data-stu-id="7f16e-113">Your selections are reflected in the check box selections above.</span></span>  
  
 <span data-ttu-id="7f16e-114">**Ausgabealias**</span><span class="sxs-lookup"><span data-stu-id="7f16e-114">**Output Alias**</span></span>  
 <span data-ttu-id="7f16e-115">Geben Sie einen Alias für jede neue Spalte ein.</span><span class="sxs-lookup"><span data-stu-id="7f16e-115">Type an alias for each new column.</span></span> <span data-ttu-id="7f16e-116">Der Standard lautet `Copy of`, gefolgt vom Namen der Eingabespalte. Sie können jedoch auch einen eindeutigen, beschreibenden Namen auswählen.</span><span class="sxs-lookup"><span data-stu-id="7f16e-116">The default is `Copy of` followed by the input column name; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="7f16e-117">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="7f16e-117">**Data Type**</span></span>  
 <span data-ttu-id="7f16e-118">Wählen Sie einen verfügbaren Datentyp aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="7f16e-118">Select an available data type from the list.</span></span> <span data-ttu-id="7f16e-119">Weitere Informationen finden Sie unter [Integration Services Datentypen](data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="7f16e-119">For more information, see [Integration Services Data Types](data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="7f16e-120">**Länge**</span><span class="sxs-lookup"><span data-stu-id="7f16e-120">**Length**</span></span>  
 <span data-ttu-id="7f16e-121">Legt für Zeichenfolgendaten die Spaltenlänge fest.</span><span class="sxs-lookup"><span data-stu-id="7f16e-121">Set the column length for string data.</span></span>  
  
 <span data-ttu-id="7f16e-122">**Genauigkeit**</span><span class="sxs-lookup"><span data-stu-id="7f16e-122">**Precision**</span></span>  
 <span data-ttu-id="7f16e-123">Legt für numerische Daten die Genauigkeit fest.</span><span class="sxs-lookup"><span data-stu-id="7f16e-123">Set the precision for numeric data.</span></span>  
  
 <span data-ttu-id="7f16e-124">**Skalierung**</span><span class="sxs-lookup"><span data-stu-id="7f16e-124">**Scale**</span></span>  
 <span data-ttu-id="7f16e-125">Legt für numerische Daten die Dezimalstellen fest.</span><span class="sxs-lookup"><span data-stu-id="7f16e-125">Set the scale for numeric data.</span></span>  
  
 <span data-ttu-id="7f16e-126">**Codepage**</span><span class="sxs-lookup"><span data-stu-id="7f16e-126">**Code page**</span></span>  
 <span data-ttu-id="7f16e-127">Wählen Sie die geeignete Codepage für Spalten vom Typ DT_STR aus.</span><span class="sxs-lookup"><span data-stu-id="7f16e-127">Select the appropriate code page for columns of type DT_STR.</span></span>  
  
 <span data-ttu-id="7f16e-128">**Fehlerausgabe konfigurieren**</span><span class="sxs-lookup"><span data-stu-id="7f16e-128">**Configure error output**</span></span>  
 <span data-ttu-id="7f16e-129">Geben Sie mithilfe des Dialogfelds [Fehlerausgabe konfigurieren](../../2014/integration-services/configure-error-output.md) an, wie Fehler auf Zeilenebene behandelt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="7f16e-129">Specify how to handle row-level errors by using the [Configure Error Output](../../2014/integration-services/configure-error-output.md) dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f16e-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7f16e-130">See Also</span></span>  
 <span data-ttu-id="7f16e-131">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="7f16e-131">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="7f16e-132">Konvertieren von Daten in einen anderen Datentyp mithilfe der Transformation für Datenkonvertierung</span><span class="sxs-lookup"><span data-stu-id="7f16e-132">Convert Data to a Different Data Type by Using the Data Conversion Transformation</span></span>](data-flow/transformations/convert-data-type-by-using-data-conversion-transformation.md)  
  
  
