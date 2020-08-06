---
title: Zwischenspeichern von Schemas (SQLXML 4,0) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- registry keys [SQLXML]
- cache [SQLXML]
- schemas [SQLXML]
ms.assetid: 7e5fda21-b435-41fd-b637-8b616560a93f
author: rothja
ms.author: jroth
ms.openlocfilehash: 4e36711955fa28bafd3b0996b1a02f6cd71f3c4f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621419"
---
# <a name="schema-caching-sqlxml-40"></a><span data-ttu-id="44bf0-102">Zwischenspeichern von Schemas (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="44bf0-102">Schema Caching (SQLXML 4.0)</span></span>
  <span data-ttu-id="44bf0-103">Bei einer parallelen Installation von XML for Microsoft SQL Server 2000 Web Release 1, Microsoft SQLXML 2.0 und SQLXML 3.0 können Sie das Zwischenspeichern von Schemas in allen Versionen mit den folgenden Registrierungsschlüsseln explizit steuern:</span><span class="sxs-lookup"><span data-stu-id="44bf0-103">With a side-by-side installation of XML for Microsoft SQL Server 2000 Web Release 1, Microsoft SQLXML 2.0, and SQLXML 3.0, you can explicitly control the schema caching in all versions by using the following registry keys:</span></span>  
  
 <span data-ttu-id="44bf0-104">Web Release 1:</span><span class="sxs-lookup"><span data-stu-id="44bf0-104">Web Release 1:</span></span>  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSSQLServer\Client\SQLXMLX\SchemaCacheSize  
```  
  
 <span data-ttu-id="44bf0-105">SQLXML 2,0:</span><span class="sxs-lookup"><span data-stu-id="44bf0-105">SQLXML 2.0:</span></span>  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSSQLServer\Client\SQLXML2\SchemaCacheSize  
```  
  
 <span data-ttu-id="44bf0-106">SQLXML 3.0:</span><span class="sxs-lookup"><span data-stu-id="44bf0-106">SQLXML 3.0:</span></span>  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSSQLServer\Client\SQLXML3\SchemaCacheSize  
```  
  
> [!CAUTION]  
>  [!INCLUDE[ssNoteRegistry](../../../includes/ssnoteregistry-md.md)]  
  
 <span data-ttu-id="44bf0-107">Weitere Informationen zur parallelen Installation finden Sie unter [What es New in SQLXML 4,0 SP1](../../sqlxml/what-s-new-in-sqlxml-4-0-sp1.md).</span><span class="sxs-lookup"><span data-stu-id="44bf0-107">For more information about side-by-side installation, see [What's New in SQLXML 4.0 SP1](../../sqlxml/what-s-new-in-sqlxml-4-0-sp1.md).</span></span>  
  
 <span data-ttu-id="44bf0-108">Das Zwischenspeichern von Schemas verbessert die Leistung einer XPath-Abfrage deutlich.</span><span class="sxs-lookup"><span data-stu-id="44bf0-108">Schema caching significantly improves the performance of an XPath query.</span></span> <span data-ttu-id="44bf0-109">Wenn eine XPath-Abfrage für ein Zuordnungsschema ausgeführt wird, wird das Schema im Arbeitsspeicher gespeichert und werden die notwendigen Datenstrukturen im Arbeitsspeicher erstellt.</span><span class="sxs-lookup"><span data-stu-id="44bf0-109">When an XPath query is executed against a mapping schema, the schema is stored in memory, and the necessary data structures are built in memory.</span></span> <span data-ttu-id="44bf0-110">Wenn das Zwischenspeichern von Schemas festgelegt ist, bleibt das Schema im Arbeitsspeicher und verbessert dadurch die Leistung für nachfolgende XPath-Abfragen.</span><span class="sxs-lookup"><span data-stu-id="44bf0-110">If schema caching is set, the schema remains in memory, thereby improving performance for subsequent XPath queries.</span></span>  
  
 <span data-ttu-id="44bf0-111">Sie können die Größe des Schemacache durch Hinzufügen des oben angegebenen Schlüssels in der Registrierung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="44bf0-111">You can set the schema cache size by adding the above key in the registry</span></span>  
  
 <span data-ttu-id="44bf0-112">Die Schemagröße wird basierend auf dem zur Verfügung stehenden Arbeitsspeicher und der Anzahl von Schemas festgelegt, die Sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="44bf0-112">The schema size is set based on the available memory and the number of schemas you are using.</span></span> <span data-ttu-id="44bf0-113">Die Standardgröße von **SchemaCacheSize** beträgt 31.</span><span class="sxs-lookup"><span data-stu-id="44bf0-113">The default **SchemaCacheSize** size is 31.</span></span> <span data-ttu-id="44bf0-114">Wenn Sie **SchemaCacheSize** höher festlegen, wird mehr Arbeitsspeicher verwendet.</span><span class="sxs-lookup"><span data-stu-id="44bf0-114">If you set **SchemaCacheSize** higher, more memory is used.</span></span> <span data-ttu-id="44bf0-115">Sie können somit die Cachegröße erhöhen, wenn der Schemazugriff langsam erscheint, oder die Cachegröße verringern, wenn der Arbeitsspeicher zu gering ist.</span><span class="sxs-lookup"><span data-stu-id="44bf0-115">Therefore, you can increase the cache size if schema access seems slow, or decrease the cache size if memory is low.</span></span>  
  
 <span data-ttu-id="44bf0-116">Aus Leistungsgründen empfiehlt es sich, " **SchemaCacheSize** " auf einen höheren Wert als die Anzahl der Zuordnungsschemas festzulegen, die Sie normalerweise verwenden.</span><span class="sxs-lookup"><span data-stu-id="44bf0-116">For performance reasons, it is recommended that you set **SchemaCacheSize** higher than the number of mapping schemas you usually use.</span></span> <span data-ttu-id="44bf0-117">Wenn die Anzahl der Schemas zunimmt, wird die Leistung beeinträchtigt, wenn **SchemaCacheSize** kleiner ist als die Anzahl der Schemas, die Sie besitzen.</span><span class="sxs-lookup"><span data-stu-id="44bf0-117">As the number of schemas increase, if **SchemaCacheSize** is less than the number of schemas you have, the performance degrades.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="44bf0-118">Während der Entwicklung empfiehlt es sich, die Schemas nicht zwischenzuspeichern, da Änderungen an den Schemas im Zwischenspeicher erst nach zwei Minuten enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="44bf0-118">During development, it is recommended that you do not cache the schemas, because the changes to the schemas are not reflected in the cache for about two minutes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44bf0-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="44bf0-119">See Also</span></span>  
 <span data-ttu-id="44bf0-120">[Zwischenspeichern von Vorlagen &#40;SQLXML 4,0&#41;](template-caching-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="44bf0-120">[Template Caching &#40;SQLXML 4.0&#41;](template-caching-sqlxml-4-0.md) </span></span>  
 [<span data-ttu-id="44bf0-121">XSL-Caching &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="44bf0-121">XSL Caching &#40;SQLXML 4.0&#41;</span></span>](xsl-caching-sqlxml-4-0.md)  
  
  
