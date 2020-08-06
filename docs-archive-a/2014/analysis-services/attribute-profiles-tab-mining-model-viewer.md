---
title: Registerkarte "Attribut profile" (Mining Modell-Viewer) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.naivebayse.profiles.f1
ms.assetid: 17c7e7ae-273c-4a6b-9a35-e8b9b8e65999
author: minewiskan
ms.author: owend
ms.openlocfilehash: 61c81b95f030bf1a69aed165bd64e58ff9af8339
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610368"
---
# <a name="attribute-profiles-tab-mining-model-viewer"></a><span data-ttu-id="e1919-102">Registerkarte "Attributprofile" (Miningmodell-Viewer)</span><span class="sxs-lookup"><span data-stu-id="e1919-102">Attribute Profiles Tab (Mining Model Viewer)</span></span>
  <span data-ttu-id="e1919-103">Mit der Registerkarte **Attributprofile** können Sie anzeigen, welche Auswirkungen die Verteilung der Eingabewerte in einem Naive Bayes-Modellstatus auf die einzelnen Status des Ergebnisattributs hat.</span><span class="sxs-lookup"><span data-stu-id="e1919-103">Use the **Attribute Profiles** tab to see how the distribution of input values in a Naive Bayes model state contribute to each state of the outcome attribute.</span></span> <span data-ttu-id="e1919-104">Die Verteilung der Werte wird als farbiges Histogramm angezeigt, und alle Verteilungen werden in einem Tabellenformat dargestellt, um das Vergleichen der Werte zu erleichtern.</span><span class="sxs-lookup"><span data-stu-id="e1919-104">The distribution of values is shown as a colored histogram, all distributions presented in a tabular format, to make it easier to compare values.</span></span>  
  
 <span data-ttu-id="e1919-105">**Weitere Informationen:** [Microsoft Naive Bayes-Algorithmus](data-mining/microsoft-naive-bayes-algorithm.md), [Durchsuchen eines Modells mit dem Microsoft Naive Bayes-Viewer](data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="e1919-105">**For More Information:** [Microsoft Naive Bayes Algorithm](data-mining/microsoft-naive-bayes-algorithm.md), [Browse a Model Using the Microsoft Naive Bayes Viewer](data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="e1919-106">Tastatur</span><span class="sxs-lookup"><span data-stu-id="e1919-106">Options</span></span>  
 <span data-ttu-id="e1919-107">**Viewerinhalt aktualisieren**</span><span class="sxs-lookup"><span data-stu-id="e1919-107">**Refresh viewer content**</span></span>  
 <span data-ttu-id="e1919-108">Lädt das Miningmodell im Viewer neu.</span><span class="sxs-lookup"><span data-stu-id="e1919-108">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="e1919-109">**Mining Modell**</span><span class="sxs-lookup"><span data-stu-id="e1919-109">**Mining Model**</span></span>  
 <span data-ttu-id="e1919-110">Wählen Sie ein anzuzeigendes Miningmodell aus der aktuellen Miningstruktur aus.</span><span class="sxs-lookup"><span data-stu-id="e1919-110">Choose a mining model to view, from those in the current mining structure.</span></span> <span data-ttu-id="e1919-111">Das Miningmodell wird im dazugehörigen Viewer geöffnet.</span><span class="sxs-lookup"><span data-stu-id="e1919-111">The mining model will open in its associated viewer.</span></span>  
  
 <span data-ttu-id="e1919-112">**Viewer**</span><span class="sxs-lookup"><span data-stu-id="e1919-112">**Viewer**</span></span>  
 <span data-ttu-id="e1919-113">Wählen Sie den Viewer aus, der zum Durchsuchen des ausgewählten Miningmodells verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e1919-113">Choose a viewer to use to explore the selected mining model.</span></span> <span data-ttu-id="e1919-114">Sie können den für jedes Miningmodell bereitgestellten benutzerdefinierten Viewer oder den [!INCLUDE[msCoName](../includes/msconame-md.md)] -Viewer für Mininginhalte auswählen.</span><span class="sxs-lookup"><span data-stu-id="e1919-114">You can choose the custom viewer provided for each mining model, or the [!INCLUDE[msCoName](../includes/msconame-md.md)] Mining Content Viewer.</span></span> <span data-ttu-id="e1919-115">Sie können auch Plug-In-Viewer verwenden, wenn diese verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="e1919-115">You can also use plug-in viewers if they are available.</span></span>  
  
 <span data-ttu-id="e1919-116">**Legende anzeigen**</span><span class="sxs-lookup"><span data-stu-id="e1919-116">**Show Legend**</span></span>  
 <span data-ttu-id="e1919-117">Wählen Sie diese Option aus, um einen Schlüssel anzuzeigen, der jeden Wert in **Status** einer der im Verteilungsdiagramm verwendeten Farben zuordnet.</span><span class="sxs-lookup"><span data-stu-id="e1919-117">Select this option to display a key that matches each value in **States** to one of the colors used in the distribution chart.</span></span>  
  
 <span data-ttu-id="e1919-118">**Histogrammbalken**</span><span class="sxs-lookup"><span data-stu-id="e1919-118">**Histogram bars**</span></span>  
 <span data-ttu-id="e1919-119">Wählen Sie aus, wie viele Balken das Histogramm enthalten soll.</span><span class="sxs-lookup"><span data-stu-id="e1919-119">Select how many bars to include in the histogram.</span></span> <span data-ttu-id="e1919-120">Sind mehr Balken vorhanden, als Sie für die Anzeige ausgewählt haben, werden die wichtigsten Balken beibehalten, und die restlichen Balken werden unter **Sonstige**gruppiert.</span><span class="sxs-lookup"><span data-stu-id="e1919-120">If more bars exist than you choose to display, the bars of highest importance are retained, and the remaining bars are grouped together into **Other**.</span></span>  
  
 <span data-ttu-id="e1919-121">**Vorhersagbar**</span><span class="sxs-lookup"><span data-stu-id="e1919-121">**Predictable**</span></span>  
 <span data-ttu-id="e1919-122">Wählen Sie eine vorhersagbare Spalte aus dem Miningmodell aus.</span><span class="sxs-lookup"><span data-stu-id="e1919-122">Select a predictable column from the mining model.</span></span>  
  
 <span data-ttu-id="e1919-123">**Attribut profile**</span><span class="sxs-lookup"><span data-stu-id="e1919-123">**Attribute Profiles**</span></span>  
 <span data-ttu-id="e1919-124">Die Tabelle umfasst die folgenden Spalten:</span><span class="sxs-lookup"><span data-stu-id="e1919-124">The table contains the following columns:</span></span>  
  
|<span data-ttu-id="e1919-125">Wert</span><span class="sxs-lookup"><span data-stu-id="e1919-125">Value</span></span>|<span data-ttu-id="e1919-126">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e1919-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e1919-127">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="e1919-127">**Attributes**</span></span>|<span data-ttu-id="e1919-128">Listet die Miningmodellspalten auf, die im Miningmodell enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="e1919-128">Lists the mining model columns contained within the mining model.</span></span>|  
|<span data-ttu-id="e1919-129">**Status**</span><span class="sxs-lookup"><span data-stu-id="e1919-129">**States**</span></span>|<span data-ttu-id="e1919-130">Eine optionale Spalte, die beschreibt, welchen Status die Farbe der entsprechenden Zeile von Attributen darstellt.</span><span class="sxs-lookup"><span data-stu-id="e1919-130">An optional column that describes what state the color in the corresponding row of attributes represents.</span></span> <span data-ttu-id="e1919-131">Verwenden Sie zum Hinzufügen oder Entfernen das Kontrollkästchen **Legende anzeigen** .</span><span class="sxs-lookup"><span data-stu-id="e1919-131">Add or remove by using the **Show Legend** check box.</span></span>|  
|<span data-ttu-id="e1919-132">**Bevölkerungs**</span><span class="sxs-lookup"><span data-stu-id="e1919-132">**Population**</span></span>|<span data-ttu-id="e1919-133">Zeigt die Verteilung der Attribute über das gesamte Dataset an.</span><span class="sxs-lookup"><span data-stu-id="e1919-133">Displays the distribution of the attribute across the whole dataset.</span></span>|  
|<span data-ttu-id="e1919-134">**Spalte für Status des vorhersagbaren Attributs**</span><span class="sxs-lookup"><span data-stu-id="e1919-134">**Column for states of predictable attribute**</span></span>|<span data-ttu-id="e1919-135">Zeigt eine Spalte für jeden Status der vorhersagbaren Spalte an; dabei entspricht jede Zeile einem Eingabeattribut im Modell.</span><span class="sxs-lookup"><span data-stu-id="e1919-135">Displays a column for each state of the predictable column, with each row corresponding to an input attribute in the model.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e1919-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e1919-136">See Also</span></span>  
 <span data-ttu-id="e1919-137">[Data Mining-Algorithmen &#40;Analysis Services Data Mining-&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="e1919-137">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="e1919-138">[Mining Modell-Viewer &#40;Data Mining-Modell-Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="e1919-138">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="e1919-139">Data Mining-Modell-Viewer</span><span class="sxs-lookup"><span data-stu-id="e1919-139">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
