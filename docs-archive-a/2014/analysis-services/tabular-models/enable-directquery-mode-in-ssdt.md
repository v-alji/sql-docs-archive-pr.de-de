---
title: Directquery-Entwurfs Modus aktivieren (SSAS-tabellarisch) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 71fc7ebd-2e86-4a76-994b-66d3a57bcc9b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8ccd2dc88f447e78f6558565a89accc341eac37c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618917"
---
# <a name="enable-directquery-design-mode-ssas-tabular"></a><span data-ttu-id="2ad71-102">Aktivieren des DirectQuery-Entwurfsmodus (SSAS – tabellarisch)</span><span class="sxs-lookup"><span data-stu-id="2ad71-102">Enable DirectQuery Design Mode (SSAS Tabular)</span></span>
  <span data-ttu-id="2ad71-103">Um im DirectQuery-Modus ein Modell zu erstellen, müssen Sie zuerst die Entwurfszeitumgebung ändern, damit sie den Benutzer des DirectQuery-Modus unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2ad71-103">To create a model in DirectQuery mode, you must first change the design-time environment so that it supports the user of DirectQuery mode.</span></span> <span data-ttu-id="2ad71-104">Wenn Sie so vorgehen, führt der Designer ebenfalls die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="2ad71-104">When you do so, the designer will also do the following:</span></span>  
  
-   <span data-ttu-id="2ad71-105">Aktivieren der Verwendung der DirectQuery-Bereitstellungseigenschaften.</span><span class="sxs-lookup"><span data-stu-id="2ad71-105">Enable the use of the DirectQuery deployment properties.</span></span>  
  
-   <span data-ttu-id="2ad71-106">Ändern der Arbeitsbereichsdatenbank für die Ausführung in einem Hybridmodus, der den Cache für Entwürfe verwendet.</span><span class="sxs-lookup"><span data-stu-id="2ad71-106">Change the workspace database to run in a hybrid mode that uses the cache for designing.</span></span> <span data-ttu-id="2ad71-107">Wenn Sie das Modell tatsächlich bereitstellen, wird der Modus wieder in den Wert geändert, der in den Projektbereitstellungseigenschaften angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="2ad71-107">When you actually deploy the model, the mode will be changed back to whatever value you specified in the project deployment properties.</span></span>  
  
-   <span data-ttu-id="2ad71-108">Deaktivieren der Entwurfsfunktionen, die mit dem DirectQuery-Modus nicht kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="2ad71-108">Disable design features that are incompatible with DirectQuery mode.</span></span>  
  
-   <span data-ttu-id="2ad71-109">Validieren des vorhandenen Modells.</span><span class="sxs-lookup"><span data-stu-id="2ad71-109">Validate the existing model.</span></span>  
  
 <span data-ttu-id="2ad71-110">Diese Prozedur beschreibt, wie der DirectQuery-Modus im Designer aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="2ad71-110">This procedure describes how to enable DirectQuery mode in the designer.</span></span>  
  
### <a name="to-enable-use-of-directquery-in-a-model"></a><span data-ttu-id="2ad71-111">So aktivieren Sie die Verwendung von DirectQuery in einem Modell</span><span class="sxs-lookup"><span data-stu-id="2ad71-111">To enable use of DirectQuery in a model</span></span>  
  
1.  <span data-ttu-id="2ad71-112">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] die Lösungsdatei.</span><span class="sxs-lookup"><span data-stu-id="2ad71-112">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the solution file.</span></span>  
  
2.  <span data-ttu-id="2ad71-113">Doppelklicken Sie in Objekt-Explorer auf die Datei "Model.bim".</span><span class="sxs-lookup"><span data-stu-id="2ad71-113">In Object Explorer, double-click the Model.bim file.</span></span>  
  
3.  <span data-ttu-id="2ad71-114">Ändern Sie im **Bereich** **Eigenschaften** die Eigenschaft **directquerymode**in ein.</span><span class="sxs-lookup"><span data-stu-id="2ad71-114">In the **Properties** pane, change the property, **DirectQueryMode**, to **On**.</span></span>  
  
4.  <span data-ttu-id="2ad71-115">Wenn Fehler vorhanden sind, öffnen Sie in Visual Studio die **Fehlerliste** , und beheben Sie alle Probleme, die verhindern würden, dass das Modell in den directquery-Modus gewechselt wird.</span><span class="sxs-lookup"><span data-stu-id="2ad71-115">If there are errors, in Visual Studio, open the **Error List** and resolve any problems that would prevent the model from being switched to DirectQuery mode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ad71-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2ad71-116">See Also</span></span>  
 [<span data-ttu-id="2ad71-117">DirectQuery-Modus &#40;SSAS – tabellarisch&#41;</span><span class="sxs-lookup"><span data-stu-id="2ad71-117">DirectQuery Mode &#40;SSAS Tabular&#41;</span></span>](directquery-mode-ssas-tabular.md)  
  
  
