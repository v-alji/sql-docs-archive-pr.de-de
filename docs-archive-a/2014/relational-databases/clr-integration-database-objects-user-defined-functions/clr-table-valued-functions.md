---
title: CLR-Tabellenwert Funktionen | Microsoft-Dokumentation
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
- Transact-SQL table-valued functions
- table-valued functions [CLR integration]
- TVFs [CLR integration]
ms.assetid: 9a6133ea-36e9-45bf-b572-1c0df3d6c194
author: rothja
ms.author: jroth
ms.openlocfilehash: b700aba5a753ecd8ee50ee9b7679cafb2f1f8581
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618733"
---
# <a name="clr-table-valued-functions"></a><span data-ttu-id="59bc0-102">CLR-Tabellenwertfunktionen</span><span class="sxs-lookup"><span data-stu-id="59bc0-102">CLR Table-Valued Functions</span></span>
  <span data-ttu-id="59bc0-103">Eine Tabellenwertfunktion ist eine benutzerdefinierte Funktion, die eine Tabelle zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="59bc0-103">A table-valued function is a user-defined function that returns a table.</span></span>  
  
 <span data-ttu-id="59bc0-104">Ab [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]verfügt [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] über erweiterte Funktionalität für Tabellenwertfunktionen, sodass Sie eine Tabellenwertfunktion in jeder beliebigen verwalteten Sprache definieren können.</span><span class="sxs-lookup"><span data-stu-id="59bc0-104">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] extends the functionality of table-valued functions by allowing you to define a table-valued function in any managed language.</span></span> <span data-ttu-id="59bc0-105">Daten werden von einer Tabellenwertfunktion durch ein `IEnumerable`-Objekt oder `IEnumerator`-Objekt zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="59bc0-105">Data is returned from a table-valued function through an `IEnumerable` or `IEnumerator` object.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="59bc0-106">Bei Tabellenwertfunktionen können die Spalten des zurückgegebenen Tabellentyps keine timestamp-Spalten oder Spalten mit Nicht-Unicode-Zeichenfolgendatentypen enthalten (z. B. `char`, `varchar` und `text`).</span><span class="sxs-lookup"><span data-stu-id="59bc0-106">For table-valued functions, the columns of the return table type cannot include timestamp columns or non-Unicode string data type columns (such as `char`, `varchar`, and `text`).</span></span> <span data-ttu-id="59bc0-107">Die NOT NULL-Einschränkung wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="59bc0-107">The NOT NULL constraint is not supported.</span></span>  
  
## <a name="differences-between-transact-sql-and-clr-table-valued-functions"></a><span data-ttu-id="59bc0-108">Unterschiede zwischen Transact-SQL- und CLR-Tabellenwertfunktionen</span><span class="sxs-lookup"><span data-stu-id="59bc0-108">Differences Between Transact-SQL and CLR Table-Valued Functions</span></span>  
 [!INCLUDE[tsql](../../includes/tsql-md.md)]<span data-ttu-id="59bc0-109">-Tabellenwertfunktionen materialisieren die Ergebnisse des Funktionsaufrufs in einer Zwischentabelle.</span><span class="sxs-lookup"><span data-stu-id="59bc0-109">table-valued functions materialize the results of calling the function into an intermediate table.</span></span> <span data-ttu-id="59bc0-110">Da sie eine Zwischentabelle verwenden, können sie Einschränkungen und eindeutige Indizes der Ergebnisse unterstützen.</span><span class="sxs-lookup"><span data-stu-id="59bc0-110">Since they use an intermediate table, they can support constraints and unique indexes over the results.</span></span> <span data-ttu-id="59bc0-111">Diese Funktionen können äußerst nützlich sein, wenn umfassende Ergebnisse zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="59bc0-111">These features can be extremely useful when large results are returned.</span></span>  
  
 <span data-ttu-id="59bc0-112">Im Gegensatz dazu stellen CLR-Tabellenwertfunktionen eine Streamingalternative dar.</span><span class="sxs-lookup"><span data-stu-id="59bc0-112">In contrast, CLR table-valued functions represent a streaming alternative.</span></span> <span data-ttu-id="59bc0-113">Es ist nicht erforderlich, das gesamte Resultset in einer einzigen Tabelle darzustellen.</span><span class="sxs-lookup"><span data-stu-id="59bc0-113">There is no requirement that the entire set of results be materialized in a single table.</span></span> <span data-ttu-id="59bc0-114">Das von der verwalteten Funktion zurückgegebene `IEnumerable`-Objekt wird direkt vom Ausführungsplan der Abfrage aufgerufen, die die Tabellenwertfunktion aufruft, und die Ergebnisse werden inkrementell verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="59bc0-114">The `IEnumerable` object returned by the managed function is directly called by the execution plan of the query that calls the table-valued function, and the results are consumed in an incremental manner.</span></span> <span data-ttu-id="59bc0-115">Beim Streamingmodell werden Ergebnisse sofort verarbeitet, sobald die erste Zeile verfügbar ist, und nicht erst, wenn die gesamte Tabelle aufgefüllt wurde.</span><span class="sxs-lookup"><span data-stu-id="59bc0-115">This streaming model ensures that results can be consumed immediately after the first row is available, instead of waiting for the entire table to be populated.</span></span> <span data-ttu-id="59bc0-116">Dieses Modell ist auch eine gute Alternative, wenn eine sehr große Anzahl an Zeilen zurückgegeben wird, da diese nicht alle auf einmal im Speicher materialisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="59bc0-116">It is also a better alternative if you have very large numbers of rows returned, because they do not have to be materialized in memory as a whole.</span></span> <span data-ttu-id="59bc0-117">Beispielsweise könnte eine verwaltete Tabellenwertfunktion verwendet werden, um eine Textdatei zu analysieren und jede Zeile als Tabellenzeile zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="59bc0-117">For example, a managed table-valued function could be used to parse a text file and return each line as a row.</span></span>  
  
## <a name="implementing-table-valued-functions"></a><span data-ttu-id="59bc0-118">Implementieren von Tabellenwertfunktionen</span><span class="sxs-lookup"><span data-stu-id="59bc0-118">Implementing Table-Valued Functions</span></span>  
 <span data-ttu-id="59bc0-119">Implementieren Sie Tabellenwertfunktionen als Methoden einer Klasse in einer [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework-Assembly.</span><span class="sxs-lookup"><span data-stu-id="59bc0-119">Implement table-valued functions as methods on a class in a [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework assembly.</span></span> <span data-ttu-id="59bc0-120">Der Code der Tabellenwertfunktion muss die `IEnumerable`-Schnittstelle implementieren.</span><span class="sxs-lookup"><span data-stu-id="59bc0-120">Your table-valued function code must implement the `IEnumerable` interface.</span></span> <span data-ttu-id="59bc0-121">Die `IEnumerable`-Schnittstelle ist in .NET Framework definiert.</span><span class="sxs-lookup"><span data-stu-id="59bc0-121">The `IEnumerable` interface is defined in the .NET Framework.</span></span> <span data-ttu-id="59bc0-122">Für Typen, die Arrays und Auflistungen in .NET Framework darstellen, ist die `IEnumerable`-Schnittstelle bereits implementiert.</span><span class="sxs-lookup"><span data-stu-id="59bc0-122">Types representing arrays and collections in the .NET Framework already implement the `IEnumerable` interface.</span></span> <span data-ttu-id="59bc0-123">Dies vereinfacht das Schreiben von Tabellenwertfunktionen, die eine Auflistung oder ein Array in ein Resultset konvertieren.</span><span class="sxs-lookup"><span data-stu-id="59bc0-123">This makes it easy for writing table-valued functions that convert a collection or an array into a result set.</span></span>  
  
## <a name="table-valued-parameters"></a><span data-ttu-id="59bc0-124">Tabellenwertparameter</span><span class="sxs-lookup"><span data-stu-id="59bc0-124">Table-Valued Parameters</span></span>  
 <span data-ttu-id="59bc0-125">Tabellenwertparameter sind benutzerdefinierte Tabellentypen, die an eine Prozedur oder Funktion übergeben werden, und bieten eine effiziente Methode zum Übergeben mehrerer Datenzeilen an den Server.</span><span class="sxs-lookup"><span data-stu-id="59bc0-125">Table-valued parameters are user-defined table types that are passed into a procedure or function and provide an efficient way to pass multiple rows of data to the server.</span></span> <span data-ttu-id="59bc0-126">Tabellenwertparameter verfügen über eine ähnliche Funktionalität wie Parameterarrays, bieten jedoch größere Flexibilität und engere Integration mit [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="59bc0-126">Table-valued parameters provide similar functionality to parameter arrays, but offer greater flexibility and closer integration with [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="59bc0-127">Außerdem verfügen sie auch über ein besseres Leistungspotenzial.</span><span class="sxs-lookup"><span data-stu-id="59bc0-127">They also provide the potential for better performance.</span></span> <span data-ttu-id="59bc0-128">Außerdem tragen Tabellenwertparameter dazu bei, die Anzahl von Roundtrips zum Server zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="59bc0-128">Table-valued parameters also help reduce the number of round trips to the server.</span></span> <span data-ttu-id="59bc0-129">Anstatt mehrere Anforderungen an den Server zu senden, wie beispielsweise bei einer Liste von skalaren Parametern, können Daten als Tabellenwertparameter an den Server gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="59bc0-129">Instead of sending multiple requests to the server, such as with a list of scalar parameters, data can be sent to the server as a table-valued parameter.</span></span> <span data-ttu-id="59bc0-130">Ein benutzerdefinierter Tabellentyp kann nicht als Tabellenwertparameter an eine verwaltete gespeicherte Prozedur oder Funktion übergeben werden, die im [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Prozess ausgeführt wird, oder von einer solchen Prozedur oder Funktion zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="59bc0-130">A user-defined table type cannot be passed as a table-valued parameter to, or be returned from, a managed stored procedure or function executing in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] process.</span></span> <span data-ttu-id="59bc0-131">Weitere Informationen zu Tabellenwertparametern finden Sie unter [Use Table-Valued Parameters &#40;Database Engine&#41; (Verwenden von Tabellenwertparametern &#40;Datenbank-Engine&#41;)](../tables/use-table-valued-parameters-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="59bc0-131">For more information about table-valued parameters, see [Use Table-Valued Parameters &#40;Database Engine&#41;](../tables/use-table-valued-parameters-database-engine.md).</span></span>  
  
## <a name="output-parameters-and-table-valued-functions"></a><span data-ttu-id="59bc0-132">Ausgabeparameter und Tabellenwertfunktionen</span><span class="sxs-lookup"><span data-stu-id="59bc0-132">Output Parameters and Table-Valued Functions</span></span>  
 <span data-ttu-id="59bc0-133">Informationen können aus Tabellenwertfunktionen möglicherweise mit Ausgabeparametern zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="59bc0-133">Information may be returned from table-valued functions using output parameters.</span></span> <span data-ttu-id="59bc0-134">Der entsprechende Parameter im Implementierungscode der Tabellenwertfunktion sollte einen als Verweis zu übergebenden Parameter als Argument verwenden.</span><span class="sxs-lookup"><span data-stu-id="59bc0-134">The corresponding parameter in the implementation code table-valued function should use a pass-by-reference parameter as the argument.</span></span> <span data-ttu-id="59bc0-135">Beachten Sie, dass Visual Basic Ausgabeparameter nicht auf die gleiche Weise unterstützt wie Visual C#.</span><span class="sxs-lookup"><span data-stu-id="59bc0-135">Note that Visual Basic does not support output parameters in the same way that Visual C# does.</span></span> <span data-ttu-id="59bc0-136">Sie müssen den Parameter als Verweis angeben und das- \<Out()> Attribut auf die Darstellung eines Ausgabe Parameters anwenden, wie im folgenden dargestellt:</span><span class="sxs-lookup"><span data-stu-id="59bc0-136">You must specify the parameter by reference and apply the \<Out()> attribute to represent an output parameter, as in the following:</span></span>  
  
```vb  
Imports System.Runtime.InteropServices  
...  
Public Shared Sub FillRow ( <Out()> ByRef value As SqlInt32)  
```  
  
### <a name="defining-a-table-valued-function-in-transact-sql"></a><span data-ttu-id="59bc0-137">Definieren einer Tabellenwertfunktion in Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="59bc0-137">Defining a Table-Valued Function in Transact-SQL</span></span>  
 <span data-ttu-id="59bc0-138">Die Syntax zum Definieren einer CLR-Tabellenwertfunktion ähnelt der einer [!INCLUDE[tsql](../../includes/tsql-md.md)]-Tabellenwertfunktion, enthält jedoch zusätzlich die `EXTERNAL NAME`-Klausel.</span><span class="sxs-lookup"><span data-stu-id="59bc0-138">The syntax for defining a CLR table-valued function is similar to that of a [!INCLUDE[tsql](../../includes/tsql-md.md)] table-valued function, with the addition of the `EXTERNAL NAME` clause.</span></span> <span data-ttu-id="59bc0-139">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="59bc0-139">For example:</span></span>  
  
```  
CREATE FUNCTION GetEmpFirstLastNames()  
RETURNS TABLE (FirstName NVARCHAR(4000), LastName NVARCHAR(4000))  
EXTERNAL NAME MyDotNETAssembly.[MyNamespace.MyClassname]. GetEmpFirstLastNames;  
```  
  
 <span data-ttu-id="59bc0-140">Tabellenwertfunktionen werden verwendet, um Daten in relationalem Format zur weiteren Verarbeitung in Abfragen darzustellen, z. B.:</span><span class="sxs-lookup"><span data-stu-id="59bc0-140">Table-valued functions are used to represent data in relational form for further processing in queries such as:</span></span>  
  
```  
select * from function();  
select * from tbl join function() f on tbl.col = f.col;  
select * from table t cross apply function(t.column);  
```  
  
 <span data-ttu-id="59bc0-141">Tabellenwertfunktionen können in den folgenden Fällen eine Tabelle zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="59bc0-141">Table-valued functions can return a table when:</span></span>  
  
-   <span data-ttu-id="59bc0-142">Wenn sie aus skalaren Eingabeargumenten erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="59bc0-142">Created from scalar input arguments.</span></span> <span data-ttu-id="59bc0-143">Beispielsweise eine Tabellenwertfunktion, die eine durch Trennzeichen getrennte Zeichenfolge von Zahlen in einer Tabelle anordnet.</span><span class="sxs-lookup"><span data-stu-id="59bc0-143">For example, a table-valued function that takes a comma-delimited string of numbers and pivots them into a table.</span></span>  
  
-   <span data-ttu-id="59bc0-144">Wenn sie aus externen Daten erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="59bc0-144">Generated from external data.</span></span> <span data-ttu-id="59bc0-145">Beispielsweise eine Tabellenwertfunktion, die das Ereignisprotokoll liest und es als Tabelle bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="59bc0-145">For example, a table-valued function that reads the event log and exposes it as a table.</span></span>  
  
 <span data-ttu-id="59bc0-146">**Hinweis** Eine Tabellenwert Funktion kann nur den Datenzugriff über eine [!INCLUDE[tsql](../../includes/tsql-md.md)] Abfrage in der `InitMethod` -Methode und nicht in der- `FillRow` Methode ausführen.</span><span class="sxs-lookup"><span data-stu-id="59bc0-146">**Note** A table-valued function can only perform data access through a [!INCLUDE[tsql](../../includes/tsql-md.md)] query in the `InitMethod` method, and not in the `FillRow` method.</span></span> <span data-ttu-id="59bc0-147">Die `InitMethod`-Methode sollte mit der `SqlFunction.DataAccess.Read`-Attributeigenschaft gekennzeichnet werden, wenn eine [!INCLUDE[tsql](../../includes/tsql-md.md)]-Abfrage ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="59bc0-147">The `InitMethod` should be marked with the `SqlFunction.DataAccess.Read` attribute property if a [!INCLUDE[tsql](../../includes/tsql-md.md)] query is performed.</span></span>  
  
## <a name="a-sample-table-valued-function"></a><span data-ttu-id="59bc0-148">Beispiel für eine Tabellenwertfunktion</span><span class="sxs-lookup"><span data-stu-id="59bc0-148">A Sample Table-Valued Function</span></span>  
 <span data-ttu-id="59bc0-149">Die folgende Tabellenwertfunktion gibt Informationen aus dem Systemereignisprotokoll zurück.</span><span class="sxs-lookup"><span data-stu-id="59bc0-149">The following table-valued function returns information from the system event log.</span></span> <span data-ttu-id="59bc0-150">Die Funktion liest ein einzelnes Zeichenfolgenargument, das den Namen des Ereignisprotokolls enthält.</span><span class="sxs-lookup"><span data-stu-id="59bc0-150">The function takes a single string argument containing the name of the event log to read.</span></span>  
  
###### <a name="sample-code"></a><span data-ttu-id="59bc0-151">Beispielcode</span><span class="sxs-lookup"><span data-stu-id="59bc0-151">Sample Code</span></span>  
  
```csharp  
using System;  
using System.Data.Sql;  
using Microsoft.SqlServer.Server;  
using System.Collections;  
using System.Data.SqlTypes;  
using System.Diagnostics;  
  
public class TabularEventLog  
{  
    [SqlFunction(FillRowMethodName = "FillRow")]  
    public static IEnumerable InitMethod(String logname)  
    {  
        return new EventLog(logname).Entries;    }  
  
    public static void FillRow(Object obj, out SqlDateTime timeWritten, out SqlChars message, out SqlChars category, out long instanceId)  
    {  
        EventLogEntry eventLogEntry = (EventLogEntry)obj;  
        timeWritten = new SqlDateTime(eventLogEntry.TimeWritten);  
        message = new SqlChars(eventLogEntry.Message);  
        category = new SqlChars(eventLogEntry.Category);  
        instanceId = eventLogEntry.InstanceId;  
    }  
}  
```  
  
```vb  
Imports System  
Imports System.Data.Sql  
Imports Microsoft.SqlServer.Server  
Imports System.Collections  
Imports System.Data.SqlTypes  
Imports System.Diagnostics  
Imports System.Runtime.InteropServices  
  
Public Class TabularEventLog  
    <SqlFunction(FillRowMethodName:="FillRow")> _  
    Public Shared Function InitMethod(ByVal logname As String) As IEnumerable  
        Return New EventLog(logname).Entries  
    End Function  
  
    Public Shared Sub FillRow(ByVal obj As Object, <Out()> ByRef timeWritten As SqlDateTime, <Out()> ByRef message As SqlChars, <Out()> ByRef category As SqlChars, <Out()> ByRef instanceId As Long)  
        Dim eventLogEnTry As EventLogEntry = CType(obj, EventLogEntry)  
        timeWritten = New SqlDateTime(eventLogEnTry.TimeWritten)  
        message = New SqlChars(eventLogEnTry.Message)  
        category = New SqlChars(eventLogEnTry.Category)  
        instanceId = eventLogEnTry.InstanceId  
    End Sub  
End Class  
```  
  
###### <a name="declaring-and-using-the-sample-table-valued-function"></a><span data-ttu-id="59bc0-152">Deklarieren und Verwenden des Beispiels für eine Tabellenwertfunktion</span><span class="sxs-lookup"><span data-stu-id="59bc0-152">Declaring and Using the Sample Table-Valued Function</span></span>  
 <span data-ttu-id="59bc0-153">Sobald das Beispiel für eine Tabellenwertfunktion kompiliert wurde, kann diese in [!INCLUDE[tsql](../../includes/tsql-md.md)] folgendermaßen deklariert werden:</span><span class="sxs-lookup"><span data-stu-id="59bc0-153">After the sample table-valued function has been compiled, it can be declared in [!INCLUDE[tsql](../../includes/tsql-md.md)] like this:</span></span>  
  
```  
use master;  
-- Replace SQL_Server_logon with your SQL Server user credentials.  
GRANT EXTERNAL ACCESS ASSEMBLY TO [SQL_Server_logon];   
-- Modify the following line to specify a different database.  
ALTER DATABASE master SET TRUSTWORTHY ON;  
  
-- Modify the next line to use the appropriate database.  
CREATE ASSEMBLY tvfEventLog   
FROM 'D:\assemblies\tvfEventLog\tvfeventlog.dll'   
WITH PERMISSION_SET = EXTERNAL_ACCESS;  
GO  
CREATE FUNCTION ReadEventLog(@logname nvarchar(100))  
RETURNS TABLE   
(logTime datetime,Message nvarchar(4000),Category nvarchar(4000),InstanceId bigint)  
AS   
EXTERNAL NAME tvfEventLog.TabularEventLog.InitMethod;  
GO  
```  
  
 <span data-ttu-id="59bc0-154">Visual C++-Datenbankobjekte, die mit /clr:pure kompiliert wurden, können nicht in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="59bc0-154">Visual C++ database objects compiled with /clr:pure are not supported for execution on [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="59bc0-155">Zu solchen Datenbankobjekten gehören beispielsweise Tabellenwertfunktionen.</span><span class="sxs-lookup"><span data-stu-id="59bc0-155">For example, such database objects include table-valued functions.</span></span>  
  
 <span data-ttu-id="59bc0-156">Führen Sie den folgenden [!INCLUDE[tsql](../../includes/tsql-md.md)] -Code aus, um das Beispiel zu testen:</span><span class="sxs-lookup"><span data-stu-id="59bc0-156">To test the sample, try the following [!INCLUDE[tsql](../../includes/tsql-md.md)] code:</span></span>  
  
```  
-- Select the top 100 events,  
SELECT TOP 100 *  
FROM dbo.ReadEventLog(N'Security') as T;  
go  
  
-- Select the last 10 login events.  
SELECT TOP 10 T.logTime, T.Message, T.InstanceId   
FROM dbo.ReadEventLog(N'Security') as T  
WHERE T.Category = N'Logon/Logoff';  
go  
```  
  
## <a name="sample-returning-the-results-of-a-sql-server-query"></a><span data-ttu-id="59bc0-157">Beispiel: Zurückgeben der Ergebnisse einer SQL Server-Abfrage</span><span class="sxs-lookup"><span data-stu-id="59bc0-157">Sample: Returning the Results of a SQL Server Query</span></span>  
 <span data-ttu-id="59bc0-158">Im folgenden Beispiel wird eine Tabellenwertfunktion gezeigt, die eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbank abfragt.</span><span class="sxs-lookup"><span data-stu-id="59bc0-158">The following sample shows a table-valued function that queries a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="59bc0-159">In diesem Beispiel wird die AdventureWorks Datenbank Light aus [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]verwendet.</span><span class="sxs-lookup"><span data-stu-id="59bc0-159">This sample uses the AdventureWorks Light database from [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span> <span data-ttu-id="59bc0-160">[https://www.codeplex.com/sqlserversamples](https://go.microsoft.com/fwlink/?LinkId=87843)Weitere Informationen zum Herunterladen von AdventureWorks finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="59bc0-160">See [https://www.codeplex.com/sqlserversamples](https://go.microsoft.com/fwlink/?LinkId=87843) for more information on downloading AdventureWorks.</span></span>  
  
 <span data-ttu-id="59bc0-161">Nennen Sie die Quellcodedatei FindInvalidEmails.cs bzw. FindInvalidEmails.vb.</span><span class="sxs-lookup"><span data-stu-id="59bc0-161">Name your source code file FindInvalidEmails.cs or FindInvalidEmails.vb.</span></span>  
  
```csharp  
using System;  
using System.Collections;  
using System.Data;  
using System.Data.SqlClient;  
using System.Data.SqlTypes;  
  
using Microsoft.SqlServer.Server;  
  
public partial class UserDefinedFunctions {  
   private class EmailResult {  
      public SqlInt32 CustomerId;  
      public SqlString EmailAdress;  
  
      public EmailResult(SqlInt32 customerId, SqlString emailAdress) {  
         CustomerId = customerId;  
         EmailAdress = emailAdress;  
      }  
   }  
  
   public static bool ValidateEmail(SqlString emailAddress) {  
      if (emailAddress.IsNull)  
         return false;  
  
      if (!emailAddress.Value.EndsWith("@adventure-works.com"))  
         return false;  
  
      // Validate the address. Put any more rules here.  
      return true;  
   }  
  
   [SqlFunction(  
       DataAccess = DataAccessKind.Read,  
       FillRowMethodName = "FindInvalidEmails_FillRow",  
       TableDefinition="CustomerId int, EmailAddress nvarchar(4000)")]  
   public static IEnumerable FindInvalidEmails(SqlDateTime modifiedSince) {  
      ArrayList resultCollection = new ArrayList();  
  
      using (SqlConnection connection = new SqlConnection("context connection=true")) {  
         connection.Open();  
  
         using (SqlCommand selectEmails = new SqlCommand(  
             "SELECT " +  
             "[CustomerID], [EmailAddress] " +  
             "FROM [AdventureWorksLT2008].[SalesLT].[Customer] " +  
             "WHERE [ModifiedDate] >= @modifiedSince",  
             connection)) {  
            SqlParameter modifiedSinceParam = selectEmails.Parameters.Add(  
                "@modifiedSince",  
                SqlDbType.DateTime);  
            modifiedSinceParam.Value = modifiedSince;  
  
            using (SqlDataReader emailsReader = selectEmails.ExecuteReader()) {  
               while (emailsReader.Read()) {  
                  SqlString emailAddress = emailsReader.GetSqlString(1);  
                  if (ValidateEmail(emailAddress)) {  
                     resultCollection.Add(new EmailResult(  
                         emailsReader.GetSqlInt32(0),  
                         emailAddress));  
                  }  
               }  
            }  
         }  
      }  
  
      return resultCollection;  
   }  
  
   public static void FindInvalidEmails_FillRow(  
       object emailResultObj,  
       out SqlInt32 customerId,  
       out SqlString emailAdress) {  
      EmailResult emailResult = (EmailResult)emailResultObj;  
  
      customerId = emailResult.CustomerId;  
      emailAdress = emailResult.EmailAdress;  
   }  
};  
```  
  
```vb  
Imports System.Collections  
Imports System.Data  
Imports System.Data.SqlClient  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
  
Public Partial Class UserDefinedFunctions  
   Private Class EmailResult  
      Public CustomerId As SqlInt32  
      Public EmailAdress As SqlString  
  
      Public Sub New(customerId__1 As SqlInt32, emailAdress__2 As SqlString)  
         CustomerId = customerId__1  
         EmailAdress = emailAdress__2  
      End Sub  
   End Class  
  
   Public Shared Function ValidateEmail(emailAddress As SqlString) As Boolean  
      If emailAddress.IsNull Then  
         Return False  
      End If  
  
      If Not emailAddress.Value.EndsWith("@adventure-works.com") Then  
         Return False  
      End If  
  
      ' Validate the address. Put any more rules here.  
      Return True  
   End Function  
  
   <SqlFunction(DataAccess := DataAccessKind.Read, FillRowMethodName := "FindInvalidEmails_FillRow", TableDefinition := "CustomerId int, EmailAddress nvarchar(4000)")> _  
   Public Shared Function FindInvalidEmails(modifiedSince As SqlDateTime) As IEnumerable  
      Dim resultCollection As New ArrayList()  
  
      Using connection As New SqlConnection("context connection=true")  
         connection.Open()  
  
         Using selectEmails As New SqlCommand("SELECT " & "[CustomerID], [EmailAddress] " & "FROM [AdventureWorksLT2008].[SalesLT].[Customer] " & "WHERE [ModifiedDate] >= @modifiedSince", connection)  
            Dim modifiedSinceParam As SqlParameter = selectEmails.Parameters.Add("@modifiedSince", SqlDbType.DateTime)  
            modifiedSinceParam.Value = modifiedSince  
  
            Using emailsReader As SqlDataReader = selectEmails.ExecuteReader()  
               While emailsReader.Read()  
                  Dim emailAddress As SqlString = emailsReader.GetSqlString(1)  
                  If ValidateEmail(emailAddress) Then  
                     resultCollection.Add(New EmailResult(emailsReader.GetSqlInt32(0), emailAddress))  
                  End If  
               End While  
            End Using  
         End Using  
      End Using  
  
      Return resultCollection  
   End Function  
  
   Public Shared Sub FindInvalidEmails_FillRow(emailResultObj As Object, ByRef customerId As SqlInt32, ByRef emailAdress As SqlString)  
      Dim emailResult As EmailResult = DirectCast(emailResultObj, EmailResult)  
  
      customerId = emailResult.CustomerId  
      emailAdress = emailResult.EmailAdress  
   End Sub  
End ClassImports System.Collections  
Imports System.Data  
Imports System.Data.SqlClient  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
  
Public Partial Class UserDefinedFunctions  
   Private Class EmailResult  
      Public CustomerId As SqlInt32  
      Public EmailAdress As SqlString  
  
      Public Sub New(customerId__1 As SqlInt32, emailAdress__2 As SqlString)  
         CustomerId = customerId__1  
         EmailAdress = emailAdress__2  
      End Sub  
   End Class  
  
   Public Shared Function ValidateEmail(emailAddress As SqlString) As Boolean  
      If emailAddress.IsNull Then  
         Return False  
      End If  
  
      If Not emailAddress.Value.EndsWith("@adventure-works.com") Then  
         Return False  
      End If  
  
      ' Validate the address. Put any more rules here.  
      Return True  
   End Function  
  
   <SqlFunction(DataAccess := DataAccessKind.Read, FillRowMethodName := "FindInvalidEmails_FillRow", TableDefinition := "CustomerId int, EmailAddress nvarchar(4000)")> _  
   Public Shared Function FindInvalidEmails(modifiedSince As SqlDateTime) As IEnumerable  
      Dim resultCollection As New ArrayList()  
  
      Using connection As New SqlConnection("context connection=true")  
         connection.Open()  
  
         Using selectEmails As New SqlCommand("SELECT " & "[CustomerID], [EmailAddress] " & "FROM [AdventureWorksLT2008].[SalesLT].[Customer] " & "WHERE [ModifiedDate] >= @modifiedSince", connection)  
            Dim modifiedSinceParam As SqlParameter = selectEmails.Parameters.Add("@modifiedSince", SqlDbType.DateTime)  
            modifiedSinceParam.Value = modifiedSince  
  
            Using emailsReader As SqlDataReader = selectEmails.ExecuteReader()  
               While emailsReader.Read()  
                  Dim emailAddress As SqlString = emailsReader.GetSqlString(1)  
                  If ValidateEmail(emailAddress) Then  
                     resultCollection.Add(New EmailResult(emailsReader.GetSqlInt32(0), emailAddress))  
                  End If  
               End While  
            End Using  
         End Using  
      End Using  
  
      Return resultCollection  
   End Function  
  
   Public Shared Sub FindInvalidEmails_FillRow(emailResultObj As Object, customerId As SqlInt32, emailAdress As SqlString)  
      Dim emailResult As EmailResult = DirectCast(emailResultObj, EmailResult)  
  
      customerId = emailResult.CustomerId  
      emailAdress = emailResult.EmailAdress  
   End Sub  
End Class  
```  
  
 <span data-ttu-id="59bc0-162">Kompilieren Sie den Quellcode zu einer DLL, und kopieren Sie die DLL in das Stammverzeichnis von Laufwerk C:.</span><span class="sxs-lookup"><span data-stu-id="59bc0-162">Compile the source code to a DLL and copy the DLL to the root directory of your C drive.</span></span>  <span data-ttu-id="59bc0-163">Führen Sie dann die folgende [!INCLUDE[tsql](../../includes/tsql-md.md)] -Abfrage aus.</span><span class="sxs-lookup"><span data-stu-id="59bc0-163">Then, execute the following [!INCLUDE[tsql](../../includes/tsql-md.md)] query.</span></span>  
  
```  
use AdventureWorksLT2008;  
go  
  
IF EXISTS (SELECT name FROM sysobjects WHERE name = 'FindInvalidEmails')  
   DROP FUNCTION FindInvalidEmails;  
go  
  
IF EXISTS (SELECT name FROM sys.assemblies WHERE name = 'MyClrCode')  
   DROP ASSEMBLY MyClrCode;  
go  
  
CREATE ASSEMBLY MyClrCode FROM 'C:\FindInvalidEmails.dll'  
WITH PERMISSION_SET = SAFE -- EXTERNAL_ACCESS;  
GO  
  
CREATE FUNCTION FindInvalidEmails(@ModifiedSince datetime)   
RETURNS TABLE (  
   CustomerId int,  
   EmailAddress nvarchar(4000)  
)  
AS EXTERNAL NAME MyClrCode.UserDefinedFunctions.[FindInvalidEmails];  
go  
  
SELECT * FROM FindInvalidEmails('2000-01-01');  
go  
```  
  
