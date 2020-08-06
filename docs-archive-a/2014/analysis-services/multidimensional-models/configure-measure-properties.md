---
title: Konfigurieren von Measure-Eigenschaften | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- additivity [Analysis Services]
- ID property
- ErrorConfiguration property
- AggregateFunction property
- DisplayFolder property
- IgnoreUnrelatedDimensions property
- FormatString property
- Description property
- semiadditive
- properties [Analysis Services], measure groups
- aggregate functions [Analysis Services]
- DataType property
- ProcessingMode property
- MeasureExpression property
- AggregationPrefix property
- Visible property
- properties [Analysis Services], measures
- StorageLocation property
- StorageMode property
- formats [Analysis Services], measures
- Source property
- aggregations [Analysis Services], measures
- measures [Analysis Services], properties
- nonadditive [Analysis Services]
- Name property
- measures [Analysis Services], display formats
- ProcessingPriority property
- measure groups [Analysis Services], properties
- Type property
- ProactiveCaching property
ms.assetid: e9031078-c4f5-4986-b0c9-4d064b622ab7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7ca291a5181fdb3f7a88845431d61ffd7a1034eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721969"
---
# <a name="configure-measure-properties"></a><span data-ttu-id="35093-102">Konfigurieren von Measureeigenschaften</span><span class="sxs-lookup"><span data-stu-id="35093-102">Configure Measure Properties</span></span>
  <span data-ttu-id="35093-103">Measures haben Eigenschaften, die es Ihnen ermöglichen, die Funktionsweise von Measures zu definieren und die Anzeige von Measures für Benutzer zu steuern.</span><span class="sxs-lookup"><span data-stu-id="35093-103">Measures have properties that enable you to define how the measures function and to control how the measures appear to users.</span></span>  
  
 <span data-ttu-id="35093-104">Sie können beim Erstellen oder Bearbeiten eines Cubes oder Measures Eigenschaften in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] festlegen.</span><span class="sxs-lookup"><span data-stu-id="35093-104">You can set properties in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] when creating or editing a cube or measure.</span></span> <span data-ttu-id="35093-105">Sie können sie mit MDX oder AMO auch programmgesteuert festlegen.</span><span class="sxs-lookup"><span data-stu-id="35093-105">You can also set them programmatically, using MDX or AMO.</span></span> <span data-ttu-id="35093-106">Einzelheiten finden Sie unter [Erstellen von Measures und Measuregruppen in mehrdimensionalen Modellen](create-measures-and-measure-groups-in-multidimensional-models.md), [CREATE MEMBER-Anweisung &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-member) oder [Programmieren von AMO OLAP Basic-Objekten](https://docs.microsoft.com/bi-reference/amo/programming-amo-olap-basic-objects).</span><span class="sxs-lookup"><span data-stu-id="35093-106">See [Create Measures and Measure Groups in Multidimensional Models](create-measures-and-measure-groups-in-multidimensional-models.md) or [CREATE MEMBER Statement &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-member) or [Programming AMO OLAP Basic Objects](https://docs.microsoft.com/bi-reference/amo/programming-amo-olap-basic-objects) for details.</span></span>  
  
## <a name="measure-properties"></a><span data-ttu-id="35093-107">Eigenschaften von Measures</span><span class="sxs-lookup"><span data-stu-id="35093-107">Measure Properties</span></span>  
 <span data-ttu-id="35093-108">Measures erben bestimmte Eigenschaften von der Measuregruppe, zu der sie gehören, sofern diese Eigenschaften nicht auf Measureebene überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="35093-108">Measures inherit certain properties from the measure group of which they are a member, unless those properties are overridden at the measure level.</span></span> <span data-ttu-id="35093-109">Measureeigenschaften bestimmen die Art der Aggregation von Measures, ihren Datentyp, den dem Benutzer angezeigten Namen, den Anzeigeordner von Measures, die Formatzeichenfolge, mögliche Measureausdrücke, zugrunde liegende Quellspalten und die Sichtbarkeit für Benutzer.</span><span class="sxs-lookup"><span data-stu-id="35093-109">Measure properties determine how a measure is aggregated, its data type, the name that is displayed to the user, the display folder in which the measure will appear, its format string, any measure expression, the underlying source column, and its visibility to users.</span></span>  
  
|<span data-ttu-id="35093-110">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="35093-110">Property</span></span>|<span data-ttu-id="35093-111">Definition</span><span class="sxs-lookup"><span data-stu-id="35093-111">Definition</span></span>|  
|--------------|----------------|  
|`AggregateFunction`|<span data-ttu-id="35093-112">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="35093-112">Required.</span></span> <span data-ttu-id="35093-113">Bestimmt, wie Measures aggregiert werden.</span><span class="sxs-lookup"><span data-stu-id="35093-113">Determines how measures are aggregated.</span></span> <span data-ttu-id="35093-114">`Sum` ist die Standardaggregation.</span><span class="sxs-lookup"><span data-stu-id="35093-114">`Sum` is the default aggregation.</span></span> <span data-ttu-id="35093-115">Weitere Informationen und eine Beschreibung zu den einzelnen Funktionen finden Sie unter [Use Aggregate Functions](use-aggregate-functions.md) .</span><span class="sxs-lookup"><span data-stu-id="35093-115">For more information, see [Use Aggregate Functions](use-aggregate-functions.md) for a description of each function.</span></span>|  
|`DataType`|<span data-ttu-id="35093-116">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="35093-116">Required.</span></span> <span data-ttu-id="35093-117">Gibt den Datentyp der zugrunde liegenden Faktentabellenspalte an, an die das Measure gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="35093-117">Specifies the data type of the column in the underlying fact table to which the measure is bound.</span></span> <span data-ttu-id="35093-118">Dieser Wert wird standardmäßig aus der Quellspalte geerbt.</span><span class="sxs-lookup"><span data-stu-id="35093-118">This value is inherited from the source column by default.</span></span>|  
|`Description`|<span data-ttu-id="35093-119">Stellt eine Beschreibung des Measures bereit, das in Clientanwendungen möglicherweise offen gelegt wird.</span><span class="sxs-lookup"><span data-stu-id="35093-119">Provides a description of the measure, which may be exposed in client applications.</span></span>|  
|`DisplayFolder`|<span data-ttu-id="35093-120">Gibt den Ordner an, in dem das Measure angezeigt wird, wenn Benutzer die Verbindung zu dem Cube erstellen.</span><span class="sxs-lookup"><span data-stu-id="35093-120">Specifies the folder in which the measure will appear when users connect to the cube.</span></span> <span data-ttu-id="35093-121">Wenn ein Cube viele Measures enthält, können Sie sie mithilfe von Anzeigeordnern kategorisieren und dem Benutzer das Durchsuchen erleichtern.</span><span class="sxs-lookup"><span data-stu-id="35093-121">When a cube has many measures, you can use display folders to categorize the measures and improve the user browsing experience.</span></span>|  
|`FormatString`|<span data-ttu-id="35093-122">Sie können das Format, das für die Anzeige der Measurewerte für Benutzer verwendet wird, mithilfe der `FormatString`-Eigenschaft des Measures auswählen.</span><span class="sxs-lookup"><span data-stu-id="35093-122">You can select the format that is used to display measure values to users by using the `FormatString` property of the measure.</span></span><br /><br /> <span data-ttu-id="35093-123">Obwohl eine Liste der Anzeigeformate in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]verfügbar ist, können Sie viele zusätzliche Formate angeben, die nicht in der Liste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="35093-123">Although a list of display formats is provided in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], you can specify many additional formats that are not in the list.</span></span> <span data-ttu-id="35093-124">Sie können jedes beliebige benannte oder benutzerdefinierte Format angeben, das in Microsoft Visual Basic gültig ist.</span><span class="sxs-lookup"><span data-stu-id="35093-124">You can specify any named or user-defined format that is valid in Microsoft Visual Basic.</span></span>|  
|`ID`|<span data-ttu-id="35093-125">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="35093-125">Required.</span></span> <span data-ttu-id="35093-126">Zeigt den eindeutigen Bezeichner (ID) des Measures an.</span><span class="sxs-lookup"><span data-stu-id="35093-126">Displays the unique identifier (ID) of the measure.</span></span> <span data-ttu-id="35093-127">Diese Eigenschaft ist schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="35093-127">This property is read-only.</span></span>|  
|`MeasureExpression`|<span data-ttu-id="35093-128">Gibt einen eingeschränkten MDX-Ausdruck an, der den Wert des Measures definiert.</span><span class="sxs-lookup"><span data-stu-id="35093-128">Specifies a constrained MDX expression defining the value of the measure.</span></span> <span data-ttu-id="35093-129">Der Ausdruck wird vor der Aggregation auf der Blattebene ausgewertet und ermöglicht die Gewichtung eines Werts.</span><span class="sxs-lookup"><span data-stu-id="35093-129">The expression is evaluated at the leaf level before being aggregated, and allows for weighting of a value.</span></span> <span data-ttu-id="35093-130">Beispielsweise bei der Währungsumrechnung, bei der ein Betrag der Verkäufe nach dem Wechselkurs gewichtet wird.</span><span class="sxs-lookup"><span data-stu-id="35093-130">For example, in currency conversion where a sales amount is weighted by the exchange rate.</span></span>|  
|`Name`|<span data-ttu-id="35093-131">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="35093-131">Required.</span></span> <span data-ttu-id="35093-132">Gibt den Namen des Measures an.</span><span class="sxs-lookup"><span data-stu-id="35093-132">Specifies the name of the measure.</span></span>|  
|`Source`|<span data-ttu-id="35093-133">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="35093-133">Required.</span></span> <span data-ttu-id="35093-134">Gibt die Spalte in der Datenquellensicht an, an die das Measure gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="35093-134">Specifies the column in the data source view to which the measure is bound.</span></span> <span data-ttu-id="35093-135">Siehe [Datenquellen und Bindungen &#40;SSAS – mehrdimensional&#41;](data-sources-and-bindings-ssas-multidimensional.md).</span><span class="sxs-lookup"><span data-stu-id="35093-135">See [Data Sources and Bindings &#40;SSAS Multidimensional&#41;](data-sources-and-bindings-ssas-multidimensional.md).</span></span>|  
|`Visible`|<span data-ttu-id="35093-136">Bestimmt die Sichtbarkeit des Measures in Clientanwendungen.</span><span class="sxs-lookup"><span data-stu-id="35093-136">Determines the visibility of the measure in client applications.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="35093-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="35093-137">See Also</span></span>  
 <span data-ttu-id="35093-138">[Konfigurieren von Measure-Gruppen Eigenschaften](configure-measure-group-properties.md) </span><span class="sxs-lookup"><span data-stu-id="35093-138">[Configure Measure Group Properties](configure-measure-group-properties.md) </span></span>  
 [<span data-ttu-id="35093-139">Ändern von Measures</span><span class="sxs-lookup"><span data-stu-id="35093-139">Modifying Measures</span></span>](../lesson-3-1-modifying-measures.md)  
  
  
