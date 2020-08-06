---
title: TuningOptions-Element (DTA) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- TuningOptions element
ms.assetid: 58a22ba1-8e03-411f-bd46-85e4540f217a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2fab1c55c9d036424142b2692e8335ea65c22340
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720623"
---
# <a name="tuningoptions-element-dta"></a><span data-ttu-id="087b0-102">TuningOptions-Element (DTA)</span><span class="sxs-lookup"><span data-stu-id="087b0-102">TuningOptions Element (DTA)</span></span>
  <span data-ttu-id="087b0-103">Enthält die Optimierungsoptionen für eine bestimmte Optimierungssitzung.</span><span class="sxs-lookup"><span data-stu-id="087b0-103">Contains the tuning options for a specific tuning session.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="087b0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="087b0-104">Syntax</span></span>  
  
```  
  
<DTAInput>  
    <Server>  
...code removed...  
    <Workload>...</Workload>  
    <TuningOptions>...</TuningOptions>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="087b0-105">Elementmerkmale</span><span class="sxs-lookup"><span data-stu-id="087b0-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="087b0-106">Merkmal</span><span class="sxs-lookup"><span data-stu-id="087b0-106">Characteristic</span></span>|<span data-ttu-id="087b0-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="087b0-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="087b0-108">**Datentyp und -länge**</span><span class="sxs-lookup"><span data-stu-id="087b0-108">**Data type and length**</span></span>|<span data-ttu-id="087b0-109">Keine.</span><span class="sxs-lookup"><span data-stu-id="087b0-109">None.</span></span>|  
|<span data-ttu-id="087b0-110">**Standardwert**</span><span class="sxs-lookup"><span data-stu-id="087b0-110">**Default value**</span></span>|<span data-ttu-id="087b0-111">Keine.</span><span class="sxs-lookup"><span data-stu-id="087b0-111">None.</span></span>|  
|<span data-ttu-id="087b0-112">**Vorkommen**</span><span class="sxs-lookup"><span data-stu-id="087b0-112">**Occurrence**</span></span>|<span data-ttu-id="087b0-113">Optional.</span><span class="sxs-lookup"><span data-stu-id="087b0-113">Optional.</span></span> <span data-ttu-id="087b0-114">Kann bei Verwendung nur einmalig pro `DTAInput`-Element verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="087b0-114">If used, can only be used once for each `DTAInput` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="087b0-115">Elementbeziehungen</span><span class="sxs-lookup"><span data-stu-id="087b0-115">Element Relationships</span></span>  
  
|<span data-ttu-id="087b0-116">Beziehung</span><span class="sxs-lookup"><span data-stu-id="087b0-116">Relationship</span></span>|<span data-ttu-id="087b0-117">Elemente</span><span class="sxs-lookup"><span data-stu-id="087b0-117">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="087b0-118">**Übergeordnetes Element**</span><span class="sxs-lookup"><span data-stu-id="087b0-118">**Parent element**</span></span>|[<span data-ttu-id="087b0-119">DTAInput-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="087b0-119">DTAInput Element &#40;DTA&#41;</span></span>](dtainput-element-dta.md)|  
|<span data-ttu-id="087b0-120">**Untergeordnete Elemente**</span><span class="sxs-lookup"><span data-stu-id="087b0-120">**Child elements**</span></span>|<span data-ttu-id="087b0-121">`ReportSet`-Element.</span><span class="sxs-lookup"><span data-stu-id="087b0-121">`ReportSet` element.</span></span> <span data-ttu-id="087b0-122">Weitere Informationen finden Sie im [XML-Schema des Datenbankoptimierungsratgebers](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="087b0-122">For more information, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span><br /><br /> <span data-ttu-id="087b0-123">`TuningLogTable`-Element.</span><span class="sxs-lookup"><span data-stu-id="087b0-123">`TuningLogTable` element.</span></span> <span data-ttu-id="087b0-124">Weitere Informationen finden Sie im [XML-Schema des Datenbankoptimierungsratgebers](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="087b0-124">For more information, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span><br /><br /> <span data-ttu-id="087b0-125">`NumberOfEvents`-Element.</span><span class="sxs-lookup"><span data-stu-id="087b0-125">`NumberOfEvents` element.</span></span> <span data-ttu-id="087b0-126">Weitere Informationen finden Sie im [XML-Schema des Datenbankoptimierungsratgebers](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="087b0-126">For more information, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span><br /><br /> [<span data-ttu-id="087b0-127">TuningTimeInMin-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="087b0-127">TuningTimeInMin Element &#40;DTA&#41;</span></span>](tuningtimeinmin-element-dta.md)<br /><br /> [<span data-ttu-id="087b0-128">StorageBoundInMB-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="087b0-128">StorageBoundInMB Element &#40;DTA&#41;</span></span>](storageboundinmb-element-dta.md)<br /><br /> <span data-ttu-id="087b0-129">`MaxKeyColumnsInIndex`-Element.</span><span class="sxs-lookup"><span data-stu-id="087b0-129">`MaxKeyColumnsInIndex` element.</span></span> <span data-ttu-id="087b0-130">Weitere Informationen finden Sie im [XML-Schema des Datenbankoptimierungsratgebers](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="087b0-130">For more information, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span><br /><br /> <span data-ttu-id="087b0-131">`MaxColumnsInIndex`-Element.</span><span class="sxs-lookup"><span data-stu-id="087b0-131">`MaxColumnsInIndex` element.</span></span> <span data-ttu-id="087b0-132">Weitere Informationen finden Sie im [XML-Schema des Datenbankoptimierungsratgebers](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="087b0-132">For more information, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span><br /><br /> <span data-ttu-id="087b0-133">`MinPercentageImprovement`-Element.</span><span class="sxs-lookup"><span data-stu-id="087b0-133">`MinPercentageImprovement` element.</span></span> <span data-ttu-id="087b0-134">Weitere Informationen finden Sie im [XML-Schema des Datenbankoptimierungsratgebers](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="087b0-134">For more information, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100)</span></span><br /><br /> [<span data-ttu-id="087b0-135">TestServer-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="087b0-135">TestServer Element &#40;DTA&#41;</span></span>](server-element-dta.md)<br /><br /> [<span data-ttu-id="087b0-136">FeatureSet-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="087b0-136">FeatureSet Element &#40;DTA&#41;</span></span>](featureset-element-dta.md)<br /><br /> [<span data-ttu-id="087b0-137">Partitioning-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="087b0-137">Partitioning Element &#40;DTA&#41;</span></span>](partitioning-element-dta.md)<br /><br /> [<span data-ttu-id="087b0-138">DropOnlyMode-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="087b0-138">DropOnlyMode Element &#40;DTA&#41;</span></span>](droponlymode-element-dta.md)<br /><br /> [<span data-ttu-id="087b0-139">KeepExisting-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="087b0-139">KeepExisting Element &#40;DTA&#41;</span></span>](keepexisting-element-dta.md)<br /><br /> [<span data-ttu-id="087b0-140">OnlineIndexOperation-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="087b0-140">OnlineIndexOperation Element &#40;DTA&#41;</span></span>](onlineindexoperation-element-dta.md)<br /><br /> [<span data-ttu-id="087b0-141">DatabaseToConnect-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="087b0-141">DatabaseToConnect Element &#40;DTA&#41;</span></span>](databasetoconnect-element-dta.md)<br /><br /> <span data-ttu-id="087b0-142">`IgnoreConstantsInWorkload`-Element.</span><span class="sxs-lookup"><span data-stu-id="087b0-142">`IgnoreConstantsInWorkload` element.</span></span> <span data-ttu-id="087b0-143">Weitere Informationen finden Sie im [XML-Schema des Datenbankoptimierungsratgebers](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="087b0-143">For more information, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span><br /><br /> <span data-ttu-id="087b0-144">`RetainShellDB`-Element.</span><span class="sxs-lookup"><span data-stu-id="087b0-144">`RetainShellDB` element.</span></span> <span data-ttu-id="087b0-145">Weitere Informationen finden Sie im [XML-Schema des Datenbankoptimierungsratgebers](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="087b0-145">For more information, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="087b0-146">Beispiel</span><span class="sxs-lookup"><span data-stu-id="087b0-146">Example</span></span>  
 <span data-ttu-id="087b0-147">Beispiele für das- `TuningOptions` Element finden Sie unter Beispiele für die [XML-Eingabedatei &#40;DTA&#41;](xml-input-file-samples-dta.md).</span><span class="sxs-lookup"><span data-stu-id="087b0-147">For examples of the `TuningOptions` element, see the [XML Input File Samples &#40;DTA&#41;](xml-input-file-samples-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="087b0-148">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="087b0-148">See Also</span></span>  
 [<span data-ttu-id="087b0-149">XML-Eingabedateireferenz &#40;Datenbankoptimierungsratgeber&#41;</span><span class="sxs-lookup"><span data-stu-id="087b0-149">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
