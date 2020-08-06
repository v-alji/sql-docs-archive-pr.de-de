---
title: sqlps-Hilfsprogramm | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- sqlps utility
- PowerShell [SQL Server], sqlps utility
ms.assetid: 4b2515a6-12c3-44fb-b263-1c567681cd2b
author: stevestein
ms.author: sstein
ms.openlocfilehash: b445366b3fb99ad4beebdf7b203ada77afe90c8d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694893"
---
# <a name="sqlps-utility"></a><span data-ttu-id="544bc-102">sqlps (Hilfsprogramm)</span><span class="sxs-lookup"><span data-stu-id="544bc-102">sqlps Utility</span></span>
  <span data-ttu-id="544bc-103">Das Hilfsprogramm `sqlps` startet eine Windows PowerShell 2.0-Sitzung mit geladenem und registriertem [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]-PowerShell-Anbieter sowie geladenen und registrierten Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="544bc-103">The `sqlps` utility starts a Windows PowerShell 2.0 session with the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell provider and cmdlets loaded and registered.</span></span> <span data-ttu-id="544bc-104">Sie können PowerShell-Befehle oder -Skripts eingeben, die die [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -PowerShell-Komponenten verwenden, sodass Instanzen von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] und ihre Objekte verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="544bc-104">You can enter PowerShell commands or scripts that use the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell components to work with instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] and their objects.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../includes/ssnotedepfutureavoid-md.md)] <span data-ttu-id="544bc-105">Verwenden Sie stattdessen das `sqlps`-PowerShell-Modul.</span><span class="sxs-lookup"><span data-stu-id="544bc-105">Use the `sqlps` PowerShell module instead.</span></span> <span data-ttu-id="544bc-106">Weitere Informationen zum- `sqlps` Modul finden Sie unter [Importieren des sqlps-Moduls](../database-engine/import-the-sqlps-module.md).</span><span class="sxs-lookup"><span data-stu-id="544bc-106">For more information about the `sqlps` module, see [Import the SQLPS Module](../database-engine/import-the-sqlps-module.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="544bc-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="544bc-107">Syntax</span></span>  
  
```  
  
      sqlps   
[ [ [ -NoLogo ][ -NoExit ][ -NoProfile ]  
    [ -OutPutFormat { Text | XML } ] [ -InPutFormat { Text | XML } ]  
  ]  
  [ -Command { -  
             | script_block [ -argsargument_array ]  
             | string [ command_parameters ]  
             }  
  ]  
]  
[ -? | -Help ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="544bc-108">Argumente</span><span class="sxs-lookup"><span data-stu-id="544bc-108">Arguments</span></span>  
 <span data-ttu-id="544bc-109">**-NoLogo**</span><span class="sxs-lookup"><span data-stu-id="544bc-109">**-NoLogo**</span></span>  
 <span data-ttu-id="544bc-110">Gibt an, dass beim Start des Hilfsprogramms `sqlps` die Copyrightinformationen ausgeblendet werden.</span><span class="sxs-lookup"><span data-stu-id="544bc-110">Specifies that the `sqlps` utility hide the copyright banner when it starts.</span></span>  
  
 <span data-ttu-id="544bc-111">**-NoExit**</span><span class="sxs-lookup"><span data-stu-id="544bc-111">**-NoExit**</span></span>  
 <span data-ttu-id="544bc-112">Gibt an, dass das Hilfsprogramm `sqlps` weiter ausgeführt wird, nachdem die Startbefehle abgeschlossen wurden.</span><span class="sxs-lookup"><span data-stu-id="544bc-112">Specifies that the `sqlps` utility continue running after the startup commands have completed.</span></span>  
  
 <span data-ttu-id="544bc-113">**-NoProfile**</span><span class="sxs-lookup"><span data-stu-id="544bc-113">**-NoProfile**</span></span>  
 <span data-ttu-id="544bc-114">Gibt an, dass das Hilfsprogramm `sqlps` kein Benutzerprofil lädt.</span><span class="sxs-lookup"><span data-stu-id="544bc-114">Specifies that the `sqlps` utility not load a user profile.</span></span> <span data-ttu-id="544bc-115">In Benutzerprofilen werden häufig verwendete Aliase, Funktionen und Variablen zur Verwendung in mehreren PowerShell-Sitzungen aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="544bc-115">User profiles record commonly used aliases, functions, and variables for use across PowerShell sessions.</span></span>  
  
 <span data-ttu-id="544bc-116">**-OutPutFormat** { **Text** | **XML** }</span><span class="sxs-lookup"><span data-stu-id="544bc-116">**-OutPutFormat** { **Text** | **XML** }</span></span>  
 <span data-ttu-id="544bc-117">Gibt an, dass die `sqlps` Ausgabe des Hilfsprogramms entweder als Text Zeichenfolgen (**Text**) oder in einem serialisierten CliXML-Format (**XML**) formatiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="544bc-117">Specifies that the `sqlps` utility output be formatted as either text strings (**Text**) or in a serialized CLIXML format (**XML**).</span></span>  
  
 <span data-ttu-id="544bc-118">**-InPutFormat** { **Text** | **XML** }</span><span class="sxs-lookup"><span data-stu-id="544bc-118">**-InPutFormat** { **Text** | **XML** }</span></span>  
 <span data-ttu-id="544bc-119">Gibt an, dass die Eingabe in das `sqlps` Hilfsprogramm entweder als Text Zeichenfolgen (**Text**) oder in einem serialisierten CliXML-Format (**XML**) formatiert ist.</span><span class="sxs-lookup"><span data-stu-id="544bc-119">Specifies that input to the `sqlps` utility is formatted as either text strings (**Text**) or in a serialized CLIXML format (**XML**).</span></span>  
  
 <span data-ttu-id="544bc-120">**-Command**</span><span class="sxs-lookup"><span data-stu-id="544bc-120">**-Command**</span></span>  
 <span data-ttu-id="544bc-121">Gibt den Befehl an, der vom Hilfsprogramm `sqlps` ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="544bc-121">Specifies the command for the `sqlps` utility to run.</span></span> <span data-ttu-id="544bc-122">Das `sqlps` Hilfsprogramm führt den Befehl aus und wird dann beendet, es sei denn, **-NoExit** ist ebenfalls angegeben.</span><span class="sxs-lookup"><span data-stu-id="544bc-122">The `sqlps` utility runs the command and then exits, unless **-NoExit** is also specified.</span></span> <span data-ttu-id="544bc-123">Geben Sie nach **-Command**keine anderen Schalter an, denn diese werden als Befehlsparameter gelesen.</span><span class="sxs-lookup"><span data-stu-id="544bc-123">Do not specify any other switches after **-Command**, they will be read as command parameters.</span></span>  
  
 **-**  
 <span data-ttu-id="544bc-124">**-Command-** gibt an, dass das `sqlps` Hilfsprogramm die Eingabe aus der Standardeingabe gelesen hat.</span><span class="sxs-lookup"><span data-stu-id="544bc-124">**-Command-** specifies that the `sqlps` utility read the input from the standard input.</span></span>  
  
 <span data-ttu-id="544bc-125">*script_block* [ **-args**_argument_array_ ]</span><span class="sxs-lookup"><span data-stu-id="544bc-125">*script_block* [ **-args**_argument_array_ ]</span></span>  
 <span data-ttu-id="544bc-126">Gibt einen Block von PowerShell-Befehlen an, die ausgeführt werden sollen. Der Block muss in geschweifte Klammern ({}) eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="544bc-126">Specifies a block of PowerShell commands to run, the block must be enclosed in braces: {}.</span></span> <span data-ttu-id="544bc-127">*Script_block* können nur angegeben werden, wenn das `sqlps` Hilfsprogramm entweder von **PowerShell** oder einer anderen `sqlps` hilfsprogrammsitzung aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="544bc-127">*Script_block* can only be specified when the `sqlps` utility is called from either **PowerShell** or another `sqlps` utility session.</span></span> <span data-ttu-id="544bc-128">*Argument_array* ist ein Array von PowerShell-Variablen, das die Argumente für die PowerShell-Befehle in *script_block*enthält.</span><span class="sxs-lookup"><span data-stu-id="544bc-128">The *argument_array* is an array of PowerShell variables containing the arguments for the PowerShell commands in the *script_block*.</span></span>  
  
 <span data-ttu-id="544bc-129">*string* [ *command_parameters* ]</span><span class="sxs-lookup"><span data-stu-id="544bc-129">*string* [ *command_parameters* ]</span></span>  
 <span data-ttu-id="544bc-130">Gibt eine Zeichenfolge an, die die auszuführenden PowerShell-Befehle enthält.</span><span class="sxs-lookup"><span data-stu-id="544bc-130">Specifies a string that contains the PowerShell commands to be run.</span></span> <span data-ttu-id="544bc-131">Verwenden Sie das Format **"& { *`command`* }"**.</span><span class="sxs-lookup"><span data-stu-id="544bc-131">Use the format **"&{*`command`*}"**.</span></span> <span data-ttu-id="544bc-132">Die Anführungszeichen geben eine Zeichenfolge an, und der Aufruf Operator (&) bewirkt, dass das `sqlps` Hilfsprogramm den Befehl ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="544bc-132">The quotation marks indicate a string, and the invoke operator (&) causes the `sqlps` utility to run the command.</span></span>  
  
 <span data-ttu-id="544bc-133">[ **-?**</span><span class="sxs-lookup"><span data-stu-id="544bc-133">[ **-?**</span></span><span data-ttu-id="544bc-134"> |  **-Help** ]</span><span class="sxs-lookup"><span data-stu-id="544bc-134"> | **-Help** ]</span></span>  
 <span data-ttu-id="544bc-135">Zeigt eine Syntaxzusammenfassung der Optionen des Hilfsprogramms `sqlps` an.</span><span class="sxs-lookup"><span data-stu-id="544bc-135">Shows the syntax summary of the `sqlps` utility options.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="544bc-136">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="544bc-136">Remarks</span></span>  
 <span data-ttu-id="544bc-137">Das `sqlps` Hilfsprogramm startet die PowerShell-Umgebung (PowerShell.exe) und lädt das [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell-Modul.</span><span class="sxs-lookup"><span data-stu-id="544bc-137">The `sqlps` utility starts the PowerShell environment (PowerShell.exe) and loads the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell module.</span></span> <span data-ttu-id="544bc-138">Das Modul, das auch heißt `sqlps` , lädt und registriert diese [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell-Snap-Ins:</span><span class="sxs-lookup"><span data-stu-id="544bc-138">The module, also named `sqlps`, loads and registers these [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell snap-ins:</span></span>  
  
-   <span data-ttu-id="544bc-139">Microsoft.SqlServer.Management.PSProvider.dll</span><span class="sxs-lookup"><span data-stu-id="544bc-139">Microsoft.SqlServer.Management.PSProvider.dll</span></span>  
  
     <span data-ttu-id="544bc-140">Implementiert den [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -PowerShell-Anbieter und zugeordnete Cmdlets, z. B. **Encode-SqlName** und **Decode-SqlName**.</span><span class="sxs-lookup"><span data-stu-id="544bc-140">Implements the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell provider and associated cmdlets such as **Encode-SqlName** and **Decode-SqlName**.</span></span>  
  
-   <span data-ttu-id="544bc-141">Microsoft.SqlServer.Management.PSSnapin.dll</span><span class="sxs-lookup"><span data-stu-id="544bc-141">Microsoft.SqlServer.Management.PSSnapin.dll</span></span>  
  
     <span data-ttu-id="544bc-142">Implementiert die Cmdlets **Invoke-Sqlcmd** und **Invoke-PolicyEvaluation** .</span><span class="sxs-lookup"><span data-stu-id="544bc-142">Implements the **Invoke-Sqlcmd** and **Invoke-PolicyEvaluation** cmdlets.</span></span>  
  
 <span data-ttu-id="544bc-143">Das Hilfsprogramm `sqlps` kann für die folgenden Tasks verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="544bc-143">You can use the `sqlps` utility to do the following:</span></span>  
  
-   <span data-ttu-id="544bc-144">Interaktives Ausführen von PowerShell-Befehlen</span><span class="sxs-lookup"><span data-stu-id="544bc-144">Interactively run PowerShell commands.</span></span>  
  
-   <span data-ttu-id="544bc-145">Ausführen von PowerShell-Skriptdateien</span><span class="sxs-lookup"><span data-stu-id="544bc-145">Run PowerShell script files.</span></span>  
  
-   <span data-ttu-id="544bc-146">Ausführen von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Cmdlets</span><span class="sxs-lookup"><span data-stu-id="544bc-146">Run [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] cmdlets.</span></span>  
  
-   <span data-ttu-id="544bc-147">Verwenden Sie die [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Anbieterpfade, um durch die Hierarchie der [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Objekte zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="544bc-147">Use the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider paths to navigate through the hierarchy of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] objects.</span></span>  
  
 <span data-ttu-id="544bc-148">Standardmäßig wird das- `sqlps` Hilfsprogramm mit der Skript Ausführungs Richtlinie auf **restricted**festgelegt.</span><span class="sxs-lookup"><span data-stu-id="544bc-148">By default, the `sqlps` utility runs with the scripting execution policy set to **Restricted**.</span></span> <span data-ttu-id="544bc-149">Dadurch wird die Ausführung von PowerShell-Skripts verhindert.</span><span class="sxs-lookup"><span data-stu-id="544bc-149">This prevents running any PowerShell scripts.</span></span> <span data-ttu-id="544bc-150">Mit dem Cmdlet **Set-ExecutionPolicy** können Sie die Ausführung signierter Skripts oder beliebiger anderer Skripts ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="544bc-150">You can use the **Set-ExecutionPolicy** cmdlet to enable running signed scripts, or any scripts.</span></span> <span data-ttu-id="544bc-151">Führen Sie nur Skripts aus vertrauenswürdigen Quellen aus, und sichern Sie alle Eingabe- und Ausgabedateien, indem Sie die geeigneten NTFS-Berechtigungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="544bc-151">Only run scripts from trusted sources, and secure all input and output files by using the appropriate NTFS permissions.</span></span> <span data-ttu-id="544bc-152">Weitere Informationen zum Aktivieren von PowerShell-Skripts finden Sie unter [Ausführen der Windows PowerShell-Skripts](https://www.tech-recipes.com/rx/2513/powershell_enable_script_support/).</span><span class="sxs-lookup"><span data-stu-id="544bc-152">For more information about enabling PowerShell scripts, see [Running Windows PowerShell Scripts](https://www.tech-recipes.com/rx/2513/powershell_enable_script_support/).</span></span>  
  
 <span data-ttu-id="544bc-153">Die Version des Hilfsprogramms `sqlps` in [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] und [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] wurde als Windows PowerShell 1.0-Mini-Shell implementiert.</span><span class="sxs-lookup"><span data-stu-id="544bc-153">The version of the `sqlps` utility in [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] and [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] was implemented as a Windows PowerShell 1.0 mini-shell.</span></span> <span data-ttu-id="544bc-154">Mini-Shells weisen bestimmte Einschränkungen auf; Benutzer können beispielsweise keine anderen als die von der Mini-Shell geladenen Snap-Ins laden.</span><span class="sxs-lookup"><span data-stu-id="544bc-154">Mini-shells have certain restrictions, such as not allowing users to load snap-ins other than those loaded by the mini-shell.</span></span> <span data-ttu-id="544bc-155">Diese Einschränkungen gelten nicht für die [!INCLUDE[ssSQL11](../includes/sssql11-md.md)]-Version und höhere Versionen des Hilfsprogramms, die dahingehend geändert wurden, dass sie das `sqlps`-Modul verwenden.</span><span class="sxs-lookup"><span data-stu-id="544bc-155">These restrictions do not apply to the [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] and higher versions of the utility, which have been changed to use the `sqlps` module.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="544bc-156">Beispiele</span><span class="sxs-lookup"><span data-stu-id="544bc-156">Examples</span></span>  

### <a name="a-run-the-sqlps-utility-in-default-interactive-mode-without-the-copyright-banner"></a><span data-ttu-id="544bc-157">A.</span><span class="sxs-lookup"><span data-stu-id="544bc-157">A.</span></span> <span data-ttu-id="544bc-158">Ausführen des Hilfsprogramms sqlps im interaktiven Standardmodus ohne Copyrightinformationen</span><span class="sxs-lookup"><span data-stu-id="544bc-158">Run the sqlps utility in default, interactive mode without the copyright banner</span></span>
  
```cmd
sqlps -NoLogo  
```  
  
### <a name="b-run-a-sql-server-powershell-script-from-the-command-prompt"></a><span data-ttu-id="544bc-159">B.</span><span class="sxs-lookup"><span data-stu-id="544bc-159">B.</span></span> <span data-ttu-id="544bc-160">Ausführen eines SQL Server PowerShell-Skripts von der Eingabeaufforderung</span><span class="sxs-lookup"><span data-stu-id="544bc-160">Run a SQL Server PowerShell script from the command prompt</span></span>
  
```cmd
sqlps -Command "&{.\MyFolder.MyScript.ps1}"  
```  
  
### <a name="c-run-a-sql-server-powershell-script-from-the-command-prompt-and-keep-running-after-the-script-completes"></a><span data-ttu-id="544bc-161">C.</span><span class="sxs-lookup"><span data-stu-id="544bc-161">C.</span></span> <span data-ttu-id="544bc-162">Ausführen eines SQL Server PowerShell-Skripts von der Eingabeaufforderung und weitere Ausführung nach Abschluss des Skripts</span><span class="sxs-lookup"><span data-stu-id="544bc-162">Run a SQL Server PowerShell script from the command prompt, and keep running after the script completes</span></span>
  
```cmd
sqlps -NoExit -Command "&{.\MyFolder.MyScript.ps1}"  
```  
  
## <a name="see-also"></a><span data-ttu-id="544bc-163">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="544bc-163">See Also</span></span>  
 <span data-ttu-id="544bc-164">[Aktivieren oder Deaktivieren eines Servernetzwerkprotokolls](../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md) </span><span class="sxs-lookup"><span data-stu-id="544bc-164">[Enable or Disable a Server Network Protocol](../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md) </span></span>  
 [<span data-ttu-id="544bc-165">SQL Server-PowerShell</span><span class="sxs-lookup"><span data-stu-id="544bc-165">SQL Server PowerShell</span></span>](../powershell/sql-server-powershell.md)  
