---
title: Transformations-Editor für Fuzzysuche (Registerkarte Erweitert) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.fuzzylookuptransformation.advanced.f1
helpviewer_keywords:
- Fuzzy Lookup Transformation Editor
ms.assetid: 0a2919be-2ea7-4c06-82b8-0ffad5f0dd83
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 68f53eb2735dc07656fc8ff2b81c3259caa4847b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696990"
---
# <a name="fuzzy-lookup-transformation-editor-advanced-tab"></a><span data-ttu-id="6f99f-102">Transformations-Editor für Fuzzysuche (Registerkarte Erweitert)</span><span class="sxs-lookup"><span data-stu-id="6f99f-102">Fuzzy Lookup Transformation Editor (Advanced Tab)</span></span>
  <span data-ttu-id="6f99f-103">Auf der Registerkarte **Erweitert** des Dialogfelds **Transformations-Editor für Fuzzysuche** können Sie die Parameter für die Fuzzysuche festlegen.</span><span class="sxs-lookup"><span data-stu-id="6f99f-103">Use the **Advanced** tab of the **Fuzzy Lookup Transformation Editor** dialog box to set parameters for the fuzzy lookup.</span></span>  
  
 <span data-ttu-id="6f99f-104">Weitere Informationen zur Transformation für Fuzzysuche finden Sie unter [Fuzzy Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="6f99f-104">To learn more about the Fuzzy Lookup transformation, see [Fuzzy Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="6f99f-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="6f99f-105">Options</span></span>  
 <span data-ttu-id="6f99f-106">**Maximale Anzahl von Übereinstimmungen, die pro Suche ausgegeben werden**</span><span class="sxs-lookup"><span data-stu-id="6f99f-106">**Maximum number of matches to output per lookup**</span></span>  
 <span data-ttu-id="6f99f-107">Geben Sie die maximale Anzahl der Übereinstimmungen an, die pro Eingabezeile von der Transformation zurückgegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="6f99f-107">Specify the maximum number of matches the transformation can return for each input row.</span></span> <span data-ttu-id="6f99f-108">Der Standardwert lautet **1**.</span><span class="sxs-lookup"><span data-stu-id="6f99f-108">The default is **1**.</span></span>  
  
 <span data-ttu-id="6f99f-109">**Schwellenwert für Ähnlichkeit**</span><span class="sxs-lookup"><span data-stu-id="6f99f-109">**Similarity threshold**</span></span>  
 <span data-ttu-id="6f99f-110">Legen Sie mithilfe des Schiebereglers den Schwellenwert für Ähnlichkeit auf Komponentenebene fest.</span><span class="sxs-lookup"><span data-stu-id="6f99f-110">Set the similarity threshold at the component level by using the slider.</span></span> <span data-ttu-id="6f99f-111">Je näher der Wert an 1 liegt, desto stärker muss die Ähnlichkeit zwischen Suchwert und Quellwert sein, um als Übereinstimmung zu gelten.</span><span class="sxs-lookup"><span data-stu-id="6f99f-111">The closer the value is to 1, the closer the resemblance of the lookup value to the source value must be to qualify as a match.</span></span> <span data-ttu-id="6f99f-112">Durch eine Erhöhung des Schwellenwertes kann die Geschwindigkeit beim Abgleich erhöht werden, weil als Kandidaten dann weniger Datensätze berücksichtigt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="6f99f-112">Increasing the threshold can improve the speed of matching since fewer candidate records need to be considered.</span></span>  
  
 <span data-ttu-id="6f99f-113">**Tokentrennzeichen**</span><span class="sxs-lookup"><span data-stu-id="6f99f-113">**Token delimiters**</span></span>  
 <span data-ttu-id="6f99f-114">Geben Sie die Trennzeichen an, die von der Transformation verwendet werden, um Spaltenwerte mit Token zu versehen.</span><span class="sxs-lookup"><span data-stu-id="6f99f-114">Specify the delimiters that the transformation uses to tokenize column values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f99f-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6f99f-115">See Also</span></span>  
 <span data-ttu-id="6f99f-116">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="6f99f-116">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="6f99f-117">[Transformations-Editor für Fuzzysuche &#40;Registerkarte Verweis Tabelle&#41;](../../2014/integration-services/fuzzy-lookup-transformation-editor-reference-table-tab.md) </span><span class="sxs-lookup"><span data-stu-id="6f99f-117">[Fuzzy Lookup Transformation Editor &#40;Reference Table Tab&#41;](../../2014/integration-services/fuzzy-lookup-transformation-editor-reference-table-tab.md) </span></span>  
 [<span data-ttu-id="6f99f-118">Transformations-Editor für Fuzzysuche &#40;Registerkarte Spalten&#41;</span><span class="sxs-lookup"><span data-stu-id="6f99f-118">Fuzzy Lookup Transformation Editor &#40;Columns Tab&#41;</span></span>](../../2014/integration-services/fuzzy-lookup-transformation-editor-columns-tab.md)  
  
  
