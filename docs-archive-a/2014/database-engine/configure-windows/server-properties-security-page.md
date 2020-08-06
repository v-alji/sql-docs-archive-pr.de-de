---
title: Servereigenschaften (Seite „Sicherheit“) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.serverproperties.security.f1
ms.assetid: b8a131c7-e7bd-4203-bf26-234f1ebfe622
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5f45c0a04a0d7cc627901d8de24175f1d63a99fe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622882"
---
# <a name="server-properties-security-page"></a><span data-ttu-id="f83ae-102">Servereigenschaften (Seite Sicherheit)</span><span class="sxs-lookup"><span data-stu-id="f83ae-102">Server Properties (Security Page)</span></span>
  <span data-ttu-id="f83ae-103">Auf dieser Seite können Sie die Optionen für die Serversicherheit anzeigen oder bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="f83ae-103">Use this page to view or modify your server security options.</span></span>  
  
## <a name="server-authentication"></a><span data-ttu-id="f83ae-104">Serverauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="f83ae-104">Server Authentication</span></span>  
 <span data-ttu-id="f83ae-105">**Windows-Authentifizierungsmodus**</span><span class="sxs-lookup"><span data-stu-id="f83ae-105">**Windows Authentication mode**</span></span>  
 <span data-ttu-id="f83ae-106">Verwendet die Windows-Authentifizierung zum Überprüfen von Verbindungsversuchen.</span><span class="sxs-lookup"><span data-stu-id="f83ae-106">Uses Windows Authentication to validate attempted connections.</span></span> <span data-ttu-id="f83ae-107">Wenn beim Ändern des Sicherheitsmodus kein Kennwort für **sa** festgelegt ist, wird der Benutzer zur Eingabe des Kennworts für **sa** aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="f83ae-107">If the **sa** password is blank when the security mode is being changed, the user is prompted to enter an **sa** password.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f83ae-108">Die Windows-Authentifizierung bietet deutlich mehr Sicherheit als die SQL Server-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="f83ae-108">Windows Authentication is much more secure than SQL Server Authentication.</span></span> <span data-ttu-id="f83ae-109">Verwenden Sie nach Möglichkeit die Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="f83ae-109">When possible, you should use Windows Authentication.</span></span>  
  
 <span data-ttu-id="f83ae-110">**SQL Server- und Windows-Authentifizierungsmodus**</span><span class="sxs-lookup"><span data-stu-id="f83ae-110">**SQL Server and Windows Authentication mode**</span></span>  
 <span data-ttu-id="f83ae-111">Verwendet aus Gründen der Abwärtskompatibilität mit früheren Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]einen gemischten Authentifizierungsmodus zum Überprüfen von Verbindungsversuchen.</span><span class="sxs-lookup"><span data-stu-id="f83ae-111">Uses mixed mode authentication to verify attempted connections, for backward compatibility with earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f83ae-112">Wenn beim Ändern des Sicherheitsmodus kein Kennwort für **sa** festgelegt ist, wird der Benutzer zur Eingabe des Kennworts für **sa** aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="f83ae-112">If the **sa** password is blank when the security mode is being changed, the user is prompted to enter an **sa** password.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f83ae-113">Das Ändern der Sicherheitskonfiguration erfordert einen Neustart des Diensts.</span><span class="sxs-lookup"><span data-stu-id="f83ae-113">Changing the security configuration requires a restart of the service.</span></span> <span data-ttu-id="f83ae-114">Beim Ändern des SQL Server- und Windows-Authentifizierungsmodus wird das SA-Konto nicht automatisch aktiviert.</span><span class="sxs-lookup"><span data-stu-id="f83ae-114">When changing the Server Authentication to SQL Server and Windows Authentication mode the SA account is not automatically enabled.</span></span> <span data-ttu-id="f83ae-115">Zum Verwenden des SA-Kontos führen Sie [ALTER LOGIN](/sql/t-sql/statements/alter-login-transact-sql) mit der Option ENABLE aus.</span><span class="sxs-lookup"><span data-stu-id="f83ae-115">To use the SA account, execute [ALTER LOGIN](/sql/t-sql/statements/alter-login-transact-sql) with the ENABLE option.</span></span>  
  
## <a name="login-auditing"></a><span data-ttu-id="f83ae-116">Anmeldungsüberwachung</span><span class="sxs-lookup"><span data-stu-id="f83ae-116">Login Auditing</span></span>  
 <span data-ttu-id="f83ae-117">**None**</span><span class="sxs-lookup"><span data-stu-id="f83ae-117">**None**</span></span>  
 <span data-ttu-id="f83ae-118">Schaltet die Anmeldungsüberwachung ab.</span><span class="sxs-lookup"><span data-stu-id="f83ae-118">Turns off login auditing.</span></span>  
  
 <span data-ttu-id="f83ae-119">**Nur fehlgeschlagene Anmeldungen**</span><span class="sxs-lookup"><span data-stu-id="f83ae-119">**Failed logins only**</span></span>  
 <span data-ttu-id="f83ae-120">Überwacht nur nicht erfolgreiche Anmeldungen.</span><span class="sxs-lookup"><span data-stu-id="f83ae-120">Audits unsuccessful logins only.</span></span>  
  
 <span data-ttu-id="f83ae-121">**Nur erfolgreiche Anmeldungen**</span><span class="sxs-lookup"><span data-stu-id="f83ae-121">**Successful logins only**</span></span>  
 <span data-ttu-id="f83ae-122">Überwacht nur erfolgreiche Anmeldungen.</span><span class="sxs-lookup"><span data-stu-id="f83ae-122">Audits successful logins only.</span></span>  
  
 <span data-ttu-id="f83ae-123">**Erfolgreiche und fehlgeschlagene Anmeldungen**</span><span class="sxs-lookup"><span data-stu-id="f83ae-123">**Both failed and successful logins**</span></span>  
 <span data-ttu-id="f83ae-124">Überwacht alle Anmeldungsversuche.</span><span class="sxs-lookup"><span data-stu-id="f83ae-124">Audits all login attempts.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f83ae-125">Eine Änderung der Überwachungsebene erfordert einen Neustart des Diensts.</span><span class="sxs-lookup"><span data-stu-id="f83ae-125">Changing the audit level requires restarting the service.</span></span>  
  
## <a name="server-proxy-account"></a><span data-ttu-id="f83ae-126">Serverproxykonto</span><span class="sxs-lookup"><span data-stu-id="f83ae-126">Server Proxy Account</span></span>  
 <span data-ttu-id="f83ae-127">**Serverproxykonto aktivieren**</span><span class="sxs-lookup"><span data-stu-id="f83ae-127">**Enable server proxy account**</span></span>  
 <span data-ttu-id="f83ae-128">Aktiviert ein Konto für die Verwendung durch **xp_cmdshell**.</span><span class="sxs-lookup"><span data-stu-id="f83ae-128">Enables an account for use by **xp_cmdshell**.</span></span> <span data-ttu-id="f83ae-129">Proxykonten ermöglichen den Identitätswechsel bei Anmeldungen, Serverrollen und Datenbankrollen, wenn ein Betriebssystembefehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f83ae-129">Proxy accounts allow for the impersonation of logins, server roles, and database roles when an operating system command is being executed.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="f83ae-130">Die vom Serverproxykonto verwendete Anmeldung sollte nur so viele Privilegien besitzen, wie zur Ausführung der vorgesehenen Arbeit erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="f83ae-130">The login used by the server proxy account should have the least privileges required to perform the intended work.</span></span> <span data-ttu-id="f83ae-131">Zu großzügige Privilegien für das Proxykonto können von einem Benutzer mit bösartigen Absichten zur Beeinträchtigung der Systemsicherheit ausgenutzt werden.</span><span class="sxs-lookup"><span data-stu-id="f83ae-131">Excessive privileges for the proxy account could be used by a malicious user to compromise your system security.</span></span>  
  
 <span data-ttu-id="f83ae-132">**Proxykonto**</span><span class="sxs-lookup"><span data-stu-id="f83ae-132">**Proxy account**</span></span>  
 <span data-ttu-id="f83ae-133">Geben Sie das verwendete Proxykonto an.</span><span class="sxs-lookup"><span data-stu-id="f83ae-133">Specify the proxy account used.</span></span>  
  
 <span data-ttu-id="f83ae-134">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="f83ae-134">**Password**</span></span>  
 <span data-ttu-id="f83ae-135">Geben Sie das Kennwort für das Proxykonto ein.</span><span class="sxs-lookup"><span data-stu-id="f83ae-135">Specify the password for the proxy account.</span></span>  
  
## <a name="options"></a><span data-ttu-id="f83ae-136">Tastatur</span><span class="sxs-lookup"><span data-stu-id="f83ae-136">Options</span></span>  
 <span data-ttu-id="f83ae-137">**C2-Überwachungs-Ablaufverfolgung aktivieren**</span><span class="sxs-lookup"><span data-stu-id="f83ae-137">**Enable C2 audit tracing**</span></span>  
 <span data-ttu-id="f83ae-138">Überwacht alle Zugriffsversuche auf Anweisungen und Objekte und zeichnet diese in einer Datei im Verzeichnis \MSSQL\Data (bei Standardinstanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]) bzw. \MSSQL$*Instanzname*\Data (bei benannten Instanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]) auf.</span><span class="sxs-lookup"><span data-stu-id="f83ae-138">Audits all attempts to access statements and objects and records them to a file in the \MSSQL\Data directory for default instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], or the \MSSQL$*instancename*\Data directory for named instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f83ae-139">Weitere Informationen finden Sie unter [C2-Überwachungsmodus (Serverkonfigurationsoption)](c2-audit-mode-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="f83ae-139">For more information, see [c2 audit mode Server Configuration Option](c2-audit-mode-server-configuration-option.md).</span></span>  
  
 <span data-ttu-id="f83ae-140">**Datenbankübergreifende Besitzverkettung**</span><span class="sxs-lookup"><span data-stu-id="f83ae-140">**Cross database ownership chaining**</span></span>  
 <span data-ttu-id="f83ae-141">Wählen Sie diese Option aus, um es der Datenbank zu ermöglichen, Quelle oder Ziel einer datenbankübergreifenden Besitzverkettung zu sein.</span><span class="sxs-lookup"><span data-stu-id="f83ae-141">Select to allow the database to be the source or target of a cross-database ownership chain.</span></span> <span data-ttu-id="f83ae-142">Weitere Informationen finden Sie unter [Datenbankübergreifende Besitzverkettung (Serverkonfigurationsoption)](cross-db-ownership-chaining-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="f83ae-142">For more information, see [cross db ownership chaining Server Configuration Option](cross-db-ownership-chaining-server-configuration-option.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f83ae-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f83ae-143">See Also</span></span>  
 [<span data-ttu-id="f83ae-144">Serverkonfigurationsoptionen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f83ae-144">Server Configuration Options &#40;SQL Server&#41;</span></span>](server-configuration-options-sql-server.md)  
  
  
