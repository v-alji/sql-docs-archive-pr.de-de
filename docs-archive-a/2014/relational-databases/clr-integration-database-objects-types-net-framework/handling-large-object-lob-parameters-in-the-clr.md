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
# <a name="handling-large-object-lob-parameters-in-the-clr"></a><span data-ttu-id="d5ef9-102">Behandlung von LOB-Parametern (Large Object) in der CLR-Routine</span><span class="sxs-lookup"><span data-stu-id="d5ef9-102">Handling Large Object (LOB) Parameters in the CLR</span></span>
  <span data-ttu-id="d5ef9-103">Verwenden Sie `SqlBytes` und `SqlChars`, um binäre LOB-Parameter (`varbinary(max)`) bzw. LOB-Zeichenparameter (`nvarchar(max)`) zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="d5ef9-103">Use `SqlBytes` and `SqlChars` to pass large object (LOB) binary type (`varbinary(max)`) and LOB character type (`nvarchar(max)`) parameters, respectively.</span></span> <span data-ttu-id="d5ef9-104">Mithilfe dieser Parameter können die LOB-Werte von der Datenbank an die CLR-Routine (Common Language Runtime) in einem Strom übergeben werden, sodass nicht der gesamte Wert in einen verwalteten Bereich kopiert werden muss.</span><span class="sxs-lookup"><span data-stu-id="d5ef9-104">These types allow streaming the LOB values from the database to the common language runtime (CLR) routine, instead of copying the entire value into managed space.</span></span> <span data-ttu-id="d5ef9-105">`SqlBinary` und `SqlString` dürden nur für kleine Binär- und Zeichenfolgenwerte verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d5ef9-105">`SqlBinary` and `SqlString` should be used only for small binary and character string values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5ef9-106">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d5ef9-106">See Also</span></span>  
 [<span data-ttu-id="d5ef9-107">SQL Server-Datentypen in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d5ef9-107">SQL Server Data Types in the .NET Framework</span></span>](sql-server-data-types-in-the-net-framework.md)  
  
  
