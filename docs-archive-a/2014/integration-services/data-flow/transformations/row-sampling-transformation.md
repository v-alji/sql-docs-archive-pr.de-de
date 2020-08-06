---
title: Transformation für Zeilenstichproben | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.rowsamplingtrans.f1
helpviewer_keywords:
- sampling seeds [Integration Services]
- random seeds
- random sampling
- sample data sets [Integration Services]
- Row Sampling transformation
- packages [Integration Services], samples
- datasets [Integration Services], sample
ms.assetid: b6caafd3-30b2-4368-82af-a44611d4cd39
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c56f07d9fafa03752ef8c6572a13c6ad7c02a8c8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727097"
---
# <a name="row-sampling-transformation"></a><span data-ttu-id="3f9e4-102">Transformation für Zeilenstichproben</span><span class="sxs-lookup"><span data-stu-id="3f9e4-102">Row Sampling Transformation</span></span>
  <span data-ttu-id="3f9e4-103">Mit der Transformation für Zeilenstichproben wird eine nach dem Zufallsprinzip ausgewählte Teilmenge eines Eingabedatasets abgerufen.</span><span class="sxs-lookup"><span data-stu-id="3f9e4-103">The Row Sampling transformation is used to obtain a randomly selected subset of an input dataset.</span></span> <span data-ttu-id="3f9e4-104">Sie können die genaue Größe der Ausgabestichprobe sowie einen Ausgangswert für den Zufallszahlen-Generator angeben.</span><span class="sxs-lookup"><span data-stu-id="3f9e4-104">You can specify the exact size of the output sample, and specify a seed for the random number generator.</span></span>  
  
 <span data-ttu-id="3f9e4-105">Für zufällige Stichproben gibt es viele Anwendungsmöglichkeiten.</span><span class="sxs-lookup"><span data-stu-id="3f9e4-105">There are many applications for random sampling.</span></span> <span data-ttu-id="3f9e4-106">Beispielsweise könnte ein Unternehmen, das 50 Mitarbeiter nach dem Zufallsprinzip für einen Lotteriepreis auswählen möchte, die Transformation für Zeilenstichproben für die Mitarbeiterdatenbank ausführen und die genaue Anzahl von Gewinnern generieren.</span><span class="sxs-lookup"><span data-stu-id="3f9e4-106">For example, a company that wanted to randomly select 50 employees to receive prizes in a lottery could use the Row Sampling transformation on the employee database to generate the exact number of winners.</span></span>  
  
 <span data-ttu-id="3f9e4-107">Die Transformation für Zeilenstichproben ist außerdem bei der Paketentwicklung hilfreich, um ein kleines, aber repräsentatives Dataset zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3f9e4-107">The Row Sampling transformation is also useful during package development for creating a small but representative dataset.</span></span> <span data-ttu-id="3f9e4-108">Sie können die Paketausführung und die Datentransformation mit äußerst repräsentativen Daten, aber schneller testen, weil anstelle des vollständigen Datasets eine zufällige Stichprobe verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3f9e4-108">You can test package execution and data transformation with richly representative data, but more quickly because a random sample is used instead of the full dataset.</span></span> <span data-ttu-id="3f9e4-109">Das vom Testpaket verwendete Stichprobendataset besitzt immer die gleiche Größe. Deshalb können mit der Stichprobenteilmenge auch Leistungsprobleme beim Paket einfacher identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="3f9e4-109">Because the sample dataset used by the test package is always the same size, using the sample subset also makes it easier to identify performance problems in the package.</span></span>  
  
 <span data-ttu-id="3f9e4-110">Diese Transformation ist mit der Transformation für Prozentwert-Stichproben vergleichbar, die ein Stichprobendataset durch Auswählen eines Prozentwerts der Eingabezeilen erstellt.</span><span class="sxs-lookup"><span data-stu-id="3f9e4-110">This transformation is similar to the Percentage Sampling transformation, which creates a sample dataset by selecting a percentage of the input rows.</span></span> <span data-ttu-id="3f9e4-111">Siehe [Percentage Sampling Transformation](percentage-sampling-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="3f9e4-111">See [Percentage Sampling Transformation](percentage-sampling-transformation.md).</span></span>  
  
## <a name="configuring-the-row-sampling-transformation"></a><span data-ttu-id="3f9e4-112">Konfigurieren der Transformation für Zeilenstichproben</span><span class="sxs-lookup"><span data-stu-id="3f9e4-112">Configuring the Row Sampling Transformation</span></span>  
 <span data-ttu-id="3f9e4-113">Die Transformation für Zeilenstichproben erstellt ein Stichprobendataset durch Auswählen einer angegebene Anzahl von Transformationseingabezeilen.</span><span class="sxs-lookup"><span data-stu-id="3f9e4-113">The Row Sampling transformation creates a sample dataset by selecting a specified number of the transformation input rows.</span></span> <span data-ttu-id="3f9e4-114">Da die Auswahl von Zeilen aus der Transformationseingabe nach dem Zufallsprinzip erfolgt, ist die Stichprobe für die Eingabe repräsentativ.</span><span class="sxs-lookup"><span data-stu-id="3f9e4-114">Because the selection of rows from the transformation input is random, the resultant sample is representative of the input.</span></span> <span data-ttu-id="3f9e4-115">Darüber hinaus können Sie den Ausgangswert angeben, der vom Zufallszahlen-Generator verwendet wird, um die Auswahl der Zeilen durch die Transformation zu beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="3f9e4-115">You can also specify the seed that is used by the random number generator, to affect how the transformation selects rows.</span></span>  
  
 <span data-ttu-id="3f9e4-116">Wenn der gleiche zufällige Ausgangswert in derselben Transformationseingabe verwendet wird, wird immer dieselbe Stichprobenausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="3f9e4-116">Using the same random seed on the same transformation input always creates the same sample output.</span></span> <span data-ttu-id="3f9e4-117">Wenn kein Ausgangswert angegeben ist, erstellt die Transformation die Zufallszahl mithilfe der Taktanzahl des Betriebssystems.</span><span class="sxs-lookup"><span data-stu-id="3f9e4-117">If no seed is specified, the transformation uses the tick count of the operating system to create the random number.</span></span> <span data-ttu-id="3f9e4-118">Deshalb können Sie beim Testen denselben Ausgangswert verwenden, um die Transformationsergebnisse beim Entwickeln und Testen des Pakets zu überprüfen. Anschließend verwenden Sie dann einen zufälligen Ausgangswert, wenn das Paket auf den Produktionsserver verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="3f9e4-118">Therefore, you could use the same seed during testing, to verify the transformation results during the development and testing of the package, and then change to a random seed when the package is moved into production.</span></span>  
  
 <span data-ttu-id="3f9e4-119">Die Transformation für Zeilenstichproben schließt die benutzerdefinierte Eigenschaft `SamplingValue` ein.</span><span class="sxs-lookup"><span data-stu-id="3f9e4-119">The Row Sampling transformation includes the `SamplingValue` custom property.</span></span> <span data-ttu-id="3f9e4-120">Diese Eigenschaft kann beim Laden des Pakets mithilfe eines Eigenschaftsausdrucks aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="3f9e4-120">This property can be updated by a property expression when the package is loaded.</span></span> <span data-ttu-id="3f9e4-121">Weitere Informationen finden Sie unter [Integration Services-Ausdrücke &#40;SSIS&#41;](../../expressions/integration-services-ssis-expressions.md), [Verwenden von Eigenschaftsausdrücken in Paketen](../../expressions/use-property-expressions-in-packages.md) und [Benutzerdefinierte Eigenschaften von Transformationen](transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="3f9e4-121">For more information, see [Integration Services &#40;SSIS&#41; Expressions](../../expressions/integration-services-ssis-expressions.md), [Use Property Expressions in Packages](../../expressions/use-property-expressions-in-packages.md), and [Transformation Custom Properties](transformation-custom-properties.md).</span></span>  
  
 <span data-ttu-id="3f9e4-122">Diese Transformation weist eine Eingabe und zwei Ausgaben auf.</span><span class="sxs-lookup"><span data-stu-id="3f9e4-122">This transformation has one input and two outputs.</span></span> <span data-ttu-id="3f9e4-123">Es ist keine Fehlerausgabe vorhanden.</span><span class="sxs-lookup"><span data-stu-id="3f9e4-123">It has no error output.</span></span>  
  
 <span data-ttu-id="3f9e4-124">Sie können Eigenschaften mit dem [!INCLUDE[ssIS](../../../includes/ssis-md.md)] -Designer oder programmgesteuert festlegen.</span><span class="sxs-lookup"><span data-stu-id="3f9e4-124">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="3f9e4-125">Weitere Informationen zu den Eigenschaften, die Sie im Dialogfeld **Transformations-Editor für Zeilenstichprobe** festlegen können, finden Sie unter [Transformations-Editor für Zeilenstichprobe &#40;Seite „Sampling“&#41;](../../row-sampling-transformation-editor-sampling-page.md).</span><span class="sxs-lookup"><span data-stu-id="3f9e4-125">For more information about the properties that you can set in the **Row Sampling Transformation Editor** dialog box, see [Row Sampling Transformation Editor &#40;Sampling Page&#41;](../../row-sampling-transformation-editor-sampling-page.md).</span></span>  
  
 <span data-ttu-id="3f9e4-126">Das Dialogfeld **Erweiterter Editor** enthält die Eigenschaften, die programmgesteuert festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="3f9e4-126">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="3f9e4-127">Klicken Sie auf eines der folgenden Themen, um weitere Informationen zu den Eigenschaften zu erhalten, die Sie im Dialogfeld **Erweiterter Editor** oder programmgesteuert festlegen können:</span><span class="sxs-lookup"><span data-stu-id="3f9e4-127">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="3f9e4-128">Common Properties</span><span class="sxs-lookup"><span data-stu-id="3f9e4-128">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="3f9e4-129">Benutzerdefinierte Eigenschaften von Transformationen</span><span class="sxs-lookup"><span data-stu-id="3f9e4-129">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="3f9e4-130">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="3f9e4-130">Related Tasks</span></span>  
 [<span data-ttu-id="3f9e4-131">Festlegen der Eigenschaften einer Datenflusskomponente</span><span class="sxs-lookup"><span data-stu-id="3f9e4-131">Set the Properties of a Data Flow Component</span></span>](../set-the-properties-of-a-data-flow-component.md)  
  
  
