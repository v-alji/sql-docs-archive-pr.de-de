---
title: Verschieben von Data Mining-Objekten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining [Analysis Services], models
- data mining editor [Analysis Services]
- mining models [Analysis Services], managing
- Data Mining Designer
- mining models [Analysis Services], modifying
ms.assetid: bc108407-2603-4387-b930-b5bb9df78069
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2b10be3a79487376b173eab87059404b7f7a618e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696326"
---
# <a name="moving-data-mining-objects"></a><span data-ttu-id="1d2e8-102">Verschieben von Data Mining-Objekten</span><span class="sxs-lookup"><span data-stu-id="1d2e8-102">Moving Data Mining Objects</span></span>
  <span data-ttu-id="1d2e8-103">Die häufigsten Szenarien beim Verschieben von Data Mining-Objekten sind das Bereitstellen eines Modells aus einer Test- oder Analyseumgebung in einer Produktionsumgebung oder die Freigabe von Modellen an andere Benutzer.</span><span class="sxs-lookup"><span data-stu-id="1d2e8-103">The most common scenarios for moving data mining objects are to deploy a model from a testing or analysis environment to a production environment, or to share models with other users.</span></span>  
  
 <span data-ttu-id="1d2e8-104">In diesem Thema wird beschrieben, wie Sie die Tools und Skripterstellungssprachen aus [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]zum Verschieben von Data Mining-Objekten verwenden können.</span><span class="sxs-lookup"><span data-stu-id="1d2e8-104">This topic describes how you can use the tools and scripting languages provided by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], for moving data mining objects.</span></span>  
  
## <a name="moving-data-mining-objects-between-databases-or-servers"></a><span data-ttu-id="1d2e8-105">Verschieben von Data Mining-Objekten zwischen Datenbanken oder Servern</span><span class="sxs-lookup"><span data-stu-id="1d2e8-105">Moving Data Mining Objects between Databases or Servers</span></span>  
 <span data-ttu-id="1d2e8-106">Sie können Data Mining-Objekte zwischen [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbanken oder Instanzen von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] auf folgende Weise verschieben:</span><span class="sxs-lookup"><span data-stu-id="1d2e8-106">You can move data mining objects between [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] databases or between instances of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] in the following ways:</span></span>  
  
-   <span data-ttu-id="1d2e8-107">Erneutes Bereitstellen der Lösung an eine andere Datenbank.</span><span class="sxs-lookup"><span data-stu-id="1d2e8-107">Re-deploying the solution to a different database.</span></span>  
  
-   <span data-ttu-id="1d2e8-108">Skripterstellung einzelne Objekte.</span><span class="sxs-lookup"><span data-stu-id="1d2e8-108">Scripting individual objects.</span></span>  
  
-   <span data-ttu-id="1d2e8-109">Sichern und anschließendes Wiederherstellen einer Kopie der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="1d2e8-109">Backing up and then restoring a copy of the database.</span></span>  
  
-   <span data-ttu-id="1d2e8-110">Exportieren und Importieren von Strukturen und Modellen.</span><span class="sxs-lookup"><span data-stu-id="1d2e8-110">Exporting and importing structures and models.</span></span>  
  
 <span data-ttu-id="1d2e8-111">Im folgenden Abschnitt werden diese Optionen ausführlich erläutert.</span><span class="sxs-lookup"><span data-stu-id="1d2e8-111">The following section explains these options in more detail.</span></span>  
  
### <a name="deploying"></a><span data-ttu-id="1d2e8-112">Wird bereitgestellt</span><span class="sxs-lookup"><span data-stu-id="1d2e8-112">Deploying</span></span>  
 <span data-ttu-id="1d2e8-113">Für die Bereitstellung der Projektmappe auf einem anderen Server bzw. einer anderen Datenbank benötigen Sie die Projektmappendatei, die mit [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="1d2e8-113">Deploying the solution to a different server or database requires that you have the solution file that was created by using [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="1d2e8-114">Weitere Informationen zur Bereitstellung von Analysis Services-Projektmappen finden Sie unter [Bereitstellen von Analysis Services-Projekten &#40;SSDT&#41;](../multidimensional-models/deploy-analysis-services-projects-ssdt.md).</span><span class="sxs-lookup"><span data-stu-id="1d2e8-114">For more information about deploying Analysis Services solutions, see [Deploy Analysis Services Projects &#40;SSDT&#41;](../multidimensional-models/deploy-analysis-services-projects-ssdt.md).</span></span>  
  
### <a name="scripting"></a><span data-ttu-id="1d2e8-115">Skripterstellung</span><span class="sxs-lookup"><span data-stu-id="1d2e8-115">Scripting</span></span>  
 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="1d2e8-116">stellt mehrere Sprachen bereit, mit denen Sie Skripte für Objekte erstellen können.</span><span class="sxs-lookup"><span data-stu-id="1d2e8-116">provides several languages that you can use to script objects.</span></span>  
  
-   <span data-ttu-id="1d2e8-117">**XMLA:** Sie können Objekte mit XMLA schreiben, indem Sie mit der rechten Maustaste auf Objekte in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]klicken.</span><span class="sxs-lookup"><span data-stu-id="1d2e8-117">**XMLA**: You can script objects using XMLA by right-clicking objects in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="1d2e8-118">Um das Skript auszuführen, öffnen Sie es in einem **XMLA-Abfrage** -Fenster auf dem Zielserver.</span><span class="sxs-lookup"><span data-stu-id="1d2e8-118">To execute the script, open it in an **XMLA Query** window on the target server.</span></span>  
  
-   <span data-ttu-id="1d2e8-119">**DMX**: Sie können Skripte anhand von Vorlagen oder einem der Abfrage-Generatoren erstellen, die in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] und [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="1d2e8-119">**DMX**: You can create scripts by using templates or one of the query builders provided in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] and [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="1d2e8-120">Beachten Sie jedoch, dass es Unterschiede in den Aufgaben gibt, die Sie mit den einzelnen Skripterstellungssprachen ausführen können:</span><span class="sxs-lookup"><span data-stu-id="1d2e8-120">Note, however, that there are differences in the tasks that you can perform with each scripting language:</span></span>  
  
-   <span data-ttu-id="1d2e8-121">Eigenschaften wie Objektbeschreibung und Datenbindungen können nur mit [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] DDL-Sprachen erstellt oder geändert werden, nicht mit DMX.</span><span class="sxs-lookup"><span data-stu-id="1d2e8-121">Properties such as the object description and data bindings can only by created or changed by using [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] DDL languages, not by using DMX.</span></span>  
  
-   <span data-ttu-id="1d2e8-122">Nur DMX unterstützt den Import und den Export von Miningobjekten.</span><span class="sxs-lookup"><span data-stu-id="1d2e8-122">Only DMX supports the import and export of mining objects.</span></span>  
  
-   <span data-ttu-id="1d2e8-123">Nur DMX unterstützt das Generieren von PMML oder Importieren von Modelldefinitionen aus PMML.</span><span class="sxs-lookup"><span data-stu-id="1d2e8-123">Only DMX supports generating PMML or importing model definitions from PMML.</span></span>  
  
-   <span data-ttu-id="1d2e8-124">Nur DMX unterstützt das Trainieren eines Modells mit Anwendungsdaten.</span><span class="sxs-lookup"><span data-stu-id="1d2e8-124">Only DMX supports training a model with application data.</span></span> <span data-ttu-id="1d2e8-125">Darüber hinaus unterstützt die DMX-Anweisung INSERT INTO das Trainieren eines Modells ohne Bereitstellung von Werten für eine Schlüsselspalte.</span><span class="sxs-lookup"><span data-stu-id="1d2e8-125">Moreover, the DMX INSERT INTO statement supports training a model without providing values for a key column.</span></span>  
  
 <span data-ttu-id="1d2e8-126">Weitere Informationen finden Sie unter [Entwickeln mit Analysis Services Scripting Language &#40;ASSL&#41;](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md).</span><span class="sxs-lookup"><span data-stu-id="1d2e8-126">For more information, see [Developing with Analysis Services Scripting Language &#40;ASSL&#41;](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md).</span></span>  
  
### <a name="backup-and-restore"></a><span data-ttu-id="1d2e8-127">Sichern und Wiederherstellen</span><span class="sxs-lookup"><span data-stu-id="1d2e8-127">Backup and Restore</span></span>  
 <span data-ttu-id="1d2e8-128">Sichern und Wiederherstellen einer gesamten Analysis Services-Datenbank bietet sich an, wenn Ihre Data Mining-Projektmappe auf OLAP-Objekten aufbaut.</span><span class="sxs-lookup"><span data-stu-id="1d2e8-128">Backup and restore of an entire Analysis Services database is the method of choice if your data mining solution relies on OLAP objects.</span></span> [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="1d2e8-129">stellt die Sicherungs- und Wiederherstellungsfunktionalität bereit, mit der Datenbanksicherungen schneller und leichter erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="1d2e8-129">provides backup and restore functionality that makes database backups faster and easier.</span></span>  
  
 <span data-ttu-id="1d2e8-130">Weitere Informationen zur Sicherung finden Sie unter [Sichern und Wiederherstellen von Analysis Services-Datenbanken](../multidimensional-models/backup-and-restore-of-analysis-services-databases.md).</span><span class="sxs-lookup"><span data-stu-id="1d2e8-130">For more information about backup, see [Backup and Restore of Analysis Services Databases](../multidimensional-models/backup-and-restore-of-analysis-services-databases.md).</span></span>  
  
### <a name="exporting-and-importing"></a><span data-ttu-id="1d2e8-131">Exportieren und Importieren</span><span class="sxs-lookup"><span data-stu-id="1d2e8-131">Exporting and Importing</span></span>  
 <span data-ttu-id="1d2e8-132">Das Exportieren und anschließende erneute Importieren von Miningmodellen und -Strukturen mit DMX-Anweisungen ist die einfachste Möglichkeit, einzelne relationale Data Mining-Objekte zu verschieben oder zu sichern.</span><span class="sxs-lookup"><span data-stu-id="1d2e8-132">Exporting and then re-importing mining models and structures by using DMX statements is the easiest way to move or back up individual relational data mining objects.</span></span> <span data-ttu-id="1d2e8-133">Weitere Informationen zur DMX-Syntax für diese Vorgänge finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="1d2e8-133">For more information about the DMX syntax for these operations, see the following topics:</span></span>  
  
-   [<span data-ttu-id="1d2e8-134">EXPORT &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="1d2e8-134">EXPORT &#40;DMX&#41;</span></span>](/sql/dmx/export-dmx)  
  
-   [<span data-ttu-id="1d2e8-135">IMPORT &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="1d2e8-135">IMPORT &#40;DMX&#41;</span></span>](/sql/dmx/import-dmx)  
  
 <span data-ttu-id="1d2e8-136">Wenn Sie die INCLUDE DEPENDENCIES-Option festlegen, exportiert [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] auch die Definition erforderlicher Datenquellensichten. Beim Importieren des Modells oder der Struktur wird die Datenquellensicht auf dem Zielserver erneut erstellt.</span><span class="sxs-lookup"><span data-stu-id="1d2e8-136">If you specify the INCLUDE DEPENDENCIES option, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] will also export the definition of any required data source views, and when you import the model or structure, it will re-create the data source view on the target server.</span></span> <span data-ttu-id="1d2e8-137">Stellen Sie nach dem Importieren des Modells sicher, dass die notwendigen Miningberechtigungen für das Objekt festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="1d2e8-137">After you have finished importing the model, make sure to set the necessary mining permissions on the object.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1d2e8-138">Sie können OLAP-Modelle nicht mit DMX exportieren und importieren.</span><span class="sxs-lookup"><span data-stu-id="1d2e8-138">You cannot export and import OLAP models by using DMX.</span></span> <span data-ttu-id="1d2e8-139">Wenn das Miningmodell auf einem OLAP-Cube basiert, müssen Sie die Funktionalität verwenden, die von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] zum Sichern und Wiederherstellen einer ganzen Datenbank bereitgestellt wird, oder den Cube und seine Modelle erneut bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="1d2e8-139">If your mining model is based on an OLAP cube, you must use the functionality provided by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] for backing up and restoring an entire database, or redeploy the cube and its models.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d2e8-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1d2e8-140">See Also</span></span>  
 [<span data-ttu-id="1d2e8-141">Verwaltung von Data Mining-Lösungen und -Objekten</span><span class="sxs-lookup"><span data-stu-id="1d2e8-141">Management of Data Mining Solutions and Objects</span></span>](management-of-data-mining-solutions-and-objects.md)  
  
  
