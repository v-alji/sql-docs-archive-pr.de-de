---
title: Hinzufügen neuer Zeilen im Ergebnisbereich (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- View Designer, Results pane
- inserting rows
- Query Designer [SQL Server], Results pane
- Results pane
- adding rows
- row additions [SQL Server], Results pane
ms.assetid: 59891c84-3f54-4ab9-8b86-72c59627b480
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3137da106279e09305261c6c7cb7fd06d254b4fa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615763"
---
# <a name="add-new-rows-in-the-results-pane-visual-database-tools"></a><span data-ttu-id="b65ad-102">Hinzufügen neuer Zeilen im Ergebnisbereich (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="b65ad-102">Add New Rows in the Results Pane (Visual Database Tools)</span></span>
  <span data-ttu-id="b65ad-103">Sie können neue Daten hinzufügen, indem Sie sie eintippen oder aus einem anderen Programm, z. B. Editor oder Excel, einfügen.</span><span class="sxs-lookup"><span data-stu-id="b65ad-103">You can add new data either by typing it in or by pasting it from another program such as Notepad or Excel.</span></span> <span data-ttu-id="b65ad-104">Eine einzufügende Zeile muss genau dieselbe Anzahl und denselben Typ von Spalten wie die Tabelle aufweisen, in die Sie die Zeile einfügen.</span><span class="sxs-lookup"><span data-stu-id="b65ad-104">A row to be pasted must have exactly the same number and types of columns as the table into which you are pasting.</span></span> <span data-ttu-id="b65ad-105">Sie können mehrere Zeilen gleichzeitig in den Ergebnisbereich einfügen.</span><span class="sxs-lookup"><span data-stu-id="b65ad-105">You can paste multiple rows into the Results pane at once.</span></span>  
  
 <span data-ttu-id="b65ad-106">Informationen zum Eingeben von Daten finden Sie unter [Regeln zum Aktualisieren von Ergebnissen &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b65ad-106">For information about how to enter data see [Rules for Updating Results &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
### <a name="to-add-a-new-data-row"></a><span data-ttu-id="b65ad-107">So fügen Sie eine neue Datenzeile ein</span><span class="sxs-lookup"><span data-stu-id="b65ad-107">To add a new data row</span></span>  
  
1.  <span data-ttu-id="b65ad-108">Wechseln Sie in den unteren Teil des Ergebnisbereichs, in dem eine leere Zeile für das Hinzufügen einer neuen Datenzeile verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="b65ad-108">Navigate to the bottom of the Results pane, where a blank row is available for adding a new data row.</span></span>  
  
     <span data-ttu-id="b65ad-109">Die Anfangswerte aller Spalten sind *NULL*.</span><span class="sxs-lookup"><span data-stu-id="b65ad-109">The initial values for all columns will be *NULL*.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="b65ad-110">Um sofort zur ersten Leerzeile zu wechseln, benutzen Sie die Navigationsleiste am unteren Rand des Ergebnisbereichs.</span><span class="sxs-lookup"><span data-stu-id="b65ad-110">To go directly to the first empty row use the navigation bar at the bottom of the Results pane.</span></span>  
  
2.  <span data-ttu-id="b65ad-111">Wenn Sie Zeilen aus der Zwischenablage einfügen, markieren Sie die neue Zeile, indem Sie auf die Schaltfläche auf der linken Seite klicken.</span><span class="sxs-lookup"><span data-stu-id="b65ad-111">If you are pasting rows from the Clipboard, select the new row by clicking the button to its left.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b65ad-112">Wenn eine oder mehrere der eingefügten Zeilen nicht in die Datenbank eingetragen werden können, wird eine Meldung ausgegeben, die darüber Auskunft gibt, welche Zeile(n) nicht eingetragen werden konnte(n).</span><span class="sxs-lookup"><span data-stu-id="b65ad-112">If one or more of the rows you're pasting can't be committed to the database you will receive a message telling you which row(s) couldn't be committed.</span></span>  
  
3.  <span data-ttu-id="b65ad-113">Geben Sie die Daten für die neue Zeile ein.</span><span class="sxs-lookup"><span data-stu-id="b65ad-113">Enter the data for the new row.</span></span> <span data-ttu-id="b65ad-114">Beim Einfügen aus der Zwischenablage wählen Sie im Menü **Bearbeiten** die Option **Einfügen** aus.</span><span class="sxs-lookup"><span data-stu-id="b65ad-114">If you are pasting, choose **Paste** from the **Edit** menu.</span></span>  
  
4.  <span data-ttu-id="b65ad-115">Bewegen Sie den Zeiger aus der Zeile heraus, damit sie in die Datenbank eingetragen wird.</span><span class="sxs-lookup"><span data-stu-id="b65ad-115">Leave that row to commit it to the database.</span></span>  
  
 <span data-ttu-id="b65ad-116">Falls beim Speichern der Zeile ein Fehler auftritt, zeigt der Abfrage- und Sicht-Designer eine Meldung an und setzt den Zeiger in die Zeile, die Sie in Bearbeitung hatten.</span><span class="sxs-lookup"><span data-stu-id="b65ad-116">If an error occurs when you save the row the Query and View Designer displays a message and then returns you to the row you were editing.</span></span> <span data-ttu-id="b65ad-117">Sie können anschließend folgende Aktionen durchführen:</span><span class="sxs-lookup"><span data-stu-id="b65ad-117">You can then:</span></span>  
  
-   <span data-ttu-id="b65ad-118">Auflösen des Fehlers durch weitere Bearbeitungen der Zeile.</span><span class="sxs-lookup"><span data-stu-id="b65ad-118">Resolve the error by making further edits in the row.</span></span>  
  
-   <span data-ttu-id="b65ad-119">Abbrechen der Bearbeitung durch Drücken von ESC.</span><span class="sxs-lookup"><span data-stu-id="b65ad-119">Cancel the edit by pressing ESC.</span></span> <span data-ttu-id="b65ad-120">Wenn Sie sich beim Drücken von ESC in einer geänderten Zelle befinden, werden die Änderungen an dieser Zelle abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="b65ad-120">If you press ESC while in a cell that you changed, the changes for that cell are canceled.</span></span> <span data-ttu-id="b65ad-121">Befinden Sie sich beim Drücken von ESC in einer nicht geänderten Zelle, werden die Änderungen für die gesamte Zeile verworfen.</span><span class="sxs-lookup"><span data-stu-id="b65ad-121">If you press ESC while in a cell you have not changed, the changes for the entire row are canceled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b65ad-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b65ad-122">See Also</span></span>  
 <span data-ttu-id="b65ad-123">[Arbeiten mit Daten im Ergebnisbereich &#40;Visual Database Tools&#41;](results-pane-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="b65ad-123">[Work with Data in the Results Pane &#40;Visual Database Tools&#41;](results-pane-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="b65ad-124">Ausführen grundlegender Vorgänge mit Abfragen &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="b65ad-124">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
