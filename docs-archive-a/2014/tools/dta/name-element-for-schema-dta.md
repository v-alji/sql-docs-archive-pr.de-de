---
title: Name-Element für Schema (DTA) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Name element
ms.assetid: 014e4854-fed2-454b-8557-5f7c5bb6b17a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 678a6d58b35b25be2aed6d91fcae7ceb2640bdcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719186"
---
# <a name="name-element-for-schema-dta"></a><span data-ttu-id="287b7-102">Namen-Element für Schema (DTA)</span><span class="sxs-lookup"><span data-stu-id="287b7-102">Name Element for Schema (DTA)</span></span>
  <span data-ttu-id="287b7-103">Enthält den Namen des Schemas.</span><span class="sxs-lookup"><span data-stu-id="287b7-103">Contains name of the schema.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="287b7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="287b7-104">Syntax</span></span>  
  
```  
  
<Database>  
...code removed here  
    <Schema>  
        <Name>...</Name>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="287b7-105">Elementmerkmale</span><span class="sxs-lookup"><span data-stu-id="287b7-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="287b7-106">Merkmal</span><span class="sxs-lookup"><span data-stu-id="287b7-106">Characteristic</span></span>|<span data-ttu-id="287b7-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="287b7-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="287b7-108">**Datentyp und -länge**</span><span class="sxs-lookup"><span data-stu-id="287b7-108">**Data type and length**</span></span>|<span data-ttu-id="287b7-109">`string`, 1 bis 255 Zeichen</span><span class="sxs-lookup"><span data-stu-id="287b7-109">`string`, between 1 and 255 characters</span></span>|  
|<span data-ttu-id="287b7-110">**Standardwert**</span><span class="sxs-lookup"><span data-stu-id="287b7-110">**Default value**</span></span>|<span data-ttu-id="287b7-111">Keine.</span><span class="sxs-lookup"><span data-stu-id="287b7-111">None.</span></span>|  
|<span data-ttu-id="287b7-112">**Vorkommen**</span><span class="sxs-lookup"><span data-stu-id="287b7-112">**Occurrence**</span></span>|<span data-ttu-id="287b7-113">Einmalig pro **Schema** -Element erforderlich.</span><span class="sxs-lookup"><span data-stu-id="287b7-113">Required once per **Schema** element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="287b7-114">Elementbeziehungen</span><span class="sxs-lookup"><span data-stu-id="287b7-114">Element Relationships</span></span>  
  
|<span data-ttu-id="287b7-115">Beziehung</span><span class="sxs-lookup"><span data-stu-id="287b7-115">Relationship</span></span>|<span data-ttu-id="287b7-116">Elemente</span><span class="sxs-lookup"><span data-stu-id="287b7-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="287b7-117">**Übergeordnetes Element**</span><span class="sxs-lookup"><span data-stu-id="287b7-117">**Parent element**</span></span>|[<span data-ttu-id="287b7-118">Schema-Element für Datenbank &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="287b7-118">Schema Element for Database &#40;DTA&#41;</span></span>](schema-element-for-database-dta.md)|  
|<span data-ttu-id="287b7-119">**Untergeordnete Elemente**</span><span class="sxs-lookup"><span data-stu-id="287b7-119">**Child elements**</span></span>|<span data-ttu-id="287b7-120">Keine.</span><span class="sxs-lookup"><span data-stu-id="287b7-120">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="287b7-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="287b7-121">Example</span></span>  
 <span data-ttu-id="287b7-122">Ein Beispiel für die Verwendung dieses Elements finden Sie unter [Server-Element &#40;DTA&#41;](server-element-dta.md).</span><span class="sxs-lookup"><span data-stu-id="287b7-122">For a usage example of this element, see [Server Element &#40;DTA&#41;](server-element-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="287b7-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="287b7-123">See Also</span></span>  
 [<span data-ttu-id="287b7-124">XML-Eingabedateireferenz &#40;Datenbankoptimierungsratgeber&#41;</span><span class="sxs-lookup"><span data-stu-id="287b7-124">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
