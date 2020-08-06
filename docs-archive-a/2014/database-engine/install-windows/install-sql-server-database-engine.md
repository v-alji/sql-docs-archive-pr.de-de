---
title: Informationen zum SQL Server Datenbank-Engine | Microsoft-Dokumentation
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
helpviewer_keywords:
- Database Engine [SQL Server], installing
ms.assetid: d0876e7f-aa52-4dd7-bd5c-029e2ffded5f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 93e3d7a749fe6be47cc84d43509a6f378476b2ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701546"
---
# <a name="about-the-sql-server-database-engine"></a><span data-ttu-id="73ea1-102">Informationen zur SQL Server-Datenbank-Engine</span><span class="sxs-lookup"><span data-stu-id="73ea1-102">About the SQL Server Database Engine</span></span>
  <span data-ttu-id="73ea1-103">Bei der Komponente [!INCLUDE[ssDE](../../includes/ssde-md.md)] von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] handelt es sich um den zentralen Dienst zum Speichern, Verarbeiten und Sichern von Daten.</span><span class="sxs-lookup"><span data-stu-id="73ea1-103">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] component of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is the core service for storing, processing, and securing data.</span></span> <span data-ttu-id="73ea1-104">Das [!INCLUDE[ssDE](../../includes/ssde-md.md)] bietet gesteuerten Zugriff und eine zügige Transaktionsverarbeitung und erfüllt damit die Anforderungen selbst der anspruchsvollsten datenlastigen Anwendungen des Unternehmens.</span><span class="sxs-lookup"><span data-stu-id="73ea1-104">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] provides controlled access and rapid transaction processing to meet the requirements of the most demanding data consuming applications in your enterprise.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="73ea1-105">unterstützt bis zu 50 Instanzen von [!INCLUDE[ssDE](../../includes/ssde-md.md)] auf einem einzelnen Computer.</span><span class="sxs-lookup"><span data-stu-id="73ea1-105">supports up to 50 instances of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] on a single computer.</span></span> <span data-ttu-id="73ea1-106">Informationen zum Erstellen einer typischen- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation finden Sie unter [Install SQL Server 2014 from the Installation Wizard &#40;Setup&#41;](install-sql-server-from-the-installation-wizard-setup.md).</span><span class="sxs-lookup"><span data-stu-id="73ea1-106">To create a typical [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation, see [Install SQL Server 2014 from the Installation Wizard &#40;Setup&#41;](install-sql-server-from-the-installation-wizard-setup.md).</span></span>  
  
 <span data-ttu-id="73ea1-107">**Wichtig** Bei einer lokalen Installation müssen Sie Setup als Administrator ausführen.</span><span class="sxs-lookup"><span data-stu-id="73ea1-107">**Important** For local installations, you must run Setup as an administrator.</span></span> <span data-ttu-id="73ea1-108">Wenn Sie [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] von einer Remotefreigabe installieren, müssen Sie ein Domänenkonto verwenden, das Lese- und Ausführungsberechtigungen auf der Remotefreigabe hat.</span><span class="sxs-lookup"><span data-stu-id="73ea1-108">If you install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from a remote share, you must use a domain account that has read and execute permissions on the remote share.</span></span>  
  
 <span data-ttu-id="73ea1-109">Wenn Sie im Installations-Assistenten von **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] auf der Seite Zu installierende Komponenten die Option** -Datenbank-Engine[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] auswählen, werden folgenden Funktionen installiert:</span><span class="sxs-lookup"><span data-stu-id="73ea1-109">The following features are installed when you select **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Database Engine** on the Components to Install page of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation Wizard:</span></span>  
  
-   [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
-   <span data-ttu-id="73ea1-110">Replikation – optionale Komponente</span><span class="sxs-lookup"><span data-stu-id="73ea1-110">Replication - is an optional component</span></span>  
  
-   <span data-ttu-id="73ea1-111">Volltextsuche – optionale Komponente</span><span class="sxs-lookup"><span data-stu-id="73ea1-111">Full-Text Search - is an optional component</span></span>  
  
-   <span data-ttu-id="73ea1-112">Data Quality Services: optionale Komponente</span><span class="sxs-lookup"><span data-stu-id="73ea1-112">Data Quality Services - is an optional component</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="73ea1-113">In dieser Version wird durch Aktivieren des Kontrollkästchens **Data Quality Services** während des Setups DQS (Data Quality Services)-Server nicht installiert.</span><span class="sxs-lookup"><span data-stu-id="73ea1-113">In this release, selecting the **Data Quality Services** check box in setup does not install the Data Quality Services (DQS) server.</span></span> <span data-ttu-id="73ea1-114">Sie müssen nach der Installation weitere Schritte ausführen, um DQS-Server zu installieren.</span><span class="sxs-lookup"><span data-stu-id="73ea1-114">You will have to perform additional steps post installation to install DQS server.</span></span> <span data-ttu-id="73ea1-115">Weitere Informationen finden Sie unter [Install Data Quality Services](../../data-quality-services/install-windows/install-data-quality-services.md).</span><span class="sxs-lookup"><span data-stu-id="73ea1-115">For more information, see [Install Data Quality Services](../../data-quality-services/install-windows/install-data-quality-services.md).</span></span>  
  
 <span data-ttu-id="73ea1-116">In vielen typischen Benutzerszenarien sind die folgenden zusätzlichen Funktionen als Optionen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="73ea1-116">The following additional features are options for many typical user scenarios:</span></span>  
  
-   <span data-ttu-id="73ea1-117">Data Quality Client</span><span class="sxs-lookup"><span data-stu-id="73ea1-117">Data Quality Client</span></span>  
  
-   [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]  
  
-   <span data-ttu-id="73ea1-118">Konnektivitätskomponenten</span><span class="sxs-lookup"><span data-stu-id="73ea1-118">Connectivity components</span></span>  
  
-   <span data-ttu-id="73ea1-119">Programmmodelle</span><span class="sxs-lookup"><span data-stu-id="73ea1-119">Programming models</span></span>  
  
-   <span data-ttu-id="73ea1-120">Verwaltungstools</span><span class="sxs-lookup"><span data-stu-id="73ea1-120">Management tools</span></span>  
  
-   [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]  
  
-   <span data-ttu-id="73ea1-121">Dokumentationskomponenten</span><span class="sxs-lookup"><span data-stu-id="73ea1-121">Documentation components</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="73ea1-122">Standardmäßig werden Beispieldatenbanken und Beispielcode nicht als Teil des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Setups installiert.</span><span class="sxs-lookup"><span data-stu-id="73ea1-122">By default, sample databases and sample code are not installed as part of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup.</span></span> <span data-ttu-id="73ea1-123">Informationen zur Installation von Beispieldatenbanken und Beispielcode finden Sie auf der [CodePlex-Website](https://go.microsoft.com/fwlink/?LinkId=87843).</span><span class="sxs-lookup"><span data-stu-id="73ea1-123">To install sample databases and sample code, see the [CodePlex Web site](https://go.microsoft.com/fwlink/?LinkId=87843).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73ea1-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="73ea1-124">See Also</span></span>  
 <span data-ttu-id="73ea1-125">[Von den-Editionen unterstützte Funktionen SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md) </span><span class="sxs-lookup"><span data-stu-id="73ea1-125">[Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md) </span></span>  
 <span data-ttu-id="73ea1-126">[Editionen und Komponenten von SQL Server 2014](../../sql-server/editions-and-components-of-sql-server-2016.md) </span><span class="sxs-lookup"><span data-stu-id="73ea1-126">[Editions and Components of SQL Server 2014](../../sql-server/editions-and-components-of-sql-server-2016.md) </span></span>  
 <span data-ttu-id="73ea1-127">[Planen einer SQL Server-Installation](../../sql-server/install/planning-a-sql-server-installation.md) </span><span class="sxs-lookup"><span data-stu-id="73ea1-127">[Planning a SQL Server Installation](../../sql-server/install/planning-a-sql-server-installation.md) </span></span>  
 <span data-ttu-id="73ea1-128">[Lösungen mit hoher Verfügbarkeit &#40;SQL Server&#41;](../../sql-server/failover-clusters/high-availability-solutions-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="73ea1-128">[High Availability Solutions &#40;SQL Server&#41;](../../sql-server/failover-clusters/high-availability-solutions-sql-server.md) </span></span>  
 [<span data-ttu-id="73ea1-129">Upgrade auf SQL Server 2014 mithilfe des Installations-Assistenten &#40;Setup&#41;</span><span class="sxs-lookup"><span data-stu-id="73ea1-129">Upgrade to SQL Server 2014 Using the Installation Wizard &#40;Setup&#41;</span></span>](upgrade-sql-server-using-the-installation-wizard-setup.md)  
  
  
