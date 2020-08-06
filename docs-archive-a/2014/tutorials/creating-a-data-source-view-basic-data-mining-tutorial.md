---
title: Erstellen einer Datenquellen Sicht (Lernprogramm zu Data Mining-Grundlagen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: c1e68a88-0f82-415d-becc-78d180d4f845
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 4582845c905ef95601cbff2c810633f0cc901e3e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616286"
---
# <a name="creating-a-data-source-view-basic-data-mining-tutorial"></a><span data-ttu-id="eec90-102">Erstellen einer Datenquellensicht (Lernprogramm zu Data Mining-Grundlagen)</span><span class="sxs-lookup"><span data-stu-id="eec90-102">Creating a Data Source View (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="eec90-103">Eine Datenquellensicht wird für eine Datenquelle erstellt und definiert eine Teilmenge der Daten, die Sie in Miningstrukturen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="eec90-103">A data source view is built on a data source and defines a subset of the data, which you can then use in your mining structures.</span></span> <span data-ttu-id="eec90-104">Sie können die Datenquellensicht auch verwenden, um Spalten hinzuzufügen, berechnete Spalten und Aggregate zu erstellen und benannte Sichten hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="eec90-104">You can also use the data source view to add columns, create calculated columns and aggregates, and add named views.</span></span> <span data-ttu-id="eec90-105">Mithilfe von Datenquellensichten können Sie die Daten auswählen, die sich auf Ihr jeweiliges Projekt beziehen, Beziehungen zwischen Tabellen festlegen und die Datenstruktur ohne Änderung der ursprünglichen Datenquelle bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="eec90-105">By using data source views, you can select the data that relates to your project, establish relationships between tables, and modify the structure of the data, without modifying the original data source.</span></span> <span data-ttu-id="eec90-106">Weitere Informationen finden Sie unter [Datenquellsichten in mehrdimensionalen Modellen](https://docs.microsoft.com/analysis-services/multidimensional-models/data-source-views-in-multidimensional-models).</span><span class="sxs-lookup"><span data-stu-id="eec90-106">For more information, see [Data Source Views in Multidimensional Models](https://docs.microsoft.com/analysis-services/multidimensional-models/data-source-views-in-multidimensional-models).</span></span>  
  
### <a name="to-create-a-data-source-view"></a><span data-ttu-id="eec90-107">So erstellen Sie eine Datenquellensicht</span><span class="sxs-lookup"><span data-stu-id="eec90-107">To create a data source view</span></span>  
  
1.  <span data-ttu-id="eec90-108">Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf **Datenquellen Sichten**, und wählen Sie **neue Datenquellen Sicht**aus.</span><span class="sxs-lookup"><span data-stu-id="eec90-108">In **Solution Explorer**, right-click **Data Source Views**, and select **New Data Source View**.</span></span>  
  
2.  <span data-ttu-id="eec90-109">Klicken Sie auf der Seite **Willkommen beim Datenquellensicht-Assistenten** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="eec90-109">On the **Welcome to the Data Source View Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="eec90-110">Wählen Sie auf der Seite **Datenquelle auswählen** unter **relationale Datenquellen**die Datenquelle Adventure Works DW 2012 aus, die Sie in der letzten Aufgabe erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="eec90-110">On the **Select a Data Source** page, under **Relational data sources**, select the Adventure Works DW 2012 data source that you created in the last task.</span></span> <span data-ttu-id="eec90-111">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="eec90-111">Click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="eec90-112">Wenn Sie eine Datenquelle erstellen möchten, klicken Sie mit der rechten Maustaste auf **Datenquellen** , und klicken Sie dann auf **neue Datenquelle** , um den Datenquellen-Assistenten zu starten.</span><span class="sxs-lookup"><span data-stu-id="eec90-112">If you want to create a data source, right-click **Data Sources** and then click **New Data Source** to start the Data Source Wizard.</span></span>  
  
4.  <span data-ttu-id="eec90-113">Wählen Sie auf der Seite **Tabellen und Sichten auswählen** die folgenden Objekte aus, und klicken Sie dann auf den Pfeil nach rechts, um Sie in die neue Datenquellen Sicht einzuschließen:</span><span class="sxs-lookup"><span data-stu-id="eec90-113">On the **Select Tables and Views** page, select the following objects, and then click the right arrow to include them in the new data source view:</span></span>  
  
    -   <span data-ttu-id="eec90-114">**ProspectiveBuyer (dbo)** -Tabelle potenzieller Fahrrad Käufer</span><span class="sxs-lookup"><span data-stu-id="eec90-114">**ProspectiveBuyer (dbo)** - table of prospective bike buyers</span></span>  
  
    -   <span data-ttu-id="eec90-115">**vTargetMail (dbo)** -Ansicht der Verlaufs Daten zu den bisherigen Fahrrad Käufern</span><span class="sxs-lookup"><span data-stu-id="eec90-115">**vTargetMail (dbo)** - view of historical data about past bike buyers</span></span>  
  
5.  <span data-ttu-id="eec90-116">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="eec90-116">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="eec90-117">Auf der Seite **Assistenten abschließen** wird die Datenquellen Sicht standardmäßig Adventure Works DW 2012 benannt.</span><span class="sxs-lookup"><span data-stu-id="eec90-117">On the **Completing the Wizard** page, by default the data source view is named Adventure Works DW 2012.</span></span> <span data-ttu-id="eec90-118">Ändern Sie den Namen in `Targeted Mailing` , und klicken Sie dann auf **Fertig**stellen.</span><span class="sxs-lookup"><span data-stu-id="eec90-118">Change the name to `Targeted Mailing`, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="eec90-119">Die neue Datenquellen Sicht wird in der Ziel Registerkarte " **Mailing. DSV [Entwurf]** " geöffnet.</span><span class="sxs-lookup"><span data-stu-id="eec90-119">The new data source view opens in the **Targeted Mailing.dsv [Design]** tab.</span></span>  
  
## <a name="previous-task-in-lesson"></a><span data-ttu-id="eec90-120">Vorherige Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="eec90-120">Previous Task in Lesson</span></span>  
 [<span data-ttu-id="eec90-121">Erstellen einer Datenquelle &#40;Lernprogramm zu Data Mining-Grundlagen&#41;</span><span class="sxs-lookup"><span data-stu-id="eec90-121">Creating a Data Source &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-data-source-basic-data-mining-tutorial.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="eec90-122">Nächste Lektion</span><span class="sxs-lookup"><span data-stu-id="eec90-122">Next Lesson</span></span>  
 [<span data-ttu-id="eec90-123">Lektion 2: aufbauen einer Ziel-Mailing Struktur &#40;Lernprogramm zu Data Mining-Grundlagen&#41;</span><span class="sxs-lookup"><span data-stu-id="eec90-123">Lesson 2: Building a Targeted Mailing Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-2-building-a-targeted-mailing-structure-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="eec90-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="eec90-124">See Also</span></span>  
 [<span data-ttu-id="eec90-125">Definieren einer Datenquellensicht &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="eec90-125">Defining a Data Source View &#40;Analysis Services&#41;</span></span>](https://docs.microsoft.com/analysis-services/multidimensional-models/defining-a-data-source-view-analysis-services)  
  
  
