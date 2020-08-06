---
title: Zieladapter für Dimensionsverarbeitung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dimensionprocessingdest.f1
helpviewer_keywords:
- Dimension Processing destination
- loading dimensions
- destinations [Integration Services], Dimension Processing
- dimensions [Analysis Services], processing
ms.assetid: 4c49bb95-7259-42f4-a785-bb6aaf5f8566
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 61cde87ac4fa5fcb1352491d787674447dd404b3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615492"
---
# <a name="dimension-processing-destination"></a><span data-ttu-id="76be0-102">Ziel für Dimensionsverarbeitung</span><span class="sxs-lookup"><span data-stu-id="76be0-102">Dimension Processing Destination</span></span>
  <span data-ttu-id="76be0-103">Das Ziel für Dimensionsverarbeitung lädt und verarbeitet eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]-Dimension.</span><span class="sxs-lookup"><span data-stu-id="76be0-103">The Dimension Processing destination loads and processes an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] dimension.</span></span> <span data-ttu-id="76be0-104">Weitere Informationen zu Dimensionen finden Sie unter [Dimensionen &#40;Analysis Services – Mehrdimensionale Daten&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data).</span><span class="sxs-lookup"><span data-stu-id="76be0-104">For more information about dimensions, see [Dimensions &#40;Analysis Services - Multidimensional Data&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data).</span></span>  
  
 <span data-ttu-id="76be0-105">Das Ziel für Dimensionsverarbeitung schließt die folgenden Funktionen ein:</span><span class="sxs-lookup"><span data-stu-id="76be0-105">The Dimension Processing destination includes the following features:</span></span>  
  
-   <span data-ttu-id="76be0-106">Optionen für die inkrementelle Verarbeitung, vollständige Verarbeitung oder Updateverarbeitung.</span><span class="sxs-lookup"><span data-stu-id="76be0-106">Options to perform incremental, full, or update processing.</span></span>  
  
-   <span data-ttu-id="76be0-107">Fehlerkonfiguration, um anzugeben, ob die Dimensionsverarbeitung Fehler ignoriert oder nach einer bestimmten Anzahl von Fehlern beendet wird.</span><span class="sxs-lookup"><span data-stu-id="76be0-107">Error configuration, to specify whether dimension processing ignores errors or stops after a specified number of errors.</span></span>  
  
-   <span data-ttu-id="76be0-108">Zuordnung von Eingabespalten zu Spalten in Dimensionstabellen.</span><span class="sxs-lookup"><span data-stu-id="76be0-108">Mapping of input columns to columns in dimension tables.</span></span>  
  
 <span data-ttu-id="76be0-109">Weitere Informationen zum Verarbeiten von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]-Objekten finden Sie unter [Verarbeitungsoptionen und -einstellungen &#40;Analysis Services&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/processing-options-and-settings-analysis-services).</span><span class="sxs-lookup"><span data-stu-id="76be0-109">For more information about processing [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects, see [Processing Options and Settings &#40;Analysis Services&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/processing-options-and-settings-analysis-services).</span></span>  
  
## <a name="configuration-of-the-dimension-processing-destination"></a><span data-ttu-id="76be0-110">Konfiguration des Ziels für die Dimensionsverarbeitung</span><span class="sxs-lookup"><span data-stu-id="76be0-110">Configuration of the Dimension Processing Destination</span></span>  
 <span data-ttu-id="76be0-111">Das Ziel für Dimensionsverarbeitung stellt mithilfe eines Verbindungs-Managers für [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] eine Verbindung mit dem [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Projekt oder der Instanz von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] her, die die vom Ziel verarbeiteten Dimensionen enthält.</span><span class="sxs-lookup"><span data-stu-id="76be0-111">The Dimension Processing destination uses an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] connection manager to connect to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project or the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] that contains the dimensions the destination processes.</span></span> <span data-ttu-id="76be0-112">Weitere Informationen finden Sie unter [Analysis Services Connection Manager](../connection-manager/analysis-services-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="76be0-112">For more information, see [Analysis Services Connection Manager](../connection-manager/analysis-services-connection-manager.md).</span></span>  
  
 <span data-ttu-id="76be0-113">Das Ziel weist eine Eingabe auf.</span><span class="sxs-lookup"><span data-stu-id="76be0-113">This destination has one input.</span></span> <span data-ttu-id="76be0-114">Eine Fehlerausgabe wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="76be0-114">It does not support an error output.</span></span>  
  
 <span data-ttu-id="76be0-115">Sie können Eigenschaften mit dem [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer oder programmgesteuert festlegen.</span><span class="sxs-lookup"><span data-stu-id="76be0-115">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="76be0-116">Klicken Sie auf eines der folgenden Themen, um weitere Informationen zu den Eigenschaften zu erhalten, die Sie im Dialogfeld **Ziel-Editor für Dimensionsverarbeitung** festlegen können:</span><span class="sxs-lookup"><span data-stu-id="76be0-116">For more information about the properties that you can set in the **Dimension Processing Destination Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="76be0-117">Ziel-Editor für Dimensionsverarbeitung &#40;Seite Verbindungs-Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="76be0-117">Dimension Processing Destination Editor &#40;Connection Manager Page&#41;</span></span>](../dimension-processing-destination-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="76be0-118">Ziel-Editor für Dimensionsverarbeitung &#40;Seite Zuordnungen&#41;</span><span class="sxs-lookup"><span data-stu-id="76be0-118">Dimension Processing Destination Editor &#40;Mappings Page&#41;</span></span>](../dimension-processing-destination-editor-mappings-page.md)  
  
-   [<span data-ttu-id="76be0-119">Ziel-Editor für Dimensionsverarbeitung &#40;Seite „Erweitert“&#41;</span><span class="sxs-lookup"><span data-stu-id="76be0-119">Dimension Processing Destination Editor &#40;Advanced Page&#41;</span></span>](../dimension-processing-destination-editor-advanced-page.md)  
  
 <span data-ttu-id="76be0-120">Das Dialogfeld **Erweiterter Editor** enthält die Eigenschaften, die programmgesteuert festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="76be0-120">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="76be0-121">Klicken Sie auf eines der folgenden Themen, um weitere Informationen zu den Eigenschaften anzuzeigen, die Sie im Dialogfeld **Erweiterter Editor** oder programmgesteuert festlegen können:</span><span class="sxs-lookup"><span data-stu-id="76be0-121">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topic:</span></span>  
  
-   [<span data-ttu-id="76be0-122">Common Properties</span><span class="sxs-lookup"><span data-stu-id="76be0-122">Common Properties</span></span>](../common-properties.md)  
  
 <span data-ttu-id="76be0-123">Informationen zum Festlegen der Eigenschaften finden Sie unter [Festlegen der Eigenschaften einer Datenflusskomponente](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="76be0-123">For more information about how to set the properties, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76be0-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="76be0-124">See Also</span></span>  
 <span data-ttu-id="76be0-125">[Datenfluss](data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="76be0-125">[Data Flow](data-flow.md) </span></span>  
 [<span data-ttu-id="76be0-126">SQL Server Integration Services-Transformationen</span><span class="sxs-lookup"><span data-stu-id="76be0-126">Integration Services Transformations</span></span>](transformations/integration-services-transformations.md)  
  
  
