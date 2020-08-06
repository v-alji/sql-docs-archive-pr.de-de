---
title: Zwischenspeichern von Vorlagen, XSL und Schemas (SQLXML 4,0) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- SQLXML, caching
- cache [SQLXML]
- memory [SQLXML]
ms.assetid: 80b4fa79-243f-442c-9f22-74ad66186501
author: rothja
ms.author: jroth
ms.openlocfilehash: 4df25909cf156957908abf0691964fd66a76343a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619037"
---
# <a name="caching-templates-xsl-and-schemas-sqlxml-40"></a><span data-ttu-id="62ea9-102">Zwischenspeichern von Vorlagen, XSL und Schemas (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="62ea9-102">Caching Templates, XSL, and Schemas (SQLXML 4.0)</span></span>
  <span data-ttu-id="62ea9-103">Um die Leistung zu verbessern, unterstützt [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML 4.0 das Zwischenspeichern von Vorlagen, XSL und Schemas.</span><span class="sxs-lookup"><span data-stu-id="62ea9-103">To improve performance, [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML 4.0 supports caching templates, XSL, and schemas.</span></span>  
  
 <span data-ttu-id="62ea9-104">Alle Schemas, Vorlagen und XSL-Dateien (außer den Dateien von einem http://- oder ftp://-Speicherort) werden zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="62ea9-104">All schemas, templates, and XSL files (except the files from an http:// or ftp:// location) are cached.</span></span> <span data-ttu-id="62ea9-105">Die zwischengespeicherten Dateien bleiben im Arbeitsspeicher, während der Prozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="62ea9-105">The cached files remain in memory while the process is running.</span></span> <span data-ttu-id="62ea9-106">Wenn der Prozess beendet wird, geht der gesamte Cacheinhalt verloren.</span><span class="sxs-lookup"><span data-stu-id="62ea9-106">As the process exits, all the cache is lost.</span></span> <span data-ttu-id="62ea9-107">Wenn Sie nur einen Prozess pro Abfrage ausführen, ist der Vorteil der Zwischenspeicherung möglicherweise nicht erkennbar.</span><span class="sxs-lookup"><span data-stu-id="62ea9-107">Therefore, if you run one process per query, the caching benefit may not be noticeable.</span></span>  
  
 <span data-ttu-id="62ea9-108">Die Themen in diesem Abschnitt liefern weitere Informationen über das Zwischenspeichern:</span><span class="sxs-lookup"><span data-stu-id="62ea9-108">The topics in this section provide more information about caching.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="62ea9-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="62ea9-109">In This Section</span></span>  
 [<span data-ttu-id="62ea9-110">Zwischenspeichern von Vorlagen &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="62ea9-110">Template Caching &#40;SQLXML 4.0&#41;</span></span>](template-caching-sqlxml-4-0.md)  
 <span data-ttu-id="62ea9-111">Beschreibt einen Registrierungsschlüssel zum Zwischenspeichern von Vorlagen und stellt ihn bereit.</span><span class="sxs-lookup"><span data-stu-id="62ea9-111">Describes and provides a registry key for template caching.</span></span>  
  
 [<span data-ttu-id="62ea9-112">XSL-Caching &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="62ea9-112">XSL Caching &#40;SQLXML 4.0&#41;</span></span>](xsl-caching-sqlxml-4-0.md)  
 <span data-ttu-id="62ea9-113">Beschreibt einen Registrierungsschlüssel zum Zwischenspeichern von XSL und stellt ihn bereit.</span><span class="sxs-lookup"><span data-stu-id="62ea9-113">Describes and provides a registry key for XSL caching.</span></span>  
  
 [<span data-ttu-id="62ea9-114">Schema Caching &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="62ea9-114">Schema Caching &#40;SQLXML 4.0&#41;</span></span>](schema-caching-sqlxml-4-0.md)  
 <span data-ttu-id="62ea9-115">Erläutert Probleme der parallelen Installation in SQLXML, die beim Zwischenspeichern von Schemas auftreten können, und stellt Registrierungsschlüssel für das Zwischenspeichern von Schemas bereit.</span><span class="sxs-lookup"><span data-stu-id="62ea9-115">Discusses SQLXML side-by-side installation issues related to schema caching, and provides registry keys for schema caching.</span></span>  
  
  
