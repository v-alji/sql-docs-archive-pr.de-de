---
title: CLR-Skalarwertfunktionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
dev_langs:
- TSQL
- VB
- CSharp
helpviewer_keywords:
- SVF
- scalar-valued functions
ms.assetid: 20dcf802-c27d-4722-9cd3-206b1e77bee0
author: rothja
ms.author: jroth
ms.openlocfilehash: be8f9616fb285d6a68d6734924874ded06fb3bd4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698313"
---
# <a name="clr-scalar-valued-functions"></a><span data-ttu-id="36032-102">CLR-Skalarwertfunktionen</span><span class="sxs-lookup"><span data-stu-id="36032-102">CLR Scalar-Valued Functions</span></span>
  <span data-ttu-id="36032-103">Eine Skalarwertfunktion gibt einen einzelnen Wert wie eine Zeichenfolge, eine ganze Zahl oder einen Bitwert zurück. Außerdem können Sie mithilfe einer beliebigen .NET Framework-Programmiersprache benutzerdefinierte Skalarwertfunktionen in verwaltetem Code erstellen.</span><span class="sxs-lookup"><span data-stu-id="36032-103">A scalar-valued function (SVF) returns a single value, such as a string, integer, or bit value.You can create scalar-valued user-defined functions in managed code using any .NET Framework programming language.</span></span> <span data-ttu-id="36032-104">Auf diese Funktionen kann über [!INCLUDE[tsql](../../includes/tsql-md.md)] oder anderen verwalteten Code zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="36032-104">These functions are accessible to [!INCLUDE[tsql](../../includes/tsql-md.md)] or other managed code.</span></span> <span data-ttu-id="36032-105">Informationen zu den Vorteilen der CLR-Integration und zur Auswahl zwischen verwaltetem Code und [!INCLUDE[tsql](../../includes/tsql-md.md)] finden Sie unter [Übersicht über die CLR-Integration](../clr-integration/clr-integration-overview.md).</span><span class="sxs-lookup"><span data-stu-id="36032-105">For information about the advantages of CLR integration and choosing between managed code and [!INCLUDE[tsql](../../includes/tsql-md.md)], see [Overview of CLR Integration](../clr-integration/clr-integration-overview.md).</span></span>  
  
## <a name="requirements-for-clr-scalar-valued-functions"></a><span data-ttu-id="36032-106">Anforderungen für CLR-Skalarwertfunktionen</span><span class="sxs-lookup"><span data-stu-id="36032-106">Requirements for CLR Scalar-Valued Functions</span></span>  
 <span data-ttu-id="36032-107">.NET Framework-Skalarwertfunktionen werden als Methoden einer Klasse in einer .NET Framework-Assembly implementiert.</span><span class="sxs-lookup"><span data-stu-id="36032-107">.NET Framework SVFs are implemented as methods on a class in a .NET Framework assembly.</span></span> <span data-ttu-id="36032-108">Die Eingabeparameter und der von einem SVF zurückgegebene Typ können einer der skalaren Datentypen sein, die von unterstützt werden [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , außer `varchar` , `char` , `rowversion` , `text` , `ntext` , `image` , `timestamp` , `table` oder `cursor` .</span><span class="sxs-lookup"><span data-stu-id="36032-108">The input parameters and the type returned from a SVF can be any of the scalar data types supported by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], except `varchar`, `char`, `rowversion`, `text`, `ntext`, `image`, `timestamp`, `table`, or `cursor`.</span></span> <span data-ttu-id="36032-109">Skalarwertfunktionen müssen sicherstellen, dass der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Datentyp und der Rückgabedatentyp der Implementierungsmethode übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="36032-109">SVFs must ensure a match between the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type and the return data type of the implementation method.</span></span> <span data-ttu-id="36032-110">Weitere Informationen zu Typkonvertierungen finden Sie unter [Mapping von CLR-Parameter Daten](../clr-integration-database-objects-types-net-framework/mapping-clr-parameter-data.md).</span><span class="sxs-lookup"><span data-stu-id="36032-110">For more information about type conversions, see [Mapping CLR Parameter Data](../clr-integration-database-objects-types-net-framework/mapping-clr-parameter-data.md).</span></span>  
  
 <span data-ttu-id="36032-111">Zur Implementierung einer .NET Framework-Skalarwertfunktion in einer .NET Framework-Sprache kann das benutzerdefinierte `SqlFunction`-Attribut angegeben werden, um zusätzliche Informationen über die Funktion aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="36032-111">When implementing a .NET Framework SVF in a .NET Framework language, the `SqlFunction` custom attribute can be specified to include additional information about the function.</span></span> <span data-ttu-id="36032-112">Das `SqlFunction`-Attribut gibt an, ob die Funktion auf Daten zugreift oder Daten verändert, ob sie deterministisch ist und ob die Funktion Gleitkommaberechnungen beinhaltet.</span><span class="sxs-lookup"><span data-stu-id="36032-112">The `SqlFunction` attribute indicates whether or not the function accesses or modifies data, if it is deterministic, and if the function involves floating point operations.</span></span>  
  
 <span data-ttu-id="36032-113">Benutzerdefinierte Skalarwertfunktionen können deterministisch oder nicht deterministisch sein.</span><span class="sxs-lookup"><span data-stu-id="36032-113">Scalar-valued user-defined functions may be deterministic or non-deterministic.</span></span> <span data-ttu-id="36032-114">Eine deterministische Funktion gibt immer dieselben Ergebnisse zurück, wenn sie mit einem bestimmten Satz an Eingabeparametern aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="36032-114">A deterministic function always returns the same result when it is called with a specific set of input parameters.</span></span> <span data-ttu-id="36032-115">Eine nicht deterministische Funktion kann unterschiedliche Ergebnisse zurückgeben, wenn sie mit einem bestimmten Satz an Eingabeparametern aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="36032-115">A non-deterministic function may return different results when it is called with a specific set of input parameters.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="36032-116">Markieren Sie eine benutzerdefinierte Funktion nicht als deterministisch, wenn die Funktion bei denselben Eingabewerten und demselben Datenbankzustand nicht immer dieselben Ausgabewerte erzeugt.</span><span class="sxs-lookup"><span data-stu-id="36032-116">Do not mark a function as deterministic if the function does not always produces the same output values, given the same input values and the same database state.</span></span> <span data-ttu-id="36032-117">Das Markieren einer Funktion als deterministisch, wenn die Funktion nicht wirklich deterministisch ist, kann zu beschädigten indizierten Sichten und berechneten Spalten führen.</span><span class="sxs-lookup"><span data-stu-id="36032-117">Marking a function as deterministic, when the function isn't truly deterministic can result in corrupted indexed views and computed columns.</span></span> <span data-ttu-id="36032-118">Sie markieren eine Funktion als deterministisch, indem Sie die `IsDeterministic`-Eigenschaft auf true festlegen.</span><span class="sxs-lookup"><span data-stu-id="36032-118">You mark a function as deterministic by setting the `IsDeterministic` property to true.</span></span>  
  
### <a name="table-valued-parameters"></a><span data-ttu-id="36032-119">Tabellenwertparameter</span><span class="sxs-lookup"><span data-stu-id="36032-119">Table-Valued Parameters</span></span>  
 <span data-ttu-id="36032-120">Tabellenwertparameter (Table Valued Parameters, TVPs), benutzerdefinierte Tabellentypen, die an eine Prozedur oder Funktion übergeben werden, bieten eine effiziente Methode zum Übergeben mehrerer Datenzeilen an den Server.</span><span class="sxs-lookup"><span data-stu-id="36032-120">Table-valued parameters (TVPs), user-defined table types that are passed into a procedure or function, provide an efficient way to pass multiple rows of data to the server.</span></span> <span data-ttu-id="36032-121">TVPs verfügen über eine ähnliche Funktionalität wie Parameterarrays, bieten aber größere Flexibilität und engere Integration mit [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="36032-121">TVPs provide similar functionality to parameter arrays, but offer greater flexibility and closer integration with [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="36032-122">Außerdem verfügen sie auch über ein besseres Leistungspotenzial.</span><span class="sxs-lookup"><span data-stu-id="36032-122">They also provide the potential for better performance.</span></span> <span data-ttu-id="36032-123">TVPs helfen auch, die Anzahl von Roundtrips zum Server zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="36032-123">TVPs also help reduce the number of round trips to the server.</span></span> <span data-ttu-id="36032-124">Anstatt mehrere Anforderungen an den Server zu senden, z. B. mit einer Liste von skalaren Parametern, können Daten als TVP an den Server gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="36032-124">Instead of sending multiple requests to the server, such as with a list of scalar parameters, data can be sent to the server as a TVP.</span></span> <span data-ttu-id="36032-125">Ein benutzerdefinierter Tabellentyp kann nicht als Tabellenwertparameter an eine verwaltete gespeicherte Prozedur oder Funktion übergeben werden, die im [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Prozess ausgeführt wird, oder von einer solchen Prozedur oder Funktion zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="36032-125">A user-defined table type cannot be passed as a table-valued parameter to, or be returned from, a managed stored procedure or function executing in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] process.</span></span> <span data-ttu-id="36032-126">Weitere Informationen zu TVPs finden Sie unter [Verwenden von Tabellenwert Parametern &#40;Datenbank-Engine&#41;](../tables/use-table-valued-parameters-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="36032-126">For more information about TVPs, see [Use Table-Valued Parameters &#40;Database Engine&#41;](../tables/use-table-valued-parameters-database-engine.md).</span></span>  
  
## <a name="example-of-a-clr-scalar-valued-function"></a><span data-ttu-id="36032-127">Beispiel für eine CLR-Skalarwertfunktion</span><span class="sxs-lookup"><span data-stu-id="36032-127">Example of a CLR Scalar-Valued Function</span></span>  
 <span data-ttu-id="36032-128">Es folgt eine einfache Skalarwertfunktion, die auf Daten zugreift und einen ganzzahligen Wert zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="36032-128">Here is a simple SVF that accesses data and returns an integer value:</span></span>  
  
```csharp  
using Microsoft.SqlServer.Server;  
using System.Data.SqlClient;  
  
public class T  
{  
    [SqlFunction(DataAccess = DataAccessKind.Read)]  
    public static int ReturnOrderCount()  
    {  
        using (SqlConnection conn   
            = new SqlConnection("context connection=true"))  
        {  
            conn.Open();  
            SqlCommand cmd = new SqlCommand(  
                "SELECT COUNT(*) AS 'Order Count' FROM SalesOrderHeader", conn);  
            return (int)cmd.ExecuteScalar();  
        }  
    }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlClient  
  
Public Class T  
    <SqlFunction(DataAccess:=DataAccessKind.Read)> _  
    Public Shared Function ReturnOrderCount() As Integer  
        Using conn As New SqlConnection("context connection=true")  
            conn.Open()  
            Dim cmd As New SqlCommand("SELECT COUNT(*) AS 'Order Count' FROM SalesOrderHeader", conn)  
            Return CType(cmd.ExecuteScalar(), Integer)  
        End Using  
    End Function  
End Class  
```  
  
 <span data-ttu-id="36032-129">Die erste Codezeile verweist auf `Microsoft.SqlServer.Server`, um auf Attribute zuzugreifen, und auf `System.Data.SqlClient`, um auf den ADO.NET-Namespace zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="36032-129">The first line of code references `Microsoft.SqlServer.Server` to access attributes and `System.Data.SqlClient` to access the ADO.NET namespace.</span></span> <span data-ttu-id="36032-130">(Dieser Namespace enthält `SqlClient`, den .NET Framework-Datenanbieter für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].)</span><span class="sxs-lookup"><span data-stu-id="36032-130">(This namespace contains `SqlClient`, the .NET Framework Data Provider for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].)</span></span>  
  
 <span data-ttu-id="36032-131">Danach empfängt die Funktion das benutzerdefinierte `SqlFunction`-Attribut, das im `Microsoft.SqlServer.Server`-Namespace enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="36032-131">Next, the function receives the `SqlFunction` custom attribute, which is found in the `Microsoft.SqlServer.Server` namespace.</span></span> <span data-ttu-id="36032-132">Das benutzerdefinierte Attribut gibt an, ob die benutzerdefinierte Funktion (UDF) den prozessinternen Anbieter verwendet, um Daten im Server zu lesen.</span><span class="sxs-lookup"><span data-stu-id="36032-132">The custom attribute indicates whether or not the user-defined function (UDF) uses the in-process provider to read data in the server.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="36032-133">lässt nicht zu, dass UDFs Daten aktualisieren, einfügen oder löschen.</span><span class="sxs-lookup"><span data-stu-id="36032-133">does not allow UDFs to update, insert, or delete data.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="36032-134">kann die Ausführung einer UDF optimieren, die den prozessinternen Anbieter nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="36032-134">can optimize execution of a UDF that does not use the in-process provider.</span></span> <span data-ttu-id="36032-135">Dies wird angegeben, indem `DataAccessKind` auf `DataAccessKind.None` festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="36032-135">This is indicated by setting `DataAccessKind` to `DataAccessKind.None`.</span></span> <span data-ttu-id="36032-136">Die Zielmethode in der nächsten Zeile ist eine öffentliche statische Methode (shared in Visual Basic .NET).</span><span class="sxs-lookup"><span data-stu-id="36032-136">On the next line, the target method is a public static (shared in Visual Basic .NET).</span></span>  
  
 <span data-ttu-id="36032-137">Die `SqlContext`-Klasse, die im `Microsoft.SqlServer.Server`-Namespace enthalten ist, kann dann über die bereits eingerichtete Verbindung mit der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Instanz auf ein `SqlCommand`-Objekt zugreifen.</span><span class="sxs-lookup"><span data-stu-id="36032-137">The `SqlContext` class, located in the `Microsoft.SqlServer.Server` namespace, can then access a `SqlCommand` object with a connection to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that is already set up.</span></span> <span data-ttu-id="36032-138">Hier wird zwar kein Gebrauch davon gemacht, aber auch der aktuelle Transaktionskontext ist über die `System.Transactions`-Anwendungsprogrammierschnittstelle (API) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="36032-138">Although not used here, the current transaction context is also available through the `System.Transactions` application programming interface (API).</span></span>  
  
 <span data-ttu-id="36032-139">Die meisten Codezeilen im Funktionsrumpf sollten Entwicklern bekannt vorkommen, die bereits Clientanwendungen mit Typen aus dem `System.Data.SqlClient`-Namespace geschrieben haben.</span><span class="sxs-lookup"><span data-stu-id="36032-139">Most of the lines of code in the function body should look familiar to developers who have written client applications that use the types found in the `System.Data.SqlClient` namespace.</span></span>  
  
 <span data-ttu-id="36032-140">[C#]</span><span class="sxs-lookup"><span data-stu-id="36032-140">[C#]</span></span>  
  
```  
using(SqlConnection conn = new SqlConnection("context connection=true"))   
{  
   conn.Open();  
   SqlCommand cmd = new SqlCommand(  
        "SELECT COUNT(*) AS 'Order Count' FROM SalesOrderHeader", conn);  
   return (int) cmd.ExecuteScalar();  
}    
```  
  
 <span data-ttu-id="36032-141">[Visual Basic]</span><span class="sxs-lookup"><span data-stu-id="36032-141">[Visual Basic]</span></span>  
  
```  
Using conn As New SqlConnection("context connection=true")  
   conn.Open()  
   Dim cmd As New SqlCommand( _  
        "SELECT COUNT(*) AS 'Order Count' FROM SalesOrderHeader", conn)  
   Return CType(cmd.ExecuteScalar(), Integer)  
End Using  
```  
  
 <span data-ttu-id="36032-142">Der entsprechende Befehlstext wird angegeben, indem das `SqlCommand`-Objekt initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="36032-142">The appropriate command text is specified by initializing the `SqlCommand` object.</span></span> <span data-ttu-id="36032-143">Im vorherigen Beispiel wird die Anzahl der Zeilen in der Tabelle `SalesOrderHeader` gezählt.</span><span class="sxs-lookup"><span data-stu-id="36032-143">The previous example counts the number of rows in table `SalesOrderHeader`.</span></span> <span data-ttu-id="36032-144">Als Nächstes wird die `ExecuteScalar`-Methode des `cmd`-Objekts aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="36032-144">Next, the `ExecuteScalar` method of the `cmd` object is called.</span></span> <span data-ttu-id="36032-145">Daraufhin wird ein Wert des Typs `int` zurückgegeben, der auf der Abfrage basiert.</span><span class="sxs-lookup"><span data-stu-id="36032-145">This returns a value of type `int` based on the query.</span></span> <span data-ttu-id="36032-146">Abschließend wird die Anzahl der Bestellungen an den Aufrufer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="36032-146">Finally, the order count is returned to the caller.</span></span>  
  
 <span data-ttu-id="36032-147">Wenn dieser Code in einer Datei namens FirstUdf.cs gespeichert wird, kann er wie folgt als Assembly kompiliert werden:</span><span class="sxs-lookup"><span data-stu-id="36032-147">If this code is saved in a file called FirstUdf.cs, it could be compiled into as assembly as follows:</span></span>  
  
 <span data-ttu-id="36032-148">[C#]</span><span class="sxs-lookup"><span data-stu-id="36032-148">[C#]</span></span>  
  
```  
csc.exe /t:library /out:FirstUdf.dll FirstUdf.cs   
```  
  
 <span data-ttu-id="36032-149">[Visual Basic]</span><span class="sxs-lookup"><span data-stu-id="36032-149">[Visual Basic]</span></span>  
  
```  
vbc.exe /t:library /out:FirstUdf.dll FirstUdf.vb  
```  
  
> [!NOTE]  
>  <span data-ttu-id="36032-150">`/t:library` gibt an, dass eine Bibliothek und keine ausführbare Datei erzeugt werden soll.</span><span class="sxs-lookup"><span data-stu-id="36032-150">`/t:library` indicates that a library, rather than an executable, should be produced.</span></span> <span data-ttu-id="36032-151">Ausführbare Dateien können nicht in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] registriert werden.</span><span class="sxs-lookup"><span data-stu-id="36032-151">Executables cannot be registered in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="36032-152">Visual C++-Datenbankobjekte, die mit `/clr:pure` kompiliert wurden, können nicht in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="36032-152">Visual C++ database objects compiled with `/clr:pure` are not supported for execution on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="36032-153">Zu solchen Datenbankobjekten gehören beispielsweise Skalarwertfunktionen.</span><span class="sxs-lookup"><span data-stu-id="36032-153">For example, such database objects include scalar-valued functions.</span></span>  
  
 <span data-ttu-id="36032-154">Die [!INCLUDE[tsql](../../includes/tsql-md.md)]-Abfrage und ein Beispielaufruf zum Registrieren der Assembly und der UDF folgen:</span><span class="sxs-lookup"><span data-stu-id="36032-154">The [!INCLUDE[tsql](../../includes/tsql-md.md)] query and a sample invocation to register the assembly and UDF are:</span></span>  
  
```  
CREATE ASSEMBLY FirstUdf FROM 'FirstUdf.dll';  
GO  
  
CREATE FUNCTION CountSalesOrderHeader() RETURNS INT   
AS EXTERNAL NAME FirstUdf.T.ReturnOrderCount;   
GO  
  
SELECT dbo.CountSalesOrderHeader();  
GO  
  
```  
  
 <span data-ttu-id="36032-155">Beachten Sie, dass der Funktionsname, der in [!INCLUDE[tsql](../../includes/tsql-md.md)] angegeben wird, nicht mit dem Namen der öffentlichen statischen Zielmethode übereinstimmen muss.</span><span class="sxs-lookup"><span data-stu-id="36032-155">Note that the function name as exposed in [!INCLUDE[tsql](../../includes/tsql-md.md)] does not need to match the name of the target public static method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36032-156">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="36032-156">See Also</span></span>  
 <span data-ttu-id="36032-157">[Mapping von CLR-Parameter Daten](../clr-integration-database-objects-types-net-framework/mapping-clr-parameter-data.md) </span><span class="sxs-lookup"><span data-stu-id="36032-157">[Mapping CLR Parameter Data](../clr-integration-database-objects-types-net-framework/mapping-clr-parameter-data.md) </span></span>  
 <span data-ttu-id="36032-158">[Übersicht über benutzerdefinierte Attribute der CLR-Integration](../../database-engine/dev-guide/overview-of-clr-integration-custom-attributes.md) </span><span class="sxs-lookup"><span data-stu-id="36032-158">[Overview of CLR Integration Custom Attributes](../../database-engine/dev-guide/overview-of-clr-integration-custom-attributes.md) </span></span>  
 <span data-ttu-id="36032-159">[Benutzerdefinierte Funktionen](../user-defined-functions/user-defined-functions.md) </span><span class="sxs-lookup"><span data-stu-id="36032-159">[User-Defined Functions](../user-defined-functions/user-defined-functions.md) </span></span>  
 [<span data-ttu-id="36032-160">Data Access from CLR Database Objects</span><span class="sxs-lookup"><span data-stu-id="36032-160">Data Access from CLR Database Objects</span></span>](../clr-integration/data-access/data-access-from-clr-database-objects.md)  
  
  
