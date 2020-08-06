---
title: Mitglieder auswählen (Business Intelligence-Assistent) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.biwizard.currencyconversion.memberconversion.f1
ms.assetid: 1a147461-d594-41e7-a41d-09d2d003e1e0
author: minewiskan
ms.author: owend
ms.openlocfilehash: fd5f184e0d9670725609531b6d0a101f8e7f8647
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615627"
---
# <a name="select-members-business-intelligence-wizard"></a><span data-ttu-id="27159-102">Elemente auswählen (Business Intelligence-Assistent)</span><span class="sxs-lookup"><span data-stu-id="27159-102">Select Members (Business Intelligence Wizard)</span></span>
  <span data-ttu-id="27159-103">Mithilfe der Seite **Elemente auswählen** können Sie bestimmen, auf welche Elemente der Business Intelligence-Assistent die Währungsumrechnungsfunktion anwenden soll, die auf der Seite **Optionen für die Währungsumrechnung festlegen** angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="27159-103">Use the **Select Members** page to determine to which members the Business Intelligence Wizard should apply the currency conversion functionality specified on the **Set Currency Conversion Options** page.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="27159-104">Diese Seite wird nicht angezeigt, wenn der Business Intelligence-Assistent vom Dimensions-Designer aus oder durch Klicken mit der rechten Maustaste auf eine Dimension im Projektmappen-Explorer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="27159-104">This page does not appear if the Business Intelligence Wizard was started from Dimension Designer or by right-clicking a dimension in Solution Explorer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="27159-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="27159-105">Options</span></span>  
 <span data-ttu-id="27159-106">**Measuredimension**</span><span class="sxs-lookup"><span data-stu-id="27159-106">**Measures dimension**</span></span>  
 <span data-ttu-id="27159-107">Wählen Sie diese Option aus, um die Währungsumrechnungsfunktion auf ein oder mehrere Measures in dem Cube anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="27159-107">Select to apply the currency conversion functionality to one or more measures in the cube.</span></span>  
  
 <span data-ttu-id="27159-108">Wenn diese Option ausgewählt ist, werden im Raster die in der folgenden Tabelle aufgeführten Optionen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="27159-108">If selected, the grid displays the options listed in the following table.</span></span>  
  
|<span data-ttu-id="27159-109">Option</span><span class="sxs-lookup"><span data-stu-id="27159-109">Option</span></span>|<span data-ttu-id="27159-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="27159-110">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="27159-111">**Elemente auswählen**</span><span class="sxs-lookup"><span data-stu-id="27159-111">**Built-in Measure Types**</span></span>|<span data-ttu-id="27159-112">Wählen Sie diese Option aus, um die Währungsumrechnungsfunktion für das angegebene Measure einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="27159-112">Select to include currency conversion functionality for the specified measure.</span></span>|  
|<span data-ttu-id="27159-113">**Hilfs**</span><span class="sxs-lookup"><span data-stu-id="27159-113">**Measures**</span></span>|<span data-ttu-id="27159-114">Wählen Sie das Measure aus der Wechselkurs-Measuregruppe aus, das den Wechselkurs enthält, der beim Konvertieren des unter **Elemente auswählen** ausgewählten Measures verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="27159-114">Select the measure from the rate measure group that contains the exchange rate to use when the measure selected in **Built-in Measure Types** is converted.</span></span>|  
  
 <span data-ttu-id="27159-115">**Kontohierarchie**</span><span class="sxs-lookup"><span data-stu-id="27159-115">**Account hierarchy**</span></span>  
 <span data-ttu-id="27159-116">Wählen Sie diese Option aus, um die Währungsumrechnungsfunktion auf ein oder mehrere Elemente in der Kontohierarchie der Kontodimension anzuwenden, die im Cube enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="27159-116">Select to apply the currency conversion functionality to one or more members in the account hierarchy of the account dimension included in the cube.</span></span> <span data-ttu-id="27159-117">Die Konto Hierarchie ist die Hierarchie innerhalb der Konto Dimension, deren- `Type` Eigenschaft auf *Account*festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="27159-117">The account hierarchy is the hierarchy within the account dimension whose `Type` property is set to *Account*.</span></span>  
  
 <span data-ttu-id="27159-118">Wenn diese Option ausgewählt ist, werden im Raster die in der folgenden Tabelle aufgeführten Optionen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="27159-118">If selected, the grid displays the options listed in the following table.</span></span>  
  
|<span data-ttu-id="27159-119">Option</span><span class="sxs-lookup"><span data-stu-id="27159-119">Option</span></span>|<span data-ttu-id="27159-120">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="27159-120">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="27159-121">**Kontoelement**</span><span class="sxs-lookup"><span data-stu-id="27159-121">**Account Member**</span></span>|<span data-ttu-id="27159-122">Wählen Sie diese Option aus, um die Währungsumrechnungsfunktion für das angegebene Element der Kontohierarchie einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="27159-122">Select to include currency conversion functionality for the specified member of the account hierarchy.</span></span>|  
|<span data-ttu-id="27159-123">**Hilfs**</span><span class="sxs-lookup"><span data-stu-id="27159-123">**Measures**</span></span>|<span data-ttu-id="27159-124">Wählen Sie das Measure aus der Wechselkurs-Measuregruppe aus, das den Wechselkurs für die Konvertierung der Measures für das unter **Kontoelement** ausgewählte Element enthält.</span><span class="sxs-lookup"><span data-stu-id="27159-124">Select the measure from the rate measure group that contains the exchange rate to use when the measures for the member selected in **Account Member** are converted.</span></span>|  
  
 <span data-ttu-id="27159-125">**Kontohierarchie basierend auf Typ**</span><span class="sxs-lookup"><span data-stu-id="27159-125">**Account hierarchy based on type**</span></span>  
 <span data-ttu-id="27159-126">Wählen Sie diese Option aus, um die Währungsumrechnungsfunktion auf alle Elemente von Attributen in der Kontohierarchie anzuwenden, deren `Type`-Eigenschaft auf einen angegebenen Kontotyp festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="27159-126">Select to apply the currency conversion functionality to all members of attributes in the account hierarchy whose `Type` property is set to a specified account type.</span></span>  
  
 <span data-ttu-id="27159-127">Wenn diese Option ausgewählt ist, werden im Raster die in der folgenden Tabelle aufgeführten Optionen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="27159-127">If selected, the grid displays the options listed in the following table.</span></span>  
  
|<span data-ttu-id="27159-128">Option</span><span class="sxs-lookup"><span data-stu-id="27159-128">Option</span></span>|<span data-ttu-id="27159-129">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="27159-129">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="27159-130">**Kontotyp**</span><span class="sxs-lookup"><span data-stu-id="27159-130">**Account Type**</span></span>|<span data-ttu-id="27159-131">Wählen Sie diese Option aus, um die Währungsumrechnungsfunktion für den angegebenen Kontotyp einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="27159-131">Select to include currency conversion functionality for the specified account type.</span></span>|  
|<span data-ttu-id="27159-132">**Hilfs**</span><span class="sxs-lookup"><span data-stu-id="27159-132">**Measures**</span></span>|<span data-ttu-id="27159-133">Wählen Sie das Measure aus der Wechselkurs-Measuregruppe aus, das den Wechselkurs für die Konvertierung der Measures für die Elemente von Attributen enthält, die den unter **Kontotyp** ausgewählten Kontotypen verwenden.</span><span class="sxs-lookup"><span data-stu-id="27159-133">Select the measure from the rate measure group that contains the exchange rate to use when measures for the members of attributes using the account type selected in **Account Type** are converted.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="27159-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="27159-134">See Also</span></span>  
 <span data-ttu-id="27159-135">[Business Intelligence Wizard (F1-Hilfe)](business-intelligence-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="27159-135">[Business Intelligence Wizard F1 Help](business-intelligence-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="27159-136">[Cube-Designer &#40;Analysis Services Mehrdimensionale Daten&#41;](cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="27159-136">[Cube Designer &#40;Analysis Services - Multidimensional Data&#41;](cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="27159-137">Der Dimensions-Designer &#40;Analysis Services Mehrdimensionale Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="27159-137">Dimension Designer &#40;Analysis Services - Multidimensional Data&#41;</span></span>](dimension-designer-analysis-services-multidimensional-data.md)  
  
  
