---
title: Angeben des Füllfaktors für einen Index | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- fill factor [SQL Server]
- page splits [SQL Server]
ms.assetid: 237a577e-b42b-4adb-90cf-aa7fb174f3ab
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ac54f2b22de55ed74c4635ec0f86d008c7624a42
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723841"
---
# <a name="specify-fill-factor-for-an-index"></a><span data-ttu-id="d58fb-102">Angeben des Füllfaktors für einen Index</span><span class="sxs-lookup"><span data-stu-id="d58fb-102">Specify Fill Factor for an Index</span></span>
  <span data-ttu-id="d58fb-103">In diesem Thema wird beschrieben, was ein Füllfaktor ist und wie ein Füllfaktorwert in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] für einen Index mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="d58fb-103">This topic describes what fill factor is and how to specify a fill factor value on an index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="d58fb-104">Die Füllfaktoroption wird zur erweiterten Leistungsoptimierung beim Speichern von Indexdaten bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="d58fb-104">The fill-factor option is provided for fine-tuning index data storage and performance.</span></span> <span data-ttu-id="d58fb-105">Wenn ein Index erstellt oder neu erstellt wird, bestimmt der Füllfaktorwert den prozentualen Speicherplatz, der auf jeder Blattebenenseite mit Daten gefüllt werden soll. Der Rest jeder Seite wird als freier Speicherplatz für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="d58fb-105">When an index is created or rebuilt, the fill-factor value determines the percentage of space on each leaf-level page to be filled with data, reserving the remainder on each page as free space for future growth.</span></span> <span data-ttu-id="d58fb-106">Wenn Sie beispielsweise einen Füllfaktorwert von 80 angeben, bedeutet dies, dass 20 Prozent jeder Seite auf der Blattebene leer gelassen werden, um Speicherplatz für zukünftige Indexerweiterungen bereitzustellen, während der zugrunde liegenden Tabelle Daten hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="d58fb-106">For example, specifying a fill-factor value of 80 means that 20 percent of each leaf-level page will be left empty, providing space for index expansion as data is added to the underlying table.</span></span> <span data-ttu-id="d58fb-107">Der freie Speicherplatz wird zwischen den Indexzeilen statt am Ende des Indexes reserviert.</span><span class="sxs-lookup"><span data-stu-id="d58fb-107">The empty space is reserved between the index rows rather than at the end of the index.</span></span>  
  
 <span data-ttu-id="d58fb-108">Der Wert des Füllfaktors ist ein Prozentwert von 1 bis 100, und der serverweite Standardwert ist 0, d. h., dass die Seiten auf Blattebene vollständig aufgefüllt werden.</span><span class="sxs-lookup"><span data-stu-id="d58fb-108">The fill-factor value is a percentage from 1 to 100, and the server-wide default is 0 which means that the leaf-level pages are filled to capacity.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d58fb-109">Die Füllfaktorwerte 0 und 100 sind in jeder Hinsicht identisch.</span><span class="sxs-lookup"><span data-stu-id="d58fb-109">Fill-factor values 0 and 100 are the same in all respects.</span></span>  
  
 <span data-ttu-id="d58fb-110">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="d58fb-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d58fb-111">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="d58fb-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="d58fb-112">Leistungsaspekte</span><span class="sxs-lookup"><span data-stu-id="d58fb-112">Performance Considerations</span></span>](#Performance)  
  
     [<span data-ttu-id="d58fb-113">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="d58fb-113">Security</span></span>](#Security)  
  
-   <span data-ttu-id="d58fb-114">**So geben Sie einen Füllfaktor für einen Index an mit:**</span><span class="sxs-lookup"><span data-stu-id="d58fb-114">**To specify a fill factor in an index, using:**</span></span>  
  
     [<span data-ttu-id="d58fb-115">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d58fb-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="d58fb-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d58fb-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d58fb-117">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="d58fb-117">Before You Begin</span></span>  
  
###  <a name="performance-considerations"></a><a name="Performance"></a> <span data-ttu-id="d58fb-118">Leistungsaspekte</span><span class="sxs-lookup"><span data-stu-id="d58fb-118">Performance Considerations</span></span>  
  
#### <a name="page-splits"></a><span data-ttu-id="d58fb-119">Seitenteilung</span><span class="sxs-lookup"><span data-stu-id="d58fb-119">Page Splits</span></span>  
 <span data-ttu-id="d58fb-120">Mit einem richtig ausgewählten Füllfaktor kann das Risiko von Seitenteilungen verringert werden, indem genug Speicherplatz für Indexerweiterungen bereitgestellt wird, während der dem Index zugrunde liegenden Tabelle Daten hinzugefügt werden. Wenn einer vollen Indexseite eine neue Zeile hinzugefügt wird, verschiebt [!INCLUDE[ssDE](../../includes/ssde-md.md)] ungefähr die Hälfte der Zeilen auf eine neue Seite, um Platz für die neue Zeile bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="d58fb-120">A correctly chosen fill-factor value can reduce potential page splits by providing enough space for index expansion as data is added to the underlying table.When a new row is added to a full index page, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] moves approximately half the rows to a new page to make room for the new row.</span></span> <span data-ttu-id="d58fb-121">Diese Neuorganisation wird auch Seitenteilung genannt.</span><span class="sxs-lookup"><span data-stu-id="d58fb-121">This reorganization is known as a page split.</span></span> <span data-ttu-id="d58fb-122">Eine Seitenteilung schafft Platz für neue Datensätze, beansprucht jedoch Zeit und Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="d58fb-122">A page split makes room for new records, but can take time to perform and is a resource intensive operation.</span></span> <span data-ttu-id="d58fb-123">Seitenteilungen können auch Fragmentierungen verursachen, die zu vermehrten E/A-Vorgängen führen.</span><span class="sxs-lookup"><span data-stu-id="d58fb-123">Also, it can cause fragmentation that causes increased I/O operations.</span></span> <span data-ttu-id="d58fb-124">Bei häufigen Seitenteilungen kann der Index neu erstellt und dabei ein neuer oder bereits vorhandener Füllfaktor verwendet werden, um die Daten neu zu verteilen.</span><span class="sxs-lookup"><span data-stu-id="d58fb-124">When frequent page splits occur, the index can be rebuilt by using a new or existing fill-factor value to redistribute the data.</span></span> <span data-ttu-id="d58fb-125">Weitere Informationen finden Sie unter [Neuorganisieren und Neuerstellen von Indizes](reorganize-and-rebuild-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="d58fb-125">For more information, see [Reorganize and Rebuild Indexes](reorganize-and-rebuild-indexes.md).</span></span>  
  
 <span data-ttu-id="d58fb-126">Ein niedriger Füllfaktor über 0 kann zwar beim Vergrößern des Indexes die Seitenteilung reduzieren; der Index erfordert dann jedoch mehr Speicherplatz, was die Leseleistung verringern kann.</span><span class="sxs-lookup"><span data-stu-id="d58fb-126">Although a low, nonzero fill-factor value may reduce the requirement to split pages as the index grows, the index will require more storage space and can decrease read performance.</span></span> <span data-ttu-id="d58fb-127">Sogar im Fall einer Anwendung, die sehr viele Einfügungen und Aktualisierungen vornimmt, treten Datenbanklesevorgänge in der Regel fünf- bis zehnmal häufiger auf als Schreibvorgänge in der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="d58fb-127">Even for an application oriented for many insert and update operations, the number of database reads typically outnumber database writes by a factor of 5 to 10.</span></span> <span data-ttu-id="d58fb-128">Aus diesem Grund kann das Ändern des Standardfüllfaktors die Leistung von Datenbanklesevorgängen in einem Umfang mindern, der umgekehrt proportional zur Füllfaktoreinstellung ist.</span><span class="sxs-lookup"><span data-stu-id="d58fb-128">Therefore, specifying a fill factor other than the default can decrease database read performance by an amount inversely proportional to the fill-factor setting.</span></span> <span data-ttu-id="d58fb-129">Ein Füllfaktorwert von 50 Prozent kann z. B. dazu führen, dass die Dauer von Datenbanklesevorgängen verdoppelt wird.</span><span class="sxs-lookup"><span data-stu-id="d58fb-129">For example, a fill-factor value of 50 can cause database read performance to decrease by two times.</span></span> <span data-ttu-id="d58fb-130">Die Leseleistung verringert sich, weil der Index eine größere Anzahl an Seiten enthält und daher die zum Abrufen der Daten erforderlichen Datenträger-E/A-Vorgänge zunehmen.</span><span class="sxs-lookup"><span data-stu-id="d58fb-130">Read performance is decreased because the index contains more pages, therefore increasing the disk IO operations required to retrieve the data.</span></span>  
  
#### <a name="adding-data-to-the-end-of-the-table"></a><span data-ttu-id="d58fb-131">Hinzufügen von Daten zum Tabellenende</span><span class="sxs-lookup"><span data-stu-id="d58fb-131">Adding Data to the End of the Table</span></span>  
 <span data-ttu-id="d58fb-132">Ein Füllfaktor ungleich 0 oder 100 kann zur Leistungsverbesserung beitragen, wenn die neuen Daten gleichmäßig in der Tabelle verteilt werden.</span><span class="sxs-lookup"><span data-stu-id="d58fb-132">A nonzero fill factor other than 0 or 100 can be good for performance if the new data is evenly distributed throughout the table.</span></span> <span data-ttu-id="d58fb-133">Wenn jedoch alle Daten am Tabellenende hinzugefügt werden, wird der freie Speicherplatz auf den Indexseiten nicht aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="d58fb-133">However, if all the data is added to the end of the table, the empty space in the index pages will not be filled.</span></span> <span data-ttu-id="d58fb-134">Wenn die Indexschlüsselspalte z. B. eine IDENTITY-Spalte ist, wird der Schlüssel für neue Zeilen stets erhöht, und die Indexzeilen werden am Ende des Indexes logisch hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="d58fb-134">For example, if the index key column is an IDENTITY column, the key for new rows is always increasing and the index rows are logically added to the end of the index.</span></span> <span data-ttu-id="d58fb-135">Wenn vorhandene Zeilen mit Daten aktualisiert werden, die die Größe der Zeilen verlängern, verwenden Sie einen Füllfaktor von weniger als 100.</span><span class="sxs-lookup"><span data-stu-id="d58fb-135">If existing rows will be updated with data that lengthens the size of the rows, use a fill factor of less than 100.</span></span> <span data-ttu-id="d58fb-136">Durch die zusätzlichen Bytes auf jeder Seite werden die Seitenteilungen minimiert, die durch die zusätzliche Länge der Zeilen verursach werden.</span><span class="sxs-lookup"><span data-stu-id="d58fb-136">The extra bytes on each page will help to minimize page splits caused by extra length in the rows.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d58fb-137">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="d58fb-137">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d58fb-138">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="d58fb-138">Permissions</span></span>  
 <span data-ttu-id="d58fb-139">Erfordert die ALTER-Berechtigung in der Tabelle oder Sicht.</span><span class="sxs-lookup"><span data-stu-id="d58fb-139">Requires ALTER permission on the table or view.</span></span> <span data-ttu-id="d58fb-140">Der Benutzer muss ein Mitglied der festen Serverrolle **sysadmin** bzw. der festen Datenbankrollen **db_ddladmin** und **db_owner** sein.</span><span class="sxs-lookup"><span data-stu-id="d58fb-140">User must be a member of the **sysadmin** fixed server role or the **db_ddladmin** and **db_owner** fixed database roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d58fb-141">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d58fb-141">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-specify-a-fill-factor-by-using-table-designer"></a><span data-ttu-id="d58fb-142">So geben Sie einen Füllfaktor mit dem Tabellen-Designer an</span><span class="sxs-lookup"><span data-stu-id="d58fb-142">To specify a fill factor by using Table Designer</span></span>  
  
1.  <span data-ttu-id="d58fb-143">Klicken Sie im Objekt-Explorer auf das Pluszeichen, um die Datenbank mit der Tabelle zu erweitern, für die Sie den Füllfaktor eines Indexes angeben möchten.</span><span class="sxs-lookup"><span data-stu-id="d58fb-143">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to specify an index's fill factor.</span></span>  
  
2.  <span data-ttu-id="d58fb-144">Klicken Sie auf das Pluszeichen, um den Ordner **Tabellen** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="d58fb-144">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="d58fb-145">Klicken Sie mit der rechten Maustaste auf die Tabelle, für die Sie den Füllfaktor eines Indexes angeben möchten, und wählen Sie die Option **Entwurf** aus.</span><span class="sxs-lookup"><span data-stu-id="d58fb-145">Right-click the table on which you want to specify an index's fill factor and select **Design**.</span></span>  
  
4.  <span data-ttu-id="d58fb-146">Klicken Sie im Menü **Tabellen-Designer** auf **Indizes/Schlüssel**.</span><span class="sxs-lookup"><span data-stu-id="d58fb-146">On the **Table Designer** menu, click **Indexes/Keys**.</span></span>  
  
5.  <span data-ttu-id="d58fb-147">Wählen Sie den Index mit dem Füllfaktor aus, den Sie angeben möchten.</span><span class="sxs-lookup"><span data-stu-id="d58fb-147">Select the index with the fill factor that you want to specify.</span></span>  
  
6.  <span data-ttu-id="d58fb-148">Erweitern Sie **Füllspezifikation**, wählen Sie die Zeile **Füllfaktor** aus, und geben Sie den gewünschten Füllfaktor in die Zeile ein.</span><span class="sxs-lookup"><span data-stu-id="d58fb-148">Expand **Fill Specification**, select the **Fill Factor** row and enter the fill factor you want in the row.</span></span>  
  
7.  <span data-ttu-id="d58fb-149">Klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="d58fb-149">Click **Close**.</span></span>  
  
8.  <span data-ttu-id="d58fb-150">Klicken Sie im Menü **Datei** auf **Save**_Tabellenname_.</span><span class="sxs-lookup"><span data-stu-id="d58fb-150">On the **File** menu, select **Save**_table_name_.</span></span>  
  
#### <a name="to-specify-a-fill-factor-in-an-index-by-using-object-explorer"></a><span data-ttu-id="d58fb-151">So geben Sie einen Füllfaktor in einem Index mit dem Objekt-Explorer an</span><span class="sxs-lookup"><span data-stu-id="d58fb-151">To specify a fill factor in an index by using Object Explorer</span></span>  
  
1.  <span data-ttu-id="d58fb-152">Klicken Sie im Objekt-Explorer auf das Pluszeichen, um die Datenbank mit der Tabelle zu erweitern, für die Sie den Füllfaktor eines Indexes angeben möchten.</span><span class="sxs-lookup"><span data-stu-id="d58fb-152">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to specify an index's fill factor.</span></span>  
  
2.  <span data-ttu-id="d58fb-153">Klicken Sie auf das Pluszeichen, um den Ordner **Tabellen** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="d58fb-153">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="d58fb-154">Klicken Sie auf das Pluszeichen, um die Tabelle zu erweitern, für die Sie den Füllfaktor eines Indexes angeben möchten.</span><span class="sxs-lookup"><span data-stu-id="d58fb-154">Click the plus sign to expand the table on which you want to specify an index's fill factor.</span></span>  
  
4.  <span data-ttu-id="d58fb-155">Klicken Sie auf das Pluszeichen, um den Ordner **Indizes** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="d58fb-155">Click the plus sign to expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="d58fb-156">Klicken Sie mit der rechten Maustaste auf den Index mit dem Füllfaktor, den Sie angeben möchten, und wählen Sie **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="d58fb-156">Right-click the index with the fill factor that you want to specify and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="d58fb-157">Wählen Sie unter **Seite auswählen**die Option **Optionen**aus.</span><span class="sxs-lookup"><span data-stu-id="d58fb-157">Under **Select a page**, select **Options**.</span></span>  
  
7.  <span data-ttu-id="d58fb-158">Geben Sie in der Zeile **Füllfaktor** den gewünschten Füllfaktor ein.</span><span class="sxs-lookup"><span data-stu-id="d58fb-158">In the **Fill factor** row, enter the fill factor that you want.</span></span>  
  
8.  <span data-ttu-id="d58fb-159">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="d58fb-159">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="d58fb-160">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d58fb-160">Using Transact-SQL</span></span>  
  
#### <a name="to-specify-a-fill-factor-in-an-existing-index"></a><span data-ttu-id="d58fb-161">So geben Sie einen Füllfaktor für einen vorhandenen Index an</span><span class="sxs-lookup"><span data-stu-id="d58fb-161">To specify a fill factor in an existing index</span></span>  
  
1.  <span data-ttu-id="d58fb-162">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="d58fb-162">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d58fb-163">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="d58fb-163">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d58fb-164">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="d58fb-164">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="d58fb-165">Im folgenden Beispiel wird ein vorhandener Index neu erstellt und der angegebene Füllfaktor während der Neuerstellung angewendet.</span><span class="sxs-lookup"><span data-stu-id="d58fb-165">The example rebuilds an existing index and applies the specified fill factor during the rebuild operation.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Rebuilds the IX_Employee_OrganizationLevel_OrganizationNode index   
    -- with a fill factor of 80 on the HumanResources.Employee table.  
  
    ALTER INDEX IX_Employee_OrganizationLevel_OrganizationNode ON HumanResources.Employee  
    REBUILD WITH (FILLFACTOR = 80);   
    GO  
    ```  
  
#### <a name="another-way-to-specify-a-fill-factor-in-an-index"></a><span data-ttu-id="d58fb-166">Alternative Möglichkeit zum Angeben eines Füllfaktors in einem Index</span><span class="sxs-lookup"><span data-stu-id="d58fb-166">Another way to specify a fill factor in an index</span></span>  
  
1.  <span data-ttu-id="d58fb-167">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="d58fb-167">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d58fb-168">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="d58fb-168">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d58fb-169">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="d58fb-169">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    /* Drops and re-creates the IX_Employee_OrganizationLevel_OrganizationNode index on the HumanResources.Employee table with a fill factor of 80.  
    */  
  
    CREATE INDEX IX_Employee_OrganizationLevel_OrganizationNode ON HumanResources.Employee  
       (OrganizationLevel, OrganizationNode)   
    WITH (DROP_EXISTING = ON, FILLFACTOR = 80);   
    GO  
    ```  
  
 <span data-ttu-id="d58fb-170">Weitere Informationen finden Sie unter [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d58fb-170">For more information, see [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
  
