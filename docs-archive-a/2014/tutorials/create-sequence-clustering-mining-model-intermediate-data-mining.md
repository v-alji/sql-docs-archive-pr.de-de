---
title: Erstellen einer Sequence Clustering-Mining Modellstruktur (Data Mining-Lernprogramm für Fortgeschrittene) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: e9339227-6c2e-4c4b-8be2-8c1960bc4a8d
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 37d0a1738a758a9d8c4fd6b80310037937a9803f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616292"
---
# <a name="creating-a-sequence-clustering-mining-model-structure-intermediate-data-mining-tutorial"></a>Erstellen einer Sequence Clustering-Miningmodellstruktur (Mittleres Data Mining Tutorial)
  Der erste Schritt zum Erstellen eines Sequenzcluster-Miningmodells besteht im Erstellen einer neuen Miningstruktur sowie eines neuen Miningmodells auf der Basis des [!INCLUDE[msCoName](../includes/msconame-md.md)] Sequence Clustering-Algorithmus mittels des Data Mining-Assistenten.  
  
 Dazu verwenden Sie die gleiche Datenquellensicht wie für die Market Basket-Analyse, fügen jedoch eine Spalte mit dem `sequence`-Bezeichner hinzu. In diesem Szenario bezeichnet "Sequenz" die Reihenfolge, in der die Elemente vom Kunden im Warenkorb abgelegt werden.  
  
 Darüber hinaus fügen Sie einige Spalten hinzu, die in einem der Modelle zum Gruppieren von Kunden anhand demografischer Daten verwendet werden.  
  
### <a name="to-create-a-sequence-clustering-structure-and-model"></a>So erstellen Sie eine Sequenzclusterstruktur und ein Sequenzclustermodell  
  
1.  Klicken Sie in Projektmappen-Explorer in mit der [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] rechten Maustaste auf **Mining Strukturen** , und wählen Sie **neue Mining Struktur**aus.  
  
2.  Klicken Sie auf der Seite **Willkommen** auf **Weiter**.  
  
3.  Überprüfen Sie auf der Seite **Definitions Methode auswählen** , ob **aus vorhandener relationaler Datenbank oder Data Warehouse** ausgewählt ist, und klicken Sie dann auf **weiter**.  
  
4.  Vergewissern Sie sich auf der Seite **Data Mining-Struktur erstellen** , dass die Option **Mining Struktur mit einem Mining Modell erstellen** ausgewählt ist. Klicken Sie anschließend auf die Dropdown Liste für die Option, **welche Data Mining Technik Sie verwenden möchten?**, und wählen Sie **Microsoft Sequence Clustering**aus. Klicken Sie auf **Weiter**.  
  
     Die Seite **Datenquellen Sicht auswählen** wird angezeigt. Wählen Sie unter **Verfügbare Datenquellen Sichten**die Option aus `Orders` .  
  
     Orders ist die gleiche Datenquellensicht, die Sie auch für das Market Basket-Szenario verwendet haben. Wenn Sie diese Datenquellen Sicht nicht erstellt haben, finden Sie weitere Informationen unter [Hinzufügen einer Datenquellen Sicht mit Tabellen &#40;Data Mining ](../../2014/tutorials/adding-a-data-source-view-with-nested-tables-intermediate-data-mining-tutorial.md)-Lernprogramm für fortgeschrittene&#41;.  
  
5.  Klicken Sie auf **Weiter**.  
  
6.  Aktivieren Sie auf der Seite **Tabellentypen angeben** neben der Tabelle **vassoctarqorders** das Kontrollkästchen **Fall** , und aktivieren Sie das Kontrollkästchen **Nested** neben der Tabelle **vassoctarqlineitems** . Klicken Sie auf **Weiter**.  
  
    > [!NOTE]  
    >  Wenn ein Fehler auftritt, wenn Sie die **Kontrollkästchen für** die Groß-/Kleinschreibung oder die Option aktivieren, ist der Join in der Datenquellen Sicht möglicherweise nicht korrekt. **Case** Die geschachtelte Table **vassocot qlineitems**muss mit der Fall Tabelle **vassocc-qorders** durch einen n:1-Join verbunden werden. Sie können die Beziehung bearbeiten, indem Sie mit der rechten Maustaste auf die Joinlinie klicken und dann die Richtung des Joins umkehren. Weitere Informationen finden Sie unter [Dialog Feld "Beziehung erstellen oder bearbeiten" &#40;Analysis Services-mehrdimensionalen Daten&#41;](../../2014/analysis-services/create-or-edit-relationship-dialog-box-analysis-services-multidimensional-data.md).  
  
7.  Wählen Sie auf der Seite **Trainingsdaten angeben** die Spalten aus, die im Modell verwendet werden sollen, indem Sie wie folgt ein Kontrollkästchen aktivieren:  
  
    -   **IncomeGroup** Aktivieren Sie das Kontrollkästchen **Eingabe** .  
  
         Diese Spalte enthält interessante Informationen über die Kunden, die Sie für das Clustering verwenden können. Eine Verwendung findet nur im ersten Modell, nicht jedoch im zweiten Modell statt.  
  
    -   **OrderNumber** Aktivieren Sie das `Key` Kontrollkästchen.  
  
         Dieses Feld wird als Bezeichner oder `Key` für die Falltabelle verwendet. Das Schlüsselfeld der Falltabelle sollte nicht als Eingabe verwendet werden, da der Schlüssel eindeutige Werte enthält, die nicht nützlich für das Clustering sind.  
  
    -   **Region** Aktivieren Sie das Kontrollkästchen **Eingabe** .  
  
         Diese Spalte enthält interessante Informationen über die Kunden, die Sie für das Clustering verwenden können. Eine Verwendung findet nur im ersten Modell, nicht jedoch im zweiten Modell statt.  
  
    -   **LineNumber** Aktivieren Sie `Key` die **Input** Kontrollkästchen und.  
  
         Das Feld " **LineNumber** " wird als Bezeichner für die geänderte Tabelle oder verwendet `Sequence Key` . Der Schlüssel für eine geschachtelte Tabelle muss immer für die Eingabe verwendet werden.  
  
    -   **Modell** Aktivieren Sie die Kontrollkästchen **Eingabe** und **vorhersagbar** .  
  
     Überprüfen Sie, ob die Auswahl richtig ist, und klicken Sie dann auf **weiter**.  
  
8.  Überprüfen Sie auf der Seite **Inhalt und Datentyp der Spalten angeben** , ob das Raster die Spalten, Inhaltstypen und Datentypen enthält, die in der folgenden Tabelle angezeigt werden, und klicken Sie dann auf **weiter**.  
  
    |Tabellen/Spalten|Inhaltstyp|Datentyp|  
    |---------------------|------------------|---------------|  
    |IncomeGroup|Discrete|Text|  
    |OrderNumber|Schlüssel|Text|  
    |Region|Discrete|Text|  
    |vAssocSeqLineItems|||  
    |Zeilennummer|Key Sequence|Long|  
    |Modell|Discrete|Text|  
  
9. Ändern Sie auf der Seite **Testsatz erstellen** den **Prozentsatz der zu testenden Daten** auf 20, und klicken Sie dann auf **weiter**.  
  
10. Geben Sie auf der Seite **Assistenten abschließen** für **Mining Struktur Name den Namen**ein `Sequence Clustering with Region` .  
  
11. Geben Sie für **Mining Modellname den Namen**ein `Sequence Clustering with Region` .  
  
12. Aktivieren Sie das Kontrollkästchen **Drillthrough zulassen** , und klicken Sie dann auf **Fertig**stellen.  
  
## <a name="next-task-in-lesson"></a>Nächste Aufgabe in der Lektion  
 [Verarbeiten des Sequenzclustermodells](../../2014/tutorials/processing-the-sequence-clustering-model.md)  
  
## <a name="see-also"></a>Weitere Informationen  
 [Data Mining-Designer](../../2014/analysis-services/data-mining/data-mining-designer.md)   
 [Microsoft Sequence Clustering-Algorithmus](../../2014/analysis-services/data-mining/microsoft-sequence-clustering-algorithm.md)  
  
  
