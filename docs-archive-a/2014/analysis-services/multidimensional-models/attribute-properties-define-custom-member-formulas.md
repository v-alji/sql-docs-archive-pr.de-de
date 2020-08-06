---
title: Definieren von benutzerdefinierten Element Formeln | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- members [Analysis Services], custom
- custom rollup formulas [Analysis Services]
- MDX [Analysis Services], custom rollup formulas
- custom member formulas [Analysis Services]
ms.assetid: 258304e2-d900-4013-97e3-871f51dfdce2
author: minewiskan
ms.author: owend
ms.openlocfilehash: 51649bea0c4134971b342b779c778b857343e62b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725122"
---
# <a name="define-custom-member-formulas"></a><span data-ttu-id="92b92-102">Definieren von benutzerdefinierten Elementformeln</span><span class="sxs-lookup"><span data-stu-id="92b92-102">Define Custom Member Formulas</span></span>
  <span data-ttu-id="92b92-103">Sie können einen MDX-Ausdruck (Multidimensional Expressions), eine so genannte benutzerdefinierte Elementformel, erstellen, um die Werte für die Mitglieder eines angegebenen Attributs bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="92b92-103">You can define a Multidimensional Expressions (MDX) expression, called a custom member formula, to supply the values for the members of a specified attribute.</span></span> <span data-ttu-id="92b92-104">Eine Spalte in einer Tabelle einer Datenquellensicht stellt für jedes Mitglied in einem Attribut den Ausdruck bereit, der zur Bereitstellung des Wertes für dieses Element verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="92b92-104">A column in a table from a data source view provides, for each member in an attribute, the expression used to supply the value for that member.</span></span>  
  
 <span data-ttu-id="92b92-105">Benutzerdefinierte Elementformeln bestimmen die Zellwerte, die mit Elementen verknüpft sind, und überschreiben die Aggregatfunktionen von Measures.</span><span class="sxs-lookup"><span data-stu-id="92b92-105">Custom member formulas determine the cell values that are associated with members and override the aggregate functions of measures.</span></span> <span data-ttu-id="92b92-106">Benutzerdefinierte Elementformeln sind in MDX geschrieben.</span><span class="sxs-lookup"><span data-stu-id="92b92-106">Custom member formulas are written in MDX.</span></span> <span data-ttu-id="92b92-107">Jede benutzerdefinierte Elementformel gilt für ein einziges Element.</span><span class="sxs-lookup"><span data-stu-id="92b92-107">Each custom member formula applies to a single member.</span></span> <span data-ttu-id="92b92-108">Benutzerdefinierte Elementformeln werden in der Dimensionstabelle oder in einer anderen Tabelle gespeichert, für die eine Fremdschlüsselbeziehung mit der Dimensionstabelle besteht.</span><span class="sxs-lookup"><span data-stu-id="92b92-108">Custom member formulas are stored in the dimension table or in another table that has a foreign key relationship with the dimension table.</span></span>  
  
 <span data-ttu-id="92b92-109">Die `CustomRollupColumn`-Eigenschaft für ein Attribut gibt die Spalte an, in der die benutzerdefinierten Elementformeln für Elemente des Attributs enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="92b92-109">The `CustomRollupColumn` property on an attribute specifies the column that contains custom member formulas for members of the attribute.</span></span> <span data-ttu-id="92b92-110">Ist eine Zeile in der Spalte leer, wird der Zellwert für das Element normal zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="92b92-110">If a row in the column is empty, the cell value for the member is returned normally.</span></span> <span data-ttu-id="92b92-111">Ist die Formel in der Spalte nicht gültig, gibt es einen Laufzeitfehler, sobald ein Zellwert abgerufen wird, der das Element verwendet.</span><span class="sxs-lookup"><span data-stu-id="92b92-111">If the formula in the column is not valid, a run-time error occurs whenever a cell value that uses the member is retrieved.</span></span>  
  
 <span data-ttu-id="92b92-112">Vor dem Angeben benutzerdefinierter Elementformeln für ein Attribut sollten Sie sicherstellen, dass die Dimensionstabelle, die das Attribut enthält, bzw. eine direkt verknüpfte Tabelle über eine Zeichenfolgenspalte zum Speichern der benutzerdefinierten Elementformeln verfügt.</span><span class="sxs-lookup"><span data-stu-id="92b92-112">Before you can specify custom member formulas for an attribute, make sure that the dimension table that contains the attribute, or a directly related table, has a string column to store the custom member formulas.</span></span> <span data-ttu-id="92b92-113">Wenn dies der Fall ist, können Sie entweder die- `CustomRollupColumn` Eigenschaft für ein Attribut manuell festlegen oder die Erweiterung benutzerdefinierte Element Formel festlegen des Business Intelligence-Assistenten verwenden, um eine benutzerdefinierte Element Formel für ein Attribut zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="92b92-113">If this is the case, you can either set the `CustomRollupColumn` property on an attribute manually or use the Set Custom Member Formula enhancement of the Business Intelligence Wizard to enable a custom member formula on an attribute.</span></span> <span data-ttu-id="92b92-114">Weitere Informationen zum Verwenden dieser Erweiterung finden Sie unter [Festlegen benutzerdefinierter Elementformeln für Attribute in einer Dimension](bi-wizard-custom-member-formulas-for-attributes-in-a-dimension.md).</span><span class="sxs-lookup"><span data-stu-id="92b92-114">For more information about how to use this enhancement, see [Set Custom Member Formulas for Attributes in a Dimension](bi-wizard-custom-member-formulas-for-attributes-in-a-dimension.md).</span></span>  
  
## <a name="evaluating-custom-member-formulas"></a><span data-ttu-id="92b92-115">Auswerten von benutzerdefinierten Elementformeln</span><span class="sxs-lookup"><span data-stu-id="92b92-115">Evaluating Custom Member Formulas</span></span>  
 <span data-ttu-id="92b92-116">Benutzerdefinierte Elementformeln unterscheiden sich von berechneten Elementen.</span><span class="sxs-lookup"><span data-stu-id="92b92-116">Custom member formulas differ from calculated members.</span></span> <span data-ttu-id="92b92-117">Benutzerdefinierte Elementformeln gelten für Elemente in Dimensionstabellen und stellen lediglich den Wert des Elements bereit.</span><span class="sxs-lookup"><span data-stu-id="92b92-117">Custom member formulas apply to members that exist in dimension tables, and only provide the value of the member.</span></span> <span data-ttu-id="92b92-118">Berechnete Elemente hingegen werden nicht in Dimensionstabellen gespeichert, und berechnete Elementausdrücke definieren sowohl Daten als auch Metadaten für zusätzliche Elemente in einer Dimension oder Hierarchie.</span><span class="sxs-lookup"><span data-stu-id="92b92-118">In contrast, calculated members are not stored in dimension tables, and calculated member expressions define both data and metadata for additional members included in a dimension or hierarchy.</span></span>  
  
 <span data-ttu-id="92b92-119">Benutzerdefinierte Elementformeln überschreiben die zu Measures gehörenden Aggregationsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="92b92-119">Custom member formulas override the aggregate functions associated with measures.</span></span> <span data-ttu-id="92b92-120">Bevor beispielsweise eine benutzerdefinierte Elementformel angegeben wird, weist ein Measure bei Verwendung der `Sum`-Aggregationsfunktion die folgenden Werte für die Elemente der Time-Dimension auf:</span><span class="sxs-lookup"><span data-stu-id="92b92-120">For example, before a custom member formula is specified, a measure using the `Sum` aggregate function has the following values for the following members of the Time dimension:</span></span>  
  
-   <span data-ttu-id="92b92-121">2003: 2100</span><span class="sxs-lookup"><span data-stu-id="92b92-121">2003: 2100</span></span>  
  
    -   <span data-ttu-id="92b92-122">Quartal 1: 700</span><span class="sxs-lookup"><span data-stu-id="92b92-122">Quarter 1: 700</span></span>  
  
    -   <span data-ttu-id="92b92-123">Quartal 2: 500</span><span class="sxs-lookup"><span data-stu-id="92b92-123">Quarter 2: 500</span></span>  
  
    -   <span data-ttu-id="92b92-124">Quartal 3: 100</span><span class="sxs-lookup"><span data-stu-id="92b92-124">Quarter 3: 100</span></span>  
  
    -   <span data-ttu-id="92b92-125">Quartal 4: 800</span><span class="sxs-lookup"><span data-stu-id="92b92-125">Quarter 4: 800</span></span>  
  
-   <span data-ttu-id="92b92-126">2004: 1500</span><span class="sxs-lookup"><span data-stu-id="92b92-126">2004: 1500</span></span>  
  
    -   <span data-ttu-id="92b92-127">Quartal 1: 600</span><span class="sxs-lookup"><span data-stu-id="92b92-127">Quarter 1: 600</span></span>  
  
    -   <span data-ttu-id="92b92-128">Quartal 2: 200</span><span class="sxs-lookup"><span data-stu-id="92b92-128">Quarter 2: 200</span></span>  
  
    -   <span data-ttu-id="92b92-129">Quartal 3: 300</span><span class="sxs-lookup"><span data-stu-id="92b92-129">Quarter 3: 300</span></span>  
  
    -   <span data-ttu-id="92b92-130">Quartal 4: 400</span><span class="sxs-lookup"><span data-stu-id="92b92-130">Quarter 4: 400</span></span>  
  
 <span data-ttu-id="92b92-131">Bei einer benutzerdefinierten Elementformel wird der Wert des Elements stattdessen von der benutzerdefinierten Rollupformel bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="92b92-131">With a custom member formula, the value of the member is instead supplied by the custom rollup formula.</span></span> <span data-ttu-id="92b92-132">Die folgende benutzerdefinierte Elementformel kann z. B. verwendet werden, um den Wert 450 für das untergeordnete Quarter 4-Element des 2004-Elements in der Time-Dimension anzugeben.</span><span class="sxs-lookup"><span data-stu-id="92b92-132">For example, the following custom member formula can be used to supply the value for the Quarter 4 child member of the 2004 member in the Time dimension as 450.</span></span>  
  
```  
Time.[Quarter 3] * 1.5  
```  
  
 <span data-ttu-id="92b92-133">Benutzerdefinierte Elementformeln werden in einer Spalte der Dimensionstabelle gespeichert.</span><span class="sxs-lookup"><span data-stu-id="92b92-133">Custom member formulas are stored in a column of the dimension table.</span></span> <span data-ttu-id="92b92-134">Benutzerdefinierte Rollupformeln werden durch Festlegen der `CustomRollupColumn`-Eigenschaft für ein Attribut aktiviert.</span><span class="sxs-lookup"><span data-stu-id="92b92-134">You enable custom rollup formulas by setting the `CustomRollupColumn` property on an attribute.</span></span>  
  
 <span data-ttu-id="92b92-135">Um einen einzelnen MDX-Ausdruck auf alle Elemente eines Attributs anzuwenden, erstellen Sie eine benannte Berechnung für die Dimensionstabelle, die einen MDX-Ausdruck als Literalzeichenfolge zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="92b92-135">To apply a single MDX expression to all members of an attribute, create a named calculation on the dimension table that returns an MDX expression as a literal string.</span></span> <span data-ttu-id="92b92-136">Legen Sie dann die benannte Berechnung mit der `CustomRollupColumn`-Eigenschaftseinstellung für das Attribut fest, das Sie konfigurieren wollen.</span><span class="sxs-lookup"><span data-stu-id="92b92-136">Then, specify the named calculation with the `CustomRollupColumn` property setting on the attribute that you want to configure.</span></span> <span data-ttu-id="92b92-137">Eine benannte Berechnung ist eine Spalte in einer Tabelle für die Datenquellensicht, die durch einen SQL-Ausdruck definierte Zeilenwerte zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="92b92-137">A named calculation is a column in a data source view table that returns row values defined by a SQL expression.</span></span> <span data-ttu-id="92b92-138">Weitere Informationen zum Erstellen von benannten Berechnungen finden Sie unter [Definieren von benannten Berechnungen in einer Datenquellensicht &#40;Analysis Services&#41;](define-named-calculations-in-a-data-source-view-analysis-services.md)</span><span class="sxs-lookup"><span data-stu-id="92b92-138">For more information about constructing named calculations, see [Define Named Calculations in a Data Source View &#40;Analysis Services&#41;](define-named-calculations-in-a-data-source-view-analysis-services.md)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="92b92-139">Um einen MDX-Ausdruck auf Elemente einer bestimmten Ebene und nicht basierend auf einem bestimmten Attribut auf Elemente aller Ebenen anzuwenden, können Sie den Ausdruck als MDX-Skript für die Ebene definieren.</span><span class="sxs-lookup"><span data-stu-id="92b92-139">To apply an MDX expression to members of a particular level instead of to members of all levels based on a particular attribute, you can define the expression as an MDX script on the level.</span></span> <span data-ttu-id="92b92-140">Weitere Informationen finden Sie unter [Grundlegendes zu MDX-Skripts &#40;Analysis Services&#41;](mdx/mdx-scripting-fundamentals-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="92b92-140">For more information, see [MDX Scripting Fundamentals &#40;Analysis Services&#41;](mdx/mdx-scripting-fundamentals-analysis-services.md).</span></span>  
  
 <span data-ttu-id="92b92-141">Wenn Sie berechnete Elemente und benutzerdefinierte Rollupformeln für Mitglieder eines Attributs verwenden, sollten Sie die Reihenfolge der Auswertung berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="92b92-141">If you use both calculated members and custom rollup formulas for members of an attribute, you should be aware of the order of evaluation.</span></span> <span data-ttu-id="92b92-142">Berechnete Elemente werden vor benutzerdefinierten Rollupformeln aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="92b92-142">Calculated members are resolved before custom rollup formulas are resolved.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92b92-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="92b92-143">See Also</span></span>  
 <span data-ttu-id="92b92-144">[Attribute und Attribut Hierarchien](../multidimensional-models-olap-logical-dimension-objects/attributes-and-attribute-hierarchies.md) </span><span class="sxs-lookup"><span data-stu-id="92b92-144">[Attributes and Attribute Hierarchies](../multidimensional-models-olap-logical-dimension-objects/attributes-and-attribute-hierarchies.md) </span></span>  
 [<span data-ttu-id="92b92-145">Festlegen benutzerdefinierter Elementformeln für Attribute in einer Dimension</span><span class="sxs-lookup"><span data-stu-id="92b92-145">Set Custom Member Formulas for Attributes in a Dimension</span></span>](bi-wizard-custom-member-formulas-for-attributes-in-a-dimension.md)  
  
  
