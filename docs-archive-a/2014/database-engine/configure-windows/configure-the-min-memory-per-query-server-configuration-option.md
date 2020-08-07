---
title: Konfigurieren des min. Arbeitsspeichers pro Abfrage (Serverkonfigurationsoption) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- memory [SQL Server], queries
- minimum query memory
- queries [SQL Server], memory
- min memory per query option
ms.assetid: ecd3fb79-b4a6-432f-9ef5-530e0d42d5a6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 56d85f36840f0900c8b5e986334a99ba610d3930
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619337"
---
# <a name="configure-the-min-memory-per-query-server-configuration-option"></a><span data-ttu-id="b7a24-102">Konfigurieren der Serverkonfigurationsoption Min. Arbeitsspeicher pro Abfrage</span><span class="sxs-lookup"><span data-stu-id="b7a24-102">Configure the min memory per query Server Configuration Option</span></span>
  <span data-ttu-id="b7a24-103">In diesem Thema wird beschrieben, wie die `min memory per query` Server Konfigurationsoption in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von oder konfiguriert wird [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b7a24-103">This topic describes how to configure the `min memory per query` server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="b7a24-104">Die `min memory per query` Option gibt die minimale Arbeitsspeicher Menge (in Kilobytes) an, die für die Ausführung einer Abfrage zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="b7a24-104">The `min memory per query` option specifies the minimum amount of memory (in kilobytes) that will be allocated for the execution of a query.</span></span> <span data-ttu-id="b7a24-105">Wenn z. b. `min memory per query` auf 2.048 KB festgelegt ist, wird sichergestellt, dass die Abfrage mindestens den gesamten Arbeitsspeicher erhält.</span><span class="sxs-lookup"><span data-stu-id="b7a24-105">For example, if `min memory per query` is set to 2,048 KB, the query is guaranteed to get at least that much total memory.</span></span> <span data-ttu-id="b7a24-106">Der Standardwert ist 1.024 KB.</span><span class="sxs-lookup"><span data-stu-id="b7a24-106">The default value is 1,024 KB.</span></span> <span data-ttu-id="b7a24-107">512 KB ist der Minimalwert, und 2.147.483.647 KB (2 GB) ist der Maximalwert.</span><span class="sxs-lookup"><span data-stu-id="b7a24-107">The minimum value 512 KB, and the maximum is 2,147,483,647 KB (2 GB).</span></span>  
  
 <span data-ttu-id="b7a24-108">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="b7a24-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b7a24-109">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="b7a24-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b7a24-110">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="b7a24-110">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="b7a24-111">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="b7a24-111">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="b7a24-112">Security</span><span class="sxs-lookup"><span data-stu-id="b7a24-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b7a24-113">**So konfigurieren Sie die Option Min. Arbeitsspeicher pro Abfrage mit:**</span><span class="sxs-lookup"><span data-stu-id="b7a24-113">**To configure the min memory per query option, using:**</span></span>  
  
     [<span data-ttu-id="b7a24-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b7a24-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b7a24-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b7a24-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="b7a24-116">**Nachverfolgung:**  [Nach dem Konfigurieren der Option „Min. Arbeitsspeicher pro Abfrage“](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="b7a24-116">**Follow Up:**  [After you configure the min memory per query option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b7a24-117">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="b7a24-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="b7a24-118">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="b7a24-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="b7a24-119">Der minimale Arbeitsspeicher pro Abfrage hat Vorrang vor der [Option Speicher für Indexerstellung](configure-the-index-create-memory-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="b7a24-119">The amount of min memory per query has precedence over the [index create memory Option](configure-the-index-create-memory-server-configuration-option.md).</span></span> <span data-ttu-id="b7a24-120">Wenn Sie beide Optionen ändern und der Wert von „index create memory“ (Speicher für Indexerstellung) den Wert von „min memory per query“ (Min. Arbeitsspeicher pro Abfrage) unterschreitet, werden die Werte zwar festgelegt, es wird jedoch eine Warnmeldung ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="b7a24-120">If you modify both options and the index create memory is less than min memory per query, you receive a warning message, but the value is set.</span></span> <span data-ttu-id="b7a24-121">Beim Ausführen der Abfrage wird eine ähnliche Warnung ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="b7a24-121">During query execution you receive another similar warning.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="b7a24-122">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="b7a24-122">Recommendations</span></span>  
  
-   <span data-ttu-id="b7a24-123">Diese Option ist eine erweiterte Option und sollte ausschließlich von einem erfahrenen Datenbankadministrator oder einem zertifizierten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Techniker geändert werden.</span><span class="sxs-lookup"><span data-stu-id="b7a24-123">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="b7a24-124">Der Abfrageprozessor von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] versucht, den optimalen Umfang an Speicher zu bestimmen, der von einer Abfrage belegt werden soll.</span><span class="sxs-lookup"><span data-stu-id="b7a24-124">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] query processor tries to determine the optimal amount of memory to allocate to a query.</span></span> <span data-ttu-id="b7a24-125">Mit der Option Min. Arbeitsspeicher pro Abfrage kann der Administrator den Umfang an Speicher angeben, der für eine einzelne Abfrage mindestens zur Verfügung gestellt wird.</span><span class="sxs-lookup"><span data-stu-id="b7a24-125">The min memory per query option lets the administrator specify the minimum amount of memory any single query receives.</span></span> <span data-ttu-id="b7a24-126">Abfragen erhalten im Allgemeinen mehr Speicher als hier angegeben, wenn Hash- und Sortiervorgänge für umfangreiche Datenmengen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b7a24-126">Queries generally receive more memory than this if they have hash and sort operations on a large volume of data.</span></span> <span data-ttu-id="b7a24-127">Durch die Erhöhung des Werts für Min. Arbeitsspeicher pro Abfrage kann es bei einigen Abfragen mit geringem bis mittlerem Umfang zur Leistungssteigerung, jedoch auch zu stärkerem Wettbewerb um Speicherressourcen kommen.</span><span class="sxs-lookup"><span data-stu-id="b7a24-127">Increasing the value of min memory per query may improve performance for some small to medium-sized queries, but doing so could lead to increased competition for memory resources.</span></span> <span data-ttu-id="b7a24-128">Die Option „Min. Arbeitsspeicher pro Abfrage“ schließt den für die Sortierung zugeordneten Arbeitsspeicher ein.</span><span class="sxs-lookup"><span data-stu-id="b7a24-128">The min memory per query option includes memory allocated for sorting.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b7a24-129">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="b7a24-129">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b7a24-130">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="b7a24-130">Permissions</span></span>  
 <span data-ttu-id="b7a24-131">Die Ausführungsberechtigungen für **sp_configure** ohne Parameter oder nur mit dem ersten Parameter werden standardmäßig allen Benutzern erteilt.</span><span class="sxs-lookup"><span data-stu-id="b7a24-131">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="b7a24-132">Zum Ausführen von **sp_configure** mit beiden Parametern zum Ändern einer Konfigurationsoption oder zum Ausführen der RECONFIGURE-Anweisung muss einem Benutzer die ALTER SETTINGS-Berechtigung auf Serverebene erteilt worden sein.</span><span class="sxs-lookup"><span data-stu-id="b7a24-132">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="b7a24-133">Die ALTER SETTINGS-Berechtigung ist in den festen Serverrollen **sysadmin** und **serveradmin** eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="b7a24-133">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b7a24-134">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b7a24-134">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-min-memory-per-query-option"></a><span data-ttu-id="b7a24-135">So konfigurieren Sie die Option Min. Arbeitsspeicher pro Abfrage</span><span class="sxs-lookup"><span data-stu-id="b7a24-135">To configure the min memory per query option</span></span>  
  
1.  <span data-ttu-id="b7a24-136">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf einen Server, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="b7a24-136">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="b7a24-137">Klicken Sie auf den **Speicher** -Knoten.</span><span class="sxs-lookup"><span data-stu-id="b7a24-137">Click the **Memory** node.</span></span>  
  
3.  <span data-ttu-id="b7a24-138">Geben Sie in das Feld **Minimaler Arbeitsspeicher pro Abfrage** die Mindestmenge an Arbeitsspeicher (in KB) ein, die für das Ausführen einer Abfrage zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="b7a24-138">In the **Minimum memory per query** box, enter the minimum amount of memory (in kilobytes) that will be allocated for the execution of a query.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b7a24-139">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b7a24-139">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-min-memory-per-query-option"></a><span data-ttu-id="b7a24-140">So konfigurieren Sie die Option Min. Arbeitsspeicher pro Abfrage</span><span class="sxs-lookup"><span data-stu-id="b7a24-140">To configure the min memory per query option</span></span>  
  
1.  <span data-ttu-id="b7a24-141">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="b7a24-141">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b7a24-142">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="b7a24-142">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b7a24-143">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="b7a24-143">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="b7a24-144">In diesem Beispiel wird gezeigt, wie [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) verwendet wird, um den Wert der Option `min memory per query` auf `3500` KB festzulegen.</span><span class="sxs-lookup"><span data-stu-id="b7a24-144">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `min memory per query` option to `3500` KB.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'min memory per query', 3500 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
##  <a name="follow-up-after-you-configure-the-min-memory-per-query-option"></a><a name="FollowUp"></a><span data-ttu-id="b7a24-145">Nächster Schritt: Nach dem Konfigurieren der Option „Min. Arbeitsspeicher pro Abfrage“</span><span class="sxs-lookup"><span data-stu-id="b7a24-145">Follow Up: After you configure the min memory per query option</span></span>  
 <span data-ttu-id="b7a24-146">Die Einstellung tritt ohne Neustarten des Servers sofort in Kraft.</span><span class="sxs-lookup"><span data-stu-id="b7a24-146">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7a24-147">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b7a24-147">See Also</span></span>  
 <span data-ttu-id="b7a24-148">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b7a24-148">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="b7a24-149">[Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b7a24-149">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="b7a24-150">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b7a24-150">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="b7a24-151">Konfigurieren der Serverkonfigurationsoption Speicher für Indexerstellung</span><span class="sxs-lookup"><span data-stu-id="b7a24-151">Configure the index create memory Server Configuration Option</span></span>](configure-the-index-create-memory-server-configuration-option.md)  
  
  
