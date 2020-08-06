---
title: Databaseto Connect-Element (DTA) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- DatabaseToConnect element
ms.assetid: 65153a66-3aee-4429-99b7-0816ac23c285
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4c21b36319e4007264677d499b84964c7cb5ea7a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695009"
---
# <a name="databasetoconnect-element-dta"></a><span data-ttu-id="d081b-102">DatabaseToConnect-Element (DTA)</span><span class="sxs-lookup"><span data-stu-id="d081b-102">DatabaseToConnect Element (DTA)</span></span>
  <span data-ttu-id="d081b-103">Gibt die erste Datenbank an, mit der der Datenbankoptimierungsratgeber beim Optimieren einer Arbeitsauslastung eine Verbindung herstellt.</span><span class="sxs-lookup"><span data-stu-id="d081b-103">Specifies the first database to which Database Engine Tuning Advisor connects when tuning a workload.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d081b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d081b-104">Syntax</span></span>  
  
```  
  
    <TuningOptions>  
...code removed here...  
      <DatabaseToConnect>...</DatabaseToConnect>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="d081b-105">Elementmerkmale</span><span class="sxs-lookup"><span data-stu-id="d081b-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="d081b-106">Merkmal</span><span class="sxs-lookup"><span data-stu-id="d081b-106">Characteristic</span></span>|<span data-ttu-id="d081b-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d081b-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="d081b-108">**Datentyp und -länge**</span><span class="sxs-lookup"><span data-stu-id="d081b-108">**Data type and length**</span></span>|<span data-ttu-id="d081b-109">`string`, unbegrenzte Länge.</span><span class="sxs-lookup"><span data-stu-id="d081b-109">`string`, unlimited length.</span></span>|  
|<span data-ttu-id="d081b-110">**Standardwert**</span><span class="sxs-lookup"><span data-stu-id="d081b-110">**Default value**</span></span>|<span data-ttu-id="d081b-111">Keine.</span><span class="sxs-lookup"><span data-stu-id="d081b-111">None.</span></span>|  
|<span data-ttu-id="d081b-112">**Vorkommen**</span><span class="sxs-lookup"><span data-stu-id="d081b-112">**Occurrence**</span></span>|<span data-ttu-id="d081b-113">Optional.</span><span class="sxs-lookup"><span data-stu-id="d081b-113">Optional.</span></span> <span data-ttu-id="d081b-114">Einmalige Verwendung pro `TuningOptions`-Element möglich.</span><span class="sxs-lookup"><span data-stu-id="d081b-114">Can use once for each `TuningOptions` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="d081b-115">Elementbeziehungen</span><span class="sxs-lookup"><span data-stu-id="d081b-115">Element Relationships</span></span>  
  
|<span data-ttu-id="d081b-116">Beziehung</span><span class="sxs-lookup"><span data-stu-id="d081b-116">Relationship</span></span>|<span data-ttu-id="d081b-117">Elemente</span><span class="sxs-lookup"><span data-stu-id="d081b-117">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="d081b-118">**Übergeordnetes Element**</span><span class="sxs-lookup"><span data-stu-id="d081b-118">**Parent element**</span></span>|[<span data-ttu-id="d081b-119">TuningOptions-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="d081b-119">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)|  
|<span data-ttu-id="d081b-120">**Untergeordnete Elemente**</span><span class="sxs-lookup"><span data-stu-id="d081b-120">**Child elements**</span></span>|<span data-ttu-id="d081b-121">Keine</span><span class="sxs-lookup"><span data-stu-id="d081b-121">None</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d081b-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="d081b-122">Remarks</span></span>  
 <span data-ttu-id="d081b-123">Mit `DatabaseToConnect` können Sie den Namen der ersten Datenbank angeben, mit der der Datenbankoptimierungsratgeber beim Starten der Optimierungssitzung eine Verbindung herstellen soll.</span><span class="sxs-lookup"><span data-stu-id="d081b-123">Use `DatabaseToConnect` to specify the name of the first database to which you want Database Engine Tuning Advisor to connect when it starts the tuning session.</span></span> <span data-ttu-id="d081b-124">Sie können mithilfe dieses Elements nur eine Datenbank angeben.</span><span class="sxs-lookup"><span data-stu-id="d081b-124">You can specify only one database with this element.</span></span> <span data-ttu-id="d081b-125">Wenn mehrere Datenbanknamen angegeben werden, gibt der Datenbankoptimierungsratgeber einen Fehler zurück.</span><span class="sxs-lookup"><span data-stu-id="d081b-125">If multiple database names are specified, Database Engine Tuning Advisor returns an error.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d081b-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d081b-126">Example</span></span>  
 <span data-ttu-id="d081b-127">Ein Beispiel für die Verwendung finden Sie unter [Beispiel für eine XML-Eingabedatei mit Inlinearbeitsauslastung &#40;DTA&#41;](xml-input-file-sample-with-inline-workload-dta.md).</span><span class="sxs-lookup"><span data-stu-id="d081b-127">For a usage example, see the [XML Input File Sample with Inline Workload &#40;DTA&#41;](xml-input-file-sample-with-inline-workload-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d081b-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d081b-128">See Also</span></span>  
 [<span data-ttu-id="d081b-129">XML-Eingabedateireferenz &#40;Datenbankoptimierungsratgeber&#41;</span><span class="sxs-lookup"><span data-stu-id="d081b-129">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
