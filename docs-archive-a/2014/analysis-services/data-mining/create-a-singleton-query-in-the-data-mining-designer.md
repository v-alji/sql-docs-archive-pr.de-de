---
title: Erstellen einer SINGLETON-Abfrage im Data Mining-Designer | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- singleton queries [Analysis Services]
- Mining Model Prediction [Analysis Services], singleton queries
ms.assetid: 6cdca8a0-cf16-46eb-a652-0bff820625ab
author: minewiskan
ms.author: owend
ms.openlocfilehash: 07491924dbcf0bd35d049e6a7c290d49becfb45d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609534"
---
# <a name="create-a-singleton-query-in-the-data-mining-designer"></a><span data-ttu-id="8ed6a-102">Erstellen einer SINGLETON-Abfrage im Data Mining-Designer</span><span class="sxs-lookup"><span data-stu-id="8ed6a-102">Create a Singleton Query in the Data Mining Designer</span></span>
  <span data-ttu-id="8ed6a-103">Eine SINGLETON-Abfrage ist nützlich, wenn Sie eine Vorhersage für einen einzelnen Fall erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="8ed6a-103">A singleton query is useful if you want to create a prediction for a single case.</span></span> <span data-ttu-id="8ed6a-104">Weitere Informationen zu SINGLETON-Abfragen finden Sie unter [Data Mining-Abfragen](data-mining-queries.md).</span><span class="sxs-lookup"><span data-stu-id="8ed6a-104">For more information about singleton queries, see [Data Mining Queries](data-mining-queries.md).</span></span>  
  
 <span data-ttu-id="8ed6a-105">Auf der Registerkarte **Miningmodellvorhersage** im Data Mining-Designer können Sie zahlreiche unterschiedliche Abfragetypen erstellen.</span><span class="sxs-lookup"><span data-stu-id="8ed6a-105">In the **Mining Model Prediction** tab of Data Mining Designer, you can create many different types of queries.</span></span> <span data-ttu-id="8ed6a-106">Sie können eine Abfrage mit dem Designer erstellen oder durch das Eingeben von DMX-Anweisungen (Data Mining-Erweiterungen).</span><span class="sxs-lookup"><span data-stu-id="8ed6a-106">You can create a query by using the designer, or by typing Data Mining Extensions (DMX) statements.</span></span> <span data-ttu-id="8ed6a-107">Sie können auch mit dem Designer beginnen und die auf diese Weise erstellte Abfrage durch Änderung der DMX-Anweisungen oder durch Hinzufügen einer WHERE- oder ORDER BY-Klausel anpassen.</span><span class="sxs-lookup"><span data-stu-id="8ed6a-107">You can also start with the designer and modify the query that it creates by changing the DMX statements, or by adding a WHERE or ORDER BY clause.</span></span>  
  
 <span data-ttu-id="8ed6a-108">Um zwischen der Abfragedesignansicht und der Abfragetextansicht zu wechseln, klicken Sie auf die erste Schaltfläche auf der Symbolleiste.</span><span class="sxs-lookup"><span data-stu-id="8ed6a-108">To switch between the query design view and the query text view, click the first button on the toolbar.</span></span> <span data-ttu-id="8ed6a-109">Wenn Sie sich in der Abfragetextansicht befinden, können Sie den vom Generator für Vorhersageabfragen erstellten DMX-Code sehen.</span><span class="sxs-lookup"><span data-stu-id="8ed6a-109">When you are in the query text view, you can view the DMX code that Prediction Query Builder creates.</span></span> <span data-ttu-id="8ed6a-110">Sie können auch die Abfrage ausführen und ändern und dann die geänderte Abfrage erneut ausführen.</span><span class="sxs-lookup"><span data-stu-id="8ed6a-110">You can also run the query, modify the query, and run the modified query.</span></span> <span data-ttu-id="8ed6a-111">Die geänderte Abfrage wird jedoch nicht persistent gespeichert, wenn Sie zurück zur Entwurfssicht wechseln.</span><span class="sxs-lookup"><span data-stu-id="8ed6a-111">However, the modified query is not persisted if you switch back to the query design view.</span></span>  
  
 <span data-ttu-id="8ed6a-112">Im folgenden Code wird ein Beispiel einer SINGLETON-Abfrage für das Targeted Mailing-Modell TM_Decision_Tree veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="8ed6a-112">The following code shows an example of a singleton query against the targeted mailing model, TM_Decision_Tree.</span></span>  
  
```  
SELECT [Bike Buyer], PredictProbability([Bike Buyer]) as ProbableBuyer  
FROM [TM_Decision_Tree]  
NATURAL PREDICTION JOIN  
(SELECT '2' AS [Number Children At Home], '45' as [Age])  
AS [t]  
```  
  
 <span data-ttu-id="8ed6a-113">Die folgenden Schritte erläutern, wie diese Vorhersageabfrage erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="8ed6a-113">The following steps explain how to create this prediction query.</span></span>  
  
### <a name="to-create-a-singleton-query-by-using-the-data-mining-designer"></a><span data-ttu-id="8ed6a-114">So erstellen Sie eine SINGLETON-Abfrage mithilfe des Data Mining-Designers</span><span class="sxs-lookup"><span data-stu-id="8ed6a-114">To create a singleton query by using the Data Mining Designer</span></span>  
  
1.  <span data-ttu-id="8ed6a-115">Klicken Sie auf die **Miningmodellvorhersage** -Registerkarte im Data Mining-Designer.</span><span class="sxs-lookup"><span data-stu-id="8ed6a-115">Click the **Mining Model Prediction** tab in Data Mining Designer.</span></span>  
  
2.  <span data-ttu-id="8ed6a-116">Klicken Sie in der **Miningmodell** -Tabelle auf **Modell auswählen** .</span><span class="sxs-lookup"><span data-stu-id="8ed6a-116">Click **Select Model** on the **Mining Model** table.</span></span>  
  
     <span data-ttu-id="8ed6a-117">Das Dialogfeld **Miningmodell auswählen** wird geöffnet. Es zeigt alle Miningstrukturen an, die im aktuellen Projekt vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="8ed6a-117">The **Select Mining Model** dialog box opens to show all the mining structures that exist in the current project.</span></span>  
  
     <span data-ttu-id="8ed6a-118">Wählen Sie das Modell aus, das Sie zum Erstellen einer Vorhersage verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="8ed6a-118">Select the model that you want to use for creating a prediction.</span></span>  
  
     <span data-ttu-id="8ed6a-119">Wählen Sie TM_Decision_Tree aus, und klicken Sie auf **OK**, um beispielsweise den Beispielcode zu Beginn dieses Themas zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8ed6a-119">For example, to create the sample code shown at the start of this topic, select TM_Decision_Tree, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="8ed6a-120">Klicken Sie auf der Symbolleiste der Registerkarte **Miningmodellvorhersage** auf **SINGLETON-Abfrage** .</span><span class="sxs-lookup"><span data-stu-id="8ed6a-120">Click **Singleton query** on the toolbar of the **Mining Model Prediction** tab.</span></span>  
  
     <span data-ttu-id="8ed6a-121">Die Tabelle **SINGLETON-Abfrageeingabe** wird auf der Registerkarte angezeigt, deren Spalten automatisch den Spalten in der **Miningmodell** -Tabelle zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="8ed6a-121">The **Singleton Query Input** table appears on the tab, with the columns automatically mapped to the columns in the **Mining Model** table.</span></span>  
  
4.  <span data-ttu-id="8ed6a-122">Wählen Sie in der **SINGLETON-Abfrageeingabe** -Tabelle in der **Wert** -Spalte Werte aus, mit denen der Fall beschrieben wird, für den Sie eine Vorhersage erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="8ed6a-122">On the **Singleton Query Input** table, select values in the **Value** column to describe the case for which you want to create a prediction.</span></span>  
  
     <span data-ttu-id="8ed6a-123">Wählen Sie beispielsweise für **Number Children at Home**den Wert **2** aus, und geben Sie dann `45` für **Age**ein.</span><span class="sxs-lookup"><span data-stu-id="8ed6a-123">For example, select **2** for **Number Children At Home**, and then type `45` for **Age**.</span></span>  
  
5.  <span data-ttu-id="8ed6a-124">Ziehen Sie eine vorhersagbare Spalte aus der **Mining Modell** Tabelle in die **Quell** Spalte unten auf der Registerkarte. Optional können Sie einen Alias für die Spalte eingeben.</span><span class="sxs-lookup"><span data-stu-id="8ed6a-124">Drag a predictable column from the **Mining Model** table to the **Source** column at the bottom of the tab. Optionally, you can type an alias for the column.</span></span>  
  
     <span data-ttu-id="8ed6a-125">Ziehen Sie beispielsweise **Bike Buyer** in die Spalte **Quelle** .</span><span class="sxs-lookup"><span data-stu-id="8ed6a-125">For example, drag **Bike Buyer** to the **Source** column.</span></span>  
  
6.  <span data-ttu-id="8ed6a-126">Fügen Sie je nach Bedarf die zusätzlichen Funktionen der Abfrage hinzu, indem Sie **Vorhersagefunktion** oder **Benutzerdefinierter Ausdruck** aus der Dropdownliste in der **Quelle** -Spalte auswählen.</span><span class="sxs-lookup"><span data-stu-id="8ed6a-126">Add any additional functions to the query by selecting **Prediction Function** or **Custom Expression** from the drop-down list in the **Source** column.</span></span>  
  
     <span data-ttu-id="8ed6a-127">Klicken Sie beispielsweise auf **Vorhersagefunktion**, und wählen Sie **PredictProbability**aus.</span><span class="sxs-lookup"><span data-stu-id="8ed6a-127">For example, click **Prediction Function**, and select **PredictProbability**.</span></span>  
  
7.  <span data-ttu-id="8ed6a-128">Klicken Sie in der Zeile **PredictProbability** auf **Kriterium/Argument** , und geben Sie den Namen der vorherzusagenden Spalte ein und optional einen bestimmten vorherzusagenden Wert.</span><span class="sxs-lookup"><span data-stu-id="8ed6a-128">Click **Criteria/Argument** in the **PredictProbability** row, and type the name of the column to predict, and optionally a specific value to predict.</span></span>  
  
     <span data-ttu-id="8ed6a-129">Geben Sie beispielsweise `[Bike Buyer], 1`.</span><span class="sxs-lookup"><span data-stu-id="8ed6a-129">For example, type `[Bike Buyer], 1`.</span></span>  
  
8.  <span data-ttu-id="8ed6a-130">Klicken Sie in der Zeile **PredictProbability** auf das Feld **Alias** , und geben Sie einen Verweisnamen für die neue Spalte ein.</span><span class="sxs-lookup"><span data-stu-id="8ed6a-130">Click the **Alias** box in the **PredictProbability** row, and type a name to refer to the new column.</span></span>  
  
     <span data-ttu-id="8ed6a-131">Geben Sie beispielsweise `ProbableBuyer`.</span><span class="sxs-lookup"><span data-stu-id="8ed6a-131">For example, type `ProbableBuyer`.</span></span>  
  
9. <span data-ttu-id="8ed6a-132">Klicken Sie auf der Symbolleiste der Registerkarte **Miningmodellvorhersage** auf **Zur Abfragergebnissicht wechseln** .</span><span class="sxs-lookup"><span data-stu-id="8ed6a-132">Click **Switch to query result view** on the toolbar of the **Mining Model Prediction** tab.</span></span>  
  
     <span data-ttu-id="8ed6a-133">Ein neuer Bildschirm wird geöffnet, der das Ergebnis der Abfrage anzeigt.</span><span class="sxs-lookup"><span data-stu-id="8ed6a-133">A new screen opens to show the result of the query.</span></span> <span data-ttu-id="8ed6a-134">Um die DMX-Anweisung anzuzeigen, die Sie gerade erstellt haben, klicken Sie auf **SQL**.</span><span class="sxs-lookup"><span data-stu-id="8ed6a-134">To view the DMX statement that you just created, click **SQL**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ed6a-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8ed6a-135">See Also</span></span>  
 [<span data-ttu-id="8ed6a-136">Vorhersageabfragen &#40;Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="8ed6a-136">Prediction Queries &#40;Data Mining&#41;</span></span>](prediction-queries-data-mining.md)  
  
  
