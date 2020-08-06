---
title: Schema-Element für Datenbank (DTA) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Schema element
ms.assetid: d932e59c-953f-4ab4-934d-b6baf344835c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7653177878f3a832abd2d1ca266bc5feb17b9a29
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609614"
---
# <a name="schema-element-for-database-dta"></a><span data-ttu-id="75be4-102">Schema-Element für Datenbank (DTA)</span><span class="sxs-lookup"><span data-stu-id="75be4-102">Schema Element for Database (DTA)</span></span>
  <span data-ttu-id="75be4-103">Gibt das Schema der zu optimierenden Datenbank an.</span><span class="sxs-lookup"><span data-stu-id="75be4-103">Specifies the schema of the database that you want to tune.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75be4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="75be4-104">Syntax</span></span>  
  
```  
  
<Database>  
...code removed here...  
    <Schema>...</Schema>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="75be4-105">Elementmerkmale</span><span class="sxs-lookup"><span data-stu-id="75be4-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="75be4-106">Merkmal</span><span class="sxs-lookup"><span data-stu-id="75be4-106">Characteristic</span></span>|<span data-ttu-id="75be4-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="75be4-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="75be4-108">**Datentyp und -länge**</span><span class="sxs-lookup"><span data-stu-id="75be4-108">**Data type and length**</span></span>|<span data-ttu-id="75be4-109">Keine.</span><span class="sxs-lookup"><span data-stu-id="75be4-109">None.</span></span>|  
|<span data-ttu-id="75be4-110">**Standardwert**</span><span class="sxs-lookup"><span data-stu-id="75be4-110">**Default value**</span></span>|<span data-ttu-id="75be4-111">Keine.</span><span class="sxs-lookup"><span data-stu-id="75be4-111">None.</span></span>|  
|<span data-ttu-id="75be4-112">**Vorkommen**</span><span class="sxs-lookup"><span data-stu-id="75be4-112">**Occurrence**</span></span>|<span data-ttu-id="75be4-113">Einmalig erforderlich für das **Database** -Element, das unter dem **Server** -Element angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="75be4-113">Required once for the **Database** element that is specified under the **Server** element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="75be4-114">Elementbeziehungen</span><span class="sxs-lookup"><span data-stu-id="75be4-114">Element Relationships</span></span>  
  
|<span data-ttu-id="75be4-115">Beziehung</span><span class="sxs-lookup"><span data-stu-id="75be4-115">Relationship</span></span>|<span data-ttu-id="75be4-116">Elemente</span><span class="sxs-lookup"><span data-stu-id="75be4-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="75be4-117">**Übergeordnetes Element**</span><span class="sxs-lookup"><span data-stu-id="75be4-117">**Parent element**</span></span>|[<span data-ttu-id="75be4-118">Database-Element für Server &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="75be4-118">Database Element for Server &#40;DTA&#41;</span></span>](database-element-for-server-dta.md)|  
|<span data-ttu-id="75be4-119">**Untergeordnete Elemente**</span><span class="sxs-lookup"><span data-stu-id="75be4-119">**Child elements**</span></span>|[<span data-ttu-id="75be4-120">Name-Element für Schema &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="75be4-120">Name Element for Schema &#40;DTA&#41;</span></span>](name-element-for-schema-dta.md)<br /><br /> [<span data-ttu-id="75be4-121">Table-Element für Schema &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="75be4-121">Table Element for Schema &#40;DTA&#41;</span></span>](table-element-for-schema-dta.md)|  
  
## <a name="example"></a><span data-ttu-id="75be4-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="75be4-122">Example</span></span>  
 <span data-ttu-id="75be4-123">Ein Beispiel für die Verwendung dieses Elements finden Sie unter [Server-Element &#40;DTA&#41;](server-element-dta.md).</span><span class="sxs-lookup"><span data-stu-id="75be4-123">For a usage example of this element, see [Server Element &#40;DTA&#41;](server-element-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75be4-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="75be4-124">See Also</span></span>  
 [<span data-ttu-id="75be4-125">XML-Eingabedateireferenz &#40;Datenbankoptimierungsratgeber&#41;</span><span class="sxs-lookup"><span data-stu-id="75be4-125">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
