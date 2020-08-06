---
title: URL-Zugriff (SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- URL access [Reporting Services]
- links [Reporting Services], URL access
- URL access [Reporting Services], about URL access
- parameters [Reporting Services], URL access
- report servers [Reporting Services], URL access
- hyperlinks [Reporting Services]
ms.assetid: 52c3f2a3-3d6d-4fee-9c46-83f366919398
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bf44ea3c15c12f37eebf6e89faf4ff3affd64433
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616355"
---
# <a name="url-access-ssrs"></a><span data-ttu-id="5ccaf-102">URL-Zugriff (SSRS)</span><span class="sxs-lookup"><span data-stu-id="5ccaf-102">URL Access (SSRS)</span></span>
  <span data-ttu-id="5ccaf-103">Durch den URL-Zugriff des Berichtsservers in SQL Server Reporting Services (SSRS) können Sie Befehle an den Berichtsserver über eine URL-Anforderung senden.</span><span class="sxs-lookup"><span data-stu-id="5ccaf-103">URL access of the report server in SQL Server Reporting Services (SSRS) enables you to send commands to a report server through a URL request.</span></span> <span data-ttu-id="5ccaf-104">Beispielsweise können Sie das Rendering eines Berichts auf einem Berichtsserver im einheitlichen Modus oder in einer SharePoint-Bibliothek anpassen.</span><span class="sxs-lookup"><span data-stu-id="5ccaf-104">For example, you can customize the rendering of a report on a native mode report server or in a SharePoint library.</span></span> <span data-ttu-id="5ccaf-105">Möglicherweise haben Sie den Bericht unter Verwendung bestimmter Berichtsparameterwerte angezeigt oder eine bestimmte Berichtsseite gelesen, die für Sie von Interesse war.</span><span class="sxs-lookup"><span data-stu-id="5ccaf-105">You may have viewed the report using a specific set of report parameter values, or you may have been viewing a particular page of interest in the report.</span></span> <span data-ttu-id="5ccaf-106">Diese Informationen können mithilfe vordefinierter URL-Zugriffsparameter in der URL gekapselt werden.</span><span class="sxs-lookup"><span data-stu-id="5ccaf-106">You can encapsulate this information in the URL using predefined URL access parameters.</span></span> <span data-ttu-id="5ccaf-107">Außerdem kann die Berichtsverarbeitung auf dem Berichtsserver weiter angepasst werden, indem Sie Parameter für Renderingformate oder für das Erscheinungsbild des Berichts-Viewers einbetten.</span><span class="sxs-lookup"><span data-stu-id="5ccaf-107">You can further customize how the report server processes the report by embedding parameters for rendering formats or for the look and feel of the report viewer.</span></span> <span data-ttu-id="5ccaf-108">Anschließend können Sie diese URL direkt in eine E-Mail oder Webseite einfügen, damit andere Benutzer im Browser auf die gleiche Weise auf den Bericht zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="5ccaf-108">You can then paste this URL directly into an email or Web page to let others to access your report in the same manner in the browser.</span></span>  
  
 <span data-ttu-id="5ccaf-109">Weitere Aktionen, die über den URL-Zugriff ausgeführt werden können:</span><span class="sxs-lookup"><span data-stu-id="5ccaf-109">Other actions you can perform through URL access are:</span></span>  
  
-   <span data-ttu-id="5ccaf-110">Senden von Befehlen an den HTML-Viewer, z. B. zum Anpassen des Erscheinungsbilds</span><span class="sxs-lookup"><span data-stu-id="5ccaf-110">Send commands to the HTML viewer, such as adjusting its look and feel</span></span>  
  
-   <span data-ttu-id="5ccaf-111">Auflisten der untergeordneten Elemente eines Katalogordners</span><span class="sxs-lookup"><span data-stu-id="5ccaf-111">List the children of a catalog folder</span></span>  
  
-   <span data-ttu-id="5ccaf-112">Abrufen der XML-Definition eines Katalogelements</span><span class="sxs-lookup"><span data-stu-id="5ccaf-112">Retrieve the XML definition of a catalog item</span></span>  
  
-   <span data-ttu-id="5ccaf-113">Rendern einer bestimmten Berichtsverlaufs-Momentaufnahme</span><span class="sxs-lookup"><span data-stu-id="5ccaf-113">Render a specific report history snapshot</span></span>  
  
-   <span data-ttu-id="5ccaf-114">Verwalten von Berichtssitzungen</span><span class="sxs-lookup"><span data-stu-id="5ccaf-114">Manage report sessions</span></span>  
  
 <span data-ttu-id="5ccaf-115">Eine vollständige Liste der über URL-Zugriff verfügbaren Befehle und Einstellungen finden Sie unter [URL-Zugriffsparameterreferenz](url-access-parameter-reference.md).</span><span class="sxs-lookup"><span data-stu-id="5ccaf-115">For the complete list of commands and settings available through URL access, see [URL Access Parameter Reference](url-access-parameter-reference.md).</span></span>  
  
## <a name="url-access-concepts"></a><span data-ttu-id="5ccaf-116">Konzepte für den URL-Zugriff</span><span class="sxs-lookup"><span data-stu-id="5ccaf-116">URL Access Concepts</span></span>  
 <span data-ttu-id="5ccaf-117">URL-Anforderungen an den Berichtsserver enthalten Parameter, die vom Berichtsserver verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="5ccaf-117">URL requests to the report server contain parameters that are processed by the report server.</span></span> <span data-ttu-id="5ccaf-118">Wie URL-Anforderungen vom Berichtsserver behandelt werden, hängt von den Parametern, den Parameterpräfixen sowie den Elementtypen ab, die in der URL enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="5ccaf-118">The way in which the report server handles URL requests depends on the parameters, parameter prefixes, and types of items that are included in the URL.</span></span> <span data-ttu-id="5ccaf-119">Berichtsserver-URLs erfüllen die URL-Formatierungsrichtlinien, wie sie vom gemeinsamen Entwurfsstandard des World Wide Web Consortium W3C/IETF vorgeschlagen wurden.</span><span class="sxs-lookup"><span data-stu-id="5ccaf-119">Report server URLs adhere to the URL formatting guidelines as proposed by the joint World Wide Web Consortium W3C/IETF draft standard.</span></span> [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] <span data-ttu-id="5ccaf-120">-URL-Funktionen sind kompatibel mit den meisten Internetbrowsern oder -anwendungen, die Standard-URL-Adressen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="5ccaf-120">URL functionality is compatible with most Internet browsers or applications that support standard URL addressing.</span></span>  
  
### <a name="url-access-syntax"></a><span data-ttu-id="5ccaf-121">URL-Zugriffssyntax</span><span class="sxs-lookup"><span data-stu-id="5ccaf-121">URL Access Syntax</span></span>  
 <span data-ttu-id="5ccaf-122">URL-Anforderungen können mehrere Parameter enthalten, die in beliebiger Reihenfolge aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="5ccaf-122">URL requests can contain multiple parameters that are listed in any order.</span></span> <span data-ttu-id="5ccaf-123">Parameter werden durch das kaufmännische Und-Zeichen (&) getrennt, Name/Wert-Paare werden durch das Gleichheitszeichen (=) getrennt.</span><span class="sxs-lookup"><span data-stu-id="5ccaf-123">Parameters are separated by an ampersand (&) and name/value pairs are separated by an equal sign (=).</span></span>  
  
```  
  
rswebserviceurl  
?  
reportpath  
      [&prefix:param=value]...n]  
  
```  
  
### <a name="syntax-description"></a><span data-ttu-id="5ccaf-124">Syntaxbeschreibung</span><span class="sxs-lookup"><span data-stu-id="5ccaf-124">Syntax Description</span></span>  
 <span data-ttu-id="5ccaf-125">*rswebserviceurl*</span><span class="sxs-lookup"><span data-stu-id="5ccaf-125">*rswebserviceurl*</span></span>  
 <span data-ttu-id="5ccaf-126">Die Webdienst-URL des Berichtsservers.</span><span class="sxs-lookup"><span data-stu-id="5ccaf-126">The Web service URL of the report server.</span></span> <span data-ttu-id="5ccaf-127">Im einheitlichen Modus ist dies die Webdienst-URL der in Konfigurations-Manager für Reporting Services konfigurierten Berichtsserverinstanz. Weitere Informationen finden Sie unter [Konfigurieren von Berichtsserver-URLs (SSRS-Konfigurations-Manager)](install-windows/configure-report-server-urls-ssrs-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="5ccaf-127">For native mode, it is the Web service URL of the report server instance configured in Reporting Services Configuration Manager (see [Configure Report Server URLs  &#40;SSRS Configuration Manager&#41;](install-windows/configure-report-server-urls-ssrs-configuration-manager.md)).</span></span> <span data-ttu-id="5ccaf-128">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="5ccaf-128">For example:</span></span>  
  
```  
http://myrshost/reportserver  
https://machine.adventure-works.com/reportserver_MYNAMEDINSTANCE  
```  
  
 <span data-ttu-id="5ccaf-129">Im integrierten SharePoint-Modus entspricht sie der URL des [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Proxys auf einer in [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]integrierten SharePoint-Website.</span><span class="sxs-lookup"><span data-stu-id="5ccaf-129">For SharePoint integrated mode, it is the URL of the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] proxy at a SharePoint site integrated with [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="5ccaf-130">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="5ccaf-130">For example:</span></span>  
  
```  
http://myspsite/subsite/_vti_bin/reportserver  
```  
  
> [!TIP]  
>  <span data-ttu-id="5ccaf-131">Es ist wichtig, dass die URL die `_vti_bin` -Proxysyntax zur Weiterleitung der Anforderung über SharePoint sowie den [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -HTTP-Proxy enthält.</span><span class="sxs-lookup"><span data-stu-id="5ccaf-131">It is important the URL include the `_vti_bin` proxy syntax to route the request through SharePoint and the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] HTTP proxy.</span></span> <span data-ttu-id="5ccaf-132">Durch den Proxy wird der HTTP-Anforderung Kontext hinzugefügt. Dieser ist erforderlich, damit der Bericht auf Berichtsservern im SharePoint-Modus ordnungsgemäß ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5ccaf-132">The proxy adds some context to the HTTP request, context that is required to ensure proper execution of the report for SharePoint mode report servers.</span></span>  
  
 <span data-ttu-id="5ccaf-133">*pathinfo*</span><span class="sxs-lookup"><span data-stu-id="5ccaf-133">*pathinfo*</span></span>  
 <span data-ttu-id="5ccaf-134">Der relative Pfadname des Elements in der Berichtsserver-Datenbank im einheitlichen Modus oder die vollqualifizierte URL des Elements in einem SharePoint-Katalog.</span><span class="sxs-lookup"><span data-stu-id="5ccaf-134">The relative path name of the item in the native mode report server database, or the fully qualified URL of the item in a SharePoint catalog.</span></span>  
  
 <span data-ttu-id="5ccaf-135">Der Pfad des Katalogelements.</span><span class="sxs-lookup"><span data-stu-id="5ccaf-135">The path of the catalog item.</span></span> <span data-ttu-id="5ccaf-136">Im einheitlichen Modus ist dies der relative Pfad des Elements in der Berichtsserver-Datenbank, der mit einem Schrägstrich (`/`) beginnt.</span><span class="sxs-lookup"><span data-stu-id="5ccaf-136">For native mode, it is the relative path of the item in the report server database, beginning with a slash (`/`).</span></span> <span data-ttu-id="5ccaf-137">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="5ccaf-137">For example:</span></span>  
  
```  
/AdventureWorks 2008R2/Employee_Sales_Summary_2008R2  
```  
  
 <span data-ttu-id="5ccaf-138">Im integrierten SharePoint-Modus ist dies die vollqualifizierte URL des Elements in der SharePoint-Bibliothek, einschließlich der Elementerweiterung.</span><span class="sxs-lookup"><span data-stu-id="5ccaf-138">For SharePoint integrated mode, it is the fully qualified URL of the item in the SharePoint library, including the item extension.</span></span> <span data-ttu-id="5ccaf-139">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="5ccaf-139">For example:</span></span>  
  
```  
http://myspsite/subsite/AdventureWorks 2008R2/Employee_Sales_Summary_2008R2.rdl  
```  
  
 `&`  
 <span data-ttu-id="5ccaf-140">Wird verwendet, um Namen- und Wertpaare von URL-Zugriffsparametern zu trennen.</span><span class="sxs-lookup"><span data-stu-id="5ccaf-140">Used to separate name and value pairs of URL access parameters.</span></span>  
  
 <span data-ttu-id="5ccaf-141">**Präfix**</span><span class="sxs-lookup"><span data-stu-id="5ccaf-141">**prefix**</span></span>  
 <span data-ttu-id="5ccaf-142">Optional.</span><span class="sxs-lookup"><span data-stu-id="5ccaf-142">Optional.</span></span> <span data-ttu-id="5ccaf-143">Ein Präfix für den URL-Zugriffsparameter (z.B. `rs:` oder `rc:`), durch das auf einen bestimmten im Berichtsserver ausgeführten Prozess zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="5ccaf-143">A prefix for the URL access parameter (for example, `rs:` or `rc:`) that accesses a specific process running within the report server.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5ccaf-144">Wenn das Präfix für einen URL-Zugriffsparameter nicht enthalten ist, wird der Parameter vom Berichtsserver als Berichtsparameter verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="5ccaf-144">If a prefix for a URL access parameter is not included, the parameter is processed by the report server as a report parameter.</span></span> <span data-ttu-id="5ccaf-145">Bei Berichtsparametern wird kein Parameterpräfix verwendet und nach Groß-/Kleinschreibung unterschieden.</span><span class="sxs-lookup"><span data-stu-id="5ccaf-145">Report parameters do not use a parameter prefix and are case-sensitive.</span></span>  
  
 <span data-ttu-id="5ccaf-146">**param**</span><span class="sxs-lookup"><span data-stu-id="5ccaf-146">**param**</span></span>  
 <span data-ttu-id="5ccaf-147">Der Name des Parameters.</span><span class="sxs-lookup"><span data-stu-id="5ccaf-147">The parameter name.</span></span>  
  
 <span data-ttu-id="5ccaf-148">*value*</span><span class="sxs-lookup"><span data-stu-id="5ccaf-148">*value*</span></span>  
 <span data-ttu-id="5ccaf-149">URL-Text, der dem Wert des Parameters entspricht, der verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5ccaf-149">URL text corresponding to the value of the parameter being used.</span></span>  
  
 <span data-ttu-id="5ccaf-150">**Hinweis:** Eine Liste der verfügbaren URL-Zugriffsparameter finden Sie unter [URL Access Parameter Reference](url-access-parameter-reference.md).</span><span class="sxs-lookup"><span data-stu-id="5ccaf-150">**Note:** For a list of the available URL access parameters, see [URL Access Parameter Reference](url-access-parameter-reference.md).</span></span> <span data-ttu-id="5ccaf-151">Beispiele für die Übergabe von Berichtsparametern mit der URL finden Sie unter [Pass a Report Parameter Within a URL](pass-a-report-parameter-within-a-url.md).</span><span class="sxs-lookup"><span data-stu-id="5ccaf-151">For examples passing report parameters on the URL, see [Pass a Report Parameter Within a URL](pass-a-report-parameter-within-a-url.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="5ccaf-152">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="5ccaf-152">Related Tasks</span></span>  
  
|<span data-ttu-id="5ccaf-153">Taskbeschreibungen</span><span class="sxs-lookup"><span data-stu-id="5ccaf-153">Task Descriptions</span></span>|<span data-ttu-id="5ccaf-154">Links</span><span class="sxs-lookup"><span data-stu-id="5ccaf-154">Links</span></span>|  
|-----------------------|-----------|  
|<span data-ttu-id="5ccaf-155">Zugreifen auf Berichtserverelemente, z. B. Berichte, freigegebene Datenquellen und Ressourcen</span><span class="sxs-lookup"><span data-stu-id="5ccaf-155">Access report server items, such as reports, shared data sources, and resources.</span></span>|[<span data-ttu-id="5ccaf-156">Access Report Server Items Using URL Access (Zugreifen auf Berichtsserverelemente über den URL-Zugriff)</span><span class="sxs-lookup"><span data-stu-id="5ccaf-156">Access Report Server Items Using URL Access</span></span>](access-report-server-items-using-url-access.md)|  
|<span data-ttu-id="5ccaf-157">Übergeben von Berichtsparametern an einen Bericht</span><span class="sxs-lookup"><span data-stu-id="5ccaf-157">Pass report parameters to a report.</span></span>|[<span data-ttu-id="5ccaf-158">Pass a Report Parameter Within a URL (Übergeben von Berichtsparametern innerhalb einer URL)</span><span class="sxs-lookup"><span data-stu-id="5ccaf-158">Pass a Report Parameter Within a URL</span></span>](pass-a-report-parameter-within-a-url.md)|  
|<span data-ttu-id="5ccaf-159">Festlegen des Gebietsschemas der Berichtsparameter in der URL-Zugriffszeichenfolge, durch die die gebietsschemaspezifische Interpretation von Datumsangaben, Währungen usw. festgelegt wird</span><span class="sxs-lookup"><span data-stu-id="5ccaf-159">Set the locale of the report parameters in the URL access string, which defines the locale-specific interpretations of dates, currencies, and so on.</span></span>|[<span data-ttu-id="5ccaf-160">Set the Language for Report Parameters in a URL (Festlegen der Sprache für Berichtsparameter in einer URL)</span><span class="sxs-lookup"><span data-stu-id="5ccaf-160">Set the Language for Report Parameters in a URL</span></span>](set-the-language-for-report-parameters-in-a-url.md)|  
|<span data-ttu-id="5ccaf-161">Senden spezifischer Einstellungen für Renderingerweiterungen, durch die das Rendern des Berichts angepasst wird</span><span class="sxs-lookup"><span data-stu-id="5ccaf-161">Send rendering extension specific settings that customize how the report is rendered.</span></span>|[<span data-ttu-id="5ccaf-162">Specify Device Information Settings in a URL (Angeben von Geräteinformationseinstellungen in einer URL)</span><span class="sxs-lookup"><span data-stu-id="5ccaf-162">Specify Device Information Settings in a URL</span></span>](specify-device-information-settings-in-a-url.md)|  
|<span data-ttu-id="5ccaf-163">Direktes Exportieren eines Berichts in ein Dateiformat, ohne ihn im Browser anzuzeigen</span><span class="sxs-lookup"><span data-stu-id="5ccaf-163">Export a report directly to a file format without viewing it in the browser.</span></span>|[<span data-ttu-id="5ccaf-164">Export a Report Using URL Access (Exportieren von Berichten über URL-Zugriff)</span><span class="sxs-lookup"><span data-stu-id="5ccaf-164">Export a Report Using URL Access</span></span>](export-a-report-using-url-access.md)|  
|<span data-ttu-id="5ccaf-165">Öffnen eines Berichts und direktes Navigieren zur Position einer Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="5ccaf-165">Open a report and navigate directly to the location of a string.</span></span>|[<span data-ttu-id="5ccaf-166">Search a Report Using URL Access (Suchen eines Berichts mithilfe von URL-Zugriff)</span><span class="sxs-lookup"><span data-stu-id="5ccaf-166">Search a Report Using URL Access</span></span>](search-a-report-using-url-access.md)|  
|<span data-ttu-id="5ccaf-167">Rendern einer bestimmten Berichtsverlaufs-Momentaufnahme</span><span class="sxs-lookup"><span data-stu-id="5ccaf-167">Render a specific report history snapshot.</span></span>|[<span data-ttu-id="5ccaf-168">Render a Report History Snapshot Using URL Access (Rendern von Berichtsverlaufs-Momentaufnahmen mit URL-Zugriff)</span><span class="sxs-lookup"><span data-stu-id="5ccaf-168">Render a Report History Snapshot Using URL Access</span></span>](render-a-report-history-snapshot-using-url-access.md)|  
  
## <a name="see-also"></a><span data-ttu-id="5ccaf-169">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5ccaf-169">See Also</span></span>  
 <span data-ttu-id="5ccaf-170">[Pass a Report Parameter Within a URL](pass-a-report-parameter-within-a-url.md) </span><span class="sxs-lookup"><span data-stu-id="5ccaf-170">[Pass a Report Parameter Within a URL](pass-a-report-parameter-within-a-url.md) </span></span>  
 <span data-ttu-id="5ccaf-171">[URL-Zugriffsparameterverweis](url-access-parameter-reference.md) </span><span class="sxs-lookup"><span data-stu-id="5ccaf-171">[URL Access Parameter Reference](url-access-parameter-reference.md) </span></span>  
 <span data-ttu-id="5ccaf-172">[Integrieren von Reporting Services mit URL-Zugriff](application-integration/integrating-reporting-services-using-url-access.md) </span><span class="sxs-lookup"><span data-stu-id="5ccaf-172">[Integrating Reporting Services Using URL Access](application-integration/integrating-reporting-services-using-url-access.md) </span></span>  
 [<span data-ttu-id="5ccaf-173">Suchen, Anzeigen und Verwalten von Berichten (Berichts-Generator und SSRS )</span><span class="sxs-lookup"><span data-stu-id="5ccaf-173">Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;</span></span>](report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md)  
  
  
