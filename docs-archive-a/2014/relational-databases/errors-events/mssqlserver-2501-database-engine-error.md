---
title: MSSQLSERVER_2501 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2501 (Database Engine error)
ms.assetid: 895aafe3-a4e7-4ed8-acc5-93be76ef3664
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 200997dcfe7bf8a5933b9fce492daabd5baffd04
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718184"
---
# <a name="mssqlserver_2501"></a><span data-ttu-id="d25be-102">MSSQLSERVER_2501</span><span class="sxs-lookup"><span data-stu-id="d25be-102">MSSQLSERVER_2501</span></span>
    
## <a name="details"></a><span data-ttu-id="d25be-103">Details</span><span class="sxs-lookup"><span data-stu-id="d25be-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d25be-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="d25be-104">Product Name</span></span>|<span data-ttu-id="d25be-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d25be-105">SQL Server</span></span>|  
|<span data-ttu-id="d25be-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="d25be-106">Event ID</span></span>|<span data-ttu-id="d25be-107">2501</span><span class="sxs-lookup"><span data-stu-id="d25be-107">2501</span></span>|  
|<span data-ttu-id="d25be-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="d25be-108">Event Source</span></span>|<span data-ttu-id="d25be-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d25be-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d25be-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="d25be-110">Component</span></span>|<span data-ttu-id="d25be-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="d25be-111">SQLEngine</span></span>|  
|<span data-ttu-id="d25be-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="d25be-112">Symbolic Name</span></span>|<span data-ttu-id="d25be-113">DBCC_NO_SUCH_TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d25be-113">DBCC_NO_SUCH_TABLE_NAME</span></span>|  
|<span data-ttu-id="d25be-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="d25be-114">Message Text</span></span>|<span data-ttu-id="d25be-115">Eine Tabelle oder ein Objekt mit dem Namen 'NAME' wurde nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="d25be-115">Cannot find a table or object with the name 'NAME'.</span></span> <span data-ttu-id="d25be-116">Überprüfen Sie den Systemkatalog.</span><span class="sxs-lookup"><span data-stu-id="d25be-116">Check the system catalog.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d25be-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="d25be-117">Explanation</span></span>  
 <span data-ttu-id="d25be-118">Das angegebene Objekt wurde nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="d25be-118">The specified object cannot be found.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="d25be-119">Mögliche Ursachen</span><span class="sxs-lookup"><span data-stu-id="d25be-119">Possible Causes</span></span>  
 <span data-ttu-id="d25be-120">Dieser Fehler kann durch eines der folgenden Probleme verursacht werden:</span><span class="sxs-lookup"><span data-stu-id="d25be-120">This error can be caused by one of the following problems:</span></span>  
  
-   <span data-ttu-id="d25be-121">Das Objekt ist nicht richtig angegeben.</span><span class="sxs-lookup"><span data-stu-id="d25be-121">The object is not specified correctly.</span></span>  
  
-   <span data-ttu-id="d25be-122">Das Objekt ist nicht vorhanden, oder das Objekt wurde entfernt, bevor von einer Anweisung versucht wurde, es zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="d25be-122">The object does not exist, or the object was dropped before a statement tried to use it.</span></span>  
  
-   <span data-ttu-id="d25be-123">Das Objekt ist möglicherweise vorhanden, es konnte jedoch nicht für den Benutzer verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="d25be-123">The object might exist, but could not be exposed to the user.</span></span> <span data-ttu-id="d25be-124">Beispielsweise besitzt der Benutzer möglicherweise keine Berechtigungen für das Objekt, oder das Objekt stellt eine interne Tabelle dar, die von einem Benutzer nicht angezeigt werden konnte.</span><span class="sxs-lookup"><span data-stu-id="d25be-124">For example, the user might not have permissions on the object, or the object is an internal table that could not be seen by a user.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d25be-125">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="d25be-125">User Action</span></span>  
  
-   <span data-ttu-id="d25be-126">Überprüfen Sie, ob der aktuelle Datenbankkontext richtig ist.</span><span class="sxs-lookup"><span data-stu-id="d25be-126">Verify the current database context is correct.</span></span> <span data-ttu-id="d25be-127">Weitere Informationen finden Sie unter [USE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/use-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d25be-127">For more information, see [USE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/use-transact-sql).</span></span>  
  
-   <span data-ttu-id="d25be-128">Überprüfen Sie, ob der Tabellen- oder Objektname richtig geschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="d25be-128">Verify that the table or object name is spelled correctly.</span></span>  
  
-   <span data-ttu-id="d25be-129">Überprüfen Sie den Namen des Schemas, das das Objekt enthält.</span><span class="sxs-lookup"><span data-stu-id="d25be-129">Verify the schema name that contains the object.</span></span> <span data-ttu-id="d25be-130">Wenn das Objekt zu einem anderen Schema als dem Standardschema (**dbo**) gehört, müssen Sie den Tabellen- bzw. Objektnamen im zweiteiligen Format *schema_name.object_name* angeben.</span><span class="sxs-lookup"><span data-stu-id="d25be-130">If the object belongs to a schema other than the default (**dbo**) schema, you must specify the table or object name by using the two-part format *schema_name.object_name*.</span></span>  
  
-   <span data-ttu-id="d25be-131">Stellen Sie sicher, dass das Objekt in den Systemtabellen vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="d25be-131">Verify that the object exists in the system tables.</span></span> <span data-ttu-id="d25be-132">Wenn Sie überprüfen möchten, ob eine Tabelle oder ein anderes schemabezogenes Objekt vorhanden ist, fragen Sie die [sys.objects](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql)-Katalogsicht ab.</span><span class="sxs-lookup"><span data-stu-id="d25be-132">To verify whether a table or other schema-scoped object exists, query the [sys.objects](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql) catalog view.</span></span> <span data-ttu-id="d25be-133">Wenn das Objekt in den Systemtabellen nicht vorhanden ist, wurde das Objekt gelöscht, oder der Benutzer besitzt keine Berechtigungen zum Anzeigen der Objektmetadaten.</span><span class="sxs-lookup"><span data-stu-id="d25be-133">If the object is not in the system tables, the object has been deleted, or the user does not have permissions to view the object metadata.</span></span> <span data-ttu-id="d25be-134">Weitere Informationen zu Berechtigungen zum Anzeigen von Objektmetadaten finden Sie unter [Konfiguration der Sichtbarkeit von Metadaten](../security/metadata-visibility-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="d25be-134">For more information about how to view object metadata, see [Metadata Visibility Configuration](../security/metadata-visibility-configuration.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d25be-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d25be-135">See Also</span></span>  
 [<span data-ttu-id="d25be-136">Katalogsichten &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d25be-136">Catalog Views &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/catalog-views-transact-sql)  
  
  
