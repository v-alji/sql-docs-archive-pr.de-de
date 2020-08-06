---
title: Teilen eines Datasets mithilfe der Transformation für bedingtes Teilen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Conditional Split transformation
- splitting dataset
- datasets [Integration Services], splitting
ms.assetid: 23b3e84f-9296-4dc9-81c0-c7f06ae3f1ff
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2efbc3973db1ab1b6b61f6de879e451319b50e49
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621089"
---
# <a name="split-a-dataset-by-using-the-conditional-split-transformation"></a><span data-ttu-id="1fd58-102">Teilen eines Datasets mithilfe der Transformation für bedingtes Teilen</span><span class="sxs-lookup"><span data-stu-id="1fd58-102">Split a Dataset by Using the Conditional Split Transformation</span></span>
  <span data-ttu-id="1fd58-103">Das Paket muss bereits mindestens einen Datenflusstask und eine Quelle enthalten, damit Sie eine Transformation für bedingtes Teilen hinzufügen und konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="1fd58-103">To add and configure a Conditional Split transformation, the package must already include at least one Data Flow task and a source.</span></span>  
  
### <a name="to-conditionally-split-a-dataset"></a><span data-ttu-id="1fd58-104">So führen Sie eine bedingte Teilung eines Datasets aus</span><span class="sxs-lookup"><span data-stu-id="1fd58-104">To conditionally split a dataset</span></span>  
  
1.  <span data-ttu-id="1fd58-105">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] das [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]-Projekt mit dem gewünschten Paket.</span><span class="sxs-lookup"><span data-stu-id="1fd58-105">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="1fd58-106">Doppelklicken Sie im Projektmappen-Explorer auf das Paket, um es zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="1fd58-106">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="1fd58-107">Klicken Sie auf die Registerkarte **Datenfluss** , und ziehen Sie dann aus **Toolbox**die Transformation für bedingtes Teilen auf die Entwurfsoberfläche.</span><span class="sxs-lookup"><span data-stu-id="1fd58-107">Click the **Data Flow** tab, and, from the **Toolbox**, drag the Conditional Split transformation to the design surface.</span></span>  
  
4.  <span data-ttu-id="1fd58-108">Verbinden Sie die Transformation für bedingtes Teilen mit dem Datenfluss, indem Sie den Konnektor von der Datenquelle oder der vorherigen Transformation auf die Transformation für bedingtes Teilen ziehen.</span><span class="sxs-lookup"><span data-stu-id="1fd58-108">Connect the Conditional Split transformation to the data flow by dragging the connector from the data source or the previous transformation to the Conditional Split transformation.</span></span>  
  
5.  <span data-ttu-id="1fd58-109">Doppelklicken Sie auf die Transformation für bedingtes Teilen.</span><span class="sxs-lookup"><span data-stu-id="1fd58-109">Double-click the Conditional Split transformation.</span></span>  
  
6.  <span data-ttu-id="1fd58-110">Erstellen Sie in **Transformations-Editor für bedingtes Teilen**die Ausdrücke, die als Bedingungen verwendet werden sollen, indem Sie Variablen, Spalten, Funktionen und Operatoren in die **Bedingung** -Spalte im Raster ziehen.</span><span class="sxs-lookup"><span data-stu-id="1fd58-110">In the **Conditional Split Transformation Editor**, build the expressions to use as conditions by dragging variables, columns, functions, and operators to the **Condition** column in the grid.</span></span> <span data-ttu-id="1fd58-111">Sie können den Ausdruck auch in die **Bedingung** -Spalte eingeben.</span><span class="sxs-lookup"><span data-stu-id="1fd58-111">Or, you can type the expression in the **Condition** column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1fd58-112">Eine Variable oder Spalte kann in mehreren Ausdrücken verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1fd58-112">A variable or column can be used in multiple expressions.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1fd58-113">Falls der Ausdruck ungültig ist, wird der Ausdruckstext hervorgehoben dargestellt, und die Fehler werden in einer QuickInfo in der Spalte beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1fd58-113">If the expression is not valid, the expression text is highlighted and a ToolTip on the column describes the errors.</span></span>  
  
7.  <span data-ttu-id="1fd58-114">Optional können Sie die Werte in der **Ausgabename** -Spalte ändern.</span><span class="sxs-lookup"><span data-stu-id="1fd58-114">Optionally, modify the values in the **Output Name** column.</span></span> <span data-ttu-id="1fd58-115">Die Standardnamen sind Fall 1, Fall 2 usw.</span><span class="sxs-lookup"><span data-stu-id="1fd58-115">The default names are Case 1, Case 2, and so forth.</span></span>  
  
8.  <span data-ttu-id="1fd58-116">Klicken Sie auf den Pfeil nach oben oder den Pfeil nach unten, um die Reihenfolge zu ändern, in der die Bedingungen ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="1fd58-116">To modify the sequence in which the conditions are evaluated, click the up arrow or down arrow.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1fd58-117">Positionieren Sie die Bedingungen, die höchstwahrscheinlich vorhanden sind, am Anfang der Liste.</span><span class="sxs-lookup"><span data-stu-id="1fd58-117">Place the conditions that are most likely to be encountered at the top of the list.</span></span>  
  
9. <span data-ttu-id="1fd58-118">Optional können Sie den Namen der Standardausgabe für Datenzeilen ändern, die mit keiner Bedingung übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="1fd58-118">Optionally, modify the name of the default output for data rows that do not match any condition.</span></span>  
  
10. <span data-ttu-id="1fd58-119">Klicken Sie auf **Fehlerausgabe konfigurieren**, um die Fehlerausgabe zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="1fd58-119">To configure an error output, click **Configure Error Output**.</span></span> <span data-ttu-id="1fd58-120">Weitere Informationen finden Sie unter [Konfigurieren einer Fehlerausgabe in einer Datenflusskomponente](../../configure-an-error-output-in-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="1fd58-120">For more information, see [Configure an Error Output in a Data Flow Component](../../configure-an-error-output-in-a-data-flow-component.md).</span></span>  
  
11. <span data-ttu-id="1fd58-121">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="1fd58-121">Click **OK**.</span></span>  
  
12. <span data-ttu-id="1fd58-122">Klicken Sie im Menü **Datei** auf **Ausgewählte Elemente speichern** , um das aktualisierte Paket zu speichern.</span><span class="sxs-lookup"><span data-stu-id="1fd58-122">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fd58-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1fd58-123">See Also</span></span>  
 <span data-ttu-id="1fd58-124">[Conditional Split Transformation](conditional-split-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="1fd58-124">[Conditional Split Transformation](conditional-split-transformation.md) </span></span>  
 <span data-ttu-id="1fd58-125">[SQL Server Integration Services-Transformationen](integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="1fd58-125">[Integration Services Transformations](integration-services-transformations.md) </span></span>  
 <span data-ttu-id="1fd58-126">[SQL Server Integration Services-Pfade](../integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="1fd58-126">[Integration Services Paths](../integration-services-paths.md) </span></span>  
 <span data-ttu-id="1fd58-127">[SQL Server Integration Services-Datentypen](../integration-services-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="1fd58-127">[Integration Services Data Types](../integration-services-data-types.md) </span></span>  
 <span data-ttu-id="1fd58-128">[Datenflusstask](../../control-flow/data-flow-task.md) </span><span class="sxs-lookup"><span data-stu-id="1fd58-128">[Data Flow Task](../../control-flow/data-flow-task.md) </span></span>  
 [<span data-ttu-id="1fd58-129">Integration Services-Ausdrücke &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="1fd58-129">Integration Services &#40;SSIS&#41; Expressions</span></span>](../../expressions/integration-services-ssis-expressions.md)  
  
  
