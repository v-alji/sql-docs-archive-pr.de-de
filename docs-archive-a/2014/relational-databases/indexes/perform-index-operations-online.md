---
title: Ausführen von Onlineindexvorgängen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- index online operations [SQL Server]
- online index operations
- ONLINE option
ms.assetid: 1e43537c-bf67-4db3-9908-3cb45c6fdaa1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4d09bd99a0eaec5fdb433bd8c33351d7622957a2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622089"
---
# <a name="perform-index-operations-online"></a><span data-ttu-id="13094-102">Ausführen von Onlineindexvorgängen</span><span class="sxs-lookup"><span data-stu-id="13094-102">Perform Index Operations Online</span></span>
  <span data-ttu-id="13094-103">In diesem Thema wird beschrieben, wie Sie Indizes in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]online erstellen, neu erstellen oder löschen.</span><span class="sxs-lookup"><span data-stu-id="13094-103">This topic describes how to create, rebuild, or drop indexes online in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="13094-104">Die ONLINE-Option ermöglicht, dass Benutzer während dieser Indexvorgänge gleichzeitig auf die dem Index zugrunde liegende Tabelle oder auf Daten eines gruppierten Indexes sowie auf alle eventuell damit verbundenen nicht gruppierten Indizes zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="13094-104">The ONLINE option allows concurrent user access to the underlying table or clustered index data and any associated nonclustered indexes during these index operations.</span></span> <span data-ttu-id="13094-105">Während beispielsweise ein gruppierter Index von einem Benutzer neu erstellt wird, kann dieser Benutzer – und alle anderen Benutzer – weiterhin die dem Index zugrunde liegenden Daten aktualisieren oder abfragen.</span><span class="sxs-lookup"><span data-stu-id="13094-105">For example, while a clustered index is being rebuilt by one user, that user and others can continue to update and query the underlying data.</span></span> <span data-ttu-id="13094-106">Wenn Sie DDL-Vorgänge (Datendefinitionssprache) wie das Erstellen oder Neuerstellen eines gruppierten Indexes offline ausführen, richten diese Vorgänge exklusive Sperren für die dem Index zugrunde liegenden Daten und damit verbundene Indizes ein.</span><span class="sxs-lookup"><span data-stu-id="13094-106">When you perform data definition language (DDL) operations offline, such as building or rebuilding a clustered index; these operations hold exclusive locks on the underlying data and associated indexes.</span></span> <span data-ttu-id="13094-107">Damit werden Änderungen und Abfragen der zugrunde liegenden Daten verhindert, bis der Indexvorgang abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="13094-107">This prevents modifications and queries to the underlying data until the index operation is complete.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="13094-108">Onlineindexvorgänge sind nicht in jeder Edition von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] verfügbar.</span><span class="sxs-lookup"><span data-stu-id="13094-108">Online index operations are not available in every [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] edition.</span></span> <span data-ttu-id="13094-109">Weitere Informationen finden Sie unter [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="13094-109">For more information, see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
 <span data-ttu-id="13094-110">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="13094-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="13094-111">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="13094-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="13094-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="13094-112">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="13094-113">Security</span><span class="sxs-lookup"><span data-stu-id="13094-113">Security</span></span>](#Security)  
  
-   <span data-ttu-id="13094-114">**Onlineneuerstellung eines Indexes mit:**</span><span class="sxs-lookup"><span data-stu-id="13094-114">**To rebuild an index online, using:**</span></span>  
  
     [<span data-ttu-id="13094-115">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="13094-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="13094-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="13094-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="13094-117">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="13094-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="13094-118">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="13094-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="13094-119">Onlineindexvorgänge werden in Geschäftsumgebungen empfohlen, die rund um die Uhr und 7 Tage die Woche aktiv sind, für die also eine gleichzeitige Benutzeraktivität während Indexvorgängen unabdingbar ist.</span><span class="sxs-lookup"><span data-stu-id="13094-119">We recommend performing online index operations for business environments that operate 24 hours a day, seven days a week, in which the need for concurrent user activity during index operations is vital.</span></span>  
  
-   <span data-ttu-id="13094-120">Die ONLINE-Option ist in folgenden [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="13094-120">The ONLINE option is available in the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span>  
  
    -   [<span data-ttu-id="13094-121">CREATE INDEX</span><span class="sxs-lookup"><span data-stu-id="13094-121">CREATE INDEX</span></span>](/sql/t-sql/statements/create-index-transact-sql)  
  
    -   [<span data-ttu-id="13094-122">ALTER INDEX</span><span class="sxs-lookup"><span data-stu-id="13094-122">ALTER INDEX</span></span>](/sql/t-sql/statements/alter-index-transact-sql)  
  
    -   [<span data-ttu-id="13094-123">DROP INDEX</span><span class="sxs-lookup"><span data-stu-id="13094-123">DROP INDEX</span></span>](/sql/t-sql/statements/drop-index-transact-sql)  
  
    -   <span data-ttu-id="13094-124">[ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) (zum Hinzufügen oder Löschen von UNIQUE- oder PRIMARY KEY-Einschränkungen mit der CLUSTERED-Indexoption)</span><span class="sxs-lookup"><span data-stu-id="13094-124">[ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) (To add or drop UNIQUE or PRIMARY KEY constraints with CLUSTERED index option)</span></span>  
  
-   <span data-ttu-id="13094-125">Weitere Einschränkungen und Einschränkungen im Zusammenhang mit der Onlineerstellung, -neuerstellung und -löschung von Indizes finden Sie unter [Richtlinien für Onlineindexvorgänge](guidelines-for-online-index-operations.md).</span><span class="sxs-lookup"><span data-stu-id="13094-125">For more limitations and restrictions concerning creating, rebuilding, or dropping indexes online, see [Guidelines for Online Index Operations](guidelines-for-online-index-operations.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="13094-126">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="13094-126">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="13094-127">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="13094-127">Permissions</span></span>  
 <span data-ttu-id="13094-128">Erfordert die ALTER-Berechtigung in der Tabelle oder Sicht.</span><span class="sxs-lookup"><span data-stu-id="13094-128">Requires ALTER permission on the table or view.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="13094-129">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="13094-129">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-rebuild-an-index-online"></a><span data-ttu-id="13094-130">Sie erstellen Sie einen Index online neu</span><span class="sxs-lookup"><span data-stu-id="13094-130">To rebuild an index online</span></span>  
  
1.  <span data-ttu-id="13094-131">Klicken Sie im Objekt-Explorer auf das Pluszeichen, um die Datenbank mit der Tabelle zu erweitern, in der Sie einen Index online neu erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="13094-131">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to rebuild an index online.</span></span>  
  
2.  <span data-ttu-id="13094-132">Erweitern Sie den Ordner **Tabellen** .</span><span class="sxs-lookup"><span data-stu-id="13094-132">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="13094-133">Klicken Sie auf das Pluszeichen, um die Tabelle zu erweitern, für die Sie einen Index online neu erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="13094-133">Click the plus sign to expand the table on which you want to rebuild an index online.</span></span>  
  
4.  <span data-ttu-id="13094-134">Erweitern Sie den Ordner **Indizes** .</span><span class="sxs-lookup"><span data-stu-id="13094-134">Expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="13094-135">Klicken Sie mit der rechten Maustaste auf den Index, den Sie online neu erstellen möchten, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="13094-135">Right-click the index that you want to rebuild online and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="13094-136">Wählen Sie unter **Seite auswählen**die Option **Optionen**aus.</span><span class="sxs-lookup"><span data-stu-id="13094-136">Under **Select a page**, select **Options**.</span></span>  
  
7.  <span data-ttu-id="13094-137">Wählen Sie **DML-Onlineverarbeitung zulassen**aus, und wählen Sie dann in der Liste **True** aus.</span><span class="sxs-lookup"><span data-stu-id="13094-137">Select **Allow online DML processing**, and then select **True** from the list.</span></span>  
  
8.  <span data-ttu-id="13094-138">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="13094-138">Click **OK**.</span></span>  
  
9. <span data-ttu-id="13094-139">Klicken Sie mit der rechten Maustaste auf den Index, den Sie online neu erstellen möchten, und wählen Sie **Neu erstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="13094-139">Right-click the index that you want to rebuild online and select **Rebuild**.</span></span>  
  
10. <span data-ttu-id="13094-140">Überprüfen Sie im Dialogfeld **Indizes neu erstellen** , dass der richtige Index im Raster **Neu zu erstellende Indizes** ausgewählt ist, und klicken sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="13094-140">In the **Rebuild Indexes** dialog box, verify that the correct index is in the **Indexes to rebuild** grid and click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="13094-141">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="13094-141">Using Transact-SQL</span></span>  
  
#### <a name="to-create-rebuild-or-drop-an-index-online"></a><span data-ttu-id="13094-142">So können Sie einen Index online erstellen, neu erstellen oder löschen</span><span class="sxs-lookup"><span data-stu-id="13094-142">To create, rebuild, or drop an index online</span></span>  
  
1.  <span data-ttu-id="13094-143">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="13094-143">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="13094-144">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="13094-144">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="13094-145">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="13094-145">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="13094-146">Im folgenden Beispiel wird ein vorhandener Index online neu erstellt.</span><span class="sxs-lookup"><span data-stu-id="13094-146">The example rebuilds an existing online</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    ALTER INDEX AK_Employee_NationalIDNumber ON HumanResources.Employee  
    REBUILD WITH (ONLINE = ON);  
    GO  
    ```  
  
     <span data-ttu-id="13094-147">Im folgenden Beispiel wird ein gruppierter Index online gelöscht, und die daraus resultierende Tabelle (Heap) wird in die Dateigruppe `NewGroup` verschoben, wofür die `MOVE TO` -Klausel verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="13094-147">The following example deletes a clustered index online and moves the resulting table (heap) to the filegroup `NewGroup` by using the `MOVE TO` clause.</span></span> <span data-ttu-id="13094-148">Die Katalogsichten `sys.indexes`, `sys.tables`und `sys.filegroups` werden abgefragt, um die Platzierung von Index und Tabelle in den Dateigruppen vor und nach der Verschiebung zu prüfen.</span><span class="sxs-lookup"><span data-stu-id="13094-148">The `sys.indexes`, `sys.tables`, and `sys.filegroups` catalog views are queried to verify the index and table placement in the filegroups before and after the move.</span></span>  
  
     [!code-sql[IndexDDL#DropIndex4](../../snippets/tsql/SQL14/tsql/indexddl/transact-sql/dropindex.sql#dropindex4)]  
  
 <span data-ttu-id="13094-149">Weitere Informationen finden Sie unter [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="13094-149">For more information, see [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
  
