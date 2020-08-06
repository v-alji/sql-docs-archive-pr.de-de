---
title: 'Lektion 4: Definieren einer Datenverbindung und einer Datentabelle für untergeordnete Berichte | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a6aa2c56-227c-43c5-a28e-c7104131ac5e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6d9144d960ad933afa65f9d4483e96b5f732d944
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609714"
---
# <a name="lesson-4-define-a-data-connection-and-data-table-for-child-report"></a><span data-ttu-id="35475-102">Lektion 4: Definieren einer Datenverbindung und einer Datentabelle für den untergeordneten Bericht</span><span class="sxs-lookup"><span data-stu-id="35475-102">Lesson 4: Define a Data Connection and Data Table for Child Report</span></span>
  <span data-ttu-id="35475-103">Nachdem Sie den übergeordneten Bericht entworfen haben, erstellen Sie im nächsten Schritt eine Datenverbindung und eine Datentabelle für den untergeordneten Bericht.</span><span class="sxs-lookup"><span data-stu-id="35475-103">After you design the parent report, you next step is to create a data connection and a data table for the child report.</span></span> <span data-ttu-id="35475-104">In diesem Lernprogramm wird eine Datenverbindung mit der AdventureWorks2008-Datenbank hergestellt.</span><span class="sxs-lookup"><span data-stu-id="35475-104">In this tutorial the data connection is to the AdventureWorks2008 database.</span></span> <span data-ttu-id="35475-105">Alternativ können Sie auch eine Verbindung mit der AdventureWorks2012-Datenbank herstellen.</span><span class="sxs-lookup"><span data-stu-id="35475-105">You also have the option of connecting to the AdventureWorks2012 database.</span></span>  
  
### <a name="to-define-a-data-connection-and-datatable-by-adding-a-dataset-for-child-report"></a><span data-ttu-id="35475-106">So definieren Sie eine Datenverbindung und eine Datentabelle durch Hinzufügen eines Datasets (für den untergeordneten Bericht)</span><span class="sxs-lookup"><span data-stu-id="35475-106">To define a data connection and DataTable by adding a DataSet (for child report)</span></span>  
  
1.  <span data-ttu-id="35475-107">Klicken Sie im Menü **Website** auf **Neues Element hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="35475-107">On the **Website** menu, click **Add New Item**.</span></span>  
  
2.  <span data-ttu-id="35475-108">Klicken Sie im Dialogfeld **Neues Element hinzufügen** auf **DataSet** und dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="35475-108">In the **Add New Item** dialog box, click **DataSet** and then click **Add**.</span></span> <span data-ttu-id="35475-109">Wenn Sie dazu aufgefordert werden, sollten Sie das Element dem Ordner **App_Code** hinzufügen, indem Sie auf **Ja**klicken.</span><span class="sxs-lookup"><span data-stu-id="35475-109">When prompted, you should add the item to the **App_Code** folder by clicking **Yes**.</span></span>  
  
     <span data-ttu-id="35475-110">Dadurch wird dem Projekt die neue XSD-Datei **DataSet2.xsd** hinzugefügt und der DataSet-Designer geöffnet.</span><span class="sxs-lookup"><span data-stu-id="35475-110">This adds a new XSD file **DataSet2.xsd** to the project and opens the DataSet Designer.</span></span>  
  
3.  <span data-ttu-id="35475-111">Ziehen Sie ein **TableAdapter** -Steuerelement aus der Toolbox auf die Entwurfsoberfläche.</span><span class="sxs-lookup"><span data-stu-id="35475-111">From the Toolbox window, drag a **TableAdapter** control to the design surface.</span></span> <span data-ttu-id="35475-112">Dadurch wird der Konfigurations-Assistent **TableAdapter** gestartet.</span><span class="sxs-lookup"><span data-stu-id="35475-112">This launches the **TableAdapter** Configuration Wizard.</span></span>  
  
4.  <span data-ttu-id="35475-113">Klicken Sie auf der Seite **Wählen Sie Ihre Datenverbindung aus** auf **Neue Verbindung**.</span><span class="sxs-lookup"><span data-stu-id="35475-113">On the **Choose Your Data Connection** page, click **New Connection**.</span></span>  
  
5.  <span data-ttu-id="35475-114">Führen Sie im Dialogfeld **Verbindung hinzufügen** die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="35475-114">In the **Add Connection** dialog box, perform the following steps:</span></span>  
  
    1.  <span data-ttu-id="35475-115">Geben Sie im Feld **Servername** den Server ein, auf dem sich die Datenbank **AdventureWorks2008** befindet.</span><span class="sxs-lookup"><span data-stu-id="35475-115">In the **Server name** box, enter the server where the **AdventureWorks2008** database is located.</span></span>  
  
         <span data-ttu-id="35475-116">Die SQL Server Express-Standardinstanz lautet **(local)\sqlexpress**.</span><span class="sxs-lookup"><span data-stu-id="35475-116">The default SQL Server Express instance is **(local)\sqlexpress**.</span></span>  
  
    2.  <span data-ttu-id="35475-117">Wählen Sie im Abschnitt **Am Server anmelden** die Option aus, die Ihnen den Zugriff auf die Daten ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="35475-117">In the **Log on to the server** section, select the option that provides you access to the data.</span></span> <span data-ttu-id="35475-118">Die Standardeinstellung ist**Windows-Authentifizierung verwenden** .</span><span class="sxs-lookup"><span data-stu-id="35475-118">**Use Windows Authentication** is the default.</span></span>  
  
    3.  <span data-ttu-id="35475-119">Klicken Sie in der Dropdown Liste **Datenbanknamen eingeben oder auswählen** auf **AdventureWorks2008**.</span><span class="sxs-lookup"><span data-stu-id="35475-119">From the **Select or enter a database name** drop-down list, click **AdventureWorks2008**.</span></span>  
  
    4.  <span data-ttu-id="35475-120">Klicken Sie auf **OK**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="35475-120">Click **OK**, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="35475-121">Wenn Sie in Schritt 5 (b) **SQL Server-Authentifizierung verwenden** ausgewählt haben, legen Sie fest, ob die vertraulichen Daten in die Zeichenfolge eingeschlossen oder ob die Informationen im Anwendungscode festgelegt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="35475-121">If you selected **Use SQL Server Authentication** in Step 5 (b), select the option whether to include the sensitive data in the string or set the information in your application code.</span></span>  
  
7.  <span data-ttu-id="35475-122">Geben Sie auf der Seite **Verbindungszeichenfolge in der Anwendungskonfigurationsdatei speichern** den Namen der Verbindungszeichenfolge ein, oder übernehmen Sie den Standardwert **AdventureWorks2008ConnectionString**.</span><span class="sxs-lookup"><span data-stu-id="35475-122">On the **Save the Connection String to the Application Configuration File** page, type in the name for the connection string or accept the default **AdventureWorks2008ConnectionString**.</span></span> <span data-ttu-id="35475-123">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="35475-123">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="35475-124">Wählen Sie auf der Seite **Wählen Sie einen Befehlstyp aus** die Option **SQL-Anweisungen verwenden**aus, und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="35475-124">On the **Choose a Command Type** page, select **Use SQL Statements**, and then click **Next**.</span></span>  
  
9. <span data-ttu-id="35475-125">Geben Sie auf der Seite **SQL-Anweisung eingeben** die folgende Transact-SQL-Abfrage zum Abrufen von Daten aus der **AdventureWorks2008** -Datenbank ein, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="35475-125">On the **Enter a SQL Statement** page, enter the following Transact-SQL query to retrieve data from the **AdventureWorks2008** database, and then click **Next**.</span></span>  
  
    ```  
    SELECT PurchaseOrderID, PurchaseOrderDetailID, OrderQty, ProductID, ReceivedQty, RejectedQty, StockedQty FROM Purchasing.PurchaseOrderDetail  
    ```  
  
     <span data-ttu-id="35475-126">Sie können die Abfrage auch erstellen, indem Sie auf den **Abfrage-Generator**klicken. Überprüfen Sie die Abfrage dann, indem Sie auf die Schaltfläche **Abfrage ausführen** klicken.</span><span class="sxs-lookup"><span data-stu-id="35475-126">You can also create the query by clicking **Query Builder**, and then verify the query by clicking **Execute Query** button.</span></span> <span data-ttu-id="35475-127">Wenn die Abfrage nicht die erwarteten Daten zurückgibt, verwenden Sie möglicherweise eine frühere Version von AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="35475-127">If the query does not return the expected data, you might be using an earlier version of AdventureWorks.</span></span> <span data-ttu-id="35475-128">Weitere Informationen zum Installieren der **AdventureWorks2008** -Version von AdventureWorks finden Sie unter [Anleitung: Installieren der AdventureWorks-Datenbank](https://msdn.microsoft.com/library/aa992075\(v=vs.100\).aspx).</span><span class="sxs-lookup"><span data-stu-id="35475-128">For more information about installing the **AdventureWorks2008** version of AdventureWorks, see [Walkthrough: Installing the AdventureWorks Database](https://msdn.microsoft.com/library/aa992075\(v=vs.100\).aspx).</span></span>  
  
10. <span data-ttu-id="35475-129">Deaktivieren Sie auf der Seite **zu generierende Methode auswählen** die Option **Methoden erstellen, um Updates direkt an die Datenbank zu senden (GenerateDBDirectMethods)**, und klicken Sie dann auf **Fertig**stellen.</span><span class="sxs-lookup"><span data-stu-id="35475-129">On the **Choose Methods to Generate** page, uncheck **Create methods to send updates directly to the database (GenerateDBDirectMethods)**, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="35475-130">Die Konfiguration der ADO.NET [DataTable](https://msdn.microsoft.com/library/system.data.datatable\(v=vs.100\).aspx) als Datenquelle für Ihren Bericht ist jetzt abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="35475-130">You have now completed configuring the ADO.NET [DataTable](https://msdn.microsoft.com/library/system.data.datatable\(v=vs.100\).aspx) as data source for your report.</span></span> <span data-ttu-id="35475-131">Auf der DataSet-Designer-Seite in Visual Studio sollte die hinzugefügte **DataTable** jetzt mit den in der Abfrage angegebenen Spalten aufgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="35475-131">On the DataSet Designer page in Visual Studio, you should see the **DataTable** you added, listing the columns specified in the query.</span></span> <span data-ttu-id="35475-132">DataSet2 enthält die auf der Abfrage basierenden Daten aus der PurchaseOrderDetail-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="35475-132">DataSet2 contains the data from the PurhcaseOrderDetail table, based on the query.</span></span>  
  
11. <span data-ttu-id="35475-133">Speichern Sie die Datei .</span><span class="sxs-lookup"><span data-stu-id="35475-133">Save the file.</span></span>  
  
12. <span data-ttu-id="35475-134">Um die Daten in der Vorschau anzuzeigen, klicken Sie im Menü **Daten** auf **Datenvorschau** , und klicken Sie dann auf **Vorschau**.</span><span class="sxs-lookup"><span data-stu-id="35475-134">To preview the data, click **Preview Data** on the **Data** menu, and then click **Preview**.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="35475-135">Nächste Aufgabe</span><span class="sxs-lookup"><span data-stu-id="35475-135">Next Task</span></span>  
 <span data-ttu-id="35475-136">Sie haben erfolgreich eine Datenverbindung und eine Datentabelle für den untergeordneten Bericht erstellt.</span><span class="sxs-lookup"><span data-stu-id="35475-136">You have successfully created a data connection and data table for the child report.</span></span> <span data-ttu-id="35475-137">Als Nächstes entwerfen Sie den untergeordneten Bericht mithilfe des Berichts-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="35475-137">Next, you will design the child report using the Report Wizard.</span></span>  
  
  
