---
title: Server-Element (DTA) | Microsoft-Dokumentation
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
ms.assetid: 9fe0bfb4-3aa6-4eb2-a83e-c0d0e7d4e9f6
author: stevestein
ms.author: sstein
ms.openlocfilehash: ab67e0303c2b629c3774886441474f5ef5b10a43
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620093"
---
# <a name="server-element-dta"></a><span data-ttu-id="8d906-102">Server-Element (DTA)</span><span class="sxs-lookup"><span data-stu-id="8d906-102">Server Element (DTA)</span></span>
  <span data-ttu-id="8d906-103">Enthält die Identifikationsinformationen für den Server, auf dem sich die zu optimierenden Datenbanken befinden.</span><span class="sxs-lookup"><span data-stu-id="8d906-103">Contains the identifying information for the server on which the databases reside that you want to tune.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d906-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8d906-104">Syntax</span></span>  
  
```  
  
<DTAInput>  
    <Server>  
    ...code removed here...  
    </Server>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="8d906-105">Elementmerkmale</span><span class="sxs-lookup"><span data-stu-id="8d906-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="8d906-106">Merkmal</span><span class="sxs-lookup"><span data-stu-id="8d906-106">Characteristic</span></span>|<span data-ttu-id="8d906-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="8d906-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="8d906-108">**Datentyp und -länge**</span><span class="sxs-lookup"><span data-stu-id="8d906-108">**Data type and length**</span></span>|<span data-ttu-id="8d906-109">Keine.</span><span class="sxs-lookup"><span data-stu-id="8d906-109">None.</span></span>|  
|<span data-ttu-id="8d906-110">**Standardwert**</span><span class="sxs-lookup"><span data-stu-id="8d906-110">**Default value**</span></span>|<span data-ttu-id="8d906-111">Keine.</span><span class="sxs-lookup"><span data-stu-id="8d906-111">None.</span></span>|  
|<span data-ttu-id="8d906-112">**Vorkommen**</span><span class="sxs-lookup"><span data-stu-id="8d906-112">**Occurrence**</span></span>|<span data-ttu-id="8d906-113">Einmal pro `DTAInput`-Element erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8d906-113">Required once per `DTAInput` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="8d906-114">Elementbeziehungen</span><span class="sxs-lookup"><span data-stu-id="8d906-114">Element Relationships</span></span>  
  
|<span data-ttu-id="8d906-115">Beziehung</span><span class="sxs-lookup"><span data-stu-id="8d906-115">Relationship</span></span>|<span data-ttu-id="8d906-116">Elemente</span><span class="sxs-lookup"><span data-stu-id="8d906-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="8d906-117">**Übergeordnetes Element**</span><span class="sxs-lookup"><span data-stu-id="8d906-117">**Parent element**</span></span>|[<span data-ttu-id="8d906-118">DTAInput-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="8d906-118">DTAInput Element &#40;DTA&#41;</span></span>](dtainput-element-dta.md)|  
|<span data-ttu-id="8d906-119">**Untergeordnete Elemente**</span><span class="sxs-lookup"><span data-stu-id="8d906-119">**Child elements**</span></span>|[<span data-ttu-id="8d906-120">Name-Element für Server &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="8d906-120">Name Element for Server &#40;DTA&#41;</span></span>](name-element-for-server-dta.md)<br /><br /> [<span data-ttu-id="8d906-121">Database-Element für Server &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="8d906-121">Database Element for Server &#40;DTA&#41;</span></span>](database-element-for-server-dta.md)|  
  
## <a name="remarks"></a><span data-ttu-id="8d906-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="8d906-122">Remarks</span></span>  
 <span data-ttu-id="8d906-123">Sie können nur ein- `Server` Element für das- `DTAInput` Element angeben.</span><span class="sxs-lookup"><span data-stu-id="8d906-123">You can specify only one `Server` element for the `DTAInput` element.</span></span> <span data-ttu-id="8d906-124">Dieses Element hat im DTA-XML-Schema den Namen **ServerDetailsTypecomplexType** .</span><span class="sxs-lookup"><span data-stu-id="8d906-124">This element is of the **ServerDetailsTypecomplexType** name in the DTA XML schema.</span></span> <span data-ttu-id="8d906-125">Dieses `Server`-Element ist nicht mit dem untergeordneten Element für das `Configuration`-Element identisch.</span><span class="sxs-lookup"><span data-stu-id="8d906-125">Do not confuse this `Server` element with the one that is the child of the `Configuration` element.</span></span> <span data-ttu-id="8d906-126">Weitere Informationen finden Sie unter [Server-Element für Konfiguration &#40;DTA&#41;](server-element-for-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="8d906-126">For more information, see [Server Element for Configuration &#40;DTA&#41;](server-element-for-configuration-dta.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8d906-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8d906-127">Example</span></span>  
 <span data-ttu-id="8d906-128">Im folgenden Beispiel wird veranschaulicht, wie die **Sales.SalesPerson** -Tabelle in der **AdventureWorks** -Datenbank auf SERVER001 angegeben wird:</span><span class="sxs-lookup"><span data-stu-id="8d906-128">The following example shows how to specify the **Sales.SalesPerson** table in the **AdventureWorks** database on SERVER001:</span></span>  
  
```xml  
<Server>  
  <Name>SERVER001</Name>  
  <Database>  
    <Name>AdventureWorks</Name>  
    <Schema>  
      <Name>Sales</Name>  
      <Table>  
        <Name>SalesPerson</Name>  
      </Table>  
    </Schema>  
  </Database>  
</Server  
```  
  
## <a name="see-also"></a><span data-ttu-id="8d906-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8d906-129">See Also</span></span>  
 [<span data-ttu-id="8d906-130">XML-Eingabedateireferenz &#40;Datenbankoptimierungsratgeber&#41;</span><span class="sxs-lookup"><span data-stu-id="8d906-130">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
