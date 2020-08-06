---
title: Angeben einer Spalte, die in einem Modell als Regressor verwendet werden soll | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d8e0cb8e-302a-4166-9ed0-e2d9e2919b0a
author: minewiskan
ms.author: owend
ms.openlocfilehash: 86899d3793985b5e3c07618360d7b6a540935a54
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608086"
---
# <a name="specify-a-column-to-use-as-regressor-in-a-model"></a><span data-ttu-id="f8aed-102">Bestimmen einer in einem Modell als Regressor zu verwendenden Spalte</span><span class="sxs-lookup"><span data-stu-id="f8aed-102">Specify a Column to Use as Regressor in a Model</span></span>
  <span data-ttu-id="f8aed-103">Ein lineares Regressionsmodell stellt den Wert des vorhersagbaren Attributs als Ergebnis einer Formel dar, die die Eingaben so kombiniert, dass die Daten so nah wie möglich an einer geschätzten Regressionsgeraden liegen.</span><span class="sxs-lookup"><span data-stu-id="f8aed-103">A linear regression model represents the value of the predictable attribute as the result of a formula that combines the inputs in such a way that the data is fitted as a closely as possible to an estimated regression line.</span></span> <span data-ttu-id="f8aed-104">Der Algorithmus akzeptiert nur numerische Werte als Eingaben und erkennt automatisch die am besten passenden Eingaben.</span><span class="sxs-lookup"><span data-stu-id="f8aed-104">The algorithm accepts only numeric values as inputs, and automatically detects the inputs that provide the best fit.</span></span>  
  
 <span data-ttu-id="f8aed-105">Sie können jedoch angeben, dass eine Spalte als Regressor einbezogen werden soll, indem Sie dem Modell den FORCE_REGRESSOR-Parameter hinzufügen und die zu verwendenden Regressoren angeben.</span><span class="sxs-lookup"><span data-stu-id="f8aed-105">However, you can specify that a column be included as a regressor by adding the FORCE_REGRESSOR parameter to the model and specifying the regressors to use.</span></span> <span data-ttu-id="f8aed-106">Sie sollten dies in Fällen tun, in denen das Attribut eine Bedeutung hat, auch wenn die Wirkung zu klein ist, um vom Modell erkannt zu werden. Oder wenn Sie sicherstellen möchten, dass das Attribut in die Formel einbezogen wird.</span><span class="sxs-lookup"><span data-stu-id="f8aed-106">You might want to do this in cases where the attribute has meaning even if the effect is too small to be detected by the model, or when you want to ensure that the attribute is included in the formula.</span></span>  
  
 <span data-ttu-id="f8aed-107">In der folgenden Prozedur wird beschrieben, wie ein einfaches lineares Regressionsmodell erstellt wird, und zwar mit den gleichen Beispieldaten, die im [Lernprogramm zu neuronalen Netzwerken](../../tutorials/lesson-5-build-models-intermediate-data-mining-tutorial.md)verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f8aed-107">The following procedure describes how to create a simple linear regression model, using the same sample data that is used for the [neural networks tutorial](../../tutorials/lesson-5-build-models-intermediate-data-mining-tutorial.md).</span></span> <span data-ttu-id="f8aed-108">Das Modell ist nicht unbedingt robust, zeigt jedoch, wie Sie ein lineares Regressionsmodell mit dem Data Mining-Designer anpassen können.</span><span class="sxs-lookup"><span data-stu-id="f8aed-108">The model is not necessarily robust, but demonstrates how to use the Data Mining Designer to customize a linear regression model.</span></span>  
  
### <a name="how-to-create-a-simple-linear-regression-model"></a><span data-ttu-id="f8aed-109">Erstellen eines einfachen linearen Regressionsmodells</span><span class="sxs-lookup"><span data-stu-id="f8aed-109">How to create a simple linear regression model</span></span>  
  
1.  <span data-ttu-id="f8aed-110">Erweitern Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]im **Projektmappen-Explorer**den Knoten **Miningstrukturen**.</span><span class="sxs-lookup"><span data-stu-id="f8aed-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], in **Solution Explorer**, expand **Mining Structures**.</span></span>  
  
2.  <span data-ttu-id="f8aed-111">Doppelklicken Sie auf die Datei Call Center.dmm, um sie im Designer zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f8aed-111">Double-click Call Center.dmm to open it in the designer.</span></span>  
  
3.  <span data-ttu-id="f8aed-112">Wählen Sie im Menü **Miningmodell** die Option **Neues Miningmodell**.</span><span class="sxs-lookup"><span data-stu-id="f8aed-112">From the **Mining Model** menu, select **New Mining Model**.</span></span>  
  
4.  <span data-ttu-id="f8aed-113">Wählen Sie als Algorithmus die Option **Microsoft Linear Regression**.</span><span class="sxs-lookup"><span data-stu-id="f8aed-113">For the algorithm, select **Microsoft Linear Regression**.</span></span> <span data-ttu-id="f8aed-114">Geben Sie als Namen **Callcenterregression**ein.</span><span class="sxs-lookup"><span data-stu-id="f8aed-114">For the name, type **Call Center Regression**.</span></span>  
  
5.  <span data-ttu-id="f8aed-115">Ändern Sie die Spaltenverwendung auf der Registerkarte **Miningmodelle** wie folgt.</span><span class="sxs-lookup"><span data-stu-id="f8aed-115">In the **Mining Models** tab, change the column usage as follows.</span></span> <span data-ttu-id="f8aed-116">Soweit dies nicht bereits der Fall ist, sollten alle Spalten, die nicht in der folgenden Liste enthalten sind, auf **Ignorieren**festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="f8aed-116">All columns not in the following list should be set to **Ignore**, if they are not already.</span></span>  
  
     <span data-ttu-id="f8aed-117">FactCallCenterID**Key**</span><span class="sxs-lookup"><span data-stu-id="f8aed-117">FactCallCenterID**Key**</span></span>  
  
     <span data-ttu-id="f8aed-118">ServiceGrade**PredictOnly**</span><span class="sxs-lookup"><span data-stu-id="f8aed-118">ServiceGrade**PredictOnly**</span></span>  
  
     <span data-ttu-id="f8aed-119">Total Operators**Input**</span><span class="sxs-lookup"><span data-stu-id="f8aed-119">Total Operators**Input**</span></span>  
  
     <span data-ttu-id="f8aed-120">AverageTimePerIssue**Input**</span><span class="sxs-lookup"><span data-stu-id="f8aed-120">AverageTimePerIssue**Input**</span></span>  
  
6.  <span data-ttu-id="f8aed-121">Wählen Sie im Menü **Miningmodell** die Option zum Festlegen der Modellparameter \*\*\*\* aus.</span><span class="sxs-lookup"><span data-stu-id="f8aed-121">From the **Mining Model** menu, select **Set Model Parameters**.</span></span>  
  
7.  <span data-ttu-id="f8aed-122">Geben Sie für den FORCE_REGRESSOR-Parameter in der Spalte **Wert** die Spaltennamen in Klammern und durch Kommas getrennt wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="f8aed-122">For the parameter, FORCE_REGRESSOR, in the **Value** column, type the column names enclosed in brackets and separated by a comma, as follows:</span></span>  
  
    ```  
    [Average Time Per Issue],[Total Operators]  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="f8aed-123">Der Algorithmus erkennt automatisch, welche Spalten die besten Regressoren sind.</span><span class="sxs-lookup"><span data-stu-id="f8aed-123">The algorithm will automatically detect which columns are the best regressors.</span></span> <span data-ttu-id="f8aed-124">Sie müssen Regressoren nur erzwingen, wenn Sie sicherstellen möchten, dass eine Spalte in der endgültigen Formel enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="f8aed-124">You only need to force regressors when you want to ensure that a column is included in the final formula.</span></span>  
  
8.  <span data-ttu-id="f8aed-125">Wählen Sie im Menü **Miningmodell** die Option **Modell verarbeiten**.</span><span class="sxs-lookup"><span data-stu-id="f8aed-125">From the **Mining Model** menu, select **Process Model**.</span></span>  
  
     <span data-ttu-id="f8aed-126">Im Viewer wird das Modell als einzelner Knoten dargestellt, der die Regressionsformel enthält.</span><span class="sxs-lookup"><span data-stu-id="f8aed-126">In the viewer, the model is represented a single node containing the regression formula.</span></span> <span data-ttu-id="f8aed-127">Sie können die Formel in der **Mininglegende**anzeigen oder die Koeffizienten für die Formel mithilfe von Abfragen extrahieren.</span><span class="sxs-lookup"><span data-stu-id="f8aed-127">You can view the formula in the **Mining Legend**, or you can extract the coefficients for the formula by using queries.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8aed-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f8aed-128">See Also</span></span>  
 <span data-ttu-id="f8aed-129">[Microsoft Linear Regression-Algorithmus](microsoft-linear-regression-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="f8aed-129">[Microsoft Linear Regression Algorithm](microsoft-linear-regression-algorithm.md) </span></span>  
 <span data-ttu-id="f8aed-130">[Data Mining-Abfragen](data-mining-queries.md) </span><span class="sxs-lookup"><span data-stu-id="f8aed-130">[Data Mining Queries](data-mining-queries.md) </span></span>  
 <span data-ttu-id="f8aed-131">[Technische Referenz für den Microsoft Linear Regression-Algorithmus](microsoft-linear-regression-algorithm-technical-reference.md) </span><span class="sxs-lookup"><span data-stu-id="f8aed-131">[Microsoft Linear Regression Algorithm Technical Reference](microsoft-linear-regression-algorithm-technical-reference.md) </span></span>  
 [<span data-ttu-id="f8aed-132">Miningmodellinhalt von linearen Regressionsmodellen &#40;Analysis Services – Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="f8aed-132">Mining Model Content for Linear Regression Models &#40;Analysis Services - Data Mining&#41;</span></span>](mining-model-content-for-linear-regression-models-analysis-services-data-mining.md)  
  
  
