---
title: Durchsuchen von Daten in einer Datenquellen Sicht (Analysis Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- exploring data [Analysis Services]
- data source views [Analysis Services], exploring data
- viewing source data
ms.assetid: 2c922c35-fbcb-45b2-96b1-c7a846d8b419
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6adf9edecd807158ba1d0de3287cccd6fa8dd787
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622907"
---
# <a name="explore-data-in-a-data-source-view-analysis-services"></a><span data-ttu-id="f503b-102">Durchsuchen von Daten in einer Datenquellensicht (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="f503b-102">Explore Data in a Data Source View (Analysis Services)</span></span>
  <span data-ttu-id="f503b-103">Sie können das Dialogfeld **Daten durchsuchen** im Datenquellensicht-Designer von [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] verwenden, um Daten für eine Tabelle, eine Sicht oder eine benannte Abfrage in einer Datenquellensicht (data source view; DSV) zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="f503b-103">You can use the **Explore Data** dialog box in Data Source View Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] to browse data for a table, view, or named query in a data source view (DSV).</span></span> <span data-ttu-id="f503b-104">Wenn Sie die Daten im Datenquellensicht-Designer durchsuchen, können Sie den Inhalt jeder Datenspalte in einer ausgewählten Tabelle, Sicht oder benannten Abfrage anzeigen.</span><span class="sxs-lookup"><span data-stu-id="f503b-104">When you explore the data in Data Source View Designer, you can view the contents of each column of data in a selected table, view, or named query.</span></span> <span data-ttu-id="f503b-105">Das Anzeigen des tatsächlichen Inhalts hilft Ihnen, zu bestimmen, ob alle Spalten benötigt werden, ob benannte Berechnungen erforderlich sind, um Benutzerfreundlichkeit und Zweckmäßigkeit zu erhöhen, und ob vorhandene benannte Berechnungen oder benannte Abfragen die erwarteten Werte zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="f503b-105">Viewing the actual contents assists you in determining whether all columns are needed, if named calculations are required to increase user friendliness and usability, and whether existing named calculations or named queries return the anticipated values.</span></span>  
  
 <span data-ttu-id="f503b-106">Zum Anzeigen von Daten müssen Sie über eine aktive Verbindung mit der Datenquelle bzw. den Datenquellen für das ausgewählte Objekt in der Datenquellensicht verfügen.</span><span class="sxs-lookup"><span data-stu-id="f503b-106">To view data, you must have an active connection to the data source or sources for the selected object in the DSV.</span></span> <span data-ttu-id="f503b-107">Alle benannten Berechnungen in einer Tabelle werden ebenfalls in der Abfrage gesendet.</span><span class="sxs-lookup"><span data-stu-id="f503b-107">Any named calculations in a table are also sent in the query.</span></span>  
  
 <span data-ttu-id="f503b-108">Die in einem tabellarischen Format zurückgegebenen Daten, die sortiert und kopiert werden können.</span><span class="sxs-lookup"><span data-stu-id="f503b-108">The data returned in a tabular format that you can sort and copy.</span></span> <span data-ttu-id="f503b-109">Klicken Sie auf die Spaltenüberschriften, um die Zeilen nach dieser Spalte erneut zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="f503b-109">Click on the column headers to re-sort the rows by that column.</span></span> <span data-ttu-id="f503b-110">Sie können auch Daten im Raster hervorheben und STRG+C drücken, um die Auswahl in die Zwischenablage zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="f503b-110">You can also highlight data in the grid and press Ctrl-C to copy the selection to the clipboard.</span></span>  
  
 <span data-ttu-id="f503b-111">Sie können zudem die Stichprobenmethode und die Anzahl für die Stichprobe steuern.</span><span class="sxs-lookup"><span data-stu-id="f503b-111">You can also control the sample method and the sample count.</span></span> <span data-ttu-id="f503b-112">Standardmäßig werden die obersten 5000 Zeilen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f503b-112">By default, the top 5000 rows are returned.</span></span>  
  
## <a name="to-browse-data-or-change-sampling-options"></a><span data-ttu-id="f503b-113">So durchsuchen Sie Daten oder ändern Stichprobenoptionen</span><span class="sxs-lookup"><span data-stu-id="f503b-113">To browse data or change sampling options</span></span>  
  
1.  <span data-ttu-id="f503b-114">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]das Projekt, oder stellen Sie eine Verbindung mit der Datenbank her, das bzw. die die Datenquellensicht enthält, in der Sie Daten durchsuchen möchten.</span><span class="sxs-lookup"><span data-stu-id="f503b-114">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the project or connect to the database that contains the data source view in which you want to browse data.</span></span>  
  
2.  <span data-ttu-id="f503b-115">Erweitern Sie im Projektmappen-Explorer den Ordner **Datenquellensichten** , und doppelklicken Sie anschließend auf die Datenquellensicht.</span><span class="sxs-lookup"><span data-stu-id="f503b-115">In Solution Explorer, expand the **Data Source Views** folder, and then double-click the data source view.</span></span>  
  
3.  <span data-ttu-id="f503b-116">Klicken Sie mit der rechten Maustaste auf die Tabelle, Sicht oder benannte Abfrage, die die anzuzeigenden Daten enthält, und klicken Sie anschließend auf **Daten durchsuchen**.</span><span class="sxs-lookup"><span data-stu-id="f503b-116">Right-click the table, view, or named query that contains the data you want to view, and then click **Explore Data**.</span></span>  
  
     <span data-ttu-id="f503b-117">Die Datenquelle, die der Tabelle, Sicht oder benannten Abfrage in der Datenquellen Sicht zugrunde liegt, sind Abfragen, und die Ergebnisse werden auf der Registerkarte \*\* \<object name> Tabelle durchsuchen\*\* angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f503b-117">The data source underlying the table, view, or named query in the data source view are queries, and the results appear in the **Explore \<object name> Table** tab.</span></span>  
  
4.  <span data-ttu-id="f503b-118">Klicken Sie auf der Symbolleiste \*\* \<object name> Tabelle durchsuchen\*\* auf das Symbol **Stichproben Optionen** .</span><span class="sxs-lookup"><span data-stu-id="f503b-118">On the **Explore \<object name> Table** toolbar, click the **Sampling options** icon.</span></span>  
  
     <span data-ttu-id="f503b-119">Das Dialogfeld **Optionen zum Durchsuchen von Daten** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="f503b-119">The **Data Exploration Options** dialog box opens.</span></span> <span data-ttu-id="f503b-120">In diesem Dialogfeld können Sie die Stichprobenmethode (mehr oder weniger Datensätze als die Standardstichprobengröße von 5000 Zeilen) oder die Anzahl für die Stichprobe angeben.</span><span class="sxs-lookup"><span data-stu-id="f503b-120">In this dialog box you can specify the sampling method (fewer or more records than the default sampling size of 5000 rows), or sample count.</span></span>  
  
5.  <span data-ttu-id="f503b-121">Klicken Sie nach Bedarf auf **OK** oder **Abbrechen** .</span><span class="sxs-lookup"><span data-stu-id="f503b-121">Click **OK** or **Cancel** as appropriate.</span></span>  
  
6.  <span data-ttu-id="f503b-122">Um die Daten neu zu überprüfen, klicken Sie auf der Symbolleiste der \*\* \<object name> Tabelle\*\* auf " **Daten neu Sample** ".</span><span class="sxs-lookup"><span data-stu-id="f503b-122">To resample the data, click **Resample Data** on the **Explore \<object name> Table** toolbar.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f503b-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f503b-123">See Also</span></span>  
 [<span data-ttu-id="f503b-124">Datenquellsichten in mehrdimensionalen Modellen</span><span class="sxs-lookup"><span data-stu-id="f503b-124">Data Source Views in Multidimensional Models</span></span>](data-source-views-in-multidimensional-models.md)  
  
  
