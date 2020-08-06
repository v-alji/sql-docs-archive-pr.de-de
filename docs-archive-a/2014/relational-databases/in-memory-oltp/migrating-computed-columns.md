---
title: Migrieren von berechneten Spalten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 64a9eade-22c3-4a9d-ab50-956219e08df1
author: rothja
ms.author: jroth
ms.openlocfilehash: feb50ef64f42d95913ad4e13f9a79e6e0e4ecad3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725777"
---
# <a name="migrating-computed-columns"></a><span data-ttu-id="21f6a-102">Migrieren von berechneten Spalten</span><span class="sxs-lookup"><span data-stu-id="21f6a-102">Migrating Computed Columns</span></span>
  <span data-ttu-id="21f6a-103">Berechnete Spalten werden in speicheroptimierten Tabellen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="21f6a-103">Computed columns are not supported in memory-optimized tables.</span></span> <span data-ttu-id="21f6a-104">Sie können jedoch eine berechnete Spalte simulieren.</span><span class="sxs-lookup"><span data-stu-id="21f6a-104">However, you can simulate a computed column.</span></span>  
  
 <span data-ttu-id="21f6a-105">Sie sollten berücksichtigen, dass berechnete Spalten beibehalten werden müssen, wenn Sie datenträgerbasierte Tabellen zu speicheroptimierten Tabellen migrieren.</span><span class="sxs-lookup"><span data-stu-id="21f6a-105">You should consider the need to persist your computed columns when you migrate your disk-based tables to memory-optimized tables.</span></span> <span data-ttu-id="21f6a-106">Aufgrund der unterschiedlichen Leistungsmerkmale speicheroptimierter Tabellen und systemintern kompilierter gespeicherter Prozeduren ist u. U. keine Persistenz erforderlich.</span><span class="sxs-lookup"><span data-stu-id="21f6a-106">The different performance characteristics of memory-optimized tables and natively compiled stored procedures may negate the need for persistence.</span></span>  
  
## <a name="non-persisted-computed-columns"></a><span data-ttu-id="21f6a-107">Nicht permanent berechnete Spalten</span><span class="sxs-lookup"><span data-stu-id="21f6a-107">Non-Persisted Computed Columns</span></span>  
 <span data-ttu-id="21f6a-108">Um die Auswirkungen einer nicht persistiert berechneten Spalte zu simulieren, erstellen Sie eine Sicht für die speicheroptimierte Tabelle.</span><span class="sxs-lookup"><span data-stu-id="21f6a-108">To simulate the effects of a non-persisted computed column, create a view on the memory-optimized table.</span></span> <span data-ttu-id="21f6a-109">Fügen Sie in der SELECT-Anweisung, durch die die Sicht definiert wird, die Definition der berechneten Spalte in die Sicht ein.</span><span class="sxs-lookup"><span data-stu-id="21f6a-109">In the SELECT statement that defines the view, add the computed column definition into the view.</span></span> <span data-ttu-id="21f6a-110">Außer in einer systemintern kompilierten gespeicherten Prozedur sollten Abfragen, die Werte aus der berechneten Spalte verwenden, aus der Sicht lesen.</span><span class="sxs-lookup"><span data-stu-id="21f6a-110">Except in a natively compiled stored procedure, queries that use values from the computed column should read from the view.</span></span> <span data-ttu-id="21f6a-111">Innerhalb der systemintern kompilierten gespeicherten Prozeduren sollten Sie eine SELECT-, UPDATE- oder DELETE-Anweisung gemäß der Definition der berechneten Spalte aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="21f6a-111">Inside natively compiled stored procedures, you should update any select, update, or delete statement according to your computed column definition.</span></span>  
  
```sql  
-- Schema for the table dbo.OrderDetails:  
-- OrderId int not null primary key,  
-- ProductId int not null,  
-- SalePrice money not null,  
-- Quantity int not null,  
-- Total money not null  
--  
-- Total is computed as SalePrice * Quantity and is not persisted.  
CREATE VIEW dbo.v_order_details AS  
   SELECT  
      OrderId,  
      ProductId,  
      SalePrice,  
      Quantity,  
      Quantity * SalePrice AS Total  
   FROM dbo.order_details  
```  
  
## <a name="persisted-computed-columns"></a><span data-ttu-id="21f6a-112">Permanent berechnete Spalten</span><span class="sxs-lookup"><span data-stu-id="21f6a-112">Persisted Computed Columns</span></span>  
 <span data-ttu-id="21f6a-113">Um die Auswirkungen einer persistiert berechneten Spalte zu simulieren, erstellen Sie eine gespeicherte Prozedur zum Einfügen in die Tabelle und eine weitere gespeicherte Prozedur zum Aktualisieren der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="21f6a-113">To simulate the effects of a persisted computed column, create a stored procedure for inserting into the table and another stored procedure for updating the table.</span></span> <span data-ttu-id="21f6a-114">Wenn Sie die Tabelle einfügen oder aktualisieren, rufen Sie diese gespeicherten Prozeduren auf, um diese Tasks auszuführen.</span><span class="sxs-lookup"><span data-stu-id="21f6a-114">When inserting or updating the table, invoke these stored procedures to perform these tasks.</span></span> <span data-ttu-id="21f6a-115">Innerhalb der gespeicherten Prozeduren berechnen Sie den Wert für das berechnete Feld gemäß den Eingaben, ähnlich der Definition der berechneten Spalte in der ursprünglichen datenträgerbasierten Tabelle.</span><span class="sxs-lookup"><span data-stu-id="21f6a-115">Inside the stored procedures, calculate the value for the computed field according to the inputs, much like how the computed column is defined on the original disk-based table.</span></span> <span data-ttu-id="21f6a-116">Anschließend können Sie die Tabelle nach Bedarf in der gespeicherten Prozedur einfügen oder aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="21f6a-116">Then, insert or update the table as needed inside the stored procedure.</span></span>  
  
```sql  
-- Schema for the table dbo.OrderDetails:  
-- OrderId int not null primary key,  
-- ProductId int not null,  
-- SalePrice money not null,  
-- Quantity int not null,  
-- Total money not null  
--  
-- Total is computed as SalePrice * Quantity and is persisted.  
-- we need to create insert and update procedures to calculate Total.  
CREATE PROCEDURE sp_insert_order_details   
@OrderId int, @ProductId int, @SalePrice money, @Quantity int  
WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS BEGIN ATOMIC WITH (LANGUAGE = N'english', TRANSACTION ISOLATION LEVEL = SNAPSHOT)  
-- compute the value here.   
-- this stored procedure works with single rows only.  
-- for bulk inserts, accept a table-valued parameter into the stored procedure  
-- and use an INSERT INTO SELECT statement.  
DECLARE @total money = @SalePrice * @Quantity  
INSERT INTO dbo.OrderDetails (OrderId, ProductId, SalePrice, Quantity, Total)  
VALUES (@OrderId, @ProductId, @SalePrice, @Quantity, @total)  
END  
GO  
  
CREATE PROCEDURE sp_update_order_details_by_id  
@OrderId int, @ProductId int, @SalePrice money, @Quantity int  
WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS BEGIN ATOMIC WITH (LANGUAGE = N'english', TRANSACTION ISOLATION LEVEL = SNAPSHOT)  
-- compute the value here.   
-- this stored procedure works with single rows only.  
DECLARE @total money = @SalePrice * @Quantity  
UPDATE dbo.OrderDetails   
SET ProductId = @ProductId, SalePrice = @SalePrice, Quantity = @Quantity, Total = @total  
WHERE OrderId = @OrderId  
END  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="21f6a-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="21f6a-117">See Also</span></span>  
 [<span data-ttu-id="21f6a-118">Migrieren zu In-Memory OLTP</span><span class="sxs-lookup"><span data-stu-id="21f6a-118">Migrating to In-Memory OLTP</span></span>](migrating-to-in-memory-oltp.md)  
  
  
