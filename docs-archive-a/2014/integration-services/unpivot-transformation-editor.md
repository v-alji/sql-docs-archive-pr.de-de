---
title: Transformations-Editor für UNPIVOT | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.unpivottransformation.f1
helpviewer_keywords:
- Unpivot Transformation Editor
ms.assetid: 72a36ef0-4070-4f6c-9c74-0720109617dd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6c3b93370b34440b73b4c9c78dc7d19fa4095275
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609942"
---
# <a name="unpivot-transformation-editor"></a><span data-ttu-id="33f33-102">Editor zum Entpivotieren von Transformationen</span><span class="sxs-lookup"><span data-stu-id="33f33-102">Unpivot Transformation Editor</span></span>
  <span data-ttu-id="33f33-103">Mithilfe des Dialogfelds **Transformations-Editor für UNPIVOT** können Sie die in Zeilen neu anzuordnenden Spalten, die Datenspalte sowie die Ausgabespalte für den neuen pivotierten Wert angeben.</span><span class="sxs-lookup"><span data-stu-id="33f33-103">Use the **Unpivot Transformation Editor** dialog box to select the columns to pivot into rows, and to specify the data column and the new pivot value output column.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="33f33-104">In diesem Thema wird die Verwendung der Optionen auf der Grundlage des in [Entpivotierungstransformation](data-flow/transformations/unpivot-transformation.md) beschriebenen Entpivotierungsszenarios veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="33f33-104">This topic relies on the Unpivot scenario described in [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md) to illustrate the use of the options.</span></span>  
  
 <span data-ttu-id="33f33-105">Weitere Informationen zur Entpivotierungstransformation finden Sie unter [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="33f33-105">To learn more about the Unpivot transformation, see [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="33f33-106">Tastatur</span><span class="sxs-lookup"><span data-stu-id="33f33-106">Options</span></span>  
 <span data-ttu-id="33f33-107">**Verfügbare Eingabespalten**</span><span class="sxs-lookup"><span data-stu-id="33f33-107">**Available Input Columns**</span></span>  
 <span data-ttu-id="33f33-108">Geben Sie mithilfe der Kontrollkästchen die Spalten an, die in Zeilen neu angeordnet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="33f33-108">Using the check boxes, specify the columns to pivot into rows.</span></span>  
  
 <span data-ttu-id="33f33-109">**Name**</span><span class="sxs-lookup"><span data-stu-id="33f33-109">**Name**</span></span>  
 <span data-ttu-id="33f33-110">Zeigt den Namen der verfügbaren Eingabespalte an.</span><span class="sxs-lookup"><span data-stu-id="33f33-110">View the name of the available input column.</span></span>  
  
 <span data-ttu-id="33f33-111">**Pass-Through**</span><span class="sxs-lookup"><span data-stu-id="33f33-111">**Pass Through**</span></span>  
 <span data-ttu-id="33f33-112">Gibt an, ob die Spalte in die entpivotierte Ausgabe eingeschlossen werden soll.</span><span class="sxs-lookup"><span data-stu-id="33f33-112">Indicate whether to include the column in the unpivoted output.</span></span>  
  
 <span data-ttu-id="33f33-113">**Eingabespalte**</span><span class="sxs-lookup"><span data-stu-id="33f33-113">**Input Column**</span></span>  
 <span data-ttu-id="33f33-114">Wählen Sie für jede Zeile eine Spalte aus der Liste der verfügbaren Eingabespalten aus.</span><span class="sxs-lookup"><span data-stu-id="33f33-114">Select from the list of available input columns for each row.</span></span> <span data-ttu-id="33f33-115">Ihre Auswahl wird entsprechend in der Auswahl der Kontrollkästchen in der **Verfügbare Eingabespalten** -Tabelle deutlich.</span><span class="sxs-lookup"><span data-stu-id="33f33-115">Your selections are reflected in the check box selections in the **Available Input Columns** table.</span></span>  
  
 <span data-ttu-id="33f33-116">Im Entpivotierungsszenario, das in [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md)beschrieben wird, sind als Eingabespalten die Spalten **Ham**, **Soda**, **Milk**, **Beer**und **Chips** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="33f33-116">In the Unpivot scenario described in [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md), the Input Columns are the **Ham**, **Soda**, **Milk**, **Beer**, and **Chips** columns.</span></span>  
  
 <span data-ttu-id="33f33-117">**Zielspalte**</span><span class="sxs-lookup"><span data-stu-id="33f33-117">**Destination Column**</span></span>  
 <span data-ttu-id="33f33-118">Geben Sie einen Namen für die Datenspalte an.</span><span class="sxs-lookup"><span data-stu-id="33f33-118">Provide a name for the data column.</span></span>  
  
 <span data-ttu-id="33f33-119">Im Entpivotierungsszenario, das in [Entpivotierungstransformation](data-flow/transformations/unpivot-transformation.md)beschrieben wird, ist die Zielspalte die Mengenspalte (**Qty**).</span><span class="sxs-lookup"><span data-stu-id="33f33-119">In the Unpivot scenario described in [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md), the Destination Column is the quantity (**Qty**) column.</span></span>  
  
 <span data-ttu-id="33f33-120">**Pivotschlüsselwert**</span><span class="sxs-lookup"><span data-stu-id="33f33-120">**Pivot Key Value**</span></span>  
 <span data-ttu-id="33f33-121">Geben Sie einen Namen für den Pivotwert an.</span><span class="sxs-lookup"><span data-stu-id="33f33-121">Provide a name for the pivot value.</span></span> <span data-ttu-id="33f33-122">Standardmäßig wird der Name der Eingabespalte verwendet. Sie können jedoch auch einen beschreibenden Namen angeben, sofern dieser eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="33f33-122">The default is the name of the input column; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="33f33-123">Der Wert dieser Eigenschaft kann mithilfe eines Eigenschaftsausdrucks angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="33f33-123">The value of this property can be specified by using a property expression.</span></span>  
  
 <span data-ttu-id="33f33-124">In dem in [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md)beschriebenen Entpivotierungsszenario werden die pivotierten Werte in der neuen, durch die Option **Name der Pivotschlüsselwert-Spalte** angegebenen Product-Spalte als die Textwerte **Ham**, **Soda**, **Milk**, **Beer**und **Chips**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="33f33-124">In the Unpivot scenario described in [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md), the Pivot Values will appear in the new Product column designated by the **Pivot Key Value Column Name** option, as the text values **Ham**, **Soda**, **Milk**, **Beer**, and **Chips**.</span></span>  
  
 <span data-ttu-id="33f33-125">**Name der Pivotschlüsselwert-Spalte**</span><span class="sxs-lookup"><span data-stu-id="33f33-125">**Pivot Key Value Column Name**</span></span>  
 <span data-ttu-id="33f33-126">Geben Sie einen Namen für die Pivotwertspalte an.</span><span class="sxs-lookup"><span data-stu-id="33f33-126">Provide a name for the pivot value column.</span></span> <span data-ttu-id="33f33-127">Standardwert ist "Pivotschlüsselwert"; Sie können jedoch einen eindeutigen, beschreibenden Namen auswählen.</span><span class="sxs-lookup"><span data-stu-id="33f33-127">The default is "Pivot Key Value"; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="33f33-128">In dem in [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md)beschriebenen Entpivotierungsszenario lautete der Name der Pivotschlüsselwert-Spalte **Product** und bezieht sich auf die neue **Product** -Spalte, in die die Spalten **Ham**, **Soda**, **Milk**, **Beer**und **Chips** entpivotiert werden.</span><span class="sxs-lookup"><span data-stu-id="33f33-128">In the Unpivot scenario described in [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md), the Pivot Key Value Column Name is **Product** and designates the new **Product** column into which the **Ham**, **Soda**, **Milk**, **Beer**, and **Chips** columns are unpivoted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33f33-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="33f33-129">See Also</span></span>  
 <span data-ttu-id="33f33-130">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="33f33-130">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="33f33-131">Transformation für Pivot</span><span class="sxs-lookup"><span data-stu-id="33f33-131">Pivot Transformation</span></span>](data-flow/transformations/pivot-transformation.md)  
  
  
