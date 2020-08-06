---
title: 'Aufgabe 2: Hochladen von Lieferantendaten in MDS mithilfe MDS-Add-in für Excel | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 598deb57-e0cc-4e0a-aeb1-94432c094c67
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 16c5fa9db81649b30c12fae4d2e57afa8bf094e8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608152"
---
# <a name="task-2-uploading-supplier-data-to-mds-using-mds-add-in-for-excel"></a><span data-ttu-id="10aa7-102">Aufgabe 2: Hochladen von Lieferantendaten in MDS mithilfe des MDS-Add-Ins für Excel</span><span class="sxs-lookup"><span data-stu-id="10aa7-102">Task 2: Uploading Supplier Data to MDS using MDS Add-in for Excel</span></span>
  <span data-ttu-id="10aa7-103">In dieser Aufgabe veröffentlichen Sie die bereinigten und Lieferantendaten mithilfe der **MDS-Add-in für Excel**in **MDS** .</span><span class="sxs-lookup"><span data-stu-id="10aa7-103">In this task, you publish the cleansed and supplier data to **MDS** using the **MDS Add-in for Excel**.</span></span> <span data-ttu-id="10aa7-104">Sie erstellen eine Entität mit dem Namen **Lieferant** in dem Modell **Suppliers** , das Sie in der vorherigen Lektion erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="10aa7-104">You create an entity named **Supplier** in the **Suppliers** model you created in the previous lesson.</span></span> <span data-ttu-id="10aa7-105">Die Entität weist ein Attribut für jede Spalte in der Excel-Datei auf.</span><span class="sxs-lookup"><span data-stu-id="10aa7-105">The entity will have an attribute for each column in the Excel file.</span></span> <span data-ttu-id="10aa7-106">Die Attribute "Code" und "Name" der Entität "Supplier" entsprechen den Spalten **SupplierID** und **Supplier Name** in Excel.</span><span class="sxs-lookup"><span data-stu-id="10aa7-106">The Code and Name attributes of the Supplier entity correspond to the **SupplierID** and **Supplier Name** columns in Excel.</span></span>  
  
1.  <span data-ttu-id="10aa7-107">Öffnen Sie **bereinigt und abgeglichen Suppliers.xls** in **Excel**.</span><span class="sxs-lookup"><span data-stu-id="10aa7-107">Open **Cleansed and Matched Suppliers.xls** in **Excel**.</span></span>  
  
2.  <span data-ttu-id="10aa7-108">Drücken Sie **STRG + A** , um die gesamten Daten auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="10aa7-108">Press **CTRL+A** to select entire data.</span></span> <span data-ttu-id="10aa7-109">Es ist **wichtig** , dass Sie die gesamten Daten in der Tabelle auswählen.</span><span class="sxs-lookup"><span data-stu-id="10aa7-109">It is **important** that you select the entire data in the spreadsheet.</span></span>  
  
3.  <span data-ttu-id="10aa7-110">Klicken Sie in der Menüleiste auf **Master Daten** .</span><span class="sxs-lookup"><span data-stu-id="10aa7-110">Click **Master Data** on the menu bar.</span></span>  
  
4.  <span data-ttu-id="10aa7-111">Klicken Sie im Menüband auf Schaltfläche **Entität erstellen** .</span><span class="sxs-lookup"><span data-stu-id="10aa7-111">Click **Create Entity** button on the ribbon.</span></span>  
  
     <span data-ttu-id="10aa7-112">![Excel – Masterdaten (Registerkarte) – Entität erstellen (Schaltfläche)](../../2014/tutorials/media/et-ulingsdtomdsusingmdsaddinforexcel-01.jpg "Excel – Masterdaten (Registerkarte) – Entität erstellen (Schaltfläche)")</span><span class="sxs-lookup"><span data-stu-id="10aa7-112">![Excel - Master Data Tab - Create Entity Button](../../2014/tutorials/media/et-ulingsdtomdsusingmdsaddinforexcel-01.jpg "Excel - Master Data Tab - Create Entity Button")</span></span>  
  
5.  <span data-ttu-id="10aa7-113">Wenn im Dialogfeld **Verbindungen verwalten** die Verbindung mit dem **lokalen MDS-Server** unter **vorhandene Verbindungen**nicht angezeigt wird, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="10aa7-113">In **Manage Connections** dialog box, if you do not see the connection to **local MDS server** under **Existing connections**, do the following:</span></span>  
  
    1.  <span data-ttu-id="10aa7-114">Wählen Sie **neue Verbindung erstellen**aus, und klicken Sie auf die Schaltfläche **neu** .</span><span class="sxs-lookup"><span data-stu-id="10aa7-114">Select **Create a new connection**, and click **New** button.</span></span>  
  
    2.  <span data-ttu-id="10aa7-115">Geben Sie im Dialogfeld **neue Verbindung hinzufügen** den **Namen local MDS Server** for **Description** und **http: \/ /localhost/MDS** für die **MDS-Server Adresse**ein, und klicken Sie auf **OK** , um das Dialogfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="10aa7-115">In the **Add New Connection** dialog box, type **Local MDS Server** for **Description** and **http:\//localhost/MDS** for **MDS server address**, and click **OK** to close the dialog box.</span></span>  
  
6.  <span data-ttu-id="10aa7-116">Wählen Sie im Dialogfeld **Verbindungen verwalten** die Option **lokaler MDS-Server** ( `http://localhost/MDS` ) aus, klicken Sie auf **Testen** , um die Verbindung zu testen.</span><span class="sxs-lookup"><span data-stu-id="10aa7-116">In **Manage Connections** dialog box, select **Local MDS Server** (`http://localhost/MDS`), click **Test** to test the connection.</span></span> <span data-ttu-id="10aa7-117">Klicken Sie im Meldungs Feld auf **OK** .</span><span class="sxs-lookup"><span data-stu-id="10aa7-117">Click **OK** on the message box.</span></span>  
  
7.  <span data-ttu-id="10aa7-118">Klicken Sie auf **verbinden** , um eine Verbindung zum MDS-Server herzustellen.</span><span class="sxs-lookup"><span data-stu-id="10aa7-118">Click **Connect** to connect to the MDS server.</span></span>  
  
8.  <span data-ttu-id="10aa7-119">Wählen Sie im Dialogfeld **Entität erstellen** die Option **Suppliers** für das **Modell**aus.</span><span class="sxs-lookup"><span data-stu-id="10aa7-119">In the **Create Entity** dialog box, select **Suppliers** for the **Model**.</span></span>  
  
9. <span data-ttu-id="10aa7-120">Stellen Sie sicher, dass für die **Version** **VERSION_1** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="10aa7-120">Ensure that **VERSION_1** is selected for **Version**.</span></span>  
  
10. <span data-ttu-id="10aa7-121">Geben Sie **Supplier** als **neuen Entitäts Namen**ein.</span><span class="sxs-lookup"><span data-stu-id="10aa7-121">Enter **Supplier** for **New entity name**.</span></span>  
  
11. <span data-ttu-id="10aa7-122">Wählen Sie **SupplierID** für **die Spalte aus, die ein eindeutiges Bezeichnerfeld enthält** (Sie können auch automatisch einen Code generieren).</span><span class="sxs-lookup"><span data-stu-id="10aa7-122">Select **SupplierID** for **the column that contains a unique identifier** field (you can also generate a code automatically).</span></span> <span data-ttu-id="10aa7-123">Sie ordnen die **SupplierID-** Spalte in **Excel** im Wesentlichen dem Attribut " **Code** " der Entität " **Supplier** " zu.</span><span class="sxs-lookup"><span data-stu-id="10aa7-123">You are essentially mapping the **SupplierID** column in **Excel** to the **Code** attribute of **Supplier** entity.</span></span>  
  
12. <span data-ttu-id="10aa7-124">Wählen Sie **Lieferanten Name** für **die Spalte aus, die das Feld Namen enthält** .</span><span class="sxs-lookup"><span data-stu-id="10aa7-124">Select **Supplier Name** for **the column that contains names** field.</span></span> <span data-ttu-id="10aa7-125">Im wesentlichen ordnen Sie die Spalte " **Supplier Name** " in **Excel** dem **namens** Attribut der Entität " **Supplier** " zu.</span><span class="sxs-lookup"><span data-stu-id="10aa7-125">You are essentially mapping the **Supplier Name** column in **Excel** to the **Name** attribute of the **Supplier** entity.</span></span> <span data-ttu-id="10aa7-126">Die Attribute " **Code** " und " **Name** " sind obligatorische Attribute für eine Entität in MDS.</span><span class="sxs-lookup"><span data-stu-id="10aa7-126">The **Code** and **Name** attributes are mandatory attributes for an entity in MDS.</span></span>  
  
     <span data-ttu-id="10aa7-127">![Entität erstellen (Dialogfeld)](../../2014/tutorials/media/et-ulingsdtomdsusingmdsaddinforexcel-02.jpg "Entität erstellen (Dialogfeld)")</span><span class="sxs-lookup"><span data-stu-id="10aa7-127">![Create Entity Dialog Box](../../2014/tutorials/media/et-ulingsdtomdsusingmdsaddinforexcel-02.jpg "Create Entity Dialog Box")</span></span>  
  
13. <span data-ttu-id="10aa7-128">Klicken Sie auf **OK** , um die Entität in MDS zu erstellen, die Master Daten in der Entität zu veröffentlichen und das Dialogfeld **Entität erstellen** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="10aa7-128">Click **OK** to create the entity on MDS, publish the master data to the entity, and close **Create Entity** dialog box.</span></span>  
  
14. <span data-ttu-id="10aa7-129">Nun sollte das neue Blatt **Lieferant**angezeigt werden, bei dem es sich um den Namen der Entität handelt, der dem Excel-Arbeitsblatt hinzugefügt wird. oben im Arbeitsblatt sollten Sie sehen, dass das Arbeitsblatt mit dem MDS-Server verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="10aa7-129">Now, you should see a new sheet titled **Supplier**, which is the name of the entity, added to your Excel spreadsheet and at the top of the worksheet you should see that the worksheet is connected to the MDS server.</span></span> <span data-ttu-id="10aa7-130">Beachten Sie, dass das ursprüngliche Arbeitsblatt (mit dem Namen **Sheet1**) noch vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="10aa7-130">Notice that the original worksheet (titled **Sheet1**) still exists.</span></span>  
  
     <span data-ttu-id="10aa7-131">![Excel – Registerkarten für Lieferanten und Tabelle1](../../2014/tutorials/media/et-ulingsdtomdsusingmdsaddinforexcel-03.jpg "Excel – Registerkarten für Lieferanten und Tabelle1")</span><span class="sxs-lookup"><span data-stu-id="10aa7-131">![Excel - Supplier and Sheet1 Tabs](../../2014/tutorials/media/et-ulingsdtomdsusingmdsaddinforexcel-03.jpg "Excel - Supplier and Sheet1 Tabs")</span></span>  
  
     <span data-ttu-id="10aa7-132">![Excel – Anzeigen von Details zur MDS-Verbindung](../../2014/tutorials/media/et-ulingsdtomdsusingmdsaddinforexcel-04.jpg "Excel – Anzeigen von Details zur MDS-Verbindung")</span><span class="sxs-lookup"><span data-stu-id="10aa7-132">![Excel - Showing MDS Connection Details](../../2014/tutorials/media/et-ulingsdtomdsusingmdsaddinforexcel-04.jpg "Excel - Showing MDS Connection Details")</span></span>  
  
15. <span data-ttu-id="10aa7-133">Lassen Sie **Excel** geöffnet.</span><span class="sxs-lookup"><span data-stu-id="10aa7-133">Keep **Excel** open.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="10aa7-134">Nächste Aufgabe</span><span class="sxs-lookup"><span data-stu-id="10aa7-134">Next Task</span></span>  
 [<span data-ttu-id="10aa7-135">Aufgabe 3: Überprüfen der Daten im Master Data Manager</span><span class="sxs-lookup"><span data-stu-id="10aa7-135">Task 3: Verifying the Data in Master Data Manager</span></span>](../../2014/tutorials/task-3-verifying-the-data-in-master-data-manager.md)  
  
  
