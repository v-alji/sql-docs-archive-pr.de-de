---
title: Erstellen einer Planungsstruktur und eines Modells (Data Mining-Lernprogramm für Fortgeschrittene) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 5f55cbf6-0db4-4cb4-a0f5-e27441873d4f
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: d77b15a9a8efe9a9c6faec49a2274ee182706992
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694889"
---
# <a name="creating-a-forecasting-structure-and-model-intermediate-data-mining-tutorial"></a>Erstellen einer Struktur und eines Modells zur Planungserstellung (Data Mining-Lernprogramm für Fortgeschrittene)
  Als Nächstes erstellen Sie mit dem Data Mining-Assistenten eine neue Miningstruktur und eine neues Miningmodell, basierend auf der zuvor erstellten Datenquellensicht. In dieser Aufgabe legen Sie fest, dass das Miningmodell den [!INCLUDE[msCoName](../includes/msconame-md.md)]-Algorithmus Zeitreihe verwenden soll.  
  
### <a name="to-create-a-forecasting-mining-structure"></a>So legen Sie eine Forecasting-Miningstruktur an  
  
1.  Klicken Sie in Projektmappen-Explorer in mit der [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] rechten Maustaste auf **Mining Strukturen** , und wählen Sie **neue Mining Struktur**aus.  
  
2.  Klicken Sie auf der Seite **Willkommen** auf **Weiter**.  
  
3.  Überprüfen Sie auf der Seite **Definitions Methode auswählen** , ob **aus vorhandener relationaler Datenbank oder Data Warehouse** ausgewählt ist, und klicken Sie dann auf **weiter**.  
  
4.  Wählen Sie auf der Seite **Data Mining-Struktur erstellen** unter **welche Data Mining Technik möchten Sie verwenden?** die Option **Microsoft Time Series**aus, und klicken Sie dann auf **weiter**.  
  
5.  Wählen Sie auf der Seite **Datenquellen Sicht auswählen** unter **Verfügbare Datenquellen Sichten**die Option **SalesByRegion**aus.  
  
6.  Klicken Sie auf **Weiter**.  
  
7.  Vergewissern Sie sich auf der Seite **Tabellentypen angeben** , dass das Kontrollkästchen in der Spalte **Fall** für die Tabelle vTimeSeries ausgewählt ist, und klicken Sie dann auf **weiter**.  
  
8.  Aktivieren Sie auf der Seite **Trainingsdaten angeben** die Kontrollkästchen in der Spalte **Schlüssel** für die Spalten ModelRegion und ReportingDate.  
  
     ReportingDate muss standardmäßig ausgewählt werden, da Sie diese Spalte beim Erstellen der Datenquellen Sicht als logischen Primärschlüssel angegeben haben. Wenn Sie ModelRegion als zweiten Schlüssel hinzufügen, weisen Sie den Algorithmus an, eine separate Zeitreihe für jede Kombination aus Modell und Region zu erstellen, die in diesem Feld aufgeführt ist.  
  
9. Aktivieren Sie die Kontrollkästchen in den **Eingabe** -und **vorhersagbaren** Spalten für die Menge und die Spalte, und klicken Sie dann auf **weiter**.  
  
     Wenn Sie **vorhersagbar**auswählen, geben Sie an, dass Sie Vorhersagen für die Daten in dieser Spalte erstellen möchten. Da Sie jedoch die Prognose anhand von vergangenen Daten erstellen möchten, müssen Sie die Spalte auch als Eingabe hinzufügen.  
  
10. Überprüfen Sie auf der Seite **Inhalt und Datentyp der Spalten angeben**die Auswahl.  
  
     Die Model Region-Spalte wird als **Schlüssel** Spalte festgelegt, und die ReportingDate-Spalte wird automatisch als **Key Time** -Spalte bezeichnet. Es kann von jedem Schlüsseltyp nur jeweils einer vorhanden sein.  
  
11. Klicken Sie auf **Weiter**.  
  
12. Geben Sie auf der Seite **Assistenten abschließen** für **Mining Struktur Name den Namen**ein `Forecasting` .  
  
    > [!NOTE]  
    >  Die Option zum Aktivieren von Drillthroughs ist für Zeitreihenmodelle nicht verfügbar.  
  
13. Geben Sie unter **Mining Modellname den Namen**ein `Forecasting` , und klicken Sie dann auf **Fertig**stellen.  
  
     Der Data Mining-Designer wird geöffnet, um die `Forecasting` soeben erstellte Mining Struktur anzuzeigen.  
  
## <a name="next-task-in-lesson"></a>Nächste Aufgabe in der Lektion  
 [Ändern der Planungsstruktur &#40;Data Mining-Lernprogramm für fortgeschrittene&#41;](../../2014/tutorials/modifying-the-forecasting-structure-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a>Weitere Informationen  
 [Data Mining-Designer](../../2014/analysis-services/data-mining/data-mining-designer.md)   
 [Microsoft Time Series-Algorithmus](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm.md)  
  
  
