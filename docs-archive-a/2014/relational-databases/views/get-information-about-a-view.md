---
title: Abrufen von Informationen zu einer Sicht | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
f1_keywords:
- sql12.swb.viewproperties.general.f1
helpviewer_keywords:
- views [SQL Server], status information
- metadata [SQL Server], views
- dependencies [SQL Server], views
- displaying view information
- views [SQL Server], metadata
- viewing view information
- status information [SQL Server], views
- view dependencies
ms.assetid: 05a73e33-8f85-4fb6-80c1-1b659e753403
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4277aad4c1de0140606575c7ba437408518b3c8a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608465"
---
# <a name="get-information-about-a-view"></a><span data-ttu-id="ef296-102">Abrufen von Informationen zu einer Sicht</span><span class="sxs-lookup"><span data-stu-id="ef296-102">Get Information About a View</span></span>
  <span data-ttu-id="ef296-103">Sie erhalten Informationen zur Definition oder den Eigenschaften einer Sicht in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ef296-103">You can gain information about a view's definition or properties in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="ef296-104">Manchmal ist es erforderlich, die Definition einer Sicht anzuzeigen, um zu verstehen, wie die Daten in der Sicht aus den Quelltabellen abgeleitet werden, oder um die durch die Sicht definierten Daten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ef296-104">You may need to see the definition of the view to understand how its data is derived from the source tables or to see the data defined by the view.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ef296-105">Wenn Sie den Namen eines Objekts ändern, auf das eine Sicht verweist, müssen Sie die Sicht so ändern, dass ihr Text den neuen Namen wiedergibt.</span><span class="sxs-lookup"><span data-stu-id="ef296-105">If you change the name of an object referenced by a view, you must modify the view so that its text reflects the new name.</span></span> <span data-ttu-id="ef296-106">Bevor Sie ein Objekt umbenennen, sollten Sie somit erst die Abhängigkeiten des Objekts anzeigen, um feststellen zu können, ob Sichten von der beabsichtigten Änderung betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="ef296-106">Therefore, before renaming an object, display the dependencies of the object first to determine if any views are affected by the proposed change.</span></span>  
  
 <span data-ttu-id="ef296-107">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="ef296-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ef296-108">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="ef296-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ef296-109">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="ef296-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ef296-110">**Informationen zu einer Sicht rufen Sie ab mit:**</span><span class="sxs-lookup"><span data-stu-id="ef296-110">**To get information about a view, using:**</span></span>  
  
     [<span data-ttu-id="ef296-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ef296-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="ef296-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ef296-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ef296-113">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="ef296-113">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ef296-114">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="ef296-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ef296-115">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="ef296-115">Permissions</span></span>  
 <span data-ttu-id="ef296-116">Für die Verwendung von `sp_helptext` zum Zurückgeben der Definition einer Sicht ist die Mitgliedschaft in der Rolle **Öffentlich** erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ef296-116">Using `sp_helptext` to return the definition of a view requires membership in the **public** role.</span></span> <span data-ttu-id="ef296-117">Für die Verwendung von `sys.sql_expression_dependencies` zur Suche aller Abhängigkeiten von einer Sicht sind die Berechtigung VIEW DEFINITION für die Datenbank und die Berechtigung SELECT auf `sys.sql_expression_dependencies` für die Datenbank erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ef296-117">Using `sys.sql_expression_dependencies` to find all the dependencies on a view requires VIEW DEFINITION permission on the database and SELECT permission on `sys.sql_expression_dependencies` for the database.</span></span> <span data-ttu-id="ef296-118">Systemobjektdefinitionen, wie die in SELECT OBJECT_DEFINITION zurückgegebenen Systemobjektdefinitionen, sind öffentlich sichtbar.</span><span class="sxs-lookup"><span data-stu-id="ef296-118">System object definitions, like the ones returned in SELECT OBJECT_DEFINITION, are publicly visible.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ef296-119">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ef296-119">Using SQL Server Management Studio</span></span>  
  
#### <a name="get-view-properties-by-using-object-explorer"></a><span data-ttu-id="ef296-120">Abrufen von Sichteigenschaften mit Objekt-Explorer</span><span class="sxs-lookup"><span data-stu-id="ef296-120">Get view properties by using Object Explorer</span></span>  
  
1.  <span data-ttu-id="ef296-121">Klicken Sie in **Objekt-Explorer**auf das Pluszeichen neben der Datenbank, die die Sicht enthält, deren Eigenschaften Sie anzeigen möchten, und klicken Sie dann auf das Pluszeichen, um den Ordner **Sichten** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="ef296-121">In **Object Explorer**, click the plus sign next to the database that contains the view to which you want to view the properties, and then click the plus sign to expand the **Views** folder.</span></span>  
  
2.  <span data-ttu-id="ef296-122">Klicken Sie mit der rechten Maustaste auf die Sicht, deren Eigenschaften Sie anzeigen möchten, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="ef296-122">Right-click the view of which you want to view the properties and select **Properties**.</span></span>  
  
     <span data-ttu-id="ef296-123">Die folgenden Eigenschaften werden im Dialogfeld **Sichteigenschaften** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ef296-123">The following properties show in the **View Properties** dialog box.</span></span>  
  
     <span data-ttu-id="ef296-124">**Datenbank**</span><span class="sxs-lookup"><span data-stu-id="ef296-124">**Database**</span></span>  
     <span data-ttu-id="ef296-125">Name der Datenbank, die diese Sicht enthält.</span><span class="sxs-lookup"><span data-stu-id="ef296-125">The name of the database containing this view.</span></span>  
  
     <span data-ttu-id="ef296-126">**Server**</span><span class="sxs-lookup"><span data-stu-id="ef296-126">**Server**</span></span>  
     <span data-ttu-id="ef296-127">Name der aktuellen Serverinstanz.</span><span class="sxs-lookup"><span data-stu-id="ef296-127">The name of the current server instance.</span></span>  
  
     <span data-ttu-id="ef296-128">**Benutzer**</span><span class="sxs-lookup"><span data-stu-id="ef296-128">**User**</span></span>  
     <span data-ttu-id="ef296-129">Name des Benutzers dieser Verbindung.</span><span class="sxs-lookup"><span data-stu-id="ef296-129">The name of the user of this connection.</span></span>  
  
     <span data-ttu-id="ef296-130">**Erstellt am**</span><span class="sxs-lookup"><span data-stu-id="ef296-130">**Created date**</span></span>  
     <span data-ttu-id="ef296-131">Zeigt das Datum an, an dem die Sicht erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="ef296-131">Displays the date the view was created.</span></span>  
  
     <span data-ttu-id="ef296-132">**Name**</span><span class="sxs-lookup"><span data-stu-id="ef296-132">**Name**</span></span>  
     <span data-ttu-id="ef296-133">Name der aktuellen Sicht.</span><span class="sxs-lookup"><span data-stu-id="ef296-133">The name of the current view.</span></span>  
  
     <span data-ttu-id="ef296-134">**Schema**</span><span class="sxs-lookup"><span data-stu-id="ef296-134">**Schema**</span></span>  
     <span data-ttu-id="ef296-135">Zeigt das Schema an, zu dem die Sicht gehört.</span><span class="sxs-lookup"><span data-stu-id="ef296-135">Displays the schema that owns the view.</span></span>  
  
     <span data-ttu-id="ef296-136">**Systemobjekt**</span><span class="sxs-lookup"><span data-stu-id="ef296-136">**System object**</span></span>  
     <span data-ttu-id="ef296-137">Gibt an, ob es sich bei der Sicht um ein Systemobjekt handelt.</span><span class="sxs-lookup"><span data-stu-id="ef296-137">Indicates whether the view is a system object.</span></span> <span data-ttu-id="ef296-138">Die Werte sind True und False.</span><span class="sxs-lookup"><span data-stu-id="ef296-138">Values are True and False.</span></span>  
  
     <span data-ttu-id="ef296-139">**ANSI NULLS**</span><span class="sxs-lookup"><span data-stu-id="ef296-139">**ANSI NULLs**</span></span>  
     <span data-ttu-id="ef296-140">Gibt an, ob das Objekt mit der Option ANSI NULLS erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="ef296-140">Indicates if the object was created with the ANSI NULLs option.</span></span>  
  
     <span data-ttu-id="ef296-141">**Verschlüsselt**</span><span class="sxs-lookup"><span data-stu-id="ef296-141">**Encrypted**</span></span>  
     <span data-ttu-id="ef296-142">Gibt an, ob die Sicht verschlüsselt ist.</span><span class="sxs-lookup"><span data-stu-id="ef296-142">Indicates whether the view is encrypted.</span></span> <span data-ttu-id="ef296-143">Die Werte sind True und False.</span><span class="sxs-lookup"><span data-stu-id="ef296-143">Values are True and False.</span></span>  
  
     <span data-ttu-id="ef296-144">**Bezeichner in Anführungszeichen**</span><span class="sxs-lookup"><span data-stu-id="ef296-144">**Quoted identifier**</span></span>  
     <span data-ttu-id="ef296-145">Gibt an, ob das Objekt mit der Option Bezeichner in Anführungszeichen erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="ef296-145">Indicates if the object was created with the quoted identifier option.</span></span>  
  
     <span data-ttu-id="ef296-146">**Schema-gebunden**</span><span class="sxs-lookup"><span data-stu-id="ef296-146">**Schema bound**</span></span>  
     <span data-ttu-id="ef296-147">Gibt an, ob die Sicht Schema-gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="ef296-147">Indicates whether the view is schema-bound.</span></span> <span data-ttu-id="ef296-148">Die Werte sind True und False.</span><span class="sxs-lookup"><span data-stu-id="ef296-148">Values are True and False.</span></span> <span data-ttu-id="ef296-149">Informationen zu Schema-gebundenen Sichten finden Sie im Abschnitt SCHEMABINDING von [CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ef296-149">For information about schema-bound views, see the SCHEMABINDING portion of [CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql).</span></span>  
  
#### <a name="getting-view-properties-by-using-the-view-designer-tool"></a><span data-ttu-id="ef296-150">Abrufen von Sichteigenschaften mit dem Tool Sicht-Designer</span><span class="sxs-lookup"><span data-stu-id="ef296-150">Getting view properties by using the View Designer tool</span></span>  
  
1.  <span data-ttu-id="ef296-151">Erweitern Sie in **Objekt-Explorer**die Datenbank, die die Sicht enthält, deren Eigenschaften Sie anzeigen möchten, und erweitern Sie dann den Ordner **Sichten** .</span><span class="sxs-lookup"><span data-stu-id="ef296-151">In **Object Explorer**, expand the database that contains the view to which you want to view the properties, and then expand the **Views** folder.</span></span>  
  
2.  <span data-ttu-id="ef296-152">Klicken Sie mit der rechten Maustaste auf die Sicht, deren Eigenschaften Sie anzeigen möchten, und wählen Sie **Entwurf**aus.</span><span class="sxs-lookup"><span data-stu-id="ef296-152">Right-click the view of which you want to view the properties and select **Design**.</span></span>  
  
3.  <span data-ttu-id="ef296-153">Klicken Sie mit der rechten Maustaste in den Leerraum des Diagrammbereichs, und klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="ef296-153">Right-click in the blank space of the Diagram pane and click **Properties**.</span></span>  
  
     <span data-ttu-id="ef296-154">Die folgenden Eigenschaften werden im Bereich **Eigenschaften** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ef296-154">The following properties show in the **Properties** pane.</span></span>  
  
     <span data-ttu-id="ef296-155">**(Name)**</span><span class="sxs-lookup"><span data-stu-id="ef296-155">**(Name)**</span></span>  
     <span data-ttu-id="ef296-156">Name der aktuellen Sicht.</span><span class="sxs-lookup"><span data-stu-id="ef296-156">The name of the current view.</span></span>  
  
     <span data-ttu-id="ef296-157">**Database Name**</span><span class="sxs-lookup"><span data-stu-id="ef296-157">**Database Name**</span></span>  
     <span data-ttu-id="ef296-158">Name der Datenbank, die diese Sicht enthält.</span><span class="sxs-lookup"><span data-stu-id="ef296-158">The name of the database containing this view.</span></span>  
  
     <span data-ttu-id="ef296-159">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="ef296-159">**Description**</span></span>  
     <span data-ttu-id="ef296-160">Eine kurze Beschreibung der aktuellen Sicht.</span><span class="sxs-lookup"><span data-stu-id="ef296-160">A brief description of the current view.</span></span>  
  
     <span data-ttu-id="ef296-161">**Schema**</span><span class="sxs-lookup"><span data-stu-id="ef296-161">**Schema**</span></span>  
     <span data-ttu-id="ef296-162">Zeigt das Schema an, zu dem die Sicht gehört.</span><span class="sxs-lookup"><span data-stu-id="ef296-162">Displays the schema that owns the view.</span></span>  
  
     <span data-ttu-id="ef296-163">**Servername**</span><span class="sxs-lookup"><span data-stu-id="ef296-163">**Server Name**</span></span>  
     <span data-ttu-id="ef296-164">Name der aktuellen Serverinstanz.</span><span class="sxs-lookup"><span data-stu-id="ef296-164">The name of the current server instance.</span></span>  
  
     <span data-ttu-id="ef296-165">**An Schema binden**</span><span class="sxs-lookup"><span data-stu-id="ef296-165">**Bind to Schema**</span></span>  
     <span data-ttu-id="ef296-166">Verhindert, dass Benutzer die zugrunde liegenden Objekte ändern, die auf beliebige Weise zu dieser Sicht beitragen, was die Sichtdefinition ungültig machen würde.</span><span class="sxs-lookup"><span data-stu-id="ef296-166">Prevents users from modifying the underlying objects that contribute to this view in any way that would invalidate the view definition.</span></span>  
  
     <span data-ttu-id="ef296-167">**Deterministisch**</span><span class="sxs-lookup"><span data-stu-id="ef296-167">**Deterministic**</span></span>  
     <span data-ttu-id="ef296-168">Zeigt, ob der Datentyp der ausgewählten Spalte mit Sicherheit bestimmt werden kann</span><span class="sxs-lookup"><span data-stu-id="ef296-168">Shows whether the data type of the selected column can be determined with certainty</span></span>  
  
     <span data-ttu-id="ef296-169">**Unterschiedliche Werte**</span><span class="sxs-lookup"><span data-stu-id="ef296-169">**Distinct Values**</span></span>  
     <span data-ttu-id="ef296-170">Gibt an, dass die Abfrage alle Duplikate in der Sicht herausfiltert.</span><span class="sxs-lookup"><span data-stu-id="ef296-170">Specifies that the query will filter out duplicates in the view.</span></span> <span data-ttu-id="ef296-171">Diese Option ist hilfreich, wenn Sie nur einige Spalten aus einer Tabelle verwenden und diese möglicherweise doppelte Werte enthalten, oder wenn die Verknüpfung von mehreren Tabellen eine Verdopplung von Zeilen im Resultset zur Folge hat.</span><span class="sxs-lookup"><span data-stu-id="ef296-171">This option is useful when you are using only some of the columns from a table and those columns might contain duplicate values, or when the process of joining two or more tables produces duplicate rows in the result set.</span></span> <span data-ttu-id="ef296-172">Das Aktivieren dieser Option ist gleichbedeutend mit dem Einfügen des Schlüsselworts DISTINCT in die Anweisung im SQL-Bereich.</span><span class="sxs-lookup"><span data-stu-id="ef296-172">Choosing this option is equivalent to inserting the keyword DISTINCT into the statement in the SQL pane.</span></span>  
  
     <span data-ttu-id="ef296-173">**GROUP BY-Erweiterung**</span><span class="sxs-lookup"><span data-stu-id="ef296-173">**GROUP BY Extension**</span></span>  
     <span data-ttu-id="ef296-174">Gibt an, dass zusätzliche Optionen für Sichten verfügbar sind, die auf Aggregatabfragen basieren.</span><span class="sxs-lookup"><span data-stu-id="ef296-174">Specifies that additional options for views based on aggregate queries are available.</span></span>  
  
     <span data-ttu-id="ef296-175">**Alle Spalten ausgeben**</span><span class="sxs-lookup"><span data-stu-id="ef296-175">**Output All Columns**</span></span>  
     <span data-ttu-id="ef296-176">Zeigt an, ob alle Spalten von der ausgewählten Sicht zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ef296-176">Shows whether all columns are returned by the selected view.</span></span> <span data-ttu-id="ef296-177">Dies wird beim Erstellen der Sicht festgelegt.</span><span class="sxs-lookup"><span data-stu-id="ef296-177">This is set at the time the view is created.</span></span>  
  
     <span data-ttu-id="ef296-178">**SQL-Kommentar**</span><span class="sxs-lookup"><span data-stu-id="ef296-178">**SQL Comment**</span></span>  
     <span data-ttu-id="ef296-179">Zeigt eine Beschreibung der SQL-Anweisungen an.</span><span class="sxs-lookup"><span data-stu-id="ef296-179">Shows a description of the SQL statements.</span></span> <span data-ttu-id="ef296-180">Klicken Sie auf die Beschreibung, und klicken Sie anschließend auf die Auslassungspunkte **(...)** rechts neben der Eigenschaft, um die ganze Beschreibung anzuzeigen oder sie zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="ef296-180">To see the entire description, or to edit it, click the description and then click the ellipses **(...)** to the right of the property.</span></span> <span data-ttu-id="ef296-181">Kommentare können Informationen darüber enthalten, wer die Sicht verwendet und wann sie verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ef296-181">Your comments might include information such as who uses the view and when they use it.</span></span>  
  
     <span data-ttu-id="ef296-182">**Oberste Angabe**</span><span class="sxs-lookup"><span data-stu-id="ef296-182">**Top Specification**</span></span>  
     <span data-ttu-id="ef296-183">Erweitert das Element, um die Eigenschaften für **Oben**, **Ausdruck**, **Prozent**und **WITH TIES** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ef296-183">Expands to show properties for the **Top**, **Expression**, **Percent**, and **With Ties** properties.</span></span>  
  
     <span data-ttu-id="ef296-184">**(Nach oben)**</span><span class="sxs-lookup"><span data-stu-id="ef296-184">**(Top)**</span></span>  
     <span data-ttu-id="ef296-185">Gibt an, dass die Sicht eine TOP-Klausel enthält, die bewirkt, dass nur die ersten N Zeilen oder ersten N Prozent der Zeilen im Resultset zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ef296-185">Specifies that the view will include a TOP clause, which returns only the first n rows or first n percentage of rows in the result set.</span></span> <span data-ttu-id="ef296-186">In der Standardeinstellung gibt die Sicht die ersten 10 Zeilen im Resultset zurück.</span><span class="sxs-lookup"><span data-stu-id="ef296-186">The default is that the view returns the first 10 rows in the result set.</span></span> <span data-ttu-id="ef296-187">Verwenden Sie dies, um die Anzahl der zurückzugebenden Zeilen zu ändern oder einen anderen Prozentwert anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ef296-187">Use this to change the number of rows to return or to specify a different percentage</span></span>  
  
     <span data-ttu-id="ef296-188">**Ausdruck**</span><span class="sxs-lookup"><span data-stu-id="ef296-188">**Expression**</span></span>  
     <span data-ttu-id="ef296-189">Zeigt an, welchen Prozentsatz (wenn **Prozent** auf **Ja**festgelegt ist) oder welche Datensätze (wenn **Prozent** auf **Nein**festgelegt wird) die Sicht zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ef296-189">Shows what percent (if **Percent** is set to **Yes**) or records (if **Percent** is set to **No**) that the view will return.</span></span>  
  
     <span data-ttu-id="ef296-190">**Prozent**</span><span class="sxs-lookup"><span data-stu-id="ef296-190">**Percent**</span></span>  
     <span data-ttu-id="ef296-191">Gibt an, dass die Abfrage eine **TOP** -Klausel enthält, von der nur die ersten N Prozent der Zeilen im Resultset zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ef296-191">Specifies that the query will include a **TOP** clause, returning only the first n percentage of rows in the result set</span></span>  
  
     <span data-ttu-id="ef296-192">**WITH TIES**</span><span class="sxs-lookup"><span data-stu-id="ef296-192">**With Ties**</span></span>  
     <span data-ttu-id="ef296-193">Gibt an, dass die Sicht eine **WITH TIES** -Klausel enthält.</span><span class="sxs-lookup"><span data-stu-id="ef296-193">Specifies that the view will include a **WITH TIES** clause.</span></span> <span data-ttu-id="ef296-194">**WITH TIES** ist hilfreich, wenn eine Sicht sowohl eine **ORDER BY** -Klausel als auch eine **TOP** -Klausel mit Prozentangabe enthält.</span><span class="sxs-lookup"><span data-stu-id="ef296-194">**WITH TIES** is useful if a view includes an **ORDER BY** clause and a **TOP** clause based on percentage.</span></span> <span data-ttu-id="ef296-195">Wenn diese Option festgelegt ist und der Prozentbereich in der Mitte einer Zeilenfolge mit identischen Werten in der **ORDER BY** -Klausel endet, wird die Sicht bis ans Ende der betreffenden Zeilenfolge erweitert.</span><span class="sxs-lookup"><span data-stu-id="ef296-195">If this option is set, and if the percentage cutoff falls in the middle of a set of rows with identical values in the **ORDER BY** clause, the view is extended to include all such rows.</span></span>  
  
     <span data-ttu-id="ef296-196">**Spezifikation aktualisieren**</span><span class="sxs-lookup"><span data-stu-id="ef296-196">**Update Specification**</span></span>  
     <span data-ttu-id="ef296-197">Erweitert, um Eigenschaften für die Eigenschaften **Aktualisieren mit Sichtregeln** und **Überprüfungsoption** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ef296-197">Expands to show properties for the **Update Using View Rules** and **Check Option** properties.</span></span>  
  
     <span data-ttu-id="ef296-198">**(Aktualisieren mit Sichtregeln)**</span><span class="sxs-lookup"><span data-stu-id="ef296-198">**(Update Using View Rules)**</span></span>  
     <span data-ttu-id="ef296-199">Gibt an, dass alle Updates und Einfügungen für die Sicht von Microsoft Data Access Components (MDAC) in SQL-Anweisungen übersetzt werden, die auf die Sicht verweisen, statt in SQL-Anweisungen, die direkt auf die Basistabellen der Sicht verweisen.</span><span class="sxs-lookup"><span data-stu-id="ef296-199">Indicates that all updates and insertions to the view will be translated by Microsoft Data Access Components (MDAC) into SQL statements that refer to the view, rather than into SQL statements that refer directly to the view's base tables.</span></span>  
  
     <span data-ttu-id="ef296-200">In einigen Fällen gibt MDAC Sichtaktualisierungen und Sichteinfügevorgänge als Aktualisierungen und Einfügungen für die zugrunde liegenden Basistabellen der Sicht bekannt.</span><span class="sxs-lookup"><span data-stu-id="ef296-200">In some cases, MDAC manifests view update and view insert operations as updates and inserts against the view's underlying base tables.</span></span> <span data-ttu-id="ef296-201">Durch Auswahl von **Aktualisieren mit Sichtregeln**wird gewährleistet, dass MDAC Aktualisierungs- und Einfügevorgänge für die Sicht selbst generiert.</span><span class="sxs-lookup"><span data-stu-id="ef296-201">By selecting **Update Using View Rules**, you can ensure that MDAC generates update and insert operations against the view itself.</span></span>  
  
     <span data-ttu-id="ef296-202">**Überprüfungsoption**</span><span class="sxs-lookup"><span data-stu-id="ef296-202">**Check Option**</span></span>  
     <span data-ttu-id="ef296-203">Gibt an, dass beim Öffnen dieser Sicht und Ändern des Bereichs **Ergebnisse** die Datenquelle überprüft, ob die hinzugefügten oder geänderten Daten die **WHERE-Klausel** der Sichtdefinition erfüllen.</span><span class="sxs-lookup"><span data-stu-id="ef296-203">Indicates that when you open this view and modify the **Results** pane, the data source checks whether the added or modified data satisfies the **WHERE** clause of the view definition.</span></span> <span data-ttu-id="ef296-204">Wenn die Änderung die **WHERE** -Klausel nicht erfüllt, erhalten Sie eine Fehlermeldung mit weiteren Informationen.</span><span class="sxs-lookup"><span data-stu-id="ef296-204">If your modification do not satisfy the **WHERE** clause, you will see an error with more information.</span></span>  
  
#### <a name="to-get-dependencies-on-the-view"></a><span data-ttu-id="ef296-205">So rufen Sie Abhängigkeiten für die Sicht ab</span><span class="sxs-lookup"><span data-stu-id="ef296-205">To get dependencies on the view</span></span>  
  
1.  <span data-ttu-id="ef296-206">Erweitern Sie in **Objekt-Explorer**die Datenbank, die die Sicht enthält, deren Eigenschaften Sie anzeigen möchten, und erweitern Sie dann den Ordner **Sichten** .</span><span class="sxs-lookup"><span data-stu-id="ef296-206">In **Object Explorer**, expand the database that contains the view to which you want to view the properties, and then expand the **Views** folder.</span></span>  
  
2.  <span data-ttu-id="ef296-207">Klicken Sie mit der rechten Maustaste auf die Sicht, deren Eigenschaften Sie anzeigen möchten, und wählen Sie **Abhängigkeiten anzeigen**aus.</span><span class="sxs-lookup"><span data-stu-id="ef296-207">Right-click the view of which you want to view the properties and select **View Dependencies**.</span></span>  
  
3.  <span data-ttu-id="ef296-208">Wählen Sie **Objekte, die von [Sichtname] abhängig sind** aus, um die Objekte anzuzeigen, die auf die Sicht verweisen.</span><span class="sxs-lookup"><span data-stu-id="ef296-208">Select **Objects that depend on [view name]** to display the objects that refer to the view.</span></span>  
  
4.  <span data-ttu-id="ef296-209">Wählen Sie **Objekte, von denen [Sichtname] abhängt** aus, um die Objekte anzuzeigen, auf die von der Sicht verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="ef296-209">Select **Objects on which [view name] depends** to display the objects that are referenced by the view.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="ef296-210">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ef296-210">Using Transact-SQL</span></span>  
  
#### <a name="to-get-the-definition-and-properties-of-a-view"></a><span data-ttu-id="ef296-211">So rufen Sie die Definition und die Eigenschaften einer Sicht ab</span><span class="sxs-lookup"><span data-stu-id="ef296-211">To get the definition and properties of a view</span></span>  
  
1.  <span data-ttu-id="ef296-212">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="ef296-212">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="ef296-213">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="ef296-213">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="ef296-214">Kopieren Sie eines der folgenden Beispiele, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="ef296-214">Copy and paste one of the following examples into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT definition, uses_ansi_nulls, uses_quoted_identifier, is_schema_bound  
    FROM sys.sql_modules  
    WHERE object_id = OBJECT_ID('HumanResources.vEmployee');   
    GO  
    ```  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    SELECT OBJECT_DEFINITION (OBJECT_ID('HumanResources.vEmployee')) AS ObjectDefinition;   
    GO  
    ```  
  
    ```  
    EXEC sp_helptext 'HumanResources.vEmployee';  
    ```  
  
 <span data-ttu-id="ef296-215">Weitere Informationen finden Sie unter [sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql), [OBJECT_DEFINITION &#40;Transact-SQL&#41;](/sql/t-sql/functions/object-definition-transact-sql) und [sp_helptext &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helptext-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ef296-215">For more information, see [sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql), [OBJECT_DEFINITION &#40;Transact-SQL&#41;](/sql/t-sql/functions/object-definition-transact-sql) and [sp_helptext &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helptext-transact-sql).</span></span>  
  
#### <a name="to-get-the-dependencies-of-a-view"></a><span data-ttu-id="ef296-216">So rufen Sie die Abhängigkeiten einer Sicht ab</span><span class="sxs-lookup"><span data-stu-id="ef296-216">To get the dependencies of a view</span></span>  
  
1.  <span data-ttu-id="ef296-217">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="ef296-217">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="ef296-218">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="ef296-218">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="ef296-219">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="ef296-219">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT OBJECT_NAME(referencing_id) AS referencing_entity_name,   
        o.type_desc AS referencing_desciption,   
        COALESCE(COL_NAME(referencing_id, referencing_minor_id), '(n/a)') AS referencing_minor_id,   
        referencing_class_desc, referenced_class_desc,  
        referenced_server_name, referenced_database_name, referenced_schema_name,  
        referenced_entity_name,   
        COALESCE(COL_NAME(referenced_id, referenced_minor_id), '(n/a)') AS referenced_column_name,  
        is_caller_dependent, is_ambiguous  
    FROM sys.sql_expression_dependencies AS sed  
    INNER JOIN sys.objects AS o ON sed.referencing_id = o.object_id  
    WHERE referencing_id = OBJECT_ID(N'Production.vProductAndDescription');  
    GO  
    ```  
  
 <span data-ttu-id="ef296-220">Weitere Informationen finden Sie unter [sys.sql_expression_dependencies &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) und [sys.objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ef296-220">For more information, see [sys.sql_expression_dependencies &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) and [sys.objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql).</span></span>  
  
  
