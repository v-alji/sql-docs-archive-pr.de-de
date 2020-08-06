---
title: Name-Element für Datenbank (DTA) | Microsoft-Dokumentation
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
ms.assetid: e871c4fa-3b57-46cf-b4f8-e3be86f92dc4
author: stevestein
ms.author: sstein
ms.openlocfilehash: c692e31b9175bf05dcfb0504ea79e98cbb82f36b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694978"
---
# <a name="name-element-for-database-dta"></a><span data-ttu-id="ef0d7-102">Name-Element für Datenbank (DTA)</span><span class="sxs-lookup"><span data-stu-id="ef0d7-102">Name Element for Database (DTA)</span></span>
  <span data-ttu-id="ef0d7-103">Gibt den Namen einer zu optimierenden Datenbank an.</span><span class="sxs-lookup"><span data-stu-id="ef0d7-103">Specifies the name of a database that you want to tune.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef0d7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ef0d7-104">Syntax</span></span>  
  
```  
  
<Server>  
    <Database>  
        <Name>...</Name>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="ef0d7-105">Elementmerkmale</span><span class="sxs-lookup"><span data-stu-id="ef0d7-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="ef0d7-106">Merkmal</span><span class="sxs-lookup"><span data-stu-id="ef0d7-106">Characteristic</span></span>|<span data-ttu-id="ef0d7-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ef0d7-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="ef0d7-108">**Datentyp und -länge**</span><span class="sxs-lookup"><span data-stu-id="ef0d7-108">**Data type and length**</span></span>|<span data-ttu-id="ef0d7-109">`string`, unbegrenzte Länge.</span><span class="sxs-lookup"><span data-stu-id="ef0d7-109">`string`, unlimited length.</span></span>|  
|<span data-ttu-id="ef0d7-110">**Standardwert**</span><span class="sxs-lookup"><span data-stu-id="ef0d7-110">**Default value**</span></span>|<span data-ttu-id="ef0d7-111">Keine.</span><span class="sxs-lookup"><span data-stu-id="ef0d7-111">None.</span></span>|  
|<span data-ttu-id="ef0d7-112">**Vorkommen**</span><span class="sxs-lookup"><span data-stu-id="ef0d7-112">**Occurrence**</span></span>|<span data-ttu-id="ef0d7-113">Einmal pro `Database`-Element erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ef0d7-113">Required once per `Database` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="ef0d7-114">Elementbeziehungen</span><span class="sxs-lookup"><span data-stu-id="ef0d7-114">Element Relationships</span></span>  
  
|<span data-ttu-id="ef0d7-115">Beziehung</span><span class="sxs-lookup"><span data-stu-id="ef0d7-115">Relationship</span></span>|<span data-ttu-id="ef0d7-116">Elemente</span><span class="sxs-lookup"><span data-stu-id="ef0d7-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="ef0d7-117">**Übergeordnetes Element**</span><span class="sxs-lookup"><span data-stu-id="ef0d7-117">**Parent element**</span></span>|[<span data-ttu-id="ef0d7-118">Database-Element für Server &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="ef0d7-118">Database Element for Server &#40;DTA&#41;</span></span>](database-element-for-server-dta.md)|  
|<span data-ttu-id="ef0d7-119">**Untergeordnete Elemente**</span><span class="sxs-lookup"><span data-stu-id="ef0d7-119">**Child elements**</span></span>|<span data-ttu-id="ef0d7-120">Keine.</span><span class="sxs-lookup"><span data-stu-id="ef0d7-120">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ef0d7-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ef0d7-121">Example</span></span>  
 <span data-ttu-id="ef0d7-122">Ein Beispiel für die Verwendung dieses Elements finden Sie unter [Server-Element &#40;DTA&#41;](server-element-dta.md).</span><span class="sxs-lookup"><span data-stu-id="ef0d7-122">For a usage example of this element, see [Server Element &#40;DTA&#41;](server-element-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef0d7-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ef0d7-123">See Also</span></span>  
 [<span data-ttu-id="ef0d7-124">XML-Eingabedateireferenz &#40;Datenbankoptimierungsratgeber&#41;</span><span class="sxs-lookup"><span data-stu-id="ef0d7-124">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
