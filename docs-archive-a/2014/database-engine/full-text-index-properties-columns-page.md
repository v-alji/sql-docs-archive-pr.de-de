---
title: Voll Text Index-Eigenschaften (Seite ' Spalten ') | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
f1_keywords:
- sql12.swb.fulltextsearch.fulltextindexproperties.columns.f1
ms.assetid: 75e52edb-0d07-4393-9345-8b5af4561e35
author: rothja
ms.author: jroth
ms.openlocfilehash: f947af04463948ef551c6df866d5a306c248c6b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622843"
---
# <a name="full-text-index-properties-columns-page"></a><span data-ttu-id="dae9a-102">Volltextindex-Eigenschaften (Seite "Spalten")</span><span class="sxs-lookup"><span data-stu-id="dae9a-102">Full-Text Index Properties (Columns Page)</span></span>
  <span data-ttu-id="dae9a-103">**So zeigen Sie die Eigenschaften eines Volltextindexes an oder ändern diese**</span><span class="sxs-lookup"><span data-stu-id="dae9a-103">**To view or change the properties of a full-text index**</span></span>  
  
-   [<span data-ttu-id="dae9a-104">Verwalten von Volltextindizes</span><span class="sxs-lookup"><span data-stu-id="dae9a-104">Manage Full-Text Indexes</span></span>](../relational-databases/indexes/indexes.md)  
  
## <a name="ui-element-list"></a><span data-ttu-id="dae9a-105">Liste der Benutzeroberflächenelemente</span><span class="sxs-lookup"><span data-stu-id="dae9a-105">UI element list</span></span>  
 <span data-ttu-id="dae9a-106">**Eindeutiger Index**</span><span class="sxs-lookup"><span data-stu-id="dae9a-106">**Unique index**</span></span>  
 <span data-ttu-id="dae9a-107">Wählen Sie einen Index aus der Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="dae9a-107">Select an index from the drop down list.</span></span> <span data-ttu-id="dae9a-108">Der Index muss genau eine Schlüsselspalte haben, muss eindeutig sein und darf keine NULL-Werte zulassen.</span><span class="sxs-lookup"><span data-stu-id="dae9a-108">The index must be a single-key-column, unique, non-nullable index.</span></span>  
  
 <span data-ttu-id="dae9a-109">**Geeignete Spalten für die Volltextindizierung auswählen**</span><span class="sxs-lookup"><span data-stu-id="dae9a-109">**Select the eligible columns that will be full-text indexed**</span></span>  
 <span data-ttu-id="dae9a-110">Im Raster werden die Tabellenspalten angezeigt, die für diesen Volltextindex verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="dae9a-110">The grid displays the table columns that are available for this full-text index.</span></span> <span data-ttu-id="dae9a-111">Derezit volltextindizierte Spalten sind markiert.</span><span class="sxs-lookup"><span data-stu-id="dae9a-111">Columns that are currently full-text indexed are checked.</span></span> <span data-ttu-id="dae9a-112">Optional können Sie weitere Spalten markieren, die volltextindiziert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="dae9a-112">Optionally, you can check additional columns that you want to be full-text indexed.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="dae9a-113">Stellen Sie sicher, dass mindestens eine Spalte markiert ist, und klicken Sie dann auf OK.</span><span class="sxs-lookup"><span data-stu-id="dae9a-113">Ensure that at least one column is checked before you click OK.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="dae9a-114">**Verfügbare Spalten**</span><span class="sxs-lookup"><span data-stu-id="dae9a-114">**Available Columns**</span></span>|<span data-ttu-id="dae9a-115">Der Spaltenname.</span><span class="sxs-lookup"><span data-stu-id="dae9a-115">The column name.</span></span>|  
|<span data-ttu-id="dae9a-116">**Sprache für die Wörtertrennung**</span><span class="sxs-lookup"><span data-stu-id="dae9a-116">**Language for Word Breaker**</span></span>|<span data-ttu-id="dae9a-117">Die Sprache, deren Wörtertrennung und Wortstammerkennung eine linguistische Analyse aller volltextindizierten Daten ausführen.</span><span class="sxs-lookup"><span data-stu-id="dae9a-117">The language whose word breakers and stemmers perform linguistic analysis on all full-text indexed data.</span></span><br /><br /> <span data-ttu-id="dae9a-118">Weitere Informationen finden Sie unter [Konfigurieren und Verwalten von Wörter Trennungen und Wort](../relational-databases/search/configure-and-manage-word-breakers-and-stemmers-for-search.md) Stamm Erkennungen für die Suche und [Auswählen einer Sprache beim Erstellen eines voll Text Indexes](../relational-databases/search/choose-a-language-when-creating-a-full-text-index.md).</span><span class="sxs-lookup"><span data-stu-id="dae9a-118">For more information, see [Configure and Manage Word Breakers and Stemmers for Search](../relational-databases/search/configure-and-manage-word-breakers-and-stemmers-for-search.md) and [Choose a Language When Creating a Full-Text Index](../relational-databases/search/choose-a-language-when-creating-a-full-text-index.md).</span></span>|  
|<span data-ttu-id="dae9a-119">**Type**</span><span class="sxs-lookup"><span data-stu-id="dae9a-119">**Type**</span></span>|<span data-ttu-id="dae9a-120">Der Name der Tabellenspalte, die den Dokumenttyp der ausgewählten Spalte enthält.</span><span class="sxs-lookup"><span data-stu-id="dae9a-120">The name of the table column that holds the document type of the selected column.</span></span> <span data-ttu-id="dae9a-121">Dies ist eine schreibgeschützte Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="dae9a-121">This is a read-only property.</span></span>|  
|<span data-ttu-id="dae9a-122">**Statistische Semantik**</span><span class="sxs-lookup"><span data-stu-id="dae9a-122">**Statistical Semantics**</span></span>|<span data-ttu-id="dae9a-123">Wählen Sie aus, ob die semantische Indizierung für die ausgewählte Spalte aktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="dae9a-123">Select whether to enable semantic indexing for the selected column.</span></span> <span data-ttu-id="dae9a-124">Weitere Informationen finden Sie unter [Semantische Suche &#40;SQL Server&#41;](../relational-databases/search/semantic-search-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="dae9a-124">For more information, see [Semantic Search &#40;SQL Server&#41;](../relational-databases/search/semantic-search-sql-server.md).</span></span><br /><br /> <span data-ttu-id="dae9a-125">Wenn Sie eine **Sprache** vor der Option **Statistische Semantik**auswählen und die ausgewählte Sprache über kein zugeordnetes semantisches Sprachmodell verfügt, ist das Kontrollkästchen **Statistische Semantik** deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="dae9a-125">If you select a **Language** prior to selecting **Statistical Semantics**, and the selected language does not have an associated Semantic Language Model, then the **Statistical Semantics** checkbox is disabled.</span></span> <span data-ttu-id="dae9a-126">Wenn Sie **Statistische Semantik** vor einer **Sprache**auswählen, werden im Dropdown-Kombinationsfeld nur die Sprachen angezeigt, für die das semantische Sprachmodell unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="dae9a-126">If you select **Statistical Semantics** prior to selecting a **Language**, the languages available in the drop-down combo box will be restricted to those for which there is Semantic Language Model support.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dae9a-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dae9a-127">See Also</span></span>  
 [<span data-ttu-id="dae9a-128">Auffüllen von Volltextindizes</span><span class="sxs-lookup"><span data-stu-id="dae9a-128">Populate Full-Text Indexes</span></span>](../relational-databases/search/populate-full-text-indexes.md)  
  
  
