---
title: DTAInput-Element (DTA) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- DTAInput element
ms.assetid: 40c19abf-ded5-43de-be96-5b43b1b81b03
author: stevestein
ms.author: sstein
ms.openlocfilehash: e7d2ff380a4ae1595e50aae472efc5fb4ac72efe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696357"
---
# <a name="dtainput-element-dta"></a><span data-ttu-id="87d6c-102">DTAInput-Element (DTA)</span><span class="sxs-lookup"><span data-stu-id="87d6c-102">DTAInput Element (DTA)</span></span>
  <span data-ttu-id="87d6c-103">Enthält die Definition der XML-Eingabe für den Datenbankoptimierungsratgeber.</span><span class="sxs-lookup"><span data-stu-id="87d6c-103">Contains the definition of XML input for Database Engine Tuning Advisor.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87d6c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="87d6c-104">Syntax</span></span>  
  
```  
  
<DTAXML>  
    <DTAInput>  
    ...code removed here...  
    </DTAInput>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="87d6c-105">Elementmerkmale</span><span class="sxs-lookup"><span data-stu-id="87d6c-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="87d6c-106">Merkmale</span><span class="sxs-lookup"><span data-stu-id="87d6c-106">Characteristics</span></span>|<span data-ttu-id="87d6c-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="87d6c-107">Description</span></span>|  
|---------------------|-----------------|  
|<span data-ttu-id="87d6c-108">**Datentyp und -länge**</span><span class="sxs-lookup"><span data-stu-id="87d6c-108">**Data type and length**</span></span>|<span data-ttu-id="87d6c-109">Keine.</span><span class="sxs-lookup"><span data-stu-id="87d6c-109">None.</span></span>|  
|<span data-ttu-id="87d6c-110">**Standardwert**</span><span class="sxs-lookup"><span data-stu-id="87d6c-110">**Default value**</span></span>|<span data-ttu-id="87d6c-111">Keine.</span><span class="sxs-lookup"><span data-stu-id="87d6c-111">None.</span></span>|  
|<span data-ttu-id="87d6c-112">**Vorkommen**</span><span class="sxs-lookup"><span data-stu-id="87d6c-112">**Occurrence**</span></span>|<span data-ttu-id="87d6c-113">Optional einmalig pro **DTAXML** -Element.</span><span class="sxs-lookup"><span data-stu-id="87d6c-113">Optional once per **DTAXML** element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="87d6c-114">Elementbeziehungen</span><span class="sxs-lookup"><span data-stu-id="87d6c-114">Element Relationships</span></span>  
  
|<span data-ttu-id="87d6c-115">Beziehung</span><span class="sxs-lookup"><span data-stu-id="87d6c-115">Relationship</span></span>|<span data-ttu-id="87d6c-116">Elemente</span><span class="sxs-lookup"><span data-stu-id="87d6c-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="87d6c-117">**Übergeordnetes Element**</span><span class="sxs-lookup"><span data-stu-id="87d6c-117">**Parent element**</span></span>|[<span data-ttu-id="87d6c-118">DTAXML-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="87d6c-118">DTAXML Element &#40;DTA&#41;</span></span>](dtaxml-element-dta.md)|  
|<span data-ttu-id="87d6c-119">**Untergeordnete Elemente**</span><span class="sxs-lookup"><span data-stu-id="87d6c-119">**Child elements**</span></span>|[<span data-ttu-id="87d6c-120">Server-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="87d6c-120">Server Element &#40;DTA&#41;</span></span>](server-element-dta.md)<br /><br /> [<span data-ttu-id="87d6c-121">Workload-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="87d6c-121">Workload Element &#40;DTA&#41;</span></span>](workload-element-dta.md)<br /><br /> [<span data-ttu-id="87d6c-122">TuningOptions-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="87d6c-122">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)<br /><br /> [<span data-ttu-id="87d6c-123">Configuration-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="87d6c-123">Configuration Element &#40;DTA&#41;</span></span>](configuration-element-dta.md)|  
  
## <a name="remarks"></a><span data-ttu-id="87d6c-124">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="87d6c-124">Remarks</span></span>  
 <span data-ttu-id="87d6c-125">Dieses Element ist der Stamm der Eingabeschemahierarchie des Datenbankoptimierungsratgebers.</span><span class="sxs-lookup"><span data-stu-id="87d6c-125">This element is the root of the Database Engine Tuning Advisor input schema hierarchy.</span></span> <span data-ttu-id="87d6c-126">Bei Eingaben in den Datenbankoptimierungsratgeber kann es sich um Argumente handeln, mit denen die Server angegeben werden, deren Datenbanken Sie optimieren möchten, oder auch Arbeitsauslastungen, Optimierungsoptionen bzw. eine benutzerspezifische Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="87d6c-126">Input to Database Engine Tuning Advisor can be arguments that specify the servers whose databases you want to tune, workloads, tuning options, or a user-specified configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="87d6c-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="87d6c-127">Example</span></span>  
 <span data-ttu-id="87d6c-128">Ein Beispiel für die Verwendung des **DTAInput**-Elements finden Sie unter [Beispiel für eine einfache XML-Eingabedatei &#40;DTA&#41;](simple-xml-input-file-sample-dta.md).</span><span class="sxs-lookup"><span data-stu-id="87d6c-128">For a usage example of the **DTAInput** element, see [Simple XML Input File Sample &#40;DTA&#41;](simple-xml-input-file-sample-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87d6c-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="87d6c-129">See Also</span></span>  
 [<span data-ttu-id="87d6c-130">XML-Eingabedateireferenz &#40;Datenbankoptimierungsratgeber&#41;</span><span class="sxs-lookup"><span data-stu-id="87d6c-130">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
