---
title: Column-Element für Index (DTA) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Column element
ms.assetid: ba9fac20-26bd-4333-940e-842c15241b46
author: stevestein
ms.author: sstein
ms.openlocfilehash: 67853dc7d1193d3a0f80e56023846bc55a20bdaa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695042"
---
# <a name="column-element-for-index-dta"></a><span data-ttu-id="535ff-102">Column-Element für Index (DTA)</span><span class="sxs-lookup"><span data-stu-id="535ff-102">Column Element for Index (DTA)</span></span>
  <span data-ttu-id="535ff-103">Gibt die Spalten an, für die der Index für eine benutzerspezifische Konfiguration erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="535ff-103">Specifies the columns on which the index is created for a user-specified configuration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="535ff-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="535ff-104">Syntax</span></span>  
  
```  
  
<Create>  
  <Index>  
    <Name>...</Name>  
    <Column [Type | SortOrder]>  
     ...code removed here...  
     </Column>  
```  
  
## <a name="element-attributes"></a><span data-ttu-id="535ff-105">Elementattribute</span><span class="sxs-lookup"><span data-stu-id="535ff-105">Element Attributes</span></span>  
  
|<span data-ttu-id="535ff-106">Spaltenattribut</span><span class="sxs-lookup"><span data-stu-id="535ff-106">Column Attribute</span></span>|<span data-ttu-id="535ff-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="535ff-107">Description</span></span>|  
|----------------------|-----------------|  
|`Type`|<span data-ttu-id="535ff-108">Optional.</span><span class="sxs-lookup"><span data-stu-id="535ff-108">Optional.</span></span> <span data-ttu-id="535ff-109">Gibt den Indexspaltentyp an.</span><span class="sxs-lookup"><span data-stu-id="535ff-109">Specifies the index column type.</span></span> <span data-ttu-id="535ff-110">Mit einem **string** -Datentyp können Sie dieses Attribut mit einem der folgenden zulässigen Werte angeben:</span><span class="sxs-lookup"><span data-stu-id="535ff-110">Use a **string** data type to specify this attribute with one of the following allowed values:</span></span><br /><br /> <span data-ttu-id="535ff-111">`KeyColumn`:</span><span class="sxs-lookup"><span data-stu-id="535ff-111">`KeyColumn`:</span></span><br />                  <span data-ttu-id="535ff-112">Gibt an, dass durch einen Indexschlüssel auf die Spalte verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="535ff-112">Specifies that the column is referenced by an index key.</span></span> <span data-ttu-id="535ff-113">Verwenden Sie die folgende Syntax, um dieses Attribut festzulegen:</span><span class="sxs-lookup"><span data-stu-id="535ff-113">Use the following syntax to set this attribute:</span></span><br />`<Column Type="KeyColumn">`<br /><span data-ttu-id="535ff-114">Weitere Informationen zu Schlüsselspalten finden Sie unter [Beschreibung von gruppierten und nicht gruppierten Indizes](../../relational-databases/indexes/clustered-and-nonclustered-indexes-described.md).</span><span class="sxs-lookup"><span data-stu-id="535ff-114">For more information about key columns, see [Clustered and Nonclustered Indexes Described](../../relational-databases/indexes/clustered-and-nonclustered-indexes-described.md).</span></span><br /><br /> <span data-ttu-id="535ff-115">`IncludedColumn`: Gibt an, dass die Spalte eine enthaltene Spalte (statt einer Schlüssel Spalte) ist.</span><span class="sxs-lookup"><span data-stu-id="535ff-115">`IncludedColumn`: Specifies that the column is an included column (instead of a key column).</span></span> <span data-ttu-id="535ff-116">Verwenden Sie die folgende Syntax, um dieses Attribut festzulegen:</span><span class="sxs-lookup"><span data-stu-id="535ff-116">Use the following syntax to set this attribute:</span></span><br />`<Column Type="IncludedColumn">`<br /><span data-ttu-id="535ff-117">Weitere Informationen zu eingeschlossenen Spalten finden Sie unter [Erstellen von Indizes mit eingeschlossenen Spalten](../../relational-databases/indexes/create-indexes-with-included-columns.md).</span><span class="sxs-lookup"><span data-stu-id="535ff-117">For more information about included columns, see [Create Indexes with Included Columns](../../relational-databases/indexes/create-indexes-with-included-columns.md).</span></span>|  
|`SortOrder`|<span data-ttu-id="535ff-118">Optional.</span><span class="sxs-lookup"><span data-stu-id="535ff-118">Optional.</span></span> <span data-ttu-id="535ff-119">Gibt die Sortierreihenfolge der Spalte an.</span><span class="sxs-lookup"><span data-stu-id="535ff-119">Specifies the sorting order of the column.</span></span> <span data-ttu-id="535ff-120">Mit einem **string** -Datentyp können Sie die Sortierreihenfolge wie folgt als **Aufsteigend** oder **Absteigend** angeben:</span><span class="sxs-lookup"><span data-stu-id="535ff-120">Use a **string** data type to specify either an **"Ascending"** or **"Descending"** sorting order as follows:</span></span><br /><br /> `<Column SortOrder="Ascending">`|  
  
## <a name="element-characteristics"></a><span data-ttu-id="535ff-121">Elementmerkmale</span><span class="sxs-lookup"><span data-stu-id="535ff-121">Element Characteristics</span></span>  
  
|<span data-ttu-id="535ff-122">Merkmal</span><span class="sxs-lookup"><span data-stu-id="535ff-122">Characteristic</span></span>|<span data-ttu-id="535ff-123">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="535ff-123">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="535ff-124">**Datentyp und -länge**</span><span class="sxs-lookup"><span data-stu-id="535ff-124">**Data type and length**</span></span>|<span data-ttu-id="535ff-125">Keine.</span><span class="sxs-lookup"><span data-stu-id="535ff-125">None.</span></span>|  
|<span data-ttu-id="535ff-126">**Standardwert**</span><span class="sxs-lookup"><span data-stu-id="535ff-126">**Default value**</span></span>|<span data-ttu-id="535ff-127">Keine.</span><span class="sxs-lookup"><span data-stu-id="535ff-127">None.</span></span>|  
|<span data-ttu-id="535ff-128">**Vorkommen**</span><span class="sxs-lookup"><span data-stu-id="535ff-128">**Occurrence**</span></span>|<span data-ttu-id="535ff-129">Angabe von bis zu 1024 Spalten für das `Index`-Element möglich.</span><span class="sxs-lookup"><span data-stu-id="535ff-129">Can specify up to 1024 columns for the `Index` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="535ff-130">Elementbeziehungen</span><span class="sxs-lookup"><span data-stu-id="535ff-130">Element Relationships</span></span>  
  
|<span data-ttu-id="535ff-131">Beziehung</span><span class="sxs-lookup"><span data-stu-id="535ff-131">Relationship</span></span>|<span data-ttu-id="535ff-132">Elemente</span><span class="sxs-lookup"><span data-stu-id="535ff-132">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="535ff-133">**Übergeordnetes Element**</span><span class="sxs-lookup"><span data-stu-id="535ff-133">**Parent element**</span></span>|[<span data-ttu-id="535ff-134">Index-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="535ff-134">Index Element &#40;DTA&#41;</span></span>](index-element-dta.md)|  
|<span data-ttu-id="535ff-135">**Untergeordnete Elemente**</span><span class="sxs-lookup"><span data-stu-id="535ff-135">**Child elements**</span></span>|[<span data-ttu-id="535ff-136">Name-Element für Spalte &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="535ff-136">Name Element for Column &#40;DTA&#41;</span></span>](name-element-for-column-dta.md)|  
  
## <a name="example"></a><span data-ttu-id="535ff-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="535ff-137">Example</span></span>  
 <span data-ttu-id="535ff-138">Ein Beispiel für die Verwendung dieses Elements finden Sie unter [Beispiel für eine XML-Eingabedatei mit benutzerdefinierter Konfiguration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="535ff-138">For a usage example of this element, see the [XML Input File Sample with User-specified Configuration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="535ff-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="535ff-139">See Also</span></span>  
 [<span data-ttu-id="535ff-140">XML-Eingabedateireferenz &#40;Datenbankoptimierungsratgeber&#41;</span><span class="sxs-lookup"><span data-stu-id="535ff-140">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
