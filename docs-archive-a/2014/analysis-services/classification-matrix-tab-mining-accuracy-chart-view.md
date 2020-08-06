---
title: Klassifizierungs Matrix (Registerkarte) (Mining Genauigkeits Diagramm Sicht) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.accuracychart.confusionmatrix.f1
ms.assetid: 85d5a047-d656-41e0-8a31-400271c2a620
author: minewiskan
ms.author: owend
ms.openlocfilehash: d202d552b25095d0d0845ff64f9c0e289f7bba0e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610275"
---
# <a name="classification-matrix-tab-mining-accuracy-chart-view"></a>Klassifikationsmatrix (Registerkarte, Mininggenauigkeitsdiagramm-Sicht)
  Die Registerkarte **Klassifikations Matrix** zeigt eine Klassifikations Matrix für jedes im Modell Raster auf der Registerkarte **Spalten Zuordnung** ausgewählte Modell an. Die Klassifikations Matrix ist nur verfügbar, wenn die vorhersagbare Spalte, die auf der Registerkarte **Spalten Zuordnung** ausgewählt wurde, nicht kontinuierlich ist. Eine ausführlichere Beschreibung der Registerkarte **Klassifikationsmatrix** finden Sie unter [Testing and Validation &#40;Data Mining&#41;](data-mining/testing-and-validation-data-mining.md).  
  
## <a name="options"></a>Tastatur  
 **Kopieren**  
 Kopiert den Inhalt jeder Klassifikationsmatrix in die Zwischenablage.  
  
 **Zähler für \<model> on\< predictable column>**  
 Zeigt eine Klassifikationsmatrix für jedes Miningmodell in der Miningstruktur an. Diese Matrix enthält die folgenden Spalten:  
  
|Wert|BESCHREIBUNG|  
|-----------|-----------------|  
|**Vorhergesagt**|Enthält eine Zeile für jeden Status der vorhersagbaren Spalte.|  
|**\<states>reale**|Eine Spalte für jeden Status in der vorhersagbaren Spalte. Wenn sich der Status der Zeile und der Spalte entsprechen, stellt die Zelle die tatsächliche Anzahl der Vorkommen des Status in der Datenbank dar. Wenn sich die Status nicht entsprechen, stellt die Zelle den Fehler der Vorhersage dar.|  
  
## <a name="see-also"></a>Weitere Informationen  
 [Mining Genauigkeits Diagramm-Designer &#40;Data Mining-&#41;](mining-accuracy-chart-designer-data-mining.md)   
 [Test-und validierungsaufgaben und Anleitungen &#40;Data Mining-&#41;](data-mining/testing-and-validation-tasks-and-how-tos-data-mining.md)   
 [Tests und Überprüfung &#40;Data Mining&#41;](data-mining/testing-and-validation-data-mining.md)  
  
  
