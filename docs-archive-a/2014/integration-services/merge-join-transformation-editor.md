---
title: Transformations-Editor für Zusammenführungsjoin Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.mergejointransformation.f1
helpviewer_keywords:
- Merge Join Transformation Editor
ms.assetid: ac06f419-30b3-42aa-8b34-42000bec4285
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e0d15d1233c2e0ff836e9dbd17459e56c48183f6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619204"
---
# <a name="merge-join-transformation-editor"></a>Transformations-Editor für Zusammenführungsjoin
  Im Dialogfeld **Transformations-Editor für Zusammenführungsjoin** geben Sie den Jointyp, die Joinspalten und die Ausgabespalten für zwei Eingaben an, die durch einen Join zusammengeführt werden.  
  
> [!IMPORTANT]  
>  Die Transformation für Zusammenführungsjoin erfordert als Eingabe sortierte Daten. Weitere Informationen zu dieser wichtigen Anforderung finden Sie unter [Sortieren von Daten für die Transformationen für Zusammenführen und Zusammenführungsjoin](data-flow/transformations/sort-data-for-the-merge-and-merge-join-transformations.md).  
  
 Weitere Informationen zur Transformation für Zusammenführungsjoins finden Sie unter [Merge Join Transformation](data-flow/transformations/merge-join-transformation.md).  
  
## <a name="options"></a>Tastatur  
 **Join-Typ**  
 Geben Sie an, ob Sie einen inneren Join, einen linken äußeren Join oder einen vollständigen Join verwenden möchten.  
  
 **Eingaben vertauschen**  
 Schalten Sie die Reihenfolge der Eingaben mithilfe der Schaltfläche **Eingaben vertauschen** um. Diese Option kann sich bei linkem äußeren Join als nützlich erweisen.  
  
 **Eingabe**  
 Wählen Sie alle Spalten, die zur zusammengeführten Ausgabe gehören sollen, in der Liste der verfügbaren Eingaben aus.  
  
 Eingaben werden in zwei separaten Tabellen angezeigt. Wählen Sie die Spalten aus, die in die Eingabe eingeschlossen werden sollen. Verschieben Sie die Spalten, um einen Join zwischen den Tabellen zu erstellen. Um einen Join zu löschen, wählen Sie diesen aus und drücken dann ENTF.  
  
 **Eingabespalte**  
 Wählen Sie eine Spalte, die in die zusammengeführte Ausgabe eingeschlossen werden soll, in der Liste der für die ausgewählte Eingabe verfügbaren Spalten aus.  
  
 **Ausgabealias**  
 Geben Sie einen Alias für jede Spalte ein. Standardmäßig wird der Name der Eingabespalte verwendet. Sie können jedoch auch einen beschreibenden Namen angeben, sofern dieser eindeutig ist.  
  
## <a name="see-also"></a>Weitere Informationen  
 [Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md)   
 [Sortieren von Daten für die Transformationen für Zusammenführen und Zusammenführungsjoin](data-flow/transformations/sort-data-for-the-merge-and-merge-join-transformations.md)   
 [Erweitern eines Datasets mithilfe der Transformation für Zusammenführungsjoin](data-flow/transformations/extend-a-dataset-by-using-the-merge-join-transformation.md)   
 [Transformation für Zusammenführen](data-flow/transformations/merge-transformation.md)   
 [Transformation für UNION ALL](data-flow/transformations/union-all-transformation.md)  
  
  
