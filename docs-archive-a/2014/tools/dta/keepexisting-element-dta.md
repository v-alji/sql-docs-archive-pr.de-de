---
title: Keepexistierende-Element (DTA) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- KeepExisting element
ms.assetid: e67aae61-d06d-4a03-85ba-6516c3502dce
author: stevestein
ms.author: sstein
ms.openlocfilehash: cde9b3091b75f55e4b9c79137853fbd7d4e0daf9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719231"
---
# <a name="keepexisting-element-dta"></a><span data-ttu-id="19ff9-102">KeepExisting-Element (DTA)</span><span class="sxs-lookup"><span data-stu-id="19ff9-102">KeepExisting Element (DTA)</span></span>
  <span data-ttu-id="19ff9-103">Gibt die physischen Entwurfsstrukturen (Indizes, indizierte Sichten oder Partitionierung) an, die der Datenbankoptimierungsratgeber beim Generieren der Empfehlung beibehalten muss.</span><span class="sxs-lookup"><span data-stu-id="19ff9-103">Specifies the physical design structures (indexes, indexed views, or partitioning) that Database Engine Tuning Advisor must retain when generating its recommendation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19ff9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="19ff9-104">Syntax</span></span>  
  
```  
  
<DTAInput>  
...code removed...  
    <TuningOptions>  
      <KeepExisting>...</KeepExisting>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="19ff9-105">Elementmerkmale</span><span class="sxs-lookup"><span data-stu-id="19ff9-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="19ff9-106">Merkmal</span><span class="sxs-lookup"><span data-stu-id="19ff9-106">Characteristic</span></span>|<span data-ttu-id="19ff9-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="19ff9-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="19ff9-108">**Datentyp und -länge**</span><span class="sxs-lookup"><span data-stu-id="19ff9-108">**Data type and length**</span></span>|<span data-ttu-id="19ff9-109">`string`, Grenzwert für die Länge wird vom Server erzwungen.</span><span class="sxs-lookup"><span data-stu-id="19ff9-109">`string`, length limit enforced by the server.</span></span>|  
|<span data-ttu-id="19ff9-110">**Zulässige Werte**</span><span class="sxs-lookup"><span data-stu-id="19ff9-110">**Allowed values**</span></span>|<span data-ttu-id="19ff9-111">**NONE**</span><span class="sxs-lookup"><span data-stu-id="19ff9-111">**NONE**</span></span><br /> <span data-ttu-id="19ff9-112">Keine vorhandenen Strukturen.</span><span class="sxs-lookup"><span data-stu-id="19ff9-112">No existing structures.</span></span><br /><br /> <span data-ttu-id="19ff9-113">**ALL**</span><span class="sxs-lookup"><span data-stu-id="19ff9-113">**ALL**</span></span><br /> <span data-ttu-id="19ff9-114">Alle vorhandenen Strukturen.</span><span class="sxs-lookup"><span data-stu-id="19ff9-114">All existing structures.</span></span><br /><br /> <span data-ttu-id="19ff9-115">**ALIGNED**</span><span class="sxs-lookup"><span data-stu-id="19ff9-115">**ALIGNED**</span></span><br /> <span data-ttu-id="19ff9-116">Alle Strukturen mit ausgerichteten Partitionen.</span><span class="sxs-lookup"><span data-stu-id="19ff9-116">All partition-aligned structures.</span></span><br /><br /> <span data-ttu-id="19ff9-117">**CL_IDX**</span><span class="sxs-lookup"><span data-stu-id="19ff9-117">**CL_IDX**</span></span><br /> <span data-ttu-id="19ff9-118">Alle gruppierten Indizes für Tabellen.</span><span class="sxs-lookup"><span data-stu-id="19ff9-118">All clustered indexes on tables.</span></span><br /><br /> <span data-ttu-id="19ff9-119">**IDX**</span><span class="sxs-lookup"><span data-stu-id="19ff9-119">**IDX**</span></span><br /> <span data-ttu-id="19ff9-120">Alle gruppierten und nicht gruppierten Indizes für Tabellen.</span><span class="sxs-lookup"><span data-stu-id="19ff9-120">All clustered and nonclustered indexes on tables.</span></span><br /><br /> <span data-ttu-id="19ff9-121">Verwenden Sie nur einen dieser Werte mit diesem Element.</span><span class="sxs-lookup"><span data-stu-id="19ff9-121">Use only one of these values with this element.</span></span>|  
|<span data-ttu-id="19ff9-122">**Standardwert**</span><span class="sxs-lookup"><span data-stu-id="19ff9-122">**Default value**</span></span>|<span data-ttu-id="19ff9-123">Keine.</span><span class="sxs-lookup"><span data-stu-id="19ff9-123">None.</span></span>|  
|<span data-ttu-id="19ff9-124">**Vorkommen**</span><span class="sxs-lookup"><span data-stu-id="19ff9-124">**Occurrence**</span></span>|<span data-ttu-id="19ff9-125">Optional.</span><span class="sxs-lookup"><span data-stu-id="19ff9-125">Optional.</span></span> <span data-ttu-id="19ff9-126">Nur einmalige Verwendung pro `TuningOptions`-Element möglich.</span><span class="sxs-lookup"><span data-stu-id="19ff9-126">Can use only once for each `TuningOptions` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="19ff9-127">Elementbeziehungen</span><span class="sxs-lookup"><span data-stu-id="19ff9-127">Element Relationships</span></span>  
  
|<span data-ttu-id="19ff9-128">Beziehung</span><span class="sxs-lookup"><span data-stu-id="19ff9-128">Relationship</span></span>|<span data-ttu-id="19ff9-129">Elemente</span><span class="sxs-lookup"><span data-stu-id="19ff9-129">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="19ff9-130">**Übergeordnetes Element**</span><span class="sxs-lookup"><span data-stu-id="19ff9-130">**Parent element**</span></span>|[<span data-ttu-id="19ff9-131">TuningOptions-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="19ff9-131">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)|  
|<span data-ttu-id="19ff9-132">**Untergeordnete Elemente**</span><span class="sxs-lookup"><span data-stu-id="19ff9-132">**Child elements**</span></span>|<span data-ttu-id="19ff9-133">Keine.</span><span class="sxs-lookup"><span data-stu-id="19ff9-133">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="19ff9-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="19ff9-134">Example</span></span>  
 <span data-ttu-id="19ff9-135">Ein Beispiel für die Verwendung dieses Elements finden Sie unter [Beispiel für eine einfache XML-Eingabedatei &#40;DTA&#41;](simple-xml-input-file-sample-dta.md).</span><span class="sxs-lookup"><span data-stu-id="19ff9-135">For a usage example of this element, see the [Simple XML Input File Sample &#40;DTA&#41;](simple-xml-input-file-sample-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19ff9-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="19ff9-136">See Also</span></span>  
 [<span data-ttu-id="19ff9-137">XML-Eingabedateireferenz &#40;Datenbankoptimierungsratgeber&#41;</span><span class="sxs-lookup"><span data-stu-id="19ff9-137">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
