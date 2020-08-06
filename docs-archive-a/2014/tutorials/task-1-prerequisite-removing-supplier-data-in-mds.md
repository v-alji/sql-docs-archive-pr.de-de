---
title: 'Aufgabe 1 (Voraussetzung): Entfernen von Lieferantendaten in MDS | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 6f0a4287-7fd4-4f18-b7e4-a5191a9d4a3c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: e78dc5ff04f95d42cf440e3f80b1b349e0315a69
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620698"
---
# <a name="task-1-prerequisite-removing-supplier-data-in-mds"></a><span data-ttu-id="54231-102">Aufgabe 1 (Voraussetzung): Entfernen von Lieferantendaten aus MDS</span><span class="sxs-lookup"><span data-stu-id="54231-102">Task 1 (Prerequisite): Removing Supplier Data in MDS</span></span>
  <span data-ttu-id="54231-103">In dieser Aufgabe entfernen Sie die Lieferantendaten, die in MDS gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="54231-103">In this task, you remove the supplier data stored in MDS.</span></span> <span data-ttu-id="54231-104">Sie haben die Daten in der vorherigen Lektion manuell mithilfe des **MDS-Excel-Add-ins** hochgeladen.</span><span class="sxs-lookup"><span data-stu-id="54231-104">You uploaded the data manually using **MDS Excel Add-in** in the previous lesson.</span></span> <span data-ttu-id="54231-105">Das SSIS-Paket, das Sie in dieser Lektion erstellen, lädt die Daten für Sie automatisch in MDS hoch.</span><span class="sxs-lookup"><span data-stu-id="54231-105">The SSIS package you create in this lesson will automatically upload the data to MDS for you.</span></span> <span data-ttu-id="54231-106">Bevor Sie das SSIS-Paket testen, müssen Sie daher die Lieferantendaten aus MDS entfernen, die abgeleitete Hierarchie entfernen, die Entitäten "Supplier" und "State" entfernen und die Entität "Supplier" ohne Daten erstellen.</span><span class="sxs-lookup"><span data-stu-id="54231-106">Therefore, before testing the SSIS package, you need to remove the supplier data from MDS, remove the derived hierarchy, remove supplier and state entities, and create the supplier entity with no data.</span></span>  
  
1.  <span data-ttu-id="54231-107">Starten Sie **Master Data Manager** , indem `http://localhost/MDS` Sie zu oder der Website und Anwendung navigieren, die Sie beim Konfigurieren von MDS angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="54231-107">Launch **Master Data Manager** by navigating to `http://localhost/MDS` or the website and application you specified when configuring MDS.</span></span> <span data-ttu-id="54231-108">Wenn Sie die **Master Data Manager** geöffnet gehalten haben, klicken Sie oben auf **SQL Server 2012 Master Data Services** , um zur **Startseite**zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="54231-108">If you kept the **Master Data Manager** open, click **SQL Server 2012 Master Data Services** at the top to switch to the **home page**.</span></span>  
  
2.  <span data-ttu-id="54231-109">Klicken Sie im Abschnitt **administrative Aufgaben** auf **System Verwaltung** .</span><span class="sxs-lookup"><span data-stu-id="54231-109">Click **System Administration** in the **Administrative Tasks** section.</span></span>  
  
3.  <span data-ttu-id="54231-110">Zeigen Sie mit der Maus auf **Verwalten** im Menü, und klicken Sie auf **abgeleitete Hierarchien**.</span><span class="sxs-lookup"><span data-stu-id="54231-110">Hover the mouse over **Manage** on the menu and click **Derived Hierarchies**.</span></span> <span data-ttu-id="54231-111">Sie müssen die abgeleitete Hierarchie **suppliersinstate** löschen, bevor Sie die Entitäten im Modell **Suppliers** löschen.</span><span class="sxs-lookup"><span data-stu-id="54231-111">You need to delete the derived hierarchy **SuppliersInState** before deleting the entities in the **Suppliers** model.</span></span>  
  
4.  <span data-ttu-id="54231-112">Wählen Sie in der Liste **abgeleitete Hierarchie** den Eintrag **suppliersinstate** aus, und klicken Sie auf der Symbolleiste auf die Schaltfläche **X**</span><span class="sxs-lookup"><span data-stu-id="54231-112">Select **SuppliersInState** from the **Derived Hierarchy** list and click **X (Delete)** button on the toolbar.</span></span>  
  
5.  <span data-ttu-id="54231-113">Klicken Sie zum Bestätigen des Löschvorgangs auf **OK** .</span><span class="sxs-lookup"><span data-stu-id="54231-113">Click **OK** to confirm deletion.</span></span>  
  
6.  <span data-ttu-id="54231-114">Zeigen Sie mit der Maus auf **Verwalten** im Menü, und klicken Sie auf **Entitäten**.</span><span class="sxs-lookup"><span data-stu-id="54231-114">Hover the mouse over **Manage** on the menu and click **Entities**.</span></span>  
  
7.  <span data-ttu-id="54231-115">Klicken **Sie in** der Symbolleiste auf die Schaltfläche **Löschen (X)** , um die Entität zu löschen.</span><span class="sxs-lookup"><span data-stu-id="54231-115">Click **Supplier** and click **Delete (X)** button on toolbar to delete the entity.</span></span> <span data-ttu-id="54231-116">Klicken Sie in den Meldungs Feldern auf **OK** .</span><span class="sxs-lookup"><span data-stu-id="54231-116">Click **OK** on message boxes.</span></span>  
  
8.  <span data-ttu-id="54231-117">Wiederholen Sie den vorherigen Schritt zum Löschen der **Zustands** Entität.</span><span class="sxs-lookup"><span data-stu-id="54231-117">Repeat the previous step to delete **State** entity.</span></span>  
  
9. <span data-ttu-id="54231-118">Schließen Sie **Master Data Manager**nicht.</span><span class="sxs-lookup"><span data-stu-id="54231-118">Don't close **Master Data Manager**.</span></span>  
  
10. <span data-ttu-id="54231-119">Wechseln Sie zum Excel-Fenster, das **bereinigt wurde und Suppliers.xls** Datei geöffnet wurde.</span><span class="sxs-lookup"><span data-stu-id="54231-119">Switch to the Excel window that has **Cleansed and Matched Suppliers.xls** file open.</span></span> <span data-ttu-id="54231-120">Wechseln Sie im unteren Bereich zur Registerkarte **Sheet1** .</span><span class="sxs-lookup"><span data-stu-id="54231-120">Switch to the **Sheet1** tab at the bottom.</span></span>  
  
11. <span data-ttu-id="54231-121">Wählen Sie nur die **erste Zeile mit Headern**aus.</span><span class="sxs-lookup"><span data-stu-id="54231-121">Select only the **first row with headers**.</span></span> <span data-ttu-id="54231-122">Wählen Sie keine andere Zeile aus.</span><span class="sxs-lookup"><span data-stu-id="54231-122">Don't select any other row.</span></span> <span data-ttu-id="54231-123">Sie möchten die Entitäten auf der Grundlage der Excel-Spalten erstellen, aber keine Daten hochladen.</span><span class="sxs-lookup"><span data-stu-id="54231-123">You want to create the entities based on the Excel columns but don't want to upload any data.</span></span> <span data-ttu-id="54231-124">Daher wählen Sie nur die erste Zeile mit den Headern aus.</span><span class="sxs-lookup"><span data-stu-id="54231-124">Therefore you select only the first row with the headers.</span></span>  
  
12. <span data-ttu-id="54231-125">Klicken Sie in der Menüleiste auf **Master Daten** .</span><span class="sxs-lookup"><span data-stu-id="54231-125">Click **Master Data** on the menu bar.</span></span>  
  
13. <span data-ttu-id="54231-126">Klicken Sie im Menüband auf **Entität erstellen** .</span><span class="sxs-lookup"><span data-stu-id="54231-126">Click **Create Entity** from the ribbon.</span></span>  
  
14. <span data-ttu-id="54231-127">Wenn im Dialogfeld **Verbindungen verwalten** die Verbindung mit dem **lokalen MDS-Server** unter **vorhandene Verbindungen**nicht angezeigt wird, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="54231-127">In **Manage Connections** dialog box, if you do not see the connection to **local MDS server** under **Existing connections**, do the following:</span></span>  
  
    1.  <span data-ttu-id="54231-128">Wählen Sie **neue Verbindung erstellen**aus, und klicken Sie auf die Schaltfläche **neu** .</span><span class="sxs-lookup"><span data-stu-id="54231-128">Select **Create a new connection**, and click **New** button.</span></span>  
  
    2.  <span data-ttu-id="54231-129">Geben Sie im Dialogfeld neue Verbindung hinzufügen den **Namen local MDS Server** for **Description** und **http: \/ /localhost/MDS** für die **MDS-Server Adresse**ein, und klicken Sie auf **OK** , um das Dialogfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="54231-129">In the Add New Connection dialog box, type **Local MDS Server** for **Description** and **http:\//localhost/MDS** for **MDS server address**, and click **OK** to close the dialog box.</span></span>  
  
15. <span data-ttu-id="54231-130">Wählen Sie im Dialogfeld **Verbindungen verwalten** die Option **lokaler MDS-Server** ( `http://localhost/MDS` ) aus, klicken Sie auf **Testen** , um die Verbindung zu testen.</span><span class="sxs-lookup"><span data-stu-id="54231-130">In **Manage Connections** dialog box, select **Local MDS Server** (`http://localhost/MDS`), click **Test** to test the connection.</span></span> <span data-ttu-id="54231-131">Klicken Sie im Meldungs Feld auf **OK** .</span><span class="sxs-lookup"><span data-stu-id="54231-131">Click **OK** on the message box.</span></span>  
  
16. <span data-ttu-id="54231-132">Klicken Sie auf **verbinden** , um eine Verbindung mit dem MDS-Server herzustellen.</span><span class="sxs-lookup"><span data-stu-id="54231-132">Click **Connect** to make a connection to the MDS server.</span></span>  
  
17. <span data-ttu-id="54231-133">Führen Sie im Dialogfeld **Entität erstellen** die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="54231-133">In the **Create Entity** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="54231-134">Vergewissern Sie sich, dass der **Bereich** auf **$1: $1**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="54231-134">Confirm that **Range** is set to **$1:$1**.</span></span>  
  
    2.  <span data-ttu-id="54231-135">Wählen Sie **Suppliers** für **Model**aus.</span><span class="sxs-lookup"><span data-stu-id="54231-135">Select **Suppliers** for **Model**.</span></span>  
  
    3.  <span data-ttu-id="54231-136">Wählen Sie **VERSION_1** für die **Version**aus.</span><span class="sxs-lookup"><span data-stu-id="54231-136">Select **VERSION_1** for **Version**.</span></span>  
  
    4.  <span data-ttu-id="54231-137">Geben Sie **Supplier** als **neuen Entitäts Namen**ein.</span><span class="sxs-lookup"><span data-stu-id="54231-137">Type **Supplier** for **New entity name**.</span></span>  
  
    5.  <span data-ttu-id="54231-138">Wählen Sie **SupplierID** für **Code**aus.</span><span class="sxs-lookup"><span data-stu-id="54231-138">Select **SupplierID** for **Code**.</span></span>  
  
    6.  <span data-ttu-id="54231-139">Wählen Sie **Lieferanten Name** für **Name**aus.</span><span class="sxs-lookup"><span data-stu-id="54231-139">Select **Supplier Name** for **Name**.</span></span>  
  
    7.  <span data-ttu-id="54231-140">Klicken Sie auf **OK** , um die Entität zu erstellen und das Dialogfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="54231-140">Click **OK** to create the entity and close the dialog box.</span></span>  
  
18. <span data-ttu-id="54231-141">Schließen Sie **Excel** , und **Speichern Sie** die Datei nicht.</span><span class="sxs-lookup"><span data-stu-id="54231-141">Close **Excel** and **do not save** the file.</span></span>  
  
19. <span data-ttu-id="54231-142">Aktualisieren Sie in **Master Data Manager**den Internetbrowser, und vergewissern Sie sich, dass die Entität **Supplier** in der Liste angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="54231-142">In **Master Data Manager**, refresh the internet browser and confirm that **Supplier** entity is displayed in the list.</span></span>  
  
20. <span data-ttu-id="54231-143">Wechseln Sie zur **Startseite** , indem Sie oben auf **SQL Server 2012 Master Data Services** klicken.</span><span class="sxs-lookup"><span data-stu-id="54231-143">Switch to the **home page** by clicking **SQL Server 2012 Master Data Services** at the top.</span></span>  
  
21. <span data-ttu-id="54231-144">Vergewissern Sie sich, dass das Modell **Suppliers** als **Modell** ausgewählt ist und **VERSION_1** für die **Version**ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="54231-144">Confirm that **Suppliers** model is selected for **Model** and **VERSION_1** is selected for **Version**.</span></span>  
  
22. <span data-ttu-id="54231-145">Klicken Sie auf **Explorer**.</span><span class="sxs-lookup"><span data-stu-id="54231-145">Click **Explorer**.</span></span> <span data-ttu-id="54231-146">Beachten Sie, dass die Entität " **Supplier** " mit allen Attributen **ohne Werte**erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="54231-146">Notice that the **Supplier** entity with all the attributes is created with **no values**.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="54231-147">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="54231-147">Next Step</span></span>  
 [<span data-ttu-id="54231-148">Aufgabe 2 &#40;optionale&#41;: Erstellen einer MDS-Abonnement Sicht mithilfe Master Data Manager</span><span class="sxs-lookup"><span data-stu-id="54231-148">Task 2 &#40;Optional&#41;: Creating a MDS Subscription View using Master Data Manager</span></span>](../../2014/tutorials/task-2-optional-creating-a-mds-subscription-view-using-master-data-manager.md)  
  
  
