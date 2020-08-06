---
title: Erstellen einer SQL-Anweisung (ODBC) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, statements
- statements [ODBC], constructing
- ODBC applications, statements
ms.assetid: 0acc71e2-8004-4dd8-8592-05c022bdd692
author: rothja
ms.author: jroth
ms.openlocfilehash: 1c454f936c49335555ca09b190e4d604c9fbad64
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608620"
---
# <a name="constructing-an-sql-statement-odbc"></a><span data-ttu-id="2f1eb-102">Erstellen einer SQL-Anweisung (ODBC)</span><span class="sxs-lookup"><span data-stu-id="2f1eb-102">Constructing an SQL Statement (ODBC)</span></span>
  <span data-ttu-id="2f1eb-103">In ODBC-Anwendungen werden fast alle Datenbankzugriffe mithilfe von [!INCLUDE[tsql](../../includes/tsql-md.md)]-Anweisungen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2f1eb-103">ODBC applications perform almost all of their database access by executing [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="2f1eb-104">Die Form dieser Anweisungen richtet sich nach den Anforderungen der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="2f1eb-104">The form of these statements depends on the application requirements.</span></span> <span data-ttu-id="2f1eb-105">SQL-Anweisungen können auf folgende Weise gebildet werden:</span><span class="sxs-lookup"><span data-stu-id="2f1eb-105">SQL statements can be constructed in the following ways:</span></span>  
  
-   <span data-ttu-id="2f1eb-106">Hartcodiert</span><span class="sxs-lookup"><span data-stu-id="2f1eb-106">Hard-coded</span></span>  
  
     <span data-ttu-id="2f1eb-107">Statische Anweisungen, die von einer Anwendung als feste Aufgabe ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2f1eb-107">Static statements performed by an application as a fixed task.</span></span>  
  
-   <span data-ttu-id="2f1eb-108">Zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="2f1eb-108">Constructed at run time</span></span>  
  
     <span data-ttu-id="2f1eb-109">SQL-Anweisungen, die zur Laufzeit gebildet werden und es den Benutzern ermöglichen, die Anweisung mit gängigen Klauseln wie SELECT, WHERE und ORDER BY anzupassen.</span><span class="sxs-lookup"><span data-stu-id="2f1eb-109">SQL statements constructed at run time that enable the user to tailor the statement by using common clauses, such as SELECT, WHERE, and ORDER BY.</span></span> <span data-ttu-id="2f1eb-110">Hierzu gehören auch von den Benutzern eingegebene Ad-hoc-Abfragen.</span><span class="sxs-lookup"><span data-stu-id="2f1eb-110">This includes ad hoc queries entered by users.</span></span>  
  
 <span data-ttu-id="2f1eb-111">Der- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Client-ODBC-Treiber analysiert SQL-Anweisungen nur für ODBC-und ISO-Syntax, die nicht direkt von unterstützt [!INCLUDE[ssDE](../../includes/ssde-md.md)] werden, die der Treiber transformiert [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2f1eb-111">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Client ODBC driver parses SQL statements only for ODBC and ISO syntax not directly supported by the [!INCLUDE[ssDE](../../includes/ssde-md.md)], which the driver transforms into [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="2f1eb-112">Jede andere SQL-Syntax wird wie vorliegend an das [!INCLUDE[ssDE](../../includes/ssde-md.md)] weitergeleitet, und [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] überprüft, ob sie in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="2f1eb-112">All other SQL syntax is passed to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] unchanged, where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will determine if it is valid [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="2f1eb-113">Dieser Ansatz hat zwei Vorteile:</span><span class="sxs-lookup"><span data-stu-id="2f1eb-113">This approach yields two benefits:</span></span>  
  
-   <span data-ttu-id="2f1eb-114">Geringerer Arbeitsaufwand</span><span class="sxs-lookup"><span data-stu-id="2f1eb-114">Reduced overhead</span></span>  
  
     <span data-ttu-id="2f1eb-115">Der Arbeitsaufwand des Treibers wird minimiert, weil er nur eine kleine Anzahl von ODBC- und ISO-Klauseln überprüfen muss.</span><span class="sxs-lookup"><span data-stu-id="2f1eb-115">Processing overhead for the driver is minimized because it only has to scan for a small set of ODBC and ISO clauses.</span></span>  
  
-   <span data-ttu-id="2f1eb-116">Flexibilität</span><span class="sxs-lookup"><span data-stu-id="2f1eb-116">Flexibility</span></span>  
  
     <span data-ttu-id="2f1eb-117">Programmierer können die Portabilität ihrer Anwendungen anpassen.</span><span class="sxs-lookup"><span data-stu-id="2f1eb-117">Programmers can tailor the portability of their applications.</span></span> <span data-ttu-id="2f1eb-118">Um die Portabilität für mehrere Datenbanken zu verbessern, verwenden Sie primär die ODBC- und ISO-Syntax.</span><span class="sxs-lookup"><span data-stu-id="2f1eb-118">To enhance portability against multiple databases, use primarily ODBC and ISO syntax.</span></span> <span data-ttu-id="2f1eb-119">Um die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-spezifischen Erweiterungen zu verwenden, verwenden Sie die entsprechende [!INCLUDE[tsql](../../includes/tsql-md.md)]-Syntax.</span><span class="sxs-lookup"><span data-stu-id="2f1eb-119">To use enhancements specific to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], use the appropriate [!INCLUDE[tsql](../../includes/tsql-md.md)] syntax.</span></span> <span data-ttu-id="2f1eb-120">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-ODBC-Treiber unterstützt die vollständige [!INCLUDE[tsql](../../includes/tsql-md.md)] Syntax, damit ODBC-basierte Anwendungen alle Funktionen in nutzen können [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2f1eb-120">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports the complete [!INCLUDE[tsql](../../includes/tsql-md.md)] syntax so ODBC-based applications can take advantage of all the features in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="2f1eb-121">Die Spaltenliste der SELECT-Anweisung sollte nur die Spalten enthalten, die zur Ausführung der aktuellen Aufgabe erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="2f1eb-121">The column list in a SELECT statement should contain only the columns required to perform the current task.</span></span> <span data-ttu-id="2f1eb-122">Dadurch werden nicht nur weniger Daten über das Netzwerk gesendet, sondern Datenbankänderungen wirken sich in geringerem Umfang auf die Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="2f1eb-122">Not only does this reduce the amount of data sent across the network, but also it reduces the effect of database changes on the application.</span></span> <span data-ttu-id="2f1eb-123">Wenn eine Anwendung nicht auf eine Spalte einer Tabelle verweist, dann ist die Anwendung von keinerlei Änderungen betroffen, die an dieser Spalte vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="2f1eb-123">If an application does not reference a column from a table, then the application is not affected by any changes made to that column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f1eb-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2f1eb-124">See Also</span></span>  
 [<span data-ttu-id="2f1eb-125">Ausführen von Abfragen &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="2f1eb-125">Executing Queries &#40;ODBC&#41;</span></span>](executing-queries-odbc.md)  
  
  
