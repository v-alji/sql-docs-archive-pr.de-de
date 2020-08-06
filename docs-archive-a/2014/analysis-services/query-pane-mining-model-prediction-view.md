---
title: Abfrage Bereich (Mining Modell-Vorhersage Ansicht) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.prediction.query.f1
ms.assetid: fdeec72e-d0bd-4453-9eaa-46436e4d6edc
author: minewiskan
ms.author: owend
ms.openlocfilehash: e17a27190891ea9e00be21d5013d0767d61ac148
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616246"
---
# <a name="query-pane-mining-model-prediction-view"></a><span data-ttu-id="6059c-102">Abfragebereich (Miningmodell-Vorhersageansicht)</span><span class="sxs-lookup"><span data-stu-id="6059c-102">Query Pane (Mining Model Prediction View)</span></span>
  <span data-ttu-id="6059c-103">Im Bereich **Abfrage** werden die vom Generator für Vorhersageabfragen erstellten DMX-Abfragen (Data Mining-Erweiterungen) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6059c-103">The **Query** pane displays the Data Mining Expressions (DMX) statements created by Prediction Query Builder.</span></span> <span data-ttu-id="6059c-104">Sie können diese Anweisungen ändern und anschließend auf die Schaltfläche **Zur Abfrageergebnissicht wechseln** klicken, um die Ergebnisse zurückgeben zu lassen.</span><span class="sxs-lookup"><span data-stu-id="6059c-104">You can modify the statements and then click the **Switch to query result view** button to return the results.</span></span> <span data-ttu-id="6059c-105">Wenn Sie zurück zur Ansicht **Design** wechseln, gehen alle an der Anweisung vorgenommenen Änderungen verloren.</span><span class="sxs-lookup"><span data-stu-id="6059c-105">If you switch back to the **Design** view, any changes you made to the statement will be lost.</span></span>  
  
 <span data-ttu-id="6059c-106">**Weitere Informationen:** [DMX-Datenbearbeitungsanweisungen &#40;Data Mining-Erweiterungen&#41;](/sql/dmx/dmx-statements-data-manipulation), [Erstellen einer DMX-Abfrage in SQL Server Management Studio](data-mining/create-a-dmx-query-in-sql-server-management-studio.md)</span><span class="sxs-lookup"><span data-stu-id="6059c-106">**For More Information:** [Data Mining Extensions &#40;DMX&#41; Data Manipulation Statements](/sql/dmx/dmx-statements-data-manipulation), [Create a DMX Query in SQL Server Management Studio](data-mining/create-a-dmx-query-in-sql-server-management-studio.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="6059c-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="6059c-107">Options</span></span>  
 <span data-ttu-id="6059c-108">**Zur Abfrageergebnissicht wechseln**</span><span class="sxs-lookup"><span data-stu-id="6059c-108">**Switch to query result view**</span></span>  
 <span data-ttu-id="6059c-109">Klicken Sie hier, um zwischen den Bereichen **Entwurf**, **Abfrage**und **Ergebnis** zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="6059c-109">Click to switch between the **Design**, **Query**, and **Result** panes.</span></span> <span data-ttu-id="6059c-110">Der Wechsel zum Bereich **Ergebnis** führt die Abfrage aus.</span><span class="sxs-lookup"><span data-stu-id="6059c-110">Switching to the **Result** pane runs the query.</span></span>  
  
 <span data-ttu-id="6059c-111">**Abfrageergebnis speichern**</span><span class="sxs-lookup"><span data-stu-id="6059c-111">**Save the query result**</span></span>  
 <span data-ttu-id="6059c-112">Öffnet das Dialogfeld **Ergebnis der Data Mining-Abfrage speichern** .</span><span class="sxs-lookup"><span data-stu-id="6059c-112">Opens the **Save Data Mining Query Result** dialog box.</span></span>  
  
 <span data-ttu-id="6059c-113">**SINGLETON-Abfrage**</span><span class="sxs-lookup"><span data-stu-id="6059c-113">**Singleton query**</span></span>  
 <span data-ttu-id="6059c-114">Ermöglicht, eine SINGLETON-Abfrage zu erstellen, in der Sie &ndash; anstelle von Verweisen auf eine Tabelle mit Eingabewerten &ndash; die Eingabedaten direkt in der Abfrage bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="6059c-114">Lets you create a singleton query, in which you provide the input data directly in your query instead of providing a reference to a table of input values.</span></span> <span data-ttu-id="6059c-115">Die Tabelle **Eingabetabelle(n) auswählen** wird durch die Tabelle **Singleton-Abfrageeingabe** ersetzt.</span><span class="sxs-lookup"><span data-stu-id="6059c-115">The **Select Input Table(s)** table is replaced by a **Singleton Query Input** table.</span></span> <span data-ttu-id="6059c-116">Die aktuelle Vorhersageabfrage geht verloren, wenn Sie zu einer SINGLETON-Abfrage wechseln.</span><span class="sxs-lookup"><span data-stu-id="6059c-116">The current prediction query will be lost if you switch to a singleton query.</span></span>  
  
 <span data-ttu-id="6059c-117">**Abfrageergebnis aktualisieren**</span><span class="sxs-lookup"><span data-stu-id="6059c-117">**Refresh query results**</span></span>  
 <span data-ttu-id="6059c-118">Verarbeitet die Vorhersageabfrage erneut.</span><span class="sxs-lookup"><span data-stu-id="6059c-118">Reprocesses the prediction query.</span></span> <span data-ttu-id="6059c-119">Diese Option ist nur im Bereich **Ergebnis** aktiviert.</span><span class="sxs-lookup"><span data-stu-id="6059c-119">This is enabled only in the **Result** pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6059c-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6059c-120">See Also</span></span>  
 <span data-ttu-id="6059c-121">[Schnittstellen für Data Mining-Abfragen](data-mining/data-mining-query-tools.md) </span><span class="sxs-lookup"><span data-stu-id="6059c-121">[Data Mining Query Interfaces](data-mining/data-mining-query-tools.md) </span></span>  
 <span data-ttu-id="6059c-122">[Data Mining-Erweiterungen &#40;DMX-&#41;-Anweisungs Referenz](/sql/dmx/data-mining-extensions-dmx-statements) </span><span class="sxs-lookup"><span data-stu-id="6059c-122">[Data Mining Extensions &#40;DMX&#41; Statement Reference](/sql/dmx/data-mining-extensions-dmx-statements) </span></span>  
 [<span data-ttu-id="6059c-123">Generator für Vorhersageabfragen &#40;Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="6059c-123">Prediction Query Builder &#40;Data Mining&#41;</span></span>](prediction-query-builder-data-mining.md)  
  
  
