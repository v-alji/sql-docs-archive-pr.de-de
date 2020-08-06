---
title: Audit Database Object Take Ownership-Ereignisklasse (Datenspalten) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- Audit Database Object Take Ownership event class
ms.assetid: 26409a60-9616-484b-b608-ca554aef08f6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 427d48eaa8f4c0812a86ab7c85851ed61afe1d1d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617021"
---
# <a name="audit-database-object-take-ownership-event-class"></a><span data-ttu-id="6494f-102">Audit Database Object Take Ownership (Ereignisklasse)</span><span class="sxs-lookup"><span data-stu-id="6494f-102">Audit Database Object Take Ownership Event Class</span></span>
  <span data-ttu-id="6494f-103">Die **Audit Database Object Take Ownership** -Ereignisklasse tritt bei einem Besitzerwechsel für Objekte im Bereich der Datenbank auf.</span><span class="sxs-lookup"><span data-stu-id="6494f-103">The **Audit Database Object Take Ownership** event class occurs when a change of owner for objects within database scope occurs.</span></span>  
  
## <a name="audit-database-object-take-ownership-event-class-data-columns"></a><span data-ttu-id="6494f-104">Audit Database Object Take Ownership-Ereignisklasse (Datenspalten)</span><span class="sxs-lookup"><span data-stu-id="6494f-104">Audit Database Object Take Ownership Event Class Data Columns</span></span>  
  
|<span data-ttu-id="6494f-105">Datenspaltenname</span><span class="sxs-lookup"><span data-stu-id="6494f-105">Data column name</span></span>|<span data-ttu-id="6494f-106">Datentyp</span><span class="sxs-lookup"><span data-stu-id="6494f-106">Data type</span></span>|<span data-ttu-id="6494f-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6494f-107">Description</span></span>|<span data-ttu-id="6494f-108">Column ID</span><span class="sxs-lookup"><span data-stu-id="6494f-108">Column ID</span></span>|<span data-ttu-id="6494f-109">Filterbar</span><span class="sxs-lookup"><span data-stu-id="6494f-109">Filterable</span></span>|  
|----------------------|---------------|-----------------|---------------|----------------|  
|<span data-ttu-id="6494f-110">**ApplicationName**</span><span class="sxs-lookup"><span data-stu-id="6494f-110">**ApplicationName**</span></span>|<span data-ttu-id="6494f-111">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="6494f-111">**nvarchar**</span></span>|<span data-ttu-id="6494f-112">Dies ist der Name der Clientanwendung, die die Verbindung mit einer Instanz von [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] hergestellt hat.</span><span class="sxs-lookup"><span data-stu-id="6494f-112">Name of the client application that created the connection to an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="6494f-113">Diese Spalte wird mit den Werten aufgefüllt, die von der Anwendung übergeben werden, und nicht mit dem angezeigten Namen des Programms.</span><span class="sxs-lookup"><span data-stu-id="6494f-113">This column is populated with the values passed by the application rather than the displayed name of the program.</span></span>|<span data-ttu-id="6494f-114">10</span><span class="sxs-lookup"><span data-stu-id="6494f-114">10</span></span>|<span data-ttu-id="6494f-115">Ja</span><span class="sxs-lookup"><span data-stu-id="6494f-115">Yes</span></span>|  
|<span data-ttu-id="6494f-116">**DatabaseID**</span><span class="sxs-lookup"><span data-stu-id="6494f-116">**DatabaseID**</span></span>|<span data-ttu-id="6494f-117">**int**</span><span class="sxs-lookup"><span data-stu-id="6494f-117">**int**</span></span>|<span data-ttu-id="6494f-118">Die ID der Datenbank, die durch die USE *database* -Anweisung angegeben wurde, bzw. die ID der Standarddatenbank, wenn für eine bestimmte Instanz keine USE *database* -Anweisung ausgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="6494f-118">ID of the database specified by the USE *database* statement or the default database if no USE *database* statement has been issued for a given instance.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="6494f-119">zeigt den Namen der Datenbank an, wenn die **ServerName** -Datenspalte in der Ablaufverfolgung aufgezeichnet wird und der Server verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="6494f-119">displays the name of the database if the **ServerName** data column is captured in the trace and the server is available.</span></span> <span data-ttu-id="6494f-120">Der Wert für eine Datenbank kann mithilfe der DB_ID-Funktion ermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="6494f-120">Determine the value for a database by using the DB_ID function.</span></span>|<span data-ttu-id="6494f-121">3</span><span class="sxs-lookup"><span data-stu-id="6494f-121">3</span></span>|<span data-ttu-id="6494f-122">Ja</span><span class="sxs-lookup"><span data-stu-id="6494f-122">Yes</span></span>|  
|<span data-ttu-id="6494f-123">**DatabaseName**</span><span class="sxs-lookup"><span data-stu-id="6494f-123">**DatabaseName**</span></span>|<span data-ttu-id="6494f-124">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="6494f-124">**nvarchar**</span></span>|<span data-ttu-id="6494f-125">Name der Datenbank, in der die Benutzeranweisung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6494f-125">Name of the database in which the user statement is running.</span></span>|<span data-ttu-id="6494f-126">35</span><span class="sxs-lookup"><span data-stu-id="6494f-126">35</span></span>|<span data-ttu-id="6494f-127">Ja</span><span class="sxs-lookup"><span data-stu-id="6494f-127">Yes</span></span>|  
|<span data-ttu-id="6494f-128">**DBUserName**</span><span class="sxs-lookup"><span data-stu-id="6494f-128">**DBUserName**</span></span>|<span data-ttu-id="6494f-129">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="6494f-129">**nvarchar**</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="6494f-130">-Benutzername des Clients.</span><span class="sxs-lookup"><span data-stu-id="6494f-130">user name of the client.</span></span>|<span data-ttu-id="6494f-131">40</span><span class="sxs-lookup"><span data-stu-id="6494f-131">40</span></span>|<span data-ttu-id="6494f-132">Ja</span><span class="sxs-lookup"><span data-stu-id="6494f-132">Yes</span></span>|  
|<span data-ttu-id="6494f-133">**EventSequence**</span><span class="sxs-lookup"><span data-stu-id="6494f-133">**EventSequence**</span></span>|<span data-ttu-id="6494f-134">**int**</span><span class="sxs-lookup"><span data-stu-id="6494f-134">**int**</span></span>|<span data-ttu-id="6494f-135">Sequenz eines bestimmten Ereignisses innerhalb der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="6494f-135">Sequence of a given event within the request.</span></span>|<span data-ttu-id="6494f-136">51</span><span class="sxs-lookup"><span data-stu-id="6494f-136">51</span></span>|<span data-ttu-id="6494f-137">Nein</span><span class="sxs-lookup"><span data-stu-id="6494f-137">No</span></span>|  
|<span data-ttu-id="6494f-138">**HostName**</span><span class="sxs-lookup"><span data-stu-id="6494f-138">**HostName**</span></span>|<span data-ttu-id="6494f-139">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="6494f-139">**nvarchar**</span></span>|<span data-ttu-id="6494f-140">Der Name des Computers, auf dem der Client ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6494f-140">Name of the computer on which the client is running.</span></span> <span data-ttu-id="6494f-141">Diese Datenspalte wird aufgefüllt, wenn der Hostname vom Client bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="6494f-141">This data column is populated if the client provides the host name.</span></span> <span data-ttu-id="6494f-142">Der Hostname kann mithilfe der HOST_NAME-Funktion bestimmt werden.</span><span class="sxs-lookup"><span data-stu-id="6494f-142">To determine the host name, use the HOST_NAME function.</span></span>|<span data-ttu-id="6494f-143">8</span><span class="sxs-lookup"><span data-stu-id="6494f-143">8</span></span>|<span data-ttu-id="6494f-144">Ja</span><span class="sxs-lookup"><span data-stu-id="6494f-144">Yes</span></span>|  
|<span data-ttu-id="6494f-145">**IsSystem**</span><span class="sxs-lookup"><span data-stu-id="6494f-145">**IsSystem**</span></span>|<span data-ttu-id="6494f-146">**int**</span><span class="sxs-lookup"><span data-stu-id="6494f-146">**int**</span></span>|<span data-ttu-id="6494f-147">Gibt an, ob das Ereignis bei einem Systemprozess oder einem Benutzerprozess aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="6494f-147">Indicates whether the event occurred on a system process or a user process.</span></span> <span data-ttu-id="6494f-148">1 = System, 0 = Benutzer.</span><span class="sxs-lookup"><span data-stu-id="6494f-148">1 = system, 0 = user.</span></span>|<span data-ttu-id="6494f-149">60</span><span class="sxs-lookup"><span data-stu-id="6494f-149">60</span></span>|<span data-ttu-id="6494f-150">Ja</span><span class="sxs-lookup"><span data-stu-id="6494f-150">Yes</span></span>|  
|<span data-ttu-id="6494f-151">**LoginName**</span><span class="sxs-lookup"><span data-stu-id="6494f-151">**LoginName**</span></span>|<span data-ttu-id="6494f-152">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="6494f-152">**nvarchar**</span></span>|<span data-ttu-id="6494f-153">Anmeldename des Benutzers (Anmeldung der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Sicherheit oder [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows-Anmeldeinformationen im Format DOMAIN\username).</span><span class="sxs-lookup"><span data-stu-id="6494f-153">Name of the login of the user (either the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] security login or the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows login credentials in the form of DOMAIN\username).</span></span>|<span data-ttu-id="6494f-154">11</span><span class="sxs-lookup"><span data-stu-id="6494f-154">11</span></span>|<span data-ttu-id="6494f-155">Ja</span><span class="sxs-lookup"><span data-stu-id="6494f-155">Yes</span></span>|  
|<span data-ttu-id="6494f-156">**LoginSid**</span><span class="sxs-lookup"><span data-stu-id="6494f-156">**LoginSid**</span></span>|<span data-ttu-id="6494f-157">**image**</span><span class="sxs-lookup"><span data-stu-id="6494f-157">**image**</span></span>|<span data-ttu-id="6494f-158">Sicherheits-ID (SID) des angemeldeten Benutzers.</span><span class="sxs-lookup"><span data-stu-id="6494f-158">Security identification number (SID) of the logged-in user.</span></span> <span data-ttu-id="6494f-159">Diese Informationen finden Sie in der **sys.server_principals** -Katalogsicht.</span><span class="sxs-lookup"><span data-stu-id="6494f-159">You can find this information in the **sys.server_principals** catalog view.</span></span> <span data-ttu-id="6494f-160">Die SID ist für jede Anmeldung beim Server eindeutig.</span><span class="sxs-lookup"><span data-stu-id="6494f-160">Each SID is unique for each login in the server.</span></span>|<span data-ttu-id="6494f-161">41</span><span class="sxs-lookup"><span data-stu-id="6494f-161">41</span></span>|<span data-ttu-id="6494f-162">Ja</span><span class="sxs-lookup"><span data-stu-id="6494f-162">Yes</span></span>|  
|<span data-ttu-id="6494f-163">**NTDomainName**</span><span class="sxs-lookup"><span data-stu-id="6494f-163">**NTDomainName**</span></span>|<span data-ttu-id="6494f-164">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="6494f-164">**nvarchar**</span></span>|<span data-ttu-id="6494f-165">Windows-Domäne, zu der der Benutzer gehört.</span><span class="sxs-lookup"><span data-stu-id="6494f-165">Windows domain to which the user belongs.</span></span>|<span data-ttu-id="6494f-166">7</span><span class="sxs-lookup"><span data-stu-id="6494f-166">7</span></span>|<span data-ttu-id="6494f-167">Ja</span><span class="sxs-lookup"><span data-stu-id="6494f-167">Yes</span></span>|  
|<span data-ttu-id="6494f-168">**NTUserName**</span><span class="sxs-lookup"><span data-stu-id="6494f-168">**NTUserName**</span></span>|<span data-ttu-id="6494f-169">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="6494f-169">**nvarchar**</span></span>|<span data-ttu-id="6494f-170">Windows-Benutzername.</span><span class="sxs-lookup"><span data-stu-id="6494f-170">Windows user name.</span></span>|<span data-ttu-id="6494f-171">6</span><span class="sxs-lookup"><span data-stu-id="6494f-171">6</span></span>|<span data-ttu-id="6494f-172">Ja</span><span class="sxs-lookup"><span data-stu-id="6494f-172">Yes</span></span>|  
|<span data-ttu-id="6494f-173">**ObjectName**</span><span class="sxs-lookup"><span data-stu-id="6494f-173">**ObjectName**</span></span>|<span data-ttu-id="6494f-174">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="6494f-174">**nvarchar**</span></span>|<span data-ttu-id="6494f-175">Name des Objekts, auf das verwiesen wird</span><span class="sxs-lookup"><span data-stu-id="6494f-175">Name of the object being referenced.</span></span>|<span data-ttu-id="6494f-176">34</span><span class="sxs-lookup"><span data-stu-id="6494f-176">34</span></span>|<span data-ttu-id="6494f-177">Ja</span><span class="sxs-lookup"><span data-stu-id="6494f-177">Yes</span></span>|  
|<span data-ttu-id="6494f-178">**ObjectType**</span><span class="sxs-lookup"><span data-stu-id="6494f-178">**ObjectType**</span></span>|<span data-ttu-id="6494f-179">**int**</span><span class="sxs-lookup"><span data-stu-id="6494f-179">**int**</span></span>|<span data-ttu-id="6494f-180">Der Wert, der den Typ des am Ereignis beteiligten Objekts darstellt.</span><span class="sxs-lookup"><span data-stu-id="6494f-180">Value representing the type of the object involved in the event.</span></span> <span data-ttu-id="6494f-181">Der für diese Spalte zurückgegebene Wert ist eine Kombination des entsprechenden Wertes in der **type** -Spalte in der **sys.objects** -Katalogsicht und der in [ObjectType-Spalte für Ablaufverfolgungsereignisse](objecttype-trace-event-column.md)aufgelisteten Werte.</span><span class="sxs-lookup"><span data-stu-id="6494f-181">The value returned for this column is a combination of the corresponding value in the **type** column in the **sys.objects** catalog view and the values listed in [ObjectType Trace Event Column](objecttype-trace-event-column.md).</span></span> <span data-ttu-id="6494f-182">Wenn z. B. der Wert 8277-U zurückgegeben wird, handelt es sich beim Objekttyp um eine benutzerdefinierte Tabelle.</span><span class="sxs-lookup"><span data-stu-id="6494f-182">For example, if 8277-U is returned, the object type is user-defined table.</span></span>|<span data-ttu-id="6494f-183">28</span><span class="sxs-lookup"><span data-stu-id="6494f-183">28</span></span>|<span data-ttu-id="6494f-184">Ja</span><span class="sxs-lookup"><span data-stu-id="6494f-184">Yes</span></span>|  
|<span data-ttu-id="6494f-185">**OwnerName**</span><span class="sxs-lookup"><span data-stu-id="6494f-185">**OwnerName**</span></span>|<span data-ttu-id="6494f-186">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="6494f-186">**nvarchar**</span></span>|<span data-ttu-id="6494f-187">Datenbank-Benutzername des Objektbesitzers.</span><span class="sxs-lookup"><span data-stu-id="6494f-187">Database user name of the object owner.</span></span>|<span data-ttu-id="6494f-188">37</span><span class="sxs-lookup"><span data-stu-id="6494f-188">37</span></span>|<span data-ttu-id="6494f-189">Ja</span><span class="sxs-lookup"><span data-stu-id="6494f-189">Yes</span></span>|  
|<span data-ttu-id="6494f-190">**RequestID**</span><span class="sxs-lookup"><span data-stu-id="6494f-190">**RequestID**</span></span>|<span data-ttu-id="6494f-191">**int**</span><span class="sxs-lookup"><span data-stu-id="6494f-191">**int**</span></span>|<span data-ttu-id="6494f-192">Die ID der Anforderung, die die Anweisung enthält.</span><span class="sxs-lookup"><span data-stu-id="6494f-192">ID of the request containing the statement.</span></span>|<span data-ttu-id="6494f-193">49</span><span class="sxs-lookup"><span data-stu-id="6494f-193">49</span></span>|<span data-ttu-id="6494f-194">Ja</span><span class="sxs-lookup"><span data-stu-id="6494f-194">Yes</span></span>|  
|<span data-ttu-id="6494f-195">**ServerName**</span><span class="sxs-lookup"><span data-stu-id="6494f-195">**ServerName**</span></span>|<span data-ttu-id="6494f-196">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="6494f-196">**nvarchar**</span></span>|<span data-ttu-id="6494f-197">Name der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz, für die eine Ablaufverfolgung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6494f-197">Name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] being traced.</span></span>|<span data-ttu-id="6494f-198">26</span><span class="sxs-lookup"><span data-stu-id="6494f-198">26</span></span>|<span data-ttu-id="6494f-199">Nein</span><span class="sxs-lookup"><span data-stu-id="6494f-199">No</span></span>|  
|<span data-ttu-id="6494f-200">**SessionLoginName**</span><span class="sxs-lookup"><span data-stu-id="6494f-200">**SessionLoginName**</span></span>|<span data-ttu-id="6494f-201">**Nvarchar**</span><span class="sxs-lookup"><span data-stu-id="6494f-201">**Nvarchar**</span></span>|<span data-ttu-id="6494f-202">Der Anmeldename des Benutzers, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="6494f-202">Login name of the user who originated the session.</span></span> <span data-ttu-id="6494f-203">Wenn Sie z. B. mit Login1 eine Verbindung zu [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] herstellen und mit Login2 eine Anweisung ausführen, zeigt **SessionLoginName** Login1 an, und **LoginName** zeigt Login2 an.</span><span class="sxs-lookup"><span data-stu-id="6494f-203">For example, if you connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using Login1 and execute a statement as Login2, **SessionLoginName** shows Login1 and **LoginName** shows Login2.</span></span> <span data-ttu-id="6494f-204">Diese Spalte zeigt sowohl den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] - als auch den Windows-Anmeldenamen an.</span><span class="sxs-lookup"><span data-stu-id="6494f-204">This column displays both [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and Windows logins.</span></span>|<span data-ttu-id="6494f-205">64</span><span class="sxs-lookup"><span data-stu-id="6494f-205">64</span></span>|<span data-ttu-id="6494f-206">Ja</span><span class="sxs-lookup"><span data-stu-id="6494f-206">Yes</span></span>|  
|<span data-ttu-id="6494f-207">**SPID**</span><span class="sxs-lookup"><span data-stu-id="6494f-207">**SPID**</span></span>|<span data-ttu-id="6494f-208">**int**</span><span class="sxs-lookup"><span data-stu-id="6494f-208">**int**</span></span>|<span data-ttu-id="6494f-209">Die ID der Sitzung, in der das Ereignis aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="6494f-209">ID of the session on which the event occurred.</span></span>|<span data-ttu-id="6494f-210">12</span><span class="sxs-lookup"><span data-stu-id="6494f-210">12</span></span>|<span data-ttu-id="6494f-211">Ja</span><span class="sxs-lookup"><span data-stu-id="6494f-211">Yes</span></span>|  
|<span data-ttu-id="6494f-212">**StartTime**</span><span class="sxs-lookup"><span data-stu-id="6494f-212">**StartTime**</span></span>|<span data-ttu-id="6494f-213">**datetime**</span><span class="sxs-lookup"><span data-stu-id="6494f-213">**datetime**</span></span>|<span data-ttu-id="6494f-214">Zeitpunkt, zu dem das Ereignis begonnen hat (falls vorhanden).</span><span class="sxs-lookup"><span data-stu-id="6494f-214">Time at which the event started, if available.</span></span>|<span data-ttu-id="6494f-215">14</span><span class="sxs-lookup"><span data-stu-id="6494f-215">14</span></span>|<span data-ttu-id="6494f-216">Ja</span><span class="sxs-lookup"><span data-stu-id="6494f-216">Yes</span></span>|  
|<span data-ttu-id="6494f-217">**Erfolgreich**</span><span class="sxs-lookup"><span data-stu-id="6494f-217">**Success**</span></span>|<span data-ttu-id="6494f-218">**int**</span><span class="sxs-lookup"><span data-stu-id="6494f-218">**int**</span></span>|<span data-ttu-id="6494f-219">1 = Erfolg</span><span class="sxs-lookup"><span data-stu-id="6494f-219">1 = success.</span></span> <span data-ttu-id="6494f-220">0 = Fehler.</span><span class="sxs-lookup"><span data-stu-id="6494f-220">0 = failure.</span></span> <span data-ttu-id="6494f-221">Der Wert 1 zeigt z. B. den Erfolg einer Berechtigungsüberprüfung an und der Wert 0 das Fehlschlagen dieser Überprüfung.</span><span class="sxs-lookup"><span data-stu-id="6494f-221">For example, a value of 1 indicates success of a permissions check and a value of 0 indicates a failure of that check.</span></span>|<span data-ttu-id="6494f-222">23</span><span class="sxs-lookup"><span data-stu-id="6494f-222">23</span></span>|<span data-ttu-id="6494f-223">Ja</span><span class="sxs-lookup"><span data-stu-id="6494f-223">Yes</span></span>|  
|<span data-ttu-id="6494f-224">**TargetUserName**</span><span class="sxs-lookup"><span data-stu-id="6494f-224">**TargetUserName**</span></span>|<span data-ttu-id="6494f-225">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="6494f-225">**nvarchar**</span></span>|<span data-ttu-id="6494f-226">Für Aktionen, die auf einen Datenbankbenutzer abzielen (z. B. das Erteilen von Berechtigungen für einen Benutzer), der Name des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="6494f-226">For actions that target a database user (for example, granting permission to a user), the name of that user.</span></span>|<span data-ttu-id="6494f-227">39</span><span class="sxs-lookup"><span data-stu-id="6494f-227">39</span></span>|<span data-ttu-id="6494f-228">Ja</span><span class="sxs-lookup"><span data-stu-id="6494f-228">Yes</span></span>|  
|<span data-ttu-id="6494f-229">**TextData**</span><span class="sxs-lookup"><span data-stu-id="6494f-229">**TextData**</span></span>|<span data-ttu-id="6494f-230">**ntext**</span><span class="sxs-lookup"><span data-stu-id="6494f-230">**ntext**</span></span>|<span data-ttu-id="6494f-231">Textwert, der von der Ereignisklasse abhängt, die in der Ablaufverfolgung aufgezeichnet wurde.</span><span class="sxs-lookup"><span data-stu-id="6494f-231">Text value dependent on the event class captured in the trace.</span></span>|<span data-ttu-id="6494f-232">1</span><span class="sxs-lookup"><span data-stu-id="6494f-232">1</span></span>|<span data-ttu-id="6494f-233">Ja</span><span class="sxs-lookup"><span data-stu-id="6494f-233">Yes</span></span>|  
|<span data-ttu-id="6494f-234">**TransactionID**</span><span class="sxs-lookup"><span data-stu-id="6494f-234">**TransactionID**</span></span>|<span data-ttu-id="6494f-235">**bigint**</span><span class="sxs-lookup"><span data-stu-id="6494f-235">**bigint**</span></span>|<span data-ttu-id="6494f-236">Die vom System zugewiesene ID der Transaktion.</span><span class="sxs-lookup"><span data-stu-id="6494f-236">System-assigned ID of the transaction.</span></span>|<span data-ttu-id="6494f-237">4</span><span class="sxs-lookup"><span data-stu-id="6494f-237">4</span></span>|<span data-ttu-id="6494f-238">Ja</span><span class="sxs-lookup"><span data-stu-id="6494f-238">Yes</span></span>|  
|<span data-ttu-id="6494f-239">**XactSequence**</span><span class="sxs-lookup"><span data-stu-id="6494f-239">**XactSequence**</span></span>|<span data-ttu-id="6494f-240">**bigint**</span><span class="sxs-lookup"><span data-stu-id="6494f-240">**bigint**</span></span>|<span data-ttu-id="6494f-241">Token zur Beschreibung der aktuellen Transaktion.</span><span class="sxs-lookup"><span data-stu-id="6494f-241">Token used to describe the current transaction.</span></span>|<span data-ttu-id="6494f-242">50</span><span class="sxs-lookup"><span data-stu-id="6494f-242">50</span></span>|<span data-ttu-id="6494f-243">Ja</span><span class="sxs-lookup"><span data-stu-id="6494f-243">Yes</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6494f-244">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6494f-244">See Also</span></span>  
 [<span data-ttu-id="6494f-245">sp_trace_setevent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6494f-245">sp_trace_setevent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)  
  
  