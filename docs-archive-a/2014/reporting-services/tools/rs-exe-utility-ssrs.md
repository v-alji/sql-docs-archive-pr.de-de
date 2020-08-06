---
title: Hilfsprogramm „RS.exe“ (SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- automatic report server tasks
- rs utility
- command prompt utilities [Reporting Services]
- report servers [Reporting Services], automating tasks
- command prompt utilities [SQL Server], rs
- scripts [Reporting Services], command prompt
- deploying reports [Reporting Services]
ms.assetid: bd6f958f-cce6-4e79-8a0f-9475da2919ce
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bcf21a1bf2453d2bd1f0644e31ca46f3f94e6884
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721025"
---
# <a name="rsexe-utility-ssrs"></a><span data-ttu-id="ee183-102">Hilfsprogramm 'RS.exe' (SSRS)</span><span class="sxs-lookup"><span data-stu-id="ee183-102">RS.exe Utility (SSRS)</span></span>
  <span data-ttu-id="ee183-103">Das Dienstprogramm rs.exe verarbeitet Skripts, die von Ihnen in einer Eingabedatei bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="ee183-103">The rs.exe utility processes script that you provide in an input file.</span></span> <span data-ttu-id="ee183-104">Verwenden Sie dieses Hilfsprogramm, um die Berichtsserverbereitstellung und Verwaltungsaufgaben zu automatisieren.</span><span class="sxs-lookup"><span data-stu-id="ee183-104">Use this utility to automate report server deployment and administration tasks.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ee183-105">In [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]und höheren Versionen wird die Verwendung des **rs** -Hilfsprogramms für Berichtsserver unterstützt, die für den integrierten SharePoint-Modus konfiguriert wurden, sowie für Server, die im einheitlichen Modus konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="ee183-105">Beginning with [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], the **rs** utility is supported against report servers that are configured for SharePoint integrated mode as well as servers configured in native mode.</span></span> <span data-ttu-id="ee183-106">In früheren Versionen wurden nur Konfigurationen im einheitlichen Modus unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ee183-106">Previous versions only supported native mode configurations.</span></span>  
  
 <span data-ttu-id="ee183-107">**In diesem Thema:**</span><span class="sxs-lookup"><span data-stu-id="ee183-107">**In this topic:**</span></span>  
  
-   [<span data-ttu-id="ee183-108">Datei Speicherort</span><span class="sxs-lookup"><span data-stu-id="ee183-108">File Location</span></span>](#bkmk_filelocation)  
  
-   [<span data-ttu-id="ee183-109">Argumente</span><span class="sxs-lookup"><span data-stu-id="ee183-109">Arguments</span></span>](#bkmk_arguments)  
  
-   [<span data-ttu-id="ee183-110">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="ee183-110">Permissions</span></span>](#bkmk_permissions)  
  
-   [<span data-ttu-id="ee183-111">Beispiele</span><span class="sxs-lookup"><span data-stu-id="ee183-111">Examples</span></span>](#bkmk_examples)  
  
## <a name="syntax"></a><span data-ttu-id="ee183-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="ee183-112">Syntax</span></span>  
  
```  
  
      rs {-?}  
{-i input_file=}  
{-s serverURL}  
{-u username}  
{-p password}  
{-e endpoint}  
{-l time_out}  
{-b batchmode}  
{-v globalvars=}  
{-t trace}  
```  
  
##  <a name="file-location"></a><a name="bkmk_filelocation"></a> <span data-ttu-id="ee183-113">Dateispeicherort</span><span class="sxs-lookup"><span data-stu-id="ee183-113">File Location</span></span>  
 <span data-ttu-id="ee183-114">**RS.exe** befindet sich unter **\Programme\Microsoft SQL Server\110\Tools\Binn**.</span><span class="sxs-lookup"><span data-stu-id="ee183-114">**RS.exe** is located at **\Program Files\Microsoft SQL Server\110\Tools\Binn**.</span></span> <span data-ttu-id="ee183-115">Sie können das Hilfsprogramm von einem beliebigen Ordner im Dateisystem ausführen.</span><span class="sxs-lookup"><span data-stu-id="ee183-115">You can run the utility from any folder on your file system.</span></span>  
  
##  <a name="arguments"></a><a name="bkmk_arguments"></a><span data-ttu-id="ee183-116">Argumente</span><span class="sxs-lookup"><span data-stu-id="ee183-116">Arguments</span></span>  
 <span data-ttu-id="ee183-117">**-?**</span><span class="sxs-lookup"><span data-stu-id="ee183-117">**-?**</span></span>  
 <span data-ttu-id="ee183-118">(Optional) Zeigt die Syntax der **rs** -Argumente an.</span><span class="sxs-lookup"><span data-stu-id="ee183-118">(Optional) Displays the syntax of **rs** arguments.</span></span>  
  
 <span data-ttu-id="ee183-119">`-i`*input_file*</span><span class="sxs-lookup"><span data-stu-id="ee183-119">`-i` *input_file*</span></span>  
 <span data-ttu-id="ee183-120">(Erforderlich) Gibt die auszuführende RSS-Datei an.</span><span class="sxs-lookup"><span data-stu-id="ee183-120">(Required) Specifies the .rss file to execute.</span></span> <span data-ttu-id="ee183-121">Dieser Wert kann einen relativen oder einen vollqualifizierten Pfad zur RSS-Datei enthalten.</span><span class="sxs-lookup"><span data-stu-id="ee183-121">This value can be a relative or fully qualified path to the .rss file.</span></span>  
  
 <span data-ttu-id="ee183-122">`-s`*ServerURL*</span><span class="sxs-lookup"><span data-stu-id="ee183-122">`-s` *serverURL*</span></span>  
 <span data-ttu-id="ee183-123">(Erforderlich) Gibt den Namen des Webservers und den Namen des virtuellen Verzeichnisses auf dem Berichtsserver an, in dem die Datei ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="ee183-123">(Required) Specifies the Web server name and report server virtual directory name to execute the file against.</span></span> <span data-ttu-id="ee183-124">Ein Beispiel für eine Berichtsserver-URL ist `http://examplewebserver/reportserver`.</span><span class="sxs-lookup"><span data-stu-id="ee183-124">An example of a report server URL is `http://examplewebserver/reportserver`.</span></span> <span data-ttu-id="ee183-125">Das Präfix http:// oder https:// zu Beginn des Servernamens ist optional.</span><span class="sxs-lookup"><span data-stu-id="ee183-125">The prefix http:// or https:// at the beginning of the server name is optional.</span></span> <span data-ttu-id="ee183-126">Wenn Sie kein Präfix angeben, verwendet der Berichtsserver-Skripthost zunächst https:// und dann http://, falls https:// nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="ee183-126">If you omit the prefix, the report server script host tries to use https first, and then uses http if https does not work.</span></span>  
  
 <span data-ttu-id="ee183-127">`-u`[*Domäne* \\ ] *Benutzername*</span><span class="sxs-lookup"><span data-stu-id="ee183-127">`-u` [*domain*\\]*username*</span></span>  
 <span data-ttu-id="ee183-128">(Optional) Gibt ein Benutzerkonto an, das für die Herstellung einer Verbindung mit dem Berichtsserver verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ee183-128">(Optional) Specifies a user account used to connect to the report server.</span></span> <span data-ttu-id="ee183-129">Wenn `-u` und `-p` nicht angegeben werden, wird das aktuelle Windows-Benutzerkonto verwendet.</span><span class="sxs-lookup"><span data-stu-id="ee183-129">If `-u` and `-p` are omitted, the current Windows user account is used.</span></span>  
  
 <span data-ttu-id="ee183-130">`-p` *password*</span><span class="sxs-lookup"><span data-stu-id="ee183-130">`-p` *password*</span></span>  
 <span data-ttu-id="ee183-131">(Erforderlich, wenn `-u` angegeben ist.) Gibt das Kennwort an, das mit dem `-u`-Argument verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ee183-131">(Required if `-u` is specified) Specifies the password to use with the `-u` argument.</span></span> <span data-ttu-id="ee183-132">Bei diesem Wert wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="ee183-132">This value is case-sensitive.</span></span>  
  
 `-e`  
 <span data-ttu-id="ee183-133">(Optional) Gibt den SOAP-Endpunkt für die Ausführung des Skripts an.</span><span class="sxs-lookup"><span data-stu-id="ee183-133">(Optional) Specifies the SOAP endpoint against which the script should run.</span></span> <span data-ttu-id="ee183-134">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="ee183-134">Valid values are the following:</span></span>  
  
-   <span data-ttu-id="ee183-135">Mgmt2010</span><span class="sxs-lookup"><span data-stu-id="ee183-135">Mgmt2010</span></span>  
  
-   <span data-ttu-id="ee183-136">Mgmt2006</span><span class="sxs-lookup"><span data-stu-id="ee183-136">Mgmt2006</span></span>  
  
-   <span data-ttu-id="ee183-137">Mgmt2005</span><span class="sxs-lookup"><span data-stu-id="ee183-137">Mgmt2005</span></span>  
  
-   <span data-ttu-id="ee183-138">Exec2005</span><span class="sxs-lookup"><span data-stu-id="ee183-138">Exec2005</span></span>  
  
 <span data-ttu-id="ee183-139">Wird kein Wert angegeben, wird der Endpunkt Mgmt2005 verwendet.</span><span class="sxs-lookup"><span data-stu-id="ee183-139">If a value is not specified, the Mgmt2005 endpoint is used.</span></span> <span data-ttu-id="ee183-140">Weitere Informationen zu den SOAP-Endpunkten finden Sie unter [Report Server Web Service Endpoints](../report-server-web-service/methods/report-server-web-service-endpoints.md).</span><span class="sxs-lookup"><span data-stu-id="ee183-140">For more information about the SOAP endpoints, see [Report Server Web Service Endpoints](../report-server-web-service/methods/report-server-web-service-endpoints.md).</span></span>  
  
 <span data-ttu-id="ee183-141">`-l`*time_out*</span><span class="sxs-lookup"><span data-stu-id="ee183-141">`-l` *time_out*</span></span>  
 <span data-ttu-id="ee183-142">Optionale Gibt die Anzahl der Sekunden an, die Verläufen, bevor die Verbindung mit dem Server über einen Timeout eintritt. Der Standardwert ist 60 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="ee183-142">(Optional) Specifies the number of seconds that elapse before the connection to the server times out. The default is 60 seconds.</span></span> <span data-ttu-id="ee183-143">Wenn Sie keinen Timeoutwert angeben, wird der Standardwert verwendet.</span><span class="sxs-lookup"><span data-stu-id="ee183-143">If you do not specify a time-out value, the default is used.</span></span> <span data-ttu-id="ee183-144">Ein Wert von `0` gibt an, dass sich für die Verbindung kein Timeout ergibt.</span><span class="sxs-lookup"><span data-stu-id="ee183-144">A value of `0` specifies that the connection never times out.</span></span>  
  
 <span data-ttu-id="ee183-145">**-b**</span><span class="sxs-lookup"><span data-stu-id="ee183-145">**-b**</span></span>  
 <span data-ttu-id="ee183-146">(Optional) Gibt an, dass die Befehle in der Skriptdatei als Batch ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ee183-146">(Optional) Specifies that the commands in the script file run in a batch.</span></span> <span data-ttu-id="ee183-147">Falls ein Befehl fehlschlägt, wird ein Rollback für den Batch ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ee183-147">If any commands fail, the batch is rolled back.</span></span> <span data-ttu-id="ee183-148">Einige Befehle können nicht als Batch ausgeführt werden. Diese Befehle werden wie gewohnt ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ee183-148">Some commands cannot be batched, and those run as usual.</span></span> <span data-ttu-id="ee183-149">Nur Ausnahmen, die ausgegeben werden und nicht innerhalb des Skripts behandelt werden, führen zu einem Rollback.</span><span class="sxs-lookup"><span data-stu-id="ee183-149">Only exceptions that are thrown and are not handled within the script result in a rollback.</span></span> <span data-ttu-id="ee183-150">Wenn das Skript eine Ausnahme behandelt und normalerweise von `Main` zurückgegeben wird, wird ein Commit für den Batch ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ee183-150">If the script handles an exception and returns normally from `Main`, the batch is committed.</span></span> <span data-ttu-id="ee183-151">Wenn Sie diesen Parameter nicht angeben, werden die Befehle ausgeführt, ohne dass ein Batch erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="ee183-151">If you omit this parameter, the commands run without creating a batch.</span></span> <span data-ttu-id="ee183-152">Weitere Informationen finden Sie unter [Batching Methods](../report-server-web-service-net-framework-soap-headers/batching-methods.md).</span><span class="sxs-lookup"><span data-stu-id="ee183-152">For more information, see [Batching Methods](../report-server-web-service-net-framework-soap-headers/batching-methods.md).</span></span>  
  
 <span data-ttu-id="ee183-153">`-v`*globalvar*</span><span class="sxs-lookup"><span data-stu-id="ee183-153">`-v` *globalvar*</span></span>  
 <span data-ttu-id="ee183-154">(Optional) Gibt globale Variablen an, die in dem Skript verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ee183-154">(Optional) Specifies global variables that are used in the script.</span></span> <span data-ttu-id="ee183-155">Wenn das Skript globale Variablen verwendet, müssen Sie dieses Argument angeben.</span><span class="sxs-lookup"><span data-stu-id="ee183-155">If the script uses global variables, you must specify this argument.</span></span> <span data-ttu-id="ee183-156">Der angegebene Wert muss für die in der RSS-Datei definierten globalen Variablen gültig sein.</span><span class="sxs-lookup"><span data-stu-id="ee183-156">The value that you specify must be valid for global variable defined in the .rss file.</span></span> <span data-ttu-id="ee183-157">Sie müssen eine globale Variable für jedes **-v-** Argument angeben.</span><span class="sxs-lookup"><span data-stu-id="ee183-157">You must specify one global variable for each **-v** argument.</span></span>  
  
 <span data-ttu-id="ee183-158">Das Argument `-v` wird in der Befehlszeile angegeben und verwendet, um zur Laufzeit einen Wert für eine globale Variable festzulegen, die in Ihrem Skript definiert ist.</span><span class="sxs-lookup"><span data-stu-id="ee183-158">The `-v` argument is specified on the command line and is used to set the value for a global variable that is defined in your script at run time.</span></span> <span data-ttu-id="ee183-159">Wenn Ihr Skript beispielsweise eine Variable namens *parentFolder*, enthält, können Sie in der Befehlszeile einen Namen für diesen Ordner angeben:</span><span class="sxs-lookup"><span data-stu-id="ee183-159">For example, if your script contains a variable named *parentFolder*, you can specify a name for that folder on the command line:</span></span>  
  
 `rs.exe -i myScriptFile.rss -s http://myServer/reportserver -v parentFolder="Financial Reports"`  
  
 <span data-ttu-id="ee183-160">Globale Variablen werden mit den vorliegenden Namen erstellt und auf die bereitgestellten Werte festgelegt.</span><span class="sxs-lookup"><span data-stu-id="ee183-160">Global variables are created with the names given and set to the values supplied.</span></span> <span data-ttu-id="ee183-161">Beispielsweise führt **-v a =**" `1` " **-v b =**" `2` " zu einer Variablen `a` mit dem Namen mit dem Wert " `1` " und einer Variablen **b** mit dem Wert " `2` ".</span><span class="sxs-lookup"><span data-stu-id="ee183-161">For example, **-v a=**"`1`" **-v b=**"`2`" results in a variable named `a` with a value of"`1`" and a variable **b** with a value of "`2`".</span></span>  
  
 <span data-ttu-id="ee183-162">Globale Variablen stehen für alle Funktionen im Skript zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="ee183-162">Global variables are available to any function in the script.</span></span> <span data-ttu-id="ee183-163">Ein umgekehrter Schrägstrich und ein Anführungszeichen (\*\* \\ "\*\*) werden als doppeltes Anführungszeichen interpretiert.</span><span class="sxs-lookup"><span data-stu-id="ee183-163">A backslash and quotation mark (**\\"**) is interpreted as a double quotation mark.</span></span> <span data-ttu-id="ee183-164">Anführungszeichen sind nur erforderlich, wenn die Zeichenfolge ein Leerzeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="ee183-164">The quotation marks are required only if the string contains a space.</span></span> <span data-ttu-id="ee183-165">Variablennamen müssen für gültig sein [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] . Sie müssen mit einem Buchstaben oder Unterstrich beginnen und alphabetische Zeichen, Ziffern oder Unterstriche enthalten.</span><span class="sxs-lookup"><span data-stu-id="ee183-165">Variable names must be valid for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]; they must start with alphabetical character or underscore and contain alphabetical characters, digits, or underscores.</span></span> <span data-ttu-id="ee183-166">Reservierte Wörter können nicht als Variablennamen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ee183-166">Reserved words cannot be used as variable names.</span></span> <span data-ttu-id="ee183-167">Weitere Informationen zur Verwendung globaler Variablen finden Sie unter [Integrierte Sammlungen in Ausdrücken &#40;Berichts-Generator und SSRS&#41;](../report-design/built-in-collections-in-expressions-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="ee183-167">For more information about using global variables, see [Built-in Collections in Expressions &#40;Report Builder and SSRS&#41;](../report-design/built-in-collections-in-expressions-report-builder.md).</span></span>  
  
 <span data-ttu-id="ee183-168">**-t**</span><span class="sxs-lookup"><span data-stu-id="ee183-168">**-t**</span></span>  
 <span data-ttu-id="ee183-169">(Optional) Schreibt Fehlermeldungen in das Ablaufverfolgungsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="ee183-169">(Optional) Outputs error messages to the trace log.</span></span> <span data-ttu-id="ee183-170">Dieses Argument enthält keinen Wert.</span><span class="sxs-lookup"><span data-stu-id="ee183-170">This argument does not take a value.</span></span> <span data-ttu-id="ee183-171">Weitere Informationen finden Sie unter [Report Server Service Trace Log](../report-server/report-server-service-trace-log.md).</span><span class="sxs-lookup"><span data-stu-id="ee183-171">For more information, see [Report Server Service Trace Log](../report-server/report-server-service-trace-log.md).</span></span>  
  
##  <a name="permissions"></a><a name="bkmk_permissions"></a> <span data-ttu-id="ee183-172">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="ee183-172">Permissions</span></span>  
 <span data-ttu-id="ee183-173">Um das Tool ausführen zu können, müssen Sie die Berechtigung besitzen, eine Verbindung mit der Berichtsserverinstanz herzustellen, für die das Skript ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ee183-173">To run the tool, you must have permission to connect to the report server instance you are running the script against.</span></span> <span data-ttu-id="ee183-174">Durch das Ausführen von Skripts können Sie Änderungen am lokalen Computer oder an einem Remotecomputer durchführen.</span><span class="sxs-lookup"><span data-stu-id="ee183-174">You can run scripts to make changes to the local computer or a remote computer.</span></span> <span data-ttu-id="ee183-175">Sollen Änderungen an einem Berichtsserver durchgeführt werden, der auf einem Remotecomputer installiert ist, geben Sie den Remotecomputer im `-s`-Argument an.</span><span class="sxs-lookup"><span data-stu-id="ee183-175">To make changes to a report server installed on a remote computer, specify the remote computer in the `-s` argument.</span></span>  
  
##  <a name="examples"></a><a name="bkmk_examples"></a> <span data-ttu-id="ee183-176">Beispiele</span><span class="sxs-lookup"><span data-stu-id="ee183-176">Examples</span></span>  
 <span data-ttu-id="ee183-177">Das folgende Beispiel zeigt, wie die Skriptdatei angegeben wird, die das [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .NET-Skript und die auszuführenden Webdienstmethoden enthält.</span><span class="sxs-lookup"><span data-stu-id="ee183-177">The following example illustrates how to specify the script file that contains [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .NET script and Web service methods that you want to execute.</span></span>  
  
```  
rs -i c:\scriptfiles\script_copycontent.rss -s http://localhost/reportserver  
```  
  
 <span data-ttu-id="ee183-178"> Ein ausführliches Beispiel finden Sie unter [Sample Reporting Services rs.exe Script to Migrate Content between Report Servers](sample-reporting-services-rs-exe-script-to-copy-content-between-report-servers.md).</span><span class="sxs-lookup"><span data-stu-id="ee183-178">For a detailed example, see [Sample Reporting Services rs.exe Script to Migrate Content between Report Servers](sample-reporting-services-rs-exe-script-to-copy-content-between-report-servers.md).</span></span>  
  
 <span data-ttu-id="ee183-179">Weitere Beispiele finden Sie unter [Ausführen einer Reporting Services-Skriptdatei](run-a-reporting-services-script-file.md)</span><span class="sxs-lookup"><span data-stu-id="ee183-179">For additional examples, see [Run a Reporting Services Script File](run-a-reporting-services-script-file.md)</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ee183-180">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ee183-180">Remarks</span></span>  
 <span data-ttu-id="ee183-181">Sie können Skripts so definieren, dass sie Systemeigenschaften festlegen, Berichte veröffentlichen usw.</span><span class="sxs-lookup"><span data-stu-id="ee183-181">You can define scripts to set system properties, publish reports, and so forth.</span></span> <span data-ttu-id="ee183-182">Die Skripts, die Sie erstellen, können jede Methode der [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -API einschließen.</span><span class="sxs-lookup"><span data-stu-id="ee183-182">The scripts that you create can include any methods of the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] API.</span></span> <span data-ttu-id="ee183-183">Weitere Informationen zu den verfügbaren Methoden und Eigenschaften finden Sie unter [Report Server Web Service](../report-server-web-service/report-server-web-service.md).</span><span class="sxs-lookup"><span data-stu-id="ee183-183">For more information about the methods and properties available to you, see [Report Server Web Service](../report-server-web-service/report-server-web-service.md).</span></span>  
  
 <span data-ttu-id="ee183-184">Das Skript muss in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .NET-Code geschrieben und in einer Unicode- oder UTF-8-Textdatei mit der Dateinamenerweiterung „.rss“ gespeichert sein.</span><span class="sxs-lookup"><span data-stu-id="ee183-184">The script must be written in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .NET code, and stored in a Unicode or UTF-8 text file with an .rss file name extension.</span></span> <span data-ttu-id="ee183-185">Das Hilfsprogramm **rs** kann nicht zum Debuggen von Skripts verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ee183-185">You cannot debug scripts with the **rs** utility.</span></span> <span data-ttu-id="ee183-186">Führen Sie den Code in aus, um ein Skript zu Debuggen [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ee183-186">To debug a script, run the code within [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="ee183-187"> Ein ausführliches Beispiel finden Sie unter [Sample Reporting Services rs.exe Script to Migrate Content between Report Servers](sample-reporting-services-rs-exe-script-to-copy-content-between-report-servers.md).</span><span class="sxs-lookup"><span data-stu-id="ee183-187">For a detailed example, see [Sample Reporting Services rs.exe Script to Migrate Content between Report Servers](sample-reporting-services-rs-exe-script-to-copy-content-between-report-servers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee183-188">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ee183-188">See Also</span></span>  
 <span data-ttu-id="ee183-189">[Ausführen einer Reporting Services Skriptdatei](run-a-reporting-services-script-file.md) </span><span class="sxs-lookup"><span data-stu-id="ee183-189">[Run a Reporting Services Script File](run-a-reporting-services-script-file.md) </span></span>  
 <span data-ttu-id="ee183-190">[Skript Bereitstellungs-und Verwaltungsaufgaben](script-deployment-and-administrative-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="ee183-190">[Script Deployment and Administrative Tasks](script-deployment-and-administrative-tasks.md) </span></span>  
 <span data-ttu-id="ee183-191">[Skripterstellung mit dem rs.exe-Hilfsprogramm und dem Webdienst](script-with-the-rs-exe-utility-and-the-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="ee183-191">[Script with the rs.exe Utility and the Web Service](script-with-the-rs-exe-utility-and-the-web-service.md) </span></span>  
 [<span data-ttu-id="ee183-192">Eingabeaufforderungs-Hilfsprogramme für Berichtsserver &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="ee183-192">Report Server Command Prompt Utilities &#40;SSRS&#41;</span></span>](report-server-command-prompt-utilities-ssrs.md)  
  
  
