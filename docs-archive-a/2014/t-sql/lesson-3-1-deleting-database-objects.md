---
title: Löschen von Datenbankobjekten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- deleting database objects
ms.assetid: dbb94fdf-c85b-477b-8e84-f830d259bade
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 6bd69935dbfac020c4c75bb391e7932009fd4197
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608999"
---
# <a name="deleting-database-objects"></a><span data-ttu-id="0e8cd-102">Löschen von Datenbankobjekten</span><span class="sxs-lookup"><span data-stu-id="0e8cd-102">Deleting Database Objects</span></span>
  <span data-ttu-id="0e8cd-103">Sie könnten einfach nur die Datenbank löschen, um dieses Lernprogramm vollständig zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="0e8cd-103">To remove all traces of this tutorial, you could just delete the database.</span></span> <span data-ttu-id="0e8cd-104">In diesem Thema führen Sie jedoch die erforderlichen Schritte aus, um jede Aktion rückgängig zu machen, die Sie im Lernprogramm ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="0e8cd-104">However, in this topic, you will go through the steps to reverse every action you took doing the tutorial.</span></span>  
  
### <a name="removing-permissions-and-objects"></a><span data-ttu-id="0e8cd-105">Entfernen von Berechtigungen und Objekten</span><span class="sxs-lookup"><span data-stu-id="0e8cd-105">Removing permissions and objects</span></span>  
  
1.  <span data-ttu-id="0e8cd-106">Bevor Sie Objekte löschen, stellen Sie sicher, dass Sie sich in der richtigen Datenbank befinden:</span><span class="sxs-lookup"><span data-stu-id="0e8cd-106">Before you delete objects, make sure you are in the correct database:</span></span>  
  
    ```  
    USE TestData;  
    GO  
    ```  
  
2.  <span data-ttu-id="0e8cd-107">Führen Sie die `REVOKE` -Anweisung aus, um die Ausführungsberechtigung für `Mary` in der gespeicherten Prozedur zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="0e8cd-107">Use the `REVOKE` statement to remove execute permission for `Mary` on the stored procedure:</span></span>  
  
    ```  
    REVOKE EXECUTE ON pr_Names FROM Mary;  
    GO  
  
    ```  
  
3.  <span data-ttu-id="0e8cd-108">Führen Sie die `DROP` -Anweisung aus, um die Berechtigung für `Mary` zum Zugriff auf die `TestData` -Datenbank zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="0e8cd-108">Use the `DROP` statement to remove permission for `Mary` to access the `TestData` database:</span></span>  
  
    ```  
    DROP USER Mary;  
    GO  
  
    ```  
  
4.  <span data-ttu-id="0e8cd-109">Führen Sie die `DROP` -Anweisung aus, um die Berechtigung für `Mary` zum Zugriff auf die Instanz von [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)]zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="0e8cd-109">Use the `DROP` statement to remove permission for `Mary` to access this instance of [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)]:</span></span>  
  
    ```  
    DROP LOGIN [<computer_name>\Mary];  
    GO  
  
    ```  
  
5.  <span data-ttu-id="0e8cd-110">Verwenden Sie die `DROP` -Anweisung zum Entfernen der gespeicherten Prozedur `pr_Names`:</span><span class="sxs-lookup"><span data-stu-id="0e8cd-110">Use the `DROP` statement to remove the store procedure `pr_Names`:</span></span>  
  
    ```  
    DROP PROC pr_Names;  
    GO  
  
    ```  
  
6.  <span data-ttu-id="0e8cd-111">Verwenden Sie die `DROP` -Anweisung zum Entfernen der `vw_Names`-Sicht:</span><span class="sxs-lookup"><span data-stu-id="0e8cd-111">Use the `DROP` statement to remove the view `vw_Names`:</span></span>  
  
    ```  
    DROP View vw_Names;  
    GO  
  
    ```  
  
7.  <span data-ttu-id="0e8cd-112">Verwenden Sie die `DELETE` -Anweisung zum Entfernen von Datenzeilen aus der `Products` -Tabelle:</span><span class="sxs-lookup"><span data-stu-id="0e8cd-112">Use the `DELETE` statement to remove all rows from the `Products` table:</span></span>  
  
    ```  
    DELETE FROM Products;  
    GO  
  
    ```  
  
8.  <span data-ttu-id="0e8cd-113">Verwenden Sie die `DROP` -Anweisung zum Entfernen der `Products` -Tabelle:</span><span class="sxs-lookup"><span data-stu-id="0e8cd-113">Use the `DROP` statement to remove the `Products` table:</span></span>  
  
    ```  
    DROP Table Products;  
    GO  
  
    ```  
  
9. <span data-ttu-id="0e8cd-114">Es ist nicht möglich, die `TestData` -Datenbank zu entfernen, während Sie sich in der Datenbank befinden. Wechseln Sie daher den Kontext zu einer anderen Datenbank, und verwenden Sie dann die `DROP` -Anweisung, um die `TestData` -Datenbank zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="0e8cd-114">You cannot remove the `TestData` database while you are in the database; therefore, first switch context to another database, and then use the `DROP` statement to remove the `TestData` database:</span></span>  
  
    ```  
    USE MASTER;  
    GO  
    DROP DATABASE TestData;  
    GO  
  
    ```  
  
 <span data-ttu-id="0e8cd-115">Damit ist das Lernprogramm zum Schreiben von [!INCLUDE[tsql](../includes/tsql-md.md)] -Anweisungen beendet.</span><span class="sxs-lookup"><span data-stu-id="0e8cd-115">This concludes the Writing [!INCLUDE[tsql](../includes/tsql-md.md)] Statements tutorial.</span></span> <span data-ttu-id="0e8cd-116">Beachten Sie, dass dieses Lernprogramm nur eine kurze Übersicht bietet und darin nicht alle Optionen der verwendeten Anweisungen beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="0e8cd-116">Remember, this tutorial is a brief overview and it does not describe all the options to the statements that are used.</span></span> <span data-ttu-id="0e8cd-117">Das Entwerfen und Erstellen einer effizienten Datenbankstruktur und das Konfigurieren des sicheren Zugriffs auf die Daten erfordern eine komplexere Datenbank als in diesem Lernprogramm gezeigt.</span><span class="sxs-lookup"><span data-stu-id="0e8cd-117">Designing and creating an efficient database structure and configuring secure access to the data requires a more complex database than that shown in this tutorial.</span></span>  
  
## <a name="return-to-sql-server-tools-portal"></a><span data-ttu-id="0e8cd-118">Zurück zum Portal für SQL Server-Tools</span><span class="sxs-lookup"><span data-stu-id="0e8cd-118">Return to SQL Server Tools Portal</span></span>  
 [<span data-ttu-id="0e8cd-119">Tutorial: Schreiben von Transact-SQL-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="0e8cd-119">Tutorial: Writing Transact-SQL Statements</span></span>](tutorial-writing-transact-sql-statements.md)  
  
## <a name="see-also"></a><span data-ttu-id="0e8cd-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0e8cd-120">See Also</span></span>  
 <span data-ttu-id="0e8cd-121">[REVOKE &#40;Transact-SQL&#41;](/sql/t-sql/statements/revoke-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0e8cd-121">[REVOKE &#40;Transact-SQL&#41;](/sql/t-sql/statements/revoke-transact-sql) </span></span>  
 <span data-ttu-id="0e8cd-122">[DROP USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-user-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0e8cd-122">[DROP USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-user-transact-sql) </span></span>  
 <span data-ttu-id="0e8cd-123">[Drop Login &#40;Transact-SQL-&#41;](/sql/t-sql/statements/drop-login-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0e8cd-123">[DROP LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-login-transact-sql) </span></span>  
 <span data-ttu-id="0e8cd-124">[DROP PROCEDURE &#40;Transact-SQL-&#41;](/sql/t-sql/statements/drop-procedure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0e8cd-124">[DROP PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-procedure-transact-sql) </span></span>  
 <span data-ttu-id="0e8cd-125">[DROP VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-view-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0e8cd-125">[DROP VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-view-transact-sql) </span></span>  
 <span data-ttu-id="0e8cd-126">[DELETE &#40;Transact-SQL&#41;](/sql/t-sql/statements/delete-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0e8cd-126">[DELETE &#40;Transact-SQL&#41;](/sql/t-sql/statements/delete-transact-sql) </span></span>  
 <span data-ttu-id="0e8cd-127">[DROP TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-table-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0e8cd-127">[DROP TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-table-transact-sql) </span></span>  
 [<span data-ttu-id="0e8cd-128">DROP DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0e8cd-128">DROP DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-database-audit-specification-transact-sql)  
  
  
