---
title: Installieren von SQL Server 2014 mithilfe einer Konfigurationsdatei | Microsoft-Dokumentation
ms.custom: ''
ms.date: 01/20/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: a832153a-6775-4bed-83f0-55790766d885
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a2f09ad6253762fe5b525f6c918931f4806c84c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697117"
---
# <a name="install-sql-server-2014-using-a-configuration-file"></a><span data-ttu-id="6c5b1-102">Installieren von SQL Server 2014 mithilfe einer Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="6c5b1-102">Install SQL Server 2014 Using a Configuration File</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="6c5b1-103">-Setup bietet die Möglichkeit, eine Konfigurationsdatei auf der Grundlage von Systemstandards und Laufzeiteingaben zu generieren.</span><span class="sxs-lookup"><span data-stu-id="6c5b1-103">Setup provides the ability to generate a configuration file based upon the system default and run-time inputs.</span></span> <span data-ttu-id="6c5b1-104">Sie können die Konfigurationsdatei verwenden, um [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] im gesamten Unternehmen mit der gleichen Konfiguration bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="6c5b1-104">You can use the configuration file to deploy [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] throughout the enterprise with the same configuration.</span></span> <span data-ttu-id="6c5b1-105">Außerdem können manuelle Installationen über das gesamte Unternehmen hinweg standardisiert werden, indem eine Batchdatei erstellt wird, die Setup.exe startet.</span><span class="sxs-lookup"><span data-stu-id="6c5b1-105">You can also standardize manual installations throughout the enterprise, by creating a batch file that launches Setup.exe.</span></span>  
  
 <span data-ttu-id="6c5b1-106">Setup unterstützt die Verwendung der Konfigurationsdatei nur über die Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="6c5b1-106">Setup supports the use of the configuration file only through the command prompt.</span></span> <span data-ttu-id="6c5b1-107">Die Verarbeitungsreihenfolge der Parameter während der Verwendung der Konfigurationsdatei wird im Folgenden erläutert:</span><span class="sxs-lookup"><span data-stu-id="6c5b1-107">The processing order of the parameters while using the configuration file is outlined below:</span></span>  
  
-   <span data-ttu-id="6c5b1-108">Die Konfigurationsdatei überschreibt die Standards in einem Paket</span><span class="sxs-lookup"><span data-stu-id="6c5b1-108">The configuration file overwrites the defaults in a package</span></span>  
  
-   <span data-ttu-id="6c5b1-109">Befehlszeilenwerte überschreiben die Werte in der Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="6c5b1-109">Command-line values overwrite the values in the configuration file</span></span>  
  
 <span data-ttu-id="6c5b1-110">Die Konfigurationsdatei kann zur Nachverfolgung der Parameter und Werte der einzelnen Installationen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6c5b1-110">The configuration file can be used to track the parameters and values for each installation.</span></span> <span data-ttu-id="6c5b1-111">Aus diesem Grund ist die Konfigurationsdatei hilfreich beim Überprüfen und Überwachen der Installationen.</span><span class="sxs-lookup"><span data-stu-id="6c5b1-111">This makes the configuration file useful for verifying and auditing the installations.</span></span>  
  
## <a name="configuration-file-structure"></a><span data-ttu-id="6c5b1-112">Struktur der Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="6c5b1-112">Configuration File Structure</span></span>  
 <span data-ttu-id="6c5b1-113">Die Datei ConfigurationFile.ini ist eine Textdatei mit Parametern (Name/Wert-Paar) und beschreibenden Kommentaren.</span><span class="sxs-lookup"><span data-stu-id="6c5b1-113">The ConfigurationFile.ini file is a text file with parameters (name/value pair) and descriptive comments.</span></span>  
  
 <span data-ttu-id="6c5b1-114">Im Folgenden finden Sie ein Beispiel für eine ConfigurationFile.ini-Datei:</span><span class="sxs-lookup"><span data-stu-id="6c5b1-114">The following is an example of a ConfigurationFile.ini file:</span></span>  
  
```  
; Microsoft SQL Server Configuration file  
[OPTIONS]  
; Specifies a Setup work flow, like INSTALL, UNINSTALL, or UPGRADE.   
; This is a required parameter.   
ACTION="Install"  
; Specifies features to install, uninstall, or upgrade.   
; The list of top-level features include SQL, AS, RS, IS, and Tools.   
; The SQL feature will install the database engine, replication, and full-text.   
; The Tools feature will install Management Tools, Books online,   
; SQL Server Data Tools, and other shared components.   
FEATURES=SQL,Tools  
```  
  
#### <a name="how-to-generate-a-configuration-file"></a><span data-ttu-id="6c5b1-115">So generieren Sie eine Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="6c5b1-115">How to generate a configuration file</span></span>  
  
1.  <span data-ttu-id="6c5b1-116">Legen Sie das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Installationsmedium ein.</span><span class="sxs-lookup"><span data-stu-id="6c5b1-116">Insert the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation media.</span></span> <span data-ttu-id="6c5b1-117">Doppelklicken Sie im Stammordner auf Setup.exe.</span><span class="sxs-lookup"><span data-stu-id="6c5b1-117">From the root folder, double-click Setup.exe.</span></span> <span data-ttu-id="6c5b1-118">Wenn Sie eine Installation über eine Netzwerkfreigabe vornehmen möchten, suchen Sie den Stammordner in der Freigabe, und doppelklicken Sie auf setup.exe.</span><span class="sxs-lookup"><span data-stu-id="6c5b1-118">To install from a network share, locate the root folder on the share, and then double-click Setup.exe.</span></span>  
  
    > [!NOTE]  
    >  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="6c5b1-119">Express Edition-Setup erstellt nicht automatisch eine Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="6c5b1-119">Express Edition setup does not create a configuration file automatically.</span></span> <span data-ttu-id="6c5b1-120">Der folgende Befehl startet das Setup und erstellt eine Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="6c5b1-120">The following command will start  setup and create a configuration file.</span></span>  
    >   
    >  <span data-ttu-id="6c5b1-121">SETUP.exe /UIMODE=Normal /ACTION=INSTALL</span><span class="sxs-lookup"><span data-stu-id="6c5b1-121">SETUP.exe /UIMODE=Normal /ACTION=INSTALL</span></span>  
  
2.  <span data-ttu-id="6c5b1-122">Folgen Sie dem Assistenten durch die Seite **Installationsbereit** .</span><span class="sxs-lookup"><span data-stu-id="6c5b1-122">Follow the wizard through to the **Ready to Install** page.</span></span> <span data-ttu-id="6c5b1-123">Der Pfad zur Konfigurationsdatei wird auf der Seite **Installationsbereit** im Abschnitt mit dem Konfigurationsdateipfad angegeben.</span><span class="sxs-lookup"><span data-stu-id="6c5b1-123">The path to the configuration file is specified in the **Ready to Install** page in the configuration file path section.</span></span> <span data-ttu-id="6c5b1-124">Weitere Informationen zum Installieren [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] von finden Sie unter [Install SQL Server 2014 from the Installation Wizard &#40;Setup&#41;](install-sql-server-from-the-installation-wizard-setup.md).</span><span class="sxs-lookup"><span data-stu-id="6c5b1-124">For more information about how to install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Install SQL Server 2014 from the Installation Wizard &#40;Setup&#41;](install-sql-server-from-the-installation-wizard-setup.md).</span></span>  
  
3.  <span data-ttu-id="6c5b1-125">Brechen Sie das Setupprogramm ab, ohne dabei die Installation abzuschließen, um die INI-Datei zu generieren.</span><span class="sxs-lookup"><span data-stu-id="6c5b1-125">Cancel the setup without actually completing the installation, to generate the INI file.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6c5b1-126">Die Setupinfrastruktur schreibt alle entsprechenden Parameter für die Aktionen, die ausgeführt wurden, mit Ausnahme vertraulicher Daten wie Kennwörter.</span><span class="sxs-lookup"><span data-stu-id="6c5b1-126">The setup infrastructure writes out all the appropriate parameters for the actions that were run, with the exception of sensitive information such as passwords.</span></span> <span data-ttu-id="6c5b1-127">Der /IAcceptSQLServerLicenseTerms-Parameter wird auch nicht in die Konfigurationsdatei geschrieben und erfordert entweder eine Änderung der Konfigurationsdatei oder die Angabe eines Werts an der Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="6c5b1-127">The /IAcceptSQLServerLicenseTerms parameter is also not written out to the configuration file and requires either a modification of the configuration file or a value to be supplied at the command prompt.</span></span> <span data-ttu-id="6c5b1-128">Weitere Informationen finden Sie unter [Installieren von SQL Server 2014 über die Eingabeaufforderung](install-sql-server-from-the-command-prompt.md).</span><span class="sxs-lookup"><span data-stu-id="6c5b1-128">For more information, see [Install SQL Server 2014 from the Command Prompt](install-sql-server-from-the-command-prompt.md).</span></span> <span data-ttu-id="6c5b1-129">Zusätzlich wird bei booleschen Parametern, bei denen der Wert normalerweise nicht über die Eingabeaufforderung angegeben wird, ein Wert eingefügt.</span><span class="sxs-lookup"><span data-stu-id="6c5b1-129">In addition, a value is included for Boolean parameters where a value is usually not supplied through the command prompt.</span></span>  
  
## <a name="using-the-configuration-file-to-install-ssnoversion"></a><span data-ttu-id="6c5b1-130">Verwenden der Konfigurationsdatei zur Installation von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c5b1-130">Using the Configuration File to Install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
 <span data-ttu-id="6c5b1-131">Sie können die Konfigurationsdatei nur bei Befehlszeileninstallationen verwenden.</span><span class="sxs-lookup"><span data-stu-id="6c5b1-131">You can only use the configuration file on command-line installations.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6c5b1-132">Wenn Sie Änderungen an der Konfigurationsdatei vornehmen müssen, empfiehlt es sich, eine Kopie zu erstellen und mit dieser zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="6c5b1-132">If you need to make changes to the configuration file, we recommend that you make a copy and work with the copy.</span></span>  
  
#### <a name="how-to-use-a-configuration-file-to-install-a-stand-alone-ssnoversion-instance"></a><span data-ttu-id="6c5b1-133">So installieren Sie eine eigenständige [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz mithilfe einer Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="6c5b1-133">How to use a configuration file to install a stand-alone [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance</span></span>  
  
-   <span data-ttu-id="6c5b1-134">Führen Sie die Installation über die Eingabeaufforderung aus, und geben Sie die ConfigurationFile.ini mithilfe des *ConfigurationFile* -Parameters an.</span><span class="sxs-lookup"><span data-stu-id="6c5b1-134">Run the installation through the command prompt and supply the ConfigurationFile.ini using the *ConfigurationFile* parameter.</span></span>  
  
#### <a name="how-to-use-a-configuration-file-to-prepare-and-complete-an-image-of-a-stand-alone-ssnoversion-instance-sysprep"></a><span data-ttu-id="6c5b1-135">So verwenden Sie eine Konfigurationsdatei zum Vorbereiten und Abschließen eines Images einer eigenständigen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz (SysPrep)</span><span class="sxs-lookup"><span data-stu-id="6c5b1-135">How to use a configuration file to prepare and complete an image of a stand-alone [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance (SysPrep)</span></span>  
  
1.  <span data-ttu-id="6c5b1-136">So bereiten Sie eine oder mehrere Instanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vor und konfigurieren sie auf dem gleichen Computer.</span><span class="sxs-lookup"><span data-stu-id="6c5b1-136">To prepare one or more instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and configure them on the same machine.</span></span>  
  
    -   <span data-ttu-id="6c5b1-137">Führen Sie **Vorbereiten eines Images von einer eigenständigen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Instanz** auf der Seite **Erweitert** des Installationscenters aus, und zeichnen Sie die Datei zur Vorbereitung der Imagekonfiguration auf.</span><span class="sxs-lookup"><span data-stu-id="6c5b1-137">Run **Image preparation of a stand-alone instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]** from the **Advanced** page of the Installation Center and capture the prepare image configuration file.</span></span>  
  
    -   <span data-ttu-id="6c5b1-138">Verwenden Sie die gleiche Datei zur Vorbereitung der Imagekonfiguration als Vorlage für weitere Instanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6c5b1-138">Use the same prepare image configuration file as a template to prepare more instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
    -   <span data-ttu-id="6c5b1-139">Führen Sie **Abschließen eines Images von einer vorbereiteten eigenständigen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Instanz** auf der Seite **Erweitert** des Installationscenters aus, um eine vorbereitete Instanz auf dem Computer zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="6c5b1-139">Run **Image completion of a prepared stand-alone instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]** from the **Advanced** page of the Installation Center to configure a prepared instances on the machine.</span></span>  
  
2.  <span data-ttu-id="6c5b1-140">So bereiten Sie ein Image des Betriebssystems, einschließlich einer nicht konfigurierten vorbereiteten Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], mit dem Windows-Tool SysPrep vor.</span><span class="sxs-lookup"><span data-stu-id="6c5b1-140">To prepare an image of the operating system including an unconfigured prepared instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], using Windows SysPrep tool.</span></span>  
  
    -   <span data-ttu-id="6c5b1-141">Führen Sie **Vorbereiten eines Images von einer eigenständigen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Instanz** auf der Seite „Erweitert“ des Installationscenters aus, und zeichnen Sie die Datei zur Vorbereitung der Imagekonfiguration auf.</span><span class="sxs-lookup"><span data-stu-id="6c5b1-141">Run the **Image preparation of a stand-alone instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]** from the Advanced page of the Installation Center and capture the prepare image configuration file.</span></span>  
  
    -   <span data-ttu-id="6c5b1-142">Führen Sie **Abschließen eines Images von einer vorbereiteten eigenständigen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Instanz** auf der Seite **Erweitert** des Installationscenters aus, brechen Sie den Befehl jedoch auf der Seite **Das Image kann jetzt abgeschlossen werden** ab, nachdem Sie die vollständige Konfigurationsdatei aufgezeichnet haben.</span><span class="sxs-lookup"><span data-stu-id="6c5b1-142">Run the **Image completion of a prepared stand-alone instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]** from the **Advanced** page of the Installation Center, but cancel it on the **Ready to Complete** page after capturing the complete configuration file.</span></span>  
  
    -   <span data-ttu-id="6c5b1-143">Die abgeschlossene Imagekonfigurationsdatei kann mit dem Windows-Image zum Automatisieren der Konfiguration der vorbereiteten Instanzen gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="6c5b1-143">The complete image configuration file can be stored with the Windows image for automating the configuration of the prepared instances.</span></span>  
  
#### <a name="how-to-install-a-ssnoversion-failover-cluster-using-the-configuration-file"></a><span data-ttu-id="6c5b1-144">So installieren Sie einen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Failovercluster mithilfe der Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="6c5b1-144">How to install a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster using the configuration file</span></span>  
  
1.  <span data-ttu-id="6c5b1-145">Option für die integrierte Installation (Erstellen Sie auf einem Knoten einen Failovercluster mit einem einzelnen Knoten, und führen Sie für zusätzliche Knoten AddNode auf den Knoten aus):</span><span class="sxs-lookup"><span data-stu-id="6c5b1-145">Integrated Install option (create a single node failover cluster on a node and for additional nodes, run AddNode on them):</span></span>  
  
    -   <span data-ttu-id="6c5b1-146">Führen Sie die Option zum Installieren eines Failoverclusters aus, und zeichnen Sie die Konfigurationsdatei auf, in der alle Installationseinstellungen aufgelistet sind.</span><span class="sxs-lookup"><span data-stu-id="6c5b1-146">Run the "Install a Failover Cluster" option and capture the configuration file that lists all the installation settings.</span></span>  
  
    -   <span data-ttu-id="6c5b1-147">Führen Sie die Installation des Failoverclusters über die Befehlszeile aus, indem Sie den *ConfigurationFile* -Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="6c5b1-147">Run the command-line failover cluster install by supplying the *ConfigurationFile* parameter.</span></span>  
  
    -   <span data-ttu-id="6c5b1-148">Führen Sie für zusätzliche Knoten, die hinzugefügt werden sollen, AddNode aus, um die für den vorhandenen Failovercluster zutreffende Datei ConfigurationFile.ini aufzuzeichnen.</span><span class="sxs-lookup"><span data-stu-id="6c5b1-148">On an additional node to be added, run AddNode to capture the ConfigurationFile.ini file applicable to the existing failover cluster.</span></span>  
  
    -   <span data-ttu-id="6c5b1-149">Führen Sie AddNode an der Befehlszeile für alle zusätzlichen Knoten aus, die Teil des Failoverclusters werden, indem Sie mithilfe des ConfigurationFile-Parameters die gleiche Konfigurationsdatei angeben.</span><span class="sxs-lookup"><span data-stu-id="6c5b1-149">Run the command-line AddNode on all the additional nodes that will join the failover cluster, by supplying the same configuration file using the ConfigurationFile parameter.</span></span>  
  
2.  <span data-ttu-id="6c5b1-150">Option für die erweiterte Installation (Bereiten Sie den Failovercluster für alle Failoverclusterknoten vor, und führen Sie danach für den Knoten, der den freigegebenen Datenträger besitzt, die Option zum Abschließen aus):</span><span class="sxs-lookup"><span data-stu-id="6c5b1-150">Advanced install option (prepare failover cluster on all failover cluster nodes, then, after preparing all the nodes, run complete on the node that owns the shared disk):</span></span>  
  
    -   <span data-ttu-id="6c5b1-151">Führen Sie **Vorbereiten** für einen der Knoten aus, und zeichnen Sie die Datei ConfigurationFile.ini auf.</span><span class="sxs-lookup"><span data-stu-id="6c5b1-151">Run **Prepare** on one of the nodes, and capture the ConfigurationFile.ini file.</span></span>  
  
    -   <span data-ttu-id="6c5b1-152">Geben Sie beim Setupvorgang für alle Knoten, die für den Failovercluster vorbereitet werden, die gleiche ConfigurationFile.ini-Datei an.</span><span class="sxs-lookup"><span data-stu-id="6c5b1-152">Supply the same ConfigurationFile.ini file to Setup on all the nodes that will be prepared for the failover cluster.</span></span>  
  
    -   <span data-ttu-id="6c5b1-153">Nachdem alle Knoten vorbereitet wurden, führen Sie einen vollständigen Failoverclustervorgang für den Knoten aus, der den freigegebenen Datenträger besitzt, und zeichnen Sie die Datei ConfigurationFile.ini auf.</span><span class="sxs-lookup"><span data-stu-id="6c5b1-153">After all the nodes have been prepared, run a complete failover cluster operation on the node that owns the shared disk and capture the ConfigurationFile.ini file.</span></span>  
  
    -   <span data-ttu-id="6c5b1-154">Sie können dann diese ConfigurationFile.ini-Datei angeben, um den Failovercluster abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="6c5b1-154">You can then supply this ConfigurationFile.ini file to complete the failover cluster.</span></span>  
  
#### <a name="how-to-add-or-remove-a-node-to-a-ssnoversion-failover-cluster-using-the-configuration-file"></a><span data-ttu-id="6c5b1-155">So fügen Sie mithilfe der Konfigurationsdatei einen Knoten zu einem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Failovercluster hinzu oder entfernen diesen</span><span class="sxs-lookup"><span data-stu-id="6c5b1-155">How to add or remove a node to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster using the configuration file</span></span>  
  
-   <span data-ttu-id="6c5b1-156">Wenn Sie über eine Konfigurationsdatei verfügen, mit der bereits ein Knoten zu einem Failovercluster hinzugefügt oder daraus entfernt wurde, können Sie diese Datei erneut zum Hinzufügen oder Entfernen zusätzlicher Knoten verwenden.</span><span class="sxs-lookup"><span data-stu-id="6c5b1-156">If you have a configuration file that was previously used to add a node to or remove a node from a failover cluster, you can reuse that same file to add or remove additional nodes.</span></span>  
  
#### <a name="how-to-upgrade-a-ssnoversion-failover-cluster-using-the-configuration-file"></a><span data-ttu-id="6c5b1-157">So aktualisieren Sie einen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Failovercluster mithilfe der Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="6c5b1-157">How to upgrade a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster using the configuration file</span></span>  
  
1.  <span data-ttu-id="6c5b1-158">Führen Sie das Upgrade für den passiven Knoten aus, und zeichnen Sie die Datei ConfigurationFile.ini auf.</span><span class="sxs-lookup"><span data-stu-id="6c5b1-158">Run upgrade on the passive node and capture the ConfigurationFile.ini file.</span></span> <span data-ttu-id="6c5b1-159">Sie können dazu entweder das tatsächliche Upgrade ausführen oder am Ende den Vorgang beenden, ohne das tatsächliche Update auszuführen.</span><span class="sxs-lookup"><span data-stu-id="6c5b1-159">You can do this either by performing the actual upgrade, or exiting at the end without doing the actual upgrade.</span></span>  
  
2.  <span data-ttu-id="6c5b1-160">Geben Sie für alle zusätzlichen Knoten, die aktualisiert werden sollen, die Datei ConfigurationFile.ini an, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="6c5b1-160">On all the additional nodes to be upgraded, supply the ConfigurationFile.ini file to complete the process.</span></span>  
  
## <a name="sample-syntax"></a><span data-ttu-id="6c5b1-161">Beispielsyntax</span><span class="sxs-lookup"><span data-stu-id="6c5b1-161">Sample Syntax</span></span>  
 <span data-ttu-id="6c5b1-162">Im Folgenden finden Sie einige Beispiele für das Verwenden der Konfigurationsdatei:</span><span class="sxs-lookup"><span data-stu-id="6c5b1-162">Following are some examples on how to use the configuration file:</span></span>  
  
-   <span data-ttu-id="6c5b1-163">Angeben der Konfigurationsdatei an der Eingabeaufforderung:</span><span class="sxs-lookup"><span data-stu-id="6c5b1-163">To specify the configuration file at the command prompt:</span></span>  
  
```  
Setup.exe /ConfigurationFile=MyConfigurationFile.INI  
```  
  
-   <span data-ttu-id="6c5b1-164">Angeben von Kennwörtern an der Eingabeaufforderung und nicht in der Konfigurationsdatei:</span><span class="sxs-lookup"><span data-stu-id="6c5b1-164">To specify passwords at the command prompt instead of in the configuration file:</span></span>  
  
```  
Setup.exe /SQLSVCPASSWORD="************" /AGTSVCPASSWORD="************" /ASSVCPASSWORD="************" /ISSVCPASSWORD="************" /RSSVCPASSWORD="************" /ConfigurationFile=MyConfigurationFile.INI  
```  
  
## <a name="see-also"></a><span data-ttu-id="6c5b1-165">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6c5b1-165">See Also</span></span>  
 <span data-ttu-id="6c5b1-166">[Installieren von SQL Server 2014 von der Eingabeaufforderung](install-sql-server-from-the-command-prompt.md) </span><span class="sxs-lookup"><span data-stu-id="6c5b1-166">[Install SQL Server 2014 from the Command Prompt](install-sql-server-from-the-command-prompt.md) </span></span>  
 <span data-ttu-id="6c5b1-167">[SQL Server-Failoverclusterinstallation](../../sql-server/failover-clusters/install/sql-server-failover-cluster-installation.md) </span><span class="sxs-lookup"><span data-stu-id="6c5b1-167">[SQL Server Failover Cluster Installation](../../sql-server/failover-clusters/install/sql-server-failover-cluster-installation.md) </span></span>  
 [<span data-ttu-id="6c5b1-168">Upgraden eines SQL Server-Failoverclusters</span><span class="sxs-lookup"><span data-stu-id="6c5b1-168">Upgrade a SQL Server Failover Cluster</span></span>](../../sql-server/failover-clusters/windows/upgrade-a-sql-server-failover-cluster-instance.md)  
  
  
