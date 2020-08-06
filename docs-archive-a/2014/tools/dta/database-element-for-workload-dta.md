---
title: Database-Element für Arbeitsauslastung (DTA) | Microsoft-Dokumentation
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
ms.assetid: 112fca2a-37e5-4162-b2e7-b56eb8ab0c6f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2774bc7ed981c84c966a394c95347208cbc6d656
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695017"
---
# <a name="database-element-for-workload-dta"></a><span data-ttu-id="a8752-102">Database-Element zur Arbeitsauslastung (DTA)</span><span class="sxs-lookup"><span data-stu-id="a8752-102">Database Element for Workload (DTA)</span></span>
  <span data-ttu-id="a8752-103">Gibt die Datenbank an, in der sich die Ablaufverfolgungstabelle der Arbeitsauslastung befindet.</span><span class="sxs-lookup"><span data-stu-id="a8752-103">Specifies the database where the workload trace table is located.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8752-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a8752-104">Syntax</span></span>  
  
```  
  
<Workload>  
  <Database>  
   ...code removed here...  
  </Database>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="a8752-105">Elementmerkmale</span><span class="sxs-lookup"><span data-stu-id="a8752-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="a8752-106">Merkmal</span><span class="sxs-lookup"><span data-stu-id="a8752-106">Characteristic</span></span>|<span data-ttu-id="a8752-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a8752-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="a8752-108">**Datentyp und -länge**</span><span class="sxs-lookup"><span data-stu-id="a8752-108">**Data type and length**</span></span>|<span data-ttu-id="a8752-109">Keine.</span><span class="sxs-lookup"><span data-stu-id="a8752-109">None.</span></span>|  
|<span data-ttu-id="a8752-110">**Standardwert**</span><span class="sxs-lookup"><span data-stu-id="a8752-110">**Default value**</span></span>|<span data-ttu-id="a8752-111">Keine.</span><span class="sxs-lookup"><span data-stu-id="a8752-111">None.</span></span>|  
|<span data-ttu-id="a8752-112">**Vorkommen**</span><span class="sxs-lookup"><span data-stu-id="a8752-112">**Occurrence**</span></span>|<span data-ttu-id="a8752-113">Einmalig erforderlich, wenn kein anderer Arbeitsauslastungstyp angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="a8752-113">Required once if no other type of workload is specified.</span></span> <span data-ttu-id="a8752-114">Sie müssen ein untergeordnetes `EventString`-, `File`- oder `Database`-Element für das übergeordnete `Workload`-Element angeben. Es kann jedoch nur ein Typ verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a8752-114">You must specify an `EventString`, a `File`, or a `Database` child element for the `Workload` parent, but only one type can be used.</span></span> <span data-ttu-id="a8752-115">Wenn Sie beispielsweise eine Arbeitsauslastung mit dem- `Database` Element angeben, können Sie auch keine Arbeitsauslastung mit dem- `File` Element in derselben XML-Eingabedatei angeben.</span><span class="sxs-lookup"><span data-stu-id="a8752-115">For example, if you specify a workload with the `Database` element, you cannot also specify a workload with the `File` element in the same XML input file.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="a8752-116">Elementbeziehungen</span><span class="sxs-lookup"><span data-stu-id="a8752-116">Element Relationships</span></span>  
  
|<span data-ttu-id="a8752-117">Beziehung</span><span class="sxs-lookup"><span data-stu-id="a8752-117">Relationship</span></span>|<span data-ttu-id="a8752-118">Elemente</span><span class="sxs-lookup"><span data-stu-id="a8752-118">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="a8752-119">**Übergeordnetes Element**</span><span class="sxs-lookup"><span data-stu-id="a8752-119">**Parent element**</span></span>|[<span data-ttu-id="a8752-120">Workload-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="a8752-120">Workload Element &#40;DTA&#41;</span></span>](workload-element-dta.md)|  
|<span data-ttu-id="a8752-121">**Untergeordnete Elemente**</span><span class="sxs-lookup"><span data-stu-id="a8752-121">**Child elements**</span></span>|[<span data-ttu-id="a8752-122">Name-Element für Datenbank &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="a8752-122">Name Element for Database &#40;DTA&#41;</span></span>](name-element-for-database-dta.md)<br /><br /> [<span data-ttu-id="a8752-123">Schema-Element für Datenbank &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="a8752-123">Schema Element for Database &#40;DTA&#41;</span></span>](schema-element-for-database-dta.md)|  
  
## <a name="remarks"></a><span data-ttu-id="a8752-124">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="a8752-124">Remarks</span></span>  
 <span data-ttu-id="a8752-125">Dieses Element hat den Namen **DatabaseDetailsTypecomplexType** im XML-Schema des Datenbankoptimierungsratgebers.</span><span class="sxs-lookup"><span data-stu-id="a8752-125">This element is of the **DatabaseDetailsTypecomplexType** name in the Database Engine Tuning Advisor XML schema.</span></span> <span data-ttu-id="a8752-126">Dieses `Database`-Element ist nicht mit dem identisch, dessen übergeordnetes Stammelement das `Configuration`-Element ist.</span><span class="sxs-lookup"><span data-stu-id="a8752-126">Do not confuse this `Database` element with the one whose root parent is the `Configuration` element.</span></span> <span data-ttu-id="a8752-127">(Weitere Informationen finden Sie unter [Database-Element für Konfiguration &#40;DTA&#41;](database-element-for-configuration-dta.md).)</span><span class="sxs-lookup"><span data-stu-id="a8752-127">(See [Database Element for Configuration &#40;DTA&#41;](database-element-for-configuration-dta.md).)</span></span>  
  
## <a name="example"></a><span data-ttu-id="a8752-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a8752-128">Example</span></span>  
 <span data-ttu-id="a8752-129">Ein Verwendungs Beispiel für dieses `Database` Element finden Sie im Codebeispiel unter Arbeits Auslastungs [Element &#40;DTA&#41;](workload-element-dta.md).</span><span class="sxs-lookup"><span data-stu-id="a8752-129">For a usage example of this `Database` element, see the code example in [Workload Element &#40;DTA&#41;](workload-element-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8752-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a8752-130">See Also</span></span>  
 [<span data-ttu-id="a8752-131">XML-Eingabedateireferenz &#40;Datenbankoptimierungsratgeber&#41;</span><span class="sxs-lookup"><span data-stu-id="a8752-131">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
