---
title: Implementieren der IRenderingExtension-Schnittstelle | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- IRenderingExtension interface
- rendering extensions [Reporting Services], IRenderingExtension interface
ms.assetid: 74b2f2b7-6796-42da-ab7d-b05891ad4001
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f57c4aa41ccfed165b69581cbf3917e4dfbb4960
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618530"
---
# <a name="implementing-the-irenderingextension-interface"></a><span data-ttu-id="a8c25-102">Implementieren der IRenderingExtension-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a8c25-102">Implementing the IRenderingExtension Interface</span></span>
  <span data-ttu-id="a8c25-103">Die Renderingerweiterung nimmt die Ergebnisse von einer Berichtsdefinition, die mit den tatsächlichen Daten kombiniert wird, und rendert die resultierenden Daten zu einem Format, das verwendbar ist.</span><span class="sxs-lookup"><span data-stu-id="a8c25-103">The rendering extension takes the results from a report definition that is combined with the actual data and renders the resulting data to a format that is useable.</span></span> <span data-ttu-id="a8c25-104">Die Transformation der kombinierten Daten und der Formatierung wird mit einer Common Language Runtime (CLR)-Klasse ausgeführt, die <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension> implementiert.</span><span class="sxs-lookup"><span data-stu-id="a8c25-104">The transformation of the combined data and formatting is done by using a common language runtime (CLR) class that implements <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension>.</span></span> <span data-ttu-id="a8c25-105">Dies wandelt das Objektmodell in ein Ausgabeformat um, das durch einen Viewer, Drucker oder ein anderes Ausgabeziel konsumierbar ist.</span><span class="sxs-lookup"><span data-stu-id="a8c25-105">This transforms the object model into an output format that is consumable by a viewer, printer, or other output target.</span></span>  
  
 <span data-ttu-id="a8c25-106"><xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension> verfügt über drei Methoden, die codiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="a8c25-106">The <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension> has three methods that must be coded:</span></span>  
  
-   <span data-ttu-id="a8c25-107"><xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.Render%2A> – rendert den Bericht.</span><span class="sxs-lookup"><span data-stu-id="a8c25-107"><xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.Render%2A> - renders the report.</span></span>  
  
-   <span data-ttu-id="a8c25-108"><xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.RenderStream%2A> – rendert einen bestimmten Datenstrom aus dem Bericht.</span><span class="sxs-lookup"><span data-stu-id="a8c25-108"><xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.RenderStream%2A> - renders a specific stream from the report.</span></span>  
  
-   <span data-ttu-id="a8c25-109"><xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.GetRenderingResource%2A>- ruft weitere Informationen ab, z. B. Symbole, die für den Bericht erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="a8c25-109"><xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.GetRenderingResource%2A> - gets additional information, such as icons, that are required for the report.</span></span>  
  
 <span data-ttu-id="a8c25-110">In den folgenden Abschnitten werden diese Methoden ausführlicher erörtert.</span><span class="sxs-lookup"><span data-stu-id="a8c25-110">The following sections discuss these methods in more detail.</span></span>  
  
## <a name="render-method"></a><span data-ttu-id="a8c25-111">Render-Methode</span><span class="sxs-lookup"><span data-stu-id="a8c25-111">Render Method</span></span>  
 <span data-ttu-id="a8c25-112">Die <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.Render%2A>-Methode enthält Argumente, die folgende Objekte darstellen:</span><span class="sxs-lookup"><span data-stu-id="a8c25-112">The <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.Render%2A> method contains arguments that represent the following objects:</span></span>  
  
-   <span data-ttu-id="a8c25-113">Den *Bericht*, den Sie rendern möchten.</span><span class="sxs-lookup"><span data-stu-id="a8c25-113">The *report* that you want to render.</span></span> <span data-ttu-id="a8c25-114">Dieses Objekt enthält Eigenschaften, Daten und Layoutinformationen für den Bericht.</span><span class="sxs-lookup"><span data-stu-id="a8c25-114">This object contains properties, data, and layout information for the report.</span></span> <span data-ttu-id="a8c25-115">Der Bericht ist der Stamm für die Modellstruktur des Berichtsobjekts.</span><span class="sxs-lookup"><span data-stu-id="a8c25-115">The report is the root of the report object model tree.</span></span>  
  
-   <span data-ttu-id="a8c25-116">Die *ServerParameters*, die das Zeichenfolgen-Wörterbuchobjekt mit den Parametern für den Berichtsserver enthalten, sofern vorhanden.</span><span class="sxs-lookup"><span data-stu-id="a8c25-116">The *ServerParameters* that contain the string dictionary object, with the parameters for the report server, if any.</span></span>  
  
-   <span data-ttu-id="a8c25-117">Der *deviceInfo*-Parameter mit den Geräteeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="a8c25-117">The *deviceInfo* parameter that contain the device settings.</span></span> <span data-ttu-id="a8c25-118">Weitere Informationen finden Sie unter [Übergeben von Geräteinformationseinstellungen an Renderingerweiterungen](../../report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="a8c25-118">For more information, see [Passing Device Information Settings to Rendering Extensions](../../report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md).</span></span>  
  
-   <span data-ttu-id="a8c25-119">Der *clientCapabilities*-Parameter, der ein <xref:System.Collections.Specialized.NameValueCollection>-Wörterbuch enthält, das Informationen über den Client umfasst, für den Sie den Rendervorgang durchführen.</span><span class="sxs-lookup"><span data-stu-id="a8c25-119">The *clientCapabilities* parameter that contains a <xref:System.Collections.Specialized.NameValueCollection> dictionary object that has information about the client to which you are rendering.</span></span>  
  
-   <span data-ttu-id="a8c25-120">*RenderProperties* mit Informationen zum Ergebnis des Rendervorgangs.</span><span class="sxs-lookup"><span data-stu-id="a8c25-120">The *RenderProperties* that contains information about the rendering result.</span></span>  
  
-   <span data-ttu-id="a8c25-121">*createAndRegisterStream* ist eine Delegatfunktion, die aufgerufen wird, damit ein Stream hineingerendert wird.</span><span class="sxs-lookup"><span data-stu-id="a8c25-121">The *createAndRegisterStream* is a delegate function to be called to get a stream to render into.</span></span>  
  
### <a name="deviceinfo-parameter"></a><span data-ttu-id="a8c25-122">deviceInfo-Parameter</span><span class="sxs-lookup"><span data-stu-id="a8c25-122">deviceInfo Parameter</span></span>  
 <span data-ttu-id="a8c25-123">Der *deviceInfo*-Parameter enthält Renderingparameter, nicht Berichtsparameter.</span><span class="sxs-lookup"><span data-stu-id="a8c25-123">The *deviceInfo* parameter contains rendering parameters, not report parameters.</span></span> <span data-ttu-id="a8c25-124">Diese Renderingparameter werden an die Renderingerweiterung übergeben.</span><span class="sxs-lookup"><span data-stu-id="a8c25-124">These rendering parameters are passed to the rendering extension.</span></span> <span data-ttu-id="a8c25-125">Die *deviceInfo*-Werte werden vom Berichtsserver zu einem <xref:System.Collections.Specialized.NameValueCollection>-Objekt konvertiert.</span><span class="sxs-lookup"><span data-stu-id="a8c25-125">The *deviceInfo* values are converted into a <xref:System.Collections.Specialized.NameValueCollection> object by the report server.</span></span> <span data-ttu-id="a8c25-126">Elemente im *deviceInfo*-Parameter werden als Werte behandelt, bei denen die Groß- und Kleinschreibung nicht beachtet wird.</span><span class="sxs-lookup"><span data-stu-id="a8c25-126">Items in the *deviceInfo* parameter are treated as case-insensitive values.</span></span> <span data-ttu-id="a8c25-127">Wenn die Renderinganforderung als Ergebnis des URL-Zugriffs aufgetreten ist, werden die URL-Parameter in Form von `rc:key=value` zu Schlüssel/Wert-Paaren im *deviceInfo*-Wörterbuchobjekt umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="a8c25-127">If the render request came as a result of URL access, the URL parameters in the form `rc:key=value` are converted to key/value pairs in the *deviceInfo* dictionary object.</span></span> <span data-ttu-id="a8c25-128">Der Code für die Browserabfrage enthält folgende Elemente im *clientCapabilities*-Wörterbuch: EcmaScriptVersion, JavaScript, MajorVersion, MinorVersion, Win32, Type und AcceptLanguage.</span><span class="sxs-lookup"><span data-stu-id="a8c25-128">The browser detection code also provides the following items in the *clientCapabilities* dictionary: EcmaScriptVersion, JavaScript, MajorVersion, MinorVersion, Win32, Type, and AcceptLanguage.</span></span> <span data-ttu-id="a8c25-129">Jedes Name/Wert-Paar im *deviceInfo*-Parameter, das nicht von der Renderingerweiterung erkannt wird, wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="a8c25-129">Any name/value pair in the *deviceInfo* parameter that is not understood by the rendering extension is ignored.</span></span> <span data-ttu-id="a8c25-130">Das folgende Codebeispiel zeigt eine <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.GetRenderingResource%2A>-Methode, die Symbole abruft:</span><span class="sxs-lookup"><span data-stu-id="a8c25-130">The following code sample shows a sample <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.GetRenderingResource%2A> method that retrieves icons:</span></span>  
  
```csharp  
public void GetRenderingResource (CreateStream createStreamCallback, NameValueCollection deviceInfo)  
{  
    string[] iconTagValues = deviceInfo.GetValues("Icon");  
    if ((iconTagValues != null) && (iconTagValues.Length > 0) )  
    {  
        // Create a stream to output to.  
        Stream outputStream = createStreamCallback(m_iconResourceName, "gif", null, "image/gif", false);  
        // Get the GIF image for one of the buttons on the toolbar  
        Image requiredImage = (Image) m_resourcemanager.GetObject(m_iconResourceName  
        // Write the image to the output stream  
        requiredImage.Save(outputStream, requiredImage.RawFormat);  
    }  
    return;  
}  
```  
  
## <a name="renderstream-method"></a><span data-ttu-id="a8c25-131">RenderStream-Methode</span><span class="sxs-lookup"><span data-stu-id="a8c25-131">RenderStream Method</span></span>  
 <span data-ttu-id="a8c25-132">Die <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.RenderStream%2A>-Methode rendert einen besonderen Datenstrom aus dem Bericht.</span><span class="sxs-lookup"><span data-stu-id="a8c25-132">The <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.RenderStream%2A> method renders a particular stream from the report.</span></span> <span data-ttu-id="a8c25-133">Alle Datenströme werden während des ersten <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.Render%2A>-Aufrufs erstellt, aber die Ströme werden anfangs nicht zum Client zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a8c25-133">All streams are created during the initial <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.Render%2A> call, but the streams are not returned to the client initially.</span></span> <span data-ttu-id="a8c25-134">Diese Methode wird für Sekundärströme (wie Bilder in HTML-Rendering) oder zusätzliche Seiten einer mehrseitigen Renderingerweiterung (wie Image/EMF) verwendet.</span><span class="sxs-lookup"><span data-stu-id="a8c25-134">This method is used for secondary streams, such as images in HTML rendering, or additional pages of a multi-page rendering extension, such as Image/EMF.</span></span>  
  
## <a name="getrenderingresource-method"></a><span data-ttu-id="a8c25-135">GetRenderingResource-Methode</span><span class="sxs-lookup"><span data-stu-id="a8c25-135">GetRenderingResource Method</span></span>  
 <span data-ttu-id="a8c25-136">Die <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.GetRenderingResource%2A>-Methode ruft die Informationen ab, ohne den kompletten Renderingvorgang für den Bericht auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a8c25-136">The <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.GetRenderingResource%2A> method retrieves the information without executing an entire rendering of the report.</span></span> <span data-ttu-id="a8c25-137">Manchmal benötigt ein Bericht Informationen, die es nicht erfordern, dass der Bericht selbst gerendert wird.</span><span class="sxs-lookup"><span data-stu-id="a8c25-137">There are times when the report requires information that does not require the report itself to be rendered.</span></span> <span data-ttu-id="a8c25-138">Wenn Sie z. b. das Symbol benötigen, das der Renderingerweiterung zugeordnet ist, verwenden Sie den *deviceInfo* -Parameter, der das einzelne Tag enthält **\<Icon>** .</span><span class="sxs-lookup"><span data-stu-id="a8c25-138">For example, if you need the icon associated with the rendering extension, use the *deviceInfo* parameter containing the single tag **\<Icon>**.</span></span> <span data-ttu-id="a8c25-139">In diesen Fällen können Sie die <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.GetRenderingResource%2A>-Methode verwenden.</span><span class="sxs-lookup"><span data-stu-id="a8c25-139">In these cases, you can use the <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.GetRenderingResource%2A> method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8c25-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a8c25-140">See Also</span></span>  
 <span data-ttu-id="a8c25-141">[Implementing a Rendering Extension (Implementieren von Renderingerweiterungen)](implementing-a-rendering-extension.md) </span><span class="sxs-lookup"><span data-stu-id="a8c25-141">[Implementing a Rendering Extension](implementing-a-rendering-extension.md) </span></span>  
 [<span data-ttu-id="a8c25-142">Rendering Extensions Overview (Übersicht über Renderingerweiterungen)</span><span class="sxs-lookup"><span data-stu-id="a8c25-142">Rendering Extensions Overview</span></span>](rendering-extensions-overview.md)  
  
  
