---
title: Hinzufügen von Spalten zu Abfragen (Visual Database Tools)| Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- inserting columns
- columns [SQL Server], adding
- queries [SQL Server], columns
- adding columns
ms.assetid: 82f3ba72-3d72-4fb1-8179-2a953a782787
author: stevestein
ms.author: sstein
ms.openlocfilehash: 49c6e575eea2d4437be1f16b400ca22120471fcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615766"
---
# <a name="add-columns-to-queries-visual-database-tools"></a><span data-ttu-id="6e006-102">Hinzufügen von Spalten zu Abfragen (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="6e006-102">Add Columns to Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="6e006-103">Wenn Sie in einer Abfrage eine Spalte verwenden möchten, müssen Sie diese der Abfrage hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="6e006-103">To use a column in a query, you must add it to the query.</span></span> <span data-ttu-id="6e006-104">Sie haben die Möglichkeit, eine hinzugefügte Spalte im Abfrageergebnis anzeigen zu lassen und sie zum Sortieren, Durchsuchen oder Zusammenfassen des Spalteninhalts zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="6e006-104">You might add a column to display it in query output, to use it for sorting, to search the contents of the column, or to summarize its contents.</span></span> <span data-ttu-id="6e006-105">Sie können festlegen, welche der in der Abfrage verwendeten Spalten beim Ausführen der Abfrage im Ergebnisbereich angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="6e006-105">You can decide which of the columns you use in the query are included in the results pane when the query is run.</span></span> <span data-ttu-id="6e006-106">Weitere Informationen finden Sie unter [Entfernen von Spalten aus Abfrageergebnissen &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="6e006-106">For more information see [Remove Columns from Query Results &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6e006-107">Wählen Sie zum Anzeigen des Datentyps einer Spalte im Abfrage- und Sicht-Designer die Tabelle oder das Tabellenwertobjekt im **Diagrammbereich** aus, und klicken Sie im Eigenschaftenfenster auf „Spaltenliste“.</span><span class="sxs-lookup"><span data-stu-id="6e006-107">To view the data type of a column in Query and View Designer; select the table or table-valued object in the **Diagram Pane** and in the properties window click Column List.</span></span> <span data-ttu-id="6e006-108">Klicken Sie dann auf die **Auslassungspunkte (...)** , um das Dialogfeld **Spaltenliste** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="6e006-108">Then click the **ellipses (...)** to open the **Column List** dialog box.</span></span>  
  
 <span data-ttu-id="6e006-109">Für alle Zwecke, für die Sie eine Spalte in einer Abfrage verwenden, können Sie auch einen Ausdruck verwenden, der aus einer beliebigen Kombination von Spalten, Zeichen, Operatoren und Funktionen bestehen kann.</span><span class="sxs-lookup"><span data-stu-id="6e006-109">Wherever you use a column in a query, you can also use an expression that can consist of any combination of columns, literals, operators, and functions.</span></span>  
  
### <a name="to-add-an-individual-column"></a><span data-ttu-id="6e006-110">So fügen Sie eine einzelne Spalte hinzu</span><span class="sxs-lookup"><span data-stu-id="6e006-110">To add an individual column</span></span>  
  
-   <span data-ttu-id="6e006-111">Aktivieren Sie im **Diagrammbereich**das Kontrollkästchen neben der einzufügenden Spalte.</span><span class="sxs-lookup"><span data-stu-id="6e006-111">In the **Diagram Pane**, select the check box next to the column that you want to include.</span></span>  
  
     <span data-ttu-id="6e006-112">Oder</span><span class="sxs-lookup"><span data-stu-id="6e006-112">-or-</span></span>  
  
-   <span data-ttu-id="6e006-113">Gehen Sie im **Kriterienbereich**zur ersten leeren Zeile des Datenblatts, klicken Sie in das Feld in der Spalte mit dem Namen **Spalte** , und wählen Sie in der Dropdownliste einen Spaltennamen aus.</span><span class="sxs-lookup"><span data-stu-id="6e006-113">In the **Criteria Pane**, move to the first blank grid row, click the field in the **Column** column, and select a column name from the drop-down list.</span></span>  
  
### <a name="to-add-all-columns-for-one-table-or-table-valued-object"></a><span data-ttu-id="6e006-114">So fügen Sie alle Spalten einer Tabelle oder eines Tabellenwertobjekts hinzu</span><span class="sxs-lookup"><span data-stu-id="6e006-114">To add all columns for one table or table-valued object</span></span>  
  
-   <span data-ttu-id="6e006-115">Aktivieren Sie im **Diagramm**Bereich das Kontrollkästchen neben \*\* \* (alle Spalten)\*\*.</span><span class="sxs-lookup"><span data-stu-id="6e006-115">In the **Diagram Pane**, select the check box next to **\*(All Columns)**.</span></span>  
  
### <a name="to-add-all-columns-for-all-tables-and-table-structured-objects"></a><span data-ttu-id="6e006-116">So fügen Sie alle Spalten sämtlicher Tabellen und Objekte mit Tabellenstruktur hinzu</span><span class="sxs-lookup"><span data-stu-id="6e006-116">To add all columns for all tables and table-structured objects</span></span>  
  
1.  <span data-ttu-id="6e006-117">Vergewissern Sie sich, dass im Bereich **Tabellenvorgänge** keine Joinlinien markiert sind.</span><span class="sxs-lookup"><span data-stu-id="6e006-117">Make sure no join lines in the **Table Operations Pane** are selected.</span></span>  
  
2.  <span data-ttu-id="6e006-118">Klicken Sie mit der rechten Maustaste auf einen leeren Bereich im Entwurfsfenster, und wählen Sie im Kontextmenü die Option **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="6e006-118">Right-click in the empty space of the Design window and choose **Properties** from the shortcut menu.</span></span>  
  
3.  <span data-ttu-id="6e006-119">Klicken Sie im Eigenschaftenfenster auf **Alle Spalten ausgeben** , und wählen Sie in der Dropdownliste die Option **Ja** oder **Nein** .</span><span class="sxs-lookup"><span data-stu-id="6e006-119">In the Properties window click **Output all columns** and choose **Yes** or **No** from the dropdown list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e006-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6e006-120">See Also</span></span>  
 <span data-ttu-id="6e006-121">[Entfernen von Spalten aus Abfrage Ergebnissen &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="6e006-121">[Remove Columns from Query Results &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="6e006-122">[Entfernen von Spalten aus Abfragen &#40;Visual Database Tools&#41;](remove-columns-from-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="6e006-122">[Remove Columns from Queries &#40;Visual Database Tools&#41;](remove-columns-from-queries-visual-database-tools.md) </span></span>  
 <span data-ttu-id="6e006-123">[Angeben von Suchkriterien &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="6e006-123">[Specify Search Criteria &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md) </span></span>  
 <span data-ttu-id="6e006-124">[Zusammenfassen von Abfrage Ergebnissen &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="6e006-124">[Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="6e006-125">Ausführen grundlegender Vorgänge mit Abfragen &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="6e006-125">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
