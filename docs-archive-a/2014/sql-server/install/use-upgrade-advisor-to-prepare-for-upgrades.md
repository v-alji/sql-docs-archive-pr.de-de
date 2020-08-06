---
title: Verwenden von Upgrade Advisor zur Vorbereitung auf Upgrades | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Upgrade Advisor [SQL Server]
- upgrading SQL Server, Upgrade Advisor
- upgrading SQL Server, preparing to upgrade
- SQL Server Upgrade Advisor
- analyzing installations for upgrading [SQL Server]
ms.assetid: d85b0833-ddeb-42e3-9397-97ea60d521b7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: e53d895cb19a172d0810ae9d6c2bda3406732da1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700575"
---
# <a name="use-upgrade-advisor-to-prepare-for-upgrades"></a><span data-ttu-id="79c1c-102">Verwenden von Upgrade Advisor zur Vorbereitung auf Upgrades</span><span class="sxs-lookup"><span data-stu-id="79c1c-102">Use Upgrade Advisor to Prepare for Upgrades</span></span>
  <span data-ttu-id="79c1c-103">Mit dem Upgrade Advisor von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] können Sie Upgrades auf [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] vorbereiten.</span><span class="sxs-lookup"><span data-stu-id="79c1c-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Upgrade Advisor helps you prepare for upgrades to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="79c1c-104">Upgrade Advisor analysiert die installierten Komponenten früherer Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] und generiert einen Bericht mit den Problemen, die entweder vor oder nach dem Upgrade behoben werden müssen.</span><span class="sxs-lookup"><span data-stu-id="79c1c-104">Upgrade Advisor analyzes installed components from earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and then generates a report that identifies issues to fix either before or after you upgrade.</span></span>  
  
## <a name="how-upgrade-advisor-works"></a><span data-ttu-id="79c1c-105">Funktionsweise des Upgrade Advisors</span><span class="sxs-lookup"><span data-stu-id="79c1c-105">How Upgrade Advisor Works</span></span>  
 <span data-ttu-id="79c1c-106">Wenn Sie Upgrade Advisor ausführen, wird die Startseite des Upgrade Advisors angezeigt.</span><span class="sxs-lookup"><span data-stu-id="79c1c-106">When you run Upgrade Advisor, the Upgrade Advisor Home page appears.</span></span> <span data-ttu-id="79c1c-107">Sie können von der Startseite aus die folgenden Tools ausführen:</span><span class="sxs-lookup"><span data-stu-id="79c1c-107">From the Home page, you can run the following tools:</span></span>  
  
-   <span data-ttu-id="79c1c-108">Analyse-Assistent des Upgrade Advisors</span><span class="sxs-lookup"><span data-stu-id="79c1c-108">Upgrade Advisor Analysis Wizard</span></span>  
  
-   <span data-ttu-id="79c1c-109">Berichts-Viewer des Upgrade Advisors</span><span class="sxs-lookup"><span data-stu-id="79c1c-109">Upgrade Advisor Report Viewer</span></span>  
  
-   <span data-ttu-id="79c1c-110">Hilfe zum Upgrade Advisor</span><span class="sxs-lookup"><span data-stu-id="79c1c-110">Upgrade Advisor Help</span></span>  
  
 <span data-ttu-id="79c1c-111">Führen Sie bei der erstmaligen Verwendung des Upgrade Advisors den Analyse-Assistenten des Upgrade Advisors aus, um [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Komponenten zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="79c1c-111">The first time that you use Upgrade Advisor, run the Upgrade Advisor Analysis Wizard to analyze [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components.</span></span> <span data-ttu-id="79c1c-112">Wenn der Assistent die Analyse abgeschlossen hat, können die resultierenden Berichte im Berichts-Viewer des Upgrade Advisors angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="79c1c-112">When the wizard finishes the analysis, view the resulting reports in the Upgrade Advisor Report Viewer.</span></span> <span data-ttu-id="79c1c-113">Jeder Bericht bietet Links zu Informationen in der Hilfe zum Upgrade Advisor, mit denen Sie bekannte Probleme beheben oder ihre Auswirkungen reduzieren können.</span><span class="sxs-lookup"><span data-stu-id="79c1c-113">Each report provides links to information in Upgrade Advisor Help that will help you fix or reduce the effect of the known issues.</span></span>  
  
## <a name="upgrade-advisor-analysis"></a><span data-ttu-id="79c1c-114">Analyse mit dem Upgrade Advisor</span><span class="sxs-lookup"><span data-stu-id="79c1c-114">Upgrade Advisor Analysis</span></span>  
 <span data-ttu-id="79c1c-115">Der Upgrade Advisor analysiert die folgenden Komponenten von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="79c1c-115">Upgrade Advisor analyzes the following [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components:</span></span>  
  
-   [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
-   [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]  
  
-   [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
-   [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]  
  
 <span data-ttu-id="79c1c-116">Bei der Analyse werden die Objekte überprüft, auf die zugegriffen werden kann, z. B. Skripts, gespeicherte Prozeduren, Trigger und Ablaufverfolgungsdateien.</span><span class="sxs-lookup"><span data-stu-id="79c1c-116">The analysis examines objects that can be accessed, such as scripts, stored procedures, triggers, and trace files.</span></span> <span data-ttu-id="79c1c-117">Der Upgrade Advisor kann keine Desktopanwendungen und verschlüsselten gespeicherten Prozeduren analysieren.</span><span class="sxs-lookup"><span data-stu-id="79c1c-117">Upgrade Advisor cannot analyze desktop applications or encrypted stored procedures.</span></span>  
  
 <span data-ttu-id="79c1c-118">Die Ausgabe erfolgt als XML-Bericht.</span><span class="sxs-lookup"><span data-stu-id="79c1c-118">Output is in the form of an XML report.</span></span> <span data-ttu-id="79c1c-119">Zeigen Sie den XML-Bericht mithilfe des Berichts-Viewers des Upgrade Advisors an.</span><span class="sxs-lookup"><span data-stu-id="79c1c-119">View the XML report by using the Upgrade Advisor report viewer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="79c1c-120">Berichte können ein "other upgrade issues"-Element enthalten.</span><span class="sxs-lookup"><span data-stu-id="79c1c-120">Reports might contain an "other upgrade issues" item.</span></span> <span data-ttu-id="79c1c-121">Dieses Element ist mit einer Liste von Problemen verknüpft, die vom Upgrade Advisor nicht erkannt werden, jedoch möglicherweise auf dem Server oder in den Anwendungen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="79c1c-121">This item links to a list of issues that are not detected by Upgrade Advisor, but might exist on your server or in your applications.</span></span> <span data-ttu-id="79c1c-122">Sie müssen die Liste nicht erkennbarer Probleme überprüfen und bestimmen, ob Sie aufgrund der nicht erkennbaren Probleme Änderungen am Server oder an den Anwendungen vornehmen müssen.</span><span class="sxs-lookup"><span data-stu-id="79c1c-122">You should review the list of undetectable issues and determine whether you must change your server or applications because of the undetectable issues.</span></span>  
  
## <a name="how-to-install-and-run-upgrade-advisor"></a><span data-ttu-id="79c1c-123">Installieren und Ausführen des Upgrade Advisors</span><span class="sxs-lookup"><span data-stu-id="79c1c-123">How to Install and Run Upgrade Advisor</span></span>  
 <span data-ttu-id="79c1c-124">Der Speicherort für das Installieren des Upgrade Advisors für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ist abhängig davon, was analysiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="79c1c-124">The location where you install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Upgrade Advisor depends on what you will be analyzing.</span></span> <span data-ttu-id="79c1c-125">Upgrade Advisor unterstützt die Remoteanalyse aller unterstützten Komponenten mit Ausnahme von [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="79c1c-125">Upgrade Advisor supports remote analysis of all supported components except [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="79c1c-126">Wenn Sie keine Instanzen von [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] scannen, können Sie den Upgrade Advisor auf einem beliebigen Computer installieren, der eine Verbindung mit der Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] herstellen kann und die Voraussetzungen des Upgrade Advisors erfüllt.</span><span class="sxs-lookup"><span data-stu-id="79c1c-126">If you are not scanning instances of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you can install Upgrade Advisor on any computer that can connect to your instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and that meets the Upgrade Advisor prerequisites.</span></span> <span data-ttu-id="79c1c-127">Weitere Informationen finden Sie unter [Unterstützte Versions- und Editionsupgrades](../../database-engine/install-windows/supported-version-and-edition-upgrades.md).</span><span class="sxs-lookup"><span data-stu-id="79c1c-127">For more information, see [Supported Version and Edition Upgrades](../../database-engine/install-windows/supported-version-and-edition-upgrades.md).</span></span> <span data-ttu-id="79c1c-128">Wenn Sie Instanzen von [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] scannen, müssen Sie den Upgrade Advisor auf dem Berichtsserver installieren.</span><span class="sxs-lookup"><span data-stu-id="79c1c-128">If you are scanning instances of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you must install Upgrade Advisor on the report server.</span></span>  
  
 <span data-ttu-id="79c1c-129">Der Upgrade Advisor ist in einem Feature Pack verfügbar.</span><span class="sxs-lookup"><span data-stu-id="79c1c-129">Upgrade Advisor is available in a feature pack.</span></span>  
  
 <span data-ttu-id="79c1c-130">Die Voraussetzungen für die Installation und Ausführung von Upgrade Advisor lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="79c1c-130">Prerequisites for installing and running Upgrade Advisor are as follows:</span></span>  
  
-   [!INCLUDE[firstref_longhorn](../../includes/firstref-longhorn-md.md)] <span data-ttu-id="79c1c-131">SP2, Windows 7 SP1 und [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1.</span><span class="sxs-lookup"><span data-stu-id="79c1c-131">SP2, Windows 7 SP1, and [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1.</span></span>  
  
-   <span data-ttu-id="79c1c-132">Windows Installer ab Version 4.5.</span><span class="sxs-lookup"><span data-stu-id="79c1c-132">Windows Installer beginning with version 4.5.</span></span> <span data-ttu-id="79c1c-133">Sie können Windows Installer von der [Windows Installer Website](https://www.microsoft.com/download/details.aspx?id=8483)installieren.</span><span class="sxs-lookup"><span data-stu-id="79c1c-133">You can install Windows Installer from the [Windows Installer Web site](https://www.microsoft.com/download/details.aspx?id=8483).</span></span>  
  
-   <span data-ttu-id="79c1c-134">Microsoft .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="79c1c-134">Microsoft .NET Framework 4.</span></span> <span data-ttu-id="79c1c-135">.NET Framework 4 ist auf dem [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Produkt Medium und auf der [Downloadseite für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=209895)verfügbar.</span><span class="sxs-lookup"><span data-stu-id="79c1c-135">.NET Framework 4 is available on the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] product media, and from the [.NET Framework 4 download page](https://go.microsoft.com/fwlink/?LinkId=209895).</span></span>  
  
    -   <span data-ttu-id="79c1c-136">Um .NET Framework 4 von den [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]-Medien zu installieren, suchen Sie das Stammverzeichnis des Datenträgerlaufwerks.</span><span class="sxs-lookup"><span data-stu-id="79c1c-136">To install the .NET Framework 4 from the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] media, locate the root of the disk drive.</span></span> <span data-ttu-id="79c1c-137">Doppelklicken Sie dann auf den Ordner \redist und auf den Ordner DotNetFrameworks, und führen Sie dotNetFx40_Full_x86_x64.exe aus (für 32-Bit- oder für 64-Bit-Betriebssysteme).</span><span class="sxs-lookup"><span data-stu-id="79c1c-137">Then, double-click the \redist folder, double-click the DotNetFrameworks folder, and run dotNetFx40_Full_x86_x64.exe (for 32-bit operating systems or for 64-bit operating systems).</span></span>  
  
 <span data-ttu-id="79c1c-138">Klicken Sie auf der Downloadseite auf die Schaltfläche zum Herunterladen, um den Upgrade Advisor aus dem Web zu installieren.</span><span class="sxs-lookup"><span data-stu-id="79c1c-138">To install Upgrade Advisor from the Web, click the download button on the download page.</span></span> <span data-ttu-id="79c1c-139">Sie können die Installation sofort ausführen oder die Datei SQLUA.msi speichern, um die Installation später auszuführen.</span><span class="sxs-lookup"><span data-stu-id="79c1c-139">You can then run installation immediately, or save the SQLUA.msi file to run later.</span></span> <span data-ttu-id="79c1c-140">Wenn Sie von der Produkt-CD installieren, führen Sie SQLUA.msi direkt vom Produkt Datenträger aus.</span><span class="sxs-lookup"><span data-stu-id="79c1c-140">If you are installing from the product disc, run SQLUA.msi directly from the product disk.</span></span>  
  
 <span data-ttu-id="79c1c-141">Nachdem Sie den Upgrade Advisor installiert haben, können Sie ihn über das **Startmenü** öffnen:</span><span class="sxs-lookup"><span data-stu-id="79c1c-141">After you install Upgrade Advisor, you can open it from the **Start** menu:</span></span>  
  
-   <span data-ttu-id="79c1c-142">Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme**, zeigen Sie auf [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)] , und klicken Sie dann auf \*\* [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Upgrade Advisor\*\*.</span><span class="sxs-lookup"><span data-stu-id="79c1c-142">Click **Start**, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], and then click **[!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Upgrade Advisor**.</span></span>  
  
 <span data-ttu-id="79c1c-143">Weitere Informationen finden Sie in der Dokumentation im Upgrade Advisor-Download sowie in den Versionshinweisen zu [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="79c1c-143">For more information, see the Upgrade Advisor documentation included in the Upgrade Advisor download and the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Release Notes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79c1c-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="79c1c-144">See Also</span></span>  
 <span data-ttu-id="79c1c-145">[Arbeiten mit mehreren Versionen und Instanzen von SQL Server](../../../2014/sql-server/install/work-with-multiple-versions-and-instances-of-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="79c1c-145">[Work with Multiple Versions and Instances of SQL Server](../../../2014/sql-server/install/work-with-multiple-versions-and-instances-of-sql-server.md) </span></span>  
 <span data-ttu-id="79c1c-146">[Unterstützte Versions- und Editionsupgrades](../../database-engine/install-windows/supported-version-and-edition-upgrades.md) </span><span class="sxs-lookup"><span data-stu-id="79c1c-146">[Supported Version and Edition Upgrades](../../database-engine/install-windows/supported-version-and-edition-upgrades.md) </span></span>  
 [<span data-ttu-id="79c1c-147">Abwärtskompatibilität</span><span class="sxs-lookup"><span data-stu-id="79c1c-147">Backward Compatibility</span></span>](../../../2014/getting-started/backward-compatibility.md)  
  
  
