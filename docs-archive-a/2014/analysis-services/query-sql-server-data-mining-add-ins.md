---
title: Abfrage (SQL Server Data Mining-Add-Ins) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- queries [data mining]
- Data Mining Query Advanced Editor
- query builder [data mining]
- DMX
ms.assetid: 16af4a6f-18d4-496a-a304-7a13aa32ee76
author: minewiskan
ms.author: owend
ms.openlocfilehash: 90794aae8a3d664d47ab251ffdd954f22d48f992
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723177"
---
# <a name="query-sql-server-data-mining-add-ins"></a><span data-ttu-id="960b5-102">Abfrage (SQL Server Data Mining-Add-Ins)</span><span class="sxs-lookup"><span data-stu-id="960b5-102">Query (SQL Server Data Mining Add-ins)</span></span>
  <span data-ttu-id="960b5-103">![Abfragemodell (Schaltfläche auf Data Mining-Menüband)](media/dmc-query.gif "Abfragemodell (Schaltfläche auf Data Mining-Menüband)")</span><span class="sxs-lookup"><span data-stu-id="960b5-103">![Query Model button, Data Mining ribbon](media/dmc-query.gif "Query Model button, Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="960b5-104">Der **Abfrage** -Assistent unterstützt Sie bei der Interaktion mit vorhandenen Mining Modellen, um Vorhersagen auf Grundlage von Daten in einer Excel-Tabelle, einem Excel-Bereich oder einer anderen Datenquelle zu treffen.</span><span class="sxs-lookup"><span data-stu-id="960b5-104">The **Query** wizard helps you interact with existing mining models to make predictions based on data in an Excel table, an Excel range, or another data source.</span></span> <span data-ttu-id="960b5-105">Der Prozess der Anwendung neuer Daten auf ein vorhandenes Modell, um Trends vorherzusagen, wird als *Vorhersage Abfrage*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="960b5-105">The process of applying new data to an existing model to predict trends is called a *prediction query*.</span></span>  
  
 <span data-ttu-id="960b5-106">Der **Abfrage** -Assistent bietet auch einen erweiterten Editor zum Erstellen oder Ändern von Data Mining Modellen, zum Erstellen von benutzerdefinierten Abfragen oder zum Arbeiten mit Strukturen, die in anderen Tools nicht unterstützt werden, z. b. in Form von geclusterte Datasets.</span><span class="sxs-lookup"><span data-stu-id="960b5-106">The **Query** wizard also provides an advanced editor for creating or modifying data mining models, for generating custom queries, or for working with structures not supported in the other tools, such as nested datasets.</span></span>  
  
-   <span data-ttu-id="960b5-107">Verwenden Sie den Text-Editor, um die DMX-Anweisungen (Data Mining Extensions) einzugeben oder einzufügen, die Sie an anderer Stelle erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="960b5-107">Use the text editor to type or paste in the Data Mining Extensions (DMX) statements you've created elsewhere.</span></span>  
  
-   <span data-ttu-id="960b5-108">Verwenden Sie den interaktiven Abfrage-Generator, um eine benutzerdefinierte DMX-Anweisung mithilfe von Vorlagen und Dialogfeldern zusammenzustellen.</span><span class="sxs-lookup"><span data-stu-id="960b5-108">Use the interactive Query Builder to compose a custom DMX statement with the help of templates and dialog boxes.</span></span>  
  
-   <span data-ttu-id="960b5-109">Erstellen Sie DMX-Anweisungen zum Verwalten oder Sichern von Miningmodellen und -strukturen.</span><span class="sxs-lookup"><span data-stu-id="960b5-109">Create DMX statements to manage or back up mining models and structures.</span></span>  
  
## <a name="using-the-query-wizard"></a><span data-ttu-id="960b5-110">Verwenden des Abfrage-Assistenten</span><span class="sxs-lookup"><span data-stu-id="960b5-110">Using the Query Wizard</span></span>  
  
1.  <span data-ttu-id="960b5-111">Geben Sie zunächst die Datenquelle für die Eingabe an.</span><span class="sxs-lookup"><span data-stu-id="960b5-111">First, you must specify a source for the data to use as input.</span></span> <span data-ttu-id="960b5-112">Sie können Daten aus einer vorhandenen Excel-Tabelle oder einem vorhandenen Excel-Bereich verwenden, oder Sie können eine SQL-Anweisung angeben, um die Daten abzurufen.</span><span class="sxs-lookup"><span data-stu-id="960b5-112">You can use data in an existing Excel table or range, or you can specify a SQL statement to retrieve the data.</span></span>  
  
2.  <span data-ttu-id="960b5-113">Anschließend wird vom Assistenten eine Liste mit Data Mining-Modellen angezeigt, die sich auf dem Server befinden, mit dem Sie verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="960b5-113">Next, the wizard presents a list of data mining models on the server to which you are connected.</span></span> <span data-ttu-id="960b5-114">Wenn Sie das gewünschte Modell kennen und mit Data Mining vertraut sind, können Sie auch auf **erweitert** klicken, um den **erweiterten Data Mining-Abfrage-Editor**zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="960b5-114">If you know the model you want and are familiar with data mining, you can also click **Advanced** to open the **Data Mining Advanced Query Editor**.</span></span>  
  
3.  <span data-ttu-id="960b5-115">Abhängig von dem von Ihnen ausgewählten Modelltyp müssen Sie die Spalte angeben, in der sich die auszuwertenden Daten befinden, und die Zuordnungen zwischen den Eingabedatenspalten und den Modellspalten definieren.</span><span class="sxs-lookup"><span data-stu-id="960b5-115">Depending on the type of model that you choose, you must specify the column that contains the data to be evaluated, and define mappings between the input data columns and the model columns.</span></span> <span data-ttu-id="960b5-116">Abhängig von dem von Ihnen ausgewählten Algorithmus können Sie weitere Eigenschaften für das Modell festlegen.</span><span class="sxs-lookup"><span data-stu-id="960b5-116">Depending on the algorithm you choose, you can set other properties on the model.</span></span>  
  
4.  <span data-ttu-id="960b5-117">Schließlich können Sie im Assistenten eine oder mehrere Vorhersagen auswählen und angeben, wo die Ergebnisse gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="960b5-117">Finally, the wizard also gives you the ability to choose one or more predictions, and specify a destination in which to store the results.</span></span>  
  
 <span data-ttu-id="960b5-118">Sie können jederzeit auf **erweitert** klicken, um zum **erweiterten Data Mining-Abfrage-Editor**zu wechseln. Dadurch erhalten Sie mehr Kontrolle über die einzelnen Teile der DMX-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="960b5-118">At any time, you can click **Advanced** to switch to the **Data Mining Advanced Query Editor**, which gives you more control over each part of the DMX statement.</span></span> <span data-ttu-id="960b5-119">Weitere Informationen zur Verwendung der erweiterten Tools zur Abfrage Bearbeitung finden Sie unter Erweiterter [Data Mining-Abfrage-Editor](advanced-data-mining-query-editor.md).</span><span class="sxs-lookup"><span data-stu-id="960b5-119">For more information about how to use the advanced query editing tools, see [Advanced Data Mining Query Editor](advanced-data-mining-query-editor.md).</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="960b5-120">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="960b5-120">Requirements</span></span>  
 <span data-ttu-id="960b5-121">Wenn Sie den **Abfrage** -Assistenten verwenden möchten, müssen Sie mit einer Instanz von verbunden sein [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="960b5-121">To use the **Query** wizard, you must be connected to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="960b5-122">Außerdem muss der Server mindestens ein Data Mining-Modell eines geeigneten Typs enthalten.</span><span class="sxs-lookup"><span data-stu-id="960b5-122">Moreover, the server must contain at least one data mining model of an appropriate type.</span></span> <span data-ttu-id="960b5-123">Wenn keine Miningmodelle verfügbar sind, können Sie mithilfe der im Data Mining-Client für Excel bereitgestellten Assistenten ein Modell erstellen.</span><span class="sxs-lookup"><span data-stu-id="960b5-123">If no mining models are available, you can create one by using the wizards provided in the Data Mining Client for Excel.</span></span> <span data-ttu-id="960b5-124">Informationen zum Erstellen eines neuen Mining Modus mithilfe eines Assistenten finden Sie unter [Erstellen eines Data Mining-Modells](creating-a-data-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="960b5-124">For information about how to create a new mining mode by using a wizard, see [Creating a Data Mining Model](creating-a-data-mining-model.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="960b5-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="960b5-125">See Also</span></span>  
 <span data-ttu-id="960b5-126">[Bereitstellen und Skalieren von Mining Modellen &#40;Data Mining-Add-Ins für Excel&#41;](deploying-and-scaling-mining-models-data-mining-add-ins-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="960b5-126">[Deploying and Scaling Mining Models &#40;Data Mining Add-ins for Excel&#41;](deploying-and-scaling-mining-models-data-mining-add-ins-for-excel.md) </span></span>  
 [<span data-ttu-id="960b5-127">Data Mining-Client für Excel &#40;SQL Server Data Mining-Add-ins&#41;</span><span class="sxs-lookup"><span data-stu-id="960b5-127">Data Mining Client for Excel &#40;SQL Server Data Mining Add-ins&#41;</span></span>](data-mining-client-for-excel-sql-server-data-mining-add-ins.md)  
  
  
