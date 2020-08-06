---
title: Konfigurieren der Serverkonfigurationsoption „Cursorschwellenwert“ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- cursor threshold option
ms.assetid: 189f2067-c6c4-48bd-9bd9-65f6b2021c12
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 0d7fd9ecafda270a02f1fba9f5dd74adc9e299d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622889"
---
# <a name="configure-the-cursor-threshold-server-configuration-option"></a><span data-ttu-id="fd6c6-102">Konfigurieren der Serverkonfigurationsoption Cursorschwellenwert</span><span class="sxs-lookup"><span data-stu-id="fd6c6-102">Configure the cursor threshold Server Configuration Option</span></span>
  <span data-ttu-id="fd6c6-103">In diesem Thema wird beschrieben, wie die Serverkonfigurationsoption **Cursorschwellenwert** in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="fd6c6-103">This topic describes how to configure the **cursor threshold** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="fd6c6-104">Mit der Option **Cursorschwellenwert** können Sie die Anzahl der Zeilen im Cursorset angeben, bei der Cursor-Keysets asynchron generiert werden.</span><span class="sxs-lookup"><span data-stu-id="fd6c6-104">The **cursor threshold** option specifies the number of rows in the cursor set at which cursor keysets are generated asynchronously.</span></span> <span data-ttu-id="fd6c6-105">Wenn Cursor ein Keyset für ein Resultset generieren, schätzt der Abfrageoptimierer die Anzahl der Zeilen, die für dieses Resultset zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="fd6c6-105">When cursors generate a keyset for a result set, the query optimizer estimates the number of rows that will be returned for that result set.</span></span> <span data-ttu-id="fd6c6-106">Wenn der Abfrageoptimierer schätzt, dass die Anzahl der zurückgegebenen Zeilen über diesem Schwellenwert liegt, wird der Cursor asynchron generiert. Dadurch kann der Benutzer Zeilen aus dem Cursor abrufen, während der Cursor weiterhin aufgefüllt wird.</span><span class="sxs-lookup"><span data-stu-id="fd6c6-106">If the query optimizer estimates that the number of returned rows is greater than this threshold, the cursor is generated asynchronously, allowing the user to fetch rows from the cursor while the cursor continues to be populated.</span></span> <span data-ttu-id="fd6c6-107">Andernfalls wird der Cursor synchron generiert, und die Abfrage wartet, bis alle Zeilen zurückgegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="fd6c6-107">Otherwise, the cursor is generated synchronously, and the query waits until all rows are returned.</span></span>  
  
 <span data-ttu-id="fd6c6-108">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="fd6c6-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="fd6c6-109">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="fd6c6-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="fd6c6-110">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="fd6c6-110">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="fd6c6-111">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="fd6c6-111">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="fd6c6-112">Security</span><span class="sxs-lookup"><span data-stu-id="fd6c6-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="fd6c6-113">**So konfigurieren Sie die Option Cursorschwellenwert mit:**</span><span class="sxs-lookup"><span data-stu-id="fd6c6-113">**To configure the cursor threshold option, using:**</span></span>  
  
     [<span data-ttu-id="fd6c6-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fd6c6-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="fd6c6-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fd6c6-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="fd6c6-116">**Nachverfolgung:**  [Nach dem Konfigurieren der Option „Cursorschwellenwert“](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="fd6c6-116">**Follow Up:**  [After you configure the cursor threshold option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="fd6c6-117">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="fd6c6-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="fd6c6-118">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="fd6c6-118">Limitations and Restrictions</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="fd6c6-119">unterstützt das asynchrone Generieren von keysetgesteuerten oder statischen [!INCLUDE[tsql](../../includes/tsql-md.md)] -Cursorn nicht.</span><span class="sxs-lookup"><span data-stu-id="fd6c6-119">does not support generating keyset-driven or static [!INCLUDE[tsql](../../includes/tsql-md.md)] cursors asynchronously.</span></span> [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="fd6c6-120">-Cursorvorgänge, z. B. OPEN oder FETCH, sind in Batches enthalten. Daher ist das asynchrone Generieren von [!INCLUDE[tsql](../../includes/tsql-md.md)] -Cursorn nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fd6c6-120">cursor operations such as OPEN or FETCH are batched, so there is no need for the asynchronous generation of [!INCLUDE[tsql](../../includes/tsql-md.md)] cursors.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="fd6c6-121">unterstützt weiterhin asynchrone keysetgesteuerte oder statische AP -Servercursor (Application Programming Interface), wobei Cursoroperationen des Typs „Open“ mit niedriger Latenz ein Problem darstellen. Dies ist auf Clientroundtrips zurückzuführen, die für jeden Cursorvorgang ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="fd6c6-121">continues to support asynchronous keyset-driven or static application programming interface (API) server cursors where low latency OPEN is a concern, due to client round trips for each cursor operation.</span></span>  
  
-   <span data-ttu-id="fd6c6-122">Die Genauigkeit des Abfrageoptimierers beim Bestimmen der Anzahl der Zeilen in einem Keyset hängt davon ab, wie aktuell die Statistiken für die einzelnen Tabellen im Cursor sind.</span><span class="sxs-lookup"><span data-stu-id="fd6c6-122">The accuracy of the query optimizer to determine an estimate for the number of rows in a keyset depends on the currency of the statistics for each of the tables in the cursor.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="fd6c6-123">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="fd6c6-123">Recommendations</span></span>  
  
-   <span data-ttu-id="fd6c6-124">Diese Option ist eine erweiterte Option und sollte ausschließlich von einem erfahrenen Datenbankadministrator oder einem zertifizierten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Techniker geändert werden.</span><span class="sxs-lookup"><span data-stu-id="fd6c6-124">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="fd6c6-125">Wenn Sie den **Cursorschwellenwert** auf -1 festlegen, werden alle Keysets synchron generiert, was für kleine Cursorsets vorteilhaft ist.</span><span class="sxs-lookup"><span data-stu-id="fd6c6-125">If you set **cursor threshold** to -1, all keysets are generated synchronously, which benefits small cursor sets.</span></span> <span data-ttu-id="fd6c6-126">Wenn Sie **Cursorschwellenwert** auf 0 festlegen, werden alle Cursor-Keysets asynchron generiert.</span><span class="sxs-lookup"><span data-stu-id="fd6c6-126">If you set **cursor threshold** to 0, all cursor keysets are generated asynchronously.</span></span> <span data-ttu-id="fd6c6-127">Bei anderen Werten vergleicht der Abfrageoptimierer die Anzahl der erwarteten Zeilen im Cursorset und erstellt das Keyset asynchron, wenn die Anzahl der in **Cursorschwellenwert**festgelegten Zeilen überschritten wird.</span><span class="sxs-lookup"><span data-stu-id="fd6c6-127">With other values, the query optimizer compares the number of expected rows in the cursor set and builds the keyset asynchronously if it exceeds the number set in **cursor threshold**.</span></span> <span data-ttu-id="fd6c6-128">Sie sollten die Option **Cursorschwellenwert** nicht zu niedrig festlegen, da es besser ist, kleine Resultsets synchron zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fd6c6-128">Do not set **cursor threshold** too low, because small result sets are better built synchronously.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="fd6c6-129">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="fd6c6-129">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="fd6c6-130">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="fd6c6-130">Permissions</span></span>  
 <span data-ttu-id="fd6c6-131">Die Ausführungsberechtigungen für **sp_configure** ohne Parameter oder nur mit dem ersten Parameter werden standardmäßig allen Benutzern erteilt.</span><span class="sxs-lookup"><span data-stu-id="fd6c6-131">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="fd6c6-132">Zum Ausführen von **sp_configure** mit beiden Parametern zum Ändern einer Konfigurationsoption oder zum Ausführen der RECONFIGURE-Anweisung muss einem Benutzer die ALTER SETTINGS-Berechtigung auf Serverebene erteilt worden sein.</span><span class="sxs-lookup"><span data-stu-id="fd6c6-132">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="fd6c6-133">Die ALTER SETTINGS-Berechtigung ist in den festen Serverrollen **sysadmin** und **serveradmin** eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="fd6c6-133">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="fd6c6-134">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fd6c6-134">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-cursor-threshold-option"></a><span data-ttu-id="fd6c6-135">So konfigurieren Sie die Option "Cursorschwellenwert"</span><span class="sxs-lookup"><span data-stu-id="fd6c6-135">To configure the cursor threshold option</span></span>  
  
1.  <span data-ttu-id="fd6c6-136">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf einen Server, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="fd6c6-136">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="fd6c6-137">Klicken Sie auf den **Erweitert** -Knoten.</span><span class="sxs-lookup"><span data-stu-id="fd6c6-137">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="fd6c6-138">Geben Sie unter **Verschiedenes**für die Option **Cursorschwellenwert** den gewünschten Wert an.</span><span class="sxs-lookup"><span data-stu-id="fd6c6-138">Under **Miscellaneous**, change the **Cursor Threshold** option to the value you want.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="fd6c6-139">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fd6c6-139">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-cursor-threshold-option"></a><span data-ttu-id="fd6c6-140">So konfigurieren Sie die Option "Cursorschwellenwert"</span><span class="sxs-lookup"><span data-stu-id="fd6c6-140">To configure the cursor threshold option</span></span>  
  
1.  <span data-ttu-id="fd6c6-141">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="fd6c6-141">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="fd6c6-142">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="fd6c6-142">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="fd6c6-143">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="fd6c6-143">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="fd6c6-144">In diesem Beispiel wird gezeigt, wie Sie [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) zum Festlegen der Option `cursor threshold` auf `0` verwenden, damit Cursor-Keysets asynchron generiert werden.</span><span class="sxs-lookup"><span data-stu-id="fd6c6-144">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the `cursor threshold` option to `0` so that cursor keysets are generated asynchronously.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1 ;  
GO  
RECONFIGURE  
GO  
EXEC sp_configure 'cursor threshold', 0 ;  
GO  
RECONFIGURE  
GO  
  
```  
  
 <span data-ttu-id="fd6c6-145">Weitere Informationen finden Sie unter [Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md)angezeigt oder konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="fd6c6-145">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-cursor-threshold-option"></a><a name="FollowUp"></a><span data-ttu-id="fd6c6-146">Nächster Schritt: Nach dem Konfigurieren der Option „Cursorschwellenwert“</span><span class="sxs-lookup"><span data-stu-id="fd6c6-146">Follow Up: After you configure the cursor threshold option</span></span>  
 <span data-ttu-id="fd6c6-147">Die Einstellung tritt ohne Neustarten des Servers sofort in Kraft.</span><span class="sxs-lookup"><span data-stu-id="fd6c6-147">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd6c6-148">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fd6c6-148">See Also</span></span>  
 <span data-ttu-id="fd6c6-149">[@@CURSOR_ROWS &#40;Transact-SQL&#41;](/sql/t-sql/functions/cursor-rows-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fd6c6-149">[@@CURSOR_ROWS &#40;Transact-SQL&#41;](/sql/t-sql/functions/cursor-rows-transact-sql) </span></span>  
 <span data-ttu-id="fd6c6-150">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fd6c6-150">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="fd6c6-151">[Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="fd6c6-151">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="fd6c6-152">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fd6c6-152">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="fd6c6-153">UPDATE STATISTICS &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="fd6c6-153">UPDATE STATISTICS &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/update-statistics-transact-sql)  
  
  
