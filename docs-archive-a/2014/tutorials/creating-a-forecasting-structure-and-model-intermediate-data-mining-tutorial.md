---
title: Erstellen einer Planungsstruktur und eines Modells (Data Mining-Lernprogramm für Fortgeschrittene) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 5f55cbf6-0db4-4cb4-a0f5-e27441873d4f
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: d77b15a9a8efe9a9c6faec49a2274ee182706992
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694889"
---
# <a name="creating-a-forecasting-structure-and-model-intermediate-data-mining-tutorial"></a><span data-ttu-id="2896f-102">Erstellen einer Struktur und eines Modells zur Planungserstellung (Data Mining-Lernprogramm für Fortgeschrittene)</span><span class="sxs-lookup"><span data-stu-id="2896f-102">Creating a Forecasting Structure and Model (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="2896f-103">Als Nächstes erstellen Sie mit dem Data Mining-Assistenten eine neue Miningstruktur und eine neues Miningmodell, basierend auf der zuvor erstellten Datenquellensicht.</span><span class="sxs-lookup"><span data-stu-id="2896f-103">Next, you will use the Data Mining Wizard to create a new mining structure and mining model based on the data source view that you just created.</span></span> <span data-ttu-id="2896f-104">In dieser Aufgabe legen Sie fest, dass das Miningmodell den [!INCLUDE[msCoName](../includes/msconame-md.md)]-Algorithmus Zeitreihe verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="2896f-104">In this task you will specify that the mining model should use the [!INCLUDE[msCoName](../includes/msconame-md.md)] Time Series algorithm.</span></span>  
  
### <a name="to-create-a-forecasting-mining-structure"></a><span data-ttu-id="2896f-105">So legen Sie eine Forecasting-Miningstruktur an</span><span class="sxs-lookup"><span data-stu-id="2896f-105">To create a forecasting mining structure</span></span>  
  
1.  <span data-ttu-id="2896f-106">Klicken Sie in Projektmappen-Explorer in mit der [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] rechten Maustaste auf **Mining Strukturen** , und wählen Sie **neue Mining Struktur**aus.</span><span class="sxs-lookup"><span data-stu-id="2896f-106">In Solution Explorer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], right-click **Mining Structures** and select **New Mining Structure**.</span></span>  
  
2.  <span data-ttu-id="2896f-107">Klicken Sie auf der Seite **Willkommen** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="2896f-107">On the **Welcome to the Data Mining Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="2896f-108">Überprüfen Sie auf der Seite **Definitions Methode auswählen** , ob **aus vorhandener relationaler Datenbank oder Data Warehouse** ausgewählt ist, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="2896f-108">On the **Select the Definition Method** page, verify that **From existing relational database or data warehouse** is selected, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="2896f-109">Wählen Sie auf der Seite **Data Mining-Struktur erstellen** unter **welche Data Mining Technik möchten Sie verwenden?** die Option **Microsoft Time Series**aus, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="2896f-109">On the **Create the Data Mining Structure** page, under **Which data mining technique do you want to use?**, select **Microsoft Time Series**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="2896f-110">Wählen Sie auf der Seite **Datenquellen Sicht auswählen** unter **Verfügbare Datenquellen Sichten**die Option **SalesByRegion**aus.</span><span class="sxs-lookup"><span data-stu-id="2896f-110">On the **Select Data Source View** page, under **Available data source views**, select **SalesByRegion**.</span></span>  
  
6.  <span data-ttu-id="2896f-111">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="2896f-111">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="2896f-112">Vergewissern Sie sich auf der Seite **Tabellentypen angeben** , dass das Kontrollkästchen in der Spalte **Fall** für die Tabelle vTimeSeries ausgewählt ist, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="2896f-112">On the **Specify Table Types** page, ensure that the check box in the **Case** column for the vTimeSeries table is selected, and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="2896f-113">Aktivieren Sie auf der Seite **Trainingsdaten angeben** die Kontrollkästchen in der Spalte **Schlüssel** für die Spalten ModelRegion und ReportingDate.</span><span class="sxs-lookup"><span data-stu-id="2896f-113">On the **Specify the Training Data** page, select the check boxes in the **Key** column for the ModelRegion and ReportingDate columns.</span></span>  
  
     <span data-ttu-id="2896f-114">ReportingDate muss standardmäßig ausgewählt werden, da Sie diese Spalte beim Erstellen der Datenquellen Sicht als logischen Primärschlüssel angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="2896f-114">ReportingDate should be selected by default, because you specified this column as the logical primary key when you created the data source view.</span></span> <span data-ttu-id="2896f-115">Wenn Sie ModelRegion als zweiten Schlüssel hinzufügen, weisen Sie den Algorithmus an, eine separate Zeitreihe für jede Kombination aus Modell und Region zu erstellen, die in diesem Feld aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="2896f-115">By adding ModelRegion as a second key, you are telling the algorithm to create a separate time series for each combination of model and region listed in this field.</span></span>  
  
9. <span data-ttu-id="2896f-116">Aktivieren Sie die Kontrollkästchen in den **Eingabe** -und **vorhersagbaren** Spalten für die Menge und die Spalte, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="2896f-116">Select the check boxes in the **Input** and **Predictable** columns for the Quantity, column, and then click **Next**.</span></span>  
  
     <span data-ttu-id="2896f-117">Wenn Sie **vorhersagbar**auswählen, geben Sie an, dass Sie Vorhersagen für die Daten in dieser Spalte erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="2896f-117">By selecting **Predictable**, you indicate that you want to create forecasts on the data in this column.</span></span> <span data-ttu-id="2896f-118">Da Sie jedoch die Prognose anhand von vergangenen Daten erstellen möchten, müssen Sie die Spalte auch als Eingabe hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="2896f-118">However, because you want to base the forecasts on past data, you must also add the column as an input.</span></span>  
  
10. <span data-ttu-id="2896f-119">Überprüfen Sie auf der Seite **Inhalt und Datentyp der Spalten angeben**die Auswahl.</span><span class="sxs-lookup"><span data-stu-id="2896f-119">On the page **Specify Columns' Content and Data Type**, review the selections.</span></span>  
  
     <span data-ttu-id="2896f-120">Die Model Region-Spalte wird als **Schlüssel** Spalte festgelegt, und die ReportingDate-Spalte wird automatisch als **Key Time** -Spalte bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="2896f-120">The ModelRegion column is designated as a **Key** column and the ReportingDate column is automatically designated as a **Key Time** column.</span></span> <span data-ttu-id="2896f-121">Es kann von jedem Schlüsseltyp nur jeweils einer vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="2896f-121">You can have only one of each type of key.</span></span>  
  
11. <span data-ttu-id="2896f-122">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="2896f-122">Click **Next**.</span></span>  
  
12. <span data-ttu-id="2896f-123">Geben Sie auf der Seite **Assistenten abschließen** für **Mining Struktur Name den Namen**ein `Forecasting` .</span><span class="sxs-lookup"><span data-stu-id="2896f-123">On the **Completing the Wizard** page, for **Mining structure name**, type `Forecasting`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2896f-124">Die Option zum Aktivieren von Drillthroughs ist für Zeitreihenmodelle nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2896f-124">The option to enable drillthrough is not available for time series models.</span></span>  
  
13. <span data-ttu-id="2896f-125">Geben Sie unter **Mining Modellname den Namen**ein `Forecasting` , und klicken Sie dann auf **Fertig**stellen.</span><span class="sxs-lookup"><span data-stu-id="2896f-125">In **Mining model name**, type `Forecasting`, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="2896f-126">Der Data Mining-Designer wird geöffnet, um die `Forecasting` soeben erstellte Mining Struktur anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2896f-126">Data Mining Designer opens to display the `Forecasting` mining structure that you just created.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="2896f-127">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="2896f-127">Next Task in Lesson</span></span>  
 [<span data-ttu-id="2896f-128">Ändern der Planungsstruktur &#40;Data Mining-Lernprogramm für fortgeschrittene&#41;</span><span class="sxs-lookup"><span data-stu-id="2896f-128">Modifying the Forecasting Structure &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/modifying-the-forecasting-structure-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="2896f-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2896f-129">See Also</span></span>  
 <span data-ttu-id="2896f-130">[Data Mining-Designer](../../2014/analysis-services/data-mining/data-mining-designer.md) </span><span class="sxs-lookup"><span data-stu-id="2896f-130">[Data Mining Designer](../../2014/analysis-services/data-mining/data-mining-designer.md) </span></span>  
 [<span data-ttu-id="2896f-131">Microsoft Time Series-Algorithmus</span><span class="sxs-lookup"><span data-stu-id="2896f-131">Microsoft Time Series Algorithm</span></span>](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm.md)  
  
  
