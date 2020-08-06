---
title: Gespeicherte CLR-Prozeduren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- database objects [CLR integration], stored procedures
- stored procedures [CLR integration]
- common language runtime [SQL Server], stored procedures
- building database objects [CLR integration], stored procedures
- output parameters [CLR integration]
- tabular results
ms.assetid: bbdd51b2-a9b4-4916-ba6f-7957ac6c3f33
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: f8c69435e28bfa67c72e26b7a54e419cd91ef220
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615542"
---
# <a name="clr-stored-procedures"></a><span data-ttu-id="b5b9e-102">CLR-gespeicherte Prozeduren</span><span class="sxs-lookup"><span data-stu-id="b5b9e-102">CLR Stored Procedures</span></span>
  <span data-ttu-id="b5b9e-103">Gespeicherte Prozeduren sind Routinen, die nicht in Skalarausdrücken verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="b5b9e-103">Stored procedures are routines that cannot be used in scalar expressions.</span></span> <span data-ttu-id="b5b9e-104">Im Gegensatz zu Skalarfunktionen können sie tabellarische Ergebnisse und Meldungen an den Client zurückgeben, Anweisungen in Datendefinitionssprache (DDL, Data Definition Language) und in Datenbearbeitungssprache (DML, Data Manipulation Language) aufrufen und Ausgabeparameter zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="b5b9e-104">Unlike scalar functions, they can return tabular results and messages to the client, invoke data definition language (DDL) and data manipulation language (DML) statements, and return output parameters.</span></span> <span data-ttu-id="b5b9e-105">Informationen zu den Vorteilen der CLR-Integration und zur Auswahl zwischen verwaltetem Code und [!INCLUDE[tsql](../../includes/tsql-md.md)] finden Sie unter [Übersicht über die CLR-Integration](../../relational-databases/clr-integration/clr-integration-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b5b9e-105">For information about the advantages of CLR integration and choosing between managed code and [!INCLUDE[tsql](../../includes/tsql-md.md)], see [Overview of CLR Integration](../../relational-databases/clr-integration/clr-integration-overview.md).</span></span>  
  
## <a name="requirements-for-clr-stored-procedures"></a><span data-ttu-id="b5b9e-106">Anforderungen für gespeicherte CLR-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="b5b9e-106">Requirements for CLR Stored Procedures</span></span>  
 <span data-ttu-id="b5b9e-107">In der Common Language Runtime (CLR) werden gespeicherte Prozeduren als öffentliche statische Methoden für eine Klasse in einer [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] Assembly implementiert.</span><span class="sxs-lookup"><span data-stu-id="b5b9e-107">In the common language runtime (CLR), stored procedures are implemented as public static methods on a class in a [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] assembly.</span></span> <span data-ttu-id="b5b9e-108">Die statische Methode kann entweder als ungültig deklariert werden oder gibt einen ganzzahligen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="b5b9e-108">The static method can either be declared as void, or return an integer value.</span></span> <span data-ttu-id="b5b9e-109">Wenn sie einen ganzzahligen Wert zurückgibt, wird die ganze Zahl von der Prozedur als Rückgabecode behandelt.</span><span class="sxs-lookup"><span data-stu-id="b5b9e-109">If it returns an integer value, the integer returned is treated as the return code from the procedure.</span></span> <span data-ttu-id="b5b9e-110">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b5b9e-110">For example:</span></span>  
  
 `EXECUTE @return_status = procedure_name`  
  
 <span data-ttu-id="b5b9e-111">Die- @return_status Variable enthält den Wert, der von der-Methode zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="b5b9e-111">The @return_status variable will contain the value returned by the method.</span></span> <span data-ttu-id="b5b9e-112">Wenn die Methode als ungültig deklariert wird, ist der Rückgabecode 0.</span><span class="sxs-lookup"><span data-stu-id="b5b9e-112">If the method is declared void, the return code is 0.</span></span>  
  
 <span data-ttu-id="b5b9e-113">Wenn die Methode Parameter verwendet, sollte die Anzahl der Parameter in der [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]-Implementierung mit der Anzahl der Parameter in der [!INCLUDE[tsql](../../includes/tsql-md.md)]-Deklaration der gespeicherten Prozedur übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="b5b9e-113">If the method takes parameters, the number of parameters in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] implementation should be the same as the number of parameters used in the [!INCLUDE[tsql](../../includes/tsql-md.md)] declaration of the stored procedure.</span></span>  
  
 <span data-ttu-id="b5b9e-114">Bei den an eine gespeicherte CLR-Prozedur weitergegebenen Parametern kann es sich um einen beliebigen der systemeigenen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Typen handeln, die über eine Entsprechung im verwalteten Code verfügen.</span><span class="sxs-lookup"><span data-stu-id="b5b9e-114">Parameters passed to a CLR stored procedure can be any of the native [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] types that have an equivalent in managed code.</span></span> <span data-ttu-id="b5b9e-115">Damit die [!INCLUDE[tsql](../../includes/tsql-md.md)]-Syntax die Prozedur erstellen kann, sollten diese Typen mit dem am besten passenden systemeigenen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Typ angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b5b9e-115">For the [!INCLUDE[tsql](../../includes/tsql-md.md)] syntax to create the procedure, these types should be specified with the most appropriate native [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] type equivalent.</span></span> <span data-ttu-id="b5b9e-116">Weitere Informationen zu Typkonvertierungen finden Sie unter [Mapping von CLR-Parameter Daten](../../relational-databases/clr-integration-database-objects-types-net-framework/mapping-clr-parameter-data.md).</span><span class="sxs-lookup"><span data-stu-id="b5b9e-116">For more information about type conversions, see [Mapping CLR Parameter Data](../../relational-databases/clr-integration-database-objects-types-net-framework/mapping-clr-parameter-data.md).</span></span>  
  
### <a name="table-valued-parameters"></a><span data-ttu-id="b5b9e-117">Tabellenwertparameter</span><span class="sxs-lookup"><span data-stu-id="b5b9e-117">Table-Valued Parameters</span></span>  
 <span data-ttu-id="b5b9e-118">Tabellenwertparameter (Table Valued Parameters, TVPs), benutzerdefinierte Tabellentypen, die an eine Prozedur oder Funktion übergeben werden, bieten eine effiziente Methode zum Übergeben mehrerer Datenzeilen an den Server.</span><span class="sxs-lookup"><span data-stu-id="b5b9e-118">Table-valued parameters (TVPs), user-defined table types that are passed into a procedure or function, provide an efficient way to pass multiple rows of data to the server.</span></span> <span data-ttu-id="b5b9e-119">TVPs verfügen über eine ähnliche Funktionalität wie Parameterarrays, bieten aber größere Flexibilität und engere Integration mit [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b5b9e-119">TVPs provide similar functionality to parameter arrays, but offer greater flexibility and closer integration with [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="b5b9e-120">Außerdem verfügen sie auch über ein besseres Leistungspotenzial.</span><span class="sxs-lookup"><span data-stu-id="b5b9e-120">They also provide the potential for better performance.</span></span> <span data-ttu-id="b5b9e-121">TVPs helfen auch, die Anzahl von Roundtrips zum Server zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="b5b9e-121">TVPs also help reduce the number of round trips to the server.</span></span> <span data-ttu-id="b5b9e-122">Anstatt mehrere Anforderungen an den Server zu senden, z. B. mit einer Liste von skalaren Parametern, können Daten als TVP an den Server gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="b5b9e-122">Instead of sending multiple requests to the server, such as with a list of scalar parameters, data can be sent to the server as a TVP.</span></span> <span data-ttu-id="b5b9e-123">Ein benutzerdefinierter Tabellentyp kann nicht als Tabellenwertparameter an eine verwaltete gespeicherte Prozedur oder Funktion übergeben werden, die im [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Prozess ausgeführt wird, oder von einer solchen Prozedur oder Funktion zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b5b9e-123">A user-defined table type cannot be passed as a table-valued parameter to, or be returned from, a managed stored procedure or function executing in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] process.</span></span> <span data-ttu-id="b5b9e-124">Weitere Informationen zu TVPs finden Sie unter [Verwenden von Tabellenwert Parametern &#40;Datenbank-Engine&#41;](../../relational-databases/tables/use-table-valued-parameters-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="b5b9e-124">For more information about TVPs, see [Use Table-Valued Parameters &#40;Database Engine&#41;](../../relational-databases/tables/use-table-valued-parameters-database-engine.md).</span></span>  
  
## <a name="returning-results-from-clr-stored-procedures"></a><span data-ttu-id="b5b9e-125">Zurückgeben von Ergebnissen von gespeicherten CLR-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="b5b9e-125">Returning Results from CLR Stored Procedures</span></span>  
 <span data-ttu-id="b5b9e-126">Informationen werden möglicherweise auf mehrere Weisen in gespeicherten [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]-Prozeduren zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b5b9e-126">Information may be returned from [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] stored procedures in several ways.</span></span> <span data-ttu-id="b5b9e-127">Dies schließt Ausgabeparameter, Tabellenergebnisse und Meldungen ein.</span><span class="sxs-lookup"><span data-stu-id="b5b9e-127">This includes output parameters, tabular results, and messages.</span></span>  
  
### <a name="output-parameters-and-clr-stored-procedures"></a><span data-ttu-id="b5b9e-128">OUTPUT-Parameter und gespeicherte CLR-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="b5b9e-128">OUTPUT Parameters and CLR Stored Procedures</span></span>  
 <span data-ttu-id="b5b9e-129">Wie bei gespeicherten [!INCLUDE[tsql](../../includes/tsql-md.md)]-Prozeduren werden Informationen möglicherweise mit OUTPUT-Parametern in gespeicherten [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]-Prozeduren zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b5b9e-129">As with [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedures, information may be returned from [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] stored procedures using OUTPUT parameters.</span></span> <span data-ttu-id="b5b9e-130">Die [!INCLUDE[tsql](../../includes/tsql-md.md)]-DML-Syntax, die zum Erstellen von gespeicherten [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]-Prozeduren verwendet wird, ist mit der Syntax identisch, die zum Erstellen gespeicherter Prozeduren, die in [!INCLUDE[tsql](../../includes/tsql-md.md)] geschrieben werden, verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b5b9e-130">The [!INCLUDE[tsql](../../includes/tsql-md.md)] DML syntax used for creating [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] stored procedures is the same as that used for creating stored procedures written in [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="b5b9e-131">Der entsprechende Parameter im Implementierungscode der [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]-Klasse sollte einen als Verweis zu übergebenden Parameter als Argument verwenden.</span><span class="sxs-lookup"><span data-stu-id="b5b9e-131">The corresponding parameter in the implementation code in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] class should use a pass-by-reference parameter as the argument.</span></span> <span data-ttu-id="b5b9e-132">Beachten Sie, dass Visual Basic Ausgabeparameter nicht auf die gleiche Weise unterstützt wie c#.</span><span class="sxs-lookup"><span data-stu-id="b5b9e-132">Note that Visual Basic does not support output parameters in the same way that C# does.</span></span> <span data-ttu-id="b5b9e-133">Sie müssen den Parameter als Verweis angeben und das- \<Out()> Attribut auf die Darstellung eines Ausgabe Parameters anwenden, wie im folgenden dargestellt:</span><span class="sxs-lookup"><span data-stu-id="b5b9e-133">You must specify the parameter by reference and apply the \<Out()> attribute to represent an OUTPUT parameter, as in the following:</span></span>  
  
```vb
Imports System.Runtime.InteropServices  
...  
Public Shared Sub PriceSum ( <Out()> ByRef value As SqlInt32)  
```  
  
 <span data-ttu-id="b5b9e-134">Das folgende Beispiel zeigt eine gespeicherte Prozedur, die Informationen über einen OUTPUT-Parameter zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="b5b9e-134">The following shows a stored procedure returning information through an OUTPUT parameter:</span></span>  
  
```csharp  
using System;  
using System.Data.SqlTypes;  
using System.Data.SqlClient;  
using Microsoft.SqlServer.Server;   
  
public class StoredProcedures   
{  
   [Microsoft.SqlServer.Server.SqlProcedure]  
   public static void PriceSum(out SqlInt32 value)  
   {  
      using(SqlConnection connection = new SqlConnection("context connection=true"))   
      {  
         value = 0;  
         connection.Open();  
         SqlCommand command = new SqlCommand("SELECT Price FROM Products", connection);  
         SqlDataReader reader = command.ExecuteReader();  
  
         using (reader)  
         {  
            while( reader.Read() )  
            {  
               value += reader.GetSqlInt32(0);  
            }  
         }           
      }  
   }  
}  
```  
  
```vb  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlClient  
Imports System.Runtime.InteropServices  
  
'The Partial modifier is only required on one class definition per project.  
Partial Public Class StoredProcedures   
    ''' <summary>  
    ''' Executes a query and iterates over the results to perform a summation.  
    ''' </summary>  
    <Microsoft.SqlServer.Server.SqlProcedure> _  
    Public Shared Sub PriceSum( <Out()> ByRef value As SqlInt32)  
  
        Using connection As New SqlConnection("context connection=true")  
           value = 0  
           Connection.Open()  
           Dim command As New SqlCommand("SELECT Price FROM Products", connection)  
           Dim reader As SqlDataReader  
           reader = command.ExecuteReader()  
  
           Using reader  
              While reader.Read()  
                 value += reader.GetSqlInt32(0)  
              End While  
           End Using  
        End Using          
    End Sub  
End Class  
```  
  
 <span data-ttu-id="b5b9e-135">Nachdem die Assembly mit der obigen gespeicherten CLR-Prozedur erstellt und auf dem Server erstellt wurde, wird Folgendes [!INCLUDE[tsql](../../includes/tsql-md.md)] verwendet, um die Prozedur in der Datenbank zu erstellen, und die *Summe* wird als Output-Parameter angegeben.</span><span class="sxs-lookup"><span data-stu-id="b5b9e-135">Once the assembly containing the above CLR stored procedure has been built and created on the server, the following [!INCLUDE[tsql](../../includes/tsql-md.md)] is used to create the procedure in the database, and specifies *sum* as an OUTPUT parameter.</span></span>  
  
```sql
CREATE PROCEDURE PriceSum (@sum int OUTPUT)  
AS EXTERNAL NAME TestStoredProc.StoredProcedures.PriceSum  
-- if StoredProcedures class was inside a namespace, called MyNS,  
-- you would use:  
-- AS EXTERNAL NAME TestStoredProc.[MyNS.StoredProcedures].PriceSum  
```  
  
 <span data-ttu-id="b5b9e-136">Beachten Sie, dass *Sum* als `int` SQL Server-Datentyp deklariert wird und dass der in der gespeicherten CLR-Prozedur definierte *Wert* Parameter als `SqlInt32` CLR-Datentyp angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="b5b9e-136">Note that *sum* is declared as an `int` SQL Server data type, and that the *value* parameter defined in the CLR stored procedure is specified as a `SqlInt32` CLR data type.</span></span> <span data-ttu-id="b5b9e-137">Wenn ein Aufruf Endes Programm die gespeicherte CLR-Prozedur ausführt, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] konvertiert den `SqlInt32` CLR-Datentyp automatisch in einen- `int` [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Datentyp.</span><span class="sxs-lookup"><span data-stu-id="b5b9e-137">When a calling program executes the CLR stored procedure, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] automatically converts the `SqlInt32` CLR data type to an `int`[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type.</span></span>  <span data-ttu-id="b5b9e-138">Weitere Informationen zu den CLR-Datentypen, die konvertiert werden können, finden Sie unter [Mapping von CLR-Parameter Daten](../../relational-databases/clr-integration-database-objects-types-net-framework/mapping-clr-parameter-data.md).</span><span class="sxs-lookup"><span data-stu-id="b5b9e-138">For more information about which CLR data types can and cannot be converted, see [Mapping CLR Parameter Data](../../relational-databases/clr-integration-database-objects-types-net-framework/mapping-clr-parameter-data.md).</span></span>  
  
### <a name="returning-tabular-results-and-messages"></a><span data-ttu-id="b5b9e-139">Zurückgeben von Tabellenergebnissen und Meldungen</span><span class="sxs-lookup"><span data-stu-id="b5b9e-139">Returning Tabular Results and Messages</span></span>  
 <span data-ttu-id="b5b9e-140">Das Zurückgeben von tabellarischen Ergebnissen und Meldungen an den Client erfolgt durch das `SqlPipe`-Objekt, das mithilfe der `Pipe`-Eigenschaft der `SqlContext`-Klasse abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="b5b9e-140">Returning tabular results and messages to the client is done through the `SqlPipe` object, which is obtained by using the `Pipe` property of the `SqlContext` class.</span></span> <span data-ttu-id="b5b9e-141">Das `SqlPipe`-Objekt verfügt über eine `Send`-Methode.</span><span class="sxs-lookup"><span data-stu-id="b5b9e-141">The `SqlPipe` object has a `Send` method.</span></span> <span data-ttu-id="b5b9e-142">Durch das Aufrufen der `Send`-Methode können Sie Daten durch die Pipe zur aufrufenden Anwendung senden.</span><span class="sxs-lookup"><span data-stu-id="b5b9e-142">By calling the `Send` method, you can transmit data through the pipe to the calling application.</span></span>  
  
 <span data-ttu-id="b5b9e-143">Dies sind verschiedene Überladungen der `SqlPipe.Send`-Methode, darunter eine, die `SqlDataReader` sendet und eine andere, die einfach eine Textzeichenfolge sendet.</span><span class="sxs-lookup"><span data-stu-id="b5b9e-143">These are several overloads of the `SqlPipe.Send` method, including one that sends a `SqlDataReader` and another that simply sends a text string.</span></span>  
  
###### <a name="returning-messages"></a><span data-ttu-id="b5b9e-144">Zurückgeben von Meldungen</span><span class="sxs-lookup"><span data-stu-id="b5b9e-144">Returning Messages</span></span>  
 <span data-ttu-id="b5b9e-145">Verwenden Sie `SqlPipe.Send(string)`, um Meldungen an die Clientanwendung zu senden.</span><span class="sxs-lookup"><span data-stu-id="b5b9e-145">Use `SqlPipe.Send(string)` to send messages to the client application.</span></span> <span data-ttu-id="b5b9e-146">Der Text der Meldung ist auf 8000 Zeichen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="b5b9e-146">The text of the message is limited to 8000 characters.</span></span> <span data-ttu-id="b5b9e-147">Wenn die Meldung 8000 Zeichen überschreitet, wird sie abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="b5b9e-147">If the message exceeds 8000 characters, it will be truncated.</span></span>  
  
###### <a name="returning-tabular-results"></a><span data-ttu-id="b5b9e-148">Zurückgeben von tabellarischen Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="b5b9e-148">Returning Tabular Results</span></span>  
 <span data-ttu-id="b5b9e-149">Um die Ergebnisse einer Abfrage direkt an den Client zu senden, verwenden Sie eine Überladung der `Execute`-Methode des `SqlPipe`-Objekts.</span><span class="sxs-lookup"><span data-stu-id="b5b9e-149">To send the results of a query directly to the client, use one of the overloads of the `Execute` method on the `SqlPipe` object.</span></span> <span data-ttu-id="b5b9e-150">Dies ist die effizienteste Methode zum Zurückgeben von Ergebnissen an den Client, da die Daten zu den Netzwerkpuffern übertragen werden, ohne in den verwalteten Arbeitsspeicher kopiert zu werden.</span><span class="sxs-lookup"><span data-stu-id="b5b9e-150">This is the most efficient way to return results to the client, since the data is transferred to the network buffers without being copied into managed memory.</span></span> <span data-ttu-id="b5b9e-151">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b5b9e-151">For example:</span></span>  
  
```csharp  
using System;  
using System.Data;  
using System.Data.SqlTypes;  
using System.Data.SqlClient;  
using Microsoft.SqlServer.Server;   
  
public class StoredProcedures   
{  
   /// <summary>  
   /// Execute a command and send the results to the client directly.  
   /// </summary>  
   [Microsoft.SqlServer.Server.SqlProcedure]  
   public static void ExecuteToClient()  
   {  
   using(SqlConnection connection = new SqlConnection("context connection=true"))   
   {  
      connection.Open();  
      SqlCommand command = new SqlCommand("select @@version", connection);  
      SqlContext.Pipe.ExecuteAndSend(command);  
      }  
   }  
}  
```  
  
```vb  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlClient  
  
'The Partial modifier is only required on one class definition per project.  
Partial Public Class StoredProcedures   
    ''' <summary>  
    ''' Execute a command and send the results to the client directly.  
    ''' </summary>  
    <Microsoft.SqlServer.Server.SqlProcedure> _  
    Public Shared Sub ExecuteToClient()  
        Using connection As New SqlConnection("context connection=true")  
            connection.Open()  
            Dim command As New SqlCommand("SELECT @@VERSION", connection)  
            SqlContext.Pipe.ExecuteAndSend(command)  
        End Using  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="b5b9e-152">Um eine zuvor ausgeführte Abfrage über den prozessinternen Anbieter zu senden (oder um die Daten mithilfe einer benutzerdefinierten Implementierung von `SqlDataReader` vorab zu verarbeiten), verwenden Sie die Überladung der `Send`-Methode, die `SqlDataReader` verwendet.</span><span class="sxs-lookup"><span data-stu-id="b5b9e-152">To send the results of a query that was executed previously through the in-process provider (or to pre-process the data using a custom implementation of `SqlDataReader`), use the overload of the `Send` method that takes a `SqlDataReader`.</span></span> <span data-ttu-id="b5b9e-153">Diese Methode ist etwas langsamer als die zuvor beschriebene direkte Methode, bietet aber größere Flexibilität zum Ändern der Daten, bevor sie an den Client gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="b5b9e-153">This method is slightly slower than the direct method described previously, but it offers greater flexibility to manipulate the data before it is sent to the client.</span></span>  
  
```csharp  
using System;  
using System.Data;  
using System.Data.SqlTypes;  
using System.Data.SqlClient;  
using Microsoft.SqlServer.Server;   
  
public class StoredProcedures   
{  
   /// <summary>  
   /// Execute a command and send the resulting reader to the client  
   /// </summary>  
   [Microsoft.SqlServer.Server.SqlProcedure]  
   public static void SendReaderToClient()  
   {  
      using(SqlConnection connection = new SqlConnection("context connection=true"))   
      {  
         connection.Open();  
         SqlCommand command = new SqlCommand("select @@version", connection);  
         SqlDataReader r = command.ExecuteReader();  
         SqlContext.Pipe.Send(r);  
      }  
   }  
}  
```  
 
```vb  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlClient  
  
'The Partial modifier is only required on one class definition per project.  
Partial Public Class StoredProcedures   
    ''' <summary>  
    ''' Execute a command and send the results to the client directly.  
    ''' </summary>  
    <Microsoft.SqlServer.Server.SqlProcedure> _  
    Public Shared Sub SendReaderToClient()  
        Using connection As New SqlConnection("context connection=true")  
            connection.Open()  
            Dim command As New SqlCommand("SELECT @@VERSION", connection)  
            Dim reader As SqlDataReader  
            reader = command.ExecuteReader()  
            SqlContext.Pipe.Send(reader)  
        End Using  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="b5b9e-154">Um ein dynamisches Resultset zu erstellen, füllen Sie es, und senden Sie es an den Client. Sie können Datensätze aus der aktuellen Verbindung erstellen und sie mithilfe von `SqlPipe.Send` senden.</span><span class="sxs-lookup"><span data-stu-id="b5b9e-154">To create a dynamic result set, populate it and send it to the client, you can create records from the current connection and send them using `SqlPipe.Send`.</span></span>  
  
```csharp  
using System.Data;  
using System.Data.SqlClient;  
using Microsoft.SqlServer.Server;   
using System.Data.SqlTypes;  
  
public class StoredProcedures   
{  
   /// <summary>  
   /// Create a result set on the fly and send it to the client.  
   /// </summary>  
   [Microsoft.SqlServer.Server.SqlProcedure]  
   public static void SendTransientResultSet()  
   {  
      // Create a record object that represents an individual row, including it's metadata.  
      SqlDataRecord record = new SqlDataRecord(new SqlMetaData("stringcol", SqlDbType.NVarChar, 128));  
  
      // Populate the record.  
      record.SetSqlString(0, "Hello World!");  
  
      // Send the record to the client.  
      SqlContext.Pipe.Send(record);  
   }  
}  
```  
  
```vb  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlClient  
  
'The Partial modifier is only required on one class definition per project.  
Partial Public Class StoredProcedures   
    ''' <summary>  
    ''' Create a result set on the fly and send it to the client.  
    ''' </summary>  
    <Microsoft.SqlServer.Server.SqlProcedure> _  
    Public Shared Sub SendTransientResultSet()  
        ' Create a record object that represents an individual row, including it's metadata.  
        Dim record As New SqlDataRecord(New SqlMetaData("stringcol", SqlDbType.NVarChar, 128) )  
  
        ' Populate the record.  
        record.SetSqlString(0, "Hello World!")  
  
        ' Send the record to the client.  
        SqlContext.Pipe.Send(record)          
    End Sub  
End Class   
```  
  
 <span data-ttu-id="b5b9e-155">Hier ist ein Beispiel für das Senden eines tabellarischen Ergebnisses und einer Meldung durch `SqlPipe`.</span><span class="sxs-lookup"><span data-stu-id="b5b9e-155">Here is an example of sending a tabular result and a message through `SqlPipe`.</span></span>  
  
```csharp  
using System.Data.SqlClient;  
using Microsoft.SqlServer.Server;   
  
public class StoredProcedures   
{  
   [Microsoft.SqlServer.Server.SqlProcedure]  
   public static void HelloWorld()  
   {  
      SqlContext.Pipe.Send("Hello world! It's now " + System.DateTime.Now.ToString()+"\n");  
      using(SqlConnection connection = new SqlConnection("context connection=true"))   
      {  
         connection.Open();  
         SqlCommand command = new SqlCommand("SELECT ProductNumber FROM ProductMaster", connection);  
         SqlDataReader reader = command.ExecuteReader();  
         SqlContext.Pipe.Send(reader);  
      }  
   }  
}  
```  
  
```vb  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlClient  
  
'The Partial modifier is only required on one class definition per project.  
Partial Public Class StoredProcedures   
    ''' <summary>  
    ''' Execute a command and send the results to the client directly.  
    ''' </summary>  
    <Microsoft.SqlServer.Server.SqlProcedure> _  
    Public Shared Sub HelloWorld()  
        SqlContext.Pipe.Send("Hello world! It's now " & System.DateTime.Now.ToString() & "\n")  
        Using connection As New SqlConnection("context connection=true")  
            connection.Open()  
            Dim command As New SqlCommand("SELECT ProductNumber FROM ProductMaster", connection)  
            Dim reader As SqlDataReader  
            reader = command.ExecuteReader()  
            SqlContext.Pipe.Send(reader)  
        End Using  
    End Sub  
End Class   
```  
  
 <span data-ttu-id="b5b9e-156">Das erste `Send` sendet eine Meldung an den Client, während das zweite ein tabellarisches Ergebnis mithilfe von `SqlDataReader` sendet.</span><span class="sxs-lookup"><span data-stu-id="b5b9e-156">The first `Send` sends a message to the client, while the second sends a tabular result using `SqlDataReader`.</span></span>  
  
 <span data-ttu-id="b5b9e-157">Beachten Sie, dass diese Beispiele lediglich zu Illustrationszwecken dienen.</span><span class="sxs-lookup"><span data-stu-id="b5b9e-157">Note that these examples are for illustrative purposes only.</span></span> <span data-ttu-id="b5b9e-158">CLR-Funktionen sind für berechnungsintensive Anwendungen geeigneter als einfache [!INCLUDE[tsql](../../includes/tsql-md.md)]-Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="b5b9e-158">CLR functions are more appropriate than simple [!INCLUDE[tsql](../../includes/tsql-md.md)] statements for computation-intensive applications.</span></span> <span data-ttu-id="b5b9e-159">Eine fast identische gespeicherte [!INCLUDE[tsql](../../includes/tsql-md.md)]-Prozedur zum vorherigen Beispiel ist:</span><span class="sxs-lookup"><span data-stu-id="b5b9e-159">An almost equivalent [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure to the previous example is:</span></span>  
  
```sql
CREATE PROCEDURE HelloWorld() AS  
BEGIN  
PRINT('Hello world!')  
SELECT ProductNumber FROM ProductMaster  
END;  
```  
  
> [!NOTE]  
>  <span data-ttu-id="b5b9e-160">Meldungen und Resultsets werden in der Clientanwendung anders abgerufen.</span><span class="sxs-lookup"><span data-stu-id="b5b9e-160">Messages and result sets are retrieved differently in the client application.</span></span> <span data-ttu-id="b5b9e-161">Beispielsweise werden [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Resultsets in der **Ergebnis** Ansicht angezeigt, und Meldungen werden im Bereich **Meldungen** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b5b9e-161">For instance, [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] result sets appear in the **Results** view, and messages appear in the **Messages** pane.</span></span>  
  
 <span data-ttu-id="b5b9e-162">Wenn der oben erwähnte Visual C#-Code in einer Datei MyFirstUdp.cs gespeichert und mit Folgendem kompiliert wird:</span><span class="sxs-lookup"><span data-stu-id="b5b9e-162">If the above Visual C# code is saved in a file MyFirstUdp.cs and compiled with:</span></span>  
  
```console
csc /t:library /out:MyFirstUdp.dll MyFirstUdp.cs   
```  
  
 <span data-ttu-id="b5b9e-163">Oder wenn der oben erwähnte Visual Basic-Code in einer Datei MyFirstUdp.vb gespeichert und mit Folgendem kompiliert wird:</span><span class="sxs-lookup"><span data-stu-id="b5b9e-163">Or, if the above Visual Basic code is saved in a file MyFirstUdp.vb and compiled with:</span></span>  
  
```console
vbc /t:library /out:MyFirstUdp.dll MyFirstUdp.vb   
```  
  
> [!NOTE]  
>  <span data-ttu-id="b5b9e-164">Ab [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] werden Visual C++-Datenbankobjekte (z. B. gespeicherte Prozeduren), die mit `/clr:pure` kompiliert werden, nicht für die Ausführung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b5b9e-164">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], Visual C++ database objects (such as stored procedures) compiled with `/clr:pure` are not supported for execution.</span></span>  
  
 <span data-ttu-id="b5b9e-165">Die resultierende Assembly kann mit folgender DLL registriert und der Einstiegspunkt aufgerufen werden:</span><span class="sxs-lookup"><span data-stu-id="b5b9e-165">The resulting assembly can be registered, and the entry point invoked, with the following DDL:</span></span>  
  
```sql
CREATE ASSEMBLY MyFirstUdp FROM 'C:\Programming\MyFirstUdp.dll';  
CREATE PROCEDURE HelloWorld  
AS EXTERNAL NAME MyFirstUdp.StoredProcedures.HelloWorld;  
EXEC HelloWorld;  
```  
  
## <a name="see-also"></a><span data-ttu-id="b5b9e-166">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b5b9e-166">See Also</span></span>  
 <span data-ttu-id="b5b9e-167">[Benutzerdefinierte CLR-Funktionen](../../relational-databases/clr-integration-database-objects-user-defined-functions/clr-user-defined-functions.md) </span><span class="sxs-lookup"><span data-stu-id="b5b9e-167">[CLR User-Defined Functions](../../relational-databases/clr-integration-database-objects-user-defined-functions/clr-user-defined-functions.md) </span></span>  
 <span data-ttu-id="b5b9e-168">[Benutzerdefinierte CLR-Typen](../../relational-databases/clr-integration-database-objects-user-defined-types/clr-user-defined-types.md) </span><span class="sxs-lookup"><span data-stu-id="b5b9e-168">[CLR User-Defined Types](../../relational-databases/clr-integration-database-objects-user-defined-types/clr-user-defined-types.md) </span></span>  
 [<span data-ttu-id="b5b9e-169">CLR-Trigger</span><span class="sxs-lookup"><span data-stu-id="b5b9e-169">CLR Triggers</span></span>](../../../2014/database-engine/dev-guide/clr-triggers.md)  
  
  
