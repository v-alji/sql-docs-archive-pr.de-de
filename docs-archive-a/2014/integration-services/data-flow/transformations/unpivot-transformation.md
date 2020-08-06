---
title: Entpivotierungstransformation | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.unpivottrans.f1
helpviewer_keywords:
- Unpivot transformation
- more normalized data set [Integration Services]
- normalized data [Integration Services]
- datasets [Integration Services], normalized data
ms.assetid: f635c64b-a9c5-4f11-9c40-9cd9d5298c5d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e605dc4827a885b5dc65fbb680cce8a434b89fd5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621081"
---
# <a name="unpivot-transformation"></a><span data-ttu-id="b2059-102">Entpivotierungstransformation</span><span class="sxs-lookup"><span data-stu-id="b2059-102">Unpivot Transformation</span></span>
  <span data-ttu-id="b2059-103">Die Transformation für UNPIVOT ändert ein nicht normalisiertes Dataset in eine stärker normalisierte Version, indem Werte aus mehreren Spalten in einem einzelnen Datensatz in mehrere Datensätze mit den gleichen Werten in einer einzigen Spalte erweitert werden.</span><span class="sxs-lookup"><span data-stu-id="b2059-103">The Unpivot transformation makes an unnormalized dataset into a more normalized version by expanding values from multiple columns in a single record into multiple records with the same values in a single column.</span></span> <span data-ttu-id="b2059-104">Angenommen, ein Dataset, das Kundennamen auflistet, weist eine Zeile pro Kunden auf, wobei die Produkte und die gekaufte Menge in Spalten in der Zeile angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b2059-104">For example, a dataset that lists customer names has one row for each customer, with the products and the quantity purchased shown in columns in the row.</span></span> <span data-ttu-id="b2059-105">Nachdem die Entpivotierungstransformation das Dataset normalisiert hat, enthält das Dataset eine andere Zeile für jedes Produkt, das der Kunde gekauft hat.</span><span class="sxs-lookup"><span data-stu-id="b2059-105">After the Unpivot transformation normalizes the data set, the data set contains a different row for each product that the customer purchased.</span></span>  
  
 <span data-ttu-id="b2059-106">Im folgenden Diagramm wird ein Dataset vor dem Entpivotieren der Daten in der Product-Spalte dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b2059-106">The following diagram shows a data set before the data is unpivoted on the Product column.</span></span>  
  
 <span data-ttu-id="b2059-107">![Dataset nach dem Entpivotieren](../../media/mw-dts-18.gif "Dataset nach dem Entpivotieren")</span><span class="sxs-lookup"><span data-stu-id="b2059-107">![Dataset after it is unpivoted](../../media/mw-dts-18.gif "Dataset after it is unpivoted")</span></span>  
  
 <span data-ttu-id="b2059-108">Im folgenden Diagramm wird ein Dataset nach dem Entpivotieren in der Product-Spalte dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b2059-108">The following diagram shows a data set after it has been unpivoted on the Product column.</span></span>  
  
 <span data-ttu-id="b2059-109">![Dataset vor dem Entpivotieren](../../media/mw-dts-17.gif "Dataset vor dem Entpivotieren")</span><span class="sxs-lookup"><span data-stu-id="b2059-109">![Dataset before it is unpivoted](../../media/mw-dts-17.gif "Dataset before it is unpivoted")</span></span>  
  
 <span data-ttu-id="b2059-110">Unter einigen Umständen enthalten die Ergebnisse der Transformation für UNPIVOT möglicherweise Zeilen mit unerwarteten Werten.</span><span class="sxs-lookup"><span data-stu-id="b2059-110">Under some circumstances, the unpivot results may contain rows with unexpected values.</span></span> <span data-ttu-id="b2059-111">Wenn z.B. die im Diagramm gezeigten zu entpivotierenden Beispieldaten in allen Qty-Spalten für Fred NULL-Werte enthielten, würde die Ausgabe nur eine Zeile für Fred enthalten, nicht fünf.</span><span class="sxs-lookup"><span data-stu-id="b2059-111">For example, if the sample data to unpivot shown in the diagram had null values in all the Qty columns for Fred, then the output would include only one row for Fred, not five.</span></span> <span data-ttu-id="b2059-112">Die Qty-Spalte würde je nach dem Datentyp der Spalte entweder NULL oder 0 enthalten.</span><span class="sxs-lookup"><span data-stu-id="b2059-112">The Qty column would contain either null or zero, depending on the column data type.</span></span>  
  
## <a name="configuration-of-the-unpivot-transformation"></a><span data-ttu-id="b2059-113">Konfiguration der Transformation für UNPIVOT</span><span class="sxs-lookup"><span data-stu-id="b2059-113">Configuration of the Unpivot Transformation</span></span>  
 <span data-ttu-id="b2059-114">Die Transformation für UNPIVOT schließt die benutzerdefinierte Eigenschaft `PivotKeyValue` ein.</span><span class="sxs-lookup"><span data-stu-id="b2059-114">The Unpivot transformation includes the `PivotKeyValue` custom property.</span></span> <span data-ttu-id="b2059-115">Diese Eigenschaft kann beim Laden des Pakets mithilfe eines Eigenschaftsausdrucks aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="b2059-115">This property can be updated by a property expression when the package is loaded.</span></span> <span data-ttu-id="b2059-116">Weitere Informationen finden Sie unter [Integration Services-Ausdrücke &#40;SSIS&#41;](../../expressions/integration-services-ssis-expressions.md), [Verwenden von Eigenschaftsausdrücken in Paketen](../../expressions/use-property-expressions-in-packages.md) und [Benutzerdefinierte Eigenschaften von Transformationen](transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="b2059-116">For more information, see [Integration Services &#40;SSIS&#41; Expressions](../../expressions/integration-services-ssis-expressions.md), [Use Property Expressions in Packages](../../expressions/use-property-expressions-in-packages.md), and [Transformation Custom Properties](transformation-custom-properties.md).</span></span>  
  
 <span data-ttu-id="b2059-117">Diese Transformation weist je eine Eingabe und eine Ausgabe auf.</span><span class="sxs-lookup"><span data-stu-id="b2059-117">This transformation has one input and one output.</span></span> <span data-ttu-id="b2059-118">Es ist keine Fehlerausgabe vorhanden.</span><span class="sxs-lookup"><span data-stu-id="b2059-118">It has no error output.</span></span>  
  
 <span data-ttu-id="b2059-119">Sie können Eigenschaften mit dem [!INCLUDE[ssIS](../../../includes/ssis-md.md)] -Designer oder programmgesteuert festlegen.</span><span class="sxs-lookup"><span data-stu-id="b2059-119">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="b2059-120">Klicken Sie auf eines der folgenden Themen, um weitere Informationen zu den Eigenschaften zu erhalten, die Sie im Dialogfeld **Editor zum Entpivotieren von Transformationen** festlegen können:</span><span class="sxs-lookup"><span data-stu-id="b2059-120">For more information about the properties that you can set in the **Unpivot Transformation Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="b2059-121">Editor zum Entpivotieren von Transformationen</span><span class="sxs-lookup"><span data-stu-id="b2059-121">Unpivot Transformation Editor</span></span>](../../unpivot-transformation-editor.md)  
  
 <span data-ttu-id="b2059-122">Klicken Sie auf eines der folgenden Themen, um weitere Informationen zu den Eigenschaften zu erhalten, die Sie im Dialogfeld **Erweiterter Editor** oder programmgesteuert festlegen können:</span><span class="sxs-lookup"><span data-stu-id="b2059-122">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="b2059-123">Common Properties</span><span class="sxs-lookup"><span data-stu-id="b2059-123">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="b2059-124">Benutzerdefinierte Eigenschaften von Transformationen</span><span class="sxs-lookup"><span data-stu-id="b2059-124">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
 <span data-ttu-id="b2059-125">Informationen zum Festlegen der Eigenschaften finden Sie unter [Festlegen der Eigenschaften einer Datenflusskomponente](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="b2059-125">For more information about how to set the properties, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
  
