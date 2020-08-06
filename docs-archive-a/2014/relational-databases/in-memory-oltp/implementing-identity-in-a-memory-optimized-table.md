---
title: Implementieren von IDENTITY in einer speicheroptimierten Tabelle | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: c0a704a3-3a31-4c2c-b967-addacda62ef8
author: rothja
ms.author: jroth
ms.openlocfilehash: 955f9f1a905a9d0c71304320f60abe300e430e4f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616560"
---
# <a name="implementing-identity-in-a-memory-optimized-table"></a><span data-ttu-id="def7a-102">Implementieren von IDENTITY in einer speicheroptimierten Tabelle</span><span class="sxs-lookup"><span data-stu-id="def7a-102">Implementing IDENTITY in a Memory-Optimized Table</span></span>
  <span data-ttu-id="def7a-103">IDENTITY(1, 1) wird in einer speicheroptimierten Tabelle unterstützt.</span><span class="sxs-lookup"><span data-stu-id="def7a-103">IDENTITY(1, 1) is supported on a memory-optimized table.</span></span> <span data-ttu-id="def7a-104">Identitätsspalten mit der Definition IDENTITY(x, y), wobei x != 1 oder y != 1 ist, werden in speicheroptimierten Tabellen jedoch nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="def7a-104">However, identity columns with definition of IDENTITY(x, y) where x != 1 or y != 1 are not supported on memory-optimized tables.</span></span> <span data-ttu-id="def7a-105">Die Problem Umgehung für Identitäts Werte verwendet das Sequenz Objekt ([Sequenznummern](../sequence-numbers/sequence-numbers.md)).</span><span class="sxs-lookup"><span data-stu-id="def7a-105">The workaround for IDENTITY values uses the SEQUENCE object ([Sequence Numbers](../sequence-numbers/sequence-numbers.md)).</span></span>  
  
 <span data-ttu-id="def7a-106">Entfernen Sie zuerst die IDENTITY-Eigenschaft aus der Tabelle, die in In-Memory OLTP konvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="def7a-106">First remove the IDENTITY property from the table you are converting to In-Memory OLTP.</span></span> <span data-ttu-id="def7a-107">Definieren Sie anschließend ein neues SEQUENCE-Objekt für die Spalte in der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="def7a-107">Then, define a new SEQUENCE object for the column in the table.</span></span> <span data-ttu-id="def7a-108">SEQUENCE-Objekte als Identitätsspalten stützen sich auf die Möglichkeit, DEFAULT-Werte für Spalten zu erstellen, die mithilfe der NEXT VALUE FOR-Syntax einen neuen Identitätswert abrufen.</span><span class="sxs-lookup"><span data-stu-id="def7a-108">SEQUENCE objects as identity columns rely on the ability to create DEFAULT values for columns that use the NEXT VALUE FOR syntax to get a new identity value.</span></span> <span data-ttu-id="def7a-109">Da DEFAULT-Werte von In-Memory OLTP nicht unterstützt werden, müssen Sie den neu generierten SEQUENCE-Wert entweder an die INSERT-Anweisung oder an eine systemintern kompilierte gespeicherte Prozedur übergeben, die den Einfügevorgang ausführt.</span><span class="sxs-lookup"><span data-stu-id="def7a-109">Since DEFAULTs are not supported in In-Memory OLTP, you need to pass the newly-generated SEQUENCE value either to the INSERT statement or to a natively compiled stored procedure that does the insert.</span></span> <span data-ttu-id="def7a-110">Dieses Muster wird im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="def7a-110">The following example demonstrates this pattern.</span></span>  
  
```sql  
-- Create a new In-Memory OLTP table to simulate IDENTITY insert  
-- Here the column C1 was the identity column in the original table  
--  
create table T1  
(  
  
[c1] integer not null primary key T1_c1 nonclustered,  
[c2] varchar(32) not null,  
[c3] datetime not null  
  
) with (memory_optimized = on)  
go  
  
-- This is a sequence provider that will give us values for column [c1]  
--  
create sequence usq_SequenceForT1 as integer start with 2 increment by 1  
go  
  
--   insert a sample row using the sequence  
--   note that a new value needs to be retrieved form   
--   the sequence object for every insert  
--  
declare @c1 integer = next value for [dbo].[usq_SequenceForT1]  
insert into T1 values (@c1, 'test', getdate())  
```  
  
 <span data-ttu-id="def7a-111">Nachdem Sie den Einfügevorgang mehrmals ausgeführt haben, stellen Sie fest, dass in Spalte [c1] monoton steigende Werte enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="def7a-111">After performing the insert several times, you see valid monotonically increasing values in column [c1].</span></span> <span data-ttu-id="def7a-112">Dieses Resultset wird mit dem Tabellenscan und dem Hashindex ohne `ORDER BY` generiert, sodass die Zeilen nicht sortiert sind.</span><span class="sxs-lookup"><span data-stu-id="def7a-112">This result set is generated using table scan and hash index without `ORDER BY` so the rows are not ordered.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="def7a-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="def7a-113">See Also</span></span>  
 [<span data-ttu-id="def7a-114">Migrieren zu In-Memory OLTP</span><span class="sxs-lookup"><span data-stu-id="def7a-114">Migrating to In-Memory OLTP</span></span>](migrating-to-in-memory-oltp.md)  
  
  
