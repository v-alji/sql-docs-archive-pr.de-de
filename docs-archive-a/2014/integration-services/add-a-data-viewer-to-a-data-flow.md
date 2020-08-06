---
title: Hinzufügen eines Daten-Viewers zu einem Datenfluss | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- data viewers [Integration Services]
- data flow [Integration Services], data viewers
- adding data viewers
ms.assetid: 5e573274-a170-4132-bfc8-a8ff3a8411e4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7abd76417552ec50da736afe024a5ae36ee6a2ae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608794"
---
# <a name="add-a-data-viewer-to-a-data-flow"></a><span data-ttu-id="86d8e-102">Hinzufügen eines Daten-Viewers zu einem Datenfluss</span><span class="sxs-lookup"><span data-stu-id="86d8e-102">Add a Data Viewer to a Data Flow</span></span>
  <span data-ttu-id="86d8e-103">In diesem Thema wird beschrieben, wie ein Daten-Viewer in einem Datenfluss hinzugefügt und konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="86d8e-103">This topic describes how to add and configure a data viewer in a data flow.</span></span> <span data-ttu-id="86d8e-104">Ein Daten-Viewer zeigt Daten an, die sich zwischen zwei Datenflusskomponenten bewegen.</span><span class="sxs-lookup"><span data-stu-id="86d8e-104">A data viewer displays data that is moving between two data flow components.</span></span> <span data-ttu-id="86d8e-105">Ein Daten-Viewer kann z. B. die Daten anzeigen, die von einer Datenquelle extrahiert werden, bevor die Daten von einer Transformation im Datenfluss geändert werden.</span><span class="sxs-lookup"><span data-stu-id="86d8e-105">For example, a data viewer can display the data that is extracted from a data source before a transformation in the data flow modifies the data.</span></span>  
  
 <span data-ttu-id="86d8e-106">Ein Pfad verbindet Komponenten in einem Datenfluss, indem die Ausgabe einer Datenflusskomponente mit der Eingabe einer anderen Komponente verbunden wird.</span><span class="sxs-lookup"><span data-stu-id="86d8e-106">A path connects components in a data flow by connecting the output of one data flow component to the input of another component.</span></span>  
  
 <span data-ttu-id="86d8e-107">Bevor Sie einem Paket Daten-Viewer hinzufügen können, muss das Paket einen Datenfluss-Task enthalten und mindestens zwei verbundene Datenflusskomponenten.</span><span class="sxs-lookup"><span data-stu-id="86d8e-107">Before you can add data viewers to a package, the package must include a Data Flow task and at least two data flow components that are connected.</span></span>  
  
### <a name="to-add-a-data-viewer-to-a-data-flow"></a><span data-ttu-id="86d8e-108">So fügen Sie einem Datenfluss einen Daten-Viewer hinzu</span><span class="sxs-lookup"><span data-stu-id="86d8e-108">To add a data viewer to a data flow</span></span>  
  
1.  <span data-ttu-id="86d8e-109">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] das [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]-Projekt mit dem gewünschten Paket.</span><span class="sxs-lookup"><span data-stu-id="86d8e-109">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="86d8e-110">Doppelklicken Sie im Projektmappen-Explorer auf das Paket, um es zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="86d8e-110">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="86d8e-111">Klicken Sie auf die Registerkarte **Ablaufsteuerung** , falls sie nicht bereits aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="86d8e-111">Click the **Control Flow** tab, if it is not already active.</span></span>  
  
4.  <span data-ttu-id="86d8e-112">Klicken Sie auf den Datenflusstask, an dessen Datenfluss Sie einen Daten-Viewer anfügen möchten, und klicken Sie dann auf die Registerkarte **Datenfluss** .</span><span class="sxs-lookup"><span data-stu-id="86d8e-112">Click the Data Flow task to whose data flow you want to attach a data viewer and then click the **Data Flow** tab.</span></span>  
  
5.  <span data-ttu-id="86d8e-113">Klicken Sie mit der rechten Maustaste auf einen Pfad zwischen zwei Datenflusskomponenten, und klicken Sie auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="86d8e-113">Right-click a path between two data flow components, and click **Edit**.</span></span>  
  
6.  <span data-ttu-id="86d8e-114">Auf der Seite **Allgemein** können Sie Pfadeigenschaften anzeigen und bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="86d8e-114">On the **General** page, you can view and edit path properties.</span></span> <span data-ttu-id="86d8e-115">Beispielsweise können Sie aus der Dropdownliste **PathAnnotation** die Anmerkung auswählen, die neben dem Pfad angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="86d8e-115">For example, from the **PathAnnotation** drop-down list you can select the annotation that appears next to the path.</span></span>  
  
7.  <span data-ttu-id="86d8e-116">Auf der Seite **Metadaten** können Sie die Spaltenmetadaten anzeigen und die Metadaten in die Zwischenablage kopieren.</span><span class="sxs-lookup"><span data-stu-id="86d8e-116">On the **Metadata** page, you can view the column metadata and copy the metadata to the Clipboard.</span></span>  
  
8.  <span data-ttu-id="86d8e-117">Klicken Sie auf der Seite **Daten-Viewer** auf **Daten-Viewer aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="86d8e-117">On the **Data Viewer** page, click **Enable data viewer**.</span></span>  
  
9. <span data-ttu-id="86d8e-118">Wählen Sie im Bereich Anzuzeigende Spalten die Spalten aus, die im Daten-Viewer angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="86d8e-118">In the Columns to display area, select the columns you want to display in the data viewer.</span></span> <span data-ttu-id="86d8e-119">Standardmäßig werden alle verfügbaren Spalten ausgewählt und in der Liste **Angezeigte Spalten** aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="86d8e-119">By default, all the available columns are selected and listed in the **Displayed Columns** list.</span></span> <span data-ttu-id="86d8e-120">Verschieben Sie Spalten, die Sie nicht verwenden möchten, in die Liste **Nicht verwendete Spalten** , indem Sie diese auswählen und dann auf den linken Pfeil klicken.</span><span class="sxs-lookup"><span data-stu-id="86d8e-120">Move columns that you do not want to use to the **Unused Column** list by selecting them and then clicking the left arrow.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="86d8e-121">Im Raster werden Werte, die die Datentypen DT_DATE, DT_DBTIME2, DT_FILETIME, DT_DBTIMESTAMP, DT_DBTIMESTAMP2 und DT_DBTIMESTAMPOFFSET darstellen, als ISO 8601-formatierte Zeichenfolgen angezeigt, und das `T`-Trennzeichen wird durch ein Leerzeichen ersetzt.</span><span class="sxs-lookup"><span data-stu-id="86d8e-121">In the grid, values that represent the DT_DATE, DT_DBTIME2, DT_FILETIME, DT_DBTIMESTAMP, DT_DBTIMESTAMP2, and DT_DBTIMESTAMPOFFSET data types appear as ISO 8601 formatted strings and a space separator replaces the `T` separator.</span></span> <span data-ttu-id="86d8e-122">Werte, die den DT_DATE-Datentyp und den DT_FILETIME-Datentyp darstellen, enthalten sieben Ziffern für Sekundenbruchteile.</span><span class="sxs-lookup"><span data-stu-id="86d8e-122">Values that represent the DT_DATE and DT_FILETIME data types include seven digits for fractional seconds.</span></span> <span data-ttu-id="86d8e-123">Da der DT_FILETIME-Datentyp nur drei Ziffern von Sekundenbruchteilen speichert, zeigt das Raster Nullen für die restlichen vier Ziffern an.</span><span class="sxs-lookup"><span data-stu-id="86d8e-123">Because the DT_FILETIME data type stores only three digits of fractional seconds, the grid displays zeros for the remaining four digits.</span></span> <span data-ttu-id="86d8e-124">Werte, die den DT_DBTIMESTAMP-Datentyp darstellen, enthalten drei Ziffern für Sekundenbruchteile.</span><span class="sxs-lookup"><span data-stu-id="86d8e-124">Values that represent the DT_DBTIMESTAMP data type include three digits for fractional seconds.</span></span> <span data-ttu-id="86d8e-125">Für Werte, die die Datentypen DT_DBTIME2, DT_DBTIMESTAMP2 und DT_DBTIMESTAMPOFFSET darstellen, entspricht die Anzahl der Ziffern für Sekundenbruchteile der für den Datentyp der Spalte festgelegten Skala.</span><span class="sxs-lookup"><span data-stu-id="86d8e-125">For values that represent the DT_DBTIME2, DT_DBTIMESTAMP2, and DT_DBTIMESTAMPOFFSET data types, the number of digits for fractional seconds corresponds to the scale specified for the column's data type.</span></span> <span data-ttu-id="86d8e-126">Weitere Informationen zu ISO 8601-Formaten finden Sie unter [Date and Time Formats](../../2014/integration-services/date-and-time-formats.md).</span><span class="sxs-lookup"><span data-stu-id="86d8e-126">For more information about ISO 8601 formats, see [Date and Time Formats](../../2014/integration-services/date-and-time-formats.md).</span></span> <span data-ttu-id="86d8e-127">Weitere Informationen zu Datentypen finden Sie unter [Integration Services Data Types](data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="86d8e-127">For more information about data types, see [Integration Services Data Types](data-flow/integration-services-data-types.md).</span></span>  
  
10. <span data-ttu-id="86d8e-128">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="86d8e-128">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86d8e-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="86d8e-129">See Also</span></span>  
 <span data-ttu-id="86d8e-130">[SQL Server Integration Services-Transformationen](data-flow/transformations/integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="86d8e-130">[Integration Services Transformations](data-flow/transformations/integration-services-transformations.md) </span></span>  
 <span data-ttu-id="86d8e-131">[SQL Server Integration Services-Pfade](data-flow/integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="86d8e-131">[Integration Services Paths](data-flow/integration-services-paths.md) </span></span>  
 <span data-ttu-id="86d8e-132">[Datenfluss](data-flow/data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="86d8e-132">[Data Flow](data-flow/data-flow.md) </span></span>  
 [<span data-ttu-id="86d8e-133">Debuggen des Datenflusses</span><span class="sxs-lookup"><span data-stu-id="86d8e-133">Debugging Data Flow</span></span>](troubleshooting/debugging-data-flow.md)  
  
  
