---
title: Auswählen von Zeilen, die mit einem Wert nicht übereinstimmen (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- search conditions [SQL Server], rows not matching value
- row not matching value [SQL Server]
- NOT operator [Visual Database Tools]
- search criteria [SQL Server], rows not matching value
ms.assetid: 19898578-7b2f-401c-bb8f-9f2a017efdf7
author: stevestein
ms.author: sstein
ms.openlocfilehash: 412ec93cbfedc87e92da9e86c7e4c7455919722a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719318"
---
# <a name="select-rows-that-do-not-match-a-value-visual-database-tools"></a><span data-ttu-id="8b277-102">Auswählen von Zeilen, die mit einem Wert nicht übereinstimmen (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="8b277-102">Select Rows That Do Not Match a Value (Visual Database Tools)</span></span>
  <span data-ttu-id="8b277-103">Zum Suchen von Zeilen, die mit einem Wert nicht übereinstimmen, wird der Operator NOT verwendet.</span><span class="sxs-lookup"><span data-stu-id="8b277-103">To find rows that do not match a value, use the NOT operator.</span></span>  
  
### <a name="to-find-rows-that-do-not-match-a-value"></a><span data-ttu-id="8b277-104">So suchen Sie nach Zeilen, die mit einem Wert nicht übereinstimmen</span><span class="sxs-lookup"><span data-stu-id="8b277-104">To find rows that do not match a value</span></span>  
  
1.  <span data-ttu-id="8b277-105">Fügen Sie im [Kriterienbereich](visual-database-tools.md)die Spalten oder Ausdrücke hinzu, die in der Suchbedingung verwendet werden sollen, falls dies nicht bereits geschehen ist.</span><span class="sxs-lookup"><span data-stu-id="8b277-105">If you have not done so already, add the columns or expressions that you want to use within your search condition to the [Criteria pane](visual-database-tools.md).</span></span>  
  
2.  <span data-ttu-id="8b277-106">Wechseln Sie zu der Zeile, die die Datenspalte oder den Ausdruck für die Suche enthält. Geben Sie anschließend in der Datenblattspalte **Filter** den Operator NOT gefolgt von einem Suchwert ein.</span><span class="sxs-lookup"><span data-stu-id="8b277-106">Locate the row containing the data column or expression to search, and then in the **Filter** grid column, enter the NOT operator followed by a search value.</span></span>  
  
 <span data-ttu-id="8b277-107">Um beispielsweise alle Zeilen in der Tabelle `products` zu suchen, in denen der Wert in der Spalte für den Produktcode nicht mit "A" beginnt, können Sie folgende Suchbedingung eingeben:</span><span class="sxs-lookup"><span data-stu-id="8b277-107">For example, to find all the rows in a `products` table where the values in the product code column begin with a character other than "A," you can enter a search condition such as the following:</span></span>  
  
```  
NOT LIKE 'A%'  
```  
  
## <a name="see-also"></a><span data-ttu-id="8b277-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8b277-108">See Also</span></span>  
 <span data-ttu-id="8b277-109">[Regeln für das Eingeben von Such Werten &#40;Visual Database Tools&#41;](rules-for-entering-search-values-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="8b277-109">[Rules for Entering Search Values &#40;Visual Database Tools&#41;](rules-for-entering-search-values-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="8b277-110">Angeben von Suchkriterien &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="8b277-110">Specify Search Criteria &#40;Visual Database Tools&#41;</span></span>](specify-search-criteria-visual-database-tools.md)  
  
  
