---
title: Neues in Berichts-Generator für SQL Server 2014 |&#39;Microsoft-Dokumentation
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 8223c19b-4b0d-4b1d-a042-9a726c18e708
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0ce72af225130bc3f081a53008a303c5213db636
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619008"
---
# <a name="what39s-new-in-report-builder-for-sql-server-2014"></a><span data-ttu-id="40a4e-102">Neues in Berichts-Generator für SQL Server 2014&#39;</span><span class="sxs-lookup"><span data-stu-id="40a4e-102">What&#39;s New in Report Builder for SQL Server 2014</span></span>
  <span data-ttu-id="40a4e-103">In [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] werden mehrere [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]-Funktionen eingeführt.</span><span class="sxs-lookup"><span data-stu-id="40a4e-103">The [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] introduces a number of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features.</span></span>  
  
 <span data-ttu-id="40a4e-104">Informationen zu den Features in dieser Version für andere [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] Produkte und Technologien finden Sie unter [What es New in SQL Server 2014](../sql-server/what-s-new-in-sql-server-2016.md).</span><span class="sxs-lookup"><span data-stu-id="40a4e-104">For information about features in this release for other [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] products and technologies, see [What's New in SQL Server 2014](../sql-server/what-s-new-in-sql-server-2016.md).</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="40a4e-105">Die neuesten Informationen und Ressourcen zu neuen Funktionen in dieser Version finden Sie unter [zusätzliche Informationen zu den Neuerungen in SQL Server Reporting Services (SSRS)](https://go.microsoft.com/fwlink/?LinkId=207147).</span><span class="sxs-lookup"><span data-stu-id="40a4e-105">For the most recent information and resources regarding new features in this release, see [Additional information on what is new in SQL Server Reporting Services (SSRS)](https://go.microsoft.com/fwlink/?LinkId=207147).</span></span>  
  
##  <a name="excel-renderer-for-microsoft-excel-2007-2010-and-microsoft-excel-2003"></a><a name="ExcelRenderer"></a><span data-ttu-id="40a4e-106">Excel-Renderer für Microsoft Excel 2007-2010 und Microsoft Excel 2003</span><span class="sxs-lookup"><span data-stu-id="40a4e-106">Excel Renderer for Microsoft Excel 2007-2010 and Microsoft Excel 2003</span></span>  
 <span data-ttu-id="40a4e-107">Die neu in [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] aufgenommene [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] Excel-Renderingerweiterung rendert einen Bericht als Excel-Dokument, das mit [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] 2007-2010 und [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] 2003 kompatibel ist, wenn das Microsoft Office Compatibility Pack für Word, Excel und PowerPoint installiert ist.</span><span class="sxs-lookup"><span data-stu-id="40a4e-107">The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Excel rendering extension, new in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], renders a report as an Excel document that is compatible with [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] 2007-2010 as well as [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] 2003 with the Microsoft Office Compatibility Pack for Word, Excel, and PowerPoint installed.</span></span> <span data-ttu-id="40a4e-108">Das Format ist Office Open XML, und die Dateierweiterung der Dateien lautet XLSX.</span><span class="sxs-lookup"><span data-stu-id="40a4e-108">The format is Office Open XML and the file extension of files is .xlsx.</span></span>  
  
 <span data-ttu-id="40a4e-109">Diese Excel-Renderingerweiterung entfernt Einschränkungen der früheren Version, die mit Excel 2003 kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="40a4e-109">This Excel-rendering extension removes limitations of the earlier version, compatible with Excel 2003.</span></span> <span data-ttu-id="40a4e-110">Im Folgenden werden die Verbesserungen der Renderingerweiterung aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="40a4e-110">The following lists the improvement in the rendering extension:</span></span>  
  
-   <span data-ttu-id="40a4e-111">Die maximale Anzahl an Zeilen pro Arbeitsblatt beträgt 1.048.576.</span><span class="sxs-lookup"><span data-stu-id="40a4e-111">Maximum rows per worksheet is 1,048,576.</span></span>  
  
-   <span data-ttu-id="40a4e-112">Die maximale Anzahl an Spalten pro Arbeitsblatt beträgt 16.384.</span><span class="sxs-lookup"><span data-stu-id="40a4e-112">Maximum columns per worksheet is 16,384.</span></span>  
  
-   <span data-ttu-id="40a4e-113">Die Anzahl von in einem Arbeitsblatt zulässigen Farben beträgt ungefähr 16 Millionen (24-Bit-Farbe).</span><span class="sxs-lookup"><span data-stu-id="40a4e-113">Number of colors allowed in a worksheet is approximately 16 million (24-bit color).</span></span>  
  
-   <span data-ttu-id="40a4e-114">Die ZIP-Komprimierung stellt kleinere Dateigrößen bereit.</span><span class="sxs-lookup"><span data-stu-id="40a4e-114">ZIP compression provides smaller files sizes.</span></span>  
  
 <span data-ttu-id="40a4e-115">Weitere Informationen finden Sie unter [Exportieren nach Microsoft Excel &#40;Berichts-Generator und SSRS&#41;](report-builder/exporting-to-microsoft-excel-report-builder-and-ssrs.md) (Exportieren nach Microsoft Excel (Berichts-Generator und SSRS)).</span><span class="sxs-lookup"><span data-stu-id="40a4e-115">For more information, see [Exporting to Microsoft Excel &#40;Report Builder and SSRS&#41;](report-builder/exporting-to-microsoft-excel-report-builder-and-ssrs.md).</span></span>  
  
##  <a name="word-renderer-for-microsoft-word-2007-2010-and-microsoft-word-2003"></a><a name="WordRenderer"></a><span data-ttu-id="40a4e-116">Word-Renderer für Microsoft Word 2007-2010 und Microsoft Word 2003</span><span class="sxs-lookup"><span data-stu-id="40a4e-116">Word Renderer for Microsoft Word 2007-2010 and Microsoft Word 2003</span></span>  
 <span data-ttu-id="40a4e-117">Die neu in [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] aufgenommene [!INCLUDE[ssSQL11](../includes/sssql11-md.md)]Word-Renderingerweiterung rendert einen Bericht als Word-Dokument, das mit [!INCLUDE[ofprword](../includes/ofprword-md.md)] 2007-2010 und [!INCLUDE[ofprword](../includes/ofprword-md.md)] 2003 kompatibel ist, wenn das [!INCLUDE[msCoName](../includes/msconame-md.md)] Office Compatibility Pack für Word, Excel und PowerPoint installiert ist.</span><span class="sxs-lookup"><span data-stu-id="40a4e-117">The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Word rendering extension, new in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], renders a report as a Word document that is compatible with [!INCLUDE[ofprword](../includes/ofprword-md.md)] 2007-2010 as well as [!INCLUDE[ofprword](../includes/ofprword-md.md)] 2003 with the [!INCLUDE[msCoName](../includes/msconame-md.md)] Office Compatibility Pack for Word, Excel, and PowerPoint installed.</span></span> <span data-ttu-id="40a4e-118">Das Format ist Office Open XML, und die Dateierweiterung der Dateien lautet DOCX.</span><span class="sxs-lookup"><span data-stu-id="40a4e-118">The format is Office Open XML and the file extension of files is docx.</span></span>  
  
 <span data-ttu-id="40a4e-119">Der Word-Renderer ermöglicht nicht nur den Zugriff auf die neuen Funktionen, die in Word 2007-2010 für exportierte Berichte verfügbar sind, sondern stellt mit dem DOCX-Format meistens auch kleinere Dateien zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="40a4e-119">In addition to making the features that are new in Word 2007-2010 available to exported reports, \*.docx files of exported reports tend to be smaller.</span></span> <span data-ttu-id="40a4e-120">Die mit dem Word-Renderer exportierten Berichte sind normalerweise deutlich kleiner als die gleichen Berichte, die mit dem Word 2003-Renderer exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="40a4e-120">Reports exported by using the Word renderer are typically significantly smaller than the same reports exported by using the Word 2003 renderer.</span></span>  
  
 <span data-ttu-id="40a4e-121">Weitere Informationen finden Sie unter [Exportieren nach Microsoft Word &#40;Berichts-Generator und SSRS&#41;](report-builder/exporting-to-microsoft-word-report-builder-and-ssrs.md)mit den Daten arbeiten.</span><span class="sxs-lookup"><span data-stu-id="40a4e-121">For more information, see [Exporting to Microsoft Word &#40;Report Builder and SSRS&#41;](report-builder/exporting-to-microsoft-word-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40a4e-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="40a4e-122">See Also</span></span>  
 [<span data-ttu-id="40a4e-123">Berichts-Generator in SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="40a4e-123">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
