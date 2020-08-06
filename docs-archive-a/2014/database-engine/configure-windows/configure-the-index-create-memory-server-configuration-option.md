---
title: Konfigurieren der Serverkonfigurationsoption Speicher für Indexerstellung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- index create memory option
ms.assetid: 3d722d9b-bada-4bf5-a9d7-bfc556bb4915
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6cd0aeb93d3fb68089338335068fdaaae19919fa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700215"
---
# <a name="configure-the-index-create-memory-server-configuration-option"></a><span data-ttu-id="e00e4-102">Konfigurieren der Serverkonfigurationsoption Speicher für Indexerstellung</span><span class="sxs-lookup"><span data-stu-id="e00e4-102">Configure the index create memory Server Configuration Option</span></span>
  <span data-ttu-id="e00e4-103">In diesem Thema wird beschrieben, wie die Serverkonfigurationsoption **Speicher für Indexerstellung** in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="e00e4-103">This topic describes how to configure the **index create memory** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="e00e4-104">Mit der Option **Speicher für Indexerstellung** wird der maximale Umfang des für die Erstellung von Indizes zugeordneten Arbeitsspeichers gesteuert.</span><span class="sxs-lookup"><span data-stu-id="e00e4-104">The **index create memory** option controls the maximum amount of memory initially allocated for creating indexes.</span></span> <span data-ttu-id="e00e4-105">Der Standardwert für diese Option beträgt 0 (Selbstkonfiguration).</span><span class="sxs-lookup"><span data-stu-id="e00e4-105">The default value for this option is 0 (self-configuring).</span></span> <span data-ttu-id="e00e4-106">Wenn später für die Indexerstellung mehr Speicherplatz benötigt wird und noch Speicherplatz verfügbar ist, wird dieser vom Server verwendet, und der für die Option festgelegte Wert wird überschritten.</span><span class="sxs-lookup"><span data-stu-id="e00e4-106">If more memory is later needed for index creation and the memory is available, the server will use it; thereby, exceeding the setting of this option.</span></span> <span data-ttu-id="e00e4-107">Wenn kein Speicherplatz mehr verfügbar ist, wird die Indexerstellung so lange fortgesetzt, wie der bereits zugeordnete Speicherplatz gestattet.</span><span class="sxs-lookup"><span data-stu-id="e00e4-107">If additional memory is not available, the index creation will continue using the memory already allocated.</span></span>  
  
 <span data-ttu-id="e00e4-108">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="e00e4-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="e00e4-109">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="e00e4-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e00e4-110">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="e00e4-110">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="e00e4-111">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="e00e4-111">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="e00e4-112">Security</span><span class="sxs-lookup"><span data-stu-id="e00e4-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e00e4-113">**So konfigurieren Sie die Option Speicher für Indexerstellung mit:**</span><span class="sxs-lookup"><span data-stu-id="e00e4-113">**To configure the index create memory option, using:**</span></span>  
  
     [<span data-ttu-id="e00e4-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e00e4-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="e00e4-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e00e4-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="e00e4-116">**Nachverfolgung:**  [Nach dem Konfigurieren der Option „Speicher für Indexerstellung“](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="e00e4-116">**Follow Up:**  [After you configure the index create memory option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e00e4-117">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="e00e4-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="e00e4-118">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="e00e4-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="e00e4-119">Die Einstellung der Option **Min. Arbeitsspeicher pro Abfrage** hat Vorrang vor der Option **Speicher für Indexerstellung**.</span><span class="sxs-lookup"><span data-stu-id="e00e4-119">The setting of the **min memory per query** option has precedence over the **index create memory** option.</span></span> <span data-ttu-id="e00e4-120">Wenn Sie beide Optionen ändern und der Wert von **index create memory** (Speicher für Indexerstellung) den Wert von **min memory per query**(Min. Arbeitsspeicher pro Abfrage) unterschreitet, werden die Werte zwar festgelegt, es wird jedoch eine Warnmeldung ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="e00e4-120">If you change both options and the **index create memory** is less than **min memory per query**, you receive a warning message, but the value is set.</span></span> <span data-ttu-id="e00e4-121">Eine ähnliche Warnmeldung erhalten Sie auch während der Ausführung.</span><span class="sxs-lookup"><span data-stu-id="e00e4-121">During query execution, you receive a similar warning.</span></span>  
  
-   <span data-ttu-id="e00e4-122">Bei der Verwendung von partitionierten Tabellen und Indizes können sich die Mindestanforderungen für den zur Indexerstellung benötigten Speicherplatz bei nicht ausgerichteten partitionierten Indizes und einem hohen Parallelitätsgrad erheblich erhöhen.</span><span class="sxs-lookup"><span data-stu-id="e00e4-122">When using partitioned tables and indexes, the minimum memory requirements for index creation may increase significantly if there are non-aligned partitioned indexes and a high degree of parallelism.</span></span> <span data-ttu-id="e00e4-123">Mit dieser Option wird gesteuert, wie viel Arbeitsspeicher den Indexpartitionen eines einzelnen Indexerstellungsvorgangs insgesamt zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="e00e4-123">This option controls the total initial amount of memory allocated for all index partitions in a single index creation operation.</span></span> <span data-ttu-id="e00e4-124">Wenn der durch die Option festgelegte Wert das zur Ausführung der Abfrage erforderliche Minimum unterschreitet, wird die Abfrage mit einem Fehler beendet.</span><span class="sxs-lookup"><span data-stu-id="e00e4-124">The query will terminate with an error message if the amount set by this option is less than the minimum required to run the query.</span></span>  
  
-   <span data-ttu-id="e00e4-125">Die tatsächliche Speicherkapazität, die für das Betriebssystem und die Hardwareplattform, auf der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ausgeführt wird, verwendet werden kann, wird durch den Ausführungswert dieser Option nicht überschritten.</span><span class="sxs-lookup"><span data-stu-id="e00e4-125">The run value for this option will not exceed the actual amount of memory that can be used for the operating system and hardware platform on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running.</span></span> <span data-ttu-id="e00e4-126">Bei 32-Bit-Betriebssystemen beträgt der Ausführungswert weniger als 3 Gigabytes (GB).</span><span class="sxs-lookup"><span data-stu-id="e00e4-126">On 32-bit operating systems, the run value will be less than 3 gigabytes (GB).</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="e00e4-127">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="e00e4-127">Recommendations</span></span>  
  
-   <span data-ttu-id="e00e4-128">Diese Option ist eine erweiterte Option und sollte ausschließlich von einem erfahrenen Datenbankadministrator oder einem zertifizierten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Techniker geändert werden.</span><span class="sxs-lookup"><span data-stu-id="e00e4-128">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="e00e4-129">Die Option **Speicher für Indexerstellung** ist eine selbstkonfigurierende Option, die im Normalfall nicht angepasst werden muss.</span><span class="sxs-lookup"><span data-stu-id="e00e4-129">The **index create memory** option is self-configuring and usually works without requiring adjustment.</span></span> <span data-ttu-id="e00e4-130">Wenn Sie jedoch Schwierigkeiten beim Erstellen von Indizes feststellen, sollten Sie den Wert dieser Option abweichend vom Ausführungswert erhöhen.</span><span class="sxs-lookup"><span data-stu-id="e00e4-130">However, if you experience difficulties creating indexes, consider increasing the value of this option from its run value.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e00e4-131">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="e00e4-131">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e00e4-132">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="e00e4-132">Permissions</span></span>  
 <span data-ttu-id="e00e4-133">Die Ausführungsberechtigungen für **sp_configure** ohne Parameter oder nur mit dem ersten Parameter werden standardmäßig allen Benutzern erteilt.</span><span class="sxs-lookup"><span data-stu-id="e00e4-133">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="e00e4-134">Zum Ausführen von **sp_configure** mit beiden Parametern zum Ändern einer Konfigurationsoption oder zum Ausführen der RECONFIGURE-Anweisung muss einem Benutzer die ALTER SETTINGS-Berechtigung auf Serverebene erteilt worden sein.</span><span class="sxs-lookup"><span data-stu-id="e00e4-134">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="e00e4-135">Die ALTER SETTINGS-Berechtigung ist in den festen Serverrollen **sysadmin** und **serveradmin** eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="e00e4-135">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="e00e4-136">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e00e4-136">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-index-create-memory-option"></a><span data-ttu-id="e00e4-137">So konfigurieren Sie die Option "Speicher für Indexerstellung"</span><span class="sxs-lookup"><span data-stu-id="e00e4-137">To configure the index create memory option</span></span>  
  
1.  <span data-ttu-id="e00e4-138">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf einen Server, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="e00e4-138">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="e00e4-139">Klicken Sie auf den **Speicher** -Knoten.</span><span class="sxs-lookup"><span data-stu-id="e00e4-139">Click the **Memory** node.</span></span>  
  
3.  <span data-ttu-id="e00e4-140">Geben Sie unter **Speicher für Indexerstellung**den gewünschten Wert für die Option „Speicher für Indexerstellung“ ein, oder wählen Sie einen Wert aus.</span><span class="sxs-lookup"><span data-stu-id="e00e4-140">Under **Index creation memory**, type or select the desired value for the index create memory option.</span></span>  
  
     <span data-ttu-id="e00e4-141">Sie können mit der Option **Speicher für Indexerstellung** den Umfang an Speicherplatz steuern, der für Sortiervorgänge bei der Indexerstellung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e00e4-141">Use the **index create memory** option to control the amount of memory used by index creation sorts.</span></span> <span data-ttu-id="e00e4-142">Bei der Option **Speicher für Indexerstellung** handelt es sich um eine selbstkonfigurierende Option, die in den meisten Fällen ohne weitere Anpassung funktionieren sollte.</span><span class="sxs-lookup"><span data-stu-id="e00e4-142">The **index create memory** option is self-configuring and should work in most cases without requiring adjustment.</span></span> <span data-ttu-id="e00e4-143">Wenn Sie jedoch Schwierigkeiten beim Erstellen von Indizes feststellen, sollten Sie den Wert dieser Option abweichend vom Ausführungswert erhöhen.</span><span class="sxs-lookup"><span data-stu-id="e00e4-143">However, if you experience difficulties creating indexes, consider increasing the value of this option from its run value.</span></span> <span data-ttu-id="e00e4-144">Das Sortieren von Abfragen wird über die Option **Min. Arbeitsspeicher pro Abfrage** gesteuert.</span><span class="sxs-lookup"><span data-stu-id="e00e4-144">Query sorts are controlled through the **min memory per query** option.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="e00e4-145">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e00e4-145">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-index-create-memory-option"></a><span data-ttu-id="e00e4-146">So konfigurieren Sie die Option "Speicher für Indexerstellung"</span><span class="sxs-lookup"><span data-stu-id="e00e4-146">To configure the index create memory option</span></span>  
  
1.  <span data-ttu-id="e00e4-147">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="e00e4-147">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e00e4-148">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="e00e4-148">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e00e4-149">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="e00e4-149">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="e00e4-150">In diesem Beispiel wird gezeigt, wie [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) verwendet wird, um den Wert der Option `index create memory` auf `4096`festzulegen.</span><span class="sxs-lookup"><span data-stu-id="e00e4-150">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `index create memory` option to `4096`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
EXEC sp_configure 'index create memory', 4096  
GO  
RECONFIGURE;  
GO  
```  
  
 <span data-ttu-id="e00e4-151">Weitere Informationen finden Sie unter [Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md)angezeigt oder konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="e00e4-151">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-index-create-memory-option"></a><a name="FollowUp"></a><span data-ttu-id="e00e4-152">Nächster Schritt: Nach dem Konfigurieren der Option „Speicher für Indexerstellung“</span><span class="sxs-lookup"><span data-stu-id="e00e4-152">Follow Up: After you configure the index create memory option</span></span>  
 <span data-ttu-id="e00e4-153">Die Einstellung tritt ohne Neustarten des Servers sofort in Kraft.</span><span class="sxs-lookup"><span data-stu-id="e00e4-153">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e00e4-154">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e00e4-154">See Also</span></span>  
 <span data-ttu-id="e00e4-155">[sys.configurations &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-configurations-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e00e4-155">[sys.configurations &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-configurations-transact-sql) </span></span>  
 <span data-ttu-id="e00e4-156">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e00e4-156">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="e00e4-157">[Serverkonfigurationsoptionen für den Serverarbeitsspeicher](server-memory-server-configuration-options.md) </span><span class="sxs-lookup"><span data-stu-id="e00e4-157">[Server Memory Server Configuration Options](server-memory-server-configuration-options.md) </span></span>  
 <span data-ttu-id="e00e4-158">[Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e00e4-158">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="e00e4-159">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e00e4-159">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
