---
title: Erstellen eines Alias für eine Modell Spalte | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining [Analysis Services], how-to topics
- mining models [Analysis Services], columns
- column names [Analysis Services]
ms.assetid: c80ebe66-a8f8-4f24-9fe8-8288de9d13bc
author: minewiskan
ms.author: owend
ms.openlocfilehash: 908c0a8d8caa810badf4b82dc3dd3f411d09f323
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609530"
---
# <a name="create-an-alias-for-a-model-column"></a><span data-ttu-id="2f0a2-102">Erstellen eines Alias für eine Modellspalte</span><span class="sxs-lookup"><span data-stu-id="2f0a2-102">Create an Alias for a Model Column</span></span>
  <span data-ttu-id="2f0a2-103">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]können Sie einen Alias für eine Modellspalte erstellen.</span><span class="sxs-lookup"><span data-stu-id="2f0a2-103">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], you can create an alias for a model column.</span></span> <span data-ttu-id="2f0a2-104">Dies kann hilfreich sein, wenn der Miningstrukturname zu lang ist, um mühelos damit zu arbeiten, oder wenn Sie der Spalte einen aussagekräftigeren Namen im Hinblick auf Inhalt oder Verwendung im Modell geben möchten.</span><span class="sxs-lookup"><span data-stu-id="2f0a2-104">This might be useful when the mining structure name is too long to easily work with, or when you want to rename the column to be more descriptive of its contents or usage in the model.</span></span> <span data-ttu-id="2f0a2-105">Beispiel: wenn Sie eine Kopie einer Strukturspalte erstellen und die Spalte dann für ein bestimmtes Modell unterschiedlich diskretisieren, können Sie die Spalte umbenennen, um den Inhalt genauer anzugeben.</span><span class="sxs-lookup"><span data-stu-id="2f0a2-105">For example, if you make a copy of a structure column and then discretize the column differently for a particular model, you can rename the column to reflect the content more accurately.</span></span>  
  
 <span data-ttu-id="2f0a2-106">Zum Erstellen eines Alias für eine Modellspalte verwenden Sie den Bereich **Eigenschaften** und legen [Name](https://docs.microsoft.com/bi-reference/assl/properties/name-element-assl) -Eigenschaft der Spalte fest.</span><span class="sxs-lookup"><span data-stu-id="2f0a2-106">To create an alias for a model column, you use the **Properties** pane and set the [Name](https://docs.microsoft.com/bi-reference/assl/properties/name-element-assl) property of the column.</span></span>  
  
 <span data-ttu-id="2f0a2-107">Auf der Registerkarte **Miningmodelle** im Data Mining Designer wird der Alias in Klammern neben der Beschriftung zur Spaltenverwendung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2f0a2-107">On the **Mining Models** tab of Data Mining Designer, the alias appears enclosed in parentheses next to the column usage label.</span></span>  
  
 <span data-ttu-id="2f0a2-108">Informationen zum Festlegen der Eigenschaften eines Miningmodells finden Sie unter [Miningmodellspalten](mining-model-columns.md).</span><span class="sxs-lookup"><span data-stu-id="2f0a2-108">For information about how to set the properties of a mining model, see [Mining Model Columns](mining-model-columns.md).</span></span>  
  
### <a name="to-add-an-alias-to-a-mining-model-column"></a><span data-ttu-id="2f0a2-109">So fügen Sie einen Alias einer Miningmodellspalte hinzu</span><span class="sxs-lookup"><span data-stu-id="2f0a2-109">To add an alias to a mining model column</span></span>  
  
1.  <span data-ttu-id="2f0a2-110">Klicken Sie im Data Mining Designer auf der Registerkarte **Miningmodelle** mit der rechten Maustaste auf die Zelle im Miningmodell für die Miningspalte, die Sie ändern möchten, und wählen Sie dann **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="2f0a2-110">In the **Mining Models** tab in Data Mining Designer, right-click the cell in the mining model for the mining column that you want to change, and then select **Properties**.</span></span>  
  
2.  <span data-ttu-id="2f0a2-111">Klicken Sie anschließend im Fenster **Eigenschaften** auf der rechten Seite des Fensters auf die Zelle neben der Name-Eigenschaft, und löschen Sie den aktuellen Wert.</span><span class="sxs-lookup"><span data-stu-id="2f0a2-111">In the **Properties** window on the right side of the screen, click the cell next to the Name property and delete the current value.</span></span> <span data-ttu-id="2f0a2-112">Geben Sie einen neuen Namen für die Spalte ein.</span><span class="sxs-lookup"><span data-stu-id="2f0a2-112">Type a new name for the column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f0a2-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2f0a2-113">See Also</span></span>  
 <span data-ttu-id="2f0a2-114">[Mining Modell Tasks und Anleitungen](mining-model-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="2f0a2-114">[Mining Model Tasks and How-tos](mining-model-tasks-and-how-tos.md) </span></span>  
 [<span data-ttu-id="2f0a2-115">Miningmodelleigenschaften</span><span class="sxs-lookup"><span data-stu-id="2f0a2-115">Mining Model Properties</span></span>](mining-model-properties.md)  
  
  
