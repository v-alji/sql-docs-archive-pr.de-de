---
title: Ausblenden einer Seiten Kopfzeile oder-Fußzeile auf der ersten oder letzten Seite (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f87ce79b-00d7-4458-a17e-e253a20f720d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 60c8789fd098df7347e9cc0f583426478aee06e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695318"
---
# <a name="hide-a-page-header-or-footer-on-the-first-or-last-page-report-builder-and-ssrs"></a><span data-ttu-id="b67c8-102">Ausblenden einer Seitenkopf- oder Seitenfußzeile auf der ersten oder letzten Seite (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="b67c8-102">Hide a Page Header or Footer on the First or Last Page (Report Builder and SSRS)</span></span>
  <span data-ttu-id="b67c8-103">Ein Bericht kann eine Seitenkopf- und Seitenfußzeile enthalten, die am oberen bzw. unteren Rand jeder Seite verläuft.</span><span class="sxs-lookup"><span data-stu-id="b67c8-103">A report can contain a page header and page footer that run along the top and bottom of each page, respectively.</span></span> <span data-ttu-id="b67c8-104">Nachdem Sie eine Kopf- bzw. Fußzeile hinzugefügt haben, können Sie sie selektiv auf der ersten und letzten Seite des Berichts ausblenden.</span><span class="sxs-lookup"><span data-stu-id="b67c8-104">After you a add a header or footer, you can selectively hide it on the first and last pages of a report.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-hide-a-page-header-on-the-first-or-last-page"></a><span data-ttu-id="b67c8-105">So blenden Sie einen Seitenkopf auf der ersten oder letzten Seite aus</span><span class="sxs-lookup"><span data-stu-id="b67c8-105">To hide a page header on the first or last page</span></span>  
  
1.  <span data-ttu-id="b67c8-106">Öffnen Sie einen Bericht in der Entwurfsansicht.</span><span class="sxs-lookup"><span data-stu-id="b67c8-106">Open a report in Design view.</span></span>  
  
2.  <span data-ttu-id="b67c8-107">Klicken Sie mit der rechten Maustaste auf den Seitenkopf, und klicken Sie anschließend auf **Kopfzeileneigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="b67c8-107">Right-click the page header, and then click **Header Properties**.</span></span> <span data-ttu-id="b67c8-108">Das Dialogfeld **Berichtskopfeigenschaften** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="b67c8-108">The **Report Header Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="b67c8-109">Vergewissern Sie sich, dass die Option **Header für diesen Bericht anzeigen** nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="b67c8-109">Verify that **Display header for this report** is not selected.</span></span>  
  
4.  <span data-ttu-id="b67c8-110">Deaktivieren Sie im Abschnitt **Druckoptionen** das Kontrollkästchen für jede einzelne Option, um die Anzeige auf der ersten oder letzten Berichtsseite auszublenden.</span><span class="sxs-lookup"><span data-stu-id="b67c8-110">In the **Print options** section, clear the check box for each option to hide the display on the first or last page of the report.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-hide-a-page-footer-on-the-first-or-last-page"></a><span data-ttu-id="b67c8-111">So blenden Sie einen Seitenfuß auf der ersten oder letzten Seite aus</span><span class="sxs-lookup"><span data-stu-id="b67c8-111">To hide a page footer on the first or last page</span></span>  
  
1.  <span data-ttu-id="b67c8-112">Öffnen Sie einen Bericht in der Entwurfsansicht.</span><span class="sxs-lookup"><span data-stu-id="b67c8-112">Open a report in Design view.</span></span>  
  
2.  <span data-ttu-id="b67c8-113">Klicken Sie mit der rechten Maustaste auf den Seitenfuß, und klicken Sie anschließend auf **Fußzeileneigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="b67c8-113">Right-click the page footer, and then click **Footer Properties**.</span></span> <span data-ttu-id="b67c8-114">Das Dialogfeld **Berichtsfußeigenschaften** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="b67c8-114">The **Report Footer Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="b67c8-115">Vergewissern Sie sich, dass die Option **Seitenfuß für diesen Bericht anzeigen** nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="b67c8-115">Verify that **Display footer for this report** is not selected.</span></span>  
  
4.  <span data-ttu-id="b67c8-116">Deaktivieren Sie im Abschnitt **Druckoptionen** das Kontrollkästchen für jede einzelne Option, um die Anzeige auf der ersten oder letzten Berichtsseite auszublenden.</span><span class="sxs-lookup"><span data-stu-id="b67c8-116">In the **Print options** section, clear the check box for each option to hide the display on the first or last page of the report.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b67c8-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b67c8-117">See Also</span></span>  
 <span data-ttu-id="b67c8-118">[Seitenkopf- und Seitenfußzeilen &#40;Berichts-Generator und SSRS&#41;](page-headers-and-footers-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b67c8-118">[Page Headers and Footers &#40;Report Builder and SSRS&#41;](page-headers-and-footers-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="b67c8-119">[Paginierung in Reporting Services &#40;Berichts-Generator und SSRS&#41;](pagination-in-reporting-services-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b67c8-119">[Pagination in Reporting Services &#40;Report Builder  and SSRS&#41;](pagination-in-reporting-services-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="b67c8-120">Hinzufügen oder Entfernen einer Seitenkopf- oder Seitenfußzeile &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="b67c8-120">Add or Remove a Page Header or Footer &#40;Report Builder and SSRS&#41;</span></span>](add-or-remove-a-page-header-or-footer-report-builder-and-ssrs.md)  
  
  
