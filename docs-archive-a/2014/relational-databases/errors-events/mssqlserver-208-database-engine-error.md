---
title: MSSQLSERVER_208 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 208 (Database Engine error)
ms.assetid: 4b1895f5-3197-4da1-af86-954c93507956
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 97ab3eb220c03c3de0c95251861f3b947890b090
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608732"
---
# <a name="mssqlserver_208"></a><span data-ttu-id="6514e-102">MSSQLSERVER_208</span><span class="sxs-lookup"><span data-stu-id="6514e-102">MSSQLSERVER_208</span></span>
    
## <a name="details"></a><span data-ttu-id="6514e-103">Details</span><span class="sxs-lookup"><span data-stu-id="6514e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6514e-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="6514e-104">Product Name</span></span>|<span data-ttu-id="6514e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="6514e-105">SQL Server</span></span>|  
|<span data-ttu-id="6514e-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="6514e-106">Event ID</span></span>|<span data-ttu-id="6514e-107">208</span><span class="sxs-lookup"><span data-stu-id="6514e-107">208</span></span>|  
|<span data-ttu-id="6514e-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="6514e-108">Event Source</span></span>|<span data-ttu-id="6514e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="6514e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="6514e-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="6514e-110">Component</span></span>|<span data-ttu-id="6514e-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="6514e-111">SQLEngine</span></span>|  
|<span data-ttu-id="6514e-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="6514e-112">Symbolic Name</span></span>|<span data-ttu-id="6514e-113">SQ_BADOBJECT</span><span class="sxs-lookup"><span data-stu-id="6514e-113">SQ_BADOBJECT</span></span>|  
|<span data-ttu-id="6514e-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="6514e-114">Message Text</span></span>|<span data-ttu-id="6514e-115">Ungültiger Objektname '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="6514e-115">Invalid object name '%.\*ls'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6514e-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="6514e-116">Explanation</span></span>  
 <span data-ttu-id="6514e-117">Das angegebene Objekt wurde nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="6514e-117">The specified object cannot be found.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="6514e-118">Mögliche Ursachen</span><span class="sxs-lookup"><span data-stu-id="6514e-118">Possible Causes</span></span>  
 <span data-ttu-id="6514e-119">Dieser Fehler kann durch eines der folgenden Probleme verursacht werden:</span><span class="sxs-lookup"><span data-stu-id="6514e-119">This error can be caused by one of the following problems:</span></span>  
  
-   <span data-ttu-id="6514e-120">Das Objekt ist nicht richtig angegeben.</span><span class="sxs-lookup"><span data-stu-id="6514e-120">The object is not specified correctly.</span></span>  
  
-   <span data-ttu-id="6514e-121">Das Objekt ist in der aktuellen Datenbank oder der angegebenen Datenbank nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="6514e-121">The object does not exist in the current database or in the specified database.</span></span>  
  
-   <span data-ttu-id="6514e-122">Das Objekt ist vorhanden, es konnte jedoch nicht für den Benutzer verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="6514e-122">The object exists, but could not be exposed to the user.</span></span> <span data-ttu-id="6514e-123">Es ist z. B. möglich, dass der Benutzer keine Berechtigungen für das Objekt besitzt oder dass das Objekt in einer EXECUTE-Anweisung erstellt ist, aber von außerhalb des Gültigkeitsbereichs der EXECUTE-Anweisung darauf zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="6514e-123">For example, the user might not have permissions on the object or the object is created within an EXECUTE statement but accessed outside the scope of the EXECUTE statement.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6514e-124">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="6514e-124">User Action</span></span>  
 <span data-ttu-id="6514e-125">Überprüfen Sie die folgenden Informationen, und korrigieren Sie die Anweisung entsprechend.</span><span class="sxs-lookup"><span data-stu-id="6514e-125">Verify the following information and correct the statement as appropriate.</span></span>  
  
-   <span data-ttu-id="6514e-126">Der Objektname wurde richtig geschrieben.</span><span class="sxs-lookup"><span data-stu-id="6514e-126">The object name is spelled correctly.</span></span>  
  
-   <span data-ttu-id="6514e-127">Der aktuelle Datenbankkontext ist richtig.</span><span class="sxs-lookup"><span data-stu-id="6514e-127">The current database context is correct.</span></span> <span data-ttu-id="6514e-128">Wenn kein Datnbankname für das Objekt angegeben ist, muss das Objekt in der aktuellen Datenbank vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="6514e-128">If a database name for the object is not specified, the object must exist in the current database.</span></span> <span data-ttu-id="6514e-129">Weitere Informationen zum Festlegen des Datenbankkontexts finden Sie unter [USE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/use-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6514e-129">For more information about setting the database context, see [USE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/use-transact-sql).</span></span>  
  
-   <span data-ttu-id="6514e-130">Das Objekt ist in den Systemtabellen vorhanden.</span><span class="sxs-lookup"><span data-stu-id="6514e-130">The object exists in the system tables.</span></span> <span data-ttu-id="6514e-131">Wenn Sie überprüfen möchten, ob eine Tabelle oder ein anderes schemabezogenes Objekt vorhanden ist, fragen Sie die **sys.objects**-Katalogsicht ab.</span><span class="sxs-lookup"><span data-stu-id="6514e-131">To verify whether a table or other schema-scoped object exists, query the **sys.objects** catalog view.</span></span> <span data-ttu-id="6514e-132">Wenn das Objekt in den Systemtabellen nicht vorhanden ist, wurde das Objekt gelöscht, oder der Benutzer besitzt keine Berechtigungen zum Anzeigen der Objektmetadaten.</span><span class="sxs-lookup"><span data-stu-id="6514e-132">If the object is not in the system tables, the object has been deleted, or the user does not have permissions to view the object metadata.</span></span> <span data-ttu-id="6514e-133">Weitere Informationen zu Berechtigungen zum Anzeigen von Objektmetadaten finden Sie unter [Konfiguration der Sichtbarkeit von Metadaten](../security/metadata-visibility-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="6514e-133">For more information about permissions to view object metadata, see [Metadata Visibility Configuration](../security/metadata-visibility-configuration.md).</span></span>  
  
-   <span data-ttu-id="6514e-134">Das Objekt ist im Standardschema des Benutzers enthalten.</span><span class="sxs-lookup"><span data-stu-id="6514e-134">The object is contained in the default schema of the user.</span></span> <span data-ttu-id="6514e-135">Andernfalls muss das Objekt im zweiteiligen Format *schema_name.object_name* angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="6514e-135">If it is not, the object must be specified using the two-part format *schema_name.object_name*.</span></span> <span data-ttu-id="6514e-136">Beachten Sie, dass Skalarwertfunktionen immer mindestens mit dem zweiteiligen Namen aufgerufen werden müssen.</span><span class="sxs-lookup"><span data-stu-id="6514e-136">Note that scalar-valued functions must always be invoked by using at least a two-part name.</span></span>  
  
-   <span data-ttu-id="6514e-137">Die Unterscheidung nach Groß-/Kleinschreibung der Datenbanksortierung.</span><span class="sxs-lookup"><span data-stu-id="6514e-137">The case sensitivity of the database collation.</span></span>  
  
     <span data-ttu-id="6514e-138">Wenn eine Datenbank eine Sortierung verwendet, die nach Groß-/Kleinschreibung unterscheidet, muss der Objektname der Schreibung des Objekts in der Datenbank entsprechen.</span><span class="sxs-lookup"><span data-stu-id="6514e-138">When a database uses a case-sensitive collation, the object name must match the case of the object in the database.</span></span> <span data-ttu-id="6514e-139">Wenn ein Objekt z.B. als **MyTable** in einer Datenbank mit Sortierung, die nach Groß-/Kleinschreibung unterscheidet, angegeben ist, geben Abfragen, die auf das Objekt als **mytable** oder **Mytable** verweisen, den Fehler 208 zurück, weil die Objektnamen nicht übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="6514e-139">For example, when an object is specified as **MyTable** in a database with a case sensitive collation, queries that refer to the object as **mytable** or **Mytable** will cause error 208 to return because the object names do not match.</span></span>  
  
     <span data-ttu-id="6514e-140">Sie können die Datenbanksortierung überprüfen, indem Sie die folgende Anweisung ausführen.</span><span class="sxs-lookup"><span data-stu-id="6514e-140">You can verify the database collation by running the following statement.</span></span>  
  
    ```  
    SELECT collation_name FROM sys.databases WHERE name = 'database_name';  
    ```  
  
     <span data-ttu-id="6514e-141">Die Abkürzung CS im Sortierungsnamen gibt an, dass bei der Sortierung nach Groß-/Kleinschreibung unterschieden wird.</span><span class="sxs-lookup"><span data-stu-id="6514e-141">The abbreviation CS in the collation name indicates the collation is case sensitive.</span></span> <span data-ttu-id="6514e-142">Beispiel: Latin1_General_CS_AS ist eine Sortierung, bei der nach Groß-/Kleinschreibung und nach Akzent unterschieden wird.</span><span class="sxs-lookup"><span data-stu-id="6514e-142">For example, Latin1_General_CS_AS is a case sensitive, accent sensitive collation.</span></span> <span data-ttu-id="6514e-143">CI gibt an, dass bei der Sortierung nicht nach Groß-/Kleinschreibung unterschieden wird.</span><span class="sxs-lookup"><span data-stu-id="6514e-143">CI indicates a case insensitive collation.</span></span>  
  
-   <span data-ttu-id="6514e-144">Der Benutzer besitzt die Berechtigung zum Zugreifen auf das Objekt.</span><span class="sxs-lookup"><span data-stu-id="6514e-144">The user has permission to access the object.</span></span> <span data-ttu-id="6514e-145">Mit der Systemfunktion **Has_Perms_By_Name** können Sie die Berechtigungen des Benutzers für das Objekt überprüfen.</span><span class="sxs-lookup"><span data-stu-id="6514e-145">To verify the permissions the user has on the object, use the **Has_Perms_By_Name** system function.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6514e-146">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6514e-146">See Also</span></span>  
 <span data-ttu-id="6514e-147">[Verwenden Sie &#40;Transact-SQL-&#41;](/sql/t-sql/language-elements/use-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6514e-147">[USE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/use-transact-sql) </span></span>  
 <span data-ttu-id="6514e-148">[Konfiguration der metadatensicht](../security/metadata-visibility-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="6514e-148">[Metadata Visibility Configuration](../security/metadata-visibility-configuration.md) </span></span>  
 [<span data-ttu-id="6514e-149">HAS_PERMS_BY_NAME &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6514e-149">HAS_PERMS_BY_NAME &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/has-perms-by-name-transact-sql)  
  
  
