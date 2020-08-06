---
title: Exportieren eines Berichts über URL-Zugriff | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- formats [Reporting Services], URL rendering
- URL access [Reporting Services], rendering formats
ms.assetid: 6a3b7fc3-3d91-4d12-8371-42ea12e74517
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 69f340855e37ffde49aec0af096c094a142659d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695434"
---
# <a name="export-a-report-using-url-access"></a><span data-ttu-id="21de1-102">Exportieren von Berichten über URL-Zugriff</span><span class="sxs-lookup"><span data-stu-id="21de1-102">Export a Report Using URL Access</span></span>
  <span data-ttu-id="21de1-103">Sie können optional das Format angeben, in dem ein Bericht mithilfe des *RS: Format* -Parameters dargestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="21de1-103">You can optionally specify the format in which to render a report by using the *rs:Format* parameter.</span></span> <span data-ttu-id="21de1-104">Um beispielsweise von einem im einheitlichen Modus ausgeführten Berichtsserver direkt eine PDF-Kopie eines Berichts abzurufen, geben Sie Folgendes an:</span><span class="sxs-lookup"><span data-stu-id="21de1-104">For example, to get a PDF copy of a report directly from a native mode report server:</span></span>  
  
```  
http://myrshost/ReportServer?/myreport&rs:Format=PDF  
```  
  
 <span data-ttu-id="21de1-105">Zum Abrufen von einem Berichtsserver im integrierten SharePoint-Modus geben Sie Folgendes an:</span><span class="sxs-lookup"><span data-stu-id="21de1-105">And, from a SharePoint integrated mode report server:</span></span>  
  
```  
http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/myrereport.rdl&rs:Format=PDF  
```  
  
 <span data-ttu-id="21de1-106">Gültige Werte für diesen Parameter sind von den Berichtrenderingerweiterungen abhängig, die auf dem Berichtsserver installiert sind, auf den zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="21de1-106">Valid values for this parameter are based on the report rendering extensions that are installed on the report server being accessed.</span></span> <span data-ttu-id="21de1-107">Häufig verwendete Erweiterungen sind HTML4.0, MHTML, IMAGE, EXCEL, WORD, CSV, PDF, XML und NULL.</span><span class="sxs-lookup"><span data-stu-id="21de1-107">Common extensions are HTML4.0, MHTML, IMAGE, EXCEL, WORD, CSV, PDF, XML, and NULL.</span></span> <span data-ttu-id="21de1-108">Wenn eine bestimmte Renderingerweiterung nicht auf dem Berichtsserver installiert ist, wird der Bericht nicht gerendert. Es wird ein Fehler generiert und im Browser angezeigt.</span><span class="sxs-lookup"><span data-stu-id="21de1-108">If a specified rendering extension is not installed on the report server, the report is not rendered and an error is generated and displayed in the browser.</span></span>  
  
 <span data-ttu-id="21de1-109">Wenn Sie den *Format* -Parameter nicht als Teil der URL aufnehmen, erkennt der Berichtsserver den Browser und rendert den Bericht im entsprechenden HTML-Format.</span><span class="sxs-lookup"><span data-stu-id="21de1-109">If you do not include the *Format* parameter as part of the URL, the report server detects the browser and renders the report in the appropriate HTML format.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21de1-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="21de1-110">See Also</span></span>  
 <span data-ttu-id="21de1-111">[URL-Zugriff &#40;SSRS-&#41;](url-access-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="21de1-111">[URL Access &#40;SSRS&#41;](url-access-ssrs.md) </span></span>  
 [<span data-ttu-id="21de1-112">URL Access Parameter Reference (URL-Zugriffsparameterverweis)</span><span class="sxs-lookup"><span data-stu-id="21de1-112">URL Access Parameter Reference</span></span>](url-access-parameter-reference.md)  
  
  
