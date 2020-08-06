---
title: Aufrufen von Methoden | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- methods [SMO]
- calling methods
- SQL Server Management Objects, method calling
- SMO [SQL Server], method calling
ms.assetid: c88d5c5f-9ff0-4f84-b2b6-24c6b90fa15e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 13216b4c533527d4249471073580d7c86f6b07e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719804"
---
# <a name="calling-methods"></a><span data-ttu-id="93f10-102">Aufrufen von Methoden</span><span class="sxs-lookup"><span data-stu-id="93f10-102">Calling Methods</span></span>
  <span data-ttu-id="93f10-103">-Methoden führen bestimmte Aufgaben im Zusammenhang mit dem-Objekt aus, z. b. das Ausgeben eines `Checkpoint` in einer Datenbank oder das Anfordern einer Aufzählungs Liste mit Anmeldungen für die-Instanz [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="93f10-103">Methods perform specific tasks related to the object, such as issuing a `Checkpoint` on a database or requesting an enumerated list of logons for the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="93f10-104">Methoden führen Vorgänge an Objekten aus.</span><span class="sxs-lookup"><span data-stu-id="93f10-104">Methods perform an operation on an object.</span></span> <span data-ttu-id="93f10-105">Methoden können Parameter enthalten, und sie verfügen häufig über einen Rückgabewert.</span><span class="sxs-lookup"><span data-stu-id="93f10-105">Methods can take parameters and often have a return value.</span></span> <span data-ttu-id="93f10-106">Bei dem Rückgabewert kann es sich um einen einfachen Datentyp, ein komplexes Objekt oder eine Struktur handeln, die mehrere Elemente enthält.</span><span class="sxs-lookup"><span data-stu-id="93f10-106">The return value can be a simple data type, a complex object, or a structure that contains many members.</span></span>  
  
 <span data-ttu-id="93f10-107">Mithilfe der Ausnahmebehandlung können Sie feststellen, ob die Methode erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="93f10-107">Use exception handling to detect whether the method has been successful.</span></span> <span data-ttu-id="93f10-108">Weitere Informationen finden Sie unter [Handling SMO Exceptions](handling-smo-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="93f10-108">For more information, see [Handling SMO Exceptions](handling-smo-exceptions.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="93f10-109">Beispiele</span><span class="sxs-lookup"><span data-stu-id="93f10-109">Examples</span></span>  
 [!INCLUDE[ssChooseProgEnv](../../../includes/sschooseprogenv-md.md)]  
  
## <a name="using-a-simple-smo-method-in-visual-basic"></a><span data-ttu-id="93f10-110">Verwenden einer einfachen SMO-Methode in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="93f10-110">Using a Simple SMO Method in Visual Basic</span></span>  
 <span data-ttu-id="93f10-111">In diesem Beispiel enthält die <xref:Microsoft.SqlServer.Management.Smo.Database.Create%2A>-Methode keine Parameter und hat keinen Rückgabewert.</span><span class="sxs-lookup"><span data-stu-id="93f10-111">In this example, the <xref:Microsoft.SqlServer.Management.Smo.Database.Create%2A> method takes no parameters and has no return value.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBMethods1](SMO How to#SMO_VBMethods1)]  -->  
  
## <a name="using-a-simple-smo-method-in-visual-c"></a><span data-ttu-id="93f10-112">Verwenden einer einfachen SMO-Methode in Visual C#</span><span class="sxs-lookup"><span data-stu-id="93f10-112">Using a Simple SMO Method in Visual C#</span></span>  
 <span data-ttu-id="93f10-113">In diesem Beispiel enthält die <xref:Microsoft.SqlServer.Management.Smo.Database.Create%2A>-Methode keine Parameter und hat keinen Rückgabewert.</span><span class="sxs-lookup"><span data-stu-id="93f10-113">In this example, the <xref:Microsoft.SqlServer.Management.Smo.Database.Create%2A> method takes no parameters and has no return value.</span></span>  
  
```  
{   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Define a Database object variable by supplying the parent server and the database name arguments in the constructor.   
Database db;   
db = new Database(srv, "Test_SMO_Database");   
//Call the Create method to create the database on the instance of SQL Server.   
db.Create();   
```  
  
 <span data-ttu-id="93f10-114">}</span><span class="sxs-lookup"><span data-stu-id="93f10-114">}</span></span>  
  
## <a name="using-an-smo-method-with-a-parameter-in-visual-basic"></a><span data-ttu-id="93f10-115">Verwenden einer SMO-Methode mit einem Parameter in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="93f10-115">Using an SMO Method with a Parameter in Visual Basic</span></span>  
 <span data-ttu-id="93f10-116">Das <xref:Microsoft.SqlServer.Management.Smo.Table>-Objekt verfügt über eine Methode mit dem Namen <xref:Microsoft.SqlServer.Management.Smo.Table.RebuildIndexes%2A>.</span><span class="sxs-lookup"><span data-stu-id="93f10-116">The <xref:Microsoft.SqlServer.Management.Smo.Table> object has a method called <xref:Microsoft.SqlServer.Management.Smo.Table.RebuildIndexes%2A>.</span></span> <span data-ttu-id="93f10-117">Diese Methode benötigt einen numerischen Parameter, der `FillFactor`angibt.</span><span class="sxs-lookup"><span data-stu-id="93f10-117">This method requires a numeric parameter that specifies the `FillFactor`.</span></span>  
  
```  
Dim srv As Server  
srv = New Server  
Dim tb As Table  
tb = srv.Databases("AdventureWorks2012").Tables("Employee", "HumanResources")  
tb.RebuildIndexes(70)  
```  
  
## <a name="using-an-smo-method-with-a-parameter-in-visual-c"></a><span data-ttu-id="93f10-118">Verwenden einer SMO-Methode mit einem Parameter in Visual C#</span><span class="sxs-lookup"><span data-stu-id="93f10-118">Using an SMO Method with a Parameter in Visual C#</span></span>  
 <span data-ttu-id="93f10-119">Das <xref:Microsoft.SqlServer.Management.Smo.Table>-Objekt verfügt über eine Methode mit dem Namen <xref:Microsoft.SqlServer.Management.Smo.Table.RebuildIndexes%2A>.</span><span class="sxs-lookup"><span data-stu-id="93f10-119">The <xref:Microsoft.SqlServer.Management.Smo.Table> object has a method called <xref:Microsoft.SqlServer.Management.Smo.Table.RebuildIndexes%2A>.</span></span> <span data-ttu-id="93f10-120">Diese Methode benötigt einen numerischen Parameter, der `FillFactor`angibt.</span><span class="sxs-lookup"><span data-stu-id="93f10-120">This method requires a numeric parameter that specifies the `FillFactor`.</span></span>  
  
```  
{   
Server srv = default(Server);   
srv = new Server();   
Table tb = default(Table);   
tb = srv.Databases("AdventureWorks2012").Tables("Employee", "HumanResources");   
tb.RebuildIndexes(70);   
}   
```  
  
## <a name="using-an-enumeration-method-that-returns-a-datatable-object-in-visual-basic"></a><span data-ttu-id="93f10-121">Verwenden einer Enumerationsmethode in Visual Basic, die ein "DataTable"-Objekt zurückgibt</span><span class="sxs-lookup"><span data-stu-id="93f10-121">Using an Enumeration Method that Returns a DataTable Object in Visual Basic</span></span>  
 <span data-ttu-id="93f10-122">In diesem Abschnitt wird beschrieben, wie eine Enumerationsmethode aufgerufen wird und wie die Daten im zurückgegebenen <xref:System.Data.DataTable>-Objekt behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="93f10-122">This section describes how to call an enumeration method and how to handle the data in the returned <xref:System.Data.DataTable> object.</span></span>  
  
 <span data-ttu-id="93f10-123">Die <xref:Microsoft.SqlServer.Management.Smo.Server.EnumCollations%2A>-Methode gibt ein <xref:System.Data.DataTable>-Objekt zurück, für das weitere Navigation erforderlich ist, auf alle verfügbaren Sortierungsinformationen zu der Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="93f10-123">The <xref:Microsoft.SqlServer.Management.Smo.Server.EnumCollations%2A> method returns a <xref:System.Data.DataTable> object, which requires further navigation to access all available collation information about the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
```  
'Connect to the local, default instance of SQL Server.  
Dim srv As Server  
srv = New Server  
'Call the EnumCollations method and return collation information to DataTable variable.  
Dim d As DataTable  
'Select the returned data into an array of DataRow.  
d = srv.EnumCollations  
'Iterate through the rows and display collation details for the instance of SQL Server.  
Dim r As DataRow  
Dim c As DataColumn  
For Each r In d.Rows  
    Console.WriteLine("==")  
    For Each c In r.Table.Columns  
        Console.WriteLine(c.ColumnName + " = " + r(c).ToString)  
    Next  
Next  
```  
  
## <a name="using-an-enumeration-method-that-returns-a-datatable-object-in-visual-c"></a><span data-ttu-id="93f10-124">Verwenden einer Enumerationsmethode in Visual C#, die ein "DataTable"-Objekt zurückgibt</span><span class="sxs-lookup"><span data-stu-id="93f10-124">Using an Enumeration Method that Returns a DataTable Object in Visual C#</span></span>  
 <span data-ttu-id="93f10-125">In diesem Abschnitt wird beschrieben, wie eine Enumerationsmethode aufgerufen wird und wie die Daten im zurückgegebenen <xref:System.Data.DataTable>-Objekt behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="93f10-125">This section describes how to call an enumeration method and how to handle the data in the returned <xref:System.Data.DataTable> object.</span></span>  
  
 <span data-ttu-id="93f10-126">Die <xref:Microsoft.SqlServer.Management.Smo.Server.EnumCollations%2A>-Methode gibt ein <xref:System.Data.DataTable>-Systemobjekt zurück.</span><span class="sxs-lookup"><span data-stu-id="93f10-126">The <xref:Microsoft.SqlServer.Management.Smo.Server.EnumCollations%2A> method returns a system <xref:System.Data.DataTable> object.</span></span> <span data-ttu-id="93f10-127">Für das <xref:System.Data.DataTable>-Objekt ist weitere Navigation erforderlich, um auf alle verfügbaren Sortierungsinformationen zu der Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="93f10-127">The <xref:System.Data.DataTable> object requires further navigation to access all available collation information about the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
```  
//Connect to the local, default instance of SQL Server.   
{   
Server srv = default(Server);   
srv = new Server();   
//Call the EnumCollations method and return collation information to DataTable variable.   
DataTable d = default(DataTable);   
//Select the returned data into an array of DataRow.   
d = srv.EnumCollations;   
//Iterate through the rows and display collation details for the instance of SQL Server.   
DataRow r = default(DataRow);   
DataColumn c = default(DataColumn);   
foreach ( r in d.Rows) {   
  Console.WriteLine("=========");   
  foreach ( c in r.Table.Columns) {   
    Console.WriteLine(c.ColumnName + " = " + r(c).ToString);   
  }   
}   
}   
```  
  
## <a name="constructing-an-object-in-visual-basic"></a><span data-ttu-id="93f10-128">Erstellen eines Objekts in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="93f10-128">Constructing an Object in Visual Basic</span></span>  
 <span data-ttu-id="93f10-129">Der Konstruktor eines Objekts kann mit dem `New`-Operator aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="93f10-129">The constructor of any object can be called by using the `New` operator.</span></span> <span data-ttu-id="93f10-130">Der <xref:Microsoft.SqlServer.Management.Smo.Database>-Objektkonstruktor ist überladen, und die Version des im Beispiel verwendeten <xref:Microsoft.SqlServer.Management.Smo.Database>-Objektkonstruktors akzeptiert zwei Parameter: das übergeordnete <xref:Microsoft.SqlServer.Management.Smo.Server>-Objekt, zu dem die Datenbank gehört, und eine Zeichenfolge, die den Namen der neuen Datenbank darstellt.</span><span class="sxs-lookup"><span data-stu-id="93f10-130">The <xref:Microsoft.SqlServer.Management.Smo.Database> object constructor is overloaded and the version of the <xref:Microsoft.SqlServer.Management.Smo.Database> object constructor that is used in the sample takes two parameters: the parent <xref:Microsoft.SqlServer.Management.Smo.Server> object to which the database belongs, and a string that represents the name of the new database.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBMethods4](SMO How to#SMO_VBMethods4)]  -->  
  
## <a name="constructing-an-object-in-visual-c"></a><span data-ttu-id="93f10-131">Erstellen eines Objekts in Visual C#</span><span class="sxs-lookup"><span data-stu-id="93f10-131">Constructing an Object in Visual C#</span></span>  
 <span data-ttu-id="93f10-132">Der Konstruktor eines Objekts kann mit dem `New`-Operator aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="93f10-132">The constructor of any object can be called by using the `New` operator.</span></span> <span data-ttu-id="93f10-133">Der <xref:Microsoft.SqlServer.Management.Smo.Database>-Objektkonstruktor ist überladen, und die Version des im Beispiel verwendeten <xref:Microsoft.SqlServer.Management.Smo.Database>-Objektkonstruktors akzeptiert zwei Parameter: das übergeordnete <xref:Microsoft.SqlServer.Management.Smo.Server>-Objekt, zu dem die Datenbank gehört, und eine Zeichenfolge, die den Namen der neuen Datenbank darstellt.</span><span class="sxs-lookup"><span data-stu-id="93f10-133">The <xref:Microsoft.SqlServer.Management.Smo.Database> object constructor is overloaded and the version of the <xref:Microsoft.SqlServer.Management.Smo.Database> object constructor that is used in the sample takes two parameters: the parent <xref:Microsoft.SqlServer.Management.Smo.Server> object to which the database belongs, and a string that represents the name of the new database.</span></span>  
  
```  
{   
Server srv;   
srv = new Server();   
Table tb;   
tb = srv.Databases("AdventureWorks2012").Tables("Employee", "HumanResources");   
tb.RebuildIndexes(70);   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Declare and define a Database object by supplying the parent server and the database name arguments in the constructor.   
Database d;   
d = new Database(srv, "Test_SMO_Database");   
//Create the database on the instance of SQL Server.   
d.Create();   
Console.WriteLine(d.Name);   
}  
```  
  
## <a name="copying-an-smo-object-in-visual-basic"></a><span data-ttu-id="93f10-134">Kopieren eines SMO-Objekts in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="93f10-134">Copying an SMO Object in Visual Basic</span></span>  
 <span data-ttu-id="93f10-135">In diesem Codebeispiel wird die <xref:Microsoft.SqlServer.Management.Common.ServerConnection.Copy%2A>-Methode zum Erstellen einer Kopie des <xref:Microsoft.SqlServer.Management.Smo.Server>-Objekts verwendet.</span><span class="sxs-lookup"><span data-stu-id="93f10-135">This code example uses the <xref:Microsoft.SqlServer.Management.Common.ServerConnection.Copy%2A> method to create a copy of the <xref:Microsoft.SqlServer.Management.Smo.Server> object.</span></span> <span data-ttu-id="93f10-136">Das <xref:Microsoft.SqlServer.Management.Smo.Server>-Objekt stellt eine Verbindung mit einer Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] dar.</span><span class="sxs-lookup"><span data-stu-id="93f10-136">The <xref:Microsoft.SqlServer.Management.Smo.Server> object represents a connection to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VCMethods6](SMO How to#SMO_VCMethods6)]  -->  
  
## <a name="copying-an-smo-object-in-visual-c"></a><span data-ttu-id="93f10-137">Kopieren eines SMO-Objekts in Visual C#</span><span class="sxs-lookup"><span data-stu-id="93f10-137">Copying an SMO Object in Visual C#</span></span>  
 <span data-ttu-id="93f10-138">In diesem Codebeispiel wird die <xref:Microsoft.SqlServer.Management.Common.ServerConnection.Copy%2A>-Methode zum Erstellen einer Kopie des <xref:Microsoft.SqlServer.Management.Smo.Server>-Objekts verwendet.</span><span class="sxs-lookup"><span data-stu-id="93f10-138">This code example uses the <xref:Microsoft.SqlServer.Management.Common.ServerConnection.Copy%2A> method to create a copy of the <xref:Microsoft.SqlServer.Management.Smo.Server> object.</span></span> <span data-ttu-id="93f10-139">Das <xref:Microsoft.SqlServer.Management.Smo.Server>-Objekt stellt eine Verbindung mit einer Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] dar.</span><span class="sxs-lookup"><span data-stu-id="93f10-139">The <xref:Microsoft.SqlServer.Management.Smo.Server> object represents a connection to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
```  
{   
//Connect to the local, default instance of SQL Server.   
Server srv1;   
srv1 = new Server();   
//Modify the default database and the timeout period for the connection.   
srv1.ConnectionContext.DatabaseName = "AdventureWorks2012";   
srv1.ConnectionContext.ConnectTimeout = 30;   
//Make a second connection using a copy of the ConnectionContext property and verify settings.   
Server srv2;   
srv2 = new Server(srv1.ConnectionContext.Copy);   
Console.WriteLine(srv2.ConnectionContext.ConnectTimeout.ToString);   
}  
```  
  
## <a name="monitoring-server-processes-in-visual-basic"></a><span data-ttu-id="93f10-140">Überwachen von Serverprozessen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="93f10-140">Monitoring Server Processes in Visual Basic</span></span>  
 <span data-ttu-id="93f10-141">Informationen zum aktuellen Statustyp der Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] können Sie über Enumerationsmethoden abrufen.</span><span class="sxs-lookup"><span data-stu-id="93f10-141">You can obtain the current status type information about the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] through enumeration methods.</span></span> <span data-ttu-id="93f10-142">Im Beispielcode wird die <xref:Microsoft.SqlServer.Management.Smo.Server.EnumProcesses%2A>-Methode zum Ermitteln von Informationen zu den aktuellen Prozessen verwendet.</span><span class="sxs-lookup"><span data-stu-id="93f10-142">The code example uses the <xref:Microsoft.SqlServer.Management.Smo.Server.EnumProcesses%2A> method to discover information about the current processes.</span></span> <span data-ttu-id="93f10-143">Dieses Beispiel zeigt auch, wie mit den Spalten und Zeilen im zurückgegebenen <xref:System.Data.DataTable>-Objekt gearbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="93f10-143">It also demonstrates how to work with the columns and rows in the returned <xref:System.Data.DataTable> object.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBMethods5](SMO How to#SMO_VBMethods5)]  -->  
  
## <a name="monitoring-server-processes-in-visual-c"></a><span data-ttu-id="93f10-144">Überwachen von Serverprozessen in Visual C#</span><span class="sxs-lookup"><span data-stu-id="93f10-144">Monitoring Server Processes in Visual C#</span></span>  
 <span data-ttu-id="93f10-145">Informationen zum aktuellen Statustyp der Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] können Sie über Enumerationsmethoden abrufen.</span><span class="sxs-lookup"><span data-stu-id="93f10-145">You can obtain the current status type information about the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] through enumeration methods.</span></span> <span data-ttu-id="93f10-146">Im Beispielcode wird die <xref:Microsoft.SqlServer.Management.Smo.Server.EnumProcesses%2A>-Methode zum Ermitteln von Informationen zu den aktuellen Prozessen verwendet.</span><span class="sxs-lookup"><span data-stu-id="93f10-146">The code example uses the <xref:Microsoft.SqlServer.Management.Smo.Server.EnumProcesses%2A> method to discover information about the current processes.</span></span> <span data-ttu-id="93f10-147">Dieses Beispiel zeigt auch, wie mit den Spalten und Zeilen im zurückgegebenen <xref:System.Data.DataTable>-Objekt gearbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="93f10-147">It also demonstrates how to work with the columns and rows in the returned <xref:System.Data.DataTable> object.</span></span>  
  
```  
//Connect to the local, default instance of SQL Server.   
{   
Server srv = default(Server);   
srv = new Server();   
//Call the EnumCollations method and return collation information to DataTable variable.   
DataTable d = default(DataTable);   
//Select the returned data into an array of DataRow.   
d = srv.EnumProcesses;   
//Iterate through the rows and display collation details for the instance of SQL Server.   
DataRow r = default(DataRow);   
DataColumn c = default(DataColumn);   
foreach ( r in d.Rows) {   
  Console.WriteLine("=====");   
  foreach ( c in r.Table.Columns) {   
    Console.WriteLine(c.ColumnName + " = " + r(c).ToString);   
  }   
}   
}   
```  
  
## <a name="see-also"></a><span data-ttu-id="93f10-148">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="93f10-148">See Also</span></span>  
 <xref:Microsoft.SqlServer.Management.Smo.Server>   
 <xref:Microsoft.SqlServer.Management.Common.ServerConnection>  
  
  
