---
title: Anzeigen räumlicher Daten im Objekt-Explorer
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 59cca562-e3f5-4257-b868-adcbcc0142cc
author: rothja
ms.author: jroth
ms.openlocfilehash: 881adf69ee83ee4b7536afae0b190fbec90f132c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618621"
---
# <a name="view-spatial-data-in-object-explorer"></a><span data-ttu-id="7f737-102">Anzeigen räumlicher Daten im Objekt-Explorer</span><span class="sxs-lookup"><span data-stu-id="7f737-102">View Spatial Data in Object Explorer</span></span>
  <span data-ttu-id="7f737-103">Im Fenster **Räumliche Ergebnisse** des Abfrage-Editors werden visuelle Zuordnungstools bereitgestellt, mit denen Sie zusätzlich zu den im Fenster **Ergebnisse** im Rasterformat angezeigten Daten Ergebnisse für räumliche Daten anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="7f737-103">The **Spatial results** window in Query Editor provides visual mapping tools for viewing spatial data results in addition to the data displayed in grid format in the **Results** window.</span></span> <span data-ttu-id="7f737-104">Zum Anzeigen räumlicher Daten im Fenster **Räumliche Ergebnisse** müssen die Abfrageergebnisse mindestens eine Spalte für räumliche Daten mit Geometrie- oder Geografiedaten enthalten.</span><span class="sxs-lookup"><span data-stu-id="7f737-104">To display spatial data in the **Spatial Results** window, your query results must contain at least one spatial data column with either geometry or geography data.</span></span>  
  
### <a name="to-view-spatial-data-in-the-spatial-results-window"></a><span data-ttu-id="7f737-105">So zeigen Sie räumliche Daten im Fenster "Räumliche Ergebnisse" an</span><span class="sxs-lookup"><span data-stu-id="7f737-105">To view spatial data in the Spatial results window</span></span>  
  
1.  <span data-ttu-id="7f737-106">Klicken Sie im Abfrage-Editor auf die Registerkarte **Räumliche Ergebnisse** .</span><span class="sxs-lookup"><span data-stu-id="7f737-106">In Query Editor, click the **Spatial results** tab.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7f737-107">Dieses Fenster ist nicht verfügbar, wenn die Abfrageergebnisse keine räumlichen Daten enthalten oder Sie angeben, dass die Ergebnisse als Text zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="7f737-107">This window is not available if your query results do not contain spatial data or if you specify that your results are returned as text.</span></span>  
  
2.  <span data-ttu-id="7f737-108">Wählen Sie die anzuzeigende Spalte in der Liste **Räumliche Spalte auswählen** aus.</span><span class="sxs-lookup"><span data-stu-id="7f737-108">Select the column you want to view from the **Select spatial column** list.</span></span> <span data-ttu-id="7f737-109">Wenn in der Tabelle nur eine räumliche Spalte enthalten ist, bildet diese Spalte die Standardoption in der Liste.</span><span class="sxs-lookup"><span data-stu-id="7f737-109">If there is only one spatial column in your table, this column is the default option in the list.</span></span>  
  
3.  <span data-ttu-id="7f737-110">Wählen Sie in der Liste **Bezeichnungsspalte auswählen** die nicht räumliche Spalte aus, die Sie für Datenbezeichnungen verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="7f737-110">Select the non-spatial column you want to use as data labels from the **Select label columns** list.</span></span>  
  
4.  <span data-ttu-id="7f737-111">Wählen Sie in der Liste **Projektion auswählen** die Projektion aus, die Sie für Geografiedaten verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="7f737-111">Select the projection you want for geography data from the **Select projection** list.</span></span> <span data-ttu-id="7f737-112">Die Standardprojektion ist Equirectangular. Andere verfügbare Projektionen sind Mercator, Robinson und Bonne.</span><span class="sxs-lookup"><span data-stu-id="7f737-112">The default projection is Equirectangular; other projections available are Mercator, Robinson, or Bonne.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7f737-113">**Projektion auswählen** ist nicht verfügbar, wenn die räumliche Spalte Geometriedaten enthält.</span><span class="sxs-lookup"><span data-stu-id="7f737-113">**Select projection** is not available if your spatial column contains geometry data.</span></span>  
  
5.  <span data-ttu-id="7f737-114">Stellen Sie den Schieberegler **Zoom** ein, um zugeordnete Elemente visuell zu vergrößern.</span><span class="sxs-lookup"><span data-stu-id="7f737-114">Adjust the **Zoom** slider to increase the visual size of mapped elements.</span></span> <span data-ttu-id="7f737-115">Bei polygonalen Formen ist die Bezeichnung nur sichtbar, wenn die Form groß genug ist, um den Bezeichnungstext aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="7f737-115">For polygon shapes, the label is visible only when the shape is large enough to hold the label text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f737-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7f737-116">See Also</span></span>  
 <span data-ttu-id="7f737-117">[Fenster "Räumliche Ergebnisse"](spatial-results-window.md) </span><span class="sxs-lookup"><span data-stu-id="7f737-117">[Spatial Results Window](spatial-results-window.md) </span></span>  
 <span data-ttu-id="7f737-118">[Abfrage-Editor der Datenbank-Engine &#40;SQL Server Management Studio&#41;](database-engine-query-editor-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="7f737-118">[Database Engine Query Editor &#40;SQL Server Management Studio&#41;](database-engine-query-editor-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="7f737-119">Abfrage- und Text-Editoren &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="7f737-119">Query and Text Editors &#40;SQL Server Management Studio&#41;</span></span>](query-and-text-editors-sql-server-management-studio.md)  
  
  
