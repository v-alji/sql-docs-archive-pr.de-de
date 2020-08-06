---
title: Datensammlersicherheit | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- data collection [SQL Server]
- security [data collector]
- data collector [SQL Server], security
ms.assetid: e75d6975-641e-440a-a642-cb39a583359a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c89f1658f6ae1b5bd79de96f20222b0b19529df2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609910"
---
# <a name="data-collector-security"></a><span data-ttu-id="02fb8-102">Datensammlersicherheit</span><span class="sxs-lookup"><span data-stu-id="02fb8-102">Data Collector Security</span></span>
  <span data-ttu-id="02fb8-103">Der Datensammler verwendet das von dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent implementierte rollenbasierte Sicherheitsmodell.</span><span class="sxs-lookup"><span data-stu-id="02fb8-103">The data collector uses the role-based security model implemented by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="02fb8-104">Mit diesem Modell kann der Datenbankadministrator die verschiedenen Datensammlertasks in einem Sicherheitskontext ausführen, der nur über die zum Ausführen dieses Tasks erforderlichen Berechtigungen verfügt.</span><span class="sxs-lookup"><span data-stu-id="02fb8-104">This model lets the database administrator run the various data collector tasks in a security context that has only the permissions required to perform that task.</span></span> <span data-ttu-id="02fb8-105">Dieser Ansatz wird auch für Vorgänge mit internen Tabellen verwendet, auf die nur unter Verwendung einer gespeicherten Prozedur oder Sicht zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="02fb8-105">This approach is also used for operations involving internal tables, which can only be accessed by using a stored procedure or view.</span></span> <span data-ttu-id="02fb8-106">Internen Tabellen werden keine Berechtigungen erteilt.</span><span class="sxs-lookup"><span data-stu-id="02fb8-106">No permissions are granted to internal tables.</span></span> <span data-ttu-id="02fb8-107">Stattdessen werden Berechtigungen für den Benutzer der gespeicherten Prozedur oder Sicht überprüft, die zum Zugreifen auf eine Tabelle verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="02fb8-107">Instead, permissions are checked on the user of the stored procedure or view that is used to access a table.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="02fb8-108">Ein anderer Hauptaspekt dieses Sicherheitsmodells sind konzentrische Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="02fb8-108">Another key aspect of this security model is concentric permissions.</span></span> <span data-ttu-id="02fb8-109">Mit konzentrischen Berechtigungen erben Rollen mit höheren Berechtigungen die Berechtigungen von Rollen mit niedrigeren Berechtigungen für Objekte (einschließlich Warnungen, Operatoren, Aufträgen, Zeitplänen und Proxys).</span><span class="sxs-lookup"><span data-stu-id="02fb8-109">Under concentric permissions, more privileged roles inherit the permissions of less privileged roles on objects (including alerts, operators, jobs, schedules, and proxies).</span></span> <span data-ttu-id="02fb8-110">Weitere Informationen finden Sie unter [SQL Server Agent Fixed Database Roles](../../ssms/agent/sql-server-agent-fixed-database-roles.md).</span><span class="sxs-lookup"><span data-stu-id="02fb8-110">For more information, see [SQL Server Agent Fixed Database Roles](../../ssms/agent/sql-server-agent-fixed-database-roles.md).</span></span>  
  
 <span data-ttu-id="02fb8-111">In den folgenden Abschnitten werden die Datensammlungssicherheit im Allgemeinen sowie die Rollen beschrieben, die Sie Benutzern erteilen müssen, damit diese den Datensammler konfigurieren und verwenden und mit dem Management Data Warehouse verbundene Tasks ausführen können.</span><span class="sxs-lookup"><span data-stu-id="02fb8-111">The following sections describe data collection security in general, as well as the roles you must grant to users so they can configure and use the data collector, and carry out tasks associated with the management data warehouse.</span></span>  
  
## <a name="general-security"></a><span data-ttu-id="02fb8-112">Allgemeine Sicherheit</span><span class="sxs-lookup"><span data-stu-id="02fb8-112">General Security</span></span>  
 <span data-ttu-id="02fb8-113">Der Datensammler wird gemäß der für [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]festgelegten dokumentierten Standards installiert.</span><span class="sxs-lookup"><span data-stu-id="02fb8-113">The data collector is installed according to the documented standards specified for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
### <a name="network-security"></a><span data-ttu-id="02fb8-114">Netzwerksicherheit</span><span class="sxs-lookup"><span data-stu-id="02fb8-114">Network Security</span></span>  
 <span data-ttu-id="02fb8-115">Vertrauliche Informationen können zwischen Zielinstanzen, der mit dem Konfigurationsserver verbundenen relationalen Instanz, den ausgeführten Sammlungssätzen und dem Server, der das Verwaltungs-Data Warehouse hostet, übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="02fb8-115">Sensitive information can be passed between target instances, the relational instance associated with the configuration server, the collection sets that are running, and the server that hosts the management data warehouse.</span></span>  
  
 <span data-ttu-id="02fb8-116">Zum Schützen von Daten, die über ein Netzwerk übertragen werden, werden die Standardsicherheitsmechanismen implementiert, beispielsweise Protokollverschlüsselung für [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="02fb8-116">To protect any data that is transferred over a network, the standard security mechanisms are implemented, such as protocol encryption for [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
## <a name="permissions-for-configuring-and-using-the-data-collector"></a><span data-ttu-id="02fb8-117">Berechtigungen zum Konfigurieren und Verwenden des Datensammlers</span><span class="sxs-lookup"><span data-stu-id="02fb8-117">Permissions for Configuring and Using the Data Collector</span></span>  
 <span data-ttu-id="02fb8-118">Je nach Task müssen Benutzer Mitglieder von mindestens einer festen Datenbankrolle sein, die für den Datensammler bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="02fb8-118">Depending on the task, users must be members of one or more of the fixed database roles provided for the data collector.</span></span> <span data-ttu-id="02fb8-119">Die Rollen lauten, geordnet von den höchsten bis zu den niedrigsten Zugriffsberechtigungen, wie folgt:</span><span class="sxs-lookup"><span data-stu-id="02fb8-119">In order of most-privileged to least-privileged access, the roles are as follows:</span></span>  
  
-   `dc_admin`  
  
-   <span data-ttu-id="02fb8-120">**dc_operator**</span><span class="sxs-lookup"><span data-stu-id="02fb8-120">**dc_operator**</span></span>  
  
-   <span data-ttu-id="02fb8-121">**dc_proxy**</span><span class="sxs-lookup"><span data-stu-id="02fb8-121">**dc_proxy**</span></span>  
  
 <span data-ttu-id="02fb8-122">Diese Rollen werden in der msdb-Datenbank gespeichert.</span><span class="sxs-lookup"><span data-stu-id="02fb8-122">These roles are stored in the msdb database.</span></span> <span data-ttu-id="02fb8-123">Standardmäßig ist kein Benutzer Mitglied dieser Datenbankrollen.</span><span class="sxs-lookup"><span data-stu-id="02fb8-123">By default, no user is a member of these database roles.</span></span> <span data-ttu-id="02fb8-124">Die Benutzermitgliedschaft in diesen Rollen muss explizit erteilt werden.</span><span class="sxs-lookup"><span data-stu-id="02fb8-124">User membership in these roles must be granted explicitly.</span></span>  
  
 <span data-ttu-id="02fb8-125">Benutzer, die Mitglieder der `sysadmin` Server Rolle Fixed sind, haben vollen Zugriff auf [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Objekte und-Datensammler Sichten.</span><span class="sxs-lookup"><span data-stu-id="02fb8-125">Users who are members of the `sysadmin` fixed server role have full access to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent objects and data collector views.</span></span> <span data-ttu-id="02fb8-126">Sie müssen jedoch explizit Datensammlerrollen hinzugefügt worden sein.</span><span class="sxs-lookup"><span data-stu-id="02fb8-126">However, they need to be explicitly added to data collector roles.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="02fb8-127">Mitglieder der db_ssisadmin-Rolle und der dc_admin-Rolle können Ihre Berechtigungen möglicherweise auf sysadmin erhöhen.</span><span class="sxs-lookup"><span data-stu-id="02fb8-127">Members of the db_ssisadmin role and the dc_admin role may be able to elevate their privileges to sysadmin.</span></span> <span data-ttu-id="02fb8-128">Diese Ausweitung von Berechtigungen ist möglich, da diese Rollen [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Pakete ändern können und [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Pakete von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mithilfe des sysadmin-Sicherheitskontexts des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agents ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="02fb8-128">This elevation of privilege can occur because these roles can modify [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages and [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages can be executed by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using the sysadmin security context of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="02fb8-129">Konfigurieren Sie als Schutz vor dieser Ausweitung von Berechtigungen beim Ausführen von Wartungsplänen, Datensammlungssätzen und anderen [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Paketen Aufträge des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agents, die Pakete ausführen, für die Verwendung eines Proxykontos mit einschränkten Berechtigungen, oder fügen Sie der db_ssisadmin-Rolle und der dc_admin-Rolle nur sysadmin-Mitglieder hinzu.</span><span class="sxs-lookup"><span data-stu-id="02fb8-129">To guard against this elevation of privilege when running maintenance plans, data collection sets, and other [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages, configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs that run packages to use a proxy account with limited privileges or only add sysadmin members to the db_ssisadmin and dc_admin roles.</span></span>  
  
### <a name="dc_admin-role"></a><span data-ttu-id="02fb8-130">dc_admin-Rolle</span><span class="sxs-lookup"><span data-stu-id="02fb8-130">dc_admin Role</span></span>  
 <span data-ttu-id="02fb8-131">Benutzer, die der `dc_admin` Rolle zugewiesen sind, haben vollen Administrator Zugriff (erstellen, lesen, aktualisieren und löschen) auf die Datensammler Konfiguration auf einer Serverinstanz.</span><span class="sxs-lookup"><span data-stu-id="02fb8-131">Users assigned to the `dc_admin` role have full administrator access (Create, Read, Update, and Delete) to the data collector configuration on a server instance.</span></span> <span data-ttu-id="02fb8-132">Mitglieder dieser Rolle können die folgenden Vorgänge ausführen:</span><span class="sxs-lookup"><span data-stu-id="02fb8-132">Members of this role can perform the following operations:</span></span>  
  
-   <span data-ttu-id="02fb8-133">Festlegen von Eigenschaften auf Sammlerebene.</span><span class="sxs-lookup"><span data-stu-id="02fb8-133">Set collector-level properties.</span></span>  
  
-   <span data-ttu-id="02fb8-134">Hinzufügen neuer Sammlungssätze.</span><span class="sxs-lookup"><span data-stu-id="02fb8-134">Add new collection sets.</span></span>  
  
-   <span data-ttu-id="02fb8-135">Installieren neuer Sammlungstypen.</span><span class="sxs-lookup"><span data-stu-id="02fb8-135">Install new collection types.</span></span>  
  
-   <span data-ttu-id="02fb8-136">Ausführen aller Vorgänge, die der **dc_operator** -Rolle erteilt wurden.</span><span class="sxs-lookup"><span data-stu-id="02fb8-136">Perform all the operations permitted to the **dc_operator** role.</span></span>  
  
 <span data-ttu-id="02fb8-137">Die `dc_admin` Rolle ist ein Mitglied der folgenden Rollen:</span><span class="sxs-lookup"><span data-stu-id="02fb8-137">The `dc_admin` role is a member of the following roles:</span></span>  
  
-   <span data-ttu-id="02fb8-138">**SQLAgentUserRole**.</span><span class="sxs-lookup"><span data-stu-id="02fb8-138">**SQLAgentUserRole**.</span></span> <span data-ttu-id="02fb8-139">Diese Rolle ist zum Erstellen von Zeitplänen und zum Ausführen von Aufträgen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="02fb8-139">This role is required to create schedules and run jobs.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="02fb8-140">Proxys, die für den Datensammler erstellt wurden, müssen Zugriff auf erteilen, `dc_admin` um Sie zu erstellen und in allen Auftrags Schritten zu verwenden, die einen Proxy erfordern.</span><span class="sxs-lookup"><span data-stu-id="02fb8-140">Proxies created for the data collector must grant access to `dc_admin` to create them and use them in any job steps that require a proxy.</span></span>  
  
-   <span data-ttu-id="02fb8-141">**dc_operator**.</span><span class="sxs-lookup"><span data-stu-id="02fb8-141">**dc_operator**.</span></span> <span data-ttu-id="02fb8-142">Mitglieder von `dc_admin` erben die Berechtigungen, die **dc_operator**erteilt wurden.</span><span class="sxs-lookup"><span data-stu-id="02fb8-142">Members of `dc_admin` inherit the permissions given to **dc_operator**.</span></span>  
  
### <a name="dc_operator-role"></a><span data-ttu-id="02fb8-143">dc_operator-Rolle</span><span class="sxs-lookup"><span data-stu-id="02fb8-143">dc_operator Role</span></span>  
 <span data-ttu-id="02fb8-144">Mitglieder der **dc_operator-Rolle** verfügen über Lese- und Aktualisierungszugriff.</span><span class="sxs-lookup"><span data-stu-id="02fb8-144">Members of the **dc_operator** role have Read and Update access.</span></span> <span data-ttu-id="02fb8-145">Diese Rolle unterstützt Vorgangstasks in Bezug auf das Ausführen und Konfigurieren von Sammlungssätzen.</span><span class="sxs-lookup"><span data-stu-id="02fb8-145">This role supports operations tasks related to running and configuring collection sets.</span></span> <span data-ttu-id="02fb8-146">Mitglieder dieser Rolle können die folgenden Vorgänge ausführen:</span><span class="sxs-lookup"><span data-stu-id="02fb8-146">Members of this role can perform the following operations:</span></span>  
  
-   <span data-ttu-id="02fb8-147">Starten oder Beenden eines Sammlungssatzes.</span><span class="sxs-lookup"><span data-stu-id="02fb8-147">Start or stop a collection set.</span></span>  
  
-   <span data-ttu-id="02fb8-148">Auflisten vorhandener Sammlungssätze.</span><span class="sxs-lookup"><span data-stu-id="02fb8-148">Enumerate existing collection sets.</span></span>  
  
-   <span data-ttu-id="02fb8-149">Anzeigen der mit einem Sammlungssatz verbundenen ausführlichen Informationen (beispielsweise Sammelelemente und Sammlungshäufigkeit).</span><span class="sxs-lookup"><span data-stu-id="02fb8-149">View the detailed information (for example, collection items, and collection frequency) associated with a collection set.</span></span>  
  
-   <span data-ttu-id="02fb8-150">Ändern der Hochladehäufigkeit für vorhandene Sammlungssätze.</span><span class="sxs-lookup"><span data-stu-id="02fb8-150">Change the upload frequency for existing collection sets.</span></span>  
  
-   <span data-ttu-id="02fb8-151">Ändern der Sammlungshäufigkeit für Sammlungselemente, die Teil eines vorhandenen Sammlungssatzes sind.</span><span class="sxs-lookup"><span data-stu-id="02fb8-151">Change the collection frequency for collection items that are part of an existing collection set.</span></span>  
  
 <span data-ttu-id="02fb8-152">Die **dc_operator** -Rolle ist ein Element der folgenden Rollen, die zum Aufzählen und Anzeigen von Datensammlerpaketen erforderlich sind:</span><span class="sxs-lookup"><span data-stu-id="02fb8-152">The **dc_operator** role is a member of the following roles that are required for enumerating and viewing data collector packages:</span></span>  
  
-   <span data-ttu-id="02fb8-153">**db_ssisltduser**</span><span class="sxs-lookup"><span data-stu-id="02fb8-153">**db_ssisltduser**</span></span>  
  
-   <span data-ttu-id="02fb8-154">**db_ssisoperator**</span><span class="sxs-lookup"><span data-stu-id="02fb8-154">**db_ssisoperator**</span></span>  
  
 <span data-ttu-id="02fb8-155">Weitere Informationen finden Sie unter [Integration Services Roles &#40;SSIS Service&#41;](../../integration-services/security/integration-services-roles-ssis-service.md) (Integration Services-Rollen [SSIS-Dienst]).</span><span class="sxs-lookup"><span data-stu-id="02fb8-155">For more information, see [Integration Services Roles &#40;SSIS Service&#41;](../../integration-services/security/integration-services-roles-ssis-service.md).</span></span>  
  
### <a name="dc_proxy-role"></a><span data-ttu-id="02fb8-156">dc_proxy-Rolle</span><span class="sxs-lookup"><span data-stu-id="02fb8-156">dc_proxy Role</span></span>  
 <span data-ttu-id="02fb8-157">Mitglieder der **dc_proxy** -Rolle verfügen über Lesezugriff auf Sammlungssätze des Datensammlers und Eigenschaften auf Sammlerebene.</span><span class="sxs-lookup"><span data-stu-id="02fb8-157">Members of the **dc_proxy** role have Read access to data collector collection sets and collector-level properties.</span></span> <span data-ttu-id="02fb8-158">Die Mitglieder dieser Rolle können auch Aufträge anzeigen und ausführen, deren Besitzer sie sind, und Auftragsschritte erstellen, die als bereits vorhandenes Proxykonto ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="02fb8-158">Members of this role can also execute jobs that they own and create job steps that run as an existing proxy account.</span></span>  
  
 <span data-ttu-id="02fb8-159">Mitglieder dieser Rolle können die folgenden Vorgänge ausführen:</span><span class="sxs-lookup"><span data-stu-id="02fb8-159">Members of this role can perform the following operations:</span></span>  
  
-   <span data-ttu-id="02fb8-160">Anzeigen der mit einem Sammlungssatz verbundenen Konfigurationsinformationen (beispielsweise Eingabeparameter für Sammelelemente und die Sammlungshäufigkeit für diese Elemente).</span><span class="sxs-lookup"><span data-stu-id="02fb8-160">View collection set configuration information (for example, input parameters for collection items, and the collection frequency for these items).</span></span>  
  
-   <span data-ttu-id="02fb8-161">Abrufen interner verschlüsselter Informationen, auf die nur von einer signierten gespeicherten Prozedur zugegriffen werden kann (beispielsweise Informationen über eine Data Warehouse-Verbindung, die zum Hochladen von Daten verwendet wird).</span><span class="sxs-lookup"><span data-stu-id="02fb8-161">Obtain internal encrypted information that can only be accessed by a signed stored procedure (for example, data warehouse connection information used for data uploads).</span></span>  
  
-   <span data-ttu-id="02fb8-162">Protokollieren von für eine Sammlung festgelegte Ereignisse zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="02fb8-162">Log collection-set run-time events.</span></span>  
  
 <span data-ttu-id="02fb8-163">Die **dc_proxy** -Rolle ist ein Element der folgenden Rollen, die zum Aufzählen und Anzeigen von Datensammlerpaketen erforderlich sind:</span><span class="sxs-lookup"><span data-stu-id="02fb8-163">The **dc_proxy** role is a member of the following roles that are required for enumerating and viewing data collector packages:</span></span>  
  
-   <span data-ttu-id="02fb8-164">**db_ssisltduser**.</span><span class="sxs-lookup"><span data-stu-id="02fb8-164">**db_ssisltduser**.</span></span>  
  
-   <span data-ttu-id="02fb8-165">**db_ssisoperator**</span><span class="sxs-lookup"><span data-stu-id="02fb8-165">**db_ssisoperator**</span></span>  
  
 <span data-ttu-id="02fb8-166">Weitere Informationen finden Sie unter [Integration Services Roles &#40;SSIS Service&#41;](../../integration-services/security/integration-services-roles-ssis-service.md) (Integration Services-Rollen [SSIS-Dienst]).</span><span class="sxs-lookup"><span data-stu-id="02fb8-166">For more information, see [Integration Services Roles &#40;SSIS Service&#41;](../../integration-services/security/integration-services-roles-ssis-service.md).</span></span>  
  
## <a name="permissions-for-configuring-and-using-the-management-data-warehouse"></a><span data-ttu-id="02fb8-167">Berechtigungen zum Konfigurieren und Verwenden des Management Data Warehouse</span><span class="sxs-lookup"><span data-stu-id="02fb8-167">Permissions for Configuring and Using the Management Data Warehouse</span></span>  
 <span data-ttu-id="02fb8-168">Je nach Task müssen Benutzer Mitglieder von mindestens einer festen Datenbankrolle sein, die für den Zugriff auf das Verwaltungs-Data Warehouse bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="02fb8-168">Depending on the task, users must be members of one or more of the fixed database roles provided for accessing the management data warehouse.</span></span> <span data-ttu-id="02fb8-169">Die Rollen lauten, geordnet von den höchsten bis zu den niedrigsten Zugriffsberechtigungen, wie folgt:</span><span class="sxs-lookup"><span data-stu-id="02fb8-169">In order of most-privileged to least-privileged access, the roles are as follows:</span></span>  
  
-   <span data-ttu-id="02fb8-170">**mdw_admin**</span><span class="sxs-lookup"><span data-stu-id="02fb8-170">**mdw_admin**</span></span>  
  
-   <span data-ttu-id="02fb8-171">**mdw_writer**</span><span class="sxs-lookup"><span data-stu-id="02fb8-171">**mdw_writer**</span></span>  
  
-   <span data-ttu-id="02fb8-172">**mdw_reader**</span><span class="sxs-lookup"><span data-stu-id="02fb8-172">**mdw_reader**</span></span>  
  
 <span data-ttu-id="02fb8-173">Diese Rollen werden in der msdb-Datenbank gespeichert.</span><span class="sxs-lookup"><span data-stu-id="02fb8-173">These roles are stored in the msdb database.</span></span> <span data-ttu-id="02fb8-174">Standardmäßig ist kein Benutzer Mitglied dieser Datenbankrollen.</span><span class="sxs-lookup"><span data-stu-id="02fb8-174">By default, no user is a member of these database roles.</span></span> <span data-ttu-id="02fb8-175">Die Benutzermitgliedschaft in diesen Rollen muss explizit erteilt werden.</span><span class="sxs-lookup"><span data-stu-id="02fb8-175">User membership in these roles must be granted explicitly.</span></span>  
  
 <span data-ttu-id="02fb8-176">Benutzer, die Mitglieder der `sysadmin` Server Rolle Fixed sind, haben vollen Zugriff auf die Datensammler Sichten.</span><span class="sxs-lookup"><span data-stu-id="02fb8-176">Users who are members of the `sysadmin` fixed server role have full access to data collector views.</span></span> <span data-ttu-id="02fb8-177">Sie müssen jedoch explizit Datenbankrollen hinzugefügt werden, um weitere Operationen durchführen zu können.</span><span class="sxs-lookup"><span data-stu-id="02fb8-177">However, they need to be explicitly added to database roles to perform other operations.</span></span>  
  
### <a name="mdw_admin-role"></a><span data-ttu-id="02fb8-178">mdw_admin-Rolle</span><span class="sxs-lookup"><span data-stu-id="02fb8-178">mdw_admin Role</span></span>  
 <span data-ttu-id="02fb8-179">Mitglieder der **mdw_admin** -Rolle verfügen über Lese-, Schreib-, Aktualisierungs- und Löschzugriff auf das Verwaltungs-Data Warehouse.</span><span class="sxs-lookup"><span data-stu-id="02fb8-179">Members of the **mdw_admin** role have Read, Write, Update, and Delete access to the management data warehouse.</span></span>  
  
 <span data-ttu-id="02fb8-180">Mitglieder dieser Rolle können die folgenden Vorgänge ausführen:</span><span class="sxs-lookup"><span data-stu-id="02fb8-180">Members of this role can perform the following operations:</span></span>  
  
-   <span data-ttu-id="02fb8-181">Ändern des Verwaltungs-Data Warehouse-Schemas, falls erforderlich (beispielsweise Hinzufügen einer neuen Tabelle, wenn ein neuer Sammlertyp installiert wird).</span><span class="sxs-lookup"><span data-stu-id="02fb8-181">Change the management data warehouse schema when required (for example, adding a new table when a new collection type is installed).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="02fb8-182">Wenn eine Schema Änderung vorliegt, muss der Benutzer auch Mitglied der Rolle sein, `dc_admin` um einen neuen Sammlertyp installieren zu können, da für diese Aktion eine Berechtigung zum Aktualisieren der Datensammler Konfiguration in msdb erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="02fb8-182">Where there is a schema change, the user must also be a member of the `dc_admin` role to install a new collector type, since this action requires permission to update the data collector configuration in msdb.</span></span>  
  
-   <span data-ttu-id="02fb8-183">Ausführen von Wartungsaufträgen für das Verwaltungs-Data Warehouse, beispielsweise Archivierung oder Cleanup.</span><span class="sxs-lookup"><span data-stu-id="02fb8-183">Run maintenance jobs on the management data warehouse, such as archive or cleanup.</span></span>  
  
### <a name="mdw_writer-role"></a><span data-ttu-id="02fb8-184">mdw_writer-Rolle</span><span class="sxs-lookup"><span data-stu-id="02fb8-184">mdw_writer Role</span></span>  
 <span data-ttu-id="02fb8-185">Mitglieder der **mdw_writer** -Rolle können Daten in das Verwaltungs-Data Warehouse hochladen und schreiben.</span><span class="sxs-lookup"><span data-stu-id="02fb8-185">Members of the **mdw_writer** role can upload and write data to the management data warehouse.</span></span> <span data-ttu-id="02fb8-186">Jeder Datensammler, der Daten in dem Verwaltungs-Data Warehouse speichert, muss ein Mitglied dieser Rolle sein.</span><span class="sxs-lookup"><span data-stu-id="02fb8-186">Any data collector that stores data in the management data warehouse has to be a member of this role.</span></span>  
  
### <a name="mdw_reader-role"></a><span data-ttu-id="02fb8-187">mdw_reader-Rolle</span><span class="sxs-lookup"><span data-stu-id="02fb8-187">mdw_reader Role</span></span>  
 <span data-ttu-id="02fb8-188">Mitglieder der **mdw_reader** -Rolle verfügen über Lesezugriff auf das Verwaltungs-Data Warehouse.</span><span class="sxs-lookup"><span data-stu-id="02fb8-188">Members of the **mdw_reader** role have Read access to the management data warehouse.</span></span> <span data-ttu-id="02fb8-189">Da diese Rolle zur Unterstützung bei der Problembehandlung dient, indem sie Zugriff auf Verlaufsdaten bietet, können Mitglieder dieser Rolle andere Elemente des Verwaltungs-Data Warehouse-Schemas nicht anzeigen.</span><span class="sxs-lookup"><span data-stu-id="02fb8-189">Because the purpose of this role is to support troubleshooting by providing access to historical data, members of this role cannot view other elements of the management data warehouse schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02fb8-190">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="02fb8-190">See Also</span></span>  
 [<span data-ttu-id="02fb8-191">Implementieren der SQL Server-Agent-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="02fb8-191">Implement SQL Server Agent Security</span></span>](../../ssms/agent/implement-sql-server-agent-security.md)  
  
  
