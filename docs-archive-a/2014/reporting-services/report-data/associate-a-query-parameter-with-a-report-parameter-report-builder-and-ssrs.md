---
title: Zuordnen eines Abfrageparameters zu einem Berichtsparameter (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- queries [Reporting Services], parameters
- parameters [Reporting Services], queries
ms.assetid: 6d297e1a-ff71-472a-addc-349e863092b5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f65aa36e8910378d68963c8c9990518b661025ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697574"
---
# <a name="associate-a-query-parameter-with-a-report-parameter-report-builder-and-ssrs"></a><span data-ttu-id="e9252-102">Zuordnen eines Abfrageparameters zu einem Berichtsparameter (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="e9252-102">Associate a Query Parameter with a Report Parameter (Report Builder and SSRS)</span></span>
  <span data-ttu-id="e9252-103">Wenn Sie eine Datasetabfrage definieren, die eine Abfragevariable enthält, wird der Abfragebefehl analysiert.</span><span class="sxs-lookup"><span data-stu-id="e9252-103">When you define a dataset query that contains a query variable, the query command is parsed.</span></span> <span data-ttu-id="e9252-104">Für jede Abfragevariable werden ein entsprechender Datasetparameter und ein Berichtsparameter erstellt.</span><span class="sxs-lookup"><span data-stu-id="e9252-104">For each query variable, a corresponding dataset parameter and report parameter are created.</span></span> <span data-ttu-id="e9252-105">Der Datasetparameter verweist auf den Berichtsparameter.</span><span class="sxs-lookup"><span data-stu-id="e9252-105">The dataset parameter points to the report parameter.</span></span> <span data-ttu-id="e9252-106">Dies ermöglicht einem Benutzer, einen Wert anzugeben, der direkt an die Abfrage übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="e9252-106">This enables a user to enter a value that passes directly to the query.</span></span> <span data-ttu-id="e9252-107">Bei jeder Bearbeitung des Abfragebefehls findet der gleiche Prozess statt.</span><span class="sxs-lookup"><span data-stu-id="e9252-107">Each time you edit the query command, the same process takes place.</span></span>  
  
 <span data-ttu-id="e9252-108">Wenn Sie einen Berichtsparameter umbenennen, der an einen Abfrageparameter gebunden ist, müssen Sie die Abfrageparameter manuell mit dem umbenannten Berichtsparameter verknüpfen. Gehen Sie hierzu wie in diesem Thema beschrieben vor.</span><span class="sxs-lookup"><span data-stu-id="e9252-108">If you rename a report parameter that is bound to a query parameter, you need to manually link the query parameters to the renamed report parameter by using the procedure in this topic.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-associate-a-query-parameter-with-a-report-parameter"></a><span data-ttu-id="e9252-109">So ordnen Sie einen Abfrageparameter einem Berichtsparameter zu</span><span class="sxs-lookup"><span data-stu-id="e9252-109">To associate a query parameter with a report parameter</span></span>  
  
1.  <span data-ttu-id="e9252-110">Klicken Sie im Berichtsdatenbereich mit der rechten Maustaste auf das Dataset, klicken Sie auf **Dataseteigenschaften**, und klicken Sie anschließend auf **Parameter**.</span><span class="sxs-lookup"><span data-stu-id="e9252-110">In the Report Data pane, right-click the dataset, click **Dataset Properties**, and then click **Parameters**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e9252-111">Zum Anzeigen des Berichtsdatenbereichs klicken Sie im Menü **Ansicht** auf **Berichtsdaten** .</span><span class="sxs-lookup"><span data-stu-id="e9252-111">If the Report Data pane is not visible, click **Report Data** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="e9252-112">In der Spalte **Parametername**finden Sie den Namen des Abfrageparameters.</span><span class="sxs-lookup"><span data-stu-id="e9252-112">In the column **Parameter Name**, find the name of the query parameter.</span></span> <span data-ttu-id="e9252-113">Parameternamen werden automatisch basierend auf der Abfrage ausgefüllt.</span><span class="sxs-lookup"><span data-stu-id="e9252-113">Parameter names are automatically populated based on the query.</span></span> <span data-ttu-id="e9252-114">Jedes Mal, wenn Sie die Abfrage ändern, wird diese auf neue Abfrageparameter überprüft.</span><span class="sxs-lookup"><span data-stu-id="e9252-114">Every time you change the query, the query is checked for new query parameters.</span></span> <span data-ttu-id="e9252-115">Abfrageparameter, die Sie manuell erstellen, werden nicht geändert, wenn sich die Abfrage ändert.</span><span class="sxs-lookup"><span data-stu-id="e9252-115">Query parameters that you create manually are not changed when the query changes.</span></span>  
  
    -   <span data-ttu-id="e9252-116">Geben Sie unter **Parametername**den Abfrageparameternamen so ein, wie er in der Abfrage angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="e9252-116">In **Parameter Name**, find the query parameter name as it exists in the query.</span></span> <span data-ttu-id="e9252-117">Sie können auch manuell einen neuen Abfrageparameter hinzufügen und einen Namen eingeben.</span><span class="sxs-lookup"><span data-stu-id="e9252-117">You can also manually add a new query parameter and enter a name.</span></span>  
  
    -   <span data-ttu-id="e9252-118">Geben Sie unter **Parameterwert**einen Ausdruck ein, der zu dem Wert ausgewertet wird, der an den Abfrageparameter übergeben werden soll, oder wählen Sie einen entsprechenden Ausdruck aus.</span><span class="sxs-lookup"><span data-stu-id="e9252-118">In **Parameter Value**, type or select an expression that evaluates to the value to pass to the query parameter.</span></span> <span data-ttu-id="e9252-119">Dies ist in der Regel der Name des Berichtsparameters.</span><span class="sxs-lookup"><span data-stu-id="e9252-119">This is typically the name of the report parameter.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="e9252-120">Bei den Werten für die Abfrageparameter sind Sie nicht auf Berichtsparameter beschränkt.</span><span class="sxs-lookup"><span data-stu-id="e9252-120">You are not limited to report parameters as values for a query parameter.</span></span> <span data-ttu-id="e9252-121">Sie können jeden beliebigen Ausdruck verwenden, der auf einen Wert für den Parameterwert ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="e9252-121">You can use any expression that evaluates to a value for the parameter value.</span></span>  
  
3.  <span data-ttu-id="e9252-122">Wiederholen Sie Schritt 2 für jeden weiteren Abfrageparameter.</span><span class="sxs-lookup"><span data-stu-id="e9252-122">Repeat step 2 for additional query parameters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9252-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e9252-123">See Also</span></span>  
 <span data-ttu-id="e9252-124">[Melden Sie eingebettete Datasets und freigegebene Datasets &#40;Berichts-Generator und SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e9252-124">[Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="e9252-125">Berichts Parameter Konzept &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e9252-125">Report Parameters Concept &#40;Report Builder and SSRS&#41;</span></span>](../report-design/report-parameters-concepts-report-builder-and-ssrs.md)  
  
  
