---
title: Pfad Eigenschaften | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- paths [Integration Services], properties
ms.assetid: 89b1e347-9579-4f6b-af74-c6519ea08eea
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ca263b866fb6d5d7ceb6352f708f387d79cad4f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609296"
---
# <a name="path-properties"></a><span data-ttu-id="e5a2b-102">Pfadeigenschaften</span><span class="sxs-lookup"><span data-stu-id="e5a2b-102">Path Properties</span></span>
  <span data-ttu-id="e5a2b-103">Die Datenfluss Objekte im- [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Objektmodell verfügen über allgemeine Eigenschaften und benutzerdefinierte Eigenschaften auf der Ebene der Komponente, Eingaben und Ausgaben sowie Eingabe-und Ausgabespalten.</span><span class="sxs-lookup"><span data-stu-id="e5a2b-103">The data flow objects in the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] object model have common properties and custom properties at the level of the component, inputs and outputs, and input columns and output columns.</span></span> <span data-ttu-id="e5a2b-104">Viele Eigenschaften verfügen über schreibgeschützte Werte, für die zur Laufzeit eine Zuweisung über die Datenfluss-Engine erfolgt.</span><span class="sxs-lookup"><span data-stu-id="e5a2b-104">Many properties have read-only values that are assigned at run time by the data flow engine.</span></span>  
  
 <span data-ttu-id="e5a2b-105">In diesem Thema werden die benutzerdefinierten Eigenschaften der Pfade, die Datenflussobjekte verbinden, aufgelistet und beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e5a2b-105">This topic lists and describes the custom properties of the paths that connect data flow objects.</span></span>  
  
## <a name="path-properties"></a><span data-ttu-id="e5a2b-106">Pfadeigenschaften</span><span class="sxs-lookup"><span data-stu-id="e5a2b-106">Path Properties</span></span>  
 <span data-ttu-id="e5a2b-107">Im [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]-Objektmodell implementiert ein Pfad, der Komponenten im Datenfluss verbindet, die Schnittstelle <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100>.</span><span class="sxs-lookup"><span data-stu-id="e5a2b-107">In the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] object model, a path that connects components in the data flow implements the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100> interface.</span></span>  
  
 <span data-ttu-id="e5a2b-108">Die folgende Tabelle beschreibt die konfigurierbaren Eigenschaften der Pfade in einem Datenfluss.</span><span class="sxs-lookup"><span data-stu-id="e5a2b-108">The following table describes the configurable properties of the paths in a data flow.</span></span> <span data-ttu-id="e5a2b-109">Die Datenfluss-Engine weist auch zusätzlichen schreibgeschützten Eigenschaften, die nicht hier aufgelistet sind, Werte zu.</span><span class="sxs-lookup"><span data-stu-id="e5a2b-109">The data flow engine also assigns values to additional read-only properties that are not listed here.</span></span>  
  
|<span data-ttu-id="e5a2b-110">Eigenschaftenname</span><span class="sxs-lookup"><span data-stu-id="e5a2b-110">Property name</span></span>|<span data-ttu-id="e5a2b-111">Datentyp</span><span class="sxs-lookup"><span data-stu-id="e5a2b-111">Data Type</span></span>|<span data-ttu-id="e5a2b-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e5a2b-112">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="e5a2b-113">PathAnnotation</span><span class="sxs-lookup"><span data-stu-id="e5a2b-113">PathAnnotation</span></span>|<span data-ttu-id="e5a2b-114">Ganze Zahl (Enumeration)</span><span class="sxs-lookup"><span data-stu-id="e5a2b-114">Integer (enumeration)</span></span>|<span data-ttu-id="e5a2b-115">Ein Wert, der angibt, ob eine Anmerkung mit dem Pfad auf der Designeroberfläche angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="e5a2b-115">A value that indicates whether an annotation should be displayed with the path on the designer surface.</span></span> <span data-ttu-id="e5a2b-116">Die möglichen Werte sind `AsNeeded`, `SourceName`, `PathName` und `Never`.</span><span class="sxs-lookup"><span data-stu-id="e5a2b-116">The possible values are `AsNeeded`, `SourceName`, `PathName`, and `Never`.</span></span> <span data-ttu-id="e5a2b-117">Standardwert: `AsNeeded`.</span><span class="sxs-lookup"><span data-stu-id="e5a2b-117">The default value is `AsNeeded`.</span></span>|  
|<span data-ttu-id="e5a2b-118">DestinationName</span><span class="sxs-lookup"><span data-stu-id="e5a2b-118">DestinationName</span></span>|<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100>|<span data-ttu-id="e5a2b-119">Die dem Pfad zugeordnete Eingabe.</span><span class="sxs-lookup"><span data-stu-id="e5a2b-119">The input associated with the path.</span></span>|  
|<span data-ttu-id="e5a2b-120">SourceName</span><span class="sxs-lookup"><span data-stu-id="e5a2b-120">SourceName</span></span>|<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100>|<span data-ttu-id="e5a2b-121">Die dem Pfad zugeordnete Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="e5a2b-121">The output associated with the path.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e5a2b-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e5a2b-122">See Also</span></span>  
 <span data-ttu-id="e5a2b-123">[SQL Server Integration Services-Pfade](data-flow/integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="e5a2b-123">[Integration Services Paths](data-flow/integration-services-paths.md) </span></span>  
 <span data-ttu-id="e5a2b-124">[Allgemeine Eigenschaften](../../2014/integration-services/common-properties.md) </span><span class="sxs-lookup"><span data-stu-id="e5a2b-124">[Common Properties](../../2014/integration-services/common-properties.md) </span></span>  
 <span data-ttu-id="e5a2b-125">[Benutzerdefinierte Eigenschaften der Transformation](data-flow/transformations/transformation-custom-properties.md) </span><span class="sxs-lookup"><span data-stu-id="e5a2b-125">[Transformation Custom Properties](data-flow/transformations/transformation-custom-properties.md) </span></span>  
 [<span data-ttu-id="e5a2b-126">Data Flow-Eigenschaften, die mithilfe von Ausdrücken festgelegt werden können</span><span class="sxs-lookup"><span data-stu-id="e5a2b-126">Data Flow Properties that Can Be Set by Using Expressions</span></span>](../../2014/integration-services/data-flow-properties-that-can-be-set-by-using-expressions.md)  
  
  
