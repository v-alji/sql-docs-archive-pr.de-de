---
title: Kennwortrichtlinie | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- ALTER LOGIN statement
- passwords [SQL Server], policy enforcement
- logins [SQL Server], passwords
- CHECK_EXPIRATION option
- complex passwords [SQL Server]
- passwords [SQL Server], expiration
- manual bad password count resets
- MUST_CHANGE option
- expiration [SQL Server]
- expired password [SQL Server]
- symbols [SQL Server]
- NetValidatePasswordPolicy() API
- passwords [SQL Server]
- password policy [SQL Server]
- resetting bad password counts
- security [SQL Server], passwords
- CHECK_POLICY option
- passwords [SQL Server], symbols
- bad password counts
- passwords [SQL Server], complexity
- characters [SQL Server], password policies
ms.assetid: c0040c0a-a18f-45b9-9c40-0625685649b1
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 902c46b4609a32139450843414a3c4d97b52fcf7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609760"
---
# <a name="password-policy"></a><span data-ttu-id="60637-102">Kennwortrichtlinie</span><span class="sxs-lookup"><span data-stu-id="60637-102">Password Policy</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="60637-103">kann Mechanismen der Windows-Kennwortrichtlinien verwenden.</span><span class="sxs-lookup"><span data-stu-id="60637-103">can use Windows password policy mechanisms.</span></span> <span data-ttu-id="60637-104">Die Kennwortrichtlinie gilt für eine Anmeldung, die die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Authentifizierung verwendet, und für einen eigenständige Datenbankbenutzer mit Kennwort.</span><span class="sxs-lookup"><span data-stu-id="60637-104">The password policy applies to a login that uses [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] authentication, and to a contained database user with password.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="60637-105">kann die gleichen Komplexitäts- und Ablaufrichtlinien anwenden, die in Windows für in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]verwendete Kennwörter verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="60637-105">can apply the same complexity and expiration policies used in Windows to passwords used inside [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="60637-106">Diese Funktion basiert auf der `NetValidatePasswordPolicy` -API.</span><span class="sxs-lookup"><span data-stu-id="60637-106">This functionality depends on the `NetValidatePasswordPolicy` API.</span></span>  
  
## <a name="password-complexity"></a><span data-ttu-id="60637-107">Kennwortkomplexität</span><span class="sxs-lookup"><span data-stu-id="60637-107">Password Complexity</span></span>  
 <span data-ttu-id="60637-108">Richtlinien zur Kennwortkomplexität werden als Maßnahme gegen Brute Force-Angriffe entworfen. Dabei wird die Anzahl der möglichen Kennwörter erhöht.</span><span class="sxs-lookup"><span data-stu-id="60637-108">Password complexity policies are designed to deter brute force attacks by increasing the number of possible passwords.</span></span> <span data-ttu-id="60637-109">Wenn eine Richtlinie zur Kennwortkomplexität erzwungen wird, müssen neue Kennwörter die folgenden Richtlinien erfüllen:</span><span class="sxs-lookup"><span data-stu-id="60637-109">When password complexity policy is enforced, new passwords must meet the following guidelines:</span></span>  
  
-   <span data-ttu-id="60637-110">Das Kennwort enthält nicht den Kontonamen des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="60637-110">The password does not contain the account name of the user.</span></span>  
  
-   <span data-ttu-id="60637-111">Das Kennwort ist wenigstens acht Zeichen lang.</span><span class="sxs-lookup"><span data-stu-id="60637-111">The password is at least eight characters long.</span></span>  
  
-   <span data-ttu-id="60637-112">Das Kennwort enthält Zeichen aus drei der folgenden vier Kategorien:</span><span class="sxs-lookup"><span data-stu-id="60637-112">The password contains characters from three of the following four categories:</span></span>  
  
    -   <span data-ttu-id="60637-113">Lateinische Großbuchstaben (A - Z)</span><span class="sxs-lookup"><span data-stu-id="60637-113">Latin uppercase letters (A through Z)</span></span>  
  
    -   <span data-ttu-id="60637-114">Lateinische Kleinbuchstaben (a - z)</span><span class="sxs-lookup"><span data-stu-id="60637-114">Latin lowercase letters (a through z)</span></span>  
  
    -   <span data-ttu-id="60637-115">10 Grundziffern (0 - 9)</span><span class="sxs-lookup"><span data-stu-id="60637-115">Base 10 digits (0 through 9)</span></span>  
  
    -   <span data-ttu-id="60637-116">Nicht alphanumerische Zeichen, wie z. B.: Ausrufezeichen (!), Dollarzeichen ($), Nummernzeichen (#) oder Prozentzeichen (%)</span><span class="sxs-lookup"><span data-stu-id="60637-116">Non-alphanumeric characters such as: exclamation point (!), dollar sign ($), number sign (#), or percent (%).</span></span>  
  
 <span data-ttu-id="60637-117">Kennwörter können bis zu 128 Zeichen lang sein.</span><span class="sxs-lookup"><span data-stu-id="60637-117">Passwords can be up to 128 characters long.</span></span> <span data-ttu-id="60637-118">Sie sollten möglichst lange und komplexe Kennwörter verwenden.</span><span class="sxs-lookup"><span data-stu-id="60637-118">You should use passwords that are as long and complex as possible.</span></span>  
  
## <a name="password-expiration"></a><span data-ttu-id="60637-119">Ablauf des Kennworts</span><span class="sxs-lookup"><span data-stu-id="60637-119">Password Expiration</span></span>  
 <span data-ttu-id="60637-120">Richtlinien zum Ablauf von Kennwörtern werden verwendet, um die Lebensdauer von Kennwörtern zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="60637-120">Password expiration policies are used to manage the lifespan of a password.</span></span> <span data-ttu-id="60637-121">Wenn [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] die Richtlinie zum Ablauf von Kennwörtern durchsetzt, werden Benutzer daran erinnert, alte Kennwörter zu ändern. Konten mit abgelaufenen Kennwörtern werden deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="60637-121">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] enforces password expiration policy, users are reminded to change old passwords, and accounts that have expired passwords are disabled.</span></span>  
  
## <a name="policy-enforcement"></a><span data-ttu-id="60637-122">Richtliniendurchsetzung</span><span class="sxs-lookup"><span data-stu-id="60637-122">Policy Enforcement</span></span>  
 <span data-ttu-id="60637-123">Das Erzwingen der Kennwortrichtlinie kann für jede SQL Server-Anmeldung einzeln konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="60637-123">The enforcement of password policy can be configured separately for each SQL Server login.</span></span> <span data-ttu-id="60637-124">Verwenden Sie [ALTER LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-login-transact-sql) , um die Kennwortrichtlinienoptionen für eine SQL Server-Anmeldung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="60637-124">Use [ALTER LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-login-transact-sql) to configure the password policy options of a SQL Server login.</span></span> <span data-ttu-id="60637-125">Die folgenden Regeln gelten für die Konfiguration zur Erzwingung der Kennwortrichtlinie:</span><span class="sxs-lookup"><span data-stu-id="60637-125">The following rules apply to the configuration of password policy enforcement:</span></span>  
  
-   <span data-ttu-id="60637-126">Wenn CHECK_POLICY in ON geändert wird, kommt es zu folgenden Verhaltensweisen:</span><span class="sxs-lookup"><span data-stu-id="60637-126">When CHECK_POLICY is changed to ON, the following behaviors occur:</span></span>  
  
    -   <span data-ttu-id="60637-127">Für CHECK_EXPIRATION wird ebenfalls ON festgelegt, es sei denn, der Wert OFF wurde ausdrücklich festgelegt.</span><span class="sxs-lookup"><span data-stu-id="60637-127">CHECK_EXPIRATION is also set to ON unless it is explicitly set to OFF.</span></span>  
  
    -   <span data-ttu-id="60637-128">Der Kennwortverlauf wird mit dem Wert des aktuellen Kennworthashes initialisiert.</span><span class="sxs-lookup"><span data-stu-id="60637-128">The password history is initialized with the value of the current password hash.</span></span>  
  
    -   <span data-ttu-id="60637-129">**Kontosperrdauer**, **Kontensperrungsschwelle**und **Zurücksetzungsdauer des Kontosperrungszählers** sind ebenfalls aktiviert.</span><span class="sxs-lookup"><span data-stu-id="60637-129">**Account lockout duration**, **account lockout threshold**, and **reset account lockout counter after** are also enabled.</span></span>  
  
-   <span data-ttu-id="60637-130">Wenn CHECK_POLICY in OFF geändert wird, kommt es zu folgenden Verhaltensweisen:</span><span class="sxs-lookup"><span data-stu-id="60637-130">When CHECK_POLICY is changed to OFF, the following behaviors occur:</span></span>  
  
    -   <span data-ttu-id="60637-131">CHECK_EXPIRATION wird ebenfalls auf OFF festgelegt.</span><span class="sxs-lookup"><span data-stu-id="60637-131">CHECK_EXPIRATION is also set to OFF.</span></span>  
  
    -   <span data-ttu-id="60637-132">Der Kennwortverlauf wird gelöscht.</span><span class="sxs-lookup"><span data-stu-id="60637-132">The password history is cleared.</span></span>  
  
    -   <span data-ttu-id="60637-133">Der Wert von `lockout_time` wird zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="60637-133">The value of `lockout_time` is reset.</span></span>  
  
 <span data-ttu-id="60637-134">Einige Kombinationen von Richtlinienoptionen werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="60637-134">Some combinations of policy options are not supported.</span></span>  
  
-   <span data-ttu-id="60637-135">Falls MUST_CHANGE angegeben wird, müssen CHECK_EXPIRATION und CHECK_POLICY auf ON festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="60637-135">If MUST_CHANGE is specified, CHECK_EXPIRATION and CHECK_POLICY must be set to ON.</span></span> <span data-ttu-id="60637-136">Andernfalls erzeugt die Anweisung einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="60637-136">Otherwise, the statement will fail.</span></span>  
  
-   <span data-ttu-id="60637-137">Falls CHECK_POLICY auf OFF festgelegt ist, kann CHECK_EXPIRATION nicht auf ON festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="60637-137">If CHECK_POLICY is set to OFF, CHECK_EXPIRATION cannot be set to ON.</span></span> <span data-ttu-id="60637-138">Eine ALTER LOGIN-Anweisung mit dieser Kombination von Optionen erzeugt einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="60637-138">An ALTER LOGIN statement that has this combination of options will fail.</span></span>  
  
 <span data-ttu-id="60637-139">Durch Festlegen von CHECK_POLICY = ON wird die Erstellung von Kennwörtern mit folgenden Eigenschaften verhindert:</span><span class="sxs-lookup"><span data-stu-id="60637-139">Setting CHECK_POLICY = ON will prevent the creation of passwords that are:</span></span>  
  
-   <span data-ttu-id="60637-140">NULL-Werte oder leere Kennwörter</span><span class="sxs-lookup"><span data-stu-id="60637-140">Null or empty</span></span>  
  
-   <span data-ttu-id="60637-141">Kennwörter, die dem Computer- oder Anmeldenamen entsprechen</span><span class="sxs-lookup"><span data-stu-id="60637-141">Same as name of computer or login</span></span>  
  
-   <span data-ttu-id="60637-142">Eines der folgenden Kennwörter: "kennwort", "admin", "administrator", "sa", "sysadmin"</span><span class="sxs-lookup"><span data-stu-id="60637-142">Any of the following: "password", "admin", "administrator", "sa", "sysadmin"</span></span>  
  
 <span data-ttu-id="60637-143">Die Sicherheitsrichtlinie kann in Windows festgelegt oder von der Domäne abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="60637-143">The security policy might be set in Windows, or might be received from the domain.</span></span> <span data-ttu-id="60637-144">Um die Kennwortrichtlinie auf dem Computer anzuzeigen, verwenden Sie das MMC-Snap-In „Lokale Sicherheitsrichtlinie“ (**secpol.msc**).</span><span class="sxs-lookup"><span data-stu-id="60637-144">To view the password policy on the computer, use the Local Security Policy MMC snap-in (**secpol.msc**).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="60637-145">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="60637-145">Related Tasks</span></span>  
 [<span data-ttu-id="60637-146">CREATE LOGIN &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="60637-146">CREATE LOGIN &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-login-transact-sql)  
  
 [<span data-ttu-id="60637-147">ALTER LOGIN &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="60637-147">ALTER LOGIN &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-login-transact-sql)  
  
 [<span data-ttu-id="60637-148">CREATE USER &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="60637-148">CREATE USER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-user-transact-sql)  
  
 [<span data-ttu-id="60637-149">ALTER USER &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="60637-149">ALTER USER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-user-transact-sql)  
  
 [<span data-ttu-id="60637-150">Erstellen eines Anmeldenamens</span><span class="sxs-lookup"><span data-stu-id="60637-150">Create a Login</span></span>](authentication-access/create-a-login.md)  
  
 [<span data-ttu-id="60637-151">Erstellen eines Datenbankbenutzers</span><span class="sxs-lookup"><span data-stu-id="60637-151">Create a Database User</span></span>](authentication-access/create-a-database-user.md)  
  
## <a name="related-content"></a><span data-ttu-id="60637-152">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="60637-152">Related Content</span></span>  
 [<span data-ttu-id="60637-153">Sichere Kennwörter</span><span class="sxs-lookup"><span data-stu-id="60637-153">Strong Passwords</span></span>](strong-passwords.md)  
  
  
