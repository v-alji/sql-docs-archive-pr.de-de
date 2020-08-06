---
title: Anzeigen oder Konfigurieren von Verbindungsoptionen für Remoteserver (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- remote servers [SQL Server], connection options
- servers [SQL Server], remote
- connections [SQL Server], remote servers
ms.assetid: 356d3e6b-8514-4bd2-a683-9de147949b2b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 73fe5e484d62cde025d1a560937e8cbcf5ec361d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697146"
---
# <a name="view-or-configure-remote-server-connection-options-sql-server"></a><span data-ttu-id="e7de7-102">Anzeigen oder Konfigurieren von Verbindungsoptionen für Remoteserver (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="e7de7-102">View or Configure Remote Server Connection Options (SQL Server)</span></span>
  <span data-ttu-id="e7de7-103">In diesem Thema wird beschrieben, wie Sie Verbindungsoptionen für Remoteserver auf Serverebene in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]anzeigen oder konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="e7de7-103">This topic describes how to view or configure remote server connection options at the server level in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="e7de7-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="e7de7-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="e7de7-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="e7de7-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e7de7-106">Security</span><span class="sxs-lookup"><span data-stu-id="e7de7-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e7de7-107">**So zeigen Sie Verbindungsoptionen für Remoteserver an oder konfigurieren sie mit**</span><span class="sxs-lookup"><span data-stu-id="e7de7-107">**To view or configure remote server connection options, using:**</span></span>  
  
     [<span data-ttu-id="e7de7-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e7de7-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="e7de7-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e7de7-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="e7de7-110">**Nachverfolgung:**  [Nach dem Konfigurieren von Verbindungsoptionen für Remoteserver](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="e7de7-110">**Follow Up:**  [After you configure remote server connection options](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e7de7-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="e7de7-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e7de7-112">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="e7de7-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e7de7-113">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="e7de7-113">Permissions</span></span>  
 <span data-ttu-id="e7de7-114">Für das Ausführen von **sp_serveroption** sind ALTER ANY LINKED SERVER-Berechtigungen auf dem Server erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e7de7-114">Executing **sp_serveroption** requires ALTER ANY LINKED SERVER permission on the server.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="e7de7-115">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e7de7-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-or-configure-remote-server-connection-options"></a><span data-ttu-id="e7de7-116">So zeigen Sie Verbindungsoptionen für Remoteserver an oder konfigurieren sie</span><span class="sxs-lookup"><span data-stu-id="e7de7-116">To view or configure remote server connection options</span></span>  
  
1.  <span data-ttu-id="e7de7-117">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf einen Server, und klicken Sie anschließend auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="e7de7-117">In Object Explorer, right-click a server, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="e7de7-118">Klicken Sie im Dialogfeld **Eigenschaften von SQL Server - \<***server_name***>** auf **Verbindungen**.</span><span class="sxs-lookup"><span data-stu-id="e7de7-118">In the **SQL Server Properties - \<***server_name***>** dialog box, click **Connections**.</span></span>  
  
3.  <span data-ttu-id="e7de7-119">Überprüfen Sie auf der Seite **Verbindungen** die Einstellungen für **Remoteserververbindungen** , und ändern Sie sie gegebenenfalls.</span><span class="sxs-lookup"><span data-stu-id="e7de7-119">On the **Connections** page, review the **Remote server connections** settings, and modify them if necessary.</span></span>  
  
4.  <span data-ttu-id="e7de7-120">Wiederholen Sie Schritt 1 bis 3 auf dem zweiten Server des Remoteserverpaares.</span><span class="sxs-lookup"><span data-stu-id="e7de7-120">Repeat steps 1 through 3 on the other server of the remote server pair.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="e7de7-121">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e7de7-121">Using Transact-SQL</span></span>  
  
#### <a name="to-view-remote-server-connection-options"></a><span data-ttu-id="e7de7-122">So zeigen Sie Verbindungsoptionen für Remoteserver an</span><span class="sxs-lookup"><span data-stu-id="e7de7-122">To view remote server connection options</span></span>  
  
1.  <span data-ttu-id="e7de7-123">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="e7de7-123">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e7de7-124">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="e7de7-124">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e7de7-125">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="e7de7-125">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="e7de7-126">In diesem Beispiel werden von [sp_helpserver](/sql/relational-databases/system-stored-procedures/sp-helpserver-transact-sql) Informationen über alle Remoteserver zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e7de7-126">This example uses [sp_helpserver](/sql/relational-databases/system-stored-procedures/sp-helpserver-transact-sql) to return information about all remote servers.</span></span>  
  
```sql  
USE master;  
GO  
EXEC sp_helpserver ;  
```  
  
#### <a name="to-configure-remote-server-connection-options"></a><span data-ttu-id="e7de7-127">So konfigurieren Sie Verbindungsoptionen für Remoteserver</span><span class="sxs-lookup"><span data-stu-id="e7de7-127">To configure remote server connection options</span></span>  
  
1.  <span data-ttu-id="e7de7-128">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="e7de7-128">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e7de7-129">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="e7de7-129">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e7de7-130">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="e7de7-130">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="e7de7-131">In diesem Beispiel wird gezeigt, wie [sp_serveroption](/sql/relational-databases/system-stored-procedures/sp-serveroption-transact-sql) zum Konfigurieren eines Remoteservers verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e7de7-131">This example shows how to use [sp_serveroption](/sql/relational-databases/system-stored-procedures/sp-serveroption-transact-sql) to configure a remote server.</span></span> <span data-ttu-id="e7de7-132">In diesem Beispiel wird ein Remoteserver, der einer anderen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Instanz ( `SEATTLE3`) entspricht, so konfiguriert, dass seine Sortierung mit der Sortierung der lokalen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Instanz kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="e7de7-132">The example configures a remote server corresponding to another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], `SEATTLE3`, to be collation compatible with the local instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
```sql  
USE master;  
EXEC sp_serveroption 'SEATTLE3', 'collation compatible', 'true';  
```  
  
##  <a name="follow-up-after-you-configure-remote-server-connection-options"></a><a name="FollowUp"></a><span data-ttu-id="e7de7-133">Nächster Schritt: Nach dem Konfigurieren von Verbindungsoptionen für Remoteserver</span><span class="sxs-lookup"><span data-stu-id="e7de7-133">Follow Up: After you configure remote server connection options</span></span>  
 <span data-ttu-id="e7de7-134">Der Remoteserver muss angehalten und neu gestartet werden, damit die Einstellung wirksam werden kann.</span><span class="sxs-lookup"><span data-stu-id="e7de7-134">The remote server must be stopped and restarted before the setting can take effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7de7-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e7de7-135">See Also</span></span>  
 <span data-ttu-id="e7de7-136">[Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e7de7-136">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="e7de7-137">[Remoteserver](remote-servers.md) </span><span class="sxs-lookup"><span data-stu-id="e7de7-137">[Remote Servers](remote-servers.md) </span></span>  
 <span data-ttu-id="e7de7-138">[Verbindungsserver &#40;Datenbank-Engine&#41;](../../relational-databases/linked-servers/linked-servers-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="e7de7-138">[Linked Servers &#40;Database Engine&#41;](../../relational-databases/linked-servers/linked-servers-database-engine.md) </span></span>  
 <span data-ttu-id="e7de7-139">[sp_linkedservers (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-linkedservers-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e7de7-139">[sp_linkedservers &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-linkedservers-transact-sql) </span></span>  
 <span data-ttu-id="e7de7-140">[sp_helpserver (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-helpserver-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e7de7-140">[sp_helpserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpserver-transact-sql) </span></span>  
 [<span data-ttu-id="e7de7-141">sp_serveroption &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e7de7-141">sp_serveroption &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-serveroption-transact-sql)  
  
  
