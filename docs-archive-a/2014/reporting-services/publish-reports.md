---
title: Veröffentlichen von Berichten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- reports [Reporting Services], publishing
- publishing reports [Reporting Services]
ms.assetid: ef5a514e-e818-4041-a8b0-15835f9a046b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bb54308a6b15260d4c336950f231d0ee40836430
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608367"
---
# <a name="publish-reports"></a><span data-ttu-id="4d183-102">Veröffentlichen von Berichten</span><span class="sxs-lookup"><span data-stu-id="4d183-102">Publish Reports</span></span>
  <span data-ttu-id="4d183-103">Von[!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]aus können Sie entweder alle Berichte und freigegebenen Datenquellen in einem Berichtsserverprojekt auf einem Berichtsserver veröffentlichen, indem Sie das Projekt bereitstellen, oder Sie können einen einzelnen Bericht veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="4d183-103">From[!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], you can publish either all the reports and shared data sources in a Report Server project to a report server by deploying the project, or you can publish a single report.</span></span> <span data-ttu-id="4d183-104">Bevor Sie einen Bericht veröffentlichen können, müssen Sie die URL des Zielberichtsservers angeben.</span><span class="sxs-lookup"><span data-stu-id="4d183-104">Before you can publish a report you must specify the URL of the target report server.</span></span> <span data-ttu-id="4d183-105">Weitere Informationen finden Sie unter [Festlegen von Bereitstellungseigenschaften &#40;Reporting Services&#41;](tools/set-deployment-properties-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="4d183-105">For more information, see [Set Deployment Properties &#40;Reporting Services&#41;](tools/set-deployment-properties-reporting-services.md).</span></span>  
  
 <span data-ttu-id="4d183-106">Sie können die [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] -Version von [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] verwenden, um sowohl [!INCLUDE[ssRSversion2005](../includes/ssrsversion2005-md.md)] -Berichte als auch [!INCLUDE[ssRSversion10](../includes/ssrsversion10-md.md)] -Berichte zu öffnen, zu ändern, in der Vorschau anzuzeigen, zu speichern und zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="4d183-106">You can use the [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] version of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to open, modify, preview, save, and publish both [!INCLUDE[ssRSversion2005](../includes/ssrsversion2005-md.md)] and [!INCLUDE[ssRSversion10](../includes/ssrsversion10-md.md)] reports.</span></span> <span data-ttu-id="4d183-107">Weitere Informationen finden Sie unter [Bereitstellung und Versionsunterstützung in SQL Server Data Tools &#40;SSRS&#41;](tools/deployment-and-version-support-in-sql-server-data-tools-ssrs.md)enthalten.</span><span class="sxs-lookup"><span data-stu-id="4d183-107">For more information, see [Deployment and Version Support in SQL Server Data Tools &#40;SSRS&#41;](tools/deployment-and-version-support-in-sql-server-data-tools-ssrs.md).</span></span>  
  
### <a name="to-publish-all-reports-in-a-project"></a><span data-ttu-id="4d183-108">So veröffentlichen Sie alle Berichte in einem Projekt</span><span class="sxs-lookup"><span data-stu-id="4d183-108">To publish all reports in a project</span></span>  
  
-   <span data-ttu-id="4d183-109">\*\*Klicken Sie \<report project name> \*\*im Menü **Erstellen** auf bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="4d183-109">On the **Build** menu, click **Deploy \<report project name>**.</span></span> <span data-ttu-id="4d183-110">Sie können auch im Projektmappen-Explorer mit der rechten Maustaste auf das Berichtsobjekt klicken. Klicken Sie dann auf **Bereitstellen**.</span><span class="sxs-lookup"><span data-stu-id="4d183-110">Alternatively, in Solution Explorer, right-click the report project and then click **Deploy**.</span></span> <span data-ttu-id="4d183-111">Den Status des Veröffentlichungsvorgangs sehen Sie im Ausgabefenster.</span><span class="sxs-lookup"><span data-stu-id="4d183-111">You can view the status of the publishing process in the Output window.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4d183-112">Wenn Sie ein Berichtsserverprojekt bereitstellen, werden die freigegebenen Datenquellen im Berichtsprojekt ebenfalls bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="4d183-112">When you deploy a Report Server project, the shared data sources in the report project are also deployed.</span></span>  
  
### <a name="to-publish-a-single-report"></a><span data-ttu-id="4d183-113">So veröffentlichen Sie einen einzelnen Bericht</span><span class="sxs-lookup"><span data-stu-id="4d183-113">To publish a single report</span></span>  
  
-   <span data-ttu-id="4d183-114">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf den Bericht, und klicken Sie auf **Bereitstellen**.</span><span class="sxs-lookup"><span data-stu-id="4d183-114">In Solution Explorer, right-click the report and then click **Deploy**.</span></span> <span data-ttu-id="4d183-115">Den Status des Veröffentlichungsvorgangs sehen Sie im Ausgabefenster.</span><span class="sxs-lookup"><span data-stu-id="4d183-115">You can view the status of the publishing process in the Output window.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4d183-116">Wenn Sie einen Bericht veröffentlichen, müssen Sie auch die freigegebenen Datenquellen bereitstellen, die vom Bericht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4d183-116">When you publish a report, you must also deploy the shared data sources that the report uses.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d183-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4d183-117">See Also</span></span>  
 <span data-ttu-id="4d183-118">[Veröffentlichen von Datenquellen und Berichten](reports/publishing-data-sources-and-reports.md) </span><span class="sxs-lookup"><span data-stu-id="4d183-118">[Publishing Data Sources and Reports](reports/publishing-data-sources-and-reports.md) </span></span>  
 <span data-ttu-id="4d183-119">[Anzeigen einer Vorschau für Berichte](reports/previewing-reports.md) </span><span class="sxs-lookup"><span data-stu-id="4d183-119">[Previewing Reports](reports/previewing-reports.md) </span></span>  
 <span data-ttu-id="4d183-120">[Veröffentlichen von Berichten auf einem Berichts Server](reports/publishing-reports-to-a-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="4d183-120">[Publishing Reports to a Report Server](reports/publishing-reports-to-a-report-server.md) </span></span>  
 <span data-ttu-id="4d183-121">[Suchen, anzeigen und Verwalten von Berichten &#40;Berichts-Generator und SSRS &#41;](report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="4d183-121">[Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;](report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="4d183-122">Exportieren von Berichten &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="4d183-122">Exporting Reports &#40;Report Builder and SSRS&#41;</span></span>](report-builder/export-reports-report-builder-and-ssrs.md)  
  
  
