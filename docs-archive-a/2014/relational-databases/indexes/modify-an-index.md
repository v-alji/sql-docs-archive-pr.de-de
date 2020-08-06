---
title: Ändern eines Indexes | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- indexes [SQL Server], modifying
- modifying indexes
- index changes [SQL Server]
ms.assetid: 97e3110d-fde7-4f5d-9309-dc1697960aeb
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2af9293966afce8372f5b83a579418c546c82816
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723874"
---
# <a name="modify-an-index"></a><span data-ttu-id="355b8-102">Ändern eines Indexes</span><span class="sxs-lookup"><span data-stu-id="355b8-102">Modify an Index</span></span>
  <span data-ttu-id="355b8-103">In diesem Thema wird beschrieben, wie Sie einen Index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]ändern.</span><span class="sxs-lookup"><span data-stu-id="355b8-103">This topic describes how to modify an index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="355b8-104">Indizes, die als Ergebnis einer PRIMARY KEY- oder UNIQUE-Einschränkung erstellt wurden, können mit dieser Methode nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="355b8-104">Indexes created as the result of a PRIMARY KEY or UNIQUE constraint cannot be modified by using this method.</span></span> <span data-ttu-id="355b8-105">In diesem Fall muss die Einschränkung geändert werden.</span><span class="sxs-lookup"><span data-stu-id="355b8-105">Instead, the constraint must be modified.</span></span>  
  
 <span data-ttu-id="355b8-106">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="355b8-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="355b8-107">**Ändern eines Indexes mit:**</span><span class="sxs-lookup"><span data-stu-id="355b8-107">**To modify an index, using:**</span></span>  
  
     [<span data-ttu-id="355b8-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="355b8-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="355b8-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="355b8-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="355b8-110">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="355b8-110">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-an-index"></a><span data-ttu-id="355b8-111">So ändern Sie einen Index</span><span class="sxs-lookup"><span data-stu-id="355b8-111">To modify an index</span></span>  
  
1.  <span data-ttu-id="355b8-112">Stellen Sie im Objekt-Explorer eine Verbindung mit einer Instanz von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] her, und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="355b8-112">In Object Explorer, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="355b8-113">Erweitern Sie **Datenbanken**und dann die Datenbank, zu der die Tabelle gehört, und klicken Sie anschließend auf **Tabellen**.</span><span class="sxs-lookup"><span data-stu-id="355b8-113">Expand **Databases**, expand the database in which the table belongs, and then expand **Tables**.</span></span>  
  
3.  <span data-ttu-id="355b8-114">Erweitern Sie die Tabelle, in die der Index gehört, und erweitern Sie dann **Indizes**.</span><span class="sxs-lookup"><span data-stu-id="355b8-114">Expand the table in which the index belongs and then expand **Indexes**.</span></span>  
  
4.  <span data-ttu-id="355b8-115">Klicken Sie mit der rechten Maustaste auf den Index, den Sie ändern möchten, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="355b8-115">Right-click the index that you want to modify and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="355b8-116">Nehmen Sie im Dialogfeld **Indexeigenschaften** die gewünschten Änderungen vor.</span><span class="sxs-lookup"><span data-stu-id="355b8-116">In the **Index Properties** dialog box, make the desired changes.</span></span> <span data-ttu-id="355b8-117">Sie können z. B. eine Spalte im Indexschlüssel hinzufügen oder entfernen oder die Einstellung einer Indexoption ändern.</span><span class="sxs-lookup"><span data-stu-id="355b8-117">For example, you can add or remove a column from the index key, or change the setting of an index option.</span></span>  
  
#### <a name="to-modify-index-columns"></a><span data-ttu-id="355b8-118">So ändern Sie Indexspalten</span><span class="sxs-lookup"><span data-stu-id="355b8-118">To modify index columns</span></span>  
  
1.  <span data-ttu-id="355b8-119">Wenn Sie die Position einer Indexspalte hinzufügen, entfernen oder ändern möchten, wählen Sie im Dialogfeld **Indexeigenschaften** die Seite **Allgemein** aus.</span><span class="sxs-lookup"><span data-stu-id="355b8-119">To add, remove, or change the position of an index column, select the **General** page from the **Index Properties** dialog box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="355b8-120">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="355b8-120">Using Transact-SQL</span></span>  
  
#### <a name="to-modify-an-index"></a><span data-ttu-id="355b8-121">So ändern Sie einen Index</span><span class="sxs-lookup"><span data-stu-id="355b8-121">To modify an index</span></span>  
  
1.  <span data-ttu-id="355b8-122">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="355b8-122">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="355b8-123">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="355b8-123">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="355b8-124">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="355b8-124">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="355b8-125">In diesem Beispiel wird ein vorhandener Index für die `ProductID` -Spalte der `Production.WorkOrder` -Tabelle mithilfe der `DROP_EXISTING` -Option gelöscht und neu erstellt.</span><span class="sxs-lookup"><span data-stu-id="355b8-125">This example drops and re-creates an existing index on the `ProductID` column of the `Production.WorkOrder` table by using the `DROP_EXISTING` option.</span></span> <span data-ttu-id="355b8-126">Die Optionen `FILLFACTOR` und `PAD_INDEX` sind ebenfalls festgelegt.</span><span class="sxs-lookup"><span data-stu-id="355b8-126">The options `FILLFACTOR` and `PAD_INDEX` are also set.</span></span>  
  
     [!code-sql[IndexDDL#CreateIndex4](../../snippets/tsql/SQL14/tsql/indexddl/transact-sql/createindex.sql#createindex4)]  
  
     <span data-ttu-id="355b8-127">Im folgenden Beispiel werden mithilfe von ALTER INDEX mehrere Optionen für den `AK_SalesOrderHeader_SalesOrderNumber`-Index festgelegt.</span><span class="sxs-lookup"><span data-stu-id="355b8-127">The following example uses ALTER INDEX to set several options on the index `AK_SalesOrderHeader_SalesOrderNumber`.</span></span>  
  
     [!code-sql[IndexDDL#AlterIndex4](../../snippets/tsql/SQL14/tsql/indexddl/transact-sql/alterindex.sql#alterindex4)]  
  
#### <a name="to-modify-index-columns"></a><span data-ttu-id="355b8-128">So ändern Sie Indexspalten</span><span class="sxs-lookup"><span data-stu-id="355b8-128">To modify index columns</span></span>  
  
1.  <span data-ttu-id="355b8-129">Wenn Sie die Position einer Indexspalte hinzufügen, entfernen oder ändern möchten, müssen Sie den Index löschen und neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="355b8-129">To add, remove, or change the position of an index column, you must drop and recreate the index.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="355b8-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="355b8-130">See Also</span></span>  
 <span data-ttu-id="355b8-131">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="355b8-131">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span></span>  
 <span data-ttu-id="355b8-132">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="355b8-132">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span></span>  
 <span data-ttu-id="355b8-133">[INDEXPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/indexproperty-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="355b8-133">[INDEXPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/indexproperty-transact-sql) </span></span>  
 <span data-ttu-id="355b8-134">[sys.indexes &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-indexes-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="355b8-134">[sys.indexes &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-indexes-transact-sql) </span></span>  
 <span data-ttu-id="355b8-135">[sys.index_columns &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-index-columns-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="355b8-135">[sys.index_columns &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-index-columns-transact-sql) </span></span>  
 <span data-ttu-id="355b8-136">[Festlegen von Indexoptionen](set-index-options.md) </span><span class="sxs-lookup"><span data-stu-id="355b8-136">[Set Index Options](set-index-options.md) </span></span>  
 [<span data-ttu-id="355b8-137">Umbenennen von Indizes</span><span class="sxs-lookup"><span data-stu-id="355b8-137">Rename Indexes</span></span>](indexes.md)  
  
  
