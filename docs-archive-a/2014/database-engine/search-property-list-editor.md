---
title: Such Eigenschaften Listen-Editor | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
f1_keywords:
- sql12.swb.spl.searchpropertylisteditor.f1
ms.assetid: 0f3ced6e-0dfd-49fc-b175-82378c3d668e
author: rothja
ms.author: jroth
ms.openlocfilehash: 6c68ec986e2c6f4f53dfec7f188ba2a120532ae4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616669"
---
# <a name="search-property-list-editor"></a><span data-ttu-id="811ad-102">Sucheigenschaftenlisten-Editor</span><span class="sxs-lookup"><span data-stu-id="811ad-102">Search Property List Editor</span></span>
  <span data-ttu-id="811ad-103">In diesem Dialogfeld können Sie einer Sucheigenschaftenliste Sucheigenschaften hinzufügen oder solche darin löschen.</span><span class="sxs-lookup"><span data-stu-id="811ad-103">Use this dialog box to add or delete search properties in a search property list.</span></span>  
  
## <a name="to-use-sql-server-management-studio-to-manage-search-property-lists"></a><span data-ttu-id="811ad-104">So verwalten Sie Sucheigenschaftenlisten in SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="811ad-104">To Use SQL Server Management Studio to Manage Search Property Lists</span></span>  
 <span data-ttu-id="811ad-105">Weitere Informationen zum Erstellen, anzeigen oder Löschen einer Such Eigenschaften Liste und zum Konfigurieren eines voll Text Indexes für die Eigenschaften Suche finden Sie unter [Suchen von Dokumenteigenschaften mit Such Eigenschaften Listen](../relational-databases/search/search-document-properties-with-search-property-lists.md).</span><span class="sxs-lookup"><span data-stu-id="811ad-105">For information about how to create, view, or delete a search property list, and about how to configure a full-text index for property searching, see [Search Document Properties with Search Property Lists](../relational-databases/search/search-document-properties-with-search-property-lists.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="811ad-106">Tastatur</span><span class="sxs-lookup"><span data-stu-id="811ad-106">Options</span></span>  
 <span data-ttu-id="811ad-107">**Eigenschaftenname**</span><span class="sxs-lookup"><span data-stu-id="811ad-107">**Property Name**</span></span>  
 <span data-ttu-id="811ad-108">Geben Sie den Namen an, der in Volltextabfragen für die Eigenschaft verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="811ad-108">Specify the name to be used to identify the property in full-text queries.</span></span> <span data-ttu-id="811ad-109">Eigenschaftsnamen können interne Leerzeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="811ad-109">A property name can contain internal spaces.</span></span> <span data-ttu-id="811ad-110">Die maximale Länge von **Eigenschaftsname** beträgt 256 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="811ad-110">The maximum length of **Property Name** is 256 characters.</span></span> <span data-ttu-id="811ad-111">Für diesen Name kann ein benutzerfreundlicher Name verwendet werden, z. B. "Autor" oder "Privatadresse", oder aber der kanonische Windows-Name der Eigenschaft, z. B. `System.Author` oder `System.Contact.HomeAddress`.</span><span class="sxs-lookup"><span data-stu-id="811ad-111">This name can be a user-friendly name, such as "Author" or "Home Address", or it can be the Windows canonical name of the property, such as `System.Author` or `System.Contact.HomeAddress`.</span></span> <span data-ttu-id="811ad-112">**Eigenschaftsname** muss die Eigenschaft innerhalb des Eigenschaftensatzes eindeutig bezeichnen.</span><span class="sxs-lookup"><span data-stu-id="811ad-112">**Property Name** must uniquely identify the property within the property set.</span></span>  
  
 <span data-ttu-id="811ad-113">Entwickler bezeichnen die Eigenschaft im [CONTAINS](/sql/t-sql/queries/contains-transact-sql) -Prädikat über den Eigenschaftsnamen.</span><span class="sxs-lookup"><span data-stu-id="811ad-113">Developers use the property name to identify the property in the [CONTAINS](/sql/t-sql/queries/contains-transact-sql) predicate.</span></span> <span data-ttu-id="811ad-114">Wenn Sie eine Eigenschaft hinzufügen, sollten Sie daher einen Wert angeben, mit dem die Eigenschaft aussagekräftig bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="811ad-114">Therefore, when adding a property it is important to specify a value that meaningfully represents the property.</span></span>  
  
 <span data-ttu-id="811ad-115">**Eigenschaftensatz-GUID**</span><span class="sxs-lookup"><span data-stu-id="811ad-115">**Property Set GUID**</span></span>  
 <span data-ttu-id="811ad-116">Geben Sie den Bezeichner des Eigenschaftensatzes an, zu dem die Eigenschaft gehört.</span><span class="sxs-lookup"><span data-stu-id="811ad-116">Specify the identifier of the property set to which the property belongs.</span></span> <span data-ttu-id="811ad-117">Bei diesem handelt es sich um einen global eindeutigen Bezeichner (GUID, Globally Unique Identifier).</span><span class="sxs-lookup"><span data-stu-id="811ad-117">This is a globally unique identifier (GUID).</span></span> <span data-ttu-id="811ad-118">Als Eigenschaftensatz wird eine Gruppe logisch aufeinander bezogener Eigenschaften bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="811ad-118">A property set is a group of logically related properties.</span></span> <span data-ttu-id="811ad-119">Informationen zum Abrufen dieses Werts finden Sie weiter unten in diesem Thema unter "Hinweise".</span><span class="sxs-lookup"><span data-stu-id="811ad-119">For information about obtaining this value, see "Remarks," later in this topic.</span></span>  
  
 <span data-ttu-id="811ad-120">**Ganzzahlige Eigenschafts-ID**</span><span class="sxs-lookup"><span data-stu-id="811ad-120">**Property Int ID**</span></span>  
 <span data-ttu-id="811ad-121">Gibt einen ganzzahligen Bezeichner für die Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="811ad-121">Specify the property integer identifier of the property.</span></span> <span data-ttu-id="811ad-122">Dieser vorab zugewiesene Wert ist eine positive ganze Zahl, die innerhalb des Eigenschaftensatzes eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="811ad-122">This pre-assigned value is a positive integer that is unique within the property set.</span></span> <span data-ttu-id="811ad-123">Informationen zum Abrufen dieses Werts finden Sie weiter unten in diesem Thema unter "Hinweise".</span><span class="sxs-lookup"><span data-stu-id="811ad-123">For information about obtaining this value, see "Remarks," later in this topic.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="811ad-124">Dokumenteigenschaften, in denen Zeichenfolgenbezeichner verwendet werden, werden von der Volltextsuche nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="811ad-124">Document properties that use string identifiers are not supported by full-text search.</span></span>  
  
 <span data-ttu-id="811ad-125">**Eigenschafts Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="811ad-125">**Property Description**</span></span>  
 <span data-ttu-id="811ad-126">Sie können auch eine Beschreibung der Eigenschaft angeben.</span><span class="sxs-lookup"><span data-stu-id="811ad-126">Optionally, specify a description of the property.</span></span> <span data-ttu-id="811ad-127">Dies ist eine Zeichenfolge mit bis zu 512 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="811ad-127">This is a string of up to 512 characters.</span></span> <span data-ttu-id="811ad-128">Eine Beschreibung kann beispielsweise Informationen zum Eigenschaftensatz der Eigenschaft oder Informationen zu einer Eigenschaft enthalten, die aus deren Namen nicht hervorgehen.</span><span class="sxs-lookup"><span data-stu-id="811ad-128">For example, a description could contain information about the property set of the property or information about a property that is not evident from its name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="811ad-129">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="811ad-129">Remarks</span></span>  
 <span data-ttu-id="811ad-130">Wenn Sie einer Sucheigenschaftenliste eine Sucheigenschaft hinzufügen möchten, müssen Sie den GUID (Globally Unique Identifier (GUID) des Eigenschaftensatzes, zu dem die Eigenschaft gehört, sowie den ganzzahligen Eigenschaftsbezeichner der Eigenschaft angeben.</span><span class="sxs-lookup"><span data-stu-id="811ad-130">To add a search property to a search property list, you must specify the globally unique identifier (GUID) of the property set to which the property belongs and the property integer identifier of the property.</span></span> <span data-ttu-id="811ad-131">Jede dieser Kombinationen muss in einer einzelnen Sucheigenschaftenliste eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="811ad-131">A given combination of these must be unique in a given search property list.</span></span> <span data-ttu-id="811ad-132">Wenn Sie versuchen, eine bereits vorhandene Kombination hinzuzufügen, tritt ein Fehler mit Fehlermeldung auf.</span><span class="sxs-lookup"><span data-stu-id="811ad-132">If you try to add an existing combination, the operation fails and issues an error.</span></span> <span data-ttu-id="811ad-133">Daher können Sie für jede Eigenschaft nur einen Namen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="811ad-133">This means that you can configure only one name for a given property.</span></span>  
  
 <span data-ttu-id="811ad-134">Die Eigenschaftsbeschreibung ist optional.</span><span class="sxs-lookup"><span data-stu-id="811ad-134">The property description is optional.</span></span>  
  
 <span data-ttu-id="811ad-135">**So konfigurieren Sie eine Sucheigenschaftenliste für einen Volltextindex**</span><span class="sxs-lookup"><span data-stu-id="811ad-135">**To configure a search property list for a full-text index**</span></span>  
  
-   [<span data-ttu-id="811ad-136">Suchen von Dokumenteigenschaften mithilfe von Sucheigenschaftenlisten</span><span class="sxs-lookup"><span data-stu-id="811ad-136">Search Document Properties with Search Property Lists</span></span>](../relational-databases/search/search-document-properties-with-search-property-lists.md)  
  
## <a name="permissions"></a><span data-ttu-id="811ad-137">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="811ad-137">Permissions</span></span>  
 <span data-ttu-id="811ad-138">Weitere Informationen finden Sie unter [Alter Search Property List &#40;Transact-SQL-&#41;](/sql/t-sql/statements/alter-search-property-list-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="811ad-138">See [ALTER SEARCH PROPERTY LIST &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-search-property-list-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="811ad-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="811ad-139">See Also</span></span>  
 <span data-ttu-id="811ad-140">[Alter Search Property List &#40;Transact-SQL-&#41;](/sql/t-sql/statements/alter-search-property-list-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="811ad-140">[ALTER SEARCH PROPERTY LIST &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-search-property-list-transact-sql) </span></span>  
 <span data-ttu-id="811ad-141">[Durchsuchen von Dokumenteigenschaften mithilfe von Such Eigenschaften Listen](../relational-databases/search/search-document-properties-with-search-property-lists.md) </span><span class="sxs-lookup"><span data-stu-id="811ad-141">[Search Document Properties with Search Property Lists](../relational-databases/search/search-document-properties-with-search-property-lists.md) </span></span>  
 [<span data-ttu-id="811ad-142">sys.registered_search_property_lists &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="811ad-142">sys.registered_search_property_lists &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-registered-search-property-lists-transact-sql)  
  
  
