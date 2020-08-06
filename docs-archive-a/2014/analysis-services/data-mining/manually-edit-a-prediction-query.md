---
title: Manuelles Bearbeiten einer Vorhersage Abfrage | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- modifying prediction queries
- Mining Model Prediction [Analysis Services], modifying prediction queries
- manual prediction query modification [Analysis Services]
ms.assetid: 9f6a9298-49d5-4675-ad49-977a47dff5a6
author: minewiskan
ms.author: owend
ms.openlocfilehash: e887e935dafcd2428859fd959cb7bc64650c660d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622953"
---
# <a name="manually-edit-a-prediction-query"></a><span data-ttu-id="40512-102">Manuelles Bearbeiten eine Vorhersageabfrage</span><span class="sxs-lookup"><span data-stu-id="40512-102">Manually Edit a Prediction Query</span></span>
  <span data-ttu-id="40512-103">Nachdem Sie eine Abfrage mit dem Generator für Vorhersageabfragen erstellt haben, können Sie die Abfrage ändern, indem Sie zur Abfragetextansicht auf der Registerkarte **Miningmodellvorhersage** des Data Mining-Designers wechseln.</span><span class="sxs-lookup"><span data-stu-id="40512-103">After you have designed a query by using the Prediction Query Builder, you can modify the query by switching to Query Text view on the **Mining Model Prediction** tab of Data Mining Designer.</span></span> <span data-ttu-id="40512-104">Am unteren Rand des Bildschirms wird ein Texteditor angezeigt, in dem die vom Abfragegenerator erstellte Abfrage angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="40512-104">A text editor appears at the bottom of the screen to display the query that the query builder created.</span></span>  
  
 <span data-ttu-id="40512-105">Das Wechseln zur Abfragetextansicht ist für Hinzufügungen zur Abfrage nützlich.</span><span class="sxs-lookup"><span data-stu-id="40512-105">Switching to Query Text view is useful for making additions to the query.</span></span> <span data-ttu-id="40512-106">Sie können z. B. eine WHERE-Klausel oder eine ORDER BY-Klausel hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="40512-106">For example, you can add a WHERE clause or ORDER BY clause.</span></span>  
  
 <span data-ttu-id="40512-107">Verwenden Sie das Raster im Generator für Vorhersageabfragen, um die Namen von Objekten und Spalten einzufügen, und richten Sie die Syntax für einzelne Vorhersagefunktionen ein, und wechseln Sie dann in den manuellen Bearbeitungsmodus, um Parameterwerte zu ändern.</span><span class="sxs-lookup"><span data-stu-id="40512-107">Use the grid in the Prediction Query Builder to insert the names of objects and columns and set up the syntax for individual prediction functions, and then switch to manual editing mode to change parameter values.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="40512-108">Wenn Sie von der **Abfragetextansicht** wieder zurück zur **Entwurfsansicht** wechseln, gehen alle von Ihnen in der **Abfragetextansicht** vorgenommenen Änderungen verloren.</span><span class="sxs-lookup"><span data-stu-id="40512-108">If you switch back to **Design** view from **Query Text** view, any changes that you made in **Query Text** view will be lost.</span></span>  
  
### <a name="modify-a-query"></a><span data-ttu-id="40512-109">Ändern einer Abfrage</span><span class="sxs-lookup"><span data-stu-id="40512-109">Modify a query</span></span>  
  
1.  <span data-ttu-id="40512-110">Klicken Sie in der Registerkarte **Miningmodellvorhersage** des Data Mining-Designers in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]auf **SQL**.</span><span class="sxs-lookup"><span data-stu-id="40512-110">On the **Mining Model Prediction** tab in Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], click **SQL**.</span></span>  
  
     <span data-ttu-id="40512-111">Der Rasterbereich am unteren Bildschirmrand wird durch einen Texteditor ersetzt, der die Abfrage enthält.</span><span class="sxs-lookup"><span data-stu-id="40512-111">The grid at the bottom of the screen is replaced by a text editor that contains the query.</span></span> <span data-ttu-id="40512-112">In diesem Editor können Sie die Abfrage ändern.</span><span class="sxs-lookup"><span data-stu-id="40512-112">You can type changes to the query in this editor.</span></span>  
  
2.  <span data-ttu-id="40512-113">Zum Ausführen der Abfrage wählen Sie im Menü **Miningmodell** die Option **Ergebnis**, oder klicken Sie auf die Schaltfläche zum Wechseln zu den Abfrageergebnissen.</span><span class="sxs-lookup"><span data-stu-id="40512-113">To run the query, on the **Mining Model** menu, select **Result**, or click the button to switch to query results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="40512-114">Wenn die erstellte Abfrage ungültig ist, werden im Ergebnisfenster weder ein Fehler noch Ergebnisse angezeigt.</span><span class="sxs-lookup"><span data-stu-id="40512-114">If the query that you have created is invalid, the Results window does not display an error and does not display any results.</span></span> <span data-ttu-id="40512-115">Klicken Sie auf die Schaltfläche **Entwurf** , oder wählen Sie im Menü **Miningmodell** die Option **Entwurf** oder **Abfrage** aus, um das Problem zu beheben und die Abfrage erneut auszuführen.</span><span class="sxs-lookup"><span data-stu-id="40512-115">Click the **Design** button, or select **Design** or **Query** from the **Mining Model** menu to correct the problem and run the query again.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40512-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="40512-116">See Also</span></span>  
 <span data-ttu-id="40512-117">[Data Mining-Abfragen](data-mining-queries.md) </span><span class="sxs-lookup"><span data-stu-id="40512-117">[Data Mining Queries](data-mining-queries.md) </span></span>  
 <span data-ttu-id="40512-118">[Vorhersage Abfrage-Generator &#40;Data Mining-&#41;](../prediction-query-builder-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="40512-118">[Prediction Query Builder &#40;Data Mining&#41;](../prediction-query-builder-data-mining.md) </span></span>  
 [<span data-ttu-id="40512-119">Lektion 6: Erstellen und Verwenden von Vorhersagen &#40;Tutorial zu Data Mining-Grundlagen&#41;</span><span class="sxs-lookup"><span data-stu-id="40512-119">Lesson 6: Creating and Working with Predictions &#40;Basic Data Mining Tutorial&#41;</span></span>](../../tutorials/lesson-6-creating-and-working-with-predictions-basic-data-mining-tutorial.md)  
  
  
