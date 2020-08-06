---
title: Banner-Element (ssbdiagnose) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- banner element
- XML output file format [ssbdiagnose], banner element
- ssbdiagnose
ms.assetid: cc6cd49a-acf0-4cfb-8c6a-554692b89de2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 13238ac4ef1745dea4fbf3392484ac6137c09df1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726405"
---
# <a name="banner-element-ssbdiagnose"></a><span data-ttu-id="770f0-102">Banner-Element (ssbdiagnose)</span><span class="sxs-lookup"><span data-stu-id="770f0-102">Banner Element (ssbdiagnose)</span></span>
  <span data-ttu-id="770f0-103">Identifiziert das Hilfsprogramm, das die XML-Ausgabedatei von **ssbdiagnose** generiert hat.</span><span class="sxs-lookup"><span data-stu-id="770f0-103">Identifies which utility generated the **ssbdiagnose** output XML file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="770f0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="770f0-104">Syntax</span></span>  
  
```  
  
<Banner  
    title="..."   
    product="..."   
    version="..." />  
```  
  
## <a name="element-attributes"></a><span data-ttu-id="770f0-105">Elementattribute</span><span class="sxs-lookup"><span data-stu-id="770f0-105">Element Attributes</span></span>  
  
|<span data-ttu-id="770f0-106">attribute</span><span class="sxs-lookup"><span data-stu-id="770f0-106">Attribute</span></span>|<span data-ttu-id="770f0-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="770f0-107">Description</span></span>|  
|---------------|-----------------|  
|`title`|<span data-ttu-id="770f0-108">Identifiziert das Hilfsprogramm, das die XML-Ausgabedatei von **ssbdiagnose** generiert hat.</span><span class="sxs-lookup"><span data-stu-id="770f0-108">Identifies the utility that generated the **ssbdiagnose** XML output file.</span></span>|  
|`product`|<span data-ttu-id="770f0-109">Identifiziert das Produkt, das die XML-Ausgabedatei von **ssbdiagnose** generiert hat.</span><span class="sxs-lookup"><span data-stu-id="770f0-109">Identifies the product that generated the **ssbdiagnose** XML output file.</span></span>|  
|`version`|<span data-ttu-id="770f0-110">Identifiziert die Version des Hilfsprogramms, das die XML-Ausgabedatei generiert hat.</span><span class="sxs-lookup"><span data-stu-id="770f0-110">Identifies which version of the utility generated the XML output file.</span></span>|  
  
## <a name="element-characteristics"></a><span data-ttu-id="770f0-111">Elementmerkmale</span><span class="sxs-lookup"><span data-stu-id="770f0-111">Element Characteristics</span></span>  
  
|<span data-ttu-id="770f0-112">Merkmal</span><span class="sxs-lookup"><span data-stu-id="770f0-112">Characteristic</span></span>|<span data-ttu-id="770f0-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="770f0-113">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="770f0-114">**Datentyp und -länge**</span><span class="sxs-lookup"><span data-stu-id="770f0-114">**Data type and length**</span></span>|<span data-ttu-id="770f0-115">Keine.</span><span class="sxs-lookup"><span data-stu-id="770f0-115">None.</span></span>|  
|<span data-ttu-id="770f0-116">**Standardwert**</span><span class="sxs-lookup"><span data-stu-id="770f0-116">**Default value**</span></span>|<span data-ttu-id="770f0-117">Keine.</span><span class="sxs-lookup"><span data-stu-id="770f0-117">None.</span></span>|  
|<span data-ttu-id="770f0-118">**Vorkommen**</span><span class="sxs-lookup"><span data-stu-id="770f0-118">**Occurrence**</span></span>|<span data-ttu-id="770f0-119">Einmal pro XML-Ausgabedatei von **ssbdiagnose**</span><span class="sxs-lookup"><span data-stu-id="770f0-119">Occurs once per **ssbdiagnose** output XML file.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="770f0-120">Elementbeziehungen</span><span class="sxs-lookup"><span data-stu-id="770f0-120">Element Relationships</span></span>  
  
|<span data-ttu-id="770f0-121">Beziehung</span><span class="sxs-lookup"><span data-stu-id="770f0-121">Relationship</span></span>|<span data-ttu-id="770f0-122">Elemente</span><span class="sxs-lookup"><span data-stu-id="770f0-122">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="770f0-123">**Übergeordnetes Element**</span><span class="sxs-lookup"><span data-stu-id="770f0-123">**Parent element**</span></span>|[<span data-ttu-id="770f0-124">DiagnosticInformation-Element &#40;ssbdiagnose&#41;</span><span class="sxs-lookup"><span data-stu-id="770f0-124">DiagnosticInformation Element &#40;ssbdiagnose&#41;</span></span>](diagnosticinformation-element-ssbdiagnose.md)|  
|<span data-ttu-id="770f0-125">**Untergeordnete Elemente**</span><span class="sxs-lookup"><span data-stu-id="770f0-125">**Child elements**</span></span>|<span data-ttu-id="770f0-126">Keine.</span><span class="sxs-lookup"><span data-stu-id="770f0-126">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="770f0-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="770f0-127">Example</span></span>  
 <span data-ttu-id="770f0-128">Das folgende Beispiel zeigt ein Banner-Element.</span><span class="sxs-lookup"><span data-stu-id="770f0-128">This is an example of a banner element.</span></span>  
  
```  
<Banner title="Service Broker Diagnostics Utility" product="Microsoft SQL Server" version="10.0.1073.0" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="770f0-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="770f0-129">See Also</span></span>  
 [<span data-ttu-id="770f0-130">ssbdiagnose-Hilfsprogramm &#40;Service Broker&#41;</span><span class="sxs-lookup"><span data-stu-id="770f0-130">ssbdiagnose Utility &#40;Service Broker&#41;</span></span>](ssbdiagnose-utility-service-broker.md)  
  
  
