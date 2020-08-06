---
title: FILEGROUP-Element für Index (DTA) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Filegroup element [DTA]
ms.assetid: 7078d2fb-fa77-44fc-beb3-c095088fcb85
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5ed8ea723d6c0798b93e16411ee47d6e956c6c22
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720659"
---
# <a name="filegroup-element-for-index-dta"></a><span data-ttu-id="a721e-102">Filegroup-Element für Index (DTA)</span><span class="sxs-lookup"><span data-stu-id="a721e-102">Filegroup Element for Index (DTA)</span></span>
  <span data-ttu-id="a721e-103">Gibt die Dateigruppe an, für die der Index für eine benutzerspezifische Konfiguration erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a721e-103">Specifies the filegroup on which the index is to be created for a user-specified configuration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a721e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a721e-104">Syntax</span></span>  
  
```  
  
<Index>  
  <Name>...</Name>  
  <Column>  
    <Name>...</Name>  
  <Filegroup>...</Filegroup>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="a721e-105">Elementmerkmale</span><span class="sxs-lookup"><span data-stu-id="a721e-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="a721e-106">Merkmal</span><span class="sxs-lookup"><span data-stu-id="a721e-106">Characteristic</span></span>|<span data-ttu-id="a721e-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a721e-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="a721e-108">**Datentyp und -länge**</span><span class="sxs-lookup"><span data-stu-id="a721e-108">**Data type and length**</span></span>|<span data-ttu-id="a721e-109">`string`, unbegrenzte Länge.</span><span class="sxs-lookup"><span data-stu-id="a721e-109">`string`, unlimited length.</span></span>|  
|<span data-ttu-id="a721e-110">**Standardwert**</span><span class="sxs-lookup"><span data-stu-id="a721e-110">**Default value**</span></span>|<span data-ttu-id="a721e-111">Keine.</span><span class="sxs-lookup"><span data-stu-id="a721e-111">None.</span></span>|  
|<span data-ttu-id="a721e-112">**Vorkommen**</span><span class="sxs-lookup"><span data-stu-id="a721e-112">**Occurrence**</span></span>|<span data-ttu-id="a721e-113">Optional.</span><span class="sxs-lookup"><span data-stu-id="a721e-113">Optional.</span></span> <span data-ttu-id="a721e-114">Einmalige Verwendung pro `Index`-Element möglich.</span><span class="sxs-lookup"><span data-stu-id="a721e-114">Can use once for each `Index` element.</span></span> <span data-ttu-id="a721e-115">Dieses Element kann nicht verwendet werden, wenn die `PartitionScheme`- und `PartitionColumn`-Elemente für das `Index`-Element angegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="a721e-115">This element cannot be used if the `PartitionScheme` and `PartitionColumn` elements are specified for the `Index` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="a721e-116">Elementbeziehungen</span><span class="sxs-lookup"><span data-stu-id="a721e-116">Element Relationships</span></span>  
  
|<span data-ttu-id="a721e-117">Beziehung</span><span class="sxs-lookup"><span data-stu-id="a721e-117">Relationship</span></span>|<span data-ttu-id="a721e-118">Elemente</span><span class="sxs-lookup"><span data-stu-id="a721e-118">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="a721e-119">**Übergeordnetes Element**</span><span class="sxs-lookup"><span data-stu-id="a721e-119">**Parent element**</span></span>|[<span data-ttu-id="a721e-120">Index-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="a721e-120">Index Element &#40;DTA&#41;</span></span>](index-element-dta.md)|  
|<span data-ttu-id="a721e-121">**Untergeordnete Elemente**</span><span class="sxs-lookup"><span data-stu-id="a721e-121">**Child elements**</span></span>|<span data-ttu-id="a721e-122">Keine.</span><span class="sxs-lookup"><span data-stu-id="a721e-122">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a721e-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a721e-123">Example</span></span>  
 <span data-ttu-id="a721e-124">Ein Beispiel für die Verwendung dieses Elements finden Sie unter [Beispiel für eine XML-Eingabedatei mit benutzerdefinierter Konfiguration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="a721e-124">For a usage example of this element, see [XML Input File Sample with User-specified Configuration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a721e-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a721e-125">See Also</span></span>  
 [<span data-ttu-id="a721e-126">XML-Eingabedateireferenz &#40;Datenbankoptimierungsratgeber&#41;</span><span class="sxs-lookup"><span data-stu-id="a721e-126">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
