---
title: Entfernen von Verweisen auf veraltete gespeicherte System Prozeduren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- undocumented system stored procedures [SQL Server]
- system stored procedures [SQL Server]
ms.assetid: 487d24fc-41d5-495e-843c-0ac974ec472f
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 65e7da666beaf84050dd8d60caf4cac5bfc013c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720845"
---
# <a name="remove-references-to-deprecated-system-stored-procedures"></a><span data-ttu-id="f2ed2-102">Entfernen von Verweisen auf veraltete gespeicherte Systemprozeduren</span><span class="sxs-lookup"><span data-stu-id="f2ed2-102">Remove references to deprecated system stored procedures</span></span>
  <span data-ttu-id="f2ed2-103">Upgrade Advisor hat Anweisungen erkannt, die auf nicht dokumentierte gespeicherte Systemprozeduren sowie erweiterte gespeicherte Prozeduren verweisen, die in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nicht mehr verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="f2ed2-103">Upgrade Advisor detected statements that reference undocumented system stored procedures and extended stored procedures that are no longer available in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f2ed2-104">Anweisungen, die auf diese Objekte verweisen, schlagen fehl.</span><span class="sxs-lookup"><span data-stu-id="f2ed2-104">Statements that reference these objects will fail.</span></span> <span data-ttu-id="f2ed2-105">Verwenden Sie keine nicht dokumentierten Systemobjekte oder APIs, da die Funktionalität in einer späteren Version möglicherweise ohne Vorankündigung geändert oder entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="f2ed2-105">Do not use undocumented system objects or APIs as the functionality might change or be removed without notification in a future release.</span></span>  
  
## <a name="component"></a><span data-ttu-id="f2ed2-106">Komponente</span><span class="sxs-lookup"><span data-stu-id="f2ed2-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="f2ed2-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f2ed2-107">Description</span></span>  
  
### <a name="documented-system-stored-procedures"></a><span data-ttu-id="f2ed2-108">Dokumentierte gespeicherte Systemprozeduren</span><span class="sxs-lookup"><span data-stu-id="f2ed2-108">Documented System Stored Procedures</span></span>  
 <span data-ttu-id="f2ed2-109">Die folgenden dokumentierten gespeicherten Systemprozeduren wurden entfernt:</span><span class="sxs-lookup"><span data-stu-id="f2ed2-109">The following documented system stored procedures have been removed:</span></span>  
  
-   <span data-ttu-id="f2ed2-110">sp_addalias</span><span class="sxs-lookup"><span data-stu-id="f2ed2-110">sp_addalias</span></span>  
  
-   <span data-ttu-id="f2ed2-111">sp_addgroup</span><span class="sxs-lookup"><span data-stu-id="f2ed2-111">sp_addgroup</span></span>  
  
-   <span data-ttu-id="f2ed2-112">sp_changegroup</span><span class="sxs-lookup"><span data-stu-id="f2ed2-112">sp_changegroup</span></span>  
  
-   <span data-ttu-id="f2ed2-113">sp_dropgroup</span><span class="sxs-lookup"><span data-stu-id="f2ed2-113">sp_dropgroup</span></span>  
  
-   <span data-ttu-id="f2ed2-114">sp_helpgroup</span><span class="sxs-lookup"><span data-stu-id="f2ed2-114">sp_helpgroup</span></span>  
  
### <a name="undocumented-system-stored-procedures"></a><span data-ttu-id="f2ed2-115">Nicht dokumentierte gespeicherte Systemprozeduren</span><span class="sxs-lookup"><span data-stu-id="f2ed2-115">Undocumented System Stored Procedures</span></span>  
 <span data-ttu-id="f2ed2-116">Die folgenden nicht dokumentierten gespeicherten Systemprozeduren und erweiterten gespeicherten Prozeduren wurden entfernt:</span><span class="sxs-lookup"><span data-stu-id="f2ed2-116">The following undocumented system stored procedures and extended stored procedures have been removed:</span></span>  
  
-   <span data-ttu-id="f2ed2-117">sp_articlesynctranprocs</span><span class="sxs-lookup"><span data-stu-id="f2ed2-117">sp_articlesynctranprocs</span></span>  
  
-   <span data-ttu-id="f2ed2-118">sp_diskdefault</span><span class="sxs-lookup"><span data-stu-id="f2ed2-118">sp_diskdefault</span></span>  
  
-   <span data-ttu-id="f2ed2-119">sp_EventLog</span><span class="sxs-lookup"><span data-stu-id="f2ed2-119">sp_EventLog</span></span>  
  
-   <span data-ttu-id="f2ed2-120">sp_GetMBCSCharLen</span><span class="sxs-lookup"><span data-stu-id="f2ed2-120">sp_GetMBCSCharLen</span></span>  
  
-   <span data-ttu-id="f2ed2-121">sp_helplog</span><span class="sxs-lookup"><span data-stu-id="f2ed2-121">sp_helplog</span></span>  
  
-   <span data-ttu-id="f2ed2-122">sp_helpsql</span><span class="sxs-lookup"><span data-stu-id="f2ed2-122">sp_helpsql</span></span>  
  
-   <span data-ttu-id="f2ed2-123">sp_IsMBCSLeadByte</span><span class="sxs-lookup"><span data-stu-id="f2ed2-123">sp_IsMBCSLeadByte</span></span>  
  
-   <span data-ttu-id="f2ed2-124">sp_lock2</span><span class="sxs-lookup"><span data-stu-id="f2ed2-124">sp_lock2</span></span>  
  
-   <span data-ttu-id="f2ed2-125">sp_MSget_current_activity</span><span class="sxs-lookup"><span data-stu-id="f2ed2-125">sp_MSget_current_activity</span></span>  
  
-   <span data-ttu-id="f2ed2-126">sp_MSset_current_activity</span><span class="sxs-lookup"><span data-stu-id="f2ed2-126">sp_MSset_current_activity</span></span>  
  
-   <span data-ttu-id="f2ed2-127">sp_MSobjessearch</span><span class="sxs-lookup"><span data-stu-id="f2ed2-127">sp_MSobjessearch</span></span>  
  
-   <span data-ttu-id="f2ed2-128">xp_enum_ActiveScriptEngines</span><span class="sxs-lookup"><span data-stu-id="f2ed2-128">xp_enum_ActiveScriptEngines</span></span>  
  
-   <span data-ttu-id="f2ed2-129">xp_eventlog</span><span class="sxs-lookup"><span data-stu-id="f2ed2-129">xp_eventlog</span></span>  
  
-   <span data-ttu-id="f2ed2-130">xp_GetAdminGroupName</span><span class="sxs-lookup"><span data-stu-id="f2ed2-130">xp_GetAdminGroupName</span></span>  
  
-   <span data-ttu-id="f2ed2-131">xp_GetFileDetails</span><span class="sxs-lookup"><span data-stu-id="f2ed2-131">xp_GetFileDetails</span></span>  
  
-   <span data-ttu-id="f2ed2-132">xp_GetLocalSystemAccountName</span><span class="sxs-lookup"><span data-stu-id="f2ed2-132">xp_GetLocalSystemAccountName</span></span>  
  
-   <span data-ttu-id="f2ed2-133">xp_IsNTAdmin</span><span class="sxs-lookup"><span data-stu-id="f2ed2-133">xp_IsNTAdmin</span></span>  
  
-   <span data-ttu-id="f2ed2-134">xp_MSLocalSystem</span><span class="sxs-lookup"><span data-stu-id="f2ed2-134">xp_MSLocalSystem</span></span>  
  
-   <span data-ttu-id="f2ed2-135">xp_MSnt2000</span><span class="sxs-lookup"><span data-stu-id="f2ed2-135">xp_MSnt2000</span></span>  
  
-   <span data-ttu-id="f2ed2-136">xp_MSplatform</span><span class="sxs-lookup"><span data-stu-id="f2ed2-136">xp_MSplatform</span></span>  
  
-   <span data-ttu-id="f2ed2-137">xp_SetSecurity</span><span class="sxs-lookup"><span data-stu-id="f2ed2-137">xp_SetSecurity</span></span>  
  
-   <span data-ttu-id="f2ed2-138">xp_varbintohexstr</span><span class="sxs-lookup"><span data-stu-id="f2ed2-138">xp_varbintohexstr</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="f2ed2-139">Korrekturmaßnahme</span><span class="sxs-lookup"><span data-stu-id="f2ed2-139">Corrective Action</span></span>  
  
### <a name="documented-system-stored-procedures"></a><span data-ttu-id="f2ed2-140">Dokumentierte gespeicherte Systemprozeduren</span><span class="sxs-lookup"><span data-stu-id="f2ed2-140">Documented System Stored Procedures</span></span>  
 <span data-ttu-id="f2ed2-141">Ändern Sie die Anwendungen entsprechend der folgenden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="f2ed2-141">Modify your applications according to the following table.</span></span>  
  
|<span data-ttu-id="f2ed2-142">Statt</span><span class="sxs-lookup"><span data-stu-id="f2ed2-142">Instead of</span></span>|<span data-ttu-id="f2ed2-143">Aktion</span><span class="sxs-lookup"><span data-stu-id="f2ed2-143">Do this</span></span>|  
|----------------|-------------|  
|<span data-ttu-id="f2ed2-144">sp_addalias</span><span class="sxs-lookup"><span data-stu-id="f2ed2-144">sp_addalias</span></span>|<span data-ttu-id="f2ed2-145">Ersetzen Sie Aliase durch eine Kombination von Benutzerkonten und Datenbankrollen.</span><span class="sxs-lookup"><span data-stu-id="f2ed2-145">Replace aliases with a combination of user accounts and database roles.</span></span> <span data-ttu-id="f2ed2-146">Weitere Informationen hierzu finden Sie in den Themen "CREATE USER (Transact-SQL)" und "CREATE ROLE (Transact-SQL)" in der SQL Server-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="f2ed2-146">For more information, see "CREATE USER (Transact-SQL)" and "CREATE ROLE (Transact-SQL)" in SQL Server Books Online.</span></span> <span data-ttu-id="f2ed2-147">Entfernen Sie Aliase in aktualisierten Datenbanken mithilfe von sp_dropalias.</span><span class="sxs-lookup"><span data-stu-id="f2ed2-147">Remove aliases in upgraded databases by using sp_dropalias.</span></span>|  
|<span data-ttu-id="f2ed2-148">sp_addgroupsp_changegroup</span><span class="sxs-lookup"><span data-stu-id="f2ed2-148">sp_addgroupsp_changegroup</span></span><br /><br /> <span data-ttu-id="f2ed2-149">sp_dropgroup</span><span class="sxs-lookup"><span data-stu-id="f2ed2-149">sp_dropgroup</span></span><br /><br /> <span data-ttu-id="f2ed2-150">sp_helpgroup</span><span class="sxs-lookup"><span data-stu-id="f2ed2-150">sp_helpgroup</span></span>|<span data-ttu-id="f2ed2-151">Verwenden Sie Rollen.</span><span class="sxs-lookup"><span data-stu-id="f2ed2-151">Use roles.</span></span> <span data-ttu-id="f2ed2-152">Weitere Informationen finden Sie in den Themen "Rollen auf Serverebene" und "Rollen auf Datenbankebene" in der SQL Server-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="f2ed2-152">For more information, see "Server-Level Roles" and "Database-Level Roles" in SQL Server Books Online.</span></span>|  
  
### <a name="undocmented-system-stored-procedures"></a><span data-ttu-id="f2ed2-153">Nicht docmentierte gespeicherte System Prozeduren</span><span class="sxs-lookup"><span data-stu-id="f2ed2-153">Undocmented System Stored Procedures</span></span>  
 <span data-ttu-id="f2ed2-154">Sie können gespeicherte CLR-Prozeduren mit entsprechender Funktionalität erstellen, um die nicht dokumentierten gespeicherten Systemprozeduren zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="f2ed2-154">You can create CLR stored procedures with equivalent functionality to replace the undocumented system stored procedures.</span></span> <span data-ttu-id="f2ed2-155">Weitere Informationen finden Sie im Thema "CLR-gespeicherte Prozeduren" in der SQL Server-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="f2ed2-155">For more information, see the topic "CLR Stored Procedures" in SQL Server Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2ed2-156">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f2ed2-156">See Also</span></span>  
 <span data-ttu-id="f2ed2-157">[Datenbank-Engine Upgradeprobleme](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="f2ed2-157">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="f2ed2-158">SQL Server 2014 Upgrade Advisor &#91;neuen&#93;</span><span class="sxs-lookup"><span data-stu-id="f2ed2-158">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  