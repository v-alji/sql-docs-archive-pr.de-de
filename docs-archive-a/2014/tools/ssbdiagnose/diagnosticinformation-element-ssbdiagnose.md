---
title: DiagnosticInformation-Element (ssbdiagnose) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- XML output file format [ssbdiagnose], diagnosticinformation element
- diagnosticinformation element
- ssbdiagnose
ms.assetid: 0cfda544-542c-4cf4-86d2-8031c91b10f6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 92d76a065c24ddc1fc8d85989ed3202308571951
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615253"
---
# <a name="diagnosticinformation-element-ssbdiagnose"></a><span data-ttu-id="7ced3-102">DiagnosticInformation-Element (ssbdiagnose)</span><span class="sxs-lookup"><span data-stu-id="7ced3-102">DiagnosticInformation Element (ssbdiagnose)</span></span>
  <span data-ttu-id="7ced3-103">Das **DiagnosticInformation** -Element enthält alle Elemente, die die vom Hilfsprogramm gefundenen Diagnoseinformationen melden.</span><span class="sxs-lookup"><span data-stu-id="7ced3-103">The **DiagnosticInformation** element contains all elements that report the diagnostic information found by the utility.</span></span> <span data-ttu-id="7ced3-104">**DiagnosticInformation** ist das Stammelement einer XML-Ausgabedatei von **ssbdiagnostic** .</span><span class="sxs-lookup"><span data-stu-id="7ced3-104">**DiagnosticInformation** is the root element of a **ssbdiagnostic** XML output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ced3-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="7ced3-105">Syntax</span></span>  
  
```  
  
<DiagnosticInformation>   
    ...   
</DiagnosticInformation>  
```  
  
## <a name="element-attributes"></a><span data-ttu-id="7ced3-106">Elementattribute</span><span class="sxs-lookup"><span data-stu-id="7ced3-106">Element Attributes</span></span>  
  
|<span data-ttu-id="7ced3-107">attribute</span><span class="sxs-lookup"><span data-stu-id="7ced3-107">Attribute</span></span>|<span data-ttu-id="7ced3-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7ced3-108">Description</span></span>|  
|---------------|-----------------|  
|`None`|<span data-ttu-id="7ced3-109">–</span><span class="sxs-lookup"><span data-stu-id="7ced3-109">N/A</span></span>|  
  
## <a name="element-characteristics"></a><span data-ttu-id="7ced3-110">Elementmerkmale</span><span class="sxs-lookup"><span data-stu-id="7ced3-110">Element Characteristics</span></span>  
  
|<span data-ttu-id="7ced3-111">Merkmal</span><span class="sxs-lookup"><span data-stu-id="7ced3-111">Characteristic</span></span>|<span data-ttu-id="7ced3-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7ced3-112">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="7ced3-113">**Datentyp und -länge**</span><span class="sxs-lookup"><span data-stu-id="7ced3-113">**Data type and length**</span></span>|<span data-ttu-id="7ced3-114">Keine.</span><span class="sxs-lookup"><span data-stu-id="7ced3-114">None.</span></span>|  
|<span data-ttu-id="7ced3-115">**Standardwert**</span><span class="sxs-lookup"><span data-stu-id="7ced3-115">**Default value**</span></span>|<span data-ttu-id="7ced3-116">Keine.</span><span class="sxs-lookup"><span data-stu-id="7ced3-116">None.</span></span>|  
|<span data-ttu-id="7ced3-117">**Vorkommen**</span><span class="sxs-lookup"><span data-stu-id="7ced3-117">**Occurrence**</span></span>|<span data-ttu-id="7ced3-118">Einmal pro **ssbdiagnose** -XML-Ausgabedatei</span><span class="sxs-lookup"><span data-stu-id="7ced3-118">Once per **ssbdiagnose** XML output file.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="7ced3-119">Elementbeziehungen</span><span class="sxs-lookup"><span data-stu-id="7ced3-119">Element Relationships</span></span>  
  
|<span data-ttu-id="7ced3-120">Beziehung</span><span class="sxs-lookup"><span data-stu-id="7ced3-120">Relationship</span></span>|<span data-ttu-id="7ced3-121">Elemente</span><span class="sxs-lookup"><span data-stu-id="7ced3-121">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="7ced3-122">**Übergeordnetes Element**</span><span class="sxs-lookup"><span data-stu-id="7ced3-122">**Parent element**</span></span>|<span data-ttu-id="7ced3-123">Keine.</span><span class="sxs-lookup"><span data-stu-id="7ced3-123">None.</span></span>|  
|<span data-ttu-id="7ced3-124">**Untergeordnete Elemente**</span><span class="sxs-lookup"><span data-stu-id="7ced3-124">**Child elements**</span></span>|[<span data-ttu-id="7ced3-125">Banner-Element &#40;ssbdiagnose&#41;</span><span class="sxs-lookup"><span data-stu-id="7ced3-125">Banner Element &#40;ssbdiagnose&#41;</span></span>](banner-element-ssbdiagnose.md)<br /><br /> [<span data-ttu-id="7ced3-126">Issue-Element &#40;ssbdiagnose&#41;</span><span class="sxs-lookup"><span data-stu-id="7ced3-126">Issue Element &#40;ssbdiagnose&#41;</span></span>](issue-element-ssbdiagnose.md)|  
  
## <a name="remarks"></a><span data-ttu-id="7ced3-127">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="7ced3-127">Remarks</span></span>  
 <span data-ttu-id="7ced3-128">Weitere Informationen zu XML-Namespaces finden Sie unter [Namespaces in an XML Document](https://go.microsoft.com/fwlink/?LinkId=7341) (in Englisch) in der [!INCLUDE[msCoName](../../includes/msconame-md.md)] MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="7ced3-128">For more information about XML namespaces, see [Namespaces in an XML Document](https://go.microsoft.com/fwlink/?LinkId=7341) in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] MSDN Library.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ced3-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7ced3-129">See Also</span></span>  
 [<span data-ttu-id="7ced3-130">ssbdiagnose-Hilfsprogramm &#40;Service Broker&#41;</span><span class="sxs-lookup"><span data-stu-id="7ced3-130">ssbdiagnose Utility &#40;Service Broker&#41;</span></span>](ssbdiagnose-utility-service-broker.md)  
  
  
