---
title: Exportieren eines Berichts in einen anderen Dateityp (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: b577568b-ecbd-44c3-be88-31dab6fc38a2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 240d3266b7b8c9a445658a9fd21fb9ea18a4c113
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695441"
---
# <a name="export-a-report-as-another-file-type-report-builder-and-ssrs"></a><span data-ttu-id="26ec2-102">Exportieren eines Berichts in ein anderes Dateiformat (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="26ec2-102">Export a Report as Another File Type (Report Builder and SSRS)</span></span>
  <span data-ttu-id="26ec2-103">Sie können einen Bericht in einem anderen Dateiformat wie CSV, Image, PDF, [!INCLUDE[ofprword](../includes/ofprword-md.md)]oder [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)]rendern, während Sie die Vorschau für den Bericht im Berichts-Generator oder Berichts-Designer anzeigen. Sie können den Bericht aber auch rendern, während Sie den Bericht auf dem Berichtsserver anzeigen.</span><span class="sxs-lookup"><span data-stu-id="26ec2-103">You can render a report to another file format, such as CSV, Image, PDF, [!INCLUDE[ofprword](../includes/ofprword-md.md)], or [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)], while previewing your report in Report Builder or Report Designer, or you can render the report while viewing the report on the report server.</span></span> <span data-ttu-id="26ec2-104">Das Rendern des Berichts in ein bestimmtes Format ist sinnvoll, wenn Sie den Bericht sofort als anderen Dateityp speichern möchten, ohne ihn auf dem Berichtsserver zu veröffentlichen, oder wenn Sie sehen möchten, wie Ihr Berichtsentwurf den Lesern in einem bestimmten Format angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="26ec2-104">Rendering the report in a specific format in is helpful when you want to immediately save the report as another file type without publishing the report to the report server or when you want to see how your report design will appear when delivered to your report readers in a specific format.</span></span> <span data-ttu-id="26ec2-105">Das Rendern des Berichts auf dem Berichtsserver ist sinnvoll, wenn Sie Abonnements einrichten, Berichte per E-Mail bereitstellen oder einen Bericht speichern möchten, der auf dem Berichtsserver verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="26ec2-105">Rendering the report on the report server is useful when you set up subscriptions or deliver your reports via e-mail, or if you want to save a report that is available on the report server.</span></span> <span data-ttu-id="26ec2-106">Weitere Informationen finden Sie unter [Abonnements und Übermittlung &#40;Reporting Services&#41;](subscriptions/subscriptions-and-delivery-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="26ec2-106">For more information, see [Subscriptions and Delivery &#40;Reporting Services&#41;](subscriptions/subscriptions-and-delivery-reporting-services.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../includes/ssrbrddup-md.md)]  
  
### <a name="to-export-a-report-as-another-file-type-in-report-builder"></a><span data-ttu-id="26ec2-107">So exportieren Sie einen Bericht mit einem anderen Dateityp im Berichts-Generator</span><span class="sxs-lookup"><span data-stu-id="26ec2-107">To export a report as another file type in Report Builder</span></span>  
  
1.  <span data-ttu-id="26ec2-108">Zeigen Sie eine Vorschau des Berichts an.</span><span class="sxs-lookup"><span data-stu-id="26ec2-108">Preview the report.</span></span>  
  
2.  <span data-ttu-id="26ec2-109">Klicken Sie im Menüband auf **Exportieren**.</span><span class="sxs-lookup"><span data-stu-id="26ec2-109">On the ribbon, click **Export**.</span></span>  
  
3.  <span data-ttu-id="26ec2-110">Wählen Sie das Format aus, das Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="26ec2-110">Select the format that you want to use.</span></span>  
  
     <span data-ttu-id="26ec2-111">Das Dialogfeld **Speichern unter** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="26ec2-111">The **Save As** dialog box opens.</span></span> <span data-ttu-id="26ec2-112">Standardmäßig entspricht der Dateiname dem Namen des exportierten Berichts.</span><span class="sxs-lookup"><span data-stu-id="26ec2-112">By default, the file name is that of the report that you exported.</span></span> <span data-ttu-id="26ec2-113">Optional können Sie den Dateinamen ändern.</span><span class="sxs-lookup"><span data-stu-id="26ec2-113">Optionally, you can change the file name.</span></span>  
  
4.  <span data-ttu-id="26ec2-114">Navigieren Sie zur Position, an der Sie den exportierten Bericht gespeichert haben, und öffnen Sie ihn.</span><span class="sxs-lookup"><span data-stu-id="26ec2-114">Navigate to the location where you saved the exported report and open it.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="26ec2-115">Wenn das Programm den Bericht nicht im gewählten Format öffnen kann, weil diesem Dateityp kein Programm zugeordnet ist, werden Sie aufgefordert, den exportierten Bericht zu speichern oder im Internet ein Programm zum Öffnen des Berichts zu suchen.</span><span class="sxs-lookup"><span data-stu-id="26ec2-115">If the program cannot open the report in the format that you chose because you do not have a program associated with this file type, you will be prompted to save the exported report or to find a program online to open the report.</span></span>  
  
### <a name="to-export-a-report-as-another-file-type-in-report-manager"></a><span data-ttu-id="26ec2-116">So exportieren Sie einen Bericht als anderen Dateityp im Berichts-Manager</span><span class="sxs-lookup"><span data-stu-id="26ec2-116">To export a report as another file type in Report Manager</span></span>  
  
1.  <span data-ttu-id="26ec2-117">Navigieren Sie auf der Seite **Home** vom Berichts-Manager aus zum Bericht, den Sie exportieren möchten.</span><span class="sxs-lookup"><span data-stu-id="26ec2-117">From the Report Manager **Home** page, navigate to the report that you want to export.</span></span>  
  
2.  <span data-ttu-id="26ec2-118">Klicken Sie auf den Bericht.</span><span class="sxs-lookup"><span data-stu-id="26ec2-118">Click the report.</span></span>  
  
     <span data-ttu-id="26ec2-119">Der Bericht wird generiert.</span><span class="sxs-lookup"><span data-stu-id="26ec2-119">The report is generated.</span></span>  
  
3.  <span data-ttu-id="26ec2-120">Klicken Sie auf der Berichts-Viewer-Symbolleiste auf den Dropdownpfeil **Format auswählen** .</span><span class="sxs-lookup"><span data-stu-id="26ec2-120">On the Report Viewer toolbar, click the **Select a format** drop-down arrow.</span></span>  
  
4.  <span data-ttu-id="26ec2-121">Wählen Sie das Format aus, das Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="26ec2-121">Select the format that you want to use.</span></span>  
  
5.  <span data-ttu-id="26ec2-122">Klicken Sie auf **Exportieren**.</span><span class="sxs-lookup"><span data-stu-id="26ec2-122">Click **Export**.</span></span>  
  
     <span data-ttu-id="26ec2-123">Eine Meldung wird angezeigt, und Sie werden gefragt, ob Sie die Datei öffnen oder speichern möchten.</span><span class="sxs-lookup"><span data-stu-id="26ec2-123">A message appears asking you if you want to open or save the file.</span></span>  
  
6.  <span data-ttu-id="26ec2-124">Klicken Sie auf **Öffnen**, um den Bericht im ausgewählten Exportformat anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="26ec2-124">To view the report in the selected export format, click **Open**.</span></span>  
  
     <span data-ttu-id="26ec2-125">\- oder -</span><span class="sxs-lookup"><span data-stu-id="26ec2-125">\- or -</span></span>  
  
     <span data-ttu-id="26ec2-126">Klicken Sie auf **Speichern**, um den Bericht sofort im ausgewählten Exportformat zu speichern.</span><span class="sxs-lookup"><span data-stu-id="26ec2-126">To immediately save the report in the selected export format, click **Save**.</span></span>  
  
     <span data-ttu-id="26ec2-127">Der Bericht wird mit der Anwendung, die dem von Ihnen gewählten Format zugeordnet ist, entweder angezeigt oder gespeichert.</span><span class="sxs-lookup"><span data-stu-id="26ec2-127">Using the application that is associated with the format that you chose, the report is either displayed or saved.</span></span> <span data-ttu-id="26ec2-128">Wenn Sie auf **Speichern**klicken, werden Sie aufgefordert, einen Speicherort für Ihren Bericht anzugeben.</span><span class="sxs-lookup"><span data-stu-id="26ec2-128">If you click **Save**, you will be prompted for a location where you can save your report.</span></span>  
  
     <span data-ttu-id="26ec2-129">**Hinweis** Wenn das Programm den Bericht nicht im gewählten Format öffnen kann, weil diesem Dateityp kein Programm zugeordnet ist, werden Sie aufgefordert, den exportierten Bericht zu speichern oder im Internet ein Programm zum Öffnen des Berichts zu suchen.</span><span class="sxs-lookup"><span data-stu-id="26ec2-129">**Note** If the program cannot open the report in the format that you chose because you do not have a program associated with this file type, you will be prompted to save the exported report or to find a program online to open the report.</span></span>  
  
### <a name="to-export-a-report-as-another-file-type-in-a-sharepoint-library"></a><span data-ttu-id="26ec2-130">So exportieren Sie einen Bericht als anderen Dateityp in eine SharePoint-Bibliothek</span><span class="sxs-lookup"><span data-stu-id="26ec2-130">To export a report as another file type in a SharePoint library</span></span>  
  
1.  <span data-ttu-id="26ec2-131">Zeigen Sie eine Vorschau des Berichts an.</span><span class="sxs-lookup"><span data-stu-id="26ec2-131">Preview the report.</span></span>  
  
2.  <span data-ttu-id="26ec2-132">Klicken Sie auf der Symbolleiste auf **Aktionen**, zeigen Sie auf **Exportieren**, und wählen Sie dann das Format aus, das Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="26ec2-132">On the toolbar, click **Actions**, point to **Export**, and then select the format that you want to use.</span></span>  
  
     <span data-ttu-id="26ec2-133">Das Dialogfeld **Dateidownload** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="26ec2-133">The **File Download** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="26ec2-134">Klicken Sie auf **Öffnen**, um den Bericht im ausgewählten Exportformat anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="26ec2-134">To view the report in the selected export format, click **Open**.</span></span>  
  
     <span data-ttu-id="26ec2-135">\- oder -</span><span class="sxs-lookup"><span data-stu-id="26ec2-135">\- or -</span></span>  
  
     <span data-ttu-id="26ec2-136">Klicken Sie auf **Speichern**, um den Bericht sofort im ausgewählten Exportformat zu speichern.</span><span class="sxs-lookup"><span data-stu-id="26ec2-136">To immediately save the report in the selected export format, click **Save**.</span></span>  
  
     <span data-ttu-id="26ec2-137">Der Bericht wird mit der Anwendung, die dem von Ihnen gewählten Format zugeordnet ist, entweder angezeigt oder gespeichert.</span><span class="sxs-lookup"><span data-stu-id="26ec2-137">Using the application that is associated with the format that you chose, the report is either displayed or saved.</span></span> <span data-ttu-id="26ec2-138">Wenn Sie auf **Speichern**klicken, werden Sie aufgefordert, einen Speicherort für Ihren Bericht anzugeben.</span><span class="sxs-lookup"><span data-stu-id="26ec2-138">If you click **Save**, you will be prompted for a location where you can save your report.</span></span>  
  
     <span data-ttu-id="26ec2-139">Sie können den Dateinamen des exportierten Berichts ändern.</span><span class="sxs-lookup"><span data-stu-id="26ec2-139">Optionally, change the file name of the exported report.</span></span>  
  
     <span data-ttu-id="26ec2-140">**Hinweis** Wenn das Programm den Bericht nicht im gewählten Format öffnen kann, weil diesem Dateityp kein Programm zugeordnet ist, werden Sie aufgefordert, den exportierten Bericht zu speichern oder im Internet ein Programm zum Öffnen des Berichts zu suchen.</span><span class="sxs-lookup"><span data-stu-id="26ec2-140">**Note** If the program cannot open the report in the format that you chose because you do not have a program associated with this file type, you will be prompted to save the exported report or to find a program online to open the report.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26ec2-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="26ec2-141">See Also</span></span>  
 <span data-ttu-id="26ec2-142">[Exportieren von Berichten &#40;Berichts-Generator und SSRS&#41;](report-builder/export-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="26ec2-142">[Exporting Reports &#40;Report Builder and SSRS&#41;](report-builder/export-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="26ec2-143">[Paginierung in Reporting Services &#40;Berichts-Generator und SSRS&#41;](report-design/pagination-in-reporting-services-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="26ec2-143">[Pagination in Reporting Services &#40;Report Builder  and SSRS&#41;](report-design/pagination-in-reporting-services-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="26ec2-144">Interaktive Funktionalität für verschiedene Berichtsrenderingerweiterungen &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="26ec2-144">Interactive Functionality for Different Report Rendering Extensions &#40;Report Builder and SSRS&#41;</span></span>](report-builder/interactive-functionality-different-report-rendering-extensions.md)  
  
  
