---
title: ErrorLog-Ereignisklasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- ErrorLog event class
ms.assetid: b0153a31-5794-410b-8816-d9f1290a5b36
author: stevestein
ms.author: sstein
ms.openlocfilehash: f718c40a990ecd6ef080a4611303db08518ea1b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617003"
---
# <a name="errorlog-event-class"></a><span data-ttu-id="ffd3e-102">ErrorLog-Ereignisklasse</span><span class="sxs-lookup"><span data-stu-id="ffd3e-102">ErrorLog Event Class</span></span>
  <span data-ttu-id="ffd3e-103">Die ErrorLog-Ereignisklasse zeigt an, dass Meldungen im [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Fehlerprotokoll protokolliert wurden.</span><span class="sxs-lookup"><span data-stu-id="ffd3e-103">The ErrorLog event class indicates that messages have been logged in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log.</span></span>  
  
## <a name="errorlog-event-class-data-columns"></a><span data-ttu-id="ffd3e-104">Datenspalten der ErrorLog-Ereignisklasse</span><span class="sxs-lookup"><span data-stu-id="ffd3e-104">ErrorLog Event Class Data Columns</span></span>  
  
|<span data-ttu-id="ffd3e-105">Datenspaltenname</span><span class="sxs-lookup"><span data-stu-id="ffd3e-105">Data column name</span></span>|<span data-ttu-id="ffd3e-106">Datentyp</span><span class="sxs-lookup"><span data-stu-id="ffd3e-106">Data type</span></span>|<span data-ttu-id="ffd3e-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ffd3e-107">Description</span></span>|<span data-ttu-id="ffd3e-108">Column ID</span><span class="sxs-lookup"><span data-stu-id="ffd3e-108">Column ID</span></span>|<span data-ttu-id="ffd3e-109">Filterbar</span><span class="sxs-lookup"><span data-stu-id="ffd3e-109">Filterable</span></span>|  
|----------------------|---------------|-----------------|---------------|----------------|  
|<span data-ttu-id="ffd3e-110">ApplicationName</span><span class="sxs-lookup"><span data-stu-id="ffd3e-110">ApplicationName</span></span>|`nvarchar`|<span data-ttu-id="ffd3e-111">Name der Clientanwendung, die die Verbindung mit einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]hergestellt hat.</span><span class="sxs-lookup"><span data-stu-id="ffd3e-111">Name of the client application that created the connection to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ffd3e-112">Diese Spalte wird mit den Werten aufgefüllt, die von der Anwendung übergeben werden, und nicht mit dem angezeigten Namen des Programms.</span><span class="sxs-lookup"><span data-stu-id="ffd3e-112">This column is populated with the values passed by the application rather than the displayed name of the program.</span></span>|<span data-ttu-id="ffd3e-113">10</span><span class="sxs-lookup"><span data-stu-id="ffd3e-113">10</span></span>|<span data-ttu-id="ffd3e-114">Ja</span><span class="sxs-lookup"><span data-stu-id="ffd3e-114">Yes</span></span>|  
|<span data-ttu-id="ffd3e-115">ClientProcessID</span><span class="sxs-lookup"><span data-stu-id="ffd3e-115">ClientProcessID</span></span>|`int`|<span data-ttu-id="ffd3e-116">Die ID, die der Hostcomputer dem Prozess zuweist, in dem die Clientanwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ffd3e-116">ID assigned by the host computer to the process where the client application is running.</span></span> <span data-ttu-id="ffd3e-117">Diese Datenspalte wird aufgefüllt, wenn der Client die Clientprozess-ID angibt.</span><span class="sxs-lookup"><span data-stu-id="ffd3e-117">This data column is populated if the client provides the client process ID.</span></span>|<span data-ttu-id="ffd3e-118">9</span><span class="sxs-lookup"><span data-stu-id="ffd3e-118">9</span></span>|<span data-ttu-id="ffd3e-119">Ja</span><span class="sxs-lookup"><span data-stu-id="ffd3e-119">Yes</span></span>|  
|<span data-ttu-id="ffd3e-120">DatabaseID</span><span class="sxs-lookup"><span data-stu-id="ffd3e-120">DatabaseID</span></span>|`int`|<span data-ttu-id="ffd3e-121">Die ID der Datenbank, die durch die USE *database* -Anweisung angegeben wurde, bzw. die ID der Standarddatenbank, wenn für eine bestimmte Instanz keine USE *database* -Anweisung ausgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="ffd3e-121">ID of the database specified by the USE *database* statement or the default database if no USE *database* statement has been issued for a given instance.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="ffd3e-122">zeigt den Namen der Datenbank an, wenn die ServerName-Datenspalte in der Ablaufverfolgung aufgezeichnet wird und der Server verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="ffd3e-122">displays the name of the database if the ServerName data column is captured in the trace and the server is available.</span></span> <span data-ttu-id="ffd3e-123">Der Wert für eine Datenbank kann mithilfe der DB_ID-Funktion ermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="ffd3e-123">Determine the value for a database by using the DB_ID function.</span></span>|<span data-ttu-id="ffd3e-124">3</span><span class="sxs-lookup"><span data-stu-id="ffd3e-124">3</span></span>|<span data-ttu-id="ffd3e-125">Ja</span><span class="sxs-lookup"><span data-stu-id="ffd3e-125">Yes</span></span>|  
|<span data-ttu-id="ffd3e-126">DatabaseName</span><span class="sxs-lookup"><span data-stu-id="ffd3e-126">DatabaseName</span></span>|`nvarchar`|<span data-ttu-id="ffd3e-127">Name der Datenbank, in der die Benutzeranweisung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ffd3e-127">Name of the database in which the user statement is running.</span></span>|<span data-ttu-id="ffd3e-128">35</span><span class="sxs-lookup"><span data-stu-id="ffd3e-128">35</span></span>|<span data-ttu-id="ffd3e-129">Ja</span><span class="sxs-lookup"><span data-stu-id="ffd3e-129">Yes</span></span>|  
|<span data-ttu-id="ffd3e-130">Fehler</span><span class="sxs-lookup"><span data-stu-id="ffd3e-130">Error</span></span>|`int`|<span data-ttu-id="ffd3e-131">Fehlernummer eines bestimmten Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="ffd3e-131">Error number of a given event.</span></span> <span data-ttu-id="ffd3e-132">Dies ist häufig die in der sys.messages-Katalogsicht gespeicherte Fehlernummer.</span><span class="sxs-lookup"><span data-stu-id="ffd3e-132">Often this is the error number stored in the sys.messages catalog view.</span></span>|<span data-ttu-id="ffd3e-133">31</span><span class="sxs-lookup"><span data-stu-id="ffd3e-133">31</span></span>|<span data-ttu-id="ffd3e-134">Ja</span><span class="sxs-lookup"><span data-stu-id="ffd3e-134">Yes</span></span>|  
|<span data-ttu-id="ffd3e-135">EventClass</span><span class="sxs-lookup"><span data-stu-id="ffd3e-135">EventClass</span></span>|`int`|<span data-ttu-id="ffd3e-136">Ereignistyp = 22.</span><span class="sxs-lookup"><span data-stu-id="ffd3e-136">Type of event = 22.</span></span>|<span data-ttu-id="ffd3e-137">27</span><span class="sxs-lookup"><span data-stu-id="ffd3e-137">27</span></span>|<span data-ttu-id="ffd3e-138">Nein</span><span class="sxs-lookup"><span data-stu-id="ffd3e-138">No</span></span>|  
|<span data-ttu-id="ffd3e-139">EventSequence</span><span class="sxs-lookup"><span data-stu-id="ffd3e-139">EventSequence</span></span>|`int`|<span data-ttu-id="ffd3e-140">Sequenz eines bestimmten Ereignisses innerhalb der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="ffd3e-140">Sequence of a given event within the request.</span></span>|<span data-ttu-id="ffd3e-141">51</span><span class="sxs-lookup"><span data-stu-id="ffd3e-141">51</span></span>|<span data-ttu-id="ffd3e-142">Nein</span><span class="sxs-lookup"><span data-stu-id="ffd3e-142">No</span></span>|  
|<span data-ttu-id="ffd3e-143">HostName</span><span class="sxs-lookup"><span data-stu-id="ffd3e-143">HostName</span></span>|`nvarchar`|<span data-ttu-id="ffd3e-144">Der Name des Computers, auf dem der Client ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ffd3e-144">Name of the computer on which the client is running.</span></span> <span data-ttu-id="ffd3e-145">Diese Datenspalte wird aufgefüllt, wenn der Hostname vom Client bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="ffd3e-145">This data column is populated if the client provides the host name.</span></span> <span data-ttu-id="ffd3e-146">Der Hostname kann mithilfe der HOST_NAME-Funktion bestimmt werden.</span><span class="sxs-lookup"><span data-stu-id="ffd3e-146">To determine the host name, use the HOST_NAME function.</span></span>|<span data-ttu-id="ffd3e-147">8</span><span class="sxs-lookup"><span data-stu-id="ffd3e-147">8</span></span>|<span data-ttu-id="ffd3e-148">Ja</span><span class="sxs-lookup"><span data-stu-id="ffd3e-148">Yes</span></span>|  
|<span data-ttu-id="ffd3e-149">IsSystem</span><span class="sxs-lookup"><span data-stu-id="ffd3e-149">IsSystem</span></span>|`int`|<span data-ttu-id="ffd3e-150">Gibt an, ob das Ereignis bei einem Systemprozess oder einem Benutzerprozess aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="ffd3e-150">Indicates whether the event occurred on a system process or a user process.</span></span> <span data-ttu-id="ffd3e-151">1 = System, 0 = Benutzer.</span><span class="sxs-lookup"><span data-stu-id="ffd3e-151">1 = system, 0 = user.</span></span>|<span data-ttu-id="ffd3e-152">60</span><span class="sxs-lookup"><span data-stu-id="ffd3e-152">60</span></span>|<span data-ttu-id="ffd3e-153">Ja</span><span class="sxs-lookup"><span data-stu-id="ffd3e-153">Yes</span></span>|  
|<span data-ttu-id="ffd3e-154">LoginName</span><span class="sxs-lookup"><span data-stu-id="ffd3e-154">LoginName</span></span>|`nvarchar`|<span data-ttu-id="ffd3e-155">Der Anmeldename des Benutzers ( [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Sicherheitsanmeldung oder [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows-Anmeldeinformationen im Format DOMAIN\username).</span><span class="sxs-lookup"><span data-stu-id="ffd3e-155">Name of the login of the user (either [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] security login or the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows login credentials in the form of DOMAIN\username).</span></span>|<span data-ttu-id="ffd3e-156">11</span><span class="sxs-lookup"><span data-stu-id="ffd3e-156">11</span></span>|<span data-ttu-id="ffd3e-157">Ja</span><span class="sxs-lookup"><span data-stu-id="ffd3e-157">Yes</span></span>|  
|<span data-ttu-id="ffd3e-158">LoginSid</span><span class="sxs-lookup"><span data-stu-id="ffd3e-158">LoginSid</span></span>|`image`|<span data-ttu-id="ffd3e-159">Sicherheits-ID (SID) des angemeldeten Benutzers.</span><span class="sxs-lookup"><span data-stu-id="ffd3e-159">Security identification number (SID) of the logged-in user.</span></span> <span data-ttu-id="ffd3e-160">Diese Informationen finden Sie in der sys.server_principals-Katalogsicht.</span><span class="sxs-lookup"><span data-stu-id="ffd3e-160">You can find this information in the sys.server_principals catalog view.</span></span> <span data-ttu-id="ffd3e-161">Die SID ist für jede Anmeldung beim Server eindeutig.</span><span class="sxs-lookup"><span data-stu-id="ffd3e-161">Each SID is unique for each login in the server.</span></span>|<span data-ttu-id="ffd3e-162">41</span><span class="sxs-lookup"><span data-stu-id="ffd3e-162">41</span></span>|<span data-ttu-id="ffd3e-163">Ja</span><span class="sxs-lookup"><span data-stu-id="ffd3e-163">Yes</span></span>|  
|<span data-ttu-id="ffd3e-164">NTDomainName</span><span class="sxs-lookup"><span data-stu-id="ffd3e-164">NTDomainName</span></span>|`nvarchar`|<span data-ttu-id="ffd3e-165">Windows-Domäne, zu der der Benutzer gehört.</span><span class="sxs-lookup"><span data-stu-id="ffd3e-165">Windows domain to which the user belongs.</span></span>|<span data-ttu-id="ffd3e-166">7</span><span class="sxs-lookup"><span data-stu-id="ffd3e-166">7</span></span>|<span data-ttu-id="ffd3e-167">Ja</span><span class="sxs-lookup"><span data-stu-id="ffd3e-167">Yes</span></span>|  
|<span data-ttu-id="ffd3e-168">NTUserName</span><span class="sxs-lookup"><span data-stu-id="ffd3e-168">NTUserName</span></span>|`nvarchar`|<span data-ttu-id="ffd3e-169">Windows-Benutzername.</span><span class="sxs-lookup"><span data-stu-id="ffd3e-169">Windows user name.</span></span>|<span data-ttu-id="ffd3e-170">6</span><span class="sxs-lookup"><span data-stu-id="ffd3e-170">6</span></span>|<span data-ttu-id="ffd3e-171">Ja</span><span class="sxs-lookup"><span data-stu-id="ffd3e-171">Yes</span></span>|  
|<span data-ttu-id="ffd3e-172">RequestID</span><span class="sxs-lookup"><span data-stu-id="ffd3e-172">RequestID</span></span>|`int`|<span data-ttu-id="ffd3e-173">Die ID der Anforderung, die die Anweisung enthält.</span><span class="sxs-lookup"><span data-stu-id="ffd3e-173">The ID of the request containing the statement.</span></span>|<span data-ttu-id="ffd3e-174">49</span><span class="sxs-lookup"><span data-stu-id="ffd3e-174">49</span></span>|<span data-ttu-id="ffd3e-175">Ja</span><span class="sxs-lookup"><span data-stu-id="ffd3e-175">Yes</span></span>|  
|<span data-ttu-id="ffd3e-176">ServerName</span><span class="sxs-lookup"><span data-stu-id="ffd3e-176">ServerName</span></span>|`nvarchar`|<span data-ttu-id="ffd3e-177">Name der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz, für die eine Ablaufverfolgung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ffd3e-177">Name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] being traced.</span></span>|<span data-ttu-id="ffd3e-178">26</span><span class="sxs-lookup"><span data-stu-id="ffd3e-178">26</span></span>|<span data-ttu-id="ffd3e-179">Nein</span><span class="sxs-lookup"><span data-stu-id="ffd3e-179">No</span></span>|  
|<span data-ttu-id="ffd3e-180">SessionLoginName</span><span class="sxs-lookup"><span data-stu-id="ffd3e-180">SessionLoginName</span></span>|`nvarchar`|<span data-ttu-id="ffd3e-181">Der Anmeldename des Benutzers, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="ffd3e-181">Login name of the user who originated the session.</span></span> <span data-ttu-id="ffd3e-182">Wenn Sie beispielsweise mithilfe von Login1 eine Verbindung mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] herstellen und eine Anweisung als Login2 ausführen, zeigt SessionLoginName den Wert Login1 an und LoginName den Wert Login2.</span><span class="sxs-lookup"><span data-stu-id="ffd3e-182">For example, if you connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using Login1 and execute a statement as Login2, SessionLoginName shows Login1 and LoginName shows Login2.</span></span> <span data-ttu-id="ffd3e-183">Diese Spalte zeigt sowohl den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] - als auch den Windows-Anmeldenamen an.</span><span class="sxs-lookup"><span data-stu-id="ffd3e-183">This column displays both [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and Windows logins.</span></span>|<span data-ttu-id="ffd3e-184">64</span><span class="sxs-lookup"><span data-stu-id="ffd3e-184">64</span></span>|<span data-ttu-id="ffd3e-185">Ja</span><span class="sxs-lookup"><span data-stu-id="ffd3e-185">Yes</span></span>|  
|<span data-ttu-id="ffd3e-186">severity</span><span class="sxs-lookup"><span data-stu-id="ffd3e-186">Severity</span></span>|`int`|<span data-ttu-id="ffd3e-187">Schweregrad einer Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="ffd3e-187">Severity level of an exception.</span></span>|<span data-ttu-id="ffd3e-188">20</span><span class="sxs-lookup"><span data-stu-id="ffd3e-188">20</span></span>|<span data-ttu-id="ffd3e-189">Ja</span><span class="sxs-lookup"><span data-stu-id="ffd3e-189">Yes</span></span>|  
|<span data-ttu-id="ffd3e-190">SPID</span><span class="sxs-lookup"><span data-stu-id="ffd3e-190">SPID</span></span>|`int`|<span data-ttu-id="ffd3e-191">Die ID der Sitzung, in der das Ereignis aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="ffd3e-191">ID of the session on which the event occurred.</span></span>|<span data-ttu-id="ffd3e-192">12</span><span class="sxs-lookup"><span data-stu-id="ffd3e-192">12</span></span>|<span data-ttu-id="ffd3e-193">Ja</span><span class="sxs-lookup"><span data-stu-id="ffd3e-193">Yes</span></span>|  
|<span data-ttu-id="ffd3e-194">StartTime</span><span class="sxs-lookup"><span data-stu-id="ffd3e-194">StartTime</span></span>|`datetime`|<span data-ttu-id="ffd3e-195">Zeitpunkt, zu dem das Ereignis begonnen hat (falls vorhanden).</span><span class="sxs-lookup"><span data-stu-id="ffd3e-195">Time at which the event started, if available.</span></span>|<span data-ttu-id="ffd3e-196">14</span><span class="sxs-lookup"><span data-stu-id="ffd3e-196">14</span></span>|<span data-ttu-id="ffd3e-197">Ja</span><span class="sxs-lookup"><span data-stu-id="ffd3e-197">Yes</span></span>|  
|<span data-ttu-id="ffd3e-198">TextData</span><span class="sxs-lookup"><span data-stu-id="ffd3e-198">TextData</span></span>|`ntext`|<span data-ttu-id="ffd3e-199">Text der Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="ffd3e-199">Text of the error message.</span></span>|<span data-ttu-id="ffd3e-200">1</span><span class="sxs-lookup"><span data-stu-id="ffd3e-200">1</span></span>|<span data-ttu-id="ffd3e-201">Ja</span><span class="sxs-lookup"><span data-stu-id="ffd3e-201">Yes</span></span>|  
|<span data-ttu-id="ffd3e-202">TransactionID</span><span class="sxs-lookup"><span data-stu-id="ffd3e-202">TransactionID</span></span>|`bigint`|<span data-ttu-id="ffd3e-203">Die vom System zugewiesene ID der Transaktion.</span><span class="sxs-lookup"><span data-stu-id="ffd3e-203">System-assigned ID of the transaction.</span></span>|<span data-ttu-id="ffd3e-204">4</span><span class="sxs-lookup"><span data-stu-id="ffd3e-204">4</span></span>|<span data-ttu-id="ffd3e-205">Ja</span><span class="sxs-lookup"><span data-stu-id="ffd3e-205">Yes</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ffd3e-206">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ffd3e-206">See Also</span></span>  
 <span data-ttu-id="ffd3e-207">[Erweiterte Ereignisse](../extended-events/extended-events.md) </span><span class="sxs-lookup"><span data-stu-id="ffd3e-207">[Extended Events](../extended-events/extended-events.md) </span></span>  
 [<span data-ttu-id="ffd3e-208">sp_trace_setevent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ffd3e-208">sp_trace_setevent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)  
  
  