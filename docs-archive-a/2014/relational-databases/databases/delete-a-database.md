---
title: Löschen einer Datenbank | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- database removal [SQL Server], SQL Server Management Studio
- removing databases
- deleting databases
- dropping databases
- databases [SQL Server], dropping
- database removal [SQL Server]
ms.assetid: 1fd8c0f5-03e1-449a-af45-b8cacb479d9c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 633d97815cf69da12f1aa67fd8ef626a2d46e0b0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725878"
---
# <a name="delete-a-database"></a><span data-ttu-id="d6658-102">Löschen einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="d6658-102">Delete a Database</span></span>
  <span data-ttu-id="d6658-103">In diesem Thema wird beschrieben, wie eine benutzerdefinierte Datenbank unter [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="d6658-103">This topic describes how to delete a user-defined database in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="d6658-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="d6658-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d6658-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="d6658-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="d6658-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="d6658-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="d6658-107">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="d6658-107">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="d6658-108">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="d6658-108">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="d6658-109">Security</span><span class="sxs-lookup"><span data-stu-id="d6658-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="d6658-110">**So löschen Sie eine Datenbank mit:**</span><span class="sxs-lookup"><span data-stu-id="d6658-110">**To delete a database, using:**</span></span>  
  
     [<span data-ttu-id="d6658-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d6658-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="d6658-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d6658-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="d6658-113">**Nachverfolgung:**  [Nach dem Löschen einer Datenbank](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="d6658-113">**Follow Up:**  [After deleting a database](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d6658-114">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="d6658-114">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="d6658-115">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="d6658-115">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="d6658-116">Systemdatenbanken können nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="d6658-116">System databases cannot be deleted.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="d6658-117">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="d6658-117">Prerequisites</span></span>  
  
-   <span data-ttu-id="d6658-118">Löschen Sie alle Datenbankmomentaufnahmen, die in der Datenbank vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="d6658-118">Delete any database snapshots that exist on the database.</span></span> <span data-ttu-id="d6658-119">Weitere Informationen finden Sie unter [Löschen einer Datenbank-Momentaufnahme &#40;Transact-SQL&#41;](drop-a-database-snapshot-transact-sql.md)angefügt werden.</span><span class="sxs-lookup"><span data-stu-id="d6658-119">For more information, see [Drop a Database Snapshot &#40;Transact-SQL&#41;](drop-a-database-snapshot-transact-sql.md).</span></span>  
  
-   <span data-ttu-id="d6658-120">Wenn für die Datenbank der Protokollversand konfiguriert ist, entfernen Sie diesen.</span><span class="sxs-lookup"><span data-stu-id="d6658-120">If the database is involved in log shipping, remove log shipping.</span></span>  
  
-   <span data-ttu-id="d6658-121">Wenn die Datenbank für die Transaktionsreplikation oder für die Mergereplikation veröffentlicht ist bzw. Abonnent der Mergereplikation ist, entfernen Sie die Replikation aus der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="d6658-121">If the database is published for transactional replication, or published or subscribed to merge replication, remove replication from the database.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="d6658-122">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="d6658-122">Recommendations</span></span>  
  
-   <span data-ttu-id="d6658-123">Ziehen Sie in Betracht, eine vollständige Sicherung der Datenbank vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="d6658-123">Consider taking a full backup of the database.</span></span> <span data-ttu-id="d6658-124">Eine gelöschte Datenbank kann nur neu erstellt werden, indem eine Sicherungskopie wiederhergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="d6658-124">A deleted database can be re-created only by restoring a backup.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d6658-125">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="d6658-125">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d6658-126">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="d6658-126">Permissions</span></span>  
 <span data-ttu-id="d6658-127">Für die Ausführung von DROP DATABASE benötigt ein Benutzer zumindest die CONTROL-Berechtigung für die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="d6658-127">To execute DROP DATABASE, at a minimum, a user must have CONTROL permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d6658-128">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d6658-128">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-database"></a><span data-ttu-id="d6658-129">So löschen Sie eine Datenbank</span><span class="sxs-lookup"><span data-stu-id="d6658-129">To delete a database</span></span>  
  
1.  <span data-ttu-id="d6658-130">Stellen Sie im **Objekt-Explorer**eine Verbindung zu einer Instanz von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]her, und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="d6658-130">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="d6658-131">Erweitern Sie **Datenbanken**, klicken Sie mit der rechten Maustaste auf die zu löschende Datenbank, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="d6658-131">Expand **Databases**, right-click the database to delete, and then click **Delete**.</span></span>  
  
3.  <span data-ttu-id="d6658-132">Bestätigen Sie, dass die richtige Datenbank ausgewählt ist, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="d6658-132">Confirm the correct database is selected, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="d6658-133">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d6658-133">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-database"></a><span data-ttu-id="d6658-134">So löschen Sie eine Datenbank</span><span class="sxs-lookup"><span data-stu-id="d6658-134">To delete a database</span></span>  
  
1.  <span data-ttu-id="d6658-135">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="d6658-135">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d6658-136">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="d6658-136">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d6658-137">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="d6658-137">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="d6658-138">Im Beispiel werden die Datenbanken `Sales` und `NewSales` entfernt.</span><span class="sxs-lookup"><span data-stu-id="d6658-138">The example removes the `Sales` and `NewSales` databases.</span></span>  
  
```sql  
USE master ;  
GO  
DROP DATABASE Sales, NewSales ;  
GO  
```  
  
##  <a name="follow-up-after-deleting-a-database"></a><a name="FollowUp"></a><span data-ttu-id="d6658-139">Nächster Schritt: Nach dem Löschen einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="d6658-139">Follow Up: After deleting a database</span></span>  
 <span data-ttu-id="d6658-140">Sichern Sie die **master** -Datenbank.</span><span class="sxs-lookup"><span data-stu-id="d6658-140">Back up the **master** database.</span></span> <span data-ttu-id="d6658-141">Wenn die **master** -Datenbank wiederhergestellt werden muss, können Fehlermeldungen auftreten, falls in den Systemkatalogsichten weiterhin Verweise auf Datenbanken bestehen, die seit der letzten Sicherung der **master** -Datenbank gelöscht wurden.</span><span class="sxs-lookup"><span data-stu-id="d6658-141">If **master** must be restored, any database that has been deleted since the last backup of **master** will still have references in the system catalog views and may cause error messages to be raised.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6658-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d6658-142">See Also</span></span>  
 <span data-ttu-id="d6658-143">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d6658-143">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 [<span data-ttu-id="d6658-144">ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d6658-144">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
  
