---
title: Invoke-PolicyEvaluation-Cmdlet | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, Invoke-PolicyEvaluation
- Policy-Based Management, PowerShell
- Invoke-PolicyEvaluation cmdlet
- Cmdlets [SQL Server], Invoke-PolicyEvaluation
- PowerShell [SQL Server], Invoke-PolicyEvaluation
ms.assetid: 3e6d4f5a-59b7-4203-b95a-f7e692c0f131
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 656fdffea191c9cf6fc42d860164bc5af1e04561
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698510"
---
# <a name="invoke-policyevaluation-cmdlet"></a><span data-ttu-id="d186c-102">Invoke-PolicyEvaluation-Cmdlet</span><span class="sxs-lookup"><span data-stu-id="d186c-102">Invoke-PolicyEvaluation cmdlet</span></span>
  <span data-ttu-id="d186c-103">**Invoke_PolicyEvaluation** ist ein [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Cmdlet, das meldet, ob ein Zielsatz von SQL Server-Objekten den Bedingungen entspricht, die in ein oder mehreren richtlinienbasierten Verwaltungsrichtlinien angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="d186c-103">**Invoke-PolicyEvaluation** is a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] cmdlet that reports whether a target set of SQL Server objects complies with the conditions specified in one or more Policy-Based Management policies.</span></span>  
  
## <a name="using-invoke-policyevaluation"></a><span data-ttu-id="d186c-104">Verwenden von Invoke-PolicyEvaluation</span><span class="sxs-lookup"><span data-stu-id="d186c-104">Using Invoke-PolicyEvaluation</span></span>  
 <span data-ttu-id="d186c-105">**Invoke-PolicyEvaluation** wertet ein oder mehrere Richtlinien für einen Satz von SQL Server-Objekten aus, der Zielsatz genannt wird.</span><span class="sxs-lookup"><span data-stu-id="d186c-105">**Invoke-PolicyEvaluation** evaluates one or more policies against a set of SQL Server objects called the target set.</span></span> <span data-ttu-id="d186c-106">Der Satz von Zielobjekten stammt von einem Zielserver.</span><span class="sxs-lookup"><span data-stu-id="d186c-106">The set of target objects comes from a target server.</span></span> <span data-ttu-id="d186c-107">Jede Richtlinie definiert Bedingungen, die die zulässigen Zustände für die Zielobjekte angeben.</span><span class="sxs-lookup"><span data-stu-id="d186c-107">Each policy defines conditions, which are the allowed states for the target objects.</span></span> <span data-ttu-id="d186c-108">Beispielsweise legt die Richtlinie **Vertrauenswürdige Datenbank** fest, dass die Datenbankeigenschaft TRUSTWORTHY auf OFF festgelegt werden muss.</span><span class="sxs-lookup"><span data-stu-id="d186c-108">For example, the **Trustworthy Database** policy states that the TRUSTWORTHY database property must be set to OFF.</span></span>  
  
 <span data-ttu-id="d186c-109">Der Parameter **-AdHocPolicyEvaluationMode** gibt die Aktionen an:</span><span class="sxs-lookup"><span data-stu-id="d186c-109">The **-AdHocPolicyEvaluationMode** parameter specifies the actions taken:</span></span>  
  
 <span data-ttu-id="d186c-110">Prüfen</span><span class="sxs-lookup"><span data-stu-id="d186c-110">Check</span></span>  
 <span data-ttu-id="d186c-111">Berichtet den Kompatibilitätsstatus der Zielobjekte unter Verwendung der Anmeldeinformationen Ihres aktuellen Anmeldenamens.</span><span class="sxs-lookup"><span data-stu-id="d186c-111">Report the compliance status of the target objects using the credentials of your current login.</span></span> <span data-ttu-id="d186c-112">Führt keine Neukonfiguration von Objekten aus.</span><span class="sxs-lookup"><span data-stu-id="d186c-112">Do no reconfigure any objects.</span></span> <span data-ttu-id="d186c-113">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="d186c-113">This is the default setting.</span></span>  
  
 <span data-ttu-id="d186c-114">CheckSqlScriptAsProxy</span><span class="sxs-lookup"><span data-stu-id="d186c-114">CheckSqlScriptAsProxy</span></span>  
 <span data-ttu-id="d186c-115">Meldet den Kompatibilitätsstatus der Zielobjekte unter Verwendung der Anmeldeinformationen des Proxyanmeldenamens **##MS_PolicyTSQLExecutionLogin##** .</span><span class="sxs-lookup"><span data-stu-id="d186c-115">Report the compliance status of the target objects using the credentials of the **##MS_PolicyTSQLExecutionLogin##** proxy login.</span></span> <span data-ttu-id="d186c-116">Führt keine Neukonfiguration von Objekten aus.</span><span class="sxs-lookup"><span data-stu-id="d186c-116">Do no reconfigure any objects.</span></span>  
  
 <span data-ttu-id="d186c-117">Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="d186c-117">Configure</span></span>  
 <span data-ttu-id="d186c-118">Berichtet den Kompatibilitätsstatus der Zielobjekte unter Verwendung der Anmeldeinformationen Ihres aktuellen Anmeldenamens.</span><span class="sxs-lookup"><span data-stu-id="d186c-118">Report the compliance status of the target objects using the credentials of your current login.</span></span> <span data-ttu-id="d186c-119">Konfiguriert alle festlegbaren und deterministischen Optionen neu, die nicht in Übereinstimmung mit den Richtlinien sind.</span><span class="sxs-lookup"><span data-stu-id="d186c-119">Reconfigure any settable and deterministic options that are not in compliance with the policies.</span></span>  
  
## <a name="specifying-polices"></a><span data-ttu-id="d186c-120">Angeben von Richtlinien</span><span class="sxs-lookup"><span data-stu-id="d186c-120">Specifying Polices</span></span>  
 <span data-ttu-id="d186c-121">Wie Sie eine Richtlinie angeben, hängt davon ab, wo die Richtlinie gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="d186c-121">How you specify a policy depends on where the policy is stored.</span></span> <span data-ttu-id="d186c-122">Richtlinien können in zwei Formaten gespeichert werden:</span><span class="sxs-lookup"><span data-stu-id="d186c-122">Policies can be stored in two formats:</span></span>  
  
-   <span data-ttu-id="d186c-123">Sie können als Objekte in einem Richtlinienspeicher gespeichert sein, wie z. B. eine Instanz der Datenbank-Engine.</span><span class="sxs-lookup"><span data-stu-id="d186c-123">They can be objects stored in a policy store, such as an instance of the Database Engine.</span></span> <span data-ttu-id="d186c-124">Sie können den Ordner SQLSERVER:\SQLPolicy verwenden, um den Speicherort von Richtlinien in einem Richtlinienspeicher anzugeben.</span><span class="sxs-lookup"><span data-stu-id="d186c-124">You can use the SQLSERVER:\SQLPolicy folder to specify the location of policies in a policy store.</span></span> <span data-ttu-id="d186c-125">Sie können Windows PowerShell-Cmdlets verwenden, um die Eingaberichtlinien basierend auf ihren Eigenschaften zu filtern. Beispielsweise können Sie Where-Object verwenden, um nach der Richtlinienkategorie zu filtern, oder Get-Item, um nach dem Richtliniennamen zu filtern.</span><span class="sxs-lookup"><span data-stu-id="d186c-125">You can use Windows PowerShell cmdlets to filter the input polices based on their properties, such as using Where-Object to filter on the policy category or Get-Item to filter on policy name.</span></span>  
  
-   <span data-ttu-id="d186c-126">Sie können als XML-Dateien exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="d186c-126">They can be exported as XML files.</span></span> <span data-ttu-id="d186c-127">Sie können ein Dateisystemlaufwerk verwenden, wie z. B. D:, um den Speicherort der XML-Dateien anzugeben.</span><span class="sxs-lookup"><span data-stu-id="d186c-127">You can use a file system drive, such as D:, to specify the location of the XML files.</span></span> <span data-ttu-id="d186c-128">Sie können Windows PowerShell-Cmdlets verwenden, wie z. B. Where-Object, um die Richtlinien nach ihren Dateieigenschaften zu filtern, wie z. B. nach dem Dateinamen.</span><span class="sxs-lookup"><span data-stu-id="d186c-128">You can use Windows PowerShell cmdlets such as Where-Object to filter the policies on their file properties, such as file name.</span></span>  
  
 <span data-ttu-id="d186c-129">Wenn die Richtlinien in einem Richtlinienspeicher gespeichert sind, müssen Sie einen Satz von PSObjects übergeben, der auf die auszuwertenden Richtlinien zeigt.</span><span class="sxs-lookup"><span data-stu-id="d186c-129">If the policies are stored in a policy store, you must pass in a set of PSObjects pointing to the policies to be evaluated.</span></span> <span data-ttu-id="d186c-130">Hierzu wird in der Regel die Ausgabe eines Cmdlets, wie z.B. Get-Item, an **Invoke-PolicyEvaluation**weitergeleitet. Es ist nicht erforderlich, dass Sie den Parameter **-Policy** angeben.</span><span class="sxs-lookup"><span data-stu-id="d186c-130">This is typically done by piping the output of a cmdlet such as Get-Item to **Invoke-PolicyEvaluation**, and does not require that you specify the **-Policy** parameter.</span></span> <span data-ttu-id="d186c-131">Wenn Sie beispielsweise die Microsoft Best Practices-Richtlinien in Ihre Instanz der Datenbank-Engine importiert haben, wertet dieser Befehl die Richtlinie **Datenbankstatus** aus:</span><span class="sxs-lookup"><span data-stu-id="d186c-131">For example, if you have imported the Microsoft Best Practices policies into your instance of the database engine, this command evaluates the **Database Status** policy:</span></span>  
  
```powershell
sl "SQLSERVER:\SQLPolicy\MyComputer\DEFAULT\Policies"  
Get-Item "Database Status" | Invoke-PolicyEvaluation -TargetServerName "MYCOMPUTER"  
```  
  
 <span data-ttu-id="d186c-132">Dieses Beispiel zeigt, wie mit „Where-Object“ mehrere Richtlinien basierend auf ihrer **PolicyCategory** -Eigenschaft aus einem Richtlinienspeicher gefiltert werden.</span><span class="sxs-lookup"><span data-stu-id="d186c-132">This example shows using Where-Object to filter multiple policies from a policy store based on their **PolicyCategory** property.</span></span> <span data-ttu-id="d186c-133">Die Objekte aus der weitergereichten Ausgabe von **Where-Object** werden von **Invoke-PolicyEvaluation**genutzt.</span><span class="sxs-lookup"><span data-stu-id="d186c-133">The objects from the piped output of **Where-Object** is consumed by **Invoke-PolicyEvaluation**.</span></span>  
  
```powershell
sl "SQLSERVER:\SQLPolicy\MyComputer\DEFAULT\Policies"  
gci | Where-Object {$_.PolicyCategory -eq "Microsoft Best Practices: Maintenance"} | Invoke-PolicyEvaluation -TargetServer "MYCOMPUTER"  
```  
  
 <span data-ttu-id="d186c-134">Wenn die Richtlinien als XML-Dateien gespeichert werden, müssen Sie den **-Policy** -Parameter verwenden, um für jede Richtlinie den Pfad und den Namen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="d186c-134">If the policies are stored as XML files, you must use the **-Policy** parameter to supply both the path and name for each policy.</span></span> <span data-ttu-id="d186c-135">Wenn Sie keinen Pfad im Parameter **-Policy** angeben, verwendet **Invoke-PolicyEvaluation** die aktuelle Einstellung des **sqlps** -Pfads.</span><span class="sxs-lookup"><span data-stu-id="d186c-135">If you do not specify a path in the **-Policy** parameter, **Invoke-PolicyEvaulation** uses the current setting of the **sqlps** path.</span></span> <span data-ttu-id="d186c-136">Beispielsweise wertet dieser Befehl eine der Microsoft Best Practice-Richtlinien, die mit SQL Server installiert wurden, anhand der Standarddatenbank für Ihren Anmeldenamen aus:</span><span class="sxs-lookup"><span data-stu-id="d186c-136">For example, this command evaluates one of the Microsoft Best Practice policies installed with SQL Server against the default database for your login:</span></span>  
  
```powershell
Invoke-PolicyEvaluation -Policy "C:\Program Files\Microsoft SQL Server\120\Tools\Policies\DatabaseEngine\1033\Database Status.xml" -TargetServerName "MYCOMPUTER"  
```  
  
 <span data-ttu-id="d186c-137">Dieser Befehl bewirkt dasselbe, verwendet jedoch den aktuellen **sqlps** -Pfad, um den Speicherort der XML-Richtliniendatei einzurichten:</span><span class="sxs-lookup"><span data-stu-id="d186c-137">This command does the same thing, only it uses the current **sqlps** path to establish the location of the policy XML file:</span></span>  
  
```powershell
sl "C:\Program Files\Microsoft SQL Server\120\Tools\Policies\DatabaseEngine\1033"  
Invoke-PolicyEvaluation -Policy "Database Status.xml" -TargetServerName "MYCOMPUTER"  
```  
  
 <span data-ttu-id="d186c-138">Dieses Beispiel zeigt die Verwendung des Cmdlets **PolicyCategory** , um mehrere XML-Richtliniendateien abzurufen und die Objekte an **Invoke-PolicyEvaluation**weiterzureichen:</span><span class="sxs-lookup"><span data-stu-id="d186c-138">This example shows using the **Get-ChildItem** cmdlet to retrieve multiple policy XML files and pipe the objects into **Invoke-PolicyEvaluation**:</span></span>  
  
```powershell
sl "C:\Program Files\Microsoft SQL Server\120\Tools\Policies\DatabaseEngine\1033"  
gci "Database Status.xml", "Trustworthy Database.xml" | Invoke-PolicyEvaluation -TargetServer "MYCOMPUTER"  
```  
  
## <a name="specifying-the-target-set"></a><span data-ttu-id="d186c-139">Angeben des Zielsatzes</span><span class="sxs-lookup"><span data-stu-id="d186c-139">Specifying the Target Set</span></span>  
 <span data-ttu-id="d186c-140">Mithilfe von drei Parametern können Sie den Satz der Zielobjekte angeben:</span><span class="sxs-lookup"><span data-stu-id="d186c-140">Use three parameters to specify the set of target objects:</span></span>  
  
-   <span data-ttu-id="d186c-141">**-TargetServerName** gibt die Instanz von SQL Server an, die die Zielobjekte enthält.</span><span class="sxs-lookup"><span data-stu-id="d186c-141">**-TargetServerName** specifies the instance of SQL Server containing the target objects.</span></span> <span data-ttu-id="d186c-142">Sie können die Informationen in einer Zeichenfolge angeben, die das für die ConnectionString-Eigenschaft der <xref:System.Data.SqlClient.SqlConnection> -Klasse definierte Format verwendet.</span><span class="sxs-lookup"><span data-stu-id="d186c-142">You can specify the information in a string that uses the format defined for the ConnectionString property of the <xref:System.Data.SqlClient.SqlConnection> class.</span></span> <span data-ttu-id="d186c-143">Sie können die <xref:System.Data.SqlClient.SqlConnectionStringBuilder> -Klasse verwenden, um eine ordnungsgemäß formatierte Verbindungszeichenfolge zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d186c-143">You can use the <xref:System.Data.SqlClient.SqlConnectionStringBuilder> class to build a correctly formatted connection string.</span></span> <span data-ttu-id="d186c-144">Sie können auch ein <xref:Microsoft.SqlServer.Management.Sdk.Sfc.SqlStoreConnection> -Objekt erstellen und an **-TargetServer**genutzt.</span><span class="sxs-lookup"><span data-stu-id="d186c-144">You can also create a <xref:Microsoft.SqlServer.Management.Sdk.Sfc.SqlStoreConnection> object and pass it to **-TargetServer**.</span></span> <span data-ttu-id="d186c-145">Wenn Sie eine Zeichenfolge angeben, die nur den Namen des Servers enthält, verwendet **Invoke-PolicyEvaluation** die Windows-Authentifizierung, um eine Verbindung mit dem Server herzustellen.</span><span class="sxs-lookup"><span data-stu-id="d186c-145">If you supply a string that has only the name of the server, **Invoke-PolicyEvaluation** uses Windows Authentication to connect to the server.</span></span>  
  
-   <span data-ttu-id="d186c-146">**-TargetObjects** nimmt ein Objekt oder ein Array von Objekten entgegen, das die SQL Server-Objekte im Zielsatz darstellt.</span><span class="sxs-lookup"><span data-stu-id="d186c-146">**-TargetObjects** takes an object or array of objects that represent the SQL Server objects in the target set.</span></span> <span data-ttu-id="d186c-147">Beispielsweise könnten Sie ein Array von <xref:Microsoft.SqlServer.Management.Smo.Database> -Klassenobjekten erstellen, um es an **-TargetObjects**genutzt.</span><span class="sxs-lookup"><span data-stu-id="d186c-147">For example, you could create an array of <xref:Microsoft.SqlServer.Management.Smo.Database> class objects to pass in to **-TargetObjects**.</span></span>  
  
-   <span data-ttu-id="d186c-148">**-TargetExpressions** nimmt eine Zeichenfolge mit einem Abfrageausdruck entgegen, der die Objekte im Zielsatz angibt.</span><span class="sxs-lookup"><span data-stu-id="d186c-148">**-TargetExpressions** takes a string containing a query expression that specifies the objects in the target set.</span></span> <span data-ttu-id="d186c-149">Der Abfrageausdruck liegt in Form von Knoten vor, die durch das Zeichen '/' getrennt sind.</span><span class="sxs-lookup"><span data-stu-id="d186c-149">The query expression is in the form of nodes separated by the '/' character.</span></span> <span data-ttu-id="d186c-150">Jeder Knoten hat das Format ObjectType [Filter].</span><span class="sxs-lookup"><span data-stu-id="d186c-150">Each node is in the form ObjectType[Filter].</span></span> <span data-ttu-id="d186c-151">Der Objekttyp ist eines der Objekte in einer SMO-Objekthierarchie (SQL Server Management Object).</span><span class="sxs-lookup"><span data-stu-id="d186c-151">Object type is one of the objects in a SQL Server Management Object (SMO) object hierarchy.</span></span> <span data-ttu-id="d186c-152">"Filter" ist ein Ausdruck, der bei diesem Knoten nach Objekten filtert.</span><span class="sxs-lookup"><span data-stu-id="d186c-152">Filter is an expression that filters for objects at that node.</span></span> <span data-ttu-id="d186c-153">Weitere Informationen finden Sie unter [Query Expressions and Uniform Resource Names](../powershell/query-expressions-and-uniform-resource-names.md).</span><span class="sxs-lookup"><span data-stu-id="d186c-153">For more information, see [Query Expressions and Uniform Resource Names](../powershell/query-expressions-and-uniform-resource-names.md).</span></span>  
  
 <span data-ttu-id="d186c-154">Geben Sie entweder **-TargetObjects** oder **-TargetExpression**, aber nicht beides an.</span><span class="sxs-lookup"><span data-stu-id="d186c-154">Specify either **-TargetObjects** or **-TargetExpression**, not both.</span></span>  
  
 <span data-ttu-id="d186c-155">In diesem Beispiel wird ein Sfc.SqlStoreConnection-Objekt verwendet, um den Zielserver anzugeben:</span><span class="sxs-lookup"><span data-stu-id="d186c-155">This example uses an Sfc.SqlStoreConnection object to specify the target server:</span></span>  
  
```powershell
sl "C:\Program Files\Microsoft SQL Server\120\Tools\Policies\DatabaseEngine\1033"  
$conn = New-Object Microsoft.SqlServer.Management.Sdk.Sfc.SqlStoreConnection("server='MYCOMPUTER';Trusted_Connection=True")  
Invoke-PolicyEvaluation -Policy "Database Status.xml" -TargetServerName $conn  
```  
  
 <span data-ttu-id="d186c-156">In diesem Beispiel wird **-TargetExpression** verwendet, um eine bestimmte auszuwertende Datenbank anzugeben:</span><span class="sxs-lookup"><span data-stu-id="d186c-156">This example uses **-TargetExpression** to identify the specific database to evaluate:</span></span>  
  
```powershell
sl "C:\Program Files\Microsoft SQL Server\120\Tools\Policies\DatabaseEngine\1033"  
Invoke-PolicyEvaluation -Policy "Database Status.xml" -TargetServerName "MyComputer" -TargetExpression "Server[@Name='MYCOMPUTER']/Database[@Name='AdventureWorks2012']"  
```  
  
## <a name="evaluating-analysis-services-policies"></a><span data-ttu-id="d186c-157">Auswerten von Analysis Services-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="d186c-157">Evaluating Analysis Services Policies</span></span>  
 <span data-ttu-id="d186c-158">Um Richtlinien anhand einer Instanz von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]auszuwerten, müssen Sie eine Assembly in PowerShell laden und registrieren, eine Variable mit einem Analysis Services-Verbindungsobjekt erstellen und die Variable an den Parameter **-TargetObject** übergeben.</span><span class="sxs-lookup"><span data-stu-id="d186c-158">To evaluate policies against an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], you must load and register an assembly into PowerShell, create a variable with an Analysis Services connection object, and pass the variable to the **-TargetObject** parameter.</span></span> <span data-ttu-id="d186c-159">Dieses Beispiel zeigt das Auswerten der Best Practices-Oberflächenkonfigurationsrichtlinie für [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="d186c-159">This example shows evaluating the Best Practices surface area configuration policy for [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]:</span></span>  
  
```powershell
sl "C:\Program Files\Microsoft SQL Server\120\Tools\Policies\AnalysisServices\1033"  
[System.Reflection.Assembly]::LoadWithPartialName("Microsoft.AnalysisServices")  
$SSASsvr = New-Object Microsoft.AnalysisServices.Server  
$SSASsvr.Connect("Data Source=Localhost")  
Invoke-PolicyEvaluation -Policy "Surface Area Configuration for Analysis Services Features.xml" -TargetObject $SSASsvr  
```  
  
## <a name="evaluating-reporting-services-policies"></a><span data-ttu-id="d186c-160">Auswerten von Reporting Services-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="d186c-160">Evaluating Reporting Services Policies</span></span>  
 <span data-ttu-id="d186c-161">Um [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Richtlinien auszuwerten, müssen Sie eine Assembly in PowerShell laden und registrieren, eine Variable mit einem [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Verbindungsobjekt erstellen und die Variable an den Parameter **-TargetObject** übergeben.</span><span class="sxs-lookup"><span data-stu-id="d186c-161">To evaluate [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] policies, you must load and register an assembly into PowerShell, create a variable with a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] connection object, and pass the variable to the **-TargetObject** parameter.</span></span> <span data-ttu-id="d186c-162">Dieses Beispiel zeigt das Auswerten der Best Practices-Oberflächenkonfigurationsrichtlinie für [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="d186c-162">This example shows evaluating the Best Practices surface area configuration policy for [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]:</span></span>  
  
```powershell
sl "C:\Program Files\Microsoft SQL Server\120\Tools\Policies\ReportingServices\1033"  
[System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SqlServer.Dmf.Adapters")  
$SSRSsvr = new-object Microsoft.SqlServer.Management.Adapters.RSContainer('MyComputer')  
Invoke-PolicyEvaluation -Policy "Surface Area Configuration for Reporting Services 2008 Features.xml" -TargetObject $SSRSsvr  
```  
  
## <a name="formatting-output"></a><span data-ttu-id="d186c-163">Formatieren der Ausgabe</span><span class="sxs-lookup"><span data-stu-id="d186c-163">Formatting Output</span></span>  
 <span data-ttu-id="d186c-164">Standardmäßig wird die Ausgabe von **Invoke-PolicyEvaluation** im Eingabeaufforderungsfenster als Kurzbericht in Klartextform angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d186c-164">By default, the output of **Invoke-PolicyEvaluation** is displayed in the command prompt window as a concise report in human-readable format.</span></span> <span data-ttu-id="d186c-165">Sie können den Parameter **-OutputXML** verwenden, um festzulegen, dass das Cmdlet stattdessen einen detaillierten Bericht als XML-Datei erstellt.</span><span class="sxs-lookup"><span data-stu-id="d186c-165">You can use the **-OutputXML** parameter to specify that the cmdlet instead produce a detailed report as an XML file.</span></span> <span data-ttu-id="d186c-166">**Invoke-PolicyEvaluation** verwendet das SML-IF-Schema (Systems Modeling Language Interchange Format), sodass die Datei von SML-IF-Readern gelesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="d186c-166">**Invoke-PolicyEvaluation** uses the Systems Modeling Language Interchange Format (SML-IF) schema so the file can be read by SML-IF readers.</span></span>  
  
```powershell
sl "SQLSERVER:\SQLPolicy\MyComputer\DEFAULT\Policies"  
Invoke-PolicyEvaluation -Policy "Datbase Status" -TargetServer "MYCOMPUTER" -OutputXML > C:\MyReports\DatabaseStatusReport.xml  
```  
  
## <a name="see-also"></a><span data-ttu-id="d186c-167">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d186c-167">See Also</span></span>  
 [<span data-ttu-id="d186c-168">Verwenden der Datenbank-Engine-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="d186c-168">Use the Database Engine cmdlets</span></span>](../../2014/database-engine/use-the-database-engine-cmdlets.md)  
