---
title: Empfehlungs-Element (DTA) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Recommendation element
ms.assetid: 679ea535-865a-4633-a4d3-5b3090515158
author: stevestein
ms.author: sstein
ms.openlocfilehash: b4eb54a106d67f0217a2604b2d08754d0d2c0765
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609615"
---
# <a name="recommendation-element-dta"></a><span data-ttu-id="881e4-102">Recommendation-Element (DTA)</span><span class="sxs-lookup"><span data-stu-id="881e4-102">Recommendation Element (DTA)</span></span>
  <span data-ttu-id="881e4-103">Enthält Informationen zu den hypothetischen Indizes, die Teil einer benutzerspezifischen Konfiguration sind.</span><span class="sxs-lookup"><span data-stu-id="881e4-103">Contains information about the hypothetical indexes that are part of a user-specified configuration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="881e4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="881e4-104">Syntax</span></span>  
  
```  
  
<Configuration>  
    ...code removed here...  
    <Table>  
      <Name>...</Name>  
      <Recommendation>  
      ...code removed here...  
      </Recommendation>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="881e4-105">Elementmerkmale</span><span class="sxs-lookup"><span data-stu-id="881e4-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="881e4-106">Merkmal</span><span class="sxs-lookup"><span data-stu-id="881e4-106">Characteristic</span></span>|<span data-ttu-id="881e4-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="881e4-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="881e4-108">**Datentyp und -länge**</span><span class="sxs-lookup"><span data-stu-id="881e4-108">**Data type and length**</span></span>|<span data-ttu-id="881e4-109">Keine.</span><span class="sxs-lookup"><span data-stu-id="881e4-109">None.</span></span>|  
|<span data-ttu-id="881e4-110">**Standardwert**</span><span class="sxs-lookup"><span data-stu-id="881e4-110">**Default value**</span></span>|<span data-ttu-id="881e4-111">Keine.</span><span class="sxs-lookup"><span data-stu-id="881e4-111">None.</span></span>|  
|<span data-ttu-id="881e4-112">**Vorkommen**</span><span class="sxs-lookup"><span data-stu-id="881e4-112">**Occurrence**</span></span>|<span data-ttu-id="881e4-113">Optional.</span><span class="sxs-lookup"><span data-stu-id="881e4-113">Optional.</span></span> <span data-ttu-id="881e4-114">Einmalige Verwendung pro `Table`-Element möglich.</span><span class="sxs-lookup"><span data-stu-id="881e4-114">Can use once for each `Table` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="881e4-115">Elementbeziehungen</span><span class="sxs-lookup"><span data-stu-id="881e4-115">Element Relationships</span></span>  
  
|<span data-ttu-id="881e4-116">Beziehung</span><span class="sxs-lookup"><span data-stu-id="881e4-116">Relationship</span></span>|<span data-ttu-id="881e4-117">Elemente</span><span class="sxs-lookup"><span data-stu-id="881e4-117">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="881e4-118">**Übergeordnetes Element**</span><span class="sxs-lookup"><span data-stu-id="881e4-118">**Parent element**</span></span>|[<span data-ttu-id="881e4-119">Table-Element für Schema &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="881e4-119">Table Element for Schema &#40;DTA&#41;</span></span>](table-element-for-schema-dta.md)|  
|<span data-ttu-id="881e4-120">**Untergeordnete Elemente**</span><span class="sxs-lookup"><span data-stu-id="881e4-120">**Child elements**</span></span>|[<span data-ttu-id="881e4-121">Create Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="881e4-121">Create Element &#40;DTA&#41;</span></span>](create-element-dta.md)<br /><br /> <span data-ttu-id="881e4-122">`Drop`-Element.</span><span class="sxs-lookup"><span data-stu-id="881e4-122">`Drop` element.</span></span> <span data-ttu-id="881e4-123">Weitere Informationen finden Sie im [XML-Schema des Datenbankoptimierungsratgebers](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="881e4-123">For more information, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="881e4-124">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="881e4-124">Remarks</span></span>  
 <span data-ttu-id="881e4-125">Dieses Element hat den Namen **CreateTypecomplexType** im XML-Schema des Datenbankoptimierungsratgebers.</span><span class="sxs-lookup"><span data-stu-id="881e4-125">This element is of the **RecommendationTypecomplexType** name in the Database Engine Tuning Advisor XML schema.</span></span> <span data-ttu-id="881e4-126">Es wird zur Angabe von Indizes für eine hypothetische Konfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="881e4-126">It is used to specify indexes for a hypothetical configuration.</span></span> <span data-ttu-id="881e4-127">Dieses `Recommendation`-Element ist nicht mit den anderen Typen identisch, die zum Angeben von Partitionierungen (`RecommendationPType`) oder Sichten (`RecommendationViewType`) verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="881e4-127">Do not confuse this `Recommendation` element with the other types that can be used to specify partitioning (`RecommendationPType`) or views (`RecommendationViewType`).</span></span> <span data-ttu-id="881e4-128">Weitere Informationen zu diesen anderen `Recommendation` Elementtypen finden Sie im [Datenbankoptimierungsratgeber XML-Schema](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="881e4-128">For information about these other `Recommendation` element types, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span>  
  
## <a name="example"></a><span data-ttu-id="881e4-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="881e4-129">Example</span></span>  
 <span data-ttu-id="881e4-130">Ein Beispiel für die Verwendung dieses Elements finden Sie unter [Beispiel für eine XML-Eingabedatei mit benutzerdefinierter Konfiguration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="881e4-130">For a usage example of this element, see the [XML Input File Sample with User-specified Configuration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="881e4-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="881e4-131">See Also</span></span>  
 [<span data-ttu-id="881e4-132">XML-Eingabedateireferenz &#40;Datenbankoptimierungsratgeber&#41;</span><span class="sxs-lookup"><span data-stu-id="881e4-132">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
