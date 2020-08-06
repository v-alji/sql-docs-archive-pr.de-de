---
title: Behandeln von Large Object-Parametern (LOB) in der CLR | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- large data, CLR integration
- LOB data [SQL Server], CLR integration
- SqlBytes data type
- SqlChars data type
ms.assetid: d07956f6-9543-4476-9426-536f95991150
author: rothja
ms.author: jroth
ms.openlocfilehash: ee791c73a6610761c2086723f9e41c2351b37dd0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725957"
---
# <a name="handling-large-object-lob-parameters-in-the-clr"></a>Behandlung von LOB-Parametern (Large Object) in der CLR-Routine
  Verwenden Sie `SqlBytes` und `SqlChars`, um binäre LOB-Parameter (`varbinary(max)`) bzw. LOB-Zeichenparameter (`nvarchar(max)`) zu übergeben. Mithilfe dieser Parameter können die LOB-Werte von der Datenbank an die CLR-Routine (Common Language Runtime) in einem Strom übergeben werden, sodass nicht der gesamte Wert in einen verwalteten Bereich kopiert werden muss. `SqlBinary` und `SqlString` dürden nur für kleine Binär- und Zeichenfolgenwerte verwendet werden.  
  
## <a name="see-also"></a>Weitere Informationen  
 [SQL Server-Datentypen in .NET Framework](sql-server-data-types-in-the-net-framework.md)  
  
  
