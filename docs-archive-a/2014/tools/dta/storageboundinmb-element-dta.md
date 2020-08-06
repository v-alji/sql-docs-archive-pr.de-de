---
title: StorageBoundInMB-Element (DTA) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- StorageBoundInMB element
ms.assetid: a8374910-bf68-4edb-b464-53a3a705e7f4
author: stevestein
ms.author: sstein
ms.openlocfilehash: ea49b0af981b8f8d96efb087033d8f1466364c76
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720665"
---
# <a name="storageboundinmb-element-dta"></a><span data-ttu-id="c268b-102">StorageBoundInMB-Element (DTA)</span><span class="sxs-lookup"><span data-stu-id="c268b-102">StorageBoundInMB Element (DTA)</span></span>
  <span data-ttu-id="c268b-103">Gibt die maximale Größe des Speicherplatzes in Megabyte an, der von der Optimierungsempfehlung des Datenbankoptimierungsratgebers (Index und Partitionierung) beansprucht werden kann.</span><span class="sxs-lookup"><span data-stu-id="c268b-103">Specifies the maximum space in megabytes that can be consumed by the Database Engine Tuning Advisor tuning recommendation (index and partitioning set).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c268b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c268b-104">Syntax</span></span>  
  
```  
  
<DTAInput>  
...code removed...  
    <TuningOptions>  
      <StorageBoundInMB>...</ StorageBoundInMB >  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="c268b-105">Elementmerkmale</span><span class="sxs-lookup"><span data-stu-id="c268b-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="c268b-106">Merkmal</span><span class="sxs-lookup"><span data-stu-id="c268b-106">Characteristic</span></span>|<span data-ttu-id="c268b-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c268b-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="c268b-108">**Datentyp und -länge**</span><span class="sxs-lookup"><span data-stu-id="c268b-108">**Data type and length**</span></span>|<span data-ttu-id="c268b-109">`unsignedInt`, unbegrenzte Länge.</span><span class="sxs-lookup"><span data-stu-id="c268b-109">`unsignedInt`, unlimited length.</span></span>|  
|<span data-ttu-id="c268b-110">**Standardwert**</span><span class="sxs-lookup"><span data-stu-id="c268b-110">**Default value**</span></span>|<span data-ttu-id="c268b-111">Keine.</span><span class="sxs-lookup"><span data-stu-id="c268b-111">None.</span></span>|  
|<span data-ttu-id="c268b-112">**Vorkommen**</span><span class="sxs-lookup"><span data-stu-id="c268b-112">**Occurrence**</span></span>|<span data-ttu-id="c268b-113">Optional.</span><span class="sxs-lookup"><span data-stu-id="c268b-113">Optional.</span></span> <span data-ttu-id="c268b-114">Kann nur einmalig für das `TuningOptions`-Element verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c268b-114">Can only be used once for the `TuningOptions` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="c268b-115">Elementbeziehungen</span><span class="sxs-lookup"><span data-stu-id="c268b-115">Element Relationships</span></span>  
  
|<span data-ttu-id="c268b-116">Beziehung</span><span class="sxs-lookup"><span data-stu-id="c268b-116">Relationship</span></span>|<span data-ttu-id="c268b-117">Elemente</span><span class="sxs-lookup"><span data-stu-id="c268b-117">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="c268b-118">**Übergeordnetes Element**</span><span class="sxs-lookup"><span data-stu-id="c268b-118">**Parent element**</span></span>|[<span data-ttu-id="c268b-119">TuningOptions-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="c268b-119">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)|  
|<span data-ttu-id="c268b-120">**Untergeordnete Elemente**</span><span class="sxs-lookup"><span data-stu-id="c268b-120">**Child elements**</span></span>|<span data-ttu-id="c268b-121">Keine</span><span class="sxs-lookup"><span data-stu-id="c268b-121">None</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c268b-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c268b-122">Remarks</span></span>  
 <span data-ttu-id="c268b-123">Wenn mehrere Datenbanken optimiert werden, werden bei der Berechnung des Speicherplatzes Empfehlungen für alle Datenbanken berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="c268b-123">When multiple databases are tuned, recommendations for all databases are considered for the space calculation.</span></span> <span data-ttu-id="c268b-124">Standardmäßig nimmt der Datenbankoptimierungsratgeber die kleinere der folgenden Speichergrößen an:</span><span class="sxs-lookup"><span data-stu-id="c268b-124">By default, Database Engine Tuning Advisor assumes the smaller of the following storage sizes:</span></span>  
  
-   <span data-ttu-id="c268b-125">Das Dreifache der aktuellen Rohdatengröße, einschließlich der Gesamtgröße von Heaps und gruppierten Indizes für Tabellen.</span><span class="sxs-lookup"><span data-stu-id="c268b-125">Three times the current raw data size, which includes the total size of heaps and clustered indexes on tables.</span></span>  
  
-   <span data-ttu-id="c268b-126">Der freie Speicherplatz auf allen angefügten Laufwerken plus die Rohdatengröße.</span><span class="sxs-lookup"><span data-stu-id="c268b-126">The free space on all attached disk drives plus the raw data size.</span></span>  
  
 <span data-ttu-id="c268b-127">Nicht im Standardspeicherplatz enthalten sind nicht gruppierte Indizes und indizierte Sichten.</span><span class="sxs-lookup"><span data-stu-id="c268b-127">The default storage size does not include nonclustered indexes and indexed views.</span></span>  
  
 <span data-ttu-id="c268b-128">Wenn der für das `StorageBoundInMB`-Element angegebene Wert den tatsächlichen Speicherplatz überschreitet, meldet der Datenbankoptimierungsratgeber einen Fehler, fährt aber mit der Optimierung fort.</span><span class="sxs-lookup"><span data-stu-id="c268b-128">If the value specified for the `StorageBoundInMB` element exceeds the actual disk space, Database Engine Tuning Advisor returns an error, but continues tuning.</span></span> <span data-ttu-id="c268b-129">Nach der Optimierung können Sie Speicherplatz hinzufügen, wenn Sie die Empfehlung implementieren möchten.</span><span class="sxs-lookup"><span data-stu-id="c268b-129">After tuning is complete, you can add disk space if you decide to implement the recommendation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c268b-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c268b-130">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="c268b-131">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c268b-131">Description</span></span>  
 <span data-ttu-id="c268b-132">Im folgenden Codebeispiel wird veranschaulicht, wie 1500 Megabytes als maximaler Speicherplatz festgelegt werden, der von einer Empfehlung zur Optimierung belegt werden kann:</span><span class="sxs-lookup"><span data-stu-id="c268b-132">The following code example shows how to set a limit of 1500 megabytes as the maximum disk space that a tuning recommendation can consume:</span></span>  
  
## <a name="code"></a><span data-ttu-id="c268b-133">Code</span><span class="sxs-lookup"><span data-stu-id="c268b-133">Code</span></span>  
  
```  
<DTAInput>  
  <Server>...</Server>  
  <Workload>...</Workload>  
  <TuningOptions>  
    <StorageBoundInMB>1500</StorageBoundInMB>  
...code removed here...  
</DTAInput>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c268b-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c268b-134">See Also</span></span>  
 [<span data-ttu-id="c268b-135">XML-Eingabedateireferenz &#40;Datenbankoptimierungsratgeber&#41;</span><span class="sxs-lookup"><span data-stu-id="c268b-135">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
