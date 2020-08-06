---
title: Erstellen von Abfragen zum Einfügen von Werten (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- inserting values
- queries [SQL Server], types
- adding values
- row additions [SQL Server], Insert Values query
- inserting rows
- Insert Values query
- adding rows
- table values [SQL Server]
ms.assetid: 2d4b2f6d-cc09-434b-8a0e-ccce40628064
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2fc71b0148ee8a7e92c517fe75b56c329b3c88f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699111"
---
# <a name="create-insert-values-queries-visual-database-tools"></a><span data-ttu-id="7e9ec-102">Erstellen von Abfragen zum Einfügen von Werten (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="7e9ec-102">Create Insert Values Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="7e9ec-103">Mit einer Abfrage zum Einfügen von Werten können Sie in der aktuellen Tabelle eine neue Zeile erstellen.</span><span class="sxs-lookup"><span data-stu-id="7e9ec-103">You can create a new row in the current table using an Insert Values query.</span></span> <span data-ttu-id="7e9ec-104">Beim Erstellen einer Abfrage zum Einfügen von Werten müssen folgende Angaben gemacht werden:</span><span class="sxs-lookup"><span data-stu-id="7e9ec-104">When you create an Insert Values query, you specify:</span></span>  
  
-   <span data-ttu-id="7e9ec-105">Die Datenbanktabelle, der die Zeile hinzugefügt werden soll</span><span class="sxs-lookup"><span data-stu-id="7e9ec-105">The database table to add the row to.</span></span>  
  
-   <span data-ttu-id="7e9ec-106">Die Spalten, deren Inhalt Sie hinzufügen möchten</span><span class="sxs-lookup"><span data-stu-id="7e9ec-106">The columns whose contents you want to add.</span></span>  
  
-   <span data-ttu-id="7e9ec-107">Der in die einzelnen Spalten einzufügende Wert oder Ausdruck</span><span class="sxs-lookup"><span data-stu-id="7e9ec-107">The value or expression to insert into the individual columns.</span></span>  
  
 <span data-ttu-id="7e9ec-108">Die folgende Abfrage fügt beispielsweise eine Zeile in die Tabelle `titles` ein, die Werte für den Titel, den Typ, den Herausgeber und den Preis angibt:</span><span class="sxs-lookup"><span data-stu-id="7e9ec-108">For example, the following query adds a row to the `titles` table, specifying values for the title, type, publisher, and price:</span></span>  
  
```  
INSERT INTO titles  
         (title_id, title, type, pub_id, price)  
VALUES   ('BU9876', 'Creating Web Pages', 'business', '1389', '29.99')  
```  
  
 <span data-ttu-id="7e9ec-109">Beim Erstellen einer Abfrage zum Einfügen von Werten ändert sich der Kriterienbereich entsprechend und zeigt die beiden Optionen an, die zum Einfügen einer neuen Zeile verfügbar sind: den Spaltennamen und den einzufügenden Wert.</span><span class="sxs-lookup"><span data-stu-id="7e9ec-109">When you create an Insert Values query, the Criteria pane changes to reflect the only options available for inserting a new row: the column name and the value to insert.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="7e9ec-110">Eine ausgeführte Abfrage zum Einfügen von Werten kann nicht mehr rückgängig gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="7e9ec-110">You cannot undo the action of executing an Insert Values query.</span></span> <span data-ttu-id="7e9ec-111">Erstellen Sie vorsichtshalber vor Ausführung der Abfrage eine Sicherungskopie der Daten.</span><span class="sxs-lookup"><span data-stu-id="7e9ec-111">As a precaution, back up your data before executing the query.</span></span>  
  
### <a name="to-create-an-insert-values-query"></a><span data-ttu-id="7e9ec-112">So erstellen Sie eine Abfrage zum Einfügen von Werten</span><span class="sxs-lookup"><span data-stu-id="7e9ec-112">To create an Insert Values query</span></span>  
  
1.  <span data-ttu-id="7e9ec-113">Fügen Sie dem Diagrammbereich die zu aktualisierende Tabelle hinzu.</span><span class="sxs-lookup"><span data-stu-id="7e9ec-113">Add the table you want to update to the Diagram pane.</span></span>  
  
2.  <span data-ttu-id="7e9ec-114">Zeigen Sie im Menü **Abfrage-Designer** auf **Typ ändern**, und klicken Sie dann auf **Werte einfügen**.</span><span class="sxs-lookup"><span data-stu-id="7e9ec-114">From the **Query Designer** menu point to **Change Type**, and then click **Insert Values**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7e9ec-115">Wenn beim Starten der Abfrage zum Einfügen von Werten mehrere Tabellen im Diagrammbereich angezeigt werden, zeigt der Abfrage- und Sicht-Designer das [Dialogfeld „Zieltabelle für eingefügte Ergebnisse auswählen“](visual-database-tools.md) an, in dem Sie zur Eingabe des Namens der zu aktualisierenden Tabelle aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="7e9ec-115">If more than one table is displayed in the Diagram pane when you start the Insert Values query, the Query and View Designer displays the [Choose Target Table for Insert Values Dialog Box](visual-database-tools.md) to prompt you for the name of the table to update.</span></span>  
  
3.  <span data-ttu-id="7e9ec-116">Aktivieren Sie im Diagrammbereich das Kontrollkästchen für die Spalten, für die Sie neue Werte eingeben wollen.</span><span class="sxs-lookup"><span data-stu-id="7e9ec-116">In the Diagram pane, click the check box for each column for which you want to supply new values.</span></span> <span data-ttu-id="7e9ec-117">Diese Spalten werden im Kriterienbereich angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7e9ec-117">Those columns will show in the Criteria pane.</span></span> <span data-ttu-id="7e9ec-118">Spalten werden nur aktualisiert, wenn sie der Abfrage hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="7e9ec-118">Columns will be updated only if you add them to the query.</span></span>  
  
4.  <span data-ttu-id="7e9ec-119">Geben Sie im Kriterienbereich in der Spalte **Neuer Wert** den neuen Wert für die Spalte ein.</span><span class="sxs-lookup"><span data-stu-id="7e9ec-119">In the **New Value** column of the Criteria pane, enter the new value for the column.</span></span> <span data-ttu-id="7e9ec-120">Sie können Literalwerte, Spaltennamen oder Ausdrücke eingeben.</span><span class="sxs-lookup"><span data-stu-id="7e9ec-120">You can enter literal values, column names, or expressions.</span></span> <span data-ttu-id="7e9ec-121">Der Wert muss dem Datentyp der zu aktualisierenden Spalte entsprechen (oder mit diesem kompatibel sein).</span><span class="sxs-lookup"><span data-stu-id="7e9ec-121">The value must match (or be compatible with) the data type of the column you are updating.</span></span>  
  
    > [!CAUTION]  
    >  <span data-ttu-id="7e9ec-122">Der Abfrage- und Sicht-Designer kann nicht überprüfen, ob die Länge eines Werts die zulässige Länge der Spalte überschreitet.</span><span class="sxs-lookup"><span data-stu-id="7e9ec-122">The Query and View Designer cannot check that a value fits within the length of the column you are inserting.</span></span> <span data-ttu-id="7e9ec-123">Bei Eingabe eines zu langen Werts kann dieser ohne vorherige Warnung verkürzt werden.</span><span class="sxs-lookup"><span data-stu-id="7e9ec-123">If you provide a value that is too long, it might be truncated without warning.</span></span> <span data-ttu-id="7e9ec-124">Wenn beispielsweise die Spalte `name` eine Länge von 20 Zeichen aufweist, Sie aber einen aus 25 Zeichen bestehenden einzufügenden Wert angeben, werden die letzten 5 Zeichen möglicherweise abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="7e9ec-124">For example, if a `name` column is 20 characters long but you specify an insert value of 25 characters, the last 5 characters might be truncated.</span></span>  
  
 <span data-ttu-id="7e9ec-125">Beim Ausführen einer Abfrage zum Einfügen von Werten werden keine Ergebnisse im [Ergebnisbereich](results-pane-visual-database-tools.md)angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7e9ec-125">When you execute an Insert Values query, no results are reported in the [Results Pane](results-pane-visual-database-tools.md).</span></span> <span data-ttu-id="7e9ec-126">Stattdessen wird eine Meldung mit der Anzahl der geänderten Zeilen ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="7e9ec-126">Instead, a message appears indicating how many rows were changed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e9ec-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7e9ec-127">See Also</span></span>  
 <span data-ttu-id="7e9ec-128">[Unterstützte Abfrage Typen &#40;Visual Database Tools&#41;](supported-query-types-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="7e9ec-128">[Supported Query Types &#40;Visual Database Tools&#41;](supported-query-types-visual-database-tools.md) </span></span>  
 <span data-ttu-id="7e9ec-129">[Themen zur Vorgehensweise beim Entwerfen von Abfragen und Sichten &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="7e9ec-129">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="7e9ec-130">Ausführen grundlegender Vorgänge mit Abfragen &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="7e9ec-130">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
