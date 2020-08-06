---
title: Ändern der Reihenfolge von Berichtsparametern (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: abd61e19-dba3-423c-a26c-e8bc43197d3f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ad9dd25be7a87fee089a48849fcc716e682e4c64
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722518"
---
# <a name="change-the-order-of-a-report-parameter-report-builder-and-ssrs"></a>Ändern der Reihenfolge von Berichtsparametern (Berichts-Generator und SSRS)
  Ändern Sie die Reihenfolge der Berichtsparameter, wenn ein abhängiger Parameter vor dem Parameter angeordnet ist, von dem er abhängt. Die Reihenfolge der Parameter spielt eine wichtige Rolle, wenn Sie mit kaskadierenden Parametern arbeiten, oder wenn Sie möchten, dass der Standardwert für einen Parameter angezeigt wird, bevor die Benutzer Werte für andere Parameter auswählen. Ein abhängiger Berichtsparameter enthält entweder in der Abfrage der Standardwerte oder in der Abfrage der gültigen Werte einen Verweis auf einen Abfrageparameter, der auf einen Berichtsparameter verweist, der in der Parameterliste im Berichtsdatenbereich nach ihm angeordnet ist.  
  
 Die Reihenfolge der Parameter auf der Symbolleiste des Berichts-Viewers hängt von der Reihenfolge der Parameter im Berichtsdatenbereich ab.  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-change-the-order-of-report-parameters"></a>So ändern Sie die Reihenfolge von Berichtsparametern  
  
1.  Erweitern Sie im Berichtsdatenbereich den Knoten Parameter.  
  
2.  Klicken Sie auf einen Parameter, und verschieben Sie ihn mit den Pfeilschaltflächen im Berichtsdatenbereich in der Liste nach oben oder nach unten. In der folgenden Grafik wird der Berichtsdatenbereich im Berichts-Generator dargestellt.  
  
     ![Berichtsdaten Bereich](../media/reportdatapane.png "Berichtsdatenbereich")  
  
## <a name="see-also"></a>Weitere Informationen  
 [Berichts Parameter &#40;Berichts-Generator und Berichts-Designer&#41;](report-parameters-report-builder-and-report-designer.md)   
 [Berichts-Generator Hilfe zu Dialog Feldern, Bereichen und Assistenten](../report-builder-help-for-dialog-boxes-panes-and-wizards.md)   
 [Hinzufügen von kaskadierenden Parametern zu einem Bericht &#40;Berichts-Generator und SSRS&#41;](add-cascading-parameters-to-a-report-report-builder-and-ssrs.md)   
 [Tutorial: Hinzufügen eines Parameters zu einem Bericht &#40;Berichts-Generator&#41;](../tutorial-add-a-parameter-to-your-report-report-builder.md)   
 [Hinzufügen von datasetfiltern, Datenbereichs Filtern und Gruppen Filtern &#40;Berichts-Generator und SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md)   
 [Verweise auf Parameters-Sammlungen &#40;Berichts-Generator und SSRS&#41;](built-in-collections-parameters-collection-references-report-builder.md)  
  
  
