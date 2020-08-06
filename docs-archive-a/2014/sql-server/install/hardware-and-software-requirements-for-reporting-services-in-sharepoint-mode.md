---
title: Hardware-und Software Anforderungen für Reporting Services im SharePoint-Modus | Microsoft-Dokumentation
ms.custom: ''
ms.date: 01/09/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: ed91877d-4f74-4266-a932-b824b4810c99
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: a4fc19b2871d7d5731649c61a8d5231d7e3479dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621850"
---
# <a name="hardware-and-software-requirements-for-reporting-services-in-sharepoint-mode"></a><span data-ttu-id="47e26-102">Hardware- und Softwareanforderungen für Reporting Services im SharePoint-Modus</span><span class="sxs-lookup"><span data-stu-id="47e26-102">Hardware and Software Requirements for Reporting Services in SharePoint Mode</span></span>

  <span data-ttu-id="47e26-103">In diesem Thema werden die Voraussetzungen, Hardwareanforderungen und Überlegungen zur Installation für die [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Ausführung im SharePoint-Modus beschrieben.</span><span class="sxs-lookup"><span data-stu-id="47e26-103">This topic describes prerequisites, hardware requirements, and installation considerations for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] running in SharePoint mode.</span></span> <span data-ttu-id="47e26-104">Da der SharePoint-Modus von [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] einen SharePoint-Server erfordert, liegt den meisten Anforderungen die SharePoint-Umgebung zugrunde.</span><span class="sxs-lookup"><span data-stu-id="47e26-104">Because [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode requires a SharePoint server, most of the requirements are based on the SharePoint environment.</span></span> <span data-ttu-id="47e26-105">Für Berichtsserver im einheitlichen Modus muss die vorhandene Hardware die Mindestanforderungen an die Hardware und Software zum Ausführen von [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]erfüllen.</span><span class="sxs-lookup"><span data-stu-id="47e26-105">For native mode report servers, your hardware should meet minimum hardware and software requirements for running [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="47e26-106">Weitere Informationen finden Sie unter [Hardware and Software Requirements for Installing SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="47e26-106">For more information, see [Hardware and Software Requirements for Installing SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md).</span></span>  
  
-   [<span data-ttu-id="47e26-107">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="47e26-107">Prerequisites</span></span>](#bkmk_prereq)  
  
-   [<span data-ttu-id="47e26-108">Anforderungen an die Berichts Server-Datenbank</span><span class="sxs-lookup"><span data-stu-id="47e26-108">Report Server Database Requirements</span></span>](#bkmk_report_server_database)  
  
-   [<span data-ttu-id="47e26-109">Power View-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="47e26-109">Power View Requirements</span></span>](#bkmk_powerview)  
  
-   [<span data-ttu-id="47e26-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="47e26-110">More Information</span></span>](#bkmk_more_information)  
  
##  <a name="prerequisites"></a><a name="bkmk_prereq"></a> <span data-ttu-id="47e26-111">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="47e26-111">Prerequisites</span></span>  
  
-   <span data-ttu-id="47e26-112">Bei lokalen Installationen muss das Konto, das sich während der Installation von SharePoint und [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] angemeldet hat, Mitglied der Administratorgruppe im lokalen Betriebssystem sein.</span><span class="sxs-lookup"><span data-stu-id="47e26-112">For local installations, the account logged in during installation of SharePoint and [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] needs to be a member of the administrators group in the local operating system.</span></span> <span data-ttu-id="47e26-113">Das Setupkonto muss kein Mitglied der Administratorgruppe für die SharePoint-Farm sein.</span><span class="sxs-lookup"><span data-stu-id="47e26-113">The setup account does not need to be a member of the SharePoint farm administrators group.</span></span>  
  
     <span data-ttu-id="47e26-114">Weitere Informationen finden Sie unter [Account permissions and security settings in SharePoint 2013](https://technet.microsoft.com/library/cc678863.aspx).</span><span class="sxs-lookup"><span data-stu-id="47e26-114">For more information, see [Account permissions and security settings in SharePoint 2013](https://technet.microsoft.com/library/cc678863.aspx).</span></span>  
  
-   [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="47e26-115">im SharePoint-Modus erfordert SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="47e26-115">running in SharePoint mode requires SharePoint Server.</span></span> <span data-ttu-id="47e26-116">Weitere Informationen zu SharePoint-Anforderungen und -Konfigurationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="47e26-116">For more information about SharePoint requirements and configurations, see the following:</span></span>  
  
    -   <span data-ttu-id="47e26-117">[Hardware-und Softwareanforderungen (SharePoint 2013)](https://go.microsoft.com/fwlink/p/?LinkId=256365) (https://go.microsoft.com/fwlink/p/?LinkId=256365)</span><span class="sxs-lookup"><span data-stu-id="47e26-117">[Hardware and software requirements (SharePoint 2013)](https://go.microsoft.com/fwlink/p/?LinkId=256365) (https://go.microsoft.com/fwlink/p/?LinkId=256365)</span></span>  
  
    -   [<span data-ttu-id="47e26-118">Kapazitätsmanagement und Größenanpassung für SharePoint Server 2013</span><span class="sxs-lookup"><span data-stu-id="47e26-118">Capacity management and sizing for SharePoint Server 2013</span></span>](https://technet.microsoft.com/library/cc261700.aspx)  
  
    -   [<span data-ttu-id="47e26-119">Softwareanforderungen für Business Intelligence (SharePoint 2013)</span><span class="sxs-lookup"><span data-stu-id="47e26-119">Software requirements for business intelligence (SharePoint 2013)</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=256367)  
  
    -   <span data-ttu-id="47e26-120">[Hardware- und Softwareanforderungen (SharePoint Server 2010)](https://technet.microsoft.com/library/cc262485\(v=office.14\))</span><span class="sxs-lookup"><span data-stu-id="47e26-120">[Hardware and software requirements (SharePoint Server 2010)](https://technet.microsoft.com/library/cc262485\(v=office.14\))</span></span>  
  
    -   <span data-ttu-id="47e26-121">[Kapazitätsmanagement und Größenanpassung für SharePoint Server 2010](https://technet.microsoft.com/library/cc261700.aspx\(v=office.14\))</span><span class="sxs-lookup"><span data-stu-id="47e26-121">[Capacity management and sizing for SharePoint Server 2010](https://technet.microsoft.com/library/cc261700.aspx\(v=office.14\))</span></span>  
  
-   <span data-ttu-id="47e26-122">Wenn Sie die vorhandene [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint-Installation mit [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]aktualisieren möchten (Upgrade oder Update), informieren Sie sich unter [Upgrade and Migrate Reporting Services](../../reporting-services/install-windows/upgrade-and-migrate-reporting-services.md)erfüllen.</span><span class="sxs-lookup"><span data-stu-id="47e26-122">If you want to upgrade or update existing [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint installation with [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], see [Upgrade and Migrate Reporting Services](../../reporting-services/install-windows/upgrade-and-migrate-reporting-services.md).</span></span>  
  
-   <span data-ttu-id="47e26-123">Überprüfen Sie, ob der **SharePoint 2013-Administration** -Dienst im Windows Server-Manager gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="47e26-123">Verify the **SharePoint 2013 Administration** service is started in Windows Server Manager.</span></span>  
  
###  <a name="report-server-database-requirements"></a><a name="bkmk_report_server_database"></a><span data-ttu-id="47e26-124">Anforderungen für die Berichtsserver-Datenbank</span><span class="sxs-lookup"><span data-stu-id="47e26-124">Report Server Database Requirements</span></span>  
  
-   <span data-ttu-id="47e26-125">Sowohl [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] als auch SharePoint-Produkte und -Technologien verwenden relationale SQL Server-Datenbanken zum Speichern von Anwendungsdaten.</span><span class="sxs-lookup"><span data-stu-id="47e26-125">Both [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] and SharePoint products and technologies use SQL Server relational databases to store application data.</span></span>  
  
-   [!INCLUDE[ssRSCurrent](../../includes/ssrscurrent-md.md)] <span data-ttu-id="47e26-126">erfordert eine Instanz von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] einer kompatiblen SQL Server-Edition.</span><span class="sxs-lookup"><span data-stu-id="47e26-126">requires an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] of a compatible SQL Server edition.</span></span> <span data-ttu-id="47e26-127">Weitere Informationen zu Hardware- und Softwareanforderungen finden Sie unter [Hardware and Software Requirements for Installing SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="47e26-127">For more information on hardware and software requirements, see [Hardware and Software Requirements for Installing SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md).</span></span>  
  
-   <span data-ttu-id="47e26-128">SharePoint-Produkte können eine vorhandene Datenbankinstanz verwenden.</span><span class="sxs-lookup"><span data-stu-id="47e26-128">SharePoint products can use an existing database instance.</span></span> <span data-ttu-id="47e26-129">Falls keine Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)] installiert ist, installiert das Setupprogramm für SharePoint-Produkte die SQL Server Express-Edition für die SharePoint-Anwendungsdatenbanken.</span><span class="sxs-lookup"><span data-stu-id="47e26-129">If an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] is not installed, the SharePoint Products Setup program installs SQL Server Express Edition for the SharePoint application databases.</span></span>  
  
-   <span data-ttu-id="47e26-130">Die SQL Server Express-Edition kann nicht für die Datenbank der Berichtsserverinstanz verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="47e26-130">The report server instance cannot use the SQL Server Express Edition for its database.</span></span> <span data-ttu-id="47e26-131">Die mit dem SharePoint-Produkt installierte Instanz der SQL Server Express Edition kann jedoch parallel mit anderen Datenbank-Engine-Editionen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="47e26-131">However, the SQL Server Express Edition instance installed by the SharePoint product can exist side-by-side with other Database Engine editions.</span></span>  
  
##  <a name="sscrescent-requirements"></a><a name="bkmk_powerview"></a><span data-ttu-id="47e26-132">[!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)]Anforderungen</span><span class="sxs-lookup"><span data-stu-id="47e26-132">[!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] Requirements</span></span>

 <span data-ttu-id="47e26-133">Lesen Sie die aktuelle [Power View-Dokumentation](https://office.microsoft.com/excel-help/power-view-explore-visualize-and-present-your-data-HA102835634.aspx) auf Office.Microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="47e26-133">Review the most up-to-date [Power View documentation](https://office.microsoft.com/excel-help/power-view-explore-visualize-and-present-your-data-HA102835634.aspx) on Office.Microsoft.com.</span></span> [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] <span data-ttu-id="47e26-134">ist eine Funktion von Microsoft Excel 2013 und Bestandteil des [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Reporting Services-Add-Ins für die Enterprise Edition von Microsoft SharePoint Server 2010 und 2013.</span><span class="sxs-lookup"><span data-stu-id="47e26-134">is a feature of Microsoft Excel 2013, and is part of the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Reporting Services add-in for Microsoft SharePoint Server 2010 and 2013 Enterprise Editions.</span></span>  
  
##  <a name="more-information"></a><a name="bkmk_more_information"></a> <span data-ttu-id="47e26-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="47e26-135">More Information</span></span>

 <span data-ttu-id="47e26-136">Weitere Informationen zu SharePoint-Änderungen finden [Sie unter Änderungen von SharePoint 2010 zu SharePoint 2013](https://technet.microsoft.com/library/ff607742\(office.15\).aspx) ( https://technet.microsoft.com/library/ff607742(office.15).aspx) .</span><span class="sxs-lookup"><span data-stu-id="47e26-136">For information on SharePoint changes, see [Changes from SharePoint 2010 to SharePoint 2013](https://technet.microsoft.com/library/ff607742\(office.15\).aspx) (https://technet.microsoft.com/library/ff607742(office.15).aspx).</span></span>  
  
 <span data-ttu-id="47e26-137">[Anmerkungen zu dieser Version von SQL Server 2014](https://go.microsoft.com/fwlink/?LinkID=296445).</span><span class="sxs-lookup"><span data-stu-id="47e26-137">[SQL Server 2014 Release Notes](https://go.microsoft.com/fwlink/?LinkID=296445).</span></span>  
  
