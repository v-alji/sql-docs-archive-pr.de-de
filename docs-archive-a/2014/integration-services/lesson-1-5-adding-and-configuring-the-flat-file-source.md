---
title: 'Schritt 5: Hinzufügen und Konfigurieren der Flatfilequelle | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5c95ce51-e0fe-4fc5-95eb-2945929f2b13
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 504cfb4bc722627eb8ee70ec1f2c562cef8f1f0f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618128"
---
# <a name="step-5-adding-and-configuring-the-flat-file-source"></a>Schritt 5: Hinzufügen und Konfigurieren der Flatfilequelle
  In dieser Aufgabe fügen Sie Ihrem Paket eine Flatfilequelle hinzu und konfigurieren sie. Eine Flatfilequelle ist eine Datenflusskomponente, die Metadaten verwendet, die durch einen Flatfile-Verbindungs-Manager definiert werden, um das Format und die Struktur der Daten anzugeben, die aus der Flatfile durch einen Transformationsprozess extrahiert werden. Die Flatfilequelle kann zum Extrahieren von Daten aus einer einzigen Flatfile konfiguriert werden, indem die Dateiformatdefinition verwendet wird, die durch den Flatfile-Verbindungs-Manager zur Verfügung gestellt wird.  
  
 In diesem Tutorial konfigurieren Sie die Flatfilequelle `Sample Flat File Source Data` so, dass Sie den zuvor erstellten Verbindungs-Manager verwendet.  
  
### <a name="to-add-a-flat-file-source-component"></a>So fügen Sie eine Flatfilequellen-Komponente hinzu  
  
1.  Öffnen Sie den **Datenfluss** -Designer, indem Sie entweder auf den `Extract Sample Currency Data` Datenfluss Task doppelklicken oder auf die **Registerkarte Datenfluss**klicken.  
  
2.  Erweitern Sie in der **SSIS-Toolbox**die Option **Weitere Quellen**, und ziehen Sie anschließend **Flatfilequelle** auf die Entwurfsoberfläche der Registerkarte **Datenfluss** .  
  
3.  Klicken Sie auf der Entwurfs Oberfläche **Datenfluss** mit der rechten Maustaste auf die neu hinzugefügte **Flatfilequelle**, klicken Sie auf **Umbenennen**, und ändern Sie den Namen in `Extract Sample Currency Data` .  
  
4.  Doppelklicken Sie auf die Flatfilequelle, um das Dialogfeld Quellen-Editor für Flatfiles zu öffnen.  
  
5.  Wählen Sie im Feld **Verbindungs-Manager für Flatfiles** die Option aus `Sample Flat File Source Data` .  
  
6.  Klicken Sie auf **Spalten** , und überprüfen Sie, ob die Namen der Spalten ordnungsgemäß sind.  
  
7.  Klicken Sie auf **OK**.  
  
8.  Klicken Sie mit der rechten Maustaste auf die Flatfilequelle, und klicken Sie auf **Eigenschaften**.  
  
9. Überprüfen Sie im Eigenschaftenfenster, ob die- `LocaleID` Eigenschaft auf **Englisch (USA)** festgelegt ist.  
  
## <a name="next-task-in-lesson"></a>Nächste Aufgabe in der Lektion  
 [Schritt 6: Hinzufügen und Konfigurieren der Transformationen zum Suchen](lesson-1-6-adding-and-configuring-the-lookup-transformations.md)  
  
## <a name="see-also"></a>Weitere Informationen  
 [Flatfilequelle](data-flow/flat-file-source.md)   
 [Verbindungs-Manager-Editor für Flatfiles &#40;Seite „Allgemein“&#41;](general-page-of-integration-services-designers-options.md)  
  
  
