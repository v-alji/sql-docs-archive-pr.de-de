---
title: 'Vorgehensweise: Bereitstellen einer Datenverarbeitungserweiterung für den Berichts-Designer | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- data processing extensions [Reporting Services], deploying
- assemblies [Reporting Services], data processing extension deployments
ms.assetid: 3614e601-004e-4a16-8388-836ffd67e9dd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 56bd56e9d8eeeeff1781f22b42cf0eb1ce706fa4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725278"
---
# <a name="how-to-deploy-a-data-processing-extension-to-report-designer"></a><span data-ttu-id="9b8d0-102">Gewusst wie: Bereitstellen einer Datenverarbeitungserweiterung für den Berichts-Designer</span><span class="sxs-lookup"><span data-stu-id="9b8d0-102">How to: Deploy a Data Processing Extension to Report Designer</span></span>
  <span data-ttu-id="9b8d0-103">Beim Entwerfen von Berichten verwendet der Berichts-Designer Datenverarbeitungserweiterungen zum Abruf und zur Verarbeitung von Daten.</span><span class="sxs-lookup"><span data-stu-id="9b8d0-103">Report Designer uses data processing extensions for retrieving and processing data while you are designing reports.</span></span> <span data-ttu-id="9b8d0-104">Sie sollten Ihre Assembly für Datenverarbeitungserweiterungen auf dem Berichts-Designer als private Assembly bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="9b8d0-104">You should deploy your data processing extension assembly to Report Designer as a private assembly.</span></span> <span data-ttu-id="9b8d0-105">Sie müssen auch einen Eintrag in der Konfigurationsdatei des Berichts-Designers RSReportDesigner.config vornehmen.</span><span class="sxs-lookup"><span data-stu-id="9b8d0-105">You also need to make an entry in the Report Designer configuration file, RSReportDesigner.config.</span></span>  
  
#### <a name="to-deploy-a-data-processing-extension-assembly"></a><span data-ttu-id="9b8d0-106">So stellen Sie eine Assembly für Datenverarbeitungserweiterungen bereit</span><span class="sxs-lookup"><span data-stu-id="9b8d0-106">To deploy a data processing extension assembly</span></span>  
  
1.  <span data-ttu-id="9b8d0-107">Kopieren Sie die Assembly aus dem Bereitstellungsverzeichnis in das Verzeichnis „Berichts-Designer“.</span><span class="sxs-lookup"><span data-stu-id="9b8d0-107">Copy your assembly from your staging location to the Report Designer directory.</span></span> <span data-ttu-id="9b8d0-108">Das Standardverzeichnis für den Berichts-Designer ist C:\Programme\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies.</span><span class="sxs-lookup"><span data-stu-id="9b8d0-108">The default location of the Report Designer directory is C:\Program Files\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies.</span></span>  
  
2.  <span data-ttu-id="9b8d0-109">Nachdem die Assemblydatei kopiert wurde, öffnen Sie die Datei RSReportDesigner.config.</span><span class="sxs-lookup"><span data-stu-id="9b8d0-109">After the assembly file is copied, open the RSReportDesigner.config file.</span></span> <span data-ttu-id="9b8d0-110">Die Datei RSReportDesigner.config befindet sich auch im Verzeichnis „Berichts-Designer“.</span><span class="sxs-lookup"><span data-stu-id="9b8d0-110">The RSReportDesigner.config file is also located in the Report Designer directory.</span></span> <span data-ttu-id="9b8d0-111">Sie müssen einen Eintrag in der Konfigurationsdatei für die Datei Ihrer Datenverarbeitungserweiterungsassembly vornehmen.</span><span class="sxs-lookup"><span data-stu-id="9b8d0-111">You need to make an entry in the configuration file for your data processing extension assembly file.</span></span> <span data-ttu-id="9b8d0-112">Sie können die Konfigurationsdatei mit [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] oder in einem einfachen Text-Editor wie dem Editor öffnen.</span><span class="sxs-lookup"><span data-stu-id="9b8d0-112">You can open the configuration file with [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] or with a simple text editor, such as Notepad.</span></span>  
  
3.  <span data-ttu-id="9b8d0-113">Suchen Sie das **Data** -Element in der Datei RSReportDesigner.config.</span><span class="sxs-lookup"><span data-stu-id="9b8d0-113">Locate the **Data** element in the RSReportDesigner.config file.</span></span> <span data-ttu-id="9b8d0-114">In folgendem Verzeichnis muss ein Eintrag für Ihre neu erstellte Datenverarbeitungserweiterung erstellt werden:</span><span class="sxs-lookup"><span data-stu-id="9b8d0-114">An entry for your newly created data processing extension should be made in the following location:</span></span>  
  
    ```  
    <Extensions>  
       <Data>  
          <Your extension configuration information goes here>  
       </Data>  
    </Extensions>  
    ```  
  
4.  <span data-ttu-id="9b8d0-115">Fügen Sie einen Eintrag für die Datenverarbeitungs Erweiterung hinzu, der ein **Erweiterungs** Element mit Werten für die `Name` `Type` Attribute, und enthält `Visible` .</span><span class="sxs-lookup"><span data-stu-id="9b8d0-115">Add an entry for your data processing extension which includes an **Extension** element with values for the `Name`, `Type`, and `Visible` attributes.</span></span> <span data-ttu-id="9b8d0-116">Der Eintrag könnte folgendermaßen aussehen:</span><span class="sxs-lookup"><span data-stu-id="9b8d0-116">Your entry might look like the following:</span></span>  
  
    ```  
    <Extension Name="ExtensionName" Type="CompanyName.ExtensionName.MyConnectionClass, AssemblyName" />  
    ```  
  
     <span data-ttu-id="9b8d0-117">Der Wert für `Name` ist der eindeutige Name der Datenverarbeitungserweiterung.</span><span class="sxs-lookup"><span data-stu-id="9b8d0-117">The value for `Name` is the unique name of the data processing extension.</span></span> <span data-ttu-id="9b8d0-118">Der Wert für `Type` ist eine durch Trennzeichen getrennte Liste, die einen Eintrag für den vollqualifizierten Namespace der Klasse enthält, welche die Schnittstellen <xref:Microsoft.ReportingServices.Interfaces.IExtension> und <xref:Microsoft.ReportingServices.DataProcessing.IDbConnection> implementiert, gefolgt vom Namen der Assembly (ohne die Dateierweiterung .dll).</span><span class="sxs-lookup"><span data-stu-id="9b8d0-118">The value for `Type` is a comma-separated list that includes an entry for the fully qualified namespace of your class that implements the <xref:Microsoft.ReportingServices.Interfaces.IExtension> and <xref:Microsoft.ReportingServices.DataProcessing.IDbConnection> interfaces, followed by the name of your assembly (not including the .dll file extension).</span></span> <span data-ttu-id="9b8d0-119">Standardmäßig sind Datenverarbeitungserweiterungen sichtbar.</span><span class="sxs-lookup"><span data-stu-id="9b8d0-119">By default, data processing extensions are visible.</span></span> <span data-ttu-id="9b8d0-120">Wenn Sie eine Erweiterung von Benutzeroberflächen ausblenden möchten, z. b. Berichts-Designer, fügen Sie `Visible` dem **Erweiterungs** Element ein-Attribut hinzu, und legen Sie es auf fest `false` .</span><span class="sxs-lookup"><span data-stu-id="9b8d0-120">To hide an extension from user interfaces, such as Report Designer, add a `Visible` attribute to the **Extension** element, and set it to `false`.</span></span>  
  
5.  <span data-ttu-id="9b8d0-121">Zuletzt müssen Sie eine Codegruppe für die benutzerdefinierte Assembly hinzufügen, die die Berechtigung **FullTrust** für Ihre Erweiterung erteilt.</span><span class="sxs-lookup"><span data-stu-id="9b8d0-121">Finally, add a code group for your custom assembly that grants **FullTrust** permission for your extension.</span></span> <span data-ttu-id="9b8d0-122">Hierzu fügen Sie die Codegruppe zur Datei rspreviewpolicy.config hinzu, die sich standardmäßig im Verzeichnis C:\Programme\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies befindet.</span><span class="sxs-lookup"><span data-stu-id="9b8d0-122">You do this by adding the code group to the rspreviewpolicy.config file located by default in C:\Program Files\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies.</span></span> <span data-ttu-id="9b8d0-123">Die Codegruppe kann folgendermaßen aussehen:</span><span class="sxs-lookup"><span data-stu-id="9b8d0-123">Your code group might look like the following:</span></span>  
  
    ```  
    <CodeGroup class="UnionCodeGroup"  
       version="1"  
       PermissionSetName="FullTrust"  
       Name="MyExtensionCodeGroup"  
       Description="Code group for my data processing extension">  
          <IMembershipCondition class="UrlMembershipCondition"  
             version="1"  
             Url="C:\Program Files\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies\MyExtensionAssembly.dll"  
           />  
    </CodeGroup>  
    ```  
  
 <span data-ttu-id="9b8d0-124">Die URL-Mitgliedschaft ist eine der vielen Mitgliedschaftsbedingungen, die Sie für die Datenverarbeitungserweiterung auswählen können.</span><span class="sxs-lookup"><span data-stu-id="9b8d0-124">URL membership is only one of many membership conditions you might choose for your data processing extension.</span></span> <span data-ttu-id="9b8d0-125">Weitere Informationen zur Codezugriffssicherheit in [!INCLUDE[ssRSversion2005](../../../includes/ssrsversion2005-md.md)] finden Sie unter [Sichere Entwicklung (Reporting Services)](../secure-development/secure-development-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="9b8d0-125">For more information about code access security in [!INCLUDE[ssRSversion2005](../../../includes/ssrsversion2005-md.md)], see [Secure Development &#40;Reporting Services&#41;](../secure-development/secure-development-reporting-services.md)</span></span>  
  
## <a name="generic-query-designer"></a><span data-ttu-id="9b8d0-126">Standardabfrage-Designer</span><span class="sxs-lookup"><span data-stu-id="9b8d0-126">Generic Query Designer</span></span>  
 <span data-ttu-id="9b8d0-127">Der Berichts-Designer enthält einen Standardabfrage-Designer, den Sie zusammen mit den benutzerdefinierten Datenverarbeitungserweiterungen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="9b8d0-127">Report Designer provides a generic query designer that you can use with custom data processing extensions.</span></span> <span data-ttu-id="9b8d0-128">Dieser Designer besteht aus zwei Bereichen: dem Abfragebereich und dem Ergebnisbereich.</span><span class="sxs-lookup"><span data-stu-id="9b8d0-128">This designer consists of two panes: a query pane and a results pane.</span></span> <span data-ttu-id="9b8d0-129">Sie können den Standard-Designer verwenden, um Abfragen zu schreiben, die nicht von der grafischen Oberfläche unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="9b8d0-129">You can use the generic designer to write queries that are not supported by the graphical interface.</span></span> <span data-ttu-id="9b8d0-130">Im Gegensatz zum grafischen Abfrage-Designer wird die Abfragesyntax vom Standardabfrage-Designer nicht überprüft und die Abfrage nicht umstrukturiert.</span><span class="sxs-lookup"><span data-stu-id="9b8d0-130">Unlike the graphical query designer, the generic query designer does not check query syntax or restructure the query.</span></span>  
  
#### <a name="to-enable-the-generic-query-designer-for-a-custom-extension"></a><span data-ttu-id="9b8d0-131">So aktivieren Sie den Standardabfrage-Designer für eine benutzerdefinierte Erweiterung</span><span class="sxs-lookup"><span data-stu-id="9b8d0-131">To enable the generic query designer for a custom extension</span></span>  
  
-   <span data-ttu-id="9b8d0-132">Fügen Sie den folgenden Eintrag in der RSReportDesigner.config-Datei unter dem **Designer** -Element hinzu, und ersetzen `Name` Sie dabei das-Attribut durch den Namen, den Sie in vorherigen Einträgen angegeben haben</span><span class="sxs-lookup"><span data-stu-id="9b8d0-132">Add the following entry to the RSReportDesigner.config file under the **Designer** element, replacing the `Name` attribute with the name that you provided in previous entries.</span></span>  
  
    ```  
    <Extension Name="ExtensionName" Type="Microsoft.ReportingServices.QueryDesigners.GenericQueryDesigner,Microsoft.ReportingServices.QueryDesigners"/>  
    ```  
  
## <a name="verifying-the-deployment"></a><span data-ttu-id="9b8d0-133">Überprüfen der Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="9b8d0-133">Verifying the Deployment</span></span>  
 <span data-ttu-id="9b8d0-134">Sie können die Bereitstellung erst überprüfen, wenn Sie alle Instanzen von [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] auf Ihrem lokalen Computer geschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="9b8d0-134">Before you can verify deployment, you must close all instances of [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] on your local computer.</span></span> <span data-ttu-id="9b8d0-135">Wenn Sie alle aktuellen Sitzungen beendet haben, können Sie überprüfen, ob die Datenverarbeitungserweiterung erfolgreich für den Berichts-Designer bereitgestellt wurde, indem Sie in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] ein neues Berichtsprojekt erstellen.</span><span class="sxs-lookup"><span data-stu-id="9b8d0-135">After you have ended all current sessions, you can verify whether your data processing extension was deployed successfully to Report Designer by creating a new report project in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span></span> <span data-ttu-id="9b8d0-136">Die Erweiterung sollte beim Erstellen eines neuen Datasets für den Bericht in der Liste der verfügbaren Datenquellentypen aufgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9b8d0-136">Your extension should be included in the list of available data source types when you create a new data set for your report.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b8d0-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9b8d0-137">See Also</span></span>  
 <span data-ttu-id="9b8d0-138">[Bereitstellen von Datenverarbeitungserweiterungen](deploying-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="9b8d0-138">[Deploying a Data Processing Extension](deploying-a-data-processing-extension.md) </span></span>  
 <span data-ttu-id="9b8d0-139">[Erweiterungen für Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="9b8d0-139">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 <span data-ttu-id="9b8d0-140">[Implementieren von Datenverarbeitungserweiterungen](implementing-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="9b8d0-140">[Implementing a Data Processing Extension](implementing-a-data-processing-extension.md) </span></span>  
 [<span data-ttu-id="9b8d0-141">Reporting Services Extension Library (Reporting Services-Erweiterungsbibliothek)</span><span class="sxs-lookup"><span data-stu-id="9b8d0-141">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
