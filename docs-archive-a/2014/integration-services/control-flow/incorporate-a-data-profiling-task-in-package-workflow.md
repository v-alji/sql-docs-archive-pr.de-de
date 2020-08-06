---
title: Einschließen einer Datenprofilerstellungs-Task in den Paket-Workflow | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Data Profiling task [Integration Services], using output in workflow
ms.assetid: 39a51586-6977-4c45-b80b-0157a54ad510
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cd3544586ac99f66b961f7961e4f4af4d9e4a4c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616629"
---
# <a name="incorporate-a-data-profiling-task-in-package-workflow"></a><span data-ttu-id="064ed-102">Einschließen einer Datenprofilerstellungs-Tasks in den Paket-Workflow</span><span class="sxs-lookup"><span data-stu-id="064ed-102">Incorporate a Data Profiling Task in Package Workflow</span></span>
  <span data-ttu-id="064ed-103">Datenprofilerstellung und Cleanup sind in den Anfangsphasen keine Kandidaten für einen automatisierten Prozess.</span><span class="sxs-lookup"><span data-stu-id="064ed-103">Data profiling and cleanup are not candidates for an automated process in their early stages.</span></span> <span data-ttu-id="064ed-104">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] erfordert die Ausgabe des Datenprofilerstellungs-Tasks normalerweise eine visuelle Analyse und menschliches Urteilsvermögen, um zu bestimmen, ob gemeldete Verstöße von Bedeutung oder übertrieben sind.</span><span class="sxs-lookup"><span data-stu-id="064ed-104">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], the output of the Data Profiling task usually requires visual analysis and human judgment to determine whether reported violations are meaningful or excessive.</span></span> <span data-ttu-id="064ed-105">Auch nach Erkennen eines Datenqualitätsproblems ist nach wie vor ein sorgfältig durchdachter Plan erforderlich, der den besten Bereinigungsansatz beinhaltet.</span><span class="sxs-lookup"><span data-stu-id="064ed-105">Even after recognizing data quality problems, there still has to be a carefully thought-out plan that addresses the best approach for cleanup.</span></span>  
  
 <span data-ttu-id="064ed-106">Nachdem Kriterien für die Datenqualität festgelegt wurden, möchten Sie jedoch möglicherweise eine regelmäßige Analyse und Bereinigung der Datenquelle automatisieren.</span><span class="sxs-lookup"><span data-stu-id="064ed-106">However, after criteria for data quality have been established, you might want to automate a periodic analysis and cleanup of the data source.</span></span> <span data-ttu-id="064ed-107">Betrachten Sie folgende Szenarios:</span><span class="sxs-lookup"><span data-stu-id="064ed-107">Consider these scenarios:</span></span>  
  
-   <span data-ttu-id="064ed-108">**Überprüfen der Datenqualität vor dem inkrementellen Laden**</span><span class="sxs-lookup"><span data-stu-id="064ed-108">**Checking data quality before an incremental load**.</span></span> <span data-ttu-id="064ed-109">Berechnen Sie mit dem Datenprofilerstellungs-Task das Profil für das Spalten-NULL-Verhältnis neuer Daten, die für die CustomerName-Spalte in einer Customers-Tabelle bestimmt sind.</span><span class="sxs-lookup"><span data-stu-id="064ed-109">Use the Data Profiling task to compute the Column Null Ratio Profile of new data intended for the CustomerName column in a Customers table.</span></span> <span data-ttu-id="064ed-110">Wenn der Prozentanteil von NULL-Werten größer als 20 % ist, senden Sie eine E-Mail-Nachricht mit der Profilausgabe an den Operator, und beenden Sie das Paket.</span><span class="sxs-lookup"><span data-stu-id="064ed-110">If the percentage of null values is greater than 20%, send an e-mail message that contains the profile output to the operator and end the package.</span></span> <span data-ttu-id="064ed-111">Andernfalls setzen Sie das inkrementelle Laden fort.</span><span class="sxs-lookup"><span data-stu-id="064ed-111">Otherwise, continue the incremental load.</span></span>  
  
-   <span data-ttu-id="064ed-112">**Automatisieren des Cleanups, wenn die angegebenen Bedingungen erfüllt werden.**</span><span class="sxs-lookup"><span data-stu-id="064ed-112">**Automating cleanup when the specified conditions are met**.</span></span> <span data-ttu-id="064ed-113">Berechnen Sie mit dem Datenprofilerstellungs-Task das Wertinklusionsprofil der State-Spalte anhand einer Suchtabelle für Status und der ZIP Code/Postal Code-Spalte anhand einer Suchtabelle für Postleitzahlen.</span><span class="sxs-lookup"><span data-stu-id="064ed-113">Use the Data Profiling task to compute the Value Inclusion Profile of the State column against a lookup table of states, and of the ZIP Code/Postal Code column against a lookup table of zip codes.</span></span> <span data-ttu-id="064ed-114">Wenn die Einschlussstärke der Statuswerte kleiner als 80 % ist, die Einschlussstärke der Postleitzahlwerte hingegen größer als 99 %, weist dies auf zwei Dinge hin.</span><span class="sxs-lookup"><span data-stu-id="064ed-114">If the inclusion strength of the state values is less than 80%, but the inclusion strength of the ZIP Code/Postal Code values is greater than 99%, this indicates two things.</span></span> <span data-ttu-id="064ed-115">Erstens sind die Statusdaten ungültig.</span><span class="sxs-lookup"><span data-stu-id="064ed-115">First, the state data is bad.</span></span> <span data-ttu-id="064ed-116">Zweitens sind die Postleitzahldaten gültig.</span><span class="sxs-lookup"><span data-stu-id="064ed-116">Second, the ZIP Code/Postal Code data is good.</span></span> <span data-ttu-id="064ed-117">Starten Sie einen Datenflusstask, der die Statusdaten durch eine Suche des richtigen Werts aus dem aktuellen Postleitzahlwert bereinigt.</span><span class="sxs-lookup"><span data-stu-id="064ed-117">Launch a Data Flow task that cleans up the state data by performing a lookup of the correct state value from the current Zip Code/Postal Code value.</span></span>  
  
 <span data-ttu-id="064ed-118">Nachdem Sie einen Workflow vorliegen haben, in den Sie den Datenflusstask integrieren können, müssen Sie sich mit den Schritten, die zum Hinzufügen dieses Tasks erforderlich sind, vertraut machen.</span><span class="sxs-lookup"><span data-stu-id="064ed-118">After you have a workflow into which you can incorporate the Data Flow task, you have to understand the steps that are required to add this task.</span></span> <span data-ttu-id="064ed-119">Im nächsten Abschnitt wird der allgemeine Prozess zur Integration des Datenflusstasks beschrieben.</span><span class="sxs-lookup"><span data-stu-id="064ed-119">The next section describes the general process of incorporating the Data Flow task.</span></span> <span data-ttu-id="064ed-120">In den beiden letzten Abschnitten wird beschrieben, wie Sie den Datenflusstask entweder direkt mit einer Datenquelle oder mit transformierten Daten aus dem Datenfluss verbinden.</span><span class="sxs-lookup"><span data-stu-id="064ed-120">The final two sections describe how to connect the Data Flow task either directly to a data source or to transformed data from the Data Flow.</span></span>  
  
## <a name="defining-a-general-workflow-for-the-data-flow-task"></a><span data-ttu-id="064ed-121">Definieren eines allgemeinen Workflows für den Datenflusstask</span><span class="sxs-lookup"><span data-stu-id="064ed-121">Defining a General Workflow for the Data Flow Task</span></span>  
 <span data-ttu-id="064ed-122">Das folgende Verfahren erklärt den allgemeinen Ansatz zur Verwendung der Ausgabe des Datenprofilerstellungs-Tasks im Workflow eines Pakets.</span><span class="sxs-lookup"><span data-stu-id="064ed-122">The following procedure outlines the general approach for using the output of the Data Profiling task in the workflow of a package.</span></span>  
  
#### <a name="to-use-the-output-of-the-data-profiling-task-programmatically-in-a-package"></a><span data-ttu-id="064ed-123">So verwenden Sie die Ausgabe des Datenprofilerstellungs-Tasks programmgesteuert in einem Paket</span><span class="sxs-lookup"><span data-stu-id="064ed-123">To use the output of the Data Profiling task programmatically in a package</span></span>  
  
1.  <span data-ttu-id="064ed-124">Fügen Sie den Datenprofilerstellungs-Task zu einem Paket hinzu, und konfigurieren Sie ihn.</span><span class="sxs-lookup"><span data-stu-id="064ed-124">Add and configure the Data Profiling task in a package.</span></span>  
  
2.  <span data-ttu-id="064ed-125">Konfigurieren Sie Paketvariablen, um die Werte, die Sie von den Profilergebnissen abrufen möchten, zu speichern.</span><span class="sxs-lookup"><span data-stu-id="064ed-125">Configure package variables to hold the values that you want to retrieve from the profile results.</span></span>  
  
3.  <span data-ttu-id="064ed-126">Fügen Sie einen Skripttask hinzu, und konfigurieren Sie ihn.</span><span class="sxs-lookup"><span data-stu-id="064ed-126">Add and configure a Script task.</span></span> <span data-ttu-id="064ed-127">Verbinden Sie den Skripttask mit dem Datenprofilerstellungs-Task.</span><span class="sxs-lookup"><span data-stu-id="064ed-127">Connect the Script task to the Data Profiling task.</span></span> <span data-ttu-id="064ed-128">Schreiben Sie Code in den Skripttask, der die gewünschten Werte aus der Ausgabedatei des Datenprofilerstellungs-Tasks liest und die Paketvariablen auffüllt.</span><span class="sxs-lookup"><span data-stu-id="064ed-128">In the Script task, write code that reads the desired values from the output file of the Data Profiling task and populates the package variables.</span></span>  
  
4.  <span data-ttu-id="064ed-129">Verwenden Sie in den Rangfolgeneinschränkungen, mit denen der Skripttask mit Downstream-Verzweigungen verbunden wird, Ausdrücke, die den Workflow anhand der Werte der Variablen steuern.</span><span class="sxs-lookup"><span data-stu-id="064ed-129">In the precedence constraints that connect the Script task to downstream branches in the workflow, write expressions that use the values of the variables to direct the workflow.</span></span>  
  
 <span data-ttu-id="064ed-130">Beim Integrieren des Datenprofilerstellungs-Tasks in den Workflow eines Pakets berücksichtigen Sie die beiden folgenden Taskfunktionen:</span><span class="sxs-lookup"><span data-stu-id="064ed-130">When incorporating the Data Profiling task into the workflow of a package, keep these two features of the task in mind:</span></span>  
  
-   <span data-ttu-id="064ed-131">**Taskausgabe**.</span><span class="sxs-lookup"><span data-stu-id="064ed-131">**Task output**.</span></span> <span data-ttu-id="064ed-132">Der Datenprofilerstellungs-Task schreibt die Ausgabe in eine Datei oder eine Paketvariable im XML-Format, das dem Schema DataProfile.xsd entsprechend strukturiert ist.</span><span class="sxs-lookup"><span data-stu-id="064ed-132">The Data Profiling task writes its output to a file or a package variable in XML format according to the DataProfile.xsd schema.</span></span> <span data-ttu-id="064ed-133">Daher müssen Sie die XML-Ausgabe abfragen, wenn Sie die Profilergebnisse im bedingten Workflow eines Pakets verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="064ed-133">Therefore, you have to query the XML output if you want to use the profile results in the conditional workflow of a package.</span></span> <span data-ttu-id="064ed-134">Zur Abfrage dieser XML-Ausgabe verwenden Sie am besten die Xpath-Abfragesprache.</span><span class="sxs-lookup"><span data-stu-id="064ed-134">You can easily use the Xpath query language to query this XML output.</span></span> <span data-ttu-id="064ed-135">Um sich die Struktur dieser XML-Ausgabe anzusehen, können Sie eine Beispielausgabedatei oder das Schema selbst öffnen.</span><span class="sxs-lookup"><span data-stu-id="064ed-135">To study the structure of this XML output, you can open a sample output file or the schema itself.</span></span> <span data-ttu-id="064ed-136">Sie können zum Öffnen der Ausgabedatei oder des Schemas [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], einen anderen XML-Editor oder einen Text-Editor wie Notepad verwenden.</span><span class="sxs-lookup"><span data-stu-id="064ed-136">To open the output file or schema, you can use [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], another XML editor, or a text editor, such as Notepad.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="064ed-137">Einige der im Datenprofil-Viewer angezeigten Profilergebnisse sind berechnete Werte, die nicht direkt in der Ausgabe zu finden sind.</span><span class="sxs-lookup"><span data-stu-id="064ed-137">Some of the profile results that are displayed in the Data Profile Viewer are calculated values that are not directly found in the output.</span></span> <span data-ttu-id="064ed-138">Die Ausgabe des Profils für das Spalten-NULL-Verhältnis enthält beispielsweise die Gesamtzahl der Zeilen und die Anzahl der Zeilen mit NULL-Werten.</span><span class="sxs-lookup"><span data-stu-id="064ed-138">For example, the output of the Column Null Ratio Profile contains the total number of rows and the number of rows that contain null values.</span></span> <span data-ttu-id="064ed-139">Zur Berechnung des Spalten-NULL-Verhältnisses müssen Sie diese beiden Werte abfragen und anschließend den Prozentanteil der Zeilen mit NULL-Werten berechnen.</span><span class="sxs-lookup"><span data-stu-id="064ed-139">You have to query these two values, and then calculate the percentage of rows that contain null values, to obtain the column null ratio.</span></span>  
  
-   <span data-ttu-id="064ed-140">**Taskeingabe**.</span><span class="sxs-lookup"><span data-stu-id="064ed-140">**Task input**.</span></span> <span data-ttu-id="064ed-141">Der Datenprofilerstellungs-Task liest seine Eingabe aus [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Tabellen.</span><span class="sxs-lookup"><span data-stu-id="064ed-141">The Data Profiling task reads its input from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tables.</span></span> <span data-ttu-id="064ed-142">Daher müssen Sie die im Speicher befindlichen Daten in Stagingtabellen speichern, wenn Sie ein Profil für Daten erstellen möchten, die bereits geladen und in den Datenfluss transformiert wurden.</span><span class="sxs-lookup"><span data-stu-id="064ed-142">Therefore, you have to save data that is in memory to staging tables if you want to profile data that has already been loaded and transformed in the data flow.</span></span>  
  
 <span data-ttu-id="064ed-143">In den folgenden Abschnitten wird beschrieben, wie dieser allgemeine Workflow auf Profildaten angewendet wird, die direkt aus einer externen Datenquelle oder transformiert aus dem Datenflusstask stammen.</span><span class="sxs-lookup"><span data-stu-id="064ed-143">The following sections apply this general workflow to profiling data that comes directly from an external data source or that comes transformed from the Data Flow task.</span></span> <span data-ttu-id="064ed-144">In diesen Abschnitten wird außerdem erklärt, wie die Eingabe- und Ausgabeanforderungen des Datenflusstasks behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="064ed-144">These sections also show how to handle the input and output requirements of the Data Flow task.</span></span>  
  
## <a name="connecting-the-data-profiling-task-directly-to-an-external-data-source"></a><span data-ttu-id="064ed-145">Direktes Verbinden des Datenprofilerstellungs-Tasks mit einer externen Datenquelle</span><span class="sxs-lookup"><span data-stu-id="064ed-145">Connecting the Data Profiling Task Directly to an External Data Source</span></span>  
 <span data-ttu-id="064ed-146">Der Datenprofilerstellungs-Task erstellt Profile für Daten, die direkt aus einer Datenquelle stammen.</span><span class="sxs-lookup"><span data-stu-id="064ed-146">The Data Profiling task can profile data that comes directly from a data source.</span></span>  <span data-ttu-id="064ed-147">Zur Veranschaulichung dieser Funktion wird im folgenden Beispiel anhand des Datenprofilerstellungs-Tasks ein Profil für ein Spalten-NULL-Verhältnis für die Spalten der Person.Address-Tabelle in der [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] -Datenbank berechnet.</span><span class="sxs-lookup"><span data-stu-id="064ed-147">To illustrate this capability, the following example uses the Data Profiling task to compute a Column Null Ratio Profile on the columns of the Person.Address table in the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] database.</span></span> <span data-ttu-id="064ed-148">Anschließend werden die Ergebnisse mithilfe eines Skripttasks aus der Ausgabedatei abgerufen, und Paketvariablen, die zur Steuerung des Workflows dienen können, werden aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="064ed-148">Then, this example uses a Script task to retrieve the results from the output file and populate package variables that can be used to direct workflow.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="064ed-149">Für dieses einfache Beispiel wurde die AddressLine2-Spalte ausgewählt, da diese Spalte einen hohen Anteil an NULL-Werten enthält.</span><span class="sxs-lookup"><span data-stu-id="064ed-149">The AddressLine2 column was selected for this simple example because this column contains a high percentage of null values.</span></span>  
  
 <span data-ttu-id="064ed-150">Dieses Beispiel umfasst die folgenden Schritte:</span><span class="sxs-lookup"><span data-stu-id="064ed-150">This example consists of the following steps:</span></span>  
  
-   <span data-ttu-id="064ed-151">Konfigurieren der Verbindungs-Manager, die die Verbindung zur externen Datenquelle und zur Ausgabedatei mit den Profilergebnissen herstellen.</span><span class="sxs-lookup"><span data-stu-id="064ed-151">Configuring the connection managers that connect to the external data source and to the output file that will contain the profile results.</span></span>  
  
-   <span data-ttu-id="064ed-152">Konfigurieren der Paketvariablen, die die vom Datenprofilerstellungs-Task benötigten Werte enthalten.</span><span class="sxs-lookup"><span data-stu-id="064ed-152">Configuring the package variables that will hold the values needed by the Data Profiling task.</span></span>  
  
-   <span data-ttu-id="064ed-153">Konfigurieren des Datenprofilerstellungs-Tasks, um das Profil für das Spalten-NULL-Verhältnis zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="064ed-153">Configuring the Data Profiling task to compute the Column Null Ratio Profile.</span></span>  
  
-   <span data-ttu-id="064ed-154">Konfigurieren des Skripttasks, um die XML-Ausgabe vom Datenprofilerstellungs-Task zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="064ed-154">Configuring the Script task to work the XML output from the Data Profiling task.</span></span>  
  
-   <span data-ttu-id="064ed-155">Konfigurieren der Rangfolgeneinschränkungen, mit denen gesteuert wird, welche Downstream-Verzweigungen im Workflow basierend auf den Ergebnissen des Datenprofilerstellungs-Tasks ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="064ed-155">Configuring the precedence constraints that will control which downstream branches in the workflow are run based on the results of the Data Profiling task.</span></span>  
  
### <a name="configure-the-connection-managers"></a><span data-ttu-id="064ed-156">Konfigurieren der Verbindungs-Manager</span><span class="sxs-lookup"><span data-stu-id="064ed-156">Configure the Connection Managers</span></span>  
 <span data-ttu-id="064ed-157">Dieses Beispiel umfasst zwei Verbindungs-Manager:</span><span class="sxs-lookup"><span data-stu-id="064ed-157">For this example, there are two connection managers:</span></span>  
  
-   <span data-ttu-id="064ed-158">Einen [!INCLUDE[vstecado](../../includes/vstecado-md.md)] -Verbindungs-Manager, der eine Verbindung mit der [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] -Datenbank herstellt.</span><span class="sxs-lookup"><span data-stu-id="064ed-158">An [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager that connects to the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] database.</span></span>  
  
-   <span data-ttu-id="064ed-159">Einen Dateiverbindungs-Manager, der die Ausgabedatei erstellt, in der die Ergebnisse des Datenprofilerstellungs-Tasks gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="064ed-159">A File connection manager that creates the output file that will hold the results of the Data Profiling task.</span></span>  
  
##### <a name="to-configure-the-connection-managers"></a><span data-ttu-id="064ed-160">So konfigurieren Sie die Verbindungs-Manager</span><span class="sxs-lookup"><span data-stu-id="064ed-160">To configure the connection managers</span></span>  
  
1.  <span data-ttu-id="064ed-161">Erstellen Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]ein neues [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Paket.</span><span class="sxs-lookup"><span data-stu-id="064ed-161">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], create a new [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package.</span></span>  
  
2.  <span data-ttu-id="064ed-162">Fügen Sie den [!INCLUDE[vstecado](../../includes/vstecado-md.md)] -Verbindungs-Manager zum Paket hinzu.</span><span class="sxs-lookup"><span data-stu-id="064ed-162">Add an [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager to the package.</span></span> <span data-ttu-id="064ed-163">Konfigurieren Sie diesen Verbindungs-Manager für die Verwendung des .NET-Datenanbieters für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SqlClient) und für die Verbindung mit einer verfügbaren Instanz der [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] -Datenbank.</span><span class="sxs-lookup"><span data-stu-id="064ed-163">Configure this connection manager to use the NET Data Provider for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SqlClient) and to connect to an available instance of the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] database.</span></span>  
  
     <span data-ttu-id="064ed-164">Standardmäßig trägt der Verbindungs-Manager den folgenden Namen: \<server name>.AdventureWorks1.</span><span class="sxs-lookup"><span data-stu-id="064ed-164">By default, the connection manager has the following name: \<server name>.AdventureWorks1.</span></span>  
  
3.  <span data-ttu-id="064ed-165">Fügen Sie einen Dateiverbindungs-Manager zum Paket hinzu.</span><span class="sxs-lookup"><span data-stu-id="064ed-165">Add a File connection manager to the package.</span></span> <span data-ttu-id="064ed-166">Konfigurieren Sie diesen Verbindungs-Manager für das Erstellen der Ausgabedatei für den Datenprofilerstellungs-Task.</span><span class="sxs-lookup"><span data-stu-id="064ed-166">Configure this connection manager to create the output file for the Data Profiling task.</span></span>  
  
     <span data-ttu-id="064ed-167">In diesem Beispiel wird der Dateiname "DataProfile1.xml" verwendet.</span><span class="sxs-lookup"><span data-stu-id="064ed-167">This example uses the file name, DataProfile1.xml.</span></span> <span data-ttu-id="064ed-168">Standardmäßig ist der Name des Verbindungs-Managers mit dem Dateinamen identisch.</span><span class="sxs-lookup"><span data-stu-id="064ed-168">By default, the connection manager has the same name as the file.</span></span>  
  
### <a name="configure-the-package-variables"></a><span data-ttu-id="064ed-169">Konfigurieren der Paketvariablen</span><span class="sxs-lookup"><span data-stu-id="064ed-169">Configure the Package Variables</span></span>  
 <span data-ttu-id="064ed-170">In diesem Beispiel werden zwei Paketvariablen verwendet:</span><span class="sxs-lookup"><span data-stu-id="064ed-170">This example uses two package variables:</span></span>  
  
-   <span data-ttu-id="064ed-171">Die ProfileConnectionName-Variable übergibt den Namen des Dateiverbindungs-Managers an den Skripttask.</span><span class="sxs-lookup"><span data-stu-id="064ed-171">The ProfileConnectionName variable passes the name of the File connection manager to the Script task.</span></span>  
  
-   <span data-ttu-id="064ed-172">Die AddressLine2NullRatio-Variable übergibt das berechnete NULL-Verhältnis für diese Spalte vom Skripttask an das Paket.</span><span class="sxs-lookup"><span data-stu-id="064ed-172">The AddressLine2NullRatio variable passes the calculated null ratio for this column out of the Script task to the package.</span></span>  
  
##### <a name="to-configure-the-package-variables-that-will-hold-profile-results"></a><span data-ttu-id="064ed-173">So konfigurieren Sie die Paketvariablen, die Profilergebnisse speichern</span><span class="sxs-lookup"><span data-stu-id="064ed-173">To configure the package variables that will hold profile results</span></span>  
  
-   <span data-ttu-id="064ed-174">Fügen Sie im Fenster **Variablen** die beiden folgenden Paketvariablen hinzu, und konfigurieren Sie sie:</span><span class="sxs-lookup"><span data-stu-id="064ed-174">In the **Variables** window, add and configure the following two package variables:</span></span>  
  
    -   <span data-ttu-id="064ed-175">Geben Sie den Namen `ProfileConnectionName` für eine der Variablen ein, und legen Sie den Typ dieser Variablen auf **String**fest.</span><span class="sxs-lookup"><span data-stu-id="064ed-175">Enter the name, `ProfileConnectionName`, for one of the variables and set the type of this variable to **String**.</span></span>  
  
    -   <span data-ttu-id="064ed-176">Geben Sie den Namen, `AddressLine2NullRatio` , für die andere Variable ein, und legen Sie den Typ dieser Variablen auf **Double**fest.</span><span class="sxs-lookup"><span data-stu-id="064ed-176">Enter the name, `AddressLine2NullRatio`, for the other variable and set the type of this variable to **Double**.</span></span>  
  
### <a name="configure-the-data-profiling-task"></a><span data-ttu-id="064ed-177">Konfigurieren des Datenprofilerstellungs-Tasks</span><span class="sxs-lookup"><span data-stu-id="064ed-177">Configure the Data Profiling Task</span></span>  
 <span data-ttu-id="064ed-178">Der Datenprofilerstellungs-Task muss wie folgt konfiguriert werden:</span><span class="sxs-lookup"><span data-stu-id="064ed-178">The Data Profiling task has to be configured in the following way:</span></span>  
  
-   <span data-ttu-id="064ed-179">Um die Daten zu verwenden, die der [!INCLUDE[vstecado](../../includes/vstecado-md.md)] -Verbindungs-Manager als Eingabe angibt.</span><span class="sxs-lookup"><span data-stu-id="064ed-179">To use the data that the [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager supplies as input.</span></span>  
  
-   <span data-ttu-id="064ed-180">Um ein Profil für ein Spalten-NULL-Verhältnis für die Eingabedaten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="064ed-180">To perform a Column Null Ratio profile on the input data.</span></span>  
  
-   <span data-ttu-id="064ed-181">Um die Profilergebnisse in der Datei zu speichern, die dem Dateiverbindungs-Manager zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="064ed-181">To save the profile results to the file that is associated with the File connection manager.</span></span>  
  
##### <a name="to-configure-the-data-profiling-task"></a><span data-ttu-id="064ed-182">So konfigurieren Sie den Datenprofilerstellungs-Task</span><span class="sxs-lookup"><span data-stu-id="064ed-182">To configure the Data Profiling task</span></span>  
  
1.  <span data-ttu-id="064ed-183">Fügen Sie der Ablaufsteuerung einen Datenprofilerstellungs-Task hinzu.</span><span class="sxs-lookup"><span data-stu-id="064ed-183">To the Control Flow, add a Data Profiling task.</span></span>  
  
2.  <span data-ttu-id="064ed-184">Öffnen Sie den **Editor für den Datenprofilerstellungs-Task** , um den Task zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="064ed-184">Open the **Data Profiling Task Editor** to configure the task.</span></span>  
  
3.  <span data-ttu-id="064ed-185">Wählen Sie auf der Seite **Allgemein** für **Ziel**den Namen des Dateiverbindungs-Managers aus, den Sie zuvor konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="064ed-185">On the **General** page of the editor, for **Destination**, select the name of the File connection manager that you have previously configured.</span></span>  
  
4.  <span data-ttu-id="064ed-186">Erstellen Sie auf der Seite **Profilanforderungen** des Editors ein neues Profil für ein Spalten-NULL-Verhältnis.</span><span class="sxs-lookup"><span data-stu-id="064ed-186">On the **Profile Requests** page of the editor, create a new Column Null Ratio Profile.</span></span>  
  
5.  <span data-ttu-id="064ed-187">Wählen Sie im Bereich **Anforderungseigenschaften** für **ConnectionManager**den [!INCLUDE[vstecado](../../includes/vstecado-md.md)] -Verbindungs-Manager aus, den Sie zuvor konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="064ed-187">In the **Request properties** pane, for **ConnectionManager**, select the [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager that you have previously configured.</span></span> <span data-ttu-id="064ed-188">Wählen Sie dann für **TableOrView**Person.Address aus.</span><span class="sxs-lookup"><span data-stu-id="064ed-188">Then, for **TableOrView**, select Person.Address.</span></span>  
  
6.  <span data-ttu-id="064ed-189">Schließen Sie den Editor für den Datenprofilerstellungs-Task.</span><span class="sxs-lookup"><span data-stu-id="064ed-189">Close the Data Profiling Task Editor.</span></span>  
  
### <a name="configure-the-script-task"></a><span data-ttu-id="064ed-190">Konfigurieren des Skripttasks</span><span class="sxs-lookup"><span data-stu-id="064ed-190">Configure the Script Task</span></span>  
 <span data-ttu-id="064ed-191">Der Skripttask muss so konfiguriert werden, dass die Ergebnisse aus der Ausgabedatei abgerufen und die zuvor konfigurierten Paketvariablen aufgefüllt werden.</span><span class="sxs-lookup"><span data-stu-id="064ed-191">The Script task has to be configured to retrieve the results from the output file and populate the package variables that were previously configured.</span></span>  
  
##### <a name="to-configure-the-script-task"></a><span data-ttu-id="064ed-192">So konfigurieren Sie den Skripttask</span><span class="sxs-lookup"><span data-stu-id="064ed-192">To configure the Script task</span></span>  
  
1.  <span data-ttu-id="064ed-193">Fügen Sie der Ablaufsteuerung einen Skripttask hinzu.</span><span class="sxs-lookup"><span data-stu-id="064ed-193">To the Control Flow, add a Script task.</span></span>  
  
2.  <span data-ttu-id="064ed-194">Verbinden Sie den Skripttask mit dem Datenprofilerstellungs-Task.</span><span class="sxs-lookup"><span data-stu-id="064ed-194">Connect the Script task to the Data Profiling task.</span></span>  
  
3.  <span data-ttu-id="064ed-195">Öffnen Sie den **Skripttask-Editor** , um den Task zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="064ed-195">Open the **Script Task Editor** to configure the task.</span></span>  
  
4.  <span data-ttu-id="064ed-196">Wählen Sie auf der Seite **Skript** die bevorzugte Programmiersprache aus.</span><span class="sxs-lookup"><span data-stu-id="064ed-196">On the **Script** page, select your preferred programming language.</span></span> <span data-ttu-id="064ed-197">Machen Sie die beiden Paketvariablen anschließend für das Skript verfügbar:</span><span class="sxs-lookup"><span data-stu-id="064ed-197">Then, make the two package variables available to the script:</span></span>  
  
    1.  <span data-ttu-id="064ed-198">Wählen Sie für die Option aus `ReadOnlyVariables` `ProfileConnectionName` .</span><span class="sxs-lookup"><span data-stu-id="064ed-198">For `ReadOnlyVariables`, select `ProfileConnectionName`.</span></span>  
  
    2.  <span data-ttu-id="064ed-199">Wählen Sie für " **Write Items variables**" aus `AddressLine2NullRatio` .</span><span class="sxs-lookup"><span data-stu-id="064ed-199">For **ReadWriteVariables**, select `AddressLine2NullRatio`.</span></span>  
  
5.  <span data-ttu-id="064ed-200">Wählen Sie **Skript bearbeiten** aus, um die Skriptentwicklungsumgebung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="064ed-200">Select **Edit Script** to open the script development environment.</span></span>  
  
6.  <span data-ttu-id="064ed-201">Fügen Sie einen Verweis zum System.Xml-Namespace hinzu.</span><span class="sxs-lookup"><span data-stu-id="064ed-201">Add a reference to the System.Xml namespace.</span></span>  
  
7.  <span data-ttu-id="064ed-202">Geben Sie den Beispielcode ein, der der Programmiersprache entspricht:</span><span class="sxs-lookup"><span data-stu-id="064ed-202">Enter the sample code that corresponds to your programming language:</span></span>  
  
    ```vb  
    Imports System  
    Imports Microsoft.SqlServer.Dts.Runtime  
    Imports System.Xml  
  
    Public Class ScriptMain  
  
      Private FILENAME As String = "C:\ TEMP\DataProfile1.xml"  
      Private PROFILE_NAMESPACE_URI As String = "https://schemas.microsoft.com/DataDebugger/"  
      Private NULLCOUNT_XPATH As String = _  
        "/default:DataProfile/default:DataProfileOutput/default:Profiles" & _  
        "/default:ColumnNullRatioProfile[default:Column[@Name='AddressLine2']]/default:NullCount/text()"  
      Private TABLE_XPATH As String = _  
        "/default:DataProfile/default:DataProfileOutput/default:Profiles" & _  
        "/default:ColumnNullRatioProfile[default:Column[@Name='AddressLine2']]/default:Table"  
  
      Public Sub Main()  
  
        Dim profileConnectionName As String  
        Dim profilePath As String  
        Dim profileOutput As New XmlDocument  
        Dim profileNSM As XmlNamespaceManager  
        Dim nullCountNode As XmlNode  
        Dim nullCount As Integer  
        Dim tableNode As XmlNode  
        Dim rowCount As Integer  
        Dim nullRatio As Double  
  
        ' Open output file.  
        profileConnectionName = Dts.Variables("ProfileConnectionName").Value.ToString()  
        profilePath = Dts.Connections(profileConnectionName).ConnectionString  
        profileOutput.Load(profilePath)  
        profileNSM = New XmlNamespaceManager(profileOutput.NameTable)  
        profileNSM.AddNamespace("default", PROFILE_NAMESPACE_URI)  
  
        ' Get null count for column.  
        nullCountNode = profileOutput.SelectSingleNode(NULLCOUNT_XPATH, profileNSM)  
        nullCount = CType(nullCountNode.Value, Integer)  
  
        ' Get row count for table.  
        tableNode = profileOutput.SelectSingleNode(TABLE_XPATH, profileNSM)  
        rowCount = CType(tableNode.Attributes("RowCount").Value, Integer)  
  
        ' Compute and return null ratio.  
        nullRatio = nullCount / rowCount  
        Dts.Variables("AddressLine2NullRatio").Value = nullRatio  
  
        Dts.TaskResult = Dts.Results.Success  
  
      End Sub  
  
    End Class  
    ```  
  
    ```csharp  
    using System;  
    using Microsoft.SqlServer.Dts.Runtime;  
    using System.Xml;  
  
    public class ScriptMain  
    {  
  
      private string FILENAME = "C:\\ TEMP\\DataProfile1.xml";  
      private string PROFILE_NAMESPACE_URI = "https://schemas.microsoft.com/DataDebugger/";  
      private string NULLCOUNT_XPATH = "/default:DataProfile/default:DataProfileOutput/default:Profiles" + "/default:ColumnNullRatioProfile[default:Column[@Name='AddressLine2']]/default:NullCount/text()";  
      private string TABLE_XPATH = "/default:DataProfile/default:DataProfileOutput/default:Profiles" + "/default:ColumnNullRatioProfile[default:Column[@Name='AddressLine2']]/default:Table";  
  
      public void Main()  
      {  
  
        string profileConnectionName;  
        string profilePath;  
        XmlDocument profileOutput = new XmlDocument();  
        XmlNamespaceManager profileNSM;  
        XmlNode nullCountNode;  
        int nullCount;  
        XmlNode tableNode;  
        int rowCount;  
        double nullRatio;  
  
        // Open output file.  
        profileConnectionName = Dts.Variables["ProfileConnectionName"].Value.ToString();  
        profilePath = Dts.Connections[profileConnectionName].ConnectionString;  
        profileOutput.Load(profilePath);  
        profileNSM = new XmlNamespaceManager(profileOutput.NameTable);  
        profileNSM.AddNamespace("default", PROFILE_NAMESPACE_URI);  
  
        // Get null count for column.  
        nullCountNode = profileOutput.SelectSingleNode(NULLCOUNT_XPATH, profileNSM);  
        nullCount = (int)nullCountNode.Value;  
  
        // Get row count for table.  
        tableNode = profileOutput.SelectSingleNode(TABLE_XPATH, profileNSM);  
        rowCount = (int)tableNode.Attributes["RowCount"].Value;  
  
        // Compute and return null ratio.  
        nullRatio = nullCount / rowCount;  
        Dts.Variables["AddressLine2NullRatio"].Value = nullRatio;  
  
        Dts.TaskResult = Dts.Results.Success;  
  
      }  
  
    }  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="064ed-203">Der in diesem Verfahren angezeigte Beispielcode veranschaulicht, wie die Ausgabe des Datenprofilerstellungs-Tasks aus einer Datei geladen wird.</span><span class="sxs-lookup"><span data-stu-id="064ed-203">The sample code shown in this procedure demonstrates how to load the output of the Data Profiling task from a file.</span></span> <span data-ttu-id="064ed-204">Um die Ausgabe des Datenprofilerstellungs-Tasks stattdessen aus einer Paketvariablen zu laden, verwenden Sie den alternativen Beispielcode, der im Anschluss an dieses Verfahren dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="064ed-204">To load the output of the Data Profiling task from a package variable instead, see the alternative sample code that follows this procedure.</span></span>  
  
8.  <span data-ttu-id="064ed-205">Schließen Sie die Skriptentwicklungsumgebung, und schließen Sie dann den Skripttask-Editor.</span><span class="sxs-lookup"><span data-stu-id="064ed-205">Close the script development environment, and then close the Script Task Editor.</span></span>  
  
#### <a name="alternative-code-reading-the-profile-output-from-a-variable"></a><span data-ttu-id="064ed-206">Alternativer Code: Lesen der Profilausgabe aus einer Variablen</span><span class="sxs-lookup"><span data-stu-id="064ed-206">Alternative Code-Reading the Profile Output from a Variable</span></span>  
 <span data-ttu-id="064ed-207">Das vorherige Verfahren zeigt, wie die Ausgabe des Datenprofilerstellungs-Tasks aus einer Datei geladen wird.</span><span class="sxs-lookup"><span data-stu-id="064ed-207">The previous procedure shows how to load the output of the Data Profiling task from a file.</span></span> <span data-ttu-id="064ed-208">Eine alternative Methode wäre allerdings, diese Ausgabe aus einer Paketvariablen zu laden.</span><span class="sxs-lookup"><span data-stu-id="064ed-208">However, an alternative method would be to load this output from a package variable.</span></span> <span data-ttu-id="064ed-209">Um die Ausgabe aus einer Variablen zu laden, müssen Sie den Beispielcode wie folgt ändern:</span><span class="sxs-lookup"><span data-stu-id="064ed-209">To load the output from a variable, you have to make the following changes to the sample code:</span></span>  
  
-   <span data-ttu-id="064ed-210">Rufen Sie die `LoadXml`-Methode der `XmlDocument`-Klasse statt der `Load`-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="064ed-210">Call the `LoadXml` method of the `XmlDocument` class instead of the `Load` method.</span></span>  
  
-   <span data-ttu-id="064ed-211">Fügen Sie im Skripttask-Editor den Namen der Paketvariablen, die die Profilausgabe enthält, zur `ReadOnlyVariables`-Liste des Tasks hinzu.</span><span class="sxs-lookup"><span data-stu-id="064ed-211">In the Script Task Editor, add the name of the package variable that contains the profile output to the task's `ReadOnlyVariables` list.</span></span>  
  
-   <span data-ttu-id="064ed-212">Übergeben Sie der `LoadXML`-Methode den string-Wert der Variablen, wie im folgenden Codebeispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="064ed-212">Pass the string value of the variable to the `LoadXML` method, as shown in the following code example.</span></span> <span data-ttu-id="064ed-213">(In diesem Beispiel wird "ProfileOutput" als Name der Paketvariable verwendet, die die Profilausgabe enthält.)</span><span class="sxs-lookup"><span data-stu-id="064ed-213">(This example uses "ProfileOutput" as the name of the package variable that contains the profile output.)</span></span>  
  
    ```vb  
    Dim outputString As String  
    outputString = Dts.Variables("ProfileOutput").Value.ToString()  
    ...  
    profileOutput.LoadXml(outputString)  
    ```  
  
    ```csharp  
    string outputString;  
    outputString = Dts.Variables["ProfileOutput"].Value.ToString();  
    ...  
    profileOutput.LoadXml(outputString);  
    ```  
  
### <a name="configure-the-precedence-constraints"></a><span data-ttu-id="064ed-214">Konfigurieren der Rangfolgeneinschränkungen</span><span class="sxs-lookup"><span data-stu-id="064ed-214">Configure the Precedence Constraints</span></span>  
 <span data-ttu-id="064ed-215">Die Rangfolgeneinschränkungen müssen so konfiguriert werden, dass gesteuert wird, welche Downstream-Verzweigungen im Workflow basierend auf den Ergebnissen des Datenprofilerstellungs-Tasks ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="064ed-215">The precedence constraints have to be configured to control which downstream branches in the workflow are run based on the results of the Data Profiling task.</span></span>  
  
##### <a name="to-configure-the-precedence-constraints"></a><span data-ttu-id="064ed-216">So konfigurieren Sie die Rangfolgeneinschränkungen</span><span class="sxs-lookup"><span data-stu-id="064ed-216">To configure the precedence constraints</span></span>  
  
-   <span data-ttu-id="064ed-217">Verwenden Sie in den Rangfolgeneinschränkungen, mit denen der Skripttask mit Downstream-Verzweigungen verbunden wird, Ausdrücke, die den Workflow anhand der Werte der Variablen steuern.</span><span class="sxs-lookup"><span data-stu-id="064ed-217">In the precedence constraints that connect the Script task to downstream branches in the workflow, write expressions that use the values of the variables to direct the workflow.</span></span>  
  
     <span data-ttu-id="064ed-218">Sie können beispielsweise den **Auswertungsvorgang** der Rangfolgeneinschränkung auf **Ausdruck und Einschränkung**festlegen.</span><span class="sxs-lookup"><span data-stu-id="064ed-218">For example, you might set the **Evaluation operation** of the precedence constraint to **Expression and Constraint**.</span></span> <span data-ttu-id="064ed-219">Dann können Sie `@AddressLine2NullRatio < .90` als Wert des Ausdrucks verwenden.</span><span class="sxs-lookup"><span data-stu-id="064ed-219">Then, you might use `@AddressLine2NullRatio < .90` as the value of the expression.</span></span> <span data-ttu-id="064ed-220">Dadurch folgt der Workflow dem ausgewählten Pfad, wenn die vorherigen Tasks erfolgreich sind und wenn der Anteil der NULL-Werte in der ausgewählten Spalte unter 90 % beträgt.</span><span class="sxs-lookup"><span data-stu-id="064ed-220">This causes the workflow to follow the selected path when the previous tasks succeed, and when the percentage of null values in the selected column is less than 90%.</span></span>  
  
## <a name="connecting-the-data-profiling-task-to-transformed-data-from-the-data-flow"></a><span data-ttu-id="064ed-221">Verbinden des Datenprofilerstellungs-Tasks mit transformierten Daten aus dem Datenfluss</span><span class="sxs-lookup"><span data-stu-id="064ed-221">Connecting the Data Profiling Task to Transformed Data from the Data Flow</span></span>  
 <span data-ttu-id="064ed-222">Statt direkt ein Profil der Daten aus einer Datenquelle zu erstellen, können Sie ein Profil für Daten erstellen, die bereits geladen und im Datenfluss transformiert wurden.</span><span class="sxs-lookup"><span data-stu-id="064ed-222">Instead of profiling data directly from a data source, you can profile data that has already been loaded and transformed in the data flow.</span></span> <span data-ttu-id="064ed-223">Der Datenprofilerstellungs-Task funktioniert jedoch nur mit persistenten Daten, nicht mit Daten im Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="064ed-223">However, the Data Profiling task works only against persisted data, not against in-memory data.</span></span> <span data-ttu-id="064ed-224">Aus diesem Grund müssen Sie zuerst eine Zielkomponente verwenden, um die transformierten Daten in einer Stagingtabelle zu speichern.</span><span class="sxs-lookup"><span data-stu-id="064ed-224">Therefore, you must first use a destination component to save the transformed data to a staging table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="064ed-225">Wenn Sie den Datenprofilerstellungs-Task konfigurieren, müssen Sie vorhandene Tabellen und Spalten auswählen.</span><span class="sxs-lookup"><span data-stu-id="064ed-225">When you configure the Data Profiling task, you have to select existing tables and columns.</span></span> <span data-ttu-id="064ed-226">Daher müssen Sie die Stagingtabelle zur Entwurfszeit erstellen, bevor Sie den Task konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="064ed-226">Therefore, you must create the staging table at design time before you can configure the task.</span></span> <span data-ttu-id="064ed-227">Mit anderen Worten, dieses Szenario erlaubt keine Verwendung einer temporären Tabelle, die zur Laufzeit erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="064ed-227">In other words, this scenario does not allow you to use a temporary table that is created at run time.</span></span>  
  
 <span data-ttu-id="064ed-228">Nachdem Sie die Daten in einer Stagingtabelle gespeichert haben, können Sie die folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="064ed-228">After saving the data to a staging table, you can do the following actions:</span></span>  
  
-   <span data-ttu-id="064ed-229">Erstellen Sie mit dem Datenprofilerstellungs-Task ein Profil der Daten.</span><span class="sxs-lookup"><span data-stu-id="064ed-229">Use the Data Profiling task to profile the data.</span></span>  
  
-   <span data-ttu-id="064ed-230">Lesen Sie mit einem Skripttask die Ergebnisse, wie weiter oben in diesem Thema beschrieben.</span><span class="sxs-lookup"><span data-stu-id="064ed-230">Use a Script task to read the results as described earlier in this topic.</span></span>  
  
-   <span data-ttu-id="064ed-231">Verwenden Sie diese Ergebnisse, um den nachfolgenden Workflow des Pakets zu steuern.</span><span class="sxs-lookup"><span data-stu-id="064ed-231">Use those results to direct the subsequent workflow of the package.</span></span>  
  
 <span data-ttu-id="064ed-232">Das folgende Verfahren bietet den allgemeinen Ansatz zur Verwendung des Datenprofilerstellungs-Tasks, um ein Profil der vom Datenfluss transformierten Daten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="064ed-232">The following procedure provides the general approach for using the Data Profiling task to profile data that has been transformed by the data flow.</span></span> <span data-ttu-id="064ed-233">Viele dieser Schritte sind identisch mit den bereits für die Erstellung eines Profils für Daten, die direkt aus einer externen Datenquelle stammen, beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="064ed-233">Many of these steps are similar to the ones described earlier for profiling data that comes directly from an external data source.</span></span> <span data-ttu-id="064ed-234">Schauen Sie sich diese bereits beschriebenen Schritte an, um weitere Informationen zum Konfigurieren der verschiedenen Komponenten zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="064ed-234">You might want to review those earlier steps for more information about how to configure the various components.</span></span>  
  
#### <a name="to-use-the-data-profiling-task-in-the-data-flow"></a><span data-ttu-id="064ed-235">So verwenden Sie den Datenprofilerstellungs-Task im Datenfluss</span><span class="sxs-lookup"><span data-stu-id="064ed-235">To use the Data Profiling task in the data flow</span></span>  
  
1.  <span data-ttu-id="064ed-236">Erstellen Sie ein Paket in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="064ed-236">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], create a package.</span></span>  
  
2.  <span data-ttu-id="064ed-237">Fügen Sie im Datenfluss die entsprechenden Quellen und die Transformationen hinzu, konfigurieren und verbinden Sie sie.</span><span class="sxs-lookup"><span data-stu-id="064ed-237">In the Data Flow, add, configure, and connect the appropriate sources and transformations.</span></span>  
  
3.  <span data-ttu-id="064ed-238">Fügen Sie im Datenfluss eine Zielkomponente, die die transformierten Daten in einer Stagingtabelle speichert, hinzu, konfigurieren und verbinden Sie sie.</span><span class="sxs-lookup"><span data-stu-id="064ed-238">In the Data Flow, add, configure, and connect a destination component that saves the transformed data to a staging table.</span></span>  
  
4.  <span data-ttu-id="064ed-239">Fügen Sie in der Ablaufsteuerung einen Datenprofilerstellungs-Task, der die gewünschten Profile anhand der transformierten Daten in der Stagingtabelle berechnet, hinzu, konfigurieren und verbinden Sie ihn.</span><span class="sxs-lookup"><span data-stu-id="064ed-239">In the Control Flow, add and configure a Data Profiling task that computes the desired profiles against the transformed data in the staging table.</span></span> <span data-ttu-id="064ed-240">Verbinden Sie den Datenprofilerstellungs-Task mit dem Datenflusstask.</span><span class="sxs-lookup"><span data-stu-id="064ed-240">Connect the Data Profiling task to the Data Flow task.</span></span>  
  
5.  <span data-ttu-id="064ed-241">Konfigurieren Sie Paketvariablen, um die Werte, die Sie von den Profilergebnissen abrufen möchten, zu speichern.</span><span class="sxs-lookup"><span data-stu-id="064ed-241">Configure package variables to hold the values that you want to retrieve from the profile results.</span></span>  
  
6.  <span data-ttu-id="064ed-242">Fügen Sie einen Skripttask hinzu, und konfigurieren Sie ihn.</span><span class="sxs-lookup"><span data-stu-id="064ed-242">Add and configure a Script task.</span></span> <span data-ttu-id="064ed-243">Verbinden Sie den Skripttask mit dem Datenprofilerstellungs-Task.</span><span class="sxs-lookup"><span data-stu-id="064ed-243">Connect the Script task to the Data Profiling task.</span></span> <span data-ttu-id="064ed-244">Schreiben Sie Code in den Skripttask, der die gewünschten Werte aus der Ausgabedatei des Datenprofilerstellungs-Tasks liest und die Paketvariablen auffüllt.</span><span class="sxs-lookup"><span data-stu-id="064ed-244">In the Script task, write code that reads the desired values from the output of the Data Profiling task and populates the package variables.</span></span>  
  
7.  <span data-ttu-id="064ed-245">Verwenden Sie in den Rangfolgeneinschränkungen, mit denen der Skripttask mit Downstream-Verzweigungen verbunden wird, Ausdrücke, die den Workflow anhand der Werte der Variablen steuern.</span><span class="sxs-lookup"><span data-stu-id="064ed-245">In the precedence constraints that connect the Script task to downstream branches in the workflow, write expressions that use the values of the variables to direct the workflow.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="064ed-246">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="064ed-246">See Also</span></span>  
 <span data-ttu-id="064ed-247">[Einrichten von Datenprofilerstellungs-Tasks](data-profiling-task.md) </span><span class="sxs-lookup"><span data-stu-id="064ed-247">[Setup of the Data Profiling Task](data-profiling-task.md) </span></span>  
 [<span data-ttu-id="064ed-248">Datenprofil-Viewer</span><span class="sxs-lookup"><span data-stu-id="064ed-248">Data Profile Viewer</span></span>](data-profile-viewer.md)  
  
  
