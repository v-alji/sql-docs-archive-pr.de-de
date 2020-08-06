---
title: Neue Such Eigenschaften Liste | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
f1_keywords:
- sql12.swb.spl.newsearchpropertylist.f1
ms.assetid: ffca78e9-8608-4b15-bd38-b2d78da4247a
author: rothja
ms.author: jroth
ms.openlocfilehash: 48c9e475b380d5f0c7310e33717f261c38acbbd4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621653"
---
# <a name="new-search-property-list"></a><span data-ttu-id="546e4-102">Neue Sucheigenschaftenliste</span><span class="sxs-lookup"><span data-stu-id="546e4-102">New Search Property List</span></span>
  <span data-ttu-id="546e4-103">In diesem Dialogfeld können Sie eine Sucheigenschaftenliste erstellen.</span><span class="sxs-lookup"><span data-stu-id="546e4-103">Use this dialog box to create a search property list.</span></span>  
  
## <a name="options"></a><span data-ttu-id="546e4-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="546e4-104">Options</span></span>  
 <span data-ttu-id="546e4-105">**Name der Sucheigenschaftenliste**</span><span class="sxs-lookup"><span data-stu-id="546e4-105">**Search property list name**</span></span>  
 <span data-ttu-id="546e4-106">Geben Sie den Namen der Sucheigenschaftenliste ein.</span><span class="sxs-lookup"><span data-stu-id="546e4-106">Enter the name of the search property list.</span></span>  
  
 <span data-ttu-id="546e4-107">**Besitzer**</span><span class="sxs-lookup"><span data-stu-id="546e4-107">**Owner**</span></span>  
 <span data-ttu-id="546e4-108">Geben Sie den Besitzer der Sucheigenschaftenliste an.</span><span class="sxs-lookup"><span data-stu-id="546e4-108">Specify the owner of the search property list.</span></span> <span data-ttu-id="546e4-109">Wenn Sie sich selbst, d. h. den aktuellen Benutzer, als Besitzer angeben möchten, lassen Sie dieses Feld leer.</span><span class="sxs-lookup"><span data-stu-id="546e4-109">If you want ownership to be assigned to yourself, that is, to the current user, leave this field empty.</span></span> <span data-ttu-id="546e4-110">Klicken Sie auf die Schaltfläche zum Durchsuchen, um einen anderen Benutzer auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="546e4-110">To specify a different user, click the browse button.</span></span>  
  
### <a name="create-search-property-list-options"></a><span data-ttu-id="546e4-111">Optionen zum Erstellen von Sucheigenschaftenlisten</span><span class="sxs-lookup"><span data-stu-id="546e4-111">Create Search Property List Options</span></span>  
 <span data-ttu-id="546e4-112">Klicken Sie auf eine der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="546e4-112">Click one of the following options:</span></span>  
  
 <span data-ttu-id="546e4-113">**Erstellen einer leeren Sucheigenschaftenliste**</span><span class="sxs-lookup"><span data-stu-id="546e4-113">**Create an empty search property list**</span></span>  
 <span data-ttu-id="546e4-114">Erstellt eine Sucheigenschaftenliste ohne Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="546e4-114">Creates a search property list without any properties.</span></span>  
  
 <span data-ttu-id="546e4-115">**Von einer vorhandenen Sucheigenschaftenliste erstellen**</span><span class="sxs-lookup"><span data-stu-id="546e4-115">**Create from an existing search property list**</span></span>  
 <span data-ttu-id="546e4-116">Kopiert die Eigenschaften aus einer vorhandenen Sucheigenschaftenliste in die neue Eigenschaftenliste.</span><span class="sxs-lookup"><span data-stu-id="546e4-116">Copies the properties of an existing search property list into the new property list.</span></span> <span data-ttu-id="546e4-117">Sucheigenschaftenlisten bilden Datenbankobjekte, deshalb müssen Sie die Datenbank angeben, die die zu kopierende Eigenschaftenliste enthält.</span><span class="sxs-lookup"><span data-stu-id="546e4-117">Search property lists are database objects, so you must specify the database that contains the property list that you want to copy.</span></span>  
  
 <span data-ttu-id="546e4-118">**Quelldatenbank**</span><span class="sxs-lookup"><span data-stu-id="546e4-118">**Source database**</span></span>  
 <span data-ttu-id="546e4-119">Geben Sie den Namen der Datenbank an, zu der die vorhandene Sucheigenschaftenliste gehört.</span><span class="sxs-lookup"><span data-stu-id="546e4-119">Specify the name of the database to which the existing search property list belongs.</span></span> <span data-ttu-id="546e4-120">Standardmäßig ist die aktuelle Datenbank ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="546e4-120">The current database is selected by default.</span></span> <span data-ttu-id="546e4-121">Wenn die aktuelle Verbindung einer Benutzer-ID in dieser Datenbank zugeordnet ist, können Sie im Listenfeld optional eine andere Datenbank auswählen.</span><span class="sxs-lookup"><span data-stu-id="546e4-121">Optionally, you can use the list box to select another database, if your current connection is associated with a user ID in that database.</span></span>  
  
 <span data-ttu-id="546e4-122">**Quelle für Sucheigenschaftenliste**</span><span class="sxs-lookup"><span data-stu-id="546e4-122">**Source search property list**</span></span>  
 <span data-ttu-id="546e4-123">Wählen Sie in den zur ausgewählten Datenbank gehörenden Listen den Namen einer vorhandenen Sucheigenschaftenliste aus.</span><span class="sxs-lookup"><span data-stu-id="546e4-123">Select the name of an existing search property list from those belonging to the selected database.</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="546e4-124">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="546e4-124">Permissions</span></span>  
 <span data-ttu-id="546e4-125">Weitere Informationen finden Sie unter [Create Search Property List &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-search-property-list-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="546e4-125">See [CREATE SEARCH PROPERTY LIST &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-search-property-list-transact-sql).</span></span>  
  
## <a name="to-use-sql-server-management-studio-to-manage-search-property-lists"></a><span data-ttu-id="546e4-126">So verwalten Sie Sucheigenschaftenlisten in SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="546e4-126">To Use SQL Server Management Studio to Manage Search Property Lists</span></span>  
 <span data-ttu-id="546e4-127">Informationen zum Erstellen, Anzeigen, Ändern oder Löschen einer Sucheigenschaftenliste und zum Konfigurieren eines Volltextindexes für die Eigenschaftensuche finden Sie unter [Search Document Properties with Search Property Lists](../relational-databases/search/search-document-properties-with-search-property-lists.md).</span><span class="sxs-lookup"><span data-stu-id="546e4-127">For information about how to create, view, change, or delete a search property list, and about how to configure a full-text index for property searching, see [Search Document Properties with Search Property Lists](../relational-databases/search/search-document-properties-with-search-property-lists.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="546e4-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="546e4-128">See Also</span></span>  
 <span data-ttu-id="546e4-129">[Erstellen einer Such Eigenschaften Liste &#40;Transact-SQL-&#41;](/sql/t-sql/statements/create-search-property-list-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="546e4-129">[CREATE SEARCH PROPERTY LIST &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-search-property-list-transact-sql) </span></span>  
 <span data-ttu-id="546e4-130">[Durchsuchen von Dokumenteigenschaften mithilfe von Such Eigenschaften Listen](../relational-databases/search/search-document-properties-with-search-property-lists.md) </span><span class="sxs-lookup"><span data-stu-id="546e4-130">[Search Document Properties with Search Property Lists](../relational-databases/search/search-document-properties-with-search-property-lists.md) </span></span>  
 [<span data-ttu-id="546e4-131">sys.registered_search_property_lists &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="546e4-131">sys.registered_search_property_lists &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-registered-search-property-lists-transact-sql)  
  
  
