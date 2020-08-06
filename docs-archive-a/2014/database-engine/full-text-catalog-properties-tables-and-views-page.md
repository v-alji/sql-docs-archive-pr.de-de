---
title: Voll Text Katalog-Eigenschaften (Seite "Tabellen und Sichten") | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
f1_keywords:
- sql12.swb.fulltextsearch.ftcatalogproperties.tablesviews.f1
ms.assetid: 2d45fcd2-0f0f-4167-9027-316d6696c106
author: rothja
ms.author: jroth
ms.openlocfilehash: eb4d968af6c550d19fbb8934b5d76a1bd63cb8da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724090"
---
# <a name="full-text-catalog-properties-tables-and-views-page"></a><span data-ttu-id="48982-102">Volltextkatalog-Eigenschaften (Seite „Tabellen und Sichten“)</span><span class="sxs-lookup"><span data-stu-id="48982-102">Full-Text Catalog Properties (Tables and Views Page)</span></span>
  <span data-ttu-id="48982-103">In diesem Dialogfeld können Sie die Tabellen und Sichten anzeigen oder bearbeiten, die dem Volltextkatalog zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="48982-103">Use this dialog page to view or modify the tables and views that are assigned to the full-text catalog.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="48982-104">Liste der Benutzeroberflächenelemente</span><span class="sxs-lookup"><span data-stu-id="48982-104">UI element list</span></span>  
 <span data-ttu-id="48982-105">**Alle geeigneten Tabellen-/Sichtobjekte in dieser Datenbank**</span><span class="sxs-lookup"><span data-stu-id="48982-105">**All eligible table/view objects in this database**</span></span>  
 <span data-ttu-id="48982-106">Listet alle Tabellen und Sichten auf, für die ein eindeutiger Index definiert ist, die jedoch noch nicht Bestandteil des Volltextkatalogs sind.</span><span class="sxs-lookup"><span data-stu-id="48982-106">Lists the tables and views that have a unique index defined on them, but are not already a part of the full-text catalog.</span></span> <span data-ttu-id="48982-107">Wenn Sie eine Tabelle oder Sicht auswählen und dem Katalog zuweisen möchten, wählen Sie die Elemente im Listenfeld aus, und klicken Sie auf die Schaltfläche "->".</span><span class="sxs-lookup"><span data-stu-id="48982-107">To select a table or view and assign it to the catalog, select the items in the list box and press the "->" button.</span></span>  
  
 <span data-ttu-id="48982-108">**Dem Katalog zugewiesene Tabellen-/Sichtobjekte**</span><span class="sxs-lookup"><span data-stu-id="48982-108">**Table/view objects assigned to the catalog**</span></span>  
 <span data-ttu-id="48982-109">Listet die Tabellen und Sichten auf, die zurzeit dem Volltextkatalog zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="48982-109">Lists the tables and views that are currently assigned to the full-text catalog</span></span>  
  
## <a name="selected-object-properties"></a><span data-ttu-id="48982-110">Ausgewählte Objekteigenschaften</span><span class="sxs-lookup"><span data-stu-id="48982-110">Selected Object Properties</span></span>  
 <span data-ttu-id="48982-111">**Eigenschaften des ausgewählten Objekts**</span><span class="sxs-lookup"><span data-stu-id="48982-111">**Selected object properties**</span></span>  
 <span data-ttu-id="48982-112">Zeigt die Eigenschaften des ausgewählten Objekts im Listenfeld der dem Katalog zugewiesenen Objekte an.</span><span class="sxs-lookup"><span data-stu-id="48982-112">Displays the properties of the selected object in the list box of objects assigned to the catalog.</span></span>  
  
 <span data-ttu-id="48982-113">**Eindeutiger Index**</span><span class="sxs-lookup"><span data-stu-id="48982-113">**Unique Index**</span></span>  
 <span data-ttu-id="48982-114">Listet die verfügbaren eindeutigen Indizes der Tabelle oder Sicht auf.</span><span class="sxs-lookup"><span data-stu-id="48982-114">Lists the available unique indexes of the table or view.</span></span>  
  
 <span data-ttu-id="48982-115">**Die Tabelle ist volltextfähig.**</span><span class="sxs-lookup"><span data-stu-id="48982-115">**Table is full-text enabled**</span></span>  
 <span data-ttu-id="48982-116">Aktivieren Sie dieses Kontrollkästchen, um den Volltextindex für die Tabelle zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="48982-116">Select this check box to enable the full-text index on the table.</span></span> <span data-ttu-id="48982-117">Deaktivieren Sie das Kontrollkästchen, um den Volltextindex zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="48982-117">Clear the check box to disable the full-text index.</span></span>  
  
## <a name="eligible-columns-grid"></a><span data-ttu-id="48982-118">Geeignetes Spaltenraster</span><span class="sxs-lookup"><span data-stu-id="48982-118">Eligible Columns Grid</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="48982-119">**Verfügbare Spalten**</span><span class="sxs-lookup"><span data-stu-id="48982-119">**Available Columns**</span></span>|<span data-ttu-id="48982-120">Zeigt alle volltextindizierten Spalten an.</span><span class="sxs-lookup"><span data-stu-id="48982-120">Displays all the columns that are full-text indexed.</span></span> <span data-ttu-id="48982-121">Aktivieren Sie ein Kontrollkästchen, um eine Spalte zum Volltextindex hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="48982-121">Select a check box to add a column to the full-text index.</span></span>|  
|<span data-ttu-id="48982-122">**Sprache für die Wörtertrennung**</span><span class="sxs-lookup"><span data-stu-id="48982-122">**Language for Word Breaker**</span></span>|<span data-ttu-id="48982-123">Zeigt die Sprache des Worttrennmoduls an.</span><span class="sxs-lookup"><span data-stu-id="48982-123">Displays the language of the word breaker.</span></span>|  
|<span data-ttu-id="48982-124">**Datentypspalte**</span><span class="sxs-lookup"><span data-stu-id="48982-124">**Data Type Column**</span></span>|<span data-ttu-id="48982-125">Listet den Namen der Spalte in der Tabelle auf, die den Dokumenttyp der Spalte enthält, die in **Verfügbare Spalten** aufgelistet ist, wenn die Spalte eine- `varbinary(max)` oder-Spalte ist `image` .</span><span class="sxs-lookup"><span data-stu-id="48982-125">Lists the name of the column in the table that holds the document type of the column listed in **Available Columns** if the column is a `varbinary(max)` or `image` column.</span></span>|  
|<span data-ttu-id="48982-126">**Statistische Semantik**</span><span class="sxs-lookup"><span data-stu-id="48982-126">**Statistical Semantics**</span></span>|<span data-ttu-id="48982-127">Wählen Sie aus, ob die semantische Indizierung für die ausgewählte Spalte aktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="48982-127">Select whether to enable semantic indexing for the selected column.</span></span> <span data-ttu-id="48982-128">Weitere Informationen finden Sie unter [Semantische Suche &#40;SQL Server&#41;](../relational-databases/search/semantic-search-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="48982-128">For more information, see [Semantic Search &#40;SQL Server&#41;](../relational-databases/search/semantic-search-sql-server.md).</span></span><br /><br /> <span data-ttu-id="48982-129">Wenn Sie eine **Sprache** vor der Option **Statistische Semantik**auswählen und die ausgewählte Sprache über kein zugeordnetes semantisches Sprachmodell verfügt, ist das Kontrollkästchen **Statistische Semantik** deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="48982-129">If you select a **Language** prior to selecting **Statistical Semantics**, and the selected language does not have an associated Semantic Language Model, then the **Statistical Semantics** checkbox is disabled.</span></span> <span data-ttu-id="48982-130">Wenn Sie **Statistische Semantik** vor einer **Sprache**auswählen, werden im Dropdown-Kombinationsfeld nur die Sprachen angezeigt, für die das semantische Sprachmodell unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="48982-130">If you select **Statistical Semantics** prior to selecting a **Language**, the languages available in the drop-down combo box will be restricted to those for which there is Semantic Language Model support.</span></span>|  
  
## <a name="track-changes"></a><span data-ttu-id="48982-131">Nachverfolgen von Änderungen</span><span class="sxs-lookup"><span data-stu-id="48982-131">Track Changes</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="48982-132">**Automatisch**</span><span class="sxs-lookup"><span data-stu-id="48982-132">**Automatic**</span></span>|<span data-ttu-id="48982-133">Der Volltextindex wird automatisch aktualisiert, wenn in der zugrunde liegenden Tabelle Daten geändert, hinzugefügt oder gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="48982-133">The full-text index is automatically updated when the data in the underlying table is modified, added, or deleted.</span></span>|  
|<span data-ttu-id="48982-134">**Manuell**</span><span class="sxs-lookup"><span data-stu-id="48982-134">**Manual**</span></span>|<span data-ttu-id="48982-135">Wenn indizierte Daten geändert, hinzugefügt oder gelöscht werden, protokolliert [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] die Änderungen.</span><span class="sxs-lookup"><span data-stu-id="48982-135">When data is modified, added, or deleted in the indexed data, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] tracks the changes.</span></span> <span data-ttu-id="48982-136">Wenn für die Nachverfolgung von Änderungen die Option **Manuell** aktiviert ist, werden die Änderungen nicht automatisch in den Index übernommen.</span><span class="sxs-lookup"><span data-stu-id="48982-136">When **Manual** change tracking is in effect, the index is not automatically updated with these changes.</span></span> <span data-ttu-id="48982-137">Stattdessen kann ein Administrator die Änderungen manuell mithilfe einer [ALTER FULLTEXT INDEX ... START UPDATE POPULATION](/sql/t-sql/statements/alter-fulltext-index-transact-sql) -Anweisung anwenden.</span><span class="sxs-lookup"><span data-stu-id="48982-137">Instead, an administrator can apply the changes manually by using an [ALTER FULLTEXT INDEX ... START UPDATE POPULATION](/sql/t-sql/statements/alter-fulltext-index-transact-sql) statement.</span></span>|  
|<span data-ttu-id="48982-138">**Änderungen nicht nachverfolgen**</span><span class="sxs-lookup"><span data-stu-id="48982-138">**Do not track change**</span></span>|<span data-ttu-id="48982-139">Wenn diese Option aktiviert ist, werden Änderungen an den indizierten Daten im Katalog nicht aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="48982-139">With this option in effect, changes to the indexed data in the catalog are not recorded.</span></span> <span data-ttu-id="48982-140">Ein Administrator muss den Index mithilfe von ALTER FULLTEXT INDEX mit FULL POPULATION oder INCREMENTAL POPULATION erstellen.</span><span class="sxs-lookup"><span data-stu-id="48982-140">An administrator must build the index by using ALTER FULLTEXT INDEX with either FULL POPULATION or INCREMENTAL POPULATION.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="48982-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="48982-141">See Also</span></span>  
 <span data-ttu-id="48982-142">[CREATE FULLTEXT CATALOG &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-catalog-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="48982-142">[CREATE FULLTEXT CATALOG &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-catalog-transact-sql) </span></span>  
 <span data-ttu-id="48982-143">[ALTER FULLTEXT CATALOG &#40;Transact-SQL-&#41;](/sql/t-sql/statements/alter-fulltext-catalog-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="48982-143">[ALTER FULLTEXT CATALOG &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-catalog-transact-sql) </span></span>  
 [<span data-ttu-id="48982-144">Auffüllen von Volltextindizes</span><span class="sxs-lookup"><span data-stu-id="48982-144">Populate Full-Text Indexes</span></span>](../relational-databases/indexes/indexes.md)  
  
  
