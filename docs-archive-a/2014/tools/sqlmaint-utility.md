---
title: sqlmaint (Hilfsprogramm) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- database maintenance plans [SQL Server]
- sqlmaint utility
- maintaining databases [SQL Server]
- backups [SQL Server], sqlmaint utility
- command prompt utilities [SQL Server], sqlmaint
- maintenance plans [SQL Server], command prompt
- backing up [SQL Server], sqlmaint utility
ms.assetid: 937a9932-4aed-464b-b97a-a5acfe6a50de
author: stevestein
ms.author: sstein
ms.openlocfilehash: 80e60b75305ee91e8b62a201d9c86af301326789
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694894"
---
# <a name="sqlmaint-utility"></a><span data-ttu-id="2f87a-102">sqlmaint (Hilfsprogramm)</span><span class="sxs-lookup"><span data-stu-id="2f87a-102">sqlmaint Utility</span></span>
  <span data-ttu-id="2f87a-103">Das**sqlmaint** -Hilfsprogramm führt eine Reihe angegebener Wartungsvorgänge für eine oder mehrere Datenbanken aus.</span><span class="sxs-lookup"><span data-stu-id="2f87a-103">The**sqlmaint** utility performs a specified set of maintenance operations on one or more databases.</span></span> <span data-ttu-id="2f87a-104">Verwenden Sie **sqlmaint** , um DBCC-Überprüfungen auszuführen, eine Datenbank und das zugehörige Transaktionsprotokoll zu sichern, Statistiken zu aktualisieren und Indizes neu zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2f87a-104">Use **sqlmaint** to run DBCC checks, back up a database and its transaction log, update statistics, and rebuild indexes.</span></span> <span data-ttu-id="2f87a-105">Bei allen Datenbankwartungsaktivitäten wird ein Bericht generiert, der an eine festgelegte Textdatei, HTML-Datei oder ein festgelegtes E-Mail-Konto gesendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="2f87a-105">All database maintenance activities generate a report that can be sent to a designated text file, HTML file, or e-mail account.</span></span> <span data-ttu-id="2f87a-106">**sqlmaint** führt Datenbankwartungspläne aus, die in früheren Versionen von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="2f87a-106">**sqlmaint** executes database maintenance plans created with previous versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="2f87a-107">Verwenden Sie das Hilfsprogramm [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] dtexec [, um Wartungspläne von](../integration-services/packages/dtexec-utility.md)über die Eingabeaufforderung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="2f87a-107">To run [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] maintenance plans from the command prompt, use the [dtexec Utility](../integration-services/packages/dtexec-utility.md).</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepNextAvoid](../includes/ssnotedepnextavoid-md.md)] <span data-ttu-id="2f87a-108">Verwenden Sie stattdessen die Wartungsplanfunktion von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2f87a-108">Use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] maintenance plan feature instead.</span></span> <span data-ttu-id="2f87a-109">Weitere Informationen zu Wartungsplänen finden Sie unter [Wartungspläne](../relational-databases/maintenance-plans/maintenance-plans.md).</span><span class="sxs-lookup"><span data-stu-id="2f87a-109">For more information on maintenance plans, see [Maintenance Plans](../relational-databases/maintenance-plans/maintenance-plans.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f87a-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="2f87a-110">Syntax</span></span>  
  
```  
  
      sqlmaint   
[-?] |  
[  
     [-Sserver_name[\instance_name]]  
     [-Ulogin_ID [-Ppassword]]  
     {  
          [-Ddatabase_name | -PlanNamename | -PlanIDguid ]  
          [-Rpttext_file]  
          [-Tooperator_name]  
          [-HtmlRpthtml_file [-DelHtmlRpt <time_period>] ]  
          [-RmUnusedSpacethreshold_percentfree_percent]  
          [-CkDB | -CkDBNoIdx]  
          [-CkAl | -CkAlNoIdx]  
          [-CkCat]  
          [-UpdOptiStatssample_percent]  
          [-RebldIdxfree_space]  
          [-SupportComputedColumn]  
          [-WriteHistory]  
          [  
               {-BkUpDB [backup_path] | -BkUpLog [backup_path] }  
               {-BkUpMedia  
                    {DISK [  
                           [-DelBkUps<time_period>]   
                           [-CrBkSubDir ]   
                           [-UseDefDir ]   
                          ]  
                     | TAPE   
                    }  
               }  
               [-BkUpOnlyIfClean]  
               [-VrfyBackup]  
          ]  
     }  
]  
<time_period> ::=  
number[minutes | hours | days | weeks | months]  
```  
  
## <a name="arguments"></a><span data-ttu-id="2f87a-111">Argumente</span><span class="sxs-lookup"><span data-stu-id="2f87a-111">Arguments</span></span>  
 <span data-ttu-id="2f87a-112">Die Parameter und ihre Werte müssen jeweils durch ein Leerzeichen getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="2f87a-112">The parameters and their values must be separated by a space.</span></span> <span data-ttu-id="2f87a-113">So muss beispielsweise zwischen **-S** und *Servername*ein Leerzeichen stehen.</span><span class="sxs-lookup"><span data-stu-id="2f87a-113">For example, there must be a space between **-S** and *server_name*.</span></span>  
  
 <span data-ttu-id="2f87a-114">**-?**</span><span class="sxs-lookup"><span data-stu-id="2f87a-114">**-?**</span></span>  
 <span data-ttu-id="2f87a-115">Gibt an, dass das Syntaxdiagramm für **sqlmaint** zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="2f87a-115">Specifies that the syntax diagram for **sqlmaint** be returned.</span></span> <span data-ttu-id="2f87a-116">Dieser Parameter darf nur alleine verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2f87a-116">This parameter must be used alone.</span></span>  
  
 <span data-ttu-id="2f87a-117">**-S** _server_name_[ **\\** _instance_name_]</span><span class="sxs-lookup"><span data-stu-id="2f87a-117">**-S** _server_name_[ **\\**_instance_name_]</span></span>  
 <span data-ttu-id="2f87a-118">Gibt die Zielinstanz von [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] an.</span><span class="sxs-lookup"><span data-stu-id="2f87a-118">Specifies the target instance of [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="2f87a-119">Geben Sie *server_name* an, um eine Verbindung mit der Standardinstanz von [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] auf diesem Server herzustellen.</span><span class="sxs-lookup"><span data-stu-id="2f87a-119">Specify *server_name* to connect to the default instance of [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] on that server.</span></span> <span data-ttu-id="2f87a-120">Geben Sie *server_name **_\\_** instance_name* an, um eine Verbindung mit einer benannten Instanz von [!INCLUDE[ssDE](../includes/ssde-md.md)] auf diesem Server herzustellen.</span><span class="sxs-lookup"><span data-stu-id="2f87a-120">Specify *server_name\*\*_\\_*\* instance_name\* to connect to a named instance of [!INCLUDE[ssDE](../includes/ssde-md.md)] on that server.</span></span> <span data-ttu-id="2f87a-121">Wenn kein Server angegeben wird, stellt **sqlmaint** eine Verbindung mit der Standardinstanz von [!INCLUDE[ssDE](../includes/ssde-md.md)] auf dem lokalen Computer her.</span><span class="sxs-lookup"><span data-stu-id="2f87a-121">If no server is specified, **sqlmaint** connects to the default instance of [!INCLUDE[ssDE](../includes/ssde-md.md)] on the local computer.</span></span>  
  
 <span data-ttu-id="2f87a-122">**-U** _login_ID_</span><span class="sxs-lookup"><span data-stu-id="2f87a-122">**-U** _login_ID_</span></span>  
 <span data-ttu-id="2f87a-123">Gibt die Anmelde-ID an, der beim Verbinden zum Server verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="2f87a-123">Specifies the login ID to use when connecting to the server.</span></span> <span data-ttu-id="2f87a-124">Wenn dieses Argument nicht angegeben wird, versucht **sqlmaint** , die [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows-Authentifizierung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="2f87a-124">If not supplied, **sqlmaint** attempts to use [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows Authentication.</span></span> <span data-ttu-id="2f87a-125">Wenn die *Anmelde-ID* Sonderzeichen enthält, muss das Argument in doppelte Anführungszeichen (") eingeschlossen werden. Andernfalls sind die doppelten Anführungszeichen optional.</span><span class="sxs-lookup"><span data-stu-id="2f87a-125">If *login_ID* contains special characters, it must be enclosed in double quotation marks ("); otherwise, the double quotation marks are optional.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2f87a-126">Verwenden Sie nach Möglichkeit die Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="2f87a-126">When possible, use Windows Authentication.</span></span>  
  
 <span data-ttu-id="2f87a-127">**-P** _password_</span><span class="sxs-lookup"><span data-stu-id="2f87a-127">**-P** _password_</span></span>  
 <span data-ttu-id="2f87a-128">Gibt das Kennwort für die Anmelde-ID an.</span><span class="sxs-lookup"><span data-stu-id="2f87a-128">Specifies the password for the login ID.</span></span> <span data-ttu-id="2f87a-129">Nur gültig, wenn der Parameter **-U** ebenfalls angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="2f87a-129">Only valid if the **-U** parameter is also supplied.</span></span> <span data-ttu-id="2f87a-130">Wenn das *Kennwort* Sonderzeichen enthält, muss das Argument in doppelte Anführungszeichen eingeschlossen werden. Andernfalls sind die doppelten Anführungszeichen optional.</span><span class="sxs-lookup"><span data-stu-id="2f87a-130">If *password* contains special characters, it must be enclosed in double quotation marks; otherwise, the double quotation marks are optional.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2f87a-131">Das Kennwort wird nicht maskiert.</span><span class="sxs-lookup"><span data-stu-id="2f87a-131">The password is not masked.</span></span> <span data-ttu-id="2f87a-132">Verwenden Sie nach Möglichkeit die Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="2f87a-132">When possible, use Windows Authentication.</span></span>  
  
 <span data-ttu-id="2f87a-133">**-D** _database_name_</span><span class="sxs-lookup"><span data-stu-id="2f87a-133">**-D** _database_name_</span></span>  
 <span data-ttu-id="2f87a-134">Gibt den Namen der Datenbank an, in der der Wartungsvorgang durchgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="2f87a-134">Specifies the name of the database in which to perform the maintenance operation.</span></span> <span data-ttu-id="2f87a-135">Wenn der *Datenbankname* Sonderzeichen enthält, muss das Argument in doppelte Anführungszeichen eingeschlossen werden. Andernfalls sind die doppelten Anführungszeichen optional.</span><span class="sxs-lookup"><span data-stu-id="2f87a-135">If *database_name* contains special characters, it must be enclosed in double quotation marks; otherwise, the double quotation marks are optional.</span></span>  
  
 <span data-ttu-id="2f87a-136">**-PlanName** _name_</span><span class="sxs-lookup"><span data-stu-id="2f87a-136">**-PlanName** _name_</span></span>  
 <span data-ttu-id="2f87a-137">Gibt den Namen eines Datenbank-Wartungsplans an, der mithilfe des Datenbank-Wartungsplanungs-Assistenten definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="2f87a-137">Specifies the name of a database maintenance plan defined using the Database Maintenance Plan Wizard.</span></span> <span data-ttu-id="2f87a-138">Von den Informationen, die dieser Plan enthält, verwendet **sqlmaint** nur die Liste der Datenbanken im Plan.</span><span class="sxs-lookup"><span data-stu-id="2f87a-138">The only information **sqlmaint** uses from the plan is the list of the databases in the plan.</span></span> <span data-ttu-id="2f87a-139">Alle Wartungsaktivitäten, die Sie in den anderen **sqlmaint** -Parametern angeben, werden auf die in dieser Liste aufgeführten Datenbanken angewendet.</span><span class="sxs-lookup"><span data-stu-id="2f87a-139">Any maintenance activities you specify in the other **sqlmaint** parameters are applied to this list of databases.</span></span>  
  
 <span data-ttu-id="2f87a-140">**-PlanID** _guid_</span><span class="sxs-lookup"><span data-stu-id="2f87a-140">**-PlanID** _guid_</span></span>  
 <span data-ttu-id="2f87a-141">Gibt einen global eindeutigen Bezeichner (Globally Unique Identifier, GUID) eines Datenbank-Wartungsplans an, der mithilfe des Datenbank-Wartungsplanungs-Assistenten definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="2f87a-141">Specifies the globally unique identifier (GUID) of a database maintenance plan defined using the Database Maintenance Plan Wizard.</span></span> <span data-ttu-id="2f87a-142">Von den Informationen, die dieser Plan enthält, verwendet **sqlmaint** nur die Liste der Datenbanken im Plan.</span><span class="sxs-lookup"><span data-stu-id="2f87a-142">The only information **sqlmaint** uses from the plan is the list of the databases in the plan.</span></span> <span data-ttu-id="2f87a-143">Alle Wartungsaktivitäten, die Sie in den anderen **sqlmaint** -Parametern angeben, werden auf die in dieser Liste aufgeführten Datenbanken angewendet.</span><span class="sxs-lookup"><span data-stu-id="2f87a-143">Any maintenance activities you specify in the other **sqlmaint** parameters are applied to this list of databases.</span></span> <span data-ttu-id="2f87a-144">Der GUID muss mit einem der plan_id-Werte in msdb.dbo.sysdbmaintplans übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2f87a-144">This must match a plan_id value in msdb.dbo.sysdbmaintplans.</span></span>  
  
 <span data-ttu-id="2f87a-145">**-Rpt** _text_file_</span><span class="sxs-lookup"><span data-stu-id="2f87a-145">**-Rpt** _text_file_</span></span>  
 <span data-ttu-id="2f87a-146">Gibt den vollständigen Pfad und Namen der Datei an, in der der Bericht generiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="2f87a-146">Specifies the full path and name of the file into which the report is to be generated.</span></span> <span data-ttu-id="2f87a-147">Der Bericht wird auch auf dem Bildschirm generiert.</span><span class="sxs-lookup"><span data-stu-id="2f87a-147">The report is also generated on the screen.</span></span> <span data-ttu-id="2f87a-148">Der Bericht verwaltet Versionsinformationen, indem er das Datum zum Dateinamen hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="2f87a-148">The report maintains version information by adding a date to the file name.</span></span> <span data-ttu-id="2f87a-149">Das Datum wird folgendermaßen generiert: am Ende des Dateinamens, aber vor dem Punkt im Format _*yyyyMMddhhmm*.</span><span class="sxs-lookup"><span data-stu-id="2f87a-149">The date is generated as follows: at the end of the file name but before the period, in the form _*yyyyMMddhhmm*.</span></span> <span data-ttu-id="2f87a-150">*yyyy* = Jahr, *MM* = Monat, *dd* = Tag, *hh* = Stunde, *mm* = Minute.</span><span class="sxs-lookup"><span data-stu-id="2f87a-150">*yyyy* = year, *MM* = month, *dd* = day, *hh* = hour, *mm* = minute.</span></span>  
  
 <span data-ttu-id="2f87a-151">Wenn Sie das Hilfsprogramm am 1. Dezember 1996 um 10:23 Uhr</span><span class="sxs-lookup"><span data-stu-id="2f87a-151">If you run the utility at 10:23 A.M.</span></span> <span data-ttu-id="2f87a-152">ausführen und dies der *Textdatei* -Wert ist:</span><span class="sxs-lookup"><span data-stu-id="2f87a-152">on December 1, 1996, and this is the *text_file* value:</span></span>  
  
```  
c:\Program Files\Microsoft SQL Server\Mssql\Backup\AdventureWorks2012_maint.rpt  
```  
  
 <span data-ttu-id="2f87a-153">Die generierte Datei hat dann folgenden Namen:</span><span class="sxs-lookup"><span data-stu-id="2f87a-153">The generated file name is:</span></span>  
  
```  
c:\Program Files\Microsoft SQL Server\Mssql\Backup\AdventureWorks2012_maint_199612011023.rpt  
```  
  
 <span data-ttu-id="2f87a-154">Für *extdatei* ist der vollständige UNC-Dateiname (Universal Naming Convention) erforderlich, wenn **sqlmaint** auf einen Remoteserver zugreift.</span><span class="sxs-lookup"><span data-stu-id="2f87a-154">The full Universal Naming Convention (UNC) file name is required for *text_file* when **sqlmaint** accesses a remote server.</span></span>  
  
 <span data-ttu-id="2f87a-155">**-Zu** _operator_name_</span><span class="sxs-lookup"><span data-stu-id="2f87a-155">**-To** _operator_name_</span></span>  
 <span data-ttu-id="2f87a-156">Gibt den Operator an, an den der generierte Bericht über SQL Mail gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="2f87a-156">Specifies the operator to whom the generated report is sent through SQL Mail.</span></span>  
  
 <span data-ttu-id="2f87a-157">**-HtmlRpt** _html_file_</span><span class="sxs-lookup"><span data-stu-id="2f87a-157">**-HtmlRpt** _html_file_</span></span>  
 <span data-ttu-id="2f87a-158">Gibt den vollständigen Pfad und Namen der Datei an, in der der HTML-Bericht generiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="2f87a-158">Specifies the full path and name of the file into which an HTML report is to be generated.</span></span> <span data-ttu-id="2f87a-159">**sqlmaint** generiert den Dateinamen, indem eine Zeichenfolge im Format _*yyyyMMddhhmm* an den Dateinamen angefügt wird, ebenso wie beim **-Rpt** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="2f87a-159">**sqlmaint** generates the file name by appending a string of the format _*yyyyMMddhhmm* to the file name, just as it does for the **-Rpt** parameter.</span></span>  
  
 <span data-ttu-id="2f87a-160">Für *HTML-Datei* ist der vollständige UNC-Dateiname erforderlich, wenn **sqlmaint** auf einen Remoteserver zugreift.</span><span class="sxs-lookup"><span data-stu-id="2f87a-160">The full UNC file name is required for *html_file* when **sqlmaint** accesses a remote server.</span></span>  
  
 <span data-ttu-id="2f87a-161">**-DelHtmlRpt** \<*time_period*></span><span class="sxs-lookup"><span data-stu-id="2f87a-161">**-DelHtmlRpt** \<*time_period*></span></span>  
 <span data-ttu-id="2f87a-162">Gibt an, dass alle HTML-Berichte im Berichtsverzeichnis gelöscht werden sollen, wenn das Zeitintervall nach dem Erstellen der Berichtsdatei den Wert für \<*time_period*> überschreitet.</span><span class="sxs-lookup"><span data-stu-id="2f87a-162">Specifies that any HTML report in the report directory be deleted if the time interval after the creation of the report file exceeds \<*time_period*>.</span></span> <span data-ttu-id="2f87a-163">**-DelHtmlRpt** sucht nach Dateien, deren Namen dem Muster entsprechen, das aus dem *HTML-Datei*-Parameter generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="2f87a-163">**-DelHtmlRpt** looks for files whose name fits the pattern generated from the *html_file* parameter.</span></span> <span data-ttu-id="2f87a-164">Wenn für *html_file* der Wert „C:\Programme\Microsoft SQL Server\Mssql\Backup\AdventureWorks2012_maint.htm“ angegeben wird, bewirkt **-DelHtmlRpt**, dass **sqlmaint** alle Dateien löscht, deren Namen dem Muster „C:\Programme\Microsoft SQL Server\Mssql\Backup\AdventureWorks2012_maint\*.htm“ entsprechen und die älter als der angegebene Wert für \<*time_period*> sind.</span><span class="sxs-lookup"><span data-stu-id="2f87a-164">If *html_file* is c:\Program Files\Microsoft SQL Server\Mssql\Backup\AdventureWorks2012_maint.htm, then **-DelHtmlRpt** causes **sqlmaint** to delete any files whose names match the pattern C:\Program Files\Microsoft SQL Server\Mssql\Backup\AdventureWorks2012_maint\*.htm and that are older than the specified \<*time_period*>.</span></span>  
  
 <span data-ttu-id="2f87a-165">**-RmUnusedSpace** _threshold_percent free_percent_</span><span class="sxs-lookup"><span data-stu-id="2f87a-165">**-RmUnusedSpace** _threshold_percent free_percent_</span></span>  
 <span data-ttu-id="2f87a-166">Gibt an, dass nicht verwendeter Speicherplatz aus der mit **-D**angegebenen Datenbank entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="2f87a-166">Specifies that unused space be removed from the database specified in **-D**.</span></span> <span data-ttu-id="2f87a-167">Diese Option ist nur für Datenbanken nützlich, die für das automatische Wachstum definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="2f87a-167">This option is only useful for databases that are defined to grow automatically.</span></span> <span data-ttu-id="2f87a-168">*Schwellenwert_Prozent* gibt die Größe in Megabytes an, die die Datenbank erreichen muss, bevor **sqlmaint** versucht, nicht verwendeten Datenspeicherplatz zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="2f87a-168">*Threshold_percent* specifies in megabytes the size that the database must reach before **sqlmaint** attempts to remove unused data space.</span></span> <span data-ttu-id="2f87a-169">Wenn die Datenbank kleiner als *Schwellenwert_Prozent*ist, wird keine Aktion ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2f87a-169">If the database is smaller than the *threshold_percent*, no action is taken.</span></span> <span data-ttu-id="2f87a-170">*Prozent_frei* gibt an, wie viel nicht verwendeter Speicherplatz in der Datenbank verbleiben muss. Die Angabe erfolgt als Prozentsatz der endgültigen Größe der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="2f87a-170">*Free_percent* specifies how much unused space must remain in the database, specified as a percentage of the final size of the database.</span></span> <span data-ttu-id="2f87a-171">Wenn eine 200 MB große Datenbank z.B. 100 MB an Daten enthält, bewirkt die Angabe des Werts 10 für *Prozent_frei* , dass die endgültige Größe der Datenbank 110 MB beträgt.</span><span class="sxs-lookup"><span data-stu-id="2f87a-171">For example, if a 200-MB database contains 100 MB of data, specifying 10 for *free_percent* results in the final database size being 110 MB.</span></span> <span data-ttu-id="2f87a-172">Beachten Sie, dass eine Datenbank nicht erweitert wird, wenn sie kleiner als der Wert ist, der sich aus *Prozent_frei* zuzüglich der Menge der Daten in der Datenbank ergibt.</span><span class="sxs-lookup"><span data-stu-id="2f87a-172">Note that a database is not expanded if it is smaller than *free_percent* plus the amount of data in the database.</span></span> <span data-ttu-id="2f87a-173">Wenn eine 108 MB große Datenbank z.B. 100 MB an Daten enthält, bewirkt die Angabe des Werts 10 für *Prozent_frei* nicht, dass die Datenbank auf 110 MB erweitert wird; die Datenbank bleibt 108 MB groß.</span><span class="sxs-lookup"><span data-stu-id="2f87a-173">For example, if a 108-MB database has 100 MB of data, specifying 10 for *free_percent* does not expand the database to 110 MB; it remains at 108 MB.</span></span>  
  
 <span data-ttu-id="2f87a-174">**-CkDB** |  **-CkDBNoIdx**</span><span class="sxs-lookup"><span data-stu-id="2f87a-174">**-CkDB** | **-CkDBNoIdx**</span></span>  
 <span data-ttu-id="2f87a-175">Gibt an, dass eine DBCC CHECKDB-Anweisung oder eine DBCC CHECKDB-Anweisung mit der Option NOINDEX in der Datenbank ausgeführt werden soll, die mit **-D**angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="2f87a-175">Specifies that a DBCC CHECKDB statement or a DBCC CHECKDB statement with the NOINDEX option be run in the database specified in **-D**.</span></span> <span data-ttu-id="2f87a-176">Weitere Informationen finden Sie unter DBCC CHECKDB.</span><span class="sxs-lookup"><span data-stu-id="2f87a-176">For more information, see DBCC CHECKDB.</span></span>  
  
 <span data-ttu-id="2f87a-177">Wenn die Datenbank zum Zeitpunkt der Ausführung von *sqlmaint* verwendet wird, wird eine Warnung in die Datei geschrieben, die mit **Textdatei** angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="2f87a-177">A warning is written to *text_file* if the database is in use when **sqlmaint** runs.</span></span>  
  
 <span data-ttu-id="2f87a-178">**-CkAl** |  **-CkAlNoIdx**</span><span class="sxs-lookup"><span data-stu-id="2f87a-178">**-CkAl** | **-CkAlNoIdx**</span></span>  
 <span data-ttu-id="2f87a-179">Gibt an, dass eine DBCC CHECKALLOC-Anweisung mit der Option NOINDEX in der Datenbank ausgeführt werden soll, die mit **-D**angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="2f87a-179">Specifies that a DBCC CHECKALLOC statement with the NOINDEX option be run in the database specified in **-D**.</span></span> <span data-ttu-id="2f87a-180">Weitere Informationen finden Sie unter [DBCC CHECKALLOC &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkalloc-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2f87a-180">For more information, see [DBCC CHECKALLOC &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkalloc-transact-sql).</span></span>  
  
 <span data-ttu-id="2f87a-181">**-CkCat**</span><span class="sxs-lookup"><span data-stu-id="2f87a-181">**-CkCat**</span></span>  
 <span data-ttu-id="2f87a-182">Gibt an, dass eine DBCC CHECKCATALOG-Anweisung (Transact-SQL) in der Datenbank ausgeführt werden soll, die mit **-D** angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="2f87a-182">Specifies that a DBCC CHECKCATALOG (Transact-SQL) statement be run in the database specified in **-D**.</span></span> <span data-ttu-id="2f87a-183">Weitere Informationen finden Sie unter [DBCC CHECKCATALOG &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkcatalog-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2f87a-183">For more information, see [DBCC CHECKCATALOG &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkcatalog-transact-sql).</span></span>  
  
 <span data-ttu-id="2f87a-184">**-UpdOptiStats** _sample_percent_</span><span class="sxs-lookup"><span data-stu-id="2f87a-184">**-UpdOptiStats** _sample_percent_</span></span>  
 <span data-ttu-id="2f87a-185">Gibt an, dass für jede Tabelle der Datenbank die folgende Anweisung ausgeführt werden soll:</span><span class="sxs-lookup"><span data-stu-id="2f87a-185">Specifies that the following statement be run on each table in the database:</span></span>  
  
```  
UPDATE STATISTICS table WITH SAMPLE sample_percent PERCENT;  
```  
  
 <span data-ttu-id="2f87a-186">Falls die Tabellen berechnete Spalten enthalten, müssen Sie auch das **-SupportedComputedColumn** -Argument angeben, wenn Sie **-UpdOptiStats**verwenden.</span><span class="sxs-lookup"><span data-stu-id="2f87a-186">If the tables contain computed columns, you must also specify the **-SupportedComputedColumn** argument when you use **-UpdOptiStats**.</span></span>  
  
 <span data-ttu-id="2f87a-187">Weitere Informationen finden Sie unter [UPDATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/update-statistics-transact-sql)erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="2f87a-187">For more information, see [UPDATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/update-statistics-transact-sql).</span></span>  
  
 <span data-ttu-id="2f87a-188">**-RebldIdx** _free_space_</span><span class="sxs-lookup"><span data-stu-id="2f87a-188">**-RebldIdx** _free_space_</span></span>  
 <span data-ttu-id="2f87a-189">Gibt an, dass die Indizes der Tabellen in der Zieldatenbank neu erstellt werden sollen, wobei der *Speicher_frei* -Prozentwert als Umkehrwert des Füllfaktors verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2f87a-189">Specifies that indexes on tables in the target database should be rebuilt by using the *free_space* percent value as the inverse of the fill factor.</span></span> <span data-ttu-id="2f87a-190">Wenn der *Speicher_frei* -Prozentsatz z.B. 30 beträgt, dann ist der verwendete Füllfaktor 70.</span><span class="sxs-lookup"><span data-stu-id="2f87a-190">For example, if *free_space* percentage is 30, then the fill factor used is 70.</span></span> <span data-ttu-id="2f87a-191">Wenn ein *Speicher_frei* -Prozentwert von 100 angegeben wird, werden die Indizes mit dem ursprünglichen Füllfaktorwert neu erstellt.</span><span class="sxs-lookup"><span data-stu-id="2f87a-191">If a *free_space* percentage value of 100 is specified, then the indexes are rebuilt with the original fill factor value.</span></span>  
  
 <span data-ttu-id="2f87a-192">Falls die Indizes für berechnete Spalten erstellt wurden, müssen Sie zudem das **-SupportComputedColumn-** Argument angeben, wenn Sie **-RebldIdx**verwenden.</span><span class="sxs-lookup"><span data-stu-id="2f87a-192">If the indexes are on computed columns, you must also specify the **-SupportComputedColumn** argument when you use **-RebldIdx**.</span></span>  
  
 <span data-ttu-id="2f87a-193">**-SupportComputedColumn-**</span><span class="sxs-lookup"><span data-stu-id="2f87a-193">**-SupportComputedColumn**</span></span>  
 <span data-ttu-id="2f87a-194">Muss angegeben werden, um DBCC-Wartungsbefehle mit **sqlmaint** für berechnete Spalten auszuführen.</span><span class="sxs-lookup"><span data-stu-id="2f87a-194">Must be specified to run DBCC maintenance commands with **sqlmaint** on computed columns.</span></span>  
  
 <span data-ttu-id="2f87a-195">**-WriteHistory**</span><span class="sxs-lookup"><span data-stu-id="2f87a-195">**-WriteHistory**</span></span>  
 <span data-ttu-id="2f87a-196">Gibt an, dass für jede von **sqlmaint**durchgeführte Wartungsaktion ein Eintrag in msdb.dbo.sysdbmaintplan_history vorgenommen wird.</span><span class="sxs-lookup"><span data-stu-id="2f87a-196">Specifies that an entry be made in msdb.dbo.sysdbmaintplan_history for each maintenance action performed by **sqlmaint**.</span></span> <span data-ttu-id="2f87a-197">Wenn **-PlanName** oder **-PlanID** angegeben ist, wird für die Einträge in sysdbmaintplan_history die ID des angegebenen Plans verwendet.</span><span class="sxs-lookup"><span data-stu-id="2f87a-197">If **-PlanName** or **-PlanID** is specified, the entries in sysdbmaintplan_history use the ID of the specified plan.</span></span> <span data-ttu-id="2f87a-198">Wenn **-D** angegeben ist, werden für die Einträge in sysdbmaintplan_history Nullen für die Plan-ID verwendet.</span><span class="sxs-lookup"><span data-stu-id="2f87a-198">If **-D** is specified, the entries in sysdbmaintplan_history are made with zeroes for the plan ID.</span></span>  
  
 <span data-ttu-id="2f87a-199">**-BkUpDB** [ *Sicherungspfad*] |  **-BkUpLog** [ *Sicherungspfad* ]</span><span class="sxs-lookup"><span data-stu-id="2f87a-199">**-BkUpDB** [ *backup_path*] |  **-BkUpLog** [ *backup_path* ]</span></span>  
 <span data-ttu-id="2f87a-200">Gibt eine Sicherungsaktion an.</span><span class="sxs-lookup"><span data-stu-id="2f87a-200">Specifies a backup action.</span></span> <span data-ttu-id="2f87a-201">**-BkUpDb** sichert die gesamte Datenbank.</span><span class="sxs-lookup"><span data-stu-id="2f87a-201">**-BkUpDb** backs up the entire database.</span></span> <span data-ttu-id="2f87a-202">**-BkUpLog** sichert nur das Transaktionsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="2f87a-202">**-BkUpLog** backs up only the transaction log.</span></span>  
  
 <span data-ttu-id="2f87a-203">*Sicherungspfad* gibt das Verzeichnis für die Sicherung an.</span><span class="sxs-lookup"><span data-stu-id="2f87a-203">*backup_path* specifies the directory for the backup.</span></span> <span data-ttu-id="2f87a-204">*Sicherungspfad* wird nicht benötigt, wenn auch **-UseDefDir** angegeben wird, und wird von **-UseDefDir** überschrieben, wenn beide angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="2f87a-204">*backup_path* is not needed if **-UseDefDir** is also specified, and is overridden by **-UseDefDir** if both are specified.</span></span> <span data-ttu-id="2f87a-205">Die Sicherung kann in einem Verzeichnis oder einer Bandmediumadresse, z.B. \\\\.\TAPE0, platziert werden.</span><span class="sxs-lookup"><span data-stu-id="2f87a-205">The backup can be placed in a directory or a tape device address (for example, \\\\.\TAPE0).</span></span> <span data-ttu-id="2f87a-206">Der Dateiname für eine Datenbanksicherung wird automatisch folgendermaßen generiert:</span><span class="sxs-lookup"><span data-stu-id="2f87a-206">The file name for a database backup is generated automatically as follows:</span></span>  
  
```  
dbname_db_yyyyMMddhhmm.BAK  
  
```  
  
 <span data-ttu-id="2f87a-207">Hierbei gilt:</span><span class="sxs-lookup"><span data-stu-id="2f87a-207">where</span></span>  
  
-   <span data-ttu-id="2f87a-208">*dbname* ist der Name der Datenbank, die gesichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="2f87a-208">*dbname* is the name of the database being backed up.</span></span>  
  
-   <span data-ttu-id="2f87a-209">*yyyyMMddhhmm* ist die Uhrzeit des Sicherungsvorgangs ( *yyyy* = Jahr, *MM* = Monat, *dd* = Tag, *hh* = Stunde und *mm* = Minute).</span><span class="sxs-lookup"><span data-stu-id="2f87a-209">*yyyyMMddhhmm* is the time of the backup operation with *yyyy* = year, *MM* = month, *dd* = day, *hh* = hour, and *mm* = minute.</span></span>  
  
 <span data-ttu-id="2f87a-210">Der Dateiname für eine Transaktionssicherung wird automatisch in einem ähnlichen Format generiert:</span><span class="sxs-lookup"><span data-stu-id="2f87a-210">The file name for a transaction backup is generated automatically with a similar format:</span></span>  
  
```  
dbname_log_yyyymmddhhmm.BAK  
  
```  
  
 <span data-ttu-id="2f87a-211">Wenn Sie den **-BkUpDB** -Parameter verwenden, müssen Sie mithilfe des **-BkUpMedia** -Parameters auch das Medium angeben.</span><span class="sxs-lookup"><span data-stu-id="2f87a-211">If you use the **-BkUpDB** parameter, you must also specify the media by using the **-BkUpMedia** parameter.</span></span>  
  
 <span data-ttu-id="2f87a-212">**-BkUpMedia**</span><span class="sxs-lookup"><span data-stu-id="2f87a-212">**-BkUpMedia**</span></span>  
 <span data-ttu-id="2f87a-213">Gibt den Medientyp der Sicherung an, entweder DISK oder TAPE.</span><span class="sxs-lookup"><span data-stu-id="2f87a-213">Specifies the media type of the backup, either DISK or TAPE.</span></span>  
  
 <span data-ttu-id="2f87a-214">**DISK**</span><span class="sxs-lookup"><span data-stu-id="2f87a-214">**DISK**</span></span>  
 <span data-ttu-id="2f87a-215">Gibt an, dass das Sicherungsmedium ein Datenträger ist.</span><span class="sxs-lookup"><span data-stu-id="2f87a-215">Specifies that the backup medium is disk.</span></span>  
  
 <span data-ttu-id="2f87a-216">**-Delta-Konfigurationsobjekte**\< *time_period* ></span><span class="sxs-lookup"><span data-stu-id="2f87a-216">**-DelBkUps**\< *time_period* ></span></span>  
 <span data-ttu-id="2f87a-217">Gibt bei Datenträgersicherungen an, dass alle Sicherungsdateien im Sicherungsverzeichnis gelöscht werden sollen, wenn das Zeitintervall nach dem Erstellen der Sicherungsdatei den Wert für \<*time_period*> überschreitet.</span><span class="sxs-lookup"><span data-stu-id="2f87a-217">For disk backups, specifies that any backup file in the backup directory be deleted if the time interval after the creation of the backup exceeds the \<*time_period*>.</span></span>  
  
 <span data-ttu-id="2f87a-218">**-CrBkSubDir**</span><span class="sxs-lookup"><span data-stu-id="2f87a-218">**-CrBkSubDir**</span></span>  
 <span data-ttu-id="2f87a-219">Gibt bei Datenträgersicherungen an, dass ein Unterverzeichnis im Verzeichnis [*Sicherungspfad*] oder im Standardsicherungsverzeichnis erstellt werden soll, wenn **-UseDefDir** ebenfalls angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="2f87a-219">For disk backups, specifies that a subdirectory be created in the [*backup_path*] directory or in the default backup directory if **-UseDefDir** is also specified.</span></span> <span data-ttu-id="2f87a-220">Der Name des Unterverzeichnisses wird anhand des Datenbanknamens generiert, der mit **-D**angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="2f87a-220">The name of the subdirectory is generated from the database name specified in **-D**.</span></span> <span data-ttu-id="2f87a-221">**-CrBkSubDir** bietet ein einfaches Verfahren, um alle Sicherungen für verschiedene Datenbanken in unterschiedlichen Unterverzeichnissen abzulegen, ohne den *Sicherungspfad* -Parameter ändern zu müssen.</span><span class="sxs-lookup"><span data-stu-id="2f87a-221">**-CrBkSubDir** offers an easy way to put all the backups for different databases into separate subdirectories without having to change the *backup_path* parameter.</span></span>  
  
 <span data-ttu-id="2f87a-222">**-UseDefDir**</span><span class="sxs-lookup"><span data-stu-id="2f87a-222">**-UseDefDir**</span></span>  
 <span data-ttu-id="2f87a-223">Gibt für Datenträgersicherungen an, dass die Sicherungsdatei im Standardsicherungsverzeichnis erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="2f87a-223">For disk backups, specifies that the backup file be created in the default backup directory.</span></span> <span data-ttu-id="2f87a-224">**UseDefDir** überschreibt *Sicherungspfad* , wenn beide Parameter angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="2f87a-224">**UseDefDir** overrides *backup_path* if both are specified.</span></span> <span data-ttu-id="2f87a-225">Bei einer Standardeinrichtung von [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] befindet sich das Standardsicherungsverzeichnis unter dem Pfad „C:\Program Files\Microsoft SQL Server\MSSQL10_50.MSSQLSERVER\MSSQL\Backup“.</span><span class="sxs-lookup"><span data-stu-id="2f87a-225">With a default [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] setup, the default backup directory is C:\Program Files\Microsoft SQL Server\MSSQL10_50.MSSQLSERVER\MSSQL\Backup.</span></span>  
  
 <span data-ttu-id="2f87a-226">**TAPE**</span><span class="sxs-lookup"><span data-stu-id="2f87a-226">**TAPE**</span></span>  
 <span data-ttu-id="2f87a-227">Gibt an, dass das Sicherungsmedium ein Band ist.</span><span class="sxs-lookup"><span data-stu-id="2f87a-227">Specifies that the backup medium is tape.</span></span>  
  
 <span data-ttu-id="2f87a-228">**-BkUpOnlyIfClean**</span><span class="sxs-lookup"><span data-stu-id="2f87a-228">**-BkUpOnlyIfClean**</span></span>  
 <span data-ttu-id="2f87a-229">Gibt an, dass eine Sicherung nur dann erfolgt, wenn bei den mit **-Ck** angegebenen Überprüfungen keine Probleme bei den Daten gefunden wurden.</span><span class="sxs-lookup"><span data-stu-id="2f87a-229">Specifies that the backup occur only if any specified **-Ck** checks did not find problems with the data.</span></span> <span data-ttu-id="2f87a-230">Wartungsaktionen werden in derselben Reihenfolge ausgeführt, in der sie an der Eingabeaufforderung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="2f87a-230">Maintenance actions run in the same sequence as they appear in the command prompt.</span></span> <span data-ttu-id="2f87a-231">Geben Sie die Parameter **-CkDB**, **-CkDBNoIdx**, **-CkAl**, **-CkAlNoIdx**, **-CkTxtAl**oder **-CkCat** vor den Parametern **-BkUpDB**/ **-BkUpLog** an, wenn Sie auch **-BkUpOnlyIfClean**angeben möchten. Andernfalls erfolgt die Sicherung unabhängig davon, ob bei der Überprüfung Probleme gemeldet werden oder nicht.</span><span class="sxs-lookup"><span data-stu-id="2f87a-231">Specify the parameters **-CkDB**, **-CkDBNoIdx**, **-CkAl**, **-CkAlNoIdx**, **-CkTxtAl**, or **-CkCat** before the **-BkUpDB**/**-BkUpLog** parameter(s) if you are also going to specify **-BkUpOnlyIfClean**, or the backup occurs whether or not the check reports problems.</span></span>  
  
 <span data-ttu-id="2f87a-232">**-VrfyBackup**</span><span class="sxs-lookup"><span data-stu-id="2f87a-232">**-VrfyBackup**</span></span>  
 <span data-ttu-id="2f87a-233">Gibt an, dass für die Sicherung RESTORE VERIFYONLY ausgeführt wird, sobald die Sicherung abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="2f87a-233">Specifies that RESTORE VERIFYONLY be run on the backup when it completes.</span></span>  
  
 <span data-ttu-id="2f87a-234">*number*[**minutes**| **hours**| **day**| **weeks**| **months**]</span><span class="sxs-lookup"><span data-stu-id="2f87a-234">*number*[**minutes**| **hours**| **day**| **weeks**| **months**]</span></span>  
 <span data-ttu-id="2f87a-235">Gibt das Zeitintervall an, das verwendet wurde, um zu bestimmen, ob ein Bericht oder eine Sicherungsdatei alt genug ist, um gelöscht zu werden.</span><span class="sxs-lookup"><span data-stu-id="2f87a-235">Specifies the time interval used to determine if a report or backup file is old enough to be deleted.</span></span> <span data-ttu-id="2f87a-236">*number* ist eine ganze Zahl, gefolgt von einer Zeiteinheit (ohne Leerzeichen).</span><span class="sxs-lookup"><span data-stu-id="2f87a-236">*number* is an integer followed (without a space) by a unit of time.</span></span> <span data-ttu-id="2f87a-237">Gültige Beispiele:</span><span class="sxs-lookup"><span data-stu-id="2f87a-237">Valid examples:</span></span>  
  
-   <span data-ttu-id="2f87a-238">**12weeks**</span><span class="sxs-lookup"><span data-stu-id="2f87a-238">**12weeks**</span></span>  
  
-   <span data-ttu-id="2f87a-239">**3months**</span><span class="sxs-lookup"><span data-stu-id="2f87a-239">**3months**</span></span>  
  
-   <span data-ttu-id="2f87a-240">**15days**</span><span class="sxs-lookup"><span data-stu-id="2f87a-240">**15days**</span></span>  
  
 <span data-ttu-id="2f87a-241">Wird nur *number* angegeben, wird **weeks**als standardmäßiges Datumsteil verwendet.</span><span class="sxs-lookup"><span data-stu-id="2f87a-241">If only *number* is specified, the default date part is **weeks**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2f87a-242">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="2f87a-242">Remarks</span></span>  
 <span data-ttu-id="2f87a-243">Das Hilfsprogramm **sqlmaint** führt Wartungsvorgänge für eine oder mehrere Datenbanken aus.</span><span class="sxs-lookup"><span data-stu-id="2f87a-243">The **sqlmaint** utility performs maintenance operations on one or more databases.</span></span> <span data-ttu-id="2f87a-244">Wenn **-D** angegeben wird, werden die Vorgänge, die mit den verbleibenden Schaltern angegeben werden, nur für die angegebene Datenbank ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2f87a-244">If **-D** is specified, the operations specified in the remaining switches are performed only on the specified database.</span></span> <span data-ttu-id="2f87a-245">Wenn **-PlanName** oder **-PlanID** angegeben wird, ruft **sqlmaint** aus dem angegebenen Wartungsplan nur die Liste der Datenbanken im Plan ab.</span><span class="sxs-lookup"><span data-stu-id="2f87a-245">If **-PlanName** or **-PlanID** are specified, the only information **sqlmaint** retrieves from the specified maintenance plan is the list of databases in the plan.</span></span> <span data-ttu-id="2f87a-246">Alle in den verbleibenden **sqlmaint** -Parametern angegebenen Vorgänge werden für jede Datenbank in der Liste ausgeführt, die aus dem Plan abgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="2f87a-246">All operations specified in the remaining **sqlmaint** parameters are applied against each database in the list obtained from the plan.</span></span> <span data-ttu-id="2f87a-247">Das Hilfsprogramm **sqlmaint** wendet keine der im Plan selbst definierten Wartungsaktivitäten an.</span><span class="sxs-lookup"><span data-stu-id="2f87a-247">The **sqlmaint** utility does not apply any of the maintenance activities defined in the plan itself.</span></span>  
  
 <span data-ttu-id="2f87a-248">Das Hilfsprogramm **sqlmaint** gibt bei erfolgreicher Ausführung 0 und bei Auftreten eines Fehlers 1 zurück.</span><span class="sxs-lookup"><span data-stu-id="2f87a-248">The **sqlmaint** utility returns 0 if it runs successfully or 1 if it fails.</span></span> <span data-ttu-id="2f87a-249">Ein Fehler wird in folgenden Fällen gemeldet:</span><span class="sxs-lookup"><span data-stu-id="2f87a-249">Failure is reported:</span></span>  
  
-   <span data-ttu-id="2f87a-250">Eine Wartungsaktion ist fehlgeschlagen.</span><span class="sxs-lookup"><span data-stu-id="2f87a-250">If any of the maintenance actions fail.</span></span>  
  
-   <span data-ttu-id="2f87a-251">Die Überprüfungen **-CkDB**, **-CkDBNoIdx**, **-CkAl**, **-CkAlNoIdx**, **-CkTxtAl**oder **-CkCat** finden Probleme mit den Daten.</span><span class="sxs-lookup"><span data-stu-id="2f87a-251">If **-CkDB**, **-CkDBNoIdx**, **-CkAl**, **-CkAlNoIdx**, **-CkTxtAl**, or **-CkCat** checks find problems with the data.</span></span>  
  
-   <span data-ttu-id="2f87a-252">Ein allgemeiner Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="2f87a-252">If a general failure is encountered.</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="2f87a-253">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="2f87a-253">Permissions</span></span>  
 <span data-ttu-id="2f87a-254">Das Hilfsprogramm **sqlmaint** kann von jedem Windows-Benutzer ausgeführt werden, der über die Berechtigung **Lesen und Ausführen** für die Datei `sqlmaint.exe`verfügt, die standardmäßig im Ordner `x:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER1\MSSQL\Binn` gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="2f87a-254">The **sqlmaint** utility can be executed by any Windows user with **Read and Execute** permission on `sqlmaint.exe`, which by default is stored in the `x:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER1\MSSQL\Binn` folder.</span></span> <span data-ttu-id="2f87a-255">Darüber hinaus muss der mit [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -login_ID **angegebene** -Anmeldename über die [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Berechtigungen verfügen, die zum Ausführen der jeweiligen Aktion erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="2f87a-255">Additionally, the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] login specified with **-login_ID** must have the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] permissions required to perform the specified action.</span></span> <span data-ttu-id="2f87a-256">Wird bei der Verbindung zu [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] die Windows-Authentifizierung verwendet, muss der dem authentifizierten Windows-Benutzer zugeordnete [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Anmeldename über die [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Berechtigungen zum Ausführen der jeweiligen Aktion verfügen.</span><span class="sxs-lookup"><span data-stu-id="2f87a-256">If the connection to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] uses Windows Authentication, the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] login mapped to the authenticated Windows user must have the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] permissions required to perform the specified action.</span></span>  
  
 <span data-ttu-id="2f87a-257">Beispielsweise erfordert die Verwendung von **-BkUpDB** die Berechtigung zum Ausführen der BACKUP-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="2f87a-257">For example, using the **-BkUpDB** requires permission to execute the BACKUP statement.</span></span> <span data-ttu-id="2f87a-258">Die Verwendung des **-UpdOptiStats** -Arguments erfordert zudem die Berechtigung zum Ausführen der UPDATE STATISTICS-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="2f87a-258">And using the **-UpdOptiStats** argument requires permission to execute the UPDATE STATISTICS statement.</span></span> <span data-ttu-id="2f87a-259">Weitere Informationen finden Sie in den Abschnitten zu Berechtigungen in den entsprechenden Themen der Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="2f87a-259">For more information, see the "Permissions" sections of the corresponding topics in Books Online.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="2f87a-260">Beispiele</span><span class="sxs-lookup"><span data-stu-id="2f87a-260">Examples</span></span>  
  
### <a name="a-performing-dbcc-checks-on-a-database"></a><span data-ttu-id="2f87a-261">A.</span><span class="sxs-lookup"><span data-stu-id="2f87a-261">A.</span></span> <span data-ttu-id="2f87a-262">Ausführen von DBCC-Überprüfungen für eine Datenbank</span><span class="sxs-lookup"><span data-stu-id="2f87a-262">Performing DBCC checks on a database</span></span>  
  
```  
sqlmaint -S MyServer -D AdventureWorks2012 -CkDB -CkAl -CkCat -Rpt C:\MyReports\AdvWks_chk.rpt  
```  
  
### <a name="b-updating-statistics-using-a-15-sample-in-all-databases-in-a-plan-also-shrink-any-of-the-database-that-have-reached-110-mb-to-having-only-10-free-space"></a><span data-ttu-id="2f87a-263">B.</span><span class="sxs-lookup"><span data-stu-id="2f87a-263">B.</span></span> <span data-ttu-id="2f87a-264">Aktualisieren von Statistiken in allen Datenbanken in einem Plan mithilfe einer Stichprobe von 15 %.</span><span class="sxs-lookup"><span data-stu-id="2f87a-264">Updating statistics using a 15% sample in all databases in a plan.</span></span> <span data-ttu-id="2f87a-265">Weiterhin: Verkleinern aller Datenbanken, die eine Größe von 110 MB erreicht haben, sodass sie anschließend nur noch 10 % freien Speicherplatz aufweisen</span><span class="sxs-lookup"><span data-stu-id="2f87a-265">Also, shrink any of the database that have reached 110 MB to having only 10% free space</span></span>  
  
```  
sqlmaint -S MyServer -PlanName MyUserDBPlan -UpdOptiStats 15 -RmUnusedSpace 110 10  
```  
  
### <a name="c-backing-up-all-the-databases-in-a-plan-to-their-individual-subdirectories-in-the-default-xprogram-filesmicrosoft-sql-servermssql12mssqlservermssqlbackup-directory-also-delete-any-backups-older-than-2-weeks"></a><span data-ttu-id="2f87a-266">C.</span><span class="sxs-lookup"><span data-stu-id="2f87a-266">C.</span></span> <span data-ttu-id="2f87a-267">Sichern aller Datenbanken in einem Plan in ihren jeweiligen Unterverzeichnissen im Standardverzeichnis "x:\Programme\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Backup".</span><span class="sxs-lookup"><span data-stu-id="2f87a-267">Backing up all the databases in a plan to their individual subdirectories in the default x:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Backup directory.</span></span> <span data-ttu-id="2f87a-268">Weiterhin: Löschen aller Sicherungen, die älter als 2 Wochen sind</span><span class="sxs-lookup"><span data-stu-id="2f87a-268">Also, delete any backups older than 2 weeks</span></span>  
  
```  
sqlmaint -S MyServer -PlanName MyUserDBPlan -BkUpDB -BkUpMedia DISK -UseDefDir -CrBkSubDir -DelBkUps 2weeks  
```  
  
### <a name="d-backing-up-a-database-to-the-default-xprogram-filesmicrosoft-sql-servermssql12mssqlservermssqlbackup-directory"></a><span data-ttu-id="2f87a-269">D:</span><span class="sxs-lookup"><span data-stu-id="2f87a-269">D.</span></span> <span data-ttu-id="2f87a-270">Sichern einer Datenbank im Standardverzeichnis "x:\Programme\Microsoft SQL server\mssql12." Mssqlserver\mssql\sicherungsverzeichnis. </span><span class="sxs-lookup"><span data-stu-id="2f87a-270">Backing up a database to the default x:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Backup directory.</span></span>\  
  
```  
sqlmaint -S MyServer -BkUpDB -BkUpMedia DISK -UseDefDir  
```  
  
## <a name="see-also"></a><span data-ttu-id="2f87a-271">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2f87a-271">See Also</span></span>  
 <span data-ttu-id="2f87a-272">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2f87a-272">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 [<span data-ttu-id="2f87a-273">UPDATE STATISTICS &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2f87a-273">UPDATE STATISTICS &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/update-statistics-transact-sql)  
  
  
