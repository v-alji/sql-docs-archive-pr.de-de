---
title: Ausschließen einer Spalte aus einem Mining Modell | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- excluding mining model columns
- mining models [Analysis Services], columns
- columns [data mining], excluding
ms.assetid: 404fe5fe-3ba2-4b9b-8780-0d02343d467f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 30affebc143184c6287858f60b5d4f5d089c322a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616273"
---
# <a name="exclude-a-column-from-a-mining-model"></a><span data-ttu-id="7f7c2-102">Ausschließen einer Spalte aus einem Miningmodell</span><span class="sxs-lookup"><span data-stu-id="7f7c2-102">Exclude a Column from a Mining Model</span></span>
  <span data-ttu-id="7f7c2-103">Wenn Sie ein neues Miningmodell erstellen, möchten Sie möglicherweise nicht alle Spalten verwenden, die in der Miningstruktur vorhanden sind, auf der das Modell basiert.</span><span class="sxs-lookup"><span data-stu-id="7f7c2-103">When you create a new mining model, you may not want to use all the columns that exist in the mining structure on which the model is based.</span></span> <span data-ttu-id="7f7c2-104">Beispielsweise haben Sie möglicherweise eine Spalte Customer Name für Drillthrough hinzugefügt, möchten Sie aber nicht für die Modellierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="7f7c2-104">For example, you might have added a customer name column for drillthrough, but don't want to use it for modeling.</span></span> <span data-ttu-id="7f7c2-105">Unter Umständen möchten Sie auch mehrere Kopien einer Spalte mit verschiedenen Diskretisierungen erstellen und in jedem Modell nur eine Kopie verwenden und die restlichen Objekte ignorieren.</span><span class="sxs-lookup"><span data-stu-id="7f7c2-105">Or, you might decide to create multiple copies of a column with different discretizations, and use only one of the copies in each model, and ignore the rest.</span></span> <span data-ttu-id="7f7c2-106">Sie könnten auch Eingabespalten in mehreren verschiedenen Modellen selektiv hinzufügen, um zu erkennen, wie die hinzugefügte Variable die Ausgabespalte beeinflusst.</span><span class="sxs-lookup"><span data-stu-id="7f7c2-106">You could also selectively add input columns in several different models to see how the added variable affects the output column.</span></span>  
  
 <span data-ttu-id="7f7c2-107">Sie müssen keine neue Miningstruktur für jede Kombination von Spalten erstellen, sondern es genügt, wenn Sie eine Spalte so kennzeichnen, dass sie nicht in einem bestimmten Modell verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7f7c2-107">You do not need to create a new mining structure for each combination of columns; instead, you can simply flag a column as not being used in a particular model.</span></span>  
  
### <a name="to-exclude-a-column-from-a-mining-model"></a><span data-ttu-id="7f7c2-108">So schließen Sie eine Spalte aus einem Miningmodell aus</span><span class="sxs-lookup"><span data-stu-id="7f7c2-108">To exclude a column from a mining model</span></span>  
  
1.  <span data-ttu-id="7f7c2-109">Wählen Sie in der Registerkarte **Miningmodelle** des Data Mining-Designers in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]unter dem entsprechenden Miningmodell die Zelle aus, die der Spalte entspricht, die ausgeschlossen werden soll.</span><span class="sxs-lookup"><span data-stu-id="7f7c2-109">In the **Mining Models** tab of Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], select the cell that corresponds to the column you want to exclude, under the appropriate mining model.</span></span>  
  
2.  <span data-ttu-id="7f7c2-110">Wählen Sie im Dropdown-Listenfeld **Ignorieren** aus.</span><span class="sxs-lookup"><span data-stu-id="7f7c2-110">Select **Ignore** from the drop-down list box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f7c2-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7f7c2-111">See Also</span></span>  
 [<span data-ttu-id="7f7c2-112">Miningmodelltasks und Anweisungen</span><span class="sxs-lookup"><span data-stu-id="7f7c2-112">Mining Model Tasks and How-tos</span></span>](mining-model-tasks-and-how-tos.md)  
  
  
