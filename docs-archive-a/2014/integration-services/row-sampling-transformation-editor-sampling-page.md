---
title: Transformations-Editor für Zeilen Stichprobe (Seite Stichprobenentnahme) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL12.DTS.DESIGNER.ROWSAMPLINGTRANSFORMATION.COLUMNS.F1
- sql12.dts.designer.rowsamplingtransformation.f1
helpviewer_keywords:
- Row Sampling Transformation Editor
ms.assetid: 544c7709-6de0-4c08-bda3-759985be9a05
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 26d0c0439e548172225f02220d8f6814a1168ea9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696941"
---
# <a name="row-sampling-transformation-editor-sampling-page"></a><span data-ttu-id="9398b-102">Transformations-Editor für Zeilenstichprobe (Seite Stichprobenentnahme)</span><span class="sxs-lookup"><span data-stu-id="9398b-102">Row Sampling Transformation Editor (Sampling Page)</span></span>
  <span data-ttu-id="9398b-103">Im Dialogfeld **Transformations-Editor für Zeilenstichprobe** können Sie einen Teil der Eingabe mithilfe der angegebenen Anzahl von Zeilen als Stichprobe entnehmen.</span><span class="sxs-lookup"><span data-stu-id="9398b-103">Use the **Row Sampling Transformation Editor** dialog box to split a portion of an input into a sample using a specified number of rows.</span></span> <span data-ttu-id="9398b-104">Durch diese Transformation wird die Eingabe in zwei getrennte Ausgaben geteilt.</span><span class="sxs-lookup"><span data-stu-id="9398b-104">This transformation divides the input into two separate outputs.</span></span>  
  
 <span data-ttu-id="9398b-105">Weitere Informationen zur Transformation für Zeilenstichproben finden Sie unter [Row Sampling Transformation](data-flow/transformations/row-sampling-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="9398b-105">To learn more about the Row Sampling transformation, see [Row Sampling Transformation](data-flow/transformations/row-sampling-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="9398b-106">Tastatur</span><span class="sxs-lookup"><span data-stu-id="9398b-106">Options</span></span>  
 <span data-ttu-id="9398b-107">**Anzahl von Zeilen**</span><span class="sxs-lookup"><span data-stu-id="9398b-107">**Number of rows**</span></span>  
 <span data-ttu-id="9398b-108">Geben Sie die Anzahl der Zeilen in der Eingabe an, die als Stichprobe verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9398b-108">Specify the number of rows from the input to use as a sample.</span></span>  
  
 <span data-ttu-id="9398b-109">Der Wert dieser Eigenschaft kann mithilfe eines Eigenschaftsausdrucks angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="9398b-109">The value of this property can be specified by using a property expression.</span></span>  
  
 <span data-ttu-id="9398b-110">**Ausgabename für Stichprobendaten**</span><span class="sxs-lookup"><span data-stu-id="9398b-110">**Sample output name**</span></span>  
 <span data-ttu-id="9398b-111">Geben Sie einen eindeutigen Namen für die Ausgabe an, die die als Stichprobe entnommenen Zeilen enthalten wird.</span><span class="sxs-lookup"><span data-stu-id="9398b-111">Provide a unique name for the output that will include the sampled rows.</span></span> <span data-ttu-id="9398b-112">Der angegebene Name wird im SSIS-Designer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9398b-112">The name provided will be displayed within SSIS Designer.</span></span>  
  
 <span data-ttu-id="9398b-113">**Ausgabename für nicht ausgewählte Daten**</span><span class="sxs-lookup"><span data-stu-id="9398b-113">**Unselected output name**</span></span>  
 <span data-ttu-id="9398b-114">Geben Sie einen eindeutigen Namen für die Ausgabe an, die die Zeilen enthalten wird, die nicht zur Stichprobe gehören.</span><span class="sxs-lookup"><span data-stu-id="9398b-114">Provide a unique name for the output that will contain the rows excluded from the sampling.</span></span> <span data-ttu-id="9398b-115">Der angegebene Name wird im SSIS-Designer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9398b-115">The name provided will be displayed within SSIS Designer.</span></span>  
  
 <span data-ttu-id="9398b-116">**Folgenden zufälligen Ausgangswert verwenden**</span><span class="sxs-lookup"><span data-stu-id="9398b-116">**Use the following random seed**</span></span>  
 <span data-ttu-id="9398b-117">Geben Sie den Ausgangswert für den Zufallszahlen-Generator an, der von der Transformation zum Erstellen der Stichprobe verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9398b-117">Specify the sampling seed for the random number generator that the transformation uses to create a sample.</span></span> <span data-ttu-id="9398b-118">Dies wird ausschließlich für Entwicklung und Tests empfohlen.</span><span class="sxs-lookup"><span data-stu-id="9398b-118">This is only recommended for development and testing.</span></span> <span data-ttu-id="9398b-119">Wenn kein zufälliger Ausgangswert angegeben wird, wird von der Transformation die Taktanzahl aus Microsoft Windows als Ausgangswert verwendet.</span><span class="sxs-lookup"><span data-stu-id="9398b-119">The transformation uses the Microsoft Windows tick count as a seed if a random seed is not specified.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9398b-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9398b-120">See Also</span></span>  
 <span data-ttu-id="9398b-121">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="9398b-121">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="9398b-122">Transformation für Prozentwert-Stichproben</span><span class="sxs-lookup"><span data-stu-id="9398b-122">Percentage Sampling Transformation</span></span>](data-flow/transformations/percentage-sampling-transformation.md)  
  
  
