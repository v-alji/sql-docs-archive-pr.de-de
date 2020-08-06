---
title: Ratgeber für native Kompilierung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
f1_keywords:
- sql12.swb.nativecompilationwizard.f1
- swb.nativecompilationwizard.f1
ms.assetid: d3898a47-2985-4a08-bc70-fd8331a01b7b
author: rothja
ms.author: jroth
ms.openlocfilehash: b2182d89489af5da8bc3b85b89484fbbf72e4dfa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725745"
---
# <a name="native-compilation-advisor"></a><span data-ttu-id="29fb5-102">Ratgeber für native Kompilierung</span><span class="sxs-lookup"><span data-stu-id="29fb5-102">Native Compilation Advisor</span></span>
  <span data-ttu-id="29fb5-103">Das Tool Transaktions Leistungsberichte (siehe [ermitteln, ob eine Tabelle oder eine gespeicherte Prozedur zu in-Memory OLTP portiert werden soll](determining-if-a-table-or-stored-procedure-should-be-ported-to-in-memory-oltp.md)) informiert Sie darüber, welche interpretierten gespeicherten Prozeduren in der Datenbank von einer Portierung zur systeminternen Kompilierung profitieren.</span><span class="sxs-lookup"><span data-stu-id="29fb5-103">Transaction performance reports tool (see [Determining if a Table or Stored Procedure Should Be Ported to In-Memory OLTP](determining-if-a-table-or-stored-procedure-should-be-ported-to-in-memory-oltp.md)) informs you about which interpreted stored procedures in your database will benefit if ported to use native compilation.</span></span> <span data-ttu-id="29fb5-104">Nachdem Sie eine gespeicherte Prozedur identifiziert haben, die Sie zur Verwendung der systeminternen Kompilierung portieren möchten, können Sie den Ratgeber für die systeminterne Kompilierung verwenden, um die Migration der interpretierten gespeicherten Prozedur zur systeminternen Kompilierung zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="29fb5-104">After you identify a stored procedure that you would like to port to use native compilation, you can use the native compilation advisor to help you migrate the interpreted stored procedure to native compilation.</span></span> <span data-ttu-id="29fb5-105">Weitere Informationen zu systemintern kompilierten gespeicherten Prozeduren finden Sie unter [Natively Compiled Stored Procedures](natively-compiled-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="29fb5-105">For more information about natively compiled stored procedures, see [Natively Compiled Stored Procedures](natively-compiled-stored-procedures.md).</span></span>  
  
 <span data-ttu-id="29fb5-106">Stellen Sie zunächst eine Verbindung mit der Instanz her, die die interpretierte gespeicherte Prozedur enthält.</span><span class="sxs-lookup"><span data-stu-id="29fb5-106">To begin, connect to the instance that contains the interpreted stored procedure.</span></span> <span data-ttu-id="29fb5-107">Die Verbindung kann mit einer Instanz von [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] oder [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="29fb5-107">You can connect to [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], or [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] instance.</span></span> <span data-ttu-id="29fb5-108">Wenn Sie jedoch einen Migrationsvorgang mit dem Ratgeber ausführen möchten, müssen Sie eine Verbindung mit einer [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] -Instanz herstellen, für die In-Memory OLTP aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="29fb5-108">However, if you wish to perform a migration operation with the advisor, you must connect to a [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] instance on which In-Memory OLTP functionality is enabled.</span></span> <span data-ttu-id="29fb5-109">Weitere Informationen zu den Anforderungen für In-Memory OLTP finden Sie unter [Requirements for Using Memory-Optimized Tables](memory-optimized-tables.md).</span><span class="sxs-lookup"><span data-stu-id="29fb5-109">For more information about In-Memory OLTP requirements, see [Requirements for Using Memory-Optimized Tables](memory-optimized-tables.md).</span></span>  
  
 <span data-ttu-id="29fb5-110">Weitere Informationen zu Migrationsmethoden finden Sie unter [In-Memory OLTP - Common Workload Patterns and Migration Considerations (In-Memory-OLTP: Allgemeine Workloadmuster und Überlegungen zur Migration)](https://msdn.microsoft.com/library/dn673538.aspx).</span><span class="sxs-lookup"><span data-stu-id="29fb5-110">For information about migration methodologies, see [In-Memory OLTP - Common Workload Patterns and Migration Considerations](https://msdn.microsoft.com/library/dn673538.aspx).</span></span>  
  
## <a name="walkthrough-using-the-native-compilation-advisor"></a><span data-ttu-id="29fb5-111">Exemplarische Vorgehensweise: Ratgeber für native Kompilierung</span><span class="sxs-lookup"><span data-stu-id="29fb5-111">Walkthrough Using the Native Compilation Advisor</span></span>  
 <span data-ttu-id="29fb5-112">Klicken Sie im **Objekt-Explorer**mit der rechten Maustaste auf die gespeicherte Prozedur, die Sie konvertieren möchten, und wählen Sie **Ratgeber für native Kompilierung**aus.</span><span class="sxs-lookup"><span data-stu-id="29fb5-112">In **Object Explorer**, right click the stored procedure you want to convert, and select **Native Compilation Advisor**.</span></span> <span data-ttu-id="29fb5-113">Daraufhin wird die Willkommensseite für **Ratgeber für die native Kompilierung gespeicherter Prozeduren**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="29fb5-113">This will display the welcome page for the **Stored Procedure Native Compilation Advisor**.</span></span> <span data-ttu-id="29fb5-114">Klicken Sie auf zum Fortfahren auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="29fb5-114">Click **Next** to continue.</span></span>  
  
### <a name="stored-procedure-validation"></a><span data-ttu-id="29fb5-115">Überprüfung der gespeicherten Prozedur</span><span class="sxs-lookup"><span data-stu-id="29fb5-115">Stored Procedure Validation</span></span>  
 <span data-ttu-id="29fb5-116">Auf dieser Seite wird angezeigt, ob die gespeicherte Prozedur Konstrukte verwendet, die mit der nativen Kompilierung nicht kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="29fb5-116">This page will report if the stored procedure uses any constructs that are not compatible with native compilation.</span></span> <span data-ttu-id="29fb5-117">Klicken Sie auf **Weiter** , um weitere Details anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="29fb5-117">You can click **Next** to see details.</span></span> <span data-ttu-id="29fb5-118">Wenn Konstrukte vorhanden sind, die nicht mit der nativen Kompilierung kompatibel sind, können Sie durch Klicken auf **Weiter** zusätzliche Details abrufen.</span><span class="sxs-lookup"><span data-stu-id="29fb5-118">If there are constructs that are not compatible with native compilation, you can click **Next** to see details.</span></span>  
  
### <a name="stored-procedure-validation-result"></a><span data-ttu-id="29fb5-119">Überprüfungsergebnis der gespeicherten Prozedur</span><span class="sxs-lookup"><span data-stu-id="29fb5-119">Stored Procedure Validation Result</span></span>  
 <span data-ttu-id="29fb5-120">Wenn Konstrukte vorhanden sind, die nicht mit der nativen Kompilierung kompatibel sind, werden auf der Seite **Überprüfungsergebnis der gespeicherten Prozedur** detaillierte Informationen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="29fb5-120">If there are constructs that are not compatible with native compilation, the **Stored Procedure Validation Result** page will display details.</span></span> <span data-ttu-id="29fb5-121">Sie können (durch Klicken auf **Bericht generieren**) einen Bericht generieren, den **Ratgeber für native Kompilierung**beenden und den Code aktualisieren, sodass er mit der nativen Kompilierung kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="29fb5-121">You can generate a report (click **Generate Report**), exit the **Native Compilation Advisor**, and update your code so that it is compatible with native compilation.</span></span>  
  
## <a name="code-sample"></a><span data-ttu-id="29fb5-122">Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="29fb5-122">Code Sample</span></span>  
 <span data-ttu-id="29fb5-123">Im folgenden Beispiel werden eine interpretierte gespeicherte Prozedur und die äquivalente gespeicherte Prozedur für die systeminterne Kompilierung erläutert.</span><span class="sxs-lookup"><span data-stu-id="29fb5-123">The following sample shows an interpreted stored procedure and the equivalent stored procedure for native compilation.</span></span> <span data-ttu-id="29fb5-124">Das in diesem Beispiel verwendete Verzeichnis ist c:\data.</span><span class="sxs-lookup"><span data-stu-id="29fb5-124">The sample assumes a directory called c:\data.</span></span>  
  
```sql  
CREATE DATABASE Demo  
ON  
PRIMARY(NAME = [Demo_data],  
FILENAME = 'C:\DATA\Demo_data.mdf', size=500MB)  
, FILEGROUP [Demo_fg] CONTAINS MEMORY_OPTIMIZED_DATA(  
NAME = [Demo_dir],  
FILENAME = 'C:\DATA\Demo_dir')  
LOG ON (name = [Demo_log], Filename='C:\DATA\Demo_log.ldf', size=500MB)  
COLLATE Latin1_General_100_BIN2;  
GO  
USE Demo;  
GO  
  
CREATE TABLE [dbo].[SalesOrders]  
(  
     [order_id] [int] NOT NULL,  
     [order_date] [datetime] NOT NULL,  
     [order_status] [tinyint] NOT NULL  
  
CONSTRAINT [PK_SalesOrders] PRIMARY KEY NONCLUSTERED HASH   
(  
     [order_id]  
)WITH ( BUCKET_COUNT = 2097152)  
)WITH ( MEMORY_OPTIMIZED = ON )  
  
go  
  
CREATE PROCEDURE [dbo].[InsertOrder] @id INT, @date DATETIME2, @status TINYINT  
AS   
BEGIN   
  
  INSERT dbo.SalesOrders VALUES (@id, @date, @status)  
  
END  
  
go  
  
CREATE PROCEDURE [dbo].[InsertOrderXTP] @id INT, @date DATETIME2, @status TINYINT  
  WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS   
BEGIN ATOMIC WITH   
(    TRANSACTION ISOLATION LEVEL = SNAPSHOT,  
     LANGUAGE = N'us_english')  
  
  INSERT dbo.SalesOrders VALUES (@id, @date, @status)  
  
END  
go  
  
select * from SalesOrders  
go  
exec dbo.InsertOrder @id= 10, @date = '1956-01-01 12:00:00', @status = 1 ;  
exec dbo.InsertOrderXTP @id= 11, @date = '1956-01-01 12:01:00', @status = 2 ;  
select * from SalesOrders  
```  
  
## <a name="see-also"></a><span data-ttu-id="29fb5-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="29fb5-125">See Also</span></span>  
 [<span data-ttu-id="29fb5-126">Migrieren zu In-Memory OLTP</span><span class="sxs-lookup"><span data-stu-id="29fb5-126">Migrating to In-Memory OLTP</span></span>](migrating-to-in-memory-oltp.md)  
  
  
