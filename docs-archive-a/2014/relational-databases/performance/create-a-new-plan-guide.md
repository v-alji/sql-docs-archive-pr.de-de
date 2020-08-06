---
title: Erstellen einer neuen Planhinweisliste | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
f1_keywords:
- sql12.swb.designer.newplanguide.f1
helpviewer_keywords:
- creating plan guides
- plan guides [SQL Server]. creating
ms.assetid: e1ad78bb-4857-40ea-a0c6-dcf5c28aef2f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 60ba31e2a63575a316db5befb397bea59c0ad1e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622615"
---
# <a name="create-a-new-plan-guide"></a><span data-ttu-id="33ba7-102">Erstellen einer neuen Planhinweisliste</span><span class="sxs-lookup"><span data-stu-id="33ba7-102">Create a New Plan Guide</span></span>
  <span data-ttu-id="33ba7-103">Sie können in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]eine Planhinweisliste erstellen.</span><span class="sxs-lookup"><span data-stu-id="33ba7-103">You can create a plan guide in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="33ba7-104">Planhinweislisten beeinflussen die Abfrageoptimierung, indem Abfragehinweise oder ein fester Abfrageplan an die Abfragen angefügt werden.</span><span class="sxs-lookup"><span data-stu-id="33ba7-104">Plan guides influence query optimization by attaching query hints or a fixed query plan to them.</span></span> <span data-ttu-id="33ba7-105">In der Planhinweisliste geben Sie die [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung an, die optimiert werden soll, sowie entweder eine OPTION-Klausel mit den zu verwendenden Abfragehinweisen oder einen spezifischen Abfrageplan, der für die Optimierung der Abfrage verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="33ba7-105">In the plan guide, you specify the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement that you want optimized and either an OPTION clause that contains the query hints you want to use or a specific query plan you want to use to optimize the query.</span></span> <span data-ttu-id="33ba7-106">Wenn die Abfrage ausgeführt wird, vergleicht der Abfrageoptimierer die [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung mit der Planhinweisliste und fügt der Abfrage entweder zur Laufzeit die OPTION-Klausel hinzu oder verwendet den angegebenen Abfrageplan.</span><span class="sxs-lookup"><span data-stu-id="33ba7-106">When the query executes, the query optimizer matches the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement to the plan guide and either attaches the OPTION clause to the query at run time or uses the specified query plan.</span></span>  
  
 <span data-ttu-id="33ba7-107">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="33ba7-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="33ba7-108">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="33ba7-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="33ba7-109">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="33ba7-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="33ba7-110">Security</span><span class="sxs-lookup"><span data-stu-id="33ba7-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="33ba7-111">**So erstellen Sie eine Planhinweisliste mit:**</span><span class="sxs-lookup"><span data-stu-id="33ba7-111">**To create a plan guide, using:**</span></span>  
  
     [<span data-ttu-id="33ba7-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="33ba7-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="33ba7-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="33ba7-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="33ba7-114">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="33ba7-114">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="33ba7-115">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="33ba7-115">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="33ba7-116">Die Argumente für sp_create_plan_guide müssen in der angezeigten Reihenfolge bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="33ba7-116">The arguments to sp_create_plan_guide must be provided in the order that is shown.</span></span> <span data-ttu-id="33ba7-117">Wenn Sie Werte für die Parameter von `sp_create_plan_guide` angeben, müssen entweder alle oder überhaupt keine Parameternamen explizit angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="33ba7-117">When you supply values for the parameters of `sp_create_plan_guide`, all parameter names must be specified explicitly, or none at all.</span></span> <span data-ttu-id="33ba7-118">Wird z. B. `@name =` angegeben, müssen auch `@stmt =` , `@type =` usw. angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="33ba7-118">For example, if `@name =` is specified, then `@stmt =` , `@type =`, and so on, must also be specified.</span></span> <span data-ttu-id="33ba7-119">Ebenso dürfen, wenn `@name =` nicht angegeben und nur der Parameterwert bereitgestellt wird, die übrigen Parameterwerte ebenfalls nicht angegeben und nur ihre Werte bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="33ba7-119">Likewise, if `@name =` is omitted and only the parameter value is provided, the remaining parameter names must also be omitted, and only their values provided.</span></span> <span data-ttu-id="33ba7-120">Argumentnamen dienen nur zu Beschreibungszwecken, zum besseren Verständnis der Syntax.</span><span class="sxs-lookup"><span data-stu-id="33ba7-120">Argument names are for descriptive purposes only, to help understand the syntax.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="33ba7-121">überprüft nicht, ob der angegebene Parametername mit dem Namen des Parameters an der Position übereinstimmt, an der der Name verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="33ba7-121">does not verify that the specified parameter name matches the name for the parameter in the position where the name is used.</span></span>  
  
-   <span data-ttu-id="33ba7-122">Sie können mehr als eine Planhinweisliste des Typs OBJECT oder SQL für dieselbe Abfrage und den Batch oder das Modul erstellen.</span><span class="sxs-lookup"><span data-stu-id="33ba7-122">You can create more than one OBJECT or SQL plan guide for the same query and batch or module.</span></span> <span data-ttu-id="33ba7-123">Es kann jedoch nur jeweils eine Planhinweisliste aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="33ba7-123">However, only one plan guide can be enabled at any given time.</span></span>  
  
-   <span data-ttu-id="33ba7-124">Planhinweislisten vom Typ OBJECT können nicht für einen @module_or_batch-Wert erstellt werden, der auf eine gespeicherte Prozedur, Funktion oder einen DML-Trigger verweist, in der bzw. dem die WITH ENCRYPTION-Klausel angegeben wird oder die bzw. der temporär ist.</span><span class="sxs-lookup"><span data-stu-id="33ba7-124">Plan guides of type OBJECT cannot be created for an @module_or_batch value that references a stored procedure, function, or DML trigger that specifies the WITH ENCRYPTION clause or that is temporary.</span></span>  
  
-   <span data-ttu-id="33ba7-125">Das Löschen oder Ändern einer Funktion, einer gespeicherten Prozedur oder eines DML-Triggers, auf die bzw. den in einer Planhinweisliste verwiesen wird, verursacht einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="33ba7-125">Trying to drop or modify a function, stored procedure, or DML trigger that is referenced by a plan guide, either enabled or disabled, causes an error.</span></span> <span data-ttu-id="33ba7-126">Auch der Versuch, eine Tabelle mit einem Trigger zu löschen, auf den eine Planhinweisliste verweist, führt zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="33ba7-126">Trying to drop a table that has a trigger defined on it that is referenced by a plan guide also causes an error.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="33ba7-127">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="33ba7-127">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="33ba7-128">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="33ba7-128">Permissions</span></span>  
 <span data-ttu-id="33ba7-129">Zum Erstellen einer Planhinweisliste vom Typ OBJECT wird die ALTER-Berechtigung für das Objekt benötigt, auf das verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="33ba7-129">To create a plan guide of type OBJECT, requires ALTER permission on the referenced object.</span></span> <span data-ttu-id="33ba7-130">Zum Erstellen einer Planhinweisliste vom Typ SQL oder TEMPLATE wird die ALTER-Berechtigung für die aktuelle Datenbank benötigt.</span><span class="sxs-lookup"><span data-stu-id="33ba7-130">To create a plan guide of type SQL or TEMPLATE, requires ALTER permission on the current database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="33ba7-131">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="33ba7-131">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-plan-guide"></a><span data-ttu-id="33ba7-132">Erstellen einer Planhinweisliste</span><span class="sxs-lookup"><span data-stu-id="33ba7-132">To create a plan guide</span></span>  
  
1.  <span data-ttu-id="33ba7-133">Klicken Sie auf das Pluszeichen, um die Datenbank zu erweitern, in der Sie eine Planhinweisliste erstellen möchten, und klicken Sie dann auf das Pluszeichen, um den Ordner **Programmierbarkeit** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="33ba7-133">Click the plus sign to expand the database in which you want to create a plan guide, and then click the plus sign to expand the **Programmability** folder.</span></span>  
  
2.  <span data-ttu-id="33ba7-134">Klicken Sie mit der rechten Maustaste auf den Ordner **Plan** Hinweis Listen, und wählen Sie **neue Plan Hinweis**Liste aus.</span><span class="sxs-lookup"><span data-stu-id="33ba7-134">Right-click the **Plan Guides** folder and select **New Plan Guide...**.</span></span>  
  
3.  <span data-ttu-id="33ba7-135">Geben Sie im Dialogfeld **Neue Planhinweisliste** im Feld **Name** den Namen der Planhinweisliste ein.</span><span class="sxs-lookup"><span data-stu-id="33ba7-135">In the **New Plan Guide** dialog box, in the **Name** box, enter the name of the plan guide.</span></span>  
  
4.  <span data-ttu-id="33ba7-136">Geben Sie im Feld **Anweisung** die [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung ein, auf die die Planhinweisliste angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="33ba7-136">In the **Statement** box, enter the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement against which the plan guide is to be applied.</span></span>  
  
5.  <span data-ttu-id="33ba7-137">Wählen Sie in der Liste **Bereichstyp** den Entitätstyp aus, mit dem die [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="33ba7-137">In the **Scope type** list, select the type of entity in which the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement appears.</span></span> <span data-ttu-id="33ba7-138">Dies gibt den Kontext zum Abgleich der [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung mit der Planhinweisliste an.</span><span class="sxs-lookup"><span data-stu-id="33ba7-138">This specifies the context for matching the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement to the plan guide.</span></span> <span data-ttu-id="33ba7-139">Mögliche Werte sind **OBJECT**, **SQL**und **TEMPLATE**.</span><span class="sxs-lookup"><span data-stu-id="33ba7-139">Possible values are **OBJECT**, **SQL**, and **TEMPLATE**.</span></span>  
  
6.  <span data-ttu-id="33ba7-140">Geben Sie im Feld **Bereichsbatch** den Batchtext ein, mit dem die [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="33ba7-140">In the **Scope batch** box, enter the batch text in which the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement appears.</span></span> <span data-ttu-id="33ba7-141">Der Batchtext darf keine USE\`\`*Datenbank* -Anweisung enthalten.</span><span class="sxs-lookup"><span data-stu-id="33ba7-141">The batch text cannot include a USE\`\`*database* statement.</span></span> <span data-ttu-id="33ba7-142">Das Feld **Bereichsbatch** ist nur verfügbar, wenn **SQL** als Bereichstyp ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="33ba7-142">The **Scope batch** box is only available when **SQL** is selected as a scope type.</span></span> <span data-ttu-id="33ba7-143">Wenn bei Verwendung von SQL als Bereichstyp im Feld Bereichsbatch kein Wert angegeben wird, wird der Wert des Batchtexts auf den gleichen Wert wie im Feld **Anweisung** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="33ba7-143">If nothing is entered in the scope batch box when SQL is the scope type, then the value of the batch text is set to the same value as is in the **Statement** box.</span></span>  
  
7.  <span data-ttu-id="33ba7-144">Geben Sie in der Liste **Name von Bereichsschema** den Namen des Schemas ein, in dem sich das Objekt befindet.</span><span class="sxs-lookup"><span data-stu-id="33ba7-144">In the **Scope schema name** list, enter the name of the schema in which the object is contained.</span></span> <span data-ttu-id="33ba7-145">Das Feld **Name von Bereichsschema** ist nur verfügbar, wenn **Objekt** als Bereichstyp ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="33ba7-145">The **Scope schema name** box is only available when **Object** is selected as a scope type.</span></span>  
  
8.  <span data-ttu-id="33ba7-146">Geben Sie im Feld **Name von Bereichsobjekt** den Namen der gespeicherten [!INCLUDE[tsql](../../includes/tsql-md.md)] -Prozedur, der benutzerdefinierten Skalarfunktion, der aus mehreren Anweisungen bestehenden Tabellenwertfunktion oder des DML-Triggers ein, worin die [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="33ba7-146">In the **Scope object name** box, enter the name of the [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure, user-defined scalar function, multistatement table-valued function, or DML trigger in which the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement appears.</span></span> <span data-ttu-id="33ba7-147">Das Feld **Name von Bereichsobjekt** ist nur verfügbar, wenn **Objekt** als Bereichstyp ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="33ba7-147">The **Scope object name** box is only available when **Object** is selected as a scope type.</span></span>  
  
9. <span data-ttu-id="33ba7-148">Geben Sie im Feld **Parameter** den Parameternamen und Datentyp aller Parameter ein, die in die [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung eingebettet sind.</span><span class="sxs-lookup"><span data-stu-id="33ba7-148">In the **Parameters** box, enter the parameter name and data type of all parameters that are embedded in the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span>  
  
     <span data-ttu-id="33ba7-149">Parameter sind nur dann anwendbar, wenn eine der folgenden Aussagen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="33ba7-149">Parameters apply only when either of the following is true:</span></span>  
  
    -   <span data-ttu-id="33ba7-150">Der Bereichstyp lautet **SQL** oder **TEMPLATE**.</span><span class="sxs-lookup"><span data-stu-id="33ba7-150">The scope type is **SQL** or **TEMPLATE**.</span></span> <span data-ttu-id="33ba7-151">Bei **TEMPLATE**dürfen Parameter nicht NULL sein.</span><span class="sxs-lookup"><span data-stu-id="33ba7-151">If **TEMPLATE**, parameters must not be NULL.</span></span>  
  
    -   <span data-ttu-id="33ba7-152">Die [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung wird mithilfe von sp_executesql übermittelt und für den Parameter ein Wert festgelegt, oder [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] übermittelt eine Anweisung intern, nachdem sie parametrisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="33ba7-152">The [!INCLUDE[tsql](../../includes/tsql-md.md)] statement is submitted by using sp_executesql and a value for the parameter is specified, or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] internally submits a statement after parameterizing it.</span></span>  
  
10. <span data-ttu-id="33ba7-153">Geben Sie im Feld **Hinweise** die Abfragehinweise oder den Abfrageplan ein, die bzw. der auf die [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="33ba7-153">In the **Hints** box, enter the query hints or query plan to be applied to the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="33ba7-154">Geben Sie eine gültige OPTION-Klausel ein, um einen oder mehrere Abfragehinweise festzulegen.</span><span class="sxs-lookup"><span data-stu-id="33ba7-154">To specify one or more query hints, enter a valid OPTION clause.</span></span>  
  
11. <span data-ttu-id="33ba7-155">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="33ba7-155">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="33ba7-156">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="33ba7-156">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-plan-guide"></a><span data-ttu-id="33ba7-157">Erstellen einer Planhinweisliste</span><span class="sxs-lookup"><span data-stu-id="33ba7-157">To create a plan guide</span></span>  
  
1.  <span data-ttu-id="33ba7-158">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="33ba7-158">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="33ba7-159">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="33ba7-159">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="33ba7-160">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="33ba7-160">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- creates a plan guide named Guide1 based on a SQL statement  
    EXEC sp_create_plan_guide   
        @name = N'Guide1',   
        @stmt = N'SELECT TOP 1 *   
                  FROM Sales.SalesOrderHeader   
                  ORDER BY OrderDate DESC',   
        @type = N'SQL',  
        @module_or_batch = NULL,   
        @params = NULL,   
        @hints = N'OPTION (MAXDOP 1)';  
  
    ```  
  
 <span data-ttu-id="33ba7-161">Weitere Informationen finden Sie unter [sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="33ba7-161">For more information, see [sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql).</span></span>  
  
  
