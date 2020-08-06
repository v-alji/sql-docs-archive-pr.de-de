---
title: Ändern der Eigenschaften einer Mining Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining structures [Analysis Services], properties
ms.assetid: 03b16897-2e36-42b8-9f7d-db1b9b898401
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2c1e63ad5fada770394e2fc283e0e592319281b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694842"
---
# <a name="change-the-properties-of-a-mining-structure"></a><span data-ttu-id="0a352-102">Ändern der Eigenschaften einer Miningstruktur</span><span class="sxs-lookup"><span data-stu-id="0a352-102">Change the Properties of a Mining Structure</span></span>
  <span data-ttu-id="0a352-103">Es gibt zwei Arten von Eigenschaften in einer Miningstruktur, die jeweils geändert werden können:</span><span class="sxs-lookup"><span data-stu-id="0a352-103">There are two kinds of properties on a mining structure, both of which can be modified:</span></span>  
  
-   <span data-ttu-id="0a352-104">Eigenschaften der Miningstruktur, die die gesamte Struktur betreffen.</span><span class="sxs-lookup"><span data-stu-id="0a352-104">Properties of the mining structure that affect the entire structure</span></span>  
  
-   <span data-ttu-id="0a352-105">Eigenschaften in einzelnen Spalten in der Struktur</span><span class="sxs-lookup"><span data-stu-id="0a352-105">Properties on individual columns in the structure</span></span>  
  
 <span data-ttu-id="0a352-106">Einige Eigenschaften sind von anderen Eigenschafteneinstellungen abhängig.</span><span class="sxs-lookup"><span data-stu-id="0a352-106">Note that some properties are dependent on other property settings.</span></span> <span data-ttu-id="0a352-107">Zum Beispiel können Sie erst Eigenschaften festlegen, die klassifizierendes Verhalten (z. B. <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationMethod%2A> oder <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationBucketCount%2A>) steuern, wenn Sie den Datentyp der Spalte auf `Discretized` festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="0a352-107">For example, you cannot set properties that control binning behavior (such as <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationMethod%2A> or <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationBucketCount%2A>) until you have set the data type of the column to `Discretized`.</span></span>  
  
 <span data-ttu-id="0a352-108">Weitere Informationen zu Miningstruktureigenschaften finden Sie unter [Miningstrukturspalten](mining-structure-columns.md).</span><span class="sxs-lookup"><span data-stu-id="0a352-108">For more information about mining structure properties, see [Mining Structure Columns](mining-structure-columns.md).</span></span>  
  
### <a name="to-change-the-properties-of-a-mining-structure"></a><span data-ttu-id="0a352-109">So ändern Sie die Eigenschaften einer Miningstruktur</span><span class="sxs-lookup"><span data-stu-id="0a352-109">To change the properties of a mining structure</span></span>  
  
1.  <span data-ttu-id="0a352-110">Klicken Sie auf der Registerkarte **Miningstruktur** im Data Mining-Designer mit der rechten Maustaste entweder auf die Miningstruktur oder auf eine Spalte innerhalb der Miningstruktur, und klicken Sie anschließend auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="0a352-110">On the **Mining Structure** tab in Data Mining Designer, right-click either the mining structure or a column in the mining structure, and then select **Properties**.</span></span>  
  
     <span data-ttu-id="0a352-111">Im rechten Bildschirmbereich wird das **Eigenschaften** -Fenster geöffnet, wenn es nicht bereits sichtbar war.</span><span class="sxs-lookup"><span data-stu-id="0a352-111">The **Properties** window opens on the right side of the screen, if it was not already visible.</span></span>  
  
2.  <span data-ttu-id="0a352-112">Wählen Sie im **Eigenschaften** -Fenster den Wert aus, der der Eigenschaft entspricht, die Sie ändern möchten, und geben Sie dann den neuen Wert ein.</span><span class="sxs-lookup"><span data-stu-id="0a352-112">In the **Properties** window, select the value that corresponds to the property that you want to change, and then enter the new value.</span></span>  
  
     <span data-ttu-id="0a352-113">Der neue Wert wird wirksam, wenn Sie ein anderes Element im Designer auswählen.</span><span class="sxs-lookup"><span data-stu-id="0a352-113">The new value will take effect when you select a different element in the designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a352-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0a352-114">See Also</span></span>  
 [<span data-ttu-id="0a352-115">Tasks und Anweisungen für Miningstrukturen</span><span class="sxs-lookup"><span data-stu-id="0a352-115">Mining Structure Tasks and How-tos</span></span>](mining-structure-tasks-and-how-tos.md)  
  
  
