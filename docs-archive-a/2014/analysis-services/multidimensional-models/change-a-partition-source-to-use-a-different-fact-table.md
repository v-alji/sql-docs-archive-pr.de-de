---
title: Ändern einer Partitions Quelle für die Verwendung einer anderen Fakten Tabelle | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- fact tables [Analysis Services]
- partitions [Analysis Services], fact tables
ms.assetid: 5508312f-8e46-4802-9362-6688ca03d098
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0063a6023d769dc6dccd616655d10e0bd3c65a98
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721998"
---
# <a name="change-a-partition-source-to-use-a-different-fact-table"></a>Ändern einer Partitionsquelle für die Verwendung einer anderen Faktentabelle
  Bei der Erstellung von Partitionen können Sie für Cubes unterschiedliche Faktentabellen verwenden. Die unterschiedlichen Tabellen können dabei aus einer einzelnen Datenquellensicht, aus verschiedenen Datenquellensichten oder aus verschiedenen Datenquellen stammen. Eine Datenquellensicht kann auch unterschiedliche Tabellen aus mehreren Datenquellen enthalten.  
  
 Alle Faktentabellen und Dimensionen für die Partitionen eines Cubes müssen dieselbe Struktur wie die Faktentabelle und die Dimensionen des Cubes besitzen. Unterschiedliche Faktentabellen können z. B. dieselbe Struktur besitzen, aber Daten für verschiedene Jahre oder verschiedene Produktlinien enthalten.  
  
 Eine Faktentabelle geben Sie auf der Seite **Quellinformationen angeben** des Partitions-Assistenten an. Geben Sie auf dieser Seite im Gruppenfeld Partitionsquelle neben **Suchen in**an, in welcher Datenquelle bzw. Datenquellensicht gesucht werden soll. Klicken Sie als Nächstes auf **Tabellen suchen**, und wählen Sie dann unter **Verfügbare Tabellen**die zu verwendende Tabelle aus.  
  
 Wenn Sie unterschiedliche Faktentabellen verwenden, sollten Sie sicherstellen, dass in den Partitionen keine Daten doppelt auftreten. Wenn eine Faktentabelle z. B. Transaktionen nur für das Jahr 2012 und eine andere Faktentabelle Transaktionen nur für das Jahr 2013 enthält, weisen diese Tabellen unabhängige Daten auf. Ebenso sind Faktentabellen für verschiedene Produktlinien oder verschiedene geografische Gebiete unabhängig voneinander.  
  
 Es ist möglich, aber nicht empfehlenswert, dass Sie unterschiedliche Faktentabellen verwenden, die doppelte Daten enthalten. In diesem Fall müssen Sie Filter in den Partitionen verwenden, um sicherzustellen, dass die von einer Partition verwendeten Daten nicht von einer anderen Partition verwendet werden. Weitere Informationen finden Sie unter [Erstellen und Verwalten einer lokalen Partition &#40;Analysis Services&#41;](create-and-manage-a-local-partition-analysis-services.md).  
  
## <a name="see-also"></a>Weitere Informationen  
 [Erstellen und Verwalten einer lokalen Partition &#40;Analysis Services&#41;](create-and-manage-a-local-partition-analysis-services.md)  
  
  
