---
title: Einrichten der TRUSTWORTHY-Eigenschaft für eine Spiegeldatenbank (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- TRUSTWORTHY database option
- mirror database [SQL Server]
- database mirroring [SQL Server], security
ms.assetid: 6993b076-78ef-453e-b0ea-e341b8e5ee3e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6cd46a08037bcb6eee178a96d84bdab358e5350d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701762"
---
# <a name="set-up-a-mirror-database-to-use-the-trustworthy-property-transact-sql"></a><span data-ttu-id="36780-102">Einrichten der TRUSTWORTHY-Eigenschaft für eine Spiegeldatenbank (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="36780-102">Set Up a Mirror Database to Use the Trustworthy Property (Transact-SQL)</span></span>
  <span data-ttu-id="36780-103">Beim Sichern einer Datenbank wird die TRUSTWORTHY-Datenbankeigenschaft auf OFF festgelegt.</span><span class="sxs-lookup"><span data-stu-id="36780-103">When a database is backed up, the TRUSTWORTHY database property is set to OFF.</span></span> <span data-ttu-id="36780-104">Deshalb ist TRUSTWORTHY bei einer neuen Spiegeldatenbank immer auf OFF festgelegt.</span><span class="sxs-lookup"><span data-stu-id="36780-104">Therefore, on a new mirror database TRUSTWORTHY is always OFF.</span></span> <span data-ttu-id="36780-105">Muss die Datenbank nach einem Failover vertrauenswürdig sein, sind zusätzliche Installationsschritte nach dem Beginn der Spiegelung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="36780-105">If the database needs to be trustworthy after a failover, extra setup steps are necessary after mirroring begins.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="36780-106">Informationen zu dieser Datenbankeigenschaft finden Sie unter [TRUSTWORTHY-Datenbankeigenschaft](../../relational-databases/security/trustworthy-database-property.md).</span><span class="sxs-lookup"><span data-stu-id="36780-106">For information about this database property, see [TRUSTWORTHY Database Property](../../relational-databases/security/trustworthy-database-property.md).</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="36780-107">Verfahren</span><span class="sxs-lookup"><span data-stu-id="36780-107">Procedure</span></span>  
  
#### <a name="to-setup-a-mirror-database-to-use-the-trustworthy-property"></a><span data-ttu-id="36780-108">So richten Sie die TRUSTWORTHY-Eigenschaft für eine Spiegeldatenbank ein</span><span class="sxs-lookup"><span data-stu-id="36780-108">To setup a mirror database to use the Trustworthy Property</span></span>  
  
1.  <span data-ttu-id="36780-109">Stellen Sie auf der Prinzipalserverinstanz sicher, dass die TRUSTWORTHY-Eigenschaft für die Prinzipaldatenbank aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="36780-109">On the principal server instance, verify that the principal database has the Trustworthy property turned on.</span></span>  
  
    ```  
    SELECT name, database_id, is_trustworthy_on FROM sys.databases   
    ```  
  
     <span data-ttu-id="36780-110">Weitere Informationen finden Sie unter [sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="36780-110">For more information, see [sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql).</span></span>  
  
2.  <span data-ttu-id="36780-111">Stellen Sie nach dem Beginn der Spiegelung sicher, dass die Datenbank derzeit die Prinzipaldatenbank ist, die Sitzung derzeit im synchronen Betriebsmodus ausgeführt wird und die Sitzung bereits synchronisiert ist.</span><span class="sxs-lookup"><span data-stu-id="36780-111">After starting mirroring, verify that the database is currently the principal database, the session is using a synchronous operating mode, and the session is already synchronized.</span></span>  
  
    ```  
    SELECT database_id, mirroring_role, mirroring_safety_level_desc, mirroring_state_desc FROM sys.database_mirroring  
    ```  
  
     <span data-ttu-id="36780-112">Weitere Informationen finden Sie unter [sys.database_mirroring &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-mirroring-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="36780-112">For more information, see [sys.database_mirroring &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-mirroring-transact-sql).</span></span>  
  
3.  <span data-ttu-id="36780-113">Nach dem Synchronisieren der Spiegelungssitzung führen Sie manuell ein Failover zur Spiegeldatenbank aus.</span><span class="sxs-lookup"><span data-stu-id="36780-113">Once the mirroring session is synchronized, manually fail over to the mirror database.</span></span>  
  
     <span data-ttu-id="36780-114">Dies ist entweder mithilfe von SQL Server Management Studio oder Transact-SQL möglich:</span><span class="sxs-lookup"><span data-stu-id="36780-114">This can be done in either SQL Server Management Studio or using Transact-SQL:</span></span>  
  
    -   [<span data-ttu-id="36780-115">Manueller Failover für eine Datenbank-Spiegelungssitzung &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="36780-115">Manually Fail Over a Database Mirroring Session &#40;SQL Server Management Studio&#41;</span></span>](manually-fail-over-a-database-mirroring-session-sql-server-management-studio.md)  
  
    -   [<span data-ttu-id="36780-116">Ausführen des manuellen Failovers einer Datenbank-Spiegelungssitzung &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="36780-116">Manually Fail Over a Database Mirroring Session &#40;Transact-SQL&#41;</span></span>](manually-fail-over-a-database-mirroring-session-transact-sql.md)  
  
4.  <span data-ttu-id="36780-117">Aktivieren Sie die TRUSTWORTHY-Datenbankeigenschaft mithilfe des folgenden ALTER DATABASE-Befehls:</span><span class="sxs-lookup"><span data-stu-id="36780-117">Turn on the trustworthy database property using the following ALTER DATABASE command:</span></span>  
  
    ```  
    ALTER DATABASE <database_name> SET TRUSTWORTHY ON  
    ```  
  
     <span data-ttu-id="36780-118">Weitere Informationen finden Sie unter [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="36780-118">For more information, see[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
5.  <span data-ttu-id="36780-119">Führen Sie optional erneut ein Failover aus, um zur ursprünglichen Prinzipaldatenbank zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="36780-119">Optionally, manually failover again to return to the original principal.</span></span>  
  
6.  <span data-ttu-id="36780-120">Wechseln Sie optional in den asynchronen Modus für hohe Leistung, indem Sie SAFETY auf OFF festlegen und sicherstellen, dass WITNESS ebenfalls auf OFF festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="36780-120">Optionally, switch to asynchronous, high-performance mode by setting SAFETY to OFF and ensuring that WITNESS is also set to OFF.</span></span>  
  
     <span data-ttu-id="36780-121">In Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="36780-121">In Transact-SQL:</span></span>  
  
    -   [<span data-ttu-id="36780-122">Ändern der Transaktionssicherheit in einer Datenbank-Spiegelungssitzung &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="36780-122">Change Transaction Safety in a Database Mirroring Session &#40;Transact-SQL&#41;</span></span>](change-transaction-safety-in-a-database-mirroring-session-transact-sql.md)  
  
    -   [<span data-ttu-id="36780-123">Entfernen des Zeugen aus einer Datenbank-Spiegelungssitzung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="36780-123">Remove the Witness from a Database Mirroring Session &#40;SQL Server&#41;</span></span>](remove-the-witness-from-a-database-mirroring-session-sql-server.md)  
  
     <span data-ttu-id="36780-124">In SQL Server Management Studio:</span><span class="sxs-lookup"><span data-stu-id="36780-124">In SQL Server Management Studio:</span></span>  
  
    -   [<span data-ttu-id="36780-125">Einrichten einer Datenbank-Spiegelungssitzung mithilfe der Windows-Authentifizierung &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="36780-125">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
## <a name="see-also"></a><span data-ttu-id="36780-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="36780-126">See Also</span></span>  
 <span data-ttu-id="36780-127">[TRUSTWORTHY-Datenbankeigenschaft](../../relational-databases/security/trustworthy-database-property.md) </span><span class="sxs-lookup"><span data-stu-id="36780-127">[TRUSTWORTHY Database Property](../../relational-databases/security/trustworthy-database-property.md) </span></span>  
 [<span data-ttu-id="36780-128">Einrichten einer verschlüsselten Spiegeldatenbank</span><span class="sxs-lookup"><span data-stu-id="36780-128">Set Up an Encrypted Mirror Database</span></span>](set-up-an-encrypted-mirror-database.md)  
  
  
