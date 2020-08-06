---
title: Aktivieren verschlüsselter Verbindungen mit dem Datenbank-Engine (SQL Server-Konfigurations-Manager) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- connections [SQL Server], encrypted
- SSL [SQL Server]
- Secure Sockets Layer (SSL)
- encryption [SQL Server], connections
- cryptography [SQL Server], connections
- certificates [SQL Server], installing
- requesting encrypted connections
- installing certificates
- security [SQL Server], encryption
ms.assetid: e1e55519-97ec-4404-81ef-881da3b42006
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e1653df929e3f8bc67158a0685ce07b8ba65de6e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724922"
---
# <a name="enable-encrypted-connections-to-the-database-engine-sql-server-configuration-manager"></a><span data-ttu-id="55493-102">Aktivieren von verschlüsselten Verbindungen zur Datenbank-Engine (SQL Server-Konfigurations-Manager)</span><span class="sxs-lookup"><span data-stu-id="55493-102">Enable Encrypted Connections to the Database Engine (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="55493-103">In diesem Thema wird beschrieben, wie Sie verschlüsselte Verbindungen für eine Instanz von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] durch Angeben eines Zertifikats für die [!INCLUDE[ssDE](../../includes/ssde-md.md)] mithilfe des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Managers aktivieren können.</span><span class="sxs-lookup"><span data-stu-id="55493-103">This topic describes how to enable encrypted connections for an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] by specifying a certificate for the [!INCLUDE[ssDE](../../includes/ssde-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span> <span data-ttu-id="55493-104">Für den Servercomputer muss ein Zertifikat bereitgestellt worden sein, und der Clientcomputer muss so eingerichtet sein, dass er die Stammzertifizierungsstelle des Zertifikats als vertrauenswürdig einstuft.</span><span class="sxs-lookup"><span data-stu-id="55493-104">The server computer must have a certificate provisioned, and the client machine must be set up to trust the certificate's root authority.</span></span> <span data-ttu-id="55493-105">Zertifikate werden bereitgestellt, indem sie mithilfe eines Importvorgangs in Windows installiert werden.</span><span class="sxs-lookup"><span data-stu-id="55493-105">Provisioning is the process of installing a certificate by importing it into Windows.</span></span>  
  
 <span data-ttu-id="55493-106">Das Zertifikat muss für die **Serverauthentifizierung**ausgegeben sein.</span><span class="sxs-lookup"><span data-stu-id="55493-106">The certificate must be issued for **Server Authentication**.</span></span> <span data-ttu-id="55493-107">Der Name des Zertifikats muss der vollqualifizierte Domänenname (FQDN) des Computers sein.</span><span class="sxs-lookup"><span data-stu-id="55493-107">The name of the certificate must be the fully qualified domain name (FQDN) of the computer.</span></span>  
  
 <span data-ttu-id="55493-108">Zertifikate werden lokal für diesen Benutzer auf dem Computer gespeichert.</span><span class="sxs-lookup"><span data-stu-id="55493-108">Certificates are stored locally for the users on the computer.</span></span> <span data-ttu-id="55493-109">Um ein Zertifikat zur Verwendung durch [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]zu installieren, müssen Sie den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Manager unter dem gleichen Benutzerkonto ausführen wie den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Dienst. Nur wenn der Dienst als LocalSystem, NetworkService oder LocalService ausgeführt wird, kann ein administratives Konto verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="55493-109">To install a certificate for use by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you must be running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager under the same user account as the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service unless the service is running as LocalSystem, NetworkService, or LocalService, in which case you may use an administrative account.</span></span>  
  
 <span data-ttu-id="55493-110">Der Client muss in der Lage sein, den Besitzer des vom Server verwendeten Zertifikats zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="55493-110">The client must be able to verify the ownership of the certificate used by the server.</span></span> <span data-ttu-id="55493-111">Wenn der Client über das Zertifikat für öffentliche Schlüssel der Zertifizierungsstelle verfügt, die das Serverzertifikat signiert hat, sind keine weiteren Konfigurationsschritte erforderlich.</span><span class="sxs-lookup"><span data-stu-id="55493-111">If the client has the public key certificate of the certification authority that signed the server certificate, no further configuration is necessary.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="55493-112">Windows enthält die Zertifikate für öffentliche Schlüssel von vielen Zertifizierungsstellen.</span><span class="sxs-lookup"><span data-stu-id="55493-112">Windows includes the public key certificates of many certification authorities.</span></span> <span data-ttu-id="55493-113">Wenn das Serverzertifikat von einer öffentlichen oder privaten Zertifizierungsstelle signiert wurde, für die der Client kein öffentliches Schlüsselzertifikat besitzt, müssen Sie das Zertifikat für öffentliche Schlüssel der Zertifizierungsstelle installieren, die das Serverzertifikat signiert hat.</span><span class="sxs-lookup"><span data-stu-id="55493-113">If the server certificate was signed by a public or private certification authority for which the client does not have the public key certificate, you must install the public key certificate of the certification authority that signed the server certificate.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="55493-114">Wenn Sie die Verschlüsselung bei einem Failovercluster verwenden möchten, müssen Sie das Serverzertifikat mit dem vollqualifizierten DNS-Namen des virtuellen Servers auf allen Knoten im Failovercluster installieren.</span><span class="sxs-lookup"><span data-stu-id="55493-114">To use encryption with a failover cluster, you must install the server certificate with the fully qualified DNS name of the virtual server on all nodes in the failover cluster.</span></span> <span data-ttu-id="55493-115">Wenn Sie z. b. über einen Cluster mit zwei Knoten verfügen, der Knoten mit dem Namen *\<your company>* test1. com und test2. *\<your company>* . com, und Sie verfügen über einen virtuellen Server mit dem Namen virorql. Sie müssen ein Zertifikat für virationql *\<your company>* installieren. com auf beiden Knoten.</span><span class="sxs-lookup"><span data-stu-id="55493-115">For example, if you have a two-node cluster, with nodes named test1.*\<your company>*.com and test2.*\<your company>*.com, and you have a virtual server named virtsql, you need to install a certificate for virtsql.*\<your company>*.com on both nodes.</span></span> <span data-ttu-id="55493-116">Sie können den Wert der Option **ForceEncryption**auf **Yes**.</span><span class="sxs-lookup"><span data-stu-id="55493-116">You can set the value of the **ForceEncryption**option to **Yes**.</span></span>  
  
 <span data-ttu-id="55493-117">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="55493-117">**In This Topic**</span></span>  
  
-   <span data-ttu-id="55493-118">**So aktivieren Sie verschlüsselte Verbindungen**</span><span class="sxs-lookup"><span data-stu-id="55493-118">**To enable encrypted connections:**</span></span>  
  
     [<span data-ttu-id="55493-119">Bereitstellen (Installieren) eines Zertifikats auf dem Server</span><span class="sxs-lookup"><span data-stu-id="55493-119">Provision (install) a certificate on the server</span></span>](#Provision)  
  
     [<span data-ttu-id="55493-120">Exportieren des Serverzertifikats</span><span class="sxs-lookup"><span data-stu-id="55493-120">Export the server certificate</span></span>](#Export)  
  
     [<span data-ttu-id="55493-121">Konfigurieren des Servers zum Annehmen verschlüsselter Verbindungen</span><span class="sxs-lookup"><span data-stu-id="55493-121">Configure the server to accept encrypted connections</span></span>](#ConfigureServerConnections)  
  
     [<span data-ttu-id="55493-122">Konfigurieren des Clients zum Anfordern verschlüsselter Verbindungen</span><span class="sxs-lookup"><span data-stu-id="55493-122">Configure the client to request encrypted connections</span></span>](#ConfigureClientConnections)  
  
     [<span data-ttu-id="55493-123">Verschlüsseln einer Verbindung in SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="55493-123">Encrypt a connection from SQL Server Management Studio</span></span>](#EncryptConnection)  
  
##  <a name="SSMSProcedure"></a>  
  
###  <a name="to-provision-install-a-certificate-on-the-server"></a><a name="Provision"></a> <span data-ttu-id="55493-124">So stellen Sie ein Zertifikat auf dem Server bereit bzw. installieren Sie ein Zertifikat</span><span class="sxs-lookup"><span data-stu-id="55493-124">To provision (install) a certificate on the server</span></span>  
  
1.  <span data-ttu-id="55493-125">Klicken Sie im **Startmenü** auf **Ausführen**, geben Sie im Feld **Öffnen** ein, `MMC` und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="55493-125">On the **Start** menu, click **Run**, and in the **Open** box, type `MMC` and click **OK**.</span></span>  
  
2.  <span data-ttu-id="55493-126">Klicken Sie in der MMC-Konsole im Menü **Datei** auf **Snap-In hinzufügen/entfernen**.</span><span class="sxs-lookup"><span data-stu-id="55493-126">In the MMC console, on the **File** menu, click **Add/Remove Snap-in**.</span></span>  
  
3.  <span data-ttu-id="55493-127">Klicken Sie im Dialogfeld **Snap-In hinzufügen/entfernen** auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="55493-127">In the **Add/Remove Snap-in** dialog box, click **Add**.</span></span>  
  
4.  <span data-ttu-id="55493-128">Klicken Sie im Dialogfeld **Eigenständiges Snap-In hinzufügen** auf **Zertifikate**, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="55493-128">In the **Add Standalone Snap-in** dialog box, click **Certificates**, click **Add**.</span></span>  
  
5.  <span data-ttu-id="55493-129">Klicken Sie im **Dialogfeld Zertifikate-Snap-In** auf **Computerkonto**, und klicken Sie dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="55493-129">In the **Certificates snap-in** dialog box, click **Computer account**, and then click **Finish**.</span></span>  
  
6.  <span data-ttu-id="55493-130">Klicken Sie im Dialogfeld **Eigenständiges Snap-In hinzufügen** auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="55493-130">In the **Add Standalone Snap-in** dialog box, click **Close.**</span></span>  
  
7.  <span data-ttu-id="55493-131">Klicken Sie im Dialogfeld **Snap-In hinzufügen/entfernen** auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="55493-131">In the **Add/Remove Snap-in** dialog box, click **OK**.</span></span>  
  
8.  <span data-ttu-id="55493-132">Erweitern Sie im Dialogfeld **Zertifikate-Snap-In** die Option **Zertifikate**, erweitern Sie **Eigene Zertifikate**, und klicken Sie dann mit der rechten Maustaste auf **Zertifikate**, zeigen Sie auf **Alle Aufgaben**, und klicken Sie anschließend auf **Importieren**.</span><span class="sxs-lookup"><span data-stu-id="55493-132">In the **Certificates** snap-in, expand **Certificates**, expand **Personal**, and then right-click **Certificates**, point to **All Tasks**, and then click **Import**.</span></span>  
  
9. <span data-ttu-id="55493-133">Ergänzen Sie die Angaben im **Zertifikatimport-Assistenten**, um dem Computer ein Zertifikat hinzuzufügen, und schließen Sie dann die MMC-Konsole.</span><span class="sxs-lookup"><span data-stu-id="55493-133">Complete the **Certificate Import Wizard**, to add a certificate to the computer, and close the MMC console.</span></span> <span data-ttu-id="55493-134">Weitere Informationen zum Hinzufügen von Zertifikaten zu einem Computer finden Sie in der Windows-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="55493-134">For more information about adding a certificate to a computer, see your Windows documentation.</span></span>  
  
###  <a name="to-export-the-server-certificate"></a><a name="Export"></a> <span data-ttu-id="55493-135">So exportieren Sie das Serverzertifikat</span><span class="sxs-lookup"><span data-stu-id="55493-135">To export the server certificate</span></span>  
  
1.  <span data-ttu-id="55493-136">Erweitern Sie im **Zertifikate** -Snap-In den Ordner **Zertifikate** / **Eigene Zertifikate** , klicken Sie mit der rechten Maustaste auf das **Zertifikat**, zeigen Sie auf **Alle Tasks**, und klicken Sie dann auf **Exportieren**.</span><span class="sxs-lookup"><span data-stu-id="55493-136">From the **Certificates** snap-in, locate the certificate in the **Certificates** / **Personal** folder, right-click the **Certificate**, point to **All Tasks**, and then click **Export**.</span></span>  
  
2.  <span data-ttu-id="55493-137">Führen Sie den **Zertifikatexport-Assistenten**aus, und speichern Sie die Zertifikatsdatei in einem geeigneten Speicherort.</span><span class="sxs-lookup"><span data-stu-id="55493-137">Complete the **Certificate Export Wizard**, storing the certificate file in a convenient location.</span></span>  
  
###  <a name="to-configure-the-server-to-accept-encrypted-connections"></a><a name="ConfigureServerConnections"></a> <span data-ttu-id="55493-138">So konfigurieren Sie den Server zum Annehmen verschlüsselter Verbindungen</span><span class="sxs-lookup"><span data-stu-id="55493-138">To configure the server to accept encrypted connections</span></span>  
  
1.  <span data-ttu-id="55493-139">Erweitern Sie im **SQL Server-Konfigurations-Manager** den Eintrag **SQL Server-Netzwerkkonfiguration**, klicken Sie mit der rechten Maustaste auf **Protokolle für** _\<server instance>_ , und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="55493-139">In **SQL Server Configuration Manager**, expand **SQL Server Network Configuration**, right-click **Protocols for** _\<server instance>_, and then select**Properties**.</span></span>  
  
2.  <span data-ttu-id="55493-140">Wählen Sie im Dialogfeld **Protokolle für** _\<instance name>_ **Eigenschaften** auf der Registerkarte **Zertifikat** das gewünschte Zertifikat aus der Dropdown-Leiste für das Feld **Zertifikat** aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="55493-140">In the **Protocols for**_\<instance name>_ **Properties** dialog box, on the **Certificate** tab, select the desired certificate from the drop down for the **Certificate** box, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="55493-141">Aktivieren Sie auf der Registerkarte **Flags** im Feld **ForceEncryption** die Option **Ja**, und klicken Sie dann auf **OK** , um das Dialogfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="55493-141">On the **Flags** tab, in the **ForceEncryption** box, select **Yes**, and then click **OK** to close the dialog box.</span></span>  
  
4.  <span data-ttu-id="55493-142">Starten Sie den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Dienst neu.</span><span class="sxs-lookup"><span data-stu-id="55493-142">Restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span>  
  
###  <a name="to-configure-the-client-to-request-encrypted-connections"></a><a name="ConfigureClientConnections"></a> <span data-ttu-id="55493-143">So konfigurieren Sie den Client zum Anfordern verschlüsselter Verbindungen</span><span class="sxs-lookup"><span data-stu-id="55493-143">To configure the client to request encrypted connections</span></span>  
  
1.  <span data-ttu-id="55493-144">Kopieren Sie entweder das Originalzertifikat oder die exportierte Zertifikatsdatei auf den Clientcomputer.</span><span class="sxs-lookup"><span data-stu-id="55493-144">Copy either the original certificate or the exported certificate file to the client computer.</span></span>  
  
2.  <span data-ttu-id="55493-145">Installieren Sie auf dem Clientcomputer mithilfe des **Zertifikate** -Snap-Ins entweder das Stammzertifikat oder die exportierte Zertifikatsdatei.</span><span class="sxs-lookup"><span data-stu-id="55493-145">On the client computer, use the **Certificates** snap-in to install either the root certificate or the exported certificate file.</span></span>  
  
3.  <span data-ttu-id="55493-146">Klicken Sie im Konsolenbereich mit der rechten Maustaste auf **SQL Server Native Client-Konfiguration**, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="55493-146">In the console pane, right-click **SQL Server Native Client Configuration**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="55493-147">Klicken Sie auf der Seite **Flags** im Feld **Protokollverschlüsselung erzwingen** auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="55493-147">On the **Flags** page, in the **Force protocol encryption** box, click **Yes**.</span></span>  
  
###  <a name="to-encrypt-a-connection-from-sql-server-management-studio"></a><a name="EncryptConnection"></a><span data-ttu-id="55493-148">So verschlüsseln Sie eine Verbindung von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="55493-148">To encrypt a connection from SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="55493-149">Klicken Sie auf der Symbolleiste des Objekt-Explorers auf **Verbinden**, und klicken Sie dann auf **Datenbank-Engine**.</span><span class="sxs-lookup"><span data-stu-id="55493-149">On the Object Explorer toolbar, click **Connect**, and then click **Database Engine**.</span></span>  
  
2.  <span data-ttu-id="55493-150">Vervollständigen Sie im Dialogfeld **Verbindung mit Server herstellen** die Verbindungseinstellungen, und klicken Sie dann auf **Optionen**.</span><span class="sxs-lookup"><span data-stu-id="55493-150">In the **Connect to Server** dialog box, complete the connection information, and then click **Options**.</span></span>  
  
3.  <span data-ttu-id="55493-151">Klicken Sie auf der Registerkarte **Verbindungseigenschaften** auf **Verbindung verschlüsseln**.</span><span class="sxs-lookup"><span data-stu-id="55493-151">On the **Connection Properties** tab, click **Encrypt connection**.</span></span>  
  
  
