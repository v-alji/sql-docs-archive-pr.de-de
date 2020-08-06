---
title: SqlPipe-Objekt | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- custom result sets [CLR integration]
- SqlPipe object
- tabular results
ms.assetid: 3e090faf-085f-4c01-a565-79e3f1c36e3b
author: rothja
ms.author: jroth
ms.openlocfilehash: 0044815a0b20d72b48b87bfe8f693d7196aaeaf3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619165"
---
# <a name="sqlpipe-object"></a><span data-ttu-id="5cfe4-102">SqlPipe-Objekt</span><span class="sxs-lookup"><span data-stu-id="5cfe4-102">SqlPipe Object</span></span>
  <span data-ttu-id="5cfe4-103">In früheren Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]war es üblich, eine gespeicherte Prozedur (oder eine erweiterte gespeicherte Prozedur) zu schreiben, die Ergebnisse oder Ausgabeparameter an den aufrufenden Client sendet.</span><span class="sxs-lookup"><span data-stu-id="5cfe4-103">In previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], it is very common to write a stored procedure (or an extended stored procedure) that sends results or output parameters to the calling client.</span></span>  
  
 <span data-ttu-id="5cfe4-104">In einer [!INCLUDE[tsql](../../includes/tsql-md.md)] gespeicherten Prozedur sendet jede `SELECT`-Anweisung, die NULL oder mehr Zeilen zurückgibt, die Ergebnisse an die "Pipe" des verbundenen Aufrufers.</span><span class="sxs-lookup"><span data-stu-id="5cfe4-104">In a [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure, any `SELECT` statement that returns zero or more rows sends the results to the connected caller's "pipe."</span></span>  
  
 <span data-ttu-id="5cfe4-105">Für CLR-Datenbankobjekte (Common Language Runtime), die in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ausgeführt werden, können Sie die Ergebnisse mit der `Send`-Methode des `SqlPipe`-Objekts an die verbundene Pipe senden.</span><span class="sxs-lookup"><span data-stu-id="5cfe4-105">For common language runtime (CLR) database objects running in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you can send results to the connected pipe using the `Send` methods of the `SqlPipe` object.</span></span> <span data-ttu-id="5cfe4-106">Greifen Sie auf die `Pipe`-Eigenschaft des `SqlContext`-Objekts zu, um das `SqlPipe`-Objekt abzurufen.</span><span class="sxs-lookup"><span data-stu-id="5cfe4-106">Access the `Pipe` property of the `SqlContext` object to obtain the `SqlPipe` object.</span></span> <span data-ttu-id="5cfe4-107">Die `SqlPipe`-Klasse gleicht konzeptionell der `Response`-Klasse in ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="5cfe4-107">The `SqlPipe` class is conceptually similar to the `Response` class found in ASP.NET.</span></span> <span data-ttu-id="5cfe4-108">Weitere Informationen finden Sie in der Referenzdokumentation zur SqlPipe-Klasse im .NET Framework Software Development Kit.</span><span class="sxs-lookup"><span data-stu-id="5cfe4-108">For more information, see the SqlPipe Class reference documentation in the .NET Framework software development kit.</span></span>  
  
## <a name="returning-tabular-results-and-messages"></a><span data-ttu-id="5cfe4-109">Zurückgeben von Tabellenergebnissen und Meldungen</span><span class="sxs-lookup"><span data-stu-id="5cfe4-109">Returning Tabular Results and Messages</span></span>  
 <span data-ttu-id="5cfe4-110">`SqlPipe` verfügt über eine `Send`-Methode, die drei Überladungen besitzt.</span><span class="sxs-lookup"><span data-stu-id="5cfe4-110">The `SqlPipe` has a `Send` method, which has three overloads.</span></span> <span data-ttu-id="5cfe4-111">Sie lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="5cfe4-111">They are:</span></span>  
  
-   `void Send(string message)`  
  
-   `void Send(SqlDataReader reader)`  
  
-   `void Send(SqlDataRecord record)`  
  
 <span data-ttu-id="5cfe4-112">Die `Send`-Methode sendet Daten direkt an den Client oder Aufrufer.</span><span class="sxs-lookup"><span data-stu-id="5cfe4-112">The `Send` method sends data straight to the client or caller.</span></span> <span data-ttu-id="5cfe4-113">Normalerweise verwendet der Client die Ausgabe der `SqlPipe`-Methode, im Fall von geschachtelten gespeicherten CLR-Prozeduren kann es sich beim Consumer der Ausgabe jedoch auch um eine gespeicherte Prozedur handeln.</span><span class="sxs-lookup"><span data-stu-id="5cfe4-113">It is usually the client that consumes the output from the `SqlPipe`, but in the case of nested CLR stored procedures the output consumer can also be a stored procedure.</span></span> <span data-ttu-id="5cfe4-114">Beispiel: Procedure1 ruft SqlCommand.ExecuteReader() mit dem Befehlstext "EXEC Procedure2" auf.</span><span class="sxs-lookup"><span data-stu-id="5cfe4-114">For example, Procedure1 calls SqlCommand.ExecuteReader() with the command text "EXEC Procedure2".</span></span> <span data-ttu-id="5cfe4-115">Bei Procedure2 handelt es sich ebenfalls um eine verwaltete gespeicherte Prozedur.</span><span class="sxs-lookup"><span data-stu-id="5cfe4-115">Procedure2 is also a managed stored procedure.</span></span> <span data-ttu-id="5cfe4-116">Wenn Procedure2 jetzt SqlPipe.Send( SqlDataRecord ) aufruft, wird die Zeile an den Reader von Procedure1 und nicht an den Client gesendet.</span><span class="sxs-lookup"><span data-stu-id="5cfe4-116">If Procedure2 now calls SqlPipe.Send( SqlDataRecord ), the row is sent to Procedure1's reader, not the client.</span></span>  
  
 <span data-ttu-id="5cfe4-117">Die `Send`-Methode sendet eine Zeichenfolgenmeldung, die auf dem Client als Informationsmeldung ähnlich wie PRINT in [!INCLUDE[tsql](../../includes/tsql-md.md)] erscheint.</span><span class="sxs-lookup"><span data-stu-id="5cfe4-117">The `Send` method sends a string message that appears on the client as an information message, equivalent to PRINT in [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="5cfe4-118">Die Methode kann mit `SqlDataRecord` auch ein einzeiliges Resultset oder mit `SqlDataReader` ein mehrzeiliges Resultset senden.</span><span class="sxs-lookup"><span data-stu-id="5cfe4-118">It can also send a single-row result-set using `SqlDataRecord`, or a multi-row result-set using a `SqlDataReader`.</span></span>  
  
 <span data-ttu-id="5cfe4-119">Das `SqlPipe`-Objekt stellt außerdem eine `ExecuteAndSend`-Methode bereit.</span><span class="sxs-lookup"><span data-stu-id="5cfe4-119">The `SqlPipe` object also has an `ExecuteAndSend` method.</span></span> <span data-ttu-id="5cfe4-120">Mit dieser Methode kann ein Befehl (der als `SqlCommand`-Objekt übergeben wird) ausgeführt und Ergebnisse direkt zurück an den Aufrufer gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="5cfe4-120">This method can be used to execute a command (passed as a `SqlCommand` object) and send results directly back to the caller.</span></span> <span data-ttu-id="5cfe4-121">Wenn im übermittelten Befehl Fehler vorhanden sind, werden Ausnahmen an die Pipe gesendet. Es wird jedoch auch eine Kopie an den aufrufenden verwalteten Code gesendet.</span><span class="sxs-lookup"><span data-stu-id="5cfe4-121">If there are errors in the command that was submitted, exceptions are sent to the pipe, but a copy is also sent to calling managed code.</span></span> <span data-ttu-id="5cfe4-122">Wenn der aufrufende Code die Ausnahme nicht abfängt, wird sie in der Liste aufwärts weitergeleitet an den [!INCLUDE[tsql](../../includes/tsql-md.md)] -Code und dann zweimal in der Ausgabe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5cfe4-122">If the calling code does not catch the exception, it propagates up the stack to the [!INCLUDE[tsql](../../includes/tsql-md.md)] code and appears in the output twice.</span></span> <span data-ttu-id="5cfe4-123">Wenn der aufrufende Code die Ausnahme abfängt, wird dem Client der Fehler angezeigt, es gibt jedoch keinen doppelten Fehler.</span><span class="sxs-lookup"><span data-stu-id="5cfe4-123">If the calling code does catch the exception, the pipe consumer still sees the error, but there is not a duplicate error.</span></span>  
  
 <span data-ttu-id="5cfe4-124">Es kann nur ein `SqlCommand`-Befehl, der mit der kontextabhängigen Verbindung verknüpft ist, akzeptiert werden. Ein Befehl, der mit der nicht kontextabhängigen Verbindung verknüpft ist, kann nicht akzeptiert werden.</span><span class="sxs-lookup"><span data-stu-id="5cfe4-124">It can only take a `SqlCommand` that is associated with the context connection; it cannot take a command that is associated with the non-context connection.</span></span>  
  
## <a name="returning-custom-result-sets"></a><span data-ttu-id="5cfe4-125">Zurückgeben von benutzerdefinierten Resultsets</span><span class="sxs-lookup"><span data-stu-id="5cfe4-125">Returning Custom Result Sets</span></span>  
 <span data-ttu-id="5cfe4-126">Verwaltete gespeicherte Prozeduren können Resultsets senden, die nicht von einem `SqlDataReader` stammen.</span><span class="sxs-lookup"><span data-stu-id="5cfe4-126">Managed stored procedures can send result sets that do not come from a `SqlDataReader`.</span></span> <span data-ttu-id="5cfe4-127">Die `SendResultsStart`-Methode ermöglicht es gespeicherten Prozeduren zusammen mit `SendResultsRow` und `SendResultsEnd`, benutzerdefinierte Resultsets an den Client zu senden.</span><span class="sxs-lookup"><span data-stu-id="5cfe4-127">The `SendResultsStart` method, along with `SendResultsRow` and `SendResultsEnd`, allows stored procedures to send custom result sets to the client.</span></span>  
  
 <span data-ttu-id="5cfe4-128">`SendResultsStart` akzeptiert einen `SqlDataRecord` als Eingabe.</span><span class="sxs-lookup"><span data-stu-id="5cfe4-128">`SendResultsStart` takes a `SqlDataRecord` as an input.</span></span> <span data-ttu-id="5cfe4-129">Die Methode kennzeichnet den Anfang eines Resultsets und erstellt mithilfe der Datensatzmetadaten die Metadaten zur Beschreibung des Resultsets.</span><span class="sxs-lookup"><span data-stu-id="5cfe4-129">It marks the beginning of a result set and uses the record metadata to construct the metadata that describes the result set.</span></span> <span data-ttu-id="5cfe4-130">Der Wert des Datensatzes wird nicht mit `SendResultsStart` gesendet.</span><span class="sxs-lookup"><span data-stu-id="5cfe4-130">It does not send the value of the record with `SendResultsStart`.</span></span> <span data-ttu-id="5cfe4-131">Alle nachfolgenden Zeilen, die mit der `SendResultsRow`-Methode gesendet werden, müssen dieser Metadatendefinition entsprechen.</span><span class="sxs-lookup"><span data-stu-id="5cfe4-131">All the subsequent rows, sent using `SendResultsRow`, must match that metadata definition.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5cfe4-132">Nach dem Aufruf der `SendResultsStart`-Methode können nur `SendResultsRow` und `SendResultsEnd` aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="5cfe4-132">After calling the `SendResultsStart` method only `SendResultsRow` and `SendResultsEnd` can be called.</span></span> <span data-ttu-id="5cfe4-133">Ein Aufruf einer beliebigen anderen Methode in der gleichen Instanz von `SqlPipe` verursacht eine `InvalidOperationException`.</span><span class="sxs-lookup"><span data-stu-id="5cfe4-133">Calling any other method in the same instance of `SqlPipe` causes an `InvalidOperationException`.</span></span> <span data-ttu-id="5cfe4-134">`SendResultsEnd` setzt `SqlPipe` auf den Ausgangszustand zurück, in dem andere Methoden aufgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="5cfe4-134">`SendResultsEnd` sets `SqlPipe` back to the initial state in which other methods can be called.</span></span>  
  
### <a name="example"></a><span data-ttu-id="5cfe4-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5cfe4-135">Example</span></span>  
 <span data-ttu-id="5cfe4-136">Die gespeicherte `uspGetProductLine`-Prozedur gibt den Namen, die Produktnummer, die Farbe und den Listenpreis aller Produkte innerhalb einer bestimmten Produktlinie zurück.</span><span class="sxs-lookup"><span data-stu-id="5cfe4-136">The `uspGetProductLine` stored procedure returns the name, product number, color, and list price of all products within a specified product line.</span></span> <span data-ttu-id="5cfe4-137">Diese gespeicherte Prozedur nimmt genaue Übereinstimmungen für *prodLine*an.</span><span class="sxs-lookup"><span data-stu-id="5cfe4-137">This stored procedure accepts exact matches for *prodLine*.</span></span>  
  
 <span data-ttu-id="5cfe4-138">C#</span><span class="sxs-lookup"><span data-stu-id="5cfe4-138">C#</span></span>  
  
```  
using System;  
using System.Data;  
using System.Data.SqlClient;  
using System.Data.SqlTypes;  
using Microsoft.SqlServer.Server;  
  
public partial class StoredProcedures  
{  
[Microsoft.SqlServer.Server.SqlProcedure]  
public static void uspGetProductLine(SqlString prodLine)  
{  
    // Connect through the context connection.  
    using (SqlConnection connection = new SqlConnection("context connection=true"))  
    {  
        connection.Open();  
  
        SqlCommand command = new SqlCommand(  
            "SELECT Name, ProductNumber, Color, ListPrice " +  
            "FROM Production.Product " +   
            "WHERE ProductLine = @prodLine;", connection);  
  
        command.Parameters.AddWithValue("@prodLine", prodLine);  
  
        try  
        {  
            // Execute the command and send the results to the caller.  
            SqlContext.Pipe.ExecuteAndSend(command);  
        }  
        catch (System.Data.SqlClient.SqlException ex)  
        {  
            // An error occurred executing the SQL command.  
        }  
     }  
}  
};  
```  
  
 <span data-ttu-id="5cfe4-139">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5cfe4-139">Visual Basic</span></span>  
  
```  
Imports System  
Imports System.Data  
Imports System.Data.SqlClient  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
  
Partial Public Class StoredProcedures  
<Microsoft.SqlServer.Server.SqlProcedure()> _  
Public Shared Sub uspGetProductLine(ByVal prodLine As SqlString)  
    Dim command As SqlCommand  
  
    ' Connect through the context connection.  
    Using connection As New SqlConnection("context connection=true")  
        connection.Open()  
  
        command = New SqlCommand( _  
        "SELECT Name, ProductNumber, Color, ListPrice " & _  
        "FROM Production.Product " & _  
        "WHERE ProductLine = @prodLine;", connection)  
        command.Parameters.AddWithValue("@prodLine", prodLine)  
  
        Try  
            ' Execute the command and send the results   
            ' directly to the caller.  
            SqlContext.Pipe.ExecuteAndSend(command)  
        Catch ex As System.Data.SqlClient.SqlException  
            ' An error occurred executing the SQL command.  
        End Try  
    End Using  
End Sub  
End Class  
```  
  
 <span data-ttu-id="5cfe4-140">Die folgende [!INCLUDE[tsql](../../includes/tsql-md.md)]-Anweisung führt die `uspGetProduct`-Prozedur aus, die eine Liste mit Touringräderprodukten zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="5cfe4-140">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement executes the `uspGetProduct` procedure, which returns a list of touring bike products.</span></span>  
  
```  
EXEC uspGetProductLineVB 'T';  
```  
  
## <a name="see-also"></a><span data-ttu-id="5cfe4-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5cfe4-141">See Also</span></span>  
 <span data-ttu-id="5cfe4-142">[SqlDataRecord-Objekt](sqldatarecord-object.md) </span><span class="sxs-lookup"><span data-stu-id="5cfe4-142">[SqlDataRecord Object](sqldatarecord-object.md) </span></span>  
 <span data-ttu-id="5cfe4-143">[Gespeicherte CLR-Prozeduren](../../database-engine/dev-guide/clr-stored-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="5cfe4-143">[CLR Stored Procedures](../../database-engine/dev-guide/clr-stored-procedures.md) </span></span>  
 [<span data-ttu-id="5cfe4-144">Von SQL Server verwendete prozessinterne spezifische Erweiterungen für ADO.NET</span><span class="sxs-lookup"><span data-stu-id="5cfe4-144">SQL Server In-Process Specific Extensions to ADO.NET</span></span>](sql-server-in-process-specific-extensions-to-ado-net.md)  
  
  
