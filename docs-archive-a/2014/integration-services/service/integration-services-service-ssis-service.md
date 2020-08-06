---
title: Integration Services-Dienst (SSIS-Dienst) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Integration Services service, about Integration Services service
- SQL Server Integration Services service
- service [Integration Services],about Integration Services service
- service [Integration Services]
- SQL Server Integration Services, service
ms.assetid: 2c785b3b-4a0c-4df7-b5cd-23756dc87842
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 04b24f0f0d54009c50654904d606a208504f229c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726070"
---
# <a name="integration-services-service-ssis-service"></a><span data-ttu-id="ea8b7-102">Integration Services-Dienst (SSIS-Dienst)</span><span class="sxs-lookup"><span data-stu-id="ea8b7-102">Integration Services Service (SSIS Service)</span></span>
  <span data-ttu-id="ea8b7-103">In den Themen in diesem Abschnitt wird der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Dienst, ein Windows-Dienst zum Verwalten von [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Paketen, erläutert.</span><span class="sxs-lookup"><span data-stu-id="ea8b7-103">The topics in this section discuss the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] service, a Windows service for managing [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.</span></span> <span data-ttu-id="ea8b7-104">Dieser Dienst ist nicht erforderlich, um Integration Services-Pakete zu erstellen, zu speichern und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ea8b7-104">This service is not required to create, save, and run Integration Services packages.</span></span> [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] <span data-ttu-id="ea8b7-105">unterstützt den [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Dienst für die Abwärtskompatibilität mit früheren Versionen von [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ea8b7-105">supports the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] service for backward compatibility with earlier releases of [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="ea8b7-106">Ab [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] speichert Objekte, Einstellungen und operative Daten in der- `SSISDB` Datenbank für Projekte, die Sie [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] mithilfe des Projekt Bereitstellungs Modells auf dem-Server bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="ea8b7-106">Starting in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] stores objects, settings, and operational data in the `SSISDB` database for projects that you've deployed to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server using the project deployment model.</span></span> <span data-ttu-id="ea8b7-107">Der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Server, bei dem es sich um eine Instanz der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Datenbank-Engine handelt, hostet die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="ea8b7-107">The [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server, which is an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Database Engine, hosts the database.</span></span> <span data-ttu-id="ea8b7-108">Weitere Informationen zur Verschlüsselung finden Sie unter [SSIS-Katalog](../catalog/ssis-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="ea8b7-108">For more information about the database, see [SSIS Catalog](../catalog/ssis-catalog.md).</span></span> <span data-ttu-id="ea8b7-109">Weitere Informationen zum Bereitstellen eines Projekts auf dem [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Server finden Sie unter [Bereitstellen von Projekten auf dem Integration Services-Server](../deploy-projects-to-integration-services-server.md).</span><span class="sxs-lookup"><span data-stu-id="ea8b7-109">For more information about deploying projects to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server, see [Deploy Projects to Integration Services Server](../deploy-projects-to-integration-services-server.md).</span></span>  
  
## <a name="management-capabilities"></a><span data-ttu-id="ea8b7-110">Managementfunktionen</span><span class="sxs-lookup"><span data-stu-id="ea8b7-110">Management Capabilities</span></span>  
 <span data-ttu-id="ea8b7-111">Der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Dienst ist ein Windows-Dienst zur Verwaltung von [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Paketen.</span><span class="sxs-lookup"><span data-stu-id="ea8b7-111">The [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] service is a Windows service for managing [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.</span></span> <span data-ttu-id="ea8b7-112">Der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Dienst steht nur in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="ea8b7-112">The [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] service is available only in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="ea8b7-113">Beim Ausführen des [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Dienstes stehen folgende Verwaltungsfunktionen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="ea8b7-113">Running the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] service provides the following management capabilities:</span></span>  
  
-   <span data-ttu-id="ea8b7-114">Starten von lokal und remote gespeicherten Paketen</span><span class="sxs-lookup"><span data-stu-id="ea8b7-114">Starting remote and locally stored packages</span></span>  
  
-   <span data-ttu-id="ea8b7-115">Beenden von lokal und remote ausgeführten Paketen</span><span class="sxs-lookup"><span data-stu-id="ea8b7-115">Stopping remote and locally running packages</span></span>  
  
-   <span data-ttu-id="ea8b7-116">Überwachen von lokal und remote ausgeführten Paketen</span><span class="sxs-lookup"><span data-stu-id="ea8b7-116">Monitoring remote and locally running packages</span></span>  
  
-   <span data-ttu-id="ea8b7-117">Importieren und Exportieren von Paketen</span><span class="sxs-lookup"><span data-stu-id="ea8b7-117">Importing and exporting packages</span></span>  
  
-   <span data-ttu-id="ea8b7-118">Verwalten des Paketspeichers</span><span class="sxs-lookup"><span data-stu-id="ea8b7-118">Managing package storage</span></span>  
  
-   <span data-ttu-id="ea8b7-119">Anpassen von Speicherordnern</span><span class="sxs-lookup"><span data-stu-id="ea8b7-119">Customizing storage folders</span></span>  
  
-   <span data-ttu-id="ea8b7-120">Beenden von ausgeführten Paketen beim Beenden des Dienstes</span><span class="sxs-lookup"><span data-stu-id="ea8b7-120">Stopping running packages when the service is stopped</span></span>  
  
-   <span data-ttu-id="ea8b7-121">Anzeigen des Windows-Ereignisprotokolls</span><span class="sxs-lookup"><span data-stu-id="ea8b7-121">Viewing the Windows Event log</span></span>  
  
-   <span data-ttu-id="ea8b7-122">Herstellen von Verbindungen mit mehreren [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Servern</span><span class="sxs-lookup"><span data-stu-id="ea8b7-122">Connecting to multiple [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] servers</span></span>  
  
## <a name="startup-type-for-integration-services-service"></a><span data-ttu-id="ea8b7-123">Starttyp für Integration Services-Dienst</span><span class="sxs-lookup"><span data-stu-id="ea8b7-123">Startup Type for Integration Services Service</span></span>  
 <span data-ttu-id="ea8b7-124">Der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Dienst wird zusammen mit der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Komponente von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]installiert.</span><span class="sxs-lookup"><span data-stu-id="ea8b7-124">The [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] service is installed when you install the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] component of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ea8b7-125">Standardmäßig wird der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Dienst gestartet, und der Starttyp des Dienstes ist auf automatisch festgelegt.</span><span class="sxs-lookup"><span data-stu-id="ea8b7-125">By default, the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] service is started and the startup type of the service is set to automatic.</span></span> <span data-ttu-id="ea8b7-126">Der Dienst muss ausgeführt werden, damit die im [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Paketspeicher gespeicherten Pakete überwacht werden.</span><span class="sxs-lookup"><span data-stu-id="ea8b7-126">The service must be running to monitor the packages that are stored in the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Store.</span></span> <span data-ttu-id="ea8b7-127">Als [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Paketspeicher können entweder die msdb-Datenbank einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] oder die dazu bestimmten Ordner des Dateisystems dienen.</span><span class="sxs-lookup"><span data-stu-id="ea8b7-127">The [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Store can be either the msdb database in an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or the designated folders in the file system.</span></span>  
  
 <span data-ttu-id="ea8b7-128">Der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Dienst ist nicht erforderlich, wenn Sie [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Pakete lediglich entwerfen und ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="ea8b7-128">The [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] service is not required if you only want to design and execute [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.</span></span> <span data-ttu-id="ea8b7-129">Der Dienst ist jedoch zum Auflisten und Überwachen von Paketen in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ea8b7-129">However, the service is required to list and monitor packages using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="ea8b7-130">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="ea8b7-130">Related Tasks</span></span>  
  
-   [<span data-ttu-id="ea8b7-131">Festlegen der Eigenschaften des Integration Services-Diensts</span><span class="sxs-lookup"><span data-stu-id="ea8b7-131">Set the Properties of the Integration Services Service</span></span>](../set-the-properties-of-the-integration-services-service.md)  
  
-   [<span data-ttu-id="ea8b7-132">Anzeigen von Ereignissen für den Integration Services-Dienst</span><span class="sxs-lookup"><span data-stu-id="ea8b7-132">View Events for the Integration Services Service</span></span>](../view-events-for-the-integration-services-service.md)  
  
  
