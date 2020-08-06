---
title: Übergeben von Berichtsparametern innerhalb einer URL | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- URL access [Reporting Services], passing parameters
- passing parameters [Reporting Services]
ms.assetid: f93a94cc-27b5-435a-aa85-69e6ec6459ad
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cf41ed82728d5d7c840276e135937b08f83fb131
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723573"
---
# <a name="pass-a-report-parameter-within-a-url"></a><span data-ttu-id="56ab7-102">Übergeben von Berichtsparametern innerhalb einer URL</span><span class="sxs-lookup"><span data-stu-id="56ab7-102">Pass a Report Parameter Within a URL</span></span>
  <span data-ttu-id="56ab7-103">Sie können Berichtsparameter an einen Bericht übergeben, indem Sie sie in eine Berichts-URL einschließen.</span><span class="sxs-lookup"><span data-stu-id="56ab7-103">You can pass report parameters to a report by including them in a report URL.</span></span> <span data-ttu-id="56ab7-104">Diesen URL-Parametern wird nichts vorangestellt, da sie direkt an die Berichtsverarbeitungs-Engine übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="56ab7-104">These URL parameters are not prefixed because they are passed directly to the report processing engine.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="56ab7-105">Es ist wichtig, dass die URL die `_vti_bin` -Proxysyntax zur Weiterleitung der Anforderung über SharePoint sowie den [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -HTTP-Proxy enthält.</span><span class="sxs-lookup"><span data-stu-id="56ab7-105">It is important the URL include the `_vti_bin` proxy syntax to route the request through SharePoint and the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] HTTP proxy.</span></span> <span data-ttu-id="56ab7-106">Durch den Proxy wird der HTTP-Anforderung Kontext hinzugefügt. Dieser ist erforderlich, damit der Bericht auf Berichtsservern im SharePoint-Modus ordnungsgemäß ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="56ab7-106">The proxy adds some context to the HTTP request, context that is required to ensure proper execution of the report for SharePoint mode report servers.</span></span>  
>   
>  <span data-ttu-id="56ab7-107">Wenn Sie die Proxy Syntax nicht einschließen, müssen Sie den Parameter mit *RP:* versehen.</span><span class="sxs-lookup"><span data-stu-id="56ab7-107">If you don't include the proxy syntax, then you need to prefix the parameter with *rp:*.</span></span>  
  
 <span data-ttu-id="56ab7-108">Alle Abfrageparameter können über entsprechende Berichtsparameter verfügen.</span><span class="sxs-lookup"><span data-stu-id="56ab7-108">All query parameters can have corresponding report parameters.</span></span> <span data-ttu-id="56ab7-109">Sie übergeben einen Abfrageparameter an einen Bericht, indem Sie den entsprechenden Berichtsparameter übergeben.</span><span class="sxs-lookup"><span data-stu-id="56ab7-109">You pass a query parameter to a report by passing the corresponding report parameter.</span></span> <span data-ttu-id="56ab7-110">Weitere Informationen finden Sie unter [Erstellen einer Abfrage im Relationalen Abfrage-Designer (Berichts-Generator und SSRS)](report-data/build-a-query-in-the-relational-query-designer-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="56ab7-110">For more information, see [Build a Query in the Relational Query Designer &#40;Report Builder and SSRS&#41;](report-data/build-a-query-in-the-relational-query-designer-report-builder-and-ssrs.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="56ab7-111">Bei den Berichtsparametern wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="56ab7-111">Report parameters are case-sensitive.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="56ab7-112">Bei Berichtsparametern wird zwischen Groß-/Kleinschreibung unterschieden, und es werden folgende Sonderzeichen verwendet:</span><span class="sxs-lookup"><span data-stu-id="56ab7-112">Report parameters are case-sensitive and utilize the following special characters:</span></span>  
> 
>  -   <span data-ttu-id="56ab7-113">Alle Leerzeichen in der URL-Zeichenfolge werden entsprechend den URL-Codierungsstandards durch die Zeichen "%20" ersetzt.</span><span class="sxs-lookup"><span data-stu-id="56ab7-113">Any space characters in the URL string are replaced with the characters "%20," according to URL encoding standards.</span></span>  
> -   <span data-ttu-id="56ab7-114">Ein Leerzeichen im Parameterteil der URL wird durch ein Pluszeichen (+) ersetzt.</span><span class="sxs-lookup"><span data-stu-id="56ab7-114">A space character in the parameter portion of the URL is replaced with a plus character (+).</span></span>  
> -   <span data-ttu-id="56ab7-115">Ein Semikolon in einem beliebigen Teil der Zeichenfolge wird durch die Zeichen "%3A" ersetzt.</span><span class="sxs-lookup"><span data-stu-id="56ab7-115">A semicolon in any portion of the string is replaced with the characters "%3A."</span></span>  
> -   <span data-ttu-id="56ab7-116">Die Browser sollten die richtige URL-Codierung automatisch ausführen.</span><span class="sxs-lookup"><span data-stu-id="56ab7-116">Browsers should automatically perform the proper URL encoding.</span></span> <span data-ttu-id="56ab7-117">Sie müssen keines der Zeichen manuell codieren.</span><span class="sxs-lookup"><span data-stu-id="56ab7-117">You do not have to encode any of the characters manually.</span></span>  
  
 <span data-ttu-id="56ab7-118">Verwenden Sie die folgende Syntax, um einen Berichtsparameter innerhalb einer URL festzulegen:</span><span class="sxs-lookup"><span data-stu-id="56ab7-118">To set a report parameter within a URL, use the following syntax:</span></span>  
  
```  
  
parameter=value  
```  
  
 <span data-ttu-id="56ab7-119">Damit Sie beispielsweise die beiden Parameter „ReportMonth“ und „ReportYear“ angeben können, die in einem Bericht definiert wurden, verwenden Sie die folgende URL für einen Berichtsserver im nativen Modus:</span><span class="sxs-lookup"><span data-stu-id="56ab7-119">For example, to specify two parameters, "ReportMonth" and "ReportYear", defined in a report, use the following URL for a native mode report server:</span></span>  
  
```  
http://myrshost/ReportServer?/AdventureWorks 2008R2/Employee_Sales_Summary_2008R2&ReportMonth=3&ReportYear=2008  
```  
  
 <span data-ttu-id="56ab7-120">Um beispielsweise dieselben beiden in einem Bericht definierten Parameter anzugeben, verwenden Sie die folgende URL für einen Berichtsserver im integrierten SharePoint-Modus.</span><span class="sxs-lookup"><span data-stu-id="56ab7-120">For example, to specify the same two parameters defined in a report, use the following URL for a SharePoint integrated mode report server.</span></span> <span data-ttu-id="56ab7-121">Beachten Sie `/_vti_bin`:</span><span class="sxs-lookup"><span data-stu-id="56ab7-121">Note the `/_vti_bin`:</span></span>  
  
```  
http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/AdventureWorks 2008R2/Employee_Sales_Summary_2008R2.rdl&ReportMonth=3&ReportYear=2008  
```  
  
 <span data-ttu-id="56ab7-122">Verwenden Sie die folgende Syntax, um einen NULL-Wert für einen Parameter zu übergeben:</span><span class="sxs-lookup"><span data-stu-id="56ab7-122">To pass a null value for a parameter, use the following syntax:</span></span>  
  
```  
  
parameter  
:isnull=true  
  
```  
  
 <span data-ttu-id="56ab7-123">Ein auf ein Objekt angewendeter</span><span class="sxs-lookup"><span data-stu-id="56ab7-123">For example,</span></span>  
  
```  
SalesOrderNumber:isnull=true  
```  
  
 <span data-ttu-id="56ab7-124">Um einen `Boolean`-Wert zu übergeben, verwenden Sie 0 für "false" und 1 für "true".</span><span class="sxs-lookup"><span data-stu-id="56ab7-124">To pass a `Boolean` value, use 0 for false and 1 for true.</span></span> <span data-ttu-id="56ab7-125">Um einen `Float`-Wert zu übergeben, schließen Sie das Dezimaltrennzeichen des Servergebietsschemas ein</span><span class="sxs-lookup"><span data-stu-id="56ab7-125">To pass a `Float` value, include the decimal separator of the server locale</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="56ab7-126">Wenn Ihr Bericht einen Berichtsparameter enthält, der einen Standardwert besitzt, und der Wert der `Prompt`-Eigenschaft `false` ist (dies bedeutet, dass die PromptUser-Eigenschaft im Berichts-Manager nicht ausgewählt ist), können Sie keinen Wert für diesen Berichtsparameter innerhalb einer URL übergeben.</span><span class="sxs-lookup"><span data-stu-id="56ab7-126">If your report contains a report parameter that has a default value and the value of the `Prompt` property is `false` (that is, the Prompt User property is not selected in Report Manager), then you cannot pass a value for that report parameter within a URL.</span></span> <span data-ttu-id="56ab7-127">Dies ermöglicht Administratoren, Benutzer daran zu hindern, die Werte bestimmter Berichtsparameter hinzuzufügen oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="56ab7-127">This provides administrators an option for preventing end users from adding or modifying the values of certain report parameters.</span></span>  
  
##  <a name="additional-examples"></a><a name="bkmk_examples"></a> <span data-ttu-id="56ab7-128">Zusätzliche Beispiele</span><span class="sxs-lookup"><span data-stu-id="56ab7-128">Additional Examples</span></span>  
 <span data-ttu-id="56ab7-129">Die URL im folgenden Beispiel enthält Leerzeichen und mehrere Parameter.</span><span class="sxs-lookup"><span data-stu-id="56ab7-129">The following URL example includes spaces and multiple parameters</span></span>  
  
-   <span data-ttu-id="56ab7-130">Der Ordnername „SQL Server User Education Team“ enthält Leerzeichen; daher wird jedes Leerzeichen durch das Pluszeichen (+) ersetzt.</span><span class="sxs-lookup"><span data-stu-id="56ab7-130">Folder name of "SQL Server User Education Team" includes spaces and therefore the "+" replaces each space.</span></span>  
  
-   <span data-ttu-id="56ab7-131">Der Berichtsname „Team Project Report“ enthält Leerzeichen, und daher wird jedes Leerzeichen durch das Pluszeichen (+) ersetzt.</span><span class="sxs-lookup"><span data-stu-id="56ab7-131">Report name of "team project report" includes spaces and therefore the "+" replaces each space.</span></span>  
  
-   <span data-ttu-id="56ab7-132">Übergibt zwei teamgrouping2-Parameter mit dem Wert „xgroup“ und teamgrouping1 mit dem Wert „ygroup“.</span><span class="sxs-lookup"><span data-stu-id="56ab7-132">Passes two parameters of "teamgrouping2" with a value of "xgroup" and "teamgrouping1" with a value of "ygroup".</span></span>  
  
```  
https://myserver/Reportserver?/SQL+Server+User+Education+Team/_ContentTeams/folder123/team+project+report&teamgrouping2=xgroup&teamgrouping1=ygroup  
```  
  
 <span data-ttu-id="56ab7-133">Die URL im folgenden Beispiel enthält einen aus mehreren Werten bestehenden OrderID-Parameter.</span><span class="sxs-lookup"><span data-stu-id="56ab7-133">The following URL example includes a multi-value parameter "OrderID.</span></span> <span data-ttu-id="56ab7-134">Das Format für einen aus mehreren Werten bestehenden Parameter legt fest, dass der Parametername für jeden Wert wiederholt wird.</span><span class="sxs-lookup"><span data-stu-id="56ab7-134">The format for a Multi-Value parameter is to repeat the parameter name for each value.</span></span>  
  
```  
https://myserver/Reportserver?/SQL+Server+User+Education+Team/_ContentTeams/folder123/team+project+report&teamgrouping2=xgroup&teamgrouping1=ygroup&OrderID=747&OrderID=787&OrderID=12  
```  
  
 <span data-ttu-id="56ab7-135">Im folgenden URL-Beispiel wird ein einzelner Parameter von *SellStartDate* mit dem Wert "7/1/2005" für einen Berichts Server im einheitlichen Modus übergeben.</span><span class="sxs-lookup"><span data-stu-id="56ab7-135">The following URL example passes a single parameter of *SellStartDate* with a value of "7/1/2005", for a native mode report server.</span></span>  
  
```  
http://myserver/ReportServer/Pages/ReportViewer.aspx?%2fProduct_and_Sales_Report_AdventureWorks&SellStartDate=7/1/2005  
```  
  
## <a name="see-also"></a><span data-ttu-id="56ab7-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="56ab7-136">See Also</span></span>  
 <span data-ttu-id="56ab7-137">[URL-Zugriff &#40;SSRS-&#41;](url-access-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="56ab7-137">[URL Access &#40;SSRS&#41;](url-access-ssrs.md) </span></span>  
 [<span data-ttu-id="56ab7-138">URL Access Parameter Reference (URL-Zugriffsparameterverweis)</span><span class="sxs-lookup"><span data-stu-id="56ab7-138">URL Access Parameter Reference</span></span>](url-access-parameter-reference.md)  
  
  
