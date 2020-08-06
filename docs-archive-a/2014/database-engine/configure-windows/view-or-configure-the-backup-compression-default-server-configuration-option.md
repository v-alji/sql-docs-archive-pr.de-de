---
title: Anzeigen oder Konfigurieren der Serverkonfigurationsoption „Standardeinstellung für die Sicherungskomprimierung“ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Management Studio [SQL Server], backup compression default option
- backup compression [SQL Server], backup compression default Option
ms.assetid: 23029395-3e93-4c29-b7d6-e5a47a3526ff
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f02458c069d7c155b199e24feb7ef028ae0f258a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622874"
---
# <a name="view-or-configure-the-backup-compression-default-server-configuration-option"></a><span data-ttu-id="f2407-102">Anzeigen oder Konfigurieren der Serverkonfigurationsoption Standardeinstellung für die Sicherungskomprimierung</span><span class="sxs-lookup"><span data-stu-id="f2407-102">View or Configure the backup compression default Server Configuration Option</span></span>
  <span data-ttu-id="f2407-103">In diesem Thema wird beschrieben, wie die Serverkonfigurationsoption **backup compression default** in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]angezeigt oder konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="f2407-103">This topic describes how to view or configure the **backup compression default** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="f2407-104">Mit der Option **backup compression default** wird bestimmt, ob die Serverinstanz standardmäßig komprimierte Sicherungen erstellt.</span><span class="sxs-lookup"><span data-stu-id="f2407-104">The **backup compression default** option determines whether the server instance creates compressed backups by default.</span></span> <span data-ttu-id="f2407-105">Wenn [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installiert ist, ist die Option **backup compression default** deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="f2407-105">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed, the **backup compression default** option is off.</span></span>  
  
 <span data-ttu-id="f2407-106">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="f2407-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f2407-107">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="f2407-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f2407-108">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="f2407-108">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="f2407-109">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="f2407-109">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="f2407-110">Security</span><span class="sxs-lookup"><span data-stu-id="f2407-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f2407-111">**So zeigen Sie die Option backup compression default an und konfigurieren sie mit:**</span><span class="sxs-lookup"><span data-stu-id="f2407-111">**To view or configure the backup compression default option, using:**</span></span>  
  
     [<span data-ttu-id="f2407-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f2407-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="f2407-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f2407-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="f2407-114">**Nachverfolgung:**  [Nach dem Konfigurieren der Option „Komprimierungsstandard für Sicherung“](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="f2407-114">**Follow Up:**  [After you configure the backup compression default option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f2407-115">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="f2407-115">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="f2407-116">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="f2407-116">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="f2407-117">Die Sicherungskomprimierung ist nicht in allen Editionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f2407-117">Backup compression is not available in all editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f2407-118">Weitere Informationen finden Sie unter [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="f2407-118">For more information, see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
-   <span data-ttu-id="f2407-119">Standardmäßig steigt die CPU-Nutzung durch die Komprimierung erheblich, und die bei der Komprimierung zusätzlich verbrauchten CPU-Ressourcen können sich negativ auf gleichzeitige Vorgänge auswirken.</span><span class="sxs-lookup"><span data-stu-id="f2407-119">By default, compression significantly increases CPU usage, and the additional CPU consumed by the compression process might adversely impact concurrent operations.</span></span> <span data-ttu-id="f2407-120">Daher ist es u. U. sinnvoll, in einer Sitzung, bei der die CPU-Nutzung durch die [Ressourcenkontrolle](../../relational-databases/resource-governor/resource-governor.md) eingeschränkt ist, komprimierte Sicherungen mit niedriger Priorität zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f2407-120">Therefore, you might want to create low-priority compressed backups in a session whose CPU usage is limited by [Resource Governor](../../relational-databases/resource-governor/resource-governor.md).</span></span> <span data-ttu-id="f2407-121">Weitere Informationen finden Sie unter [Einschränken der CPU-Nutzung durch die Sicherungskomprimierung mithilfe der Ressourcenkontrolle &#40;Transact-SQL&#41;](../../relational-databases/backup-restore/use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="f2407-121">For more information, see [Use Resource Governor to Limit CPU Usage by Backup Compression &#40;Transact-SQL&#41;](../../relational-databases/backup-restore/use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md).</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="f2407-122">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="f2407-122">Recommendations</span></span>  
  
-   <span data-ttu-id="f2407-123">Wenn Sie eine einzelne Sicherung, eine Protokollversandkonfiguration oder einen Wartungsplan erstellen, können Sie die Standardeinstellung auf Serverebene überschreiben.</span><span class="sxs-lookup"><span data-stu-id="f2407-123">When you are creating an individual backup, configuring a log shipping configuration, or creating a maintenance plan, you can override the server-level default.</span></span>  
  
-   <span data-ttu-id="f2407-124">Die Komprimierung von Sicherungen wird sowohl bei Datenträgersicherungsmedien als auch bei Bandsicherungsgeräten unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f2407-124">Backup compression is supported for both disk backup devices and tape backup devices.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f2407-125">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="f2407-125">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f2407-126">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="f2407-126">Permissions</span></span>  
 <span data-ttu-id="f2407-127">Die Ausführungsberechtigungen für **sp_configure** ohne Parameter oder nur mit dem ersten Parameter werden standardmäßig allen Benutzern erteilt.</span><span class="sxs-lookup"><span data-stu-id="f2407-127">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="f2407-128">Zum Ausführen von **sp_configure** mit beiden Parametern zum Ändern einer Konfigurationsoption oder zum Ausführen der RECONFIGURE-Anweisung muss einem Benutzer die ALTER SETTINGS-Berechtigung auf Serverebene erteilt worden sein.</span><span class="sxs-lookup"><span data-stu-id="f2407-128">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="f2407-129">Die ALTER SETTINGS-Berechtigung ist in den festen Serverrollen **sysadmin** und **serveradmin** eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="f2407-129">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f2407-130">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f2407-130">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-or-configure-the-backup-compression-default-option"></a><span data-ttu-id="f2407-131">So zeigen Sie die Option 'backup compression default' an und konfigurieren sie</span><span class="sxs-lookup"><span data-stu-id="f2407-131">To view or configure the backup compression default option</span></span>  
  
1.  <span data-ttu-id="f2407-132">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf einen Server, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="f2407-132">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="f2407-133">Klicken Sie auf den Knoten **Datenbankeinstellungen** .</span><span class="sxs-lookup"><span data-stu-id="f2407-133">Click the **Database settings** node.</span></span>  
  
3.  <span data-ttu-id="f2407-134">Unter **Sichern und Wiederherstellen**wird für **Sicherung komprimieren** die aktuelle Einstellung der Option **backup compression default** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f2407-134">Under **Backup and restore**, **Compress backup** shows the current setting of the **backup compression default** option.</span></span> <span data-ttu-id="f2407-135">Durch diese Einstellung wird die Standardeinstellung für die Sicherungskomprimierung auf Serverebene wie folgt festgelegt:</span><span class="sxs-lookup"><span data-stu-id="f2407-135">This setting determines the server-level default for compressing backups, as follows:</span></span>  
  
    -   <span data-ttu-id="f2407-136">Wenn das Feld **Sicherung komprimieren** leer ist, werden neue Sicherungen nicht komprimiert.</span><span class="sxs-lookup"><span data-stu-id="f2407-136">If the **Compress backup** box is blank, new backups are uncompressed by default.</span></span>  
  
    -   <span data-ttu-id="f2407-137">Wenn das Kontrollkästchen **Sicherung komprimieren** aktiviert ist, werden neue Sicherungen standardmäßig komprimiert.</span><span class="sxs-lookup"><span data-stu-id="f2407-137">If the **Compress backup** box is checked, new backups are compressed by default.</span></span>  
  
     <span data-ttu-id="f2407-138">Wenn Sie Mitglied der festen Serverrolle **sysadmin** bzw. **serveradmin** sind, können Sie die Standardeinstellung auch durch Klicken auf das Kontrollkästchen **Sicherung komprimieren** ändern.</span><span class="sxs-lookup"><span data-stu-id="f2407-138">If you are a member of the **sysadmin** or **serveradmin** fixed server role, you can also change the default setting by clicking the **Compress backup** box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="f2407-139">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f2407-139">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-backup-compression-default-option"></a><span data-ttu-id="f2407-140">So zeigen Sie die Option backup compression default an</span><span class="sxs-lookup"><span data-stu-id="f2407-140">To view the backup compression default option</span></span>  
  
1.  <span data-ttu-id="f2407-141">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="f2407-141">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f2407-142">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="f2407-142">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f2407-143">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="f2407-143">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="f2407-144">In diesem Beispiel wird die Katalogsicht [sys.configurations](/sql/relational-databases/system-catalog-views/sys-configurations-transact-sql) abgefragt, um den Wert für `backup compression default`zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="f2407-144">This example queries the [sys.configurations](/sql/relational-databases/system-catalog-views/sys-configurations-transact-sql) catalog view to determine the value for `backup compression default`.</span></span> <span data-ttu-id="f2407-145">Der Wert 0 bedeutet, dass die Sicherungskomprimierung deaktiviert ist, und der Wert 1 bedeutet, dass die Sicherungskomprimierung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="f2407-145">A value of 0 means that backup compression is off, and a value of 1 means that backup compression is enabled.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
SELECT value   
FROM sys.configurations   
WHERE name = 'backup compression default' ;  
GO  
  
```  
  
#### <a name="to-configure-the-backup-compression-default-option"></a><span data-ttu-id="f2407-146">So konfigurieren Sie die Option backup compression default</span><span class="sxs-lookup"><span data-stu-id="f2407-146">To configure the backup compression default option</span></span>  
  
1.  <span data-ttu-id="f2407-147">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="f2407-147">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f2407-148">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="f2407-148">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f2407-149">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="f2407-149">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="f2407-150">In diesem Beispiel wird gezeigt, wie die Serverinstanz mithilfe von [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) so konfiguriert wird, dass standardmäßig komprimierte Sicherungen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="f2407-150">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to configure the server instance to create compressed backups by default.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
EXEC sp_configure 'backup compression default', 1 ;  
RECONFIGURE WITH OVERRIDE ;  
GO  
  
```  
  
 <span data-ttu-id="f2407-151">Weitere Informationen finden Sie unter [Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md)angezeigt oder konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="f2407-151">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-backup-compression-default-option"></a><a name="FollowUp"></a><span data-ttu-id="f2407-152">Nächster Schritt: Nach dem Konfigurieren der Option „Komprimierungsstandard für Sicherung“</span><span class="sxs-lookup"><span data-stu-id="f2407-152">Follow Up: After you configure the backup compression default option</span></span>  
 <span data-ttu-id="f2407-153">Die Einstellung tritt ohne Neustarten des Servers sofort in Kraft.</span><span class="sxs-lookup"><span data-stu-id="f2407-153">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2407-154">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f2407-154">See Also</span></span>  
 <span data-ttu-id="f2407-155">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f2407-155">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="f2407-156">[Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f2407-156">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="f2407-157">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f2407-157">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="f2407-158">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f2407-158">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="f2407-159">Übersicht über Sicherungen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f2407-159">Backup Overview &#40;SQL Server&#41;</span></span>](../../relational-databases/backup-restore/backup-overview-sql-server.md)  
  
  
