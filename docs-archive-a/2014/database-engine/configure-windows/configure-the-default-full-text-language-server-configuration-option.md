---
title: Konfigurieren der Serverkonfigurationsoption „Volltext-Standardsprache“ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- languages [full-text search]
- default full-text language option
ms.assetid: 0fa8785b-0830-4a52-aff5-fcf8268b72fc
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ec0736326a4da0708d125bfc480996d54bb86c8a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608847"
---
# <a name="configure-the-default-full-text-language-server-configuration-option"></a><span data-ttu-id="aab69-102">Konfigurieren der Serverkonfigurationsoption Volltext-Standardsprache</span><span class="sxs-lookup"><span data-stu-id="aab69-102">Configure the default full-text language Server Configuration Option</span></span>
  <span data-ttu-id="aab69-103">In diesem Thema wird beschrieben, wie die `default full-text language` Server Konfigurationsoption in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von oder konfiguriert wird [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="aab69-103">This topic describes how to configure the `default full-text language` server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="aab69-104">Mit der- `default full-text language` Option wird ein Standard sprach Wert für Volltextindizes angegeben.</span><span class="sxs-lookup"><span data-stu-id="aab69-104">The `default full-text language` option specifies a default language value for full-text indexes.</span></span> <span data-ttu-id="aab69-105">Für alle Daten, die Volltextindizes aufweisen, wird eine linguistische Analyse ausgeführt, die von der Sprache der Daten abhängt.</span><span class="sxs-lookup"><span data-stu-id="aab69-105">Linguistic analysis is performed on all data that is full-text indexed and is dependent on the language of the data.</span></span> <span data-ttu-id="aab69-106">Der Standardwert für diese Option ist die Sprache des Servers.</span><span class="sxs-lookup"><span data-stu-id="aab69-106">The default value of this option is the language of the server.</span></span> <span data-ttu-id="aab69-107">Bei einer lokalisierten Version von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] wird [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] die `default full-text language` Option von Setup auf die Sprache des Servers festgelegt, wenn eine entsprechende Entsprechung vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="aab69-107">For a localized version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup sets the `default full-text language` option to the language of the server if an appropriate match exists.</span></span> <span data-ttu-id="aab69-108">Bei einer nicht lokalisierten Version [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] wird Englisch für die Option `default full-text language` verwendet.</span><span class="sxs-lookup"><span data-stu-id="aab69-108">For a non-localized version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the `default full-text language` option is English.</span></span>  
  
 <span data-ttu-id="aab69-109">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="aab69-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="aab69-110">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="aab69-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="aab69-111">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="aab69-111">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="aab69-112">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="aab69-112">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="aab69-113">Security</span><span class="sxs-lookup"><span data-stu-id="aab69-113">Security</span></span>](#Security)  
  
-   <span data-ttu-id="aab69-114">**So konfigurieren Sie die Option Volltext-Standardsprache mit:**</span><span class="sxs-lookup"><span data-stu-id="aab69-114">**To configure the default full-text language option, using:**</span></span>  
  
     [<span data-ttu-id="aab69-115">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="aab69-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="aab69-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="aab69-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="aab69-117">**Nachverfolgung:**  [Nach dem Konfigurieren der Option „Volltext-Standardsprache“](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="aab69-117">**Follow Up:**  [After you configure the default full-text language option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="aab69-118">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="aab69-118">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="aab69-119">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="aab69-119">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="aab69-120">Der Wert der `default full-text language` Option wird in einem Volltextindex verwendet, wenn für eine Spalte keine Sprache über die Option language **language_term** in der CREATE FULLTEXT INDEX-Anweisung oder der ALTER FULLTEXT INDEX-Anweisung angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="aab69-120">The value of the `default full-text language` option is used in a full-text index when no language is specified for a column through the LANGUAGE **language_term** option in the CREATE FULLTEXT INDEX or ALTER FULLTEXT INDEX statements.</span></span> <span data-ttu-id="aab69-121">Wenn die Volltext-Standardsprache nicht unterstützt wird oder das Sprachanalysepaket nicht verfügbar ist, schlägt die CREATE- oder ALTER-Operation fehl, und [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] gibt eine Fehlermeldung zurück, die besagt, dass die angegebene Sprache ungültig ist.</span><span class="sxs-lookup"><span data-stu-id="aab69-121">If the default full-text language is not supported or the linguistic analysis package is not available, the CREATE or ALTER operation will fail and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will return an error message stating that the language specified is not valid.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="aab69-122">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="aab69-122">Recommendations</span></span>  
  
-   <span data-ttu-id="aab69-123">Diese Option ist eine erweiterte Option und sollte ausschließlich von einem erfahrenen Datenbankadministrator oder einem zertifizierten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Techniker geändert werden.</span><span class="sxs-lookup"><span data-stu-id="aab69-123">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="aab69-124">Die `default full-text language` Option erfordert einen LCID-Wert.</span><span class="sxs-lookup"><span data-stu-id="aab69-124">The `default full-text language` option requires an LCID value.</span></span> <span data-ttu-id="aab69-125">Eine Liste mit unterstützten LCIDs und den dazugehörigen Sprachen finden Sie unter [sys.fulltext_languages &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-languages-transact-sql)konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="aab69-125">For a list of supported LCIDs and their related languages, see [sys.fulltext_languages &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-languages-transact-sql).</span></span> <span data-ttu-id="aab69-126">Andere Sprachen können beispielsweise von unabhängigen Softwareherstellern verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="aab69-126">Other languages may also be available from independent software vendors, for example.</span></span> <span data-ttu-id="aab69-127">Wenn keine spezielle Sprache gefunden wird, schaltet die Volltextsuch-Engine automatisch in die primäre Sprache.</span><span class="sxs-lookup"><span data-stu-id="aab69-127">If no specific language dialect is found, the Full-Text Engine will automatically switch to the primary language.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="aab69-128">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="aab69-128">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="aab69-129">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="aab69-129">Permissions</span></span>  
 <span data-ttu-id="aab69-130">Die Ausführungsberechtigungen für **sp_configure** ohne Parameter oder nur mit dem ersten Parameter werden standardmäßig allen Benutzern erteilt.</span><span class="sxs-lookup"><span data-stu-id="aab69-130">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="aab69-131">Zum Ausführen von **sp_configure** mit beiden Parametern zum Ändern einer Konfigurationsoption oder zum Ausführen der RECONFIGURE-Anweisung muss einem Benutzer die ALTER SETTINGS-Berechtigung auf Serverebene erteilt worden sein.</span><span class="sxs-lookup"><span data-stu-id="aab69-131">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="aab69-132">Die ALTER SETTINGS-Berechtigung ist in den festen Serverrollen **sysadmin** und **serveradmin** eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="aab69-132">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="aab69-133">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="aab69-133">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-default-full-text-language-option"></a><span data-ttu-id="aab69-134">So konfigurieren Sie die Option Volltext-Standardsprache</span><span class="sxs-lookup"><span data-stu-id="aab69-134">To configure the default full-text language option</span></span>  
  
1.  <span data-ttu-id="aab69-135">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf einen Server, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="aab69-135">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="aab69-136">Klicken Sie auf den **Erweitert** -Knoten.</span><span class="sxs-lookup"><span data-stu-id="aab69-136">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="aab69-137">Verwenden Sie unter Verschiedenes die Option **Volltext-Standardsprache** , um einen Wert für die Standardsprache für volltextindizierte Spalten anzugeben.</span><span class="sxs-lookup"><span data-stu-id="aab69-137">Under Miscellaneous, use **Default Full Text Language** to specify a default language value for full-text indexed columns.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="aab69-138">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="aab69-138">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-default-full-text-language-option"></a><span data-ttu-id="aab69-139">So konfigurieren Sie die Option Volltext-Standardsprache</span><span class="sxs-lookup"><span data-stu-id="aab69-139">To configure the default full-text language option</span></span>  
  
1.  <span data-ttu-id="aab69-140">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="aab69-140">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="aab69-141">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="aab69-141">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="aab69-142">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="aab69-142">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="aab69-143">In diesem Beispiel wird gezeigt, wie [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) verwendet wird, um den Wert der Option `default full-text` auf Holländisch (`1043`) festzulegen.</span><span class="sxs-lookup"><span data-stu-id="aab69-143">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `default full-text` option to Dutch (`1043`).</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1 ;  
GO  
RECONFIGURE  
GO  
EXEC sp_configure 'default full-text language', 1043 ;  
GO  
RECONFIGURE  
GO  
  
```  
  
 <span data-ttu-id="aab69-144">Weitere Informationen finden Sie unter [Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md)angezeigt oder konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="aab69-144">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-default-full-text-language-option"></a><a name="FollowUp"></a><span data-ttu-id="aab69-145">Nächster Schritt: Nach dem Konfigurieren der Option „Volltext-Standardsprache“</span><span class="sxs-lookup"><span data-stu-id="aab69-145">Follow Up: After you configure the default full-text language option</span></span>  
 <span data-ttu-id="aab69-146">Die Einstellung tritt ohne Neustarten des Servers sofort in Kraft.</span><span class="sxs-lookup"><span data-stu-id="aab69-146">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aab69-147">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="aab69-147">See Also</span></span>  
 <span data-ttu-id="aab69-148">[sys.fulltext_languages &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-languages-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="aab69-148">[sys.fulltext_languages &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-languages-transact-sql) </span></span>  
 <span data-ttu-id="aab69-149">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="aab69-149">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="aab69-150">[Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="aab69-150">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="aab69-151">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="aab69-151">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 <span data-ttu-id="aab69-152">[CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="aab69-152">[CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-index-transact-sql) </span></span>  
 [<span data-ttu-id="aab69-153">ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="aab69-153">ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-fulltext-index-transact-sql)  
  
  
