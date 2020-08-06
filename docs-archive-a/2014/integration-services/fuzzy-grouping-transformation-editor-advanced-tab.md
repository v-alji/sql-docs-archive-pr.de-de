---
title: Transformations-Editor für Fuzzygruppierung (Registerkarte Erweitert) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.fuzzygroupingtransformation.advanced.f1
helpviewer_keywords:
- Fuzzy Grouping Transformation Editor
ms.assetid: dd820d75-b8a7-4515-aea4-3553ba5b442e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2f5dd05eda56b4818914f659734eb3cdfb20c4d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615440"
---
# <a name="fuzzy-grouping-transformation-editor-advanced-tab"></a><span data-ttu-id="52027-102">Transformations-Editor für Fuzzygruppierung (Registerkarte Erweitert)</span><span class="sxs-lookup"><span data-stu-id="52027-102">Fuzzy Grouping Transformation Editor (Advanced Tab)</span></span>
  <span data-ttu-id="52027-103">Geben Sie mithilfe der Registerkarte **Erweitert** von **Transformations-Editor für Fuzzygruppierung** die Ein- und Ausgabespalten an, legen Sie Schwellenwerte für die Ähnlichkeit fest, und definieren Sie Begrenzungszeichen.</span><span class="sxs-lookup"><span data-stu-id="52027-103">Use the **Advanced** tab of the **Fuzzy Grouping Transformation Editor** dialog box to specify input and output columns, set similarity thresholds, and define delimiters.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="52027-104">Die `Exhaustive` -Eigenschaft und die-Eigenschaft der `MaxMemoryUsage` Transformation für Fuzzygruppierung sind im **Transformations-Editor für Fuzzygruppierung**nicht verfügbar, können jedoch mit dem- **Erweiterter Editor**festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="52027-104">The `Exhaustive` and the `MaxMemoryUsage` properties of the Fuzzy Grouping transformation are not available in the **Fuzzy Grouping Transformation Editor**, but can be set by using the **Advanced Editor**.</span></span> <span data-ttu-id="52027-105">Weitere Informationen zu diesen Eigenschaften finden Sie im Abschnitt Transformation für Fuzzgruppierung von [Transformation Custom Properties](data-flow/transformations/transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="52027-105">For more information on these properties, see the Fuzzy Grouping Transformation section of [Transformation Custom Properties](data-flow/transformations/transformation-custom-properties.md).</span></span>  
  
 <span data-ttu-id="52027-106">Weitere Informationen zur Transformation für Fuzzygruppierung finden Sie unter [Fuzzy Grouping Transformation](data-flow/transformations/fuzzy-grouping-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="52027-106">To learn more about the Fuzzy Grouping transformation, see [Fuzzy Grouping Transformation](data-flow/transformations/fuzzy-grouping-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="52027-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="52027-107">Options</span></span>  
 <span data-ttu-id="52027-108">**Name der Eingabeschlüsselspalte**</span><span class="sxs-lookup"><span data-stu-id="52027-108">**Input key column name**</span></span>  
 <span data-ttu-id="52027-109">Geben Sie den Namen einer Ausgabespalte an, die den eindeutigen Bezeichner für jede Eingabezeile enthält.</span><span class="sxs-lookup"><span data-stu-id="52027-109">Specify the name of an output column that contains the unique identifier for each input row.</span></span> <span data-ttu-id="52027-110">Die `_key_in`-Spalte enthält einen für jede Zeile eindeutigen Wert.</span><span class="sxs-lookup"><span data-stu-id="52027-110">The `_key_in` column has a value that uniquely identifies each row.</span></span>  
  
 <span data-ttu-id="52027-111">**Name der Ausgabeschlüsselspalte**</span><span class="sxs-lookup"><span data-stu-id="52027-111">**Output key column name**</span></span>  
 <span data-ttu-id="52027-112">Geben Sie den Namen einer Ausgabespalte an, die den eindeutigen Bezeichner für die kanonische Zeile einer Gruppe doppelter Zeilen enthält.</span><span class="sxs-lookup"><span data-stu-id="52027-112">Specify the name of an output column that contains the unique identifier for the canonical row of a group of duplicate rows.</span></span> <span data-ttu-id="52027-113">Die `_key_out`-Spalte entspricht dem `_key_in`-Wert der kanonischen Datenzeile.</span><span class="sxs-lookup"><span data-stu-id="52027-113">The `_key_out` column corresponds to the `_key_in` value of the canonical data row.</span></span>  
  
 <span data-ttu-id="52027-114">**Name der Ähnlichkeitsergebnisspalte**</span><span class="sxs-lookup"><span data-stu-id="52027-114">**Similarity score column name**</span></span>  
 <span data-ttu-id="52027-115">Geben Sie einen Namen für die Spalte an, die das Ähnlichkeitsergebnis enthält.</span><span class="sxs-lookup"><span data-stu-id="52027-115">Specify a name for the column that contains the similarity score.</span></span> <span data-ttu-id="52027-116">Das Ähnlichkeitsergebnis ist ein Wert zwischen 0 und 1, der die Ähnlichkeit zwischen der Eingabezeile und der kanonischen Zeile anzeigt.</span><span class="sxs-lookup"><span data-stu-id="52027-116">The similarity score is a value between 0 and 1 that indicates the similarity of the input row to the canonical row.</span></span> <span data-ttu-id="52027-117">Je näher das Ergebnis an 1 liegt, desto genauer stimmt die Zeile mit der kanonischen Zeile überein.</span><span class="sxs-lookup"><span data-stu-id="52027-117">The closer the score is to 1, the more closely the row matches the canonical row.</span></span>  
  
 <span data-ttu-id="52027-118">**Schwellenwert für Ähnlichkeit**</span><span class="sxs-lookup"><span data-stu-id="52027-118">**Similarity threshold**</span></span>  
 <span data-ttu-id="52027-119">Legen Sie den Schwellenwert für die Ähnlichkeit mithilfe des Schiebereglers fest.</span><span class="sxs-lookup"><span data-stu-id="52027-119">Set the similarity threshold by using the slider.</span></span> <span data-ttu-id="52027-120">Je näher der Schwellenwert an 1 kommt, desto mehr müssen die Zeilen einander ähneln, um als Duplikate angesehen zu werden.</span><span class="sxs-lookup"><span data-stu-id="52027-120">The closer the threshold is to 1, the more the rows must resemble each other to qualify as duplicates.</span></span> <span data-ttu-id="52027-121">Durch eine Erhöhung des Schwellenwertes kann die Geschwindigkeit beim Abgleich erhöht werden, weil als Kandidaten dann weniger Datensätze berücksichtigt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="52027-121">Increasing the threshold can improve the speed of matching because fewer candidate records have to be considered.</span></span>  
  
 <span data-ttu-id="52027-122">**Tokentrennzeichen**</span><span class="sxs-lookup"><span data-stu-id="52027-122">**Token delimiters**</span></span>  
 <span data-ttu-id="52027-123">Die Transformation bietet einen Standardsatz von Trennzeichen, um Daten mit Tokens zu versehen. Sie können durch Bearbeiten der Liste aber ggf. Trennzeichen hinzufügen oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="52027-123">The transformation provides a default set of delimiters for tokenizing data, but you can add or remove delimiters as needed by editing the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52027-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="52027-124">See Also</span></span>  
 <span data-ttu-id="52027-125">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="52027-125">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="52027-126">Identifizieren ähnlicher Datenzeilen mithilfe der Transformation für Fuzzygruppierung</span><span class="sxs-lookup"><span data-stu-id="52027-126">Identify Similar Data Rows by Using the Fuzzy Grouping Transformation</span></span>](data-flow/transformations/identify-similar-data-rows-by-using-the-fuzzy-grouping-transformation.md)  
  
  
