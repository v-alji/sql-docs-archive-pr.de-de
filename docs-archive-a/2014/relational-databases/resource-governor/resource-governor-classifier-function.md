---
title: Klassifizierungsfunktion der Ressourcenkontrolle | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Resource Governor, classifier function
- user-defined functions [SQL Server], classifier function
- classifier function [SQL Server]
- classifier function [SQL Server], overview
ms.assetid: 64c25012-7068-476f-afa2-0b4f3adde9a4
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 69b6fd10ac0adc6f76925e0d41f110b917111466
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699387"
---
# <a name="resource-governor-classifier-function"></a><span data-ttu-id="cb5df-102">Resource Governor Classifier Function</span><span class="sxs-lookup"><span data-stu-id="cb5df-102">Resource Governor Classifier Function</span></span>
  <span data-ttu-id="cb5df-103">Beim Klassifizierungsprozess der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Ressourcenkontrolle werden eingehende Sitzungen auf Grundlage der Eigenschaften der Sitzung einer Arbeitsauslastungsgruppe zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="cb5df-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resource governor classification process assigns incoming sessions to a workload group based on the characteristics of the session.</span></span> <span data-ttu-id="cb5df-104">Sie können die Klassifizierungslogik anpassen, indem Sie eine benutzerdefinierte Funktion schreiben, die als Klassifizierungsfunktion bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="cb5df-104">You can tailor the classification logic by writing a user-defined function, called a classifier function.</span></span>  
  
## <a name="classification"></a><span data-ttu-id="cb5df-105">Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="cb5df-105">Classification</span></span>  
 <span data-ttu-id="cb5df-106">Die Ressourcenkontrolle unterstützt die Klassifikation eingehender Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="cb5df-106">Resource Governor supports the classification of incoming sessions.</span></span> <span data-ttu-id="cb5df-107">Die Klassifikation basiert auf einer Reihe von benutzerspezifischen Kriterien, die in einer Funktion enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="cb5df-107">Classification is based on a set of user-written criteria contained in a function.</span></span> <span data-ttu-id="cb5df-108">Anhand der Ergebnisse der Funktionslogik kann die Ressourcenkontrolle Sitzungen in vorhandene Arbeitsauslastungsgruppen klassifizieren.</span><span class="sxs-lookup"><span data-stu-id="cb5df-108">The results of the function logic enable Resource Governor to classify sessions into existing workload groups.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cb5df-109">Die interne Arbeitsauslastungsgruppe wird mit Anforderungen gefüllt, die nur für die interne Verwendung bestimmt sind.</span><span class="sxs-lookup"><span data-stu-id="cb5df-109">The internal workload group is populated with requests that are for internal use only.</span></span> <span data-ttu-id="cb5df-110">Die zum Weiterleiten dieser Anforderungen verwendeten Kriterien können nicht geändert werden, und es können keine Anforderungen der internen Arbeitsauslastungsgruppe zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="cb5df-110">You cannot change the criteria used for routing these requests and you cannot classify requests into the internal workload group.</span></span>  
  
 <span data-ttu-id="cb5df-111">Sie können eine Skalarfunktion schreiben, die die Logik enthält, auf deren Grundlage eingehende Sitzungen einer Arbeitsauslastungsgruppe zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="cb5df-111">You can write a scalar function that contains the logic that is used to assign incoming sessions to a workload group.</span></span> <span data-ttu-id="cb5df-112">Bevor Sie diese Funktion verwenden können, müssen Sie folgende Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="cb5df-112">Before you can use this function, you must complete the following actions:</span></span>  
  
-   <span data-ttu-id="cb5df-113">Erstellen und registrieren Sie die Funktion mit der ALTER RESOURCE GOVERNOR-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="cb5df-113">Create and register the function using the ALTER RESOURCE GOVERNOR statement.</span></span> <span data-ttu-id="cb5df-114">Weitere Informationen finden Sie unter [ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-resource-governor-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="cb5df-114">For more information, see [ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-resource-governor-transact-sql).</span></span>  
  
-   <span data-ttu-id="cb5df-115">Aktualisieren Sie die Konfiguration der Ressourcenkontrolle mit der ALTER RESOURCE GOVERNOR-Anweisung und dem RECONFIGURE-Parameter.</span><span class="sxs-lookup"><span data-stu-id="cb5df-115">Update the Resource Governor configuration using the ALTER RESOURCE GOVERNOR statement with the RECONFIGURE parameter.</span></span>  
  
 <span data-ttu-id="cb5df-116">Nachdem Sie die Funktion erstellt und die Konfigurationsänderungen übernommen haben, verwendet die Klassifizierungsfunktion der Ressourcenkontrolle den von der Funktion zurückgegebenen Arbeitsauslastungsgruppennamen, um eine neue Anforderung an die entsprechende Arbeitsauslastungsgruppe zu senden.</span><span class="sxs-lookup"><span data-stu-id="cb5df-116">After you create the function and apply the configuration changes, the Resource Governor classifier will use the workload group name returned by the function to send a new request to the appropriate workload group.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="cb5df-117">Die Clientsitzung kann in einen Timeout laufen, falls die Klassifizierungsfunktion nicht innerhalb des festgelegten Timeouts für die Anmeldung abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="cb5df-117">The client session may time out if the classification function does not complete within the specified time-out for the login.</span></span> <span data-ttu-id="cb5df-118">Da der Anmeldetimeout eine Eigenschaft des Clients ist, wird dieser Timeout vom Server nicht beachtet. Eine Klassifizierungsfunktion mit langer Laufzeit kann auf dem Server zu lang andauernden verwaisten Verbindungen führen.</span><span class="sxs-lookup"><span data-stu-id="cb5df-118">Login time-out is a client property and as such, the server is unaware of a time-out. A long-running classifier function can leave the server with orphaned connections for long periods.</span></span> <span data-ttu-id="cb5df-119">Daher ist es wichtig, Klassifizierungsfunktionen zu erstellen, deren Ausführung vor einem Verbindungstimeout beendet ist.</span><span class="sxs-lookup"><span data-stu-id="cb5df-119">It is important that you create classifier functions that finish executing before a connection time-out.</span></span>  
  
 <span data-ttu-id="cb5df-120">Die benutzerdefinierte Funktion weist die folgenden Merkmale und Verhaltensweisen auf:</span><span class="sxs-lookup"><span data-stu-id="cb5df-120">The user-defined function has the following characteristics and behaviors:</span></span>  
  
-   <span data-ttu-id="cb5df-121">Die benutzerdefinierte Funktion wird für jede neue Sitzung ausgewertet, auch dann, wenn Verbindungspooling aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="cb5df-121">The user-defined function is evaluated for every new session, even when connection pooling is enabled.</span></span>  
  
-   <span data-ttu-id="cb5df-122">Die benutzerdefinierte Funktion stellt einen Arbeitsauslastungsgruppenkontext für die Sitzung bereit.</span><span class="sxs-lookup"><span data-stu-id="cb5df-122">The user-defined function gives workload group context for the session.</span></span> <span data-ttu-id="cb5df-123">Nachdem die Gruppenmitgliedschaft bestimmt ist, wird die Sitzung für ihre Lebensdauer an die Arbeitsauslastungsgruppe gebunden.</span><span class="sxs-lookup"><span data-stu-id="cb5df-123">After group membership is determined, the session is bound to the workload group for the lifetime of the session.</span></span>  
  
-   <span data-ttu-id="cb5df-124">Falls die benutzerdefinierte Funktion NULL, "default" oder den Namen einer nicht vorhandenen Gruppe zurückgibt, wird die Sitzung dem Kontext für die Standardarbeitsauslastungsgruppe zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="cb5df-124">If the user-defined function returns NULL, default, or the name of non-existent group the session is given the default workload group context.</span></span> <span data-ttu-id="cb5df-125">Die Sitzung wird dem Standardkontext auch zugeordnet, falls die Funktion fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="cb5df-125">The session is also given the default context if the function fails for any reason.</span></span>  
  
-   <span data-ttu-id="cb5df-126">Die Funktion sollte für den Serverbereich (Masterdatenbank) definiert werden.</span><span class="sxs-lookup"><span data-stu-id="cb5df-126">The function should be defined with server scope (master database).</span></span>  
  
-   <span data-ttu-id="cb5df-127">Die Bestimmung der Funktion als benutzerdefinierte Klassifizierungsfunktion wird erst nach Ausführung von ALTER RESOURCE GOVERNOR RECONFIGURE wirksam.</span><span class="sxs-lookup"><span data-stu-id="cb5df-127">The classifier user-defined function designation only takes effect after ALTER RESOURCE GOVERNOR RECONFIGURE is executed.</span></span>  
  
-   <span data-ttu-id="cb5df-128">Es kann immer nur eine benutzerdefinierte Funktion als Klassifizierungsfunktion bestimmt werden.</span><span class="sxs-lookup"><span data-stu-id="cb5df-128">Only one user-defined function can be designated as a classifier at a time.</span></span>  
  
-   <span data-ttu-id="cb5df-129">Die benutzerdefinierte Klassifizierungsfunktion kann nicht gelöscht oder geändert werden. Ihr kann lediglich der Klassifizierungsstatus entzogen werden.</span><span class="sxs-lookup"><span data-stu-id="cb5df-129">The classifier user-defined function cannot be dropped or altered unless its classifier status is removed.</span></span>  
  
-   <span data-ttu-id="cb5df-130">Falls keine benutzerdefinierte Klassifizierungsfunktion ausgewiesen wurde, werden alle Sitzungen der Standardgruppe zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="cb5df-130">In the absence of a classifier user-defined function, all sessions are classified into the default group.</span></span>  
  
-   <span data-ttu-id="cb5df-131">Die von der Klassifizierungsfunktion zurückgegebene Arbeitsauslastungsgruppe liegt außerhalb des Bereichs der Schemabindungseinschränkung.</span><span class="sxs-lookup"><span data-stu-id="cb5df-131">The workload group returned by the classifier function is outside the scope of the schema-binding restriction.</span></span> <span data-ttu-id="cb5df-132">So können Sie z. B. keine Tabelle löschen, aber Sie können eine Arbeitsauslastungsgruppe löschen.</span><span class="sxs-lookup"><span data-stu-id="cb5df-132">For example, you cannot drop a table, but you can drop a workload group.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="cb5df-133">Es wird empfohlen, die dedizierte Administratorverbindung (Dedicated Administrator Connection, DAC) auf dem Server zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="cb5df-133">We recommend enabling the Dedicated Administrator Connection (DAC) on the server.</span></span> <span data-ttu-id="cb5df-134">Die DAC unterliegt nicht der Klassifizierung der Ressourcenkontrolle und kann daher zum Überwachen einer Klassifizierungsfunktion und für die entsprechende Problembehandlung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cb5df-134">The DAC is not subject to Resource Governor classification and can be used to monitor and troubleshoot a classifier function.</span></span> <span data-ttu-id="cb5df-135">Weitere Informationen finden Sie unter [Diagnoseverbindung für Datenbankadministratoren](../../database-engine/configure-windows/diagnostic-connection-for-database-administrators.md).</span><span class="sxs-lookup"><span data-stu-id="cb5df-135">For more information, see [Diagnostic Connection for Database Administrators](../../database-engine/configure-windows/diagnostic-connection-for-database-administrators.md).</span></span> <span data-ttu-id="cb5df-136">Wenn keine DAC für die Problembehandlung verfügbar ist, können Sie alternativ das System im Einzelbenutzermodus neu starten.</span><span class="sxs-lookup"><span data-stu-id="cb5df-136">If a DAC is not available for troubleshooting, the other option is to restart the system in single user mode.</span></span> <span data-ttu-id="cb5df-137">Der Einzelbenutzermodus unterliegt zwar nicht der Klassifizierung, allerdings haben Sie in diesem Modus nicht die Möglichkeit, die Klassifizierung der Ressourcenkontrolle während der Ausführung zu diagnostizieren.</span><span class="sxs-lookup"><span data-stu-id="cb5df-137">Although single user mode is not subject to classification, it does not give you the ability to diagnose Resource Governor classification while it is running.</span></span>  
  
### <a name="classification-process"></a><span data-ttu-id="cb5df-138">Klassifizierungsprozess</span><span class="sxs-lookup"><span data-stu-id="cb5df-138">Classification Process</span></span>  
 <span data-ttu-id="cb5df-139">Im Kontext der Ressourcenkontrolle besteht der Anmeldevorgang für eine Sitzung aus den folgenden Schritten:</span><span class="sxs-lookup"><span data-stu-id="cb5df-139">In the context of Resource Governor, the login process for a session consists of the following steps:</span></span>  
  
1.  <span data-ttu-id="cb5df-140">Anmeldeauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="cb5df-140">Login authentication</span></span>  
  
2.  <span data-ttu-id="cb5df-141">Ausführung von LOGON-Triggern</span><span class="sxs-lookup"><span data-stu-id="cb5df-141">LOGON trigger execution</span></span>  
  
3.  <span data-ttu-id="cb5df-142">Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="cb5df-142">Classification</span></span>  
  
 <span data-ttu-id="cb5df-143">Wenn die Klassifizierung gestartet wird, führt die Ressourcenkontrolle die Klassifizierungsfunktion aus und verwendet den von der Funktion zurückgegebenen Wert, um Anforderungen an die entsprechende Arbeitsauslastungsgruppe zu senden.</span><span class="sxs-lookup"><span data-stu-id="cb5df-143">When classification starts, Resource Governor executes the classifier function and uses the value returned by the function to send requests to the appropriate workload group.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cb5df-144">Informationen zum Ausführen der Klassifizierungsfunktion und der LOGON-Trigger werden in [sys.dm_exec_sessions](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-sessions-transact-sql) und [sys.dm_exec_requests](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-requests-transact-sql)verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="cb5df-144">Information about the execution of the classifier function and LOGON triggers is exposed in [sys.dm_exec_sessions](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-sessions-transact-sql) and [sys.dm_exec_requests](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-requests-transact-sql).</span></span>  
  
## <a name="classification-function-tasks"></a><span data-ttu-id="cb5df-145">Tasks der Klassifizierungsfunktion</span><span class="sxs-lookup"><span data-stu-id="cb5df-145">Classification Function Tasks</span></span>  
  
|<span data-ttu-id="cb5df-146">Taskbeschreibung</span><span class="sxs-lookup"><span data-stu-id="cb5df-146">Task Description</span></span>|<span data-ttu-id="cb5df-147">Thema</span><span class="sxs-lookup"><span data-stu-id="cb5df-147">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="cb5df-148">Beschreibt, wie benutzerdefinierte Klassifizierungsfunktionen erstellt und getestet werden.</span><span class="sxs-lookup"><span data-stu-id="cb5df-148">Describes how to create and test a classifier user-defined function.</span></span>|[<span data-ttu-id="cb5df-149">Erstellen und Testen einer benutzerdefinierten Klassifizierungsfunktion</span><span class="sxs-lookup"><span data-stu-id="cb5df-149">Create and Test a Classifier User-Defined Function</span></span>](create-and-test-a-classifier-user-defined-function.md)|  
  
## <a name="see-also"></a><span data-ttu-id="cb5df-150">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cb5df-150">See Also</span></span>  
 <span data-ttu-id="cb5df-151">[Resource Governor](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="cb5df-151">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="cb5df-152">[Aktivieren der Ressourcenkontrolle](enable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="cb5df-152">[Enable Resource Governor](enable-resource-governor.md) </span></span>  
 <span data-ttu-id="cb5df-153">[Ressourcenpool für die Ressourcenkontrolle](resource-governor-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="cb5df-153">[Resource Governor Resource Pool](resource-governor-resource-pool.md) </span></span>  
 <span data-ttu-id="cb5df-154">[Arbeitsauslastungsgruppe der Ressourcenkontrolle](resource-governor-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="cb5df-154">[Resource Governor Workload Group](resource-governor-workload-group.md) </span></span>  
 <span data-ttu-id="cb5df-155">[Konfigurieren der Ressourcenkontrolle mit einer Vorlage](configure-resource-governor-using-a-template.md) </span><span class="sxs-lookup"><span data-stu-id="cb5df-155">[Configure Resource Governor Using a Template](configure-resource-governor-using-a-template.md) </span></span>  
 [<span data-ttu-id="cb5df-156">Anzeigen der Eigenschaften der Ressourcenkontrolle</span><span class="sxs-lookup"><span data-stu-id="cb5df-156">View Resource Governor Properties</span></span>](view-resource-governor-properties.md)  
  
  
