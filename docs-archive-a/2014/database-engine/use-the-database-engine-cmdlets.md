---
title: Verwenden des Datenbank-Engine-Cmdlets | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Cmdlets [SQL Server], Encode-Sqlname
- Encode-Sqlname cmdlet
- PowerShell [SQL Server], Encode-Sqlname
- Convert-UrnToPath cmdlet
- PowerShell [SQL Server], cmdlets
- Cmdlets [SQL Server]
- PowerShell [SQL Server], Convert-UrnToPath
- Cmdlets [SQL Server], Convert-UrnToPath
- Decode-Sqlname cmdlet
- PowerShell [SQL Server], Decode-Sqlname
- Cmdlets [SQL Server], Decode-Sqlname
ms.assetid: 720aa982-09ae-41a3-b603-a91004cfbe3e
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 015500c7c985f9f1a1d190954406844f3b184932
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608795"
---
# <a name="use-the-database-engine-cmdlets"></a><span data-ttu-id="36e91-102">Verwenden der Datenbank-Engine-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="36e91-102">Use the Database Engine cmdlets</span></span>
  <span data-ttu-id="36e91-103"> Windows PowerShell-Cmdlets sind Einzelfunktionsbefehle, für die i.d.R. eine Verb-Substantiv-Namenskonvention gilt, z.B. **Get-Help** oder **Set-MachineName**.</span><span class="sxs-lookup"><span data-stu-id="36e91-103">Windows PowerShell cmdlets are single-function commands that typically have a verb-noun naming convention, such as **Get-Help** or **Set-MachineName**.</span></span> <span data-ttu-id="36e91-104">Der [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Anbieter für Windows PowerShell bietet für [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]spezifische Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="36e91-104">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider for Windows PowerShell supplies cmdlets specific to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="database-engine-cmdlets"></a><span data-ttu-id="36e91-105">Datenbank-Engine-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="36e91-105">Database Engine cmdlets</span></span>  
 [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="36e91-106">implementiert eine kleine Anzahl von Cmdlets für [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="36e91-106">implements a small number of cmdlets for the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span> <span data-ttu-id="36e91-107">Diese Cmdlets werden hauptsächlich zum Ausführen vorhandener Transact-SQL-Skripts aus neuen PowerShell-Skripts, Auswerten richtlinienbasierter Verwaltungsrichtlinien und Unterstützen beim Angeben von SQL Server-Bezeichnern in SQL Server-Anbieterpfaden verwendet.</span><span class="sxs-lookup"><span data-stu-id="36e91-107">These cmdlets are primarily used to run existing Transact-SQL scripts from new PowerShell scripts, evaluate policy-based management policies, and aid in specifying SQL Server identifiers in SQL Server Provider paths.</span></span>  
  
 <span data-ttu-id="36e91-108">Bei den meisten Windows PowerShell-Skripts wird [!INCLUDE[ssDE](../includes/ssde-md.md)] genutzt. Hierbei kommen der SQL Server PowerShell-Anbieter und SQL Server-Verwaltbarkeits-Objektmodelle zum Einsatz.</span><span class="sxs-lookup"><span data-stu-id="36e91-108">Most Windows PowerShell scripts work with the [!INCLUDE[ssDE](../includes/ssde-md.md)] by using the SQL Server PowerShell provider and the SQL Server manageability object models.</span></span> <span data-ttu-id="36e91-109">Weitere Informationen finden Sie unter [SQL Server-PowerShell](../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="36e91-109">For more information, see [SQL Server PowerShell](../powershell/sql-server-powershell.md).</span></span>  
  
### <a name="get-cmdlet-help"></a><span data-ttu-id="36e91-110">Get-Help-Cmdlet</span><span class="sxs-lookup"><span data-stu-id="36e91-110">Get Cmdlet Help</span></span>  
 <span data-ttu-id="36e91-111">In der Windows PowerShell-Umgebung stellt das **Get-Help** -Cmdlet Hilfeinformationen für jedes Cmdlet bereit.</span><span class="sxs-lookup"><span data-stu-id="36e91-111">In the Windows PowerShell environment, the **Get-Help** cmdlet provides help information for each cmdlet.</span></span> <span data-ttu-id="36e91-112">**Get-Help** gibt Informationen wie Syntax, Parameterdefinitionen, Eingabe- und Ausgabetypen und eine Beschreibung der vom Cmdlet durchgeführten Aktion zurück.</span><span class="sxs-lookup"><span data-stu-id="36e91-112">**Get-Help** returns information such as the syntax, parameter definitions, input and output types, and a description of the action performed by the cmdlet.</span></span> <span data-ttu-id="36e91-113">Weitere Informationen finden Sie unter [Get Help SQL Server PowerShell](../../2014/database-engine/get-help-sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="36e91-113">For more information, see [Get Help SQL Server PowerShell](../../2014/database-engine/get-help-sql-server-powershell.md).</span></span>  
  
### <a name="partial-parameter-names"></a><span data-ttu-id="36e91-114">Partielle Parameternamen</span><span class="sxs-lookup"><span data-stu-id="36e91-114">Partial Parameter Names</span></span>  
 <span data-ttu-id="36e91-115">Sie müssen nicht den ganzen Namen eines Cmdlet-Parameters angeben.</span><span class="sxs-lookup"><span data-stu-id="36e91-115">You do not have to specify the entire name of a cmdlet parameter.</span></span> <span data-ttu-id="36e91-116">Sie müssen nur so viele Zeichen des Namens eingeben, dass dieser eindeutig von den anderen Parametern unterschieden werden kann, die von dem Cmdlet unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="36e91-116">You only have to specify enough of the name to uniquely separate it from the other parameters that are supported by the cmdlet.</span></span> <span data-ttu-id="36e91-117">In diesen Beispielen werden drei Methoden zum Angeben des Parameters **Invoke-Sqlcmd-QueryTimeout** veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="36e91-117">For example, these examples show three ways of specifying the **Invoke-Sqlcmd -QueryTimeout** parameter:</span></span>  
  
```powershell
Invoke-Sqlcmd -Query "SELECT @@VERSION;" -QueryTimeout 3  
Invoke-Sqlcmd -Query "SELECT @@VERSION;" -QueryTime 3  
Invoke-Sqlcmd -Query "SELECT @@VERSION;" -QueryT 3  
```  
  
## <a name="database-engine-cmdlet-tasks"></a><span data-ttu-id="36e91-118">Cmdlet-Tasks der Datenbank-Engine</span><span class="sxs-lookup"><span data-stu-id="36e91-118">Database Engine cmdlet Tasks</span></span>  
  
|<span data-ttu-id="36e91-119">Taskbeschreibung</span><span class="sxs-lookup"><span data-stu-id="36e91-119">Task Description</span></span>|<span data-ttu-id="36e91-120">Thema</span><span class="sxs-lookup"><span data-stu-id="36e91-120">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="36e91-121">Beschreibt die Verwendung von **Invoke-Sqlcmd** zum Ausführen von **sqlcmd** -Skripts oder -Befehlen, die [!INCLUDE[tsql](../includes/tsql-md.md)] - oder XQuery-Anweisungen enthalten.</span><span class="sxs-lookup"><span data-stu-id="36e91-121">Describes using **Invoke-Sqlcmd** to run **sqlcmd** scripts or commands that contain [!INCLUDE[tsql](../includes/tsql-md.md)] or XQuery statements.</span></span> <span data-ttu-id="36e91-122">Die **sqlcmd** -Eingabe wird entweder als Zeichenfolgen-Eingabeparameter oder als Name einer zu öffnenden Skriptdatei akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="36e91-122">It can accept the **sqlcmd** input as either a character string input parameter, or as the name of a script file to open.</span></span>|[<span data-ttu-id="36e91-123">Invoke-Sqlcmd-Cmdlet</span><span class="sxs-lookup"><span data-stu-id="36e91-123">Invoke-Sqlcmd cmdlet</span></span>](../../2014/database-engine/invoke-sqlcmd-cmdlet.md)|  
|<span data-ttu-id="36e91-124">Beschreibt die Verwendung von **Invoke-PolicyEvaluation** zum Melden, ob ein Zielsatz von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Objekten den in richtlinienbasierten Verwaltungsrichtlinien definierten Bedingungen entspricht.</span><span class="sxs-lookup"><span data-stu-id="36e91-124">Describes using **Invoke-PolicyEvaluation** to report whether a target set of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] objects comply with the conditions that are defined in policy-based management policies.</span></span> <span data-ttu-id="36e91-125">Optional können mit dem Cmdlet alle festlegbaren Optionen in den Zielobjekten neu konfiguriert werden, die den Richtlinienbedingungen nicht entsprechen.</span><span class="sxs-lookup"><span data-stu-id="36e91-125">Optionally, the cmdlet can be used to reconfigure any settable options in the target objects that do not comply with the policy conditions.</span></span>|[<span data-ttu-id="36e91-126">Invoke-PolicyEvaluation-Cmdlet</span><span class="sxs-lookup"><span data-stu-id="36e91-126">Invoke-PolicyEvaluation cmdlet</span></span>](../../2014/database-engine/invoke-policyevaluation-cmdlet.md)|  
|<span data-ttu-id="36e91-127">Beschreibt die Verwendung von `Encode-Sqlname` und `Decode-Sqlname` zum Verarbeiten von SQL Server-Bezeichnern, die in Windows PowerShell-Pfaden nicht unterstützte Zeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="36e91-127">Describes using `Encode-Sqlname` and `Decode-Sqlname` to handle SQL Server identifiers that contain characters not supported in Windows PowerShell paths.</span></span>|[<span data-ttu-id="36e91-128">Codierung und Decodierung von SQL Server-Bezeichnern</span><span class="sxs-lookup"><span data-stu-id="36e91-128">Encode and Decode SQL Server Identifiers</span></span>](../powershell/encode-and-decode-sql-server-identifiers.md)|  
|<span data-ttu-id="36e91-129">Beschreibt die Verwendung von `Convert-UrnToPath` zum Konvertieren eines URN (Uniform Resource Name, einheitlicher Name für Ressourcen) für SQL Server-Verwaltbarkeitsobjekte in den entsprechenden Pfad des SQL Server-Anbieters.</span><span class="sxs-lookup"><span data-stu-id="36e91-129">Describes using `Convert-UrnToPath` to convert a SQL Server Manageability Object Uniform Resource Name (URN) to the equivalent SQL Server Provider path.</span></span>|[<span data-ttu-id="36e91-130">Konvertieren von URNs in SQL Server-Anbieterpfade</span><span class="sxs-lookup"><span data-stu-id="36e91-130">Convert URNs to SQL Server Provider Paths</span></span>](../../2014/database-engine/convert-urns-to-sql-server-provider-paths.md)|  
  
## <a name="see-also"></a><span data-ttu-id="36e91-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="36e91-131">See Also</span></span>  
 <span data-ttu-id="36e91-132">[SQL Server PowerShell Anbieter](../powershell/sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="36e91-132">[SQL Server PowerShell Provider](../powershell/sql-server-powershell-provider.md) </span></span>  
 <span data-ttu-id="36e91-133">[SQL Server PowerShell](../powershell/sql-server-powershell.md) </span><span class="sxs-lookup"><span data-stu-id="36e91-133">[SQL Server PowerShell](../powershell/sql-server-powershell.md) </span></span>  
 [<span data-ttu-id="36e91-134">Übersicht über PowerShell-Cmdlets für AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="36e91-134">Overview of PowerShell Cmdlets for AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](availability-groups/windows/overview-of-powershell-cmdlets-for-always-on-availability-groups-sql-server.md)  
  
  
