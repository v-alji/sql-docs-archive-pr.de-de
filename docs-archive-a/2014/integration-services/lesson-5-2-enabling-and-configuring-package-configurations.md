---
title: 'Schritt 2: Aktivieren und Konfigurieren von Paketkonfigurationen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 005218ab-8dd5-48e9-a185-6bc60cd43a7a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a804efcd84ebe563a13f61443fe19096788ca809
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615436"
---
# <a name="step-2-enabling-and-configuring-package-configurations"></a><span data-ttu-id="b5484-102">Schritt 2: Aktivieren und Konfigurieren von Paketkonfigurationen</span><span class="sxs-lookup"><span data-stu-id="b5484-102">Step 2: Enabling and Configuring Package Configurations</span></span>
  <span data-ttu-id="b5484-103">In dieser Aufgabe konvertieren Sie das Projekt in das Paketbereitstellungsmodell und aktivieren Paketkonfigurationen mithilfe des Paketkonfigurations-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="b5484-103">In this task, you will convert the project to the Package Deployment Model and enable package configurations using the Package Configuration Wizard.</span></span> <span data-ttu-id="b5484-104">Sie verwenden diesen Assistenten zum Generieren einer XML-Konfigurationsdatei, die Konfigurationseinstellungen für die `Directory`-Eigenschaft des Foreach-Schleifencontainers enthält.</span><span class="sxs-lookup"><span data-stu-id="b5484-104">You will use this wizard to generate an XML configuration file that contains configuration settings for the `Directory` property of the Foreach Loop container.</span></span> <span data-ttu-id="b5484-105">Der Wert der Directory-Eigenschaft wird durch eine neue Variable auf Paketebene bereitgestellt, die Sie zur Laufzeit aktualisieren können.</span><span class="sxs-lookup"><span data-stu-id="b5484-105">The value of the Directory property is supplied by a new package-level variable that you can update at run time.</span></span> <span data-ttu-id="b5484-106">Zusätzlich füllen Sie einen neuen Beispieldatenordner auf, der während des Testens verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b5484-106">Additionally, you will populate a new sample data folder to use during testing.</span></span>  
  
### <a name="to-create-a-new-package-level-variable-mapped-to-the-directory-property"></a><span data-ttu-id="b5484-107">So erstellen Sie eine neue Variable auf Paketebene, die der Directory-Eigenschaft zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="b5484-107">To create a new package-level variable mapped to the Directory property</span></span>  
  
1.  <span data-ttu-id="b5484-108">Klicken Sie in den Hintergrund der Registerkarte **Ablaufsteuerung** im [!INCLUDE[ssIS](../includes/ssis-md.md)] -Designer.</span><span class="sxs-lookup"><span data-stu-id="b5484-108">Click the background of the **Control Flow** tab in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="b5484-109">Dadurch wird der Bereich für die Variable, die Sie erstellen, auf das Paket festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b5484-109">This sets the scope for the variable you will create to the package.</span></span>  
  
2.  <span data-ttu-id="b5484-110">Wählen Sie im Menü [!INCLUDE[ssIS](../includes/ssis-md.md)] den Befehl **Variablen**aus.</span><span class="sxs-lookup"><span data-stu-id="b5484-110">On the [!INCLUDE[ssIS](../includes/ssis-md.md)] menu, select **Variables**.</span></span>  
  
3.  <span data-ttu-id="b5484-111">Klicken Sie im Fenster **Variablen** auf das Symbol „Variable hinzufügen“.</span><span class="sxs-lookup"><span data-stu-id="b5484-111">In the **Variables** window, click the Add Variable icon.</span></span>  
  
4.  <span data-ttu-id="b5484-112">Geben Sie im Feld **Name** den Namen **varFolderName**ein.</span><span class="sxs-lookup"><span data-stu-id="b5484-112">In the **Name** box, type **varFolderName**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="b5484-113">Bei Variablennamen wird nach Groß-/Kleinschreibung unterschieden.</span><span class="sxs-lookup"><span data-stu-id="b5484-113">Variable names are case sensitive.</span></span>  
  
5.  <span data-ttu-id="b5484-114">Überprüfen Sie, ob im Feld **Bereich** der Name des Pakets (Lesson 5) angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b5484-114">Verify that the **Scope** box shows the name of the package, Lesson 5.</span></span>  
  
6.  <span data-ttu-id="b5484-115">Legen Sie den Wert des Felds **Datentyp** der `varFolderName` -Variable auf **String**fest.</span><span class="sxs-lookup"><span data-stu-id="b5484-115">Set the value of the **Data Type** box of the `varFolderName` variable to **String**.</span></span>  
  
7.  <span data-ttu-id="b5484-116">Kehren Sie zur Registerkarte **Ablaufsteuerung** zurück, und doppelklicken Sie auf den **Foreach File in Folder** -Container.</span><span class="sxs-lookup"><span data-stu-id="b5484-116">Return to the **Control Flow** tab and double-click the **Foreach File in Folder** container.</span></span>  
  
8.  <span data-ttu-id="b5484-117">Klicken Sie auf der Seite **Sammlung** des **Foreach-Schleifen-Editors** auf **Ausdrücke** und anschließend auf die Schaltfläche mit den Auslassungspunkten **(...)**.</span><span class="sxs-lookup"><span data-stu-id="b5484-117">On the **Collection** page of the **Foreach Loop Editor**, click **Expressions**, and then click the ellipsis button **(...)**.</span></span>  
  
9. <span data-ttu-id="b5484-118">Klicken Sie im **Eigenschafts Ausdrucks-Editor**in die Liste **Eigenschaft** , und wählen Sie aus `Directory` .</span><span class="sxs-lookup"><span data-stu-id="b5484-118">In the **Property Expressions Editor**, click in the **Property** list, and select `Directory`.</span></span>  
  
10. <span data-ttu-id="b5484-119">Klicken Sie im Feld **Ausdruck** auf die Schaltfläche mit den Auslassungs Punkten **(...)**.</span><span class="sxs-lookup"><span data-stu-id="b5484-119">In the **Expression** box, click the ellipsis button **(...)**.</span></span>  
  
11. <span data-ttu-id="b5484-120">Erweitern Sie im **Ausdrucks-Generator**den Ordner Variablen, und ziehen Sie die Variable **User::varFolderName** in das Feld **Ausdruck** .</span><span class="sxs-lookup"><span data-stu-id="b5484-120">In the **Expression Builder**, expand the Variables folder, and drag the variable **User::varFolderName** to the **Expression** box.</span></span>  
  
12. <span data-ttu-id="b5484-121">Klicken Sie auf **OK** , um den **Ausdrucks-Generator**zu schließen.</span><span class="sxs-lookup"><span data-stu-id="b5484-121">Click **OK** to exit the **Expression Builder**.</span></span>  
  
13. <span data-ttu-id="b5484-122">Klicken Sie auf **OK** , um den **Eigenschaftsausdrucks-Editor**zu schließen.</span><span class="sxs-lookup"><span data-stu-id="b5484-122">Click **OK** to exit the **Property Expressions Editor**.</span></span>  
  
14. <span data-ttu-id="b5484-123">Klicken Sie auf **OK** , um den **Foreach-Schleifen-Editor**zu beenden.</span><span class="sxs-lookup"><span data-stu-id="b5484-123">Click **OK** to exit the **Foreach Loop Editor**.</span></span>  
  
### <a name="to-enable-package-configurations"></a><span data-ttu-id="b5484-124">So aktivieren Sie Paketkonfigurationen</span><span class="sxs-lookup"><span data-stu-id="b5484-124">To enable package configurations</span></span>  
  
1.  <span data-ttu-id="b5484-125">Klicken Sie im **Menü Projekt**auf **in Paket Bereitstellungs Modell konvertieren**.</span><span class="sxs-lookup"><span data-stu-id="b5484-125">On the **Project Menu**, click **Convert to Package Deployment Model**.</span></span>  
  
2.  <span data-ttu-id="b5484-126">Klicken Sie in der Warnungs-Eingabeaufforderung auf **OK** , nachdem die Konvertierung abgeschlossen ist, und klicken Sie im Dialogfeld **In Paketbereitstellungsmodell konvertieren** auf **OK** .</span><span class="sxs-lookup"><span data-stu-id="b5484-126">Click **OK** on the warning prompt and, once the conversion is complete, click **OK** on the **Convert to Package Deployment Model** dialog.</span></span>  
  
3.  <span data-ttu-id="b5484-127">Klicken Sie in den Hintergrund der Registerkarte **Ablaufsteuerung** im [!INCLUDE[ssIS](../includes/ssis-md.md)] -Designer.</span><span class="sxs-lookup"><span data-stu-id="b5484-127">Click the background of the **Control Flow** tab in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
4.  <span data-ttu-id="b5484-128">Klicken Sie im Menü **SSIS** auf **Paketkonfigurationen**.</span><span class="sxs-lookup"><span data-stu-id="b5484-128">On the **SSIS** menu, click **Package Configurations**.</span></span>  
  
5.  <span data-ttu-id="b5484-129">Wählen Sie im Dialogfeld **Paketkonfigurationsplaner** die Option **Paketkonfigurationen aktivieren**aus, und klicken Sie anschließend auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="b5484-129">In the **Package Configurations Organizer** dialog box, select **Enable Package Configurations**, and then click **Add**.</span></span>  
  
6.  <span data-ttu-id="b5484-130">Klicken Sie im Paketkonfigurations-Assistenten auf der Seite Willkommen auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="b5484-130">On the welcome page of the Package Configuration Wizard, click **Next**.</span></span>  
  
7.  <span data-ttu-id="b5484-131">Überprüfen Sie auf der Seite **Konfigurationstyp auswählen** , ob **Konfigurationstyp** auf **XML-Konfigurationsdatei**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="b5484-131">On the **Select Configuration Type** page, verify that the **Configuration type** is set to **XML configuration file**.</span></span>  
  
8.  <span data-ttu-id="b5484-132">Klicken Sie auf der Seite **Konfigurationstyp auswählen** auf **Durchsuchen**.</span><span class="sxs-lookup"><span data-stu-id="b5484-132">On the **Select Configuration Type** page, click **Browse**.</span></span>  
  
9. <span data-ttu-id="b5484-133">Standardmäßig wird das Dialogfeld **Speicherort der Konfigurationsdatei auswählen** mit dem Projektordner geöffnet.</span><span class="sxs-lookup"><span data-stu-id="b5484-133">By default, the **Select Configuration File Location** dialog box will open to the project folder.</span></span>  
  
10. <span data-ttu-id="b5484-134">Geben Sie im Dialogfeld **Speicherort der Konfigurationsdatei auswählen** als **Dateinamen\*\*\*\*SSISTutorial**ein, und klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="b5484-134">In the **Select Configuration File Location** dialog box, for **File name** type **SSISTutorial**, and then click **Save**.</span></span>  
  
11. <span data-ttu-id="b5484-135">Klicken Sie auf der Seite **Konfigurationstyp auswählen** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="b5484-135">On the **Select Configuration Type** page, click **Next.**</span></span>  
  
12. <span data-ttu-id="b5484-136">Erweitern Sie **Variablen** auf der Seite **Eigenschaften für den Exportvorgang auswählen** im Bereich **Objekte**, erweitern Sie **varFolderName**und **Eigenschaften**, und wählen Sie anschließend **Wert**aus.</span><span class="sxs-lookup"><span data-stu-id="b5484-136">On the **Select Properties to Export** page, in the **Objects** pane, expand **Variables**, expand **varFolderName**, expand **Properties**, and then select **Value**.</span></span>  
  
13. <span data-ttu-id="b5484-137">Klicken Sie auf der Seite **Eigenschaften für den Exportvorgang auswählen** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="b5484-137">On the **Select Properties to Export** page, click **Next**.</span></span>  
  
14. <span data-ttu-id="b5484-138">Geben Sie auf der Seite **Assistenten abschließen** einen Konfigurationsnamen für die Konfiguration ein, beispielsweise **SSIS Tutorial Directory configuration**.</span><span class="sxs-lookup"><span data-stu-id="b5484-138">On the **Completing the Wizard** page, type a configuration name for the configuration, such as **SSIS Tutorial Directory configuration**.</span></span> <span data-ttu-id="b5484-139">Dies ist der Konfigurationsname, der im Dialogfeld **Paketkonfigurationsplaner** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b5484-139">This is the configuration name that is displayed in the **Package Configuration Organizer** dialog box.</span></span>  
  
15. <span data-ttu-id="b5484-140">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="b5484-140">Click **Finish**.</span></span>  
  
16. <span data-ttu-id="b5484-141">Klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="b5484-141">Click **Close**.</span></span>  
  
17. <span data-ttu-id="b5484-142">Der Assistent erstellt eine Konfigurationsdatei mit dem Namen SSISTutorial. dzconfig, die Konfigurationseinstellungen für den `value` der Variablen enthält, die wiederum die- `Directory` Eigenschaft des Enumerators festlegt.</span><span class="sxs-lookup"><span data-stu-id="b5484-142">The wizard creates a configuration file, named SSISTutorial.dtsConfig, that contains configuration settings for the `value` of the variable that in turn sets the `Directory` property of the enumerator.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b5484-143">Eine Konfigurationsdatei enthält typischerweise komplexe Informationen zu den Paketeigenschaften. In diesem Lernprogramm sollte die einzige Konfigurationsinformation allerdings Folgende sein:</span><span class="sxs-lookup"><span data-stu-id="b5484-143">A configuration file typically contains complex information about the package properties, but for this tutorial the only configuration information should be</span></span>  
    > <span data-ttu-id="b5484-144"><Configuration ConfiguredType="Property"</span><span class="sxs-lookup"><span data-stu-id="b5484-144"><Configuration ConfiguredType="Property"</span></span>  
    > <span data-ttu-id="b5484-145">Path = "\Package.variables [User:: varFolderName]. Properties [value] "ValueType =" String "\></span><span class="sxs-lookup"><span data-stu-id="b5484-145">Path="\Package.Variables[User::varFolderName].Properties[Value]" ValueType="String"\></span></span>  
    >  \<ConfiguredValue>\</ConfiguredValue>  
    > <span data-ttu-id="b5484-146">\</Configuration>.</span><span class="sxs-lookup"><span data-stu-id="b5484-146">\</Configuration>.</span></span>  
  
### <a name="to-create-and-populate-a-new-sample-data-folder"></a><span data-ttu-id="b5484-147">So erstellen und füllen Sie einen neuen Beispieldatenordner</span><span class="sxs-lookup"><span data-stu-id="b5484-147">To create and populate a new sample data folder</span></span>  
  
1.  <span data-ttu-id="b5484-148">Erstellen Sie in Windows-Explorer auf der Stamm Ebene Ihres Laufwerks (z. b \\ . C:) einen neuen Ordner mit dem Namen `New Sample Data` .</span><span class="sxs-lookup"><span data-stu-id="b5484-148">In Windows Explorer, at the root level of your drive (for example, C:\\), create a new folder named `New Sample Data`.</span></span>  
  
2.  <span data-ttu-id="b5484-149">Suchen Sie die Beispieldateien auf dem Computer, und kopieren Sie drei der Dateien aus dem Ordner.</span><span class="sxs-lookup"><span data-stu-id="b5484-149">Locate the sample files on your computer and copy three of the files from the folder.</span></span>  
  
3.  <span data-ttu-id="b5484-150">Fügen Sie `New Sample Data` die kopierten Dateien in den Ordner ein.</span><span class="sxs-lookup"><span data-stu-id="b5484-150">In the `New Sample Data` folder, paste the copied files.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="b5484-151">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="b5484-151">Next Task in Lesson</span></span>  
 [<span data-ttu-id="b5484-152">Schritt 3: Ändern des Konfigurationswerts der Directory-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="b5484-152">Step 3: Modifying the Directory Property Configuration Value</span></span>](lesson-5-3-modifying-the-directory-property-configuration-value.md)  
  
  
