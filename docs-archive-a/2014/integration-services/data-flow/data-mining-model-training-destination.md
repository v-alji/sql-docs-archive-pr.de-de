---
title: Ziel des Data Mining-Modelltrainings | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dataminingmodeltrainingdest.f1
helpviewer_keywords:
- destinations [Integration Services], Data Mining Model Training
- Data Mining Model Training destination
- mining models [Analysis Services], training
- training mining models
ms.assetid: 6bc8cbe2-46af-4f7b-93d6-86779313c9d7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e101a7e374f16b12b3a5aa30a49dbecd2632f06f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618830"
---
# <a name="data-mining-model-training-destination"></a><span data-ttu-id="a79ae-102">Ziel des Data Mining-Modelltrainings</span><span class="sxs-lookup"><span data-stu-id="a79ae-102">Data Mining Model Training Destination</span></span>
  <span data-ttu-id="a79ae-103">Das Ziel des Data Mining-Modelltrainings trainiert Data Mining-Modelle, indem die Daten, die vom Ziel empfangen werden, über Data Mining-Modellalgorithmen übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="a79ae-103">The Data Mining Model Training destination trains data mining models by passing the data that the destination receives through the data mining model algorithms.</span></span> <span data-ttu-id="a79ae-104">Mehrere Data Mining-Modelle können von einem Ziel trainiert werden, falls die Modelle mit der gleichen Data Mining-Struktur erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="a79ae-104">Multiple data mining models can be trained by one destination if the models are built on the same data mining structure.</span></span> <span data-ttu-id="a79ae-105">Weitere Informationen finden Sie unter [Mining Structure Columns](https://docs.microsoft.com/analysis-services/data-mining/mining-structure-columns) und [Mining Model Columns](https://docs.microsoft.com/analysis-services/data-mining/mining-model-columns).</span><span class="sxs-lookup"><span data-stu-id="a79ae-105">For more information, see [Mining Structure Columns](https://docs.microsoft.com/analysis-services/data-mining/mining-structure-columns) and [Mining Model Columns](https://docs.microsoft.com/analysis-services/data-mining/mining-model-columns).</span></span>  
  
## <a name="configuration-of-the-data-mining-model-training-destination"></a><span data-ttu-id="a79ae-106">Konfiguration des Ziels des Data Mining-Modelltrainings</span><span class="sxs-lookup"><span data-stu-id="a79ae-106">Configuration of the Data Mining Model Training Destination</span></span>  
 <span data-ttu-id="a79ae-107">Wenn eine Spalte auf Fallebene der Zielstruktur und die Modelle, die mit der Struktur erstellt wurden, den Inhaltstyp KEY TIME oder KEY SEQUENCE aufweisen, müssen die Eingabedaten nach dieser Spalte sortiert werden.</span><span class="sxs-lookup"><span data-stu-id="a79ae-107">If a case level column of the target structure and the models built on the structure has the content type KEY TIME or KEY SEQUENCE, the input data must be sorted on that column.</span></span> <span data-ttu-id="a79ae-108">Beispielsweise verwenden Modelle, die mit dem Microsoft Time Series-Algorithmus erstellt wurden, den KEY TIME-Inhaltstyp.</span><span class="sxs-lookup"><span data-stu-id="a79ae-108">For example, models built using the Microsoft Time Series algorithm use the content type KEY TIME.</span></span> <span data-ttu-id="a79ae-109">Falls Eingabedaten nicht sortiert sind, wird beim Verarbeiten des Modells möglicherweise ein Fehler gemeldet.</span><span class="sxs-lookup"><span data-stu-id="a79ae-109">If input data is not sorted, the processing of the model may fail.</span></span> <span data-ttu-id="a79ae-110">Falls die Daten sortiert werden müssen, können sie mithilfe einer Transformation zum Sortieren in einer früheren Phase des Datenflusses sortiert werden.</span><span class="sxs-lookup"><span data-stu-id="a79ae-110">If the data requires sorting, you can use a Sort transformation earlier in the data flow to sort the data.</span></span> <span data-ttu-id="a79ae-111">Diese Anforderung gilt nicht für Spalten mit dem KEY-Inhaltstyp.</span><span class="sxs-lookup"><span data-stu-id="a79ae-111">This requirement does not apply to columns with the KEY content type.</span></span> <span data-ttu-id="a79ae-112">Weitere Informationen finden Sie unter [Inhaltstypen &#40;Data Mining&#41;](https://docs.microsoft.com/analysis-services/data-mining/content-types-data-mining) und [Transformation zum Sortieren](transformations/sort-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="a79ae-112">For more information, see [Content Types &#40;Data Mining&#41;](https://docs.microsoft.com/analysis-services/data-mining/content-types-data-mining) and [Sort Transformation](transformations/sort-transformation.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a79ae-113">Die Eingabe des Zieles für das Data Mining-Modelltraining muss sortiert werden.</span><span class="sxs-lookup"><span data-stu-id="a79ae-113">The input to the Data Mining Model training destination must be sorted.</span></span> <span data-ttu-id="a79ae-114">Zum Sortieren der Daten können Sie ein Upstreamsortierungsziel aus dem Ziel des Data Mining-Modelltrainings in den Datenfluss einschließen.</span><span class="sxs-lookup"><span data-stu-id="a79ae-114">To sort the data, you can include a Sort destination upstream from the Data Mining Model Training destination in the data flow.</span></span> <span data-ttu-id="a79ae-115">Weitere Informationen finden Sie unter [Sort Transformation](transformations/sort-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="a79ae-115">For more information, see [Sort Transformation](transformations/sort-transformation.md).</span></span>  
  
 <span data-ttu-id="a79ae-116">Dieses Ziel weist eine Eingabe und keine Ausgabe auf.</span><span class="sxs-lookup"><span data-stu-id="a79ae-116">This destination has one input and no output.</span></span>  
  
 <span data-ttu-id="a79ae-117">Das Ziel des Data Mining-Modelltrainings stellt mithilfe eines Verbindungs-Managers für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] eine Verbindung mit dem [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]-Projekt oder der Instanz von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] her, die die Miningstruktur und die Miningmodelle enthält, die vom Ziel trainiert werden.</span><span class="sxs-lookup"><span data-stu-id="a79ae-117">The Data Mining Model Training destination uses an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] connection manager to connect to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project or the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] that contains the mining structure and mining models that the destination trains.</span></span> <span data-ttu-id="a79ae-118">Weitere Informationen finden Sie unter [Analysis Services Connection Manager](../connection-manager/analysis-services-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="a79ae-118">For more information, see [Analysis Services Connection Manager](../connection-manager/analysis-services-connection-manager.md).</span></span>  
  
 <span data-ttu-id="a79ae-119">Sie können Eigenschaften mit dem [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer oder programmgesteuert festlegen.</span><span class="sxs-lookup"><span data-stu-id="a79ae-119">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="a79ae-120">Klicken Sie auf eines der folgenden Themen, um weitere Informationen zu den Eigenschaften zu erhalten, die Sie im Dialogfeld **Trainings-Editor für Data Mining-Modelle** festlegen können:</span><span class="sxs-lookup"><span data-stu-id="a79ae-120">For more information about the properties that you can set in the **Data Mining Model Training Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="a79ae-121">Trainings-Editor für Data Mining-Modelle &#40;Registerkarte Verbindung&#41;</span><span class="sxs-lookup"><span data-stu-id="a79ae-121">Data Mining Model Training Editor &#40;Connection Tab&#41;</span></span>](../data-mining-model-training-editor-connection-tab.md)  
  
-   [<span data-ttu-id="a79ae-122">Trainings-Editor für Data Mining-Modelle &#40;Registerkarte Spalten&#41;</span><span class="sxs-lookup"><span data-stu-id="a79ae-122">Data Mining Model Training Editor &#40;Columns Tab&#41;</span></span>](../data-mining-model-training-editor-columns-tab.md)  
  
 <span data-ttu-id="a79ae-123">Das Dialogfeld **Erweiterter Editor** enthält die Eigenschaften, die programmgesteuert festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="a79ae-123">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="a79ae-124">Klicken Sie auf eines der folgenden Themen, um weitere Informationen zu den Eigenschaften zu erhalten, die Sie im Dialogfeld **Erweiterter Editor** oder programmgesteuert festlegen können:</span><span class="sxs-lookup"><span data-stu-id="a79ae-124">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="a79ae-125">Common Properties</span><span class="sxs-lookup"><span data-stu-id="a79ae-125">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="a79ae-126">Benutzerdefinierte Eigenschaften des Ziels des Data Mining-Modelltrainings</span><span class="sxs-lookup"><span data-stu-id="a79ae-126">Data Mining Model Training Destination Custom Properties</span></span>](data-mining-model-training-destination-custom-properties.md)  
  
 <span data-ttu-id="a79ae-127">Weitere Informationen zum Festlegen der Eigenschaften finden Sie unter [Festlegen der Eigenschaften einer Datenflusskomponente](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="a79ae-127">For more information about how to set properties, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
  
