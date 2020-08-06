---
title: Drillthrough (Dialog Feld) (Mining Modell-Viewer) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.drillthrough.f1
ms.assetid: 42b78399-143d-4f44-90e0-b545ffb79e10
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1b00c62017de5a26c4507a04aeaf59aba7522146
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621247"
---
# <a name="drill-through-dialog-box-mining-model-viewer"></a><span data-ttu-id="ec9b8-102">Dialogfeld "Drillthrough" (Miningmodell &ndash; Viewer)</span><span class="sxs-lookup"><span data-stu-id="ec9b8-102">Drill Through Dialog Box (Mining Model Viewer)</span></span>
  <span data-ttu-id="ec9b8-103">Wenn Sie ein Miningmodell mithilfe der Registerkarte **Miningmodell-Viewer** im Data Mining-Designer anzeigen, können Sie einen Drillthrough in die Details der Falldaten ausführen, wenn in dem Modell Drillthrough aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="ec9b8-103">When you view a mining model by using the **Mining Model Viewer** tab of Data Mining Designer, you can drill through into details about the case data, provided the model has drillthrough enabled.</span></span> <span data-ttu-id="ec9b8-104">Wenn in der zugrunde liegenden Miningstruktur Drillthrough aktiviert ist, werden zudem in der Miningstruktur auch dann Spalten angezeigt, wenn diese Spalten nicht in dem Miningmodell enthalten waren.</span><span class="sxs-lookup"><span data-stu-id="ec9b8-104">Moreover, if the underlying mining structure has drillthrough enabled, you can also see columns in the mining structure, even if those columns were not included in the mining model.</span></span> <span data-ttu-id="ec9b8-105">In der Spaltenliste sind die Strukturspalten mit dem Präfix "Struktur"</span><span class="sxs-lookup"><span data-stu-id="ec9b8-105">In the column list, the structure columns are prefixed by the "Structure."</span></span> <span data-ttu-id="ec9b8-106">gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="ec9b8-106">label.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ec9b8-107">Sie können keinen Drillthrough auf einer vorhandenen Miningstruktur aktivieren.</span><span class="sxs-lookup"><span data-stu-id="ec9b8-107">You cannot enable drillthrough on an existing mining structure.</span></span> <span data-ttu-id="ec9b8-108">Stattdessen müssen Sie die Miningstruktur erneut erstellen und Drillthrough während des Erstellungsprozesses aktivieren.</span><span class="sxs-lookup"><span data-stu-id="ec9b8-108">Instead, you must re-create the mining structure and enable drillthrough during the creation process.</span></span>  
  
 <span data-ttu-id="ec9b8-109">Informationen über das Zugreifen auf Falldaten über die verschiedenen Miningmodell-Viewer, die Drillthrough unterstützen, **finden Sie unter** [Ausführen von Drillthroughs für Falldaten aus einem Miningmodell](data-mining/drill-through-to-case-data-from-a-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="ec9b8-109">For information about how to access case data from each of the mining model viewers that support drillthrough, **see** [Drill Through to Case Data from a Mining Model](data-mining/drill-through-to-case-data-from-a-mining-model.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="ec9b8-110">Tastatur</span><span class="sxs-lookup"><span data-stu-id="ec9b8-110">Options</span></span>  
 <span data-ttu-id="ec9b8-111">**Klassifizierte Fälle für**</span><span class="sxs-lookup"><span data-stu-id="ec9b8-111">**Cases Classified To**</span></span>  
 <span data-ttu-id="ec9b8-112">Zeigt die Definition der Regeln Itemset und Cluster an, die im ausgewählten Knoten enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="ec9b8-112">Displays the definition of the rule, itemset, and cluster that are contained in the selected node.</span></span>  
  
 <span data-ttu-id="ec9b8-113">**Spaltenliste**</span><span class="sxs-lookup"><span data-stu-id="ec9b8-113">**Column list**</span></span>  
 <span data-ttu-id="ec9b8-114">Zeigt die Spalten im Modell an, gefolgt von den Strukturspalten.</span><span class="sxs-lookup"><span data-stu-id="ec9b8-114">Displays the columns in the model, followed by the structure columns.</span></span>  
  
 <span data-ttu-id="ec9b8-115">**Hinweis** Strukturspalten werden nur angezeigt, wenn Drillthrough auf der Miningstruktur aktiviert ist und wenn Sie die Option **Model- und Strukturspalten**gewählt haben.</span><span class="sxs-lookup"><span data-stu-id="ec9b8-115">**Note** Structure columns are displayed only if drillthrough is enabled on the mining structure, and if you selected the option, **Model and Structure Columns**.</span></span> <span data-ttu-id="ec9b8-116">Um die Spalten anzuzeigen, müssen Drillthroughberechtigungen außerdem sowohl im Miningmodell als auch in der Miningstruktur aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="ec9b8-116">Moreover, you must have drillthrough permissions on both the mining model and the mining structure to view the columns.</span></span>  
  
 <span data-ttu-id="ec9b8-117">Struktur Spalten, die nicht im Modell enthalten sind, werden als **Struktur \<column name> .** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ec9b8-117">Structure columns that are not included in the model appear as **Structure.\<column name>**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ec9b8-118">Sie können an einer beliebigen Stelle im Spaltenraster mit der rechten Maustaste klicken und **Alle kopieren** auswählen, um die Drillthroughdaten in tabulatorgetrenntem Format in die Zwischenablage zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="ec9b8-118">You can right-click anywhere in the column grid and select **Copy All** to copy the drillthrough data, in tab-delimited format, to the Clipboard.</span></span> <span data-ttu-id="ec9b8-119">Die kopierten Daten enthalten nur die Falldaten, nicht die Knotendefinition.</span><span class="sxs-lookup"><span data-stu-id="ec9b8-119">The copied data includes only the case data, not the node definition.</span></span>  
  
 <span data-ttu-id="ec9b8-120">**Abspielen**</span><span class="sxs-lookup"><span data-stu-id="ec9b8-120">**Play**</span></span>  
 <span data-ttu-id="ec9b8-121">Klicken Sie auf die Schaltfläche mit dem grünen Pfeil, um die Daten zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="ec9b8-121">Click the green arrow button to refresh the data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec9b8-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ec9b8-122">See Also</span></span>  
 <span data-ttu-id="ec9b8-123">[Drillthrough-Abfragen &#40;Data Mining-&#41;](data-mining/drillthrough-queries-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="ec9b8-123">[Drillthrough Queries &#40;Data Mining&#41;](data-mining/drillthrough-queries-data-mining.md) </span></span>  
 <span data-ttu-id="ec9b8-124">[Mining Modell-Viewer &#40;Data Mining-Modell-Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="ec9b8-124">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="ec9b8-125">Tasks und Anweisungen für Miningmodell-Viewer</span><span class="sxs-lookup"><span data-stu-id="ec9b8-125">Mining Model Viewer Tasks and How-tos</span></span>](data-mining/mining-model-viewer-tasks-and-how-tos.md)  
  
  
