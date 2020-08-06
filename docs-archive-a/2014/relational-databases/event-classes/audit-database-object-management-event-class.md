---
title: Datenspalten der Audit Database Object Management-Ereignisklasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- Audit Database Object Management event class
ms.assetid: bc5c0be2-990b-4032-a5e6-41ce98661698
author: stevestein
ms.author: sstein
ms.openlocfilehash: bb9493acc0cbada458d05b3ab102237b2d1aa00e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616081"
---
# <a name="audit-database-object-management-event-class"></a><span data-ttu-id="de1ac-102">Audit Database Object Management-Ereignisklasse</span><span class="sxs-lookup"><span data-stu-id="de1ac-102">Audit Database Object Management Event Class</span></span>
  <span data-ttu-id="de1ac-103">Die **Audit Database Object Management** -Ereignisklasse tritt auf, wenn eine CREATE-, ALTER- oder DROP-Anweisung für Datenbankobjekte ausgeführt wird, wie z. B. Schemas.</span><span class="sxs-lookup"><span data-stu-id="de1ac-103">The **Audit Database Object Management** event class occurs when a CREATE, ALTER, or DROP statement is executed on database objects, such as schemas.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="de1ac-104">Auf den öffentlichen Schlüssel bezogene Aktionen werden nicht überwacht.</span><span class="sxs-lookup"><span data-stu-id="de1ac-104">Actions related to the public key are not audited.</span></span>  
  
## <a name="audit-database-object-management-event-class-data-columns"></a><span data-ttu-id="de1ac-105">Datenspalten der Audit Database Object Management-Ereignisklasse</span><span class="sxs-lookup"><span data-stu-id="de1ac-105">Audit Database Object Management Event Class Data Columns</span></span>  
  
|<span data-ttu-id="de1ac-106">Datenspaltenname</span><span class="sxs-lookup"><span data-stu-id="de1ac-106">Data column name</span></span>|<span data-ttu-id="de1ac-107">Datentyp</span><span class="sxs-lookup"><span data-stu-id="de1ac-107">Data type</span></span>|<span data-ttu-id="de1ac-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="de1ac-108">Description</span></span>|<span data-ttu-id="de1ac-109">Column ID</span><span class="sxs-lookup"><span data-stu-id="de1ac-109">Column ID</span></span>|<span data-ttu-id="de1ac-110">Filterbar</span><span class="sxs-lookup"><span data-stu-id="de1ac-110">Filterable</span></span>|  
|----------------------|---------------|-----------------|---------------|----------------|  
|<span data-ttu-id="de1ac-111">**ApplicationName**</span><span class="sxs-lookup"><span data-stu-id="de1ac-111">**ApplicationName**</span></span>|<span data-ttu-id="de1ac-112">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="de1ac-112">**nvarchar**</span></span>|<span data-ttu-id="de1ac-113">Dies ist der Name der Clientanwendung, die die Verbindung mit einer Instanz von [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] hergestellt hat.</span><span class="sxs-lookup"><span data-stu-id="de1ac-113">Name of the client application that created the connection to an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="de1ac-114">Diese Spalte wird mit den Werten aufgefüllt, die von der Anwendung übergeben werden, und nicht mit dem angezeigten Namen des Programms.</span><span class="sxs-lookup"><span data-stu-id="de1ac-114">This column is populated with the values passed by the application rather than the displayed name of the program.</span></span>|<span data-ttu-id="de1ac-115">10</span><span class="sxs-lookup"><span data-stu-id="de1ac-115">10</span></span>|<span data-ttu-id="de1ac-116">Ja</span><span class="sxs-lookup"><span data-stu-id="de1ac-116">Yes</span></span>|  
|<span data-ttu-id="de1ac-117">**DatabaseID**</span><span class="sxs-lookup"><span data-stu-id="de1ac-117">**DatabaseID**</span></span>|<span data-ttu-id="de1ac-118">**int**</span><span class="sxs-lookup"><span data-stu-id="de1ac-118">**int**</span></span>|<span data-ttu-id="de1ac-119">Die ID der Datenbank, die durch die USE *database* -Anweisung angegeben wurde, bzw. die ID der Standarddatenbank, wenn für eine bestimmte Instanz keine USE *database* -Anweisung ausgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="de1ac-119">ID of the database specified by the USE *database* statement or the default database if no USE *database* statement has been issued for a given instance.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="de1ac-120">zeigt den Namen der Datenbank an, wenn die **ServerName** -Datenspalte in der Ablaufverfolgung aufgezeichnet wird und der Server verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="de1ac-120">displays the name of the database if the **ServerName** data column is captured in the trace and the server is available.</span></span> <span data-ttu-id="de1ac-121">Der Wert für eine Datenbank kann mithilfe der DB_ID-Funktion ermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="de1ac-121">Determine the value for a database by using the DB_ID function.</span></span>|<span data-ttu-id="de1ac-122">3</span><span class="sxs-lookup"><span data-stu-id="de1ac-122">3</span></span>|<span data-ttu-id="de1ac-123">Ja</span><span class="sxs-lookup"><span data-stu-id="de1ac-123">Yes</span></span>|  
|<span data-ttu-id="de1ac-124">**DatabaseName**</span><span class="sxs-lookup"><span data-stu-id="de1ac-124">**DatabaseName**</span></span>|<span data-ttu-id="de1ac-125">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="de1ac-125">**nvarchar**</span></span>|<span data-ttu-id="de1ac-126">Name der Datenbank, in der die Benutzeranweisung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="de1ac-126">Name of the database in which the user statement is running.</span></span>|<span data-ttu-id="de1ac-127">35</span><span class="sxs-lookup"><span data-stu-id="de1ac-127">35</span></span>|<span data-ttu-id="de1ac-128">Ja</span><span class="sxs-lookup"><span data-stu-id="de1ac-128">Yes</span></span>|  
|<span data-ttu-id="de1ac-129">**DBUserName**</span><span class="sxs-lookup"><span data-stu-id="de1ac-129">**DBUserName**</span></span>|<span data-ttu-id="de1ac-130">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="de1ac-130">**nvarchar**</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="de1ac-131">-Benutzername des Clients.</span><span class="sxs-lookup"><span data-stu-id="de1ac-131">user name of the client.</span></span>|<span data-ttu-id="de1ac-132">40</span><span class="sxs-lookup"><span data-stu-id="de1ac-132">40</span></span>|<span data-ttu-id="de1ac-133">Ja</span><span class="sxs-lookup"><span data-stu-id="de1ac-133">Yes</span></span>|  
|<span data-ttu-id="de1ac-134">**EventSequence**</span><span class="sxs-lookup"><span data-stu-id="de1ac-134">**EventSequence**</span></span>|<span data-ttu-id="de1ac-135">**int**</span><span class="sxs-lookup"><span data-stu-id="de1ac-135">**int**</span></span>|<span data-ttu-id="de1ac-136">Sequenz eines bestimmten Ereignisses innerhalb der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="de1ac-136">Sequence of a given event within the request.</span></span>|<span data-ttu-id="de1ac-137">51</span><span class="sxs-lookup"><span data-stu-id="de1ac-137">51</span></span>|<span data-ttu-id="de1ac-138">Nein</span><span class="sxs-lookup"><span data-stu-id="de1ac-138">No</span></span>|  
|<span data-ttu-id="de1ac-139">**EventSubClass**</span><span class="sxs-lookup"><span data-stu-id="de1ac-139">**EventSubClass**</span></span>|<span data-ttu-id="de1ac-140">**int**</span><span class="sxs-lookup"><span data-stu-id="de1ac-140">**int**</span></span>|<span data-ttu-id="de1ac-141">Der Typ der Ereignisunterklasse.</span><span class="sxs-lookup"><span data-stu-id="de1ac-141">Type of event subclass.</span></span><br /><br /> <span data-ttu-id="de1ac-142">1 = Erstellen</span><span class="sxs-lookup"><span data-stu-id="de1ac-142">1=Create</span></span><br /><br /> <span data-ttu-id="de1ac-143">2 = Ändern</span><span class="sxs-lookup"><span data-stu-id="de1ac-143">2=Alter</span></span><br /><br /> <span data-ttu-id="de1ac-144">3 = Löschen</span><span class="sxs-lookup"><span data-stu-id="de1ac-144">3=Drop</span></span><br /><br /> <span data-ttu-id="de1ac-145">4 = Sichern</span><span class="sxs-lookup"><span data-stu-id="de1ac-145">4=Dump</span></span><br /><br /> <span data-ttu-id="de1ac-146">10 = Öffnen</span><span class="sxs-lookup"><span data-stu-id="de1ac-146">10=Open</span></span><br /><br /> <span data-ttu-id="de1ac-147">11 = Laden</span><span class="sxs-lookup"><span data-stu-id="de1ac-147">11=Load</span></span><br /><br /> <span data-ttu-id="de1ac-148">12 = Zugreifen</span><span class="sxs-lookup"><span data-stu-id="de1ac-148">12=Access</span></span>|<span data-ttu-id="de1ac-149">21</span><span class="sxs-lookup"><span data-stu-id="de1ac-149">21</span></span>|<span data-ttu-id="de1ac-150">Ja</span><span class="sxs-lookup"><span data-stu-id="de1ac-150">Yes</span></span>|  
|<span data-ttu-id="de1ac-151">**HostName**</span><span class="sxs-lookup"><span data-stu-id="de1ac-151">**HostName**</span></span>|<span data-ttu-id="de1ac-152">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="de1ac-152">**nvarchar**</span></span>|<span data-ttu-id="de1ac-153">Der Name des Computers, auf dem der Client ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="de1ac-153">Name of the computer on which the client is running.</span></span> <span data-ttu-id="de1ac-154">Diese Datenspalte wird aufgefüllt, wenn der Hostname vom Client bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="de1ac-154">This data column is populated if the client provides the host name.</span></span> <span data-ttu-id="de1ac-155">Der Hostname kann mithilfe der HOST_NAME-Funktion bestimmt werden.</span><span class="sxs-lookup"><span data-stu-id="de1ac-155">To determine the host name, use the HOST_NAME function.</span></span>|<span data-ttu-id="de1ac-156">8</span><span class="sxs-lookup"><span data-stu-id="de1ac-156">8</span></span>|<span data-ttu-id="de1ac-157">Ja</span><span class="sxs-lookup"><span data-stu-id="de1ac-157">Yes</span></span>|  
|<span data-ttu-id="de1ac-158">**IsSystem**</span><span class="sxs-lookup"><span data-stu-id="de1ac-158">**IsSystem**</span></span>|<span data-ttu-id="de1ac-159">**int**</span><span class="sxs-lookup"><span data-stu-id="de1ac-159">**int**</span></span>|<span data-ttu-id="de1ac-160">Gibt an, ob das Ereignis bei einem Systemprozess oder einem Benutzerprozess aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="de1ac-160">Indicates whether the event occurred on a system process or a user process.</span></span> <span data-ttu-id="de1ac-161">1 = System, 0 = Benutzer.</span><span class="sxs-lookup"><span data-stu-id="de1ac-161">1 = system, 0 = user.</span></span>|<span data-ttu-id="de1ac-162">60</span><span class="sxs-lookup"><span data-stu-id="de1ac-162">60</span></span>|<span data-ttu-id="de1ac-163">Ja</span><span class="sxs-lookup"><span data-stu-id="de1ac-163">Yes</span></span>|  
|<span data-ttu-id="de1ac-164">**LoginName**</span><span class="sxs-lookup"><span data-stu-id="de1ac-164">**LoginName**</span></span>|<span data-ttu-id="de1ac-165">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="de1ac-165">**nvarchar**</span></span>|<span data-ttu-id="de1ac-166">Anmeldename des Benutzers (Anmeldung der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Sicherheit oder [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows-Anmeldeinformationen im Format DOMAIN\username).</span><span class="sxs-lookup"><span data-stu-id="de1ac-166">Name of the login of the user (either the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] security login or the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows login credentials in the form of DOMAIN\username).</span></span>|<span data-ttu-id="de1ac-167">11</span><span class="sxs-lookup"><span data-stu-id="de1ac-167">11</span></span>|<span data-ttu-id="de1ac-168">Ja</span><span class="sxs-lookup"><span data-stu-id="de1ac-168">Yes</span></span>|  
|<span data-ttu-id="de1ac-169">**LoginSid**</span><span class="sxs-lookup"><span data-stu-id="de1ac-169">**LoginSid**</span></span>|<span data-ttu-id="de1ac-170">**image**</span><span class="sxs-lookup"><span data-stu-id="de1ac-170">**image**</span></span>|<span data-ttu-id="de1ac-171">Sicherheits-ID (SID) des angemeldeten Benutzers.</span><span class="sxs-lookup"><span data-stu-id="de1ac-171">Security identification number (SID) of the logged-in user.</span></span> <span data-ttu-id="de1ac-172">Diese Informationen finden Sie in der **sys.server_principals** -Katalogsicht.</span><span class="sxs-lookup"><span data-stu-id="de1ac-172">You can find this information in the **sys.server_principals** catalog view.</span></span> <span data-ttu-id="de1ac-173">Die SID ist für jede Anmeldung beim Server eindeutig.</span><span class="sxs-lookup"><span data-stu-id="de1ac-173">Each SID is unique for each login in the server.</span></span>|<span data-ttu-id="de1ac-174">41</span><span class="sxs-lookup"><span data-stu-id="de1ac-174">41</span></span>|<span data-ttu-id="de1ac-175">Ja</span><span class="sxs-lookup"><span data-stu-id="de1ac-175">Yes</span></span>|  
|<span data-ttu-id="de1ac-176">**NTDomainName**</span><span class="sxs-lookup"><span data-stu-id="de1ac-176">**NTDomainName**</span></span>|<span data-ttu-id="de1ac-177">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="de1ac-177">**nvarchar**</span></span>|<span data-ttu-id="de1ac-178">Windows-Domäne, zu der der Benutzer gehört.</span><span class="sxs-lookup"><span data-stu-id="de1ac-178">Windows domain to which the user belongs.</span></span>|<span data-ttu-id="de1ac-179">7</span><span class="sxs-lookup"><span data-stu-id="de1ac-179">7</span></span>|<span data-ttu-id="de1ac-180">Ja</span><span class="sxs-lookup"><span data-stu-id="de1ac-180">Yes</span></span>|  
|<span data-ttu-id="de1ac-181">**NTUserName**</span><span class="sxs-lookup"><span data-stu-id="de1ac-181">**NTUserName**</span></span>|<span data-ttu-id="de1ac-182">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="de1ac-182">**nvarchar**</span></span>|<span data-ttu-id="de1ac-183">Windows-Benutzername.</span><span class="sxs-lookup"><span data-stu-id="de1ac-183">Windows user name.</span></span>|<span data-ttu-id="de1ac-184">6</span><span class="sxs-lookup"><span data-stu-id="de1ac-184">6</span></span>|<span data-ttu-id="de1ac-185">Ja</span><span class="sxs-lookup"><span data-stu-id="de1ac-185">Yes</span></span>|  
|<span data-ttu-id="de1ac-186">**ObjectName**</span><span class="sxs-lookup"><span data-stu-id="de1ac-186">**ObjectName**</span></span>|<span data-ttu-id="de1ac-187">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="de1ac-187">**nvarchar**</span></span>|<span data-ttu-id="de1ac-188">Name des Objekts, auf das verwiesen wird</span><span class="sxs-lookup"><span data-stu-id="de1ac-188">Name of the object being referenced.</span></span>|<span data-ttu-id="de1ac-189">34</span><span class="sxs-lookup"><span data-stu-id="de1ac-189">34</span></span>|<span data-ttu-id="de1ac-190">Ja</span><span class="sxs-lookup"><span data-stu-id="de1ac-190">Yes</span></span>|  
|<span data-ttu-id="de1ac-191">**ObjectType**</span><span class="sxs-lookup"><span data-stu-id="de1ac-191">**ObjectType**</span></span>|<span data-ttu-id="de1ac-192">**int**</span><span class="sxs-lookup"><span data-stu-id="de1ac-192">**int**</span></span>|<span data-ttu-id="de1ac-193">Der Wert, der den Typ des am Ereignis beteiligten Objekts darstellt.</span><span class="sxs-lookup"><span data-stu-id="de1ac-193">Value representing the type of the object involved in the event.</span></span> <span data-ttu-id="de1ac-194">Dieser Wert entspricht der type-Spalte in der **sys.objects** -Katalogsicht.</span><span class="sxs-lookup"><span data-stu-id="de1ac-194">This value corresponds to the type column in the **sys.objects** catalog view.</span></span> <span data-ttu-id="de1ac-195">Weitere Werte finden Sie unter [ObjectType (Spalte für Ablaufverfolgungsereignisse)](objecttype-trace-event-column.md).</span><span class="sxs-lookup"><span data-stu-id="de1ac-195">For values, see [ObjectType Trace Event Column](objecttype-trace-event-column.md).</span></span>|<span data-ttu-id="de1ac-196">28</span><span class="sxs-lookup"><span data-stu-id="de1ac-196">28</span></span>|<span data-ttu-id="de1ac-197">Ja</span><span class="sxs-lookup"><span data-stu-id="de1ac-197">Yes</span></span>|  
|<span data-ttu-id="de1ac-198">**OwnerName**</span><span class="sxs-lookup"><span data-stu-id="de1ac-198">**OwnerName**</span></span>|<span data-ttu-id="de1ac-199">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="de1ac-199">**nvarchar**</span></span>|<span data-ttu-id="de1ac-200">Datenbank-Benutzername des Objektbesitzers.</span><span class="sxs-lookup"><span data-stu-id="de1ac-200">Database user name of the object owner.</span></span>|<span data-ttu-id="de1ac-201">37</span><span class="sxs-lookup"><span data-stu-id="de1ac-201">37</span></span>|<span data-ttu-id="de1ac-202">Ja</span><span class="sxs-lookup"><span data-stu-id="de1ac-202">Yes</span></span>|  
|<span data-ttu-id="de1ac-203">**RequestID**</span><span class="sxs-lookup"><span data-stu-id="de1ac-203">**RequestID**</span></span>|<span data-ttu-id="de1ac-204">**int**</span><span class="sxs-lookup"><span data-stu-id="de1ac-204">**int**</span></span>|<span data-ttu-id="de1ac-205">Die ID der Anforderung, die die Anweisung enthält.</span><span class="sxs-lookup"><span data-stu-id="de1ac-205">ID of the request containing the statement.</span></span>|<span data-ttu-id="de1ac-206">49</span><span class="sxs-lookup"><span data-stu-id="de1ac-206">49</span></span>|<span data-ttu-id="de1ac-207">Ja</span><span class="sxs-lookup"><span data-stu-id="de1ac-207">Yes</span></span>|  
|<span data-ttu-id="de1ac-208">**ServerName**</span><span class="sxs-lookup"><span data-stu-id="de1ac-208">**ServerName**</span></span>|<span data-ttu-id="de1ac-209">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="de1ac-209">**nvarchar**</span></span>|<span data-ttu-id="de1ac-210">Name der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz, für die eine Ablaufverfolgung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="de1ac-210">Name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] being traced.</span></span>|<span data-ttu-id="de1ac-211">26</span><span class="sxs-lookup"><span data-stu-id="de1ac-211">26</span></span>|<span data-ttu-id="de1ac-212">Nein</span><span class="sxs-lookup"><span data-stu-id="de1ac-212">No</span></span>|  
|<span data-ttu-id="de1ac-213">**SessionLoginName**</span><span class="sxs-lookup"><span data-stu-id="de1ac-213">**SessionLoginName**</span></span>|<span data-ttu-id="de1ac-214">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="de1ac-214">**nvarchar**</span></span>|<span data-ttu-id="de1ac-215">Der Anmeldename des Benutzers, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="de1ac-215">Login name of the user who originated the session.</span></span> <span data-ttu-id="de1ac-216">Wenn Sie z. B. mit Login1 eine Verbindung zu [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] herstellen und mit Login2 eine Anweisung ausführen, zeigt **SessionLoginName** Login1 an, und **LoginName** zeigt Login2 an.</span><span class="sxs-lookup"><span data-stu-id="de1ac-216">For example, if you connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using Login1 and execute a statement as Login2, **SessionLoginName** shows Login1 and **LoginName** shows Login2.</span></span> <span data-ttu-id="de1ac-217">Diese Spalte zeigt sowohl den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] - als auch den Windows-Anmeldenamen an.</span><span class="sxs-lookup"><span data-stu-id="de1ac-217">This column displays both [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and Windows logins.</span></span>|<span data-ttu-id="de1ac-218">64</span><span class="sxs-lookup"><span data-stu-id="de1ac-218">64</span></span>|<span data-ttu-id="de1ac-219">Ja</span><span class="sxs-lookup"><span data-stu-id="de1ac-219">Yes</span></span>|  
|<span data-ttu-id="de1ac-220">**SPID**</span><span class="sxs-lookup"><span data-stu-id="de1ac-220">**SPID**</span></span>|<span data-ttu-id="de1ac-221">**int**</span><span class="sxs-lookup"><span data-stu-id="de1ac-221">**int**</span></span>|<span data-ttu-id="de1ac-222">Die ID der Sitzung, in der das Ereignis aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="de1ac-222">ID of the session on which the event occurred.</span></span>|<span data-ttu-id="de1ac-223">12</span><span class="sxs-lookup"><span data-stu-id="de1ac-223">12</span></span>|<span data-ttu-id="de1ac-224">Ja</span><span class="sxs-lookup"><span data-stu-id="de1ac-224">Yes</span></span>|  
|<span data-ttu-id="de1ac-225">**StartTime**</span><span class="sxs-lookup"><span data-stu-id="de1ac-225">**StartTime**</span></span>|<span data-ttu-id="de1ac-226">**datetime**</span><span class="sxs-lookup"><span data-stu-id="de1ac-226">**datetime**</span></span>|<span data-ttu-id="de1ac-227">Zeitpunkt, zu dem das Ereignis begonnen hat (falls vorhanden).</span><span class="sxs-lookup"><span data-stu-id="de1ac-227">Time at which the event started, if available.</span></span>|<span data-ttu-id="de1ac-228">14</span><span class="sxs-lookup"><span data-stu-id="de1ac-228">14</span></span>|<span data-ttu-id="de1ac-229">Ja</span><span class="sxs-lookup"><span data-stu-id="de1ac-229">Yes</span></span>|  
|<span data-ttu-id="de1ac-230">**Erfolgreich**</span><span class="sxs-lookup"><span data-stu-id="de1ac-230">**Success**</span></span>|<span data-ttu-id="de1ac-231">**int**</span><span class="sxs-lookup"><span data-stu-id="de1ac-231">**int**</span></span>|<span data-ttu-id="de1ac-232">1 = Erfolg</span><span class="sxs-lookup"><span data-stu-id="de1ac-232">1 = success.</span></span> <span data-ttu-id="de1ac-233">0 = Fehler.</span><span class="sxs-lookup"><span data-stu-id="de1ac-233">0 = failure.</span></span> <span data-ttu-id="de1ac-234">Der Wert 1 deutet beispielsweise auf eine erfolgreiche Überprüfung der Berechtigungen hin, während die Überprüfung bei dem Wert 0 fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="de1ac-234">For example, a value of 1 indicates success of a permissions check and a value of 0 indicates failure of that check.</span></span>|<span data-ttu-id="de1ac-235">23</span><span class="sxs-lookup"><span data-stu-id="de1ac-235">23</span></span>|<span data-ttu-id="de1ac-236">Ja</span><span class="sxs-lookup"><span data-stu-id="de1ac-236">Yes</span></span>|  
|<span data-ttu-id="de1ac-237">**TextData**</span><span class="sxs-lookup"><span data-stu-id="de1ac-237">**TextData**</span></span>|<span data-ttu-id="de1ac-238">**ntext**</span><span class="sxs-lookup"><span data-stu-id="de1ac-238">**ntext**</span></span>|<span data-ttu-id="de1ac-239">Textwert, der von der Ereignisklasse abhängt, die in der Ablaufverfolgung aufgezeichnet wurde.</span><span class="sxs-lookup"><span data-stu-id="de1ac-239">Text value dependent on the event class captured in the trace.</span></span>|<span data-ttu-id="de1ac-240">1</span><span class="sxs-lookup"><span data-stu-id="de1ac-240">1</span></span>|<span data-ttu-id="de1ac-241">Ja</span><span class="sxs-lookup"><span data-stu-id="de1ac-241">Yes</span></span>|  
|<span data-ttu-id="de1ac-242">**TransactionID**</span><span class="sxs-lookup"><span data-stu-id="de1ac-242">**TransactionID**</span></span>|<span data-ttu-id="de1ac-243">**bigint**</span><span class="sxs-lookup"><span data-stu-id="de1ac-243">**bigint**</span></span>|<span data-ttu-id="de1ac-244">Die vom System zugewiesene ID der Transaktion.</span><span class="sxs-lookup"><span data-stu-id="de1ac-244">System-assigned ID of the transaction.</span></span>|<span data-ttu-id="de1ac-245">4</span><span class="sxs-lookup"><span data-stu-id="de1ac-245">4</span></span>|<span data-ttu-id="de1ac-246">Ja</span><span class="sxs-lookup"><span data-stu-id="de1ac-246">Yes</span></span>|  
|<span data-ttu-id="de1ac-247">**XactSequence**</span><span class="sxs-lookup"><span data-stu-id="de1ac-247">**XactSequence**</span></span>|<span data-ttu-id="de1ac-248">**bigint**</span><span class="sxs-lookup"><span data-stu-id="de1ac-248">**bigint**</span></span>|<span data-ttu-id="de1ac-249">Token zur Beschreibung der aktuellen Transaktion.</span><span class="sxs-lookup"><span data-stu-id="de1ac-249">Token used to describe the current transaction.</span></span>|<span data-ttu-id="de1ac-250">50</span><span class="sxs-lookup"><span data-stu-id="de1ac-250">50</span></span>|<span data-ttu-id="de1ac-251">Ja</span><span class="sxs-lookup"><span data-stu-id="de1ac-251">Yes</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="de1ac-252">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="de1ac-252">See Also</span></span>  
 <span data-ttu-id="de1ac-253">[Erweiterte Ereignisse](../extended-events/extended-events.md) </span><span class="sxs-lookup"><span data-stu-id="de1ac-253">[Extended Events](../extended-events/extended-events.md) </span></span>  
 [<span data-ttu-id="de1ac-254">sp_trace_setevent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="de1ac-254">sp_trace_setevent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)  
  
  