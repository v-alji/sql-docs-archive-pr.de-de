---
title: Sicherungsfähige Elemente | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/14/2015
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.roleproperties.selectobject.f1
helpviewer_keywords:
- securables [SQL Server]
- schemas [SQL Server], securables
- database securables [SQL Server]
- hierarchies [SQL Server], securables
- server securables [SQL Server]
ms.assetid: bfa748f0-70b0-453c-870a-04b7b205b9ff
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: ff2aaba72e2e5489694d31b35e594622c099acab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697698"
---
# <a name="securables"></a><span data-ttu-id="61f64-102">Sicherungsfähige Elemente</span><span class="sxs-lookup"><span data-stu-id="61f64-102">Securables</span></span>
  <span data-ttu-id="61f64-103">Als sicherungsfähige Elemente werden Ressourcen bezeichnet, auf die der Zugriff durch das Autorisierungssystem von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] reguliert wird.</span><span class="sxs-lookup"><span data-stu-id="61f64-103">Securables are the resources to which the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] authorization system regulates access.</span></span> <span data-ttu-id="61f64-104">Eine Tabelle ist z. B. ein sicherungsfähiges Element.</span><span class="sxs-lookup"><span data-stu-id="61f64-104">For example, a table is a securable.</span></span> <span data-ttu-id="61f64-105">Bestimmte sicherungsfähige Elemente können sich innerhalb anderer Elemente befinden. Dadurch entstehen geschachtelte Hierarchien, so genannte "Bereiche", die selbst sicherungsfähig sind.</span><span class="sxs-lookup"><span data-stu-id="61f64-105">Some securables can be contained within others, creating nested hierarchies called "scopes" that can themselves be secured.</span></span> <span data-ttu-id="61f64-106">Sicherungsfähige Bereiche sind **Server**, **Datenbank**und **Schema**.</span><span class="sxs-lookup"><span data-stu-id="61f64-106">The securable scopes are **server**, **database**, and **schema**.</span></span>  
  
## <a name="securable-scope-server"></a><span data-ttu-id="61f64-107">Sicherungsfähiger Bereich: Server</span><span class="sxs-lookup"><span data-stu-id="61f64-107">Securable scope: Server</span></span>  
 <span data-ttu-id="61f64-108">Der sicherungsfähige Bereich **Server** enthält die folgenden sicherungsfähigen Elemente:</span><span class="sxs-lookup"><span data-stu-id="61f64-108">The **server** securable scope contains the following securables:</span></span>  
  
-   <span data-ttu-id="61f64-109">Verfügbarkeitsgruppe</span><span class="sxs-lookup"><span data-stu-id="61f64-109">Availability group</span></span>  
  
-   <span data-ttu-id="61f64-110">Endpunkt</span><span class="sxs-lookup"><span data-stu-id="61f64-110">Endpoint</span></span>  
  
-   <span data-ttu-id="61f64-111">Anmeldename</span><span class="sxs-lookup"><span data-stu-id="61f64-111">Login</span></span>  
  
-   <span data-ttu-id="61f64-112">Serverrolle</span><span class="sxs-lookup"><span data-stu-id="61f64-112">Server role</span></span>  
  
-   <span data-ttu-id="61f64-113">Datenbank</span><span class="sxs-lookup"><span data-stu-id="61f64-113">Database</span></span>  
  
## <a name="securable-scope-database"></a><span data-ttu-id="61f64-114">Sicherungsfähiger Bereich: Datenbank</span><span class="sxs-lookup"><span data-stu-id="61f64-114">Securable scope: Database</span></span>  
 <span data-ttu-id="61f64-115">Der sicherungsfähige Bereich **Datenbank** enthält die folgenden sicherungsfähigen Elemente:</span><span class="sxs-lookup"><span data-stu-id="61f64-115">The **database** securable scope contains the following securables:</span></span>  
  
-   <span data-ttu-id="61f64-116">Anwendungsrolle</span><span class="sxs-lookup"><span data-stu-id="61f64-116">Application role</span></span>  
  
-   <span data-ttu-id="61f64-117">Assembly</span><span class="sxs-lookup"><span data-stu-id="61f64-117">Assembly</span></span>  
  
-   <span data-ttu-id="61f64-118">Asymmetrischer Schlüssel</span><span class="sxs-lookup"><span data-stu-id="61f64-118">Asymmetric key</span></span>  
  
-   <span data-ttu-id="61f64-119">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="61f64-119">Certificate</span></span>  
  
-   <span data-ttu-id="61f64-120">Vertrag</span><span class="sxs-lookup"><span data-stu-id="61f64-120">Contract</span></span>  
  
-   <span data-ttu-id="61f64-121">Volltextkatalog</span><span class="sxs-lookup"><span data-stu-id="61f64-121">Fulltext catalog</span></span>  
  
-   <span data-ttu-id="61f64-122">Volltextstoppliste</span><span class="sxs-lookup"><span data-stu-id="61f64-122">Fulltext stoplist</span></span>  
  
-   <span data-ttu-id="61f64-123">Nachrichtentyp</span><span class="sxs-lookup"><span data-stu-id="61f64-123">Message type</span></span>  
  
-   <span data-ttu-id="61f64-124">Remotedienstbindung</span><span class="sxs-lookup"><span data-stu-id="61f64-124">Remote Service Binding</span></span>  
  
-   <span data-ttu-id="61f64-125">(Datenbank-)Rolle</span><span class="sxs-lookup"><span data-stu-id="61f64-125">(Database) Role</span></span>  
  
-   <span data-ttu-id="61f64-126">Route</span><span class="sxs-lookup"><span data-stu-id="61f64-126">Route</span></span>  
  
-   <span data-ttu-id="61f64-127">Schema</span><span class="sxs-lookup"><span data-stu-id="61f64-127">Schema</span></span>  
  
-   <span data-ttu-id="61f64-128">Sucheigenschaftenliste</span><span class="sxs-lookup"><span data-stu-id="61f64-128">Search property list</span></span>  
  
-   <span data-ttu-id="61f64-129">Dienst</span><span class="sxs-lookup"><span data-stu-id="61f64-129">Service</span></span>  
  
-   <span data-ttu-id="61f64-130">Symmetrischer Schlüssel</span><span class="sxs-lookup"><span data-stu-id="61f64-130">Symmetric key</span></span>  
  
-   <span data-ttu-id="61f64-131">Benutzer</span><span class="sxs-lookup"><span data-stu-id="61f64-131">User</span></span>  
  
## <a name="securable-scope-schema"></a><span data-ttu-id="61f64-132">Sicherungsfähiger Bereich: Schema</span><span class="sxs-lookup"><span data-stu-id="61f64-132">Securable scope: Schema</span></span>  
 <span data-ttu-id="61f64-133">Der sicherungsfähige Bereich **Schema** enthält die folgenden sicherungsfähigen Elemente:</span><span class="sxs-lookup"><span data-stu-id="61f64-133">The **schema** securable scope contains the following securables:</span></span>  
  
-   <span data-ttu-id="61f64-134">type</span><span class="sxs-lookup"><span data-stu-id="61f64-134">Type</span></span>  
  
-   <span data-ttu-id="61f64-135">XML-Schemaauflistung</span><span class="sxs-lookup"><span data-stu-id="61f64-135">XML schema collection</span></span>  
  
-   <span data-ttu-id="61f64-136">Objekt: Die Objektklasse enthält die folgenden Elemente:</span><span class="sxs-lookup"><span data-stu-id="61f64-136">Object - The object class has the following members:</span></span>  
  
    -   <span data-ttu-id="61f64-137">Aggregat</span><span class="sxs-lookup"><span data-stu-id="61f64-137">Aggregate</span></span>  
  
    -   <span data-ttu-id="61f64-138">Funktion</span><span class="sxs-lookup"><span data-stu-id="61f64-138">Function</span></span>  
  
    -   <span data-ttu-id="61f64-139">Verfahren</span><span class="sxs-lookup"><span data-stu-id="61f64-139">Procedure</span></span>  
  
    -   <span data-ttu-id="61f64-140">Warteschlange</span><span class="sxs-lookup"><span data-stu-id="61f64-140">Queue</span></span>  
  
    -   <span data-ttu-id="61f64-141">Synonym</span><span class="sxs-lookup"><span data-stu-id="61f64-141">Synonym</span></span>  
  
    -   <span data-ttu-id="61f64-142">Tabelle</span><span class="sxs-lookup"><span data-stu-id="61f64-142">Table</span></span>  
  
    -   <span data-ttu-id="61f64-143">Sicht</span><span class="sxs-lookup"><span data-stu-id="61f64-143">View</span></span>  
  
## <a name="controlling-access-to-a-securable"></a><span data-ttu-id="61f64-144">Steuern von Zugriff auf ein sicherungsfähiges Element</span><span class="sxs-lookup"><span data-stu-id="61f64-144">Controlling Access to a Securable</span></span>  
 <span data-ttu-id="61f64-145">Die Entität, die die Berechtigung für ein sicherungsfähiges Element empfängt, wird als Prinzipal bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="61f64-145">The entity that receives permission to a securable is called a principal.</span></span> <span data-ttu-id="61f64-146">Die am häufigsten auftretenden Prinzipale sind Anmeldedaten und Datenbankbenutzer.</span><span class="sxs-lookup"><span data-stu-id="61f64-146">The most common principals are logins and database users.</span></span> <span data-ttu-id="61f64-147">Der Zugriff auf sicherungsfähige Elemente wird durch das Gewähren oder Verweigern von Berechtigungen gesteuert, oder durch das Hinzufügen von Anmeldedaten und Benutzer zu Rollen, die über Zugriff verfügen.</span><span class="sxs-lookup"><span data-stu-id="61f64-147">Access to securables is controlled by granting or denying permissions, or by adding logins and user to roles which have access.</span></span> <span data-ttu-id="61f64-148">Informationen zum Steuern von Berechtigungen finden Sie unter [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql), [REVOKE &#40;Transact-SQL&#41;](/sql/t-sql/statements/revoke-transact-sql), [DENY &#40;Transact-SQL&#41;](/sql/t-sql/statements/deny-transact-sql), [sp_addrolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addrolemember-transact-sql) und [sp_droprolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-droprolemember-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="61f64-148">For information about controlling permissions, see [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql), [REVOKE &#40;Transact-SQL&#41;](/sql/t-sql/statements/revoke-transact-sql), [DENY &#40;Transact-SQL&#41;](/sql/t-sql/statements/deny-transact-sql), [sp_addrolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addrolemember-transact-sql), and [sp_droprolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-droprolemember-transact-sql).</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="61f64-149">Die Standardberechtigungen, die Systemobjekten zum Zeitpunkt der Installation erteilt wurden, werden sorgfältig bezüglich möglicher Bedrohungen ausgewertet und müssen nicht im Rahmen der Härtung der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Installation geändert werden.</span><span class="sxs-lookup"><span data-stu-id="61f64-149">The default permissions that are granted to system objects at the time of setup are carefully evaluated against possible threats and need not be altered as part of hardening the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] installation.</span></span> <span data-ttu-id="61f64-150">Alle Änderungen an den Berechtigungen für Systemobjekte können die Funktionalität einschränken oder unterbrechen und potenziell dazu führen, dass Ihre [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Installation einen nicht unterstützten Zustand aufweist.</span><span class="sxs-lookup"><span data-stu-id="61f64-150">Any changes to the permissions on the system objects could limit or break the functionality and could potentially leave your [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] installation in an unsupported state.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="61f64-151">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="61f64-151">Related Content</span></span>  
 [<span data-ttu-id="61f64-152">Sichern von SQL Server</span><span class="sxs-lookup"><span data-stu-id="61f64-152">Securing SQL Server</span></span>](securing-sql-server.md)  
  
 [<span data-ttu-id="61f64-153">sys.database_principals &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="61f64-153">sys.database_principals &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-database-principals-transact-sql)  
  
 [<span data-ttu-id="61f64-154">sys.database_role_members &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="61f64-154">sys.database_role_members &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-database-role-members-transact-sql)  
  
 [<span data-ttu-id="61f64-155">sys.server_principals &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="61f64-155">sys.server_principals &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-server-principals-transact-sql)  
  
 [<span data-ttu-id="61f64-156">sys.server_role_members &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="61f64-156">sys.server_role_members &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-server-role-members-transact-sql)  
  
 [<span data-ttu-id="61f64-157">sys.sql_logins &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="61f64-157">sys.sql_logins &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-sql-logins-transact-sql)  
  
  
