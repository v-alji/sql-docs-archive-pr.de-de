---
title: Anzeigen von Prozentwerten in einem Kreisdiagramm (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: eb905fc1-5235-4773-a27e-b07be9318be5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2dee9017d34f2751b790b2e4928571160b597f1d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617734"
---
# <a name="display-percentage-values-on-a-pie-chart-report-builder-and-ssrs"></a>Anzeigen von Prozentwerten in einem Kreisdiagramm (Berichts-Generator und SSRS)
  Standardmäßig werden Kategorien in der Legende angezeigt, um jeden Wert zu identifizieren. Wenn Sie das Kreisdiagramm mit Kategoriebezeichnungen versehen haben, möchten Sie möglicherweise Prozentsätze in der Legende anzeigen.  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-display-percentage-values-as-labels-on-a-pie-chart"></a>So zeigen Sie Prozentwerte als Bezeichnungen in einem Kreisdiagramm an  
  
1.  Fügen Sie dem Bericht ein Kreisdiagramm hinzu. Weitere Informationen finden Sie unter [Hinzufügen eines Diagramms zu einem Bericht &#40;Berichts-Generator und SSRS&#41;](add-a-chart-to-a-report-report-builder-and-ssrs.md).  
  
2.  Klicken Sie auf der Entwurfsoberfläche mit der rechten Maustaste auf das Kreisdiagramm, und wählen Sie **Datenbezeichnungen anzeigen**aus. Die Datenbezeichnungen sollten innerhalb jedes Segments des Kreisdiagramms angezeigt werden.  
  
3.  Klicken Sie auf der Entwurfsoberfläche mit der rechten Maustaste auf die Bezeichnungen, und wählen Sie **Reihenbezeichnungseigenschaften**aus. Das Dialogfeld **Reihenbezeichnungseigenschaften** wird angezeigt.  
  
4.  Geben Sie `#PERCENT` für die Option Bezeichnungs **Daten** ein.  
  
5.  (Optional) Wenn Sie die Anzahl von Dezimalstellen in der Bezeichnung angeben möchten, geben Sie „#PERECENT{P*n*}“ an, wobei *n* die Anzahl der anzuzeigenden Dezimalstellen darstellt. Geben Sie z. B. "#PERCENT{P0}" ein, um keine Dezimalstellen anzuzeigen.  
  
### <a name="to-display-percentage-values-in-the-legend-of-a-pie-chart"></a>So zeigen Sie Prozentwerte in der Legende eines Kreisdiagramms an  
  
1.  Klicken Sie auf der Entwurfsoberfläche mit der rechten Maustaste auf das Kreisdiagramm, und wählen Sie **Reiheneigenschaften**aus. Das Dialogfeld **Reiheneigenschaften** wird angezeigt.  
  
2.  Geben **Legend**Sie in Legende `#PERCENT` für die Eigenschaft **benutzerdefinierter Legenden Text** ein.  
  
## <a name="see-also"></a>Weitere Informationen  
 [Kreis Diagramme &#40;Berichts-Generator und SSRS&#41;](charts-report-builder-and-ssrs.md)   
 [Formatieren der Legende in einem Diagramm &#40;Berichts-Generator und SSRS&#41;](chart-legend-formatting-report-builder.md)   
 [Anzeigen von Datenpunkt Bezeichnungen außerhalb eines Kreis Diagramms &#40;Berichts-Generator und SSRS&#41;](display-data-point-labels-outside-a-pie-chart-report-builder-and-ssrs.md)   
 [Zusammenfassen von kleinen Slices in einem Kreisdiagramm &#40;Berichts-Generator und SSRS&#41;](collect-small-slices-on-a-pie-chart-report-builder-and-ssrs.md)  
  
  
