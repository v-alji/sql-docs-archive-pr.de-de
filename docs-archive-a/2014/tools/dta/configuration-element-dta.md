---
title: Configuration-Element (DTA) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Configuration element
ms.assetid: 1478e56f-57c4-4441-bac9-1ac91453839b
author: stevestein
ms.author: sstein
ms.openlocfilehash: d11938d9a9a694f994a3ea977022a393cbae23d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695038"
---
# <a name="configuration-element-dta"></a><span data-ttu-id="4d74d-102">Configuration-Element (DTA)</span><span class="sxs-lookup"><span data-stu-id="4d74d-102">Configuration Element (DTA)</span></span>
  <span data-ttu-id="4d74d-103">Gibt eine benutzerdefinierte Konfiguration an, die aus vorhandenen und hypothetischen physischen Entwurfsstrukturen besteht, die der Datenbankoptimierungsratgeber beim Optimieren einer Arbeitsauslastung analysiert.</span><span class="sxs-lookup"><span data-stu-id="4d74d-103">Specifies a user-specified configuration consisting of existing and hypothetical physical design structures for the Database Engine Tuning Advisor to analyze when tuning a workload.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d74d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4d74d-104">Syntax</span></span>  
  
```  
  
<DTAInput>  
    <Server>...</Server>  
    <Workload>...</Workload>  
    <TuningOptions>...</TuningOptions  
    <Configuration [SpecificationMode="Relative" | "Absolute"]>  
    ...code removed here...  
    </Configuration>  
</DTAInput>  
```  
  
## <a name="element-attributes"></a><span data-ttu-id="4d74d-105">Elementattribute</span><span class="sxs-lookup"><span data-stu-id="4d74d-105">Element Attributes</span></span>  
  
|<span data-ttu-id="4d74d-106">Konfigurationsattribut</span><span class="sxs-lookup"><span data-stu-id="4d74d-106">Configuration Attribute</span></span>|<span data-ttu-id="4d74d-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4d74d-107">Description</span></span>|  
|-----------------------------|-----------------|  
|`SpecificationMode`|<span data-ttu-id="4d74d-108">Optional.</span><span class="sxs-lookup"><span data-stu-id="4d74d-108">Optional.</span></span> <span data-ttu-id="4d74d-109">Gibt an, ob der Datenbankoptimierungsratgeber die angegebene Konfiguration im Vergleich zur aktuellen vorhandenen Konfiguration oder als vollständig neue eigenständige Konfiguration analysieren soll.</span><span class="sxs-lookup"><span data-stu-id="4d74d-109">Specifies whether Database Engine Tuning Advisor should analyze the specified configuration in relation to the current existing configuration, or as a completely new, standalone one.</span></span> <span data-ttu-id="4d74d-110">Mit einem **string** -Datentyp können Sie dieses Attribut mit einem der folgenden zulässigen Werte angeben:</span><span class="sxs-lookup"><span data-stu-id="4d74d-110">Use a **string** data type to specify this attribute with one of the following allowed values:</span></span><br /><br /> <span data-ttu-id="4d74d-111">`Relative`:</span><span class="sxs-lookup"><span data-stu-id="4d74d-111">`Relative`:</span></span> <br />                  <span data-ttu-id="4d74d-112">Wertet die angegebene Konfiguration im Vergleich zur aktuellen vorhandenen Konfiguration physischer Entwurfsstrukturen (Indizes, indizierte Sichten, Partitionierung) in der Datenbank aus, die optimiert wird.</span><span class="sxs-lookup"><span data-stu-id="4d74d-112">Evaluates the specified configuration in relation to the current existing configuration of physical design structures (indexes, indexed views, partitioning) in the database that is being tuned.</span></span> <span data-ttu-id="4d74d-113">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="4d74d-113">For example:</span></span> <br />`<Configuration SpecificationMode="Relative">`<br /><br /> <span data-ttu-id="4d74d-114">`Absolute`:</span><span class="sxs-lookup"><span data-stu-id="4d74d-114">`Absolute`:</span></span> <br />                  <span data-ttu-id="4d74d-115">Wertet die angegebene Konfiguration als eigenständige Konfiguration aus.</span><span class="sxs-lookup"><span data-stu-id="4d74d-115">Evaluates the specified configuration as a standalone configuration.</span></span> <span data-ttu-id="4d74d-116">Wenn der Absolute-Wert angegeben ist, wird die vorhandene Konfiguration nicht vom Datenbankoptimierungsratgeber berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="4d74d-116">When Absolute is specified, Database Engine Tuning Advisor does not consider the existing configuration.</span></span> <span data-ttu-id="4d74d-117">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="4d74d-117">For example:</span></span><br />`<Configuration SpecificationMode="Absolute">`|  
  
## <a name="element-characteristics"></a><span data-ttu-id="4d74d-118">Elementmerkmale</span><span class="sxs-lookup"><span data-stu-id="4d74d-118">Element Characteristics</span></span>  
  
|<span data-ttu-id="4d74d-119">Merkmal</span><span class="sxs-lookup"><span data-stu-id="4d74d-119">Characteristic</span></span>|<span data-ttu-id="4d74d-120">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4d74d-120">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="4d74d-121">**Datentyp und -länge**</span><span class="sxs-lookup"><span data-stu-id="4d74d-121">**Data type and length**</span></span>|<span data-ttu-id="4d74d-122">Keine.</span><span class="sxs-lookup"><span data-stu-id="4d74d-122">None.</span></span>|  
|<span data-ttu-id="4d74d-123">**Standardwert**</span><span class="sxs-lookup"><span data-stu-id="4d74d-123">**Default value**</span></span>|<span data-ttu-id="4d74d-124">Keine.</span><span class="sxs-lookup"><span data-stu-id="4d74d-124">None.</span></span>|  
|<span data-ttu-id="4d74d-125">**Vorkommen**</span><span class="sxs-lookup"><span data-stu-id="4d74d-125">**Occurrence**</span></span>|<span data-ttu-id="4d74d-126">Optional.</span><span class="sxs-lookup"><span data-stu-id="4d74d-126">Optional.</span></span> <span data-ttu-id="4d74d-127">Einmalige Verwendung pro `DTAInput`-Element möglich.</span><span class="sxs-lookup"><span data-stu-id="4d74d-127">Can use once for each `DTAInput` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="4d74d-128">Elementbeziehungen</span><span class="sxs-lookup"><span data-stu-id="4d74d-128">Element Relationships</span></span>  
  
|<span data-ttu-id="4d74d-129">Beziehung</span><span class="sxs-lookup"><span data-stu-id="4d74d-129">Relationship</span></span>|<span data-ttu-id="4d74d-130">Elemente</span><span class="sxs-lookup"><span data-stu-id="4d74d-130">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="4d74d-131">**Übergeordnetes Element**</span><span class="sxs-lookup"><span data-stu-id="4d74d-131">**Parent element**</span></span>|[<span data-ttu-id="4d74d-132">DTAInput-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="4d74d-132">DTAInput Element &#40;DTA&#41;</span></span>](dtainput-element-dta.md)|  
|<span data-ttu-id="4d74d-133">**Untergeordnete Elemente**</span><span class="sxs-lookup"><span data-stu-id="4d74d-133">**Child elements**</span></span>|[<span data-ttu-id="4d74d-134">Server-Element für Konfiguration &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="4d74d-134">Server Element for Configuration &#40;DTA&#41;</span></span>](server-element-for-configuration-dta.md)|  
  
## <a name="example"></a><span data-ttu-id="4d74d-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4d74d-135">Example</span></span>  
 <span data-ttu-id="4d74d-136">Ein Beispiel für die Verwendung dieses Elements finden Sie unter [Beispiel für eine XML-Eingabedatei mit benutzerdefinierter Konfiguration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="4d74d-136">For a usage example of this element, see the [XML Input File Sample with User-specified Configuration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d74d-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4d74d-137">See Also</span></span>  
 [<span data-ttu-id="4d74d-138">XML-Eingabedateireferenz &#40;Datenbankoptimierungsratgeber&#41;</span><span class="sxs-lookup"><span data-stu-id="4d74d-138">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
