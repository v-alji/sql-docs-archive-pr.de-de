---
title: osql-Hilfsprogramm | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- statements [SQL Server], command prompt
- QUIT command
- Transact-SQL statements, command prompt
- EXIT command
- operating systems [SQL Server], commands
- osql utility [SQL Server]
- stored procedures [SQL Server], command prompt
- scripts [SQL Server], command prompt
- RESET command
- GO command
- command prompt utilities [SQL Server], osql
- CTRL+C command
ms.assetid: cf530d9e-0609-4528-8975-ab8e08e40b9a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 95782afe0de8567781316e3478d04a090f968ed5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694977"
---
# <a name="osql-utility"></a><span data-ttu-id="fb3f7-102">osql (Hilfsprogramm)</span><span class="sxs-lookup"><span data-stu-id="fb3f7-102">osql Utility</span></span>
  <span data-ttu-id="fb3f7-103">Das Hilfsprogramm **osql** ermöglicht es Ihnen, [!INCLUDE[tsql](../includes/tsql-md.md)] -Anweisungen, Systemprozeduren und Skriptdateien einzugeben.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-103">The **osql** utility allows you to enter [!INCLUDE[tsql](../includes/tsql-md.md)] statements, system procedures, and script files.</span></span> <span data-ttu-id="fb3f7-104">Dieses Hilfsprogramm verwendet ODBC, um Daten mit dem Server auszutauschen.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-104">This utility uses ODBC to communicate with the server.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="fb3f7-105">Diese Funktion wird in einer zukünftigen Version von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]entfernt.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-105">This feature will be removed in a future version of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="fb3f7-106">Verwenden Sie diese Funktion beim Entwickeln neuer Anwendungen nicht, und planen Sie das Ändern von Anwendungen, in denen sie aktuell verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-106">Avoid using this feature in new development work, and plan to modify applications that currently use the feature.</span></span> <span data-ttu-id="fb3f7-107">Verwenden Sie stattdessen **sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="fb3f7-107">Use **sqlcmd** instead.</span></span> <span data-ttu-id="fb3f7-108">Weitere Informationen finden Sie unter [sqlcmd Utility](sqlcmd-utility.md).</span><span class="sxs-lookup"><span data-stu-id="fb3f7-108">For more information, see [sqlcmd Utility](sqlcmd-utility.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb3f7-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="fb3f7-109">Syntax</span></span>  
  
```  
  
      osql  
[-?] |  
[-L] |  
[  
  {  
     {-Ulogin_id [-Ppassword]} | -E }  
     [-Sserver_name[\instance_name]] [-Hwksta_name] [-ddb_name]  
     [-ltime_out] [-ttime_out] [-hheaders]  
     [-scol_separator] [-wcolumn_width] [-apacket_size]  
     [-e] [-I] [-D data_source_name]  
     [-ccmd_end] [-q "query"] [-Q"query"]  
     [-n] [-merror_level] [-r {0 | 1}]  
     [-iinput_file] [-ooutput_file] [-p]  
     [-b] [-u] [-R] [-O]  
]  
```  
  
## <a name="arguments"></a><span data-ttu-id="fb3f7-110">Argumente</span><span class="sxs-lookup"><span data-stu-id="fb3f7-110">Arguments</span></span>  
 <span data-ttu-id="fb3f7-111">**-?**</span><span class="sxs-lookup"><span data-stu-id="fb3f7-111">**-?**</span></span>  
 <span data-ttu-id="fb3f7-112">Zeigt eine Syntaxzusammenfassung der **osql** -Schalter an.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-112">Displays the syntax summary of **osql** switches.</span></span>  
  
 <span data-ttu-id="fb3f7-113">**-L**</span><span class="sxs-lookup"><span data-stu-id="fb3f7-113">**-L**</span></span>  
 <span data-ttu-id="fb3f7-114">Listet die lokal konfigurierten Server sowie die Namen der Server auf, die Nachrichten über das Netzwerk senden.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-114">Lists the locally configured servers and the names of the servers broadcasting on the network.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fb3f7-115">Aufgrund der Übertragungsart in Netzwerken, ist es möglich, dass **osql** nicht zeitnah von allen Servern eine Antwort erhält.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-115">Due to the nature of broadcasting on networks, **osql** may not receive a timely response from all servers.</span></span> <span data-ttu-id="fb3f7-116">Aus diesem Grund kann die Liste der zurückgegebenen Server mit jedem Aufruf dieser Option variieren.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-116">Therefore the list of servers returned may vary for each invocation of this option.</span></span>  
  
 <span data-ttu-id="fb3f7-117">**-U** _login_id_</span><span class="sxs-lookup"><span data-stu-id="fb3f7-117">**-U** _login_id_</span></span>  
 <span data-ttu-id="fb3f7-118">Die Benutzeranmelde-ID.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-118">Is the user login ID.</span></span> <span data-ttu-id="fb3f7-119">Bei Anmelde-IDs wird die Groß- und Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-119">Login IDs are case-sensitive.</span></span>  
  
 <span data-ttu-id="fb3f7-120">**-P** _password_</span><span class="sxs-lookup"><span data-stu-id="fb3f7-120">**-P** _password_</span></span>  
 <span data-ttu-id="fb3f7-121">Ein vom Benutzer angegebenes Kennwort.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-121">Is a user-specified password.</span></span> <span data-ttu-id="fb3f7-122">Falls die Option **-P** nicht verwendet wird, fordert **osql** zur Eingabe eines Kennworts auf.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-122">If the **-P** option is not used, **osql** prompts for a password.</span></span> <span data-ttu-id="fb3f7-123">Falls die Option **-P** am Ende der Eingabeaufforderung ohne Angabe eines Kennworts verwendet wird, verwendet **osql** das Standardkennwort (NULL).</span><span class="sxs-lookup"><span data-stu-id="fb3f7-123">If the **-P** option is used at the end of the command prompt without any password, **osql** uses the default password (NULL).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="fb3f7-124">Verwenden Sie kein leeres Kennwort.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-124">Do not use a blank password.</span></span> <span data-ttu-id="fb3f7-125">Verwenden Sie ein sicheres Kennwort.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-125">Use a strong password.</span></span> <span data-ttu-id="fb3f7-126">Weitere Informationen finden Sie unter [Strong Passwords](../relational-databases/security/strong-passwords.md).</span><span class="sxs-lookup"><span data-stu-id="fb3f7-126">For more information, see [Strong Passwords](../relational-databases/security/strong-passwords.md).</span></span>  
  
 <span data-ttu-id="fb3f7-127">Bei Kennwörtern wird nach Groß- und Kleinschreibung unterschieden.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-127">Passwords are case-sensitive.</span></span>  
  
 <span data-ttu-id="fb3f7-128">Über die OSQLPASSWORD-Umgebungsvariable können Sie ein Standardkennwort für die aktuelle Sitzung festlegen.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-128">The OSQLPASSWORD environment variable allows you to set a default password for the current session.</span></span> <span data-ttu-id="fb3f7-129">Dadurch müssen Sie keine Kennwörter in Batchdateien hartcodieren.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-129">Therefore, you do not have to hard code a password into batch files.</span></span>  
  
 <span data-ttu-id="fb3f7-130">Falls Sie kein Kennwort mit der Option **-P** angeben, überprüft **osql** zuerst die OSQLPASSWORD-Variable.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-130">If you do not specify a password with the **-P** option, **osql** first checks for the OSQLPASSWORD variable.</span></span> <span data-ttu-id="fb3f7-131">Wurde kein Wert festgelegt, verwendet **osql** das Standardkennwort (NULL).</span><span class="sxs-lookup"><span data-stu-id="fb3f7-131">If no value is set, **osql** uses the default password, NULL.</span></span> <span data-ttu-id="fb3f7-132">Im folgenden Beispiel wird die OSQLPASSWORD-Variable an der Eingabeaufforderung festgelegt und greift dann auf das Hilfsprogramm **osql** zu:</span><span class="sxs-lookup"><span data-stu-id="fb3f7-132">The following example sets the OSQLPASSWORD variable at a command prompt and then accesses the **osql** utility:</span></span>  
  
```  
C:\>SET OSQLPASSWORD=abracadabra  
C:\>osql   
```  
  
> [!IMPORTANT]  
>  <span data-ttu-id="fb3f7-133">Zum Maskieren des Kennworts sollten Sie die Option **-P** nicht in Verbindung mit der Option **-U** angeben.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-133">To mask your password, do not specify the **-P** option along with the **-U** option.</span></span> <span data-ttu-id="fb3f7-134">Drücken Sie stattdessen nach der Angabe von **osql** mit der Option **-U** und anderen Schaltern (geben Sie **-P**nicht an) die EINGABETASTE. Sie werden daraufhin von **osql** zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-134">Instead, after specifying **osql** along with the **-U** option and other switches (do not specify **-P**), press ENTER, and **osql** will prompt you for a password.</span></span> <span data-ttu-id="fb3f7-135">Durch diese Methode wird sichergestellt, dass das Kennwort bei der Eingabe maskiert wird.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-135">This method ensures that your password will be masked when it is entered.</span></span>  
  
 <span data-ttu-id="fb3f7-136">**-E**</span><span class="sxs-lookup"><span data-stu-id="fb3f7-136">**-E**</span></span>  
 <span data-ttu-id="fb3f7-137">Verwendet eine vertrauenswürdige Verbindung, statt ein Kennwort anzufordern.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-137">Uses a trusted connection instead of requesting a password.</span></span>  
  
 <span data-ttu-id="fb3f7-138">**-S** _server_name_[ **\\** _instance_name_]</span><span class="sxs-lookup"><span data-stu-id="fb3f7-138">**-S** _server_name_[ **\\**_instance_name_]</span></span>  
 <span data-ttu-id="fb3f7-139">Gibt die [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Instanz an, mit der eine Verbindung hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-139">Specifies the instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to connect to.</span></span> <span data-ttu-id="fb3f7-140">Geben Sie *server_name* an, um eine Verbindung mit der Standardinstanz von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] auf diesem Server herzustellen.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-140">Specify *server_name* to connect to the default instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] on that server.</span></span> <span data-ttu-id="fb3f7-141">Geben Sie _server_name_ **\\** _instance_name_ an, um eine Verbindung mit einer benannten Instanz von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] auf diesem Server herzustellen.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-141">Specify _server_name_**\\**_instance_name_ to connect to a named instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] on that server.</span></span> <span data-ttu-id="fb3f7-142">Falls kein Server angegeben ist, stellt **osql** eine Verbindung mit der Standardinstanz von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] auf dem lokalen Computer her.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-142">If no server is specified, **osql** connects to the default instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] on the local computer.</span></span> <span data-ttu-id="fb3f7-143">Diese Option ist erforderlich, wenn **osql** von einem Remotecomputer im Netzwerk ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-143">This option is required when executing **osql** from a remote computer on the network.</span></span>  
  
 <span data-ttu-id="fb3f7-144">**-H** _wksta_name_</span><span class="sxs-lookup"><span data-stu-id="fb3f7-144">**-H** _wksta_name_</span></span>  
 <span data-ttu-id="fb3f7-145">Der Name einer Arbeitsstation.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-145">Is a workstation name.</span></span> <span data-ttu-id="fb3f7-146">Dieser Name ist in **sysprocesses.hostname** gespeichert und wird mithilfe von **sp_who**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-146">The workstation name is stored in **sysprocesses.hostname** and is displayed by **sp_who**.</span></span> <span data-ttu-id="fb3f7-147">Wenn diese Option nicht angegeben ist, wird der Name des aktuellen Computers angenommen.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-147">If this option is not specified, the current computer name is assumed.</span></span>  
  
 <span data-ttu-id="fb3f7-148">**-d** _db_name_</span><span class="sxs-lookup"><span data-stu-id="fb3f7-148">**-d** _db_name_</span></span>  
 <span data-ttu-id="fb3f7-149">Gibt die USE *db_name* -Anweisung aus, wenn **osql**gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-149">Issues a USE *db_name* statement when **osql**is started.</span></span>  
  
 <span data-ttu-id="fb3f7-150">**-l** _time_out_</span><span class="sxs-lookup"><span data-stu-id="fb3f7-150">**-l** _time_out_</span></span>  
 <span data-ttu-id="fb3f7-151">Gibt an, nach wie vielen Sekunden ein Timeout bei der **osql** -Anmeldung auftritt. Der Standardwert für das Timeout bei einer **osql** -Anmeldung ist acht Sekunden.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-151">Specifies the number of seconds before an **osql** login times out. The default time-out for login to **osql** is eight seconds.</span></span>  
  
 <span data-ttu-id="fb3f7-152">**-t** _time_out_</span><span class="sxs-lookup"><span data-stu-id="fb3f7-152">**-t** _time_out_</span></span>  
 <span data-ttu-id="fb3f7-153">Gibt an, nach wie vielen Sekunden ein Befehl wegen eines Timeout abgebrochen wird. Wenn für *time_out* kein Wert angegeben wird, tritt für die Befehle kein Timeout ein.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-153">Specifies the number of seconds before a command times out. If a *time_out* value is not specified, commands do not time out.</span></span>  
  
 <span data-ttu-id="fb3f7-154">**-h** _headers_</span><span class="sxs-lookup"><span data-stu-id="fb3f7-154">**-h** _headers_</span></span>  
 <span data-ttu-id="fb3f7-155">Gibt die Anzahl der Zeilen an, die zwischen den Spaltenüberschriften gedruckt werden.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-155">Specifies the number of rows to print between column headings.</span></span> <span data-ttu-id="fb3f7-156">Standardmäßig werden die Überschriften für jedes Resultset der Abfrage einmal gedruckt.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-156">The default is to print headings one time for each set of query results.</span></span> <span data-ttu-id="fb3f7-157">Mit -1 können Sie angeben, dass keine Überschriften gedruckt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-157">Use -1 to specify that no headers will be printed.</span></span> <span data-ttu-id="fb3f7-158">Falls -1 verwendet wird, darf zwischen dem Parameter und der Einstellung kein Leerzeichen stehen ( **-h-1**und nicht **-h -1**).</span><span class="sxs-lookup"><span data-stu-id="fb3f7-158">If -1 is used, there must be no space between the parameter and the setting (**-h-1**, not **-h -1**).</span></span>  
  
 <span data-ttu-id="fb3f7-159">**-s** _col_separator_</span><span class="sxs-lookup"><span data-stu-id="fb3f7-159">**-s** _col_separator_</span></span>  
 <span data-ttu-id="fb3f7-160">Gibt das Spaltentrennzeichen an. Standardmäßig wird ein Leerzeichen verwendet.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-160">Specifies the column-separator character, which is a blank space by default.</span></span> <span data-ttu-id="fb3f7-161">Um Zeichen zu verwenden, die für das Betriebssystem eine besondere Bedeutung haben (z. b. |; & \< > ), müssen Sie das Zeichen in doppelte Anführungszeichen (") einschließen.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-161">To use characters that have special meaning to the operating system (for example, | ; & \< >), enclose the character in double quotation marks (").</span></span>  
  
 <span data-ttu-id="fb3f7-162">**-w** _column_width_</span><span class="sxs-lookup"><span data-stu-id="fb3f7-162">**-w** _column_width_</span></span>  
 <span data-ttu-id="fb3f7-163">Ermöglicht dem Benutzer, die Bildschirmbreite für die Ausgabe festzulegen.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-163">Allows the user to set the screen width for output.</span></span> <span data-ttu-id="fb3f7-164">Die Standardeinstellung ist 80 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-164">The default is 80 characters.</span></span> <span data-ttu-id="fb3f7-165">Wenn eine Ausgabezeile die maximale Bildschirmbreite erreicht hat, wird die Zeile umbrochen.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-165">When an output line has reached its maximum screen width, it is broken into multiple lines.</span></span>  
  
 <span data-ttu-id="fb3f7-166">**-a** _packet_size_</span><span class="sxs-lookup"><span data-stu-id="fb3f7-166">**-a** _packet_size_</span></span>  
 <span data-ttu-id="fb3f7-167">Ermöglicht es Ihnen, Pakete mit einer anderen Größe anzufordern.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-167">Allows you to request a different-sized packet.</span></span> <span data-ttu-id="fb3f7-168">Gültige Werte für *packet_size* sind 512 bis 65535.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-168">The valid values for *packet_size* are 512 through 65535.</span></span> <span data-ttu-id="fb3f7-169">Der Standardwert **osql** ist der Serverstandard.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-169">The default value **osql** is the server default.</span></span> <span data-ttu-id="fb3f7-170">Die gestiegene Paketgröße kann die Ausführung größerer Skripts verbessern, bei denen zwischen den GO-Befehlen eine erhebliche Menge an SQL-Anweisungen vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-170">Increased packet size can enhance performance on larger script execution where the amount of SQL statements between GO commands is substantial.</span></span> [!INCLUDE[msCoName](../includes/msconame-md.md)] <span data-ttu-id="fb3f7-171">-Tests geben an, dass 8192 in der Regel die schnellste Einstellung für Massenkopiervorgänge ist.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-171">testing indicates that 8192 is typically the fastest setting for bulk copy operations.</span></span> <span data-ttu-id="fb3f7-172">Eine größere Paketgröße kann angefordert werden; **osql** verwendet jedoch standardmäßig den Standardwert des Servers, wenn die Anforderung nicht gewährt werden kann.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-172">A larger packet size can be requested, but **osql** defaults to the server default if the request cannot be granted.</span></span>  
  
 <span data-ttu-id="fb3f7-173">**-e**</span><span class="sxs-lookup"><span data-stu-id="fb3f7-173">**-e**</span></span>  
 <span data-ttu-id="fb3f7-174">Bewirkt, dass die Eingabe auf dem Bildschirm angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-174">Echoes input.</span></span>  
  
 <span data-ttu-id="fb3f7-175">**-I**</span><span class="sxs-lookup"><span data-stu-id="fb3f7-175">**-I**</span></span>  
 <span data-ttu-id="fb3f7-176">Aktiviert die QUOTED_IDENTIFIER-Verbindungsoption.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-176">Sets the QUOTED_IDENTIFIER connection option on.</span></span>  
  
 <span data-ttu-id="fb3f7-177">**-D** _data_source_name_</span><span class="sxs-lookup"><span data-stu-id="fb3f7-177">**-D** _data_source_name_</span></span>  
 <span data-ttu-id="fb3f7-178">Stellt eine Verbindung mit einer ODBC-Datenquelle her, die so definiert ist, dass sie den ODBC-Treiber für [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]verwendet.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-178">Connects to an ODBC data source that is defined using the ODBC driver for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="fb3f7-179">Die **osql** -Verbindung verwendet die Optionen, die in der Datenquelle angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-179">The **osql** connection uses the options specified in the data source.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fb3f7-180">Diese Option kann nicht mit Datenquellen verwendet werden, die für andere Treiber definiert sind.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-180">This option does not work with data sources defined for other drivers.</span></span>  
  
 <span data-ttu-id="fb3f7-181">**-c** _cmd_end_</span><span class="sxs-lookup"><span data-stu-id="fb3f7-181">**-c** _cmd_end_</span></span>  
 <span data-ttu-id="fb3f7-182">Gibt das Befehlsabschlusszeichen an.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-182">Specifies the command terminator.</span></span> <span data-ttu-id="fb3f7-183">Standardmäßig werden Befehle abgeschlossen und an [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] gesendet, indem Sie GO in eine eigene Zeile eingeben.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-183">By default, commands are terminated and sent to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] by entering GO on a line by itself.</span></span> <span data-ttu-id="fb3f7-184">Wenn Sie das Befehlsabschlusszeichen neu festlegen, dürfen Sie keine für [!INCLUDE[tsql](../includes/tsql-md.md)] reservierten Wörter oder Zeichen verwenden, die eine spezielle Bedeutung für das Betriebssystem haben, unabhängig davon, ob vor einem Wort bzw. Zeichen ein umgekehrter Schrägstrich steht.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-184">When you reset the command terminator, do not use [!INCLUDE[tsql](../includes/tsql-md.md)] reserved words or characters that have special meaning to the operating system, whether preceded by a backslash or not.</span></span>  
  
 <span data-ttu-id="fb3f7-185">**-q "** _query_ **"**</span><span class="sxs-lookup"><span data-stu-id="fb3f7-185">**-q "** _query_ **"**</span></span>  
 <span data-ttu-id="fb3f7-186">Führt eine Abfrage aus, wenn **osql** startet, beendet **osql** aber nicht, nachdem die Abfrage abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-186">Executes a query when **osql** starts, but does not exit **osql** when the query completes.</span></span> <span data-ttu-id="fb3f7-187">(Beachten Sie, dass die Abfrageanweisung keinen GO-Befehl enthalten darf.)</span><span class="sxs-lookup"><span data-stu-id="fb3f7-187">(Note that the query statement should not include GO).</span></span> <span data-ttu-id="fb3f7-188">Wenn Sie eine Abfrage aus einer Batchdatei ausgeben, können Sie Variablen (%Variable) oder Umgebungsvariablen (%Umgebungsvariable%) verwenden.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-188">If you issue a query from a batch file, use %variables, or environment %variables%.</span></span> <span data-ttu-id="fb3f7-189">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="fb3f7-189">For example:</span></span>  
  
```  
SET table=sys.objects  
osql -E -q "select name, object_id from %table%"  
```  
  
 <span data-ttu-id="fb3f7-190">Schließen Sie die Abfrage in doppelte Anführungszeichen und alle Elemente, die in die Abfrage eingebettet sind, in einfache Anführungszeichen ein.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-190">Use double quotation marks around the query and single quotation marks around anything embedded in the query.</span></span>  
  
 <span data-ttu-id="fb3f7-191">**-Q"** _query_ **"**</span><span class="sxs-lookup"><span data-stu-id="fb3f7-191">**-Q"** _query_ **"**</span></span>  
 <span data-ttu-id="fb3f7-192">Führt eine Abfrage aus und beendet **osql**sofort.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-192">Executes a query and immediately exits **osql**.</span></span> <span data-ttu-id="fb3f7-193">Schließen Sie die Abfrage in doppelte Anführungszeichen und alle Elemente, die in die Abfrage eingebettet sind, in einfache Anführungszeichen ein.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-193">Use double quotation marks around the query and single quotation marks around anything embedded in the query.</span></span>  
  
 <span data-ttu-id="fb3f7-194">**-n**</span><span class="sxs-lookup"><span data-stu-id="fb3f7-194">**-n**</span></span>  
 <span data-ttu-id="fb3f7-195">Entfernt die Nummerierung und das Symbol für die Eingabeaufforderung (>) aus den Eingabezeilen.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-195">Removes numbering and the prompt symbol (>) from input lines.</span></span>  
  
 <span data-ttu-id="fb3f7-196">**-m** _error_level_</span><span class="sxs-lookup"><span data-stu-id="fb3f7-196">**-m** _error_level_</span></span>  
 <span data-ttu-id="fb3f7-197">Passt die Anzeige der Fehlermeldungen an.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-197">Customizes the display of error messages.</span></span> <span data-ttu-id="fb3f7-198">Für jeden Fehler mit dem angegebenen oder einem höheren Schweregrad wird die Meldungsnummer, der Status und der Fehlergrad angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-198">The message number, state, and error level are displayed for errors of the specified severity level or higher.</span></span> <span data-ttu-id="fb3f7-199">Für Fehler mit einem niedrigeren ist als dem angegebenen Schweregrad wird nichts angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-199">Nothing is displayed for errors of levels lower than the specified level.</span></span> <span data-ttu-id="fb3f7-200">Mit **-1** können Sie angeben, dass alle Header mit Meldungen zurückgegeben werden. Dies gilt auch für Informationsmeldungen.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-200">Use **-1** to specify that all headers are returned with messages, even informational messages.</span></span> <span data-ttu-id="fb3f7-201">Falls Sie **-1**verwenden, darf kein Leerzeichen zwischen dem Parameter und der Einstellung stehen ( **-m-1**und nicht **-m -1**).</span><span class="sxs-lookup"><span data-stu-id="fb3f7-201">If using **-1**, there must be no space between the parameter and the setting (**-m-1**, not **-m -1**).</span></span>  
  
 <span data-ttu-id="fb3f7-202">**-r** { **0**| **1**}</span><span class="sxs-lookup"><span data-stu-id="fb3f7-202">**-r** { **0**| **1**}</span></span>  
 <span data-ttu-id="fb3f7-203">Leitet die Meldungsausgabe auf den Bildschirm um (**stderr**).</span><span class="sxs-lookup"><span data-stu-id="fb3f7-203">Redirects message output to the screen (**stderr**).</span></span> <span data-ttu-id="fb3f7-204">Wenn Sie keinen Parameter oder **0**angeben, werden nur Fehlermeldungen umgeleitet, deren Schweregrad 11 oder höher ist.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-204">If you do not specify a parameter, or if you specify **0**, only error messages with a severity level 11 or higher are redirected.</span></span> <span data-ttu-id="fb3f7-205">Wenn Sie **1**angeben, werden alle Meldungsausgaben (einschließlich der Ausgabe von "print") umgeleitet.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-205">If you specify **1**, all message output (including "print") is redirected.</span></span>  
  
 <span data-ttu-id="fb3f7-206">**-i** _input_file_</span><span class="sxs-lookup"><span data-stu-id="fb3f7-206">**-i** _input_file_</span></span>  
 <span data-ttu-id="fb3f7-207">Identifiziert die Datei, die einen Batch mit SQL-Anweisungen oder gespeicherten Prozeduren enthält.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-207">Identifies the file that contains a batch of SQL statements or stored procedures.</span></span> <span data-ttu-id="fb3f7-208">Anstelle von **\<** -i **kann der Kleiner-als-Vergleichsoperator (** ) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-208">The less than (**\<**) comparison operator can be used in place of **-i**.</span></span>  
  
 <span data-ttu-id="fb3f7-209">**-o** _output_file_</span><span class="sxs-lookup"><span data-stu-id="fb3f7-209">**-o** _output_file_</span></span>  
 <span data-ttu-id="fb3f7-210">Identifiziert die Datei, die die Ausgabe von **osql**erhält.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-210">Identifies the file that receives output from **osql**.</span></span> <span data-ttu-id="fb3f7-211">Anstelle von **>** -o **kann der Größer-als-Vergleichsoperator (** ) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-211">The greater than (**>**) comparison operator can be used in place of **-o**.</span></span>  
  
 <span data-ttu-id="fb3f7-212">Falls *input_file* nicht im Unicode-Format vorliegt und **-u** nicht angegeben ist, wird *output_file* im OEM-Format gespeichert.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-212">If *input_file* is not Unicode and **-u** is not specified, *output_file* is stored in OEM format.</span></span> <span data-ttu-id="fb3f7-213">Falls *input_file* im Unicode-Format vorliegt oder **-u** angegeben ist, wird *output_file* im Unicode-Format gespeichert.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-213">If *input_file* is Unicode or **-u** is specified, *output_file* is stored in Unicode format.</span></span>  
  
 <span data-ttu-id="fb3f7-214">**-p**</span><span class="sxs-lookup"><span data-stu-id="fb3f7-214">**-p**</span></span>  
 <span data-ttu-id="fb3f7-215">Druckt die Leistungsstatistik.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-215">Prints performance statistics.</span></span>  
  
 <span data-ttu-id="fb3f7-216">**-b**</span><span class="sxs-lookup"><span data-stu-id="fb3f7-216">**-b**</span></span>  
 <span data-ttu-id="fb3f7-217">Gibt an, dass **osql** beendet und ein DOS ERRORLEVEL-Wert zurückgegeben wird, wenn ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-217">Specifies that **osql** exits and returns a DOS ERRORLEVEL value when an error occurs.</span></span> <span data-ttu-id="fb3f7-218">Für die DOS ERRORLEVEL-Variable wird der Wert 1 zurückgegeben, wenn der Schweregrad der [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Fehlermeldung 11 oder größer ist. Andernfalls wird der Wert 0 zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-218">The value returned to the DOS ERRORLEVEL variable is 1 when the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] error message has a severity of 11 or greater; otherwise, the value returned is 0.</span></span> [!INCLUDE[msCoName](../includes/msconame-md.md)] <span data-ttu-id="fb3f7-219">MS-DOS-Batchdateien können verwendet werden, um den Wert von DOS ERRORLEVEL zu testen und den Fehler entsprechend zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-219">MS-DOS batch files can test the value of DOS ERRORLEVEL and handle the error appropriately.</span></span>  
  
 <span data-ttu-id="fb3f7-220">**-u**</span><span class="sxs-lookup"><span data-stu-id="fb3f7-220">**-u**</span></span>  
 <span data-ttu-id="fb3f7-221">Gibt an, dass *output_file* unabhängig vom Format von *input_file*im Unicode-Format gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-221">Specifies that *output_file* is stored in Unicode format, regardless of the format of the *input_file*.</span></span>  
  
 <span data-ttu-id="fb3f7-222">**-R**</span><span class="sxs-lookup"><span data-stu-id="fb3f7-222">**-R**</span></span>  
 <span data-ttu-id="fb3f7-223">Gibt an, dass der [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -ODBC-Treiber Clienteinstellungen verwendet, wenn Währungs-, Datums- oder Zeitdaten in Zeichendaten konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-223">Specifies that the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ODBC driver use client settings when converting currency, date, and time data to character data.</span></span>  
  
 <span data-ttu-id="fb3f7-224">**-O**</span><span class="sxs-lookup"><span data-stu-id="fb3f7-224">**-O**</span></span>  
 <span data-ttu-id="fb3f7-225">Gibt an, dass bestimmte **osql** -Funktionen deaktiviert werden, um eine Übereinstimmung mit dem Verhalten früherer **isql**-Versionen zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-225">Specifies that certain **osql** features be deactivated to match the behavior of earlier versions of **isql**.</span></span> <span data-ttu-id="fb3f7-226">Die folgenden Funktionen werden deaktiviert:</span><span class="sxs-lookup"><span data-stu-id="fb3f7-226">These features are deactivated:</span></span>  
  
-   <span data-ttu-id="fb3f7-227">EOF-Batchverarbeitung</span><span class="sxs-lookup"><span data-stu-id="fb3f7-227">EOF batch processing</span></span>  
  
-   <span data-ttu-id="fb3f7-228">Automatisches Skalieren der Konsolenbreite</span><span class="sxs-lookup"><span data-stu-id="fb3f7-228">Automatic console width scaling</span></span>  
  
-   <span data-ttu-id="fb3f7-229">Ausführliche Meldungen</span><span class="sxs-lookup"><span data-stu-id="fb3f7-229">Wide messages</span></span>  
  
 <span data-ttu-id="fb3f7-230">Außerdem wird der Standardwert von DOS ERRORLEVEL auf -1 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-230">It also sets the default DOS ERRORLEVEL value to -1.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fb3f7-231">Die Optionen **-n**, **-O** und **-D** werden von **osql**nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-231">The **-n**, **-O** and **-D** options are no longer supported by **osql**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fb3f7-232">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="fb3f7-232">Remarks</span></span>  
 <span data-ttu-id="fb3f7-233">Das Hilfsprogramm **osql** wird direkt vom Betriebssystem aus mit den hier aufgelisteten Optionen gestartet, wobei bei den Optionen zwischen Groß- und Kleinschreibung unterschieden wird.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-233">The **osql** utility is started directly from the operating system with the case-sensitive options listed here.</span></span> <span data-ttu-id="fb3f7-234">Nachdem **osql**gestartet wurde, akzeptiert das Hilfsprogramm SQL-Anweisungen und sendet diese interaktiv an [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fb3f7-234">After **osql**starts, it accepts SQL statements and sends them to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] interactively.</span></span> <span data-ttu-id="fb3f7-235">Die Ergebnisse werden formatiert und auf dem Bildschirm angezeigt (**stdout**).</span><span class="sxs-lookup"><span data-stu-id="fb3f7-235">The results are formatted and displayed on the screen (**stdout**).</span></span> <span data-ttu-id="fb3f7-236">Verwenden Sie QUIT oder EXIT zum Beenden von **osql**.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-236">Use QUIT or EXIT to exit from **osql**.</span></span>  
  
 <span data-ttu-id="fb3f7-237">Wenn Sie beim Starten von **osql**keinen Benutzernamen angeben, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] überprüft die Umgebungsvariablen und verwendet diese, z.b. **OSQLUSER = ( *`user`* )** oder **osqlserver = ( *`server`* )**.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-237">If you do not specify a user name when you start **osql**, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] checks for the environment variables and uses those, for example, **osqluser=(*`user`*)** or **osqlserver=(*`server`*)**.</span></span> <span data-ttu-id="fb3f7-238">Wenn keine Umgebungsvariablen festgelegt sind, wird der Benutzername der Arbeitsstation verwendet.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-238">If no environment variables are set, the workstation user name is used.</span></span> <span data-ttu-id="fb3f7-239">Wenn Sie keinen Server angeben, wird der Name der Arbeitsstation verwendet.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-239">If you do not specify a server, the name of the workstation is used.</span></span>  
  
 <span data-ttu-id="fb3f7-240">Falls weder die Option **-U** noch die Option **-P** verwendet wird, versucht [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , die Verbindung mithilfe des [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows-Authentifizierungsmodus herzustellen.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-240">If neither the **-U** or **-P** options are used, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] attempts to connect using [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows Authentication Mode.</span></span> <span data-ttu-id="fb3f7-241">Die Authentifizierung basiert auf dem [!INCLUDE[msCoName](../includes/msconame-md.md)] -Windows-Konto des Benutzers, der **osql**ausführt.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-241">Authentication is based on the [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows account of the user running **osql**.</span></span>  
  
 <span data-ttu-id="fb3f7-242">Das Hilfsprogramm **osql** verwendet die ODBC-API.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-242">The **osql** utility uses the ODBC API.</span></span> <span data-ttu-id="fb3f7-243">Das Hilfsprogramm verwendet die Standardeinstellungen des [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -ODBC-Treibers für die ISO-Verbindungsoptionen in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fb3f7-243">The utility uses the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ODBC driver default settings for the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ISO connection options.</span></span> <span data-ttu-id="fb3f7-244">Weitere Informationen finden Sie im Thema zu den Effekten der ANSI-Optionen.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-244">For more information, see Effects of ANSI Options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fb3f7-245">Das Hilfsprogramm **osql** bietet keine Unterstützung für benutzerdefinierte CLR-Datentypen.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-245">The **osql** utility does not support CLR user-defined data types.</span></span> <span data-ttu-id="fb3f7-246">Zum Verarbeiten dieser Datentypen müssen Sie das Hilfsprogramm **sqlcmd** verwenden.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-246">To process these data types, you must use the **sqlcmd** utility.</span></span> <span data-ttu-id="fb3f7-247">Weitere Informationen finden Sie unter [sqlcmd Utility](sqlcmd-utility.md).</span><span class="sxs-lookup"><span data-stu-id="fb3f7-247">For more information, see [sqlcmd Utility](sqlcmd-utility.md).</span></span>  
  
## <a name="osql-commands"></a><span data-ttu-id="fb3f7-248">OSQL-Befehle</span><span class="sxs-lookup"><span data-stu-id="fb3f7-248">OSQL Commands</span></span>  
 <span data-ttu-id="fb3f7-249">Zusätzlich zu den [!INCLUDE[tsql](../includes/tsql-md.md)] -Anweisungen in **osql**, sind auch die folgenden Befehle verfügbar.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-249">In addition to [!INCLUDE[tsql](../includes/tsql-md.md)] statements within **osql**, these commands are also available.</span></span>  
  
|<span data-ttu-id="fb3f7-250">Get-Help</span><span class="sxs-lookup"><span data-stu-id="fb3f7-250">Command</span></span>|<span data-ttu-id="fb3f7-251">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="fb3f7-251">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fb3f7-252">GO</span><span class="sxs-lookup"><span data-stu-id="fb3f7-252">GO</span></span>|<span data-ttu-id="fb3f7-253">Führt alle Anweisungen aus, die nach dem letzten GO-Befehl eingegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-253">Executes all statements entered after the last GO.</span></span>|  
|<span data-ttu-id="fb3f7-254">RESET</span><span class="sxs-lookup"><span data-stu-id="fb3f7-254">RESET</span></span>|<span data-ttu-id="fb3f7-255">Löscht alle Anweisungen, die Sie eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-255">Clears any statements you have entered.</span></span>|  
|<span data-ttu-id="fb3f7-256">QUIT oder EXIT( )</span><span class="sxs-lookup"><span data-stu-id="fb3f7-256">QUIT or EXIT( )</span></span>|<span data-ttu-id="fb3f7-257">Beendet **osql**.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-257">Exits from **osql**.</span></span>|  
|<span data-ttu-id="fb3f7-258">STRG+C</span><span class="sxs-lookup"><span data-stu-id="fb3f7-258">CTRL+C</span></span>|<span data-ttu-id="fb3f7-259">Beendet eine Abfrage, ohne **osql**zu beenden.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-259">Ends a query without exiting from **osql**.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="fb3f7-260">Die Befehle !!</span><span class="sxs-lookup"><span data-stu-id="fb3f7-260">The !!</span></span> <span data-ttu-id="fb3f7-261">und ED werden von **osql**nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-261">and ED commands are no longer supported by **osql**.</span></span>  
  
 <span data-ttu-id="fb3f7-262">Die Befehlsabschlusszeichen GO (Standard), RESET EXIT, QUIT und STRG+C werden nur erkannt, wenn sie am Anfang einer Zeile unmittelbar hinter der **osql** -Eingabeaufforderung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-262">The command terminators GO (by default), RESET EXIT, QUIT, and CTRL+C, are recognized only if they appear at the beginning of a line, immediately following the **osql** prompt.</span></span>  
  
 <span data-ttu-id="fb3f7-263">GO signalisiert sowohl das Ende eines Batches als auch die Ausführung aller zwischengespeicherten [!INCLUDE[tsql](../includes/tsql-md.md)] -Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-263">GO signals both the end of a batch and the execution of any cached [!INCLUDE[tsql](../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="fb3f7-264">Sobald Sie am Ende einer Eingabezeile die EINGABETASTE drücken, werden die Anweisungen in dieser Zeile von **osql** zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-264">When you press ENTER at the end of each input line, **osql** caches the statements on that line.</span></span> <span data-ttu-id="fb3f7-265">Wenn Sie nach dem Eingeben von GO die EINGABETASTE drücken, werden alle zurzeit zwischengespeicherten Anweisungen als Batch an [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]gesendet.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-265">When you press ENTER after typing GO, all of the currently cached statements are sent as a batch to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="fb3f7-266">Die aktuelle Version des Hilfsprogramms **osql** arbeitet so, als würde sich am Ende jedes ausgeführten Skripts ein impliziter GO-Befehl befinden. Daher werden alle Anweisungen im Skript ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-266">The current **osql** utility works as if there is an implied GO at the end of any script executed, therefore all statements in the script execute.</span></span>  
  
 <span data-ttu-id="fb3f7-267">Beenden Sie einen Befehl, indem Sie eine Zeile eingeben, die mit einem Befehlsabschlusszeichen beginnt.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-267">End a command by typing a line beginning with a command terminator.</span></span> <span data-ttu-id="fb3f7-268">Durch das Eingeben einer ganzen Zahl hinter einem Befehlsabschlusszeichen können Sie angeben, wie oft der Befehl ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-268">You can follow the command terminator with an integer to specify how many times the command should be run.</span></span> <span data-ttu-id="fb3f7-269">Wenn Sie diesen Befehl z. B. 100-mal ausführen möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="fb3f7-269">For example, to execute this command 100 times, type:</span></span>  
  
```  
SELECT x = 1  
GO 100  
```  
  
 <span data-ttu-id="fb3f7-270">Die Ergebnisse werden einmal am Ende der Ausführung ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-270">The results are printed once at the end of execution.</span></span> <span data-ttu-id="fb3f7-271">**osql** akzeptiert nicht mehr als 1.000 Zeichen pro Zeile.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-271">**osql** does not accept more than 1,000 characters per line.</span></span> <span data-ttu-id="fb3f7-272">Umfangreiche Anweisungen sollten auf mehrere Zeilen verteilt werden.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-272">Large statements should be spread across multiple lines.</span></span>  
  
 <span data-ttu-id="fb3f7-273">Mithilfe der Befehlsrückruffunktionen von Windows können **osql** -Anweisungen zurückgerufen und geändert werden.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-273">The command recall facilities of Windows can be used to recall and modify **osql** statements.</span></span> <span data-ttu-id="fb3f7-274">Der vorhandene Abfragepuffer kann durch das Eingeben von RESET geleert werden.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-274">The existing query buffer can be cleared by typing RESET.</span></span>  
  
 <span data-ttu-id="fb3f7-275">Wenn gespeicherte Prozeduren ausgeführt werden, gibt **osql** eine Leerzeile zwischen den einzelnen Resultsets in einem Batch aus.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-275">When running stored procedures, **osql** prints a blank line between each set of results in a batch.</span></span> <span data-ttu-id="fb3f7-276">Außerdem wird die Meldung "0 Zeilen betroffen" nicht angezeigt, wenn sie für die ausgeführte Anweisung nicht gilt.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-276">In addition, the "0 rows affected" message does not appear when it does not apply to the statement executed.</span></span>  
  
## <a name="using-osql-interactively"></a><span data-ttu-id="fb3f7-277">Interaktives Verwenden von osql</span><span class="sxs-lookup"><span data-stu-id="fb3f7-277">Using osql Interactively</span></span>  
 <span data-ttu-id="fb3f7-278">Wenn Sie **osql** interaktiv verwenden möchten, geben Sie an der Eingabeaufforderung den Befehl **osql** (und alle darüber hinaus gewünschten Optionen) ein.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-278">To use **osql** interactively, type the **osql** command (and any of the options) at a command prompt.</span></span>  
  
 <span data-ttu-id="fb3f7-279">Sie können eine Datei einlesen, die eine Abfrage enthält (wie z.B. „Stores.qry“), die von **osql** ausgeführt werden soll, indem Sie in etwa folgenden Befehl eingeben:</span><span class="sxs-lookup"><span data-stu-id="fb3f7-279">You can read in a file containing a query (such as Stores.qry) for execution by **osql** by typing a command similar to this:</span></span>  
  
```  
osql -E -i stores.qry  
```  
  
 <span data-ttu-id="fb3f7-280">Sie können eine Datei mit einer Abfrage (z. B. Titles.qry) einlesen und die Ergebnisse in eine andere Datei umleiten, indem Sie einen Befehl eingeben, der in etwa wie folgt aussieht:</span><span class="sxs-lookup"><span data-stu-id="fb3f7-280">You can read in a file containing a query (such as Titles.qry) and direct the results to another file by typing a command similar to this:</span></span>  
  
```  
osql -E -i titles.qry -o titles.res  
```  
  
> [!IMPORTANT]  
>  <span data-ttu-id="fb3f7-281">Verwenden Sie, sofern möglich, die Option **-E**(vertrauenswürdige Verbindung).</span><span class="sxs-lookup"><span data-stu-id="fb3f7-281">When possible, use the **-E**option (trusted connection).</span></span>  
  
 <span data-ttu-id="fb3f7-282">Wenn Sie **osql** interaktiv verwenden, können Sie eine Betriebssystem Datei mit dem folgenden Befehl in den Befehls Puffer einlesen **: r**_file_name_.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-282">When using **osql** interactively, you can read an operating-system file into the command buffer with **:r**_file_name_.</span></span> <span data-ttu-id="fb3f7-283">Hierdurch wird das in *file_name* angegebene SQL-Skript direkt als ein einziger Batch an den Server gesendet.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-283">This sends the SQL script in *file_name* directly to the server as a single batch.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fb3f7-284">Wenn Sie **osql**verwenden, behandelt [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] das Batchtrennzeichen GO als Syntaxfehler, falls es in einer SQL-Skriptdatei verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-284">When using **osql**, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] treats the batch separator GO, if it appears in a SQL script file, as a syntax error.</span></span>  
  
## <a name="inserting-comments"></a><span data-ttu-id="fb3f7-285">Einfügen von Kommentaren</span><span class="sxs-lookup"><span data-stu-id="fb3f7-285">Inserting Comments</span></span>  
 <span data-ttu-id="fb3f7-286">Sie können Kommentare in eine Transact-SQL-Anweisung einschließen, die von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] osql **an**gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-286">You can include comments in a Transact-SQL statement submitted to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] by **osql**.</span></span> <span data-ttu-id="fb3f7-287">Für Kommentare sind die beiden folgenden Formate zulässig: -- und /\*...\*/.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-287">Two types of commenting styles are allowed: -- and /\*...\*/.</span></span>  
  
## <a name="using-exit-to-return-results-in-osql"></a><span data-ttu-id="fb3f7-288">Verwenden von EXIT zum Zurückgeben von Ergebnissen in "osql"</span><span class="sxs-lookup"><span data-stu-id="fb3f7-288">Using EXIT to Return Results in osql</span></span>  
 <span data-ttu-id="fb3f7-289">Sie können das Ergebnis einer SELECT-Anweisung als Rückgabewert von **osql**verwenden.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-289">You can use the result of a SELECT statement as the return value from **osql**.</span></span> <span data-ttu-id="fb3f7-290">Wenn numerisch, wird die letzte Spalte der letzten Ergebniszeile in eine 4 Byte lange ganze Zahl (Long) konvertiert.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-290">If it is numeric, the last column of the last result row is converted to a 4-byte integer (long).</span></span> <span data-ttu-id="fb3f7-291">MS-DOS übergibt das niedrige Byte an den übergeordneten Prozess oder an die Fehlerebene des Betriebssystems.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-291">MS-DOS passes the low byte to the parent process or operating system error level.</span></span> <span data-ttu-id="fb3f7-292">Windows übergibt die gesamte 4 Byte lange ganze Zahl.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-292">Windows passes the entire 4-byte integer.</span></span> <span data-ttu-id="fb3f7-293">Die Syntax ist:</span><span class="sxs-lookup"><span data-stu-id="fb3f7-293">The syntax is:</span></span>  
  
```  
EXIT ( < query > )  
```  
  
 <span data-ttu-id="fb3f7-294">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="fb3f7-294">For example:</span></span>  
  
```  
EXIT(SELECT @@ROWCOUNT)  
```  
  
 <span data-ttu-id="fb3f7-295">Sie können den EXIT-Parameter auch als Teil einer Batchdatei einschließen.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-295">You can also include the EXIT parameter as part of a batch file.</span></span> <span data-ttu-id="fb3f7-296">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="fb3f7-296">For example:</span></span>  
  
```  
osql -E -Q "EXIT(SELECT COUNT(*) FROM '%1')"  
```  
  
 <span data-ttu-id="fb3f7-297">Das Hilfsprogramm **osql** übergibt alle zwischen den Klammern **( )** stehenden Zeichen exakt so an den Server, wie sie eingegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-297">The **osql** utility passes everything between the parentheses **()** to the server exactly as entered.</span></span> <span data-ttu-id="fb3f7-298">Wenn eine gespeicherte Systemprozedur eine Menge auswählt und einen Wert zurückgibt, wird nur die Auswahl zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-298">If a stored system procedure selects a set and returns a value, only the selection is returned.</span></span> <span data-ttu-id="fb3f7-299">Eine EXIT **()** -Anweisung ohne Angabe zwischen den Klammern führt alle im Batch vorhergehenden Anweisungen aus und beendet das Hilfsprogramm dann ohne Rückgabewert.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-299">The EXIT **()** statement with nothing between the parentheses executes everything preceding it in the batch and then exits with no return value.</span></span>  
  
 <span data-ttu-id="fb3f7-300">Es gibt vier EXIT-Formate:</span><span class="sxs-lookup"><span data-stu-id="fb3f7-300">There are four EXIT formats:</span></span>  
  
-   <span data-ttu-id="fb3f7-301">EXIT</span><span class="sxs-lookup"><span data-stu-id="fb3f7-301">EXIT</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fb3f7-302">Führt den Batch nicht aus, beendet das Hilfsprogramm sofort und gibt keinen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-302">Does not execute the batch; quits immediately and returns no value.</span></span>  
  
-   <span data-ttu-id="fb3f7-303">EXIT **()**</span><span class="sxs-lookup"><span data-stu-id="fb3f7-303">EXIT **()**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fb3f7-304">Führt den Batch aus, beendet dann das Hilfsprogramm und gibt keinen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-304">Executes the batch, and then quits and returns no value.</span></span>  
  
-   <span data-ttu-id="fb3f7-305">Exit **( *`query`* )**</span><span class="sxs-lookup"><span data-stu-id="fb3f7-305">EXIT **(*`query`*)**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fb3f7-306">Führt den Batch einschließlich der Abfrage aus und beendet dann das Hilfsprogramm, nachdem die Ergebnisse der Abfrage zurückgegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-306">Executes the batch, including the query, and then quits after returning the results of the query.</span></span>  
  
-   <span data-ttu-id="fb3f7-307">RAISERROR mit einem Status von 127</span><span class="sxs-lookup"><span data-stu-id="fb3f7-307">RAISERROR with a state of 127</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fb3f7-308">Falls RAISERROR in einem **osql** -Skript verwendet wird, und der Status 127 ausgelöst wird, wird **osql** beendet und gibt die Meldungs-ID an den Client zurück.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-308">If RAISERROR is used within an **osql** script and a state of 127 is raised, **osql** will quit and return the message ID back to the client.</span></span> <span data-ttu-id="fb3f7-309">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="fb3f7-309">For example:</span></span>  
  
```  
RAISERROR(50001, 10, 127)  
```  
  
 <span data-ttu-id="fb3f7-310">Dieser Fehler bewirkt, dass das **osql** -Skript beendet und die Meldungs-ID 50001 an den Client zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-310">This error will cause the **osql** script to end and the message ID 50001 will be returned to the client.</span></span>  
  
 <span data-ttu-id="fb3f7-311">Die Rückgabewerte -1 bis -99 sind von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]reserviert; **osql** definiert die folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="fb3f7-311">The return values -1 to -99 are reserved by [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]; **osql** defines these values:</span></span>  
  
-   <span data-ttu-id="fb3f7-312">-100</span><span class="sxs-lookup"><span data-stu-id="fb3f7-312">-100</span></span>  
  
     <span data-ttu-id="fb3f7-313">Vor dem Auswählen des Rückgabewerts ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-313">Error encountered prior to selecting return value.</span></span>  
  
-   <span data-ttu-id="fb3f7-314">-101</span><span class="sxs-lookup"><span data-stu-id="fb3f7-314">-101</span></span>  
  
     <span data-ttu-id="fb3f7-315">Beim Auswählen eines Rückgabewerts wurden keine Zeilen gefunden.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-315">No rows found when selecting return value.</span></span>  
  
-   <span data-ttu-id="fb3f7-316">-102</span><span class="sxs-lookup"><span data-stu-id="fb3f7-316">-102</span></span>  
  
     <span data-ttu-id="fb3f7-317">Beim Auswählen des Rückgabewerts ist ein Konvertierungsfehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-317">Conversion error occurred when selecting return value.</span></span>  
  
## <a name="displaying-money-and-smallmoney-data-types"></a><span data-ttu-id="fb3f7-318">Anzeigen der Datentypen money und smallmoney</span><span class="sxs-lookup"><span data-stu-id="fb3f7-318">Displaying money and smallmoney Data Types</span></span>  
 <span data-ttu-id="fb3f7-319">**osql** zeigt den `money` - `smallmoney` Datentyp und den-Datentyp mit zwei Dezimalstellen an, obwohl [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] den Wert intern mit vier Dezimalstellen speichert.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-319">**osql** displays the `money` and `smallmoney` data types with two decimal places although [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] stores the value internally with four decimal places.</span></span> <span data-ttu-id="fb3f7-320">Beachten Sie folgendes Beispiel:</span><span class="sxs-lookup"><span data-stu-id="fb3f7-320">Consider the example:</span></span>  
  
```  
SELECT CAST(CAST(10.3496 AS money) AS decimal(6, 4))  
GO  
```  
  
 <span data-ttu-id="fb3f7-321">Diese Anweisung gibt als Ergebnis `10.3496`zurück. Dieses Ergebnis zeigt an, dass der Wert mit allen unveränderten Dezimalstellen gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="fb3f7-321">This statement produces a result of `10.3496`, which indicates that the value is stored with all decimal places intact.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb3f7-322">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fb3f7-322">See Also</span></span>  
 <span data-ttu-id="fb3f7-323">[Kommentar &#40;MDX&#41;](/sql/mdx/comment-mdx) </span><span class="sxs-lookup"><span data-stu-id="fb3f7-323">[Comment &#40;MDX&#41;](/sql/mdx/comment-mdx) </span></span>  
 <span data-ttu-id="fb3f7-324">[-- &#40;Kommentar&#41; &#40;MDX&#41;](/sql/mdx/comment-mdx) </span><span class="sxs-lookup"><span data-stu-id="fb3f7-324">[-- &#40;Comment&#41; &#40;MDX&#41;](/sql/mdx/comment-mdx) </span></span>  
 <span data-ttu-id="fb3f7-325">[CAST und CONVERT &#40;Transact-SQL&#41;](/sql/t-sql/functions/cast-and-convert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fb3f7-325">[CAST and CONVERT &#40;Transact-SQL&#41;](/sql/t-sql/functions/cast-and-convert-transact-sql) </span></span>  
 [<span data-ttu-id="fb3f7-326">RAISERROR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="fb3f7-326">RAISERROR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/raiserror-transact-sql)  
  
  
