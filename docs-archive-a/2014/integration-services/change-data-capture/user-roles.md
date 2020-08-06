---
title: Benutzer Rollen für Change Data Capture Service für Oracle von Attunity | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: be0ec384-e03b-4483-96ca-02b289804d6a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e694da0cfd8645fe594b049b6dc2394b55d1bb55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720293"
---
# <a name="user-roles-for-change-data-capture-service-for-oracle-by-attunity"></a><span data-ttu-id="9c6ed-102">Benutzerrollen für Change Data Capture Service für Oracle von Attunity</span><span class="sxs-lookup"><span data-stu-id="9c6ed-102">User Roles for Change Data Capture Service for Oracle by Attunity</span></span>
  <span data-ttu-id="9c6ed-103">In diesem Abschnitt werden die Benutzerrollen für den Change Data Capture Service für Oracle von Attunity beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9c6ed-103">This section describes the user roles for the Change Data Capture Service for Oracle by Attunity.</span></span> <span data-ttu-id="9c6ed-104">Die beschriebenen Rollen sind [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbankrollen, Windows-Rollen und Oracle-Datenbankrollen.</span><span class="sxs-lookup"><span data-stu-id="9c6ed-104">The roles described are [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database roles, Windows roles, or Oracle database roles.</span></span>  
  
## <a name="windows-user-roles"></a><span data-ttu-id="9c6ed-105">Windows-Benutzerrollen</span><span class="sxs-lookup"><span data-stu-id="9c6ed-105">Windows User Roles</span></span>  
 <span data-ttu-id="9c6ed-106">Im Folgenden werden die vom Oracle CDC Service verwendeten Windows-Benutzerrollen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9c6ed-106">The following describes the Windows user roles used by the Oracle CDC Service.</span></span>  
  
### <a name="computer-administrator-oracle-cdc-service"></a><span data-ttu-id="9c6ed-107">Computeradministrator: Oracle CDC Service</span><span class="sxs-lookup"><span data-stu-id="9c6ed-107">Computer Administrator: Oracle CDC Service</span></span>  
 <span data-ttu-id="9c6ed-108">Der Computeradministrator ist ein Windows-Benutzer, der für das Erstellen und Verwalten des CDC Service auf dem Computer zuständig ist.</span><span class="sxs-lookup"><span data-stu-id="9c6ed-108">The computer administrator is a Windows user responsible for creating and maintaining the CDC Service on the computer.</span></span> <span data-ttu-id="9c6ed-109">Dieser Benutzer muss der Gruppe der lokalen Computeradministratoren angehören.</span><span class="sxs-lookup"><span data-stu-id="9c6ed-109">This user must belong to the group of local machine administrators.</span></span>  
  
 <span data-ttu-id="9c6ed-110">Zu den vom Oracle CDC Service-Computeradministrator ausgeführten Tasks gehört Folgendes:</span><span class="sxs-lookup"><span data-stu-id="9c6ed-110">The tasks performed by the Oracle CDC Service Computer Administrator include:</span></span>  
  
-   <span data-ttu-id="9c6ed-111">Installieren der CDC Service for Oracle-Software</span><span class="sxs-lookup"><span data-stu-id="9c6ed-111">Installing the CDC Service for Oracle software</span></span>  
  
-   <span data-ttu-id="9c6ed-112">Erstellen eines Oracle CDC-Windows-Diensts</span><span class="sxs-lookup"><span data-stu-id="9c6ed-112">Creating an Oracle CDC Windows service</span></span>  
  
-   <span data-ttu-id="9c6ed-113">Herstellen der CDC Service-Verbindung mit der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Zielinstanz (Verbindungszeichenfolge und Anmeldeinformationen)</span><span class="sxs-lookup"><span data-stu-id="9c6ed-113">Setting up the CDC Service connection to the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance (connection string and credentials)</span></span>  
  
-   <span data-ttu-id="9c6ed-114">Sicherstellen, dass das CDC Service-Masterkennwort als Schutz für die Oracle-Log Mining-Anmeldeinformationen verwendet wird</span><span class="sxs-lookup"><span data-stu-id="9c6ed-114">Ensuring that the CDC Service Master Password with which Oracle log mining credentials are protected</span></span>  
  
-   <span data-ttu-id="9c6ed-115">Löschen eines CDC Service-Windows-Diensts</span><span class="sxs-lookup"><span data-stu-id="9c6ed-115">Deleting a CDC Service Windows service</span></span>  
  
-   <span data-ttu-id="9c6ed-116">Deinstallieren der CDC Service for Oracle-Software</span><span class="sxs-lookup"><span data-stu-id="9c6ed-116">Uninstalling the CDC Service for Oracle software</span></span>  
  
-   <span data-ttu-id="9c6ed-117">Verwalten der CDC Service for Oracle-Software (z. B. Installation von Updates)</span><span class="sxs-lookup"><span data-stu-id="9c6ed-117">Maintaining the CDC Service for Oracle software (for example, installing updates)</span></span>  
  
-   <span data-ttu-id="9c6ed-118">Starten und Beenden eines CDC Service-Windows-Diensts</span><span class="sxs-lookup"><span data-stu-id="9c6ed-118">Starting and stopping a CDC Service Windows service</span></span>  
  
 <span data-ttu-id="9c6ed-119">Beim Verwenden von Konfigurationen mit hoher Verfügbarkeit, z. B. Microsoft-Failovercluster, muss der Computeradministrator über zusätzliche Zuständigkeiten und Berechtigungen verfügen, z. B.:</span><span class="sxs-lookup"><span data-stu-id="9c6ed-119">When working with high-availability configurations, such as Microsoft failover clusters, the computer administrator must have additional responsibilities and permissions such as:</span></span>  
  
-   <span data-ttu-id="9c6ed-120">Installation und Wartung der CDC Service for Oracle-Software auf allen Clusterknoten.</span><span class="sxs-lookup"><span data-stu-id="9c6ed-120">Installation and maintenance of the CDC Service for Oracle software on all cluster nodes.</span></span>  
  
-   <span data-ttu-id="9c6ed-121">Definition von generischen Clusterdienstressourcen für den CDC Service-Windows-Dienst auf den verschiedenen Clusterknoten.</span><span class="sxs-lookup"><span data-stu-id="9c6ed-121">Defining generic cluster service resources for the CDC Service' Windows service on the various cluster nodes.</span></span>  
  
-   <span data-ttu-id="9c6ed-122">Arbeit als Computeradministrator, der auf dem Computer, auf dem der CDC Service for Oracle installiert ist, als Administrator autorisiert ist.</span><span class="sxs-lookup"><span data-stu-id="9c6ed-122">Acting as the computer administrator authorized as an administrator on the computer where the CDC Service for Oracle is installed.</span></span> <span data-ttu-id="9c6ed-123">Diese Person installiert den CDC Service for Oracle und verwendet die CDC Service Configuration Console, um einen CDC Service for Oracle auf einem lokalen Computer zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="9c6ed-123">This person installs the CDC Service for Oracle and uses the CDC Service Configuration Console to configure a CDC Service for Oracle on a local computer.</span></span>  
  
### <a name="service-account-oracle-cdc-service"></a><span data-ttu-id="9c6ed-124">Dienstkonto: Oracle CDC Service</span><span class="sxs-lookup"><span data-stu-id="9c6ed-124">Service Account: Oracle CDC Service</span></span>  
 <span data-ttu-id="9c6ed-125">Dieses Oracle CDC Service-Windows-Dienstkonto ist ein Windows-Konto, das zum Ausführen des Oracle CDC Service (das Dienstkonto) verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9c6ed-125">This is Oracle CDC Service Windows Service Account is a Windows account used for running the Oracle CDC Service (the Service Account).</span></span>  
  
 <span data-ttu-id="9c6ed-126">Die einzige Berechtigung für das Dienstkonto, die erforderlich ist, ist die Möglichkeit der Verwendung des Oracle-Clients und des systemeigenen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC-Anbieters.</span><span class="sxs-lookup"><span data-stu-id="9c6ed-126">The only required privilege necessary for the service account is to be able to use the Oracle client and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native client ODBC provider.</span></span> <span data-ttu-id="9c6ed-127">Dieses Konto benötigt keinen Zugriff auf Dateien, es sei denn, dies ist für bestimmte Anbieter erforderlich (wenn z.B. die Verbindungszeichenfolge des Oracle-Clients auf Oracle-Datenbankinstanzen in der Datei **tnsnames.ora** verweist, muss das Dienstkonto für diese Datei über Lesezugriff verfügen).</span><span class="sxs-lookup"><span data-stu-id="9c6ed-127">This account does not need to access files unless required by specific providers (for example, if the Oracle client connection string references Oracle database instances in a **tnsnames.ora** file, then that file must be read-accessible to the service account).</span></span>  
  
 <span data-ttu-id="9c6ed-128">Beim Erstellen eines Oracle CDC Service unter Windows Vista oder Windows Server 2008 ist das Standarddienstkonto das Konto NETZWERKDIENST.</span><span class="sxs-lookup"><span data-stu-id="9c6ed-128">When creating an Oracle CDC Service on Windows Vista or Windows Server 2008, the default service account is the NETWORK SERVICE account.</span></span>  
  
 <span data-ttu-id="9c6ed-129">Unter Windows 7 und Windows Server 2008 R2 und höher ist das Standarddienstkonto NT-Dienst\\<Dienstname>.</span><span class="sxs-lookup"><span data-stu-id="9c6ed-129">On Windows 7, Windows Server 2008 R2 and later, the default service account is NT Service\\<service-name>.</span></span>  
  
 <span data-ttu-id="9c6ed-130">Wenn [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] auf einem anderen Computer ausgeführt wird oder eine gruppierte [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz ist und der Dienst per Windows-Authentifizierung eine Verbindung zum [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Ziel herstellen muss, sollte das Dienstkonto ein Domänenkonto sein.</span><span class="sxs-lookup"><span data-stu-id="9c6ed-130">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] runs on another machine or is a clustered [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance and there the service needs to connect to the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using Windows authentication, then the service account should be a domain account.</span></span>  
  
## <a name="sql-server-user-roles"></a><span data-ttu-id="9c6ed-131">SQL Server-Benutzerrollen</span><span class="sxs-lookup"><span data-stu-id="9c6ed-131">SQL Server User Roles</span></span>  
 <span data-ttu-id="9c6ed-132">Im Folgenden werden die vom Oracle CDC Service verwendeten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Benutzerrollen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9c6ed-132">The following describes the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user roles used by the Oracle CDC Service.</span></span>  
  
### <a name="oracle-cdc-service-administrator"></a><span data-ttu-id="9c6ed-133">Oracle CDC Service-Administrator</span><span class="sxs-lookup"><span data-stu-id="9c6ed-133">Oracle CDC Service Administrator</span></span>  
 <span data-ttu-id="9c6ed-134">Der CDC-Dienstadministrator ist ein [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Benutzer mit vollständiger Kontrolle über die Oracle CDC Service-Artefakte auf der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Zielinstanz.</span><span class="sxs-lookup"><span data-stu-id="9c6ed-134">The CDC Service Administrator is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user with full control over the Oracle CDC Service artifacts in the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="9c6ed-135">Der CDC-Dienstadministrator verwendet die Oracle CDC Designer Console, um Oracle CDC-Instanzen zu entwerfen.</span><span class="sxs-lookup"><span data-stu-id="9c6ed-135">The CDC Service Administrator uses the Oracle CDC Designer Console to design Oracle CDC Instances.</span></span>  
  
 <span data-ttu-id="9c6ed-136">Dem CDC Service-Administrator sollten die festen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Serverrollen **public** und **dbcreator**gewährt werden.</span><span class="sxs-lookup"><span data-stu-id="9c6ed-136">The CDC Service Administrator should be granted the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fixed server roles **public** and **dbcreator**.</span></span>  
  
 <span data-ttu-id="9c6ed-137">Zu den vom CDC Service-Administrator ausgeführten Tasks gehört Folgendes:</span><span class="sxs-lookup"><span data-stu-id="9c6ed-137">The tasks performed by the CDC Service Administrator include:</span></span>  
  
-   <span data-ttu-id="9c6ed-138">Vorbereiten einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz auf das Hosten von Oracle CDC-Instanzen (bei denen es sich um [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbanken handelt)</span><span class="sxs-lookup"><span data-stu-id="9c6ed-138">Preparing a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance to host Oracle CDC Instances (which are [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases).</span></span> <span data-ttu-id="9c6ed-139">In diesem Task wird auf der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz eine spezielle Datenbank mit dem Namen MSXDBCDC erstellt.</span><span class="sxs-lookup"><span data-stu-id="9c6ed-139">In this task, a special database called MSXDBCDC is created in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>  
  
-   <span data-ttu-id="9c6ed-140">Erstellen einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbank für die Oracle CDC-Instanz</span><span class="sxs-lookup"><span data-stu-id="9c6ed-140">Creating an Oracle CDC Instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="9c6ed-141">Dieser Task beinhaltet das Aktivieren der neu erstellten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbank für CDC, wofür ein [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Systemadministrator (**sysadmin**) erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="9c6ed-141">Task includes enabling the newly created [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database for CDC, which requires a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system administrator (**sysadmin**).</span></span>  
  
-   <span data-ttu-id="9c6ed-142">Entwerfen einer Oracle CDC-Instanz</span><span class="sxs-lookup"><span data-stu-id="9c6ed-142">Designing an Oracle CDC Instance.</span></span> <span data-ttu-id="9c6ed-143">Dieser Task beinhaltet das Bereitstellen von Informationen zur Oracle-Quelldatenbank und zu aufgezeichneten Tabellen, wofür ein Oracle-Datenbankadministrator erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="9c6ed-143">This task includes providing information about the source Oracle database and captured tables, which requires an Oracle database administrator.</span></span>  
  
-   <span data-ttu-id="9c6ed-144">Pflegen der Oracle CDC-Instanz, z. B. Hinzufügen/Entfernen von Aufzeichnungsinstanzen und Aktualisieren der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="9c6ed-144">Maintaining the Oracle CDC Instance over time, which includes adding/removing capture instances and updating configuration.</span></span>  
  
-   <span data-ttu-id="9c6ed-145">Aktivieren oder Deaktivieren einer Oracle CDC-Instanz</span><span class="sxs-lookup"><span data-stu-id="9c6ed-145">Enabling or disabling an Oracle CDC Instance.</span></span>  
  
-   <span data-ttu-id="9c6ed-146">Überwachen des Status einer Oracle CDC-Instanz</span><span class="sxs-lookup"><span data-stu-id="9c6ed-146">Monitoring the state of an Oracle CDC Instance.</span></span>  
  
-   <span data-ttu-id="9c6ed-147">Behandeln von Problemen, die sich auf die Oracle CDC-Instanz auswirken</span><span class="sxs-lookup"><span data-stu-id="9c6ed-147">Troubleshooting issues that affect the Oracle CDC Instance.</span></span>  
  
 <span data-ttu-id="9c6ed-148">Der CDC Service-Administrator ist, zumindest am Anfang, in der festen Datenbankrolle **db_owner** für die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC-Datenbank der Oracle CDC-Instanz zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="9c6ed-148">The CDC Service Administrator is, at least initially, in the **db_owner** fixed database role for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC database associated with the Oracle CDC Instance.</span></span> <span data-ttu-id="9c6ed-149">So erhält der CDC Service-Administrator Zugriff auf die in der CDC-Datenbank gespeicherten Änderungsdaten.</span><span class="sxs-lookup"><span data-stu-id="9c6ed-149">This gives the CDC Service Administrator access to the change data stored in the CDC database.</span></span> <span data-ttu-id="9c6ed-150">Nach der Erstellung kann die Rolle **db_owner** der CDC-Datenbank einem anderen Benutzer zugewiesen werden, der alle oben aufgeführten Tasks ausführen kann (mit Ausnahme der Vorbereitung einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz und der Erstellung einer weiteren Oracle CDC-Instanz).</span><span class="sxs-lookup"><span data-stu-id="9c6ed-150">Once created, the **db_owner** role of the CDC database can be assigned to a different user who can carry out all of the tasks listed above except for preparing a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance and creating another Oracle CDC Instance).</span></span>  
  
 <span data-ttu-id="9c6ed-151">Der CDC Service-Administrator muss dabei nicht das Masterkennwort kennen, das bei der Erstellung des Oracle CDC-Windows-Diensts angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="9c6ed-151">The CDC Service Administrator does not need to know the master password specified with the creation of the Oracle CDC Windows service.</span></span>  
  
### <a name="system-administrator"></a><span data-ttu-id="9c6ed-152">Systemadministrator</span><span class="sxs-lookup"><span data-stu-id="9c6ed-152">System Administrator</span></span>  
 <span data-ttu-id="9c6ed-153">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Systemadministrator ist ein [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Benutzer, dem die feste Serverrolle **sysadmin** für die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz gewährt werden sollte, die den Oracle CDC-Diensten zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="9c6ed-153">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system administrator is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user and should be granted the fixed server **sysadmin** role on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance associated with the Oracle CDC Service(s).</span></span>  
  
 <span data-ttu-id="9c6ed-154">Es ist nur ein Oracle CDC-spezifischer Task vorhanden, der über den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Systemadministrator ausgeführt wird. Dieser Task ist das Aktivieren der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbank für eine Oracle CDC-Instanz für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC.</span><span class="sxs-lookup"><span data-stu-id="9c6ed-154">There is only one Oracle CDC specific task that carried out with the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] System Administrator and that is to enable the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database for an Oracle CDC Instance for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC.</span></span> <span data-ttu-id="9c6ed-155">Dieser Task wird beim Erstellen einer neuen Oracle CDC-Instanz mit der Oracle CDC Designer Console ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="9c6ed-155">This task is performed using the Oracle CDC Designer console when creating a new Oracle CDC Instance.</span></span>  
  
### <a name="oracle-cdc-service-user"></a><span data-ttu-id="9c6ed-156">Oracle CDC Service-Benutzer</span><span class="sxs-lookup"><span data-stu-id="9c6ed-156">Oracle CDC Service User</span></span>  
 <span data-ttu-id="9c6ed-157">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Oracle CDC Service-Benutzer ist eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Anmeldung, die vom Oracle CDC Service verwendet wird, um die Arbeitsschritte mit der MSXDBCDC-Datenbank und mit allen von diesem Dienst behandelten Oracle CDC-Instanzen (CDC-Datenbanken) durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="9c6ed-157">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Oracle CDC Service user is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login which is used by the Oracle CDC Service to perform its work against the MSXDBCDC and all of the Oracle CDC Instances (CDC databases) handled by this service.</span></span>  
  
 <span data-ttu-id="9c6ed-158">Dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Oracle CDC Service-Benutzer sollte Folgendes gewährt werden:</span><span class="sxs-lookup"><span data-stu-id="9c6ed-158">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Oracle CDC Service user should be granted the following:</span></span>  
  
-   <span data-ttu-id="9c6ed-159">Mitglied der festen Datenbankrollen **db_dlladmin**, **db_datareader**und **db_datawriter** für alle CDC-Datenbanken, die vom Server behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="9c6ed-159">Member of the fixed database roles **db_dlladmin**, **db_datareader**, and **db_datawriter** for all CDC databases handled by the server.</span></span>  
  
-   <span data-ttu-id="9c6ed-160">Mitglied der festen Datenbankrollen **db_datareader** und **db_datawriter** für die MSXDBCDC-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="9c6ed-160">Member of the fixed database roles **db_datareader** and **db_datawriter** for the MSXDBCDC database.</span></span>  
  
 <span data-ttu-id="9c6ed-161">Da der Oracle CDC Service für die Verwendung aller CDC-Datenbanken und der MSXDBCDC-Datenbank eine einzelne [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Anmeldung verwendet, sollte diese Anmeldung in all diesen Datenbanken zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="9c6ed-161">Because the Oracle CDC Service uses a single [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to work with all CDC databases and the MSXDBCDC database, this login should be mapped in all of these databases.</span></span>  
  
### <a name="oracle-cdc-change-consumer"></a><span data-ttu-id="9c6ed-162">Oracle CDC Change Consumer</span><span class="sxs-lookup"><span data-stu-id="9c6ed-162">Oracle CDC Change Consumer</span></span>  
 <span data-ttu-id="9c6ed-163">Der Oracle CDC Change Consumer ist ein [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Benutzer, der Änderungen nutzt, die in den CDC-Tabellen der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Oracle CDC-Instanzdatenbank gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="9c6ed-163">The Oracle CDC Change Consumer is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user that consumes changes stored in the CDC tables in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Oracle CDC Instance database.</span></span>  
  
 <span data-ttu-id="9c6ed-164">Dieser Benutzer bestimmt die Benutzerrolle, die für den Zugriff auf die einzelnen CDC-Tabellen über die CDC-Funktionen erforderlich ist, die von der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC-Infrastruktur generiert werden.</span><span class="sxs-lookup"><span data-stu-id="9c6ed-164">This user determines the user role that is required for accessing each of the CDC tables through the CDC functions generated by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC infrastructure.</span></span> <span data-ttu-id="9c6ed-165">Wenn beim Angeben einer Aufzeichnungsinstanz keine Benutzerrolle angegeben wird, ist der Zugriff auf die Änderungen auf das Mitglied der festen Datenbankrolle **db_owner** der CDC-Datenbank beschränkt.</span><span class="sxs-lookup"><span data-stu-id="9c6ed-165">If no user role is specified when a capture instance is specified, access to the changes is limited to the member of the **db_owner** fixed database role of the CDC database.</span></span>  
  
## <a name="oracle-user-roles"></a><span data-ttu-id="9c6ed-166">Oracle-Benutzerrollen</span><span class="sxs-lookup"><span data-stu-id="9c6ed-166">Oracle User Roles</span></span>  
 <span data-ttu-id="9c6ed-167">Im Folgenden werden die vom Oracle CDC Service verwendeten Oracle-Benutzerrollen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9c6ed-167">The following describes the Oracle user roles used by the Oracle CDC Service.</span></span>  
  
### <a name="database-administrator-dba"></a><span data-ttu-id="9c6ed-168">Datenbankadministrator (DBA)</span><span class="sxs-lookup"><span data-stu-id="9c6ed-168">Database Administrator (DBA)</span></span>  
 <span data-ttu-id="9c6ed-169">Der Oracle-Datenbankadministrator (DBA) ist ein Oracle-Datenbankbenutzer.</span><span class="sxs-lookup"><span data-stu-id="9c6ed-169">The Oracle database administrator (DBA) is an Oracle database user.</span></span> <span data-ttu-id="9c6ed-170">Vom Oracle-Datenbankadministrator ausgeführte Tasks sind z. B.:</span><span class="sxs-lookup"><span data-stu-id="9c6ed-170">The tasks performed by the Oracle DBA include:</span></span>  
  
-   <span data-ttu-id="9c6ed-171">Einrichten der Oracle-Quelldatenbank für die Arbeit im ARCHIVELOG-Modus</span><span class="sxs-lookup"><span data-stu-id="9c6ed-171">Setting the source Oracle database to work in ARCHIVELOG mode.</span></span>  
  
-   <span data-ttu-id="9c6ed-172">Einrichten eines Log Mining-Benutzers mit den erforderlichen Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="9c6ed-172">Setting up a log mining user with the required permissions.</span></span>  
  
-   <span data-ttu-id="9c6ed-173">Festlegen der ergänzenden Protokollierung für aufgezeichnete Tabellen</span><span class="sxs-lookup"><span data-stu-id="9c6ed-173">Setting supplemental logging for captured tables.</span></span>  
  
-   <span data-ttu-id="9c6ed-174">Unterstützen der Wiederherstellung archivierter Transaktionsprotokolldateien, die nicht mehr verfügbar sind, um die Verarbeitung zu ermöglichen</span><span class="sxs-lookup"><span data-stu-id="9c6ed-174">Helping to restore archived transaction log files no longer available so they can be processed.</span></span>  
  
 <span data-ttu-id="9c6ed-175">Der Oracle-Datenbankadministrator kann Oracle SQL-Skripts abrufen, die ausgeführt werden müssen, damit diese vor dem Ausführen ausgewertet werden können.</span><span class="sxs-lookup"><span data-stu-id="9c6ed-175">The Oracle database administrator can get Oracle SQL scripts that need to run so they can be evaluated before running them.</span></span> <span data-ttu-id="9c6ed-176">Der Oracle-Datenbankadministrator kann Oracle SQL-Skripts auch direkt über die Oracle CDC Designer Console ausführen.</span><span class="sxs-lookup"><span data-stu-id="9c6ed-176">The Oracle database administrator can also directly run Oracle SQL scripts from the Oracle CDC Designer console.</span></span>  
  
 <span data-ttu-id="9c6ed-177">Wenn der Oracle-Datenbankadministrator sich für die Verwendung der Oracle CDC Designer Console entscheidet, werden die Anmeldeinformationen des Administrators nicht beibehalten, mit Ausnahme des Kontexts (Dialogfeld), in dem sie verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="9c6ed-177">If the Oracle database administrator chooses to use the Oracle CDC Designer console, administrator's credentials are not kept except for the context (dialog) in which they were used.</span></span>  
  
 <span data-ttu-id="9c6ed-178">Der Oracle-Datenbankadministrator arbeitet in Abstimmung mit dem Oracle CDC Service-Administrator an der Konfiguration der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Oracle CDC-Instanzen.</span><span class="sxs-lookup"><span data-stu-id="9c6ed-178">The Oracle database administrator works in coordination with the Oracle CDC Service administrator on the configuration of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Oracle CDC Instances.</span></span>  
  
### <a name="log-mining-user"></a><span data-ttu-id="9c6ed-179">Log Mining-Benutzer</span><span class="sxs-lookup"><span data-stu-id="9c6ed-179">Log Mining User</span></span>  
 <span data-ttu-id="9c6ed-180">Der Oracle Log Miner-Benutzer ist ein spezieller Oracle-Datenbankbenutzer, dem die erforderlichen Berechtigungen für den Zugriff auf und die Verarbeitung von Oracle-Transaktionsprotokollen gewährt werden.</span><span class="sxs-lookup"><span data-stu-id="9c6ed-180">The Oracle Log Miner user is a special Oracle database user that is granted the required privileges for accessing and processing the Oracle transaction logs.</span></span>  
  
 <span data-ttu-id="9c6ed-181">Die Anmeldeinformationen für diesen Benutzer werden mithilfe der Verschlüsselung per asymmetrischem Schlüssel in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Oracle CDC-Instanzdatenbank gespeichert.</span><span class="sxs-lookup"><span data-stu-id="9c6ed-181">The credentials for this user are stored in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Oracle CDC Instance database using asymmetric key encryption.</span></span> <span data-ttu-id="9c6ed-182">Der Zugriff ist nur für den Oracle CDC Service möglich, nicht für den Besitzer der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Oracle CDC-Instanzdatenbank.</span><span class="sxs-lookup"><span data-stu-id="9c6ed-182">They are accessible only to the Oracle CDC Service but not to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Oracle CDC Instance database owner.</span></span>  
  
 <span data-ttu-id="9c6ed-183">In der folgenden Liste sind die erforderlichen Berechtigungen beschrieben, die dem Log Mining-Benutzer gewährt werden sollten:</span><span class="sxs-lookup"><span data-stu-id="9c6ed-183">The following list describes the required privileges of the log mining user should be granted:</span></span>  
  
-   <span data-ttu-id="9c6ed-184">SELECT on \<any-captured-table></span><span class="sxs-lookup"><span data-stu-id="9c6ed-184">SELECT on \<any-captured-table></span></span>  
  
-   <span data-ttu-id="9c6ed-185">SELECT ANY TRANSACTION</span><span class="sxs-lookup"><span data-stu-id="9c6ed-185">SELECT ANY TRANSACTION</span></span>  
  
-   <span data-ttu-id="9c6ed-186">EXECUTE on DBMS_LOGMNR</span><span class="sxs-lookup"><span data-stu-id="9c6ed-186">EXECUTE on DBMS_LOGMNR</span></span>  
  
-   <span data-ttu-id="9c6ed-187">SELECT on V$LOGMNR_CONTENTS</span><span class="sxs-lookup"><span data-stu-id="9c6ed-187">SELECT on V$LOGMNR_CONTENTS</span></span>  
  
-   <span data-ttu-id="9c6ed-188">SELECT on V$ARCHIVED_LOG</span><span class="sxs-lookup"><span data-stu-id="9c6ed-188">SELECT on V$ARCHIVED_LOG</span></span>  
  
-   <span data-ttu-id="9c6ed-189">SELECT on V$LOG</span><span class="sxs-lookup"><span data-stu-id="9c6ed-189">SELECT on V$LOG</span></span>  
  
-   <span data-ttu-id="9c6ed-190">SELECT on V$LOGFILE</span><span class="sxs-lookup"><span data-stu-id="9c6ed-190">SELECT on V$LOGFILE</span></span>  
  
-   <span data-ttu-id="9c6ed-191">SELECT on V$DATABASE</span><span class="sxs-lookup"><span data-stu-id="9c6ed-191">SELECT on V$DATABASE</span></span>  
  
-   <span data-ttu-id="9c6ed-192">SELECT on V$THREAD</span><span class="sxs-lookup"><span data-stu-id="9c6ed-192">SELECT on V$THREAD</span></span>  
  
-   <span data-ttu-id="9c6ed-193">SELECT on V$PARAMETER</span><span class="sxs-lookup"><span data-stu-id="9c6ed-193">SELECT on V$PARAMETER</span></span>  
  
-   <span data-ttu-id="9c6ed-194">SELECT on DBA_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="9c6ed-194">SELECT on DBA_REGISTRY</span></span>  
  
-   <span data-ttu-id="9c6ed-195">SELECT on ALL_INDEXES</span><span class="sxs-lookup"><span data-stu-id="9c6ed-195">SELECT on ALL_INDEXES</span></span>  
  
-   <span data-ttu-id="9c6ed-196">SELECT on ALL_OBJECTS</span><span class="sxs-lookup"><span data-stu-id="9c6ed-196">SELECT on ALL_OBJECTS</span></span>  
  
-   <span data-ttu-id="9c6ed-197">SELECT on DBA_OBJECTS</span><span class="sxs-lookup"><span data-stu-id="9c6ed-197">SELECT on DBA_OBJECTS</span></span>  
  
-   <span data-ttu-id="9c6ed-198">SELECT on ALL_TABLES</span><span class="sxs-lookup"><span data-stu-id="9c6ed-198">SELECT on ALL_TABLES</span></span>  
  
 <span data-ttu-id="9c6ed-199">Wenn einem V$xxx einige dieser Berechtigungen nicht gewährt werden können, sollten sie V $xxx gewährt werden.</span><span class="sxs-lookup"><span data-stu-id="9c6ed-199">If any of these privileges cannot be granted to a V$xxx, then they should be granted to the V $xxx.</span></span>  
  
### <a name="schema-user"></a><span data-ttu-id="9c6ed-200">Schemabenutzer</span><span class="sxs-lookup"><span data-stu-id="9c6ed-200">Schema User</span></span>  
 <span data-ttu-id="9c6ed-201">Der Oracle-Schemabenutzer ist ein Oracle-Benutzer mit Lesezugriff auf das Schema der aufzuzeichnenden Oracle-Tabellen.</span><span class="sxs-lookup"><span data-stu-id="9c6ed-201">The Oracle Schema User is an Oracle user with read access to the schema of the Oracle tables to be captured.</span></span> <span data-ttu-id="9c6ed-202">Dieser Benutzer wird beim Verwenden der Oracle CDC Designer Console benötigt, um die Liste der Oracle-Schemas, aufzuzeichnende Tabellen und ihre Spalten, Indizes und Schlüssel abzurufen.</span><span class="sxs-lookup"><span data-stu-id="9c6ed-202">This user is necessary when working with the Oracle CDC Designer console to retrieve the list of Oracle schema, tables to be captured and their columns, indexes and keys.</span></span>  
  
 <span data-ttu-id="9c6ed-203">Die Anmeldeinformationen für diesen Benutzer werden nicht gespeichert.</span><span class="sxs-lookup"><span data-stu-id="9c6ed-203">The credentials for this user are never stored.</span></span> <span data-ttu-id="9c6ed-204">Sie werden von der CDC Designer Console jeweils angefordert, wenn sie benötigt werden, und dann für die restlichen Benutzeroberflächen-Sitzungen beibehalten.</span><span class="sxs-lookup"><span data-stu-id="9c6ed-204">They are requested by the CDC Designer console each time they are needed and they are kept for the rest of the UI sessions.</span></span>  
  
  
