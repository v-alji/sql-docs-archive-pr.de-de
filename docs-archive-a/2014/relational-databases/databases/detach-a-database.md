---
title: Trennen einer Datenbank | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.detachdatabase.f1
helpviewer_keywords:
- database detaching [SQL Server]
- detaching databases [SQL Server]
ms.assetid: f63d4107-13e4-4bfe-922d-5e4f712e472d
author: stevestein
ms.author: sstein
ms.openlocfilehash: b8acc809b881012d18f78995bb8e521337fb02ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622668"
---
# <a name="detach-a-database"></a><span data-ttu-id="b90b6-102">Trennen einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="b90b6-102">Detach a Database</span></span>
  <span data-ttu-id="b90b6-103">In diesem Thema wird beschrieben, wie eine Datenbank in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]getrennt wird.</span><span class="sxs-lookup"><span data-stu-id="b90b6-103">This topic describes how to detach a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="b90b6-104">Die getrennten Dateien bleiben gespeichert und können mithilfe von CREATE DATABASE (mit der FOR ATTACH- oder FOR ATTACH_REBUILD_LOG-Option) erneut angefügt werden.</span><span class="sxs-lookup"><span data-stu-id="b90b6-104">The detached files remain and can be reattached by using CREATE DATABASE with the FOR ATTACH or FOR ATTACH_REBUILD_LOG option.</span></span> <span data-ttu-id="b90b6-105">Die Dateien können auf einen anderen Server verschoben und dort angefügt werden.</span><span class="sxs-lookup"><span data-stu-id="b90b6-105">The files can be moved to another server and attached there.</span></span>  
  
 <span data-ttu-id="b90b6-106">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="b90b6-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b90b6-107">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="b90b6-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b90b6-108">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="b90b6-108">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="b90b6-109">Security</span><span class="sxs-lookup"><span data-stu-id="b90b6-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b90b6-110">**So trennen Sie eine Datenbank mit**</span><span class="sxs-lookup"><span data-stu-id="b90b6-110">**To detach a database, using:**</span></span>  
  
     [<span data-ttu-id="b90b6-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b90b6-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b90b6-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b90b6-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b90b6-113">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="b90b6-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="b90b6-114">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="b90b6-114">Limitations and Restrictions</span></span>  
 <span data-ttu-id="b90b6-115">Eine Liste der Einschränkungen finden Sie unter [Anfügen und Trennen von Datenbanken &#40;SQL Server&#41;](database-detach-and-attach-sql-server.md)getrennt wird.</span><span class="sxs-lookup"><span data-stu-id="b90b6-115">For a list of limitations and restrictions, see [Database Detach and Attach &#40;SQL Server&#41;](database-detach-and-attach-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b90b6-116">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="b90b6-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b90b6-117">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="b90b6-117">Permissions</span></span>  
 <span data-ttu-id="b90b6-118">Erfordert die Mitgliedschaft in der festen Datenbankrolle "db_owner".</span><span class="sxs-lookup"><span data-stu-id="b90b6-118">Requires membership in the db_owner fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b90b6-119">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b90b6-119">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-detach-a-database"></a><span data-ttu-id="b90b6-120">So trennen Sie eine Datenbank</span><span class="sxs-lookup"><span data-stu-id="b90b6-120">To detach a database</span></span>  
  
1.  <span data-ttu-id="b90b6-121">Stellen Sie im Objekt-Explorer von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] eine Verbindung zu der Instanz von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] her, und erweitern Sie dann die Instanz.</span><span class="sxs-lookup"><span data-stu-id="b90b6-121">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Object Explorer, connect to the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand the instance.</span></span>  
  
2.  <span data-ttu-id="b90b6-122">Erweitern Sie **Datenbanken**, und wählen Sie den Namen der zu trennenden Benutzerdatenbank aus.</span><span class="sxs-lookup"><span data-stu-id="b90b6-122">Expand **Databases**, and select the name of the user database you want to detach.</span></span>  
  
3.  <span data-ttu-id="b90b6-123">Klicken Sie mit der rechten Maustaste auf den Datenbanknamen, zeigen Sie auf **Tasks**, und klicken Sie dann auf **Trennen**.</span><span class="sxs-lookup"><span data-stu-id="b90b6-123">Right-click the database name, point to **Tasks**, and then click **Detach**.</span></span> <span data-ttu-id="b90b6-124">Das Dialogfeld **Datenbank trennen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b90b6-124">The **Detach Database** dialog box appears.</span></span>  
  
     <span data-ttu-id="b90b6-125">**Zu trennende Datenbanken**</span><span class="sxs-lookup"><span data-stu-id="b90b6-125">**Databases to detach**</span></span>  
     <span data-ttu-id="b90b6-126">Führt die zu trennenden Datenbanken auf.</span><span class="sxs-lookup"><span data-stu-id="b90b6-126">Lists the databases to detach.</span></span>  
  
     <span data-ttu-id="b90b6-127">**Database Name**</span><span class="sxs-lookup"><span data-stu-id="b90b6-127">**Database Name**</span></span>  
     <span data-ttu-id="b90b6-128">Zeigt den Namen der zu trennenden Datenbank an.</span><span class="sxs-lookup"><span data-stu-id="b90b6-128">Displays the name of the database to be detached.</span></span>  
  
     <span data-ttu-id="b90b6-129">**Verbindungen löschen**</span><span class="sxs-lookup"><span data-stu-id="b90b6-129">**Drop Connections**</span></span>  
     <span data-ttu-id="b90b6-130">Trennt die Verbindungen zu der angegebenen Datenbank.</span><span class="sxs-lookup"><span data-stu-id="b90b6-130">Disconnect connections to the specified database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b90b6-131">Sie können eine Datenbank mit aktiven Verbindungen nicht trennen.</span><span class="sxs-lookup"><span data-stu-id="b90b6-131">You cannot detach a database with active connections.</span></span>  
  
     <span data-ttu-id="b90b6-132">**Statistikaktualisierung**</span><span class="sxs-lookup"><span data-stu-id="b90b6-132">**Update Statistics**</span></span>  
     <span data-ttu-id="b90b6-133">Standardmäßig werden durch den Trennvorgang beim Trennen der Datenbank die veralteten Optimierungsstatistiken beibehalten. Um die vorhandenen Optimierungsstatistiken zu aktualisieren, aktivieren Sie dieses Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="b90b6-133">By default, the detach operation retains any out-of-date optimization statistics when detaching the database; to update the existing optimization statistics, click this check box.</span></span>  
  
     <span data-ttu-id="b90b6-134">**Volltextkataloge beibehalten**</span><span class="sxs-lookup"><span data-stu-id="b90b6-134">**Keep Full-Text Catalogs**</span></span>  
     <span data-ttu-id="b90b6-135">Standardmäßig werden während des Trennvorgangs alle der Datenbank zugeordneten Volltextkataloge beibehalten.</span><span class="sxs-lookup"><span data-stu-id="b90b6-135">By default, the detach operation keeps any full-text catalogs that are associated with the database.</span></span> <span data-ttu-id="b90b6-136">Um sie zu entfernen, deaktivieren Sie das Kontrollkästchen **Volltextkataloge beibehalten** .</span><span class="sxs-lookup"><span data-stu-id="b90b6-136">To remove them, clear the **Keep Full-Text Catalogs** check box.</span></span> <span data-ttu-id="b90b6-137">Diese Option wird nur beim Aktualisieren einer Datenbank von [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b90b6-137">This option appears only when you are upgrading a database from [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
     <span data-ttu-id="b90b6-138">**Status**</span><span class="sxs-lookup"><span data-stu-id="b90b6-138">**Status**</span></span>  
     <span data-ttu-id="b90b6-139">Zeigt einen der folgenden Statuswerte an: **Ready** (Bereit) der **Not ready** (Nicht bereit).</span><span class="sxs-lookup"><span data-stu-id="b90b6-139">Displays one of the following states: **Ready** or **Not ready**.</span></span>  
  
     <span data-ttu-id="b90b6-140">**Meldung**</span><span class="sxs-lookup"><span data-stu-id="b90b6-140">**Message**</span></span>  
     <span data-ttu-id="b90b6-141">Unter **Meldung** können folgende Informationen zur Datenbank angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="b90b6-141">The **Message** column may display information about the database, as follows:</span></span>  
  
    -   <span data-ttu-id="b90b6-142">Wenn eine Datenbank an einer Replikation beteiligt ist, hat der **Status** den Wert **Nicht bereit** , und unter **Meldung** wird **Die Datenbank wurde repliziert**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b90b6-142">When a database is involved with replication, the **Status** is **Not ready** and the **Message** column displays **Database replicated**.</span></span>  
  
    -   <span data-ttu-id="b90b6-143">Wenn eine Datenbank über eine oder mehrere Verbindungen verfügt, weist der **Status** den Wert **Nicht bereit** auf, und in der Spalte **Meldung** wird _<Anzahl_aktiver_Verbindungen>_ **Aktive Verbindung(en)** angezeigt, z. B.: **1 Aktive Verbindung(en)** .</span><span class="sxs-lookup"><span data-stu-id="b90b6-143">When a database has one or more active connections, the **Status** is **Not ready** and the **Message** column displays _<number_of_active_connections>_**Active connection(s)** - for example: **1 Active connection(s)**.</span></span> <span data-ttu-id="b90b6-144">Bevor Sie die Datenbank trennen können, müssen Sie durch Auswählen der Option **Verbindungen löschen**alle aktiven Verbindungen trennen.</span><span class="sxs-lookup"><span data-stu-id="b90b6-144">Before you can detach the database, you need to disconnect any active connections by selecting **Drop Connections**.</span></span>  
  
     <span data-ttu-id="b90b6-145">Weitere Informationen zu einer Meldung erhalten Sie, indem Sie auf den Linktext klicken, um den Aktivitätsmonitor zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="b90b6-145">To obtain more information about a message, click the hyperlinked text to open Activity Monitor.</span></span>  
  
4.  <span data-ttu-id="b90b6-146">Wenn Sie zum Trennen der Datenbank bereit sind, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b90b6-146">When you are ready to detach the database, click **OK**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b90b6-147">Die jetzt getrennte Datenbank bleibt im **Datenbanken** -Knoten des Objekt-Explorers sichtbar, bis die Ansicht aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="b90b6-147">The newly detached database will remain visible in the **Databases** node of Object Explorer until the view is refreshed.</span></span> <span data-ttu-id="b90b6-148">Sie können die Ansicht jederzeit aktualisieren: Klicken Sie in den Objekt-Explorer-Bereich, und wählen Sie in der Menüleiste **Ansicht** und dann **Aktualisieren** aus.</span><span class="sxs-lookup"><span data-stu-id="b90b6-148">You can refresh the view at any time: Click in the Object Explorer pane, and from the menu bar select **View** and then **Refresh**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b90b6-149">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b90b6-149">Using Transact-SQL</span></span>  
  
#### <a name="to-detach-a-database"></a><span data-ttu-id="b90b6-150">So trennen Sie eine Datenbank</span><span class="sxs-lookup"><span data-stu-id="b90b6-150">To detach a database</span></span>  
  
1.  <span data-ttu-id="b90b6-151">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="b90b6-151">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b90b6-152">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="b90b6-152">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b90b6-153">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="b90b6-153">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="b90b6-154">Im folgenden Beispiel wird die AdventureWorks2012-Datenbank getrennt, wobei "skipchecks" auf "true" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="b90b6-154">This example detaches the AdventureWorks2012 database with skipchecks set to true.</span></span>  
  
```  
EXEC sp_detach_db 'AdventureWorks2012', 'true';  
```  
  
## <a name="see-also"></a><span data-ttu-id="b90b6-155">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b90b6-155">See Also</span></span>  
 <span data-ttu-id="b90b6-156">[Anfügen und Trennen von Datenbanken &#40;SQL Server&#41;](database-detach-and-attach-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b90b6-156">[Database Detach and Attach &#40;SQL Server&#41;](database-detach-and-attach-sql-server.md) </span></span>  
 [<span data-ttu-id="b90b6-157">sp_detach_db &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b90b6-157">sp_detach_db &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-detach-db-transact-sql)  
  
  
