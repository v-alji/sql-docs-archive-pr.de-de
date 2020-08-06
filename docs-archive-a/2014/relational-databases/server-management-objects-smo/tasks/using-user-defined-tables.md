---
title: Verwenden von benutzerdefinierten Tabellen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- user-defined tables [SQL Server]
ms.assetid: 620a4e1f-9678-4711-ae09-bcf7c9cae724
author: stevestein
ms.author: sstein
ms.openlocfilehash: 869bff26dc6801a6844e31b11322eb43515f3eac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725361"
---
# <a name="using-user-defined-tables"></a><span data-ttu-id="e73ea-102">Verwenden von benutzerdefinierten Tabellen</span><span class="sxs-lookup"><span data-stu-id="e73ea-102">Using User-Defined Tables</span></span>
  <span data-ttu-id="e73ea-103">Benutzerdefinierte Tabellen stellen Tabelleninformationen dar.</span><span class="sxs-lookup"><span data-stu-id="e73ea-103">User-defined tables represent tabular information.</span></span> <span data-ttu-id="e73ea-104">Sie werden als Parameter verwendet, wenn Sie Tabellendaten in gespeicherte Prozeduren oder benutzerdefinierte Funktionen übergeben.</span><span class="sxs-lookup"><span data-stu-id="e73ea-104">They are used as parameters when you pass tabular data into stored procedures or user-defined functions.</span></span> <span data-ttu-id="e73ea-105">Benutzerdefinierte Tabellen können nicht verwendet werden, um Spalten in einer Datenbanktabelle darzustellen.</span><span class="sxs-lookup"><span data-stu-id="e73ea-105">User-defined tables cannot be used to represent columns in a database table.</span></span>  
  
 <span data-ttu-id="e73ea-106">Das <xref:Microsoft.SqlServer.Management.Smo.Database>-Objekt verfügt über eine <xref:Microsoft.SqlServer.Management.Smo.Database.UserDefinedTableTypes%2A>-Eigenschaft, die auf ein <xref:Microsoft.SqlServer.Management.Smo.UserDefinedTableTypeCollection>-Objekt verweist.</span><span class="sxs-lookup"><span data-stu-id="e73ea-106">The <xref:Microsoft.SqlServer.Management.Smo.Database> object has a <xref:Microsoft.SqlServer.Management.Smo.Database.UserDefinedTableTypes%2A> property that references a <xref:Microsoft.SqlServer.Management.Smo.UserDefinedTableTypeCollection> object.</span></span> <span data-ttu-id="e73ea-107">Jedes- <xref:Microsoft.SqlServer.Management.Smo.UserDefinedTableType> Objekt in dieser Auflistung verfügt über eine **Columns** -Eigenschaft, die auf eine Auflistung von-Objekten verweist, die <xref:Microsoft.SqlServer.Management.Smo.Column> die Spalten in der benutzerdefinierten Tabelle auflisten.</span><span class="sxs-lookup"><span data-stu-id="e73ea-107">Each <xref:Microsoft.SqlServer.Management.Smo.UserDefinedTableType> object in that collection has a **Columns** property that refers to a collection of <xref:Microsoft.SqlServer.Management.Smo.Column> objects that list the columns in the user-defined table.</span></span> <span data-ttu-id="e73ea-108">Verwenden Sie die Add-Methode, um Spalten zu einer benutzerdefinierten Tabelle hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="e73ea-108">Use the Add method to add columns to the user-defined table.</span></span>  
  
 <span data-ttu-id="e73ea-109">Wenn Sie eine neue benutzerdefinierte Tabelle mithilfe des <xref:Microsoft.SqlServer.Management.Smo.UserDefinedTableType>-Objekts definieren, müssen Sie Spalten und einen Primärschlüssel basierend auf einer der Spalten bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="e73ea-109">When you define a new user-defined table by using the <xref:Microsoft.SqlServer.Management.Smo.UserDefinedTableType> object, you will have to supply columns and a primary key based on one of the columns.</span></span>  
  
 <span data-ttu-id="e73ea-110">Benutzerdefinierte Tabellentypen können nicht geändert werden, nachdem sie erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="e73ea-110">User-defined table types cannot be altered after they are created.</span></span> <span data-ttu-id="e73ea-111"><xref:Microsoft.SqlServer.Management.Smo.UserDefinedTableType> unterstützt nicht die Alter-Methode.</span><span class="sxs-lookup"><span data-stu-id="e73ea-111">The <xref:Microsoft.SqlServer.Management.Smo.UserDefinedTableType> does not support the Alter method.</span></span> <span data-ttu-id="e73ea-112">Benutzerdefinierte Tabellentypen können über CHECK-Einschränkungen verfügen. Allerdings lösen einige CHECK-Vorgänge Ausnahmen aus, da der Typ nicht änderbar ist.</span><span class="sxs-lookup"><span data-stu-id="e73ea-112">User-defined table types can have check constraints, but some check operations will throw an exception because the type is not alterable.</span></span>  
  
 <span data-ttu-id="e73ea-113">Die <xref:Microsoft.SqlServer.Management.Smo.DataType>-Klasse wird verwendet, um den Datentyp anzugeben, der Spalten und Parametern zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="e73ea-113">The <xref:Microsoft.SqlServer.Management.Smo.DataType> class is used to specify the data type that is associated with columns and parameters.</span></span> <span data-ttu-id="e73ea-114">Verwenden Sie diesen Typ, um den benutzerdefinierten Tabellentyp als Parameter für benutzerdefinierte Funktionen und gespeicherte Prozeduren festzulegen.</span><span class="sxs-lookup"><span data-stu-id="e73ea-114">Use this type to specify the user-defined table type as a parameter for user-defined functions and stored procedures.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="e73ea-115">Beispiele</span><span class="sxs-lookup"><span data-stu-id="e73ea-115">Examples</span></span>  
 [!INCLUDE[ssChooseProgEnv](../../../includes/sschooseprogenv-md.md)]  
  
## <a name="creating-a-user-defined-table-in-visual-basic"></a><span data-ttu-id="e73ea-116">Erstellen einer benutzerdefinierten Tabelle in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e73ea-116">Creating a User Defined Table in Visual Basic</span></span>  
 <span data-ttu-id="e73ea-117">Für dieses Beispiel müssen Sie eine Imports-Anweisung für die Klassenbibliothek einbinden, die den `StringCollection`-Typ enthält.</span><span class="sxs-lookup"><span data-stu-id="e73ea-117">For this example, you will have to include an imports statement for the class library that contains the `StringCollection` type.</span></span>  
  
 `Imports System.Collections.Specialized`  
  
 <span data-ttu-id="e73ea-118">Das Codebeispiel zeigt, wie eine benutzerdefinierte Tabelle erstellt und als Parameter in einer benutzerdefinierten Funktion verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e73ea-118">The example demonstrates how to create a user-defined table, and then how to use it as a parameter in a user-defined function.</span></span>  
  
```vb
'Connect to the local, default instance of SQL Server  
        Dim srv As Server  
        srv = New Server  
        'Reference the AdventureWorks2012 database.  
        Dim db As Database  
        db = srv.Databases("AdventureWorks2012")  
        'Define a UserDefinedTableType object variable by supplying the 'database and name in the constructor.  
        Dim udtt As UserDefinedTableType  
        udtt = New UserDefinedTableType(db, "My_User_Defined_Table")  
        'Add three columns of different types to the  
        'UserDefinedTableType object.  
        udtt.Columns.Add(New Column(udtt, "Col1", DataType.Int))  
        udtt.Columns.Add(New Column(udtt, "Col2", DataType.VarCharMax))  
        udtt.Columns.Add(New Column(udtt, "Col3", DataType.Money))  
        'Define an Index object variable by supplying the user-defined  
        'table variable and name in the constructor.  
        Dim idx As Index  
        idx = New Index(udtt, "PK_UddtTable")  
        'Add the first column in the user-defined table as  
        'the indexed column.  
        idx.IndexedColumns.Add(New IndexedColumn(idx, "Col1"))  
        'Specify that the index is a clustered, unique, primary key.  
        idx.IsClustered = True  
        idx.IsUnique = True  
        idx.IndexKeyType = IndexKeyType.DriPrimaryKey  
        udtt.Indexes.Add(idx)  
        'Add the index and create the user-defined table.  
        udtt.Create()  
        'Display the Transact-SQL creation script for the  
        'user-defined table.  
        Dim sc As StringCollection  
        sc = udtt.Script()  
        For Each c As String In sc  
            Console.WriteLine(c)  
        Next  
  
        'Define a new user-defined function with a single parameter.  
        Dim udf As UserDefinedFunction  
        udf = New UserDefinedFunction(db, "My_User_Defined_Function")  
        udf.TextMode = False  
        udf.FunctionType = UserDefinedFunctionType.Scalar  
        udf.ImplementationType = ImplementationType.TransactSql  
        udf.DataType = DataType.DateTime  
        'Specify the parameter as a UserDefinedTableTable object.  
        Dim udfp As UserDefinedFunctionParameter  
        udfp = New UserDefinedFunctionParameter(udf, "@param")  
        udfp.DataType = New DataType(udtt)  
        udfp.IsReadOnly = True  
        udf.Parameters.Add(udfp)  
        'Specify the TextBody property to the Transact-SQL definition of the  
        'user-defined function.  
        udf.TextBody = "BEGIN RETURN (GETDATE());end"  
        'Create the user-defined function.  
        udf.Create()  
```  
  
## <a name="creating-a-user-defined-table-in-visual-c"></a><span data-ttu-id="e73ea-119">Erstellen einer benutzerdefinierten Tabelle in Visual C#</span><span class="sxs-lookup"><span data-stu-id="e73ea-119">Creating a User Defined Table in Visual C#</span></span>  
 <span data-ttu-id="e73ea-120">Für dieses Beispiel müssen Sie eine Imports-Anweisung für die Klassenbibliothek einbinden, die den `StringCollection`-Typ enthält.</span><span class="sxs-lookup"><span data-stu-id="e73ea-120">For this example, you will have to include an imports statement for the class library that contains the `StringCollection` type.</span></span>  
  
 `using System.Collections.Specialized;`  
  
 <span data-ttu-id="e73ea-121">Das Codebeispiel zeigt, wie eine benutzerdefinierte Tabelle erstellt und als Parameter in einer benutzerdefinierten Funktion verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e73ea-121">The example shows how to create a user-defined table, and then how to use it as a parameter in a user-defined function.</span></span>  
  
```csharp
{  
            //Connect to the local, default instance of SQL Server   
               Server srv = new Server();  
  
            //Reference the AdventureWorks2012 database.   
            Database db = srv.Databases["AdventureWorks2012"];  
            //Define a UserDefinedTableType object variable by supplying the  
            //database and name in the constructor.   
         UserDefinedTableType udtt = new UserDefinedTableType(db, "My_User_Defined_Table");  
  
            //Add three columns of different types to the   
            //UserDefinedTableType object.   
         udtt.Columns.Add(new Column(udtt, "Col1", DataType.Int));  
         udtt.Columns.Add(new Column(udtt, "Col2", DataType.VarCharMax));  
         udtt.Columns.Add(new Column(udtt, "Col3", DataType.Money));  
  
            //Define an Index object variable by supplying the user-defined   
            //table variable and name in the constructor.   
  
            Index idx = new Index(udtt, "PK_UddtTable");  
  
            //Add the first column in the user-defined table as   
            //the indexed column.   
            idx.IndexedColumns.Add(new IndexedColumn(idx, "Col1"));  
            //Specify that the index is a clustered, unique, primary key.   
            idx.IsClustered = true;  
            idx.IsUnique = true;  
            idx.IndexKeyType = IndexKeyType.DriPrimaryKey;  
            udtt.Indexes.Add(idx);  
            //Add the index and create the user-defined table.   
            udtt.Create();  
  
            //Display the Transact-SQL creation script for the   
            //user-defined table.   
            System.Collections.Specialized.StringCollection sc;  
            sc = udtt.Script();  
            foreach (string s in sc)  
            {  
                Console.WriteLine(s);  
            }  
  
            //Define a new user-defined function with a single parameter.  
            UserDefinedFunction udf = new UserDefinedFunction(db, "My_User_Defined_Function");  
            udf.TextMode = false;  
            udf.FunctionType = UserDefinedFunctionType.Scalar;  
            udf.ImplementationType = ImplementationType.TransactSql;  
            udf.DataType = DataType.DateTime;  
  
            //Specify the parameter as a UserDefinedTableTable object.  
             UserDefinedFunctionParameter udfp = new UserDefinedFunctionParameter(udf, "@param");  
            udfp.DataType = new DataType(udtt);  
            udfp.IsReadOnly = true;  
            udf.Parameters.Add(udfp);  
  
            //Specify the TextBody property to the Transact-SQL definition of the   
            //user-defined function.   
            udf.TextBody = "BEGIN RETURN (GETDATE());end";  
            //Create the user-defined function.   
            udf.Create();  
        }  
```  
  
## <a name="creating-a-user-defined-table-in-powershell"></a><span data-ttu-id="e73ea-122">Erstellen einer benutzerdefinierten Tabelle in PowerShell</span><span class="sxs-lookup"><span data-stu-id="e73ea-122">Creating a User Defined Table in PowerShell</span></span>  
 <span data-ttu-id="e73ea-123">Für dieses Beispiel müssen Sie eine Imports-Anweisung für die Klassenbibliothek einbinden, die den `StringCollection`-Typ enthält.</span><span class="sxs-lookup"><span data-stu-id="e73ea-123">For this example, you will have to include an imports statement for the class library that contains the `StringCollection` type.</span></span>  
  
 `using System.Collections.Specialized;`  
  
 <span data-ttu-id="e73ea-124">Das Codebeispiel zeigt, wie eine benutzerdefinierte Tabelle erstellt und als Parameter in einer benutzerdefinierten Funktion verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e73ea-124">The example shows how to create a user-defined table, and then how to use it as a parameter in a user-defined function.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server and get a reference to AdventureWorks2012  
CD \sql\localhost\default\databases  
$db = Get-Item Adventureworks2012  
  
#Define a UserDefinedTableType object variable by supplying the  
#database and name in the constructor.
$udtt = New-Object -TypeName Microsoft.SqlServer.Management.SMO.UserDefinedTableType -ArgumentList $db, "My_User_Defined_Table"  
  
#Add three columns of different types to the UserDefinedTableType object.  
  
$type = [Microsoft.SqlServer.Management.SMO.DataType]::Int  
$col = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Column -ArgumentList $udtt, "col1", $type  
$udtt.Columns.Add($col)  
  
$type = [Microsoft.SqlServer.Management.SMO.DataType]::VarCharMax  
$col = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Column -ArgumentList $udtt, "col2", $type  
$udtt.Columns.Add($col)  
  
 $type = [Microsoft.SqlServer.Management.SMO.DataType]::Money  
$col = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Column -ArgumentList $udtt, "col3", $type  
$udtt.Columns.Add($col)
  
#Define an Index object variable by supplying the user-defined table variable and name in the constructor.
$idx = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Index `  
-argumentlist $udtt, "PK_UddtTable"  
  
#Add the first column in the user-defined table as the indexed column.
$idxcol = New-Object -TypeName Microsoft.SqlServer.Management.SMO.IndexedColumn `  
-argumentlist $idx, "Col1"  
$idx.IndexedColumns.Add($idxcol)  
  
#Specify that the index is a clustered, unique, primary key.
$idx.IsClustered = $true  
$idx.IsUnique = $true  
$idx.IndexKeyType = [Microsoft.SqlServer.Management.SMO.IndexKeyType]::DriPrimaryKey;  
  
#Add the index and create the user-defined table.
$udtt.Indexes.Add($idx)  
$udtt.Create();  
  
# Display the Transact-SQL creation script for the user-defined table.
$sc = $udtt.Script()  
$sc  
  
# Define a new user-defined function with a single parameter.
$udf = New-Object -TypeName Microsoft.SqlServer.Management.SMO.UserDefinedFunction -ArgumentList $db, "My_User_Defined_Function"  
$udf.TextMode = $false  
$udf.FunctionType = [Microsoft.SqlServer.Management.SMO.UserDefinedFunctionType]::Scalar  
$udf.ImplementationType = [Microsoft.SqlServer.Management.SMO.ImplementationType]::TransactSql  
$udf.DataType = [Microsoft.SqlServer.Management.SMO.DataType]::DateTime  
  
# Specify the parameter as a UserDefinedTableTable object.  
$udfp = New-Object -TypeName Microsoft.SqlServer.Management.SMO.UserDefinedFunctionParameter -ArgumentList $udf, "@param"  
$type = New-Object -TypeName Microsoft.SqlServer.Management.SMO.DataType -ArgumentList $udtt  
$udfp.DataType = $type  
$udfp.IsReadOnly = $true  
$udf.Parameters.Add($udfp)  
  
# Specify the TextBody property to the Transact-SQL definition of the user-defined function.   
$udf.TextBody = "BEGIN RETURN (GETDATE());end"  
  
# Create the user-defined function.
$udf.Create()
```  
  
## <a name="see-also"></a><span data-ttu-id="e73ea-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e73ea-125">See Also</span></span>  
 <xref:Microsoft.SqlServer.Management.Smo.FileGroup>   
 [<span data-ttu-id="e73ea-126">Datenbankdateien und Dateigruppen</span><span class="sxs-lookup"><span data-stu-id="e73ea-126">Database Files and Filegroups</span></span>](../../databases/database-files-and-filegroups.md)  
