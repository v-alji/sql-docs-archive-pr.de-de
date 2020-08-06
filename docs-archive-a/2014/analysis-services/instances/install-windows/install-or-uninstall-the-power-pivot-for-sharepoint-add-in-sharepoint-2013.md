---
title: Installieren oder Deinstallieren des PowerPivot für SharePoint-Add-Ins (SharePoint 2013) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: fe13ce8b-9369-4126-928a-9426f9119424
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7df54d11021163167149e5b0c1edd960fee1a2ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697281"
---
# <a name="install-or-uninstall-the-powerpivot-for-sharepoint-add-in-sharepoint-2013"></a><span data-ttu-id="461ac-102">Installieren oder Deinstallieren des PowerPivot für SharePoint-Add-Ins (SharePoint 2013)</span><span class="sxs-lookup"><span data-stu-id="461ac-102">Install or Uninstall the PowerPivot for SharePoint Add-in (SharePoint 2013)</span></span>
  [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] <span data-ttu-id="461ac-103">ist eine Sammlung von Anwendungsserverkomponenten und Back-End-Diensten, die [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] -Datenzugriff in einer [!INCLUDE[SPS2013](../../../includes/sps2013-md.md)] -Farm ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="461ac-103">is a collection of application server components and back-end services that provide [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] data access in a [!INCLUDE[SPS2013](../../../includes/sps2013-md.md)] farm.</span></span> <span data-ttu-id="461ac-104">Das [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] für SharePoint-Add-In (**spPowerpivot.msi**) ist ein Installationspaket, mit dem die Anwendungsserverkomponenten installiert werden.</span><span class="sxs-lookup"><span data-stu-id="461ac-104">The [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] for SharePoint add-in (**spPowerpivot.msi**) is an installer package used to install the application server components.</span></span>

-   <span data-ttu-id="461ac-105">Für SharePoint 2010-Bereitstellungen ist das Add-In nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="461ac-105">The add-in is not required for SharePoint 2010 deployments.</span></span>

-   <span data-ttu-id="461ac-106">In einer einzelnen Serverbereitstellung, die SharePoint 2013 und [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] im SharePoint-Modus umfasst, ist das Add-In nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="461ac-106">The add-in is not required on a single server deployment that includes SharePoint 2013 and [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] in SharePoint mode.</span></span> <span data-ttu-id="461ac-107">Wenn Sie einen [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] -Server im SharePoint-Modus installieren, sind die durch das Add-In installierten Komponenten bereits enthalten.</span><span class="sxs-lookup"><span data-stu-id="461ac-107">The components installed by the add-in are included when you install an [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] server in SharePoint mode.</span></span> <span data-ttu-id="461ac-108">Diagramme von Beispielsbereitstellungen mit dem Add-In finden Sie unter [Deployment Topologies for SQL Server BI Features in SharePoint](../../../sql-server/install/deployment-topologies-for-sql-server-bi-features-in-sharepoint.md).</span><span class="sxs-lookup"><span data-stu-id="461ac-108">For diagrams of example deployments with the add-in, see [Deployment Topologies for SQL Server BI Features in SharePoint](../../../sql-server/install/deployment-topologies-for-sql-server-bi-features-in-sharepoint.md).</span></span>

 <span data-ttu-id="461ac-109">**Hinweis:** In diesem Thema wird das Installieren der [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] -Lösungsdateien sowie des [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] für SharePoint 2013-Konfigurationstools beschrieben.</span><span class="sxs-lookup"><span data-stu-id="461ac-109">**Note:** This topic describes installing the [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] solution files and [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] for SharePoint 2013 Configuration tool.</span></span> <span data-ttu-id="461ac-110">Nach der Installation finden Sie im folgenden Thema Informationen zum Konfigurationstool und zusätzlichen Features, zum Konfigurieren von Power Pivot und zum Bereitstellen von [Lösungen &#40;SharePoint 2013&#41;](https://docs.microsoft.com/analysis-services/instances/install-windows/configure-power-pivot-and-deploy-solutions-sharepoint-2013).</span><span class="sxs-lookup"><span data-stu-id="461ac-110">After the installation, see the following topic for information on the configuration tool and additional features, [Configure PowerPivot and Deploy Solutions &#40;SharePoint 2013&#41;](https://docs.microsoft.com/analysis-services/instances/install-windows/configure-power-pivot-and-deploy-solutions-sharepoint-2013).</span></span>

 <span data-ttu-id="461ac-111">Informationen zum Herunterladen von **spPowerPivot.msi**finden Sie unter [Microsoft® SQL Server® 2014 PowerPivot® für Microsoft SharePoint®](https://go.microsoft.com/fwlink/?LinkID=324854).</span><span class="sxs-lookup"><span data-stu-id="461ac-111">For information on how to download **spPowerPivot.msi**, see [Microsoft® SQL Server® 2014 PowerPivot® for Microsoft SharePoint®](https://go.microsoft.com/fwlink/?LinkID=324854).</span></span>

 <span data-ttu-id="461ac-112">**In diesem Thema:**</span><span class="sxs-lookup"><span data-stu-id="461ac-112">**In this topic:**</span></span>

-   [<span data-ttu-id="461ac-113">Hintergrund</span><span class="sxs-lookup"><span data-stu-id="461ac-113">Background</span></span>](#bkmk_background)

-   [<span data-ttu-id="461ac-114">Wo soll spPowerPivot.msi installiert werden?</span><span class="sxs-lookup"><span data-stu-id="461ac-114">Where to Install spPowerPivot.msi?</span></span>](#bkmk_where_to_install)

-   [<span data-ttu-id="461ac-115">Anforderungen und erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="461ac-115">Requirements and Prerequisites</span></span>](#bkmk_prereq)

-   [<span data-ttu-id="461ac-116">So installieren Sie PowerPivot für SharePoint</span><span class="sxs-lookup"><span data-stu-id="461ac-116">To Install PowerPivot for SharePoint</span></span>](#bkmk_install)

-   [<span data-ttu-id="461ac-117">Bereitstellen der SharePoint-Lösungsdateien mit dem PowerPivot für SharePoint 2013-Konfigurationstool</span><span class="sxs-lookup"><span data-stu-id="461ac-117">Deploy the SharePoint Solution Files with the PowerPivot for SharePoint 2013 Configuration Tool</span></span>](#bkmk_deploy_solution)

-   [<span data-ttu-id="461ac-118">Deinstallieren oder Reparieren des Add-Ins</span><span class="sxs-lookup"><span data-stu-id="461ac-118">Uninstall or repair the add-in</span></span>](#bkmk_remove_addin)

##  <a name="background"></a><a name="bkmk_background"></a> <span data-ttu-id="461ac-119">Hintergrund</span><span class="sxs-lookup"><span data-stu-id="461ac-119">Background</span></span>

-   <span data-ttu-id="461ac-120">**Anwendungsserver:** [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] -Funktionen in SharePoint 2013 umfassen die Verwendung von Arbeitsmappen als Datenquelle, die planmäßige Datenaktualisierung und das [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] -Management-Dashboard.</span><span class="sxs-lookup"><span data-stu-id="461ac-120">**Application Server:** [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] functionality in SharePoint 2013 includes using workbooks as a data source, scheduled data refresh, and the [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] Management Dashboard.</span></span>

     [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] <span data-ttu-id="461ac-121">ist ein [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows Installer-Paket (**spPowerpivot.msi**), das Analysis Services-Clientbibliotheken bereitstellt und [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] -Installationsdateien auf den Computer kopiert.</span><span class="sxs-lookup"><span data-stu-id="461ac-121">is a [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows Installer package (**spPowerpivot.msi**) that deploys Analysis Services client libraries and copies [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] installation files to the computer.</span></span> <span data-ttu-id="461ac-122">[!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] -Funktionen in SharePoint werden vom Installationsprogramm nicht bereitgestellt oder konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="461ac-122">The installer does not deploy or configure [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] features in SharePoint.</span></span> <span data-ttu-id="461ac-123">Die folgenden Komponenten sind standardmäßig installiert:</span><span class="sxs-lookup"><span data-stu-id="461ac-123">The following components install by default:</span></span>

    -   [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] <span data-ttu-id="461ac-124">2013. Diese Komponente enthält PowerShell-Skripts (PS1-Dateien), SharePoint-Lösungspakete (WSP) und das [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] 2013-Konfigurationstool zum Bereitstellen von [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] in einer SharePoint 2013-Farm.</span><span class="sxs-lookup"><span data-stu-id="461ac-124">2013. This component includes PowerShell scripts (.ps1 files), SharePoint solution packages (.wsp), and the [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] 2013 configuration tool to deploy [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] in a SharePoint 2013 farm.</span></span>

    -   [!INCLUDE[msCoName](../../../includes/msconame-md.md)] <span data-ttu-id="461ac-125">OLE DB-Anbieter für Analysis Services (MSOLAP).</span><span class="sxs-lookup"><span data-stu-id="461ac-125">OLE DB Provider for Analysis Services (MSOLAP).</span></span>

    -   <span data-ttu-id="461ac-126">ADOMD.NET-Datenanbieter.</span><span class="sxs-lookup"><span data-stu-id="461ac-126">ADOMD.NET data provider.</span></span>

    -   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="461ac-127">Analysis Management Objects.</span><span class="sxs-lookup"><span data-stu-id="461ac-127">Analysis Management Objects.</span></span>

-   <span data-ttu-id="461ac-128">**Back-End-Dienste:** Wenn Sie [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] für Excel verwenden, um Arbeitsmappen mit analytischen Daten zu erstellen, müssen Sie Excel Services mit einem BI-Server konfigurieren, auf dem [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] im SharePoint-Modus ausgeführt wird, um in einer Serverumgebung auf die betreffenden Daten zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="461ac-128">**Backend services:** If you use [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] for Excel to create workbooks that contain analytical data, you must have Excel Services configured with a BI server running [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] in SharePoint mode to access that data in a server environment.</span></span> <span data-ttu-id="461ac-129">Sie können SQL Server-Setup auf einem Computer ausführen, auf dem SharePoint Server 2013 installiert ist, oder auf einem anderen Computer, der keine SharePoint-Software enthält.</span><span class="sxs-lookup"><span data-stu-id="461ac-129">You can run SQL Server Setup on a computer that has SharePoint Server 2013 installed, or on a different computer that has no SharePoint software.</span></span> <span data-ttu-id="461ac-130">Zwischen Analysis Services und SharePoint bestehen keine Abhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="461ac-130">Analysis Services does not have any dependencies on SharePoint.</span></span>

     <span data-ttu-id="461ac-131">Weitere Informationen zum Installieren, Deinstallieren und Konfigurieren der Back-End-Dienste finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="461ac-131">For more information on installing, uninstalling, and configuring the backend services, see the following:</span></span>

    -   [<span data-ttu-id="461ac-132">PowerPivot für SharePoint 2013 Installation</span><span class="sxs-lookup"><span data-stu-id="461ac-132">PowerPivot for SharePoint 2013 Installation</span></span>](https://docs.microsoft.com/analysis-services/instances/install-windows/install-analysis-services-in-power-pivot-mode)

    -   [<span data-ttu-id="461ac-133">Deinstallieren von PowerPivot für SharePoint</span><span class="sxs-lookup"><span data-stu-id="461ac-133">Uninstall PowerPivot for SharePoint</span></span>](../../../sql-server/install/uninstall-power-pivot-for-sharepoint.md)

##  <a name="where-to-install-sppowerpivotmsi"></a><a name="bkmk_where_to_install"></a> <span data-ttu-id="461ac-134">Installationsort der Datei "spPowerPivot.msi"</span><span class="sxs-lookup"><span data-stu-id="461ac-134">Where to Install spPowerPivot.msi?</span></span>
 <span data-ttu-id="461ac-135">Als bewährte Methode wird empfohlen, **spPowerPivot.msi** aus Konsistenzgründen auf allen Servern in der SharePoint-Farm zu installieren, einschließlich der Anwendungsserver und Web-Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="461ac-135">A recommended best practice is to install **spPowerPivot.msi** on all servers in the SharePoint farm for configuration consistency, including application servers and web-front end servers.</span></span> <span data-ttu-id="461ac-136">Das Installationspaket schließt die Analysis Services-Datenanbieter sowie das [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] -Konfigurationstool ein.</span><span class="sxs-lookup"><span data-stu-id="461ac-136">The installer package includes the Analysis Services data providers as well as the [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] configuration tool.</span></span> <span data-ttu-id="461ac-137">Bei der Installation von **spPowerPivot.msi** können Sie die Installation anpassen, indem Sie einzelne Komponenten ausschließen.</span><span class="sxs-lookup"><span data-stu-id="461ac-137">When you install **spPowerPivot.msi** you can customize the installation by excluding individual components.</span></span>

 <span data-ttu-id="461ac-138">**Datenanbieter:** Mehrere SharePoint- und SQL Server-Technologien verwenden die Analysis Services-Datenanbieter einschließlich Excel Services, PerformancePoint Services und Power View.</span><span class="sxs-lookup"><span data-stu-id="461ac-138">**Data providers:** Several SharePoint and SQL Server technologies use the Analysis Services data providers including Excel Services, PerformancePoint Services, and Power View.</span></span> <span data-ttu-id="461ac-139">Durch die Installation von **SpPowerPivot.msi** auf allen SharePoint-Servern wird sichergestellt, dass der vollständige Satz der Analysis Services-Datenanbieter und PowerPivot-Konnektivität durchgehend in der Farm verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="461ac-139">Installing **spPowerPivot.msi** on all SharePoint servers ensures the full set of Analysis Services data providers and PowerPivot connectivity is consistently available across the farm.</span></span>

> [!NOTE]
>  <span data-ttu-id="461ac-140">Sie müssen die Analysis Services-Datenanbieter mit **spPowerPivot.msi**auf einem SharePoint 2013-Server installieren.</span><span class="sxs-lookup"><span data-stu-id="461ac-140">You must install the Analysis Services data providers on a SharePoint 2013 server using **spPowerPivot.msi**.</span></span> <span data-ttu-id="461ac-141">Andere im [!INCLUDE[ssSQL14](../../../includes/sssql14-md.md)] Feature Pack verfügbaren Installationspakete werden nicht unterstützt, da diese Pakete keine SharePoint 2013-Unterstützungsdateien enthalten, die von den Datenanbietern in dieser Umgebung benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="461ac-141">Other installer packages available in the [!INCLUDE[ssSQL14](../../../includes/sssql14-md.md)] Feature Pack are not supported because these packages do not include the SharePoint 2013 support files that the data providers require in this environment.</span></span>

 <span data-ttu-id="461ac-142">**Konfigurationstool:** Das PowerPivot für SharePoint 2013-Konfigurationstool ist auf nur einem der SharePoint-Server erforderlich.</span><span class="sxs-lookup"><span data-stu-id="461ac-142">**Configuration Tool:** The PowerPivot for SharePoint 2013 configuration tool is required on only one of the SharePoint servers.</span></span> <span data-ttu-id="461ac-143">Als bewährte Methode in Multiserverfarmen empfiehlt es sich, das Konfigurationstool auf mindestens zwei Servern zu installieren, damit Sie Zugriff auf das Konfigurationstool haben, wenn einer der beiden Server offline ist.</span><span class="sxs-lookup"><span data-stu-id="461ac-143">However a recommended best practice in multi-server farms is to install the configuration tool on at least two servers so you have access to the configuration tool if one of the two servers is offline.</span></span>

##  <a name="requirements-and-prerequisites"></a><a name="bkmk_prereq"></a><span data-ttu-id="461ac-144">Anforderungen und Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="461ac-144">Requirements and Prerequisites</span></span>

-   [!INCLUDE[msCoName](../../../includes/msconame-md.md)] <span data-ttu-id="461ac-145">SharePoint Server 2013</span><span class="sxs-lookup"><span data-stu-id="461ac-145">SharePoint Server 2013.</span></span>

-   <span data-ttu-id="461ac-146">In Übereinstimmung mit den Anforderungen von SharePoint-Produkten und -Technologien ist**spPowerPivot.msi** nur für 64-Bit ausgelegt.</span><span class="sxs-lookup"><span data-stu-id="461ac-146">**spPowerPivot.msi** is 64-bit only, in accordance with the requirements of SharePoint products and technologies.</span></span>

-   <span data-ttu-id="461ac-147">Ein [!INCLUDE[ssASCurrent](../../../includes/ssascurrent-md.md)] -Server im PowerPivot-Modus.</span><span class="sxs-lookup"><span data-stu-id="461ac-147">A [!INCLUDE[ssASCurrent](../../../includes/ssascurrent-md.md)] server in PowerPivot mode.</span></span> <span data-ttu-id="461ac-148">Excel Services verwenden die SQL Server Analysis Services-Instanz als PowerPivot-Server.</span><span class="sxs-lookup"><span data-stu-id="461ac-148">Excel Services will use the SQL Server Analysis Services instance as a PowerPivot server.</span></span> <span data-ttu-id="461ac-149">Analysis Services können auf dem lokalen oder einem Remotecomputer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="461ac-149">Analysis Services can run on the local or a remote computer.</span></span>

-   <span data-ttu-id="461ac-150">**Berechtigungen:** Zur Installation von [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)]muss der aktuelle Benutzer über Administratorrechte auf dem Computer verfügen und Mitglied der Gruppe der SharePoint-Farmadministratoren sein.</span><span class="sxs-lookup"><span data-stu-id="461ac-150">**Permissions:** To install [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)], the current user is required to be an administrator on the computer and a SharePoint Farm Administrators group.</span></span>

-   <span data-ttu-id="461ac-151">Weitere Informationen zu [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] Anforderungen und Voraussetzungen finden Sie unter [Hardware-und Software Anforderungen für Analysis Services Server im SharePoint-Modus &#40;SQL Server 2014&#41;](../../../sql-server/install/hardware-software-requirements-analysis-services-server-sharepoint-mode.md).</span><span class="sxs-lookup"><span data-stu-id="461ac-151">For more information on [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] requirements and pre-requisites, go to [Hardware and Software Requirements for Analysis Services Server in SharePoint Mode &#40;SQL Server 2014&#41;](../../../sql-server/install/hardware-software-requirements-analysis-services-server-sharepoint-mode.md).</span></span>

##  <a name="to-install-powerpivot-for-sharepoint"></a><a name="bkmk_install"></a><span data-ttu-id="461ac-152">So installieren Sie PowerPivot für SharePoint</span><span class="sxs-lookup"><span data-stu-id="461ac-152">To Install PowerPivot for SharePoint</span></span>
 <span data-ttu-id="461ac-153">Das Installationspaket **spPowerpivot.msi** unterstützt sowohl eine grafische Benutzeroberfläche als auch einen Befehlszeilenmodus.</span><span class="sxs-lookup"><span data-stu-id="461ac-153">The **spPowerpivot.msi** installer package supports both a graphical user interface and a command-line mode.</span></span> <span data-ttu-id="461ac-154">Beide Installationsmethoden setzen voraus, dass die MSI-Datei mit Administratorrechten ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="461ac-154">Both methods of installation require that you run the .msi with administrator privileges.</span></span> <span data-ttu-id="461ac-155">Nach der Installation finden Sie im folgenden Thema Informationen zum Konfigurationstool und zusätzlichen Features, zum Konfigurieren von Power Pivot und zum Bereitstellen von [Lösungen &#40;SharePoint 2013&#41;](https://docs.microsoft.com/analysis-services/instances/install-windows/configure-power-pivot-and-deploy-solutions-sharepoint-2013).</span><span class="sxs-lookup"><span data-stu-id="461ac-155">After the installation, see the following topic for information on the configuration tool and additional features, [Configure PowerPivot and Deploy Solutions &#40;SharePoint 2013&#41;](https://docs.microsoft.com/analysis-services/instances/install-windows/configure-power-pivot-and-deploy-solutions-sharepoint-2013).</span></span>

### <a name="user-interface-installation"></a><span data-ttu-id="461ac-156">Installation über die Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="461ac-156">User interface installation</span></span>
 <span data-ttu-id="461ac-157">Um [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] über die grafische Benutzeroberfläche zu installieren, führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="461ac-157">To install [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] with the graphical user interface, complete the following steps:</span></span>

1.  <span data-ttu-id="461ac-158">Führen Sie **SpPowerPivot.msi**aus.</span><span class="sxs-lookup"><span data-stu-id="461ac-158">Run **SpPowerPivot.msi**.</span></span>

2.  <span data-ttu-id="461ac-159">Klicken Sie auf der Willkommensseite auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="461ac-159">Click **Next** on the Welcome page.</span></span>

3.  <span data-ttu-id="461ac-160">Lesen und akzeptieren Sie den Lizenzvertrag, und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="461ac-160">Review and accept the license agreement, then click **Next**.</span></span>

4.  <span data-ttu-id="461ac-161">Auf der Seite **Funktionsauswahl** sind alle Funktionen standardmäßig ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="461ac-161">On the **Feature Selection** page, all of the features are selected by default.</span></span>

5.  <span data-ttu-id="461ac-162">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="461ac-162">Click **Next**.</span></span>

6.  <span data-ttu-id="461ac-163">Klicken Sie auf **Installieren** , um die Installation abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="461ac-163">Click **Install** to install to finish the installation.</span></span>

### <a name="command-line-installation"></a><span data-ttu-id="461ac-164">Installation über die Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="461ac-164">Command Line Installation</span></span>
 <span data-ttu-id="461ac-165">Öffnen Sie bei der Installation über die Befehlszeile eine Eingabeaufforderung mit Administratorberechtigungen, und führen Sie dann **spPowerPivot.msi**aus.</span><span class="sxs-lookup"><span data-stu-id="461ac-165">For a command-line installation, open a command prompt with administrative permissions, and then run the **spPowerPivot.msi**.</span></span> <span data-ttu-id="461ac-166">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="461ac-166">For example:</span></span>

 <span data-ttu-id="461ac-167">`Msiexec.exe /i SpPowerPivot.msi`.</span><span class="sxs-lookup"><span data-stu-id="461ac-167">`Msiexec.exe /i SpPowerPivot.msi`.</span></span>

 <span data-ttu-id="461ac-168">Um ein Installationsprotokoll zu erstellen, verwenden Sie die Standardoptionen für die MsiExec-Protokollierung.</span><span class="sxs-lookup"><span data-stu-id="461ac-168">To create an installation log, use the standard MsiExec logging switches.</span></span> <span data-ttu-id="461ac-169">Im folgenden Beispiel wird die Protokolldatei "Install_Log.txt" mithilfe des ausführlichen Protokollierungs Schalters "v" erstellt.</span><span class="sxs-lookup"><span data-stu-id="461ac-169">The following example creates the log file "Install_Log.txt" using the "v" verbose logging switch.</span></span>

```cmd
Msiexec.exe /i SpPowerPivot.msi /L v c:\test\Install_Log.txt
```

### <a name="quiet-command-line-installation-for-scripting"></a><span data-ttu-id="461ac-170">Installation über die Befehlszeile im stillen Modus unter Verwendung eines Skripts</span><span class="sxs-lookup"><span data-stu-id="461ac-170">Quiet Command Line Installation for scripting</span></span>
 <span data-ttu-id="461ac-171">Sie können die Schalter **/q** oder **/quiet** für eine "Stille" Installation verwenden, bei der keine Dialogfelder oder Warnungen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="461ac-171">You can use the **/q** or **/quiet** switches for a "quiet" installation that will not display any dialogs or warnings.</span></span> <span data-ttu-id="461ac-172">Die stille Installation ist nützlich, wenn Sie für die Installation des Add-Ins ein Skript schreiben möchten.</span><span class="sxs-lookup"><span data-stu-id="461ac-172">The quiet installation is useful if you want to script the installation of the add-in.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="461ac-173">Wenn Sie den Schalter **/q** für eine Befehlszeileninstallation im unbeaufsichtigten Modus verwenden, wird der Endbenutzer-Lizenzvertrag nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="461ac-173">If you use the **/q** switch for a silent command line installation, the end-user license agreement will not be displayed.</span></span> <span data-ttu-id="461ac-174">Unabhängig von der Installationsmethode unterliegt die Verwendung dieser Software einem Lizenzvertrag, dessen Einhaltung in Ihrer Verantwortung liegt.</span><span class="sxs-lookup"><span data-stu-id="461ac-174">Regardless of the installation method, the use of this software is governed by a license agreement and you are responsible for complying with the license agreement.</span></span>

#### <a name="to-perform-a-quiet-installation"></a><span data-ttu-id="461ac-175">So führen Sie eine stille Installation aus</span><span class="sxs-lookup"><span data-stu-id="461ac-175">To perform a quiet installation</span></span>

1.  <span data-ttu-id="461ac-176">Öffnen Sie eine Eingabeaufforderung **mit Administrator Berechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="461ac-176">Open a command prompt **with administrator permissions**.</span></span>

2.  <span data-ttu-id="461ac-177">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="461ac-177">Run the following command:</span></span>

    ```cmd
    Msiexec.exe /i spPowerPivot.msi /q
    ```

### <a name="command-line-installation-to-include-specific-components"></a><span data-ttu-id="461ac-178">Installation über die Befehlszeile, um bestimmte Komponenten einzuschließen</span><span class="sxs-lookup"><span data-stu-id="461ac-178">Command Line Installation to include specific components</span></span>
 <span data-ttu-id="461ac-179">Das [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] -Konfigurationstool ist nicht auf jedem SharePoint-Server erforderlich, es wird jedoch empfohlen, das Konfigurationstool mindestens auf zwei Servern zu installieren, damit es bei Bedarf verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="461ac-179">The [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] Configuration tool is not required on every SharePoint server, however it is recommended to install it on at least two servers so the configuration tool is available when you need it.</span></span>

 <span data-ttu-id="461ac-180">Bei der Installation von spPowerPivot.msi [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] können Sie anstelle des -Konfigurationstools die Befehlszeilenoptionen verwenden, um bestimmte Komponenten, wie die Datenanbieter, zu installieren.</span><span class="sxs-lookup"><span data-stu-id="461ac-180">When you install the spPowerPivot.msi, you can use the command line options to install specific items, such as the data providers and not the [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] Configuration tool.</span></span> <span data-ttu-id="461ac-181">Die folgende Befehlszeile stellt ein Beispiel für die Installation aller Komponenten mit Ausnahme des Konfigurationstools dar:</span><span class="sxs-lookup"><span data-stu-id="461ac-181">The following command line is an example of installing all components except the configuration tool:</span></span>

```
Msiexec /i spPowerPivot.msi AGREETOLICENSE="yes" ADDLOCAL=" SQL_OLAPDM,SQL_ADOMD,SQL_AMO,SQLAS_SP_Common"
```

|<span data-ttu-id="461ac-182">Option</span><span class="sxs-lookup"><span data-stu-id="461ac-182">Option</span></span>|<span data-ttu-id="461ac-183">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="461ac-183">Description</span></span>|
|------------|-----------------|
|<span data-ttu-id="461ac-184">Analysis_Server_SP_addin</span><span class="sxs-lookup"><span data-stu-id="461ac-184">Analysis_Server_SP_addin</span></span>|<span data-ttu-id="461ac-185">PowerPivot-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="461ac-185">PowerPivot Configuration</span></span>|
|<span data-ttu-id="461ac-186">SQL_OLAPDM</span><span class="sxs-lookup"><span data-stu-id="461ac-186">SQL_OLAPDM</span></span>|<span data-ttu-id="461ac-187">MSOLAP</span><span class="sxs-lookup"><span data-stu-id="461ac-187">MSOLAP</span></span>|
|<span data-ttu-id="461ac-188">SQL_ADOMD</span><span class="sxs-lookup"><span data-stu-id="461ac-188">SQL_ADOMD</span></span>|<span data-ttu-id="461ac-189">ADOMD.NET-Anbieter</span><span class="sxs-lookup"><span data-stu-id="461ac-189">ADOMD.net provider</span></span>|
|<span data-ttu-id="461ac-190">SQL_AMO</span><span class="sxs-lookup"><span data-stu-id="461ac-190">SQL_AMO</span></span>|<span data-ttu-id="461ac-191">AMO-Anbieter</span><span class="sxs-lookup"><span data-stu-id="461ac-191">AMO provider</span></span>|
|<span data-ttu-id="461ac-192">SQLAS_SP_Common</span><span class="sxs-lookup"><span data-stu-id="461ac-192">SQLAS_SP_Common</span></span>|<span data-ttu-id="461ac-193">Allgemeine Analysis Services-Komponenten für SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="461ac-193">Analysis Services common components for SharePoint 2013</span></span>|

##  <a name="deploy-the-sharepoint-solution-files-with-the-powerpivot-for-sharepoint-2013-configuration-tool"></a><a name="bkmk_deploy_solution"></a><span data-ttu-id="461ac-194">Bereitstellen der SharePoint-Lösungs Dateien mit dem Konfigurations Tool "PowerPivot für SharePoint 2013"</span><span class="sxs-lookup"><span data-stu-id="461ac-194">Deploy the SharePoint Solution Files with the PowerPivot for SharePoint 2013 Configuration Tool</span></span>
 <span data-ttu-id="461ac-195">Drei der Dateien, die von spPowerPivot.msi auf die Festplatte kopiert werden, sind SharePoint-Lösungsdateien.</span><span class="sxs-lookup"><span data-stu-id="461ac-195">Three of the files copied to the hard drive by spPowerPivot.msi are SharePoint solution files.</span></span> <span data-ttu-id="461ac-196">Eine Lösungsdatei bezieht sich auf die Webanwendungsebene, während sich die anderen Dateien auf die Farmebene beziehen.</span><span class="sxs-lookup"><span data-stu-id="461ac-196">The scope of one solution file is the Web application level while the scope of the other files is the farm level.</span></span> <span data-ttu-id="461ac-197">Die Dateien lauten:</span><span class="sxs-lookup"><span data-stu-id="461ac-197">The files are the following:</span></span>

-   `PowerPivotFarmSolution.wsp`

-   `PowerPivotFarm14Solution.wsp`

-   `PowerPivotWebApplicationSolution.wsp`

 <span data-ttu-id="461ac-198">Die Lösungsdateien werden in den folgenden Ordner kopiert:</span><span class="sxs-lookup"><span data-stu-id="461ac-198">The solution files are copied to the following folder:</span></span>

 `C:\Program Files\Microsoft SQL Server\120\Tools\PowerPivotTools\SPAddinConfiguration\Resources`

 <span data-ttu-id="461ac-199">Nach Abschluss der MSI-Installation führen Sie das [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] -Konfigurationstool aus, um die Lösungen in der SharePoint-Farm zu konfigurieren und bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="461ac-199">Following the .msi installation, run the [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] Configuration Tool to configure and deploy the solutions in the SharePoint farm.</span></span>

### <a name="to-start-the-configuration-tool"></a><span data-ttu-id="461ac-200">So starten Sie das Konfigurationstool</span><span class="sxs-lookup"><span data-stu-id="461ac-200">To start the configuration tool</span></span> 

 <span data-ttu-id="461ac-201">Geben Sie auf dem Windows-Start Bildschirm "Power" ein, und klicken Sie in den Suchergebnissen der apps auf **PowerPivot für SharePoint 2013-Konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="461ac-201">From the Windows Start screen type "power" and in the Apps search results, click **PowerPivot for SharePoint 2013 Configuration**.</span></span> <span data-ttu-id="461ac-202">Beachten Sie, dass die Suchergebnisse u. U. zwei Links enthalten, weil [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Setup separate [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] -Konfigurationstools für SharePoint 2010 und SharePoint 2013 installiert.</span><span class="sxs-lookup"><span data-stu-id="461ac-202">Note that the search results may include two links because [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] setup installs separate [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] configuration tools for SharePoint 2010 and SharePoint 2013.</span></span> <span data-ttu-id="461ac-203">Stellen Sie sicher, dass Sie das [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] für SharePoint 2013-Konfigurationstool starten.</span><span class="sxs-lookup"><span data-stu-id="461ac-203">Make sure you start the [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] for SharePoint 2013 Configuration tool.</span></span>

 <span data-ttu-id="461ac-204">![zwei Power Pivot-Konfigurationstools](../../media/as-powerpivot-configtools-bothicons.gif "zwei Power Pivot-Konfigurationstools")</span><span class="sxs-lookup"><span data-stu-id="461ac-204">![two powerpivot configuration tools](../../media/as-powerpivot-configtools-bothicons.gif "two powerpivot configuration tools")</span></span>

 <span data-ttu-id="461ac-205">**Oder**</span><span class="sxs-lookup"><span data-stu-id="461ac-205">**Or**</span></span>

1.  <span data-ttu-id="461ac-206">Wechseln Sie zu **Start**, **Alle Programme**.</span><span class="sxs-lookup"><span data-stu-id="461ac-206">Go to **Start**, **All Programs**.</span></span>

2.  <span data-ttu-id="461ac-207">Klicken Sie auf **Microsoft SQL Server 2014**.</span><span class="sxs-lookup"><span data-stu-id="461ac-207">Click **Microsoft SQL Server 2014**.</span></span>

3.  <span data-ttu-id="461ac-208">Klicken Sie auf **Konfigurationstools**.</span><span class="sxs-lookup"><span data-stu-id="461ac-208">Click **Configuration Tools**.</span></span>

4.  <span data-ttu-id="461ac-209">Klicken Sie auf **Konfiguration von PowerPivot für SharePoint 2013**.</span><span class="sxs-lookup"><span data-stu-id="461ac-209">Click **PowerPivot for SharePoint 2013 Configuration**.</span></span>

 <span data-ttu-id="461ac-210">Weitere Informationen zum Konfigurationstool finden Sie unter [PowerPivot Configuration Tools](../../power-pivot-sharepoint/power-pivot-configuration-tools.md).</span><span class="sxs-lookup"><span data-stu-id="461ac-210">For more information on the configuration tool, see [PowerPivot Configuration Tools](../../power-pivot-sharepoint/power-pivot-configuration-tools.md).</span></span>

##  <a name="uninstall-or-repair-the-add-in"></a><a name="bkmk_remove_addin"></a><span data-ttu-id="461ac-211">Deinstallieren oder Reparieren des Add-ins</span><span class="sxs-lookup"><span data-stu-id="461ac-211">Uninstall or repair the add-in</span></span>

> [!CAUTION]
>  <span data-ttu-id="461ac-212">Bei der Deinstallation von **spPowerPivot.msi** werden die Datenanbieter und das Konfigurationstool deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="461ac-212">If you uninstall **spPowerPivot.msi** the data providers and the configuration tool are uninstalled.</span></span> <span data-ttu-id="461ac-213">Nach Deinstallation der Datenanbieter kann der Server keine Verbindung mit PowerPivot mehr herstellen.</span><span class="sxs-lookup"><span data-stu-id="461ac-213">Uninstalling the data providers will cause the server to be unable to connect to PowerPivot.</span></span>

 <span data-ttu-id="461ac-214">Sie können [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] mithilfe einer der folgenden Methoden deinstallieren oder reparieren:</span><span class="sxs-lookup"><span data-stu-id="461ac-214">You can uninstall or repair [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] using one of the following methods:</span></span>

1.  <span data-ttu-id="461ac-215">**Windows-Systemsteuerung:** Wählen Sie **Microsoft SQL Server 2012 PowerPivot für SharePoint 2013**aus.</span><span class="sxs-lookup"><span data-stu-id="461ac-215">**Windows control panel:** Select **Microsoft SQL Server 2012 PowerPivot for SharePoint 2013**.</span></span> <span data-ttu-id="461ac-216">Klicken Sie entweder auf **Deinstallieren** oder auf **Reparieren**.</span><span class="sxs-lookup"><span data-stu-id="461ac-216">Click either **Uninstall** or **Repair**.</span></span>

2.  <span data-ttu-id="461ac-217">Führen Sie spPowerPivot.msi aus, und wählen Sie die Option **Entfernen** oder **Reparieren** aus.</span><span class="sxs-lookup"><span data-stu-id="461ac-217">Run the spPowerPivot.msi and select the **Remove** option or the **Repair** option.</span></span>

 <span data-ttu-id="461ac-218">**Befehlszeile:** Um PowerPivot für SharePoint 2013 über die Befehlszeile zu reparieren oder zu deinstallieren, öffnen Sie die Eingabeaufforderung mit **Administratorberechtigungen** , und führen Sie einen der folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="461ac-218">**Command Line:** To repair or uninstall PowerPivot for SharePoint 2013 using the command line, open a command prompt **with administrator permissions** and run one of the following commands:</span></span>

-   <span data-ttu-id="461ac-219">Zum Reparieren führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="461ac-219">To Repair, run the following command:</span></span>

    ```cmd
    msiexec.exe /f spPowerPivot.msi
    ```

 <span data-ttu-id="461ac-220">ODER</span><span class="sxs-lookup"><span data-stu-id="461ac-220">OR</span></span>

-   <span data-ttu-id="461ac-221">Zum Deinstallieren führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="461ac-221">To uninstall, run the following command:</span></span>

    ```cmd
    msiexec.exe /uninstall spPowerPivot.msi
    ```
