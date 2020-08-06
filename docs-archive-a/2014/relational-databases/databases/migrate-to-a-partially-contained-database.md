---
title: Migrieren zu einer partiell eigenständigen Datenbank | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- contained database, migrating to
ms.assetid: 90faac38-f79e-496d-b589-e8b2fe01c562
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6142d46dc0540e5998fa66d463538d1453a17d84
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725841"
---
# <a name="migrate-to-a-partially-contained-database"></a><span data-ttu-id="a677d-102">Migrate to a Partially Contained Database</span><span class="sxs-lookup"><span data-stu-id="a677d-102">Migrate to a Partially Contained Database</span></span>
  <span data-ttu-id="a677d-103">In diesem Thema wird beschrieben, wie die Umstellung auf das teilweise eigenständige Datenbankmodell vorbereitet wird. Anschließend werden die Migrationsschritte erläutert.</span><span class="sxs-lookup"><span data-stu-id="a677d-103">This topic discusses how to prepare to change to the partially contained database model and then provides the migration steps.</span></span>  
  
 <span data-ttu-id="a677d-104">**In diesem Thema:**</span><span class="sxs-lookup"><span data-stu-id="a677d-104">**In this topic:**</span></span>  
  
-   [<span data-ttu-id="a677d-105">Vorbereiten auf das Migrieren einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="a677d-105">Preparing to Migrate a Database</span></span>](#prepare)  
  
-   [<span data-ttu-id="a677d-106">Aktivieren enthaltener Datenbanken</span><span class="sxs-lookup"><span data-stu-id="a677d-106">Enable Contained Databases</span></span>](#enable)  
  
-   [<span data-ttu-id="a677d-107">Konvertieren einer Datenbank in eine teilweise eigenständige Datenbank</span><span class="sxs-lookup"><span data-stu-id="a677d-107">Converting a Database to Partially Contained</span></span>](#convert)  
  
-   [<span data-ttu-id="a677d-108">Migrieren von Benutzern zu Benutzern eigenständiger Datenbanken</span><span class="sxs-lookup"><span data-stu-id="a677d-108">Migrating Users to Contained Database Users</span></span>](#users)  
  
##  <a name="preparing-to-migrate-a-database"></a><a name="prepare"></a> <span data-ttu-id="a677d-109">Vorbereiten auf das Migrieren einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="a677d-109">Preparing to Migrate a Database</span></span>  
 <span data-ttu-id="a677d-110">Überprüfen Sie die folgenden Punkte, wenn Sie eine Datenbank zum teilweise eigenständigen Datenbankmodell migrieren möchten.</span><span class="sxs-lookup"><span data-stu-id="a677d-110">Review the following items when considering migrating a database to the partially contained database model.</span></span>  
  
-   <span data-ttu-id="a677d-111">Machen Sie sich mit dem teilweise eigenständigen Datenbankmodell vertraut.</span><span class="sxs-lookup"><span data-stu-id="a677d-111">You should understand the partially contained database model.</span></span> <span data-ttu-id="a677d-112">Weitere Informationen finden Sie unter [Contained Databases](contained-databases.md).</span><span class="sxs-lookup"><span data-stu-id="a677d-112">For more information, see [Contained Databases](contained-databases.md).</span></span>  
  
-   <span data-ttu-id="a677d-113">Sie müssen die Risiken verstehen, die mit teilweise eigenständigen Datenbanken verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="a677d-113">You should understand risks that are unique to partially contained databases.</span></span> <span data-ttu-id="a677d-114">Weitere Informationen finden Sie unter [Security Best Practices with Contained Databases](security-best-practices-with-contained-databases.md).</span><span class="sxs-lookup"><span data-stu-id="a677d-114">For more information, see [Security Best Practices with Contained Databases](security-best-practices-with-contained-databases.md).</span></span>  
  
-   <span data-ttu-id="a677d-115">Enthaltene Datenbanken unterstützen weder die Replikation, noch das Aufzeichnen oder das Nachverfolgen von Änderungsdaten.</span><span class="sxs-lookup"><span data-stu-id="a677d-115">Contained databases do not support replication, change data capture, or change tracking.</span></span> <span data-ttu-id="a677d-116">Vergewissern Sie sich, dass diese Funktionen für die Datenbank nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a677d-116">Confirm the database does not use these features.</span></span>  
  
-   <span data-ttu-id="a677d-117">Sehen Sie die Liste der Datenbankfunktionen ein, die für teilweise eigenständige Datenbanken geändert werden.</span><span class="sxs-lookup"><span data-stu-id="a677d-117">Review the list of database features that are modified for partially contained databases.</span></span> <span data-ttu-id="a677d-118">Weitere Informationen finden Sie unter [Geänderte Funktionen &#40;Eigenständige Datenbank&#41;](modified-features-contained-database.md).</span><span class="sxs-lookup"><span data-stu-id="a677d-118">For more information, see [Modified Features &#40;Contained Database&#41;](modified-features-contained-database.md).</span></span>  
  
-   <span data-ttu-id="a677d-119">Fragen Sie [sys.dm_db_uncontained_entities &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-uncontained-entities-transact-sql) ab, um nicht enthaltene Objekte oder Funktionen in der Datenbank zu suchen.</span><span class="sxs-lookup"><span data-stu-id="a677d-119">Query [sys.dm_db_uncontained_entities &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-uncontained-entities-transact-sql) to find uncontained objects or features in the database.</span></span> <span data-ttu-id="a677d-120">Weitere Informationen finden Sie weiter oben unter</span><span class="sxs-lookup"><span data-stu-id="a677d-120">For more information, see.</span></span>  
  
-   <span data-ttu-id="a677d-121">Überwachen Sie das **database_uncontained_usage** -XEvent, um festzustellen, ob nicht enthaltene Funktionen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a677d-121">Monitor the **database_uncontained_usage** XEvent to see when uncontained features are used.</span></span>  
  
##  <a name="enable-contained-databases"></a><a name="enable"></a> <span data-ttu-id="a677d-122">Aktivieren enthaltener Datenbanken</span><span class="sxs-lookup"><span data-stu-id="a677d-122">Enable Contained Databases</span></span>  
 <span data-ttu-id="a677d-123">Enthaltene Datenbanken müssen für die [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]-Instanz aktiviert sein, bevor sie erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="a677d-123">Contained databases must be enabled on the instance of [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], before contained databases can be created.</span></span>  
  
### <a name="enabling-contained-databases-using-transact-sql"></a><span data-ttu-id="a677d-124">Aktivieren von enthaltenen Datenbanken mit Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a677d-124">Enabling Contained Databases Using Transact-SQL</span></span>  
 <span data-ttu-id="a677d-125">Im folgenden Beispiel werden enthaltene Datenbanken für die [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]-Instanz aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a677d-125">The following example enables contained databases on the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
```sql  
sp_configure 'contained database authentication', 1;  
GO  
RECONFIGURE ;  
GO  
```  
  
#### <a name="enabling-contained-databases-using-management-studio"></a><span data-ttu-id="a677d-126">Aktivieren von enthaltenen Datenbanken mit Management Studio</span><span class="sxs-lookup"><span data-stu-id="a677d-126">Enabling Contained Databases Using Management Studio</span></span>  
 <span data-ttu-id="a677d-127">Im folgenden Beispiel werden enthaltene Datenbanken für die [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]-Instanz aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a677d-127">The following example enables contained databases on the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
1.  <span data-ttu-id="a677d-128">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf den Servernamen, und klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="a677d-128">In Object Explorer, right-click the server name, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="a677d-129">Legen Sie auf der Seite **Erweitert** im Abschnitt **Kapselung** die Option **Enthaltene Datenbanken aktivieren** auf **True**fest.</span><span class="sxs-lookup"><span data-stu-id="a677d-129">On the **Advanced** page, in the **Containment** section, set the **Enable Contained Databases** option to **True**.</span></span>  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
##  <a name="converting-a-database-to-partially-contained"></a><a name="convert"></a> <span data-ttu-id="a677d-130">Konvertieren einer Datenbank in eine teilweise eigenständige Datenbank</span><span class="sxs-lookup"><span data-stu-id="a677d-130">Converting a Database to Partially Contained</span></span>  
 <span data-ttu-id="a677d-131">Eine Datenbank wird in eine enthaltene Datenbank konvertiert, indem die **CONTAINMENT** -Option geändert wird.</span><span class="sxs-lookup"><span data-stu-id="a677d-131">A database is converted to a contained database by changing the **CONTAINMENT** option.</span></span>  
  
### <a name="converting-a-database-to-partially-contained-using-transact-sql"></a><span data-ttu-id="a677d-132">Konvertieren einer Datenbank in eine teilweise eigenständige Datenbank mit Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a677d-132">Converting a Database to Partially Contained Using Transact-SQL</span></span>  
 <span data-ttu-id="a677d-133">Im folgenden Beispiel wird die Datenbank `Accounting` in eine teilweise eigenständige Datenbank konvertiert.</span><span class="sxs-lookup"><span data-stu-id="a677d-133">The following example converts a database named `Accounting` to a partially contained database.</span></span>  
  
```sql  
USE [master]  
GO  
ALTER DATABASE [Accounting] SET CONTAINMENT = PARTIAL  
GO  
```  
  
### <a name="converting-a-database-to-partially-contained-using-management-studio"></a><span data-ttu-id="a677d-134">Konvertieren einer Datenbank in die teilweise eigenständige Datenbank mit Management Studio</span><span class="sxs-lookup"><span data-stu-id="a677d-134">Converting a Database to Partially contained Using Management Studio</span></span>  
 <span data-ttu-id="a677d-135">Im folgenden Beispiel wird die Datenbank in eine teilweise eigenständige Datenbank konvertiert.</span><span class="sxs-lookup"><span data-stu-id="a677d-135">The following example converts a database to a partially contained database.</span></span>  
  
1.  <span data-ttu-id="a677d-136">Erweitern Sie im Objekt-Explorer **Datenbanken**, klicken Sie mit der rechten Maustaste auf die zu konvertierende Datenbank, und klicken Sie anschließend auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="a677d-136">In Object Explorer, expand **Databases**, right-click the database to be converted, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="a677d-137">Ändern Sie auf der Seite **Optionen** die Option **Kapselungstyp** in **Teilweise**.</span><span class="sxs-lookup"><span data-stu-id="a677d-137">On the **Options** page, change the **Containment type** option to **Partial**.</span></span>  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
##  <a name="migrating-users-to-contained-database-users"></a><a name="users"></a> <span data-ttu-id="a677d-138">Migrieren von Benutzern zu Benutzern eigenständiger Datenbanken</span><span class="sxs-lookup"><span data-stu-id="a677d-138">Migrating Users to Contained Database Users</span></span>  
 <span data-ttu-id="a677d-139">Im folgenden Beispiel werden alle Benutzer, die auf [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Anmeldungen basieren, in Benutzer enthaltener Datenbanken mit Kennwörtern migriert.</span><span class="sxs-lookup"><span data-stu-id="a677d-139">The following example migrates all users that are based on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logins to contained database users with passwords.</span></span> <span data-ttu-id="a677d-140">Nicht berücksichtigt werden Anmeldungen, die nicht aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="a677d-140">The example excludes logins that are not enabled.</span></span> <span data-ttu-id="a677d-141">Das Beispiel muss in der enthaltenen Datenbank ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a677d-141">The example must be executed in the contained database.</span></span>  
  
```sql  
DECLARE @username sysname ;  
DECLARE user_cursor CURSOR  
    FOR   
        SELECT dp.name   
        FROM sys.database_principals AS dp  
        JOIN sys.server_principals AS sp   
        ON dp.sid = sp.sid  
        WHERE dp.authentication_type = 1 AND sp.is_disabled = 0;  
OPEN user_cursor  
FETCH NEXT FROM user_cursor INTO @username  
    WHILE @@FETCH_STATUS = 0  
    BEGIN  
        EXECUTE sp_migrate_user_to_contained   
        @username = @username,  
        @rename = N'keep_name',  
        @disablelogin = N'disable_login';  
    FETCH NEXT FROM user_cursor INTO @username  
    END  
CLOSE user_cursor ;  
DEALLOCATE user_cursor ;  
```  
  
## <a name="see-also"></a><span data-ttu-id="a677d-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a677d-142">See Also</span></span>  
 <span data-ttu-id="a677d-143">[Eigenständige Datenbanken](contained-databases.md) </span><span class="sxs-lookup"><span data-stu-id="a677d-143">[Contained Databases](contained-databases.md) </span></span>  
 <span data-ttu-id="a677d-144">[sp_migrate_user_to_contained &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-migrate-user-to-contained-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a677d-144">[sp_migrate_user_to_contained &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-migrate-user-to-contained-transact-sql) </span></span>  
 [<span data-ttu-id="a677d-145">sys.dm_db_uncontained_entities &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a677d-145">sys.dm_db_uncontained_entities &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-uncontained-entities-transact-sql)  
  
  
