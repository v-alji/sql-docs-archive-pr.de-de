---
title: Ändern von Indikatorsymbolen und Indikatorsätzen (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 8a056adf-4473-473d-9b0c-314675af7bfd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 398d21319ab6da22f2b10c3607baf8f110d6e65b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722526"
---
# <a name="change-indicator-icons-and-indicator-sets-report-builder-and-ssrs"></a><span data-ttu-id="03efd-102">Ändern von Indikatorsymbolen und Indikatorsätzen (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="03efd-102">Change Indicator Icons and Indicator Sets (Report Builder and SSRS)</span></span>
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]<span data-ttu-id="03efd-103">bietet vorkonfigurierte Indikatorensätze, die Ihre Daten möglicherweise nicht immer effektiv darstellen und im übermittelten Bericht gut funktionieren.</span><span class="sxs-lookup"><span data-stu-id="03efd-103">provides preconfigured indicators sets, which might not always depict your data effectively and work well in the delivered report.</span></span> <span data-ttu-id="03efd-104">Dieses Thema enthält Vorgehensweisen, um die Darstellung von Indikatorsymbolen zu ändern und die Indikatorsätze anzupassen, sodass andere, mehr oder weniger Indikatorsymbole enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="03efd-104">This topic provides procedures to change the appearance of indicator icons and change the indicator sets to include different, more, or fewer indicator icons.</span></span>  
  
 <span data-ttu-id="03efd-105">Optionen wie Farben können mit Ausdrücken festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="03efd-105">Options such as colors can be set by using expressions.</span></span> <span data-ttu-id="03efd-106">Weitere Informationen finden Sie unter [Ausdrücke &#40;Berichts-Generator und SSRS&#41;](expressions-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="03efd-106">For more information, see [Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-change-the-color-of-an-indicator-icon"></a><span data-ttu-id="03efd-107">So ändern Sie die Farbe eines Indikatorsymbols</span><span class="sxs-lookup"><span data-stu-id="03efd-107">To change the color of an indicator icon</span></span>  
  
1.  <span data-ttu-id="03efd-108">Klicken Sie mit der rechten Maustaste auf den Indikator, der geändert werden soll, und klicken Sie auf **Indikatoreigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="03efd-108">Right-click the indicator you want to change and click **Indicator Properties**.</span></span>  
  
2.  <span data-ttu-id="03efd-109">Klicken Sie im linken Bereich auf **Wert und Status** .</span><span class="sxs-lookup"><span data-stu-id="03efd-109">Click **Values and States** in the left pane.</span></span>  
  
3.  <span data-ttu-id="03efd-110">Klicken Sie in der Spalte **Farbe** neben dem Symbol, das geändert werden soll, auf den Nach-unten-Pfeil, und wählen Sie dann die gewünschte Farbe, **Keine Farbe**oder **Weitere Farben**.</span><span class="sxs-lookup"><span data-stu-id="03efd-110">Click the down arrow in the **Color** column next to the icon that you want to change and click the color to use, **No Color**, or **More colors**.</span></span>  
  
     <span data-ttu-id="03efd-111">Klicken Sie optional auf die Schaltfläche **Ausdruck** (*fx*), um einen Ausdruck zu bearbeiten, mit dem der Wert der Option **Farbe** festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="03efd-111">Optionally, click the **Expression** (*fx*) button to edit an expression that sets the value of the **Color** option.</span></span>  
  
     <span data-ttu-id="03efd-112">Wenn Sie auf **Weitere Farben**geklickt haben, wird das Dialogfeld **Farbe auswählen** geöffnet, in dem Sie zwischen vielen verschiedenen Farben auswählen können.</span><span class="sxs-lookup"><span data-stu-id="03efd-112">If you clicked **More Colors**, the **Select Color** dialog box opens, where you can choose from a wide array of colors.</span></span> <span data-ttu-id="03efd-113">Weitere Informationen zu den zugehörigen Optionen finden Sie unter [Farbe auswählen (Dialogfeld) (Berichts-Generator und SSRS)](../select-color-dialog-box-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="03efd-113">For more information about its options, see [Select Color Dialog Box &#40;Report Builder and SSRS&#41;](../select-color-dialog-box-report-builder-and-ssrs.md).</span></span> <span data-ttu-id="03efd-114">Klicken Sie auf **OK** , um das Dialogfeld **Farbe auswählen** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="03efd-114">Click **OK** to close the **Select Color** dialog box.</span></span>  
  
4.  <span data-ttu-id="03efd-115">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="03efd-115">Click **OK**.</span></span>  
  
### <a name="to-change-the-icon"></a><span data-ttu-id="03efd-116">So ändern Sie das Symbol</span><span class="sxs-lookup"><span data-stu-id="03efd-116">To change the icon</span></span>  
  
1.  <span data-ttu-id="03efd-117">Klicken Sie mit der rechten Maustaste auf den Indikator, der geändert werden soll, und klicken Sie auf **Indikatoreigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="03efd-117">Right-click the indicator you want to change and click **Indicator Properties**.</span></span>  
  
2.  <span data-ttu-id="03efd-118">Klicken Sie im linken Bereich auf **Wert und Status** .</span><span class="sxs-lookup"><span data-stu-id="03efd-118">Click **Values and States** in the left pane.</span></span>  
  
3.  <span data-ttu-id="03efd-119">Klicken Sie auf den Nach-unten-Pfeil neben dem Symbol, das Sie ändern möchten, und wählen Sie ein anderes Symbol aus.</span><span class="sxs-lookup"><span data-stu-id="03efd-119">Click the down arrow next to the icon that you want to change and select a different icon.</span></span>  
  
     <span data-ttu-id="03efd-120">Klicken Sie optional auf die Schaltfläche **Ausdruck** (*fx*), um einen Ausdruck zu bearbeiten, der den Wert der Option **Symbol** festlegt.</span><span class="sxs-lookup"><span data-stu-id="03efd-120">Optionally, click the **Expression** (*fx*) button to edit an expression that sets the value of the **Icon** option.</span></span>  
  
4.  <span data-ttu-id="03efd-121">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="03efd-121">Click **OK**.</span></span>  
  
### <a name="to-use-a-custom-image-as-an-indicator-icon"></a><span data-ttu-id="03efd-122">So verwenden Sie ein benutzerdefiniertes Bild als Indikatorsymbol</span><span class="sxs-lookup"><span data-stu-id="03efd-122">To use a custom image as an indicator icon</span></span>  
  
1.  <span data-ttu-id="03efd-123">Klicken Sie mit der rechten Maustaste auf den Indikator, der geändert werden soll, und klicken Sie auf **Indikatoreigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="03efd-123">Right-click the indicator you want to change and click **Indicator Properties**.</span></span>  
  
2.  <span data-ttu-id="03efd-124">Klicken Sie im linken Bereich auf **Wert und Status** .</span><span class="sxs-lookup"><span data-stu-id="03efd-124">Click **Values and States** in the left pane.</span></span>  
  
3.  <span data-ttu-id="03efd-125">Klicken Sie auf den Nach-unten-Pfeil neben dem Symbol, das Sie ändern möchten, und wählen Sie **Bild**aus.</span><span class="sxs-lookup"><span data-stu-id="03efd-125">Click the down arrow next to the icon that you wan to change and select **Image**.</span></span>  
  
4.  <span data-ttu-id="03efd-126">Klicken Sie in der Liste **Bildquelle auswählen** auf **Extern**, **Eingebettet**oder **Datenbank**.</span><span class="sxs-lookup"><span data-stu-id="03efd-126">In the **Select the image source** list, click **External**, **Embedded**, or **Database**.</span></span>  
  
5.  <span data-ttu-id="03efd-127">Führen Sie abhängig von der Bildquelle eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="03efd-127">Depending on the source of the image, do the one of the following:</span></span>  
  
    -   <span data-ttu-id="03efd-128">Wenn Sie ein Bild verwenden, das außerhalb des Berichts gespeichert ist, klicken Sie auf **Durchsuchen** , und navigieren Sie zu dem Bild.</span><span class="sxs-lookup"><span data-stu-id="03efd-128">To use an image that is stored externally to the report, click **Browse** and locate the image.</span></span> <span data-ttu-id="03efd-129">Der Bericht enthält einen Verweis auf das Bild.</span><span class="sxs-lookup"><span data-stu-id="03efd-129">The report will include a reference to the image.</span></span>  
  
    -   <span data-ttu-id="03efd-130">Wenn Sie ein Bild verwenden möchten, das in den Bericht eingebettet ist, klicken Sie auf **Importieren** , und navigieren Sie zu dem Bild.</span><span class="sxs-lookup"><span data-stu-id="03efd-130">To use an image that is embedded in the report, click **Import** and locate the image.</span></span> <span data-ttu-id="03efd-131">Das Bild wird der Berichtsdefinition hinzugefügt und zusammen damit gespeichert.</span><span class="sxs-lookup"><span data-stu-id="03efd-131">The image will be added to the report definition and saved with it.</span></span>  
  
    -   <span data-ttu-id="03efd-132">Wenn Sie ein Bild verwenden möchten, das sich in einer Datenbank in der Liste **Dieses Feld verwenden** befindet,</span><span class="sxs-lookup"><span data-stu-id="03efd-132">To use an image that is in a database, in the **Use this field** list.</span></span> <span data-ttu-id="03efd-133">wählen Sie das Feld aus der Liste aus. Wählen Sie danach in der Liste **Diesen MIME-Typ verwenden** den MIME-Typ des Bilds aus.</span><span class="sxs-lookup"><span data-stu-id="03efd-133">select the field from the list and then in the **Use this MIME type** list, select the MIME type of the image.</span></span>  
  
6.  <span data-ttu-id="03efd-134">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="03efd-134">Click **OK**.</span></span>  
  
### <a name="to-add-an-icon-to-the-indicator-set"></a><span data-ttu-id="03efd-135">So fügen Sie dem Indikatorsatz ein Symbol hinzu</span><span class="sxs-lookup"><span data-stu-id="03efd-135">To add an icon to the indicator set</span></span>  
  
1.  <span data-ttu-id="03efd-136">Klicken Sie mit der rechten Maustaste auf den Indikator, der geändert werden soll, und klicken Sie auf **Indikatoreigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="03efd-136">Right-click the indicator you want to change and click **Indicator Properties**.</span></span>  
  
2.  <span data-ttu-id="03efd-137">Klicken Sie im linken Bereich auf **Wert und Status** .</span><span class="sxs-lookup"><span data-stu-id="03efd-137">Click **Values and States** in the left pane.</span></span>  
  
3.  <span data-ttu-id="03efd-138">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="03efd-138">Click **Add**.</span></span> <span data-ttu-id="03efd-139">Ein Indikator wird mithilfe des Standardsymbols und der Option **Keine Farbe** hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="03efd-139">An indicator is added, using the default icon and the **No Color** option.</span></span>  
  
     <span data-ttu-id="03efd-140">Konfigurieren Sie den indictor, um das gewünschte Symbol und die gewünschte Farbe zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="03efd-140">Configure the indictor to use the icon and color you want.</span></span> <span data-ttu-id="03efd-141">In den Vorgehensweisen weiter oben in diesem Thema werden die entsprechenden Schritte erläutert.</span><span class="sxs-lookup"><span data-stu-id="03efd-141">Procedures earlier in this topic describe the steps to do this.</span></span>  
  
4.  <span data-ttu-id="03efd-142">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="03efd-142">Click **OK**.</span></span>  
  
### <a name="to-delete-an-icon-to-the-indicator-set"></a><span data-ttu-id="03efd-143">So löschen Sie ein Symbol im Indikatorsatz</span><span class="sxs-lookup"><span data-stu-id="03efd-143">To delete an icon to the indicator set</span></span>  
  
1.  <span data-ttu-id="03efd-144">Klicken Sie mit der rechten Maustaste auf den Indikator, der geändert werden soll, und klicken Sie auf **Indikatoreigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="03efd-144">Right-click the indicator you want to change and click **Indicator Properties**.</span></span>  
  
2.  <span data-ttu-id="03efd-145">Klicken Sie im linken Bereich auf **Wert und Status** .</span><span class="sxs-lookup"><span data-stu-id="03efd-145">Click **Values and States** in the left pane.</span></span>  
  
3.  <span data-ttu-id="03efd-146">Wählen Sie den Indikator aus, der gelöscht werden soll, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="03efd-146">Select the icon to delete, and click **Delete**.</span></span>  
  
4.  <span data-ttu-id="03efd-147">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="03efd-147">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03efd-148">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="03efd-148">See Also</span></span>  
 [<span data-ttu-id="03efd-149">Indikatoren &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="03efd-149">Indicators &#40;Report Builder and SSRS&#41;</span></span>](indicators-report-builder-and-ssrs.md)  
  
  
