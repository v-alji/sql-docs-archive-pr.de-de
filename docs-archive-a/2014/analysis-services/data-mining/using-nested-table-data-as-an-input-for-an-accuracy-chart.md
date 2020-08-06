---
title: Verwenden von Daten in einer Datentabelle als Eingabe für ein Genauigkeits Diagramm | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Mining Accuracy Chart [Analysis Services], nested tables
- Mining Accuracy Chart [Analysis Services], input tables
- nested tables
- adding nested tables
ms.assetid: 162e0686-ada3-4dd3-9151-9589926e6613
author: minewiskan
ms.author: owend
ms.openlocfilehash: 97d5bbd75d09b1a9e4276c4723ad6986dbabf9e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608078"
---
# <a name="using-nested-table-data-as-an-input-for-an-accuracy-chart"></a><span data-ttu-id="bb2a1-102">Verwenden von geschachtelten Tabellendaten als Eingabe für ein Genauigkeitsdiagramm</span><span class="sxs-lookup"><span data-stu-id="bb2a1-102">Using Nested Table Data as an Input for an Accuracy Chart</span></span>
  <span data-ttu-id="bb2a1-103">Wenn Sie zum Testen der Genauigkeit eines Miningmodells externe Daten verwenden und das Miningmodell geschachtelte Tabellen enthält, müssen die externen Daten auch eine Falltabelle und eine verbundene geschachtelte Tabelle enthalten.</span><span class="sxs-lookup"><span data-stu-id="bb2a1-103">When you test the accuracy of a mining model by using external data, if the mining model contains nested tables, the external data must also contain a case table and an associated nested table.</span></span>  
  
 <span data-ttu-id="bb2a1-104">In diesem Thema wird beschrieben, wie Sie mit für Modelltests verwendeten geschachtelten Tabellen arbeiten, wie Sie geschachtelte Tabellen und Falltabellen im Modus zuordnen und wie Sie einen Filter auf eine geschachtelte Tabelle anwenden.</span><span class="sxs-lookup"><span data-stu-id="bb2a1-104">This topic describes how to work with nested tables used for model testing, how to map nested and case tables in the mode and in the external data, and how to apply a filter to a nested table.</span></span>  
  
 <span data-ttu-id="bb2a1-105">Wenn Sie mit geschachtelten Tabellen arbeiten, denken Sie an folgende Tipps:</span><span class="sxs-lookup"><span data-stu-id="bb2a1-105">When working with nested tables, keep in mind these tips:</span></span>  
  
-   <span data-ttu-id="bb2a1-106">Wenn Sie die Option **Testfälle für Miningmodell verwenden** oder **Testfälle für Miningstruktur verwenden**auswählen, muss keine Falltabelle oder geschachtelte Tabelle angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="bb2a1-106">If you select the option **Use mining model test cases** or **Use mining structure test cases**, you do not need to specify a case table or nested table.</span></span> <span data-ttu-id="bb2a1-107">Mit diesen Optionen wird die Definition der Testdaten in der Miningstruktur gespeichert, und die Testdaten werden automatisch ausgewählt, wenn Sie das Genauigkeitsdiagramm erstellen.</span><span class="sxs-lookup"><span data-stu-id="bb2a1-107">With those options, the definition of the test data is stored in the mining structure and the test data is automatically selected when you create the accuracy chart.</span></span>  
  
-   <span data-ttu-id="bb2a1-108">Falls bereits eine Beziehung zwischen der Falltabelle und der geschachtelten Tabelle in der Datenquelle besteht, werden die Spalten der Miningstruktur automatisch den gleichnamigen Spalten der Eingabetabelle zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="bb2a1-108">If a relationship already exists between the case and nested table in the data source, the columns in the mining structure are automatically mapped to the columns that have the same name in the input table.</span></span>  
  
-   <span data-ttu-id="bb2a1-109">Sie können erst eine geschachtelte Tabelle auswählen, nachdem Sie die Falltabelle angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="bb2a1-109">You cannot select a nested table until you have specified the case table.</span></span> <span data-ttu-id="bb2a1-110">Außerdem können Sie nur dann eine geschachtelte Tabelle als Eingabe angeben, wenn das Miningmodell eine Falltabelle und eine geschachtelte Tabellenstruktur verwendet.</span><span class="sxs-lookup"><span data-stu-id="bb2a1-110">Also, you cannot specify a nested table as an input unless the mining model also uses a case table and nested table structure.</span></span>  
  
### <a name="use-a-nested-table-as-input-to-an-accuracy-chart"></a><span data-ttu-id="bb2a1-111">Verwenden einer geschachtelten Tabelle als Eingabe für ein Genauigkeitsdiagramm</span><span class="sxs-lookup"><span data-stu-id="bb2a1-111">Use a nested table as input to an accuracy chart</span></span>  
  
1.  <span data-ttu-id="bb2a1-112">Doppelklicken Sie auf die Miningstruktur, um sie in Data Mining-Designer zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="bb2a1-112">Double-click the mining structure to open it in Data Mining Designer.</span></span>  
  
2.  <span data-ttu-id="bb2a1-113">Wählen Sie die Registerkarte **Mininggenauigkeitsdiagramm** und anschließend die Registerkarte **Eingabeauswahl** aus.</span><span class="sxs-lookup"><span data-stu-id="bb2a1-113">Select the **Mining Accuracy Chart** tab, and then select the **Input Selection** tab.</span></span>  
  
3.  <span data-ttu-id="bb2a1-114">Wählen Sie unter **Dataset auswählen, das für das Genauigkeitsdiagramm verwendet werden soll**die Option **Anderes Dataset verwenden**aus.</span><span class="sxs-lookup"><span data-stu-id="bb2a1-114">In **Select data set to be used for accuracy chart**, select the option **Specify a different data set**.</span></span>  
  
4.  <span data-ttu-id="bb2a1-115">Klicken Sie auf die Schaltfläche zum Durchsuchen **(...)** , um das externe DataSet aus einer Liste mit Datenquellen Sichten auf dem aktuellen Server auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="bb2a1-115">Click the browse button **(...)** to choose the external data set from a list of data source views on the current server.</span></span>  
  
5.  <span data-ttu-id="bb2a1-116">Klicken Sie auf **Falltabelle auswählen**.</span><span class="sxs-lookup"><span data-stu-id="bb2a1-116">Click **Select Case Table**.</span></span> <span data-ttu-id="bb2a1-117">Wählen Sie im Dialogfeld **Tabelle auswählen** in der Datenquellensicht die Tabelle aus, die die Falldaten enthält. Klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="bb2a1-117">In the **Select Table** dialog box, choose the table from the data source view that contains the case data, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="bb2a1-118">Klicken Sie auf **Geschachtelte Tabelle auswählen**.</span><span class="sxs-lookup"><span data-stu-id="bb2a1-118">Click **Select Nested Table**.</span></span> <span data-ttu-id="bb2a1-119">Wählen Sie im Dialogfeld **Tabelle auswählen** die Tabelle aus, die die geschachtelten Daten enthält. Klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="bb2a1-119">In the **Select Table** dialog box, select the table that contains the nested data, and then click **OK**.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="bb2a1-120">Wenn Sie die Beziehung zwischen der geschachtelten Tabelle und der Falltabelle ändern müssen, klicken Sie auf **Join ändern** , um das Dialogfeld **Beziehung erstellen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="bb2a1-120">If you need to modify the relationship between the nested table and the case table, click **Modify Join** to open the **Create Relationship** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb2a1-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bb2a1-121">See Also</span></span>  
 <span data-ttu-id="bb2a1-122">[Auswählen und Zuordnen von Modell Test Daten](choose-and-map-model-testing-data.md) </span><span class="sxs-lookup"><span data-stu-id="bb2a1-122">[Choose and Map Model Testing Data](choose-and-map-model-testing-data.md) </span></span>  
 [<span data-ttu-id="bb2a1-123">Anwenden von Filtern zum Modellieren von Testdaten</span><span class="sxs-lookup"><span data-stu-id="bb2a1-123">Apply Filters to Model Testing Data</span></span>](apply-filters-to-model-testing-data.md)  
  
  
