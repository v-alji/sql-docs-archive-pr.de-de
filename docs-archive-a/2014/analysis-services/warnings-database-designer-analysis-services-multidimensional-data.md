---
title: Warnungen (Datenbank-Designer) (Analysis Services-Mehrdimensionale Daten) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.databasedesigner.warnings.f1
ms.assetid: 13f58b4d-f345-4fbc-ae2d-b3c8290a797d
author: minewiskan
ms.author: owend
ms.openlocfilehash: bf635460187fe56f4811de5090cada002ea8ca3b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616191"
---
# <a name="warnings-database-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="9f5c6-102">Warnungen (Datenbank-Designer) (Analysis Services – Mehrdimensionale Daten)</span><span class="sxs-lookup"><span data-stu-id="9f5c6-102">Warnings (Database Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="9f5c6-103">Mithilfe der Registerkarte **Warnungen** können Sie Regeln anzeigen und global verwerfen sowie bestimmte Instanzen verworfener Warnungen anzeigen und erneut aktivieren.</span><span class="sxs-lookup"><span data-stu-id="9f5c6-103">Use the **Warnings** tab to view and dismiss rules globally, and to view and re-enable specific instances of dismissed warnings.</span></span> <span data-ttu-id="9f5c6-104">Die Registerkarte **Warnungen** enthält zwei Raster: **Entwurfswarnungsregeln** und **Verworfene Warnungen**.</span><span class="sxs-lookup"><span data-stu-id="9f5c6-104">The **Warnings** tab displays two grids: **Design Warning Rules** and **Dismissed Warnings**.</span></span>  
  
 <span data-ttu-id="9f5c6-105">**So zeigen Sie die Registerkarte Warnungen an**</span><span class="sxs-lookup"><span data-stu-id="9f5c6-105">**To display the Warnings tab**</span></span>  
  
1.  <span data-ttu-id="9f5c6-106">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]ein [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Projekt.</span><span class="sxs-lookup"><span data-stu-id="9f5c6-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project.</span></span>  
  
2.  <span data-ttu-id="9f5c6-107">Klicken Sie im **Projektmappen-Explorer**mit der rechten Maustaste auf das [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Projekt, klicken Sie auf **Datenbank bearbeiten**und anschließend auf die Registerkarte **Warnungen** .</span><span class="sxs-lookup"><span data-stu-id="9f5c6-107">In **Solution Explorer**, right-click the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, click **Edit Database**, and then click the **Warnings** tab.</span></span>  
  
## <a name="design-warning-rules-grid"></a><span data-ttu-id="9f5c6-108">Raster Entwurfswarnungsregeln</span><span class="sxs-lookup"><span data-stu-id="9f5c6-108">Design Warning Rules Grid</span></span>  
 <span data-ttu-id="9f5c6-109">Das Raster **Entwurfswarnungsregeln** enthält alle Entwurfswarnungsregeln.</span><span class="sxs-lookup"><span data-stu-id="9f5c6-109">The **Design Warning Rules** grid displays all the design warning rules.</span></span> <span data-ttu-id="9f5c6-110">Mit diesem Raster wird auch gesteuert, welche Regeln für die Datenbank aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="9f5c6-110">This grid also controls which rules are enabled for the database.</span></span> <span data-ttu-id="9f5c6-111">Um eine Warnregel zu aktivieren oder zu deaktivieren, aktivieren bzw. deaktivieren das zugehörige Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="9f5c6-111">To enable or disable a warning rule, select or clear its check box.</span></span>  
  
 <span data-ttu-id="9f5c6-112">Das Raster **Entwurfswarnungsregeln** weist die folgenden Spalten auf:</span><span class="sxs-lookup"><span data-stu-id="9f5c6-112">The **Design Warning Rules** grid has the following columns:</span></span>  
  
 <span data-ttu-id="9f5c6-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="9f5c6-113">**Description**</span></span>  
 <span data-ttu-id="9f5c6-114">Zeigt den Namen der Regel an.</span><span class="sxs-lookup"><span data-stu-id="9f5c6-114">Displays the name of the rule.</span></span> <span data-ttu-id="9f5c6-115">Regeln werden nach Kategorien gruppiert.</span><span class="sxs-lookup"><span data-stu-id="9f5c6-115">Rules are grouped by category.</span></span>  
  
 <span data-ttu-id="9f5c6-116">**Wichtigkeit**</span><span class="sxs-lookup"><span data-stu-id="9f5c6-116">**Importance**</span></span>  
 <span data-ttu-id="9f5c6-117">Zeigt die der Regel zugewiesene Wichtigkeit an.</span><span class="sxs-lookup"><span data-stu-id="9f5c6-117">Displays the importance assigned to the rule.</span></span>  
  
 <span data-ttu-id="9f5c6-118">**Kommentare**</span><span class="sxs-lookup"><span data-stu-id="9f5c6-118">**Comments**</span></span>  
 <span data-ttu-id="9f5c6-119">(Optional) Ermöglicht es dem Benutzer, einen Kommentar einzugeben, der erklärt, warum die Warnung verworfen wurde.</span><span class="sxs-lookup"><span data-stu-id="9f5c6-119">(Optional) Allows the user to type a comment that explains why you are dismissing the warning.</span></span>  
  
## <a name="dismissed-warnings-grid"></a><span data-ttu-id="9f5c6-120">Raster Verworfene Warnungen</span><span class="sxs-lookup"><span data-stu-id="9f5c6-120">Dismissed Warnings Grid</span></span>  
 <span data-ttu-id="9f5c6-121">Das Raster **Verworfene Warnungen** enthält die einzelnen Warnungen, die aus der **Fehlerliste**entfernt wurden.</span><span class="sxs-lookup"><span data-stu-id="9f5c6-121">The **Dismissed Warnings** grid displays all specific warning occurrences that have been dismissed from the **Error List**.</span></span> <span data-ttu-id="9f5c6-122">Um eine Warnung erneut zu aktivieren, markieren Sie sie im Raster, und klicken Sie dann auf **Erneut aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="9f5c6-122">To re-enable a warning, select it in the grid, and then click **Re-enable**.</span></span>  
  
 <span data-ttu-id="9f5c6-123">Das Raster **Verworfene Warnungen** umfasst folgende Elemente:</span><span class="sxs-lookup"><span data-stu-id="9f5c6-123">The **Dismissed Warnings** grid has the following :</span></span>  
  
 <span data-ttu-id="9f5c6-124">**Object**</span><span class="sxs-lookup"><span data-stu-id="9f5c6-124">**Object**</span></span>  
 <span data-ttu-id="9f5c6-125">Zeigt ein Symbol an, das den Objekttyp und den Objektnamen darstellt.</span><span class="sxs-lookup"><span data-stu-id="9f5c6-125">Displays an icon that represents the object type and the object name.</span></span>  
  
 <span data-ttu-id="9f5c6-126">**Type**</span><span class="sxs-lookup"><span data-stu-id="9f5c6-126">**Type**</span></span>  
 <span data-ttu-id="9f5c6-127">Zeigt den Objekttyp an.</span><span class="sxs-lookup"><span data-stu-id="9f5c6-127">Displays the object type.</span></span>  
  
 <span data-ttu-id="9f5c6-128">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="9f5c6-128">**Description**</span></span>  
 <span data-ttu-id="9f5c6-129">Zeigt den Namen der Regel an.</span><span class="sxs-lookup"><span data-stu-id="9f5c6-129">Displays the name of the rule.</span></span>  
  
 <span data-ttu-id="9f5c6-130">**Wichtigkeit**</span><span class="sxs-lookup"><span data-stu-id="9f5c6-130">**Importance**</span></span>  
 <span data-ttu-id="9f5c6-131">Zeigt die der Regel zugewiesene Wichtigkeit an.</span><span class="sxs-lookup"><span data-stu-id="9f5c6-131">Displays the importance assigned to the rule.</span></span>  
  
 <span data-ttu-id="9f5c6-132">**Kommentare**</span><span class="sxs-lookup"><span data-stu-id="9f5c6-132">**Comments**</span></span>  
 <span data-ttu-id="9f5c6-133">Zeigt den Kommentar an, der eingegeben wurde, als die Warnung verworfen wurde.</span><span class="sxs-lookup"><span data-stu-id="9f5c6-133">Displays the comment that was entered when the warning was dismissed.</span></span> <span data-ttu-id="9f5c6-134">Sie können hier einen Kommentar hinzufügen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="9f5c6-134">You can add or modify a comment here.</span></span>  
  
 <span data-ttu-id="9f5c6-135">**Erneut aktivieren**</span><span class="sxs-lookup"><span data-stu-id="9f5c6-135">**Re-enable**</span></span>  
 <span data-ttu-id="9f5c6-136">Aktiviert die ausgewählten Warnungen erneut.</span><span class="sxs-lookup"><span data-stu-id="9f5c6-136">Re-enables the selected warnings.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9f5c6-137">Wenn ein Objekt über eine Warnung verfügt, sich das Objekt aber in einem ungültigen Zustand befindet oder von Hand aus dem Projekt entfernt wurde, wird in der Liste ein Fehlersymbol neben der Warnung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9f5c6-137">If an object has a warning, but the object is in an invalid state or was manually removed from the project, an error icon appears next to the warning in the list.</span></span> <span data-ttu-id="9f5c6-138">Um die Warnung zu verwerfen, wählen Sie das Objekt aus, und klicken Sie anschließend auf **Erneut aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="9f5c6-138">To dismiss the warning, select it and then click **Re-enable**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f5c6-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9f5c6-139">See Also</span></span>  
 <span data-ttu-id="9f5c6-140">[Dialog Feld "Warnung verwerfen" &#40;Analysis Services-Mehrdimensionale Daten&#41;](dismiss-warning-dialog-box-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="9f5c6-140">[Dismiss Warning Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](dismiss-warning-dialog-box-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="9f5c6-141">Allgemeine &#40;Daten Bank Designer&#41; &#40;Analysis Services Mehrdimensionale Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="9f5c6-141">General &#40;Database Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](general-database-designer-analysis-services-multidimensional-data.md)  
  
  
