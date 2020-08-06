---
title: Erstellen von Abfragen (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- queries [SQL Server], creating
ms.assetid: 696a080d-848f-44d3-a918-e29bafaab85a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 52392adff03b27e1c4c19f354bc62c350cccf17a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608201"
---
# <a name="create-queries-visual-database-tools"></a><span data-ttu-id="2a77d-102">Erstellen von Abfragen (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="2a77d-102">Create Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="2a77d-103">Mit Abfragen können Daten aus den Tabellen und Sichten in der Datenbank abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="2a77d-103">Queries allow you to retrieve data from the tables and views in your database.</span></span> <span data-ttu-id="2a77d-104">Sie erstellen und verwenden Abfragen im **Abfrage- und Sicht-Designer**, der vier Bereiche umfasst: den [Diagrammbereich](visual-database-tools.md), den [SQL-Bereich](sql-pane-visual-database-tools.md), den [Kriterienbereich](criteria-pane-visual-database-tools.md)und den [Ergebnisbereich](results-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="2a77d-104">You create and work with queries in **Query and View Designer**, which is composed of four panes: the [Diagram Pane](visual-database-tools.md), the [SQL Pane](sql-pane-visual-database-tools.md), the [Criteria Pane](criteria-pane-visual-database-tools.md), and the [Results Pane](results-pane-visual-database-tools.md).</span></span>  
  
### <a name="to-create-a-new-query"></a><span data-ttu-id="2a77d-105">So erstellen Sie eine neue Abfrage</span><span class="sxs-lookup"><span data-stu-id="2a77d-105">To create a new query</span></span>  
  
1.  <span data-ttu-id="2a77d-106">Erweitern Sie im **Objekt-Explorer**den Knoten **Tabellen** für die Datenbank, die Sie abfragen möchten.</span><span class="sxs-lookup"><span data-stu-id="2a77d-106">In **Object Explorer**, expand the **Tables** node for the database you want to query.</span></span> <span data-ttu-id="2a77d-107">Klicken Sie mit der rechten Maustaste auf die Tabelle, die Sie abfragen möchten, und klicken Sie auf **Tabelle öffnen**.</span><span class="sxs-lookup"><span data-stu-id="2a77d-107">Right-click the table you want to query and click **Open Table**.</span></span>  
  
2.  <span data-ttu-id="2a77d-108">Wenn Sie der Abfrage weitere Tabellen hinzufügen möchten, wählen Sie im Menü „Abfrage-Designer“ den Befehl **Tabelle hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="2a77d-108">To add more tables to the query, on the Query Designer menu, select **Add Table**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2a77d-109">Wenn der Bereich **Diagramm**, **SQL**, **Kriterien**oder **Ergebnisse** nicht angezeigt wird, zeigen Sie im Abfrage-Designer-Menü auf **Bereich** , und klicken Sie auf den zu öffnenden Bereich.</span><span class="sxs-lookup"><span data-stu-id="2a77d-109">If you do not see the **Diagram**, **SQL**, **Criteria**, or **Results** panes, from the Query Designer menu, point to **Pane** and click the pane you want to open.</span></span>  
  
3.  <span data-ttu-id="2a77d-110">Wählen Sie im Dialogfeld **Tabelle hinzufügen** die Tabellen aus, die Sie abfragen möchten, und klicken Sie bei jeder Tabelle auf **Hinzufügen** .</span><span class="sxs-lookup"><span data-stu-id="2a77d-110">In the **Add Table** dialog box, select the tables you want to query and click **Add** for each one.</span></span>  
  
4.  <span data-ttu-id="2a77d-111">Sobald Sie alle Tabellen hinzugefügt haben, die Sie abfragen möchten, klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="2a77d-111">Once you have added all the tables you want to query, click **Close**.</span></span>  
  
     <span data-ttu-id="2a77d-112">Wenn Sie später weitere Tabellen hinzufügen möchten, klicken Sie im Bereich **Diagramm** mit der rechten Maustaste auf den leeren Bereich, und klicken Sie im Kontextmenü auf **Tabelle hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="2a77d-112">To add more tables later, right-click the open space in the **Diagram** pane and from the shortcut menu click **Add Table**.</span></span>  
  
5.  <span data-ttu-id="2a77d-113">Aktivieren Sie im **Diagrammbereich**in den Tabellenwertobjekten die Kontrollkästchen für jede Spalte, die Sie abfragen möchten.</span><span class="sxs-lookup"><span data-stu-id="2a77d-113">In the **Diagram Pane**, check the boxes in the table-valued objects for each column you want to query.</span></span>  
  
6.  <span data-ttu-id="2a77d-114">Wählen Sie im Menü „Abfrage-Designer“ den Befehl **SQL ausführen** aus, um die Abfrage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="2a77d-114">From the Query Designer menu, choose **Execute SQL** to run your query.</span></span>  
  
 <span data-ttu-id="2a77d-115">Zur weiteren Verfeinerung der Abfrage können Sie den SQL-Code im **SQL-Bereich** ändern oder im **Kriterienbereich**Optionen wie die Sortierreihenfolge und Spaltenaliase auswählen.</span><span class="sxs-lookup"><span data-stu-id="2a77d-115">To further refine your query, you can change the SQL code in the **SQL Pane** or choose options such as sort order and column aliases in the **Criteria Pane.**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a77d-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2a77d-116">See Also</span></span>  
 <span data-ttu-id="2a77d-117">[Speichern von Abfragen &#40;Visual Database Tools&#41;](save-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="2a77d-117">[Save Queries &#40;Visual Database Tools&#41;](save-queries-visual-database-tools.md) </span></span>  
 <span data-ttu-id="2a77d-118">[Typen von Abfragen &#40;Visual Database Tools&#41;](types-of-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="2a77d-118">[Types of Queries &#40;Visual Database Tools&#41;](types-of-queries-visual-database-tools.md) </span></span>  
 <span data-ttu-id="2a77d-119">[Angeben von Suchkriterien &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="2a77d-119">[Specify Search Criteria &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md) </span></span>  
 <span data-ttu-id="2a77d-120">[Zusammenfassen von Abfrage Ergebnissen &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="2a77d-120">[Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="2a77d-121">Ausführen grundlegender Vorgänge mit Abfragen &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="2a77d-121">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
