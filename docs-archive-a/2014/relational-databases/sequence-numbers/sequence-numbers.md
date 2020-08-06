---
title: Sequenznummern | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- sequence number object, overview
- sequence [Database Engine]
- autonumbers, sequences
- sequence numbers [SQL Server]
- sequence number object
ms.assetid: c900e30d-2fd3-4d5f-98ee-7832f37e79d1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6c65b4df915a85cf0ec7c7c0c8c0ff9f6607ad96
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725366"
---
# <a name="sequence-numbers"></a><span data-ttu-id="3d53c-102">Sequenznummern</span><span class="sxs-lookup"><span data-stu-id="3d53c-102">Sequence Numbers</span></span>
  <span data-ttu-id="3d53c-103">Als Sequenz wird ein benutzerdefiniertes schemagebundenes Objekt bezeichnet, das eine Sequenz numerischer Werte anhand der Spezifikation generiert, mit der die Sequenz erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="3d53c-103">A sequence is a user-defined schema-bound object that generates a sequence of numeric values according to the specification with which the sequence was created.</span></span> <span data-ttu-id="3d53c-104">Die Sequenz von numerischen Werten wird in aufsteigender oder absteigender Reihenfolge in einem definierten Intervall generiert, und je nach Anforderung wird ein Zyklus (Wiederholungen) ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="3d53c-104">The sequence of numeric values is generated in an ascending or descending order at a defined interval and may cycle (repeat) as requested.</span></span> <span data-ttu-id="3d53c-105">Sequenzen werden anders als Identitätsspalten keinen Tabellen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="3d53c-105">Sequences, unlike identity columns, are not associated with tables.</span></span> <span data-ttu-id="3d53c-106">Eine Anwendung verweist auf ein Sequenzobjekt, um den nächsten Wert zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="3d53c-106">An application refers to a sequence object to receive its next value.</span></span> <span data-ttu-id="3d53c-107">Die Beziehung zwischen Sequenzen und Tabellen wird von der Anwendung gesteuert.</span><span class="sxs-lookup"><span data-stu-id="3d53c-107">The relationship between sequences and tables is controlled by the application.</span></span> <span data-ttu-id="3d53c-108">Benutzeranwendungen können auf ein Sequenzobjekt verweisen und die Werteschlüssel in mehreren Zeilen und Tabellen koordinieren.</span><span class="sxs-lookup"><span data-stu-id="3d53c-108">User applications can reference a sequence object and coordinate the values keys across multiple rows and tables.</span></span>  
  
 <span data-ttu-id="3d53c-109">Eine Sequenz wird unabhängig von den Tabellen mithilfe der **CREATE SEQUENCE** -Anweisung erstellt.</span><span class="sxs-lookup"><span data-stu-id="3d53c-109">A sequence is created independently of the tables by using the **CREATE SEQUENCE** statement.</span></span> <span data-ttu-id="3d53c-110">Mithilfe von Optionen können Sie das Inkrement, Maximal- und Minimalwerte, den Anfangspunkt, die automatische Neustartfunktion sowie das Zwischenspeichern konfigurieren, um die Leistung zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="3d53c-110">Options enable you to control the increment, maximum and minimum values, starting point, automatic restarting capability, and caching to improve performance.</span></span> <span data-ttu-id="3d53c-111">Weitere Informationen zu den Optionen finden Sie unter [CREATE SEQUENCE](/sql/t-sql/statements/create-sequence-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3d53c-111">For information about the options, see [CREATE SEQUENCE](/sql/t-sql/statements/create-sequence-transact-sql).</span></span>  
  
 <span data-ttu-id="3d53c-112">Im Unterschied zu Identitätsspaltenwerten, die beim Einfügen von Zeilen generiert werden, kann eine Anwendung durch Aufrufen der [NEXT VALUE FOR](/sql/t-sql/functions/next-value-for-transact-sql) -Funktion die nächste Sequenznummer abrufen, bevor die Zeile eingefügt wird.</span><span class="sxs-lookup"><span data-stu-id="3d53c-112">Unlike identity column values, which are generated when rows are inserted, an application can obtain the next sequence number before inserting the row by calling the [NEXT VALUE FOR](/sql/t-sql/functions/next-value-for-transact-sql) function.</span></span> <span data-ttu-id="3d53c-113">Die Sequenznummer wird beim Aufruf von NEXT VALUE FOR zugeordnet, selbst wenn die Nummer nie in eine Tabelle eingefügt wird.</span><span class="sxs-lookup"><span data-stu-id="3d53c-113">The sequence number is allocated when NEXT VALUE FOR is called even if the number is never inserted into a table.</span></span> <span data-ttu-id="3d53c-114">Die NEXT VALUE FOR-Funktion kann als Standardwert für eine Spalte in einer Tabellendefinition verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3d53c-114">The NEXT VALUE FOR function can be used as the default value for a column in a table definition.</span></span> <span data-ttu-id="3d53c-115">Mit [sp_sequence_get_range](/sql/relational-databases/system-stored-procedures/sp-sequence-get-range-transact-sql) können Sie einen Bereich von mehreren Sequenznummern gleichzeitig abrufen.</span><span class="sxs-lookup"><span data-stu-id="3d53c-115">Use [sp_sequence_get_range](/sql/relational-databases/system-stored-procedures/sp-sequence-get-range-transact-sql) to get a range of multiple sequence numbers at once.</span></span>  
  
 <span data-ttu-id="3d53c-116">Eine Sequenz kann als beliebiger ganzzahliger Datentyp definiert werden.</span><span class="sxs-lookup"><span data-stu-id="3d53c-116">A sequence can be defined as any integer data type.</span></span> <span data-ttu-id="3d53c-117">Wenn kein Datentyp nicht angegeben ist, wird eine Sequenz standardmäßig auf `bigint` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="3d53c-117">If the data type is not specified, a sequence defaults to `bigint`.</span></span>  
  
## <a name="using-sequences"></a><span data-ttu-id="3d53c-118">Verwenden von Sequenzen</span><span class="sxs-lookup"><span data-stu-id="3d53c-118">Using Sequences</span></span>  
 <span data-ttu-id="3d53c-119">Verwenden Sie in den folgenden Szenarios Sequenzen anstelle der Identitätsspalten:</span><span class="sxs-lookup"><span data-stu-id="3d53c-119">Use sequences instead of identity columns in the following scenarios:</span></span>  
  
-   <span data-ttu-id="3d53c-120">Die Anwendung fordert eine Nummer an, bevor die Einfügung in die Tabelle ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3d53c-120">The application requires a number before the insert into the table is made.</span></span>  
  
-   <span data-ttu-id="3d53c-121">Die Anwendung erfordert das Freigeben einer einzelnen Reihe von Nummern zwischen mehreren Tabellen oder mehreren Spalten innerhalb einer Tabelle.</span><span class="sxs-lookup"><span data-stu-id="3d53c-121">The application requires sharing a single series of numbers between multiple tables or multiple columns within a table.</span></span>  
  
-   <span data-ttu-id="3d53c-122">Die Anwendung muss die Nummernreihe neu starten, wenn eine angegebene Nummer erreicht wurde.</span><span class="sxs-lookup"><span data-stu-id="3d53c-122">The application must restart the number series when a specified number is reached.</span></span> <span data-ttu-id="3d53c-123">Beispiel: Nachdem die Werte 1 bis 10 zugewiesen wurden, beginnt die Anwendung erneut mit dem Zuweisen der Werte 1 bis 10.</span><span class="sxs-lookup"><span data-stu-id="3d53c-123">For example, after assigning values 1 through 10, the application starts assigning values 1 through 10 again.</span></span>  
  
-   <span data-ttu-id="3d53c-124">Die Anwendung erfordert, dass Sequenzwerte nach einem weiteren Feld sortiert werden.</span><span class="sxs-lookup"><span data-stu-id="3d53c-124">The application requires sequence values to be sorted by another field.</span></span> <span data-ttu-id="3d53c-125">Die NEXT VALUE FOR-Funktion kann die OVER-Klausel auf den Funktionsaufruf anwenden.</span><span class="sxs-lookup"><span data-stu-id="3d53c-125">The NEXT VALUE FOR function can apply the OVER clause to the function call.</span></span> <span data-ttu-id="3d53c-126">Die OVER-Klausel garantiert, dass die zurückgegebenen Werte in der Reihenfolge der ORDER BY-Klausel der OVER-Klausel generiert werden.</span><span class="sxs-lookup"><span data-stu-id="3d53c-126">The OVER clause guarantees that the values returned are generated in the order of the OVER clause's ORDER BY clause.</span></span>  
  
-   <span data-ttu-id="3d53c-127">Eine Anwendung erfordert, dass mehrere Nummern gleichzeitig zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="3d53c-127">An application requires multiple numbers to be assigned at the same time.</span></span> <span data-ttu-id="3d53c-128">Eine Anwendung muss z. B. fünf sequenzielle Nummern reservieren.</span><span class="sxs-lookup"><span data-stu-id="3d53c-128">For example, an application needs to reserve five sequential numbers.</span></span> <span data-ttu-id="3d53c-129">Wenn Identitätswerte angefordert werden, können Lücken in der Reihe entstehen, wenn andere Prozesse gleichzeitig Nummern ausgeben.</span><span class="sxs-lookup"><span data-stu-id="3d53c-129">Requesting identity values could result in gaps in the series if other processes were simultaneously issued numbers.</span></span> <span data-ttu-id="3d53c-130">Durch einen Aufruf von sp_sequence_get_range können mehrere Nummern in der Sequenz gleichzeitig abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="3d53c-130">Calling sp_sequence_get_range can retrieve several numbers in the sequence at once.</span></span>  
  
-   <span data-ttu-id="3d53c-131">Sie müssen die Spezifikation der Sequenz ändern (z. B. den Inkrementwert).</span><span class="sxs-lookup"><span data-stu-id="3d53c-131">You need to change the specification of the sequence, such as the increment value.</span></span>  
  
## <a name="limitations"></a><span data-ttu-id="3d53c-132">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="3d53c-132">Limitations</span></span>  
 <span data-ttu-id="3d53c-133">Im Unterschied zu Identitätsspalten, deren Werte nicht geändert werden können, werden Sequenzwerte nach dem Einfügen in die Tabelle nicht automatisch geschützt.</span><span class="sxs-lookup"><span data-stu-id="3d53c-133">Unlike identity columns, whose values cannot be changed, sequence values are not automatically protected after insertion into the table.</span></span> <span data-ttu-id="3d53c-134">Um das Ändern von Sequenzwerten zu verhindern, verwenden Sie für die Tabelle einen Updatetrigger, um einen Rollback der Änderungen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="3d53c-134">To prevent sequence values from being changed, use an update trigger on the table to roll back changes.</span></span>  
  
 <span data-ttu-id="3d53c-135">Die Eindeutigkeit von Sequenzwerten wird nicht automatisch erzwungen.</span><span class="sxs-lookup"><span data-stu-id="3d53c-135">Uniqueness is not automatically enforced for sequence values.</span></span> <span data-ttu-id="3d53c-136">Sequenzwerte sind so konzipiert, dass sie wiederverwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="3d53c-136">The ability to reuse sequence values is by design.</span></span> <span data-ttu-id="3d53c-137">Wenn Sequenzwerte in einer Tabelle eindeutig sein müssen, erstellen Sie für die Spalte einen eindeutigen Index.</span><span class="sxs-lookup"><span data-stu-id="3d53c-137">If sequence values in a table are required to be unique, create a unique index on the column.</span></span> <span data-ttu-id="3d53c-138">Wenn Sequenzwerte in einer Tabelle für eine ganze Gruppe von Tabellen eindeutig sein müssen, erstellen Sie Trigger, mit denen verhindert wird, dass durch Updateanweisungen oder Sequenznummerzyklen Duplikate erzeugt werden.</span><span class="sxs-lookup"><span data-stu-id="3d53c-138">If sequence values in a table are required to be unique throughout a group of tables, create triggers to prevent duplicates caused by update statements or sequence number cycling.</span></span>  
  
 <span data-ttu-id="3d53c-139">Das Sequenzobjekt generiert Nummern entsprechend seiner Definition, es steuert jedoch nicht die Verwendung dieser Nummern.</span><span class="sxs-lookup"><span data-stu-id="3d53c-139">The sequence object generates numbers according to its definition, but the sequence object does not control how the numbers are used.</span></span> <span data-ttu-id="3d53c-140">In eine Tabelle eingefügte Sequenznummern können Lücken aufweisen, wenn ein Rollback für eine Transaktion ausgeführt wird, wenn ein Sequenzobjekt von mehreren Tabellen gemeinsam verwendet wird oder wenn Sequenznummern zugeordnet sind, ohne dass sie in Tabellen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3d53c-140">Sequence numbers inserted into a table can have gaps when a transaction is rolled back, when a sequence object is shared by multiple tables, or when sequence numbers are allocated without using them in tables.</span></span> <span data-ttu-id="3d53c-141">Bei Erstellung mit der CACHE-Option können die Sequenznummern im Cache durch unerwartetes Herunterfahren, z. B. bei einem Stromausfall, verloren gehen.</span><span class="sxs-lookup"><span data-stu-id="3d53c-141">When created with the CACHE option, an unexpected shutdown, such as a power failure, can lose the sequence numbers in the cache.</span></span>  
  
 <span data-ttu-id="3d53c-142">Wenn mehrere Instanzen der `NEXT VALUE FOR`-Funktion denselben Sequenz-Generator in einer einzelnen [!INCLUDE[tsql](../../../includes/tsql-md.md)]-Anweisung angeben, geben all diese Instanzen den gleichen Wert für eine bestimmte Zeile zurück, die von dieser [!INCLUDE[tsql](../../../includes/tsql-md.md)]-Anweisung verarbeitet wurde.</span><span class="sxs-lookup"><span data-stu-id="3d53c-142">If there are multiple instances of the `NEXT VALUE FOR` function specifying the same sequence generator within a single [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement, all those instances return the same value for a given row processed by that [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="3d53c-143">Dieses Verhalten ist mit dem ANSI-Standard konsistent.</span><span class="sxs-lookup"><span data-stu-id="3d53c-143">This behavior is consistent with the ANSI standard.</span></span>  
  
## <a name="typical-use"></a><span data-ttu-id="3d53c-144">Typische Verwendung</span><span class="sxs-lookup"><span data-stu-id="3d53c-144">Typical Use</span></span>  
 <span data-ttu-id="3d53c-145">Verwenden Sie die folgende Anweisung, um eine ganzzahlige Sequenznummer zu erstellen, die von -2.147.483.648 bis 2.147.483.647 um jeweils 1 inkrementiert wird.</span><span class="sxs-lookup"><span data-stu-id="3d53c-145">To create an integer sequence number that increments by 1 from -2,147,483,648 to 2,147,483,647, use the following statement.</span></span>  
  
```  
CREATE SEQUENCE Schema.SequenceName  
    AS int  
    INCREMENT BY 1 ;  
```  
  
 <span data-ttu-id="3d53c-146">Verwenden Sie die folgende Anweisung, um eine ganzzahlige Sequenznummer zu erstellen, die einer Identitätsspalte ähnelt, die von 1 bis 2.147.483.647 um jeweils 1 inkrementiert wird.</span><span class="sxs-lookup"><span data-stu-id="3d53c-146">To create an integer sequence number similar to an identity column that increments by 1 from 1 to 2,147,483,647, use the following statement.</span></span>  
  
```  
CREATE SEQUENCE Schema.SequenceName  
    AS int  
    START WITH 1  
    INCREMENT BY 1 ;  
  
```  
  
## <a name="managing-sequences"></a><span data-ttu-id="3d53c-147">Verwalten von Sequenzen</span><span class="sxs-lookup"><span data-stu-id="3d53c-147">Managing Sequences</span></span>  
 <span data-ttu-id="3d53c-148">Weitere Informationen zu Sequenzen erhalten Sie durch Abfragen von [sys.sequences](/sql/relational-databases/system-catalog-views/sys-sequences-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3d53c-148">For information about sequences, query [sys.sequences](/sql/relational-databases/system-catalog-views/sys-sequences-transact-sql).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="3d53c-149">Beispiele</span><span class="sxs-lookup"><span data-stu-id="3d53c-149">Examples</span></span>  
 <span data-ttu-id="3d53c-150">Es werden zusätzliche Beispiele in den Themen [CREATE SEQUENCE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-sequence-transact-sql), [NEXT VALUE FOR &#40;Transact-SQL&#41;](/sql/t-sql/functions/next-value-for-transact-sql) und [sp_sequence_get_range](/sql/relational-databases/system-stored-procedures/sp-sequence-get-range-transact-sql) behandelt.</span><span class="sxs-lookup"><span data-stu-id="3d53c-150">There are additional examples in the topics [CREATE SEQUENCE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-sequence-transact-sql), [NEXT VALUE FOR &#40;Transact-SQL&#41;](/sql/t-sql/functions/next-value-for-transact-sql), and [sp_sequence_get_range](/sql/relational-databases/system-stored-procedures/sp-sequence-get-range-transact-sql).</span></span>  
  
### <a name="a-using-a-sequence-number-in-a-single-table"></a><span data-ttu-id="3d53c-151">A.</span><span class="sxs-lookup"><span data-stu-id="3d53c-151">A.</span></span> <span data-ttu-id="3d53c-152">Verwenden einer Sequenznummer in einer einzelnen Tabelle</span><span class="sxs-lookup"><span data-stu-id="3d53c-152">Using a sequence number in a single table</span></span>  
 <span data-ttu-id="3d53c-153">Im folgenden Beispiel werden das Schema „Test“, die Tabelle „Orders“ sowie die Sequenz „CountBy1“ erstellt. Anschließend werden mithilfe der NEXT VALUE FOR-Funktion Zeilen in die Tabelle eingefügt.</span><span class="sxs-lookup"><span data-stu-id="3d53c-153">The following example creates a schema named Test, a table named Orders, and a sequence named CountBy1, and then inserts rows into the table using the NEXT VALUE FOR function.</span></span>  
  
```  
--Create the Test schema  
CREATE SCHEMA Test ;  
GO  
  
-- Create a table  
CREATE TABLE Test.Orders  
    (OrderID int PRIMARY KEY,  
    Name varchar(20) NOT NULL,  
    Qty int NOT NULL);  
GO  
  
-- Create a sequence  
CREATE SEQUENCE Test.CountBy1  
    START WITH 1  
    INCREMENT BY 1 ;  
GO  
  
-- Insert three records  
INSERT Test.Orders (OrderID, Name, Qty)  
    VALUES (NEXT VALUE FOR Test.CountBy1, 'Tire', 2) ;  
INSERT test.Orders (OrderID, Name, Qty)  
    VALUES (NEXT VALUE FOR Test.CountBy1, 'Seat', 1) ;  
INSERT test.Orders (OrderID, Name, Qty)  
    VALUES (NEXT VALUE FOR Test.CountBy1, 'Brake', 1) ;  
GO  
  
-- View the table  
SELECT * FROM Test.Orders ;  
GO  
```  
  
 [!INCLUDE[ssResult](../../../includes/ssresult-md.md)]  
  
 `OrderID  Name    Qty`  
  
 `1        Tire    2`  
  
 `2        Seat    1`  
  
 `3        Brake   1`  
  
### <a name="b-calling-next-value-for-before-inserting-a-row"></a><span data-ttu-id="3d53c-154">B.</span><span class="sxs-lookup"><span data-stu-id="3d53c-154">B.</span></span> <span data-ttu-id="3d53c-155">Aufrufen von NEXT VALUE FOR vor dem Einfügen einer Zeile</span><span class="sxs-lookup"><span data-stu-id="3d53c-155">Calling NEXT VALUE FOR before inserting a row</span></span>  
 <span data-ttu-id="3d53c-156">Im folgenden Beispiel wird mit der in Beispiel A erstellten `Orders` -Tabelle eine Variable mit dem Namen `@nextID`erstellt. Anschließend wird die Variable mithilfe der NEXT VALUE FOR-Funktion auf die nächste verfügbare Sequenznummer festgelegt.</span><span class="sxs-lookup"><span data-stu-id="3d53c-156">Using the `Orders` table created in example A, the following example declares a variable named `@nextID`, and then uses the NEXT VALUE FOR function to set the variable to the next available sequence number.</span></span> <span data-ttu-id="3d53c-157">Hierfür wird angenommen, dass die Bestellung von der Anwendung verarbeitet wird, beispielsweise, indem für den Benutzer die `OrderID` -Nummer der potenziellen Bestellung bereitgestellt wird. Anschließend wird die Bestellung validiert.</span><span class="sxs-lookup"><span data-stu-id="3d53c-157">The application is presumed to do some processing of the order, such as providing the customer with the `OrderID` number of their potential order, and then validates the order.</span></span> <span data-ttu-id="3d53c-158">Ungeachtet der Zeit, die für diese Verarbeitung benötigt wird und wie viele weitere Bestellungen während des Prozesses hinzugefügt werden, wird die ursprüngliche Nummer für die Verwendung durch diese Verbindung beibehalten.</span><span class="sxs-lookup"><span data-stu-id="3d53c-158">No matter how long this processing might take, or how many other orders are added during the process, the original number is preserved for use by this connection.</span></span> <span data-ttu-id="3d53c-159">Schließlich wird die Bestellung mit der `INSERT` -Anweisung der `Orders` -Tabelle hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="3d53c-159">Finally, the `INSERT` statement adds the order to the `Orders` table.</span></span>  
  
```  
DECLARE @NextID int ;  
SET @NextID = NEXT VALUE FOR Test.CountBy1;  
-- Some work happens  
INSERT Test.Orders (OrderID, Name, Qty)  
    VALUES (@NextID, 'Rim', 2) ;  
GO  
  
```  
  
### <a name="c-using-a-sequence-number-in-multiple-tables"></a><span data-ttu-id="3d53c-160">C.</span><span class="sxs-lookup"><span data-stu-id="3d53c-160">C.</span></span> <span data-ttu-id="3d53c-161">Verwenden einer Sequenznummer in mehreren Tabellen</span><span class="sxs-lookup"><span data-stu-id="3d53c-161">Using a sequence number in multiple tables</span></span>  
 <span data-ttu-id="3d53c-162">In diesem Beispiel wird davon ausgegangen, dass ein Fertigungsstraßen-Überwachungsprozess Benachrichtigung über Ereignisse empfängt, die am Produktionsort auftreten.</span><span class="sxs-lookup"><span data-stu-id="3d53c-162">This example assumes that a production-line monitoring process receives notification of events that occur throughout the workshop.</span></span> <span data-ttu-id="3d53c-163">Jedem Ereignis wird eine eindeutige und stetig steigende `EventID` -Nummer zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="3d53c-163">Each event receives a unique and monotonically increasing `EventID` number.</span></span> <span data-ttu-id="3d53c-164">Für alle Ereignisse wird dieselbe `EventID` -Sequenznummer verwendet, sodass die einzelnen Ereignisse in Berichten, in denen alle Ereignisse kombiniert sind, eindeutig identifiziert werden können.</span><span class="sxs-lookup"><span data-stu-id="3d53c-164">All events use the same `EventID` sequence number so that reports that combine all events can uniquely identify each event.</span></span> <span data-ttu-id="3d53c-165">Die Ereignisdaten werden jedoch in drei verschiedenen Tabellen gespeichert, je nach Typ des jeweiligen Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="3d53c-165">However the event data is stored in three different tables, depending on the type of event.</span></span> <span data-ttu-id="3d53c-166">Im Codebeispiel werden das Schema `Audit`, die Sequenz `EventCounter`und drei Tabellen erstellt, die jeweils die `EventCounter` -Sequenz als Standardwert verwenden.</span><span class="sxs-lookup"><span data-stu-id="3d53c-166">The code example creates a schema named `Audit`, a sequence named `EventCounter`, and three tables which each use the `EventCounter` sequence as a default value.</span></span> <span data-ttu-id="3d53c-167">Anschließend werden den drei Tabellen Zeilen hinzugefügt, und die Ergebnisse werden abgefragt.</span><span class="sxs-lookup"><span data-stu-id="3d53c-167">Then the example adds rows to the three tables and queries the results.</span></span>  
  
```  
CREATE SCHEMA Audit ;  
GO  
CREATE SEQUENCE Audit.EventCounter  
    AS int  
    START WITH 1  
    INCREMENT BY 1 ;  
GO  
  
CREATE TABLE Audit.ProcessEvents  
(  
    EventID int PRIMARY KEY CLUSTERED   
        DEFAULT (NEXT VALUE FOR Audit.EventCounter),  
    EventTime datetime NOT NULL DEFAULT (getdate()),  
    EventCode nvarchar(5) NOT NULL,  
    Description nvarchar(300) NULL  
) ;  
GO  
  
CREATE TABLE Audit.ErrorEvents  
(  
    EventID int PRIMARY KEY CLUSTERED  
        DEFAULT (NEXT VALUE FOR Audit.EventCounter),  
    EventTime datetime NOT NULL DEFAULT (getdate()),  
    EquipmentID int NULL,  
    ErrorNumber int NOT NULL,  
    EventDesc nvarchar(256) NULL  
) ;  
GO  
  
CREATE TABLE Audit.StartStopEvents  
(  
    EventID int PRIMARY KEY CLUSTERED  
        DEFAULT (NEXT VALUE FOR Audit.EventCounter),  
    EventTime datetime NOT NULL DEFAULT (getdate()),  
    EquipmentID int NOT NULL,  
    StartOrStop bit NOT NULL  
) ;  
GO  
  
INSERT Audit.StartStopEvents (EquipmentID, StartOrStop)   
    VALUES (248, 0) ;  
INSERT Audit.StartStopEvents (EquipmentID, StartOrStop)   
    VALUES (72, 0) ;  
INSERT Audit.ProcessEvents (EventCode, Description)   
    VALUES (2735,   
    'Clean room temperature 18 degrees C.') ;  
INSERT Audit.ProcessEvents (EventCode, Description)   
    VALUES (18, 'Spin rate threashold exceeded.') ;  
INSERT Audit.ErrorEvents (EquipmentID, ErrorNumber, EventDesc)   
    VALUES (248, 82, 'Feeder jam') ;  
INSERT Audit.StartStopEvents (EquipmentID, StartOrStop)   
    VALUES (248, 1) ;  
INSERT Audit.ProcessEvents (EventCode, Description)   
    VALUES (1841, 'Central feed in bypass mode.') ;  
-- The following statement combines all events, though not all fields.  
SELECT EventID, EventTime, Description FROM Audit.ProcessEvents   
UNION SELECT EventID, EventTime, EventDesc FROM Audit.ErrorEvents   
UNION SELECT EventID, EventTime,   
CASE StartOrStop   
    WHEN 0 THEN 'Start'   
    ELSE 'Stop'  
END   
FROM Audit.StartStopEvents  
ORDER BY EventID ;  
GO  
  
```  
  
 [!INCLUDE[ssResult](../../../includes/ssresult-md.md)]  
  
 `EventID  EventTime                Description`  
  
 `1        2009-11-02 15:00:51.157  Start`  
  
 `2        2009-11-02 15:00:51.160  Start`  
  
 `3        2009-11-02 15:00:51.167  Clean room temperature 18 degrees C.`  
  
 `4        2009-11-02 15:00:51.167  Spin rate threshold exceeded.`  
  
 `5        2009-11-02 15:00:51.173  Feeder jam`  
  
 `6        2009-11-02 15:00:51.177  Stop`  
  
 `7        2009-11-02 15:00:51.180  Central feed in bypass mode.`  
  
### <a name="d-generating-repeating-sequence-numbers-in-a-result-set"></a><span data-ttu-id="3d53c-168">D:</span><span class="sxs-lookup"><span data-stu-id="3d53c-168">D.</span></span> <span data-ttu-id="3d53c-169">Generieren von wiederholten Sequenznummern in einem Resultset</span><span class="sxs-lookup"><span data-stu-id="3d53c-169">Generating repeating sequence numbers in a result set</span></span>  
 <span data-ttu-id="3d53c-170">Im folgenden Beispiel werden zwei Eigenschaften von Sequenznummern veranschaulicht: die zyklische Verwendung und das Verwenden von `NEXT VALUE FOR` in einer SELECT-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="3d53c-170">The following example demonstrates two features of sequence numbers: cycling, and using `NEXT VALUE FOR` in a select statement.</span></span>  
  
```  
CREATE SEQUENCE CountBy5  
   AS tinyint  
    START WITH 1  
    INCREMENT BY 1  
    MINVALUE 1  
    MAXVALUE 5  
    CYCLE ;  
GO  
  
SELECT NEXT VALUE FOR CountBy5 AS SurveyGroup, Name FROM sys.objects ;  
GO  
```  
  
### <a name="e-generating-sequence-numbers-for-a-result-set-by-using-the-over-clause"></a><span data-ttu-id="3d53c-171">E.</span><span class="sxs-lookup"><span data-stu-id="3d53c-171">E.</span></span> <span data-ttu-id="3d53c-172">Generieren von Sequenznummern für ein Resultset mit der OVER-Klausel</span><span class="sxs-lookup"><span data-stu-id="3d53c-172">Generating sequence numbers for a result set by using the OVER clause</span></span>  
 <span data-ttu-id="3d53c-173">Im folgenden Beispiel wird das Resultset mithilfe der `OVER` -Klausel nach `Name` sortiert, bevor die Sequenznummernspalte hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="3d53c-173">The following example uses the `OVER` clause to sort the result set by `Name` before it adds the sequence number column.</span></span>  
  
```  
USE AdventureWorks2012 ;  
GO  
  
CREATE SCHEMA Samples ;  
GO  
  
CREATE SEQUENCE Samples.IDLabel  
    AS tinyint  
    START WITH 1  
    INCREMENT BY 1 ;  
GO  
  
SELECT NEXT VALUE FOR Samples.IDLabel OVER (ORDER BY Name) AS NutID, ProductID, Name, ProductNumber FROM Production.Product  
WHERE Name LIKE '%nut%' ;  
```  
  
### <a name="f-resetting-the-sequence-number"></a><span data-ttu-id="3d53c-174">F.</span><span class="sxs-lookup"><span data-stu-id="3d53c-174">F.</span></span> <span data-ttu-id="3d53c-175">Zurücksetzen der Sequenznummer</span><span class="sxs-lookup"><span data-stu-id="3d53c-175">Resetting the sequence number</span></span>  
 <span data-ttu-id="3d53c-176">In Beispiel E wurden die ersten 79 der `Samples.IDLabel`-Sequenznummern verbraucht.</span><span class="sxs-lookup"><span data-stu-id="3d53c-176">Example E consumed the first 79 of the `Samples.IDLabel` sequence numbers.</span></span> <span data-ttu-id="3d53c-177">(Ihre Version von `AdventureWorks2012` gibt möglicherweise eine andere Anzahl von Ergebnissen zurück.) Führen Sie Folgendes aus, um die nächsten 79 Sequenznummern (80 bis 158) zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="3d53c-177">(Your version of `AdventureWorks2012` may return a different number of results.) Execute the following to consume the next 79 sequence numbers (80 though 158).</span></span>  
  
```  
SELECT NEXT VALUE FOR Samples.IDLabel OVER (ORDER BY Name) AS NutID, ProductID, Name, ProductNumber FROM Production.Product  
WHERE Name LIKE '%nut%' ;  
```  
  
 <span data-ttu-id="3d53c-178">Führen Sie die folgende Anweisung aus, um die `Samples.IDLabel` -Sequenz neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="3d53c-178">Execute the following statement to restart the `Samples.IDLabel` sequence.</span></span>  
  
```  
ALTER SEQUENCE Samples.IDLabel  
RESTART WITH 1 ;  
```  
  
 <span data-ttu-id="3d53c-179">Führen Sie die SELECT-Anweisung erneut aus, um sich zu vergewissern, dass die `Samples.IDLabel` -Sequenz mit der Nummer 1 neu gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="3d53c-179">Execute the select statement again to verify that the `Samples.IDLabel` sequence restarted with number 1.</span></span>  
  
```  
SELECT NEXT VALUE FOR Samples.IDLabel OVER (ORDER BY Name) AS NutID, ProductID, Name, ProductNumber FROM Production.Product  
WHERE Name LIKE '%nut%' ;  
```  
  
### <a name="g-changing-a-table-from-identity-to-sequence"></a><span data-ttu-id="3d53c-180">G.</span><span class="sxs-lookup"><span data-stu-id="3d53c-180">G.</span></span> <span data-ttu-id="3d53c-181">Ändern einer Tabelle von einer Identitäts- in eine Sequenztabelle</span><span class="sxs-lookup"><span data-stu-id="3d53c-181">Changing a table from identity to sequence</span></span>  
 <span data-ttu-id="3d53c-182">Im folgenden Beispiel werden ein Schema und eine Tabelle erstellt, die drei Zeilen für das Beispiel enthält.</span><span class="sxs-lookup"><span data-stu-id="3d53c-182">The following example creates a schema and table containing three rows for the example.</span></span> <span data-ttu-id="3d53c-183">Anschließend wird eine neue Spalte hinzugefügt, und die alte Spalte wird gelöscht.</span><span class="sxs-lookup"><span data-stu-id="3d53c-183">Then the example adds a new column and drops the old column.</span></span>  
  
```  
-- Create a schema  
CREATE SCHEMA Test ;  
GO  
  
-- Create a table  
CREATE TABLE Test.Department  
    (  
        DepartmentID smallint IDENTITY(1,1) NOT NULL,  
        Name nvarchar(100) NOT NULL,  
        GroupName nvarchar(100) NOT NULL  
    CONSTRAINT PK_Department_DepartmentID PRIMARY KEY CLUSTERED   
         (DepartmentID ASC)   
    ) ;  
GO  
  
-- Insert three rows into the table  
INSERT Test.Department(Name, GroupName)  
    VALUES ('Engineering', 'Research and Development');  
GO  
  
INSERT Test.Department(Name, GroupName)  
    VALUES ('Tool Design', 'Research and Development');  
GO  
  
INSERT Test.Department(Name, GroupName)  
    VALUES ('Sales', 'Sales and Marketing');  
GO  
  
-- View the table that will be changed  
SELECT * FROM Test.Department ;  
GO  
  
-- End of portion creating a sample table  
--------------------------------------------------------  
-- Add the new column that does not have the IDENTITY property  
ALTER TABLE Test.Department   
    ADD DepartmentIDNew smallint NULL  
GO  
  
-- Copy values from the old column to the new column  
UPDATE Test.Department  
    SET DepartmentIDNew = DepartmentID ;  
GO  
  
-- Drop the primary key constraint on the old column  
ALTER TABLE Test.Department  
    DROP CONSTRAINT [PK_Department_DepartmentID];  
-- Drop the old column  
ALTER TABLE Test.Department  
    DROP COLUMN DepartmentID ;  
GO  
  
-- Rename the new column to the old columns name  
EXEC sp_rename 'Test.Department.DepartmentIDNew',   
    'DepartmentID', 'COLUMN';  
GO  
  
-- Change the new column to NOT NULL  
ALTER TABLE Test.Department  
    ALTER COLUMN DepartmentID smallint NOT NULL ;  
-- Add the unique primary key constraint  
ALTER TABLE Test.Department  
    ADD CONSTRAINT PK_Department_DepartmentID PRIMARY KEY CLUSTERED   
         (DepartmentID ASC) ;  
-- Get the highest current value from the DepartmentID column   
-- and create a sequence to use with the column. (Returns 3.)  
SELECT MAX(DepartmentID) FROM Test.Department ;  
-- Use the next desired value (4) as the START WITH VALUE;  
CREATE SEQUENCE Test.DeptSeq  
    AS smallint  
    START WITH 4  
    INCREMENT BY 1 ;  
GO  
  
-- Add a default value for the DepartmentID column  
ALTER TABLE Test.Department  
    ADD CONSTRAINT DefSequence DEFAULT (NEXT VALUE FOR Test.DeptSeq)   
        FOR DepartmentID;  
GO  
  
-- View the result  
SELECT DepartmentID, Name, GroupName  
FROM Test.Department ;   
-- Test insert  
INSERT Test.Department (Name, GroupName)  
    VALUES ('Audit', 'Quality Assurance') ;  
GO  
  
-- View the result  
SELECT DepartmentID, Name, GroupName  
FROM Test.Department ;  
GO  
  
```  
  
 [!INCLUDE[tsql](../../../includes/tsql-md.md)]<span data-ttu-id="3d53c-184">-Anweisungen, die `SELECT *` verwenden, empfangen die neue Spalte anstelle der ersten Spalte als letzte Spalte.</span><span class="sxs-lookup"><span data-stu-id="3d53c-184">statements that use `SELECT *` will receive the new column as the last column instead of the first column.</span></span> <span data-ttu-id="3d53c-185">Wenn dies nicht zulässig ist, müssen Sie eine völlig neue Tabelle erstellen, die Daten in diese Tabelle verschieben und die Berechtigungen für die neue Tabelle erneut erstellen.</span><span class="sxs-lookup"><span data-stu-id="3d53c-185">If this is not acceptable, then you must create an entirely new table, move the data to it, and then recreate the permissions on the new table.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="3d53c-186">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="3d53c-186">Related Content</span></span>  
 [<span data-ttu-id="3d53c-187">CREATE SEQUENCE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3d53c-187">CREATE SEQUENCE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-sequence-transact-sql)  
  
 [<span data-ttu-id="3d53c-188">ALTER SEQUENCE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3d53c-188">ALTER SEQUENCE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-sequence-transact-sql)  
  
 [<span data-ttu-id="3d53c-189">DROP SEQUENCE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3d53c-189">DROP SEQUENCE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-sequence-transact-sql)  
  
 [<span data-ttu-id="3d53c-190">IDENTITY &#40;Property&#41; &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3d53c-190">IDENTITY &#40;Property&#41; &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-table-transact-sql-identity-property)  
  
  
