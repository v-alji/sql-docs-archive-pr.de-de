---
title: XML-Eingabedateireferenz (Datenbankoptimierungsratgeber) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Database Engine Tuning Advisor [SQL Server], XML input files
- input file reference [Database Engine Tuning Advisor]
- XML input files [Database Engine Tuning Advisor]
ms.assetid: 05e5e5f0-d6df-4336-b18e-e9bc2835a766
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3bbd38299e4921db33cbaf318883c2f0a9041d92
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725177"
---
# <a name="xml-input-file-reference-database-engine-tuning-advisor"></a><span data-ttu-id="b0251-102">XML-Eingabedateireferenz (Datenbankoptimierungsratgeber)</span><span class="sxs-lookup"><span data-stu-id="b0251-102">XML Input File Reference (Database Engine Tuning Advisor)</span></span>
  [!INCLUDE[ssDE](../../includes/ssde-md.md)] <span data-ttu-id="b0251-103">-Optimierungsratgeber kann mithilfe einer XML-Eingabedatei eine Datenbank optimieren.</span><span class="sxs-lookup"><span data-stu-id="b0251-103">Tuning Advisor can use an XML input file to tune a database.</span></span> <span data-ttu-id="b0251-104">Anhand dieser XML-Datei wird festgelegt, welche Datenbanken, Tabellen, Arbeitsauslastungsdateien oder -tabellen und Optimierungsoptionen für die Optimierungssitzung verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b0251-104">This XML file designates which databases, tables, workload files or tables, and tuning options to use for the tuning session.</span></span> <span data-ttu-id="b0251-105">Außerdem können Sie mit dieser Datei eine vom Benutzer angegebene Konfiguration zum Ausführen von Was-wäre-wenn-Analysen festlegen.</span><span class="sxs-lookup"><span data-stu-id="b0251-105">You can also use this file to specify a user-specified configuration to perform "what-if" analysis.</span></span>  
  
 <span data-ttu-id="b0251-106">In XML-Eingabedateien des [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Optimierungsratgebers befinden sich hierarchisch angeordnete XML-Elemente mit Text oder anderen Elementen, die die Einstellungen der Optimierungssitzung angeben.</span><span class="sxs-lookup"><span data-stu-id="b0251-106">A [!INCLUDE[ssDE](../../includes/ssde-md.md)] Tuning Advisor XML input file contains a hierarchy of XML elements, each containing text or other elements that specify the tuning session settings.</span></span> <span data-ttu-id="b0251-107">Die XML-Eingabedatei des [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Optimierungsratgebers muss den Standards für wohlgeformte XML-Dokumente entsprechen, d. h., dass bei allen Elementnamen die Groß-/Kleinschreibung beachtet wird.</span><span class="sxs-lookup"><span data-stu-id="b0251-107">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] Tuning Advisor XML input file must conform to the standards for well-formed XML, so all element names are case sensitive.</span></span> <span data-ttu-id="b0251-108">Die Groß-/Kleinschreibung der Elemente ist wie in Pascal. Das bedeutet, dass das erste Zeichen ein Großbuchstabe und der erste Buchstabe eines nachfolgenden verketteten Worts ein Großbuchstabe ist.</span><span class="sxs-lookup"><span data-stu-id="b0251-108">Elements are specified using Pascal case, which means that the first character is uppercase and the first letter of any subsequent concatenated word is uppercase.</span></span>  
  
 <span data-ttu-id="b0251-109">Alle Elementwerte müssen den XML-Benennungskonventionen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="b0251-109">All element values must conform to XML naming conventions.</span></span> <span data-ttu-id="b0251-110">Weitere Informationen zu diesen Konventionen finden Sie unter [XML-Textinhalt](https://go.microsoft.com/fwlink/?LinkId=7614) in der MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="b0251-110">For more information about these conventions, see [XML Textual Content](https://go.microsoft.com/fwlink/?LinkId=7614) in the MSDN Library.</span></span>  
  
 <span data-ttu-id="b0251-111">Beachten Sie, dass dies keine vollständige Referenz ist.</span><span class="sxs-lookup"><span data-stu-id="b0251-111">Note that this reference is not comprehensive.</span></span> <span data-ttu-id="b0251-112">Informationen zu allen Elementen, die Sie zum Definieren von XML-Eingabedateien verwenden können, finden Sie im XML-Schema DTASchema.xsd des [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Optimierungsratgebers.</span><span class="sxs-lookup"><span data-stu-id="b0251-112">For information about all the elements you can use to define XML input, refer to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Tuning Advisor XML schema, DTASchema.xsd.</span></span>  
  
## <a name="xml-declaration"></a><span data-ttu-id="b0251-113">XML-Deklaration</span><span class="sxs-lookup"><span data-stu-id="b0251-113">XML Declaration</span></span>  
  
-   [<span data-ttu-id="b0251-114">XML-Daten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b0251-114">XML Data &#40;SQL Server&#41;</span></span>](../../relational-databases/xml/xml-data-sql-server.md)  
  
## <a name="dtaxml-root-element"></a><span data-ttu-id="b0251-115">DTAXML-Stammelement</span><span class="sxs-lookup"><span data-stu-id="b0251-115">DTAXML Root Element</span></span>  
  
-   [<span data-ttu-id="b0251-116">DTAXML-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="b0251-116">DTAXML Element &#40;DTA&#41;</span></span>](dtaxml-element-dta.md)  
  
## <a name="dtainput-elements"></a><span data-ttu-id="b0251-117">DTAInput-Elemente</span><span class="sxs-lookup"><span data-stu-id="b0251-117">DTAInput Elements</span></span>  
  
-   [<span data-ttu-id="b0251-118">DTAInput-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="b0251-118">DTAInput Element &#40;DTA&#41;</span></span>](dtainput-element-dta.md)  
  
-   [<span data-ttu-id="b0251-119">Server-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="b0251-119">Server Element &#40;DTA&#41;</span></span>](server-element-dta.md)  
  
-   [<span data-ttu-id="b0251-120">Workload-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="b0251-120">Workload Element &#40;DTA&#41;</span></span>](workload-element-dta.md)  
  
-   [<span data-ttu-id="b0251-121">TuningOptions-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="b0251-121">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)  
  
-   [<span data-ttu-id="b0251-122">Configuration-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="b0251-122">Configuration Element &#40;DTA&#41;</span></span>](configuration-element-dta.md)  
  
## <a name="server-elements"></a><span data-ttu-id="b0251-123">Serverelemente</span><span class="sxs-lookup"><span data-stu-id="b0251-123">Server Elements</span></span>  
  
-   [<span data-ttu-id="b0251-124">Name-Element für Server &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="b0251-124">Name Element for Server &#40;DTA&#41;</span></span>](name-element-for-server-dta.md)  
  
-   [<span data-ttu-id="b0251-125">Database-Element für Server &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="b0251-125">Database Element for Server &#40;DTA&#41;</span></span>](database-element-for-server-dta.md)  
  
## <a name="workload-elements"></a><span data-ttu-id="b0251-126">Arbeitsauslastungselemente</span><span class="sxs-lookup"><span data-stu-id="b0251-126">Workload Elements</span></span>  
  
-   [<span data-ttu-id="b0251-127">File-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="b0251-127">File Element &#40;DTA&#41;</span></span>](file-element-dta.md)  
  
-   [<span data-ttu-id="b0251-128">Database-Element zur Arbeitsauslastung &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="b0251-128">Database Element for Workload &#40;DTA&#41;</span></span>](database-element-for-workload-dta.md)  
  
-   [<span data-ttu-id="b0251-129">EventString-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="b0251-129">EventString Element &#40;DTA&#41;</span></span>](eventstring-element-dta.md)  
  
## <a name="tuning-options-elements"></a><span data-ttu-id="b0251-130">Optimierungsoptionselemente</span><span class="sxs-lookup"><span data-stu-id="b0251-130">Tuning Options Elements</span></span>  
  
-   [<span data-ttu-id="b0251-131">TuningTimeInMin-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="b0251-131">TuningTimeInMin Element &#40;DTA&#41;</span></span>](tuningtimeinmin-element-dta.md)  
  
-   [<span data-ttu-id="b0251-132">StorageBoundInMB-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="b0251-132">StorageBoundInMB Element &#40;DTA&#41;</span></span>](storageboundinmb-element-dta.md)  
  
-   [<span data-ttu-id="b0251-133">TestServer-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="b0251-133">TestServer Element &#40;DTA&#41;</span></span>](testserver-element-dta.md)  
  
-   [<span data-ttu-id="b0251-134">FeatureSet-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="b0251-134">FeatureSet Element &#40;DTA&#41;</span></span>](featureset-element-dta.md)  
  
-   [<span data-ttu-id="b0251-135">Partitioning-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="b0251-135">Partitioning Element &#40;DTA&#41;</span></span>](partitioning-element-dta.md)  
  
-   [<span data-ttu-id="b0251-136">DropOnlyMode-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="b0251-136">DropOnlyMode Element &#40;DTA&#41;</span></span>](droponlymode-element-dta.md)  
  
-   [<span data-ttu-id="b0251-137">KeepExisting-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="b0251-137">KeepExisting Element &#40;DTA&#41;</span></span>](keepexisting-element-dta.md)  
  
-   [<span data-ttu-id="b0251-138">OnlineIndexOperation-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="b0251-138">OnlineIndexOperation Element &#40;DTA&#41;</span></span>](onlineindexoperation-element-dta.md)  
  
-   [<span data-ttu-id="b0251-139">DatabaseToConnect-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="b0251-139">DatabaseToConnect Element &#40;DTA&#41;</span></span>](databasetoconnect-element-dta.md)  
  
## <a name="configuration-elements"></a><span data-ttu-id="b0251-140">Konfigurationselemente</span><span class="sxs-lookup"><span data-stu-id="b0251-140">Configuration Elements</span></span>  
  
-   [<span data-ttu-id="b0251-141">Server-Element für Konfiguration &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="b0251-141">Server Element for Configuration &#40;DTA&#41;</span></span>](server-element-for-configuration-dta.md)  
  
-   [<span data-ttu-id="b0251-142">Database-Element für Konfiguration &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="b0251-142">Database Element for Configuration &#40;DTA&#41;</span></span>](database-element-for-configuration-dta.md)  
  
-   [<span data-ttu-id="b0251-143">Recommendation-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="b0251-143">Recommendation Element &#40;DTA&#41;</span></span>](recommendation-element-dta.md)  
  
-   [<span data-ttu-id="b0251-144">Create Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="b0251-144">Create Element &#40;DTA&#41;</span></span>](create-element-dta.md)  
  
-   [<span data-ttu-id="b0251-145">Index-Element &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="b0251-145">Index Element &#40;DTA&#41;</span></span>](index-element-dta.md)  
  
-   [<span data-ttu-id="b0251-146">Name-Element für Index &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="b0251-146">Name Element for Index &#40;DTA&#41;</span></span>](name-element-for-index-dta.md)  
  
-   [<span data-ttu-id="b0251-147">Column-Element für Index &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="b0251-147">Column Element for Index &#40;DTA&#41;</span></span>](column-element-for-index-dta.md)  
  
-   [<span data-ttu-id="b0251-148">Name-Element für Spalte &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="b0251-148">Name Element for Column &#40;DTA&#41;</span></span>](name-element-for-column-dta.md)  
  
-   [<span data-ttu-id="b0251-149">Filegroup-Element für Index &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="b0251-149">Filegroup Element for Index &#40;DTA&#41;</span></span>](filegroup-element-for-index-dta.md)  
  
## <a name="database-elements"></a><span data-ttu-id="b0251-150">Datenbankelemente</span><span class="sxs-lookup"><span data-stu-id="b0251-150">Database Elements</span></span>  
  
-   [<span data-ttu-id="b0251-151">Name-Element für Datenbank &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="b0251-151">Name Element for Database &#40;DTA&#41;</span></span>](name-element-for-database-dta.md)  
  
-   [<span data-ttu-id="b0251-152">Schema-Element für Datenbank &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="b0251-152">Schema Element for Database &#40;DTA&#41;</span></span>](schema-element-for-database-dta.md)  
  
-   [<span data-ttu-id="b0251-153">Name-Element für Schema &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="b0251-153">Name Element for Schema &#40;DTA&#41;</span></span>](name-element-for-schema-dta.md)  
  
-   [<span data-ttu-id="b0251-154">Table-Element für Schema &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="b0251-154">Table Element for Schema &#40;DTA&#41;</span></span>](table-element-for-schema-dta.md)  
  
-   [<span data-ttu-id="b0251-155">Name-Element für Tabelle &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="b0251-155">Name Element for Table &#40;DTA&#41;</span></span>](name-element-for-table-dta.md)  
  
## <a name="see-also"></a><span data-ttu-id="b0251-156">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b0251-156">See Also</span></span>  
 [<span data-ttu-id="b0251-157">Datenbankoptimierungsratgeber</span><span class="sxs-lookup"><span data-stu-id="b0251-157">Database Engine Tuning Advisor</span></span>](../../relational-databases/performance/database-engine-tuning-advisor.md)  
  
  
