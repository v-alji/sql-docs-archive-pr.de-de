---
title: Darstellung von Joins im Abfrage-und Sicht-Designer (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL pane [Visual Database Tools]
- joins [SQL Server], Query and View Designer
- Diagram pane [Visual Database Tools]
ms.assetid: 20a99dcb-83bd-4aa6-9139-92e2e5ba4887
author: stevestein
ms.author: sstein
ms.openlocfilehash: 55fdea533436f9fa7c2a902667b3166085c27e99
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618978"
---
# <a name="how-the-query-and-view-designer-represents-joins-visual-database-tools"></a><span data-ttu-id="952c6-102">Darstellungsweise von Joins im Abfrage- und Sicht-Designer (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="952c6-102">How the Query and View Designer Represents Joins (Visual Database Tools)</span></span>
  <span data-ttu-id="952c6-103">Bei verknüpften Tabellen stellt der [Abfrage- und Sicht-Designer](visual-database-tools.md) die Verknüpfung im [Diagrammbereich](diagram-pane-visual-database-tools.md) grafisch und im [SQL-Bereich](sql-pane-visual-database-tools.md)mithilfe von SQL-Syntax dar.</span><span class="sxs-lookup"><span data-stu-id="952c6-103">If tables are joined, the [Query and View Designer](visual-database-tools.md) represents the join graphically in the [Diagram pane](diagram-pane-visual-database-tools.md) and by using SQL syntax in the [SQL pane](sql-pane-visual-database-tools.md).</span></span>  
  
## <a name="diagram-pane"></a><span data-ttu-id="952c6-104">Diagrammbereich</span><span class="sxs-lookup"><span data-stu-id="952c6-104">Diagram Pane</span></span>  
 <span data-ttu-id="952c6-105">Im Diagrammbereich wird im Abfrage- und Sicht-Designer eine Joinlinie zwischen den verknüpften Datenspalten an.</span><span class="sxs-lookup"><span data-stu-id="952c6-105">In the Diagram pane the Query and View Designer displays a join line between the data columns involved in the join.</span></span> <span data-ttu-id="952c6-106">Der Abfrage- und Sicht-Designer zeigt eine Joinlinie für jede Joinbedingung an.</span><span class="sxs-lookup"><span data-stu-id="952c6-106">The Query and View Designer displays one join line for each join condition.</span></span> <span data-ttu-id="952c6-107">Die folgende Abbildung zeigt eine Joinlinie zwischen zwei verknüpften Tabellen:</span><span class="sxs-lookup"><span data-stu-id="952c6-107">For example, the following illustration shows a join line between two tables that are joined:</span></span>  
  
 <span data-ttu-id="952c6-108">![Joinlinie zeigt Beziehung zwischen zwei Tabellen](../../database-engine/media//dv3wbig.gif "Joinlinie zeigt Beziehung zwischen zwei Tabellen")</span><span class="sxs-lookup"><span data-stu-id="952c6-108">![Join line shows relationship between two tables](../../database-engine/media//dv3wbig.gif "Join line shows relationship between two tables")</span></span>  
  
 <span data-ttu-id="952c6-109">Wenn Tabellen durch mehrere Joinbedingungen miteinander verknüpft sind, zeigt der Abfrage- und Sicht-Designer wie im folgenden Beispiel mehrere Joinlinien an:</span><span class="sxs-lookup"><span data-stu-id="952c6-109">If tables are joined using more than one join condition, the Query and View Designer displays multiple join lines, as in the following example:</span></span>  
  
 <span data-ttu-id="952c6-110">![Mit mehr als einer Verknüpfungsbedingung verknüpfte Tabellen](../../database-engine/media//dv3w9n1.gif "Mit mehr als einer Verknüpfungsbedingung verknüpfte Tabellen")</span><span class="sxs-lookup"><span data-stu-id="952c6-110">![Tables joined using more than one join condition](../../database-engine/media//dv3w9n1.gif "Tables joined using more than one join condition")</span></span>  
  
 <span data-ttu-id="952c6-111">Wenn die verknüpften Datenspalten nicht angezeigt werden (z. B., weil das die Tabelle oder das Objekt mit Tabellenstruktur darstellende Rechteck minimiert ist oder der Join einen Ausdruck beinhaltet), setzt der Abfrage- und Sicht-Designer die Joinlinie in die Titelleiste des Rechtecks, das die Tabelle oder das Objekt mit Tabellenstruktur darstellt.</span><span class="sxs-lookup"><span data-stu-id="952c6-111">If the joined data columns are not displayed (for example, the rectangle representing the table or table-structured object is minimized or the join involves an expression), the Query and View Designer places the join line at the title bar of the rectangle representing the table or table-structured object.</span></span>  
  
 <span data-ttu-id="952c6-112">Die Form des Symbols in der Mitte der Joinlinie zeigt an, wie die Tabellen oder Objekte mit Tabellenstruktur verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="952c6-112">The shape of the icon in the middle of the join line indicates how the tables or table-structured objects are joined.</span></span> <span data-ttu-id="952c6-113">Wenn die Joinklausel einen anderen Operator als „gleich“ (=) verwendet, wird der Operator im Symbol der Joinlinie angezeigt.</span><span class="sxs-lookup"><span data-stu-id="952c6-113">If the join clause uses an operator other than equal (=), the operator appears in the join line icon.</span></span> <span data-ttu-id="952c6-114">In der folgenden Tabelle werden die in der Joinlinie angezeigten Symbole aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="952c6-114">The following table lists the icons that appear in the join line.</span></span>  
  
|<span data-ttu-id="952c6-115">**Joinliniensymbol**</span><span class="sxs-lookup"><span data-stu-id="952c6-115">**Join line icon**</span></span>|<span data-ttu-id="952c6-116">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="952c6-116">**Description**</span></span>|  
|------------------------|---------------------|  
|<span data-ttu-id="952c6-117">![Visual Database Tools (Symbol)](../../database-engine/media//dv3wbih.gif "Visual Database Tools (Symbol)")</span><span class="sxs-lookup"><span data-stu-id="952c6-117">![Visual Database Tools icon](../../database-engine/media//dv3wbih.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="952c6-118">Innerer Join (erstellt mit einem Gleichheitszeichen).</span><span class="sxs-lookup"><span data-stu-id="952c6-118">Inner join (created using an equal sign).</span></span>|  
|<span data-ttu-id="952c6-119">![Visual Database Tools (Symbol)](../../database-engine/media//dv3wbii.gif "Visual Database Tools (Symbol)")</span><span class="sxs-lookup"><span data-stu-id="952c6-119">![Visual Database Tools icon](../../database-engine/media//dv3wbii.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="952c6-120">Innerer Join mit dem Operator "größer als".</span><span class="sxs-lookup"><span data-stu-id="952c6-120">Inner join based on the "greater than" operator.</span></span>|  
|<span data-ttu-id="952c6-121">![Visual Database Tools (Symbol)](../../database-engine/media//dv3wbij.gif "Visual Database Tools (Symbol)")</span><span class="sxs-lookup"><span data-stu-id="952c6-121">![Visual Database Tools icon](../../database-engine/media//dv3wbij.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="952c6-122">Äußerer Join, bei dem sämtliche Zeilen aus der links angezeigten Tabelle aufgenommen werden, auch wenn keine Übereinstimmungen in der verknüpften Tabelle vorliegen.</span><span class="sxs-lookup"><span data-stu-id="952c6-122">Outer join in which all rows from the table represented on the left will be included, even if they do not have matches in the related table.</span></span>|  
|<span data-ttu-id="952c6-123">![Visual Database Tools (Symbol)](../../database-engine/media//dv3wbik.gif "Visual Database Tools (Symbol)")</span><span class="sxs-lookup"><span data-stu-id="952c6-123">![Visual Database Tools icon](../../database-engine/media//dv3wbik.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="952c6-124">Äußerer Join, bei dem sämtliche Zeilen aus der rechts angezeigten Tabelle aufgenommen werden, auch wenn keine Übereinstimmungen in der verknüpften Tabelle vorliegen.</span><span class="sxs-lookup"><span data-stu-id="952c6-124">Outer join in which all rows from the table represented on the right will be included, even if they do not have matches in the related table.</span></span>|  
|<span data-ttu-id="952c6-125">![Visual Database Tools (Symbol)](../../database-engine/media//dv3wbil.gif "Visual Database Tools (Symbol)")</span><span class="sxs-lookup"><span data-stu-id="952c6-125">![Visual Database Tools icon](../../database-engine/media//dv3wbil.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="952c6-126">Ein vollständiger äußerer Join, bei der alle Zeilen aus beiden Tabellen aufgenommen werden, auch wenn keine Übereinstimmungen in der verknüpften Tabelle vorliegen.</span><span class="sxs-lookup"><span data-stu-id="952c6-126">Full outer join in which all rows from both tables will be included, even if they do not have matches in the related table.</span></span>|  
  
 <span data-ttu-id="952c6-127">Die Symbole an den Enden der Joinlinie zeigen den Jointyp an.</span><span class="sxs-lookup"><span data-stu-id="952c6-127">The symbols on the ends of the join line indicate the type of join.</span></span> <span data-ttu-id="952c6-128">In der folgenden Tabelle werden die Jointypen und die an den Enden der Joinslinien verwendeten Symbole aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="952c6-128">The following table lists the types of joins and the icons displayed on the ends of the join line.</span></span>  
  
|<span data-ttu-id="952c6-129">**Symbole an den Enden der Joinlinien**</span><span class="sxs-lookup"><span data-stu-id="952c6-129">**Icon on ends of join line**</span></span>|<span data-ttu-id="952c6-130">**Jointyp**</span><span class="sxs-lookup"><span data-stu-id="952c6-130">**Type of join**</span></span>|  
|-----------------------------------|----------------------|  
|<span data-ttu-id="952c6-131">![Visual Database Tools (Symbol)](../../database-engine/media//dv3wbim.gif "Visual Database Tools (Symbol)")</span><span class="sxs-lookup"><span data-stu-id="952c6-131">![Visual Database Tools icon](../../database-engine/media//dv3wbim.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="952c6-132">1:1-Join</span><span class="sxs-lookup"><span data-stu-id="952c6-132">One-to-one join.</span></span>|  
|<span data-ttu-id="952c6-133">![Visual Database Tools (Symbol)](../../database-engine/media//dv3wbin.gif "Visual Database Tools (Symbol)")</span><span class="sxs-lookup"><span data-stu-id="952c6-133">![Visual Database Tools icon](../../database-engine/media//dv3wbin.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="952c6-134">1:n-Join</span><span class="sxs-lookup"><span data-stu-id="952c6-134">One-to-many join.</span></span>|  
|<span data-ttu-id="952c6-135">![Visual Database Tools (Symbol)](../../database-engine/media//dv3wbio.gif "Visual Database Tools (Symbol)")</span><span class="sxs-lookup"><span data-stu-id="952c6-135">![Visual Database Tools icon](../../database-engine/media//dv3wbio.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="952c6-136">Der Abfrage- und Sicht-Designer konnte den Joinstyp nicht ermitteln.</span><span class="sxs-lookup"><span data-stu-id="952c6-136">Query and View Designer cannot determine the join type.</span></span> <span data-ttu-id="952c6-137">Dies tritt häufig auf, wenn Sie einen Join manuell erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="952c6-137">This situation occurs most often when you have created a join manually.</span></span>|  
  
## <a name="sql-pane"></a><span data-ttu-id="952c6-138">SQL-Bereich</span><span class="sxs-lookup"><span data-stu-id="952c6-138">SQL Pane</span></span>  
 <span data-ttu-id="952c6-139">Ein Join kann in einer SQL-Anweisung auf unterschiedliche Weise ausgedrückt werden.</span><span class="sxs-lookup"><span data-stu-id="952c6-139">A join can be expressed in a number of ways in an SQL statement.</span></span> <span data-ttu-id="952c6-140">Die genaue Syntax ergibt sich aus der verwendeten Datenbank und daraus, wie Sie den Join definiert haben.</span><span class="sxs-lookup"><span data-stu-id="952c6-140">The exact syntax depends on the database you are using and on how you have defined the join.</span></span>  
  
 <span data-ttu-id="952c6-141">Folgende Syntaxoptionen werden beim Verknüpfen von Tabellen angewendet:</span><span class="sxs-lookup"><span data-stu-id="952c6-141">Syntax options for joining tables include:</span></span>  
  
-   <span data-ttu-id="952c6-142">**JOIN-Qualifizierer in der FROM-Klausel**.</span><span class="sxs-lookup"><span data-stu-id="952c6-142">**JOIN qualifier for the FROM clause**.</span></span>   <span data-ttu-id="952c6-143">Die Schlüsselwörter INNER und OUTER geben den Jointyp an.</span><span class="sxs-lookup"><span data-stu-id="952c6-143">The keywords INNER and OUTER specify the join type.</span></span> <span data-ttu-id="952c6-144">Diese Syntax entspricht dem Standard bei ANSI 92 SQL.</span><span class="sxs-lookup"><span data-stu-id="952c6-144">This syntax is standard for ANSI 92 SQL.</span></span>  
  
     <span data-ttu-id="952c6-145">Wenn Sie z. B. die Tabellen `publishers` und `pub_info` über die Spalte `pub_id` der beiden Tabellen verknüpfen, kann dies mit folgender SQL-Anweisung ausgedrückt werden:</span><span class="sxs-lookup"><span data-stu-id="952c6-145">For example, if you join the `publishers` and `pub_info` tables based on the `pub_id` column in each table, the resulting SQL statement might look like this:</span></span>  
  
    ```  
    SELECT *  
    FROM publishers INNER JOIN pub_info ON  
       publishers.pub_id = pub_info.pub_id  
    ```  
  
     <span data-ttu-id="952c6-146">Wenn Sie einen äußeren Join erstellen, wird LEFT OUTER oder RIGHT OUTER statt INNER verwendet.</span><span class="sxs-lookup"><span data-stu-id="952c6-146">If you create an outer join, the words LEFT OUTER or RIGHT OUTER appear in place of the word INNER.</span></span>  
  
-   <span data-ttu-id="952c6-147">**WHERE-Klausel zum Vergleich der Spalten in beiden Tabellen**.</span><span class="sxs-lookup"><span data-stu-id="952c6-147">**WHERE clause compares columns in both tables**.</span></span>   <span data-ttu-id="952c6-148">Eine WHERE-Klausel wird angezeigt, wenn die Datenbank die JOIN-Syntax nicht unterstützt (oder wenn Sie sie selbst eingegeben haben).</span><span class="sxs-lookup"><span data-stu-id="952c6-148">A WHERE clause appears if the database does not support the JOIN syntax (or if you entered it yourself).</span></span> <span data-ttu-id="952c6-149">Wenn der Join über die WHERE-Klausel erstellt wird, werden beide Tabellennamen in der FROM-Klausel angegeben.</span><span class="sxs-lookup"><span data-stu-id="952c6-149">If the join is created in the WHERE clause, both table names appear in the FROM clause.</span></span>  
  
     <span data-ttu-id="952c6-150">Die folgende Anweisung verknüpft z. B. die Tabellen `publishers` und `pub_info` .</span><span class="sxs-lookup"><span data-stu-id="952c6-150">For example, the following statement joins the `publishers` and `pub_info` tables.</span></span>  
  
    ```  
    SELECT *  
    FROM publishers, pub_info  
    WHERE publishers.pub_id = pub_info.pub_id  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="952c6-151">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="952c6-151">See Also</span></span>  
 <span data-ttu-id="952c6-152">[Abfragen mit Joins &#40;Visual Database Tools&#41;](query-with-joins-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="952c6-152">[Query with Joins &#40;Visual Database Tools&#41;](query-with-joins-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="952c6-153">Verknüpfen (Dialogfeld) &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="952c6-153">Join Dialog Box &#40;Visual Database Tools&#41;</span></span>](join-dialog-box-visual-database-tools.md)  
  
  
