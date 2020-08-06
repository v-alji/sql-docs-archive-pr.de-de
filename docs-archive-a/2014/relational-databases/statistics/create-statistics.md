---
title: Erstellen von Statistiken | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
f1_keywords:
- sql12.swb.statistics.propertis.f1
- sql12.swb.statistics.filter.f1
- sql12.swb.stat.properties.f1
- sql12.swb.stat.columns.f1
helpviewer_keywords:
- creating statistics
- statistics [SQL Server], creating
ms.assetid: 95a455fb-664d-4c95-851e-c6b62d7ebe04
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 230bd4d840c3d59dc1267dd6801754b68386cb32
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621418"
---
# <a name="create-statistics"></a><span data-ttu-id="861bb-102">Erstellen von Statistiken</span><span class="sxs-lookup"><span data-stu-id="861bb-102">Create Statistics</span></span>
  <span data-ttu-id="861bb-103">Sie können Abfrageoptimierungsstatistiken in einer oder mehreren Spalten einer Tabelle oder indizierten Sicht in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] erstellen, indem Sie [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]verwenden.</span><span class="sxs-lookup"><span data-stu-id="861bb-103">You can create query optimization statistics on one or more columns of a table or indexed view in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="861bb-104">Bei den meisten Abfragen generiert der Abfrageoptimierer automatisch die notwendigen Statistiken für einen hochwertigen Abfrageplan. In einigen Fällen müssen Sie weitere Statistiken erstellen.</span><span class="sxs-lookup"><span data-stu-id="861bb-104">For most queries, the query optimizer already generates the necessary statistics for a high-quality query plan; in a few cases, you need to create additional statistics.</span></span>  
  
 <span data-ttu-id="861bb-105">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="861bb-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="861bb-106">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="861bb-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="861bb-107">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="861bb-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="861bb-108">Security</span><span class="sxs-lookup"><span data-stu-id="861bb-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="861bb-109">**So erstellen Sie Statistiken mit:**</span><span class="sxs-lookup"><span data-stu-id="861bb-109">**To create statistics, using:**</span></span>  
  
     [<span data-ttu-id="861bb-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="861bb-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="861bb-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="861bb-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="861bb-112">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="861bb-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="861bb-113">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="861bb-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="861bb-114">Vergewissern Sie sich vor dem Erstellen von Statistiken mit der CREATE STATISTICS-Anweisung, dass auf Datenbankebene die AUTO_CREATE_STATISTICS-Option festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="861bb-114">Before creating statistics with the CREATE STATISTICS statement, verify that the AUTO_CREATE_STATISTICS option is set at the database level.</span></span> <span data-ttu-id="861bb-115">Dadurch wird sichergestellt, dass der Abfrageoptimierer weiterhin routinemäßig einspaltige Statistiken für Abfrageprädikatsspalten erstellt.</span><span class="sxs-lookup"><span data-stu-id="861bb-115">This will ensure that the query optimizer continues to routinely create single-column statistics for query predicate columns.</span></span>  
  
-   <span data-ttu-id="861bb-116">Sie können bis zu 32 Spalten pro Statistikobjekt auflisten.</span><span class="sxs-lookup"><span data-stu-id="861bb-116">You can list up to 32 columns per statistics object.</span></span>  
  
-   <span data-ttu-id="861bb-117">Sie können die Definition einer in einem Prädikat der gefilterten Statistik definierten Tabellenspalte nicht löschen, umbenennen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="861bb-117">You cannot drop, rename, or alter the definition of a table column that is defined in a filtered statistics predicate.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="861bb-118">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="861bb-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="861bb-119">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="861bb-119">Permissions</span></span>  
 <span data-ttu-id="861bb-120">Erfordert, dass der Benutzer der Besitzer der Tabelle oder indizierten Sicht oder ein Mitglied einer der folgenden Rollen ist: feste Serverrolle **sysadmin** , feste Datenbankrolle **db_owner** oder feste Datenbankrolle **db_ddladmin** .</span><span class="sxs-lookup"><span data-stu-id="861bb-120">Requires that the user be the table or indexed view owner, or a member of one of the following roles: **sysadmin** fixed server role, **db_owner** fixed database role, or the **db_ddladmin** fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="861bb-121">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="861bb-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-statistics"></a><span data-ttu-id="861bb-122">So erstellen Sie Statistiken</span><span class="sxs-lookup"><span data-stu-id="861bb-122">To create statistics</span></span>  
  
1.  <span data-ttu-id="861bb-123">Klicken Sie im **Objekt-Explorer**auf das Pluszeichen, um die Datenbank zu erweitern, in der Sie eine neue Statistik erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="861bb-123">In **Object Explorer**, click the plus sign to expand the database in which you want to create a new statistic.</span></span>  
  
2.  <span data-ttu-id="861bb-124">Klicken Sie auf das Pluszeichen, um den Ordner **Tabellen** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="861bb-124">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="861bb-125">Klicken Sie auf das Pluszeichen, um die Tabelle zu erweitern, in der Sie eine neue Statistik erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="861bb-125">Click the plus sign to expand the table in which you want to create a new statistic.</span></span>  
  
4.  <span data-ttu-id="861bb-126">Klicken Sie mit der rechten Maustaste auf den Ordner **Statistik**, und wählen Sie dann **New Statistics...** (Neue Statistiken…).</span><span class="sxs-lookup"><span data-stu-id="861bb-126">Right-click the **Statistics** folder and select **New Statistics...**.</span></span>  
  
     <span data-ttu-id="861bb-127">Die folgenden Eigenschaften werden auf der Seite **Allgemein** im Dialogfeld **neue Statistik für Tabelle**_table_name_ angezeigt.</span><span class="sxs-lookup"><span data-stu-id="861bb-127">The following properties show on the **General** page in the **New Statistics on Table**_table_name_ dialog box.</span></span>  
  
     <span data-ttu-id="861bb-128">**Tabellenname**</span><span class="sxs-lookup"><span data-stu-id="861bb-128">**Table Name**</span></span>  
     <span data-ttu-id="861bb-129">Zeigt den Namen der Tabelle an, die von den Statistiken beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="861bb-129">Displays the name of the table described by the statistics.</span></span>  
  
     <span data-ttu-id="861bb-130">**Statistikname**</span><span class="sxs-lookup"><span data-stu-id="861bb-130">**Statistics Name**</span></span>  
     <span data-ttu-id="861bb-131">Zeigt den Namen des Datenbankobjekts an, in dem die Statistiken gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="861bb-131">Displays the name of the database object where the statistics are stored.</span></span>  
  
     <span data-ttu-id="861bb-132">**Statistikspalten**</span><span class="sxs-lookup"><span data-stu-id="861bb-132">**Statistics Columns**</span></span>  
     <span data-ttu-id="861bb-133">Dieses Raster zeigt die von dieser Gruppe von Statistiken beschriebenen Spalten an.</span><span class="sxs-lookup"><span data-stu-id="861bb-133">This grid shows the columns described by this set of statistics.</span></span> <span data-ttu-id="861bb-134">Alle Werte im Raster sind schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="861bb-134">All values in the grid are read-only.</span></span>  
  
     <span data-ttu-id="861bb-135">**Name**</span><span class="sxs-lookup"><span data-stu-id="861bb-135">**Name**</span></span>  
     <span data-ttu-id="861bb-136">Zeigt den Namen der Spalte an, die von den Statistiken beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="861bb-136">Displays the name of the column described by the statistics.</span></span> <span data-ttu-id="861bb-137">Dabei kann es sich um eine einzelne Spalte oder eine Kombination aus Spalten in einer einzelnen Tabelle handeln.</span><span class="sxs-lookup"><span data-stu-id="861bb-137">This can be a single column or a combination of columns in a single table.</span></span>  
  
     <span data-ttu-id="861bb-138">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="861bb-138">**Data Type**</span></span>  
     <span data-ttu-id="861bb-139">Gibt den Datentyp der von den Statistiken beschriebenen Spalten an.</span><span class="sxs-lookup"><span data-stu-id="861bb-139">Indicates the data type of the columns described by the statistics.</span></span>  
  
     <span data-ttu-id="861bb-140">**Größe**</span><span class="sxs-lookup"><span data-stu-id="861bb-140">**Size**</span></span>  
     <span data-ttu-id="861bb-141">Zeigt jeweils die Größe des Datentyps für die einzelnen Spalten an.</span><span class="sxs-lookup"><span data-stu-id="861bb-141">Displays the size of the data type for each column.</span></span>  
  
     <span data-ttu-id="861bb-142">**Identität**</span><span class="sxs-lookup"><span data-stu-id="861bb-142">**Identity**</span></span>  
     <span data-ttu-id="861bb-143">Gibt eine Identitätsspalte an, wenn diese Option aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="861bb-143">Indicates an identity column when it is checked.</span></span>  
  
     <span data-ttu-id="861bb-144">**NULL-Werte zulassen**</span><span class="sxs-lookup"><span data-stu-id="861bb-144">**Allow Nulls**</span></span>  
     <span data-ttu-id="861bb-145">Gibt an, ob die Spalte NULL-Werte annimmt.</span><span class="sxs-lookup"><span data-stu-id="861bb-145">Indicates whether the column accepts NULL values.</span></span>  
  
     <span data-ttu-id="861bb-146">**Add (Hinzufügen)**</span><span class="sxs-lookup"><span data-stu-id="861bb-146">**Add**</span></span>  
     <span data-ttu-id="861bb-147">Fügt dem Statistikraster zusätzliche Spalten aus der Tabelle hinzu.</span><span class="sxs-lookup"><span data-stu-id="861bb-147">Add additional columns from the table to the statistics grid.</span></span>  
  
     <span data-ttu-id="861bb-148">**Remove**</span><span class="sxs-lookup"><span data-stu-id="861bb-148">**Remove**</span></span>  
     <span data-ttu-id="861bb-149">Entfernt die ausgewählte Spalte aus dem Statistikraster.</span><span class="sxs-lookup"><span data-stu-id="861bb-149">Remove the selected column from the statistics grid.</span></span>  
  
     <span data-ttu-id="861bb-150">**Nach oben**</span><span class="sxs-lookup"><span data-stu-id="861bb-150">**Move Up**</span></span>  
     <span data-ttu-id="861bb-151">Verschiebt die ausgewählte Spalte an eine frühere Position im Statistikraster.</span><span class="sxs-lookup"><span data-stu-id="861bb-151">Move the selected column to an earlier location in the statistics grid.</span></span> <span data-ttu-id="861bb-152">Die Position im Raster kann in erheblichem Maß die Eignung der Statistiken beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="861bb-152">The location in the grid can substantially impact the usefulness of the statistics.</span></span>  
  
     <span data-ttu-id="861bb-153">**Nach unten**</span><span class="sxs-lookup"><span data-stu-id="861bb-153">**Move Down**</span></span>  
     <span data-ttu-id="861bb-154">Verschiebt die ausgewählte Spalte an eine spätere Position im Statistikraster.</span><span class="sxs-lookup"><span data-stu-id="861bb-154">Move the selected column to a later location in the statistics grid.</span></span>  
  
     <span data-ttu-id="861bb-155">**Die Statistiken für diese Spalten wurden zuletzt aktualisiert:**</span><span class="sxs-lookup"><span data-stu-id="861bb-155">**Statistics for these columns were last updated:**</span></span>  
     <span data-ttu-id="861bb-156">Gibt das Alter von Statistiken an.</span><span class="sxs-lookup"><span data-stu-id="861bb-156">Indicates how old the statistics are.</span></span> <span data-ttu-id="861bb-157">Statistiken sind wertvoller, wenn Sie aktuell sind.</span><span class="sxs-lookup"><span data-stu-id="861bb-157">Statistics are more valuable when they are current.</span></span> <span data-ttu-id="861bb-158">Aktualisieren Sie Statistiken nach umfangreichen Änderungen an den Daten bzw. nach Hinzufügen atypischer Daten.</span><span class="sxs-lookup"><span data-stu-id="861bb-158">Update statistics after large changes to the data or after adding atypical data.</span></span> <span data-ttu-id="861bb-159">Statistiken für Tabellen mit konsistenter Verteilung der Daten müssen seltener aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="861bb-159">Statistics for tables that have a consistent distribution of data need to be updated less frequently.</span></span>  
  
     <span data-ttu-id="861bb-160">**Statistiken für diese Spalten aktualisieren**</span><span class="sxs-lookup"><span data-stu-id="861bb-160">**Update statistics for these columns**</span></span>  
     <span data-ttu-id="861bb-161">Aktivieren Sie diese Option, wenn die Statistiken beim Schließen des Dialogfelds aktualisiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="861bb-161">Check to update the statistics when the dialog box is closed.</span></span>  
  
     <span data-ttu-id="861bb-162">Die folgende Eigenschaft wird auf der Seite **Filter** im Dialogfeld **neue Statistik für Tabelle**_table_name_ angezeigt.</span><span class="sxs-lookup"><span data-stu-id="861bb-162">The following property shows on the **Filter** page in the **New Statistics on Table**_table_name_ dialog box.</span></span>  
  
     <span data-ttu-id="861bb-163">**Filterausdruck**</span><span class="sxs-lookup"><span data-stu-id="861bb-163">**Filter Expression**</span></span>  
     <span data-ttu-id="861bb-164">Definiert, welche Datenzeilen in die gefilterte Statistik eingeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="861bb-164">Defines which data rows to include in the filtered statistics.</span></span> <span data-ttu-id="861bb-165">Zum Beispiel, `Production.ProductSubcategoryID IN ( 1,2,3 )`</span><span class="sxs-lookup"><span data-stu-id="861bb-165">For example, `Production.ProductSubcategoryID IN ( 1,2,3 )`</span></span>  
  
5.  <span data-ttu-id="861bb-166">Klicken Sie im Dialogfeld **neue Statistik für Tabelle**_table_name_ auf der Seite **Allgemein** auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="861bb-166">In the **New Statistics on Table**_table_name_ dialog box, on the **General** page, click **Add**.</span></span>  
  
     <span data-ttu-id="861bb-167">Die folgenden Eigenschaften werden im Dialogfeld **Spalten auswählen** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="861bb-167">The following properties show in the **Select Columns** dialog box.</span></span> <span data-ttu-id="861bb-168">Diese Informationen sind schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="861bb-168">This information is read-only.</span></span>  
  
     <span data-ttu-id="861bb-169">**Name**</span><span class="sxs-lookup"><span data-stu-id="861bb-169">**Name**</span></span>  
     <span data-ttu-id="861bb-170">Zeigt den Namen der Spalte an, die von den Statistiken beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="861bb-170">Displays the name of the column described by the statistics.</span></span> <span data-ttu-id="861bb-171">Dabei kann es sich um eine einzelne Spalte oder eine Kombination aus Spalten in einer einzelnen Tabelle handeln.</span><span class="sxs-lookup"><span data-stu-id="861bb-171">This can be a single column or a combination of columns in a single table.</span></span>  
  
     <span data-ttu-id="861bb-172">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="861bb-172">**Data Type**</span></span>  
     <span data-ttu-id="861bb-173">Gibt den Datentyp der von den Statistiken beschriebenen Spalten an.</span><span class="sxs-lookup"><span data-stu-id="861bb-173">Indicates the data type of the columns described by the statistics.</span></span>  
  
     <span data-ttu-id="861bb-174">**Größe**</span><span class="sxs-lookup"><span data-stu-id="861bb-174">**Size**</span></span>  
     <span data-ttu-id="861bb-175">Zeigt jeweils die Größe des Datentyps für die einzelnen Spalten an.</span><span class="sxs-lookup"><span data-stu-id="861bb-175">Displays the size of the data type for each column.</span></span>  
  
     <span data-ttu-id="861bb-176">**Identität**</span><span class="sxs-lookup"><span data-stu-id="861bb-176">**Identity**</span></span>  
     <span data-ttu-id="861bb-177">Gibt eine Identitätsspalte an, wenn diese Option aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="861bb-177">Indicates an identity column when checked.</span></span>  
  
     <span data-ttu-id="861bb-178">**NULL-Werte zulassen**</span><span class="sxs-lookup"><span data-stu-id="861bb-178">**Allow NULLs**</span></span>  
     <span data-ttu-id="861bb-179">Gibt an, ob die Spalte NULL-Werte annimmt.</span><span class="sxs-lookup"><span data-stu-id="861bb-179">Indicates whether the column accepts NULL values.</span></span>  
  
6.  <span data-ttu-id="861bb-180">Aktivieren Sie im Dialogfeld **Spalten auswählen** das oder die Kontrollkästchen der einzelnen Spalten, für die Sie eine Statistik erstellen möchten, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="861bb-180">In the **Select Columns** dialog box, select the check box or check boxes of each column for which you want to create a statistic and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="861bb-181">Klicken Sie im Dialogfeld **neue Statistik für Tabelle**_table_name_ auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="861bb-181">In the **New Statistics on Table**_table_name_ dialog box, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="861bb-182">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="861bb-182">Using Transact-SQL</span></span>  
  
#### <a name="to-create-statistics"></a><span data-ttu-id="861bb-183">So erstellen Sie Statistiken</span><span class="sxs-lookup"><span data-stu-id="861bb-183">To create statistics</span></span>  
  
1.  <span data-ttu-id="861bb-184">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="861bb-184">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="861bb-185">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="861bb-185">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="861bb-186">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="861bb-186">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    -- Create new statistic object called ContactMail1  
    -- on the BusinessEntityID and EmailPromotion columns in the Person.Person table.   
  
    CREATE STATISTICS ContactMail1  
        ON Person.Person (BusinessEntityID, EmailPromotion);   
    GO  
    ```  
  
4.  <span data-ttu-id="861bb-187">Die oben erstellte Statistik kann zu einer Verbesserung der Ergebnisse für die folgende Abfrage führen.</span><span class="sxs-lookup"><span data-stu-id="861bb-187">The statistic created above potentially improves the results for the following query.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    SELECT LastName, FirstName  
    FROM Person.Person  
    WHERE EmailPromotion = 2  
    ORDER BY LastName, FirstName;   
    GO  
    ```  
  
 <span data-ttu-id="861bb-188">Weitere Informationen finden Sie unter [CREATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-statistics-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="861bb-188">For more information, see [CREATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-statistics-transact-sql).</span></span>  
  
  
