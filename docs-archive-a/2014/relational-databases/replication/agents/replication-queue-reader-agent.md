---
title: Warteschlangenlese-Agent der Microsoft SQL Server-Replikation | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/29/2018
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- agents [SQL Server replication], Queue Reader Agent
- command prompt [SQL Server replication]
- Queue Reader Agent, parameter reference
- Queue Reader Agent, executables
ms.assetid: 8e227793-11f6-47c6-99dc-ffc282f5d4bf
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 854c425db3fbaa346dab5eb2c41bd58cf03f65c2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609156"
---
# <a name="replication-queue-reader-agent"></a><span data-ttu-id="3b2ab-102">Warteschlangenlese-Agent der Microsoft SQL Server-Replikation</span><span class="sxs-lookup"><span data-stu-id="3b2ab-102">Replication Queue Reader Agent</span></span>
  <span data-ttu-id="3b2ab-103">Der Replikationswarteschlangenlese-Agent ist eine ausführbare Datei, die in einer [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Warteschlange oder einer [!INCLUDE[msCoName](../../../includes/msconame-md.md)]-Nachrichtenwarteschlange gespeicherte Nachrichten liest und diese Nachrichten dann auf den Verleger anwendet.</span><span class="sxs-lookup"><span data-stu-id="3b2ab-103">The Replication Queue Reader Agent is an executable that reads messages stored in a [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] queue or a [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Message Queue and then applies those messages to the Publisher.</span></span> <span data-ttu-id="3b2ab-104">Der Warteschlangenlese-Agent wird bei Momentaufnahme- und Transaktionsveröffentlichungen verwendet, die das verzögerte Update über eine Warteschlange gestatten.</span><span class="sxs-lookup"><span data-stu-id="3b2ab-104">Queue Reader Agent is used with snapshot and transactional publications that allow queued updating.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3b2ab-105">Parameter können in beliebiger Reihenfolge angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="3b2ab-105">Parameters can be specified in any order.</span></span> <span data-ttu-id="3b2ab-106">Wenn keine optionalen Parameter angegeben werden, werden vordefinierte Werte auf Grundlage des Standardagentprofils verwendet.</span><span class="sxs-lookup"><span data-stu-id="3b2ab-106">When optional parameters are not specified, predefined values based on the default agent profile are used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b2ab-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="3b2ab-107">Syntax</span></span>  
  
```  
  
      qrdrsvc [-?]  
[-Continuous]  
[-DefinitionFiledefinition_file]  
[-Distributorserver_name[\instance_name]]  
[-DistributionDBdistribution_database]  
[-DistributorLogindistributor_login]  
[-DistributorPassworddistributor_password]  
[-DistributorSecurityMode [0|1]]  
[-EncryptionLevel [0|1|2]]  
[-HistoryVerboseLevel [0|1|2|3]]  
[-LoginTimeOutlogin_time_out_seconds]  
[-Outputoutput_path_and_file_name]  
[-OutputVerboseLevel [0|1|2]]  
[-PollingIntervalpolling_interval]  
[-PublisherFailoverPartnerserver_name[\instance_name] ]  
[-ProfileNameagent_profile_name]  
[-QueryTimeOutquery_time_out_seconds]  
[-ResolverState [1|2|3]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="3b2ab-108">Argumente</span><span class="sxs-lookup"><span data-stu-id="3b2ab-108">Arguments</span></span>  
 <span data-ttu-id="3b2ab-109">**-?**</span><span class="sxs-lookup"><span data-stu-id="3b2ab-109">**-?**</span></span>  
 <span data-ttu-id="3b2ab-110">Zeigt Informationen zur Nutzung an.</span><span class="sxs-lookup"><span data-stu-id="3b2ab-110">Displays usage information.</span></span>  
  
 <span data-ttu-id="3b2ab-111">**-Continuous**</span><span class="sxs-lookup"><span data-stu-id="3b2ab-111">**-Continuous**</span></span>  
 <span data-ttu-id="3b2ab-112">Gibt an, ob der Agent fortlaufend versucht, Transaktionen in der Warteschlange zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="3b2ab-112">Specifies whether the agent attempts to process queued transactions continuously.</span></span> <span data-ttu-id="3b2ab-113">Wenn dieses Argument angegeben ist, setzt der Agent die Ausführung auch dann fort, wenn in der Warteschlange keine ausstehenden Transaktionen von einem der Abonnenten vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="3b2ab-113">If specified, the agent continues execution even if there are no queued transactions pending from any of the subscribers.</span></span>  
  
 <span data-ttu-id="3b2ab-114">**-DefinitionFile** _def_path_and_file_name_</span><span class="sxs-lookup"><span data-stu-id="3b2ab-114">**-DefinitionFile** _def_path_and_file_name_</span></span>  
 <span data-ttu-id="3b2ab-115">Der Pfad der Agentdefinitionsdatei.</span><span class="sxs-lookup"><span data-stu-id="3b2ab-115">Is the path of the agent definition file.</span></span> <span data-ttu-id="3b2ab-116">Eine Agentdefinitionsdatei enthält Befehlszeilenargumente für den Agent.</span><span class="sxs-lookup"><span data-stu-id="3b2ab-116">An agent definition file contains command-line arguments for the agent.</span></span> <span data-ttu-id="3b2ab-117">Der Inhalt der Datei wird als ausführbare Datei analysiert.</span><span class="sxs-lookup"><span data-stu-id="3b2ab-117">The content of the file is parsed as an executable file.</span></span> <span data-ttu-id="3b2ab-118">Verwenden Sie doppelte Anführungszeichen ("), um Argumentwerte anzugeben, die beliebige Zeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="3b2ab-118">Use double quotation marks (") to specify argument values containing arbitrary characters.</span></span>  
  
 <span data-ttu-id="3b2ab-119">**-Distributor** _server_name_[ **\\** _instance_name_]</span><span class="sxs-lookup"><span data-stu-id="3b2ab-119">**-Distributor** _server_name_[**\\**_instance_name_]</span></span>  
 <span data-ttu-id="3b2ab-120">Der Name des Verteilers.</span><span class="sxs-lookup"><span data-stu-id="3b2ab-120">Is the Distributor name.</span></span> <span data-ttu-id="3b2ab-121">Geben Sie *server_name* für die Standardinstanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] auf diesem Server an.</span><span class="sxs-lookup"><span data-stu-id="3b2ab-121">Specify *server_name* for the default instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] on that server.</span></span> <span data-ttu-id="3b2ab-122">Geben Sie *server_name*\\*instance_name* für eine benannte Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] auf diesem Server an.</span><span class="sxs-lookup"><span data-stu-id="3b2ab-122">Specify *server_name*\\*instance_name* for a named instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] on that server.</span></span> <span data-ttu-id="3b2ab-123">Wenn kein Name angegeben wird, wird als Standardwert der Name der Standardinstanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] auf dem lokalen Computer verwendet.</span><span class="sxs-lookup"><span data-stu-id="3b2ab-123">If not specified, the name defaults to the name of the default instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] on the local computer.</span></span>  
  
 <span data-ttu-id="3b2ab-124">**-DistributionDB** _distribution_database_</span><span class="sxs-lookup"><span data-stu-id="3b2ab-124">**-DistributionDB** _distribution_database_</span></span>  
 <span data-ttu-id="3b2ab-125">Die Verteilungsdatenbank.</span><span class="sxs-lookup"><span data-stu-id="3b2ab-125">Is the distribution database.</span></span>  
  
 <span data-ttu-id="3b2ab-126">**-DistributorLogin** _distributor_login_</span><span class="sxs-lookup"><span data-stu-id="3b2ab-126">**-DistributorLogin** _distributor_login_</span></span>  
 <span data-ttu-id="3b2ab-127">Der Anmeldename des Verteilers.</span><span class="sxs-lookup"><span data-stu-id="3b2ab-127">Is the Distributor login name.</span></span>  
  
 <span data-ttu-id="3b2ab-128">**-DistributorPassword** _distributor_password_</span><span class="sxs-lookup"><span data-stu-id="3b2ab-128">**-DistributorPassword** _distributor_password_</span></span>  
 <span data-ttu-id="3b2ab-129">Das Verteilerkennwort.</span><span class="sxs-lookup"><span data-stu-id="3b2ab-129">Is the Distributor password.</span></span>  
  
 <span data-ttu-id="3b2ab-130">**-DistributorSecurityMode** [ **0**| **1**]</span><span class="sxs-lookup"><span data-stu-id="3b2ab-130">**-DistributorSecurityMode** [ **0**| **1**]</span></span>  
 <span data-ttu-id="3b2ab-131">Gibt den Sicherheitsmodus des Verteilers an.</span><span class="sxs-lookup"><span data-stu-id="3b2ab-131">Specifies the security mode of the Distributor.</span></span> <span data-ttu-id="3b2ab-132">Der Wert **0** steht für den [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Authentifizierungsmodus (Standard), der Wert **1** für den Windows-Authentifizierungsmodus.</span><span class="sxs-lookup"><span data-stu-id="3b2ab-132">A value of **0** indicates [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication Mode (default), and a value of **1** indicates Windows Authentication Mode.</span></span>  
  
 <span data-ttu-id="3b2ab-133">**-EncryptionLevel** [ **0** | **1** | **2** ]</span><span class="sxs-lookup"><span data-stu-id="3b2ab-133">**-EncryptionLevel** [ **0** | **1** | **2** ]</span></span>  
 <span data-ttu-id="3b2ab-134">Die Ebene der SSL-Verschlüsselung (Secure Sockets Layer), die vom Warteschlangenlese-Agent beim Herstellen von Verbindungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3b2ab-134">Is the level of Secure Sockets Layer (SSL) encryption used by the Queue Reader Agent when making connections.</span></span>  
  
|<span data-ttu-id="3b2ab-135">Wert von EncryptionLevel</span><span class="sxs-lookup"><span data-stu-id="3b2ab-135">EncryptionLevel value</span></span>|<span data-ttu-id="3b2ab-136">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3b2ab-136">Description</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="3b2ab-137">**0**</span><span class="sxs-lookup"><span data-stu-id="3b2ab-137">**0**</span></span>|<span data-ttu-id="3b2ab-138">Gibt an, dass SSL nicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3b2ab-138">Specifies that SSL is not used.</span></span>|  
|<span data-ttu-id="3b2ab-139">**1**</span><span class="sxs-lookup"><span data-stu-id="3b2ab-139">**1**</span></span>|<span data-ttu-id="3b2ab-140">Gibt an, dass SSL verwendet wird, der Agent jedoch nicht überprüft, ob das SSL-Serverzertifikat von einem vertrauenswürdigen Aussteller signiert wurde.</span><span class="sxs-lookup"><span data-stu-id="3b2ab-140">Specifies that SSL is used, but the agent does not verify that the SSL server certificate is signed by a trusted issuer.</span></span>|  
|<span data-ttu-id="3b2ab-141">**2**</span><span class="sxs-lookup"><span data-stu-id="3b2ab-141">**2**</span></span>|<span data-ttu-id="3b2ab-142">Gibt an, dass SSL verwendet und das Zertifikat überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="3b2ab-142">Specifies that SSL is used, and that the certificate is verified.</span></span>|  

 > [!NOTE]  
 >  <span data-ttu-id="3b2ab-143">Ein gültiges SSL-Zertifikat wird mit dem vollqualifizierten Domänennamen der SQL Server-Instanz definiert.</span><span class="sxs-lookup"><span data-stu-id="3b2ab-143">A valid SSL certificate is defined with a fully qualified domain name of the SQL Server.</span></span> <span data-ttu-id="3b2ab-144">Damit der Agent die Verbindung erfolgreich herstellen kann, wenn „-EncryptionLevel“ auf 2 festgelegt ist, sollten Sie einen Alias auf der lokalen SQL Server-Instanz erstellen.</span><span class="sxs-lookup"><span data-stu-id="3b2ab-144">In order for the agent to connect successfully when setting -EncryptionLevel to 2, create an alias on the local SQL Server.</span></span> <span data-ttu-id="3b2ab-145">Der Parameter „Alias Name“ sollte den Servernamen enthalten, und für den Parameter „Server“ sollte der vollqualifizierte Name der SQL Server-Instanz festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="3b2ab-145">The 'Alias Name' parameter should be the server name and the 'Server' parameter should be set to the fully qualified name of the SQL Server.</span></span>
  
 <span data-ttu-id="3b2ab-146">Weitere Informationen finden Sie unter [SQL Server-Replikation-Sicherheit](../security/view-and-modify-replication-security-settings.md).</span><span class="sxs-lookup"><span data-stu-id="3b2ab-146">For more information, see [SQL Server Replication Security](../security/view-and-modify-replication-security-settings.md).</span></span>  
  
 <span data-ttu-id="3b2ab-147">**-HistoryVerboseLevel** [ **0**| **1**| **2**| **3**]</span><span class="sxs-lookup"><span data-stu-id="3b2ab-147">**-HistoryVerboseLevel** [ **0**| **1**| **2**| **3**]</span></span>  
 <span data-ttu-id="3b2ab-148">Gibt den Umfang des Verlaufs an, der während eines Vorgangs des Warteschlangenlese-Agents protokolliert wird.</span><span class="sxs-lookup"><span data-stu-id="3b2ab-148">Specifies the amount of history logged during a queue reader operation.</span></span> <span data-ttu-id="3b2ab-149">Sie können die negativen Auswirkungen der Verlaufsprotokollierung auf die Leistung minimieren, indem Sie den Wert **1**auswählen.</span><span class="sxs-lookup"><span data-stu-id="3b2ab-149">You can minimize the effect of history logging on performance by selecting **1**.</span></span>  
  
|<span data-ttu-id="3b2ab-150">Wert von <legacyBold>HistoryVerboseLevel</legacyBold></span><span class="sxs-lookup"><span data-stu-id="3b2ab-150">HistoryVerboseLevel value</span></span>|<span data-ttu-id="3b2ab-151">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3b2ab-151">Description</span></span>|  
|-------------------------------|-----------------|  
|<span data-ttu-id="3b2ab-152">**0**</span><span class="sxs-lookup"><span data-stu-id="3b2ab-152">**0**</span></span>|<span data-ttu-id="3b2ab-153">Keine Verlaufsprotokollierung (nicht empfohlen).</span><span class="sxs-lookup"><span data-stu-id="3b2ab-153">No history logging (not recommended).</span></span>|  
|<span data-ttu-id="3b2ab-154">**1**</span><span class="sxs-lookup"><span data-stu-id="3b2ab-154">**1**</span></span>|<span data-ttu-id="3b2ab-155">Standard.</span><span class="sxs-lookup"><span data-stu-id="3b2ab-155">Default.</span></span> <span data-ttu-id="3b2ab-156">Aktualisieren Sie immer eine vorherige Verlaufsmeldung mit dem gleichen Status (Start, Status, Erfolg usw.).</span><span class="sxs-lookup"><span data-stu-id="3b2ab-156">Always update a previous history message of the same status (startup, progress, success, and so on).</span></span> <span data-ttu-id="3b2ab-157">Wenn kein vorheriger Datensatz mit dem gleichen Status vorhanden ist, fügen Sie einen neuen Datensatz ein.</span><span class="sxs-lookup"><span data-stu-id="3b2ab-157">If no previous record with the same status exists, insert a new record.</span></span>|  
|<span data-ttu-id="3b2ab-158">**2**</span><span class="sxs-lookup"><span data-stu-id="3b2ab-158">**2**</span></span>|<span data-ttu-id="3b2ab-159">Fügen Sie neue Verlaufsdatensätze ein, einschließlich Leerlaufmeldungen oder Meldungen zu Aufträgen mit langer Ausführungszeit.</span><span class="sxs-lookup"><span data-stu-id="3b2ab-159">Insert new history records, including idle messages or long-running job messages.</span></span>|  
|<span data-ttu-id="3b2ab-160">**3**</span><span class="sxs-lookup"><span data-stu-id="3b2ab-160">**3**</span></span>|<span data-ttu-id="3b2ab-161">Fügen Sie neue Verlaufsdatensätze ein, die weitere Details enthalten, die möglicherweise für die Problembehandlung nützlich sind.</span><span class="sxs-lookup"><span data-stu-id="3b2ab-161">Insert new history records that include additional details that may be useful for troubleshooting.</span></span>|  
  
 <span data-ttu-id="3b2ab-162">**-LoginTimeOut** _login_time_out_seconds_</span><span class="sxs-lookup"><span data-stu-id="3b2ab-162">**-LoginTimeOut** _login_time_out_seconds_</span></span>  
 <span data-ttu-id="3b2ab-163">Die Anzahl von Sekunden, nach denen ein Timeout bei der Anmeldung eintritt. Der Standardwert ist 15 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="3b2ab-163">Is the number of seconds before the login times out. The default is 15 seconds.</span></span>  
  
 <span data-ttu-id="3b2ab-164">**-Output** _output_path_and_file_name_</span><span class="sxs-lookup"><span data-stu-id="3b2ab-164">**-Output** _output_path_and_file_name_</span></span>  
 <span data-ttu-id="3b2ab-165">Der Pfad der Agentausgabedatei.</span><span class="sxs-lookup"><span data-stu-id="3b2ab-165">Is the path of the agent output file.</span></span> <span data-ttu-id="3b2ab-166">Wenn kein Dateiname angegeben ist, wird die Ausgabe an die Konsole gesendet.</span><span class="sxs-lookup"><span data-stu-id="3b2ab-166">If the file name is not provided, the output is sent to the console.</span></span> <span data-ttu-id="3b2ab-167">Wenn eine Datei mit dem angegebenen Namen vorhanden ist, wird die Ausgabe an diese Datei angefügt.</span><span class="sxs-lookup"><span data-stu-id="3b2ab-167">If the specified file name exists, the output is appended to the file.</span></span>  
  
 <span data-ttu-id="3b2ab-168">**-OutputVerboseLevel** [ **0**| **1**| **2**]</span><span class="sxs-lookup"><span data-stu-id="3b2ab-168">**-OutputVerboseLevel** [ **0**| **1**| **2**]</span></span>  
 <span data-ttu-id="3b2ab-169">Gibt an, ob die Ausgabe ausführlich sein soll.</span><span class="sxs-lookup"><span data-stu-id="3b2ab-169">Specifies whether the output should be verbose.</span></span> <span data-ttu-id="3b2ab-170">Wenn die Meldungsstufe **0**beträgt, werden nur Fehlermeldungen gedruckt.</span><span class="sxs-lookup"><span data-stu-id="3b2ab-170">If the verbose level is **0**, only error messages are printed.</span></span> <span data-ttu-id="3b2ab-171">Wenn die Meldungsstufe **1**beträgt, werden alle Statusberichtsmeldungen gedruckt.</span><span class="sxs-lookup"><span data-stu-id="3b2ab-171">If the verbose level is **1**, all the progress report messages are printed.</span></span> <span data-ttu-id="3b2ab-172">Wenn die Meldungsstufe **2** (Standard) beträgt, werden alle Fehlermeldungen und Statusberichtsmeldungen gedruckt, was beim Debuggen nützlich ist.</span><span class="sxs-lookup"><span data-stu-id="3b2ab-172">If the verbose level is **2** (default), all error messages and progress report messages are printed, which is useful for debugging.</span></span>  
  
 <span data-ttu-id="3b2ab-173">**-PollingInterval** _polling_interval_</span><span class="sxs-lookup"><span data-stu-id="3b2ab-173">**-PollingInterval** _polling_interval_</span></span>  
 <span data-ttu-id="3b2ab-174">Ist nur relevant, um Abonnements zu aktualisieren, die auf [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] basierende Warteschlangen verwenden.</span><span class="sxs-lookup"><span data-stu-id="3b2ab-174">Is relevant only for updating subscriptions that use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] based queues.</span></span> <span data-ttu-id="3b2ab-175">Gibt an, wie oft die [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Warteschlange nach anstehenden Transaktionen abgefragt wird (in Sekunden).</span><span class="sxs-lookup"><span data-stu-id="3b2ab-175">Specifies how often, in seconds, the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] queue is polled for pending queued transactions.</span></span> <span data-ttu-id="3b2ab-176">Der Wert kann zwischen 0 und 240 Sekunden liegen.</span><span class="sxs-lookup"><span data-stu-id="3b2ab-176">The value can be between 0 and 240 seconds.</span></span> <span data-ttu-id="3b2ab-177">Die Standardeinstellung ist 5 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="3b2ab-177">The default is 5 seconds.</span></span>  
  
 <span data-ttu-id="3b2ab-178">**-PublisherFailoverPartner** _server_name_[ **\\** _instance_name_]</span><span class="sxs-lookup"><span data-stu-id="3b2ab-178">**-PublisherFailoverPartner** _server_name_[**\\**_instance_name_]</span></span>  
 <span data-ttu-id="3b2ab-179">Gibt die Failoverpartnerinstanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] an, die an einer Datenbank-Spiegelungssitzung mit der Veröffentlichungsdatenbank teilnimmt.</span><span class="sxs-lookup"><span data-stu-id="3b2ab-179">Specifies the failover partner instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] participating in a database mirroring session with the publication database.</span></span> <span data-ttu-id="3b2ab-180">Weitere Informationen finden Sie unter [Datenbankspiegelung und Replikation &#40;SQL Server&#41;](../../../database-engine/database-mirroring/database-mirroring-and-replication-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="3b2ab-180">For more information, see [Database Mirroring and Replication &#40;SQL Server&#41;](../../../database-engine/database-mirroring/database-mirroring-and-replication-sql-server.md).</span></span>  
  
 <span data-ttu-id="3b2ab-181">**-ProfileName** _agent_profile_name_</span><span class="sxs-lookup"><span data-stu-id="3b2ab-181">**-ProfileName** _agent_profile_name_</span></span>  
 <span data-ttu-id="3b2ab-182">Der Name eines Agentprofils, das zum Bereitstellen von Standardwerten an den Agent verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3b2ab-182">Is the name of an agent profile used to supply a set of default values to the agent.</span></span> <span data-ttu-id="3b2ab-183">Weitere Informationen finden Sie unter [Replication Agent Profiles](replication-agent-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="3b2ab-183">For information, see [Replication Agent Profiles](replication-agent-profiles.md).</span></span>  
  
 <span data-ttu-id="3b2ab-184">**-QueryTimeOut** _query_time_out_seconds_</span><span class="sxs-lookup"><span data-stu-id="3b2ab-184">**-QueryTimeOut** _query_time_out_seconds_</span></span>  
 <span data-ttu-id="3b2ab-185">Die Anzahl von Sekunden, nach denen ein Timeout bei der Abfrage eintritt. Die Standardeinstellung ist 1800 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="3b2ab-185">Is the number of seconds before the query times out. The default is 1800 seconds.</span></span>  
  
 <span data-ttu-id="3b2ab-186">**-ResolverState** [ **1**| **2**| **3**]</span><span class="sxs-lookup"><span data-stu-id="3b2ab-186">**-ResolverState** [ **1**| **2**| **3**]</span></span>  
 <span data-ttu-id="3b2ab-187">Gibt an, wie Konflikte bei verzögertem Update über eine Warteschlange gelöst werden.</span><span class="sxs-lookup"><span data-stu-id="3b2ab-187">Specifies how queued updating conflicts are resolved.</span></span> <span data-ttu-id="3b2ab-188">Der Wert **1** gibt an, dass der Verleger den Konflikt gewinnt und für die aktuelle Transaktion in der Warteschlage, bei der der Konflikt aufgetreten ist, auf dem Verleger und dem ursprünglichen Updateabonnenten ein Rollback ausgeführt wird. Die Verarbeitung der folgenden Transaktionen in der Warteschlange wird fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="3b2ab-188">A value of **1** indicates the Publisher wins the conflict, and the current conflicting queued transaction will be rolled back on the Publisher and the originating updating Subscriber; the processing of subsequent queued transactions will continue.</span></span> <span data-ttu-id="3b2ab-189">Der Wert **2** gibt an, dass der Abonnent den Konflikt gewinnt und durch die Transaktion in der Warteschlange die Werte auf dem Verleger überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="3b2ab-189">A value of **2** indicates the Subscriber wins the conflict, and the queued transaction will override the values on the Publisher.</span></span> <span data-ttu-id="3b2ab-190">Der Wert **3** gibt an, dass jeder Konflikt zu einer erneuten Initialisierung des Abonnenten führt. Der Verleger gewinnt den Konflikt, die Verarbeitung der folgenden Transaktionen in der Warteschlange wird beendet, und das Abonnement wird erneut initialisiert.</span><span class="sxs-lookup"><span data-stu-id="3b2ab-190">A value of **3** indicates that any conflict will result in Subscriber re-initialization; the Publisher wins the conflict, processing of subsequent queued transactions will be terminated, and the subscription will be reinitialized.</span></span> <span data-ttu-id="3b2ab-191">Die Standardeinstellung für Transaktionsveröffentlichungen lautet **1** , für Momentaufnahmeveröffentlichungen **3** .</span><span class="sxs-lookup"><span data-stu-id="3b2ab-191">The default setting is **1** for transactional publications and **3** for snapshot publications.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3b2ab-192">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="3b2ab-192">Remarks</span></span>  
 <span data-ttu-id="3b2ab-193">Führen Sie zum Starten des Warteschlangenlese-Agents von der Eingabeaufforderung **qrdrsvc.exe** aus.</span><span class="sxs-lookup"><span data-stu-id="3b2ab-193">To start the Queue Reader Agent, execute **qrdrsvc.exe** from the command prompt.</span></span> <span data-ttu-id="3b2ab-194">Informationen hierzu finden Sie im [Abschnitt zu den ausführbaren Dateien von Replikations-Agents](../concepts/replication-agent-executables-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="3b2ab-194">For information, see [Replication Agent Executables](../concepts/replication-agent-executables-concepts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b2ab-195">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3b2ab-195">See Also</span></span>  
 [<span data-ttu-id="3b2ab-196">Replikations-Agent-Verwaltung</span><span class="sxs-lookup"><span data-stu-id="3b2ab-196">Replication Agent Administration</span></span>](replication-agent-administration.md)  
  
  
