---
title: Verwenden des URL-Zugriffs in einer Webanwendung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- links [Reporting Services], URL access
- URL access [Reporting Services], Web applications
- POST requests
- direct addressing [Reporting Services]
- Web applications [Reporting Services]
- hyperlinks [Reporting Services]
ms.assetid: 39e7918c-ad2d-4ca6-b099-2dd4dbdb83dc
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cd31f76658f8160cbb2a576debc335588f77e72c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607553"
---
# <a name="using-url-access-in-a-web-application"></a><span data-ttu-id="39b8a-102">Verwenden des URL-Zugriffs in einer Webanwendung</span><span class="sxs-lookup"><span data-stu-id="39b8a-102">Using URL Access in a Web Application</span></span>
  <span data-ttu-id="39b8a-103">Der URL-Zugriff in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] wurde speziell konzipiert, um den Zugriff auf einzelne Berichte über ein Netzwerk zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="39b8a-103">URL access in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is specifically designed to enable access to individual reports over a network.</span></span> <span data-ttu-id="39b8a-104">Dieser Zugriffstyp eignet sich am besten, um die Anzeige und Navigation von Berichten in eine benutzerdefinierte Webanwendung zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="39b8a-104">This type of access is best for integrating report viewing and navigation into a custom Web application.</span></span> <span data-ttu-id="39b8a-105">Um den URL-Zugriff in Webanwendungen zu verwenden, können Sie Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="39b8a-105">To use URL access in Web applications, you can:</span></span>  
  
-   <span data-ttu-id="39b8a-106">Richten Sie eine URL von einer Website oder einem Portal an einen bestimmten Berichtsserver.</span><span class="sxs-lookup"><span data-stu-id="39b8a-106">Address a URL to a specific report server from a Web site or portal.</span></span>  
  
-   <span data-ttu-id="39b8a-107">Verwenden Sie eine Formular-POST-Methode, und leiten Sie die Parameter für die Abfragezeichenfolge mithilfe von Formularfeldern an eine Berichtsserver-URL.</span><span class="sxs-lookup"><span data-stu-id="39b8a-107">Use a form POST method and pass query string parameters to a report server URL using form fields.</span></span>  
  
## <a name="url-access-through-direct-addressing"></a><span data-ttu-id="39b8a-108">URL-Zugriff über Direktadressierung</span><span class="sxs-lookup"><span data-stu-id="39b8a-108">URL Access Through Direct Addressing</span></span>  
 <span data-ttu-id="39b8a-109">Um mit einer URL auf einen Berichtsserver oder ein Berichtsserver-Datenbankelement zuzugreifen, geben Sie einfach die URL-Adresse im Webbrowser oder der Webanwendung an.</span><span class="sxs-lookup"><span data-stu-id="39b8a-109">To access a report server or report server database item using a URL, simply provide the URL address from within a Web browser or application.</span></span> <span data-ttu-id="39b8a-110">Sie können auch Parameter für die URL angeben, die das Erscheinungsbild des Berichts oder der Ressource, auf die gerade zugegriffen wird, verändert.</span><span class="sxs-lookup"><span data-stu-id="39b8a-110">You can also supply parameters to the URL that can affect the appearance of the report or resource that is being accessed.</span></span> <span data-ttu-id="39b8a-111">Eine URL kann über die Adressleiste eines Webbrowsers an einen Berichtsserver weiterleiten oder die Quelle eines **IFrame** sein, das Bestandteil einer größeren Webanwendung oder eines Portals ist.</span><span class="sxs-lookup"><span data-stu-id="39b8a-111">A URL can target a report server through the address bar of a Web browser, or a URL can be the source of an **IFrame** that is part of a larger Web application or portal.</span></span> <span data-ttu-id="39b8a-112">Sie können Links zu verschiedenen Webseiten Ihres Portals in die Berichte aufnehmen, außerdem können Sie einen speziellen Frame für den Bericht ansteuern oder ein neues Browserfenster im Prozess öffnen.</span><span class="sxs-lookup"><span data-stu-id="39b8a-112">You can include hyperlinks to reports on various Web pages of your portal, as well as target a specific frame for the report or open a new browser window in the process.</span></span>  
  
 <span data-ttu-id="39b8a-113">Im folgenden Beispiel steuert der Link einen Frame mit dem Namen „main“ an, der sich von dem Frame unterscheiden kann, der den Link enthält.</span><span class="sxs-lookup"><span data-stu-id="39b8a-113">In the following example, the hyperlink targets a frame named "main", which might be different from the one that includes the hyperlink.</span></span> <span data-ttu-id="39b8a-114">Der Link kann ein Teil eines Webportals sein.</span><span class="sxs-lookup"><span data-stu-id="39b8a-114">The hyperlink might be part of Web portal.</span></span>  
  
```  
<a href="http://server/reportserver?/SampleReports/Territory Sales   
Drilldown&rs:Command=Render&rc:LinkTarget=main" target="main" >  
   Click here for the Territory Sales Drilldown sample report  
</a>  
```  
  
 <span data-ttu-id="39b8a-115">Im vorherigen Beispiel wird die **LinkTarget**-Einstellung für Geräteinformationen mit dem Wert „main“ in der Abfragezeichenfolge der URL übergeben.</span><span class="sxs-lookup"><span data-stu-id="39b8a-115">In the previous example, the device information setting **LinkTarget** is passed with a value of "main" in the query string of the URL.</span></span> <span data-ttu-id="39b8a-116">Damit wird sichergestellt, dass alle Drillthroughlinks im Bericht auch den Frame „main“ ansteuern.</span><span class="sxs-lookup"><span data-stu-id="39b8a-116">This ensures that any drillthrough hyperlinks in the report also target the frame named "main".</span></span>  
  
 <span data-ttu-id="39b8a-117">Weitere Informationen zu den Einstellungen für Geräteinformationen finden Sie unter [Übergeben von Geräteinformationseinstellungen an Renderingerweiterungen](../report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="39b8a-117">For more information about device information settings, see [Passing Device Information Settings to Rendering Extensions](../report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md).</span></span>  
  
 <span data-ttu-id="39b8a-118">Beachten Sie, dass in vielen Servern und Browsern die Anzahl der zulässigen Zeichen in einer URL beschränkt ist.</span><span class="sxs-lookup"><span data-stu-id="39b8a-118">Note that many servers and browsers limit the number of characters allowed in a URL.</span></span> <span data-ttu-id="39b8a-119">In einigen Fällen sind maximal 256 Zeichen zulässig.</span><span class="sxs-lookup"><span data-stu-id="39b8a-119">In some cases, a 256-character limit is imposed.</span></span> <span data-ttu-id="39b8a-120">Um diese Einschränkung zu umgehen, können Sie POST-Anforderungen mit Formularübergabe verwenden.</span><span class="sxs-lookup"><span data-stu-id="39b8a-120">To get around this limitation, you can use POST requests using form submission.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="39b8a-121">Die maximale URL-Länge im Internet Explorer beträgt 2.083 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="39b8a-121">Internet Explorer has a maximum URL length of 2,083 characters.</span></span> <span data-ttu-id="39b8a-122">Diese Grenze gilt sowohl für POST- als auch für GET-Anforderungs-URLs.</span><span class="sxs-lookup"><span data-stu-id="39b8a-122">This limit applies to both POST and GET request URLs.</span></span> <span data-ttu-id="39b8a-123">POST-Anforderungen werden jedoch bei der Übergabe von Name-/Wert-Paaren nicht durch die Größe der URL beschränkt, da sie im Header und nicht in der URL übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="39b8a-123">POST, however, is not limited by the size of the URL for submitting name/value pairs as part of a form, because they are transferred in the header and not the URL.</span></span>  
  
## <a name="url-access-through-a-form-post-method"></a><span data-ttu-id="39b8a-124">URL-Zugriff über die Formular POST-Methode</span><span class="sxs-lookup"><span data-stu-id="39b8a-124">URL Access Through a Form POST Method</span></span>  
 <span data-ttu-id="39b8a-125">Wenn ein Benutzer mit URL-Zugriff Daten von einem Berichtsserver anfordert, verwendet die HTTP-Anforderung die GET-Methode.</span><span class="sxs-lookup"><span data-stu-id="39b8a-125">When a user requests data from a report server using URL access, the HTTP request uses the GET method.</span></span> <span data-ttu-id="39b8a-126">Dies entspricht einer Formularübergabe von METHOD = "GET".</span><span class="sxs-lookup"><span data-stu-id="39b8a-126">This is equivalent to a form submission where METHOD="GET".</span></span> <span data-ttu-id="39b8a-127">URL-Anforderungen oder Formularübergaben, die METHOD="GET" verwenden, sind durch die maximale Anzahl von Zeichen beschränkt, die ein Server oder Webbrowser verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="39b8a-127">URL requests or form submissions that use METHOD="GET" are limited by the maximum number of characters that a server or Web browser can process.</span></span>  
  
 <span data-ttu-id="39b8a-128">Mit POST-Anforderungen (METHOD="POST" und Eingabefelder) werden die Name/Wert-Paare im Header und nicht in der URL übertragen.</span><span class="sxs-lookup"><span data-stu-id="39b8a-128">With POST requests (METHOD="POST" and input fields), the name/value pairs are transferred in the header and not the URL.</span></span> <span data-ttu-id="39b8a-129">Daher sind die Name/Wert-Paare der Abfragezeichenfolge nicht Teil der URL und können viel längere und komplexere Parameterlisten enthalten.</span><span class="sxs-lookup"><span data-stu-id="39b8a-129">Therefore, the name/value pairs of the query string are not part of the URL, thus enabling you to provide much longer and more complex parameter lists.</span></span>  
  
 <span data-ttu-id="39b8a-130">Über den Direktzugriff kann ein Benutzer die URL für den Berichtsserver sehen und kann daher möglicherweise die Abfragezeichenfolge ändern oder sich die jeweiligen Parameter der URL-Anforderung und des Berichtsservers für eine spätere Verwendung notieren.</span><span class="sxs-lookup"><span data-stu-id="39b8a-130">Using direct access, a user can see the URL for the report server, and may be able to modify the  query string or note the particular URL request and report server parameters for later use.</span></span>  
  
 <span data-ttu-id="39b8a-131">Die folgende Beispiel-HTML zeigt die Verwendung eines Formulars, das Sie verwenden können, um einen Berichtsserver mit einer bestimmten URL anzusteuern und die Parameter der Abfragezeichenfolge als Teil der Eingabefelder des Formulars weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="39b8a-131">The following sample HTML demonstrates the use of a form that you can use to target a report server with a specific URL and pass query string parameters as part of the form's input fields.</span></span>  
  
```  
<FORM id="frmRender" action="http://server/reportserver?/SampleReports/  
   Territory Sales Drilldown" method="post" target="_self">  
   <INPUT type="hidden" name="rs:Command" value="Render">   
   <INPUT type="hidden" name="rc:LinkTarget" value="main">  
   <INPUT type="hidden" name="rs:Format" value="HTML4.0">  
   <INPUT type="submit" value="Button">  
</FORM>  
```  
  
 <span data-ttu-id="39b8a-132">Im vorhergehenden Beispiel gibt der Berichtsserver, wenn ein Benutzer auf die Schaltfläche im Formular klickt, einen HTML-gerenderten Bericht zurück, der auf den aktuellen Frame gerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="39b8a-132">In the previous example, if a user clicks the button on the form, the report server returns an HTML-rendered report targeted at the current frame.</span></span> <span data-ttu-id="39b8a-133">Eine vergleichbare URL-Zugriffszeichenfolge könnte folgendermaßen aussehen:</span><span class="sxs-lookup"><span data-stu-id="39b8a-133">A comparable URL access string might look like the following:</span></span>  
  
```  
http://server/reportserver?/SampleReports/Territory Sales   
Drilldown&rs:Command=Render&rc:LinkTarget=main&rs:Format=HTML4.0  
```  
  
## <a name="see-also"></a><span data-ttu-id="39b8a-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="39b8a-134">See Also</span></span>  
 <span data-ttu-id="39b8a-135">[Integrieren von Reporting Services in Anwendungen](../application-integration/integrating-reporting-services-into-applications.md) </span><span class="sxs-lookup"><span data-stu-id="39b8a-135">[Integrating Reporting Services into Applications](../application-integration/integrating-reporting-services-into-applications.md) </span></span>  
 <span data-ttu-id="39b8a-136">[Integrieren von Reporting Services mithilfe des URL-Zugriffs](integrating-reporting-services-using-url-access.md) </span><span class="sxs-lookup"><span data-stu-id="39b8a-136">[Integrating Reporting Services Using URL Access](integrating-reporting-services-using-url-access.md) </span></span>  
 <span data-ttu-id="39b8a-137">[Verwenden des URL-Zugriffs in einer Windows-Anwendung](integrating-reporting-services-using-url-access-windows-application.md) </span><span class="sxs-lookup"><span data-stu-id="39b8a-137">[Using URL Access in a Windows Application](integrating-reporting-services-using-url-access-windows-application.md) </span></span>  
 [<span data-ttu-id="39b8a-138">URL-Zugriff &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="39b8a-138">URL Access &#40;SSRS&#41;</span></span>](../url-access-ssrs.md)  
  
  
