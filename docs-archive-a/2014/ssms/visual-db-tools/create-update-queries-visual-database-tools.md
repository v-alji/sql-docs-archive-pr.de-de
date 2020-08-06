---
title: Erstellen von Updateabfragen (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- tables [SQL Server], updating
- queries [SQL Server], types
- Update query
- updating tables
ms.assetid: 178b7b75-8078-4e61-b2a8-4719b9d8033d
author: stevestein
ms.author: sstein
ms.openlocfilehash: bbea575d544875dba73de923474cc11bbcb46a9b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618989"
---
# <a name="create-update-queries-visual-database-tools"></a><span data-ttu-id="acde5-102">Erstellen von Updateabfragen (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="acde5-102">Create Update Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="acde5-103">Mit einer Aktualisierungsabfrage können Sie in einem Vorgang den Inhalt mehrerer Zeilen ändern.</span><span class="sxs-lookup"><span data-stu-id="acde5-103">You can change the contents of multiple rows in one operation by using an Update query.</span></span> <span data-ttu-id="acde5-104">Sie können beispielsweise in der Tabelle `titles` eine Updateabfrage verwenden, um den Preis aller Bücher eines bestimmten Herausgebers um 10 % zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="acde5-104">For example, in a `titles` table you can use an Update query to add 10% to the price of all books for a particular publisher.</span></span>  
  
 <span data-ttu-id="acde5-105">Beim Erstellen einer Updateabfrage müssen folgende Angaben gemacht werden:</span><span class="sxs-lookup"><span data-stu-id="acde5-105">When you create an Update query, you specify:</span></span>  
  
-   <span data-ttu-id="acde5-106">Die zu aktualisierende Tabelle</span><span class="sxs-lookup"><span data-stu-id="acde5-106">The table to update.</span></span>  
  
-   <span data-ttu-id="acde5-107">Die Spalten, deren Inhalt Sie aktualisieren möchten</span><span class="sxs-lookup"><span data-stu-id="acde5-107">The columns whose contents you want to update.</span></span>  
  
-   <span data-ttu-id="acde5-108">Der Wert oder Ausdruck, der zum Aktualisieren der einzelnen Spalten verwendet werden soll</span><span class="sxs-lookup"><span data-stu-id="acde5-108">The value or expression to use to update the individual columns.</span></span>  
  
-   <span data-ttu-id="acde5-109">Suchbedingungen zum Definieren der zu aktualisierenden Zeilen</span><span class="sxs-lookup"><span data-stu-id="acde5-109">Search conditions to define the rows you want to update.</span></span>  
  
 <span data-ttu-id="acde5-110">Die folgende Abfrage aktualisiert beispielsweise die Tabelle `titles` , indem der Preis sämtlicher Titel eines Herausgebers um 10 % erhöht wird:</span><span class="sxs-lookup"><span data-stu-id="acde5-110">For example, the following query updates the `titles` table by adding 10% to the price of all titles for one publisher:</span></span>  
  
```  
UPDATE titles  
SET price = price * 1.1  
WHERE (pub_id = '0766')  
```  
  
> [!CAUTION]  
>  <span data-ttu-id="acde5-111">Eine ausgeführte Updateabfrage kann nicht rückgängig gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="acde5-111">You cannot undo the action of executing an Update query.</span></span> <span data-ttu-id="acde5-112">Erstellen Sie vorsichtshalber vor Ausführung der Abfrage eine Sicherungskopie der Daten.</span><span class="sxs-lookup"><span data-stu-id="acde5-112">As a precaution, back up your data before executing the query.</span></span>  
  
### <a name="to-create-an-update-query"></a><span data-ttu-id="acde5-113">So erstellen Sie eine Updateabfrage</span><span class="sxs-lookup"><span data-stu-id="acde5-113">To create an Update query</span></span>  
  
1.  <span data-ttu-id="acde5-114">Fügen Sie dem Diagrammbereich die zu aktualisierende Tabelle hinzu.</span><span class="sxs-lookup"><span data-stu-id="acde5-114">Add the table you want to update to the Diagram pane.</span></span>  
  
2.  <span data-ttu-id="acde5-115">Zeigen Sie im Menü **Abfrage-Designer** auf **Typ ändern**, und klicken Sie dann auf **Aktualisieren**.</span><span class="sxs-lookup"><span data-stu-id="acde5-115">From the **Query Designer** menu point to **Change Type**, and then click **Update**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="acde5-116">Wenn beim Starten der Updateabfrage mehr als eine Tabelle im Diagrammbereich angezeigt wird, zeigt der Abfrage- und Sicht-Designer das [Dialogfeld „Zieltabelle für eingefügte Ergebnisse auswählen“](visual-database-tools.md) an, in dem Sie zur Eingabe des Namens der zu aktualisierenden Tabelle aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="acde5-116">If more than one table is displayed in the Diagram pane when you start the Update query, the Query and View Designer displays the [Choose Target Table for Insert Values Dialog Box](visual-database-tools.md) to prompt you for the name of the table to update.</span></span>  
  
3.  <span data-ttu-id="acde5-117">Aktivieren Sie im Diagrammbereich das Kontrollkästchen für die Spalten, für die Sie neue Werte eingeben wollen.</span><span class="sxs-lookup"><span data-stu-id="acde5-117">In the Diagram pane, click the check box for each column for which you want to supply new values.</span></span> <span data-ttu-id="acde5-118">Diese Spalten werden im Kriterienbereich angezeigt.</span><span class="sxs-lookup"><span data-stu-id="acde5-118">Those columns will show in the Criteria pane.</span></span> <span data-ttu-id="acde5-119">Spalten werden nur aktualisiert, wenn sie der Abfrage hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="acde5-119">Columns will be updated only if you add them to the query.</span></span>  
  
4.  <span data-ttu-id="acde5-120">Geben Sie im Kriterienbereich in der Spalte **Neuer Wert** den Updatewert für die Spalte ein.</span><span class="sxs-lookup"><span data-stu-id="acde5-120">In the **New Value** column of the Criteria pane, enter the update value for the column.</span></span> <span data-ttu-id="acde5-121">Sie können Literalwerte, Spaltennamen oder Ausdrücke eingeben.</span><span class="sxs-lookup"><span data-stu-id="acde5-121">You can enter literal values, column names, or expressions.</span></span> <span data-ttu-id="acde5-122">Der Wert muss dem Datentyp der zu aktualisierenden Spalte entsprechen (oder mit diesem kompatibel sein).</span><span class="sxs-lookup"><span data-stu-id="acde5-122">The value must match (or be compatible with) the data type of the column you are updating.</span></span>  
  
    > [!CAUTION]  
    >  <span data-ttu-id="acde5-123">Der Abfrage- und Sicht-Designer kann nicht überprüfen, ob ein Wert von der Länge her in die zu aktualisierende Spalte passt.</span><span class="sxs-lookup"><span data-stu-id="acde5-123">The Query and View Designer cannot check that a value fits within the length of the column you are updating.</span></span> <span data-ttu-id="acde5-124">Bei Eingabe eines zu langen Werts kann dieser ohne vorherige Warnung verkürzt werden.</span><span class="sxs-lookup"><span data-stu-id="acde5-124">If you provide a value that is too long, it might be truncated without warning.</span></span> <span data-ttu-id="acde5-125">Wenn beispielsweise die Spalte `name` eine Länge von 20 Zeichen aufweist, Sie aber einen aus 25 Zeichen bestehenden Updatewert angeben, werden die letzten 5 Zeichen möglicherweise abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="acde5-125">For example, if a `name` column is 20 characters long but you specify an update value of 25 characters, the last 5 characters might be truncated.</span></span>  
  
5.  <span data-ttu-id="acde5-126">Definieren Sie die zu aktualisierenden Zeilen, indem Sie in der Spalte **Filter** Suchbedingungen eingeben.</span><span class="sxs-lookup"><span data-stu-id="acde5-126">Define the rows to update by entering search conditions in the **Filter** column.</span></span> <span data-ttu-id="acde5-127">Weitere Informationen finden Sie unter [Angeben von Suchbedingungen &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="acde5-127">For details, see [Specify Search Criteria &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md).</span></span>  
  
     <span data-ttu-id="acde5-128">Wenn Sie keine Suchbedingung angeben, werden alle Zeilen der angegebenen Tabelle aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="acde5-128">If you do not specify a search condition, all rows in the specified table will be updated.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="acde5-129">Wenn Sie dem Kriterienbereich eine Spalte zum Verwenden in einer Suchbedingung hinzufügen, wird sie vom Abfrage- und Sicht-Designer auch der Liste der zu aktualisierenden Spalten hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="acde5-129">When you add a column to the Criteria pane for use in a search condition, the Query and View Designer also adds it to the list of columns to be updated.</span></span> <span data-ttu-id="acde5-130">Wenn Sie eine Spalte für eine Suchbedingung verwenden, aber nicht aktualisieren möchten, deaktivieren Sie das Kontrollkästchen in dem Rechteck neben dem Spaltennamen, das die Tabelle oder das Tabellenwertobjekt darstellt.</span><span class="sxs-lookup"><span data-stu-id="acde5-130">If you want to use a column for a search condition but not update it, clear the check box next to the column name in the rectangle representing the table or table-valued object.</span></span>  
  
 <span data-ttu-id="acde5-131">Beim Ausführen einer Updateabfrage werden keine Ergebnisse im [Ergebnisbereich](results-pane-visual-database-tools.md)angezeigt.</span><span class="sxs-lookup"><span data-stu-id="acde5-131">When you execute an Update query, no results are reported in the [Results Pane](results-pane-visual-database-tools.md).</span></span> <span data-ttu-id="acde5-132">Stattdessen wird eine Meldung mit der Anzahl der geänderten Zeilen ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="acde5-132">Instead, a message appears indicating how many rows were changed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acde5-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="acde5-133">See Also</span></span>  
 <span data-ttu-id="acde5-134">[Unterstützte Abfrage Typen &#40;Visual Database Tools&#41;](supported-query-types-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="acde5-134">[Supported Query Types &#40;Visual Database Tools&#41;](supported-query-types-visual-database-tools.md) </span></span>  
 <span data-ttu-id="acde5-135">[Themen zur Vorgehensweise beim Entwerfen von Abfragen und Sichten &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="acde5-135">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="acde5-136">Ausführen grundlegender Vorgänge mit Abfragen &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="acde5-136">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
