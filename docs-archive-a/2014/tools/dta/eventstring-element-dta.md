---
title: Event String-Element (DTA) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- EventString element
ms.assetid: f76c37b4-2f6e-4274-8ee2-87e89d98e8a2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 981cd0be06fd0972426fcb2fa67b0c4143cf9178
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722106"
---
# <a name="eventstring-element-dta"></a><span data-ttu-id="2f5f1-102">EventString-Element (DTA)</span><span class="sxs-lookup"><span data-stu-id="2f5f1-102">EventString Element (DTA)</span></span>
  <span data-ttu-id="2f5f1-103">Gibt eine auf einem [!INCLUDE[tsql](../../includes/tsql-md.md)] -Skript basierende Arbeitsauslastung direkt in der XML-Eingabedatei an.</span><span class="sxs-lookup"><span data-stu-id="2f5f1-103">Specifies a [!INCLUDE[tsql](../../includes/tsql-md.md)] script workload directly in the XML input file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f5f1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2f5f1-104">Syntax</span></span>  
  
```  
  
<Workload>  
    <EventString Weight="...">  
    ...code removed here...  
    </EventString>  
</Workload>  
```  
  
## <a name="element-attributes"></a><span data-ttu-id="2f5f1-105">Elementattribute</span><span class="sxs-lookup"><span data-stu-id="2f5f1-105">Element Attributes</span></span>  
  
|<span data-ttu-id="2f5f1-106">attribute</span><span class="sxs-lookup"><span data-stu-id="2f5f1-106">Attribute</span></span>|<span data-ttu-id="2f5f1-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2f5f1-107">Description</span></span>|  
|---------------|-----------------|  
|`Weight`|<span data-ttu-id="2f5f1-108">Optional.</span><span class="sxs-lookup"><span data-stu-id="2f5f1-108">Optional.</span></span> <span data-ttu-id="2f5f1-109">Gibt den Gewichtungsfaktor der Abfrage (ein Faktor für die Wichtigkeit) für das angegebene Ereignis an.</span><span class="sxs-lookup"><span data-stu-id="2f5f1-109">Specifies the query weight factor (a factor of importance) for the specified event.</span></span> <span data-ttu-id="2f5f1-110">Sie können die Gewichtung mit einem `float`-Datentyp angeben.</span><span class="sxs-lookup"><span data-stu-id="2f5f1-110">Use a `float` data type to specify the weight.</span></span> <span data-ttu-id="2f5f1-111">Beispiel: `Weight`="100,01".</span><span class="sxs-lookup"><span data-stu-id="2f5f1-111">For example, `Weight`="100.01".</span></span> <span data-ttu-id="2f5f1-112">Der Mindestwert für `Weight` ist "0".</span><span class="sxs-lookup"><span data-stu-id="2f5f1-112">The minimum value you can specify for `Weight` is "0".</span></span>|  
  
## <a name="element-characteristics"></a><span data-ttu-id="2f5f1-113">Elementmerkmale</span><span class="sxs-lookup"><span data-stu-id="2f5f1-113">Element Characteristics</span></span>  
  
|<span data-ttu-id="2f5f1-114">Merkmal</span><span class="sxs-lookup"><span data-stu-id="2f5f1-114">Characteristic</span></span>|<span data-ttu-id="2f5f1-115">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2f5f1-115">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="2f5f1-116">**Datentyp und -länge**</span><span class="sxs-lookup"><span data-stu-id="2f5f1-116">**Data type and length**</span></span>|<span data-ttu-id="2f5f1-117">`string`, die Länge ist unbegrenzt.</span><span class="sxs-lookup"><span data-stu-id="2f5f1-117">`string`, length is unlimited.</span></span>|  
|<span data-ttu-id="2f5f1-118">**Standardwert**</span><span class="sxs-lookup"><span data-stu-id="2f5f1-118">**Default value**</span></span>|<span data-ttu-id="2f5f1-119">Keine.</span><span class="sxs-lookup"><span data-stu-id="2f5f1-119">None.</span></span>|  
|<span data-ttu-id="2f5f1-120">**Vorkommen**</span><span class="sxs-lookup"><span data-stu-id="2f5f1-120">**Occurrence**</span></span>|<span data-ttu-id="2f5f1-121">Einmalig erforderlich, wenn kein anderer Arbeitsauslastungstyp angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="2f5f1-121">Required once if no other type of workload is specified.</span></span> <span data-ttu-id="2f5f1-122">Sie müssen ein untergeordnetes `EventString`-, `File`- oder `Database`-Element für das übergeordnete `Workload`-Element angeben. Es kann jedoch nur ein Typ verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2f5f1-122">You must specify an `EventString`, a `File`, or a `Database` child element for the `Workload` parent, but only one type can be used.</span></span> <span data-ttu-id="2f5f1-123">Wenn Sie beispielsweise eine Arbeitsauslastung mit dem `EventString`-Element angeben, können Sie in dieser XML-Eingabedatei keine Arbeitsauslastung mit dem `File`-Element angeben.</span><span class="sxs-lookup"><span data-stu-id="2f5f1-123">For example, if you specify a workload with the `EventString` element, then you cannot also specify a workload with the `File` element in the same XML input file.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="2f5f1-124">Elementbeziehungen</span><span class="sxs-lookup"><span data-stu-id="2f5f1-124">Element Relationships</span></span>  
  
|<span data-ttu-id="2f5f1-125">Beziehung</span><span class="sxs-lookup"><span data-stu-id="2f5f1-125">Relationship</span></span>|<span data-ttu-id="2f5f1-126">Elemente</span><span class="sxs-lookup"><span data-stu-id="2f5f1-126">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="2f5f1-127">**Übergeordnetes Element**</span><span class="sxs-lookup"><span data-stu-id="2f5f1-127">**Parent element**</span></span>|[<span data-ttu-id="2f5f1-128">Workload-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="2f5f1-128">Workload Element &#40;DTA&#41;</span></span>](workload-element-dta.md)|  
|<span data-ttu-id="2f5f1-129">**Untergeordnete Elemente**</span><span class="sxs-lookup"><span data-stu-id="2f5f1-129">**Child elements**</span></span>|<span data-ttu-id="2f5f1-130">Keine.</span><span class="sxs-lookup"><span data-stu-id="2f5f1-130">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2f5f1-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2f5f1-131">Example</span></span>  
 <span data-ttu-id="2f5f1-132">Ein Beispiel für die Verwendung dieses Elements finden Sie unter [Beispiel für eine XML-Eingabedatei mit Inlinearbeitsauslastung &#40;DTA&#41;](xml-input-file-sample-with-inline-workload-dta.md).</span><span class="sxs-lookup"><span data-stu-id="2f5f1-132">For a usage example of this element, see the [XML Input File Sample with Inline Workload &#40;DTA&#41;](xml-input-file-sample-with-inline-workload-dta.md) .</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f5f1-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2f5f1-133">See Also</span></span>  
 [<span data-ttu-id="2f5f1-134">XML-Eingabedateireferenz &#40;Datenbankoptimierungsratgeber&#41;</span><span class="sxs-lookup"><span data-stu-id="2f5f1-134">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
