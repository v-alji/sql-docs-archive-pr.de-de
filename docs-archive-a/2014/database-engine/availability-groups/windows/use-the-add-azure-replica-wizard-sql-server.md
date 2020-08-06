---
title: Verwenden des Assistenten zum Hinzufügen von Azure-Replikaten (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.addreplicawizard.azurereplica.f1
ms.assetid: b89cc41b-07b4-49f3-82cc-bc42b2e793ae
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8f7ee9e80f0511fe23aebb887b15b5e8b7e9cabf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696061"
---
# <a name="use-the-add-azure-replica-wizard-sql-server"></a><span data-ttu-id="30453-102">Verwenden des Assistenten zum Hinzufügen von Azure-Replikaten (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="30453-102">Use the Add Azure Replica Wizard (SQL Server)</span></span>
  <span data-ttu-id="30453-103">Mithilfe des Assistenten zum Hinzufügen von Azure-Replikaten können Sie eine neue Azure-VM in Hybrid-IT erstellen und als sekundäres Replikat für eine neue oder vorhandene AlwaysOn-Verfügbarkeits Gruppe konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="30453-103">Use the Add Azure Replica Wizard to help you create a new Azure VM in hybrid IT and configure it as a secondary replica for a new or existing AlwaysOn availability group.</span></span>  
  
-   <span data-ttu-id="30453-104">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="30453-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="30453-105">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="30453-105">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="30453-106">Security</span><span class="sxs-lookup"><span data-stu-id="30453-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="30453-107">**Fügen Sie ein Replikat hinzu mit:**  [Assistent zum Hinzufügen von Azure-Replikaten (SQL Server Management Studio)](#SSMSProcedure)</span><span class="sxs-lookup"><span data-stu-id="30453-107">**To add a replica, using:**  [Add Azure Replica Wizard (SQL Server Management Studio)](#SSMSProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="30453-108">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="30453-108">Before You Begin</span></span>  
 <span data-ttu-id="30453-109">Wenn Sie einer Verfügbarkeits Gruppe noch nie ein Verfügbarkeits Replikat hinzugefügt haben, lesen Sie die Abschnitte "Server Instanzen" und "Verfügbarkeits Gruppen und-Replikate" unter [Voraussetzungen, Einschränkungen und Empfehlungen für die AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="30453-109">If you have never added any availability replica to an availability group, see the "Server instances" and "Availability groups and replicas" sections in [Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="30453-110">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="30453-110">Prerequisites</span></span>  
  
-   <span data-ttu-id="30453-111">Sie müssen mit der Serverinstanz verbunden sein, auf der das aktuelle primäre Replikat gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="30453-111">You must be connected to the server instance that hosts the current primary replica.</span></span>  
  
-   <span data-ttu-id="30453-112">Sie benötigen eine hybride IT-Umgebung, in der das lokale Subnetz über ein Site-to-Site-VPN mit Azure verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="30453-112">You must have a hybrid-IT environment where your on-premise subnet has a site-to-site VPN with Azure.</span></span> <span data-ttu-id="30453-113">Weitere Informationen finden Sie unter [Konfigurieren eines Standort-zu-Standort-VPNs im Verwaltungsportal](https://azure.microsoft.com/documentation/articles/vpn-gateway-site-to-site-create).</span><span class="sxs-lookup"><span data-stu-id="30453-113">For more information, see [Configure a Site-to-Site VPN in the Management Portal](https://azure.microsoft.com/documentation/articles/vpn-gateway-site-to-site-create).</span></span>  
  
-   <span data-ttu-id="30453-114">Ihre Verfügbarkeitsgruppe muss lokale Verfügbarkeitsreplikate enthalten.</span><span class="sxs-lookup"><span data-stu-id="30453-114">Your availability group must contain on-premise availability replicas.</span></span>  
  
-   <span data-ttu-id="30453-115">Clients des Verfügbarkeitsgruppenlisteners müssen über Internetverbindungen verfügen, falls sie mit dem Listener verbunden bleiben sollen, wenn für die Verfügbarkeitsgruppe ein Failover auf ein Azure-Replikat ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="30453-115">Clients to the availability group listener must have connectivity to the Internet if they want to maintain connectivity with the listener when the availability group is failed over to an Azure replica.</span></span>  
  
-   <span data-ttu-id="30453-116">**Voraussetzungen für die Verwendung der vollständigen anfänglichen Datensynchronisierung** : Sie müssen eine Netzwerkfreigabe angeben, damit der Assistent Sicherungen erstellen und darauf zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="30453-116">**Prerequisites for using full initial data synchronization** You will need to specify a network share in order for the wizard to create and access backups.</span></span> <span data-ttu-id="30453-117">Für das primäre Replikat kann das zum Starten von [!INCLUDE[ssDE](../../../includes/ssde-md.md)] verwendete Konto über Lese- und Schreibberechtigungen für das Dateisystem in einer Netzwerkfreigabe verfügen.</span><span class="sxs-lookup"><span data-stu-id="30453-117">For the primary replica, the account used to start the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] must have read and write file-system permissions on a network share.</span></span> <span data-ttu-id="30453-118">Bei sekundären Replikaten muss das Konto über eine Leseberechtigung für die Netzwerkfreigabe verfügen.</span><span class="sxs-lookup"><span data-stu-id="30453-118">For secondary replicas, the account must have read permission on the network share.</span></span>  
  
     <span data-ttu-id="30453-119">Wenn Sie nicht den Assistenten für eine vollständige anfängliche Datensynchronisierung verwenden können, müssen Sie die sekundären Datenbanken manuell vorbereiten.</span><span class="sxs-lookup"><span data-stu-id="30453-119">If you are unable to use the wizard to perform full initial data synchronization, you need to prepare your secondary databases manually.</span></span> <span data-ttu-id="30453-120">Dies ist vor oder nach dem Ausführen des Assistenten möglich.</span><span class="sxs-lookup"><span data-stu-id="30453-120">You can do this before or after running the wizard.</span></span> <span data-ttu-id="30453-121">Weitere Informationen finden Sie unter [Manuelles Vorbereiten einer sekundären Datenbank auf eine Verfügbarkeitsgruppe &#40;SQL Server&#41;](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md)erstellt und konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="30453-121">For more information, see [Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="30453-122">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="30453-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="30453-123">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="30453-123">Permissions</span></span>  
 <span data-ttu-id="30453-124">Siehe [Security](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md#Security)</span><span class="sxs-lookup"><span data-stu-id="30453-124">See [Security](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md#Security)</span></span>  
  
##  <a name="using-the-add-azure-replica-wizard-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="30453-125">Verwenden des Assistenten zum Hinzufügen von Azure-Replikaten (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="30453-125">Using the Add Azure Replica Wizard (SQL Server Management Studio)</span></span>  
 <span data-ttu-id="30453-126">Der Assistent zum Hinzufügen von Azure-Replikaten kann auf der Seite [Replikate angeben](specify-replicas-page-new-availability-group-wizard-add-replica-wizard.md)gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="30453-126">The Add Azure Replica Wizard can be launched from the [Specify Replicas Page](specify-replicas-page-new-availability-group-wizard-add-replica-wizard.md).</span></span> <span data-ttu-id="30453-127">Die Seite kann auf zwei Weisen aufgerufen werden:</span><span class="sxs-lookup"><span data-stu-id="30453-127">There are two ways to reach this page:</span></span>  
  
-   [<span data-ttu-id="30453-128">Verwenden des Assistenten für Verfügbarkeitsgruppen &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="30453-128">Use the Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="30453-129">Verwenden des Assistenten zum Hinzufügen von Replikaten zu Verfügbarkeitsgruppen &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="30453-129">Use the Add Replica to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md)  
  
 <span data-ttu-id="30453-130">Nachdem Sie den Assistenten zum Hinzufügen von Azure-Replikaten gestartet haben, führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="30453-130">Once you have launched the Add Azure Replica Wizard, follow the steps below:</span></span>  
  
1.  <span data-ttu-id="30453-131">Laden Sie zunächst ein Verwaltungszertifikat für Ihr Azure-Abonnement herunter.</span><span class="sxs-lookup"><span data-stu-id="30453-131">First, download a management certificate for your Azure subscription.</span></span> <span data-ttu-id="30453-132">Klicken Sie auf **Herunterladen** , um die Anmeldeseite zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="30453-132">Click **Download** to open the sign-in page.</span></span>  
  
2.  <span data-ttu-id="30453-133">Melden Sie sich auf der Anmeldeseite bei Ihrem Azure-Abonnement an.</span><span class="sxs-lookup"><span data-stu-id="30453-133">In the sign-in page, sign in to your Azure subscription.</span></span> <span data-ttu-id="30453-134">Sobald Sie angemeldet sind, installiert der Assistent ein Verwaltungszertifikat auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="30453-134">Once you are signed in, the wizard installs a management certificate onto your local machine.</span></span> <span data-ttu-id="30453-135">Dieses Verwaltungszertifikat wird automatisch geladen, wenn Sie den Assistenten erneut verwenden.</span><span class="sxs-lookup"><span data-stu-id="30453-135">This management certificate is automatically loaded when you use this wizard again.</span></span> <span data-ttu-id="30453-136">Wenn Sie mehrere Verwaltungszertifikate heruntergeladen haben, können Sie auf die Schaltfläche zum Durchsuchen ( **...** ) klicken, um das gewünschte Zertifikat auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="30453-136">If you have downloaded multiple management certificates, you can click the **...** button to select the one you want to use.</span></span>  
  
3.  <span data-ttu-id="30453-137">Stellen Sie als Nächstes eine Verbindung mit dem Abonnement her, indem Sie auf **Verbinden**klicken.</span><span class="sxs-lookup"><span data-stu-id="30453-137">Next, connect to your subscription by clicking **Connect**.</span></span> <span data-ttu-id="30453-138">Sobald die Verbindung hergestellt ist, werden die Dropdownlisten mit den Azure-Parametern, wie **Virtuelles Netzwerk** und **Virtuelles Netzwerk – Subnetz**, aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="30453-138">Once you are connected, the drop-down lists are populated with your Azure parameters, such as **Virtual Network** and **Virtual Network Subnet**.</span></span>  
  
4.  <span data-ttu-id="30453-139">Geben Sie die Einstellungen für die Azure-VM an, die das neue sekundäre Replikat hostet:</span><span class="sxs-lookup"><span data-stu-id="30453-139">Specify the settings for the Azure VM that will host the new secondary replica:</span></span>  
  
     <span data-ttu-id="30453-140">Image</span><span class="sxs-lookup"><span data-stu-id="30453-140">Image</span></span>  
     <span data-ttu-id="30453-141">Der Name des SQL Server-Images, das für die Azure-VM verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="30453-141">The name of the SQL Server image to use for the Azure VM</span></span>  
  
     <span data-ttu-id="30453-142">Größe des virtuellen Computers</span><span class="sxs-lookup"><span data-stu-id="30453-142">VM Size</span></span>  
     <span data-ttu-id="30453-143">Die Größe der Azure-VM.</span><span class="sxs-lookup"><span data-stu-id="30453-143">The size of the Azure VM</span></span>  
  
     <span data-ttu-id="30453-144">VM-Name</span><span class="sxs-lookup"><span data-stu-id="30453-144">VM Name</span></span>  
     <span data-ttu-id="30453-145">Der DNS-Name der Azure-VM.</span><span class="sxs-lookup"><span data-stu-id="30453-145">The DNS name of the Azure VM</span></span>  
  
     <span data-ttu-id="30453-146">VM-Benutzername</span><span class="sxs-lookup"><span data-stu-id="30453-146">VM Username</span></span>  
     <span data-ttu-id="30453-147">Der Benutzername des Standardadministrators für die Azure-VM.</span><span class="sxs-lookup"><span data-stu-id="30453-147">The username of the default administrator for the Azure VM</span></span>  
  
     <span data-ttu-id="30453-148">VM-Administratorkennwort (und Kennwortbestätigung)</span><span class="sxs-lookup"><span data-stu-id="30453-148">VM Administrator Password (and Confirm Password)</span></span>  
     <span data-ttu-id="30453-149">Das Kennwort des Standardadministrators für die Azure-VM.</span><span class="sxs-lookup"><span data-stu-id="30453-149">The password for the default administrator for the Azure VM</span></span>  
  
     <span data-ttu-id="30453-150">Virtual Network</span><span class="sxs-lookup"><span data-stu-id="30453-150">Virtual Network</span></span>  
     <span data-ttu-id="30453-151">Das virtuelle Netzwerk, in das die Azure-VM eingefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="30453-151">The virtual network in which to place the Azure VM</span></span>  
  
     <span data-ttu-id="30453-152">Virtuelles Netzwerk – Subnetz</span><span class="sxs-lookup"><span data-stu-id="30453-152">Virtual Network Subnet</span></span>  
     <span data-ttu-id="30453-153">Das Subnetz des virtuellen Netzwerks, in das die Azure-VM eingefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="30453-153">The virtual network subnet in which to place the Azure VM</span></span>  
  
     <span data-ttu-id="30453-154">Domain</span><span class="sxs-lookup"><span data-stu-id="30453-154">Domain</span></span>  
     <span data-ttu-id="30453-155">Die Active Directory (AD)-Domäne, mit der die Azure-VM verknüpft werden soll.</span><span class="sxs-lookup"><span data-stu-id="30453-155">The Active Directory (AD) domain to join the Azure VM</span></span>  
  
     <span data-ttu-id="30453-156">Domänenbenutzername</span><span class="sxs-lookup"><span data-stu-id="30453-156">Domain Username</span></span>  
     <span data-ttu-id="30453-157">Der AD-Benutzername, über den die Azure-VM mit der Domäne verknüpft wird.</span><span class="sxs-lookup"><span data-stu-id="30453-157">The AD username used to join the Azure VM to the domain</span></span>  
  
     <span data-ttu-id="30453-158">Kennwort</span><span class="sxs-lookup"><span data-stu-id="30453-158">Password</span></span>  
     <span data-ttu-id="30453-159">Das Kennwort, über das die Azure-VM mit der Domäne verknüpft wird.</span><span class="sxs-lookup"><span data-stu-id="30453-159">The password used to join the Azure VM to the domain</span></span>  
  
5.  <span data-ttu-id="30453-160">Klicken Sie auf **OK** , um Ihre Einstellungen zu bestätigen und den Assistenten zum Hinzufügen von Azure-Replikaten zu beenden.</span><span class="sxs-lookup"><span data-stu-id="30453-160">Click **OK** to commit your settings and exit the Add Azure Replica Wizard.</span></span>  
  
6.  <span data-ttu-id="30453-161">Führen Sie die übrigen Konfigurationsschritte auf der Seite [Replikate angeben](specify-replicas-page-new-availability-group-wizard-add-replica-wizard.md) wie für jedes neue Replikat aus.</span><span class="sxs-lookup"><span data-stu-id="30453-161">Continue with the rest of the configuration steps for [Specify Replicas Page](specify-replicas-page-new-availability-group-wizard-add-replica-wizard.md) as you do for any new replica.</span></span>  
  
     <span data-ttu-id="30453-162">Wenn Sie den Assistenten für Verfügbarkeits Gruppen oder den Assistenten zum Hinzufügen von Replikaten zu Verfügbarkeits Gruppen abgeschlossen haben, führt der Konfigurationsprozess alle Vorgänge in Azure aus, um den neuen virtuellen Computer zu erstellen, ihn mit der AD-Domäne zu verknüpfen, ihn dem Windows-Cluster hinzuzufügen, Hochverfügbarkeit von AlwaysOn zu aktivieren und das neue Replikat der Verfügbarkeits</span><span class="sxs-lookup"><span data-stu-id="30453-162">Once you are finished with the Availability Group Wizard or the Add Replica to Availability Group Wizard, the configuration process performs all operations in Azure to create the new VM, join it to the AD domain, add it to the Windows cluster, enable AlwaysOn High Availability, and add the new replica to the availability group.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="30453-163">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="30453-163">Related Tasks</span></span>  
  
-   [<span data-ttu-id="30453-164">Hinzufügen eines sekundären Replikats zu einer Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="30453-164">Add a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](add-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="30453-165">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="30453-165">See Also</span></span>  
 <span data-ttu-id="30453-166">[Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="30453-166">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="30453-167">[Voraussetzungen, Einschränkungen und Empfehlungen für AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="30453-167">[Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md) </span></span>  
 [<span data-ttu-id="30453-168">Hinzufügen eines sekundären Replikats zu einer Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="30453-168">Add a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](add-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
  
