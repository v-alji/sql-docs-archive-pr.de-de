---
title: In Excel analysieren (Registerkarte ' Browser ', Cube-Designer) (Analysis Services-Mehrdimensionale Daten) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.browsecube.datapane.f1
- sql12.asvs.ssms.analyzeinexcel.f1
ms.assetid: 890ed457-137e-44ac-9b2c-83344a1b8fc9
author: minewiskan
ms.author: owend
ms.openlocfilehash: b9fa27ae291d40b7f5637e3968438fcaec1de03d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610388"
---
# <a name="analyze-in-excel-browser-tab-cube-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="3ddc6-102">In Excel analysieren (Registerkarte 'Browser', Cube-Designer) (Analysis Services – Mehrdimensionale Daten)</span><span class="sxs-lookup"><span data-stu-id="3ddc6-102">Analyze in Excel (Browser Tab, Cube Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="3ddc6-103">Die Funktion**In Excel analysieren** bietet dem Cubeentwickler eine Möglichkeit, schnell zu überprüfen, wie ein Projekt für den Endbenutzer aussehen würde.</span><span class="sxs-lookup"><span data-stu-id="3ddc6-103">**Analyze in Excel** provides the cube developer with a way to quickly review how a project would look to the end user.</span></span> <span data-ttu-id="3ddc6-104">Über die Funktion **In Excel analysieren** wird Microsoft Excel geöffnet; stellt eine Datenquellenverbindung mit der Arbeitsbereichsdatenbank her und fügt automatisch eine PivotTable in das Arbeitsblatt ein.</span><span class="sxs-lookup"><span data-stu-id="3ddc6-104">The **Analyze in Excel** feature opens Microsoft Excel, creates a data source connection to the workspace database, and automatically adds a PivotTable to the worksheet.</span></span> <span data-ttu-id="3ddc6-105">Diese Funktion ersetzt das Office-Websteuerelement, durch das in vorherigen Versionen eine eingebettete PivotTable auf der Registerkarte Browser bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="3ddc6-105">This feature replaces the Office Web Control that provided an embedded PivotTable in the Browser tab in previous releases.</span></span>  
  
 <span data-ttu-id="3ddc6-106">**So zeigen Sie Cubedaten an**</span><span class="sxs-lookup"><span data-stu-id="3ddc6-106">**To view cube data:**</span></span>  
  
1.  <span data-ttu-id="3ddc6-107">Doppelklicken Sie im Projektmappen-Explorer von [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]auf einen Cube, um ihn im Cube-Designer zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="3ddc6-107">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], in Solution Explorer, double-click a cube to open it in Cube Designer.</span></span>  
  
2.  <span data-ttu-id="3ddc6-108">Klicken Sie auf die Registerkarte **Browser** .</span><span class="sxs-lookup"><span data-stu-id="3ddc6-108">Click the **Browser** tab.</span></span>  
  
3.  <span data-ttu-id="3ddc6-109">Klicken Sie auf **Verbindung wiederherstellen** , um die Verbindung zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="3ddc6-109">Click **Reconnect** to validate the connection.</span></span>  
  
4.  <span data-ttu-id="3ddc6-110">Klicken Sie in der Menüleiste auf das Excel-Symbol.</span><span class="sxs-lookup"><span data-stu-id="3ddc6-110">Click the Excel icon in the menu bar.</span></span>  
  
5.  <span data-ttu-id="3ddc6-111">Klicken Sie auf **Aktivieren**, wenn Sie zur Aktivierung von Datenverbindungen aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="3ddc6-111">When asked to enable data connections, click **Enable**.</span></span> <span data-ttu-id="3ddc6-112">Excel wird unter Verwendung der aktuellen Datenverbindung geöffnet. Dem Arbeitsblatt wird eine PivotTable hinzugefügt, sodass Sie die Daten direkt durchsuchen können.</span><span class="sxs-lookup"><span data-stu-id="3ddc6-112">Excel opens using the current data connection, adding a PivotTable to the worksheet so that you can begin browsing your data.</span></span>  
  
 <span data-ttu-id="3ddc6-113">Sie können nun interaktiv eine PivotTable erstellen, indem Sie Measures aus der Faktentabelle in den Wertebereich und Dimensionsattribute in die Zeilen- und Spaltenbereiche ziehen.</span><span class="sxs-lookup"><span data-stu-id="3ddc6-113">You can now build a PivotTable interactively by dragging measures from the fact table to the Values area, and dimension attributes to the Row and Column areas.</span></span> <span data-ttu-id="3ddc6-114">Wenn Sie über Hierarchien verfügen, fügen Sie diese dem Zeilen- oder Spaltenbereich hinzu.</span><span class="sxs-lookup"><span data-stu-id="3ddc6-114">If you have hierarchies, add them to Rows or Column areas.</span></span> <span data-ttu-id="3ddc6-115">Sie können Rollups oder Drilldowns in der Hierarchie ausführen, um Faktendaten auf unterschiedlichen Ebenen zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="3ddc6-115">You can roll up or drill down the hierarchy to browse fact data at different levels.</span></span>  
  
 <span data-ttu-id="3ddc6-116">Objekte und Daten werden innerhalb des Kontexts des effektiven Benutzers oder der Rolle und Perspektive angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3ddc6-116">Objects and data are viewed within the context of the effective user or role and perspective.</span></span> <span data-ttu-id="3ddc6-117">Bei Verwendung von Excel werden die Anmeldeinformationen des aktuellen Benutzers und nicht die auf der Seite **Identitätswechselinformationen** angegebenen Anmeldeinformationen zum Herstellen einer Verbindung mit der Datenquelle verwendet, wenn eine Abfrage ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3ddc6-117">When using Excel, the credentials of the current user, not the credentials specified in the **Impersonation Information** page, are used to connect to the data source when a query is executed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3ddc6-118">Um die Funktion In Excel analysieren zu verwenden, muss Excel auf demselben Computer wie [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]installiert sein.</span><span class="sxs-lookup"><span data-stu-id="3ddc6-118">To use the Analyze in Excel feature, Excel must be installed on the same computer as [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="3ddc6-119">Wenn Excel nicht auf demselben Computer installiert ist, können Sie Excel auf einem anderen Computer verwenden und eine Verbindung mit dem Cube als Datenquelle herstellen.</span><span class="sxs-lookup"><span data-stu-id="3ddc6-119">If Excel is not installed on the same computer, you can use Excel on another computer and connect to the cube as a data source.</span></span> <span data-ttu-id="3ddc6-120">Sie können dem Arbeitsblatt dann manuell eine PivotTable hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="3ddc6-120">You can then manually add a PivotTable to the worksheet.</span></span> <span data-ttu-id="3ddc6-121">Modellobjekte (Tabellen, Spalten, Measures und KPIs) sind als Felder in der PivotTable-Feldliste enthalten.</span><span class="sxs-lookup"><span data-stu-id="3ddc6-121">Model objects (tables, columns, measures, and KPIs) are included as fields in the PivotTable field list.</span></span>  
  
 <span data-ttu-id="3ddc6-122">Weitere Informationen zur Funktion **In Excel analysieren** finden Sie in den folgenden Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="3ddc6-122">For more information about the **Analyze in Excel** feature, see these resources:</span></span>  
  
 [<span data-ttu-id="3ddc6-123">Analysieren in Excel &#40;SSAS – tabellarisch&#41;</span><span class="sxs-lookup"><span data-stu-id="3ddc6-123">Analyze in Excel &#40;SSAS Tabular&#41;</span></span>](tabular-models/analyze-in-excel-ssas-tabular.md)  
  
 [<span data-ttu-id="3ddc6-124">Analysieren eines Tabellenmodells in Excel &#40;SSAS – tabellarisch&#41;</span><span class="sxs-lookup"><span data-stu-id="3ddc6-124">Analyze a Tabular Model in Excel &#40;SSAS Tabular&#41;</span></span>](tabular-models/analyze-a-tabular-model-in-excel-ssas-tabular.md)  
  
 [<span data-ttu-id="3ddc6-125">Durchsuchen von Daten und Metadaten in Cube</span><span class="sxs-lookup"><span data-stu-id="3ddc6-125">Browse data and metadata in Cube</span></span>](multidimensional-models/browse-data-and-metadata-in-cube.md)  
  
## <a name="see-also"></a><span data-ttu-id="3ddc6-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3ddc6-126">See Also</span></span>  
 <span data-ttu-id="3ddc6-127">[Browser &#40;Cube-Designer&#41; &#40;Analysis Services Mehrdimensionale Daten&#41;](browser-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="3ddc6-127">[Browser &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](browser-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="3ddc6-128">[Symbolleiste &#40;Registerkarte "Browser", Cube-Designer&#41; &#40;Analysis Services Mehrdimensionale Daten&#41;](toolbar-browser-tab-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="3ddc6-128">[Toolbar &#40;Browser Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](toolbar-browser-tab-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="3ddc6-129">[Metadaten &#40;Registerkarte "Browser", Cube-Designer&#41; &#40;Analysis Services Mehrdimensionale Daten&#41;](metadata-browser-tab-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="3ddc6-129">[Metadata &#40;Browser Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](metadata-browser-tab-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="3ddc6-130">Abfragen und Filtern &#40;Registerkarte "Browser", Cube-Designer&#41; &#40;Analysis Services-mehrdimensionalen Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="3ddc6-130">Query and Filter &#40;Browser Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](query-filter-browser-cube-designer-analysis-services-multidimensional-data.md)  
  
  
