---
title: Datenbankübergreifende Abfragen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: a0305f5b-91bd-4d18-a2fc-ec235b062fd3
author: rothja
ms.author: jroth
ms.openlocfilehash: 4afbb580a55273ec241005493fd37f99e98ec0e7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615387"
---
# <a name="cross-database-queries"></a><span data-ttu-id="e16ca-102">Datenbankübergreifende Abfragen</span><span class="sxs-lookup"><span data-stu-id="e16ca-102">Cross-Database Queries</span></span>
  <span data-ttu-id="e16ca-103">In [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]bieten speicheroptimierte Tabellen keine Unterstützung für datenbankübergreifende Transaktionen.</span><span class="sxs-lookup"><span data-stu-id="e16ca-103">In [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)], memory-optimized tables do not support cross-database transactions.</span></span> <span data-ttu-id="e16ca-104">Innerhalb einer Transaktion oder Abfrage, die auf eine speicheroptimierte Tabelle zugreift, können Sie nicht gleichzeitig auf eine andere Datenbank zugreifen.</span><span class="sxs-lookup"><span data-stu-id="e16ca-104">You cannot access another database from the same transaction or the same query that also accesses a memory-optimized table.</span></span> <span data-ttu-id="e16ca-105">Daten aus einer Tabelle in einer Datenbank können nicht einfach in eine speicheroptimierte Tabelle in einer anderen Datenbank kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="e16ca-105">You cannot easily copy data from a table in one database, to a memory-optimized table in another database.</span></span>  
  
 <span data-ttu-id="e16ca-106">Tabellenvariablen sind nicht transaktional.</span><span class="sxs-lookup"><span data-stu-id="e16ca-106">Table variables are not transactional.</span></span> <span data-ttu-id="e16ca-107">Daher können speicheroptimierte Tabellenvariablen in datenbankübergreifenden Abfragen verwendet werden, um Daten aus einer Datenbank in speicheroptimierte Tabellen in einer anderen Datenbank zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="e16ca-107">Therefore, memory-optimized table variables can be used in cross-database queries, and can thus facilitate moving data from one database into memory-optimized tables in another.</span></span> <span data-ttu-id="e16ca-108">Sie können zwei Transaktionen verwenden.</span><span class="sxs-lookup"><span data-stu-id="e16ca-108">You can use two transactions.</span></span> <span data-ttu-id="e16ca-109">In der ersten Transaktion fügen Sie die Daten aus der Remotetabelle in die Variable ein.</span><span class="sxs-lookup"><span data-stu-id="e16ca-109">In the first transaction, insert the data from the remote table into the variable.</span></span> <span data-ttu-id="e16ca-110">In der zweiten Transaktion fügen Sie die Daten aus der Variablen in die lokale speicheroptimierte Tabelle ein.</span><span class="sxs-lookup"><span data-stu-id="e16ca-110">In the second transaction, insert the data into the local memory-optimized table from the variable.</span></span>  
  
 <span data-ttu-id="e16ca-111">Wenn Sie z. b. die Zeile aus Tabelle T1 in Datenbank db1 in Tabelle T2 in DB2 kopieren möchten, verwenden Sie eine Variable @v1 des Typs dbo. TT1, um Folgendes zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="e16ca-111">For example, to copy the row from table t1 in database db1 to table t2 in db2, using variable @v1 of type dbo.tt1, you can use something like:</span></span>  
  
```sql  
USE db2   
GO   
DECLARE @v1 dbo.tt1   
INSERT @v1 SELECT * FROM db1.dbo.t1   
INSERT dbo.t2 SELECT * FROM @v1   
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="e16ca-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e16ca-112">See Also</span></span>  
 [<span data-ttu-id="e16ca-113">Migrieren zu In-Memory OLTP</span><span class="sxs-lookup"><span data-stu-id="e16ca-113">Migrating to In-Memory OLTP</span></span>](migrating-to-in-memory-oltp.md)  
  
  
