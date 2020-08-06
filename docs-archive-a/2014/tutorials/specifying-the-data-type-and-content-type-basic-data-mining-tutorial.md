---
title: Angeben von Datentyp und Inhaltstyp (Lernprogramm zu Data Mining-Grundlagen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 72484d27-3ef1-4f16-813c-2f43231fc2da
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 73ff61dbe439b9f2fb50f3a8004f4e7bcad8369a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720446"
---
# <a name="specifying-the-data-type-and-content-type-basic-data-mining-tutorial"></a>Angeben des Datentyps und des Inhaltstyps (Lernprogramm zu Data Mining-Grundlagen)
  Nachdem Sie die Spalten zum Erstellen der Struktur und zum Trainieren der Modelle ausgewählt haben, können Sie erforderliche Änderungen an den Standarddaten und Inhaltstypen vornehmen, die vom Assistenten festgelegt wurden.  
  
#### <a name="review-and-modify-content-type-and-data-type-for-each-column"></a>Überprüfen und Ändern von Inhaltstyp und Datentyp für jede Spalte  
  
1.  Klicken Sie auf der Seite **Inhalt und Datentyp der Spalten angeben** auf **Erkennen** , um einen Algorithmus zur Bestimmung der Standarddaten und Inhaltstypen für die einzelnen Spalten auszuführen.  
  
2.  Überprüfen die Einträge in den Spalten **Inhaltstyp** und **Datentyp** . Ändern Sie die Einträge bei Bedarf, um sicherzustellen, dass die Einstellungen den in der folgenden Tabelle aufgeführten Einstellungen entsprechen.  
  
     Der Assistent erkennt normalerweise Zahlen und weist einen entsprechenden numerischen Datentyp zu. In vielen Szenarien bietet es sich jedoch an, eine Zahl stattdessen als Text zu behandeln. Beispielsweise sollte **GeographyKey** als Text behandelt werden, da mathematische Operationen sich für diese ID nicht eignen.  
  
    |Spalte|Inhaltstyp|Datentyp|  
    |------------|------------------|---------------|  
    |**Address Line1**|**Discrete**|**Text**|  
    |**Address Line2**|**Discrete**|**Text**|  
    |**Age**|**Fortlaufend**|**Long**|  
    |**Bike Buyer**|**Discrete**|**Long**|  
    |**Commute Distance**|**Discrete**|**Text**|  
    |**CustomerKey**|**Schlüssel**|**Long**|  
    |**DateLastPurchase**|**Fortlaufend**|**Datum**|  
    |**E-Mail-Adresse**|**Discrete**|**Text**|  
    |**EnglishEducation**|**Discrete**|**Text**|  
    |**English Occupation**|**Discrete**|**Text**|  
    |**Vorname**|**Discrete**|**Text**|  
    |**Geschlecht**|**Discrete**|**Text**|  
    |**Geography Key**|**Discrete**|**Text**|  
    |**House Owner Flag**|**Discrete**|**Text**|  
    |**Last Name**|**Discrete**|**Text**|  
    |**Marital Status**|**Discrete**|**Text**|  
    |**Number Cars Owned**|**Discrete**|**Long**|  
    |**Anzahl der Kinder zu Hause**|**Discrete**|**Long**|  
    |**Region**|**Discrete**|**Text**|  
    |**Total Children**|**Discrete**|**Long**|  
    |**Yearly Income**|**Fortlaufend**|**Double**|  
  
3.  Klicken Sie auf **Weiter**.  
  
## <a name="next-task-in-lesson"></a>Nächste Aufgabe in der Lektion  
 [Angeben eines Test Datasets für die Struktur &#40;Lernprogramm zu Data Mining-Grundlagen&#41;](../../2014/tutorials/specifying-a-testing-data-set-for-the-structure-basic-data-mining-tutorial.md)  
  
## <a name="previous-task-in-lesson"></a>Vorherige Aufgabe in der Lektion  
 [Erstellen einer zielgerichteten Mailing-Mining Modellstruktur &#40;grundlegenden Data Mining-Lernprogramm&#41;](../../2014/tutorials/creating-a-targeted-mailing-mining-model-structure-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a>Weitere Informationen  
 [Inhaltstypen &#40;Data Mining-&#41;](../../2014/analysis-services/data-mining/content-types-data-mining.md)   
 [Datentypen &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/data-types-data-mining.md)  
  
  
