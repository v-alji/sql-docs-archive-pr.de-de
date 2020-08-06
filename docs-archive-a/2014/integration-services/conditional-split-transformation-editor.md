---
title: Transformations-Editor für bedingtes Teilen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.conditionalsplittransformation.f1
helpviewer_keywords:
- Conditional Split Transformation Editor
ms.assetid: c30e1633-537a-4837-9991-6203c6f2a21e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 386a93eb7c3058c7c3e98f2b652199d115d841f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609373"
---
# <a name="conditional-split-transformation-editor"></a><span data-ttu-id="5cd89-102">Transformations-Editor für bedingtes Teilen</span><span class="sxs-lookup"><span data-stu-id="5cd89-102">Conditional Split Transformation Editor</span></span>
  <span data-ttu-id="5cd89-103">Mithilfe des Dialogfelds **Transformations-Editor für bedingtes Teilen** können Sie Ausdrücke erstellen, die Reihenfolge festlegen, in der Ausdrücke ausgewertet werden, und die Ausgaben des bedingten Teilens benennen.</span><span class="sxs-lookup"><span data-stu-id="5cd89-103">Use the **Conditional Split Transformation Editor** dialog box to create expressions, set the order in which expressions are evaluated, and name the outputs of a conditional split.</span></span> <span data-ttu-id="5cd89-104">Dieses Dialogfeld schließt Funktionen und Operatoren für mathematische Berechnungen, Zeichenfolgen und Datum/Uhrzeit ein, die Sie für das Erstellen von Ausdrücken verwenden können.</span><span class="sxs-lookup"><span data-stu-id="5cd89-104">This dialog box includes mathematical, string, and date/time functions and operators that you can use to build expressions.</span></span> <span data-ttu-id="5cd89-105">Die erste Bedingung, bei der die Auswertung den Wert TRUE ergibt, bestimmt die Ausgabe, an die eine Zeile geleitet wird.</span><span class="sxs-lookup"><span data-stu-id="5cd89-105">The first condition that evaluates as true determines the output to which a row is directed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5cd89-106">Die Transformation für bedingtes Teilen leitet jede Eingabezeile an nur eine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="5cd89-106">The Conditional Split transformation directs each input row to one output only.</span></span> <span data-ttu-id="5cd89-107">Wenn Sie mehrere Bedingungen eingeben, wird jede Zeile durch die Transformation an die erste Ausgabe gesendet, bei der die Bedingung erfüllt ist (TRUE). Dadurch bleiben alle folgenden Bedingungen für diese Zeile unberücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="5cd89-107">If you enter multiple conditions, the transformation sends each row to the first output for which the condition is true and disregards subsequent conditions for that row.</span></span> <span data-ttu-id="5cd89-108">Wenn mehrere Bedingungen aufeinander folgend ausgewertet werden sollen, dann müssen Sie mehrere Transformationen für bedingtes Teilen im Datenfluss miteinander verketten.</span><span class="sxs-lookup"><span data-stu-id="5cd89-108">If you need to evaluate several conditions successively, you may need to concatenate multiple Conditional Split transformations in the data flow.</span></span>  
  
 <span data-ttu-id="5cd89-109">Weitere Informationen zur Transformation für bedingtes Teilen finden Sie unter [Transformation für bedingtes Teilen](data-flow/transformations/conditional-split-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="5cd89-109">To learn more about the Conditional Split transformation, see [Conditional Split Transformation](data-flow/transformations/conditional-split-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="5cd89-110">Tastatur</span><span class="sxs-lookup"><span data-stu-id="5cd89-110">Options</span></span>  
 <span data-ttu-id="5cd89-111">**Order**</span><span class="sxs-lookup"><span data-stu-id="5cd89-111">**Order**</span></span>  
 <span data-ttu-id="5cd89-112">Wählen Sie eine Zeile aus, und verwenden Sie die Pfeiltasten auf der rechten Seite, um die Reihenfolge zu ändern, in der die Ausdrücke ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="5cd89-112">Select a row and use the arrow keys at right to change the order in which to evaluate expressions.</span></span>  
  
 <span data-ttu-id="5cd89-113">**Ausgabe Name**</span><span class="sxs-lookup"><span data-stu-id="5cd89-113">**Output Name**</span></span>  
 <span data-ttu-id="5cd89-114">Geben Sie einen Ausgabenamen an.</span><span class="sxs-lookup"><span data-stu-id="5cd89-114">Provide an output name.</span></span> <span data-ttu-id="5cd89-115">Standardwert ist eine nummerierte Liste aus Fällen; Sie können jedoch einen eindeutigen, beschreibenden Namen auswählen.</span><span class="sxs-lookup"><span data-stu-id="5cd89-115">The default is a numbered list of cases; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="5cd89-116">**Condition**</span><span class="sxs-lookup"><span data-stu-id="5cd89-116">**Condition**</span></span>  
 <span data-ttu-id="5cd89-117">Geben Sie einen Ausdruck ein, oder erstellen Sie einen, indem Sie aus der Liste der verfügbaren Spalten, Variablen, Funktionen und Operatoren die entsprechenden Teile ziehen.</span><span class="sxs-lookup"><span data-stu-id="5cd89-117">Type an expression or build one by dragging from the list of available columns, variables, functions, and operators.</span></span>  
  
 <span data-ttu-id="5cd89-118">Der Wert dieser Eigenschaft kann mithilfe eines Eigenschaftsausdrucks angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="5cd89-118">The value of this property can be specified by using a property expression.</span></span>  
  
 <span data-ttu-id="5cd89-119">**Verwandte Themen:**  [Integration Services-Ausdrücke &#40;SSIS&#41;](expressions/integration-services-ssis-expressions.md), [Operatoren &#40;SSIS-Ausdruck&#41;](expressions/operators-ssis-expression.md) und [Funktionen &#40;SSIS-Ausdruck&#41;](expressions/functions-ssis-expression.md)</span><span class="sxs-lookup"><span data-stu-id="5cd89-119">**Related topics:**  [Integration Services &#40;SSIS&#41; Expressions](expressions/integration-services-ssis-expressions.md), [Operators &#40;SSIS Expression&#41;](expressions/operators-ssis-expression.md), and [Functions &#40;SSIS Expression&#41;](expressions/functions-ssis-expression.md)</span></span>  
  
 <span data-ttu-id="5cd89-120">**Standardausgabename**</span><span class="sxs-lookup"><span data-stu-id="5cd89-120">**Default output name**</span></span>  
 <span data-ttu-id="5cd89-121">Geben Sie einen Namen für die Standardausgabe ein, oder verwenden Sie den Standardnamen.</span><span class="sxs-lookup"><span data-stu-id="5cd89-121">Type a name for the default output, or use the default.</span></span>  
  
 <span data-ttu-id="5cd89-122">**Fehlerausgabe konfigurieren**</span><span class="sxs-lookup"><span data-stu-id="5cd89-122">**Configure error output**</span></span>  
 <span data-ttu-id="5cd89-123">Geben Sie mithilfe des Dialogfelds [Fehlerausgabe konfigurieren](../../2014/integration-services/configure-error-output.md) an, wie Fehler behandelt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="5cd89-123">Specify how to handle errors by using the [Configure Error Output](../../2014/integration-services/configure-error-output.md) dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cd89-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5cd89-124">See Also</span></span>  
 <span data-ttu-id="5cd89-125">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="5cd89-125">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="5cd89-126">Teilen eines Datasets mithilfe der Transformation für bedingtes Teilen</span><span class="sxs-lookup"><span data-stu-id="5cd89-126">Split a Dataset by Using the Conditional Split Transformation</span></span>](data-flow/transformations/split-a-dataset-by-using-the-conditional-split-transformation.md)  
  
  
