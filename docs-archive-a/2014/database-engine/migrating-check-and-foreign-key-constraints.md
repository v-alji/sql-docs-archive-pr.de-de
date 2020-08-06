---
title: Migrieren von Check-und FOREIGN KEY-Einschränkungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: e0a1a1e4-0062-4872-93c3-cd91b7a43c23
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4bacd7a9c5c00fc6abbb763eaa02dca9493fa513
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618878"
---
# <a name="migrating-check-and-foreign-key-constraints"></a><span data-ttu-id="11f08-102">Migrieren von Überprüfungs- und Fremdschlüsseleinschränkungen</span><span class="sxs-lookup"><span data-stu-id="11f08-102">Migrating Check and Foreign Key Constraints</span></span>
  <span data-ttu-id="11f08-103">Check-und FOREIGN KEY-Einschränkungen werden in in nicht unterstützt [!INCLUDE[hek_2](../includes/hek-2-md.md)] [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="11f08-103">Check and foreign key constraints are not supported in [!INCLUDE[hek_2](../includes/hek-2-md.md)] in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span></span> <span data-ttu-id="11f08-104">Diese Konstrukte werden in der Regel verwendet, um die Integrität logischer Daten im Schema zu erzwingen, und können wichtig sein, um die funktionale Richtigkeit von Anwendungen zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="11f08-104">These constructs are usually used to enforce logical data integrity in the schema and can be important to maintaining the functional correctness of applications.</span></span>  
  
 <span data-ttu-id="11f08-105">Logische Integritätsprüfungen für eine Tabelle, wie z. b. Check-und FOREIGN KEY-Einschränkungen, erfordern zusätzliche Verarbeitungsschritte für Transaktionen und sollten im Allgemeinen für Leistungs sensible Anwendungen vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="11f08-105">Logical integrity checks on a table such as check and foreign key constraints require additional processing on transactions and should generally be avoided for performance-sensitive applications.</span></span> <span data-ttu-id="11f08-106">Wenn solche Überprüfungen jedoch für Ihre Anwendung von entscheidender Bedeutung sind, gibt es zwei Problem Umgehungen.</span><span class="sxs-lookup"><span data-stu-id="11f08-106">However, if such checks are crucial to your application, there exist two workarounds.</span></span>  
  
## <a name="checking-constraints-after-an-insert-update-or-delete-operation"></a><span data-ttu-id="11f08-107">Überprüfen von Einschränkungen nach einem INSERT-, Update-oder DELETE-Vorgang</span><span class="sxs-lookup"><span data-stu-id="11f08-107">Checking Constraints After an Insert, Update, or Delete Operation</span></span>  
 <span data-ttu-id="11f08-108">Diese Problem Umgehung ist optimistisch und basiert auf der Annahme, dass die Mehrzahl der Änderungen die Einschränkungen nicht verletzen.</span><span class="sxs-lookup"><span data-stu-id="11f08-108">This workaround is optimistic, based on the assumption that the majority of changes do not violate the constraints.</span></span> <span data-ttu-id="11f08-109">Bei dieser Problem Umgehung werden die Daten zuerst geändert, bevor die Einschränkungen ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="11f08-109">In this workaround, data is modified first before the constraints are evaluated.</span></span> <span data-ttu-id="11f08-110">Wenn eine Einschränkung verletzt wird, wird Sie erkannt, aber für die Änderung wird kein Rollback ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="11f08-110">If a constraint is violated, it would be detected, but the change will not be rolled back.</span></span>  
  
 <span data-ttu-id="11f08-111">Diese Problem Umgehung hat den Vorteil, dass die Leistung nur minimal beeinträchtigt wird, da die Datenänderung durch Einschränkungs Überprüfungen nicht blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="11f08-111">This workaround has the advantage of having minimal impact on performance because data modification is not blocked by constraint checks.</span></span> <span data-ttu-id="11f08-112">Wenn jedoch eine Änderung auftritt, die gegen eine oder mehrere Einschränkungen verstößt, kann der Vorgang zum Zurücksetzen dieser Änderung viel Zeit in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="11f08-112">However, if a change that violates one or more constraints does occur, the process to roll back that change could take a long time.</span></span>  
  
## <a name="enforcing-constraints-before-an-insert-update-or-delete-operation"></a><span data-ttu-id="11f08-113">Erzwingen von Einschränkungen vor einem INSERT-, Update-oder DELETE-Vorgang</span><span class="sxs-lookup"><span data-stu-id="11f08-113">Enforcing Constraints Before an Insert, Update, or Delete Operation</span></span>  
 <span data-ttu-id="11f08-114">Diese Problem Umgehung emuliert das Verhalten von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="11f08-114">This workaround emulates the behavior of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] constraints.</span></span> <span data-ttu-id="11f08-115">Die Einschränkungen werden vor der Datenänderung überprüft und beenden die Transaktion, wenn eine Überprüfung fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="11f08-115">The constraints are checked before data modification occurs and will terminate the transaction if a check fails.</span></span> <span data-ttu-id="11f08-116">Diese Methode führt zu einer Leistungs Einbuße bei Datenänderungen, stellt jedoch sicher, dass die Daten in einer Tabelle immer den Einschränkungen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="11f08-116">This method incurs a performance penalty on data modifications, but ensures that data inside a table always satisfies the constraints.</span></span>  
  
 <span data-ttu-id="11f08-117">Verwenden Sie diese Problem Umgehung, wenn die Integrität logischer Daten für Richtigkeit und Änderungen, die gegen eine Einschränkung verstoßen, sehr wichtig ist.</span><span class="sxs-lookup"><span data-stu-id="11f08-117">Use this workaround when logical data integrity is crucial to correctness and modifications that violate a constraint are likely.</span></span> <span data-ttu-id="11f08-118">Um die Integrität zu gewährleisten, müssen alle Datenänderungen jedoch über gespeicherte Prozeduren erfolgen, die diese enforktionen einschließen.</span><span class="sxs-lookup"><span data-stu-id="11f08-118">However, to guarantee integrity, all data modifications must occur through stored procedures that include these enforcements.</span></span> <span data-ttu-id="11f08-119">Änderungen durch Ad-hoc-Abfragen und andere gespeicherte Prozeduren erzwingen diese Einschränkungen nicht und können daher ohne Warnung verletzt werden.</span><span class="sxs-lookup"><span data-stu-id="11f08-119">Modifications through ad-hoc queries and other stored procedures will not enforce these constraints and therefore may violate them with no warning.</span></span>  
  
## <a name="sample-code"></a><span data-ttu-id="11f08-120">Beispielcode</span><span class="sxs-lookup"><span data-stu-id="11f08-120">Sample Code</span></span>  
 <span data-ttu-id="11f08-121">Die folgenden Beispiele basieren auf der AdventureWorks2012-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="11f08-121">The following samples are based on the AdventureWorks2012 database.</span></span> <span data-ttu-id="11f08-122">Diese Beispiele basieren speziell auf [Sales]. [SalesOrderDetail]-Tabelle und zugehörige Check-und FOREIGN KEY-Einschränkungen zusätzlich zum eindeutigen Index.</span><span class="sxs-lookup"><span data-stu-id="11f08-122">Specifically, these samples are based on the [Sales].[SalesOrderDetail] table and its associated check and foreign key constraints in addition to the unique index.</span></span>  
  
 <span data-ttu-id="11f08-123">Die hier angegebenen gespeicherten Prozeduren sind nur für einfügen-Vorgänge vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="11f08-123">The stored procedures specified here are for inset operations only.</span></span> <span data-ttu-id="11f08-124">Gespeicherte Prozeduren für Aktualisierungs-und Löschvorgänge sollten ähnliche Strukturen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="11f08-124">Stored procedures for update and delete operations should have similar structures.</span></span>  
  
## <a name="table-definition-for-the-workarounds"></a><span data-ttu-id="11f08-125">Tabellen Definition für die Problem Umgehungen</span><span class="sxs-lookup"><span data-stu-id="11f08-125">Table Definition for the Workarounds</span></span>  
 <span data-ttu-id="11f08-126">Vor der Umstellung in eine Speicher optimierte Tabelle die Definition für [Sales]. [SalesOrderDetail] lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="11f08-126">Before converting to a memory-optimized table, the definition for [Sales].[SalesOrderDetail] is as follows:</span></span>  
  
```sql  
USE [AdventureWorks2012]  
GO  
  
CREATE TABLE [Sales].[SalesOrderDetail]([SalesOrderID] [int] NOT NULL,  
   [SalesOrderDetailID] [int] IDENTITY(1,1) NOT NULL,  
   [CarrierTrackingNumber] [nvarchar](25) NULL,  
   [OrderQty] [smallint] NOT NULL,  
   [ProductID] [int] NOT NULL,  
   [SpecialOfferID] [int] NOT NULL,  
   [UnitPrice] [money] NOT NULL,  
   [UnitPriceDiscount] [money] NOT NULL CONSTRAINT [DF_SalesOrderDetail_UnitPriceDiscount]  DEFAULT ((0.0)),  
   [LineTotal]  AS (isnull(([UnitPrice]*((1.0)-[UnitPriceDiscount]))*[OrderQty],(0.0))),  
   [rowguid] [uniqueidentifier] ROWGUIDCOL  NOT NULL CONSTRAINT [DF_SalesOrderDetail_rowguid]  DEFAULT (newid()),  
   [ModifiedDate] [datetime] NOT NULL CONSTRAINT [DF_SalesOrderDetail_ModifiedDate]  DEFAULT (getdate()),  
 CONSTRAINT [PK_SalesOrderDetail_SalesOrderID_SalesOrderDetailID] PRIMARY KEY CLUSTERED   
(  
   [SalesOrderID] ASC,  
   [SalesOrderDetailID] ASC  
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]) ON [PRIMARY]  
  
GO  
  
ALTER TABLE [Sales].[SalesOrderDetail]  WITH CHECK ADD  CONSTRAINT [FK_SalesOrderDetail_SalesOrderHeader_SalesOrderID] FOREIGN KEY([SalesOrderID])  
REFERENCES [Sales].[SalesOrderHeader] ([SalesOrderID])  
ON DELETE CASCADE  
GO  
  
ALTER TABLE [Sales].[SalesOrderDetail] CHECK CONSTRAINT [FK_SalesOrderDetail_SalesOrderHeader_SalesOrderID]  
GO  
  
ALTER TABLE [Sales].[SalesOrderDetail]  WITH CHECK ADD  CONSTRAINT [FK_SalesOrderDetail_SpecialOfferProduct_SpecialOfferIDProductID] FOREIGN KEY([SpecialOfferID], [ProductID])  
REFERENCES [Sales].[SpecialOfferProduct] ([SpecialOfferID], [ProductID])  
GO  
  
ALTER TABLE [Sales].[SalesOrderDetail] CHECK CONSTRAINT [FK_SalesOrderDetail_SpecialOfferProduct_SpecialOfferIDProductID]  
GO  
  
ALTER TABLE [Sales].[SalesOrderDetail]  WITH CHECK ADD  CONSTRAINT [CK_SalesOrderDetail_OrderQty] CHECK  (([OrderQty]>(0)))  
GO  
  
ALTER TABLE [Sales].[SalesOrderDetail] CHECK CONSTRAINT [CK_SalesOrderDetail_OrderQty]  
GO  
  
ALTER TABLE [Sales].[SalesOrderDetail]  WITH CHECK ADD  CONSTRAINT [CK_SalesOrderDetail_UnitPrice] CHECK  (([UnitPrice]>=(0.00)))  
GO  
  
ALTER TABLE [Sales].[SalesOrderDetail] CHECK CONSTRAINT [CK_SalesOrderDetail_UnitPrice]  
GO  
  
ALTER TABLE [Sales].[SalesOrderDetail]  WITH CHECK ADD  CONSTRAINT [CK_SalesOrderDetail_UnitPriceDiscount] CHECK  (([UnitPriceDiscount]>=(0.00)))  
GO  
  
ALTER TABLE [Sales].[SalesOrderDetail] CHECK CONSTRAINT [CK_SalesOrderDetail_UnitPriceDiscount]  
GO  
```  
  
 <span data-ttu-id="11f08-127">Nach der Umstellung in eine Speicher optimierte Tabelle die Definition für [Sales]. [SalesOrderDetail] lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="11f08-127">After converting to a memory-optimized table, the definition for [Sales].[SalesOrderDetail] is as follows:</span></span>  
  
 <span data-ttu-id="11f08-128">Beachten Sie, dass ROWGUID keine ROWGUIDCOL mehr ist, da Sie in nicht unterstützt wird [!INCLUDE[hek_2](../includes/hek-2-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="11f08-128">Note that rowguid is no longer a ROWGUIDCOL as it is not supported in [!INCLUDE[hek_2](../includes/hek-2-md.md)].</span></span> <span data-ttu-id="11f08-129">Die Spalte wurde entfernt.</span><span class="sxs-lookup"><span data-stu-id="11f08-129">The column has been removed.</span></span> <span data-ttu-id="11f08-130">Außerdem ist "LineTotal" eine berechnete Spalte und liegt außerhalb des gültigen Bereichs für diesen Artikel und wurde daher ebenfalls entfernt.</span><span class="sxs-lookup"><span data-stu-id="11f08-130">In addition, LineTotal is a computed column and out of scope for this article, so it also has been removed.</span></span>  
  
```sql  
USE [AdventureWorks2012]  
GO  
  
CREATE TABLE [Sales].[SalesOrderDetail]([SalesOrderID] [int] NOT NULL,  
   [SalesOrderDetailID] [int] IDENTITY(1,1) NOT NULL,  
   [CarrierTrackingNumber] [nvarchar](25) NULL,  
   [OrderQty] [smallint] NOT NULL,  
   [ProductID] [int] NOT NULL,  
   [SpecialOfferID] [int] NOT NULL,  
   [UnitPrice] [money] NOT NULL,  
   [UnitPriceDiscount] [money] NOT NULL CONSTRAINT [DF_SalesOrderDetail_UnitPriceDiscount]  DEFAULT ((0.0)),  
   [ModifiedDate] [datetime] NOT NULL CONSTRAINT [DF_SalesOrderDetail_ModifiedDate]  DEFAULT (getdate()),  
   CONSTRAINT [PK_SalesOrderDetail_SalesOrderID_SalesOrderDetailID] PRIMARY KEY NONCLUSTERED   
   (  
      [SalesOrderID] ASC,  
      [SalesOrderDetailID] ASC  
   ),  
   INDEX [AK_SalesOrderDetail_rowguid] NONCLUSTERED HASH ([rowguid]) WITH (BUCKET_COUNT = 1048576),  
   INDEX [IX_SalesOrderDetail_ProductId] NONCLUSTERED ([ProductId] ASC)) WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)  
  
GO  
```  
  
## <a name="checking-constraints-after-an-insert-update-or-delete-operation"></a><span data-ttu-id="11f08-131">Überprüfen von Einschränkungen nach einem INSERT-, Update-oder DELETE-Vorgang</span><span class="sxs-lookup"><span data-stu-id="11f08-131">Checking Constraints After an Insert, Update, or Delete Operation</span></span>  
  
```sql  
USE AdventureWorks2012  
GO  
  
CREATE PROCEDURE Sales.usp_insert_SalesOrderDetails   
   @SalesOrderId int, @CarrierTrackingNumber nvarchar(25) = null, @OrderQty smallint, @ProductId int, @SpecialOfferID int,   
   @UnitPrice money, @UnitPriceDiscount money = 0.00, @ModifiedDate datetime = null  
AS  
BEGIN  
BEGIN TRANSACTION   
   -- handle defaults for the insert.  
   -- This is to make the insert logic less complex. Default constraints on the table should be in sync with this logic.  
   -- Conversely, you can write an INSERT statement for each case where one or more values for the three columns with default constraints are not specified.  
   IF @ModifiedDate = null SET @ModifiedDate = GETDATE()  
  
   -- Insert the row.  
   INSERT INTO Sales.SalesOrderDetail   
      (SalesOrderID, CarrierTrackingNumber, OrderQty, ProductID, SpecialOfferID, UnitPrice, UnitPriceDiscount, ModifiedDate)  
   VALUES   
      (@SalesOrderId, @CarrierTrackingNumber, @OrderQty, @ProductID, @SpecialOfferID, @UnitPrice, @UnitPriceDiscount, , @ModifiedDate)   
  
   -- Now handle constraints  
   DECLARE @violations TABLE   
   (   
      ConstraintName sysname,  
      ViolatedValue1 sql_variant,  
      ViolatedValue2 sql_variant  
   )  
  
   -- FK_SalesOrderDetail_SalesOrderHeader_SalesOrderID  
   IF NOT EXISTS (SELECT soh.SalesOrderId AS [Exists] FROM Sales.SalesOrderHeader soh WHERE soh.SalesOrderID = @SalesOrderId)   
      INSERT INTO @violations (ConstraintName, ViolatedValue1, ViolatedValue2)   
      VALUES (N'FK_SalesOrderDetail_SalesOrderHeader_SalesOrderID', @SalesOrderId, NULL)  
   -- FK_SalesOrderDetail_SpecialOfferProduct_SpecialOfferIDProductID  
   IF NOT EXISTS (SELECT sop.SpecialOfferID, sop.ProductID FROM [Sales].[SpecialOfferProduct] sop WHERE sop.SpecialOfferID = @SpecialOfferID AND sop.ProductID = @ProductId)  
      INSERT INTO @violations (ConstraintName, ViolatedValue1, ViolatedValue2)   
      VALUES (N'FK_SalesOrderDetail_SpecialOfferProduct_SpecialOfferIDProductID', @SpecialOfferId, @ProductId)  
   -- CK_SalesOrderDetail_OrderQty  
   IF NOT @OrderQty > 0   
      INSERT INTO @violations (ConstraintName, ViolatedValue1, ViolatedValue2)   
      VALUES (N'CK_SalesOrderDetail_OrderQty', @OrderQty, NULL)  
   -- CK_SalesOrderDetail_UnitPrice  
   IF NOT @UnitPrice >= 0.00  
      INSERT INTO @violations (ConstraintName, ViolatedValue1, ViolatedValue2)   
      VALUES (N'CK_SalesOrderDetail_UnitPrice', @UnitPrice, NULL)  
   -- CK_SalesOrderDetail_UnitPriceDiscout  
   IF NOT @UnitPriceDiscount >= 0.00  
      INSERT INTO @violations (ConstraintName, ViolatedValue1, ViolatedValue2)   
      VALUES (N'CK_SalesOrderDetail_UnitPriceDiscount', @UnitPriceDiscount, NULL)  
  
   -- Return a rowset containing violated constraints. On an item that doesn't violate anything, should return an empty rowset.  
   SELECT ConstraintName, ViolatedValue1, ViolatedValue2 FROM @violations  
   COMMIT TRANSACTION  
END  
```  
  
## <a name="enforcing-constraints-before-an-insert-update-or-delete-operation"></a><span data-ttu-id="11f08-132">Erzwingen von Einschränkungen vor einem INSERT-, Update-oder DELETE-Vorgang</span><span class="sxs-lookup"><span data-stu-id="11f08-132">Enforcing Constraints Before an Insert, Update or Delete Operation</span></span>  
  
```sql  
USE AdventureWorks2012  
GO  
  
CREATE PROCEDURE Sales.usp_insert_SalesOrderDetails   
   @SalesOrderId int, @CarrierTrackingNumber nvarchar(25) = null, @OrderQty smallint, @ProductId int, @SpecialOfferID int,   
   @UnitPrice money, @UnitPriceDiscount money = 0.00, @ModifiedDate datetime = null  
AS  
BEGIN  
BEGIN TRY  
   BEGIN TRANSACTION  
   -- Verify the constraints first.  
   -- FK_SalesOrderDetail_SalesOrderHeader_SalesOrderID  
   IF NOT EXISTS (SELECT soh.SalesOrderId FROM Sales.SalesOrderHeader soh WHERE soh.SalesOrderID = @SalesOrderId)   
      THROW 50547, N'This SalesOrderId does not exist in SalesOrderHeader', 1  
   -- FK_SalesOrderDetail_SpecialOfferProduct_SpecialOfferIDProductID  
   IF NOT EXISTS (SELECT sop.SpecialOfferID, sop.ProductID FROM [Sales].[SpecialOfferProduct] sop WHERE sop.SpecialOfferID = @SpecialOfferID AND sop.ProductID = @ProductId)  
      THROW 50547, N'This combination of SpecialOfferID and ProductID does not exist in SpecialOfferProduct', 1   
   -- CK_SalesOrderDetail_OrderQty  
   IF NOT @OrderQty > 0   
      THROW 50547, N'OrderQty must be greater than zero.', 1  
   -- CK_SalesOrderDetail_UnitPrice  
   IF NOT @UnitPrice >= 0.00  
      THROW 50547, N'UnitPrice cannot be negative.', 1  
   -- CK_SalesOrderDetail_UnitPriceDiscout  
   IF NOT @UnitPriceDiscount >= 0.00  
      THROW 50547, N'UnitPriceDiscount cannot be negative', 1  
  
   -- All verifications have now passed. Proceed to insert.  
  
   -- handle defaults for the insert.  
   -- This is to make the insert logic less complex. Default constraints on the table should be in sync with this logic.  
   -- Conversely, you can write an INSERT statement for each case where one or more values for the three columns with default constraints are not specified.  
  
   IF @ModifiedDate = null SET @ModifiedDate = GETDATE()  
  
   -- Calculate computed columnn and store it.  
   DECLARE @LineTotal numeric(38, 6)  
   SET @LineTotal = (isnull((@UnitPrice * ((1.0) - @UnitPriceDiscount)) * @OrderQty, (0.0)))  
  
   -- Insert the row.  
   INSERT INTO Sales.SalesOrderDetail   
      (SalesOrderID, CarrierTrackingNumber, OrderQty, ProductID, SpecialOfferID, UnitPrice, UnitPriceDiscount, ModifiedDate)  
   VALUES   
      (@SalesOrderId, @CarrierTrackingNumber, @OrderQty, @ProductID, @SpecialOfferID, @UnitPrice, @UnitPriceDiscount, @ModifiedDate)  
   COMMIT TRANSACTION  
END TRY  
BEGIN CATCH  
   IF @@TRANCOUNT > 0  
      ROLLBACK TRANSACTION  
      THROW;  
END CATCH  
END  
```  
  
## <a name="see-also"></a><span data-ttu-id="11f08-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="11f08-133">See Also</span></span>  
 [<span data-ttu-id="11f08-134">Migrieren zu In-Memory OLTP</span><span class="sxs-lookup"><span data-stu-id="11f08-134">Migrating to In-Memory OLTP</span></span>](../relational-databases/in-memory-oltp/migrating-to-in-memory-oltp.md)  
  
  
