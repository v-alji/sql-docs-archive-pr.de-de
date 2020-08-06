---
title: 'Verwenden der Anmerkungen "SQL: Identity" und "SQL: GUID" | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- sql:guid
- annotated XSD schemas, IDENTITY-type columns
- annotated XSD schemas, GUID values
- DiffGrams [SQLXML], annotations
- identity annotation
- XSD schemas [SQLXML], GUID values
- GUIDs [SQLXML]
- guid annotation
- sql:identity
- IDENTITY-type column
- XSD schemas [SQLXML], IDENTITY-type columns
- updategrams [SQLXML], GUID values
ms.assetid: 7661dfd0-6573-4692-a8f1-3597adcd33c4
author: rothja
ms.author: jroth
ms.openlocfilehash: dc5c08f158911edb0a1a0638fc4bcee1e05a248c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617904"
---
# <a name="using-the-sqlidentity-and-sqlguid-annotations"></a><span data-ttu-id="f51ca-102">Verwenden der Anmerkungen 'sql:identity' und 'sql:guid'</span><span class="sxs-lookup"><span data-stu-id="f51ca-102">Using the sql:identity and sql:guid Annotations</span></span>
  <span data-ttu-id="f51ca-103">Sie können die `sql:identity` -und-Anmerkungen `sql:guid` in einem XSD-Schema auf allen Knoten angeben, die einer Daten Bank Spalte in zugeordnet sind [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f51ca-103">You can specify the `sql:identity` and `sql:guid` annotations in an XSD schema on any node that maps to a database column in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f51ca-104">Während das Updategram-Format das `updg:at-identity`-Attribut und das `updg:guid`-Attribut unterstützt, ist das beim DiffGram-Format nicht der Fall.</span><span class="sxs-lookup"><span data-stu-id="f51ca-104">Whereas the updategram format supports the `updg:at-identity` and `updg:guid` attributes, the DiffGram format does not.</span></span> <span data-ttu-id="f51ca-105">Das `updg:at-identity`-Attribut definiert das Verhalten beim Aktualisieren der Spalte vom Typ IDENTITY.</span><span class="sxs-lookup"><span data-stu-id="f51ca-105">The `updg:at-identity` attribute defines the behavior in updating an IDENTITY-type column.</span></span> <span data-ttu-id="f51ca-106">Mit dem `updg:guid`-Attribut können Sie einen GUID-Wert von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] abfragen und ihn im Updategram verwenden.</span><span class="sxs-lookup"><span data-stu-id="f51ca-106">The `updg:guid` attribute allows you to obtain a GUID value from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and use it in the updategram.</span></span> <span data-ttu-id="f51ca-107">Weitere Informationen und funktionierende Beispiele finden Sie unter [Einfügen von Daten mit XML-Update grams &#40;SQLXML 4,0&#41;](../sqlxml-annotated-xsd-schemas-xpath-queries/updategrams/inserting-data-using-xml-updategrams-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="f51ca-107">For more information and working samples, see [Inserting Data Using XML Updategrams &#40;SQLXML 4.0&#41;](../sqlxml-annotated-xsd-schemas-xpath-queries/updategrams/inserting-data-using-xml-updategrams-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="f51ca-108">Die `sql:identity`-Anmerkung und `sql:guid`-Anmerkung erweitern diese Funktionalität auf DiffGrams.</span><span class="sxs-lookup"><span data-stu-id="f51ca-108">The `sql:identity` and `sql:guid` annotations extend this functionality to DiffGrams.</span></span>  
  
 <span data-ttu-id="f51ca-109">Wenn Sie ein DiffGram ausführen, wird es zunächst in ein Updategram konvertiert, dann wird das Updategram ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f51ca-109">When you execute a DiffGram, it is first converted to an updategram, and then the updategram is executed.</span></span> <span data-ttu-id="f51ca-110">Indem Sie die `sql:identity`-Anmerkung und die `sql:guid`-Anmerkung im XSD-Schema angeben, definieren Sie das Verhalten eines Updategrams.</span><span class="sxs-lookup"><span data-stu-id="f51ca-110">By specifying the `sql:identity` and `sql:guid` annotations in the XSD schema, you are in fact defining the behavior of an updategram.</span></span> <span data-ttu-id="f51ca-111">Daher werden alle Anmerkungen im Kontext eines Updategrams beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f51ca-111">Therefore, all the annotations are described in the context of an updategram.</span></span> <span data-ttu-id="f51ca-112">Die Anmerkungen können sowohl für DiffGrams als auch für Updategrams verwendet werden. Updategrams stellen jedoch ein leistungsfähigeres Verfahren zur Verarbeitung von Identitäts- und GUID-Werten dar.</span><span class="sxs-lookup"><span data-stu-id="f51ca-112">The annotations can be used both for DiffGrams and updategrams; however, updategrams already provide a more powerful way of handling identity and GUID values.</span></span>  
  
 <span data-ttu-id="f51ca-113">Die `sql:identity`-Anmerkung und die `sql:guid`-Anmerkung können für ein komplexes Inhaltselement definiert werden.</span><span class="sxs-lookup"><span data-stu-id="f51ca-113">The `sql:identity` and `sql:guid` annotations can be defined on a complex content element.</span></span>  
  
## <a name="sqlidentity-annotation"></a><span data-ttu-id="f51ca-114">'sql:identity'-Anmerkung</span><span class="sxs-lookup"><span data-stu-id="f51ca-114">sql:identity Annotation</span></span>  
 <span data-ttu-id="f51ca-115">Sie können die `sql:identity`-Anmerkung im XSD-Schema für jeden beliebigen Knoten angeben, der einer Datenbankspalte vom Typ IDENTITY zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="f51ca-115">You can specify the `sql:identity` annotation in the XSD schema on any node that maps to an IDENTITY-type database column.</span></span> <span data-ttu-id="f51ca-116">Der für diese Anmerkung angegebene Wert definiert, wie die Identity-Type-Spalte aktualisiert wird (entweder mit dem im Update Gram angegebenen Wert, um die Spalte zu ändern, oder indem der Wert ignoriert wird. in diesem Fall wird ein von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] generierter Wert für diese Spalte verwendet).</span><span class="sxs-lookup"><span data-stu-id="f51ca-116">The value specified for this annotation defines how the IDENTITY-type column is updated (either by using the value provided in the updategram to modify the column or by ignoring the value, in which case a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-generated value is used for this column).</span></span>  
  
 <span data-ttu-id="f51ca-117">Der `sql:identity`-Anmerkung können zwei Werte zugewiesen werden:</span><span class="sxs-lookup"><span data-stu-id="f51ca-117">The `sql:identity` annotation can be assigned two values:</span></span>  
  
 <span data-ttu-id="f51ca-118">ignore</span><span class="sxs-lookup"><span data-stu-id="f51ca-118">ignore</span></span>  
 <span data-ttu-id="f51ca-119">Weist das Updategram an, einen für diese Spalte im Updategram vorhandenen Wert zu ignorieren und es [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] zu überlassen, den Identitätswert zu generieren.</span><span class="sxs-lookup"><span data-stu-id="f51ca-119">Directs the updategram to ignore any value that is provided in the updategram for that column and to rely on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to generate the identity value.</span></span>  
  
 <span data-ttu-id="f51ca-120">useValue</span><span class="sxs-lookup"><span data-stu-id="f51ca-120">useValue</span></span>  
 <span data-ttu-id="f51ca-121">Weist das Updategram an, den im Updategram angegebenen Wert zur Aktualisierung der Spalte vom Typ IDENTITY zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f51ca-121">Directs the updategram to use the value that is provided in the updategram to update the IDENTITY-type column.</span></span> <span data-ttu-id="f51ca-122">Ein Updategram prüft nicht, ob es sich bei der Spalte um eine Identitätsspalte handelt.</span><span class="sxs-lookup"><span data-stu-id="f51ca-122">An updategram does not check whether the column is an identity value or not.</span></span>  
  
 <span data-ttu-id="f51ca-123">Wenn das Updategram einen Wert für die Spalte vom Typ IDENTITY angibt, muss `sql:identity="useValue"` im Schema angegeben sein.</span><span class="sxs-lookup"><span data-stu-id="f51ca-123">If the updategram specifies a value for the IDENTITY-type column, the `sql:identity="useValue"` must be specified in the schema.</span></span>  
  
## <a name="sqlguid-annotation"></a><span data-ttu-id="f51ca-124">'sql:guid'-Anmerkung</span><span class="sxs-lookup"><span data-stu-id="f51ca-124">sql:guid Annotation</span></span>  
 <span data-ttu-id="f51ca-125">Ein Updategram kann [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] veranlassen, einen GUID-Wert zu generieren, der dann im Updategram verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f51ca-125">An updategram can have [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] generate a GUID value and then use this value in the updategram.</span></span> <span data-ttu-id="f51ca-126">Im Kontext von DiffGrams können Sie mit der `sql:guid`-Anmerkung angeben, ob ein von SQL Server generierter GUID-Wert oder der im Updategram angegebene Wert für die betreffende Spalte verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="f51ca-126">In the context of DiffGrams, you can use the `sql:guid` annotation to specify whether to use a GUID value that is generated by SQL Server or use the value that is provided in the updategram for that column.</span></span>  
  
 <span data-ttu-id="f51ca-127">Der `sql:guid`-Anmerkung können zwei Werte zugewiesen werden:</span><span class="sxs-lookup"><span data-stu-id="f51ca-127">The `sql:guid` annotation can be assigned two values:</span></span>  
  
 <span data-ttu-id="f51ca-128">generate</span><span class="sxs-lookup"><span data-stu-id="f51ca-128">generate</span></span>  
 <span data-ttu-id="f51ca-129">Gibt an, dass der von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] generierte GUID-Wert im Updatevorgang für diese Spalte verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="f51ca-129">Specifies that the GUID generated by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] be used for that column in the update operation.</span></span>  
  
 <span data-ttu-id="f51ca-130">useValue</span><span class="sxs-lookup"><span data-stu-id="f51ca-130">useValue</span></span>  
 <span data-ttu-id="f51ca-131">Gibt an, dass der im Updategram angegebene Wert für die Spalte verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="f51ca-131">Specifies that the value specified in the updategram be used for the column.</span></span> <span data-ttu-id="f51ca-132">Dies ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="f51ca-132">This is the default value.</span></span>  
  
  
