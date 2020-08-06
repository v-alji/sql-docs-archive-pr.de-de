---
title: Installieren von SQL Server 2014 auf Server Core | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: 1dd294cc-5b69-4d0c-9005-3e307b75678b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d2614c43bb763757db7db46b1c7a966221da96f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697145"
---
# <a name="install-sql-server-2014-on-server-core"></a><span data-ttu-id="bc44e-102">Installieren von SQL Server 2014 unter Server Core</span><span class="sxs-lookup"><span data-stu-id="bc44e-102">Install SQL Server 2014 on Server Core</span></span>
  <span data-ttu-id="bc44e-103">Sie können [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in einer Server Core-Installation von [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 oder [!INCLUDE[win8srv](../../includes/win8srv-md.md)]installieren.</span><span class="sxs-lookup"><span data-stu-id="bc44e-103">You can install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on a Server Core installation of [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 or [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span></span> <span data-ttu-id="bc44e-104">Dieses Thema enthält setupspezifische Details zum Installieren von [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] auf Server Core.</span><span class="sxs-lookup"><span data-stu-id="bc44e-104">This topic provides setup-specific details for installing [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] on Server Core.</span></span>  
  
 <span data-ttu-id="bc44e-105">Die Server Core-Installationsoption für das Betriebssystem [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] oder [!INCLUDE[win8srv](../../includes/win8srv-md.md)] stellt eine minimale Umgebung zum Ausführen von bestimmten Serverrollen bereit.</span><span class="sxs-lookup"><span data-stu-id="bc44e-105">The Server Core installation option for the [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] or [!INCLUDE[win8srv](../../includes/win8srv-md.md)] operating system provides a minimal environment for running specific server roles.</span></span> <span data-ttu-id="bc44e-106">Dies hilft, Wartung und Verwaltungsanforderungen und die Angriffsfläche für jene Serverrollen zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="bc44e-106">This helps to reduce maintenance and management requirements and the attack surface for those server roles.</span></span> <span data-ttu-id="bc44e-107">Weitere Informationen zu Server Core, wie unter implementiert [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] , finden Sie unter [Server Core für Windows Server 2008 R2](https://go.microsoft.com/fwlink/?LinkId=202439) ( https://go.microsoft.com/fwlink/?LinkId=202439) .</span><span class="sxs-lookup"><span data-stu-id="bc44e-107">For more information on Server Core as implemented on [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)], see [Server Core for Windows Server 2008 R2](https://go.microsoft.com/fwlink/?LinkId=202439) (https://go.microsoft.com/fwlink/?LinkId=202439).</span></span> <span data-ttu-id="bc44e-108">Weitere Informationen zur Implementierung von Server Core unter [!INCLUDE[win8srv](../../includes/win8srv-md.md)] finden Sie unter [Server Core für Windows Server 2012](https://msdn.microsoft.com/library/hh846323\(VS.85\).aspx) (https://msdn.microsoft.com/library/hh846323(VS.85).aspx) ).</span><span class="sxs-lookup"><span data-stu-id="bc44e-108">For more information on Server Core as implemented on [!INCLUDE[win8srv](../../includes/win8srv-md.md)], see [Server Core for Windows Server 2012](https://msdn.microsoft.com/library/hh846323\(VS.85\).aspx) (https://msdn.microsoft.com/library/hh846323(VS.85).aspx).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="bc44e-109">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="bc44e-109">Prerequisites</span></span>  
  
|<span data-ttu-id="bc44e-110">Anforderung</span><span class="sxs-lookup"><span data-stu-id="bc44e-110">Requirement</span></span>|<span data-ttu-id="bc44e-111">So führen Sie die Installation durch</span><span class="sxs-lookup"><span data-stu-id="bc44e-111">How to install</span></span>|  
|-----------------|--------------------|  
|[!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] <span data-ttu-id="bc44e-112">2.0 SP2</span><span class="sxs-lookup"><span data-stu-id="bc44e-112">2.0 SP2</span></span>|<span data-ttu-id="bc44e-113">In der Server Core-Installation von [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 und [!INCLUDE[win8srv](../../includes/win8srv-md.md)]enthalten.</span><span class="sxs-lookup"><span data-stu-id="bc44e-113">Included in Server Core installation of [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 and [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span></span> <span data-ttu-id="bc44e-114">Wenn nicht aktiviert, aktiviert Setup es standardmäßig.</span><span class="sxs-lookup"><span data-stu-id="bc44e-114">If it is not enabled, Setup enables it by default.</span></span><br /><br /> <span data-ttu-id="bc44e-115">Es ist nicht möglich, die Versionen 2.0, 3.0 und 3.5 parallel auf einem Computer auszuführen.</span><span class="sxs-lookup"><span data-stu-id="bc44e-115">It is not possible to run versions 2.0, 3.0, and 3.5 side by side on a computer.</span></span> <span data-ttu-id="bc44e-116">Wenn Sie .NET Framework 3.5 SP1 installieren, erhalten Sie die 2.0- und 3.0-Ebenen automatisch.</span><span class="sxs-lookup"><span data-stu-id="bc44e-116">When you install the .NET Framework 3.5 SP1, you get the 2.0 and 3.0 layers automatically.</span></span>|  
|[!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] <span data-ttu-id="bc44e-117">3.5 SP1 Vollständiges Profil</span><span class="sxs-lookup"><span data-stu-id="bc44e-117">3.5 SP1 Full Profile</span></span>|<span data-ttu-id="bc44e-118">In der Server Core-Installation von [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 enthalten.</span><span class="sxs-lookup"><span data-stu-id="bc44e-118">Included in Server Core installation of [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1.</span></span> <span data-ttu-id="bc44e-119">Wenn nicht aktiviert, aktiviert Setup es standardmäßig.</span><span class="sxs-lookup"><span data-stu-id="bc44e-119">If it is not enabled, Setup enables it by default.</span></span><br /><br /> <span data-ttu-id="bc44e-120">Auf einem Computer mit einem Windows-Serverbetriebssystem müssen Sie .NET Framework 3.5 SP1 herunterladen und installieren, bevor Sie Setup ausführen, um von .NET 3.5 SP1 abhängige Komponenten installieren zu können.</span><span class="sxs-lookup"><span data-stu-id="bc44e-120">On a computer with Windows server operating system you must download and install .NET Framework 3.5 SP1 before you run Setup, to install components dependent on .NET 3.5 SP1.</span></span><br /><br /> <span data-ttu-id="bc44e-121">Weitere Informationen zu den Empfehlungen und Anleitungen zum Abrufen und Aktivieren von .NET Framework 3,5 in finden Sie unter [!INCLUDE[win8srv](../../includes/win8srv-md.md)] [Überlegungen zur Bereitstellung von Microsoft .NET Framework 3,5](https://msdn.microsoft.com/library/windows/hardware/hh975396) ( https://msdn.microsoft.com/library/windows/hardware/hh975396) .</span><span class="sxs-lookup"><span data-stu-id="bc44e-121">For more information about the recommendations and guidance on how to acquire and enable .NET Framework 3.5 in [!INCLUDE[win8srv](../../includes/win8srv-md.md)], see [Microsoft .NET Framework 3.5 Deployment Considerations](https://msdn.microsoft.com/library/windows/hardware/hh975396) (https://msdn.microsoft.com/library/windows/hardware/hh975396).</span></span>|  
|[!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] <span data-ttu-id="bc44e-122">4 Server Core-Profil</span><span class="sxs-lookup"><span data-stu-id="bc44e-122">4 Server Core Profile</span></span>|<span data-ttu-id="bc44e-123">Für alle Editionen von [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] außer [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)]installiert Setup das [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] 4 Server Core-Profil als erforderliche Komponente.</span><span class="sxs-lookup"><span data-stu-id="bc44e-123">For all editions of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] except [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], Setup installs the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] 4 Server Core Profile as a prerequisite.</span></span><br /><br /> <span data-ttu-id="bc44e-124">Laden Sie für [!INCLUDE[ssExpressEd11](../../includes/ssexpressed11-md.md)] das [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] 4 Server Core-Profil von [Microsoft .NET Framework 4 (eigenständiges Installationsprogramm) für Server Core ()](https://www.microsoft.com/download/details.aspx?id=17718) herunter, https://www.microsoft.com/download/details.aspx?id=17718) und installieren Sie es, bevor Sie mit dem Setup fortfahren.</span><span class="sxs-lookup"><span data-stu-id="bc44e-124">For [!INCLUDE[ssExpressEd11](../../includes/ssexpressed11-md.md)], download the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] 4 Server Core Profile from [Microsoft .NET Framework 4 (Standalone Installer) for Server Core](https://www.microsoft.com/download/details.aspx?id=17718) (https://www.microsoft.com/download/details.aspx?id=17718), and install it before you proceed with the setup.</span></span>|  
|<span data-ttu-id="bc44e-125">Windows Installer 4.5</span><span class="sxs-lookup"><span data-stu-id="bc44e-125">Windows Installer 4.5</span></span>|<span data-ttu-id="bc44e-126">Im Lieferumfang der Server Core-Installation von [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 und [!INCLUDE[win8srv](../../includes/win8srv-md.md)]enthalten.</span><span class="sxs-lookup"><span data-stu-id="bc44e-126">Shipped with Server Core installation of [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 and [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span></span>|  
|<span data-ttu-id="bc44e-127">Windows PowerShell 2.0</span><span class="sxs-lookup"><span data-stu-id="bc44e-127">Windows PowerShell 2.0</span></span>|<span data-ttu-id="bc44e-128">Im Lieferumfang der Server Core-Installation von [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 und [!INCLUDE[win8srv](../../includes/win8srv-md.md)]enthalten.</span><span class="sxs-lookup"><span data-stu-id="bc44e-128">Shipped with Server Core installation of [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 and [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span></span>|  
  
##  <a name="supported-features"></a><a name="BK_SupportedFeatures"></a> <span data-ttu-id="bc44e-129">Unterstützte Funktionen</span><span class="sxs-lookup"><span data-stu-id="bc44e-129">Supported Features</span></span>  
 <span data-ttu-id="bc44e-130">In der folgenden Tabelle finden Sie die Funktionen, die in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] bei einer Server Core-Installation von [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 und [!INCLUDE[win8srv](../../includes/win8srv-md.md)]unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="bc44e-130">Use the following table to find which features are supported in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] on a Server Core installation of [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 and [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span></span>  
  
|<span data-ttu-id="bc44e-131">Funktion</span><span class="sxs-lookup"><span data-stu-id="bc44e-131">Feature</span></span>|<span data-ttu-id="bc44e-132">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="bc44e-132">Supported</span></span>|  
|-------------|---------------|  
|[!INCLUDE[ssDE](../../includes/ssde-md.md)] <span data-ttu-id="bc44e-133">-Dienste</span><span class="sxs-lookup"><span data-stu-id="bc44e-133">Services</span></span>|<span data-ttu-id="bc44e-134">Ja</span><span class="sxs-lookup"><span data-stu-id="bc44e-134">Yes</span></span>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="bc44e-135">Replikation</span><span class="sxs-lookup"><span data-stu-id="bc44e-135">Replication</span></span>|<span data-ttu-id="bc44e-136">Ja</span><span class="sxs-lookup"><span data-stu-id="bc44e-136">Yes</span></span>|  
|<span data-ttu-id="bc44e-137">Volltextsuche</span><span class="sxs-lookup"><span data-stu-id="bc44e-137">Full Text Search</span></span>|<span data-ttu-id="bc44e-138">Ja</span><span class="sxs-lookup"><span data-stu-id="bc44e-138">Yes</span></span>|  
|[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]|<span data-ttu-id="bc44e-139">Ja</span><span class="sxs-lookup"><span data-stu-id="bc44e-139">Yes</span></span>|  
|[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]|<span data-ttu-id="bc44e-140">Nein</span><span class="sxs-lookup"><span data-stu-id="bc44e-140">No</span></span>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="bc44e-141">Data Tools (SSDT)</span><span class="sxs-lookup"><span data-stu-id="bc44e-141">Data Tools (SSDT)</span></span>|<span data-ttu-id="bc44e-142">Nein</span><span class="sxs-lookup"><span data-stu-id="bc44e-142">No</span></span>|  
|<span data-ttu-id="bc44e-143">Konnektivität der Clienttools</span><span class="sxs-lookup"><span data-stu-id="bc44e-143">Client Tools Connectivity</span></span>|<span data-ttu-id="bc44e-144">Ja</span><span class="sxs-lookup"><span data-stu-id="bc44e-144">Yes</span></span>|  
|<span data-ttu-id="bc44e-145">Integration Services Server<sup>[1]</sup></span><span class="sxs-lookup"><span data-stu-id="bc44e-145">Integration Services Server<sup>[1]</sup></span></span>|<span data-ttu-id="bc44e-146">Ja</span><span class="sxs-lookup"><span data-stu-id="bc44e-146">Yes</span></span>|  
|<span data-ttu-id="bc44e-147">Clienttools-Abwärtskompatibilität</span><span class="sxs-lookup"><span data-stu-id="bc44e-147">Client Tools Backward Compatibility</span></span>|<span data-ttu-id="bc44e-148">Nein</span><span class="sxs-lookup"><span data-stu-id="bc44e-148">No</span></span>|  
|<span data-ttu-id="bc44e-149">Clienttools SDK</span><span class="sxs-lookup"><span data-stu-id="bc44e-149">Client Tools SDK</span></span>|<span data-ttu-id="bc44e-150">Nein</span><span class="sxs-lookup"><span data-stu-id="bc44e-150">No</span></span>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="bc44e-151">-Onlinedokumentation</span><span class="sxs-lookup"><span data-stu-id="bc44e-151">Books Online</span></span>|<span data-ttu-id="bc44e-152">Nein</span><span class="sxs-lookup"><span data-stu-id="bc44e-152">No</span></span>|  
|<span data-ttu-id="bc44e-153">Verwaltungstools - Einfach</span><span class="sxs-lookup"><span data-stu-id="bc44e-153">Management Tools - Basic</span></span>|<span data-ttu-id="bc44e-154">Nur Remote<sup>[2]</sup></span><span class="sxs-lookup"><span data-stu-id="bc44e-154">Remote Only<sup>[2]</sup></span></span>|  
|<span data-ttu-id="bc44e-155">Verwaltungstools – Vollständig</span><span class="sxs-lookup"><span data-stu-id="bc44e-155">Management Tools - Complete</span></span>|<span data-ttu-id="bc44e-156">Nur Remote<sup>[2]</sup></span><span class="sxs-lookup"><span data-stu-id="bc44e-156">Remote Only<sup>[2]</sup></span></span>|  
|<span data-ttu-id="bc44e-157">Distributed Replay Controller</span><span class="sxs-lookup"><span data-stu-id="bc44e-157">Distributed Replay Controller</span></span>|<span data-ttu-id="bc44e-158">Nein</span><span class="sxs-lookup"><span data-stu-id="bc44e-158">No</span></span>|  
|<span data-ttu-id="bc44e-159">Distributed Replay Client</span><span class="sxs-lookup"><span data-stu-id="bc44e-159">Distributed Replay Client</span></span>|<span data-ttu-id="bc44e-160">Nur Remote<sup>[2]</sup></span><span class="sxs-lookup"><span data-stu-id="bc44e-160">Remote Only<sup>[2]</sup></span></span>|  
|<span data-ttu-id="bc44e-161">SQL Client Connectivity SDK</span><span class="sxs-lookup"><span data-stu-id="bc44e-161">SQL Client Connectivity SDK</span></span>|<span data-ttu-id="bc44e-162">Ja</span><span class="sxs-lookup"><span data-stu-id="bc44e-162">Yes</span></span>|  
|<span data-ttu-id="bc44e-163">Microsoft Sync Framework</span><span class="sxs-lookup"><span data-stu-id="bc44e-163">Microsoft Sync Framework</span></span>|<span data-ttu-id="bc44e-164">Ja<sup>[3]</sup></span><span class="sxs-lookup"><span data-stu-id="bc44e-164">Yes<sup>[3]</sup></span></span>|  
|[!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)]|<span data-ttu-id="bc44e-165">Nein</span><span class="sxs-lookup"><span data-stu-id="bc44e-165">No</span></span>|  
|[!INCLUDE[ssDQSnoversion](../../includes/ssdqsnoversion-md.md)]|<span data-ttu-id="bc44e-166">Nein</span><span class="sxs-lookup"><span data-stu-id="bc44e-166">No</span></span>|  
  
 <span data-ttu-id="bc44e-167"><sup>[1]</sup> Weitere Informationen zum neuen Integration Services-Server und dessen Funktionen in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] finden Sie unter [Integration Services &#40;SSIS&#41; Server](../../integration-services/catalog/integration-services-ssis-server-and-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="bc44e-167"><sup>[1]</sup>For more information about the new Integration Services Server and its features in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], see [Integration Services &#40;SSIS&#41; Server](../../integration-services/catalog/integration-services-ssis-server-and-catalog.md).</span></span>  
  
 <span data-ttu-id="bc44e-168"><sup>[2]</sup> Die Installation dieser Funktionen unter Server Core wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="bc44e-168"><sup>[2]</sup>Installation of these features on Server Core is not supported.</span></span> <span data-ttu-id="bc44e-169">Diese Komponenten können auf einem anderen Server, der nicht [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] Server Core SP1 oder [!INCLUDE[win8srv](../../includes/win8srv-md.md)] Server Core aufweist, installiert und mit den auf Server Core installierten [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Diensten verbunden werden.</span><span class="sxs-lookup"><span data-stu-id="bc44e-169">These components can be installed on a different server that is not [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] Server Core SP1 or [!INCLUDE[win8srv](../../includes/win8srv-md.md)] Server Core, and connected to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] services installed on Server Core.</span></span>  
  
 <span data-ttu-id="bc44e-170"><sup>[3]</sup> Microsoft Sync Framework ist nicht im [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Installationspaket enthalten.</span><span class="sxs-lookup"><span data-stu-id="bc44e-170"><sup>[3]</sup>Microsoft Sync Framework is not included in the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] installation package.</span></span> <span data-ttu-id="bc44e-171">Sie können die geeignete Sync Framework-Version von diesem [Microsoft Download Center](https://go.microsoft.com/fwlink/?LinkId=221788) herunterladen ( https://go.microsoft.com/fwlink/?LinkId=221788) Seite und auf einem Computer installieren, auf dem die Server Core-Installation von SP1 oder ausgeführt wird) [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] [!INCLUDE[win8srv](../../includes/win8srv-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bc44e-171">You can download the appropriate version of Sync Framework from this [Microsoft Download Center](https://go.microsoft.com/fwlink/?LinkId=221788) (https://go.microsoft.com/fwlink/?LinkId=221788) page and install it on a computer that is running Server Core installation of [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 or [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span></span>  
  
## <a name="supported-scenario-matrix"></a><span data-ttu-id="bc44e-172">Matrix unterstützter Szenarien</span><span class="sxs-lookup"><span data-stu-id="bc44e-172">Supported Scenario Matrix</span></span>  
 <span data-ttu-id="bc44e-173">In der folgenden Tabelle wird die Matrix unterstützter Szenarien zum Installieren von [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] auf einer Server Core-Installation von [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 und [!INCLUDE[win8srv](../../includes/win8srv-md.md)]angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bc44e-173">The following table shows the supported scenario matrix for installing [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] on a Server Core installation of [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 and [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span></span>  
  
|||  
|-|-|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="bc44e-174">Editionen</span><span class="sxs-lookup"><span data-stu-id="bc44e-174">editions</span></span>|<span data-ttu-id="bc44e-175">Alle [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] 64-Bit-Editionen<sup>[1]</sup></span><span class="sxs-lookup"><span data-stu-id="bc44e-175">All [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] 64-bit editions<sup>[1]</sup></span></span>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="bc44e-176">-Sprache</span><span class="sxs-lookup"><span data-stu-id="bc44e-176">language</span></span>|<span data-ttu-id="bc44e-177">Alle Sprachen</span><span class="sxs-lookup"><span data-stu-id="bc44e-177">All languages</span></span>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="bc44e-178">-Sprache auf Betriebssystem Sprache/Gebietsschema (Kombination)</span><span class="sxs-lookup"><span data-stu-id="bc44e-178">language on OS language/locale (combination)</span></span>|<span data-ttu-id="bc44e-179">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] auf JPN (Japanisch) Windows</span><span class="sxs-lookup"><span data-stu-id="bc44e-179">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on JPN (Japanese) Windows</span></span><br /><br /> <span data-ttu-id="bc44e-180">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] auf GER (Deutsch) Windows</span><span class="sxs-lookup"><span data-stu-id="bc44e-180">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on GER (German) Windows</span></span><br /><br /> <span data-ttu-id="bc44e-181">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] auf CHS (Chinesisch-China) Windows</span><span class="sxs-lookup"><span data-stu-id="bc44e-181">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on CHS (Chinese-China) Windows</span></span><br /><br /> <span data-ttu-id="bc44e-182">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] auf ARA (Arabisch (SA)) Windows</span><span class="sxs-lookup"><span data-stu-id="bc44e-182">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on ARA (Arabic (SA)) Windows</span></span><br /><br /> <span data-ttu-id="bc44e-183">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] auf THA (Thai) Windows</span><span class="sxs-lookup"><span data-stu-id="bc44e-183">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on THA (Thai) Windows</span></span><br /><br /> <span data-ttu-id="bc44e-184">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] auf TRK (Türkisch) Windows</span><span class="sxs-lookup"><span data-stu-id="bc44e-184">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on TRK (Turkish) Windows</span></span><br /><br /> <span data-ttu-id="bc44e-185">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] auf pt-PT (Portugiesisch Portugal) Windows</span><span class="sxs-lookup"><span data-stu-id="bc44e-185">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on pt-PT (Portuguese Portugal) Windows</span></span><br /><br /> <span data-ttu-id="bc44e-186">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] auf ENG (Englisch) Windows</span><span class="sxs-lookup"><span data-stu-id="bc44e-186">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on ENG (English) Windows</span></span>|  
|<span data-ttu-id="bc44e-187">Windows-Edition</span><span class="sxs-lookup"><span data-stu-id="bc44e-187">Windows edition</span></span>|[!INCLUDE[win8srv](../../includes/win8srv-md.md)] <span data-ttu-id="bc44e-188">64-Bit x64 Datacenter</span><span class="sxs-lookup"><span data-stu-id="bc44e-188">64-bit x64 Datacenter</span></span><br /><br /> [!INCLUDE[win8srv](../../includes/win8srv-md.md)] <span data-ttu-id="bc44e-189">64-Bit x64 Standard</span><span class="sxs-lookup"><span data-stu-id="bc44e-189">64-bit x64 Standard</span></span><br /><br /> [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] <span data-ttu-id="bc44e-190">SP1 64-bit x64 Data Center Server Core</span><span class="sxs-lookup"><span data-stu-id="bc44e-190">SP1 64-bit x64 Data Center Server Core</span></span><br /><br /> [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] <span data-ttu-id="bc44e-191">SP1 64-Bit x64 Enterprise Server Core</span><span class="sxs-lookup"><span data-stu-id="bc44e-191">SP1 64-bit x64 Enterprise Server Core</span></span><br /><br /> [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] <span data-ttu-id="bc44e-192">SP1 64-bit x64 Standard Server Core</span><span class="sxs-lookup"><span data-stu-id="bc44e-192">SP1 64-bit x64 Standard Server Core</span></span><br /><br /> [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] <span data-ttu-id="bc44e-193">SP1 64-Bit x64 Web Server Core</span><span class="sxs-lookup"><span data-stu-id="bc44e-193">SP1 64-bit x64 Web Server Core</span></span>|  
  
 <span data-ttu-id="bc44e-194"><sup>[1]</sup> Die Installation der 32-Bit-Version von- [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Editionen wird auf Server Core nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="bc44e-194"><sup>[1]</sup>Installing the 32-bit version of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] editions is not supported on Server Core.</span></span>  
  
## <a name="upgrading"></a><span data-ttu-id="bc44e-195">Wird aktualisiert</span><span class="sxs-lookup"><span data-stu-id="bc44e-195">Upgrading</span></span>  
 <span data-ttu-id="bc44e-196">In Server Core-Installationen werden Upgrades von [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] auf [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] unterstützt.</span><span class="sxs-lookup"><span data-stu-id="bc44e-196">On Server Core installations, upgrading from [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] to [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] is supported.</span></span>  
  
## <a name="installation"></a><span data-ttu-id="bc44e-197">Installation</span><span class="sxs-lookup"><span data-stu-id="bc44e-197">Installation</span></span>  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="bc44e-198">unterstützt kein Setup mit dem Installations-Assistenten unter dem Server Core-Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="bc44e-198">does not support setup by using the installation wizard on the Server Core operating system.</span></span> <span data-ttu-id="bc44e-199">Beim Installieren unter Server Core unterstützt [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Setup mithilfe des /Q-Parameters den vollständigen stillen Modus oder mithilfe des /QS-Parameters den einfachen stillen Modus.</span><span class="sxs-lookup"><span data-stu-id="bc44e-199">When installing on Server Core, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup supports full quiet mode by using the /Q parameter, or Quiet Simple mode by using the /QS parameter.</span></span> <span data-ttu-id="bc44e-200">Weitere Informationen finden Sie unter [Installieren von SQL Server 2014 über die Eingabeaufforderung](install-sql-server-from-the-command-prompt.md).</span><span class="sxs-lookup"><span data-stu-id="bc44e-200">For more information, see [Install SQL Server 2014 from the Command Prompt](install-sql-server-from-the-command-prompt.md).</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="bc44e-201">kann nicht parallel mit früheren Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] auf einem Computer installiert werden, auf dem [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] Server Core SP1 oder [!INCLUDE[win8srv](../../includes/win8srv-md.md)] Server Core ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="bc44e-201">cannot be installed side-by-side with earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on a computer that is running [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] Server Core SP1 or [!INCLUDE[win8srv](../../includes/win8srv-md.md)] Server Core.</span></span>  
  
 <span data-ttu-id="bc44e-202">Unabhängig von der Installationsmethode ist es erforderlich, dass Sie den Softwarelizenzbedingungen als Einzelperson oder im Auftrag einer juristischen Person zustimmen, sofern die Verwendung der Software in keiner separaten Vereinbarung geregelt ist, z. B. einem [!INCLUDE[msCoName](../../includes/msconame-md.md)] -Volumenlizenzvertrag oder einem Vertrag eines Drittanbieters mit einem ISV oder OEM.</span><span class="sxs-lookup"><span data-stu-id="bc44e-202">Regardless of the installation method, you are required to confirm acceptance of the software license terms as an individual or on behalf of an entity, unless your use of the software is governed by a separate agreement such as a [!INCLUDE[msCoName](../../includes/msconame-md.md)] volume licensing agreement or a third-party agreement with an ISV or OEM.</span></span>  
  
 <span data-ttu-id="bc44e-203">Die Lizenzbedingungen werden in der Setup-Benutzeroberfläche angezeigt, damit Sie diese lesen und akzeptieren können.</span><span class="sxs-lookup"><span data-stu-id="bc44e-203">The license terms are displayed for review and acceptance in the Setup user interface.</span></span> <span data-ttu-id="bc44e-204">Unbeaufsichtigte Installationen (mit dem /Q-Parameter oder /QS-Parameter) müssen den /IACCEPTSQLSERVERLICENSETERMS-Parameter enthalten.</span><span class="sxs-lookup"><span data-stu-id="bc44e-204">Unattended installations (using the /Q or /QS parameters) must include the /IACCEPTSQLSERVERLICENSETERMS parameter.</span></span> <span data-ttu-id="bc44e-205">Sie können die Lizenzbedingungen unter [Microsoft-Software-Lizenzbedingungen](https://go.microsoft.com/fwlink/?LinkId=148209)in einer separaten Kopie lesen.</span><span class="sxs-lookup"><span data-stu-id="bc44e-205">You can review the license terms separately at [Microsoft Software License Terms](https://go.microsoft.com/fwlink/?LinkId=148209).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bc44e-206">Abhängig davon, wie Sie die Software erworben haben (z. B. durch [!INCLUDE[msCoName](../../includes/msconame-md.md)] -Volumenlizenzierung), unterliegt die Verwendung der Software möglicherweise zusätzlichen Bestimmungen.</span><span class="sxs-lookup"><span data-stu-id="bc44e-206">Depending on how you received the software (for example, through [!INCLUDE[msCoName](../../includes/msconame-md.md)] volume licensing), your use of the software may be subject to additional terms and conditions.</span></span>  
  
 <span data-ttu-id="bc44e-207">Um bestimmte Funktionen zu installieren, verwenden Sie den /FEATURES-Parameter, und geben Sie die übergeordnete Funktion oder die Funktionswerte an.</span><span class="sxs-lookup"><span data-stu-id="bc44e-207">To install specific features, use the /FEATURES parameter and specify the parent feature or feature values.</span></span> <span data-ttu-id="bc44e-208">Weitere Informationen zu Funktionsparametern und ihrer Verwendung finden Sie in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="bc44e-208">For more information about feature parameters and their use, see the following sections.</span></span>  
  
### <a name="feature-parameters"></a><span data-ttu-id="bc44e-209">Funktionsparameter</span><span class="sxs-lookup"><span data-stu-id="bc44e-209">Feature Parameters</span></span>  
  
|<span data-ttu-id="bc44e-210">Funktionsparameter</span><span class="sxs-lookup"><span data-stu-id="bc44e-210">Feature parameter</span></span>|<span data-ttu-id="bc44e-211">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="bc44e-211">Description</span></span>|  
|-----------------------|-----------------|  
|<span data-ttu-id="bc44e-212">SQLENGINE</span><span class="sxs-lookup"><span data-stu-id="bc44e-212">SQLENGINE</span></span>|<span data-ttu-id="bc44e-213">Installiert nur [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bc44e-213">Installs only the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>|  
|<span data-ttu-id="bc44e-214">REPLIKATION</span><span class="sxs-lookup"><span data-stu-id="bc44e-214">REPLICATION</span></span>|<span data-ttu-id="bc44e-215">Installiert die Replikationskomponente und das [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bc44e-215">Installs the Replication component along with [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>|  
|<span data-ttu-id="bc44e-216">FULLTEXT</span><span class="sxs-lookup"><span data-stu-id="bc44e-216">FULLTEXT</span></span>|<span data-ttu-id="bc44e-217">Installiert die FullText-Komponente und das [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bc44e-217">Installs the FullText component along with [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>|  
|<span data-ttu-id="bc44e-218">AS</span><span class="sxs-lookup"><span data-stu-id="bc44e-218">AS</span></span>|<span data-ttu-id="bc44e-219">Installiert alle [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Komponenten.</span><span class="sxs-lookup"><span data-stu-id="bc44e-219">Installs all [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] components.</span></span>|  
|<span data-ttu-id="bc44e-220">IS</span><span class="sxs-lookup"><span data-stu-id="bc44e-220">IS</span></span>|<span data-ttu-id="bc44e-221">Installiert alle [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Komponenten.</span><span class="sxs-lookup"><span data-stu-id="bc44e-221">Installs all [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] components.</span></span>|  
|<span data-ttu-id="bc44e-222">CONN</span><span class="sxs-lookup"><span data-stu-id="bc44e-222">CONN</span></span>|<span data-ttu-id="bc44e-223">Installiert die Konnektivitätskomponenten.</span><span class="sxs-lookup"><span data-stu-id="bc44e-223">Installs the connectivity components.</span></span>|  
  
 <span data-ttu-id="bc44e-224">Vergleichen Sie die folgenden Beispiele für die Verwendung von Funktionsparametern:</span><span class="sxs-lookup"><span data-stu-id="bc44e-224">See the following examples of the usage of feature parameters:</span></span>  
  
|<span data-ttu-id="bc44e-225">Parameter und Werte</span><span class="sxs-lookup"><span data-stu-id="bc44e-225">Parameter and values</span></span>|<span data-ttu-id="bc44e-226">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="bc44e-226">Description</span></span>|  
|--------------------------|-----------------|  
|<span data-ttu-id="bc44e-227">/FEATURES=SQLEngine</span><span class="sxs-lookup"><span data-stu-id="bc44e-227">/FEATURES=SQLEngine</span></span>|<span data-ttu-id="bc44e-228">Installiert nur [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bc44e-228">Installs only the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>|  
|<span data-ttu-id="bc44e-229">/FEATURES=SQLEngine,FullText</span><span class="sxs-lookup"><span data-stu-id="bc44e-229">/FEATURES=SQLEngine,FullText</span></span>|<span data-ttu-id="bc44e-230">Installiert das [!INCLUDE[ssDE](../../includes/ssde-md.md)] und Volltext.</span><span class="sxs-lookup"><span data-stu-id="bc44e-230">Installs the [!INCLUDE[ssDE](../../includes/ssde-md.md)] and full-text.</span></span>|  
|<span data-ttu-id="bc44e-231">/FEATURES=SQLEngine,Conn</span><span class="sxs-lookup"><span data-stu-id="bc44e-231">/FEATURES=SQLEngine,Conn</span></span>|<span data-ttu-id="bc44e-232">Installiert [!INCLUDE[ssDE](../../includes/ssde-md.md)] und die Konnektivitätskomponenten.</span><span class="sxs-lookup"><span data-stu-id="bc44e-232">Installs the [!INCLUDE[ssDE](../../includes/ssde-md.md)] and the connectivity components.</span></span>|  
|<span data-ttu-id="bc44e-233">/FEATURES=SQLEngine,AS,IS,Conn</span><span class="sxs-lookup"><span data-stu-id="bc44e-233">/FEATURES=SQLEngine,AS,IS,Conn</span></span>|<span data-ttu-id="bc44e-234">Installiert [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]und die Konnektivitätskomponenten.</span><span class="sxs-lookup"><span data-stu-id="bc44e-234">Installs the [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], and the connectivity components.</span></span>|  
  
### <a name="installation-options"></a><span data-ttu-id="bc44e-235">Installationsoptionen</span><span class="sxs-lookup"><span data-stu-id="bc44e-235">Installation Options</span></span>  
 <span data-ttu-id="bc44e-236">Beim Installieren von [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] unter einem Server Core-Betriebssystem unterstützt das Setup die folgenden Installationsoptionen:</span><span class="sxs-lookup"><span data-stu-id="bc44e-236">The Setup supports the following installation options while installing [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] on a Server Core operating system:</span></span>  
  
1.  <span data-ttu-id="bc44e-237">**Installation über die Befehlszeile**</span><span class="sxs-lookup"><span data-stu-id="bc44e-237">**Installation from Command Line**</span></span>  
  
     <span data-ttu-id="bc44e-238">Um bestimmte Funktionen über die Befehlszeilen-Installationsoption zu installieren, verwenden Sie den /FEATURES-Parameter und geben die übergeordnete Funktion oder die Funktionswerte an.</span><span class="sxs-lookup"><span data-stu-id="bc44e-238">To install specific features using the command prompt installation option, use the /FEATURES parameter and specify the parent feature or feature values.</span></span> <span data-ttu-id="bc44e-239">Nachfolgend wird gezeigt, wie die Parameter in der Befehlszeile verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="bc44e-239">The following is an example of using the parameters from the command line:</span></span>  
  
    ```cmd
    setup.exe /qs /ACTION=Install /FEATURES=SQLEngine,Replication /INSTANCENAME=MSSQLSERVER /SQLSVCACCOUNT="<DomainName\UserName>" /SQLSVCPASSWORD="<StrongPassword>" /SQLSYSADMINACCOUNTS="<DomainName\UserName>" /AGTSVCACCOUNT="NT AUTHORITY\Network Service" /TCPENABLED=1 /IACCEPTSQLSERVERLICENSETERMS  
    ```  
  
2.  <span data-ttu-id="bc44e-240">**Installation über die Konfigurationsdatei**</span><span class="sxs-lookup"><span data-stu-id="bc44e-240">**Installation using Configuration File**</span></span>  
  
     <span data-ttu-id="bc44e-241">Setup unterstützt die Verwendung der Konfigurationsdatei nur über die Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="bc44e-241">Setup supports the use of the configuration file only through the command prompt.</span></span> <span data-ttu-id="bc44e-242">Die Konfigurationsdatei ist eine Textdatei mit der grundlegenden Struktur eines Parameters (Name/Wert-Paar) und einem beschreibenden Kommentar.</span><span class="sxs-lookup"><span data-stu-id="bc44e-242">The configuration file is a text file with the basic structure of a parameter (name/value pair) and a descriptive comment.</span></span> <span data-ttu-id="bc44e-243">Die an der Eingabeaufforderung angegebene Konfigurationsdatei sollte die Dateinamenerweiterung .INI haben.</span><span class="sxs-lookup"><span data-stu-id="bc44e-243">The configuration file specified at the command prompt should have an .INI file name extension.</span></span> <span data-ttu-id="bc44e-244">Nachfolgend finden Sie einige Beispiele für ConfigurationFile.INI:</span><span class="sxs-lookup"><span data-stu-id="bc44e-244">See the following examples of ConfigurationFile.INI:</span></span>  
  
    -   <span data-ttu-id="bc44e-245">Installieren von [!INCLUDE[ssDE](../../includes/ssde-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc44e-245">Installing [!INCLUDE[ssDE](../../includes/ssde-md.md)]</span></span>  
  
         <span data-ttu-id="bc44e-246">Im folgenden Beispiel wird gezeigt, wie eine neue eigenständige Instanz, die das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssDE](../../includes/ssde-md.md)]einschließt, installiert wird:</span><span class="sxs-lookup"><span data-stu-id="bc44e-246">The following example shows how to install a new stand-alone instance that includes the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssDE](../../includes/ssde-md.md)]:</span></span>  
  
        ```  
        ; ssNoVersion Configuration File  
        [OPTIONS]  
  
        ; Specifies a Setup work flow, like INSTALL, UNINSTALL, or UPGRADE. This is a required parameter.   
  
        ACTION="Install"  
  
        ; Specifies features to install, uninstall, or upgrade. The lists of features include SQLEngine, FullText, Replication, AS, IS, and Conn.   
  
        FEATURES=SQLENGINE  
  
        ; Specify a default or named instance. MSSQLSERVER is the default instance for non-Express editions and SQLExpress for Express editions. This parameter is required when installing the ssNoVersion Database Engine, and Analysis Services (AS).  
  
        INSTANCENAME="MSSQLSERVER"  
  
        ; Specify the Instance ID for the ssNoVersion features you have specified. ssNoVersion directory structure, registry structure, and service names will incorporate the instance ID of the ssNoVersion instance.   
  
        INSTANCEID="MSSQLSERVER"  
  
        ; Account for ssNoVersion service: Domain\User or system account.   
  
        SQLSVCACCOUNT="NT Service\MSSQLSERVER"  
  
        ; Windows account(s) to provision as ssNoVersion system administrators.   
  
        SQLSYSADMINACCOUNTS="<DomainName\UserName>"  
  
        ; Accept the License agreement to continue with Installation  
  
        IAcceptSQLServerLicenseTerms="True"
        ```  
  
    -   <span data-ttu-id="bc44e-247">Installieren von Konnektivitätskomponenten</span><span class="sxs-lookup"><span data-stu-id="bc44e-247">Installing connectivity components</span></span>  
  
         <span data-ttu-id="bc44e-248">Im folgenden Beispiel wird gezeigt, wie die Konnektivitätskomponenten installiert werden:</span><span class="sxs-lookup"><span data-stu-id="bc44e-248">The following example shows how to install the connectivity components:</span></span>  
  
        ```  
        ; ssNoVersion Configuration File  
        [OPTIONS]  
  
        ; Specifies a Setup work flow, like INSTALL, UNINSTALL, or UPGRADE. This is a required parameter.   
  
        ACTION="Install"  
  
        ; Specifies features to install, uninstall, or upgrade. The lists of features include SQLEngine, FullText, Replication, AS, IS, and Conn.   
  
        FEATURES=Conn  
  
        ; Specifies acceptance of License Terms  
  
        IAcceptSQLServerLicenseTerms="True
        ```  
  
    -   <span data-ttu-id="bc44e-249">Installieren aller unterstützten Funktionen</span><span class="sxs-lookup"><span data-stu-id="bc44e-249">Installing all supported features</span></span>  
  
         <span data-ttu-id="bc44e-250">Im folgenden Beispiel wird gezeigt, wie alle unterstützten Funktionen von [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] unter Server Core installiert werden:</span><span class="sxs-lookup"><span data-stu-id="bc44e-250">The following example shows how to install all supported features of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] on Server Core:</span></span>  
  
        ```  
        ; ssNoVersion Configuration File  
        [OPTIONS]  
        ; Specifies a Setup work flow, like INSTALL, UNINSTALL, or UPGRADE. This is a required parameter.   
  
        ACTION="Install"  
  
        ; Specifies features to install, uninstall, or upgrade. The lists of features include SQLEngine, FullText, Replication, AS, IS, and Conn.   
  
        FEATURES=SQLENGINE,FullText,Replication,AS,IS,Conn  
  
        ; Specify a default or named instance. MSSQLSERVER is the default instance for non-Express editions and SQLExpress for Express editions. This parameter is required when installing the ssNoVersion Database Engine (SQL), or Analysis Services (AS).  
  
        INSTANCENAME="MSSQLSERVER"  
  
        ; Specify the Instance ID for the ssNoVersion features you have specified. ssNoVersion directory structure, registry structure, and service names will incorporate the instance ID of the ssNoVersion instance.   
  
        INSTANCEID="MSSQLSERVER"  
  
        ; Account for ssNoVersion service: Domain\User or system account.   
  
        SQLSVCACCOUNT="NT Service\MSSQLSERVER"  
  
        ; Windows account(s) to provision as ssNoVersion system administrators.   
  
        SQLSYSADMINACCOUNTS="<DomainName\UserName>"  
  
        ; The name of the account that the Analysis Services service runs under.   
  
        ASSVCACCOUNT= "NT Service\MSSQLServerOLAPService"  
  
        ; Specifies the list of administrator accounts that need to be provisioned.   
  
        ASSYSADMINACCOUNTS="<DomainName\UserName>"  
  
        ; Specifies the server mode of the Analysis Services instance. Valid values are MULTIDIMENSIONAL, POWERPIVOT or TABULAR. ASSERVERMODE is case-sensitive. All values must be expressed in upper case.   
  
        ASSERVERMODE="MULTIDIMENSIONAL"  
  
        ; Optional value, which specifies the state of the TCP protocol for the ssNoVersion service. Supported values are: 0 to disable the TCP protocol, and 1 to enable the TCP protocol.  
  
        TCPENABLED=1  
  
        ;Specifies acceptance of License Terms  
  
        IAcceptSQLServerLicenseTerms="True"  
        ```  
  
     <span data-ttu-id="bc44e-251">Die folgenden Beispiele zeigen, wie Sie das Setup mithilfe einer Konfigurationsdatei starten können.</span><span class="sxs-lookup"><span data-stu-id="bc44e-251">The following examples show how you can launch the Setup using a configuration file.</span></span>  
  
    -   <span data-ttu-id="bc44e-252">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="bc44e-252">Configuration file</span></span>  
  
         <span data-ttu-id="bc44e-253">Im Folgenden finden Sie einige Beispiele für das Verwenden der Konfigurationsdatei:</span><span class="sxs-lookup"><span data-stu-id="bc44e-253">Following are some examples of how to use the configuration file:</span></span>  
  
        -   <span data-ttu-id="bc44e-254">Angeben der Konfigurationsdatei an der Eingabeaufforderung:</span><span class="sxs-lookup"><span data-stu-id="bc44e-254">To specify the configuration file at the command prompt:</span></span>  
  
        ```cmd
        setup.exe /QS /ConfigurationFile=MyConfigurationFile.INI  
        ```  
  
        -   <span data-ttu-id="bc44e-255">Angeben von Kennwörtern an der Eingabeaufforderung und nicht in der Konfigurationsdatei:</span><span class="sxs-lookup"><span data-stu-id="bc44e-255">To specify passwords at the command prompt instead of in the configuration file:</span></span>  
  
        ```cmd
        setup.exe /QS /SQLSVCPASSWORD="************" /ASSVCPASSWORD="************"  /ConfigurationFile=MyConfigurationFile.INI  
        ```  
  
    -   <span data-ttu-id="bc44e-256">DefaultSetup.ini</span><span class="sxs-lookup"><span data-stu-id="bc44e-256">DefaultSetup.ini</span></span>  
  
         <span data-ttu-id="bc44e-257">Wenn sich die Datei „DefaultSetup.ini“ in den Ordnern „\x86“ und „\x64“ auf der Stammebene der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Quellmedien befindet, öffnen Sie die Datei „DefaultSetup.ini“, und fügen Sie der Datei den Parameter *Features* hinzu.</span><span class="sxs-lookup"><span data-stu-id="bc44e-257">If you have the DefaultSetup.ini file in the \x86 and \x64 folders at the root level of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] source media, open the DefaultSetup.ini file, and then add the *Features* parameter to the file.</span></span>  
  
         <span data-ttu-id="bc44e-258">Wenn die Datei DefaultSetup.ini nicht vorhanden ist, können Sie sie erstellen und sie in die Ordner \x86 und \x64 auf der Stammebene der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Quellmedien kopieren.</span><span class="sxs-lookup"><span data-stu-id="bc44e-258">If the DefaultSetup.ini file does not exist, you can create it and copy it to the \x86 and \x64 folders at the root level of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] source media.</span></span>  
  
## <a name="configuring-remote-access-of-ssnoversion-running-on-server-core"></a><span data-ttu-id="bc44e-259">Konfigurieren von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Remotezugriff bei einer Server Core-Installation</span><span class="sxs-lookup"><span data-stu-id="bc44e-259">Configuring Remote Access of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Running on Server Core</span></span>  
 <span data-ttu-id="bc44e-260">Führen Sie die unten beschriebenen Aktionen aus, um den Remotezugriff auf eine [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] -Instanz zu konfigurieren, die auf einer Server Core-Installation von [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 oder [!INCLUDE[win8srv](../../includes/win8srv-md.md)]ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="bc44e-260">Perform the actions described below to configure remote access of a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] instance that is running on a Server Core installation of [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 or [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span></span>  
  
### <a name="enable-remote-connections-on-the-instance-of-ssnoversion"></a><span data-ttu-id="bc44e-261">Aktivieren von Remoteverbindungen auf der Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc44e-261">Enable remote connections on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
 <span data-ttu-id="bc44e-262">Um Remoteverbindungen zu aktivieren, verwenden Sie SQLCMD.exe lokal, und führen Sie die folgenden Anweisungen für die Server Core-Instanz aus:</span><span class="sxs-lookup"><span data-stu-id="bc44e-262">To enable remote connections, use SQLCMD.exe locally and execute the following statements against the Server Core instance:</span></span>  
  
-   `EXEC sys.sp_configure N'remote access', N'1'`  
  
     `GO`  
  
-   `RECONFIGURE WITH OVERRIDE`  
  
     `GO`  
  
### <a name="enable-and-start-the-ssnoversion-browser-service"></a><span data-ttu-id="bc44e-263">Aktivieren und Starten des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Browserdiensts</span><span class="sxs-lookup"><span data-stu-id="bc44e-263">Enable and start the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service</span></span>  
 <span data-ttu-id="bc44e-264">Standardmäßig ist der Browserdienst deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="bc44e-264">By default, the Browser service is disabled.</span></span>  <span data-ttu-id="bc44e-265">Wenn er auf einer auf Server Core ausgeführten Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] deaktiviert ist, führen Sie den folgenden Befehl von der Befehlszeile aus, um ihn zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="bc44e-265">If it is disabled on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running on Server Core, run the following command from the command prompt to enable it:</span></span>  
  
 `sc config SQLBROWSER start= auto`  
  
 <span data-ttu-id="bc44e-266">Nachdem er aktiviert wurde, führen Sie den folgenden Befehl von der Befehlszeile aus, um den Dienst zu starten:</span><span class="sxs-lookup"><span data-stu-id="bc44e-266">After it is enabled, run the following command from the command prompt to start the service:</span></span>  
  
 `net start SQLBROWSER`  
  
### <a name="create-exceptions-in-windows-firewall"></a><span data-ttu-id="bc44e-267">Erstellen von Ausnahmen von Windows-Firewall</span><span class="sxs-lookup"><span data-stu-id="bc44e-267">Create exceptions in Windows Firewall</span></span>  
 <span data-ttu-id="bc44e-268">Um Ausnahmen für den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Zugriff in der Windows-Firewall zu erstellen, führen Sie die in [Konfigurieren der Windows-Firewall für den SQL Server-Zugriff](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md)angegebenen Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="bc44e-268">To create exceptions for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] access in Windows Firewall, follow the steps specified in [Configure the Windows Firewall to Allow SQL Server Access](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md).</span></span>  
  
### <a name="enable-tcpip-on-the-instance-of-ssnoversion"></a><span data-ttu-id="bc44e-269">Aktivieren von TCP/IP auf der Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc44e-269">Enable TCP/IP on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
 <span data-ttu-id="bc44e-270">Das TCP/IP-Protokoll kann durch Windows PowerShell für eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz auf Server Core aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="bc44e-270">The TCP/IP protocol can be enabled through Windows PowerShell for an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on Server Core.</span></span> <span data-ttu-id="bc44e-271">Folgen Sie diesen Schritten:</span><span class="sxs-lookup"><span data-stu-id="bc44e-271">Follow these steps:</span></span>  
  
1.  <span data-ttu-id="bc44e-272">Starten Sie den Task-Manager auf dem Computer, auf dem [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] Server Core SP1 oder [!INCLUDE[win8srv](../../includes/win8srv-md.md)] Server Core ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="bc44e-272">On the computer that is running [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] Server Core SP1 or [!INCLUDE[win8srv](../../includes/win8srv-md.md)] Server Core, launch Task Manager.</span></span>  
  
2.  <span data-ttu-id="bc44e-273">Klicken Sie auf der Registerkarte **Anwendungen** auf **Neuer Task**.</span><span class="sxs-lookup"><span data-stu-id="bc44e-273">On the **Applications** tab, click **New Task**.</span></span>  
  
3.  <span data-ttu-id="bc44e-274">Geben Sie im Dialogfeld **Neuen Task erstellen** in das Feld **Öffnen** den Wert **sqlps.exe** ein, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="bc44e-274">In the **Create New Task** dialog box, type **sqlps.exe** in the **Open** field and then click **OK**.</span></span> <span data-ttu-id="bc44e-275">Dadurch wird das \*\* [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell\*\* -Fenster geöffnet.</span><span class="sxs-lookup"><span data-stu-id="bc44e-275">This opens the **[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Powershell** window.</span></span>  
  
4.  <span data-ttu-id="bc44e-276">Führen Sie im Fenster **Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell** das folgende Skript aus, um das TCP/IP-Protokoll zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="bc44e-276">In the **Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Powershell** window, run the following script to enable the TCP/IP protocol:</span></span>  
  
```powershell
$smo = 'Microsoft.SqlServer.Management.Smo.'  
$wmi = New-Object ($smo + 'Wmi.ManagedComputer')  
# Enable the TCP protocol on the default instance.  If the instance is named, replace MSSQLSERVER with the instance name in the following line.  
$uri = "ManagedComputer[@Name='" + (get-item env:\computername).Value + "']/ServerInstance[@Name='MSSQLSERVER']/ServerProtocol[@Name='Tcp']"  
$Tcp = $wmi.GetSmoObject($uri)  
$Tcp.IsEnabled = $true  
$Tcp.Alter()  
$Tcp  
```  
  
## <a name="uninstallation"></a><span data-ttu-id="bc44e-277">Deinstallation</span><span class="sxs-lookup"><span data-stu-id="bc44e-277">Uninstallation</span></span>  
 <span data-ttu-id="bc44e-278">Nachdem Sie sich an einem Computer angemeldet haben, auf dem [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] Server Core SP1 oder [!INCLUDE[win8srv](../../includes/win8srv-md.md)] Server Core ausgeführt wird, haben Sie eine beschränkte Desktopumgebung mit einer Administratoreingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="bc44e-278">After you log on to a computer that is running [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] Server Core SP1 or [!INCLUDE[win8srv](../../includes/win8srv-md.md)] Server Core, you have a limited desktop environment with an Administrator command prompt.</span></span> <span data-ttu-id="bc44e-279">Sie können die Deinstallation einer Instanz von [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]mithilfe dieser Eingabeaufforderung initiieren.</span><span class="sxs-lookup"><span data-stu-id="bc44e-279">You can use this command prompt to initiate uninstallation of an instance of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="bc44e-280">Um eine Instanz von [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]zu deinstallieren, starten Sie die Deinstallation im vollständigen stillen Modus mit dem /Q-Parameter oder im stillen einfachen Modus mit dem /QS-Parameter von der Eingabeaufforderung aus.</span><span class="sxs-lookup"><span data-stu-id="bc44e-280">To uninstall an instance of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], launch the uninstallation from the command prompt in full quiet mode by using the /Q parameter, or quiet simple mode by using the /QS parameter.</span></span> <span data-ttu-id="bc44e-281">Der /QS-Parameter zeigt den Status durch die Benutzeroberfläche an, akzeptiert jedoch keine Eingabe.</span><span class="sxs-lookup"><span data-stu-id="bc44e-281">The /QS parameter shows progress through the UI, but does not accept any input.</span></span> <span data-ttu-id="bc44e-282">/Q gibt an, dass Setup ohne Benutzeroberfläche in einem stillen Modus ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="bc44e-282">/Q runs in a quiet mode without any user interface.</span></span>  
  
 <span data-ttu-id="bc44e-283">So deinstallieren Sie eine vorhandene Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="bc44e-283">To uninstall an existing instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
```cmd
setup.exe /Q /Action=Uninstall /FEATURES=SQLEngine,AS,IS /INSTANCENAME=MSSQLSERVER  
```  
  
 <span data-ttu-id="bc44e-284">Um eine benannte Instanz zu entfernen, geben Sie den Namen der Instanz an und nicht wie im vorhergehenden Beispiel "MSSQLSERVER".</span><span class="sxs-lookup"><span data-stu-id="bc44e-284">To remove a named instance, specify the name of the instance instead of "MSSQLSERVER" in the preceding example.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="bc44e-285">Wenn Sie die Eingabeaufforderung unbeabsichtigt schließen, können Sie eine neue Eingabeaufforderung starten, indem Sie folgende Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="bc44e-285">If you accidentally close the command prompt, you can start a new command prompt by following these steps:</span></span>  
> 
>  1.  <span data-ttu-id="bc44e-286">Drücken Sie STRG+UMSCHALT+ESC, um Task-Manager anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="bc44e-286">Press Ctrl+Shift+Esc to display Task Manager.</span></span>  
> 2.  <span data-ttu-id="bc44e-287">Klicken Sie auf der Registerkarte **Anwendungen** auf **Neuer Task**.</span><span class="sxs-lookup"><span data-stu-id="bc44e-287">On the **Applications** tab, click **New Task**.</span></span>  
> 3.  <span data-ttu-id="bc44e-288">Geben Sie im Dialogfeld **Neuen Task erstellen** im Feld **Öffnen** den Wert **cmd** ein, und [!INCLUDE[clickOK](../../includes/clickok-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bc44e-288">In the **Create New Task** dialog box, type **cmd** in the **Open** field and then [!INCLUDE[clickOK](../../includes/clickok-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc44e-289">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bc44e-289">See Also</span></span>  
 <span data-ttu-id="bc44e-290">[Installieren von SQL Server 2014 mithilfe einer Konfigurationsdatei](install-sql-server-using-a-configuration-file.md) </span><span class="sxs-lookup"><span data-stu-id="bc44e-290">[Install SQL Server 2014 Using a Configuration File](install-sql-server-using-a-configuration-file.md) </span></span>  
 <span data-ttu-id="bc44e-291">[Installieren von SQL Server 2014 von der Eingabeaufforderung](install-sql-server-from-the-command-prompt.md) </span><span class="sxs-lookup"><span data-stu-id="bc44e-291">[Install SQL Server 2014 from the Command Prompt](install-sql-server-from-the-command-prompt.md) </span></span>  
 <span data-ttu-id="bc44e-292">[Von den-Editionen unterstützte Funktionen SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md) </span><span class="sxs-lookup"><span data-stu-id="bc44e-292">[Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md) </span></span>  
 <span data-ttu-id="bc44e-293">[Start Anleitung für die Server Core-Installations Option](https://go.microsoft.com/fwlink/?LinkId=221422) </span><span class="sxs-lookup"><span data-stu-id="bc44e-293">[Server Core Installation Option Getting Started Guide](https://go.microsoft.com/fwlink/?LinkId=221422) </span></span>  
 <span data-ttu-id="bc44e-294">[Konfigurieren einer Server Core-Installation: Übersicht](https://go.microsoft.com/fwlink/?LinkId=221423) </span><span class="sxs-lookup"><span data-stu-id="bc44e-294">[Configuring a Server Core installation: Overview](https://go.microsoft.com/fwlink/?LinkId=221423) </span></span>  
 <span data-ttu-id="bc44e-295">[Failovercluster-Cmdlets in Windows PowerShell, aufgelistet nach Aufgaben Fokus](https://go.microsoft.com/fwlink/?LinkId=221419) </span><span class="sxs-lookup"><span data-stu-id="bc44e-295">[Failover Cluster Cmdlets in Windows PowerShell Listed by Task Focus](https://go.microsoft.com/fwlink/?LinkId=221419) </span></span>  
 [<span data-ttu-id="bc44e-296">Zuordnen von Cluster.exe-Befehlen zu Windows PowerShell-Cmdlets für Failovercluster</span><span class="sxs-lookup"><span data-stu-id="bc44e-296">Mapping Cluster.exe Commands to Windows PowerShell Cmdlets for Failover Clusters</span></span>](https://go.microsoft.com/fwlink/?LinkId=221421)  
