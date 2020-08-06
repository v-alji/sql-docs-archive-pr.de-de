---
title: Erstellen eines benutzerdefinierten Datentypalias | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.userdefineddatatype.general.f1
- sql12.swb.new.datatype.properties.general.f1
helpviewer_keywords:
- alias data types [SQL Server], creating
ms.assetid: b1dd8413-0cd0-411b-a79b-1bb043ccc62d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 35db332c23e2df5a8e67c3677cd2411768816765
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607824"
---
# <a name="create-a-user-defined-data-type-alias"></a><span data-ttu-id="df2e0-102">Erstellen eines benutzerdefinierten Datentypalias</span><span class="sxs-lookup"><span data-stu-id="df2e0-102">Create a User-Defined Data Type Alias</span></span>
  <span data-ttu-id="df2e0-103">In diesem Thema wird beschrieben, wie ein neuer benutzerdefinierter Datentypalias in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="df2e0-103">This topic describes how to create a new user-defined data type alias in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="df2e0-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="df2e0-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="df2e0-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="df2e0-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="df2e0-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="df2e0-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="df2e0-107">Security</span><span class="sxs-lookup"><span data-stu-id="df2e0-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="df2e0-108">**So erstellen Sie einen benutzerdefinierten Datentypalias mit:**</span><span class="sxs-lookup"><span data-stu-id="df2e0-108">**To create a user-defined data type alias, using:**</span></span>  
  
     [<span data-ttu-id="df2e0-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="df2e0-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="df2e0-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="df2e0-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="df2e0-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="df2e0-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="df2e0-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="df2e0-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="df2e0-113">Bei der Verwendung eines Namens für einen benutzerdefinierten Datentypalias müssen die Regeln für Bezeichner eingehalten werden.</span><span class="sxs-lookup"><span data-stu-id="df2e0-113">The name of a user-defined data type alias must comply with the rules for identifiers.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="df2e0-114">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="df2e0-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="df2e0-115">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="df2e0-115">Permissions</span></span>  
 <span data-ttu-id="df2e0-116">Erfordert die CREATE TYPE-Berechtigung für die aktuelle Datenbank und die ALTER-Berechtigung für *schema_name*.</span><span class="sxs-lookup"><span data-stu-id="df2e0-116">Requires CREATE TYPE permission in the current database and ALTER permission on *schema_name*.</span></span> <span data-ttu-id="df2e0-117">Wenn *schema_name* nicht angegeben wird, gelten die Standardregeln für die Namensauflösung, um das Schema für den aktuellen Benutzer zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="df2e0-117">If *schema_name* is not specified, the default name resolution rules for determining the schema for the current user apply.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="df2e0-118">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="df2e0-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-user-defined-data-type"></a><span data-ttu-id="df2e0-119">So erstellen Sie einen benutzerdefinierten Datentyp</span><span class="sxs-lookup"><span data-stu-id="df2e0-119">To create a user-defined data type</span></span>  
  
1.  <span data-ttu-id="df2e0-120">Erweitern Sie im Objekt-Explorer **Datenbanken**, erweitern Sie eine Datenbank, erweitern Sie **Programmierbarkeit**, erweitern Sie **Typen**, klicken Sie mit der rechten Maustaste auf **Benutzerdefinierte Datentypen**, und klicken Sie dann auf **Neuer benutzerdefinierter Datentyp**.</span><span class="sxs-lookup"><span data-stu-id="df2e0-120">In Object Explorer, expand **Databases**, expand a database, expand **Programmability**, expand **Types**, right-click **User-Defined Data Types**, and then click **New User-Defined Data Type**.</span></span>  
  
     <span data-ttu-id="df2e0-121">**NULL-Werte zulassen**</span><span class="sxs-lookup"><span data-stu-id="df2e0-121">**Allow NULLs**</span></span>  
     <span data-ttu-id="df2e0-122">Geben Sie an, ob der benutzerdefinierte Datentyp NULL-Werte akzeptieren kann.</span><span class="sxs-lookup"><span data-stu-id="df2e0-122">Specify whether the user-defined data type can accept NULL values.</span></span> <span data-ttu-id="df2e0-123">Die NULL-Zulässigkeit eines vorhandenen benutzerdefinierten Datentyps ist nicht bearbeitbar.</span><span class="sxs-lookup"><span data-stu-id="df2e0-123">The nullability of an existing user-defined data type is not editable.</span></span>  
  
     <span data-ttu-id="df2e0-124">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="df2e0-124">**Data type**</span></span>  
     <span data-ttu-id="df2e0-125">Wählen Sie den Basisdatentyp aus dem Listenfeld aus.</span><span class="sxs-lookup"><span data-stu-id="df2e0-125">Select the base data type from the list box.</span></span> <span data-ttu-id="df2e0-126">Im Listenfeld werden alle Datentypen mit Ausnahme der Datentypen `geography`, `geometry`, `hierarchyid`, `sysname`, `timestamp` und `xml` angezeigt.</span><span class="sxs-lookup"><span data-stu-id="df2e0-126">The list box displays all data types except for the `geography`, `geometry`, `hierarchyid`, `sysname`, `timestamp` , and `xml` data types.</span></span> <span data-ttu-id="df2e0-127">Der Datentyp eines vorhandenen benutzerdefinierten Datentyps ist nicht bearbeitbar.</span><span class="sxs-lookup"><span data-stu-id="df2e0-127">The data type of an existing user-defined data type is not editable.</span></span>  
  
     <span data-ttu-id="df2e0-128">**Standard**</span><span class="sxs-lookup"><span data-stu-id="df2e0-128">**Default**</span></span>  
     <span data-ttu-id="df2e0-129">Wählen Sie optional eine Regel oder einen Standardwert zum Binden an den benutzerdefinierten Datentypalias aus.</span><span class="sxs-lookup"><span data-stu-id="df2e0-129">Optionally select a rule or a default to bind to the user-defined data type alias.</span></span>  
  
     <span data-ttu-id="df2e0-130">**Länge/Genauigkeit**</span><span class="sxs-lookup"><span data-stu-id="df2e0-130">**Length/Precision**</span></span>  
     <span data-ttu-id="df2e0-131">Zeigt jeweils die Länge bzw. Genauigkeit des Datentyps an.</span><span class="sxs-lookup"><span data-stu-id="df2e0-131">Displays the length or precision of the data type as applicable.</span></span> <span data-ttu-id="df2e0-132">**Länge** gilt für zeichenbasierte benutzerdefinierte Datentypen, und **Genauigkeit** gilt nur für auf numerischen Werten basierende benutzerdefinierte Datentypen.</span><span class="sxs-lookup"><span data-stu-id="df2e0-132">**Length** applies to character-based user-defined data types; **Precision** applies only to numeric-based user-defined data types.</span></span> <span data-ttu-id="df2e0-133">Die Bezeichnung ändert sich je nach dem zuvor gewählten Datentyp.</span><span class="sxs-lookup"><span data-stu-id="df2e0-133">The label changes depending on the data type selected earlier.</span></span> <span data-ttu-id="df2e0-134">Dieses Feld ist bearbeitbar, wenn die Länge oder Genauigkeit des ausgewählten Datentyps fest ist.</span><span class="sxs-lookup"><span data-stu-id="df2e0-134">This box is not editable if the length or precision of the selected data type is fixed.</span></span>  
  
     <span data-ttu-id="df2e0-135">Für die Datentypen `nvarchar(max)`, `varchar(max)` oder `varbinary(max)` wird keine Länge angezeigt.</span><span class="sxs-lookup"><span data-stu-id="df2e0-135">Length is not displayed for `nvarchar(max)`, `varchar(max)`, or `varbinary(max)` data types.</span></span>  
  
     <span data-ttu-id="df2e0-136">**Name**</span><span class="sxs-lookup"><span data-stu-id="df2e0-136">**Name**</span></span>  
     <span data-ttu-id="df2e0-137">Wenn Sie einen neuen benutzerdefinierten Datentypalias erstellen, geben Sie einen eindeutigen Namen ein, der in der gesamten Datenbank verwendet werden soll, um den benutzerdefinierten Datentyp darzustellen.</span><span class="sxs-lookup"><span data-stu-id="df2e0-137">If you are creating a new user-defined data type alias, type a unique name to be used across the database to represent the user-defined data type.</span></span> <span data-ttu-id="df2e0-138">Die maximale Anzahl von Zeichen muss dem System `sysname` Datentyp entsprechen.</span><span class="sxs-lookup"><span data-stu-id="df2e0-138">The maximum number of characters must match the system `sysname` data type.</span></span> <span data-ttu-id="df2e0-139">Der Name eines vorhandenen benutzerdefinierten Datentypalias ist nicht bearbeitbar.</span><span class="sxs-lookup"><span data-stu-id="df2e0-139">The name of an existing user-defined data type alias is not editable.</span></span>  
  
     <span data-ttu-id="df2e0-140">**Regel**</span><span class="sxs-lookup"><span data-stu-id="df2e0-140">**Rule**</span></span>  
     <span data-ttu-id="df2e0-141">Wählen Sie optional eine Regel zum Binden an den benutzerdefinierten Datentypalias aus.</span><span class="sxs-lookup"><span data-stu-id="df2e0-141">Optionally select a rule to bind to the user-defined data type alias.</span></span>  
  
     <span data-ttu-id="df2e0-142">**Skalieren**</span><span class="sxs-lookup"><span data-stu-id="df2e0-142">**Scale**</span></span>  
     <span data-ttu-id="df2e0-143">Gibt an, wie viele Dezimalstellen (Ziffern nach dem Dezimalzeichen) maximal gespeichert werden können.</span><span class="sxs-lookup"><span data-stu-id="df2e0-143">Specify the maximum number of decimal digits that can be stored to the right of the decimal point.</span></span>  
  
     <span data-ttu-id="df2e0-144">**Schema**</span><span class="sxs-lookup"><span data-stu-id="df2e0-144">**Schema**</span></span>  
     <span data-ttu-id="df2e0-145">Wählen Sie ein Schema aus einer Liste mit allen für den aktuellen Benutzer verfügbaren Schemas aus.</span><span class="sxs-lookup"><span data-stu-id="df2e0-145">Select a schema from a list of all schemas available to the current user.</span></span> <span data-ttu-id="df2e0-146">Die Standardauswahl ist das Standardschema für den aktuellen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="df2e0-146">The default selection is the default schema for the current user.</span></span>  
  
     <span data-ttu-id="df2e0-147">**Storage**</span><span class="sxs-lookup"><span data-stu-id="df2e0-147">**Storage**</span></span>  
     <span data-ttu-id="df2e0-148">Zeigt die maximale Speichergröße für den benutzerdefinierten Datentypalias an.</span><span class="sxs-lookup"><span data-stu-id="df2e0-148">Displays the maximum storage size for the user-defined data type alias.</span></span> <span data-ttu-id="df2e0-149">Die maximalen Speicherplatzgrößen variieren in Abhängigkeit von der Genauigkeit.</span><span class="sxs-lookup"><span data-stu-id="df2e0-149">Maximum storage sizes vary, based on precision.</span></span>  
  
    |||  
    |-|-|  
    |<span data-ttu-id="df2e0-150">1 – 9</span><span class="sxs-lookup"><span data-stu-id="df2e0-150">1 - 9</span></span>|<span data-ttu-id="df2e0-151">5</span><span class="sxs-lookup"><span data-stu-id="df2e0-151">5</span></span>|  
    |<span data-ttu-id="df2e0-152">10 – 19</span><span class="sxs-lookup"><span data-stu-id="df2e0-152">10 - 19</span></span>|<span data-ttu-id="df2e0-153">9</span><span class="sxs-lookup"><span data-stu-id="df2e0-153">9</span></span>|  
    |<span data-ttu-id="df2e0-154">20 – 28</span><span class="sxs-lookup"><span data-stu-id="df2e0-154">20 - 28</span></span>|<span data-ttu-id="df2e0-155">13</span><span class="sxs-lookup"><span data-stu-id="df2e0-155">13</span></span>|  
    |<span data-ttu-id="df2e0-156">29 – 38</span><span class="sxs-lookup"><span data-stu-id="df2e0-156">29 - 38</span></span>|<span data-ttu-id="df2e0-157">17</span><span class="sxs-lookup"><span data-stu-id="df2e0-157">17</span></span>|  
  
     <span data-ttu-id="df2e0-158">Bei `nchar` `nvarchar` den Datentypen und ist der Speicher Wert immer das Zweifache des Werts in **Länge**.</span><span class="sxs-lookup"><span data-stu-id="df2e0-158">For `nchar` and `nvarchar` data types, the storage value is always two times the value in **Length**.</span></span>  
  
     <span data-ttu-id="df2e0-159">Für die Datentypen `nvarchar(max)`, `varchar(max)` oder `varbinary(max)` wird kein Speicher angezeigt.</span><span class="sxs-lookup"><span data-stu-id="df2e0-159">Storage is not displayed for `nvarchar(max)`, `varchar(max)`, or `varbinary(max)` data types.</span></span>  
  
2.  <span data-ttu-id="df2e0-160">Geben Sie im Dialogfeld **Neuer benutzerdefinierter Datentyp** in das Feld **Schema** das Schema ein, das diesen Datentypalias besitzen soll, oder wählen Sie mit der Schaltfläche zum Durchsuchen das Schema aus.</span><span class="sxs-lookup"><span data-stu-id="df2e0-160">In the **New User-defined Data Type** dialog box, in the **Schema** box, type the schema to own this data type alias, or use the browse button to select the schema.</span></span>  
  
3.  <span data-ttu-id="df2e0-161">Geben Sie in das Feld **Name** einen Namen für den neuen Datentypalias ein.</span><span class="sxs-lookup"><span data-stu-id="df2e0-161">In the **Name** box, type a name for the new data type alias.</span></span>  
  
4.  <span data-ttu-id="df2e0-162">Wählen Sie im Feld **Datentyp** den Datentyp aus, auf dem der neue Datentypalias basieren soll.</span><span class="sxs-lookup"><span data-stu-id="df2e0-162">In the **Data type** box, select the data type that the new data type alias will be based on.</span></span>  
  
5.  <span data-ttu-id="df2e0-163">Vervollständigen Sie, soweit für diesen Datentyp zutreffend, die Felder **Länge**, **Genauigkeit**und **Dezimalstellen** .</span><span class="sxs-lookup"><span data-stu-id="df2e0-163">Complete the **Length**, **Precision**, and **Scale** boxes if appropriate for that data type.</span></span>  
  
6.  <span data-ttu-id="df2e0-164">Aktivieren Sie **NULL-Werte zulassen** , damit der neue Datentypalias NULL-Werte zulässt.</span><span class="sxs-lookup"><span data-stu-id="df2e0-164">Check **Allow NULLs** if the new data type alias can permit NULL values.</span></span>  
  
7.  <span data-ttu-id="df2e0-165">Vervollständigen Sie im Bereich **Bindung** die Felder **Standard** oder **Regel** , falls Sie dem neuen Datentypalias einen Standardwert oder eine Regel zuordnen möchten.</span><span class="sxs-lookup"><span data-stu-id="df2e0-165">In the **Binding** area, complete the **Default** or **Rule** boxes if you want to bind a default or rule to the new data type alias.</span></span> <span data-ttu-id="df2e0-166">Standardwerte und Regeln können in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]nicht erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="df2e0-166">Defaults and rules cannot be created in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="df2e0-167">Verwenden Sie [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="df2e0-167">Use [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="df2e0-168">Beispielcode zum Erstellen von Standardwerten und Regeln finden Sie im Vorlagen-Explorer.</span><span class="sxs-lookup"><span data-stu-id="df2e0-168">Example code for creating defaults and rules are available in Template Explorer.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="df2e0-169">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="df2e0-169">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-user-defined-data-type-alias"></a><span data-ttu-id="df2e0-170">So erstellen Sie einen benutzerdefinierten Datentypalias</span><span class="sxs-lookup"><span data-stu-id="df2e0-170">To create a user-defined data type alias</span></span>  
  
1.  <span data-ttu-id="df2e0-171">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="df2e0-171">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="df2e0-172">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="df2e0-172">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="df2e0-173">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="df2e0-173">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="df2e0-174">In diesem Beispiel wird ein Datentypalias erstellt, der auf dem vom System bereitgestellten Datentyp `varchar` basiert.</span><span class="sxs-lookup"><span data-stu-id="df2e0-174">This example creates a data type alias based on the system-supplied `varchar` data type.</span></span> <span data-ttu-id="df2e0-175">Der Datentypalias `ssn` wird für Spalten mit elfstelligen Sozialversicherungsnummern verwendet (999-99-9999).</span><span class="sxs-lookup"><span data-stu-id="df2e0-175">The `ssn` data type alias is used for columns holding 11-digit social security numbers (999-99-9999).</span></span> <span data-ttu-id="df2e0-176">Diese Spalte darf nicht den Wert NULL aufweisen.</span><span class="sxs-lookup"><span data-stu-id="df2e0-176">The column cannot be NULL.</span></span>  
  
```sql  
CREATE TYPE ssn  
FROM varchar(11) NOT NULL ;  
```  
  
## <a name="see-also"></a><span data-ttu-id="df2e0-177">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="df2e0-177">See Also</span></span>  
 <span data-ttu-id="df2e0-178">[Datenbankbezeichner](database-identifiers.md) </span><span class="sxs-lookup"><span data-stu-id="df2e0-178">[Database Identifiers](database-identifiers.md) </span></span>  
 [<span data-ttu-id="df2e0-179">CREATE TYPE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="df2e0-179">CREATE TYPE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-type-transact-sql)  
  
  
