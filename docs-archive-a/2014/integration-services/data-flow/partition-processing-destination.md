---
title: Ziel für Partitionsverarbeitung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.partitionprocessingdest.f1
helpviewer_keywords:
- partitions [Analysis Services], processing
- Partition Processing destination [Integration Services]
- destinations [Integration Services], Partition Processing
ms.assetid: 36c592ff-3f78-4a58-b496-31c1c8eee131
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d32306328f7a0575e55397d5209b4767d0cf1bd6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615472"
---
# <a name="partition-processing-destination"></a><span data-ttu-id="fb4cd-102">Ziel für Partitionsverarbeitung</span><span class="sxs-lookup"><span data-stu-id="fb4cd-102">Partition Processing Destination</span></span>
  <span data-ttu-id="fb4cd-103">Das Ziel für Partitionsverarbeitung lädt und verarbeitet eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]-Partition.</span><span class="sxs-lookup"><span data-stu-id="fb4cd-103">The Partition Processing destination loads and processes an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] partition.</span></span> <span data-ttu-id="fb4cd-104">Weitere Informationen zu Partitionen finden Sie unter [Partitionen &#40;Analysis Services – Mehrdimensionale Daten&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data).</span><span class="sxs-lookup"><span data-stu-id="fb4cd-104">For more information about partitions, see [Partitions &#40;Analysis Services - Multidimensional Data&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data).</span></span>  
  
 <span data-ttu-id="fb4cd-105">Das Ziel für Partitionsverarbeitung schließt die folgenden Funktionen ein:</span><span class="sxs-lookup"><span data-stu-id="fb4cd-105">The Partition Processing destination includes the following features:</span></span>  
  
-   <span data-ttu-id="fb4cd-106">Optionen für die inkrementelle Verarbeitung, vollständige Verarbeitung oder Updateverarbeitung.</span><span class="sxs-lookup"><span data-stu-id="fb4cd-106">Options to perform incremental, full, or update processing.</span></span>  
  
-   <span data-ttu-id="fb4cd-107">Fehlerkonfiguration, um anzugeben, ob die Verarbeitung Fehler ignoriert oder nach einer bestimmten Anzahl von Fehlern beendet wird.</span><span class="sxs-lookup"><span data-stu-id="fb4cd-107">Error configuration, to specify whether processing ignores errors or stops after a specified number of errors.</span></span>  
  
-   <span data-ttu-id="fb4cd-108">Zuordnung von Eingabespalten zu Partitionsspalten.</span><span class="sxs-lookup"><span data-stu-id="fb4cd-108">Mapping of input columns to partition columns.</span></span>  
  
 <span data-ttu-id="fb4cd-109">Weitere Informationen zum Verarbeiten von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]-Objekten finden Sie unter [Verarbeitungsoptionen und -einstellungen &#40;Analysis Services&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/processing-options-and-settings-analysis-services).</span><span class="sxs-lookup"><span data-stu-id="fb4cd-109">For more information about processing [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects, see [Processing Options and Settings &#40;Analysis Services&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/processing-options-and-settings-analysis-services).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fb4cd-110">Hier beschriebene Tasks gelten nicht für tabellarische Analysis Services-Modelle.</span><span class="sxs-lookup"><span data-stu-id="fb4cd-110">Tasks described here do not apply to Analysis Services tabular models.</span></span>  <span data-ttu-id="fb4cd-111">Sie können Partitionsspalten für tabellarische Modelle keine Eingabespalten zuordnen.</span><span class="sxs-lookup"><span data-stu-id="fb4cd-111">You cannot map input columns to partition columns for tabular models.</span></span> <span data-ttu-id="fb4cd-112">Sie können stattdessen den Analysis Services-Task "DDL ausführen" [Analysis Services Execute DDL Task](../control-flow/analysis-services-execute-ddl-task.md) verwenden, um die Partition zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="fb4cd-112">You can instead use the Analysis Services Execute DDL task [Analysis Services Execute DDL Task](../control-flow/analysis-services-execute-ddl-task.md) to process the partition.</span></span>  
  
## <a name="configuration-of-the-partition-processing-destination"></a><span data-ttu-id="fb4cd-113">Konfiguration des Ziels für die Partitionsverarbeitung</span><span class="sxs-lookup"><span data-stu-id="fb4cd-113">Configuration of the Partition Processing Destination</span></span>  
 <span data-ttu-id="fb4cd-114">Das Ziel für Partitionsverarbeitung stellt mithilfe eines Verbindungs-Managers für [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] eine Verbindung mit dem [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Projekt oder der Instanz von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] her, die die vom Ziel verarbeiteten Cubes und Partitionen enthält.</span><span class="sxs-lookup"><span data-stu-id="fb4cd-114">The Partition Processing destination uses an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] connection manager to connect to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project or the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] that contains the cubes and partitions the destination processes.</span></span> <span data-ttu-id="fb4cd-115">Weitere Informationen finden Sie unter [Analysis Services Connection Manager](../connection-manager/analysis-services-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="fb4cd-115">For more information, see [Analysis Services Connection Manager](../connection-manager/analysis-services-connection-manager.md).</span></span>  
  
 <span data-ttu-id="fb4cd-116">Das Ziel weist eine Eingabe auf.</span><span class="sxs-lookup"><span data-stu-id="fb4cd-116">This destination has one input.</span></span> <span data-ttu-id="fb4cd-117">Eine Fehlerausgabe wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fb4cd-117">It does not support an error output.</span></span>  
  
 <span data-ttu-id="fb4cd-118">Sie können Eigenschaften mit dem [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer oder programmgesteuert festlegen.</span><span class="sxs-lookup"><span data-stu-id="fb4cd-118">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="fb4cd-119">Klicken Sie auf eines der folgenden Themen, um weitere Informationen zu den Eigenschaften zu erhalten, die Sie im Dialogfeld **Ziel-Editor für Partitionsverarbeitung** festlegen können:</span><span class="sxs-lookup"><span data-stu-id="fb4cd-119">For more information about the properties that you can set in the Partition Processing **Destination Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="fb4cd-120">Ziel-Editor für Partitionsverarbeitung &#40;Seite „Verbindungs-Manager“&#41;</span><span class="sxs-lookup"><span data-stu-id="fb4cd-120">Partition Processing Destination Editor &#40;Connection Manager Page&#41;</span></span>](../partition-processing-destination-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="fb4cd-121">Ziel-Editor für Partitionsverarbeitung &#40;Seite Zuordnungen&#41;</span><span class="sxs-lookup"><span data-stu-id="fb4cd-121">Partition Processing Destination Editor &#40;Mappings Page&#41;</span></span>](../partition-processing-destination-editor-mappings-page.md)  
  
-   [<span data-ttu-id="fb4cd-122">Ziel-Editor für Partitionsverarbeitung &#40;Seite „Erweitert“&#41;</span><span class="sxs-lookup"><span data-stu-id="fb4cd-122">Partition Processing Destination Editor &#40;Advanced Page&#41;</span></span>](../partition-processing-destination-editor-advanced-page.md)  
  
 <span data-ttu-id="fb4cd-123">Das Dialogfeld **Erweiterter Editor** enthält die Eigenschaften, die programmgesteuert festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="fb4cd-123">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="fb4cd-124">Klicken Sie auf eines der folgenden Themen, um weitere Informationen zu den Eigenschaften zu erhalten, die Sie im Dialogfeld **Erweiterter Editor** oder programmgesteuert festlegen können:</span><span class="sxs-lookup"><span data-stu-id="fb4cd-124">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="fb4cd-125">Common Properties</span><span class="sxs-lookup"><span data-stu-id="fb4cd-125">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="fb4cd-126">Benutzerdefinierte Eigenschaften des Ziels für Partitionsverarbeitung</span><span class="sxs-lookup"><span data-stu-id="fb4cd-126">Partition Processing Destination Custom Properties</span></span>](partition-processing-destination-custom-properties.md)  
  
 <span data-ttu-id="fb4cd-127">Informationen zum Festlegen der Eigenschaften finden Sie unter [Festlegen der Eigenschaften einer Datenflusskomponente](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="fb4cd-127">For more information about how to set the properties, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
  
