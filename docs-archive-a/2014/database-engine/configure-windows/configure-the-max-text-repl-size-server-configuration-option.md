---
title: Konfigurieren der Serverkonfigurationsoption „max text repl size“ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- max text repl size option
ms.assetid: 3056cf64-621d-4996-9162-3913f6bc6d5b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2af0cf426583ee328f0a484de1c3539836c0d8af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619342"
---
# <a name="configure-the-max-text-repl-size-server-configuration-option"></a><span data-ttu-id="a81ae-102">Konfigurieren der Serverkonfigurationsoption max text repl size</span><span class="sxs-lookup"><span data-stu-id="a81ae-102">Configure the max text repl size Server Configuration Option</span></span>
  <span data-ttu-id="a81ae-103">In diesem Thema wird beschrieben, wie die Serverkonfigurationsoption **Max. Textgröße für Replikation** in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="a81ae-103">This topic describes how to configure the **max text repl size** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="a81ae-104">Die Option **max text repl size** gibt die maximale Größe (in Bytes) von Daten vom Typ, `text` `ntext` , `varchar(max)` , `nvarchar(max)` ,, und an, die `varbinary(max)` `xml` `image` einer replizierten oder aufgezeichneten Spalte in einer einzelnen INSERT-, Update-, WRITETEXT-oder Update Text-Anweisung hinzugefügt werden können.</span><span class="sxs-lookup"><span data-stu-id="a81ae-104">The **max text repl size** option specifies the maximum size (in bytes) of `text`, `ntext`, `varchar(max)`, `nvarchar(max)`, `varbinary(max)`, `xml`, and `image` data that can be added to a replicated column or captured column in a single INSERT, UPDATE, WRITETEXT, or UPDATETEXT statement.</span></span> <span data-ttu-id="a81ae-105">Der Standardwert ist 65536 Byte.</span><span class="sxs-lookup"><span data-stu-id="a81ae-105">The default value is 65536 bytes.</span></span> <span data-ttu-id="a81ae-106">Der Wert -1 gibt an, dass mit Ausnahme der durch den Datentyp auferlegten Größenbegrenzung keine Begrenzung der Größe gilt.</span><span class="sxs-lookup"><span data-stu-id="a81ae-106">A value of -1 indicates that there is no size limit, other than the limit imposed by the data type.</span></span>  
  
 <span data-ttu-id="a81ae-107">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="a81ae-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a81ae-108">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="a81ae-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a81ae-109">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="a81ae-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="a81ae-110">Security</span><span class="sxs-lookup"><span data-stu-id="a81ae-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a81ae-111">**So konfigurieren Sie die Option Max. Textgröße für Replikation mit:**</span><span class="sxs-lookup"><span data-stu-id="a81ae-111">**To configure the max text repl size option, using:**</span></span>  
  
     [<span data-ttu-id="a81ae-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a81ae-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="a81ae-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a81ae-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="a81ae-114">**Nachverfolgung:**  [Nach dem Konfigurieren der Option Max. Textgröße für Replikation](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="a81ae-114">**Follow Up:**  [After you configure the max text repl size option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a81ae-115">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="a81ae-115">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="a81ae-116">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="a81ae-116">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="a81ae-117">Diese Option gilt für die Transaktionsreplikation und Change Data Capture.</span><span class="sxs-lookup"><span data-stu-id="a81ae-117">This option applies to transactional replication and Change Data Capture.</span></span> <span data-ttu-id="a81ae-118">Wenn ein Server sowohl für die Transaktionsreplikation als auch für Change Data Capture konfiguriert ist, gilt der angegebene Wert für beide Funktionen.</span><span class="sxs-lookup"><span data-stu-id="a81ae-118">When a server is configured for both transactional replication and Change Data Capture, the specified value applies to both features.</span></span> <span data-ttu-id="a81ae-119">Diese Option gilt nicht für die Momentaufnahmereplikation und die Mergereplikation.</span><span class="sxs-lookup"><span data-stu-id="a81ae-119">This option is ignored by snapshot replication and merge replication.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a81ae-120">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="a81ae-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a81ae-121">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="a81ae-121">Permissions</span></span>  
 <span data-ttu-id="a81ae-122">Die Ausführungsberechtigungen für **sp_configure** ohne Parameter oder nur mit dem ersten Parameter werden standardmäßig allen Benutzern erteilt.</span><span class="sxs-lookup"><span data-stu-id="a81ae-122">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="a81ae-123">Zum Ausführen von **sp_configure** mit beiden Parametern zum Ändern einer Konfigurationsoption oder zum Ausführen der RECONFIGURE-Anweisung muss einem Benutzer die ALTER SETTINGS-Berechtigung auf Serverebene erteilt worden sein.</span><span class="sxs-lookup"><span data-stu-id="a81ae-123">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="a81ae-124">Die ALTER SETTINGS-Berechtigung ist in den festen Serverrollen **sysadmin** und **serveradmin** eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="a81ae-124">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a81ae-125">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a81ae-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-max-text-repl-size-option"></a><span data-ttu-id="a81ae-126">So konfigurieren Sie die Option Max. Textgröße für Replikation</span><span class="sxs-lookup"><span data-stu-id="a81ae-126">To configure the max text repl size option</span></span>  
  
1.  <span data-ttu-id="a81ae-127">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf einen Server, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="a81ae-127">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="a81ae-128">Klicken Sie auf den **Erweitert** -Knoten.</span><span class="sxs-lookup"><span data-stu-id="a81ae-128">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="a81ae-129">Geben Sie unter **Verschiedenes**für die Option **Max. Textgröße für Replikation** den gewünschten Wert an.</span><span class="sxs-lookup"><span data-stu-id="a81ae-129">Under **Miscellaneous**, change the **Max Text Replication Size** option to the desired value.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a81ae-130">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a81ae-130">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-max-text-repl-size-option"></a><span data-ttu-id="a81ae-131">So konfigurieren Sie die Option Max. Textgröße für Replikation</span><span class="sxs-lookup"><span data-stu-id="a81ae-131">To configure the max text repl size option</span></span>  
  
1.  <span data-ttu-id="a81ae-132">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="a81ae-132">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="a81ae-133">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="a81ae-133">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="a81ae-134">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="a81ae-134">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="a81ae-135">In diesem Beispiel wird gezeigt, wie [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) verwendet wird, um die Option `max text repl size` auf `-1`festzulegen.</span><span class="sxs-lookup"><span data-stu-id="a81ae-135">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to configure the `max text repl size` option to `-1`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1 ;   
RECONFIGURE ;   
GO  
EXEC sp_configure 'max text repl size', -1 ;   
GO  
RECONFIGURE;   
GO  
  
```  
  
 <span data-ttu-id="a81ae-136">Weitere Informationen finden Sie unter [Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md)angezeigt oder konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="a81ae-136">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-max-text-repl-size-option"></a><a name="FollowUp"></a><span data-ttu-id="a81ae-137">Nächster Schritt: Nach dem Konfigurieren der Option Max. Textgröße für Replikation</span><span class="sxs-lookup"><span data-stu-id="a81ae-137">Follow Up: After you configure the max text repl size option</span></span>  
 <span data-ttu-id="a81ae-138">Die Einstellung tritt ohne Neustarten des Servers sofort in Kraft.</span><span class="sxs-lookup"><span data-stu-id="a81ae-138">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a81ae-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a81ae-139">See Also</span></span>  
 <span data-ttu-id="a81ae-140">[SQL Server-Replikation](../../relational-databases/replication/sql-server-replication.md) </span><span class="sxs-lookup"><span data-stu-id="a81ae-140">[SQL Server Replication](../../relational-databases/replication/sql-server-replication.md) </span></span>  
 <span data-ttu-id="a81ae-141">[INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a81ae-141">[INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql) </span></span>  
 <span data-ttu-id="a81ae-142">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a81ae-142">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="a81ae-143">[Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a81ae-143">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="a81ae-144">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a81ae-144">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 <span data-ttu-id="a81ae-145">[UPDATE (Transact-SQL)](/sql/t-sql/queries/update-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a81ae-145">[UPDATE &#40;Transact-SQL&#41;](/sql/t-sql/queries/update-transact-sql) </span></span>  
 <span data-ttu-id="a81ae-146">[UPDATETEXT (Transact-SQL)](/sql/t-sql/queries/updatetext-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a81ae-146">[UPDATETEXT &#40;Transact-SQL&#41;](/sql/t-sql/queries/updatetext-transact-sql) </span></span>  
 [<span data-ttu-id="a81ae-147">WRITETEXT (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="a81ae-147">WRITETEXT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/writetext-transact-sql)  
  
  
