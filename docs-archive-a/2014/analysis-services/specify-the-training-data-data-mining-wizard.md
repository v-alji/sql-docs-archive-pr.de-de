---
title: Trainingsdaten angeben (Data Mining-Assistent) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.dmwizard.specifytrainingdata.f1
ms.assetid: cb04deeb-0f89-4bba-b3f1-efccada16825
author: minewiskan
ms.author: owend
ms.openlocfilehash: 87a802256d287a3e8e9e7fb65bbd91687cb71a4a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620541"
---
# <a name="specify-the-training-data-data-mining-wizard"></a><span data-ttu-id="f7e2d-102">Trainingsdaten angeben (Data Mining-Assistent)</span><span class="sxs-lookup"><span data-stu-id="f7e2d-102">Specify the Training Data (Data Mining Wizard)</span></span>
  <span data-ttu-id="f7e2d-103">Mithilfe der Seite **Trainingsdaten angeben** können Sie festlegen, welche Spalten in der Miningstruktur enthalten sein sollen.</span><span class="sxs-lookup"><span data-stu-id="f7e2d-103">Use the **Specify the Training Data** page to identify which columns to include in the mining structure.</span></span> <span data-ttu-id="f7e2d-104">Sie können auch Spalten für die Struktur auswählen, wenn Sie sie nicht in allen Modellen verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="f7e2d-104">You can select columns to include in the structure even if you do not use them in all models.</span></span> <span data-ttu-id="f7e2d-105">Wenn Sie beispielsweise einen Drillthrough zu den Spalten vom Miningmodell ausführen möchten, können Sie die Spalten in die Struktur aufnehmen, aber nicht in das Modell.</span><span class="sxs-lookup"><span data-stu-id="f7e2d-105">For example, if you want to drill through to the columns from the mining model, you can include them in the structure but not in the model.</span></span>  
  
 <span data-ttu-id="f7e2d-106">Mindestens eine Schlüsselspalte ist für jede Tabelle erforderlich, die in die Struktur aufgenommen wird.</span><span class="sxs-lookup"><span data-stu-id="f7e2d-106">At least one key column is required for each table that is included in the structure.</span></span> <span data-ttu-id="f7e2d-107">Welche Spalte Sie als Schlüssel auswählen, hängt davon ab, ob die Tabelle eine Falltabelle oder eine geschachtelte Tabelle ist.</span><span class="sxs-lookup"><span data-stu-id="f7e2d-107">The column that you pick as the key depends on whether the table is a case table or a nested table.</span></span> <span data-ttu-id="f7e2d-108">Ist die Tabelle eine geschachtelte Tabelle, ist der Schlüssel häufig auch die vorhersagbare Spalte, nicht der relationale Fremdschlüssel.</span><span class="sxs-lookup"><span data-stu-id="f7e2d-108">If the table is a nested table, the key is often also the predictable column, not the relational foreign key.</span></span> <span data-ttu-id="f7e2d-109">Weitere Informationen zu geschachtelten Schlüsseln finden Sie unter [Geschachtelte Tabellen &#40;Analysis Services – Data Mining&#41;](data-mining/nested-tables-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="f7e2d-109">To learn about nested keys, see [Nested Tables &#40;Analysis Services - Data Mining&#41;](data-mining/nested-tables-analysis-services-data-mining.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f7e2d-110">Unterschiedliche Miningalgorithmen verwenden Schlüssel auf unterschiedliche Art und Weise.</span><span class="sxs-lookup"><span data-stu-id="f7e2d-110">Different mining algorithms use keys differently.</span></span> <span data-ttu-id="f7e2d-111">Weitere Informationen über die verschiedenen Schlüsselarten finden Sie unter [Inhaltstypen &#40;Data Mining&#41;](data-mining/content-types-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="f7e2d-111">To learn about the different kinds of keys, see [Content Types &#40;Data Mining&#41;](data-mining/content-types-data-mining.md).</span></span>  
  
 <span data-ttu-id="f7e2d-112">**Weitere Informationen:** [Miningstrukturen &#40;Analysis Services - Data Mining&#41;](data-mining/mining-structures-analysis-services-data-mining.md), [Miningmodellspalten](data-mining/mining-model-columns.md), [Data Mining-Assistent &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-wizard-analysis-services-data-mining.md), [Erstellen einer relationalen Miningstruktur](data-mining/create-a-relational-mining-structure.md)</span><span class="sxs-lookup"><span data-stu-id="f7e2d-112">**For More Information:** [Mining Structures &#40;Analysis Services - Data Mining&#41;](data-mining/mining-structures-analysis-services-data-mining.md), [Mining Model Columns](data-mining/mining-model-columns.md), [Data Mining Wizard &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-wizard-analysis-services-data-mining.md), [Create a Relational Mining Structure](data-mining/create-a-relational-mining-structure.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="f7e2d-113">Tastatur</span><span class="sxs-lookup"><span data-stu-id="f7e2d-113">Options</span></span>  
 <span data-ttu-id="f7e2d-114">**Tabellen/Spalten**</span><span class="sxs-lookup"><span data-stu-id="f7e2d-114">**Tables/Columns**</span></span>  
 <span data-ttu-id="f7e2d-115">Zeigt die Tabellen und Spalten an, die Sie auf der vorherigen Seite des Assistenten ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="f7e2d-115">Displays the tables and columns that you selected on the previous page of the wizard.</span></span>  
  
 **\<check box>**  
 <span data-ttu-id="f7e2d-116">Wählen Sie die Spalten aus, die in die Miningstruktur aufgenommen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f7e2d-116">Select the columns to include in the mining structure.</span></span>  
  
 <span data-ttu-id="f7e2d-117">Wenn Ihre Datenquelle geschachtelte Tabellen oder mehrere Ansichten enthält, erweitern Sie die Spaltenliste, um die geschachtelten Tabellen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f7e2d-117">If your data source includes nested tables or multiple views, expand the column list to view the nested tables.</span></span>  
  
 <span data-ttu-id="f7e2d-118">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="f7e2d-118">**Key**</span></span>  
 <span data-ttu-id="f7e2d-119">Wählen Sie diese Option aus, um die Spalte als eindeutigen Bezeichner für die Daten auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="f7e2d-119">Select to use the column as a unique identifier for the data.</span></span>  
  
 <span data-ttu-id="f7e2d-120">Bei einer Falltabelle ist der Schlüssel in der Regel der eindeutige Bezeichner.</span><span class="sxs-lookup"><span data-stu-id="f7e2d-120">For a case table, the key is usually the unique identifier.</span></span>  
  
 <span data-ttu-id="f7e2d-121">Bei einer geschachtelten Tabelle gibt der **Schlüssel** den Bezeichner einer Zeile im Kontext des verbundenen Falls an.</span><span class="sxs-lookup"><span data-stu-id="f7e2d-121">For nested table, the **Key** indicates the identifier of a row in the context of the associated case.</span></span>  
  
 <span data-ttu-id="f7e2d-122">**Eingabe**</span><span class="sxs-lookup"><span data-stu-id="f7e2d-122">**Input**</span></span>  
 <span data-ttu-id="f7e2d-123">Wählen Sie diese Option aus, um die Spalte beim Erstellen von Vorhersagen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f7e2d-123">Select to use the column in creating predictions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f7e2d-124">Diese Spalte ist nur verfügbar, wenn Sie zusammen mit der Miningstruktur ein Miningmodell erstellen.</span><span class="sxs-lookup"><span data-stu-id="f7e2d-124">This column is only available when you are creating a mining model together with the mining structure.</span></span>  
  
 <span data-ttu-id="f7e2d-125">**Vorhersagbar**</span><span class="sxs-lookup"><span data-stu-id="f7e2d-125">**Predictable**</span></span>  
 <span data-ttu-id="f7e2d-126">Wählen Sie diese Option aus, um zu aktivieren, dass die Tabelle oder die Spalte auf der Grundlage zukünftiger zusätzlicher Eingaben vorhergesagt werden können.</span><span class="sxs-lookup"><span data-stu-id="f7e2d-126">Select to enable the table or column to be predicted based on additional future input.</span></span>  
  
 <span data-ttu-id="f7e2d-127">Wenn Sie eine geschachtelte Tabelle außerdem als vorhersagbar kennzeichnen, wird die gesamte geschachtelte Tabelle vorhersagbar.</span><span class="sxs-lookup"><span data-stu-id="f7e2d-127">If you also mark a nested table as predictable, the whole nested table becomes predictable.</span></span> <span data-ttu-id="f7e2d-128">Wenn in der geschachtelten Tabelle keine Spalten als Eingabe oder als vorhersagbar gekennzeichnet sind, erscheint die geschachtelte Tabelle in der Miningstruktur, wird aber im Modell ignoriert.</span><span class="sxs-lookup"><span data-stu-id="f7e2d-128">If no columns in the nested table are marked as input or predictable, the nested table will appear in the mining structure, but will be ignored in the model.</span></span>  
  
 <span data-ttu-id="f7e2d-129">**Hinweis** Diese Spalte ist nur verfügbar, wenn Sie zusammen mit der Miningstruktur ein Miningmodell erstellen.</span><span class="sxs-lookup"><span data-stu-id="f7e2d-129">**Note** This column is only available when you are creating a mining model together with the mining structure.</span></span>  
  
 <span data-ttu-id="f7e2d-130">**Vorschlagen**</span><span class="sxs-lookup"><span data-stu-id="f7e2d-130">**Suggest**</span></span>  
 <span data-ttu-id="f7e2d-131">Klicken Sie hierauf, um das Dialogfeld **Verbundene Spalten vorschlagen** zu öffnen, das eine Analyse einer Datenprobe durchführt, um auf der Grundlage der Entropie Eingabespalten zu ermitteln, die die engste Beziehung zur ausgewählten Spalte **Vorhersagbar** haben.</span><span class="sxs-lookup"><span data-stu-id="f7e2d-131">Click to open the **Suggest Related Columns** dialog box, which performs an analysis on a sample of data to identify input columns that show the greatest relationship to the selected **Predictable** column based on entropy.</span></span> <span data-ttu-id="f7e2d-132">Diese Analyse bezieht auch Spalten geschachtelter Tabellen oder Miningstrukturen ein, die auf OLAP-Quellen basieren.</span><span class="sxs-lookup"><span data-stu-id="f7e2d-132">This analysis also applies to nested table columns or mining structures that are based on OLAP sources.</span></span>  
  
 <span data-ttu-id="f7e2d-133">**Hinweis** Diese Spalte ist nur verfügbar, wenn Sie zusammen mit der Miningstruktur ein Miningmodell erstellen.</span><span class="sxs-lookup"><span data-stu-id="f7e2d-133">**Note** This column only available when you are creating a mining model together with the mining structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7e2d-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f7e2d-134">See Also</span></span>  
 <span data-ttu-id="f7e2d-135">[Data Mining-Assistent (F1-Hilfe &#40;Analysis Services-Data Mining-&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="f7e2d-135">[Data Mining Wizard F1 Help &#40;Analysis Services - Data Mining&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="f7e2d-136">[Verwandte Spalten &#40;Data Mining-Assistenten vorschlagen&#41;](suggest-related-columns-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="f7e2d-136">[Suggest Related Columns &#40;Data Mining Wizard&#41;](suggest-related-columns-data-mining-wizard.md) </span></span>  
 <span data-ttu-id="f7e2d-137">[Geben Sie die Tabellentypen &#40;Data Mining-Assistenten an&#41;](specify-table-types-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="f7e2d-137">[Specify Table Types &#40;Data Mining Wizard&#41;](specify-table-types-data-mining-wizard.md) </span></span>  
 [<span data-ttu-id="f7e2d-138">Geben Sie den Inhalt und den Datentyp der Spalte &#40;Data Mining-Assistenten an&#41;</span><span class="sxs-lookup"><span data-stu-id="f7e2d-138">Specify the Column's Content and Data Type &#40;Data Mining Wizard&#41;</span></span>](specify-the-column-s-content-and-data-type-data-mining-wizard.md)  
  
  
