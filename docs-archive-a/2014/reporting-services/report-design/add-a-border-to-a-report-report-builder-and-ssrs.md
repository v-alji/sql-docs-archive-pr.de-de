---
title: Hinzufügen eines Lesezeichens zu einem Bericht (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 81412f94-2991-4e58-bc05-5ccc0cbf2a75
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bf4a0c2c117774a0f3b25ca0644796fd067bc971
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723482"
---
# <a name="add-a-border-to-a-report-report-builder-and-ssrs"></a><span data-ttu-id="7b704-102">Hinzufügen eines Rahmens zu einem Bericht (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="7b704-102">Add a Border to a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="7b704-103">Sie können einem Bericht ohne Hinzufügen von Linien oder Rechtecken einen Rahmen hinzufügen, indem Sie Kopfzeilen, Fußzeilen und dem Berichtshauptteil selbst Rahmen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="7b704-103">You can add a border to a report by adding borders to the headers, footers, and report body themselves, without adding lines or rectangles.</span></span>  
  
 <span data-ttu-id="7b704-104">Wenn Sie einen Berichtsrahmen hinzufügen, der in der Seitenkopf- oder -fußzeile angezeigt wird, unterdrücken Sie nicht die Kopf- und Fußzeile auf der ersten und letzten Seite des Berichts.</span><span class="sxs-lookup"><span data-stu-id="7b704-104">If you add a report border that appears on the page header and footer, do not suppress the header and footer on the first and last pages of the report.</span></span> <span data-ttu-id="7b704-105">In diesem Fall kann der Rahmen u. U. oben oder unten auf der ersten und letzten Seite des Berichts abgeschnitten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="7b704-105">If you do, the border may appear cut off at the top or bottom of the first and last pages of the report.</span></span> <span data-ttu-id="7b704-106">Weitere Informationen finden Sie unter [Seitenkopf- und Seitenfußzeilen (Berichts-Generator und SSRS)](page-headers-and-footers-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="7b704-106">For more information, see [Page Headers and Footers &#40;Report Builder and SSRS&#41;](page-headers-and-footers-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-border-to-a-report"></a><span data-ttu-id="7b704-107">So fügen Sie einem Bericht einen Rahmen hinzu</span><span class="sxs-lookup"><span data-stu-id="7b704-107">To add a border to a report</span></span>  
  
1.  <span data-ttu-id="7b704-108">Klicken Sie mit der rechten Maustaste außerhalb irgendeines Elements auf die Kopfzeile, und klicken Sie anschließend auf **Kopfzeileneigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="7b704-108">Right-click in the header outside any items in the header, and click **Header Properties**.</span></span> <span data-ttu-id="7b704-109">Fügen Sie auf der Registerkarte **Rahmen** einen linken, oberen und rechten Rahmen in dem gewünschten Format hinzu.</span><span class="sxs-lookup"><span data-stu-id="7b704-109">On the **Border** tab, add a left, top, and right border with the style you want.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7b704-110"> Wenn Sie in Ihrem Bericht keine Kopfzeilen verwenden, können Sie Rahmen nur um den Berichtshauptteil platzieren. Sie können auch auf der Registerkarte **Einfügen** Kopfzeilen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="7b704-110">If you do not use headers in your report, you can place borders around just the report body, or you can add headers from the **Insert** tab.</span></span>  
  
2.  <span data-ttu-id="7b704-111">Klicken Sie im Hauptteil mit der rechten Maustaste außerhalb irgendeines Elements auf die Entwurfsoberfläche, und klicken Sie auf **Eigenschaften des Hauptteils**.</span><span class="sxs-lookup"><span data-stu-id="7b704-111">Right-click in the body outside any items on the design surface, and click **Body Properties**.</span></span> <span data-ttu-id="7b704-112">Fügen Sie auf der Registerkarte **Rahmen** einen linken und rechten Rahmen in dem gewünschten Format hinzu.</span><span class="sxs-lookup"><span data-stu-id="7b704-112">On the **Border** tab, add a left and right border with the style you want.</span></span>  
  
3.  <span data-ttu-id="7b704-113">Klicken Sie mit der rechten Maustaste außerhalb irgendeines Elements auf die Fußzeile, und klicken Sie anschließend auf **Fußzeileneigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="7b704-113">Right-click in the footer outside any items in the footer, and click **Footer Properties**.</span></span> <span data-ttu-id="7b704-114">Fügen Sie auf der Registerkarte **Rahmen** einen linken, unteren und rechten Rahmen in dem gewünschten Format hinzu.</span><span class="sxs-lookup"><span data-stu-id="7b704-114">On the **Border** tab, add a left, bottom, and right border with the style you want.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b704-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7b704-115">See Also</span></span>  
 [<span data-ttu-id="7b704-116">Rechtecke und Linien &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="7b704-116">Rectangles and Lines &#40;Report Builder and SSRS&#41;</span></span>](rectangles-and-lines-report-builder-and-ssrs.md)  
  
  
