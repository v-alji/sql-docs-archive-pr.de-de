---
title: Directquery-Entwurfs Modus aktivieren (SSAS-tabellarisch) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 71fc7ebd-2e86-4a76-994b-66d3a57bcc9b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8ccd2dc88f447e78f6558565a89accc341eac37c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618917"
---
# <a name="enable-directquery-design-mode-ssas-tabular"></a>Aktivieren des DirectQuery-Entwurfsmodus (SSAS – tabellarisch)
  Um im DirectQuery-Modus ein Modell zu erstellen, müssen Sie zuerst die Entwurfszeitumgebung ändern, damit sie den Benutzer des DirectQuery-Modus unterstützt. Wenn Sie so vorgehen, führt der Designer ebenfalls die folgenden Schritte aus:  
  
-   Aktivieren der Verwendung der DirectQuery-Bereitstellungseigenschaften.  
  
-   Ändern der Arbeitsbereichsdatenbank für die Ausführung in einem Hybridmodus, der den Cache für Entwürfe verwendet. Wenn Sie das Modell tatsächlich bereitstellen, wird der Modus wieder in den Wert geändert, der in den Projektbereitstellungseigenschaften angegeben wurde.  
  
-   Deaktivieren der Entwurfsfunktionen, die mit dem DirectQuery-Modus nicht kompatibel sind.  
  
-   Validieren des vorhandenen Modells.  
  
 Diese Prozedur beschreibt, wie der DirectQuery-Modus im Designer aktiviert wird.  
  
### <a name="to-enable-use-of-directquery-in-a-model"></a>So aktivieren Sie die Verwendung von DirectQuery in einem Modell  
  
1.  Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] die Lösungsdatei.  
  
2.  Doppelklicken Sie in Objekt-Explorer auf die Datei "Model.bim".  
  
3.  Ändern Sie im **Bereich** **Eigenschaften** die Eigenschaft **directquerymode**in ein.  
  
4.  Wenn Fehler vorhanden sind, öffnen Sie in Visual Studio die **Fehlerliste** , und beheben Sie alle Probleme, die verhindern würden, dass das Modell in den directquery-Modus gewechselt wird.  
  
## <a name="see-also"></a>Weitere Informationen  
 [DirectQuery-Modus &#40;SSAS – tabellarisch&#41;](directquery-mode-ssas-tabular.md)  
  
  
