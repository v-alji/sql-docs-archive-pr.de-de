---
title: Sortieren von Daten in einer Tabelle (SSAS-tabellarisch) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 5fa6ad56-bf68-4aac-a226-52556173b7e2
author: minewiskan
ms.author: owend
ms.openlocfilehash: d9a6636c2c11fc571e8d4c1bcbc25c1e02d815fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694718"
---
# <a name="sort-data-in-a-table-ssas-tabular"></a>Sortieren von Daten in einer Tabelle (SSAS – tabellarisch)
  Sie können Daten in einer oder mehreren Spalten nach Text (A bis Z oder Z bis A) und Zahlen (kleinsten zu größten oder größten zu kleinsten) sortieren.  
  
### <a name="to-sort-the-data-in-a-table-based-on-a-text-column"></a>So sortieren Sie die Daten in einer Tabelle anhand einer Textspalte  
  
1.  Wählen Sie im Modell-Designer eine Spalte mit alphanumerischen Daten oder einen Zellbereich in einer Spalte aus, oder stellen Sie sicher, dass sich die aktive Zelle in einer Tabellenspalte befindet, die alphanumerische Daten enthält. Klicken Sie dann auf den Pfeil in der Kopfzeile der Spalte, nach der Sie filtern möchten.  
  
2.  Führen Sie im Menü AutoFilter einen der folgenden Schritte aus:  
  
    -   Um in aufsteigender alphanumerischer Reihenfolge zu sortieren, klicken Sie auf **Von A bis Z sortieren**.  
  
    -   Um in absteigender alphanumerischer Reihenfolge zu sortieren, klicken Sie auf **Von Z bis A sortieren**.  
  
    > [!NOTE]  
    >  In einigen Fällen können vor Daten, die aus anderen Anwendungen importiert werden, Leerzeichen eingefügt sein. Sie müssen diese Leerzeichen entfernen, um die Daten ordnungsgemäß sortieren zu können.  
  
### <a name="to-sort-the-data-in-a-table-based-on-a-numeric-column"></a>So sortieren Sie die Daten in einer Tabelle anhand einer numerischen Spalte  
  
1.  Wählen Sie im Modell-Designer eine Spalte mit alphanumerischen Daten oder einen Zellbereich in einer Spalte aus, oder stellen Sie sicher, dass sich die aktive Zelle in einer Tabellenspalte befindet, die alphanumerische Daten enthält. Klicken Sie dann auf den Pfeil in der Kopfzeile der Spalte, nach der Sie filtern möchten.  
  
2.  Führen Sie im Menü AutoFilter einen der folgenden Schritte aus:  
  
    -   Um von niedrigen Zahlen zu hohen Zahlen zu sortieren, klicken Sie auf **Nach Größe sortieren (aufsteigend)**.  
  
    -   Um von hohen Zahlen zu niedrigen Zahlen zu sortieren, klicken Sie auf **Nach Größe sortieren (absteigend).**  
  
    > [!NOTE]  
    >  Wenn die Ergebnisse nicht die erwarteten sind, enthält die Spalte möglicherweise als Text und nicht als Zahlen gespeicherte Zahlen. Zum Beispiel werden aus einigen Abrechnungssystemen importierte negative Zahlen oder Zahlen, denen ein ' (Apostroph) vorangeht, als Text gespeichert.  
  
## <a name="see-also"></a>Weitere Informationen  
 [Filtern und Sortieren von Daten &#40;tabellarischen SSAS-&#41;](../filter-and-sort-data-ssas-tabular.md)   
 [Perspektiven &#40;tabellarischen SSAS-&#41;](perspectives-ssas-tabular.md)   
 [Rollen &#40;SSAS – tabellarisch&#41;](roles-ssas-tabular.md)  
  
  
