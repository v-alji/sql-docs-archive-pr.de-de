---
title: Anpassen der Parameter für Renderingerweiterungen in der Datei „RSReportServer.config“ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- configuration options [Reporting Services]
- DeviceInfo settings
- rendering extensions [Reporting Services], overriding behaviors
- parameters [Reporting Services], report rendering
- overriding report rendering behavior
- extensions [Reporting Services], rendering
ms.assetid: 3bf7ab2b-70bb-41c8-acda-227994d15aed
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 35a01e12fa4016d03717b008e4241c3be5e55236
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725317"
---
# <a name="customize-rendering-extension-parameters-in-rsreportserverconfig"></a><span data-ttu-id="43007-102">Anpassen der Parameter für Renderingerweiterungen in der Datei RSReportServer.config</span><span class="sxs-lookup"><span data-stu-id="43007-102">Customize Rendering Extension Parameters in RSReportServer.Config</span></span>
  <span data-ttu-id="43007-103">Sie können in der RSReportServer-Konfigurationsdatei Parameter für Renderingerweiterungen angeben, um das standardmäßige Rendern von Berichten zu überschreiben, die auf einem [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Berichtsserver ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="43007-103">You can specify rendering extension parameters in the RSReportServer configuration file to override default report rendering behavior for reports that run on a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] report server.</span></span> <span data-ttu-id="43007-104">Sie können die Parameter für Renderingerweiterungen ändern, um Folgendes zu bewirken:</span><span class="sxs-lookup"><span data-stu-id="43007-104">You can modify rendering extension parameters to achieve the following objectives:</span></span>  
  
-   <span data-ttu-id="43007-105">Ändern der Anzeige des Renderingerweiterungsnamens in der Exportliste der Berichtssymbolleiste (z. B. Ändern von "Webarchiv" in "MHTML") oder Lokalisieren des Namens in eine andere Sprache.</span><span class="sxs-lookup"><span data-stu-id="43007-105">Change how the rendering extension name appears in the Export list of the report toolbar (for example, to change "Web archive" to "MHTML"), or localize the name to a different language.</span></span>  
  
-   <span data-ttu-id="43007-106">Erstellen mehrerer Instanzen derselben Renderingerweiterung, um verschiedene Berichtspräsentationsoptionen zu unterstützen (z. B. Darstellung einer Bildrenderingerweiterung im Hoch- und im Querformat).</span><span class="sxs-lookup"><span data-stu-id="43007-106">Create multiple instances of the same rendering extension to support different report presentation options (for example, a portrait and landscape mode version of the Image rendering extension).</span></span>  
  
-   <span data-ttu-id="43007-107">Ändern der standardmäßigen Renderingerweiterungsparameter, um verschieden Werte zu verwenden (beispielsweise wird für die Bildrenderingerweiterung TIFF als Standardausgabeformat verwendet; sie können die Erweiterungsparameter so ändern, dass stattdessen EMF verwendet wird).</span><span class="sxs-lookup"><span data-stu-id="43007-107">Change the default rendering extension parameters to use different values (for example, the Image rendering extension uses TIFF as the default output format; you can modify the extension parameters to use EMF instead).</span></span>  
  
 <span data-ttu-id="43007-108">Eine Änderung der Parameter für Renderingerweiterungen wirkt sich nur auf die Renderingvorgänge auf dem Berichtsserver aus.</span><span class="sxs-lookup"><span data-stu-id="43007-108">Changing the rendering extension parameters only affects rendering operations on the report server.</span></span> <span data-ttu-id="43007-109">Sie können die Renderingerweiterungseinstellungen in der Berichtsvorschau im Berichts-Designer nicht überschreiben.</span><span class="sxs-lookup"><span data-stu-id="43007-109">You cannot override rendering extension settings in report preview in Report Designer.</span></span>  
  
 <span data-ttu-id="43007-110">Die Angabe von Parametern für Renderingerweiterungen in den Konfigurationsdateien wirkt sich global auf Renderingerweiterungen aus.</span><span class="sxs-lookup"><span data-stu-id="43007-110">Specifying rendering extension parameters in the configuration files affects rendering extensions globally.</span></span> <span data-ttu-id="43007-111">Die Einstellungen in den Konfigurationsdateien werden bei Verwendung einer bestimmten Renderingerweiterung statt der Standardwerte verwendet.</span><span class="sxs-lookup"><span data-stu-id="43007-111">The settings in the configuration files are used in place of default values whenever a particular rendering extension is used.</span></span> <span data-ttu-id="43007-112">Wenn Sie Renderingerweiterungsparameter für einen bestimmten Bericht oder Rendervorgang festlegen möchten, müssen Sie die Geräteinformationen entweder programmgesteuert mithilfe der <xref:ReportExecution2005.ReportExecutionService.Render%2A> -Methode angeben oder durch Angabe der Geräteinformationseinstellungen für eine Berichts-URL.</span><span class="sxs-lookup"><span data-stu-id="43007-112">If you want to set rendering extension parameters for a specific report or render operation, you must specify device information programmatically using the <xref:ReportExecution2005.ReportExecutionService.Render%2A> method or by specifying device information settings on a report URL.</span></span> <span data-ttu-id="43007-113">Weitere Informationen zum Angeben von Geräteinformationseinstellungen für einen Rendervorgang und zum Anzeigen der vollständigen Liste der Geräteinformationseinstellungen finden Sie unter [Übergeben von Geräteinformationseinstellungen an Renderingerweiterungen](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="43007-113">For more information about specifying device information settings for a render operation, and to view the complete list of device information settings, see [Passing Device Information Settings to Rendering Extensions](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md).</span></span>  
  
## <a name="finding-and-modifying-rsreportserverconfig"></a><span data-ttu-id="43007-114">Suchen und Ändern von RSReportServer.config</span><span class="sxs-lookup"><span data-stu-id="43007-114">Finding and Modifying RSReportServer.config</span></span>  
 <span data-ttu-id="43007-115">Konfigurationseinstellungen für Berichtsausgabeformate werden als Renderingerweiterungsparameter in der Datei RSReportServer.config angegeben.</span><span class="sxs-lookup"><span data-stu-id="43007-115">Configuration settings for report output formats are specified as rendering extension parameters in the RSReportServer.config file.</span></span> <span data-ttu-id="43007-116">Wenn Sie Parameter für Renderingerweiterungen in den Konfigurationsdateien angeben möchten, müssen Sie wissen, wie die XML-Strukturen definiert werden, die Renderingparameter festlegen.</span><span class="sxs-lookup"><span data-stu-id="43007-116">To specify rendering extension parameters in the configuration files, you must know how to define the XML structures that set rendering parameters.</span></span> <span data-ttu-id="43007-117">Es stehen zwei XML-Strukturen zur Verfügung, die geändert werden können:</span><span class="sxs-lookup"><span data-stu-id="43007-117">There are two XML structures that you can modify:</span></span>  
  
-   <span data-ttu-id="43007-118">Das `OverrideNames`-Element definiert den Anzeigenamen und die Sprache der Renderingerweiterung.</span><span class="sxs-lookup"><span data-stu-id="43007-118">The `OverrideNames` element defines the display name and language of the rendering extension.</span></span>  
  
-   <span data-ttu-id="43007-119">Die `DeviceInfo`-XML-Struktur definiert die von einer Renderingerweiterung verwendeten Geräteinformationseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="43007-119">The `DeviceInfo` XML structure defines the device information settings that are used by a rendering extension.</span></span> <span data-ttu-id="43007-120">Die meisten Parameter für Renderingerweiterungen werden als Geräteinformationseinstellungen angegeben.</span><span class="sxs-lookup"><span data-stu-id="43007-120">Most rendering extension parameters are specified as device information settings.</span></span>  
  
 <span data-ttu-id="43007-121">Sie können die Datei mithilfe eines Text-Editors ändern.</span><span class="sxs-lookup"><span data-stu-id="43007-121">You can use a text editor to modify the file.</span></span> <span data-ttu-id="43007-122">Die Datei RSReportServer.config befindet sich im Ordner \Reporting Services\Report Server\Bin.</span><span class="sxs-lookup"><span data-stu-id="43007-122">The RSReportServer.config file can be found in the \Reporting Services\Report Server\Bin folder.</span></span> <span data-ttu-id="43007-123">Weitere Informationen zum Ändern von Konfigurationsdateien finden Sie unter [Ändern einer Reporting Services-Konfigurationsdatei (RSreportserver.config)](report-server/modify-a-reporting-services-configuration-file-rsreportserver-config.md).</span><span class="sxs-lookup"><span data-stu-id="43007-123">For more information about modifying configuration files, see [Modify a Reporting Services Configuration File &#40;RSreportserver.config&#41;](report-server/modify-a-reporting-services-configuration-file-rsreportserver-config.md).</span></span>  
  
## <a name="changing-the-display-name"></a><span data-ttu-id="43007-124">Ändern des Anzeigenamens</span><span class="sxs-lookup"><span data-stu-id="43007-124">Changing the Display Name</span></span>  
 <span data-ttu-id="43007-125">Der Anzeigename für eine Renderingerweiterung wird in der Exportliste der Berichtssymbolleiste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="43007-125">The display name for a rendering extension appears in the Export list of the report toolbar.</span></span> <span data-ttu-id="43007-126">Zu den Standardanzeigenamen gehören unter anderem Webarchiv, TIFF-Datei und Acrobat-Datei (PDF-Datei).</span><span class="sxs-lookup"><span data-stu-id="43007-126">Examples of default display names include Web archive, TIFF file, and Acrobat (PDF) file.</span></span> <span data-ttu-id="43007-127">Sie können den Standardanzeigenamen durch einen benutzerdefinierten Wert ersetzen, indem Sie in den Konfigurationsdateien das `OverrideNames`-Element angeben.</span><span class="sxs-lookup"><span data-stu-id="43007-127">You can replace the default display name with a custom value by specifying the `OverrideNames` element in the configuration files.</span></span> <span data-ttu-id="43007-128">Darüber hinaus können Sie das `OverrideNames`-Element verwenden, um die einzelnen Instanzen in der Exportliste voneinander zu unterscheiden, wenn Sie zwei Instanzen für eine einzelne Renderingerweiterung definieren.</span><span class="sxs-lookup"><span data-stu-id="43007-128">In addition, if you are defining two instances of a single rendering extension, you can use the `OverrideNames` element to distinguish each instance in the Export list.</span></span>  
  
 <span data-ttu-id="43007-129">Da die Anzeigenamen lokalisiert werden, müssen Sie das `Language`-Attribut festlegen, wenn Sie den Standardanzeigenamen durch einen benutzerdefinierten Wert ersetzen.</span><span class="sxs-lookup"><span data-stu-id="43007-129">Because display names are localized, you must set the `Language` attribute if you are replacing the default display name with a custom value.</span></span> <span data-ttu-id="43007-130">Andernfalls werden die von Ihnen angegebenen Namen ignoriert.</span><span class="sxs-lookup"><span data-stu-id="43007-130">Otherwise, any name that you specify will be ignored.</span></span> <span data-ttu-id="43007-131">Der von Ihnen festgelegte Sprachwert muss für den Berichtsservercomputer gültig sein.</span><span class="sxs-lookup"><span data-stu-id="43007-131">The language value that you set must be valid for the report server computer.</span></span> <span data-ttu-id="43007-132">Wenn der Berichtsserver beispielsweise mit einem französischen Betriebssystem ausgeführt wird, sollten Sie als Attributwert "fr-FR" angeben.</span><span class="sxs-lookup"><span data-stu-id="43007-132">For example, if the report server is running on a French operating system, you should specify "fr-FR" as the attribute value.</span></span>  
  
 <span data-ttu-id="43007-133">Im folgenden Beispiel wird dargestellt, wie Sie einen benutzerdefinierten Namen auf einem englischen Berichtsserver bereitstellen:</span><span class="sxs-lookup"><span data-stu-id="43007-133">The following example illustrates how to provide a custom name on an English report server:</span></span>  
  
```  
<Extension Name="XML" Type="Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport,Microsoft.ReportingServices.DataRendering">  
   <OverrideNames>  
     <Name Language="en-US">My Custom Display Name for XML Rendering</Name>  
   </OverrideNames>  
</Extension>  
```  
  
## <a name="changing-device-information-settings"></a><span data-ttu-id="43007-134">Ändern der Geräteinformationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="43007-134">Changing Device Information Settings</span></span>  
 <span data-ttu-id="43007-135">Wenn Sie die standardmäßigen Geräteinformationseinstellungen ändern möchten, die von einer bereits auf dem Berichtsserver bereitgestellten Renderingerweiterung verwendet werden, müssen Sie die `DeviceInfo`-XML-Struktur in die Konfigurationsdateien eingeben.</span><span class="sxs-lookup"><span data-stu-id="43007-135">To modify default device information settings that are used by a rendering extension that is already deployed on your report server, you must type the `DeviceInfo` XML structure into the configuration files.</span></span> <span data-ttu-id="43007-136">Jede Renderingerweiterung unterstützt Geräteinformationseinstellungen, die für die jeweilige Erweiterung eindeutig sind.</span><span class="sxs-lookup"><span data-stu-id="43007-136">Every rendering extension supports device information settings that are unique to that extension.</span></span> <span data-ttu-id="43007-137">Gehen Sie unter [Übergeben von Geräteinformationseinstellungen an Renderingerweiterungen](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md), um eine vollständige Liste von Geräteinformationseinstellungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="43007-137">To view the complete list of device information settings, see [Passing Device Information Settings to Rendering Extensions](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md).</span></span>  
  
 <span data-ttu-id="43007-138">Im folgenden Beispiel wird die XML-Struktur und -Syntax veranschaulicht, mit der die Standardeinstellungen für die Bildrenderingerweiterung geändert werden:</span><span class="sxs-lookup"><span data-stu-id="43007-138">The following example provides an illustration of the XML structure and syntax that modifies the default settings of the Image rendering extension:</span></span>  
  
```  
<Render>  
    <Extension Name="IMAGE (EMF)" Type="Microsoft.ReportingServices.Rendering.ImageRenderer.ImageRenderer,Microsoft.ReportingServices.ImageRendering">  
        <OverrideNames>  
            <Name Language="en-US">Image (EMF)</Name>  
        </OverrideNames>  
        <Configuration>  
            <DeviceInfo>  
                <ColorDepth>32</ColorDepth>  
                <DpiX>300</DpiX>  
                <DpiY>300</DpiY>  
                <OutputFormat>EMF</OutputFormat>  
            </DeviceInfo>  
        </Configuration>  
    </Extension>  
</Render>  
```  
  
## <a name="configuring-multiple-entries-for-a-rendering-extension"></a><span data-ttu-id="43007-139">Konfigurieren mehrerer Einträge für eine Renderingerweiterung</span><span class="sxs-lookup"><span data-stu-id="43007-139">Configuring Multiple Entries for a Rendering Extension</span></span>  
 <span data-ttu-id="43007-140">Sie können mehrere Instanzen derselben Renderingerweiterung erstellen, damit verschiedene Berichtspräsentationsoptionen unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="43007-140">You can create multiple instances of the same rendering extension to support different report presentation options.</span></span> <span data-ttu-id="43007-141">Die von Ihnen definierten Instanzen können verschiedene Kombinationen der Parameterwerte aufweisen.</span><span class="sxs-lookup"><span data-stu-id="43007-141">Each instance that you define can have a different combination of parameter values.</span></span> <span data-ttu-id="43007-142">Stellen Sie beim Definieren neuer Instanzen einer vorhandenen Renderingerweiterung Folgendes sicher:</span><span class="sxs-lookup"><span data-stu-id="43007-142">When defining new instances of an existing rendering extension, be sure to do the following:</span></span>  
  
-   <span data-ttu-id="43007-143">Geben Sie einen eindeutigen Namen für die Erweiterung an.</span><span class="sxs-lookup"><span data-stu-id="43007-143">Specify a unique name for the extension.</span></span>  
  
     <span data-ttu-id="43007-144">Jede Instanz muss über einen eindeutigen Wert für das `Name`-Attribut verfügen.</span><span class="sxs-lookup"><span data-stu-id="43007-144">Each instance must have a unique value for the `Name` attribute.</span></span> <span data-ttu-id="43007-145">Im folgenden Beispiel werden die Namen "IMAGE (EMF Landscape)" und "IMAGE (EMF Portrait)" verwendet, um die beiden Instanzen voneinander unterscheiden zu können.</span><span class="sxs-lookup"><span data-stu-id="43007-145">The following example uses the names "IMAGE (EMF Landscape)" and "IMAGE (EMF Portrait)" to distinguish between the two instances.</span></span>  
  
     <span data-ttu-id="43007-146">Gehen Sie beim Ändern des Namens für eine bereits bereitgestellte Renderingerweiterung mit Bedacht vor.</span><span class="sxs-lookup"><span data-stu-id="43007-146">Use caution when changing the name of a rendering extension that is already deployed.</span></span> <span data-ttu-id="43007-147">Entwickler, die Renderingerweiterungen programmgesteuert angeben, verwenden den Erweiterungsnamen zur Identifizierung der für einen bestimmten Rendervorgang zu verwendenden Instanz.</span><span class="sxs-lookup"><span data-stu-id="43007-147">Developers who specify rendering extensions programmatically use the extension name to identify which instance to use for a particular render operation.</span></span> <span data-ttu-id="43007-148">Stellen Sie sicher, dass der Entwickler informiert wird, sobald Sie einen vorhandenen Erweiterungsnamen ändern oder einen neuen hinzufügen, wenn Sie eine benutzerdefinierte [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Anwendung auf Ihrem Berichtsserver ausführen.</span><span class="sxs-lookup"><span data-stu-id="43007-148">If you are running custom [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] applications on your report server, make sure that the developer knows if you modify an existing extension name or add a new one.</span></span>  
  
-   <span data-ttu-id="43007-149">Geben Sie einen eindeutigen Anzeigenamen an, damit Benutzer die Unterschiede zwischen den einzelnen Ausgabeformaten nachvollziehen können.</span><span class="sxs-lookup"><span data-stu-id="43007-149">Specify a unique display name so that users can understand the differences for each output format.</span></span>  
  
     <span data-ttu-id="43007-150">Wenn Sie mehrere Versionen derselben Erweiterung konfigurieren, können Sie für jede Version einen eindeutigen Namen verwenden, indem Sie einen Wert für `OverrideNames` angeben.</span><span class="sxs-lookup"><span data-stu-id="43007-150">If you are configuring multiple versions of the same extension, you can give each version a unique name by providing a value for `OverrideNames`.</span></span> <span data-ttu-id="43007-151">Andernfalls weisen alle Versionen der Erweiterung in der Exportoptionenliste auf der Berichtssymbolleiste denselben Namen auf.</span><span class="sxs-lookup"><span data-stu-id="43007-151">Otherwise, all versions of the extension will appear to have the same name in the Export options list on the report toolbar.</span></span>  
  
 <span data-ttu-id="43007-152">Im folgenden Beispiel wird die Verwendung der standardmäßigen Bildrenderingerweiterung veranschaulicht (wobei das Ausgabeformat TIFF erstellt wird), um die EMF im Hochformat auszugeben, sowie eine zweite Instanz, mit der Berichte als EMF im Querformat ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="43007-152">The following example illustrates how to use the default Image rendering extension (which produces TIFF output) to output EMF in Portrait mode alongside a second instance that outputs reports in EMF in Landscape mode.</span></span> <span data-ttu-id="43007-153">Beachten Sie, dass die einzelnen Erweiterungsnamen eindeutig sind.</span><span class="sxs-lookup"><span data-stu-id="43007-153">Notice that each extension name is unique.</span></span> <span data-ttu-id="43007-154">Achten Sie beim Testen dieses Beispiels darauf, dass Sie Berichte auswählen, die keine interaktiven Funktionen wie Optionen zum Ein- und Ausblenden, Matrizen oder Drillthroughlinks enthalten (interaktive Funktionen können in Bildrenderingerweiterungen nicht ausgeführt werden).</span><span class="sxs-lookup"><span data-stu-id="43007-154">When testing this example, remember to choose reports that do not contain interactive features such as show/hide options, matrices, or drillthrough links (interactive features do not work in the Image rendering extension):</span></span>  
  
```  
<Render>  
    <Extension Name="IMAGE (EMF Landscape)" Type="Microsoft.ReportingServices.Rendering.ImageRenderer.ImageRenderer,Microsoft.ReportingServices.ImageRendering">  
        <OverrideNames>  
            <Name Language="en-US">EMF in Landscape Mode</Name>  
        </OverrideNames>  
        <Configuration>  
            <DeviceInfo>  
                <OutputFormat>EMF</OutputFormat>  
                <PageHeight>8.5in</PageHeight>  
                <PageWidth>11in</PageWidth>  
            </DeviceInfo>  
        </Configuration>  
    </Extension>  
    <Extension Name="IMAGE (EMF Portrait)" Type="Microsoft.ReportingServices.Rendering.ImageRenderer.ImageRenderer,Microsoft.ReportingServices.ImageRendering">  
        <OverrideNames>  
            <Name Language="en-US">EMF in Portait Mode</Name>  
        </OverrideNames>  
        <Configuration>  
            <DeviceInfo>  
                <OutputFormat>EMF</OutputFormat>  
                <PageHeight>11in</PageHeight>  
                <PageWidth>8.5in</PageWidth>  
            </DeviceInfo>  
        </Configuration>  
    </Extension>  
</Render>  
```  
  
## <a name="see-also"></a><span data-ttu-id="43007-155">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="43007-155">See Also</span></span>  
 <span data-ttu-id="43007-156">[RSReportServer-Konfigurationsdatei](report-server/rsreportserver-config-configuration-file.md) </span><span class="sxs-lookup"><span data-stu-id="43007-156">[RSReportServer Configuration File](report-server/rsreportserver-config-configuration-file.md) </span></span>  
 <span data-ttu-id="43007-157">[RSReportDesigner-Konfigurationsdatei](report-server/rsreportdesigner-configuration-file.md) </span><span class="sxs-lookup"><span data-stu-id="43007-157">[RSReportDesigner Configuration File](report-server/rsreportdesigner-configuration-file.md) </span></span>  
 <span data-ttu-id="43007-158">[CSV Device Information Settings (CSV-Geräteinformationseinstellungen)](csv-device-information-settings.md) </span><span class="sxs-lookup"><span data-stu-id="43007-158">[CSV Device Information Settings](csv-device-information-settings.md) </span></span>  
 <span data-ttu-id="43007-159">[Excel Device Information Settings (Geräteinformationseinstellungen für Excel)](excel-device-information-settings.md) </span><span class="sxs-lookup"><span data-stu-id="43007-159">[Excel Device Information Settings](excel-device-information-settings.md) </span></span>  
 <span data-ttu-id="43007-160">[HTML-Geräteinformationseinstellungen](html-device-information-settings.md) </span><span class="sxs-lookup"><span data-stu-id="43007-160">[HTML Device Information Settings](html-device-information-settings.md) </span></span>  
 <span data-ttu-id="43007-161">[Geräteinformationseinstellungen für Bilder](image-device-information-settings.md) </span><span class="sxs-lookup"><span data-stu-id="43007-161">[Image Device Information Settings](image-device-information-settings.md) </span></span>  
 <span data-ttu-id="43007-162">[Geräteinformationseinstellungen für MHTML](mhtml-device-information-settings.md) </span><span class="sxs-lookup"><span data-stu-id="43007-162">[MHTML Device Information Settings](mhtml-device-information-settings.md) </span></span>  
 <span data-ttu-id="43007-163">[PDF Device Information Settings (PDF-Geräteinformationseinstellungen)](pdf-device-information-settings.md) </span><span class="sxs-lookup"><span data-stu-id="43007-163">[PDF Device Information Settings](pdf-device-information-settings.md) </span></span>  
 [<span data-ttu-id="43007-164">XML Device Information Settings (XML-Geräteinformationseinstellungen)</span><span class="sxs-lookup"><span data-stu-id="43007-164">XML Device Information Settings</span></span>](xml-device-information-settings.md)  
  
  
