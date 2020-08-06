---
title: Table-Element für Schema (DTA) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Table element [DTA]
ms.assetid: a59e8319-05d1-47f3-af39-7d970ab8e7dc
author: stevestein
ms.author: sstein
ms.openlocfilehash: dd444b1da99b22e0259dc1f50818c1763b7052ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720653"
---
# <a name="table-element-for-schema-dta"></a><span data-ttu-id="b67e0-102">Table-Element für Schema (DTA)</span><span class="sxs-lookup"><span data-stu-id="b67e0-102">Table Element for Schema (DTA)</span></span>
  <span data-ttu-id="b67e0-103">Gibt die Tabelle zum Optimieren an.</span><span class="sxs-lookup"><span data-stu-id="b67e0-103">Specifies the table for tuning.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b67e0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b67e0-104">Syntax</span></span>  
  
```  
  
<Schema>  
...code removed here...  
    <Table>...</Table>  
```  
  
## <a name="element-attributes"></a><span data-ttu-id="b67e0-105">Elementattribute</span><span class="sxs-lookup"><span data-stu-id="b67e0-105">Element Attributes</span></span>  
  
|<span data-ttu-id="b67e0-106">attribute</span><span class="sxs-lookup"><span data-stu-id="b67e0-106">Attribute</span></span>|<span data-ttu-id="b67e0-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b67e0-107">Description</span></span>|  
|---------------|-----------------|  
|`NumberOfRows`|<span data-ttu-id="b67e0-108">Optional.</span><span class="sxs-lookup"><span data-stu-id="b67e0-108">Optional.</span></span> <span data-ttu-id="b67e0-109">Eine ganze Zahl, mit der Sie Tabellen unterschiedlicher Größe simulieren können.</span><span class="sxs-lookup"><span data-stu-id="b67e0-109">Integer that allows you to simulate tables of different sizes.</span></span>|  
  
## <a name="element-characteristics"></a><span data-ttu-id="b67e0-110">Elementmerkmale</span><span class="sxs-lookup"><span data-stu-id="b67e0-110">Element Characteristics</span></span>  
  
|<span data-ttu-id="b67e0-111">Merkmal</span><span class="sxs-lookup"><span data-stu-id="b67e0-111">Characteristic</span></span>|<span data-ttu-id="b67e0-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b67e0-112">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="b67e0-113">**Datentyp und -länge**</span><span class="sxs-lookup"><span data-stu-id="b67e0-113">**Data type and length**</span></span>|<span data-ttu-id="b67e0-114">**string**, 1 bis 255 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="b67e0-114">**string**, between 1 and 255 characters.</span></span>|  
|<span data-ttu-id="b67e0-115">**Standardwert**</span><span class="sxs-lookup"><span data-stu-id="b67e0-115">**Default value**</span></span>|<span data-ttu-id="b67e0-116">Keine.</span><span class="sxs-lookup"><span data-stu-id="b67e0-116">None.</span></span>|  
|<span data-ttu-id="b67e0-117">**Vorkommen**</span><span class="sxs-lookup"><span data-stu-id="b67e0-117">**Occurrence**</span></span>|<span data-ttu-id="b67e0-118">Optional.</span><span class="sxs-lookup"><span data-stu-id="b67e0-118">Optional.</span></span> <span data-ttu-id="b67e0-119">Sie können beliebig viele Tabellen für die Arbeitsauslastung auflisten.</span><span class="sxs-lookup"><span data-stu-id="b67e0-119">List as many tables as appropriate for your workload.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="b67e0-120">Elementbeziehungen</span><span class="sxs-lookup"><span data-stu-id="b67e0-120">Element Relationships</span></span>  
  
|<span data-ttu-id="b67e0-121">Beziehung</span><span class="sxs-lookup"><span data-stu-id="b67e0-121">Relationship</span></span>|<span data-ttu-id="b67e0-122">Elemente</span><span class="sxs-lookup"><span data-stu-id="b67e0-122">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="b67e0-123">**Übergeordnetes Element**</span><span class="sxs-lookup"><span data-stu-id="b67e0-123">**Parent element**</span></span>|[<span data-ttu-id="b67e0-124">Schema-Element für Datenbank &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="b67e0-124">Schema Element for Database &#40;DTA&#41;</span></span>](schema-element-for-database-dta.md)|  
|<span data-ttu-id="b67e0-125">**Untergeordnete Elemente**</span><span class="sxs-lookup"><span data-stu-id="b67e0-125">**Child elements**</span></span>|[<span data-ttu-id="b67e0-126">Name-Element für Tabelle &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="b67e0-126">Name Element for Table &#40;DTA&#41;</span></span>](name-element-for-table-dta.md)|  
  
## <a name="remarks"></a><span data-ttu-id="b67e0-127">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="b67e0-127">Remarks</span></span>  
 <span data-ttu-id="b67e0-128">Wenn Sie kein `Table`-Element angeben, geht der Datenbankoptimierungsratgeber davon aus, dass sich alle Tabellen in der angegebenen Datenbank optimieren lassen.</span><span class="sxs-lookup"><span data-stu-id="b67e0-128">If you do not specify a `Table` element, Database Engine Tuning Advisor will assume all tables on the specified database can be tuned.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b67e0-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b67e0-129">Example</span></span>  
 <span data-ttu-id="b67e0-130">Ein Beispiel für die Verwendung finden Sie unter [Server-Element &#40;DTA&#41;](server-element-dta.md).</span><span class="sxs-lookup"><span data-stu-id="b67e0-130">For a usage example, see [Server Element &#40;DTA&#41;](server-element-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b67e0-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b67e0-131">See Also</span></span>  
 [<span data-ttu-id="b67e0-132">XML-Eingabedateireferenz &#40;Datenbankoptimierungsratgeber&#41;</span><span class="sxs-lookup"><span data-stu-id="b67e0-132">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
