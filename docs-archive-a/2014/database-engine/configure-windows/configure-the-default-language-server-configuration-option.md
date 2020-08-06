---
title: Konfigurieren der Serverkonfigurationsoption „Standardsprache“ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- default language option
ms.assetid: c08c26d8-5a62-487e-a4ee-4c529e4f9287
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b0e62fef112dad2c6c307946bc720adf1f14d82b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724933"
---
# <a name="configure-the-default-language-server-configuration-option"></a><span data-ttu-id="cc612-102">Konfigurieren der Serverkonfigurationsoption Standardsprache</span><span class="sxs-lookup"><span data-stu-id="cc612-102">Configure the default language Server Configuration Option</span></span>
  <span data-ttu-id="cc612-103">In diesem Thema wird beschrieben, wie die Serverkonfigurationsoption **Standardsprache** in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="cc612-103">This topic describes how to configure the **default language** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="cc612-104">Verwenden Sie die Option **Standardsprache** , um die Standardsprache für alle neu erstellten Anmeldenamen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="cc612-104">The **default language** option specifies the default language for all newly created logins.</span></span> <span data-ttu-id="cc612-105">Geben Sie zum Festlegen der Standardsprache den **langid** -Wert der gewünschten Sprache an.</span><span class="sxs-lookup"><span data-stu-id="cc612-105">To set default language, specify the **langid** value of the language you want.</span></span> <span data-ttu-id="cc612-106">Sie können den **langid** -Wert abrufen, indem Sie die **sys.syslanguages** -Kompatibilitätssicht abfragen.</span><span class="sxs-lookup"><span data-stu-id="cc612-106">The **langid** value can be obtained by querying the **sys.syslanguages** compatibility view.</span></span>  
  
 <span data-ttu-id="cc612-107">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="cc612-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="cc612-108">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="cc612-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="cc612-109">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="cc612-109">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="cc612-110">Security</span><span class="sxs-lookup"><span data-stu-id="cc612-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="cc612-111">**So konfigurieren Sie die Option Standardsprache mit:**</span><span class="sxs-lookup"><span data-stu-id="cc612-111">**To configure the default language option, using:**</span></span>  
  
     [<span data-ttu-id="cc612-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cc612-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="cc612-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cc612-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="cc612-114">**Nachverfolgung:**  [Nach dem Konfigurieren der Option „Standardsprache“](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="cc612-114">**Follow Up:**  [After you configure the default language option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="cc612-115">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="cc612-115">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="cc612-116">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="cc612-116">Recommendations</span></span>  
  
-   <span data-ttu-id="cc612-117">Die Standardsprache für einen Anmeldenamen kann mit CREATE LOGIN oder ALTER LOGIN überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="cc612-117">The default language for a login can be overridden by using CREATE LOGIN or ALTER LOGIN.</span></span> <span data-ttu-id="cc612-118">Die Sprache für den Anmeldenamen der Sitzung ist die Standardsprache für die Sitzung, es sei denn, dieser Wert wird für die jeweilige Sitzung mithilfe der Open Database Connectivity (ODBC)- oder OLE DB-APIs überschrieben.</span><span class="sxs-lookup"><span data-stu-id="cc612-118">The default language for a session is the language for that session's login, unless overridden on a per-session basis by using the Open Database Connectivity (ODBC) or OLE DB APIs.</span></span> <span data-ttu-id="cc612-119">Beachten Sie, dass Sie die Option **Standardsprache** nur auf eine Sprachen-ID festlegen können, die in [sys.syslanguages](/sql/relational-databases/system-compatibility-views/sys-syslanguages-transact-sql) (0-32) definiert ist.</span><span class="sxs-lookup"><span data-stu-id="cc612-119">Note that you can only set the **default language** option to a language ID defined in [sys.syslanguages](/sql/relational-databases/system-compatibility-views/sys-syslanguages-transact-sql) (0-32).</span></span> <span data-ttu-id="cc612-120">Bei Verwendung von eigenständigen Datenbanken kann eine Standardsprache mit CREATE DATABASE oder ALTER DATABASE für eine Datenbank und mit CREATE USER oder ALTER USER für Benutzer eigenständiger Datenbanken festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="cc612-120">When you are using contained databases, a default language can be set for a database by using CREATE DATABASE or ALTER DATABASE, and for contained database users by using CREATE USER or ALTER USER.</span></span> <span data-ttu-id="cc612-121">Beim Festlegen von Standardsprachen in einer enthaltenen Datenbank wird der **langid** -Wert, der Sprachenname oder ein in **sys.syslanguages**aufgelistetes Sprachalias akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="cc612-121">Setting default languages in a contained database accepts **langid** value, the language name, or a language alias as listed in **sys.syslanguages**.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="cc612-122">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="cc612-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="cc612-123">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="cc612-123">Permissions</span></span>  
 <span data-ttu-id="cc612-124">Die Ausführungsberechtigungen für **sp_configure** ohne Parameter oder nur mit dem ersten Parameter werden standardmäßig allen Benutzern erteilt.</span><span class="sxs-lookup"><span data-stu-id="cc612-124">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="cc612-125">Zum Ausführen von **sp_configure** mit beiden Parametern zum Ändern einer Konfigurationsoption oder zum Ausführen der RECONFIGURE-Anweisung muss einem Benutzer die ALTER SETTINGS-Berechtigung auf Serverebene erteilt worden sein.</span><span class="sxs-lookup"><span data-stu-id="cc612-125">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="cc612-126">Die ALTER SETTINGS-Berechtigung ist in den festen Serverrollen **sysadmin** und **serveradmin** eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="cc612-126">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="cc612-127">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cc612-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-default-language-option"></a><span data-ttu-id="cc612-128">So konfigurieren Sie die Option Standardsprache</span><span class="sxs-lookup"><span data-stu-id="cc612-128">To configure the default language option</span></span>  
  
1.  <span data-ttu-id="cc612-129">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf einen Server, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="cc612-129">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="cc612-130">Klicken Sie auf den **Sonstige Servereinstellungen** -Knoten.</span><span class="sxs-lookup"><span data-stu-id="cc612-130">Click the **Misc server settings** node.</span></span>  
  
3.  <span data-ttu-id="cc612-131">Wählen Sie im Feld **Standardsprache für den Benutzer** die Sprache, in der [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Systemmeldungen anzeigen soll.</span><span class="sxs-lookup"><span data-stu-id="cc612-131">In the **Default language for users** box, choose the language in which [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] should display system messages.</span></span>  
  
     <span data-ttu-id="cc612-132">Die Standardsprache ist Deutsch.</span><span class="sxs-lookup"><span data-stu-id="cc612-132">The default language is English.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="cc612-133">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cc612-133">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-default-language-option"></a><span data-ttu-id="cc612-134">So konfigurieren Sie die Option Standardsprache</span><span class="sxs-lookup"><span data-stu-id="cc612-134">To configure the default language option</span></span>  
  
1.  <span data-ttu-id="cc612-135">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="cc612-135">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="cc612-136">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="cc612-136">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="cc612-137">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="cc612-137">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="cc612-138">In diesem Beispiel wird gezeigt, wie [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) verwendet wird, um die Option `default language` auf Französisch (`2`) festzulegen.</span><span class="sxs-lookup"><span data-stu-id="cc612-138">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to configure the `default language` option to French (`2`).</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'default language', 2 ;  
GO  
RECONFIGURE ;  
GO  
```  
  
 <span data-ttu-id="cc612-139">Weitere Informationen finden Sie unter [Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md)angezeigt oder konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="cc612-139">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-default-language-option"></a><a name="FollowUp"></a><span data-ttu-id="cc612-140">Nächster Schritt: Nach dem Konfigurieren der Option „Standardsprache“</span><span class="sxs-lookup"><span data-stu-id="cc612-140">Follow Up: After you configure the default language option</span></span>  
 <span data-ttu-id="cc612-141">Die Einstellung tritt ohne Neustarten des Servers sofort in Kraft.</span><span class="sxs-lookup"><span data-stu-id="cc612-141">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc612-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cc612-142">See Also</span></span>  
 <span data-ttu-id="cc612-143">[CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cc612-143">[CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql) </span></span>  
 <span data-ttu-id="cc612-144">[ALTER LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-login-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cc612-144">[ALTER LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-login-transact-sql) </span></span>  
 <span data-ttu-id="cc612-145">[CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cc612-145">[CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql) </span></span>  
 <span data-ttu-id="cc612-146">[ALTER USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-user-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cc612-146">[ALTER USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-user-transact-sql) </span></span>  
 <span data-ttu-id="cc612-147">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cc612-147">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 <span data-ttu-id="cc612-148">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cc612-148">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="cc612-149">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cc612-149">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="cc612-150">[Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="cc612-150">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="cc612-151">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cc612-151">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
