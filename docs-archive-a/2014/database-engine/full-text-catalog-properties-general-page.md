---
title: Voll Text Katalog-Eigenschaften (Seite "Allgemein") | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
f1_keywords:
- sql12.swb.fulltextsearch.ftcatalogproperties.general.f1
ms.assetid: d1f66762-2d40-4f24-b635-a417d22ee79a
author: rothja
ms.author: jroth
ms.openlocfilehash: 483601c53db6c8a806ea8c53f771fd4f2608293b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724097"
---
# <a name="full-text-catalog-properties-general-page"></a><span data-ttu-id="b0c07-102">Volltextkatalog-Eigenschaften (Seite 'Allgemein')</span><span class="sxs-lookup"><span data-stu-id="b0c07-102">Full-Text Catalog Properties (General Page)</span></span>
  <span data-ttu-id="b0c07-103">In diesem Abschnitt sind die auf der Seite **Allgemein** des Dialogfelds **Volltextkatalog-Eigenschaften** verfügbaren Optionen und ihre Funktionen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="b0c07-103">This section shows the options and functions available on the **General** page of the **Full-Text Catalog Properties** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b0c07-104">Im Zusammenhang mit [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] -Datenbanken ist ein Volltextkatalog ein logisches Konzept, das auf eine Gruppe von Volltextindizes verweist.</span><span class="sxs-lookup"><span data-stu-id="b0c07-104">For [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] databases, a full-text catalog is a logical concept that refers to a group of full-text indexes.</span></span> <span data-ttu-id="b0c07-105">Ein Volltextkatalog ist ein virtuelles Objekt und gehört keiner Dateigruppe an.</span><span class="sxs-lookup"><span data-stu-id="b0c07-105">The full-text catalog is a virtual object that does not belong to any filegroup.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b0c07-106">Tastatur</span><span class="sxs-lookup"><span data-stu-id="b0c07-106">Options</span></span>  
  
### <a name="properties"></a><span data-ttu-id="b0c07-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="b0c07-107">Properties</span></span>  
 <span data-ttu-id="b0c07-108">**Standardkatalog**</span><span class="sxs-lookup"><span data-stu-id="b0c07-108">**Default Catalog**</span></span>  
 <span data-ttu-id="b0c07-109">Zeigt an, ob es sich bei dem Katalog um den Standardkatalog der Datenbank handelt.</span><span class="sxs-lookup"><span data-stu-id="b0c07-109">Displays whether the catalog is the default catalog for the database.</span></span>  
  
 <span data-ttu-id="b0c07-110">**Auffüllungsstatus**</span><span class="sxs-lookup"><span data-stu-id="b0c07-110">**Population Status**</span></span>  
 <span data-ttu-id="b0c07-111">Zeigt den Status des Katalogs an.</span><span class="sxs-lookup"><span data-stu-id="b0c07-111">Indicates the status of the catalog.</span></span> <span data-ttu-id="b0c07-112">Mögliche Werte:</span><span class="sxs-lookup"><span data-stu-id="b0c07-112">Possible values are:</span></span>  
  
-   <span data-ttu-id="b0c07-113">**Gesch**</span><span class="sxs-lookup"><span data-stu-id="b0c07-113">**Idle**</span></span>  
  
-   <span data-ttu-id="b0c07-114">**Durchforstung wird ausgeführt**</span><span class="sxs-lookup"><span data-stu-id="b0c07-114">**Crawl in Progress**</span></span>  
  
-   <span data-ttu-id="b0c07-115">**Angehalten**</span><span class="sxs-lookup"><span data-stu-id="b0c07-115">**Paused**</span></span>  
  
-   <span data-ttu-id="b0c07-116">**Gedrosselt**</span><span class="sxs-lookup"><span data-stu-id="b0c07-116">**Throttled**</span></span>  
  
-   <span data-ttu-id="b0c07-117">**Meer**</span><span class="sxs-lookup"><span data-stu-id="b0c07-117">**Recovering**</span></span>  
  
-   <span data-ttu-id="b0c07-118">**Herunterfahren**</span><span class="sxs-lookup"><span data-stu-id="b0c07-118">**Shutdown**</span></span>  
  
-   <span data-ttu-id="b0c07-119">**Inkrementelles Auffüllen wird ausgeführt**</span><span class="sxs-lookup"><span data-stu-id="b0c07-119">**Incremental population in progress**</span></span>  
  
-   <span data-ttu-id="b0c07-120">**Index wird erstellt**</span><span class="sxs-lookup"><span data-stu-id="b0c07-120">**Building index**</span></span>  
  
-   <span data-ttu-id="b0c07-121">**Der Datenträger ist vollständig angehalten.**</span><span class="sxs-lookup"><span data-stu-id="b0c07-121">**Disk is full-Paused**</span></span>  
  
-   <span data-ttu-id="b0c07-122">**Änderungsnachverfolgung**</span><span class="sxs-lookup"><span data-stu-id="b0c07-122">**Change tracking**</span></span>  
  
 <span data-ttu-id="b0c07-123">**Anzahl der Elemente**</span><span class="sxs-lookup"><span data-stu-id="b0c07-123">**Item Count**</span></span>  
 <span data-ttu-id="b0c07-124">Zeigt die Anzahl der Volltextelemente im Katalog an.</span><span class="sxs-lookup"><span data-stu-id="b0c07-124">Displays the number of full-text items in the catalog.</span></span>  
  
 <span data-ttu-id="b0c07-125">**Kataloggröße**</span><span class="sxs-lookup"><span data-stu-id="b0c07-125">**Catalog Size**</span></span>  
 <span data-ttu-id="b0c07-126">Zeigt die Größe des Volltextkatalogs in Megabyte an.</span><span class="sxs-lookup"><span data-stu-id="b0c07-126">Displays the size, in megabytes, of the full-text catalog.</span></span>  
  
 <span data-ttu-id="b0c07-127">**Name**</span><span class="sxs-lookup"><span data-stu-id="b0c07-127">**Name**</span></span>  
 <span data-ttu-id="b0c07-128">Name des Volltextkatalogs.</span><span class="sxs-lookup"><span data-stu-id="b0c07-128">The name of the full-text catalog.</span></span>  
  
 <span data-ttu-id="b0c07-129">**Unterscheidung nach Akzent**</span><span class="sxs-lookup"><span data-stu-id="b0c07-129">**Accent Sensitive**</span></span>  
 <span data-ttu-id="b0c07-130">Anzeigen oder ändern, ob der Katalog von diakritischen Zeichen unterschieden wird, z. b. eine Tilde ( **~** ),**´**ein akritisches Akzentzeichen (.**¨**) oder Umlaut (".").</span><span class="sxs-lookup"><span data-stu-id="b0c07-130">View or modify whether the catalog is sensitive to diacritical marks, such as a tilde (**~**), acute accent mark (**´**), or umlaut (**¨**).</span></span> <span data-ttu-id="b0c07-131">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="b0c07-131">Valid values are:</span></span>  
  
-   <span data-ttu-id="b0c07-132">**No**</span><span class="sxs-lookup"><span data-stu-id="b0c07-132">**No**</span></span>  
  
-   <span data-ttu-id="b0c07-133">**Ja**</span><span class="sxs-lookup"><span data-stu-id="b0c07-133">**Yes**</span></span>  
  
-   <span data-ttu-id="b0c07-134">Informationen zu diakritischen Markierungen finden Sie unter [diakritische](https://www.merriam-webster.com/dictionary/diacritic) Zeichen im Merriam-Webster-Wörterbuch.</span><span class="sxs-lookup"><span data-stu-id="b0c07-134">For information about diacritical marks, see [Diacritic](https://www.merriam-webster.com/dictionary/diacritic) in the Merriam-Webster dictionary.</span></span>  
  
 <span data-ttu-id="b0c07-135">**Letzte Auffüllung am**</span><span class="sxs-lookup"><span data-stu-id="b0c07-135">**Last Population Date**</span></span>  
 <span data-ttu-id="b0c07-136">Zeigt das Datum an, an dem der Katalog zuletzt aufgefüllt wurde.</span><span class="sxs-lookup"><span data-stu-id="b0c07-136">Displays the date the catalog was last populated.</span></span>  
  
 <span data-ttu-id="b0c07-137">**Besitzer**</span><span class="sxs-lookup"><span data-stu-id="b0c07-137">**Owner**</span></span>  
 <span data-ttu-id="b0c07-138">Der Besitzer des Volltextkatalogs.</span><span class="sxs-lookup"><span data-stu-id="b0c07-138">The owner of the full-text catalog.</span></span>  
  
 <span data-ttu-id="b0c07-139">**Anzahl eindeutiger Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="b0c07-139">**Unique Key Count**</span></span>  
 <span data-ttu-id="b0c07-140">Anzahl eindeutiger Wörter, aus denen der Volltextindex für den Katalog besteht.</span><span class="sxs-lookup"><span data-stu-id="b0c07-140">The number of unique words that make up the full-text index for the catalog.</span></span>  
  
### <a name="catalog-action"></a><span data-ttu-id="b0c07-141">Katalogaktion</span><span class="sxs-lookup"><span data-stu-id="b0c07-141">Catalog Action</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b0c07-142">**None**</span><span class="sxs-lookup"><span data-stu-id="b0c07-142">**None**</span></span>|<span data-ttu-id="b0c07-143">Führt keinen der folgenden Vorgänge aus: **Katalog optimieren**, **Katalog neu erstellen**und **Katalog neu auffüllen** .</span><span class="sxs-lookup"><span data-stu-id="b0c07-143">Does not perform **Optimize catalog**, **Rebuild catalog**, or **Repopulate catalog** operations.</span></span>|  
|<span data-ttu-id="b0c07-144">**Katalog optimieren**</span><span class="sxs-lookup"><span data-stu-id="b0c07-144">**Optimize catalog**</span></span>|<span data-ttu-id="b0c07-145">Optimiert die Speicherplatzausnutzung des Katalogs und verbessert die Abfrageleistung.</span><span class="sxs-lookup"><span data-stu-id="b0c07-145">Optimizes the space utilization of the catalog and improves query performance.</span></span> <span data-ttu-id="b0c07-146">Erhöht außerdem die Genauigkeit der Relevanzbewertung von Suchergebnissen.</span><span class="sxs-lookup"><span data-stu-id="b0c07-146">It also improves the accuracy of relevance ranking of search results.</span></span><br /><br /> <span data-ttu-id="b0c07-147">Diese Aktion führt ALTER FULLTEXT CATALOG *catalog_name* REORGANIZE aus.</span><span class="sxs-lookup"><span data-stu-id="b0c07-147">This action executes ALTER FULLTEXT CATALOG *catalog_name* REORGANIZE.</span></span>|  
|<span data-ttu-id="b0c07-148">**Katalog neu erstellen**</span><span class="sxs-lookup"><span data-stu-id="b0c07-148">**Rebuild catalog**</span></span>|<span data-ttu-id="b0c07-149">Löscht den Volltextkatalog und erstellt ihn neu.</span><span class="sxs-lookup"><span data-stu-id="b0c07-149">Deletes and rebuilds the full-text catalog.</span></span> <span data-ttu-id="b0c07-150">Dieser Vorgang muss bei der Änderung einer grundlegenden Katalogeigenschaft, z. B. der Akzentunterscheidung, ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b0c07-150">This operation must be performed if a fundamental catalog property is changed, such as accent sensitivity.</span></span><br /><br /> <span data-ttu-id="b0c07-151">Damit die Neuerstellung erfolgreich ist, muss die Dateigruppe, in der sich der Volltextkatalog befindet, online oder les- und beschreibbar sein.</span><span class="sxs-lookup"><span data-stu-id="b0c07-151">For the rebuild to succeed, the filegroup the full-text catalog resides in must be online or read-writeable.</span></span> <span data-ttu-id="b0c07-152">Nach der Neuerstellung wird der Volltextindex neu aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="b0c07-152">After the rebuild, the full-text index will be repopulated.</span></span><br /><br /> <span data-ttu-id="b0c07-153">Diese Aktion führt ALTER FULLTEXT CATALOG *catalog_name* REBUILD aus.</span><span class="sxs-lookup"><span data-stu-id="b0c07-153">This action executes ALTER FULLTEXT CATALOG *catalog_name* REBUILD.</span></span>|  
|<span data-ttu-id="b0c07-154">**Katalog neu auffüllen**</span><span class="sxs-lookup"><span data-stu-id="b0c07-154">**Repopulate catalog**</span></span>|<span data-ttu-id="b0c07-155">Aktualisiert den Katalog entsprechend den kürzlich vorgenommenen Datenänderungen.</span><span class="sxs-lookup"><span data-stu-id="b0c07-155">Updates the catalog with recent changes to the data.</span></span> <span data-ttu-id="b0c07-156">Diese Option hat keine Katalogausfallzeit zur Folge.</span><span class="sxs-lookup"><span data-stu-id="b0c07-156">This option does require catalog downtime.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b0c07-157">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b0c07-157">See Also</span></span>  
 [<span data-ttu-id="b0c07-158">Auffüllen von Volltextindizes</span><span class="sxs-lookup"><span data-stu-id="b0c07-158">Populate Full-Text Indexes</span></span>](../relational-databases/indexes/indexes.md)  
  
  
