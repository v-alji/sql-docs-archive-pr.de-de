---
title: Voll Text Index-Eigenschaften (Seite "Allgemein") | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
f1_keywords:
- sql12.swb.fulltextsearch.fulltextindexproperties.general.f1
ms.assetid: f4dff61c-8c2f-4ff9-abe4-70a34421448f
author: rothja
ms.author: jroth
ms.openlocfilehash: 61b9f2948df138c39230cf6f5787c395a364c695
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622840"
---
# <a name="full-text-index-properties-general-page"></a><span data-ttu-id="be83e-102">Volltextindex-Eigenschaften (Seite 'Allgemein')</span><span class="sxs-lookup"><span data-stu-id="be83e-102">Full-Text Index Properties (General Page)</span></span>
  <span data-ttu-id="be83e-103">**So zeigen Sie die veränderbaren Eigenschaften eines Volltextindexes an oder ändern Sie diese**</span><span class="sxs-lookup"><span data-stu-id="be83e-103">**To view or change the modifiable properties of a full-text index**</span></span>  
  
-   [<span data-ttu-id="be83e-104">Verwalten von Volltextindizes</span><span class="sxs-lookup"><span data-stu-id="be83e-104">Manage Full-Text Indexes</span></span>](../relational-databases/indexes/indexes.md)  
  
## <a name="ui-element-list"></a><span data-ttu-id="be83e-105">Liste der Benutzeroberflächenelemente</span><span class="sxs-lookup"><span data-stu-id="be83e-105">UI element list</span></span>  
 <span data-ttu-id="be83e-106">**Voll Text Katalog**</span><span class="sxs-lookup"><span data-stu-id="be83e-106">**Full-Text Catalog**</span></span>  
 <span data-ttu-id="be83e-107">Zeigt den Namen des Volltextkatalogs an, dem dieser Volltextindex zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="be83e-107">Displays the name of the full-text catalog with which the full-text index is associated.</span></span>  
  
 <span data-ttu-id="be83e-108">**Datenbank**</span><span class="sxs-lookup"><span data-stu-id="be83e-108">**Database**</span></span>  
 <span data-ttu-id="be83e-109">Zeigt den Namen der Datenbank an, in der sich der Volltextindex befindet.</span><span class="sxs-lookup"><span data-stu-id="be83e-109">Displays the name of the database in which the full-text index resides.</span></span>  
  
 <span data-ttu-id="be83e-110">**Tabelle**</span><span class="sxs-lookup"><span data-stu-id="be83e-110">**Table**</span></span>  
 <span data-ttu-id="be83e-111">Zeigt den Namen der Tabelle an, für die der Volltextindex definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="be83e-111">Displays the name of the table on which the full-text index is defined.</span></span>  
  
 <span data-ttu-id="be83e-112">**Volltext-Indexschlüssel**</span><span class="sxs-lookup"><span data-stu-id="be83e-112">**Full-Text Index Key**</span></span>  
 <span data-ttu-id="be83e-113">Zeigt den Namen des Volltext-Indexschlüssels an, der einen eindeutigen Index für eine einzelne Spalte der Tabelle darstellt.</span><span class="sxs-lookup"><span data-stu-id="be83e-113">Displays the name of the full-text index key, which is a unique index on a single column of the table.</span></span>  
  
 <span data-ttu-id="be83e-114">**Volltext-Auffüllstatus-Tabelle**</span><span class="sxs-lookup"><span data-stu-id="be83e-114">**Table Full-Text Populate Status**</span></span>  
 <span data-ttu-id="be83e-115">Zeigt den Auffüllungsstatus der volltextindizierten Tabelle an.</span><span class="sxs-lookup"><span data-stu-id="be83e-115">Displays the population status of the full-text indexed table.</span></span>  
  
 <span data-ttu-id="be83e-116">Die folgenden Werte sind möglich:</span><span class="sxs-lookup"><span data-stu-id="be83e-116">The possible values are as follows:</span></span>  
  
 <span data-ttu-id="be83e-117">0 = Im Leerlauf.</span><span class="sxs-lookup"><span data-stu-id="be83e-117">0 = Idle.</span></span>  
  
 <span data-ttu-id="be83e-118">1 = Vollständige Auffüllung wird ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="be83e-118">1 = Full population is in progress.</span></span>  
  
 <span data-ttu-id="be83e-119">2 = Inkrementelle Auffüllung wird ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="be83e-119">2 = Incremental population is in progress.</span></span>  
  
 <span data-ttu-id="be83e-120">3 = Propagierung der Überarbeitungen wird ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="be83e-120">3 = Propagation of tracked changes is in progress.</span></span>  
  
 <span data-ttu-id="be83e-121">4 = Indexupdate wird im Hintergrund ausgeführt, z. B. automatische Änderungsnachverfolgung.</span><span class="sxs-lookup"><span data-stu-id="be83e-121">4 = Background update index is in progress, such as automatic change tracking.</span></span>  
  
 <span data-ttu-id="be83e-122">5 = Volltextindizierung wurde gedrosselt oder angehalten.</span><span class="sxs-lookup"><span data-stu-id="be83e-122">5 = Full-text indexing is throttled or paused.</span></span>  
  
 <span data-ttu-id="be83e-123">**Aktiver Volltextindex**</span><span class="sxs-lookup"><span data-stu-id="be83e-123">**Active Full-Text Index**</span></span>  
 <span data-ttu-id="be83e-124">Gibt an, ob die Tabelle über einen aktiven Volltextindex verfügt.</span><span class="sxs-lookup"><span data-stu-id="be83e-124">Indicates whether the table has an active full-text index.</span></span>  
  
 <span data-ttu-id="be83e-125">1 = True</span><span class="sxs-lookup"><span data-stu-id="be83e-125">1 = True</span></span>  
  
 <span data-ttu-id="be83e-126">0 = False</span><span class="sxs-lookup"><span data-stu-id="be83e-126">0 = False</span></span>  
  
 <span data-ttu-id="be83e-127">**Volltextindex-Dateigruppe**</span><span class="sxs-lookup"><span data-stu-id="be83e-127">**Full-Text Index Filegroup**</span></span>  
 <span data-ttu-id="be83e-128">Die Dateigruppe, zu der der Volltextindex gehört.</span><span class="sxs-lookup"><span data-stu-id="be83e-128">The filegroup to which the full-text index belongs.</span></span>  
  
 <span data-ttu-id="be83e-129">**Volltextindex-Stoppliste**</span><span class="sxs-lookup"><span data-stu-id="be83e-129">**Full-Text Index Stoplist**</span></span>  
 <span data-ttu-id="be83e-130">Die Stoppliste, die gegenwärtig dem Volltextindex zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="be83e-130">The stoplist that is currently associated with the full-text index.</span></span> <span data-ttu-id="be83e-131">Eine Stoppliste ist eine Liste von [Stoppwörtern](../relational-databases/search/full-text-search.md).</span><span class="sxs-lookup"><span data-stu-id="be83e-131">A stoplist is a list of [stopwords](../relational-databases/search/full-text-search.md).</span></span> <span data-ttu-id="be83e-132">Die ggf. einem Volltextindex zugeordnete Stoppliste wird auf Volltextabfragen für diesen Index angewendet.</span><span class="sxs-lookup"><span data-stu-id="be83e-132">The stoplist associated with a full-text index, if any, is applied to full-text queries on that index.</span></span> <span data-ttu-id="be83e-133">Sie können die Stopp Liste aus dem Index entfernen, indem Sie **\<OFF>** aus der Liste auswählen, oder Sie können eine andere Stopp Liste auswählen; **\<SYSTEM>** gibt die System Stopp Liste an.</span><span class="sxs-lookup"><span data-stu-id="be83e-133">You can remove the stoplist from the index by selecting **\<OFF>** from the list, or you can select a different stoplist; **\<SYSTEM>** indicates the system stoplist.</span></span>  
  
 <span data-ttu-id="be83e-134">**So erstellen Sie eine Stoppliste**</span><span class="sxs-lookup"><span data-stu-id="be83e-134">**To create a stoplist**</span></span>  
  
-   [<span data-ttu-id="be83e-135">Konfigurieren und Verwalten von Stoppwörtern und Stopplisten für Volltextsuche</span><span class="sxs-lookup"><span data-stu-id="be83e-135">Configure and Manage Stopwords and Stoplists for Full-Text Search</span></span>](../relational-databases/search/full-text-search.md)  
  
 <span data-ttu-id="be83e-136">**Sucheigenschaftenliste**</span><span class="sxs-lookup"><span data-stu-id="be83e-136">**Search Property List**</span></span>  
 <span data-ttu-id="be83e-137">Die Sucheigenschaftenliste, die ggf. derzeit dem Volltextindex zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="be83e-137">The search property list that is currently associated with the full-text index, if any.</span></span> <span data-ttu-id="be83e-138">Eine Sucheigenschaftenliste gibt einen Satz von Dokumenteigenschaften an, die im zugeordneten Volltextindex enthalten sind, wenn dieser aufgefüllt ist.</span><span class="sxs-lookup"><span data-stu-id="be83e-138">A search property list specifies a set of document properties that are included in the associated full-text index when it is populated.</span></span> <span data-ttu-id="be83e-139">Weitere Informationen finden Sie unter [Suchen von Dokumenteigenschaften mithilfe von Sucheigenschaftenlisten](../relational-databases/search/search-document-properties-with-search-property-lists.md).</span><span class="sxs-lookup"><span data-stu-id="be83e-139">For more information, see [Search Document Properties with Search Property Lists](../relational-databases/search/search-document-properties-with-search-property-lists.md).</span></span>  
  
 <span data-ttu-id="be83e-140">**\<Off>** Gibt an, dass dem Index derzeit keine Such Eigenschaften Liste zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="be83e-140">**\<Off>** indicates that there is currently no search property list associated with the index.</span></span> <span data-ttu-id="be83e-141">Sie können die aktuelle Such Eigenschaften Liste aus dem Index entfernen, indem Sie **\<Off>** aus der Liste auswählen, oder Sie können in der Liste eine andere Such Eigenschaften Liste auswählen.</span><span class="sxs-lookup"><span data-stu-id="be83e-141">You can remove the current search property list from the index by selecting **\<Off>** from the list, or you can select a different search property list from the list.</span></span> <span data-ttu-id="be83e-142">An dieser Stelle werden nur Sucheigenschaftenlisten in der aktuellen Datenbank aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="be83e-142">Only search property lists in the current database are listed here.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="be83e-143">Sie können eine Sucheigenschaftenliste mehr als einem Volltextindex in der gleichen Datenbank zuordnen.</span><span class="sxs-lookup"><span data-stu-id="be83e-143">You can associate a given search property list with more than one full-text index in the same database.</span></span>  
  
 <span data-ttu-id="be83e-144">**So erstellen Sie eine Sucheigenschaftenliste**</span><span class="sxs-lookup"><span data-stu-id="be83e-144">**To create a search property list**</span></span>  
  
-   [<span data-ttu-id="be83e-145">Suchen von Dokumenteigenschaften mithilfe von Sucheigenschaftenlisten</span><span class="sxs-lookup"><span data-stu-id="be83e-145">Search Document Properties with Search Property Lists</span></span>](../relational-databases/search/search-document-properties-with-search-property-lists.md)  
  
 <span data-ttu-id="be83e-146">**Volltext-Elementanzahl-Tabelle**</span><span class="sxs-lookup"><span data-stu-id="be83e-146">**Table Full-Text Item Count**</span></span>  
 <span data-ttu-id="be83e-147">Gibt die Anzahl der Zeilen an, die erfolgreich volltextindiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="be83e-147">Indicates the number of rows that were full-text indexed successfully.</span></span>  
  
 <span data-ttu-id="be83e-148">Diese Eigenschaft entspricht der von der OBJECTPROPERTYEX-Funktion von [!INCLUDE[tsql](../includes/tsql-md.md)] zurückgegebenen `TableFulltextItemCount`-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="be83e-148">This property corresponds to the `TableFulltextItemCount` property returned by the OBJECTPROPERTYEX [!INCLUDE[tsql](../includes/tsql-md.md)] function.</span></span>  
  
 <span data-ttu-id="be83e-149">**Tabelle für verarbeitete Volltextdokumente**</span><span class="sxs-lookup"><span data-stu-id="be83e-149">**Table Full-Text Docs Processed**</span></span>  
 <span data-ttu-id="be83e-150">Zeigt die Anzahl der seit dem Start der Volltextindizierung verarbeiteten Zeilen an.</span><span class="sxs-lookup"><span data-stu-id="be83e-150">Displays the number of rows that have been processed since the start of full-text indexing.</span></span> <span data-ttu-id="be83e-151">In einer Tabelle, die für die Volltextsuche indiziert wird, werden alle Spalten einer Zeile als Teil eines zu indizierenden Dokuments betrachtet.</span><span class="sxs-lookup"><span data-stu-id="be83e-151">In a table that is being indexed for full-text search, all the columns of one row are considered as part of one document to be indexed.</span></span> <span data-ttu-id="be83e-152">Gelöschte Zeilen werden nicht gezählt.</span><span class="sxs-lookup"><span data-stu-id="be83e-152">Deleted rows are not counted.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="be83e-153">0</span><span class="sxs-lookup"><span data-stu-id="be83e-153">0</span></span>|<span data-ttu-id="be83e-154">Gibt an, dass die Volltextindizierung abgeschlossen ist und keine aktive Auffüllung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="be83e-154">Indicates that full-text indexing is completed and there is no active population.</span></span>|  
|<span data-ttu-id="be83e-155">> 0</span><span class="sxs-lookup"><span data-stu-id="be83e-155">> 0</span></span>|<span data-ttu-id="be83e-156">Gibt bei einer aktiven Auffüllung die Anzahl der Dokumente an, die seit einer der folgenden Aktionen mithilfe von Einfüge- und Updatevorgängen verarbeitet wurden: Auffüllung, Aktivieren der Änderungsnachverfolgung mit Indexupdate im Hintergrund (z. B. automatische Änderungsnachverfolgung), Änderung des Schemas für den Volltextindex, Neuerstellung des Volltextkatalogs, Neustart de Instanz von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], usw.</span><span class="sxs-lookup"><span data-stu-id="be83e-156">For an active population, indicates the number of documents processed by insert or update operations since any of the following: a population, enabling of change tracking with background update index population (such as auto change tracking), changing the full-text index schema, rebuilding the full-text catalog, restarting the instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], and so forth.</span></span>|  
  
 <span data-ttu-id="be83e-157">**Tabelle für ausstehende Volltextänderungen**</span><span class="sxs-lookup"><span data-stu-id="be83e-157">**Table Full-Text Pending Changes**</span></span>  
 <span data-ttu-id="be83e-158">Anzahl der zu verarbeitenden ausstehenden Änderungsnachverfolgungseinträge.</span><span class="sxs-lookup"><span data-stu-id="be83e-158">Number of pending change tracking entries to process.</span></span>  
  
 <span data-ttu-id="be83e-159">0 = Änderungsnachverfolgung ist nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="be83e-159">0 = change tracking is not enabled.</span></span>  
  
 <span data-ttu-id="be83e-160">NULL = Die Tabelle besitzt keinen Volltextindex.</span><span class="sxs-lookup"><span data-stu-id="be83e-160">NULL = Table does not have a full-text index.</span></span>  
  
 <span data-ttu-id="be83e-161">**Volltext-Fehlerzahl-Tabelle**</span><span class="sxs-lookup"><span data-stu-id="be83e-161">**Table Full-Text Fail Count**</span></span>  
 <span data-ttu-id="be83e-162">Die Anzahl der Zeilen, die von der Volltextsuche nicht indiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="be83e-162">The number of rows that full-text search did not index.</span></span>  
  
 <span data-ttu-id="be83e-163">0 = Die Auffüllung ist abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="be83e-163">0 = The population has completed.</span></span>  
  
 <span data-ttu-id="be83e-164">\>0 = eine der folgenden:</span><span class="sxs-lookup"><span data-stu-id="be83e-164">\>0 = One of the following:</span></span>  
  
-   <span data-ttu-id="be83e-165">Die Anzahl der Dokumente, die seit dem Start der Auffüllung mithilfe der vollständigen, inkrementellen und manuellen Änderungsnachverfolgung nicht indiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="be83e-165">The number of documents that were not indexed since the start of full, incremental, or manual change tracking population.</span></span>  
  
-   <span data-ttu-id="be83e-166">Bei der Änderungsnachverfolgung mit Indexupdate im Hintergrund die Anzahl der Zeilen, die seit dem Start der Auffüllung oder dem Neustart der Auffüllung nicht indiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="be83e-166">For change tracking with background update index, the number of rows that were not indexed since the start of the population, or the restart of the population.</span></span> <span data-ttu-id="be83e-167">Dies könnte durch eine Schemaänderung, eine erneute Erstellung des Katalogs, einen Neustart des Servers usw. verursacht werden.</span><span class="sxs-lookup"><span data-stu-id="be83e-167">This could be caused by a schema change, rebuild of the catalog, server restart, and so on</span></span>  
  
 <span data-ttu-id="be83e-168">**Volltextindizierung aktiviert**</span><span class="sxs-lookup"><span data-stu-id="be83e-168">**Full-Text Indexing Enabled**</span></span>  
 <span data-ttu-id="be83e-169">Gibt an, ob die Volltextindizierung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="be83e-169">Specifies whether full-text indexing is enabled.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="be83e-170">**Wahr**</span><span class="sxs-lookup"><span data-stu-id="be83e-170">**True**</span></span>|<span data-ttu-id="be83e-171">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="be83e-171">Enabled</span></span>|  
|<span data-ttu-id="be83e-172">**False**</span><span class="sxs-lookup"><span data-stu-id="be83e-172">**False**</span></span>|<span data-ttu-id="be83e-173">Disabled</span><span class="sxs-lookup"><span data-stu-id="be83e-173">Disabled</span></span>|  
  
 <span data-ttu-id="be83e-174">**Änderungsnachverfolgung**</span><span class="sxs-lookup"><span data-stu-id="be83e-174">**Change Tracking**</span></span>  
 <span data-ttu-id="be83e-175">Gibt an, ob die Volltext-Änderungsnachverfolgung für die Tabelle aktiviert ist, und wenn dies der Fall ist, deren Typ.</span><span class="sxs-lookup"><span data-stu-id="be83e-175">Specifies whether the table has full-text change-tracking enabled, and if so, what kind.</span></span> <span data-ttu-id="be83e-176">Bei der Volltext-Änderungsnachverfolgung werden die Zeilen aufgezeichnet, die in einer Tabelle oder indizierten Sicht geändert wurden, die für die Volltextindizierung eingerichtet wurde.</span><span class="sxs-lookup"><span data-stu-id="be83e-176">Full-text change tracking maintains a record of the rows that have been modified in a table or indexed view that has been set up for full-text indexing.</span></span> <span data-ttu-id="be83e-177">Diese Änderungen können an den Volltextindex weitergegeben werden.</span><span class="sxs-lookup"><span data-stu-id="be83e-177">These changes can be propagated to the full-text index.</span></span>  
  
 <span data-ttu-id="be83e-178">Folgende Werte für **Änderungsnachverfolgung** sind möglich:</span><span class="sxs-lookup"><span data-stu-id="be83e-178">The **Change Tracking** values are as follows:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="be83e-179">**Deaktiviert**</span><span class="sxs-lookup"><span data-stu-id="be83e-179">**Off**</span></span>|<span data-ttu-id="be83e-180">Der Volltextindex wird nicht mit Änderungen an den zugrunde liegenden Daten aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="be83e-180">The full-text index is not updated with changes to the underlying data.</span></span>|  
|<span data-ttu-id="be83e-181">**Manuell**</span><span class="sxs-lookup"><span data-stu-id="be83e-181">**Manual**</span></span>|<span data-ttu-id="be83e-182">Der Volltextindex wird bei Änderungen zu den zugrunde liegenden Daten nicht automatisch aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="be83e-182">The full-text index is not updated automatically as changes occur to the underlying data.</span></span> <span data-ttu-id="be83e-183">Änderungen an den zugrunde liegenden Daten werden jedoch beibehalten, und Sie können sie an den</span><span class="sxs-lookup"><span data-stu-id="be83e-183">However, changes to the underlying data are maintained, and you can propagate them to the .</span></span> <span data-ttu-id="be83e-184">Volltextindex weitergeben, entweder nach einem Zeitplan unter Verwendung des SQL-Server-Agents oder manuell.</span><span class="sxs-lookup"><span data-stu-id="be83e-184">full-text index either on a schedule using SQL Server Agent or manually.</span></span>|  
|<span data-ttu-id="be83e-185">**Automatisch**</span><span class="sxs-lookup"><span data-stu-id="be83e-185">**Automatic**</span></span>|<span data-ttu-id="be83e-186">Der Volltextindex wird bei Änderungen zu den zugrunde liegenden Daten in der Basistabelle automatisch aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="be83e-186">The full-text index is updated automatically as changes occur to the underlying data in the base table.</span></span>|  
  
 <span data-ttu-id="be83e-187">**Index neu auffüllen**</span><span class="sxs-lookup"><span data-stu-id="be83e-187">**Repopulate index**</span></span>  
 <span data-ttu-id="be83e-188">Klicken Sie, um beim Beenden des Dialogfelds die Auffüllung des Volltextindexes zu starten.</span><span class="sxs-lookup"><span data-stu-id="be83e-188">Click to start a population on the full-text index on exiting the dialog box.</span></span> <span data-ttu-id="be83e-189">Wählen Sie einen der folgenden Auffüllungstypen aus:</span><span class="sxs-lookup"><span data-stu-id="be83e-189">Select one of the following types of population:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="be83e-190">**Vollständig**</span><span class="sxs-lookup"><span data-stu-id="be83e-190">**Full**</span></span>|<span data-ttu-id="be83e-191">Während einer vollständigen Auffüllung einer Tabelle werden Indexeinträge für alle Zeilen erstellt.</span><span class="sxs-lookup"><span data-stu-id="be83e-191">During a full population of a table, index entries are built for all the rows.</span></span>|  
|<span data-ttu-id="be83e-192">**Inkrementell**</span><span class="sxs-lookup"><span data-stu-id="be83e-192">**Incremental**</span></span>|<span data-ttu-id="be83e-193">Bei der inkrementellen Auffüllung wird der Volltextindex bezüglich der Zeilen aktualisiert, die seit der letzten Auffüllung oder während des letzten Auffüllungsvorgangs hinzugefügt, gelöscht oder geändert wurden.</span><span class="sxs-lookup"><span data-stu-id="be83e-193">Incremental population updates the full-text index for rows added, deleted, or modified after the last population, or while the last population was in progress.</span></span> <span data-ttu-id="be83e-194">Für eine inkrementelle Auffüllung muss die Basistabelle eine Spalte des Datentyps `timestamp` enthalten.</span><span class="sxs-lookup"><span data-stu-id="be83e-194">Performing an incremental population requires that the base table contain a column of the `timestamp` data type.</span></span>|  
|<span data-ttu-id="be83e-195">**Aktualisieren**</span><span class="sxs-lookup"><span data-stu-id="be83e-195">**Update**</span></span>|<span data-ttu-id="be83e-196">Der Volltextindex wird stets aktualisiert, wenn die Daten in der Basistabelle geändert werden.</span><span class="sxs-lookup"><span data-stu-id="be83e-196">The full-text index is updated whenever the data in the base table is modified.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="be83e-197">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="be83e-197">See Also</span></span>  
 [<span data-ttu-id="be83e-198">Erste Schritte mit der Volltextsuche</span><span class="sxs-lookup"><span data-stu-id="be83e-198">Get Started with Full-Text Search</span></span>](../relational-databases/search/get-started-with-full-text-search.md)  
  
  
