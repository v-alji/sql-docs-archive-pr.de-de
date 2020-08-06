---
title: Umgehen der Excel-Zeilen Einschränkung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a4c8700b-bef5-4440-a99c-bba5dcc46bfd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 128f65cf09833d23234da10bf7744c6ce30065ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615312"
---
# <a name="work-around-the-excel-row-limitation"></a><span data-ttu-id="25275-102">Umgehung der Zeilenbeschränkung in Excel</span><span class="sxs-lookup"><span data-stu-id="25275-102">Work Around the Excel Row Limitation</span></span>
  <span data-ttu-id="25275-103">In diesem Thema wird erläutert, wie Sie beim Exportieren von Berichten nach Excel die Zeilenbeschränkung von Excel 2003 umgehen.</span><span class="sxs-lookup"><span data-stu-id="25275-103">This topic explains how to work around the Excel 2003 row limitation when you export reports to Excel.</span></span> <span data-ttu-id="25275-104">Die Problemumgehung bezieht sich auf einen Bericht, der nur eine Tabelle enthält.</span><span class="sxs-lookup"><span data-stu-id="25275-104">The workaround is for a report that contains only a table.</span></span>  
  
 <span data-ttu-id="25275-105">Excel 2003 unterstützt maximal 65.536 Zeilen pro Arbeitsblatt.</span><span class="sxs-lookup"><span data-stu-id="25275-105">Excel 2003 supports a maximum of 65,536 rows per worksheet.</span></span> <span data-ttu-id="25275-106">Sie können diese Einschränkung umgehen, indem Sie nach einer bestimmten Anzahl von Zeilen einen expliziten Seitenumbruch erzwingen.</span><span class="sxs-lookup"><span data-stu-id="25275-106">You can work around this limitation by forcing an explicit page break after a certain number of rows.</span></span> <span data-ttu-id="25275-107">Der Excel-Renderer erstellt bei jedem expliziten Seitenumbruch ein neues Arbeitsblatt.</span><span class="sxs-lookup"><span data-stu-id="25275-107">The Excel renderer creates a new worksheet for each explicit page break.</span></span>  
  
### <a name="to-create-an-explicit-page-break"></a><span data-ttu-id="25275-108">So erstellen Sie einen expliziten Seitenumbruch</span><span class="sxs-lookup"><span data-stu-id="25275-108">To create an explicit page break</span></span>  
  
1.  <span data-ttu-id="25275-109">Öffnen Sie den Bericht in [!INCLUDE[ss_dtbi](../../includes/ss-dtbi-md.md)] oder im Berichts-Manager.</span><span class="sxs-lookup"><span data-stu-id="25275-109">Open the report in [!INCLUDE[ss_dtbi](../../includes/ss-dtbi-md.md)] or Report Manager.</span></span>  
  
2.  <span data-ttu-id="25275-110">Klicken Sie mit der rechten Maustaste auf die Daten Zeile in der Tabelle, und klicken Sie dann auf übergeordnete Gruppe der **Gruppe hinzufügen**,  >  **Parent Group** um eine äußere Tabellen Gruppe</span><span class="sxs-lookup"><span data-stu-id="25275-110">Right click the Data row in the table, and then click **Add Group** > **Parent Group** to add an outer table group.</span></span>  
  
     <span data-ttu-id="25275-111">![Auswählen der übergeordneten Gruppe](../media/datarow-selectparentgroup.png "Auswählen der übergeordneten Gruppe")</span><span class="sxs-lookup"><span data-stu-id="25275-111">![Select the Parent Group](../media/datarow-selectparentgroup.png "Select the Parent Group")</span></span>  
  
3.  <span data-ttu-id="25275-112">Geben Sie die folgende Formel im Ausdrucksfeld **Gruppieren nach** ein, und klicken Sie dann auf **OK** , um die übergeordnete Gruppe hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="25275-112">Enter the following formula in the **Group by** expression box, and then click **OK** to add the parent group.</span></span>  
  
     <span data-ttu-id="25275-113">=Int((RowNumber(Nothing)-1)/65000)</span><span class="sxs-lookup"><span data-stu-id="25275-113">=Int((RowNumber(Nothing)-1)/65000)</span></span>  
  
     <span data-ttu-id="25275-114">Durch die Formel wird jedem im Dataset enthaltenen Satz von 65.000 Zeilen eine Zahl zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="25275-114">The formula assigns a number to each set of 65000 rows in the dataset.</span></span> <span data-ttu-id="25275-115">Wenn ein Seitenumbruch für die Gruppe definiert ist, führt dieser Ausdruck alle 65.000 Zeilen zu einem Seitenumbruch.</span><span class="sxs-lookup"><span data-stu-id="25275-115">When a page break is defined for the group, the expression results in a page break every 65000 rows.</span></span>  
  
     <span data-ttu-id="25275-116">Durch das Hinzufügen der äußeren Tabellengruppe wird dem Bericht eine Gruppenspalte hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="25275-116">Adding the outer table group adds a group column to the report.</span></span>  
  
4.  <span data-ttu-id="25275-117">Löschen Sie die Gruppenspalte, indem Sie mit der rechten Maustaste auf die Spaltenüberschrift klicken, auf **Spalten löschen**klicken, **Nur Spalten löschen**auswählen und anschließend auf **OK**klicken.</span><span class="sxs-lookup"><span data-stu-id="25275-117">Delete the group column by right-clicking on the column header, clicking **Delete Columns**, selecting **Delete columns only**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="25275-118">![Löschen einer Gruppenspalte](../media/groupcolumn-delete-updated.png "Löschen einer Gruppenspalte")</span><span class="sxs-lookup"><span data-stu-id="25275-118">![Delete a group column](../media/groupcolumn-delete-updated.png "Delete a group column")</span></span>  
  
5.  <span data-ttu-id="25275-119">Klicken Sie mit der rechten Maustaste im Bereich **Zeilengruppen** auf **Gruppe 1** , und klicken Sie dann auf **Gruppeneigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="25275-119">Right click **Group 1** in the **Row Groups** section, and then click **Group Properties**.</span></span>  
  
     <span data-ttu-id="25275-120">![Anzeigen von Gruppeneigenschaften](../media/groupproperties-updated.png "Anzeigen von Gruppeneigenschaften")</span><span class="sxs-lookup"><span data-stu-id="25275-120">![View group properties](../media/groupproperties-updated.png "View group properties")</span></span>  
  
6.  <span data-ttu-id="25275-121">Wählen Sie im Dialogfeld **Gruppeneigenschaften** auf der Seite **Sortierung** die Standardsortierungsoption aus, und klicken Sie auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="25275-121">On the **Sorting** page of the **Group Properties** dialog box, select the default sorting option and click **Delete**.</span></span>  
  
     <span data-ttu-id="25275-122">![Löschen der Standardsortierung](../media/groupproperties-sorting-updated.png "Löschen der Standardsortierung")</span><span class="sxs-lookup"><span data-stu-id="25275-122">![Delete default sorting](../media/groupproperties-sorting-updated.png "Delete default sorting")</span></span>  
  
7.  <span data-ttu-id="25275-123">Klicken Sie auf der Seite **Seitenumbrüche** auf **Zwischen den einzelnen Instanzen einer Gruppe** , und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="25275-123">On the **Page Breaks** page, click **Between each instance of a group** and then click **OK**.</span></span>  
  
     <span data-ttu-id="25275-124">![Festlegen von Seitenumbrüchen](../media/groupproperties-pagebreaks-updated.png "Festlegen von Seitenumbrüchen")</span><span class="sxs-lookup"><span data-stu-id="25275-124">![Set page breaks](../media/groupproperties-pagebreaks-updated.png "Set page breaks")</span></span>  
  
8.  <span data-ttu-id="25275-125">Speichern Sie den Bericht.</span><span class="sxs-lookup"><span data-stu-id="25275-125">Save the report.</span></span> <span data-ttu-id="25275-126">Beim Exportieren des Berichts nach Excel wird dieser in mehrere Arbeitsblätter exportiert. Jedes Arbeitsblatt enthält maximal 65.000 Zeilen.</span><span class="sxs-lookup"><span data-stu-id="25275-126">When you export it to Excel, it exports to multiple worksheets and each worksheet contains a maximum of 65000 rows.</span></span>  
  
  
