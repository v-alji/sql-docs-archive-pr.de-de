---
title: Suchen nach Updates oder Deaktivieren von Updates (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 9c69792d-d7c4-453b-ae2f-6d2d071d8606
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 088d41e71d770f746367f2760cff8ff67b15623c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617796"
---
# <a name="check-for-updates-or-turn-updates-off-report-builder-and-ssrs"></a><span data-ttu-id="dd938-102">Suchen nach Updates oder Deaktivieren von Updates (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="dd938-102">Check for Updates or Turn Updates Off (Report Builder and SSRS)</span></span>
  <span data-ttu-id="dd938-103">Jedes Mal, wenn Sie einen Bericht öffnen, überprüft der Berichts-Generator, ob die veröffentlichten Instanzen der Berichtsteile in diesem Bericht auf dem Berichtsserver oder auf der in den Berichtsserver integrierten SharePoint-Website aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="dd938-103">Every time you open a report, Report Builder checks to see if the published instances of report parts in that report have been updated on the report server or SharePoint site integrated with a report server.</span></span> <span data-ttu-id="dd938-104">Er überprüft auch Änderungen in den abhängigen Elementen des Berichtsteils, z. B. im Dataset und den Parametern.</span><span class="sxs-lookup"><span data-stu-id="dd938-104">It also checks for changes in the report parts' dependent items, such as the dataset and parameters.</span></span> <span data-ttu-id="dd938-105">Wenn Berichtsteile oder ihre Abhängigkeiten auf der Website oder dem Server aktualisiert wurden, zeigt eine Informationsleiste im Bericht die Anzahl der aktualisierten Teile an.</span><span class="sxs-lookup"><span data-stu-id="dd938-105">If any report parts or their dependencies have been updated on the site or server, an information bar in your report displays the number of updated parts.</span></span> <span data-ttu-id="dd938-106">Sie können die Updates anzeigen und akzeptieren oder ablehnen oder die Informationsleiste schließen.</span><span class="sxs-lookup"><span data-stu-id="dd938-106">You can choose to view and accept or reject the updates, or dismiss the information bar.</span></span>  
  
 <span data-ttu-id="dd938-107">Sie können auch die Informationsleiste deaktivieren. In diesem Fall werden Sie nicht darüber informiert, wenn veröffentlichte Instanzen der Berichtsteile sich geändert haben.</span><span class="sxs-lookup"><span data-stu-id="dd938-107">You can also disable the information bar and not be informed if published instances of report parts have changed.</span></span> <span data-ttu-id="dd938-108">Dies ist eine Benutzereinstellung; sie wird für alle Berichte deaktiviert, die Sie öffnen.</span><span class="sxs-lookup"><span data-stu-id="dd938-108">This is a user setting; it will be disabled for all reports that you open.</span></span> <span data-ttu-id="dd938-109">Auch wenn Sie die Informationsleiste deaktiviert haben, können Sie weiterhin nach Updates suchen.</span><span class="sxs-lookup"><span data-stu-id="dd938-109">Even if you have disabled the information bar, you can still check for updates.</span></span>  
  
### <a name="to-turn-on-and-off-report-part-updates"></a><span data-ttu-id="dd938-110">So aktivieren und deaktivieren Sie Updates von Berichtsteilen</span><span class="sxs-lookup"><span data-stu-id="dd938-110">To turn on and off report part updates</span></span>  
  
1.  <span data-ttu-id="dd938-111">Klicken Sie auf die Schaltfläche Berichts-Generator, und klicken Sie dann auf **Optionen**.</span><span class="sxs-lookup"><span data-stu-id="dd938-111">Click the Report Builder button, and then click **Options**.</span></span>  
  
2.  <span data-ttu-id="dd938-112">Aktivieren bzw. deaktivieren Sie im Dialogfeld **Optionen** auf der Registerkarte **Ressourcen** das Kontrollkästchen **Updates für Berichts Teile in meinen Berichten anzeigen** .</span><span class="sxs-lookup"><span data-stu-id="dd938-112">In the **Options** dialog box, on the **Resources** tab, select or clear the **Show updates to report parts in my reports** check box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dd938-113">Dies ist eine Benutzereinstellung.</span><span class="sxs-lookup"><span data-stu-id="dd938-113">This is a user setting.</span></span> <span data-ttu-id="dd938-114">Sie wird für alle Berichte deaktiviert, die Sie öffnen.</span><span class="sxs-lookup"><span data-stu-id="dd938-114">It will be disabled for all reports that you open.</span></span>  
  
### <a name="to-check-for-updates"></a><span data-ttu-id="dd938-115">So überprüfen Sie auf Updates</span><span class="sxs-lookup"><span data-stu-id="dd938-115">To check for updates</span></span>  
  
-   <span data-ttu-id="dd938-116">Klicken Sie mit der rechten Maustaste auf die Entwurfs Oberfläche außerhalb des Berichts oder im Hauptteil des Berichts, und klicken Sie auf **nach Updates suchen**.</span><span class="sxs-lookup"><span data-stu-id="dd938-116">Right-click the design surface outside the report, or in the report body, and click **Check for Updates**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd938-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dd938-117">See Also</span></span>  
 <span data-ttu-id="dd938-118">[Berichts Teile &#40;Berichts-Generator und SSRS&#41;](report-parts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="dd938-118">[Report Parts &#40;Report Builder and SSRS&#41;](report-parts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="dd938-119">[Berichts Teile &#40;Berichts-Generator und SSRS veröffentlichen und erneut veröffentlichen&#41;](report-design/publish-and-republish-report-parts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="dd938-119">[Publish and Republish Report Parts &#40;Report Builder and SSRS&#41;](report-design/publish-and-republish-report-parts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="dd938-120">[Suchen nach Berichts teilen und Festlegen eines Standard Ordners &#40;Berichts-Generator und SSRS&#41;](report-design/browse-for-report-parts-and-set-a-default-folder-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="dd938-120">[Browse for Report Parts and Set a Default Folder &#40;Report Builder and SSRS&#41;](report-design/browse-for-report-parts-and-set-a-default-folder-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="dd938-121">[Problembehandlung bei Berichts teilen &#40;Berichts-Generator und SSRS&#41;](../../2014/reporting-services/troubleshoot-report-parts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="dd938-121">[Troubleshoot Report Parts &#40;Report Builder and SSRS&#41;](../../2014/reporting-services/troubleshoot-report-parts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="dd938-122">Berichtsteile und Datasets in Berichts-Generator</span><span class="sxs-lookup"><span data-stu-id="dd938-122">Report Parts and Datasets in Report Builder</span></span>](report-data/report-parts-and-datasets-in-report-builder.md)  
  
  
