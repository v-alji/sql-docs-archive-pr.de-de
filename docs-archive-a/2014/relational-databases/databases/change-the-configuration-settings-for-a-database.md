---
title: Ändern der Konfigurationseinstellungen für eine Datenbank| Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- database configuration [SQL Server]
- configuration options [SQL Server], databases
- modifying database configuration settings
ms.assetid: c29c3385-5043-400f-bb4e-044a4c9a9a4b
author: stevestein
ms.author: sstein
ms.openlocfilehash: f9edecefae5154bb66a65e38724d9e77a94fdbb4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725910"
---
# <a name="change-the-configuration-settings-for-a-database"></a><span data-ttu-id="d9d00-102">Ändern der Konfigurationseinstellungen für eine Datenbank</span><span class="sxs-lookup"><span data-stu-id="d9d00-102">Change the Configuration Settings for a Database</span></span>
  <span data-ttu-id="d9d00-103">In diesem Thema wird beschrieben, wie Optionen auf Datenbankebene in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]geändert werden.</span><span class="sxs-lookup"><span data-stu-id="d9d00-103">This topic describes how to change database-level options in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="d9d00-104">Diese Optionen sind für jede Datenbank eindeutig und haben keinen Einfluss auf andere Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="d9d00-104">These options are unique to each database and do not affect other databases.</span></span>  
  
 <span data-ttu-id="d9d00-105">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="d9d00-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d9d00-106">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="d9d00-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="d9d00-107">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="d9d00-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="d9d00-108">Security</span><span class="sxs-lookup"><span data-stu-id="d9d00-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="d9d00-109">**So ändern Sie die Optionseinstellungen für eine Datenbank mit:**</span><span class="sxs-lookup"><span data-stu-id="d9d00-109">**To change the option settings for a database, using:**</span></span>  
  
     [<span data-ttu-id="d9d00-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d9d00-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="d9d00-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d9d00-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d9d00-112">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="d9d00-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="d9d00-113">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="d9d00-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="d9d00-114">Nur der Systemadministrator, der Datenbankbesitzer sowie Mitglieder der festen Serverrollen **sysadmin** und **dbcreator** und der festen Datenbankrolle **db_owner** können diese Optionen ändern.</span><span class="sxs-lookup"><span data-stu-id="d9d00-114">Only the system administrator, database owner, members of the **sysadmin** and **dbcreator** fixed server roles and **db_owner** fixed database roles can modify these options.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d9d00-115">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="d9d00-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d9d00-116">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="d9d00-116">Permissions</span></span>  
 <span data-ttu-id="d9d00-117">Erfordert die ALTER-Berechtigung für die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="d9d00-117">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d9d00-118">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d9d00-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-change-the-option-settings-for-a-database"></a><span data-ttu-id="d9d00-119">So ändern Sie die Optionseinstellungen für eine Datenbank</span><span class="sxs-lookup"><span data-stu-id="d9d00-119">To change the option settings for a database</span></span>  
  
1.  <span data-ttu-id="d9d00-120">Stellen Sie im Objekt-Explorer eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Instanz her, erweitern Sie den Server, erweitern Sie **Datenbanken**, klicken Sie mit der rechten Maustaste auf eine Datenbank, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="d9d00-120">In Object Explorer, connect to a [!INCLUDE[ssDE](../../includes/ssde-md.md)] instance, expand the server, expand **Databases**, right-click a database, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="d9d00-121">Klicken Sie im Dialogfeld **Datenbankeigenschaften** auf **Optionen** , um auf die meisten Konfigurationseinstellungen zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="d9d00-121">In the **Database Properties** dialog box, click **Options** to access most of the configuration settings.</span></span> <span data-ttu-id="d9d00-122">Auf den entsprechenden Seiten finden Sie Datei- und Dateigruppenkonfigurationen, Spiegelung und Protokollversand.</span><span class="sxs-lookup"><span data-stu-id="d9d00-122">File and filegroup configurations, mirroring and log shipping are on their respective pages.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="d9d00-123">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d9d00-123">Using Transact-SQL</span></span>  
  
#### <a name="to-change-the-option-settings-for-a-database"></a><span data-ttu-id="d9d00-124">So ändern Sie die Optionseinstellungen für eine Datenbank</span><span class="sxs-lookup"><span data-stu-id="d9d00-124">To change the option settings for a database</span></span>  
  
1.  <span data-ttu-id="d9d00-125">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="d9d00-125">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d9d00-126">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="d9d00-126">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d9d00-127">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="d9d00-127">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="d9d00-128">In diesem Beispiel werden die Optionen für das Wiederherstellungsmodell und die Datenseitenüberprüfung für die [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] -Beispieldatenbank festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d9d00-128">This example sets the recovery model and data page verification options for the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span>  
  
 [!code-sql[DatabaseDDL#AlterDatabase7](../../snippets/tsql/SQL14/tsql/databaseddl/transact-sql/alterdatabase.sql#alterdatabase7)]  
  
 <span data-ttu-id="d9d00-129">Weitere Beispiele finden Sie unter [ALTER DATABASE SET-Optionen &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span><span class="sxs-lookup"><span data-stu-id="d9d00-129">For more examples, see [ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9d00-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d9d00-130">See Also</span></span>  
 <span data-ttu-id="d9d00-131">[ALTER DATABASE-Kompatibilitätsgrad &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level) </span><span class="sxs-lookup"><span data-stu-id="d9d00-131">[ALTER DATABASE Compatibility Level &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level) </span></span>  
 <span data-ttu-id="d9d00-132">[ALTER DATABASE-Datenbankspiegelung &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span><span class="sxs-lookup"><span data-stu-id="d9d00-132">[ALTER DATABASE Database Mirroring &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span></span>  
 <span data-ttu-id="d9d00-133">[ALTER DATABASE SET HADR &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) </span><span class="sxs-lookup"><span data-stu-id="d9d00-133">[ALTER DATABASE SET HADR &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) </span></span>  
 <span data-ttu-id="d9d00-134">[Umbenennen einer Datenbank](rename-a-database.md) </span><span class="sxs-lookup"><span data-stu-id="d9d00-134">[Rename a Database](rename-a-database.md) </span></span>  
 [<span data-ttu-id="d9d00-135">Verkleinern einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="d9d00-135">Shrink a Database</span></span>](shrink-a-database.md)  
  
  
