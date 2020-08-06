---
title: Durchsuchen von Modellen in Excel (SQL Server Data Mining-Add-Ins) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models, browsing
- browse models
- mining models, viewing
ms.assetid: a8cca1d7-602a-449a-875c-99da564965bc
author: minewiskan
ms.author: owend
ms.openlocfilehash: c992f1f61112478a85276b6596da0137ccd5c9be
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610297"
---
# <a name="browsing-models-in-excel-sql-server-data-mining-add-ins"></a><span data-ttu-id="bf31a-102">Durchsuchen von Modellen in Excel (SQL Server Data Mining-Add-Ins)</span><span class="sxs-lookup"><span data-stu-id="bf31a-102">Browsing Models in Excel (SQL Server Data Mining Add-ins)</span></span>
  <span data-ttu-id="bf31a-103">![Modell durchsuchen (Schaltfläche auf Data Mining-Menüband)](media/dmc-browse.gif "Modell durchsuchen (Schaltfläche auf Data Mining-Menüband)")</span><span class="sxs-lookup"><span data-stu-id="bf31a-103">![Browse Model button in Data Mining ribbon](media/dmc-browse.gif "Browse Model button in Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="bf31a-104">Die visuelle Erforschung des Modells ist meistens der schnellste und einfachste Weg, um ein klares Verständnis der Regeln und Beziehungen zu gewinnen, die von der Analyse aufgedeckt werden.</span><span class="sxs-lookup"><span data-stu-id="bf31a-104">Visually exploring the model is usually the fastest and easiest way to get an understanding of the rules and relationships discovered by analysis.</span></span> <span data-ttu-id="bf31a-105">Mit dem Data Mining-Client für Excel können Sie sowohl temporäre Modelle, die während der aktuellen Excel-Sitzung erstellt wurden, als auch die in einer [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]-Instanz gespeicherten Modelle durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="bf31a-105">By using the Data Mining Client for Excel, you can browse both temporary models created during the current Excel session, and models stored in an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="bf31a-106">Um ein Modell zu durchsuchen, wählen Sie ein Modell und die zugeordnete Struktur aus einer Liste der verfügbaren Modelle aus. Das Add-In wählt automatisch den entsprechenden Viewer für diesen Data Mining-Algorithmus aus.</span><span class="sxs-lookup"><span data-stu-id="bf31a-106">To browse a model, you select a model and its associated structure from a list of available models, and the add-in automatically picks the viewer that is appropriate for that data mining algorithm.</span></span> <span data-ttu-id="bf31a-107">Sie können einen Drillvorgang auf die interessantesten Trends ausführen, das fertig erstellte Data Mining-Modell filtern sowie Diagramme und Daten in Excel oder Visio kopieren.</span><span class="sxs-lookup"><span data-stu-id="bf31a-107">You can drill into the most interesting trends, filter the completed data mining model, and copy graphs and data to Excel or to Visio.</span></span>  
  
## <a name="using-the-browse-model-wizard"></a><span data-ttu-id="bf31a-108">Verwenden des Assistenten zum Durchsuchen von Modellen</span><span class="sxs-lookup"><span data-stu-id="bf31a-108">Using the Browse Model Wizard</span></span>  
  
1.  <span data-ttu-id="bf31a-109">Klicken Sie auf die Registerkarte **Data Mining** .</span><span class="sxs-lookup"><span data-stu-id="bf31a-109">Click the **Data Mining** tab.</span></span>  
  
2.  <span data-ttu-id="bf31a-110">Klicken Sie in der Gruppe **Modell Verwendung** auf **Durchsuchen**.</span><span class="sxs-lookup"><span data-stu-id="bf31a-110">In the **Model Usage** group, click **Browse**.</span></span>  
  
3.  <span data-ttu-id="bf31a-111">Wählen Sie im Dialogfeld **Modell auswählen** ein Mining Modell aus der Liste aus, und klicken Sie auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="bf31a-111">In the **Select Model** dialog box, choose a mining model from the list, and click **Next**.</span></span>  
  
4.  <span data-ttu-id="bf31a-112">Der Assistent öffnet ein Fenster zum **Durchsuchen** , das für den von Ihnen ausgewählten Modelltyp geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="bf31a-112">The wizard opens a **Browse** window that is appropriate for the type of model that you selected.</span></span>  
  
## <a name="list-of-data-mining-viewers"></a><span data-ttu-id="bf31a-113">Liste von Data Mining-Viewern</span><span class="sxs-lookup"><span data-stu-id="bf31a-113">List of Data Mining Viewers</span></span>  
 <span data-ttu-id="bf31a-114">Abhängig von dem Data Mining Algorithmus, den Sie beim Erstellen des Modells verwendet haben, sieht das Fenster **Durchsuchen** etwas anders aus.</span><span class="sxs-lookup"><span data-stu-id="bf31a-114">Depending on the data mining algorithm that you used when you created the model, the **Browse** window will look a bit different.</span></span> <span data-ttu-id="bf31a-115">Es kann Diagramme enthalten, die Ihnen das Verständnis der Ergebnisse erleichtern, oder Legenden mit zusätzlichen Details oder Steuerelemente für die Interaktion mit den Daten.</span><span class="sxs-lookup"><span data-stu-id="bf31a-115">It can include graphs to help interpret the results, legends that contain additional detail, and controls for interacting with the data.</span></span>  
  
 <span data-ttu-id="bf31a-116">Die folgenden Themen erhalten Anleitungen zur Verwendung der einzelnen Viewer, einschließlich Hinweise zum Interpretieren komplexer Diagramme und Anweisungen zum Ändern, Kopieren oder Verwenden der Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="bf31a-116">The following topics provide guidance in how to use each of the viewers, including tips on interpreting the complex graphs, and how to change, copy, or work with the results.</span></span>  
  
 [<span data-ttu-id="bf31a-117">Durchsuchen eines Association Rules-Modells</span><span class="sxs-lookup"><span data-stu-id="bf31a-117">Browsing an Association Rules Model</span></span>](browsing-an-association-rules-model.md)  
  
 [<span data-ttu-id="bf31a-118">Durchsuchen eines Clustermodells</span><span class="sxs-lookup"><span data-stu-id="bf31a-118">Browsing a Clustering Model</span></span>](browsing-a-clustering-model.md)  
  
 [<span data-ttu-id="bf31a-119">Durchsuchen eines Entscheidungsstrukturmodells</span><span class="sxs-lookup"><span data-stu-id="bf31a-119">Browsing a Decision Trees Model</span></span>](browsing-a-decision-trees-model.md)  
  
 [<span data-ttu-id="bf31a-120">Durchsuchen eines Planungsmodells</span><span class="sxs-lookup"><span data-stu-id="bf31a-120">Browsing a Forecasting Model</span></span>](browsing-a-forecasting-model.md)  
  
 [<span data-ttu-id="bf31a-121">Durchsuchen eines Naive Bayes-Modells</span><span class="sxs-lookup"><span data-stu-id="bf31a-121">Browsing a Naive Bayes Model</span></span>](browsing-a-naive-bayes-model.md)  
  
 [<span data-ttu-id="bf31a-122">Durchsuchen von Neural Network-Modellen</span><span class="sxs-lookup"><span data-stu-id="bf31a-122">Browsing a Neural Network Model</span></span>](browsing-a-neural-network-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="bf31a-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bf31a-123">See Also</span></span>  
 <span data-ttu-id="bf31a-124">[Anzeigen von Data Mining-Modellen in Visio &#40;Data Mining-Add-ins&#41;](viewing-data-mining-models-in-visio-data-mining-add-ins.md) </span><span class="sxs-lookup"><span data-stu-id="bf31a-124">[Viewing Data Mining Models in Visio &#40;Data Mining Add-ins&#41;](viewing-data-mining-models-in-visio-data-mining-add-ins.md) </span></span>  
 [<span data-ttu-id="bf31a-125">Verwalten von Modellen &#40;SQL Server Data Mining-Add-ins&#41;</span><span class="sxs-lookup"><span data-stu-id="bf31a-125">Manage Models &#40;SQL Server Data Mining Add-ins&#41;</span></span>](manage-models-sql-server-data-mining-add-ins.md)  
  
  
