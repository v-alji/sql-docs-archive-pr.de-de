---
title: Zugreifen auf Berichtsserverelemente über den URL-Zugriff | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- referencing URL items for report server access
- URL access [Reporting Services], report servers
ms.assetid: a58b4ca6-129d-45e9-95c7-e9169fe5bba4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6693419490c1b3770ccb41b2645cbdba8996630a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619667"
---
# <a name="access-report-server-items-using-url-access"></a><span data-ttu-id="d7706-102">Zugreifen auf Berichtsserverelemente über den URL-Zugriff</span><span class="sxs-lookup"><span data-stu-id="d7706-102">Access Report Server Items Using URL Access</span></span>
  <span data-ttu-id="d7706-103">In diesem Thema wird beschrieben, wie Sie in einer Berichtsserver-Datenbank oder auf einer SharePoint-Website unter Verwendung von *rs:Befehl*=*Wert*auf Katalogelemente mit unterschiedlichen Typen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="d7706-103">This topic describes how to access catalog items of different types in a report server data base or in a SharePoint site using *rs:Command*=*Value*.</span></span>  
  
 <span data-ttu-id="d7706-104">Es ist nicht erforderlich, diese Parameterzeichenfolge hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="d7706-104">It is not necessary to add this parameter string.</span></span> <span data-ttu-id="d7706-105">Wenn Sie sie weglassen, wertet der Berichtsserver den Elementtyp aus und wählt den entsprechenden Parameterwert automatisch aus.</span><span class="sxs-lookup"><span data-stu-id="d7706-105">If you omit it, the report server evaluates the item type and selects the appropriate parameter value automatically.</span></span> <span data-ttu-id="d7706-106">Durch die Verwendung der *rs:Command*=*Value* -Zeichenfolge in der URL verbessert sich jedoch die Leistung des Berichtsservers.</span><span class="sxs-lookup"><span data-stu-id="d7706-106">However, using the *rs:Command*=*Value* string in the URL improves the performance of the report server.</span></span>  
  
 <span data-ttu-id="d7706-107">Beachten Sie in den Beispielen unten die `_vti_bin` -Proxysyntax.</span><span class="sxs-lookup"><span data-stu-id="d7706-107">Note the `_vti_bin` proxy syntax in the examples below.</span></span> <span data-ttu-id="d7706-108">Weitere Informationen zum Verwenden der Proxysyntax finden Sie unter [URL Access Parameter Reference](url-access-parameter-reference.md).</span><span class="sxs-lookup"><span data-stu-id="d7706-108">For more information about using the proxy syntax, see [URL Access Parameter Reference](url-access-parameter-reference.md).</span></span>  
  
## <a name="access-a-report"></a><span data-ttu-id="d7706-109">Zugreifen auf einen Bericht</span><span class="sxs-lookup"><span data-stu-id="d7706-109">Access a Report</span></span>  
 <span data-ttu-id="d7706-110">Um einen Bericht im Browser anzuzeigen, verwenden Sie den *RS: Command*- = *Rendering* -Parameter.</span><span class="sxs-lookup"><span data-stu-id="d7706-110">To view a report in the browser, use the *rs:Command*=*Render* parameter.</span></span> <span data-ttu-id="d7706-111">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d7706-111">For example:</span></span>  
  
 <span data-ttu-id="d7706-112">`Native` `http://myrshost/reportserver?/Sales/YearlySalesByCategory&rs:Command=Render`</span><span class="sxs-lookup"><span data-stu-id="d7706-112">`Native` `http://myrshost/reportserver?/Sales/YearlySalesByCategory&rs:Command=Render`</span></span>  
  
 <span data-ttu-id="d7706-113">`SharePoint` `http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/Sales/YearlySalesByCategory&rs:Command=Render`</span><span class="sxs-lookup"><span data-stu-id="d7706-113">`SharePoint` `http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/Sales/YearlySalesByCategory&rs:Command=Render`</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="d7706-114">Es ist wichtig, dass die URL die `_vti_bin` -Proxysyntax zur Weiterleitung der Anforderung über SharePoint sowie den [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -HTTP-Proxy enthält.</span><span class="sxs-lookup"><span data-stu-id="d7706-114">It is important the URL include the `_vti_bin` proxy syntax to route the request through SharePoint and the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] HTTP proxy.</span></span> <span data-ttu-id="d7706-115">Durch den Proxy wird der HTTP-Anforderung Kontext hinzugefügt. Dieser ist erforderlich, damit der Bericht auf Berichtsservern im SharePoint-Modus ordnungsgemäß ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d7706-115">The proxy adds some context to the HTTP request, context that is required to ensure proper execution of the report for SharePoint mode report servers.</span></span>  
  
## <a name="access-a-resource"></a><span data-ttu-id="d7706-116">Zugreifen auf eine Ressource</span><span class="sxs-lookup"><span data-stu-id="d7706-116">Access a Resource</span></span>  
 <span data-ttu-id="d7706-117">Verwenden Sie den *RS: Command* = *GetResourceContents* -Parameter, um auf eine Ressource zuzugreifen. Wenn die Ressource mit dem Browser kompatibel ist (z. b. ein Bild), wird Sie im Browser geöffnet.</span><span class="sxs-lookup"><span data-stu-id="d7706-117">To access a resource, use the *rs:Command*=*GetResourceContents* parameter.If the resource is compatible with the browser, such as an image, it is opened in the browser.</span></span> <span data-ttu-id="d7706-118">Andernfalls werden Sie aufgefordert, die Datei oder Ressource zu öffnen oder auf dem Datenträger zu speichern.</span><span class="sxs-lookup"><span data-stu-id="d7706-118">Otherwise, you are prompted to open or save the file or resource to disk.</span></span>  
  
 <span data-ttu-id="d7706-119">`Native` `http://myrshost/reportserver?/Sales/StorePicture&rs:Command=GetResourceContents`</span><span class="sxs-lookup"><span data-stu-id="d7706-119">`Native` `http://myrshost/reportserver?/Sales/StorePicture&rs:Command=GetResourceContents`</span></span>  
  
 <span data-ttu-id="d7706-120">`SharePoint` `http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/Sales/StorePicture.jpg&rs:Command=GetResourceContents`</span><span class="sxs-lookup"><span data-stu-id="d7706-120">`SharePoint` `http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/Sales/StorePicture.jpg&rs:Command=GetResourceContents`</span></span>  
  
## <a name="access-a-data-source"></a><span data-ttu-id="d7706-121">Zugreifen auf eine Datenquelle</span><span class="sxs-lookup"><span data-stu-id="d7706-121">Access a Data Source</span></span>  
 <span data-ttu-id="d7706-122">Um auf eine Datenquelle zuzugreifen, verwenden Sie den Parameter *RS: Command* = *GetDataSourceContents* .</span><span class="sxs-lookup"><span data-stu-id="d7706-122">To access a data source, use the *rs:Command*=*GetDataSourceContents* parameter.</span></span> <span data-ttu-id="d7706-123">Wenn Ihr Browser XML unterstützt, wird die Datenquellendefinition angezeigt, wenn Sie ein für die Datenquelle authentifizierter Benutzer mit der Berechtigung `Read Contents` sind.</span><span class="sxs-lookup"><span data-stu-id="d7706-123">If your browser supports XML, the data source definition is displayed if you are an authenticated user with `Read Contents` permission on the data source.</span></span> <span data-ttu-id="d7706-124">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d7706-124">For example:</span></span>  
  
 <span data-ttu-id="d7706-125">`Native` `http://myrshost/reportserver?/Sales/AdventureWorks2012&rs:Command=GetDataSourceContents`</span><span class="sxs-lookup"><span data-stu-id="d7706-125">`Native` `http://myrshost/reportserver?/Sales/AdventureWorks2012&rs:Command=GetDataSourceContents`</span></span>  
  
 <span data-ttu-id="d7706-126">`SharePoint` `http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/Sales/AdventureWorks2012&rs:Command=GetDataSourceContents`</span><span class="sxs-lookup"><span data-stu-id="d7706-126">`SharePoint` `http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/Sales/AdventureWorks2012&rs:Command=GetDataSourceContents`</span></span>  
  
 <span data-ttu-id="d7706-127">Die XML-Struktur kann Ähnlichkeit mit folgendem Beispiel haben:</span><span class="sxs-lookup"><span data-stu-id="d7706-127">The XML structure might look similar to the following example:</span></span>  
  
```  
<DataSourceDefinition>  
   <Extension>SQL</Extension>  
   <ConnectString>Provider=SQLOLEDB.1;Integrated Security=SSPI;Persist Security Info=False;Initial Catalog=AdventureWorks2012;Data Source=MYSERVER1;</ConnectString>  
   <CredentialRetrieval>Integrated</CredentialRetrieval>  
   <WindowsCredentials>False</WindowsCredentials>  
   <ImpersonateUser>False</ImpersonateUser>  
   <Prompt />  
   <Enabled>True</Enabled>  
</DataSourceDefinition>  
```  
  
 <span data-ttu-id="d7706-128">Die Verbindungszeichenfolge wird auf Grundlage der **SecureConnectionLevel** -Einstellung des Berichtsservers zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d7706-128">The connection string is returned based on the **SecureConnectionLevel** setting of the report server.</span></span> <span data-ttu-id="d7706-129">Weitere Informationen zur **SecureConnectionLevel** -Einstellung finden Sie unter [Using Secure Web Service Methods](report-server-web-service/net-framework/using-secure-web-service-methods.md).</span><span class="sxs-lookup"><span data-stu-id="d7706-129">For more information about the **SecureConnectionLevel** setting, see [Using Secure Web Service Methods](report-server-web-service/net-framework/using-secure-web-service-methods.md).</span></span>  
  
## <a name="access-the-contents-of-a-folder"></a><span data-ttu-id="d7706-130">Zugreifen auf den Inhalt eines Ordners</span><span class="sxs-lookup"><span data-stu-id="d7706-130">Access the Contents of a Folder</span></span>  
 <span data-ttu-id="d7706-131">Um auf den Inhalt eines Ordners zuzugreifen, verwenden Sie den *RS: Command* = *GetChildren* -Parameter.</span><span class="sxs-lookup"><span data-stu-id="d7706-131">To access the contents of a folder, use the *rs:Command*=*GetChildren* parameter.</span></span> <span data-ttu-id="d7706-132">Es wird eine generische Seite zur Ordnernavigation zurückgegeben, die Links zu den Unterordnern, Berichten, Datenquellen und Ressourcen im angeforderten Ordner enthält.</span><span class="sxs-lookup"><span data-stu-id="d7706-132">A generic folder-navigation page is returned that contains links to the subfolders, reports, data sources, and resources in the requested folder.</span></span> <span data-ttu-id="d7706-133">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d7706-133">For example:</span></span>  
  
 <span data-ttu-id="d7706-134">`Native` `http://myrshost/reportserver?/Sales&rs:Command=GetChildren`</span><span class="sxs-lookup"><span data-stu-id="d7706-134">`Native` `http://myrshost/reportserver?/Sales&rs:Command=GetChildren`</span></span>  
  
 <span data-ttu-id="d7706-135">`SharePoint` `http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/Sales&rs:Command=GetChildren`</span><span class="sxs-lookup"><span data-stu-id="d7706-135">`SharePoint` `http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/Sales&rs:Command=GetChildren`</span></span>  
  
 <span data-ttu-id="d7706-136">Die angezeigte Benutzeroberfläche hat Ähnlichkeit mit dem Verzeichnissuchmodus, der von [!INCLUDE[msCoName](../includes/msconame-md.md)] IIS (Internet Information Server) verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d7706-136">The user interface you see is similar to the directory browsing mode used by [!INCLUDE[msCoName](../includes/msconame-md.md)] Internet Information Server (IIS).</span></span> <span data-ttu-id="d7706-137">Die Versionsnummer, einschließlich der Buildnummer des Berichtsservers, wird ebenfalls unter der Ordnerliste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d7706-137">The version number, including the build number, of the report server is also displayed below the folder listing.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7706-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d7706-138">See Also</span></span>  
 <span data-ttu-id="d7706-139">[URL-Zugriff &#40;SSRS-&#41;](url-access-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d7706-139">[URL Access &#40;SSRS&#41;](url-access-ssrs.md) </span></span>  
 [<span data-ttu-id="d7706-140">URL Access Parameter Reference (URL-Zugriffsparameterverweis)</span><span class="sxs-lookup"><span data-stu-id="d7706-140">URL Access Parameter Reference</span></span>](url-access-parameter-reference.md)  
  
  
