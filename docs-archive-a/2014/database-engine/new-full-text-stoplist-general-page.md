---
title: Neue Volltext-Stopp Liste (Seite "Allgemein") | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
f1_keywords:
- sql12.swb.fulltextsearch.ftstoplist.general.f1
ms.assetid: 97f8e82d-82ab-4525-91c9-1ee3ae217309
author: rothja
ms.author: jroth
ms.openlocfilehash: a6272fb570b85989f38c8187e29712966862710d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621667"
---
# <a name="new-full-text-stoplist-general-page"></a><span data-ttu-id="990c4-102">Neue Volltext-Stoppliste (Seite 'Allgemein')</span><span class="sxs-lookup"><span data-stu-id="990c4-102">New Full-Text Stoplist (General Page)</span></span>
  <span data-ttu-id="990c4-103">In diesem Dialogfeld können Sie eine neue Volltext-Stoppliste erstellen.</span><span class="sxs-lookup"><span data-stu-id="990c4-103">Use this dialog box to create a full-text stoplist.</span></span> <span data-ttu-id="990c4-104">Eine *Stoppliste* ist eine Sammlung häufig verwendeter Wörter, die als *Stoppwörter*bezeichnet werden. Diese werden bei der Volltextindizierung für Tabellen, denen die Stoppliste zugewiesen wurde, weggelassen.</span><span class="sxs-lookup"><span data-stu-id="990c4-104">A *stoplist* is a set of commonly used words, called *stopwords*, that are omitted from full-text indexing for tables that use the stoplist.</span></span> <span data-ttu-id="990c4-105">Weitere Informationen finden sie unter [Konfigurieren und Verwalten von Stoppwörtern und Stopplisten für Volltextsuche](../relational-databases/search/full-text-search.md).</span><span class="sxs-lookup"><span data-stu-id="990c4-105">For more information, see [Configure and Manage Stopwords and Stoplists for Full-Text Search](../relational-databases/search/full-text-search.md).</span></span>  
  
 <span data-ttu-id="990c4-106">**So erstellen Sie eine Stoppliste mit SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="990c4-106">**To use SQL Server Management Studio to create a stoplist**</span></span>  
  
-   [<span data-ttu-id="990c4-107">Konfigurieren und Verwalten von Stoppwörtern und Stopplisten für Volltextsuche</span><span class="sxs-lookup"><span data-stu-id="990c4-107">Configure and Manage Stopwords and Stoplists for Full-Text Search</span></span>](../relational-databases/search/full-text-search.md)  
  
## <a name="options"></a><span data-ttu-id="990c4-108">Tastatur</span><span class="sxs-lookup"><span data-stu-id="990c4-108">Options</span></span>  
 <span data-ttu-id="990c4-109">**Name der Volltext-Stoppliste**</span><span class="sxs-lookup"><span data-stu-id="990c4-109">**Full-text stoplist name**</span></span>  
 <span data-ttu-id="990c4-110">Geben Sie hier den Namen für die Volltext-Stoppliste ein.</span><span class="sxs-lookup"><span data-stu-id="990c4-110">Enter the name of the full-text stoplist.</span></span>  
  
 <span data-ttu-id="990c4-111">**Besitzer**</span><span class="sxs-lookup"><span data-stu-id="990c4-111">**Owner**</span></span>  
 <span data-ttu-id="990c4-112">Geben Sie den Besitzer der Volltext-Stoppliste an.</span><span class="sxs-lookup"><span data-stu-id="990c4-112">Specify the owner of the full-text stoplist.</span></span> <span data-ttu-id="990c4-113">Wenn Sie sich selbst, d. h. den aktuellen Benutzer, als Besitzer angeben möchten, lassen Sie dieses Feld leer.</span><span class="sxs-lookup"><span data-stu-id="990c4-113">If you want ownership to be assigned to yourself, that is, to the current user, leave this field empty.</span></span>  
  
 <span data-ttu-id="990c4-114">Klicken Sie auf die Schaltfläche zum Durchsuchen, um einen anderen Benutzer auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="990c4-114">To specify a different user, click the browse button.</span></span>  
  
### <a name="create-stoplist-options"></a><span data-ttu-id="990c4-115">Optionen zur Stopplistenerstellung</span><span class="sxs-lookup"><span data-stu-id="990c4-115">Create stoplist options</span></span>  
 <span data-ttu-id="990c4-116">Klicken Sie auf eine der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="990c4-116">Click one of the following create options:</span></span>  
  
 <span data-ttu-id="990c4-117">**Leere Stoppliste erstellen**</span><span class="sxs-lookup"><span data-stu-id="990c4-117">**Create an empty stoplist**</span></span>  
 <span data-ttu-id="990c4-118">Die neue Stoppliste enthält keine Stoppwörter.</span><span class="sxs-lookup"><span data-stu-id="990c4-118">The new stoplist will not contain any stopwords.</span></span>  
  
 <span data-ttu-id="990c4-119">**Aus der Systemstoppliste erstellen**</span><span class="sxs-lookup"><span data-stu-id="990c4-119">**Create from the system stoplist**</span></span>  
 <span data-ttu-id="990c4-120">Die neue Stoppliste wird aus der Stoppliste erstellt, die standardmäßig in der [Ressourcendatenbank](../relational-databases/databases/resource-database.md)enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="990c4-120">The new stoplist is created from the stoplist that exists by default in the [Resource database](../relational-databases/databases/resource-database.md).</span></span>  
  
 <span data-ttu-id="990c4-121">**Aus vorhandener Volltext-Stoppliste erstellen**</span><span class="sxs-lookup"><span data-stu-id="990c4-121">**Create from an existing full-text stoplist**</span></span>  
 <span data-ttu-id="990c4-122">Die neue Stoppliste wird durch Kopieren einer vorhandenen Stoppliste erstellt.</span><span class="sxs-lookup"><span data-stu-id="990c4-122">The new stoplist is created by copying an existing stoplist.</span></span>  
  
 <span data-ttu-id="990c4-123">**Quelldatenbank**</span><span class="sxs-lookup"><span data-stu-id="990c4-123">**Source database**</span></span>  
 <span data-ttu-id="990c4-124">Gibt den Namen der Datenbank an, zu der die vorhandene Stoppliste gehört.</span><span class="sxs-lookup"><span data-stu-id="990c4-124">Specifies the name of the database to which the existing stoplist belongs.</span></span> <span data-ttu-id="990c4-125">Standardmäßig ist die aktuelle Datenbank ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="990c4-125">The current database is selected by default.</span></span> <span data-ttu-id="990c4-126">Sie können optional eine andere Datenbank in der Liste auswählen.</span><span class="sxs-lookup"><span data-stu-id="990c4-126">Optionally, select a different database from the list box.</span></span>  
  
 <span data-ttu-id="990c4-127">**Quellstoppliste**</span><span class="sxs-lookup"><span data-stu-id="990c4-127">**Source stoplist**</span></span>  
 <span data-ttu-id="990c4-128">Gibt den Namen einer vorhandenen Stoppliste an.</span><span class="sxs-lookup"><span data-stu-id="990c4-128">Specifies the name of an existing stoplist.</span></span> <span data-ttu-id="990c4-129">Wählen Sie aus der Liste der verfügbaren Stoppliste eine Stoppliste aus, die als Quelle verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="990c4-129">From the list of available stoplists, select the one to use as the source.</span></span> <span data-ttu-id="990c4-130">Die verfügbaren Stopplisten werden in der Reihenfolge aufgelistet, in der sie im Objekt-Explorer angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="990c4-130">The available stoplists are listed in the order in which they appear in Object Explorer.</span></span>  
  
 <span data-ttu-id="990c4-131">Wenn eine in den Stoppwörtern der Quellstoppliste angegebene Sprache in der aktuellen Datenbank nicht registriert ist, wird CREATE FULLTEXT STOPLIST erfolgreich ausgeführt. Allerdings werden Warnungen zurückgegeben, und die entsprechenden Stoppwörter werden nicht hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="990c4-131">If any languages specified in the stop words of the source stoplist are not registered in the current database, CREATE FULLTEXT STOPLIST succeeds, but warning(s) are returned and the corresponding stop words are not added.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="990c4-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="990c4-132">See Also</span></span>  
 <span data-ttu-id="990c4-133">[ALTER FULLTEXT STOPLIST &#40;Transact-SQL-&#41;](/sql/t-sql/statements/alter-fulltext-stoplist-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="990c4-133">[ALTER FULLTEXT STOPLIST &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-stoplist-transact-sql) </span></span>  
 <span data-ttu-id="990c4-134">[CREATE FULLTEXT STOPLIST &#40;Transact-SQL-&#41;](/sql/t-sql/statements/create-fulltext-stoplist-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="990c4-134">[CREATE FULLTEXT STOPLIST &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-stoplist-transact-sql) </span></span>  
 <span data-ttu-id="990c4-135">[DROP FULLTEXT STOPLIST &#40;Transact-SQL-&#41;](/sql/t-sql/statements/drop-fulltext-stoplist-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="990c4-135">[DROP FULLTEXT STOPLIST &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-fulltext-stoplist-transact-sql) </span></span>  
 <span data-ttu-id="990c4-136">[Konfigurieren und Verwalten von Stopp Wörtern und Stopp Listen für die voll Text Suche](../relational-databases/search/full-text-search.md) </span><span class="sxs-lookup"><span data-stu-id="990c4-136">[Configure and Manage Stopwords and Stoplists for Full-Text Search](../relational-databases/search/full-text-search.md) </span></span>  
 [<span data-ttu-id="990c4-137">sys.fulltext_stoplists &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="990c4-137">sys.fulltext_stoplists &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-fulltext-stoplists-transact-sql)  
  
  
