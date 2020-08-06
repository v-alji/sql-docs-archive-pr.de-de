---
title: Featureset-Element (DTA) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- FeatureSet element
ms.assetid: f2070c53-4a5c-4c11-ac38-96ee200c84f0
author: stevestein
ms.author: sstein
ms.openlocfilehash: d36c28b24a56ef2dcdf69578fb7e8c196306a416
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722086"
---
# <a name="featureset-element-dta"></a><span data-ttu-id="741f9-102">FeatureSet-Element (DTA)</span><span class="sxs-lookup"><span data-stu-id="741f9-102">FeatureSet Element (DTA)</span></span>
  <span data-ttu-id="741f9-103">Enthält die physischen Entwurfsstrukturen (Indizes oder indizierte Sichten), die der Datenbankoptimierungsratgeber bei der Analyse verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="741f9-103">Contains the physical design structures (indexes or indexed views) that you would like Database Engine Tuning Advisor to use during analysis.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="741f9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="741f9-104">Syntax</span></span>  
  
```  
  
<DTAInput>  
...code removed...  
    <TuningOptions>  
      <FeatureSet>...</FeatureSet>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="741f9-105">Elementmerkmale</span><span class="sxs-lookup"><span data-stu-id="741f9-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="741f9-106">Merkmal</span><span class="sxs-lookup"><span data-stu-id="741f9-106">Characteristic</span></span>|<span data-ttu-id="741f9-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="741f9-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="741f9-108">**Datentyp und -länge**</span><span class="sxs-lookup"><span data-stu-id="741f9-108">**Data type and length**</span></span>|<span data-ttu-id="741f9-109">`string`, keine maximale Länge.</span><span class="sxs-lookup"><span data-stu-id="741f9-109">`string`, no maximum length.</span></span>|  
|<span data-ttu-id="741f9-110">**Zulässige Werte**</span><span class="sxs-lookup"><span data-stu-id="741f9-110">**Allowed values**</span></span>|<span data-ttu-id="741f9-111">**IDX_IV**</span><span class="sxs-lookup"><span data-stu-id="741f9-111">**IDX_IV**</span></span><br /> <span data-ttu-id="741f9-112">Indizes und indizierte Sichten.</span><span class="sxs-lookup"><span data-stu-id="741f9-112">Indexes and indexed views.</span></span><br /><br /> <span data-ttu-id="741f9-113">**IDX**</span><span class="sxs-lookup"><span data-stu-id="741f9-113">**IDX**</span></span><br /> <span data-ttu-id="741f9-114">Nur Indizes.</span><span class="sxs-lookup"><span data-stu-id="741f9-114">Indexes only.</span></span><br /><br /> <span data-ttu-id="741f9-115">**IV**</span><span class="sxs-lookup"><span data-stu-id="741f9-115">**IV**</span></span><br /> <span data-ttu-id="741f9-116">Nur indizierte Sichten.</span><span class="sxs-lookup"><span data-stu-id="741f9-116">Indexed views only.</span></span><br /><br /> <span data-ttu-id="741f9-117">**NCL_IDX**</span><span class="sxs-lookup"><span data-stu-id="741f9-117">**NCL_IDX**</span></span><br /> <span data-ttu-id="741f9-118">Nur nicht gruppierte Indizes.</span><span class="sxs-lookup"><span data-stu-id="741f9-118">Nonclustered indexes only.</span></span><br /><br /> <span data-ttu-id="741f9-119">Verwenden Sie einen dieser Werte mit diesem Element.</span><span class="sxs-lookup"><span data-stu-id="741f9-119">Use one of these values with this element.</span></span>|  
|<span data-ttu-id="741f9-120">**Standardwert**</span><span class="sxs-lookup"><span data-stu-id="741f9-120">**Default value**</span></span>|<span data-ttu-id="741f9-121">**IDX**</span><span class="sxs-lookup"><span data-stu-id="741f9-121">**IDX**</span></span>|  
|<span data-ttu-id="741f9-122">**Vorkommen**</span><span class="sxs-lookup"><span data-stu-id="741f9-122">**Occurrence**</span></span>|<span data-ttu-id="741f9-123">Einmalig erforderlich für jedes `TuningOptions`-Element, es sei denn, das `DropOnlyMode`-Element wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="741f9-123">Required once for each `TuningOptions` element, unless the `DropOnlyMode` element is used.</span></span> <span data-ttu-id="741f9-124">Wird das `DropOnlyMode`-Element verwendet, kann das `FeatureSet`-Element nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="741f9-124">If `DropOnlyMode` is used, you cannot use `FeatureSet`.</span></span> <span data-ttu-id="741f9-125">Diese Elemente schließen sich gegenseitig aus.</span><span class="sxs-lookup"><span data-stu-id="741f9-125">These elements are mutually exclusive.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="741f9-126">Elementbeziehungen</span><span class="sxs-lookup"><span data-stu-id="741f9-126">Element Relationships</span></span>  
  
|<span data-ttu-id="741f9-127">Beziehung</span><span class="sxs-lookup"><span data-stu-id="741f9-127">Relationship</span></span>|<span data-ttu-id="741f9-128">Elemente</span><span class="sxs-lookup"><span data-stu-id="741f9-128">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="741f9-129">**Übergeordnetes Element**</span><span class="sxs-lookup"><span data-stu-id="741f9-129">**Parent element**</span></span>|[<span data-ttu-id="741f9-130">TuningOptions-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="741f9-130">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)|  
|<span data-ttu-id="741f9-131">**Untergeordnete Elemente**</span><span class="sxs-lookup"><span data-stu-id="741f9-131">**Child elements**</span></span>|<span data-ttu-id="741f9-132">Keine.</span><span class="sxs-lookup"><span data-stu-id="741f9-132">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="741f9-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="741f9-133">Example</span></span>  
 <span data-ttu-id="741f9-134">Ein Beispiel für die Verwendung dieses Elements finden Sie unter [Beispiel für eine einfache XML-Eingabedatei &#40;DTA&#41;](simple-xml-input-file-sample-dta.md).</span><span class="sxs-lookup"><span data-stu-id="741f9-134">For a usage example of this element, see the [Simple XML Input File Sample &#40;DTA&#41;](simple-xml-input-file-sample-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="741f9-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="741f9-135">See Also</span></span>  
 [<span data-ttu-id="741f9-136">XML-Eingabedateireferenz &#40;Datenbankoptimierungsratgeber&#41;</span><span class="sxs-lookup"><span data-stu-id="741f9-136">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
