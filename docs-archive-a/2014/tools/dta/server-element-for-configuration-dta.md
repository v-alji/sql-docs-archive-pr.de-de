---
title: Server-Element für Konfiguration (DTA) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Server element
ms.assetid: da9ff870-9cfd-42fe-994b-7b9292681f7d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 88182cdad2e7313f0910a106ee37d727d840bfed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620090"
---
# <a name="server-element-for-configuration-dta"></a><span data-ttu-id="72bb1-102">Server-Element für Konfiguration (DTA)</span><span class="sxs-lookup"><span data-stu-id="72bb1-102">Server Element for Configuration (DTA)</span></span>
  <span data-ttu-id="72bb1-103">Enthält die Identifikationsinformationen für den Server, auf dem der Datenbankoptimierungsratgeber die hypothetische Konfiguration auswerten soll (wird durch das `Configuration`-Element angegeben).</span><span class="sxs-lookup"><span data-stu-id="72bb1-103">Contains the identifying information for the server where you want Database Engine Tuning Advisor to evaluate the hypothetical configuration (specified by the `Configuration` element).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72bb1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="72bb1-104">Syntax</span></span>  
  
```  
  
<Configuration>  
    <Server>  
...code removed here...  
    </Server>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="72bb1-105">Elementmerkmale</span><span class="sxs-lookup"><span data-stu-id="72bb1-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="72bb1-106">Merkmal</span><span class="sxs-lookup"><span data-stu-id="72bb1-106">Characteristic</span></span>|<span data-ttu-id="72bb1-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="72bb1-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="72bb1-108">**Datentyp und -länge**</span><span class="sxs-lookup"><span data-stu-id="72bb1-108">**Data type and length**</span></span>|<span data-ttu-id="72bb1-109">Keine.</span><span class="sxs-lookup"><span data-stu-id="72bb1-109">None.</span></span>|  
|<span data-ttu-id="72bb1-110">**Standardwert**</span><span class="sxs-lookup"><span data-stu-id="72bb1-110">**Default value**</span></span>|<span data-ttu-id="72bb1-111">Keine.</span><span class="sxs-lookup"><span data-stu-id="72bb1-111">None.</span></span>|  
|<span data-ttu-id="72bb1-112">**Vorkommen**</span><span class="sxs-lookup"><span data-stu-id="72bb1-112">**Occurrence**</span></span>|<span data-ttu-id="72bb1-113">Einmal pro `Configuration`-Element erforderlich.</span><span class="sxs-lookup"><span data-stu-id="72bb1-113">Required once per `Configuration` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="72bb1-114">Elementbeziehungen</span><span class="sxs-lookup"><span data-stu-id="72bb1-114">Element Relationships</span></span>  
  
|<span data-ttu-id="72bb1-115">Beziehung</span><span class="sxs-lookup"><span data-stu-id="72bb1-115">Relationship</span></span>|<span data-ttu-id="72bb1-116">Elemente</span><span class="sxs-lookup"><span data-stu-id="72bb1-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="72bb1-117">**Übergeordnetes Element**</span><span class="sxs-lookup"><span data-stu-id="72bb1-117">**Parent element**</span></span>|[<span data-ttu-id="72bb1-118">Configuration-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="72bb1-118">Configuration Element &#40;DTA&#41;</span></span>](configuration-element-dta.md)|  
|<span data-ttu-id="72bb1-119">**Untergeordnete Elemente**</span><span class="sxs-lookup"><span data-stu-id="72bb1-119">**Child elements**</span></span>|[<span data-ttu-id="72bb1-120">Name-Element für Server &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="72bb1-120">Name Element for Server &#40;DTA&#41;</span></span>](name-element-for-server-dta.md)<br /><br /> [<span data-ttu-id="72bb1-121">Database-Element für Konfiguration &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="72bb1-121">Database Element for Configuration &#40;DTA&#41;</span></span>](database-element-for-configuration-dta.md)|  
  
## <a name="remarks"></a><span data-ttu-id="72bb1-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="72bb1-122">Remarks</span></span>  
 <span data-ttu-id="72bb1-123">Sie können nur ein- `Server` Element für das- `Configuration` Element angeben.</span><span class="sxs-lookup"><span data-stu-id="72bb1-123">You can specify only one `Server` element for the `Configuration` element.</span></span> <span data-ttu-id="72bb1-124">Dieses Element hat den Namen **ServerTypecomplexType** im [XML-Schema des Datenbankoptimierungsratgebers](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="72bb1-124">This element is of the **ServerTypecomplexType** name in the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span> <span data-ttu-id="72bb1-125">Dieses `Server`-Element ist nicht mit dem untergeordneten Element für das `DTAInput`-Element identisch.</span><span class="sxs-lookup"><span data-stu-id="72bb1-125">Do not confuse this `Server` element with the one that is the child of the `DTAInput` element.</span></span> <span data-ttu-id="72bb1-126">Weitere Informationen finden Sie unter [Server-Element &#40;DTA&#41;](server-element-dta.md).</span><span class="sxs-lookup"><span data-stu-id="72bb1-126">For more information, see [Server Element &#40;DTA&#41;](server-element-dta.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="72bb1-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="72bb1-127">Example</span></span>  
 <span data-ttu-id="72bb1-128">Ein Beispiel für die Syntax finden Sie unter [Beispiel für eine XML-Eingabedatei mit benutzerdefinierter Konfiguration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="72bb1-128">For a usage example, see the [XML Input File Sample with User-specified Configuration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72bb1-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="72bb1-129">See Also</span></span>  
 [<span data-ttu-id="72bb1-130">XML-Eingabedateireferenz &#40;Datenbankoptimierungsratgeber&#41;</span><span class="sxs-lookup"><span data-stu-id="72bb1-130">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
