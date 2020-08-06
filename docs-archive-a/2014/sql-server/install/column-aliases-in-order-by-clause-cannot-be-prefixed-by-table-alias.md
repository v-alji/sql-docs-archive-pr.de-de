---
title: Spalten Aliasen in der ORDER BY-Klausel können keinen Tabellenalias als Präfix aufweisen. Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- aliases [SQL Server], columns
ms.assetid: fee7328f-6e8d-4005-930b-56fb6f17e0b2
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 44333d778753a2f8761d32d181681b798e3bc409
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617493"
---
# <a name="column-aliases-in-order-by-clause-cannot-be-prefixed-by-table-alias"></a><span data-ttu-id="3e5a6-102">Spaltenaliase in ORDER BY-Klauseln können nicht vom Tabellenalias als Präfix verwendet werden</span><span class="sxs-lookup"><span data-stu-id="3e5a6-102">Column aliases in ORDER BY clause cannot be prefixed by table alias</span></span>
  <span data-ttu-id="3e5a6-103">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] oder höher können Spaltenaliase in ORDER BY-Klauseln nicht vom Tabellenalias als Präfix verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3e5a6-103">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or later, column aliases in the ORDER BY clause cannot be prefixed by the table alias.</span></span>  
  
## <a name="component"></a><span data-ttu-id="3e5a6-104">Komponente</span><span class="sxs-lookup"><span data-stu-id="3e5a6-104">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="3e5a6-105">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3e5a6-105">Description</span></span>  
 <span data-ttu-id="3e5a6-106">Die folgende Abfrage wird z. B. in [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] ausgeführt, gibt in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] jedoch einen Fehler zurück</span><span class="sxs-lookup"><span data-stu-id="3e5a6-106">For example, the following query executes in [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], but returns an error in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT FirstName AS f, LastName AS l  
FROM Person.Contact p  
ORDER BY p.l  
```  
  
 <span data-ttu-id="3e5a6-107">[!INCLUDE[ssDEversion10](../../includes/ssdeversion10-md.md)] ordnet `p.l` in der `ORDER BY`-Klausel keiner gültigen Spalte in der Tabelle zu.</span><span class="sxs-lookup"><span data-stu-id="3e5a6-107">The [!INCLUDE[ssDEversion10](../../includes/ssdeversion10-md.md)] does not match `p.l` in the `ORDER BY` clause to a valid column in the table.</span></span>  
  
### <a name="exception"></a><span data-ttu-id="3e5a6-108">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="3e5a6-108">Exception</span></span>  
 <span data-ttu-id="3e5a6-109">Wenn der in der ORDER BY-Klausel vorangestellte Spaltenalias ein gültiger Spaltenname in der angegebenen Tabelle ist, wird die Abfrage ohne Fehler ausgeführt. In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] kann die Semantik der Anweisung unterschiedlich sein.</span><span class="sxs-lookup"><span data-stu-id="3e5a6-109">If the prefixed column alias that is specified in the ORDER BY clause is a valid column name in the specified table, the query executes without error; in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], the semantics of the statement might be different.</span></span> <span data-ttu-id="3e5a6-110">So ist der Spaltenalias (`id`) in der folgenden Anweisung beispielsweise ein gültiger Spaltenname in der `sysobjects`-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="3e5a6-110">For example, the column alias (`id`) specified in the following statement is a valid column name in the `sysobjects` table.</span></span> <span data-ttu-id="3e5a6-111">In [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] wird der `CAST`-Vorgang beim Ausführen der Anweisung durchgeführt, nachdem das Resultset sortiert wurde.</span><span class="sxs-lookup"><span data-stu-id="3e5a6-111">In [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], when the statement executes, the `CAST` operation is performed after the result set is sorted.</span></span> <span data-ttu-id="3e5a6-112">Dies bedeutet, dass die `name`-Spalte im Sortiervorgang verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3e5a6-112">This means the `name` column is used in the sort operation.</span></span> <span data-ttu-id="3e5a6-113">In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] wird der `CAST`-Vorgang vor dem Sortiervorgang ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="3e5a6-113">In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], the `CAST` operation occurs before the sort operation.</span></span> <span data-ttu-id="3e5a6-114">Dies bedeutet, dass die `id`-Spalte der Tabelle im Sortiervorgang verwendet wird und das Resultset in einer unerwarteten Reihenfolge zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="3e5a6-114">This means the `id` column in the table is used in the sort operation and returns the result set in an unexpected order.</span></span>  
  
```  
SELECT CAST (o.name AS char(128)) AS id  
FROM sysobjects AS o  
ORDER BY o.id;  
```  
  
## <a name="corrective-action"></a><span data-ttu-id="3e5a6-115">Korrekturmaßnahme</span><span class="sxs-lookup"><span data-stu-id="3e5a6-115">Corrective Action</span></span>  
 <span data-ttu-id="3e5a6-116">Ändern Sie die Abfragen, die Spaltenaliase mit vorangestellten Tabellenaliasen in der ORDER BY-Klausel verwenden, auf eine der folgenden Arten:</span><span class="sxs-lookup"><span data-stu-id="3e5a6-116">Modify queries that use column aliases prefixed by table aliases in the ORDER BY clause in either of the following ways:</span></span>  
  
-   <span data-ttu-id="3e5a6-117">Stellen Sie in der ORDER BY-Klausel nach Möglichkeit kein Präfix vor den Spaltenalias.</span><span class="sxs-lookup"><span data-stu-id="3e5a6-117">Do not prefix the column alias in the ORDER BY clause, if possible.</span></span>  
  
-   <span data-ttu-id="3e5a6-118">Ersetzen Sie den Spaltenalias durch den Spaltennamen.</span><span class="sxs-lookup"><span data-stu-id="3e5a6-118">Replace the column alias with the column name.</span></span>  
  
 <span data-ttu-id="3e5a6-119">Die beiden folgenden Abfragen werden in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] beispielsweise ohne Fehler ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="3e5a6-119">For example, both of the following queries execute without error in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT FirstName AS f, LastName AS l  
FROM Person.Contact p  
ORDER BY l  
  
USE AdventureWorks2012;  
GO  
SELECT FirstName AS f, LastName AS l  
FROM Person.Contact p  
ORDER BY p.LastName  
```  
  
## <a name="see-also"></a><span data-ttu-id="3e5a6-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3e5a6-120">See Also</span></span>  
 <span data-ttu-id="3e5a6-121">[Datenbank-Engine Upgradeprobleme](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="3e5a6-121">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="3e5a6-122">SQL Server 2014 Upgrade Advisor &#91;neuen&#93;</span><span class="sxs-lookup"><span data-stu-id="3e5a6-122">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
