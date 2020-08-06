---
title: Erstellen eindeutiger Indizes | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- unique indexes
- designing indexes [SQL Server], unique
- clustered indexes, unique
- indexes [SQL Server], unique
- nonclustered indexes [SQL Server], unique
- unique indexes, design guidelines
ms.assetid: 56b5982e-cb94-46c0-8fbb-772fc275354a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8c96c4e17a8ce0863452db171302d650f6114919
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724622"
---
# <a name="create-unique-indexes"></a><span data-ttu-id="4a5bc-102">Erstellen eindeutiger Indizes</span><span class="sxs-lookup"><span data-stu-id="4a5bc-102">Create Unique Indexes</span></span>
  <span data-ttu-id="4a5bc-103">In diesem Thema wird beschrieben, wie ein eindeutiger Index auf einer Tabelle in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="4a5bc-103">This topic describes how to create a unique index on a table in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="4a5bc-104">Ein eindeutiger Index garantiert, dass der Indexschlüssel keine doppelten Werte enthält und dass deshalb jede Zeile in der Tabelle in gewisser Weise eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="4a5bc-104">A unique index guarantees that the index key contains no duplicate values and therefore every row in the table is in some way unique.</span></span> <span data-ttu-id="4a5bc-105">Es gibt keine bedeutenden Unterschiede zwischen dem Erstellen einer UNIQUE-Einschränkung und dem Erstellen eines eindeutigen, von Einschränkungen unabhängigen Index.</span><span class="sxs-lookup"><span data-stu-id="4a5bc-105">There are no significant differences between creating a UNIQUE constraint and creating a unique index that is independent of a constraint.</span></span> <span data-ttu-id="4a5bc-106">Die Datenüberprüfung erfolgt auf dieselbe Weise, und der Abfrageoptimierer macht keinen Unterschied zwischen einem durch eine Einschränkung erstellten eindeutigen Index und einem manuell erstellten.</span><span class="sxs-lookup"><span data-stu-id="4a5bc-106">Data validation occurs in the same manner, and the query optimizer does not differentiate between a unique index created by a constraint or manually created.</span></span> <span data-ttu-id="4a5bc-107">Das Erstellen einer UNIQUE-Einschränkung auf der Spalte verdeutlicht jedoch die Zielsetzung des Indexes.</span><span class="sxs-lookup"><span data-stu-id="4a5bc-107">However, creating a UNIQUE constraint on the column makes the objective of the index clear.</span></span> <span data-ttu-id="4a5bc-108">Weitere Informationen zu UNIQUE-Einschränkungen finden Sie unter [Unique Constraints and Check Constraints](../tables/unique-constraints-and-check-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="4a5bc-108">For more information on UNIQUE constraints, see [Unique Constraints and Check Constraints](../tables/unique-constraints-and-check-constraints.md).</span></span>  
  
 <span data-ttu-id="4a5bc-109">Beim Erstellen eines eindeutigen Indexes können Sie eine Option aktivieren, um doppelt vorhandene Schlüssel zu ignorieren.</span><span class="sxs-lookup"><span data-stu-id="4a5bc-109">When you create a unique index, you can set an option to ignore duplicate keys.</span></span> <span data-ttu-id="4a5bc-110">Wenn diese Option auf **Ja** festgelegt ist und Sie versuchen, doppelte Schlüssel zu erstellen, indem Sie (mit der INSERT-Anweisung) Daten hinzufügen, die mehrere Zeilen betreffen, wird die Zeile mit dem Duplikat nicht hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="4a5bc-110">If this option is set to **Yes** and you attempt to create duplicate keys by adding data that affects multiple rows (with the INSERT statement), the row containing a duplicate is not added.</span></span> <span data-ttu-id="4a5bc-111">Wenn die Option auf **Nein**festgelegt ist, schlägt die gesamte INSERT-Operation fehl, und alle Daten werden zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="4a5bc-111">If it is set to **No**, the entire insert operation fails and all the data is rolled back.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4a5bc-112">Sie können keinen eindeutigen Index für eine einzelne Spalte erstellen, wenn mehr als eine Zeile der Spalte NULL enthält.</span><span class="sxs-lookup"><span data-stu-id="4a5bc-112">You cannot create a unique index on a single column if that column contains NULL in more than one row.</span></span> <span data-ttu-id="4a5bc-113">Ebenso können Sie keinen eindeutigen Index für mehrere Spalten erstellen, wenn die Spaltenkombination in mehreren Zeilen NULL enthält.</span><span class="sxs-lookup"><span data-stu-id="4a5bc-113">Similarly, you cannot create a unique index on multiple columns if the combination of columns contains NULL in more than one row.</span></span> <span data-ttu-id="4a5bc-114">Diese werden beim Indizieren als doppelt vorhandene Werte betrachtet.</span><span class="sxs-lookup"><span data-stu-id="4a5bc-114">These are treated as duplicate values for indexing purposes.</span></span>  
  
 <span data-ttu-id="4a5bc-115">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="4a5bc-115">**In This Topic**</span></span>  
  
-   <span data-ttu-id="4a5bc-116">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="4a5bc-116">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="4a5bc-117">Vorteile eines eindeutigen Indexes</span><span class="sxs-lookup"><span data-stu-id="4a5bc-117">Benefits of a Unique Index</span></span>](#Benefits)  
  
     [<span data-ttu-id="4a5bc-118">Typische Implementierungen</span><span class="sxs-lookup"><span data-stu-id="4a5bc-118">Typical Implementations</span></span>](#Implementations)  
  
     [<span data-ttu-id="4a5bc-119">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="4a5bc-119">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="4a5bc-120">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="4a5bc-120">Security</span></span>](#Security)  
  
-   <span data-ttu-id="4a5bc-121">**So erstellen Sie einen eindeutigen Index auf einer Tabelle mithilfe von:**</span><span class="sxs-lookup"><span data-stu-id="4a5bc-121">**To create a unique index on a table, using:**</span></span>  
  
     [<span data-ttu-id="4a5bc-122">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4a5bc-122">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="4a5bc-123">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4a5bc-123">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4a5bc-124">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="4a5bc-124">Before You Begin</span></span>  
  
###  <a name="benefits-of-a-unique-index"></a><a name="Benefits"></a> <span data-ttu-id="4a5bc-125">Vorteile eines eindeutigen Indexes</span><span class="sxs-lookup"><span data-stu-id="4a5bc-125">Benefits of a Unique Index</span></span>  
  
-   <span data-ttu-id="4a5bc-126">Eindeutige Indizes für mehrere Spalten stellen sicher, dass jede Kombination der Werte in der indizierten Spalte eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="4a5bc-126">Multicolumn unique indexes guarantee that each combination of values in the index key is unique.</span></span> <span data-ttu-id="4a5bc-127">Wenn z. B. ein eindeutiger Index für eine Kombination der Spalten **LastName**, **FirstName**und **MiddleName** erstellt wird, können keine zwei Zeilen in der Tabelle dieselbe Kombination der Werte in diesen Spalten aufweisen.</span><span class="sxs-lookup"><span data-stu-id="4a5bc-127">For example, if a unique index is created on a combination of **LastName**, **FirstName**, and **MiddleName** columns, no two rows in the table could have the same combination of values for these columns.</span></span>  
  
-   <span data-ttu-id="4a5bc-128">Unter der Voraussetzung, dass die Daten in jeder Spalte eindeutig sind, können Sie einen eindeutigen gruppierten Index und mehrere eindeutige nicht gruppierte Indizes in derselben Tabelle erstellen.</span><span class="sxs-lookup"><span data-stu-id="4a5bc-128">Provided that the data in each column is unique, you can create both a unique clustered index and multiple unique nonclustered indexes on the same table.</span></span>  
  
-   <span data-ttu-id="4a5bc-129">Eindeutige Indizes sichern die Datenintegrität der definierten Spalten.</span><span class="sxs-lookup"><span data-stu-id="4a5bc-129">Unique indexes ensure the data integrity of the defined columns.</span></span>  
  
-   <span data-ttu-id="4a5bc-130">Eindeutige Indizes stellen weitere hilfreiche Informationen für den Abfrageoptimierer bereit, der effizientere Ausführungspläne erstellen kann.</span><span class="sxs-lookup"><span data-stu-id="4a5bc-130">Unique indexes provide additional information helpful to the query optimizer that can produce more efficient execution plans.</span></span>  
  
###  <a name="typical-implementations"></a><a name="Implementations"></a> <span data-ttu-id="4a5bc-131">Typische Implementierungen</span><span class="sxs-lookup"><span data-stu-id="4a5bc-131">Typical Implementations</span></span>  
 <span data-ttu-id="4a5bc-132">Eindeutige Indizes werden auf folgende Weise implementiert:</span><span class="sxs-lookup"><span data-stu-id="4a5bc-132">Unique indexes are implemented in the following ways:</span></span>  
  
-   <span data-ttu-id="4a5bc-133">**PRIMARY KEY- oder UNIQUE-Einschränkung**</span><span class="sxs-lookup"><span data-stu-id="4a5bc-133">**PRIMARY KEY or UNIQUE constraint**</span></span>  
  
     <span data-ttu-id="4a5bc-134">Wenn Sie eine PRIMARY KEY-Einschränkung erstellen, wird automatisch ein eindeutiger gruppierter Index für die Spalte(n) erstellt, wenn noch kein gruppierter Index für die Tabelle vorhanden ist und Sie keinen eindeutigen nicht gruppierten Index angeben.</span><span class="sxs-lookup"><span data-stu-id="4a5bc-134">When you create a PRIMARY KEY constraint, a unique clustered index on the column or columns is automatically created if a clustered index on the table does not already exist and you do not specify a unique nonclustered index.</span></span> <span data-ttu-id="4a5bc-135">Die Primärschlüsselspalte darf keine NULL-Werte zulassen.</span><span class="sxs-lookup"><span data-stu-id="4a5bc-135">The primary key column cannot allow NULL values.</span></span>  
  
     <span data-ttu-id="4a5bc-136">Wenn Sie eine UNIQUE-Einschränkung erstellen, wird ein eindeutiger nicht gruppierter Index erstellt, um standardmäßig eine UNIQUE-Einschränkung zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="4a5bc-136">When you create a UNIQUE constraint, a unique nonclustered index is created to enforce a UNIQUE constraint by default.</span></span> <span data-ttu-id="4a5bc-137">Sie können einen eindeutigen gruppierten Index angeben, wenn noch kein gruppierter Index für die Tabelle vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="4a5bc-137">You can specify a unique clustered index if a clustered index on the table does not already exist.</span></span>  
  
     <span data-ttu-id="4a5bc-138">Weitere Informationen finden Sie unter [Unique Constraints and Check Constraints](../tables/unique-constraints-and-check-constraints.md) und [Primary and Foreign Key Constraints](../tables/primary-and-foreign-key-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="4a5bc-138">For more information, see [Unique Constraints and Check Constraints](../tables/unique-constraints-and-check-constraints.md) and [Primary and Foreign Key Constraints](../tables/primary-and-foreign-key-constraints.md).</span></span>  
  
-   <span data-ttu-id="4a5bc-139">**Index unabhängig von einer Einschränkung**</span><span class="sxs-lookup"><span data-stu-id="4a5bc-139">**Index independent of a constraint**</span></span>  
  
     <span data-ttu-id="4a5bc-140">Es können mehrere eindeutige nicht gruppierte Indizes für eine Tabelle definiert werden.</span><span class="sxs-lookup"><span data-stu-id="4a5bc-140">Multiple unique nonclustered indexes can be defined on a table.</span></span>  
  
     <span data-ttu-id="4a5bc-141">Weitere Informationen finden Sie unter [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4a5bc-141">For more information, see [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span></span>  
  
-   <span data-ttu-id="4a5bc-142">**Indizierte Sicht**</span><span class="sxs-lookup"><span data-stu-id="4a5bc-142">**Indexed view**</span></span>  
  
     <span data-ttu-id="4a5bc-143">Zum Erstellen einer indizierten Sicht wird ein eindeutiger gruppierter Index für mindestens eine Spalte der Sicht definiert.</span><span class="sxs-lookup"><span data-stu-id="4a5bc-143">To create an indexed view, a unique clustered index is defined on one or more view columns.</span></span> <span data-ttu-id="4a5bc-144">Diese Sicht wird ausgeführt und das Resultset auf der Blattebene des Indexes gespeichert, so wie auch Tabellendaten in einem gruppierten Index gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="4a5bc-144">The view is executed and the result set is stored in the leaf level of the index in the same way table data is stored in a clustered index.</span></span> <span data-ttu-id="4a5bc-145">Weitere Informationen finden Sie unter [Erstellen von indizierten Sichten](../views/views.md).</span><span class="sxs-lookup"><span data-stu-id="4a5bc-145">For more information, see [Create Indexed Views](../views/views.md).</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="4a5bc-146">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="4a5bc-146">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="4a5bc-147">Ein eindeutiger Index, die UNIQUE-Einschränkung oder die PRIMARY KEY-Einschränkung kann nicht erstellt werden, wenn in den Daten doppelte Schlüsselwerte vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="4a5bc-147">A unique index, UNIQUE constraint, or PRIMARY KEY constraint cannot be created if duplicate key values exist in the data.</span></span>  
  
-   <span data-ttu-id="4a5bc-148">Ein eindeutiger, nicht gruppierter Index kann eingeschlossene Nichtschlüsselspalten enthalten.</span><span class="sxs-lookup"><span data-stu-id="4a5bc-148">A unique nonclustered index can contain included nonkey columns.</span></span> <span data-ttu-id="4a5bc-149">Weitere Informationen finden Sie unter [Create Indexes with Included Columns](create-indexes-with-included-columns.md).</span><span class="sxs-lookup"><span data-stu-id="4a5bc-149">For more information, see [Create Indexes with Included Columns](create-indexes-with-included-columns.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4a5bc-150">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="4a5bc-150">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4a5bc-151">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="4a5bc-151">Permissions</span></span>  
 <span data-ttu-id="4a5bc-152">Erfordert die ALTER-Berechtigung in der Tabelle oder Sicht.</span><span class="sxs-lookup"><span data-stu-id="4a5bc-152">Requires ALTER permission on the table or view.</span></span> <span data-ttu-id="4a5bc-153">Der Benutzer muss ein Mitglied der festen Serverrolle **sysadmin** bzw. der festen Datenbankrollen **db_ddladmin** und **db_owner** sein.</span><span class="sxs-lookup"><span data-stu-id="4a5bc-153">User must be a member of the **sysadmin** fixed server role or the **db_ddladmin** and **db_owner** fixed database roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4a5bc-154">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4a5bc-154">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-unique-index-by-using-the-table-designer"></a><span data-ttu-id="4a5bc-155">So erstellen Sie einen eindeutigen Index mit dem Tabellen-Designer</span><span class="sxs-lookup"><span data-stu-id="4a5bc-155">To create a unique index by using the Table Designer</span></span>  
  
1.  <span data-ttu-id="4a5bc-156">Erweitern Sie im Objekt-Explorer die Datenbank mit der Tabelle, für die Sie einen eindeutigen Index erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="4a5bc-156">In Object Explorer, expand the database that contains the table on which you want to create a unique index.</span></span>  
  
2.  <span data-ttu-id="4a5bc-157">Erweitern Sie den Ordner **Tabellen** .</span><span class="sxs-lookup"><span data-stu-id="4a5bc-157">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="4a5bc-158">Klicken Sie mit der rechten Maustaste auf die Tabelle, in der Sie einen eindeutigen Index erstellen möchten, und wählen Sie **Entwurf**aus.</span><span class="sxs-lookup"><span data-stu-id="4a5bc-158">Right-click the table on which you want to create a unique index and select **Design**.</span></span>  
  
4.  <span data-ttu-id="4a5bc-159">Wählen Sie im Menü **Tabellen-Designer** **Indizes/Schlüssel**aus.</span><span class="sxs-lookup"><span data-stu-id="4a5bc-159">On the **Table Designer** menu, select **Indexes/Keys**.</span></span>  
  
5.  <span data-ttu-id="4a5bc-160">Klicken Sie im Dialogfeld **Indizes/Schlüssel** auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="4a5bc-160">In the **Indexes/Keys** dialog box, click **Add**.</span></span>  
  
6.  <span data-ttu-id="4a5bc-161">Wählen Sie im Textfeld **Ausgewählter Primärschlüssel/eindeutiger Schlüssel oder Index** den neuen Index aus.</span><span class="sxs-lookup"><span data-stu-id="4a5bc-161">Select the new index in the **Selected Primary/Unique Key or Index** text box.</span></span>  
  
7.  <span data-ttu-id="4a5bc-162">Wählen Sie im Hauptraster unter **(Allgemein)** **Typ** aus, und wählen Sie dann **Index** aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="4a5bc-162">In the main grid, under **(General)**, select **Type** and then choose **Index** from the list.</span></span>  
  
8.  <span data-ttu-id="4a5bc-163">Wählen Sie **Spalten** aus, und klicken Sie dann auf die Auslassungspunkte **(...)** .</span><span class="sxs-lookup"><span data-stu-id="4a5bc-163">Select **Columns**, and then click the ellipsis **(...)**.</span></span>  
  
9. <span data-ttu-id="4a5bc-164">Wählen Sie im Dialogfeld **Indexspalten** unter **Spaltenname**die Spalten aus, die Sie indizieren möchten.</span><span class="sxs-lookup"><span data-stu-id="4a5bc-164">In the **Index Columns** dialog box, under **Column Name**, select the columns you want to index.</span></span> <span data-ttu-id="4a5bc-165">Sie können bis zu 16 Spalten auswählen.</span><span class="sxs-lookup"><span data-stu-id="4a5bc-165">You can select up to 16 columns.</span></span> <span data-ttu-id="4a5bc-166">Um optimale Ergebnisse zu gewährleisten, sollten Sie für jeden Index höchstens zwei Spalten auswählen.</span><span class="sxs-lookup"><span data-stu-id="4a5bc-166">For optimal performance, select only one or two columns per index.</span></span> <span data-ttu-id="4a5bc-167">Für jede ausgewählte Spalte können Sie festlegen, ob die darin enthaltenen Werte über den Index in aufsteigender oder absteigender Reihenfolge geordnet werden.</span><span class="sxs-lookup"><span data-stu-id="4a5bc-167">For each column you select, indicate whether the index arranges values of this column in ascending or descending order.</span></span>  
  
10. <span data-ttu-id="4a5bc-168">Wenn alle Spalten für den Index ausgewählt sind, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="4a5bc-168">When all columns for the index are selected, click **OK**.</span></span>  
  
11. <span data-ttu-id="4a5bc-169">Wählen Sie im Raster unter **(Allgemein)** **Ist eindeutig** aus, und wählen Sie anschließend **Ja** aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="4a5bc-169">In the grid, under **(General)**, select **Is Unique** and then choose **Yes** from the list.</span></span>  
  
12. <span data-ttu-id="4a5bc-170">Optional: wählen Sie im Hauptraster unter **Tabellen-Designer** **Doppelte Schlüssel ignorieren** aus, und wählen Sie dann **Ja** aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="4a5bc-170">Optional: In the main grid, under **Table Designer**, select **Ignore Duplicate Keys** and then choose **Yes** from the list.</span></span> <span data-ttu-id="4a5bc-171">Auf diese Weise ignorieren Sie Versuche, Daten hinzuzufügen, die im eindeutigen Index einen doppelten Schlüssel erstellen würden.</span><span class="sxs-lookup"><span data-stu-id="4a5bc-171">Do this if you want to ignore attempts to add data that would create a duplicate key in the unique index.</span></span>  
  
13. <span data-ttu-id="4a5bc-172">Klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="4a5bc-172">Click **Close**.</span></span>  
  
14. <span data-ttu-id="4a5bc-173">Klicken Sie im Menü **Datei** auf **Save**_table_name_speichern.</span><span class="sxs-lookup"><span data-stu-id="4a5bc-173">On the **File** menu, click **Save**_table_name_.</span></span>  
  
#### <a name="create-a-unique-index-by-using-object-explorer"></a><span data-ttu-id="4a5bc-174">Erstellen eines eindeutigen Indexes mit dem Objekt-Explorer</span><span class="sxs-lookup"><span data-stu-id="4a5bc-174">Create a unique index by using Object Explorer</span></span>  
  
1.  <span data-ttu-id="4a5bc-175">Erweitern Sie im Objekt-Explorer die Datenbank mit der Tabelle, für die Sie einen eindeutigen Index erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="4a5bc-175">In Object Explorer, expand the database that contains the table on which you want to create a unique index.</span></span>  
  
2.  <span data-ttu-id="4a5bc-176">Erweitern Sie den Ordner **Tabellen** .</span><span class="sxs-lookup"><span data-stu-id="4a5bc-176">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="4a5bc-177">Erweitern Sie die Tabelle, für die Sie einen eindeutigen Index erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="4a5bc-177">Expand the table on which you want to create a unique index.</span></span>  
  
4.  <span data-ttu-id="4a5bc-178">Klicken Sie mit der rechten Maustaste auf den Ordner **Indizes**, zeigen Sie auf **Neuer Index**, und wählen Sie **Nicht gruppierter Index...** aus.</span><span class="sxs-lookup"><span data-stu-id="4a5bc-178">Right-click the **Indexes** folder, point to **New Index**, and select **Non-Clustered Index...**.</span></span>  
  
5.  <span data-ttu-id="4a5bc-179">Geben Sie in das Dialogfeld **Neuer Index** auf der Seite **Allgemein** den Namen des neuen Indexes in das Feld **Indexname** ein.</span><span class="sxs-lookup"><span data-stu-id="4a5bc-179">In the **New Index** dialog box, on the **General** page, enter the name of the new index in the **Index name** box.</span></span>  
  
6.  <span data-ttu-id="4a5bc-180">Aktivieren Sie das Kontrollkästchen **Eindeutig** .</span><span class="sxs-lookup"><span data-stu-id="4a5bc-180">Select the **Unique** check box.</span></span>  
  
7.  <span data-ttu-id="4a5bc-181">Klicken Sie unter **Indexschlüsselspalten** auf **Hinzufügen…** .</span><span class="sxs-lookup"><span data-stu-id="4a5bc-181">Under **Index key columns**, click **Add...**.</span></span>  
  
8.  <span data-ttu-id="4a5bc-182">Aktivieren Sie im Dialogfeld **Spalten auswählen aus**_table_name_ das Kontrollkästchen bzw. die Kontrollkästchen der Tabellenspalte oder der Spalten, die dem eindeutigen Index hinzugefügt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="4a5bc-182">In the **Select Columns from**_table_name_ dialog box, select the check box or check boxes of the table column or columns to be added to the unique index.</span></span>  
  
9. <span data-ttu-id="4a5bc-183">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="4a5bc-183">Click **OK**.</span></span>  
  
10. <span data-ttu-id="4a5bc-184">Klicken Sie im Dialogfeld **Neuer Index** auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="4a5bc-184">In the **New Index** dialog box, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4a5bc-185">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4a5bc-185">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-unique-index-on-a-table"></a><span data-ttu-id="4a5bc-186">So erstellen Sie einen eindeutigen Index auf einer Tabelle</span><span class="sxs-lookup"><span data-stu-id="4a5bc-186">To create a unique index on a table</span></span>  
  
1.  <span data-ttu-id="4a5bc-187">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="4a5bc-187">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4a5bc-188">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="4a5bc-188">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4a5bc-189">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="4a5bc-189">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Find an existing index named AK_UnitMeasure_Name and delete it if found  
    IF EXISTS (SELECT name from sys.indexes  
               WHERE name = N'AK_UnitMeasure_Name')   
       DROP INDEX AK_UnitMeasure_Name ON Production.UnitMeasure;   
    GO  
    -- Create a unique index called AK_UnitMeasure_Name  
    -- on the Production.UnitMeasure table using the Name column.  
    CREATE UNIQUE INDEX AK_UnitMeasure_Name   
       ON Production.UnitMeasure (Name);   
    GO  
    ```  
  
 <span data-ttu-id="4a5bc-190">Weitere Informationen finden Sie unter [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4a5bc-190">For more information, see [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span></span>  
  
  
