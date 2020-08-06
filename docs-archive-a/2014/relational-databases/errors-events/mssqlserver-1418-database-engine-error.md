---
title: MSSQLSERVER_1418 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1418 (Database Engine error)
ms.assetid: 6e9c7241-0201-44e0-9f8b-b3c4e293f0f6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1fcac03f044aacce5e907824862eb589c97a07d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718205"
---
# <a name="mssqlserver_1418"></a><span data-ttu-id="2086e-102">MSSQLSERVER_1418</span><span class="sxs-lookup"><span data-stu-id="2086e-102">MSSQLSERVER_1418</span></span>
    
## <a name="details"></a><span data-ttu-id="2086e-103">Details</span><span class="sxs-lookup"><span data-stu-id="2086e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2086e-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="2086e-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="2086e-105">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="2086e-105">Event ID</span></span>|<span data-ttu-id="2086e-106">1418</span><span class="sxs-lookup"><span data-stu-id="2086e-106">1418</span></span>|  
|<span data-ttu-id="2086e-107">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="2086e-107">Event Source</span></span>|<span data-ttu-id="2086e-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="2086e-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="2086e-109">Komponente</span><span class="sxs-lookup"><span data-stu-id="2086e-109">Component</span></span>|<span data-ttu-id="2086e-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="2086e-110">SQLEngine</span></span>|  
|<span data-ttu-id="2086e-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="2086e-111">Symbolic Name</span></span>|<span data-ttu-id="2086e-112">DBM_PARTNERNOTFOUND</span><span class="sxs-lookup"><span data-stu-id="2086e-112">DBM_PARTNERNOTFOUND</span></span>|  
|<span data-ttu-id="2086e-113">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="2086e-113">Message Text</span></span>|<span data-ttu-id="2086e-114">Die Server-Netzwerkadresse "%.\*ls" ist nicht erreichbar oder nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="2086e-114">The server network address "%.\*ls" can not be reached or does not exist.</span></span> <span data-ttu-id="2086e-115">Überprüfen Sie den Namen der Netzwerkadresse, und dass die Ports für die lokalen und Remoteendpunkte betriebsbereit sind.</span><span class="sxs-lookup"><span data-stu-id="2086e-115">Check the network address name and that the ports for the local and remote endpoints are operational.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2086e-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="2086e-116">Explanation</span></span>  
 <span data-ttu-id="2086e-117">Der Endpunkt des Servernetzwerks hat nicht reagiert, da die angegebene Server-Netzwerkadresse nicht erreichbar oder nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="2086e-117">The server network endpoint did not respond because the specified server network address cannot be reached or does not exist.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2086e-118">Standardmäßig blockiert das [!INCLUDE[msCoName](../../includes/msconame-md.md)]-Betriebssystem alle Ports.</span><span class="sxs-lookup"><span data-stu-id="2086e-118">By default, [!INCLUDE[msCoName](../../includes/msconame-md.md)] operating system blocks all ports.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2086e-119">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="2086e-119">User Action</span></span>  
 <span data-ttu-id="2086e-120">Überprüfen Sie den Namen der Netzwerkadresse, und führen Sie den Befehl erneut aus.</span><span class="sxs-lookup"><span data-stu-id="2086e-120">Verify the network address name and reissue the command.</span></span>  
  
 <span data-ttu-id="2086e-121">Möglicherweise sind korrigierende Maßnahmen auf beiden Partnern erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2086e-121">Corrective action might be required on both partners.</span></span> <span data-ttu-id="2086e-122">Wird beispielsweise diese Fehlermeldung beim Ausführen der SET PARTNER-Anweisung auf der Prinzipalserverinstanz ausgelöst, wird mit der Meldung der Eindruck erweckt, die Ausführung korrigierender Maßnahmen auf der Spiegelserverinstanz wäre ausreichend.</span><span class="sxs-lookup"><span data-stu-id="2086e-122">For example, if this message is raised when you are trying to run SET PARTNER on the principal server instance, the message might imply that you only have to take corrective action on the mirror server instance.</span></span> <span data-ttu-id="2086e-123">Möglicherweise sind jedoch korrigierende Maßnahmen auf beiden Partnern erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2086e-123">However, corrective actions might be required on both partners.</span></span>  
  
### <a name="additional-corrective-actions"></a><span data-ttu-id="2086e-124">Zusätzliche korrigierende Maßnahmen</span><span class="sxs-lookup"><span data-stu-id="2086e-124">Additional Corrective Actions</span></span>  
  
-   <span data-ttu-id="2086e-125">Stellen Sie sicher, dass die Spiegeldatenbank für die Spiegelung bereit ist.</span><span class="sxs-lookup"><span data-stu-id="2086e-125">Make sure that the mirror database is ready for mirroring.</span></span>  
  
-   <span data-ttu-id="2086e-126">Stellen Sie sicher, dass der Name und der Port der Spiegelserverinstanz richtig sind.</span><span class="sxs-lookup"><span data-stu-id="2086e-126">Make sure that the name and port of the mirror server instance are correct.</span></span>  
  
-   <span data-ttu-id="2086e-127">Stellen Sie sicher, dass sich die Ziel-Spiegelserverinstanz nicht hinter einer Firewall befindet.</span><span class="sxs-lookup"><span data-stu-id="2086e-127">Make sure that the destination mirror server instance is not behind a firewall.</span></span>  
  
-   <span data-ttu-id="2086e-128">Stellen Sie sicher, dass sich die Prinzipalserverinstanz nicht hinter einer Firewall befindet.</span><span class="sxs-lookup"><span data-stu-id="2086e-128">Make sure that the principal server instance is not behind a firewall.</span></span>  
  
-   <span data-ttu-id="2086e-129">Stellen Sie mithilfe der **state**- oder **state_desc**-Spalte in der **sys.database_mirroring_endpoints**-Katalogsicht sicher, dass die Endpunkte auf den Partnern gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="2086e-129">Verify that the endpoints are started on the partners by using the **state** or **state_desc** column the of the **sys.database_mirroring_endpoints** catalog view.</span></span> <span data-ttu-id="2086e-130">Wurde einer der Endpunkte nicht gestartet, führen Sie zum Starten eine ALTER ENDPOINT-Anweisung aus.</span><span class="sxs-lookup"><span data-stu-id="2086e-130">If either endpoint is not started, execute an ALTER ENDPOINT statement to start it.</span></span>  
  
-   <span data-ttu-id="2086e-131">Stellen Sie sicher, dass die Prinzipalserverinstanz am Port lauscht, der dem Endpunkt der Datenbankspiegelung zugewiesen wurde, und dass die Spiegelserverinstanz an ihrem Port lauscht.</span><span class="sxs-lookup"><span data-stu-id="2086e-131">Make sure that the principal server instance is listening on the port assigned to its database mirroring endpoint and that and the mirror server instance is listening on its port.</span></span> <span data-ttu-id="2086e-132">Weitere Informationen finden Sie im Abschnitt zum Überprüfen der Verfügbarkeit von Ports weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="2086e-132">For more information, see "Verifying Port Availability," later in this topic.</span></span> <span data-ttu-id="2086e-133">Lauscht einer der Partner an den ihm zugewiesenen Port nicht, ändern Sie den Endpunkt der Datenbankspiegelung so, dass er an einen anderen Port lauscht.</span><span class="sxs-lookup"><span data-stu-id="2086e-133">If a partner is not listening on its assigned port, modify the database mirroring endpoint to listen on a different port.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="2086e-134">Fehlerhaft konfigurierte Sicherheit kann zu einem allgemeinen Setupfehler führen.</span><span class="sxs-lookup"><span data-stu-id="2086e-134">Improperly configured security can cause a general setup error message.</span></span> <span data-ttu-id="2086e-135">In der Regel löscht die Serverinstanz einfach die fehlerhafte Verbindungsanforderung, ohne zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="2086e-135">Typically, the server instance drops the bad connection request without responding.</span></span> <span data-ttu-id="2086e-136">Für den Aufrufer könnte der Eindruck entstehen, dass ein Sicherheitskonfigurationsfehler aufgrund einer Vielzahl anderer Gründe aufgetreten ist, wie z. B. einer nicht vorhandenen Spiegeldatenbank oder aufgrund des mangelhaften Zustands der Datenbank oder unzureichender Berechtigungen usw.</span><span class="sxs-lookup"><span data-stu-id="2086e-136">To the caller, a security-configuration error could appear to have occurred for a variety of other reasons, such as the mirror database in a bad state or does not exist, incorrect permissions, and so on.</span></span>  
  
### <a name="using-the-error-log-file-for-diagnosis"></a><span data-ttu-id="2086e-137">Verwenden der Fehlerprotokolldatei für die Diagnose</span><span class="sxs-lookup"><span data-stu-id="2086e-137">Using the Error Log File for Diagnosis</span></span>  
 <span data-ttu-id="2086e-138">In einigen Fällen kann die Ursache nur anhand der Fehlerprotokolldateien untersucht werden.</span><span class="sxs-lookup"><span data-stu-id="2086e-138">In some cases, only error log files are available for investigation.</span></span> <span data-ttu-id="2086e-139">Ermitteln Sie in diesen Fällen, ob im Fehlerprotokoll die Fehlermeldung 26023 für den TCP-Port des Endpunkts für die Datenbankspiegelung enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="2086e-139">In these cases, determine whether the error log contains error message 26023 for the TCP port of the database mirroring endpoint.</span></span> <span data-ttu-id="2086e-140">Dieser Fehler mit Schweregrad 16 kann darauf hinweisen, dass der Endpunkt der Datenbankspiegelung nicht gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="2086e-140">This error, which is severity 16, might indicate that the database mirroring endpoint is not started.</span></span> <span data-ttu-id="2086e-141">Diese Meldung kann auch dann ausgegeben werden, wenn **sys.database_mirroring_endpoints** den Status des Endpunkts als STARTED anzeigt.</span><span class="sxs-lookup"><span data-stu-id="2086e-141">This message can occur even if **sys.database_mirroring_endpoints** shows the endpoint state as started.</span></span>  
  
 <span data-ttu-id="2086e-142">Nach dem Beheben möglicher Probleme versuchen Sie erneut, die Anweisung ALTER DATABASE *Datenbank_Name* SET PARTNER auf dem Prinzipalserver auszuführen.</span><span class="sxs-lookup"><span data-stu-id="2086e-142">After resolving any issues that you encounter, rerun the ALTER DATABASE *database_name* SET PARTNER statement on the principal server.</span></span>  
  
### <a name="verifying-port-availability"></a><span data-ttu-id="2086e-143">Überprüfen der Verfügbarkeit von Ports</span><span class="sxs-lookup"><span data-stu-id="2086e-143">Verifying Port Availability</span></span>  
 <span data-ttu-id="2086e-144">Stellen Sie beim Konfigurieren des Netzwerks für eine Datenbankspiegelungssitzung sicher, dass der Endpunkt der Datenbankspiegelung der einzelnen Serverinstanzen nur vom Datenbankspiegelungsprozess verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2086e-144">When you are configuring the network for a database mirroring session, make sure the database mirroring endpoint of each server instance is used by only the database mirroring process.</span></span> <span data-ttu-id="2086e-145">Wenn an dem einem Datenbank-Spiegelungsendpunkt zugeordneten Port von einem anderen Prozess gelauscht wird, können die Datenbankspiegelungsprozesse der anderen Serverinstanzen keine Verbindung mit dem Endpunkt herstellen.</span><span class="sxs-lookup"><span data-stu-id="2086e-145">If another process is listening on the port assigned to a database mirroring endpoint, the database mirroring processes of the other server instances cannot connect to the endpoint.</span></span>  
  
 <span data-ttu-id="2086e-146">Mithilfe des Eingabeaufforderungs-Hilfsprogramms **netstat** können Sie alle Ports anzeigen, die ein Windows-basierten Server überwacht.</span><span class="sxs-lookup"><span data-stu-id="2086e-146">To display all the ports on which a Windows-based server is listening, use the **netstat** command-prompt utility.</span></span> <span data-ttu-id="2086e-147">Die **netstat**-Syntax ist von der Version des Windows-Betriebssystems abhängig.</span><span class="sxs-lookup"><span data-stu-id="2086e-147">The syntax for **netstat** depends on the version of the Windows operating system.</span></span> <span data-ttu-id="2086e-148">Weitere Informationen finden Sie in der Dokumentation zum Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="2086e-148">For more information, see the operating system documentation.</span></span>  
  
#### <a name="windows-server-2003-service-pack-1-sp1"></a><span data-ttu-id="2086e-149">Windows Server 2003 Service Pack 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="2086e-149">Windows Server 2003 Service Pack 1 (SP1)</span></span>  
 <span data-ttu-id="2086e-150">Geben Sie an der Windows-Eingabeaufforderung den folgenden Befehl ein, um eine Liste der Ports, an denen gelauscht wird, sowie der Prozesse anzuzeigen, die diese Ports geöffnet haben:</span><span class="sxs-lookup"><span data-stu-id="2086e-150">To list listening ports and the processes that have those ports opened, enter the following command at the Windows command prompt:</span></span>  
  
 <span data-ttu-id="2086e-151">**netstat -abn**</span><span class="sxs-lookup"><span data-stu-id="2086e-151">**netstat -abn**</span></span>  
  
#### <a name="windows-server-2003-pre-sp1"></a><span data-ttu-id="2086e-152">Windows Server 2003 (vor SP1)</span><span class="sxs-lookup"><span data-stu-id="2086e-152">Windows Server 2003 (pre-SP1)</span></span>  
 <span data-ttu-id="2086e-153">Gehen Sie zum Identifizieren der Ports, an denen gelauscht wird sowie der Prozesse, die diese Ports geöffnet haben, folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="2086e-153">To identify the listening ports and the processes that have those ports opened, follow these steps:</span></span>  
  
1.  <span data-ttu-id="2086e-154">Rufen Sie die Prozess-ID ab.</span><span class="sxs-lookup"><span data-stu-id="2086e-154">Obtain the process ID.</span></span>  
  
     <span data-ttu-id="2086e-155">Die Prozess-ID einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] können Sie ermitteln, indem Sie eine Verbindung mit der Instanz herstellen und die folgende [!INCLUDE[tsql](../../includes/tsql-md.md)]-Anweisung verwenden:</span><span class="sxs-lookup"><span data-stu-id="2086e-155">To learn the process ID of an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], connect to that instance and use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
    ```  
    SELECT SERVERPROPERTY('ProcessID')   
    ```  
  
     <span data-ttu-id="2086e-156">Weitere Informationen finden Sie unter "SERVERPROPERTY (Transact-SQL)" in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="2086e-156">For more information, see "SERVERPROPERTY (Transact-SQL)" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
2.  <span data-ttu-id="2086e-157">Gleichen Sie die Prozess-ID mit der Ausgabe des folgenden **netstat**-Befehls ab:</span><span class="sxs-lookup"><span data-stu-id="2086e-157">Match the process ID with the output of the following **netstat** command:</span></span>  
  
     <span data-ttu-id="2086e-158">**netstat -ano**</span><span class="sxs-lookup"><span data-stu-id="2086e-158">**netstat -ano**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2086e-159">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2086e-159">See Also</span></span>  
 <span data-ttu-id="2086e-160">[ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2086e-160">[ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql) </span></span>  
 <span data-ttu-id="2086e-161">[Der Datenbankspiegelungs-Endpunkt &#40;SQL Server&#41;](../../database-engine/database-mirroring/the-database-mirroring-endpoint-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2086e-161">[The Database Mirroring Endpoint &#40;SQL Server&#41;](../../database-engine/database-mirroring/the-database-mirroring-endpoint-sql-server.md) </span></span>  
 <span data-ttu-id="2086e-162">[Vorbereiten einer Spiegeldatenbank auf die Spiegelung (SQL Server)](../../database-engine/database-mirroring/prepare-a-mirror-database-for-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2086e-162">[Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/prepare-a-mirror-database-for-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="2086e-163">[SERVERPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/serverproperty-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2086e-163">[SERVERPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/serverproperty-transact-sql) </span></span>  
 <span data-ttu-id="2086e-164">[Angeben einer Servernetzwerkadresse (Datenbankspiegelung)](../../database-engine/database-mirroring/specify-a-server-network-address-database-mirroring.md) </span><span class="sxs-lookup"><span data-stu-id="2086e-164">[Specify a Server Network Address &#40;Database Mirroring&#41;](../../database-engine/database-mirroring/specify-a-server-network-address-database-mirroring.md) </span></span>  
 <span data-ttu-id="2086e-165">[sys.database_mirroring_endpoints (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-database-mirroring-endpoints-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2086e-165">[sys.database_mirroring_endpoints &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-mirroring-endpoints-transact-sql) </span></span>  
 [<span data-ttu-id="2086e-166">Problembehandlung für die Datenbankspiegelungskonfiguration &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2086e-166">Troubleshoot Database Mirroring Configuration &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/troubleshoot-database-mirroring-configuration-sql-server.md)  
  
  
