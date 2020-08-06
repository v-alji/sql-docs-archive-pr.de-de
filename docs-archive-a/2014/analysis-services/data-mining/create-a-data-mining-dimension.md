---
title: Erstellen einer Data Mining-Dimension | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining structures [Analysis Services], dimensions
ms.assetid: 9f0c39e5-3516-43ab-b203-f3f6dbcff89a
author: minewiskan
ms.author: owend
ms.openlocfilehash: 265cf671bbc825258f0b2bd6627690e8c52f252b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694834"
---
# <a name="create-a-data-mining-dimension"></a><span data-ttu-id="62d1d-102">Erstellen einer Data Mining-Dimension</span><span class="sxs-lookup"><span data-stu-id="62d1d-102">Create a Data Mining Dimension</span></span>
  <span data-ttu-id="62d1d-103">Wenn Ihre Miningstruktur auf einem OLAP-Cube basiert, können Sie eine Dimension erstellen, die den Inhalt des Miningmodells enthält.</span><span class="sxs-lookup"><span data-stu-id="62d1d-103">If your mining structure is based on an OLAP cube, you can create a dimension that contains the content of the mining model.</span></span> <span data-ttu-id="62d1d-104">Sie können dann die Dimension wieder in den Quellcube einbinden.</span><span class="sxs-lookup"><span data-stu-id="62d1d-104">You can then incorporate the dimension back into the source cube.</span></span>  
  
 <span data-ttu-id="62d1d-105">Sie können auch die Dimension durchsuchen, sie zum Untersuchen der Modellergebnisse verwenden oder die Dimension mit MDX abfragen.</span><span class="sxs-lookup"><span data-stu-id="62d1d-105">You can also browse the dimension, use it to explore the model results, or query the dimension using MDX.</span></span>  
  
### <a name="to-create-a-data-mining-dimension"></a><span data-ttu-id="62d1d-106">So erstellen Sie eine Data Mining-Dimension</span><span class="sxs-lookup"><span data-stu-id="62d1d-106">To create a data mining dimension</span></span>  
  
1.  <span data-ttu-id="62d1d-107">Wählen Sie im Data Mining-Designer in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]entweder die **Miningstruktur** -Registerkarte oder die **Miningmodelle** -Registerkarte aus.</span><span class="sxs-lookup"><span data-stu-id="62d1d-107">In Data Mining Designer in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], select either the **Mining Structure** tab or the **Mining Models** tab.</span></span>  
  
2.  <span data-ttu-id="62d1d-108">Wählen Sie aus dem Menü **Miningmodell** die Option **Data Mining-Dimension erstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="62d1d-108">From the **Mining Model** menu, select **Create a Data Mining Dimension**.</span></span>  
  
     <span data-ttu-id="62d1d-109">Das Dialogfeld **Data Mining-Dimension erstellen** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="62d1d-109">The **Create Data Mining Dimension** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="62d1d-110">Wählen Sie in der **Modellname** -Liste des Dialogfelds **Data Mining-Dimension auswählen** ein OLAP-Miningmodell aus.</span><span class="sxs-lookup"><span data-stu-id="62d1d-110">In the **Model name** list of the **Create Data Mining Dimension** dialog box, select an OLAP mining model.</span></span>  
  
4.  <span data-ttu-id="62d1d-111">Geben Sie im Feld **Dimensionsname** einen Namen für die neue Data Mining-Dimension ein.</span><span class="sxs-lookup"><span data-stu-id="62d1d-111">In the **Dimension name** box, enter a name for the new data mining dimension.</span></span>  
  
5.  <span data-ttu-id="62d1d-112">Wenn Sie einen Cube erstellen wollen, der die neue Data Mining-Dimension einbindet, wählen Sie **Cube erstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="62d1d-112">If you want to create a cube that includes the new data mining dimension, select **Create cube**.</span></span> <span data-ttu-id="62d1d-113">Nachdem Sie **Cube erstellen**ausgewählt haben, können Sie einen neuen Namen für den Cube eingeben.</span><span class="sxs-lookup"><span data-stu-id="62d1d-113">After you select **Create cube**, you can enter a new name for the cube.</span></span>  
  
6.  <span data-ttu-id="62d1d-114">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="62d1d-114">Click **OK**.</span></span>  
  
     <span data-ttu-id="62d1d-115">Die Data Mining-Dimension wird erstellt und dem **Dimensionen** -Ordner im Projektmappen-Explorer hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="62d1d-115">The data mining dimension is created and is added to the **Dimensions** folder in Solution Explorer.</span></span> <span data-ttu-id="62d1d-116">Wenn Sie **Cube erstellen**ausgewählt haben, wird auch ein neuer Cube erstellt und dem **Cubes** -Ordner hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="62d1d-116">If you selected **Create cube**, a new cube is also created and is added to the **Cubes** folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62d1d-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="62d1d-117">See Also</span></span>  
 [<span data-ttu-id="62d1d-118">Tasks und Anweisungen für Miningstrukturen</span><span class="sxs-lookup"><span data-stu-id="62d1d-118">Mining Structure Tasks and How-tos</span></span>](mining-structure-tasks-and-how-tos.md)  
  
  
