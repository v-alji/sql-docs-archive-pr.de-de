---
title: Zugreifen auf die aktuelle Transaktion | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- current transaction access
- Current property
- Transaction class
ms.assetid: 1a4e2ce5-f627-4c81-8960-6a9968cefda2
author: rothja
ms.author: jroth
ms.openlocfilehash: 34b7e67d30cb9d89a02eb918fcd03651b2915955
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725982"
---
# <a name="accessing-the-current-transaction"></a><span data-ttu-id="c4db3-102">Zugriff auf die aktuelle Transaktion</span><span class="sxs-lookup"><span data-stu-id="c4db3-102">Accessing the Current Transaction</span></span>
  <span data-ttu-id="c4db3-103">Wenn zu dem Zeitpunkt eine Transaktion aktiv ist, zu dem mit der Ausführung von in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] auszuführendem CLR-Code begonnen wird, dann wird die Transaktion durch die `System.Transactions.Transaction`-Klasse verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="c4db3-103">If a transaction is active at the point at which common language runtime (CLR) code running on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is entered, the transaction is exposed through the `System.Transactions.Transaction` class.</span></span> <span data-ttu-id="c4db3-104">Mit der `Transaction.Current`-Eigenschaft wird auf die aktuelle Transaktion zugegriffen.</span><span class="sxs-lookup"><span data-stu-id="c4db3-104">The `Transaction.Current` property is used to access the current transaction.</span></span> <span data-ttu-id="c4db3-105">In den meisten Fällen ist es nicht notwendig, explizit auf die Transaktion zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="c4db3-105">In most cases it is not necessary to access the transaction explicitly.</span></span> <span data-ttu-id="c4db3-106">Bei Datenbankverbindungen überprüft ADO.NET `Transaction.Current` automatisch beim Aufruf der `Connection.Open`-Methode, und trägt die Verbindung automatisch in diese Transaktion ein (sofern für das Schlüsselwort `Enlist` in der Verbindungszeichenfolge nicht false angegeben wurde).</span><span class="sxs-lookup"><span data-stu-id="c4db3-106">For database connections, ADO.NET checks `Transaction.Current` automatically when the `Connection.Open` method is called, and transparently enlists the connection in that transaction (unless the `Enlist` keyword is set to false in the connection string).</span></span>  
  
 <span data-ttu-id="c4db3-107">In den folgenden Szenarien sollten Sie das `Transaction`-Objekt direkt verwenden:</span><span class="sxs-lookup"><span data-stu-id="c4db3-107">You might want to use the `Transaction` object directly in the following scenarios:</span></span>  
  
-   <span data-ttu-id="c4db3-108">Wenn Sie eine Ressource eintragen möchten, die nicht automatisch eingetragen wird oder die aus irgendeinem Grund während der Initialisierung nicht eingetragen wurde.</span><span class="sxs-lookup"><span data-stu-id="c4db3-108">If you want to enlist a resource that does not do automatic enlistment, or that for some reason was not enlisted during initialization.</span></span>  
  
-   <span data-ttu-id="c4db3-109">Wenn Sie eine Ressource explizit in die Transaktion eintragen möchten.</span><span class="sxs-lookup"><span data-stu-id="c4db3-109">If you want to explicitly enlist a resource in the transaction.</span></span>  
  
-   <span data-ttu-id="c4db3-110">Wenn Sie die externe Transaktion aus einer gespeicherten Prozedur oder Funktion heraus beenden möchten.</span><span class="sxs-lookup"><span data-stu-id="c4db3-110">If you want to terminate the external transaction from within your stored procedure or function.</span></span> <span data-ttu-id="c4db3-111">In diesem Fall verwenden Sie <xref:System.Transactions.TransactionScope>.</span><span class="sxs-lookup"><span data-stu-id="c4db3-111">In this case, you use <xref:System.Transactions.TransactionScope>.</span></span> <span data-ttu-id="c4db3-112">Beispielsweise wird mit dem folgenden Code die aktuelle Transaktion rückgängig gemacht.</span><span class="sxs-lookup"><span data-stu-id="c4db3-112">For example, the following code will rollback the current transaction:</span></span>  
  
    ```  
    using(TransactionScope transactionScope = new TransactionScope(TransactionScopeOptions.Required)) { }  
    ```  
  
 <span data-ttu-id="c4db3-113">Im weiteren Verlauf dieses Themas werden andere Möglichkeiten beschrieben, eine externe Transaktion abzubrechen.</span><span class="sxs-lookup"><span data-stu-id="c4db3-113">The rest of this topic describes other ways to cancel an external transaction.</span></span>  
  
## <a name="canceling-an-external-transaction"></a><span data-ttu-id="c4db3-114">Abbrechen einer externen Transaktion</span><span class="sxs-lookup"><span data-stu-id="c4db3-114">Canceling an External Transaction</span></span>  
 <span data-ttu-id="c4db3-115">Sie können externe Transaktionen wie folgt von einer verwalteten Prozedur oder einer Funktion aus abbrechen:</span><span class="sxs-lookup"><span data-stu-id="c4db3-115">You can cancel external transactions from a managed procedure or function in the following ways:</span></span>  
  
-   <span data-ttu-id="c4db3-116">Die verwaltete Prozedur oder die Funktion kann in einem Ausgabeparameter einen Wert zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="c4db3-116">The managed procedure or function can return a value by using an output parameter.</span></span> <span data-ttu-id="c4db3-117">Die aufrufende [!INCLUDE[tsql](../../includes/tsql-md.md)]-Prozedur kann den zurückgegebenen Wert überprüfen und gegebenenfalls `ROLLBACK TRANSACTION` ausführen.</span><span class="sxs-lookup"><span data-stu-id="c4db3-117">The calling [!INCLUDE[tsql](../../includes/tsql-md.md)] procedure can check the returned value and, if appropriate, execute `ROLLBACK TRANSACTION`.</span></span>  
  
-   <span data-ttu-id="c4db3-118">Die verwaltete Prozedur oder die Funktion kann eine benutzerdefinierte Ausnahme auslösen.</span><span class="sxs-lookup"><span data-stu-id="c4db3-118">The managed procedure or function can throw a custom exception.</span></span> <span data-ttu-id="c4db3-119">Die aufrufenden [!INCLUDE[tsql](../../includes/tsql-md.md)] Prozedur kann die Ausnahme abfangen, die von der verwalteten Prozedur oder Funktion in einem try/catch-Block ausgelöst und ausgeführt wird `ROLLBACK TRANSACTION` .</span><span class="sxs-lookup"><span data-stu-id="c4db3-119">The calling [!INCLUDE[tsql](../../includes/tsql-md.md)] procedure can catch the exception thrown by the managed procedure or function in a try/catch block and execute `ROLLBACK TRANSACTION`.</span></span>  
  
-   <span data-ttu-id="c4db3-120">Die verwaltete Prozedur oder die Funktion kann die aktuelle Transaktion durch einen Aufruf der `Transaction.Rollback`-Methode abbrechen, wenn eine bestimmte Bedingung erfüllt wird.</span><span class="sxs-lookup"><span data-stu-id="c4db3-120">The managed procedure or function can cancel the current transaction by calling the `Transaction.Rollback` method if a certain condition is met.</span></span>  
  
 <span data-ttu-id="c4db3-121">Beim Aufruf innerhalb einer verwalteten Prozedur oder Funktion löst die `Transaction.Rollback`-Methode eine Ausnahme mit einer nicht eindeutigen Fehlermeldung aus und kann in einen try/catch-Block eingebunden werden.</span><span class="sxs-lookup"><span data-stu-id="c4db3-121">When it is called within a managed procedure or function, the `Transaction.Rollback` method throws an exception with an ambiguous error message and can be wrapped in a try/catch block.</span></span> <span data-ttu-id="c4db3-122">Die Fehlermeldung lautet wie folgt oder ähnlich:</span><span class="sxs-lookup"><span data-stu-id="c4db3-122">The error message thresembles similar to the following:</span></span>  
  
```  
Msg 3994, Level 16, State 1, Procedure uspRollbackFromProc, Line 0  
Transaction is not allowed to roll back inside a user defined routine, trigger or aggregate because the transaction is not started in that CLR level. Change application logic to enforce strict transaction nesting.  
```  
  
 <span data-ttu-id="c4db3-123">Diese Ausnahme wird erwartet und der try/catch-Block ist notwendig, damit die Codeausführung fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="c4db3-123">This exception is expected and the try/catch block is necessary for code execution to continue.</span></span> <span data-ttu-id="c4db3-124">Wenn kein try/catch-Block vorhanden ist, wird die Ausnahme sofort der aufrufenden [!INCLUDE[tsql](../../includes/tsql-md.md)] -Prozedur übergeben und der verwaltete Code wird zu Ende ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c4db3-124">Without the try/catch block, the exception will be immediately thrown to the calling [!INCLUDE[tsql](../../includes/tsql-md.md)] procedure and managed code execution will finish.</span></span> <span data-ttu-id="c4db3-125">Wenn die Ausführung des verwalteten Codes beendet ist, wird eine andere Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="c4db3-125">When the managed code finishes execution, another exception is raised:</span></span>  
  
```  
Msg 3991, Level 16, State 1, Procedure uspRollbackFromProc, Line 1   
The context transaction which was active before entering user defined routine, trigger or aggregate " uspRollbackFromProc " has been ended inside of it, which is not allowed. Change application logic to enforce strict transaction nesting. The statement has been terminated.  
```  
  
 <span data-ttu-id="c4db3-126">Diese Ausnahme ist ebenfalls zu erwarten, und die [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung, welche die den Trigger auslösenden Aktion ausführt, muss in einen try/catch-Block eingeschlossen werden, damit die Ausführung fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="c4db3-126">This exception is also expected, and for execution to continue, you must have a try/catch block around the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement that performs the action that fires the trigger.</span></span> <span data-ttu-id="c4db3-127">Trotz der zwei ausgelösten Ausnahmen wird ein Rollback für die Transaktion ausgeführt, und für die Änderungen in der Tabelle wird kein Commit ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c4db3-127">Despite the two exceptions thrown, the transaction is rolled back and the changes are not committed.</span></span>  
  
### <a name="example"></a><span data-ttu-id="c4db3-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c4db3-128">Example</span></span>  
 <span data-ttu-id="c4db3-129">Im folgenden Beispiel wird von der verwalteten Prozedur für eine Transaktion mit der `Transaction.Rollback`-Methode ein Rollback für die Transaktion ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c4db3-129">The following is an example of a transaction being rolled back from a managed procedure by using the `Transaction.Rollback` method.</span></span> <span data-ttu-id="c4db3-130">Beachten Sie den try/catch-Block um die `Transaction.Rollback`-Methode im verwalteten Code.</span><span class="sxs-lookup"><span data-stu-id="c4db3-130">Notice the try/catch block around the `Transaction.Rollback` method in the managed code.</span></span> <span data-ttu-id="c4db3-131">Das [!INCLUDE[tsql](../../includes/tsql-md.md)] -Skript erstellt eine Assembly und eine verwaltete gespeicherte Prozedur.</span><span class="sxs-lookup"><span data-stu-id="c4db3-131">The [!INCLUDE[tsql](../../includes/tsql-md.md)] script creates an assembly and managed stored procedure.</span></span> <span data-ttu-id="c4db3-132">Beachten Sie, dass die- `EXEC uspRollbackFromProc` Anweisung in einen try/catch-Block umgerückt ist, sodass die Ausnahme abgefangen wird, wenn die Ausführung der verwalteten Prozedur beendet wird.</span><span class="sxs-lookup"><span data-stu-id="c4db3-132">Be aware that the `EXEC uspRollbackFromProc` statement is wrapped in a try/catch block, so that the exception thrown when the managed procedure completes execution is caught.</span></span>  
  
```csharp  
using System;  
using System.Data;  
using System.Data.SqlClient;  
using System.Data.SqlTypes;  
using Microsoft.SqlServer.Server;  
using System.Transactions;  
  
public partial class StoredProcedures  
{  
[Microsoft.SqlServer.Server.SqlProcedure]  
public static void uspRollbackFromProc()  
{  
   using (SqlConnection connection = new SqlConnection(@"context connection=true"))  
   {  
      // Open the connection.  
      connection.Open();  
  
      bool successCondition = true;  
  
      // Success condition is met.  
      if (successCondition)  
      {  
         SqlContext.Pipe.Send("Success condition met in procedure.");   
         // Perform other actions here.  
      }  
  
      //  Success condition is not met, the transaction will be rolled back.  
      else  
      {  
         SqlContext.Pipe.Send("Success condition not met in managed procedure. Transaction rolling back...");  
         try  
         {  
               // Get the current transaction and roll it back.  
               Transaction trans = Transaction.Current;  
               trans.Rollback();  
         }  
         catch (SqlException ex)  
         {  
            // Catch the expected exception.   
            // This allows the connection to close correctly.                      
         }    
      }  
  
      // Close the connection.  
      connection.Close();  
   }  
}  
};  
```  
  
```vb  
Imports System  
Imports System.Data  
Imports System.Data.SqlClient  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Transactions  
  
Partial Public Class StoredProcedures  
<Microsoft.SqlServer.Server.SqlProcedure()> _  
Public Shared Sub  uspRollbackFromProc ()  
   Using connection As New SqlConnection("context connection=true")  
  
   ' Open the connection.  
   connection.Open()  
  
   Dim successCondition As Boolean  
   successCondition = False  
  
   ' Success condition is met.  
   If successCondition Then  
  
      SqlContext.Pipe.Send("Success condition met in procedure.")  
  
      ' Success condition is not met, the transaction will be rolled back.  
  
   Else  
      SqlContext.Pipe.Send("Success condition not met in managed procedure. Transaction rolling back...")  
      Try  
         ' Get the current transaction and roll it back.  
         Dim trans As Transaction  
         trans = Transaction.Current  
         trans.Rollback()  
  
      Catch ex As SqlException  
         ' Catch the exception instead of throwing it.    
         ' This allows the connection to close correctly.                      
      End Try  
  
   End If  
  
   ' Close the connection.  
   connection.Close()  
  
End Using  
End Sub  
End Class  
```  
  
 <span data-ttu-id="c4db3-133">**Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="c4db3-133">**Transact-SQL**</span></span>  
  
```  
--Register assembly.  
CREATE ASSEMBLY TestProcs FROM 'C:\Programming\TestProcs.dll'   
Go  
CREATE PROCEDURE uspRollbackFromProc AS EXTERNAL NAME TestProcs.StoredProcedures.uspRollbackFromProc  
Go  
  
-- Execute procedure.  
BEGIN TRY  
BEGIN TRANSACTION   
-- Perform other actions.  
Exec uspRollbackFromProc  
-- Perform other actions.  
PRINT N'Commiting transaction...'  
COMMIT TRANSACTION  
END TRY  
  
BEGIN CATCH  
SELECT ERROR_NUMBER() AS ErrorNum, ERROR_MESSAGE() AS ErrorMessage  
PRINT N'Exception thrown, rolling back transaction.'  
ROLLBACK TRANSACTION  
PRINT N'Transaction rolled back.'   
END CATCH  
Go  
  
-- Clean up.  
DROP Procedure uspRollbackFromProc;  
Go  
DROP ASSEMBLY TestProcs;  
Go  
```  
  
## <a name="see-also"></a><span data-ttu-id="c4db3-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c4db3-134">See Also</span></span>  
 [<span data-ttu-id="c4db3-135">CLR-Integration und Transaktionen</span><span class="sxs-lookup"><span data-stu-id="c4db3-135">CLR Integration and Transactions</span></span>](../native-client-ole-db-transactions/transactions.md)  
  
  
