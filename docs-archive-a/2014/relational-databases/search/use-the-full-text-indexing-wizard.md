---
title: Verwenden des Volltextindizierungs-Assistenten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
f1_keywords:
- sql12.swb.fulltextindexingwizard.selecttablecolumns.f1
- sql12.swb.fulltextindexingwizard.welcome.f1
- sql12.swb.fulltextindexingwizard.selectacatalog.f1
- sql12.swb.fulltextindexingwizard.progress.f1
- sql12.swb.fulltextindexingwizard.selectorcreatepopschedules.f1
- sql12.swb.fulltextindexingwizard.selectatableorview.f1
- sql12.swb.fulltextindexingwizard.selectchangetracking.f1
- sql12.swb.fulltextindexingwizard.selectanindex.f1
- sql12.swb.fulltextindexingwizard.summary.f1
helpviewer_keywords:
- Full-Text Indexing Wizard
- full-text search [SQL Server], Full-Text Indexing Wizard
ms.assetid: 3e9d9605-6525-4781-9168-fdaa06db3459
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5ef8a23c4d85cbe47bf6bdb47eb3f45723f1559d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697820"
---
# <a name="use-the-full-text-indexing-wizard"></a><span data-ttu-id="4cdbc-102">Verwenden des Volltextindizierungs-Assistenten</span><span class="sxs-lookup"><span data-stu-id="4cdbc-102">Use the Full-Text Indexing Wizard</span></span>
  <span data-ttu-id="4cdbc-103">Der Volltextindizierungs-Assistent führt Sie durch eine Reihe von Arbeitsschritten, die Ihnen das Erstellen eines Volltextindexes erleichtern.</span><span class="sxs-lookup"><span data-stu-id="4cdbc-103">The Full-Text Indexing Wizard walks you through a series of steps designed to help you create a full-text index.</span></span>  
  
#### <a name="to-use-the-full-text-indexing-wizard"></a><span data-ttu-id="4cdbc-104">So verwenden Sie den Volltextindizierungs-Assistenten</span><span class="sxs-lookup"><span data-stu-id="4cdbc-104">To use the Full-Text Indexing wizard</span></span>  
  
1.  <span data-ttu-id="4cdbc-105">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf die Tabelle, für die Sie einen Volltextindex erstellen möchten, zeigen Sie auf **Volltextindex**, und klicken Sie anschließend auf **Volltextindex definieren**.</span><span class="sxs-lookup"><span data-stu-id="4cdbc-105">In Object Explorer, right-click the table on which you want to create a full-text index, point to **Full-Text index**, and then click **Define Full-Text Index**.</span></span>  
  
     <span data-ttu-id="4cdbc-106">**Eindeutiger Index**</span><span class="sxs-lookup"><span data-stu-id="4cdbc-106">**Unique Index**</span></span>  
     <span data-ttu-id="4cdbc-107">Wählen Sie einen Index aus der Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="4cdbc-107">Select an index from the drop down list.</span></span> <span data-ttu-id="4cdbc-108">Der Index muss genau eine Schlüsselspalte haben, muss eindeutig sein und darf keine NULL-Werte zulassen.</span><span class="sxs-lookup"><span data-stu-id="4cdbc-108">The index must be a single-key-column, unique, non-nullable index.</span></span> <span data-ttu-id="4cdbc-109">Wählen Sie als eindeutigen Volltextschlüssel stets den kleinsten eindeutigen Index aus.</span><span class="sxs-lookup"><span data-stu-id="4cdbc-109">Select the smallest unique key index for the full-text unique key.</span></span> <span data-ttu-id="4cdbc-110">Für die bestmögliche Leistung ist ein gruppierter Index zu empfehlen.</span><span class="sxs-lookup"><span data-stu-id="4cdbc-110">For best performance, a clustered index is recommended.</span></span>  
  
     <span data-ttu-id="4cdbc-111">**Verfügbare Spalten**</span><span class="sxs-lookup"><span data-stu-id="4cdbc-111">**Available Columns**</span></span>  
     <span data-ttu-id="4cdbc-112">Um eine Spalte in den Index einzuschließen, aktivieren Sie das Kontrollkästchen neben dem Spaltennamen.</span><span class="sxs-lookup"><span data-stu-id="4cdbc-112">To include a column in the index, select the check box next to the column name.</span></span> <span data-ttu-id="4cdbc-113">Spalten, die für eine Volltextindizierung nicht infrage kommen, werden grau angezeigt, und die entsprechenden Kontrollkästchen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="4cdbc-113">Columns that are not eligible for full-text indexing appear in grey with their check boxes disabled.</span></span>  
  
     <span data-ttu-id="4cdbc-114">**Sprache für die Wörtertrennung**</span><span class="sxs-lookup"><span data-stu-id="4cdbc-114">**Language for Word Breaker**</span></span>  
     <span data-ttu-id="4cdbc-115">Wählen Sie eine Sprache aus der Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="4cdbc-115">Select a language from the drop-down list.</span></span> <span data-ttu-id="4cdbc-116">Diese Auswahl wird von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] verwendet, um die richtigen Wörtertrennungen für den Index zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="4cdbc-116">This choice will be used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to identify the correct word breakers for the index.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="4cdbc-117">In werden mithilfe von Wörtertrennzeichen Wortgrenzen in den volltextindizierten Daten gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="4cdbc-117">uses word breakers to identify word boundaries in the full-text indexed data.</span></span>  
  
     <span data-ttu-id="4cdbc-118">**Typspalte**</span><span class="sxs-lookup"><span data-stu-id="4cdbc-118">**Type Column**</span></span>  
     <span data-ttu-id="4cdbc-119">Wählen Sie den Namen der Spalte aus, in der der Dokumenttyp der volltextindizierten Spalte enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="4cdbc-119">Select the name of the column that holds the document type of column being full-text indexed.</span></span>  
  
     <span data-ttu-id="4cdbc-120">Die **Typspalte** ist nur aktiviert, wenn die Spalte mit dem Namen in der Spalte **Verfügbare Spalten** den Typ `varbinary(max)` oder hat `image` .</span><span class="sxs-lookup"><span data-stu-id="4cdbc-120">The  **Type Column** is only enabled when the column named in the **Available Columns** column is of type `varbinary(max)` or `image`.</span></span>  
  
     <span data-ttu-id="4cdbc-121">**Statistische Semantik**</span><span class="sxs-lookup"><span data-stu-id="4cdbc-121">**Statistical Semantics**</span></span>  
     <span data-ttu-id="4cdbc-122">Wählen Sie aus, ob die semantische Indizierung für die ausgewählte Spalte aktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="4cdbc-122">Select whether to enable semantic indexing for the selected column.</span></span> <span data-ttu-id="4cdbc-123">Weitere Informationen finden Sie unter [Semantische Suche &#40;SQL Server&#41;](semantic-search-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4cdbc-123">For more information, see [Semantic Search &#40;SQL Server&#41;](semantic-search-sql-server.md).</span></span>  
  
     <span data-ttu-id="4cdbc-124">Wenn Sie eine **Sprache** vor der Option **Statistische Semantik**auswählen und die ausgewählte Sprache über kein zugeordnetes semantisches Sprachmodell verfügt, ist das Kontrollkästchen **Statistische Semantik** deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="4cdbc-124">If you select a **Language** prior to selecting **Statistical Semantics**, and the selected language does not have an associated Semantic Language Model, then the **Statistical Semantics** checkbox is disabled.</span></span> <span data-ttu-id="4cdbc-125">Wenn Sie **Statistische Semantik** vor einer **Sprache**auswählen, werden im Dropdown-Kombinationsfeld nur die Sprachen angezeigt, für die das semantische Sprachmodell unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="4cdbc-125">If you select **Statistical Semantics** prior to selecting a **Language**, the languages available in the drop-down combo box will be restricted to those for which there is Semantic Language Model support.</span></span>  
  
2.  <span data-ttu-id="4cdbc-126">Aktivieren Sie die Optionen zur Änderungsnachverfolgung.</span><span class="sxs-lookup"><span data-stu-id="4cdbc-126">Select the change tracking options.</span></span>  
  
     <span data-ttu-id="4cdbc-127">**Automatisch**</span><span class="sxs-lookup"><span data-stu-id="4cdbc-127">**Automatically**</span></span>  
     <span data-ttu-id="4cdbc-128">Wählen Sie diese Optionsschaltfläche, wenn der Volltextindex im Falle von Änderungen an den zugrunde liegenden Daten automatisch aktualisiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="4cdbc-128">Select this radio button to have the full-text index updated automatically as changes occur to the underlying data.</span></span>  
  
     <span data-ttu-id="4cdbc-129">**Manuell**</span><span class="sxs-lookup"><span data-stu-id="4cdbc-129">**Manually**</span></span>  
     <span data-ttu-id="4cdbc-130">Wählen Sie diese Optionsschaltfläche, wenn der Volltextindex im Falle von Änderungen an den zugrunde liegenden Daten nicht automatisch aktualisiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="4cdbc-130">Select this radio button if you do not want the full-text index to be updated automatically as changes occur to the underlying data.</span></span> <span data-ttu-id="4cdbc-131">Die Änderungen an den zugrunde liegenden Daten bleiben erhalten.</span><span class="sxs-lookup"><span data-stu-id="4cdbc-131">Changes to the underlying data are maintained.</span></span> <span data-ttu-id="4cdbc-132">Um jedoch die Änderungen im Volltextindex zu berücksichtigen, müssen Sie diesen Prozess manuell oder über einen Zeitplan starten.</span><span class="sxs-lookup"><span data-stu-id="4cdbc-132">However, to apply the changes to the full-text index you must start or schedule this process manually.</span></span>  
  
     <span data-ttu-id="4cdbc-133">**Änderungen nicht nachverfolgen**</span><span class="sxs-lookup"><span data-stu-id="4cdbc-133">**Do not track changes**</span></span>  
     <span data-ttu-id="4cdbc-134">Wählen Sie diese Optionsschaltfläche, wenn der Volltextindex bei Änderungen an den zugrunde liegenden Daten nicht aktualisiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="4cdbc-134">Select this radio button if you do not want the full-text index to be updated with changes to the underlying data.</span></span>  
  
     <span data-ttu-id="4cdbc-135">**Vollständige Auffüllung bei der Indexerstellung starten**</span><span class="sxs-lookup"><span data-stu-id="4cdbc-135">**Start full population when index is created**</span></span>  
     <span data-ttu-id="4cdbc-136">Wählen Sie diese Optionsschaltfläche, um nach erfolgreichem Abschluss dieses Assistenten eine vollständige Auffüllung zu starten.</span><span class="sxs-lookup"><span data-stu-id="4cdbc-136">Select this radio button to kick off a full population at the successful completion of this wizard.</span></span> <span data-ttu-id="4cdbc-137">Dabei wird die Volltext-Indexstruktur im Katalog erstellt und der Katalog mit volltextindizierten Daten aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="4cdbc-137">This will consist of creating the full-text index structure in the catalog and populating it with full-text indexed data.</span></span>  
  
3.  <span data-ttu-id="4cdbc-138">Wählen Sie den Katalog, die Indexdateigruppe und die Stoppliste aus.</span><span class="sxs-lookup"><span data-stu-id="4cdbc-138">Select the catalog, index filegroup and stoplist.</span></span>  
  
     <span data-ttu-id="4cdbc-139">**Volltextkatalog auswählen**</span><span class="sxs-lookup"><span data-stu-id="4cdbc-139">**Select full-text catalog**</span></span>  
     <span data-ttu-id="4cdbc-140">Wählen Sie einen Volltextkatalog aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="4cdbc-140">Select a full-text catalog from the list.</span></span> <span data-ttu-id="4cdbc-141">Der Standardkatalog für die Datenbank entspricht standardmäßig dem in der Liste ausgewählten Element.</span><span class="sxs-lookup"><span data-stu-id="4cdbc-141">The default catalog for the database will be the selected item by default in the list.</span></span> <span data-ttu-id="4cdbc-142">Wenn keine Kataloge verfügbar sind, wird die Liste deaktiviert, und das Kontrollkästchen **Neuen Katalog erstellen** wird überprüft und deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="4cdbc-142">If no catalogs are available, the list will be disabled, and the **Create a new catalog** checkbox will be checked and disabled.</span></span>  
  
    |||  
    |-|-|  
    |<span data-ttu-id="4cdbc-143">**Erstellen eines neuen Katalogs**</span><span class="sxs-lookup"><span data-stu-id="4cdbc-143">**Create a new catalog**</span></span>|<span data-ttu-id="4cdbc-144">Aktivieren Sie dieses Kontrollkästchen, um einen neuen Volltextkatalog zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4cdbc-144">Select to create a new full-text catalog.</span></span>|  
  
     <span data-ttu-id="4cdbc-145">**Name**</span><span class="sxs-lookup"><span data-stu-id="4cdbc-145">**Name**</span></span>  
     <span data-ttu-id="4cdbc-146">Geben Sie einen Namen für den neuen Volltextkatalog ein.</span><span class="sxs-lookup"><span data-stu-id="4cdbc-146">Enter a name for the new full-text catalog.</span></span>  
  
     <span data-ttu-id="4cdbc-147">**Als Standardkatalog festlegen**</span><span class="sxs-lookup"><span data-stu-id="4cdbc-147">**Set as default catalog**</span></span>  
     <span data-ttu-id="4cdbc-148">Wählen Sie diese Option aus, um diesen Katalog als Standardkatalog für die Datenbank festzulegen.</span><span class="sxs-lookup"><span data-stu-id="4cdbc-148">Select to make the catalog the default for this database.</span></span>  
  
     <span data-ttu-id="4cdbc-149">**Unterscheidung nach Akzent**</span><span class="sxs-lookup"><span data-stu-id="4cdbc-149">**Accent sensitivity**</span></span>  
     <span data-ttu-id="4cdbc-150">Geben Sie an, ob für den neuen Katalog nach Akzenten unterschieden wird.</span><span class="sxs-lookup"><span data-stu-id="4cdbc-150">Specify whether the new catalog will be accent-sensitive or accent-insensitive.</span></span> <span data-ttu-id="4cdbc-151">Wenn in der Datenbank nach Akzent unterschieden wird, ist die Option **Mit Unterscheidung** standardmäßig ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="4cdbc-151">If the database is accent-sensitive, **Sensitive** will be selected by default.</span></span>  
  
     <span data-ttu-id="4cdbc-152">**Indexdateigruppe auswählen**</span><span class="sxs-lookup"><span data-stu-id="4cdbc-152">**Select index filegroup**</span></span>  
     <span data-ttu-id="4cdbc-153">Geben Sie die Dateigruppe an, für die der Volltextindex erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="4cdbc-153">Specify the filegroup on which to create the full-text index.</span></span>  
  
     <span data-ttu-id="4cdbc-154">Folgende Werte sind möglich:</span><span class="sxs-lookup"><span data-stu-id="4cdbc-154">Select one of the following values:</span></span>  
  
    |<span data-ttu-id="4cdbc-155">Wert</span><span class="sxs-lookup"><span data-stu-id="4cdbc-155">Value</span></span>|<span data-ttu-id="4cdbc-156">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4cdbc-156">Description</span></span>|  
    |-----------|-----------------|  
    |**\<default>**|<span data-ttu-id="4cdbc-157">Wenn die Tabelle oder Sicht nicht partitioniert ist, wählen Sie diese Option, um dieselbe Dateigruppe wie die zugrunde liegende Tabelle oder Sicht zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="4cdbc-157">If the table or view is not partitioned, select to use the same filegroup as the underlying table or view.</span></span> <span data-ttu-id="4cdbc-158">Wenn die Tabelle oder Sicht partitioniert ist, wird die primäre Dateigruppe verwendet.</span><span class="sxs-lookup"><span data-stu-id="4cdbc-158">If the table or view is partitioned, the primary filegroup is used.</span></span>|  
    |<span data-ttu-id="4cdbc-159">**Vorrangiges**</span><span class="sxs-lookup"><span data-stu-id="4cdbc-159">**PRIMARY**</span></span>|<span data-ttu-id="4cdbc-160">Wählen Sie diese Option, um die primäre Dateigruppe für den neuen Volltextindex zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="4cdbc-160">Select to use the primary filegroup for the new full-text index.</span></span>|  
    |<span data-ttu-id="4cdbc-161">*Eine vom Benutzer angegebene Standarddateigruppe*</span><span class="sxs-lookup"><span data-stu-id="4cdbc-161">*user-specified default filegroup*</span></span>|<span data-ttu-id="4cdbc-162">Wenn eine benutzerdefinierte Standardstoppliste vorhanden ist, wählen Sie den Namen in der Liste aus, um die zugehörige Dateigruppe für den neuen Volltextindex zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="4cdbc-162">If a user-defined default stoplist exists, select its name from the list to use that filegroup for the new full-text index.</span></span>|  
  
     <span data-ttu-id="4cdbc-163">**Volltext-Stoppliste auswählen**</span><span class="sxs-lookup"><span data-stu-id="4cdbc-163">**Select full-text stoplist**</span></span>  
     <span data-ttu-id="4cdbc-164">Geben Sie eine Stoppliste an, die für den Volltextindex verwendet werden soll, oder deaktivieren Sie die Stopplistenverwendung.</span><span class="sxs-lookup"><span data-stu-id="4cdbc-164">Specify a stoplist to use for the full-text index, or disable stoplist use.</span></span>  
  
     <span data-ttu-id="4cdbc-165">In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] und neueren Versionen werden Stoppwörter in Datenbanken über Objekte verwaltet, die als Stopplisten bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="4cdbc-165">In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] and later versions, stopwords are managed in databases using objects called stoplists.</span></span> <span data-ttu-id="4cdbc-166">Eine *Stopp Liste* ist eine Liste von Stopp Wörtern, die, wenn Sie einem Volltextindex zugeordnet ist, auf voll Text Abfragen für diesen Index angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="4cdbc-166">A *stoplist* is a list of stopwords that, when associated with a full-text index, is applied to full-text queries on that index.</span></span> <span data-ttu-id="4cdbc-167">Weitere Informationen finden sie unter [Konfigurieren und Verwalten von Stoppwörtern und Stopplisten für Volltextsuche](configure-and-manage-stopwords-and-stoplists-for-full-text-search.md).</span><span class="sxs-lookup"><span data-stu-id="4cdbc-167">For more information, see [Configure and Manage Stopwords and Stoplists for Full-Text Search](configure-and-manage-stopwords-and-stoplists-for-full-text-search.md).</span></span>  
  
     <span data-ttu-id="4cdbc-168">Folgende Werte sind möglich:</span><span class="sxs-lookup"><span data-stu-id="4cdbc-168">Select one of the following values:</span></span>  
  
    |<span data-ttu-id="4cdbc-169">Wert</span><span class="sxs-lookup"><span data-stu-id="4cdbc-169">Value</span></span>|<span data-ttu-id="4cdbc-170">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4cdbc-170">Description</span></span>|  
    |-----------|-----------------|  
    |**\<system>**|<span data-ttu-id="4cdbc-171">Wählen Sie diese Option, um die Systemstoppliste für den neuen Volltextindex zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="4cdbc-171">Select to use the system stoplist on the new full-text index.</span></span> <span data-ttu-id="4cdbc-172">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="4cdbc-172">This is the default</span></span>|  
    |**\<off>**|<span data-ttu-id="4cdbc-173">Wählen Sie diese Option, um Stopplisten für den neuen Volltextindex zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="4cdbc-173">Select to disable stoplists for the new full-text index.</span></span>|  
    |<span data-ttu-id="4cdbc-174">*user-defined-stoplist-name*</span><span class="sxs-lookup"><span data-stu-id="4cdbc-174">*user-defined-stoplist-name*</span></span>|<span data-ttu-id="4cdbc-175">Die Liste enthält die Namen aller benutzerdefinierten Stopplisten (falls vorhanden), die für die Datenbank erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="4cdbc-175">The list displays the name of each user-defined stoplist, if any, that has been created on the database.</span></span> <span data-ttu-id="4cdbc-176">Wählen Sie eine beliebige benutzerdefinierte Stoppliste zur Verwendung für den neuen Volltextindex aus.</span><span class="sxs-lookup"><span data-stu-id="4cdbc-176">Select any user-defined stoplist to use for the new full-text index.</span></span>|  
  
4.  <span data-ttu-id="4cdbc-177">Optional können Sie auch den Auffüllungszeitplan definieren.</span><span class="sxs-lookup"><span data-stu-id="4cdbc-177">Optionally, define the population schedule.</span></span> <span data-ttu-id="4cdbc-178">Sofern Sie die Ausführung nicht für die Zukunft geplant haben, beginnen die Indizierungsvorgänge sofort.</span><span class="sxs-lookup"><span data-stu-id="4cdbc-178">Indexing operations will begin immediately unless they have been scheduled for future execution.</span></span> <span data-ttu-id="4cdbc-179">Die Zeitpläne werden sofort erstellt, sie werden jedoch erst zum festgelegten Zeitpunkt ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4cdbc-179">Schedules will be created immediately, although they will not run until their scheduled time.</span></span>  
  
     <span data-ttu-id="4cdbc-180">**Neuer Tabellenzeitplan**</span><span class="sxs-lookup"><span data-stu-id="4cdbc-180">**New Table Schedule**</span></span>  
     <span data-ttu-id="4cdbc-181">Definieren eines Auffüllungszeitplans für eine Tabelle.</span><span class="sxs-lookup"><span data-stu-id="4cdbc-181">Define a population schedule for a table.</span></span>  
  
     <span data-ttu-id="4cdbc-182">**Neuer Katalogzeitplan**</span><span class="sxs-lookup"><span data-stu-id="4cdbc-182">**New Catalog Schedule**</span></span>  
     <span data-ttu-id="4cdbc-183">Definieren eines Auffüllungszeitplans für einen Volltextkatalog.</span><span class="sxs-lookup"><span data-stu-id="4cdbc-183">Define a population schedule for a full-text catalog.</span></span>  
  
     <span data-ttu-id="4cdbc-184">**Bearbeiten**</span><span class="sxs-lookup"><span data-stu-id="4cdbc-184">**Edit**</span></span>  
     <span data-ttu-id="4cdbc-185">Bearbeiten eines Zeitplans.</span><span class="sxs-lookup"><span data-stu-id="4cdbc-185">Edit a schedule.</span></span>  
  
     <span data-ttu-id="4cdbc-186">**Löschen**</span><span class="sxs-lookup"><span data-stu-id="4cdbc-186">**Delete**</span></span>  
     <span data-ttu-id="4cdbc-187">Löschen eines Zeitplans.</span><span class="sxs-lookup"><span data-stu-id="4cdbc-187">Delete a schedule.</span></span>  
  
5.  <span data-ttu-id="4cdbc-188">Zeigen Sie den Status des Volltextindizierungs-Assistenten an, bzw. steuern Sie ihn.</span><span class="sxs-lookup"><span data-stu-id="4cdbc-188">View or control the progress of the Full-Text Indexing Wizard.</span></span>  
  
     <span data-ttu-id="4cdbc-189">**Beenden**</span><span class="sxs-lookup"><span data-stu-id="4cdbc-189">**Stop**</span></span>  
     <span data-ttu-id="4cdbc-190">Unterbricht den aktuellen Vorgang und verhindert die Ausführung nachfolgender Volltextvorgänge durch den Assistenten während dieser Sitzung.</span><span class="sxs-lookup"><span data-stu-id="4cdbc-190">Interrupts the current operation and prevents subsequent full-text operations from being performed by the wizard during this session.</span></span>  
  
     <span data-ttu-id="4cdbc-191">**Report**</span><span class="sxs-lookup"><span data-stu-id="4cdbc-191">**Report**</span></span>  
     <span data-ttu-id="4cdbc-192">Wenn alle Vorgänge ausgeführt wurden, können Sie auf diese Schaltfläche klicken, um auf einen Bericht zu den ausgeführten Vorgängen zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="4cdbc-192">When all of the operations have finished executing, click this button to access a report on the operations performed.</span></span> <span data-ttu-id="4cdbc-193">Sie können den Bericht anzeigen, in eine Datei drucken, in die Zwischenablage kopieren oder ihn per E-Mail versenden.</span><span class="sxs-lookup"><span data-stu-id="4cdbc-193">You can view the report, print it to a file, copy it to the clipboard, or e-mail the report.</span></span>  
  
  
