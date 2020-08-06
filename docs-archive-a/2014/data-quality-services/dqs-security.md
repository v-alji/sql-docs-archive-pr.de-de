---
title: DQS-Sicherheit | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 921927f5-1b1e-452a-a79e-c691829fd826
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 3da3cdbe746b69c5c4cfe7c7c796827dd74a433c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700275"
---
# <a name="dqs-security"></a><span data-ttu-id="e931f-102">DQS-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="e931f-102">DQS Security</span></span>
  <span data-ttu-id="e931f-103">Die [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS)-Sicherheitsinfrastruktur basiert auf der SQL Server-Sicherheitsinfrastruktur.</span><span class="sxs-lookup"><span data-stu-id="e931f-103">The [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) security infrastructure is based upon the SQL Server security infrastructure.</span></span> <span data-ttu-id="e931f-104">Ein Datenbankadministrator gewährt einem Benutzer einen Satz von Berechtigungen, indem er dem Benutzer eine DQS-Rolle zuordnet.</span><span class="sxs-lookup"><span data-stu-id="e931f-104">A database administrator grants a user a set of permissions by associating the user with a DQS role.</span></span> <span data-ttu-id="e931f-105">Auf diese Weise wird bestimmt, auf welche DQS-Ressourcen der Benutzer Zugriff hat und welche funktionalen Aktivitäten der Benutzer ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="e931f-105">Doing so determines the DQS resources that the user has access to and the functional activities that the user is allowed to perform.</span></span>  
  
## <a name="dqs-roles"></a><span data-ttu-id="e931f-106">DQS-Rollen</span><span class="sxs-lookup"><span data-stu-id="e931f-106">DQS Roles</span></span>  
 <span data-ttu-id="e931f-107">Es gibt vier Rollen für DQS.</span><span class="sxs-lookup"><span data-stu-id="e931f-107">There are four roles for DQS.</span></span> <span data-ttu-id="e931f-108">Eine davon ist der Datenbankadministrator (DBA), der hauptsächlich für Produktinstallation, Datenbankwartung und Benutzerverwaltung zuständig ist.</span><span class="sxs-lookup"><span data-stu-id="e931f-108">One is the database administrator (DBA) who deals primarily with product installation, database maintenance, and user management.</span></span> <span data-ttu-id="e931f-109">Diese Rolle verwendet meist eher SQL Server Management Studio als die [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] - Anwendung.</span><span class="sxs-lookup"><span data-stu-id="e931f-109">This role primarily uses the SQL Server Management Studio, rather than within the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] application.</span></span> <span data-ttu-id="e931f-110">Die Serverrolle ist „sysadmin“.</span><span class="sxs-lookup"><span data-stu-id="e931f-110">Their server role is sysadmin.</span></span>  
  
 <span data-ttu-id="e931f-111">Die anderen Rollen sind „Information Workers“ und „Data Stewards“, die das Produkt direkt durch in der Anwendung [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] verwenden.</span><span class="sxs-lookup"><span data-stu-id="e931f-111">The three other roles are information workers, data stewards who use the product directly by working in the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] application.</span></span> <span data-ttu-id="e931f-112">Zu diesen Rollen gehören:</span><span class="sxs-lookup"><span data-stu-id="e931f-112">These roles include the following:</span></span>  
  
-   <span data-ttu-id="e931f-113">Der **DQS-Administrator** (dqs_administrator-Rolle) kann im Rahmen des Produkts alle Vorgänge ausführen.</span><span class="sxs-lookup"><span data-stu-id="e931f-113">The **DQS Administrator** (dqs_administrator role) can do everything in the scope of the product.</span></span> <span data-ttu-id="e931f-114">Der Administrator kann ein Projekt bearbeiten und ausführen, eine Wissensdatenbank erstellen und bearbeiten, eine Aktivität beenden, einen Prozess innerhalb einer Aktivität stoppen und die Konfiguration sowie die Reference Data Services-Einstellungen ändern.</span><span class="sxs-lookup"><span data-stu-id="e931f-114">The administrator can edit and execute a project, create and edit a knowledge base, terminate an activity, stop a process within an activity, and can change the configuration and Reference Data Services settings.</span></span> <span data-ttu-id="e931f-115">Der DQS-Administrator kann jedoch nicht den Server installieren oder neue Benutzer hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e931f-115">The DQS Administrator cannot, however, install the server or add new users.</span></span> <span data-ttu-id="e931f-116">Dies ist Aufgabe des Datenbankadministrators.</span><span class="sxs-lookup"><span data-stu-id="e931f-116">The database administrator must do that.</span></span>  
  
-   <span data-ttu-id="e931f-117">Der **DQS KB-Editor** (Rolle „dqs_kb_editor“) kann alle DQS-Aktivitäten mit Ausnahme von Verwaltungsaufgaben ausführen.</span><span class="sxs-lookup"><span data-stu-id="e931f-117">The **DQS KB Editor** (dqs_kb_editor role) can perform all of the DQS activities, except for administration.</span></span> <span data-ttu-id="e931f-118">Der KB-Editor kann ein Projekt bearbeiten und ausführen sowie eine Wissensdatenbank erstellen und bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="e931f-118">The KB Editor can edit and execute a project, and create and edit a knowledge base.</span></span> <span data-ttu-id="e931f-119">Er kann die Aktivitätsüberwachungsdaten anzeigen, die Aktivität jedoch weder abschließen noch stoppen oder Verwaltungsaufgaben ausführen.</span><span class="sxs-lookup"><span data-stu-id="e931f-119">They can see the activity monitoring data, but cannot terminate or stop an activity or perform administrative duties.</span></span>  
  
-   <span data-ttu-id="e931f-120">Der **DQS KB-Operator** (Rolle „dqs_kb_operator“) kann ein Projekt bearbeiten und ausführen.</span><span class="sxs-lookup"><span data-stu-id="e931f-120">The **DQS KB Operator** (dqs_kb_operator role) can edit and execute a project.</span></span> <span data-ttu-id="e931f-121">Er kann keinerlei Wissensverwaltung ausführen und keine Wissensdatenbank erstellen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="e931f-121">They cannot perform any kind of knowledge management; they cannot create or change a knowledge base.</span></span> <span data-ttu-id="e931f-122">Er kann die Aktivitätsüberwachungsdaten anzeigen, die Aktivität jedoch nicht abschließen bzw. keine Verwaltungsaufgaben ausführen.</span><span class="sxs-lookup"><span data-stu-id="e931f-122">They can see the activity monitoring data, but cannot terminate an activity or perform administrative duties.</span></span>  
  
## <a name="user-management"></a><span data-ttu-id="e931f-123">Benutzerverwaltung</span><span class="sxs-lookup"><span data-stu-id="e931f-123">User Management</span></span>  
 <span data-ttu-id="e931f-124">Der Datenbankadministrator (DBA) erstellt DQS-Benutzer und ordnet sie DQS-Rollen in SQL Server Management Studio zu.</span><span class="sxs-lookup"><span data-stu-id="e931f-124">The database administrator (DBA) creates DQS users and associates them with DQS roles in SQL Server Management Studio.</span></span> <span data-ttu-id="e931f-125">Der DBA verwaltet ihre Berechtigungen, indem er der DQS_MAIN-Datenbank SQL-Anmeldenamen als Benutzer hinzufügt und jeden Benutzer mit einer der DQS-Rollen verknüpft.</span><span class="sxs-lookup"><span data-stu-id="e931f-125">The DBA manages their permissions by adding SQL Logins as users of the DQS_MAIN database, and associating each user with one of the DQS roles.</span></span> <span data-ttu-id="e931f-126">Jeder Rolle werden Berechtigungen für einen Satz von gespeicherten Prozeduren in der DQS_MAIN-Datenbank gewährt.</span><span class="sxs-lookup"><span data-stu-id="e931f-126">Each role is granted permissions to a set of stored procedures on the DQS_MAIN database.</span></span> <span data-ttu-id="e931f-127">Die drei DQS-Rollen sind für die Datenbanken DQS_PROJECTS und DQS_STAGING_DATA nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e931f-127">The three DQS roles are not available for the DQS_PROJECTS and DQS_STAGING_DATA databases.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="e931f-128">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="e931f-128">Related Tasks</span></span>  
  
|<span data-ttu-id="e931f-129">Taskbeschreibung</span><span class="sxs-lookup"><span data-stu-id="e931f-129">Task Description</span></span>|<span data-ttu-id="e931f-130">Thema</span><span class="sxs-lookup"><span data-stu-id="e931f-130">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="e931f-131">Beschreibt, wie Sie mit SQL Server Management Studio einen Benutzer erstellen und diesem DQS-Rollen gewähren.</span><span class="sxs-lookup"><span data-stu-id="e931f-131">Describes how to create a user and grant DQS roles using SQL Server Management Studio.</span></span>|[<span data-ttu-id="e931f-132">Verwalten von DQS-Benutzern in SSMS</span><span class="sxs-lookup"><span data-stu-id="e931f-132">Manage DQS Users in SSMS</span></span>](../../2014/data-quality-services/manage-dqs-users-in-ssms.md)|  
  
  