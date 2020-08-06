---
title: Create-Element (DTA) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Create element (DTA)
ms.assetid: 9d076c90-f933-45f4-b6d9-447793f6528b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 407f16c3898e56cd393e36c39ed799b83e0092ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695018"
---
# <a name="create-element-dta"></a><span data-ttu-id="0929f-102">Create-Element (DTA)</span><span class="sxs-lookup"><span data-stu-id="0929f-102">Create Element (DTA)</span></span>
  <span data-ttu-id="0929f-103">Enthält Informationen zu den Indizes, Statistiken oder Heapstrukturen in einer benutzerspezifischen Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="0929f-103">Contains information about the indexes, statistics, or heap structures in a user-specified configuration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0929f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0929f-104">Syntax</span></span>  
  
```  
  
<Recommendation>  
    <Create>  
    ...code removed here...  
    </Create>  
</Recommendation>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="0929f-105">Elementmerkmale</span><span class="sxs-lookup"><span data-stu-id="0929f-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="0929f-106">Merkmal</span><span class="sxs-lookup"><span data-stu-id="0929f-106">Characteristic</span></span>|<span data-ttu-id="0929f-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0929f-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="0929f-108">**Datentyp und -länge**</span><span class="sxs-lookup"><span data-stu-id="0929f-108">**Data type and length**</span></span>|<span data-ttu-id="0929f-109">Keine.</span><span class="sxs-lookup"><span data-stu-id="0929f-109">None.</span></span>|  
|<span data-ttu-id="0929f-110">**Standardwert**</span><span class="sxs-lookup"><span data-stu-id="0929f-110">**Default value**</span></span>|<span data-ttu-id="0929f-111">Keine.</span><span class="sxs-lookup"><span data-stu-id="0929f-111">None.</span></span>|  
|<span data-ttu-id="0929f-112">**Vorkommen**</span><span class="sxs-lookup"><span data-stu-id="0929f-112">**Occurrence**</span></span>|<span data-ttu-id="0929f-113">Einmalig erforderlich pro physischem Entwurfsstrukturtyp (Indizes, Statistiken oder Heapstrukturen).</span><span class="sxs-lookup"><span data-stu-id="0929f-113">Required once for each physical design structure type (indexes, statistics, or heap structures).</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="0929f-114">Elementbeziehungen</span><span class="sxs-lookup"><span data-stu-id="0929f-114">Element Relationships</span></span>  
  
|<span data-ttu-id="0929f-115">Beziehung</span><span class="sxs-lookup"><span data-stu-id="0929f-115">Relationship</span></span>|<span data-ttu-id="0929f-116">Elemente</span><span class="sxs-lookup"><span data-stu-id="0929f-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="0929f-117">**Übergeordnetes Element**</span><span class="sxs-lookup"><span data-stu-id="0929f-117">**Parent element**</span></span>|[<span data-ttu-id="0929f-118">Recommendation-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="0929f-118">Recommendation Element &#40;DTA&#41;</span></span>](recommendation-element-dta.md)|  
|<span data-ttu-id="0929f-119">**Untergeordnete Elemente**</span><span class="sxs-lookup"><span data-stu-id="0929f-119">**Child elements**</span></span>|[<span data-ttu-id="0929f-120">Index-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="0929f-120">Index Element &#40;DTA&#41;</span></span>](index-element-dta.md)<br /><br /> <span data-ttu-id="0929f-121">`Statistics`-Element (Weitere Informationen finden Sie unter [Datenbankoptimierungsratgeber XML-Schema](https://schemas.microsoft.com/sqlserver/) )</span><span class="sxs-lookup"><span data-stu-id="0929f-121">`Statistics` Element (see [Database Engine Tuning Advisor XML schema](https://schemas.microsoft.com/sqlserver/) for information)</span></span><br /><br /> <span data-ttu-id="0929f-122">`Heap`-Element (Weitere Informationen finden Sie unter [Datenbankoptimierungsratgeber XML-Schema](https://schemas.microsoft.com/sqlserver/) )</span><span class="sxs-lookup"><span data-stu-id="0929f-122">`Heap` Element (see [Database Engine Tuning Advisor XML schema](https://schemas.microsoft.com/sqlserver/) for information)</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0929f-123">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="0929f-123">Remarks</span></span>  
 <span data-ttu-id="0929f-124">Dieses Element hat den Namen **CreateTypecomplexType** im XML-Schema des Datenbankoptimierungsratgebers.</span><span class="sxs-lookup"><span data-stu-id="0929f-124">This element is of the **CreateTypecomplexType** name in the Database Engine Tuning Advisor XML schema.</span></span> <span data-ttu-id="0929f-125">Es wird zum Erstellen von Indizes, Statistiken und Heapstrukturen für eine benutzerspezifische Konfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="0929f-125">It is used to create indexes, statistics, and heap structures for a user-specified configuration.</span></span> <span data-ttu-id="0929f-126">Dieses `Create`-Element ist nicht mit den anderen Typen identisch, mit denen Sichten (`CreateViewType`) oder Partitionierungen (`CreatePType`) erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="0929f-126">Do not confuse this `Create` element with the other types that can be used to create views (`CreateViewType`) or partitioning (`CreatePType`).</span></span> <span data-ttu-id="0929f-127">Informationen zu diesen anderen Elementtypen finden Sie im [Datenbankoptimierungsratgeber XML-Schema](https://schemas.microsoft.com/sqlserver/) `Create` .</span><span class="sxs-lookup"><span data-stu-id="0929f-127">Refer to the [Database Engine Tuning Advisor XML schema](https://schemas.microsoft.com/sqlserver/) for information about these other `Create` element types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0929f-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0929f-128">Example</span></span>  
 <span data-ttu-id="0929f-129">Ein Beispiel für die Verwendung dieses Elements finden Sie unter [Beispiel für eine XML-Eingabedatei mit benutzerdefinierter Konfiguration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="0929f-129">For a usage example of this element, see the [XML Input File Sample with User-specified Configuration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0929f-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0929f-130">See Also</span></span>  
 [<span data-ttu-id="0929f-131">XML-Eingabedateireferenz &#40;Datenbankoptimierungsratgeber&#41;</span><span class="sxs-lookup"><span data-stu-id="0929f-131">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
