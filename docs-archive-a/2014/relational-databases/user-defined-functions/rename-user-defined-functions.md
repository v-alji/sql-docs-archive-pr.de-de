---
title: Umbenennen von benutzerdefinierten Funktionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: c2695a5c-9cc5-4b18-8771-53027ca9a9af
author: rothja
ms.author: jroth
ms.openlocfilehash: ec923be64cf7819c4018ebda71a472f58b29cf8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630577"
---
# <a name="rename-user-defined-functions"></a><span data-ttu-id="ee05f-102">Umbenennen von benutzerdefinierten Funktionen</span><span class="sxs-lookup"><span data-stu-id="ee05f-102">Rename User-defined Functions</span></span>
  <span data-ttu-id="ee05f-103">Sie können benutzerdefinierte Funktionen in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]umbenennen.</span><span class="sxs-lookup"><span data-stu-id="ee05f-103">You can rename user-defined functions in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="ee05f-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="ee05f-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ee05f-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="ee05f-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ee05f-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="ee05f-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="ee05f-107">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="ee05f-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ee05f-108">**So benennen Sie benutzerdefinierte Funktionen um mit:**</span><span class="sxs-lookup"><span data-stu-id="ee05f-108">**To rename user-defined functions, using:**</span></span>  
  
     [<span data-ttu-id="ee05f-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ee05f-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="ee05f-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ee05f-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ee05f-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="ee05f-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="ee05f-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="ee05f-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="ee05f-113">Funktionsnamen müssen den Regeln für [Bezeichner](../databases/database-identifiers.md)entsprechen.</span><span class="sxs-lookup"><span data-stu-id="ee05f-113">Function names must comply with the rules for [identifiers](../databases/database-identifiers.md).</span></span>  
  
-   <span data-ttu-id="ee05f-114">Beim Umbenennen einer benutzerdefinierten Funktion wird der Name des entsprechenden Objektnamens in der Definitionsspalte der **sys.sql_modules** -Katalogsicht nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="ee05f-114">Renaming a user-defined function will not change the name of the corresponding object name in the definition column of the **sys.sql_modules** catalog view.</span></span> <span data-ttu-id="ee05f-115">Daher empfiehlt es sich, diesen Objekttyp nicht umzubenennen.</span><span class="sxs-lookup"><span data-stu-id="ee05f-115">Therefore, we recommend that you do not rename this object type.</span></span> <span data-ttu-id="ee05f-116">Löschen Sie die gespeicherte Prozedur stattdessen, und erstellen Sie sie unter dem neuen Namen neu.</span><span class="sxs-lookup"><span data-stu-id="ee05f-116">Instead, drop and re-create the stored procedure with its new name.</span></span>  
  
-   <span data-ttu-id="ee05f-117">Das Ändern des Namens oder der Definition einer benutzerdefinierten Funktion kann dazu führen, dass abhängige Objekte einen Fehler erzeugen, wenn die Objekte nicht so aktualisiert wurden, dass sie die Änderungen an der Funktion widerspiegeln.</span><span class="sxs-lookup"><span data-stu-id="ee05f-117">Changing the name or definition of a user-defined function can cause dependent objects to fail when the objects are not updated to reflect the changes that have been made to the function.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ee05f-118">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="ee05f-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ee05f-119">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="ee05f-119">Permissions</span></span>  
 <span data-ttu-id="ee05f-120">Zum Löschen der Funktion ist entweder die ALTER-Berechtigungen für das Schema, zu dem die Funktion gehört, oder die CONTROL-Berechtigung für die Funktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ee05f-120">To drop the function, requires either ALTER permission on the schema to which the function belongs or CONTROL permission on the function.</span></span> <span data-ttu-id="ee05f-121">Zum Neuerstellen der Funktion ist die CREATE FUNCTION-Berechtigung in der Datenbank und die ALTER-Berechtigung für das Schema erforderlich, in dem die Funktion erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="ee05f-121">To re-create the function, requires CREATE FUNCTION permission in the database and ALTER permission on the schema in which the function is being created.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ee05f-122">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ee05f-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-rename-user-defined-functions"></a><span data-ttu-id="ee05f-123">So benennen Sie benutzerdefinierte Funktionen um</span><span class="sxs-lookup"><span data-stu-id="ee05f-123">To rename user-defined functions</span></span>  
  
1.  <span data-ttu-id="ee05f-124">Klicken Sie im **Objekt-Explorer**auf das Pluszeichen neben der Datenbank, in der die Tabelle enthalten ist, die Sie umbenennen möchten.</span><span class="sxs-lookup"><span data-stu-id="ee05f-124">In **Object Explorer**, click the plus sign next to the database that contains the function you wish to rename and then</span></span>  
  
2.  <span data-ttu-id="ee05f-125">Klicken Sie neben dem Ordner **Programmierbarkeit** auf das Pluszeichen.</span><span class="sxs-lookup"><span data-stu-id="ee05f-125">Click the plus sign next to the **Programmability** folder.</span></span>  
  
3.  <span data-ttu-id="ee05f-126">Klicken Sie neben dem Ordner, der die Funktion enthält, die Sie umbenennen möchten, auf das Pluszeichen:</span><span class="sxs-lookup"><span data-stu-id="ee05f-126">Click the plus sign next to the folder that contains the function you wish to rename:</span></span>  
  
    -   <span data-ttu-id="ee05f-127">Table-valued Function</span><span class="sxs-lookup"><span data-stu-id="ee05f-127">Table-valued Function</span></span>  
  
    -   <span data-ttu-id="ee05f-128">Skalarwertfunktion</span><span class="sxs-lookup"><span data-stu-id="ee05f-128">Scalar-valued Function</span></span>  
  
    -   <span data-ttu-id="ee05f-129">Aggregatfunktion</span><span class="sxs-lookup"><span data-stu-id="ee05f-129">Aggregate Function</span></span>  
  
4.  <span data-ttu-id="ee05f-130">Klicken Sie mit der rechten Maustaste auf die Funktion, die Sie umbenennen möchten, und wählen Sie die Option **Umbenennen**.</span><span class="sxs-lookup"><span data-stu-id="ee05f-130">Right-click the function you wish to rename and select **Rename**.</span></span>  
  
5.  <span data-ttu-id="ee05f-131">Geben Sie den neuen Namen der Funktion ein.</span><span class="sxs-lookup"><span data-stu-id="ee05f-131">Enter the function's new name.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="ee05f-132">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ee05f-132">Using Transact-SQL</span></span>  
 <span data-ttu-id="ee05f-133">**So benennen Sie benutzerdefinierte Funktionen um**</span><span class="sxs-lookup"><span data-stu-id="ee05f-133">**To rename user-defined functions**</span></span>  
  
 <span data-ttu-id="ee05f-134">Diese Aufgabe kann nicht mit Transact-SQL-Anweisungen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ee05f-134">This task cannot be performed using Transact-SQL statements.</span></span> <span data-ttu-id="ee05f-135">Um eine benutzerdefinierte Funktion mit Transact-SQL umzubenennen, müssen Sie zuerst die vorhandene Funktion löschen und dann unter dem neuen Namen neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ee05f-135">To rename a user-defined function using Transact-SQL, you must first delete the existing function and then re-create it with the new name.</span></span> <span data-ttu-id="ee05f-136">Stellen Sie sicher, dass für den Code und alle Anwendungen, die den alten Namen der Funktion verwendet haben, jetzt der neue Name verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ee05f-136">Ensure that all code and applications that used the function's old name now use the new name.</span></span>  
  
 <span data-ttu-id="ee05f-137">Weitere Informationen finden Sie unter [CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql) und [DROP FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-function-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ee05f-137">For more information, see [CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql) and [DROP FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-function-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee05f-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ee05f-138">See Also</span></span>  
 <span data-ttu-id="ee05f-139">[sys.sql_expression_dependencies &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ee05f-139">[sys.sql_expression_dependencies &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) </span></span>  
 [<span data-ttu-id="ee05f-140">Anzeigen benutzerdefinierter Funktionen</span><span class="sxs-lookup"><span data-stu-id="ee05f-140">View User-defined Functions</span></span>](user-defined-functions.md)  
  
  
