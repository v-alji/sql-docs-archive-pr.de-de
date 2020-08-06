---
title: Registrieren eines .NET Framework-Standarddatenproviders (SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- reports [Reporting Services], data
- .NET Framework data providers for Reporting Services
- data processing extensions [Reporting Services]
- data providers [Reporting Services]
- data retrieval [Reporting Services]
- Reporting Services, data sources
ms.assetid: d92add64-e93c-4598-8508-55d1bc46acf6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5fd26f9c7fa163d9e6005d42e24c7b1483987f3e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696453"
---
# <a name="register-a-standard-net-framework-data-provider-ssrs"></a><span data-ttu-id="0b489-102">Registrieren eines .NET Framework-Standarddatenproviders (SSRS)</span><span class="sxs-lookup"><span data-stu-id="0b489-102">Register a Standard .NET Framework Data Provider (SSRS)</span></span>
  <span data-ttu-id="0b489-103">Wenn Sie zum Abrufen von Daten für ein [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] -Berichtsdataset einen [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Datenanbieter eines Drittanbieters verwenden möchten, müssen Sie die [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] -Datenanbieterassembly an zwei Speicherorten bereitstellen und registrieren: auf dem Berichterstellungsclient und auf dem Berichtsserver.</span><span class="sxs-lookup"><span data-stu-id="0b489-103">To use a third-party [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider to retrieve data for a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report dataset, you need to deploy and register the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider assembly in two locations: on the report authoring client and on the report server.</span></span> <span data-ttu-id="0b489-104">Auf dem Berichterstellungsclient müssen Sie den Datenanbieter als Datenquellentyp registrieren und einem Abfrage-Designer zuordnen.</span><span class="sxs-lookup"><span data-stu-id="0b489-104">On the report authoring client, you must register the data provider as a data source type and associate it with a query designer.</span></span> <span data-ttu-id="0b489-105">Beim Erstellen eines Berichtsdatasets können Sie diesen Datenanbieter als Datenquellentyp auswählen.</span><span class="sxs-lookup"><span data-stu-id="0b489-105">You can then select this data provider as a type of data source when you create a report dataset.</span></span> <span data-ttu-id="0b489-106">Der zugeordnete Abfrage-Designer wird geöffnet, um das Erstellen von Abfragen für diesen Datenquellentyp zu erleichtern.</span><span class="sxs-lookup"><span data-stu-id="0b489-106">The associated query designer opens to help you create queries for this data source type.</span></span> <span data-ttu-id="0b489-107">Der Datenanbieter muss auf dem Berichtsserver als Datenquellentyp registriert werden.</span><span class="sxs-lookup"><span data-stu-id="0b489-107">On the report server, you must register the data provider as a data source type.</span></span> <span data-ttu-id="0b489-108">Anschließend können Sie veröffentlichte Berichte verarbeiten, für die mithilfe dieses Datenanbieters Daten von einer Datenquelle abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="0b489-108">You can then process published reports that retrieve data from a data source using this data provider.</span></span>  
  
 <span data-ttu-id="0b489-109">Es wird nicht notwendigerweise die gesamte Funktionalität von Drittanbieter-Datenanbietern unterstützt, die mit den Datenverarbeitungserweiterungen von [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="0b489-109">Third-party data providers do not necessarily provide all the functionality available with the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] data processing extensions.</span></span> <span data-ttu-id="0b489-110">Weitere Informationen finden Sie unter [Von Reporting Services unterstützte Datenquellen &#40;SSRS&#41;](../create-deploy-and-manage-mobile-and-paginated-reports.md).</span><span class="sxs-lookup"><span data-stu-id="0b489-110">For more information, see [Data Sources Supported by Reporting Services &#40;SSRS&#41;](../create-deploy-and-manage-mobile-and-paginated-reports.md).</span></span> <span data-ttu-id="0b489-111">Informationen zum Erweitern der Funktionalität eines .[!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b489-111">To learn about extending the functionality of a .[!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]</span></span> <span data-ttu-id="0b489-112">-Datenanbieters finden Sie unter [Implementieren von Datenverarbeitungserweiterungen](../extensions/data-processing/implementing-a-data-processing-extension.md).</span><span class="sxs-lookup"><span data-stu-id="0b489-112">data provider, see [Implementing a Data Processing Extension](../extensions/data-processing/implementing-a-data-processing-extension.md).</span></span>  
  
 <span data-ttu-id="0b489-113">Zum Installieren und Registrieren von Datenanbietern benötigen Sie Anmeldeinformationen als Administrator.</span><span class="sxs-lookup"><span data-stu-id="0b489-113">You need administrator credentials to install and register data providers.</span></span>  
  
## <a name="registering-a-net-framework-data-provider-on-the-report-server"></a><span data-ttu-id="0b489-114">Registrieren eines .NET Framework-Datenanbieters auf dem Berichtsserver</span><span class="sxs-lookup"><span data-stu-id="0b489-114">Registering a .NET Framework Data Provider on the Report Server</span></span>  
 <span data-ttu-id="0b489-115">Wenn Sie auf dem Berichtsserver veröffentlichte Berichte verarbeiten möchten, für die dieser [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] -Datenanbieter verwendet wird, muss die Assembly auf dem Berichtsserver installiert werden.</span><span class="sxs-lookup"><span data-stu-id="0b489-115">In order to process published reports that use this [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider on the report server, you need to install the assembly on the report server.</span></span> <span data-ttu-id="0b489-116">Zwei Konfigurationsdateien müssen geändert werden.</span><span class="sxs-lookup"><span data-stu-id="0b489-116">You must modify two configuration files.</span></span> <span data-ttu-id="0b489-117">Ändern Sie rsreportserver.config so, dass der Datenanbieter registriert wird.</span><span class="sxs-lookup"><span data-stu-id="0b489-117">Modify rsreportserver.config to register the data provider.</span></span> <span data-ttu-id="0b489-118">Ändern Sie rssrvpolicy.config so, dass Codezugriffsberechtigungen für die Assembly erteilt werden.</span><span class="sxs-lookup"><span data-stu-id="0b489-118">Modify rssrvpolicy.config to grant code access security permissions for the assembly.</span></span>  
  
#### <a name="to-install-a-data-provider-assembly-on-the-report-server"></a><span data-ttu-id="0b489-119">So installieren Sie eine Datenanbieterassembly auf dem Berichtsserver</span><span class="sxs-lookup"><span data-stu-id="0b489-119">To install a data provider assembly on the report server</span></span>  
  
1.  <span data-ttu-id="0b489-120">Navigieren Sie zum Standardspeicherort des BIN-Verzeichnisses auf dem Berichtsserver, auf dem Sie den [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] -Datenanbieter verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="0b489-120">Navigate to the default location of the bin directory on the report server on which you want to use the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider.</span></span> <span data-ttu-id="0b489-121">Der Standard Speicherort für das bin-Verzeichnis des Berichts Servers lautet *\<drive>* : \Programme\Microsoft SQL Server \ MSRS10_50. MSSQLSERVER\Reporting Services\ReportServer\bin.</span><span class="sxs-lookup"><span data-stu-id="0b489-121">The default location of the report server bin directory is *\<drive>*:\Program Files\Microsoft SQL Server\MSRS10_50.MSSQLSERVER\Reporting Services\ReportServer\bin.</span></span>  
  
2.  <span data-ttu-id="0b489-122">Kopieren Sie die Assembly aus dem Bereitstellungsverzeichnis in das BIN-Verzeichnis des Berichtsservers.</span><span class="sxs-lookup"><span data-stu-id="0b489-122">Copy your assembly from your staging location to the bin directory of the report server.</span></span> <span data-ttu-id="0b489-123">Sie können die Assembly im globalen Assemblycache (Global Assembly Cache, GAC) laden.</span><span class="sxs-lookup"><span data-stu-id="0b489-123">Alternatively, you can load your assembly in the global assembly cache (GAC).</span></span> <span data-ttu-id="0b489-124">Weitere Informationen finden Sie unter dem Thema [Arbeiten mit Assemblys und dem globalen Assemblycache](https://go.microsoft.com/fwlink/?linkid=63912) in der [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK-Dokumentation zur Plattform MSDN.</span><span class="sxs-lookup"><span data-stu-id="0b489-124">For more information, see [Working with Assemblies and the Global Assembly Cache](https://go.microsoft.com/fwlink/?linkid=63912) in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK documentation on MSDN.</span></span>  
  
#### <a name="to-register-a-net-data-provider-on-the-report-server"></a><span data-ttu-id="0b489-125">So registrieren Sie einen .NET-Datenanbieter auf dem Berichtsserver</span><span class="sxs-lookup"><span data-stu-id="0b489-125">To register a .NET data provider on the report server</span></span>  
  
1.  <span data-ttu-id="0b489-126">Erstellen Sie in dem ReportServer-Verzeichnis, das dem BIN-Verzeichnis übergeordnet ist, eine Sicherungskopie der Datei RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="0b489-126">Make a backup of the RSReportServer.config file in the ReportServer parent directory for bin.</span></span>  
  
2.  <span data-ttu-id="0b489-127">Öffnen Sie die Datei "RSReportServer.config". Sie können die Konfigurationsdatei mit [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] oder in einem einfachen Text-Editor wie Editor öffnen.</span><span class="sxs-lookup"><span data-stu-id="0b489-127">Open RSReportServer.config. You can open the configuration file with [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] or a simple text editor, such as Notepad.</span></span>  
  
3.  <span data-ttu-id="0b489-128">Suchen Sie das `Data`-Element in der Datei RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="0b489-128">Locate the `Data` element in the RSReportServer.config file.</span></span> <span data-ttu-id="0b489-129">Im folgenden Verzeichnis muss ein Eintrag für den [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] -Datenanbieter erstellt werden:</span><span class="sxs-lookup"><span data-stu-id="0b489-129">An entry for the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider should be made in the following location:</span></span>  
  
    ```  
    <Extensions>  
       <Data>  
          <Extension Your data provider configuration information goes here />  
       </Data>  
    </Extensions>  
    ```  
  
4.  <span data-ttu-id="0b489-130">Fügen Sie einen Eintrag für den [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] -Datenanbieter hinzu.</span><span class="sxs-lookup"><span data-stu-id="0b489-130">Add an entry for the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider.</span></span>  
  
    |<span data-ttu-id="0b489-131">attribute</span><span class="sxs-lookup"><span data-stu-id="0b489-131">Attribute</span></span>|<span data-ttu-id="0b489-132">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0b489-132">Description</span></span>|  
    |---------------|-----------------|  
    |`Name`|<span data-ttu-id="0b489-133">Geben Sie einen eindeutigen Namen für den Datenanbieter an, z. B. **MyNETDataProvider**.</span><span class="sxs-lookup"><span data-stu-id="0b489-133">Provide a unique name for the data provider, for example, **MyNETDataProvider**.</span></span> <span data-ttu-id="0b489-134">Die maximale Länge für das `Name`-Attribut beträgt 255 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="0b489-134">The maximum length for the `Name` attribute is 255 characters.</span></span> <span data-ttu-id="0b489-135">Der Name muss für sämtliche Einträge im `Extension`-Element einer Konfigurationsdatei eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="0b489-135">The name must be unique among all entries within the `Extension` element of a configuration file.</span></span> <span data-ttu-id="0b489-136">Der hier eingeschlossene Wert wird beim Erstellen einer neuen Datenquelle in der Dropdownliste der Datenquellentypen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0b489-136">The value you include here appears in the drop-down list of data source types when you create a new data source.</span></span>|  
    |`Type`|<span data-ttu-id="0b489-137">Geben Sie eine durch Trennzeichen getrennte Liste ein, die den vollqualifizierten Namespace der Klasse enthält, die die <xref:System.Data.IDbConnection> -Schnittstelle implementiert, gefolgt vom Namen der [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] -Datenanbieterassembly (ohne die Dateinamenerweiterung DLL).</span><span class="sxs-lookup"><span data-stu-id="0b489-137">Enter a comma-separated list that includes the fully qualified namespace of the class that implements the <xref:System.Data.IDbConnection> interface, followed by the name of the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider assembly (not including the .dll file name extension).</span></span>|  
  
     <span data-ttu-id="0b489-138">Für eine im BIN-Verzeichnis des Berichtsservers bereitgestellte DLL-Datei kann der Eintrag beispielsweise dem Folgenden ähneln:</span><span class="sxs-lookup"><span data-stu-id="0b489-138">For example, the entry might resemble the following for a DLL deployed to the report server bin directory:</span></span>  
  
    ```  
    <Extension Name="MyNETDataProvider" Type="CompanyName.ExtensionName.DataProviderConnectionClass, DataProviderAssembly" />   
    ```  
  
     <span data-ttu-id="0b489-139">Wenn Sie die Assembly in den GAC (Global Assembly Cache, globalen Assemblycache) laden, müssen Sie die Eigenschaften für starke Namen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="0b489-139">If you load your assembly into the global assembly cache (GAC), you must provide the strong name properties.</span></span> <span data-ttu-id="0b489-140">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0b489-140">For example:</span></span>  
  
    ```  
    <Extension Name="MyNETDataProvider" Type="CompanyName.ExtensionName.DataProviderConnectionClass, DataProviderAssembly,Version=1.0.0.0, Culture=neutral, PublicKeyToken=MyPublicToken"/>  
    ```  
  
#### <a name="to-set-the-code-group-policy-for-a-net-data-provider"></a><span data-ttu-id="0b489-141">Festlegen der Codegruppenrichtlinie für einen .NET-Datenanbieter</span><span class="sxs-lookup"><span data-stu-id="0b489-141">To set the code group policy for a .NET data provider</span></span>  
  
1.  <span data-ttu-id="0b489-142">Erstellen Sie im Verzeichnis "ReportServer", das dem Verzeichnis "bin" übergeordnet ist, eine Sicherungskopie der Datei "rssrvpolicy.config".</span><span class="sxs-lookup"><span data-stu-id="0b489-142">Make a backup copy of the rssrvpolicy.config file in the ReportServer parent directory for bin.</span></span>  
  
2.  <span data-ttu-id="0b489-143">Öffnen Sie rssrvpolicy.config. Sie können die Konfigurationsdatei mit [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] oder einem einfachen Text-Editor wie Notepad öffnen.</span><span class="sxs-lookup"><span data-stu-id="0b489-143">Open rssrvpolicy.config. You can open the configuration file with [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] or a simple text editor such as Notepad.</span></span>  
  
3.  <span data-ttu-id="0b489-144">Suchen Sie das `CodeGroup`-Element in der Datei rssrvpolicy.config.</span><span class="sxs-lookup"><span data-stu-id="0b489-144">Locate the `CodeGroup` element in the rssrvpolicy.config file.</span></span>  
  
4.  <span data-ttu-id="0b489-145">Fügen Sie eine Codegruppe für die Datenanbieterassembly hinzu, durch die die Berechtigung `FullTrust` erteilt wird.</span><span class="sxs-lookup"><span data-stu-id="0b489-145">Add a code group for the data provider assembly that grants `FullTrust` permission.</span></span> <span data-ttu-id="0b489-146">Die Codegruppe könnte beispielsweise der Folgenden ähneln:</span><span class="sxs-lookup"><span data-stu-id="0b489-146">Your code group might resemble the following:</span></span>  
  
    ```  
    <CodeGroup class="UnionCodeGroup"  
       version="1"  
       PermissionSetName="FullTrust"  
       Name="ThisDataProviderCodeGroup"  
       Description="Code group for the .NET data provider">  
          <IMembershipCondition class="UrlMembershipCondition"  
             version="1"  
             Url=  
    "C:\Program Files\Microsoft SQL Server\MSRS10_50.MSSQLSERVER\Reporting Services\ReportServer\bin\DataProviderAssembly.dll"  
           />  
    </CodeGroup>  
    ```  
  
 <span data-ttu-id="0b489-147">Die URL-Mitgliedschaft ist eine der vielen Mitgliedschaftsbedingungen, die Sie für den Datenanbieter auswählen können.</span><span class="sxs-lookup"><span data-stu-id="0b489-147">URL membership is only one of many membership conditions you might select for the data provider.</span></span>  
  
### <a name="verifying-the-deployment-and-registration"></a><span data-ttu-id="0b489-148">Überprüfen der Bereitstellung und der Registrierung</span><span class="sxs-lookup"><span data-stu-id="0b489-148">Verifying the Deployment and Registration</span></span>  
 <span data-ttu-id="0b489-149">Sie können überprüfen, ob der Datenanbieter erfolgreich auf dem Berichtsserver bereitgestellt wurde, indem Sie den Berichts-Manager öffnen und sicherstellen, dass der Datenanbieter in der Liste verfügbarer Datenquellen vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="0b489-149">You can verify whether the data provider was deployed successfully to the report server by opening Report Manager and verifying that the data provider is included in the list of available data sources.</span></span> <span data-ttu-id="0b489-150">Weitere Informationen zu Berichts-Manager und Datenquellen finden Sie unter [Erstellen, Ändern und Löschen von freigegebenen Datenquellen (SSRS)](create-modify-and-delete-shared-data-sources-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="0b489-150">For more information about Report Manager and data sources, see [Create, Modify, and Delete Shared Data Sources &#40;SSRS&#41;](create-modify-and-delete-shared-data-sources-ssrs.md).</span></span>  
  
## <a name="registering-a-net-framework-data-provider-on-the-report-designer-client"></a><span data-ttu-id="0b489-151">Registrieren eines .NET Framework-Datenanbieters auf dem Berichts-Designer-Client</span><span class="sxs-lookup"><span data-stu-id="0b489-151">Registering a .NET Framework Data Provider on the Report Designer Client</span></span>  
 <span data-ttu-id="0b489-152">Wenn Sie Berichte erstellen möchten, für die dieser [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] -Datenanbieter als Datenquelle verwendet wird, muss die Assembly auf dem Clientcomputer installiert werden, auf dem der Berichts-Designer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0b489-152">In order to author reports that use this [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider for a data source, you must install the assembly on your client computer that runs Report Designer.</span></span> <span data-ttu-id="0b489-153">Zwei Konfigurationsdateien müssen geändert werden.</span><span class="sxs-lookup"><span data-stu-id="0b489-153">You must modify two configuration files.</span></span> <span data-ttu-id="0b489-154">Ändern Sie RSReportDesigner.config so, dass der Datenanbieter als Datenquelle registriert und der standardmäßige Abfrage-Designer verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0b489-154">Modify RSReportDesigner.config to register the data provider as a data source and to use the generic query designer.</span></span> <span data-ttu-id="0b489-155">Ändern Sie RSPreviewPolicy.config so, dass Codezugriffsberechtigungen für die Datenanbieterassembly erteilt werden.</span><span class="sxs-lookup"><span data-stu-id="0b489-155">Modify RSPreviewPolicy.config to grant code access security permissions for the data provider assembly.</span></span>  
  
#### <a name="to-install-a-data-provider-assembly-on-the-report-designer-client"></a><span data-ttu-id="0b489-156">So installieren Sie eine Datenanbieterassembly auf dem Berichts-Designer-Client</span><span class="sxs-lookup"><span data-stu-id="0b489-156">To install a data provider assembly on the Report Designer client</span></span>  
  
1.  <span data-ttu-id="0b489-157">Navigieren Sie zum Standardspeicherort des Verzeichnisses PrivateAssemblies auf dem Berichts-Designer-Client, auf dem Sie den [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] -Datenanbieter verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="0b489-157">Navigate to the default location of the PrivateAssemblies directory on the Report Designer client on which you want to use the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider.</span></span> <span data-ttu-id="0b489-158">Der Standard Speicherort für das privateassemblyverzeichnis lautet *\<drive>* : \Programme\Microsoft Visual Studio 9.0 \ Common7\IDE\PrivateAssemblies.</span><span class="sxs-lookup"><span data-stu-id="0b489-158">The default location of the PrivateAssemblies directory is *\<drive>*:\Program Files\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies.</span></span>  
  
2.  <span data-ttu-id="0b489-159">Kopieren Sie die Assembly aus dem Bereitstellungsverzeichnis in das Verzeichnis PrivateAssemblies des Berichts-Designer-Clients.</span><span class="sxs-lookup"><span data-stu-id="0b489-159">Copy your assembly from your staging location to the PrivateAssemblies directory of the Report Designer client.</span></span> <span data-ttu-id="0b489-160">Sie können die Assembly im globalen Assemblycache (Global Assembly Cache, GAC) laden.</span><span class="sxs-lookup"><span data-stu-id="0b489-160">Alternatively, you can load your assembly in the global assembly cache (GAC).</span></span> <span data-ttu-id="0b489-161">Weitere Informationen finden Sie unter dem Thema [Arbeiten mit Assemblys und dem globalen Assemblycache](https://go.microsoft.com/fwlink/?linkid=63912) in der [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK-Dokumentation zur Plattform MSDN.</span><span class="sxs-lookup"><span data-stu-id="0b489-161">For more information, see [Working with Assemblies and the Global Assembly Cache](https://go.microsoft.com/fwlink/?linkid=63912) in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK documentation on MSDN.</span></span>  
  
#### <a name="to-register-a-net-data-provider-on-the-report-designer-client"></a><span data-ttu-id="0b489-162">So registrieren Sie einen .NET-Datenanbieter auf dem Berichts-Designer-Client</span><span class="sxs-lookup"><span data-stu-id="0b489-162">To register a .NET data provider on the Report Designer client</span></span>  
  
1.  <span data-ttu-id="0b489-163">Erstellen Sie eine Sicherungskopie der Datei "RSReportDesigner.config" im Verzeichnis "PrivateAssemblies".</span><span class="sxs-lookup"><span data-stu-id="0b489-163">Make a backup copy of the RSReportDesigner.config file in the PrivateAssemblies directory.</span></span>  
  
2.  <span data-ttu-id="0b489-164">Öffnen Sie die Datei "RSReportDesigner.config" mit [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] oder in einem einfachen Text-Editor wie Editor.</span><span class="sxs-lookup"><span data-stu-id="0b489-164">Open RSReportDesigner.config with [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] or a simple text editor such as Notepad.</span></span>  
  
3.  <span data-ttu-id="0b489-165">Suchen Sie das `Data`-Element in der Datei RSReportDesigner.config.</span><span class="sxs-lookup"><span data-stu-id="0b489-165">Locate the `Data` element in the RSReportDesigner.config file.</span></span> <span data-ttu-id="0b489-166">Im folgenden Verzeichnis muss ein Eintrag für den Datenanbieter erstellt werden:</span><span class="sxs-lookup"><span data-stu-id="0b489-166">An entry for the data provider should be made in the following location:</span></span>  
  
    ```  
    <Extensions>  
       <Data>  
          <Extension Your data provider configuration information goes here />  
       </Data>  
    </Extensions>  
    ```  
  
4.  <span data-ttu-id="0b489-167">Fügen Sie einen Eintrag für den Datenanbieter hinzu.</span><span class="sxs-lookup"><span data-stu-id="0b489-167">Add an entry for the data provider.</span></span>  
  
    |<span data-ttu-id="0b489-168">attribute</span><span class="sxs-lookup"><span data-stu-id="0b489-168">Attribute</span></span>|<span data-ttu-id="0b489-169">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0b489-169">Description</span></span>|  
    |---------------|-----------------|  
    |`Name`|<span data-ttu-id="0b489-170">Geben Sie einen eindeutigen Namen für den Datenanbieter an, z. B. **MyNETDataProvider**.</span><span class="sxs-lookup"><span data-stu-id="0b489-170">Provide a unique name for the data provider, for example, **MyNETDataProvider**.</span></span> <span data-ttu-id="0b489-171">Die maximale Länge für das `Name`-Attribut beträgt 255 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="0b489-171">The maximum length for the `Name` attribute is 255 characters.</span></span> <span data-ttu-id="0b489-172">Der Name muss für sämtliche Einträge im `Extension`-Element einer Konfigurationsdatei eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="0b489-172">The name must be unique among all entries within the `Extension` element of a configuration file.</span></span> <span data-ttu-id="0b489-173">Der hier eingeschlossene Wert wird beim Erstellen einer neuen Datenquelle in der Dropdownliste der Datenquellentypen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0b489-173">The value that you include here appears in the drop-down list of data source types when you create a new data source.</span></span>|  
    |`Type`|<span data-ttu-id="0b489-174">Geben Sie eine durch Trennzeichen getrennte Liste ein, die den vollqualifizierten Namespace der Klasse enthält, die die <xref:System.Data.IDbConnection> -Schnittstelle implementiert, gefolgt vom Namen der [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] -Datenanbieterassembly (ohne die Dateinamenerweiterung DLL).</span><span class="sxs-lookup"><span data-stu-id="0b489-174">Enter a comma-separated list that includes the fully qualified namespace of the class that implements the <xref:System.Data.IDbConnection> interface, followed by the name of the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider assembly (not including the .dll file name extension).</span></span>|  
  
     <span data-ttu-id="0b489-175">Für eine im Verzeichnis PrivateAssemblies von [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] bereitgestellte DLL-Datei kann der Eintrag beispielsweise dem Folgenden ähneln:</span><span class="sxs-lookup"><span data-stu-id="0b489-175">For example, the entry might resemble the following for a DLL deployed to the [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] PrivateAssemblies directory:</span></span>  
  
    ```  
    <Extension Name="MyNETDataProvider" Type="CompanyName.ExtensionName.DataProviderConnectionClass, DataProviderAssembly" />   
    ```  
  
     <span data-ttu-id="0b489-176">Wenn Sie die Assembly in den GAC (Global Assembly Cache, globaler Assemblycache) laden, müssen Sie die Eigenschaften für starke Namen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="0b489-176">If you load your assembly into the GAC, you must provide the strong name properties.</span></span> <span data-ttu-id="0b489-177">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0b489-177">For example:</span></span>  
  
    ```  
    <Extension Name="MyNETDataProvider" Type="CompanyName.ExtensionName.DataProviderConnectionClass, DataProviderAssembly, Version=1.0.0.0, Culture=neutral, PublicKeyToken=MyPublicToken"/>  
    ```  
  
5.  <span data-ttu-id="0b489-178">Suchen Sie das `Designer`-Element in der Datei RSReportDesigner.config.</span><span class="sxs-lookup"><span data-stu-id="0b489-178">Locate the `Designer` element in the RSReportDesigner.config file.</span></span> <span data-ttu-id="0b489-179">Im folgenden Verzeichnis muss ein Eintrag für den [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] -Datenanbieter erstellt werden:</span><span class="sxs-lookup"><span data-stu-id="0b489-179">An entry for the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider should be made in the following location:</span></span>  
  
    ```  
    <Extensions>  
       <Designer>  
          <Your data provider configuration information goes here>  
       </Designer>  
    </Extensions>  
    ```  
  
6.  <span data-ttu-id="0b489-180">Fügen Sie der Datei RSReportDesigner.config unter dem `Designer`-Element den folgenden Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="0b489-180">Add the following entry to the RSReportDesigner.config file under the `Designer` element.</span></span> <span data-ttu-id="0b489-181">Sie müssen nur das `Name`-Attribut durch den in früheren Einträgen angegebenen Namen ersetzen.</span><span class="sxs-lookup"><span data-stu-id="0b489-181">You need to replace only the `Name` attribute with the name that you provided in previous entries.</span></span>  
  
    ```  
    <Extension Name="MyNETDataProvider" Type="Microsoft.ReportingServices.QueryDesigners.GenericQueryDesigner,Microsoft.ReportingServices.QueryDesigners"/>  
    ```  
  
#### <a name="to-set-the-code-group-policy-for-a-net-data-provider-on-the-report-designer-client"></a><span data-ttu-id="0b489-182">So legen Sie die Codegruppenrichtlinie für einen .NET-Datenanbieter auf dem Berichts-Designer-Client fest</span><span class="sxs-lookup"><span data-stu-id="0b489-182">To set the code group policy for a .NET data provider on the Report Designer client</span></span>  
  
1.  <span data-ttu-id="0b489-183">Erstellen Sie eine Sicherungskopie der Datei "RSPreviewPolicy.config" im Verzeichnis "PrivateAssemblies".</span><span class="sxs-lookup"><span data-stu-id="0b489-183">Make a backup copy of the RSPreviewPolicy.config file in the PrivateAssemblies directory.</span></span>  
  
2.  <span data-ttu-id="0b489-184">Öffnen Sie RSPreviewPolicy.config in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] oder einem einfachen Text-Editor, z. B. im Windows-Editor.</span><span class="sxs-lookup"><span data-stu-id="0b489-184">Open RSPreviewPolicy.config with [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] or a simple text editor, such as Notepad.</span></span>  
  
3.  <span data-ttu-id="0b489-185">Suchen Sie das `CodeGroup`-Element in der Datei RSPreviewPolicy.config.</span><span class="sxs-lookup"><span data-stu-id="0b489-185">Locate the `CodeGroup` element in the RSPreviewPolicy.config file.</span></span>  
  
4.  <span data-ttu-id="0b489-186">Fügen Sie eine Codegruppe für die [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]-Datenanbieterassembly hinzu, durch die die Berechtigung `FullTrust` erteilt wird.</span><span class="sxs-lookup"><span data-stu-id="0b489-186">Add a code group for the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider assembly that grants `FullTrust` permission.</span></span> <span data-ttu-id="0b489-187">Die Codegruppe könnte beispielsweise der Folgenden ähneln:</span><span class="sxs-lookup"><span data-stu-id="0b489-187">Your code group might resemble the following:</span></span>  
  
    ```  
    <CodeGroup class="UnionCodeGroup"  
       version="1"  
       PermissionSetName="FullTrust"  
       Name="ThisDataProviderCodeGroup"  
       Description="Code group for the .NET data provider">  
          <IMembershipCondition class="UrlMembershipCondition"  
             version="1"  
             Url=  
    " C:\Program Files\Microsoft Visual Studio 9\Common7\IDE\PrivateAssemblies\DataProviderAssembly.dll"  
           />  
    </CodeGroup>  
    ```  
  
 <span data-ttu-id="0b489-188">Die URL-Mitgliedschaft ist eine der vielen Mitgliedschaftsbedingungen, die Sie für den Datenanbieter auswählen können.</span><span class="sxs-lookup"><span data-stu-id="0b489-188">URL membership is only one of many membership conditions you might select for the data provider.</span></span>  
  
### <a name="verifying-the-deployment-and-registration-on-the-report-designer-client"></a><span data-ttu-id="0b489-189">Überprüfen der Bereitstellung und der Registrierung auf dem Berichts-Designer-Client</span><span class="sxs-lookup"><span data-stu-id="0b489-189">Verifying the Deployment and Registration on the Report Designer Client</span></span>  
 <span data-ttu-id="0b489-190">Sie können die Bereitstellung erst überprüfen, wenn Sie alle Instanzen von [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] auf Ihrem lokalen Computer geschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="0b489-190">Before you can verify deployment, you must close all instances of [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] on your local computer.</span></span> <span data-ttu-id="0b489-191">Wenn Sie alle aktuellen Sitzungen beendet haben, können Sie überprüfen, ob der Datenanbieter erfolgreich für den Berichts-Designer bereitgestellt wurde, indem Sie in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]ein neues Berichtsprojekt erstellen.</span><span class="sxs-lookup"><span data-stu-id="0b489-191">After you have ended all current sessions, you can verify whether your data provider was deployed successfully to Report Designer by creating a new report project in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span></span> <span data-ttu-id="0b489-192">Der Datenanbieter sollte beim Erstellen eines neuen Datasets für den Bericht in der Liste der verfügbaren Datenquellentypen aufgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="0b489-192">The data provider should be included in the list of available data source types when you create a new data set for your report.</span></span>  
  
## <a name="platform-considerations"></a><span data-ttu-id="0b489-193">Bedingungen bezüglich der Plattform</span><span class="sxs-lookup"><span data-stu-id="0b489-193">Platform Considerations</span></span>  
 <span data-ttu-id="0b489-194">Auf einer 64-Bit-Plattform (x64) wird [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] im 32-Bit-WOW-Modus ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="0b489-194">On a 64-bit (x64) platform, [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] runs in 32-bit WOW mode.</span></span> <span data-ttu-id="0b489-195">Wenn Sie Berichte auf einer x64-Plattform erstellen, müssen auf dem Berichterstellungsclient 32-Bit-Datenanbieter installiert sein, um eine Vorschau der Berichte zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="0b489-195">When you author reports on an x64 platform, you need 32-bit data providers installed on the report authoring client in order to preview your reports.</span></span> <span data-ttu-id="0b489-196">Wenn Sie den Bericht in demselben System veröffentlichen, benötigen Sie x64-Datenanbieter zum Anzeigen des Berichts im Berichts-Manager.</span><span class="sxs-lookup"><span data-stu-id="0b489-196">If you publish the report on the same system, you need x64 data providers to view the report with Report Manager.</span></span>  
  
 [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] <span data-ttu-id="0b489-197">wird für [!INCLUDE[vcpritanium](../../includes/vcpritanium-md.md)]-basierte Plattformen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0b489-197">is not supported for [!INCLUDE[vcpritanium](../../includes/vcpritanium-md.md)]-based platforms.</span></span>  
  
 <span data-ttu-id="0b489-198">Die mit [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installierten Datenverarbeitungserweiterungen müssen für jede Plattform systemintern kompiliert und in den richtigen Verzeichnissen installiert werden.</span><span class="sxs-lookup"><span data-stu-id="0b489-198">The data processing extensions that are installed with [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] must be compiled natively for each platform and installed in the correct locations.</span></span> <span data-ttu-id="0b489-199">Wenn Sie einen benutzerdefinierten Datenanbieter oder einen [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] -Standarddatenanbieter registrieren, muss dieser systemintern für die betreffende Plattform kompiliert und im entsprechenden Verzeichnis installiert werden.</span><span class="sxs-lookup"><span data-stu-id="0b489-199">If you register a custom data provider or a standard [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider, it needs to be compiled natively for the appropriate platform and installed the appropriate locations.</span></span> <span data-ttu-id="0b489-200">Wenn Sie diesen auf einer 32-Bit-Plattform ausführen, muss der Datenanbieter für eine 32-Bit-Plattform kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="0b489-200">If you are running on a 32-bit platform, the data provider must be compiled for a 32-bit platform.</span></span> <span data-ttu-id="0b489-201">Wenn Sie ihn auf einer 64-Bit-Plattform ausführen, muss der Datenanbieter für die 64-Bit-Plattform kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="0b489-201">If you are running on a 64-bit platform, the data provider must be compiled for the 64-bit platform.</span></span> <span data-ttu-id="0b489-202">Sie können keinen 32-Bit-Datenanbieter verwenden, der in 64-Bit-Schnittstellen für eine 64-Bit-Plattform eingeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="0b489-202">You cannot use a 32-bit data provider wrapped with 64-bit interfaces on a 64 bit platform.</span></span> <span data-ttu-id="0b489-203">Überprüfen Sie Ihre Drittanbietersoftware auf Informationen dazu, ob der Datenanbieter für die installierte Plattform verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="0b489-203">Check your third-party software for information about whether the data provider will work on the installed platform.</span></span> <span data-ttu-id="0b489-204">Weitere Informationen zu Datenanbietern und zur Plattformunterstützung finden Sie unter [Von Reporting Services unterstützte Datenquellen (SSRS)](../create-deploy-and-manage-mobile-and-paginated-reports.md).</span><span class="sxs-lookup"><span data-stu-id="0b489-204">For more information about data providers and platform support, see [Data Sources Supported by Reporting Services &#40;SSRS&#41;](../create-deploy-and-manage-mobile-and-paginated-reports.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b489-205">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0b489-205">See Also</span></span>  
 <span data-ttu-id="0b489-206">[Konfigurieren und Verwalten eines Berichtsservers &#40;einheitlicher SSRS-Modus&#41;](../report-server/configure-and-administer-a-report-server-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="0b489-206">[Configure and Administer a Report Server &#40;SSRS Native Mode&#41;](../report-server/configure-and-administer-a-report-server-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="0b489-207">[Implementieren einer Datenverarbeitungs Erweiterung](../extensions/data-processing/implementing-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="0b489-207">[Implementing a Data Processing Extension](../extensions/data-processing/implementing-a-data-processing-extension.md) </span></span>  
 <span data-ttu-id="0b489-208">[Reporting Services-Konfigurationsdateien](../report-server/reporting-services-configuration-files.md) </span><span class="sxs-lookup"><span data-stu-id="0b489-208">[Reporting Services Configuration Files](../report-server/reporting-services-configuration-files.md) </span></span>  
 [<span data-ttu-id="0b489-209">Codezugriffssicherheit in Reporting Services</span><span class="sxs-lookup"><span data-stu-id="0b489-209">Code Access Security in Reporting Services</span></span>](../extensions/secure-development/code-access-security-in-reporting-services.md)  
  
  
