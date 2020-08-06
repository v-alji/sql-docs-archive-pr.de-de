---
title: Testserver-Element (DTA) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- TestServer element
ms.assetid: caa3547a-2cd5-47ad-ace2-a36752835cfe
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8d1f1fadf76a43caca262652254e8a778602183c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720656"
---
# <a name="testserver-element-dta"></a><span data-ttu-id="9c625-102">TestServer-Element (DTA)</span><span class="sxs-lookup"><span data-stu-id="9c625-102">TestServer Element (DTA)</span></span>
  <span data-ttu-id="9c625-103">Gibt den Testserver an, der beim Optimieren eines Produktionsservers verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="9c625-103">Specifies the test server to use when tuning a production server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c625-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9c625-104">Syntax</span></span>  
  
```  
  
<TuningOptions>  
  <TestServer>...</TestServer>  
   ...code removed here...  
</TuningOptions>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="9c625-105">Elementmerkmale</span><span class="sxs-lookup"><span data-stu-id="9c625-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="9c625-106">Merkmal</span><span class="sxs-lookup"><span data-stu-id="9c625-106">Characteristic</span></span>|<span data-ttu-id="9c625-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9c625-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="9c625-108">**Datentyp und -länge**</span><span class="sxs-lookup"><span data-stu-id="9c625-108">**Data type and length**</span></span>|<span data-ttu-id="9c625-109">**string**, unbegrenzte Länge.</span><span class="sxs-lookup"><span data-stu-id="9c625-109">**string**, unlimited length.</span></span>|  
|<span data-ttu-id="9c625-110">**Standardwert**</span><span class="sxs-lookup"><span data-stu-id="9c625-110">**Default value**</span></span>|<span data-ttu-id="9c625-111">Keine.</span><span class="sxs-lookup"><span data-stu-id="9c625-111">None.</span></span>|  
|<span data-ttu-id="9c625-112">**Vorkommen**</span><span class="sxs-lookup"><span data-stu-id="9c625-112">**Occurrence**</span></span>|<span data-ttu-id="9c625-113">Optional.</span><span class="sxs-lookup"><span data-stu-id="9c625-113">Optional.</span></span> <span data-ttu-id="9c625-114">Einmalige Verwendung pro `TuningOptions`-Element möglich.</span><span class="sxs-lookup"><span data-stu-id="9c625-114">Can use once for each `TuningOptions` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="9c625-115">Elementbeziehungen</span><span class="sxs-lookup"><span data-stu-id="9c625-115">Element Relationships</span></span>  
  
|<span data-ttu-id="9c625-116">Beziehung</span><span class="sxs-lookup"><span data-stu-id="9c625-116">Relationship</span></span>|<span data-ttu-id="9c625-117">Elemente</span><span class="sxs-lookup"><span data-stu-id="9c625-117">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="9c625-118">**Übergeordnetes Element**</span><span class="sxs-lookup"><span data-stu-id="9c625-118">**Parent element**</span></span>|[<span data-ttu-id="9c625-119">TuningOptions-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="9c625-119">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)|  
|<span data-ttu-id="9c625-120">**Untergeordnete Elemente**</span><span class="sxs-lookup"><span data-stu-id="9c625-120">**Child elements**</span></span>|<span data-ttu-id="9c625-121">Keine.</span><span class="sxs-lookup"><span data-stu-id="9c625-121">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9c625-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9c625-122">Example</span></span>  
 <span data-ttu-id="9c625-123">Ein Beispiel für die Verwendung dieses Elements finden Sie unter [Reduzieren der Optimierungsauslastung des Produktionsservers](../../relational-databases/performance/reduce-the-production-server-tuning-load.md).</span><span class="sxs-lookup"><span data-stu-id="9c625-123">For a usage example of this element, see [Reduce the Production Server Tuning Load](../../relational-databases/performance/reduce-the-production-server-tuning-load.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c625-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9c625-124">See Also</span></span>  
 [<span data-ttu-id="9c625-125">XML-Eingabedateireferenz &#40;Datenbankoptimierungsratgeber&#41;</span><span class="sxs-lookup"><span data-stu-id="9c625-125">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
