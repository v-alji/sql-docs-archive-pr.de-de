---
title: Tabelle suchen (Dialog Feld) (Analysis Services Mehrdimensionale Daten) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.findtabledialog.f1
helpviewer_keywords:
- Find Table dialog box
ms.assetid: 133d28e8-55eb-4783-bb8b-d3776a95ebda
author: minewiskan
ms.author: owend
ms.openlocfilehash: ee22c912a3121841a7827e31d53f7b8baba72174
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610186"
---
# <a name="find-table-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="fe8e6-102">Dialogfeld 'Tabelle suchen' (Analysis Services – Mehrdimensionale Daten)</span><span class="sxs-lookup"><span data-stu-id="fe8e6-102">Find Table Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="fe8e6-103">Mithilfe des Dialogfelds **Tabelle suchen** von [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] können Sie in der Datenquellensicht, die einer Dimension, einem Cube oder einer Miningstruktur zugeordnet ist, nach einer Tabelle suchen.</span><span class="sxs-lookup"><span data-stu-id="fe8e6-103">Use the **Find Table** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to locate a table in the data source view associated with a dimension, cube, or mining structure.</span></span> <span data-ttu-id="fe8e6-104">Dieses Dialogfeld von [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] können Sie folgendermaßen aufrufen:</span><span class="sxs-lookup"><span data-stu-id="fe8e6-104">You can display this dialog box in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] by:</span></span>  
  
-   <span data-ttu-id="fe8e6-105">Öffnen Sie **Dimensions-Designer** , und klicken Sie im Bereich **Symbolleiste** der Seite **Dimensionsstruktur** auf **Tabelle suchen**.</span><span class="sxs-lookup"><span data-stu-id="fe8e6-105">Clicking **Find Table** from the **Toolbar** pane on the **Dimension Structure** page of the **Dimension Designer**.</span></span>  
  
-   <span data-ttu-id="fe8e6-106">Öffnen Sie **Dimensions-Designer** , klicken Sie auf der Seite **Dimensionsstruktur** mit der rechten Maustaste auf den Hintergrund des Bereichs **Datenquellensicht** , und wählen Sie **Tabelle suchen**aus.</span><span class="sxs-lookup"><span data-stu-id="fe8e6-106">Right-clicking the background of the **Data Source View** pane on the **Dimension Structure** page of the **Dimension Designer** and selecting **Find Table**.</span></span>  
  
-   <span data-ttu-id="fe8e6-107">Öffnen Sie **Cube-Designer** , und klicken Sie im Bereich **Symbolleiste** der Seite **Cubestruktur** auf **Tabelle suchen**.</span><span class="sxs-lookup"><span data-stu-id="fe8e6-107">Clicking **Find Table** from the **Toolbar** pane on the **Cube Structure** page of the **Cube Designer**.</span></span>  
  
-   <span data-ttu-id="fe8e6-108">Öffnen Sie **Cube-Designer** , klicken Sie auf der Seite **Cubestruktur** mit der rechten Maustaste auf den Hintergrund des Bereichs **Datenquellensicht** , und wählen Sie **Tabelle suchen**aus.</span><span class="sxs-lookup"><span data-stu-id="fe8e6-108">Right-clicking the background of the **Data Source View** pane on the **Cube Structure** page of the **Cube Designer** and selecting **Find Table**.</span></span>  
  
-   <span data-ttu-id="fe8e6-109">Öffnen Sie **Data Mining-Modelldesigner** , klicken Sie auf der Seite **Miningstruktur** mit der rechten Maustaste auf den Hintergrund des Bereichs **Datenquellensicht** , und wählen Sie **Tabelle suchen**aus.</span><span class="sxs-lookup"><span data-stu-id="fe8e6-109">Right-clicking the background of the **Data Source View** pane on the **Mining Structure** page of the **Data Mining Model Designer** and selecting **Find Table**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="fe8e6-110">Tastatur</span><span class="sxs-lookup"><span data-stu-id="fe8e6-110">Options</span></span>  
 <span data-ttu-id="fe8e6-111">**Wählen Sie eine Tabelle aus der Datenquellensicht aus:**</span><span class="sxs-lookup"><span data-stu-id="fe8e6-111">**Select a table from data source view**</span></span>  
 <span data-ttu-id="fe8e6-112">Wählen Sie im Bereich **Datenquellensicht** die Tabelle aus, nach der gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="fe8e6-112">Select the table to find in the **Data Source View** pane.</span></span> <span data-ttu-id="fe8e6-113">Diese Option zeigt ein Raster verfügbarer Objekte und ihrer Typen an, die mit dem unter **Filter** festgelegten Filter übereinstimmen (oder aller Tabellen, wenn kein **Filter** festgelegt wurde) und noch nicht im aktuellen Diagramm angezeigt wurden.</span><span class="sxs-lookup"><span data-stu-id="fe8e6-113">This option displays a grid of available objects and their types that match the filter set in **Filter** (or all tables if **Filter** is not set) and have not yet been shown in the current diagram.</span></span>  
  
 <span data-ttu-id="fe8e6-114">**Filter**</span><span class="sxs-lookup"><span data-stu-id="fe8e6-114">**Filter**</span></span>  
 <span data-ttu-id="fe8e6-115">Geben Sie den Filter ein, der zum Einschränken der aufgeführten Objekte verwendet wird, und klicken Sie auf die Schaltfläche, um die Tabellen unter **Wählen Sie eine Tabelle aus der Datenquellensicht aus**zu filtern.</span><span class="sxs-lookup"><span data-stu-id="fe8e6-115">Type the filter used to restrict the objects listed, and then click the button to filter the tables listed in **Select a table from data source view**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe8e6-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fe8e6-116">See Also</span></span>  
 <span data-ttu-id="fe8e6-117">[Dialog Feld ' Assemblyeigenschaften ' &#40;Analysis Services Mehrdimensionale Daten&#41;](assembly-properties-dialog-box-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="fe8e6-117">[Assembly Properties Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](assembly-properties-dialog-box-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="fe8e6-118">[Datenquellen Sicht &#40;Registerkarte "Dimensions Struktur", Dimensions-Designer&#41; &#40;Analysis Services Mehrdimensionale Daten&#41;](datasource-view-dimension-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="fe8e6-118">[Data Source View &#40;Dimension Structure Tab, Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](datasource-view-dimension-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="fe8e6-119">Datenquellen Sicht &#40;Registerkarte "Cubestruktur", Cube-Designer&#41; &#40;Analysis Services-Mehrdimensionale Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="fe8e6-119">Data Source View &#40;Cube Structure Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](data-source-view-cube-designer-analysis-services-multidimensional-data.md)  
  
  
