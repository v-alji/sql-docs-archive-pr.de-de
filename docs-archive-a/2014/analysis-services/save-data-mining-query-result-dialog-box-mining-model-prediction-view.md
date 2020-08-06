---
title: Ergebnis der Data Mining-Abfrage speichern (Dialog Feld) (Mining Modell-Vorhersage Ansicht) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dm.savedataminingqueryresult.f1
helpviewer_keywords:
- Save Data Mining Query Result dialog box
ms.assetid: 112fb527-7466-4fd4-9cf1-75596135648f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0838c90f0797a0db9c8a66cd8c5f877aaecdad0a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610125"
---
# <a name="save-data-mining-query-result-dialog-box-mining-model-prediction-view"></a><span data-ttu-id="23e01-102">Ergebnis der Data Mining-Abfrage speichern (Dialogfeld - Miningmodellvorhersage-Sicht)</span><span class="sxs-lookup"><span data-stu-id="23e01-102">Save Data Mining Query Result Dialog Box (Mining Model Prediction View)</span></span>
  <span data-ttu-id="23e01-103">Verwenden Sie das Dialogfeld **Ergebnis der Data Mining-Abfrage speichern** , um die Ergebnisse einer Data Mining-Abfrage in einer neuen Tabelle zu speichern.</span><span class="sxs-lookup"><span data-stu-id="23e01-103">Use the **Save Data Mining Query Result** dialog box to save the results of a data mining query to a new table.</span></span>  
  
 <span data-ttu-id="23e01-104">Die neue Tabelle wird in der durch die Datenquelle definierten Datenbank erstellt.</span><span class="sxs-lookup"><span data-stu-id="23e01-104">The new table will be created in the database defined by the data source.</span></span>  
  
## <a name="options"></a><span data-ttu-id="23e01-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="23e01-105">Options</span></span>  
 <span data-ttu-id="23e01-106">**Data Source**</span><span class="sxs-lookup"><span data-stu-id="23e01-106">**Data Source**</span></span>  
 <span data-ttu-id="23e01-107">Wählen Sie eine Datenquelle aus dem aktuellen Projekt aus.</span><span class="sxs-lookup"><span data-stu-id="23e01-107">Select a data source from the current project.</span></span> <span data-ttu-id="23e01-108">Wenn die richtige Datenquelle nicht vorhanden ist, klicken Sie auf **Neu** , um eine neue Datenquelle zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="23e01-108">If the correct data source does not exist, click **New** to create a new data source.</span></span>  
  
 <span data-ttu-id="23e01-109">**Neu**</span><span class="sxs-lookup"><span data-stu-id="23e01-109">**New**</span></span>  
 <span data-ttu-id="23e01-110">Öffnet den **Datenquellen-Assistenten**.</span><span class="sxs-lookup"><span data-stu-id="23e01-110">Opens the **Data Source Wizard**.</span></span>  
  
 <span data-ttu-id="23e01-111">**Tabellenname**</span><span class="sxs-lookup"><span data-stu-id="23e01-111">**Table Name**</span></span>  
 <span data-ttu-id="23e01-112">Geben Sie einen Namen für die neue Tabelle ein.</span><span class="sxs-lookup"><span data-stu-id="23e01-112">Type a name for the new table.</span></span>  
  
 <span data-ttu-id="23e01-113">**Überschreiben, falls vorhanden**</span><span class="sxs-lookup"><span data-stu-id="23e01-113">**Overwrite if exists**</span></span>  
 <span data-ttu-id="23e01-114">Aktivieren Sie diese Option, wenn eine vorhandene Tabelle mit demselben Namen überschrieben werden soll.</span><span class="sxs-lookup"><span data-stu-id="23e01-114">Select this option if you want to overwrite an existing table with the same name.</span></span>  
  
 <span data-ttu-id="23e01-115">In folgenden Fällen muss die vorhandene Tabelle überschrieben werden:</span><span class="sxs-lookup"><span data-stu-id="23e01-115">Overwriting the existing table is required if any of the following is true:</span></span>  
  
-   <span data-ttu-id="23e01-116">Sie haben der Vorhersageabfrage Spalten hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="23e01-116">You added columns to the prediction query.</span></span>  
  
-   <span data-ttu-id="23e01-117">Sie haben die Namen oder Datentypen von Spalten in der Vorhersageabfrage geändert.</span><span class="sxs-lookup"><span data-stu-id="23e01-117">You changed the names or data types of any columns in the prediction query.</span></span>  
  
-   <span data-ttu-id="23e01-118">Sie haben eine ALTER-Anweisung für die Zieltabelle ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="23e01-118">You ran an ALTER statement on the destination table.</span></span>  
  
 <span data-ttu-id="23e01-119">Wenn mehrere Spalten denselben Namen aufweisen (wenn mehrere abgeleitete Spalten z.B. über den standardmäßigen Spaltennamen **Ausdruck**verfügen), müssen Sie für jede Spalte mit einem doppelten Namen einen Alias erstellen.</span><span class="sxs-lookup"><span data-stu-id="23e01-119">If multiple columns have the same name (for example, several derived columns might have the default column name **Expression**), you must create an alias for each column with a duplicate name.</span></span> <span data-ttu-id="23e01-120">Wenn die Spalten keine eindeutigen Namen aufweisen, tritt ein Fehler auf, wenn der Designer versucht, die Ergebnisse in SQL Server zu speichern, da Spalten in einer Tabelle über eindeutige Namen verfügen müssen.</span><span class="sxs-lookup"><span data-stu-id="23e01-120">If the columns do not have unique names, an error will be raised when the designer tries to save the results to SQL Server, because columns in a table must have unique names.</span></span>  
  
 <span data-ttu-id="23e01-121">**Zur Datenquellensicht hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="23e01-121">**Add to DSV**</span></span>  
 <span data-ttu-id="23e01-122">(Optional) Wählen Sie eine im Projekt enthaltene Datenquellensicht aus, wenn Sie die Tabelle einer vorhandenen Datenquelle hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="23e01-122">(Optional) Select a data source view contained in the project if you want to add the table to an existing data source.</span></span>  
  
 <span data-ttu-id="23e01-123">Diese Option ist nützlich, wenn Sie alle verknüpften Tabellen für ein Modell (z. b. Trainingsdaten, Vorhersage Quelldaten und Abfrageergebnisse) in derselben Datenquelle beibehalten möchten.</span><span class="sxs-lookup"><span data-stu-id="23e01-123">This option is useful if you want to keep all related tables for a model-such as training data, prediction source data, and query results-in the same data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23e01-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="23e01-124">See Also</span></span>  
 <span data-ttu-id="23e01-125">[Vorhersage Abfrage-Generator &#40;Data Mining-&#41;](prediction-query-builder-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="23e01-125">[Prediction Query Builder &#40;Data Mining&#41;](prediction-query-builder-data-mining.md) </span></span>  
 <span data-ttu-id="23e01-126">[Schnittstellen für Data Mining-Abfragen](data-mining/data-mining-query-tools.md) </span><span class="sxs-lookup"><span data-stu-id="23e01-126">[Data Mining Query Interfaces](data-mining/data-mining-query-tools.md) </span></span>  
 [<span data-ttu-id="23e01-127">Data Mining-Erweiterungen &#40;DMX&#41; – Anweisungsreferenz</span><span class="sxs-lookup"><span data-stu-id="23e01-127">Data Mining Extensions &#40;DMX&#41; Statement Reference</span></span>](/sql/dmx/data-mining-extensions-dmx-statements)  
  
  
