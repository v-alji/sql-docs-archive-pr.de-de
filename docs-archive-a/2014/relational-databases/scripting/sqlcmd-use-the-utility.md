---
title: Verwenden des Hilfsprogramms sqlcmd
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- Transact-SQL statements, executing
- command prompt utilities [SQL Server], sqlcmd
- statements [SQL Server], executing
- sqlcmd utility, about sqlcmd utility
ms.assetid: 3ec89119-7314-43ef-9e91-12e72bb63d62
author: rothja
ms.author: jroth
ms.openlocfilehash: 922f9915272fb2d7fc63487ec135ce44ee91e88b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620261"
---
# <a name="use-the-sqlcmd-utility"></a><span data-ttu-id="45521-102">Verwenden des Hilfsprogramms sqlcmd</span><span class="sxs-lookup"><span data-stu-id="45521-102">Use the sqlcmd Utility</span></span>
  <span data-ttu-id="45521-103">Das Hilfsprogramm `sqlcmd` ist ein Befehlszeilen-Hilfsprogramm für die interaktive Ad-hoc-Ausführung von [!INCLUDE[tsql](../../includes/tsql-md.md)]-Anweisungen und -Skripts und die Automatisierung von [!INCLUDE[tsql](../../includes/tsql-md.md)]-Skripttasks.</span><span class="sxs-lookup"><span data-stu-id="45521-103">The `sqlcmd` utility is a command-line utility for ad hoc, interactive execution of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and scripts and for automating [!INCLUDE[tsql](../../includes/tsql-md.md)] scripting tasks.</span></span> <span data-ttu-id="45521-104">Damit Sie `sqlcmd` interaktiv verwenden oder Skriptdateien aufbauen können, die mithilfe von `sqlcmd` ausgeführt werden, müssen Sie mit den Grundlagen von [!INCLUDE[tsql](../../includes/tsql-md.md)] vertraut sein.</span><span class="sxs-lookup"><span data-stu-id="45521-104">To use `sqlcmd` interactively, or to build script files to be run using `sqlcmd`, users must understand [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="45521-105">Das Hilfsprogramm `sqlcmd` wird in der Regel wie folgt verwendet:</span><span class="sxs-lookup"><span data-stu-id="45521-105">The `sqlcmd` utility is typically used in the following ways:</span></span>  
  
-   <span data-ttu-id="45521-106">Der Benutzer gibt [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen ähnlich wie bei der Arbeit an der Eingabeaufforderung interaktiv ein.</span><span class="sxs-lookup"><span data-stu-id="45521-106">Users interactively enter [!INCLUDE[tsql](../../includes/tsql-md.md)] statements in a manner similar to working at the command prompt.</span></span> <span data-ttu-id="45521-107">Die Ergebnisse werden an der Eingabeaufforderung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="45521-107">The results are displayed at the command prompt.</span></span> <span data-ttu-id="45521-108">Klicken Sie auf **Start**, **Alle Programme**, zeigen Sie auf **Zubehör**, und klicken Sie dann auf **Eingabeaufforderung**, um das Eingabeaufforderungsfenster zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="45521-108">To open a Command Prompt window, click **Start**, click **All Programs**, point to **Accessories**, and then click **Command Prompt**.</span></span> <span data-ttu-id="45521-109">Geben Sie an der Eingabeaufforderung `sqlcmd` ein, gefolgt von einer Liste der gewünschten Optionen.</span><span class="sxs-lookup"><span data-stu-id="45521-109">At the command prompt, type `sqlcmd` followed by a list of options that you want.</span></span> <span data-ttu-id="45521-110">Eine umfassende Liste der Optionen, die von unterstützt werden `sqlcmd` , finden Sie unter [sqlcmd Utility](../../tools/sqlcmd-utility.md).</span><span class="sxs-lookup"><span data-stu-id="45521-110">For a complete list of the options that are supported by `sqlcmd`, see [sqlcmd Utility](../../tools/sqlcmd-utility.md).</span></span>  
  
-   <span data-ttu-id="45521-111">Der Benutzer sendet einen `sqlcmd`-Auftrag entweder durch Angeben einer einzelnen auszuführenden [!INCLUDE[tsql](../../includes/tsql-md.md)]-Anweisung oder durch Verweisen auf eine Textdatei, in der die auszuführenden [!INCLUDE[tsql](../../includes/tsql-md.md)]-Anweisungen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="45521-111">Users submit a `sqlcmd` job either by specifying a single [!INCLUDE[tsql](../../includes/tsql-md.md)] statement to execute, or by pointing the utility to a text file that contains [!INCLUDE[tsql](../../includes/tsql-md.md)] statements to execute.</span></span> <span data-ttu-id="45521-112">Die Ausgabe wird normalerweise in einer Textdatei gespeichert, sie kann jedoch auch an der Eingabeaufforderung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="45521-112">The output is usually directed to a text file, but it can also be displayed at the command prompt.</span></span>  
  
-   <span data-ttu-id="45521-113">[SQLCMD-Modus](edit-sqlcmd-scripts-with-query-editor.md) im [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] -Abfrage-Editor.</span><span class="sxs-lookup"><span data-stu-id="45521-113">[SQLCMD mode](edit-sqlcmd-scripts-with-query-editor.md) in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor.</span></span>  
  
-   <span data-ttu-id="45521-114">SQL Server Management Objects (SMO)</span><span class="sxs-lookup"><span data-stu-id="45521-114">SQL Server Management Objects (SMO)</span></span>  
  
-   <span data-ttu-id="45521-115">CmdExec-Aufträge des SQL Server-Agents.</span><span class="sxs-lookup"><span data-stu-id="45521-115">SQL Server Agent CmdExec jobs.</span></span>  
  
## <a name="typically-used-sqlcmd-options"></a><span data-ttu-id="45521-116">Normalerweise verwendete Optionen für sqlcmd</span><span class="sxs-lookup"><span data-stu-id="45521-116">Typically Used sqlcmd Options</span></span>  
 <span data-ttu-id="45521-117">Die folgenden Optionen werden am häufigsten verwendet:</span><span class="sxs-lookup"><span data-stu-id="45521-117">The following options are used most frequently:</span></span>  
  
-   <span data-ttu-id="45521-118">Die Server Option (**-S**), mit der die Instanz von identifiziert wird, mit der eine Verbindung hergestellt wird [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `sqlcmd` .</span><span class="sxs-lookup"><span data-stu-id="45521-118">The server option (**-S**) that identifies the instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to which `sqlcmd` connects.</span></span>  
  
-   <span data-ttu-id="45521-119">Authentifizierungs Optionen (**-E**, **-U**und **-P**), mit denen die Anmelde Informationen angegeben werden, die `sqlcmd` von verwendet werden, um eine Verbindung mit der Instanz von herzustellen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="45521-119">Authentication options (**-E**, **-U**, and **-P**) that specify the credentials that `sqlcmd` uses to connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="45521-120">Die Option **-E** ist die Standardeinstellung und muss nicht angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="45521-120">The **-E** option is the default and does not have to be specified.</span></span>  
  
-   <span data-ttu-id="45521-121">Eingabeoptionen (**-q**, **-q**und **-i**), mit denen der Speicherort der Eingabe für identifiziert wird `sqlcmd` .</span><span class="sxs-lookup"><span data-stu-id="45521-121">Input options (**-Q**, **-q**, and **-i**) that identify the location of the input to `sqlcmd`.</span></span>  
  
-   <span data-ttu-id="45521-122">Die Ausgabe Option (**-o**), mit der die Datei angegeben wird, in der die `sqlcmd` Ausgabe abgelegt werden soll.</span><span class="sxs-lookup"><span data-stu-id="45521-122">The output option (**-o**) that specifies the file in which `sqlcmd` is to put its output.</span></span>  
  
## <a name="connecting-to-the-sqlcmd-utility"></a><span data-ttu-id="45521-123">Herstellen einer Verbindung mit dem Hilfsprogramm "sqlcmd"</span><span class="sxs-lookup"><span data-stu-id="45521-123">Connecting to the sqlcmd Utility</span></span>  
 <span data-ttu-id="45521-124">Das Hilfsprogramm `sqlcmd` wird häufig für folgende Aufgaben verwendet:</span><span class="sxs-lookup"><span data-stu-id="45521-124">The following are common uses of the `sqlcmd` utility:</span></span>  
  
-   <span data-ttu-id="45521-125">Herstellen einer Verbindung mit einer Standardinstanz mithilfe der Windows-Authentifizierung, um [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen interaktiv auszuführen:</span><span class="sxs-lookup"><span data-stu-id="45521-125">Connecting to a default instance by using Windows Authentication to interactively run [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
    ```  
    sqlcmd -S <ComputerName>  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="45521-126">Im vorherigen Beispiel wurde **-E** nicht angegeben, da es sich hierbei um den Standardwert handelt und `sqlcmd` mithilfe der Windows-Authentifizierung eine Verbindung mit der Standard Instanz hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="45521-126">In the previous example, **-E** is not specified because it is the default and `sqlcmd` connects to the default instance by using Windows Authentication.</span></span>  
  
-   <span data-ttu-id="45521-127">Herstellen einer Verbindung mit einer benannten Instanz mithilfe der Windows-Authentifizierung, um [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen interaktiv auszuführen:</span><span class="sxs-lookup"><span data-stu-id="45521-127">Connecting to a named instance by using Windows Authentication to interactively run [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
    ```  
    sqlcmd -S <ComputerName>\<InstanceName>  
    ```  
  
     <span data-ttu-id="45521-128">oder</span><span class="sxs-lookup"><span data-stu-id="45521-128">or</span></span>  
  
    ```  
    sqlcmd -S .\<InstanceName>  
    ```  
  
-   <span data-ttu-id="45521-129">Herstellen einer Verbindung mit einer benannten Instanz mithilfe der Windows-Authentifizierung und Angeben von Eingabe- und Ausgabedateien:</span><span class="sxs-lookup"><span data-stu-id="45521-129">Connecting to a named instance by using Windows Authentication and specifying input and output files:</span></span>  
  
    ```  
    sqlcmd -S <ComputerName>\<InstanceName> -i <MyScript.sql> -o <MyOutput.rpt>  
    ```  
  
-   <span data-ttu-id="45521-130">Herstellen einer Verbindung mit der Standardinstanz auf dem lokalen Computer mithilfe der Windows-Authentifizierung, wobei eine Abfrage ausgeführt wird und `sqlcmd` nach Abschluss der Abfrage weiterhin ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="45521-130">Connecting to the default instance on the local computer by using Windows Authentication, executing a query, and having `sqlcmd` remain running after the query has finished running:</span></span>  
  
    ```  
    sqlcmd -q "SELECT * FROM AdventureWorks2012.Person.Person"  
    ```  
  
-   <span data-ttu-id="45521-131">Herstellen einer Verbindung mit der Standardinstanz auf dem lokalen Computer mithilfe der Windows-Authentifizierung, wobei eine Abfrage ausgeführt, die Ausgabe an eine Datei weitergeleitet und `sqlcmd` nach Abschluss der Abfrage beendet wird:</span><span class="sxs-lookup"><span data-stu-id="45521-131">Connecting to the default instance on the local computer by using Windows Authentication, executing a query, directing the output to a file, and having `sqlcmd` exit after the query has finished running:</span></span>  
  
    ```  
    sqlcmd -Q "SELECT * FROM AdventureWorks2012.Person.Person" -o MyOutput.txt  
    ```  
  
-   <span data-ttu-id="45521-132">Herstellen einer Verbindung mit einer benannten Instanz mithilfe der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Authentifizierung, um [!INCLUDE[tsql](../../includes/tsql-md.md)]-Anweisungen interaktiv auszuführen, wobei von `sqlcmd` eine Aufforderung zur Kennworteingabe erfolgt:</span><span class="sxs-lookup"><span data-stu-id="45521-132">Connecting to a named instance using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication to interactively run [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, with `sqlcmd` prompting for a password:</span></span>  
  
    ```  
    sqlcmd -U MyLogin -S <ComputerName>\<InstanceName>  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="45521-133">Eine vollständige Liste der von `sqlcmd` unterstützten Optionen erhalten Sie, indem Sie folgenden Befehl ausführen: `sqlcmd -?`.</span><span class="sxs-lookup"><span data-stu-id="45521-133">To see a list of the options that are supported by the `sqlcmd` utility run: `sqlcmd -?`.</span></span>  
  
## <a name="running-transact-sql-statements-interactively-by-using-sqlcmd"></a><span data-ttu-id="45521-134">Interaktives Ausführen von Transact-SQL-Anweisungen mithilfe von "sqlcmd"</span><span class="sxs-lookup"><span data-stu-id="45521-134">Running Transact-SQL Statements Interactively by Using sqlcmd</span></span>  
 <span data-ttu-id="45521-135">Sie können das Hilfsprogramm `sqlcmd` interaktiv verwenden, um [!INCLUDE[tsql](../../includes/tsql-md.md)]-Anweisungen in einem Eingabeaufforderungsfenster auszuführen.</span><span class="sxs-lookup"><span data-stu-id="45521-135">You can use the `sqlcmd` utility interactively to execute [!INCLUDE[tsql](../../includes/tsql-md.md)] statements in a Command Prompt window.</span></span> <span data-ttu-id="45521-136">Um [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen interaktiv mithilfe von auszuführen `sqlcmd` , führen Sie das Hilfsprogramm ohne die Optionen **-q**, **-q**, **-Z**, oder **-i** aus, um Eingabedateien oder Abfragen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="45521-136">To interactively execute [!INCLUDE[tsql](../../includes/tsql-md.md)] statements by using `sqlcmd`, run the utility without using the **-Q**, **-q**, **-Z**, or **-i** options to specify any input files or queries.</span></span> <span data-ttu-id="45521-137">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="45521-137">For example:</span></span>  
  
 `sqlcmd -S <ComputerName>\<InstanceName>`  
  
 <span data-ttu-id="45521-138">Wenn der Befehl ohne Eingabedateien oder Abfragen ausgeführt wird, wird von `sqlcmd` eine Verbindung mit der angegebenen Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] hergestellt und anschließend eine neue Zeile mit einer `1>` gefolgt von einem blinkenden Unterstrich angezeigt. Dies wird als `sqlcmd`-Aufforderung bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="45521-138">When the command is executed without input files or queries, `sqlcmd` connects to the specified instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and then displays a new line with a `1>` followed by a blinking underscore that is named the `sqlcmd` prompt.</span></span> <span data-ttu-id="45521-139">`1` bedeutet, dass es sich um die erste Zeile einer [!INCLUDE[tsql](../../includes/tsql-md.md)]-Anweisung handelt, und die `sqlcmd`-Aufforderung ist die Stelle, an der die [!INCLUDE[tsql](../../includes/tsql-md.md)]-Anweisung beginnt, wenn Sie sie eingeben.</span><span class="sxs-lookup"><span data-stu-id="45521-139">The `1` signifies that this is the first line of a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement, and the `sqlcmd` prompt is the point at which the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement will start when you type it in.</span></span>  
  
 <span data-ttu-id="45521-140">An der `sqlcmd` Eingabeaufforderung können Sie sowohl [!INCLUDE[tsql](../../includes/tsql-md.md)]-Anweisungen als auch `sqlcmd`-Befehle (z. B. `GO` und `EXIT`) eingeben.</span><span class="sxs-lookup"><span data-stu-id="45521-140">At the `sqlcmd` prompt, you can type both [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and `sqlcmd` commands, such as `GO` and `EXIT`.</span></span> <span data-ttu-id="45521-141">Die einzelnen [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen werden in einen Puffer geladen, den sogenannten Anweisungscache.</span><span class="sxs-lookup"><span data-stu-id="45521-141">Each [!INCLUDE[tsql](../../includes/tsql-md.md)] statement is put in a buffer called the statement cache.</span></span> <span data-ttu-id="45521-142">Diese Anweisungen werden an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] gesendet, nachdem Sie den Befehl `GO` eingegeben haben und die EINGABETASTE drücken.</span><span class="sxs-lookup"><span data-stu-id="45521-142">These statements are sent to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] after you type the `GO` command and press ENTER.</span></span> <span data-ttu-id="45521-143">Um den Vorgang zu beenden `sqlcmd` , geben Sie `EXIT` oder `QUIT` am Anfang einer neuen Zeile ein.</span><span class="sxs-lookup"><span data-stu-id="45521-143">To exit `sqlcmd`, type `EXIT` or `QUIT` at the start of a new line.</span></span>  
  
 <span data-ttu-id="45521-144">Den Anweisungscache können Sie löschen, indem Sie `:RESET` eingeben.</span><span class="sxs-lookup"><span data-stu-id="45521-144">To clear the statement cache, type `:RESET`.</span></span> <span data-ttu-id="45521-145">`^C`Die Eingabe bewirkt `sqlcmd` , dass beendet wird.</span><span class="sxs-lookup"><span data-stu-id="45521-145">Typing `^C` causes `sqlcmd` to exit.</span></span> <span data-ttu-id="45521-146">`^C` kann auch dazu verwendet werden, die Ausführung des Anweisungscaches zu beenden, nachdem ein `GO`-Befehl ausgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="45521-146">`^C` can also be used to stop the execution of the statement cache after a `GO` command has been issued.</span></span>  
  
 [!INCLUDE[tsql](../../includes/tsql-md.md)]<span data-ttu-id="45521-147">Anweisungen, die in einer interaktiven Sitzung eingegeben werden, können bearbeitet werden, indem der Befehl " **: Ed** " und die Eingabeaufforderung eingegeben werden `sqlcmd` .</span><span class="sxs-lookup"><span data-stu-id="45521-147">statements that are entered in an interactive session can edited by entering the **:ED** command and the `sqlcmd` prompt.</span></span> <span data-ttu-id="45521-148">Der Editor wird geöffnet. Nachdem Sie die [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung bearbeitet und den Editor geschlossen haben, wird die überarbeitete [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung im Eingabeaufforderungsfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="45521-148">The editor will open and, after editing the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement and closing the editor, the revised [!INCLUDE[tsql](../../includes/tsql-md.md)] statement will appear in the command window.</span></span> <span data-ttu-id="45521-149">Geben Sie ein `GO` , um die resultierende [!INCLUDE[tsql](../../includes/tsql-md.md)] Anweisung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="45521-149">Enter `GO` to run therevised [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span>  
  
## <a name="quoted-strings"></a><span data-ttu-id="45521-150">Zeichenfolgen in Anführungszeichen</span><span class="sxs-lookup"><span data-stu-id="45521-150">Quoted Strings</span></span>  
 <span data-ttu-id="45521-151">Zeichen, die in Anführungszeichen eingeschlossen sind, werden ohne weitere Vorverarbeitung verwendet. Die einzige Ausnahme besteht darin, dass Anführungszeichen durch das Eingeben von zwei aufeinander folgenden Anführungszeichen in eine Zeichenfolge eingefügt werden können.</span><span class="sxs-lookup"><span data-stu-id="45521-151">Characters that are enclosed in quotation marks are used without any additional preprocessing, except that quotations marks can be inserted into a string by entering two consecutive quotation marks.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="45521-152">In wird diese Zeichenfolgensequenz als ein Anführungszeichen behandelt.</span><span class="sxs-lookup"><span data-stu-id="45521-152">treats this character sequence as one quotation mark.</span></span> <span data-ttu-id="45521-153">(Die Übersetzung erfolgt jedoch auf dem Server.) Skriptvariablen werden nicht erweitert, wenn sie innerhalb einer Zeichenfolge auftreten.</span><span class="sxs-lookup"><span data-stu-id="45521-153">(However, the translation occurs in the server.) Scripting variables will not be expanded when they appear within a string.</span></span>  
  
 <span data-ttu-id="45521-154">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="45521-154">For example:</span></span>  
  
 `sqlcmd`  
  
 `PRINT "Length: 5"" 7'";`  
  
 `GO`  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `Length: 5" 7'`  
  
## <a name="strings-that-span-multiple-lines"></a><span data-ttu-id="45521-155">Mehrere Zeilen umfassende Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="45521-155">Strings That Span Multiple Lines</span></span>  
 <span data-ttu-id="45521-156">Bei `sqlcmd` werden Skripts mit Zeichenfolgen, die mehrere Zeilen umfassen, unterstützt.</span><span class="sxs-lookup"><span data-stu-id="45521-156">`sqlcmd` supports scripts that have strings that span multiple lines.</span></span> <span data-ttu-id="45521-157">Beispielsweise umfasst die folgende `SELECT` -Anweisung mehrere Zeilen; es handelt sich jedoch um eine einzelne Zeichenfolge, die ausgeführt wird, wenn Sie `GO`eingeben und anschließend die EINGABETASTE drücken.</span><span class="sxs-lookup"><span data-stu-id="45521-157">For example, the following `SELECT` statement spans multiple lines but is a single string executed when you press the ENTER key after typing `GO`.</span></span>  
  
 `SELECT First line`  
  
 `FROM Second line`  
  
 `WHERE Third line;`  
  
 `GO`  
  
## <a name="interactive-sqlcmd-example"></a><span data-ttu-id="45521-158">Beispiel für die interaktive Verwendung von "sqlcmd"</span><span class="sxs-lookup"><span data-stu-id="45521-158">Interactive sqlcmd Example</span></span>  
 <span data-ttu-id="45521-159">In diesem Beispiel wird veranschaulicht, was bei der interaktiven Ausführung von `sqlcmd` angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="45521-159">This is an example of what you see when you run `sqlcmd` interactively.</span></span>  
  
 <span data-ttu-id="45521-160">Wenn Sie ein Eingabeaufforderungsfenster öffnen, wird nur eine Zeile ähnlich der Folgenden angezeigt:</span><span class="sxs-lookup"><span data-stu-id="45521-160">When you open a Command Prompt window, there is one line similar to:</span></span>  
  
 `C:\> _`  
  
 <span data-ttu-id="45521-161">Dies bedeutet, dass der Ordner `C:\` der aktuelle Ordner ist. Wenn Sie einen Dateinamen angeben, wird in Windows in diesem Ordner nach der Datei gesucht.</span><span class="sxs-lookup"><span data-stu-id="45521-161">This means the folder `C:\` is the current folder, and if you specify a file name, Windows will look for the file in that folder.</span></span>  
  
 <span data-ttu-id="45521-162">Geben Sie `sqlcmd` ein, um eine Verbindung mit der Standardinstanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] auf dem lokalen Computer herzustellen. In diesem Fall lautet der Inhalt des Eingabeaufforderungsfensters folgendermaßen:</span><span class="sxs-lookup"><span data-stu-id="45521-162">Type `sqlcmd` to connect to the default instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on the local computer, and the contents of the Command Prompt window will be:</span></span>  
  
 `C:\>sqlcmd`  
  
 `1> _`  
  
 <span data-ttu-id="45521-163">Dies bedeutet, dass Sie eine Verbindung mit dieser Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] hergestellt haben und von `sqlcmd` ab sofort [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen und `sqlcmd` -Befehle akzeptiert werden.</span><span class="sxs-lookup"><span data-stu-id="45521-163">This means you have connected to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and `sqlcmd` is now ready to accept [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and `sqlcmd` commands.</span></span> <span data-ttu-id="45521-164">Der blinkende Unterstrich hinter der `1>` ist die `sqlcmd` -Aufforderung. Damit wird die Stelle gekennzeichnet, an der die von Ihnen eingegebenen Anweisungen und Befehle angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="45521-164">The flashing underscore after the `1>` is the `sqlcmd` prompt that marks the location at which the statements and commands you type will be displayed.</span></span> <span data-ttu-id="45521-165">Geben Sie nun ein `USE AdventureWorks2012` , und drücken Sie die EINGABETASTE, und geben `GO` Sie ein.</span><span class="sxs-lookup"><span data-stu-id="45521-165">Now, type `USE AdventureWorks2012` and press ENTER, and then type `GO` and press ENTER.</span></span> <span data-ttu-id="45521-166">Im Eingabeaufforderungsfensters wird der folgende Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="45521-166">The contents of the Command Prompt window will be:</span></span>  
  
 `sqlcmd`  
  
 `USE AdventureWorks2012;`  
  
 `GO`  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `Changed database context to 'AdventureWorks2012'.`  
  
 `1> _`  
  
 <span data-ttu-id="45521-167">Durch das Drücken der EINGABETASTE nach dem Eingeben von `USE AdventureWorks2012` wurde `sqlcmd` angewiesen, eine neue Zeile zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="45521-167">Pressing ENTER after entering `USE AdventureWorks2012` signaled `sqlcmd` to start a new line.</span></span> <span data-ttu-id="45521-168">Durch das Drücken der EINGABETASTE nach dem Eingeben von `GO,` wurde `sqlcmd` angewiesen, die `USE AdventureWorks2012` -Anweisung an die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]zu senden.</span><span class="sxs-lookup"><span data-stu-id="45521-168">Pressing ENTER, after you type `GO,` signaled `sqlcmd` to send the `USE AdventureWorks2012` statement to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="45521-169">`sqlcmd` Anschließend wurde von sqlcmd die Meldung zurückgegeben, dass die `USE` -Anweisung erfolgreich ausgeführt wurde, und es wurde eine neue `1>` -Eingabeaufforderung als Hinweis zum Eingeben einer neuen Anweisung oder eines neuen Befehls angezeigt.</span><span class="sxs-lookup"><span data-stu-id="45521-169">`sqlcmd` then returned a message to indicate that the `USE` statement completed successfully and displayed a new `1>` prompt as a signal to enter a new statement or command.</span></span>  
  
 <span data-ttu-id="45521-170">Im folgenden Beispiel wird gezeigt, was im Eingabeaufforderungsfenster angezeigt wird, wenn Sie eine `SELECT` -Anweisung, eine `GO` -Anweisung zum Ausführen von `SELECT`und anschließend `EXIT` eingeben, um `sqlcmd`zu beenden:</span><span class="sxs-lookup"><span data-stu-id="45521-170">The following example shows what the Command Prompt window contains if you type a `SELECT` statement, a `GO` to execute the `SELECT`, and an `EXIT` to exit `sqlcmd`:</span></span>  
  
 `sqlcmd`  
  
 `USE AdventureWorks2012;`  
  
 `GO`  
  
 `SELECT TOP (3) BusinessEntityID, FirstName, LastName`  
  
 `FROM Person.Person;`  
  
 `GO`  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `BusinessEntityID   FirstName                 LastName`  
  
 `----------- -------------------------------- -----------`  
  
 `1           Syed                             Abbas`  
  
 `2           Catherine                        Abel`  
  
 `3           Kim                              Abercrombie`  
  
 `(3 rows affected)`  
  
 `1> EXIT`  
  
 `C:\>`  
  
 <span data-ttu-id="45521-171">Bei den Zeilen im Anschluss an die Zeile `3> GO` handelt es sich um die Ausgabe einer `SELECT` -Anweisung.</span><span class="sxs-lookup"><span data-stu-id="45521-171">The lines after line `3> GO` are the output of a `SELECT` statement.</span></span> <span data-ttu-id="45521-172">Nach dem Generieren einer Ausgabe wird die `sqlcmd` -Eingabeaufforderung durch `sqlcmd` zurückgesetzt, und es wird `1>`angezeigt.</span><span class="sxs-lookup"><span data-stu-id="45521-172">After you generate output, `sqlcmd` resets the `sqlcmd` prompt and displays `1>`.</span></span> <span data-ttu-id="45521-173">Nach der Eingabe von `EXIT` in der Zeile `1>`wird im Eingabeaufforderungsfenster dieselbe Zeile wie beim ersten Öffnen der Eingabeaufforderung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="45521-173">After entering `EXIT` at line `1>`, the Command Prompt window displays the same line it did when you first opened it.</span></span> <span data-ttu-id="45521-174">Dies bedeutet, dass die Sitzung von `sqlcmd` beendet ist.</span><span class="sxs-lookup"><span data-stu-id="45521-174">This indicates that `sqlcmd` has exited its session.</span></span> <span data-ttu-id="45521-175">Sie können das Eingabeaufforderungsfenster nun schließen, indem Sie einen weiteren `EXIT` -Befehl eingeben.</span><span class="sxs-lookup"><span data-stu-id="45521-175">You can now close the Command Prompt window by typing another `EXIT` command.</span></span>  
  
## <a name="running-transact-sql-script-files-by-using-sqlcmd"></a><span data-ttu-id="45521-176">Ausführen von Transact-SQL-Skriptdateien mithilfe von "sqlcmd"</span><span class="sxs-lookup"><span data-stu-id="45521-176">Running Transact-SQL Script Files by Using sqlcmd</span></span>  
 <span data-ttu-id="45521-177">Sie können `sqlcmd` zum Ausführen von Datenbankskriptdateien verwenden.</span><span class="sxs-lookup"><span data-stu-id="45521-177">You can use `sqlcmd` to execute database script files.</span></span> <span data-ttu-id="45521-178">Skriptdateien sind Textdateien, die eine Mischung aus [!INCLUDE[tsql](../../includes/tsql-md.md)] Anweisungen, `sqlcmd` Befehlen und Skript Variablen enthalten.</span><span class="sxs-lookup"><span data-stu-id="45521-178">Script files are text files that contain a mix of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, `sqlcmd` commands, and scripting variables.</span></span> <span data-ttu-id="45521-179">Weitere Informationen zum Definieren von Skriptvariablen finden Sie unter [Verwenden von sqlcmd mit Skriptvariablen](sqlcmd-use-with-scripting-variables.md).</span><span class="sxs-lookup"><span data-stu-id="45521-179">For more information about how to script variables, see [Use sqlcmd with Scripting Variables](sqlcmd-use-with-scripting-variables.md).</span></span> <span data-ttu-id="45521-180">In `sqlcmd` werden Anweisungen, Befehle und Skriptvariablen in einer Skriptdatei verwendet, ähnlich wie bei der Verwendung interaktiv eingegebener Anweisungen und Befehle.</span><span class="sxs-lookup"><span data-stu-id="45521-180">`sqlcmd` works with the statements, commands, and scripting variables in a script file in a manner similar to how it works with statements and commands that are entered interactively.</span></span> <span data-ttu-id="45521-181">Der Hauptunterschied besteht darin, dass die Eingabedatei von `sqlcmd` ohne Pause durchgelesen wird, anstatt darauf zu warten, dass ein Benutzer die Anweisungen, Befehle und Skriptvariablen eingibt.</span><span class="sxs-lookup"><span data-stu-id="45521-181">The main difference is that `sqlcmd` reads through the input file without pause instead of waiting for a user to enter the statements, commands, and scripting variables.</span></span>  
  
 <span data-ttu-id="45521-182">Es gibt verschiedene Möglichkeiten, um Datenbankskriptdateien zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="45521-182">There are different ways to create database script files:</span></span>  
  
-   <span data-ttu-id="45521-183">Sie können eine Reihe von [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen interaktiv in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]erstellen und debuggen und anschließend den Inhalt des Abfragefensters als Skriptdatei speichern.</span><span class="sxs-lookup"><span data-stu-id="45521-183">You can interactively build and debug a set of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then save the contents of the Query window as a script file.</span></span>  
  
-   <span data-ttu-id="45521-184">Sie können eine Textdatei mit [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen mithilfe eines Text-Editors (z. B. Editor) erstellen.</span><span class="sxs-lookup"><span data-stu-id="45521-184">You can create a text file that contains [!INCLUDE[tsql](../../includes/tsql-md.md)] statements by using a text editor, such as Notepad.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="45521-185">Beispiele</span><span class="sxs-lookup"><span data-stu-id="45521-185">Examples</span></span>  
  
### <a name="a-running-a-script-by-using-sqlcmd"></a><span data-ttu-id="45521-186">A.</span><span class="sxs-lookup"><span data-stu-id="45521-186">A.</span></span> <span data-ttu-id="45521-187">Ausführen eines Skripts mithilfe von "sqlcmd"</span><span class="sxs-lookup"><span data-stu-id="45521-187">Running a script by using sqlcmd</span></span>  
 <span data-ttu-id="45521-188">Starten Sie Editor, und geben Sie die folgenden [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen ein:</span><span class="sxs-lookup"><span data-stu-id="45521-188">Start Notepad, and type the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
 `USE AdventureWorks2012;`  
  
 `GO`  
  
 `SELECT TOP (3) BusinessEntityID, FirstName, LastName`  
  
 `FROM Person.Person;`  
  
 `GO`  
  
 <span data-ttu-id="45521-189">Erstellen Sie einen neuen Ordner mit dem Namen `MyFolder` , und speichern Sie das Skript als Datei `MyScript.sql` im Ordner `C:\MyFolder`.</span><span class="sxs-lookup"><span data-stu-id="45521-189">Create a folder named `MyFolder` and then save the script as the file `MyScript.sql` in the folder `C:\MyFolder`.</span></span> <span data-ttu-id="45521-190">Geben Sie die folgende Eingabeaufforderung ein, um das Skript auszuführen, und speichern Sie die Ausgabe in `MyOutput.txt` im Ordner `MyFolder`:</span><span class="sxs-lookup"><span data-stu-id="45521-190">Enter the following at the command prompt to run the script and put the output in `MyOutput.txt` in `MyFolder`:</span></span>  
  
 `sqlcmd -i C:\MyFolder\MyScript.sql -o C:\MyFolder\MyOutput.txt`  
  
 <span data-ttu-id="45521-191">Wenn Sie den Inhalt von `MyOutput.txt` in Editor anzeigen, sehen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="45521-191">When you view the contents of `MyOutput.txt` in Notepad, you will see the following:</span></span>  
  
 `Changed database context to 'AdventureWorks2012'.`  
  
 `BusinessEntityID FirstName   LastName`  
  
 `---------------- ----------- -----------`  
  
 `1                Syed        Abbas`  
  
 `2                Catherine   Abel`  
  
 `3                Kim         Abercrombie`  
  
 `(3 rows affected)`  
  
### <a name="b-using-sqlcmd-with-a-dedicated-administrative-connection"></a><span data-ttu-id="45521-192">B.</span><span class="sxs-lookup"><span data-stu-id="45521-192">B.</span></span> <span data-ttu-id="45521-193">Verwenden von "sqlcmd" mit einer dedizierten Verwaltungsverbindung</span><span class="sxs-lookup"><span data-stu-id="45521-193">Using sqlcmd with a dedicated administrative connection</span></span>  
 <span data-ttu-id="45521-194">Im folgenden Beispiel wird mithilfe von `sqlcmd` eine Verbindung mit einem Server hergestellt, der Blockierungsprobleme aufweist. Dies erfolgt mithilfe einer dedizierten Administratorverbindung (Dedicated Administrator Connection, DAC).</span><span class="sxs-lookup"><span data-stu-id="45521-194">In the following example, `sqlcmd` is used to connect to a server that has a blocking problem by using the dedicated administrator connection (DAC).</span></span>  
  
 `C:\>sqlcmd -S ServerName -A`  
  
 `1> SELECT blocked FROM sys.dm_exec_requests WHERE blocked <> 0;`  
  
 `2> GO`  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `spid   blocked`  
  
 `------ -------`  
  
 `62       64`  
  
 `(1 rows affected)`  
  
 <span data-ttu-id="45521-195">Beenden Sie den Blockierungsprozess mithilfe von `sqlcmd` .</span><span class="sxs-lookup"><span data-stu-id="45521-195">Use `sqlcmd` to end the blocking process.</span></span>  
  
 `1> KILL 64;`  
  
 `2> GO`  
  
### <a name="c-using-sqlcmd-to-execute-a-stored-procedure"></a><span data-ttu-id="45521-196">C.</span><span class="sxs-lookup"><span data-stu-id="45521-196">C.</span></span> <span data-ttu-id="45521-197">Verwenden von "sqlcmd" zum Ausführen einer gespeicherten Prozedur</span><span class="sxs-lookup"><span data-stu-id="45521-197">Using sqlcmd to execute a stored procedure</span></span>  
 <span data-ttu-id="45521-198">Im folgenden Beispiel wird veranschaulicht, wie eine gespeicherte Prozedur mithilfe von `sqlcmd`ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="45521-198">The following example shows how to execute a stored procedure by using `sqlcmd`.</span></span> <span data-ttu-id="45521-199">Erstellen Sie die folgende gespeicherte Prozedur.</span><span class="sxs-lookup"><span data-stu-id="45521-199">Create the following stored procedure.</span></span>  
  
 `USE AdventureWorks2012;`  
  
 `IF OBJECT_ID ( ' dbo.ContactEmailAddress, 'P' ) IS NOT NULL`  
  
 `DROP PROCEDURE dbo.ContactEmailAddress;`  
  
 `GO`  
  
 `CREATE PROCEDURE dbo.ContactEmailAddress`  
  
 `(`  
  
 `@FirstName nvarchar(50)`  
  
 `,@LastName nvarchar(50)`  
  
 `)`  
  
 `AS`  
  
 `SET NOCOUNT ON`  
  
 `SELECT EmailAddress`  
  
 `FROM Person.Person`  
  
 `WHERE FirstName = @FirstName`  
  
 `AND LastName = @LastName;`  
  
 `SET NOCOUNT OFF`  
  
 <span data-ttu-id="45521-200">Geben Sie an der `sqlcmd` -Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="45521-200">At the `sqlcmd` prompt, enter the following:</span></span>  
  
 `C:\sqlcmd`  
  
 `1> :Setvar FirstName Gustavo`  
  
 `1> :Setvar LastName Achong`  
  
 `1> EXEC dbo.ContactEmailAddress $(Gustavo),$(Achong)`  
  
 `2> GO`  
  
 `EmailAddress`  
  
 `-----------------------------`  
  
 `gustavo0@adventure-works.com`  
  
### <a name="d-using-sqlcmd-for-database-maintenance"></a><span data-ttu-id="45521-201">D:</span><span class="sxs-lookup"><span data-stu-id="45521-201">D.</span></span> <span data-ttu-id="45521-202">Verwenden von "sqlcmd" für die Datenbankwartung</span><span class="sxs-lookup"><span data-stu-id="45521-202">Using sqlcmd for database maintenance</span></span>  
 <span data-ttu-id="45521-203">Im folgenden Beispiel wird veranschaulicht, wie mithilfe von `sqlcmd` Datenbankwartungstasks ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="45521-203">The following example shows how to use `sqlcmd` for a database maintenance task.</span></span> <span data-ttu-id="45521-204">Erstellen Sie `C:\BackupTemplate.sql` mit dem folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="45521-204">Create `C:\BackupTemplate.sql` with the following code.</span></span>  
  
 `USE master;`  
  
 `BACKUP DATABASE [$(db)] TO DISK='$(bakfile)';`  
  
 <span data-ttu-id="45521-205">Geben Sie an der `sqlcmd` -Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="45521-205">At the `sqlcmd` prompt, enter the following:</span></span>  
  
 `C:\ >sqlcmd`  
  
 `1> :connect <server>`  
  
 `Sqlcmd: Successfully connected to server <server>.`  
  
 `1> :setvar db msdb`  
  
 `1> :setvar bakfile c:\msdb.bak`  
  
 `1> :r c:\BackupTemplate.sql`  
  
 `2> GO`  
  
 `Changed database context to 'master'.`  
  
 `Processed 688 pages for database 'msdb', file 'MSDBData' on file 2.`  
  
 `Processed 5 pages for database 'msdb', file 'MSDBLog' on file 2.`  
  
 `BACKUP DATABASE successfully processed 693 pages in 0.725 seconds (7.830 MB/sec)`  
  
### <a name="e-using-sqlcmd-to-execute-code-on-multiple-instances"></a><span data-ttu-id="45521-206">E.</span><span class="sxs-lookup"><span data-stu-id="45521-206">E.</span></span> <span data-ttu-id="45521-207">Verwenden von "sqlcmd" zum Ausführen von Code auf mehreren Instanzen</span><span class="sxs-lookup"><span data-stu-id="45521-207">Using sqlcmd to execute code on multiple instances</span></span>  
 <span data-ttu-id="45521-208">Mit dem folgenden Code wird in einer Datei ein Skript angezeigt, mit dem eine Verbindung mit zwei Instanzen hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="45521-208">The following code in a file shows a script that connects to two instances.</span></span> <span data-ttu-id="45521-209">Beachten Sie die `GO` -Anweisung vom dem Herstellen einer Verbindung mit der zweiten Instanz.</span><span class="sxs-lookup"><span data-stu-id="45521-209">Notice the `GO` before the connection to the second instance.</span></span>  
  
 `:CONNECT <server>\,<instance1>`  
  
 `EXEC dbo.SomeProcedure`  
  
 `GO`  
  
 `:CONNECT <server>\,<instance2>`  
  
 `EXEC dbo.SomeProcedure`  
  
 `GO`  
  
### <a name="e-returning-xml-output"></a><span data-ttu-id="45521-210">E.</span><span class="sxs-lookup"><span data-stu-id="45521-210">E.</span></span> <span data-ttu-id="45521-211">Zurückgeben einer XML-Ausgabe</span><span class="sxs-lookup"><span data-stu-id="45521-211">Returning XML output</span></span>  
 <span data-ttu-id="45521-212">Im folgenden Beispiel wird gezeigt, wie eine XML-Ausgabe unformatiert in einem fortlaufenden Datenstrom zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="45521-212">The following example shows how XML output is returned unformatted, in a continuous stream.</span></span>  
  
 `C:\>sqlcmd -d AdventureWorks2012`  
  
 `1> :XML ON`  
  
 `1> SELECT TOP 3 FirstName + ' ' + LastName + ', '`  
  
 `2> FROM Person.Person`  
  
 `3> GO`  
  
 `Syed Abbas, Catherine Abel, Kim Abercrombie,`  
  
### <a name="f-using-sqlcmd-in-a-windows-script-file"></a><span data-ttu-id="45521-213">F.</span><span class="sxs-lookup"><span data-stu-id="45521-213">F.</span></span> <span data-ttu-id="45521-214">Verwenden von "sqlcmd" in einer Windows-Skriptdatei</span><span class="sxs-lookup"><span data-stu-id="45521-214">Using sqlcmd in a Windows script file</span></span>  
 <span data-ttu-id="45521-215">Ein `sqlcmd` Befehl wie `sqlcmd -i C:\InputFile.txt -o C:\OutputFile.txt,` kann in einer bat-Datei in Verbindung mit VBScript ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="45521-215">A `sqlcmd`command such as `sqlcmd -i C:\InputFile.txt -o C:\OutputFile.txt,` can be executed in a .bat file together with VBScript.</span></span> <span data-ttu-id="45521-216">In diesem Fall werden keine interaktiven Optionen verwendet.</span><span class="sxs-lookup"><span data-stu-id="45521-216">In this case, do not use interactive options.</span></span> <span data-ttu-id="45521-217">`sqlcmd` muss auf dem Computer installiert sein, auf dem die BAT-Datei ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="45521-217">`sqlcmd` must be installed on the computer that is executing the .bat file.</span></span>  
  
 <span data-ttu-id="45521-218">Erstellen Sie zunächst die folgenden vier Dateien:</span><span class="sxs-lookup"><span data-stu-id="45521-218">First, create the following four files:</span></span>  
  
-   <span data-ttu-id="45521-219">C:\badscript.sql</span><span class="sxs-lookup"><span data-stu-id="45521-219">C:\badscript.sql</span></span>  
  
    ```  
    SELECT batch_1_this_is_an_error  
    GO  
    SELECT 'batch #2'  
    GO  
    ```  
  
-   <span data-ttu-id="45521-220">C:\goodscript.sql</span><span class="sxs-lookup"><span data-stu-id="45521-220">C:\goodscript.sql</span></span>  
  
    ```  
    SELECT 'batch #1'  
    GO  
    SELECT 'batch #2'  
    GO  
    ```  
  
-   <span data-ttu-id="45521-221">C:\returnvalue.sql</span><span class="sxs-lookup"><span data-stu-id="45521-221">C:\returnvalue.sql</span></span>  
  
    ```  
    :exit(select 100)  
    @echo off  
    C:\windowsscript.bat  
    @echo off  
  
    echo Running badscript.sql  
    sqlcmd -i badscript.sql -b -o out.log  
    if not errorlevel 1 goto next1  
    echo == An error occurred   
  
    :next1  
  
    echo Running goodscript.sql  
    sqlcmd -i goodscript.sql -b -o out.log  
    if not errorlevel 1 goto next2  
    echo == An error occurred   
  
    :next2  
    echo Running returnvalue.sql  
    sqlcmd -i returnvalue.sql -o out.log  
    echo SQLCMD returned %errorlevel% to the command shell  
  
    :exit  
    ```  
  
-   <span data-ttu-id="45521-222">C:\windowsscript.bat</span><span class="sxs-lookup"><span data-stu-id="45521-222">C:\windowsscript.bat</span></span>  
  
    ```  
    @echo off  
  
    echo Running badscript.sql  
    sqlcmd -i badscript.sql -b -o out.log  
    if not errorlevel 1 goto next1  
    echo == An error occurred   
  
    :next1  
  
    echo Running goodscript.sql  
    sqlcmd -i goodscript.sql -b -o out.log  
    if not errorlevel 1 goto next2  
    echo == An error occurred   
  
    :next2  
    echo Running returnvalue.sql  
    sqlcmd -i returnvalue.sql -o out.log  
    echo SQLCMD returned %errorlevel% to the command shell  
  
    :exit  
    ```  
  
 <span data-ttu-id="45521-223">Führen Sie anschließend an der Eingabeaufforderung `C:\windowsscript.bat`aus:</span><span class="sxs-lookup"><span data-stu-id="45521-223">Then, at the command prompt, run `C:\windowsscript.bat`:</span></span>  
  
 `C:\>windowsscript.bat`  
  
 `Running badscript.sql`  
  
 `== An error occurred`  
  
 `Running goodscript.sql`  
  
 `Running returnvalue.sql`  
  
 `SQLCMD returned 100 to the command shell`  
  
### <a name="g-using-sqlcmd-to-set-encryption-on-azure-sql-database"></a><span data-ttu-id="45521-224">G.</span><span class="sxs-lookup"><span data-stu-id="45521-224">G.</span></span> <span data-ttu-id="45521-225">Verwenden von „sqlcmd“ zum Festlegen der Verschlüsselung für eine Azure SQL-Datenbank</span><span class="sxs-lookup"><span data-stu-id="45521-225">Using sqlcmd to set encryption on Azure SQL Database</span></span>  
 <span data-ttu-id="45521-226">Eine `sqlcmd` kann für eine Verbindung mit-Daten ausgeführt werden [!INCLUDE[ssSDS](../../includes/sssds-md.md)] , um die Verschlüsselung und Zertifikats Vertrauensstellung anzugeben.</span><span class="sxs-lookup"><span data-stu-id="45521-226">A `sqlcmd`can be executed on a connection to [!INCLUDE[ssSDS](../../includes/sssds-md.md)] data on to specify encryption and certificate trust.</span></span> <span data-ttu-id="45521-227">Zwei ' sqlcmd ' ' '-Optionen sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="45521-227">Two \`sqlcmd\`\`\`options are available:</span></span>  
  
-   <span data-ttu-id="45521-228">Der Schalter "-N" wird vom Client verwendet, um eine verschlüsselte Verbindung anzufordern.</span><span class="sxs-lookup"><span data-stu-id="45521-228">The -N switch is used by the client to request an encrypted connection.</span></span> <span data-ttu-id="45521-229">Diese Option entspricht der ADO.NET-Option `ENCRYPT = true`.</span><span class="sxs-lookup"><span data-stu-id="45521-229">This option is equivalent to the ADO.net option `ENCRYPT = true`.</span></span>  
  
-   <span data-ttu-id="45521-230">Der Switch „–C“ wird vom Client verwendet, um ihn so zu konfigurieren, dass dem Serverzertifikat implizit vertraut wird, ohne es zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="45521-230">The -C switch is used by the client to configure it to implicitly the trust server certificate and not validate it.</span></span> <span data-ttu-id="45521-231">Diese Option entspricht der ADO.NET-Option `TRUSTSERVERCERTIFICATE = true`.</span><span class="sxs-lookup"><span data-stu-id="45521-231">This option is equivalent to the ADO.net option `TRUSTSERVERCERTIFICATE = true`.</span></span>  
  
 <span data-ttu-id="45521-232">Der [!INCLUDE[ssSDS](../../includes/sssds-md.md)] -Dienst unterstützt nicht alle `SET` -Optionen, die für eine SQL Server-Instanz verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="45521-232">The [!INCLUDE[ssSDS](../../includes/sssds-md.md)] service does not support all the `SET` options available on a SQL Server instance.</span></span> <span data-ttu-id="45521-233">Die folgenden Optionen lösen einen Fehler aus, wenn die entsprechende `SET` -Option auf `ON` oder `OFF`festgelegt wird:</span><span class="sxs-lookup"><span data-stu-id="45521-233">The following options throw an error when the corresponding `SET` option is set to `ON` or `OFF`:</span></span>  
  
-   <span data-ttu-id="45521-234">SET ANSI_DEFAULTS</span><span class="sxs-lookup"><span data-stu-id="45521-234">SET ANSI_DEFAULTS</span></span>  
  
-   <span data-ttu-id="45521-235">SET ANSI_NULLS</span><span class="sxs-lookup"><span data-stu-id="45521-235">SET ANSI_NULLS</span></span>  
  
-   <span data-ttu-id="45521-236">SET REMOTE_PROC_TRANSACTIONS</span><span class="sxs-lookup"><span data-stu-id="45521-236">SET REMOTE_PROC_TRANSACTIONS</span></span>  
  
-   <span data-ttu-id="45521-237">SET ANSI_NULL_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="45521-237">SET ANSI_NULL_DEFAULT</span></span>  
  
 <span data-ttu-id="45521-238">Die folgenden SET-Optionen lösen zwar keine Ausnahmen aus, können jedoch nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="45521-238">The following SET options do not throw exceptions but cannot be used.</span></span> <span data-ttu-id="45521-239">Sie sind veraltet:</span><span class="sxs-lookup"><span data-stu-id="45521-239">They are deprecated:</span></span>  
  
-   <span data-ttu-id="45521-240">SET CONCAT_NULL_YIELDS_NULL</span><span class="sxs-lookup"><span data-stu-id="45521-240">SET CONCAT_NULL_YIELDS_NULL</span></span>  
  
-   <span data-ttu-id="45521-241">SET ANSI_PADDING</span><span class="sxs-lookup"><span data-stu-id="45521-241">SET ANSI_PADDING</span></span>  
  
-   <span data-ttu-id="45521-242">SET QUERY_GOVERNOR_COST_LIMIT</span><span class="sxs-lookup"><span data-stu-id="45521-242">SET QUERY_GOVERNOR_COST_LIMIT</span></span>  
  
#### <a name="syntax"></a><span data-ttu-id="45521-243">Syntax</span><span class="sxs-lookup"><span data-stu-id="45521-243">Syntax</span></span>  
 <span data-ttu-id="45521-244">Die folgenden Beispiele beziehen sich auf Fälle,in denen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-Anbieter-Einstellungen Folgendes umfasst: `ForceProtocolEncryption = False`, `Trust Server Certificate = No`</span><span class="sxs-lookup"><span data-stu-id="45521-244">The following examples refer to cases where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client Provider settings include: `ForceProtocolEncryption = False`, `Trust Server Certificate = No`</span></span>  
  
 <span data-ttu-id="45521-245">Verbindung mit Windows-Anmeldeinformationen herstellen und Kommunikation verschlüsseln:</span><span class="sxs-lookup"><span data-stu-id="45521-245">Connect using Windows credentials and encrypt communication:</span></span>  
  
```  
SQLCMD -E -N  
  
```  
  
 <span data-ttu-id="45521-246">Verbindung mit Windows-Anmeldeinformationen herstellen und Serverzertifikat vertrauen:</span><span class="sxs-lookup"><span data-stu-id="45521-246">Connect using Windows credentials and trust server certificate:</span></span>  
  
```  
SQLCMD -E -C  
  
```  
  
 <span data-ttu-id="45521-247">Verbindung mit Windows-Anmeldeinformationen herstellen, Kommunikation verschlüsseln und Serverzertifikat vertrauen:</span><span class="sxs-lookup"><span data-stu-id="45521-247">Connect using Windows credentials, encrypt communication and trust server certificate:</span></span>  
  
```  
SQLCMD -E -N -C  
  
```  
  
 <span data-ttu-id="45521-248">Die folgenden Beispiele beziehen sich auf zwei Fälle, in denen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-Anbieter-Einstellungen wie folgt lauten: `ForceProtocolEncryption = True`, `TrustServerCertificate = Yes`.</span><span class="sxs-lookup"><span data-stu-id="45521-248">The following examples refer to cases where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client Provider settings include: `ForceProtocolEncryption = True`, `TrustServerCertificate = Yes`.</span></span>  
  
 <span data-ttu-id="45521-249">Verbindung mit Windows-Anmeldeinformationen herstellen, Kommunikation verschlüsseln und Serverzertifikat vertrauen:</span><span class="sxs-lookup"><span data-stu-id="45521-249">Connect using Windows credentials, encrypt communication and trust server certificate:</span></span>  
  
```  
SQLCMD -E  
  
```  
  
 <span data-ttu-id="45521-250">Verbindung mit Windows-Anmeldeinformationen herstellen, Kommunikation verschlüsseln und Serverzertifikat vertrauen:</span><span class="sxs-lookup"><span data-stu-id="45521-250">Connect using Windows credentials, encrypt communication and trust server certificate:</span></span>  
  
```  
SQLCMD -E -N  
  
```  
  
 <span data-ttu-id="45521-251">Verbindung mit Windows-Anmeldeinformationen herstellen, Kommunikation verschlüsseln und Serverzertifikat vertrauen:</span><span class="sxs-lookup"><span data-stu-id="45521-251">Connect using Windows credentials, encrypt communication and trust server certificate:</span></span>  
  
```  
SQLCMD -E -T  
  
```  
  
 <span data-ttu-id="45521-252">Verbindung mit Windows-Anmeldeinformationen herstellen, Kommunikation verschlüsseln und Serverzertifikat vertrauen:</span><span class="sxs-lookup"><span data-stu-id="45521-252">Connect using Windows credentials, encrypt communication and trust server certificate:</span></span>  
  
```  
SQLCMD -E -N -C  
  
```  
  
 <span data-ttu-id="45521-253">Wenn der Anbieter `ForceProtocolEncryption = True` angibt, wird die Verschlüsselung aktiviert, auch wenn die Verbindungszeichenfolge `Encrypt=No` enthält.</span><span class="sxs-lookup"><span data-stu-id="45521-253">If the provider specifies `ForceProtocolEncryption = True` then encryption is enabled even if `Encrypt=No` in the connection string.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45521-254">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="45521-254">See Also</span></span>  
 <span data-ttu-id="45521-255">[sqlcmd (Hilfsprogramm)](../../tools/sqlcmd-utility.md) </span><span class="sxs-lookup"><span data-stu-id="45521-255">[sqlcmd Utility](../../tools/sqlcmd-utility.md) </span></span>  
 <span data-ttu-id="45521-256">[Verwenden von sqlcmd mit Skriptvariablen](sqlcmd-use-with-scripting-variables.md) </span><span class="sxs-lookup"><span data-stu-id="45521-256">[Use sqlcmd with Scripting Variables](sqlcmd-use-with-scripting-variables.md) </span></span>  
 <span data-ttu-id="45521-257">[Bearbeiten von SQLCMD-Skripts mit dem Abfrage-Editor](edit-sqlcmd-scripts-with-query-editor.md) </span><span class="sxs-lookup"><span data-stu-id="45521-257">[Edit SQLCMD Scripts with Query Editor](edit-sqlcmd-scripts-with-query-editor.md) </span></span>  
 <span data-ttu-id="45521-258">[Verwalten von Auftragsschritten](../../ssms/agent/manage-job-steps.md) </span><span class="sxs-lookup"><span data-stu-id="45521-258">[Manage Job Steps](../../ssms/agent/manage-job-steps.md) </span></span>  
 [<span data-ttu-id="45521-259">Erstellen eines CmdExec-Auftragsschritts</span><span class="sxs-lookup"><span data-stu-id="45521-259">Create a CmdExec Job Step</span></span>](../../ssms/agent/create-a-cmdexec-job-step.md)  
  
  
