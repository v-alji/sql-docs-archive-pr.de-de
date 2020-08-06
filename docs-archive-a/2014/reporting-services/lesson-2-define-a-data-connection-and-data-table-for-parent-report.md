---
title: 'Lektion 2: Definieren einer Datenverbindung und einer Datentabelle für den untergeordneten Bericht | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f02dee0c-85ad-45d4-b707-10e9e8541db9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 045ff576061bf12d163668cb9a57651e591768a4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609035"
---
# <a name="lesson-2-define-a-data-connection-and-data-table-for-parent-report"></a><span data-ttu-id="2316e-102">Lektion 2: Definieren einer Datenverbindung und einer Datentabelle für den übergeordneten Bericht</span><span class="sxs-lookup"><span data-stu-id="2316e-102">Lesson 2: Define a Data Connection and Data Table for Parent Report</span></span>
  <span data-ttu-id="2316e-103">Nachdem Sie ein neues Websiteprojekt mithilfe der ASP.NET-Websitevorlage für Visual C# erstellt haben, erstellen Sie im nächsten Schritt eine Datenverbindung und eine Datentabelle für den übergeordneten Bericht.</span><span class="sxs-lookup"><span data-stu-id="2316e-103">After you create a new website project using the ASP.NET website template for Visual C#, your next step is to create a data connection and a data table for the parent report.</span></span> <span data-ttu-id="2316e-104">In diesem Lernprogramm wird eine Datenverbindung mit der AdventureWorks2008-Datenbank hergestellt.</span><span class="sxs-lookup"><span data-stu-id="2316e-104">In this tutorial the data connection is to the AdventureWorks2008 database.</span></span> <span data-ttu-id="2316e-105">Alternativ können Sie auch eine Verbindung mit der AdventureWorks2012-Datenbank herstellen.</span><span class="sxs-lookup"><span data-stu-id="2316e-105">You also have the option of connecting to the AdventureWorks2012 database.</span></span>  
  
### <a name="to-define-a-data-connection-and-data-table-by-adding-a-dataset-for-parent-report"></a><span data-ttu-id="2316e-106">So definieren Sie eine Datenverbindung und eine Datentabelle durch Hinzufügen eines Datasets (für den übergeordneten Bericht)</span><span class="sxs-lookup"><span data-stu-id="2316e-106">To define a data connection and Data Table by adding a DataSet (for parent report)</span></span>  
  
1.  <span data-ttu-id="2316e-107">Wählen Sie im Menü **Website** die Option **Neues Element hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="2316e-107">On the **Website** menu, select **Add New Item**.</span></span>  
  
2.  <span data-ttu-id="2316e-108">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **DataSet** aus, und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="2316e-108">In the **Add New Item** dialog box, select **DataSet** and click **Add**.</span></span> <span data-ttu-id="2316e-109">Wenn Sie dazu aufgefordert werden, sollten Sie das Element dem Ordner **App_Code** hinzufügen, indem Sie auf **Ja**klicken.</span><span class="sxs-lookup"><span data-stu-id="2316e-109">When prompted you should add the item to the **App_Code** folder by clicking **Yes**.</span></span>  
  
     <span data-ttu-id="2316e-110">Dadurch wird dem Projekt die neue XSD-Datei **DataSet1.xsd** hinzugefügt und der DataSet-Designer geöffnet.</span><span class="sxs-lookup"><span data-stu-id="2316e-110">This adds a new XSD file **DataSet1.xsd** to the project and opens the DataSet Designer.</span></span>  
  
3.  <span data-ttu-id="2316e-111">Ziehen Sie aus dem Fenster Toolbox ein **[TableAdapter](https://msdn.microsoft.com/library/bz9tthwx\(v=vs.100\).aspx)** -Steuerelement auf die Entwurfs Oberfläche.</span><span class="sxs-lookup"><span data-stu-id="2316e-111">From the Toolbox window, drag a **[TableAdapter](https://msdn.microsoft.com/library/bz9tthwx\(v=vs.100\).aspx)** control to the design surface.</span></span> <span data-ttu-id="2316e-112">Dadurch wird der Konfigurations-Assistent **TableAdapter** gestartet.</span><span class="sxs-lookup"><span data-stu-id="2316e-112">This launches the **TableAdapter** Configuration Wizard.</span></span>  
  
4.  <span data-ttu-id="2316e-113">Klicken Sie auf der Seite **Wählen Sie Ihre Datenverbindung aus** auf **Neue Verbindung**.</span><span class="sxs-lookup"><span data-stu-id="2316e-113">On the **Choose Your Data Connection** page, click **New Connection**.</span></span>  
  
5.  <span data-ttu-id="2316e-114">Wenn Sie zum ersten Mal eine Datenquelle in Visual Studio erstellt haben, wird die Seite **Datenquelle auswählen** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2316e-114">If this is the first time you've created a data source in Visual Studio, you will see the **Choose Data Source** page.</span></span> <span data-ttu-id="2316e-115">Wählen Sie im Feld **Datenquelle** die Option **Microsoft SQL Server**aus.</span><span class="sxs-lookup"><span data-stu-id="2316e-115">In the **Data Source** box, select **Microsoft SQL Server**.</span></span>  
  
6.  <span data-ttu-id="2316e-116">Führen Sie im Dialogfeld **Verbindung hinzufügen** die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="2316e-116">In the **Add Connection** dialog box, perform the following steps:</span></span>  
  
    1.  <span data-ttu-id="2316e-117">Geben Sie im Feld **Servername** den Server ein, auf dem sich die Datenbank **AdventureWorks2008** befindet.</span><span class="sxs-lookup"><span data-stu-id="2316e-117">In the **Server name** box, enter the server where the **AdventureWorks2008** database is located.</span></span>  
  
         <span data-ttu-id="2316e-118">Die SQL Server Express-Standardinstanz lautet **(local)\sqlexpress**.</span><span class="sxs-lookup"><span data-stu-id="2316e-118">The default SQL Server Express instance is **(local)\sqlexpress**.</span></span>  
  
    2.  <span data-ttu-id="2316e-119">Wählen Sie im Abschnitt **Am Server anmelden** die Option aus, die Ihnen den Zugriff auf die Daten ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="2316e-119">In the **Log on to the server** section, select the option that provides you access to the data.</span></span> <span data-ttu-id="2316e-120">Die Standardeinstellung ist**Windows-Authentifizierung verwenden** .</span><span class="sxs-lookup"><span data-stu-id="2316e-120">**Use Windows Authentication** is the default.</span></span>  
  
    3.  <span data-ttu-id="2316e-121">Klicken Sie in der Dropdown Liste **Datenbanknamen eingeben oder auswählen** auf **AdventureWorks2008**.</span><span class="sxs-lookup"><span data-stu-id="2316e-121">From the **Select or enter a database name** drop-down list, click **AdventureWorks2008**.</span></span>  
  
    4.  <span data-ttu-id="2316e-122">Klicken Sie auf **OK**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="2316e-122">Click **OK**, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="2316e-123">Wenn Sie in Schritt 6 (b) **SQL Server-Authentifizierung verwenden** ausgewählt haben, legen Sie fest, ob die vertraulichen Daten in die Zeichenfolge eingeschlossen oder ob die Informationen im Anwendungscode festgelegt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="2316e-123">If you selected **Use SQL Server Authentication** in the Step 6 (b), select the option whether to include the sensitive data in the string or set the information in your application code.</span></span>  
  
8.  <span data-ttu-id="2316e-124">Geben Sie auf der Seite **Verbindungszeichenfolge in der Anwendungskonfigurationsdatei speichern** den Namen der Verbindungszeichenfolge ein, oder übernehmen Sie den Standardwert **AdventureWorks2008ConnectionString**.</span><span class="sxs-lookup"><span data-stu-id="2316e-124">On the **Save the Connection String to the Application Configuration File** page, type in the name for the connection string or accept the default **AdventureWorks2008ConnectionString**.</span></span> <span data-ttu-id="2316e-125">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="2316e-125">Click **Next**.</span></span>  
  
9. <span data-ttu-id="2316e-126">Wählen Sie auf der Seite **Wählen Sie einen Befehlstyp aus** die Option **SQL-Anweisungen verwenden**aus, und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="2316e-126">On the **Choose a Command Type** page, select **Use SQL Statements**, and then click **Next**.</span></span>  
  
10. <span data-ttu-id="2316e-127">Geben Sie auf der Seite **SQL-Anweisung eingeben** die folgende Transact-SQL-Abfrage zum Abrufen von Daten aus der **AdventureWorks2008** -Datenbank ein, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="2316e-127">On the **Enter a SQL Statement** page, enter the following Transact-SQL query to retrieve data from the **AdventureWorks2008** database, and then click **Next**.</span></span>  
  
    ```  
    SELECT ProductID, Name, ProductNumber, SafetyStockLevel, ReorderPoint FROM  Production.Product Order By ProductID  
    ```  
  
     <span data-ttu-id="2316e-128">Sie können die Abfrage auch erstellen, indem Sie auf **Abfrage-Generator**klicken. Überprüfen Sie anschließend die Abfrage, indem Sie auf **Abfrage ausführen**klicken.</span><span class="sxs-lookup"><span data-stu-id="2316e-128">You can also create the query by clicking **Query Builder**, and then verify the query by clicking **Execute Query**.</span></span> <span data-ttu-id="2316e-129">Wenn die Abfrage nicht die erwarteten Daten zurückgibt, verwenden Sie möglicherweise eine frühere Version von AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="2316e-129">If the query does not return the expected data, you might be using an earlier version of AdventureWorks.</span></span> <span data-ttu-id="2316e-130">Weitere Informationen zum Installieren der **AdventureWorks2008** -Version von AdventureWorks finden Sie unter [Anleitung: Installieren der AdventureWorks-Datenbank](https://msdn.microsoft.com/library/aa992075\(v=vs.100\).aspx).</span><span class="sxs-lookup"><span data-stu-id="2316e-130">For more information about installing the **AdventureWorks2008** version of AdventureWorks, see [Walkthrough: Installing the AdventureWorks Database](https://msdn.microsoft.com/library/aa992075\(v=vs.100\).aspx).</span></span>  
  
11. <span data-ttu-id="2316e-131">Deaktivieren Sie auf der Seite **zu generierende Methode auswählen** die Option **Methoden erstellen, um Updates direkt an die Datenbank zu senden (GenerateDBDirectMethods)**, und klicken Sie dann auf **Fertig**stellen.</span><span class="sxs-lookup"><span data-stu-id="2316e-131">On the **Choose Methods to Generate** page, be sure to uncheck **Create methods to send updates directly to the database (GenerateDBDirectMethods)**, and then click **Finish**.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="2316e-132">Die Option Erstellen muss deaktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="2316e-132">Be sure to uncheck Create</span></span>  
  
     <span data-ttu-id="2316e-133">Die Konfiguration des ADO.NET DataTable-Objekts als Datenquelle für Ihren Bericht ist jetzt abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="2316e-133">You have now completed configuring the ADO.NET DataTable object as the data source for your report.</span></span> <span data-ttu-id="2316e-134">Auf der DataSet-Designer-Seite in Visual Studio sollte das hinzugefügte DataTable-Objekt jetzt mit den in der Abfrage angegebenen Spalten aufgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2316e-134">On the DataSet Designer page in Visual Studio, you should see the DataTable object you added, listing the columns specified in the query.</span></span> <span data-ttu-id="2316e-135">DataSet1 enthält die Daten aus der Product-Tabelle basierend auf der Abfrage.</span><span class="sxs-lookup"><span data-stu-id="2316e-135">DataSet1 contains the data from the Product table, based on the query.</span></span>  
  
12. <span data-ttu-id="2316e-136">Speichern Sie die Datei .</span><span class="sxs-lookup"><span data-stu-id="2316e-136">Save the file.</span></span>  
  
13. <span data-ttu-id="2316e-137">Um die Daten in der Vorschau anzuzeigen, klicken Sie im Menü **Daten** auf **Datenvorschau** , und klicken Sie dann auf **Vorschau**.</span><span class="sxs-lookup"><span data-stu-id="2316e-137">To preview the data, click **Preview Data** on the **Data** menu, and then click **Preview**.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="2316e-138">Nächste Aufgabe</span><span class="sxs-lookup"><span data-stu-id="2316e-138">Next Task</span></span>  
 <span data-ttu-id="2316e-139">Sie haben erfolgreich eine Datenverbindung und eine Datentabelle für den übergeordneten Bericht erstellt.</span><span class="sxs-lookup"><span data-stu-id="2316e-139">You have successfully created a data connection and a data table for the parent report.</span></span> <span data-ttu-id="2316e-140">Als Nächstes erstellen Sie den übergeordneten Bericht mithilfe des Berichts-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="2316e-140">Next, you will design the parent report using the Report Wizard.</span></span>  
  
  
