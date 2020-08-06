---
title: Claims to Windows Token Service (C2WTS) und Reporting Services | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/25/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- c2wts.exe.config
- SharePoint mode
- C2WTS
- WSS_WPG
ms.assetid: 4d380509-deed-4b4b-a9c1-a9134cc40641
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: cf2e245dfae17556bdb906c134ba0d53898a8631
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617509"
---
# <a name="claims-to-windows-token-service-c2wts-and-reporting-services"></a><span data-ttu-id="dd208-102">Claims to Windows Token Service (C2WTS) und Reporting Services</span><span class="sxs-lookup"><span data-stu-id="dd208-102">Claims to Windows Token Service (C2WTS) and Reporting Services</span></span>
  <span data-ttu-id="dd208-103">Der SharePoint claims to Windows Token Service (c2WTS) ist im [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint-Modus erforderlich, wenn Sie die Windows-Authentifizierung für Datenquellen verwenden möchten, die sich außerhalb der SharePoint-Farm befinden.</span><span class="sxs-lookup"><span data-stu-id="dd208-103">The SharePoint Claims to Windows Token Service (c2WTS) is required with [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode if you want to use windows authentication for Data Sources that are outside the SharePoint farm.</span></span> <span data-ttu-id="dd208-104">Dies gilt auch, wenn der Benutzer über die Windows-Authentifizierung auf die Datenquellen zugreift, weil die Kommunikation zwischen dem Web-Front-End (WFE) und dem gemeinsamen [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]-Dienst immer der forderungsbasierten Authentifizierung unterliegt.</span><span class="sxs-lookup"><span data-stu-id="dd208-104">This is true even if the user accesses the data sources with Windows Authentication because the communication between the web front-end (WFE) and the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] shared service will always be Claims authentication.</span></span>  
  
 <span data-ttu-id="dd208-105">c2WTS wird auch dann benötigt, auch sich die Datenquelle(n) auf demselben Computer wie der gemeinsame Dienst befinden.</span><span class="sxs-lookup"><span data-stu-id="dd208-105">c2WTS is needed even if your data source(s) are on the same computer as the shared service.</span></span> <span data-ttu-id="dd208-106">In diesem Szenario ist jedoch keine eingeschränkte Delegierung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="dd208-106">However in this scenario, constrained delegation is not needed.</span></span>  
  
 <span data-ttu-id="dd208-107">Die von c2WTS erstellten Token funktionieren nur bei der eingeschränkten Delegierung (Einschränkungen für bestimmte Dienste) und bei Verwendung der Konfigurationsoption "Beliebiges Authentifizierungsprotokoll verwenden".</span><span class="sxs-lookup"><span data-stu-id="dd208-107">The tokens created by c2WTS will only work with constrained delegation (constrains to specific services) and the configuration option "using any authentication protocol".</span></span> <span data-ttu-id="dd208-108">Wenn sich die Datenquellen auf demselben Computer wie der gemeinsame Dienst befinden, ist wie oben bereits erwähnt keine eingeschränkte Delegierung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="dd208-108">As noted earlier, if your data sources are on the same computer as the shared service, then constrained delegation is not needed.</span></span>  
  
 <span data-ttu-id="dd208-109">Wenn in der Umgebung die eingeschränkte Kerberos-Delegierung verwendet wird, dann müssen sich der SharePoint Server-Dienst und externe Datenquellen in derselben Windows-Domäne befinden.</span><span class="sxs-lookup"><span data-stu-id="dd208-109">If your environment will use Kerberos constrained delegation, then the SharePoint Server service and external data sources need to reside in the same Windows domain.</span></span> <span data-ttu-id="dd208-110">Jeder Dienst, der auf C2WTS (Claims to Windows Token Service) basiert, muss die **eingeschränkte** Kerberos-Delegierung verwenden, damit C2WTS den Kerberos-Protokollübergang verwenden kann, um Ansprüche (Claims) in Windows-Anmeldeinformationen zu übersetzen.</span><span class="sxs-lookup"><span data-stu-id="dd208-110">Any service that relies on the Claims to Windows token service (c2WTS) must use Kerberos **constrained** delegation to allow c2WTS to use Kerberos protocol transition to translate claims into Windows credentials.</span></span> <span data-ttu-id="dd208-111">Diese Anforderungen gelten für alle gemeinsamen SharePoint-Dienste.</span><span class="sxs-lookup"><span data-stu-id="dd208-111">These requirements are true for all SharePoint Shared Services.</span></span> <span data-ttu-id="dd208-112">Weitere Informationen finden Sie unter [Übersicht über die Kerberos-Authentifizierung für Microsoft SharePoint 2010 https://technet.microsoft.com/library/gg502594.aspx) -Produkte (](https://technet.microsoft.com/library/gg502594.aspx).</span><span class="sxs-lookup"><span data-stu-id="dd208-112">For more information, see [Overview of Kerberos authentication for Microsoft SharePoint 2010 Products  (https://technet.microsoft.com/library/gg502594.aspx)](https://technet.microsoft.com/library/gg502594.aspx).</span></span>  
  
 <span data-ttu-id="dd208-113">Die Prozedur wird in diesem Thema zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="dd208-113">The procedure is summarized in this topic.</span></span>  
  
||  
|-|  
|<span data-ttu-id="dd208-114">**[!INCLUDE[applies](../../includes/applies-md.md)]** SharePoint 2013 &#124; SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="dd208-114">**[!INCLUDE[applies](../../includes/applies-md.md)]**  SharePoint 2013 &#124; SharePoint 2010</span></span>|  
  
## <a name="prerequisites"></a><span data-ttu-id="dd208-115">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="dd208-115">Prerequisites</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dd208-116">Hinweis: Einige der Konfigurationsschritte ändern sich möglicherweise oder funktionieren nicht in bestimmten Farmtopologien.</span><span class="sxs-lookup"><span data-stu-id="dd208-116">Note: Some of the configuration steps may change, or may not work in certain farm topologies.</span></span> <span data-ttu-id="dd208-117">Bei der Installation eines einzelnen Servers werden beispielsweise keine Windows Identity Foundations-c2WTS-Dienste unterstützt, sodass Claims to Windows Token-Delegierungsszenarien innerhalb dieser Farmkonfiguration nicht zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="dd208-117">For instance, a single server install does not support the Windows Identity Foundation c2WTS services so claims to windows token delegation scenarios are not possible with this farm configuration.</span></span>  
  
### <a name="basic-steps-needed-to-configure-c2wts"></a><span data-ttu-id="dd208-118">Grundlegende Schritte für die c2WTS-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="dd208-118">Basic steps needed to configure c2WTS</span></span>  
  
1.  <span data-ttu-id="dd208-119">Konfigurieren Sie das c2WTS-Dienstkonto.</span><span class="sxs-lookup"><span data-stu-id="dd208-119">Configure the c2WTS service account.</span></span> <span data-ttu-id="dd208-120">Fügen Sie das Dienstkonto der lokalen Administratorengruppe auf jedem Anwendungsserver, auf dem c2WTS ausgeführt wird, hinzu.</span><span class="sxs-lookup"><span data-stu-id="dd208-120">Add the service account to the local Administrators group on each application server running c2WTS.</span></span> <span data-ttu-id="dd208-121">Stellen Sie außerdem sicher, dass das Konto über die folgenden lokalen Sicherheitsrichtlinienrechte verfügt:</span><span class="sxs-lookup"><span data-stu-id="dd208-121">In addition, verify that the account has the following local security policy rights:</span></span>  
  
    -   <span data-ttu-id="dd208-122">Einsetzen als Teil des Betriebssystems</span><span class="sxs-lookup"><span data-stu-id="dd208-122">Act as part of the operating system</span></span>  
  
    -   <span data-ttu-id="dd208-123">Annehmen der Identität eines Clients nach der Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="dd208-123">Impersonate a client after authentication</span></span>  
  
    -   <span data-ttu-id="dd208-124">Anmelden als Dienst</span><span class="sxs-lookup"><span data-stu-id="dd208-124">Log on as a service</span></span>  
  
     <span data-ttu-id="dd208-125">Das Konto, das Sie für c2WTS verwenden, muss außerdem für die eingeschränkte Delegierung mit Protokoll Übergang konfiguriert werden. Außerdem benötigt es Berechtigungen zum Delegieren an die Dienste, mit denen es kommunizieren muss (d. h. SQL Server-Engine SQL Server Analysis Services). Zum Konfigurieren der Delegierung können Sie das Snap-in "Active Directory-Benutzer und-Computer" verwenden.</span><span class="sxs-lookup"><span data-stu-id="dd208-125">The account you use for c2WTS also needs to be configured for Constrained Delegation with Protocol Transitioning and needs permissions to delegate to the Services it is required to communicate with (i.e. SQL Server Engine, SQL Server Analysis Services).To configure delegation you can use the Active Directory Users and Computer snap-in.</span></span>  
  
    1.  <span data-ttu-id="dd208-126">Klicken Sie mit der rechten Maustaste auf jedes Dienstkonto, und öffnen Sie das Eigenschaftendialogfeld.</span><span class="sxs-lookup"><span data-stu-id="dd208-126">Right-click each service account and open the properties dialog.</span></span> <span data-ttu-id="dd208-127">Klicken Sie im Dialogfeld auf die Registerkarte **Delegierung** .</span><span class="sxs-lookup"><span data-stu-id="dd208-127">In the dialog click the **Delegation** tab.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="dd208-128">Hinweis: Die Registerkarte Delegierung ist nur sichtbar, wenn dem Objekt ein SPN zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="dd208-128">Note: the delegation tab is only visible if the object has an SPN assigned to it.</span></span> <span data-ttu-id="dd208-129">c2WTS erfordert keinen Dienst Prinzipal Namen (SPN) für das c2WTS-Konto. die Registerkarte " **Delegierung** " ist jedoch nicht sichtbar.</span><span class="sxs-lookup"><span data-stu-id="dd208-129">c2WTS does not require an SPN on the c2WTS Account, however, without an SPN, the **Delegation** tab will not be visible.</span></span> <span data-ttu-id="dd208-130">Eine Alternative zur Konfiguration der eingeschränkten Delegierung ist die Verwendung des Hilfsprogramms **ADSIEdit**.</span><span class="sxs-lookup"><span data-stu-id="dd208-130">An alternative way to configure constrained delegation is to use a utility such as **ADSIEdit**.</span></span>  
  
    2.  <span data-ttu-id="dd208-131">Wesentliche Konfigurationsoptionen auf der Registerkarte "Delegierung":</span><span class="sxs-lookup"><span data-stu-id="dd208-131">Key configuration options on the delegation tab are the following:</span></span>  
  
        -   <span data-ttu-id="dd208-132">Wählen Sie "diesen Benutzer nur bei Delegierungen angegebener Dienste vertrauen" aus.</span><span class="sxs-lookup"><span data-stu-id="dd208-132">Select "Trust this user for delegation to specified services only"</span></span>  
  
        -   <span data-ttu-id="dd208-133">Wählen Sie "beliebiges Authentifizierungsprotokoll verwenden" aus.</span><span class="sxs-lookup"><span data-stu-id="dd208-133">Select "Use any authentication protocol"</span></span>  
  
         <span data-ttu-id="dd208-134">Weitere Informationen finden Sie im Abschnitt "Konfigurieren der eingeschränkten Kerberos-Delegierung für Computer und Dienst Konten" im folgenden Whitepaper: [Konfigurieren der Kerberos-Authentifizierung für SharePoint 2010-und SQL Server 2008 R2-Produkte](https://docs.microsoft.com/archive/blogs/tothesharepoint/white-paper-configuring-kerberos-authentication-for-sharepoint-2010-and-sql-server-2008-r2-products) .</span><span class="sxs-lookup"><span data-stu-id="dd208-134">For more information, see the "configure Kerberos constrained delegation for computers and service accounts" section of the following white paper, [Configuring Kerberos authentication for SharePoint 2010 and SQL Server 2008 R2 products](https://docs.microsoft.com/archive/blogs/tothesharepoint/white-paper-configuring-kerberos-authentication-for-sharepoint-2010-and-sql-server-2008-r2-products)</span></span>  
  
2.  <span data-ttu-id="dd208-135">Konfigurieren von c2WTS ' ' ' Zuweisung ' '</span><span class="sxs-lookup"><span data-stu-id="dd208-135">Configure c2WTS 'AllowedCallers'</span></span>  
  
     <span data-ttu-id="dd208-136">c2WTS erfordert, dass die Identitäten der "Aufrufer" explizit in der Konfigurationsdatei aufgeführt sind, **c2wtshost.exe.config**. c2WTS akzeptiert keine Anforderungen von allen authentifizierten Benutzern im System, es sei denn, dies ist dafür konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="dd208-136">c2WTS requires the 'callers' identities explicitly listed in the configuration file, **c2wtshost.exe.config**. c2WTS does not accept requests from all authenticated users in the system unless it is configured to do so.</span></span> <span data-ttu-id="dd208-137">In diesem Fall entspricht der „Aufrufer“ der WSS_WPG-Windows-Gruppe.</span><span class="sxs-lookup"><span data-stu-id="dd208-137">In this case the 'caller' is the WSS_WPG Windows group.</span></span> <span data-ttu-id="dd208-138">Die Datei c2wtshost.exe.config wird im folgenden Ordner gespeichert:</span><span class="sxs-lookup"><span data-stu-id="dd208-138">The c2wtshost.exe.confi file is saved in the following location:</span></span>  
  
     <span data-ttu-id="dd208-139">**\Programme\Windows Identity Foundation\v3.5\c2wtshost.exe.config**</span><span class="sxs-lookup"><span data-stu-id="dd208-139">**\Program Files\Windows Identity Foundation\v3.5\c2wtshost.exe.config**</span></span>  
  
     <span data-ttu-id="dd208-140">Im folgenden Beispiel wird die Konfigurationsdatei gezeigt:</span><span class="sxs-lookup"><span data-stu-id="dd208-140">The following is an example of the configuration file:</span></span>  
  
    ```  
    <configuration>  
      <windowsTokenService>  
        <!--  
            By default no callers are allowed to use the Windows Identity Foundation Claims To NT Token Service.  
            Add the identities you wish to allow below.  
          -->  
        <allowedCallers>  
          <clear/>  
          <add value="WSS_WPG" />  
        </allowedCallers>  
      </windowsTokenService>  
    </configuration>  
    ```  
  
3.  <span data-ttu-id="dd208-141">Starten Sie den c2WTS-Dienst des Betriebssystems:</span><span class="sxs-lookup"><span data-stu-id="dd208-141">Start the operating system c2WTS service:</span></span>  
  
    1.  <span data-ttu-id="dd208-142">Konfigurieren Sie den Dienst für die Verwendung des Dienstkontos, das Sie im vorangehenden Schritt konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="dd208-142">Configure the service to use the service account you configured in the previous step.</span></span>  
  
    2.  <span data-ttu-id="dd208-143">Ändern Sie den Starttyp in "**automatisch**", und starten Sie den Dienst.</span><span class="sxs-lookup"><span data-stu-id="dd208-143">Change the Startup type to "**Automatic**" and start the service.</span></span>  
  
4.  <span data-ttu-id="dd208-144">Starten Sie den SharePoint-claims to Windows Token Service (claims to Windows Token Service): Starten Sie den Claims to Windows Token Service über die SharePoint-zentral Administration auf der Seite **Dienste auf dem Server verwalten** .</span><span class="sxs-lookup"><span data-stu-id="dd208-144">Start the SharePoint 'Claims to Windows Token Service': Start the Claims to Windows Token Service through SharePoint Central Administration on the **Manage Services on Server** page.</span></span> <span data-ttu-id="dd208-145">Der Dienst sollte auf dem Server gestartet werden, auf dem die Aktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="dd208-145">The service should be started on the server that will be performing the action.</span></span> <span data-ttu-id="dd208-146">Wenn Sie z.B. über einen WFE-Server und einen Anwendungsserver verfügen, auf dem der gemeinsame Dienst von [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] ausgeführt wird, müssen Sie C2WTS nur auf dem Anwendungsserver starten.</span><span class="sxs-lookup"><span data-stu-id="dd208-146">For example if you have a server that is a WFE and another server that is an Application Server that has the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] shared service running, you only need to start c2WTS on the Application Server.</span></span> <span data-ttu-id="dd208-147">c2WTS wird auf dem WFE-Server nicht benötigt.</span><span class="sxs-lookup"><span data-stu-id="dd208-147">c2WTS is not needed on the WFE.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd208-148">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dd208-148">See Also</span></span>  
 <span data-ttu-id="dd208-149">[Übersicht über claims to Windows Token Service (c2WTS) (https://msdn.microsoft.com/library/ee517278.aspx)](https://msdn.microsoft.com/library/ee517278.aspx) </span><span class="sxs-lookup"><span data-stu-id="dd208-149">[Claims to Windows Token Service (c2WTS) Overview (https://msdn.microsoft.com/library/ee517278.aspx)](https://msdn.microsoft.com/library/ee517278.aspx) </span></span>  
 [<span data-ttu-id="dd208-150">Übersicht über die Kerberos-Authentifizierung für Microsoft SharePoint 2010-Produkte (https://technet.microsoft.com/library/gg502594.aspx)</span><span class="sxs-lookup"><span data-stu-id="dd208-150">Overview of Kerberos authentication for Microsoft SharePoint 2010 Products (https://technet.microsoft.com/library/gg502594.aspx)</span></span>](https://technet.microsoft.com/library/gg502594.aspx)  
  
