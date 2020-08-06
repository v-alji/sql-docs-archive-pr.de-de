---
title: 'Vorgehensweise: Bereitstellen einer Datenverarbeitungserweiterung für einen Berichtsserver | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- data processing extensions [Reporting Services], deploying
- assemblies [Reporting Services], data processing extension deployments
ms.assetid: e00dface-70f8-434b-9763-8ebee18737d2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d606096b9f2060d3cf5b9cea1f95a5345e592383
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725294"
---
# <a name="how-to-deploy-a-data-processing-extension-to-a-report-server"></a><span data-ttu-id="c8f49-102">Gewusst wie: Bereitstellen einer Datenverarbeitungserweiterung für einen Berichtsserver</span><span class="sxs-lookup"><span data-stu-id="c8f49-102">How to: Deploy a Data Processing Extension to a Report Server</span></span>
  <span data-ttu-id="c8f49-103">Berichtsserver verwenden Datenverarbeitungserweiterungen zum Abrufen und Verarbeiten von Daten in gerenderten Berichten.</span><span class="sxs-lookup"><span data-stu-id="c8f49-103">Report servers use data processing extensions for retrieving and processing data in rendered reports.</span></span> <span data-ttu-id="c8f49-104">Sie sollten Ihre Assembly für Datenverarbeitungserweiterungen auf dem Berichtsserver als private Assembly bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="c8f49-104">You should deploy your data processing extension assembly to a report server as a private assembly.</span></span> <span data-ttu-id="c8f49-105">Sie müssen auch einen Eintrag in der Konfigurationsdatei des Berichtsservers RSReportServer.config vornehmen.</span><span class="sxs-lookup"><span data-stu-id="c8f49-105">You also need to make an entry in the report server configuration file, RSReportServer.config.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="c8f49-106">Prozeduren</span><span class="sxs-lookup"><span data-stu-id="c8f49-106">Procedures</span></span>  
  
#### <a name="to-deploy-a-data-processing-extension-assembly"></a><span data-ttu-id="c8f49-107">So stellen Sie eine Assembly für Datenverarbeitungserweiterungen bereit</span><span class="sxs-lookup"><span data-stu-id="c8f49-107">To deploy a data processing extension assembly</span></span>  
  
1.  <span data-ttu-id="c8f49-108">Kopieren Sie die Assembly aus dem Bereitstellungsverzeichnis in das BIN-Verzeichnis des Berichtsservers, auf dem Sie die Datenverarbeitungserweiterung verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="c8f49-108">Copy your assembly from your staging location to the bin directory of the report server on which you want to use the data processing extension.</span></span> <span data-ttu-id="c8f49-109">Der Standard Speicherort für das bin-Verzeichnis des Berichts Servers lautet%ProgramFiles%\Microsoft SQL Server \ MSRS10_50. \<*Instance Name*> \Reporting Services\ReportServer\bin.</span><span class="sxs-lookup"><span data-stu-id="c8f49-109">The default location of the report server bin directory is %ProgramFiles%\Microsoft SQL Server\MSRS10_50.\<*Instance Name*>\Reporting Services\ReportServer\bin.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c8f49-110">Dieser Schritt verhindert ein Upgrade auf eine neuere Instanz von SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c8f49-110">This step will prevent an upgrade to a newer instance of SQL Server.</span></span> <span data-ttu-id="c8f49-111">Weitere Informationen finden Sie unter [Upgrade and Migrate Reporting Services](../../install-windows/upgrade-and-migrate-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="c8f49-111">For more information, see [Upgrade and Migrate Reporting Services](../../install-windows/upgrade-and-migrate-reporting-services.md).</span></span>  
  
2.  <span data-ttu-id="c8f49-112">Nachdem die Assemblydatei kopiert wurde, öffnen Sie die Datei RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="c8f49-112">After the assembly file is copied, open the RSReportServer.config file.</span></span> <span data-ttu-id="c8f49-113">Die Datei RSReportServer.config befindet sich im Verzeichnis "ReportServer".</span><span class="sxs-lookup"><span data-stu-id="c8f49-113">The RSReportServer.config file is located in the ReportServer directory.</span></span> <span data-ttu-id="c8f49-114">Sie müssen einen Eintrag in der Konfigurationsdatei für die Datei Ihrer Datenverarbeitungserweiterungsassembly vornehmen.</span><span class="sxs-lookup"><span data-stu-id="c8f49-114">You need to make an entry in the configuration file for your data processing extension assembly file.</span></span> <span data-ttu-id="c8f49-115">Sie können die Konfigurationsdatei mit Visual Studio oder mit einem einfachen Text-Editor wie dem Microsoft-Editor öffnen.</span><span class="sxs-lookup"><span data-stu-id="c8f49-115">You can open the configuration file with Visual Studio or a simple text editor, such as Notepad.</span></span>  
  
3.  <span data-ttu-id="c8f49-116">Suchen Sie das `Data`-Element in der Datei RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="c8f49-116">Locate the `Data` element in the RSReportServer.config file.</span></span> <span data-ttu-id="c8f49-117">In folgendem Verzeichnis muss ein Eintrag für Ihre neu erstellte Datenverarbeitungserweiterung erstellt werden:</span><span class="sxs-lookup"><span data-stu-id="c8f49-117">An entry for your newly created data processing extension should be made in the following location:</span></span>  
  
    ```  
    <Extensions>  
       <Data>  
          <Your extension configuration information goes here>  
       </Data>  
    </Extensions>  
    ```  
  
4.  <span data-ttu-id="c8f49-118">Fügen Sie einen Eintrag für die Datenverarbeitungserweiterung hinzu.</span><span class="sxs-lookup"><span data-stu-id="c8f49-118">Add an entry for your data processing extension.</span></span> <span data-ttu-id="c8f49-119">Der Eintrag sollte ein `Extension` Element mit Werten für `Name` und enthalten `Type` und könnte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="c8f49-119">Your entry should include an `Extension` element with values for `Name` and `Type` and might look like the following:</span></span>  
  
    ```  
    <Extension Name="ExtensionName" Type="CompanyName.ExtensionName.MyConnectionClass, MyExtensionAssembly" />  
    ```  
  
     <span data-ttu-id="c8f49-120">Der Wert für `Name` ist der eindeutige Name der Datenverarbeitungserweiterung.</span><span class="sxs-lookup"><span data-stu-id="c8f49-120">The value for `Name` is the unique name of the data processing extension.</span></span> <span data-ttu-id="c8f49-121">Der Wert für `Type` ist eine durch Trennzeichen getrennte Liste, die einen Eintrag für den vollqualifizierten Namespace der Klasse enthält, welche die Schnittstellen <xref:Microsoft.ReportingServices.Interfaces.IExtension> und <xref:Microsoft.ReportingServices.DataProcessing.IDbConnection> implementiert, gefolgt vom Namen der Assembly (ohne die Dateierweiterung .dll).</span><span class="sxs-lookup"><span data-stu-id="c8f49-121">The value for `Type` is a comma-separated list that includes an entry for the fully qualified namespace of your class that implements the <xref:Microsoft.ReportingServices.Interfaces.IExtension> and <xref:Microsoft.ReportingServices.DataProcessing.IDbConnection> interfaces, followed by the name of your assembly (not including the .dll file extension).</span></span> <span data-ttu-id="c8f49-122">Standardmäßig sind Datenverarbeitungserweiterungen sichtbar.</span><span class="sxs-lookup"><span data-stu-id="c8f49-122">By default, data processing extensions are visible.</span></span> <span data-ttu-id="c8f49-123">Um eine Erweiterung in Benutzeroberflächen wie dem Berichts-Manager auszublenden, fügen Sie das `Visible`-Attribut zum `Extension`-Element hinzu und setzen es auf `false`.</span><span class="sxs-lookup"><span data-stu-id="c8f49-123">To hide an extension from user interfaces, such as Report Manager, add a `Visible` attribute to the `Extension` element, and set it to `false`.</span></span>  
  
5.  <span data-ttu-id="c8f49-124">Fügen Sie eine Codegruppe für die benutzerdefinierte Assembly hinzu, die die Berechtigung `FullTrust` für die Erweiterung erteilt.</span><span class="sxs-lookup"><span data-stu-id="c8f49-124">Add a code group for your custom assembly that grants `FullTrust` permission for your extension.</span></span> <span data-ttu-id="c8f49-125">Hierzu fügen Sie die Codegruppe der rssrvpolicy.config Datei hinzu, die sich standardmäßig in%ProgramFiles%\Microsoft SQL Server \\<MSRS10_50 befindet. \<*Instance Name*> \Reporting Services\ReportServer.</span><span class="sxs-lookup"><span data-stu-id="c8f49-125">You do this by adding the code group to the rssrvpolicy.config file located by default in %ProgramFiles%\Microsoft SQL Server\\<MSRS10_50.\<*Instance Name*>\Reporting Services\ReportServer.</span></span> <span data-ttu-id="c8f49-126">Die Codegruppe kann folgendermaßen aussehen:</span><span class="sxs-lookup"><span data-stu-id="c8f49-126">Your code group might look like the following:</span></span>  
  
    ```  
    <CodeGroup class="UnionCodeGroup"  
       version="1"  
       PermissionSetName="FullTrust"  
       Name="MyExtensionCodeGroup"  
       Description="Code group for my data processing extension">  
          <IMembershipCondition class="UrlMembershipCondition"  
             version="1"  
             Url="C:\Program Files\Microsoft SQL Server\MSRS10_50.<Instance Name>\Reporting Services\ReportServer\bin\MyExtensionAssembly.dll"  
           />  
    </CodeGroup>  
    ```  
  
 <span data-ttu-id="c8f49-127">Die URL-Mitgliedschaft ist eine der vielen Mitgliedschaftsbedingungen, die Sie für die Datenverarbeitungserweiterung auswählen können.</span><span class="sxs-lookup"><span data-stu-id="c8f49-127">URL membership is only one of many membership conditions you might choose for your data processing extension.</span></span> <span data-ttu-id="c8f49-128">Weitere Informationen zur Codezugriffssicherheit in [!INCLUDE[ssCurrentUI](../../../includes/sscurrentui-md.md)] [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] finden Sie unter [Sichere Entwicklung &#40;Reporting Services&#41;](../secure-development/secure-development-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="c8f49-128">For more information about code access security in [!INCLUDE[ssCurrentUI](../../../includes/sscurrentui-md.md)] [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], see [Secure Development &#40;Reporting Services&#41;](../secure-development/secure-development-reporting-services.md).</span></span>  
  
## <a name="verifying-the-deployment"></a><span data-ttu-id="c8f49-129">Überprüfen der Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="c8f49-129">Verifying the Deployment</span></span>  
 <span data-ttu-id="c8f49-130">Sie können prüfen, ob Ihre Datenverarbeitungserweiterung erfolgreich auf dem Berichtsserver bereitgestellt wurde, indem Sie die Webdienstmethode <xref:ReportService2010.ReportingService2010.ListExtensions%2A> verwenden.</span><span class="sxs-lookup"><span data-stu-id="c8f49-130">You can verify whether your data processing extension was deployed successfully to the report server by using the Web service <xref:ReportService2010.ReportingService2010.ListExtensions%2A> method.</span></span> <span data-ttu-id="c8f49-131">Sie können auch den Berichts-Manager öffnen und prüfen, ob die Erweiterung in der Liste der verfügbaren Datenquellen enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="c8f49-131">You can also open Report Manager and verify that your extension is included in the list of available data sources.</span></span> <span data-ttu-id="c8f49-132">Weitere Informationen zu Berichts-Manager und Datenquellen finden Sie unter [Erstellen, Ändern und Löschen von freigegebenen Datenquellen (SSRS)](../../report-data/create-modify-and-delete-shared-data-sources-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="c8f49-132">For more information about Report Manager and data sources, see [Create, Modify, and Delete Shared Data Sources &#40;SSRS&#41;](../../report-data/create-modify-and-delete-shared-data-sources-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8f49-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c8f49-133">See Also</span></span>  
 <span data-ttu-id="c8f49-134">[Bereitstellen von Datenverarbeitungserweiterungen](deploying-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="c8f49-134">[Deploying a Data Processing Extension](deploying-a-data-processing-extension.md) </span></span>  
 <span data-ttu-id="c8f49-135">[Erweiterungen für Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="c8f49-135">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 <span data-ttu-id="c8f49-136">[Implementieren von Datenverarbeitungserweiterungen](implementing-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="c8f49-136">[Implementing a Data Processing Extension](implementing-a-data-processing-extension.md) </span></span>  
 [<span data-ttu-id="c8f49-137">Reporting Services Extension Library (Reporting Services-Erweiterungsbibliothek)</span><span class="sxs-lookup"><span data-stu-id="c8f49-137">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
