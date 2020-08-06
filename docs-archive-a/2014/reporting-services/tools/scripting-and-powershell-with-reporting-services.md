---
title: Skripterstellung und PowerShell mit Reporting Services | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- scripts [Reporting Services]
- Reporting Services, scripting
- scripting [Reporting Services]
ms.assetid: 1ac2646d-ed5a-4436-b18f-2150c33f3d87
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a7a8dc805351897c11202467ed8bcb0373ef77c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619016"
---
# <a name="scripting-and-powershell-with-reporting-services"></a><span data-ttu-id="c6f09-102">Skripterstellung und PowerShell mit Reporting Services</span><span class="sxs-lookup"><span data-stu-id="c6f09-102">Scripting and PowerShell with Reporting Services</span></span>
  [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="c6f09-103">unterstützt eine Vielzahl von Entwicklungs- und Verwaltungsszenarien über Skripts, beispielsweise das Befehlszeilenprogramm RS.exe, PowerShell-Cmdlets für Berichtsserver im SharePoint-Modus und die Nutzung des [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] -Objektmodells in PowerShell für den einheitlichen und den SharePoint-Modus.</span><span class="sxs-lookup"><span data-stu-id="c6f09-103">supports a wide range of development and management scenarios through script, including the rs.exe command line utility, PowerShell cmdlets for SharePoint mode report servers, and leveraging the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] object model from PowerShell for both Native and SharePoint mode.</span></span>

-   <span data-ttu-id="c6f09-104">Administratoren können Skripts in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] erstellen, um das Bereitstellen und Verwalten einer Berichtsserverinstallation zu automatisieren.</span><span class="sxs-lookup"><span data-stu-id="c6f09-104">Administrators can write script in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] to automate how they deploy and manage a report server installation.</span></span> <span data-ttu-id="c6f09-105">Zudem können Administratoren [!INCLUDE[tsql](../../includes/tsql-md.md)] -Skripts generieren und ausführen, mit denen eine Berichtsserver-Datenbank erstellt, konfiguriert und aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="c6f09-105">Administrators can also generate and run [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts that create, configure, and update a report server database.</span></span> <span data-ttu-id="c6f09-106">Administratoren können auch die in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] verfügbaren Funktionen zum Aufzeichnen und Wiedergeben von Skripts verwenden, um routinemäßige Wartungsaufgaben zu automatisieren.</span><span class="sxs-lookup"><span data-stu-id="c6f09-106">Administrators can also use the record and playback script features in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] to automate routine maintenance tasks.</span></span>

-   <span data-ttu-id="c6f09-107">Entwickler können benutzerdefinierte Anwendungen erstellen, die Skripts enthalten.</span><span class="sxs-lookup"><span data-stu-id="c6f09-107">Developers can create custom applications that include script.</span></span> <span data-ttu-id="c6f09-108">Sie können Skripts ausführen, mit denen den Report Server-Webdienst aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="c6f09-108">You can run script that makes calls to the Report Server Web service.</span></span> <span data-ttu-id="c6f09-109">Fast jeder Vorgang, den Sie in verwaltetem Code schreiben können, kann auch als Skript geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="c6f09-109">Almost any operation that you can write in managed code can also be written in script.</span></span>

-   [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="c6f09-110">unterstützen das [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] .NET-Skript als Skriptsprache, die vom Hilfsprogramm RS.exe, einem auf dem Berichtsserver ausgeführten Skripthost, verarbeitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="c6f09-110">supports [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] .NET script as the script language that can be processed by the RS.exe utility, a script host that runs on the report server.</span></span>

## <a name="reporting-services-sharepoint-mode-powershell-cmdlets-and-samples"></a><span data-ttu-id="c6f09-111">PowerShell-Cmdlets für Reporting Services im SharePoint-Modus und Beispiele</span><span class="sxs-lookup"><span data-stu-id="c6f09-111">Reporting Services SharePoint mode PowerShell cmdlets and samples</span></span>
 <span data-ttu-id="c6f09-112">![PowerShell-Inhalt](../media/rs-powershellicon.jpg "PowerShell-Inhalt")</span><span class="sxs-lookup"><span data-stu-id="c6f09-112">![PowerShell related content](../media/rs-powershellicon.jpg "PowerShell related content")</span></span>

 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="c6f09-113">SharePoint-Modus umfasst [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] -Cmdlets für die Verwaltung des Berichtsservers.</span><span class="sxs-lookup"><span data-stu-id="c6f09-113">SharePoint mode includes [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] cmdlets for report server administration.</span></span>

-   <span data-ttu-id="c6f09-114">[PowerShell cmdlets for Reporting Services SharePoint Mode](../powershell-cmdlets-for-reporting-services-sharepoint-mode.md) enthält die folgenden Beispiele:</span><span class="sxs-lookup"><span data-stu-id="c6f09-114">[PowerShell cmdlets for Reporting Services SharePoint Mode](../powershell-cmdlets-for-reporting-services-sharepoint-mode.md) Includes the following examples:</span></span>

    -   <span data-ttu-id="c6f09-115">Erstellen einer Dienstanwendung und eines Proxys</span><span class="sxs-lookup"><span data-stu-id="c6f09-115">Create a service application and proxy</span></span>

    -   <span data-ttu-id="c6f09-116">Überprüfen und Aktualisieren einer Übermittlungserweiterung</span><span class="sxs-lookup"><span data-stu-id="c6f09-116">Review and update a delivery extension</span></span>

    -   <span data-ttu-id="c6f09-117">Abrufen und Festlegen von Eigenschaften der Reporting Services-Anwendungsdatenbank, z. B. Timeout der Datenbank</span><span class="sxs-lookup"><span data-stu-id="c6f09-117">Get and set Properties of the Reporting Service Application Database, for example database timeout</span></span>

    -   <span data-ttu-id="c6f09-118">Datenerweiterungen auflisten</span><span class="sxs-lookup"><span data-stu-id="c6f09-118">List Data Extensions</span></span>

## <a name="reporting-services-object-model-and-powershell-samples"></a><span data-ttu-id="c6f09-119">Reporting Services-Objektmodell und Powershell-Beispiele</span><span class="sxs-lookup"><span data-stu-id="c6f09-119">Reporting Services Object model and Powershell samples</span></span>
 <span data-ttu-id="c6f09-120">![PowerShell-Inhalt](../media/rs-powershellicon.jpg "PowerShell-Inhalt")</span><span class="sxs-lookup"><span data-stu-id="c6f09-120">![PowerShell related content](../media/rs-powershellicon.jpg "PowerShell related content")</span></span>

 <span data-ttu-id="c6f09-121">PowerShell-Aufruf des Kern-Objektmodells und zum größten Teil gültig für SharePoint- und einheitlichen Modus, z. B. die Migrationsarbeit, Abonnementarbeit und weitere Beispiele für Abonnementarbeit in SQL15.</span><span class="sxs-lookup"><span data-stu-id="c6f09-121">PowerShell calling the core object model and for the most part valid for SharePoint and native mode, for example the migration work, subscription work, and more related samples for subscriptions work in SQL15.</span></span>

-   <span data-ttu-id="c6f09-122">[Verwenden von PowerShell, um Reporting Services-Abonnenten zu ändern und aufzulisten sowie ein Abonnement auszuführen](../subscriptions/manage-subscription-owners-and-run-subscription-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="c6f09-122">[Use PowerShell to Change and List Reporting Services Subscription Owners and Run a Subscription](../subscriptions/manage-subscription-owners-and-run-subscription-powershell.md).</span></span>

-   <span data-ttu-id="c6f09-123">[Verwenden von PowerShell zum Erstellen einer Azure-VM mit einem Berichtsserver im einheitlichen Modus](https://msdn.microsoft.com/library/azure/dn449661.aspx).</span><span class="sxs-lookup"><span data-stu-id="c6f09-123">[Use PowerShell to Create an Azure VM With a Native Mode Report Server](https://msdn.microsoft.com/library/azure/dn449661.aspx).</span></span>

-   <span data-ttu-id="c6f09-124">Weitere Informationen finden Sie im Abschnitt „Zugreifen auf die WMI-Klassen mit PowerShell“ unter [Zugreifen auf den Reporting Services-WMI-Anbieter](access-the-reporting-services-wmi-provider.md).</span><span class="sxs-lookup"><span data-stu-id="c6f09-124">See the section "Access the WMI classes using PowerShell" in [Access the Reporting Services WMI Provider](access-the-reporting-services-wmi-provider.md).</span></span>

-   <span data-ttu-id="c6f09-125">[Verwalten von SSRS mit PowerShell](https://www.sqlshack.com/how-to-administer-sql-server-reporting-services-ssrs-subscriptions-using-powershell/).scriptin</span><span class="sxs-lookup"><span data-stu-id="c6f09-125">[How to Administer SSRS using PowerShell](https://www.sqlshack.com/how-to-administer-sql-server-reporting-services-ssrs-subscriptions-using-powershell/).scriptin</span></span>

## <a name="rsexe-scripting-samples"></a><span data-ttu-id="c6f09-126">Skriptbeispiele für RS.exe</span><span class="sxs-lookup"><span data-stu-id="c6f09-126">RS.exe scripting samples</span></span>

-   <span data-ttu-id="c6f09-127">[Beispiel Reporting Services rs.exe Skript zum Migrieren von Inhalten Zwischenberichts Servern](sample-reporting-services-rs-exe-script-to-copy-content-between-report-servers.md).</span><span class="sxs-lookup"><span data-stu-id="c6f09-127">[Sample Reporting Services rs.exe Script to Migrate Content between Report Servers](sample-reporting-services-rs-exe-script-to-copy-content-between-report-servers.md).</span></span>

-   <span data-ttu-id="c6f09-128">Zusätzliche Skripts, Anwendungs- und Erweiterungsbeispiele finden Sie unter [SQL Server Reporting Services-Produktbeispiele](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="c6f09-128">For additional script, application, and extension examples, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>

## <a name="see-also"></a><span data-ttu-id="c6f09-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c6f09-129">See Also</span></span>
 <span data-ttu-id="c6f09-130">[RS.exe-Hilfsprogramm &#40;SSRS&#41;](rs-exe-utility-ssrs.md) [Skript Bereitstellung und Skript für administrative Aufgaben](script-deployment-and-administrative-tasks.md) [mit dem rs.exe Hilfsprogramm und dem Webdienst](script-with-the-rs-exe-utility-and-the-web-service.md)</span><span class="sxs-lookup"><span data-stu-id="c6f09-130">[RS.exe Utility &#40;SSRS&#41;](rs-exe-utility-ssrs.md) [Script Deployment and Administrative Tasks](script-deployment-and-administrative-tasks.md) [Script with the rs.exe Utility and the Web Service](script-with-the-rs-exe-utility-and-the-web-service.md)</span></span>


