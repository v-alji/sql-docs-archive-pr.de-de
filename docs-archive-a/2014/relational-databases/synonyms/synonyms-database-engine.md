---
title: Synonyme (Datenbank-Engine) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: t-sql
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- synonyms [SQL Server], about synonyms
ms.assetid: 6210e1d5-075f-47e4-ac8d-f84bcf26fbc0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3494f4f5b13c422efb8e2a39597e131c10d81ed1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617877"
---
# <a name="synonyms-database-engine"></a><span data-ttu-id="074ea-102">Synonyme (Datenbank-Engine)</span><span class="sxs-lookup"><span data-stu-id="074ea-102">Synonyms (Database Engine)</span></span>
  <span data-ttu-id="074ea-103">Ein Synonym ist ein Datenbankobjekt, das zu folgenden Zwecken dient:</span><span class="sxs-lookup"><span data-stu-id="074ea-103">A synonym is a database object that serves the following purposes:</span></span>  
  
-   <span data-ttu-id="074ea-104">Ein Synonym stellt einen alternativen Namen für ein anderes Datenbankobjekt bereit, das als Basisobjekt bezeichnet wird und auf einem lokalen Server oder Remoteserver gespeichert sein kann.</span><span class="sxs-lookup"><span data-stu-id="074ea-104">Provides an alternative name for another database object, referred to as the base object, that can exist on a local or remote server.</span></span>  
  
-   <span data-ttu-id="074ea-105">Ein Synonym stellt eine Abstraktionsschicht bereit, die eine Clientanwendung vor Änderungen schützt, die am Namen oder Speicherort des Basisobjekts vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="074ea-105">Provides a layer of abstraction that protects a client application from changes made to the name or location of the base object.</span></span>  
  
 <span data-ttu-id="074ea-106">Nehmen Sie z. B. die **Employee** -Tabelle von [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)], die auf dem Server **Server1**gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="074ea-106">For example, consider the **Employee** table of [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)], located on a server named **Server1**.</span></span> <span data-ttu-id="074ea-107">Eine Clientanwendung müsste, um von einem anderen Server, **Server2**, auf diese Tabelle zu verweisen, den vierteiligen Namen **Server1.AdventureWorks.Person.Employee**verwenden.</span><span class="sxs-lookup"><span data-stu-id="074ea-107">To reference this table from another server, **Server2**, a client application would have to use the four-part name **Server1.AdventureWorks.Person.Employee**.</span></span> <span data-ttu-id="074ea-108">Die Clientanwendung müsste außerdem geändert werden, wenn sich der Speicherort der Tabelle ändert, z. B. in einen anderen Server.</span><span class="sxs-lookup"><span data-stu-id="074ea-108">Also, if the location of the table were to change, for example, to another server, the client application would have to be modified to reflect that change.</span></span>  
  
 <span data-ttu-id="074ea-109">Um diese beiden Probleme zu vermeiden, können Sie das Synonym **EmpTable**auf **Server2** für die **Employee** -Tabelle auf **Server1**erstellen.</span><span class="sxs-lookup"><span data-stu-id="074ea-109">To address both these issues, you can create a synonym, **EmpTable**, on **Server2** for the **Employee** table on **Server1**.</span></span> <span data-ttu-id="074ea-110">Nun muss die Clientanwendung nur den einteiligen Namen **EmpTable**verwenden, um auf die **Employee** -Tabelle zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="074ea-110">Now, the client application only has to use the single-part name, **EmpTable**, to reference the **Employee** table.</span></span> <span data-ttu-id="074ea-111">Wenn sich außerdem der Speicherort der **Employee** -Tabelle ändert, müssen Sie das Synonym **EmpTable**ändern, um auf den neuen Speicherort der **Employee** -Tabelle zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="074ea-111">Also, if the location of the **Employee** table changes, you will have to modify the synonym, **EmpTable**, to point to the new location of the **Employee** table.</span></span> <span data-ttu-id="074ea-112">Da es keine ALTER SYNONYM-Anweisung gibt, müssen Sie zuerst das Synonym **EmpTable**löschen und anschließend mit dem gleichen Namen neu erstellen, aber das Synonym auf den neuen Speicherort der **Employee**-Tabelle verweisen lassen.</span><span class="sxs-lookup"><span data-stu-id="074ea-112">Because there is no ALTER SYNONYM statement, you first have to drop the synonym, **EmpTable**, and then re-create the synonym with the same name, but point the synonym to the new location of **Employee**.</span></span>  
  
 <span data-ttu-id="074ea-113">Ein Synonym gehört zu einem Schema, und der Name eines Schemas muss wie andere Objekte in einem Schema eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="074ea-113">A synonym belongs to a schema, and like other objects in a schema, the name of a synonym must be unique.</span></span> <span data-ttu-id="074ea-114">Sie können Synonyme für die folgenden Datenbankobjekte erstellen:</span><span class="sxs-lookup"><span data-stu-id="074ea-114">You can create synonyms for the following database objects:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="074ea-115">Gespeicherte Assemblyprozedur (CLR)</span><span class="sxs-lookup"><span data-stu-id="074ea-115">Assembly (CLR) stored procedure</span></span>|<span data-ttu-id="074ea-116">Assembly-Tabellenwertfunktion (CLR)</span><span class="sxs-lookup"><span data-stu-id="074ea-116">Assembly (CLR) table-valued function</span></span>|  
|<span data-ttu-id="074ea-117">Assemblyskalarfunktion (CLR)</span><span class="sxs-lookup"><span data-stu-id="074ea-117">Assembly (CLR) scalar function</span></span>|<span data-ttu-id="074ea-118">Assemblyaggregatfunktion (CLR)</span><span class="sxs-lookup"><span data-stu-id="074ea-118">Assembly (CLR) aggregate functions</span></span>|  
|<span data-ttu-id="074ea-119">Replikationsfilterprozedur</span><span class="sxs-lookup"><span data-stu-id="074ea-119">Replication-filter-procedure</span></span>|<span data-ttu-id="074ea-120">Erweiterte gespeicherte Prozedur</span><span class="sxs-lookup"><span data-stu-id="074ea-120">Extended stored procedure</span></span>|  
|<span data-ttu-id="074ea-121">SQL-Skalarfunktion</span><span class="sxs-lookup"><span data-stu-id="074ea-121">SQL scalar function</span></span>|<span data-ttu-id="074ea-122">SQL-Tabellenwertfunktion</span><span class="sxs-lookup"><span data-stu-id="074ea-122">SQL table-valued function</span></span>|  
|<span data-ttu-id="074ea-123">SQL-Inline-Tabellenwertfunktion</span><span class="sxs-lookup"><span data-stu-id="074ea-123">SQL inline-tabled-valued function</span></span>|<span data-ttu-id="074ea-124">Gespeicherte SQL-Prozedur</span><span class="sxs-lookup"><span data-stu-id="074ea-124">SQL stored procedure</span></span>|  
|<span data-ttu-id="074ea-125">Sicht</span><span class="sxs-lookup"><span data-stu-id="074ea-125">View</span></span>|<span data-ttu-id="074ea-126">Tabelle<sup>1</sup> (Benutzerdefiniert)</span><span class="sxs-lookup"><span data-stu-id="074ea-126">Table<sup>1</sup> (User-defined)</span></span>|  
  
 <span data-ttu-id="074ea-127"><sup>1</sup> enthält lokale und globale temporäre Tabellen.</span><span class="sxs-lookup"><span data-stu-id="074ea-127"><sup>1</sup> Includes local and global temporary tables</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="074ea-128">Vierteilige Namen für Funktionsbasisobjekte werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="074ea-128">Four-part names for function base objects are not supported.</span></span>  
  
 <span data-ttu-id="074ea-129">Ein Synonym kann nicht das Basisobjekt für ein anderes Synonym sein. Außerdem kann ein Synonym nicht auf eine benutzerdefinierte Aggregatfunktion verweisen.</span><span class="sxs-lookup"><span data-stu-id="074ea-129">A synonym cannot be the base object for another synonym, and a synonym cannot reference a user-defined aggregate function.</span></span>  
  
 <span data-ttu-id="074ea-130">Die Bindung zwischen einem Synonym und dem zugehörigen Basisobjekt erfolgt nur mit dem Namen.</span><span class="sxs-lookup"><span data-stu-id="074ea-130">The binding between a synonym and its base object is by name only.</span></span> <span data-ttu-id="074ea-131">Alle Überprüfungen auf das Vorhandensein, den Typ und die Berechtigungen für das Basisobjekt werden bis zur Laufzeit verschoben.</span><span class="sxs-lookup"><span data-stu-id="074ea-131">All existence, type, and permissions checking on the base object is deferred until run time.</span></span> <span data-ttu-id="074ea-132">Deshalb kann das Basisobjekt geändert, gelöscht oder gelöscht und durch ein anderes Objekt, das den gleichen Namen wie das ursprüngliche Basisobjekt hat, ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="074ea-132">Therefore, the base object can be modified, dropped, or dropped and replaced by another object that has the same name as the original base object.</span></span> <span data-ttu-id="074ea-133">Betrachten wir als Beispiel das Synonym **MyContacts**, das auf die **Person.Contact** -Tabelle in [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)]verweist.</span><span class="sxs-lookup"><span data-stu-id="074ea-133">For example, consider a synonym, **MyContacts**, that references the **Person.Contact** table in [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)].</span></span> <span data-ttu-id="074ea-134">Wenn die **Contact** -Tabelle gelöscht und durch die **Person.Contact**-Sicht ersetzt wird, verweist **MyContacts** nun auf die **Person.Contact** -Sicht.</span><span class="sxs-lookup"><span data-stu-id="074ea-134">If the **Contact** table is dropped and replaced by a view named **Person.Contact**, **MyContacts** now references the **Person.Contact** view.</span></span>  
  
 <span data-ttu-id="074ea-135">Verweise auf Synonyme sind nicht schemagebunden.</span><span class="sxs-lookup"><span data-stu-id="074ea-135">References to synonyms are not schema-bound.</span></span> <span data-ttu-id="074ea-136">Deshalb kann ein Synonym jederzeit gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="074ea-136">Therefore, a synonym can be dropped at any time.</span></span> <span data-ttu-id="074ea-137">Durch das Löschen eines Synonyms besteht jedoch die Gefahr, dass Verweise auf das gelöschte Synonym zurückbleiben.</span><span class="sxs-lookup"><span data-stu-id="074ea-137">However, by dropping a synonym, you run the risk of leaving dangling references to the synonym that was dropped.</span></span> <span data-ttu-id="074ea-138">Diese Verweise werden erst zur Laufzeit gefunden.</span><span class="sxs-lookup"><span data-stu-id="074ea-138">These references will only be found at run time.</span></span>  
  
## <a name="synonyms-and-schemas"></a><span data-ttu-id="074ea-139">Synonyme und Schemas</span><span class="sxs-lookup"><span data-stu-id="074ea-139">Synonyms and Schemas</span></span>  
 <span data-ttu-id="074ea-140">Wenn Sie über ein Standardschema verfügen, das nicht Ihnen gehört, und Sie ein Synonym erstellen möchten, müssen Sie den Synonymnamen mit dem Namen eines Schemas, das Ihnen gehört, qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="074ea-140">If you have a default schema that you do not own and want to create a synonym, you must qualify the synonym name with the name of a schema that you do own.</span></span> <span data-ttu-id="074ea-141">Angenommen, Ihnen gehört ein Schema **x**, aber **y** ist Ihr Standardschema und Sie verwenden die CREATE SYNONYM-Anweisung. In diesem Fall müssen Sie dem Namen des Synonyms das Schema **x**als Präfix voranstellen, anstatt dem Synonym einen einteiligen Namen zu geben.</span><span class="sxs-lookup"><span data-stu-id="074ea-141">For example, if you own a schema **x**, but **y** is your default schema and you use the CREATE SYNONYM statement, you must prefix the name of the synonym with the schema **x**, instead of naming the synonym by using a single-part name.</span></span> <span data-ttu-id="074ea-142">Weitere Informationen zum Erstellen von Synonymen finden Sie unter [CREATE SYNONYM &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-synonym-transact-sql)gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="074ea-142">For more information about how to create synonyms, see [CREATE SYNONYM &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-synonym-transact-sql).</span></span>  
  
## <a name="granting-permissions-on-a-synonym"></a><span data-ttu-id="074ea-143">Erteilen von Berechtigungen für Synonyme</span><span class="sxs-lookup"><span data-stu-id="074ea-143">Granting Permissions on a Synonym</span></span>  
 <span data-ttu-id="074ea-144">Nur Besitzer eines Synonyms, Mitglieder der Rollen **db_owner**oder **db_ddladmin** können Berechtigungen für ein Synonym erteilen.</span><span class="sxs-lookup"><span data-stu-id="074ea-144">Only synonym owners, members of **db_owner**, or members of **db_ddladmin** can grant permission on a synonym.</span></span>  
  
 <span data-ttu-id="074ea-145">Sie können eine GRANT-, DENY-, REVOKE-Anweisung für alle oder einige der folgenden Berechtigungen für ein Synonym ausführen:</span><span class="sxs-lookup"><span data-stu-id="074ea-145">You can GRANT, DENY, REVOKE all or any of the following permissions on a synonym:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="074ea-146">CONTROL</span><span class="sxs-lookup"><span data-stu-id="074ea-146">CONTROL</span></span>|<span data-ttu-id="074ea-147">Delete</span><span class="sxs-lookup"><span data-stu-id="074ea-147">DELETE</span></span>|  
|<span data-ttu-id="074ea-148">Führen Sie</span><span class="sxs-lookup"><span data-stu-id="074ea-148">EXECUTE</span></span>|<span data-ttu-id="074ea-149">INSERT</span><span class="sxs-lookup"><span data-stu-id="074ea-149">INSERT</span></span>|  
|<span data-ttu-id="074ea-150">SELECT</span><span class="sxs-lookup"><span data-stu-id="074ea-150">SELECT</span></span>|<span data-ttu-id="074ea-151">TAKE OWNERSHIP</span><span class="sxs-lookup"><span data-stu-id="074ea-151">TAKE OWNERSHIP</span></span>|  
|<span data-ttu-id="074ea-152">UPDATE</span><span class="sxs-lookup"><span data-stu-id="074ea-152">UPDATE</span></span>|<span data-ttu-id="074ea-153">VIEW DEFINITION</span><span class="sxs-lookup"><span data-stu-id="074ea-153">VIEW DEFINITION</span></span>|  
  
## <a name="using-synonyms"></a><span data-ttu-id="074ea-154">Verwenden von Synonymen</span><span class="sxs-lookup"><span data-stu-id="074ea-154">Using Synonyms</span></span>  
 <span data-ttu-id="074ea-155">Synonyme können anstelle des Basisobjekts, auf das verwiesen wird, in mehreren SQL-Anweisungen und Ausdruckskontexten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="074ea-155">You can use synonyms in place of their referenced base object in several SQL statements and expression contexts.</span></span> <span data-ttu-id="074ea-156">Die folgende Tabelle enthält eine Liste dieser Anweisungen und Ausdruckskontexte:</span><span class="sxs-lookup"><span data-stu-id="074ea-156">The following table contains a list of these statements and expression contexts:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="074ea-157">SELECT</span><span class="sxs-lookup"><span data-stu-id="074ea-157">SELECT</span></span>|<span data-ttu-id="074ea-158">INSERT</span><span class="sxs-lookup"><span data-stu-id="074ea-158">INSERT</span></span>|  
|<span data-ttu-id="074ea-159">UPDATE</span><span class="sxs-lookup"><span data-stu-id="074ea-159">UPDATE</span></span>|<span data-ttu-id="074ea-160">Delete</span><span class="sxs-lookup"><span data-stu-id="074ea-160">DELETE</span></span>|  
|<span data-ttu-id="074ea-161">Führen Sie</span><span class="sxs-lookup"><span data-stu-id="074ea-161">EXECUTE</span></span>|<span data-ttu-id="074ea-162">Untergeordnete SELECT-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="074ea-162">Sub-selects</span></span>|  
  
 <span data-ttu-id="074ea-163">Wenn Sie Synonyme in den vorher beschriebenen Kontexten verwenden, ist das Basisobjekt davon betroffen.</span><span class="sxs-lookup"><span data-stu-id="074ea-163">When you are working with synonyms in the contexts previously stated, the base object is affected.</span></span> <span data-ttu-id="074ea-164">Angenommen, ein Synonym verweist auf ein Basisobjekt, das eine Tabelle darstellt, und Sie fügen eine Zeile in das Synonym ein. In Wirklichkeit fügen Sie dann eine Zeile in die Tabelle ein, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="074ea-164">For example, if a synonym references a base object that is a table and you insert a row into the synonym, you are actually inserting a row into the referenced table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="074ea-165">Auf ein Synonym, das auf einem Verbindungsserver gespeichert ist, kann nicht verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="074ea-165">You cannot reference a synonym that is located on a linked server.</span></span>  
  
 <span data-ttu-id="074ea-166">Sie können ein Synonym als Parameter für die OBJECT_ID-Funktion verwenden; die Funktion gibt jedoch die Objekt-ID des Synonyms und nicht das Basisobjekt zurück.</span><span class="sxs-lookup"><span data-stu-id="074ea-166">You can use a synonym as the parameter for the OBJECT_ID function; however, the function returns the object ID of the synonym, not the base object.</span></span>  
  
 <span data-ttu-id="074ea-167">Sie können in einer DDL-Anweisung nicht auf ein Synonym verweisen.</span><span class="sxs-lookup"><span data-stu-id="074ea-167">You cannot reference a synonym in a DDL statement.</span></span> <span data-ttu-id="074ea-168">So generieren beispielsweise die folgenden Anweisungen, die auf ein Synonym namens `dbo.MyProduct`verweisen, einen Fehler:</span><span class="sxs-lookup"><span data-stu-id="074ea-168">For example, the following statements, which reference a synonym named `dbo.MyProduct`, generate errors:</span></span>  
  
```  
ALTER TABLE dbo.MyProduct  
   ADD NewFlag int null;  
EXEC ('ALTER TABLE dbo.MyProduct  
   ADD NewFlag int null');  
```  
  
 <span data-ttu-id="074ea-169">Die folgenden Berechtigungsanweisungen beziehen sich nur auf das Synonym, nicht auf das Basisobjekt.</span><span class="sxs-lookup"><span data-stu-id="074ea-169">The following permission statements are associated only with the synonym and not the base object:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="074ea-170">GRANT</span><span class="sxs-lookup"><span data-stu-id="074ea-170">GRANT</span></span>|<span data-ttu-id="074ea-171">VERWEIGERN</span><span class="sxs-lookup"><span data-stu-id="074ea-171">DENY</span></span>|  
|<span data-ttu-id="074ea-172">REVOKE</span><span class="sxs-lookup"><span data-stu-id="074ea-172">REVOKE</span></span>||  
  
 <span data-ttu-id="074ea-173">Synonyme sind nicht schemagebunden. Deshalb kann von den folgenden schemagebundenen Ausdruckskontexten nicht auf Synonyme verwiesen werden:</span><span class="sxs-lookup"><span data-stu-id="074ea-173">Synonyms are not schema-bound and, therefore, cannot be referenced by the following schema-bound expression contexts:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="074ea-174">CHECK-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="074ea-174">CHECK constraints</span></span>|<span data-ttu-id="074ea-175">Berechnete Spalten</span><span class="sxs-lookup"><span data-stu-id="074ea-175">Computed columns</span></span>|  
|<span data-ttu-id="074ea-176">Standardausdrücke</span><span class="sxs-lookup"><span data-stu-id="074ea-176">Default expressions</span></span>|<span data-ttu-id="074ea-177">Regelausdrücke</span><span class="sxs-lookup"><span data-stu-id="074ea-177">Rule expressions</span></span>|  
|<span data-ttu-id="074ea-178">Schemagebundene Sichten</span><span class="sxs-lookup"><span data-stu-id="074ea-178">Schema-bound views</span></span>|<span data-ttu-id="074ea-179">Schemagebundene Funktionen</span><span class="sxs-lookup"><span data-stu-id="074ea-179">Schema-bound functions</span></span>|  
  
 <span data-ttu-id="074ea-180">Weitere Informationen zu schemagebundenen Funktionen finden Sie unter [Erstellen von benutzerdefinierten Funktionen &#40;Datenbank-Engine&#41;](../user-defined-functions/create-user-defined-functions-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="074ea-180">For more information about schema-bound functions, see [Create User-defined Functions &#40;Database Engine&#41;](../user-defined-functions/create-user-defined-functions-database-engine.md).</span></span>  
  
## <a name="getting-information-about-synonyms"></a><span data-ttu-id="074ea-181">Abrufen von Informationen zu Synonymen</span><span class="sxs-lookup"><span data-stu-id="074ea-181">Getting Information About Synonyms</span></span>  
 <span data-ttu-id="074ea-182">Die sys.synonyms-Katalogsicht enthält einen Eintrag für jedes Synonym in einer bestimmten Datenbank.</span><span class="sxs-lookup"><span data-stu-id="074ea-182">The sys.synonyms catalog view contains an entry for each synonym in a given database.</span></span> <span data-ttu-id="074ea-183">Diese Katalogsicht macht Synonymmetadaten verfügbar, wie z. B. den Namen des Synonyms und den Namen des Basisobjekts.</span><span class="sxs-lookup"><span data-stu-id="074ea-183">This catalog view exposes synonym metadata such as the name of the synonym and the name of the base object.</span></span> <span data-ttu-id="074ea-184">Weitere Informationen zur- `sys.synonyms` Katalog Sicht finden Sie unter [sys. Synonyme &#40;Transact-SQL-&#41;](/sql/relational-databases/system-catalog-views/sys-synonyms-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="074ea-184">For more information about the `sys.synonyms` catalog view, see [sys.synonyms &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-synonyms-transact-sql).</span></span>  
  
 <span data-ttu-id="074ea-185">Mithilfe erweiterter Eigenschaften können Sie Beschreibungs- oder Anweisungstext, Eingabeformate und Formatierungsregeln als Eigenschaften eines Synonyms hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="074ea-185">By using extended properties, you can add descriptive or instructional text, input masks, and formatting rules as properties of a synonym.</span></span> <span data-ttu-id="074ea-186">Da die Eigenschaft in der Datenbank gespeichert wird, können alle Anwendungen, die die Eigenschaft lesen, das Objekt auf die gleiche Weise auswerten.</span><span class="sxs-lookup"><span data-stu-id="074ea-186">Because the property is stored in the database, all applications that read the property can evaluate the object in the same way.</span></span> <span data-ttu-id="074ea-187">Weitere Informationen finden Sie unter [sp_addextendedproperty &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addextendedproperty-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="074ea-187">For more information, see [sp_addextendedproperty &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addextendedproperty-transact-sql).</span></span>  
  
 <span data-ttu-id="074ea-188">Verwenden Sie die OBJECTPROPERTYEX-Funktion, um den Basistyp des Basisobjekts eines Synonyms zu suchen.</span><span class="sxs-lookup"><span data-stu-id="074ea-188">To find the base type of the base object of a synonym, use the OBJECTPROPERTYEX function.</span></span> <span data-ttu-id="074ea-189">Weitere Informationen finden Sie unter [OBJECTPROPERTYEX &#40;Transact-SQL&#41;](/sql/t-sql/functions/objectproperty-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="074ea-189">For more information, see [OBJECTPROPERTYEX &#40;Transact-SQL&#41;](/sql/t-sql/functions/objectproperty-transact-sql).</span></span>  
  
### <a name="examples"></a><span data-ttu-id="074ea-190">Beispiele</span><span class="sxs-lookup"><span data-stu-id="074ea-190">Examples</span></span>  
 <span data-ttu-id="074ea-191">Das folgende Beispiel gibt den Basistyp des Basisobjekts eines Synonyms zurück, das ein lokales Objekt ist.</span><span class="sxs-lookup"><span data-stu-id="074ea-191">The following example returns the base type of a synonym's base object that is a local object.</span></span>  
  
```  
USE tempdb;  
GO  
CREATE SYNONYM MyEmployee   
FOR AdventureWorks2012.HumanResources.Employee;  
GO  
SELECT OBJECTPROPERTYEX(OBJECT_ID('MyEmployee'), 'BaseType') AS BaseType;  
```  
  
 <span data-ttu-id="074ea-192">Das folgende Beispiel gibt den Basistyp des Basisobjekts eines Synonyms zurück, das ein Remoteobjekt auf einem Server mit dem Namen `Server1`ist.</span><span class="sxs-lookup"><span data-stu-id="074ea-192">The following example returns the base type of a synonym's base object that is a remote object located on a server named `Server1`.</span></span>  
  
```  
EXECUTE sp_addlinkedserver Server1;  
GO  
CREATE SYNONYM MyRemoteEmployee  
FOR Server1.AdventureWorks2012.HumanResources.Employee;  
GO  
SELECT OBJECTPROPERTYEX(OBJECT_ID('MyRemoteEmployee'), 'BaseType') AS BaseType;  
GO  
```  
  
## <a name="related-content"></a><span data-ttu-id="074ea-193">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="074ea-193">Related Content</span></span>  
 [<span data-ttu-id="074ea-194">Erstellen von Synonymen</span><span class="sxs-lookup"><span data-stu-id="074ea-194">Create Synonyms</span></span>](create-synonyms.md)  
  
 [<span data-ttu-id="074ea-195">CREATE SYNONYM &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="074ea-195">CREATE SYNONYM &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-synonym-transact-sql)  
  
 [<span data-ttu-id="074ea-196">DROP SYNONYM &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="074ea-196">DROP SYNONYM &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-synonym-transact-sql)  
  
  
