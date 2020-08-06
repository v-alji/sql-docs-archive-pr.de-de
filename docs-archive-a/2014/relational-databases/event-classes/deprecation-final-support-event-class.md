---
title: Deprecation Final Support (Ereignisklasse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- Deprecation Final Support event class
- deprecation [SQL Server], events final support
ms.assetid: 2b4d88d0-62be-45c0-bea8-c5900d553d31
author: stevestein
ms.author: sstein
ms.openlocfilehash: 09910ec1da0b6d157a3a0a53953f2650a924c314
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701120"
---
# <a name="deprecation-final-support-event-class"></a><span data-ttu-id="1735e-102">Deprecation Final Support (Ereignisklasse)</span><span class="sxs-lookup"><span data-stu-id="1735e-102">Deprecation Final Support Event Class</span></span>
  <span data-ttu-id="1735e-103">Die **Deprecation Final Support** -Ereignisklasse tritt auf, wenn Sie eine Funktion verwenden, die aus der nächsten Hauptversion von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="1735e-103">The **Deprecation Final Support** event class occurs when you use a feature that will be removed from the next major release of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="1735e-104">Damit Ihre Anwendungen möglichst langlebig sind, sollten Sie keine Funktionen verwenden, die die **Deprecation Announcement** -Ereignisklasse oder die **Deprecation Final Support** -Ereignisklasse auslösen.</span><span class="sxs-lookup"><span data-stu-id="1735e-104">For greatest longevity of your applications, do not use features that cause the **Deprecation Final Support** event class or the **Deprecation Announcement** event class.</span></span> <span data-ttu-id="1735e-105">Ändern Sie Anwendungen mit veralteten Funktionen so bald wie möglich.</span><span class="sxs-lookup"><span data-stu-id="1735e-105">Modify applications that use final deprecation features as soon as possible.</span></span>  
  
## <a name="deprecation-final-support-event-class-data-columns"></a><span data-ttu-id="1735e-106">Deprecation Final Support-Ereignisklasse (Datenspalten)</span><span class="sxs-lookup"><span data-stu-id="1735e-106">Deprecation Final Support Event Class Data Columns</span></span>  
  
|<span data-ttu-id="1735e-107">Datenspaltenname</span><span class="sxs-lookup"><span data-stu-id="1735e-107">Data column name</span></span>|<span data-ttu-id="1735e-108">Datentyp</span><span class="sxs-lookup"><span data-stu-id="1735e-108">Data type</span></span>|<span data-ttu-id="1735e-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1735e-109">Description</span></span>|<span data-ttu-id="1735e-110">Column ID</span><span class="sxs-lookup"><span data-stu-id="1735e-110">Column ID</span></span>|<span data-ttu-id="1735e-111">Filterbar</span><span class="sxs-lookup"><span data-stu-id="1735e-111">Filterable</span></span>|  
|----------------------|---------------|-----------------|---------------|----------------|  
|<span data-ttu-id="1735e-112">ApplicationName</span><span class="sxs-lookup"><span data-stu-id="1735e-112">ApplicationName</span></span>|`nvarchar`|<span data-ttu-id="1735e-113">Name der Clientanwendung, die die Verbindung mit einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]hergestellt hat.</span><span class="sxs-lookup"><span data-stu-id="1735e-113">Name of the client application that created the connection to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="1735e-114">Diese Spalte wird mit den Werten aufgefüllt, die von der Anwendung übergeben werden, und nicht mit dem angezeigten Namen des Programms.</span><span class="sxs-lookup"><span data-stu-id="1735e-114">This column is populated with the values passed by the application rather than the displayed name of the program.</span></span>|<span data-ttu-id="1735e-115">10</span><span class="sxs-lookup"><span data-stu-id="1735e-115">10</span></span>|<span data-ttu-id="1735e-116">Ja</span><span class="sxs-lookup"><span data-stu-id="1735e-116">Yes</span></span>|  
|<span data-ttu-id="1735e-117">ClientProcessID</span><span class="sxs-lookup"><span data-stu-id="1735e-117">ClientProcessID</span></span>|`int`|<span data-ttu-id="1735e-118">Die ID, die der Hostcomputer dem Prozess zuweist, in dem die Clientanwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1735e-118">ID assigned by the host computer to the process where the client application is running.</span></span> <span data-ttu-id="1735e-119">Diese Datenspalte wird aufgefüllt, wenn der Client die Clientprozess-ID angibt.</span><span class="sxs-lookup"><span data-stu-id="1735e-119">This data column is populated if the client provides the client process ID.</span></span>|<span data-ttu-id="1735e-120">9</span><span class="sxs-lookup"><span data-stu-id="1735e-120">9</span></span>|<span data-ttu-id="1735e-121">Ja</span><span class="sxs-lookup"><span data-stu-id="1735e-121">Yes</span></span>|  
|<span data-ttu-id="1735e-122">DatabaseID</span><span class="sxs-lookup"><span data-stu-id="1735e-122">DatabaseID</span></span>|`int`|<span data-ttu-id="1735e-123">Die ID der Datenbank, die durch die USE *database* -Anweisung angegeben wurde, bzw. die ID der Standarddatenbank, wenn für eine bestimmte Instanz keine USE *database* -Anweisung ausgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="1735e-123">ID of the database specified by the USE *database* statement or the default database if no USE *database* statement has been issued for a given instance.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="1735e-124">zeigt den Namen der Datenbank an, wenn die `ServerName`-Datenspalte in der Ablaufverfolgung erfasst wird und der Server verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="1735e-124">displays the name of the database if the `ServerName` data column is captured in the trace and the server is available.</span></span> <span data-ttu-id="1735e-125">Der Wert für eine Datenbank kann mithilfe der DB_ID-Funktion ermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="1735e-125">Determine the value for a database by using the DB_ID function.</span></span>|<span data-ttu-id="1735e-126">3</span><span class="sxs-lookup"><span data-stu-id="1735e-126">3</span></span>|<span data-ttu-id="1735e-127">Ja</span><span class="sxs-lookup"><span data-stu-id="1735e-127">Yes</span></span>|  
|<span data-ttu-id="1735e-128">DatabaseName</span><span class="sxs-lookup"><span data-stu-id="1735e-128">DatabaseName</span></span>|`nvarchar`|<span data-ttu-id="1735e-129">Name der Datenbank, in der die Benutzeranweisung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1735e-129">Name of the database in which the user statement is running.</span></span>|<span data-ttu-id="1735e-130">35</span><span class="sxs-lookup"><span data-stu-id="1735e-130">35</span></span>|<span data-ttu-id="1735e-131">Ja</span><span class="sxs-lookup"><span data-stu-id="1735e-131">Yes</span></span>|  
|<span data-ttu-id="1735e-132">EventClass</span><span class="sxs-lookup"><span data-stu-id="1735e-132">EventClass</span></span>|`int`|<span data-ttu-id="1735e-133">Ereignistyp = 126.</span><span class="sxs-lookup"><span data-stu-id="1735e-133">Type of event = 126.</span></span>|<span data-ttu-id="1735e-134">27</span><span class="sxs-lookup"><span data-stu-id="1735e-134">27</span></span>|<span data-ttu-id="1735e-135">Nein</span><span class="sxs-lookup"><span data-stu-id="1735e-135">No</span></span>|  
|<span data-ttu-id="1735e-136">EventSequence</span><span class="sxs-lookup"><span data-stu-id="1735e-136">EventSequence</span></span>|`int`|<span data-ttu-id="1735e-137">Sequenz eines bestimmten Ereignisses innerhalb der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="1735e-137">Sequence of a given event within the request.</span></span>|<span data-ttu-id="1735e-138">51</span><span class="sxs-lookup"><span data-stu-id="1735e-138">51</span></span>|<span data-ttu-id="1735e-139">Nein</span><span class="sxs-lookup"><span data-stu-id="1735e-139">No</span></span>|  
|<span data-ttu-id="1735e-140">HostName</span><span class="sxs-lookup"><span data-stu-id="1735e-140">HostName</span></span>|`nvarchar`|<span data-ttu-id="1735e-141">Der Name des Computers, auf dem der Client ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1735e-141">Name of the computer on which the client is running.</span></span> <span data-ttu-id="1735e-142">Diese Datenspalte wird aufgefüllt, wenn der Hostname vom Client bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="1735e-142">This data column is populated if the client provides the host name.</span></span> <span data-ttu-id="1735e-143">Der Hostname kann mithilfe der HOST_NAME-Funktion bestimmt werden.</span><span class="sxs-lookup"><span data-stu-id="1735e-143">To determine the host name, use the HOST_NAME function.</span></span>|<span data-ttu-id="1735e-144">8</span><span class="sxs-lookup"><span data-stu-id="1735e-144">8</span></span>|<span data-ttu-id="1735e-145">Ja</span><span class="sxs-lookup"><span data-stu-id="1735e-145">Yes</span></span>|  
|<span data-ttu-id="1735e-146">IntegerData2</span><span class="sxs-lookup"><span data-stu-id="1735e-146">IntegerData2</span></span>|`int`|<span data-ttu-id="1735e-147">Endoffset (in Bytes) der Anweisung, die gerade ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1735e-147">End offset (in bytes) of the statement that is being executed.</span></span>|<span data-ttu-id="1735e-148">55</span><span class="sxs-lookup"><span data-stu-id="1735e-148">55</span></span>|<span data-ttu-id="1735e-149">Ja</span><span class="sxs-lookup"><span data-stu-id="1735e-149">Yes</span></span>|  
|<span data-ttu-id="1735e-150">IsSystem</span><span class="sxs-lookup"><span data-stu-id="1735e-150">IsSystem</span></span>|`int`|<span data-ttu-id="1735e-151">Gibt an, ob das Ereignis bei einem Systemprozess oder einem Benutzerprozess aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="1735e-151">Indicates whether the event occurred on a system process or a user process.</span></span> <span data-ttu-id="1735e-152">1 = System, 0 = Benutzer.</span><span class="sxs-lookup"><span data-stu-id="1735e-152">1 = system, 0 = user.</span></span>|<span data-ttu-id="1735e-153">60</span><span class="sxs-lookup"><span data-stu-id="1735e-153">60</span></span>|<span data-ttu-id="1735e-154">Ja</span><span class="sxs-lookup"><span data-stu-id="1735e-154">Yes</span></span>|  
|<span data-ttu-id="1735e-155">LoginName</span><span class="sxs-lookup"><span data-stu-id="1735e-155">LoginName</span></span>|`nvarchar`|<span data-ttu-id="1735e-156">Der Anmeldename des Benutzers ( [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Sicherheitsanmeldung oder [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows-Anmeldeinformationen im Format DOMAIN\username).</span><span class="sxs-lookup"><span data-stu-id="1735e-156">Name of the login of the user (either [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] security login or the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows login credentials in the form of DOMAIN\username).</span></span>|<span data-ttu-id="1735e-157">11</span><span class="sxs-lookup"><span data-stu-id="1735e-157">11</span></span>|<span data-ttu-id="1735e-158">Ja</span><span class="sxs-lookup"><span data-stu-id="1735e-158">Yes</span></span>|  
|<span data-ttu-id="1735e-159">LoginSid</span><span class="sxs-lookup"><span data-stu-id="1735e-159">LoginSid</span></span>|`image`|<span data-ttu-id="1735e-160">Sicherheits-ID (SID) des angemeldeten Benutzers.</span><span class="sxs-lookup"><span data-stu-id="1735e-160">Security identification number (SID) of the logged-in user.</span></span> <span data-ttu-id="1735e-161">Diese Informationen finden Sie in der **sys.server_principals** -Katalogsicht.</span><span class="sxs-lookup"><span data-stu-id="1735e-161">You can find this information in the **sys.server_principals** catalog view.</span></span> <span data-ttu-id="1735e-162">Die SID ist für jede Anmeldung beim Server eindeutig.</span><span class="sxs-lookup"><span data-stu-id="1735e-162">Each SID is unique for each login in the server.</span></span>|<span data-ttu-id="1735e-163">41</span><span class="sxs-lookup"><span data-stu-id="1735e-163">41</span></span>|<span data-ttu-id="1735e-164">Ja</span><span class="sxs-lookup"><span data-stu-id="1735e-164">Yes</span></span>|  
|<span data-ttu-id="1735e-165">NTDomainName</span><span class="sxs-lookup"><span data-stu-id="1735e-165">NTDomainName</span></span>|`nvarchar`|<span data-ttu-id="1735e-166">Windows-Domäne, zu der der Benutzer gehört.</span><span class="sxs-lookup"><span data-stu-id="1735e-166">Windows domain to which the user belongs.</span></span>|<span data-ttu-id="1735e-167">7</span><span class="sxs-lookup"><span data-stu-id="1735e-167">7</span></span>|<span data-ttu-id="1735e-168">Ja</span><span class="sxs-lookup"><span data-stu-id="1735e-168">Yes</span></span>|  
|<span data-ttu-id="1735e-169">NTUserName</span><span class="sxs-lookup"><span data-stu-id="1735e-169">NTUserName</span></span>|`nvarchar`|<span data-ttu-id="1735e-170">Windows-Benutzername.</span><span class="sxs-lookup"><span data-stu-id="1735e-170">Windows user name.</span></span>|<span data-ttu-id="1735e-171">6</span><span class="sxs-lookup"><span data-stu-id="1735e-171">6</span></span>|<span data-ttu-id="1735e-172">Ja</span><span class="sxs-lookup"><span data-stu-id="1735e-172">Yes</span></span>|  
|<span data-ttu-id="1735e-173">Offset</span><span class="sxs-lookup"><span data-stu-id="1735e-173">Offset</span></span>|`int`|<span data-ttu-id="1735e-174">Der Startoffset der Anweisung in der gespeicherten Prozedur oder im Batch.</span><span class="sxs-lookup"><span data-stu-id="1735e-174">Starting offset of the statement within the stored procedure or batch.</span></span>|<span data-ttu-id="1735e-175">61</span><span class="sxs-lookup"><span data-stu-id="1735e-175">61</span></span>|<span data-ttu-id="1735e-176">Ja</span><span class="sxs-lookup"><span data-stu-id="1735e-176">Yes</span></span>|  
|<span data-ttu-id="1735e-177">ObjectID</span><span class="sxs-lookup"><span data-stu-id="1735e-177">ObjectID</span></span>|`int`|<span data-ttu-id="1735e-178">Die ID der veralteten Funktion.</span><span class="sxs-lookup"><span data-stu-id="1735e-178">ID number of the deprecated feature.</span></span>|<span data-ttu-id="1735e-179">22</span><span class="sxs-lookup"><span data-stu-id="1735e-179">22</span></span>|<span data-ttu-id="1735e-180">Ja</span><span class="sxs-lookup"><span data-stu-id="1735e-180">Yes</span></span>|  
|<span data-ttu-id="1735e-181">ObjectName</span><span class="sxs-lookup"><span data-stu-id="1735e-181">ObjectName</span></span>|`nvarchar`|<span data-ttu-id="1735e-182">Der Name der veralteten Funktion.</span><span class="sxs-lookup"><span data-stu-id="1735e-182">Name of the deprecated feature.</span></span>|<span data-ttu-id="1735e-183">34</span><span class="sxs-lookup"><span data-stu-id="1735e-183">34</span></span>|<span data-ttu-id="1735e-184">Ja</span><span class="sxs-lookup"><span data-stu-id="1735e-184">Yes</span></span>|  
|<span data-ttu-id="1735e-185">RequestID</span><span class="sxs-lookup"><span data-stu-id="1735e-185">RequestID</span></span>|`int`|<span data-ttu-id="1735e-186">Die ID der Anforderung, die die Anweisung enthält.</span><span class="sxs-lookup"><span data-stu-id="1735e-186">ID of the request containing the statement.</span></span>|<span data-ttu-id="1735e-187">49</span><span class="sxs-lookup"><span data-stu-id="1735e-187">49</span></span>|<span data-ttu-id="1735e-188">Ja</span><span class="sxs-lookup"><span data-stu-id="1735e-188">Yes</span></span>|  
|<span data-ttu-id="1735e-189">ServerName</span><span class="sxs-lookup"><span data-stu-id="1735e-189">ServerName</span></span>|`nvarchar`|<span data-ttu-id="1735e-190">Name der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz, für die eine Ablaufverfolgung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1735e-190">Name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] being traced.</span></span>|<span data-ttu-id="1735e-191">26</span><span class="sxs-lookup"><span data-stu-id="1735e-191">26</span></span>|<span data-ttu-id="1735e-192">Nein</span><span class="sxs-lookup"><span data-stu-id="1735e-192">No</span></span>|  
|<span data-ttu-id="1735e-193">SessionLoginName</span><span class="sxs-lookup"><span data-stu-id="1735e-193">SessionLoginName</span></span>|`nvarchar`|<span data-ttu-id="1735e-194">Anmeldename des Benutzers, der die Sitzung geöffnet hat.</span><span class="sxs-lookup"><span data-stu-id="1735e-194">The login name of the user who originated the session.</span></span> <span data-ttu-id="1735e-195">Wenn Sie z. B. eine Verbindung mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mithilfe von Login1 herstellen und eine Anweisung mithilfe von Login2 ausführen, zeigt `SessionLoginName` Login1 an, und `LoginName` zeigt Login2 an.</span><span class="sxs-lookup"><span data-stu-id="1735e-195">For example, if you connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using Login1 and execute a statement as Login2, `SessionLoginName` shows Login1 and `LoginName` shows Login2.</span></span> <span data-ttu-id="1735e-196">In dieser Spalte werden sowohl der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] - als auch der Windows-Anmeldename angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1735e-196">This column will display both [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and Windows logins.</span></span>|<span data-ttu-id="1735e-197">64</span><span class="sxs-lookup"><span data-stu-id="1735e-197">64</span></span>|<span data-ttu-id="1735e-198">Ja</span><span class="sxs-lookup"><span data-stu-id="1735e-198">Yes</span></span>|  
|<span data-ttu-id="1735e-199">SPID</span><span class="sxs-lookup"><span data-stu-id="1735e-199">SPID</span></span>|`int`|<span data-ttu-id="1735e-200">Die ID der Sitzung, in der das Ereignis aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="1735e-200">ID of the session on which the event occurred.</span></span>|<span data-ttu-id="1735e-201">12</span><span class="sxs-lookup"><span data-stu-id="1735e-201">12</span></span>|<span data-ttu-id="1735e-202">Ja</span><span class="sxs-lookup"><span data-stu-id="1735e-202">Yes</span></span>|  
|<span data-ttu-id="1735e-203">SqlHandle</span><span class="sxs-lookup"><span data-stu-id="1735e-203">SqlHandle</span></span>|`image`|<span data-ttu-id="1735e-204">Binäres Handle, mit dem SQL-Batches oder gespeicherte Prozeduren identifiziert werden können.</span><span class="sxs-lookup"><span data-stu-id="1735e-204">Binary handle that can be used to identify SQL batches or stored procedures.</span></span>|<span data-ttu-id="1735e-205">63</span><span class="sxs-lookup"><span data-stu-id="1735e-205">63</span></span>|<span data-ttu-id="1735e-206">Ja</span><span class="sxs-lookup"><span data-stu-id="1735e-206">Yes</span></span>|  
|<span data-ttu-id="1735e-207">StartTime</span><span class="sxs-lookup"><span data-stu-id="1735e-207">StartTime</span></span>|`datetime`|<span data-ttu-id="1735e-208">Zeitpunkt, zu dem das Ereignis begonnen hat (falls vorhanden).</span><span class="sxs-lookup"><span data-stu-id="1735e-208">Time at which the event started, if available.</span></span>|<span data-ttu-id="1735e-209">14</span><span class="sxs-lookup"><span data-stu-id="1735e-209">14</span></span>|<span data-ttu-id="1735e-210">Ja</span><span class="sxs-lookup"><span data-stu-id="1735e-210">Yes</span></span>|  
|<span data-ttu-id="1735e-211">TextData</span><span class="sxs-lookup"><span data-stu-id="1735e-211">TextData</span></span>|`ntext`|<span data-ttu-id="1735e-212">Textwert, der von der Ereignisklasse abhängt, die in der Ablaufverfolgung aufgezeichnet wurde.</span><span class="sxs-lookup"><span data-stu-id="1735e-212">Text value dependent on the event class captured in the trace.</span></span>|<span data-ttu-id="1735e-213">1</span><span class="sxs-lookup"><span data-stu-id="1735e-213">1</span></span>|<span data-ttu-id="1735e-214">Ja</span><span class="sxs-lookup"><span data-stu-id="1735e-214">Yes</span></span>|  
|<span data-ttu-id="1735e-215">TransactionID</span><span class="sxs-lookup"><span data-stu-id="1735e-215">TransactionID</span></span>|`bigint`|<span data-ttu-id="1735e-216">Die vom System zugewiesene ID der Transaktion.</span><span class="sxs-lookup"><span data-stu-id="1735e-216">System-assigned ID of the transaction.</span></span>|<span data-ttu-id="1735e-217">4</span><span class="sxs-lookup"><span data-stu-id="1735e-217">4</span></span>|<span data-ttu-id="1735e-218">Ja</span><span class="sxs-lookup"><span data-stu-id="1735e-218">Yes</span></span>|  
|<span data-ttu-id="1735e-219">XactSequence</span><span class="sxs-lookup"><span data-stu-id="1735e-219">XactSequence</span></span>|`bigint`|<span data-ttu-id="1735e-220">Das Token, das die aktuelle Transaktion beschreibt.</span><span class="sxs-lookup"><span data-stu-id="1735e-220">Token that describes the current transaction.</span></span>|<span data-ttu-id="1735e-221">50</span><span class="sxs-lookup"><span data-stu-id="1735e-221">50</span></span>|<span data-ttu-id="1735e-222">Ja</span><span class="sxs-lookup"><span data-stu-id="1735e-222">Yes</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1735e-223">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1735e-223">See Also</span></span>  
 <span data-ttu-id="1735e-224">[sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1735e-224">[sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span></span>  
 <span data-ttu-id="1735e-225">[Deprecation Announcement-Ereignisklasse](deprecation-announcement-event-class.md) </span><span class="sxs-lookup"><span data-stu-id="1735e-225">[Deprecation Announcement Event Class](deprecation-announcement-event-class.md) </span></span>  
 [<span data-ttu-id="1735e-226">Als veraltet markierte Funktionen der Datenbank-Engine in SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="1735e-226">Deprecated Database Engine Features in SQL Server 2014</span></span>](../../database-engine/deprecated-database-engine-features-in-sql-server-2016.md)  
  
  