---
title: Bearbeiten von SQLCMD-Skripts mit dem Abfrage-Editor
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- scripts [SQL Server], SQLCMD scripts
- SQLCMD scripts
- modifying scripts
- Query Editor [Database Engine], SQLCMD scripts
- scripts [SQL Server], SQL Server Management Studio
ms.assetid: f77b866d-c330-47c9-9e74-0b8d8dff4b31
author: rothja
ms.author: jroth
ms.openlocfilehash: a3466cfc15ea2f4f0c8de5da42f4a1c24c28a575
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618624"
---
# <a name="edit-sqlcmd-scripts-with-query-editor"></a><span data-ttu-id="b31cd-102">Bearbeiten von SQLCMD-Skripts mit dem Abfrage-Editor</span><span class="sxs-lookup"><span data-stu-id="b31cd-102">Edit SQLCMD Scripts with Query Editor</span></span>
  <span data-ttu-id="b31cd-103">Mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Abfrage-Editor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] können Sie Abfragen als SQLCMD-Skripts schreiben und bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="b31cd-103">By using the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] you can write and edit queries as SQLCMD scripts.</span></span> <span data-ttu-id="b31cd-104">Sie verwenden SQLCMD-Skripts, wenn Sie Windows-Systembefehle und [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen in einem Skript verarbeiten müssen.</span><span class="sxs-lookup"><span data-stu-id="b31cd-104">You use SQLCMD scripts when you have to process Windows System commands and [!INCLUDE[tsql](../../includes/tsql-md.md)] statements in the same script.</span></span>  
  
## <a name="sqlcmd-mode"></a><span data-ttu-id="b31cd-105">SQLCMD-Modus</span><span class="sxs-lookup"><span data-stu-id="b31cd-105">SQLCMD Mode</span></span>  
 <span data-ttu-id="b31cd-106">Wenn Sie den [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Abfrage-Editor zum Schreiben oder Bearbeiten von SQLCMD-Skripts verwenden möchten, müssen Sie den SQLCMD-Skriptmodus aktivieren.</span><span class="sxs-lookup"><span data-stu-id="b31cd-106">To use the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor to write or edit SQLCMD scripts, you must enable the SQLCMD scripting mode.</span></span> <span data-ttu-id="b31cd-107">Standardmäßig ist der SQLCMD-Skriptmodus im Abfrage-Editor nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="b31cd-107">By default, SQLCMD mode is not enabled in the Query Editor.</span></span> <span data-ttu-id="b31cd-108">Zum Aktivieren des Skriptmodus klicken Sie auf das Symbol **SQLCMD-Modus** auf der Symbolleiste, oder wählen Sie im Menü **Abfrage** die Option **SQLCMD-Modus** aus.</span><span class="sxs-lookup"><span data-stu-id="b31cd-108">You can enable scripting mode by clicking the **SQLCMD Mode** icon in the toolbar or by selecting **SQLCMD Mode** from the **Query** menu.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b31cd-109">Durch Aktivieren des SQLCMD-Modus werden IntelliSense und der [!INCLUDE[tsql](../../includes/tsql-md.md)] -Debugger im [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Abfrage-Editor deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="b31cd-109">Enabling SQLCMD mode turns off IntelliSense and the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor.</span></span>  
  
 <span data-ttu-id="b31cd-110">SQLCMD-Skripts im Abfrage-Editor können dieselben Funktionen wie alle [!INCLUDE[tsql](../../includes/tsql-md.md)] -Skripts verwenden.</span><span class="sxs-lookup"><span data-stu-id="b31cd-110">SQLCMD scripts in the Query Editor can use the same features that all [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts use.</span></span> <span data-ttu-id="b31cd-111">Zu diesen Funktionen gehören folgende:</span><span class="sxs-lookup"><span data-stu-id="b31cd-111">These features include the following:</span></span>  
  
-   <span data-ttu-id="b31cd-112">Farbcodierung</span><span class="sxs-lookup"><span data-stu-id="b31cd-112">Color Coding</span></span>  
  
-   <span data-ttu-id="b31cd-113">Ausführen von Skripts</span><span class="sxs-lookup"><span data-stu-id="b31cd-113">Executing Scripts</span></span>  
  
-   <span data-ttu-id="b31cd-114">Quellcodeverwaltung</span><span class="sxs-lookup"><span data-stu-id="b31cd-114">Source Control</span></span>  
  
-   <span data-ttu-id="b31cd-115">Analysieren von Skripts</span><span class="sxs-lookup"><span data-stu-id="b31cd-115">Parsing Scripts</span></span>  
  
-   <span data-ttu-id="b31cd-116">Showplan</span><span class="sxs-lookup"><span data-stu-id="b31cd-116">Showplan</span></span>  
  
## <a name="enable-sqlcmd-scripting-in-query-editor"></a><span data-ttu-id="b31cd-117">Aktivieren von SQLCMD-Skripts im Abfrage-Editor</span><span class="sxs-lookup"><span data-stu-id="b31cd-117">Enable SQLCMD Scripting in Query Editor</span></span>  
 <span data-ttu-id="b31cd-118">Verwenden Sie das folgende Verfahren, um die SQLCMD-Skripterstellung für ein aktives Fenster des [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Abfrage-Editors zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="b31cd-118">To turn SQLCMD scripting on for an active [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor window, use the following procedure.</span></span>  
  
#### <a name="to-switch-a-database-engine-query-editor-window-to-sqlcmd-mode"></a><span data-ttu-id="b31cd-119">So wechseln Sie in einem Abfrage-Editorfenster der Datenbank-Engine in den SQLCMD-Modus</span><span class="sxs-lookup"><span data-stu-id="b31cd-119">To switch a Database Engine Query Editor window to SQLCMD mode</span></span>  
  
1.  <span data-ttu-id="b31cd-120">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf den Server, und klicken Sie dann auf **Neue Abfrage**, um ein neues [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Abfrage-Editorfenster zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="b31cd-120">In Object Explorer, right-click the server, and then click **New Query**, to open a new [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor window.</span></span>  
  
2.  <span data-ttu-id="b31cd-121">Klicken Sie im Menü **Abfrage** auf **SQLCMD-Modus**.</span><span class="sxs-lookup"><span data-stu-id="b31cd-121">On the **Query** menu, click **SQLCMD Mode**.</span></span>  
  
     <span data-ttu-id="b31cd-122">Der Abfrage-Editor führt **sqlcmd** -Anweisungen im Kontext des Abfrage-Editors aus.</span><span class="sxs-lookup"><span data-stu-id="b31cd-122">The Query Editor executes **sqlcmd** statements in the context of the Query Editor.</span></span>  
  
3.  <span data-ttu-id="b31cd-123">Wählen Sie auf der **SQL-Editor** -Symbolleiste in der Liste **Verfügbare Datenbanken** die [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)]-Datenbank aus.</span><span class="sxs-lookup"><span data-stu-id="b31cd-123">On the **SQL Editor** toolbar, in the **Available Databases** list, select [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span></span>  
  
4.  <span data-ttu-id="b31cd-124">Geben Sie im Fenster des Abfrage-Editors die folgenden beiden [!INCLUDE[tsql](../../includes/tsql-md.md)]-Anweisungen und die `!!DIR`-Anweisung **sqlcmd** ein:</span><span class="sxs-lookup"><span data-stu-id="b31cd-124">In the Query Editor window, type the following two [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and the `!!DIR` **sqlcmd** statement:</span></span>  
  
    ```  
    SELECT DISTINCT Type FROM Sales.SpecialOffer;  
    GO  
    !!DIR  
    GO  
    SELECT ProductCategoryID, Name FROM Production.ProductCategory;  
    GO  
    ```  
  
5.  <span data-ttu-id="b31cd-125">Drücken Sie F5, um den gesamten Abschnitt gemischter [!INCLUDE[tsql](../../includes/tsql-md.md)] - und MS-DOS-Anweisungen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="b31cd-125">Press F5 to execute the whole section of mixed [!INCLUDE[tsql](../../includes/tsql-md.md)] and MS-DOS statements.</span></span>  
  
     <span data-ttu-id="b31cd-126">Beachten Sie die beiden SQL-Ergebnisbereiche aus der ersten und dritten Anweisung.</span><span class="sxs-lookup"><span data-stu-id="b31cd-126">Notice the two SQL result panes from the first and third statements.</span></span>  
  
6.  <span data-ttu-id="b31cd-127">Klicken Sie im Bereich **Ergebnisse** auf die Registerkarte **Meldungen** , um die Meldungen für alle drei Anweisungen anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="b31cd-127">In the **Results** pane, click the **Messages** tab to see the messages from all three statements:</span></span>  
  
    -   <span data-ttu-id="b31cd-128">(6 Zeile(n) betroffen)</span><span class="sxs-lookup"><span data-stu-id="b31cd-128">(6 row(s) affected)</span></span>  
  
    -   \<The directory information>  
  
    -   <span data-ttu-id="b31cd-129">(4 Zeile(n) betroffen)</span><span class="sxs-lookup"><span data-stu-id="b31cd-129">(4 row(s) affected)</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b31cd-130">Wenn das Hilfsprogramm **sqlcmd** an der Befehlszeile ausgeführt wird, ermöglicht es die vollständige Interaktion mit dem Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="b31cd-130">When executed from the command line, the **sqlcmd** utility permits full interaction with the operating system.</span></span> <span data-ttu-id="b31cd-131">Wird der Abfrage-Editor im **SQLCMD-Modus**ausgeführt, müssen Sie darauf achten, dass Sie keine interaktiven Anweisungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="b31cd-131">When you use the Query Editor in **SQLCMD Mode**, you must be careful not to execute interactive statements.</span></span> <span data-ttu-id="b31cd-132">Der Abfrage-Editor kann auf keine Aufforderungen des Betriebssystems reagieren.</span><span class="sxs-lookup"><span data-stu-id="b31cd-132">The Query Editor cannot respond to operating system prompts.</span></span>  
  
 <span data-ttu-id="b31cd-133">Weitere Informationen zum Ausführen von SQLCMD finden Sie unter [sqlcmd Utility](../../tools/sqlcmd-utility.md). Sie können auch das SQLCMD-Lernprogramm ausführen.</span><span class="sxs-lookup"><span data-stu-id="b31cd-133">For more information about how to run SQLCMD, see [sqlcmd Utility](../../tools/sqlcmd-utility.md), or take the SQLCMD tutorial.</span></span>  
  
## <a name="enable-sqlcmd-scripting-by-default"></a><span data-ttu-id="b31cd-134">Aktivieren der SQLCMD-Skripterstellung als Standard</span><span class="sxs-lookup"><span data-stu-id="b31cd-134">Enable SQLCMD Scripting by Default</span></span>  
 <span data-ttu-id="b31cd-135">Zum Aktivieren der SQLCMD-Skripterstellung als Standard wählen Sie im Menü **Extras** die Option **Optionen**aus, erweitern Sie **Abfrageausführung**und **SQL Server**, klicken Sie auf die Seite **Allgemein** , und aktivieren Sie das Kontrollkästchen **Standardmäßig neue Abfragen im SQLCMD-Modus öffnen** .</span><span class="sxs-lookup"><span data-stu-id="b31cd-135">To turn SQLCMD scripting on by default, on the **Tools** menu select **Options**, expand **Query Execution**, and **SQL Server**, click the **General** page, and then check the **By default open new queries in SQLCMD Mode** box.</span></span>  
  
## <a name="writing-and-editing-sqlcmd-scripts"></a><span data-ttu-id="b31cd-136">Schreiben und Bearbeiten von SQLCMD-Skripts</span><span class="sxs-lookup"><span data-stu-id="b31cd-136">Writing and Editing SQLCMD Scripts</span></span>  
 <span data-ttu-id="b31cd-137">Wenn Sie den Skriptmodus aktiviert haben, können Sie SQLCMD-Befehle und [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen schreiben.</span><span class="sxs-lookup"><span data-stu-id="b31cd-137">After enabling scripting mode you may write SQLCMD commands and [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="b31cd-138">Es gelten die folgenden Regeln:</span><span class="sxs-lookup"><span data-stu-id="b31cd-138">The following rules apply:</span></span>  
  
-   <span data-ttu-id="b31cd-139">SQLCMD-Befehle müssen die erste Anweisung in einer Zeile sein.</span><span class="sxs-lookup"><span data-stu-id="b31cd-139">SQLCMD commands must be the first statement on a line.</span></span>  
  
-   <span data-ttu-id="b31cd-140">Pro Zeile ist nur ein SQLCMD-Befehl zulässig.</span><span class="sxs-lookup"><span data-stu-id="b31cd-140">Only one SQLCMD command is permitted on each line.</span></span>  
  
-   <span data-ttu-id="b31cd-141">Vor SQLCMD-Befehlen können Kommentare oder Leerzeichen stehen.</span><span class="sxs-lookup"><span data-stu-id="b31cd-141">SQLCMD commands can be preceded by comments or white space.</span></span>  
  
-   <span data-ttu-id="b31cd-142">SQLCMD-Befehle in Kommentarzeichen werden nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b31cd-142">SQLCMD commands within comment characters are not executed.</span></span>  
  
-   <span data-ttu-id="b31cd-143">Bei Kommentaren, die aus einer einzelnen Zeile bestehen, bestehen die Kommentarzeichen aus zwei Bindestrichen (`--)` . Sie müssen am Anfang einer Zeile stehen.</span><span class="sxs-lookup"><span data-stu-id="b31cd-143">Single line comment characters are two hyphens (`--)` and must appear at the beginning of a line.</span></span>  
  
-   <span data-ttu-id="b31cd-144">Vor Betriebssystembefehlen müssen zwei Ausrufezeichen (`!!`) stehen.</span><span class="sxs-lookup"><span data-stu-id="b31cd-144">Operating system commands must be preceded by two exclamation points (`!!`).</span></span> <span data-ttu-id="b31cd-145">Der Befehl mit doppelten Ausrufezeichen sorgt dafür, dass die Anweisung nach den Ausrufezeichen mit dem Befehlsprozessor `cmd.exe` ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b31cd-145">The double-exclamation points command causes the statement that follows the exclamation points to be executed using the `cmd.exe` command processor.</span></span> <span data-ttu-id="b31cd-146">Der Text nach `!!` wird als Parameter an `cmd.exe`übergeben. Die letzte Befehlszeile wird somit wie folgt ausgeführt: `"%SystemRoot%\system32\cmd.exe /c <text after !!>"`.</span><span class="sxs-lookup"><span data-stu-id="b31cd-146">The text after `!!` is passed in as a parameter to `cmd.exe`, so the final command line will execute as: `"%SystemRoot%\system32\cmd.exe /c <text after !!>"`.</span></span>  
  
-   <span data-ttu-id="b31cd-147">Um eine klare Unterscheidung zwischen SQLCMD-Befehlen und [!INCLUDE[tsql](../../includes/tsql-md.md)]zu treffen, müssen alle SQLCMD-Befehle als Präfix einen Doppelpunkt (`:`) haben.</span><span class="sxs-lookup"><span data-stu-id="b31cd-147">To make a clear distinction between SQLCMD commands and [!INCLUDE[tsql](../../includes/tsql-md.md)], all SQLCMD commands, need to be prefixed with a colon (`:`).</span></span>  
  
-   <span data-ttu-id="b31cd-148">Der `GO` -Befehl kann möglicherweise verwendet werden, ohne ihm etwas voranzustellen oder mit vorangestelltem `!!:`</span><span class="sxs-lookup"><span data-stu-id="b31cd-148">The `GO` command may be used without preface, or preceded by `!!:`</span></span>  
  
-   <span data-ttu-id="b31cd-149">Der [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Abfrage-Editor unterstützt Umgebungsvariablen und Variablen, die als Teil eines SQLCMD-Skripts definiert sind. Integrierte SQLCMD- oder **osql** -Variablen werden jedoch nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b31cd-149">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor supports environment variables and variables that are defined as part of a SQLCMD script, but does not support built-in SQLCMD or **osql** variables.</span></span> <span data-ttu-id="b31cd-150">Bei der SQLCMD-Verarbeitung von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] wird für Variablen die Groß- und Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="b31cd-150">SQLCMD processing by [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] is case sensitive for variables.</span></span> <span data-ttu-id="b31cd-151">PRINT '$(COMPUTERNAME)' erzeugt beispielsweise das korrekte Ergebnis, bei PRINT '$(ComputerName)' wird jedoch ein Fehler zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b31cd-151">For example, PRINT '$(COMPUTERNAME)' produces the correct result, but PRINT '$(ComputerName)' returns an error.</span></span>  
  
> [!CAUTION]  
>  [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="b31cd-152">verwendet [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]SqlClient zur Ausführung im regulären und im SQLCMD-Modus.</span><span class="sxs-lookup"><span data-stu-id="b31cd-152">uses [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]SqlClient for execution in regular and SQLCMD mode.</span></span> <span data-ttu-id="b31cd-153">Beim Ausführen an der Befehlszeile verwendet SQLCMD den OLE DB-Anbieter.</span><span class="sxs-lookup"><span data-stu-id="b31cd-153">When run from the command line, SQLCMD uses the OLE DB provider.</span></span> <span data-ttu-id="b31cd-154">Da unterschiedliche Standardoptionen gelten können, wird beim Ausführen derselben Abfrage im SQLCMD-Modus in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] und im Hilfsprogramm SQLCMD möglicherweise ein anderes Verhalten erzielt.</span><span class="sxs-lookup"><span data-stu-id="b31cd-154">Because different default options may apply, it is possible to get different behavior while executing the same query in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] SQLCMD Mode, and in the SQLCMD utility.</span></span>  
  
## <a name="supported-sqlcmd-syntax"></a><span data-ttu-id="b31cd-155">Unterstützte SQLCMD-Syntax</span><span class="sxs-lookup"><span data-stu-id="b31cd-155">Supported SQLCMD Syntax</span></span>  
 <span data-ttu-id="b31cd-156">Der [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Abfrage-Editor unterstützt die folgenden Schlüsselwörter für SQLCMD-Skripts:</span><span class="sxs-lookup"><span data-stu-id="b31cd-156">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor supports the following SQLCMD script keywords:</span></span>  
  
 `[!!:]GO[count]`  
  
 `!! <command>`  
  
 `:exit(statement)`  
  
 `:Quit`  
  
 `:r <filename>`  
  
 `:setvar <var> <value>`  
  
 `:connect server[\instance] [-l login_timeout] [-U user [-P password]]`  
  
 `:on error [ignore|exit]`  
  
 `:error <filename>|stderr|stdout`  
  
 `:out <filename>|stderr|stdout`  
  
> [!NOTE]  
>  <span data-ttu-id="b31cd-157">`:error` und `:out`senden sowohl für `stderr` als auch für `stdout` die Ausgabe an die Registerkarte Meldungen.</span><span class="sxs-lookup"><span data-stu-id="b31cd-157">For both `:error` and `:out`, `stderr` and `stdout` send output to the messages tab.</span></span>  
  
 <span data-ttu-id="b31cd-158">SQLCMD-Befehle, die oben nicht aufgeführt sind, werden im Abfrage-Editor nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b31cd-158">SQLCMD commands not listed above are not supported in Query Editor.</span></span> <span data-ttu-id="b31cd-159">Wenn ein Skript ausgeführt wird, das nicht unterstützte sqlcmd-Schlüsselwörter enthält, sendet der Abfrage-Editor \<ignored command*> für jedes nicht unterstützte Schlüsselwort eine Meldung zum Ignorieren des Befehls \* an das Ziel.</span><span class="sxs-lookup"><span data-stu-id="b31cd-159">When a script containing SQLCMD keywords that are not supported is executed, the Query Editor will send an "Ignoring command \*\<ignored command*>" message to the destination for each unsupported keyword.</span></span> <span data-ttu-id="b31cd-160">Das Skript wird erfolgreich ausgeführt. Die nicht unterstützten Befehle werden allerdings ignoriert.</span><span class="sxs-lookup"><span data-stu-id="b31cd-160">The script will execute successfully, but the unsupported commands will be ignored.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="b31cd-161">Da Sie SQLCMD nicht über die Befehlszeile starten, bestehen beim Ausführen des Abfrage-Editors im SQLCMD-Modus einige Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="b31cd-161">Because you are not starting SQLCMD from the command line, there are some limitations when running Query Editor in SQLCMD Mode.</span></span> <span data-ttu-id="b31cd-162">So können Sie keine Befehlszeilenparameter wie Variablen übergeben. Außerdem müssen Sie darauf achten, keine interaktiven Anweisungen auszuführen, da der Abfrage-Editor nicht auf Eingabeaufforderungen des Betriebssystems antworten kann.</span><span class="sxs-lookup"><span data-stu-id="b31cd-162">You cannot pass in command-line parameters such as variables, and, because the Query Editor does not have the ability to respond to operating system prompts, you must be careful not to execute interactive statements.</span></span>  
  
## <a name="color-coding-in-sqlcmd-scripts"></a><span data-ttu-id="b31cd-163">Farbcodierung in SQLCMD-Skripts</span><span class="sxs-lookup"><span data-stu-id="b31cd-163">Color Coding in SQLCMD Scripts</span></span>  
 <span data-ttu-id="b31cd-164">Wenn die SQLCMD-Skripterstellung aktiviert sind, werden die Skripts farblich codiert.</span><span class="sxs-lookup"><span data-stu-id="b31cd-164">With SQLCMD scripting enabled, scripts will be color coded.</span></span> <span data-ttu-id="b31cd-165">Die Farbcodierung für [!INCLUDE[tsql](../../includes/tsql-md.md)] -Schlüsselwörter bleibt gleich.</span><span class="sxs-lookup"><span data-stu-id="b31cd-165">The color coding for [!INCLUDE[tsql](../../includes/tsql-md.md)] keywords will remain the same.</span></span> <span data-ttu-id="b31cd-166">SQLCMD-Befehle werden mit einem schattierten Hintergrund angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b31cd-166">SQLCMD commands are presented with a shaded background.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b31cd-167">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b31cd-167">Example</span></span>  
 <span data-ttu-id="b31cd-168">Im folgenden Beispiel wird eine **sqlcmd** -Anweisung zum Erstellen einer Ausgabedatei mit dem Namen „testoutput.txt“ verwendet, und es werden zwei [!INCLUDE[tsql](../../includes/tsql-md.md)] -SELECT-Anweisungen zusammen mit einem Betriebssystembefehl ausgeführt (zum Drucken des aktuellen Verzeichnisses).</span><span class="sxs-lookup"><span data-stu-id="b31cd-168">The following example uses a **sqlcmd** statement to create an output file called testoutput.txt, executes two [!INCLUDE[tsql](../../includes/tsql-md.md)] SELECT statements along with one operating system command (to print out the current directory).</span></span> <span data-ttu-id="b31cd-169">Die ergebene Datei enthält die Meldungsausgabe von der `DIR` -Anweisung gefolgt von der ergebenen Ausgabe der [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="b31cd-169">The resultant file contains the message output from the `DIR` statement, followed by the results output from the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span>  
  
```  
:out C:\testoutput.txt  
SELECT @@VERSION As 'Server Version'  
!!DIR  
!!:GO  
SELECT @@SERVERNAME AS 'Server Name'  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="b31cd-170">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b31cd-170">See Also</span></span>  
 [<span data-ttu-id="b31cd-171">SQLCMD-Hilfsprogramm</span><span class="sxs-lookup"><span data-stu-id="b31cd-171">sqlcmd Utility</span></span>](../../tools/sqlcmd-utility.md)  
  
  
