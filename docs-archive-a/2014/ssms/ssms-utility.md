---
title: Ssms-Hilfsprogramm | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Management Studio [SQL Server], opening
- command prompt utilities [SQL Server], sqlwb
- sqlwb utility
- Management Studio command line
- opening SQL Server Management Studio
ms.assetid: aafda520-9e2a-4e1e-b936-1b165f1684e8
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0cfc9469e49e6ce3839d02a61477b8957fbc13e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621812"
---
# <a name="ssms-utility"></a><span data-ttu-id="6e24a-102">Ssms-Hilfsprogramm</span><span class="sxs-lookup"><span data-stu-id="6e24a-102">Ssms Utility</span></span>
  <span data-ttu-id="6e24a-103">Mit dem **Ssms**-Hilfsprogramm wird [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]geöffnet.</span><span class="sxs-lookup"><span data-stu-id="6e24a-103">The **Ssms**utility opens [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="6e24a-104">Bei entsprechender Angabe stellt **Ssms** zudem eine Verbindung mit einem Server her und öffnet Abfragen, Skripts, Dateien, Projekte und Lösungen.</span><span class="sxs-lookup"><span data-stu-id="6e24a-104">If specified, **Ssms** also establishes a connection to a server, and opens queries, scripts, files, projects, and solutions.</span></span>  
  
 <span data-ttu-id="6e24a-105">Sie können Dateien angeben, die Abfragen, Projekte oder Lösungen enthalten.</span><span class="sxs-lookup"><span data-stu-id="6e24a-105">You can specify files that contain queries, projects, or solutions.</span></span> <span data-ttu-id="6e24a-106">Für Dateien, die Abfragen enthalten, wird automatisch eine Verbindung mit einem Server hergestellt, wenn Verbindungsinformationen bereitgestellt werden und der Dateityp diesem Servertyp zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="6e24a-106">Files that contain queries are automatically connected to a server if connection information is provided and the file type is associated with that type of server.</span></span> <span data-ttu-id="6e24a-107">So wird z. B. für SQL-Dateien ein SQL-Abfrage-Editorfenster in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]und für MDX-Dateien ein MDX-Abfrage-Editorfenster in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]geöffnet.</span><span class="sxs-lookup"><span data-stu-id="6e24a-107">For instance, .sql files will open a SQL Query Editor window in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], and .mdx files will open an MDX Query Editor window in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="6e24a-108">**SQL Server-Lösungen und -Projekte** werden in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]geöffnet.</span><span class="sxs-lookup"><span data-stu-id="6e24a-108">**SQL Server Solutions and Projects** will open in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6e24a-109">Das Hilfsprogramm **Ssms** führt keine Abfragen aus.</span><span class="sxs-lookup"><span data-stu-id="6e24a-109">The **Ssms** utility does not run queries.</span></span> <span data-ttu-id="6e24a-110">Zum Ausführen von Abfragen in der Befehlszeile verwenden Sie das **sqlcmd** -Hilfsprogramm.</span><span class="sxs-lookup"><span data-stu-id="6e24a-110">To run queries from the command line, use the **sqlcmd** utility.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e24a-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="6e24a-111">Syntax</span></span>  
  
```  
  
      Ssms  
    [scriptfile] [projectfile] [solutionfile]  
    [-Sservername] [-ddatabasename] [-Uusername] [-Ppassword]   
    [-E] [-nosplash] [-log[filename]?] [-?]  
```  
  
## <a name="arguments"></a><span data-ttu-id="6e24a-112">Argumente</span><span class="sxs-lookup"><span data-stu-id="6e24a-112">Arguments</span></span>  
 <span data-ttu-id="6e24a-113">*scriptfile*</span><span class="sxs-lookup"><span data-stu-id="6e24a-113">*scriptfile*</span></span>  
 <span data-ttu-id="6e24a-114">Gibt eine oder mehrere zu öffnende Skriptdateien an.</span><span class="sxs-lookup"><span data-stu-id="6e24a-114">Specifies one or more script files to open.</span></span> <span data-ttu-id="6e24a-115">Der Parameter muss den vollständigen Pfad zu den Dateien enthalten.</span><span class="sxs-lookup"><span data-stu-id="6e24a-115">The parameter must contain the full path to the files.</span></span>  
  
 <span data-ttu-id="6e24a-116">*projectfile*</span><span class="sxs-lookup"><span data-stu-id="6e24a-116">*projectfile*</span></span>  
 <span data-ttu-id="6e24a-117">Gibt ein zu öffnendes Skriptprojekt an.</span><span class="sxs-lookup"><span data-stu-id="6e24a-117">Specifies a script project to open.</span></span> <span data-ttu-id="6e24a-118">Der Parameter muss den vollständigen Pfad zur Skriptprojektdatei enthalten.</span><span class="sxs-lookup"><span data-stu-id="6e24a-118">The parameter must contain the full path to the script project file.</span></span>  
  
 <span data-ttu-id="6e24a-119">*solutionfile*</span><span class="sxs-lookup"><span data-stu-id="6e24a-119">*solutionfile*</span></span>  
 <span data-ttu-id="6e24a-120">Gibt eine zu öffnende Lösung an.</span><span class="sxs-lookup"><span data-stu-id="6e24a-120">Specifies a solution to open.</span></span> <span data-ttu-id="6e24a-121">Der Parameter muss den vollständigen Pfad zur Lösungsdatei enthalten.</span><span class="sxs-lookup"><span data-stu-id="6e24a-121">The parameter must contain the full path to the solution file.</span></span>  
  
 <span data-ttu-id="6e24a-122">[**-S** _Servername_]</span><span class="sxs-lookup"><span data-stu-id="6e24a-122">[**-S** _servername_]</span></span>  
 <span data-ttu-id="6e24a-123">Servername</span><span class="sxs-lookup"><span data-stu-id="6e24a-123">Server name</span></span>  
  
 <span data-ttu-id="6e24a-124">[**-d** _DatabaseName_]</span><span class="sxs-lookup"><span data-stu-id="6e24a-124">[**-d** _databasename_]</span></span>  
 <span data-ttu-id="6e24a-125">Datenbankname</span><span class="sxs-lookup"><span data-stu-id="6e24a-125">Database name</span></span>  
  
 <span data-ttu-id="6e24a-126">[**-U** _username_]</span><span class="sxs-lookup"><span data-stu-id="6e24a-126">[**-U** _username_]</span></span>  
 <span data-ttu-id="6e24a-127">Benutzername, wenn die Verbindung mithilfe der [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Authentifizierung hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="6e24a-127">User name when connecting with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication</span></span>  
  
 <span data-ttu-id="6e24a-128">[**-P** _Kennwort_]</span><span class="sxs-lookup"><span data-stu-id="6e24a-128">[**-P** _password_]</span></span>  
 <span data-ttu-id="6e24a-129">Kennwort, wenn die Verbindung mithilfe der [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Authentifizierung hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="6e24a-129">Password when connecting with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication</span></span>  
  
 <span data-ttu-id="6e24a-130">[**-E**]</span><span class="sxs-lookup"><span data-stu-id="6e24a-130">[**-E**]</span></span>  
 <span data-ttu-id="6e24a-131">Verbindung mithilfe der Windows-Authentifizierung herstellen</span><span class="sxs-lookup"><span data-stu-id="6e24a-131">Connect using Windows Authentication</span></span>  
  
 <span data-ttu-id="6e24a-132">[**-nosplash**]</span><span class="sxs-lookup"><span data-stu-id="6e24a-132">[**-nosplash**]</span></span>  
 <span data-ttu-id="6e24a-133">Verhindert, dass [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] beim Öffnen den Begrüßungsbildschirm anzeigt.</span><span class="sxs-lookup"><span data-stu-id="6e24a-133">Prevents [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] from displaying the splash screen graphic while opening.</span></span> <span data-ttu-id="6e24a-134">Verwenden Sie diese Option, wenn Sie eine Verbindung zum Computer mit [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] herstellen und hierfür Terminaldienste über eine Verbindung mit begrenzter Bandbreite einsetzen.</span><span class="sxs-lookup"><span data-stu-id="6e24a-134">Use this option when connecting to the computer running [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] by means of Terminal Services over a connection with a limited bandwidth.</span></span> <span data-ttu-id="6e24a-135">Bei diesem Argument wird die Groß- und Kleinschreibung nicht beachtet. Es kann vor oder nach anderen Argumenten angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="6e24a-135">This argument is not case-sensitive and may appear before or after other arguments</span></span>  
  
 <span data-ttu-id="6e24a-136">[**-Log**_[fileName]?_]</span><span class="sxs-lookup"><span data-stu-id="6e24a-136">[**-log**_[filename]?_]</span></span>  
 <span data-ttu-id="6e24a-137">Protokolliert die [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] -Aktivität zur Problembehandlung in der angegebenen Datei.</span><span class="sxs-lookup"><span data-stu-id="6e24a-137">Logs [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] activity to the specified file for troubleshooting</span></span>  
  
 <span data-ttu-id="6e24a-138">[**-?**]</span><span class="sxs-lookup"><span data-stu-id="6e24a-138">[**-?**]</span></span>  
 <span data-ttu-id="6e24a-139">Zeigt die Hilfe zur Befehlszeile an.</span><span class="sxs-lookup"><span data-stu-id="6e24a-139">Displays command line help</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6e24a-140">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="6e24a-140">Remarks</span></span>  
 <span data-ttu-id="6e24a-141">Alle Schalter sind optional und werden durch Leerzeichen voneinander getrennt. Eine Ausnahme hiervon bilden Dateien, die durch Kommas getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="6e24a-141">All of the switches are optional and separated by a space except files which are separated by commas.</span></span> <span data-ttu-id="6e24a-142">Wenn Sie keine Schalter angeben, wird **Ssms** Ssms [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] so geöffnet, wie es in den Einstellungen unter **Optionen** im Menü **Extras** angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="6e24a-142">If you do not specify any switches, **Ssms** opens [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] as specified in the **Options** settings on the **Tools** menu.</span></span> <span data-ttu-id="6e24a-143">Wenn z.B. auf der Seite **Umgebung/Allgemein** unter **Beim Start** die Option **Neues Abfragefenster öffnen**angegeben ist, öffnet **Ssms** ein leeres Abfrage-Editor-Fenster.</span><span class="sxs-lookup"><span data-stu-id="6e24a-143">For example, if the **Environment/General** page **At startup** option specifies **Open new query window**, **Ssms** will open with a blank Query Editor.</span></span>  
  
 <span data-ttu-id="6e24a-144">Der Schalter **-Log** muss am Ende der Befehlszeile nach allen anderen Schaltern angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="6e24a-144">The **-log** switch must appear at the end of the command line, after all other switches.</span></span> <span data-ttu-id="6e24a-145">Das filename-Argument ist optional.</span><span class="sxs-lookup"><span data-stu-id="6e24a-145">The filename argument is optional.</span></span> <span data-ttu-id="6e24a-146">Wenn ein Dateiname angegeben wird und die Datei nicht vorhanden ist, wird sie erstellt.</span><span class="sxs-lookup"><span data-stu-id="6e24a-146">If a filename is specified, and the file does not exist, the file is created.</span></span> <span data-ttu-id="6e24a-147">Wenn die Datei beispielsweise aufgrund unzureichender Schreibberechtigungen nicht erstellt werden kann, wird die Datei stattdessen in den Ordner für nicht lokalisierte Anwendungsdaten (APPDATA) geschrieben (siehe unten).</span><span class="sxs-lookup"><span data-stu-id="6e24a-147">If the file cannot be created - for example, due to insufficient write access, the log is written to the nonlocalized APPDATA location instead (See below).</span></span> <span data-ttu-id="6e24a-148">Wenn das filename-Argument nicht angegeben wird, werden zwei Dateien in den Ordner für nicht lokalisierte Anwendungsdaten des aktuellen Benutzers geschrieben.</span><span class="sxs-lookup"><span data-stu-id="6e24a-148">If the filename argument is not specified, two files are written to the current user's nonlocalized application data folder.</span></span> <span data-ttu-id="6e24a-149">Der Ordner für nicht lokalisierte Anwendungsdaten in SQL Server kann anhand der APPDATA-Umgebungsvariablen ermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="6e24a-149">The nonlocalized application data folder for SQL Server can be found from the APPDATA environment variable.</span></span> <span data-ttu-id="6e24a-150">Für SQL Server 2012 lautet der Ordner z \<system drive> . b.: \Users \\<username \> \appdata\roaming\microsoft\appenv\10.0 \\ .</span><span class="sxs-lookup"><span data-stu-id="6e24a-150">For example, for SQL Server 2012, the folder is \<system drive>:\Users\\<username\>\AppData\Roaming\Microsoft\AppEnv\10.0\\.</span></span> <span data-ttu-id="6e24a-151">Die beiden Dateien erhalten standardmäßig den Namen ActivityLog.xml und ActivityLog.xsl.</span><span class="sxs-lookup"><span data-stu-id="6e24a-151">The two files are, by default, named ActivityLog.xml and ActivityLog.xsl.</span></span> <span data-ttu-id="6e24a-152">Die erste Datei enthält die Aktivitätsprotokolldaten, und die zweite Datei ist ein XML-Stylesheet, mit dem die XML-Datei auf bequeme Weise angezeigt werden kann.</span><span class="sxs-lookup"><span data-stu-id="6e24a-152">The former contains the activity log data and the latter is an XML style sheet which provides a more convenient way to view the XML file.</span></span> <span data-ttu-id="6e24a-153">Führen Sie die folgenden Schritte aus, um die Protokolldatei in Ihrem XML-Standard Viewer anzuzeigen, wie z. b. Internet Explorer: Klicken Sie auf Start und dann auf ausführen..., und geben Sie dann " \<system drive> : \Users \\<username \>\AppData\Roaming\Microsoft\AppEnv\10.0\ActivityLog.xml" in das angegebene Feld ein. Drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="6e24a-153">Use the following steps to view the log file in your default XML viewer, like Internet Explorer:  Click Start, then click Run...", then type "\<system drive>:\Users\\<username\>\AppData\Roaming\Microsoft\AppEnv\10.0\ActivityLog.xml" into the field provided, and then press Enter.</span></span>  
  
 <span data-ttu-id="6e24a-154">Dateien, die Abfragen enthalten, fordern eine Verbindung mit einem Server an, wenn Verbindungsinformationen bereitgestellt werden und der Dateityp diesem Servertyp zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="6e24a-154">Files that contain queries will prompt to be connected to a server if connection information is provided and the file type is associated with that type of server.</span></span> <span data-ttu-id="6e24a-155">So wird z. B. für SQL-Dateien ein SQL-Abfrage-Editorfenster in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]und für MDX-Dateien ein MDX-Abfrage-Editorfenster in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]geöffnet.</span><span class="sxs-lookup"><span data-stu-id="6e24a-155">For instance, .sql files will open a SQL Query Editor window in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], and .mdx files will open an MDX Query Editor window in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="6e24a-156">**SQL Server-Lösungen und -Projekte** werden in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]geöffnet.</span><span class="sxs-lookup"><span data-stu-id="6e24a-156">**SQL Server Solutions and Projects** will open in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="6e24a-157">In der folgenden Tabelle werden Servertypen zu Dateierweiterungen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="6e24a-157">The following table maps server types to file extensions.</span></span>  
  
|<span data-ttu-id="6e24a-158">Servertyp</span><span class="sxs-lookup"><span data-stu-id="6e24a-158">Server type</span></span>|<span data-ttu-id="6e24a-159">Durchwahl</span><span class="sxs-lookup"><span data-stu-id="6e24a-159">Extension</span></span>|  
|-----------------|---------------|  
|[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]|<span data-ttu-id="6e24a-160">SQL</span><span class="sxs-lookup"><span data-stu-id="6e24a-160">.sql</span></span>|  
|<span data-ttu-id="6e24a-161">SQL Server Analysis Services</span><span class="sxs-lookup"><span data-stu-id="6e24a-161">SQL Server Analysis Services</span></span>|<span data-ttu-id="6e24a-162">MDX</span><span class="sxs-lookup"><span data-stu-id="6e24a-162">.mdx</span></span><br /><br /> <span data-ttu-id="6e24a-163">XMLA</span><span class="sxs-lookup"><span data-stu-id="6e24a-163">.xmla</span></span>|  
  
## <a name="examples"></a><span data-ttu-id="6e24a-164">Beispiele</span><span class="sxs-lookup"><span data-stu-id="6e24a-164">Examples</span></span>  
 <span data-ttu-id="6e24a-165">Mit dem folgenden Skript wird [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] mit den Standardeinstellungen von der Eingabeaufforderung aus geöffnet.</span><span class="sxs-lookup"><span data-stu-id="6e24a-165">The following script opens [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] from a command prompt with the default settings:</span></span>  
  
```  
Ssms  
  
```  
  
 <span data-ttu-id="6e24a-166">Mit dem folgenden Skript wird [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] von der Eingabeaufforderung aus geöffnet. Es wird die Windows-Authentifizierung verwendet, im Code-Editor wird der Server `ACCTG and the database AdventureWorks2012,` ausgewählt, und der Begrüßungsbildschirm wird nicht angezeigt:</span><span class="sxs-lookup"><span data-stu-id="6e24a-166">The following script opens [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] from a command prompt, with Windows Authentication, with the Code Editor set to the server `ACCTG and the database AdventureWorks2012,` without showing the splash screen:</span></span>  
  
```  
Ssms -E -S ACCTG -d AdventureWorks2012 -nosplash  
  
```  
  
 <span data-ttu-id="6e24a-167">Mit dem folgenden Skript wird [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] von der Eingabeaufforderung aus geöffnet. Anschließend wird das Skript MonthEndQuery geöffnet.</span><span class="sxs-lookup"><span data-stu-id="6e24a-167">The following script opens [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] from a command prompt, and opens the MonthEndQuery script.</span></span>  
  
```  
Ssms "C:\Documents and Settings\username\My Documents\SQL Server Management Studio Projects\FinanceScripts\FinanceScripts\MonthEndQuery.sql"  
  
```  
  
 <span data-ttu-id="6e24a-168">Mit dem folgenden Skript wird [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] von der Eingabeaufforderung aus geöffnet. Anschließend wird das Projekt NewReportsProject auf dem Computer `developer`geöffnet:</span><span class="sxs-lookup"><span data-stu-id="6e24a-168">The following script opens [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] from a command prompt, and opens the NewReportsProject project on the computer named `developer`:</span></span>  
  
```  
Ssms "\\developer\fin\ReportProj\ReportProj\NewReportProj.ssmssqlproj"  
  
```  
  
 <span data-ttu-id="6e24a-169">Mit dem folgenden Skript wird [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] von der Eingabeaufforderung aus geöffnet. Anschließend wird die Lösung MonthlyReports geöffnet:</span><span class="sxs-lookup"><span data-stu-id="6e24a-169">The following script opens [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] from a command prompt, and opens the MonthlyReports solution:</span></span>  
  
```  
Ssms "C:\solutionsfolder\ReportProj\MonthlyReports.ssmssln"  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="6e24a-170">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6e24a-170">See Also</span></span>  
 [<span data-ttu-id="6e24a-171">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6e24a-171">Use SQL Server Management Studio</span></span>](../database-engine/use-sql-server-management-studio.md)  
  
  
