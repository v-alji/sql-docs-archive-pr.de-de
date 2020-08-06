---
title: Anwenden der Änderungen auf das Ziel | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- incremental load [Integration Services],applying changes
ms.assetid: 338a56db-cb14-4784-a692-468eabd30f41
author: chugugrace
ms.author: chugu
ms.openlocfilehash: dd7ab93a299ffaab2259c3d462a5c0a69160ad5b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622795"
---
# <a name="apply-the-changes-to-the-destination"></a><span data-ttu-id="d304b-102">Anwenden der Änderungen auf das Ziel</span><span class="sxs-lookup"><span data-stu-id="d304b-102">Apply the Changes to the Destination</span></span>
  <span data-ttu-id="d304b-103">Im Datenfluss eines [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Pakets, das ein inkrementelles Laden von Änderungsdaten ausführt, ist der dritte und letzte Task die Anwendung der Änderungen auf Ihr Ziel.</span><span class="sxs-lookup"><span data-stu-id="d304b-103">In the data flow of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that performs an incremental load of change data, the third and final task is to apply the changes to your destination.</span></span> <span data-ttu-id="d304b-104">Sie benötigen jeweils eine Komponente, um Einfügungen, Updates und Löschungen anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="d304b-104">You will need one component to apply inserts, one to apply updates, and one to apply deletes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d304b-105">Der zweite Task beim Entwerfen des Datenflusses eines Pakets, das ein inkrementelles Laden von Änderungsdaten ausführt, ist die Trennung von Einfügungen, Updates und Löschungen.</span><span class="sxs-lookup"><span data-stu-id="d304b-105">The second task in designing the data flow of a package that performs an incremental load of change data is to separate inserts, updates, and deletes.</span></span> <span data-ttu-id="d304b-106">Weitere Informationen zu dieser Komponente finden Sie unter [Verarbeiten von Einfügungen, Updates und Löschungen](process-inserts-updates-and-deletes.md).</span><span class="sxs-lookup"><span data-stu-id="d304b-106">For more information about this component, see [Process Inserts, Updates, and Deletes](process-inserts-updates-and-deletes.md).</span></span> <span data-ttu-id="d304b-107">Eine Beschreibung des Gesamtprozesses zur Erstellung eines Pakets, das ein inkrementelles Laden von Änderungsdaten ausführt, finden Sie unter [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="d304b-107">For a description of the overall process for creating a package that performs an incremental load of change data, see [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span></span>  
  
## <a name="applying-inserts"></a><span data-ttu-id="d304b-108">Anwenden von Einfügungen</span><span class="sxs-lookup"><span data-stu-id="d304b-108">Applying Inserts</span></span>  
 <span data-ttu-id="d304b-109">Zum Anwenden von Einfügungen verwenden Sie ein OLE DB-Ziel, da die neuen Zeilen keine besondere Behandlung erfordern.</span><span class="sxs-lookup"><span data-stu-id="d304b-109">To apply inserts, you use an OLE DB destination because the new rows do not require any special handling.</span></span>  
  
#### <a name="to-process-inserts-by-using-an-ole-db-destination"></a><span data-ttu-id="d304b-110">So verarbeiten Sie Einfügungen mit einem OLE DB-Ziel</span><span class="sxs-lookup"><span data-stu-id="d304b-110">To process inserts by using an OLE DB Destination</span></span>  
  
1.  <span data-ttu-id="d304b-111">Fügen Sie auf der Registerkarte **Datenfluss** ein OLE DB-Ziel hinzu.</span><span class="sxs-lookup"><span data-stu-id="d304b-111">On the **Data flow** tab, add an OLE DB destination.</span></span>  
  
2.  <span data-ttu-id="d304b-112">Verbinden Sie die Ausgabe, die Einfügungen aus der Transformation für bedingtes Teilen enthält, mit dem OLE DB-Ziel.</span><span class="sxs-lookup"><span data-stu-id="d304b-112">Connect the output that contains inserts from the Conditional Split transformation to the OLE DB destination.</span></span>  
  
3.  <span data-ttu-id="d304b-113">Aktivieren Sie im **Ziel-Editor für OLE DB**auf der Seite **Verbindungs-Manager** die folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="d304b-113">In the **OLE DB Destination Editor**, on the **Connection Manager** page, select the following options:</span></span>  
  
    1.  <span data-ttu-id="d304b-114">Wählen Sie einen OLE DB-Verbindungs-Manager für die Zieldatenbank aus oder erstellen Sie einen.</span><span class="sxs-lookup"><span data-stu-id="d304b-114">Select or create an OLE DB Connection Manager for the destination database.</span></span>  
  
    2.  <span data-ttu-id="d304b-115">Wählen Sie eine Option für den **Datenzugriffsmodus** aus, und wählen Sie dann die Zieltabelle aus, oder geben Sie eine SQL-Anweisung mit den Zielspalten ein.</span><span class="sxs-lookup"><span data-stu-id="d304b-115">Select a **Data access mode** option, and then select the destination table or enter a SQL statement that contains the destination columns.</span></span>  
  
4.  <span data-ttu-id="d304b-116">Ordnen Sie auf der Seite **Zuordnungen** des Editors die entsprechenden Spalten von den Änderungsdaten der Zieltabelle zu.</span><span class="sxs-lookup"><span data-stu-id="d304b-116">On the **Mappings** page of the editor, map the appropriate columns from the change data to the destination table.</span></span>  
  
## <a name="applying-updates"></a><span data-ttu-id="d304b-117">Anwenden von Updates</span><span class="sxs-lookup"><span data-stu-id="d304b-117">Applying Updates</span></span>  
 <span data-ttu-id="d304b-118">Zum Anwenden von Updates verwenden Sie eine Transformation für OLE DB-Befehl.</span><span class="sxs-lookup"><span data-stu-id="d304b-118">To apply updates, you use an OLE DB Command transformation.</span></span> <span data-ttu-id="d304b-119">Sie verwenden diese Transformation, da Sie eine parametrisierte UPDATE-Anweisung verwenden müssen, um jeweils eine Zeile mit den neuen Spaltenwerten zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="d304b-119">You use this transformation because you have to use a parameterized UPDATE statement to update one row at a time with the new column values.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d304b-120">Sie können auch Zielkomponenten verwenden, um Updates anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="d304b-120">You can also use destination components to apply updates.</span></span> <span data-ttu-id="d304b-121">Bei dieser Vorgehensweise verwenden Sie die Zielkomponenten, um die Zeilen in temporäre Tabellen zu speichern, die Sie für diesen Zweck erstellen.</span><span class="sxs-lookup"><span data-stu-id="d304b-121">When using this approach, you use the destination components to save the rows to temporary tables that you create for this purpose.</span></span> <span data-ttu-id="d304b-122">Sie verwenden dann Tasks "SQL Ausführen", um Massenupdates und Massenlöschungen auf dem Ziel von den temporären Tabellen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d304b-122">Then, you use Execute SQL tasks to perform bulk update and bulk delete operations against the destination from the temporary tables.</span></span>  
  
#### <a name="to-process-updates-by-using-an-ole-db-command-transformation"></a><span data-ttu-id="d304b-123">So verarbeiten Sie Updates mit einer Transformation für OLE DB-Befehl</span><span class="sxs-lookup"><span data-stu-id="d304b-123">To process updates by using an OLE DB Command transformation</span></span>  
  
1.  <span data-ttu-id="d304b-124">Fügen Sie auf der Registerkarte **Datenfluss** eine Transformation für OLE DB-Befehl hinzu.</span><span class="sxs-lookup"><span data-stu-id="d304b-124">On the **Data flow** tab, add an OLE DB Command transformation.</span></span>  
  
2.  <span data-ttu-id="d304b-125">Verbinden Sie die Ausgabe, die Updates aus der Transformation für bedingtes Teilen enthält, mit der Transformation für OLE DB-Befehl.</span><span class="sxs-lookup"><span data-stu-id="d304b-125">Connect the output that contains updates from the Conditional Split transformation to the OLE DB Command transformation.</span></span>  
  
3.  <span data-ttu-id="d304b-126">Wählen Sie auf der Registerkarte **Verbindungs-Manager**im **Erweiterten Editor für OLE DB-Befehl** für die Zieldatenbank einen OLE DB-Verbindungs-Manager aus, oder erstellen Sie einen.</span><span class="sxs-lookup"><span data-stu-id="d304b-126">In the **Advanced Editor for OLE DB Command**, on the **Connection Manager** tab, select or create an OLE DB Connection Manager for the destination database.</span></span>  
  
4.  <span data-ttu-id="d304b-127">Geben Sie auf der Registerkarte **Komponenteneigenschaften**im **Erweiterten Editor für OLE DB-Befehl** für **SqlCommand**eine parametrisierte UPDATE-Anweisung ein.</span><span class="sxs-lookup"><span data-stu-id="d304b-127">In the **Advanced Editor for OLE DB Command**, on the **Component Properties** tab, for **SqlCommand**, enter a parameterized UPDATE statement.</span></span>  
  
     <span data-ttu-id="d304b-128">Zum Beispiel könnte eine UPDATE-Anweisung für eine Customer-Tabelle die folgende Syntax aufweisen:</span><span class="sxs-lookup"><span data-stu-id="d304b-128">For example, an UPDATE statement for a Customer table might have the following syntax:</span></span>  
  
    ```  
    update CDCSample.Customer  
    set TerritoryID  = ?,  
        CustomerType  = ?,  
        rowguid  = ?,  
        ModifiedDate  = ?  
    where CustomerID = ?  
  
    ```  
  
5.  <span data-ttu-id="d304b-129">Ordnen Sie auf der Registerkarte **Spaltenzuordnungen** des Editors den Parametern in der UPDATE-Anweisung die entsprechenden Spalten von den Änderungsdaten zu.</span><span class="sxs-lookup"><span data-stu-id="d304b-129">On the **Column Mappings** tab of the editor, map the appropriate columns from the change data to the parameters in the UPDATE statement.</span></span>  
  
## <a name="applying-deletes"></a><span data-ttu-id="d304b-130">Anwenden von Löschungen</span><span class="sxs-lookup"><span data-stu-id="d304b-130">Applying Deletes</span></span>  
 <span data-ttu-id="d304b-131">Zum Anwenden von Löschungen verwenden Sie eine Transformation für OLE DB-Befehl.</span><span class="sxs-lookup"><span data-stu-id="d304b-131">To apply deletes, you use an OLE DB Command transformation.</span></span> <span data-ttu-id="d304b-132">Sie verwenden diese Transformation, da Sie eine parametrisierte DELETE-Anweisung verwenden müssen, die jeweils eine einzelne Zeile löscht, die auf dem Spaltenwert basiert, der die Zeile eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="d304b-132">You use this transformation because you have to use a parameterized DELETE statement that deletes a single row at a time based on the column value that uniquely identifies the row.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d304b-133">Sie können auch Zielkomponenten verwenden, um Löschungen anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="d304b-133">You can also use destination components to apply deletes.</span></span> <span data-ttu-id="d304b-134">Bei dieser Vorgehensweise verwenden Sie die Zielkomponenten, um die Zeilen in temporäre Tabellen zu speichern, die Sie für diesen Zweck erstellen.</span><span class="sxs-lookup"><span data-stu-id="d304b-134">When using this approach, you use the destination components to save the rows to temporary tables that you create for this purpose.</span></span> <span data-ttu-id="d304b-135">Sie verwenden dann Tasks "SQL Ausführen", um Massenupdates und Massenlöschungen auf dem Ziel von den temporären Tabellen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d304b-135">Then, you use Execute SQL tasks to perform bulk update and bulk delete operations against the destination from the temporary tables.</span></span>  
  
#### <a name="to-process-deletes-by-using-an-ole-db-command-transformation"></a><span data-ttu-id="d304b-136">So verarbeiten Sie Löschungen mit einer Transformation für OLE DB-Befehl</span><span class="sxs-lookup"><span data-stu-id="d304b-136">To process deletes by using an OLE DB Command transformation</span></span>  
  
1.  <span data-ttu-id="d304b-137">Fügen Sie auf der Registerkarte **Datenfluss** eine Transformation für OLE DB-Befehl dem Datenfluss hinzu.</span><span class="sxs-lookup"><span data-stu-id="d304b-137">On the **Data flow** tab, add an OLE DB Command transformation to the data flow.</span></span>  
  
2.  <span data-ttu-id="d304b-138">Verbinden Sie die Ausgabe, die Löschungen aus der Transformation für bedingtes Teilen enthält, mit der Transformation für OLE DB-Befehl.</span><span class="sxs-lookup"><span data-stu-id="d304b-138">Connect the output that contains deletes from the Conditional Split transformation to the OLE DB Command transformation.</span></span>  
  
3.  <span data-ttu-id="d304b-139">Öffnen Sie den erweiterten Editor, um die Transformation zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="d304b-139">Open the Advanced Editor to configure the transformation.</span></span>  
  
4.  <span data-ttu-id="d304b-140">Wählen Sie auf der Registerkarte **Verbindungs-Manager**im **Erweiterten Editor für OLE DB-Befehl** für die Zieldatenbank einen OLE DB-Verbindungs-Manager aus, oder erstellen Sie einen.</span><span class="sxs-lookup"><span data-stu-id="d304b-140">In the **Advanced Editor for OLE DB Command**, on the **Connection Manager** tab, select or create an OLE DB Connection Manager for the destination database.</span></span>  
  
5.  <span data-ttu-id="d304b-141">Geben Sie im **Erweiterten Editor für OLE DB-Befehl**auf der Registerkarte **Komponenteneigenschaften** des Editors für **SqlCommand**eine parametrisierte DELETE-Anweisung ein.</span><span class="sxs-lookup"><span data-stu-id="d304b-141">In the **Advanced Editor for OLE DB Command**, on the **Component Properties** tab of the editor, for **SqlCommand**, enter a parameterized DELETE statement.</span></span>  
  
     <span data-ttu-id="d304b-142">Zum Beispiel könnte eine DELETE-Anweisung für eine Customer-Tabelle die folgende Syntax aufweisen:</span><span class="sxs-lookup"><span data-stu-id="d304b-142">For example, a DELETE statement for a Customer table might have the following syntax:</span></span>  
  
    ```  
    delete from Customer where CustomerID = ?  
  
    ```  
  
6.  <span data-ttu-id="d304b-143">Ordnen Sie auf der Registerkarte **Spaltenzuordnungen** des Editors die entsprechende Spalte von den Änderungsdaten dem Parameter in der DELETE-Anweisung zu.</span><span class="sxs-lookup"><span data-stu-id="d304b-143">On the **Column Mappings** tab of the editor, map the appropriate column from the change data to the parameter in the DELETE statement.</span></span>  
  
## <a name="optimizing-inserts-and-updates-by-using-merge-functionality"></a><span data-ttu-id="d304b-144">Optimieren von Einfügungen und Updates mithilfe der MERGE-Funktionalität</span><span class="sxs-lookup"><span data-stu-id="d304b-144">Optimizing Inserts and Updates by Using MERGE Functionality</span></span>  
 <span data-ttu-id="d304b-145">Sie können die Verarbeitung von Einfügungen und Updates optimieren, indem Sie bestimmte Change Data Capture-Optionen mit der Verwendung des Transact-SQL-MERGE-Schlüsselworts kombinieren.</span><span class="sxs-lookup"><span data-stu-id="d304b-145">You can optimize the processing of inserts and updates by combining certain change data capture options with the use of the Transact-SQL MERGE keyword.</span></span> <span data-ttu-id="d304b-146">Weitere Informationen zum MERGE-Schlüsselwort finden Sie unter [MERGE &#40;Transact-SQL&#41;](/sql/t-sql/statements/merge-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d304b-146">For more information about the MERGE keyword, see [MERGE &#40;Transact-SQL&#41;](/sql/t-sql/statements/merge-transact-sql).</span></span>  
  
 <span data-ttu-id="d304b-147">In der Transact-SQL-Anweisung, mit der die Änderungsdaten abgerufen werden, können Sie *all with merge* als den Wert des *row_filter_option*-Parameters festlegen, wenn Sie die **cdc.fn_cdc_get_net_changes_<capture_instance>** -Funktion aufrufen.</span><span class="sxs-lookup"><span data-stu-id="d304b-147">In the Transact-SQL statement that retrieves the change data, you can specify *all with merge* as the value of the *row_filter_option* parameter when you call the **cdc.fn_cdc_get_net_changes_<capture_instance>** function.</span></span> <span data-ttu-id="d304b-148">Diese Change Data Capture-Funktion arbeitet effizienter, wenn sie nicht die zusätzliche Verarbeitung ausführen muss, die erforderlich ist, um Einfügungen von Updates zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="d304b-148">This change data capture function operates more efficiently when it does not have to perform the extra processing that is required to distinguish inserts from updates.</span></span> <span data-ttu-id="d304b-149">Wenn Sie den *all with merge* -Parameterwert angeben, ist der **__$operation** -Wert der Änderungsdaten 1 für Löschungen oder 5 für Änderungen, die durch Einfügungen oder Updates verursacht wurden.</span><span class="sxs-lookup"><span data-stu-id="d304b-149">When you specify the *all with merge* parameter value, the **__$operation** value of the change data is 1 for deletes or 5 for changes that were caused by inserts or updates.</span></span> <span data-ttu-id="d304b-150">Weitere Informationen zur Transact-SQL-Funktion, die zum Abrufen der Änderungsdaten verwendet wird, finden Sie unter [Abrufen und Verstehen der Änderungsdaten](retrieve-and-understand-the-change-data.md). Nachdem Sie Änderungen mit dem *all with merge* -Parameterwert abgerufen haben, können Sie Löschungen anwenden und die übrigen Zeilen in eine temporäre Tabelle oder eine Stagingtabelle ausgeben.</span><span class="sxs-lookup"><span data-stu-id="d304b-150">For more information about the Transact-SQL function that is used to retrieve the change data, see [Retrieve and Understand the Change Data](retrieve-and-understand-the-change-data.md).After retrieving changes with the *all with merge* parameter value, you can apply deletes, and output the remaining rows to a temporary table or a staging table.</span></span> <span data-ttu-id="d304b-151">Sie können dann in einem Downstream-Task 'SQL Ausführen' eine einzelne MERGE-Anweisung verwenden, um alle Einfügungen oder Updates aus der Stagingtabelle auf das Ziel anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="d304b-151">Then, in a downstream Execute SQL Task, you can use a single MERGE statement to apply all the inserts or updates from the staging table to the destination.</span></span>  
  
  
