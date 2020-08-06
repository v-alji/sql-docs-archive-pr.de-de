---
title: Verwenden von System. Transactions | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- TransactionScope class
- Dispose method
- System.Transactions namespace
ms.assetid: 79656ce5-ce46-4c5e-9540-cf9869bd774b
author: rothja
ms.author: jroth
ms.openlocfilehash: 277edd75ea0437dc532ed5672e3c7b8a0569af8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725965"
---
# <a name="using-systemtransactions"></a><span data-ttu-id="aa3d8-102">Verwenden von 'System.Transactions'</span><span class="sxs-lookup"><span data-stu-id="aa3d8-102">Using System.Transactions</span></span>
  <span data-ttu-id="aa3d8-103">Durch den `System.Transactions`-Namespace wird ein neues Transaktionsframework bereitgestellt, das voll in ADO.NET und [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CLR (Common Language Runtime) integriert ist.</span><span class="sxs-lookup"><span data-stu-id="aa3d8-103">The `System.Transactions` namespace provides a transaction framework that is fully integrated with ADO.NET and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] common language runtime (CLR) integration.</span></span> <span data-ttu-id="aa3d8-104">Die `System.Transactions.TransactionScope`-Klasse bewirkt, dass ein Codeblock transaktional wird, indem sie Verbindungen implizit in einer verteilten Transaktion einträgt.</span><span class="sxs-lookup"><span data-stu-id="aa3d8-104">The `System.Transactions.TransactionScope` class makes a code block transactional by implicitly enlisting connections in a distributed transaction.</span></span> <span data-ttu-id="aa3d8-105">Sie müssen am Ende des Codeblocks, der durch `Complete` markiert wird, die `TransactionScope`-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="aa3d8-105">You must call the `Complete` method at the end of the code block marked by the `TransactionScope`.</span></span> <span data-ttu-id="aa3d8-106">Die `Dispose`-Methode wird aufgerufen, wenn die Programmausführung einen Codeblock verlässt, was dazu führt, dass die Transaktion nicht fortgeführt wird, wenn die `Complete`-Methode nicht aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="aa3d8-106">The `Dispose` method is invoked when program execution leaves a code block, causing the transaction to be discontinued if the `Complete` method is not called.</span></span> <span data-ttu-id="aa3d8-107">Wenn eine Ausnahme ausgelöst wurde, die dazu führt, dass der Code den Bereich verlässt, wird die Transaktion als nicht fortgeführt betrachtet.</span><span class="sxs-lookup"><span data-stu-id="aa3d8-107">If an exception has been thrown that causes the code to leave scope, the transaction is considered to be discontinued.</span></span>  
  
 <span data-ttu-id="aa3d8-108">Wir empfehlen die Verwendung eines `using`-Blocks um sicherzustellen, dass die `Dispose`-Methode für das `TransactionScope`-Objekt aufgerufen wird, wenn der `using`-Block verlassen wird.</span><span class="sxs-lookup"><span data-stu-id="aa3d8-108">We recommend that you employ a `using` block to ensure that the `Dispose` method is called on the `TransactionScope` object when the `using` block is exited.</span></span> <span data-ttu-id="aa3d8-109">Wird für ausstehende Transaktionen kein Commit oder Rollback ausgeführt, wird die Leistung unter Umständen stark beeinträchtigt, da der Timeout für `TransactionScope` standardmäßig eine Minute beträgt.</span><span class="sxs-lookup"><span data-stu-id="aa3d8-109">Failure to commit or roll back pending transactions can seriously degrade performance because the default time-out for the `TransactionScope` is one minute.</span></span> <span data-ttu-id="aa3d8-110">Wenn Sie keine `using`-Anweisung verwenden, müssen Sie alle Arbeiten in einem `Try`-Block ausführen und die `Dispose`-Methode im `Finally`-Block explizit aufrufen.</span><span class="sxs-lookup"><span data-stu-id="aa3d8-110">If you do not use a `using` statement, you must perform all work in a `Try` block and explicitly call the `Dispose` method in the `Finally` block.</span></span>  
  
 <span data-ttu-id="aa3d8-111">Wenn innerhalb von `TransactionScope` eine Ausnahme auftritt, wird die Transaktion als inkonsistent markiert und aufgegeben.</span><span class="sxs-lookup"><span data-stu-id="aa3d8-111">If an exception occurs within the `TransactionScope`, the transaction is marked as inconsistent and is abandoned.</span></span> <span data-ttu-id="aa3d8-112">Es wird ein Rollback für die Transaktion ausgeführt, wenn `TransactionScope` verworfen wird.</span><span class="sxs-lookup"><span data-stu-id="aa3d8-112">It is rolled back when the `TransactionScope` is disposed.</span></span> <span data-ttu-id="aa3d8-113">Wenn keine Ausnahme auftritt, wird für teilnehmende Transaktionen ein Commit ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="aa3d8-113">If no exception occurs, participating transactions commit.</span></span>  
  
 <span data-ttu-id="aa3d8-114">`TransactionScope` sollte nur verwendet werden, wenn auf lokale Datenquellen und Remotedatenquellen oder externe Ressourcen-Manager zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="aa3d8-114">`TransactionScope` should be used only when local and remote data sources or external resource managers are being accessed.</span></span> <span data-ttu-id="aa3d8-115">Der Grund dafür ist, dass die `TransactionScope`-Klasse immer zur Höherstufung von Transaktionen führt, selbst dann, wenn sie nur innerhalb einer Kontextverbindung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="aa3d8-115">This is because `TransactionScope` always causes transactions to promote, even if it is being used only within a context connection.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="aa3d8-116">Die `TransactionScope`-Klasse erstellt `System.Transactions.Transaction.IsolationLevel` standardmäßig mit dem Wert `Serializable`.</span><span class="sxs-lookup"><span data-stu-id="aa3d8-116">The `TransactionScope` class creates a transaction with a `System.Transactions.Transaction.IsolationLevel` of `Serializable` by default.</span></span> <span data-ttu-id="aa3d8-117">Je nach Ihrer Anwendung kann es vorteilhaft sein, die Isolationsstufe herabzusetzen, um ein hohes Konfliktpotenzial in der Anwendung zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="aa3d8-117">Depending on your application, you might want to consider lowering the isolation level to avoid high contention in your application.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="aa3d8-118">Es empfiehlt sich, nur Updates, Einfügungen und Löschungen innerhalb verteilter Transaktionen für Remoteserver auszuführen, da sie erhebliche Datenbankressourcen in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="aa3d8-118">We recommend that you perform only updates, inserts, and deletes within distributed transactions against remote servers because they consume significant database resources.</span></span> <span data-ttu-id="aa3d8-119">Wenn der Vorgang auf dem lokalen Server ausgeführt werden soll, ist keine verteilte Transaktion notwendig, sondern es reicht eine lokale Transaktion aus.</span><span class="sxs-lookup"><span data-stu-id="aa3d8-119">If the operation is going to be performed on the local server, a distributed transaction is not necessary and a local transaction will suffice.</span></span> <span data-ttu-id="aa3d8-120">SELECT-Anweisungen sperren unter Umständen Datenbankressourcen, ohne dass dies erforderlich ist. Und in einigen Szenarien ist die Verwendung von Auswahlen möglicherweise notwendig.</span><span class="sxs-lookup"><span data-stu-id="aa3d8-120">SELECT statements may lock database resources unnecessarily, and in some scenarios it may be necessary to use transactions for selects.</span></span> <span data-ttu-id="aa3d8-121">Jeder Arbeitsschritt, der nicht die Datenbank betrifft, sollte außerhalb des Transaktionsbereichs durchgeführt werden, sofern keine anderen Ressourcen-Manager von der Transaktion betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="aa3d8-121">Any non-database work should be done outside of the scope of the transaction, unless it involves other transacted resource managers.</span></span> <span data-ttu-id="aa3d8-122">Wenngleich eine Ausnahme innerhalb des Transaktionsbereichs ein Transaktionscommit verhindert, verfügt die `TransactionScope`-Klasse nicht über die Möglichkeit, außerhalb des Bereichs der Transaktion selbst ein Rollback von Änderungen auszuführen, die Ihr Code vorgenommen hat.</span><span class="sxs-lookup"><span data-stu-id="aa3d8-122">Although an exception within the scope of the transaction prevents the transaction from committing, the `TransactionScope` class has no provision for rolling back any changes your code has made outside of the scope of the transaction itself.</span></span> <span data-ttu-id="aa3d8-123">Wenn Sie bestimmte Vorgänge beim Rollback der Transaktion ausführen möchten, müssen Sie eine eigene Implementierung der `System.Transactions.IEnlistmentNotification`-Schnittstelle schreiben und eine explizite Eintragung in die Transaktion vornehmen.</span><span class="sxs-lookup"><span data-stu-id="aa3d8-123">If you need to take some action when the transaction is rolled back, you must write your own implementation of the `System.Transactions.IEnlistmentNotification` interface, and explicitly enlist in the transaction.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aa3d8-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="aa3d8-124">Example</span></span>  
 <span data-ttu-id="aa3d8-125">Um mit `System.Transactions` zu arbeiten, müssen Sie über einen Verweis auf die Datei System.Transactions.dll verfügen.</span><span class="sxs-lookup"><span data-stu-id="aa3d8-125">To work with `System.Transactions`, you must have a reference to the System.Transactions.dll file.</span></span>  
  
 <span data-ttu-id="aa3d8-126">Der nachfolgende Code zeigt, wie eine Transaktion erstellt wird, die für zwei verschiedene Instanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]heraufgestuft werden kann.</span><span class="sxs-lookup"><span data-stu-id="aa3d8-126">The following code demonstrates how to create a transaction that can be promoted against two different instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="aa3d8-127">Diese Instanzen werden durch zwei verschiedene `System.Data.SqlClient.SqlConnection`-Objekte dargestellt, die von einem `TransactionScope`-Block umschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="aa3d8-127">These instances are represented by two different `System.Data.SqlClient.SqlConnection` objects, which are wrapped in a `TransactionScope` block.</span></span> <span data-ttu-id="aa3d8-128">Der Code erstellt den `TransactionScope`-Block mit einer `using`-Anweisung und öffnet die erste Verbindung, wodurch sie automatisch im `TransactionScope` eingetragen wird.</span><span class="sxs-lookup"><span data-stu-id="aa3d8-128">The code creates the `TransactionScope` block with a `using` statement, and opens the first connection, which automatically enlists it in the `TransactionScope`.</span></span> <span data-ttu-id="aa3d8-129">Die Transaktion wird anfänglich als einfache Transaktion, nicht als vollständig verteilte Transaktion, eingetragen.</span><span class="sxs-lookup"><span data-stu-id="aa3d8-129">The transaction is initially enlisted as a lightweight transaction, not a full distributed transaction.</span></span> <span data-ttu-id="aa3d8-130">Der Code geht von der Existenz bedingter Logik aus (welche der Kürze halber weggelassen wurde).</span><span class="sxs-lookup"><span data-stu-id="aa3d8-130">The code assumes the existence of conditional logic (which has been omitted for brevity).</span></span> <span data-ttu-id="aa3d8-131">Er öffnet die zweite Verbindung nur, wenn es nötig ist, und trägt sie dann im `TransactionScope` ein.</span><span class="sxs-lookup"><span data-stu-id="aa3d8-131">It opens the second connection only if it is needed, enlisting it in the `TransactionScope`.</span></span> <span data-ttu-id="aa3d8-132">Wenn die Verbindung geöffnet wird, wird die Transaktion automatisch auf eine vollständig verteilte Transaktion hochgestuft.</span><span class="sxs-lookup"><span data-stu-id="aa3d8-132">When the connection is opened, the transaction is automatically promoted to a full distributed transaction.</span></span> <span data-ttu-id="aa3d8-133">Der Code ruft dann `TransactionScope.Complete` auf, was zur Ausführung eines Commits für die Transaktion führt.</span><span class="sxs-lookup"><span data-stu-id="aa3d8-133">The code then invokes `TransactionScope.Complete`, which commits the transaction.</span></span> <span data-ttu-id="aa3d8-134">Der Code gibt die beiden Verbindungen beim Beenden der `using`-Anweisungen für die Verbindungen frei.</span><span class="sxs-lookup"><span data-stu-id="aa3d8-134">The code disposes of the two connections when exiting the `using` statements for the connections.</span></span> <span data-ttu-id="aa3d8-135">Die `TransactionScope.Dispose`-Methode für `TransactionScope` wird am Ende des `using`-Blocks für `TransactionScope` automatisch aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="aa3d8-135">The `TransactionScope.Dispose` method for the `TransactionScope` is automatically called at the termination of the `using` block for the `TransactionScope`.</span></span> <span data-ttu-id="aa3d8-136">Wenn an einem Punkt im `TransactionScope`-Block eine Ausnahme aufgetreten ist, wird `Complete` nicht aufgerufen, und für die verteilte Transaktion wird ein Rollback ausgeführt, sobald der `TransactionScope` gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="aa3d8-136">If an exception has been thrown at any point in the `TransactionScope` block, `Complete` does not get called, and the distributed transaction will roll back when the `TransactionScope` is disposed.</span></span>  
  
 <span data-ttu-id="aa3d8-137">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="aa3d8-137">Visual Basic</span></span>  
  
```  
Using transScope As New TransactionScope()  
    Using connection1 As New SqlConnection(connectString1)  
        ' Opening connection1 automatically enlists it in the   
        ' TransactionScope as a lightweight transaction.  
        connection1.Open()  
  
        ' Do work in the first connection.  
  
        ' Assumes conditional logic in place where the second  
        ' connection will only be opened as needed.  
        Using connection2 As New SqlConnection(connectString2)  
            ' Open the second connection, which enlists the   
            ' second connection and promotes the transaction to  
            ' a full distributed transaction.  
            connection2.Open()  
  
            ' Do work in the second connection.  
  
        End Using  
    End Using  
  
    ' Commit the transaction.  
    transScope.Complete()  
End Using  
```  
  
 <span data-ttu-id="aa3d8-138">C#</span><span class="sxs-lookup"><span data-stu-id="aa3d8-138">C#</span></span>  
  
```  
using (TransactionScope transScope = new TransactionScope())  
{  
    using (SqlConnection connection1 = new   
       SqlConnection(connectString1))  
    {  
        // Opening connection1 automatically enlists it in the   
        // TransactionScope as a lightweight transaction.  
        connection1.Open();  
  
        // Do work in the first connection.  
  
        // Assumes conditional logic in place where the second  
        // connection will only be opened as needed.  
        using (SqlConnection connection2 = new   
            SqlConnection(connectString2))  
        {  
            // Open the second connection, which enlists the   
            // second connection and promotes the transaction to  
            // a full distributed transaction.   
            connection2.Open();  
  
            // Do work in the second connection.  
        }  
    }  
    //  The Complete method commits the transaction.  
    transScope.Complete();  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="aa3d8-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="aa3d8-139">See Also</span></span>  
 [<span data-ttu-id="aa3d8-140">CLR-Integration und Transaktionen</span><span class="sxs-lookup"><span data-stu-id="aa3d8-140">CLR Integration and Transactions</span></span>](../native-client-ole-db-transactions/transactions.md)  
  
  
