---
title: Konfigurieren der Serverkonfigurationsoption „Wiederherstellungsintervall“ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- restoring recovery interval [SQL Server]
- checkpoints [SQL Server]
- recovery interval option [SQL Server]
- default recovery interval option
- time [SQL Server], recovery interval
- interval for recovery [SQL Server]
- maximum number of minutes per database recovery
- recovery [SQL Server], recovery interval option
ms.assetid: e4734b3b-8fbe-4b65-9c48-91b5a3dd18e1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 560d514ba8dd1503b59b3b59ecf404d876e24cd2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609439"
---
# <a name="configure-the-recovery-interval-server-configuration-option"></a><span data-ttu-id="90d07-102">Konfigurieren der Serverkonfigurationsoption Wiederherstellungsintervall</span><span class="sxs-lookup"><span data-stu-id="90d07-102">Configure the recovery interval Server Configuration Option</span></span>
  <span data-ttu-id="90d07-103">In diesem Thema wird beschrieben, wie die Serverkonfigurationsoption **Wiederherstellungsintervall** in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="90d07-103">This topic describes how to configure the **recovery interval** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="90d07-104">Mit der Option **Wiederherstellungsintervall** wird eine Obergrenze für die Zeitdauer festgelegt, wie lange das Wiederherstellen einer Datenbank dauern darf.</span><span class="sxs-lookup"><span data-stu-id="90d07-104">The **recovery interval** option defines an upper limit on the time recovering a database should take.</span></span> <span data-ttu-id="90d07-105">[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] verwendet den für diese Option angegebenen Wert, um annäherungsweise zu ermitteln, wie häufig [automatische Prüfpunkte](../../relational-databases/logs/database-checkpoints-sql-server.md) für die jeweilige Datenbank ausgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="90d07-105">The [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] uses the value specified for this option to determine approximately how often [automatic checkpoints](../../relational-databases/logs/database-checkpoints-sql-server.md) to issue automatic checkpoints on a given database.</span></span>  
  
 <span data-ttu-id="90d07-106">Der Standardwert für das Wiederherstellungsintervall ist 0, was es dem [!INCLUDE[ssDE](../../includes/ssde-md.md)] ermöglicht, das Wiederherstellungsintervall automatisch zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="90d07-106">The default recovery-interval value is 0, which allows the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to automatically configure the recovery interval.</span></span> <span data-ttu-id="90d07-107">In der Regel geht mit dem standardmäßigen Wiederherstellungsintervall etwa ein automatischer Prüfpunkt pro Minute für aktive Datenbanken einher, was zu Wiederherstellungszeiten von unter einer Minute führt.</span><span class="sxs-lookup"><span data-stu-id="90d07-107">Typically, the default recovery interval results in automatic checkpoints occurring approximately once a minute for active databases and a recovery time of less than one minute.</span></span> <span data-ttu-id="90d07-108">Höhere Werte geben die ungefähre maximale Wiederherstellungszeit in Minuten an.</span><span class="sxs-lookup"><span data-stu-id="90d07-108">Higher values indicate the approximate maximum recovery time, in minutes.</span></span> <span data-ttu-id="90d07-109">Wenn Sie beispielsweise das Wiederherstellungsintervall auf 3 festlegen, bedeutet dies eine maximale Wiederherstellungszeit von ungefähr drei Minuten.</span><span class="sxs-lookup"><span data-stu-id="90d07-109">For example, setting the recovery interval to 3 indicates a maximum recovery time of approximately three minutes.</span></span>  
  
 <span data-ttu-id="90d07-110">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="90d07-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="90d07-111">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="90d07-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="90d07-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="90d07-112">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="90d07-113">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="90d07-113">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="90d07-114">Security</span><span class="sxs-lookup"><span data-stu-id="90d07-114">Security</span></span>](#Security)  
  
-   <span data-ttu-id="90d07-115">**So konfigurieren Sie die Wiederherstellungsintervall-Serverkonfigurationsoption mit**</span><span class="sxs-lookup"><span data-stu-id="90d07-115">**To Configure the recovery interval Server Configuration Option, using:**</span></span>  
  
     [<span data-ttu-id="90d07-116">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="90d07-116">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="90d07-117">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="90d07-117">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="90d07-118">**Nachverfolgung:**  [Nach dem Konfigurieren der Option „Wiederherstellungsintervall“](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="90d07-118">**Follow Up:**  [After you configure the recovery interval option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="90d07-119">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="90d07-119">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="90d07-120">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="90d07-120">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="90d07-121">Das Wiederherstellungsintervall wirkt sich nur auf Datenbanken aus, die die standardmäßige Zielwiederherstellungszeit (0) verwenden.</span><span class="sxs-lookup"><span data-stu-id="90d07-121">The recovery interval affects only databases that use the default target recovery time (0).</span></span> <span data-ttu-id="90d07-122">Um das Serverwiederherstellungsintervall für eine Datenbank zu überschreiben, konfigurieren Sie für die Datenbank eine nicht standardmäßige Zielwiederherstellungszeit.</span><span class="sxs-lookup"><span data-stu-id="90d07-122">To override the server recovery interval on a database, configure a non-default target recovery time on the database.</span></span> <span data-ttu-id="90d07-123">Weitere Informationen finden Sie unter [Ändern der Zielwiederherstellungszeit einer Datenbank &#40;SQL Server&#41;](../../relational-databases/logs/change-the-target-recovery-time-of-a-database-sql-server.md)konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="90d07-123">For more information, see [Change the Target Recovery Time of a Database &#40;SQL Server&#41;](../../relational-databases/logs/change-the-target-recovery-time-of-a-database-sql-server.md).</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="90d07-124">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="90d07-124">Recommendations</span></span>  
  
-   <span data-ttu-id="90d07-125">Diese Option ist eine erweiterte Option und sollte ausschließlich von einem erfahrenen Datenbankadministrator oder einem zertifizierten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Techniker geändert werden.</span><span class="sxs-lookup"><span data-stu-id="90d07-125">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="90d07-126">In der Regel empfiehlt es sich, das Wiederherstellungsintervall bei 0 zu belassen, falls keine Leistungsprobleme auftreten.</span><span class="sxs-lookup"><span data-stu-id="90d07-126">Typically, we recommend that you keep the recovery interval at 0, unless you experience performance problems.</span></span> <span data-ttu-id="90d07-127">Wenn Sie die Einstellung für das Wiederherstellungsintervall erhöhen möchten, empfehlen wir eine schrittweise Erhöhung des entsprechenden Werts. Werten Sie zudem die Auswirkungen der jeweiligen stufenweisen Erhöhung auf die Wiederherstellungsleistung aus.</span><span class="sxs-lookup"><span data-stu-id="90d07-127">If you decide to increase the recovery-interval setting, we recommend increasing it gradually by small increments and evaluating the effect of each incremental increase on recovery performance.</span></span>  
  
-   <span data-ttu-id="90d07-128">Wenn Sie **sp_configure** zum Ändern des Werts der Option **Wiederherstellungsintervall** auf mehr als 60 (Minuten) verwenden, sollten Sie RECONFIGURE WITH OVERRIDE angeben.</span><span class="sxs-lookup"><span data-stu-id="90d07-128">If you use **sp_configure** to change the value of the **recovery interval** option to more than 60 (minutes), specify RECONFIGURE WITH OVERRIDE.</span></span> <span data-ttu-id="90d07-129">Mit WITH OVERRIDE wird die Überprüfung des Konfigurationswerts deaktiviert (für Werte, die nicht gültig sind oder die keine empfohlenen Werte sind).</span><span class="sxs-lookup"><span data-stu-id="90d07-129">WITH OVERRIDE disables configuration value checking (for values that are not valid or are nonrecommended values).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="90d07-130">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="90d07-130">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="90d07-131">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="90d07-131">Permissions</span></span>  
 <span data-ttu-id="90d07-132">Die Ausführungsberechtigungen für **sp_configure** ohne Parameter oder nur mit dem ersten Parameter werden standardmäßig allen Benutzern erteilt.</span><span class="sxs-lookup"><span data-stu-id="90d07-132">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="90d07-133">Zum Ausführen von **sp_configure** mit beiden Parametern zum Ändern einer Konfigurationsoption oder zum Ausführen der RECONFIGURE-Anweisung muss einem Benutzer die ALTER SETTINGS-Berechtigung auf Serverebene erteilt worden sein.</span><span class="sxs-lookup"><span data-stu-id="90d07-133">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="90d07-134">Die ALTER SETTINGS-Berechtigung ist in den festen Serverrollen **sysadmin** und **serveradmin** eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="90d07-134">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="90d07-135">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="90d07-135">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="90d07-136">**So legen Sie das Wiederherstellungsintervall fest**</span><span class="sxs-lookup"><span data-stu-id="90d07-136">**To set the recovery interval**</span></span>  
  
1.  <span data-ttu-id="90d07-137">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf eine Serverinstanz, und wählen Sie **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="90d07-137">In Object Explorer, right-click server instance and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="90d07-138">Klicken Sie auf den Knoten **Datenbankeinstellungen** .</span><span class="sxs-lookup"><span data-stu-id="90d07-138">Click the **Database settings** node.</span></span>  
  
3.  <span data-ttu-id="90d07-139">Geben Sie unter **Wiederherstellung**im Feld **Wiederherstellungsintervall (Minuten)** einen Wert zwischen 0 und 32767 ein, oder wählen Sie einen Wert aus, um die maximale Zeitdauer in Minuten festzulegen, die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] beim Starten zum Wiederherstellen jeder Datenbank verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="90d07-139">Under **Recovery**, in the **Recovery interval (minutes)** box, type or select a value from 0 through 32767 to set the maximum amount of time, in minutes, that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] should spend recovering each database at startup.</span></span> <span data-ttu-id="90d07-140">Die Standardeinstellung ist 0; bei dieser Einstellung wird die Option automatisch von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="90d07-140">The default is 0, indicating automatic configuration by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="90d07-141">In der Praxis bedeutet dies eine Wiederherstellungszeit von weniger als einer Minute und das Auftreten eines Prüfpunktes in Abständen von ungefähr einer Minute bei aktiven Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="90d07-141">In practice, this means a recovery time of less than one minute and a checkpoint approximately every one minute for active databases.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="90d07-142">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="90d07-142">Using Transact-SQL</span></span>  
  
#### <a name="to-set-the-recovery-interval"></a><span data-ttu-id="90d07-143">So legen Sie das Wiederherstellungsintervall fest</span><span class="sxs-lookup"><span data-stu-id="90d07-143">To set the recovery interval</span></span>  
  
1.  <span data-ttu-id="90d07-144">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="90d07-144">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="90d07-145">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="90d07-145">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="90d07-146">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="90d07-146">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="90d07-147">In diesem Beispiel wird gezeigt, wie [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) verwendet wird, um den Wert der Option `recovery interval` auf `3` Minuten festzulegen.</span><span class="sxs-lookup"><span data-stu-id="90d07-147">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `recovery interval` option to `3` minutes.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'recovery interval', 3 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="90d07-148">Weitere Informationen finden Sie unter [Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md)angezeigt oder konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="90d07-148">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-recovery-internal-option"></a><a name="FollowUp"></a><span data-ttu-id="90d07-149">Nächster Schritt: Nach dem Konfigurieren der Option „Wiederherstellungsintervall“</span><span class="sxs-lookup"><span data-stu-id="90d07-149">Follow Up: After you configure the recovery internal option</span></span>  
 <span data-ttu-id="90d07-150">Die Einstellung tritt ohne Neustarten des Servers sofort in Kraft.</span><span class="sxs-lookup"><span data-stu-id="90d07-150">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90d07-151">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="90d07-151">See Also</span></span>  
 <span data-ttu-id="90d07-152">[Ändern der Zielwiederherstellungszeit einer Datenbank &#40;SQL Server&#41;](../../relational-databases/logs/change-the-target-recovery-time-of-a-database-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="90d07-152">[Change the Target Recovery Time of a Database &#40;SQL Server&#41;](../../relational-databases/logs/change-the-target-recovery-time-of-a-database-sql-server.md) </span></span>  
 <span data-ttu-id="90d07-153">[Datenbankprüfpunkte &#40;SQL Server&#41;](../../relational-databases/logs/database-checkpoints-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="90d07-153">[Database Checkpoints &#40;SQL Server&#41;](../../relational-databases/logs/database-checkpoints-sql-server.md) </span></span>  
 <span data-ttu-id="90d07-154">[Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="90d07-154">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="90d07-155">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="90d07-155">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 <span data-ttu-id="90d07-156">[Erweiterte Optionen anzeigen (Serverkonfigurationsoption)](show-advanced-options-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="90d07-156">[show advanced options Server Configuration Option](show-advanced-options-server-configuration-option.md) </span></span>  
 [<span data-ttu-id="90d07-157">RECONFIGURE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="90d07-157">RECONFIGURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/reconfigure-transact-sql)  
  
  
