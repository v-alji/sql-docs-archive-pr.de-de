---
title: Anzeigen benutzerdefinierter Funktionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.udfproperties.general.f1
- sql12.swb.functionproperties.general.f1
helpviewer_keywords:
- displaying user-defined functions
- viewing user-defined functions
- user-defined functions [SQL Server], viewing
- status information [SQL Server], user-defined functions
ms.assetid: a45dfab5-6384-4311-b935-2e23a70c5c10
author: rothja
ms.author: jroth
ms.openlocfilehash: 5248f75540b72b489a7605b2cca34144dfcfedbf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607591"
---
# <a name="view-user-defined-functions"></a><span data-ttu-id="d6353-102">Anzeigen benutzerdefinierter Funktionen</span><span class="sxs-lookup"><span data-stu-id="d6353-102">View User-defined Functions</span></span>
  <span data-ttu-id="d6353-103">Sie können Informationen zur Definition oder zu den Eigenschaften einer benutzerdefinierten Funktion in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]abrufen.</span><span class="sxs-lookup"><span data-stu-id="d6353-103">You can gain information about the definition or properties of a user-defined function in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="d6353-104">Manchmal ist es erforderlich, die Definition einer Funktion anzuzeigen, um zu verstehen, wie die Daten der Funktion aus den Quelltabellen abgeleitet werden, oder um die durch die Funktion definierten Daten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d6353-104">You may need to see the definition of the function to understand how its data is derived from the source tables or to see the data defined by the function.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d6353-105">Wenn Sie den Namen eines Objekts ändern, auf das eine Funktion verweist, müssen Sie den Text dieser Funktion mit dem neuen Namen aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="d6353-105">If you change the name of an object referenced by a function, you must modify that function so that its text reflects the new name.</span></span> <span data-ttu-id="d6353-106">Bevor Sie ein Objekt umbenennen, sollten Sie daher erst die Abhängigkeiten des Objekts anzeigen, um feststellen zu können, ob Funktionen von der beabsichtigten Änderung betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="d6353-106">Therefore, before renaming an object, display the dependencies of the object first to determine if any functions are affected by the proposed change.</span></span>  
  
 <span data-ttu-id="d6353-107">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="d6353-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d6353-108">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="d6353-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="d6353-109">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="d6353-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="d6353-110">**Abrufen von Informationen zu einer Funktion mit:**</span><span class="sxs-lookup"><span data-stu-id="d6353-110">**To get information about a function, using:**</span></span>  
  
     [<span data-ttu-id="d6353-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d6353-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="d6353-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d6353-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d6353-113">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="d6353-113">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d6353-114">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="d6353-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d6353-115">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="d6353-115">Permissions</span></span>  
 <span data-ttu-id="d6353-116">Das Anzeigen aller Abhängigkeiten einer Funktion mithilfe von **sys.sql_expression_dependencies** erfordert die VIEW DEFINITION-Berechtigung für die Datenbank und die SELECT-Berechtigung für **sys.sql_expression_dependencies** für die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="d6353-116">Using **sys.sql_expression_dependencies** to find all the dependencies on a function requires VIEW DEFINITION permission on the database and SELECT permission on **sys.sql_expression_dependencies** for the database.</span></span> <span data-ttu-id="d6353-117">Systemobjektdefinitionen, wie die in OBJECT_DEFINITION zurückgegebenen Definitionen, sind öffentlich sichtbar.</span><span class="sxs-lookup"><span data-stu-id="d6353-117">System object definitions, like the ones returned in OBJECT_DEFINITION, are publicly visible.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d6353-118">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d6353-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-show-a-user-defined-functions-properties"></a><span data-ttu-id="d6353-119">So zeigen Sie die Eigenschaften einer benutzerdefinierten Funktion an</span><span class="sxs-lookup"><span data-stu-id="d6353-119">To show a user-defined function's properties</span></span>  
  
1.  <span data-ttu-id="d6353-120">Klicken Sie im **Objekt-Explorer**auf das Pluszeichen neben der Datenbank mit der Funktion, deren Eigenschaften Sie anzeigen möchten, und klicken Sie dann auf das Pluszeichen, um den Ordner **Programmierbarkeit** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="d6353-120">In **Object Explorer**, click the plus sign next to the database that contains the function to which you want to view the properties, and then click the plus sign to expand the **Programmability** folder.</span></span>  
  
2.  <span data-ttu-id="d6353-121">Klicken Sie auf das Pluszeichen, um den Ordner **Funktionen** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="d6353-121">Click the plus sign to expand the **Functions** folder.</span></span>  
  
3.  <span data-ttu-id="d6353-122">Klicken Sie auf das Pluszeichen, um den Ordner mit der Funktion zu erweitern, deren Eigenschaften Sie anzeigen möchten:</span><span class="sxs-lookup"><span data-stu-id="d6353-122">Click the plus sign to expand the folder that contains the function to which you want to view the properties:</span></span>  
  
    -   <span data-ttu-id="d6353-123">Table-valued Function</span><span class="sxs-lookup"><span data-stu-id="d6353-123">Table-valued Function</span></span>  
  
    -   <span data-ttu-id="d6353-124">Skalarwertfunktion</span><span class="sxs-lookup"><span data-stu-id="d6353-124">Scalar-valued Function</span></span>  
  
    -   <span data-ttu-id="d6353-125">Aggregatfunktion</span><span class="sxs-lookup"><span data-stu-id="d6353-125">Aggregate Function</span></span>  
  
4.  <span data-ttu-id="d6353-126">Klicken Sie mit der rechten Maustaste auf die Funktion, deren Eigenschaften Sie anzeigen möchten, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="d6353-126">Right-click the function of which you want to view the properties and select **Properties**.</span></span>  
  
     <span data-ttu-id="d6353-127">Die folgenden Eigenschaften werden im Dialogfeld **Funktionseigenschaften -** _function_name_ angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d6353-127">The following properties appear in the **Function Properties -** _function_name_ dialog box.</span></span>  
  
     <span data-ttu-id="d6353-128">**Datenbank**</span><span class="sxs-lookup"><span data-stu-id="d6353-128">**Database**</span></span>  
     <span data-ttu-id="d6353-129">Name der Datenbank, die diese Funktion enthält.</span><span class="sxs-lookup"><span data-stu-id="d6353-129">The name of the database containing this function.</span></span>  
  
     <span data-ttu-id="d6353-130">**Server**</span><span class="sxs-lookup"><span data-stu-id="d6353-130">**Server**</span></span>  
     <span data-ttu-id="d6353-131">Name der aktuellen Serverinstanz.</span><span class="sxs-lookup"><span data-stu-id="d6353-131">The name of the current server instance.</span></span>  
  
     <span data-ttu-id="d6353-132">**Benutzer**</span><span class="sxs-lookup"><span data-stu-id="d6353-132">**User**</span></span>  
     <span data-ttu-id="d6353-133">Name des Benutzers dieser Verbindung.</span><span class="sxs-lookup"><span data-stu-id="d6353-133">The name of the user of this connection.</span></span>  
  
     <span data-ttu-id="d6353-134">**Erstellt am**</span><span class="sxs-lookup"><span data-stu-id="d6353-134">**Created date**</span></span>  
     <span data-ttu-id="d6353-135">Zeigt das Datum an, an dem die Funktion erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="d6353-135">Displays the date the function was created.</span></span>  
  
     <span data-ttu-id="d6353-136">**Ausführen als**</span><span class="sxs-lookup"><span data-stu-id="d6353-136">**Execute As**</span></span>  
     <span data-ttu-id="d6353-137">Ausführungskontext für die Funktion.</span><span class="sxs-lookup"><span data-stu-id="d6353-137">Execution context for the function.</span></span>  
  
     <span data-ttu-id="d6353-138">**Name**</span><span class="sxs-lookup"><span data-stu-id="d6353-138">**Name**</span></span>  
     <span data-ttu-id="d6353-139">Name der aktuellen Funktion.</span><span class="sxs-lookup"><span data-stu-id="d6353-139">The name of the current function.</span></span>  
  
     <span data-ttu-id="d6353-140">**Schema**</span><span class="sxs-lookup"><span data-stu-id="d6353-140">**Schema**</span></span>  
     <span data-ttu-id="d6353-141">Zeigt das Schema an, zu dem die Funktion gehört.</span><span class="sxs-lookup"><span data-stu-id="d6353-141">Displays the schema that owns the function.</span></span>  
  
     <span data-ttu-id="d6353-142">**Systemobjekt**</span><span class="sxs-lookup"><span data-stu-id="d6353-142">**System object**</span></span>  
     <span data-ttu-id="d6353-143">Gibt an, ob es sich bei der Funktion um ein Systemobjekt handelt.</span><span class="sxs-lookup"><span data-stu-id="d6353-143">Indicates whether the function is a system object.</span></span> <span data-ttu-id="d6353-144">Die Werte sind True und False.</span><span class="sxs-lookup"><span data-stu-id="d6353-144">Values are True and False.</span></span>  
  
     <span data-ttu-id="d6353-145">**ANSI NULLS**</span><span class="sxs-lookup"><span data-stu-id="d6353-145">**ANSI NULLs**</span></span>  
     <span data-ttu-id="d6353-146">Gibt an, ob das Objekt mit der Option ANSI NULLS erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="d6353-146">Indicates if the object was created with the ANSI NULLs option.</span></span>  
  
     <span data-ttu-id="d6353-147">**Verschlüsselt**</span><span class="sxs-lookup"><span data-stu-id="d6353-147">**Encrypted**</span></span>  
     <span data-ttu-id="d6353-148">Gibt an, ob die Funktion verschlüsselt ist.</span><span class="sxs-lookup"><span data-stu-id="d6353-148">Indicates whether the function is encrypted.</span></span> <span data-ttu-id="d6353-149">Die Werte sind True und False.</span><span class="sxs-lookup"><span data-stu-id="d6353-149">Values are True and False.</span></span>  
  
     <span data-ttu-id="d6353-150">**Funktionstyp**</span><span class="sxs-lookup"><span data-stu-id="d6353-150">**Function Type**</span></span>  
     <span data-ttu-id="d6353-151">Typ der benutzerdefinierten Funktion.</span><span class="sxs-lookup"><span data-stu-id="d6353-151">The type of user defined function.</span></span>  
  
     <span data-ttu-id="d6353-152">**Bezeichner in Anführungszeichen**</span><span class="sxs-lookup"><span data-stu-id="d6353-152">**Quoted identifier**</span></span>  
     <span data-ttu-id="d6353-153">Gibt an, ob das Objekt mit der Option Bezeichner in Anführungszeichen erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="d6353-153">Indicates if the object was created with the quoted identifier option.</span></span>  
  
     <span data-ttu-id="d6353-154">**Schema-gebunden**</span><span class="sxs-lookup"><span data-stu-id="d6353-154">**Schema bound**</span></span>  
     <span data-ttu-id="d6353-155">Gibt an, ob die Funktion Schema-gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="d6353-155">Indicates whether the function is schema-bound.</span></span> <span data-ttu-id="d6353-156">Die Werte sind True und False.</span><span class="sxs-lookup"><span data-stu-id="d6353-156">Values are True and False.</span></span> <span data-ttu-id="d6353-157">Informationen zu schemagebundenen Funktionen finden Sie im Abschnitt SCHEMABINDING von [CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d6353-157">For information about schema-bound functions, see the SCHEMABINDING section of [CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="d6353-158">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d6353-158">Using Transact-SQL</span></span>  
  
#### <a name="to-get-the-definition-and-properties-of-a-function"></a><span data-ttu-id="d6353-159">So rufen Sie die Definition und die Eigenschaften einer Funktion ab</span><span class="sxs-lookup"><span data-stu-id="d6353-159">To get the definition and properties of a function</span></span>  
  
1.  <span data-ttu-id="d6353-160">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="d6353-160">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d6353-161">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="d6353-161">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d6353-162">Kopieren Sie eines der folgenden Beispiele, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="d6353-162">Copy and paste one of the following examples into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Get the function name, definition, and relevant properties  
    SELECT sm.object_id,   
       OBJECT_NAME(sm.object_id) AS object_name,   
       o.type,   
       o.type_desc,   
       sm.definition,  
       sm.uses_ansi_nulls,  
       sm.uses_quoted_identifier,  
       sm.is_schema_bound,  
       sm.execute_as_principal_id  
    -- using the two system tables sys.sql_modules and sys.objects  
    FROM sys.sql_modules AS sm  
    JOIN sys.objects AS o ON sm.object_id = o.object_id  
    -- from the function 'dbo.ufnGetProductDealerPrice'  
    WHERE sm.object_id = OBJECT_ID('dbo.ufnGetProductDealerPrice')  
    ORDER BY o.type;  
    GO  
  
    ```  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Get the definition of the function dbo.ufnGetProductDealerPrice  
    SELECT OBJECT_DEFINITION (OBJECT_ID('dbo.ufnGetProductDealerPrice')) AS ObjectDefinition;  
    GO  
    ```  
  
 <span data-ttu-id="d6353-163">Weitere Informationen finden Sie unter [sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) und [OBJECT_DEFINITION &#40;Transact-SQL&#41;](/sql/t-sql/functions/object-definition-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d6353-163">For more information, see [sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) and [OBJECT_DEFINITION &#40;Transact-SQL&#41;](/sql/t-sql/functions/object-definition-transact-sql).</span></span>  
  
#### <a name="to-get-the-dependencies-of-a-function"></a><span data-ttu-id="d6353-164">So rufen Sie die Abhängigkeiten einer Funktion ab</span><span class="sxs-lookup"><span data-stu-id="d6353-164">To get the dependencies of a function</span></span>  
  
1.  <span data-ttu-id="d6353-165">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="d6353-165">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d6353-166">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="d6353-166">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d6353-167">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="d6353-167">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Get all of the dependency information  
    SELECT OBJECT_NAME(sed.referencing_id) AS referencing_entity_name,   
        o.type_desc AS referencing_desciption,   
        COALESCE(COL_NAME(sed.referencing_id, sed.referencing_minor_id), '(n/a)') AS referencing_minor_id,   
        sed.referencing_class_desc, sed.referenced_class_desc,  
        sed.referenced_server_name, sed.referenced_database_name, sed.referenced_schema_name,  
        sed.referenced_entity_name,   
        COALESCE(COL_NAME(sed.referenced_id, sed.referenced_minor_id), '(n/a)') AS referenced_column_name,  
        sed.is_caller_dependent, sed.is_ambiguous  
    -- from the two system tables sys.sql_expression_dependencies and sys.object  
    FROM sys.sql_expression_dependencies AS sed  
    INNER JOIN sys.objects AS o ON sed.referencing_id = o.object_id  
    -- on the function dbo.ufnGetProductDealerPrice  
    WHERE sed.referencing_id = OBJECT_ID('dbo.ufnGetProductDealerPrice');  
    GO  
    ```  
  
 <span data-ttu-id="d6353-168">Weitere Informationen finden Sie unter [sys.sql_expression_dependencies &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) und [sys.objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d6353-168">For more information, see [sys.sql_expression_dependencies &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) and [sys.objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql).</span></span>  
  
  
