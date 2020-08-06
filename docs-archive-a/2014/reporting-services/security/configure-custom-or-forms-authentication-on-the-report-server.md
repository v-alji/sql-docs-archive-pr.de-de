---
title: Konfigurieren der benutzerdefinierten oder Formularauthentifizierung auf dem Berichtsserver | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Forms authentication, configuring
- custom authentication [Reporting Services]
ms.assetid: e8601a8f-e66d-4649-8e4d-a46ca20ec7d0
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1447e1e695f0e59dbc07b7e19f4df335a1220a97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615265"
---
# <a name="configure-custom-or-forms-authentication-on-the-report-server"></a><span data-ttu-id="b4915-102">Konfiguration der benutzerdefinierten oder Formularauthentifizierung auf dem Berichtsserver</span><span class="sxs-lookup"><span data-stu-id="b4915-102">Configure Custom or Forms Authentication on the Report Server</span></span>
  <span data-ttu-id="b4915-103">Reporting Services stellt eine erweiterbare Architektur zur Verfügung, mit der Sie benutzerdefinierte oder formularbasierte Authentifizierungsmodule integrieren können.</span><span class="sxs-lookup"><span data-stu-id="b4915-103">Reporting Services provides an extensible architecture that allows you to plug in custom or forms-based authentication modules.</span></span> <span data-ttu-id="b4915-104">Möglicherweise ist es ratsam, eine benutzerdefinierte Authentifizierungserweiterung zu implementieren, wenn die Bereitstellungsanforderungen keine Windows-integrierte Sicherheit oder grundlegende Authentifizierung umfassen.</span><span class="sxs-lookup"><span data-stu-id="b4915-104">You might consider implementing a custom authentication extension if deployment requirements do not include Windows integrated security or Basic authentication.</span></span> <span data-ttu-id="b4915-105">Das häufigste Szenario für die Verwendung der benutzerdefinierten Authentifizierung ist eine Unterstützung des Internet- oder Extranetzugriffs auf eine Webanwendung.</span><span class="sxs-lookup"><span data-stu-id="b4915-105">The most common scenario for using custom authentication is to support Internet or extranet access to a Web application.</span></span> <span data-ttu-id="b4915-106">Durch das Ersetzen der standardmäßigen Windows-Authentifizierungserweiterung durch eine benutzerdefinierte Erweiterung können Sie besser steuern, wie externen Benutzern Zugriff auf den Berichtsserver gewährt wird.</span><span class="sxs-lookup"><span data-stu-id="b4915-106">Replacing the default Windows Authentication extension with a custom authentication extension gives you more control over how external users are granted access to the report server.</span></span>  
  
 <span data-ttu-id="b4915-107">In der Praxis erfordert das Bereitstellen einer benutzerdefinierten Authentifizierungserweiterung mehrere Schritte, darunter das Kopieren von Assemblys und Anwendungsdateien, das Bearbeiten von Konfigurationsdateien und das Testen.</span><span class="sxs-lookup"><span data-stu-id="b4915-107">In practice, deploying a custom authentication extension requires multiple steps that include copying assemblies and application files, modifying configuration files, and testing.</span></span> <span data-ttu-id="b4915-108">Dieses Thema konzentriert sich ganz auf die Authentifizierungseinstellungen, die Sie in den Konfigurationsdateien angeben.</span><span class="sxs-lookup"><span data-stu-id="b4915-108">This topic focuses on just the authentication settings that you specify in the configuration files.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b4915-109">Zum Erstellen einer benutzerdefinierten Authentifizierungserweiterung sind benutzerdefinierter Code und Kenntnisse der [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] -Sicherheit erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b4915-109">Creating a custom authentication extension requires custom code and expertise in [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] security.</span></span> <span data-ttu-id="b4915-110">Wenn Sie keine benutzerdefinierte Authentifizierungserweiterung erstellen möchten, können Sie [!INCLUDE[msCoName](../../includes/msconame-md.md)] Active Directory-Gruppen und -Konten verwenden, aber Sie sollten den Rahmen einer Berichtsserverbereitstellung deutlich verringern.</span><span class="sxs-lookup"><span data-stu-id="b4915-110">If you do not want to create a custom authentication extension, you can use [!INCLUDE[msCoName](../../includes/msconame-md.md)] Active Directory groups and accounts, but you should greatly reduce the scope of a report server deployment.</span></span> <span data-ttu-id="b4915-111">Weitere Informationen zur benutzerdefinierten Authentifizierung finden Sie unter [Implementing a Security Extension](../extensions/security-extension/implementing-a-security-extension.md).</span><span class="sxs-lookup"><span data-stu-id="b4915-111">For more information about custom authentication, see [Implementing a Security Extension](../extensions/security-extension/implementing-a-security-extension.md).</span></span>  
  
 <span data-ttu-id="b4915-112">Wenn Sie eine Formular- oder benutzerdefinierte Authentifizierungserweiterung in einer [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Umgebung verwenden möchten, die mit einem SharePoint-Produkt integriert ist, müssen Sie zusätzlich die SharePoint-Website für die Verwendung der von Ihnen gewählten Authentifizierungsmethode konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b4915-112">Additionally, if you want to use Forms authentication or a custom authentication extension in a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] environment that is integrated with a SharePoint product, you must configure the SharePoint site to use the authentication method that you choose.</span></span> <span data-ttu-id="b4915-113">Weitere Informationen über das Konfigurieren der Authentifizierung in SharePoint finden Sie unter [Authentication Samples](https://go.microsoft.com/fwlink/?LinkId=115575) im [!INCLUDE[msCoName](../../includes/msconame-md.md)] Developer Network (MSDN).</span><span class="sxs-lookup"><span data-stu-id="b4915-113">For more information about configuring authentication in SharePoint, see [Authentication Samples](https://go.microsoft.com/fwlink/?LinkId=115575) on [!INCLUDE[msCoName](../../includes/msconame-md.md)] Developer Network (MSDN).</span></span>  
  
### <a name="to-configure-a-report-server-to-use-custom-authentication"></a><span data-ttu-id="b4915-114">So konfigurieren Sie einen Berichtsserver für die Verwendung der benutzerdefinierten Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="b4915-114">To configure a report server to use Custom authentication</span></span>  
  
1.  <span data-ttu-id="b4915-115">Öffnen Sie RSReportServer.config in einem Text-Editor.</span><span class="sxs-lookup"><span data-stu-id="b4915-115">Open RSReportServer.config in a text editor.</span></span>  
  
2.  <span data-ttu-id="b4915-116">Suchen Sie nach <`Authentication`>.</span><span class="sxs-lookup"><span data-stu-id="b4915-116">Find <`Authentication`>.</span></span>  
  
3.  <span data-ttu-id="b4915-117">Kopieren Sie die folgende XML-Struktur:</span><span class="sxs-lookup"><span data-stu-id="b4915-117">Copy the following XML structure:</span></span>  
  
    ```  
    <Authentication>  
          <AuthenticationTypes>  
                 <Custom />  
          </AuthenticationTypes>  
          <EnableAuthPersistence>true</EnableAuthPersistence>  
    </Authentication>  
    ```  
  
4.  <span data-ttu-id="b4915-118">Fügen Sie Sie über die vorhandenen Einträge für <`Authentication`> ein.</span><span class="sxs-lookup"><span data-stu-id="b4915-118">Paste it over the existing entries for <`Authentication`>.</span></span>  
  
     <span data-ttu-id="b4915-119">Beachten Sie, dass Sie `Custom` nicht mit anderen Authentifizierungstypen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="b4915-119">Note that you cannot use `Custom` with other authentication types.</span></span>  
  
5.  <span data-ttu-id="b4915-120">Speichern Sie die Datei .</span><span class="sxs-lookup"><span data-stu-id="b4915-120">Save the file.</span></span>  
  
6.  <span data-ttu-id="b4915-121">Öffnen Sie die Datei Web.config für den Berichtsserver.</span><span class="sxs-lookup"><span data-stu-id="b4915-121">Open the Web.config file for the report server.</span></span> <span data-ttu-id="b4915-122">Standardmäßig befindet sich diese Datei unter "Programme\Microsoft SQL Server\MSRS10_50.MSSQLSERVER\ReportServer".</span><span class="sxs-lookup"><span data-stu-id="b4915-122">By default, it is located at \Program Files\Microsoft SQL Server\MSRS10_50.MSSQLSERVER\ReportServer.</span></span>  
  
7.  <span data-ttu-id="b4915-123">Suchen `authentication mode` und festlegen `Forms` .</span><span class="sxs-lookup"><span data-stu-id="b4915-123">Find `authentication mode` and set it `Forms`.</span></span>  
  
    ```  
    <authentication mode = "Forms" />  
    ```  
  
8.  <span data-ttu-id="b4915-124">Suchen Sie `identity impersonate`, und legen Sie dafür `False` fest.</span><span class="sxs-lookup"><span data-stu-id="b4915-124">Find `identity impersonate` and set it to `False`.</span></span>  
  
    ```  
    <identity impersonate = "false" />  
    ```  
  
9. <span data-ttu-id="b4915-125">Öffnen Sie die Datei Web.config für den Berichts-Manager.</span><span class="sxs-lookup"><span data-stu-id="b4915-125">Open the Web.config file for Report Manager.</span></span> <span data-ttu-id="b4915-126">Standardmäßig befindet sich diese Datei unter \Programme\Microsoft SQL Server\MSRS10_50.MSSQLSERVER\ReportManager.</span><span class="sxs-lookup"><span data-stu-id="b4915-126">By default, it is located at \Program Files\Microsoft SQL Server\MSRS10_50.MSSQLSERVER\ReportManager.</span></span>  
  
10. <span data-ttu-id="b4915-127">Suchen `authentication mode` und festlegen `Forms` .</span><span class="sxs-lookup"><span data-stu-id="b4915-127">Find `authentication mode` and set it `Forms`.</span></span>  
  
    ```  
    <authentication mode = "Forms" />  
    ```  
  
11. <span data-ttu-id="b4915-128">Suchen Sie `identity impersonate`, und legen Sie dafür `False` fest.</span><span class="sxs-lookup"><span data-stu-id="b4915-128">Find `identity impersonate` and set it to `False`.</span></span>  
  
    ```  
    <identity impersonate = "false" />  
    ```  
  
12. <span data-ttu-id="b4915-129">Fügen Sie der Konfigurationsdatei die Elementstruktur `PassThroughCookies` hinzu.</span><span class="sxs-lookup"><span data-stu-id="b4915-129">Add the `PassThroughCookies` element structure to the configuration file.</span></span> <span data-ttu-id="b4915-130">Weitere Informationen finden Sie unter [Konfigurieren des Berichts-Managers für die Übergabe von benutzerdefinierten Authentifizierungscookies](configure-the-web-portal-to-pass-custom-authentication-cookies.md).</span><span class="sxs-lookup"><span data-stu-id="b4915-130">For more information, see [Configure Report Manager to Pass Custom Authentication Cookies](configure-the-web-portal-to-pass-custom-authentication-cookies.md).</span></span>  
  
13. <span data-ttu-id="b4915-131">Speichern Sie die Datei .</span><span class="sxs-lookup"><span data-stu-id="b4915-131">Save the file.</span></span>  
  
14. <span data-ttu-id="b4915-132">Wenn Sie eine horizontal skalierte Bereitstellung konfiguriert haben, wiederholen Sie alle vorherigen Schritte für andere in der Bereitstellung vorhandene Berichtsserver.</span><span class="sxs-lookup"><span data-stu-id="b4915-132">If you configured a scale-out deployment, repeat all of the previous steps for other report servers in the deployment.</span></span>  
  
15. <span data-ttu-id="b4915-133">Starten Sie den Berichtsserver neu, um alle momentan geöffneten Sitzungen zu beenden.</span><span class="sxs-lookup"><span data-stu-id="b4915-133">Restart the report server to clear any sessions that are currently open.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4915-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b4915-134">See Also</span></span>  
 <span data-ttu-id="b4915-135">[Implementieren von Sicherheitserweiterungen](../extensions/security-extension/implementing-a-security-extension.md) </span><span class="sxs-lookup"><span data-stu-id="b4915-135">[Implementing a Security Extension](../extensions/security-extension/implementing-a-security-extension.md) </span></span>  
 <span data-ttu-id="b4915-136">[Authentifizierung mit dem Berichtsserver](authentication-with-the-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="b4915-136">[Authentication with the Report Server](authentication-with-the-report-server.md) </span></span>  
 <span data-ttu-id="b4915-137">[RSReportServer-Konfigurationsdatei](../report-server/rsreportserver-config-configuration-file.md) </span><span class="sxs-lookup"><span data-stu-id="b4915-137">[RSReportServer Configuration File](../report-server/rsreportserver-config-configuration-file.md) </span></span>  
 <span data-ttu-id="b4915-138">[Konfigurieren der Standard Authentifizierung auf dem Berichts Server](configure-basic-authentication-on-the-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="b4915-138">[Configure Basic Authentication on the Report Server](configure-basic-authentication-on-the-report-server.md) </span></span>  
 [<span data-ttu-id="b4915-139">Configure Windows Authentication on the Report Server (Konfigurieren der Windows-Authentifizierung auf dem Berichtsserver)</span><span class="sxs-lookup"><span data-stu-id="b4915-139">Configure Windows Authentication on the Report Server</span></span>](configure-windows-authentication-on-the-report-server.md)  
  
  
