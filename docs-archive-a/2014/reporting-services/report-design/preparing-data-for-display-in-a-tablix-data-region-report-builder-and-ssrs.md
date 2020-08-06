---
title: Daten für die Anzeige in einem Tablix-Datenbereich vorbereiten (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: fbb00dc6-7887-480c-b771-cab6fecb8dcc
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 72ac150f2dcd227b1e3afb624a5ca5866fb4c360
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621353"
---
# <a name="preparing-data-for-display-in-a-tablix-data-region-report-builder-and-ssrs"></a><span data-ttu-id="87b94-102">Vorbereiten von Daten für die Anzeige in einem Tablix-Datenbereich (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="87b94-102">Preparing Data for Display in a Tablix Data Region (Report Builder and SSRS)</span></span>
  <span data-ttu-id="87b94-103">Ein Tablix-Datenbereich zeigt Daten aus einem Dataset an.</span><span class="sxs-lookup"><span data-stu-id="87b94-103">A tablix data region displays data from a dataset.</span></span> <span data-ttu-id="87b94-104">Sie können alle für das Dataset abgerufenen Daten anzeigen oder Filter erstellen, sodass nur eine Teilmenge der Daten angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="87b94-104">You can view all the data retrieved for the dataset or you can create filters so that you see only a subset of the data.</span></span> <span data-ttu-id="87b94-105">Sie können auch bedingte Ausdrücke hinzufügen, um NULL-Werte aufzufüllen, oder die Abfrage für ein Dataset so ändern, dass Spalten mit Definitionen der Sortierreihenfolge für eine vorhandene Spalte enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="87b94-105">You can also add conditional expressions to fill in null values or modify the query for a dataset to include columns that define the sort order for an existing column.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="working-with-nulls-and-blanks-in-field-values"></a><span data-ttu-id="87b94-106">Verwenden von NULL- und leeren Werten in Feldwerten</span><span class="sxs-lookup"><span data-stu-id="87b94-106">Working with Nulls and Blanks in Field Values</span></span>  
 <span data-ttu-id="87b94-107">Daten für die Feldauflistung in einem Dataset enthalten alle zur Laufzeit aus der Datenquelle abgerufenen Werte, einschließlich von NULL- und leeren Werten.</span><span class="sxs-lookup"><span data-stu-id="87b94-107">Data for the field collection in a dataset includes all values retrieved from the data source at run time, including null values and blanks.</span></span> <span data-ttu-id="87b94-108">Normalerweise können NULL-Werte und leere Werte nicht unterschieden werden.</span><span class="sxs-lookup"><span data-stu-id="87b94-108">Normally null values and blanks are indistinguishable.</span></span> <span data-ttu-id="87b94-109">Dies stellt in den meisten Fällen das gewünschte Verhalten dar.</span><span class="sxs-lookup"><span data-stu-id="87b94-109">In most cases, this is the desired behavior.</span></span> <span data-ttu-id="87b94-110">Beispiel: Numerische Aggregatfunktionen wie [Sum](report-builder-functions-sum-function.md) und [Avg](report-builder-functions-avg-function.md) ignorieren NULL-Werte.</span><span class="sxs-lookup"><span data-stu-id="87b94-110">For example, Numeric aggregate functions like [Sum](report-builder-functions-sum-function.md) and [Avg](report-builder-functions-avg-function.md) ignore null values.</span></span> <span data-ttu-id="87b94-111">Weitere Informationen finden Sie unter [Aggregatfunktionsreferenz &#40;Berichts-Generator und SSRS&#41;](report-builder-functions-aggregate-functions-reference.md).</span><span class="sxs-lookup"><span data-stu-id="87b94-111">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md).</span></span>  
  
 <span data-ttu-id="87b94-112">Wenn Sie NULL-Werte auf andere Weise behandeln möchten, können Sie bedingte Ausdrücke oder benutzerdefinierten Code verwenden, um den NULL-Wert durch einen benutzerdefinierten Wert zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="87b94-112">If you do want to handle null values differently, you can use conditional expressions or custom code to substitute a custom value for the null value.</span></span> <span data-ttu-id="87b94-113">Durch den folgenden Ausdruck wird beispielsweise der Text `Null` für jeden NULL-Wert im Feld `[Size]`eingesetzt.</span><span class="sxs-lookup"><span data-stu-id="87b94-113">For example, the following expression substitutes the text `Null` wherever a null value occurs in the field `[Size]`.</span></span>  
  
```  
=IIF(Fields!Size.Value IS NOTHING,"Null",Fields!Size.Value)  
```  
  
 <span data-ttu-id="87b94-114">Weitere Informationen über das Ausschließen von NULL-Werten in den Daten vor dem Abruf der Daten aus einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenquelle mithilfe von [!INCLUDE[tsql](../../includes/tsql-md.md)] -Abfragen finden Sie unter "NULL-Werte" und "NULL-Werte und Joins" in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Dokumentation in der [SQL Server-Onlinedokumentation](https://go.microsoft.com/fwlink/?linkid=120955).</span><span class="sxs-lookup"><span data-stu-id="87b94-114">For more information about eliminating nulls in your data before retrieving the data from a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data source using [!INCLUDE[tsql](../../includes/tsql-md.md)] queries, see "Null Values" and "Null Values and Joins" in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] documentation in [SQL Server Books Online](https://go.microsoft.com/fwlink/?linkid=120955).</span></span>  
  
## <a name="handling-null-field-names"></a><span data-ttu-id="87b94-115">Behandeln von NULL-Feldnamen</span><span class="sxs-lookup"><span data-stu-id="87b94-115">Handling Null Field Names</span></span>  
 <span data-ttu-id="87b94-116">Die Überprüfung auf NULL-Werte in einem Ausdruck ist problemlos möglich, sofern das Feld selbst im Abfrageresultset vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="87b94-116">Testing for null values in an expression is fine as long as the field itself exists in the query result set.</span></span> <span data-ttu-id="87b94-117">Sie können in benutzerdefinierten Code überprüfen, ob das Feld selbst in den Auflistungsfeldern vorhanden ist, die zur Laufzeit von der Datenquelle zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="87b94-117">From custom code, you can test whether the field itself is present in the collection fields returned from the data source at run time.</span></span> <span data-ttu-id="87b94-118">Weitere Informationen finden Sie unter [Verweise auf Datasetfeld-Auflistungen &#40;Berichts-Generator und SSRS&#41;](built-in-collections-dataset-fields-collection-references-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="87b94-118">For more information, see [Dataset Fields Collection References &#40;Report Builder and SSRS&#41;](built-in-collections-dataset-fields-collection-references-report-builder.md).</span></span>  
  
## <a name="adding-a-sort-order-column"></a><span data-ttu-id="87b94-119">Hinzufügen einer Sortierenreihenfolge-Spalte</span><span class="sxs-lookup"><span data-stu-id="87b94-119">Adding a Sort Order Column</span></span>  
 <span data-ttu-id="87b94-120">Standardmäßig können Sie Werte in einem Datasetfeld alphabetisch sortieren.</span><span class="sxs-lookup"><span data-stu-id="87b94-120">By default, you can alphabetically sort values in a dataset field.</span></span> <span data-ttu-id="87b94-121">Um in einer anderen Reihenfolge zu sortieren, können Sie dem Dataset eine neue Spalte hinzufügen, die die für den Datenbereich gewünschte Sortierreihenfolge definiert.</span><span class="sxs-lookup"><span data-stu-id="87b94-121">To sort in a different order, you can add a new column to your dataset that defines the sort order you want in a data region.</span></span> <span data-ttu-id="87b94-122">Wenn Sie beispielsweise nach dem Feld `[Color]` mit weißen und schwarzen Elementen am Anfang sortieren möchten, können Sie die Spalte `[ColorSortOrder]`wie in der folgenden Abfrage hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="87b94-122">For example, to sort on the field `[Color]` and sort white and black items first, you can add a column `[ColorSortOrder]`, shown in the following query:</span></span>  
  
```  
SELECT ProductID, p.Name, Color,  
   CASE  
      WHEN p.Color = 'White' THEN 1  
      WHEN p.Color = 'Black' THEN 2  
      WHEN p.Color = 'Blue' THEN 3  
      WHEN p.Color = 'Yellow' THEN 4  
      ELSE 5  
   END As ColorSortOrder  
FROM Production.Product p  
```  
  
 <span data-ttu-id="87b94-123">Um einen Tabellendatenbereich nach dieser Sortierreihenfolge zu sortieren, legen Sie den Sortierausdruck für die Detailgruppe auf `=Fields!ColorSortOrder.Value`fest.</span><span class="sxs-lookup"><span data-stu-id="87b94-123">To sort a table data region according to this sort order, set the sort expression on the detail group to `=Fields!ColorSortOrder.Value`.</span></span> <span data-ttu-id="87b94-124">Weitere Informationen finden Sie unter [Sortieren von Daten in einem Datenbereich (Berichts-Generator und SSRS)](sort-data-in-a-data-region-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="87b94-124">For more information, see [Sort Data in a Data Region &#40;Report Builder and SSRS&#41;](sort-data-in-a-data-region-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87b94-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="87b94-125">See Also</span></span>  
 <span data-ttu-id="87b94-126">[Datasetfeld-Sammlung &#40;Berichts-Generator und SSRS&#41;](../report-data/dataset-fields-collection-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="87b94-126">[Dataset Fields Collection &#40;Report Builder and SSRS&#41;](../report-data/dataset-fields-collection-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="87b94-127">[Ausdrücke &#40;Berichts-Generator und SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="87b94-127">[Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="87b94-128">Filtern, Gruppieren und Sortieren von Daten &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="87b94-128">Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;</span></span>](filter-group-and-sort-data-report-builder-and-ssrs.md)  
  
  
