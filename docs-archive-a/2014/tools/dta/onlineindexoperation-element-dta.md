---
title: OnlineIndexOperation-Element (DTA) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- OnlineIndexOperation element
ms.assetid: 7c5614cd-09aa-4a59-9591-347aa7d36473
author: stevestein
ms.author: sstein
ms.openlocfilehash: 48943c1b31d7a0a24ae939050d44494476e50034
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620097"
---
# <a name="onlineindexoperation-element-dta"></a>OnlineIndexOperation-Element (DTA)
  Gibt an, ob die vom Datenbankoptimierungsratgeber empfohlenen Indizes, indizierten Sichten oder Partitionen online erstellt werden können.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
<DTAInput>  
...code removed...  
    <TuningOptions>  
      <OnlineIndexOperation>...</OnlineIndexOperation>  
```  
  
## <a name="element-characteristics"></a>Elementmerkmale  
  
|Merkmal|BESCHREIBUNG|  
|--------------------|-----------------|  
|**Datentyp und -länge**|`string`, keine maximale Länge.|  
|**Zulässige Werte**|**OFF**<br /> Es können keine empfohlenen physischen Entwurfsstrukturen online erstellt werden.<br /><br /> **ON**<br /> Alle empfohlenen physischen Entwurfsstrukturen können online erstellt werden.<br /><br /> **GEMISCHT**<br /> Der Datenbankoptimierungsratgeber versucht, sofern möglich physische Entwurfsstrukturen zu empfehlen, die online erstellt werden können.<br /><br /> Verwenden Sie einen dieser Werte mit diesem Element. Wenn Indizes online erstellt werden, wird das Schlüsselwort **ONLINE = ON** an die Objektdefinition angehängt.|  
|**Standardwert**|Keine.|  
|**Vorkommen**|Optional. Wenn Sie verwendet wird, kann nur einmal für das-Element verwendet werden `TuningOptions` .|  
  
## <a name="element-relationships"></a>Elementbeziehungen  
  
|Beziehung|Elemente|  
|------------------|--------------|  
|**Übergeordnetes Element**|[TuningOptions-Element &#40;DTA&#41;](tuningoptions-element-dta.md)|  
|**Untergeordnete Elemente**|Keine.|  
  
## <a name="example"></a>Beispiel  
 Ein Beispiel für die Verwendung dieses Elements finden Sie unter [Beispiel für eine einfache XML-Eingabedatei &#40;DTA&#41;](simple-xml-input-file-sample-dta.md).  
  
## <a name="see-also"></a>Weitere Informationen  
 [XML-Eingabedateireferenz &#40;Datenbankoptimierungsratgeber&#41;](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
