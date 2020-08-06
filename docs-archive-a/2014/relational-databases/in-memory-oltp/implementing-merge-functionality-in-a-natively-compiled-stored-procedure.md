---
title: Implementieren von Merge-Funktionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: d4bcdc36-3302-4abc-9b35-64ec2b920986
author: rothja
ms.author: jroth
ms.openlocfilehash: 8c2e2d3f0796396c0f3f451215f1fd685979a842
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616559"
---
# <a name="implementing-merge-functionality"></a><span data-ttu-id="daff5-102">Implementieren von MERGE-Funktionalität</span><span class="sxs-lookup"><span data-stu-id="daff5-102">Implementing MERGE Functionality</span></span>
  <span data-ttu-id="daff5-103">Eine Datenbank muss u. U. einen Einfüge- oder einen Updatevorgang ausführen, je nachdem, ob eine bestimmte Zeile in der Datenbank bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="daff5-103">A database may need to perform either an insert of an update, depending on whether a particular row already exists in the database.</span></span>  
  
 <span data-ttu-id="daff5-104">Ohne Verwendung der `MERGE`-Anweisung kann der folgende Ansatz in [!INCLUDE[tsql](../../includes/tsql-md.md)] verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="daff5-104">Without using the `MERGE` statement, the following is one approach you can use in [!INCLUDE[tsql](../../includes/tsql-md.md)]:</span></span>  
  
```sql  
UPDATE mytable SET col=@somevalue WHERE myPK = @parm  
IF @@ROWCOUNT = 0  
    INSERT mytable (columns) VALUES (@parm, @other values)  
```  
  
 <span data-ttu-id="daff5-105">Eine weitere [!INCLUDE[tsql](../../includes/tsql-md.md)] -Methode zum Implementieren eines Merge:</span><span class="sxs-lookup"><span data-stu-id="daff5-105">Another [!INCLUDE[tsql](../../includes/tsql-md.md)] method to implement a merge:</span></span>  
  
```sql  
IF EXISTS (SELECT 1 FROM mytable WHERE myPK = @parm)  
    UPDATE....  
ELSE  
    INSERT  
```  
  
 <span data-ttu-id="daff5-106">Für eine systemintern kompilierte gespeicherte Prozedur</span><span class="sxs-lookup"><span data-stu-id="daff5-106">For a natively compiled stored procedure</span></span>  
  
```sql  
DECLARE @i  int  = 0  -- or whatever your PK data type is  
UPDATE mytable SET @i=myPK, othercolums = other values WHERE myPK = @parm  
IF @i = 0  
   INSERT....  
```  
  
## <a name="see-also"></a><span data-ttu-id="daff5-107">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="daff5-107">See Also</span></span>  
 <span data-ttu-id="daff5-108">[Migrationsprobleme bei systemintern kompilierten gespeicherten Prozeduren](migration-issues-for-natively-compiled-stored-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="daff5-108">[Migration Issues for Natively Compiled Stored Procedures](migration-issues-for-natively-compiled-stored-procedures.md) </span></span>  
 [<span data-ttu-id="daff5-109">Von In-Memory OLTP nicht unterstützte Transact-SQL-Konstrukte.</span><span class="sxs-lookup"><span data-stu-id="daff5-109">Transact-SQL Constructs Not Supported by In-Memory OLTP</span></span>](transact-sql-constructs-not-supported-by-in-memory-oltp.md)  
  
  
