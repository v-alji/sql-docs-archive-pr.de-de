---
title: Auswirkungs Analyse (Dialog Feld) (Analysis Services-Mehrdimensionale Daten) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.process.impactanalysisdialog.f1
ms.assetid: 208268eb-4e14-44db-9c64-6f74b776adb6
author: minewiskan
ms.author: owend
ms.openlocfilehash: e47ab806b9bd10afc812113b69fe0849437068b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696289"
---
# <a name="impact-analysis-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="7f1a3-102">Dialogfeld 'Auswirkungsanalyse' (Analysis Services – Mehrdimensionale Daten)</span><span class="sxs-lookup"><span data-stu-id="7f1a3-102">Impact Analysis Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="7f1a3-103">Mithilfe des Dialogfelds **Auswirkungsanalyse** in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] und [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] können Sie abhängige Objekte identifizieren und optional verarbeiten, auf die sich das Verarbeiten der im Dialogfeld **Verarbeiten** aufgeführten Objekte auswirkt.</span><span class="sxs-lookup"><span data-stu-id="7f1a3-103">Use the **Impact Analysis** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] and [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to identify and optionally process dependent objects that are affected if the objects listed in the **Process** dialog box are processed.</span></span> <span data-ttu-id="7f1a3-104">Zum Anzeigen des Dialogfelds **Auswirkungsanalyse** klicken Sie im Dialogfeld **Verarbeiten** auf **Auswirkungsanalyse** .</span><span class="sxs-lookup"><span data-stu-id="7f1a3-104">You can display the **Impact Analysis** dialog box by clicking **Impact Analysis** from the **Process** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7f1a3-105">Ein Objekt wird mehrfach angezeigt, wenn es auf mehr als eine Weise betroffen ist.</span><span class="sxs-lookup"><span data-stu-id="7f1a3-105">An object appears more than once if it is affected in more than one way.</span></span>  
  
## <a name="options"></a><span data-ttu-id="7f1a3-106">Tastatur</span><span class="sxs-lookup"><span data-stu-id="7f1a3-106">Options</span></span>  
 <span data-ttu-id="7f1a3-107">**Objektliste**</span><span class="sxs-lookup"><span data-stu-id="7f1a3-107">**Object list**</span></span>  
 <span data-ttu-id="7f1a3-108">Zeigt eine Liste abhängiger Objekte in einem Raster an.</span><span class="sxs-lookup"><span data-stu-id="7f1a3-108">Displays a list of dependent objects in a grid.</span></span> <span data-ttu-id="7f1a3-109">Das Raster enthält die folgenden Spalten:</span><span class="sxs-lookup"><span data-stu-id="7f1a3-109">The grid contains the following columns:</span></span>  
  
 <span data-ttu-id="7f1a3-110">**Objektnamen**</span><span class="sxs-lookup"><span data-stu-id="7f1a3-110">**Object Name**</span></span>  
 <span data-ttu-id="7f1a3-111">Zeigt den Namen des abhängigen Objekts an, das ggf. verarbeitet werden muss.</span><span class="sxs-lookup"><span data-stu-id="7f1a3-111">Displays the name of the dependent object that may need to be processed.</span></span> <span data-ttu-id="7f1a3-112">Das Symbol links vom Namen gibt den Objekttyp an.</span><span class="sxs-lookup"><span data-stu-id="7f1a3-112">The icon to the left of the name indicates the object type.</span></span>  
  
 <span data-ttu-id="7f1a3-113">**Type**</span><span class="sxs-lookup"><span data-stu-id="7f1a3-113">**Type**</span></span>  
 <span data-ttu-id="7f1a3-114">Zeigt den Typ des abhängigen Objekts an, das ggf. verarbeitet werden muss.</span><span class="sxs-lookup"><span data-stu-id="7f1a3-114">Displays the type of dependent object that may need to be processed.</span></span>  
  
 <span data-ttu-id="7f1a3-115">**Auswirkungstyp**</span><span class="sxs-lookup"><span data-stu-id="7f1a3-115">**Impact Type**</span></span>  
 <span data-ttu-id="7f1a3-116">Zeigt die Auswirkung an, die das Verarbeiten der Objekte im Dialogfeld **Verarbeiten** auf das abhängige Objekt hat.</span><span class="sxs-lookup"><span data-stu-id="7f1a3-116">Displays the effect that processing the objects in the **Process** dialog box has on the dependent object.</span></span> <span data-ttu-id="7f1a3-117">Die folgende Tabelle führt die möglichen Auswirkungen der Verarbeitung auf und gibt an, ob eine Auswirkung zu einer Warnung oder einem Fehler führt.</span><span class="sxs-lookup"><span data-stu-id="7f1a3-117">The following table lists the possible effects of processing and notes whether each one results in a warning or an error.</span></span>  
  
|<span data-ttu-id="7f1a3-118">Auswirkung</span><span class="sxs-lookup"><span data-stu-id="7f1a3-118">Impact</span></span>|<span data-ttu-id="7f1a3-119">Meldung</span><span class="sxs-lookup"><span data-stu-id="7f1a3-119">Message</span></span>|  
|------------|-------------|  
|<span data-ttu-id="7f1a3-120">Objekt wird gelöscht (keine Verarbeitung)</span><span class="sxs-lookup"><span data-stu-id="7f1a3-120">Object will be cleared (unprocessed)</span></span>|<span data-ttu-id="7f1a3-121">Warnung</span><span class="sxs-lookup"><span data-stu-id="7f1a3-121">Warning</span></span>|  
|<span data-ttu-id="7f1a3-122">Objekt wäre ungültig</span><span class="sxs-lookup"><span data-stu-id="7f1a3-122">Object would be invalid</span></span>|<span data-ttu-id="7f1a3-123">Fehler</span><span class="sxs-lookup"><span data-stu-id="7f1a3-123">Error</span></span>|  
|<span data-ttu-id="7f1a3-124">Aggregation würde gelöscht</span><span class="sxs-lookup"><span data-stu-id="7f1a3-124">Aggregation would be dropped</span></span>|<span data-ttu-id="7f1a3-125">Warnung</span><span class="sxs-lookup"><span data-stu-id="7f1a3-125">Warning</span></span>|  
|<span data-ttu-id="7f1a3-126">Flexible Aggregation würde gelöscht</span><span class="sxs-lookup"><span data-stu-id="7f1a3-126">Flexible aggregation would be dropped</span></span>|<span data-ttu-id="7f1a3-127">Warnung</span><span class="sxs-lookup"><span data-stu-id="7f1a3-127">Warning</span></span>|  
|<span data-ttu-id="7f1a3-128">Indizes werden gelöscht</span><span class="sxs-lookup"><span data-stu-id="7f1a3-128">Indexes will be dropped</span></span>|<span data-ttu-id="7f1a3-129">Warnung</span><span class="sxs-lookup"><span data-stu-id="7f1a3-129">Warning</span></span>|  
|<span data-ttu-id="7f1a3-130">Nicht untergeordnetes Objekt wird verarbeitet</span><span class="sxs-lookup"><span data-stu-id="7f1a3-130">Non-child object will be processed</span></span>|<span data-ttu-id="7f1a3-131">Warnung</span><span class="sxs-lookup"><span data-stu-id="7f1a3-131">Warning</span></span>|  
  
 <span data-ttu-id="7f1a3-132">**Objekt verarbeiten**</span><span class="sxs-lookup"><span data-stu-id="7f1a3-132">**Process Object**</span></span>  
 <span data-ttu-id="7f1a3-133">Wählen Sie die abhängigen Objekte aus, die Sie mit dem Verarbeitungsvorgang verarbeiten möchten</span><span class="sxs-lookup"><span data-stu-id="7f1a3-133">Select the dependent objects that you want to process with the processing operation.</span></span> <span data-ttu-id="7f1a3-134">Nicht ausgewählte abhängige Objekte müssen verarbeitet werden, nachdem der Verarbeitungsvorgang abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="7f1a3-134">Dependent objects that are not selected must be processed after the processing operation is finished.</span></span> <span data-ttu-id="7f1a3-135">Andernfalls können sie nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7f1a3-135">Otherwise, they cannot be used.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f1a3-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7f1a3-136">See Also</span></span>  
 <span data-ttu-id="7f1a3-137">[Analysis Services Designer und Dialog Felder &#40;Mehrdimensionale Daten&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="7f1a3-137">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="7f1a3-138">Verarbeiten (Dialog Feld) &#40;Analysis Services-mehrdimensionalen Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="7f1a3-138">Process Dialog Box &#40;Analysis Services - Multidimensional Data&#41;</span></span>](process-dialog-box-analysis-services-multidimensional-data.md)  
  
  
