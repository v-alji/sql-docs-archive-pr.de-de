---
title: Transformations-Editor für Prozent Stichproben | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.percentagesamplingtransformation.f1
helpviewer_keywords:
- Percentage Sampling Transformation Editor
ms.assetid: 2c40d804-26a3-4d35-809b-bc923d83d451
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c4dbd96ab952b6c88bdaa7bf56a0a2f1b3585c57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609294"
---
# <a name="percentage-sampling-transformation-editor"></a><span data-ttu-id="ad46f-102">Transformations-Editor für Prozentwertstichprobe</span><span class="sxs-lookup"><span data-stu-id="ad46f-102">Percentage Sampling Transformation Editor</span></span>
  <span data-ttu-id="ad46f-103">Im Dialogfeld **Transformations-Editor für Prozentwertstichprobe** können Sie einen Teil der Eingabe mithilfe des angegebenen Prozentsatzes von Zeilen als Stichprobe entnehmen.</span><span class="sxs-lookup"><span data-stu-id="ad46f-103">Use the **Percentage Sampling Transformation Editor** dialog box to split part of an input into a sample using a specified percentage of rows.</span></span> <span data-ttu-id="ad46f-104">Durch diese Transformation wird die Eingabe in zwei getrennte Ausgaben geteilt.</span><span class="sxs-lookup"><span data-stu-id="ad46f-104">This transformation divides the input into two separate outputs.</span></span>  
  
 <span data-ttu-id="ad46f-105">Weitere Informationen zur Transformation für Prozentwert-Stichproben finden Sie unter [Percentage Sampling Transformation](data-flow/transformations/percentage-sampling-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="ad46f-105">To learn more about the percentage sampling transformation, see [Percentage Sampling Transformation](data-flow/transformations/percentage-sampling-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="ad46f-106">Tastatur</span><span class="sxs-lookup"><span data-stu-id="ad46f-106">Options</span></span>  
 <span data-ttu-id="ad46f-107">**Prozentsatz der Zeilen**</span><span class="sxs-lookup"><span data-stu-id="ad46f-107">**Percentage of rows**</span></span>  
 <span data-ttu-id="ad46f-108">Geben Sie den Prozentsatz der Zeilen in der Eingabe an, die als Stichprobe verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ad46f-108">Specify the percentage of rows in the input to use as a sample.</span></span>  
  
 <span data-ttu-id="ad46f-109">Der Wert dieser Eigenschaft kann mithilfe eines Eigenschaftsausdrucks angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ad46f-109">The value of this property can be specified by using a property expression.</span></span>  
  
 <span data-ttu-id="ad46f-110">**Ausgabename für Stichprobendaten**</span><span class="sxs-lookup"><span data-stu-id="ad46f-110">**Sample output name**</span></span>  
 <span data-ttu-id="ad46f-111">Geben Sie einen eindeutigen Namen für die Ausgabe an, die die als Stichprobe entnommenen Zeilen enthalten wird.</span><span class="sxs-lookup"><span data-stu-id="ad46f-111">Provide a unique name for the output that will include the sampled rows.</span></span> <span data-ttu-id="ad46f-112">Der bereitgestellte Name wird im [!INCLUDE[ssIS](../includes/ssis-md.md)] -Designer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ad46f-112">The name provided will be displayed within the [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="ad46f-113">**Ausgabename für nicht ausgewählte Daten**</span><span class="sxs-lookup"><span data-stu-id="ad46f-113">**Unselected output name**</span></span>  
 <span data-ttu-id="ad46f-114">Geben Sie einen eindeutigen Namen für die Ausgabe an, die die Zeilen enthalten wird, die nicht zur Stichprobe gehören.</span><span class="sxs-lookup"><span data-stu-id="ad46f-114">Provide a unique name for the output that will contain the rows excluded from the sampling.</span></span> <span data-ttu-id="ad46f-115">Der bereitgestellte Name wird im [!INCLUDE[ssIS](../includes/ssis-md.md)] -Designer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ad46f-115">The name provided will be displayed within the [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="ad46f-116">**Folgenden zufälligen Ausgangswert verwenden**</span><span class="sxs-lookup"><span data-stu-id="ad46f-116">**Use the following random seed**</span></span>  
 <span data-ttu-id="ad46f-117">Geben Sie den Ausgangswert für den Zufallszahlen-Generator an, der von der Transformation zum Erstellen der Stichprobe verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ad46f-117">Specify the sampling seed for the random number generator that the transformation uses to create a sample.</span></span> <span data-ttu-id="ad46f-118">Dies wird ausschließlich für Entwicklung und Tests empfohlen.</span><span class="sxs-lookup"><span data-stu-id="ad46f-118">This is only recommended for development and testing.</span></span> <span data-ttu-id="ad46f-119">Wenn kein zufälliger Ausgangswert angegeben wird, wird von der Transformation die Taktanzahl aus Microsoft Windows verwendet.</span><span class="sxs-lookup"><span data-stu-id="ad46f-119">The transformation uses the Microsoft Windows tick count if a random seed is not specified.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad46f-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ad46f-120">See Also</span></span>  
 <span data-ttu-id="ad46f-121">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="ad46f-121">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="ad46f-122">Transformation für Zeilenstichproben</span><span class="sxs-lookup"><span data-stu-id="ad46f-122">Row Sampling Transformation</span></span>](data-flow/transformations/row-sampling-transformation.md)  
  
  
