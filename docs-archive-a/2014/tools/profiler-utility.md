---
title: Profiler-Hilfsprogramm | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- command prompt utilities [SQL Server], profiler90 utility
- profiler90 utility
- Profiler [SQL Server Profiler], starting
- SQL Server Profiler, starting
- starting SQL Server Profiler
ms.assetid: e91c30a9-0d29-4f84-bcb8-e8fb62afadda
author: stevestein
ms.author: sstein
ms.openlocfilehash: a8df3e8557bb52839d17291bae0c5ba507d0a671
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694970"
---
# <a name="profiler-utility"></a><span data-ttu-id="9d72e-102">Profiler-Hilfsprogramm</span><span class="sxs-lookup"><span data-stu-id="9d72e-102">Profiler Utility</span></span>
  <span data-ttu-id="9d72e-103">Mit dem **Profiler** -Hilfsprogramm wird das [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] -Tool gestartet.</span><span class="sxs-lookup"><span data-stu-id="9d72e-103">The **profiler** utility launches the [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] tool.</span></span> <span data-ttu-id="9d72e-104">Mit den optionalen Argumenten, die weiter unten in diesem Thema aufgeführt sind, können Sie steuern, wie die Anwendung gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="9d72e-104">The optional arguments listed later in this topic allow you to control how the application starts.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9d72e-105">Das **Profiler** -Hilfsprogramm dient nicht zum Erstellen von Skripts für Ablaufverfolgungen.</span><span class="sxs-lookup"><span data-stu-id="9d72e-105">The **profiler** utility is not intended for scripting traces.</span></span> <span data-ttu-id="9d72e-106">Weitere Informationen finden Sie unter [SQL Server Profiler](sql-server-profiler/sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="9d72e-106">For more information, see [SQL Server Profiler](sql-server-profiler/sql-server-profiler.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d72e-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="9d72e-107">Syntax</span></span>  
  
```  
  
      profiler  
          [ /? ] |  
[  
{  
{ /U login_id [ /P password ] }  
| /E  
}  
{[ /S sql_server_name ] | [ /A analysis_services_server_name ] }  
[ /D database ]  
[ /T "template_name" ]  
[ /B { "trace_table_name" } ]  
{ [/F "filename" ] | [ /O "filename" ] }  
[ /L locale_ID ]  
[ /M "MM-DD-YY hh:mm:ss" ]  
[ /R ]  
[ /Z file_size ]  
]  
```  
  
## <a name="arguments"></a><span data-ttu-id="9d72e-108">Argumente</span><span class="sxs-lookup"><span data-stu-id="9d72e-108">Arguments</span></span>  
 <span data-ttu-id="9d72e-109">**/?**</span><span class="sxs-lookup"><span data-stu-id="9d72e-109">**/?**</span></span>  
 <span data-ttu-id="9d72e-110">Zeigt die Syntaxzusammenfassung der **Profiler** -Argumente an.</span><span class="sxs-lookup"><span data-stu-id="9d72e-110">Displays the syntax summary of **profiler** arguments.</span></span>  
  
 <span data-ttu-id="9d72e-111">**/U** *login_id*</span><span class="sxs-lookup"><span data-stu-id="9d72e-111">**/U** *login_id*</span></span>  
 <span data-ttu-id="9d72e-112">Die Benutzeranmelde-ID für die [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="9d72e-112">Is the user login ID for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="9d72e-113">Bei Anmelde-IDs wird die Groß- und Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="9d72e-113">Login IDs are case sensitive.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssNoteWinAuthentication](../includes/ssnotewinauthentication-md.md)]<span data-ttu-id="9d72e-114">.</span><span class="sxs-lookup"><span data-stu-id="9d72e-114">.</span></span>  
  
 <span data-ttu-id="9d72e-115">**/P** *password*</span><span class="sxs-lookup"><span data-stu-id="9d72e-115">**/P** *password*</span></span>  
 <span data-ttu-id="9d72e-116">Gibt ein benutzerdefiniertes Kennwort für die [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Authentifizierung an.</span><span class="sxs-lookup"><span data-stu-id="9d72e-116">Specifies a user-specified password for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="9d72e-117">**/E**</span><span class="sxs-lookup"><span data-stu-id="9d72e-117">**/E**</span></span>  
 <span data-ttu-id="9d72e-118">Gibt an, dass die Verbindung mithilfe der Windows-Authentifizierung erfolgt und die Anmeldeinformationen des aktuellen Benutzers verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9d72e-118">Specifies connecting with Windows Authentication with the current user's credentials.</span></span>  
  
 <span data-ttu-id="9d72e-119">**/S** *sql_server_name*</span><span class="sxs-lookup"><span data-stu-id="9d72e-119">**/S**  *sql_server_name*</span></span>  
 <span data-ttu-id="9d72e-120">Gibt eine [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]-Instanz an.</span><span class="sxs-lookup"><span data-stu-id="9d72e-120">Specifies an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="9d72e-121">Profiler stellt automatisch eine Verbindung mit dem angegebenen Server her und verwendet dabei die Authentifizierungsinformationen, die mit den Schaltern **/U** und **/P** oder mit dem Schalter **/E** angegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="9d72e-121">Profiler will automatically connect to the specified server using the authentication information specified in the **/U** and **/P** switches or the **/E** switch.</span></span> <span data-ttu-id="9d72e-122">Verwenden Sie **/S** *sql_server_name*\\*instance_name*, um eine Verbindung mit einer benannten [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]-Instanz herzustellen.</span><span class="sxs-lookup"><span data-stu-id="9d72e-122">To connect to a named instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], use **/S** *sql_server_name*\\*instance_name*.</span></span>  
  
 <span data-ttu-id="9d72e-123">**/A** *analysis_services_server_name*</span><span class="sxs-lookup"><span data-stu-id="9d72e-123">**/A**  *analysis_services_server_name*</span></span>  
 <span data-ttu-id="9d72e-124">Gibt eine Analysis Services-Instanz an.</span><span class="sxs-lookup"><span data-stu-id="9d72e-124">Specifies an instance of Analysis Services.</span></span> <span data-ttu-id="9d72e-125">Profiler stellt automatisch eine Verbindung mit dem angegebenen Server her und verwendet dabei die Authentifizierungsinformationen, die mit den Schaltern **/U** und **/P** oder mit dem Schalter **/E** angegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="9d72e-125">Profiler will automatically connect to the specified server using the authentication information specified in the **/U** and **/P** switches or the **/E** switch.</span></span> <span data-ttu-id="9d72e-126">Verwenden Sie **/A** *analysis_services_server_name\instance_name*, um eine Verbindung mit einer benannten [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]-Instanz herzustellen.</span><span class="sxs-lookup"><span data-stu-id="9d72e-126">To connect to a named instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] use **/A** *analysis_services_server_name\instance_name*.</span></span>  
  
 <span data-ttu-id="9d72e-127">**/D** *database*</span><span class="sxs-lookup"><span data-stu-id="9d72e-127">**/D** *database*</span></span>  
 <span data-ttu-id="9d72e-128">Gibt den Namen der Datenbank an, die zusammen mit dieser Verbindung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="9d72e-128">Specifies the name of the database to be used with the connection.</span></span> <span data-ttu-id="9d72e-129">Mit dieser Option wird die Standarddatenbank für den angegebenen Benutzer ausgewählt, wenn keine Datenbank angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="9d72e-129">This option will select the default database for the specified user if no database is specified.</span></span>  
  
 <span data-ttu-id="9d72e-130">**/B "** *trace_table_name* **"**</span><span class="sxs-lookup"><span data-stu-id="9d72e-130">**/B "** *trace_table_name* **"**</span></span>  
 <span data-ttu-id="9d72e-131">Gibt eine Ablaufverfolgungstabelle an, die beim Starten von Profiler geladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="9d72e-131">Specifies a trace table to load when the profiler is launched.</span></span> <span data-ttu-id="9d72e-132">Sie müssen die Datenbank, den Benutzer oder das Schema und die Tabelle angeben.</span><span class="sxs-lookup"><span data-stu-id="9d72e-132">You must specify the database, the user or schema, and the table.</span></span>  
  
 <span data-ttu-id="9d72e-133">**/T"** *template_name* **"**</span><span class="sxs-lookup"><span data-stu-id="9d72e-133">**/T"** *template_name* **"**</span></span>  
 <span data-ttu-id="9d72e-134">Gibt die Vorlage an, die geladen wird, um die Ablaufverfolgung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="9d72e-134">Specifies the template that will be loaded to configure the trace.</span></span> <span data-ttu-id="9d72e-135">Der Vorlagenname muss in Anführungszeichen eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="9d72e-135">The template name must be in quotes.</span></span> <span data-ttu-id="9d72e-136">Die Vorlage muss sich entweder im Systemverzeichnis für Vorlagen oder im Benutzerverzeichnis für Vorlagen befinden.</span><span class="sxs-lookup"><span data-stu-id="9d72e-136">The template name must be in either the system template directory or the user template directory.</span></span> <span data-ttu-id="9d72e-137">Wenn sich in beiden Verzeichnissen eine Vorlage mit diesem Namen befindet, wird die Vorlage aus dem Systemverzeichnis geladen.</span><span class="sxs-lookup"><span data-stu-id="9d72e-137">If two templates with the same name exist in both directories, the template from the system directory will be loaded.</span></span> <span data-ttu-id="9d72e-138">Wenn die Verzeichnisse keine Vorlage mit dem angegebenen Namen enthalten, wird die Standardvorlage geladen.</span><span class="sxs-lookup"><span data-stu-id="9d72e-138">If no template with the specified name exists, the standard template will be loaded.</span></span> <span data-ttu-id="9d72e-139">Beachten Sie, dass die Dateierweiterung für die Vorlage (TDF) nicht als Teil des *Vorlagennamens*angegeben werden darf.</span><span class="sxs-lookup"><span data-stu-id="9d72e-139">Note that the file extension for the template (.tdf) should not be specified as part of the *template_name*.</span></span> <span data-ttu-id="9d72e-140">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9d72e-140">For example:</span></span>  
  
```  
/T "standard"  
```  
  
 <span data-ttu-id="9d72e-141">**/F"** *filename* **"**</span><span class="sxs-lookup"><span data-stu-id="9d72e-141">**/F"** *filename* **"**</span></span>  
 <span data-ttu-id="9d72e-142">Gibt den Pfad und den Dateinamen einer Ablaufverfolgungsdatei an, die beim Starten von Profiler geladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="9d72e-142">Specifies the path and filename of a trace file to load when profiler is launched.</span></span> <span data-ttu-id="9d72e-143">Der Pfad und der Dateiname müssen in Anführungszeichen eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="9d72e-143">The entire path and filename must be in quotes.</span></span> <span data-ttu-id="9d72e-144">Diese Option kann nicht zusammen mit **/O**verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9d72e-144">This option cannot be used with **/O**.</span></span>  
  
 <span data-ttu-id="9d72e-145">**/O "** *filename* **"**</span><span class="sxs-lookup"><span data-stu-id="9d72e-145">**/O "** *filename*  **"**</span></span>  
 <span data-ttu-id="9d72e-146">Gibt den Pfad und den Dateinamen einer Datei an, in der die Ergebnisse der Ablaufverfolgung erfasst werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9d72e-146">Specifies the path and filename of a file to which trace results should be written.</span></span> <span data-ttu-id="9d72e-147">Der Pfad und der Dateiname müssen in Anführungszeichen eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="9d72e-147">The entire path and filename must be in quotes.</span></span> <span data-ttu-id="9d72e-148">Diese Option kann nicht zusammen mit **/F**verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9d72e-148">This option cannot be used with **/F.**</span></span>  
  
 <span data-ttu-id="9d72e-149">**/L** *locale_ID*</span><span class="sxs-lookup"><span data-stu-id="9d72e-149">**/L** *locale_ID*</span></span>  
 <span data-ttu-id="9d72e-150">Nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9d72e-150">Not available.</span></span>  
  
 <span data-ttu-id="9d72e-151">**/M "** *MM-DD-YY hh:mm:ss* **"**</span><span class="sxs-lookup"><span data-stu-id="9d72e-151">**/M "** *MM-DD-YY hh:mm:ss* **"**</span></span>  
 <span data-ttu-id="9d72e-152">Gibt das Datum und die Uhrzeit für die Beendigung der Ablaufverfolgung an.</span><span class="sxs-lookup"><span data-stu-id="9d72e-152">Specifies the date and time for the trace to stop.</span></span> <span data-ttu-id="9d72e-153">Der Beendigungszeitpunkt muss in Anführungszeichen eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="9d72e-153">The stop time must be in quotes.</span></span> <span data-ttu-id="9d72e-154">Geben Sie den Beendigungszeitpunkt gemäß den Parametern in der folgenden Tabelle an:</span><span class="sxs-lookup"><span data-stu-id="9d72e-154">Specify the stop time according to the parameters in the table below:</span></span>  
  
|<span data-ttu-id="9d72e-155">Parameter</span><span class="sxs-lookup"><span data-stu-id="9d72e-155">Parameter</span></span>|<span data-ttu-id="9d72e-156">Definition</span><span class="sxs-lookup"><span data-stu-id="9d72e-156">Definition</span></span>|  
|---------------|----------------|  
|<span data-ttu-id="9d72e-157">MM</span><span class="sxs-lookup"><span data-stu-id="9d72e-157">MM</span></span>|<span data-ttu-id="9d72e-158">Zweistellige Angabe des Monats</span><span class="sxs-lookup"><span data-stu-id="9d72e-158">Two-digit month</span></span>|  
|<span data-ttu-id="9d72e-159">DD</span><span class="sxs-lookup"><span data-stu-id="9d72e-159">DD</span></span>|<span data-ttu-id="9d72e-160">Zweistellige Angabe des Tages</span><span class="sxs-lookup"><span data-stu-id="9d72e-160">Two-digit day</span></span>|  
|<span data-ttu-id="9d72e-161">YY</span><span class="sxs-lookup"><span data-stu-id="9d72e-161">YY</span></span>|<span data-ttu-id="9d72e-162">Zweistellige Angabe des Jahres</span><span class="sxs-lookup"><span data-stu-id="9d72e-162">Two-digit year</span></span>|  
|<span data-ttu-id="9d72e-163">hh</span><span class="sxs-lookup"><span data-stu-id="9d72e-163">hh</span></span>|<span data-ttu-id="9d72e-164">Zweistellige Angabe der Stunde im 24-Stundenformat</span><span class="sxs-lookup"><span data-stu-id="9d72e-164">Two-digit hour on a 24-hour clock</span></span>|  
|<span data-ttu-id="9d72e-165">MM</span><span class="sxs-lookup"><span data-stu-id="9d72e-165">mm</span></span>|<span data-ttu-id="9d72e-166">Zweistellige Angabe der Minuten</span><span class="sxs-lookup"><span data-stu-id="9d72e-166">Two-digit minute</span></span>|  
|<span data-ttu-id="9d72e-167">ss</span><span class="sxs-lookup"><span data-stu-id="9d72e-167">ss</span></span>|<span data-ttu-id="9d72e-168">Zweistellige Angabe der Sekunden</span><span class="sxs-lookup"><span data-stu-id="9d72e-168">Two-digit second</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="9d72e-169">Das Format „MM-DD-YY hh:mm:ss“ kann nur verwendet werden, wenn die Option **Einstellungen für Land/Region zum Anzeigen von Datums- und Uhrzeitwerten** verwenden in [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)]aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="9d72e-169">The "MM-DD-YY hh:mm:ss" format can only be used if the **Use regional settings to display date and time values** option is enabled in [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="9d72e-170">Wenn diese Option nicht aktiviert ist, müssen Sie das Format "YYYY-MM-DD-hh:mm:ss" für Datum und Uhrzeit verwenden.</span><span class="sxs-lookup"><span data-stu-id="9d72e-170">If this option is not enabled, you must use the "YYYY-MM-DD hh:mm:ss" date and time format.</span></span>  
  
 <span data-ttu-id="9d72e-171">**/R**</span><span class="sxs-lookup"><span data-stu-id="9d72e-171">**/R**</span></span>  
 <span data-ttu-id="9d72e-172">Aktiviert das Rollover für Ablaufverfolgungsdateien.</span><span class="sxs-lookup"><span data-stu-id="9d72e-172">Enables trace file rollover.</span></span>  
  
 <span data-ttu-id="9d72e-173">**/Z** *file_size*</span><span class="sxs-lookup"><span data-stu-id="9d72e-173">**/Z**  *file_size*</span></span>  
 <span data-ttu-id="9d72e-174">Gibt die Größe der Ablaufverfolgungsdatei in Megabytes (MB) an.</span><span class="sxs-lookup"><span data-stu-id="9d72e-174">Specifies the size of the trace file in megabytes (MB).</span></span> <span data-ttu-id="9d72e-175">Die Standardgröße ist 5 MB.</span><span class="sxs-lookup"><span data-stu-id="9d72e-175">The default size is 5 MB.</span></span> <span data-ttu-id="9d72e-176">Wenn das Rollover aktiviert ist, wird die Größe aller Rolloverdateien auf den in diesem Argument angegebenen Wert begrenzt.</span><span class="sxs-lookup"><span data-stu-id="9d72e-176">If rollover is enabled, all rollover files will be limited to the value specified in this argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9d72e-177">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="9d72e-177">Remarks</span></span>  
 <span data-ttu-id="9d72e-178">Verwenden Sie die Option **/S** zusammen mit der Option **/T** , um eine Ablaufverfolgung mit einer bestimmten Vorlage zu starten.</span><span class="sxs-lookup"><span data-stu-id="9d72e-178">To start a trace with a specific template, use the **/S** and **/T** options together.</span></span> <span data-ttu-id="9d72e-179">Wenn Sie beispielsweise eine Ablaufverfolgung mithilfe der Standardvorlage im Verzeichnis MyServer\MyInstance starten möchten, geben Sie an der Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="9d72e-179">For example, to start a trace using the Standard template on MyServer\MyInstance, enter the following at the command prompt:</span></span>  
  
```  
profiler /S MyServer\MyInstance /T "Standard"  
```  
  
## <a name="see-also"></a><span data-ttu-id="9d72e-180">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9d72e-180">See Also</span></span>  
 [<span data-ttu-id="9d72e-181">Referenz zum Eingabeaufforderungs-Hilfsprogramm &#40;Datenbank-Engine&#41;</span><span class="sxs-lookup"><span data-stu-id="9d72e-181">Command Prompt Utility Reference &#40;Database Engine&#41;</span></span>](command-prompt-utility-reference-database-engine.md)  
  
  
