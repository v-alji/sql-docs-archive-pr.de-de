---
title: Konfigurieren der Serverkonfigurationsoption „Netzwerkpaketgröße“ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- default packet size
- size [SQL Server], packets
- packets [SQL Server], size
- network packet size option
ms.assetid: 236985bf-fc4a-4a57-98f7-a71ef977fd7b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 69e5963675349bceff6a0ee022f6dc28da03db59
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700209"
---
# <a name="configure-the-network-packet-size-server-configuration-option"></a><span data-ttu-id="bc935-102">Konfigurieren der Serverkonfigurationsoption Netzwerkpaketgröße</span><span class="sxs-lookup"><span data-stu-id="bc935-102">Configure the network packet size Server Configuration Option</span></span>
  <span data-ttu-id="bc935-103">In diesem Thema wird beschrieben, wie die `network packet size` Server Konfigurationsoption in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von oder konfiguriert wird [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bc935-103">This topic describes how to configure the `network packet size` server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="bc935-104">Mit der- `network packet size` Option wird die Paketgröße (in Bytes) festgelegt, die im gesamten Netzwerk verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="bc935-104">The `network packet size` option sets the packet size (in bytes) that is used across the whole network.</span></span> <span data-ttu-id="bc935-105">Pakete sind die Datenabschnitte fester Größe, die Anforderungen und Ergebnisse zwischen Clients und Servern übertragen.</span><span class="sxs-lookup"><span data-stu-id="bc935-105">Packets are the fixed-size chunks of data that transfer requests and results between clients and servers.</span></span> <span data-ttu-id="bc935-106">Die Standardpaketgröße beträgt 4.096 Bytes.</span><span class="sxs-lookup"><span data-stu-id="bc935-106">The default packet size is 4,096 bytes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bc935-107">Sie sollten die Paketgröße nur dann ändern, wenn Sie sicher sind, dass die Leistung dadurch verbessert werden kann.</span><span class="sxs-lookup"><span data-stu-id="bc935-107">Do not change the packet size unless you are certain that it will improve performance.</span></span> <span data-ttu-id="bc935-108">Für die meisten Anwendungen empfiehlt sich die Standardpaketgröße.</span><span class="sxs-lookup"><span data-stu-id="bc935-108">For most applications, the default packet size is best.</span></span>  
  
 <span data-ttu-id="bc935-109">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="bc935-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="bc935-110">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="bc935-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="bc935-111">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="bc935-111">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="bc935-112">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="bc935-112">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="bc935-113">Security</span><span class="sxs-lookup"><span data-stu-id="bc935-113">Security</span></span>](#Security)  
  
-   <span data-ttu-id="bc935-114">**So konfigurieren Sie die Option Netzwerkpaketgröße mit:**</span><span class="sxs-lookup"><span data-stu-id="bc935-114">**To configure the network packet size option, using:**</span></span>  
  
     [<span data-ttu-id="bc935-115">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="bc935-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="bc935-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="bc935-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="bc935-117">**Nachverfolgung:**  [Nach dem Konfigurieren der Option „Netzwerkpaketgröße“](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="bc935-117">**Follow Up:**  [After you configure the network packet size option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="bc935-118">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="bc935-118">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="bc935-119">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="bc935-119">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="bc935-120">Die maximale Netzwerkpaketgröße für verschlüsselte Verbindungen beträgt 16.383 Bytes.</span><span class="sxs-lookup"><span data-stu-id="bc935-120">The maximum network packet size for encrypted connections is 16,383 bytes.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="bc935-121">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="bc935-121">Recommendations</span></span>  
  
-   <span data-ttu-id="bc935-122">Diese Option ist eine erweiterte Option und sollte ausschließlich von einem erfahrenen Datenbankadministrator oder einem zertifizierten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Techniker geändert werden.</span><span class="sxs-lookup"><span data-stu-id="bc935-122">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="bc935-123">Wenn eine Anwendung Massenkopiervorgänge ausführt oder große Mengen an Daten vom Typ text oder image sendet bzw. empfängt, kann eine über der Standardgröße liegende Paketgröße die Effizienz verbessern, da weniger Netzwerklesevorgänge und -schreibvorgänge ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="bc935-123">If an application does bulk copy operations or sends or receives large amounts of text or image data, a packet size larger than the default might improve efficiency because it results in fewer network read-and-write operations.</span></span> <span data-ttu-id="bc935-124">Sendet und empfängt eine Anwendung wenige Informationen, können Sie die Paketgröße auf 512 Bytes festlegen. Dies ist für die meisten Datenübertragungen ausreichend.</span><span class="sxs-lookup"><span data-stu-id="bc935-124">If an application sends and receives small amounts of information, the packet size can be set to 512 bytes, which is sufficient for most data transfers.</span></span>  
  
-   <span data-ttu-id="bc935-125">Bei Systemen, die verschiedene Netzwerkprotokolle verwenden, sollten Sie die Option „Netzwerkpaketgröße“ auf die Größe festlegen, die das am häufigsten verwendete Protokoll vorgibt.</span><span class="sxs-lookup"><span data-stu-id="bc935-125">On systems that are using different network protocols, set network packet size to the size for the most common protocol used.</span></span> <span data-ttu-id="bc935-126">Wenn Netzwerkprotokolle größere Pakete unterstützen, kann durch Netzwerkpaketgröße die Netzwerkleistung verbessert werden.</span><span class="sxs-lookup"><span data-stu-id="bc935-126">The network packet size option improves network performance when network protocols support larger packets.</span></span> <span data-ttu-id="bc935-127">Clientanwendungen können diesen Wert überschreiben.</span><span class="sxs-lookup"><span data-stu-id="bc935-127">Client applications can override this value.</span></span>  
  
-   <span data-ttu-id="bc935-128">Sie können auch die Funktionen von OLE DB, ODBC (Open Database Connectivity) und der DB-Library aufrufen, um eine Änderung der Paketgröße anzufordern.</span><span class="sxs-lookup"><span data-stu-id="bc935-128">You can also call OLE DB, Open Database Connectivity (ODBC), and DB-Library functions request a change the packet size.</span></span> <span data-ttu-id="bc935-129">Wenn der Server die angeforderte Paketgröße nicht unterstützt, sendet [!INCLUDE[ssDE](../../includes/ssde-md.md)] eine Warnmeldung an den Client.</span><span class="sxs-lookup"><span data-stu-id="bc935-129">If the server cannot support the requested packet size, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] will send a warning message to the client.</span></span> <span data-ttu-id="bc935-130">Unter gewissen Umständen führt das Ändern der Paketgröße möglicherweise zu einem Kommunikationsverbindungsfehler, wie beispielsweise:</span><span class="sxs-lookup"><span data-stu-id="bc935-130">In some circumstances, changing the packet size might lead to a communication link failure, such as the following:</span></span>  
  
     `Native Error: 233, no process is on the other end of the pipe.`  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="bc935-131">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="bc935-131">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="bc935-132">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="bc935-132">Permissions</span></span>  
 <span data-ttu-id="bc935-133">Die Ausführungsberechtigungen für **sp_configure** ohne Parameter oder nur mit dem ersten Parameter werden standardmäßig allen Benutzern erteilt.</span><span class="sxs-lookup"><span data-stu-id="bc935-133">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="bc935-134">Zum Ausführen von **sp_configure** mit beiden Parametern zum Ändern einer Konfigurationsoption oder zum Ausführen der RECONFIGURE-Anweisung muss einem Benutzer die ALTER SETTINGS-Berechtigung auf Serverebene erteilt worden sein.</span><span class="sxs-lookup"><span data-stu-id="bc935-134">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="bc935-135">Die ALTER SETTINGS-Berechtigung ist in den festen Serverrollen **sysadmin** und **serveradmin** eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="bc935-135">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="bc935-136">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="bc935-136">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-network-packet-size-option"></a><span data-ttu-id="bc935-137">So konfigurieren Sie die Option Netzwerkpaketgröße</span><span class="sxs-lookup"><span data-stu-id="bc935-137">To configure the network packet size option</span></span>  
  
1.  <span data-ttu-id="bc935-138">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf einen Server, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="bc935-138">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="bc935-139">Klicken Sie auf den **Erweitert** -Knoten.</span><span class="sxs-lookup"><span data-stu-id="bc935-139">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="bc935-140">Wählen Sie unter **Netzwerk**einen Wert im Feld **Netzwerkpaketgröße** aus.</span><span class="sxs-lookup"><span data-stu-id="bc935-140">Under **Network**, select a value for the **Network Packet Size** box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="bc935-141">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="bc935-141">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-network-packet-size-option"></a><span data-ttu-id="bc935-142">So konfigurieren Sie die Option Netzwerkpaketgröße</span><span class="sxs-lookup"><span data-stu-id="bc935-142">To configure the network packet size option</span></span>  
  
1.  <span data-ttu-id="bc935-143">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="bc935-143">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="bc935-144">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="bc935-144">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="bc935-145">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="bc935-145">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="bc935-146">In diesem Beispiel wird gezeigt, wie [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) verwendet wird, um den Wert der Option `network packet size` auf `6500` Byte festzulegen.</span><span class="sxs-lookup"><span data-stu-id="bc935-146">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `network packet size` option to `6500` bytes.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'network packet size', 6500 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="bc935-147">Weitere Informationen finden Sie unter [Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md)angezeigt oder konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="bc935-147">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-network-packet-size-option"></a><a name="FollowUp"></a><span data-ttu-id="bc935-148">Nächster Schritt: Nach dem Konfigurieren der Option „Netzwerkpaketgröße“</span><span class="sxs-lookup"><span data-stu-id="bc935-148">Follow Up: After you configure the network packet size option</span></span>  
 <span data-ttu-id="bc935-149">Die Einstellung tritt ohne Neustarten des Servers sofort in Kraft.</span><span class="sxs-lookup"><span data-stu-id="bc935-149">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc935-150">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bc935-150">See Also</span></span>  
 <span data-ttu-id="bc935-151">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="bc935-151">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="bc935-152">[Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="bc935-152">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="bc935-153">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="bc935-153">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
