---
title: Erstellen einer neuen relationalen Mining Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining structures [Analysis Services], relational
- mining structures [Analysis Services], creating
- relational mining models [Analysis Services]
ms.assetid: 55bac3bd-700e-4f91-bcc6-f3cd8c026da1
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2b41dd3ac2e6144011c1b3acde27c4b5829a1661
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609538"
---
# <a name="create-a-new-relational-mining-structure"></a><span data-ttu-id="5b8d2-102">Erstellen einer neuen relationalen Miningstruktur</span><span class="sxs-lookup"><span data-stu-id="5b8d2-102">Create a New Relational Mining Structure</span></span>
  <span data-ttu-id="5b8d2-103">Verwenden Sie den Data Mining-Assistenten, um eine neue Mining Struktur zu erstellen, indem Sie Daten aus einer relationalen Datenbank oder einer anderen Quelle verwenden, und speichern Sie dann die Struktur und alle zugehörigen Modelle in einer [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Datenbank.</span><span class="sxs-lookup"><span data-stu-id="5b8d2-103">Use the Data Mining Wizard to create a new mining structure, using data from a relational database or other source, and then save the structure and any related models to a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span>  
  
### <a name="to-create-a-relational-mining-structure"></a><span data-ttu-id="5b8d2-104">So erstellen Sie eine relationale Miningstruktur</span><span class="sxs-lookup"><span data-stu-id="5b8d2-104">To create a relational mining structure</span></span>  
  
1.  <span data-ttu-id="5b8d2-105">Klicken Sie im Projektmappen-Explorer in einem **-Projekt mit der rechten Maustaste auf den Ordner** Miningstrukturen [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , und klicken Sie dann auf **Neue Miningstruktur**.</span><span class="sxs-lookup"><span data-stu-id="5b8d2-105">In Solution Explorer, right-click the **Mining Structures** folder in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project, and then click **New Mining Structure**.</span></span>  
  
     <span data-ttu-id="5b8d2-106">Der Data Mining-Assistent wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="5b8d2-106">The Data Mining Wizard opens.</span></span>  
  
2.  <span data-ttu-id="5b8d2-107">Klicken Sie auf der Seite **Willkommen** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="5b8d2-107">On the **Welcome to the Data Mining Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="5b8d2-108">Wählen Sie auf der Seite **Definitionsmethode auswählen** die Option **Aus vorhandener relationaler Datenbank oder vorhandenem Data Warehouse**aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="5b8d2-108">On the **Select the Definition Method** page, select **From existing relational database or data warehouse**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="5b8d2-109">Wählen Sie auf der Seite **Data Mining-Technik auswählen** den Data Mining-Algorithmus aus, den Sie verwenden wollen, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="5b8d2-109">On the **Select the Data Mining Technique** page, select the data mining algorithm that you want to use, and then click **Next**.</span></span>  
  
     <span data-ttu-id="5b8d2-110">Weitere Informationen zu Data Mining-Algorithmen finden Sie unter [Data Mining-Algorithmen &#40;Analysis Services – Data Mining&#41;](data-mining-algorithms-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="5b8d2-110">For more information about data mining algorithms, see [Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining-algorithms-analysis-services-data-mining.md).</span></span>  
  
5.  <span data-ttu-id="5b8d2-111">Klicken Sie auf der Seite **Datenquelle auswählen** unter **Verfügbare Datenquellensichten**auf die Datenquellensicht, die Sie verwenden wollen, und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="5b8d2-111">On the **Select Data Source View** page, under **Available data source views**, click the data source view that you want to use, and then click **Next**.</span></span>  
  
     <span data-ttu-id="5b8d2-112">Weitere Informationen zum Erstellen einer Datenquellensicht finden Sie unter [Datenquellensichten in mehrdimensionalen Modellen](../multidimensional-models/data-source-views-in-multidimensional-models.md).</span><span class="sxs-lookup"><span data-stu-id="5b8d2-112">For more information about creating a data source view, see [Data Source Views in Multidimensional Models](../multidimensional-models/data-source-views-in-multidimensional-models.md).</span></span>  
  
6.  <span data-ttu-id="5b8d2-113">Wählen Sie auf der Seite **Tabellentypen angeben** unter **Eingabetabellen**eine Falltabelle und eine geschachtelte Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="5b8d2-113">On the **Specify Table Types** page, under **Input tables**, select a case table and a nested table.</span></span>  
  
7.  <span data-ttu-id="5b8d2-114">Wählen Sie auf der Seite **Trainingsdaten angeben** unter **Miningmodellstruktur**den Schlüssel, die Eingabe und die vorhersagbaren Spalten aus.</span><span class="sxs-lookup"><span data-stu-id="5b8d2-114">On the **Specify the Training Data** page, under **Mining model structure**, select the key, input, and predictable columns.</span></span>  
  
     <span data-ttu-id="5b8d2-115">Nachdem Sie die vorhersagbare Spalte ausgewählt haben, können Sie auf die Schaltfläche **Vorschlagen** klicken, um das Dialogfeld **Verbundene Spalten vorschlagen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="5b8d2-115">After you select the predictable column, you can click the **Suggest** button to open the **Suggest Related Columns** dialog box.</span></span> <span data-ttu-id="5b8d2-116">Sie können die vorgeschlagenen Spalten übernehmen, indem Sie in diesem Dialogfeld auf **OK** klicken. Die ausgewählten Spalten werden dann in die Miningstruktur übernommen. Oder Sie ändern zuerst die Auswahl in der **Eingabe** -Spalte und klicken anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="5b8d2-116">You can accept the suggested columns by clicking **OK** in this dialog box to include the selected columns in the mining structure, or you can change the selections in the **Input** column first, and then click **OK**.</span></span> <span data-ttu-id="5b8d2-117">Um die Vorschläge zu ignorieren, klicken Sie auf **Abbrechen**.</span><span class="sxs-lookup"><span data-stu-id="5b8d2-117">To ignore the suggestions, click **Cancel**.</span></span>  
  
8.  <span data-ttu-id="5b8d2-118">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="5b8d2-118">Click **Next**.</span></span>  
  
9. <span data-ttu-id="5b8d2-119">Auf der Seite **Inhalt und Datentyp der Spalten angeben** können Sie unter **Miningmodellstruktur**den Inhaltstyp und den Datentyp jeder Spalte anpassen.</span><span class="sxs-lookup"><span data-stu-id="5b8d2-119">On the **Specify Columns' Content and Data Type** page, under **Mining model structure**, you can adjust the content type and data type for each column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5b8d2-120">Sie können auf **Erkennen** klicken, damit automatisch erkannt wird, ob eine Spalte kontinuierliche oder diskrete Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="5b8d2-120">You can click **Detect** to automatically detect whether a column contains continuous or discrete data.</span></span> <span data-ttu-id="5b8d2-121">Nachdem Sie auf diese Schaltfläche geklickt haben, werden in den Spalten **Inhaltstyp** und **Datentyp** der Spalteninhalt und die Datentypen aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="5b8d2-121">After you click this button, the column content and data types will be updated in the **Content Type** and **Data Type** columns.</span></span> <span data-ttu-id="5b8d2-122">Weitere Informationen zu den Inhalts- und Datentypen finden Sie unter [Inhaltstypen &#40;Data Mining&#41;](content-types-data-mining.md) und [Datentypen &#40;Data Mining&#41;](data-types-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="5b8d2-122">For more information about content types and data types, see [Content Types &#40;Data Mining&#41;](content-types-data-mining.md) and [Data Types &#40;Data Mining&#41;](data-types-data-mining.md).</span></span>  
  
10. <span data-ttu-id="5b8d2-123">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="5b8d2-123">Click **Next**.</span></span>  
  
11. <span data-ttu-id="5b8d2-124">Geben Sie auf der Seite **Assistenten abschließen** einen Namen für die zu erstellende Miningstruktur und das zugehörige ursprüngliche Miningmodell an. Klicken Sie anschließend auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="5b8d2-124">On the **Completing the Wizard** page, provide a name for the mining structure and the related initial mining model that will be created, and then click **Finish**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b8d2-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5b8d2-125">See Also</span></span>  
 [<span data-ttu-id="5b8d2-126">Tasks und Anweisungen für Miningstrukturen</span><span class="sxs-lookup"><span data-stu-id="5b8d2-126">Mining Structure Tasks and How-tos</span></span>](mining-structure-tasks-and-how-tos.md)  
  
  
