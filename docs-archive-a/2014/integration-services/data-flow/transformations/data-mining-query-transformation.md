---
title: Transformation für Data Mining-Abfragen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dataminingquerytrans.f1
helpviewer_keywords:
- Data Mining Query transformation
- prediction queries [Integration Services]
ms.assetid: 7960133b-a3e1-48af-ba43-55ed78c38e71
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 278fdc3b1abd38b63f01e967e28d11983a09e682
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608772"
---
# <a name="data-mining-query-transformation"></a><span data-ttu-id="59866-102">Transformation für Data Mining-Abfragen</span><span class="sxs-lookup"><span data-stu-id="59866-102">Data Mining Query Transformation</span></span>
  <span data-ttu-id="59866-103">Die Transformation für Data Mining-Abfragen führt Vorhersageabfragen für Data Mining-Modelle aus.</span><span class="sxs-lookup"><span data-stu-id="59866-103">The Data Mining Query transformation performs prediction queries against data mining models.</span></span> <span data-ttu-id="59866-104">Diese Transformation enthält einen Abfrage-Generator zum Erstellen von DMX-Abfragen (Data Mining Extensions).</span><span class="sxs-lookup"><span data-stu-id="59866-104">This transformation contains a query builder for creating Data Mining Extensions (DMX) queries.</span></span> <span data-ttu-id="59866-105">Mit dem Abfrage-Generator können Sie mithilfe der DMX-Sprache benutzerdefinierte Anweisungen erstellen, um Transformationseingabedaten mit einem vorhandenen Miningmodell zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="59866-105">The query builder lets you create custom statements for evaluating the transformation input data against an existing mining model using the DMX language.</span></span> <span data-ttu-id="59866-106">Weitere Informationen finden Sie unter [Data Mining-Erweiterungen &#40;DMX&#41; – Referenz](/sql/dmx/data-mining-extensions-dmx-reference).</span><span class="sxs-lookup"><span data-stu-id="59866-106">For more information, see [Data Mining Extensions &#40;DMX&#41; Reference](/sql/dmx/data-mining-extensions-dmx-reference).</span></span>  
  
 <span data-ttu-id="59866-107">Eine Transformation kann mehrere Vorhersageabfragen ausführen, falls die Modelle mit der gleichen Data Mining-Struktur erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="59866-107">One transformation can execute multiple prediction queries if the models are built on the same data mining structure.</span></span> <span data-ttu-id="59866-108">Weitere Informationen finden Sie unter [Data Mining-Abfrageschnittstellen](https://docs.microsoft.com/analysis-services/data-mining/data-mining-query-tools).</span><span class="sxs-lookup"><span data-stu-id="59866-108">For more information, see [Data Mining Query Interfaces](https://docs.microsoft.com/analysis-services/data-mining/data-mining-query-tools).</span></span>  
  
## <a name="configuration-of-the-data-mining-query-transformation"></a><span data-ttu-id="59866-109">Konfiguration der Transformation für Data Mining-Abfragen</span><span class="sxs-lookup"><span data-stu-id="59866-109">Configuration of the Data Mining Query Transformation</span></span>  
 <span data-ttu-id="59866-110">Die Transformation für Data Mining-Abfragen stellt mithilfe eines Verbindungs-Managers für [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] eine Verbindung mit dem [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] -Projekt oder der Instanz von [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] her, die die Miningstruktur und die Miningmodelle enthält.</span><span class="sxs-lookup"><span data-stu-id="59866-110">The Data Mining Query transformation uses an [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] connection manager to connect to the [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] project or the instance of [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] that contains the mining structure and mining models.</span></span> <span data-ttu-id="59866-111">Weitere Informationen finden Sie unter [Analysis Services Connection Manager](../../connection-manager/analysis-services-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="59866-111">For more information, see [Analysis Services Connection Manager](../../connection-manager/analysis-services-connection-manager.md).</span></span>  
  
 <span data-ttu-id="59866-112">Diese Transformation weist je eine Eingabe und eine Ausgabe auf.</span><span class="sxs-lookup"><span data-stu-id="59866-112">This transformation has one input and one output.</span></span> <span data-ttu-id="59866-113">Eine Fehlerausgabe wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="59866-113">It does not support an error output.</span></span>  
  
 <span data-ttu-id="59866-114">Sie können Eigenschaften mit dem [!INCLUDE[ssIS](../../../includes/ssis-md.md)] -Designer oder programmgesteuert festlegen.</span><span class="sxs-lookup"><span data-stu-id="59866-114">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="59866-115">Klicken Sie auf eines der folgenden Themen, um weitere Informationen zu den Eigenschaften zu erhalten, die Sie im Dialogfeld **Transformations-Editor für Data Mining-Abfragen** festlegen können:</span><span class="sxs-lookup"><span data-stu-id="59866-115">For more information about the properties that you can set in the **Data Mining Query Transformation Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="59866-116">Transformations-Editor für Data Mining-Abfragen &#40;Registerkarte „Miningmodell“&#41;</span><span class="sxs-lookup"><span data-stu-id="59866-116">Data Mining Query Transformation Editor &#40;Mining Model Tab&#41;</span></span>](../../data-mining-query-transformation-editor-mining-model-tab.md)  
  
-   [<span data-ttu-id="59866-117">Transformations-Editor für Data Mining-Abfragen &#40;Registerkarte „Miningmodell“&#41;</span><span class="sxs-lookup"><span data-stu-id="59866-117">Data Mining Query Transformation Editor &#40;Mining Model Tab&#41;</span></span>](../../data-mining-query-transformation-editor-mining-model-tab.md)  
  
 <span data-ttu-id="59866-118">Das Dialogfeld **Erweiterter Editor** enthält die Eigenschaften, die programmgesteuert festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="59866-118">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="59866-119">Klicken Sie auf eines der folgenden Themen, um weitere Informationen zu den Eigenschaften zu erhalten, die Sie im Dialogfeld **Erweiterter Editor** oder programmgesteuert festlegen können:</span><span class="sxs-lookup"><span data-stu-id="59866-119">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="59866-120">Common Properties</span><span class="sxs-lookup"><span data-stu-id="59866-120">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="59866-121">Benutzerdefinierte Eigenschaften von Transformationen</span><span class="sxs-lookup"><span data-stu-id="59866-121">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
 <span data-ttu-id="59866-122">Weitere Informationen zum Festlegen der Eigenschaften finden Sie unter [Festlegen der Eigenschaften einer Datenflusskomponente](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="59866-122">For more information about how to set properties, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
  
