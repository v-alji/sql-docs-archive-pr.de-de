---
title: Verwenden von sp_rename zum Umbenennen des Namens eines doppelten Indexes | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- table names [SQL Server]
- duplicate table names
- index names [SQL Server]
- sp_rename
- duplicate index names
ms.assetid: ee66c7a5-eb6d-4fcf-970c-ab099d78c8d9
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: b8ffe3b9befd0c7239d32094e5738e0fb2947c5a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726442"
---
# <a name="use-sp_rename-to-rename-duplicate-index-name"></a><span data-ttu-id="d53f2-102">Verwenden Sie bei doppelten Indexnamen 'sp_rename' zum Umbenennen</span><span class="sxs-lookup"><span data-stu-id="d53f2-102">Use sp_rename to rename duplicate index name</span></span>
  <span data-ttu-id="d53f2-103">Der Upgrade Advisor hat doppelte Tabellen- oder Sichtindexnamen erkannt.</span><span class="sxs-lookup"><span data-stu-id="d53f2-103">Upgrade Advisor has detected duplicate table or view index names.</span></span> <span data-ttu-id="d53f2-104">Vor dem Upgrade müssen Sie die Indizes umbenennen, um Duplikate zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="d53f2-104">Rename the indexes to remove duplicates before upgrading.</span></span>  
  
## <a name="component"></a><span data-ttu-id="d53f2-105">Komponente</span><span class="sxs-lookup"><span data-stu-id="d53f2-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="d53f2-106">Korrekturmaßnahme</span><span class="sxs-lookup"><span data-stu-id="d53f2-106">Corrective Action</span></span>  
  
1.  <span data-ttu-id="d53f2-107">Suchen Sie die doppelten Indizes durch Ausführen der folgenden Abfrage.</span><span class="sxs-lookup"><span data-stu-id="d53f2-107">Locate the duplicate indexes by executing the following query.</span></span>  
  
    ```  
    SELECT DISTINCT OBJECT_NAME(o.id), name  
    FROM sysindexes as o  
    WHERE EXISTS   
        (SELECT name FROM sysindexes  as i  
          WHERE i.id = o.id  
          AND i.name = o.name and i.indid < o.indid);  
    ```  
  
2.  <span data-ttu-id="d53f2-108">Verwenden Sie **sp_rename** , um einen der Indexnamen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="d53f2-108">Use **sp_rename** to change one of the index names.</span></span> <span data-ttu-id="d53f2-109">Da die Indexnamen identisch sind, können Sie nicht bestimmen, welcher Index umbenannt wird.</span><span class="sxs-lookup"><span data-stu-id="d53f2-109">Because the index names are the same, you cannot determine which index will be renamed.</span></span> <span data-ttu-id="d53f2-110">Durch diesen Schritt können Sie die Indizes unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="d53f2-110">This step allows you to differentiate the indexes.</span></span>  
  
    ```  
    EXEC sp_rename N'table_name.index_name', N'new_index_name', N'INDEX'  
    ```  
  
3.  <span data-ttu-id="d53f2-111">Überprüfen Sie durch Ausführen der folgenden Abfrage, welcher Index umbenannt wurde.</span><span class="sxs-lookup"><span data-stu-id="d53f2-111">Verify which index was renamed by executing the following query.</span></span> <span data-ttu-id="d53f2-112">Diese Abfrage gibt alle Indizes (einschließlich der Schlüsselspaltennamen) für die angegebene Tabelle oder Sicht zurück.</span><span class="sxs-lookup"><span data-stu-id="d53f2-112">This query returns all indexes (including key column names) on the specified table or view.</span></span>  
  
    ```  
    SELECT i.name AS IndexName, c.name AS ColumnName, ik.colid, ik.keyno  
    FROM sysindexes i  
    JOIN sysindexkeys ik ON i.id = ik.id and i.indid = ik.indid   
    JOIN syscolumns c ON c.id = ik.id and ik.colid = c.colid  
    WHERE i.id = OBJECT_ID('table_or_view_name')  
    ```  
  
4.  <span data-ttu-id="d53f2-113">Verwenden Sie ggf. **sp_rename** erneut, um die Indexnamen zu korrigieren.</span><span class="sxs-lookup"><span data-stu-id="d53f2-113">If necessary, use **sp_rename** again to correct the index names.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d53f2-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d53f2-114">See Also</span></span>  
 <span data-ttu-id="d53f2-115">[Datenbank-Engine Upgradeprobleme](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="d53f2-115">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="d53f2-116">SQL Server 2014 Upgrade Advisor &#91;neuen&#93;</span><span class="sxs-lookup"><span data-stu-id="d53f2-116">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
