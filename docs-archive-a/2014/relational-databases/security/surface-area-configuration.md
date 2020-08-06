---
title: Oberflächenkonfiguration | Microsoft Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- reducing attackable surface area
- upgrading SQL Server, security
- surface area configuration [SQL Server]
- surface area configuration [SQL Server], about surface area configuration
- attackable surface area [SQL Server]
- installing SQL Server, security
ms.assetid: f741169c-1453-4ad2-830b-bf2be27d712f
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: ef64fbbeb2b8953ff3816db63572b499d42f012e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697661"
---
# <a name="surface-area-configuration"></a><span data-ttu-id="1f7a5-102">Oberflächenkonfiguration</span><span class="sxs-lookup"><span data-stu-id="1f7a5-102">Surface Area Configuration</span></span>
  <span data-ttu-id="1f7a5-103">Bei neuen Installationen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]sind viele Funktionen in der Standardkonfiguration nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="1f7a5-103">In the default configuration of new installations of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], many features are not enabled.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="1f7a5-104">führt die Installation selektiv durch und startet nur zentrale Dienste und Funktionen, damit möglichst wenige Funktionen eine Angriffsfläche für böswillige Benutzer bieten.</span><span class="sxs-lookup"><span data-stu-id="1f7a5-104">selectively installs and starts only key services and features, to minimize the number of features that can be attacked by a malicious user.</span></span> <span data-ttu-id="1f7a5-105">Zum Zeitpunkt der Installation können diese Standardeinstellungen von einem Systemadministrator geändert werden. Ebenso ist es möglich, Funktionen einer laufenden Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]selektiv zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="1f7a5-105">A system administrator can change these defaults at installation time and also selectively enable or disable features of a running instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="1f7a5-106">Darüber hinaus sind einige Komponenten beim Herstellen einer Verbindung von anderen Computern möglicherweise erst verfügbar, wenn Protokolle konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="1f7a5-106">Additionally, some components may not be available when connecting from other computers until protocols are configured.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1f7a5-107">Im Unterschied zu neuen Installationen werden während eines Upgrades keine bestehenden Dienste oder Funktionen deaktiviert. Es können jedoch nach Abschluss des Upgrades zusätzliche Optionen für die Oberflächenkonfiguration angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="1f7a5-107">Unlike new installations, no existing services or features are turned off during an upgrade, but additional surface area configuration options can be applied after the upgrade is completed.</span></span>  
  
## <a name="protocols-connection-and-startup-options"></a><span data-ttu-id="1f7a5-108">Protokolle, Verbindungs- und Startoptionen</span><span class="sxs-lookup"><span data-stu-id="1f7a5-108">Protocols, Connection, and Startup Options</span></span>  
 <span data-ttu-id="1f7a5-109">Verwenden Sie den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Manager, um Dienste zu starten oder zu beenden, die Startoptionen zu konfigurieren und Protokolle sowie andere Verbindungsoptionen zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="1f7a5-109">Use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager to start and stop services, configure the startup options, and enable protocols and other connection options.</span></span>  
  
#### <a name="to-start-sql-server-configuration-manager"></a><span data-ttu-id="1f7a5-110">So starten Sie den SQL Server-Konfigurations-Manager</span><span class="sxs-lookup"><span data-stu-id="1f7a5-110">To start SQL Server Configuration Manager</span></span>  
  
1.  <span data-ttu-id="1f7a5-111">Zeigen Sie im Menü **Start** auf **Alle Programme**, zeigen Sie auf [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], zeigen Sie auf **Konfigurationstools**, und klicken Sie dann auf **SQL Server-Konfigurations-Manager**.</span><span class="sxs-lookup"><span data-stu-id="1f7a5-111">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
    -   <span data-ttu-id="1f7a5-112">Verwenden Sie den Bereich **SQL Server-Dienste** , um Komponenten zu starten und die automatischen Startoptionen zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="1f7a5-112">Use the **SQL Server Services** area to start components and configure the automatic starting options.</span></span>  
  
    -   <span data-ttu-id="1f7a5-113">Verwenden Sie den Bereich **SQL Server-Netzwerkkonfiguration** , um Verbindungsprotokolle und Verbindungsoptionen wie feste TCP/IP-Ports zu aktivieren oder die Verschlüsselung zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="1f7a5-113">Use the **SQL Server Network Configuration** area to enable connection protocols, and connection options such as fixed TCP/IP ports, or forcing encryption.</span></span>  
  
 <span data-ttu-id="1f7a5-114">Weitere Informationen finden Sie unter [SQL Server Configuration Manager](../sql-server-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="1f7a5-114">For more information, see [SQL Server Configuration Manager](../sql-server-configuration-manager.md).</span></span> <span data-ttu-id="1f7a5-115">Remotekonnektivität kann auch von der richtigen Konfiguration einer Firewall abhängen.</span><span class="sxs-lookup"><span data-stu-id="1f7a5-115">Remote connectivity can also depend upon the correct configuration of a firewall.</span></span> <span data-ttu-id="1f7a5-116">Weitere Informationen finden Sie unter [Konfigurieren der Windows-Firewall für den SQL Server-Zugriff](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md).</span><span class="sxs-lookup"><span data-stu-id="1f7a5-116">For more information, see [Configure the Windows Firewall to Allow SQL Server Access](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md).</span></span>  
  
## <a name="enabling-and-disabling-features"></a><span data-ttu-id="1f7a5-117">Aktivieren und Deaktivieren von Funktionen</span><span class="sxs-lookup"><span data-stu-id="1f7a5-117">Enabling and Disabling Features</span></span>  
 <span data-ttu-id="1f7a5-118">Das Aktivieren und Deaktivieren von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Funktionen kann mit Facets in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="1f7a5-118">Enabling and disabling [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] features can be configured using facets in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
#### <a name="to-configure-surface-area-using-facets"></a><span data-ttu-id="1f7a5-119">So konfigurieren Sie die Oberfläche mit Facets</span><span class="sxs-lookup"><span data-stu-id="1f7a5-119">To configure surface area using facets</span></span>  
  
1.  <span data-ttu-id="1f7a5-120">Stellen Sie in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] eine Verbindung mit einer Komponente von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="1f7a5-120">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] connect to a component of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="1f7a5-121">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf den Server, und klicken Sie dann auf **Facets**.</span><span class="sxs-lookup"><span data-stu-id="1f7a5-121">In Object Explorer, right-click the server, and then click **Facets**.</span></span>  
  
3.  <span data-ttu-id="1f7a5-122">Erweitern Sie im Dialogfeld **Facets anzeigen** die Liste **Facet** , und wählen Sie das entsprechende **Oberflächenkonfigurations-Facet** (**Oberflächenkonfiguration**, **Oberflächenkonfiguration für Analysis Services**oder **Oberflächenkonfiguration für Reporting Services**) aus.</span><span class="sxs-lookup"><span data-stu-id="1f7a5-122">In the **View Facets** dialog box, expand the **Facet** list, and select the appropriate **Surface Area Configuration** facet (**Surface Area Configuration**, **Surface Area Configuration for Analysis Services**, or **Surface Area Configuration for Reporting Services**).</span></span>  
  
4.  <span data-ttu-id="1f7a5-123">Wählen Sie im Bereich **Facet-Eigenschaften** die gewünschten Werte für jede Eigenschaft aus.</span><span class="sxs-lookup"><span data-stu-id="1f7a5-123">In the **Facet properties** area, select the values that you want for each property.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
 <span data-ttu-id="1f7a5-124">Verwenden Sie die richtlinienbasierte Verwaltung, um die Konfiguration eines Facets in regelmäßigen Abständen zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="1f7a5-124">To periodically check the configuration of a facet, use Policy-Based Management.</span></span> <span data-ttu-id="1f7a5-125">Weitere Informationen finden Sie unter [Verwalten von Servern mit der richtlinienbasierten Verwaltung](../policy-based-management/administer-servers-by-using-policy-based-management.md).</span><span class="sxs-lookup"><span data-stu-id="1f7a5-125">For more information about Policy-Based Management, see [Administer Servers by Using Policy-Based Management](../policy-based-management/administer-servers-by-using-policy-based-management.md).</span></span>  
  
 <span data-ttu-id="1f7a5-126">Sie können [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Optionen auch mit der gespeicherten Prozedur `sp_configure` festlegen.</span><span class="sxs-lookup"><span data-stu-id="1f7a5-126">You can also set [!INCLUDE[ssDE](../../includes/ssde-md.md)] options using the `sp_configure` stored procedure.</span></span> <span data-ttu-id="1f7a5-127">Weitere Informationen finden Sie unter [Serverkonfigurationsoptionen &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md)angezeigt oder konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="1f7a5-127">For more information, see [Server Configuration Options &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md).</span></span>  
  
 <span data-ttu-id="1f7a5-128">Verwenden Sie die Eigenschaftseinstellungen in **, um die** EnableIntegrated Security [!INCLUDE[ssRS](../../includes/ssrs.md)]-Eigenschaft von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]zu ändern.</span><span class="sxs-lookup"><span data-stu-id="1f7a5-128">To change the **EnableIntegrated Security** property of [!INCLUDE[ssRS](../../includes/ssrs.md)], use the property settings in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="1f7a5-129">Bearbeiten Sie die Konfigurationsdatei **RSReportServer.config** , um die Eigenschaften **Geplante Ereignisse und Berichtsübermittlung** und **Webdienst und HTTP-Zugriff** zu ändern.</span><span class="sxs-lookup"><span data-stu-id="1f7a5-129">To change the **Schedule events and report delivery** property and the **Web service and HTTP access** property, edit the **RSReportServer.config** configuration file.</span></span>  
  
## <a name="command-prompt-options"></a><span data-ttu-id="1f7a5-130">Befehlszeilenoptionen</span><span class="sxs-lookup"><span data-stu-id="1f7a5-130">Command-prompt Options</span></span>  
 <span data-ttu-id="1f7a5-131">Mit dem PowerShell-Cmdlet **Invoke-PolicyEvaluation** von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] können Sie Oberflächenkonfigurations-Richtlinien aufrufen.</span><span class="sxs-lookup"><span data-stu-id="1f7a5-131">Use the **Invoke-PolicyEvaluation**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell cmdlet to invoke Surface Area Configuration Policies.</span></span> <span data-ttu-id="1f7a5-132">Weitere Informationen finden Sie unter [Verwenden der Datenbank-Engine-Cmdlets](../../database-engine/use-the-database-engine-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="1f7a5-132">For more information, see [Use the Database Engine cmdlets](../../database-engine/use-the-database-engine-cmdlets.md).</span></span>  
  
## <a name="soap-and-service-broker-endpoints"></a><span data-ttu-id="1f7a5-133">SOAP- und Service Broker-Endpunkte</span><span class="sxs-lookup"><span data-stu-id="1f7a5-133">SOAP and Service Broker Endpoints</span></span>  
 <span data-ttu-id="1f7a5-134">Mithilfe der richtlinienbasierte Verwaltung können Sie Endpunkte ausschalten.</span><span class="sxs-lookup"><span data-stu-id="1f7a5-134">To turn endpoints off, use Policy-Based Management.</span></span> <span data-ttu-id="1f7a5-135">Verwenden Sie zum Erstellen und Ändern der Eigenschaften von Endpunkten [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql) und [ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1f7a5-135">To create and alter the properties of endpoints, use [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql) and [ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql).</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="1f7a5-136">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="1f7a5-136">Related Content</span></span>  
 [<span data-ttu-id="1f7a5-137">Sicherheitscenter für SQL Server-Datenbank-Engine und Azure SQL-Datenbank</span><span class="sxs-lookup"><span data-stu-id="1f7a5-137">Security Center for SQL Server Database Engine and Azure SQL Database</span></span>](security-center-for-sql-server-database-engine-and-azure-sql-database.md)  
  
 [<span data-ttu-id="1f7a5-138">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1f7a5-138">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
