---
title: Anzeigen und Speichern der Ergebnisse einer Vorhersage Abfrage | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- prediction queries [Analysis Services]
- viewing prediction query results
- displaying prediction query results
- Mining Model Prediction [Analysis Services], viewing results
ms.assetid: abba4d24-3619-44c1-8279-88f27ad627d3
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6da4b515c4280969f665dba2cf5bee5281df0a00
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616820"
---
# <a name="view-and-save-the-results-of-a-prediction-query"></a><span data-ttu-id="54a9d-102">Anzeigen und Speichern der Ergebnisse einer Vorhersageabfrage</span><span class="sxs-lookup"><span data-stu-id="54a9d-102">View and Save the Results of a Prediction Query</span></span>
  <span data-ttu-id="54a9d-103">Nachdem Sie [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] mithilfe von Vorhersage Abfrage-Generator eine Abfrage in definiert haben, können Sie die Abfrage ausführen und die Ergebnisse anzeigen, indem Sie zur Abfrageergebnis Sicht wechseln.</span><span class="sxs-lookup"><span data-stu-id="54a9d-103">After you have defined a query in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] by using Prediction Query Builder, you can run the query and view the results by switching to the query result view.</span></span>  
  
 <span data-ttu-id="54a9d-104">Sie können die Ergebnisse einer Vorhersage Abfrage in einer Tabelle in jeder Datenquelle speichern, die in einem Projekt definiert ist [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="54a9d-104">You can save the results of a prediction query to a table in any data source that is defined in a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span> <span data-ttu-id="54a9d-105">Sie können dabei entweder eine neue Tabelle erstellen oder die Abfrageergebnisse in einer bereits vorhandenen Tabelle speichern.</span><span class="sxs-lookup"><span data-stu-id="54a9d-105">You can either create a new table or save the query results to an existing table.</span></span> <span data-ttu-id="54a9d-106">Wenn Sie die Ergebnisse in einer vorhandenen Tabelle speichern, können Sie entweder die aktuell in der Tabelle gespeicherten Daten überschreiben lassen. Ansonsten werden die Abfrageergebnisse an die vorhandenen Daten in der Tabelle angehängt.</span><span class="sxs-lookup"><span data-stu-id="54a9d-106">If you save the results to an existing table, you can choose to overwrite the data that is currently stored in the table; otherwise, the query results are appended to the existing data in the table.</span></span>  
  
### <a name="run-a-query-and-view-the-results"></a><span data-ttu-id="54a9d-107">Ausführen von Abfragen und Anzeigen von Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="54a9d-107">Run a query and view the results</span></span>  
  
1.  <span data-ttu-id="54a9d-108">Klicken Sie auf der Symbolleiste der Registerkarte **Miningmodellvorhersage** im Data Mining-Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]auf **Ergebnis** .</span><span class="sxs-lookup"><span data-stu-id="54a9d-108">On the toolbar of the **Mining Model Prediction** tab of Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], click **Result** .</span></span>  
  
     <span data-ttu-id="54a9d-109">Die Abfrageergebnissicht wird geöffnet, und die Abfrage wird ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="54a9d-109">The query results view opens and runs the query.</span></span> <span data-ttu-id="54a9d-110">Die Ergebnisse werden im Viewer in einem Raster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="54a9d-110">The results are displayed in a grid in the viewer.</span></span>  
  
### <a name="save-the-results-of-a-prediction-query-to-a-table"></a><span data-ttu-id="54a9d-111">Speichern der Ergebnisse einer Vorhersageabfrage in einer Tabelle</span><span class="sxs-lookup"><span data-stu-id="54a9d-111">Save the results of a prediction query to a table</span></span>  
  
1.  <span data-ttu-id="54a9d-112">Klicken Sie auf der Symbolleiste der Registerkarte **Miningmodellvorhersage** im Data Mining-Designer auf **Abfrageergebnis speichern**.</span><span class="sxs-lookup"><span data-stu-id="54a9d-112">On the toolbar of the **Mining Model Prediction** tab in Data Mining Designer, click **Save query result**.</span></span>  
  
     <span data-ttu-id="54a9d-113">Das Dialogfeld **Ergebnis der Data Mining-Abfrage speichern** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="54a9d-113">The **Save Data Mining Query Result** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="54a9d-114">Wählen Sie aus der **Datenquelle** -Liste eine Datenquelle aus, oder klicken Sie auf **Neu** , um eine neue Datenquelle zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="54a9d-114">Select a data source from the **Data Source** list, or click **New** to create a new data source.</span></span>  
  
3.  <span data-ttu-id="54a9d-115">Geben Sie im Feld **Tabellenname** den Namen der Tabelle ein.</span><span class="sxs-lookup"><span data-stu-id="54a9d-115">In the **Table Name** box, enter the name of the table.</span></span> <span data-ttu-id="54a9d-116">Wenn die Tabelle bereits vorhanden ist, können Sie das Kontrollkästchen **Überschreiben, falls vorhanden** aktivieren, um den bisherigen Inhalt der Tabelle mit den Abfrageergebnissen zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="54a9d-116">If the table already exists, select **Overwrite if exists** to replace the contents of the table with the query results.</span></span> <span data-ttu-id="54a9d-117">Wenn der Inhalt der Tabelle nicht überschrieben werden soll, dürfen Sie dieses Kontrollkästchen nicht aktivieren.</span><span class="sxs-lookup"><span data-stu-id="54a9d-117">If you do not want to overwrite the contents of the table, do not select this check box.</span></span> <span data-ttu-id="54a9d-118">Die neuen Abfrageergebnisse werden dann an die in der Tabelle vorhandenen Daten angehängt.</span><span class="sxs-lookup"><span data-stu-id="54a9d-118">The new query results will be appended to the existing data in the table.</span></span>  
  
4.  <span data-ttu-id="54a9d-119">Wählen Sie unter **Zur Datenquellensicht hinzufügen** , wenn Sie die Tabelle zu einer Datenquellensicht hinzufügen wollen.</span><span class="sxs-lookup"><span data-stu-id="54a9d-119">Select a data source view from **Add to DSV** if you want to add the table to a data source view.</span></span>  
  
5.  <span data-ttu-id="54a9d-120">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="54a9d-120">Click **Save**.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="54a9d-121">Wenn das Ziel keine hierarchischen Rowsets unterstützt, können Sie den Ergebnissen das FALTTENED-Schlüsselwort hinzufügen, um es als flache Tabelle zu speichern.</span><span class="sxs-lookup"><span data-stu-id="54a9d-121">If the destination does not support hierarchical rowsets, you can add the FALTTENED keyword to the results to save as a flat table.</span></span>  
  
  
