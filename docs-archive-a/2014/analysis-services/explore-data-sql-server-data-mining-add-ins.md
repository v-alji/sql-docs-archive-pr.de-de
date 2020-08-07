---
title: Durchsuchen von Daten (SQL Server Data Mining-Add-Ins) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data preparation
- histogram [data mining]
- data visualization
ms.assetid: 714845a9-4c27-461a-9ba3-149e1e818386
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2572c11e92dcf99dfa3adf661603e8f65f05116e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718874"
---
# <a name="explore-data-sql-server-data-mining-add-ins"></a><span data-ttu-id="94152-102">Daten durchsuchen (SQL Server Data Mining-Add-Ins)</span><span class="sxs-lookup"><span data-stu-id="94152-102">Explore Data (SQL Server Data Mining Add-ins)</span></span>
  <span data-ttu-id="94152-103">![Assistent zum Durchsuchen von Daten](media/dmc-explore.gif "Assistent zum Durchsuchen von Daten")</span><span class="sxs-lookup"><span data-stu-id="94152-103">![Explore Data wizard](media/dmc-explore.gif "Explore Data wizard")</span></span>  
  
 <span data-ttu-id="94152-104">Der Assistent zum durch **Suchen von Daten** hilft Ihnen, den Typ und die Menge der Daten in der Datentabelle zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="94152-104">The **Explore Data** wizard helps you understand the type and amount of data in your data table.</span></span> <span data-ttu-id="94152-105">Der Assistent stellt die Verteilung und Werte für die ausgewählten Spalten spaltenweise grafisch dar.</span><span class="sxs-lookup"><span data-stu-id="94152-105">The wizard graphs the distribution and values for the selected columns, one column at a time.</span></span> <span data-ttu-id="94152-106">Anschließend können Sie die Gruppierung der Daten versuchsweise ändern oder das Diagramm, in dem der Inhalt angezeigt wird, zur Überprüfung in eine Excel-Arbeitsmappe kopieren.</span><span class="sxs-lookup"><span data-stu-id="94152-106">You can then experiment with changing the way that data is grouped, or copy the chart that shows the content to an Excel workbook for review.</span></span>  
  
 <span data-ttu-id="94152-107">Wenn Ihre Daten fortlaufende numerische Daten enthalten, können Sie zwischen den folgenden beiden Ansichten wechseln:</span><span class="sxs-lookup"><span data-stu-id="94152-107">If your data contains continuous numeric data, you can toggle between these two views:</span></span>  
  
-   <span data-ttu-id="94152-108">**Liniendiagramm.**</span><span class="sxs-lookup"><span data-stu-id="94152-108">**Line graph.**</span></span> <span data-ttu-id="94152-109">Dieses Diagramm zeichnet die Datenwerte auf der X-Achse und die Anzahl der Fälle auf der y-Achse auf.</span><span class="sxs-lookup"><span data-stu-id="94152-109">This graph charts the data values on the X-axis and the number of cases on the y-axis.</span></span>  
  
-   <span data-ttu-id="94152-110">**Balkendiagramm.**</span><span class="sxs-lookup"><span data-stu-id="94152-110">**Bar chart.**</span></span> <span data-ttu-id="94152-111">Im Balkendiagramm werden die Werte nach der Anzahl von Fällen für jeden Wert gruppiert.</span><span class="sxs-lookup"><span data-stu-id="94152-111">This graph groups values by the number of cases for each value.</span></span>  
  
 <span data-ttu-id="94152-112">Wenn der Assistent Gruppen in den Daten findet, verwendet er die tatsächliche Verteilung der Datenwerte.</span><span class="sxs-lookup"><span data-stu-id="94152-112">When the wizard finds groups in the data, it uses the actual distribution of data values.</span></span> <span data-ttu-id="94152-113">Folglich werden im Balkendiagramm die numerischen Werte nicht in den typischen Ganzzahlunterteilungen auf den Achsen gruppiert (z. B. Zehner- oder Hundertergruppen).</span><span class="sxs-lookup"><span data-stu-id="94152-113">Therefore, the bar chart does not show typical whole-number numeric axis markers such as 10 or 100.</span></span> <span data-ttu-id="94152-114">Stattdessen können die im Balkendiagramm angezeigten Bereiche durch Zahlen wie 43521-55603 (für die Einkommensspalte) angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="94152-114">Instead, the ranges shown in the bar chart might be something like 43521-55603 (for the Income column).</span></span>  
  
 <span data-ttu-id="94152-115">Wenn Sie die Daten in anderen Bereichen gruppieren möchten, sollten Sie diese Unterteilung in Excel vornehmen, bevor Sie die Daten analysieren.</span><span class="sxs-lookup"><span data-stu-id="94152-115">If you want to group your data into other ranges, you should do this in Excel before analyzing the data.</span></span> <span data-ttu-id="94152-116">Oder Sie [können die Daten mithilfe des Assistenten zum](relabel-sql-server-data-mining-add-ins.md) neubezeichnen neu bezeichnen.</span><span class="sxs-lookup"><span data-stu-id="94152-116">Or, you can relabel the data by using the [Relabel](relabel-sql-server-data-mining-add-ins.md) wizard.</span></span>  
  
## <a name="using-the-explore-data-wizard"></a><span data-ttu-id="94152-117">Verwenden des Assistenten zum Durchsuchen von Daten</span><span class="sxs-lookup"><span data-stu-id="94152-117">Using the Explore Data Wizard</span></span>  
  
1.  <span data-ttu-id="94152-118">Klicken Sie im **Data Mining** -Menüband auf **Daten durchsuchen**.</span><span class="sxs-lookup"><span data-stu-id="94152-118">In the **Data Mining** ribbon, click **Explore Data**.</span></span>  
  
2.  <span data-ttu-id="94152-119">Wählen Sie im Dialogfeld **Quelle auswählen** die Tabelle oder den Zellen Bereich aus, der die Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="94152-119">In the **Select Source** dialog box, select the table or range of cells that contains your data.</span></span>  
  
3.  <span data-ttu-id="94152-120">Wählen Sie im Dialogfeld **Spalte auswählen** die zu analysierende Spalte aus den im Bereich angezeigten Beispiel Daten aus.</span><span class="sxs-lookup"><span data-stu-id="94152-120">In the **Select Column** dialog box, choose the column to analyze, from the sample data displayed in the pane.</span></span>  
  
4.  <span data-ttu-id="94152-121">Wählen Sie im Dialogfeld **Daten durchsuchen** die Diagrammtypen für die Anzeige der Datenverteilung aus.</span><span class="sxs-lookup"><span data-stu-id="94152-121">In the **Explore Data** dialog box, choose the chart types for displaying the distribution of data.</span></span>  
  
5.  <span data-ttu-id="94152-122">Sie können optional auch neue Spalten zu den Daten hinzufügen, die Segmentierung der Daten ändern oder das Diagramm in Excel kopieren.</span><span class="sxs-lookup"><span data-stu-id="94152-122">Optionally, you can add new columns to the data, change the way that the data is segmented, or copy the chart to Excel.</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="94152-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="94152-123">Requirements</span></span>  
 <span data-ttu-id="94152-124">Wenn Sie den Assistenten zum durch **Suchen von Daten** verwenden möchten, müssen sich die Daten in einer Excel-Datentabelle befinden.</span><span class="sxs-lookup"><span data-stu-id="94152-124">To use the **Explore Data** wizard, your data must be in an Excel data table.</span></span>   
  
## <a name="see-also"></a><span data-ttu-id="94152-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="94152-125">See Also</span></span>  
 [<span data-ttu-id="94152-126">Prüfliste der Vorbereitung für Data Mining</span><span class="sxs-lookup"><span data-stu-id="94152-126">Checklist of Preparation for Data Mining</span></span>](checklist-of-preparation-for-data-mining.md)  
  
  
