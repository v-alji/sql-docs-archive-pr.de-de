---
title: Ändern von Standard Tabellennamen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: ddd97483-a76d-43c1-8b40-fc7cc57fb0c2
author: minewiskan
ms.author: owend
ms.openlocfilehash: 254f797be95f60211983400b019415431d4cf39c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608052"
---
# <a name="modifying-default-table-names"></a><span data-ttu-id="747ab-102">Ändern von Standardtabellennamen</span><span class="sxs-lookup"><span data-stu-id="747ab-102">Modifying Default Table Names</span></span>
  <span data-ttu-id="747ab-103">Sie können den Wert der **FriendlyName** -Eigenschaft für Objekte in der Datenquellensicht ändern, um die Benutzerfreundlichkeit und Identifizierung zu optimieren.</span><span class="sxs-lookup"><span data-stu-id="747ab-103">You can change the value of the **FriendlyName** property for objects in the data source view to make them easier to notice and use.</span></span>  
  
 <span data-ttu-id="747ab-104">In der folgenden Aufgabe ändern Sie den Anzeigenamen jeder Tabelle in der Datenquellensicht, indem Sie die Präfixe**Dim**und**Fact**aus diesen Tabellen entfernen.</span><span class="sxs-lookup"><span data-stu-id="747ab-104">In the following task, you will change the friendly name of each table in the data source view by removing the "**Dim**" and "**Fact**" prefixes from these tables.</span></span> <span data-ttu-id="747ab-105">Dadurch lassen sich der Cube und die Dimensionsobjekte (die Sie in der nächsten Lektion definieren) einfacher identifizieren und verwenden.</span><span class="sxs-lookup"><span data-stu-id="747ab-105">This will make the cube and dimension objects (that you will define in the next lesson) easier to notice and use.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="747ab-106">Sie können auch die Anzeigenamen von Spalten ändern, berechnete Spalten definieren und Tabellen oder Sichten in der Datenquellensicht verknüpfen, um die Benutzerfreundlichkeit zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="747ab-106">You can also change the friendly names of columns, define calculated columns, and join tables or views in the data source view to make them easier to use.</span></span>  
  
### <a name="to-modify-the-default-name-of-a-table"></a><span data-ttu-id="747ab-107">So ändern Sie den Standardnamen einer Tabelle</span><span class="sxs-lookup"><span data-stu-id="747ab-107">To modify the default name of a table</span></span>  
  
1.  <span data-ttu-id="747ab-108">Klicken Sie im Bereich **Tabellen** des **Datenquellensicht-Designers**mit der rechten Maustaste auf die Tabelle **FactInternetSales** , und klicken Sie anschließend auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="747ab-108">In the **Tables** pane of **Data Source View Designer**, right-click the **FactInternetSales** table, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="747ab-109">Wenn das Eigenschaftenfenster auf der rechten Seite des Microsoft Visual Studio-Fensters nicht angezeigt wird, klicken Sie in der Titelleiste des Eigenschaftenfensters auf die Schaltfläche **Automatisch im Hintergrund** , damit es sichtbar bleibt.</span><span class="sxs-lookup"><span data-stu-id="747ab-109">If the Properties window on the right side of the Microsoft Visual Studio window is not displayed, click the **Auto Hide** button on the title bar of the Properties window so that this window remains visible.</span></span>  
  
     <span data-ttu-id="747ab-110">Es ist einfacher, die Eigenschaften für jede Tabelle in der Datenquellensicht zu ändern, wenn das Eigenschaftenfenster geöffnet bleibt.</span><span class="sxs-lookup"><span data-stu-id="747ab-110">It is easier to change the properties for each table in the data source view when the Properties window remains open.</span></span> <span data-ttu-id="747ab-111">Wenn Sie das Fenster nicht mithilfe der Schaltfläche **Automatisch im Hintergrund** geöffnet halten, wird das Fenster geschlossen, sobald Sie auf ein anderes Objekt im Bereich **Diagramm** klicken.</span><span class="sxs-lookup"><span data-stu-id="747ab-111">If you do not pin the window open by using the **Auto Hide** button, the window will close when you click a different object in the **Diagram** pane.</span></span>  
  
3.  <span data-ttu-id="747ab-112">Ändern Sie die **FriendlyName** -Eigenschaft für das **FactInternetSales** -Objekt in *`InternetSales`* .</span><span class="sxs-lookup"><span data-stu-id="747ab-112">Change the **FriendlyName** property for the **FactInternetSales** object to *`InternetSales`*.</span></span>  
  
     <span data-ttu-id="747ab-113">Wenn Sie außerhalb der Zelle für die **FriendlyName** -Eigenschaft klicken, wird die Änderung angewendet.</span><span class="sxs-lookup"><span data-stu-id="747ab-113">When you click away from the cell for the **FriendlyName** property, the change is applied.</span></span> <span data-ttu-id="747ab-114">In der nächsten Lektion definieren Sie eine Measuregruppe, die auf dieser Faktentabelle basiert.</span><span class="sxs-lookup"><span data-stu-id="747ab-114">In the next lesson, you will define a measure group that is based on this fact table.</span></span> <span data-ttu-id="747ab-115">Der Name der Faktentabelle lautet dann InternetSales statt FactInternetSales, weil Sie in dieser Lektion Änderungen vorgenommen haben.</span><span class="sxs-lookup"><span data-stu-id="747ab-115">The name of the fact table will be InternetSales instead of FactInternetSales because of the change you made in this lesson.</span></span>  
  
4.  <span data-ttu-id="747ab-116">Klicken Sie im Bereich **Tabellen** auf **DimProduct** .</span><span class="sxs-lookup"><span data-stu-id="747ab-116">Click **DimProduct** in the **Tables** pane.</span></span> <span data-ttu-id="747ab-117">Ändern Sie im Eigenschaftenfenster die **FriendlyName** -Eigenschaft in *`Product`* .</span><span class="sxs-lookup"><span data-stu-id="747ab-117">In the Properties window, change the **FriendlyName** property to *`Product`*.</span></span>  
  
5.  <span data-ttu-id="747ab-118">Ändern Sie die **FriendlyName** -Eigenschaft jeder verbleibenden Tabelle in der Datenquellensicht in der gleichen Weise, um das Präfix "**Dim**" zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="747ab-118">Change the **FriendlyName** property of each remaining table in the data source view in the same way, to remove the "**Dim**" prefix.</span></span>  
  
6.  <span data-ttu-id="747ab-119">Klicken Sie nach dem Fertigstellen auf die Schaltfläche **Automatisch im Hintergrund** , um das Eigenschaftenfenster wieder auszublenden.</span><span class="sxs-lookup"><span data-stu-id="747ab-119">When you have finished, click the **Auto Hide** button to hide the Properties window again.</span></span>  
  
7.  <span data-ttu-id="747ab-120">Klicken Sie im Menü **Datei** oder in der Symbolleiste von [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]auf **Alle speichern** , um die von Ihnen bis jetzt vorgenommenen Änderungen im [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial-Projekt zu speichern.</span><span class="sxs-lookup"><span data-stu-id="747ab-120">On the **File** menu, or on the toolbar of [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click **Save All** to save the changes you have made to this point in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project.</span></span> <span data-ttu-id="747ab-121">Sie können das Lernprogramm hier beenden, wenn Sie möchten, und es später fortsetzen.</span><span class="sxs-lookup"><span data-stu-id="747ab-121">You can stop the tutorial here if you want and resume it later.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="747ab-122">Nächste Lektion</span><span class="sxs-lookup"><span data-stu-id="747ab-122">Next Lesson</span></span>  
 [<span data-ttu-id="747ab-123">Lektion 2: Definieren und Bereitstellen eines Cubes</span><span class="sxs-lookup"><span data-stu-id="747ab-123">Lesson 2: Defining and Deploying a Cube</span></span>](lesson-2-defining-and-deploying-a-cube.md)  
  
## <a name="see-also"></a><span data-ttu-id="747ab-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="747ab-124">See Also</span></span>  
 <span data-ttu-id="747ab-125">[Datenquellen Sichten in mehrdimensionalen Modellen](multidimensional-models/data-source-views-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="747ab-125">[Data Source Views in Multidimensional Models](multidimensional-models/data-source-views-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="747ab-126">Ändern von Eigenschaften in einer Datenquellensicht &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="747ab-126">Change Properties in a Data Source View &#40;Analysis Services&#41;</span></span>](multidimensional-models/change-properties-in-a-data-source-view-analysis-services.md)  
  
  
