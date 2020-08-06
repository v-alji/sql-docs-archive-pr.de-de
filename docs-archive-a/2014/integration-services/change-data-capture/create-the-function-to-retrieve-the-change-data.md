---
title: Erstellen der Funktion zum Abrufen der Änderungsdaten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- incremental load [Integration Services],creating function
ms.assetid: 55dd0946-bd67-4490-9971-12dfb5b9de94
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cc1d5af0a64225aca4ff54570ad6504d25d62812
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724050"
---
# <a name="create-the-function-to-retrieve-the-change-data"></a><span data-ttu-id="160a9-102">Erstellen der Funktion zum Abrufen der Änderungsdaten</span><span class="sxs-lookup"><span data-stu-id="160a9-102">Create the Function to Retrieve the Change Data</span></span>
  <span data-ttu-id="160a9-103">Nach Abschluss der Ablaufsteuerung für ein [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Paket, das ein inkrementelles Laden von Änderungsdaten ausführt, ist der nächste Task die Erstellung einer Tabellenwertfunktion, mit der die Änderungsdaten abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="160a9-103">After completing the control flow for an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that performs an incremental load of change data, the next task is to create a table-valued function that retrieves the change data.</span></span> <span data-ttu-id="160a9-104">Sie müssen diese Funktion nur einmal vor dem ersten inkrementellen Laden erstellen.</span><span class="sxs-lookup"><span data-stu-id="160a9-104">You only have to create this function one time before the first incremental load.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="160a9-105">Das Erstellen einer Funktion zum Abrufen der Änderungsdaten ist der zweite Schritt beim Erstellen eines Pakets, das ein inkrementelles Laden von Änderungsdaten ausführt.</span><span class="sxs-lookup"><span data-stu-id="160a9-105">The creation of a function to retrieve the change data is the second step in the process of creating a package that performs an incremental load of change data.</span></span> <span data-ttu-id="160a9-106">Eine Beschreibung des Gesamtprozesses zum Entwurf dieses Pakets finden Sie unter [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="160a9-106">For a description of the overall process for creating this package, see [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span></span>  
  
## <a name="design-considerations-for-change-data-capture-functions"></a><span data-ttu-id="160a9-107">Entwurfsaspekte für Change Data Capture-Funktionen</span><span class="sxs-lookup"><span data-stu-id="160a9-107">Design Considerations for Change Data Capture Functions</span></span>  
 <span data-ttu-id="160a9-108">Zum Abrufen von Änderungsdaten ruft eine Quellkomponente im Datenfluss des Pakets eine der folgenden Change Data Capture-Abfragefunktionen auf:</span><span class="sxs-lookup"><span data-stu-id="160a9-108">To retrieve change data, a source component in the data flow of the package calls one of the following change data capture query functions:</span></span>  
  
-   <span data-ttu-id="160a9-109">**cdc.fn_cdc_get_net_changes_<Aufzeichnungsinstanz>** Bei dieser Abfrage enthält die für jedes Update zurückgegebene einzelne Zeile den finalen Status jeder geänderten Zeile.</span><span class="sxs-lookup"><span data-stu-id="160a9-109">**cdc.fn_cdc_get_net_changes_<capture_instance>** For this query, the single row returned for each update contains the final state of each changed row.</span></span> <span data-ttu-id="160a9-110">In den meisten Fällen benötigen Sie nur die von einer Abfrage von Nettoänderungen zurückgegebenen Daten.</span><span class="sxs-lookup"><span data-stu-id="160a9-110">In most cases, you only need the data returned by a query for net changes.</span></span> <span data-ttu-id="160a9-111">Weitere Informationen finden Sie unter [cdc.fn_cdc_get_net_changes_&#60;capture_instance&#62; &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-net-changes-capture-instance-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="160a9-111">For more information, see [cdc.fn_cdc_get_net_changes_&#60;capture_instance&#62; &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-net-changes-capture-instance-transact-sql).</span></span>  
  
-   <span data-ttu-id="160a9-112">**cdc.fn_cdc_get_all_changes_<Aufzeichnungsinstanz>** Diese Abfrage gibt alle Änderungen zurück, die während des Aufzeichnungsintervalls in jeder Zeile aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="160a9-112">**cdc.fn_cdc_get_all_changes_<capture_instance>** This query returns all the changes that have occurred in each row during the capture interval.</span></span> <span data-ttu-id="160a9-113">Weitere Informationen finden Sie unter [cdc.fn_cdc_get_all_changes_&#60;capture_instance&#62;  &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-all-changes-capture-instance-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="160a9-113">For more information, see [cdc.fn_cdc_get_all_changes_&#60;capture_instance&#62;  &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-all-changes-capture-instance-transact-sql).</span></span>  
  
 <span data-ttu-id="160a9-114">Die Quellkomponente nimmt dann die von der Funktion zurückgegebenen Ergebnisse und übergibt sie an Downstream-Transformationen und -Ziele, die die Änderungsdaten auf das endgültige Ziel anwenden.</span><span class="sxs-lookup"><span data-stu-id="160a9-114">The source component then takes the results returned by the function and passes them to downstream transformations and destinations, which apply the change data to the final destination.</span></span>  
  
 <span data-ttu-id="160a9-115">Eine [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Quellkomponente kann diese Change Data Capture-Funktionen jedoch nicht direkt aufrufen.</span><span class="sxs-lookup"><span data-stu-id="160a9-115">However, an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] source component cannot call these change data capture functions directly.</span></span> <span data-ttu-id="160a9-116">Eine [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Quellkomponente erfordert Metadaten zu den Spalten, die die Abfrage zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="160a9-116">An [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] source component requires metadata about the columns that the query returns.</span></span> <span data-ttu-id="160a9-117">Die Change Data Capture-Funktionen definieren nicht die Spalten ihrer Ausgabetabelle.</span><span class="sxs-lookup"><span data-stu-id="160a9-117">The change data capture functions do not define the columns of their output table.</span></span> <span data-ttu-id="160a9-118">Somit geben diese Funktionen nicht genügend Metadaten für eine [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Quellkomponente zurück.</span><span class="sxs-lookup"><span data-stu-id="160a9-118">Thus, these functions do not return sufficient metadata for an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] source component.</span></span>  
  
 <span data-ttu-id="160a9-119">Verwenden Sie stattdessen eine Tabellenwert-Wrapperfunktion, da diese Art von Funktion die Spalten ihrer Ausgabetabelle explizit in ihrer RETURNS-Klausel definiert.</span><span class="sxs-lookup"><span data-stu-id="160a9-119">Instead, you use a table-valued wrapper function because this kind of function explicitly defines the columns of its output table in its RETURNS clause.</span></span> <span data-ttu-id="160a9-120">Diese explizite Definition von Spalten stellt die Metadaten bereit, die eine [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Quellkomponente benötigt.</span><span class="sxs-lookup"><span data-stu-id="160a9-120">This explicit definition of columns provides the metadata that an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] source component needs.</span></span> <span data-ttu-id="160a9-121">Sie müssen diese Funktion für jede Tabelle erstellen, für die Sie Änderungsdaten abrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="160a9-121">You have to create this function for each table for which you want to retrieve change data.</span></span>  
  
 <span data-ttu-id="160a9-122">Sie haben zwei Möglichkeiten, die Tabellenwert-Wrapperfunktion zu erstellen, die die Data Capture-Abfragefunktion aufruft:</span><span class="sxs-lookup"><span data-stu-id="160a9-122">You have two options for creating the table-valued wrapper function that calls the change data capture query function:</span></span>  
  
-   <span data-ttu-id="160a9-123">Sie können die gespeicherte Systemprozedur **sys.sp_cdc_generate_wrapper_function** aufrufen, damit diese die Tabellenwertfunktionen für Sie erstellt.</span><span class="sxs-lookup"><span data-stu-id="160a9-123">You can call the **sys.sp_cdc_generate_wrapper_function** system stored procedure to create the table-valued functions for you.</span></span>  
  
-   <span data-ttu-id="160a9-124">Sie können mithilfe der Hinweise und Beispiele in diesem Thema Ihre eigene Tabellenwertfunktion schreiben.</span><span class="sxs-lookup"><span data-stu-id="160a9-124">You can write your own table-valued function by using the guidelines and the example in this topic.</span></span>  
  
## <a name="calling-a-stored-procedure-to-create-the-table-valued-function"></a><span data-ttu-id="160a9-125">Aufrufen der gespeicherten Prozedur zur Erstellung der Tabellenwertfunktion</span><span class="sxs-lookup"><span data-stu-id="160a9-125">Calling a Stored Procedure to Create the Table-valued Function</span></span>  
 <span data-ttu-id="160a9-126">Die schnellste und einfachste Möglichkeit zur Erstellung der benötigten Tabellenwertfunktionen ist der Aufruf der gespeicherten Systemprozedur **sys.sp_cdc_generate_wrapper_function** .</span><span class="sxs-lookup"><span data-stu-id="160a9-126">The quickest and easiest way to create the table-valued functions that you need is to call the **sys.sp_cdc_generate_wrapper_function** system stored procedure.</span></span> <span data-ttu-id="160a9-127">Diese gespeicherte Prozedur erzeugt Skripts zur Erstellung der Wrapperfunktionen, die speziell für die Anforderungen der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Quellkomponente entwickelt wurden.</span><span class="sxs-lookup"><span data-stu-id="160a9-127">This stored procedure generates scripts to create wrapper functions that are designed specifically to meet the needs of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] source component.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="160a9-128">Die gespeicherte Systemprozedur **sys.sp_cdc_generate_wrapper_function** erstellt nicht direkt die Wrapperfunktionen.</span><span class="sxs-lookup"><span data-stu-id="160a9-128">The **sys.sp_cdc_generate_wrapper_function** system stored procedure does not directly create the wrapper functions.</span></span> <span data-ttu-id="160a9-129">Die gespeicherte Prozedur generiert stattdessen die CREATE-Skripts für die Wrapperfunktionen.</span><span class="sxs-lookup"><span data-stu-id="160a9-129">Instead, the stored procedure generates the CREATE scripts for the wrapper functions.</span></span> <span data-ttu-id="160a9-130">Der Entwickler muss die von der gespeicherten Prozedur erzeugten CREATE-Skripts ausführen, bevor ein Paket für inkrementelles Laden die Wrapperfunktionen aufrufen kann.</span><span class="sxs-lookup"><span data-stu-id="160a9-130">The developer must run the CREATE scripts that the stored procedure generates before an incremental load package can call the wrapper functions.</span></span>  
  
 <span data-ttu-id="160a9-131">Um zu verstehen, wie diese gespeicherte Systemprozedur verwendet wird, müssen Sie verstehen, wie diese Prozedur funktioniert, welche Skripts die Prozedur generiert und welche Wrapperfunktionen diese Skripts erstellen.</span><span class="sxs-lookup"><span data-stu-id="160a9-131">To understand how to use this system stored procedure, you should understand what the procedure does, what scripts the procedure generates, and what wrapper functions the scripts create.</span></span>  
  
### <a name="understanding-and-using-the-stored-procedure"></a><span data-ttu-id="160a9-132">Grundlegendes zu gespeicherten Prozeduren und deren Verwendung</span><span class="sxs-lookup"><span data-stu-id="160a9-132">Understanding and Using the Stored Procedure</span></span>  
 <span data-ttu-id="160a9-133">Die gespeicherte Systemprozedur **sys.sp_cdc_generate_wrapper_function** generiert Skripts zur Erstellung von Wrapperfunktionen, die von [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Paketen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="160a9-133">The **sys.sp_cdc_generate_wrapper_function** system stored procedure generates scripts to create wrapper functions for use by [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.</span></span>  
  
 <span data-ttu-id="160a9-134">Der folgende Code stellt die ersten Zeilen der Definition der gespeicherten Prozedur dar:</span><span class="sxs-lookup"><span data-stu-id="160a9-134">Here are the first few lines of the definition of the stored procedure:</span></span>  
  
 `CREATE PROCEDURE sys.sp_cdc_generate_wrapper_function`  
  
 `(`  
  
 `@capture_instance sysname = null`  
  
 `@closed_high_end_point bit = 1,`  
  
 `@column_list = null,`  
  
 `@update_flag_list = null`  
  
 `)`  
  
 <span data-ttu-id="160a9-135">Alle Parameter für die gespeicherte Prozedur sind optional.</span><span class="sxs-lookup"><span data-stu-id="160a9-135">All the parameters for the stored procedure are optional.</span></span> <span data-ttu-id="160a9-136">Wenn Sie die gespeicherte Prozedur ohne die Bereitstellung von Werten für einen der Parameter aufrufen, erstellt die gespeicherte Prozedur Wrapperfunktionen für alle Aufzeichnungsinstanzen, auf die Sie Zugriff haben.</span><span class="sxs-lookup"><span data-stu-id="160a9-136">If you call the stored procedure without supplying values for any of the parameters, the stored procedure creates wrapper functions for all the capture instances to which you have access.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="160a9-137">Weitere Informationen über die Syntax dieser gespeicherten Prozedur und ihre Parameter finden Sie unter [sys.sp_cdc_generate_wrapper_function &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-cdc-generate-wrapper-function-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="160a9-137">For more information about the syntax of this stored procedure and its parameters, see [sys.sp_cdc_generate_wrapper_function &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-cdc-generate-wrapper-function-transact-sql).</span></span>  
  
 <span data-ttu-id="160a9-138">Die gespeicherte Funktion generiert immer eine Wrapperfunktion, um alle Änderungen aus allen Aufzeichnungsinstanzen zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="160a9-138">The stored procedure always generates a wrapper function to return all changes from each capture instance.</span></span> <span data-ttu-id="160a9-139">Wenn der- *@supports_net_changes* Parameter beim Erstellen der Aufzeichnungs Instanz festgelegt wurde, generiert die gespeicherte Prozedur außerdem eine Wrapper Funktion, um die Netto Änderungen von jeder anwendbaren Aufzeichnungs Instanz zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="160a9-139">If the *@supports_net_changes* parameter was set when the capture instance was created, the stored procedure also generates a wrapper function to return net changes from each applicable capture instance.</span></span>  
  
 <span data-ttu-id="160a9-140">Die gespeicherte Prozedur gibt ein Resultset mit zwei Spalten zurück:</span><span class="sxs-lookup"><span data-stu-id="160a9-140">The stored procedure returns a result set with two columns:</span></span>  
  
-   <span data-ttu-id="160a9-141">Den Namen der Wrapperfunktion, die von der gespeicherten Prozedur generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="160a9-141">The name of the wrapper function that the stored procedure has generated.</span></span> <span data-ttu-id="160a9-142">Diese gespeicherte Prozedur ruft den Funktionsnamen vom Namen der Aufzeichnungsinstanz ab.</span><span class="sxs-lookup"><span data-stu-id="160a9-142">This stored procedure derives the function name from the name of the capture instance name.</span></span> <span data-ttu-id="160a9-143">(Der Funktionsname lautet „fn_all_changes_“, gefolgt vom Namen der Aufzeichnungsinstanz.</span><span class="sxs-lookup"><span data-stu-id="160a9-143">(The function name is 'fn_all_changes_' followed by the capture instance name.</span></span> <span data-ttu-id="160a9-144">Das Präfix, das für die Funktion für Nettoänderungen verwendet wird, lautet, wenn es erstellt wird, „fn_net_changes_“.)</span><span class="sxs-lookup"><span data-stu-id="160a9-144">The prefix used for the net changes function, if it is created, is 'fn_net_changes_'.)</span></span>  
  
-   <span data-ttu-id="160a9-145">Die CREATE-Anweisung für die Wrapperfunktion.</span><span class="sxs-lookup"><span data-stu-id="160a9-145">The CREATE statement for the wrapper function.</span></span>  
  
### <a name="understanding-and-using-the-scripts-created-by-the-stored-procedure"></a><span data-ttu-id="160a9-146">Grundlegendes zu den von der gespeicherten Prozedur erstellten Skripts und deren Verwendung</span><span class="sxs-lookup"><span data-stu-id="160a9-146">Understanding and Using the Scripts Created by the Stored Procedure</span></span>  
 <span data-ttu-id="160a9-147">Normalerweise verwendet ein Entwickler eine INSERT...EXEC-Anweisung, um die gespeicherte Prozedur **sys.sp_cdc_generate_wrapper_function** aufzurufen und die Skripts zu speichern, die die gespeicherte Prozedur in einer temporären Tabelle erstellt.</span><span class="sxs-lookup"><span data-stu-id="160a9-147">Typically, a developer would use an INSERT...EXEC statement to call the **sys.sp_cdc_generate_wrapper_function** stored procedure and save the scripts that the stored procedure creates to a temporary table.</span></span> <span data-ttu-id="160a9-148">Anschließend könnte jedes Skript einzeln ausgewählt und ausgeführt werden, um die entsprechende Wrapperfunktion zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="160a9-148">Each script could then be individually selected and run to create the corresponding wrapper function.</span></span> <span data-ttu-id="160a9-149">Ein Entwickler könnte jedoch auch einen Satz von SQL-Befehlen verwenden, um alle CREATE-Skripts auszuführen, wie im folgenden Beispielcode dargestellt:</span><span class="sxs-lookup"><span data-stu-id="160a9-149">However, a developer could also use one set of SQL commands to run all the CREATE scripts, as shown in the following sample code:</span></span>  
  
```  
create table #wrapper_functions  
      (function_name sysname, create_stmt nvarchar(max))  
insert into #wrapper_functions  
exec sys.sp_cdc_generate_wrapper_function  
  
declare @stmt nvarchar(max)  
declare #hfunctions cursor local fast_forward for   
      select create_stmt from #wrapper_functions  
open #hfunctions  
fetch #hfunctions into @stmt  
while (@@fetch_status <> -1)  
begin  
      exec sp_executesql @stmt  
      fetch #hfunctions into @stmt  
end  
close #hfunctions  
deallocate #hfunctions  
```  
  
### <a name="understanding-and-using-the-functions-created-by-the-stored-procedure"></a><span data-ttu-id="160a9-150">Grundlegendes zu den von der gespeicherten Prozedur erstellten Funktionen und deren Verwendung</span><span class="sxs-lookup"><span data-stu-id="160a9-150">Understanding and Using the Functions Created by the Stored Procedure</span></span>  
 <span data-ttu-id="160a9-151">Um die Zeitachse der aufgezeichneten Änderungs Daten systematisch zu durchlaufen, gehen die generierten Wrapper Funktionen davon aus, dass der *@end_time* Parameter für ein Intervall der-Parameter *@start_time* für das nachfolgende Intervall ist.</span><span class="sxs-lookup"><span data-stu-id="160a9-151">To systematically walk the timeline of captured change data, the generated wrapper functions expect that the *@end_time* parameter for one interval will be the *@start_time* parameter for the subsequent interval.</span></span> <span data-ttu-id="160a9-152">Wenn diese Konvention eingehalten wird, kann die generierte Wrapperfunktion folgende Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="160a9-152">When this convention is followed, the generated wrapper functions can do the following tasks:</span></span>  
  
-   <span data-ttu-id="160a9-153">Zuordnung der Datums-/Zeitwerte zu den intern verwendeten LSN-Werten</span><span class="sxs-lookup"><span data-stu-id="160a9-153">Map the date/time values to the LSN values that are used internally.</span></span>  
  
-   <span data-ttu-id="160a9-154">Sicherstellen, dass keine Daten verloren gehen oder wiederholt werden</span><span class="sxs-lookup"><span data-stu-id="160a9-154">Ensure that no data is lost or repeated.</span></span>  
  
 <span data-ttu-id="160a9-155">Zur Vereinfachung der Abfrage aller Zeilen einer Änderungstabelle unterstützt die generierte Wrapperfunktion auch folgende Konventionen:</span><span class="sxs-lookup"><span data-stu-id="160a9-155">To make querying for all rows of a change table simpler, the generated wrapper functions also support the following conventions:</span></span>  
  
-   <span data-ttu-id="160a9-156">Wenn der @start_time-Parameter NULL ist, verwendet die Wrapperfunktion den niedrigsten LSN-Wert in der Aufzeichnungsinstanz als untere Begrenzung der Abfrage.</span><span class="sxs-lookup"><span data-stu-id="160a9-156">If the @start_time parameter is null, the wrapper functions use the lowest LSN value in the capture instance as the lower bound of the query.</span></span>  
  
-   <span data-ttu-id="160a9-157">Wenn der @end_time-Parameter NULL ist, verwendet die Wrapperfunktion den höchsten LSN-Wert in der Aufzeichnungsinstanz als obere Begrenzung der Abfrage.</span><span class="sxs-lookup"><span data-stu-id="160a9-157">If the @end_time parameter is null, the wrapper functions use the highest LSN value in the capture instance as the upper bound of the query.</span></span>  
  
 <span data-ttu-id="160a9-158">Die meisten Benutzer sollten die von der gespeicherten Systemprozedur **sys.sp_cdc_generate_wrapper_function** erstellte Wrapperfunktion ohne Änderungen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="160a9-158">Most users should be able to use the wrapper functions that the **sys.sp_cdc_generate_wrapper_function** system stored procedure creates without modification.</span></span> <span data-ttu-id="160a9-159">Wenn Sie die Wrapperfunktion anpassen möchten, müssen Sie jedoch die CREATE-Skripts anpassen, bevor Sie diese ausführen.</span><span class="sxs-lookup"><span data-stu-id="160a9-159">However, to customize the wrapper functions, you have to customize the CREATE scripts before you run the scripts.</span></span>  
  
 <span data-ttu-id="160a9-160">Wenn Ihr Paket die Wrapperfunktion aufruft, muss das Paket Werte für drei Parameter bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="160a9-160">When your package calls the wrapper functions, the package must supply values for three parameters.</span></span> <span data-ttu-id="160a9-161">Diese drei Parameter entsprechen den drei Parametern, die von den Change Data Capture-Funktionen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="160a9-161">These three parameters are like the three parameters that the change data capture functions use.</span></span> <span data-ttu-id="160a9-162">Dabei handelt es sich um folgende drei Parameter:</span><span class="sxs-lookup"><span data-stu-id="160a9-162">These three parameters are as follows:</span></span>  
  
-   <span data-ttu-id="160a9-163">Die Werte für Startdatum und -uhrzeit sowie für Enddatum und -uhrzeit für das Intervall.</span><span class="sxs-lookup"><span data-stu-id="160a9-163">The starting date/time value and the ending date/time value for the interval.</span></span> <span data-ttu-id="160a9-164">Während die Wrapperfunktionen Datums-/Zeitwerte als Endpunkte für das Abfrageintervall verwenden, verwenden die Change Data Capture-Funktionen zwei LSN-Werte als Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="160a9-164">While the wrapper functions use date/time values as the end points for the query interval, the change data capture functions use two LSN values as the end points.</span></span>  
  
-   <span data-ttu-id="160a9-165">Den Zeilenfilter.</span><span class="sxs-lookup"><span data-stu-id="160a9-165">The row filter.</span></span> <span data-ttu-id="160a9-166">Für die Wrapper Funktionen und die Change Data Capture Funktionen ist der- *@row_filter_option* Parameter identisch.</span><span class="sxs-lookup"><span data-stu-id="160a9-166">For both the wrapper functions and the change data capture functions, the *@row_filter_option* parameter is the same.</span></span> <span data-ttu-id="160a9-167">Weitere Informationen finden Sie unter [cdc.fn_cdc_get_all_changes_&#60;Aufzeichnungsinstanz&#62;  &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-all-changes-capture-instance-transact-sql) und [cdc.fn_cdc_get_net_changes_&#60;Aufzeichnungsinstanz&#62; &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-net-changes-capture-instance-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="160a9-167">For more information, see [cdc.fn_cdc_get_all_changes_&#60;capture_instance&#62;  &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-all-changes-capture-instance-transact-sql) and [cdc.fn_cdc_get_net_changes_&#60;capture_instance&#62; &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-net-changes-capture-instance-transact-sql).</span></span>  
  
 <span data-ttu-id="160a9-168">Das von den Wrapperfunktionen zurückgegebene Resultset enthält folgende Daten:</span><span class="sxs-lookup"><span data-stu-id="160a9-168">The result set returned by the wrapper functions includesthe following data:</span></span>  
  
-   <span data-ttu-id="160a9-169">Alle angeforderten Spalten der Änderungsdaten</span><span class="sxs-lookup"><span data-stu-id="160a9-169">All of the requested columns of change data.</span></span>  
  
-   <span data-ttu-id="160a9-170">Eine Spalte mit dem Namen __CDC_OPERATION, die ein Feld mit einem oder zwei Zeichen verwendet, um den der Zeile zugeordneten Vorgang zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="160a9-170">A column named __CDC_OPERATION that uses a one- or two-character field to identify the operation that is associated with the row.</span></span> <span data-ttu-id="160a9-171">Folgende Werte sind für dieses Feld gültig: „I“ für „insert“ (einfügen), „D“ für delete (löschen), „UO“ für „update old values“ (alte Werte aktualisieren) und „UN“ für „update new values“ (neue Werte aktualisieren).</span><span class="sxs-lookup"><span data-stu-id="160a9-171">The valid values for this field are as follows: 'I' for insert, 'D' for delete, 'UO' for update old values, and 'UN' for update new values.</span></span>  
  
-   <span data-ttu-id="160a9-172">UpdateFlags, wenn Sie diese anfordern, die als Bitspalten nach dem Vorgangs Code und in der im-Parameter angegebenen Reihenfolge angezeigt werden *@update_flag_list* .</span><span class="sxs-lookup"><span data-stu-id="160a9-172">Update flags, when you request them, that appear as bit columns after the operation code and in the order that is specified in the *@update_flag_list* parameter.</span></span> <span data-ttu-id="160a9-173">Diese Spalten werden bezeichnet, indem „_uflag“ an den zugeordneten Spaltennamen angehängt wird.</span><span class="sxs-lookup"><span data-stu-id="160a9-173">These columns are named by appending '_uflag' to the associated column name.</span></span>  
  
 <span data-ttu-id="160a9-174">Wenn Ihr Paket eine Wrapperfunktion aufruft, die alle Änderungen abfragt, gibt die Wrapperfunktion außerdem die Spalten __CDC_STARTLSN und \__CDC_SEQVAL zurück.</span><span class="sxs-lookup"><span data-stu-id="160a9-174">If your package calls a wrapper function that queries for all changes, the wrapper function also returns the columns, __CDC_STARTLSN and \__CDC_SEQVAL.</span></span> <span data-ttu-id="160a9-175">Diese beiden Spalten sind die erste bzw. die zweite Spalte des Resultsets.</span><span class="sxs-lookup"><span data-stu-id="160a9-175">These two columns become the first and second columns, respectively, of the result set.</span></span> <span data-ttu-id="160a9-176">Die Wrapperfunktion sortiert das Resultset außerdem auf der Grundlage dieser beiden Spalten.</span><span class="sxs-lookup"><span data-stu-id="160a9-176">The wrapper function also sorts the result set based on these two columns.</span></span>  
  
## <a name="writing-your-own-table-value-function"></a><span data-ttu-id="160a9-177">Schreiben einer eigenen Tabellenwert-Funktion</span><span class="sxs-lookup"><span data-stu-id="160a9-177">Writing Your Own Table-Value Function</span></span>  
 <span data-ttu-id="160a9-178">Sie können [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] auch verwenden, um eine eigene Tabellenwert-Wrapperfunktion zu schreiben, die die Change Data Capture-Abfragefunktion aufruft, und die Tabellenwert-Wrapperfunktion in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]speichern.</span><span class="sxs-lookup"><span data-stu-id="160a9-178">You can also use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to write your own table-valued wrapper function that calls the change data capture query function, and store the table-valued wrapper function in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="160a9-179">Weitere Informationen zum Erstellen einer Transact-SQL-Funktion finden Sie unter [CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="160a9-179">For more information about how to create a Transact-SQL function, see [CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql).</span></span>  
  
 <span data-ttu-id="160a9-180">Das folgende Beispiel definiert eine Tabellenwertfunktion, mit der für das angegebene Änderungsintervall Änderungen von einer Customer-Tabelle abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="160a9-180">The following example defines a table-valued function that retrieves changes from a Customer table for the specified change interval.</span></span> <span data-ttu-id="160a9-181">Diese Funktion verwendet Change Data Capture-Funktionen, um die `datetime`-Werte den binären Protokollfolgenummer-Werten (Log Sequence Number, LSN) zuzuordnen, die die Änderungstabellen intern verwenden.</span><span class="sxs-lookup"><span data-stu-id="160a9-181">This function uses change data capture functions to map the `datetime` values to the binary log sequence number (LSN) values that the change tables use internally.</span></span> <span data-ttu-id="160a9-182">Diese Funktion behandelt auch mehrere besondere Bedingungen:</span><span class="sxs-lookup"><span data-stu-id="160a9-182">This function also handles several special conditions:</span></span>  
  
-   <span data-ttu-id="160a9-183">Wenn für die Startzeit ein NULL-Wert übergeben wird, verwendet diese Funktion den frühesten verfügbaren Wert.</span><span class="sxs-lookup"><span data-stu-id="160a9-183">When a null value is passed for the starting time, this function uses the earliest available value.</span></span>  
  
-   <span data-ttu-id="160a9-184">Wenn für die Beendigungszeit ein NULL-Wert übergeben wird, verwendet diese Funktion den letzten verfügbaren Wert.</span><span class="sxs-lookup"><span data-stu-id="160a9-184">When a null value is passed for the ending time, this function uses the latest available value.</span></span>  
  
-   <span data-ttu-id="160a9-185">Wenn die Start-LSN mit der Beendigungs-LSN übereinstimmt, was in der Regel darauf hinweist, dass für das ausgewählte Intervall keine Datensätze vorliegen, wird diese Funktion beendet.</span><span class="sxs-lookup"><span data-stu-id="160a9-185">When the starting LSN is equal to the ending LSN, which usually indicates that there are no records for the selected interval, this function exits.</span></span>  
  
### <a name="example-of-a-table-value-function-that-queries-for-change-data"></a><span data-ttu-id="160a9-186">Beispiel einer Tabellenwert-Funktion, mit der Änderungsdaten abgefragt werden</span><span class="sxs-lookup"><span data-stu-id="160a9-186">Example of a Table-Value Function that Queries for Change Data</span></span>  
  
```  
CREATE function CDCSample.uf_Customer (  
     @start_time datetime  
    ,@end_time datetime  
)  
returns @Customer table (  
     CustomerID int  
    ,TerritoryID int  
    ,CustomerType nchar(1)  
    ,rowguid uniqueidentifier  
    ,ModifiedDate datetime  
    ,CDC_OPERATION varchar(1)  
) as  
begin  
    declare @from_lsn binary(10), @to_lsn binary(10)  
  
    if (@start_time is null)  
        select @from_lsn = sys.fn_cdc_get_min_lsn('Customer')  
    else  
        select @from_lsn = sys.fn_cdc_increment_lsn(sys.fn_cdc_map_time_to_lsn('largest less than or equal',@start_time))  
  
    if (@end_time is null)  
        select @to_lsn = sys.fn_cdc_get_max_lsn()  
    else  
        select @to_lsn = sys.fn_cdc_map_time_to_lsn('largest less than or equal',@end_time)  
  
    if (@from_lsn = sys.fn_cdc_increment_lsn(@to_lsn))  
        return  
  
    -- Query for change data  
    insert into @Customer  
    select   
        CustomerID,      
        TerritoryID,   
        CustomerType,   
        rowguid,   
        ModifiedDate,   
        case __$operation  
                when 1 then 'D'  
                when 2 then 'I'  
                when 4 then 'U'  
                else null  
         end as CDC_OPERATION  
    from   
        cdc.fn_cdc_get_net_changes_Customer(@from_lsn, @to_lsn, 'all')  
  
    return  
end   
go  
  
```  
  
### <a name="retrieving-additional-metadata-with-the-change-data"></a><span data-ttu-id="160a9-187">Abrufen weiterer Metadaten mit den Änderungsdaten</span><span class="sxs-lookup"><span data-stu-id="160a9-187">Retrieving Additional Metadata with the Change Data</span></span>  
 <span data-ttu-id="160a9-188">Obwohl die zuvor gezeigte vom Benutzer erstellte Tabellenwert-Funktion nur die **__$operation**-Spalte verwendet, gibt die **cdc.fn_cdc_get_net_changes_<Aufzeichnungsinstanz>** -Funktion für jede Änderungszeile vier Metadatenspalten zurück.</span><span class="sxs-lookup"><span data-stu-id="160a9-188">Although the user-created table-valued function shown earlier uses only the **__$operation** column, the **cdc.fn_cdc_get_net_changes_<capture_instance>** function returns four columns of metadata for each change row.</span></span> <span data-ttu-id="160a9-189">Wenn Sie diese Werte in Ihrem Datenfluss verwenden möchten, können Sie diese als zusätzliche Spalten aus der Tabellenwert-Wrapperfunktion zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="160a9-189">If you want to use these values in your data flow, you can return them as additional columns from the table-valued wrapper function.</span></span>  
  
|<span data-ttu-id="160a9-190">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="160a9-190">Column name</span></span>|<span data-ttu-id="160a9-191">Datentyp</span><span class="sxs-lookup"><span data-stu-id="160a9-191">Data type</span></span>|<span data-ttu-id="160a9-192">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="160a9-192">Description</span></span>|  
|-----------------|---------------|-----------------|  
|<span data-ttu-id="160a9-193">**__$start_lsn**</span><span class="sxs-lookup"><span data-stu-id="160a9-193">**__$start_lsn**</span></span>|`binary(10)`|<span data-ttu-id="160a9-194">LSN, die dem Commit für die Änderung zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="160a9-194">LSN associated with the commit transaction for the change.</span></span><br /><br /> <span data-ttu-id="160a9-195">Alle Änderungen, für die ein Commit in derselben Transaktion ausgeführt wurde, verwenden dieselbe Commit-LSN.</span><span class="sxs-lookup"><span data-stu-id="160a9-195">All changes committed in the same transaction share the same commit LSN.</span></span> <span data-ttu-id="160a9-196">Wenn beispielsweise bei einem Updatevorgang in der Quelltabelle zwei unterschiedliche Zeilen geändert werden, enthält die Änderungstabelle vier Zeilen (zwei mit den alten Werten und zwei mit den neuen Werten), die jeweils denselben **__$start_lsn** -Wert aufweisen.</span><span class="sxs-lookup"><span data-stu-id="160a9-196">For example, if an update operation on the source table modifies two different rows, the change table will contain four rows (two with the old values and two with the new values), each with the same **__$start_lsn** value.</span></span>|  
|<span data-ttu-id="160a9-197">**__$seqval**</span><span class="sxs-lookup"><span data-stu-id="160a9-197">**__$seqval**</span></span>|`binary(10)`|<span data-ttu-id="160a9-198">Sequenzwert, mit dem Zeilenänderungen in einer Transaktion sortiert werden.</span><span class="sxs-lookup"><span data-stu-id="160a9-198">Sequence value that is used to order the row changes in a transaction.</span></span>|  
|<span data-ttu-id="160a9-199">**__$operation**</span><span class="sxs-lookup"><span data-stu-id="160a9-199">**__$operation**</span></span>|`int`|<span data-ttu-id="160a9-200">Der Vorgang der Datenbearbeitungssprache (Data Manipulation Language, DML), der der Änderung zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="160a9-200">The data manipulation language (DML) operation associated with the change.</span></span> <span data-ttu-id="160a9-201">Dabei kann es sich um eine der folgenden Methoden handeln:</span><span class="sxs-lookup"><span data-stu-id="160a9-201">Can be one of the following:</span></span><br /><br /> <span data-ttu-id="160a9-202">1 = Löschen</span><span class="sxs-lookup"><span data-stu-id="160a9-202">1 = delete</span></span><br /><br /> <span data-ttu-id="160a9-203">2 = Einfügen</span><span class="sxs-lookup"><span data-stu-id="160a9-203">2 = insert</span></span><br /><br /> <span data-ttu-id="160a9-204">3 = Update (Werte vor dem Updatevorgang)</span><span class="sxs-lookup"><span data-stu-id="160a9-204">3 = update (Values before the update operation.)</span></span><br /><br /> <span data-ttu-id="160a9-205">4 = Update (Werte nach dem Updatevorgang)</span><span class="sxs-lookup"><span data-stu-id="160a9-205">4 = update (Values after the update operation.)</span></span>|  
|<span data-ttu-id="160a9-206">**__$update_mask**</span><span class="sxs-lookup"><span data-stu-id="160a9-206">**__$update_mask**</span></span>|`varbinary(128)`|<span data-ttu-id="160a9-207">Eine Bitmaske, die auf den Spaltenordnungszahlen der Änderungstabelle basiert, die geänderte Spalten identifiziert.</span><span class="sxs-lookup"><span data-stu-id="160a9-207">A bitmask that is based on the column ordinals of the change table identifying those columns that changed.</span></span> <span data-ttu-id="160a9-208">Sie könnten diesen Wert überprüfen, wenn Sie bestimmen müssten, welche Spalten sich geändert haben.</span><span class="sxs-lookup"><span data-stu-id="160a9-208">You could examine this value if you had to determine which columns have changed.</span></span>|  
|**\<captured source table columns>**|<span data-ttu-id="160a9-209">Variiert</span><span class="sxs-lookup"><span data-stu-id="160a9-209">varies</span></span>|<span data-ttu-id="160a9-210">Bei den von der Funktion zurückgegebenen verbleibenden Spalten handelt es sich um die Spalten aus der Quelltabelle, die beim Erstellen der Aufzeichnungsinstanz als aufgezeichnete Spalten identifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="160a9-210">The remaining columns returned by the function are the columns from the source table that were identified as captured columns when the capture instance was created.</span></span> <span data-ttu-id="160a9-211">Wenn in der Liste der aufgezeichneten Spalten ursprünglich keine Spalten angegeben wurden, werden alle Spalten in der Quelltabelle zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="160a9-211">If no columns were originally specified in the captured column list, all columns in the source table are returned.</span></span>|  
  
 <span data-ttu-id="160a9-212">Weitere Informationen finden Sie unter [cdc.fn_cdc_get_net_changes_&#60;capture_instance&#62; &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-net-changes-capture-instance-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="160a9-212">For more information, see [cdc.fn_cdc_get_net_changes_&#60;capture_instance&#62; &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-net-changes-capture-instance-transact-sql).</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="160a9-213">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="160a9-213">Next Step</span></span>  
 <span data-ttu-id="160a9-214">Nach dem Erstellen der Tabellenwertfunktion, mit der Änderungsdaten abgefragt werden, ist der nächste Schritt der Entwurf des Datenflusses im Paket.</span><span class="sxs-lookup"><span data-stu-id="160a9-214">After you have created the table-valued function that queries for change data, the next step is to start designing the data flow in the package.</span></span>  
  
 <span data-ttu-id="160a9-215">**Nächstes Thema:** [Abrufen und Verstehen der Änderungsdaten](retrieve-and-understand-the-change-data.md)</span><span class="sxs-lookup"><span data-stu-id="160a9-215">**Next topic:** [Retrieve and Understand the Change Data](retrieve-and-understand-the-change-data.md)</span></span>  
  
  
