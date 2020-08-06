---
title: Legen Sie die Sortierung benutzerdefinierter Datenbanken so fest, dass Sie mit denen der Master-und Model-Datenbanken identisch sind. Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: c686446f-dae1-4b05-a3df-837b3422988d
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: b48696fb56c40062d62f04845715170887f84fda
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696025"
---
# <a name="set-the-collation-of-user-defined-databases-to-match-those-of-the-master-and-model-databases"></a><span data-ttu-id="3fa31-102">Festlegen der Sortierung benutzerdefinierter Datenbanken übereinstimmend zu jener der master- und model-Datenbanken</span><span class="sxs-lookup"><span data-stu-id="3fa31-102">Set the Collation of User-defined Databases to Match Those of the master and model Databases</span></span>
  <span data-ttu-id="3fa31-103">Diese Regel überprüft, ob benutzerdefinierte Datenbanken unter Verwendung einer Datenbanksortierung definiert sind, die mit der Sortierung der master- oder model-Datenbank übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="3fa31-103">This rule checks whether user-defined databases are defined by using a database collation that is the same as the collation for master or model.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="3fa31-104">Empfehlungen zu Best Practices</span><span class="sxs-lookup"><span data-stu-id="3fa31-104">Best Practices Recommendations</span></span>  
 <span data-ttu-id="3fa31-105">Es wird empfohlen, dass die Sortierungen benutzerdefinierter Datenbanken mit der Sortierung der Datenbanken 'master' oder 'model' übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="3fa31-105">We recommend that the collations of user-defined databases match the collation of master or model.</span></span> <span data-ttu-id="3fa31-106">Andernfalls können Sortierungskonflikte auftreten, die verhindern könnten, dass Code ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3fa31-106">Otherwise, collation conflicts can occur that might prevent code from executing.</span></span> <span data-ttu-id="3fa31-107">Wenn beispielsweise eine gespeicherte Prozedur eine Tabelle mit einer temporären Tabelle verknüpft und die Sortierungen der benutzerdefinierten Datenbank und der model-Datenbank unterschiedlich sind, kann [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] den Batch beenden und einen Sortierungskonfliktfehler zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="3fa31-107">For example, when a stored procedure joins one table to a temporary table, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] might end the batch and return a collation conflict error if the collations of the user-defined database and the model database are different.</span></span> <span data-ttu-id="3fa31-108">Dies ist darauf zurückzuführen, dass temporäre Tabellen in der tempdb-Datenbank erstellt werden, deren Sortierung auf der der model-Datenbank basiert.</span><span class="sxs-lookup"><span data-stu-id="3fa31-108">This occurs because temporary tables are created in tempdb, which bases its collation on that of model.</span></span>  
  
 <span data-ttu-id="3fa31-109">Wenn Sortierungskonfliktfehler auftreten, ziehen Sie eine der folgenden Lösungen in Betracht:</span><span class="sxs-lookup"><span data-stu-id="3fa31-109">If you experience collation conflict errors, consider one of the following solutions:</span></span>  
  
-   <span data-ttu-id="3fa31-110">Exportieren Sie die Daten aus der Benutzerdatenbank, und importieren Sie sie in neue Tabellen, die dieselbe Sortierung aufweisen wie die master- und model-Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="3fa31-110">Export the data from the user database and import it into new tables that have the same collation as the master and model databases.</span></span>  
  
-   <span data-ttu-id="3fa31-111">Erstellen Sie die Systemdatenbanken so neu, dass sie eine Sortierung verwenden, die mit der Sortierung der Benutzerdatenbank übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="3fa31-111">Rebuild the system databases to use a collation that matches the user database collation.</span></span> <span data-ttu-id="3fa31-112">Weitere Informationen zum Neuerstellen der System Datenbanken finden Sie unter [Neuerstellen von System Datenbanken](../relational-databases/databases/system-databases.md).</span><span class="sxs-lookup"><span data-stu-id="3fa31-112">For more information about how to rebuild the system databases, see [Rebuild System Databases](../relational-databases/databases/system-databases.md).</span></span>  
  
-   <span data-ttu-id="3fa31-113">Ändern Sie alle gespeicherten Prozeduren, die Benutzertabellen mit Tabellen in der tempdb-Datenbank verknüpfen so, dass die Tabellen in der tempdb-Datenbank unter Verwendung der Sortierung der Benutzerdatenbank erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="3fa31-113">Modify any stored procedures that join user tables to tables in tempdb to create the tables in tempdb by using the collation of the user database.</span></span> <span data-ttu-id="3fa31-114">Fügen Sie zu diesem Zweck den Spaltendefinitionen der temporären Tabelle die Klausel `COLLATE database_default` hinzu, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="3fa31-114">To do this, add the `COLLATE database_default` clause to the column definitions of the temporary table, as shown in the following example:</span></span>  
  
    ```  
    CREATE TABLE #temp1 ( c1 int, c2 varchar(30) COLLATE database_default )  
    ```  
  
## <a name="for-more-information"></a><span data-ttu-id="3fa31-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3fa31-115">For More Information</span></span>  
 [<span data-ttu-id="3fa31-116">Festlegen oder Ändern der Datenbanksortierung</span><span class="sxs-lookup"><span data-stu-id="3fa31-116">Set or Change the Database Collation</span></span>](../relational-databases/collations/set-or-change-the-database-collation.md)  
  
 [<span data-ttu-id="3fa31-117">Festlegen oder Ändern der Spaltensortierung</span><span class="sxs-lookup"><span data-stu-id="3fa31-117">Set or Change the Column Collation</span></span>](../relational-databases/collations/set-or-change-the-column-collation.md)  
  
 [<span data-ttu-id="3fa31-118">ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3fa31-118">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
 [<span data-ttu-id="3fa31-119">COLLATE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3fa31-119">COLLATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/collations)  
  
 [<span data-ttu-id="3fa31-120">sys.databases &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3fa31-120">sys.databases &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql)  
  
 [<span data-ttu-id="3fa31-121">Microsoft Knowledge Base-Artikel 325335</span><span class="sxs-lookup"><span data-stu-id="3fa31-121">Microsoft Knowledge Base article 325335</span></span>](https://go.microsoft.com/fwlink/?linkid=117751)  
  
 [<span data-ttu-id="3fa31-122">Vorgehensweise: Installieren von SQL Server 2008 von der Eingabeaufforderung</span><span class="sxs-lookup"><span data-stu-id="3fa31-122">How to: Install SQL Server 2008 from the Command Prompt</span></span>](https://go.microsoft.com/fwlink/?LinkId=81585)  
  
## <a name="see-also"></a><span data-ttu-id="3fa31-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3fa31-123">See Also</span></span>  
 [<span data-ttu-id="3fa31-124">Überwachen und Erzwingen von Best Practices mit der richtlinienbasierten Verwaltung</span><span class="sxs-lookup"><span data-stu-id="3fa31-124">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](../relational-databases/policy-based-management/monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
