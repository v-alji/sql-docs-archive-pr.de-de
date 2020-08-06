---
title: 'Tutorial: Verwenden der odata-Quelle [SSIS] | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 2c64cf8b-5edb-48df-8ffe-697096258f71
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a13b04494ed00251774b490b1cc929769a869acb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621076"
---
# <a name="tutorial-using-the-odata-source-ssis"></a><span data-ttu-id="0697e-102">Lernprogramm: Verwenden der OData-Quelle [SSIS]</span><span class="sxs-lookup"><span data-stu-id="0697e-102">Tutorial: Using the OData Source [SSIS]</span></span>
  <span data-ttu-id="0697e-103">Dieses Tutorial führt Sie schrittweise durch den Prozess, bei dem die Sammlung **Employees** aus dem OData-Beispieldienst **Northwind** (http://services.odata.org/V3/Northwind/Northwind.svc/) extrahiert und anschließend in eine Flatfile geladen wird.</span><span class="sxs-lookup"><span data-stu-id="0697e-103">This tutorial walks you through the process to extract the **Employees** collection from the sample **Northwind** OData service (http://services.odata.org/V3/Northwind/Northwind.svc/), and then load it into a flat file.</span></span>  
  
## <a name="1-create-an-integration-services-project"></a><span data-ttu-id="0697e-104">1. Erstellen eines Integration Services-Projekts</span><span class="sxs-lookup"><span data-stu-id="0697e-104">1. Create an Integration Services Project</span></span>  
  
1.  <span data-ttu-id="0697e-105">Starten Sie **SQL Server Data Tools** oder [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0697e-105">Launch **SQL Server Data Tools** or [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span></span>  
  
2.  <span data-ttu-id="0697e-106">Klicken Sie auf **Datei**, zeigen Sie auf **Neu**, und klicken Sie auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="0697e-106">Click **File**, point to **New**, and click **Project**.</span></span>  
  
3.  <span data-ttu-id="0697e-107">Erweitern Sie im Dialogfeld **Neues Projekt** die Knoten **Installiert**, **Vorlagen**und **Business Intelligence**, und klicken Sie auf **Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="0697e-107">In the **New Project** dialog box, expand **Installed**, expand **Templates**, expand **Business Intelligence**, and click **Integration Services**.</span></span>  
  
4.  <span data-ttu-id="0697e-108">Wählen Sie als Projekttyp **Integration Services-Projekt** aus.</span><span class="sxs-lookup"><span data-stu-id="0697e-108">Select **Integration Services Project** for the type of project.</span></span>  
  
5.  <span data-ttu-id="0697e-109">Geben Sie einen **Namen** ein, und wählen Sie einen **Speicherort** für das Projekt aus. Klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="0697e-109">Enter a **name** and select a **location** for the project, and click **OK**.</span></span>  
  
## <a name="2-add-and-configure-odata-source-to-the-ssis-package"></a><span data-ttu-id="0697e-110">2. Hinzufügen und Konfigurieren einer OData-Quelle für das SSIS-Paket</span><span class="sxs-lookup"><span data-stu-id="0697e-110">2. Add and Configure OData Source to the SSIS Package</span></span>  
  
1.  <span data-ttu-id="0697e-111">Ziehen Sie einen **Datenflusstask** aus der **SSIS-Toolbox** auf die Entwurfsoberfläche der Ablaufsteuerung des SSIS-Pakets.</span><span class="sxs-lookup"><span data-stu-id="0697e-111">Drag-drop a **Data Flow Task** from the **SSIS Toolbox** on to the control flow design surface of your SSIS package.</span></span>  
  
2.  <span data-ttu-id="0697e-112">Klicken Sie auf die Registerkarte **Datenfluss** , oder doppelklicken Sie auf den neu hinzugefügten **Datenflusstask** , um die **Datenfluss-Entwurfsoberfläche**zu starten.</span><span class="sxs-lookup"><span data-stu-id="0697e-112">Click the **Data Flow** tab, or double click on the newly added **Data Flow Task** to launch the **Data Flow design surface**.</span></span>  
  
3.  <span data-ttu-id="0697e-113">Ziehen Sie die **OData-Quelle** aus der Gruppe **Allgemein** in die **SSIS-Toolbox**.</span><span class="sxs-lookup"><span data-stu-id="0697e-113">Drag-drop **OData Source** from the **Common** group in the **SSIS Toolbox**.</span></span> <span data-ttu-id="0697e-114">Beim erstmaligen Installieren der **OData-Quelle** wird sie unter der Gruppe **Allgemein** in der **SSIS-Toolbox**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0697e-114">When the **OData Source** is first installed, it will appear under the **Common** group in the **SSIS Toolbox**.</span></span>  
  
4.  <span data-ttu-id="0697e-115">Doppelklicken Sie auf die Komponente **OData-Quelle** , um das Dialogfeld **Quellen-Editor für OData** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="0697e-115">Double click the **OData Source** component to launch the **OData Source Editor** dialog box.</span></span>  
  
5.  <span data-ttu-id="0697e-116">Klicken Sie auf **Neu…**, um einen neuen OData-Verbindungs-Manager hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="0697e-116">Click **New...** to add a new OData Connection Manager.</span></span>  
  
6.  <span data-ttu-id="0697e-117">Geben Sie die OData-Dienst-URL als **Speicherort des Dienstdokuments**ein.</span><span class="sxs-lookup"><span data-stu-id="0697e-117">Enter the OData service URL for **Service document location**.</span></span> <span data-ttu-id="0697e-118">Hierbei kann es sich um die URL zum Dienstdokument oder zu einem bestimmten Feed oder einer bestimmten Entität handeln.</span><span class="sxs-lookup"><span data-stu-id="0697e-118">This can be the URL to the service document, or to a specific feed or entity.</span></span> <span data-ttu-id="0697e-119">Geben Sie für dieses Tutorial den Namen ein [http://services.odata.org/V3/Northwind/Northwind.svc/](http://services.odata.org/V3/Northwind/Northwind.svc/) .</span><span class="sxs-lookup"><span data-stu-id="0697e-119">For the purpose of this tutorial, type [http://services.odata.org/V3/Northwind/Northwind.svc/](http://services.odata.org/V3/Northwind/Northwind.svc/).</span></span>  
  
7.  <span data-ttu-id="0697e-120">Vergewissern Sie sich, dass als **Authentifizierung** der Typ **Windows-Authentifizierung** für den Zugriff auf den OData-Dienst ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="0697e-120">Confirm that **Windows Authentication** is selected for the **authentication** to use to access the OData Service.</span></span> <span data-ttu-id="0697e-121">**Windows-Authentifizierung** ist standardmäßig ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="0697e-121">**Windows Authentication** is selected by default.</span></span> <span data-ttu-id="0697e-122">Wenn Sie die Standardauthentifizierung verwenden möchten, wählen Sie **Diesen Benutzernamen und dieses Kennwort verwenden**aus.</span><span class="sxs-lookup"><span data-stu-id="0697e-122">To use basic authentication, select **Use this user name and password**.</span></span>  
  
8.  <span data-ttu-id="0697e-123">Klicken Sie für die Verbindung auf **Verbindung testen** , und klicken Sie auf **OK** , um eine Instanz des OData-Verbindungs-Managers zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0697e-123">Click **Test Connection** to the connection, and click **OK** to create an instance of OData Connection Manager.</span></span>  
  
9. <span data-ttu-id="0697e-124">Vergewissern Sie sich im Dialogfeld **Quellen-Editor für OData** , dass **Auflistung** für die Option **Auflistung für Ressourcenpfad verwenden** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="0697e-124">In the **OData Source Editor** Dialog Box, confirm that **Collection** is selected for **Use collection on resource path** option.</span></span>  
  
10. <span data-ttu-id="0697e-125">Wählen Sie in der Dropdownliste **Auflistung** den Eintrag **Employees**aus.</span><span class="sxs-lookup"><span data-stu-id="0697e-125">From the **Collection** drop down list, select **Employees**.</span></span>  
  
11. <span data-ttu-id="0697e-126">Geben Sie zusätzliche OData-Abfrageoptionen oder Filter für **Abfrageoptionen**ein.</span><span class="sxs-lookup"><span data-stu-id="0697e-126">Enter any additional OData query options or filters for **Query Options**.</span></span> <span data-ttu-id="0697e-127">Ex.</span><span class="sxs-lookup"><span data-stu-id="0697e-127">Ex.</span></span> <span data-ttu-id="0697e-128">$orderby=CompanyName&$top=100.</span><span class="sxs-lookup"><span data-stu-id="0697e-128">$orderby=CompanyName&$top=100.</span></span> <span data-ttu-id="0697e-129">Geben Sie für die Zwecke dieses Lernprogramms **$top=5**ein.</span><span class="sxs-lookup"><span data-stu-id="0697e-129">For the purpose of this tutorial, enter **$top=5**.</span></span>  
  
12. <span data-ttu-id="0697e-130">Klicken Sie auf **Vorschau** , um eine Vorschau der Daten aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="0697e-130">Click **Preview** to preview the data.</span></span>  
  
13. <span data-ttu-id="0697e-131">Klicken Sie im linken Navigationsbereich auf **Spalten** , um zur Seite **Spalten** zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="0697e-131">Click **Columns** in the left navigation pane to switch to the **Columns** page.</span></span>  
  
14. <span data-ttu-id="0697e-132">Wählen Sie in **Verfügbare externe Spalten**die Spalten **EmployeeID**, **FirstName** und **LastName** aus, indem Sie die Kontrollkästchen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="0697e-132">Select **EmployeeID**, **FirstName**, and **LastName** from **Available External Columns** by checking the check boxes.</span></span>  
  
15. <span data-ttu-id="0697e-133">Klicken Sie auf **OK** , um das Dialogfeld **Quellen-Editor für OData** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="0697e-133">Click **OK** to close the **OData Source Editor** dialog box.</span></span>  
  
## <a name="3-add-flat-file-destination-and-test-the-solution"></a><span data-ttu-id="0697e-134">3. Hinzufügen eines Flatfileziels und Testen der Projektmappe</span><span class="sxs-lookup"><span data-stu-id="0697e-134">3. Add Flat File Destination and Test the Solution</span></span>  
  
1.  <span data-ttu-id="0697e-135">Ziehen Sie nun ein **Flatfileziel** aus der **SSIS-Toolbox** auf die Entwurfsoberfläche Datenfluss unter die Komponente **OData-Quelle** .</span><span class="sxs-lookup"><span data-stu-id="0697e-135">Now, drag-drop a **Flat File Destination** from **SSIS Toolbox** to the Data Flow design surface below the **OData Source** component.</span></span>  
  
2.  <span data-ttu-id="0697e-136">Verbindung Sie über einen blauen Pfeil die Komponente **OData-Quelle** mit der Komponente **Flatfileziel** .</span><span class="sxs-lookup"><span data-stu-id="0697e-136">Connect **OData Source** component with the **Flat File Destination** component using blue arrow.</span></span>  
  
3.  <span data-ttu-id="0697e-137">Doppelklicken Sie auf **Flatfileziel**.</span><span class="sxs-lookup"><span data-stu-id="0697e-137">Double-click on **Flat File Destination**.</span></span> <span data-ttu-id="0697e-138">Das Dialogfeld **Ziel-Editor für Flatfiles** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="0697e-138">You should see the **Flat File Destination Editor** dialog box.</span></span>  
  
4.  <span data-ttu-id="0697e-139">Klicken Sie im Dialogfeld **Ziel-Editor für Flatfiles** auf **Neu** , um einen neuen Verbindungs-Manager für Flatfiles zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0697e-139">In the **Flat File Destination Editor** dialog box, click **New** to create a new flat file connection manager.</span></span>  
  
5.  <span data-ttu-id="0697e-140">Wählen Sie im Dialogfeld **Flatfileformat** die Option **Mit Trennzeichen**aus.</span><span class="sxs-lookup"><span data-stu-id="0697e-140">In the **Flat File Format** dialog box, select **Delimited**.</span></span> <span data-ttu-id="0697e-141">Das Dialogfeld **Verbindungs-Manager-Editor für Flatfiles** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="0697e-141">You should see the **Flat File Connection Manager Editor** dialog box.</span></span>  
  
6.  <span data-ttu-id="0697e-142">Geben Sie im Dialogfeld **Verbindungs-Manager-Editor für Flatfiles** für **Dateiname**den Namen **c:\Employees.txt**ein.</span><span class="sxs-lookup"><span data-stu-id="0697e-142">In the **Flat File Connection Manager Editor** dialog box, for the **File name**, enter **c:\Employees.txt**.</span></span>  
  
7.  <span data-ttu-id="0697e-143">Klicken Sie im linken Navigationsbereich auf **Spalten**.</span><span class="sxs-lookup"><span data-stu-id="0697e-143">In the left navigation pane, click **Columns**.</span></span> <span data-ttu-id="0697e-144">Auf dieser Seite können Sie die Daten in der Vorschau anzeigen.</span><span class="sxs-lookup"><span data-stu-id="0697e-144">You can preview the data on this page.</span></span>  
  
8.  <span data-ttu-id="0697e-145">Klicken Sie auf OK, um das Dialogfeld **Verbindungs-Manager-Editor für Flatfiles** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="0697e-145">Click OK to close the **Flat File Connection Manager** Editor dialog box.</span></span>  
  
9. <span data-ttu-id="0697e-146">Klicken Sie im Dialogfeld **Ziel-Editor für Flatfiles** im linken Navigationsbereich auf **Zuordnungen** .</span><span class="sxs-lookup"><span data-stu-id="0697e-146">In the **Flat File Destination Editor** dialog box, click **Mappings** in the left navigation pane.</span></span> <span data-ttu-id="0697e-147">Überprüfen Sie die Zuordnungen.</span><span class="sxs-lookup"><span data-stu-id="0697e-147">Review the mappings.</span></span>  
  
10. <span data-ttu-id="0697e-148">Klicken Sie auf OK, um das Dialogfeld **Ziel-Editor für Flatfiles** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="0697e-148">Click OK to close the **Flat File Destination Editor** dialog box.</span></span>  
  
11. <span data-ttu-id="0697e-149">Kompilieren Sie das SSIS-Paket, und führen Sie es aus.</span><span class="sxs-lookup"><span data-stu-id="0697e-149">Compile and execute the SSIS package.</span></span> <span data-ttu-id="0697e-150">Überprüfen Sie, ob die Ausgabedatei mit ID, Vorname und Nachname für fünf Mitarbeiter aus dem OData-Feed erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="0697e-150">Verify that the output file is created with ID, First Name, and Last Name for 5 employees from the OData feed.</span></span>  
  
  
