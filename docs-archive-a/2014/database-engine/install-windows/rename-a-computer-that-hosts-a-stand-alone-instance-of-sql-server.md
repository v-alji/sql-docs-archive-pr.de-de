---
title: Umbenennen eines Computers, der eine eigenständige Instanz von SQL Server hostet | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
helpviewer_keywords:
- remote login errors [SQL Server]
- standalone computer names [SQL Server]
- names [SQL Server], standalone instances of SQL Server
- renaming standalone instances of SQL Server
- sysservers system table
- removing remote logins
- deleting remote logins
- dropping remote logins
ms.assetid: bbaf1445-b8a2-4ebf-babe-17d8cf20b037
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 079348921900a7cbf880027433280253df1a9e30
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724086"
---
# <a name="rename-a-computer-that-hosts-a-stand-alone-instance-of-sql-server"></a><span data-ttu-id="a07d7-102">Umbenennen eines Computers, der eine eigenständige Instanz von SQL Server hostet</span><span class="sxs-lookup"><span data-stu-id="a07d7-102">Rename a Computer that Hosts a Stand-Alone Instance of SQL Server</span></span>
  <span data-ttu-id="a07d7-103">Wenn Sie den Namen des Computers ändern, auf dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]ausgeführt wird, wird der neue Name beim Starten von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] erkannt.</span><span class="sxs-lookup"><span data-stu-id="a07d7-103">When you change the name of the computer that is running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the new name is recognized during [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] startup.</span></span> <span data-ttu-id="a07d7-104">Sie müssen das Setup nicht erneut ausführen, um den Computernamen zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="a07d7-104">You do not have to run Setup again to reset the computer name.</span></span> <span data-ttu-id="a07d7-105">Führen Sie stattdessen die folgenden Schritte aus, um die Systemmetadaten zu aktualisieren, die in sys.servers gespeichert sind und von der Systemfunktion @@SERVERNAME gemeldet werden.</span><span class="sxs-lookup"><span data-stu-id="a07d7-105">Instead, use the following steps to update system metadata that is stored in sys.servers and reported by the system function @@SERVERNAME.</span></span> <span data-ttu-id="a07d7-106">Aktualisieren Sie die Systemmetadaten, um Änderungen des Computernamens für Remoteverbindungen und -anwendungen widerzuspiegeln, die @@SERVERNAME verwenden oder die den Servernamen von sys.servers abfragen.</span><span class="sxs-lookup"><span data-stu-id="a07d7-106">Update system metadata to reflect computer name changes for remote connections and applications that use @@SERVERNAME, or that query the server name from sys.servers.</span></span>  
  
 <span data-ttu-id="a07d7-107">Die folgenden Schritte können nicht verwendet werden, um eine Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]umzubenennen.</span><span class="sxs-lookup"><span data-stu-id="a07d7-107">The following steps cannot be used to rename an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a07d7-108">Die Schritte können nur verwendet werden, um den Teil des Instanznamens umzubenennen, der dem Computernamen entspricht.</span><span class="sxs-lookup"><span data-stu-id="a07d7-108">They can be used only to rename the part of the instance name that corresponds to the computer name.</span></span> <span data-ttu-id="a07d7-109">Sie können beispielsweise einen Computer mit dem Namen MB1 umbenennen (z. B. in MB2), der eine Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mit dem Namen Instance1 hostet.</span><span class="sxs-lookup"><span data-stu-id="a07d7-109">For example, you can change a computer named MB1 that hosts an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] named Instance1 to another name, such as MB2.</span></span> <span data-ttu-id="a07d7-110">Der Teil des Namens, der sich auf die Instanz bezieht, Instance1, bleibt jedoch unverändert.</span><span class="sxs-lookup"><span data-stu-id="a07d7-110">However, the instance part of the name, Instance1, will remain unchanged.</span></span> <span data-ttu-id="a07d7-111">In diesem Beispiel wird \\\\*ComputerName*\\*InstanceName* von \\\MB1\Instance1 in \\\MB2\Instance1 geändert.</span><span class="sxs-lookup"><span data-stu-id="a07d7-111">In this example, the \\\\*ComputerName*\\*InstanceName* would be changed from \\\MB1\Instance1 to \\\MB2\Instance1.</span></span>  
  
 <span data-ttu-id="a07d7-112">**Voraussetzungen**</span><span class="sxs-lookup"><span data-stu-id="a07d7-112">**Before you begin**</span></span>  
  
 <span data-ttu-id="a07d7-113">Bevor Sie den Umbenennungsprozess beginnen, überprüfen Sie die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="a07d7-113">Before you begin the renaming process, review the following information:</span></span>  
  
-   <span data-ttu-id="a07d7-114">Wenn eine Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Teil eines [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Failoverclusters ist, unterscheidet sich der Umbenennungsvorgang des Computers von einem Computer, der eine eigenständige Instanz hostet.</span><span class="sxs-lookup"><span data-stu-id="a07d7-114">When an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is part of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster, the computer renaming process differs from a computer that hosts a stand-alone instance.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="a07d7-115">unterstützt nicht die Umbenennung von Computern, die an einer Replikation beteiligt sind. Eine Ausnahme stellt die Verwendung des Protokollversands mit Replikation dar.</span><span class="sxs-lookup"><span data-stu-id="a07d7-115">does not support renaming computers that are involved in replication, except when you use log shipping with replication.</span></span> <span data-ttu-id="a07d7-116">Der sekundäre Computer beim Protokollversand kann umbenannt werden, wenn eine Wiederherstellung des primären Computers nicht mehr möglich ist.</span><span class="sxs-lookup"><span data-stu-id="a07d7-116">The secondary computer in log shipping can be renamed if the primary computer is permanently lost.</span></span> <span data-ttu-id="a07d7-117">Weitere Informationen finden Sie unter [Protokollversand und Replikation &#40;SQL Server&#41;](../log-shipping/log-shipping-and-replication-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="a07d7-117">For more information, see [Log Shipping and Replication &#40;SQL Server&#41;](../log-shipping/log-shipping-and-replication-sql-server.md).</span></span>  
  
-   <span data-ttu-id="a07d7-118">Wenn Sie einen Computer umbenennen, der für die Verwendung von [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] konfiguriert wurde, kann es sein, dass [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] nach der Namensänderung nicht mehr zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="a07d7-118">When you rename a computer that is configured to use [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] might not be available after the computer name change.</span></span> <span data-ttu-id="a07d7-119">Weitere Informationen finden Sie unter [Umbenennen eines Berichtsservercomputers](../../reporting-services/report-server/rename-a-report-server-computer.md).</span><span class="sxs-lookup"><span data-stu-id="a07d7-119">For more information, see [Rename a Report Server Computer](../../reporting-services/report-server/rename-a-report-server-computer.md).</span></span>  
  
-   <span data-ttu-id="a07d7-120">Wenn Sie einen für die Verwendung der Datenbankspiegelung konfigurierten Computer umbenennen, müssen Sie die Datenbankspiegelung vor dem Umbenennungsvorgang deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="a07d7-120">When you rename a computer that is configured to use database mirroring, you must turn off database mirroring before the renaming operation.</span></span> <span data-ttu-id="a07d7-121">Aktivieren Sie Datenbankspiegelung dann mit dem neuen Computernamen erneut.</span><span class="sxs-lookup"><span data-stu-id="a07d7-121">Then, re-establish database mirroring with the new computer name.</span></span> <span data-ttu-id="a07d7-122">Die Metadaten für die Datenbankspiegelung werden nicht automatisch aktualisiert, um den neuen Namen des Computers widerzuspiegeln.</span><span class="sxs-lookup"><span data-stu-id="a07d7-122">Metadata for database mirroring will not be updated automatically to reflect the new computer name.</span></span> <span data-ttu-id="a07d7-123">Führen Sie die folgenden Schritte aus, um die Systemmetadaten zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="a07d7-123">Use the following steps to update system metadata.</span></span>  
  
-   <span data-ttu-id="a07d7-124">Es kann sein, dass Benutzer, die über eine Windows-Gruppe mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] verbunden sind, in der ein hartcodierter Verweis auf den Computernamen verwendet wird, die Verbindung zu [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]nicht herstellen können.</span><span class="sxs-lookup"><span data-stu-id="a07d7-124">Users who connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] through a Windows group that uses a hard-coded reference to the computer name might not be able to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a07d7-125">Dies kann nach der Umbenennung passieren, wenn die Windows-Gruppe den alten Computernamen angibt.</span><span class="sxs-lookup"><span data-stu-id="a07d7-125">This can occur after the rename if the Windows group specifies the old computer name.</span></span> <span data-ttu-id="a07d7-126">Aktualisieren Sie die Windows-Gruppe für die Verwendung des neuen Computernamens, um sicherzustellen, dass solche Windows-Gruppen nach dem Umbenennungsvorgang für die Verbindung mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="a07d7-126">To ensure that such Windows groups have [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connectivity following the renaming operation, update the Windows group to specify the new computer name.</span></span>  
  
 <span data-ttu-id="a07d7-127">Sie können mithilfe des neuen Computernamens eine Verbindung zu [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] herstellen, nachdem Sie [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]neu gestartet haben.</span><span class="sxs-lookup"><span data-stu-id="a07d7-127">You can connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using the new computer name after you have restarted [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a07d7-128">Um sicherzustellen, dass @@SERVERNAME den aktualisierten Namen der lokalen Serverinstanz zurückgibt, führen Sie manuell eine der folgenden Prozeduren aus, die für Ihr Szenario zutrifft.</span><span class="sxs-lookup"><span data-stu-id="a07d7-128">To ensure that @@SERVERNAME returns the updated name of the local server instance, you should manually run the following procedure that applies to your scenario.</span></span> <span data-ttu-id="a07d7-129">Die verwendete Prozedur hängt davon ab, ob Sie einen Computer aktualisieren, der eine Standardinstanz oder eine benannte Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]hostet.</span><span class="sxs-lookup"><span data-stu-id="a07d7-129">The procedure you use depends on whether you are updating a computer that hosts a default or named instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
### <a name="to-rename-a-computer-that-hosts-a-stand-alone-instance-of-ssnoversion"></a><span data-ttu-id="a07d7-130">So benennen Sie einen Computer um, der eine eigenständige Instanz hostet von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a07d7-130">To rename a computer that hosts a stand-alone instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
  
-   <span data-ttu-id="a07d7-131">Führen Sie für einen umbenannten Computer, der eine Standardinstanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]hostet, die folgenden Prozeduren aus:</span><span class="sxs-lookup"><span data-stu-id="a07d7-131">For a renamed computer that hosts a default instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], run the following procedures:</span></span>  
  
    ```  
    sp_dropserver <old_name>;  
    GO  
    sp_addserver <new_name>, local;  
    GO  
    ```  
  
     <span data-ttu-id="a07d7-132">Starten Sie die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]neu.</span><span class="sxs-lookup"><span data-stu-id="a07d7-132">Restart the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="a07d7-133">Führen Sie für einen umbenannten Computer, der eine benannte Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]hostet, die folgenden Prozeduren aus:</span><span class="sxs-lookup"><span data-stu-id="a07d7-133">For a renamed computer that hosts a named instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], run the following procedures:</span></span>  
  
    ```  
    sp_dropserver <old_name\instancename>;  
    GO  
    sp_addserver <new_name\instancename>, local;  
    GO  
    ```  
  
     <span data-ttu-id="a07d7-134">Starten Sie die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]neu.</span><span class="sxs-lookup"><span data-stu-id="a07d7-134">Restart the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="after-the-renaming-operation"></a><span data-ttu-id="a07d7-135">Nach dem Umbenennungsvorgang</span><span class="sxs-lookup"><span data-stu-id="a07d7-135">After the Renaming Operation</span></span>  
 <span data-ttu-id="a07d7-136">Nachdem ein Computer umbenannt wurde, müssen alle Verbindungen, bei denen der alte Computername verwendet wurde, mithilfe des neuen Namens hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="a07d7-136">After a computer has been renamed, any connections that used the old computer name must connect by using the new name.</span></span>  
  
#### <a name="to-verify-that-the-renaming-operation-has-completed-successfully"></a><span data-ttu-id="a07d7-137">So überprüfen Sie, ob der Umbenennungsvorgang erfolgreich abgeschlossen wurde</span><span class="sxs-lookup"><span data-stu-id="a07d7-137">To verify that the renaming operation has completed successfully</span></span>  
  
-   <span data-ttu-id="a07d7-138">Wählen Sie entweder Informationen von @@SERVERNAME oder von sys.servers aus.</span><span class="sxs-lookup"><span data-stu-id="a07d7-138">Select information from either @@SERVERNAME or sys.servers.</span></span> <span data-ttu-id="a07d7-139">Die @@SERVERNAME-Funktion gibt den neuen Namen zurück, und in der sys.servers-Tabelle wird der neue Name angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a07d7-139">The @@SERVERNAME function will return the new name, and the sys.servers table will show the new name.</span></span> <span data-ttu-id="a07d7-140">Im folgenden Beispiel wird die Verwendung von @@SERVERNAME veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="a07d7-140">The following example shows the use of @@SERVERNAME.</span></span>  
  
    ```  
    SELECT @@SERVERNAME AS 'Server Name';  
    ```  
  
## <a name="additional-considerations"></a><span data-ttu-id="a07d7-141">Weitere Überlegungen</span><span class="sxs-lookup"><span data-stu-id="a07d7-141">Additional Considerations</span></span>  
 <span data-ttu-id="a07d7-142">**Remoteanmeldungen** : Wenn der Computer über Remoteanmeldungen verfügt, wird beim Ausführen von **sp_dropserver** ggf. ein Fehler generiert, der dem Folgenden ähnelt:</span><span class="sxs-lookup"><span data-stu-id="a07d7-142">**Remote Logins** - If the computer has any remote logins, running **sp_dropserver** might generate an error similar to the following:</span></span>  
  
 `Server: Msg 15190, Level 16, State 1, Procedure sp_dropserver, Line 44 There are still remote logins for the server 'SERVER1'.`  
  
 <span data-ttu-id="a07d7-143">Um den Fehler zu beheben, müssen Sie Remoteanmeldungen für diesen Server löschen.</span><span class="sxs-lookup"><span data-stu-id="a07d7-143">To resolve the error, you must drop remote logins for this server.</span></span>  
  
#### <a name="to-drop-remote-logins"></a><span data-ttu-id="a07d7-144">So löschen Sie Remoteanmeldungen</span><span class="sxs-lookup"><span data-stu-id="a07d7-144">To drop remote logins</span></span>  
  
-   <span data-ttu-id="a07d7-145">Führen Sie für eine Standardinstanz die folgende Prozedur aus:</span><span class="sxs-lookup"><span data-stu-id="a07d7-145">For a default instance, run the following procedure:</span></span>  
  
    ```  
    sp_dropremotelogin old_name;  
    GO  
    ```  
  
-   <span data-ttu-id="a07d7-146">Führen Sie für eine benannte Instanz die folgende Prozedur aus:</span><span class="sxs-lookup"><span data-stu-id="a07d7-146">For a named instance, run the following procedure:</span></span>  
  
    ```  
    sp_dropremotelogin old_name\instancename;  
    GO  
    ```  
  
 <span data-ttu-id="a07d7-147">**Verbindungsserverkonfigurationen** : Das Umbenennen von Computern wirkt sich auf die Verbindungsserverkonfigurationen aus.</span><span class="sxs-lookup"><span data-stu-id="a07d7-147">**Linked Server Configurations** - Linked server configurations will be affected by the computer renaming operation.</span></span> <span data-ttu-id="a07d7-148">Verwenden Sie `sp_addlinkedserver` oder `sp_setnetname`, um Verweise auf Computernamen zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="a07d7-148">Use `sp_addlinkedserver` or `sp_setnetname` to update computer name references.</span></span> <span data-ttu-id="a07d7-149">Weitere Informationen finden Sie unter [sp_addlinkedserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql) oder [sp_setnetname &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-setnetname-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a07d7-149">For more information, see the [sp_addlinkedserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql) or [sp_setnetname &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-setnetname-transact-sql).</span></span>  
  
 <span data-ttu-id="a07d7-150">**Clientaliasnamen**: Das Umbenennen von Computern wirkt sich auf Clientaliasnamen aus, die Named Pipes verwenden.</span><span class="sxs-lookup"><span data-stu-id="a07d7-150">**Client Alias Names** - Client aliases that use named pipes will be affected by the computer renaming operation.</span></span> <span data-ttu-id="a07d7-151">Wenn z. B. ein Alias "PROD_SRVR" erstellt wurde, um auf SRVR1 zu verweisen, und dieser das Named Pipes-Protokoll verwendet, lautet der Pipe-Name `\\SRVR1\pipe\sql\query`.</span><span class="sxs-lookup"><span data-stu-id="a07d7-151">For example, if an alias "PROD_SRVR" was created to point to SRVR1 and uses the named pipes protocol, the pipe name will look like `\\SRVR1\pipe\sql\query`.</span></span> <span data-ttu-id="a07d7-152">Nachdem der Computer umbenannt wurde, ist der Pfad der Named Pipe nicht mehr gültig.</span><span class="sxs-lookup"><span data-stu-id="a07d7-152">After the computer is renamed, the path of the named pipe will no longer be valid and.</span></span> <span data-ttu-id="a07d7-153">Weitere Informationen zu Named Pipes finden Sie unter [Erstellen einer gültigen Verbindungszeichenfolge mithilfe von Named Pipes](https://go.microsoft.com/fwlink/?LinkId=111063).</span><span class="sxs-lookup"><span data-stu-id="a07d7-153">For more information about named pipes, see the [Creating a Valid Connection String Using Named Pipes](https://go.microsoft.com/fwlink/?LinkId=111063).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a07d7-154">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a07d7-154">See Also</span></span>  
 [<span data-ttu-id="a07d7-155">Installieren von SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="a07d7-155">Install SQL Server 2014</span></span>](../../database-engine/install-windows/install-sql-server.md)  
  
  
