---
title: Häufig verwendete Filter (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- multivalued parameters [Reporting Services]
- single-valued parameters [Reporting Services]
- parameters [Reporting Services], multivalued
- valid values [Reporting Services]
ms.assetid: cb70d0cd-707b-4de5-b39f-e4eb57d316aa
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 201cf83d431d1b61e0f20e9d039b2016ad4f13e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618497"
---
# <a name="commonly-used-filters-report-builder-and-ssrs"></a><span data-ttu-id="10d62-102">Häufig verwendete Filter (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="10d62-102">Commonly Used Filters (Report Builder and SSRS)</span></span>
  <span data-ttu-id="10d62-103">Zum Erstellen eines Filters müssen Sie mindestens eine Filtergleichung angeben.</span><span class="sxs-lookup"><span data-stu-id="10d62-103">To create a filter, you must specify one or more filter equations.</span></span> <span data-ttu-id="10d62-104">Eine Filtergleichung schließt einen Ausdruck, einen Datentyp, einen Operator und einen Wert ein.</span><span class="sxs-lookup"><span data-stu-id="10d62-104">A filter equation includes an expression, a data type, an operator, and a value.</span></span> <span data-ttu-id="10d62-105">Dieses Thema enthält Beispiele für häufig verwendete Filter.</span><span class="sxs-lookup"><span data-stu-id="10d62-105">This topic provides examples of commonly used filters.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="filter-examples"></a><span data-ttu-id="10d62-106">Beispiele für Filter</span><span class="sxs-lookup"><span data-stu-id="10d62-106">Filter Examples</span></span>  
 <span data-ttu-id="10d62-107">In der folgenden Tabelle werden Beispiele für Filtergleichungen dargestellt, die andere Datentypen und andere Operatoren verwenden.</span><span class="sxs-lookup"><span data-stu-id="10d62-107">The following table shows examples of filter equations that use different data types and different operators.</span></span> <span data-ttu-id="10d62-108">Der Bereich für den Vergleich wird von dem Berichtselement bestimmt, für das ein Filter definiert wird.</span><span class="sxs-lookup"><span data-stu-id="10d62-108">The scope for the comparison is determined by report item for which a filter is defined.</span></span> <span data-ttu-id="10d62-109">Beispiel: Bei einem für ein Dataset definierten Filter bezeichnet **Erste % 10** die ersten 10 Prozent der Werte im Dataset. Im Falle eines für eine Gruppe definierten Filters bedeutet **Erste % 10** die ersten 10 Prozent der Werte in der Gruppe.</span><span class="sxs-lookup"><span data-stu-id="10d62-109">For example, for a filter defined on a dataset, **TOP % 10** is the top 10 percent of values in the dataset; for a filter defined on a group, **TOP % 10** is the top 10 percent of values in the group.</span></span>  
  
|<span data-ttu-id="10d62-110">Einfacher Ausdruck</span><span class="sxs-lookup"><span data-stu-id="10d62-110">Simple Expression</span></span>|<span data-ttu-id="10d62-111">Datentyp</span><span class="sxs-lookup"><span data-stu-id="10d62-111">Data Type</span></span>|<span data-ttu-id="10d62-112">Operator</span><span class="sxs-lookup"><span data-stu-id="10d62-112">Operator</span></span>|<span data-ttu-id="10d62-113">value</span><span class="sxs-lookup"><span data-stu-id="10d62-113">Value</span></span>|<span data-ttu-id="10d62-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="10d62-114">Description</span></span>|  
|-----------------------|---------------|--------------|-----------|-----------------|  
|`[SUM(Quantity)]`|`Integer`|`>`|`7`|<span data-ttu-id="10d62-115">Schließt Datenwerte ein, die größer als 7 sind.</span><span class="sxs-lookup"><span data-stu-id="10d62-115">Includes data values that are greater than 7.</span></span>|  
|`[SUM(Quantity)]`|`Integer`|`TOP N`|`10`|<span data-ttu-id="10d62-116">Schließt die ersten 10 Datenwerte ein.</span><span class="sxs-lookup"><span data-stu-id="10d62-116">Includes the top 10 data values.</span></span>|  
|`[SUM(Quantity)]`|`Integer`|`TOP %`|`20`|<span data-ttu-id="10d62-117">Schließt die ersten 20 % der Datenwerte ein.</span><span class="sxs-lookup"><span data-stu-id="10d62-117">Includes the top 20% of data values.</span></span>|  
|`[Sales]`|`Text`|`>`|`=CDec(100)`|<span data-ttu-id="10d62-118">Schließt alle Werte des Typs System.Decimal (SQL-Datentyp "money") größer als $100 ein.</span><span class="sxs-lookup"><span data-stu-id="10d62-118">Includes all values of type System.Decimal (SQL "money" data types) greater than $100.</span></span>|  
|`[OrderDate]`|`DateTime`|`>`|`2088-01-01`|<span data-ttu-id="10d62-119">Schließt alle Datumsangaben vom 1. Januar 2008 bis zum gegenwärtigen Datum ein.</span><span class="sxs-lookup"><span data-stu-id="10d62-119">Includes all dates from January 1, 2008 to the present date.</span></span>|  
|`[OrderDate]`|`DateTime`|`BETWEEN`|`2008-01-01`<br /><br /> `2008-02-01`|<span data-ttu-id="10d62-120">Schließt Datumsangaben vom 1. Januar 2008 bis zum 1. Februar 2008 einschließlich ein.</span><span class="sxs-lookup"><span data-stu-id="10d62-120">Includes dates from January 1, 2008 up to and including February 1, 2008.</span></span>|  
|`[Territory]`|`Text`|`LIKE`|`*east`|<span data-ttu-id="10d62-121">Alle Gebietsnamen, die auf "east" enden.</span><span class="sxs-lookup"><span data-stu-id="10d62-121">All territory names that end in "east".</span></span>|  
|`[Territory]`|`Text`|`LIKE`|`%o%th*`|<span data-ttu-id="10d62-122">Alle Gebietsnamen, die mit "North" und "South" beginnen.</span><span class="sxs-lookup"><span data-stu-id="10d62-122">All territory names that include North and South at the beginning of the name.</span></span>|  
|`=LEFT(Fields!Subcat.Value,1)`|`Text`|`IN`|`B, C, T`|<span data-ttu-id="10d62-123">Alle Unterkategoriewerte, die mit B, C oder T beginnen.</span><span class="sxs-lookup"><span data-stu-id="10d62-123">All subcategory values that begin with the letters B, C, or T.</span></span>|  
  
## <a name="examples-with-report-parameters"></a><span data-ttu-id="10d62-124">Beispiele für Berichtsparameter</span><span class="sxs-lookup"><span data-stu-id="10d62-124">Examples with Report Parameters</span></span>  
 <span data-ttu-id="10d62-125">In der folgenden Tabelle werden Beispiele für Filterausdrücke bereitgestellt, die einen einwertigen oder mehrwertigen Parameterverweis einschließen.</span><span class="sxs-lookup"><span data-stu-id="10d62-125">The following table provides examples of filter expression that includes a single-value or multivalue parameter reference.</span></span>  
  
|<span data-ttu-id="10d62-126">Parametertyp</span><span class="sxs-lookup"><span data-stu-id="10d62-126">Parameter type</span></span>|<span data-ttu-id="10d62-127">(Filter-)Ausdruck</span><span class="sxs-lookup"><span data-stu-id="10d62-127">(Filter) Expression</span></span>|<span data-ttu-id="10d62-128">Operator</span><span class="sxs-lookup"><span data-stu-id="10d62-128">Operator</span></span>|<span data-ttu-id="10d62-129">Wert</span><span class="sxs-lookup"><span data-stu-id="10d62-129">Value</span></span>|<span data-ttu-id="10d62-130">Datentyp</span><span class="sxs-lookup"><span data-stu-id="10d62-130">Data Type</span></span>|  
|--------------------|---------------------------|--------------|-----------|---------------|  
|<span data-ttu-id="10d62-131">Einzelwert</span><span class="sxs-lookup"><span data-stu-id="10d62-131">Single value</span></span>|`[EmployeeID]`|=|`[@EmployeeID]`|<span data-ttu-id="10d62-132">Integer</span><span class="sxs-lookup"><span data-stu-id="10d62-132">Integer</span></span>|  
|<span data-ttu-id="10d62-133">Mehrwertig</span><span class="sxs-lookup"><span data-stu-id="10d62-133">Multivalue</span></span>|`[EmployeeID]`|<span data-ttu-id="10d62-134">IN</span><span class="sxs-lookup"><span data-stu-id="10d62-134">IN</span></span>|`[@EmployeeID]`|<span data-ttu-id="10d62-135">Integer</span><span class="sxs-lookup"><span data-stu-id="10d62-135">Integer</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="10d62-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="10d62-136">See Also</span></span>  
 <span data-ttu-id="10d62-137">[Berichts Parameter &#40;Berichts-Generator und Berichts-Designer&#41;](report-parameters-report-builder-and-report-designer.md) </span><span class="sxs-lookup"><span data-stu-id="10d62-137">[Report Parameters &#40;Report Builder and Report Designer&#41;](report-parameters-report-builder-and-report-designer.md) </span></span>  
 <span data-ttu-id="10d62-138">[Hinzufügen von datasetfiltern, Datenbereichs Filtern und Gruppen Filtern &#40;Berichts-Generator und SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span><span class="sxs-lookup"><span data-stu-id="10d62-138">[Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span></span>  
 <span data-ttu-id="10d62-139">[Ausdruck verwendet in Berichten &#40;Berichts-Generator und SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="10d62-139">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="10d62-140">[Beispiele für Ausdrücke &#40;Berichts-Generator und SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="10d62-140">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="10d62-141">Datentypen in Ausdrücken (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="10d62-141">Data Types in Expressions &#40;Report Builder and SSRS&#41;</span></span>](expressions-report-builder-and-ssrs.md)  
  
  
