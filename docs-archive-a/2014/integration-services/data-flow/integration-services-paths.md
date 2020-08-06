---
title: SQL Server Integration Services-Pfade | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- paths [Integration Services], about paths
- data flow [Integration Services], paths
- paths [Integration Services]
- destinations [Integration Services], paths
- sources [Integration Services], paths
ms.assetid: 6c4629a9-2ede-4011-9101-3b342249640e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c52bbd06974311a7fc94b3058309399d70df0034
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700119"
---
# <a name="integration-services-paths"></a><span data-ttu-id="a336a-102">SQL Server Integration Services-Pfade</span><span class="sxs-lookup"><span data-stu-id="a336a-102">Integration Services Paths</span></span>
  <span data-ttu-id="a336a-103">Ein Pfad verbindet zwei Komponenten in einem Datenfluss, indem die Ausgabe einer Datenflusskomponente mit der Eingabe einer anderen Komponente verbunden wird.</span><span class="sxs-lookup"><span data-stu-id="a336a-103">A path connects two components in a data flow by connecting the output of one data flow component to the input of another component.</span></span> <span data-ttu-id="a336a-104">Ein Pfad weist eine Quelle und ein Ziel auf.</span><span class="sxs-lookup"><span data-stu-id="a336a-104">A path has a source and a destination.</span></span> <span data-ttu-id="a336a-105">Wenn z. B. ein Pfad eine Verbindung mit einer OLE DB-Quelle und einer Transformation zum Sortieren herstellt, ist die OLE DB-Quelle die Quelle des Pfads, und die Transformation zum Sortieren ist das Ziel des Pfads.</span><span class="sxs-lookup"><span data-stu-id="a336a-105">For example, if a path connects an OLE DB source and a Sort transformation, the OLE DB source is the source of the path, and the Sort transformation is the destination of the path.</span></span> <span data-ttu-id="a336a-106">Die Quelle ist die Komponente, wo der Pfad beginnt, und das Ziel ist die Komponente, wo der Pfad endet.</span><span class="sxs-lookup"><span data-stu-id="a336a-106">The source is the component where the path starts, and the destination is the component where the path ends.</span></span>  
  
 <span data-ttu-id="a336a-107">Wenn Sie ein Paket im [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer ausführen, können Sie die Daten in einem Datenfluss anzeigen, indem Sie Daten-Viewer an einen Pfad anfügen.</span><span class="sxs-lookup"><span data-stu-id="a336a-107">If you run a package in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, you can view the data in a data flow by attaching data viewers to a path.</span></span> <span data-ttu-id="a336a-108">Ein Daten-Viewer kann zur Anzeige von Daten in einem Raster konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="a336a-108">A data viewer can be configured to display data in a grid.</span></span> <span data-ttu-id="a336a-109">Ein Daten-Viewer ist ein hilfreiches Tool zum Debuggen.</span><span class="sxs-lookup"><span data-stu-id="a336a-109">A data viewer is a useful debugging tool.</span></span> <span data-ttu-id="a336a-110">Weitere Informationen finden Sie unter [Debugging Data Flow](../troubleshooting/debugging-data-flow.md).</span><span class="sxs-lookup"><span data-stu-id="a336a-110">For more information, see [Debugging Data Flow](../troubleshooting/debugging-data-flow.md).</span></span>  
  
## <a name="configuration-of-the-path"></a><span data-ttu-id="a336a-111">Konfiguration des Pfads</span><span class="sxs-lookup"><span data-stu-id="a336a-111">Configuration of the Path</span></span>  
 <span data-ttu-id="a336a-112">Der [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer stellt das Dialogfeld **Datenflusspfad-Editor** bereit, in dem Sie Pfadeigenschaften festlegen, die Metadaten der Datenspalten, die über den Pfad übergeben werden, anzeigen sowie Daten-Viewer konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="a336a-112">The [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer provides the **Data Flow Path Editor** dialog box for setting path properties, viewing the metadata of the data columns that pass through the path, and configuring data viewers.</span></span>  
  
 <span data-ttu-id="a336a-113">Zu den konfigurierbaren Pfadeigenschaften gehört der Name, die Beschreibung und die Anmerkung des Pfads.</span><span class="sxs-lookup"><span data-stu-id="a336a-113">The configurable path properties include the name, description, and annotation of the path.</span></span> <span data-ttu-id="a336a-114">Pfade können auch programmgesteuert konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="a336a-114">You can also configure paths programmatically.</span></span> <span data-ttu-id="a336a-115">Weitere Informationen finden Sie unter [Programmgesteuertes Verbinden von Datenflusskomponenten](../building-packages-programmatically/connecting-data-flow-components-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="a336a-115">For more information, see [Connecting Data Flow Components Programmatically](../building-packages-programmatically/connecting-data-flow-components-programmatically.md).</span></span>  
  
 <span data-ttu-id="a336a-116">Eine Pfadanmerkung zeigt den Namen der Pfadquelle oder den Pfadnamen in der Entwurfsoberfläche der Registerkarte **Datenfluss** im [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer an.</span><span class="sxs-lookup"><span data-stu-id="a336a-116">A path annotation displays the name of the path source or the path name on the design surface of the **Data Flow** tab in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="a336a-117">Pfadanmerkungen sind mit den Anmerkungen vergleichbar, die Sie Datenflüssen, Ablaufsteuerungen und Ereignishandlern hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="a336a-117">Path annotations are similar to the annotations you can add to data flows, control flows, and event handlers.</span></span> <span data-ttu-id="a336a-118">Der einzige Unterschied besteht darin, dass eine Pfadanmerkung einem Pfad hinzugefügt wird, während andere Anmerkungen auf den Registerkarten **Datenfluss**, **Ablaufsteuerung**und **Ereignishandler**des [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designers angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="a336a-118">The only difference is that a path annotation is attached to a path, whereas other annotations appear on the **Data Flow**, **Control Flow**, and **Event Handle**r tabs of [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="a336a-119">Die Metadaten zeigen den Namen, den Datentyp, die Genauigkeit, die Dezimalstellen, die Länge, die Codepage und die Quellkomponente jeder Spalte in der Ausgabe der vorherigen Komponente an.</span><span class="sxs-lookup"><span data-stu-id="a336a-119">The metadata shows the name, data type, precision, scale, length, code page, and source component of each column in the output of the previous component.</span></span> <span data-ttu-id="a336a-120">Die Quellkomponente ist jene Datenflusskomponente, die die Spalte erstellt hat.</span><span class="sxs-lookup"><span data-stu-id="a336a-120">The source component is the data flow component that created the column.</span></span> <span data-ttu-id="a336a-121">Dies kann, muss aber nicht die erste Komponente im Datenfluss sein.</span><span class="sxs-lookup"><span data-stu-id="a336a-121">This may or may not be the first component in the data flow.</span></span> <span data-ttu-id="a336a-122">Beispielsweise werden mit einer Transformation für UNION ALL und einer Transformation zum Sortieren eigene Spalten erstellt, die die Quelle der Ausgabespalten sind.</span><span class="sxs-lookup"><span data-stu-id="a336a-122">For example, the Union All and Sort transformations create their own columns, and they are the sources of their output columns.</span></span> <span data-ttu-id="a336a-123">Dagegen können Spalten mit einer Transformation für das Kopieren von Spalten durchlaufen werden, ohne sie zu ändern. Es können auch neue Spalten erstellt werden, indem Eingabespalten kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="a336a-123">In contrast, a Copy Column transformation can pass through columns without changing them or can create new columns by copying input columns.</span></span> <span data-ttu-id="a336a-124">Die Transformation für das Kopieren von Spalten ist nur für neue Spalten die Quellkomponente.</span><span class="sxs-lookup"><span data-stu-id="a336a-124">The Copy Column transformation is the source component only of the new columns.</span></span>  
  
 <span data-ttu-id="a336a-125">Sie können Eigenschaften mit dem [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer oder programmgesteuert festlegen.</span><span class="sxs-lookup"><span data-stu-id="a336a-125">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="a336a-126">Klicken Sie auf eines der folgenden Themen, um weitere Informationen zu den Eigenschaften zu erhalten, die Sie im Dialogfeld **Datenflusspfad-Editor** festlegen können:</span><span class="sxs-lookup"><span data-stu-id="a336a-126">For more information about the properties that you can set in the **Data Flow Path Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="a336a-127">Datenfluss Pfad-Editor &#40;Seite "Allgemein"&#41;</span><span class="sxs-lookup"><span data-stu-id="a336a-127">Data Flow Path Editor &#40;General Page&#41;</span></span>](../general-page-of-integration-services-designers-options.md)  
  
-   [<span data-ttu-id="a336a-128">Datenfluss Pfad-Editor &#40;Seite "Metadaten"&#41;</span><span class="sxs-lookup"><span data-stu-id="a336a-128">Data Flow Path Editor &#40;Metadata Page&#41;</span></span>](../data-flow-path-editor-metadata-page.md)  
  
-   [<span data-ttu-id="a336a-129">Datenfluss Pfad-Editor &#40;Seite "Daten-Viewer"&#41;</span><span class="sxs-lookup"><span data-stu-id="a336a-129">Data Flow Path Editor &#40;Data Viewers Page&#41;</span></span>](../data-flow-path-editor-data-viewers-page.md)  
  
 <span data-ttu-id="a336a-130">Weitere Informationen zu den Eigenschaften, die Sie programmgesteuert festlegen können, finden Sie unter [Path Properties](../path-properties.md).</span><span class="sxs-lookup"><span data-stu-id="a336a-130">For more information about the properties that you can set programmatically, see [Path Properties](../path-properties.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="a336a-131">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="a336a-131">Related Tasks</span></span>  
  
-   [<span data-ttu-id="a336a-132">Anzeigen von Pfadmetadaten im Datenflusspfad-Editor</span><span class="sxs-lookup"><span data-stu-id="a336a-132">View Path Metadata in the Data Flow Path Editor</span></span>](../view-path-metadata-in-the-data-flow-path-editor.md)  
  
-   [<span data-ttu-id="a336a-133">Verbinden von Komponenten in einem Datenfluss</span><span class="sxs-lookup"><span data-stu-id="a336a-133">Connect Components in a Data Flow</span></span>](connect-components-in-a-data-flow.md)  
  
## <a name="see-also"></a><span data-ttu-id="a336a-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a336a-134">See Also</span></span>  
 [<span data-ttu-id="a336a-135">Datenfluss</span><span class="sxs-lookup"><span data-stu-id="a336a-135">Data Flow</span></span>](data-flow.md)  
  
  
