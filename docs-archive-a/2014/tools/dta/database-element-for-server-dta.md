---
title: Database-Element für Server (DTA) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Database element
ms.assetid: 5cd9a87a-af4b-45f3-8c18-f7fd7e7d3064
author: stevestein
ms.author: sstein
ms.openlocfilehash: 9a48d255898eff6bd780f8edf2c8d2da7229b0ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695013"
---
# <a name="database-element-for-server-dta"></a><span data-ttu-id="3e679-102">Database-Element für Server (DTA)</span><span class="sxs-lookup"><span data-stu-id="3e679-102">Database Element for Server (DTA)</span></span>
  <span data-ttu-id="3e679-103">Gibt die Datenbank an, die Sie auf einem bestimmten Server optimieren möchten.</span><span class="sxs-lookup"><span data-stu-id="3e679-103">Specifies the database you want to tune on a specific server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e679-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3e679-104">Syntax</span></span>  
  
```  
  
<Server>  
...code removed here...  
    <Database>...</Database>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="3e679-105">Elementmerkmale</span><span class="sxs-lookup"><span data-stu-id="3e679-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="3e679-106">Merkmal</span><span class="sxs-lookup"><span data-stu-id="3e679-106">Characteristic</span></span>|<span data-ttu-id="3e679-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3e679-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="3e679-108">Datentyp und -länge</span><span class="sxs-lookup"><span data-stu-id="3e679-108">Data type and length</span></span>|<span data-ttu-id="3e679-109">Keine.</span><span class="sxs-lookup"><span data-stu-id="3e679-109">None.</span></span>|  
|<span data-ttu-id="3e679-110">Standardwert</span><span class="sxs-lookup"><span data-stu-id="3e679-110">Default value</span></span>|<span data-ttu-id="3e679-111">Keine.</span><span class="sxs-lookup"><span data-stu-id="3e679-111">None.</span></span>|  
|<span data-ttu-id="3e679-112">Vorkommen</span><span class="sxs-lookup"><span data-stu-id="3e679-112">Occurrence</span></span>|<span data-ttu-id="3e679-113">Einmal oder mehrfach pro `Server`-Element erforderlich.</span><span class="sxs-lookup"><span data-stu-id="3e679-113">Required one or more times per `Server` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="3e679-114">Elementbeziehungen</span><span class="sxs-lookup"><span data-stu-id="3e679-114">Element Relationships</span></span>  
  
|<span data-ttu-id="3e679-115">Beziehung</span><span class="sxs-lookup"><span data-stu-id="3e679-115">Relationship</span></span>|<span data-ttu-id="3e679-116">Elemente</span><span class="sxs-lookup"><span data-stu-id="3e679-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="3e679-117">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="3e679-117">Parent element</span></span>|[<span data-ttu-id="3e679-118">Server-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="3e679-118">Server Element &#40;DTA&#41;</span></span>](server-element-dta.md)|  
|<span data-ttu-id="3e679-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3e679-119">Child elements</span></span>|[<span data-ttu-id="3e679-120">Name-Element für Datenbank &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="3e679-120">Name Element for Database &#40;DTA&#41;</span></span>](name-element-for-database-dta.md)<br /><br /> [<span data-ttu-id="3e679-121">Schema-Element für Datenbank &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="3e679-121">Schema Element for Database &#40;DTA&#41;</span></span>](schema-element-for-database-dta.md)|  
  
## <a name="remarks"></a><span data-ttu-id="3e679-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="3e679-122">Remarks</span></span>  
 <span data-ttu-id="3e679-123">Dieses Element hat den Namen **DatabaseDetailsTypecomplexType** im XML-Schema des Datenbankoptimierungsratgebers.</span><span class="sxs-lookup"><span data-stu-id="3e679-123">This element is of the **DatabaseDetailsTypecomplexType** name in the Database Engine Tuning Advisor XML schema.</span></span> <span data-ttu-id="3e679-124">Dieses `Database`-Element ist nicht mit dem identisch, dessen übergeordnetes Stammelement das `Configuration`-Element ist.</span><span class="sxs-lookup"><span data-stu-id="3e679-124">Do not confuse this `Database` element with the one whose root parent is the `Configuration` element.</span></span> <span data-ttu-id="3e679-125">Weitere Informationen finden Sie unter [Database-Element für Konfiguration &#40;DTA&#41;](database-element-for-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="3e679-125">For more information, see [Database Element for Configuration &#40;DTA&#41;](database-element-for-configuration-dta.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3e679-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3e679-126">Example</span></span>  
 <span data-ttu-id="3e679-127">Ein Verwendungs Beispiel für das- `Database` Element finden Sie unter [Server-Element &#40;DTA&#41;](server-element-dta.md).</span><span class="sxs-lookup"><span data-stu-id="3e679-127">For a usage example of the `Database` element, see [Server Element &#40;DTA&#41;](server-element-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e679-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3e679-128">See Also</span></span>  
 [<span data-ttu-id="3e679-129">XML-Eingabedateireferenz &#40;Datenbankoptimierungsratgeber&#41;</span><span class="sxs-lookup"><span data-stu-id="3e679-129">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
