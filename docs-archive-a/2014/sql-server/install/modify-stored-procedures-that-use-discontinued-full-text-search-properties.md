---
title: Ändern gespeicherter Prozeduren, die nicht mehr unterstützte Eigenschaften der voll Text Suche verwenden Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- discontinued properties [Full-Text Search]
- stored procedures [Full-Text Search]
ms.assetid: 8d9392d9-a9ba-4378-84e4-59f516b67ddb
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 12262a588742f0e3be094e32a2a0208a85b6f28a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617471"
---
# <a name="modify-stored-procedures-that-use-discontinued-full-text-search-properties"></a><span data-ttu-id="cc9b0-102">Ändern gespeicherter Prozeduren, die nicht mehr unterstützte Volltextsuche-Eigenschaften verwenden</span><span class="sxs-lookup"><span data-stu-id="cc9b0-102">Modify stored procedures that use discontinued Full-Text Search properties</span></span>
  <span data-ttu-id="cc9b0-103">Um sicherzustellen, dass Ihre gespeicherten Prozeduren korrekt funktionieren, sollten Sie vorhandene Prozeduren bearbeiten und volltextbezogene Eigenschaften und Einstellungen entfernen, die entfernt wurden oder nicht mehr unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="cc9b0-103">To ensure that your stored procedures perform correctly, you should edit existing procedures and remove those full-text related properties and settings that have been removed or deprecated.</span></span>  
  
## <a name="component"></a><span data-ttu-id="cc9b0-104">Komponente</span><span class="sxs-lookup"><span data-stu-id="cc9b0-104">Component</span></span>  
 <span data-ttu-id="cc9b0-105">Volltextsuche</span><span class="sxs-lookup"><span data-stu-id="cc9b0-105">Full-Text Search</span></span>  
  
## <a name="description"></a><span data-ttu-id="cc9b0-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="cc9b0-106">Description</span></span>  
 <span data-ttu-id="cc9b0-107">Die folgenden Eigenschaften und Einstellungen der Volltextsuche wurden entfernt.</span><span class="sxs-lookup"><span data-stu-id="cc9b0-107">The following Full-Text Search-related properties and settings have been removed.</span></span>  
  
-   <span data-ttu-id="cc9b0-108">**DataTimeout**</span><span class="sxs-lookup"><span data-stu-id="cc9b0-108">**DataTimeout**</span></span>  
  
-   <span data-ttu-id="cc9b0-109">**ConnectTimeout**</span><span class="sxs-lookup"><span data-stu-id="cc9b0-109">**ConnectTimeout**</span></span>  
  
-   <span data-ttu-id="cc9b0-110">**Clean_up**</span><span class="sxs-lookup"><span data-stu-id="cc9b0-110">**Clean_up**</span></span>  
  
-   <span data-ttu-id="cc9b0-111">**LogSize**</span><span class="sxs-lookup"><span data-stu-id="cc9b0-111">**LogSize**</span></span>  
  
 <span data-ttu-id="cc9b0-112">Die folgenden Eigenschaften und Einstellungen der Volltextsuche wurden entfernt bzw. werden nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="cc9b0-112">The following Full-Text Search-related properties and settings have been removed or deprecated:</span></span>  
  
-   <span data-ttu-id="cc9b0-113">'Path' des Volltextkatalogs.</span><span class="sxs-lookup"><span data-stu-id="cc9b0-113">'Path' of the Full-Text Catalog.</span></span> <span data-ttu-id="cc9b0-114">Der Volltextkatalog ist ein logisches Objekt ohne einen spezifischen Dateipfad im System.</span><span class="sxs-lookup"><span data-stu-id="cc9b0-114">The Full-Text Catalog will be a logic object without a specific file path in the system.</span></span>  
  
-   <span data-ttu-id="cc9b0-115">Das Aktivieren/Deaktivieren von SP_FULLTEXT_DATABASE hat keine Wirkung mehr, da Datenbanken in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] jederzeit und standardmäßig für die Volltextsuche aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="cc9b0-115">Enable/disable in SP_FULLTEXT_DATABASE has no effect anymore as databases are enabled for Full-Text Search at all times and by default in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="cc9b0-116">Korrekturmaßnahme</span><span class="sxs-lookup"><span data-stu-id="cc9b0-116">Corrective Action</span></span>  
 <span data-ttu-id="cc9b0-117">Ändern Sie die gespeicherten Prozeduren, um diese Eigenschaften zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="cc9b0-117">Modify your stored procedures to remove these properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc9b0-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cc9b0-118">See Also</span></span>  
 [<span data-ttu-id="cc9b0-119">Arbeiten mit dem Upgrade Advisor</span><span class="sxs-lookup"><span data-stu-id="cc9b0-119">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
