---
title: Konfigurieren der Serverkonfigurationsoption „Medienbeibehaltung“ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- backup retention duration [SQL Server]
- backup sets [SQL Server], retention duration
- media retention option
ms.assetid: 12e9fe6a-20a5-4c6e-9cc9-d500c003b70a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 092e0a2b5cfc30fd2d2362645fc1242bf4a1651e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616176"
---
# <a name="configure-the-media-retention-server-configuration-option"></a><span data-ttu-id="8513e-102">Konfigurieren der Serverkonfigurationsoption Medienbeibehaltung</span><span class="sxs-lookup"><span data-stu-id="8513e-102">Configure the media retention Server Configuration Option</span></span>
  <span data-ttu-id="8513e-103">In diesem Thema wird beschrieben, wie die Serverkonfigurationsoption **Medienbeibehaltung** in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]konfiguriert werden kann.</span><span class="sxs-lookup"><span data-stu-id="8513e-103">This topic describes how to configure the **media retention** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="8513e-104">Die Option **Medienbeibehaltung** gibt den Zeitraum an, wie lange jeder Sicherungssatz beibehalten werden soll.</span><span class="sxs-lookup"><span data-stu-id="8513e-104">The **media retention** option specifies the length of time to retain each backup set.</span></span> <span data-ttu-id="8513e-105">Mithilfe dieser Option wird verhindert, dass Sicherungen vor Ablauf der angegebenen Anzahl von Tagen überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="8513e-105">The option helps protect backups from being overwritten until the specified number of days has elapsed.</span></span> <span data-ttu-id="8513e-106">Nachdem Sie die Option **Medienbeibehaltung** konfiguriert haben, müssen Sie nicht jedes Mal beim Ausführen einer Sicherung den Zeitraum angeben, wie lange die Systemsicherungen beibehalten werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8513e-106">After you configure **media retention** option, you do not have to specify the length of time to retain system backups each time you perform a backup.</span></span> <span data-ttu-id="8513e-107">Der Standardwert ist 0 Tage, und der Maximalwert ist 365 Tage.</span><span class="sxs-lookup"><span data-stu-id="8513e-107">The default value is 0 days, and the maximum value is 365 days.</span></span>  
  
 <span data-ttu-id="8513e-108">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="8513e-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="8513e-109">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="8513e-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="8513e-110">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="8513e-110">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="8513e-111">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="8513e-111">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="8513e-112">Security</span><span class="sxs-lookup"><span data-stu-id="8513e-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="8513e-113">**So konfigurieren Sie die Option Medienbeibehaltung mit:**</span><span class="sxs-lookup"><span data-stu-id="8513e-113">**To configure the media retention option, using:**</span></span>  
  
     [<span data-ttu-id="8513e-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8513e-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="8513e-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8513e-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="8513e-116">**Nachverfolgung:**  [Nach dem Konfigurieren der Option „Medienbeibehaltung“](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="8513e-116">**Follow Up:**  [After you configure the media retention option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8513e-117">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="8513e-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="8513e-118">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="8513e-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="8513e-119">Wenn Sie das Sicherungsmedium verwenden, bevor die festgelegte Anzahl von Tagen verstrichen ist, wird von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] eine Warnmeldung ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="8513e-119">If you use the backup medium before the set number of days has passed, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] issues a warning message.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="8513e-120">wird nur dann eine Warnmeldung ausgegeben, wenn Sie die Standardeinstellung ändern.</span><span class="sxs-lookup"><span data-stu-id="8513e-120">does not issue a warning unless you change the default.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="8513e-121">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="8513e-121">Recommendations</span></span>  
  
-   <span data-ttu-id="8513e-122">Diese Option ist eine erweiterte Option und sollte ausschließlich von einem erfahrenen Datenbankadministrator oder einem zertifizierten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Techniker geändert werden.</span><span class="sxs-lookup"><span data-stu-id="8513e-122">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="8513e-123">Die Option **Medienbeibehaltung** kann außer Kraft gesetzt werden, indem die RETAINDAYS-Klausel der [BACKUP](/sql/t-sql/statements/backup-transact-sql) -Anweisung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8513e-123">The **media retention** option can be overridden by using the RETAINDAYS clause of the [BACKUP](/sql/t-sql/statements/backup-transact-sql) statement.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8513e-124">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="8513e-124">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8513e-125">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="8513e-125">Permissions</span></span>  
 <span data-ttu-id="8513e-126">Die Ausführungsberechtigungen für **sp_configure** ohne Parameter oder nur mit dem ersten Parameter werden standardmäßig allen Benutzern erteilt.</span><span class="sxs-lookup"><span data-stu-id="8513e-126">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="8513e-127">Zum Ausführen von **sp_configure** mit beiden Parametern zum Ändern einer Konfigurationsoption oder zum Ausführen der RECONFIGURE-Anweisung muss einem Benutzer die ALTER SETTINGS-Berechtigung auf Serverebene erteilt worden sein.</span><span class="sxs-lookup"><span data-stu-id="8513e-127">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="8513e-128">Die ALTER SETTINGS-Berechtigung ist in den festen Serverrollen **sysadmin** und **serveradmin** eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="8513e-128">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8513e-129">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8513e-129">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-media-retention-option"></a><span data-ttu-id="8513e-130">So konfigurieren Sie die Option Medienbeibehaltung</span><span class="sxs-lookup"><span data-stu-id="8513e-130">To configure the media retention option</span></span>  
  
1.  <span data-ttu-id="8513e-131">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf einen Server, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="8513e-131">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="8513e-132">Klicken Sie auf den Knoten **Datenbankeinstellungen** .</span><span class="sxs-lookup"><span data-stu-id="8513e-132">Click the **Database settings** node.</span></span>  
  
3.  <span data-ttu-id="8513e-133">Geben Sie im Feld **Standardbeibehaltungsdauer für Sicherungsmedien (in Tagen)** unter **Sicherung/Wiederherstellung** einen Wert zwischen 0 und 365 ein, oder wählen Sie einen Wert aus, um in Tagen festzulegen, wie lange das Sicherungsmedium nach dem Sichern einer Datenbank oder eines Transaktionsprotokolls beibehalten werden soll.</span><span class="sxs-lookup"><span data-stu-id="8513e-133">Under **Backup/Restore**, in the **Default backup media retention** box, type or select a value from 0 through 365 to set the number of days the backup medium will be retained after a database or transaction log backup.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="8513e-134">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8513e-134">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-media-retention-option"></a><span data-ttu-id="8513e-135">So konfigurieren Sie die Option Medienbeibehaltung</span><span class="sxs-lookup"><span data-stu-id="8513e-135">To configure the media retention option</span></span>  
  
1.  <span data-ttu-id="8513e-136">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="8513e-136">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="8513e-137">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="8513e-137">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8513e-138">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="8513e-138">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="8513e-139">In diesem Beispiel wird gezeigt, wie [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) verwendet wird, um den Wert der Option `media retention` auf `60` Tage festzulegen.</span><span class="sxs-lookup"><span data-stu-id="8513e-139">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `media retention` option to `60` days.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'media retention', 60 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="8513e-140">Weitere Informationen finden Sie unter [Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md)angezeigt oder konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="8513e-140">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-media-retention-option"></a><a name="FollowUp"></a><span data-ttu-id="8513e-141">Nächster Schritt: Nach dem Konfigurieren der Option „Medienbeibehaltung“</span><span class="sxs-lookup"><span data-stu-id="8513e-141">Follow Up: After you configure the media retention option</span></span>  
 <span data-ttu-id="8513e-142">Die Einstellung tritt ohne Neustarten des Servers sofort in Kraft.</span><span class="sxs-lookup"><span data-stu-id="8513e-142">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8513e-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8513e-143">See Also</span></span>  
 <span data-ttu-id="8513e-144">[Sichern und Wiederherstellen von SQL Server-Datenbanken](../../relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="8513e-144">[Back Up and Restore of SQL Server Databases](../../relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases.md) </span></span>  
 <span data-ttu-id="8513e-145">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8513e-145">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="8513e-146">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8513e-146">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="8513e-147">[Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="8513e-147">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="8513e-148">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8513e-148">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
