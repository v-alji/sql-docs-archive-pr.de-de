---
title: Verschieben eines vorhandenen Indexes in eine andere Dateigruppe | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- moving tables
- switching filegroups for index
- moving indexes
- indexes [SQL Server], moving
- filegroups [SQL Server], switching
ms.assetid: 167ebe77-487d-4ca8-9452-4b2c7d5cb96e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c99847dcb8d4d65272dd3660c7fd60d3efb8d951
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622092"
---
# <a name="move-an-existing-index-to-a-different-filegroup"></a><span data-ttu-id="50fb8-102">Verschieben eines vorhandenen Indexes in eine andere Dateigruppe</span><span class="sxs-lookup"><span data-stu-id="50fb8-102">Move an Existing Index to a Different Filegroup</span></span>
  <span data-ttu-id="50fb8-103">In diesem Thema wird beschrieben, wie Sie einen vorhandenen Index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]von der aktuellen Dateigruppe in eine andere verschieben.</span><span class="sxs-lookup"><span data-stu-id="50fb8-103">This topic describes how to move an existing index from its current filegroup to a different filegroup in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="50fb8-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="50fb8-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="50fb8-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="50fb8-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="50fb8-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="50fb8-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="50fb8-107">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="50fb8-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="50fb8-108">**Verschieben eines vorhandenen Indexes in eine andere Dateigruppe mit:**</span><span class="sxs-lookup"><span data-stu-id="50fb8-108">**To move an existing index to a different filegroup, using:**</span></span>  
  
     [<span data-ttu-id="50fb8-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="50fb8-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="50fb8-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="50fb8-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="50fb8-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="50fb8-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="50fb8-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="50fb8-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="50fb8-113">Bei Tabellen mit gruppiertem Index wird beim Verschieben des gruppierten Index in eine neue Dateigruppe auch die Tabelle in diese Dateigruppe verschoben.</span><span class="sxs-lookup"><span data-stu-id="50fb8-113">If a table has a clustered index, moving the clustered index to a new filegroup moves the table to that filegroup.</span></span>  
  
-   <span data-ttu-id="50fb8-114">Mit einer UNIQUE- oder PRIMARY KEY-Einschränkung mit [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]erstellte Indizes können nicht verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="50fb8-114">You cannot move indexes created using a UNIQUE or PRIMARY KEY constraint using [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span> <span data-ttu-id="50fb8-115">Verwenden Sie zum Verschieben dieser Indizes die [CREATE INDEX](/sql/t-sql/statements/create-index-transact-sql) -Anweisung mit der Option (DROP_EXISTING=ON) in [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="50fb8-115">To move these indexes use the [CREATE INDEX](/sql/t-sql/statements/create-index-transact-sql) statement with the (DROP_EXISTING=ON) option in [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="50fb8-116">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="50fb8-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="50fb8-117">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="50fb8-117">Permissions</span></span>  
 <span data-ttu-id="50fb8-118">Erfordert die ALTER-Berechtigung in der Tabelle oder Sicht.</span><span class="sxs-lookup"><span data-stu-id="50fb8-118">Requires ALTER permission on the table or view.</span></span> <span data-ttu-id="50fb8-119">Der Benutzer muss ein Mitglied der festen Serverrolle **sysadmin** bzw. der festen Datenbankrollen **db_ddladmin** und **db_owner** sein.</span><span class="sxs-lookup"><span data-stu-id="50fb8-119">User must be a member of the **sysadmin** fixed server role or the **db_ddladmin** and **db_owner** fixed database roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="50fb8-120">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="50fb8-120">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-move-an-existing-index-to-a-different-filegroup-using-table-designer"></a><span data-ttu-id="50fb8-121">So verschieben Sie einen vorhandenen Index mit dem Tabellen-Designer in eine andere Dateigruppe</span><span class="sxs-lookup"><span data-stu-id="50fb8-121">To move an existing index to a different filegroup using Table Designer</span></span>  
  
1.  <span data-ttu-id="50fb8-122">Klicken Sie im Objekt-Explorer auf das Pluszeichen, um die Datenbank zu erweitern, die die Tabelle mit dem zu verschiebenden Index enthält.</span><span class="sxs-lookup"><span data-stu-id="50fb8-122">In Object Explorer, click the plus sign to expand the database that contains the table containing the index that you want to move.</span></span>  
  
2.  <span data-ttu-id="50fb8-123">Klicken Sie auf das Pluszeichen, um den Ordner **Tabellen** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="50fb8-123">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="50fb8-124">Klicken Sie mit der rechten Maustaste auf die Tabelle mit dem zu verschiebenden Index, und wählen Sie **Entwurf**aus.</span><span class="sxs-lookup"><span data-stu-id="50fb8-124">Right-click the table containing the index that you want to move and select **Design**.</span></span>  
  
4.  <span data-ttu-id="50fb8-125">Klicken Sie im Menü **Tabellen-Designer** auf **Indizes/Schlüssel**.</span><span class="sxs-lookup"><span data-stu-id="50fb8-125">On the **Table Designer** menu, click **Indexes/Keys**.</span></span>  
  
5.  <span data-ttu-id="50fb8-126">Wählen Sie den Index aus, den Sie verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="50fb8-126">Select the index that you want to move.</span></span>  
  
6.  <span data-ttu-id="50fb8-127">Erweitern Sie im Hauptraster **Datenbereichsspezifikation**.</span><span class="sxs-lookup"><span data-stu-id="50fb8-127">In the main grid, expand **Data Space Specification**.</span></span>  
  
7.  <span data-ttu-id="50fb8-128">Wählen Sie **Schemaname der Dateigruppe oder Partition** aus, und wählen Sie in der Liste die Dateigruppe oder das Partitionsschema aus, in die bzw. den Sie den Index verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="50fb8-128">Select **Filegroup or Partition Scheme Name** and select from the list the filegroup or partition scheme to where you want to move the index.</span></span>  
  
8.  <span data-ttu-id="50fb8-129">Klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="50fb8-129">Click **Close**.</span></span>  
  
9. <span data-ttu-id="50fb8-130">Klicken Sie im Menü **Datei** auf **Save**_Tabellenname_.</span><span class="sxs-lookup"><span data-stu-id="50fb8-130">On the **File** menu, select **Save**_table_name_.</span></span>  
  
#### <a name="to-move-an-existing-index-to-a-different-filegroup-in-object-explorer"></a><span data-ttu-id="50fb8-131">So verschieben Sie einen vorhandenen Index im Objekt-Explorer in eine andere Dateigruppe</span><span class="sxs-lookup"><span data-stu-id="50fb8-131">To move an existing index to a different filegroup in Object Explorer</span></span>  
  
1.  <span data-ttu-id="50fb8-132">Klicken Sie im Objekt-Explorer auf das Pluszeichen, um die Datenbank zu erweitern, die die Tabelle mit dem zu verschiebenden Index enthält.</span><span class="sxs-lookup"><span data-stu-id="50fb8-132">In Object Explorer, click the plus sign to expand the database that contains the table containing the index that you want to move.</span></span>  
  
2.  <span data-ttu-id="50fb8-133">Klicken Sie auf das Pluszeichen, um den Ordner **Tabellen** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="50fb8-133">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="50fb8-134">Klicken Sie auf das Pluszeichen, um die Tabelle mit dem zu verschiebenden Index zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="50fb8-134">Click the plus sign to expand the table containing the index that you want to move.</span></span>  
  
4.  <span data-ttu-id="50fb8-135">Klicken Sie auf das Pluszeichen, um den Ordner **Indizes** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="50fb8-135">Click the plus sign to expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="50fb8-136">Klicken Sie mit der rechten Maustaste auf den Index, den Sie verschieben möchten, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="50fb8-136">Right-click the index that you want to move and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="50fb8-137">Wählen Sie unter **Seite auswählen**die Option **Speicher**aus.</span><span class="sxs-lookup"><span data-stu-id="50fb8-137">Under **Select a page**, select **Storage**.</span></span>  
  
7.  <span data-ttu-id="50fb8-138">Wählen Sie die Dateigruppe aus, in die der Index verschoben werden soll.</span><span class="sxs-lookup"><span data-stu-id="50fb8-138">Select the filegroup in which to move the index.</span></span>  
  
     <span data-ttu-id="50fb8-139">Wählen Sie bei partitionierten Tabellen und Indizes das Partitionsschema aus, in das der Index verschoben werden soll.</span><span class="sxs-lookup"><span data-stu-id="50fb8-139">If the table or index is partitioned, select the partition scheme in which to move the index.</span></span> <span data-ttu-id="50fb8-140">Weitere Informationen zu partitionierten Indizes finden Sie unter [Partitioned Tables and Indexes](../partitions/partitioned-tables-and-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="50fb8-140">For more information about partitioned indexes, see [Partitioned Tables and Indexes](../partitions/partitioned-tables-and-indexes.md).</span></span>  
  
     <span data-ttu-id="50fb8-141">Für das Verschieben von gruppierten Indizes können Sie die Onlineverarbeitung verwenden.</span><span class="sxs-lookup"><span data-stu-id="50fb8-141">If you are moving a clustered index, you can use online processing.</span></span> <span data-ttu-id="50fb8-142">Die Onlineverarbeitung ermöglicht, dass Benutzer während des Verschiebungsvorgangs des Indexes auf die dem Index zugrunde liegenden Daten sowie auf nicht gruppierte Indizes zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="50fb8-142">Online processing allows concurrent user access to the underlying data and to nonclustered indexes during the index operation.</span></span> <span data-ttu-id="50fb8-143">Weitere Informationen finden Sie unter [Ausführen von Onlineindexvorgängen](perform-index-operations-online.md) .</span><span class="sxs-lookup"><span data-stu-id="50fb8-143">For more information, see [Perform Index Operations Online](perform-index-operations-online.md).</span></span>  
  
     <span data-ttu-id="50fb8-144">Auf Multiprozessorcomputern mit [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]können Sie die Anzahl der zum Ausführen der Indexanweisung verwendeten Prozessoren mit einem maximalen Grad an Parallelität konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="50fb8-144">On multiprocessor computers using [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], you can configure the number of processors used to execute the index statement by specifying a maximum degree of parallelism value.</span></span> <span data-ttu-id="50fb8-145">Die Funktion für parallele Indexvorgänge ist nicht in jeder Edition von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]verfügbar.</span><span class="sxs-lookup"><span data-stu-id="50fb8-145">The Parallel indexed operations feature is not available in every edition of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="50fb8-146">Eine Liste der Funktionen, die von den Editionen von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]unterstützt werden, finden Sie unter [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="50fb8-146">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span> <span data-ttu-id="50fb8-147">Weitere Informationen zu parallelen Indexvorgängen finden Sie unter [Konfigurieren von Parallelindexvorgängen](configure-parallel-index-operations.md).</span><span class="sxs-lookup"><span data-stu-id="50fb8-147">For more information about Parallel indexed operations, see [Configure Parallel Index Operations](configure-parallel-index-operations.md).</span></span>  
  
8.  <span data-ttu-id="50fb8-148">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="50fb8-148">Click **OK**.</span></span>  
  
 <span data-ttu-id="50fb8-149">Die folgenden Informationen sind auf der Seite **Speicher** des Dialogfelds **Indexeigenschaften –** _Indexname_ verfügbar:</span><span class="sxs-lookup"><span data-stu-id="50fb8-149">The following information is available on the **Storage** page of the **Index Properties -** _index_name_ dialog box:</span></span>  
  
 <span data-ttu-id="50fb8-150">**Dateigruppe**</span><span class="sxs-lookup"><span data-stu-id="50fb8-150">**Filegroup**</span></span>  
 <span data-ttu-id="50fb8-151">Speichert den Index in der angegebenen Dateigruppe.</span><span class="sxs-lookup"><span data-stu-id="50fb8-151">Stores the index in the specified filegroup.</span></span> <span data-ttu-id="50fb8-152">Diese Liste enthält nur Standarddateigruppen (ROW).</span><span class="sxs-lookup"><span data-stu-id="50fb8-152">The list only displays standard (row) filegroups.</span></span> <span data-ttu-id="50fb8-153">Die Standardauswahl in der Liste ist die PRIMARY-Dateigruppe der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="50fb8-153">The default list selection is the PRIMARY filegroup of the database.</span></span>  
  
 <span data-ttu-id="50fb8-154">**FILESTREAM-Dateigruppe**</span><span class="sxs-lookup"><span data-stu-id="50fb8-154">**Filestream filegroup**</span></span>  
 <span data-ttu-id="50fb8-155">Gibt die Dateigruppe für FILESTREAM-Daten an.</span><span class="sxs-lookup"><span data-stu-id="50fb8-155">Specifies the filegroup for FILESTREAM data.</span></span> <span data-ttu-id="50fb8-156">Diese Liste zeigt nur FILESTREAM-Dateigruppen an.</span><span class="sxs-lookup"><span data-stu-id="50fb8-156">This list displays only FILESTREAM filegroups.</span></span> <span data-ttu-id="50fb8-157">Die Standardlistenauswahl ist die Dateigruppe PRIMARY FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="50fb8-157">The default list selection is the PRIMARY FILESTREAM filegroup.</span></span>  
  
 <span data-ttu-id="50fb8-158">**Partitionsschema**</span><span class="sxs-lookup"><span data-stu-id="50fb8-158">**Partition scheme**</span></span>  
 <span data-ttu-id="50fb8-159">Speichert den Index in einem Partitionsschema.</span><span class="sxs-lookup"><span data-stu-id="50fb8-159">Stores the index in a partition scheme.</span></span> <span data-ttu-id="50fb8-160">Wenn Sie auf **Partitionsschema** klicken, wird das unten stehende Raster aktiviert.</span><span class="sxs-lookup"><span data-stu-id="50fb8-160">Clicking **Partition Scheme** enables the grid below.</span></span> <span data-ttu-id="50fb8-161">Die Standardlistenauswahl ist das für das Speichern der Tabellendaten verwendete Partitionsschema.</span><span class="sxs-lookup"><span data-stu-id="50fb8-161">The default list selection is the partition scheme that is used for storing the table data.</span></span> <span data-ttu-id="50fb8-162">Bei Auswahl eines anderen Partitionsschemas in der Liste werden die im Raster angezeigten Informationen aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="50fb8-162">When you select a different partition scheme in the list, the information in the grid is updated.</span></span>  
  
 <span data-ttu-id="50fb8-163">Die Option Partitionsschema ist nicht verfügbar, wenn in der Datenbank keine Partitionsschemas vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="50fb8-163">The partition scheme option is unavailable if there are no partition schemes in the database.</span></span>  
  
 <span data-ttu-id="50fb8-164">**Dateidatenstrom-Partitionsschema**</span><span class="sxs-lookup"><span data-stu-id="50fb8-164">**Filestream partition scheme**</span></span>  
 <span data-ttu-id="50fb8-165">Gibt das Partitionsschema für FILESTREAM-Daten an.</span><span class="sxs-lookup"><span data-stu-id="50fb8-165">Specifies the partition scheme for FILESTREAM data.</span></span> <span data-ttu-id="50fb8-166">Das Partitionsschema muss mit dem Schema symmetrisch sein, das in der Option **Partitionsschema** angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="50fb8-166">The partition scheme must be symmetric with the scheme that is specified in the **Partition scheme** option.</span></span>  
  
 <span data-ttu-id="50fb8-167">Wenn die Tabelle nicht partitioniert ist, ist das Feld leer.</span><span class="sxs-lookup"><span data-stu-id="50fb8-167">If the table is not partitioned, the field is blank.</span></span>  
  
 <span data-ttu-id="50fb8-168">**Partitionsschemaparameter**</span><span class="sxs-lookup"><span data-stu-id="50fb8-168">**Partition Scheme Parameter**</span></span>  
 <span data-ttu-id="50fb8-169">Zeigt den Namen der Spalte an, die Teil des Partitionsschemas ist.</span><span class="sxs-lookup"><span data-stu-id="50fb8-169">Displays the name of the column that participates in the partition scheme.</span></span>  
  
 <span data-ttu-id="50fb8-170">**Tabellenspalte**</span><span class="sxs-lookup"><span data-stu-id="50fb8-170">**Table Column**</span></span>  
 <span data-ttu-id="50fb8-171">Wählt die Tabelle oder Sicht aus, die dem Partitionsschema zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="50fb8-171">Select the table or view to map to the partition scheme.</span></span>  
  
 <span data-ttu-id="50fb8-172">**Datentyp der Spalte**</span><span class="sxs-lookup"><span data-stu-id="50fb8-172">**Column Data Type**</span></span>  
 <span data-ttu-id="50fb8-173">Zeigt Datentypinformationen zu der Spalte an.</span><span class="sxs-lookup"><span data-stu-id="50fb8-173">Displays data type information about the column.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="50fb8-174">Wenn die Tabellenspalte eine berechnete Spalte ist, wird unter **Spaltendatentyp** „berechnete Spalte“ angezeigt.</span><span class="sxs-lookup"><span data-stu-id="50fb8-174">If the table column is a computed column, **Column Data Type** displays "computed column."</span></span>  
  
 <span data-ttu-id="50fb8-175">**Onlineverarbeitung von DML-Anweisungen während der Indexverschiebung zulassen**</span><span class="sxs-lookup"><span data-stu-id="50fb8-175">**Allow online processing of DML statements while moving the index**</span></span>  
 <span data-ttu-id="50fb8-176">Ermöglicht Benutzern während des Indexvorgangs den Zugriff auf die zugrunde liegenden Tabellen- bzw. gruppierten Indexdaten und zugehörigen nicht gruppierten Indizes.</span><span class="sxs-lookup"><span data-stu-id="50fb8-176">Allows users to access the underlying table or clustered index data and any associated nonclustered indexes during the index operation.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="50fb8-177">Diese Option ist für XML-Indizes nicht verfügbar. Das gilt auch, wenn der Index ein deaktivierter gruppierter Index ist.</span><span class="sxs-lookup"><span data-stu-id="50fb8-177">This option is not available for XML indexes, or if the index is a disabled clustered index.</span></span>  
  
 <span data-ttu-id="50fb8-178">**Maximalen Grad an Parallelität festlegen**</span><span class="sxs-lookup"><span data-stu-id="50fb8-178">**Set maximum degree of parallelism**</span></span>  
 <span data-ttu-id="50fb8-179">Begrenzt die Anzahl der bei der Ausführung paralleler Pläne einzusetzenden Prozessoren.</span><span class="sxs-lookup"><span data-stu-id="50fb8-179">Limits the number of processors to use during parallel plan execution.</span></span> <span data-ttu-id="50fb8-180">Der Standardwert ist 0; bei diesem Wert wird die tatsächliche Anzahl der verfügbaren CPUs verwendet.</span><span class="sxs-lookup"><span data-stu-id="50fb8-180">The default value, 0, uses the actual number of available CPUs.</span></span> <span data-ttu-id="50fb8-181">Wenn Sie den Wert auf 1 setzen, wird die Ausführung paralleler Pläne unterdrückt; bei einem Wert von größer als 1 wird die maximale Anzahl der bei der Ausführung einer einzelnen Abfrage zu verwendenden Prozessoren begrenzt.</span><span class="sxs-lookup"><span data-stu-id="50fb8-181">Setting the value to 1 suppresses parallel plan generation; setting the value to a number greater than 1 restricts the maximum number of processors used by a single query execution.</span></span> <span data-ttu-id="50fb8-182">Diese Option ist nur verfügbar, wenn sich das Dialogfeld im Status **Neu organisieren** oder **Neu erstellen** befindet.</span><span class="sxs-lookup"><span data-stu-id="50fb8-182">This option only becomes available if the dialog box is in the **Rebuild** or **Recreate** state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="50fb8-183">Wird ein Wert angegeben, der über der Anzahl der verfügbaren CPUs liegt, wird die tatsächliche Anzahl der CPUs verwendet.</span><span class="sxs-lookup"><span data-stu-id="50fb8-183">If a value greater than the number of available CPUs is specified, the actual number of available CPUs is used.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="50fb8-184">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="50fb8-184">Using Transact-SQL</span></span>  
  
#### <a name="to-move-an-existing-index-to-a-different-filegroup"></a><span data-ttu-id="50fb8-185">So verschieben Sie einen vorhandenen Index in eine andere Dateigruppe</span><span class="sxs-lookup"><span data-stu-id="50fb8-185">To move an existing index to a different filegroup</span></span>  
  
1.  <span data-ttu-id="50fb8-186">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="50fb8-186">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="50fb8-187">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="50fb8-187">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="50fb8-188">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="50fb8-188">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Creates the TransactionsFG1 filegroup on the AdventureWorks2012 database  
    ALTER DATABASE AdventureWorks2012  
    ADD FILEGROUP TransactionsFG1;  
    GO  
    /* Adds the TransactionsFG1dat3 file to the TransactionsFG1 filegroup. Please note that you will have to change the filename parameter in this statement to execute it without errors.  
    */  
    ALTER DATABASE AdventureWorks2012   
    ADD FILE   
    (  
        NAME = TransactionsFG1dat3,  
        FILENAME = 'C:\Program Files\Microsoft SQL Server\MSSQL12\MSSQL\DATA\TransactionsFG1dat3.ndf',  
        SIZE = 5MB,  
        MAXSIZE = 100MB,  
        FILEGROWTH = 5MB  
    )  
    TO FILEGROUP TransactionsFG1;  
    GO  
    /*Creates the IX_Employee_OrganizationLevel_OrganizationNode index  
      on the TransactionsPS1 filegroup and drops the original IX_Employee_OrganizationLevel_OrganizationNode index.  
    */  
    CREATE NONCLUSTERED INDEX IX_Employee_OrganizationLevel_OrganizationNode  
        ON HumanResources.Employee (OrganizationLevel, OrganizationNode)  
        WITH (DROP_EXISTING = ON)  
        ON TransactionsFG1;  
    GO  
    ```  
  
 <span data-ttu-id="50fb8-189">Weitere Informationen finden Sie unter [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="50fb8-189">For more information, see [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span></span>  
  
  
