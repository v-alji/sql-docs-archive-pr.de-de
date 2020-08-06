---
title: Andere Anmerkungen (SQLXML 4,0) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- url-encode annotation
- sql:key-fields
- use-cdata annotation
- sql:is-mapping-schema
- sql:url-encode
- sql:id-prefix
- sql:use-cdata
- key-fields annotation
- id-prefix annotation [SQLXML]
- is-mapping-schema annotation
ms.assetid: f7b4d37b-d6d3-4ac3-b2fd-a0b534a924e4
author: rothja
ms.author: jroth
ms.openlocfilehash: b654568c93df0a0c3e08cf6eaa615b7026a9c18a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617887"
---
# <a name="other-annotations-sqlxml-40"></a><span data-ttu-id="3d93b-102">Andere Anmerkungen (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="3d93b-102">Other Annotations (SQLXML 4.0)</span></span>
  <span data-ttu-id="3d93b-103">Neben den in den vorherigen Themen in diesem Abschnitt beschriebenen Anmerkungen interpretiert XML-Massenladen diese anderen Anmerkungen folgendermaßen:</span><span class="sxs-lookup"><span data-stu-id="3d93b-103">In addition to the annotations discussed in the previous topics in this section, XML Bulk Load interprets these other annotations, as follows:</span></span>  
  
 `sql:id-prefix`  
 <span data-ttu-id="3d93b-104">Wenn das Schema Präfixe für die XML-Daten festlegt, entfernt XML-Massenladen die Präfixe, bevor die Daten an Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="3d93b-104">If the schema specifies prefixes to the XML data, XML Bulk Load removes the prefixes before sending the data to Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 `sql:use-cdata`  
 <span data-ttu-id="3d93b-105">XML-Massenladen liest den Text, der in den CDATA-Abschnitten gespeichert wird, und sendet ihn an [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3d93b-105">XML Bulk Load reads the text that is stored in the CDATA sections and sends it to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 `sql:url-encode`  
 <span data-ttu-id="3d93b-106">XML-Massenladen unterstützt diese Anmerkung nicht.</span><span class="sxs-lookup"><span data-stu-id="3d93b-106">XML Bulk Load does not support this annotation.</span></span> <span data-ttu-id="3d93b-107">Eine in der XML-Dateneingabe angegebene URL wird beispielsweise von XML-Massenladen an diesem Speicherort nicht gelesen, sodass sie in der Datenbank gespeichert werden kann.</span><span class="sxs-lookup"><span data-stu-id="3d93b-107">For example, you cannot specify a URL in the XML data input and expect XML Bulk Load to read data from that location to store it in the database.</span></span>  
  
 `sql:is-mapping-schema`  
 <span data-ttu-id="3d93b-108">XML-Massenladen unterstützt weder diese Anmerkung noch `sql:id`.</span><span class="sxs-lookup"><span data-stu-id="3d93b-108">XML Bulk Load does not support this annotation, nor does it support `sql:id`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3d93b-109">XML-Massenladen unterstützt keine Inlinezuordnungsschemas.</span><span class="sxs-lookup"><span data-stu-id="3d93b-109">XML Bulk Load does not support inline mapping schemas.</span></span>  
  
 `sql:key-fields`  
 <span data-ttu-id="3d93b-110">XML-Massenladen ignoriert stets diese Anmerkung.</span><span class="sxs-lookup"><span data-stu-id="3d93b-110">XML Bulk Load always ignores this annotation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d93b-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3d93b-111">See Also</span></span>  
 [<span data-ttu-id="3d93b-112">Interpretation der Anmerkung &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="3d93b-112">Annotation Interpretation &#40;SQLXML 4.0&#41;</span></span>](annotation-interpretation-sqlxml-4-0.md)  
  
  
