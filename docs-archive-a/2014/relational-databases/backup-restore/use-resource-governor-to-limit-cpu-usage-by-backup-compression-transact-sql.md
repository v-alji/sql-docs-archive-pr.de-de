---
title: Einschränken der CPU-Nutzung durch die Sicherungskomprimierung mithilfe der Ressourcenkontrolle (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- backup compression [SQL Server], Resource Governor
- backup compression [SQL Server], CPU usage
- compression [SQL Server], backup compression
- backups [SQL Server], compression
- Resource Governor, backup compression
ms.assetid: 01796551-578d-4425-9b9e-d87210f7ba72
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 19a95cfa5c6780fbdf71ae58bd141aa9aa351efa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725993"
---
# <a name="use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql"></a><span data-ttu-id="06517-102">Einschränken der CPU-Nutzung durch die Sicherungskomprimierung mithilfe der Ressourcenkontrolle (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="06517-102">Use Resource Governor to Limit CPU Usage by Backup Compression (Transact-SQL)</span></span>
  <span data-ttu-id="06517-103">Standardmäßig steigt die CPU-Nutzung durch die Sicherung mit Komprimierung erheblich, und die bei der Komprimierung zusätzlich benötigten CPU-Ressourcen können sich negativ auf gleichzeitig ausgeführte Vorgänge auswirken.</span><span class="sxs-lookup"><span data-stu-id="06517-103">By default, backing up using compression significantly increases CPU usage, and the additional CPU consumed by the compression process can adversely impact concurrent operations.</span></span> <span data-ttu-id="06517-104">Daher ist es u.U. sinnvoll, in einer Sitzung, bei der die CPU-Nutzung durch den[Resource Governor](../resource-governor/resource-governor.md) eingeschränkt ist, eine komprimierte Sicherung mit niedriger Priorität zu erstellen, wenn CPU-Konflikte bestehen.</span><span class="sxs-lookup"><span data-stu-id="06517-104">Therefore, you might want to create a low-priority compressed backup in a session whose CPU usage is limited by[Resource Governor](../resource-governor/resource-governor.md) when CPU contention occurs.</span></span> <span data-ttu-id="06517-105">In diesem Thema wird ein Szenario dargestellt, in dem die Sitzungen eines bestimmten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Benutzers klassifiziert werden, indem diese einer Arbeitsauslastungsgruppe der Ressourcenkontrolle zugeordnet werden, die die CPU-Nutzung in solchen Fällen einschränkt.</span><span class="sxs-lookup"><span data-stu-id="06517-105">This topic presents a scenario that classifies the sessions of a particular [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user by mapping them to a Resource Governor workload group that limits CPU usage in such cases.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="06517-106">In einem Szenario für Ressourcenkontrolle kann die Klassifizierung der Sitzungen auf einem Benutzernamen, einem Anwendungsnamen oder einem beliebigen anderen Element basieren, anhand dessen Verbindungen voneinander unterschieden werden können.</span><span class="sxs-lookup"><span data-stu-id="06517-106">In a given Resource Governor scenario, session classification might be based on a user name, an application name, or anything else that can differentiate a connection.</span></span> <span data-ttu-id="06517-107">Weitere Informationen finden Sie unter [Resource Governor Classifier Function](../resource-governor/resource-governor-classifier-function.md) und [Resource Governor Workload Group](../resource-governor/resource-governor-workload-group.md).</span><span class="sxs-lookup"><span data-stu-id="06517-107">For more information, see [Resource Governor Classifier Function](../resource-governor/resource-governor-classifier-function.md) and [Resource Governor Workload Group](../resource-governor/resource-governor-workload-group.md).</span></span>  
  
##  <a name="this-topic-contains-the-following-set-of-scenarios-which-are-presented-in-sequence"></a><a name="Top"></a> <span data-ttu-id="06517-108">Dieses Thema enthält die folgenden Szenarien, die nacheinander dargestellt werden:</span><span class="sxs-lookup"><span data-stu-id="06517-108">This topic contains the following set of scenarios, which are presented in sequence:</span></span>  
  
1.  [<span data-ttu-id="06517-109">Einrichten einer Anmeldung und eines Benutzers für Vorgänge mit niedriger Priorität</span><span class="sxs-lookup"><span data-stu-id="06517-109">Setting Up a Login and User for Low-Priority Operations</span></span>](#setup_login_and_user)  
  
2.  [<span data-ttu-id="06517-110">Konfigurieren der Ressourcenkontrolle zum Einschränken der CPU-Nutzung</span><span class="sxs-lookup"><span data-stu-id="06517-110">Configuring Resource Governor to Limit CPU Usage</span></span>](#configure_RG)  
  
3.  [<span data-ttu-id="06517-111">Überprüfen der Klassifizierung der aktuellen Sitzung (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="06517-111">Verifying the Classification of the Current Session (Transact-SQL)</span></span>](#verifying)  
  
4.  [<span data-ttu-id="06517-112">Komprimieren von Sicherungen in einer Sitzung mit CPU-Grenzwert</span><span class="sxs-lookup"><span data-stu-id="06517-112">Compressing Backups Using a Session with Limited CPU</span></span>](#creating_compressed_backup)  
  
##  <a name="setting-up-a-login-and-user-for-low-priority-operations"></a><a name="setup_login_and_user"></a> <span data-ttu-id="06517-113">Einrichten einer Anmeldung und eines Benutzers für Vorgänge mit niedriger Priorität</span><span class="sxs-lookup"><span data-stu-id="06517-113">Setting Up a Login and User for Low-Priority Operations</span></span>  
 <span data-ttu-id="06517-114">Für das Szenario in diesem Thema sind eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Anmeldung und ein zugehöriger Benutzer für Vorgänge mit niedriger Priorität erforderlich.</span><span class="sxs-lookup"><span data-stu-id="06517-114">The scenario in this topic requires a low-priority [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login and user.</span></span> <span data-ttu-id="06517-115">Mithilfe des Benutzernamens werden die in der Anmeldung ausgeführten Sitzungen klassifiziert und an eine Arbeitsauslastungsgruppe der Ressourcenkontrolle weitergeleitet, die die CPU-Nutzung einschränkt.</span><span class="sxs-lookup"><span data-stu-id="06517-115">The user name will be used to classify sessions running in the login and route them to a Resource Governor workload group that limits CPU usage.</span></span>  
  
 <span data-ttu-id="06517-116">Im folgenden Verfahren werden die Schritte zum Einrichten einer Anmeldung und eines Benutzers zu diesem Zweck beschrieben. Darauf folgt das [!INCLUDE[tsql](../../includes/tsql-md.md)]-Beispiel „Beispiel A: Einrichten einer Anmeldung und eines Benutzers (Transact-SQL).“</span><span class="sxs-lookup"><span data-stu-id="06517-116">The following procedure describes the steps for setting up a login and user for this purpose, followed by a [!INCLUDE[tsql](../../includes/tsql-md.md)] example, "Example A: Setting Up a Login and User (Transact-SQL)."</span></span>  
  
### <a name="to-set-up-a-login-and-database-user-for-classifying-sessions"></a><span data-ttu-id="06517-117">So richten Sie eine Anmeldung und einen Datenbankbenutzer zum Klassifizieren von Sitzungen ein</span><span class="sxs-lookup"><span data-stu-id="06517-117">To set up a login and database user for classifying sessions</span></span>  
  
1.  <span data-ttu-id="06517-118">Erstellen Sie eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Anmeldung zum Erstellen komprimierter Sicherungen mit niedriger Priorität.</span><span class="sxs-lookup"><span data-stu-id="06517-118">Create a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login for creating low-priority compressed backups.</span></span>  
  
     <span data-ttu-id="06517-119">**So erstellen Sie eine Anmeldung**</span><span class="sxs-lookup"><span data-stu-id="06517-119">**To create a login**</span></span>  
  
    -   [<span data-ttu-id="06517-120">Erstellen eines Anmeldenamens</span><span class="sxs-lookup"><span data-stu-id="06517-120">Create a Login</span></span>](../security/authentication-access/create-a-login.md)  
  
    -   [<span data-ttu-id="06517-121">CREATE LOGIN &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="06517-121">CREATE LOGIN &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-login-transact-sql)  
  
2.  <span data-ttu-id="06517-122">Sie können dieser Anmeldung die VIEW SERVER STATE-Berechtigung erteilen.</span><span class="sxs-lookup"><span data-stu-id="06517-122">Optionally, grant VIEW SERVER STATE to this login.</span></span>  
  
    -   [<span data-ttu-id="06517-123">GRANT (Berechtigungen für Systemobjekte) &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="06517-123">GRANT System Object Permissions &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/grant-system-object-permissions-transact-sql)  
  
     <span data-ttu-id="06517-124">Weitere Informationen finden Sie unter [GRANT (Berechtigungen für Datenbankprinzipal) &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-principal-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="06517-124">For more information, see [GRANT Database Principal Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-principal-permissions-transact-sql).</span></span>  
  
3.  <span data-ttu-id="06517-125">Erstellen Sie einen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Benutzer für diese Anmeldung.</span><span class="sxs-lookup"><span data-stu-id="06517-125">Create a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user for this login.</span></span>  
  
     <span data-ttu-id="06517-126">**So erstellen Sie einen Benutzer**</span><span class="sxs-lookup"><span data-stu-id="06517-126">**To create a user**</span></span>  
  
    -   [<span data-ttu-id="06517-127">Erstellen eines Datenbankbenutzers</span><span class="sxs-lookup"><span data-stu-id="06517-127">Create a Database User</span></span>](../security/authentication-access/create-a-database-user.md)  
  
    -   [<span data-ttu-id="06517-128">CREATE USER &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="06517-128">CREATE USER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-user-transact-sql)  
  
4.  <span data-ttu-id="06517-129">Fügen Sie den Benutzer der Datenbankrolle db_backupoperator der Datenbank hinzu, damit für die Anmeldung Sitzungen möglich sind und der Benutzer eine Datenbank sichern kann.</span><span class="sxs-lookup"><span data-stu-id="06517-129">To enable sessions of this login and user to back up a given database, add the user to the db_backupoperator database role of that database.</span></span> <span data-ttu-id="06517-130">Wiederholen Sie diesen Schritt für alle Datenbanken, die gesichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="06517-130">Do this for each database that this user will back up.</span></span> <span data-ttu-id="06517-131">Sie können den Benutzer auch anderen festen Datenbankrollen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="06517-131">Optionally, add the user to other fixed database roles.</span></span>  
  
     <span data-ttu-id="06517-132">**So fügen Sie einen Benutzer einer festen Datenbankrolle hinzu**</span><span class="sxs-lookup"><span data-stu-id="06517-132">**To add a user to a fixed database role**</span></span>  
  
    -   [<span data-ttu-id="06517-133">sp_addrolemember &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="06517-133">sp_addrolemember &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-addrolemember-transact-sql)  
  
     <span data-ttu-id="06517-134">Weitere Informationen finden Sie unter [GRANT (Berechtigungen für Datenbankprinzipal) &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-principal-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="06517-134">For more information, see [GRANT Database Principal Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-principal-permissions-transact-sql).</span></span>  
  
### <a name="example-a-setting-up-a-login-and-user-transact-sql"></a><span data-ttu-id="06517-135">Beispiel A: Einrichten einer Anmeldung und eines Benutzers (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="06517-135">Example A: Setting Up a Login and User (Transact-SQL)</span></span>  
 <span data-ttu-id="06517-136">Das folgende Beispiel ist nur dann relevant, wenn Sie eine neue [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Anmeldung und einen zugehörigen Benutzer für Sicherungen mit niedriger Priorität erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="06517-136">The following example is relevant only if you choose to create a new [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login and user for low-priority backups.</span></span> <span data-ttu-id="06517-137">Alternativ können Sie eine vorhandene Anmeldung und einen vorhandenen Benutzer verwenden, wenn entsprechende vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="06517-137">Alternatively, you can use an existing login and user, if an appropriate one exists.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="06517-138">Im folgenden Beispiel werden eine Beispielanmeldung und ein Beispielbenutzername, *domain_name*`\MAX_CPU`, verwendet.</span><span class="sxs-lookup"><span data-stu-id="06517-138">The following example uses a sample login and user name, *domain_name*`\MAX_CPU`.</span></span> <span data-ttu-id="06517-139">Ersetzen Sie diese durch die Namen der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Anmeldung und des zugehörigen Benutzers, die beim Erstellen komprimierter Sicherungen mit niedriger Priorität verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="06517-139">Replace these with the names of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login and user that you plan to use when creating your low-priority compressed backups.</span></span>  
  
 <span data-ttu-id="06517-140">In diesem Beispiel wird eine Anmeldung für das Windows-Konto *domain_name*`\MAX_CPU` erstellt, und dieser wird anschließend die VIEW SERVER STATE-Berechtigung erteilt.</span><span class="sxs-lookup"><span data-stu-id="06517-140">This example creates a login for the *domain_name*`\MAX_CPU` Windows account and then grants VIEW SERVER STATE permission to the login.</span></span> <span data-ttu-id="06517-141">Mit dieser Berechtigung können Sie die Klassifizierung der Sitzungen der Anmeldung durch die Ressourcenkontrolle überprüfen.</span><span class="sxs-lookup"><span data-stu-id="06517-141">This permission enables you to verify the Resource Governor classification of sessions of the login.</span></span> <span data-ttu-id="06517-142">Im Beispiel wird anschließend ein Benutzer für *domain_name*`\MAX_CPU` erstellt, und dieser wird der festen Datenbankrolle db_backupoperator für die [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] -Beispieldatenbank hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="06517-142">The example then creates a user for *domain_name*`\MAX_CPU` and adds it to the db_backupoperator fixed database role for the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] sample database.</span></span> <span data-ttu-id="06517-143">Dieser Benutzername wird von der Klassifizierungsfunktion der Ressourcenkontrolle verwendet.</span><span class="sxs-lookup"><span data-stu-id="06517-143">This user name will be used by the Resource Governor classifier function.</span></span>  
  
```sql  
-- Create a SQL Server login for low-priority operations  
USE master;  
CREATE LOGIN [domain_name\MAX_CPU] FROM WINDOWS;  
GRANT VIEW SERVER STATE TO [domain_name\MAX_CPU];  
GO  
-- Create a SQL Server user in AdventureWorks2012 for this login  
USE AdventureWorks2012;  
CREATE USER [domain_name\MAX_CPU] FOR LOGIN [domain_name\MAX_CPU];  
EXEC sp_addrolemember 'db_backupoperator', 'domain_name\MAX_CPU';  
GO  
  
```  
  
 [<span data-ttu-id="06517-144">&#91;Nach oben&#93;</span><span class="sxs-lookup"><span data-stu-id="06517-144">&#91;Top&#93;</span></span>](#Top)  
  
##  <a name="configuring-resource-governor-to-limit-cpu-usage"></a><a name="configure_RG"></a> <span data-ttu-id="06517-145">Konfigurieren der Ressourcenkontrolle zum Einschränken der CPU-Nutzung</span><span class="sxs-lookup"><span data-stu-id="06517-145">Configuring Resource Governor to Limit CPU Usage</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="06517-146">Stellen Sie sicher, dass die Ressourcenkontrolle aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="06517-146">Ensure that Resource Governor is enabled.</span></span> <span data-ttu-id="06517-147">Weitere Informationen finden Sie unter [Aktivieren der Ressourcenkontrolle](../resource-governor/enable-resource-governor.md).</span><span class="sxs-lookup"><span data-stu-id="06517-147">For more information, see [Enable Resource Governor](../resource-governor/enable-resource-governor.md).</span></span>  
  
 <span data-ttu-id="06517-148">In diesem Szenario für Ressourcenkontrolle besteht die Konfiguration aus den folgenden grundlegenden Schritten:</span><span class="sxs-lookup"><span data-stu-id="06517-148">In this Resource Governor scenario, configuration comprises the following basic steps:</span></span>  
  
1.  <span data-ttu-id="06517-149">Erstellen und konfigurieren Sie einen Ressourcenpool für die Ressourcenkontrolle zum Einschränken der maximalen durchschnittlichen CPU-Bandbreite für alle Anforderungen im Ressourcenpool, wenn CPU-Konflikte bestehen.</span><span class="sxs-lookup"><span data-stu-id="06517-149">Create and configure a Resource Governor resource pool that limits the maximum average CPU bandwidth that will be given to requests in the resource pool when CPU contention occurs.</span></span>  
  
2.  <span data-ttu-id="06517-150">Erstellen und konfigurieren Sie eine Arbeitsauslastungsgruppe der Ressourcenkontrolle, die diesen Pool verwendet.</span><span class="sxs-lookup"><span data-stu-id="06517-150">Create and configure a Resource Governor workload group that uses this pool.</span></span>  
  
3.  <span data-ttu-id="06517-151">Erstellen Sie eine *Klassifizierungsfunktion*. Dabei handelt es sich um eine benutzerdefinierte Funktion (User-Defined Function, UDF), deren Rückgabewerte von Resource Governor verwendet wird, um Sitzungen zu klassifizieren, sodass diese an die entsprechende Arbeitsauslastungsgruppe weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="06517-151">Create a *classifier function*, which is a user-defined function (UDF) whose return values are used by Resource Governor for classifying sessions so that they are routed to the appropriate workload group.</span></span>  
  
4.  <span data-ttu-id="06517-152">Registrieren Sie die Klassifizierungsfunktion bei der Ressourcenkontrolle.</span><span class="sxs-lookup"><span data-stu-id="06517-152">Register the classifier function with Resource Governor.</span></span>  
  
5.  <span data-ttu-id="06517-153">Wenden Sie die Änderungen auf die Konfiguration im Arbeitsspeicher der Ressourcenkontrolle an.</span><span class="sxs-lookup"><span data-stu-id="06517-153">Apply the changes to the Resource Governor in-memory configuration.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="06517-154">Informationen zu Ressourcenpools der von Resource Governor, Arbeitsauslastungsgruppen und Klassifizierung finden Sie unter [Ressourcenkontrolle](../resource-governor/resource-governor.md).</span><span class="sxs-lookup"><span data-stu-id="06517-154">For information about Resource Governor resource pools, workload groups, and classification, see [Resource Governor](../resource-governor/resource-governor.md).</span></span>  
  
 <span data-ttu-id="06517-155">Die [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen für diese Schritte werden unter "So konfigurieren Sie die Ressourcenkontrolle zum Einschränken der CPU-Nutzung" beschrieben, worauf ein [!INCLUDE[tsql](../../includes/tsql-md.md)] -Beispiel für die Vorgehensweise folgt.</span><span class="sxs-lookup"><span data-stu-id="06517-155">The [!INCLUDE[tsql](../../includes/tsql-md.md)] statements for these steps are described in the procedure, "To configure Resource Governor for limiting CPU usage," which is followed by a [!INCLUDE[tsql](../../includes/tsql-md.md)] example of the procedure.</span></span>  
  
 <span data-ttu-id="06517-156">**So konfigurieren Sie die Ressourcenkontrolle (SQL Server Management Studio)**</span><span class="sxs-lookup"><span data-stu-id="06517-156">**To configure Resource Governor (SQL Server Management Studio)**</span></span>  
  
-   [<span data-ttu-id="06517-157">Konfigurieren der Ressourcenkontrolle mit einer Vorlage</span><span class="sxs-lookup"><span data-stu-id="06517-157">Configure Resource Governor Using a Template</span></span>](../resource-governor/configure-resource-governor-using-a-template.md)  
  
-   [<span data-ttu-id="06517-158">Erstellen eines Ressourcenpools</span><span class="sxs-lookup"><span data-stu-id="06517-158">Create a Resource Pool</span></span>](../resource-governor/create-a-resource-pool.md)  
  
-   [<span data-ttu-id="06517-159">Erstellen einer Arbeitsauslastungsgruppe</span><span class="sxs-lookup"><span data-stu-id="06517-159">Create a Workload Group</span></span>](../resource-governor/create-a-workload-group.md)  
  
### <a name="to-configure-resource-governor-for-limiting-cpu-usage-transact-sql"></a><span data-ttu-id="06517-160">So konfigurieren Sie die Ressourcenkontrolle zum Einschränken der CPU-Nutzung (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="06517-160">To configure Resource Governor for limiting CPU usage (Transact-SQL)</span></span>  
  
1.  <span data-ttu-id="06517-161">Geben Sie eine [CREATE RESOURCE POOL](/sql/t-sql/statements/create-resource-pool-transact-sql) -Anweisung aus, um einen Ressourcenpool zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="06517-161">Issue a [CREATE RESOURCE POOL](/sql/t-sql/statements/create-resource-pool-transact-sql) statement to create a resource pool.</span></span> <span data-ttu-id="06517-162">Im Beispiel für diese Vorgehensweise wird die folgende Syntax verwendet:</span><span class="sxs-lookup"><span data-stu-id="06517-162">The example for this procedure uses the following syntax:</span></span>  
  
     <span data-ttu-id="06517-163">*CREATE RESOURCE POOL pool_name* WITH ( MAX_CPU_PERCENT = *value* );</span><span class="sxs-lookup"><span data-stu-id="06517-163">*CREATE RESOURCE POOL pool_name* WITH ( MAX_CPU_PERCENT = *value* );</span></span>  
  
     <span data-ttu-id="06517-164">*Value* ist ein ganzzahliger Wert zwischen 1 und 100, der den Prozentsatz der maximalen durchschnittlichen CPU-Bandbreite angibt.</span><span class="sxs-lookup"><span data-stu-id="06517-164">*Value* is an integer from 1 to 100 that indicates the percentage of maximum average CPU bandwidth.</span></span> <span data-ttu-id="06517-165">Der korrekte Wert hängt von der Umgebung ab.</span><span class="sxs-lookup"><span data-stu-id="06517-165">The appropriate value depends on your environment.</span></span> <span data-ttu-id="06517-166">Zur Veranschaulichung wird im Beispiel in diesem Thema der Wert 20 % (MAX_CPU_PERCENT = 20) verwendet.</span><span class="sxs-lookup"><span data-stu-id="06517-166">For the purpose of illustration, the example in this topic uses 20%  percent (MAX_CPU_PERCENT = 20.)</span></span>  
  
2.  <span data-ttu-id="06517-167">Geben Sie eine [CREATE WORKLOAD GROUP](/sql/t-sql/statements/create-workload-group-transact-sql) -Anweisung aus, um eine Arbeitsauslastungsgruppe für Vorgänge mit niedriger Priorität zu erstellen, deren CPU-Nutzung kontrolliert werden soll.</span><span class="sxs-lookup"><span data-stu-id="06517-167">Issue a [CREATE WORKLOAD GROUP](/sql/t-sql/statements/create-workload-group-transact-sql) statement to create a workload group for low-priority operations whose CPU usage you want to govern.</span></span> <span data-ttu-id="06517-168">Im Beispiel für diese Vorgehensweise wird die folgende Syntax verwendet:</span><span class="sxs-lookup"><span data-stu-id="06517-168">The example for this procedure uses the following syntax:</span></span>  
  
     <span data-ttu-id="06517-169">CREATE WORKLOAD GROUP *group_name* USING *pool_name*;</span><span class="sxs-lookup"><span data-stu-id="06517-169">CREATE WORKLOAD GROUP *group_name* USING *pool_name*;</span></span>  
  
3.  <span data-ttu-id="06517-170">Geben Sie eine [CREATE FUNCTION](/sql/t-sql/statements/create-function-transact-sql) -Anweisung aus, um eine Klassifizierungsfunktion zu erstellen, die die im vorherigen Schritt erstellte Arbeitsauslastungsgruppe dem Benutzer mit der Anmeldung mit niedriger Priorität zuordnet.</span><span class="sxs-lookup"><span data-stu-id="06517-170">Issue a [CREATE FUNCTION](/sql/t-sql/statements/create-function-transact-sql) statement to create a classifier function that maps the workload group created in the preceding step to the user of the low-priority login.</span></span> <span data-ttu-id="06517-171">Im Beispiel für diese Vorgehensweise wird die folgende Syntax verwendet:</span><span class="sxs-lookup"><span data-stu-id="06517-171">The example for this procedure uses the following syntax:</span></span>  
  
     <span data-ttu-id="06517-172">CREATE FUNCTION [*schema_name*.]*function_name*() RETURNS sysname</span><span class="sxs-lookup"><span data-stu-id="06517-172">CREATE FUNCTION [*schema_name*.]*function_name*() RETURNS sysname</span></span>  
  
     <span data-ttu-id="06517-173">WITH SCHEMABINDING</span><span class="sxs-lookup"><span data-stu-id="06517-173">WITH SCHEMABINDING</span></span>  
  
     <span data-ttu-id="06517-174">AS</span><span class="sxs-lookup"><span data-stu-id="06517-174">AS</span></span>  
  
     <span data-ttu-id="06517-175">BEGIN</span><span class="sxs-lookup"><span data-stu-id="06517-175">BEGIN</span></span>  
  
     <span data-ttu-id="06517-176">DEKLARIEREN SIE @workload_group_name ALS *sysname*</span><span class="sxs-lookup"><span data-stu-id="06517-176">DECLARE @workload_group_name AS *sysname*</span></span>  
  
     <span data-ttu-id="06517-177">IF (SUSER_NAME() = '*user_of_low_priority_login*')</span><span class="sxs-lookup"><span data-stu-id="06517-177">IF (SUSER_NAME() = '*user_of_low_priority_login*')</span></span>  
  
     <span data-ttu-id="06517-178">SET @workload_group_name = '*workload_group_name*'</span><span class="sxs-lookup"><span data-stu-id="06517-178">SET @workload_group_name = '*workload_group_name*'</span></span>  
  
     <span data-ttu-id="06517-179">RÜCKGABEWERT @workload_group_name</span><span class="sxs-lookup"><span data-stu-id="06517-179">RETURN @workload_group_name</span></span>  
  
     <span data-ttu-id="06517-180">ENDE</span><span class="sxs-lookup"><span data-stu-id="06517-180">END</span></span>  
  
     <span data-ttu-id="06517-181">Informationen zu den Komponenten dieser CREATE FUNCTION-Anweisung finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="06517-181">For information about the components of this CREATE FUNCTION statement, see:</span></span>  
  
    -   [<span data-ttu-id="06517-182">DECLARE @local_variable &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="06517-182">DECLARE @local_variable &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/declare-local-variable-transact-sql)  
  
    -   [<span data-ttu-id="06517-183">SUSER_SNAME &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="06517-183">SUSER_SNAME &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/suser-sname-transact-sql)  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="06517-184">SUSER_NAME ist nur eine von mehreren Systemfunktionen, die in einer Klassifizierungsfunktion verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="06517-184">SUSER_NAME is just one of several system functions that can be used in a classifier function.</span></span> <span data-ttu-id="06517-185">Weitere Informationen finden Sie unter [Erstellen und Testen einer benutzerdefinierten Klassifizierungsfunktion](../resource-governor/create-and-test-a-classifier-user-defined-function.md).</span><span class="sxs-lookup"><span data-stu-id="06517-185">For more information, see [Create and Test a Classifier User-Defined Function](../resource-governor/create-and-test-a-classifier-user-defined-function.md).</span></span>  
  
    -   <span data-ttu-id="06517-186">[SET @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/set-local-variable-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="06517-186">[SET @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/set-local-variable-transact-sql).</span></span>  
  
4.  <span data-ttu-id="06517-187">Geben Sie eine [ALTER RESOURCE GOVERNOR](/sql/t-sql/statements/alter-resource-governor-transact-sql) -Anweisung aus, um die Klassifizierungsfunktion bei der Ressourcenkontrolle zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="06517-187">Issue an [ALTER RESOURCE GOVERNOR](/sql/t-sql/statements/alter-resource-governor-transact-sql) statement to register the classifier function with Resource Governor.</span></span> <span data-ttu-id="06517-188">Im Beispiel für diese Vorgehensweise wird die folgende Syntax verwendet:</span><span class="sxs-lookup"><span data-stu-id="06517-188">The example for this procedure uses the following syntax:</span></span>  
  
     <span data-ttu-id="06517-189">ALTER RESOURCE GOVERNOR WITH (CLASSIFIER_FUNCTION = *schema_name*.*function_name*);</span><span class="sxs-lookup"><span data-stu-id="06517-189">ALTER RESOURCE GOVERNOR WITH (CLASSIFIER_FUNCTION = *schema_name*.*function_name*);</span></span>  
  
5.  <span data-ttu-id="06517-190">Geben Sie eine weitere ALTER RESOURCE GOVERNOR-Anweisung aus, um die Änderungen folgendermaßen auf die Konfiguration im Arbeitsspeicher der Ressourcenkontrolle anzuwenden:</span><span class="sxs-lookup"><span data-stu-id="06517-190">Issue a second ALTER RESOURCE GOVERNOR statement to apply the changes to the Resource Governor in-memory configuration, as follows:</span></span>  
  
    ```  
    ALTER RESOURCE GOVERNOR RECONFIGURE;  
    ```  
  
### <a name="example-b-configuring-resource-governor-transact-sql"></a><span data-ttu-id="06517-191">Beispiel B: Konfigurieren des Resource Governor (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="06517-191">Example B: Configuring Resource Governor (Transact-SQL)</span></span>  
 <span data-ttu-id="06517-192">Im folgenden Beispiel werden die folgenden Schritte in einer einzelnen Transaktion ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="06517-192">The following example performs the following steps within a single transaction:</span></span>  
  
1.  <span data-ttu-id="06517-193">Der `pMAX_CPU_PERCENT_20` -Ressourcenpool wird erstellt.</span><span class="sxs-lookup"><span data-stu-id="06517-193">Creates the `pMAX_CPU_PERCENT_20` resource pool.</span></span>  
  
2.  <span data-ttu-id="06517-194">Die `gMAX_CPU_PERCENT_20` -Arbeitsauslastungsgruppe wird erstellt.</span><span class="sxs-lookup"><span data-stu-id="06517-194">Creates the `gMAX_CPU_PERCENT_20` workload group.</span></span>  
  
3.  <span data-ttu-id="06517-195">Die `rgclassifier_MAX_CPU()` -Klassifizierungsfunktion, die den im vorherigen Beispiel erstellten Benutzernamen verwendet, wird erstellt.</span><span class="sxs-lookup"><span data-stu-id="06517-195">Creates the `rgclassifier_MAX_CPU()` classifier function, which uses the user name created in the preceding example.</span></span>  
  
4.  <span data-ttu-id="06517-196">Die Klassifizierungsfunktion wird bei der Ressourcenkontrolle registriert.</span><span class="sxs-lookup"><span data-stu-id="06517-196">Registers the classifier function with Resource Governor.</span></span>  
  
 <span data-ttu-id="06517-197">Nachdem für die Transaktion ein Commit ausgeführt wurde, werden im Beispiel alle Konfigurationsänderungen angewendet, die in der ALTER WORKLOAD GROUP-Anweisung oder der ALTER RESOURCE POOL-Anweisung angefordert wurden.</span><span class="sxs-lookup"><span data-stu-id="06517-197">After committing the transaction, the example applies the configuration changes requested in the ALTER WORKLOAD GROUP or ALTER RESOURCE POOL statements.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="06517-198">Im folgenden Beispiel wird der Benutzername des Beispiel-[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Benutzers verwendet, der unter „Beispiel A: Einrichten einer Anmeldung und eines Benutzers (Transact-SQL)“ als *domain_name*`\MAX_CPU` erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="06517-198">The following example uses the user name of the sample [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user created in "Example A: Setting Up a Login and User (Transact-SQL)," *domain_name*`\MAX_CPU`.</span></span> <span data-ttu-id="06517-199">Ersetzen Sie diesen durch den Namen des Benutzers der Anmeldung, die zum Erstellen komprimierter Sicherungen mit niedriger Priorität verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="06517-199">Replace this with the name of the user of the login that you plan to use for creating low-priority compressed backups.</span></span>  
  
```sql  
-- Configure Resource Governor.  
BEGIN TRAN  
USE master;  
-- Create a resource pool that sets the MAX_CPU_PERCENT to 20%.   
CREATE RESOURCE POOL pMAX_CPU_PERCENT_20  
   WITH  
      (MAX_CPU_PERCENT = 20);  
GO  
-- Create a workload group to use this pool.   
CREATE WORKLOAD GROUP gMAX_CPU_PERCENT_20  
USING pMAX_CPU_PERCENT_20;  
GO  
-- Create a classification function.  
-- Note that any request that does not get classified goes into   
-- the 'Default' group.  
CREATE FUNCTION dbo.rgclassifier_MAX_CPU() RETURNS sysname   
WITH SCHEMABINDING  
AS  
BEGIN  
    DECLARE @workload_group_name AS sysname  
      IF (SUSER_NAME() = 'domain_name\MAX_CPU')  
          SET @workload_group_name = 'gMAX_CPU_PERCENT_20'  
    RETURN @workload_group_name  
END;  
GO  
  
-- Register the classifier function with Resource Governor.  
ALTER RESOURCE GOVERNOR WITH (CLASSIFIER_FUNCTION= dbo.rgclassifier_MAX_CPU);  
COMMIT TRAN;  
GO  
-- Start Resource Governor  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
  
```  
  
 [<span data-ttu-id="06517-200">&#91;Nach oben&#93;</span><span class="sxs-lookup"><span data-stu-id="06517-200">&#91;Top&#93;</span></span>](#Top)  
  
##  <a name="verifying-the-classification-of-the-current-session-transact-sql"></a><a name="verifying"></a> <span data-ttu-id="06517-201">Überprüfen der Klassifizierung der aktuellen Sitzung (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="06517-201">Verifying the Classification of the Current Session (Transact-SQL)</span></span>  
 <span data-ttu-id="06517-202">Melden Sie sich optional als der Benutzer an, den Sie in der Klassifizierungsfunktion angegeben haben, und überprüfen Sie die Sitzungsklassifizierung durch Ausgeben der folgenden [SELECT](/sql/t-sql/queries/select-transact-sql) -Anweisung im Objekt-Explorer:</span><span class="sxs-lookup"><span data-stu-id="06517-202">Optionally, log in as the user that you specified in your classifier function, and verify the session classification by issuing the following [SELECT](/sql/t-sql/queries/select-transact-sql) statement in Object Explorer:</span></span>  
  
```sql  
USE master;  
SELECT sess.session_id, sess.login_name, sess.group_id, grps.name   
FROM sys.dm_exec_sessions AS sess   
JOIN sys.dm_resource_governor_workload_groups AS grps   
    ON sess.group_id = grps.group_id  
WHERE session_id > 50;  
GO  
```  
  
 <span data-ttu-id="06517-203">Im Ergebnisbereich sollte in der Spalte **Name** mindestens eine Sitzung für den Namen der Arbeitsauslastungsgruppe aufgeführt werden, den Sie in der Klassifizierungsfunktion angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="06517-203">In the results pane, the **name** column should list one or more sessions for the workload-group name that you specified in your classifier function.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="06517-204">Informationen zu den dynamischen Verwaltungssichten, die von dieser SELECT-Anweisung aufgerufen werden, finden Sie unter [sys.dm_exec_sessions &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-sessions-transact-sql) und [sys.dm_resource_governor_workload_groups &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-resource-governor-workload-groups-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="06517-204">For information about the dynamic management views called by this SELECT statement, see [sys.dm_exec_sessions &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-sessions-transact-sql) and [sys.dm_resource_governor_workload_groups &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-resource-governor-workload-groups-transact-sql).</span></span>  
  
 [<span data-ttu-id="06517-205">&#91;Nach oben&#93;</span><span class="sxs-lookup"><span data-stu-id="06517-205">&#91;Top&#93;</span></span>](#Top)  
  
##  <a name="compressing-backups-using-a-session-with-limited-cpu"></a><a name="creating_compressed_backup"></a> <span data-ttu-id="06517-206">Komprimieren von Sicherungen in einer Sitzung mit CPU-Grenzwert</span><span class="sxs-lookup"><span data-stu-id="06517-206">Compressing Backups Using a Session with Limited CPU</span></span>  
 <span data-ttu-id="06517-207">Melden Sie sich zum Erstellen einer komprimierten Sicherung in einer Sitzung mit maximalem CPU-Grenzwert als der Benutzer an, der in der Klassifizierungsfunktion angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="06517-207">To create a compressed backup in a session with a limited maximum CPU, log in as the user specified in your classifier function.</span></span> <span data-ttu-id="06517-208">Geben Sie im Backup-Befehl entweder with Compression ( [!INCLUDE[tsql](../../includes/tsql-md.md)] ) an, oder wählen Sie **Sicherung komprimieren** ( [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ) aus.</span><span class="sxs-lookup"><span data-stu-id="06517-208">In your backup command, either specify WITH COMPRESSION ([!INCLUDE[tsql](../../includes/tsql-md.md)]) or select **Compress backup** ([!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]).</span></span> <span data-ttu-id="06517-209">Informationen zum Erstellen einer komprimierten Datenbanksicherung finden Sie unter [Erstellen einer vollständigen Datenbanksicherung &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="06517-209">To create a compressed database backup, see [Create a Full Database Backup &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md).</span></span>  
  
### <a name="example-c-creating-a-compressed-backup-transact-sql"></a><span data-ttu-id="06517-210">Beispiel C: Erstellen einer komprimierten Sicherung (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="06517-210">Example C: Creating a Compressed Backup (Transact-SQL)</span></span>  
 <span data-ttu-id="06517-211">Im folgenden [BACKUP](/sql/t-sql/statements/backup-transact-sql) -Beispiel wird eine komprimierte, vollständige Sicherung der [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] -Datenbank in der neu formatierten Sicherungsdatei `Z:\SQLServerBackups\AdvWorksData.bak`erstellt.</span><span class="sxs-lookup"><span data-stu-id="06517-211">The following [BACKUP](/sql/t-sql/statements/backup-transact-sql) example creates a compressed full backup of the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] database in a newly formatted backup file, `Z:\SQLServerBackups\AdvWorksData.bak`.</span></span>  
  
```sql  
--Run backup statement in the gBackup session.  
BACKUP DATABASE AdventureWorks2012 TO DISK='Z:\SQLServerBackups\AdvWorksData.bak'   
WITH   
   FORMAT,   
   MEDIADESCRIPTION='AdventureWorks2012 Compressed Data Backups'  
   DESCRIPTION='First database backup on AdventureWorks2012 Compressed Data Backups media set'  
   COMPRESSION;  
GO  
```  
  
 [<span data-ttu-id="06517-212">&#91;Nach oben&#93;</span><span class="sxs-lookup"><span data-stu-id="06517-212">&#91;Top&#93;</span></span>](#Top)  
  
## <a name="see-also"></a><span data-ttu-id="06517-213">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="06517-213">See Also</span></span>  
 <span data-ttu-id="06517-214">[Erstellen und Testen einer benutzerdefinierten Klassifizierungsfunktion](../resource-governor/create-and-test-a-classifier-user-defined-function.md) </span><span class="sxs-lookup"><span data-stu-id="06517-214">[Create and Test a Classifier User-Defined Function](../resource-governor/create-and-test-a-classifier-user-defined-function.md) </span></span>  
 [<span data-ttu-id="06517-215">Ressourcenkontrolle</span><span class="sxs-lookup"><span data-stu-id="06517-215">Resource Governor</span></span>](../resource-governor/resource-governor.md)  
  
  
