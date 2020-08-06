---
title: Hinzufügen eines Links zu einer URL (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d3392c0b-7b62-4d27-bc04-2bd0c5487d08
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d3db3fc75feca1393e73e698f44db633f09e8dc1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697546"
---
# <a name="add-a-hyperlink-to-a-url-report-builder-and-ssrs"></a><span data-ttu-id="cdb25-102">Hinzufügen eines Links zu einer URL (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="cdb25-102">Add a Hyperlink to a URL (Report Builder and SSRS)</span></span>
  <span data-ttu-id="cdb25-103">Sie können einem Berichtselement einen Hyperlink hinzufügen, wenn Benutzer in der Lage sein sollen, in einem Bericht auf einen Link zu klicken und einen Browser mit der von Ihnen angegebenen URL zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="cdb25-103">You can add a hyperlink to a report item when you want your users to be able to click a link in a report and open a browser to the URL that you specify.</span></span> <span data-ttu-id="cdb25-104">Ein Link kann eine statische URL sein oder ein Ausdruck, der zu einer URL ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="cdb25-104">A hyperlink can be a static URL or an expression that evaluates to a URL.</span></span> <span data-ttu-id="cdb25-105">Wenn ein Feld in einer Datenbank URLs enthält, kann der Ausdruck dieses Feld enthalten, wodurch eine dynamische Liste von Links in dem Bericht entsteht.</span><span class="sxs-lookup"><span data-stu-id="cdb25-105">If you have a field in a database that contains URLs, the expression can contain that field, resulting in a dynamic list of hyperlinks in the report.</span></span> <span data-ttu-id="cdb25-106">Links können Textfeldern, Bildern, Diagrammen und Messgeräten hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="cdb25-106">You can add hyperlinks to text boxes, images, charts, and gauges.</span></span> <span data-ttu-id="cdb25-107">Sie müssen sicherstellen, dass der Benutzer Zugriff auf die URL hat, die Sie bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="cdb25-107">You must ensure that the user has access to the URL that you provide.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
 <span data-ttu-id="cdb25-108">Sie können auch URLs zu Berichten auf beliebigen Berichtsservern angeben, für die Sie und Ihre Benutzer über eine Leseberechtigung verfügen, indem Sie URL-Anforderungen an den Berichtsserver verwenden.</span><span class="sxs-lookup"><span data-stu-id="cdb25-108">You can also specify URLs to reports on any report server that you and your users have permission to view using URL requests to the report server.</span></span> <span data-ttu-id="cdb25-109">Sie können z. B. einen Bericht angeben und die Dokumentstruktur für Benutzer ausblenden, wenn diese den Bericht zum ersten Mal anzeigen.</span><span class="sxs-lookup"><span data-stu-id="cdb25-109">For example, you can specify a report and hide the document map for the user when they first view the report.</span></span> <span data-ttu-id="cdb25-110">Weitere Informationen finden Sie unter [URL-Zugriff &#40;SSRS&#41;](../url-access-ssrs.md) in der [Reporting Services-Dokumentation](https://go.microsoft.com/fwlink/?linkid=121312) in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="cdb25-110">For more information, see [URL Access &#40;SSRS&#41;](../url-access-ssrs.md) in the [Reporting Services documentation](https://go.microsoft.com/fwlink/?linkid=121312) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="cdb25-111">Ein Link zu einer URL kann jedem Element hinzugefügt werden, das über eine **Action** -Eigenschaft verfügt, z. B. ein Textfeld, ein Bild oder eine berechnete Reihe in einem Diagramm.</span><span class="sxs-lookup"><span data-stu-id="cdb25-111">You can add a hyperlink to a URL to any item that has an **Action** property, for example, a text box, an image, or a calculated series in a chart.</span></span> <span data-ttu-id="cdb25-112">Wenn der Benutzer auf das Berichtselement klickt, wird die von Ihnen definierte Aktion ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="cdb25-112">When the user clicks that report item, the action that you define takes place.</span></span> <span data-ttu-id="cdb25-113">Weitere Informationen finden Sie unter [Aktionseigenschaften &#40;Dialogfeld, Berichts-Generator und SSRS&#41;](../action-properties-dialog-box-report-builder-and-ssrs.md) und [Angeben von Pfaden zu externen Elementen &#40;Berichts-Generator und SSRS&#41;](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="cdb25-113">For more information, see the [Action Properties Dialog Box &#40;Report Builder and SSRS&#41;](../action-properties-dialog-box-report-builder-and-ssrs.md) and [Specifying Paths to External Items &#40;Report Builder and SSRS&#41;](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="cdb25-114">Eine schnelle Einführung finden Sie unter [Tutorial: Formatieren von Text &#40;Berichts-Generator&#41;](../tutorial-format-text-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="cdb25-114">To quickly get started, see [Tutorial: Format Text &#40;Report Builder&#41;](../tutorial-format-text-report-builder.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cdb25-115">Links, die an Datasetfelder gebunden sind, sind unter Umständen anfällig für böswillige Manipulationen.</span><span class="sxs-lookup"><span data-stu-id="cdb25-115">Links that are bound to dataset fields can be vulnerable to tampering for malicious purposes.</span></span> <span data-ttu-id="cdb25-116">Weitere Informationen finden Sie unter [Sichern von Berichten und Ressourcen](../security/secure-reports-and-resources.md) in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-[Onlinedokumentation](https://go.microsoft.com/fwlink/?LinkId=154888) auf msdn.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="cdb25-116">For more information, see [Secure Reports and Resources](../security/secure-reports-and-resources.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][Books Online](https://go.microsoft.com/fwlink/?LinkId=154888) on msdn.microsoft.com.</span></span>  
  
### <a name="to-add-a-hyperlink"></a><span data-ttu-id="cdb25-117">So fügen Sie einen Link hinzu</span><span class="sxs-lookup"><span data-stu-id="cdb25-117">To add a hyperlink</span></span>  
  
1.  <span data-ttu-id="cdb25-118">Klicken Sie in der Berichtsentwurfsansicht mit der rechten Maustaste auf das Textfeld, Bild oder Diagramm, dem Sie einen Link hinzufügen möchten, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="cdb25-118">In report design view, right-click the text box, image, or chart to which you want to add a link and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="cdb25-119">Klicken Sie im Dialogfeld **Eigenschaften**auf Aktion.</span><span class="sxs-lookup"><span data-stu-id="cdb25-119">In the Properties dialog box, click **Action**.</span></span>  
  
3.  <span data-ttu-id="cdb25-120">Wählen Sie **Gehe zu URL**.</span><span class="sxs-lookup"><span data-stu-id="cdb25-120">Select **Go to URL**.</span></span> <span data-ttu-id="cdb25-121">Im Dialogfeld für diese Option wird ein zusätzlicher Abschnitt angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cdb25-121">An additional section appears in the dialog box for this option.</span></span>  
  
4.  <span data-ttu-id="cdb25-122">Geben Sie in **URL auswählen**eine URL oder einen Ausdruck, der eine URL ergibt, ein (bzw. wählen Sie diese aus), oder klicken Sie auf den Dropdownpfeil, und klicken Sie auf den Namen eines Felds, das eine URL enthält.</span><span class="sxs-lookup"><span data-stu-id="cdb25-122">In **Select URL**, type or select a URL or an expression that evaluates to a URL, or click the drop-down arrow and click the name of a field that contains a URL.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="cdb25-123">(Optional) Der Text wird nicht automatisch als Link formatiert.</span><span class="sxs-lookup"><span data-stu-id="cdb25-123">(Optional) The text is not automatically formatted as a link.</span></span> <span data-ttu-id="cdb25-124">Es empfiehlt sich, die Farbe und den Effekt des Texts zu ändern, um zu verdeutlichen, dass es sich um einen Link handelt.</span><span class="sxs-lookup"><span data-stu-id="cdb25-124">For text, it is helpful to change the color and effect of the text to indicate that the text is a link.</span></span> <span data-ttu-id="cdb25-125">Ändern Sie im Abschnitt **Schriftart** auf der Registerkarte "Home" des Menübands z. B. die Farbe in Blau und den Effekt in "Unterstrichen".</span><span class="sxs-lookup"><span data-stu-id="cdb25-125">For example, change the color to blue and the effect to underline in the **Font** section in the Home tab of the Ribbon.</span></span>  
  
7.  <span data-ttu-id="cdb25-126">Klicken Sie zum Testen des Links auf **Ausführen** , um eine Vorschau des Berichts anzuzeigen, und klicken Sie dann auf das Berichtselement, für das Sie den Link festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="cdb25-126">To test the link, click **Run** to preview the report, and then click the report item that you set this link on.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdb25-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cdb25-127">See Also</span></span>  
 <span data-ttu-id="cdb25-128">[Interaktive Sortierung, Dokument Strukturen und Verknüpfungen &#40;Berichts-Generator und SSRS&#41;](interactive-sort-document-maps-and-links-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="cdb25-128">[Interactive Sort, Document Maps, and Links &#40;Report Builder and SSRS&#41;](interactive-sort-document-maps-and-links-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="cdb25-129">Erstellen einer Dokumentstruktur &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="cdb25-129">Create a Document Map &#40;Report Builder and SSRS&#41;</span></span>](create-a-document-map-report-builder-and-ssrs.md)  
  
  
