---
title: Name-Element für Index (DTA) | Microsoft-Dokumentation
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
ms.assetid: 2300e9cf-f0a8-49e6-b1f5-45ffe03ccb5f
author: stevestein
ms.author: sstein
ms.openlocfilehash: a878923a3d483fae5ad6b55421a2b286f15ceb29
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724302"
---
# <a name="name-element-for-index-dta"></a><span data-ttu-id="05f99-102">Name-Element für Index (DTA)</span><span class="sxs-lookup"><span data-stu-id="05f99-102">Name Element for Index (DTA)</span></span>
  <span data-ttu-id="05f99-103">Gibt einen Namen für einen Index in der benutzerdefinierten Konfiguration an.</span><span class="sxs-lookup"><span data-stu-id="05f99-103">Specifies a name for an index in the user-specified configuration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05f99-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="05f99-104">Syntax</span></span>  
  
```  
  
<Create>  
    <Index>  
        <Name>...</Name>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="05f99-105">Elementmerkmale</span><span class="sxs-lookup"><span data-stu-id="05f99-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="05f99-106">Merkmal</span><span class="sxs-lookup"><span data-stu-id="05f99-106">Characteristic</span></span>|<span data-ttu-id="05f99-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="05f99-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="05f99-108">**Datentyp und -länge**</span><span class="sxs-lookup"><span data-stu-id="05f99-108">**Data type and length**</span></span>|<span data-ttu-id="05f99-109">`string`, unbegrenzte Länge.</span><span class="sxs-lookup"><span data-stu-id="05f99-109">`string`, unlimited length.</span></span>|  
|<span data-ttu-id="05f99-110">**Standardwert**</span><span class="sxs-lookup"><span data-stu-id="05f99-110">**Default value**</span></span>|<span data-ttu-id="05f99-111">Keine.</span><span class="sxs-lookup"><span data-stu-id="05f99-111">None.</span></span>|  
|<span data-ttu-id="05f99-112">**Vorkommen**</span><span class="sxs-lookup"><span data-stu-id="05f99-112">**Occurrence**</span></span>|<span data-ttu-id="05f99-113">Für jedes `Index`-Element erforderlich.</span><span class="sxs-lookup"><span data-stu-id="05f99-113">Required once for each `Index` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="05f99-114">Elementbeziehungen</span><span class="sxs-lookup"><span data-stu-id="05f99-114">Element Relationships</span></span>  
  
|<span data-ttu-id="05f99-115">Beziehung</span><span class="sxs-lookup"><span data-stu-id="05f99-115">Relationship</span></span>|<span data-ttu-id="05f99-116">Elemente</span><span class="sxs-lookup"><span data-stu-id="05f99-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="05f99-117">**Übergeordnetes Element**</span><span class="sxs-lookup"><span data-stu-id="05f99-117">**Parent element**</span></span>|[<span data-ttu-id="05f99-118">Index-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="05f99-118">Index Element &#40;DTA&#41;</span></span>](index-element-dta.md)|  
|<span data-ttu-id="05f99-119">**Untergeordnete Elemente**</span><span class="sxs-lookup"><span data-stu-id="05f99-119">**Child elements**</span></span>|<span data-ttu-id="05f99-120">Keine.</span><span class="sxs-lookup"><span data-stu-id="05f99-120">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="05f99-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="05f99-121">Example</span></span>  
 <span data-ttu-id="05f99-122">Ein Beispiel für die Verwendung dieses Elements finden Sie unter [Beispiel für eine XML-Eingabedatei mit benutzerdefinierter Konfiguration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="05f99-122">For a usage example of this element, see [XML Input File Sample with User-specified Configuration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05f99-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="05f99-123">See Also</span></span>  
 [<span data-ttu-id="05f99-124">XML-Eingabedateireferenz &#40;Datenbankoptimierungsratgeber&#41;</span><span class="sxs-lookup"><span data-stu-id="05f99-124">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
