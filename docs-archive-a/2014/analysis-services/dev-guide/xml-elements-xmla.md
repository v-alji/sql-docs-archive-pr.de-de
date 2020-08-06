---
title: XML-Elemente (XMLA) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- XMLA, elements
- XML for Analysis, elements
- elements [XML for Analysis]
ms.assetid: 40ab2360-efb6-4ba6-bf23-e84964e51008
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5c1e5b046bfa57302baefc43a4da989be9c70e08
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621259"
---
# <a name="xml-elements-xmla"></a><span data-ttu-id="39fed-102">XML-Elemente (XMLA)</span><span class="sxs-lookup"><span data-stu-id="39fed-102">XML Elements (XMLA)</span></span>
  <span data-ttu-id="39fed-103">In den folgenden Themen werden die verschiedenen von unterstützten XML for Analysis (XMLA)-Element Kategorien beschrieben [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="39fed-103">The following topics describe the various XML for Analysis (XMLA) element categories supported by [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="39fed-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="39fed-104">In This Section</span></span>  
  
|<span data-ttu-id="39fed-105">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="39fed-105">Property</span></span>|<span data-ttu-id="39fed-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="39fed-106">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="39fed-107">Header &#40;XMLA&#41;</span><span class="sxs-lookup"><span data-stu-id="39fed-107">Headers &#40;XMLA&#41;</span></span>](https://docs.microsoft.com/bi-reference/xmla/xml-elements-headers/xml-elements-headers)|<span data-ttu-id="39fed-108">Beschreibt die Elemente, die in einem SOAP-Header eines SOAP-Umschlags durch die Anwendung oder eine [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]-Instanz gesendet werden, um Funktionen auf Protokollebene zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="39fed-108">Describes those elements sent in the SOAP header of a SOAP envelope, either by an application or by an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance, to manage protocol-level features.</span></span>|  
|[<span data-ttu-id="39fed-109">Methoden &#40;XMLA&#41;</span><span class="sxs-lookup"><span data-stu-id="39fed-109">Methods &#40;XMLA&#41;</span></span>](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods)|<span data-ttu-id="39fed-110">Beschreibt die obersten Elemente, die von einer Anwendung in einem SOAP-Umschlag an eine [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]-Instanz gesendet werden, um Daten oder Metadaten abzufragen oder Aktionen auf der Instanz durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="39fed-110">Describes the topmost elements sent by an application in a SOAP envelope to an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance to retrieve data or metadata, or to perform actions on the instance.</span></span>|  
|[<span data-ttu-id="39fed-111">Befehle &#40;XMLA&#41;</span><span class="sxs-lookup"><span data-stu-id="39fed-111">Commands &#40;XMLA&#41;</span></span>](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/xml-elements-commands)|<span data-ttu-id="39fed-112">Beschreibt die Elemente innerhalb einer XMLA-Methode, die eine bestimmte Aktion durchführen.</span><span class="sxs-lookup"><span data-stu-id="39fed-112">Describes the elements sent within an XMLA method to perform a specific action.</span></span>|  
|[<span data-ttu-id="39fed-113">Objekte &#40;XMLA&#41;</span><span class="sxs-lookup"><span data-stu-id="39fed-113">Objects &#40;XMLA&#41;</span></span>](https://docs.microsoft.com/bi-reference/xmla/xml-elements-objects)|<span data-ttu-id="39fed-114">Beschreibt die obersten Elemente, die von einer Anwendung in einem SOAP-Umschlag von einer [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]-Instanz als Antwort auf eine XMLA-Methode erhalten werden.</span><span class="sxs-lookup"><span data-stu-id="39fed-114">Describes the topmost elements received by an application in a SOAP envelope from an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance in response to an XMLA method.</span></span>|  
|[<span data-ttu-id="39fed-115">Eigenschaften &#40;XMLA&#41;</span><span class="sxs-lookup"><span data-stu-id="39fed-115">Properties &#40;XMLA&#41;</span></span>](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/xml-elements-properties)|<span data-ttu-id="39fed-116">Beschreibt die untergeordneten Elemente für XMLA-Header, Methoden, Objekte oder Befehle.</span><span class="sxs-lookup"><span data-stu-id="39fed-116">Describes the child elements for XMLA headers, methods, objects, or commands.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="39fed-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="39fed-117">See Also</span></span>  
 <span data-ttu-id="39fed-118">[XML-Datentypen &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-data-types/xml-data-types-xmla) </span><span class="sxs-lookup"><span data-stu-id="39fed-118">[XML Data Types &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-data-types/xml-data-types-xmla) </span></span>  
 [<span data-ttu-id="39fed-119">Entwickeln mit Analysis Services Scripting Language &#40;ASSL&#41;</span><span class="sxs-lookup"><span data-stu-id="39fed-119">Developing with Analysis Services Scripting Language &#40;ASSL&#41;</span></span>](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md)  
  
  
