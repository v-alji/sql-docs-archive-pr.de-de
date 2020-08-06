---
title: Benutzerdefinierte Eigenschaften der XML-Quelle | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: eb29b28c-3159-41ec-b3d7-fce5b2f2be55
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5e152b23b4f59ca46cb8272ca677dc1161b3efec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621071"
---
# <a name="xml-source-custom-properties"></a><span data-ttu-id="73955-102">Benutzerdefinierte Eigenschaften der XML-Quelle</span><span class="sxs-lookup"><span data-stu-id="73955-102">XML Source Custom Properties</span></span>
  <span data-ttu-id="73955-103">Die XML-Quelle verfügt sowohl über benutzerdefinierte Eigenschaften als auch über die Eigenschaften, die allen Datenflusskomponenten gemeinsam sind.</span><span class="sxs-lookup"><span data-stu-id="73955-103">The XML source has both custom properties and the properties common to all data flow components.</span></span>  
  
 <span data-ttu-id="73955-104">In der folgenden Tabelle werden die benutzerdefinierten Eigenschaften der XML-Quelle beschrieben.</span><span class="sxs-lookup"><span data-stu-id="73955-104">The following table describes the custom properties of the XML source.</span></span> <span data-ttu-id="73955-105">Alle Eigenschaften weisen Lese-/Schreibzugriff auf.</span><span class="sxs-lookup"><span data-stu-id="73955-105">All properties are read/write.</span></span>  
  
|<span data-ttu-id="73955-106">Eigenschaftenname</span><span class="sxs-lookup"><span data-stu-id="73955-106">Property name</span></span>|<span data-ttu-id="73955-107">Datentyp</span><span class="sxs-lookup"><span data-stu-id="73955-107">Data Type</span></span>|<span data-ttu-id="73955-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="73955-108">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="73955-109">AccessMode</span><span class="sxs-lookup"><span data-stu-id="73955-109">AccessMode</span></span>|<span data-ttu-id="73955-110">Integer</span><span class="sxs-lookup"><span data-stu-id="73955-110">Integer</span></span>|<span data-ttu-id="73955-111">Der zum Zugreifen auf die XML-Daten verwendete Modus.</span><span class="sxs-lookup"><span data-stu-id="73955-111">The mode used to access the XML data.</span></span>|  
|<span data-ttu-id="73955-112">UseInlineSchema</span><span class="sxs-lookup"><span data-stu-id="73955-112">UseInlineSchema</span></span>|<span data-ttu-id="73955-113">Boolean</span><span class="sxs-lookup"><span data-stu-id="73955-113">Boolean</span></span>|<span data-ttu-id="73955-114">Ein Wert, der angibt, ob eine Inlineschemadefinition innerhalb der XML-Quelle verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="73955-114">A value that indicates whether to use an inline schema definition within the XML source.</span></span> <span data-ttu-id="73955-115">Der Standardwert dieser Eigenschaft ist `False`.</span><span class="sxs-lookup"><span data-stu-id="73955-115">The default value of this property is `False`.</span></span>|  
|<span data-ttu-id="73955-116">XMLData</span><span class="sxs-lookup"><span data-stu-id="73955-116">XMLData</span></span>|<span data-ttu-id="73955-117">String</span><span class="sxs-lookup"><span data-stu-id="73955-117">String</span></span>|<span data-ttu-id="73955-118">Die Datei oder die Variablen, aus der bzw. denen die XML-Daten abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="73955-118">The file or variables from which to retrieve the XML data.</span></span><br /><br /> <span data-ttu-id="73955-119">Der Wert dieser Eigenschaft kann mithilfe eines Eigenschaftsausdrucks angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="73955-119">The value of this property can be specified by using a property expression.</span></span>|  
|<span data-ttu-id="73955-120">XMLSchemaDefinition</span><span class="sxs-lookup"><span data-stu-id="73955-120">XMLSchemaDefinition</span></span>|<span data-ttu-id="73955-121">String</span><span class="sxs-lookup"><span data-stu-id="73955-121">String</span></span>|<span data-ttu-id="73955-122">Der Pfad und der Dateiname der Schemadefinitionsdatei (.xsd).</span><span class="sxs-lookup"><span data-stu-id="73955-122">The path and file name of the schema definition file (.xsd).</span></span><br /><br /> <span data-ttu-id="73955-123">Der Wert dieser Eigenschaft kann mithilfe eines Eigenschaftsausdrucks angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="73955-123">The value of this property can be specified by using a property expression.</span></span>|  
  
 <span data-ttu-id="73955-124">Die folgende Tabelle beschreibt die benutzerdefinierten Eigenschaften der Ausgabe der XML-Quelle.</span><span class="sxs-lookup"><span data-stu-id="73955-124">The following table describes the custom properties of the output of the XML source.</span></span> <span data-ttu-id="73955-125">Alle Eigenschaften weisen Lese-/Schreibzugriff auf.</span><span class="sxs-lookup"><span data-stu-id="73955-125">All properties are read/write.</span></span>  
  
|<span data-ttu-id="73955-126">Eigenschaftenname</span><span class="sxs-lookup"><span data-stu-id="73955-126">Property name</span></span>|<span data-ttu-id="73955-127">Datentyp</span><span class="sxs-lookup"><span data-stu-id="73955-127">Data Type</span></span>|<span data-ttu-id="73955-128">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="73955-128">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="73955-129">RowsetID</span><span class="sxs-lookup"><span data-stu-id="73955-129">RowsetID</span></span>|<span data-ttu-id="73955-130">String</span><span class="sxs-lookup"><span data-stu-id="73955-130">String</span></span>|<span data-ttu-id="73955-131">Ein Wert, der das der Ausgabe zugeordnete Rowset identifiziert.</span><span class="sxs-lookup"><span data-stu-id="73955-131">A value that identifies the rowset associated with the output.</span></span>|  
  
 <span data-ttu-id="73955-132">Die Ausgabespalten der XML-Quelle verfügen nicht über benutzerdefinierte Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="73955-132">The output columns of the XML source have no custom properties.</span></span>  
  
 <span data-ttu-id="73955-133">Weitere Informationen finden Sie unter [XML Source](xml-source.md).</span><span class="sxs-lookup"><span data-stu-id="73955-133">For more information, see [XML Source](xml-source.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73955-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="73955-134">See Also</span></span>  
 [<span data-ttu-id="73955-135">Common Properties</span><span class="sxs-lookup"><span data-stu-id="73955-135">Common Properties</span></span>](../common-properties.md)  
  
  
