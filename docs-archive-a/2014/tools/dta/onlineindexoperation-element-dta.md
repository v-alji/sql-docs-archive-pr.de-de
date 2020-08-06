---
title: OnlineIndexOperation-Element (DTA) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- OnlineIndexOperation element
ms.assetid: 7c5614cd-09aa-4a59-9591-347aa7d36473
author: stevestein
ms.author: sstein
ms.openlocfilehash: 48943c1b31d7a0a24ae939050d44494476e50034
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620097"
---
# <a name="onlineindexoperation-element-dta"></a><span data-ttu-id="94cbd-102">OnlineIndexOperation-Element (DTA)</span><span class="sxs-lookup"><span data-stu-id="94cbd-102">OnlineIndexOperation Element (DTA)</span></span>
  <span data-ttu-id="94cbd-103">Gibt an, ob die vom Datenbankoptimierungsratgeber empfohlenen Indizes, indizierten Sichten oder Partitionen online erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="94cbd-103">Specifies whether the indexes, indexed views, or partitions that Database Engine Tuning Advisor recommends can be created online.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94cbd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="94cbd-104">Syntax</span></span>  
  
```  
  
<DTAInput>  
...code removed...  
    <TuningOptions>  
      <OnlineIndexOperation>...</OnlineIndexOperation>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="94cbd-105">Elementmerkmale</span><span class="sxs-lookup"><span data-stu-id="94cbd-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="94cbd-106">Merkmal</span><span class="sxs-lookup"><span data-stu-id="94cbd-106">Characteristic</span></span>|<span data-ttu-id="94cbd-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="94cbd-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="94cbd-108">**Datentyp und -länge**</span><span class="sxs-lookup"><span data-stu-id="94cbd-108">**Data type and length**</span></span>|<span data-ttu-id="94cbd-109">`string`, keine maximale Länge.</span><span class="sxs-lookup"><span data-stu-id="94cbd-109">`string`, no maximum length.</span></span>|  
|<span data-ttu-id="94cbd-110">**Zulässige Werte**</span><span class="sxs-lookup"><span data-stu-id="94cbd-110">**Allowed values**</span></span>|<span data-ttu-id="94cbd-111">**OFF**</span><span class="sxs-lookup"><span data-stu-id="94cbd-111">**OFF**</span></span><br /> <span data-ttu-id="94cbd-112">Es können keine empfohlenen physischen Entwurfsstrukturen online erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="94cbd-112">No recommended physical design structures can be created online.</span></span><br /><br /> <span data-ttu-id="94cbd-113">**ON**</span><span class="sxs-lookup"><span data-stu-id="94cbd-113">**ON**</span></span><br /> <span data-ttu-id="94cbd-114">Alle empfohlenen physischen Entwurfsstrukturen können online erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="94cbd-114">All recommended physical design structures can be created online.</span></span><br /><br /> <span data-ttu-id="94cbd-115">**GEMISCHT**</span><span class="sxs-lookup"><span data-stu-id="94cbd-115">**MIXED**</span></span><br /> <span data-ttu-id="94cbd-116">Der Datenbankoptimierungsratgeber versucht, sofern möglich physische Entwurfsstrukturen zu empfehlen, die online erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="94cbd-116">Database Engine Tuning Advisor attempts to recommend physical design structures that can be created online when possible.</span></span><br /><br /> <span data-ttu-id="94cbd-117">Verwenden Sie einen dieser Werte mit diesem Element.</span><span class="sxs-lookup"><span data-stu-id="94cbd-117">Use one of these values with this element.</span></span> <span data-ttu-id="94cbd-118">Wenn Indizes online erstellt werden, wird das Schlüsselwort **ONLINE = ON** an die Objektdefinition angehängt.</span><span class="sxs-lookup"><span data-stu-id="94cbd-118">If indexes are created online, the keyword **ONLINE = ON** is appended to its object definition.</span></span>|  
|<span data-ttu-id="94cbd-119">**Standardwert**</span><span class="sxs-lookup"><span data-stu-id="94cbd-119">**Default value**</span></span>|<span data-ttu-id="94cbd-120">Keine.</span><span class="sxs-lookup"><span data-stu-id="94cbd-120">None.</span></span>|  
|<span data-ttu-id="94cbd-121">**Vorkommen**</span><span class="sxs-lookup"><span data-stu-id="94cbd-121">**Occurrence**</span></span>|<span data-ttu-id="94cbd-122">Optional.</span><span class="sxs-lookup"><span data-stu-id="94cbd-122">Optional.</span></span> <span data-ttu-id="94cbd-123">Wenn Sie verwendet wird, kann nur einmal für das-Element verwendet werden `TuningOptions` .</span><span class="sxs-lookup"><span data-stu-id="94cbd-123">If used, can only be used once for the `TuningOptions` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="94cbd-124">Elementbeziehungen</span><span class="sxs-lookup"><span data-stu-id="94cbd-124">Element Relationships</span></span>  
  
|<span data-ttu-id="94cbd-125">Beziehung</span><span class="sxs-lookup"><span data-stu-id="94cbd-125">Relationship</span></span>|<span data-ttu-id="94cbd-126">Elemente</span><span class="sxs-lookup"><span data-stu-id="94cbd-126">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="94cbd-127">**Übergeordnetes Element**</span><span class="sxs-lookup"><span data-stu-id="94cbd-127">**Parent element**</span></span>|[<span data-ttu-id="94cbd-128">TuningOptions-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="94cbd-128">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)|  
|<span data-ttu-id="94cbd-129">**Untergeordnete Elemente**</span><span class="sxs-lookup"><span data-stu-id="94cbd-129">**Child elements**</span></span>|<span data-ttu-id="94cbd-130">Keine.</span><span class="sxs-lookup"><span data-stu-id="94cbd-130">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="94cbd-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="94cbd-131">Example</span></span>  
 <span data-ttu-id="94cbd-132">Ein Beispiel für die Verwendung dieses Elements finden Sie unter [Beispiel für eine einfache XML-Eingabedatei &#40;DTA&#41;](simple-xml-input-file-sample-dta.md).</span><span class="sxs-lookup"><span data-stu-id="94cbd-132">For a usage example of this element, see the [Simple XML Input File Sample &#40;DTA&#41;](simple-xml-input-file-sample-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94cbd-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="94cbd-133">See Also</span></span>  
 [<span data-ttu-id="94cbd-134">XML-Eingabedateireferenz &#40;Datenbankoptimierungsratgeber&#41;</span><span class="sxs-lookup"><span data-stu-id="94cbd-134">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
