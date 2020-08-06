---
title: Festlegen des Ablaufdatums für eine Sicherung (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- backing up databases [SQL Server], expiration dates
- expiration [SQL Server]
- database backups [SQL Server], expiration dates
ms.assetid: 76e814df-6487-4893-9f09-7759f1863a5c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9185222df93e0a1150256535526ba910c593cf6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616109"
---
# <a name="set-the-expiration-date-on-a-backup-sql-server"></a><span data-ttu-id="281ec-102">Festlegen des Ablaufdatums für eine Sicherung (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="281ec-102">Set the Expiration Date on a Backup (SQL Server)</span></span>
  <span data-ttu-id="281ec-103">In diesem Thema wird beschrieben, wie Sie das Ablaufdatum für eine Sicherung in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]festlegen.</span><span class="sxs-lookup"><span data-stu-id="281ec-103">This topic describes how to set the expiration date on a backup in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="281ec-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="281ec-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="281ec-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="281ec-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="281ec-106">Security</span><span class="sxs-lookup"><span data-stu-id="281ec-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="281ec-107">**So legen Sie das Ablaufdatum für eine Sicherung fest mit**</span><span class="sxs-lookup"><span data-stu-id="281ec-107">**To set the expiration date on a backup, using:**</span></span>  
  
     [<span data-ttu-id="281ec-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="281ec-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="281ec-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="281ec-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="281ec-110">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="281ec-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="281ec-111">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="281ec-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="281ec-112">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="281ec-112">Permissions</span></span>  
 <span data-ttu-id="281ec-113">Mitglieder der festen Serverrolle **sysadmin** und der festen Datenbankrollen **db_owner** und **db_backupoperator** verfügen standardmäßig über BACKUP DATABASE- und BACKUP LOG-Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="281ec-113">BACKUP DATABASE and BACKUP LOG permissions default to members of the **sysadmin** fixed server role and the **db_owner** and **db_backupoperator** fixed database roles.</span></span>  
  
 <span data-ttu-id="281ec-114">Besitz- und Berechtigungsprobleme im Zusammenhang mit der physischen Datei des Sicherungsmediums können den Sicherungsvorgang beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="281ec-114">Ownership and permission problems on the backup device's physical file can interfere with a backup operation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="281ec-115">muss über Lese- und Schreibberechtigungen für das Medium verfügen. Das Konto, unter dem der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Dienst ausgeführt wird, muss Schreibberechtigungen haben.</span><span class="sxs-lookup"><span data-stu-id="281ec-115">must be able to read and write to the device; the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service runs must have write permissions.</span></span> <span data-ttu-id="281ec-116">Allerdings prüft die gespeicherte Prozedur [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), die den Systemtabellen einen Eintrag für ein Sicherungsmedium hinzufügt, nicht die Dateizugriffsberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="281ec-116">However, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), which adds an entry for a backup device in the system tables, does not check file access permissions.</span></span> <span data-ttu-id="281ec-117">Solche Probleme mit der physischen Datei des Sicherungsmediums treten möglicherweise erst auf, wenn auf die physische Ressource zugegriffen wird, um einen Sicherungs- oder Wiederherstellungsvorgang auszuführen.</span><span class="sxs-lookup"><span data-stu-id="281ec-117">Such problems on the backup device's physical file may not appear until the physical resource is accessed when the backup or restore is attempted.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="281ec-118">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="281ec-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-set-the-expiration-date-on-a-backup"></a><span data-ttu-id="281ec-119">So legen Sie das Ablaufdatum für eine Sicherung fest</span><span class="sxs-lookup"><span data-stu-id="281ec-119">To set the expiration date on a backup</span></span>  
  
1.  <span data-ttu-id="281ec-120">Klicken Sie nach dem Herstellen einer Verbindung mit der entsprechenden Instanz von [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)] im Objekt-Explorer auf den Servernamen, um die Serverstruktur zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="281ec-120">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="281ec-121">Erweitern Sie **Datenbanken**, und wählen Sie je nach Datenbank eine Benutzerdatenbank aus, oder erweitern Sie **Systemdatenbanken** , und wählen Sie eine Systemdatenbank aus.</span><span class="sxs-lookup"><span data-stu-id="281ec-121">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="281ec-122">Klicken Sie mit der rechten Maustaste auf die Datenbank, zeigen Sie auf **Tasks**, und klicken Sie dann auf **Sichern**.</span><span class="sxs-lookup"><span data-stu-id="281ec-122">Right-click the database, point to **Tasks**, and then click **Back Up**.</span></span> <span data-ttu-id="281ec-123">Das Dialogfeld **Datenbank sichern** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="281ec-123">The **Back Up Database** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="281ec-124">Geben Sie auf der Seite **Allgemein** für **Sicherungssatz läuft ab**ein Ablaufdatum an, um anzugeben, wann der Sicherungssatz durch eine andere Sicherung überschrieben werden kann:</span><span class="sxs-lookup"><span data-stu-id="281ec-124">On the **General** page, for **Backup set will expire**, specify an expiration date to indicate when the backup set can be overwritten by another backup:</span></span>  
  
    -   <span data-ttu-id="281ec-125">Wenn der Sicherungssatz nach einer bestimmten Anzahl von Tagen ablaufen soll, klicken Sie auf **Nach** (die Standardoption), und geben Sie an, nach wie vielen Tagen der Sicherungssatz abläuft.</span><span class="sxs-lookup"><span data-stu-id="281ec-125">To have the backup set expire after a specific number of days, click **After** (the default option), and enter the number of days after set creation that the set will expire.</span></span> <span data-ttu-id="281ec-126">Dieser Wert kann zwischen 0 und 99999 Tagen liegen. Ein Wert von 0 Tagen bedeutet, dass der Sicherungssatz nicht abläuft.</span><span class="sxs-lookup"><span data-stu-id="281ec-126">This value can be from 0 to 99999 days; a value of 0 days means that the backup set will never expire.</span></span>  
  
         <span data-ttu-id="281ec-127">Der Standardwert wird im Dialogfeld **Servereigenschaften** (Seite **Datenbankeinstellungen** ) über die Option**Standardbeibehaltung für Sicherungsmedien (in Tagen)** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="281ec-127">The default value is set in the **Default backup media retention (in days)** option of the **Server Properties** dialog box (**Database Settings** page).</span></span> <span data-ttu-id="281ec-128">Klicken Sie hierzu mit der rechten Maustaste auf den Servernamen im Objekt-Explorer, und wählen Sie Eigenschaften aus. Wählen Sie anschließend die Seite **Datenbankeinstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="281ec-128">To access this, right-click the server name in Object Explorer and select properties; then select the **Database Settings** page.</span></span>  
  
    -   <span data-ttu-id="281ec-129">Zum Speichern des Sicherungssatzes an einem bestimmten Datum klicken Sie auf **Am**. Geben Sie das Datum ein, an dem der Sicherungssatz abläuft.</span><span class="sxs-lookup"><span data-stu-id="281ec-129">To have the backup set expire on a specific date, click **On**, and enter the date on which the set will expire.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="281ec-130">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="281ec-130">Using Transact-SQL</span></span>  
  
#### <a name="to-set-the-expiration-date-on-a-backup"></a><span data-ttu-id="281ec-131">So legen Sie das Ablaufdatum für eine Sicherung fest</span><span class="sxs-lookup"><span data-stu-id="281ec-131">To set the expiration date on a backup</span></span>  
  
1.  <span data-ttu-id="281ec-132">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="281ec-132">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="281ec-133">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="281ec-133">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="281ec-134">Geben Sie in der [BACKUP](/sql/t-sql/statements/backup-transact-sql) -Anweisung entweder die Option EXPIREDATE oder RETAINDAYS an, um zu bestimmen, wann der die Sicherung von [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)] überschrieben werden kann.</span><span class="sxs-lookup"><span data-stu-id="281ec-134">In the [BACKUP](/sql/t-sql/statements/backup-transact-sql) statement, specify either the EXPIREDATE or RETAINDAYS option to determine when the [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)] can overwrite the backup.</span></span> <span data-ttu-id="281ec-135">Wenn keine der Optionen angegeben wird, wird das Ablaufdatum durch die Serverkonfigurationseinstellung [Medienbeibehaltung](../../database-engine/configure-windows/configure-the-media-retention-server-configuration-option.md) bestimmt.</span><span class="sxs-lookup"><span data-stu-id="281ec-135">If neither option is specified, the expiration date is determined by the [media retention](../../database-engine/configure-windows/configure-the-media-retention-server-configuration-option.md) server configuration setting.</span></span> <span data-ttu-id="281ec-136">In diesem Beispiel wird die `EXPIREDATE` -Option verwendet, um das Ablaufdatum auf den 30. Juni 2015 festzulegen (`6/30/2015`).</span><span class="sxs-lookup"><span data-stu-id="281ec-136">This example uses the `EXPIREDATE` option to specify an expiration date of June 30, 2015 (`6/30/2015`).</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
BACKUP DATABASE AdventureWorks2012  
 TO DISK = 'Z:\SQLServerBackups\AdventureWorks2012.Bak'  
   WITH EXPIREDATE = '6/30/2015' ;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="281ec-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="281ec-137">See Also</span></span>  
 <span data-ttu-id="281ec-138">[Erstellen einer vollständigen Datenbanksicherung &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="281ec-138">[Create a Full Database Backup &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md) </span></span>  
 <span data-ttu-id="281ec-139">[Sichern von Dateien und Dateigruppen &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="281ec-139">[Back Up Files and Filegroups &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span></span>  
 <span data-ttu-id="281ec-140">[Sichern eines Transaktionsprotokolls &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="281ec-140">[Back Up a Transaction Log &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span></span>  
 [<span data-ttu-id="281ec-141">Erstellen einer differenziellen Datenbanksicherung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="281ec-141">Create a Differential Database Backup &#40;SQL Server&#41;</span></span>](create-a-differential-database-backup-sql-server.md)  
  
  
