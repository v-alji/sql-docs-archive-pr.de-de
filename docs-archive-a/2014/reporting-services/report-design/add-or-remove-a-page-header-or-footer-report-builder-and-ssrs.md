---
title: Hinzufügen oder Entfernen einer Seitenkopf- oder Seitenfußzeile (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 72988623-fee8-4a05-9f72-8fcb8e668576
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b29db3f72323c460360c872a0f60d13a808e3e05
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719591"
---
# <a name="add-or-remove-a-page-header-or-footer-report-builder-and-ssrs"></a><span data-ttu-id="56b3c-102">Hinzufügen oder Entfernen einer Seitenkopf- oder Seitenfußzeile (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="56b3c-102">Add or Remove a Page Header or Footer (Report Builder and SSRS)</span></span>
  <span data-ttu-id="56b3c-103">Sie können statischen Text, Bilder, Linien, Rechtecke und Rahmen zu Seitenköpfen und -füßen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="56b3c-103">You can add static text, images, lines, rectangles, and borders to page headers or footers.</span></span> <span data-ttu-id="56b3c-104">Wenn Sie variable oder berechnete Daten in einem Seitenkopf oder -fuß verwenden möchten, können Sie Ausdrücke und datengebundene Bilder in einem Textfeld platzieren.</span><span class="sxs-lookup"><span data-stu-id="56b3c-104">You can place expressions and data-bound images in a textbox if you want variable or computed data in a header or footer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="56b3c-105">Seitenköpfe und -füße werden von den einzelnen Renderingerweiterungen unterschiedlich verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="56b3c-105">Each rendering extension processes page headers and footers differently.</span></span> <span data-ttu-id="56b3c-106">Weitere Informationen finden Sie unter [Seitenkopf- und Seitenfußzeilen (Berichts-Generator und SSRS)](page-headers-and-footers-report-builder-and-ssrs.md) und [Paginierung in Reporting Services (Berichts-Generator und SSRS)](pagination-in-reporting-services-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="56b3c-106">For more information, see [Page Headers and Footers &#40;Report Builder and SSRS&#41;](page-headers-and-footers-report-builder-and-ssrs.md) and [Pagination in Reporting Services &#40;Report Builder  and SSRS&#41;](pagination-in-reporting-services-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-page-header-or-footer"></a><span data-ttu-id="56b3c-107">So fügen Sie einen Seitenkopf oder -fuß hinzu</span><span class="sxs-lookup"><span data-stu-id="56b3c-107">To add a page header or footer</span></span>  
  
1.  <span data-ttu-id="56b3c-108">Öffnen Sie einen Bericht.</span><span class="sxs-lookup"><span data-stu-id="56b3c-108">Open a report.</span></span>  
  
2.  <span data-ttu-id="56b3c-109">Klicken Sie auf der Entwurfsoberfläche mit der rechten Maustaste auf den Bericht, zeigen Sie auf **Einfügen**, und klicken Sie anschließend auf **Kopfzeile** oder **Fußzeile**.</span><span class="sxs-lookup"><span data-stu-id="56b3c-109">On the design surface, right-click the report, point to **Insert**, and then click **Header** or **Footer**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="56b3c-110">Die Optionen **Kopfzeile** und **Fußzeile** werden nur angezeigt, wenn ein Seitenkopf oder Seitenfuß nicht bereits zum Bericht gehört.</span><span class="sxs-lookup"><span data-stu-id="56b3c-110">The **Header** and **Footer** options appear only when a header or footer is not already part of the report.</span></span>  
  
### <a name="to-configure-a-page-header-or-footer"></a><span data-ttu-id="56b3c-111">So konfigurieren Sie eine Seitenkopf- oder Seitenfußzeile</span><span class="sxs-lookup"><span data-stu-id="56b3c-111">To configure a page header or footer</span></span>  
  
1.  <span data-ttu-id="56b3c-112">Klicken Sie auf der Entwurfsoberfläche mit der rechten Maustaste auf die Seitenkopf- oder -fußzeile.</span><span class="sxs-lookup"><span data-stu-id="56b3c-112">On the design surface, right-click the page header or footer.</span></span>  
  
2.  <span data-ttu-id="56b3c-113">Zeigen Sie auf **Einfügen**, und klicken Sie dann auf eines der folgenden Elemente, um es dem Kopf- oder Fußzeilenbereich hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="56b3c-113">Point to **Insert**, and then click one of the following items to add it to the header or footer area:</span></span>  
  
    -   <span data-ttu-id="56b3c-114">**Textfeld**</span><span class="sxs-lookup"><span data-stu-id="56b3c-114">**Textbox**</span></span>  
  
    -   <span data-ttu-id="56b3c-115">**Linie**</span><span class="sxs-lookup"><span data-stu-id="56b3c-115">**Line**</span></span>  
  
    -   <span data-ttu-id="56b3c-116">**Rechteck**</span><span class="sxs-lookup"><span data-stu-id="56b3c-116">**Rectangle**</span></span>  
  
    -   <span data-ttu-id="56b3c-117">**Image**</span><span class="sxs-lookup"><span data-stu-id="56b3c-117">**Image**</span></span>  
  
3.  <span data-ttu-id="56b3c-118">Klicken Sie mit der rechten Maustaste auf den Seitenkopf, und klicken Sie anschließend auf **Seitenkopfeigenschaften** , um Rahmen, Hintergrundbilder oder Farben hinzuzufügen oder die Breite des Seitenkopfes anzupassen.</span><span class="sxs-lookup"><span data-stu-id="56b3c-118">Right-click the page header, and then click **Header Properties** to add borders, background images, or colors, or to adjust the width of the header.</span></span> <span data-ttu-id="56b3c-119">Klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="56b3c-119">Then click **OK**.</span></span>  
  
4.  <span data-ttu-id="56b3c-120">Klicken Sie mit der rechten Maustaste auf den Seitenfuß, und klicken Sie anschließend auf **Fußzeileneigenschaften** , um Rahmen, Hintergrundbilder oder Farben hinzuzufügen oder die Breite des Seitenfußes anzupassen.</span><span class="sxs-lookup"><span data-stu-id="56b3c-120">Right-click the page footer, and then click **Footer Properties** to add borders, background images, or colors, or to adjust the width of the footer.</span></span> <span data-ttu-id="56b3c-121">Klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="56b3c-121">Then click **OK**.</span></span>  
  
### <a name="to-remove-a-page-header-or-footer"></a><span data-ttu-id="56b3c-122">So entfernen Sie einen Seitenkopf oder -fuß</span><span class="sxs-lookup"><span data-stu-id="56b3c-122">To remove a page header or footer</span></span>  
  
1.  <span data-ttu-id="56b3c-123">Öffnen Sie einen Bericht.</span><span class="sxs-lookup"><span data-stu-id="56b3c-123">Open a report.</span></span>  
  
2.  <span data-ttu-id="56b3c-124">Klicken Sie auf der Entwurfsoberfläche mit der rechten Maustaste auf den Seitenkopf oder -fuß, und klicken Sie anschließend auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="56b3c-124">On the design surface, right-click the page header or footer, and then click **Delete**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="56b3c-125">Wenn Sie einen Seitenkopf oder -fuß entfernen, wird er aus dem Bericht gelöscht.</span><span class="sxs-lookup"><span data-stu-id="56b3c-125">When you remove a page header or footer, you delete it from the report.</span></span> <span data-ttu-id="56b3c-126">Alle Elemente, die Sie zuvor zum Seitenkopf oder -fuß hinzugefügt haben, werden nicht erneut angezeigt, wenn Sie den Seitenkopf oder -fuß anschließend wieder hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="56b3c-126">Any items that you previously added to the page header or footer will not reappear if you subsequently add the header or footer again.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56b3c-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="56b3c-127">See Also</span></span>  
 [<span data-ttu-id="56b3c-128">Seitenkopf- und Seitenfußzeilen &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="56b3c-128">Page Headers and Footers &#40;Report Builder and SSRS&#41;</span></span>](page-headers-and-footers-report-builder-and-ssrs.md)  
  
  
