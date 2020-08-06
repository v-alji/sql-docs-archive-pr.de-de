---
title: Überlegungen zur Schema Sicherheit mit Anmerkungen (SQLXML 4,0) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- mapping schema [SQLXML], security
- annotated XDR schemas, security
- XDR schemas [SQLXML], security
- annotations [SQLXML]
- annotated XSD schemas, security
- SQLXML, annotated XSD schemas
- SQLXML, annotated XDR schemas
- security [SQLXML], annotated schemas
- XSD schemas [SQLXML], security
ms.assetid: 7d7e44dc-b6d3-4e0f-95c7-8f99930c94f2
author: rothja
ms.author: jroth
ms.openlocfilehash: 098f554410a846ed0223d17117b51025dfcf7897
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608474"
---
# <a name="annotated-schema-security-considerations-sqlxml-40"></a><span data-ttu-id="e8782-102">Überlegungen zur Sicherheit von Schemas mit Anmerkungen (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="e8782-102">Annotated Schema Security Considerations (SQLXML 4.0)</span></span>
  <span data-ttu-id="e8782-103">Im Folgenden werden Sicherheitsrichtlinien zur Verwendung von Schemas mit Anmerkungen gegeben:</span><span class="sxs-lookup"><span data-stu-id="e8782-103">The following are security guidelines for using annotated schemas:</span></span>  
  
-   <span data-ttu-id="e8782-104">Vermeiden Sie die Verwendung der Standardzuordnung in den Zuordnungsschemas.</span><span class="sxs-lookup"><span data-stu-id="e8782-104">Avoid using default mapping in the mapping schemas.</span></span> <span data-ttu-id="e8782-105">Die Standardzuordnung macht die Datenbankinformationen (Tabellen- und Spaltennamen) im resultierenden XML-Dokument verfügbar, da standardmäßig die Elementnamen den Tabellennamen und die Attributnamen den Spaltennamen zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="e8782-105">The default mapping exposes the database information (table and column names) in the resulting XML document because, by default, the element names map to table names and attribute names map to column names.</span></span> <span data-ttu-id="e8782-106">Daher hat jeder Benutzer, der das XML-Dokument einsehen kann, auch Zugriff auf die Tabellen- und Spalteninformationen in der Datenbank, was ein mögliches Sicherheitsrisiko bedeutet.</span><span class="sxs-lookup"><span data-stu-id="e8782-106">Therefore, any user who sees the XML document has access to the table and column information in the database, presenting a potential security risk.</span></span> <span data-ttu-id="e8782-107">Geben Sie daher willkürlich gewählte Element- und Attributnamen im Schema an, und verwenden Sie Anmerkungen zur expliziten Zuordnung derselben zu den Tabellen und Spalten. Auf diese Weise wird das Sicherheitsrisiko vermieden.</span><span class="sxs-lookup"><span data-stu-id="e8782-107">To avoid this risk, specify arbitrary element and attribute names in the schema and use annotations to explicitly map them to the tables and columns.</span></span> <span data-ttu-id="e8782-108">Weitere Informationen zum Verwenden der Standard Zuordnung beim Erstellen von XSD-Schemas finden Sie [unter Standard Zuordnung von XSD-Elementen und-Attributen zu Tabellen und Spalten &#40;SQLXML 4,0&#41;](../../sqlxml-annotated-xsd-schemas-using/default-mapping-of-xsd-elements-and-attributes-to-tables-and-columns-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="e8782-108">For more information about using default mapping when you create XSD schemas, see [Default Mapping of XSD Elements and Attributes to Tables and Columns &#40;SQLXML 4.0&#41;](../../sqlxml-annotated-xsd-schemas-using/default-mapping-of-xsd-elements-and-attributes-to-tables-and-columns-sqlxml-4-0.md).</span></span>  
  
-   <span data-ttu-id="e8782-109">Die mithilfe von Anmerkungen angegebene explizite Zuordnung macht die Datenbankinformationen (wie Tabellennamen und Spaltennamen) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e8782-109">The explicit mapping specified using the annotations exposes the database information (such as table names and column names).</span></span> <span data-ttu-id="e8782-110">Daher werden Sie es möglicherweise vorziehen, diese Schemas nicht öffentlich verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="e8782-110">Therefore, you may not want to make these schemas available publicly.</span></span>  
  
-   <span data-ttu-id="e8782-111">Bestimmte Abfragen wie solche, die für ein Zuordnungsschema mit Rekursion angegeben werden (mit auf einen höheren Wert festgelegter `max-depth`-Anmerkung), benötigen eventuell mehr Zeit zur Ausführung.</span><span class="sxs-lookup"><span data-stu-id="e8782-111">Certain queries such as those specified against mapping schema with recursion (specified using `max-depth` annotation set to a higher value) may take longer to execute.</span></span> <span data-ttu-id="e8782-112">Sie können optional ein Timeout Limit angeben, indem Sie die Eigenschaft Befehls Timeout (in Sekunden) festlegen.</span><span class="sxs-lookup"><span data-stu-id="e8782-112">You can optionally specify a time-out limit by setting the Command Time Out property (in seconds).</span></span> <span data-ttu-id="e8782-113">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e8782-113">For example:</span></span>  
  
    ```  
    cn.Open "Provider=SQLOLEDB;Server=localhost;Database=tempdb;Integrated Security=SSPI;Command Properties='Command Time Out=50';"  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="e8782-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e8782-114">See Also</span></span>  
 [<span data-ttu-id="e8782-115">XSD-Schemas mit Anmerkungen in SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="e8782-115">Annotated XSD Schemas in SQLXML 4.0</span></span>](../../sqlxml/annotated-xsd-schemas/annotated-xsd-schemas-in-sqlxml-4-0.md)  
  
  
