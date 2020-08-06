---
title: ASSL-Objekte und-Objekteigenschaften | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- reference exceptions [Analysis Services Scripting Language]
- ASSL, objects
- inheritance [Analysis Services Scripting Language]
- localized names [Analysis Services Scripting Language]
- objects [Analysis Services Scripting Language]
- names [Analysis Services Scripting Language]
- Analysis Services Scripting Language, objects
- expansion [Analysis Services Scripting Language]
ms.assetid: 6e5c28b5-c0bc-4ccd-82e5-e174bbb71386
author: minewiskan
ms.author: owend
ms.openlocfilehash: 76d57bb421a7f486983476a6549a5121ce88ee9b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620023"
---
# <a name="assl-objects-and-object-characteristics"></a><span data-ttu-id="97c69-102">ASSL-Objekte und -Objekteigenschaften</span><span class="sxs-lookup"><span data-stu-id="97c69-102">ASSL Objects and Object Characteristics</span></span>
  <span data-ttu-id="97c69-103">Objekte in Analysis Services Scripting Language (ASSL) folgen spezifischen Richtlinien in Bezug auf Objektgruppen, Vererbung, Benennung, Erweiterung und Verarbeitung.</span><span class="sxs-lookup"><span data-stu-id="97c69-103">Objects in Analysis Services Scripting Language (ASSL) follow specific guidelines in regards to object groups, inheritance, naming, expansion, and processing.</span></span>  
  
## <a name="object-groups"></a><span data-ttu-id="97c69-104">Objektgruppen</span><span class="sxs-lookup"><span data-stu-id="97c69-104">Object Groups</span></span>  
 <span data-ttu-id="97c69-105">Alle- [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] Objekte weisen eine XML-Darstellung auf.</span><span class="sxs-lookup"><span data-stu-id="97c69-105">All [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] objects have an XML representation.</span></span> <span data-ttu-id="97c69-106">Die Objekte sind in zwei Gruppen unterteilt:</span><span class="sxs-lookup"><span data-stu-id="97c69-106">The objects are divided into two groups:</span></span>  
  
 <span data-ttu-id="97c69-107">**Hauptobjekte**</span><span class="sxs-lookup"><span data-stu-id="97c69-107">**Major objects**</span></span>  
 <span data-ttu-id="97c69-108">Hauptobjekte können unabhängig erstellt, geändert und gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="97c69-108">Major objects can be independently created, altered, and deleted.</span></span> <span data-ttu-id="97c69-109">Zu den Hauptobjekten gehören:</span><span class="sxs-lookup"><span data-stu-id="97c69-109">Major objects include:</span></span>  
  
-   <span data-ttu-id="97c69-110">Server</span><span class="sxs-lookup"><span data-stu-id="97c69-110">Servers</span></span>  
  
-   <span data-ttu-id="97c69-111">Datenbanken</span><span class="sxs-lookup"><span data-stu-id="97c69-111">Databases</span></span>  
  
-   <span data-ttu-id="97c69-112">Dimensionen</span><span class="sxs-lookup"><span data-stu-id="97c69-112">Dimensions</span></span>  
  
-   <span data-ttu-id="97c69-113">Cubes</span><span class="sxs-lookup"><span data-stu-id="97c69-113">Cubes</span></span>  
  
-   <span data-ttu-id="97c69-114">Measuregruppen</span><span class="sxs-lookup"><span data-stu-id="97c69-114">Measure groups</span></span>  
  
-   <span data-ttu-id="97c69-115">Partitionen</span><span class="sxs-lookup"><span data-stu-id="97c69-115">Partitions</span></span>  
  
-   <span data-ttu-id="97c69-116">Perspektiven</span><span class="sxs-lookup"><span data-stu-id="97c69-116">Perspectives</span></span>  
  
-   <span data-ttu-id="97c69-117">Miningmodelle</span><span class="sxs-lookup"><span data-stu-id="97c69-117">Mining models</span></span>  
  
-   <span data-ttu-id="97c69-118">Rollen</span><span class="sxs-lookup"><span data-stu-id="97c69-118">Roles</span></span>  
  
-   <span data-ttu-id="97c69-119">Einem Server oder einer Datenbank zugeordnete Befehle</span><span class="sxs-lookup"><span data-stu-id="97c69-119">Commands associated with a server or database</span></span>  
  
-   <span data-ttu-id="97c69-120">Datenquellen</span><span class="sxs-lookup"><span data-stu-id="97c69-120">Data sources</span></span>  
  
 <span data-ttu-id="97c69-121">Hauptobjekte haben die folgenden Eigenschaften, um ihren Verlauf und Status nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="97c69-121">Major objects have the following properties to track their history and status.</span></span>  
  
-   `CreatedTimestamp`  
  
-   `LastSchemaUpdate`  
  
-   <span data-ttu-id="97c69-122">`LastProcessed` (wenn geeignet)</span><span class="sxs-lookup"><span data-stu-id="97c69-122">`LastProcessed` (where appropriate)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="97c69-123">Die Klassifizierung eines Objekts als Hauptobjekt wirkt sich darauf aus, wie eine Instanz von [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] dieses Objekt behandelt und wie es in der Objektdefinitionssprache gehandhabt wird.</span><span class="sxs-lookup"><span data-stu-id="97c69-123">The classification of an object as a major object affects how an instance of [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] treats that object and how that object is handled in the object definition language.</span></span> <span data-ttu-id="97c69-124">Diese Klassifizierung ist jedoch keine Garantie dafür, dass [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] -Tools für die Verwaltung und Entwicklung das unabhängige Erstellen, Bearbeiten oder Löschen dieser Objekte zulassen.</span><span class="sxs-lookup"><span data-stu-id="97c69-124">However, this classification does not guarantee that [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] management and development tools will allow the independent creation, modification, or deletion of these objects.</span></span>  
  
 <span data-ttu-id="97c69-125">**Nebenobjekte**</span><span class="sxs-lookup"><span data-stu-id="97c69-125">**Minor objects**</span></span>  
 <span data-ttu-id="97c69-126">Nebenobjekte sind Objekte, die nur im Rahmen des Erstellens, Änderns oder Löschens des übergeordneten Hauptobjekts erstellt, geändert oder gelöscht werden können.</span><span class="sxs-lookup"><span data-stu-id="97c69-126">Minor objects can only be created, altered, or deleted as part of creating, altering, or deleting the parent major object.</span></span> <span data-ttu-id="97c69-127">Zu den Nebenobjekten gehören:</span><span class="sxs-lookup"><span data-stu-id="97c69-127">Minor objects include:</span></span>  
  
-   <span data-ttu-id="97c69-128">Hierarchien und Ebenen</span><span class="sxs-lookup"><span data-stu-id="97c69-128">Hierarchies and levels</span></span>  
  
-   <span data-ttu-id="97c69-129">Attribute</span><span class="sxs-lookup"><span data-stu-id="97c69-129">Attributes</span></span>  
  
-   <span data-ttu-id="97c69-130">Measures</span><span class="sxs-lookup"><span data-stu-id="97c69-130">Measures</span></span>  
  
-   <span data-ttu-id="97c69-131">Miningmodellspalten</span><span class="sxs-lookup"><span data-stu-id="97c69-131">Mining model columns</span></span>  
  
-   <span data-ttu-id="97c69-132">Einem Cube zugeordnete Befehle</span><span class="sxs-lookup"><span data-stu-id="97c69-132">Commands associated with a cube</span></span>  
  
-   <span data-ttu-id="97c69-133">Aggregationen</span><span class="sxs-lookup"><span data-stu-id="97c69-133">Aggregations</span></span>  
  
## <a name="object-expansion"></a><span data-ttu-id="97c69-134">ObjectExpansion</span><span class="sxs-lookup"><span data-stu-id="97c69-134">Object Expansion</span></span>  
 <span data-ttu-id="97c69-135">Mit der `ObjectExpansion`-Beschränkung kann der Grad der Erweiterung des vom Server zurückgegebenen ASSL XML-Werts festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="97c69-135">The `ObjectExpansion` restriction can be used to control the degree of expansion of ASSL XML returned by the server.</span></span> <span data-ttu-id="97c69-136">Für diese Beschränkung sind die in der folgenden Tabelle aufgeführten Optionen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="97c69-136">This restriction has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="97c69-137">Enumerationswert</span><span class="sxs-lookup"><span data-stu-id="97c69-137">Enumeration value</span></span>|<span data-ttu-id="97c69-138">Zulässig für\<Alter></span><span class="sxs-lookup"><span data-stu-id="97c69-138">Allowed for \<Alter></span></span>|<span data-ttu-id="97c69-139">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="97c69-139">Description</span></span>|  
|-----------------------|---------------------------|-----------------|  
|<span data-ttu-id="97c69-140">*ReferenceOnly*</span><span class="sxs-lookup"><span data-stu-id="97c69-140">*ReferenceOnly*</span></span>|<span data-ttu-id="97c69-141">nein</span><span class="sxs-lookup"><span data-stu-id="97c69-141">no</span></span>|<span data-ttu-id="97c69-142">Gibt nur den Namen, die ID und den Timestamp für das angeforderte Objekt und alle enthaltenen Hauptobjekte rekursiv zurück.</span><span class="sxs-lookup"><span data-stu-id="97c69-142">Returns only the name, ID, and timestamp for the requested object and for all contained major objects recursively.</span></span>|  
|<span data-ttu-id="97c69-143">*ObjectProperties*</span><span class="sxs-lookup"><span data-stu-id="97c69-143">*ObjectProperties*</span></span>|<span data-ttu-id="97c69-144">ja</span><span class="sxs-lookup"><span data-stu-id="97c69-144">yes</span></span>|<span data-ttu-id="97c69-145">Erweitert das angeforderte Objekt und die enthaltenen Nebenobjekte, aber gibt keine enthaltenen Hauptobjekte zurück.</span><span class="sxs-lookup"><span data-stu-id="97c69-145">Expands the requested object and minor contained objects, but does not return major contained objects.</span></span>|  
|<span data-ttu-id="97c69-146">*ExpandObject*</span><span class="sxs-lookup"><span data-stu-id="97c69-146">*ExpandObject*</span></span>|<span data-ttu-id="97c69-147">nein</span><span class="sxs-lookup"><span data-stu-id="97c69-147">no</span></span>|<span data-ttu-id="97c69-148">Wie *ObjectProperties*, gibt jedoch auch den Namen, die ID und den Timestamp für enthaltene Hauptobjekte zurück.</span><span class="sxs-lookup"><span data-stu-id="97c69-148">Same as *ObjectProperties*, but also returns the name, ID, and timestamp for contained major objects.</span></span>|  
|<span data-ttu-id="97c69-149">*ExpandFull*</span><span class="sxs-lookup"><span data-stu-id="97c69-149">*ExpandFull*</span></span>|<span data-ttu-id="97c69-150">ja</span><span class="sxs-lookup"><span data-stu-id="97c69-150">yes</span></span>|<span data-ttu-id="97c69-151">Erweitert das angeforderte Objekt und alle enthaltenen Objekte vollständig und rekursiv.</span><span class="sxs-lookup"><span data-stu-id="97c69-151">Fully expands the requested object and all contained objects recursively.</span></span>|  
  
 <span data-ttu-id="97c69-152">In diesem ASSL-Verweisabschnitt wird die *ExpandFull* -Darstellung beschrieben.</span><span class="sxs-lookup"><span data-stu-id="97c69-152">This ASSL reference section describes the *ExpandFull* representation.</span></span> <span data-ttu-id="97c69-153">Alle anderen `ObjectExpansion`-Ebenen werden von dieser Ebene abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="97c69-153">All other `ObjectExpansion` levels are derived from this level.</span></span>  
  
## <a name="object-processing"></a><span data-ttu-id="97c69-154">Objektverarbeitung</span><span class="sxs-lookup"><span data-stu-id="97c69-154">Object Processing</span></span>  
 <span data-ttu-id="97c69-155">ASSL enthält schreibgeschützte Elemente oder Eigenschaften (z. B. `LastProcessed`), die von der [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] Instanz gelesen werden können, jedoch nicht angegeben werden, wenn Befehlsskripts an die Instanz übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="97c69-155">ASSL includes read-only elements or properties (for example, `LastProcessed`) that can be read from the [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] instance, but which are omitted when command scripts are submitted to the instance.</span></span> [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] <span data-ttu-id="97c69-156">ignoriert geänderte Werte für schreibgeschützte Elemente, ohne eine Warnung oder einen Fehler auszugeben.</span><span class="sxs-lookup"><span data-stu-id="97c69-156">ignores modified values for read-only elements without warning or error.</span></span>  
  
 [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] <span data-ttu-id="97c69-157">ignoriert auch unpassende oder irrelevante Eigenschaften, ohne Überprüfungsfehler auszulösen.</span><span class="sxs-lookup"><span data-stu-id="97c69-157">also ignores inappropriate or irrelevant properties without raising validation errors.</span></span> <span data-ttu-id="97c69-158">Beispielsweise sollte das X-Element nur vorhanden sein, wenn das Y-Element einen besonderen Wert aufweist.</span><span class="sxs-lookup"><span data-stu-id="97c69-158">For example, the X element should only be present when the Y element has a particular value.</span></span> <span data-ttu-id="97c69-159">Die [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] -Instanz ignoriert das X-Element, anstatt es in Bezug auf den Wert des Y-Elements zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="97c69-159">The [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] instance ignores the X element instead of validating that element against the value of the Y element.</span></span>  
  
  
