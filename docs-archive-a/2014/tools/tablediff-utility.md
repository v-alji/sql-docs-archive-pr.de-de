---
title: Hilfsprogramm tablediff-Hilfsprogramm | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- comparing data
- tablediff utility
- tables [SQL Server replication]
- table comparisons [SQL Server]
- command prompt utilities [SQL Server], tablediff
- troubleshooting [SQL Server replication], non-convergence
- non-convergence [SQL Server]
ms.assetid: 3c3cb865-7a4d-4d66-98f2-5935e28929fc
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0a23465a7d2c7db53475a6dca81a8471a3b78b50
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720599"
---
# <a name="tablediff-utility"></a><span data-ttu-id="39589-102">tablediff (Hilfsprogramm)</span><span class="sxs-lookup"><span data-stu-id="39589-102">tablediff Utility</span></span>
  <span data-ttu-id="39589-103">Mit dem Hilfsprogramm **tablediff** wird verglichen, ob die Daten in zwei Tabellen konvergent sind. Das Hilfsprogramm eignet sich besonders zur Problembehandlung bei mangelnder Konvergenz in einer Replikationstopologie.</span><span class="sxs-lookup"><span data-stu-id="39589-103">The **tablediff** utility is used to compare the data in two tables for non-convergence, and is particularly useful for troubleshooting non-convergence in a replication topology.</span></span> <span data-ttu-id="39589-104">Dieses Hilfsprogramm kann an der Eingabeaufforderung oder in einer Batchdatei verwendet werden, um die folgenden Aufgaben auszuführen:</span><span class="sxs-lookup"><span data-stu-id="39589-104">This utility can be used from the command prompt or in a batch file to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="39589-105">Durchführen eines zeilenweisen Vergleichs einer Quelltabelle in einer [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]-Instanz, die als Replikationsherausgeber fungiert, mit der Zieltabelle in einer oder mehreren [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]-Instanzen, die als Replikationsabonnenten fungieren.</span><span class="sxs-lookup"><span data-stu-id="39589-105">A row by row comparison between a source table in an instance of [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] acting as a replication Publisher and the destination table at one or more instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] acting as replication Subscribers.</span></span>  
  
-   <span data-ttu-id="39589-106">Ausführen eines schnellen Vergleichs, indem nur Zeilenanzahl und Schema verglichen werden.</span><span class="sxs-lookup"><span data-stu-id="39589-106">Perform a fast comparison by only comparing row counts and schema.</span></span>  
  
-   <span data-ttu-id="39589-107">Ausführen spaltenweiser Vergleiche.</span><span class="sxs-lookup"><span data-stu-id="39589-107">Perform column-level comparisons.</span></span>  
  
-   <span data-ttu-id="39589-108">Generieren eines [!INCLUDE[tsql](../includes/tsql-md.md)] -Skripts, um Abweichungen auf dem Zielserver zu beheben und auf diese Weise die Konvergenz von Quell- und Zieltabelle herzustellen.</span><span class="sxs-lookup"><span data-stu-id="39589-108">Generate a [!INCLUDE[tsql](../includes/tsql-md.md)] script to fix discrepancies at the destination server to bring the source and destination tables into convergence.</span></span>  
  
-   <span data-ttu-id="39589-109">Protokollieren von Ergebnissen in einer Ausgabedatei oder einer Tabelle in der Zieldatenbank.</span><span class="sxs-lookup"><span data-stu-id="39589-109">Log results to an output file or into a table in the destination database.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39589-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="39589-110">Syntax</span></span>  
  
```  
  
      tablediff   
[ -? ] |   
{  
        -sourceserversource_server_name[\instance_name]  
        -sourcedatabasesource_database-sourcetablesource_table_name   
    [ -sourceschemasource_schema_name ]  
    [ -sourcepasswordsource_password ]  
    [ -sourceusersource_login ]  
    [ -sourcelocked ]  
        -destinationserverdestination_server_name[\instance_name]  
        -destinationdatabasesubscription_database-destinationtabledestination_table   
    [ -destinationschemadestination_schema_name ]  
    [ -destinationpassworddestination_password ]  
    [ -destinationuserdestination_login ]  
    [ -destinationlocked ]  
    [ -blarge_object_bytes ]   
    [ -bfnumber_of_statements ]   
    [ -c ]   
    [ -dt ]   
    [ -ettable_name ]   
    [ -f [ file_name ] ]   
    [ -ooutput_file_name ]   
    [ -q ]   
    [ -rcnumber_of_retries ]   
    [ -riretry_interval ]   
    [ -strict ]  
    [ -tconnection_timeouts ]   
}  
```  
  
## <a name="arguments"></a><span data-ttu-id="39589-111">Argumente</span><span class="sxs-lookup"><span data-stu-id="39589-111">Arguments</span></span>  
 <span data-ttu-id="39589-112">[ **-?**</span><span class="sxs-lookup"><span data-stu-id="39589-112">[ **-?**</span></span> <span data-ttu-id="39589-113">]</span><span class="sxs-lookup"><span data-stu-id="39589-113">]</span></span>  
 <span data-ttu-id="39589-114">Gibt die Liste unterstützter Parameter zurück.</span><span class="sxs-lookup"><span data-stu-id="39589-114">Returns the list of supported parameters.</span></span>  
  
 <span data-ttu-id="39589-115">**-sourceServer** *source_server_name*[ **\\** _instance_name_]</span><span class="sxs-lookup"><span data-stu-id="39589-115">**-sourceserver** *source_server_name*[**\\**_instance_name_]</span></span>  
 <span data-ttu-id="39589-116">Der Name des Quellservers.</span><span class="sxs-lookup"><span data-stu-id="39589-116">Is the name of the source server.</span></span> <span data-ttu-id="39589-117">Geben Sie den _Quell \_ Server \_ Namen_ für die Standard Instanz von an [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="39589-117">Specify _source\_server\_name_ for the default instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="39589-118">Geben Sie den Instanznamen des _Quell \_ Server \_ namens_ **\\** _ \_ _ für eine benannte Instanz von an [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="39589-118">Specify _source\_server\_name_**\\**_instance\_name_ for a named instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="39589-119">**-sourcedatabase** *source_database*</span><span class="sxs-lookup"><span data-stu-id="39589-119">**-sourcedatabase** *source_database*</span></span>  
 <span data-ttu-id="39589-120">Der Name der Quelldatenbank.</span><span class="sxs-lookup"><span data-stu-id="39589-120">Is the name of the source database.</span></span>  
  
 <span data-ttu-id="39589-121">**-sourcetable** *source_table_name*</span><span class="sxs-lookup"><span data-stu-id="39589-121">**-sourcetable** *source_table_name*</span></span>  
 <span data-ttu-id="39589-122">Der Name der zu überprüfenden Quelldatenbank.</span><span class="sxs-lookup"><span data-stu-id="39589-122">Is the name of the source table being checked.</span></span>  
  
 <span data-ttu-id="39589-123">**-sourceschema** *source_schema_name*</span><span class="sxs-lookup"><span data-stu-id="39589-123">**-sourceschema** *source_schema_name*</span></span>  
 <span data-ttu-id="39589-124">Der Schemabesitzer der Quelltabelle.</span><span class="sxs-lookup"><span data-stu-id="39589-124">The schema owner of the source table.</span></span> <span data-ttu-id="39589-125">Standardmäßig wird dbo als Tabellenbesitzer angenommen.</span><span class="sxs-lookup"><span data-stu-id="39589-125">By default, the table owner is assumed to be dbo.</span></span>  
  
 <span data-ttu-id="39589-126">**-sourcepassword** *source_password*</span><span class="sxs-lookup"><span data-stu-id="39589-126">**-sourcepassword** *source_password*</span></span>  
 <span data-ttu-id="39589-127">Das Kennwort für den Anmeldenamen, der verwendet wird, um mithilfe der [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Authentifizierung eine Verbindung mit dem Quellserver herzustellen.</span><span class="sxs-lookup"><span data-stu-id="39589-127">Is the password for the login used to connect to the source server using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="39589-128">Anmeldeinformationen sollten, sofern möglich, zur Laufzeit angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="39589-128">When possible, supply security credentials at runtime.</span></span> <span data-ttu-id="39589-129">Wenn Anmeldeinformationen in einer Skriptdatei gespeichert werden müssen, sollten Sie die Datei an einem sicheren Ort speichern, um den unbefugten Zugriff zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="39589-129">If you must store credentials in a script file, you should secure the file to prevent unauthorized access.</span></span>  
  
 <span data-ttu-id="39589-130">**-sourceuser** *source_login*</span><span class="sxs-lookup"><span data-stu-id="39589-130">**-sourceuser** *source_login*</span></span>  
 <span data-ttu-id="39589-131">Der Anmeldename, der verwendet wird, um mithilfe der [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Authentifizierung eine Verbindung mit dem Quellserver herzustellen.</span><span class="sxs-lookup"><span data-stu-id="39589-131">Is the login used to connect to the source server using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="39589-132">Wenn *Quellanmeldename* nicht angegeben wird, wird die Windows-Authentifizierung zum Herstellen der Verbindung mit dem Quellserver verwendet.</span><span class="sxs-lookup"><span data-stu-id="39589-132">If *source_login* is not supplied, then Windows Authentication is used when connecting to the source server.</span></span> [!INCLUDE[ssNoteWinAuthentication](../includes/ssnotewinauthentication-md.md)]  
  
 <span data-ttu-id="39589-133">**-sourcelocked**</span><span class="sxs-lookup"><span data-stu-id="39589-133">**-sourcelocked**</span></span>  
 <span data-ttu-id="39589-134">Die Quelltabelle wird während des Vergleichs mit den Tabellenhinweisen TABLOCK und HOLDLOCK gesperrt.</span><span class="sxs-lookup"><span data-stu-id="39589-134">The source table is locked during the comparison using the TABLOCK and HOLDLOCK table hints.</span></span>  
  
 <span data-ttu-id="39589-135">**-DestinationServer** *destination_server_name*[ **\\** _ \_ Instanzname_]</span><span class="sxs-lookup"><span data-stu-id="39589-135">**-destinationserver** *destination_server_name*[**\\**_instance\_name_]</span></span>  
 <span data-ttu-id="39589-136">Der Name des Zielservers.</span><span class="sxs-lookup"><span data-stu-id="39589-136">Is the name of the destination server.</span></span> <span data-ttu-id="39589-137">Angeben von *Zielservername* für die Standardinstanz von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="39589-137">Specify *destination_server_name* for the default instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="39589-138">Geben Sie den _Namen der Ziel \_ Server \_ Namen_- **\\** _Instanz \_ _ für eine benannte Instanz von an [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="39589-138">Specify _destination\_server\_name_**\\**_instance\_name_ for a named instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="39589-139">**-destinationdatabase** *subscription_database*</span><span class="sxs-lookup"><span data-stu-id="39589-139">**-destinationdatabase** *subscription_database*</span></span>  
 <span data-ttu-id="39589-140">Der Name der Zieldatenbank.</span><span class="sxs-lookup"><span data-stu-id="39589-140">Is the name of the destination database.</span></span>  
  
 <span data-ttu-id="39589-141">**-destinationtable** *destination_table*</span><span class="sxs-lookup"><span data-stu-id="39589-141">**-destinationtable** *destination_table*</span></span>  
 <span data-ttu-id="39589-142">Entspricht dem Namen der Zieltabelle.</span><span class="sxs-lookup"><span data-stu-id="39589-142">Is the name of the destination table.</span></span>  
  
 <span data-ttu-id="39589-143">**-destinationschema** *destination_schema_name*</span><span class="sxs-lookup"><span data-stu-id="39589-143">**-destinationschema** *destination_schema_name*</span></span>  
 <span data-ttu-id="39589-144">Der Schemabesitzer der Zieltabelle.</span><span class="sxs-lookup"><span data-stu-id="39589-144">The schema owner of the destination table.</span></span> <span data-ttu-id="39589-145">Standardmäßig wird dbo als Tabellenbesitzer angenommen.</span><span class="sxs-lookup"><span data-stu-id="39589-145">By default, the table owner is assumed to be dbo.</span></span>  
  
 <span data-ttu-id="39589-146">**-destinationpassword** *destination_password*</span><span class="sxs-lookup"><span data-stu-id="39589-146">**-destinationpassword** *destination_password*</span></span>  
 <span data-ttu-id="39589-147">Das Kennwort für den Anmeldenamen, der verwendet wird, um mithilfe der [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Authentifizierung eine Verbindung mit dem Zielserver herzustellen.</span><span class="sxs-lookup"><span data-stu-id="39589-147">Is the password for the login used to connect to the destination server using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="39589-148">Anmeldeinformationen sollten, sofern möglich, zur Laufzeit angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="39589-148">When possible, supply security credentials at runtime.</span></span> <span data-ttu-id="39589-149">Wenn Anmeldeinformationen in einer Skriptdatei gespeichert werden müssen, sollten Sie die Datei an einem sicheren Ort speichern, um den unbefugten Zugriff zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="39589-149">If you must store credentials in a script file, you should secure the file to prevent unauthorized access.</span></span>  
  
 <span data-ttu-id="39589-150">**-destinationuser** *destination_login*</span><span class="sxs-lookup"><span data-stu-id="39589-150">**-destinationuser** *destination_login*</span></span>  
 <span data-ttu-id="39589-151">Der Anmeldename, der verwendet wird, um mithilfe der [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Authentifizierung eine Verbindung mit dem Zielserver herzustellen.</span><span class="sxs-lookup"><span data-stu-id="39589-151">Is the login used to connect to the destination server using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="39589-152">Wenn *Zielanmeldename* nicht angegeben wird, wird die Windows-Authentifizierung zum Herstellen der Verbindung mit dem Server verwendet.</span><span class="sxs-lookup"><span data-stu-id="39589-152">If *destination_login* is not supplied, then Windows Authentication is used when connecting to the server.</span></span> [!INCLUDE[ssNoteWinAuthentication](../includes/ssnotewinauthentication-md.md)]  
  
 <span data-ttu-id="39589-153">**-destinationlocked**</span><span class="sxs-lookup"><span data-stu-id="39589-153">**-destinationlocked**</span></span>  
 <span data-ttu-id="39589-154">Die Zieltabelle wird während des Vergleichs mit den Tabellenhinweisen TABLOCK und HOLDLOCK gesperrt.</span><span class="sxs-lookup"><span data-stu-id="39589-154">The destination table is locked during the comparison using the TABLOCK and HOLDLOCK table hints.</span></span>  
  
 <span data-ttu-id="39589-155">**-b** *large_object_bytes*</span><span class="sxs-lookup"><span data-stu-id="39589-155">**-b** *large_object_bytes*</span></span>  
 <span data-ttu-id="39589-156">Ist die Anzahl von Bytes, die für LOB-Datentyp-Spalten verglichen werden sollen, darunter: `text`, `ntext`, `image`, `varchar(max)`, `nvarchar(max)` und `varbinary(max)`.</span><span class="sxs-lookup"><span data-stu-id="39589-156">Is the number of bytes to compare for large object data type columns, which includes: `text`, `ntext`, `image`, `varchar(max)`, `nvarchar(max)` and `varbinary(max)`.</span></span> <span data-ttu-id="39589-157">*large_object_bytes* wird standardmäßig auf die Größe der Spalte festgelegt.</span><span class="sxs-lookup"><span data-stu-id="39589-157">*large_object_bytes* defaults to the size of the column.</span></span> <span data-ttu-id="39589-158">Alle Daten über *large_object_bytes* werden nicht überprüft.</span><span class="sxs-lookup"><span data-stu-id="39589-158">Any data above *large_object_bytes* will not be compared.</span></span>  
  
 <span data-ttu-id="39589-159">**-bf** *number_of_statements*</span><span class="sxs-lookup"><span data-stu-id="39589-159">**-bf**  *number_of_statements*</span></span>  
 <span data-ttu-id="39589-160">Die Anzahl der [!INCLUDE[tsql](../includes/tsql-md.md)] -Anweisungen, die in die aktuelle [!INCLUDE[tsql](../includes/tsql-md.md)] -Skriptdatei geschrieben werden können, wenn die Option **-f** verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="39589-160">Is the number of [!INCLUDE[tsql](../includes/tsql-md.md)] statements to write to the current [!INCLUDE[tsql](../includes/tsql-md.md)] script file when the **-f** option is used.</span></span> <span data-ttu-id="39589-161">Wenn die Anzahl der [!INCLUDE[tsql](../includes/tsql-md.md)] -Anweisungen *number_of_statements*überschreitet, wird eine neue [!INCLUDE[tsql](../includes/tsql-md.md)] -Skriptdatei erstellt.</span><span class="sxs-lookup"><span data-stu-id="39589-161">When the number of [!INCLUDE[tsql](../includes/tsql-md.md)] statements exceeds *number_of_statements*, a new [!INCLUDE[tsql](../includes/tsql-md.md)] script file is created.</span></span>  
  
 <span data-ttu-id="39589-162">**-c**</span><span class="sxs-lookup"><span data-stu-id="39589-162">**-c**</span></span>  
 <span data-ttu-id="39589-163">Vergleicht Unterschiede auf Spaltenebene.</span><span class="sxs-lookup"><span data-stu-id="39589-163">Compare column-level differences.</span></span>  
  
 <span data-ttu-id="39589-164">**-dt**</span><span class="sxs-lookup"><span data-stu-id="39589-164">**-dt**</span></span>  
 <span data-ttu-id="39589-165">Löscht die in *table_name*angegebene Ergebnistabelle, wenn die Tabelle bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="39589-165">Drop the result table specified by *table_name*, if the table already exists.</span></span>  
  
 <span data-ttu-id="39589-166">**-et** *table_name*</span><span class="sxs-lookup"><span data-stu-id="39589-166">**-et** *table_name*</span></span>  
 <span data-ttu-id="39589-167">Gibt den Namen der zu erstellenden Ergebnistabelle an.</span><span class="sxs-lookup"><span data-stu-id="39589-167">Specifies the name of the result table to create.</span></span> <span data-ttu-id="39589-168">Wenn diese Tabelle bereits vorhanden ist, muss **-DT** verwendet werden; andernfalls schlägt der Vorgang fehl.</span><span class="sxs-lookup"><span data-stu-id="39589-168">If this table already exists, **-DT** must be used or the operation will fail.</span></span>  
  
 <span data-ttu-id="39589-169">**-f** [ *file_name* ]</span><span class="sxs-lookup"><span data-stu-id="39589-169">**-f** [ *file_name* ]</span></span>  
 <span data-ttu-id="39589-170">Generiert ein [!INCLUDE[tsql](../includes/tsql-md.md)] -Skript, um die Konvergenz zwischen der Tabelle auf dem Zielserver und der Tabelle auf dem Quellserver herzustellen.</span><span class="sxs-lookup"><span data-stu-id="39589-170">Generates a [!INCLUDE[tsql](../includes/tsql-md.md)] script to bring the table at the destination server into convergence with the table at the source server.</span></span> <span data-ttu-id="39589-171">Optional können Sie einen Namen und einen Pfad für die generierte [!INCLUDE[tsql](../includes/tsql-md.md)] -Skriptdatei angeben.</span><span class="sxs-lookup"><span data-stu-id="39589-171">You can optionally specify a name and path for the generated [!INCLUDE[tsql](../includes/tsql-md.md)] script file.</span></span> <span data-ttu-id="39589-172">Wurde *file_name* nicht angegeben, wird die [!INCLUDE[tsql](../includes/tsql-md.md)] -Skriptdatei in dem Verzeichnis erstellt, in dem das Hilfsprogramm ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="39589-172">If *file_name* is not specified, the [!INCLUDE[tsql](../includes/tsql-md.md)] script file is generated in the directory where the utility runs.</span></span>  
  
 <span data-ttu-id="39589-173">**-o** *output_file_name*</span><span class="sxs-lookup"><span data-stu-id="39589-173">**-o** *output_file_name*</span></span>  
 <span data-ttu-id="39589-174">Gibt den vollständigen Namen und Pfad der Ausgabedatei an.</span><span class="sxs-lookup"><span data-stu-id="39589-174">Is the full name and path of the output file.</span></span>  
  
 <span data-ttu-id="39589-175">**-q**</span><span class="sxs-lookup"><span data-stu-id="39589-175">**-q**</span></span>  
 <span data-ttu-id="39589-176">Ausführen eines schnellen Vergleichs, indem nur Zeilenanzahl und Schema verglichen werden.</span><span class="sxs-lookup"><span data-stu-id="39589-176">Perform a fast comparison by only comparing row counts and schema.</span></span>  
  
 <span data-ttu-id="39589-177">**-rc** *number_of_retries*</span><span class="sxs-lookup"><span data-stu-id="39589-177">**-rc** *number_of_retries*</span></span>  
 <span data-ttu-id="39589-178">Gibt an, wie oft das Hilfsprogramm einen fehlgeschlagenen Vorgang wiederholt.</span><span class="sxs-lookup"><span data-stu-id="39589-178">Number of times that the utility retries a failed operation.</span></span>  
  
 <span data-ttu-id="39589-179">**-ri** *retry_interval*</span><span class="sxs-lookup"><span data-stu-id="39589-179">**-ri**  *retry_interval*</span></span>  
 <span data-ttu-id="39589-180">Gibt das Intervall (in Sekunden) zwischen den Wiederholungen an.</span><span class="sxs-lookup"><span data-stu-id="39589-180">Interval, in seconds, to wait between retries.</span></span>  
  
 <span data-ttu-id="39589-181">**-strict**</span><span class="sxs-lookup"><span data-stu-id="39589-181">**-strict**</span></span>  
 <span data-ttu-id="39589-182">Für Quell- und Zielschema wird ein strenger Vergleich durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="39589-182">Source and destination schema are strictly compared.</span></span>  
  
 <span data-ttu-id="39589-183">**-t** *connection_timeouts*</span><span class="sxs-lookup"><span data-stu-id="39589-183">**-t** *connection_timeouts*</span></span>  
 <span data-ttu-id="39589-184">Legt das Verbindungstimeout (in Sekunden) für Verbindungen zwischen dem Quellserver und dem Zielserver fest.</span><span class="sxs-lookup"><span data-stu-id="39589-184">Sets the connection timeout period, in seconds, for connections to the source server and destination server.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="39589-185">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="39589-185">Return Value</span></span>  
  
|<span data-ttu-id="39589-186">Wert</span><span class="sxs-lookup"><span data-stu-id="39589-186">Value</span></span>|<span data-ttu-id="39589-187">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="39589-187">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="39589-188">**0**</span><span class="sxs-lookup"><span data-stu-id="39589-188">**0**</span></span>|<span data-ttu-id="39589-189">Erfolg</span><span class="sxs-lookup"><span data-stu-id="39589-189">Success</span></span>|  
|<span data-ttu-id="39589-190">**1**</span><span class="sxs-lookup"><span data-stu-id="39589-190">**1**</span></span>|<span data-ttu-id="39589-191">Schwerwiegender Fehler</span><span class="sxs-lookup"><span data-stu-id="39589-191">Critical error</span></span>|  
|<span data-ttu-id="39589-192">**2**</span><span class="sxs-lookup"><span data-stu-id="39589-192">**2**</span></span>|<span data-ttu-id="39589-193">Tabellenunterschiede</span><span class="sxs-lookup"><span data-stu-id="39589-193">Table differences</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="39589-194">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="39589-194">Remarks</span></span>  
 <span data-ttu-id="39589-195">Das Hilfsprogramm **Hilfsprogramm tablediff** kann nicht mit nicht--Servern verwendet werden [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="39589-195">The **tablediff** utility cannot be used with non-[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] servers.</span></span>  
  
 <span data-ttu-id="39589-196">Tabellen, die Spalten des Datentyps `sql_variant` enthalten, werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="39589-196">Tables with `sql_variant` data type columns are not supported.</span></span>  
  
 <span data-ttu-id="39589-197">Standardmäßig unterstützt das Hilfsprogramm **tablediff** die folgenden Datentypzuordnungen zwischen Quell- und Zielspalten.</span><span class="sxs-lookup"><span data-stu-id="39589-197">By default, the **tablediff** utility supports the following data type mappings between source and destination columns.</span></span>  
  
|<span data-ttu-id="39589-198">Quelldatentyp</span><span class="sxs-lookup"><span data-stu-id="39589-198">Source data type</span></span>|<span data-ttu-id="39589-199">Zieldatentyp</span><span class="sxs-lookup"><span data-stu-id="39589-199">Destination data type</span></span>|  
|----------------------|---------------------------|  
|`tinyint`|<span data-ttu-id="39589-200">`smallint`, `int` oder `bigint`</span><span class="sxs-lookup"><span data-stu-id="39589-200">`smallint`, `int`, or `bigint`</span></span>|  
|`smallint`|<span data-ttu-id="39589-201">`int` oder `bigint`</span><span class="sxs-lookup"><span data-stu-id="39589-201">`int` or `bigint`</span></span>|  
|`int`|`bigint`|  
|`timestamp`|`varbinary`|  
|`varchar(max)`|`text`|  
|`nvarchar(max)`|`ntext`|  
|`varbinary(max)`|`image`|  
|`text`|`varchar(max)`|  
|`ntext`|`nvarchar(max)`|  
|`image`|`varbinary(max)`|  
  
 <span data-ttu-id="39589-202">Verwenden Sie die Option **-strict** , wenn Sie diese Zuordnungen nicht zulassen und eine strenge Überprüfung durchführen möchten.</span><span class="sxs-lookup"><span data-stu-id="39589-202">Use the **-strict** option to disallow these mappings and perform a strict validation.</span></span>  
  
 <span data-ttu-id="39589-203">Die Quelltabelle bei dem Vergleich muss mindestens eine Primärschlüssel-, Identitäts- oder ROWGUID-Spalte enthalten.</span><span class="sxs-lookup"><span data-stu-id="39589-203">The source table in the comparison must contain at least one primary key, identity, or ROWGUID column.</span></span> <span data-ttu-id="39589-204">Wenn Sie die Option **-strict** verwenden, muss die Zieltabelle ebenfalls eine Primärschlüssel-, Identitäts- oder ROWGUID-Spalte enthalten.</span><span class="sxs-lookup"><span data-stu-id="39589-204">When you use the **-strict** option, the destination table must also have a primary key, identity, or ROWGUID column.</span></span>  
  
 <span data-ttu-id="39589-205">Das [!INCLUDE[tsql](../includes/tsql-md.md)] -Skript, das generiert wurde, um die Konvergenz der Zieltabelle herzustellen, enthält die folgenden Datentypen nicht:</span><span class="sxs-lookup"><span data-stu-id="39589-205">The [!INCLUDE[tsql](../includes/tsql-md.md)] script generated to bring the destination table into convergence does not include the following data types:</span></span>  
  
-   `varchar(max)`  
  
-   `nvarchar(max)`  
  
-   `varbinary(max)`  
  
-   `timestamp`  
  
-   <span data-ttu-id="39589-206">**xml**</span><span class="sxs-lookup"><span data-stu-id="39589-206">**xml**</span></span>  
  
-   `text`  
  
-   `ntext`  
  
-   `image`  
  
## <a name="permissions"></a><span data-ttu-id="39589-207">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="39589-207">Permissions</span></span>  
 <span data-ttu-id="39589-208">Für den Vergleich von Tabellen benötigen Sie SELECT ALL-Berechtigungen für die zu vergleichenden Tabellenobjekte.</span><span class="sxs-lookup"><span data-stu-id="39589-208">To compare tables, you need SELECT ALL permissions on the table objects being compared.</span></span>  
  
 <span data-ttu-id="39589-209">Damit Sie die Option **-et** verwenden können, müssen Sie ein Mitglied der festen Datenbankrolle db_owner sein oder zumindest über die CREATE TABLE-Berechtigung für die Abonnementdatenbank und die ALTER-Berechtigung für das Zielbesitzerschema auf dem Zielserver verfügen.</span><span class="sxs-lookup"><span data-stu-id="39589-209">To use the **-et** option, you must be a member of the db_owner fixed database role, or at least have CREATE TABLE permission in the subscription database and ALTER permission on the destination owner schema at the destination server.</span></span>  
  
 <span data-ttu-id="39589-210">Damit Sie die Option **-dt** verwenden können, müssen Sie ein Mitglied der festen Datenbankrolle db_owner sein oder zumindest über die ALTER-Berechtigung für das Zielbesitzerschema auf dem Zielserver verfügen.</span><span class="sxs-lookup"><span data-stu-id="39589-210">To use the **-dt** option, you must be a member of the db_owner fixed database role, or at least have ALTER permission on the destination owner schema at the destination server.</span></span>  
  
 <span data-ttu-id="39589-211">Damit Sie die Option **-o** oder **-f** verwenden können, müssen Sie über Schreibberechtigungen für das angegebene Dateiverzeichnis verfügen.</span><span class="sxs-lookup"><span data-stu-id="39589-211">To use the **-o** or **-f** options, you must have write permissions to the specified file directory location.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39589-212">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="39589-212">See Also</span></span>  
 [<span data-ttu-id="39589-213">Überprüfen replizierter Tabellen auf Unterschiede &#40;Replikationsprogrammierung&#41;</span><span class="sxs-lookup"><span data-stu-id="39589-213">Compare Replicated Tables for Differences &#40;Replication Programming&#41;</span></span>](../relational-databases/replication/administration/compare-replicated-tables-for-differences-replication-programming.md)  
  
  
