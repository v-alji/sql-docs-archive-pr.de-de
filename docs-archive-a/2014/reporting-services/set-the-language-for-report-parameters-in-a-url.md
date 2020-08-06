---
title: Festlegen der Sprache für Berichtsparameter in einer URL | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- overriding report language settings
- report servers [Reporting Services], language settings
- languages [Reporting Services]
- URL access [Reporting Services], language overrides
- international considerations [Reporting Services]
- global considerations [Reporting Services]
ms.assetid: e1ccf22f-80d6-45bc-aae0-f5f263275092
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 8087a181906517bb60d4cd6839eed0681f52a5eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700760"
---
# <a name="set-the-language-for-report-parameters-in-a-url"></a><span data-ttu-id="f57eb-102">Festlegen der Sprache für Berichtsparameter in einer URL</span><span class="sxs-lookup"><span data-stu-id="f57eb-102">Set the Language for Report Parameters in a URL</span></span>
  <span data-ttu-id="f57eb-103">Der *rs:ParameterLanguage* -Parameter für den URL-Zugriff behebt ein Problem, das auftritt, wenn kulturabhängige Berichtsparameter wie Datums-, Zeit-, Währungs- und Zahlenangaben über die Spracheinstellung des Browsers interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="f57eb-103">The *rs:ParameterLanguage* URL access parameter alleviates a problem in which culture-sensitive report parameters, such as dates, times, currency, and numbers, are interpreted using the browser language.</span></span> <span data-ttu-id="f57eb-104">Mit *rs:ParameterLanguage*wird die URL unabhängig vom Browser interpretiert.</span><span class="sxs-lookup"><span data-stu-id="f57eb-104">With *rs:ParameterLanguage*, the URL is now interpreted independently of the browser.</span></span> <span data-ttu-id="f57eb-105">Wenn die Ländereinstellungen des Berichtsservers z. B. auf die Option Deutsch festgelegt sind, ein Benutzer jedoch mit einem Browser, für den die Option Englisch festgelegt ist, über eine URL auf einen Bericht zugreift, werden die an den Berichtsserver übergebenen Parameterwerte falsch interpretiert.</span><span class="sxs-lookup"><span data-stu-id="f57eb-105">For example, if the report server is set to a regional setting of German, but a user is accessing a report via a URL using a browser that is set to English-United States, parameter values that are passed to a report server will be misinterpreted.</span></span>  
  
 <span data-ttu-id="f57eb-106">Betrachten Sie die folgende URL für einen Bericht:</span><span class="sxs-lookup"><span data-stu-id="f57eb-106">Consider the following URL to a report:</span></span>  
  
```  
http://myrshost/Reportserver?/SampleReports/Product+Line+Sales&rs:Command=Render&StartDate=4/10/2008&EndDate=11/10/2008  
```  
  
 <span data-ttu-id="f57eb-107">Im oben beschriebenen Fall generiert der Server, der unter der Kultur "de-de" ausgeführt wird, eine URL entweder durch ein E-Mail-Abonnement oder durch einen Link.</span><span class="sxs-lookup"><span data-stu-id="f57eb-107">In the above case, the server, running under a culture of "de-de", generates a URL either through an e-mail subscription or a hyperlink.</span></span> <span data-ttu-id="f57eb-108">Der Link gibt an, dass der Bericht gemäß deutschen Standards für Datums- und Zeitangaben mit dem 4. Oktober 2008 als Anfangsdatum und dem 11. Oktober 2008 als Enddatum parametrisiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="f57eb-108">The hyperlink indicates that the report should be parameterized by a start date of October 4, 2008 and an end date of October 11, 2008 according to German date/time standards.</span></span> <span data-ttu-id="f57eb-109">Ein Benutzer, der mit einem Browser auf die URL zugreift, für den die Option "en-us" festgelegt wurde, zwingt den Server, die Werte gemäß amerikanischen Standards für Datums- und Zeitangaben als 10. April 2008 und 10. November 2008 zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="f57eb-109">However, a user that is accessing the URL through a browser set to "en-us" forces the server to interpret the values as April 10, 2008 and November 10, 2008 under United States English date/time standards.</span></span> <span data-ttu-id="f57eb-110">Das Problem kann behoben werden, indem Sie mit *rs:ParameterLanguage* die Browsersprache für die Parameterinterpretation überschreiben:</span><span class="sxs-lookup"><span data-stu-id="f57eb-110">To fix the problem, *rs:ParameterLanguage* can be used to override the browser language for parameter interpretation:</span></span>  
  
```  
http://myrshost/Reportserver?/SampleReports/Product+Line+Sales&rs:Command=Render&StartDate=4/10/2008&EndDate=11/10/2008&rs:ParameterLanguage=de-DE  
```  
  
 <span data-ttu-id="f57eb-111">Zusätzlich zu den Werten **true** und **false** für den URL-Zugriffsparameter *rc:Parameters*können Sie jetzt den Wert **Collapsed**übergeben.</span><span class="sxs-lookup"><span data-stu-id="f57eb-111">In addition to a value of **true** and **false** for the URL access parameter *rc:Parameters*, you can now pass a value of **Collapsed**.</span></span> <span data-ttu-id="f57eb-112">Wenn Sie *rc:Parameters*=**Collapsed** für eine URL verwenden, wird der Eingabeaufforderungsbereichs für Parameter des HTML-Viewers ausgeblendet, kann jedoch vom Benutzer wieder eingeblendet werden.</span><span class="sxs-lookup"><span data-stu-id="f57eb-112">When using *rc:Parameters*=**Collapsed** on a URL, the parameter prompt area of the HTML viewer is collapsed out of sight, but can still be toggled by the user.</span></span> <span data-ttu-id="f57eb-113">Der Wert **false** entfernt den Eingabeaufforderungsbereichs für Parameter ganz aus der Symbolleiste des HTML-Viewers, und der Endbenutzer kann den Parameterbereich nicht mehr anzeigen.</span><span class="sxs-lookup"><span data-stu-id="f57eb-113">A value of **false** removes the parameter prompt area from the HTML viewer toolbar and makes it unavailable to the end-user.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f57eb-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f57eb-114">See Also</span></span>  
 <span data-ttu-id="f57eb-115">[URL-Zugriff &#40;SSRS&#41;](url-access-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f57eb-115">[URL Access &#40;SSRS&#41;](url-access-ssrs.md) </span></span>  
 [<span data-ttu-id="f57eb-116">URL Access Parameter Reference (URL-Zugriffsparameterverweis)</span><span class="sxs-lookup"><span data-stu-id="f57eb-116">URL Access Parameter Reference</span></span>](url-access-parameter-reference.md)  
  
  
