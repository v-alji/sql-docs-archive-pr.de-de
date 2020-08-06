---
title: Planen von administrativen SSAS-Tasks mit SQL Server-Agent | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 2d1484b3-51d9-48a0-93d2-0c3e4ed22b87
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2c78fa5fcebc0589ba863163b93ad2d10731b75a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702062"
---
# <a name="schedule-ssas-administrative-tasks-with-sql-server-agent"></a><span data-ttu-id="6e6d3-102">Planen von administrativen Tasks in SSAS mithilfe von SQL Server-Agent</span><span class="sxs-lookup"><span data-stu-id="6e6d3-102">Schedule SSAS Administrative Tasks with SQL Server Agent</span></span>
  <span data-ttu-id="6e6d3-103">Mithilfe des SQL Server-Agent-Diensts können Sie die gewünschte Reihenfolge und die erforderlichen Zeitpunkte für die Ausführung von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Verwaltungsaufgaben planen.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-103">Using the SQL Server Agent service, you can schedule [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] administrative tasks to run in the order and times that you need.</span></span> <span data-ttu-id="6e6d3-104">Mit geplanten Tasks können Sie Vorgänge automatisieren, die in regelmäßigen oder vorhersagbaren Abständen ausgeführt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-104">Scheduled tasks help you automate processes that run on regular or predictable cycles.</span></span> <span data-ttu-id="6e6d3-105">Dabei können Sie administrative Tasks wie z. B. die Cubeverarbeitung so planen, dass sie zu Zeiten ausgeführt werden, in denen die geschäftliche Auslastung des Servers niedrig ist.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-105">You can schedule administrative tasks, such as cube processing, to run during times of slow business activity.</span></span> <span data-ttu-id="6e6d3-106">Sie können auch die Reihenfolge bestimmen, in der die Tasks ausgeführt werden sollen, indem Sie innerhalb eines SQL Server-Agent-Auftrags Auftragsschritte erstellen.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-106">You can also determine the order in which tasks run by creating job steps within a SQL Server Agent job.</span></span> <span data-ttu-id="6e6d3-107">Beispielsweise können Sie einen Cube verarbeiten und dann eine Sicherung des Cubes durchführen lassen.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-107">For example, you can process a cube and then perform a backup of the cube.</span></span>  
  
 <span data-ttu-id="6e6d3-108">Mit Auftragsschritten können Sie den Ausführungsprozess steuern.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-108">Job steps give you control over flow of execution.</span></span> <span data-ttu-id="6e6d3-109">Sie können SQL Server-Agent so konfigurieren, dass im Fall eines Fehlers bei einem Auftrag mit der Ausführung der restlichen Tasks fortgefahren wird, oder die Ausführung angehalten wird.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-109">If one job fails, you can configure SQL Server Agent to continue to run the remaining tasks or to stop execution.</span></span> <span data-ttu-id="6e6d3-110">Sie können in SQL Server-Agent auch das Senden von Benachrichtigungen über die erfolgreiche bzw. fehlerhafte Ausführung eines Auftrags konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-110">You can also configure SQL Server Agent to send notifications about the success or failure of job execution.</span></span>  
  
 <span data-ttu-id="6e6d3-111">Dieses Thema ist eine exemplarische Vorgehensweise, in der zwei Methoden erläutert werden, wie Sie XMLA-Skript mithilfe des SQL Server-Agents ausführen.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-111">This topic is a walkthrough that shows two ways of using SQL Server Agent to run XMLA script.</span></span> <span data-ttu-id="6e6d3-112">Im ersten Beispiel wird veranschaulicht, wie die Verarbeitung einer einzelnen Dimension geplant wird.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-112">The first example demonstrates how to schedule processing of a single dimension.</span></span> <span data-ttu-id="6e6d3-113">Im zweiten Beispiel wird gezeigt, wie Verarbeitungstasks in ein einzelnes Skript kombiniert werden, das nach einem Zeitplan ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-113">Example two shows how to combine processing tasks into a single script that runs on a schedule.</span></span> <span data-ttu-id="6e6d3-114">Wenn Sie diese exemplarische Vorgehensweise abschließen möchten, müssen folgende Voraussetzungen erfüllt sein.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-114">To complete this walkthrough, you will need to meet the following prerequisites.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6e6d3-115">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="6e6d3-115">Prerequisites</span></span>  
 <span data-ttu-id="6e6d3-116">Der SQL Server-Agent-Dienst muss installiert sein.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-116">SQL Server Agent service must be installed.</span></span>  
  
 <span data-ttu-id="6e6d3-117">Standardmäßig werden Aufträge unter demselben Dienstkonto ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-117">By default, jobs run under the service account.</span></span> <span data-ttu-id="6e6d3-118">In [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] lautet das Standardkonto für SQL Server-Agent NT service\sqlagent $ \<instancename> .</span><span class="sxs-lookup"><span data-stu-id="6e6d3-118">In [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], the default account for SQL Server Agent is NT Service\SQLAgent$\<instancename>.</span></span> <span data-ttu-id="6e6d3-119">Um einen Sicherungs- oder Verarbeitungstask auszuführen, muss dieses Konto Systemadministrator auf der Analysis Services-Instanz sein.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-119">To perform a backup or processing task, this account must be a system administrator on the Analysis Services instance.</span></span> <span data-ttu-id="6e6d3-120">Weitere Informationen finden Sie unter [Erteilen von Server Administrator Berechtigungen &#40;Analysis Services&#41;](grant-server-admin-rights-to-an-analysis-services-instance.md).</span><span class="sxs-lookup"><span data-stu-id="6e6d3-120">For more information, see [Grant Server Administrator Permissions &#40;Analysis Services&#41;](grant-server-admin-rights-to-an-analysis-services-instance.md).</span></span>  
  
 <span data-ttu-id="6e6d3-121">Sie sollten außerdem eine Testdatenbank haben, um damit zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-121">You should also have a test database to work with.</span></span> <span data-ttu-id="6e6d3-122">Sie können die mehrdimensionale AdventureWorks-Beispieldatenbank oder ein Projekt aus dem mehrdimensionalen Analysis Services-Lernprogramm bereitstellen, um es in dieser exemplarischen Vorgehensweise zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-122">You can deploy the AdventureWorks multidimensional sample database or a project from the Analysis Services multidimensional tutorial to use in this walkthrough.</span></span> <span data-ttu-id="6e6d3-123">Weitere Informationen finden Sie unter [Installieren von Beispiel Daten und-Projekten für das Analysis Services Tutorial zur mehrdimensionalen Modellierung](../install-sample-data-and-projects.md).</span><span class="sxs-lookup"><span data-stu-id="6e6d3-123">For more information, see [Install Sample Data and Projects for the Analysis Services Multidimensional Modeling Tutorial](../install-sample-data-and-projects.md).</span></span>  
  
## <a name="example-1-processing-a-dimension-in-a-scheduled-task"></a><span data-ttu-id="6e6d3-124">Beispiel 1: Verarbeiten einer Dimension in einem geplanten Task</span><span class="sxs-lookup"><span data-stu-id="6e6d3-124">Example 1: Processing a dimension in a scheduled task</span></span>  
 <span data-ttu-id="6e6d3-125">In diesem Beispiel wird veranschaulicht, wie Sie einen Auftrag erstellen und planen, um eine Dimension zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-125">This example demonstrates how to create and schedule a job that processes a dimension.</span></span>  
  
 <span data-ttu-id="6e6d3-126">Ein geplanter [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Task ist ein in einem SQL Server-Agent-Auftrag eingebettetes XMLA-Skript.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-126">An [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] scheduled task is an XMLA script that is embedded into a SQL Server Agent job.</span></span> <span data-ttu-id="6e6d3-127">Dieser Auftrag ist geplant, d. h. er wird zu den festgelegten Zeiten und mit der festgelegten Häufigkeit ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-127">This job is scheduled to run at desired times and frequency.</span></span> <span data-ttu-id="6e6d3-128">SQL Server-Agent ist Teil von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], daher benötigen Sie zum Erstellen und Planen von administrativen Tasks sowohl die Datenbank-Engine als auch [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6e6d3-128">Because the SQL Server Agent is part of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you work with both the Database Engine and [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to create and schedule an administrative task.</span></span>  
  
###  <a name="create-a-script-for-processing-a-dimension-in-a-sql-server-agent-job"></a><a name="bkmk_CreateScript"></a> <span data-ttu-id="6e6d3-129">Erstellen eines Skripts zum Verarbeiten einer Dimension in einem SQL Server-Agent-Auftrag</span><span class="sxs-lookup"><span data-stu-id="6e6d3-129">Create a script for processing a dimension in a SQL Server Agent job</span></span>  
  
1.  <span data-ttu-id="6e6d3-130">Stellen Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]eine Verbindung zu [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-130">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="6e6d3-131">Öffnen Sie einen Datenbankordner, und suchen Sie eine Dimension.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-131">Open a database folder and find a dimension.</span></span> <span data-ttu-id="6e6d3-132">Klicken Sie mit der rechten Maustaste auf die Dimension, und wählen Sie **Verarbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-132">Right-click the dimension and select **Process**.</span></span>  
  
2.  <span data-ttu-id="6e6d3-133">Überprüfen Sie im Dialogfeld **Dimension aufbereiten** in der Spalte **Verarbeitungsoptionen** unter **Objektliste**, ob die Option für diese Spalte **Vollständig verarbeiten**lautet.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-133">In the **Process Dimension** dialog box, in the **Process Options** column under **Object list**, verify that the option for this column is **Process Full**.</span></span> <span data-ttu-id="6e6d3-134">Falls dies nicht der Fall ist, klicken Sie auf die Option unter **Verarbeitungsoptionen**, und wählen Sie anschließend **Vollständig verarbeiten** aus der Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-134">If it is not, under **Process Options**, click the option, and then select **Process Full** from the drop-down list.</span></span>  
  
3.  <span data-ttu-id="6e6d3-135">Klicken Sie auf **Skript**.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-135">Click **Script**.</span></span>  
  
     <span data-ttu-id="6e6d3-136">Dieser Schritt öffnet ein **XML-Abfragefenster** , welches das XMLA-Skript enthält, das die Dimension verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-136">This step opens an **XML Query** window that contains the XMLA script that processes the dimension.</span></span>  
  
4.  <span data-ttu-id="6e6d3-137">Klicken Sie im Dialogfeld **Dimension aufbereiten** auf **Abbrechen** , um das Dialogfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-137">In the **Process Dimension** dialog box, click **Cancel** to close the dialog box.</span></span>  
  
5.  <span data-ttu-id="6e6d3-138">Markieren Sie im **XMLA-Abfragefenster** das XMLA-Skript, klicken Sie mit der rechten Maustaste auf das markierte Skript, und wählen Sie **Kopieren**aus.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-138">In the **XMLA Query** window, highlight the XMLA script, right-click the highlighted script, and select **Copy**.</span></span>  
  
     <span data-ttu-id="6e6d3-139">Dieser Schritt kopiert das XMLA-Skript in die Windows-Zwischenablage.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-139">This step copies the XMLA script to the Windows Clipboard.</span></span> <span data-ttu-id="6e6d3-140">Sie können das XMLA-Skript in der Zwischenablage lassen oder es in Editor oder einen anderen Text-Editor einfügen.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-140">You can leave the XMLA script in the Clipboard or paste it into Notepad or another text editor.</span></span> <span data-ttu-id="6e6d3-141">Unten ist ein Beispiel für das XMLA-Skript angegeben.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-141">The following is an example of the XMLA script.</span></span>  
  
    ```  
    <Batch xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
     <Parallel>  
      <Process xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
        <Object>  
          <DatabaseID>Adventure Works DW Multidimensional</DatabaseID>  
          <DimensionID>Dim Account</DimensionID>  
        </Object>  
        <Type>ProcessFull</Type>  
        <WriteBackTableCreation>UseExisting</WriteBackTableCreation>  
      </Process>  
     </Parallel>  
    </Batch>  
    ```  
  
###  <a name="create-and-schedule-the-dimension-processing-job"></a><a name="bkmk_ProcessJob"></a> <span data-ttu-id="6e6d3-142">Erstellen und Planen des Dimensionsverarbeitungsauftrags</span><span class="sxs-lookup"><span data-stu-id="6e6d3-142">Create and schedule the dimension processing job</span></span>  
  
1.  <span data-ttu-id="6e6d3-143">Stellen Sie eine Verbindung mit einer Instanz der Datenbank-Engine her, und öffnen Sie dann den Objekt-Explorer.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-143">Connect to an instance of the Database Engine and then open Object Explorer.</span></span>  
  
2.  <span data-ttu-id="6e6d3-144">Erweitern Sie **SQL Server-Agent**.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-144">Expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="6e6d3-145">Klicken Sie mit der rechten Maustaste auf **Aufträge** , und wählen Sie **Neuer Auftrag**aus.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-145">Right-click **Jobs** and select **New Job**.</span></span>  
  
4.  <span data-ttu-id="6e6d3-146">Geben Sie im Dialogfeld **Neuer Auftrag** unter **Name**einen Auftragsnamen ein.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-146">In the **New Job** dialog box, enter a job name in **Name**.</span></span>  
  
5.  <span data-ttu-id="6e6d3-147">Wählen Sie unter **Seite auswählen**die Option **Schritte**aus, und klicken Sie dann auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-147">Under **Select a page**, select **Steps**, and then click **New**.</span></span>  
  
6.  <span data-ttu-id="6e6d3-148">Geben Sie im Dialogfeld **Neuer Auftragsschritt** unter **Schrittname**einen Schrittnamen ein.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-148">In the **New Job Step** dialog box, enter a step name in **Step Name**.</span></span>  
  
7.  <span data-ttu-id="6e6d3-149">Geben **Server**Sie in Server **localhost** für eine Standard Instanz von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] und \*\*localhost \\ \*\* \<*instance name*> für eine benannte Instanz ein.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-149">In **Server**, type **localhost** for a default instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] and **localhost\\**\<*instance name*> for a named instance.</span></span>  
  
     <span data-ttu-id="6e6d3-150">Wenn Sie den Auftrag von einem Remotecomputer ausführen, verwenden Sie den Namen des Servers und der Instanz, wo der Auftrag ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-150">If you will be running the job from a remote computer, use the server name and instance name where the job will run.</span></span> <span data-ttu-id="6e6d3-151">Verwenden Sie das Format \<*server name*> für eine Standard Instanz und den \<*server name*> \\ < *Instanznamen*> für eine benannte Instanz.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-151">Use the format \<*server name*> for a default instance, and \<*server name*>\\<*instance name*> for a named instance.</span></span>  
  
8.  <span data-ttu-id="6e6d3-152">Wählen Sie unter **Typ**die Option **SQL Server Analysis Services-Befehl**aus.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-152">In **Type**, select **SQL Server Analysis Services Command**.</span></span>  
  
9. <span data-ttu-id="6e6d3-153">Klicken Sie unter **Befehl**mit der rechten Maustaste, und wählen Sie **Einfügen**aus.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-153">In **Command**, right-click and select **Paste**.</span></span> <span data-ttu-id="6e6d3-154">Das XMLA-Skript, das Sie im vorherigen Schritt generiert haben, sollte im Befehlsfenster angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-154">The XMLA script that you generated in the previous step should appear in the command window.</span></span>  
  
10. <span data-ttu-id="6e6d3-155">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-155">Click **OK**.</span></span>  
  
11. <span data-ttu-id="6e6d3-156">Wählen Sie unter **Seite auswählen**die Option **Zeitpläne**aus, und klicken Sie dann auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-156">Under **Select a page**, click **Schedules**, and then click **New**.</span></span>  
  
12. <span data-ttu-id="6e6d3-157">Geben Sie im Dialogfeld **Neuer Auftragszeitplan** einen Namen für den Zeitplan in das Feld **Name**ein, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-157">In the **New Job Schedule** dialog box, enter a schedule name in **Name**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="6e6d3-158">Dieser Schritt erstellt einen Zeitplan für Sonntag 00:00 Uhr.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-158">This step creates a schedule for Sunday at 12:00 AM.</span></span> <span data-ttu-id="6e6d3-159">Im nächsten Schritt sehen Sie, wie der Auftrag manuell ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-159">The next step shows you how to manually execute the job.</span></span> <span data-ttu-id="6e6d3-160">Sie können auch einen Zeitplan angeben, der den Auftrag ausführt, wenn Sie ihn überwachen.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-160">You can also specify a schedule that executes the job when you are monitoring it.</span></span>  
  
13. <span data-ttu-id="6e6d3-161">Klicken Sie im Dialogfeld **Neuer Auftrag** auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-161">In the **New Job** dialog box, click **OK**.</span></span>  
  
14. <span data-ttu-id="6e6d3-162">Erweitern Sie im **Objekt-Explorer**den Eintrag **Aufträge**, klicken Sie mit der rechten Maustaste auf den erstellten Auftrag, und wählen Sie anschließend **Auftrag starten bei Schritt**aus.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-162">In **Object Explorer**, expand **Jobs**, right-click the job you created, and then select **Start Job at Step**.</span></span>  
  
     <span data-ttu-id="6e6d3-163">Da der Auftrag nur einen Schritt hat, wird der Auftrag sofort ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-163">Because the job has only one step, the job executes immediately.</span></span> <span data-ttu-id="6e6d3-164">Wenn der Auftrag aus mehr als einem Schritt besteht, können Sie angeben, mit welchem Schritt der Auftrag beginnen soll.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-164">If the job contains more than one step, you can select the step at which the job should start.</span></span>  
  
15. <span data-ttu-id="6e6d3-165">Klicken Sie nach Abschluss des Auftrags auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-165">When the job finishes, click **Close**.</span></span>  
  
## <a name="example-2-batch-processing-a-dimension-and-a-partition-in-a-scheduled-task"></a><span data-ttu-id="6e6d3-166">Beispiel 2: Batchverarbeitung einer Dimension und einer Partition in einem geplanten Task</span><span class="sxs-lookup"><span data-stu-id="6e6d3-166">Example 2: Batch processing a dimension and a partition in a scheduled task</span></span>  
 <span data-ttu-id="6e6d3-167">Die Prozeduren in diesem Beispiel veranschaulichen, wie Sie einen Auftrag erstellen und planen, der eine Batchverarbeitung für eine [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbankdimension ausführt und zur gleichen Zeit eine Cubepartition verarbeitet, deren Aggregation von der Dimension abhängt.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-167">The procedures in this example demonstrate how to create and schedule a job that batch processes an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database dimension, and at the same time to process a  cube partition that depends on the dimension for aggregation.</span></span> <span data-ttu-id="6e6d3-168">Weitere Informationen zur Batchverarbeitung von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]-Objekten finden Sie unter [Batchverarbeitung &#40;Analysis Services&#41;](../multidimensional-models/batch-processing-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="6e6d3-168">For more information about batch processing of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects, see [Batch Processing &#40;Analysis Services&#41;](../multidimensional-models/batch-processing-analysis-services.md).</span></span>  
  
###  <a name="create-a-script-for-batch-processing-a-dimension-and-partition-in-a-sql-server-agent-job"></a><a name="bkmk_BatchProcess"></a><span data-ttu-id="6e6d3-169">Erstellen eines Skripts für die Batch Verarbeitung einer Dimension und einer Partition in einem SQL Server-Agent Auftrag</span><span class="sxs-lookup"><span data-stu-id="6e6d3-169">Create a script for batch processing a dimension and partition in a SQL Server Agent job</span></span>  
  
1.  <span data-ttu-id="6e6d3-170">Erweitern Sie unter Verwendung der gleichen Datenbank den Eintrag **Dimensionen**, klicken Sie mit der rechten Maustaste auf die **Customer** -Dimension, und wählen Sie **Verarbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-170">Using the same database, expand **Dimensions**, right-click the **Customer** dimension, and select **Process**.</span></span>  
  
2.  <span data-ttu-id="6e6d3-171">Überprüfen Sie im Dialogfeld **Dimension aufbereiten** in der Spalte **Verarbeitungsoptionen** unter **Objektliste**, ob die Option für diese Spalte **Vollständig verarbeiten**lautet.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-171">In the **Process Dimension** dialog box, in **Process Options** column under **Object list**, verify that the option for this column is **Process Full**.</span></span>  
  
3.  <span data-ttu-id="6e6d3-172">Klicken Sie auf **Skript**.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-172">Click **Script**.</span></span>  
  
     <span data-ttu-id="6e6d3-173">Dieser Schritt öffnet ein **XML-Abfragefenster** , welches das XMLA-Skript enthält, das die Dimension verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-173">This step opens an **XML Query** window that contains the XMLA script that processes the dimension.</span></span>  
  
4.  <span data-ttu-id="6e6d3-174">Klicken Sie im Dialogfeld **Dimension aufbereiten** auf **Abbrechen** , um das Dialogfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-174">In the **Process Dimension** dialog box, click **Cancel** to close the dialog box.</span></span>  
  
5.  <span data-ttu-id="6e6d3-175">Erweitern Sie **Cubes**, erweitern Sie **Adventure Works**, erweitern Sie **Measuregruppen**, erweitern Sie **Internet Sales**, erweitern Sie **Partitionen**, klicken Sie mit der rechten Maustaste in der Liste auf die letzte Partition, und wählen Sie anschließend **Verarbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-175">Expand **Cubes**, expand **Adventure Works**, expand **Measure Groups**, expand **Internet Sales**, expand **Partitions**, right-click the last partition in the list, and then select **Process**.</span></span>  
  
6.  <span data-ttu-id="6e6d3-176">Überprüfen Sie im Dialogfeld **Partition verarbeiten** in der Spalte **Verarbeitungsoptionen** unter **Objektliste**, ob die Option für diese Spalte **Vollständig verarbeiten**lautet.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-176">In the **Process Partition** dialog box, in the **Process Options** column under **Object list**, verify that the option for this column is **Process Full**.</span></span>  
  
7.  <span data-ttu-id="6e6d3-177">Klicken Sie auf **Skript**.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-177">Click **Script**.</span></span>  
  
     <span data-ttu-id="6e6d3-178">Dieser Schritt öffnet ein zweites **XML-Abfragefenster** , welches das XMLA-Skript enthält, das die Partition verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-178">This step opens a second **XML Query** window that contains the XMLA script that processes the partition.</span></span>  
  
8.  <span data-ttu-id="6e6d3-179">Klicken Sie im Dialogfeld **Partition verarbeiten** auf **Abbrechen** , um den Editor zu schließen.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-179">In the **Process Partition** dialog box, click **Cancel** to close the editor.</span></span>  
  
     <span data-ttu-id="6e6d3-180">An diesem Punkt müssen Sie die zwei Skripts zusammenführen und sicherstellen, dass die Dimension zuerst verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-180">At this point you must merge the two scripts, and ensure that the dimension is processed first.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="6e6d3-181">Wenn die Partition zuerst verarbeitet wird, bewirkt die nachfolgende Dimensionsverarbeitung, dass die Partition nicht mehr verarbeitet ist.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-181">If the partition is processed first, the subsequent dimension processing causes the partition to become unprocessed.</span></span> <span data-ttu-id="6e6d3-182">Die Partition würde dann eine zweite Verarbeitung erfordern, um den Status "Verarbeitet" aufzuweisen.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-182">The partition would then require a second processing to reach a processed state.</span></span>  
  
9. <span data-ttu-id="6e6d3-183">Markieren Sie im **XMLA-Abfragefenster** , das das XMLA-Skript enthält, das die Partition verarbeitet, den Code in den Tags `Batch` und `Parallel` , klicken Sie mit der rechten Maustaste auf das markierte Skript, und wählen Sie **Kopieren**aus.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-183">In the **XMLA Query** window that contains the XMLA script that processes the partition, highlight the code inside the `Batch` and `Parallel` tags, right-click the highlighted script, and select **Copy**.</span></span>  
  
    ```  
    <Process xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
        <Object>  
          <DatabaseID> Adventure Works DW Multidimensional</DatabaseID>  
          <CubeID>Adventure Works</CubeID>  
          <MeasureGroupID>Fact Internet Sales 1</MeasureGroupID>  
          <PartitionID> Internet_Sales_2004</PartitionID>  
        </Object>  
        <Type>ProcessFull</Type>  
        <WriteBackTableCreation>UseExisting</WriteBackTableCreation>  
      </Process>  
    ```  
  
10. <span data-ttu-id="6e6d3-184">Öffnen Sie das **XMLA-Abfragefenster** , welches das XMLA-Skript enthält, das die Dimension verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-184">Open the **XMLA Query** window that contains the XMLA script that processes the dimension.</span></span> <span data-ttu-id="6e6d3-185">Klicken Sie mit der rechten Maustaste innerhalb des Skripts links vom `</Process>` -Tag, und wählen Sie **Einfügen**aus.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-185">Right-click within the script to the left of the `</Process>` tag and select **Paste**.</span></span>  
  
     <span data-ttu-id="6e6d3-186">Im folgenden Beispiel sehen Sie das überarbeitete XMLA-Skript.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-186">The following example shows the revised XMLA script.</span></span>  
  
    ```  
    <Batch xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
     <Parallel>  
      <Process xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
        <Object>  
          <DatabaseID>Adventure Works DW Multidimensional</DatabaseID>  
          <DimensionID>Dim Customer</DimensionID>  
        </Object>  
        <Type>ProcessFull</Type>  
        <WriteBackTableCreation>UseExisting</WriteBackTableCreation>  
      </Process>  
      <Process xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
        <Object>  
          <DatabaseID>Adventure Works DW Multidimensional</DatabaseID>  
          <CubeID>Adventure Works</CubeID>  
          <MeasureGroupID>Fact Internet Sales 1</MeasureGroupID>  
          <PartitionID>Internet_Sales_2004</PartitionID>  
        </Object>  
        <Type>ProcessFull</Type>  
        <WriteBackTableCreation>UseExisting</WriteBackTableCreation>  
      </Process>  
     </Parallel>  
    </Batch>  
    ```  
  
11. <span data-ttu-id="6e6d3-187">Markieren Sie das überarbeitete XMLA-Skript, klicken Sie mit der rechten Maustaste auf das markierte Skript, und wählen Sie **Kopieren**.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-187">Highlight the revised XMLA script, right-click the highlighted script, and select **Copy.**</span></span>  
  
12. <span data-ttu-id="6e6d3-188">Dieser Schritt kopiert das XMLA-Skript in die Windows-Zwischenablage.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-188">This step copies the XMLA script to the Windows Clipboard.</span></span> <span data-ttu-id="6e6d3-189">Sie können das XMLA-Skript in der Zwischenablage lassen, in einer Datei speichern oder es in Editor oder einen anderen Text-Editor einfügen.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-189">You can leave the XMLA script in the Clipboard, save it to a file, or paste it into Notepad or another text editor.</span></span>  
  
###  <a name="create-and-schedule-the-batch-processing-job"></a><a name="bkmk_Scheduling"></a> <span data-ttu-id="6e6d3-190">Erstellen und Planen des Batchverarbeitungsauftrags</span><span class="sxs-lookup"><span data-stu-id="6e6d3-190">Create and schedule the batch processing job</span></span>  
  
1.  <span data-ttu-id="6e6d3-191">Stellen Sie eine Verbindung mit einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]her, und öffnen Sie den Objekt-Explorer.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-191">Connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and then open Object Explorer.</span></span>  
  
2.  <span data-ttu-id="6e6d3-192">Erweitern Sie **SQL Server-Agent**.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-192">Expand **SQL Server Agent**.</span></span> <span data-ttu-id="6e6d3-193">Starten Sie den Dienst, wenn er nicht bereits ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-193">Start the service if is not running.</span></span>  
  
3.  <span data-ttu-id="6e6d3-194">Klicken Sie mit der rechten Maustaste auf **Aufträge** , und wählen Sie **Neuer Auftrag**aus.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-194">Right-click **Jobs** and select **New Job**.</span></span>  
  
4.  <span data-ttu-id="6e6d3-195">Geben Sie im Dialogfeld **Neuer Auftrag** unter **Name**einen Auftragsnamen ein.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-195">In the **New Job** dialog box, enter a job name in **Name**.</span></span>  
  
5.  <span data-ttu-id="6e6d3-196">Klicken Sie in **Schritte**auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-196">In **Steps**, click **New**.</span></span>  
  
6.  <span data-ttu-id="6e6d3-197">Geben Sie im Dialogfeld **Neuer Auftragsschritt** unter **Schrittname**einen Schrittnamen ein.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-197">In the **New Job Step** dialog box, enter a step name in **Step Name**.</span></span>  
  
7.  <span data-ttu-id="6e6d3-198">Wählen Sie unter **Typ**die Option **SQL Server Analysis Services-Befehl**aus.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-198">In **Type**, select **SQL Server Analysis Services Command**.</span></span>  
  
8.  <span data-ttu-id="6e6d3-199">Wählen Sie unter **Ausführen als**das **SQL Server-Agent-Dienstkonto**aus.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-199">In **Run as**, select the **SQL Server Agent Service Account**.</span></span> <span data-ttu-id="6e6d3-200">Aus dem Abschnitt zu Voraussetzungen wissen Sie bereits, dass dieses Konto über Administratorberechtigungen für Analysis Services verfügen muss.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-200">Recall from the Prerequisites section that this account must have administrative permissions on Analysis Services.</span></span>  
  
9. <span data-ttu-id="6e6d3-201">Geben Sie unter **Server**den Servernamen der Analysis Services-Instanz an.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-201">In **Server**, specify the server name of the Analysis Services instance.</span></span>  
  
10. <span data-ttu-id="6e6d3-202">Klicken Sie unter **Befehl**mit der rechten Maustaste, und wählen Sie **Einfügen**aus.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-202">In **Command**, right-click and select **Paste**.</span></span>  
  
11. <span data-ttu-id="6e6d3-203">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-203">Click **OK**.</span></span>  
  
12. <span data-ttu-id="6e6d3-204">Klicken Sie auf der Seite **Zeitpläne** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-204">In the **Schedules** page, click **New**.</span></span>  
  
13. <span data-ttu-id="6e6d3-205">Geben Sie im Dialogfeld **Neuer Auftragszeitplan** einen Namen für den Zeitplan in das Feld **Name**ein, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-205">In the **New Job Schedule** dialog box, enter a schedule name in **Name**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="6e6d3-206">Dieser Schritt erstellt einen Zeitplan für Sonntag 00:00 Uhr.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-206">This step creates a schedule for Sunday at 12:00 AM.</span></span> <span data-ttu-id="6e6d3-207">Im nächsten Schritt sehen Sie, wie der Auftrag manuell ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-207">The next step shows you how to manually execute the job.</span></span> <span data-ttu-id="6e6d3-208">Sie können auch einen Zeitplan auswählen, der den Auftrag ausführt, wenn Sie ihn überwachen.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-208">You can also select a schedule which will execute the job when you are monitoring it.</span></span>  
  
14. <span data-ttu-id="6e6d3-209">Klicken Sie auf **OK** , um das Dialogfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-209">Click **OK** to close the dialog box.</span></span>  
  
15. <span data-ttu-id="6e6d3-210">Erweitern Sie im **Objekt-Explorer**den Eintrag **Aufträge**, klicken Sie mit der rechten Maustaste auf den erstellten Auftrag, und wählen Sie **Auftrag starten bei Schritt**aus.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-210">In **Object Explorer**, expand **Jobs**, right-click the job you created, and select **Start Job at Step**.</span></span>  
  
     <span data-ttu-id="6e6d3-211">Da der Auftrag nur einen Schritt hat, wird der Auftrag sofort ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-211">Because the job has only one step, the job executes immediately.</span></span> <span data-ttu-id="6e6d3-212">Wenn der Auftrag aus mehr als einem Schritt besteht, können Sie angeben, mit welchem Schritt der Auftrag beginnen soll.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-212">If the job contains more than one step, you can select the step at which the job should start.</span></span>  
  
16. <span data-ttu-id="6e6d3-213">Klicken Sie nach Abschluss des Auftrags auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="6e6d3-213">When the job finishes, click **Close**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e6d3-214">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6e6d3-214">See Also</span></span>  
 <span data-ttu-id="6e6d3-215">[Verarbeitungsoptionen und-Einstellungen &#40;Analysis Services&#41;](../multidimensional-models/processing-options-and-settings-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="6e6d3-215">[Processing Options and Settings &#40;Analysis Services&#41;](../multidimensional-models/processing-options-and-settings-analysis-services.md) </span></span>  
 [<span data-ttu-id="6e6d3-216">Skriptverwaltungsaufgaben in Analysis Services</span><span class="sxs-lookup"><span data-stu-id="6e6d3-216">Script Administrative Tasks in Analysis Services</span></span>](../script-administrative-tasks-in-analysis-services.md)  
  
  
