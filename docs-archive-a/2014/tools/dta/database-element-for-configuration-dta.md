---
title: Database-Element für Konfiguration (DTA) | Microsoft-Dokumentation
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
ms.assetid: e91ba243-6cc9-457a-8f5a-134f3c71ae69
author: stevestein
ms.author: sstein
ms.openlocfilehash: 69ce1a0ac9912907f6d22916dd6243621e0778db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695014"
---
# <a name="database-element-for-configuration-dta"></a><span data-ttu-id="709d0-102">Database-Element für Konfiguration (DTA)</span><span class="sxs-lookup"><span data-stu-id="709d0-102">Database Element for Configuration (DTA)</span></span>
  <span data-ttu-id="709d0-103">Gibt die Datenbank an, für die der Datenbankoptimierungsratgeber die hypothetische Konfiguration auswerten soll (wird durch das `Configuration`-Element angegeben).</span><span class="sxs-lookup"><span data-stu-id="709d0-103">Specifies the database against which you want the Database Engine Tuning Advisor to evaluate the hypothetical configuration (specified by the `Configuration` element).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="709d0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="709d0-104">Syntax</span></span>  
  
```  
  
<Server>  
...code removed here...  
    <Database>...</Database>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="709d0-105">Elementmerkmale</span><span class="sxs-lookup"><span data-stu-id="709d0-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="709d0-106">Merkmal</span><span class="sxs-lookup"><span data-stu-id="709d0-106">Characteristic</span></span>|<span data-ttu-id="709d0-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="709d0-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="709d0-108">**Datentyp und -länge**</span><span class="sxs-lookup"><span data-stu-id="709d0-108">**Data type and length**</span></span>|<span data-ttu-id="709d0-109">Keine.</span><span class="sxs-lookup"><span data-stu-id="709d0-109">None.</span></span>|  
|<span data-ttu-id="709d0-110">**Standardwert**</span><span class="sxs-lookup"><span data-stu-id="709d0-110">**Default value**</span></span>|<span data-ttu-id="709d0-111">Keine.</span><span class="sxs-lookup"><span data-stu-id="709d0-111">None.</span></span>|  
|<span data-ttu-id="709d0-112">**Vorkommen**</span><span class="sxs-lookup"><span data-stu-id="709d0-112">**Occurrence**</span></span>|<span data-ttu-id="709d0-113">Einmal oder mehrfach pro `Server`-Element erforderlich.</span><span class="sxs-lookup"><span data-stu-id="709d0-113">Required one or more times per `Server` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="709d0-114">Elementbeziehungen</span><span class="sxs-lookup"><span data-stu-id="709d0-114">Element Relationships</span></span>  
  
|<span data-ttu-id="709d0-115">Beziehung</span><span class="sxs-lookup"><span data-stu-id="709d0-115">Relationship</span></span>|<span data-ttu-id="709d0-116">Elemente</span><span class="sxs-lookup"><span data-stu-id="709d0-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="709d0-117">**Übergeordnetes Element**</span><span class="sxs-lookup"><span data-stu-id="709d0-117">**Parent element**</span></span>|[<span data-ttu-id="709d0-118">Server-Element für Konfiguration &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="709d0-118">Server Element for Configuration &#40;DTA&#41;</span></span>](server-element-for-configuration-dta.md)|  
|<span data-ttu-id="709d0-119">**Untergeordnete Elemente**</span><span class="sxs-lookup"><span data-stu-id="709d0-119">**Child elements**</span></span>|[<span data-ttu-id="709d0-120">Name-Element für Datenbank &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="709d0-120">Name Element for Database &#40;DTA&#41;</span></span>](name-element-for-database-dta.md)<br /><br /> [<span data-ttu-id="709d0-121">Schema-Element für Datenbank &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="709d0-121">Schema Element for Database &#40;DTA&#41;</span></span>](schema-element-for-database-dta.md)<br /><br /> [<span data-ttu-id="709d0-122">Recommendation-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="709d0-122">Recommendation Element &#40;DTA&#41;</span></span>](recommendation-element-dta.md)|  
  
## <a name="remarks"></a><span data-ttu-id="709d0-123">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="709d0-123">Remarks</span></span>  
 <span data-ttu-id="709d0-124">Dieses Element hat den Namen **DatabaseTypecomplexType** im XML-Schema des Datenbankoptimierungsratgebers.</span><span class="sxs-lookup"><span data-stu-id="709d0-124">This element is of the **DatabaseTypecomplexType** name in the Database Engine Tuning Advisor XML schema.</span></span> <span data-ttu-id="709d0-125">Dieses `Database`-Element ist nicht mit dem Element identisch, dessen übergeordnetes Stammelement das `Server`-Element ist. Dieses Element wird oben in der XML-Eingabedatei angezeigt.</span><span class="sxs-lookup"><span data-stu-id="709d0-125">Do not confuse this `Database` element with the one whose root parent is the `Server` element, which occurs at the top of the XML input file.</span></span> <span data-ttu-id="709d0-126">Weitere Informationen finden Sie unter [Database-Element für Server &#40;DTA&#41;](database-element-for-server-dta.md).</span><span class="sxs-lookup"><span data-stu-id="709d0-126">For more information, see [Database Element for Server &#40;DTA&#41;](database-element-for-server-dta.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="709d0-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="709d0-127">Example</span></span>  
 <span data-ttu-id="709d0-128">Ein Beispiel für die Verwendung dieses `Database` Elements finden Sie unter Beispiel für eine [XML-Eingabedatei mit benutzerdefinierten Konfigurations &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="709d0-128">For a usage example of this `Database` element, see the [XML Input File Sample with User-specified Configuration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="709d0-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="709d0-129">See Also</span></span>  
 [<span data-ttu-id="709d0-130">XML-Eingabedateireferenz &#40;Datenbankoptimierungsratgeber&#41;</span><span class="sxs-lookup"><span data-stu-id="709d0-130">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
