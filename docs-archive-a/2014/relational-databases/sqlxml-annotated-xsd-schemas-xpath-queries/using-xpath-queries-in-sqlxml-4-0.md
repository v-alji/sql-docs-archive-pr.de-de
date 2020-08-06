---
title: Verwenden von XPath-Abfragen in SQLXML 4,0 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath queries [SQLXML]
- annotated XSD schemas, XPath queries
- queries [SQLXML], XPath
- XML views [SQLXML]
ms.assetid: 7814d099-81ec-4fb8-894a-729cdbb5015a
author: rothja
ms.author: jroth
ms.openlocfilehash: 80d82513b22d2a50aedb37955a210dd33746db86
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619734"
---
# <a name="using-xpath-queries-in-sqlxml-40"></a><span data-ttu-id="73bab-102">Verwenden von XPath-Abfragen in SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="73bab-102">Using XPath Queries in SQLXML 4.0</span></span>
  <span data-ttu-id="73bab-103">Da Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mit Anmerkungen versehene XSD-Schemas unterstützt, können Sie XML-Sichten der in einer Datenbank gespeicherten relationalen Daten erstellen.</span><span class="sxs-lookup"><span data-stu-id="73bab-103">Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] support for annotated XSD schemas allows you to create XML views of the relational data stored in the database.</span></span> <span data-ttu-id="73bab-104">Mit einer Teilmenge der Xpath-Sprache können Sie die von dem mit Anmerkungen versehenen XSD-Schema erstellten XML-Sichten abfragen.</span><span class="sxs-lookup"><span data-stu-id="73bab-104">You can use a subset of the XPath language to query the XML views created by an annotated XSD schema.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="73bab-105">Um XPath-Abfragen in SQLXML 4.0 verstehen zu können, müssen Sie XML-Sichten und verwandte Konzepte wie Vorlagen und Zuordnungsschemas kennen.</span><span class="sxs-lookup"><span data-stu-id="73bab-105">To understand XPath queries in SQLXML 4.0, you must be familiar with XML views and related concepts such as templates and mapping schema.</span></span> <span data-ttu-id="73bab-106">Weitere Informationen finden Sie unter [Einführung in XSD-Schemas mit Anmerkungen &#40;SQLXML 4,0&#41;](../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="73bab-106">For more information, see [Introduction to Annotated XSD Schemas &#40;SQLXML 4.0&#41;](../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md).</span></span> <span data-ttu-id="73bab-107">Weitere Informationen zu XPath finden Sie unter dem von der World Wide Web Consortium (W3C) definierten XPath-Standard unter http://www.w3.org/TR/xpath .</span><span class="sxs-lookup"><span data-stu-id="73bab-107">For more information about XPath, see the XPath standard defined by the World Wide Web Consortium (W3C) at http://www.w3.org/TR/xpath.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="73bab-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="73bab-108">In This Section</span></span>  
 [<span data-ttu-id="73bab-109">Einführung in die Verwendung von XPath-Abfragen &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="73bab-109">Introduction to Using XPath Queries &#40;SQLXML 4.0&#41;</span></span>](introduction-to-using-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="73bab-110">Gibt eine Einführung in XPath-Abfragen in SQLXML 4.0 sowie unterstützte und nicht unterstützte Funktionen der W3C XPath-Spezifikation.</span><span class="sxs-lookup"><span data-stu-id="73bab-110">Provides introductory information about XPath queries in SQLXML 4.0, including supported and unsupported functionality from the W3C XPath specification.</span></span>  
  
 [<span data-ttu-id="73bab-111">Angeben eines Speicherort Pfads &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="73bab-111">Specifying a Location Path &#40;SQLXML 4.0&#41;</span></span>](location-path/specifying-a-location-path-sqlxml-4-0.md)  
 <span data-ttu-id="73bab-112">Beschreibt, wie Speicherpfade in XPath-Abfragen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="73bab-112">Describes how to specify location paths in XPath queries.</span></span>  
  
 [<span data-ttu-id="73bab-113">Beispiel-XPath-Abfragen &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="73bab-113">Sample XPath Queries &#40;SQLXML 4.0&#41;</span></span>](samples/sample-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="73bab-114">Stellt Beispiele für XPath-Abfragen in SQLXML 4.0 bereit.</span><span class="sxs-lookup"><span data-stu-id="73bab-114">Provides sample XPath queries for SQLXML 4.0.</span></span>  
  
 [<span data-ttu-id="73bab-115">XPath-Datentypen &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="73bab-115">XPath Data Types &#40;SQLXML 4.0&#41;</span></span>](xpath-data-types-sqlxml-4-0.md)  
 <span data-ttu-id="73bab-116">Beschreibt XPath-Datentypen, die sich von den in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] und XSD verwendeten stark unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="73bab-116">Describes XPath data types, which are significantly different from those of both [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and XSD.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73bab-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="73bab-117">See Also</span></span>  
 [<span data-ttu-id="73bab-118">Client seitige XML-Formatierung &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="73bab-118">Client-side XML Formatting &#40;SQLXML 4.0&#41;</span></span>](../sqlxml/formatting/client-side-xml-formatting-sqlxml-4-0.md)  
  
  
