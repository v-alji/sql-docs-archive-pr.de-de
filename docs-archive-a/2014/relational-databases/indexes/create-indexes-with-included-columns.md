---
title: Erstellen von Indizes mit eingeschlossenen Spalten | Microsoft Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- index size [SQL Server]
- index keys [SQL Server]
- index columns [SQL Server]
- size [SQL Server], indexes
- key columns [SQL Server]
- included columns
- nonclustered indexes [SQL Server], included columns
- designing indexes [SQL Server], included columns
- nonkey columns
ms.assetid: d198648d-fea5-416d-9f30-f9d4aebbf4ec
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e5a464f9791ea635236069555647229bf1f0d79e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724630"
---
# <a name="create-indexes-with-included-columns"></a><span data-ttu-id="59e31-102">Erstellen von Indizes mit eingeschlossenen Spalten</span><span class="sxs-lookup"><span data-stu-id="59e31-102">Create Indexes with Included Columns</span></span>
  <span data-ttu-id="59e31-103">In diesem Thema wird beschrieben, wie eingeschlossene Spalten (oder Nichtschlüsselspalten) hinzugefügt werden, um die Funktionalität von nicht gruppierten Indizes in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="59e31-103">This topic describes how to add included (or nonkey) columns to extend the functionality of nonclustered indexes in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="59e31-104">Indem Sie Nichtschlüsselspalten einschließen, erstellen Sie nicht gruppierte Indizes, die eine größere Anzahl von Abfragen abdecken.</span><span class="sxs-lookup"><span data-stu-id="59e31-104">By including nonkey columns, you can create nonclustered indexes that cover more queries.</span></span> <span data-ttu-id="59e31-105">Dies ist der Fall, weil Nichtschlüsselspalten die folgenden Vorteile aufweisen:</span><span class="sxs-lookup"><span data-stu-id="59e31-105">This is because the nonkey columns have the following benefits:</span></span>  
  
-   <span data-ttu-id="59e31-106">Es kann sich um Datentypen handeln, die als Indexschlüsselspalten nicht zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="59e31-106">They can be data types not allowed as index key columns.</span></span>  
  
-   <span data-ttu-id="59e31-107">Sie werden von [!INCLUDE[ssDE](../../includes/ssde-md.md)] beim Berechnen der Indexschlüsselspalten oder Indexschlüsselgröße nicht berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="59e31-107">They are not considered by the [!INCLUDE[ssDE](../../includes/ssde-md.md)] when calculating the number of index key columns or index key size.</span></span>  
  
 <span data-ttu-id="59e31-108">Ein Index mit Nichtschlüsselspalten kann die Abfrageleistung erheblich steigern, wenn alle Spalten in der Abfrage in den Index als Schlüssel- oder Nichtschlüsselspalten eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="59e31-108">An index with nonkey columns can significantly improve query performance when all columns in the query are included in the index either as key or nonkey columns.</span></span> <span data-ttu-id="59e31-109">Leistungsvorteile werden erzielt, weil der Abfrageoptimierer alle Spaltenwerte im Index finden kann; auf Daten der Tabelle oder des gruppierten Indexes wird nicht zugegriffen, sodass als Ergebnis weniger Datenträger-E/A-Vorgänge auftreten.</span><span class="sxs-lookup"><span data-stu-id="59e31-109">Performance gains are achieved because the query optimizer can locate all the column values within the index; table or clustered index data is not accessed resulting in fewer disk I/O operations.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="59e31-110">Wenn ein Index alle Spalten enthält, auf die eine Abfrage verweist, wird dies normalerweise als *Abdecken der Abfrage*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="59e31-110">When an index contains all the columns referenced by a query it is typically referred to as *covering the query*.</span></span>  
  
 <span data-ttu-id="59e31-111">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="59e31-111">**In This Topic**</span></span>  
  
-   <span data-ttu-id="59e31-112">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="59e31-112">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="59e31-113">Entwurfs Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="59e31-113">Design Recommendations</span></span>](#DesignRecs)  
  
     [<span data-ttu-id="59e31-114">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="59e31-114">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="59e31-115">Security</span><span class="sxs-lookup"><span data-stu-id="59e31-115">Security</span></span>](#Security)  
  
-   <span data-ttu-id="59e31-116">**So erstellen Sie einen Index mit Nichtschlüsselspalten mit:**</span><span class="sxs-lookup"><span data-stu-id="59e31-116">**To create an index with nonkey columns, using:**</span></span>  
  
     [<span data-ttu-id="59e31-117">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="59e31-117">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="59e31-118">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="59e31-118">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="59e31-119">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="59e31-119">Before You Begin</span></span>  
  
###  <a name="design-recommendations"></a><a name="DesignRecs"></a> <span data-ttu-id="59e31-120">Entwurfsempfehlungen</span><span class="sxs-lookup"><span data-stu-id="59e31-120">Design Recommendations</span></span>  
  
-   <span data-ttu-id="59e31-121">Überarbeiten Sie nicht gruppierte Indizes mit großen Indexschlüsseln so, dass nur Spalten, die für Suchen und Suchvorgänge verwendet werden, Schlüsselspalten sind.</span><span class="sxs-lookup"><span data-stu-id="59e31-121">Redesign nonclustered indexes with a large index key size so that only columns used for searching and lookups are key columns.</span></span> <span data-ttu-id="59e31-122">Erklären Sie alle anderen Spalten, die die Abfrage abdecken, zu Nichtschlüsselspalten.</span><span class="sxs-lookup"><span data-stu-id="59e31-122">Make all other columns that cover the query into nonkey columns.</span></span> <span data-ttu-id="59e31-123">Auf diese Weise sind alle Spalten vorhanden, die zum Abdecken der Abfrage erforderlich sind, der Indexschlüssel selbst ist jedoch klein und effizient.</span><span class="sxs-lookup"><span data-stu-id="59e31-123">In this way, you will have all columns needed to cover the query, but the index key itself is small and efficient.</span></span>  
  
-   <span data-ttu-id="59e31-124">Schließen Sie Nichtschlüsselspalten in einen nicht gruppierten Index ein, damit die Größenbegrenzungen des aktuellen Indexes von maximal 16 Schlüsselspalten und einer maximalen Größe des Indexschlüssels von 900 Byte nicht überschritten werden.</span><span class="sxs-lookup"><span data-stu-id="59e31-124">Include nonkey columns in a nonclustered index to avoid exceeding the current index size limitations of a maximum of 16 key columns and a maximum index key size of 900 bytes.</span></span> <span data-ttu-id="59e31-125">Nichtschlüsselspalten werden von [!INCLUDE[ssDE](../../includes/ssde-md.md)] beim Berechnen der Indexschlüsselspalten oder Indexschlüsselgröße nicht berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="59e31-125">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] does not consider nonkey columns when calculating the number of index key columns or index key size.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="59e31-126">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="59e31-126">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="59e31-127">Nichtschlüsselspalten können nur für nicht gruppierte Indizes definiert werden.</span><span class="sxs-lookup"><span data-stu-id="59e31-127">Nonkey columns can only be defined on nonclustered indexes.</span></span>  
  
-   <span data-ttu-id="59e31-128">Alle Datentypen außer `text`, `ntext` und `image` können als Nichtschlüsselspalten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="59e31-128">All data types except `text`, `ntext`, and `image` can be used as nonkey columns.</span></span>  
  
-   <span data-ttu-id="59e31-129">Berechnete Spalten, die deterministisch und entweder präzise oder unpräzise sind, können als Nichtschlüsselspalten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="59e31-129">Computed columns that are deterministic and either precise or imprecise can be nonkey columns.</span></span> <span data-ttu-id="59e31-130">Weitere Informationen finden Sie unter [Indexes on Computed Columns](indexes-on-computed-columns.md).</span><span class="sxs-lookup"><span data-stu-id="59e31-130">For more information, see [Indexes on Computed Columns](indexes-on-computed-columns.md).</span></span>  
  
-   <span data-ttu-id="59e31-131">Berechnete Spalten, die aus den Datentypen `image`, `ntext` und `text` abgeleitet werden, können Nichtschlüsselspalten sein, wenn der Datentyp der berechneten Spalte als Nichtschlüssel-Indexspalte zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="59e31-131">Computed columns derived from `image`, `ntext`, and `text` data types can be nonkey columns as long as the computed column data type is allowed as a nonkey index column.</span></span>  
  
-   <span data-ttu-id="59e31-132">Nichtschlüsselspalten können nur aus einer Tabelle gelöscht werden, wenn der Index der Tabelle zuvor gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="59e31-132">Nonkey columns cannot be dropped from a table unless that table's index is dropped first.</span></span>  
  
-   <span data-ttu-id="59e31-133">Nichtschlüsselspalten können nur zum Ausführen der folgenden Aufgaben geändert werden:</span><span class="sxs-lookup"><span data-stu-id="59e31-133">Nonkey columns cannot be changed, except to do the following:</span></span>  
  
    -   <span data-ttu-id="59e31-134">Ändern der NULL-Zulässigkeit der Spalte von NOT NULL in NULL.</span><span class="sxs-lookup"><span data-stu-id="59e31-134">Change the nullability of the column from NOT NULL to NULL.</span></span>  
  
    -   <span data-ttu-id="59e31-135">Vergrößern der Länge von `varchar`-, `nvarchar`- oder `varbinary`-Spalten.</span><span class="sxs-lookup"><span data-stu-id="59e31-135">Increase the length of `varchar`, `nvarchar`, or `varbinary` columns.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="59e31-136">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="59e31-136">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="59e31-137">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="59e31-137">Permissions</span></span>  
 <span data-ttu-id="59e31-138">Erfordert die ALTER-Berechtigung in der Tabelle oder Sicht.</span><span class="sxs-lookup"><span data-stu-id="59e31-138">Requires ALTER permission on the table or view.</span></span> <span data-ttu-id="59e31-139">Der Benutzer muss ein Mitglied der festen Serverrolle **sysadmin** bzw. der festen Datenbankrollen **db_ddladmin** und **db_owner** sein.</span><span class="sxs-lookup"><span data-stu-id="59e31-139">User must be a member of the **sysadmin** fixed server role or the **db_ddladmin** and **db_owner** fixed database roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="59e31-140">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="59e31-140">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-an-index-with-nonkey-columns"></a><span data-ttu-id="59e31-141">So erstellen Sie einen Index mit Nichtschlüsselspalten</span><span class="sxs-lookup"><span data-stu-id="59e31-141">To create an index with nonkey columns</span></span>  
  
1.  <span data-ttu-id="59e31-142">Klicken Sie im Objekt-Explorer auf das Pluszeichen, um die Datenbank zu erweitern, die die Tabelle enthält, in der Sie einen Index mit Nichtschlüsselspalten erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="59e31-142">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to create an index with nonkey columns.</span></span>  
  
2.  <span data-ttu-id="59e31-143">Klicken Sie auf das Pluszeichen, um den Ordner **Tabellen** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="59e31-143">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="59e31-144">Klicken Sie auf das Pluszeichen, um die Tabelle zu erweitern, für die Sie einen Index mit Nichtschlüsselspalten erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="59e31-144">Click the plus sign to expand the table on which you want to create an index with nonkey columns.</span></span>  
  
4.  <span data-ttu-id="59e31-145">Klicken Sie mit der rechten Maustaste auf den Ordner **Indizes**, zeigen Sie auf **Neuer Index**, und wählen Sie **Nicht gruppierter Index...** aus.</span><span class="sxs-lookup"><span data-stu-id="59e31-145">Right-click the **Indexes** folder, point to **New Index**, and select **Non-Clustered Index...**.</span></span>  
  
5.  <span data-ttu-id="59e31-146">Geben Sie in das Dialogfeld **Neuer Index** auf der Seite **Allgemein** den Namen des neuen Indexes in das Feld **Indexname** ein.</span><span class="sxs-lookup"><span data-stu-id="59e31-146">In the **New Index** dialog box, on the **General** page, enter the name of the new index in the **Index name** box.</span></span>  
  
6.  <span data-ttu-id="59e31-147">Klicken Sie in der Registerkarte **Indexschlüsselspalten** auf **Hinzufügen…** .</span><span class="sxs-lookup"><span data-stu-id="59e31-147">Under the **Index key columns** tab, click **Add...**.</span></span>  
  
7.  <span data-ttu-id="59e31-148">Aktivieren Sie im Dialogfeld **Spalten auswählen aus**_table_name_ das Kontrollkästchen bzw. die Kontrollkästchen der Tabellenspalte oder der Spalten, die dem Index hinzugefügt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="59e31-148">In the **Select Columns from**_table_name_ dialog box, select the check box or check boxes of the table column or columns to be added to the index.</span></span>  
  
8.  <span data-ttu-id="59e31-149">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="59e31-149">Click **OK**.</span></span>  
  
9. <span data-ttu-id="59e31-150">Klicken Sie auf der Registerkarte **Eingeschlossene Spalten** auf **Hinzufügen...** .</span><span class="sxs-lookup"><span data-stu-id="59e31-150">Under the **Included columns** tab, click **Add...**.</span></span>  
  
10. <span data-ttu-id="59e31-151">Aktivieren Sie im Dialogfeld **Spalten auswählen aus**_table_name_ das Kontrollkästchen oder die Kontrollkästchen der Tabellen Spalten, die dem Index als nicht Schlüssel Spalten hinzugefügt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="59e31-151">In the **Select Columns from**_table_name_ dialog box, select the check box or check boxes of the table column or columns to be added to the index as nonkey columns.</span></span>  
  
11. <span data-ttu-id="59e31-152">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="59e31-152">Click **OK**.</span></span>  
  
12. <span data-ttu-id="59e31-153">Klicken Sie im Dialogfeld **Neuer Index** auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="59e31-153">In the **New Index** dialog box, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="59e31-154">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="59e31-154">Using Transact-SQL</span></span>  
  
#### <a name="to-create-an-index-with-nonkey-columns"></a><span data-ttu-id="59e31-155">So erstellen Sie einen Index mit Nichtschlüsselspalten</span><span class="sxs-lookup"><span data-stu-id="59e31-155">To create an index with nonkey columns</span></span>  
  
1.  <span data-ttu-id="59e31-156">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="59e31-156">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="59e31-157">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="59e31-157">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="59e31-158">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="59e31-158">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Creates a nonclustered index on the Person.Address table with four included (nonkey) columns.   
    -- index key column is PostalCode and the nonkey columns are  
    -- AddressLine1, AddressLine2, City, and StateProvinceID.  
    CREATE NONCLUSTERED INDEX IX_Address_PostalCode  
    ON Person.Address (PostalCode)  
    INCLUDE (AddressLine1, AddressLine2, City, StateProvinceID);  
    GO  
    ```  
  
 <span data-ttu-id="59e31-159">Weitere Informationen finden Sie unter [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="59e31-159">For more information, see [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span></span>  
  
  
