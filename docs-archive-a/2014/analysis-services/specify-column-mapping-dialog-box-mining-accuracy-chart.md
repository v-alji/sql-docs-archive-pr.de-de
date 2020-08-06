---
title: Spalten Zuordnung angeben (Dialog Feld) (Mining Genauigkeits Diagramm) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.accuracychart.coltotablecolmapping.f1
ms.assetid: 68e9e2d2-173f-4363-a515-fc60bfee3af0
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8ede835567f678f4152b3d1944f3c2c7160c6837
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620565"
---
# <a name="specify-column-mapping-dialog-box-mining-accuracy-chart"></a><span data-ttu-id="c530e-102">Spaltenzuordnung angeben (Dialogfeld, Mininggenauigkeitsdiagramm)</span><span class="sxs-lookup"><span data-stu-id="c530e-102">Specify Column Mapping Dialog Box (Mining Accuracy Chart)</span></span>
  <span data-ttu-id="c530e-103">Auf der Registerkarte **Spaltenzuordnung angeben** können Sie Tabellen aus einer externen Datenquelle auswählen und die Spalten einem Data Mining-Modell zuordnen.</span><span class="sxs-lookup"><span data-stu-id="c530e-103">Use the **Specify Column Mapping** tab to select tables from an external data source and map the columns to a data mining model.</span></span> <span data-ttu-id="c530e-104">Mithilfe der externen Daten können Sie dann die Genauigkeit eines Miningmodells testen und die Ergebnisse im Genauigkeitsdiagramm anzeigen.</span><span class="sxs-lookup"><span data-stu-id="c530e-104">You can then use the external data to test the accuracy of a mining model and displays the results in the accuracy chart.</span></span>  
  
 <span data-ttu-id="c530e-105">**Weitere Informationen:** [Tests und Überprüfung &#40;Data Mining&#41;](data-mining/testing-and-validation-data-mining.md)</span><span class="sxs-lookup"><span data-stu-id="c530e-105">**For more information:** [Testing and Validation &#40;Data Mining&#41;](data-mining/testing-and-validation-data-mining.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="c530e-106">Tastatur</span><span class="sxs-lookup"><span data-stu-id="c530e-106">Options</span></span>  
 <span data-ttu-id="c530e-107">**Miningstruktur**</span><span class="sxs-lookup"><span data-stu-id="c530e-107">**Mining Structure**</span></span>  
 <span data-ttu-id="c530e-108">Zeigt die ausgewählte Miningstruktur mit dem zu testenden Modell an.</span><span class="sxs-lookup"><span data-stu-id="c530e-108">Displays the selected mining structure that contains the model that you will test.</span></span>  
  
 <span data-ttu-id="c530e-109">**Struktur auswählen**</span><span class="sxs-lookup"><span data-stu-id="c530e-109">**Select Structure**</span></span>  
 <span data-ttu-id="c530e-110">Klicken Sie auf diese Option, um das Dialogfeld **Miningstruktur auswählen** zu öffnen und eine andere Miningstruktur auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="c530e-110">Click to open the **Select Mining Structure** dialog box and select a different mining structure.</span></span>  
  
 <span data-ttu-id="c530e-111">**Eingabetabelle(n) auswählen**</span><span class="sxs-lookup"><span data-stu-id="c530e-111">**Select Input Table(s)**</span></span>  
 <span data-ttu-id="c530e-112">Zeigt die zum Generieren des Prognosegütediagramms ausgewählten Eingabetabellen an.</span><span class="sxs-lookup"><span data-stu-id="c530e-112">Displays the selected input tables that are used to generate the lift chart.</span></span> <span data-ttu-id="c530e-113">Wählen Sie die Tabelle mit den Testdaten aus, die Sie zum Testen der Genauigkeit des Modells verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="c530e-113">Select the table that contains the test data that you will use to test the accuracy of the models.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c530e-114"> Klicken Sie auf **Falltabelle auswählen** , wenn der Bereich keine Tabellen enthält, um Tabellen aus einer Datenquellensicht hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="c530e-114">If the pane does not contain any tables, click **Select Case Table** to add tables from a data source view.</span></span>  
  
 <span data-ttu-id="c530e-115">**Tabelle entfernen**</span><span class="sxs-lookup"><span data-stu-id="c530e-115">**Remove Table**</span></span>  
 <span data-ttu-id="c530e-116">Entfernt die ausgewählte Tabelle.</span><span class="sxs-lookup"><span data-stu-id="c530e-116">Removes the selected table.</span></span> <span data-ttu-id="c530e-117">Diese Schaltfläche ist deaktiviert, wenn keine Tabelle ausgewählt wurde oder in der Liste **Eingabetabelle(n) auswählen** keine Tabellen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c530e-117">This button is disabled if a table has not been selected or if no tables are displayed in the **Select Input Tables** list.</span></span>  
  
 <span data-ttu-id="c530e-118">**Falltabelle auswählen**</span><span class="sxs-lookup"><span data-stu-id="c530e-118">**Select Case Table**</span></span>  
 <span data-ttu-id="c530e-119">Klicken Sie auf diese Option, um das Dialogfeld **Tabelle auswählen** zu öffnen und eine Datenquellensicht auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="c530e-119">Click to open the **Select Table** dialog box and select a data source view.</span></span>  
  
 <span data-ttu-id="c530e-120">**Hinweis** Diese Schaltfläche wird nur angezeigt, wenn noch keine Falltabelle ausgewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="c530e-120">**Note** This button appears only if a case table has not been selected.</span></span> <span data-ttu-id="c530e-121">Löschen Sie die Liste, indem Sie alle vorhandenen Tabellen auswählen und anschließend auf **Tabelle entfernen**klicken, um die Schaltfläche zu aktivieren und eine andere Falltabelle auswählen zu können.</span><span class="sxs-lookup"><span data-stu-id="c530e-121">To enable the button so that you can select a different case table, clear the list by selecting all existing tables and then clicking **Remove Table**.</span></span>  
  
 <span data-ttu-id="c530e-122">**Geschachtelte Tabelle auswählen**</span><span class="sxs-lookup"><span data-stu-id="c530e-122">**Select Nested Table**</span></span>  
 <span data-ttu-id="c530e-123">Öffnet das Dialogfeld **Tabelle auswählen** .</span><span class="sxs-lookup"><span data-stu-id="c530e-123">Opens the **Select Table** dialog box.</span></span> <span data-ttu-id="c530e-124">Diese Schaltfläche wird nur angezeigt, wenn eine Falltabelle ausgewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="c530e-124">This button appears only if a case table has been selected.</span></span> <span data-ttu-id="c530e-125">Wenn die entsprechende Miningstruktur keine geschachtelte Tabelle enthält, ist diese Schaltfläche deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="c530e-125">If the associated mining structure does not contain a nested table, this button is disabled.</span></span>  
  
 <span data-ttu-id="c530e-126">**Join ändern**</span><span class="sxs-lookup"><span data-stu-id="c530e-126">**Modify Join**</span></span>  
 <span data-ttu-id="c530e-127">Öffnet das Dialogfeld **Geschachtelten Join angeben** .</span><span class="sxs-lookup"><span data-stu-id="c530e-127">Opens the **Specify Nested Join** dialog box.</span></span> <span data-ttu-id="c530e-128">Diese Schaltfläche ist nur aktiviert, wenn eine geschachtelte Tabelle ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="c530e-128">This button is active only if the nested table is selected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c530e-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c530e-129">See Also</span></span>  
 <span data-ttu-id="c530e-130">[Test-und validierungsaufgaben und Anleitungen &#40;Data Mining-&#41;](data-mining/testing-and-validation-tasks-and-how-tos-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="c530e-130">[Testing and Validation Tasks and How-tos &#40;Data Mining&#41;](data-mining/testing-and-validation-tasks-and-how-tos-data-mining.md) </span></span>  
 [<span data-ttu-id="c530e-131">Mining Genauigkeits Diagramm-Designer &#40;Data Mining-&#41;</span><span class="sxs-lookup"><span data-stu-id="c530e-131">Mining Accuracy Chart Designer &#40;Data Mining&#41;</span></span>](mining-accuracy-chart-designer-data-mining.md)  
  
  
