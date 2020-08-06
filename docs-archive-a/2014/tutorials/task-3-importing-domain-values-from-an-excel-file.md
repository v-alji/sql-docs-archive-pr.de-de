---
title: 'Aufgabe 3: Importieren von Domänen Werten aus einer Excel-Datei | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 242e8309-1195-495b-9cd5-aa127748c185
ms.author: lle
author: lrtoyou1223
ms.openlocfilehash: 707a3925bb6d0014e2a1248f904123b076024e2c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609592"
---
# <a name="task-3-importing-domain-values-from-an-excel-file"></a>Aufgabe 3: Importieren von Domänenwerten aus einer Excel-Datei

  In dieser Aufgabe importieren Sie Werte für die Domäne **State** aus einem Arbeitsblatt einer Excel-Datei.

1.  Klicken Sie in der **Domänenliste** auf die Domäne **State**.

2.  Stellen Sie sicher, dass die Registerkarte **Domänenwerte** im rechten Bereich aktiv ist.

3.  Klicken Sie im rechten Bereich auf der Symbolleiste auf den **Nach-unten-Pfeil** neben der Schaltfläche **Werte importieren** , und klicken Sie auf **Gültige Werte aus Excel importieren**.

     ![Gültige Werte aus Excel importieren (Menü)](../../2014/tutorials/media/et-importingdomainvaluesfromanexcelfile-01.jpg "Gültige Werte aus Excel importieren (Menü)")

4.  Klicken Sie auf **Durchsuchen**, wählen Sie **Suppliers.xls**aus, und klicken Sie auf **Öffnen**.

5.  Wählen Sie **StatesToImport$** als **Arbeitsblatt**aus.

     ![Domänenwerte importieren (Dialogfeld)](../../2014/tutorials/media/et-importingdomainvaluesfromanexcelfile-02.jpg "Domänenwerte importieren (Dialogfeld)")

6.  Klicken Sie auf **OK** , um das Dialogfeld **Domänenwerte importieren** zu schließen. Die Namen aller importierten Bundesstaaten sollten in der Liste angezeigt werden. Die Option **Nur neue anzeigen** wird nach dem Import automatisch aktiviert. Wenn Sie Werte importieren und die alten Werte nicht in der Liste angezeigt werden, liegt dies daran, dass diese Option nach dem Import automatisch aktiviert wird. Um alle Werte anzuzeigen, deaktivieren Sie das Kontrollkästchen. Wenn Sie den gleichen Satz Werte erneut importieren, wird keiner der Werte importiert, da sie bereits in der Domäne vorhanden sind.

     ![Kontrollkästchen "Nur neue anzeigen" für Domänenwerte](../../2014/tutorials/media/et-importingdomainvaluesfromanexcelfile-03.jpg "Kontrollkästchen "Nur neue anzeigen" für Domänenwerte")

## <a name="next-step"></a>Nächster Schritt
 [Aufgabe 4: Festlegen von Domänenregeln](../../2014/tutorials/task-4-setting-domain-rules.md)


