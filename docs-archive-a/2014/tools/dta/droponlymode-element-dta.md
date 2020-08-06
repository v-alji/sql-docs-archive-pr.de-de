---
title: DropOnlyMode-Element (DTA) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- DropOnlyMode element
ms.assetid: 80960676-7581-4074-889b-80ee665963dd
author: stevestein
ms.author: sstein
ms.openlocfilehash: b274dc394a933308cf2161cc271d09b8391900c4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695005"
---
# <a name="droponlymode-element-dta"></a><span data-ttu-id="131eb-102">DropOnlyMode-Element (DTA)</span><span class="sxs-lookup"><span data-stu-id="131eb-102">DropOnlyMode Element (DTA)</span></span>
  <span data-ttu-id="131eb-103">Gibt an, dass der Datenbankoptimierungsratgeber während der Optimierungssitzung nur vorhandene Indizes, indizierte Sichten oder Partitionen löschen soll.</span><span class="sxs-lookup"><span data-stu-id="131eb-103">Specifies that Database Engine Tuning Advisor should only consider dropping existing indexes, indexed views, or partitions during the tuning session.</span></span> <span data-ttu-id="131eb-104">Wenn diese Optimierungsoption angegeben ist, werden keine neuen physischen Entwurfsstrukturen berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="131eb-104">No new physical design structures are considered when this tuning option is specified.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="131eb-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="131eb-105">Syntax</span></span>  
  
```  
  
<DTAInput>  
...code removed...  
    <TuningOptions>  
      <DropOnlyMode>...</DropOnlyMode>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="131eb-106">Elementmerkmale</span><span class="sxs-lookup"><span data-stu-id="131eb-106">Element Characteristics</span></span>  
  
|<span data-ttu-id="131eb-107">Merkmal</span><span class="sxs-lookup"><span data-stu-id="131eb-107">Characteristic</span></span>|<span data-ttu-id="131eb-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="131eb-108">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="131eb-109">**Datentyp und -länge**</span><span class="sxs-lookup"><span data-stu-id="131eb-109">**Data type and length**</span></span>|<span data-ttu-id="131eb-110">Keine.</span><span class="sxs-lookup"><span data-stu-id="131eb-110">None.</span></span>|  
|<span data-ttu-id="131eb-111">**Standardwert**</span><span class="sxs-lookup"><span data-stu-id="131eb-111">**Default value**</span></span>|<span data-ttu-id="131eb-112">Keine.</span><span class="sxs-lookup"><span data-stu-id="131eb-112">None.</span></span>|  
|<span data-ttu-id="131eb-113">**Vorkommen**</span><span class="sxs-lookup"><span data-stu-id="131eb-113">**Occurrence**</span></span>|<span data-ttu-id="131eb-114">Optional.</span><span class="sxs-lookup"><span data-stu-id="131eb-114">Optional.</span></span> <span data-ttu-id="131eb-115">Nur einmalige Verwendung pro `TuningOptions`-Element möglich.</span><span class="sxs-lookup"><span data-stu-id="131eb-115">Can use only once for each `TuningOptions` element.</span></span> <span data-ttu-id="131eb-116">Keine Verwendung möglich, wenn im `TuningOptions`-Element die folgenden Elemente angegeben sind:</span><span class="sxs-lookup"><span data-stu-id="131eb-116">Cannot be used if the following elements are specified in the `TuningOptions` element:</span></span><br /><br /> [<span data-ttu-id="131eb-117">FeatureSet-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="131eb-117">FeatureSet Element &#40;DTA&#41;</span></span>](featureset-element-dta.md)<br /><br /> [<span data-ttu-id="131eb-118">Partitioning-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="131eb-118">Partitioning Element &#40;DTA&#41;</span></span>](partitioning-element-dta.md)<br /><br /> <span data-ttu-id="131eb-119">[KeepExisting-Element &#40;DTA&#41;](keepexisting-element-dta.md) ist auf **ALL** festgelegt</span><span class="sxs-lookup"><span data-stu-id="131eb-119">[KeepExisting Element &#40;DTA&#41;](keepexisting-element-dta.md) is set to **ALL**</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="131eb-120">Elementbeziehungen</span><span class="sxs-lookup"><span data-stu-id="131eb-120">Element Relationships</span></span>  
  
|<span data-ttu-id="131eb-121">Beziehung</span><span class="sxs-lookup"><span data-stu-id="131eb-121">Relationship</span></span>|<span data-ttu-id="131eb-122">Elemente</span><span class="sxs-lookup"><span data-stu-id="131eb-122">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="131eb-123">**Übergeordnetes Element**</span><span class="sxs-lookup"><span data-stu-id="131eb-123">**Parent element**</span></span>|[<span data-ttu-id="131eb-124">TuningOptions-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="131eb-124">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)|  
|<span data-ttu-id="131eb-125">**Untergeordnete Elemente**</span><span class="sxs-lookup"><span data-stu-id="131eb-125">**Child elements**</span></span>|<span data-ttu-id="131eb-126">Keine.</span><span class="sxs-lookup"><span data-stu-id="131eb-126">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="131eb-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="131eb-127">Example</span></span>  
 <span data-ttu-id="131eb-128">Das folgende Beispiel veranschaulicht den `TuningOptions`-Abschnitt einer XML-Eingabedatei des Datenbankoptimierungsratgebers, wobei `DropOnlyMode` angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="131eb-128">The following example shows the `TuningOptions` section of a Database Engine Tuning Advisor XML input file where the `DropOnlyMode` is specified.</span></span> <span data-ttu-id="131eb-129">In diesem Beispiel ist die Optimierungszeit auf 24 Stunden (1440 Minuten) begrenzt, und alle vorhandenen gruppierten und nicht gruppierten Indizes sollen gelöscht werden:</span><span class="sxs-lookup"><span data-stu-id="131eb-129">In this example the tuning time is limited to 24 hours (1440 minutes) and all existing clustered and nonclustered indexes will be considered for dropping:</span></span>  
  
```xml  
<TuningOptions  
  <TuningTimeInMin>1440</Name>  
  <KeepExisting>ALIGNED</KeepExisting>  
  <DropOnlyMode />  
</TuningOptions>  
```  
  
## <a name="see-also"></a><span data-ttu-id="131eb-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="131eb-130">See Also</span></span>  
 [<span data-ttu-id="131eb-131">XML-Eingabedateireferenz &#40;Datenbankoptimierungsratgeber&#41;</span><span class="sxs-lookup"><span data-stu-id="131eb-131">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
