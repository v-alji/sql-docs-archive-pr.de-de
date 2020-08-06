---
title: Integration Services (SSIS)-Server | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- packages [Integration Services], managing
- managing packages [Integration Services]
ms.assetid: 6d667bba-7c25-492a-8f4d-70ebaca28f40
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a0da83cdac269499dfbde7a6387a4af4690c83ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619284"
---
# <a name="integration-services-ssis-server"></a><span data-ttu-id="1d981-102">Integration Services (SSIS)-Server</span><span class="sxs-lookup"><span data-stu-id="1d981-102">Integration Services (SSIS) Server</span></span>
  <span data-ttu-id="1d981-103">Nachdem Sie Pakete und Konfigurationen in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]entworfen und getestet haben, können Sie die Projekte, die die Pakete enthalten, auf dem [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Server bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="1d981-103">After you design and test packages in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], you can deploy the projects that contain the packages to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
 <span data-ttu-id="1d981-104">Der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Server stellt eine Instanz von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] dar, die als Host für die `SSISDB`-Datenbank fungiert.</span><span class="sxs-lookup"><span data-stu-id="1d981-104">The [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server is an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that hosts the `SSISDB` database.</span></span> <span data-ttu-id="1d981-105">Die Datenbank speichert die folgenden Objekte: Pakete, Projekte, Parameter, Berechtigungen, Servereigenschaften und Verwendungsverlauf.</span><span class="sxs-lookup"><span data-stu-id="1d981-105">The database stores the following objects: packages, projects, parameters, permissions, server properties, and operational history.</span></span>  
  
 <span data-ttu-id="1d981-106">Die `SSISDB`-Datenbank macht die Objektinformationen in öffentlichen Sichten verfügbar, die Sie abfragen können.</span><span class="sxs-lookup"><span data-stu-id="1d981-106">The `SSISDB` database exposes the object information in public views that you can query.</span></span> <span data-ttu-id="1d981-107">Die Datenbank stellt auch gespeicherte Prozeduren bereit, die Sie aufrufen können, um die Objekte zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="1d981-107">The database also provides stored procedures that you can call to manage the objects.</span></span>  
  
 <span data-ttu-id="1d981-108">Bevor Sie die Projekte auf dem [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Server bereitstellen können, müssen Sie den `SSISDB`-Katalog erstellen.</span><span class="sxs-lookup"><span data-stu-id="1d981-108">Before you can deploy the projects to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server, you need to create the `SSISDB` catalog.</span></span>  
  
 <span data-ttu-id="1d981-109">Eine Übersicht über die Funktionen des SSISDB-Katalogs finden Sie unter [SSIS-Katalog](ssis-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="1d981-109">For an overview of the SSISDB catalog functionality, see [SSIS Catalog](ssis-catalog.md).</span></span>  
  
## <a name="high-availability"></a><span data-ttu-id="1d981-110">Hochverfügbarkeit</span><span class="sxs-lookup"><span data-stu-id="1d981-110">High Availability</span></span>  
 <span data-ttu-id="1d981-111">Wie andere Benutzerdatenbanken unterstützt die Datenbank `SSISDB` die Datenbankspiegelung und Replikation.</span><span class="sxs-lookup"><span data-stu-id="1d981-111">Like other user databases, the `SSISDB` database does support database mirroring and replication.</span></span> <span data-ttu-id="1d981-112">Weitere Informationen zur Spiegelung und Replikation finden Sie unter [Datenbankspiegelung &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1d981-112">For more information about mirroring and replication, see [Database Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md).</span></span>  
  
 <span data-ttu-id="1d981-113">Sie können auch die hohe Verfügbarkeit von SSISDB und die Inhalte bereitstellen, indem Sie die SSIS- und AlwaysOn-Verfügbarkeitsgruppen verwenden.</span><span class="sxs-lookup"><span data-stu-id="1d981-113">You can also provide high-availability of SSISDB and its contents by making use of SSIS and AlwaysOn Availability Groups.</span></span> <span data-ttu-id="1d981-114">Weitere Informationen finden Sie im folgenden Blogbeitrag von Matt Masson bei blogs.msdn.com: [SSIS mit AlwaysOn](https://go.microsoft.com/fwlink/?LinkId=255873).</span><span class="sxs-lookup"><span data-stu-id="1d981-114">For more information, see this blog post by Matt Masson, [SSIS with AlwaysOn](https://go.microsoft.com/fwlink/?LinkId=255873), at blogs.msdn.com.</span></span>  
  
##  <a name="integration-services-server-in-sql-server-management-studio"></a><a name="ssms"></a><span data-ttu-id="1d981-115">Integration Services Server in SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1d981-115">Integration Services Server in SQL Server Management Studio</span></span>  
 <span data-ttu-id="1d981-116">Wenn Sie eine Verbindung mit einer Instanz des [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]s herstellen, die als Host für die `SSISDB`-Datenbank fungiert, werden die folgenden Objekte im Objekt-Explorer angezeigt:</span><span class="sxs-lookup"><span data-stu-id="1d981-116">When you connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that hosts the `SSISDB` database, you see the following objects in Object Explorer:</span></span>  
  
-   <span data-ttu-id="1d981-117">**SSISDB-Datenbank**</span><span class="sxs-lookup"><span data-stu-id="1d981-117">**SSISDB Database**</span></span>  
  
     <span data-ttu-id="1d981-118">Die `SSISDB` Datenbank wird unter dem Knoten **Datenbanken** in Objekt durchsuchen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1d981-118">The `SSISDB` database appears under the **Databases** node in Object Explore.</span></span> <span data-ttu-id="1d981-119">Sie können die Sichten abfragen und die gespeicherten Prozeduren aufrufen, die zur Verwaltung des [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Servers sowie der darauf gespeicherten Objekte verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1d981-119">You can query the views and call the stored procedures that manage the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server and the objects that are stored on the server.</span></span>  
  
-   <span data-ttu-id="1d981-120">**Integration Services-Kataloge**</span><span class="sxs-lookup"><span data-stu-id="1d981-120">**Integration Services Catalogs**</span></span>  
  
     <span data-ttu-id="1d981-121">Unter dem Knoten **Integration Services-Kataloge** befinden sich Ordner für [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Projekte und -Umgebungen.</span><span class="sxs-lookup"><span data-stu-id="1d981-121">Under the **Integration Services Catalogs** node there are folders for [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] projects and environments.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="1d981-122">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="1d981-122">Related Tasks</span></span>  
  
-   [<span data-ttu-id="1d981-123">Erstellen des SSIS-Katalogs</span><span class="sxs-lookup"><span data-stu-id="1d981-123">Create the SSIS Catalog</span></span>](../create-the-ssis-catalog.md)  
  
-   [<span data-ttu-id="1d981-124">Anzeigen der Liste der auf dem Integration Services-Server gespeicherten Pakete</span><span class="sxs-lookup"><span data-stu-id="1d981-124">View the List of Packages on the Integration Services Server</span></span>](view-the-list-of-packages-on-the-integration-services-server.md)  
  
-   [<span data-ttu-id="1d981-125">Deploy Projects to Integration Services Server</span><span class="sxs-lookup"><span data-stu-id="1d981-125">Deploy Projects to Integration Services Server</span></span>](../deploy-projects-to-integration-services-server.md)  
  
-   [<span data-ttu-id="1d981-126">Ausführen eines Pakets auf dem SSIS-Server mit SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1d981-126">Run a Package on the SSIS Server Using SQL Server Management Studio</span></span>](../run-a-package-on-the-ssis-server-using-sql-server-management-studio.md)  
  
## <a name="related-content"></a><span data-ttu-id="1d981-127">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="1d981-127">Related Content</span></span>  
 <span data-ttu-id="1d981-128">Blogeintrag zu [SSIS mit AlwaysOn](https://go.microsoft.com/fwlink/?LinkId=255873)auf blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="1d981-128">Blog entry, [SSIS with AlwaysOn](https://go.microsoft.com/fwlink/?LinkId=255873), at blogs.msdn.com.</span></span>  
  
  
