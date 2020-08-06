---
title: Entfernen von Tabellen aus Abfragen (Visual Database Tools)|Microsoft-Dokumente
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- deleting tables
- removing tables
- dropping tables
- queries [SQL Server], tables
ms.assetid: 8fea0b4f-99b7-4050-8d6f-a97ffb839619
author: stevestein
ms.author: sstein
ms.openlocfilehash: fab5380e13742f3cd289ce17f26ad2e5fb9089ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617355"
---
# <a name="remove-tables-from-queries-visual-database-tools"></a><span data-ttu-id="fc8ad-102">Entfernen von Tabellen aus Abfragen (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="fc8ad-102">Remove Tables from Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="fc8ad-103">Sie können eine Tabelle oder ein Tabellenwertobjekt aus der Abfrage entfernen.</span><span class="sxs-lookup"><span data-stu-id="fc8ad-103">You can remove a table - or any table-valued object - from the query.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fc8ad-104">Beim Entfernen einer Tabelle oder eines Tabellenwertobjekts wird das entsprechende Objekt nur aus der Abfrage entfernt und nicht aus der Datenbank selbst.</span><span class="sxs-lookup"><span data-stu-id="fc8ad-104">Removing a table or table-valued object does not delete anything from the database; it only removes it from the current query.</span></span> <span data-ttu-id="fc8ad-105">Ausführliche Informationen zum Entfernen einer Tabelle aus einer Datenbank finden Sie unter [Löschen von Tabellen &#40;Datenbank-Engine&#41;](../../relational-databases/tables/delete-tables-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="fc8ad-105">For details about removing a table from a database, see [Delete Tables &#40;Database Engine&#41;](../../relational-databases/tables/delete-tables-database-engine.md).</span></span>  
  
### <a name="to-remove-a-table-or-table-structured-object"></a><span data-ttu-id="fc8ad-106">So entfernen Sie eine Tabelle oder ein Objekt mit Tabellenstruktur</span><span class="sxs-lookup"><span data-stu-id="fc8ad-106">To remove a table or table-structured object</span></span>  
  
-   <span data-ttu-id="fc8ad-107">Wählen Sie im **Diagrammbereich**die Tabelle, die Sicht, die benutzerdefinierte Funktion, das Synonym oder die Abfrage aus, und drücken Sie anschließend ENTF, oder klicken Sie mit der rechten Maustaste auf das Objekt, und wählen Sie im daraufhin angezeigten Dialogfeld den Befehl **Entfernen** aus.</span><span class="sxs-lookup"><span data-stu-id="fc8ad-107">In the **Diagram Pane**, select the table, view, user-defined function, synonym, or query, and then press DELETE, or right-click the object and then choose **Remove** in the resulting dialog box.</span></span> <span data-ttu-id="fc8ad-108">Sie können mehrere Objekte auswählen und gleichzeitig entfernen.</span><span class="sxs-lookup"><span data-stu-id="fc8ad-108">You can select and remove multiple objects at one time.</span></span>  
  
     <span data-ttu-id="fc8ad-109">Oder</span><span class="sxs-lookup"><span data-stu-id="fc8ad-109">-or-</span></span>  
  
-   <span data-ttu-id="fc8ad-110">Entfernen Sie im **SQL-Bereich**alle Verweise auf das Objekt.</span><span class="sxs-lookup"><span data-stu-id="fc8ad-110">Remove all references to the object in the **SQL Pane.**</span></span>  
  
 <span data-ttu-id="fc8ad-111">Wenn Sie eine Tabelle oder ein Tabellenwertobjekt entfernen, werden vom Abfrage- und Sicht-Designer Verknüpfungen mit dieser Tabelle oder diesem Tabellenwertobjekt automatisch entfernt. Außerdem werden Verweise auf die Spalten des Objekts aus dem **SQL-Bereich** und dem **Kriterienbereich**entfernt.</span><span class="sxs-lookup"><span data-stu-id="fc8ad-111">When you remove a table or table-valued object, the Query and View Designer automatically removes joins that involve that table or table-valued object and removes references to the object's columns in the **SQL Pane** and **Criteria Pane**.</span></span> <span data-ttu-id="fc8ad-112">Wenn die Abfrage jedoch komplexe, auf das Objekt bezogene Ausdrücke enthält, wird das Objekt erst nach dem Entfernen aller zugehörigen Verweise entfernt.</span><span class="sxs-lookup"><span data-stu-id="fc8ad-112">However, if the query contains complex expressions involving the object, the object is not automatically removed until all references to it are removed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc8ad-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fc8ad-113">See Also</span></span>  
 <span data-ttu-id="fc8ad-114">[Hinzufügen von Tabellen zu Abfragen &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="fc8ad-114">[Add Tables to Queries &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="fc8ad-115">[Erstellen von Tabellenaliasen &#40;Visual Database Tools&#41;](create-table-aliases-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="fc8ad-115">[Create Table Aliases &#40;Visual Database Tools&#41;](create-table-aliases-visual-database-tools.md) </span></span>  
 <span data-ttu-id="fc8ad-116">[Angeben von Suchkriterien &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="fc8ad-116">[Specify Search Criteria &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md) </span></span>  
 <span data-ttu-id="fc8ad-117">[Zusammenfassen von Abfrage Ergebnissen &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="fc8ad-117">[Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="fc8ad-118">Ausführen grundlegender Vorgänge mit Abfragen &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="fc8ad-118">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
