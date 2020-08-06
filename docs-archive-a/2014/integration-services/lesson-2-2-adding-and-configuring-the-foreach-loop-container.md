---
title: 'Schritt 2: Hinzufügen und Konfigurieren des Foreach-Schleifencontainers | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 88a973cc-0f23-4ecf-adb6-5b06279c2df6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: de5e8875c43edda618ccef4839c88c3b84a003cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609319"
---
# <a name="step-2-adding-and-configuring-the-foreach-loop-container"></a><span data-ttu-id="0e5a9-102">Schritt 2: Hinzufügen und Konfigurieren des Foreach-Schleifencontainers</span><span class="sxs-lookup"><span data-stu-id="0e5a9-102">Step 2: Adding and Configuring the Foreach Loop Container</span></span>
  <span data-ttu-id="0e5a9-103">In dieser Aufgabe fügen Sie die Möglichkeit zum Schleifendurchlauf für einen Ordner von Flatfiles hinzu und wenden die auch in Lektion 1 verwendete Datenflusstransformation auf jede dieser Flatfiles an.</span><span class="sxs-lookup"><span data-stu-id="0e5a9-103">In this task, you will add the ability to loop through a folder of flat files and apply the same data flow transformation used in Lesson 1 to each of those flat files.</span></span> <span data-ttu-id="0e5a9-104">Dies geschieht durch das Hinzufügen eines Foreach-Schleifencontainers zur Ablaufsteuerung und dessen Konfigurierung.</span><span class="sxs-lookup"><span data-stu-id="0e5a9-104">You do this by adding and configuring a Foreach Loop container to the control flow.</span></span>  
  
 <span data-ttu-id="0e5a9-105">Für den von Ihnen hinzugefügten Foreach-Schleifencontainer muss es möglich sein, eine Verbindung mit jeder Flatfile im Ordner herzustellen.</span><span class="sxs-lookup"><span data-stu-id="0e5a9-105">The Foreach Loop container that you add must be able to connect to each flat file in the folder.</span></span> <span data-ttu-id="0e5a9-106">Da alle Dateien im Ordner das gleiche Format aufweisen, kann vom Foreach-Schleifencontainer der gleiche Flatfile-Verbindungs-Manager zum Herstellen einer Verbindung mit jeder dieser Dateien verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0e5a9-106">Because all the files in the folder have the same format, the Foreach Loop container can use the same Flat File connection manager to connect to each of these files.</span></span> <span data-ttu-id="0e5a9-107">Der vom Container verwendete Flatfile-Verbindungs-Manager ist der gleiche Flatfile-Verbindungs-Manager, den Sie in Lektion 1 erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="0e5a9-107">The Flat File connection manager that the container will use is the same Flat File connection manager that you created in Lesson 1.</span></span>  
  
 <span data-ttu-id="0e5a9-108">Zurzeit wird vom Flatfile-Verbindungs-Manager aus der Lektion 1 nur eine Verbindung mit einer bestimmten Flatfile hergestellt.</span><span class="sxs-lookup"><span data-stu-id="0e5a9-108">Currently, the Flat File connection manager from Lesson 1 connects to only one, specific flat file.</span></span> <span data-ttu-id="0e5a9-109">Um iterativ Verbindungen mit jedem Flatfile im Ordner herzustellen, müssen Sie sowohl den Foreach-Schleifencontainer als auch den Flatfile-Verbindungs-Manager wie folgt konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="0e5a9-109">To iteratively connect to each flat file in the folder, you will have to configure both the Foreach Loop container and the Flat File connection manager as follows:</span></span>  
  
-   <span data-ttu-id="0e5a9-110">**Foreach-Schleifencontainer:** Sie ordnen den aufgezählten Wert des Containers einer benutzerdefinierten Paketvariable zu.</span><span class="sxs-lookup"><span data-stu-id="0e5a9-110">**Foreach Loop container:** You will map the enumerated value of the container to a user-defined package variable.</span></span> <span data-ttu-id="0e5a9-111">Vom Container wird dann diese benutzerdefinierte Variable verwendet, um die `ConnectionString`-Eigenschaft des Flatfile-Verbindungs-Managers dynamisch zu ändern und iterativ Verbindungen mit jeder Flatfile im Ordner herzustellen.</span><span class="sxs-lookup"><span data-stu-id="0e5a9-111">The container will then use this user-defined variable to dynamically modify the `ConnectionString` property of the Flat File connection manager and iteratively connect to each flat file in the folder.</span></span>  
  
-   <span data-ttu-id="0e5a9-112">**Verbindungs-Manager für Flatfiles:** Sie ändern den Verbindungs-Manager, der in Lektion 1 erstellt wurde, indem Sie eine benutzerdefinierte Variable verwenden, um die-Eigenschaft des Verbindungs-Managers aufzufüllen `ConnectionString` .</span><span class="sxs-lookup"><span data-stu-id="0e5a9-112">**Flat File connection manager:** You will modify the connection manager that was created in Lesson 1 by using a user-defined variable to populate the connection manager's `ConnectionString` property.</span></span>  
  
 <span data-ttu-id="0e5a9-113">Die Vorgänge in diesem Task verdeutlichen, wie Sie den Foreach-Schleifencontainer erstellen und ändern, um eine benutzerdefinierte Paketvariable zu verwenden, und wie der Schleife der Datenflusstask hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="0e5a9-113">The procedures in this task show you how to create and modify the Foreach Loop container to use a user-defined package variable and to add the data flow task to the loop.</span></span> <span data-ttu-id="0e5a9-114">Sie lernen, wie der Flatfile-Verbindungs-Manager geändert wird, um eine benutzerdefinierte Variable in der nächsten Aufgabe zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="0e5a9-114">You will learn how to modify the Flat File connection manager to use a user-defined variable in the next task.</span></span>  
  
 <span data-ttu-id="0e5a9-115">Nachdem Sie diese Änderungen am Paket vorgenommen haben, iteriert der Foreach-Schleifencontainer beim Ausführen des Pakets durch die Auflistung der Dateien im Ordner Sample Data.</span><span class="sxs-lookup"><span data-stu-id="0e5a9-115">After you have made these modifications to the package, when the package is run, the Foreach Loop Container will iterate through the collection of files in the Sample Data folder.</span></span> <span data-ttu-id="0e5a9-116">Jedes Mal, wenn eine mit dem Kriterium übereinstimmende Datei gefunden wird, wird die benutzerdefinierte Variable vom Foreach-Schleifencontainer mit dem Dateinamen aufgefüllt, die benutzerdefinierte Variable der `ConnectionString`-Eigenschaft des Sample Currency Data-Flatfile-Verbindungs-Managers zugeordnet und dann der Datenfluss gegen diese Datei ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="0e5a9-116">Each time a file is found that matches the criteria, the Foreach Loop Container will populate the user-defined variable with the file name, map the user-defined variable to the `ConnectionString` property of the Sample Currency Data Flat File connection manager, and then run the data flow against that file.</span></span> <span data-ttu-id="0e5a9-117">Dadurch wird in jeder Iteration der Foreach-Schleife vom Datenflusstask eine andere Flatfile verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="0e5a9-117">Therefore, in each iteration of the Foreach Loop the Data Flow task will consume a different flat file.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0e5a9-118">Weil [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] die Ablaufsteuerung vom Datenfluss trennt, erfordert keine der Schleifen, die Sie der Ablaufsteuerung hinzufügen, Änderungen am Datenfluss.</span><span class="sxs-lookup"><span data-stu-id="0e5a9-118">Because [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] separates control flow from data flow, any looping that you add to the control flow will not require modification to the data flow.</span></span> <span data-ttu-id="0e5a9-119">Deshalb muss der von Ihnen in Lektion 1 erstellte Datenfluss nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="0e5a9-119">Therefore, the data flow that you created in Lesson 1 does not have to be changed.</span></span>  
  
### <a name="to-add-a-foreach-loop-container"></a><span data-ttu-id="0e5a9-120">So fügen Sie einen Foreach-Schleifencontainer hinzu</span><span class="sxs-lookup"><span data-stu-id="0e5a9-120">To add a Foreach Loop container</span></span>  
  
1.  <span data-ttu-id="0e5a9-121">Klicken Sie in **SQL Server Data Tools**auf die Registerkarte **Ablaufsteuerung** .</span><span class="sxs-lookup"><span data-stu-id="0e5a9-121">In **SQL Server Data Tools**, click the **Control Flow** tab.</span></span>  
  
2.  <span data-ttu-id="0e5a9-122">Erweitern Sie **Container**in der **SSIS-Toolbox**, und ziehen Sie anschließend **Foreach-Schleifencontainer** auf die Entwurfsoberfläche der Registerkarte **Ablaufsteuerung** .</span><span class="sxs-lookup"><span data-stu-id="0e5a9-122">In the **SSIS Toolbox**, expand **Containers**, and then drag a **Foreach Loop Container** onto the design surface of the **Control Flow** tab.</span></span>  
  
3.  <span data-ttu-id="0e5a9-123">Klicken Sie mit der rechten Maustaste auf den neu hinzugefügten **Foreach-Schleifencontainer** , und wählen Sie **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="0e5a9-123">Right-click the newly added **Foreach Loop Container** and select **Edit**.</span></span>  
  
4.  <span data-ttu-id="0e5a9-124">Geben Sie im Dialogfeld **foreach-Schleifen-Editor** auf der Seite **Allgemein** unter **Name den Namen**ein `Foreach File in Folder` .</span><span class="sxs-lookup"><span data-stu-id="0e5a9-124">In the **Foreach Loop Editor** dialog box, on the **General** page, for **Name**, enter `Foreach File in Folder`.</span></span> <span data-ttu-id="0e5a9-125">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="0e5a9-125">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="0e5a9-126">Klicken Sie mit der rechten Maustaste auf den Foreach-Schleifen Container, klicken Sie auf **Eigenschaften**, und überprüfen Sie im Eigenschaftenfenster, ob die- `LocaleID` Eigenschaft auf **Englisch (USA)** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="0e5a9-126">Right-click the Foreach Loop container, click **Properties**, and in the Properties window, verify that the `LocaleID` property is set to **English (United States)**.</span></span>  
  
### <a name="to-configure-the-enumerator-for-the-foreach-loop-container"></a><span data-ttu-id="0e5a9-127">So konfigurieren Sie den Enumerator für den Foreach-Schleifencontainer</span><span class="sxs-lookup"><span data-stu-id="0e5a9-127">To configure the enumerator for the Foreach Loop container</span></span>  
  
1.  <span data-ttu-id="0e5a9-128">Doppelklicken Sie auf Foreach File in Folder, um den **Foreach-Schleifen-Editor** erneut zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="0e5a9-128">Double-click Foreach File in Folder to reopen the **Foreach Loop Editor**.</span></span>  
  
2.  <span data-ttu-id="0e5a9-129">Klicken Sie auf **Sammlung**.</span><span class="sxs-lookup"><span data-stu-id="0e5a9-129">Click **Collection**.</span></span>  
  
3.  <span data-ttu-id="0e5a9-130">Wählen Sie auf der Seite **Sammlung** **Foreach-Dateienumerator**aus.</span><span class="sxs-lookup"><span data-stu-id="0e5a9-130">On the **Collection** page, select **Foreach File Enumerator**.</span></span>  
  
4.  <span data-ttu-id="0e5a9-131">Klicken Sie in der Gruppe **Enumeratorkonfiguration** auf **Durchsuchen**.</span><span class="sxs-lookup"><span data-stu-id="0e5a9-131">In the **Enumerator configuration** group, click **Browse**.</span></span>  
  
5.  <span data-ttu-id="0e5a9-132">Suchen Sie im Dialogfeld **Nach Ordner suchen** den Ordner auf dem Computer, der die „Currency_\*.txt“-Dateien enthält.</span><span class="sxs-lookup"><span data-stu-id="0e5a9-132">In the **Browse for Folder** dialog box, locate the folder on your machine that contains the Currency_\*.txt files.</span></span>  
  
     <span data-ttu-id="0e5a9-133">Die Beispieldaten sind in den [!INCLUDE[ssIS](../includes/ssis-md.md)] -Lektionspaketen enthalten.</span><span class="sxs-lookup"><span data-stu-id="0e5a9-133">This sample data is included with the [!INCLUDE[ssIS](../includes/ssis-md.md)] lesson packages.</span></span> <span data-ttu-id="0e5a9-134">Um die Beispieldaten und die Lektionspakete herunterzuladen, gehen Sie wie folgt vor.</span><span class="sxs-lookup"><span data-stu-id="0e5a9-134">To download the sample data and the lesson packages, do the following.</span></span>  
  
    1.  <span data-ttu-id="0e5a9-135">Klicken Sie [hier](https://go.microsoft.com/fwlink/?LinkId=275027), um zur Seite Integration Services Product Samples zu gelangen</span><span class="sxs-lookup"><span data-stu-id="0e5a9-135">Navigate to [Integration Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=275027)</span></span>  
  
    2.  <span data-ttu-id="0e5a9-136">Klicken Sie auf die Registerkarte **DOWNLOADS** .</span><span class="sxs-lookup"><span data-stu-id="0e5a9-136">Click the **DOWNLOADS** tab.</span></span>  
  
    3.  <span data-ttu-id="0e5a9-137">Klicken Sie auf den Hyperlink " https://msftisprodsamples.codeplex.com/downloads/get/578097 " SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip Datei.</span><span class="sxs-lookup"><span data-stu-id="0e5a9-137">Click the  HYPERLINK "https://msftisprodsamples.codeplex.com/downloads/get/578097" SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip file.</span></span>  
  
6.  <span data-ttu-id="0e5a9-138">Geben Sie im Feld **Dateien\*\*\*\*Currency_\*.txt** ein.</span><span class="sxs-lookup"><span data-stu-id="0e5a9-138">In the **Files** box, type **Currency_\*.txt**.</span></span>  
  
### <a name="to-map-the-enumerator-to-a-user-defined-variable"></a><span data-ttu-id="0e5a9-139">So ordnen Sie den Enumerator einer benutzerdefinierten Variablen zu</span><span class="sxs-lookup"><span data-stu-id="0e5a9-139">To map the enumerator to a user-defined variable</span></span>  
  
1.  <span data-ttu-id="0e5a9-140">Klicken Sie auf **Variablenzuordnungen**.</span><span class="sxs-lookup"><span data-stu-id="0e5a9-140">Click **Variable Mappings**.</span></span>  
  
2.  <span data-ttu-id="0e5a9-141">Klicken Sie auf der Seite **Variablen** Zuordnungen in der Spalte **Variable** auf die leere Zelle, und wählen Sie aus **\<New Variable...>** .</span><span class="sxs-lookup"><span data-stu-id="0e5a9-141">On the **Variable Mappings** page, in the **Variable** column, click the empty cell and select **\<New Variable...>**.</span></span>  
  
3.  <span data-ttu-id="0e5a9-142">Geben Sie im Dialogfeld **Variable hinzufügen** für **Name den Namen**ein `varFileName` .</span><span class="sxs-lookup"><span data-stu-id="0e5a9-142">In the **Add Variable** dialog box, for **Name**, type `varFileName`.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="0e5a9-143">Bei Variablennamen wird nach Groß-/Kleinschreibung unterschieden.</span><span class="sxs-lookup"><span data-stu-id="0e5a9-143">Variable names are case sensitive.</span></span>  
  
4.  <span data-ttu-id="0e5a9-144">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="0e5a9-144">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="0e5a9-145">Klicken Sie erneut auf **OK** , um das Dialogfeld **Foreach-Schleifen-Editor** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="0e5a9-145">Click **OK** again to exit the **Foreach Loop Editor** dialog box.</span></span>  
  
### <a name="to-add-the-data-flow-task-to-the-loop"></a><span data-ttu-id="0e5a9-146">So fügen Sie der Schleife den Datenflusstask hinzu</span><span class="sxs-lookup"><span data-stu-id="0e5a9-146">To add the data flow task to the loop</span></span>  
  
-   <span data-ttu-id="0e5a9-147">Ziehen Sie den **Extract Sample Currency Data** -Datenfluss Task auf den Foreach-Schleifen Container, der jetzt umbenannt wurde `Foreach File in Folder` .</span><span class="sxs-lookup"><span data-stu-id="0e5a9-147">Drag the **Extract Sample Currency Data** data flow task onto the Foreach Loop container now renamed `Foreach File in Folder`.</span></span>  
  
## <a name="next-lesson-task"></a><span data-ttu-id="0e5a9-148">Aufgabe in der nächsten Lektion</span><span class="sxs-lookup"><span data-stu-id="0e5a9-148">Next Lesson Task</span></span>  
 [<span data-ttu-id="0e5a9-149">Schritt 3: Ändern des Flatfile-Verbindungs-Managers</span><span class="sxs-lookup"><span data-stu-id="0e5a9-149">Step 3: Modifying the Flat File Connection Manager</span></span>](lesson-2-3-modifying-the-flat-file-connection-manager.md)  
  
## <a name="see-also"></a><span data-ttu-id="0e5a9-150">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0e5a9-150">See Also</span></span>  
 <span data-ttu-id="0e5a9-151">[Konfigurieren eines Foreach-Schleifen Containers](control-flow/foreach-loop-container.md) </span><span class="sxs-lookup"><span data-stu-id="0e5a9-151">[Configure a Foreach Loop Container](control-flow/foreach-loop-container.md) </span></span>  
 [<span data-ttu-id="0e5a9-152">Verwenden von Variablen in Paketen</span><span class="sxs-lookup"><span data-stu-id="0e5a9-152">Use Variables in Packages</span></span>](use-variables-in-packages.md)  
  
