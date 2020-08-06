---
title: 'Lektion 4: Markieren als Datums Tabelle | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: c32cc336-b7d8-4122-9d62-4936344d2315
author: minewiskan
ms.author: owend
ms.openlocfilehash: c3ccc57d770d954e9523196d2393fa9dc2ada5b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619429"
---
# <a name="lesson-4-mark-as-date-table"></a><span data-ttu-id="a4ce9-102">Lektion 4: Als Datumstabelle markieren</span><span class="sxs-lookup"><span data-stu-id="a4ce9-102">Lesson 4: Mark as Date Table</span></span>
  <span data-ttu-id="a4ce9-103">In "Lektion 2: Hinzufügen von Daten" haben Sie eine Dimensionstabelle mit dem Namen "DimDate" importiert.</span><span class="sxs-lookup"><span data-stu-id="a4ce9-103">In Lesson 2: Add Data, you imported a dimension table named DimDate.</span></span> <span data-ttu-id="a4ce9-104">Dann haben Sie in "Lektion 3: Umbenennen von Spalten" die Tabelle "DimDate" in "Date" umbenannt.</span><span class="sxs-lookup"><span data-stu-id="a4ce9-104">You then renamed the DimDate table, in Lesson 3: Rename Columns, to simply, Date.</span></span> <span data-ttu-id="a4ce9-105">In Ihrem Modell lautet der Name dieser Tabelle jetzt „Date“, sie kann jedoch auch als *Datumstabelle* bezeichnet werden, da sie Datums- und Uhrzeitdaten enthält.</span><span class="sxs-lookup"><span data-stu-id="a4ce9-105">While in your model this table is now named Date, it can also be known as a *Date table*, in that it contains date and time data.</span></span>  
  
 <span data-ttu-id="a4ce9-106">Immer wenn Sie in Berechnungen Zeitintelligenzfunktionen verwenden, z.B. in Kürze beim Erstellen von Measures, müssen Sie Eigenschaften von Datentabellen angeben, die eine *Datumstabelle* und als eindeutigen Bezeichner die *Datumsspalte* in dieser Tabelle enthalten.</span><span class="sxs-lookup"><span data-stu-id="a4ce9-106">Whenever you use Time Intelligence functions in calculations, as you will do when you create measures a little later, you must specify date table properties, which include a *Date table* and a unique identifier *Date column* in that table.</span></span> <span data-ttu-id="a4ce9-107">Sie können dann gültige Beziehungen zwischen anderen Tabellen und der Datumstabelle erstellen. Dies ist für Berechnungen mit DAX-Zeitintelligenzfunktionen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a4ce9-107">You can then create valid relationships between other tables and the Date table; necessary for calculations using DAX time intelligence functions.</span></span>  
  
 <span data-ttu-id="a4ce9-108">In dieser Lektion kennzeichnen Sie die importierte und umbenannte Date-Tabelle als *Datumstabelle* und die Date-Spalte (in der Date-Tabelle) als *Datumsspalte* (eindeutiger Bezeichner).</span><span class="sxs-lookup"><span data-stu-id="a4ce9-108">In this lesson, you will mark the imported and renamed Date table as the *Date table* and the Date column (in the Date table) as the *Date column* (unique identifier).</span></span> <span data-ttu-id="a4ce9-109">Alle Verwendungsmöglichkeiten des Namens Datums können verwirrend sein, aber Sie werden bald die Idee erhalten.</span><span class="sxs-lookup"><span data-stu-id="a4ce9-109">All the use of the name Date can get kind of confusing, but you'll soon get the idea.</span></span>  
  
 <span data-ttu-id="a4ce9-110">Geschätzte Zeit zum Bearbeiten dieser Lektion: **3 Minuten**</span><span class="sxs-lookup"><span data-stu-id="a4ce9-110">Estimated time to complete this lesson: **3 minutes**</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a4ce9-111">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="a4ce9-111">Prerequisites</span></span>  
 <span data-ttu-id="a4ce9-112">Dieses Thema ist Teil eines Tutorials zur Tabellenmodellierung, das in der richtigen Reihenfolge absolviert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="a4ce9-112">This topic is part of a tabular modeling tutorial, which should be completed in order.</span></span> <span data-ttu-id="a4ce9-113">Sie sollten vor dem Ausführen der Aufgaben in dieser Lektion die vorherige Lektion abgeschlossen haben: [Lektion 3: Umbenennen von Spalten](rename-columns.md).</span><span class="sxs-lookup"><span data-stu-id="a4ce9-113">Before performing the tasks in this lesson, you should have completed the previous lesson: [Lesson 3: Rename Columns](rename-columns.md).</span></span>  
  
### <a name="to-set-mark-as-date-table"></a><span data-ttu-id="a4ce9-114">Markieren als Datumstabelle</span><span class="sxs-lookup"><span data-stu-id="a4ce9-114">To set Mark as Date Table</span></span>  
  
1.  <span data-ttu-id="a4ce9-115">Klicken Sie im Modell-Designer auf die Tabelle (Registerkarte) **Date** .</span><span class="sxs-lookup"><span data-stu-id="a4ce9-115">In the model designer, click the **Date** table (tab).</span></span>  
  
2.  <span data-ttu-id="a4ce9-116">Klicken Sie im Menü **Tabelle** auf **Datum**, und klicken Sie dann auf **als Datums Tabelle markieren**.</span><span class="sxs-lookup"><span data-stu-id="a4ce9-116">Click the **Table** menu, then click **Date**, and then click **Mark as Date Table**.</span></span>  
  
3.  <span data-ttu-id="a4ce9-117">Wählen Sie im Dialogfeld **Als Datumstabelle markieren** im Listenfeld **Datum** die Spalte **Datum** als eindeutigen Bezeichner aus.</span><span class="sxs-lookup"><span data-stu-id="a4ce9-117">In the **Mark as Date Table** dialog box, in the **Date** listbox, select the **Date** column as the unique identifier.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="a4ce9-118">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="a4ce9-118">Next Steps</span></span>  
 <span data-ttu-id="a4ce9-119">Wenn Sie mit diesem Tutorial fortfahren möchten, wechseln Sie zur nächsten Lektion: [Lektion 5: Erstellen von Beziehungen](lesson-4-create-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="a4ce9-119">To continue this tutorial, go to the next lesson: [Lesson 5: Create Relationships](lesson-4-create-relationships.md).</span></span>  
  
  
