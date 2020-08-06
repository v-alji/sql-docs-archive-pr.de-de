---
title: 'Angeben des SQL: inverse-Attributs für SQL: Relationship (SQLXML 4,0) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- sql:relationship
- bulk load [SQLXML]
- inverse attribute
- relationships [SQLXML], inverse orders
- relationship annotation
- XSD schemas [SQLXML], relationships
- annotated XSD schemas, relationships
- updategrams [SQLXML], relationships
- sql:inverse
ms.assetid: 08904cbd-9c86-493d-90c3-f5e1d13ce59d
author: rothja
ms.author: jroth
ms.openlocfilehash: 5b0781102371b98cced72a5a0edee70c9567c372
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617899"
---
# <a name="specifying-the-sqlinverse-attribute-on-sqlrelationship-sqlxml-40"></a><span data-ttu-id="959b4-102">Angeben des sql:inverse-Attributs für sql:relationship (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="959b4-102">Specifying the sql:inverse Attribute on sql:relationship (SQLXML 4.0)</span></span>
  <span data-ttu-id="959b4-103">Das `sql:inverse`-Attribut ist nur dann nützlich, wenn das XSD-Schema zum Massenladen oder von einem Updategram verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="959b4-103">The `sql:inverse` attribute is useful only when the XSD schema is used for either bulk load or by an updategram.</span></span> <span data-ttu-id="959b4-104">Das- `sql:inverse` Attribut kann für das- **\<sql:relationship>** Element angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="959b4-104">The `sql:inverse` attribute can be specified on the **\<sql:relationship>** element.</span></span> <span data-ttu-id="959b4-105">In Updategrams interpretiert die Updategramlogik das Schema beim Bestimmen der Tabellen und Spalten, die durch den Updategramvorgang aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="959b4-105">In updategrams, the updategram logic interprets the schema in determining the tables and columns that are updated by the updategram operation.</span></span> <span data-ttu-id="959b4-106">Die im Schema angegebenen Über-/Unterordnungsbeziehungen legen die Reihenfolge fest, in der die Datensätze modifiziert (eingefügt oder gelöscht) werden.</span><span class="sxs-lookup"><span data-stu-id="959b4-106">The parent-child relationships that are specified in the schema determine the order in which the records are modified (inserted or deleted).</span></span>  
  
 <span data-ttu-id="959b4-107">Wenn ein XSD-Schema gegeben ist, in dem die Über-/Unterordnungsbeziehung invers zur Primär-/Fremdschlüssel-Beziehung zwischen den zugehörigen Datenbankspalten angegeben ist, dann schlägt der Updategramvorgang zum Einfügen oder Löschen wegen der Primär-/Fremdschlüsselverletzung fehl.</span><span class="sxs-lookup"><span data-stu-id="959b4-107">If you have an XSD schema in which the parent-child relationship is specified in the inverse order of the primary-key/foreign-key relationship between the corresponding database columns, the insert or delete updategram operation will fail because of the primary-key/foreign-key violation.</span></span> <span data-ttu-id="959b4-108">In solchen Fällen wird das `sql:inverse` -Attribut ( `sql:inverse="true"` ) im **\<sql:relationship>** -Element angegeben, und die Update Gram Logik kehrt die Interpretation der im Schema angegebenen über-/Unterordnungsbeziehung um.</span><span class="sxs-lookup"><span data-stu-id="959b4-108">In such cases, the `sql:inverse` attribute is specified (`sql:inverse="true"`) in the **\<sql:relationship>** element, and the updategram logic inverses its interpretation of the parent-child relationship specified in the schema.</span></span>  
  
 <span data-ttu-id="959b4-109">Das `sql:inverse`-Attribut akzeptiert einen booleschen Wert (0 = false, 1 = true).</span><span class="sxs-lookup"><span data-stu-id="959b4-109">The `sql:inverse` attribute takes a Boolean value (0=false, 1=true).</span></span> <span data-ttu-id="959b4-110">Zulässig sind die Werte 0, 1, true und false.</span><span class="sxs-lookup"><span data-stu-id="959b4-110">The acceptable values are 0, 1, true, and false.</span></span>  
  
 <span data-ttu-id="959b4-111">Ein funktionierendes Beispiel mit der-Anmerkung `sql:inverse` finden Sie unter [Angeben eines Mapping-Schemas mit Anmerkungen in einem Update Gram](../sqlxml-annotated-xsd-schemas-xpath-queries/updategrams/specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="959b4-111">For a working sample using the `sql:inverse` annotation, see [Specifying an Annotated Mapping Schema in an Updategram](../sqlxml-annotated-xsd-schemas-xpath-queries/updategrams/specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="959b4-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="959b4-112">See Also</span></span>  
 [<span data-ttu-id="959b4-113">Angeben von Beziehungen mithilfe von ' SQL: Relationship ' &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="959b4-113">Specifying Relationships Using sql:relationship &#40;SQLXML 4.0&#41;</span></span>](specifying-relationships-using-sql-relationship-sqlxml-4-0.md)  
  
  
