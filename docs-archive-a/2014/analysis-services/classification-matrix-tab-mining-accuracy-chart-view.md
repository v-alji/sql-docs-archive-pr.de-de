---
title: Klassifizierungs Matrix (Registerkarte) (Mining Genauigkeits Diagramm Sicht) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.accuracychart.confusionmatrix.f1
ms.assetid: 85d5a047-d656-41e0-8a31-400271c2a620
author: minewiskan
ms.author: owend
ms.openlocfilehash: d202d552b25095d0d0845ff64f9c0e289f7bba0e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610275"
---
# <a name="classification-matrix-tab-mining-accuracy-chart-view"></a><span data-ttu-id="f5d05-102">Klassifikationsmatrix (Registerkarte, Mininggenauigkeitsdiagramm-Sicht)</span><span class="sxs-lookup"><span data-stu-id="f5d05-102">Classification Matrix Tab (Mining Accuracy Chart View)</span></span>
  <span data-ttu-id="f5d05-103">Die Registerkarte **Klassifikations Matrix** zeigt eine Klassifikations Matrix für jedes im Modell Raster auf der Registerkarte **Spalten Zuordnung** ausgewählte Modell an. Die Klassifikations Matrix ist nur verfügbar, wenn die vorhersagbare Spalte, die auf der Registerkarte **Spalten Zuordnung** ausgewählt wurde, nicht kontinuierlich ist.</span><span class="sxs-lookup"><span data-stu-id="f5d05-103">The **Classification Matrix** tab displays a classification matrix for each model selected in the models grid on the **Column Mapping** tab. The classification matrix is only available if the predictable column that is selected in the **Column Mapping** tab is not continuous.</span></span> <span data-ttu-id="f5d05-104">Eine ausführlichere Beschreibung der Registerkarte **Klassifikationsmatrix** finden Sie unter [Testing and Validation &#40;Data Mining&#41;](data-mining/testing-and-validation-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="f5d05-104">For a more detailed description of the **Classification Matrix** tab, see [Testing and Validation &#40;Data Mining&#41;](data-mining/testing-and-validation-data-mining.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="f5d05-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="f5d05-105">Options</span></span>  
 <span data-ttu-id="f5d05-106">**Kopieren**</span><span class="sxs-lookup"><span data-stu-id="f5d05-106">**Copy**</span></span>  
 <span data-ttu-id="f5d05-107">Kopiert den Inhalt jeder Klassifikationsmatrix in die Zwischenablage.</span><span class="sxs-lookup"><span data-stu-id="f5d05-107">Copies the content of each classification matrix to the clipboard.</span></span>  
  
 <span data-ttu-id="f5d05-108">**Zähler für \<model> on\< predictable column>**</span><span class="sxs-lookup"><span data-stu-id="f5d05-108">**Counts for \<model> on \< predictable column>**</span></span>  
 <span data-ttu-id="f5d05-109">Zeigt eine Klassifikationsmatrix für jedes Miningmodell in der Miningstruktur an.</span><span class="sxs-lookup"><span data-stu-id="f5d05-109">Displays a classification matrix for each mining model in the mining structure.</span></span> <span data-ttu-id="f5d05-110">Diese Matrix enthält die folgenden Spalten:</span><span class="sxs-lookup"><span data-stu-id="f5d05-110">The matrix contains the following columns:</span></span>  
  
|<span data-ttu-id="f5d05-111">Wert</span><span class="sxs-lookup"><span data-stu-id="f5d05-111">Value</span></span>|<span data-ttu-id="f5d05-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f5d05-112">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f5d05-113">**Vorhergesagt**</span><span class="sxs-lookup"><span data-stu-id="f5d05-113">**Predicted**</span></span>|<span data-ttu-id="f5d05-114">Enthält eine Zeile für jeden Status der vorhersagbaren Spalte.</span><span class="sxs-lookup"><span data-stu-id="f5d05-114">Contains a row for each state of the predictable column.</span></span>|  
|<span data-ttu-id="f5d05-115">**\<states>reale**</span><span class="sxs-lookup"><span data-stu-id="f5d05-115">**\<states> (actual)**</span></span>|<span data-ttu-id="f5d05-116">Eine Spalte für jeden Status in der vorhersagbaren Spalte.</span><span class="sxs-lookup"><span data-stu-id="f5d05-116">A column for each state in the predictable column.</span></span> <span data-ttu-id="f5d05-117">Wenn sich der Status der Zeile und der Spalte entsprechen, stellt die Zelle die tatsächliche Anzahl der Vorkommen des Status in der Datenbank dar.</span><span class="sxs-lookup"><span data-stu-id="f5d05-117">If the state of the row and the column correspond, the cell represents the actual number of times the state exists in the database.</span></span> <span data-ttu-id="f5d05-118">Wenn sich die Status nicht entsprechen, stellt die Zelle den Fehler der Vorhersage dar.</span><span class="sxs-lookup"><span data-stu-id="f5d05-118">If they do not correspond, the cell represents the error of the prediction.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f5d05-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f5d05-119">See Also</span></span>  
 <span data-ttu-id="f5d05-120">[Mining Genauigkeits Diagramm-Designer &#40;Data Mining-&#41;](mining-accuracy-chart-designer-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="f5d05-120">[Mining Accuracy Chart Designer &#40;Data Mining&#41;](mining-accuracy-chart-designer-data-mining.md) </span></span>  
 <span data-ttu-id="f5d05-121">[Test-und validierungsaufgaben und Anleitungen &#40;Data Mining-&#41;](data-mining/testing-and-validation-tasks-and-how-tos-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="f5d05-121">[Testing and Validation Tasks and How-tos &#40;Data Mining&#41;](data-mining/testing-and-validation-tasks-and-how-tos-data-mining.md) </span></span>  
 [<span data-ttu-id="f5d05-122">Tests und Überprüfung &#40;Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="f5d05-122">Testing and Validation &#40;Data Mining&#41;</span></span>](data-mining/testing-and-validation-data-mining.md)  
  
  
