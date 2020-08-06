---
title: Name-Element für Tabelle (DTA) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Name element
ms.assetid: 422a755f-ee52-4863-b1aa-f4ef1b8fd0bb
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8fa8481cf8990fb63995abcb6300cd9a352c859a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620098"
---
# <a name="name-element-for-table-dta"></a><span data-ttu-id="466d5-102">Name-Element für Tabelle (DTA)</span><span class="sxs-lookup"><span data-stu-id="466d5-102">Name Element for Table (DTA)</span></span>
  <span data-ttu-id="466d5-103">Gibt einen Tabellennamen zur Optimierung an.</span><span class="sxs-lookup"><span data-stu-id="466d5-103">Specifies a table name for tuning.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="466d5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="466d5-104">Syntax</span></span>  
  
```  
  
<Schema>  
    <Table>  
        <Name>...</Name>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="466d5-105">Elementmerkmale</span><span class="sxs-lookup"><span data-stu-id="466d5-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="466d5-106">Merkmal</span><span class="sxs-lookup"><span data-stu-id="466d5-106">Characteristic</span></span>|<span data-ttu-id="466d5-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="466d5-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="466d5-108">**Datentyp und -länge**</span><span class="sxs-lookup"><span data-stu-id="466d5-108">**Data type and length**</span></span>|<span data-ttu-id="466d5-109">`string`, 1 bis 255 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="466d5-109">`string`, between 1 and 255 characters.</span></span>|  
|<span data-ttu-id="466d5-110">**Standardwert**</span><span class="sxs-lookup"><span data-stu-id="466d5-110">**Default value**</span></span>|<span data-ttu-id="466d5-111">Keine.</span><span class="sxs-lookup"><span data-stu-id="466d5-111">None.</span></span>|  
|<span data-ttu-id="466d5-112">**Vorkommen**</span><span class="sxs-lookup"><span data-stu-id="466d5-112">**Occurrence**</span></span>|<span data-ttu-id="466d5-113">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="466d5-113">Required.</span></span> <span data-ttu-id="466d5-114">Einmalig pro `Table`-Element.</span><span class="sxs-lookup"><span data-stu-id="466d5-114">Once for each `Table` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="466d5-115">Elementbeziehungen</span><span class="sxs-lookup"><span data-stu-id="466d5-115">Element Relationships</span></span>  
  
|<span data-ttu-id="466d5-116">Beziehung</span><span class="sxs-lookup"><span data-stu-id="466d5-116">Relationship</span></span>|<span data-ttu-id="466d5-117">Elemente</span><span class="sxs-lookup"><span data-stu-id="466d5-117">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="466d5-118">**Übergeordnetes Element**</span><span class="sxs-lookup"><span data-stu-id="466d5-118">**Parent element**</span></span>|[<span data-ttu-id="466d5-119">Table-Element für Schema &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="466d5-119">Table Element for Schema &#40;DTA&#41;</span></span>](table-element-for-schema-dta.md)|  
|<span data-ttu-id="466d5-120">**Untergeordnete Elemente**</span><span class="sxs-lookup"><span data-stu-id="466d5-120">**Child elements**</span></span>|<span data-ttu-id="466d5-121">Keine.</span><span class="sxs-lookup"><span data-stu-id="466d5-121">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="466d5-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="466d5-122">Example</span></span>  
 <span data-ttu-id="466d5-123">Ein Beispiel für die Verwendung finden Sie unter [Server-Element &#40;DTA&#41;](server-element-dta.md).</span><span class="sxs-lookup"><span data-stu-id="466d5-123">For a usage example, see [Server Element &#40;DTA&#41;](server-element-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="466d5-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="466d5-124">See Also</span></span>  
 [<span data-ttu-id="466d5-125">XML-Eingabedateireferenz &#40;Datenbankoptimierungsratgeber&#41;</span><span class="sxs-lookup"><span data-stu-id="466d5-125">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
