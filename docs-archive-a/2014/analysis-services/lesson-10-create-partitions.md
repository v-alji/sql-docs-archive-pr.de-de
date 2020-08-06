---
title: 'Lektion 11: Erstellen von Partitionen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 92eb21a8-5fc4-4999-ad37-1332ce26431d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4db5edd5d47fe424ef6e6ad2a822106110209059
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608050"
---
# <a name="lesson-11-create-partitions"></a><span data-ttu-id="3cfa5-102">Lektion 11: Erstellen von Partitionen</span><span class="sxs-lookup"><span data-stu-id="3cfa5-102">Lesson 11: Create Partitions</span></span>
  <span data-ttu-id="3cfa5-103">In dieser Lektion erstellen Sie Partitionen, um die Internet Sales-Tabelle in kleinere logische Teile aufzuteilen, die unabhängig von anderen Partitionen verarbeitet (aktualisiert) werden können.</span><span class="sxs-lookup"><span data-stu-id="3cfa5-103">In this lesson, you will create partitions to divide the Internet Sales table into smaller logical parts that can be processed (Refreshed) independent of other partitions.</span></span> <span data-ttu-id="3cfa5-104">Standardmäßig verfügt jede Tabelle, die Sie in Ihr Modell einschließen, über eine Partition, die alle Spalten und Zeilen der Tabelle enthält.</span><span class="sxs-lookup"><span data-stu-id="3cfa5-104">By default, every table you include in your model has one partition which includes all of the table's columns and rows.</span></span> <span data-ttu-id="3cfa5-105">Für die Internet Sales-Tabelle sollen die Daten nach Jahr aufgeteilt werden. eine Partition für jede der fünf Jahre der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="3cfa5-105">For the Internet Sales table, we want to divide the data by year; one partition for each of the table's five years.</span></span>  <span data-ttu-id="3cfa5-106">Jede Partition kann dann unabhängig verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="3cfa5-106">Each partition can then be processed independently.</span></span> <span data-ttu-id="3cfa5-107">Weitere Informationen finden Sie unter [Partitionen &#40;SSAS – tabellarisch&#41;](tabular-models/partitions-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="3cfa5-107">To learn more, see [Partitions &#40;SSAS Tabular&#41;](tabular-models/partitions-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="3cfa5-108">Geschätzte Zeit zum Bearbeiten dieser Lektion: **15 Minuten**</span><span class="sxs-lookup"><span data-stu-id="3cfa5-108">Estimated time to complete this lesson: **15 minutes**</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3cfa5-109">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="3cfa5-109">Prerequisites</span></span>  
 <span data-ttu-id="3cfa5-110">Dieses Thema ist Teil eines Tutorials zur Tabellenmodellierung, das in der richtigen Reihenfolge absolviert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="3cfa5-110">This topic is part of a tabular modeling tutorial, which should be completed in order.</span></span> <span data-ttu-id="3cfa5-111">Sie sollten vor dem Ausführen der Aufgaben in dieser Lektion die vorherige Lektion abgeschlossen haben: [Lektion 10: Erstellen von Hierarchien](lesson-9-create-hierarchies.md).</span><span class="sxs-lookup"><span data-stu-id="3cfa5-111">Before performing the tasks in this lesson, you should have completed the previous lesson: [Lesson 10: Create Hierarchies](lesson-9-create-hierarchies.md).</span></span>  
  
## <a name="create-partitions"></a><span data-ttu-id="3cfa5-112">Erstellen von Partitionen</span><span class="sxs-lookup"><span data-stu-id="3cfa5-112">Create Partitions</span></span>  
  
#### <a name="to-create-partitions-in-the-internet-sales-table"></a><span data-ttu-id="3cfa5-113">So erstellen Sie Partitionen in der Internet Sales-Tabelle</span><span class="sxs-lookup"><span data-stu-id="3cfa5-113">To create partitions in the Internet Sales table</span></span>  
  
1.  <span data-ttu-id="3cfa5-114">Klicken Sie im Modell-Designer auf die Tabelle **Internet Sales** und dann auf das Menü **Tabelle** . Klicken Sie anschließend auf **Partitionen**.</span><span class="sxs-lookup"><span data-stu-id="3cfa5-114">In the model designer, click on the **Internet Sales** table, then click on the **Table** menu, and then click **Partitions**.</span></span>  
  
     <span data-ttu-id="3cfa5-115">Das Dialogfeld **Partitions-Manager** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="3cfa5-115">The **Partition Manager** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="3cfa5-116">Klicken Sie im Dialogfeld **Partitions-Manager** unter **Partitionen**auf die Partition **Internet Sales** .</span><span class="sxs-lookup"><span data-stu-id="3cfa5-116">In the **Partition Manager** dialog box, in **Partitions**, click the **Internet Sales** partition.</span></span>  
  
3.  <span data-ttu-id="3cfa5-117">Ändern Sie unter **Partitions Name**den Namen in `Internet Sales 2005` .</span><span class="sxs-lookup"><span data-stu-id="3cfa5-117">In **Partition Name**, change the name to `Internet Sales 2005`.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="3cfa5-118">Vor dem Fortfahren mit dem nächsten Schritt ist zu beachten, dass die Spaltennamen für diese in der Modelltabelle enthaltenen (aktivierten) Spalten im Tabellenvorschaufenster den Spaltennamen der Quelle entsprechen.</span><span class="sxs-lookup"><span data-stu-id="3cfa5-118">Before continuing to the next step, notice the column names in the Table Preview window display those columns included in the model table (checked) with the column names from the source.</span></span> <span data-ttu-id="3cfa5-119">Das liegt daran, dass das Tabellenvorschaufenster Spalten von der Quelltabelle und nicht von der Modelltabelle anzeigt.</span><span class="sxs-lookup"><span data-stu-id="3cfa5-119">This is because the Table Preview window displays columns from the source table, not from the model table.</span></span>  
  
4.  <span data-ttu-id="3cfa5-120">Klicken Sie direkt rechts oberhalb des Vorschaufensters auf die Schaltfläche **Abfrage-Editor** .</span><span class="sxs-lookup"><span data-stu-id="3cfa5-120">Select the **Query Editor** button just above the right side of the preview window.</span></span>  
  
     <span data-ttu-id="3cfa5-121">Da die Partition nur die Zeilen eines bestimmten Zeitraums beinhalten soll, ist die WHERE-Klausel einzufügen.</span><span class="sxs-lookup"><span data-stu-id="3cfa5-121">Because you want the partition to include only those rows within a certain period, you must include a WHERE clause.</span></span> <span data-ttu-id="3cfa5-122">Sie können nur anhand einer SQL-Anweisung eine WHERE-Klausel erstellen.</span><span class="sxs-lookup"><span data-stu-id="3cfa5-122">You can only create a WHERE clause by using a SQL Statement.</span></span>  
  
5.  <span data-ttu-id="3cfa5-123">Ersetzen Sie im Feld **SQL-Anweisung** die vorhandene Anweisung durch die folgende Anweisung:</span><span class="sxs-lookup"><span data-stu-id="3cfa5-123">In the **SQL Statement** field, replace the existing statement by pasting in the following statement:</span></span>  
  
    ```  
    SELECT   
    [dbo].[FactInternetSales].[ProductKey],  
    [dbo].[FactInternetSales].[CustomerKey],  
    [dbo].[FactInternetSales].[PromotionKey],  
    [dbo].[FactInternetSales].[CurrencyKey],  
    [dbo].[FactInternetSales].[SalesTerritoryKey],  
    [dbo].[FactInternetSales].[SalesOrderNumber],  
    [dbo].[FactInternetSales].[SalesOrderLineNumber],  
    [dbo].[FactInternetSales].[RevisionNumber],  
    [dbo].[FactInternetSales].[OrderQuantity],  
    [dbo].[FactInternetSales].[UnitPrice],  
    [dbo].[FactInternetSales].[ExtendedAmount],  
    [dbo].[FactInternetSales].[UnitPriceDiscountPct],  
    [dbo].[FactInternetSales].[DiscountAmount],  
    [dbo].[FactInternetSales].[ProductStandardCost],  
    [dbo].[FactInternetSales].[TotalProductCost],  
    [dbo].[FactInternetSales].[SalesAmount],  
    [dbo].[FactInternetSales].[TaxAmt],  
    [dbo].[FactInternetSales].[Freight],  
    [dbo].[FactInternetSales].[CarrierTrackingNumber],  
    [dbo].[FactInternetSales].[CustomerPONumber],  
    [dbo].[FactInternetSales].[OrderDate],  
    [dbo].[FactInternetSales].[DueDate],  
    [dbo].[FactInternetSales].[ShipDate]   
    FROM [dbo].[FactInternetSales]  
    WHERE (([OrderDate] >= N'2005-01-01 00:00:00') AND ([OrderDate] < N'2006-01-01 00:00:00'))  
    ```  
  
     <span data-ttu-id="3cfa5-124">Diese Anweisung gibt an, dass die Partition alle Daten der Zeilen beinhalten soll, bei denen OrderDate für das Kalenderjahr 2005 gilt (wie in der WHERE-Klausel angegeben).</span><span class="sxs-lookup"><span data-stu-id="3cfa5-124">This statement specifies the partition should include all of the data in those rows where the OrderDate is for the 2005 calendar year as specified in the WHERE clause.</span></span>  
  
6.  <span data-ttu-id="3cfa5-125">Klicken Sie auf **Überprüfen**.</span><span class="sxs-lookup"><span data-stu-id="3cfa5-125">Click **Validate**.</span></span>  
  
     <span data-ttu-id="3cfa5-126">Beachten Sie, dass eine Warnung mit dem Hinweis angezeigt wird, dass bestimmte Spalten nicht in der Quelle vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="3cfa5-126">Notice a warning is displayed stating that certain columns are not present in source.</span></span> <span data-ttu-id="3cfa5-127">Dies liegt daran, dass Sie in [Lektion 3: Umbenennen von Spalten](rename-columns.md)die Spalten in der Internet Sales-Tabelle im Modell umbenannt haben, sodass Sie sich von denselben Spalten an der Quelle unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="3cfa5-127">This is because in [Lesson 3: Rename Columns](rename-columns.md), you renamed those columns in the Internet Sales table in the model to be different from those same columns at the source.</span></span>  
  
#### <a name="to-create-a-partition-for-the-2006-year-in-the-internet-sales-table"></a><span data-ttu-id="3cfa5-128">So erstellen Sie für das Jahr 2006 in der Internet Sales-Tabelle eine Partition</span><span class="sxs-lookup"><span data-stu-id="3cfa5-128">To create a partition for the 2006 year in the Internet Sales table</span></span>  
  
1.  <span data-ttu-id="3cfa5-129">Klicken Sie im Dialogfeld **Partitions-Manager** unter **Partitionen**auf die Partition, die `Internet Sales 2005` Sie soeben erstellt haben, und dann auf **Kopieren**.</span><span class="sxs-lookup"><span data-stu-id="3cfa5-129">In the **Partition Manager** dialog box, in **Partitions**, click the `Internet Sales 2005` partition you just created, and then **Copy**.</span></span>  
  
2.  <span data-ttu-id="3cfa5-130">Geben Sie in **Partitions Name den Namen**ein `Internet Sales 2006` .</span><span class="sxs-lookup"><span data-stu-id="3cfa5-130">In **Partition Name**, type `Internet Sales 2006`.</span></span>  
  
3.  <span data-ttu-id="3cfa5-131">Ersetzen Sie in der SQL-Anweisung die WHERE-Klausel durch Folgendes, damit die Partition nur die Zeilen für das 2006-Jahr enthält:</span><span class="sxs-lookup"><span data-stu-id="3cfa5-131">In the SQL Statement, in-order for the partition to include only those rows for the 2006 year, replace the WHERE clause with the following:</span></span>  
  
    ```  
    WHERE (([OrderDate] >= N'2006-01-01 00:00:00') AND ([OrderDate] < N'2007-01-01 00:00:00'))  
    ```  
  
#### <a name="to-create-a-partition-for-the-2007-year-in-the-internet-sales-table"></a><span data-ttu-id="3cfa5-132">So erstellen Sie für das Jahr 2007 in der Internet Sales-Tabelle eine Partition</span><span class="sxs-lookup"><span data-stu-id="3cfa5-132">To create a partition for the 2007 year in the Internet Sales table</span></span>  
  
1.  <span data-ttu-id="3cfa5-133">Klicken Sie im Dialogfeld **Partitions-Manager** auf **Kopieren**.</span><span class="sxs-lookup"><span data-stu-id="3cfa5-133">In the **Partition Manager** dialog box, click **Copy**.</span></span>  
  
2.  <span data-ttu-id="3cfa5-134">Geben Sie in **Partitions Name den Namen**ein `Internet Sales 2007` .</span><span class="sxs-lookup"><span data-stu-id="3cfa5-134">In **Partition Name**, type `Internet Sales 2007`.</span></span>  
  
3.  <span data-ttu-id="3cfa5-135">Wählen Sie in **Wechseln zu die**Option **Abfrage-Editor**aus.</span><span class="sxs-lookup"><span data-stu-id="3cfa5-135">In **Switch To**, select **Query Editor**.</span></span>  
  
4.  <span data-ttu-id="3cfa5-136">Ersetzen Sie in der SQL-Anweisung die WHERE-Klausel durch Folgendes, damit die Partition nur die Zeilen für das 2007-Jahr enthält:</span><span class="sxs-lookup"><span data-stu-id="3cfa5-136">In the SQL Statement, in-order for the partition to include only those rows for the 2007 year, replace the WHERE clause with the following:</span></span>  
  
    ```  
    WHERE (([OrderDate] >= N'2007-01-01 00:00:00') AND ([OrderDate] < N'2008-01-01 00:00:00'))  
    ```  
  
#### <a name="to-create-a-partition-for-the-2008-year-in-the-internet-sales-table"></a><span data-ttu-id="3cfa5-137">So erstellen Sie für das Jahr 2008 in der Internet Sales-Tabelle eine Partition</span><span class="sxs-lookup"><span data-stu-id="3cfa5-137">To create a partition for the 2008 year in the Internet Sales table</span></span>  
  
1.  <span data-ttu-id="3cfa5-138">Klicken Sie im Dialogfeld **Partitions-Manager** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="3cfa5-138">In the **Partition Manager** dialog box, click **New**.</span></span>  
  
2.  <span data-ttu-id="3cfa5-139">Geben Sie in **Partitions Name den Namen**ein `Internet Sales 2008` .</span><span class="sxs-lookup"><span data-stu-id="3cfa5-139">In **Partition Name**, type `Internet Sales 2008`.</span></span>  
  
3.  <span data-ttu-id="3cfa5-140">Wählen Sie in **Wechseln zu die**Option **Abfrage-Editor**aus.</span><span class="sxs-lookup"><span data-stu-id="3cfa5-140">In **Switch To**, select **Query Editor**.</span></span>  
  
4.  <span data-ttu-id="3cfa5-141">Ersetzen Sie in der SQL-Anweisung die WHERE-Klausel durch Folgendes, damit die Partition nur die Zeilen für das 2008-Jahr enthält:</span><span class="sxs-lookup"><span data-stu-id="3cfa5-141">In the SQL Statement, in-order for the partition to include only those rows for the 2008 year, replace the WHERE clause with the following:</span></span>  
  
    ```  
    WHERE (([OrderDate] >= N'2008-01-01 00:00:00') AND ([OrderDate] < N'2009-01-01 00:00:00'))  
    ```  
  
#### <a name="to-create-a-partition-for-the-2009-year-in-the-internet-sales-table"></a><span data-ttu-id="3cfa5-142">So erstellen Sie für das Jahr 2009 in der Internet Sales-Tabelle eine Partition</span><span class="sxs-lookup"><span data-stu-id="3cfa5-142">To create a partition for the 2009 year in the Internet Sales table</span></span>  
  
1.  <span data-ttu-id="3cfa5-143">Klicken Sie im Dialogfeld **Partitions-Manager** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="3cfa5-143">In the **Partition Manager** dialog box, click **New**.</span></span>  
  
2.  <span data-ttu-id="3cfa5-144">Geben Sie in **Partitions Name den Namen**ein `Internet Sales 2009` .</span><span class="sxs-lookup"><span data-stu-id="3cfa5-144">In **Partition Name**, type `Internet Sales 2009`.</span></span>  
  
3.  <span data-ttu-id="3cfa5-145">Wählen Sie in **Wechseln zu die**Option **Abfrage-Editor**aus.</span><span class="sxs-lookup"><span data-stu-id="3cfa5-145">In **Switch To**, select **Query Editor**.</span></span>  
  
4.  <span data-ttu-id="3cfa5-146">Ersetzen Sie in der SQL-Anweisung die WHERE-Klausel durch Folgendes, damit die Partition nur die Zeilen für das Jahr 2009 enthält:</span><span class="sxs-lookup"><span data-stu-id="3cfa5-146">In the SQL Statement, in-order for the partition to include only those rows for the 2009 year, replace the WHERE clause with the following:</span></span>  
  
    ```  
    WHERE (([OrderDate] >= N'2009-01-01 00:00:00') AND ([OrderDate] < N'2010-01-01 00:00:00'))  
    ```  
  
## <a name="process-partitions"></a><span data-ttu-id="3cfa5-147">Partitionen verarbeiten</span><span class="sxs-lookup"><span data-stu-id="3cfa5-147">Process Partitions</span></span>  
 <span data-ttu-id="3cfa5-148">Achten Sie im Dialogfeld **Partitions-Manager** auf das Sternchen (**\***) neben den Partitionsnamen für jede der gerade neu erstellten Partitionen.</span><span class="sxs-lookup"><span data-stu-id="3cfa5-148">In the **Partition Manager** dialog box, notice the asterisk (**\***) next to the partition names for each of the new partitions you just created.</span></span> <span data-ttu-id="3cfa5-149">Dies gibt an, dass die Partition noch nicht verarbeitet (aktualisiert) wurde.</span><span class="sxs-lookup"><span data-stu-id="3cfa5-149">This indicates that the partition has not been processed (refreshed).</span></span> <span data-ttu-id="3cfa5-150">Wenn Sie neue Partitionen erstellen, führen Sie einen Partitionsverarbeitungs- bzw. Tabellenverarbeitungsvorgang aus, um die Daten dieser Partitionen zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="3cfa5-150">When you create new partitions, you should run a Process Partitions or Process Table operation to refresh the data in those partitions.</span></span>  
  
#### <a name="to-process-internet-sales-partitions"></a><span data-ttu-id="3cfa5-151">So verarbeiten Sie die Internet Sales-Partitionen</span><span class="sxs-lookup"><span data-stu-id="3cfa5-151">To process Internet Sales partitions</span></span>  
  
1.  <span data-ttu-id="3cfa5-152">Klicken Sie auf **OK** , um das Dialogfeld **Partitions-Manager** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="3cfa5-152">Click **OK** to close the **Partition Manager** dialog box.</span></span>  
  
2.  <span data-ttu-id="3cfa5-153">Klicken Sie im Modell-Designer auf die Tabelle **Internet Sales** . Klicken Sie anschließend auf das Menü **Modell** , zeigen Sie auf **Verarbeiten** (Aktualisieren), und klicken Sie auf **Partitionen verarbeiten**.</span><span class="sxs-lookup"><span data-stu-id="3cfa5-153">In the model designer, click the **Internet Sales** table, then click the **Model** menu, then point to **Process** (Refresh), and then click **Process Partitions**.</span></span>  
  
3.  <span data-ttu-id="3cfa5-154">Überprüfen Sie im Dialogfeld **Partitionen verarbeiten** , ob der Wert für **Modus** auf **Standard verarbeiten**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="3cfa5-154">In the **Process Partitions** dialog box, verify the **Mode** is set to **Process Default**.</span></span>  
  
4.  <span data-ttu-id="3cfa5-155">Aktivieren Sie für jede der fünf Partitionen, die Sie erstellt haben, das Kontrollkästchen in der Spalte **Verarbeiten**, und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3cfa5-155">Select the checkbox in the **Process** column for each of the five partitions you created, and then click **OK**.</span></span>  
  
     <span data-ttu-id="3cfa5-156">Wenn Identitätswechsel-Anmeldeinformationen verlangt werden, geben Sie die Kombination aus Windows-Benutzername und Kennwort ein, die Sie in Lektion 2 (Schritt 6) angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="3cfa5-156">If you are prompted for Impersonation credentials, enter the Windows user name and password you specified in Lesson 2, step 6.</span></span>  
  
     <span data-ttu-id="3cfa5-157">Daraufhin wird das Dialogfeld **Daten Prozess** angezeigt, in dem die Prozessdetails für jede Partition angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="3cfa5-157">The **Data Process** dialog box then appears and displays process details for each partition.</span></span> <span data-ttu-id="3cfa5-158">Beachten Sie, dass eine unterschiedliche Anzahl an Zeilen für jede Partition übertragen wird.</span><span class="sxs-lookup"><span data-stu-id="3cfa5-158">Notice that a different number of rows for each partition are transferred.</span></span> <span data-ttu-id="3cfa5-159">Das liegt daran, dass jede Partition nur die Zeilen für das in der WHERE-Klausel der SQL-Anweisung angegebene Jahr beinhaltet.</span><span class="sxs-lookup"><span data-stu-id="3cfa5-159">This is because each partition includes only those rows for the year specified in the WHERE clause in the SQL Statement.</span></span> <span data-ttu-id="3cfa5-160">Für das Jahr 2010 sind keine Daten vorhanden.</span><span class="sxs-lookup"><span data-stu-id="3cfa5-160">There is no data for the 2010 year.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="3cfa5-161">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="3cfa5-161">Next Steps</span></span>  
 <span data-ttu-id="3cfa5-162">Wenn Sie mit diesem Tutorial fortfahren möchten, wechseln Sie zur nächsten Lektion: [Lektion 12: Erstellen von Rollen](lesson-11-create-roles.md).</span><span class="sxs-lookup"><span data-stu-id="3cfa5-162">To continue this tutorial, go to the next lesson: Lesson: [Lesson 12: Create Roles](lesson-11-create-roles.md).</span></span>  
  
  
