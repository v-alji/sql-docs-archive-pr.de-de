---
title: Verwenden von sqlcmd mit Skriptvariablen
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- scripts [SQL Server], sqlcmd utility
- variables [SQL Server], scripts
- scripting variables [SQL Server]
- sqlcmd utility, scripts
- setvar command
ms.assetid: 793495ca-cfc9-498d-8276-c44a5d09a92c
author: rothja
ms.author: jroth
ms.openlocfilehash: 8443cb400dc099726ba75bfcec2d38cee4ee2dff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620808"
---
# <a name="use-sqlcmd-with-scripting-variables"></a><span data-ttu-id="c1338-102">Verwenden von sqlcmd mit Skriptvariablen</span><span class="sxs-lookup"><span data-stu-id="c1338-102">Use sqlcmd with Scripting Variables</span></span>
  <span data-ttu-id="c1338-103">Variablen, die in Skripts verwendet werden, werden als Skriptvariablen bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="c1338-103">Variables that are used in scripts are called scripting variables.</span></span> <span data-ttu-id="c1338-104">Durch Skriptvariablen wird ein Skript aktiviert, das in verschiedenen Szenarien verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c1338-104">Scripting variables enable one script to be used in multiple scenarios.</span></span> <span data-ttu-id="c1338-105">Wenn Sie beispielsweise ein einzelnes Skript auf mehreren Servern ausführen möchten, anstatt das Skript für jeden Server zu ändern, können Sie eine Skriptvariable für den Servernamen verwenden.</span><span class="sxs-lookup"><span data-stu-id="c1338-105">For example, if you want to run one script against multiple servers, instead of modifying the script for each server, you can use a scripting variable for the server name.</span></span> <span data-ttu-id="c1338-106">Durch das Ändern des Servernamens für die Skriptvariable kann das gleiche Skript auf verschiedenen Servern ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c1338-106">By changing the server name supplied to the scripting variable, the same script can be executed on different servers.</span></span>  
  
 <span data-ttu-id="c1338-107">Skriptvariablen können explizit mithilfe des Befehls **setvar** oder implizit mithilfe der Option **sqlcmd -v** definiert werden.</span><span class="sxs-lookup"><span data-stu-id="c1338-107">Scripting variables can be defined explicitly by using the **setvar** command, or implicitly by using the **sqlcmd-v** option.</span></span>  
  
 <span data-ttu-id="c1338-108">Dieses Thema enthält auch Beispiele zum Definieren von Umgebungsvariablen an der Eingabeaufforderung von „Cmd.exe“ mithilfe von **SET**.</span><span class="sxs-lookup"><span data-stu-id="c1338-108">This topic also includes examples defining environmental variables at the Cmd.exe command prompt by using **SET**.</span></span>  
  
## <a name="setting-scripting-variables-by-using-the-setvar-command"></a><span data-ttu-id="c1338-109">Festlegen von Skriptvariablen mithilfe des setvar-Befehls</span><span class="sxs-lookup"><span data-stu-id="c1338-109">Setting Scripting Variables by Using the setvar Command</span></span>  
 <span data-ttu-id="c1338-110">Der Befehl **setvar** wird zum Definieren von Skriptvariablen verwendet.</span><span class="sxs-lookup"><span data-stu-id="c1338-110">The **setvar** command is used to define scripting variables.</span></span> <span data-ttu-id="c1338-111">Mithilfe des Befehls **setvar** definierte Variablen werden intern gespeichert.</span><span class="sxs-lookup"><span data-stu-id="c1338-111">Variables that are defined by using the **setvar** command are stored internally.</span></span> <span data-ttu-id="c1338-112">Skriptvariablen dürfen nicht mit Umgebungsvariablen verwechselt werden, die mithilfe von **SET**an der Eingabeaufforderung definiert werden.</span><span class="sxs-lookup"><span data-stu-id="c1338-112">Scripting variables should not be confused with environment variables that are defined at the command prompt by using **SET**.</span></span> <span data-ttu-id="c1338-113">Wenn ein Skript auf eine Variable verweist, die keine Umgebungsvariable ist oder nicht mithilfe von **setvar**definiert wurde, wird eine Fehlermeldung zurückgegeben und die Ausführung des Skripts unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="c1338-113">If a script references a variable that is not an environment variable or is not defined by using **setvar**, an error message is returned and the execution of the script will stop.</span></span> <span data-ttu-id="c1338-114">Weitere Informationen finden Sie unter der Option **-b** im [Hilfsprogramm sqlcmd](../../tools/sqlcmd-utility.md).</span><span class="sxs-lookup"><span data-stu-id="c1338-114">For more information, see the **-b** option in [sqlcmd Utility](../../tools/sqlcmd-utility.md).</span></span>  
  
## <a name="variable-precedence-low-to-high"></a><span data-ttu-id="c1338-115">Rangfolge der Variablen (vom niedrigsten bis zum höchsten Rang)</span><span class="sxs-lookup"><span data-stu-id="c1338-115">Variable Precedence (Low to High)</span></span>  
 <span data-ttu-id="c1338-116">Wenn mehrere Variablentypen denselben Namen aufweisen, wird die Variable mit der höchsten Rangfolge verwendet.</span><span class="sxs-lookup"><span data-stu-id="c1338-116">If more than one type of variable has the same name, the variable with the highest precedence is used.</span></span>  
  
1.  <span data-ttu-id="c1338-117">Umgebungsvariablen auf Systemebene</span><span class="sxs-lookup"><span data-stu-id="c1338-117">System level environmental variables</span></span>  
  
2.  <span data-ttu-id="c1338-118">Umgebungsvariablen auf Benutzerebene</span><span class="sxs-lookup"><span data-stu-id="c1338-118">User level environmental variables</span></span>  
  
3.  <span data-ttu-id="c1338-119">Die vor dem Starten von**SET X=Y**an der Eingabeaufforderung festgelegte Befehlsshell ( **SET X=Y**)</span><span class="sxs-lookup"><span data-stu-id="c1338-119">Command shell (**SET X=Y**) set at command prompt before starting **sqlcmd**</span></span>  
  
4.  <span data-ttu-id="c1338-120">**sqlcmd-v** X=Y</span><span class="sxs-lookup"><span data-stu-id="c1338-120">**sqlcmd-v** X=Y</span></span>  
  
5.  <span data-ttu-id="c1338-121">**:Setvar** X Y</span><span class="sxs-lookup"><span data-stu-id="c1338-121">**:Setvar** X Y</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c1338-122">Öffnen Sie die **Systemsteuerung**, klicken Sie auf **System**und anschließend auf die Registerkarte **Erweitert** , um die Umgebungsvariablen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c1338-122">To view the environmental variables, in **Control Panel**, open **System**, and then click the **Advanced** tab.</span></span>  
  
## <a name="implicitly-setting-scripting-variables"></a><span data-ttu-id="c1338-123">Implizites Festlegen von Skriptvariablen</span><span class="sxs-lookup"><span data-stu-id="c1338-123">Implicitly Setting Scripting Variables</span></span>  
 <span data-ttu-id="c1338-124">Wenn Sie **sqlcmd** mit einer Option starten, die eine verknüpfte **sqlcmd** -Variable aufweist, wird die **sqlcmd** -Variable implizit auf den Wert festgelegt, der mithilfe der Option angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="c1338-124">When you start **sqlcmd** with an option that has a related **sqlcmd** variable, the **sqlcmd** variable is set implicitly to the value that is specified by using the option.</span></span> <span data-ttu-id="c1338-125">Im folgenden Beispiel beginnt `sqlcmd` mit der Option `-l` .</span><span class="sxs-lookup"><span data-stu-id="c1338-125">In the following example, `sqlcmd` is started with the `-l` option.</span></span> <span data-ttu-id="c1338-126">Dadurch wird implizit die SQLLOGINTIMEOUT-Variable festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c1338-126">This implicitly sets the SQLLOGINTIMEOUT variable.</span></span>  
  
 `c:\> sqlcmd -l 60`  
  
 <span data-ttu-id="c1338-127">Sie können auch die Option **-v** verwenden, um eine Skriptvariable festzulegen, die in einem Skript vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="c1338-127">You can also use the **-v** option to set a scripting variable that exists in a script.</span></span> <span data-ttu-id="c1338-128">Im folgenden Skript (der Dateiname lautet `testscript.sql`) wird `ColumnName` als Skriptvariable verwendet.</span><span class="sxs-lookup"><span data-stu-id="c1338-128">In the following script (the file name is `testscript.sql`), `ColumnName` is a scripting variable.</span></span>  
  
 `USE AdventureWorks2012;`  
  
 `SELECT x.$(ColumnName)`  
  
 `FROM Person.Person x`  
  
 <span data-ttu-id="c1338-129">`WHERE c.`BusinessEntityID `< 5;`</span><span class="sxs-lookup"><span data-stu-id="c1338-129">`WHERE c.`BusinessEntityID `< 5;`</span></span>  
  
 <span data-ttu-id="c1338-130">Sie können daraufhin den Namen der Spalte angeben, die mithilfe der Option `-v` zurückgegeben werden soll:</span><span class="sxs-lookup"><span data-stu-id="c1338-130">You can then specify the name of the column that you want returned by using the `-v` option:</span></span>  
  
 `sqlcmd -v ColumnName ="FirstName" -i c:\testscript.sql`  
  
 <span data-ttu-id="c1338-131">Ändern Sie den Wert der `ColumnName` -Skriptvariablen, um eine andere Spalte mithilfe desselben Skripts zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="c1338-131">To return a different column by using the same script, change the value of the `ColumnName` scripting variable.</span></span>  
  
 `sqlcmd -v ColumnName ="LastName" -i c:\testscript.sql`  
  
## <a name="guidelines-for-scripting-variable-names-and-values"></a><span data-ttu-id="c1338-132">Richtlinien für Namen und Werte von Skriptvariablen</span><span class="sxs-lookup"><span data-stu-id="c1338-132">Guidelines for Scripting Variable Names and Values</span></span>  
 <span data-ttu-id="c1338-133">Die folgenden Richtlinien sollten bei der Benennung von Skriptvariablen berücksichtigt werden:</span><span class="sxs-lookup"><span data-stu-id="c1338-133">Consider the following guidelines when you name scripting variables:</span></span>  
  
-   <span data-ttu-id="c1338-134">Variablennamen dürfen keine Leerzeichen oder Anführungszeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="c1338-134">Variable names must not contain white space characters or quotation marks.</span></span>  
  
-   <span data-ttu-id="c1338-135">Variablennamen dürfen nicht die gleiche Form wie Variablenausdrücke (beispielsweise *$(var)*) aufweisen.</span><span class="sxs-lookup"><span data-stu-id="c1338-135">Variable names must not have the same form as a variable expression, such as *$(var)*.</span></span>  
  
-   <span data-ttu-id="c1338-136">Bei Skriptvariablen wird nicht zwischen Groß- und Kleinschreibung unterschieden.</span><span class="sxs-lookup"><span data-stu-id="c1338-136">Scripting variables are case-insensitive</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c1338-137">Wenn einer **sqlcmd** -Umgebungsvariablen kein Wert zugewiesen wird, wird die Variable entfernt.</span><span class="sxs-lookup"><span data-stu-id="c1338-137">If no value is assigned to a **sqlcmd** environment variable, the variable is removed.</span></span> <span data-ttu-id="c1338-138">Bei Verwendung von **:setvar VarName** ohne Wert wird die Variable gelöscht.</span><span class="sxs-lookup"><span data-stu-id="c1338-138">Using **:setvar VarName** without a value clears the variable.</span></span>  
  
 <span data-ttu-id="c1338-139">Die folgenden Richtlinien sollten beim Angeben von Werten für Skriptvariablen berücksichtigt werden:</span><span class="sxs-lookup"><span data-stu-id="c1338-139">Consider the following guidelines when you specify values for scripting variables:</span></span>  
  
-   <span data-ttu-id="c1338-140">Variablenwerte, die mit **setvar** oder mit der Option **-v** definiert werden, müssen in Anführungszeichen eingeschlossen werden, sofern im Zeichenfolgenwert Leerzeichen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="c1338-140">Variable values that are defined by using **setvar** or the **-v** option must be enclosed by quotation marks if the string value contains spaces.</span></span>  
  
-   <span data-ttu-id="c1338-141">Wenn Anführungszeichen Bestandteil des Variablenwerts sind, müssen sie mit Escapezeichen versehen werden.</span><span class="sxs-lookup"><span data-stu-id="c1338-141">If quotation marks are part of the variable value, they must be escaped.</span></span> <span data-ttu-id="c1338-142">Beispiel: :`setvar MyVar "spac""e"`.</span><span class="sxs-lookup"><span data-stu-id="c1338-142">For example: :`setvar MyVar "spac""e"`.</span></span>  
  
## <a name="guidelines-for-cmdexe-set-variable-values-and-names"></a><span data-ttu-id="c1338-143">Richtlinien für Cmd.exe SET-Variablennamen und -werte</span><span class="sxs-lookup"><span data-stu-id="c1338-143">Guidelines for Cmd.exe SET Variable Values and Names</span></span>  
 <span data-ttu-id="c1338-144">Mithilfe von SET definierte Variablen sind Teil der Cmd.exe-Umgebung, und es kann mit **sqlcmd**auf sie verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="c1338-144">Variables that are defined by using SET are part of the Cmd.exe environment and can be referenced by **sqlcmd**.</span></span> <span data-ttu-id="c1338-145">Berücksichtigen Sie die folgenden Richtlinien:</span><span class="sxs-lookup"><span data-stu-id="c1338-145">Consider the following guidelines:</span></span>  
  
-   <span data-ttu-id="c1338-146">Variablennamen dürfen keine Leerzeichen oder Anführungszeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="c1338-146">Variable names must not contain white space characters or quotation marks.</span></span>  
  
-   <span data-ttu-id="c1338-147">Variablenwerte dürfen Leerzeichen oder Anführungszeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="c1338-147">Variable values may contain spaces or quotation marks.</span></span>  
  
## <a name="sqlcmd-scripting-variables"></a><span data-ttu-id="c1338-148">sqlcmd-Skriptvariablen</span><span class="sxs-lookup"><span data-stu-id="c1338-148">sqlcmd Scripting Variables</span></span>  
 <span data-ttu-id="c1338-149">Mithilfe von **sqlcmd** definierte Variablen werden als Skriptvariablen bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="c1338-149">Variables that are defined by **sqlcmd** are known as scripting variables.</span></span> <span data-ttu-id="c1338-150">In der folgenden Tabelle sind die **sqlcmd** -Skriptvariablen aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="c1338-150">The following table lists **sqlcmd** scripting variables.</span></span>  
  
|<span data-ttu-id="c1338-151">Variable</span><span class="sxs-lookup"><span data-stu-id="c1338-151">Variable</span></span>|<span data-ttu-id="c1338-152">Zugehörige Option</span><span class="sxs-lookup"><span data-stu-id="c1338-152">Related option</span></span>|<span data-ttu-id="c1338-153">R/W</span><span class="sxs-lookup"><span data-stu-id="c1338-153">R/W</span></span>|<span data-ttu-id="c1338-154">Standard</span><span class="sxs-lookup"><span data-stu-id="c1338-154">Default</span></span>|  
|--------------|--------------------|----------|-------------|  
|<span data-ttu-id="c1338-155">SQLCMDUSER\*</span><span class="sxs-lookup"><span data-stu-id="c1338-155">SQLCMDUSER\*</span></span>|<span data-ttu-id="c1338-156">-U</span><span class="sxs-lookup"><span data-stu-id="c1338-156">-U</span></span>|<span data-ttu-id="c1338-157">R</span><span class="sxs-lookup"><span data-stu-id="c1338-157">R</span></span>|<span data-ttu-id="c1338-158">""</span><span class="sxs-lookup"><span data-stu-id="c1338-158">""</span></span>|  
|<span data-ttu-id="c1338-159">SQLCMDPASSWORD\*</span><span class="sxs-lookup"><span data-stu-id="c1338-159">SQLCMDPASSWORD\*</span></span>|<span data-ttu-id="c1338-160">-P</span><span class="sxs-lookup"><span data-stu-id="c1338-160">-P</span></span>|--|<span data-ttu-id="c1338-161">""</span><span class="sxs-lookup"><span data-stu-id="c1338-161">""</span></span>|  
|<span data-ttu-id="c1338-162">SQLCMDSERVER\*</span><span class="sxs-lookup"><span data-stu-id="c1338-162">SQLCMDSERVER\*</span></span>|<span data-ttu-id="c1338-163">-S</span><span class="sxs-lookup"><span data-stu-id="c1338-163">-S</span></span>|<span data-ttu-id="c1338-164">R</span><span class="sxs-lookup"><span data-stu-id="c1338-164">R</span></span>|<span data-ttu-id="c1338-165">"DefaultLocalInstance"</span><span class="sxs-lookup"><span data-stu-id="c1338-165">"DefaultLocalInstance"</span></span>|  
|<span data-ttu-id="c1338-166">SQLCMDWORKSTATION</span><span class="sxs-lookup"><span data-stu-id="c1338-166">SQLCMDWORKSTATION</span></span>|<span data-ttu-id="c1338-167">-H</span><span class="sxs-lookup"><span data-stu-id="c1338-167">-H</span></span>|<span data-ttu-id="c1338-168">R</span><span class="sxs-lookup"><span data-stu-id="c1338-168">R</span></span>|<span data-ttu-id="c1338-169">"ComputerName"</span><span class="sxs-lookup"><span data-stu-id="c1338-169">"ComputerName"</span></span>|  
|<span data-ttu-id="c1338-170">SQLCMDDBNAME</span><span class="sxs-lookup"><span data-stu-id="c1338-170">SQLCMDDBNAME</span></span>|<span data-ttu-id="c1338-171">-d</span><span class="sxs-lookup"><span data-stu-id="c1338-171">-d</span></span>|<span data-ttu-id="c1338-172">R</span><span class="sxs-lookup"><span data-stu-id="c1338-172">R</span></span>|<span data-ttu-id="c1338-173">""</span><span class="sxs-lookup"><span data-stu-id="c1338-173">""</span></span>|  
|<span data-ttu-id="c1338-174">SQLCMDLOGINTIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c1338-174">SQLCMDLOGINTIMEOUT</span></span>|<span data-ttu-id="c1338-175">-l</span><span class="sxs-lookup"><span data-stu-id="c1338-175">-l</span></span>|<span data-ttu-id="c1338-176">R/W</span><span class="sxs-lookup"><span data-stu-id="c1338-176">R/W</span></span>|<span data-ttu-id="c1338-177">"8" (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="c1338-177">"8" (seconds)</span></span>|  
|<span data-ttu-id="c1338-178">SQLCMDSTATTIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c1338-178">SQLCMDSTATTIMEOUT</span></span>|<span data-ttu-id="c1338-179">-t</span><span class="sxs-lookup"><span data-stu-id="c1338-179">-t</span></span>|<span data-ttu-id="c1338-180">R/W</span><span class="sxs-lookup"><span data-stu-id="c1338-180">R/W</span></span>|<span data-ttu-id="c1338-181">"0" = unbegrenzt warten</span><span class="sxs-lookup"><span data-stu-id="c1338-181">"0" = wait indefinitely</span></span>|  
|<span data-ttu-id="c1338-182">SQLCMDHEADERS</span><span class="sxs-lookup"><span data-stu-id="c1338-182">SQLCMDHEADERS</span></span>|<span data-ttu-id="c1338-183">-H</span><span class="sxs-lookup"><span data-stu-id="c1338-183">-h</span></span>|<span data-ttu-id="c1338-184">R/W</span><span class="sxs-lookup"><span data-stu-id="c1338-184">R/W</span></span>|<span data-ttu-id="c1338-185">"0"</span><span class="sxs-lookup"><span data-stu-id="c1338-185">"0"</span></span>|  
|<span data-ttu-id="c1338-186">SQLCMDCOLSEP</span><span class="sxs-lookup"><span data-stu-id="c1338-186">SQLCMDCOLSEP</span></span>|<span data-ttu-id="c1338-187">-S</span><span class="sxs-lookup"><span data-stu-id="c1338-187">-s</span></span>|<span data-ttu-id="c1338-188">R/W</span><span class="sxs-lookup"><span data-stu-id="c1338-188">R/W</span></span>|<span data-ttu-id="c1338-189">" "</span><span class="sxs-lookup"><span data-stu-id="c1338-189">" "</span></span>|  
|<span data-ttu-id="c1338-190">SQLCMDCOLWIDTH</span><span class="sxs-lookup"><span data-stu-id="c1338-190">SQLCMDCOLWIDTH</span></span>|<span data-ttu-id="c1338-191">-w</span><span class="sxs-lookup"><span data-stu-id="c1338-191">-w</span></span>|<span data-ttu-id="c1338-192">R/W</span><span class="sxs-lookup"><span data-stu-id="c1338-192">R/W</span></span>|<span data-ttu-id="c1338-193">"0"</span><span class="sxs-lookup"><span data-stu-id="c1338-193">"0"</span></span>|  
|<span data-ttu-id="c1338-194">SQLCMDPACKETSIZE</span><span class="sxs-lookup"><span data-stu-id="c1338-194">SQLCMDPACKETSIZE</span></span>|<span data-ttu-id="c1338-195">-a</span><span class="sxs-lookup"><span data-stu-id="c1338-195">-a</span></span>|<span data-ttu-id="c1338-196">R</span><span class="sxs-lookup"><span data-stu-id="c1338-196">R</span></span>|<span data-ttu-id="c1338-197">"4096"</span><span class="sxs-lookup"><span data-stu-id="c1338-197">"4096"</span></span>|  
|<span data-ttu-id="c1338-198">SQLCMDERRORLEVEL</span><span class="sxs-lookup"><span data-stu-id="c1338-198">SQLCMDERRORLEVEL</span></span>|<span data-ttu-id="c1338-199">-M</span><span class="sxs-lookup"><span data-stu-id="c1338-199">-m</span></span>|<span data-ttu-id="c1338-200">R/W</span><span class="sxs-lookup"><span data-stu-id="c1338-200">R/W</span></span>|<span data-ttu-id="c1338-201">"0"</span><span class="sxs-lookup"><span data-stu-id="c1338-201">"0"</span></span>|  
|<span data-ttu-id="c1338-202">SQLCMDMAXVARTYPEWIDTH</span><span class="sxs-lookup"><span data-stu-id="c1338-202">SQLCMDMAXVARTYPEWIDTH</span></span>|<span data-ttu-id="c1338-203">-y</span><span class="sxs-lookup"><span data-stu-id="c1338-203">-y</span></span>|<span data-ttu-id="c1338-204">R/W</span><span class="sxs-lookup"><span data-stu-id="c1338-204">R/W</span></span>|<span data-ttu-id="c1338-205">"256"</span><span class="sxs-lookup"><span data-stu-id="c1338-205">"256"</span></span>|  
|<span data-ttu-id="c1338-206">SQLCMDMAXFIXEDTYPEWIDTH</span><span class="sxs-lookup"><span data-stu-id="c1338-206">SQLCMDMAXFIXEDTYPEWIDTH</span></span>|<span data-ttu-id="c1338-207">-y</span><span class="sxs-lookup"><span data-stu-id="c1338-207">-Y</span></span>|<span data-ttu-id="c1338-208">R/W</span><span class="sxs-lookup"><span data-stu-id="c1338-208">R/W</span></span>|<span data-ttu-id="c1338-209">"0" = unbegrenzt</span><span class="sxs-lookup"><span data-stu-id="c1338-209">"0" = unlimited</span></span>|  
|<span data-ttu-id="c1338-210">SQLCMDEDITOR</span><span class="sxs-lookup"><span data-stu-id="c1338-210">SQLCMDEDITOR</span></span>||<span data-ttu-id="c1338-211">R/W</span><span class="sxs-lookup"><span data-stu-id="c1338-211">R/W</span></span>|<span data-ttu-id="c1338-212">"edit.com"</span><span class="sxs-lookup"><span data-stu-id="c1338-212">"edit.com"</span></span>|  
|<span data-ttu-id="c1338-213">SQLCMDINI</span><span class="sxs-lookup"><span data-stu-id="c1338-213">SQLCMDINI</span></span>||<span data-ttu-id="c1338-214">R</span><span class="sxs-lookup"><span data-stu-id="c1338-214">R</span></span>|<span data-ttu-id="c1338-215">""</span><span class="sxs-lookup"><span data-stu-id="c1338-215">""</span></span>|  
  
 <span data-ttu-id="c1338-216">\*SQLCMDUSER, SQLCMDPASSWORD und SQLCMDSERVER werden festgelegt, wenn **: Connect** verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c1338-216">\* SQLCMDUSER, SQLCMDPASSWORD and SQLCMDSERVER are set when **:Connect** is used.</span></span>  
  
 <span data-ttu-id="c1338-217">Durch R wird angezeigt, dass der Wert nur einmal während der Programminitialisierung festgelegt werden kann.</span><span class="sxs-lookup"><span data-stu-id="c1338-217">R indicates the value can only be set one time during program initialization.</span></span>  
  
 <span data-ttu-id="c1338-218">Durch R/W wird angezeigt, dass der Wert mithilfe des Befehls **setvar** zurückgesetzt werden kann. Für nachfolgende Befehle wird der neue Wert verwendet.</span><span class="sxs-lookup"><span data-stu-id="c1338-218">R/W indicates that the value can be reset by using the **setvar** command and subsequent commands will use the new value.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="c1338-219">Beispiele</span><span class="sxs-lookup"><span data-stu-id="c1338-219">Examples</span></span>  
  
### <a name="a-using-the-setvar-command-in-a-script"></a><span data-ttu-id="c1338-220">A.</span><span class="sxs-lookup"><span data-stu-id="c1338-220">A.</span></span> <span data-ttu-id="c1338-221">Verwenden des setvar-Befehls in einem Skript</span><span class="sxs-lookup"><span data-stu-id="c1338-221">Using the setvar command in a script</span></span>  
 <span data-ttu-id="c1338-222">Viele **sqlcmd** -Optionen können in einem Skript mithilfe des Befehls **setvar** gesteuert werden.</span><span class="sxs-lookup"><span data-stu-id="c1338-222">Many **sqlcmd** options can be controlled in a script by using the **setvar** command.</span></span> <span data-ttu-id="c1338-223">Im folgenden Beispiel wird das Skript `test.sql` erstellt, in dem die Variable `SQLCMDLOGINTIMEOUT` auf `60` Sekunden festgelegt ist. Eine weitere Skriptvariable ( `server`) wird auf `testserver`festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c1338-223">In the following example, the script `test.sql` is created in which the `SQLCMDLOGINTIMEOUT` variable is set to `60` seconds and another scripting variable, `server`, is set to `testserver`.</span></span> <span data-ttu-id="c1338-224">Der folgende Code befindet sich in `test.sql`.</span><span class="sxs-lookup"><span data-stu-id="c1338-224">The following code is in `test.sql`.</span></span>  
  
 `:setvar SQLCMDLOGINTIMEOUT 60`  
  
 `:setvar server "testserver"`  
  
 `:connect $(server) -l $(SQLCMDLOGINTIMEOUT)`  
  
 `USE AdventureWorks2012;`  
  
 `SELECT FirstName, LastName`  
  
 `FROM Person.Person;`  
  
 `The script is then called by using sqlcmd:`  
  
 `sqlcmd -i c:\test.sql`  
  
### <a name="b-using-the-setvar-command-interactively"></a><span data-ttu-id="c1338-225">B.</span><span class="sxs-lookup"><span data-stu-id="c1338-225">B.</span></span> <span data-ttu-id="c1338-226">Interaktives Verwenden des setvar-Befehls</span><span class="sxs-lookup"><span data-stu-id="c1338-226">Using the setvar command interactively</span></span>  
 <span data-ttu-id="c1338-227">Im folgenden Beispiel wird veranschaulicht, wie eine Skriptvariable mithilfe des `setvar` -Befehls interaktiv festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="c1338-227">The following example shows how to set a scripting variable interactively by using the `setvar` command.</span></span>  
  
 `sqlcmd`  
  
 `:setvar  MYDATABASE AdventureWorks2012`  
  
 `USE $(MYDATABASE);`  
  
 `GO`  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `Changed database context to 'AdventureWorks2012'`  
  
 `1>`  
  
### <a name="c-using-command-prompt-environment-variables-within-sqlcmd"></a><span data-ttu-id="c1338-228">C.</span><span class="sxs-lookup"><span data-stu-id="c1338-228">C.</span></span> <span data-ttu-id="c1338-229">Verwenden von Eingabeaufforderung-Umgebungsvariablen innerhalb von "sqlcmd"</span><span class="sxs-lookup"><span data-stu-id="c1338-229">Using command prompt environment variables within sqlcmd</span></span>  
 <span data-ttu-id="c1338-230">`are` Im folgenden Beispiel werden vier Umgebungsvariablen festgelegt und dann von `sqlcmd`aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="c1338-230">In the following example, four environment variables `are` set and then called from `sqlcmd`.</span></span>  
  
 `C:\>SET tablename=Person.Person`  
  
 `C:\>SET col1=FirstName`  
  
 `C:\>SET col2=LastName`  
  
 `C:\>SET title=Ms.`  
  
 `C:\>sqlcmd -d AdventureWorks2012`  
  
 `1> SELECT TOP 5 $(col1) + ' ' + $(col2) AS Name`  
  
 `2> FROM $(tablename)`  
  
 `3> WHERE Title ='$(title)'`  
  
 `4> GO`  
  
### <a name="d-using-user-level-environment-variables-within-sqlcmd"></a><span data-ttu-id="c1338-231">D:</span><span class="sxs-lookup"><span data-stu-id="c1338-231">D.</span></span> <span data-ttu-id="c1338-232">Verwenden von Umgebungsvariablen auf Benutzerebene in "sqlcmd"</span><span class="sxs-lookup"><span data-stu-id="c1338-232">Using user-level environment variables within sqlcmd</span></span>  
 <span data-ttu-id="c1338-233">Im folgenden Beispiel wird die `%Temp%` -Umgebungsvariable auf Benutzerebene an der Eingabeaufforderung festgelegt und an die `sqlcmd` -Eingabedatei übergeben.</span><span class="sxs-lookup"><span data-stu-id="c1338-233">In the following example the user-level environmental variable `%Temp%` is set at the command prompt and passed to the `sqlcmd` input file.</span></span> <span data-ttu-id="c1338-234">Zum Abrufen der Umgebungsvariable auf Benutzerebene doppelklicken Sie unter **Systemsteuerung**auf **System**.</span><span class="sxs-lookup"><span data-stu-id="c1338-234">To obtain the user-level environment variable, in **Control Panel**, double-click **System**.</span></span> <span data-ttu-id="c1338-235">Klicken Sie auf die Registerkarte **Erweitert** , und klicken Sie dann auf **Umgebungsvariablen**.</span><span class="sxs-lookup"><span data-stu-id="c1338-235">Click the **Advance** tab, and then click **Environment Variables**.</span></span>  
  
 <span data-ttu-id="c1338-236">In der Eingabedatei `c:\testscript.txt`ist der folgende Code enthalten:</span><span class="sxs-lookup"><span data-stu-id="c1338-236">The following code is in the input file `c:\testscript.txt`:</span></span>  
  
 `:OUT $(MyTempDirectory)`  
  
 `USE AdventureWorks2012;`  
  
 `SELECT FirstName`  
  
 `FROM AdventureWorks2012.Person.Person`  
  
 <span data-ttu-id="c1338-237">`WHERE BusinessEntityID` `< 5;`</span><span class="sxs-lookup"><span data-stu-id="c1338-237">`WHERE BusinessEntityID` `< 5;`</span></span>  
  
 <span data-ttu-id="c1338-238">Der folgende Code wird an der Eingabeaufforderung eingegeben:</span><span class="sxs-lookup"><span data-stu-id="c1338-238">This following code is entered at the command prompt:</span></span>  
  
 `C:\ >SET MyTempDirectory=%Temp%\output.txt`  
  
 `C:\ >sqlcmd -i C:\testscript.txt`  
  
 <span data-ttu-id="c1338-239">Das folgende Ergebnis wird an die Ausgabedatei „C:\Dokumente und Einstellungen\\<Benutzer\>\Lokale Einstellungen\Temp\output.txt“ gesendet.</span><span class="sxs-lookup"><span data-stu-id="c1338-239">The following result is sent to the output file C:\Documents and Settings\\<user\>\Local Settings\Temp\output.txt.</span></span>  
  
 `Changed database context to 'AdventureWorks2012'.`  
  
 `FirstName`  
  
 `--------------------------------------------------`  
  
 `Gustavo`  
  
 `Catherine`  
  
 `Kim`  
  
 `Humberto`  
  
 `(4 rows affected)`  
  
### <a name="e-using-a-startup-script"></a><span data-ttu-id="c1338-240">E.</span><span class="sxs-lookup"><span data-stu-id="c1338-240">E.</span></span> <span data-ttu-id="c1338-241">Verwenden eines Startskripts</span><span class="sxs-lookup"><span data-stu-id="c1338-241">Using a startup script</span></span>  
 <span data-ttu-id="c1338-242">Beim Starten von **sqlcmd** wird ein **sqlcmd** -Startskript ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c1338-242">A **sqlcmd** startup script is executed when **sqlcmd** is started.</span></span> <span data-ttu-id="c1338-243">Im folgenden Beispiel wird die Umgebungsvariable `SQLCMDINI`festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c1338-243">The following example sets the environment variable `SQLCMDINI`.</span></span> <span data-ttu-id="c1338-244">Dies ist der Inhalt von `init.sql.`</span><span class="sxs-lookup"><span data-stu-id="c1338-244">This is the contents of `init.sql.`</span></span>  
  
 `SET NOCOUNT ON`  
  
 `GO`  
  
 `DECLARE @nt_username nvarchar(128)`  
  
 `SET @nt_username = (SELECT rtrim(convert(nvarchar(128), nt_username))`  
  
 `FROM sys.dm_exec_sessions WHERE spid = @@SPID)`  
  
 `SELECT  @nt_username + ' is connected to ' +`  
  
 `rtrim(CONVERT(nvarchar(20), SERVERPROPERTY('servername'))) +`  
  
 `' (' +`  
  
 `rtrim(CONVERT(nvarchar(20), SERVERPROPERTY('productversion'))) +`  
  
 `')'`  
  
 `:setvar SQLCMDMAXFIXEDTYPEWIDTH 100`  
  
 `SET NOCOUNT OFF`  
  
 `GO`  
  
 `:setvar SQLCMDMAXFIXEDTYPEWIDTH`  
  
 <span data-ttu-id="c1338-245">Damit wird die Datei `init.sql` beim Starten von `sqlcmd` aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="c1338-245">This calls the `init.sql` file when `sqlcmd` is started.</span></span>  
  
 `C:\> SET sqlcmdini=c:\init.sql`  
  
 `>1 Sqlcmd`  
  
 <span data-ttu-id="c1338-246">Dies ist die Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="c1338-246">This is the output.</span></span>  
  
 `>1 < user > is connected to < server > (9.00.2047.00)`  
  
> [!NOTE]  
>  <span data-ttu-id="c1338-247">Mit der Option **-X** wird die Startskriptfunktion deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="c1338-247">The **-X** option disables the startup script feature.</span></span>  
  
### <a name="f-variable-expansion"></a><span data-ttu-id="c1338-248">F.</span><span class="sxs-lookup"><span data-stu-id="c1338-248">F.</span></span> <span data-ttu-id="c1338-249">Variablenerweiterung</span><span class="sxs-lookup"><span data-stu-id="c1338-249">Variable expansion</span></span>  
 <span data-ttu-id="c1338-250">Im folgenden Beispiel wird die Verwendung von Daten in Form einer **sqlcmd** -Variablen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="c1338-250">The following example shows working with data in the form of a **sqlcmd** variable.</span></span>  
  
 `USE AdventureWorks2012;`  
  
 `CREATE TABLE AdventureWorks2012.dbo.VariableTest`  
  
 `(`  
  
 `Col1 nvarchar(50)`  
  
 `);`  
  
 `GO`  
  
 <span data-ttu-id="c1338-251">Fügen Sie eine Zeile in `Col1` von `dbo.VariableTest` ein, in der der Wert `$(tablename)`enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="c1338-251">Insert one row into `Col1` of `dbo.VariableTest` that contains the value `$(tablename)`.</span></span>  
  
 `INSERT INTO AdventureWorks2012.dbo.VariableTest(Col1)`  
  
 `VALUES('$(tablename)');`  
  
 `GO`  
  
 <span data-ttu-id="c1338-252">Wenn keine Variable auf einen Wert gleich `sqlcmd` festgelegt ist, wird die Zeile an der `$(tablename)`-Eingabeaufforderung mit folgenden Anweisungen zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="c1338-252">At the `sqlcmd` prompt, when no variable is set equal to `$(tablename)`, the following statements return the row.</span></span>  
  
 `C:\> sqlcmd`  
  
 `>1 SELECT Col1 FROM dbo.VariableTest WHERE Col1 = '$(tablename)';`  
  
 `>2 GO`  
  
 `>3 SELECT Col1 FROM dbo.VariableTest WHERE Col1 = N'$(tablename)';`  
  
 `>4 GO`  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `>1 Col1`  
  
 `>2 ------------------`  
  
 `>3 $(tablename)`  
  
 `>4`  
  
 `>5 (1 rows affected)`  
  
 <span data-ttu-id="c1338-253">Es wird angenommen, dass die Variable `MyVar` auf `$(tablename)`festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="c1338-253">Given the variable `MyVar` is set to `$(tablename)`.</span></span>  
  
 `>6 :setvar MyVar $(tablename)`  
  
 <span data-ttu-id="c1338-254">Die Zeile wird mit diesen Anweisungen zurückgegeben. Außerdem wird die Meldung "Die 'tablename'-Skriptvariable ist nicht definiert." zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c1338-254">These statements return the row and also return the message "'tablename' scripting variable not defined."</span></span>  
  
 `>6 SELECT Col1 FROM dbo.VariableTest WHERE Col1 = '$(tablename)';`  
  
 `>7 GO`  
  
 `>1 SELECT Col1 FROM dbo.VariableTest WHERE Col1 = N'$(tablename)';`  
  
 `>2 GO`  
  
 <span data-ttu-id="c1338-255">Die Zeile wird mit diesen Anweisungen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c1338-255">These statements return the row.</span></span>  
  
 `>1 SELECT Col1 FROM dbo.VariableTest WHERE Col1 = '$(MyVar)';`  
  
 `>2 GO`  
  
 `>1 SELECT Col1 FROM dbo.VariableTest WHERE Col1 = N'$(MyVar)';`  
  
 `>2 GO`  
  
## <a name="see-also"></a><span data-ttu-id="c1338-256">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c1338-256">See Also</span></span>  
 <span data-ttu-id="c1338-257">[Verwenden des Hilfsprogramms „sqlcmd“](sqlcmd-use-the-utility.md) </span><span class="sxs-lookup"><span data-stu-id="c1338-257">[Use the sqlcmd Utility](sqlcmd-use-the-utility.md) </span></span>  
 <span data-ttu-id="c1338-258">[sqlcmd (Hilfsprogramm)](../../tools/sqlcmd-utility.md) </span><span class="sxs-lookup"><span data-stu-id="c1338-258">[sqlcmd Utility](../../tools/sqlcmd-utility.md) </span></span>  
 [<span data-ttu-id="c1338-259">Referenz zum Eingabeaufforderungs-Hilfsprogramm &#40;Datenbank-Engine&#41;</span><span class="sxs-lookup"><span data-stu-id="c1338-259">Command Prompt Utility Reference &#40;Database Engine&#41;</span></span>](../../tools/command-prompt-utility-reference-database-engine.md)  
  
  
