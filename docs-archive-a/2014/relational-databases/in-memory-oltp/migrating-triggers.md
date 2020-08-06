---
title: Migrieren von Triggern | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: ad5385c5-5a50-40ca-a319-97d5606b8511
author: rothja
ms.author: jroth
ms.openlocfilehash: 25965e7cce84b0dcfcd3b6ce6176e8ad3ddabc6a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725766"
---
# <a name="migrating-triggers"></a><span data-ttu-id="a3293-102">Migrieren von Triggern</span><span class="sxs-lookup"><span data-stu-id="a3293-102">Migrating Triggers</span></span>
  <span data-ttu-id="a3293-103">In diesem Thema werden DDL- und DML-Trigger sowie speicheroptimierte Tabellen erläutert.</span><span class="sxs-lookup"><span data-stu-id="a3293-103">This topic discusses DDL and DML triggers and memory-optimized tables.</span></span>  
  
 <span data-ttu-id="a3293-104">LOGON-Trigger sind Trigger zum Auslösen von LOGON-Ereignissen.</span><span class="sxs-lookup"><span data-stu-id="a3293-104">LOGON triggers are triggers defined to fire on LOGON events.</span></span> <span data-ttu-id="a3293-105">LOGON-Trigger wirken sich nicht auf speicheroptimierte Tabellen aus.</span><span class="sxs-lookup"><span data-stu-id="a3293-105">LOGON triggers do not affect memory-optimized tables.</span></span>  
  
## <a name="ddl-triggers"></a><span data-ttu-id="a3293-106">DDL-Trigger</span><span class="sxs-lookup"><span data-stu-id="a3293-106">DDL Triggers</span></span>  
 <span data-ttu-id="a3293-107">DDL-Trigger sind Trigger, die ausgelöst werden, wenn eine CREATE-, ALTER-, DROP-, GRANT-, DENY-, REVOKE- oder UPDATE STATISTICS-Anweisung für die Datenbank oder den Server ausgeführt wird, für die oder den sie definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="a3293-107">DDL triggers are triggers defined to fire when a CREATE, ALTER, DROP, GRANT, DENY, REVOKE, or UPDATE STATISTICS statement is executed on the database or server on which it is defined.</span></span>  
  
 <span data-ttu-id="a3293-108">Sie können keine speicheroptimierten Tabellen erstellen, wenn die Datenbank oder der Server über mindestens einen DDL-Trigger verfügt, der für CREATE_TABLE oder eine beliebige Ereignisgruppe definiert wurde, in der das Ereignis enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="a3293-108">You cannot create memory-optimized tables if the database or server has one or more DDL trigger defined on CREATE_TABLE or any event group that includes it.</span></span> <span data-ttu-id="a3293-109">Sie können keine speicheroptimierte Tabelle löschen, wenn die Datenbank oder der Server über mindestens einen DDL-Trigger verfügt, der für DROP_TABLE oder eine beliebige Ereignisgruppe definiert wurde, in der das Ereignis enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="a3293-109">You cannot drop a memory-optimized table if the database or server has one or more DDL trigger defined on DROP_TABLE or any event group that includes it.</span></span>  
  
 <span data-ttu-id="a3293-110">Systemintern kompilierte gespeicherte Prozeduren können nicht erstellt werden, wenn mindestens ein DDL-Trigger für CREATE_PROCEDURE, DROP_PROCEDURE oder eine beliebige Ereignisgruppe definiert wurde, in der diese Ereignisse enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="a3293-110">You cannot create natively compiled stored procedures if there are one or more DDL triggers on CREATE_PROCEDURE, DROP_PROCEDURE, or any event group that includes those events.</span></span>  
  
## <a name="dml-triggers"></a><span data-ttu-id="a3293-111">DML-Trigger</span><span class="sxs-lookup"><span data-stu-id="a3293-111">DML Triggers</span></span>  
 <span data-ttu-id="a3293-112">DML-Trigger können nicht für speicheroptimierte Tabellen definiert werden.</span><span class="sxs-lookup"><span data-stu-id="a3293-112">DML triggers cannot be defined on memory-optimized tables.</span></span> <span data-ttu-id="a3293-113">Mit In-Memory OLTP können Sie jedoch eine mit DML-Triggern vergleichbare Wirkung erzielen, wenn Sie gespeicherte Prozeduren explizit verwenden, um INSERT-, UPDATE- oder DELETE-Vorgänge für Daten auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a3293-113">However, In-Memory OLTP allows you to achieve an effect similar to DML triggers if you explicitly use stored procedures to insert, update, or delete data.</span></span> <span data-ttu-id="a3293-114">Wenn Ihr System Ad-hoc-Abfragen enthält, sollten Sie sie konvertieren, damit sie die gespeicherten Prozeduren verwenden, anstatt die Wirkung von DML-Triggern zu simulieren.</span><span class="sxs-lookup"><span data-stu-id="a3293-114">If your system contains ad-hoc queries, convert them to use these stored procedures instead to simulate the effect of DML triggers.</span></span>  
  
 <span data-ttu-id="a3293-115">Je nach Triggerereignis (FOR/AFTER oder INSTEAD OF) können Sie den Inhalt des Triggers in die entsprechende gespeicherte Prozedur einschließen, von der INSERT, UPDATE oder DELETE für die Tabelle ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a3293-115">Depending on the trigger event (FOR/AFTER or INSTEAD OF), you may include the content of the trigger in the appropriate stored procedure that performs INSERT, UPDATE, or DELETE on that table.</span></span> <span data-ttu-id="a3293-116">Bei der Migration eines AFTER INSERT-Triggers können Sie beispielsweise die gespeicherte Prozedur ändern, die den Einfügevorgang ausführt. Dazu fügen Sie den Inhalt des Triggers nach der entsprechenden INSERT-Anweisung ein.</span><span class="sxs-lookup"><span data-stu-id="a3293-116">For example, when migrating an AFTER INSERT trigger, you could alter the stored procedure that performs the insert operation by including the content of the trigger after the appropriate INSERT statement.</span></span>  
  
 <span data-ttu-id="a3293-117">Sie können eine interpretierte gespeicherte Prozedur oder eine systemintern kompilierte gespeicherte Prozedur verwenden.</span><span class="sxs-lookup"><span data-stu-id="a3293-117">You can use an interpreted stored procedure or a natively compiled stored procedure.</span></span> <span data-ttu-id="a3293-118">Die meisten [!INCLUDE[tsql](../../includes/tsql-md.md)]-Konstrukte in einer interpretierten gespeicherten Prozedur können für eine speicheroptimierte Tabelle ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a3293-118">Most [!INCLUDE[tsql](../../includes/tsql-md.md)] constructs in an interpreted stored procedure can execute on a memory-optimized table.</span></span> <span data-ttu-id="a3293-119">In systemintern kompilierten gespeicherten Prozeduren wird jedoch nur eine Teilmenge der [!INCLUDE[tsql](../../includes/tsql-md.md)]-Konstrukte unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a3293-119">However, only a subset of [!INCLUDE[tsql](../../includes/tsql-md.md)] constructs are supported in natively compiled stored procedures.</span></span> <span data-ttu-id="a3293-120">Informationen zur [!INCLUDE[tsql](../../includes/tsql-md.md)] Unterstützung für Speicher optimierte Tabellen finden Sie unter [zugreifen auf Speicher optimierte Tabellen mit interpretiertem Transact-SQL](accessing-memory-optimized-tables-using-interpreted-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="a3293-120">For information on [!INCLUDE[tsql](../../includes/tsql-md.md)] support on memory-optimized tables, see [Accessing Memory-Optimized Tables Using Interpreted Transact-SQL](accessing-memory-optimized-tables-using-interpreted-transact-sql.md).</span></span> <span data-ttu-id="a3293-121">Informationen zur [!INCLUDE[tsql](../../includes/tsql-md.md)] Unterstützung in System intern kompilierten gespeicherten Prozeduren finden Sie unter [von in-Memory OLTP nicht unterstützte Transact-SQL-Konstrukte](transact-sql-constructs-not-supported-by-in-memory-oltp.md).</span><span class="sxs-lookup"><span data-stu-id="a3293-121">For information on [!INCLUDE[tsql](../../includes/tsql-md.md)] support in natively compiled stored procedures, see [Transact-SQL Constructs Not Supported by In-Memory OLTP](transact-sql-constructs-not-supported-by-in-memory-oltp.md).</span></span>  
  
 <span data-ttu-id="a3293-122">Im Folgenden finden Sie ein einfaches Beispiel dafür, wie Sie das Verhalten von DML-Triggern für eine speicheroptimierte Tabelle simulieren.</span><span class="sxs-lookup"><span data-stu-id="a3293-122">The following is a simple example of simulating DML trigger behavior on a memory-optimized table.</span></span>  
  
 <span data-ttu-id="a3293-123">Die Datenbank enthält die folgenden Objekte, die in Form von CREATE TABLE-, CREATE TRIGGER- und CREATE PROCEDURE-Anweisungen in Skripts definiert sind:</span><span class="sxs-lookup"><span data-stu-id="a3293-123">The database contains the following objects, scripted as CREATE TABLE, CREATE TRIGGER, and CREATE PROCEDURE statements:</span></span>  
  
```sql  
CREATE TABLE OrderDetails  
(  
   OrderId int not null primary key,  
   ProductId int not null,  
   SalePrice money not null,  
   Quantity int not null,  
   Total money not null,  
   IsDeleted bit not null DEFAULT (0)  
)  
GO  
  
CREATE TRIGGER tr_order_details_insteadof_insert  
ON OrderDetails  
INSTEAD OF INSERT AS  
BEGIN  
   DECLARE @pid int, @qty_buy int, @qty_remain int  
   SELECT @pid = ProductId, @qty_buy = Quantity FROM inserted  
   SELECT @qty_remain = Quantity FROM Inventory WHERE ProductId = @pid  
   IF (@qty_remain <= @qty_buy)  
      THROW 51000, N'Insufficient inventory!', 1  
   ELSE  
   BEGIN  
      INSERT INTO dbo.OrderDetails (OrderId, ProductId, SalePrice, Quantity, Total)   
      SELECT OrderId, ProductId, SalePrice, Quantity, Total FROM inserted  
      UPDATE Inventory SET Quantity = Quantity - @qty_buy WHERE ProductId = @pid  
   END  
END  
GO  
  
CREATE TRIGGER tr_order_details_after_update  
ON OrderDetails  
AFTER UPDATE AS  
BEGIN  
   INSERT INTO UpdateNotifications (OrderId, UpdateTime) SELECT OrderId, GETDATE() FROM inserted     
END  
GO  
  
CREATE PROCEDURE sp_insert_order_details   
   @OrderId int, @ProductId int, @SalePrice money, @Quantity int, @total money  
AS BEGIN  
   INSERT INTO dbo.OrderDetails (OrderId, ProductId, SalePrice, Quantity, Total)  
   VALUES (@OrderId, @ProductId, @SalePrice, @Quantity, @total)  
END  
GO  
  
CREATE PROCEDURE sp_update_order_details_by_id  
   @OrderId int, @ProductId int, @SalePrice money, @Quantity int, @Total money  
AS BEGIN  
   UPDATE dbo.OrderDetails   
   SET ProductId = @ProductId, SalePrice = @SalePrice, Quantity = @Quantity, Total = @total  
   WHERE OrderId = @OrderId  
END  
GO  
```  
  
 <span data-ttu-id="a3293-124">Die folgenden Objekte sind funktional äquivalent mit dem Zustand vor der Migration:</span><span class="sxs-lookup"><span data-stu-id="a3293-124">The following objects are functionally equivalent to the pre-migration state:</span></span>  
  
```sql  
CREATE TABLE OrderDetails  
(  
   OrderId int not null PRIMARY KEY NONCLUSTERED HASH WITH (BUCKET_COUNT = 1048576),  
   ProductId int not null,  
   SalePrice money not null,  
   Quantity int not null,  
   Total money not null,  
   IsDeleted bit not null DEFAULT (0)  
) WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)  
GO  
  
CREATE TABLE Inventory  
(  
   ProductId int not null PRIMARY KEY NONCLUSTERED,  
   Quantity int not null  
) WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)  
GO  
  
CREATE TABLE UpdateNotifications  
(  
   OrderId int not null,  
   UpdateTime datetime2 not null  
   CONSTRAINT pk_updateNotifications PRIMARY KEY NONCLUSTERED (OrderId, UpdateTime)  
) WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)  
GO  
  
CREATE PROCEDURE sp_insert_order_details   
   @OrderId int, @ProductId int, @SalePrice money, @Quantity int, @total money  
WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'English')  
   DECLARE @qty_remain int  
   SELECT @qty_remain = Quantity FROM dbo.Inventory WHERE ProductId = @ProductId  
   IF (@qty_remain <= @Quantity)  
      THROW 51000, N'Insufficient inventory!', 1  
   ELSE  
   BEGIN  
      INSERT INTO dbo.OrderDetails (OrderId, ProductId, SalePrice, Quantity, Total)   
      VALUES (@OrderId, @ProductId, @SalePrice, @Quantity, @total)  
      UPDATE dbo.Inventory SET Quantity = Quantity - @Quantity WHERE ProductId = @ProductId  
   END  
END  
GO  
  
CREATE PROCEDURE sp_update_order_details_by_id  
   @OrderId int, @ProductId int, @SalePrice money, @Quantity int, @Total money  
WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'English')  
   UPDATE dbo.OrderDetails   
   SET ProductId = @ProductId, SalePrice = @SalePrice, Quantity = @Quantity, Total = @total  
   WHERE OrderId = @OrderId  
   INSERT INTO dbo.UpdateNotifications (OrderId, UpdateTime) VALUES (@OrderId, GETDATE())  
END  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="a3293-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a3293-125">See Also</span></span>  
 [<span data-ttu-id="a3293-126">Migrieren zu In-Memory OLTP</span><span class="sxs-lookup"><span data-stu-id="a3293-126">Migrating to In-Memory OLTP</span></span>](migrating-to-in-memory-oltp.md)  
  
  
