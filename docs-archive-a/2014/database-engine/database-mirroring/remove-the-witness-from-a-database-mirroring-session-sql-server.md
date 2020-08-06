---
title: Entfernen des Zeugen aus einer Datenbank-Spiegelungssitzung (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- witness [SQL Server], turning off
- witness [SQL Server], removing
- database mirroring [SQL Server], witness
ms.assetid: f3ce7afc-8936-4d35-80ce-d0f8fbc318d3
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d5ede54aca3588a6fcd7cee8759112b606eac752
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701798"
---
# <a name="remove-the-witness-from-a-database-mirroring-session-sql-server"></a><span data-ttu-id="d62e8-102">Entfernen des Zeugen aus einer Datenbank-Spiegelungssitzung (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="d62e8-102">Remove the Witness from a Database Mirroring Session (SQL Server)</span></span>
  <span data-ttu-id="d62e8-103">In diesem Thema wird beschrieben, wie Sie einen Zeugen in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]aus einer Datenbankspiegelungssitzung entfernen.</span><span class="sxs-lookup"><span data-stu-id="d62e8-103">This topic describes how to remove a witness from a database mirroring session in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="d62e8-104">Der Datenbankbesitzer kann den Zeugen für eine Datenbank-Spiegelungssitzung jederzeit während einer Datenbank-Spiegelungssitzung deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="d62e8-104">At any time during a database mirroring session, the database owner can turn off the witness for a database mirroring session.</span></span>  
  
 <span data-ttu-id="d62e8-105">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="d62e8-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d62e8-106">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="d62e8-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="d62e8-107">Security</span><span class="sxs-lookup"><span data-stu-id="d62e8-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="d62e8-108">**Entfernen des Zeugen mit:**</span><span class="sxs-lookup"><span data-stu-id="d62e8-108">**To Replace remove the witness, using:**</span></span>  
  
     [<span data-ttu-id="d62e8-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d62e8-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="d62e8-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d62e8-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="d62e8-111">**Nachverfolgung:**  [Nach dem Entfernen des Zeugen](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="d62e8-111">**Follow Up:**  [After Removing the Witness](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d62e8-112">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="d62e8-112">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d62e8-113">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="d62e8-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d62e8-114">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="d62e8-114">Permissions</span></span>  
 <span data-ttu-id="d62e8-115">Erfordert die ALTER-Berechtigung für die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="d62e8-115">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d62e8-116">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d62e8-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-remove-the-witness"></a><span data-ttu-id="d62e8-117">So entfernen Sie den Zeugen</span><span class="sxs-lookup"><span data-stu-id="d62e8-117">To remove the witness</span></span>  
  
1.  <span data-ttu-id="d62e8-118">Stellen Sie eine Verbindung zur Prinzipalserverinstanz her, und klicken Sie im Bereich **Objekt-Explorer** auf den Servernamen, um die Serverstruktur zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="d62e8-118">Connect to the principal server instance and, in the **Object Explorer** pane, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="d62e8-119">Erweitern Sie **Datenbanken**, und wählen Sie die Datenbank aus, deren Zeuge entfernt werden soll.</span><span class="sxs-lookup"><span data-stu-id="d62e8-119">Expand **Databases**, and select the database whose witness you want to remove.</span></span>  
  
3.  <span data-ttu-id="d62e8-120">Klicken Sie mit der rechten Maustaste auf die Datenbank, wählen Sie **Tasks**aus, und klicken Sie dann auf **Spiegeln**.</span><span class="sxs-lookup"><span data-stu-id="d62e8-120">Right-click the database, select **Tasks**, and then click **Mirror**.</span></span> <span data-ttu-id="d62e8-121">Dadurch wird die Seite **Spiegelung** im Dialogfeld **Datenbankeigenschaften** geöffnet.</span><span class="sxs-lookup"><span data-stu-id="d62e8-121">This opens the **Mirroring** page of the **Database Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="d62e8-122">Zum Entfernen des Zeugen löschen Sie seine Servernetzwerkadresse aus dem Feld **Zeuge** .</span><span class="sxs-lookup"><span data-stu-id="d62e8-122">To remove the witness, delete its server network address from the **Witness** field.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d62e8-123">Wenn Sie vom Modus für hohe Sicherheit mit automatischem Failover zum Modus zur hohe Leistung wechseln, wird das Feld **Zeuge** automatisch gelöscht.</span><span class="sxs-lookup"><span data-stu-id="d62e8-123">If you switch from high-safety mode with automatic failover to high-performance mode, the **Witness** field is automatically cleared.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="d62e8-124">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d62e8-124">Using Transact-SQL</span></span>  
  
#### <a name="to-remove-the-witness"></a><span data-ttu-id="d62e8-125">So entfernen Sie den Zeugen</span><span class="sxs-lookup"><span data-stu-id="d62e8-125">To remove the witness</span></span>  
  
1.  <span data-ttu-id="d62e8-126">Stellen Sie für eine der Partnerserverinstanzen eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)] her.</span><span class="sxs-lookup"><span data-stu-id="d62e8-126">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] on either partner server instance.</span></span>  
  
2.  <span data-ttu-id="d62e8-127">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="d62e8-127">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d62e8-128">Führen Sie die folgende Anweisung aus:</span><span class="sxs-lookup"><span data-stu-id="d62e8-128">Issue the following statement:</span></span>  
  
     <span data-ttu-id="d62e8-129">[ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) *Datenbankname* SET WITNESS OFF</span><span class="sxs-lookup"><span data-stu-id="d62e8-129">[ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) *database_name* SET WITNESS OFF</span></span>  
  
     <span data-ttu-id="d62e8-130">Dabei ist *Datenbankname* der Name der gespiegelten Datenbank.</span><span class="sxs-lookup"><span data-stu-id="d62e8-130">where *database_name* is the name of the mirrored database.</span></span>  
  
     <span data-ttu-id="d62e8-131">Im folgenden Beispiel wird der Zeuge aus der [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] -Datenbank entfernt.</span><span class="sxs-lookup"><span data-stu-id="d62e8-131">The following example removes the witness from the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks2012 SET WITNESS OFF ;  
    ```  
  
##  <a name="follow-up-after-removing-the-witness"></a><a name="FollowUp"></a> <span data-ttu-id="d62e8-132">Nachverfolgung: Nach dem Entfernen des Zeugen</span><span class="sxs-lookup"><span data-stu-id="d62e8-132">Follow Up: After Removing the Witness</span></span>  
 <span data-ttu-id="d62e8-133">Durch das Deaktivieren des Zeugen ändert sich der [Betriebsmodus](database-mirroring-operating-modes.md)entsprechend der Einstellung für die Transaktionssicherheit:</span><span class="sxs-lookup"><span data-stu-id="d62e8-133">Turning off the witness changes the [operating mode](database-mirroring-operating-modes.md)in accordance with the transaction-safety setting:</span></span>  
  
-   <span data-ttu-id="d62e8-134">Wenn die Transaktionssicherheit auf FULL (Standardeinstellung) festgelegt ist, wird in der Sitzung der synchrone Modus für hohe Sicherheit ohne automatisches Failover verwendet.</span><span class="sxs-lookup"><span data-stu-id="d62e8-134">If transaction safety is set to FULL (the default), the session uses high-safety, synchronous mode without automatic failover.</span></span>  
  
-   <span data-ttu-id="d62e8-135">Wenn die Transaktionssicherheit auf OFF festgelegt ist, wird die Sitzung asynchron (im Modus für hohe Leistung) ausgeführt, ohne dass ein Quorum erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="d62e8-135">If transaction safety is set to OFF, the session operates asynchronously (in high-performance mode) without requiring quorum.</span></span> <span data-ttu-id="d62e8-136">Bei deaktivierter Transaktionssicherheit wird stets dringend empfohlen, den Zeugen ebenfalls zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="d62e8-136">Whenever transaction safety is turned off, we strongly recommend also turning the witness off.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="d62e8-137">Die Transaktionssicherheitseinstellung der Datenbank wird auf jedem Partner in der [sys.database_mirroring](/sql/relational-databases/system-catalog-views/sys-database-mirroring-transact-sql)-Katalogsicht in der **mirroring_safety_level**-Spalte und der **mirroring_safety_level_desc**-Spalte aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="d62e8-137">The transaction safety setting of the database is recorded on each partner in the [sys.database_mirroring](/sql/relational-databases/system-catalog-views/sys-database-mirroring-transact-sql) catalog view in the **mirroring_safety_level** and **mirroring_safety_level_desc** columns.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="d62e8-138">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="d62e8-138">Related Tasks</span></span>  
  
-   [<span data-ttu-id="d62e8-139">Hinzufügen eines Zeugen für die Datenbankspiegelung mithilfe der Windows-Authentifizierung &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d62e8-139">Add a Database Mirroring Witness Using Windows Authentication &#40;Transact-SQL&#41;</span></span>](add-a-database-mirroring-witness-using-windows-authentication-transact-sql.md)  
  
-   [<span data-ttu-id="d62e8-140">Hinzufügen oder Ersetzen eines Datenbank-Spiegelungszeugen &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="d62e8-140">Add or Replace a Database Mirroring Witness &#40;SQL Server Management Studio&#41;</span></span>](../database-mirroring/add-or-replace-a-database-mirroring-witness-sql-server-management-studio.md)  
  
## <a name="see-also"></a><span data-ttu-id="d62e8-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d62e8-141">See Also</span></span>  
 <span data-ttu-id="d62e8-142">[ALTER DATABASE-Datenbankspiegelung &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span><span class="sxs-lookup"><span data-stu-id="d62e8-142">[ALTER DATABASE Database Mirroring &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span></span>  
 <span data-ttu-id="d62e8-143">[Ändern der Transaktionssicherheit in einer Datenbank-Spiegelungs Sitzung &#40;Transact-SQL-&#41;](change-transaction-safety-in-a-database-mirroring-session-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="d62e8-143">[Change Transaction Safety in a Database Mirroring Session &#40;Transact-SQL&#41;](change-transaction-safety-in-a-database-mirroring-session-transact-sql.md) </span></span>  
 <span data-ttu-id="d62e8-144">[Hinzufügen eines Datenbankspiegelungs-Zeugen mithilfe der Windows-Authentifizierung &#40;Transact-SQL&#41;](add-a-database-mirroring-witness-using-windows-authentication-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="d62e8-144">[Add a Database Mirroring Witness Using Windows Authentication &#40;Transact-SQL&#41;](add-a-database-mirroring-witness-using-windows-authentication-transact-sql.md) </span></span>  
 [<span data-ttu-id="d62e8-145">Datenbank-Spiegelungszeuge</span><span class="sxs-lookup"><span data-stu-id="d62e8-145">Database Mirroring Witness</span></span>](database-mirroring-witness.md)  
  
  
