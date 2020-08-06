---
title: Erstellen, ändern und Löschen von benutzerdefinierten Funktionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- user-defined functions [SMO]
ms.assetid: 0ebebd3b-0775-41c2-989d-aa4cf81af12a
author: stevestein
ms.author: sstein
ms.openlocfilehash: b9ff6d1b6e675d41e96f26fc24e6e0dd4ba69454
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621979"
---
# <a name="creating-altering-and-removing-user-defined-functions"></a><span data-ttu-id="10915-102">Erstellen, Ändern und Löschen von benutzerdefinierten Funktionen</span><span class="sxs-lookup"><span data-stu-id="10915-102">Creating, Altering, and Removing User-Defined Functions</span></span>
  <span data-ttu-id="10915-103">Das- <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction> Objekt stellt Funktionen bereit, mit denen Benutzer benutzerdefinierte Funktionen in Programm gesteuert verwalten können [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="10915-103">The <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction> object provides functionality that lets users programmatically manage user-defined functions in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="10915-104">Benutzerdefinierte Funktionen unterstützen sowohl Eingabe- und Ausgabeparameter als auch direkte Verweise auf Tabellenspalten.</span><span class="sxs-lookup"><span data-stu-id="10915-104">User-defined functions support input and output parameters, and also support direct references to table columns.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="10915-105">erfordert, dass Assemblys in einer Datenbank registriert werden, bevor diese in gespeicherten Prozeduren, benutzerdefinierten Funktionen, Trigger und benutzerdefinierten Datentypen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="10915-105">requires assemblies to be registered within a database before these can be used inside stored procedures, user defined functions, triggers, and user defined data types.</span></span> <span data-ttu-id="10915-106">SMO unterstützt diese Funktion mit dem <xref:Microsoft.SqlServer.Management.Smo.SqlAssembly>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="10915-106">SMO supports this feature with the <xref:Microsoft.SqlServer.Management.Smo.SqlAssembly> object.</span></span>  
  
 <span data-ttu-id="10915-107">Das <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction>-Objekt verweist auf die .NET-Assembly mit den Eigenschaften <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction.AssemblyName%2A>, <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction.ClassName%2A> und <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction.MethodName%2A>.</span><span class="sxs-lookup"><span data-stu-id="10915-107">The <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction> object references the .NET assembly with the <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction.AssemblyName%2A>, <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction.ClassName%2A>, and <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction.MethodName%2A> properties.</span></span>  
  
 <span data-ttu-id="10915-108">Wenn das <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction>-Objekt auf eine .NET-Assembly verweist, müssen Sie die Assembly registrieren, indem Sie ein <xref:Microsoft.SqlServer.Management.Smo.SqlAssembly>-Objekt erstellen und dieses dem <xref:Microsoft.SqlServer.Management.Smo.SqlAssemblyCollection>-Objekt hinzufügen, das zum <xref:Microsoft.SqlServer.Management.Smo.Database>-Objekt gehört.</span><span class="sxs-lookup"><span data-stu-id="10915-108">When the <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction> object references a .NET assembly, you must register the assembly by creating a <xref:Microsoft.SqlServer.Management.Smo.SqlAssembly> object and adding it to the <xref:Microsoft.SqlServer.Management.Smo.SqlAssemblyCollection> object, which belongs to the <xref:Microsoft.SqlServer.Management.Smo.Database> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="10915-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="10915-109">Example</span></span>  
 <span data-ttu-id="10915-110">Zum Verwenden eines angegebenen Codebeispiels müssen Sie die Programmierumgebung, Programmiervorlage und die zu verwendende Programmiersprache auswählen, um Ihre Anwendung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="10915-110">To use any code example that is provided, you will have to choose the programming environment, the programming template, and the programming language in which to create your application.</span></span> <span data-ttu-id="10915-111">Weitere Informationen finden Sie unter [Erstellen eines Visual Basic SMO-Projekts in Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) oder [Erstellen eines Visual C&#35; SMO-Projekts in Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="10915-111">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) or [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="creating-a-scalar-user-defined-function-in-visual-basic"></a><span data-ttu-id="10915-112">Erstellen einer benutzerdefinierten Skalarfunktion in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="10915-112">Creating a Scalar User-Defined Function in Visual Basic</span></span>  
 <span data-ttu-id="10915-113">In diesem Codebeispiel wird gezeigt, wie in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] eine benutzerdefinierte Skalarfunktion erstellt und gelöscht wird, die über einen <xref:System.DateTime>-Eingabeobjektparameter und einen ganzzahligen Rückgabetyp verfügt.</span><span class="sxs-lookup"><span data-stu-id="10915-113">This code example shows how to create and remove a scalar user-defined function that has an input <xref:System.DateTime> object parameter and an integer return type in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)].</span></span> <span data-ttu-id="10915-114">Die benutzerdefinierte Funktion wird für die [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] -Datenbank erstellt.</span><span class="sxs-lookup"><span data-stu-id="10915-114">The user-defined function is created on the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] database.</span></span> <span data-ttu-id="10915-115">Im Beispiel wird die benutzerdefinierte Funktion ISOweek erstellt, die ein Datumsargument annimmt und die Nummer der ISO-Woche berechnet.</span><span class="sxs-lookup"><span data-stu-id="10915-115">The example creates a user-defined function, ISOweek, which takes a date argument and calculates the ISO week number.</span></span> <span data-ttu-id="10915-116">Damit diese Funktion ordnungsgemäß berechnet wird, muss die DATEFIRST-Option der Datenbank auf 1 festgelegt werden, bevor die Funktion aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="10915-116">For this function to calculate correctly, the database DATEFIRST option must be set to 1 before the function is called.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBUserDefFuncs1](SMO How to#SMO_VBUserDefFuncs1)]  -->  
  
## <a name="creating-a-scalar-user-defined-function-in-visual-c"></a><span data-ttu-id="10915-117">Erstellen einer benutzerdefinierten Skalarfunktion in Visual C#</span><span class="sxs-lookup"><span data-stu-id="10915-117">Creating a Scalar User-Defined Function in Visual C#</span></span>  
 <span data-ttu-id="10915-118">In diesem Codebeispiel wird gezeigt, wie in [!INCLUDE[csprcs](../../../includes/csprcs-md.md)] eine benutzerdefinierte Skalarfunktion erstellt und gelöscht wird, die über einen <xref:System.DateTime>-Eingabeobjektparameter und einen ganzzahligen Rückgabetyp verfügt.</span><span class="sxs-lookup"><span data-stu-id="10915-118">This code example shows how to create and remove a scalar user-defined function that has an input <xref:System.DateTime> object parameter and an integer return type in [!INCLUDE[csprcs](../../../includes/csprcs-md.md)].</span></span> <span data-ttu-id="10915-119">Die benutzerdefinierte Funktion wird für die [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] -Datenbank erstellt.</span><span class="sxs-lookup"><span data-stu-id="10915-119">The user-defined function is created on the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] database.</span></span> <span data-ttu-id="10915-120">Im Beispiel wird die folgende benutzerdefinierte Funktion erstellt.</span><span class="sxs-lookup"><span data-stu-id="10915-120">The example creates the user-defined function.</span></span> <span data-ttu-id="10915-121">`ISOweek`.</span><span class="sxs-lookup"><span data-stu-id="10915-121">`ISOweek`.</span></span> <span data-ttu-id="10915-122">Diese Funktion nimmt ein Datumsargument an und berechnet die Nummer der ISO-Woche.</span><span class="sxs-lookup"><span data-stu-id="10915-122">This function takes a date argument and calculates the ISO week number.</span></span> <span data-ttu-id="10915-123">Damit diese Funktion richtige Werte berechnet, muss die Datenbankoption `DATEFIRST` auf `1` festgelegt werden, bevor die Funktion aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="10915-123">For this function to calculate correctly, the database `DATEFIRST` option must be set to `1` before the function is called.</span></span>  
  
```csharp
{  
            //Connect to the local, default instance of SQL Server.   
           Server srv = new Server();  
            //Reference the AdventureWorks2012 database.   
           Database db = srv.Databases["AdventureWorks2012"];  
  
            //Define a UserDefinedFunction object variable by supplying the parent database and the name arguments in the constructor.   
            UserDefinedFunction udf = new UserDefinedFunction(db, "IsOWeek");  
  
            //Set the TextMode property to false and then set the other properties.   
            udf.TextMode = false;  
            udf.DataType = DataType.Int;  
            udf.ExecutionContext = ExecutionContext.Caller;  
            udf.FunctionType = UserDefinedFunctionType.Scalar;  
            udf.ImplementationType = ImplementationType.TransactSql;  
  
            //Add a parameter.   
  
     UserDefinedFunctionParameter par = new UserDefinedFunctionParameter(udf, "@DATE", DataType.DateTime);  
            udf.Parameters.Add(par);  
  
            //Set the TextBody property to define the user-defined function.   
            udf.TextBody = "BEGIN DECLARE @ISOweek int SET @ISOweek= DATEPART(wk,@DATE)+1 -DATEPART(wk,CAST(DATEPART(yy,@DATE) as CHAR(4))+'0104') IF (@ISOweek=0) SET @ISOweek=dbo.ISOweek(CAST(DATEPART(yy,@DATE)-1 AS CHAR(4))+'12'+ CAST(24+DATEPART(DAY,@DATE) AS CHAR(2)))+1 IF ((DATEPART(mm,@DATE)=12) AND ((DATEPART(dd,@DATE)-DATEPART(dw,@DATE))>= 28)) SET @ISOweek=1 RETURN(@ISOweek) END;";  
  
            //Create the user-defined function on the instance of SQL Server.   
            udf.Create();  
  
            //Remove the user-defined function.   
            udf.Drop();  
        }  
```  
  
## <a name="creating-a-scalar-user-defined-function-in-powershell"></a><span data-ttu-id="10915-124">Erstellen einer benutzerdefinierten Skalarfunktion in PowerShell</span><span class="sxs-lookup"><span data-stu-id="10915-124">Creating a Scalar User-Defined Function in PowerShell</span></span>  
 <span data-ttu-id="10915-125">In diesem Codebeispiel wird gezeigt, wie in [!INCLUDE[csprcs](../../../includes/csprcs-md.md)] eine benutzerdefinierte Skalarfunktion erstellt und gelöscht wird, die über einen <xref:System.DateTime>-Eingabeobjektparameter und einen ganzzahligen Rückgabetyp verfügt.</span><span class="sxs-lookup"><span data-stu-id="10915-125">This code example shows how to create and remove a scalar user-defined function that has an input <xref:System.DateTime> object parameter and an integer return type in [!INCLUDE[csprcs](../../../includes/csprcs-md.md)].</span></span> <span data-ttu-id="10915-126">Die benutzerdefinierte Funktion wird für die [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] -Datenbank erstellt.</span><span class="sxs-lookup"><span data-stu-id="10915-126">The user-defined function is created on the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] database.</span></span> <span data-ttu-id="10915-127">Im Beispiel wird die folgende benutzerdefinierte Funktion erstellt.</span><span class="sxs-lookup"><span data-stu-id="10915-127">The example creates the user-defined function.</span></span> <span data-ttu-id="10915-128">`ISOweek`.</span><span class="sxs-lookup"><span data-stu-id="10915-128">`ISOweek`.</span></span> <span data-ttu-id="10915-129">Diese Funktion nimmt ein Datumsargument an und berechnet die Nummer der ISO-Woche.</span><span class="sxs-lookup"><span data-stu-id="10915-129">This function takes a date argument and calculates the ISO week number.</span></span> <span data-ttu-id="10915-130">Damit diese Funktion richtige Werte berechnet, muss die Datenbankoption `DATEFIRST` auf `1` festgelegt werden, bevor die Funktion aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="10915-130">For this function to calculate correctly, the database `DATEFIRST` option must be set to `1` before the function is called.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server and get a reference to AdventureWorks2012  
CD \sql\localhost\default\databases  
$db = Get-Item Adventureworks2012  
  
# Define a user defined function object variable by supplying the parent database and name arguments in the constructor.
$udf  = New-Object -TypeName Microsoft.SqlServer.Management.SMO.UserDefinedFunction -argumentlist $db, "IsOWeek"  
  
# Set the TextMode property to false and then set the other properties.
$udf.TextMode = $false  
$udf.DataType = [Microsoft.SqlServer.Management.SMO.DataType]::Int
$udf.ExecutionContext = [Microsoft.SqlServer.Management.SMO.ExecutionContext]::Caller  
$udf.FunctionType = [Microsoft.SqlServer.Management.SMO.UserDefinedFunctionType]::Scalar  
$udf.ImplementationType = [Microsoft.SqlServer.Management.SMO.ImplementationType]::TransactSql  
  
# Define a Parameter object variable by supplying the parent function, name and type arguments in the constructor.  
$type = [Microsoft.SqlServer.Management.SMO.DataType]::DateTime  
$par  = New-Object -TypeName Microsoft.SqlServer.Management.SMO.UserDefinedFunctionParameter -argumentlist $udf, "@DATE",$type  
  
# Add the parameter to the function  
$udf.Parameters.Add($par)  
  
#Set the TextBody property to define the user-defined function.
$udf.TextBody = "BEGIN DECLARE @ISOweek int SET @ISOweek= DATEPART(wk,@DATE)+1 -DATEPART(wk,CAST(DATEPART(yy,@DATE) as CHAR(4))+'0104') IF (@ISOweek=0) SET @ISOweek=dbo.ISOweek(CAST(DATEPART(yy,@DATE)-1 AS CHAR(4))+'12'+ CAST(24+DATEPART(DAY,@DATE) AS CHAR(2)))+1 IF ((DATEPART(mm,@DATE)=12) AND ((DATEPART(dd,@DATE)-DATEPART(dw,@DATE))>= 28)) SET @ISOweek=1 RETURN(@ISOweek) END;"  
  
# Create the user-defined function on the instance of SQL Server.
$udf.Create()  
  
# Remove the user-defined function.
$udf.Drop()  
```  
  
## <a name="see-also"></a><span data-ttu-id="10915-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="10915-131">See Also</span></span>  
 <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction>  
