---
title: TuningTimeInMin-Element (DTA) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- TuningTimeInMin element
ms.assetid: 4973d9ac-20fd-4ac3-bc9f-5d60e39fdb7d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4dae3fe4e9ac3126f43ec017c34d2bc548fda6d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720620"
---
# <a name="tuningtimeinmin-element-dta"></a><span data-ttu-id="e2701-102">TuningTimeInMin-Element (DTA)</span><span class="sxs-lookup"><span data-stu-id="e2701-102">TuningTimeInMin Element (DTA)</span></span>
  <span data-ttu-id="e2701-103">Gibt die maximale Dauer einer Optimierungssitzung in Minuten an.</span><span class="sxs-lookup"><span data-stu-id="e2701-103">Specifies the maximum length of a tuning session in minutes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2701-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e2701-104">Syntax</span></span>  
  
```  
  
<DTAInput>  
...code removed...  
    <TuningOptions>  
      <TuningTimeInMin>...</TuningTimeInMin>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="e2701-105">Elementmerkmale</span><span class="sxs-lookup"><span data-stu-id="e2701-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="e2701-106">Merkmal</span><span class="sxs-lookup"><span data-stu-id="e2701-106">Characteristic</span></span>|<span data-ttu-id="e2701-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e2701-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="e2701-108">**Datentyp und -länge**</span><span class="sxs-lookup"><span data-stu-id="e2701-108">**Data type and length**</span></span>|<span data-ttu-id="e2701-109">`unsignedInt`, unbegrenzte Länge.</span><span class="sxs-lookup"><span data-stu-id="e2701-109">`unsignedInt`, unlimited length.</span></span>|  
|<span data-ttu-id="e2701-110">**Standardwert**</span><span class="sxs-lookup"><span data-stu-id="e2701-110">**Default value**</span></span>|<span data-ttu-id="e2701-111">480 Minuten (8 Stunden).</span><span class="sxs-lookup"><span data-stu-id="e2701-111">480 minutes (8 hours).</span></span>|  
|<span data-ttu-id="e2701-112">**Vorkommen**</span><span class="sxs-lookup"><span data-stu-id="e2701-112">**Occurrence**</span></span>|<span data-ttu-id="e2701-113">Erforderlich, sofern kein Wert für das `NumberOfEvents`-Element festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="e2701-113">Required unless a value has been specified for the `NumberOfEvents` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="e2701-114">Elementbeziehungen</span><span class="sxs-lookup"><span data-stu-id="e2701-114">Element Relationships</span></span>  
  
|<span data-ttu-id="e2701-115">Beziehung</span><span class="sxs-lookup"><span data-stu-id="e2701-115">Relationship</span></span>|<span data-ttu-id="e2701-116">Elemente</span><span class="sxs-lookup"><span data-stu-id="e2701-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="e2701-117">**Übergeordnetes Element**</span><span class="sxs-lookup"><span data-stu-id="e2701-117">**Parent element**</span></span>|[<span data-ttu-id="e2701-118">TuningOptions-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="e2701-118">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)|  
|<span data-ttu-id="e2701-119">**Untergeordnete Elemente**</span><span class="sxs-lookup"><span data-stu-id="e2701-119">**Child elements**</span></span>|<span data-ttu-id="e2701-120">Keine</span><span class="sxs-lookup"><span data-stu-id="e2701-120">None</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e2701-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e2701-121">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="e2701-122">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e2701-122">Description</span></span>  
 <span data-ttu-id="e2701-123">Im folgenden Codebeispiel wird gezeigt, wie 12 Stunden als maximale Optimierungszeit festgelegt werden:</span><span class="sxs-lookup"><span data-stu-id="e2701-123">The following code example shows how to set 12 hours as the maximum tuning time:</span></span>  
  
## <a name="code"></a><span data-ttu-id="e2701-124">Code</span><span class="sxs-lookup"><span data-stu-id="e2701-124">Code</span></span>  
  
```  
<DTAInput>  
  <Server>...</Server>  
  <Workload>...</Workload>  
  <TuningOptions>  
    <TuningTimeInMin>720</TuningTimeInMin>  
...code removed here...  
</DTAInput>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e2701-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e2701-125">See Also</span></span>  
 [<span data-ttu-id="e2701-126">XML-Eingabedateireferenz &#40;Datenbankoptimierungsratgeber&#41;</span><span class="sxs-lookup"><span data-stu-id="e2701-126">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
