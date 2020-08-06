---
title: Spalten Inhalt und-Datentyp angeben (Data Mining-Assistent) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 0634be64-4c38-4381-9b19-fe9a5889306c
author: minewiskan
ms.author: owend
ms.openlocfilehash: e22f46808877391376f721bcab55ea4fd9074186
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616719"
---
# <a name="specify-column-content-and-data-type-data-mining-wizard"></a><span data-ttu-id="3a11e-102">Inhalt und Datentyp der Spalten angeben (Data Mining-Assistent)</span><span class="sxs-lookup"><span data-stu-id="3a11e-102">Specify Column Content and Data Type (Data Mining Wizard)</span></span>
  <span data-ttu-id="3a11e-103">Auf der Seite **Inhalt und Datentyp der Spalten angeben** geben Sie die Verwendung und den Datentyp für jede Spalte an, die Sie auf der vorherigen Seite des Assistenten ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="3a11e-103">Use the **Specify Column Content and Data Type** page to specify the usage and data type for each column that you selected on the previous page of the wizard.</span></span> <span data-ttu-id="3a11e-104">Wenn Sie die Spalte ignorieren möchten, klicken Sie auf **Zurück** , um zur Seite **Trainingsdaten**zurückzukehren, und deaktivieren Sie alle Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="3a11e-104">If you want to ignore the column, click **Back** to return to the page **Specify the Training Data**, and clear all checkboxes.</span></span>  
  
 <span data-ttu-id="3a11e-105">Die Verwendung einer Spalte gibt an, wie die Daten im Modell verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3a11e-105">The usage of a column indicates how the data will be used in the model.</span></span> <span data-ttu-id="3a11e-106">Eine Spalte kann als Schlüssel zum Identifizieren einer Reihe, als Eingabewert zur Verwendung in Analysen oder als der Wert verwendet werden, den Sie vorhersagen möchten.</span><span class="sxs-lookup"><span data-stu-id="3a11e-106">A column can be used as a key to identify a series, as an input value to use in analysis, or as the value that you want to predict.</span></span> <span data-ttu-id="3a11e-107">Spalten können sowohl für Vorhersagen als auch als Eingabe verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3a11e-107">Columns can be used for both prediction and input.</span></span>  
  
 <span data-ttu-id="3a11e-108">Der Datentyp gibt zusätzliche Details zum Typ der in der Spalte enthaltenen Daten und zur Verwendung der Daten während des Trainings an.</span><span class="sxs-lookup"><span data-stu-id="3a11e-108">The data type specifies additional detail about the type of data that is contained in the column, and how the data will be used during training.</span></span> <span data-ttu-id="3a11e-109">Einige Inhaltstypen erfordern einen bestimmten Datentyp und umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="3a11e-109">Some content types require a specific data type, and vice versa.</span></span> <span data-ttu-id="3a11e-110">Je nach Algorithmus, den Sie beim Erstellen eines Miningmodells verwenden, müssen Sie unter Umständen einen bestimmten Datentyp angeben.</span><span class="sxs-lookup"><span data-stu-id="3a11e-110">You might also need to specify a particular data type depending on the algorithm that you use when you create a mining model.</span></span> <span data-ttu-id="3a11e-111">Informationen zu den Inhalts- und Datentypen in Miningmodellen und -strukturen finden Sie unter [Inhaltstypen &#40;Data Mining&#41;](data-mining/content-types-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="3a11e-111">For information about content types and data types in mining models and structures, see [Content Types &#40;Data Mining&#41;](data-mining/content-types-data-mining.md).</span></span>  
  
 <span data-ttu-id="3a11e-112">**Weitere Informationen:** [Miningstrukturen &#40;Analysis Services - Data Mining&#41;](data-mining/mining-structures-analysis-services-data-mining.md), [Miningmodellspalten](data-mining/mining-model-columns.md), [Data Mining-Assistent &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-wizard-analysis-services-data-mining.md), [Erstellen einer relationalen Miningstruktur](data-mining/create-a-relational-mining-structure.md)</span><span class="sxs-lookup"><span data-stu-id="3a11e-112">**For More Information:** [Mining Structures &#40;Analysis Services - Data Mining&#41;](data-mining/mining-structures-analysis-services-data-mining.md), [Mining Model Columns](data-mining/mining-model-columns.md), [Data Mining Wizard &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-wizard-analysis-services-data-mining.md), [Create a Relational Mining Structure](data-mining/create-a-relational-mining-structure.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="3a11e-113">Tastatur</span><span class="sxs-lookup"><span data-stu-id="3a11e-113">Options</span></span>  
 <span data-ttu-id="3a11e-114">**Miningmodellstruktur**</span><span class="sxs-lookup"><span data-stu-id="3a11e-114">**Mining model structure**</span></span>  
 <span data-ttu-id="3a11e-115">Zeigt die Spalten aus den Ansichten und geschachtelte Tabellen an, die Sie auf der vorherigen Seite des Assistenten ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="3a11e-115">Displays the columns from the views and nested tables that you selected on the previous page of the wizard.</span></span>  
  
 <span data-ttu-id="3a11e-116">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="3a11e-116">**Columns**</span></span>  
 <span data-ttu-id="3a11e-117">Listet die Spalten auf.</span><span class="sxs-lookup"><span data-stu-id="3a11e-117">Lists the columns.</span></span>  
  
 <span data-ttu-id="3a11e-118">**Inhaltstyp**</span><span class="sxs-lookup"><span data-stu-id="3a11e-118">**Content type**</span></span>  
 <span data-ttu-id="3a11e-119">Geben Sie den Inhaltstyp für die Spalte an.</span><span class="sxs-lookup"><span data-stu-id="3a11e-119">Specify the content type for the column.</span></span> <span data-ttu-id="3a11e-120">Wenn Sie auf der vorherigen Seite des Assistenten angegeben haben, dass die Spalte ein Schlüssel ist, sind die folgenden Werte verfügbar:</span><span class="sxs-lookup"><span data-stu-id="3a11e-120">If you specified that the column is a key on the previous page of the wizard, the following values are available:</span></span>  
  
|<span data-ttu-id="3a11e-121">Option</span><span class="sxs-lookup"><span data-stu-id="3a11e-121">Option</span></span>|<span data-ttu-id="3a11e-122">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3a11e-122">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="3a11e-123">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="3a11e-123">Key</span></span>|<span data-ttu-id="3a11e-124">Geben Sie an, dass die Spalte einen eindeutigen Bezeichner für die Fallreihe enthält.</span><span class="sxs-lookup"><span data-stu-id="3a11e-124">Specify that the column contains a unique identifier for the case series.</span></span>|  
|<span data-ttu-id="3a11e-125">Key Sequence</span><span class="sxs-lookup"><span data-stu-id="3a11e-125">Key Sequence</span></span>|<span data-ttu-id="3a11e-126">Geben Sie an, dass die Spalte einen Sequenzbezeichner enthält.</span><span class="sxs-lookup"><span data-stu-id="3a11e-126">Specify that the column contains a sequence identifier.</span></span>|  
|<span data-ttu-id="3a11e-127">Key Time</span><span class="sxs-lookup"><span data-stu-id="3a11e-127">Key Time</span></span>|<span data-ttu-id="3a11e-128">Geben Sie an, dass die Spalte ein Datum oder eine andere eindeutige fortlaufende Nummer enthält, die zum Bezeichnen einer Datums- oder Zeitreihe verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3a11e-128">Specify that the column contains a date or other unique continuous number that is used to identify a date or time series.</span></span>|  
  
 <span data-ttu-id="3a11e-129">Wenn Sie die Spalte als Nicht-Schlüsselspalte ausgewählt haben, sind je nach Datentyp die folgenden Werte verfügbar:</span><span class="sxs-lookup"><span data-stu-id="3a11e-129">If you selected the column as a non-key column, the following values are available, depending on the data type:</span></span>  
  
|<span data-ttu-id="3a11e-130">Option</span><span class="sxs-lookup"><span data-stu-id="3a11e-130">Option</span></span>|<span data-ttu-id="3a11e-131">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3a11e-131">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="3a11e-132">Fortlaufend</span><span class="sxs-lookup"><span data-stu-id="3a11e-132">Continuous</span></span>|<span data-ttu-id="3a11e-133">Geben Sie an, dass die Spalte fortlaufende numerische Werte enthält.</span><span class="sxs-lookup"><span data-stu-id="3a11e-133">Specify that the column contains continuous numeric values.</span></span>|  
|<span data-ttu-id="3a11e-134">Discretized</span><span class="sxs-lookup"><span data-stu-id="3a11e-134">Discretized</span></span>|<span data-ttu-id="3a11e-135">Geben Sie an, dass die Spalte numerische Werte enthält, die diskretisiert wurden oder als diskrete Werte behandelt werden können.</span><span class="sxs-lookup"><span data-stu-id="3a11e-135">Specify that the column contains numeric values that either have been discretized, or can be treated as discrete values.</span></span>|  
|<span data-ttu-id="3a11e-136">Discrete</span><span class="sxs-lookup"><span data-stu-id="3a11e-136">Discrete</span></span>|<span data-ttu-id="3a11e-137">Geben Sie an, dass die Spalte Text oder andere nicht numerische Werte enthält.</span><span class="sxs-lookup"><span data-stu-id="3a11e-137">Specify that the column contains text or other nonnumeric values.</span></span>|  
  
 <span data-ttu-id="3a11e-138">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="3a11e-138">**Data type**</span></span>  
 <span data-ttu-id="3a11e-139">Geben Sie den Datentyp für die Spalte an.</span><span class="sxs-lookup"><span data-stu-id="3a11e-139">Specify the data type for the column.</span></span>  
  
 <span data-ttu-id="3a11e-140">Die folgenden Werte sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="3a11e-140">The following values are available:</span></span>  
  
-   `Boolean`  
  
-   `Date`  
  
-   `Double`  
  
-   `Long`  
  
-   `Text`  
  
 <span data-ttu-id="3a11e-141">**Detect**</span><span class="sxs-lookup"><span data-stu-id="3a11e-141">**Detect**</span></span>  
 <span data-ttu-id="3a11e-142">Analysieren Sie ein Datenbeispiel in allen numerischen Spalten.</span><span class="sxs-lookup"><span data-stu-id="3a11e-142">Analyze a sample of data in all numeric columns.</span></span> <span data-ttu-id="3a11e-143">Ersetzt angegebene Werte für den **Inhaltstyp** durch einen empfohlenen Inhaltstyp.</span><span class="sxs-lookup"><span data-stu-id="3a11e-143">Replaces specified **Content Type** values with a recommended content type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a11e-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3a11e-144">See Also</span></span>  
 <span data-ttu-id="3a11e-145">[Data Mining-Assistent (F1-Hilfe &#40;Analysis Services-Data Mining-&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="3a11e-145">[Data Mining Wizard F1 Help &#40;Analysis Services - Data Mining&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="3a11e-146">[Verwandte Spalten &#40;Data Mining-Assistenten vorschlagen&#41;](suggest-related-columns-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="3a11e-146">[Suggest Related Columns &#40;Data Mining Wizard&#41;](suggest-related-columns-data-mining-wizard.md) </span></span>  
 <span data-ttu-id="3a11e-147">[Geben Sie die Tabellentypen &#40;Data Mining-Assistenten an&#41;](specify-table-types-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="3a11e-147">[Specify Table Types &#40;Data Mining Wizard&#41;](specify-table-types-data-mining-wizard.md) </span></span>  
 [<span data-ttu-id="3a11e-148">Geben Sie den Inhalt und den Datentyp der Spalte &#40;Data Mining-Assistenten an&#41;</span><span class="sxs-lookup"><span data-stu-id="3a11e-148">Specify the Column's Content and Data Type &#40;Data Mining Wizard&#41;</span></span>](specify-the-column-s-content-and-data-type-data-mining-wizard.md)  
  
  
