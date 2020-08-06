---
title: Dimensions Eigenschaften (Dialog Feld) (Analysis Services-Mehrdimensionale Daten) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.sqlserverstudio.dimensionproperties.f1
helpviewer_keywords:
- Dimension Properties dialog box
ms.assetid: 7235d443-b2ce-4c53-b2eb-abceb28394bb
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0523220c76c11280165bc825c5c00c5eb9e23be6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622938"
---
# <a name="dimension-properties-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="9bb76-102">Dialogfeld 'Dimensionseigenschaften' (Analysis Services – Mehrdimensionale Daten)</span><span class="sxs-lookup"><span data-stu-id="9bb76-102">Dimension Properties Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="9bb76-103">Mithilfe des Dialogfelds **Dimensionseigenschaften** in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] können Sie die Eigenschaften einer Dimension in einer [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Datenbank festlegen.</span><span class="sxs-lookup"><span data-stu-id="9bb76-103">Use the **Dimension Properties** dialog box in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to set the properties of a dimension in an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="9bb76-104">Zum Anzeigen des Dialogfelds **Dimensionseigenschaften** klicken Sie im Objekt-Explorer mit der rechten Maustaste auf eine Dimension und wählen die Option **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="9bb76-104">You can display the **Dimension Properties** dialog box by right-clicking a dimension in Object Explorer and selecting **Properties**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="9bb76-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="9bb76-105">Options</span></span>  
  
|<span data-ttu-id="9bb76-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="9bb76-106">Term</span></span>|<span data-ttu-id="9bb76-107">Definition</span><span class="sxs-lookup"><span data-stu-id="9bb76-107">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="9bb76-108">**Name**</span><span class="sxs-lookup"><span data-stu-id="9bb76-108">**Name**</span></span>|<span data-ttu-id="9bb76-109">Zeigt den Namen der Dimension an.</span><span class="sxs-lookup"><span data-stu-id="9bb76-109">Displays the name of the dimension.</span></span>|  
|<span data-ttu-id="9bb76-110">**ID**</span><span class="sxs-lookup"><span data-stu-id="9bb76-110">**ID**</span></span>|<span data-ttu-id="9bb76-111">Zeigt den Bezeichner der Dimension an.</span><span class="sxs-lookup"><span data-stu-id="9bb76-111">Displays the identifier of the dimension.</span></span>|  
|<span data-ttu-id="9bb76-112">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="9bb76-112">**Description**</span></span>|<span data-ttu-id="9bb76-113">Zeigt die Beschreibung einer Dimension an.</span><span class="sxs-lookup"><span data-stu-id="9bb76-113">Displays the description of the dimension.</span></span>|  
|<span data-ttu-id="9bb76-114">**Timestamp erstellen**</span><span class="sxs-lookup"><span data-stu-id="9bb76-114">**Create Timestamp**</span></span>|<span data-ttu-id="9bb76-115">Zeigt das Datum und die Uhrzeit der Erstellung der Dimension an.</span><span class="sxs-lookup"><span data-stu-id="9bb76-115">Displays the date and time the dimension was created.</span></span>|  
|<span data-ttu-id="9bb76-116">**Letztes Schemaupdate**</span><span class="sxs-lookup"><span data-stu-id="9bb76-116">**Last Schema Update**</span></span>|<span data-ttu-id="9bb76-117">Zeigt das Datum und die Uhrzeit des letzten Updates der Metadaten für die Dimension an.</span><span class="sxs-lookup"><span data-stu-id="9bb76-117">Displays the date and time the metadata for the dimension was last updated.</span></span>|  
|<span data-ttu-id="9bb76-118">**Verarbeitungsmodus**</span><span class="sxs-lookup"><span data-stu-id="9bb76-118">**Processing Mode**</span></span>|<span data-ttu-id="9bb76-119">Wählen Sie den für die Dimension zu verwendenden Verarbeitungsmodus aus.</span><span class="sxs-lookup"><span data-stu-id="9bb76-119">Select the processing mode to use for the dimension.</span></span> <span data-ttu-id="9bb76-120">Weitere Informationen zu den Werten für diese Eigenschaft finden Sie unter <xref:Microsoft.AnalysisServices.Dimension.ProcessingMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="9bb76-120">For more information about the values for this property, see <xref:Microsoft.AnalysisServices.Dimension.ProcessingMode%2A>.</span></span>|  
|<span data-ttu-id="9bb76-121">**State**</span><span class="sxs-lookup"><span data-stu-id="9bb76-121">**State**</span></span>|<span data-ttu-id="9bb76-122">Zeigt den Verarbeitungsstatus der Dimension an.</span><span class="sxs-lookup"><span data-stu-id="9bb76-122">Displays the processing state of the dimension.</span></span> <span data-ttu-id="9bb76-123">Weitere Informationen zu den Werten für diese Eigenschaft finden Sie unter <xref:Microsoft.AnalysisServices.ProcessableMajorObject.State%2A>.</span><span class="sxs-lookup"><span data-stu-id="9bb76-123">For more information about the values for this property, see <xref:Microsoft.AnalysisServices.ProcessableMajorObject.State%2A>.</span></span>|  
|<span data-ttu-id="9bb76-124">**Zuletzt verarbeitet**</span><span class="sxs-lookup"><span data-stu-id="9bb76-124">**Last Processed**</span></span>|<span data-ttu-id="9bb76-125">Zeigt das Datum und die Uhrzeit an, zu der die Dimension zuletzt verarbeitet wurde.</span><span class="sxs-lookup"><span data-stu-id="9bb76-125">Displays the date and time the dimension was last processed.</span></span>|  
|<span data-ttu-id="9bb76-126">**Aktueller Speichermodus**</span><span class="sxs-lookup"><span data-stu-id="9bb76-126">**Current Storage Mode**</span></span>|<span data-ttu-id="9bb76-127">Zeigt den aktuellen Speichermodus der Dimension an.</span><span class="sxs-lookup"><span data-stu-id="9bb76-127">Displays the current storage mode for the dimension.</span></span> <span data-ttu-id="9bb76-128">Weitere Informationen zu den Werten für diese Eigenschaft finden Sie unter <xref:Microsoft.AnalysisServices.Dimension.CurrentStorageMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="9bb76-128">For more information about the values for this property, see <xref:Microsoft.AnalysisServices.Dimension.CurrentStorageMode%2A>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9bb76-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9bb76-129">See Also</span></span>  
 <span data-ttu-id="9bb76-130">[Analysis Services Designer und Dialog Felder &#40;Mehrdimensionale Daten&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="9bb76-130">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="9bb76-131">Dimensionen &#40;Analysis Services – mehrdimensionale Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="9bb76-131">Dimensions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md)  
  
  
