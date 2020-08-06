---
title: 'Aufgabe 9: Hinzufügen der Transformation für Union all zum kombinieren richtiger und korrigierter Datensätze | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 24ba466d-a7d3-49e7-9111-b348399c9e58
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 83afb5ea9367660048fe36d00ab59d808da17b81
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726362"
---
# <a name="task-9-adding-union-all-transform-to-combine-correct-and-corrected-records"></a><span data-ttu-id="f6e5d-102">Aufgabe 9: Hinzufügen der Transformation UNION ALL zur Kombination richtiger und korrigierter Datensätze</span><span class="sxs-lookup"><span data-stu-id="f6e5d-102">Task 9: Adding Union All Transform to Combine Correct and Corrected Records</span></span>
  <span data-ttu-id="f6e5d-103">In dieser Aufgabe fügen Sie dem Datenfluss die Transformation UNION ALL hinzu.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-103">In this task, you add the Union All Transform to the data flow.</span></span> <span data-ttu-id="f6e5d-104">Die Transformation für UNION ALL kombiniert mehrere Eingaben zu einer einzigen Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-104">The Union All transformation combines multiple inputs into one output.</span></span> <span data-ttu-id="f6e5d-105">In Ihrem Szenario kombiniert sie richtige und korrigierte Datensätze zu einem Datenstrom.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-105">In your scenario, it combine both Correct and Corrected records into one stream.</span></span>  
  
1.  <span data-ttu-id="f6e5d-106">Ziehen Sie die Transformation **Union all** Transform aus **Common** section der **SSIS-Toolbox** auf die Registerkarte **Datenfluss** , und platzieren Sie Sie unter **richtige und korrigierte Datensätze auswählen**.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-106">Drag-drop **Union All** Transform from **Common** section of the **SSIS Toolbox** to the **Data Flow** tab and place it under **Pick Correct and Corrected Records**.</span></span>  
  
2.  <span data-ttu-id="f6e5d-107">Klicken Sie mit der rechten Maustaste auf **Union all** Transform auf der Registerkarte **Datenfluss** , und klicken Sie auf **Umbenennen**</span><span class="sxs-lookup"><span data-stu-id="f6e5d-107">Right-click **Union All** Transform in the **Data Flow** tab, and click **Rename**.</span></span> <span data-ttu-id="f6e5d-108">Geben **Sie** **richtige und korrigierte Datensätze zusammenfassen**ein</span><span class="sxs-lookup"><span data-stu-id="f6e5d-108">Type **Combine Correct and Corrected Records**, and press **ENTER**.</span></span>  
  
     <span data-ttu-id="f6e5d-109">![Kombinieren richtiger und korrigierter Datensätze](../../2014/tutorials/media/et-addinguattocombinecacrecords-01.jpg "Kombinieren richtiger und korrigierter Datensätze")</span><span class="sxs-lookup"><span data-stu-id="f6e5d-109">![Combine Correct and Corrected Reocrds](../../2014/tutorials/media/et-addinguattocombinecacrecords-01.jpg "Combine Correct and Corrected Reocrds")</span></span>  
  
3.  <span data-ttu-id="f6e5d-110">Verbinden Sie **richtige und korrigierte Datensätze** , um **korrekte und korrigierte Datensätze** auf der Registerkarte " **Datenfluss** " mit dem blauen Connector zu kombinieren.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-110">Connect **Pick Correct and Corrected Records** to **Combine Correct and Corrected Records** in the **Data Flow** tab by using the blue connector.</span></span> <span data-ttu-id="f6e5d-111">Das Dialogfeld **Eingabe Ausgabe Auswahl** sollte angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-111">You should see the **Input Output Selection** dialog box.</span></span>  
  
4.  <span data-ttu-id="f6e5d-112">Wählen Sie im Dialogfeld **Eingabe Ausgabe** die Option für **Ausgabe** **korrigieren** aus, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-112">In the **Input Output** dialog box, select **Correct** for **Output** and click **OK**.</span></span>  
  
     <span data-ttu-id="f6e5d-113">![Eingabe-/Ausgabe-Auswahl (Dialogfeld)](../../2014/tutorials/media/et-addinguattocombinecacrecords-02.jpg "Eingabe-/Ausgabe-Auswahl (Dialogfeld)")</span><span class="sxs-lookup"><span data-stu-id="f6e5d-113">![Input Output Selection Dialog Box](../../2014/tutorials/media/et-addinguattocombinecacrecords-02.jpg "Input Output Selection Dialog Box")</span></span>  
  
5.  <span data-ttu-id="f6e5d-114">Verschieben Sie den Connector mit dem Titel **richtig** nach links, indem Sie den Punkt am Ende des Verbindungs Punkts nach links ziehen und ablegen.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-114">Move the connector titled **Correct** to the left by dragging and dropping the dot at the end of the connector to left.</span></span>  
  
     <span data-ttu-id="f6e5d-115">![Verbinden mit richtigen Datensätzen zum Kombinieren richtiger und korrigierter Datensätze](../../2014/tutorials/media/et-addinguattocombinecacrecords-03.jpg "Verbinden mit richtigen Datensätzen zum Kombinieren richtiger und korrigierter Datensätze")</span><span class="sxs-lookup"><span data-stu-id="f6e5d-115">![Connect Correct to Combine Correct and Corrected](../../2014/tutorials/media/et-addinguattocombinecacrecords-03.jpg "Connect Correct to Combine Correct and Corrected")</span></span>  
  
6.  <span data-ttu-id="f6e5d-116">Wenn Sie Transformation für **richtige und korrigierte Datensätze** auswählen auswählen, sollte ein weiterer blauer Connector angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-116">If you select **Pick Correct and Corrected Records** transform, you should see another blue connector.</span></span> <span data-ttu-id="f6e5d-117">Ziehen Sie diesen blauen Connector, um **korrekte und korrigierte Datensätze zu kombinieren**</span><span class="sxs-lookup"><span data-stu-id="f6e5d-117">Drag that blue connector to **Combine Correct and Corrected Records**.</span></span>  
  
     <span data-ttu-id="f6e5d-118">![Verbinden mit korrigierten Datensätzen zum Kombinieren richtiger und korrigierter Datensätze](../../2014/tutorials/media/et-addinguattocombinecacrecords-04.jpg "Verbinden mit korrigierten Datensätzen zum Kombinieren richtiger und korrigierter Datensätze")</span><span class="sxs-lookup"><span data-stu-id="f6e5d-118">![Connect Corrected to Combine Correct and Corrected](../../2014/tutorials/media/et-addinguattocombinecacrecords-04.jpg "Connect Corrected to Combine Correct and Corrected")</span></span>  
  
7.  <span data-ttu-id="f6e5d-119">Dieser **Connector** sollte mit dem Titel **korrigiert**versehen werden.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-119">This **connector** should be titled **Corrected**.</span></span> <span data-ttu-id="f6e5d-120">Da nur zwei Bedingungen **korrekt** und **korrigiert**sind und bereits eine Bedingung verwendet wurde, wird das Dialogfeld Eingabe- **/ausgabeauswahl** nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-120">Since you have only two conditions **Correct** and **Corrected**, and one condition was already used, the **Input Output Selection** dialog box is not displayed this time.</span></span> <span data-ttu-id="f6e5d-121">Wenn sich die Konnektoren überlappen, verschieben Sie einen nach links und den anderen nach rechts, indem Sie den Konnektor nach links bzw. rechts ziehen.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-121">If the connectors overlap, move one to left and the other one to right by dragging the connector to left or right.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="f6e5d-122">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="f6e5d-122">Next Step</span></span>  
 [<span data-ttu-id="f6e5d-123">Aufgabe 10: Hinzufügen der Transformation für Fuzzygruppierung zur Identifizierung von Duplikaten</span><span class="sxs-lookup"><span data-stu-id="f6e5d-123">Task 10: Adding Fuzzy Group Transform to Identify Duplicates</span></span>](../../2014/tutorials/task-10-adding-fuzzy-group-transform-to-identify-duplicates.md)  
  
  
