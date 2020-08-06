---
title: Konfigurieren von Parallelindexvorgängen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- index parallel operations [SQL Server]
- processors [SQL Server], parallel index operations
- max degree of parallelism option
- MAXDOP index option, parallel index operations
- parallel index operations [SQL Server]
ms.assetid: 8ec8c71e-5fc1-443a-92da-136ee3fc7f88
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8831aadae15af03a05f4ab03cfe514e54566df1f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608641"
---
# <a name="configure-parallel-index-operations"></a><span data-ttu-id="53c17-102">Konfigurieren von Parallelindexvorgängen</span><span class="sxs-lookup"><span data-stu-id="53c17-102">Configure Parallel Index Operations</span></span>
  <span data-ttu-id="53c17-103">In diesem Thema wird der maximale Grad an Parallelität beschrieben und erläutert, wie Sie diese Einstellung in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]ändern.</span><span class="sxs-lookup"><span data-stu-id="53c17-103">This topic defines max degree of parallelism and explains how to modify this setting in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="53c17-104">Auf Multiprozessorcomputern, auf denen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Enterprise oder höher ausgeführt wird, werden für Indexanweisungen möglicherweise mehrere Prozessoren verwendet, um die mit der Indexanweisung verknüpften Scan-, Sortierungs- und Indexvorgänge auszuführen. Dies geschieht in gleicher Weise wie bei anderen Abfragen.</span><span class="sxs-lookup"><span data-stu-id="53c17-104">On multiprocessor computers that are running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Enterprise or higher, index statements may use multiple processors to perform the scan, sort, and index operations associated with the index statement just like other queries do.</span></span> <span data-ttu-id="53c17-105">Die Anzahl der Prozessoren, die zur Ausführung einer einzelnen Indexanweisung verwendet werden, wird durch die Konfigurationsoption [Max. Grad an Parallelität](../../database-engine/configure-windows/configure-the-max-degree-of-parallelism-server-configuration-option.md) sowie durch die aktuelle Arbeitslast und die Indexstatistiken bestimmt.</span><span class="sxs-lookup"><span data-stu-id="53c17-105">The number of processors used to run a single index statement is determined by the [max degree of parallelism](../../database-engine/configure-windows/configure-the-max-degree-of-parallelism-server-configuration-option.md) configuration option, the current workload, and the index statistics.</span></span> <span data-ttu-id="53c17-106">Mit der Option Max. Grad an Parallelität wird die maximale Anzahl der Prozessoren festgelegt, die bei der Ausführung paralleler Pläne verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="53c17-106">The max degree of parallelism option determines the maximum number of processors to use in parallel plan execution.</span></span> <span data-ttu-id="53c17-107">Wenn [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] feststellt, dass das System ausgelastet ist, wird der Grad der Parallelität des Indexvorgangs automatisch verringert, bevor mit dem Ausführen der Anweisung begonnen wird.</span><span class="sxs-lookup"><span data-stu-id="53c17-107">If the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] detects that the system is busy, the degree of parallelism of the index operation is automatically reduced before statement execution starts.</span></span> <span data-ttu-id="53c17-108">[!INCLUDE[ssDE](../../includes/ssde-md.md)] kann den Grad der Parallelität auch verringern, wenn die führende Schlüsselspalte eines nicht partitionierten Indexes eine begrenzte Anzahl unterschiedlicher Werte aufweist, oder wenn die Häufigkeit der einzelnen unterschiedlichen Werte stark schwankt.</span><span class="sxs-lookup"><span data-stu-id="53c17-108">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] can also reduce the degree of parallelism if the leading key column of a non-partitioned index has a limited number of distinct values or the frequency of each distinct value varies significantly.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="53c17-109">Parallele Indexvorgänge sind nicht in jeder [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Edition verfügbar.</span><span class="sxs-lookup"><span data-stu-id="53c17-109">Parallel index operations are not available in every [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] edition.</span></span> <span data-ttu-id="53c17-110">Weitere Informationen finden Sie unter [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="53c17-110">For more information, see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
 <span data-ttu-id="53c17-111">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="53c17-111">**In This Topic**</span></span>  
  
-   <span data-ttu-id="53c17-112">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="53c17-112">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="53c17-113">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="53c17-113">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="53c17-114">Security</span><span class="sxs-lookup"><span data-stu-id="53c17-114">Security</span></span>](#Security)  
  
-   <span data-ttu-id="53c17-115">**Festlegen des maximalen Grads an Parallelität mit:**</span><span class="sxs-lookup"><span data-stu-id="53c17-115">**To set the max degree of parallelism, using:**</span></span>  
  
     [<span data-ttu-id="53c17-116">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="53c17-116">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="53c17-117">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="53c17-117">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="53c17-118">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="53c17-118">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="53c17-119">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="53c17-119">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="53c17-120">Mit der Anzahl der Prozessoren, die vom Abfrageoptimierer verwendet wird, kann zumeist eine optimale Leistung gewährleistet werden.</span><span class="sxs-lookup"><span data-stu-id="53c17-120">The number of processors that are used by the query optimizer typically provides optimal performance.</span></span> <span data-ttu-id="53c17-121">Allerdings können bestimmte Vorgänge, wie das Erstellen, erneute Erstellen oder Löschen sehr großer Indizes die Ressourcen stark beanspruchen, wodurch während des Indexvorgangs möglicherweise nicht genügend Ressourcen für andere Anwendungen und Datenbankvorgänge verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="53c17-121">However, operations such as creating, rebuilding, or dropping very large indexes are resource intensive and can cause insufficient resources for other applications and database operations for the duration of the index operation.</span></span> <span data-ttu-id="53c17-122">Wenn dieses Problem auftritt, können Sie die zum Ausführen der Indexanweisung verwendete maximale Anzahl von Prozessoren manuell konfigurieren, indem Sie die Anzahl von Prozessoren für den Indexvorgang verringern.</span><span class="sxs-lookup"><span data-stu-id="53c17-122">When this problem occurs, you can manually configure the maximum number of processors that are used to run the index statement by limiting the number of processors to use for the index operation.</span></span>  
  
-   <span data-ttu-id="53c17-123">Die MAXDOP-Indexoption überschreibt die Max. Grad an Parallelität-Konfigurationsoption, jedoch nur für die Abfrage, die diese Option angibt.</span><span class="sxs-lookup"><span data-stu-id="53c17-123">The MAXDOP index option overrides the max degree of parallelism configuration option only for the query specifying this option.</span></span> <span data-ttu-id="53c17-124">In der folgenden Tabelle werden die gültigen ganzzahligen Werte aufgelistet, die mit der Max. Grad an Parallelität-Konfigurationsoption und der MAXDOP-Indexoption angegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="53c17-124">The following table lists the valid integer values that can be specified with the max degree of parallelism configuration option and the MAXDOP index option.</span></span>  
  
    |<span data-ttu-id="53c17-125">Wert</span><span class="sxs-lookup"><span data-stu-id="53c17-125">Value</span></span>|<span data-ttu-id="53c17-126">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="53c17-126">Description</span></span>|  
    |-----------|-----------------|  
    |<span data-ttu-id="53c17-127">0</span><span class="sxs-lookup"><span data-stu-id="53c17-127">0</span></span>|<span data-ttu-id="53c17-128">Gibt an, dass der Server die Anzahl der CPUs festlegt, die verwendet werden, abhängig von der aktuellen Systemarbeitsauslastung.</span><span class="sxs-lookup"><span data-stu-id="53c17-128">Specifies that the server determines the number of CPUs that are used, depending on the current system workload.</span></span> <span data-ttu-id="53c17-129">Dies ist die Standardeinstellung und die empfohlene Einstellung.</span><span class="sxs-lookup"><span data-stu-id="53c17-129">This is the default value and recommended setting.</span></span>|  
    |<span data-ttu-id="53c17-130">1</span><span class="sxs-lookup"><span data-stu-id="53c17-130">1</span></span>|<span data-ttu-id="53c17-131">Unterdrückt das Generieren paralleler Pläne.</span><span class="sxs-lookup"><span data-stu-id="53c17-131">Suppresses parallel plan generation.</span></span> <span data-ttu-id="53c17-132">Die Operationen werden dann nacheinander, also seriell ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="53c17-132">The operation will be executed serially.</span></span>|  
    |<span data-ttu-id="53c17-133">2 - 64</span><span class="sxs-lookup"><span data-stu-id="53c17-133">2-64</span></span>|<span data-ttu-id="53c17-134">Schränkt die Anzahl der Prozessoren auf den angegebenen Wert ein.</span><span class="sxs-lookup"><span data-stu-id="53c17-134">Limits the number of processors to the specified value.</span></span> <span data-ttu-id="53c17-135">In Abhängigkeit von der aktuellen Systemlast kann eine geringere Anzahl von Prozessoren verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="53c17-135">Fewer processors may be used depending on the current workload.</span></span> <span data-ttu-id="53c17-136">Wird ein Wert angegeben, der über der Anzahl der verfügbaren CPUs liegt, wird die tatsächliche Anzahl der CPUs verwendet.</span><span class="sxs-lookup"><span data-stu-id="53c17-136">If a value larger than the number of available CPUs is specified, the actual number of available CPUs is used.</span></span>|  
  
-   <span data-ttu-id="53c17-137">Die parallele Indexausführung und die MAXDOP-Indexoption gelten für die folgenden [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="53c17-137">Parallel index execution and the MAXDOP index option apply to the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
    -   <span data-ttu-id="53c17-138">CREATE INDEX</span><span class="sxs-lookup"><span data-stu-id="53c17-138">CREATE INDEX</span></span>  
  
    -   <span data-ttu-id="53c17-139">ALTER INDEX REBUILD</span><span class="sxs-lookup"><span data-stu-id="53c17-139">ALTER INDEX REBUILD</span></span>  
  
    -   <span data-ttu-id="53c17-140">DROP INDEX (Gilt nur für gruppierte Indizes.)</span><span class="sxs-lookup"><span data-stu-id="53c17-140">DROP INDEX (This applies to clustered indexes only.)</span></span>  
  
    -   <span data-ttu-id="53c17-141">ALTER TABLE ADD (Index) CONSTRAINT</span><span class="sxs-lookup"><span data-stu-id="53c17-141">ALTER TABLE ADD (index) CONSTRAINT</span></span>  
  
    -   <span data-ttu-id="53c17-142">ALTER TABLE DROP (gruppierter Index) CONSTRAINT</span><span class="sxs-lookup"><span data-stu-id="53c17-142">ALTER TABLE DROP (clustered index) CONSTRAINT</span></span>  
  
-   <span data-ttu-id="53c17-143">In der ALTER INDEX REORGANIZE-Anweisung kann die MAXDOP-Indexoption nicht angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="53c17-143">The MAXDOP index option cannot be specified in the ALTER INDEX REORGANIZE statement.</span></span>  
  
-   <span data-ttu-id="53c17-144">Die Speicheranforderungen für partitionierte Indexvorgänge, bei denen Sortiervorgänge erforderlich sind, können größer sein, wenn der Abfrageoptimierer Grade der Parallelität beim Erstellungsvorgang verwendet.</span><span class="sxs-lookup"><span data-stu-id="53c17-144">Memory requirements for partitioned index operations that require sorting can be greater if the query optimizer applies degrees of parallelism to the build operation.</span></span> <span data-ttu-id="53c17-145">Je höher der Grad der Parallelität ist, desto höher ist der Speicherbedarf.</span><span class="sxs-lookup"><span data-stu-id="53c17-145">The higher the degrees of parallelism, the greater the memory requirement is.</span></span> <span data-ttu-id="53c17-146">Weitere Informationen finden Sie unter [partitionierte Tabellen und Indizes](../partitions/partitioned-tables-and-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="53c17-146">For more information, see [Partitioned Tables and Indexes](../partitions/partitioned-tables-and-indexes.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="53c17-147">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="53c17-147">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="53c17-148">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="53c17-148">Permissions</span></span>  
 <span data-ttu-id="53c17-149">Erfordert die ALTER-Berechtigung in der Tabelle oder Sicht.</span><span class="sxs-lookup"><span data-stu-id="53c17-149">Requires ALTER permission on the table or view.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="53c17-150">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="53c17-150">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-set-max-degree-of-parallelism-on-an-index"></a><span data-ttu-id="53c17-151">So legen Sie den maximalen Grad an Parallelität für einen Index fest</span><span class="sxs-lookup"><span data-stu-id="53c17-151">To set max degree of parallelism on an index</span></span>  
  
1.  <span data-ttu-id="53c17-152">Klicken Sie im Objekt-Explorer auf das Pluszeichen, um die Datenbank mit der Tabelle zu erweitern, in der Sie den maximalen Grad an Parallelität für einen Index festlegen möchten.</span><span class="sxs-lookup"><span data-stu-id="53c17-152">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to set max degree of parallelism for an index.</span></span>  
  
2.  <span data-ttu-id="53c17-153">Erweitern Sie den Ordner **Tabellen** .</span><span class="sxs-lookup"><span data-stu-id="53c17-153">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="53c17-154">Klicken Sie auf das Pluszeichen, um die Tabelle zu erweitern, in der Sie den maximalen Grad an Parallelität für einen Index festlegen möchten.</span><span class="sxs-lookup"><span data-stu-id="53c17-154">Click the plus sign to expand the table on which you want to set max degree of parallelism for an index.</span></span>  
  
4.  <span data-ttu-id="53c17-155">Erweitern Sie den Ordner **Indizes** .</span><span class="sxs-lookup"><span data-stu-id="53c17-155">Expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="53c17-156">Klicken Sie mit der rechten Maustaste auf den Index, für den Sie den maximalen Grad an Parallelität festlegen möchten, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="53c17-156">Right-click the index for which you want to set the max degree of parallelism and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="53c17-157">Wählen Sie unter **Seite auswählen**die Option **Optionen**aus.</span><span class="sxs-lookup"><span data-stu-id="53c17-157">Under **Select a page**, select **Options**.</span></span>  
  
7.  <span data-ttu-id="53c17-158">Wählen Sie **Maximaler Grad an Parallelität**aus, und geben Sie dann einen Wert zwischen 1 und 64 ein.</span><span class="sxs-lookup"><span data-stu-id="53c17-158">Select **Maximum degree of parallelism**, and then enter some value between 1 and 64.</span></span>  
  
8.  <span data-ttu-id="53c17-159">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="53c17-159">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="53c17-160">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="53c17-160">Using Transact-SQL</span></span>  
  
#### <a name="to-set-max-degree-of-parallelism-on-an-existing-index"></a><span data-ttu-id="53c17-161">So legen Sie den maximalen Grad an Parallelität für einen vorhandenen Index fest</span><span class="sxs-lookup"><span data-stu-id="53c17-161">To set max degree of parallelism on an existing index</span></span>  
  
1.  <span data-ttu-id="53c17-162">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="53c17-162">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="53c17-163">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="53c17-163">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="53c17-164">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="53c17-164">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    /*Alters the IX_ProductVendor_VendorID index on the Purchasing.ProductVendor table so that, if the server has eight or more processors, the Database Engine will limit the execution of the index operation to eight or fewer processors.  
    */  
    ALTER INDEX IX_ProductVendor_VendorID ON Purchasing.ProductVendor  
    REBUILD WITH (MAXDOP=8);   
    GO  
    ```  
  
 <span data-ttu-id="53c17-165">Weitere Informationen finden Sie unter [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="53c17-165">For more information, see [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
#### <a name="set-max-degree-of-parallelism-on-a-new-index"></a><span data-ttu-id="53c17-166">So legen Sie den maximalen Grad an Parallelität für einen neuen Index fest</span><span class="sxs-lookup"><span data-stu-id="53c17-166">Set max degree of parallelism on a new index</span></span>  
  
1.  <span data-ttu-id="53c17-167">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="53c17-167">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="53c17-168">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="53c17-168">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="53c17-169">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="53c17-169">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    CREATE INDEX IX_ProductVendor_NewVendorID   
    ON Purchasing.ProductVendor (BusinessEntityID)  
    WITH (MAXDOP=8);  
    GO  
    ```  
  
 <span data-ttu-id="53c17-170">Weitere Informationen finden Sie unter [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="53c17-170">For more information, see [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span></span>  
  
  
