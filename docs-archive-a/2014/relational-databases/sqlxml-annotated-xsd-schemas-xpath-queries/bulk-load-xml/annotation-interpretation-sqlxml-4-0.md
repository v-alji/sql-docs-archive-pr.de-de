---
title: Interpretation von Anmerkungen (SQLXML 4,0) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- annotated XSD schemas, XML Bulk Load
- XML Bulk Load [SQLXML], annotation intepretations
- annotations [SQLXML]
- bulk load [SQLXML], annotation interpretations
- annotated XDR schemas, XML Bulk Load
ms.assetid: 1c46bdb6-2812-4a13-b60b-7101c04b299f
author: rothja
ms.author: jroth
ms.openlocfilehash: c31d56f7dd577b4b5a5b582eb0e3b1db312109a8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619754"
---
# <a name="annotation-interpretation-sqlxml-40"></a><span data-ttu-id="ec3e8-102">Interpretation von Anmerkungen (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="ec3e8-102">Annotation Interpretation (SQLXML 4.0)</span></span>
  <span data-ttu-id="ec3e8-103">In den Themen in diesem Abschnitt wird beschrieben, wie beim XML-Massenladen Anmerkungen im XSD-Schema interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="ec3e8-103">The topics in this section describe how XML Bulk Load interprets annotations in the XSD schema.</span></span> <span data-ttu-id="ec3e8-104">Das hier beschriebene Verhalten gilt auch für die Anmerkungen im XDR-Schema.</span><span class="sxs-lookup"><span data-stu-id="ec3e8-104">The behavior described here also applies to the annotations in the XDR schema.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ec3e8-105">In diesen Themen werden nur diejenigen Anmerkungen behandelt, die in der Verarbeitung von XML-Massenladevorgängen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ec3e8-105">The information in these topics describes only the annotations used by XML Bulk Load in its processing.</span></span> <span data-ttu-id="ec3e8-106">Eine umfassende Liste der Anmerkungen für das XSD-Schema, die von SQLXML 4,0 unterstützt werden, finden [Sie unter Verwenden von Anmerkungen in XSD-Schemas &#40;SQLXML 4,0&#41;](../../sqlxml-annotated-xsd-schemas-using/using-annotations-in-xsd-schemas-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="ec3e8-106">For a complete list of annotations for the XSD schema that are supported by SQLXML 4.0, see [Using Annotations in XSD Schemas &#40;SQLXML 4.0&#41;](../../sqlxml-annotated-xsd-schemas-using/using-annotations-in-xsd-schemas-sqlxml-4-0.md).</span></span> <span data-ttu-id="ec3e8-107">Eine Liste der unterstützten Anmerkungen für XDR-Schemas finden Sie unter [mit Anmerkungen versehene XDR-Schemas &#40;in SQLXML 4,0&#41;deprecated ](../../sqlxml/annotated-xsd-schemas/annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="ec3e8-107">For a list of supported annotations for XDR schemas, see [Annotated XDR Schemas &#40;Deprecated in SQLXML 4.0&#41;](../../sqlxml/annotated-xsd-schemas/annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ec3e8-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="ec3e8-108">In This Section</span></span>  
 [<span data-ttu-id="ec3e8-109">SQL: Relationship und die Schlüssel Bestellungs Regel &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="ec3e8-109">sql:relationship and the Key Ordering Rule &#40;SQLXML 4.0&#41;</span></span>](annotation-interpretation-sql-relationship-and-key-ordering-rule.md)  
 <span data-ttu-id="ec3e8-110">Beschreibt, wie die `sql:relationship`-Anmerkung beim XML-Massenladen interpretiert wird.</span><span class="sxs-lookup"><span data-stu-id="ec3e8-110">Describes how the `sql:relationship` annotation is interpreted in XML Bulk Load.</span></span>  
  
 [<span data-ttu-id="ec3e8-111">SQL: zugeordnet &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="ec3e8-111">sql:mapped &#40;SQLXML 4.0&#41;</span></span>](annotation-interpretation-sql-mapped.md)  
 <span data-ttu-id="ec3e8-112">Beschreibt, wie die `sql:mapped`-Anmerkung beim XML-Massenladen interpretiert wird.</span><span class="sxs-lookup"><span data-stu-id="ec3e8-112">Describes how the `sql:mapped` annotation is interpreted in XML Bulk Load.</span></span>  
  
 [<span data-ttu-id="ec3e8-113">SQL: limit-field und SQL: limit-value &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="ec3e8-113">sql:limit-field and sql:limit-value &#40;SQLXML 4.0&#41;</span></span>](annotation-interpretation-sql-limit-field-and-sql-limit-value.md)  
 <span data-ttu-id="ec3e8-114">Beschreibt, wie die `sql:limit-field`-Anmerkung und die `sql:limit-value`-Anmerkung beim XML-Massenladen interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="ec3e8-114">Describes how the `sql:limit-field` and `sql:limit-value` annotations are interpreted in XML Bulk Load.</span></span>  
  
 [<span data-ttu-id="ec3e8-115">SQL: overflow-Feld &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="ec3e8-115">sql:overflow-field &#40;SQLXML 4.0&#41;</span></span>](annotation-interpretation-sql-overflow-field.md)  
 <span data-ttu-id="ec3e8-116">Beschreibt, wie die `sql:overflow`-Anmerkung beim XML-Massenladen interpretiert wird.</span><span class="sxs-lookup"><span data-stu-id="ec3e8-116">Describes how the `sql:overflow` annotation is interpreted in XML Bulk Load.</span></span>  
  
 [<span data-ttu-id="ec3e8-117">Andere Anmerkungen &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="ec3e8-117">Other Annotations &#40;SQLXML 4.0&#41;</span></span>](annotation-interpretation-other-annotations.md)  
 <span data-ttu-id="ec3e8-118">Beschreibt, wie die folgenden Anmerkungen beim XML-Massenladen interpretiert werden:  `sql:id-prefix`, `sql:use-cdata`, `sql:url-encode`, `sql:is-mapping-schema`, `sql:key-fields`.</span><span class="sxs-lookup"><span data-stu-id="ec3e8-118">Describes how the following annotations are interpreted in XML Bulk Load: `sql:id-prefix`, `sql:use-cdata`, `sql:url-encode`, `sql:is-mapping-schema`, `sql:key-fields`.</span></span>  
  
  
