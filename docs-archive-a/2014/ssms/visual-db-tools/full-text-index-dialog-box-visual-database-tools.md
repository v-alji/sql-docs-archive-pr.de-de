---
title: Volltextindex (Dialogfeld) (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.fulltextindex
ms.assetid: ef45b585-2567-4abe-b421-9fd0994e0146
author: stevestein
ms.author: sstein
ms.openlocfilehash: f98d3bf43707caedd8c9d0a01349f36d5a5bfbcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725185"
---
# <a name="full-text-index-dialog-box-visual-database-tools"></a><span data-ttu-id="652a3-102">Volltextindex (Dialogfeld) (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="652a3-102">Full-Text Index Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="652a3-103">Mit diesem Dialogfeld können Sie einen Volltextindex für Volltextsuchen in textbasierten Spalten von Datenbanktabellen erstellen.</span><span class="sxs-lookup"><span data-stu-id="652a3-103">This dialog box allows you to create a full-text index, for full-text searches on text-based columns in your database tables.</span></span> <span data-ttu-id="652a3-104">Da ein Volltextindex auf einem regulären Index basiert, müssen Sie zuerst einen regulären Index erstellen.</span><span class="sxs-lookup"><span data-stu-id="652a3-104">A full-text index relies on a regular index, so you must create that first.</span></span> <span data-ttu-id="652a3-105">Der reguläre Index muss für eine einzelne Nicht-NULL-Spalte erstellt werden. Am besten wählen Sie eine Spalte mit kleinen Werten anstatt einer Spalte mit großen Werten aus.</span><span class="sxs-lookup"><span data-stu-id="652a3-105">The regular index must be created on a single, non-null column; it is best to choose a column with small values rather than a column with large ones.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="652a3-106">Bevor Sie einen Volltextindex erstellen können, müssen Sie mithilfe eines externen Tools wie [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder Enterprise Manager einen Volltextkatalog für die Datenbank erstellen.</span><span class="sxs-lookup"><span data-stu-id="652a3-106">To create a full-text index, you must first create a full-text catalog for the database using an outside tool, such as [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or Enterprise Manager.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="652a3-107">Eine Volltextindex-Funktionalität ist nicht in jeder Edition von [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]verfügbar.</span><span class="sxs-lookup"><span data-stu-id="652a3-107">Full-text index functionality is not available in every edition of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="652a3-108">Eine Liste der Funktionen, die von den Editionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]unterstützt werden, finden Sie unter [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="652a3-108">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="652a3-109">Tastatur</span><span class="sxs-lookup"><span data-stu-id="652a3-109">Options</span></span>  
 <span data-ttu-id="652a3-110">**Ausgewählter Volltextindex**</span><span class="sxs-lookup"><span data-stu-id="652a3-110">**Selected Full-Text Index**</span></span>  
 <span data-ttu-id="652a3-111">Listet vorhandene Volltextindizes auf.</span><span class="sxs-lookup"><span data-stu-id="652a3-111">Lists existing full-text indexes.</span></span> <span data-ttu-id="652a3-112">Wählen Sie einen Index aus, um seine Eigenschaften im Datenblatt rechts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="652a3-112">Select an index to show its properties in the grid to the right.</span></span> <span data-ttu-id="652a3-113">Wenn die Liste leer ist, wurden bisher keine Volltextbeziehungen für die Tabelle definiert.</span><span class="sxs-lookup"><span data-stu-id="652a3-113">If the list is empty, no full-text relationships have been defined for the table.</span></span>  
  
 <span data-ttu-id="652a3-114">**Add (Hinzufügen)**</span><span class="sxs-lookup"><span data-stu-id="652a3-114">**Add**</span></span>  
 <span data-ttu-id="652a3-115">Erstellen Sie einen neuen Volltextindex.</span><span class="sxs-lookup"><span data-stu-id="652a3-115">Create a new full-text index.</span></span>  
  
 <span data-ttu-id="652a3-116">**Löschen**</span><span class="sxs-lookup"><span data-stu-id="652a3-116">**Delete**</span></span>  
 <span data-ttu-id="652a3-117">Löschen Sie den in der Liste **Ausgewählter Volltextindex** ausgewählten Volltextindex.</span><span class="sxs-lookup"><span data-stu-id="652a3-117">Delete the full-text index selected in the **Selected Full-Text Index** list.</span></span>  
  
 <span data-ttu-id="652a3-118">**Kategorie Allgemein**</span><span class="sxs-lookup"><span data-stu-id="652a3-118">**General Category**</span></span>  
 <span data-ttu-id="652a3-119">Wenn die Kategorie erweitert ist, werden **Spalten** und **Volltextkatalogname**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="652a3-119">When expanded, shows **Columns** and **Full-text Catalog Name**.</span></span>  
  
 <span data-ttu-id="652a3-120">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="652a3-120">**Columns**</span></span>  
 <span data-ttu-id="652a3-121">Zeigt eine durch Trennzeichen getrennte Liste mit den Namen volltextdurchsuchbarer Spalten an.</span><span class="sxs-lookup"><span data-stu-id="652a3-121">Displays a comma-separated list of the names of full-text-searchable columns.</span></span> <span data-ttu-id="652a3-122">Klicken Sie auf die Schaltfläche mit den Auslassungspunkten ( **…** ) links neben dem Eigenschaftenfeld, um die Liste vollständig anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="652a3-122">To see the complete list, click the ellipsis button (**...**) to the left of the property field.</span></span>  
  
 <span data-ttu-id="652a3-123">**Full-Text Catalog Name**</span><span class="sxs-lookup"><span data-stu-id="652a3-123">**Full-Text Catalog Name**</span></span>  
 <span data-ttu-id="652a3-124">Zeigt den Namen des Volltextkatalogs an, für den dieser Volltextindex gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="652a3-124">Displays the name of the full-text catalog on which this full-text index is stored.</span></span> <span data-ttu-id="652a3-125">Um den Index für einen anderen Katalog zu speichern, klicken Sie auf den Katalognamen, und wählen Sie aus der Dropdownliste den gewünschten Katalog aus.</span><span class="sxs-lookup"><span data-stu-id="652a3-125">To store the index on a different catalog, click the catalog name and choose another from the drop-down list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="652a3-126">Der Katalog muss vorher in einem externen Tool (z. B. [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder Enterprise Manager) erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="652a3-126">The catalog must be created first in an outside tool, such as [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or Enterprise Manager.</span></span>  
  
 <span data-ttu-id="652a3-127">**Kategorie Identität**</span><span class="sxs-lookup"><span data-stu-id="652a3-127">**Identity Category**</span></span>  
 <span data-ttu-id="652a3-128">Wenn die Kategorie erweitert ist, wird das Feld Name für den Index angezeigt.</span><span class="sxs-lookup"><span data-stu-id="652a3-128">When expanded, shows the name field for this index.</span></span>  
  
 <span data-ttu-id="652a3-129">**Name**</span><span class="sxs-lookup"><span data-stu-id="652a3-129">**Name**</span></span>  
 <span data-ttu-id="652a3-130">Zeigt den systemspezifischen Namen für diesen Volltextindex an.</span><span class="sxs-lookup"><span data-stu-id="652a3-130">Displays the system-specified name for this full-text index.</span></span>  
  
 <span data-ttu-id="652a3-131">**Kategorie Tabellen-Designer**</span><span class="sxs-lookup"><span data-stu-id="652a3-131">**Table Designer Category**</span></span>  
 <span data-ttu-id="652a3-132">Wenn die Kategorie erweitert ist, werden Eigenschaften angezeigt, die das Verhalten des Indexes festlegen.</span><span class="sxs-lookup"><span data-stu-id="652a3-132">When expanded, shows properties that dictate how the index performs.</span></span>  
  
 <span data-ttu-id="652a3-133">**Aktiv**</span><span class="sxs-lookup"><span data-stu-id="652a3-133">**Active**</span></span>  
 <span data-ttu-id="652a3-134">Gibt an, ob Sie zurzeit mit diesem Volltextindex eine Volltextsuche ausführen können.</span><span class="sxs-lookup"><span data-stu-id="652a3-134">Indicates whether you can currently perform a full-text search using this full-text index.</span></span>  
  
 <span data-ttu-id="652a3-135">**Einstellung für das Nachverfolgen von Änderungen**</span><span class="sxs-lookup"><span data-stu-id="652a3-135">**Change Tracking Setting**</span></span>  
 <span data-ttu-id="652a3-136">Beschreibt den Status der Änderungsnachverfolgung für den Index: Manuell, Automatisch oder Aus.</span><span class="sxs-lookup"><span data-stu-id="652a3-136">Describes the status of change tracking for this index: Manual, Auto, or Off.</span></span>  
  
 <span data-ttu-id="652a3-137">**Die Durchforstung ist abgeschlossen**</span><span class="sxs-lookup"><span data-stu-id="652a3-137">**Crawl Completed**</span></span>  
 <span data-ttu-id="652a3-138">Zeigt an, ob die zuletzt gestartete Durchforstung abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="652a3-138">Shows whether the most recent crawl has been completed.</span></span> <span data-ttu-id="652a3-139">Wenn der Wert dieser Eigenschaft No ist, wird gerade eine Durchforstung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="652a3-139">If this property value is No, a crawl is currently in progress.</span></span>  
  
 <span data-ttu-id="652a3-140">**Enddatum und -uhrzeit der aktuellen oder letzten Durchforstung**</span><span class="sxs-lookup"><span data-stu-id="652a3-140">**End Date And Time Of Current Or Last Crawl**</span></span>  
 <span data-ttu-id="652a3-141">Zeigt Abschlussdatum und -zeit der letzten Durchforstung an.</span><span class="sxs-lookup"><span data-stu-id="652a3-141">Displays the date and time that the most recent crawl ended.</span></span>  
  
 <span data-ttu-id="652a3-142">**Fehler in der aktuellen oder letzten Durchforstung**</span><span class="sxs-lookup"><span data-stu-id="652a3-142">**Errors In Current Or Last Crawl**</span></span>  
 <span data-ttu-id="652a3-143">Zeigt die Anzahl der Fehler in der aktuellen oder letzten Durchforstung an.</span><span class="sxs-lookup"><span data-stu-id="652a3-143">Displays the number of errors in current or most recent crawl.</span></span>  
  
 <span data-ttu-id="652a3-144">**Indexversion**</span><span class="sxs-lookup"><span data-stu-id="652a3-144">**Index Version**</span></span>  
 <span data-ttu-id="652a3-145">Zeigt die Schemaversion der Tabelle zum Zeitpunkt des Durchforstungsstarts an.</span><span class="sxs-lookup"><span data-stu-id="652a3-145">Displays the schema version of table at time the crawl started.</span></span>  
  
 <span data-ttu-id="652a3-146">**Zeilen in der aktuellen oder letzten Durchforstung**</span><span class="sxs-lookup"><span data-stu-id="652a3-146">**Rows In Current Or Last Crawl**</span></span>  
 <span data-ttu-id="652a3-147">Zeigt die Anzahl der aktualisierten Zeilen in der aktuellen oder letzten Durchforstung an.</span><span class="sxs-lookup"><span data-stu-id="652a3-147">Displays the number of rows updated in the current or most recent crawl.</span></span>  
  
 <span data-ttu-id="652a3-148">**Startdatum und -uhrzeit der aktuellen oder letzten Durchforstung**</span><span class="sxs-lookup"><span data-stu-id="652a3-148">**Start Date And Time Of Current Or Last Crawl**</span></span>  
 <span data-ttu-id="652a3-149">Zeigt Startdatum und -zeit der aktuellen oder letzten Durchforstung an.</span><span class="sxs-lookup"><span data-stu-id="652a3-149">Displays the date and time that the current or most recent crawl started.</span></span>  
  
 <span data-ttu-id="652a3-150">**Timestamp für nächste Durchforstung**</span><span class="sxs-lookup"><span data-stu-id="652a3-150">**Time Stamp For Next Crawl**</span></span>  
 <span data-ttu-id="652a3-151">Zeigt Datum und Zeit des nächsten Durchforstungsstarts an.</span><span class="sxs-lookup"><span data-stu-id="652a3-151">Displays the date and time that the next crawl will start.</span></span>  
  
 <span data-ttu-id="652a3-152">**Typ der aktuellen oder letzten Durchforstung**</span><span class="sxs-lookup"><span data-stu-id="652a3-152">**Type Of Current Or Last Crawl**</span></span>  
 <span data-ttu-id="652a3-153">Zeigt den Typ der aktuellen oder letzten Durchforstung an: Vollständig, Inkrementell, Aktualisieren oder Automatische Propagierung.</span><span class="sxs-lookup"><span data-stu-id="652a3-153">Displays the type of the current or most recent crawl: Full, Incremental, Update, or Auto Propagation.</span></span>  
  
 <span data-ttu-id="652a3-154">**Eindeutiger Indexname**</span><span class="sxs-lookup"><span data-stu-id="652a3-154">**Unique Index Name**</span></span>  
 <span data-ttu-id="652a3-155">Zeigt eine Liste der Namen aller Spalten in dieser Datenbank an, die einen eindeutigen, einspaltigen Index haben.</span><span class="sxs-lookup"><span data-stu-id="652a3-155">Displays a list of all of the names of columns in this database that have unique single-column indexes.</span></span> <span data-ttu-id="652a3-156">Diese Spalten können verwendet werden, um einen Volltextindex zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="652a3-156">These columns can be used to create a full-text index.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="652a3-157">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="652a3-157">See Also</span></span>  
 <span data-ttu-id="652a3-158">[Verwenden des Volltextindizierungs-Assistenten](../../relational-databases/search/use-the-full-text-indexing-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="652a3-158">[Use the Full-Text Indexing Wizard](../../relational-databases/search/use-the-full-text-indexing-wizard.md) </span></span>  
 [<span data-ttu-id="652a3-159">CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="652a3-159">CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-fulltext-index-transact-sql)  
  
  
