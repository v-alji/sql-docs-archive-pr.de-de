---
title: Name-Element für Spalte (DTA) | Microsoft-Dokumentation
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
ms.assetid: f93b61de-01fe-4237-ada4-f1e481550564
author: stevestein
ms.author: sstein
ms.openlocfilehash: fad3d9a86a7c5db6b6a7503dc90b5a1540e3618b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694990"
---
# <a name="name-element-for-column-dta"></a><span data-ttu-id="759b6-102">Name-Element für Spalte (DTA)</span><span class="sxs-lookup"><span data-stu-id="759b6-102">Name Element for Column (DTA)</span></span>
  <span data-ttu-id="759b6-103">Gibt den Namen für eine Indexspalte in einer benutzerdefinierten Konfiguration an.</span><span class="sxs-lookup"><span data-stu-id="759b6-103">Specifies the name for an index column in a user-specified configuration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="759b6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="759b6-104">Syntax</span></span>  
  
```  
  
<Index>  
    <Column>  
        <Name>...</Name>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="759b6-105">Elementmerkmale</span><span class="sxs-lookup"><span data-stu-id="759b6-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="759b6-106">Merkmal</span><span class="sxs-lookup"><span data-stu-id="759b6-106">Characteristic</span></span>|<span data-ttu-id="759b6-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="759b6-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="759b6-108">**Datentyp und -länge**</span><span class="sxs-lookup"><span data-stu-id="759b6-108">**Data type and length**</span></span>|<span data-ttu-id="759b6-109">`string`, unbegrenzte Länge.</span><span class="sxs-lookup"><span data-stu-id="759b6-109">`string`, unlimited length.</span></span>|  
|<span data-ttu-id="759b6-110">**Standardwert**</span><span class="sxs-lookup"><span data-stu-id="759b6-110">**Default value**</span></span>|<span data-ttu-id="759b6-111">Keine.</span><span class="sxs-lookup"><span data-stu-id="759b6-111">None.</span></span>|  
|<span data-ttu-id="759b6-112">**Vorkommen**</span><span class="sxs-lookup"><span data-stu-id="759b6-112">**Occurrence**</span></span>|<span data-ttu-id="759b6-113">Für jedes `Column`-Element erforderlich.</span><span class="sxs-lookup"><span data-stu-id="759b6-113">Required once for each `Column` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="759b6-114">Elementbeziehungen</span><span class="sxs-lookup"><span data-stu-id="759b6-114">Element Relationships</span></span>  
  
|<span data-ttu-id="759b6-115">Beziehung</span><span class="sxs-lookup"><span data-stu-id="759b6-115">Relationship</span></span>|<span data-ttu-id="759b6-116">Elemente</span><span class="sxs-lookup"><span data-stu-id="759b6-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="759b6-117">**Übergeordnetes Element**</span><span class="sxs-lookup"><span data-stu-id="759b6-117">**Parent element**</span></span>|[<span data-ttu-id="759b6-118">Column-Element für Index &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="759b6-118">Column Element for Index &#40;DTA&#41;</span></span>](column-element-for-index-dta.md)|  
|<span data-ttu-id="759b6-119">**Untergeordnete Elemente**</span><span class="sxs-lookup"><span data-stu-id="759b6-119">**Child elements**</span></span>|<span data-ttu-id="759b6-120">Keine.</span><span class="sxs-lookup"><span data-stu-id="759b6-120">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="759b6-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="759b6-121">Example</span></span>  
 <span data-ttu-id="759b6-122">Ein Beispiel für die Verwendung dieses Elements finden Sie unter [Beispiel für eine XML-Eingabedatei mit benutzerdefinierter Konfiguration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="759b6-122">For a usage example of this element, see [XML Input File Sample with User-specified Configuration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="759b6-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="759b6-123">See Also</span></span>  
 [<span data-ttu-id="759b6-124">XML-Eingabedateireferenz &#40;Datenbankoptimierungsratgeber&#41;</span><span class="sxs-lookup"><span data-stu-id="759b6-124">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
